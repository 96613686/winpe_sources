# WdsGetCurrentDirectory

- ea: `0x18001c930`
- end: `0x18001ca58`
- name: `WdsGetCurrentDirectory`
- size: `296`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x18000214c`
- `0x18001b0cc`
- `0x18001c930`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001ca2e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001ca2e`
- `KERNEL32!GetCurrentDirectoryW` at `0x18001c95d`
- `KERNEL32!GetCurrentDirectoryW` at `0x18001c9df`
- `KERNEL32!GetCurrentDirectoryW` at `0x18001c95d`
- `KERNEL32!GetCurrentDirectoryW` at `0x18001c9df`
- `KERNEL32!GetLastError` at `0x18001c96f`
- `KERNEL32!GetLastError` at `0x18001c9ef`
- `KERNEL32!GetLastError` at `0x18001c96f`
- `KERNEL32!GetLastError` at `0x18001c9ef`

## pseudocode

```c
__int64 __fastcall WdsGetCurrentDirectory(WCHAR **a1)
{
  signed int v1; // ebx
  DWORD CurrentDirectoryW; // eax
  unsigned __int64 v4; // rdi
  DWORD v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  int v8; // eax
  unsigned __int64 v9; // rax
  WCHAR *v10; // rax
  WCHAR *v11; // rsi
  DWORD v12; // eax
  DWORD LastError; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  int v16; // eax

  v1 = 0;
  if ( a1 )
  {
    CurrentDirectoryW = GetCurrentDirectoryW(0, 0);
    v4 = CurrentDirectoryW;
    if ( CurrentDirectoryW )
    {
      v9 = 2LL * CurrentDirectoryW;
      if ( !is_mul_ok(v4, 2u) )
        v9 = -1;
      v10 = (WCHAR *)operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
      v11 = v10;
      if ( v10 )
      {
        v12 = GetCurrentDirectoryW(v4, v10);
        if ( v12 )
        {
          if ( v12 <= (unsigned int)v4 )
          {
            *a1 = v11;
            return (unsigned int)v1;
          }
          v1 = -2147024809;
        }
        else
        {
          LastError = GetLastError();
          v16 = ElValidateWin32_8(LastError, v14, v15, 2802);
          v1 = v16;
          if ( v16 > 0 )
            v1 = (unsigned __int16)v16 | 0x80070000;
          if ( v1 >= 0 )
            v1 = -2147467259;
        }
        operator delete(v11);
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
    else
    {
      v5 = GetLastError();
      v8 = ElValidateWin32_8(v5, v6, v7, 2784);
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
0x18001c930  mov     [rsp+arg_0], rbx
0x18001c935  mov     [rsp+arg_8], rsi
0x18001c93a  mov     [rsp+arg_10], rdi
0x18001c93f  push    r14
0x18001c941  sub     rsp, 20h
0x18001c945  xor     ebx, ebx
0x18001c947  mov     r14, rcx
0x18001c94a  test    rcx, rcx
0x18001c94d  jnz     short loc_18001C959
0x18001c94f  mov     ebx, 80070057h
0x18001c954  jmp     loc_18001CA3F
0x18001c959  xor     edx, edx; lpBuffer
0x18001c95b  xor     ecx, ecx; nBufferLength
0x18001c95d  call    cs:__imp_GetCurrentDirectoryW
0x18001c964  nop     dword ptr [rax+rax+00h]
0x18001c969  mov     edi, eax
0x18001c96b  test    eax, eax
0x18001c96d  jnz     short loc_18001C9A9
0x18001c96f  call    cs:__imp_GetLastError
0x18001c976  nop     dword ptr [rax+rax+00h]
0x18001c97b  mov     ecx, eax
0x18001c97d  mov     r9d, 0AE0h
0x18001c983  call    ElValidateWin32_8
0x18001c988  mov     ebx, eax
0x18001c98a  test    eax, eax
0x18001c98c  jle     short loc_18001C997
0x18001c98e  movzx   ebx, ax
0x18001c991  or      ebx, 80070000h
0x18001c997  test    ebx, ebx
0x18001c999  js      loc_18001CA3F
0x18001c99f  mov     ebx, 80004005h
0x18001c9a4  jmp     loc_18001CA3F
0x18001c9a9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001c9b0  mov     eax, 2
0x18001c9b5  mul     rdi
0x18001c9b8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001c9bf  cmovo   rax, rcx
0x18001c9c3  mov     rcx, rax; unsigned __int64
0x18001c9c6  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001c9cb  mov     rsi, rax
0x18001c9ce  test    rax, rax
0x18001c9d1  jnz     short loc_18001C9DA
0x18001c9d3  mov     ebx, 8007000Eh
0x18001c9d8  jmp     short loc_18001CA3F
0x18001c9da  mov     rdx, rsi; lpBuffer
0x18001c9dd  mov     ecx, edi; nBufferLength
0x18001c9df  call    cs:__imp_GetCurrentDirectoryW
0x18001c9e6  nop     dword ptr [rax+rax+00h]
0x18001c9eb  test    eax, eax
0x18001c9ed  jnz     short loc_18001CA22
0x18001c9ef  call    cs:__imp_GetLastError
0x18001c9f6  nop     dword ptr [rax+rax+00h]
0x18001c9fb  mov     ecx, eax
0x18001c9fd  mov     r9d, 0AF2h
0x18001ca03  call    ElValidateWin32_8
0x18001ca08  mov     ebx, eax
0x18001ca0a  test    eax, eax
0x18001ca0c  jle     short loc_18001CA17
0x18001ca0e  movzx   ebx, ax
0x18001ca11  or      ebx, 80070000h
0x18001ca17  test    ebx, ebx
0x18001ca19  js      short loc_18001CA2B
0x18001ca1b  mov     ebx, 80004005h
0x18001ca20  jmp     short loc_18001CA2B
0x18001ca22  cmp     eax, edi
0x18001ca24  jbe     short loc_18001CA3C
0x18001ca26  mov     ebx, 80070057h
0x18001ca2b  mov     rcx, rsi
0x18001ca2e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001ca35  nop     dword ptr [rax+rax+00h]
0x18001ca3a  jmp     short loc_18001CA3F
0x18001ca3c  mov     [r14], rsi
0x18001ca3f  mov     rsi, [rsp+28h+arg_8]
0x18001ca44  mov     eax, ebx
0x18001ca46  mov     rbx, [rsp+28h+arg_0]
0x18001ca4b  mov     rdi, [rsp+28h+arg_10]
0x18001ca50  add     rsp, 20h
0x18001ca54  pop     r14
0x18001ca56  retn
```
