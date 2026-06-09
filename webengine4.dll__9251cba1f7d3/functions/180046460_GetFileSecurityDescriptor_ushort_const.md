# GetFileSecurityDescriptor(ushort const *)

- ea: `0x180046460`
- end: `0x18004655f`
- name: `?GetFileSecurityDescriptor@@YAPEAXPEBG@Z`
- size: `255`
- prototype: `void *__fastcall(LPCWSTR lpFileName)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180046460`
- `0x180046ed4`
- `0x18004d350`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180046536`
- `KERNEL32!CloseHandle` at `0x180046536`
- `KERNEL32!GetLastError` at `0x1800464bf`
- `KERNEL32!GetLastError` at `0x1800464bf`
- `KERNEL32!CreateFileW` at `0x1800464b1`
- `KERNEL32!CreateFileW` at `0x180046509`
- `KERNEL32!CreateFileW` at `0x1800464b1`
- `KERNEL32!CreateFileW` at `0x180046509`
- `KERNEL32!GetFileAttributesW` at `0x1800464d5`
- `KERNEL32!GetFileAttributesW` at `0x1800464d5`

## pseudocode

```c
__int64 __fastcall GetFileSecurityDescriptor(LPCWSTR lpFileName)
{
  __int64 v2; // rbx
  HANDLE FileW; // rsi
  DWORD LastError; // eax
  DWORD FileAttributesW; // eax
  int LastWin32Error; // edi
  void *v8; // [rsp+50h] [rbp+8h] BYREF

  v2 = -1;
  v8 = (void *)-1LL;
  if ( !lpFileName )
    return -1;
  FileW = CreateFileW(lpFileName, 0x80000000, 7u, 0, 3u, 0x80u, 0);
  if ( FileW != (HANDLE)-1LL )
    goto LABEL_11;
  LastError = GetLastError();
  if ( LastError - 2 <= 1 || LastError == 123 )
    return 0;
  FileAttributesW = GetFileAttributesW(lpFileName);
  if ( FileAttributesW == -1
    || (FileAttributesW & 0x10) == 0
    || (FileW = CreateFileW(lpFileName, 0x80000000, 5u, 0, 3u, 0x2000000u, 0), FileW == (HANDLE)-1LL) )
  {
    LastWin32Error = GetLastWin32Error();
  }
  else
  {
LABEL_11:
    LastWin32Error = GetSecurityDescriptor(FileW, &v8);
    CloseHandle(FileW);
    v2 = (__int64)v8;
  }
  if ( LastWin32Error )
    return -1;
  return v2;
}

```

## disassembly

```asm
0x180046460  mov     rax, rsp
0x180046463  mov     [rax+10h], rbx
0x180046467  mov     [rax+18h], rbp
0x18004646b  mov     [rax+20h], rsi
0x18004646f  push    rdi
0x180046470  sub     rsp, 40h
0x180046474  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180046478  mov     rdi, rcx
0x18004647b  mov     rbx, rbp
0x18004647e  mov     [rax+8], rbx
0x180046482  test    rcx, rcx
0x180046485  jnz     short loc_18004648F
0x180046487  mov     rax, rbp
0x18004648a  jmp     loc_18004654A
0x18004648f  and     [rsp+48h+var_18], 0
0x180046495  xor     r9d, r9d; lpSecurityAttributes
0x180046498  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800464a0  mov     edx, 80000000h; dwDesiredAccess
0x1800464a5  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x1800464ad  lea     r8d, [r9+7]; dwShareMode
0x1800464b1  call    cs:__imp_CreateFileW
0x1800464b7  mov     rsi, rax
0x1800464ba  cmp     rax, rbp
0x1800464bd  jnz     short loc_180046524
0x1800464bf  call    cs:__imp_GetLastError
0x1800464c5  lea     ecx, [rax-2]
0x1800464c8  cmp     ecx, 1
0x1800464cb  jbe     short loc_180046520
0x1800464cd  cmp     eax, 7Bh ; '{'
0x1800464d0  jz      short loc_180046520
0x1800464d2  mov     rcx, rdi; lpFileName
0x1800464d5  call    cs:__imp_GetFileAttributesW
0x1800464db  cmp     eax, 0FFFFFFFFh
0x1800464de  jz      short loc_180046517
0x1800464e0  test    al, 10h
0x1800464e2  jz      short loc_180046517
0x1800464e4  and     [rsp+48h+var_18], 0
0x1800464ea  xor     r9d, r9d; lpSecurityAttributes
0x1800464ed  mov     [rsp+48h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x1800464f5  mov     edx, 80000000h; dwDesiredAccess
0x1800464fa  mov     rcx, rdi; lpFileName
0x1800464fd  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180046505  lea     r8d, [r9+5]; dwShareMode
0x180046509  call    cs:__imp_CreateFileW
0x18004650f  mov     rsi, rax
0x180046512  cmp     rax, rbp
0x180046515  jnz     short loc_180046524
0x180046517  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18004651c  mov     edi, eax
0x18004651e  jmp     short loc_180046541
0x180046520  xor     eax, eax
0x180046522  jmp     short loc_18004654A
0x180046524  lea     rdx, [rsp+48h+arg_0]; void **
0x180046529  mov     rcx, rsi; Handle
0x18004652c  call    ?GetSecurityDescriptor@@YAJPEAXPEAPEAX@Z; GetSecurityDescriptor(void *,void * *)
0x180046531  mov     edi, eax
0x180046533  mov     rcx, rsi; hObject
0x180046536  call    cs:__imp_CloseHandle
0x18004653c  mov     rbx, [rsp+48h+arg_0]
0x180046541  test    edi, edi
0x180046543  cmovnz  rbx, rbp
0x180046547  mov     rax, rbx
0x18004654a  mov     rbx, [rsp+48h+arg_8]
0x18004654f  mov     rbp, [rsp+48h+arg_10]
0x180046554  mov     rsi, [rsp+48h+arg_18]
0x180046559  add     rsp, 40h
0x18004655d  pop     rdi
0x18004655e  retn
```
