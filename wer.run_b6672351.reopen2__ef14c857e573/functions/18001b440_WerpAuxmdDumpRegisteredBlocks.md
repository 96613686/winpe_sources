# WerpAuxmdDumpRegisteredBlocks

- ea: `0x18001b440`
- end: `0x18001b6c6`
- name: `WerpAuxmdDumpRegisteredBlocks`
- size: `646`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18001b440`
- `0x18001b6cc`
- `0x18001c368`
- `0x18002dc4c`
- `0x180042734`
- `0x18006f9b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b4dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b62e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b4dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b62e`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18001b4cc`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18001b61e`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18001b4cc`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18001b61e`

## pseudocode

```c
__int64 __fastcall WerpAuxmdDumpRegisteredBlocks(__int64 a1)
{
  void *v1; // rdi
  unsigned int v3; // r12d
  int GatherListStart; // eax
  __int64 v5; // rbx
  int v6; // eax
  DWORD LastError; // eax
  __int64 v8; // rdx
  __int64 v9; // rax
  __int64 v10; // r8
  void *v11; // rdi
  DWORD v12; // eax
  __int128 Buffer; // [rsp+40h] [rbp-20h] BYREF
  __int128 v15; // [rsp+50h] [rbp-10h]
  LPCVOID lpBaseAddress; // [rsp+B0h] [rbp+50h] BYREF
  SIZE_T NumberOfBytesRead; // [rsp+B8h] [rbp+58h] BYREF

  v1 = *(void **)a1;
  v3 = 0;
  lpBaseAddress = 0;
  NumberOfBytesRead = 0;
  Buffer = 0;
  v15 = 0;
  GatherListStart = WerpGetGatherListStart(v1, (struct WER_GATHER **)&lpBaseAddress);
  v5 = (__int64)lpBaseAddress;
  if ( GatherListStart >= 0 )
  {
    if ( lpBaseAddress )
    {
      if ( lpBaseAddress == (LPCVOID)-1LL )
      {
        v6 = -2147024637;
      }
      else if ( ReadProcessMemory(v1, lpBaseAddress, &Buffer, 0x20u, &NumberOfBytesRead) )
      {
        if ( NumberOfBytesRead == 32 )
        {
          v5 = Buffer;
          if ( !(_QWORD)Buffer )
            v5 = -1;
          v6 = 0;
          lpBaseAddress = (LPCVOID)v5;
        }
        else
        {
          v6 = -2147024597;
        }
      }
      else
      {
        LastError = GetLastError();
        v6 = ERROR_HR_FROM_WIN32(LastError);
      }
    }
    else
    {
      v6 = -2147023728;
    }
    while ( 1 )
    {
      if ( v6 < 0 )
        goto LABEL_34;
      if ( (WORD4(Buffer) & 0xC000) == 0 && DWORD2(v15) <= 0x10000 )
      {
        v8 = *(unsigned int *)(a1 + 44);
        v9 = v8 + DWORD2(v15);
        v10 = ~(v8 - 1);
        if ( (v10 & (unsigned __int64)(v9 + v15 - 1)) > ((unsigned __int64)v15 & v10) )
        {
          WerpAuxmdpDumpRegisteredBlock(a1, v10 & (v9 + v15 - 1));
          ++v3;
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 8) != 0 )
            WPP_SF_DDDDD(*((_QWORD *)WPP_GLOBAL_Control + 2));
        }
      }
      v11 = *(void **)a1;
      NumberOfBytesRead = 0;
      Buffer = 0;
      v15 = 0;
      if ( v5 )
        break;
      v6 = WerpGetGatherListStart(v11, (struct WER_GATHER **)&lpBaseAddress);
      v5 = (__int64)lpBaseAddress;
      if ( v6 >= 0 )
      {
        if ( lpBaseAddress )
          break;
        v6 = -2147023728;
      }
LABEL_33:
      if ( v3 >= 0x200 )
        goto LABEL_34;
    }
    if ( v5 == -1 )
    {
      v6 = -2147024637;
    }
    else if ( ReadProcessMemory(v11, (LPCVOID)v5, &Buffer, 0x20u, &NumberOfBytesRead) )
    {
      if ( NumberOfBytesRead == 32 )
      {
        v5 = Buffer;
        if ( !(_QWORD)Buffer )
          v5 = -1;
        v6 = 0;
        lpBaseAddress = (LPCVOID)v5;
      }
      else
      {
        v6 = -2147024597;
      }
    }
    else
    {
      v12 = GetLastError();
      v6 = ERROR_HR_FROM_WIN32(v12);
    }
    goto LABEL_33;
  }
LABEL_34:
  *(_DWORD *)(a1 + 4160) = v3;
  *(_DWORD *)(a1 + 4164) = 0;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 8) != 0 )
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_78df9e3b89b83f0cbcd64e4857b7b890_Traceguids, 0, v3);
  return 0;
}

```

## disassembly

```asm
0x18001b440  push    rbp
0x18001b442  push    rbx
0x18001b443  push    rsi
0x18001b444  push    rdi
0x18001b445  push    r12
0x18001b447  push    r14
0x18001b449  push    r15
0x18001b44b  mov     rbp, rsp
0x18001b44e  sub     rsp, 60h
0x18001b452  mov     rdi, [rcx]
0x18001b455  lea     rdx, [rbp+lpBaseAddress]; struct WER_GATHER **
0x18001b459  xorps   xmm0, xmm0
0x18001b45c  mov     [rbp+arg_8], 0
0x18001b463  mov     r15, rcx
0x18001b466  mov     [rbp+arg_0], 0
0x18001b46d  xor     r14d, r14d
0x18001b470  xor     r12d, r12d
0x18001b473  mov     rcx, rdi; void *
0x18001b476  mov     [rbp+lpBaseAddress], r14
0x18001b47a  mov     [rbp+NumberOfBytesRead], r12
0x18001b47e  movups  [rbp+Buffer], xmm0
0x18001b482  movups  [rbp+var_10], xmm0
0x18001b486  call    ?WerpGetGatherListStart@@YAJPEAXPEAPEAUWER_GATHER@@@Z; WerpGetGatherListStart(void *,WER_GATHER * *)
0x18001b48b  mov     rbx, [rbp+lpBaseAddress]
0x18001b48f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001b493  test    eax, eax
0x18001b495  js      loc_18001B66F
0x18001b49b  test    rbx, rbx
0x18001b49e  jnz     short loc_18001B4A7
0x18001b4a0  mov     eax, 80070490h
0x18001b4a5  jmp     short loc_18001B510
0x18001b4a7  cmp     rbx, rsi
0x18001b4aa  jnz     short loc_18001B4B3
0x18001b4ac  mov     eax, 80070103h
0x18001b4b1  jmp     short loc_18001B510
0x18001b4b3  lea     rax, [rbp+NumberOfBytesRead]
0x18001b4b7  mov     r9d, 20h ; ' '; nSize
0x18001b4bd  lea     r8, [rbp+Buffer]; lpBuffer
0x18001b4c1  mov     [rsp+60h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x18001b4c6  mov     rdx, rbx; lpBaseAddress
0x18001b4c9  mov     rcx, rdi; hProcess
0x18001b4cc  call    cs:__imp_ReadProcessMemory
0x18001b4d3  nop     dword ptr [rax+rax+00h]
0x18001b4d8  test    eax, eax
0x18001b4da  jnz     short loc_18001B4F1
0x18001b4dc  call    cs:__imp_GetLastError
0x18001b4e3  nop     dword ptr [rax+rax+00h]
0x18001b4e8  mov     ecx, eax; unsigned int
0x18001b4ea  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18001b4ef  jmp     short loc_18001B510
0x18001b4f1  cmp     [rbp+NumberOfBytesRead], 20h ; ' '
0x18001b4f6  jz      short loc_18001B4FF
0x18001b4f8  mov     eax, 8007012Bh
0x18001b4fd  jmp     short loc_18001B510
0x18001b4ff  mov     rbx, qword ptr [rbp+Buffer]
0x18001b503  test    rbx, rbx
0x18001b506  cmovz   rbx, rsi
0x18001b50a  xor     eax, eax
0x18001b50c  mov     [rbp+lpBaseAddress], rbx
0x18001b510  test    eax, eax
0x18001b512  js      loc_18001B66F
0x18001b518  mov     eax, 0C000h
0x18001b51d  test    word ptr [rbp+Buffer+8], ax
0x18001b521  jnz     loc_18001B5BE
0x18001b527  cmp     dword ptr [rbp+var_10+8], 10000h
0x18001b52e  ja      loc_18001B5BE
0x18001b534  mov     edx, [r15+2Ch]
0x18001b538  mov     rcx, qword ptr [rbp+var_10]
0x18001b53c  mov     eax, dword ptr [rbp+var_10+8]
0x18001b53f  add     rax, rdx
0x18001b542  lea     r8, [rdx-1]
0x18001b546  not     r8
0x18001b549  lea     rdi, [rcx-1]
0x18001b54d  add     rdi, rax
0x18001b550  mov     rsi, r8
0x18001b553  and     rsi, rcx
0x18001b556  and     rdi, r8
0x18001b559  cmp     rdi, rsi
0x18001b55c  jbe     short loc_18001B5BA
0x18001b55e  mov     r9, rsi
0x18001b561  mov     [rsp+60h+lpNumberOfBytesRead], rdi; __int64
0x18001b566  lea     r8, [rbp+arg_8]
0x18001b56a  mov     rcx, r15; int
0x18001b56d  lea     rdx, [rbp+arg_0]
0x18001b571  call    WerpAuxmdpDumpRegisteredBlock
0x18001b576  mov     r9d, [rbp+arg_0]
0x18001b57a  mov     edx, eax
0x18001b57c  add     r14d, r9d
0x18001b57f  inc     r12d
0x18001b582  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b589  lea     rax, WPP_GLOBAL_Control
0x18001b590  cmp     rcx, rax
0x18001b593  jz      short loc_18001B5BA
0x18001b595  test    byte ptr [rcx+1Ch], 8
0x18001b599  jz      short loc_18001B5BA
0x18001b59b  mov     eax, [rbp+arg_8]
0x18001b59e  sub     edi, esi
0x18001b5a0  mov     rcx, [rcx+10h]
0x18001b5a4  mov     [rsp+60h+var_28], eax
0x18001b5a8  mov     [rsp+60h+var_30], edx
0x18001b5ac  mov     [rsp+60h+var_38], r12d
0x18001b5b1  mov     dword ptr [rsp+60h+lpNumberOfBytesRead], edi
0x18001b5b5  call    WPP_SF_DDDDD
0x18001b5ba  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001b5be  mov     rdi, [r15]
0x18001b5c1  xorps   xmm0, xmm0
0x18001b5c4  mov     [rbp+NumberOfBytesRead], 0
0x18001b5cc  movups  [rbp+Buffer], xmm0
0x18001b5d0  movups  [rbp+var_10], xmm0
0x18001b5d4  test    rbx, rbx
0x18001b5d7  jnz     short loc_18001B5F9
0x18001b5d9  lea     rdx, [rbp+lpBaseAddress]; struct WER_GATHER **
0x18001b5dd  mov     rcx, rdi; void *
0x18001b5e0  call    ?WerpGetGatherListStart@@YAJPEAXPEAPEAUWER_GATHER@@@Z; WerpGetGatherListStart(void *,WER_GATHER * *)
0x18001b5e5  mov     rbx, [rbp+lpBaseAddress]
0x18001b5e9  test    eax, eax
0x18001b5eb  js      short loc_18001B662
0x18001b5ed  test    rbx, rbx
0x18001b5f0  jnz     short loc_18001B5F9
0x18001b5f2  mov     eax, 80070490h
0x18001b5f7  jmp     short loc_18001B662
0x18001b5f9  cmp     rbx, rsi
0x18001b5fc  jnz     short loc_18001B605
0x18001b5fe  mov     eax, 80070103h
0x18001b603  jmp     short loc_18001B662
0x18001b605  lea     rax, [rbp+NumberOfBytesRead]
0x18001b609  mov     r9d, 20h ; ' '; nSize
0x18001b60f  lea     r8, [rbp+Buffer]; lpBuffer
0x18001b613  mov     [rsp+60h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x18001b618  mov     rdx, rbx; lpBaseAddress
0x18001b61b  mov     rcx, rdi; hProcess
0x18001b61e  call    cs:__imp_ReadProcessMemory
0x18001b625  nop     dword ptr [rax+rax+00h]
0x18001b62a  test    eax, eax
0x18001b62c  jnz     short loc_18001B643
0x18001b62e  call    cs:__imp_GetLastError
0x18001b635  nop     dword ptr [rax+rax+00h]
0x18001b63a  mov     ecx, eax; unsigned int
0x18001b63c  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18001b641  jmp     short loc_18001B662
0x18001b643  cmp     [rbp+NumberOfBytesRead], 20h ; ' '
0x18001b648  jz      short loc_18001B651
0x18001b64a  mov     eax, 8007012Bh
0x18001b64f  jmp     short loc_18001B662
0x18001b651  mov     rbx, qword ptr [rbp+Buffer]
0x18001b655  test    rbx, rbx
0x18001b658  cmovz   rbx, rsi
0x18001b65c  xor     eax, eax
0x18001b65e  mov     [rbp+lpBaseAddress], rbx
0x18001b662  cmp     r12d, 200h
0x18001b669  jb      loc_18001B510
0x18001b66f  mov     [r15+1040h], r12d
0x18001b676  mov     [r15+1044h], r14d
0x18001b67d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b684  lea     rax, WPP_GLOBAL_Control
0x18001b68b  cmp     rcx, rax
0x18001b68e  jz      short loc_18001B6B3
0x18001b690  test    byte ptr [rcx+1Ch], 8
0x18001b694  jz      short loc_18001B6B3
0x18001b696  mov     rcx, [rcx+10h]
0x18001b69a  lea     r8, WPP_78df9e3b89b83f0cbcd64e4857b7b890_Traceguids
0x18001b6a1  mov     edx, 1Bh
0x18001b6a6  mov     dword ptr [rsp+60h+lpNumberOfBytesRead], r12d
0x18001b6ab  mov     r9d, r14d
0x18001b6ae  call    WPP_SF_Dd
0x18001b6b3  mov     eax, r14d
0x18001b6b6  add     rsp, 60h
0x18001b6ba  pop     r15
0x18001b6bc  pop     r14
0x18001b6be  pop     r12
0x18001b6c0  pop     rdi
0x18001b6c1  pop     rsi
0x18001b6c2  pop     rbx
0x18001b6c3  pop     rbp
0x18001b6c4  retn
```
