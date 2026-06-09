# GetFileHandleFromPath

- ea: `0x180001e20`
- end: `0x180001f2b`
- name: `GetFileHandleFromPath`
- size: `267`
- prototype: `__int64 __fastcall(LPCWCH lpWideCharStr, DWORD dwDesiredAccess)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180001270`
- `0x180001300`
- `0x180001490`

## callees

- `0x180001e20`
- `0x180001f40`
- `0x18000d1c0`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x180001ee6`
- `KERNEL32!WideCharToMultiByte` at `0x180001ee6`
- `KERNEL32!CreateFileW` at `0x180001e7a`
- `KERNEL32!CreateFileW` at `0x180001e7a`
- `KERNEL32!CreateFileA` at `0x180001f15`
- `KERNEL32!CreateFileA` at `0x180001f15`

## pseudocode

```c
_BOOL8 __fastcall GetFileHandleFromPath(LPCWCH lpWideCharStr, DWORD dwDesiredAccess, __int64 *a3)
{
  HANDLE FileW; // rax
  __int64 v7; // rax
  CHAR MultiByteStr[272]; // [rsp+40h] [rbp-138h] BYREF

  *a3 = 0;
  if ( (unsigned int)IsWinNT() )
  {
    FileW = CreateFileW(lpWideCharStr, dwDesiredAccess, 1u, 0, 3u, 0x80u, 0);
LABEL_3:
    *a3 = (__int64)FileW;
    goto LABEL_4;
  }
  if ( WideCharToMultiByte(0, 0, lpWideCharStr, -1, MultiByteStr, 261, 0, 0) )
  {
    FileW = CreateFileA(MultiByteStr, dwDesiredAccess, 1u, 0, 3u, 0x80u, 0);
    goto LABEL_3;
  }
LABEL_4:
  v7 = *a3;
  if ( *a3 == -1 )
  {
    *a3 = 0;
    v7 = 0;
  }
  return v7 != 0;
}

```

## disassembly

```asm
0x180001e20  mov     [rsp+arg_18], rbx
0x180001e25  push    rbp
0x180001e26  push    rsi
0x180001e27  push    rdi
0x180001e28  sub     rsp, 160h
0x180001e2f  mov     rax, cs:__security_cookie
0x180001e36  xor     rax, rsp
0x180001e39  mov     [rsp+178h+var_28], rax
0x180001e41  xor     ebp, ebp
0x180001e43  mov     rbx, r8
0x180001e46  mov     [r8], rbp
0x180001e49  mov     esi, edx
0x180001e4b  mov     rdi, rcx
0x180001e4e  call    IsWinNT
0x180001e53  test    eax, eax
0x180001e55  jz      short loc_180001EBD
0x180001e57  mov     [rsp+178h+hTemplateFile], rbp; hTemplateFile
0x180001e5c  xor     r9d, r9d; lpSecurityAttributes
0x180001e5f  mov     [rsp+178h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180001e67  mov     r8d, 1; dwShareMode
0x180001e6d  mov     edx, esi; dwDesiredAccess
0x180001e6f  mov     [rsp+178h+dwCreationDisposition], 3; dwCreationDisposition
0x180001e77  mov     rcx, rdi; lpFileName
0x180001e7a  call    cs:__imp_CreateFileW
0x180001e80  mov     [rbx], rax
0x180001e83  mov     rax, [rbx]
0x180001e86  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180001e8a  jz      loc_180001F20
0x180001e90  test    rax, rax
0x180001e93  mov     ecx, ebp
0x180001e95  setnz   cl
0x180001e98  mov     eax, ecx
0x180001e9a  mov     rcx, [rsp+178h+var_28]
0x180001ea2  xor     rcx, rsp; StackCookie
0x180001ea5  call    __security_check_cookie
0x180001eaa  mov     rbx, [rsp+178h+arg_18]
0x180001eb2  add     rsp, 160h
0x180001eb9  pop     rdi
0x180001eba  pop     rsi
0x180001ebb  pop     rbp
0x180001ebc  retn
0x180001ebd  mov     [rsp+178h+lpUsedDefaultChar], rbp; lpUsedDefaultChar
0x180001ec2  lea     rax, [rsp+178h+MultiByteStr]
0x180001ec7  mov     [rsp+178h+hTemplateFile], rbp; lpDefaultChar
0x180001ecc  mov     r9d, 0FFFFFFFFh; cchWideChar
0x180001ed2  mov     [rsp+178h+dwFlagsAndAttributes], 105h; cbMultiByte
0x180001eda  mov     r8, rdi; lpWideCharStr
0x180001edd  xor     edx, edx; dwFlags
0x180001edf  mov     qword ptr [rsp+178h+dwCreationDisposition], rax; lpMultiByteStr
0x180001ee4  xor     ecx, ecx; CodePage
0x180001ee6  call    cs:__imp_WideCharToMultiByte
0x180001eec  test    eax, eax
0x180001eee  jz      short loc_180001E83
0x180001ef0  mov     [rsp+178h+hTemplateFile], rbp; hTemplateFile
0x180001ef5  lea     rcx, [rsp+178h+MultiByteStr]; lpFileName
0x180001efa  mov     [rsp+178h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180001f02  xor     r9d, r9d; lpSecurityAttributes
0x180001f05  mov     r8d, 1; dwShareMode
0x180001f0b  mov     [rsp+178h+dwCreationDisposition], 3; dwCreationDisposition
0x180001f13  mov     edx, esi; dwDesiredAccess
0x180001f15  call    cs:__imp_CreateFileA
0x180001f1b  jmp     loc_180001E80
0x180001f20  mov     [rbx], rbp
0x180001f23  mov     rax, rbp
0x180001f26  jmp     loc_180001E90
```
