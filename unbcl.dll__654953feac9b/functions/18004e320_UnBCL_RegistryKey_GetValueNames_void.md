# UnBCL::RegistryKey::GetValueNames(void)

- ea: `0x18004e320`
- end: `0x18004e658`
- name: `?GetValueNames@RegistryKey@UnBCL@@QEAAPEAV?$Array@PEAVString@UnBCL@@@2@XZ`
- size: `824`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config`

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
- `0x18004e320`
- `0x18005b790`
- `0x1800641a0`
- `0x18006f010`

## import_xrefs

- `ADVAPI32!RegQueryInfoKeyW` at `0x18004e3a1`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18004e3a1`
- `ADVAPI32!RegEnumValueW` at `0x18004e490`
- `ADVAPI32!RegEnumValueW` at `0x18004e490`

## string_xrefs

- `0x18004e620`: `method called on closed RegistryKey`
- `0x18004e599`: `class UnBCL::Array<class UnBCL::String *> *__cdecl UnBCL::RegistryKey::GetValueNames(void)`
- `0x18004e5e9`: `class UnBCL::Array<class UnBCL::String *> *__cdecl UnBCL::RegistryKey::GetValueNames(void)`
- `0x18004e634`: `class UnBCL::Array<class UnBCL::String *> *__cdecl UnBCL::RegistryKey::GetValueNames(void)`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall UnBCL::RegistryKey::GetValueNames(__int64 a1)
{
  LSTATUS InfoKeyW; // ebx
  void *v3; // rax
  __int64 v4; // rax
  char *v5; // rbx
  __int64 v6; // rbx
  DWORD i; // edi
  __int64 (__fastcall ***v8)(_QWORD); // rcx
  WCHAR *v9; // rax
  LSTATUS v10; // esi
  __int64 v11; // r15
  void (__fastcall *v12)(char *, _QWORD, __int64); // r12
  UnBCL::String *v13; // rsi
  const unsigned __int16 *v14; // rax
  __int64 v15; // rax
  UnBCL::Win32Exception *v17; // rax
  __int64 v18; // rax
  UnBCL::Win32Exception *v19; // rax
  __int64 v20; // rax
  UnBCL::ObjectDisposedException *v21; // rax
  __int64 v22; // rax
  DWORD cValues[2]; // [rsp+68h] [rbp-A0h] BYREF
  void **v24; // [rsp+70h] [rbp-98h] BYREF
  char *v25; // [rsp+78h] [rbp-90h]
  __int64 v26; // [rsp+80h] [rbp-88h]
  _BYTE v27[16]; // [rsp+88h] [rbp-80h] BYREF
  _QWORD *v28; // [rsp+98h] [rbp-70h]
  void **v29; // [rsp+A8h] [rbp-60h] BYREF
  __int64 cchValueName; // [rsp+178h] [rbp+70h] BYREF
  __int64 pExceptionObject; // [rsp+180h] [rbp+78h] BYREF
  UnBCL::Win32Exception *v32; // [rsp+188h] [rbp+80h]

  v26 = -2;
  if ( *(_DWORD *)(a1 + 8) )
  {
    v21 = (UnBCL::ObjectDisposedException *)UnBCL::Object::operator new(0x38u);
    pExceptionObject = (__int64)v21;
    if ( v21 )
      v22 = UnBCL::ObjectDisposedException::ObjectDisposedException(v21, L"method called on closed RegistryKey");
    else
      v22 = 0;
    cchValueName = AddStackTraceToException<UnBCL::InvalidOperationException>(
                     v22,
                     "class UnBCL::Array<class UnBCL::String *> *__cdecl UnBCL::RegistryKey::GetValueNames(void)");
    throw (UnBCL::ObjectDisposedException **)&cchValueName;
  }
  cValues[0] = 0;
  cValues[1] = 0;
  InfoKeyW = RegQueryInfoKeyW(**(HKEY **)(a1 + 16), 0, 0, 0, 0, 0, 0, cValues, &cValues[1], 0, 0, 0);
  if ( InfoKeyW )
  {
    v17 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    pExceptionObject = (__int64)v17;
    if ( v17 )
      v18 = UnBCL::Win32Exception::Win32Exception(v17, InfoKeyW, L"unable to query key info");
    else
      v18 = 0;
    cchValueName = AddStackTraceToException<UnBCL::InvalidOperationException>(
                     v18,
                     "class UnBCL::Array<class UnBCL::String *> *__cdecl UnBCL::RegistryKey::GetValueNames(void)");
    throw (UnBCL::Win32Exception **)&cchValueName;
  }
  v3 = UnBCL::Object::operator new(0xB0u);
  cchValueName = (__int64)v3;
  if ( v3 )
    v4 = UnBCL::Array<UnBCL::String *>::Array<UnBCL::String *>(v3, cValues[0], 0, 1);
  else
    v4 = 0;
  UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::SmartPtr<UnBCL::Array<UnBCL::String *>>(&v24, v4);
  v5 = v25;
  if ( (**(unsigned int (__fastcall ***)(char *))v25)(v25) )
  {
    UnBCL::Array<unsigned short>::Array<unsigned short>(v27, cValues[1] + 1, 0, 1);
    for ( i = 0; i < cValues[0]; ++i )
    {
      v8 = (__int64 (__fastcall ***)(_QWORD))((char *)v28 + *(int *)(v28[1] + 12LL) + 8);
      LODWORD(cchValueName) = (**v8)(v8);
      v9 = (WCHAR *)(*(__int64 (__fastcall **)(_QWORD *, _QWORD))(*v28 + 112LL))(v28, 0);
      v10 = RegEnumValueW(**(HKEY **)(a1 + 16), i, v9, (LPDWORD)&cchValueName, 0, 0, 0, 0);
      if ( v10 )
      {
        v19 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
        v32 = v19;
        if ( v19 )
          v20 = UnBCL::Win32Exception::Win32Exception(v19, v10, L"unable to retrieve value name");
        else
          v20 = 0;
        pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                             v20,
                             "class UnBCL::Array<class UnBCL::String *> *__cdecl UnBCL::RegistryKey::GetValueNames(void)");
        throw (UnBCL::Win32Exception **)&pExceptionObject;
      }
      v11 = *(int *)(*((_QWORD *)v5 + 1) + 16LL);
      v12 = *(void (__fastcall **)(char *, _QWORD, __int64))(*(_QWORD *)&v5[v11 + 8] + 32LL);
      v13 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
      pExceptionObject = (__int64)v13;
      if ( v13 )
      {
        v14 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD *, _QWORD))(*v28 + 112LL))(v28, 0);
        v15 = UnBCL::String::String(v13, v14);
      }
      else
      {
        v15 = 0;
      }
      v12(&v5[v11 + 8], i, v15);
    }
    (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v5 + 24LL))(v5, 1);
    v6 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::Steal(&v24);
    UnBCL::Array<unsigned short>::~Array<unsigned short>(&v29);
    v29 = &UnBCL::Object::`vftable';
  }
  else
  {
    v6 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::Steal(&v24);
  }
  v24 = &UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::`vftable';
  UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::SerializationStream::TypeFactoryList *>>::DeAssign(&v24);
  return v6;
}

```

## disassembly

```asm
0x18004e320  mov     rax, rsp
0x18004e323  push    rbp
0x18004e324  push    rsi
0x18004e325  push    rdi
0x18004e326  push    r12
0x18004e328  push    r13
0x18004e32a  push    r14
0x18004e32c  push    r15
0x18004e32e  lea     rbp, [rax-68h]
0x18004e332  sub     rsp, 130h
0x18004e339  mov     [rsp+160h+var_E8], 0FFFFFFFFFFFFFFFEh
0x18004e342  mov     [rax+20h], rbx
0x18004e346  mov     r14, rcx
0x18004e349  xor     r13d, r13d
0x18004e34c  cmp     [rcx+8], r13d
0x18004e350  jnz     loc_18004E60D
0x18004e356  mov     [rsp+160h+cValues], r13d
0x18004e35b  mov     [rsp+160h+cValues+4], r13d
0x18004e360  mov     rcx, [rcx+10h]
0x18004e364  mov     [rsp+160h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18004e369  mov     [rsp+160h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18004e36e  mov     [rsp+160h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x18004e373  lea     rax, [rsp+160h+cValues+4]
0x18004e378  mov     [rsp+160h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18004e37d  lea     rax, [rsp+160h+cValues]
0x18004e382  mov     [rsp+160h+lpcValues], rax; lpcValues
0x18004e387  mov     [rsp+160h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x18004e38c  mov     [rsp+160h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x18004e391  mov     [rsp+160h+lpcSubKeys], r13; lpcSubKeys
0x18004e396  xor     r9d, r9d; lpReserved
0x18004e399  xor     r8d, r8d; lpcchClass
0x18004e39c  xor     edx, edx; lpClass
0x18004e39e  mov     rcx, [rcx]; hKey
0x18004e3a1  call    cs:__imp_RegQueryInfoKeyW
0x18004e3a7  mov     ebx, eax
0x18004e3a9  test    eax, eax
0x18004e3ab  jnz     loc_18004E570
0x18004e3b1  mov     ecx, 0B0h; unsigned __int64
0x18004e3b6  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004e3bb  mov     [rbp+60h+cchValueName], rax
0x18004e3bf  lea     edi, [rbx+1]
0x18004e3c2  test    rax, rax
0x18004e3c5  jz      short loc_18004E3DB
0x18004e3c7  mov     r9d, edi
0x18004e3ca  xor     r8d, r8d
0x18004e3cd  mov     edx, [rsp+160h+cValues]
0x18004e3d1  mov     rcx, rax
0x18004e3d4  call    ??0?$Array@PEAVString@UnBCL@@@UnBCL@@QEAA@HH@Z; UnBCL::Array<UnBCL::String *>::Array<UnBCL::String *>(int,int)
0x18004e3d9  jmp     short loc_18004E3DE
0x18004e3db  mov     rax, r13
0x18004e3de  mov     rdx, rax
0x18004e3e1  lea     rcx, [rsp+160h+var_F8]
0x18004e3e6  call    ??0?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@PEAVString@UnBCL@@@1@@Z; UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::SmartPtr<UnBCL::Array<UnBCL::String *>>(UnBCL::Array<UnBCL::String *> *)
0x18004e3eb  nop
0x18004e3ec  mov     rbx, [rsp+160h+var_F0]
0x18004e3f1  mov     rax, [rbx]
0x18004e3f4  mov     rcx, rbx
0x18004e3f7  mov     rax, [rax]
0x18004e3fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e3ff  test    eax, eax
0x18004e401  jnz     short loc_18004E415
0x18004e403  lea     rcx, [rsp+160h+var_F8]
0x18004e408  call    ?Steal@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::Steal(void)
0x18004e40d  mov     rbx, rax
0x18004e410  jmp     loc_18004E53C
0x18004e415  mov     edx, [rsp+160h+cValues+4]
0x18004e419  inc     edx
0x18004e41b  mov     r9d, edi
0x18004e41e  xor     r8d, r8d
0x18004e421  lea     rcx, [rbp+60h+var_E0]
0x18004e425  call    ??0?$Array@G@UnBCL@@QEAA@HH@Z; UnBCL::Array<ushort>::Array<ushort>(int,int)
0x18004e42a  nop
0x18004e42b  mov     edi, r13d
0x18004e42e  cmp     [rsp+160h+cValues], r13d
0x18004e433  jbe     loc_18004E507
0x18004e439  mov     rdx, [rbp+60h+var_D0]
0x18004e43d  mov     rax, [rdx+8]
0x18004e441  movsxd  rcx, dword ptr [rax+0Ch]
0x18004e445  add     rdx, 8
0x18004e449  add     rcx, rdx
0x18004e44c  mov     rax, [rcx]
0x18004e44f  mov     rax, [rax]
0x18004e452  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e457  mov     dword ptr [rbp+60h+cchValueName], eax
0x18004e45a  mov     rcx, [rbp+60h+var_D0]
0x18004e45e  mov     rax, [rcx]
0x18004e461  xor     edx, edx
0x18004e463  mov     rax, [rax+70h]
0x18004e467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e46c  mov     rcx, [r14+10h]
0x18004e470  mov     [rsp+160h+lpcValues], r13; lpcbData
0x18004e475  mov     [rsp+160h+lpcbMaxClassLen], r13; lpData
0x18004e47a  mov     [rsp+160h+lpcbMaxSubKeyLen], r13; lpType
0x18004e47f  mov     [rsp+160h+lpcSubKeys], r13; lpReserved
0x18004e484  lea     r9, [rbp+60h+cchValueName]; lpcchValueName
0x18004e488  mov     r8, rax; lpValueName
0x18004e48b  mov     edx, edi; dwIndex
0x18004e48d  mov     rcx, [rcx]; hKey
0x18004e490  call    cs:__imp_RegEnumValueW
0x18004e496  mov     esi, eax
0x18004e498  test    eax, eax
0x18004e49a  jnz     loc_18004E5BD
0x18004e4a0  mov     rax, [rbx+8]
0x18004e4a4  movsxd  r15, dword ptr [rax+10h]
0x18004e4a8  mov     rax, [r15+rbx+8]
0x18004e4ad  mov     r12, [rax+20h]
0x18004e4b1  lea     ecx, [rsi+18h]; unsigned __int64
0x18004e4b4  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004e4b9  mov     rsi, rax
0x18004e4bc  mov     [rbp+60h+pExceptionObject], rax
0x18004e4c0  test    rax, rax
0x18004e4c3  jz      short loc_18004E4E4
0x18004e4c5  mov     rcx, [rbp+60h+var_D0]
0x18004e4c9  mov     rdx, [rcx]
0x18004e4cc  mov     rax, [rdx+70h]
0x18004e4d0  xor     edx, edx
0x18004e4d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e4d7  mov     rdx, rax; unsigned __int16 *
0x18004e4da  mov     rcx, rsi; this
0x18004e4dd  call    ??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18004e4e2  jmp     short loc_18004E4E7
0x18004e4e4  mov     rax, r13
0x18004e4e7  mov     r8, rax
0x18004e4ea  mov     edx, edi
0x18004e4ec  lea     rcx, [rbx+8]
0x18004e4f0  add     rcx, r15
0x18004e4f3  mov     rax, r12
0x18004e4f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e4fb  inc     edi
0x18004e4fd  cmp     edi, [rsp+160h+cValues]
0x18004e501  jb      loc_18004E439
0x18004e507  mov     rax, [rbx]
0x18004e50a  mov     edx, 1
0x18004e50f  mov     rcx, rbx
0x18004e512  mov     rax, [rax+18h]
0x18004e516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e51b  lea     rcx, [rsp+160h+var_F8]
0x18004e520  call    ?Steal@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::Steal(void)
0x18004e525  mov     rbx, rax
0x18004e528  lea     rcx, [rbp+60h+var_C0]
0x18004e52c  call    ??1?$Array@G@UnBCL@@UEAA@XZ; UnBCL::Array<ushort>::~Array<ushort>(void)
0x18004e531  lea     rax, ??_7Object@UnBCL@@6B@; const UnBCL::Object::`vftable'
0x18004e538  mov     [rbp+60h+var_C0], rax
0x18004e53c  lea     rax, ??_7?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::`vftable'
0x18004e543  mov     [rsp+160h+var_F8], rax
0x18004e548  lea     rcx, [rsp+160h+var_F8]
0x18004e54d  call    ?DeAssign@?$SmartPtr@U?$IEnumerator@PEAVTypeFactoryList@SerializationStream@UnBCL@@@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::SerializationStream::TypeFactoryList *>>::DeAssign(void)
0x18004e552  mov     rax, rbx
0x18004e555  mov     rbx, [rsp+160h+arg_18]
0x18004e55d  add     rsp, 130h
0x18004e564  pop     r15
0x18004e566  pop     r14
0x18004e568  pop     r13
0x18004e56a  pop     r12
0x18004e56c  pop     rdi
0x18004e56d  pop     rsi
0x18004e56e  pop     rbp
0x18004e56f  retn
0x18004e570  mov     ecx, 40h ; '@'; unsigned __int64
0x18004e575  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004e57a  mov     [rbp+60h+pExceptionObject], rax
0x18004e57e  test    rax, rax
0x18004e581  jz      short loc_18004E596
0x18004e583  lea     r8, aUnableToQueryK; "unable to query key info"
0x18004e58a  mov     edx, ebx; dwMessageId
0x18004e58c  mov     rcx, rax; this
0x18004e58f  call    ??0Win32Exception@UnBCL@@QEAA@KPEBG@Z; UnBCL::Win32Exception::Win32Exception(ulong,ushort const *)
0x18004e594  jmp     short loc_18004E599
0x18004e596  mov     rax, r13
0x18004e599  lea     rdx, aClassUnbclArra_6; "class UnBCL::Array<class UnBCL::String "...
0x18004e5a0  mov     rcx, rax
0x18004e5a3  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004e5a8  mov     [rbp+60h+cchValueName], rax
0x18004e5ac  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18004e5b3  lea     rcx, [rbp+60h+cchValueName]; pExceptionObject
0x18004e5b7  call    _CxxThrowException_0
0x18004e5bd  mov     ecx, 40h ; '@'; unsigned __int64
0x18004e5c2  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004e5c7  mov     [rbp+60h+arg_10], rax
0x18004e5ce  test    rax, rax
0x18004e5d1  jz      short loc_18004E5E6
0x18004e5d3  lea     r8, aUnableToRetrie_2; "unable to retrieve value name"
0x18004e5da  mov     edx, esi; dwMessageId
0x18004e5dc  mov     rcx, rax; this
0x18004e5df  call    ??0Win32Exception@UnBCL@@QEAA@KPEBG@Z; UnBCL::Win32Exception::Win32Exception(ulong,ushort const *)
0x18004e5e4  jmp     short loc_18004E5E9
0x18004e5e6  mov     rax, r13
0x18004e5e9  lea     rdx, aClassUnbclArra_6; "class UnBCL::Array<class UnBCL::String "...
0x18004e5f0  mov     rcx, rax
0x18004e5f3  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004e5f8  mov     [rbp+60h+pExceptionObject], rax
0x18004e5fc  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18004e603  lea     rcx, [rbp+60h+pExceptionObject]; pExceptionObject
0x18004e607  call    _CxxThrowException_0
0x18004e60d  mov     ecx, 38h ; '8'; unsigned __int64
0x18004e612  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004e617  mov     [rbp+60h+pExceptionObject], rax
0x18004e61b  test    rax, rax
0x18004e61e  jz      short loc_18004E631
0x18004e620  lea     rdx, aMethodCalledOn; "method called on closed RegistryKey"
0x18004e627  mov     rcx, rax; this
0x18004e62a  call    ??0ObjectDisposedException@UnBCL@@QEAA@PEBG@Z; UnBCL::ObjectDisposedException::ObjectDisposedException(ushort const *)
0x18004e62f  jmp     short loc_18004E634
0x18004e631  mov     rax, r13
0x18004e634  lea     rdx, aClassUnbclArra_6; "class UnBCL::Array<class UnBCL::String "...
0x18004e63b  mov     rcx, rax
0x18004e63e  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004e643  mov     [rbp+60h+cchValueName], rax
0x18004e647  lea     rdx, _TI5PEAVObjectDisposedException@UnBCL@@; pThrowInfo
0x18004e64e  lea     rcx, [rbp+60h+cchValueName]; pExceptionObject
0x18004e652  call    _CxxThrowException_0
```
