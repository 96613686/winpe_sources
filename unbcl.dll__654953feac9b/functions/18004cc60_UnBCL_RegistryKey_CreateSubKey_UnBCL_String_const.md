# UnBCL::RegistryKey::CreateSubKey(UnBCL::String const *)

- ea: `0x18004cc60`
- end: `0x18004cf0d`
- name: `?CreateSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@@Z`
- size: `685`
- prototype: `struct UnBCL::RegistryKey *__fastcall(UnBCL::RegistryKey *__hidden this, const struct UnBCL::String *)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config`

## callees

- `0x18000225c`
- `0x180002f90`
- `0x1800099b0`
- `0x180009e7c`
- `0x1800360e0`
- `0x1800477d0`
- `0x180047d60`
- `0x18004c978`
- `0x18004c9d0`
- `0x18004cc60`
- `0x18004d760`
- `0x18004e670`
- `0x180060150`
- `0x1800641a0`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x18004cd7e`
- `ADVAPI32!RegCreateKeyExW` at `0x18004cd7e`

## string_xrefs

- `0x18004ce46`: `method called on closed RegistryKey`
- `0x18004ce0f`: `class UnBCL::RegistryKey *__cdecl UnBCL::RegistryKey::CreateSubKey(const class UnBCL::String *)`
- `0x18004ce56`: `class UnBCL::RegistryKey *__cdecl UnBCL::RegistryKey::CreateSubKey(const class UnBCL::String *)`
- `0x18004cea2`: `class UnBCL::RegistryKey *__cdecl UnBCL::RegistryKey::CreateSubKey(const class UnBCL::String *)`
- `0x18004cee9`: `class UnBCL::RegistryKey *__cdecl UnBCL::RegistryKey::CreateSubKey(const class UnBCL::String *)`
- `0x18004ced9`: `null keyname to RegistryKey#CreateSubKey`
- `0x18004ce8d`: `attempt to create subkey of key opened read-only`
- `0x18004cdfd`: `unable to create subkey`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
struct UnBCL::RegistryKey *__fastcall UnBCL::RegistryKey::CreateSubKey(
        UnBCL::RegistryKey *this,
        const struct UnBCL::String *a2)
{
  struct UnBCL::String *v3; // rax
  struct UnBCL::RegistryKey *v4; // rax
  __int64 v5; // rdi
  LSTATUS v7; // ebx
  UnBCL::RegistryKey *v8; // rax
  __int64 v9; // rbx
  UnBCL::Win32Exception *v10; // rax
  UnBCL::ObjectDisposedException *v11; // rax
  UnBCL::Win32Exception *v12; // rax
  UnBCL::ArgumentNullException *v13; // rax
  void **v14; // [rsp+60h] [rbp+17h] BYREF
  __int64 v15; // [rsp+68h] [rbp+1Fh]
  _BYTE v16[8]; // [rsp+70h] [rbp+27h] BYREF
  __int64 v17; // [rsp+78h] [rbp+2Fh]
  struct UnBCL::String *v18[4]; // [rsp+80h] [rbp+37h] BYREF
  DWORD dwDisposition; // [rsp+B0h] [rbp+67h] BYREF
  HKEY phkResult; // [rsp+C0h] [rbp+77h] BYREF
  __int64 pExceptionObject; // [rsp+C8h] [rbp+7Fh] BYREF

  if ( *((_DWORD *)this + 2) )
  {
    v11 = (UnBCL::ObjectDisposedException *)UnBCL::Object::operator new(0x38u);
    if ( v11 )
      v11 = (UnBCL::ObjectDisposedException *)UnBCL::ObjectDisposedException::ObjectDisposedException(
                                                v11,
                                                L"method called on closed RegistryKey");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v11,
                         "class UnBCL::RegistryKey *__cdecl UnBCL::RegistryKey::CreateSubKey(const class UnBCL::String *)");
    throw (UnBCL::ObjectDisposedException **)&pExceptionObject;
  }
  if ( !*((_DWORD *)this + 3) )
  {
    v12 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    if ( v12 )
      v12 = (UnBCL::Win32Exception *)UnBCL::Win32Exception::Win32Exception(
                                       v12,
                                       5u,
                                       L"attempt to create subkey of key opened read-only");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v12,
                         "class UnBCL::RegistryKey *__cdecl UnBCL::RegistryKey::CreateSubKey(const class UnBCL::String *)");
    throw (UnBCL::Win32Exception **)&pExceptionObject;
  }
  if ( !a2 )
  {
    v13 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    if ( v13 )
      v13 = (UnBCL::ArgumentNullException *)UnBCL::ArgumentNullException::ArgumentNullException(
                                              v13,
                                              L"null keyname to RegistryKey#CreateSubKey");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v13,
                         "class UnBCL::RegistryKey *__cdecl UnBCL::RegistryKey::CreateSubKey(const class UnBCL::String *)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  v3 = UnBCL::RegistryKey::FixupName(this, a2);
  UnBCL::StringPtr::StringPtr((UnBCL::StringPtr *)v16, v3);
  v4 = UnBCL::RegistryKey::OpenSubKey(this, *(struct UnBCL::String **)((char *)v18 + *(int *)(v17 + 4)), 1);
  UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(&v14, v4);
  v5 = v15;
  if ( v15 )
  {
    _InterlockedDecrement((volatile signed __int32 *)(*(int *)(*(_QWORD *)v15 + 4LL) + v15 + 8));
    v15 = 0;
    v14 = &UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable';
    UnBCL::SmartPtr<UnBCL::MultiSz>::DeAssign(&v14);
    v18[0] = (struct UnBCL::String *)&UnBCL::SmartPtr<UnBCL::String>::`vftable';
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v18);
    return (struct UnBCL::RegistryKey *)v5;
  }
  else
  {
    dwDisposition = 0;
    phkResult = 0;
    v7 = RegCreateKeyExW(
           **((HKEY **)this + 2),
           (*(LPCWSTR **)((char *)v18 + *(int *)(v17 + 4)))[2],
           0,
           0,
           0,
           0x2001Fu,
           0,
           &phkResult,
           &dwDisposition);
    if ( v7 )
    {
      v10 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
      if ( v10 )
        v10 = (UnBCL::Win32Exception *)UnBCL::Win32Exception::Win32Exception(v10, v7, L"unable to create subkey");
      pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                           v10,
                           "class UnBCL::RegistryKey *__cdecl UnBCL::RegistryKey::CreateSubKey(const class UnBCL::String *)");
      throw (UnBCL::Win32Exception **)&pExceptionObject;
    }
    v8 = (UnBCL::RegistryKey *)UnBCL::Object::operator new(0x40u);
    pExceptionObject = (__int64)v8;
    if ( v8 )
      v9 = UnBCL::RegistryKey::RegistryKey(v8, phkResult, 1);
    else
      v9 = 0;
    v14 = &UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable';
    UnBCL::SmartPtr<UnBCL::MultiSz>::DeAssign(&v14);
    v18[0] = (struct UnBCL::String *)&UnBCL::SmartPtr<UnBCL::String>::`vftable';
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v18);
    return (struct UnBCL::RegistryKey *)v9;
  }
}

```

## disassembly

```asm
0x18004cc60  push    rbp
0x18004cc62  push    rbx
0x18004cc63  push    rdi
0x18004cc64  lea     rbp, [rsp-47h]
0x18004cc69  sub     rsp, 90h
0x18004cc70  mov     [rbp+57h+var_50], 0FFFFFFFFFFFFFFFEh
0x18004cc78  mov     rbx, rcx
0x18004cc7b  cmp     dword ptr [rcx+8], 0
0x18004cc7f  jnz     loc_18004CE33
0x18004cc85  cmp     dword ptr [rcx+0Ch], 0
0x18004cc89  jz      loc_18004CE7A
0x18004cc8f  test    rdx, rdx
0x18004cc92  jz      loc_18004CEC6
0x18004cc98  call    ?FixupName@RegistryKey@UnBCL@@AEAAPEAVString@2@AEBV32@@Z; UnBCL::RegistryKey::FixupName(UnBCL::String const &)
0x18004cc9d  mov     rdx, rax; struct UnBCL::String *
0x18004cca0  mov     r8d, 1
0x18004cca6  lea     rcx, [rbp+57h+var_30]; this
0x18004ccaa  call    ??0StringPtr@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::StringPtr::StringPtr(UnBCL::String *)
0x18004ccaf  nop
0x18004ccb0  mov     rax, [rbp+57h+var_28]
0x18004ccb4  movsxd  rdx, dword ptr [rax+4]
0x18004ccb8  mov     r8d, 1; int
0x18004ccbe  mov     rdx, [rbp+rdx+57h+var_20]; struct UnBCL::String *
0x18004ccc3  mov     rcx, rbx; this
0x18004ccc6  call    ?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@H@Z; UnBCL::RegistryKey::OpenSubKey(UnBCL::String const *,int)
0x18004cccb  mov     rdx, rax
0x18004ccce  lea     rcx, [rbp+57h+var_40]
0x18004ccd2  call    ??0?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@QEAA@PEAVRegistryKey@1@@Z; UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(UnBCL::RegistryKey *)
0x18004ccd7  nop
0x18004ccd8  mov     rdi, [rbp+57h+var_38]
0x18004ccdc  test    rdi, rdi
0x18004ccdf  jz      short loc_18004CD26
0x18004cce1  mov     rcx, [rdi]
0x18004cce4  movsxd  rdx, dword ptr [rcx+4]
0x18004cce8  lock dec dword ptr [rdx+rdi+8]
0x18004cced  mov     [rbp+57h+var_38], 0
0x18004ccf5  lea     rcx, ??_7?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable'
0x18004ccfc  mov     [rbp+57h+var_40], rcx
0x18004cd00  lea     rcx, [rbp+57h+var_40]
0x18004cd04  call    ?DeAssign@?$SmartPtr@VMultiSz@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::MultiSz>::DeAssign(void)
0x18004cd09  nop
0x18004cd0a  lea     rcx, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x18004cd11  mov     [rbp+57h+var_20], rcx
0x18004cd15  lea     rcx, [rbp+57h+var_20]
0x18004cd19  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18004cd1e  mov     rax, rdi
0x18004cd21  jmp     loc_18004CDE3
0x18004cd26  mov     [rbp+57h+dwDisposition], 0
0x18004cd2d  mov     [rbp+57h+arg_10], 0
0x18004cd35  mov     rax, [rbp+57h+var_28]
0x18004cd39  movsxd  rcx, dword ptr [rax+4]
0x18004cd3d  mov     rdx, [rbp+rcx+57h+var_20]
0x18004cd42  mov     rcx, [rbx+10h]
0x18004cd46  lea     rax, [rbp+57h+dwDisposition]
0x18004cd4a  mov     [rsp+0A0h+lpdwDisposition], rax; lpdwDisposition
0x18004cd4f  lea     rax, [rbp+57h+arg_10]
0x18004cd53  mov     [rsp+0A0h+phkResult], rax; phkResult
0x18004cd58  mov     [rsp+0A0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18004cd61  mov     [rsp+0A0h+samDesired], 2001Fh; samDesired
0x18004cd69  mov     [rsp+0A0h+dwOptions], 0; dwOptions
0x18004cd71  xor     r9d, r9d; lpClass
0x18004cd74  xor     r8d, r8d; Reserved
0x18004cd77  mov     rdx, [rdx+10h]; lpSubKey
0x18004cd7b  mov     rcx, [rcx]; hKey
0x18004cd7e  call    cs:__imp_RegCreateKeyExW
0x18004cd84  mov     ebx, eax
0x18004cd86  mov     ecx, 40h ; '@'; unsigned __int64
0x18004cd8b  test    eax, eax
0x18004cd8d  jnz     short loc_18004CDEE
0x18004cd8f  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004cd94  mov     [rbp+57h+pExceptionObject], rax
0x18004cd98  test    rax, rax
0x18004cd9b  jz      short loc_18004CDB5
0x18004cd9d  lea     r9d, [rbx+1]
0x18004cda1  mov     r8d, r9d; int
0x18004cda4  mov     rdx, [rbp+57h+arg_10]; HKEY
0x18004cda8  mov     rcx, rax; this
0x18004cdab  call    ??0RegistryKey@UnBCL@@QEAA@PEAUHKEY__@@H@Z; UnBCL::RegistryKey::RegistryKey(HKEY__ *,int)
0x18004cdb0  mov     rbx, rax
0x18004cdb3  jmp     short loc_18004CDB7
0x18004cdb5  xor     ebx, ebx
0x18004cdb7  lea     rcx, ??_7?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable'
0x18004cdbe  mov     [rbp+57h+var_40], rcx
0x18004cdc2  lea     rcx, [rbp+57h+var_40]
0x18004cdc6  call    ?DeAssign@?$SmartPtr@VMultiSz@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::MultiSz>::DeAssign(void)
0x18004cdcb  nop
0x18004cdcc  lea     rcx, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x18004cdd3  mov     [rbp+57h+var_20], rcx
0x18004cdd7  lea     rcx, [rbp+57h+var_20]
0x18004cddb  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18004cde0  mov     rax, rbx
0x18004cde3  add     rsp, 90h
0x18004cdea  pop     rdi
0x18004cdeb  pop     rbx
0x18004cdec  pop     rbp
0x18004cded  retn
0x18004cdee  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004cdf3  nop
0x18004cdf4  mov     [rbp+57h+var_48], rax
0x18004cdf8  test    rax, rax
0x18004cdfb  jz      short loc_18004CE0F
0x18004cdfd  lea     r8, aUnableToCreate_0; "unable to create subkey"
0x18004ce04  mov     edx, ebx; dwMessageId
0x18004ce06  mov     rcx, rax; this
0x18004ce09  call    ??0Win32Exception@UnBCL@@QEAA@KPEBG@Z; UnBCL::Win32Exception::Win32Exception(ulong,ushort const *)
0x18004ce0e  nop
0x18004ce0f  lea     rdx, aClassUnbclRegi; "class UnBCL::RegistryKey *__cdecl UnBCL"...
0x18004ce16  mov     rcx, rax
0x18004ce19  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004ce1e  mov     [rbp+57h+pExceptionObject], rax
0x18004ce22  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18004ce29  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18004ce2d  call    _CxxThrowException_0
0x18004ce33  mov     ecx, 38h ; '8'; unsigned __int64
0x18004ce38  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004ce3d  mov     [rbp+57h+var_48], rax
0x18004ce41  test    rax, rax
0x18004ce44  jz      short loc_18004CE56
0x18004ce46  lea     rdx, aMethodCalledOn; "method called on closed RegistryKey"
0x18004ce4d  mov     rcx, rax; this
0x18004ce50  call    ??0ObjectDisposedException@UnBCL@@QEAA@PEBG@Z; UnBCL::ObjectDisposedException::ObjectDisposedException(ushort const *)
0x18004ce55  nop
0x18004ce56  lea     rdx, aClassUnbclRegi; "class UnBCL::RegistryKey *__cdecl UnBCL"...
0x18004ce5d  mov     rcx, rax
0x18004ce60  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004ce65  mov     [rbp+57h+pExceptionObject], rax
0x18004ce69  lea     rdx, _TI5PEAVObjectDisposedException@UnBCL@@; pThrowInfo
0x18004ce70  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18004ce74  call    _CxxThrowException_0
0x18004ce7a  mov     ecx, 40h ; '@'; unsigned __int64
0x18004ce7f  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004ce84  mov     [rbp+57h+var_48], rax
0x18004ce88  test    rax, rax
0x18004ce8b  jz      short loc_18004CEA2
0x18004ce8d  lea     r8, aAttemptToCreat_0; "attempt to create subkey of key opened "...
0x18004ce94  mov     edx, 5; dwMessageId
0x18004ce99  mov     rcx, rax; this
0x18004ce9c  call    ??0Win32Exception@UnBCL@@QEAA@KPEBG@Z; UnBCL::Win32Exception::Win32Exception(ulong,ushort const *)
0x18004cea1  nop
0x18004cea2  lea     rdx, aClassUnbclRegi; "class UnBCL::RegistryKey *__cdecl UnBCL"...
0x18004cea9  mov     rcx, rax
0x18004ceac  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004ceb1  mov     [rbp+57h+pExceptionObject], rax
0x18004ceb5  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18004cebc  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18004cec0  call    _CxxThrowException_0
0x18004cec6  mov     ecx, 38h ; '8'; unsigned __int64
0x18004cecb  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004ced0  mov     [rbp+57h+var_48], rax
0x18004ced4  test    rax, rax
0x18004ced7  jz      short loc_18004CEE9
0x18004ced9  lea     rdx, aNullKeynameToR_0; "null keyname to RegistryKey#CreateSubKe"...
0x18004cee0  mov     rcx, rax; this
0x18004cee3  call    ??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x18004cee8  nop
0x18004cee9  lea     rdx, aClassUnbclRegi; "class UnBCL::RegistryKey *__cdecl UnBCL"...
0x18004cef0  mov     rcx, rax
0x18004cef3  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004cef8  mov     [rbp+57h+pExceptionObject], rax
0x18004cefc  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x18004cf03  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18004cf07  call    _CxxThrowException_0
```
