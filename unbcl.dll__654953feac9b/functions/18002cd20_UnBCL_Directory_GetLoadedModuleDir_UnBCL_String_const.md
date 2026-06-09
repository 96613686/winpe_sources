# UnBCL::Directory::GetLoadedModuleDir(UnBCL::String const *)

- ea: `0x18002cd20`
- end: `0x18002cee1`
- name: `?GetLoadedModuleDir@Directory@UnBCL@@SAPEAVString@2@PEBV32@@Z`
- size: `449`
- prototype: `struct UnBCL::String *__fastcall(const struct UnBCL::String *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, installer_update`

## callees

- `0x18000225c`
- `0x180002f50`
- `0x180002f90`
- `0x1800099b0`
- `0x180009e7c`
- `0x180011570`
- `0x18002cd20`
- `0x1800477d0`
- `0x1800498a0`
- `0x18005b790`
- `0x180064680`
- `0x180069020`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18002cd8e`
- `msvcrt!wcsrchr` at `0x18002cd8e`
- `KERNEL32!GetModuleHandleW` at `0x18002cd59`
- `KERNEL32!GetModuleHandleW` at `0x18002cd59`
- `KERNEL32!GetModuleFileNameW` at `0x18002cd76`
- `KERNEL32!GetModuleFileNameW` at `0x18002cd76`

## string_xrefs

- `0x18002ceb3`: `base\ntsetup\unbcl\src\directory.cpp`
- `0x18002cecd`: `base\ntsetup\unbcl\src\directory.cpp`
- `0x18002ce87`: `class UnBCL::String *__cdecl UnBCL::Directory::GetLoadedModuleDir(const class UnBCL::String *)`
- `0x18002ce75`: `null ModuleName to Directory::GetLoadedModuleDir`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
struct UnBCL::String *__fastcall UnBCL::Directory::GetLoadedModuleDir(LPCWSTR *a1)
{
  __int64 v1; // rbx
  HMODULE ModuleHandleW; // rax
  wchar_t *v3; // rax
  UnBCL::String *v4; // rax
  __int64 v5; // rax
  struct UnBCL::String *LongName; // rax
  struct UnBCL::String *v7; // rax
  UnBCL::ArgumentNullException *v9; // rax
  void **v10; // [rsp+20h] [rbp-468h] BYREF
  struct UnBCL::String *v11; // [rsp+28h] [rbp-460h]
  __int64 pExceptionObject; // [rsp+30h] [rbp-458h] BYREF
  _QWORD v13[3]; // [rsp+38h] [rbp-450h] BYREF
  void (__fastcall ***v14)(_QWORD, __int64); // [rsp+50h] [rbp-438h] BYREF
  WCHAR Filename[520]; // [rsp+60h] [rbp-428h] BYREF

  v13[2] = -2;
  v1 = 0;
  if ( !a1 )
  {
    v9 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v10 = (void **)v9;
    if ( v9 )
      v1 = UnBCL::ArgumentNullException::ArgumentNullException(v9, L"null ModuleName to Directory::GetLoadedModuleDir");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v1,
                         "class UnBCL::String *__cdecl UnBCL::Directory::GetLoadedModuleDir(const class UnBCL::String *)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  ModuleHandleW = GetModuleHandleW(a1[2]);
  if ( !ModuleHandleW )
    UnBCL::Win32Exception::ThrowLastError(L"GetModuleHandle failed", "base\\ntsetup\\unbcl\\src\\directory.cpp", 1767);
  if ( !GetModuleFileNameW(ModuleHandleW, Filename, 0x208u) )
    UnBCL::Win32Exception::ThrowLastError(
      L"GetModuleFileNameW failed",
      "base\\ntsetup\\unbcl\\src\\directory.cpp",
      1773);
  v3 = wcsrchr(Filename, 0x5Cu);
  if ( v3 )
    *v3 = 0;
  v4 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
  v10 = (void **)v4;
  if ( v4 )
    v5 = UnBCL::String::String(v4, Filename);
  else
    v5 = 0;
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v10, v5);
  try
  {
    LongName = UnBCL::Path::GetLongName(v11);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v13, LongName);
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(&v10, v13[1]);
    v13[0] = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v13);
  }
  catch ( UnBCL::Exception *v14 )
  {
    if ( v14 )
      (**v14)(v14, 1);
    v1 = 0;
  }
  v7 = v11;
  if ( v11 )
  {
    _InterlockedDecrement((volatile signed __int32 *)v11 + 2);
    v11 = 0;
    v1 = (__int64)v7;
  }
  v10 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v10);
  return (struct UnBCL::String *)v1;
}

```

## disassembly

```asm
0x18002cd20  mov     rax, rsp
0x18002cd23  push    rdi
0x18002cd24  sub     rsp, 480h
0x18002cd2b  mov     [rsp+488h+var_440], 0FFFFFFFFFFFFFFFEh
0x18002cd34  mov     [rax+10h], rbx
0x18002cd38  mov     rax, cs:__security_cookie
0x18002cd3f  xor     rax, rsp
0x18002cd42  mov     [rsp+488h+var_18], rax
0x18002cd4a  xor     ebx, ebx
0x18002cd4c  test    rcx, rcx
0x18002cd4f  jz      loc_18002CE63
0x18002cd55  mov     rcx, [rcx+10h]; lpModuleName
0x18002cd59  call    cs:__imp_GetModuleHandleW
0x18002cd5f  test    rax, rax
0x18002cd62  jz      loc_18002CEAD
0x18002cd68  mov     r8d, 208h; nSize
0x18002cd6e  lea     rdx, [rsp+488h+Filename]; lpFilename
0x18002cd73  mov     rcx, rax; hModule
0x18002cd76  call    cs:__imp_GetModuleFileNameW
0x18002cd7c  test    eax, eax
0x18002cd7e  jz      loc_18002CEC7
0x18002cd84  mov     edx, 5Ch ; '\'; Ch
0x18002cd89  lea     rcx, [rsp+488h+Filename]; Str
0x18002cd8e  call    cs:__imp_wcsrchr
0x18002cd94  test    rax, rax
0x18002cd97  jz      short loc_18002CD9C
0x18002cd99  mov     [rax], bx
0x18002cd9c  mov     ecx, 18h; unsigned __int64
0x18002cda1  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002cda6  mov     [rsp+488h+var_468], rax
0x18002cdab  test    rax, rax
0x18002cdae  jz      short loc_18002CDBF
0x18002cdb0  lea     rdx, [rsp+488h+Filename]; unsigned __int16 *
0x18002cdb5  mov     rcx, rax; this
0x18002cdb8  call    ??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18002cdbd  jmp     short loc_18002CDC2
0x18002cdbf  mov     rax, rbx
0x18002cdc2  mov     rdx, rax
0x18002cdc5  lea     rcx, [rsp+488h+var_468]
0x18002cdca  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18002cdcf  nop
0x18002cdd0  mov     rcx, [rsp+488h+var_460]; struct UnBCL::String *
0x18002cdd5  call    ?GetLongName@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetLongName(UnBCL::String const *)
0x18002cdda  mov     rdx, rax
0x18002cddd  lea     rcx, [rsp+488h+var_450]
0x18002cde2  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18002cde7  nop
0x18002cde8  mov     rdx, [rsp+488h+var_448]
0x18002cded  lea     rcx, [rsp+488h+var_468]
0x18002cdf2  call    ?Assign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXPEAVXmlNamespaceManager@2@@Z; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(UnBCL::XmlNamespaceManager *)
0x18002cdf7  nop
0x18002cdf8  lea     rdi, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x18002cdff  mov     [rsp+488h+var_450], rdi
0x18002ce04  lea     rcx, [rsp+488h+var_450]
0x18002ce09  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18002ce0e  nop
0x18002ce0f  jmp     short loc_18002CE1A
0x18002ce11  xor     ebx, ebx
0x18002ce13  lea     rdi, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x18002ce1a  mov     rax, [rsp+488h+var_460]
0x18002ce1f  test    rax, rax
0x18002ce22  jz      short loc_18002CE30
0x18002ce24  lock dec dword ptr [rax+8]
0x18002ce28  mov     [rsp+488h+var_460], rbx
0x18002ce2d  mov     rbx, rax
0x18002ce30  mov     [rsp+488h+var_468], rdi
0x18002ce35  lea     rcx, [rsp+488h+var_468]
0x18002ce3a  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18002ce3f  mov     rax, rbx
0x18002ce42  mov     rcx, [rsp+488h+var_18]
0x18002ce4a  xor     rcx, rsp; StackCookie
0x18002ce4d  call    __security_check_cookie
0x18002ce52  mov     rbx, [rsp+488h+arg_8]
0x18002ce5a  add     rsp, 480h
0x18002ce61  pop     rdi
0x18002ce62  retn
0x18002ce63  lea     ecx, [rbx+38h]; unsigned __int64
0x18002ce66  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002ce6b  mov     [rsp+488h+var_468], rax
0x18002ce70  test    rax, rax
0x18002ce73  jz      short loc_18002CE87
0x18002ce75  lea     rdx, aNullModulename; "null ModuleName to Directory::GetLoaded"...
0x18002ce7c  mov     rcx, rax; this
0x18002ce7f  call    ??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x18002ce84  mov     rbx, rax
0x18002ce87  lea     rdx, aClassUnbclStri_4; "class UnBCL::String *__cdecl UnBCL::Dir"...
0x18002ce8e  mov     rcx, rbx
0x18002ce91  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002ce96  mov     [rsp+488h+pExceptionObject], rax
0x18002ce9b  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x18002cea2  lea     rcx, [rsp+488h+pExceptionObject]; pExceptionObject
0x18002cea7  call    _CxxThrowException_0
0x18002cead  mov     r8d, 6E7h; int
0x18002ceb3  lea     rdx, aBaseNtsetupUnb_3; "base\\ntsetup\\unbcl\\src\\directory.cp"...
0x18002ceba  lea     rcx, aGetmodulehandl; "GetModuleHandle failed"
0x18002cec1  call    ?ThrowLastError@Win32Exception@UnBCL@@SAXPEBGPEBDH@Z; UnBCL::Win32Exception::ThrowLastError(ushort const *,char const *,int)
0x18002cec7  mov     r8d, 6EDh; int
0x18002cecd  lea     rdx, aBaseNtsetupUnb_3; "base\\ntsetup\\unbcl\\src\\directory.cp"...
0x18002ced4  lea     rcx, aGetmodulefilen; "GetModuleFileNameW failed"
0x18002cedb  call    ?ThrowLastError@Win32Exception@UnBCL@@SAXPEBGPEBDH@Z; UnBCL::Win32Exception::ThrowLastError(ushort const *,char const *,int)
```
