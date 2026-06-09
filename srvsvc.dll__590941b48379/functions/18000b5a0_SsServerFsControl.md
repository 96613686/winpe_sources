# SsServerFsControl

- ea: `0x18000b5a0`
- end: `0x18000b932`
- name: `SsServerFsControl`
- size: `914`
- prototype: `__int64 __usercall@<rax>(ULONG FsControlCode@<ecx>, int)`
- caller_count: `9`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001cb8`
- `0x18000b4c0`
- `0x180012f20`
- `0x180014880`
- `0x180015500`
- `0x18002c110`
- `0x18002e6d4`
- `0x18002e7f4`
- `0x18002ea20`

## callees

- `0x18000ae90`
- `0x18000b5a0`
- `0x18002ecf4`
- `0x18002ed48`
- `0x1800435f8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b767`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b767`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b927`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b927`
- `ntdll!NtCreateEvent` at `0x18000b628`
- `ntdll!NtCreateEvent` at `0x18000b628`
- `ntdll!NtWaitForSingleObject` at `0x18000b70a`
- `ntdll!NtWaitForSingleObject` at `0x18000b70a`
- `ntdll!NtFsControlFile` at `0x18000b665`
- `ntdll!NtFsControlFile` at `0x18000b665`
- `ntdll!NtClose` at `0x18000b67e`
- `ntdll!NtClose` at `0x18000b67e`

## pseudocode

```c
__int64 __fastcall SsServerFsControl(ULONG FsControlCode, __int64 a2, void *a3, ULONG a4, char a5)
{
  HANDLE v5; // rbx
  _OWORD *InputBuffer; // rsi
  ULONG InputBufferLength; // r13d
  __int64 v12; // rdx
  __int64 v13; // r8
  int Status; // r12d
  unsigned int v15; // ebx
  __int64 result; // rax
  __int64 v17; // rcx
  __int64 v18; // rax
  _OWORD *v19; // rax
  char *v20; // r12
  __int64 v21; // rdx
  char *v22; // r9
  __int64 v23; // rdx
  __int64 v24; // rax
  void *EventHandle; // [rsp+50h] [rbp-58h] BYREF
  __int64 v26; // [rsp+58h] [rbp-50h]
  __int64 v27; // [rsp+60h] [rbp-48h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp-40h] BYREF

  v5 = Handle;
  EventHandle = 0;
  if ( (a5 & 1) != 0 )
    v5 = FileHandle;
  IoStatusBlock = 0;
  if ( v5 )
  {
    if ( a2 )
    {
      v17 = *(_QWORD *)(a2 + 8);
      v18 = *(_QWORD *)(a2 + 24);
      v26 = v17;
      v27 = v18;
      if ( v17 || v18 )
      {
        InputBufferLength = 96;
        if ( v17 )
          InputBufferLength = *(unsigned __int16 *)(a2 + 2) + 96;
        if ( v18 )
          InputBufferLength += *(unsigned __int16 *)(a2 + 18);
        v19 = LocalAlloc(0x40u, InputBufferLength);
        InputBuffer = v19;
        if ( !v19 )
          return 8;
        v20 = (char *)(v19 + 6);
        *v19 = *(_OWORD *)a2;
        v19[1] = *(_OWORD *)(a2 + 16);
        v19[2] = *(_OWORD *)(a2 + 32);
        v19[3] = *(_OWORD *)(a2 + 48);
        v19[4] = *(_OWORD *)(a2 + 64);
        v19[5] = *(_OWORD *)(a2 + 80);
        if ( *(_QWORD *)(a2 + 8) )
        {
          *(_WORD *)v19 = *(_WORD *)a2;
          *((_WORD *)v19 + 1) = *(_WORD *)(a2 + 2);
          *((_QWORD *)v19 + 1) = v20;
          memcpy_0(v19 + 6, *(const void **)(a2 + 8), *(unsigned __int16 *)(a2 + 2));
          v21 = *((_QWORD *)InputBuffer + 1) - (_QWORD)InputBuffer;
          v22 = &v20[*(unsigned __int16 *)(a2 + 2)];
          if ( !*((_QWORD *)InputBuffer + 1) )
            v21 = 0;
          *((_QWORD *)InputBuffer + 1) = v21;
        }
        else
        {
          v22 = (char *)(v19 + 6);
        }
        if ( *(_QWORD *)(a2 + 24) )
        {
          *((_WORD *)InputBuffer + 8) = *(_WORD *)(a2 + 16);
          *((_WORD *)InputBuffer + 9) = *(_WORD *)(a2 + 18);
          *((_QWORD *)InputBuffer + 3) = v22;
          memcpy_0(v22, *(const void **)(a2 + 24), *(unsigned __int16 *)(a2 + 18));
          v23 = *((_QWORD *)InputBuffer + 3) - (_QWORD)InputBuffer;
          if ( !*((_QWORD *)InputBuffer + 3) )
            v23 = 0;
          *((_QWORD *)InputBuffer + 3) = v23;
        }
      }
      else
      {
        InputBuffer = (_OWORD *)a2;
        InputBufferLength = 96;
      }
    }
    else
    {
      v26 = 0;
      InputBuffer = 0;
      v27 = 0;
      InputBufferLength = 0;
    }
    Status = NtCreateEvent(&EventHandle, 0x1F01FFu, 0, NotificationEvent, 0);
    if ( Status >= 0 )
    {
      Status = NtFsControlFile(
                 v5,
                 EventHandle,
                 0,
                 0,
                 &IoStatusBlock,
                 FsControlCode,
                 InputBuffer,
                 InputBufferLength,
                 a3,
                 a4);
      if ( Status == 259 )
        NtWaitForSingleObject(EventHandle, 0, 0);
      NtClose(EventHandle);
    }
    if ( InputBuffer )
    {
      v15 = *((_DWORD *)InputBuffer + 17);
      if ( v15 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_Ll(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, v13, FsControlCode, *((_DWORD *)InputBuffer + 17));
        }
        goto LABEL_13;
      }
    }
    if ( Status >= 0 )
      Status = IoStatusBlock.Status;
    if ( Status == -2147483612 )
    {
      v15 = 1811;
    }
    else
    {
      v15 = NetpNtStatusToApiStatus(Status);
      if ( !v15 )
      {
LABEL_13:
        if ( InputBuffer != (_OWORD *)a2 )
        {
          v24 = v26;
          *(_OWORD *)a2 = *InputBuffer;
          *(_OWORD *)(a2 + 16) = InputBuffer[1];
          *(_OWORD *)(a2 + 32) = InputBuffer[2];
          *(_OWORD *)(a2 + 48) = InputBuffer[3];
          *(_OWORD *)(a2 + 64) = InputBuffer[4];
          *(_OWORD *)(a2 + 80) = InputBuffer[5];
          *(_QWORD *)(a2 + 8) = v24;
          *(_QWORD *)(a2 + 24) = v27;
          LocalFree(InputBuffer);
        }
        return v15;
      }
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_LlD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, v13, FsControlCode, v15, Status);
    }
    goto LABEL_13;
  }
  result = 58;
  if ( (a5 & 1) == 0 )
    return 3023;
  return result;
}

```

## disassembly

```asm
0x18000b5a0  mov     r11, rsp
0x18000b5a3  push    rbx
0x18000b5a4  push    rbp
0x18000b5a5  push    rdi
0x18000b5a6  push    r14
0x18000b5a8  push    r15
0x18000b5aa  sub     rsp, 80h
0x18000b5b1  mov     r10d, [rsp+0A8h+arg_20]
0x18000b5b9  xor     eax, eax
0x18000b5bb  mov     rbx, cs:Handle
0x18000b5c2  and     r10d, 1
0x18000b5c6  xorps   xmm0, xmm0
0x18000b5c9  mov     [r11-58h], rax
0x18000b5cd  cmovnz  rbx, cs:FileHandle
0x18000b5d5  mov     ebp, r9d
0x18000b5d8  mov     r14, r8
0x18000b5db  mov     rdi, rdx
0x18000b5de  mov     r15d, ecx
0x18000b5e1  movups  xmmword ptr [rsp+0A8h+IoStatusBlock], xmm0
0x18000b5e6  test    rbx, rbx
0x18000b5e9  jz      loc_18000B6E1
0x18000b5ef  mov     [r11+8], rsi
0x18000b5f3  mov     [r11+10h], r12
0x18000b5f7  mov     [r11+18h], r13
0x18000b5fb  test    rdx, rdx
0x18000b5fe  jnz     loc_18000B715
0x18000b604  mov     [rsp+0A8h+var_50], rax
0x18000b609  mov     esi, eax
0x18000b60b  mov     [rsp+0A8h+var_48], rax
0x18000b610  mov     r13d, eax
0x18000b613  xor     r9d, r9d; EventType
0x18000b616  mov     [rsp+0A8h+InitialState], 0; InitialState
0x18000b61b  xor     r8d, r8d; ObjectAttributes
0x18000b61e  lea     rcx, [rsp+0A8h+EventHandle]; EventHandle
0x18000b623  mov     edx, 1F01FFh; DesiredAccess
0x18000b628  call    cs:__imp_NtCreateEvent
0x18000b62e  mov     r12d, eax
0x18000b631  test    eax, eax
0x18000b633  js      short loc_18000B684
0x18000b635  mov     rdx, [rsp+0A8h+EventHandle]; Event
0x18000b63a  lea     rax, [rsp+0A8h+IoStatusBlock]
0x18000b63f  mov     [rsp+0A8h+OutputBufferLength], ebp; OutputBufferLength
0x18000b643  xor     r9d, r9d; ApcContext
0x18000b646  mov     [rsp+0A8h+OutputBuffer], r14; OutputBuffer
0x18000b64b  xor     r8d, r8d; ApcRoutine
0x18000b64e  mov     [rsp+0A8h+InputBufferLength], r13d; InputBufferLength
0x18000b653  mov     rcx, rbx; FileHandle
0x18000b656  mov     [rsp+0A8h+InputBuffer], rsi; InputBuffer
0x18000b65b  mov     [rsp+0A8h+FsControlCode], r15d; FsControlCode
0x18000b660  mov     qword ptr [rsp+0A8h+InitialState], rax; IoStatusBlock
0x18000b665  call    cs:__imp_NtFsControlFile
0x18000b66b  mov     r12d, eax
0x18000b66e  cmp     eax, 103h
0x18000b673  jz      loc_18000B700
0x18000b679  mov     rcx, [rsp+0A8h+EventHandle]; Handle
0x18000b67e  call    cs:__imp_NtClose
0x18000b684  test    rsi, rsi
0x18000b687  jz      loc_18000B874
0x18000b68d  mov     ebx, [rsi+44h]
0x18000b690  test    ebx, ebx
0x18000b692  jz      loc_18000B874
0x18000b698  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b69f  lea     rax, WPP_GLOBAL_Control
0x18000b6a6  cmp     rcx, rax
0x18000b6a9  jnz     loc_18000B84B
0x18000b6af  cmp     rsi, rdi
0x18000b6b2  jnz     loc_18000B8E4
0x18000b6b8  mov     eax, ebx
0x18000b6ba  mov     r12, [rsp+0A8h+arg_8]
0x18000b6c2  mov     rsi, [rsp+0A8h+arg_0]
0x18000b6ca  mov     r13, [rsp+0A8h+arg_10]
0x18000b6d2  add     rsp, 80h
0x18000b6d9  pop     r15
0x18000b6db  pop     r14
0x18000b6dd  pop     rdi
0x18000b6de  pop     rbp
0x18000b6df  pop     rbx
0x18000b6e0  retn
0x18000b6e1  test    r10d, r10d
0x18000b6e4  mov     eax, 3Ah ; ':'
0x18000b6e9  mov     ecx, 0BCFh
0x18000b6ee  cmovz   eax, ecx
0x18000b6f1  add     rsp, 80h
0x18000b6f8  pop     r15
0x18000b6fa  pop     r14
0x18000b6fc  pop     rdi
0x18000b6fd  pop     rbp
0x18000b6fe  pop     rbx
0x18000b6ff  retn
0x18000b700  mov     rcx, [rsp+0A8h+EventHandle]; Handle
0x18000b705  xor     r8d, r8d; Timeout
0x18000b708  xor     edx, edx; Alertable
0x18000b70a  call    cs:__imp_NtWaitForSingleObject
0x18000b710  jmp     loc_18000B679
0x18000b715  mov     rcx, [rdx+8]
0x18000b719  mov     rax, [rdx+18h]
0x18000b71d  mov     [rsp+0A8h+var_50], rcx
0x18000b722  mov     [rsp+0A8h+var_48], rax
0x18000b727  test    rcx, rcx
0x18000b72a  jnz     short loc_18000B73F
0x18000b72c  test    rax, rax
0x18000b72f  jnz     short loc_18000B73F
0x18000b731  mov     rsi, rdi
0x18000b734  mov     r13d, 60h ; '`'
0x18000b73a  jmp     loc_18000B613
0x18000b73f  mov     r13d, 60h ; '`'
0x18000b745  test    rcx, rcx
0x18000b748  jz      short loc_18000B753
0x18000b74a  movzx   r13d, word ptr [rdx+2]
0x18000b74f  add     r13d, 60h ; '`'
0x18000b753  test    rax, rax
0x18000b756  jz      short loc_18000B75F
0x18000b758  movzx   eax, word ptr [rdx+12h]
0x18000b75c  add     r13d, eax
0x18000b75f  mov     edx, r13d; uBytes
0x18000b762  mov     ecx, 40h ; '@'; uFlags
0x18000b767  call    cs:__imp_LocalAlloc
0x18000b76d  mov     rsi, rax
0x18000b770  test    rax, rax
0x18000b773  jnz     short loc_18000B77F
0x18000b775  mov     eax, 8
0x18000b77a  jmp     loc_18000B6BA
0x18000b77f  movups  xmm0, xmmword ptr [rdi]
0x18000b782  lea     r12, [rax+60h]
0x18000b786  movups  xmmword ptr [rax], xmm0
0x18000b789  movups  xmm1, xmmword ptr [rdi+10h]
0x18000b78d  movups  xmmword ptr [rax+10h], xmm1
0x18000b791  movups  xmm0, xmmword ptr [rdi+20h]
0x18000b795  movups  xmmword ptr [rax+20h], xmm0
0x18000b799  movups  xmm1, xmmword ptr [rdi+30h]
0x18000b79d  movups  xmmword ptr [rax+30h], xmm1
0x18000b7a1  movups  xmm0, xmmword ptr [rdi+40h]
0x18000b7a5  movups  xmmword ptr [rax+40h], xmm0
0x18000b7a9  movups  xmm1, xmmword ptr [rdi+50h]
0x18000b7ad  movups  xmmword ptr [rax+50h], xmm1
0x18000b7b1  cmp     qword ptr [rdi+8], 0
0x18000b7b6  jz      short loc_18000B7FC
0x18000b7b8  movzx   eax, word ptr [rdi]
0x18000b7bb  mov     rcx, r12; void *
0x18000b7be  mov     [rsi], ax
0x18000b7c1  movzx   eax, word ptr [rdi+2]
0x18000b7c5  mov     [rsi+2], ax
0x18000b7c9  mov     [rsi+8], r12
0x18000b7cd  movzx   r8d, word ptr [rdi+2]; Size
0x18000b7d2  mov     rdx, [rdi+8]; Src
0x18000b7d6  call    memcpy_0
0x18000b7db  mov     rax, [rsi+8]
0x18000b7df  xor     ecx, ecx
0x18000b7e1  movzx   r9d, word ptr [rdi+2]
0x18000b7e6  mov     rdx, rax
0x18000b7e9  sub     rdx, rsi
0x18000b7ec  add     r9, r12
0x18000b7ef  test    rax, rax
0x18000b7f2  cmovz   rdx, rcx
0x18000b7f6  mov     [rsi+8], rdx
0x18000b7fa  jmp     short loc_18000B7FF
0x18000b7fc  mov     r9, r12
0x18000b7ff  cmp     qword ptr [rdi+18h], 0
0x18000b804  jz      loc_18000B613
0x18000b80a  movzx   eax, word ptr [rdi+10h]
0x18000b80e  mov     rcx, r9; void *
0x18000b811  mov     [rsi+10h], ax
0x18000b815  movzx   eax, word ptr [rdi+12h]
0x18000b819  mov     [rsi+12h], ax
0x18000b81d  mov     [rsi+18h], r9
0x18000b821  movzx   r8d, word ptr [rdi+12h]; Size
0x18000b826  mov     rdx, [rdi+18h]; Src
0x18000b82a  call    memcpy_0
0x18000b82f  mov     rax, [rsi+18h]
0x18000b833  xor     ecx, ecx
0x18000b835  mov     rdx, rax
0x18000b838  sub     rdx, rsi
0x18000b83b  test    rax, rax
0x18000b83e  cmovz   rdx, rcx
0x18000b842  mov     [rsi+18h], rdx
0x18000b846  jmp     loc_18000B613
0x18000b84b  test    byte ptr [rcx+1Ch], 8
0x18000b84f  jz      loc_18000B6AF
0x18000b855  cmp     byte ptr [rcx+19h], 1
0x18000b859  jb      loc_18000B6AF
0x18000b85f  mov     rcx, [rcx+10h]
0x18000b863  mov     r9d, r15d
0x18000b866  mov     dword ptr [rsp+0A8h+InitialState], ebx
0x18000b86a  call    WPP_SF_Ll
0x18000b86f  jmp     loc_18000B6AF
0x18000b874  test    r12d, r12d
0x18000b877  cmovns  r12d, dword ptr [rsp+0A8h+IoStatusBlock]
0x18000b87d  cmp     r12d, 80000024h
0x18000b884  jnz     short loc_18000B88D
0x18000b886  mov     ebx, 713h
0x18000b88b  jmp     short loc_18000B89F
0x18000b88d  mov     ecx, r12d; Status
0x18000b890  call    NetpNtStatusToApiStatus
0x18000b895  mov     ebx, eax
0x18000b897  test    eax, eax
0x18000b899  jz      loc_18000B6AF
0x18000b89f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b8a6  lea     rax, WPP_GLOBAL_Control
0x18000b8ad  cmp     rcx, rax
0x18000b8b0  jz      loc_18000B6AF
0x18000b8b6  test    byte ptr [rcx+1Ch], 8
0x18000b8ba  jz      loc_18000B6AF
0x18000b8c0  cmp     byte ptr [rcx+19h], 1
0x18000b8c4  jb      loc_18000B6AF
0x18000b8ca  mov     rcx, [rcx+10h]
0x18000b8ce  mov     r9d, r15d
0x18000b8d1  mov     [rsp+0A8h+FsControlCode], r12d
0x18000b8d6  mov     dword ptr [rsp+0A8h+InitialState], ebx
0x18000b8da  call    WPP_SF_LlD
0x18000b8df  jmp     loc_18000B6AF
0x18000b8e4  movups  xmm0, xmmword ptr [rsi]
0x18000b8e7  mov     rax, [rsp+0A8h+var_50]
0x18000b8ec  mov     rcx, rsi; hMem
0x18000b8ef  movups  xmmword ptr [rdi], xmm0
0x18000b8f2  movups  xmm1, xmmword ptr [rsi+10h]
0x18000b8f6  movups  xmmword ptr [rdi+10h], xmm1
0x18000b8fa  movups  xmm0, xmmword ptr [rsi+20h]
0x18000b8fe  movups  xmmword ptr [rdi+20h], xmm0
0x18000b902  movups  xmm1, xmmword ptr [rsi+30h]
0x18000b906  movups  xmmword ptr [rdi+30h], xmm1
0x18000b90a  movups  xmm0, xmmword ptr [rsi+40h]
0x18000b90e  movups  xmmword ptr [rdi+40h], xmm0
0x18000b912  movups  xmm1, xmmword ptr [rsi+50h]
0x18000b916  movups  xmmword ptr [rdi+50h], xmm1
0x18000b91a  mov     [rdi+8], rax
0x18000b91e  mov     rax, [rsp+0A8h+var_48]
0x18000b923  mov     [rdi+18h], rax
0x18000b927  call    cs:__imp_LocalFree
0x18000b92d  jmp     loc_18000B6B8
```
