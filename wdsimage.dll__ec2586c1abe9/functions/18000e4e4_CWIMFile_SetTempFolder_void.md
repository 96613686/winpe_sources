# CWIMFile::SetTempFolder(void)

- ea: `0x18000e4e4`
- end: `0x18000e5e9`
- name: `?SetTempFolder@CWIMFile@@AEAAKXZ`
- size: `261`
- prototype: `unsigned int __fastcall(CWIMFile *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000e39c`

## callees

- `0x1800015d8`
- `0x18000e4e4`
- `0x18000e688`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000e5c4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000e5c4`
- `KERNEL32!GetTempPathW` at `0x18000e502`
- `KERNEL32!GetTempPathW` at `0x18000e56c`
- `KERNEL32!GetTempPathW` at `0x18000e502`
- `KERNEL32!GetTempPathW` at `0x18000e56c`
- `KERNEL32!GetLastError` at `0x18000e514`
- `KERNEL32!GetLastError` at `0x18000e57c`
- `KERNEL32!GetLastError` at `0x18000e5a6`
- `KERNEL32!GetLastError` at `0x18000e514`
- `KERNEL32!GetLastError` at `0x18000e57c`
- `KERNEL32!GetLastError` at `0x18000e5a6`
- `WIMGAPI!WIMSetTemporaryPath` at `0x18000e596`
- `WIMGAPI!WIMSetTemporaryPath` at `0x18000e596`

## pseudocode

```c
__int64 __fastcall CWIMFile::SetTempFolder(CWIMFile *this)
{
  unsigned int v2; // ebx
  DWORD TempPathW; // edi
  DWORD v4; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  DWORD v7; // edi
  unsigned __int64 v8; // rax
  WCHAR *v9; // rax
  WCHAR *v10; // rsi
  DWORD LastError; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9

  v2 = 0;
  TempPathW = GetTempPathW(0, 0);
  if ( TempPathW )
  {
    v7 = TempPathW + 1;
    v8 = 2LL * v7;
    if ( !is_mul_ok(v7, 2u) )
      v8 = -1;
    v9 = (WCHAR *)operator new[](v8, (const struct std::nothrow_t *)&std::nothrow);
    v10 = v9;
    if ( !v9 )
      return 8;
    if ( GetTempPathW(v7, v9) )
    {
      if ( (unsigned int)WIMSetTemporaryPath(*(_QWORD *)this, v10) )
      {
LABEL_12:
        operator delete(v10);
        return v2;
      }
      LastError = GetLastError();
      v14 = 203;
    }
    else
    {
      LastError = GetLastError();
      v14 = 197;
    }
    v2 = ElValidateWin32_5(LastError, v12, v13, v14);
    goto LABEL_12;
  }
  v4 = GetLastError();
  return (unsigned int)ElValidateWin32_5(v4, v5, v6, 183);
}

```

## disassembly

```asm
0x18000e4e4  mov     [rsp+arg_0], rbx
0x18000e4e9  mov     [rsp+arg_8], rsi
0x18000e4ee  mov     [rsp+arg_10], rdi
0x18000e4f3  push    r14
0x18000e4f5  sub     rsp, 20h
0x18000e4f9  mov     r14, rcx
0x18000e4fc  xor     edx, edx; lpBuffer
0x18000e4fe  xor     ecx, ecx; nBufferLength
0x18000e500  xor     ebx, ebx
0x18000e502  call    cs:__imp_GetTempPathW
0x18000e509  nop     dword ptr [rax+rax+00h]
0x18000e50e  mov     edi, eax
0x18000e510  test    eax, eax
0x18000e512  jnz     short loc_18000E534
0x18000e514  call    cs:__imp_GetLastError
0x18000e51b  nop     dword ptr [rax+rax+00h]
0x18000e520  mov     ecx, eax
0x18000e522  mov     r9d, 0B7h
0x18000e528  call    ElValidateWin32_5
0x18000e52d  mov     ebx, eax
0x18000e52f  jmp     loc_18000E5D0
0x18000e534  inc     edi
0x18000e536  mov     eax, 2
0x18000e53b  mov     ecx, edi
0x18000e53d  mul     rcx
0x18000e540  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000e547  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000e54e  cmovo   rax, rcx
0x18000e552  mov     rcx, rax; unsigned __int64
0x18000e555  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000e55a  mov     rsi, rax
0x18000e55d  test    rax, rax
0x18000e560  jnz     short loc_18000E567
0x18000e562  lea     ebx, [rax+8]
0x18000e565  jmp     short loc_18000E5D0
0x18000e567  mov     rdx, rsi; lpBuffer
0x18000e56a  mov     ecx, edi; nBufferLength
0x18000e56c  call    cs:__imp_GetTempPathW
0x18000e573  nop     dword ptr [rax+rax+00h]
0x18000e578  test    eax, eax
0x18000e57a  jnz     short loc_18000E590
0x18000e57c  call    cs:__imp_GetLastError
0x18000e583  nop     dword ptr [rax+rax+00h]
0x18000e588  mov     r9d, 0C5h
0x18000e58e  jmp     short loc_18000E5B8
0x18000e590  mov     rcx, [r14]
0x18000e593  mov     rdx, rsi
0x18000e596  call    cs:__imp_WIMSetTemporaryPath
0x18000e59d  nop     dword ptr [rax+rax+00h]
0x18000e5a2  test    eax, eax
0x18000e5a4  jnz     short loc_18000E5C1
0x18000e5a6  call    cs:__imp_GetLastError
0x18000e5ad  nop     dword ptr [rax+rax+00h]
0x18000e5b2  mov     r9d, 0CBh
0x18000e5b8  mov     ecx, eax
0x18000e5ba  call    ElValidateWin32_5
0x18000e5bf  mov     ebx, eax
0x18000e5c1  mov     rcx, rsi
0x18000e5c4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000e5cb  nop     dword ptr [rax+rax+00h]
0x18000e5d0  mov     rsi, [rsp+28h+arg_8]
0x18000e5d5  mov     eax, ebx
0x18000e5d7  mov     rbx, [rsp+28h+arg_0]
0x18000e5dc  mov     rdi, [rsp+28h+arg_10]
0x18000e5e1  add     rsp, 20h
0x18000e5e5  pop     r14
0x18000e5e7  retn
```
