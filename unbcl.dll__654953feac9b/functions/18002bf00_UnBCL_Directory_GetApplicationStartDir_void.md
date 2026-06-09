# UnBCL::Directory::GetApplicationStartDir(void)

- ea: `0x18002bf00`
- end: `0x18002c040`
- name: `?GetApplicationStartDir@Directory@UnBCL@@SAPEAVString@2@XZ`
- size: `320`
- prototype: `struct UnBCL::String *(void)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callees

- `0x180002f50`
- `0x180002f90`
- `0x180011570`
- `0x18002bf00`
- `0x1800477d0`
- `0x1800498a0`
- `0x18005b790`
- `0x180064680`
- `0x180069020`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18002bf51`
- `msvcrt!wcsrchr` at `0x18002bf51`
- `KERNEL32!GetModuleFileNameW` at `0x18002bf37`
- `KERNEL32!GetModuleFileNameW` at `0x18002bf37`

## string_xrefs

- `0x18002c02c`: `base\ntsetup\unbcl\src\directory.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct UnBCL::String *UnBCL::Directory::GetApplicationStartDir(void)
{
  struct UnBCL::String *v0; // rbx
  wchar_t *v1; // rax
  UnBCL::String *v2; // rax
  __int64 v3; // rax
  struct UnBCL::String *LongName; // rax
  struct UnBCL::String *v5; // rax
  void **v7; // [rsp+20h] [rbp-458h] BYREF
  struct UnBCL::String *v8; // [rsp+28h] [rbp-450h]
  _QWORD v9[3]; // [rsp+30h] [rbp-448h] BYREF
  void (__fastcall ***v10)(_QWORD, __int64); // [rsp+48h] [rbp-430h] BYREF
  WCHAR Filename[520]; // [rsp+50h] [rbp-428h] BYREF

  v9[2] = -2;
  v0 = 0;
  if ( !GetModuleFileNameW(0, Filename, 0x208u) )
    UnBCL::Win32Exception::ThrowLastError(
      L"GetModuleFileNameW failed",
      "base\\ntsetup\\unbcl\\src\\directory.cpp",
      1732);
  v1 = wcsrchr(Filename, 0x5Cu);
  if ( v1 )
    *v1 = 0;
  v2 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
  v7 = (void **)v2;
  if ( v2 )
    v3 = UnBCL::String::String(v2, Filename);
  else
    v3 = 0;
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v7, v3);
  try
  {
    LongName = UnBCL::Path::GetLongName((const unsigned __int16 **)v8);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v9, LongName);
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(&v7, v9[1]);
    v9[0] = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v9);
  }
  catch ( UnBCL::Exception *v10 )
  {
    if ( v10 )
      (**v10)(v10, 1);
    v0 = 0;
  }
  v5 = v8;
  if ( v8 )
  {
    _InterlockedDecrement((volatile signed __int32 *)v8 + 2);
    v8 = 0;
    v0 = v5;
  }
  v7 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v7);
  return v0;
}

```

## disassembly

```asm
0x18002bf00  mov     rax, rsp
0x18002bf03  push    rdi
0x18002bf04  sub     rsp, 470h
0x18002bf0b  mov     [rsp+478h+var_438], 0FFFFFFFFFFFFFFFEh
0x18002bf14  mov     [rax+8], rbx
0x18002bf18  mov     rax, cs:__security_cookie
0x18002bf1f  xor     rax, rsp
0x18002bf22  mov     [rsp+478h+var_18], rax
0x18002bf2a  mov     r8d, 208h; nSize
0x18002bf30  lea     rdx, [rsp+478h+Filename]; lpFilename
0x18002bf35  xor     ecx, ecx; hModule
0x18002bf37  call    cs:__imp_GetModuleFileNameW
0x18002bf3d  xor     ebx, ebx
0x18002bf3f  test    eax, eax
0x18002bf41  jz      loc_18002C026
0x18002bf47  mov     edx, 5Ch ; '\'; Ch
0x18002bf4c  lea     rcx, [rsp+478h+Filename]; Str
0x18002bf51  call    cs:__imp_wcsrchr
0x18002bf57  test    rax, rax
0x18002bf5a  jz      short loc_18002BF5F
0x18002bf5c  mov     [rax], bx
0x18002bf5f  mov     ecx, 18h; unsigned __int64
0x18002bf64  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002bf69  mov     [rsp+478h+var_458], rax
0x18002bf6e  test    rax, rax
0x18002bf71  jz      short loc_18002BF82
0x18002bf73  lea     rdx, [rsp+478h+Filename]; unsigned __int16 *
0x18002bf78  mov     rcx, rax; this
0x18002bf7b  call    ??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18002bf80  jmp     short loc_18002BF85
0x18002bf82  mov     rax, rbx
0x18002bf85  mov     rdx, rax
0x18002bf88  lea     rcx, [rsp+478h+var_458]
0x18002bf8d  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18002bf92  nop
0x18002bf93  mov     rcx, [rsp+478h+var_450]; struct UnBCL::String *
0x18002bf98  call    ?GetLongName@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetLongName(UnBCL::String const *)
0x18002bf9d  mov     rdx, rax
0x18002bfa0  lea     rcx, [rsp+478h+var_448]
0x18002bfa5  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18002bfaa  nop
0x18002bfab  mov     rdx, [rsp+478h+var_440]
0x18002bfb0  lea     rcx, [rsp+478h+var_458]
0x18002bfb5  call    ?Assign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXPEAVXmlNamespaceManager@2@@Z; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(UnBCL::XmlNamespaceManager *)
0x18002bfba  nop
0x18002bfbb  lea     rdi, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x18002bfc2  mov     [rsp+478h+var_448], rdi
0x18002bfc7  lea     rcx, [rsp+478h+var_448]
0x18002bfcc  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18002bfd1  nop
0x18002bfd2  jmp     short loc_18002BFDD
0x18002bfd4  xor     ebx, ebx
0x18002bfd6  lea     rdi, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x18002bfdd  mov     rax, [rsp+478h+var_450]
0x18002bfe2  test    rax, rax
0x18002bfe5  jz      short loc_18002BFF3
0x18002bfe7  lock dec dword ptr [rax+8]
0x18002bfeb  mov     [rsp+478h+var_450], rbx
0x18002bff0  mov     rbx, rax
0x18002bff3  mov     [rsp+478h+var_458], rdi
0x18002bff8  lea     rcx, [rsp+478h+var_458]
0x18002bffd  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18002c002  mov     rax, rbx
0x18002c005  mov     rcx, [rsp+478h+var_18]
0x18002c00d  xor     rcx, rsp; StackCookie
0x18002c010  call    __security_check_cookie
0x18002c015  mov     rbx, [rsp+478h+arg_0]
0x18002c01d  add     rsp, 470h
0x18002c024  pop     rdi
0x18002c025  retn
0x18002c026  mov     r8d, 6C4h; int
0x18002c02c  lea     rdx, aBaseNtsetupUnb_3; "base\\ntsetup\\unbcl\\src\\directory.cp"...
0x18002c033  lea     rcx, aGetmodulefilen; "GetModuleFileNameW failed"
0x18002c03a  call    ?ThrowLastError@Win32Exception@UnBCL@@SAXPEBGPEBDH@Z; UnBCL::Win32Exception::ThrowLastError(ushort const *,char const *,int)
```
