# UnBCL::RegistryKey::GetSubKeyNames(void)

- ea: `0x18004de80`
- end: `0x18004e117`
- name: `?GetSubKeyNames@RegistryKey@UnBCL@@QEAAPEAV?$Array@PEAVString@UnBCL@@@2@XZ`
- size: `663`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x18004d2c0`

## callees

- `0x18000225c`
- `0x180006b70`
- `0x180008de0`
- `0x180009e7c`
- `0x18000afd0`
- `0x18000cc20`
- `0x180011450`
- `0x180011940`
- `0x1800477d0`
- `0x180047d60`
- `0x18004de80`
- `0x18004f0f0`
- `0x18005b790`
- `0x1800641a0`
- `0x18006f010`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x18004df9b`
- `ADVAPI32!RegEnumKeyExW` at `0x18004df9b`

## string_xrefs

- `0x18004e091`: `method called on closed RegistryKey`
- `0x18004e0a5`: `class UnBCL::Array<class UnBCL::String *> *__cdecl UnBCL::RegistryKey::GetSubKeyNames(void)`
- `0x18004e0f3`: `class UnBCL::Array<class UnBCL::String *> *__cdecl UnBCL::RegistryKey::GetSubKeyNames(void)`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall UnBCL::RegistryKey::GetSubKeyNames(__int64 a1)
{
  signed int SubKeyCount; // esi
  void *v3; // rax
  __int64 v4; // rax
  char *v5; // rbx
  __int64 v6; // rbx
  DWORD i; // edi
  __int64 (__fastcall ***v8)(_QWORD); // rcx
  WCHAR *v9; // rax
  LSTATUS v10; // r15d
  __int64 v11; // r12
  void (__fastcall *v12)(char *, _QWORD, UnBCL::String *); // r13
  UnBCL::String *v13; // rax
  UnBCL::String *v14; // r15
  const unsigned __int16 *v15; // rax
  UnBCL::ObjectDisposedException *v17; // rax
  __int64 v18; // rax
  UnBCL::Win32Exception *v19; // rax
  __int64 v20; // rax
  void **v21; // [rsp+48h] [rbp-C0h] BYREF
  char *v22; // [rsp+50h] [rbp-B8h]
  __int64 v23; // [rsp+58h] [rbp-B0h]
  __int64 v24; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD *v25; // [rsp+78h] [rbp-90h]
  void **v26; // [rsp+88h] [rbp-80h] BYREF
  __int64 cchName; // [rsp+158h] [rbp+50h] BYREF
  __int64 pExceptionObject; // [rsp+160h] [rbp+58h] BYREF
  UnBCL::Win32Exception *v29; // [rsp+168h] [rbp+60h]

  v23 = -2;
  if ( *(_DWORD *)(a1 + 8) )
  {
    v17 = (UnBCL::ObjectDisposedException *)UnBCL::Object::operator new(0x38u);
    pExceptionObject = (__int64)v17;
    if ( v17 )
      v18 = UnBCL::ObjectDisposedException::ObjectDisposedException(v17, L"method called on closed RegistryKey");
    else
      v18 = 0;
    cchName = AddStackTraceToException<UnBCL::InvalidOperationException>(
                v18,
                "class UnBCL::Array<class UnBCL::String *> *__cdecl UnBCL::RegistryKey::GetSubKeyNames(void)");
    throw (UnBCL::ObjectDisposedException **)&cchName;
  }
  SubKeyCount = UnBCL::RegistryKey::get_SubKeyCount((UnBCL::RegistryKey *)a1);
  v3 = UnBCL::Object::operator new(0xB0u);
  cchName = (__int64)v3;
  if ( v3 )
    v4 = UnBCL::Array<UnBCL::String *>::Array<UnBCL::String *>(v3, (unsigned int)SubKeyCount, 0, 1);
  else
    v4 = 0;
  UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::SmartPtr<UnBCL::Array<UnBCL::String *>>(&v21, v4);
  v5 = v22;
  if ( (**(unsigned int (__fastcall ***)(char *))v22)(v22) )
  {
    UnBCL::Array<unsigned short>::Array<unsigned short>(&v24, 256, 0, 1);
    for ( i = 0; (int)i < SubKeyCount; ++i )
    {
      v8 = (__int64 (__fastcall ***)(_QWORD))((char *)v25 + *(int *)(v25[1] + 12LL) + 8);
      LODWORD(cchName) = (**v8)(v8);
      v9 = (WCHAR *)(*(__int64 (__fastcall **)(_QWORD *, _QWORD))(*v25 + 112LL))(v25, 0);
      v10 = RegEnumKeyExW(**(HKEY **)(a1 + 16), i, v9, (LPDWORD)&cchName, 0, 0, 0, 0);
      if ( v10 )
      {
        v19 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
        v29 = v19;
        if ( v19 )
          v20 = UnBCL::Win32Exception::Win32Exception(v19, v10, L"unable to retrieve subkey name");
        else
          v20 = 0;
        pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                             v20,
                             "class UnBCL::Array<class UnBCL::String *> *__cdecl UnBCL::RegistryKey::GetSubKeyNames(void)");
        throw (UnBCL::Win32Exception **)&pExceptionObject;
      }
      v11 = *(int *)(*((_QWORD *)v5 + 1) + 16LL);
      v12 = *(void (__fastcall **)(char *, _QWORD, UnBCL::String *))(*(_QWORD *)&v5[v11 + 8] + 32LL);
      v13 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
      v14 = v13;
      pExceptionObject = (__int64)v13;
      if ( v13 )
      {
        v15 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD *, _QWORD))(*v25 + 112LL))(v25, 0);
        v13 = (UnBCL::String *)UnBCL::String::String(v14, v15);
      }
      v12(&v5[v11 + 8], i, v13);
    }
    (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v5 + 24LL))(v5, 1);
    v6 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::Steal(&v21);
    UnBCL::Array<unsigned short>::~Array<unsigned short>(&v26);
    v26 = &UnBCL::Object::`vftable';
  }
  else
  {
    v6 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::Steal(&v21);
  }
  v21 = &UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::`vftable';
  UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::SerializationStream::TypeFactoryList *>>::DeAssign(&v21);
  return v6;
}

```

## disassembly

```asm
0x18004de80  mov     rax, rsp
0x18004de83  push    rbp
0x18004de84  push    rsi
0x18004de85  push    rdi
0x18004de86  push    r12
0x18004de88  push    r13
0x18004de8a  push    r14
0x18004de8c  push    r15
0x18004de8e  lea     rbp, [rax-48h]
0x18004de92  sub     rsp, 110h
0x18004de99  mov     [rsp+140h+var_F0], 0FFFFFFFFFFFFFFFEh
0x18004dea2  mov     [rax+20h], rbx
0x18004dea6  mov     r14, rcx
0x18004dea9  xor     r12d, r12d
0x18004deac  cmp     [rcx+8], r12d
0x18004deb0  jnz     loc_18004E07E
0x18004deb6  call    ?get_SubKeyCount@RegistryKey@UnBCL@@QEBAHXZ; UnBCL::RegistryKey::get_SubKeyCount(void)
0x18004debb  mov     esi, eax
0x18004debd  mov     ecx, 0B0h; unsigned __int64
0x18004dec2  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004dec7  mov     [rbp+40h+cchName], rax
0x18004decb  lea     edi, [r12+1]
0x18004ded0  test    rax, rax
0x18004ded3  jz      short loc_18004DEE7
0x18004ded5  mov     r9d, edi
0x18004ded8  xor     r8d, r8d
0x18004dedb  mov     edx, esi
0x18004dedd  mov     rcx, rax
0x18004dee0  call    ??0?$Array@PEAVString@UnBCL@@@UnBCL@@QEAA@HH@Z; UnBCL::Array<UnBCL::String *>::Array<UnBCL::String *>(int,int)
0x18004dee5  jmp     short loc_18004DEEA
0x18004dee7  mov     rax, r12
0x18004deea  mov     rdx, rax
0x18004deed  lea     rcx, [rsp+140h+var_100]
0x18004def2  call    ??0?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@PEAVString@UnBCL@@@1@@Z; UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::SmartPtr<UnBCL::Array<UnBCL::String *>>(UnBCL::Array<UnBCL::String *> *)
0x18004def7  nop
0x18004def8  mov     rbx, [rsp+140h+var_F8]
0x18004defd  mov     rax, [rbx]
0x18004df00  mov     rcx, rbx
0x18004df03  mov     rax, [rax]
0x18004df06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004df0b  test    eax, eax
0x18004df0d  jnz     short loc_18004DF21
0x18004df0f  lea     rcx, [rsp+140h+var_100]
0x18004df14  call    ?Steal@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::Steal(void)
0x18004df19  mov     rbx, rax
0x18004df1c  jmp     loc_18004E04A
0x18004df21  mov     r9d, edi
0x18004df24  xor     r8d, r8d
0x18004df27  mov     edx, 100h
0x18004df2c  lea     rcx, [rsp+60h]
0x18004df31  call    ??0?$Array@G@UnBCL@@QEAA@HH@Z; UnBCL::Array<ushort>::Array<ushort>(int,int)
0x18004df36  nop
0x18004df37  mov     edi, r12d
0x18004df3a  test    esi, esi
0x18004df3c  jle     loc_18004E015
0x18004df42  mov     rdx, [rsp+140h+var_D0]
0x18004df47  mov     rax, [rdx+8]
0x18004df4b  movsxd  rcx, dword ptr [rax+0Ch]
0x18004df4f  add     rdx, 8
0x18004df53  add     rcx, rdx
0x18004df56  mov     rax, [rcx]
0x18004df59  mov     rax, [rax]
0x18004df5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004df61  mov     dword ptr [rbp+40h+cchName], eax
0x18004df64  mov     rcx, [rsp+140h+var_D0]
0x18004df69  mov     rax, [rcx]
0x18004df6c  xor     edx, edx
0x18004df6e  mov     rax, [rax+70h]
0x18004df72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004df77  mov     rcx, [r14+10h]
0x18004df7b  mov     [rsp+140h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18004df80  mov     [rsp+140h+lpcchClass], r12; lpcchClass
0x18004df85  mov     [rsp+140h+lpClass], r12; lpClass
0x18004df8a  mov     [rsp+140h+lpReserved], r12; lpReserved
0x18004df8f  lea     r9, [rbp+40h+cchName]; lpcchName
0x18004df93  mov     r8, rax; lpName
0x18004df96  mov     edx, edi; dwIndex
0x18004df98  mov     rcx, [rcx]; hKey
0x18004df9b  call    cs:__imp_RegEnumKeyExW
0x18004dfa1  mov     r15d, eax
0x18004dfa4  test    eax, eax
0x18004dfa6  jnz     loc_18004E0C9
0x18004dfac  mov     rax, [rbx+8]
0x18004dfb0  movsxd  r12, dword ptr [rax+10h]
0x18004dfb4  mov     rax, [r12+rbx+8]
0x18004dfb9  mov     r13, [rax+20h]
0x18004dfbd  lea     ecx, [r15+18h]; unsigned __int64
0x18004dfc1  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004dfc6  mov     r15, rax
0x18004dfc9  mov     [rbp+40h+pExceptionObject], rax
0x18004dfcd  test    rax, rax
0x18004dfd0  jz      short loc_18004DFF1
0x18004dfd2  mov     rcx, [rsp+140h+var_D0]
0x18004dfd7  mov     rdx, [rcx]
0x18004dfda  mov     rax, [rdx+70h]
0x18004dfde  xor     edx, edx
0x18004dfe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dfe5  mov     rdx, rax; unsigned __int16 *
0x18004dfe8  mov     rcx, r15; this
0x18004dfeb  call    ??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18004dff0  nop
0x18004dff1  mov     r8, rax
0x18004dff4  mov     edx, edi
0x18004dff6  lea     rcx, [rbx+8]
0x18004dffa  add     rcx, r12
0x18004dffd  mov     rax, r13
0x18004e000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e005  inc     edi
0x18004e007  cmp     edi, esi
0x18004e009  mov     r12d, 0
0x18004e00f  jl      loc_18004DF42
0x18004e015  mov     rax, [rbx]
0x18004e018  mov     edx, 1
0x18004e01d  mov     rcx, rbx
0x18004e020  mov     rax, [rax+18h]
0x18004e024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e029  lea     rcx, [rsp+140h+var_100]
0x18004e02e  call    ?Steal@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::Steal(void)
0x18004e033  mov     rbx, rax
0x18004e036  lea     rcx, [rbp+40h+var_C0]
0x18004e03a  call    ??1?$Array@G@UnBCL@@UEAA@XZ; UnBCL::Array<ushort>::~Array<ushort>(void)
0x18004e03f  lea     rax, ??_7Object@UnBCL@@6B@; const UnBCL::Object::`vftable'
0x18004e046  mov     [rbp+40h+var_C0], rax
0x18004e04a  lea     rax, ??_7?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::`vftable'
0x18004e051  mov     [rsp+140h+var_100], rax
0x18004e056  lea     rcx, [rsp+140h+var_100]
0x18004e05b  call    ?DeAssign@?$SmartPtr@U?$IEnumerator@PEAVTypeFactoryList@SerializationStream@UnBCL@@@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::SerializationStream::TypeFactoryList *>>::DeAssign(void)
0x18004e060  mov     rax, rbx
0x18004e063  mov     rbx, [rsp+140h+arg_18]
0x18004e06b  add     rsp, 110h
0x18004e072  pop     r15
0x18004e074  pop     r14
0x18004e076  pop     r13
0x18004e078  pop     r12
0x18004e07a  pop     rdi
0x18004e07b  pop     rsi
0x18004e07c  pop     rbp
0x18004e07d  retn
0x18004e07e  mov     ecx, 38h ; '8'; unsigned __int64
0x18004e083  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004e088  mov     [rbp+40h+pExceptionObject], rax
0x18004e08c  test    rax, rax
0x18004e08f  jz      short loc_18004E0A2
0x18004e091  lea     rdx, aMethodCalledOn; "method called on closed RegistryKey"
0x18004e098  mov     rcx, rax; this
0x18004e09b  call    ??0ObjectDisposedException@UnBCL@@QEAA@PEBG@Z; UnBCL::ObjectDisposedException::ObjectDisposedException(ushort const *)
0x18004e0a0  jmp     short loc_18004E0A5
0x18004e0a2  mov     rax, r12
0x18004e0a5  lea     rdx, aClassUnbclArra_3; "class UnBCL::Array<class UnBCL::String "...
0x18004e0ac  mov     rcx, rax
0x18004e0af  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004e0b4  mov     [rbp+40h+cchName], rax
0x18004e0b8  lea     rdx, _TI5PEAVObjectDisposedException@UnBCL@@; pThrowInfo
0x18004e0bf  lea     rcx, [rbp+40h+cchName]; pExceptionObject
0x18004e0c3  call    _CxxThrowException_0
0x18004e0c9  mov     ecx, 40h ; '@'; unsigned __int64
0x18004e0ce  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004e0d3  mov     [rbp+40h+arg_10], rax
0x18004e0d7  test    rax, rax
0x18004e0da  jz      short loc_18004E0F0
0x18004e0dc  lea     r8, aUnableToRetrie_1; "unable to retrieve subkey name"
0x18004e0e3  mov     edx, r15d; dwMessageId
0x18004e0e6  mov     rcx, rax; this
0x18004e0e9  call    ??0Win32Exception@UnBCL@@QEAA@KPEBG@Z; UnBCL::Win32Exception::Win32Exception(ulong,ushort const *)
0x18004e0ee  jmp     short loc_18004E0F3
0x18004e0f0  mov     rax, r12
0x18004e0f3  lea     rdx, aClassUnbclArra_3; "class UnBCL::Array<class UnBCL::String "...
0x18004e0fa  mov     rcx, rax
0x18004e0fd  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004e102  mov     [rbp+40h+pExceptionObject], rax
0x18004e106  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18004e10d  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x18004e111  call    _CxxThrowException_0
```
