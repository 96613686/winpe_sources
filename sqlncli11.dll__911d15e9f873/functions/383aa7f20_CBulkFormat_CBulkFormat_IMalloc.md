# CBulkFormat::CBulkFormat(IMalloc *)

- ea: `0x383aa7f20`
- end: `0x383aa80c0`
- name: `??0CBulkFormat@@QEAA@PEAUIMalloc@@@Z`
- size: `416`
- prototype: `CBulkFormat *__fastcall(CBulkFormat *__hidden this, struct IMalloc *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x383aa04a0`
- `0x383aa1b80`

## callees

- `0x3838434c0`
- `0x383aa7f20`
- `0x383aa81a0`
- `0x383ade150`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x383aa7feb`
- `KERNEL32!LoadLibraryW` at `0x383aa7feb`
- `KERNEL32!GetProcAddress` at `0x383aa801e`
- `KERNEL32!GetProcAddress` at `0x383aa801e`

## string_xrefs

- `0x383aa7fe4`: `xmlrw.dll`
- `0x383aa8017`: `CreateInfoSetReaderEx`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
CBulkFormat *__fastcall CBulkFormat::CBulkFormat(CBulkFormat *this, struct IMalloc *a2)
{
  _QWORD *v3; // rdi
  _QWORD *v4; // rbx
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  int pExceptionObject; // [rsp+20h] [rbp-38h] BYREF
  __int64 v9; // [rsp+28h] [rbp-30h]
  CBulkFormat *v10; // [rsp+30h] [rbp-28h]
  _DWORD v11[4]; // [rsp+38h] [rbp-20h] BYREF

  v9 = -2;
  v10 = this;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *(_QWORD *)this = &CBulkRecord::`vftable';
  *((_QWORD *)this + 8) = 0;
  v3 = (_QWORD *)((char *)this + 72);
  *((_QWORD *)this + 10) = (char *)this + 72;
  *((_QWORD *)this + 9) = (char *)this + 72;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  v4 = (_QWORD *)((char *)this + 104);
  *((_QWORD *)this + 14) = (char *)this + 104;
  *((_QWORD *)this + 13) = (char *)this + 104;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_BYTE *)this + 136) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_DWORD *)this + 38) = 0;
  *((_QWORD *)this + 20) = a2;
  v11[0] = 1713306798;
  v11[1] = 1246963580;
  v11[2] = 1993242558;
  v11[3] = 1034315658;
  LibraryW = LoadLibraryW(L"xmlrw.dll");
  *((_QWORD *)this + 15) = LibraryW;
  if ( !LibraryW )
  {
    pExceptionObject = 1;
    throw (CXMLRWLoadException *)&pExceptionObject;
  }
  ProcAddress = GetProcAddress(LibraryW, "CreateInfoSetReaderEx");
  if ( !ProcAddress )
  {
    pExceptionObject = 2;
    throw (CXMLRWLoadException *)&pExceptionObject;
  }
  if ( ((unsigned int (__fastcall *)(_DWORD *, char *, _QWORD))ProcAddress)(
         v11,
         (char *)this + 128,
         *((_QWORD *)this + 20)) )
  {
    pExceptionObject = 3;
    throw (CXMLRWLoadException *)&pExceptionObject;
  }
  *((_QWORD *)this + 14) = (char *)this + 104;
  *v4 = v4;
  *((_QWORD *)this + 10) = (char *)this + 72;
  *v3 = v3;
  CBulkFormat::Destroy(this);
  *((_QWORD *)this + 14) = (char *)this + 104;
  *v4 = v4;
  *((_QWORD *)this + 10) = (char *)this + 72;
  *v3 = v3;
  return this;
}

```

## disassembly

```asm
0x383aa7f20  push    r14
0x383aa7f22  sub     rsp, 50h
0x383aa7f26  mov     [rsp+58h+var_30], 0FFFFFFFFFFFFFFFEh
0x383aa7f2f  mov     [rsp+58h+arg_8], rbx
0x383aa7f34  mov     [rsp+58h+arg_10], rsi
0x383aa7f39  mov     [rsp+58h+arg_18], rdi
0x383aa7f3e  mov     rax, cs:__security_cookie
0x383aa7f45  xor     rax, rsp
0x383aa7f48  mov     [rsp+58h+var_10], rax
0x383aa7f4d  mov     rsi, rcx
0x383aa7f50  mov     [rsp+58h+var_28], rcx
0x383aa7f55  xor     ecx, ecx
0x383aa7f57  mov     [rsi+8], rcx
0x383aa7f5b  mov     [rsi+10h], rcx
0x383aa7f5f  mov     [rsi+18h], rcx
0x383aa7f63  mov     [rsi+20h], rcx
0x383aa7f67  mov     [rsi+28h], rcx
0x383aa7f6b  mov     [rsi+30h], rcx
0x383aa7f6f  mov     [rsi+38h], rcx
0x383aa7f73  lea     rax, ??_7CBulkRecord@@6B@; const CBulkRecord::`vftable'
0x383aa7f7a  mov     [rsi], rax
0x383aa7f7d  mov     [rsi+40h], rcx
0x383aa7f81  lea     rdi, [rsi+48h]
0x383aa7f85  mov     [rdi+8], rdi
0x383aa7f89  mov     [rdi], rdi
0x383aa7f8c  mov     [rsi+58h], rcx
0x383aa7f90  mov     [rsi+60h], rcx
0x383aa7f94  lea     rbx, [rsi+68h]
0x383aa7f98  mov     [rbx+8], rbx
0x383aa7f9c  mov     [rbx], rbx
0x383aa7f9f  mov     [rsi+78h], rcx
0x383aa7fa3  mov     [rsi+80h], rcx
0x383aa7faa  mov     [rsi+88h], cl
0x383aa7fb0  mov     [rsi+90h], rcx
0x383aa7fb7  mov     [rsi+98h], ecx
0x383aa7fbd  mov     [rsi+0A0h], rdx
0x383aa7fc4  mov     [rsp+58h+var_20], 661EFCAEh
0x383aa7fcc  mov     [rsp+58h+var_1C], 4A53277Ch
0x383aa7fd4  mov     [rsp+58h+var_18], 76CE77BEh
0x383aa7fdc  mov     [rsp+58h+var_14], 3DA6678Ah
0x383aa7fe4  lea     rcx, aXmlrwDll; "xmlrw.dll"
0x383aa7feb  call    cs:__imp_LoadLibraryW
0x383aa7ff1  mov     [rsi+78h], rax
0x383aa7ff5  mov     rcx, rax; hModule
0x383aa7ff8  test    rax, rax
0x383aa7ffb  jnz     short loc_383AA8017
0x383aa7ffd  mov     [rsp+58h+pExceptionObject], 1
0x383aa8005  lea     rdx, _TI1?AVCXMLRWLoadException@@; pThrowInfo
0x383aa800c  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x383aa8011  call    _CxxThrowException
0x383aa8017  lea     rdx, aCreateinfosetr; "CreateInfoSetReaderEx"
0x383aa801e  call    cs:__imp_GetProcAddress
0x383aa8024  test    rax, rax
0x383aa8027  jnz     short loc_383AA8043
0x383aa8029  mov     [rsp+58h+pExceptionObject], 2
0x383aa8031  lea     rdx, _TI1?AVCXMLRWLoadException@@; pThrowInfo
0x383aa8038  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x383aa803d  call    _CxxThrowException
0x383aa8043  mov     r8, [rsi+0A0h]
0x383aa804a  lea     rdx, [rsi+80h]
0x383aa8051  lea     rcx, [rsp+58h+var_20]
0x383aa8056  call    rax
0x383aa8058  test    eax, eax
0x383aa805a  jz      short loc_383AA8076
0x383aa805c  mov     [rsp+58h+pExceptionObject], 3
0x383aa8064  lea     rdx, _TI1?AVCXMLRWLoadException@@; pThrowInfo
0x383aa806b  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x383aa8070  call    _CxxThrowException
0x383aa8076  mov     [rbx+8], rbx
0x383aa807a  mov     [rbx], rbx
0x383aa807d  mov     [rdi+8], rdi
0x383aa8081  mov     [rdi], rdi
0x383aa8084  mov     rcx, rsi; this
0x383aa8087  call    ?Destroy@CBulkFormat@@AEAAXXZ; CBulkFormat::Destroy(void)
0x383aa808c  mov     [rbx+8], rbx
0x383aa8090  mov     [rbx], rbx
0x383aa8093  mov     [rdi+8], rdi
0x383aa8097  mov     [rdi], rdi
0x383aa809a  mov     rax, rsi
0x383aa809d  mov     rcx, [rsp+58h+var_10]
0x383aa80a2  xor     rcx, rsp; StackCookie
0x383aa80a5  call    __security_check_cookie
0x383aa80aa  mov     rbx, [rsp+58h+arg_8]
0x383aa80af  mov     rsi, [rsp+58h+arg_10]
0x383aa80b4  mov     rdi, [rsp+58h+arg_18]
0x383aa80b9  add     rsp, 50h
0x383aa80bd  pop     r14
0x383aa80bf  retn
```
