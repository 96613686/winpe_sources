# CreateHStringFromUnicodeHGlobal(void *,HSTRING__ * *)

- ea: `0x1800238dc`
- end: `0x1800239be`
- name: `?CreateHStringFromUnicodeHGlobal@@YAJPEAXPEAPEAUHSTRING__@@@Z`
- size: `226`
- prototype: `__int64 __fastcall(HGLOBAL hMem, HSTRING *string)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180034790`
- `0x180034920`
- `0x180053c10`
- `0x180053cb0`

## callees

- `0x1800238dc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002397a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002397a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023994`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023994`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18002398c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18002398c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x1800238f0`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x1800238f0`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800238fc`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800238fc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CreateHStringFromUnicodeHGlobal(HGLOBAL hMem, HSTRING *string)
{
  SIZE_T v4; // rbx
  const WCHAR *v5; // rax
  const WCHAR *v6; // r10
  SIZE_T v7; // r8
  unsigned __int64 v8; // rdx
  signed int v9; // ecx
  unsigned __int64 v10; // r9
  int v11; // ebx
  signed int LastError; // eax

  *string = 0;
  v4 = GlobalSize(hMem);
  v5 = (const WCHAR *)GlobalLock(hMem);
  v6 = v5;
  if ( v5 )
  {
    v7 = v4 >> 1;
    v8 = v4 >> 1;
    if ( v4 >> 1 > 0x7FFFFFFF )
    {
      v9 = -2147024809;
    }
    else
    {
      if ( v4 >= 2 )
      {
        do
        {
          if ( !*v5 )
            break;
          ++v5;
          --v7;
        }
        while ( v7 );
      }
      v9 = v7 == 0 ? 0x80070057 : 0;
      if ( v7 )
        v10 = (v4 >> 1) - v7;
      else
        v10 = 0;
      if ( v7 )
        goto LABEL_13;
    }
    v10 = 0;
LABEL_13:
    if ( v9 >= 0 )
      v8 = v10;
    if ( v8 > 0xFFFFFFFF )
      v11 = -2147024362;
    else
      v11 = WindowsCreateString(v6, v8, string);
    GlobalUnlock(hMem);
    return (unsigned int)v11;
  }
  LastError = GetLastError();
  v11 = LastError;
  if ( LastError > 0 )
    v11 = (unsigned __int16)LastError | 0x80070000;
  if ( v11 >= 0 )
    return (unsigned int)-2147467259;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800238dc  push    rbx
0x1800238de  push    rbp
0x1800238df  push    rsi
0x1800238e0  push    rdi
0x1800238e1  sub     rsp, 28h
0x1800238e5  xor     ebp, ebp
0x1800238e7  mov     rsi, rdx
0x1800238ea  mov     [rdx], rbp
0x1800238ed  mov     rdi, rcx
0x1800238f0  call    cs:__imp_GlobalSize
0x1800238f6  mov     rcx, rdi; hMem
0x1800238f9  mov     rbx, rax
0x1800238fc  call    cs:__imp_GlobalLock
0x180023902  mov     r10, rax
0x180023905  test    rax, rax
0x180023908  jz      loc_180023994
0x18002390e  mov     r8, rbx
0x180023911  shr     r8, 1
0x180023914  mov     rdx, r8
0x180023917  cmp     r8, 7FFFFFFFh
0x18002391e  ja      short loc_18002395C
0x180023920  mov     r9, r8
0x180023923  cmp     rbx, 2
0x180023927  jb      short loc_180023938
0x180023929  cmp     [rax], bp
0x18002392c  jz      short loc_180023938
0x18002392e  add     rax, 2
0x180023932  sub     r8, 1
0x180023936  jnz     short loc_180023929
0x180023938  mov     rax, r8
0x18002393b  neg     rax
0x18002393e  sbb     ecx, ecx
0x180023940  not     ecx
0x180023942  and     ecx, 80070057h
0x180023948  test    r8, r8
0x18002394b  jz      short loc_180023952
0x18002394d  sub     r9, r8
0x180023950  jmp     short loc_180023955
0x180023952  mov     r9, rbp
0x180023955  test    r8, r8
0x180023958  jz      short loc_180023961
0x18002395a  jmp     short loc_180023964
0x18002395c  mov     ecx, 80070057h
0x180023961  mov     r9, rbp
0x180023964  test    ecx, ecx
0x180023966  mov     eax, 0FFFFFFFFh
0x18002396b  cmovns  rdx, r9; length
0x18002396f  cmp     rdx, rax
0x180023972  ja      short loc_180023984
0x180023974  mov     r8, rsi; string
0x180023977  mov     rcx, r10; sourceString
0x18002397a  call    cs:__imp_WindowsCreateString
0x180023980  mov     ebx, eax
0x180023982  jmp     short loc_180023989
0x180023984  mov     ebx, 80070216h
0x180023989  mov     rcx, rdi; hMem
0x18002398c  call    cs:__imp_GlobalUnlock
0x180023992  jmp     short loc_1800239B3
0x180023994  call    cs:__imp_GetLastError
0x18002399a  mov     ebx, eax
0x18002399c  test    eax, eax
0x18002399e  jle     short loc_1800239A9
0x1800239a0  movzx   ebx, ax
0x1800239a3  or      ebx, 80070000h
0x1800239a9  test    ebx, ebx
0x1800239ab  mov     eax, 80004005h
0x1800239b0  cmovns  ebx, eax
0x1800239b3  mov     eax, ebx
0x1800239b5  add     rsp, 28h
0x1800239b9  pop     rdi
0x1800239ba  pop     rsi
0x1800239bb  pop     rbp
0x1800239bc  pop     rbx
0x1800239bd  retn
```
