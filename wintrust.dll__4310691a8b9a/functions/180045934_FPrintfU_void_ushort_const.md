# FPrintfU(void *,ushort const *,...)

- ea: `0x180045934`
- end: `0x180045a2b`
- name: `?FPrintfU@@YAXPEAXPEBGZZ`
- size: `247`
- prototype: `void(void *, const unsigned __int16 *, ...)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180045c18`
- `0x180045e84`
- `0x180046230`
- `0x180046380`

## callees

- `0x18002d2d8`
- `0x18002ede8`
- `0x180045934`
- `0x18004deb0`
- `0x18004df40`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180045a05`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180045a05`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800459d8`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800459d8`

## pseudocode

```c
void FPrintfU(void *a1, const unsigned __int16 *a2, ...)
{
  __int64 v3; // r9
  DWORD v4; // eax
  DWORD NumberOfBytesWritten; // [rsp+48h] [rbp-C0h] BYREF
  int v6; // [rsp+4Ch] [rbp-BCh]
  CHAR MultiByteStr[2048]; // [rsp+58h] [rbp-B0h] BYREF
  wchar_t pszDest[2048]; // [rsp+858h] [rbp+750h] BYREF
  size_t *argList; // [rsp+1898h] [rbp+1790h] BYREF
  va_list va; // [rsp+1898h] [rbp+1790h]
  va_list va1; // [rsp+18A0h] [rbp+1798h] BYREF

  va_start(va1, a2);
  va_start(va, a2);
  argList = va_arg(va1, size_t *);
  v6 = 0;
  NumberOfBytesWritten = 0;
  StringVPrintfWorkerW(pszDest, 0x800u, argList, a2, va);
  v3 = -1;
  do
    ++v3;
  while ( pszDest[v3] );
  v4 = WideCharToMultiByte(0, 0, pszDest, v3 + 1, MultiByteStr, 2048, 0, 0);
  if ( v4 >= 0x800 )
    _report_rangecheckfailure();
  NumberOfBytesWritten = 0;
  MultiByteStr[v4] = 0;
  WriteFile(a1, MultiByteStr, v4, &NumberOfBytesWritten, 0);
}

```

## disassembly

```asm
0x180045934  mov     rax, rsp
0x180045937  mov     [rax+10h], rdx
0x18004593b  mov     [rax+18h], r8
0x18004593f  mov     [rax+20h], r9
0x180045943  push    rbp
0x180045944  push    rbx
0x180045945  push    rdi
0x180045946  lea     rbp, [rax-1778h]
0x18004594d  mov     eax, 1860h
0x180045952  call    _alloca_probe
0x180045957  sub     rsp, rax
0x18004595a  mov     rax, cs:__security_cookie
0x180045961  xor     rax, rsp
0x180045964  mov     [rbp+1770h+var_20], rax
0x18004596b  xor     edi, edi
0x18004596d  lea     rax, [rbp+1770h+arg_10]
0x180045974  mov     rbx, rcx
0x180045977  mov     qword ptr [rsp+1870h+NumberOfBytesWritten], rdi
0x18004597c  mov     r9, rdx; pszFormat
0x18004597f  mov     [rsp+1870h+NumberOfBytesWritten], edi
0x180045983  mov     edx, 800h; cchDest
0x180045988  mov     [rsp+1870h+argList], rax; argList
0x18004598d  lea     rcx, [rbp+1770h+pszDest]; pszDest
0x180045994  call    StringVPrintfWorkerW
0x180045999  lea     rax, [rbp+1770h+pszDest]
0x1800459a0  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800459a4  inc     r9
0x1800459a7  cmp     [rax+r9*2], di
0x1800459ac  jnz     short loc_1800459A4
0x1800459ae  mov     [rsp+1870h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x1800459b3  lea     rax, [rsp+1870h+MultiByteStr]
0x1800459b8  mov     [rsp+1870h+lpDefaultChar], rdi; lpDefaultChar
0x1800459bd  lea     r8, [rbp+1770h+pszDest]; lpWideCharStr
0x1800459c4  mov     [rsp+1870h+cbMultiByte], 800h; cbMultiByte
0x1800459cc  inc     r9d; cchWideChar
0x1800459cf  xor     edx, edx; dwFlags
0x1800459d1  mov     [rsp+1870h+argList], rax; lpMultiByteStr
0x1800459d6  xor     ecx, ecx; CodePage
0x1800459d8  call    cs:__imp_WideCharToMultiByte
0x1800459de  cmp     eax, 800h
0x1800459e3  jnb     short loc_180045A25
0x1800459e5  mov     edx, eax
0x1800459e7  lea     r9, [rsp+1870h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800459ec  mov     r8d, eax; nNumberOfBytesToWrite
0x1800459ef  mov     [rsp+1870h+NumberOfBytesWritten], edi
0x1800459f3  mov     rcx, rbx; hFile
0x1800459f6  mov     [rsp+1870h+argList], rdi; lpOverlapped
0x1800459fb  mov     [rsp+rdx+1870h+MultiByteStr], dil
0x180045a00  lea     rdx, [rsp+1870h+MultiByteStr]; lpBuffer
0x180045a05  call    cs:__imp_WriteFile
0x180045a0b  mov     rcx, [rbp+1770h+var_20]
0x180045a12  xor     rcx, rsp; StackCookie
0x180045a15  call    __security_check_cookie
0x180045a1a  add     rsp, 1860h
0x180045a21  pop     rdi
0x180045a22  pop     rbx
0x180045a23  pop     rbp
0x180045a24  retn
0x180045a25  call    __report_rangecheckfailure
```
