# WdsGetSystemDirectory

- ea: `0x18001d510`
- end: `0x18001d62b`
- name: `WdsGetSystemDirectory`
- size: `283`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x18000214c`
- `0x18001b0cc`
- `0x18001d510`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001d602`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001d602`
- `KERNEL32!GetSystemDirectoryW` at `0x18001d53c`
- `KERNEL32!GetSystemDirectoryW` at `0x18001d5be`
- `KERNEL32!GetSystemDirectoryW` at `0x18001d53c`
- `KERNEL32!GetSystemDirectoryW` at `0x18001d5be`
- `KERNEL32!GetLastError` at `0x18001d54e`
- `KERNEL32!GetLastError` at `0x18001d5ce`
- `KERNEL32!GetLastError` at `0x18001d54e`
- `KERNEL32!GetLastError` at `0x18001d5ce`

## pseudocode

```c
__int64 __fastcall WdsGetSystemDirectory(WCHAR **a1)
{
  signed int v1; // ebx
  UINT SystemDirectoryW; // eax
  unsigned __int64 v4; // rbp
  DWORD v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  int v8; // eax
  unsigned __int64 v9; // rax
  WCHAR *v10; // rax
  WCHAR *v11; // rdi
  DWORD LastError; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  int v15; // eax

  v1 = 0;
  if ( a1 )
  {
    SystemDirectoryW = GetSystemDirectoryW(0, 0);
    v4 = SystemDirectoryW;
    if ( SystemDirectoryW )
    {
      v9 = 2LL * SystemDirectoryW;
      if ( !is_mul_ok(v4, 2u) )
        v9 = -1;
      v10 = (WCHAR *)operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
      v11 = v10;
      if ( v10 )
      {
        if ( GetSystemDirectoryW(v10, v4) )
        {
          *a1 = v11;
        }
        else
        {
          LastError = GetLastError();
          v15 = ElValidateWin32_8(LastError, v13, v14, 2883);
          v1 = v15;
          if ( v15 > 0 )
            v1 = (unsigned __int16)v15 | 0x80070000;
          if ( v1 >= 0 )
            v1 = -2147467259;
          operator delete(v11);
        }
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
    else
    {
      v5 = GetLastError();
      v8 = ElValidateWin32_8(v5, v6, v7, 2871);
      v1 = v8;
      if ( v8 > 0 )
        v1 = (unsigned __int16)v8 | 0x80070000;
      if ( v1 >= 0 )
        return (unsigned int)-2147467259;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18001d510  mov     [rsp+arg_0], rbx
0x18001d515  mov     [rsp+arg_8], rbp
0x18001d51a  mov     [rsp+arg_10], rsi
0x18001d51f  push    rdi
0x18001d520  sub     rsp, 20h
0x18001d524  xor     ebx, ebx
0x18001d526  mov     rsi, rcx
0x18001d529  test    rcx, rcx
0x18001d52c  jnz     short loc_18001D538
0x18001d52e  mov     ebx, 80070057h
0x18001d533  jmp     loc_18001D613
0x18001d538  xor     edx, edx; uSize
0x18001d53a  xor     ecx, ecx; lpBuffer
0x18001d53c  call    cs:__imp_GetSystemDirectoryW
0x18001d543  nop     dword ptr [rax+rax+00h]
0x18001d548  mov     ebp, eax
0x18001d54a  test    eax, eax
0x18001d54c  jnz     short loc_18001D588
0x18001d54e  call    cs:__imp_GetLastError
0x18001d555  nop     dword ptr [rax+rax+00h]
0x18001d55a  mov     ecx, eax
0x18001d55c  mov     r9d, 0B37h
0x18001d562  call    ElValidateWin32_8
0x18001d567  mov     ebx, eax
0x18001d569  test    eax, eax
0x18001d56b  jle     short loc_18001D576
0x18001d56d  movzx   ebx, ax
0x18001d570  or      ebx, 80070000h
0x18001d576  test    ebx, ebx
0x18001d578  js      loc_18001D613
0x18001d57e  mov     ebx, 80004005h
0x18001d583  jmp     loc_18001D613
0x18001d588  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001d58f  mov     eax, 2
0x18001d594  mul     rbp
0x18001d597  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001d59e  cmovo   rax, rcx
0x18001d5a2  mov     rcx, rax; unsigned __int64
0x18001d5a5  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001d5aa  mov     rdi, rax
0x18001d5ad  test    rax, rax
0x18001d5b0  jnz     short loc_18001D5B9
0x18001d5b2  mov     ebx, 8007000Eh
0x18001d5b7  jmp     short loc_18001D613
0x18001d5b9  mov     edx, ebp; uSize
0x18001d5bb  mov     rcx, rdi; lpBuffer
0x18001d5be  call    cs:__imp_GetSystemDirectoryW
0x18001d5c5  nop     dword ptr [rax+rax+00h]
0x18001d5ca  test    eax, eax
0x18001d5cc  jnz     short loc_18001D610
0x18001d5ce  call    cs:__imp_GetLastError
0x18001d5d5  nop     dword ptr [rax+rax+00h]
0x18001d5da  mov     ecx, eax
0x18001d5dc  mov     r9d, 0B43h
0x18001d5e2  call    ElValidateWin32_8
0x18001d5e7  mov     ebx, eax
0x18001d5e9  test    eax, eax
0x18001d5eb  jle     short loc_18001D5F6
0x18001d5ed  movzx   ebx, ax
0x18001d5f0  or      ebx, 80070000h
0x18001d5f6  test    ebx, ebx
0x18001d5f8  js      short loc_18001D5FF
0x18001d5fa  mov     ebx, 80004005h
0x18001d5ff  mov     rcx, rdi
0x18001d602  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001d609  nop     dword ptr [rax+rax+00h]
0x18001d60e  jmp     short loc_18001D613
0x18001d610  mov     [rsi], rdi
0x18001d613  mov     rbp, [rsp+28h+arg_8]
0x18001d618  mov     eax, ebx
0x18001d61a  mov     rbx, [rsp+28h+arg_0]
0x18001d61f  mov     rsi, [rsp+28h+arg_10]
0x18001d624  add     rsp, 20h
0x18001d628  pop     rdi
0x18001d629  retn
```
