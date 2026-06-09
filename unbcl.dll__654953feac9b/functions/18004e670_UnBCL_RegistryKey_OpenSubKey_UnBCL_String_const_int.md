# UnBCL::RegistryKey::OpenSubKey(UnBCL::String const *,int)

- ea: `0x18004e670`
- end: `0x18004e89f`
- name: `?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@H@Z`
- size: `559`
- prototype: `struct UnBCL::RegistryKey *(UnBCL::RegistryKey *__hidden this, const struct UnBCL::String *, int)`
- caller_count: `4`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004cc60`
- `0x18004d000`
- `0x18004d2c0`
- `0x18004e660`

## callees

- `0x18000225c`
- `0x180002f90`
- `0x1800098b0`
- `0x1800099b0`
- `0x180009e7c`
- `0x1800477d0`
- `0x180047d60`
- `0x18004c954`
- `0x18004c9d0`
- `0x18004d760`
- `0x18004e670`
- `0x18004fb00`
- `0x180060150`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18004e70b`
- `ADVAPI32!RegOpenKeyExW` at `0x18004e70b`

## string_xrefs

- `0x18004e7dd`: `method called on closed RegistryKey`
- `0x18004e7ed`: `class UnBCL::RegistryKey *__cdecl UnBCL::RegistryKey::OpenSubKey(const class UnBCL::String *,int)`
- `0x18004e834`: `class UnBCL::RegistryKey *__cdecl UnBCL::RegistryKey::OpenSubKey(const class UnBCL::String *,int)`
- `0x18004e87b`: `class UnBCL::RegistryKey *__cdecl UnBCL::RegistryKey::OpenSubKey(const class UnBCL::String *,int)`
- `0x18004e824`: `null keyname to RegistryKey#DeleteSubKey`
- `0x18004e79d`: `unable to open subkey`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
struct UnBCL::RegistryKey *__fastcall UnBCL::RegistryKey::OpenSubKey(
        UnBCL::RegistryKey *this,
        const struct UnBCL::String *a2,
        int a3)
{
  struct UnBCL::String *v5; // rax
  LSTATUS v6; // eax
  UnBCL::RegistryKey *v8; // rax
  __int64 v9; // rbx
  UnBCL::SecurityException *v10; // rax
  UnBCL::ObjectDisposedException *v11; // rax
  UnBCL::ArgumentNullException *v12; // rax
  UnBCL::ArgumentException *v13; // rax
  _BYTE v14[8]; // [rsp+40h] [rbp-20h] BYREF
  __int64 v15; // [rsp+48h] [rbp-18h]
  _QWORD v16[2]; // [rsp+50h] [rbp-10h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp+10h] BYREF
  __int64 pExceptionObject; // [rsp+88h] [rbp+28h] BYREF

  if ( *((_DWORD *)this + 2) )
  {
    v11 = (UnBCL::ObjectDisposedException *)UnBCL::Object::operator new(0x38u);
    if ( v11 )
      v11 = (UnBCL::ObjectDisposedException *)UnBCL::ObjectDisposedException::ObjectDisposedException(
                                                v11,
                                                L"method called on closed RegistryKey");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v11,
                         "class UnBCL::RegistryKey *__cdecl UnBCL::RegistryKey::OpenSubKey(const class UnBCL::String *,int)");
    throw (UnBCL::ObjectDisposedException **)&pExceptionObject;
  }
  if ( !a2 )
  {
    v12 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    if ( v12 )
      v12 = (UnBCL::ArgumentNullException *)UnBCL::ArgumentNullException::ArgumentNullException(
                                              v12,
                                              L"null keyname to RegistryKey#DeleteSubKey");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v12,
                         "class UnBCL::RegistryKey *__cdecl UnBCL::RegistryKey::OpenSubKey(const class UnBCL::String *,int)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  if ( *(int *)(*((_QWORD *)a2 + 2) - 16LL) > 255 )
  {
    v13 = (UnBCL::ArgumentException *)UnBCL::Object::operator new(0x38u);
    if ( v13 )
      v13 = (UnBCL::ArgumentException *)UnBCL::ArgumentException::ArgumentException(
                                          v13,
                                          L"keyname exceeds maximum name length");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v13,
                         "class UnBCL::RegistryKey *__cdecl UnBCL::RegistryKey::OpenSubKey(const class UnBCL::String *,int)");
    throw (UnBCL::ArgumentException **)&pExceptionObject;
  }
  phkResult = 0;
  v5 = UnBCL::RegistryKey::FixupName(this, a2);
  UnBCL::StringPtr::StringPtr((UnBCL::StringPtr *)v14, v5);
  v6 = RegOpenKeyExW(
         **((HKEY **)this + 2),
         *(LPCWSTR *)(*(_QWORD *)((char *)v16 + *(int *)(v15 + 4)) + 16LL),
         0,
         a3 != 0 ? 131103 : 131097,
         &phkResult);
  if ( v6 == 5 )
  {
    v10 = (UnBCL::SecurityException *)UnBCL::Object::operator new(0x38u);
    if ( v10 )
      v10 = (UnBCL::SecurityException *)UnBCL::SecurityException::SecurityException(v10, L"unable to open subkey");
    pExceptionObject = AddStackTraceToException<UnBCL::SecurityException>(v10);
    throw (UnBCL::SecurityException **)&pExceptionObject;
  }
  if ( v6 )
  {
    v16[0] = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v16);
    return 0;
  }
  else
  {
    v8 = (UnBCL::RegistryKey *)UnBCL::Object::operator new(0x40u);
    pExceptionObject = (__int64)v8;
    if ( v8 )
      v9 = UnBCL::RegistryKey::RegistryKey(v8, phkResult, a3);
    else
      v9 = 0;
    v16[0] = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v16);
    return (struct UnBCL::RegistryKey *)v9;
  }
}

```

## disassembly

```asm
0x18004e670  mov     rax, rsp
0x18004e673  push    rbp
0x18004e674  mov     rbp, rsp
0x18004e677  sub     rsp, 60h
0x18004e67b  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFEh
0x18004e683  mov     [rax+10h], rbx
0x18004e687  mov     [rax+18h], rdi
0x18004e68b  mov     edi, r8d
0x18004e68e  mov     rbx, rcx
0x18004e691  cmp     dword ptr [rcx+8], 0
0x18004e695  jnz     loc_18004E7CA
0x18004e69b  test    rdx, rdx
0x18004e69e  jz      loc_18004E811
0x18004e6a4  mov     rax, [rdx+10h]
0x18004e6a8  cmp     dword ptr [rax-10h], 0FFh
0x18004e6af  jg      loc_18004E858
0x18004e6b5  mov     [rbp+arg_0], 0
0x18004e6bd  call    ?FixupName@RegistryKey@UnBCL@@AEAAPEAVString@2@AEBV32@@Z; UnBCL::RegistryKey::FixupName(UnBCL::String const &)
0x18004e6c2  mov     rdx, rax; struct UnBCL::String *
0x18004e6c5  mov     r8d, 1
0x18004e6cb  lea     rcx, [rbp+var_20]; this
0x18004e6cf  call    ??0StringPtr@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::StringPtr::StringPtr(UnBCL::String *)
0x18004e6d4  nop
0x18004e6d5  mov     eax, edi
0x18004e6d7  neg     eax
0x18004e6d9  sbb     r9d, r9d
0x18004e6dc  and     r9d, 6
0x18004e6e0  add     r9d, 20019h; samDesired
0x18004e6e7  mov     rax, [rbp+var_18]
0x18004e6eb  movsxd  rcx, dword ptr [rax+4]
0x18004e6ef  mov     rdx, [rbp+rcx+var_10]
0x18004e6f4  mov     rcx, [rbx+10h]
0x18004e6f8  lea     rax, [rbp+arg_0]
0x18004e6fc  mov     [rsp+60h+phkResult], rax; phkResult
0x18004e701  xor     r8d, r8d; ulOptions
0x18004e704  mov     rdx, [rdx+10h]; lpSubKey
0x18004e708  mov     rcx, [rcx]; hKey
0x18004e70b  call    cs:__imp_RegOpenKeyExW
0x18004e711  cmp     eax, 5
0x18004e714  jz      short loc_18004E78A
0x18004e716  test    eax, eax
0x18004e718  jz      short loc_18004E732
0x18004e71a  lea     rax, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x18004e721  mov     [rbp+var_10], rax
0x18004e725  lea     rcx, [rbp+var_10]
0x18004e729  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18004e72e  xor     eax, eax
0x18004e730  jmp     short loc_18004E778
0x18004e732  mov     ecx, 40h ; '@'; unsigned __int64
0x18004e737  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004e73c  mov     [rbp+pExceptionObject], rax
0x18004e740  test    rax, rax
0x18004e743  jz      short loc_18004E75F
0x18004e745  mov     r9d, 1
0x18004e74b  mov     r8d, edi; int
0x18004e74e  mov     rdx, [rbp+arg_0]; HKEY
0x18004e752  mov     rcx, rax; this
0x18004e755  call    ??0RegistryKey@UnBCL@@QEAA@PEAUHKEY__@@H@Z; UnBCL::RegistryKey::RegistryKey(HKEY__ *,int)
0x18004e75a  mov     rbx, rax
0x18004e75d  jmp     short loc_18004E761
0x18004e75f  xor     ebx, ebx
0x18004e761  lea     rax, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x18004e768  mov     [rbp+var_10], rax
0x18004e76c  lea     rcx, [rbp+var_10]
0x18004e770  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18004e775  mov     rax, rbx
0x18004e778  lea     r11, [rsp+60h+var_s0]
0x18004e77d  mov     rbx, [r11+18h]
0x18004e781  mov     rdi, [r11+20h]
0x18004e785  mov     rsp, r11
0x18004e788  pop     rbp
0x18004e789  retn
0x18004e78a  mov     ecx, 38h ; '8'; unsigned __int64
0x18004e78f  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004e794  mov     [rbp+var_28], rax
0x18004e798  test    rax, rax
0x18004e79b  jz      short loc_18004E7AD
0x18004e79d  lea     rdx, aUnableToOpenSu; "unable to open subkey"
0x18004e7a4  mov     rcx, rax; this
0x18004e7a7  call    ??0SecurityException@UnBCL@@QEAA@PEBG@Z; UnBCL::SecurityException::SecurityException(ushort const *)
0x18004e7ac  nop
0x18004e7ad  mov     rcx, rax
0x18004e7b0  call    ??$AddStackTraceToException@VSecurityException@UnBCL@@@@YAPEAVSecurityException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::SecurityException>(UnBCL::SecurityException *,char const *)
0x18004e7b5  mov     [rbp+pExceptionObject], rax
0x18004e7b9  lea     rdx, _TI5PEAVSecurityException@UnBCL@@; pThrowInfo
0x18004e7c0  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18004e7c4  call    _CxxThrowException_0
0x18004e7ca  mov     ecx, 38h ; '8'; unsigned __int64
0x18004e7cf  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004e7d4  mov     [rbp+var_28], rax
0x18004e7d8  test    rax, rax
0x18004e7db  jz      short loc_18004E7ED
0x18004e7dd  lea     rdx, aMethodCalledOn; "method called on closed RegistryKey"
0x18004e7e4  mov     rcx, rax; this
0x18004e7e7  call    ??0ObjectDisposedException@UnBCL@@QEAA@PEBG@Z; UnBCL::ObjectDisposedException::ObjectDisposedException(ushort const *)
0x18004e7ec  nop
0x18004e7ed  lea     rdx, aClassUnbclRegi_0; "class UnBCL::RegistryKey *__cdecl UnBCL"...
0x18004e7f4  mov     rcx, rax
0x18004e7f7  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004e7fc  mov     [rbp+pExceptionObject], rax
0x18004e800  lea     rdx, _TI5PEAVObjectDisposedException@UnBCL@@; pThrowInfo
0x18004e807  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18004e80b  call    _CxxThrowException_0
0x18004e811  mov     ecx, 38h ; '8'; unsigned __int64
0x18004e816  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004e81b  mov     [rbp+var_28], rax
0x18004e81f  test    rax, rax
0x18004e822  jz      short loc_18004E834
0x18004e824  lea     rdx, aNullKeynameToR_1; "null keyname to RegistryKey#DeleteSubKe"...
0x18004e82b  mov     rcx, rax; this
0x18004e82e  call    ??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x18004e833  nop
0x18004e834  lea     rdx, aClassUnbclRegi_0; "class UnBCL::RegistryKey *__cdecl UnBCL"...
0x18004e83b  mov     rcx, rax
0x18004e83e  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004e843  mov     [rbp+pExceptionObject], rax
0x18004e847  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x18004e84e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18004e852  call    _CxxThrowException_0
0x18004e858  mov     ecx, 38h ; '8'; unsigned __int64
0x18004e85d  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004e862  mov     [rbp+var_28], rax
0x18004e866  test    rax, rax
0x18004e869  jz      short loc_18004E87B
0x18004e86b  lea     rdx, aKeynameExceeds; "keyname exceeds maximum name length"
0x18004e872  mov     rcx, rax; this
0x18004e875  call    ??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x18004e87a  nop
0x18004e87b  lea     rdx, aClassUnbclRegi_0; "class UnBCL::RegistryKey *__cdecl UnBCL"...
0x18004e882  mov     rcx, rax
0x18004e885  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004e88a  mov     [rbp+pExceptionObject], rax
0x18004e88e  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x18004e895  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18004e899  call    _CxxThrowException_0
```
