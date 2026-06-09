# UnBCL::RegistryKey::SetValue(UnBCL::String const *,UnBCL::Array<UnBCL::String *> const *)

- ea: `0x18004edc0`
- end: `0x18004f0dd`
- name: `?SetValue@RegistryKey@UnBCL@@QEAAXPEBVString@2@PEBV?$Array@PEAVString@UnBCL@@@2@@Z`
- size: `797`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config`

## callees

- `0x18000225c`
- `0x180002276`
- `0x1800099b0`
- `0x180009e7c`
- `0x18000afd0`
- `0x180011940`
- `0x1800477d0`
- `0x180047d60`
- `0x18004edc0`
- `0x1800641a0`
- `0x18006f010`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18004ef7f`
- `ADVAPI32!RegSetValueExW` at `0x18004ef7f`

## string_xrefs

- `0x18004f016`: `method called on closed RegistryKey`
- `0x18004f05d`: `attempt to set value on key opened read-only`
- `0x18004f0a9`: `null value to RegistryKey#SetValue`
- `0x18004efdf`: `void __cdecl UnBCL::RegistryKey::SetValue(const class UnBCL::String *,const class UnBCL::Array<class UnBCL::String *> *)`
- `0x18004f026`: `void __cdecl UnBCL::RegistryKey::SetValue(const class UnBCL::String *,const class UnBCL::Array<class UnBCL::String *> *)`
- `0x18004f072`: `void __cdecl UnBCL::RegistryKey::SetValue(const class UnBCL::String *,const class UnBCL::Array<class UnBCL::String *> *)`
- `0x18004f0b9`: `void __cdecl UnBCL::RegistryKey::SetValue(const class UnBCL::String *,const class UnBCL::Array<class UnBCL::String *> *)`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void **__fastcall UnBCL::RegistryKey::SetValue(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v5; // r14d
  int i; // ebx
  __int64 v7; // rcx
  unsigned int v8; // r13d
  unsigned int j; // r12d
  __int64 v10; // rcx
  unsigned int v11; // edi
  __int64 v12; // rcx
  const void *v13; // rbx
  void *v14; // rax
  char *v15; // rcx
  HKEY *v16; // rdi
  __int64 (__fastcall ***v17)(_QWORD); // rcx
  DWORD cbData; // ebx
  const BYTE *lpData; // rax
  LSTATUS v20; // ebx
  void **result; // rax
  UnBCL::Win32Exception *v22; // rax
  UnBCL::ObjectDisposedException *v23; // rax
  UnBCL::Win32Exception *v24; // rax
  UnBCL::ArgumentNullException *v25; // rax
  __int64 v26; // [rsp+48h] [rbp-89h] BYREF
  _QWORD *v27; // [rsp+58h] [rbp-79h]
  void **v28; // [rsp+68h] [rbp-69h] BYREF
  __int64 pExceptionObject; // [rsp+138h] [rbp+67h] BYREF
  __int64 v30; // [rsp+140h] [rbp+6Fh]
  UnBCL::ObjectDisposedException *v31; // [rsp+150h] [rbp+7Fh]

  v30 = a2;
  if ( *(_DWORD *)(a1 + 8) )
  {
    v23 = (UnBCL::ObjectDisposedException *)UnBCL::Object::operator new(0x38u);
    v31 = v23;
    if ( v23 )
      v23 = (UnBCL::ObjectDisposedException *)UnBCL::ObjectDisposedException::ObjectDisposedException(
                                                v23,
                                                L"method called on closed RegistryKey");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v23,
                         "void __cdecl UnBCL::RegistryKey::SetValue(const class UnBCL::String *,const class UnBCL::Array<"
                         "class UnBCL::String *> *)");
    throw (UnBCL::ObjectDisposedException **)&pExceptionObject;
  }
  if ( !*(_DWORD *)(a1 + 12) )
  {
    v24 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    v31 = v24;
    if ( v24 )
      v24 = (UnBCL::Win32Exception *)UnBCL::Win32Exception::Win32Exception(
                                       v24,
                                       5u,
                                       L"attempt to set value on key opened read-only");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v24,
                         "void __cdecl UnBCL::RegistryKey::SetValue(const class UnBCL::String *,const class UnBCL::Array<"
                         "class UnBCL::String *> *)");
    throw (UnBCL::Win32Exception **)&pExceptionObject;
  }
  if ( !a3 )
  {
    v25 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v31 = v25;
    if ( v25 )
      v25 = (UnBCL::ArgumentNullException *)UnBCL::ArgumentNullException::ArgumentNullException(
                                              v25,
                                              L"null value to RegistryKey#SetValue");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v25,
                         "void __cdecl UnBCL::RegistryKey::SetValue(const class UnBCL::String *,const class UnBCL::Array<"
                         "class UnBCL::String *> *)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  v5 = 1;
  for ( i = 0; i < (**(int (__fastcall ***)(__int64))a3)(a3); ++i )
  {
    v7 = a3 + *(int *)(*(_QWORD *)(a3 + 8) + 16LL) + 8LL;
    v5 += *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v7 + 16LL))(
                                               v7,
                                               (unsigned int)i)
                                + 16LL)
                    - 16LL)
        + 1;
  }
  UnBCL::Array<unsigned short>::Array<unsigned short>(&v26, v5, 0, 1);
  v8 = 0;
  for ( j = 0; (int)j < (**(int (__fastcall ***)(__int64))a3)(a3); ++j )
  {
    v10 = a3 + *(int *)(*(_QWORD *)(a3 + 8) + 16LL) + 8LL;
    v11 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v10 + 16LL))(
                                               v10,
                                               j)
                                + 16LL)
                    - 16LL)
        + 1;
    v12 = a3 + *(int *)(*(_QWORD *)(a3 + 8) + 16LL) + 8LL;
    v13 = *(const void **)(*(_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v12 + 16LL))(v12, j) + 16LL);
    v14 = (void *)(*(__int64 (__fastcall **)(_QWORD *, _QWORD))(*v27 + 112LL))(v27, v8);
    memcpy_0(v14, v13, 2LL * v11);
    v8 += v11;
  }
  v15 = (char *)v27 + *(int *)(v27[1] + 16LL) + 8;
  (*(void (__fastcall **)(char *, _QWORD, _QWORD))(*(_QWORD *)v15 + 32LL))(v15, v5 - 1, 0);
  v16 = *(HKEY **)(a1 + 16);
  v17 = (__int64 (__fastcall ***)(_QWORD))((char *)v27 + *(int *)(v27[1] + 12LL) + 8);
  cbData = 2 * (**v17)(v17);
  lpData = (const BYTE *)(*(__int64 (__fastcall **)(_QWORD *, _QWORD))(*v27 + 112LL))(v27, 0);
  v20 = RegSetValueExW(*v16, *(LPCWSTR *)(v30 + 16), 0, 7u, lpData, cbData);
  if ( v20 )
  {
    v22 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    v31 = v22;
    if ( v22 )
      v22 = (UnBCL::Win32Exception *)UnBCL::Win32Exception::Win32Exception(v22, v20, L"unable to set value on key");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v22,
                         "void __cdecl UnBCL::RegistryKey::SetValue(const class UnBCL::String *,const class UnBCL::Array<"
                         "class UnBCL::String *> *)");
    throw (UnBCL::Win32Exception **)&pExceptionObject;
  }
  UnBCL::Array<unsigned short>::~Array<unsigned short>(&v28);
  result = &UnBCL::Object::`vftable';
  v28 = &UnBCL::Object::`vftable';
  return result;
}

```

## disassembly

```asm
0x18004edc0  mov     rax, rsp
0x18004edc3  mov     [rax+10h], rdx
0x18004edc7  push    rbp
0x18004edc8  push    rsi
0x18004edc9  push    rdi
0x18004edca  push    r12
0x18004edcc  push    r13
0x18004edce  push    r14
0x18004edd0  push    r15
0x18004edd2  lea     rbp, [rax-5Fh]
0x18004edd6  sub     rsp, 0F0h
0x18004eddd  mov     qword ptr [rsp+30h], 0FFFFFFFFFFFFFFFEh
0x18004ede6  mov     [rax+18h], rbx
0x18004edea  mov     rsi, r8
0x18004eded  mov     r15, rcx
0x18004edf0  cmp     dword ptr [rcx+8], 0
0x18004edf4  jnz     loc_18004F003
0x18004edfa  cmp     dword ptr [rcx+0Ch], 0
0x18004edfe  jz      loc_18004F04A
0x18004ee04  test    r8, r8
0x18004ee07  jz      loc_18004F096
0x18004ee0d  mov     edi, 1
0x18004ee12  mov     r14d, edi
0x18004ee15  xor     ebx, ebx
0x18004ee17  mov     rax, [rsi]
0x18004ee1a  mov     rcx, rsi
0x18004ee1d  mov     rax, [rax]
0x18004ee20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ee25  cmp     ebx, eax
0x18004ee27  jge     short loc_18004EE59
0x18004ee29  mov     rax, [rsi+8]
0x18004ee2d  movsxd  rcx, dword ptr [rax+10h]
0x18004ee31  add     rcx, 8
0x18004ee35  add     rcx, rsi
0x18004ee38  mov     rax, [rcx]
0x18004ee3b  mov     edx, ebx
0x18004ee3d  mov     rax, [rax+10h]
0x18004ee41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ee46  mov     rcx, [rax]
0x18004ee49  mov     rax, [rcx+10h]
0x18004ee4d  mov     ecx, [rax-10h]
0x18004ee50  inc     ecx
0x18004ee52  add     r14d, ecx
0x18004ee55  add     ebx, edi
0x18004ee57  jmp     short loc_18004EE17
0x18004ee59  mov     r9d, edi
0x18004ee5c  xor     r8d, r8d
0x18004ee5f  mov     edx, r14d
0x18004ee62  lea     rcx, [rsp+40h]
0x18004ee67  call    ??0?$Array@G@UnBCL@@QEAA@HH@Z; UnBCL::Array<ushort>::Array<ushort>(int,int)
0x18004ee6c  nop
0x18004ee6d  xor     r13d, r13d
0x18004ee70  xor     r12d, r12d
0x18004ee73  mov     rax, [rsi]
0x18004ee76  mov     rcx, rsi
0x18004ee79  mov     rax, [rax]
0x18004ee7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ee81  cmp     r12d, eax
0x18004ee84  jge     short loc_18004EF04
0x18004ee86  mov     rax, [rsi+8]
0x18004ee8a  movsxd  rcx, dword ptr [rax+10h]
0x18004ee8e  add     rcx, 8
0x18004ee92  add     rcx, rsi
0x18004ee95  mov     rax, [rcx]
0x18004ee98  mov     edx, r12d
0x18004ee9b  mov     rax, [rax+10h]
0x18004ee9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eea4  mov     rcx, [rax]
0x18004eea7  mov     rax, [rcx+10h]
0x18004eeab  mov     edi, [rax-10h]
0x18004eeae  inc     edi
0x18004eeb0  mov     rax, [rsi+8]
0x18004eeb4  movsxd  rcx, dword ptr [rax+10h]
0x18004eeb8  add     rcx, 8
0x18004eebc  add     rcx, rsi
0x18004eebf  mov     rax, [rcx]
0x18004eec2  mov     edx, r12d
0x18004eec5  mov     rax, [rax+10h]
0x18004eec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eece  mov     rcx, [rax]
0x18004eed1  mov     rbx, [rcx+10h]
0x18004eed5  mov     rcx, [rbp+57h+var_D0]
0x18004eed9  mov     rax, [rcx]
0x18004eedc  mov     edx, r13d
0x18004eedf  mov     rax, [rax+70h]
0x18004eee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eee8  mov     r8d, edi
0x18004eeeb  add     r8, r8; Size
0x18004eeee  mov     rdx, rbx; Src
0x18004eef1  mov     rcx, rax; void *
0x18004eef4  call    memcpy_0
0x18004eef9  add     r13d, edi
0x18004eefc  inc     r12d
0x18004eeff  jmp     loc_18004EE73
0x18004ef04  mov     rdx, [rbp+57h+var_D0]
0x18004ef08  mov     rax, [rdx+8]
0x18004ef0c  movsxd  rcx, dword ptr [rax+10h]
0x18004ef10  add     rcx, 8
0x18004ef14  add     rcx, rdx
0x18004ef17  mov     rax, [rcx]
0x18004ef1a  xor     r8d, r8d
0x18004ef1d  lea     edx, [r14-1]
0x18004ef21  mov     rax, [rax+20h]
0x18004ef25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ef2a  mov     rdi, [r15+10h]
0x18004ef2e  mov     rdx, [rbp+57h+var_D0]
0x18004ef32  mov     rax, [rdx+8]
0x18004ef36  movsxd  rcx, dword ptr [rax+0Ch]
0x18004ef3a  add     rdx, 8
0x18004ef3e  add     rcx, rdx
0x18004ef41  mov     rax, [rcx]
0x18004ef44  mov     rax, [rax]
0x18004ef47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ef4c  mov     ebx, eax
0x18004ef4e  add     ebx, ebx
0x18004ef50  mov     rcx, [rbp+57h+var_D0]
0x18004ef54  mov     rdx, [rcx]
0x18004ef57  mov     rax, [rdx+70h]
0x18004ef5b  xor     edx, edx
0x18004ef5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ef62  mov     [rsp+120h+cbData], ebx; cbData
0x18004ef66  mov     [rsp+120h+lpData], rax; lpData
0x18004ef6b  mov     r9d, 7; dwType
0x18004ef71  xor     r8d, r8d; Reserved
0x18004ef74  mov     rdx, [rbp+57h+arg_8]
0x18004ef78  mov     rdx, [rdx+10h]; lpValueName
0x18004ef7c  mov     rcx, [rdi]; hKey
0x18004ef7f  call    cs:__imp_RegSetValueExW
0x18004ef85  mov     ebx, eax
0x18004ef87  test    eax, eax
0x18004ef89  jnz     short loc_18004EFBA
0x18004ef8b  lea     rcx, [rbp+57h+var_C0]
0x18004ef8f  call    ??1?$Array@G@UnBCL@@UEAA@XZ; UnBCL::Array<ushort>::~Array<ushort>(void)
0x18004ef94  lea     rax, ??_7Object@UnBCL@@6B@; const UnBCL::Object::`vftable'
0x18004ef9b  mov     [rbp+57h+var_C0], rax
0x18004ef9f  mov     rbx, [rsp+120h+arg_10]
0x18004efa7  add     rsp, 0F0h
0x18004efae  pop     r15
0x18004efb0  pop     r14
0x18004efb2  pop     r13
0x18004efb4  pop     r12
0x18004efb6  pop     rdi
0x18004efb7  pop     rsi
0x18004efb8  pop     rbp
0x18004efb9  retn
0x18004efba  mov     ecx, 40h ; '@'; unsigned __int64
0x18004efbf  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004efc4  mov     [rbp+57h+arg_18], rax
0x18004efc8  test    rax, rax
0x18004efcb  jz      short loc_18004EFDF
0x18004efcd  lea     r8, aUnableToSetVal; "unable to set value on key"
0x18004efd4  mov     edx, ebx; dwMessageId
0x18004efd6  mov     rcx, rax; this
0x18004efd9  call    ??0Win32Exception@UnBCL@@QEAA@KPEBG@Z; UnBCL::Win32Exception::Win32Exception(ulong,ushort const *)
0x18004efde  nop
0x18004efdf  lea     rdx, aVoidCdeclUnbcl_137; "void __cdecl UnBCL::RegistryKey::SetVal"...
0x18004efe6  mov     rcx, rax
0x18004efe9  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004efee  mov     [rbp+57h+pExceptionObject], rax
0x18004eff2  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18004eff9  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18004effd  call    _CxxThrowException_0
0x18004f003  mov     ecx, 38h ; '8'; unsigned __int64
0x18004f008  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004f00d  mov     [rbp+57h+arg_18], rax
0x18004f011  test    rax, rax
0x18004f014  jz      short loc_18004F026
0x18004f016  lea     rdx, aMethodCalledOn; "method called on closed RegistryKey"
0x18004f01d  mov     rcx, rax; this
0x18004f020  call    ??0ObjectDisposedException@UnBCL@@QEAA@PEBG@Z; UnBCL::ObjectDisposedException::ObjectDisposedException(ushort const *)
0x18004f025  nop
0x18004f026  lea     rdx, aVoidCdeclUnbcl_137; "void __cdecl UnBCL::RegistryKey::SetVal"...
0x18004f02d  mov     rcx, rax
0x18004f030  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004f035  mov     [rbp+57h+pExceptionObject], rax
0x18004f039  lea     rdx, _TI5PEAVObjectDisposedException@UnBCL@@; pThrowInfo
0x18004f040  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18004f044  call    _CxxThrowException_0
0x18004f04a  mov     ecx, 40h ; '@'; unsigned __int64
0x18004f04f  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004f054  mov     [rbp+57h+arg_18], rax
0x18004f058  test    rax, rax
0x18004f05b  jz      short loc_18004F072
0x18004f05d  lea     r8, aAttemptToSetVa; "attempt to set value on key opened read"...
0x18004f064  mov     edx, 5; dwMessageId
0x18004f069  mov     rcx, rax; this
0x18004f06c  call    ??0Win32Exception@UnBCL@@QEAA@KPEBG@Z; UnBCL::Win32Exception::Win32Exception(ulong,ushort const *)
0x18004f071  nop
0x18004f072  lea     rdx, aVoidCdeclUnbcl_137; "void __cdecl UnBCL::RegistryKey::SetVal"...
0x18004f079  mov     rcx, rax
0x18004f07c  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004f081  mov     [rbp+57h+pExceptionObject], rax
0x18004f085  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18004f08c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18004f090  call    _CxxThrowException_0
0x18004f096  mov     ecx, 38h ; '8'; unsigned __int64
0x18004f09b  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004f0a0  mov     [rbp+57h+arg_18], rax
0x18004f0a4  test    rax, rax
0x18004f0a7  jz      short loc_18004F0B9
0x18004f0a9  lea     rdx, aNullValueToReg; "null value to RegistryKey#SetValue"
0x18004f0b0  mov     rcx, rax; this
0x18004f0b3  call    ??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x18004f0b8  nop
0x18004f0b9  lea     rdx, aVoidCdeclUnbcl_137; "void __cdecl UnBCL::RegistryKey::SetVal"...
0x18004f0c0  mov     rcx, rax
0x18004f0c3  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004f0c8  mov     [rbp+57h+pExceptionObject], rax
0x18004f0cc  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x18004f0d3  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18004f0d7  call    _CxxThrowException_0
```
