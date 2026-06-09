# CNTFSSecurity::SetSecurityLocal(ulong,void *,int)

- ea: `0x180007a58`
- end: `0x180007cd9`
- name: `?SetSecurityLocal@CNTFSSecurity@@IEAAJKPEAXH@Z`
- size: `641`
- prototype: `__int64 __fastcall(CNTFSSecurity *this, int, void *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180007950`

## callees

- `0x180007a58`
- `0x18001d322`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180007bb2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180007bb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ac5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ac5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c83`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007cac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007cb5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007cac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007cb5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007b01`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007b35`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007b6d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007b01`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007b35`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007b6d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180007bee`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180007bee`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180007c74`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180007c74`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007c9c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007c9c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180007abb`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180007abb`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180007b21`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180007b57`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180007b21`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180007b57`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180007af1`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180007af1`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x180007c5f`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x180007c5f`
- `USER32!DispatchMessageW` at `0x180007c49`
- `USER32!DispatchMessageW` at `0x180007c49`
- `USER32!TranslateMessage` at `0x180007c3f`
- `USER32!TranslateMessage` at `0x180007c3f`
- `USER32!PeekMessageW` at `0x180007c31`
- `USER32!PeekMessageW` at `0x180007c31`

## pseudocode

```c
__int64 __fastcall CNTFSSecurity::SetSecurityLocal(CNTFSSecurity *this, int a2, void *a3, int a4)
{
  void *v9; // rdi
  HLOCAL v10; // r14
  unsigned int v11; // ebx
  signed int LastError; // eax
  HLOCAL v13; // rax
  _DWORD *v14; // rax
  HANDLE EventW; // rax
  signed int v16; // eax
  DWORD Size; // [rsp+30h] [rbp-50h] BYREF
  DWORD Size_4; // [rsp+34h] [rbp-4Ch] BYREF
  DWORD dwRevision; // [rsp+38h] [rbp-48h] BYREF
  DWORD ThreadId; // [rsp+3Ch] [rbp-44h] BYREF
  HANDLE pHandles; // [rsp+40h] [rbp-40h] BYREF
  tagMSG Msg; // [rsp+48h] [rbp-38h] BYREF
  WORD pControl; // [rsp+B8h] [rbp+38h] BYREF

  Size = 0;
  if ( !a2 )
    return 0;
  v9 = 0;
  v10 = 0;
  if ( *((_QWORD *)this + 7) )
  {
    pControl = 0;
    dwRevision = 0;
    if ( !GetSecurityDescriptorControl(a3, &pControl, &dwRevision) )
      goto LABEL_6;
    if ( (pControl & 0x8000u) == 0 )
    {
      MakeSelfRelativeSD(a3, 0, &Size);
      if ( !Size )
        goto LABEL_6;
      v13 = LocalAlloc(0x40u, Size);
      v10 = v13;
      if ( !v13 )
        goto LABEL_12;
      if ( !MakeSelfRelativeSD(a3, v13, &Size) )
      {
LABEL_6:
        LastError = GetLastError();
        v11 = LastError;
        if ( LastError > 0 )
          v11 = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_28;
      }
    }
    else
    {
      Size = GetSecurityDescriptorLength(a3);
      v10 = LocalAlloc(0x40u, Size);
      memcpy_0(v10, a3, Size);
    }
    v14 = LocalAlloc(0x40u, 0x28u);
    v9 = v14;
    if ( v14 )
    {
      *v14 = a2;
      *((_QWORD *)v14 + 1) = this;
      *((_QWORD *)v14 + 2) = v10;
      v14[6] = 0;
      v14[8] = (a4 != 0) + 1;
      if ( *((_QWORD *)this + 49) || (EventW = CreateEventW(0, 0, 1, 0), (*((_QWORD *)this + 49) = EventW) != 0) )
      {
        ThreadId = 0;
        pHandles = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)CNTFSSecurity::TreeSetSecurityThread, v9, 0, &ThreadId);
        if ( pHandles )
        {
          while ( MsgWaitForMultipleObjectsEx(1u, &pHandles, 0xFFFFFFFF, 0x1CFFu, 4u) )
          {
            memset(&Msg, 0, sizeof(Msg));
            if ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
            {
              TranslateMessage(&Msg);
              DispatchMessageW(&Msg);
            }
          }
          Size_4 = 0;
          if ( GetExitCodeThread(pHandles, &Size_4) )
          {
            v11 = Size_4;
          }
          else
          {
            v16 = GetLastError();
            v11 = v16;
            if ( v16 > 0 )
              v11 = (unsigned __int16)v16 | 0x80070000;
          }
          CloseHandle(pHandles);
        }
        else
        {
          v11 = -2147467259;
        }
        goto LABEL_28;
      }
      goto LABEL_6;
    }
LABEL_12:
    v11 = -2147024882;
    goto LABEL_28;
  }
  v11 = -2147418113;
LABEL_28:
  LocalFree(v9);
  LocalFree(v10);
  return v11;
}

```

## disassembly

```asm
0x180007a58  mov     [rsp-28h+arg_0], rbx
0x180007a5d  mov     [rsp-28h+arg_10], rsi
0x180007a62  push    rbp
0x180007a63  push    rdi
0x180007a64  push    r12
0x180007a66  push    r14
0x180007a68  push    r15
0x180007a6a  mov     rbp, rsp
0x180007a6d  sub     rsp, 80h
0x180007a74  mov     dword ptr [rbp+Size], 0
0x180007a7b  mov     r12d, r9d
0x180007a7e  mov     rsi, r8
0x180007a81  mov     r15d, edx
0x180007a84  mov     rbx, rcx
0x180007a87  test    edx, edx
0x180007a89  jnz     short loc_180007A92
0x180007a8b  xor     eax, eax
0x180007a8d  jmp     loc_180007CBD
0x180007a92  xor     edi, edi
0x180007a94  xor     r14d, r14d
0x180007a97  cmp     [rcx+38h], rdi
0x180007a9b  jnz     short loc_180007AA7
0x180007a9d  mov     ebx, 8000FFFFh
0x180007aa2  jmp     loc_180007CA9
0x180007aa7  xor     eax, eax
0x180007aa9  lea     r8, [rbp+dwRevision]; lpdwRevision
0x180007aad  lea     rdx, [rbp+pControl]; pControl
0x180007ab1  mov     [rbp+pControl], ax
0x180007ab5  mov     rcx, rsi; pSecurityDescriptor
0x180007ab8  mov     [rbp+dwRevision], eax
0x180007abb  call    cs:__imp_GetSecurityDescriptorControl
0x180007ac1  test    eax, eax
0x180007ac3  jnz     short loc_180007AE3
0x180007ac5  call    cs:__imp_GetLastError
0x180007acb  mov     ebx, eax
0x180007acd  test    eax, eax
0x180007acf  jle     loc_180007CA9
0x180007ad5  movzx   ebx, ax
0x180007ad8  or      ebx, 80070000h
0x180007ade  jmp     loc_180007CA9
0x180007ae3  mov     eax, 8000h
0x180007ae8  mov     rcx, rsi; pAbsoluteSecurityDescriptor
0x180007aeb  test    [rbp+pControl], ax
0x180007aef  jz      short loc_180007B1B
0x180007af1  call    cs:__imp_GetSecurityDescriptorLength
0x180007af7  mov     edx, eax; uBytes
0x180007af9  mov     ecx, 40h ; '@'; uFlags
0x180007afe  mov     dword ptr [rbp+Size], edx
0x180007b01  call    cs:__imp_LocalAlloc
0x180007b07  mov     r8d, dword ptr [rbp+Size]; Size
0x180007b0b  mov     rdx, rsi; Src
0x180007b0e  mov     rcx, rax; void *
0x180007b11  mov     r14, rax
0x180007b14  call    memcpy_0
0x180007b19  jmp     short loc_180007B65
0x180007b1b  lea     r8, [rbp+Size]; lpdwBufferLength
0x180007b1f  xor     edx, edx; pSelfRelativeSecurityDescriptor
0x180007b21  call    cs:__imp_MakeSelfRelativeSD
0x180007b27  mov     eax, dword ptr [rbp+Size]
0x180007b2a  test    eax, eax
0x180007b2c  jz      short loc_180007AC5
0x180007b2e  mov     edx, eax; uBytes
0x180007b30  mov     ecx, 40h ; '@'; uFlags
0x180007b35  call    cs:__imp_LocalAlloc
0x180007b3b  mov     r14, rax
0x180007b3e  test    rax, rax
0x180007b41  jnz     short loc_180007B4D
0x180007b43  mov     ebx, 8007000Eh
0x180007b48  jmp     loc_180007CA9
0x180007b4d  lea     r8, [rbp+Size]; lpdwBufferLength
0x180007b51  mov     rdx, rax; pSelfRelativeSecurityDescriptor
0x180007b54  mov     rcx, rsi; pAbsoluteSecurityDescriptor
0x180007b57  call    cs:__imp_MakeSelfRelativeSD
0x180007b5d  test    eax, eax
0x180007b5f  jz      loc_180007AC5
0x180007b65  mov     edx, 28h ; '('; uBytes
0x180007b6a  lea     ecx, [rdx+18h]; uFlags
0x180007b6d  call    cs:__imp_LocalAlloc
0x180007b73  mov     rdi, rax
0x180007b76  test    rax, rax
0x180007b79  jz      short loc_180007B43
0x180007b7b  mov     [rax], r15d
0x180007b7e  neg     r12d
0x180007b81  mov     [rax+8], rbx
0x180007b85  mov     esi, 1
0x180007b8a  mov     [rax+10h], r14
0x180007b8e  mov     dword ptr [rax+18h], 0
0x180007b95  sbb     eax, eax
0x180007b97  neg     eax
0x180007b99  add     eax, esi
0x180007b9b  mov     [rdi+20h], eax
0x180007b9e  cmp     qword ptr [rbx+188h], 0
0x180007ba6  jnz     short loc_180007BC8
0x180007ba8  xor     r9d, r9d; lpName
0x180007bab  mov     r8d, esi; bInitialState
0x180007bae  xor     edx, edx; bManualReset
0x180007bb0  xor     ecx, ecx; lpEventAttributes
0x180007bb2  call    cs:__imp_CreateEventW
0x180007bb8  mov     [rbx+188h], rax
0x180007bbf  test    rax, rax
0x180007bc2  jz      loc_180007AC5
0x180007bc8  lea     rax, [rbp+ThreadId]
0x180007bcc  mov     [rbp+ThreadId], 0
0x180007bd3  mov     [rsp+80h+lpThreadId], rax; lpThreadId
0x180007bd8  lea     r8, ?TreeSetSecurityThread@CNTFSSecurity@@KAKPEAX@Z; lpStartAddress
0x180007bdf  mov     r9, rdi; lpParameter
0x180007be2  mov     [rsp+80h+dwCreationFlags], 0; dwCreationFlags
0x180007bea  xor     edx, edx; dwStackSize
0x180007bec  xor     ecx, ecx; lpThreadAttributes
0x180007bee  call    cs:__imp_CreateThread
0x180007bf4  mov     [rbp+pHandles], rax
0x180007bf8  test    rax, rax
0x180007bfb  jz      loc_180007CA4
0x180007c01  mov     ebx, 4
0x180007c06  mov     r15d, 1CFFh
0x180007c0c  or      r12d, 0FFFFFFFFh
0x180007c10  jmp     short loc_180007C4F
0x180007c12  xorps   xmm0, xmm0
0x180007c15  mov     [rsp+80h+dwCreationFlags], esi; wRemoveMsg
0x180007c19  xor     r9d, r9d; wMsgFilterMax
0x180007c1c  lea     rcx, [rbp+Msg]; lpMsg
0x180007c20  xor     r8d, r8d; wMsgFilterMin
0x180007c23  xor     edx, edx; hWnd
0x180007c25  movups  xmmword ptr [rbp+Msg.hwnd], xmm0
0x180007c29  movups  xmmword ptr [rbp+Msg.wParam], xmm0
0x180007c2d  movups  xmmword ptr [rbp+Msg.time], xmm0
0x180007c31  call    cs:__imp_PeekMessageW
0x180007c37  test    eax, eax
0x180007c39  jz      short loc_180007C4F
0x180007c3b  lea     rcx, [rbp+Msg]; lpMsg
0x180007c3f  call    cs:__imp_TranslateMessage
0x180007c45  lea     rcx, [rbp+Msg]; lpMsg
0x180007c49  call    cs:__imp_DispatchMessageW
0x180007c4f  mov     r9d, r15d; dwWakeMask
0x180007c52  mov     [rsp+80h+dwCreationFlags], ebx; dwFlags
0x180007c56  mov     r8d, r12d; dwMilliseconds
0x180007c59  lea     rdx, [rbp+pHandles]; pHandles
0x180007c5d  mov     ecx, esi; nCount
0x180007c5f  call    cs:__imp_MsgWaitForMultipleObjectsEx
0x180007c65  test    eax, eax
0x180007c67  jnz     short loc_180007C12
0x180007c69  mov     rcx, [rbp+pHandles]; hThread
0x180007c6d  lea     rdx, [rbp+Size+4]; lpExitCode
0x180007c71  mov     dword ptr [rbp+Size+4], eax
0x180007c74  call    cs:__imp_GetExitCodeThread
0x180007c7a  test    eax, eax
0x180007c7c  jz      short loc_180007C83
0x180007c7e  mov     ebx, dword ptr [rbp+Size+4]
0x180007c81  jmp     short loc_180007C98
0x180007c83  call    cs:__imp_GetLastError
0x180007c89  mov     ebx, eax
0x180007c8b  test    eax, eax
0x180007c8d  jle     short loc_180007C98
0x180007c8f  movzx   ebx, ax
0x180007c92  or      ebx, 80070000h
0x180007c98  mov     rcx, [rbp+pHandles]; hObject
0x180007c9c  call    cs:__imp_CloseHandle
0x180007ca2  jmp     short loc_180007CA9
0x180007ca4  mov     ebx, 80004005h
0x180007ca9  mov     rcx, rdi; hMem
0x180007cac  call    cs:__imp_LocalFree
0x180007cb2  mov     rcx, r14; hMem
0x180007cb5  call    cs:__imp_LocalFree
0x180007cbb  mov     eax, ebx
0x180007cbd  lea     r11, [rsp+80h+var_s0]
0x180007cc5  mov     rbx, [r11+30h]
0x180007cc9  mov     rsi, [r11+40h]
0x180007ccd  mov     rsp, r11
0x180007cd0  pop     r15
0x180007cd2  pop     r14
0x180007cd4  pop     r12
0x180007cd6  pop     rdi
0x180007cd7  pop     rbp
0x180007cd8  retn
```
