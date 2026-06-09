# WdsGetSystemDirectory

- ea: `0x18001c610`
- end: `0x18001c724`
- name: `WdsGetSystemDirectory`
- size: `276`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x18000179c`
- `0x18001a28c`
- `0x18001c610`
- `0x18002e468`

## import_xrefs

- `KERNEL32!GetSystemDirectoryW` at `0x18001c63c`
- `KERNEL32!GetSystemDirectoryW` at `0x18001c6be`
- `KERNEL32!GetSystemDirectoryW` at `0x18001c63c`
- `KERNEL32!GetSystemDirectoryW` at `0x18001c6be`
- `KERNEL32!GetLastError` at `0x18001c64e`
- `KERNEL32!GetLastError` at `0x18001c6ce`
- `KERNEL32!GetLastError` at `0x18001c64e`
- `KERNEL32!GetLastError` at `0x18001c6ce`

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
0x18001c610  mov     [rsp+arg_0], rbx
0x18001c615  mov     [rsp+arg_8], rbp
0x18001c61a  mov     [rsp+arg_10], rsi
0x18001c61f  push    rdi
0x18001c620  sub     rsp, 20h
0x18001c624  xor     ebx, ebx
0x18001c626  mov     rsi, rcx
0x18001c629  test    rcx, rcx
0x18001c62c  jnz     short loc_18001C638
0x18001c62e  mov     ebx, 80070057h
0x18001c633  jmp     loc_18001C70C
0x18001c638  xor     edx, edx; uSize
0x18001c63a  xor     ecx, ecx; lpBuffer
0x18001c63c  call    cs:__imp_GetSystemDirectoryW
0x18001c643  nop     dword ptr [rax+rax+00h]
0x18001c648  mov     ebp, eax
0x18001c64a  test    eax, eax
0x18001c64c  jnz     short loc_18001C688
0x18001c64e  call    cs:__imp_GetLastError
0x18001c655  nop     dword ptr [rax+rax+00h]
0x18001c65a  mov     ecx, eax
0x18001c65c  mov     r9d, 0B37h
0x18001c662  call    ElValidateWin32_8
0x18001c667  mov     ebx, eax
0x18001c669  test    eax, eax
0x18001c66b  jle     short loc_18001C676
0x18001c66d  movzx   ebx, ax
0x18001c670  or      ebx, 80070000h
0x18001c676  test    ebx, ebx
0x18001c678  js      loc_18001C70C
0x18001c67e  mov     ebx, 80004005h
0x18001c683  jmp     loc_18001C70C
0x18001c688  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001c68f  mov     eax, 2
0x18001c694  mul     rbp
0x18001c697  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001c69e  cmovo   rax, rcx
0x18001c6a2  mov     rcx, rax; unsigned __int64
0x18001c6a5  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001c6aa  mov     rdi, rax
0x18001c6ad  test    rax, rax
0x18001c6b0  jnz     short loc_18001C6B9
0x18001c6b2  mov     ebx, 8007000Eh
0x18001c6b7  jmp     short loc_18001C70C
0x18001c6b9  mov     edx, ebp; uSize
0x18001c6bb  mov     rcx, rdi; lpBuffer
0x18001c6be  call    cs:__imp_GetSystemDirectoryW
0x18001c6c5  nop     dword ptr [rax+rax+00h]
0x18001c6ca  test    eax, eax
0x18001c6cc  jnz     short loc_18001C709
0x18001c6ce  call    cs:__imp_GetLastError
0x18001c6d5  nop     dword ptr [rax+rax+00h]
0x18001c6da  mov     ecx, eax
0x18001c6dc  mov     r9d, 0B43h
0x18001c6e2  call    ElValidateWin32_8
0x18001c6e7  mov     ebx, eax
0x18001c6e9  test    eax, eax
0x18001c6eb  jle     short loc_18001C6F6
0x18001c6ed  movzx   ebx, ax
0x18001c6f0  or      ebx, 80070000h
0x18001c6f6  test    ebx, ebx
0x18001c6f8  js      short loc_18001C6FF
0x18001c6fa  mov     ebx, 80004005h
0x18001c6ff  mov     rcx, rdi; lpMem
0x18001c702  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001c707  jmp     short loc_18001C70C
0x18001c709  mov     [rsi], rdi
0x18001c70c  mov     rbp, [rsp+28h+arg_8]
0x18001c711  mov     eax, ebx
0x18001c713  mov     rbx, [rsp+28h+arg_0]
0x18001c718  mov     rsi, [rsp+28h+arg_10]
0x18001c71d  add     rsp, 20h
0x18001c721  pop     rdi
0x18001c722  retn
```
