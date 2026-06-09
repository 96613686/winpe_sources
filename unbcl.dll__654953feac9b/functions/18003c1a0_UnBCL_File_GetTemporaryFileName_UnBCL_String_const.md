# UnBCL::File::GetTemporaryFileName(UnBCL::String const *)

- ea: `0x18003c1a0`
- end: `0x18003c396`
- name: `?GetTemporaryFileName@File@UnBCL@@SAPEAVString@2@PEBV32@@Z`
- size: `502`
- prototype: `struct UnBCL::String *__fastcall(const struct UnBCL::String *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x180029980`

## callees

- `0x18000225c`
- `0x180002ca0`
- `0x180002f50`
- `0x180002f90`
- `0x180009e7c`
- `0x180011570`
- `0x18002d0e0`
- `0x18003c1a0`
- `0x1800477d0`
- `0x18004b0a0`
- `0x18005b650`
- `0x18005b790`
- `0x180064340`
- `0x180069020`

## import_xrefs

- `KERNEL32!GetTempFileNameW` at `0x18003c287`
- `KERNEL32!GetTempFileNameW` at `0x18003c287`
- `KERNEL32!GetLastError` at `0x18003c306`
- `KERNEL32!GetLastError` at `0x18003c306`

## string_xrefs

- `0x18003c326`: `class UnBCL::String *__cdecl UnBCL::File::GetTemporaryFileName(const class UnBCL::String *)`
- `0x18003c370`: `class UnBCL::String *__cdecl UnBCL::File::GetTemporaryFileName(const class UnBCL::String *)`
- `0x18003c360`: `GetTemporaryFileName: tempPath->Lenght > (MAX_PATH - 14).`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
struct UnBCL::String *__fastcall UnBCL::File::GetTemporaryFileName(const struct UnBCL::String *a1)
{
  struct UnBCL::String *TempPathName; // rax
  UnBCL::String *v3; // rax
  const WCHAR *v4; // rcx
  UnBCL::String *v5; // rax
  __int64 v6; // rbx
  UnBCL::Win32Exception *v8; // rax
  UnBCL::Win32Exception *v9; // rdi
  DWORD LastError; // ebx
  const struct UnBCL::String *v11; // rax
  UnBCL::PathTooLongException *v12; // rax
  void **v13; // [rsp+28h] [rbp-E0h] BYREF
  __int64 v14; // [rsp+30h] [rbp-D8h]
  __int64 pExceptionObject; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD v16[3]; // [rsp+40h] [rbp-C8h] BYREF
  WCHAR TempFileName[264]; // [rsp+58h] [rbp-B0h] BYREF

  v16[2] = -2;
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v16, 0);
  if ( a1 )
  {
    v3 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
    pExceptionObject = (__int64)v3;
    if ( v3 )
      v3 = (UnBCL::String *)UnBCL::String::String(v3, a1);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v13, v3);
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(v16, v14);
  }
  else
  {
    TempPathName = UnBCL::Directory::GetTempPathName();
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v13, TempPathName);
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(v16, v14);
  }
  v13 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v13);
  v4 = *(const WCHAR **)(v16[1] + 16LL);
  if ( *((int *)v4 - 4) > 246 )
  {
    v12 = (UnBCL::PathTooLongException *)UnBCL::Object::operator new(0x38u);
    v13 = (void **)v12;
    if ( v12 )
      v12 = (UnBCL::PathTooLongException *)UnBCL::PathTooLongException::PathTooLongException(
                                             v12,
                                             L"GetTemporaryFileName: tempPath->Lenght > (MAX_PATH - 14).");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v12,
                         "class UnBCL::String *__cdecl UnBCL::File::GetTemporaryFileName(const class UnBCL::String *)");
    throw (UnBCL::PathTooLongException **)&pExceptionObject;
  }
  if ( !GetTempFileNameW(v4, L"tmp", 0, TempFileName) )
  {
    v8 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    v9 = v8;
    v13 = (void **)v8;
    if ( v8 )
    {
      LastError = GetLastError();
      v11 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::Decoder>::operator->(v16);
      v8 = (UnBCL::Win32Exception *)UnBCL::Win32Exception::Win32Exception(v9, LastError, v11);
    }
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v8,
                         "class UnBCL::String *__cdecl UnBCL::File::GetTemporaryFileName(const class UnBCL::String *)");
    throw (UnBCL::Win32Exception **)&pExceptionObject;
  }
  v5 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
  v13 = (void **)v5;
  if ( v5 )
    v6 = UnBCL::String::String(v5, TempFileName);
  else
    v6 = 0;
  v16[0] = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v16);
  return (struct UnBCL::String *)v6;
}

```

## disassembly

```asm
0x18003c1a0  mov     rax, rsp
0x18003c1a3  push    rbp
0x18003c1a4  lea     rbp, [rax-178h]
0x18003c1ab  sub     rsp, 270h
0x18003c1b2  mov     qword ptr [rsp+270h+var_228], 0FFFFFFFFFFFFFFFEh
0x18003c1bb  mov     [rax+10h], rbx
0x18003c1bf  mov     [rax+18h], rdi
0x18003c1c3  mov     rax, cs:__security_cookie
0x18003c1ca  xor     rax, rsp
0x18003c1cd  mov     [rbp+170h+var_10], rax
0x18003c1d4  mov     rbx, rcx
0x18003c1d7  xor     edx, edx
0x18003c1d9  lea     rcx, [rsp+270h+var_238]
0x18003c1de  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18003c1e3  nop
0x18003c1e4  test    rbx, rbx
0x18003c1e7  jnz     short loc_18003C20E
0x18003c1e9  call    ?GetTempPathName@Directory@UnBCL@@SAPEAVString@2@XZ; UnBCL::Directory::GetTempPathName(void)
0x18003c1ee  mov     rdx, rax
0x18003c1f1  lea     rcx, [rsp+270h+var_250]
0x18003c1f6  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18003c1fb  nop
0x18003c1fc  mov     rdx, [rsp+270h+var_248]
0x18003c201  lea     rcx, [rsp+270h+var_238]
0x18003c206  call    ?Assign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXPEAVXmlNamespaceManager@2@@Z; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(UnBCL::XmlNamespaceManager *)
0x18003c20b  nop
0x18003c20c  jmp     short loc_18003C24C
0x18003c20e  mov     ecx, 18h; unsigned __int64
0x18003c213  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003c218  mov     [rsp+270h+pExceptionObject], rax
0x18003c21d  test    rax, rax
0x18003c220  jz      short loc_18003C22E
0x18003c222  mov     rdx, rbx; struct UnBCL::String *
0x18003c225  mov     rcx, rax; this
0x18003c228  call    ??0String@UnBCL@@QEAA@PEBV01@@Z; UnBCL::String::String(UnBCL::String const *)
0x18003c22d  nop
0x18003c22e  mov     rdx, rax
0x18003c231  lea     rcx, [rsp+270h+var_250]
0x18003c236  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18003c23b  nop
0x18003c23c  mov     rdx, [rsp+270h+var_248]
0x18003c241  lea     rcx, [rsp+270h+var_238]
0x18003c246  call    ?Assign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXPEAVXmlNamespaceManager@2@@Z; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(UnBCL::XmlNamespaceManager *)
0x18003c24b  nop
0x18003c24c  lea     rdi, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x18003c253  mov     [rsp+270h+var_250], rdi
0x18003c258  lea     rcx, [rsp+270h+var_250]
0x18003c25d  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18003c262  mov     rax, [rsp+270h+var_230]
0x18003c267  mov     rcx, [rax+10h]; lpPathName
0x18003c26b  cmp     dword ptr [rcx-10h], 0F6h
0x18003c272  jg      loc_18003C34C
0x18003c278  lea     r9, [rsp+270h+TempFileName]; lpTempFileName
0x18003c27d  xor     r8d, r8d; uUnique
0x18003c280  lea     rdx, PrefixString; "tmp"
0x18003c287  call    cs:__imp_GetTempFileNameW
0x18003c28d  test    eax, eax
0x18003c28f  jz      short loc_18003C2EF
0x18003c291  mov     ecx, 18h; unsigned __int64
0x18003c296  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003c29b  mov     [rsp+270h+var_250], rax
0x18003c2a0  test    rax, rax
0x18003c2a3  jz      short loc_18003C2B7
0x18003c2a5  lea     rdx, [rsp+270h+TempFileName]; unsigned __int16 *
0x18003c2aa  mov     rcx, rax; this
0x18003c2ad  call    ??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18003c2b2  mov     rbx, rax
0x18003c2b5  jmp     short loc_18003C2B9
0x18003c2b7  xor     ebx, ebx
0x18003c2b9  mov     [rsp+270h+var_238], rdi
0x18003c2be  lea     rcx, [rsp+270h+var_238]
0x18003c2c3  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18003c2c8  mov     rax, rbx
0x18003c2cb  mov     rcx, [rbp+170h+var_10]
0x18003c2d2  xor     rcx, rsp; StackCookie
0x18003c2d5  call    __security_check_cookie
0x18003c2da  lea     r11, [rsp+270h+var_s0]
0x18003c2e2  mov     rbx, [r11+18h]
0x18003c2e6  mov     rdi, [r11+20h]
0x18003c2ea  mov     rsp, r11
0x18003c2ed  pop     rbp
0x18003c2ee  retn
0x18003c2ef  mov     ecx, 40h ; '@'; unsigned __int64
0x18003c2f4  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003c2f9  mov     rdi, rax
0x18003c2fc  mov     [rsp+270h+var_250], rax
0x18003c301  test    rax, rax
0x18003c304  jz      short loc_18003C326
0x18003c306  call    cs:__imp_GetLastError
0x18003c30c  mov     ebx, eax
0x18003c30e  lea     rcx, [rsp+270h+var_238]
0x18003c313  call    ??C?$SmartPtr@VDecoder@UnBCL@@@UnBCL@@QEBAPEAVDecoder@1@XZ; UnBCL::SmartPtr<UnBCL::Decoder>::operator->(void)
0x18003c318  mov     r8, rax; struct UnBCL::String *
0x18003c31b  mov     edx, ebx; dwMessageId
0x18003c31d  mov     rcx, rdi; this
0x18003c320  call    ??0Win32Exception@UnBCL@@QEAA@KPEBVString@1@@Z; UnBCL::Win32Exception::Win32Exception(ulong,UnBCL::String const *)
0x18003c325  nop
0x18003c326  lea     rdx, aClassUnbclStri_15; "class UnBCL::String *__cdecl UnBCL::Fil"...
0x18003c32d  mov     rcx, rax
0x18003c330  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003c335  mov     [rsp+270h+pExceptionObject], rax
0x18003c33a  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18003c341  lea     rcx, [rsp+270h+pExceptionObject]; pExceptionObject
0x18003c346  call    _CxxThrowException_0
0x18003c34c  mov     ecx, 38h ; '8'; unsigned __int64
0x18003c351  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003c356  mov     [rsp+270h+var_250], rax
0x18003c35b  test    rax, rax
0x18003c35e  jz      short loc_18003C370
0x18003c360  lea     rdx, aGettemporaryfi_0; "GetTemporaryFileName: tempPath->Lenght "...
0x18003c367  mov     rcx, rax; this
0x18003c36a  call    ??0PathTooLongException@UnBCL@@QEAA@PEBG@Z; UnBCL::PathTooLongException::PathTooLongException(ushort const *)
0x18003c36f  nop
0x18003c370  lea     rdx, aClassUnbclStri_15; "class UnBCL::String *__cdecl UnBCL::Fil"...
0x18003c377  mov     rcx, rax
0x18003c37a  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003c37f  mov     [rsp+270h+pExceptionObject], rax
0x18003c384  lea     rdx, _TI5PEAVPathTooLongException@UnBCL@@; pThrowInfo
0x18003c38b  lea     rcx, [rsp+270h+pExceptionObject]; pExceptionObject
0x18003c390  call    _CxxThrowException_0
```
