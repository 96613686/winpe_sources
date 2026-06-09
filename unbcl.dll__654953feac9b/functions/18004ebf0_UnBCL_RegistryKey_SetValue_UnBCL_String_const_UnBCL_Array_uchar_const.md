# UnBCL::RegistryKey::SetValue(UnBCL::String const *,UnBCL::Array<uchar> const *)

- ea: `0x18004ebf0`
- end: `0x18004edb1`
- name: `?SetValue@RegistryKey@UnBCL@@QEAAXPEBVString@2@PEBV?$Array@E@2@@Z`
- size: `449`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x18000225c`
- `0x1800099b0`
- `0x180009e7c`
- `0x1800477d0`
- `0x180047d60`
- `0x18004ebf0`
- `0x1800641a0`
- `0x18006f010`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18004ec6f`
- `ADVAPI32!RegSetValueExW` at `0x18004ec6f`

## string_xrefs

- `0x18004ecea`: `method called on closed RegistryKey`
- `0x18004ed31`: `attempt to set value on key opened read-only`
- `0x18004ed7d`: `null value to RegistryKey#SetValue`
- `0x18004ecb3`: `void __cdecl UnBCL::RegistryKey::SetValue(const class UnBCL::String *,const class UnBCL::Array<unsigned char> *)`
- `0x18004ecfa`: `void __cdecl UnBCL::RegistryKey::SetValue(const class UnBCL::String *,const class UnBCL::Array<unsigned char> *)`
- `0x18004ed46`: `void __cdecl UnBCL::RegistryKey::SetValue(const class UnBCL::String *,const class UnBCL::Array<unsigned char> *)`
- `0x18004ed8d`: `void __cdecl UnBCL::RegistryKey::SetValue(const class UnBCL::String *,const class UnBCL::Array<unsigned char> *)`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
LSTATUS __fastcall UnBCL::RegistryKey::SetValue(__int64 a1, __int64 a2, __int64 a3)
{
  HKEY *v5; // rdi
  DWORD cbData; // ebx
  const BYTE *lpData; // rax
  LSTATUS result; // eax
  DWORD v9; // ebx
  UnBCL::Win32Exception *v10; // rax
  UnBCL::ObjectDisposedException *v11; // rax
  UnBCL::Win32Exception *v12; // rax
  UnBCL::ArgumentNullException *v13; // rax
  __int64 pExceptionObject; // [rsp+60h] [rbp+20h] BYREF
  UnBCL::ObjectDisposedException *v15; // [rsp+78h] [rbp+38h]

  if ( *(_DWORD *)(a1 + 8) )
  {
    v11 = (UnBCL::ObjectDisposedException *)UnBCL::Object::operator new(0x38u);
    v15 = v11;
    if ( v11 )
      v11 = (UnBCL::ObjectDisposedException *)UnBCL::ObjectDisposedException::ObjectDisposedException(
                                                v11,
                                                L"method called on closed RegistryKey");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v11,
                         "void __cdecl UnBCL::RegistryKey::SetValue(const class UnBCL::String *,const class UnBCL::Array<"
                         "unsigned char> *)");
    throw (UnBCL::ObjectDisposedException **)&pExceptionObject;
  }
  if ( !*(_DWORD *)(a1 + 12) )
  {
    v12 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    v15 = v12;
    if ( v12 )
      v12 = (UnBCL::Win32Exception *)UnBCL::Win32Exception::Win32Exception(
                                       v12,
                                       5u,
                                       L"attempt to set value on key opened read-only");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v12,
                         "void __cdecl UnBCL::RegistryKey::SetValue(const class UnBCL::String *,const class UnBCL::Array<"
                         "unsigned char> *)");
    throw (UnBCL::Win32Exception **)&pExceptionObject;
  }
  if ( !a3 )
  {
    v13 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v15 = v13;
    if ( v13 )
      v13 = (UnBCL::ArgumentNullException *)UnBCL::ArgumentNullException::ArgumentNullException(
                                              v13,
                                              L"null value to RegistryKey#SetValue");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v13,
                         "void __cdecl UnBCL::RegistryKey::SetValue(const class UnBCL::String *,const class UnBCL::Array<"
                         "unsigned char> *)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  v5 = *(HKEY **)(a1 + 16);
  cbData = (**(__int64 (__fastcall ***)(__int64))a3)(a3);
  lpData = (const BYTE *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a3 + 48LL))(a3, 0);
  result = RegSetValueExW(*v5, *(LPCWSTR *)(a2 + 16), 0, 3u, lpData, cbData);
  v9 = result;
  if ( result )
  {
    v10 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    v15 = v10;
    if ( v10 )
      v10 = (UnBCL::Win32Exception *)UnBCL::Win32Exception::Win32Exception(v10, v9, L"unable to set value on key");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v10,
                         "void __cdecl UnBCL::RegistryKey::SetValue(const class UnBCL::String *,const class UnBCL::Array<"
                         "unsigned char> *)");
    throw (UnBCL::Win32Exception **)&pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x18004ebf0  push    rbp
0x18004ebf2  push    rdi
0x18004ebf3  push    r14
0x18004ebf5  mov     rbp, rsp
0x18004ebf8  sub     rsp, 40h
0x18004ebfc  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFEh
0x18004ec04  mov     [rsp+40h+arg_8], rbx
0x18004ec09  mov     [rsp+40h+arg_10], rsi
0x18004ec0e  mov     rsi, r8
0x18004ec11  mov     r14, rdx
0x18004ec14  cmp     dword ptr [rcx+8], 0
0x18004ec18  jnz     loc_18004ECD7
0x18004ec1e  cmp     dword ptr [rcx+0Ch], 0
0x18004ec22  jz      loc_18004ED1E
0x18004ec28  test    r8, r8
0x18004ec2b  jz      loc_18004ED6A
0x18004ec31  mov     rdi, [rcx+10h]
0x18004ec35  mov     rax, [r8]
0x18004ec38  mov     rcx, r8
0x18004ec3b  mov     rax, [rax]
0x18004ec3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ec43  mov     ebx, eax
0x18004ec45  mov     rdx, [rsi]
0x18004ec48  mov     rax, [rdx+30h]
0x18004ec4c  xor     edx, edx
0x18004ec4e  mov     rcx, rsi
0x18004ec51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ec56  mov     [rsp+40h+cbData], ebx; cbData
0x18004ec5a  mov     [rsp+40h+lpData], rax; lpData
0x18004ec5f  mov     r9d, 3; dwType
0x18004ec65  xor     r8d, r8d; Reserved
0x18004ec68  mov     rdx, [r14+10h]; lpValueName
0x18004ec6c  mov     rcx, [rdi]; hKey
0x18004ec6f  call    cs:__imp_RegSetValueExW
0x18004ec75  mov     ebx, eax
0x18004ec77  test    eax, eax
0x18004ec79  jnz     short loc_18004EC8E
0x18004ec7b  mov     rbx, [rsp+40h+arg_8]
0x18004ec80  mov     rsi, [rsp+40h+arg_10]
0x18004ec85  add     rsp, 40h
0x18004ec89  pop     r14
0x18004ec8b  pop     rdi
0x18004ec8c  pop     rbp
0x18004ec8d  retn
0x18004ec8e  mov     ecx, 40h ; '@'; unsigned __int64
0x18004ec93  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004ec98  mov     [rbp+arg_18], rax
0x18004ec9c  test    rax, rax
0x18004ec9f  jz      short loc_18004ECB3
0x18004eca1  lea     r8, aUnableToSetVal; "unable to set value on key"
0x18004eca8  mov     edx, ebx; dwMessageId
0x18004ecaa  mov     rcx, rax; this
0x18004ecad  call    ??0Win32Exception@UnBCL@@QEAA@KPEBG@Z; UnBCL::Win32Exception::Win32Exception(ulong,ushort const *)
0x18004ecb2  nop
0x18004ecb3  lea     rdx, aVoidCdeclUnbcl_77; "void __cdecl UnBCL::RegistryKey::SetVal"...
0x18004ecba  mov     rcx, rax
0x18004ecbd  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004ecc2  mov     [rbp+pExceptionObject], rax
0x18004ecc6  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18004eccd  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18004ecd1  call    _CxxThrowException_0
0x18004ecd7  mov     ecx, 38h ; '8'; unsigned __int64
0x18004ecdc  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004ece1  mov     [rbp+arg_18], rax
0x18004ece5  test    rax, rax
0x18004ece8  jz      short loc_18004ECFA
0x18004ecea  lea     rdx, aMethodCalledOn; "method called on closed RegistryKey"
0x18004ecf1  mov     rcx, rax; this
0x18004ecf4  call    ??0ObjectDisposedException@UnBCL@@QEAA@PEBG@Z; UnBCL::ObjectDisposedException::ObjectDisposedException(ushort const *)
0x18004ecf9  nop
0x18004ecfa  lea     rdx, aVoidCdeclUnbcl_77; "void __cdecl UnBCL::RegistryKey::SetVal"...
0x18004ed01  mov     rcx, rax
0x18004ed04  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004ed09  mov     [rbp+pExceptionObject], rax
0x18004ed0d  lea     rdx, _TI5PEAVObjectDisposedException@UnBCL@@; pThrowInfo
0x18004ed14  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18004ed18  call    _CxxThrowException_0
0x18004ed1e  mov     ecx, 40h ; '@'; unsigned __int64
0x18004ed23  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004ed28  mov     [rbp+arg_18], rax
0x18004ed2c  test    rax, rax
0x18004ed2f  jz      short loc_18004ED46
0x18004ed31  lea     r8, aAttemptToSetVa; "attempt to set value on key opened read"...
0x18004ed38  mov     edx, 5; dwMessageId
0x18004ed3d  mov     rcx, rax; this
0x18004ed40  call    ??0Win32Exception@UnBCL@@QEAA@KPEBG@Z; UnBCL::Win32Exception::Win32Exception(ulong,ushort const *)
0x18004ed45  nop
0x18004ed46  lea     rdx, aVoidCdeclUnbcl_77; "void __cdecl UnBCL::RegistryKey::SetVal"...
0x18004ed4d  mov     rcx, rax
0x18004ed50  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004ed55  mov     [rbp+pExceptionObject], rax
0x18004ed59  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18004ed60  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18004ed64  call    _CxxThrowException_0
0x18004ed6a  mov     ecx, 38h ; '8'; unsigned __int64
0x18004ed6f  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004ed74  mov     [rbp+arg_18], rax
0x18004ed78  test    rax, rax
0x18004ed7b  jz      short loc_18004ED8D
0x18004ed7d  lea     rdx, aNullValueToReg; "null value to RegistryKey#SetValue"
0x18004ed84  mov     rcx, rax; this
0x18004ed87  call    ??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x18004ed8c  nop
0x18004ed8d  lea     rdx, aVoidCdeclUnbcl_77; "void __cdecl UnBCL::RegistryKey::SetVal"...
0x18004ed94  mov     rcx, rax
0x18004ed97  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004ed9c  mov     [rbp+pExceptionObject], rax
0x18004eda0  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x18004eda7  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18004edab  call    _CxxThrowException_0
```
