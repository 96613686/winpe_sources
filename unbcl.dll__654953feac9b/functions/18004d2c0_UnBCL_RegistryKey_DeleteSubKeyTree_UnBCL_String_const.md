# UnBCL::RegistryKey::DeleteSubKeyTree(UnBCL::String const *)

- ea: `0x18004d2c0`
- end: `0x18004d614`
- name: `?DeleteSubKeyTree@RegistryKey@UnBCL@@QEAAXPEBVString@2@@Z`
- size: `852`
- prototype: `void __fastcall(UnBCL::RegistryKey *__hidden this, const struct UnBCL::String *)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, registry_config`

## callers

- `0x18004d2c0`

## callees

- `0x18000225c`
- `0x180002f90`
- `0x180006b70`
- `0x1800098b0`
- `0x1800099b0`
- `0x180009e7c`
- `0x180011450`
- `0x1800360e0`
- `0x1800477d0`
- `0x180047d60`
- `0x18004c978`
- `0x18004cbf0`
- `0x18004cf14`
- `0x18004d2c0`
- `0x18004d760`
- `0x18004de80`
- `0x18004e670`
- `0x18004f0f0`
- `0x180060150`
- `0x1800641a0`
- `0x18006f010`

## string_xrefs

- `0x18004d4f6`: `method called on closed RegistryKey`
- `0x18004d4a9`: `unable to delete subkey`
- `0x18004d541`: `attempt to delete subkey tree of key opened read-only`
- `0x18004d472`: `void __cdecl UnBCL::RegistryKey::DeleteSubKeyTree(const class UnBCL::String *)`
- `0x18004d4bf`: `void __cdecl UnBCL::RegistryKey::DeleteSubKeyTree(const class UnBCL::String *)`
- `0x18004d50a`: `void __cdecl UnBCL::RegistryKey::DeleteSubKeyTree(const class UnBCL::String *)`
- `0x18004d55a`: `void __cdecl UnBCL::RegistryKey::DeleteSubKeyTree(const class UnBCL::String *)`
- `0x18004d5a5`: `void __cdecl UnBCL::RegistryKey::DeleteSubKeyTree(const class UnBCL::String *)`
- `0x18004d5f0`: `void __cdecl UnBCL::RegistryKey::DeleteSubKeyTree(const class UnBCL::String *)`
- `0x18004d5dc`: `attempt to delete "" subkey of hive`
- `0x18004d591`: `null keyname to RegistryKey#DeleteSubKeyTree`
- `0x18004d45e`: `attempt to delete nonexistent subkey tree`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall UnBCL::RegistryKey::DeleteSubKeyTree(UnBCL::RegistryKey *this, const struct UnBCL::String *a2)
{
  struct UnBCL::String *v3; // rax
  struct UnBCL::RegistryKey *v4; // rax
  __int64 SubKeyNames; // rax
  int v6; // r14d
  __int64 v7; // rsi
  __int64 v8; // rcx
  const struct UnBCL::String **v9; // rax
  DWORD v10; // ebx
  UnBCL::ArgumentException *v11; // rax
  __int64 v12; // rax
  UnBCL::Win32Exception *v13; // rax
  __int64 v14; // rax
  UnBCL::ObjectDisposedException *v15; // rax
  __int64 v16; // rax
  UnBCL::Win32Exception *v17; // rax
  __int64 v18; // rax
  UnBCL::ArgumentNullException *v19; // rax
  __int64 v20; // rax
  UnBCL::ArgumentException *v21; // rax
  __int64 v22; // rax
  void **v23; // [rsp+28h] [rbp-48h] BYREF
  UnBCL::RegistryKey *v24; // [rsp+30h] [rbp-40h]
  _QWORD v25[2]; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v26[8]; // [rsp+48h] [rbp-28h] BYREF
  __int64 v27; // [rsp+50h] [rbp-20h]
  struct UnBCL::String *v28[3]; // [rsp+58h] [rbp-18h] BYREF
  __int64 pExceptionObject; // [rsp+90h] [rbp+20h] BYREF
  UnBCL::ObjectDisposedException *v30; // [rsp+A0h] [rbp+30h]

  if ( *((_DWORD *)this + 2) )
  {
    v15 = (UnBCL::ObjectDisposedException *)UnBCL::Object::operator new(0x38u);
    v30 = v15;
    if ( v15 )
      v16 = UnBCL::ObjectDisposedException::ObjectDisposedException(v15, L"method called on closed RegistryKey");
    else
      v16 = 0;
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v16,
                         "void __cdecl UnBCL::RegistryKey::DeleteSubKeyTree(const class UnBCL::String *)");
    throw (UnBCL::ObjectDisposedException **)&pExceptionObject;
  }
  if ( !*((_DWORD *)this + 3) )
  {
    v17 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    v30 = v17;
    if ( v17 )
      v18 = UnBCL::Win32Exception::Win32Exception(v17, 5u, L"attempt to delete subkey tree of key opened read-only");
    else
      v18 = 0;
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v18,
                         "void __cdecl UnBCL::RegistryKey::DeleteSubKeyTree(const class UnBCL::String *)");
    throw (UnBCL::Win32Exception **)&pExceptionObject;
  }
  if ( !a2 )
  {
    v19 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v30 = v19;
    if ( v19 )
      v20 = UnBCL::ArgumentNullException::ArgumentNullException(v19, L"null keyname to RegistryKey#DeleteSubKeyTree");
    else
      v20 = 0;
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v20,
                         "void __cdecl UnBCL::RegistryKey::DeleteSubKeyTree(const class UnBCL::String *)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  if ( !**((_WORD **)a2 + 2) )
  {
    v21 = (UnBCL::ArgumentException *)UnBCL::Object::operator new(0x38u);
    v30 = v21;
    if ( v21 )
      v22 = UnBCL::ArgumentException::ArgumentException(v21, L"attempt to delete \"\" subkey of hive");
    else
      v22 = 0;
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v22,
                         "void __cdecl UnBCL::RegistryKey::DeleteSubKeyTree(const class UnBCL::String *)");
    throw (UnBCL::ArgumentException **)&pExceptionObject;
  }
  v3 = UnBCL::RegistryKey::FixupName(this, a2);
  UnBCL::StringPtr::StringPtr((UnBCL::StringPtr *)v26, v3);
  v4 = UnBCL::RegistryKey::OpenSubKey(this, *(struct UnBCL::String **)((char *)v28 + *(int *)(v27 + 4)), 1);
  UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(&v23, v4);
  if ( !v24 )
  {
    v11 = (UnBCL::ArgumentException *)UnBCL::Object::operator new(0x38u);
    v30 = v11;
    if ( v11 )
      v12 = UnBCL::ArgumentException::ArgumentException(v11, L"attempt to delete nonexistent subkey tree");
    else
      v12 = 0;
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v12,
                         "void __cdecl UnBCL::RegistryKey::DeleteSubKeyTree(const class UnBCL::String *)");
    throw (UnBCL::ArgumentException **)&pExceptionObject;
  }
  if ( (int)UnBCL::RegistryKey::get_SubKeyCount(v24) > 0 )
  {
    SubKeyNames = UnBCL::RegistryKey::GetSubKeyNames(v24);
    UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::SmartPtr<UnBCL::Array<UnBCL::String *>>(v25, SubKeyNames);
    v6 = 0;
    v7 = v25[1];
    while ( v6 < (**(int (__fastcall ***)(__int64))v7)(v7) )
    {
      v8 = v7 + *(int *)(*(_QWORD *)(v7 + 8) + 16LL) + 8LL;
      v9 = (const struct UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v8 + 24LL))(
                                            v8,
                                            (unsigned int)v6);
      UnBCL::RegistryKey::DeleteSubKeyTree(v24, *v9);
      ++v6;
    }
    v25[0] = &UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::`vftable';
    UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::SerializationStream::TypeFactoryList *>>::DeAssign(v25);
  }
  UnBCL::RegistryKey::Close(v24);
  UnBCL::SmartPtr<UnBCL::MultiSz>::DeAssign(&v23);
  v10 = ATL::CRegKey::DeleteSubKey(
          *((ATL::CRegKey **)this + 2),
          (*(const unsigned __int16 ***)((char *)v28 + *(int *)(v27 + 4)))[2]);
  if ( v10 )
  {
    v13 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    v30 = v13;
    if ( v13 )
      v14 = UnBCL::Win32Exception::Win32Exception(v13, v10, L"unable to delete subkey");
    else
      v14 = 0;
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v14,
                         "void __cdecl UnBCL::RegistryKey::DeleteSubKeyTree(const class UnBCL::String *)");
    throw (UnBCL::Win32Exception **)&pExceptionObject;
  }
  v23 = &UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable';
  UnBCL::SmartPtr<UnBCL::MultiSz>::DeAssign(&v23);
  v28[0] = (struct UnBCL::String *)&UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v28);
}

```

## disassembly

```asm
0x18004d2c0  mov     rax, rsp
0x18004d2c3  push    rbp
0x18004d2c4  push    r14
0x18004d2c6  push    r15
0x18004d2c8  mov     rbp, rsp
0x18004d2cb  sub     rsp, 70h
0x18004d2cf  mov     [rbp+var_50], 0FFFFFFFFFFFFFFFEh
0x18004d2d7  mov     [rax+10h], rbx
0x18004d2db  mov     [rax+20h], rsi
0x18004d2df  mov     rbx, rcx
0x18004d2e2  xor     r15d, r15d
0x18004d2e5  cmp     [rcx+8], r15d
0x18004d2e9  jnz     loc_18004D4E3
0x18004d2ef  cmp     [rcx+0Ch], r15d
0x18004d2f3  jz      loc_18004D52E
0x18004d2f9  test    rdx, rdx
0x18004d2fc  jz      loc_18004D57E
0x18004d302  mov     rax, [rdx+10h]
0x18004d306  cmp     [rax], r15w
0x18004d30a  jz      loc_18004D5C9
0x18004d310  call    ?FixupName@RegistryKey@UnBCL@@AEAAPEAVString@2@AEBV32@@Z; UnBCL::RegistryKey::FixupName(UnBCL::String const &)
0x18004d315  mov     rdx, rax; struct UnBCL::String *
0x18004d318  lea     r8d, [r15+1]
0x18004d31c  lea     rcx, [rbp+var_28]; this
0x18004d320  call    ??0StringPtr@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::StringPtr::StringPtr(UnBCL::String *)
0x18004d325  nop
0x18004d326  mov     rax, [rbp+var_20]
0x18004d32a  movsxd  rdx, dword ptr [rax+4]
0x18004d32e  lea     r8d, [r15+1]; int
0x18004d332  mov     rdx, [rbp+rdx+var_18]; struct UnBCL::String *
0x18004d337  mov     rcx, rbx; this
0x18004d33a  call    ?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@H@Z; UnBCL::RegistryKey::OpenSubKey(UnBCL::String const *,int)
0x18004d33f  mov     rdx, rax
0x18004d342  lea     rcx, [rbp+var_48]
0x18004d346  call    ??0?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@QEAA@PEAVRegistryKey@1@@Z; UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(UnBCL::RegistryKey *)
0x18004d34b  nop
0x18004d34c  cmp     [rbp+var_40], r15
0x18004d350  jz      loc_18004D44B
0x18004d356  mov     rcx, [rbp+var_40]; this
0x18004d35a  call    ?get_SubKeyCount@RegistryKey@UnBCL@@QEBAHXZ; UnBCL::RegistryKey::get_SubKeyCount(void)
0x18004d35f  test    eax, eax
0x18004d361  jle     short loc_18004D3D6
0x18004d363  mov     rcx, [rbp+var_40]
0x18004d367  call    ?GetSubKeyNames@RegistryKey@UnBCL@@QEAAPEAV?$Array@PEAVString@UnBCL@@@2@XZ; UnBCL::RegistryKey::GetSubKeyNames(void)
0x18004d36c  mov     rdx, rax
0x18004d36f  lea     rcx, [rbp+var_38]
0x18004d373  call    ??0?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@PEAVString@UnBCL@@@1@@Z; UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::SmartPtr<UnBCL::Array<UnBCL::String *>>(UnBCL::Array<UnBCL::String *> *)
0x18004d378  nop
0x18004d379  mov     r14d, r15d
0x18004d37c  mov     rsi, [rbp+var_30]
0x18004d380  mov     rax, [rsi]
0x18004d383  mov     rcx, rsi
0x18004d386  mov     rax, [rax]
0x18004d389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d38e  cmp     r14d, eax
0x18004d391  jge     short loc_18004D3C2
0x18004d393  mov     rax, [rsi+8]
0x18004d397  movsxd  rcx, dword ptr [rax+10h]
0x18004d39b  add     rcx, 8
0x18004d39f  add     rcx, rsi
0x18004d3a2  mov     rax, [rcx]
0x18004d3a5  mov     edx, r14d
0x18004d3a8  mov     rax, [rax+18h]
0x18004d3ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d3b1  mov     rdx, [rax]; struct UnBCL::String *
0x18004d3b4  mov     rcx, [rbp+var_40]; this
0x18004d3b8  call    ?DeleteSubKeyTree@RegistryKey@UnBCL@@QEAAXPEBVString@2@@Z; UnBCL::RegistryKey::DeleteSubKeyTree(UnBCL::String const *)
0x18004d3bd  inc     r14d
0x18004d3c0  jmp     short loc_18004D380
0x18004d3c2  lea     rax, ??_7?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::`vftable'
0x18004d3c9  mov     [rbp+var_38], rax
0x18004d3cd  lea     rcx, [rbp+var_38]
0x18004d3d1  call    ?DeAssign@?$SmartPtr@U?$IEnumerator@PEAVTypeFactoryList@SerializationStream@UnBCL@@@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::SerializationStream::TypeFactoryList *>>::DeAssign(void)
0x18004d3d6  mov     rcx, [rbp+var_40]; this
0x18004d3da  call    ?Close@RegistryKey@UnBCL@@QEAAXXZ; UnBCL::RegistryKey::Close(void)
0x18004d3df  lea     rcx, [rbp+var_48]
0x18004d3e3  call    ?DeAssign@?$SmartPtr@VMultiSz@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::MultiSz>::DeAssign(void)
0x18004d3e8  mov     rax, [rbp+var_20]
0x18004d3ec  movsxd  rcx, dword ptr [rax+4]
0x18004d3f0  mov     rdx, [rbp+rcx+var_18]
0x18004d3f5  mov     rdx, [rdx+10h]; unsigned __int16 *
0x18004d3f9  mov     rcx, [rbx+10h]; this
0x18004d3fd  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18004d402  mov     ebx, eax
0x18004d404  test    eax, eax
0x18004d406  jnz     loc_18004D496
0x18004d40c  lea     rax, ??_7?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable'
0x18004d413  mov     [rbp+var_48], rax
0x18004d417  lea     rcx, [rbp+var_48]
0x18004d41b  call    ?DeAssign@?$SmartPtr@VMultiSz@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::MultiSz>::DeAssign(void)
0x18004d420  nop
0x18004d421  lea     rax, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x18004d428  mov     [rbp+var_18], rax
0x18004d42c  lea     rcx, [rbp+var_18]
0x18004d430  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18004d435  lea     r11, [rsp+70h+var_s0]
0x18004d43a  mov     rbx, [r11+28h]
0x18004d43e  mov     rsi, [r11+38h]
0x18004d442  mov     rsp, r11
0x18004d445  pop     r15
0x18004d447  pop     r14
0x18004d449  pop     rbp
0x18004d44a  retn
0x18004d44b  mov     ecx, 38h ; '8'; unsigned __int64
0x18004d450  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004d455  mov     [rbp+arg_10], rax
0x18004d459  test    rax, rax
0x18004d45c  jz      short loc_18004D46F
0x18004d45e  lea     rdx, aAttemptToDelet; "attempt to delete nonexistent subkey tr"...
0x18004d465  mov     rcx, rax; this
0x18004d468  call    ??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x18004d46d  jmp     short loc_18004D472
0x18004d46f  mov     rax, r15
0x18004d472  lea     rdx, aVoidCdeclUnbcl_87; "void __cdecl UnBCL::RegistryKey::Delete"...
0x18004d479  mov     rcx, rax
0x18004d47c  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004d481  mov     [rbp+pExceptionObject], rax
0x18004d485  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x18004d48c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18004d490  call    _CxxThrowException_0
0x18004d496  mov     ecx, 40h ; '@'; unsigned __int64
0x18004d49b  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004d4a0  mov     [rbp+arg_10], rax
0x18004d4a4  test    rax, rax
0x18004d4a7  jz      short loc_18004D4BC
0x18004d4a9  lea     r8, aUnableToDelete; "unable to delete subkey"
0x18004d4b0  mov     edx, ebx; dwMessageId
0x18004d4b2  mov     rcx, rax; this
0x18004d4b5  call    ??0Win32Exception@UnBCL@@QEAA@KPEBG@Z; UnBCL::Win32Exception::Win32Exception(ulong,ushort const *)
0x18004d4ba  jmp     short loc_18004D4BF
0x18004d4bc  mov     rax, r15
0x18004d4bf  lea     rdx, aVoidCdeclUnbcl_87; "void __cdecl UnBCL::RegistryKey::Delete"...
0x18004d4c6  mov     rcx, rax
0x18004d4c9  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004d4ce  mov     [rbp+pExceptionObject], rax
0x18004d4d2  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18004d4d9  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18004d4dd  call    _CxxThrowException_0
0x18004d4e3  mov     ecx, 38h ; '8'; unsigned __int64
0x18004d4e8  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004d4ed  mov     [rbp+arg_10], rax
0x18004d4f1  test    rax, rax
0x18004d4f4  jz      short loc_18004D507
0x18004d4f6  lea     rdx, aMethodCalledOn; "method called on closed RegistryKey"
0x18004d4fd  mov     rcx, rax; this
0x18004d500  call    ??0ObjectDisposedException@UnBCL@@QEAA@PEBG@Z; UnBCL::ObjectDisposedException::ObjectDisposedException(ushort const *)
0x18004d505  jmp     short loc_18004D50A
0x18004d507  mov     rax, r15
0x18004d50a  lea     rdx, aVoidCdeclUnbcl_87; "void __cdecl UnBCL::RegistryKey::Delete"...
0x18004d511  mov     rcx, rax
0x18004d514  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004d519  mov     [rbp+pExceptionObject], rax
0x18004d51d  lea     rdx, _TI5PEAVObjectDisposedException@UnBCL@@; pThrowInfo
0x18004d524  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18004d528  call    _CxxThrowException_0
0x18004d52e  mov     ecx, 40h ; '@'; unsigned __int64
0x18004d533  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004d538  mov     [rbp+arg_10], rax
0x18004d53c  test    rax, rax
0x18004d53f  jz      short loc_18004D557
0x18004d541  lea     r8, aAttemptToDelet_5; "attempt to delete subkey tree of key op"...
0x18004d548  mov     edx, 5; dwMessageId
0x18004d54d  mov     rcx, rax; this
0x18004d550  call    ??0Win32Exception@UnBCL@@QEAA@KPEBG@Z; UnBCL::Win32Exception::Win32Exception(ulong,ushort const *)
0x18004d555  jmp     short loc_18004D55A
0x18004d557  mov     rax, r15
0x18004d55a  lea     rdx, aVoidCdeclUnbcl_87; "void __cdecl UnBCL::RegistryKey::Delete"...
0x18004d561  mov     rcx, rax
0x18004d564  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004d569  mov     [rbp+pExceptionObject], rax
0x18004d56d  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18004d574  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18004d578  call    _CxxThrowException_0
0x18004d57e  mov     ecx, 38h ; '8'; unsigned __int64
0x18004d583  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004d588  mov     [rbp+arg_10], rax
0x18004d58c  test    rax, rax
0x18004d58f  jz      short loc_18004D5A2
0x18004d591  lea     rdx, aNullKeynameToR; "null keyname to RegistryKey#DeleteSubKe"...
0x18004d598  mov     rcx, rax; this
0x18004d59b  call    ??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x18004d5a0  jmp     short loc_18004D5A5
0x18004d5a2  mov     rax, r15
0x18004d5a5  lea     rdx, aVoidCdeclUnbcl_87; "void __cdecl UnBCL::RegistryKey::Delete"...
0x18004d5ac  mov     rcx, rax
0x18004d5af  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004d5b4  mov     [rbp+pExceptionObject], rax
0x18004d5b8  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x18004d5bf  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18004d5c3  call    _CxxThrowException_0
0x18004d5c9  mov     ecx, 38h ; '8'; unsigned __int64
0x18004d5ce  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004d5d3  mov     [rbp+arg_10], rax
0x18004d5d7  test    rax, rax
0x18004d5da  jz      short loc_18004D5ED
0x18004d5dc  lea     rdx, aAttemptToDelet_0; "attempt to delete \"\" subkey of hive"
0x18004d5e3  mov     rcx, rax; this
0x18004d5e6  call    ??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x18004d5eb  jmp     short loc_18004D5F0
0x18004d5ed  mov     rax, r15
0x18004d5f0  lea     rdx, aVoidCdeclUnbcl_87; "void __cdecl UnBCL::RegistryKey::Delete"...
0x18004d5f7  mov     rcx, rax
0x18004d5fa  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004d5ff  mov     [rbp+pExceptionObject], rax
0x18004d603  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x18004d60a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18004d60e  call    _CxxThrowException_0
```
