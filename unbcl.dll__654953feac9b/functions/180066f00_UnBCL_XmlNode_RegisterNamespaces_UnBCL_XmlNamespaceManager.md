# UnBCL::XmlNode::RegisterNamespaces(UnBCL::XmlNamespaceManager *)

- ea: `0x180066f00`
- end: `0x1800672b8`
- name: `?RegisterNamespaces@XmlNode@UnBCL@@AEAAXPEAVXmlNamespaceManager@2@@Z`
- size: `952`
- prototype: `void __fastcall(UnBCL::XmlNode *__hidden this, struct UnBCL::XmlNamespaceManager *)`
- caller_count: `2`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180067630`
- `0x180067790`

## callees

- `0x18000225c`
- `0x180002f50`
- `0x180002f90`
- `0x1800061e0`
- `0x180006b70`
- `0x180009e7c`
- `0x180011570`
- `0x180034588`
- `0x1800475e0`
- `0x1800477d0`
- `0x18005c180`
- `0x18005f750`
- `0x18005f820`
- `0x18005f990`
- `0x18005fde0`
- `0x180066d50`
- `0x180066f00`
- `0x180068060`
- `0x180068fd7`
- `0x18006f010`

## string_xrefs

- `0x18006728e`: `void __cdecl UnBCL::XmlNode::RegisterNamespaces(class UnBCL::XmlNamespaceManager *)`
- `0x1800670f8`: `xmlns:%s="%s"`
- `0x18006716d`: `xmlns="%s"`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall UnBCL::XmlNode::RegisterNamespaces(UnBCL::XmlNode *this, struct UnBCL::XmlNamespaceManager *a2)
{
  UnBCL::XmlDocument *OwnerDocument; // rsi
  __int64 (__fastcall ***v5)(_QWORD); // rcx
  __int64 v6; // rax
  __int64 v7; // rdi
  __int64 (__fastcall ***v8)(_QWORD); // rdx
  const unsigned __int16 *v9; // rcx
  int v10; // ebx
  __int64 (__fastcall *v11)(__int64, char *); // rax
  __int64 v12; // rdx
  __int64 v13; // rbx
  __int64 (__fastcall ***v14)(_QWORD); // rdx
  __int64 v15; // rax
  struct UnBCL::String *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rax
  struct UnBCL::String *v19; // rax
  struct UnBCL::String *v20; // rax
  UnBCL::NotSupportedException *v21; // rax
  __int64 v22; // rax
  void **v23; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v24; // [rsp+40h] [rbp-C8h]
  void **v25; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v26; // [rsp+50h] [rbp-B8h]
  void **v27; // [rsp+58h] [rbp-B0h] BYREF
  struct UnBCL::String *v28; // [rsp+60h] [rbp-A8h]
  _QWORD v29[2]; // [rsp+68h] [rbp-A0h] BYREF
  _BYTE v30[16]; // [rsp+78h] [rbp-90h] BYREF
  __int64 v31; // [rsp+88h] [rbp-80h]
  __int64 v32; // [rsp+90h] [rbp-78h]
  char v33[48]; // [rsp+98h] [rbp-70h] BYREF
  void **v34; // [rsp+C8h] [rbp-40h] BYREF
  char v35[48]; // [rsp+D8h] [rbp-30h] BYREF
  void **v36; // [rsp+108h] [rbp+0h] BYREF
  char v37[48]; // [rsp+118h] [rbp+10h] BYREF
  void **v38; // [rsp+148h] [rbp+40h] BYREF
  char v39[48]; // [rsp+158h] [rbp+50h] BYREF
  void **v40; // [rsp+188h] [rbp+80h] BYREF
  __int64 pExceptionObject; // [rsp+1D8h] [rbp+D0h] BYREF
  UnBCL::NotSupportedException *v42; // [rsp+1E0h] [rbp+D8h]

  v32 = -2;
  v25 = &UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *>>>::`vftable';
  v26 = 0;
  UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::SerializationStream::TypeFactoryList *>>::DeAssign(&v25);
  v26 = 0;
  OwnerDocument = UnBCL::XmlNode::get_OwnerDocument(this);
  if ( !OwnerDocument )
  {
    OwnerDocument = (UnBCL::XmlDocument *)_RTDynamicCast_0(
                                            this,
                                            0,
                                            &UnBCL::XmlNode `RTTI Type Descriptor',
                                            &UnBCL::XmlDocument `RTTI Type Descriptor',
                                            0);
    if ( !OwnerDocument )
    {
      v21 = (UnBCL::NotSupportedException *)UnBCL::Object::operator new(0x38u);
      v42 = v21;
      if ( v21 )
        v22 = UnBCL::NotSupportedException::NotSupportedException(v21);
      else
        v22 = 0;
      pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                           v22,
                           "void __cdecl UnBCL::XmlNode::RegisterNamespaces(class UnBCL::XmlNamespaceManager *)");
      throw (UnBCL::NotSupportedException **)&pExceptionObject;
    }
  }
  v5 = (__int64 (__fastcall ***)(_QWORD))(*((_QWORD *)a2 + 2)
                                        + 8LL
                                        + *(int *)(*(_QWORD *)(*((_QWORD *)a2 + 2) + 8LL) + 8LL));
  v6 = (**v5)(v5);
  v7 = v6;
  v23 = &UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *>>>::`vftable';
  v24 = 0;
  if ( v6 )
    _InterlockedIncrement((volatile signed __int32 *)(*(int *)(*(_QWORD *)(v6 + 8) + 4LL) + v6 + 16));
  UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::SerializationStream::TypeFactoryList *>>::DeAssign(&v23);
  v24 = v7;
  if ( v7 )
    _InterlockedIncrement((volatile signed __int32 *)(*(int *)(*(_QWORD *)(v7 + 8) + 4LL) + v7 + 16));
  UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::SerializationStream::TypeFactoryList *>>::DeAssign(&v25);
  v26 = v7;
  v23 = &UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *>>>::`vftable';
  UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::SerializationStream::TypeFactoryList *>>::DeAssign(&v23);
  UnBCL::StringBuilder::StringBuilder((UnBCL::StringBuilder *)v30);
  while ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7) )
  {
    v23 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
    v24 = 0;
    v8 = (__int64 (__fastcall ***)(_QWORD))(**(__int64 (__fastcall ***)(__int64, char *))v7)(v7, v33);
    v9 = *(const unsigned __int16 **)((**v8)(v8) + 16);
    if ( v9 == &qword_180089560 )
      goto LABEL_10;
    if ( v9 )
    {
      if ( !*v9 )
      {
LABEL_10:
        v10 = 0;
        goto LABEL_15;
      }
      v10 = 1;
    }
    else
    {
      v10 = -1;
    }
LABEL_15:
    UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *>::~DictionaryEntry<UnBCL::String *,UnBCL::String *>(&v34);
    v34 = &UnBCL::Object::`vftable';
    v11 = **(__int64 (__fastcall ***)(__int64, char *))v7;
    if ( v10 )
    {
      v12 = v11(v7, v37);
      v13 = *(_QWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12) + 16);
      v14 = (__int64 (__fastcall ***)(_QWORD))(**(__int64 (__fastcall ***)(__int64, char *))v7)(v7, v35);
      v15 = (**v14)(v14);
      v16 = UnBCL::String::Format(L"xmlns:%s=\"%s\"", *(_QWORD *)(v15 + 16), v13);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v29, v16);
      UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(&v23, v29[1]);
      v29[0] = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
      UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v29);
      UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *>::~DictionaryEntry<UnBCL::String *,UnBCL::String *>(&v36);
      v36 = &UnBCL::Object::`vftable';
      UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *>::~DictionaryEntry<UnBCL::String *,UnBCL::String *>(&v38);
      v38 = &UnBCL::Object::`vftable';
    }
    else
    {
      v17 = v11(v7, v39);
      v18 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      v19 = UnBCL::String::Format(L"xmlns=\"%s\"", *(_QWORD *)(v18 + 16));
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v27, v19);
      UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(&v23, v28);
      v27 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
      UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v27);
      UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *>::~DictionaryEntry<UnBCL::String *,UnBCL::String *>(&v40);
      v40 = &UnBCL::Object::`vftable';
    }
    UnBCL::StringBuilder::Append((UnBCL::StringBuilder *)v30, *(const unsigned __int16 **)(v24 + 16));
    ATL::CSimpleStringT<unsigned short,0>::Append(v31, L" ", 1);
    v23 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v23);
  }
  v20 = UnBCL::StringBuilder::ToString((UnBCL::StringBuilder *)v30);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v27, v20);
  UnBCL::XmlDocument::RegisterNamespaces(OwnerDocument, v28);
  v27 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v27);
  UnBCL::StringBuilder::~StringBuilder((UnBCL::StringBuilder *)v30);
  v25 = &UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *>>>::`vftable';
  UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::SerializationStream::TypeFactoryList *>>::DeAssign(&v25);
}

```

## disassembly

```asm
0x180066f00  mov     rax, rsp
0x180066f03  push    rbp
0x180066f04  push    rdi
0x180066f05  push    r12
0x180066f07  push    r13
0x180066f09  push    r14
0x180066f0b  lea     rbp, [rax-0B8h]
0x180066f12  sub     rsp, 190h
0x180066f19  mov     [rbp+0B0h+var_128], 0FFFFFFFFFFFFFFFEh
0x180066f21  mov     [rax+8], rbx
0x180066f25  mov     [rax+10h], rsi
0x180066f29  mov     rdi, rdx
0x180066f2c  mov     rbx, rcx
0x180066f2f  lea     r12, ??_7?$SmartPtr@U?$IEnumerator@V?$DictionaryEntry@PEAVString@UnBCL@@PEAV12@@UnBCL@@@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *>>>::`vftable'
0x180066f36  mov     [rsp+1B0h+var_170], r12
0x180066f3b  xor     r14d, r14d
0x180066f3e  mov     [rsp+1B0h+var_168], r14
0x180066f43  lea     rcx, [rsp+1B0h+var_170]
0x180066f48  call    ?DeAssign@?$SmartPtr@U?$IEnumerator@PEAVTypeFactoryList@SerializationStream@UnBCL@@@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::SerializationStream::TypeFactoryList *>>::DeAssign(void)
0x180066f4d  mov     [rsp+1B0h+var_168], r14
0x180066f52  mov     rcx, rbx; this
0x180066f55  call    ?get_OwnerDocument@XmlNode@UnBCL@@QEAAPEAVXmlDocument@2@XZ; UnBCL::XmlNode::get_OwnerDocument(void)
0x180066f5a  mov     rsi, rax
0x180066f5d  test    rax, rax
0x180066f60  jnz     short loc_180066F8B
0x180066f62  mov     [rsp+1B0h+var_190], r14d
0x180066f67  lea     r9, ??_R0?AVXmlDocument@UnBCL@@@8; UnBCL::XmlDocument `RTTI Type Descriptor'
0x180066f6e  lea     r8, ??_R0?AVXmlNode@UnBCL@@@8; UnBCL::XmlNode `RTTI Type Descriptor'
0x180066f75  xor     edx, edx
0x180066f77  mov     rcx, rbx
0x180066f7a  call    __RTDynamicCast_0
0x180066f7f  mov     rsi, rax
0x180066f82  test    rax, rax
0x180066f85  jz      loc_18006726B
0x180066f8b  mov     rdx, [rdi+10h]
0x180066f8f  mov     rax, [rdx+8]
0x180066f93  movsxd  rcx, dword ptr [rax+8]
0x180066f97  add     rdx, 8
0x180066f9b  add     rcx, rdx
0x180066f9e  mov     rax, [rcx]
0x180066fa1  mov     rax, [rax]
0x180066fa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066fa9  mov     rdi, rax
0x180066fac  mov     [rsp+1B0h+var_180], r12
0x180066fb1  mov     [rsp+1B0h+var_178], r14
0x180066fb6  test    rax, rax
0x180066fb9  jz      short loc_180066FC8
0x180066fbb  mov     rcx, [rax+8]
0x180066fbf  movsxd  rdx, dword ptr [rcx+4]
0x180066fc3  lock inc dword ptr [rdx+rax+10h]
0x180066fc8  lea     rcx, [rsp+1B0h+var_180]
0x180066fcd  call    ?DeAssign@?$SmartPtr@U?$IEnumerator@PEAVTypeFactoryList@SerializationStream@UnBCL@@@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::SerializationStream::TypeFactoryList *>>::DeAssign(void)
0x180066fd2  mov     [rsp+1B0h+var_178], rdi
0x180066fd7  test    rdi, rdi
0x180066fda  jz      short loc_180066FE9
0x180066fdc  mov     rax, [rdi+8]
0x180066fe0  movsxd  rcx, dword ptr [rax+4]
0x180066fe4  lock inc dword ptr [rcx+rdi+10h]
0x180066fe9  lea     rcx, [rsp+1B0h+var_170]
0x180066fee  call    ?DeAssign@?$SmartPtr@U?$IEnumerator@PEAVTypeFactoryList@SerializationStream@UnBCL@@@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::SerializationStream::TypeFactoryList *>>::DeAssign(void)
0x180066ff3  mov     [rsp+1B0h+var_168], rdi
0x180066ff8  mov     [rsp+1B0h+var_180], r12
0x180066ffd  lea     rcx, [rsp+1B0h+var_180]
0x180067002  call    ?DeAssign@?$SmartPtr@U?$IEnumerator@PEAVTypeFactoryList@SerializationStream@UnBCL@@@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::SerializationStream::TypeFactoryList *>>::DeAssign(void)
0x180067007  lea     rcx, [rsp+1B0h+var_140]; this
0x18006700c  call    ??0StringBuilder@UnBCL@@QEAA@XZ; UnBCL::StringBuilder::StringBuilder(void)
0x180067011  nop
0x180067012  lea     r13, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x180067019  lea     r12, ??_7Object@UnBCL@@6B@; const UnBCL::Object::`vftable'
0x180067020  mov     rbx, rdi
0x180067023  mov     rax, [rbx]
0x180067026  mov     rcx, rbx
0x180067029  mov     rax, [rax+8]
0x18006702d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067032  test    eax, eax
0x180067034  jz      loc_1800671F8
0x18006703a  mov     [rsp+1B0h+var_180], r13
0x18006703f  mov     [rsp+1B0h+var_178], r14
0x180067044  mov     rax, [rbx]
0x180067047  lea     rdx, [rbp+0B0h+var_120]
0x18006704b  mov     rcx, rbx
0x18006704e  mov     rax, [rax]
0x180067051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067056  mov     rdx, rax
0x180067059  mov     rcx, [rax]
0x18006705c  mov     rax, [rcx]
0x18006705f  mov     rcx, rdx
0x180067062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067067  mov     rcx, [rax+10h]
0x18006706b  lea     rax, qword_180089560
0x180067072  cmp     rcx, rax
0x180067075  jnz     short loc_18006707C
0x180067077  mov     ebx, r14d
0x18006707a  jmp     short loc_180067091
0x18006707c  test    rcx, rcx
0x18006707f  jnz     short loc_180067086
0x180067081  or      ebx, 0FFFFFFFFh
0x180067084  jmp     short loc_180067091
0x180067086  cmp     [rcx], r14w
0x18006708a  jz      short loc_180067077
0x18006708c  sbb     ebx, ebx
0x18006708e  or      ebx, 1
0x180067091  lea     rcx, [rbp+0B0h+var_F0]
0x180067095  call    ??1?$DictionaryEntry@PEAVString@UnBCL@@PEAV12@@UnBCL@@UEAA@XZ; UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *>::~DictionaryEntry<UnBCL::String *,UnBCL::String *>(void)
0x18006709a  mov     [rbp+0B0h+var_F0], r12
0x18006709e  mov     rax, [rdi]
0x1800670a1  mov     rcx, rdi
0x1800670a4  mov     rax, [rax]
0x1800670a7  test    ebx, ebx
0x1800670a9  jz      loc_18006714E
0x1800670af  lea     rdx, [rbp+0B0h+var_A0]
0x1800670b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800670b8  mov     rdx, rax
0x1800670bb  mov     rcx, [rax]
0x1800670be  mov     rax, [rcx+10h]
0x1800670c2  mov     rcx, rdx
0x1800670c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800670ca  mov     rbx, [rax+10h]
0x1800670ce  mov     rax, [rdi]
0x1800670d1  lea     rdx, [rbp+0B0h+var_E0]
0x1800670d5  mov     rcx, rdi
0x1800670d8  mov     rax, [rax]
0x1800670db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800670e0  mov     rdx, rax
0x1800670e3  mov     rcx, [rax]
0x1800670e6  mov     rax, [rcx]
0x1800670e9  mov     rcx, rdx
0x1800670ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800670f1  mov     r8, rbx
0x1800670f4  mov     rdx, [rax+10h]
0x1800670f8  lea     rcx, aXmlnsSS; "xmlns:%s=\"%s\""
0x1800670ff  call    ?Format@String@UnBCL@@SAPEAV12@PEBGZZ; UnBCL::String::Format(ushort const *,...)
0x180067104  mov     rdx, rax
0x180067107  lea     rcx, [rsp+1B0h+var_150]
0x18006710c  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180067111  nop
0x180067112  mov     rdx, qword ptr [rsp+1B0h+var_148]
0x180067117  lea     rcx, [rsp+1B0h+var_180]
0x18006711c  call    ?Assign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXPEAVXmlNamespaceManager@2@@Z; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(UnBCL::XmlNamespaceManager *)
0x180067121  nop
0x180067122  mov     [rsp+1B0h+var_150], r13
0x180067127  lea     rcx, [rsp+1B0h+var_150]
0x18006712c  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x180067131  nop
0x180067132  lea     rcx, [rbp+0B0h+var_B0]
0x180067136  call    ??1?$DictionaryEntry@PEAVString@UnBCL@@PEAV12@@UnBCL@@UEAA@XZ; UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *>::~DictionaryEntry<UnBCL::String *,UnBCL::String *>(void)
0x18006713b  mov     [rbp+0B0h+var_B0], r12
0x18006713f  lea     rcx, [rbp+0B0h+var_70]
0x180067143  call    ??1?$DictionaryEntry@PEAVString@UnBCL@@PEAV12@@UnBCL@@UEAA@XZ; UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *>::~DictionaryEntry<UnBCL::String *,UnBCL::String *>(void)
0x180067148  mov     [rbp+0B0h+var_70], r12
0x18006714c  jmp     short loc_1800671BA
0x18006714e  lea     rdx, [rbp+0B0h+var_60]
0x180067152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067157  mov     rdx, rax
0x18006715a  mov     rcx, [rax]
0x18006715d  mov     rax, [rcx+10h]
0x180067161  mov     rcx, rdx
0x180067164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067169  mov     rdx, [rax+10h]
0x18006716d  lea     rcx, aXmlnsS; "xmlns=\"%s\""
0x180067174  call    ?Format@String@UnBCL@@SAPEAV12@PEBGZZ; UnBCL::String::Format(ushort const *,...)
0x180067179  mov     rdx, rax
0x18006717c  lea     rcx, [rsp+1B0h+var_160]
0x180067181  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180067186  nop
0x180067187  mov     rdx, [rsp+1B0h+var_158]
0x18006718c  lea     rcx, [rsp+1B0h+var_180]
0x180067191  call    ?Assign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXPEAVXmlNamespaceManager@2@@Z; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(UnBCL::XmlNamespaceManager *)
0x180067196  nop
0x180067197  mov     [rsp+1B0h+var_160], r13
0x18006719c  lea     rcx, [rsp+1B0h+var_160]
0x1800671a1  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x1800671a6  nop
0x1800671a7  lea     rcx, [rbp+0B0h+var_30]
0x1800671ae  call    ??1?$DictionaryEntry@PEAVString@UnBCL@@PEAV12@@UnBCL@@UEAA@XZ; UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *>::~DictionaryEntry<UnBCL::String *,UnBCL::String *>(void)
0x1800671b3  mov     [rbp+0B0h+var_30], r12
0x1800671ba  mov     rdx, [rsp+1B0h+var_178]
0x1800671bf  mov     rdx, [rdx+10h]; unsigned __int16 *
0x1800671c3  lea     rcx, [rsp+1B0h+var_140]; this
0x1800671c8  call    ?Append@StringBuilder@UnBCL@@QEAAPEAV12@PEBG@Z; UnBCL::StringBuilder::Append(ushort const *)
0x1800671cd  mov     r8d, 1
0x1800671d3  lea     rdx, asc_180085DF8; " "
0x1800671da  mov     rcx, [rbp+0B0h+var_130]
0x1800671de  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x1800671e3  nop
0x1800671e4  mov     [rsp+1B0h+var_180], r13
0x1800671e9  lea     rcx, [rsp+1B0h+var_180]
0x1800671ee  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x1800671f3  jmp     loc_180067020
0x1800671f8  lea     rcx, [rsp+1B0h+var_140]; this
0x1800671fd  call    ?ToString@StringBuilder@UnBCL@@UEBAPEAVString@2@XZ; UnBCL::StringBuilder::ToString(void)
0x180067202  mov     rdx, rax
0x180067205  lea     rcx, [rsp+1B0h+var_160]
0x18006720a  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18006720f  nop
0x180067210  mov     rdx, [rsp+1B0h+var_158]; struct UnBCL::String *
0x180067215  mov     rcx, rsi; this
0x180067218  call    ?RegisterNamespaces@XmlDocument@UnBCL@@QEAAXPEAVString@2@@Z; UnBCL::XmlDocument::RegisterNamespaces(UnBCL::String *)
0x18006721d  nop
0x18006721e  mov     [rsp+1B0h+var_160], r13
0x180067223  lea     rcx, [rsp+1B0h+var_160]
0x180067228  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18006722d  nop
0x18006722e  lea     rcx, [rsp+1B0h+var_140]; this
0x180067233  call    ??1StringBuilder@UnBCL@@UEAA@XZ; UnBCL::StringBuilder::~StringBuilder(void)
0x180067238  nop
0x180067239  lea     r12, ??_7?$SmartPtr@U?$IEnumerator@V?$DictionaryEntry@PEAVString@UnBCL@@PEAV12@@UnBCL@@@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *>>>::`vftable'
0x180067240  mov     [rsp+1B0h+var_170], r12
0x180067245  lea     rcx, [rsp+1B0h+var_170]
0x18006724a  call    ?DeAssign@?$SmartPtr@U?$IEnumerator@PEAVTypeFactoryList@SerializationStream@UnBCL@@@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::SerializationStream::TypeFactoryList *>>::DeAssign(void)
0x18006724f  lea     r11, [rsp+1B0h+var_20]
0x180067257  mov     rbx, [r11+30h]
0x18006725b  mov     rsi, [r11+38h]
0x18006725f  mov     rsp, r11
0x180067262  pop     r14
0x180067264  pop     r13
0x180067266  pop     r12
0x180067268  pop     rdi
0x180067269  pop     rbp
0x18006726a  retn
0x18006726b  mov     ecx, 38h ; '8'; unsigned __int64
0x180067270  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180067275  mov     [rbp+0B0h+arg_18], rax
0x18006727c  test    rax, rax
0x18006727f  jz      short loc_18006728B
0x180067281  mov     rcx, rax; this
0x180067284  call    ??0NotSupportedException@UnBCL@@QEAA@XZ; UnBCL::NotSupportedException::NotSupportedException(void)
0x180067289  jmp     short loc_18006728E
0x18006728b  mov     rax, r14
0x18006728e  lea     rdx, aVoidCdeclUnbcl_165; "void __cdecl UnBCL::XmlNode::RegisterNa"...
0x180067295  mov     rcx, rax
0x180067298  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18006729d  mov     [rbp+0B0h+pExceptionObject], rax
0x1800672a4  lea     rdx, _TI5PEAVNotSupportedException@UnBCL@@; pThrowInfo
0x1800672ab  lea     rcx, [rbp+0B0h+pExceptionObject]; pExceptionObject
0x1800672b2  call    _CxxThrowException_0
```
