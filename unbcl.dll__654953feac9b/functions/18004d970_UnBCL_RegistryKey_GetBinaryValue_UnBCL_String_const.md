# UnBCL::RegistryKey::GetBinaryValue(UnBCL::String const *)

- ea: `0x18004d970`
- end: `0x18004db66`
- name: `?GetBinaryValue@RegistryKey@UnBCL@@QEAAPEAV?$Array@E@2@PEBVString@2@@Z`
- size: `502`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config`

## callees

- `0x18000225c`
- `0x180006b70`
- `0x180008de0`
- `0x180009e7c`
- `0x18000a470`
- `0x1800113c0`
- `0x1800477d0`
- `0x180047d60`
- `0x18004d970`
- `0x1800641a0`
- `0x18006f010`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18004d9ca`
- `ADVAPI32!RegQueryValueExW` at `0x18004da46`
- `ADVAPI32!RegQueryValueExW` at `0x18004d9ca`
- `ADVAPI32!RegQueryValueExW` at `0x18004da46`

## string_xrefs

- `0x18004dae9`: `method called on closed RegistryKey`
- `0x18004dab2`: `class UnBCL::Array<unsigned char> *__cdecl UnBCL::RegistryKey::GetBinaryValue(const class UnBCL::String *)`
- `0x18004daf9`: `class UnBCL::Array<unsigned char> *__cdecl UnBCL::RegistryKey::GetBinaryValue(const class UnBCL::String *)`
- `0x18004db42`: `class UnBCL::Array<unsigned char> *__cdecl UnBCL::RegistryKey::GetBinaryValue(const class UnBCL::String *)`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall UnBCL::RegistryKey::GetBinaryValue(__int64 a1, __int64 a2)
{
  LSTATUS v4; // edi
  void *v5; // rax
  HKEY *v6; // rbx
  BYTE *lpData; // rax
  LSTATUS v8; // ebx
  __int64 v9; // rbx
  UnBCL::Win32Exception *v11; // rax
  UnBCL::ObjectDisposedException *v12; // rax
  UnBCL::Win32Exception *v13; // rax
  DWORD cbData; // [rsp+30h] [rbp-20h] BYREF
  DWORD Type; // [rsp+34h] [rbp-1Ch] BYREF
  __int64 v16; // [rsp+38h] [rbp-18h]
  void **v17; // [rsp+40h] [rbp-10h] BYREF
  __int64 v18; // [rsp+48h] [rbp-8h]
  __int64 pExceptionObject; // [rsp+70h] [rbp+20h] BYREF
  UnBCL::ObjectDisposedException *v20; // [rsp+80h] [rbp+30h]

  v16 = -2;
  if ( *(_DWORD *)(a1 + 8) )
  {
    v12 = (UnBCL::ObjectDisposedException *)UnBCL::Object::operator new(0x38u);
    v20 = v12;
    if ( v12 )
      v12 = (UnBCL::ObjectDisposedException *)UnBCL::ObjectDisposedException::ObjectDisposedException(
                                                v12,
                                                L"method called on closed RegistryKey");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v12,
                         "class UnBCL::Array<unsigned char> *__cdecl UnBCL::RegistryKey::GetBinaryValue(const class UnBCL::String *)");
    throw (UnBCL::ObjectDisposedException **)&pExceptionObject;
  }
  Type = 0;
  cbData = 0;
  v4 = RegQueryValueExW(**(HKEY **)(a1 + 16), *(LPCWSTR *)(a2 + 16), 0, &Type, 0, &cbData);
  if ( v4 )
  {
    v13 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    v20 = v13;
    if ( v13 )
      v13 = (UnBCL::Win32Exception *)UnBCL::Win32Exception::Win32Exception(v13, v4, L"unable to query value");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v13,
                         "class UnBCL::Array<unsigned char> *__cdecl UnBCL::RegistryKey::GetBinaryValue(const class UnBCL::String *)");
    throw (UnBCL::Win32Exception **)&pExceptionObject;
  }
  v5 = UnBCL::Object::operator new(0xB0u);
  pExceptionObject = (__int64)v5;
  if ( v5 )
    v5 = (void *)UnBCL::Array<unsigned char>::Array<unsigned char>(v5, cbData, 0, (unsigned int)(v4 + 1));
  UnBCL::SmartPtr<UnBCL::Array<unsigned char>>::SmartPtr<UnBCL::Array<unsigned char>>(&v17, v5);
  v6 = *(HKEY **)(a1 + 16);
  lpData = (BYTE *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v18 + 56LL))(v18, 0);
  LODWORD(pExceptionObject) = 0;
  v8 = RegQueryValueExW(*v6, *(LPCWSTR *)(a2 + 16), 0, (LPDWORD)&pExceptionObject, lpData, &cbData);
  if ( v8 )
  {
LABEL_9:
    v11 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    v20 = v11;
    if ( v11 )
      v11 = (UnBCL::Win32Exception *)UnBCL::Win32Exception::Win32Exception(
                                       v11,
                                       v8,
                                       L"unable to get binary value on key");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v11,
                         "class UnBCL::Array<unsigned char> *__cdecl UnBCL::RegistryKey::GetBinaryValue(const class UnBCL::String *)");
    throw (UnBCL::Win32Exception **)&pExceptionObject;
  }
  if ( (_DWORD)pExceptionObject != 3 )
  {
    v8 = 13;
    goto LABEL_9;
  }
  v9 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::Steal(&v17);
  v17 = &UnBCL::SmartPtr<UnBCL::Array<unsigned char>>::`vftable';
  UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::SerializationStream::TypeFactoryList *>>::DeAssign(&v17);
  return v9;
}

```

## disassembly

```asm
0x18004d970  push    rbp
0x18004d972  push    rsi
0x18004d973  push    rdi
0x18004d974  mov     rbp, rsp
0x18004d977  sub     rsp, 50h
0x18004d97b  mov     [rbp+var_18], 0FFFFFFFFFFFFFFFEh
0x18004d983  mov     [rsp+50h+arg_8], rbx
0x18004d988  mov     rsi, rdx
0x18004d98b  mov     rbx, rcx
0x18004d98e  cmp     dword ptr [rcx+8], 0
0x18004d992  jnz     loc_18004DAD6
0x18004d998  mov     [rbp+Type], 0
0x18004d99f  mov     [rbp+cbData], 0
0x18004d9a6  mov     rcx, [rcx+10h]
0x18004d9aa  lea     rax, [rbp+cbData]
0x18004d9ae  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18004d9b3  mov     [rsp+50h+lpData], 0; lpData
0x18004d9bc  lea     r9, [rbp+Type]; lpType
0x18004d9c0  xor     r8d, r8d; lpReserved
0x18004d9c3  mov     rdx, [rdx+10h]; lpValueName
0x18004d9c7  mov     rcx, [rcx]; hKey
0x18004d9ca  call    cs:__imp_RegQueryValueExW
0x18004d9d0  mov     edi, eax
0x18004d9d2  test    eax, eax
0x18004d9d4  jnz     loc_18004DB1D
0x18004d9da  mov     ecx, 0B0h; unsigned __int64
0x18004d9df  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004d9e4  mov     [rbp+pExceptionObject], rax
0x18004d9e8  test    rax, rax
0x18004d9eb  jz      short loc_18004DA00
0x18004d9ed  lea     r9d, [rdi+1]
0x18004d9f1  xor     r8d, r8d
0x18004d9f4  mov     edx, [rbp+cbData]
0x18004d9f7  mov     rcx, rax
0x18004d9fa  call    ??0?$Array@E@UnBCL@@QEAA@HH@Z; UnBCL::Array<uchar>::Array<uchar>(int,int)
0x18004d9ff  nop
0x18004da00  mov     rdx, rax
0x18004da03  lea     rcx, [rbp+var_10]
0x18004da07  call    ??0?$SmartPtr@V?$Array@E@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@E@1@@Z; UnBCL::SmartPtr<UnBCL::Array<uchar>>::SmartPtr<UnBCL::Array<uchar>>(UnBCL::Array<uchar> *)
0x18004da0c  nop
0x18004da0d  mov     rbx, [rbx+10h]
0x18004da11  mov     rcx, [rbp+var_8]
0x18004da15  mov     rax, [rcx]
0x18004da18  xor     edx, edx
0x18004da1a  mov     rax, [rax+38h]
0x18004da1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004da23  mov     dword ptr [rbp+pExceptionObject], 0
0x18004da2a  lea     rcx, [rbp+cbData]
0x18004da2e  mov     [rsp+50h+lpcbData], rcx; lpcbData
0x18004da33  mov     [rsp+50h+lpData], rax; lpData
0x18004da38  lea     r9, [rbp+pExceptionObject]; lpType
0x18004da3c  xor     r8d, r8d; lpReserved
0x18004da3f  mov     rdx, [rsi+10h]; lpValueName
0x18004da43  mov     rcx, [rbx]; hKey
0x18004da46  call    cs:__imp_RegQueryValueExW
0x18004da4c  mov     ebx, eax
0x18004da4e  test    eax, eax
0x18004da50  jnz     short loc_18004DA8D
0x18004da52  cmp     dword ptr [rbp+pExceptionObject], 3
0x18004da56  jnz     short loc_18004DA88
0x18004da58  lea     rcx, [rbp+var_10]
0x18004da5c  call    ?Steal@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::Steal(void)
0x18004da61  mov     rbx, rax
0x18004da64  lea     rax, ??_7?$SmartPtr@V?$Array@E@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::Array<uchar>>::`vftable'
0x18004da6b  mov     [rbp+var_10], rax
0x18004da6f  lea     rcx, [rbp+var_10]
0x18004da73  call    ?DeAssign@?$SmartPtr@U?$IEnumerator@PEAVTypeFactoryList@SerializationStream@UnBCL@@@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::SerializationStream::TypeFactoryList *>>::DeAssign(void)
0x18004da78  mov     rax, rbx
0x18004da7b  mov     rbx, [rsp+50h+arg_8]
0x18004da80  add     rsp, 50h
0x18004da84  pop     rdi
0x18004da85  pop     rsi
0x18004da86  pop     rbp
0x18004da87  retn
0x18004da88  mov     ebx, 0Dh
0x18004da8d  mov     ecx, 40h ; '@'; unsigned __int64
0x18004da92  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004da97  mov     [rbp+arg_10], rax
0x18004da9b  test    rax, rax
0x18004da9e  jz      short loc_18004DAB2
0x18004daa0  lea     r8, aUnableToGetBin; "unable to get binary value on key"
0x18004daa7  mov     edx, ebx; dwMessageId
0x18004daa9  mov     rcx, rax; this
0x18004daac  call    ??0Win32Exception@UnBCL@@QEAA@KPEBG@Z; UnBCL::Win32Exception::Win32Exception(ulong,ushort const *)
0x18004dab1  nop
0x18004dab2  lea     rdx, aClassUnbclArra_7; "class UnBCL::Array<unsigned char> *__cd"...
0x18004dab9  mov     rcx, rax
0x18004dabc  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004dac1  mov     [rbp+pExceptionObject], rax
0x18004dac5  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18004dacc  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18004dad0  call    _CxxThrowException_0
0x18004dad6  mov     ecx, 38h ; '8'; unsigned __int64
0x18004dadb  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004dae0  mov     [rbp+arg_10], rax
0x18004dae4  test    rax, rax
0x18004dae7  jz      short loc_18004DAF9
0x18004dae9  lea     rdx, aMethodCalledOn; "method called on closed RegistryKey"
0x18004daf0  mov     rcx, rax; this
0x18004daf3  call    ??0ObjectDisposedException@UnBCL@@QEAA@PEBG@Z; UnBCL::ObjectDisposedException::ObjectDisposedException(ushort const *)
0x18004daf8  nop
0x18004daf9  lea     rdx, aClassUnbclArra_7; "class UnBCL::Array<unsigned char> *__cd"...
0x18004db00  mov     rcx, rax
0x18004db03  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004db08  mov     [rbp+pExceptionObject], rax
0x18004db0c  lea     rdx, _TI5PEAVObjectDisposedException@UnBCL@@; pThrowInfo
0x18004db13  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18004db17  call    _CxxThrowException_0
0x18004db1d  mov     ecx, 40h ; '@'; unsigned __int64
0x18004db22  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004db27  mov     [rbp+arg_10], rax
0x18004db2b  test    rax, rax
0x18004db2e  jz      short loc_18004DB42
0x18004db30  lea     r8, aUnableToQueryV; "unable to query value"
0x18004db37  mov     edx, edi; dwMessageId
0x18004db39  mov     rcx, rax; this
0x18004db3c  call    ??0Win32Exception@UnBCL@@QEAA@KPEBG@Z; UnBCL::Win32Exception::Win32Exception(ulong,ushort const *)
0x18004db41  nop
0x18004db42  lea     rdx, aClassUnbclArra_7; "class UnBCL::Array<unsigned char> *__cd"...
0x18004db49  mov     rcx, rax
0x18004db4c  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004db51  mov     [rbp+pExceptionObject], rax
0x18004db55  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18004db5c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18004db60  call    _CxxThrowException_0
```
