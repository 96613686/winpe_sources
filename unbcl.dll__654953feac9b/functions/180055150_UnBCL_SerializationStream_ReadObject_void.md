# UnBCL::SerializationStream::ReadObject(void)

- ea: `0x180055150`
- end: `0x1800554f5`
- name: `?ReadObject@SerializationStream@UnBCL@@IEAAPEAUISerializable@2@XZ`
- size: `933`
- prototype: `struct UnBCL::ISerializable *__fastcall(UnBCL::SerializationStream *__hidden this)`
- caller_count: `4`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180051c80`
- `0x180051df0`
- `0x180051fd0`
- `0x180055730`

## callees

- `0x18000225c`
- `0x180002b60`
- `0x180002ca0`
- `0x180002f50`
- `0x180002f90`
- `0x180003dd0`
- `0x180009e7c`
- `0x180011570`
- `0x180012480`
- `0x18001a700`
- `0x180039a80`
- `0x1800477d0`
- `0x18004ffa0`
- `0x1800500d8`
- `0x1800515d0`
- `0x180055150`
- `0x180055500`
- `0x180057920`
- `0x18005b5d0`
- `0x18005c180`
- `0x180068fd7`
- `0x18006f010`

## string_xrefs

- `0x180055456`: `Deserialized non ISerializable object: %s`
- `0x180055402`: `struct UnBCL::ISerializable *__cdecl UnBCL::SerializationStream::ReadObject(void)`
- `0x1800554d1`: `struct UnBCL::ISerializable *__cdecl UnBCL::SerializationStream::ReadObject(void)`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
struct UnBCL::ISerializable *__fastcall UnBCL::SerializationStream::ReadObject(UnBCL::SerializationStream *this)
{
  __int64 v2; // rax
  __int64 v3; // r15
  UnBCL::String *v4; // rax
  UnBCL::SerializationId *v5; // rax
  int v6; // r8d
  struct UnBCL::String *v7; // rdx
  __int64 v8; // rcx
  __int64 *v9; // rax
  __int64 v10; // rax
  __int64 (__fastcall ***v11)(_QWORD); // rcx
  _QWORD *v12; // rsi
  __int64 v13; // r8
  __int64 v14; // rax
  char *v15; // rdx
  __int64 v16; // rbx
  struct UnBCL::ISerializable *result; // rax
  struct UnBCL::Object *v18; // rbx
  UnBCL::SystemInfo *v19; // rax
  unsigned int IsVM; // ebx
  UnBCL::SerializationId *v21; // rax
  const unsigned __int16 *TypeName; // rax
  struct UnBCL::String *v23; // rax
  UnBCL::SerializationException *v24; // rax
  UnBCL::SerializationException *v25; // rbx
  __int64 v26; // rax
  const unsigned __int16 *InnerList; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  struct UnBCL::String *v31; // rax
  UnBCL::SerializationException *v32; // rax
  UnBCL::SerializationException *v33; // rbx
  __int64 v34; // rax
  const unsigned __int16 *v35; // rax
  void **v36; // [rsp+38h] [rbp-28h] BYREF
  struct UnBCL::String *v37; // [rsp+40h] [rbp-20h]
  void **v38; // [rsp+48h] [rbp-18h] BYREF
  __int64 v39; // [rsp+50h] [rbp-10h]
  struct UnBCL::Object *pExceptionObject; // [rsp+98h] [rbp+38h] BYREF
  UnBCL::String *v41; // [rsp+A0h] [rbp+40h]

  pExceptionObject = 0;
  if ( (unsigned int)UnBCL::SerializationStream::ReadObjectHeader(this, &pExceptionObject) )
  {
    v2 = *((_QWORD *)this + 3);
    if ( v2 )
    {
      _InterlockedDecrement((volatile signed __int32 *)(v2 + 8));
      v3 = *((_QWORD *)this + 3);
      *((_QWORD *)this + 3) = 0;
    }
    else
    {
      v3 = 0;
    }
    v4 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
    v41 = v4;
    if ( v4 )
      v4 = (UnBCL::String *)UnBCL::String::String(v4, this);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v36, v4);
    LODWORD(pExceptionObject) = 0;
    UnBCL::SerializationStream::ReadPrimitive<int>(this, &pExceptionObject);
    v5 = (UnBCL::SerializationId *)UnBCL::Object::operator new(0x20u);
    v41 = v5;
    if ( v5 )
    {
      v6 = (int)pExceptionObject;
      v7 = v37;
      if ( v37 )
      {
        _InterlockedDecrement((volatile signed __int32 *)v37 + 2);
        v37 = 0;
      }
      v5 = (UnBCL::SerializationId *)UnBCL::SerializationId::SerializationId(v5, v7, v6);
    }
    UnBCL::SmartPtr<UnBCL::SerializationId>::SmartPtr<UnBCL::SerializationId>(&v38, v5);
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign((char *)this + 16, v39);
    v38 = &UnBCL::SmartPtr<UnBCL::SerializationId>::`vftable';
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v38);
    v36 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v36);
    v8 = UnBCL::SerializationStream::s_Registered
       + 8
       + *(int *)(*(_QWORD *)(UnBCL::SerializationStream::s_Registered + 8) + 16LL);
    v9 = (__int64 *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v8 + 16LL))(v8, *((_QWORD *)this + 3));
    if ( !v9 || (v10 = *v9) == 0 || (v11 = *(__int64 (__fastcall ****)(_QWORD))(v10 + 8)) == 0 )
    {
      v19 = (UnBCL::SystemInfo *)UnBCL::SmartPtr<UnBCL::Decoder>::operator->((char *)this + 16);
      IsVM = UnBCL::SystemInfo::get_IsVM(v19);
      v21 = (UnBCL::SerializationId *)UnBCL::SmartPtr<UnBCL::Decoder>::operator->((char *)this + 16);
      TypeName = UnBCL::SerializationId::get_TypeName(v21);
      v23 = UnBCL::String::Format(L"saw unrecognized type/version pair '%s - %d'", TypeName, IsVM);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v38, v23);
      v24 = (UnBCL::SerializationException *)UnBCL::Object::operator new(0x38u);
      v25 = v24;
      v41 = v24;
      if ( v24 )
      {
        v26 = UnBCL::SmartPtr<UnBCL::Decoder>::operator->(&v38);
        InnerList = (const unsigned __int16 *)UnBCL::CollectionBase<UnBCL::Object *>::get_InnerList(v26);
        v24 = (UnBCL::SerializationException *)UnBCL::SerializationException::SerializationException(v25, InnerList);
      }
      pExceptionObject = (struct UnBCL::Object *)AddStackTraceToException<UnBCL::InvalidOperationException>(
                                                   v24,
                                                   "struct UnBCL::ISerializable *__cdecl UnBCL::SerializationStream::ReadObject(void)");
      throw (UnBCL::SerializationException **)&pExceptionObject;
    }
    v12 = (_QWORD *)(**v11)(v11);
    v13 = *((_QWORD *)this + 9);
    if ( v12 )
      v15 = (char *)v12 + *(int *)(v12[1] + 4LL) + 8;
    else
      v15 = 0;
    v14 = *(int *)(*(_QWORD *)(v13 + 8) + 16LL);
    (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)(v14 + v13 + 8) + 40LL))(v14 + v13 + 8, v15);
    v16 = *((_QWORD *)this + 5);
    (*(void (__fastcall **)(_QWORD *, UnBCL::SerializationStream *))(*v12 + 24LL))(v12, this);
    *((_QWORD *)this + 5) = v16;
    UnBCL::SmartPtr<UnBCL::SerializationId>::SmartPtr<UnBCL::SerializationId>(&v38, v3);
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign((char *)this + 16, v39);
    v38 = &UnBCL::SmartPtr<UnBCL::SerializationId>::`vftable';
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v38);
    return (struct UnBCL::ISerializable *)v12;
  }
  else
  {
    v18 = pExceptionObject;
    if ( pExceptionObject )
    {
      result = (struct UnBCL::ISerializable *)_RTDynamicCast_0(
                                                pExceptionObject,
                                                0,
                                                &UnBCL::Object `RTTI Type Descriptor',
                                                &UnBCL::ISerializable `RTTI Type Descriptor',
                                                0);
      if ( !result )
      {
        v28 = (*(__int64 (__fastcall **)(struct UnBCL::Object *))(*(_QWORD *)v18 + 32LL))(v18);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v38, v28);
        v29 = UnBCL::SmartPtr<UnBCL::Decoder>::operator->(&v38);
        v30 = UnBCL::CollectionBase<UnBCL::Object *>::get_InnerList(v29);
        v31 = UnBCL::String::Format(L"Deserialized non ISerializable object: %s", v30);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v36, v31);
        UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::operator=(&v38, &v36);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v36);
        if ( v18 )
          (**(void (__fastcall ***)(struct UnBCL::Object *, __int64))v18)(v18, 1);
        v32 = (UnBCL::SerializationException *)UnBCL::Object::operator new(0x38u);
        v33 = v32;
        v41 = v32;
        if ( v32 )
        {
          v34 = UnBCL::SmartPtr<UnBCL::Decoder>::operator->(&v38);
          v35 = (const unsigned __int16 *)UnBCL::CollectionBase<UnBCL::Object *>::get_InnerList(v34);
          v32 = (UnBCL::SerializationException *)UnBCL::SerializationException::SerializationException(v33, v35);
        }
        pExceptionObject = (struct UnBCL::Object *)AddStackTraceToException<UnBCL::InvalidOperationException>(
                                                     v32,
                                                     "struct UnBCL::ISerializable *__cdecl UnBCL::SerializationStream::ReadObject(void)");
        throw (UnBCL::SerializationException **)&pExceptionObject;
      }
    }
    else
    {
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180055150  mov     rax, rsp
0x180055153  push    rbp
0x180055154  push    rdi
0x180055155  push    r13
0x180055157  push    r14
0x180055159  push    r15
0x18005515b  mov     rbp, rsp
0x18005515e  sub     rsp, 60h
0x180055162  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFEh
0x18005516a  mov     [rax+8], rbx
0x18005516e  mov     [rax+20h], rsi
0x180055172  mov     rdi, rcx
0x180055175  mov     [rbp+pExceptionObject], 0
0x18005517d  lea     rdx, [rbp+pExceptionObject]; struct UnBCL::Object **
0x180055181  call    ?ReadObjectHeader@SerializationStream@UnBCL@@AEAAHAEAPEAVObject@2@@Z; UnBCL::SerializationStream::ReadObjectHeader(UnBCL::Object * &)
0x180055186  test    eax, eax
0x180055188  jz      loc_180055356
0x18005518e  lea     r14, [rdi+10h]
0x180055192  mov     rax, [r14+8]
0x180055196  test    rax, rax
0x180055199  jnz     short loc_1800551A0
0x18005519b  xor     r15d, r15d
0x18005519e  jmp     short loc_1800551B0
0x1800551a0  lock dec dword ptr [rax+8]
0x1800551a4  mov     r15, [rdi+18h]
0x1800551a8  mov     qword ptr [rdi+18h], 0
0x1800551b0  mov     ecx, 18h; unsigned __int64
0x1800551b5  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800551ba  mov     [rbp+arg_10], rax
0x1800551be  test    rax, rax
0x1800551c1  jz      short loc_1800551CF
0x1800551c3  mov     rdx, rdi; struct UnBCL::SerializationStream *
0x1800551c6  mov     rcx, rax; this
0x1800551c9  call    ??0String@UnBCL@@QEAA@AEAVSerializationStream@1@@Z; UnBCL::String::String(UnBCL::SerializationStream &)
0x1800551ce  nop
0x1800551cf  mov     rdx, rax
0x1800551d2  lea     rcx, [rbp+var_28]
0x1800551d6  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1800551db  nop
0x1800551dc  mov     dword ptr [rbp+pExceptionObject], 0
0x1800551e3  lea     rdx, [rbp+pExceptionObject]
0x1800551e7  mov     rcx, rdi
0x1800551ea  call    ??$ReadPrimitive@H@SerializationStream@UnBCL@@IEAAAEAV01@AEAH@Z; UnBCL::SerializationStream::ReadPrimitive<int>(int &)
0x1800551ef  mov     ecx, 20h ; ' '; unsigned __int64
0x1800551f4  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800551f9  mov     [rbp+arg_10], rax
0x1800551fd  test    rax, rax
0x180055200  jz      short loc_180055224
0x180055202  mov     r8d, dword ptr [rbp+pExceptionObject]; int
0x180055206  mov     rdx, [rbp+var_20]; struct UnBCL::String *
0x18005520a  test    rdx, rdx
0x18005520d  jz      short loc_18005521B
0x18005520f  lock dec dword ptr [rdx+8]
0x180055213  mov     [rbp+var_20], 0
0x18005521b  mov     rcx, rax; this
0x18005521e  call    ??0SerializationId@UnBCL@@QEAA@PEAVString@1@H@Z; UnBCL::SerializationId::SerializationId(UnBCL::String *,int)
0x180055223  nop
0x180055224  mov     rdx, rax
0x180055227  lea     rcx, [rbp+var_18]
0x18005522b  call    ??0?$SmartPtr@VSerializationId@UnBCL@@@UnBCL@@QEAA@PEAVSerializationId@1@@Z; UnBCL::SmartPtr<UnBCL::SerializationId>::SmartPtr<UnBCL::SerializationId>(UnBCL::SerializationId *)
0x180055230  nop
0x180055231  mov     rdx, [rbp+var_10]
0x180055235  mov     rcx, r14
0x180055238  call    ?Assign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXPEAVXmlNamespaceManager@2@@Z; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(UnBCL::XmlNamespaceManager *)
0x18005523d  nop
0x18005523e  lea     r13, ??_7?$SmartPtr@VSerializationId@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::SerializationId>::`vftable'
0x180055245  mov     [rbp+var_18], r13
0x180055249  lea     rcx, [rbp+var_18]
0x18005524d  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x180055252  nop
0x180055253  lea     rax, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x18005525a  mov     [rbp+var_28], rax
0x18005525e  lea     rcx, [rbp+var_28]
0x180055262  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x180055267  mov     rdx, cs:?s_Registered@SerializationStream@UnBCL@@0PEAV?$Hashtable@PEAVSerializationId@UnBCL@@PEAVTypeFactoryList@SerializationStream@2@@2@EA; UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *> * UnBCL::SerializationStream::s_Registered
0x18005526e  mov     rax, [rdx+8]
0x180055272  movsxd  rcx, dword ptr [rax+10h]
0x180055276  add     rdx, 8
0x18005527a  add     rcx, rdx
0x18005527d  mov     rax, [rcx]
0x180055280  mov     rdx, [rdi+18h]
0x180055284  mov     rax, [rax+10h]
0x180055288  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005528d  test    rax, rax
0x180055290  jz      loc_18005538E
0x180055296  mov     rax, [rax]
0x180055299  test    rax, rax
0x18005529c  jz      loc_18005538E
0x1800552a2  mov     rcx, [rax+8]
0x1800552a6  test    rcx, rcx
0x1800552a9  jz      loc_18005538E
0x1800552af  mov     rax, [rcx]
0x1800552b2  mov     rax, [rax]
0x1800552b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800552ba  mov     rsi, rax
0x1800552bd  mov     r8, [rdi+48h]
0x1800552c1  mov     rcx, [r8+8]
0x1800552c5  movsxd  rax, dword ptr [rcx+10h]
0x1800552c9  mov     rcx, [rax+r8+8]
0x1800552ce  mov     r9, [rcx+28h]
0x1800552d2  test    rsi, rsi
0x1800552d5  jnz     short loc_1800552DB
0x1800552d7  xor     edx, edx
0x1800552d9  jmp     short loc_1800552EA
0x1800552db  mov     rdx, [rsi+8]
0x1800552df  movsxd  rdx, dword ptr [rdx+4]
0x1800552e3  add     rdx, 8
0x1800552e7  add     rdx, rsi
0x1800552ea  lea     rcx, [r8+8]
0x1800552ee  add     rcx, rax
0x1800552f1  mov     rax, r9
0x1800552f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800552f9  mov     rbx, [rdi+28h]
0x1800552fd  mov     rax, [rsi]
0x180055300  mov     rdx, rdi
0x180055303  mov     rcx, rsi
0x180055306  mov     rax, [rax+18h]
0x18005530a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005530f  mov     [rdi+28h], rbx
0x180055313  mov     rdx, r15
0x180055316  lea     rcx, [rbp+var_18]
0x18005531a  call    ??0?$SmartPtr@VSerializationId@UnBCL@@@UnBCL@@QEAA@PEAVSerializationId@1@@Z; UnBCL::SmartPtr<UnBCL::SerializationId>::SmartPtr<UnBCL::SerializationId>(UnBCL::SerializationId *)
0x18005531f  nop
0x180055320  mov     rdx, [rbp+var_10]
0x180055324  mov     rcx, r14
0x180055327  call    ?Assign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXPEAVXmlNamespaceManager@2@@Z; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(UnBCL::XmlNamespaceManager *)
0x18005532c  nop
0x18005532d  mov     [rbp+var_18], r13
0x180055331  lea     rcx, [rbp+var_18]
0x180055335  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18005533a  mov     rax, rsi
0x18005533d  lea     r11, [rsp+60h+var_s0]
0x180055342  mov     rbx, [r11+30h]
0x180055346  mov     rsi, [r11+48h]
0x18005534a  mov     rsp, r11
0x18005534d  pop     r15
0x18005534f  pop     r14
0x180055351  pop     r13
0x180055353  pop     rdi
0x180055354  pop     rbp
0x180055355  retn
0x180055356  mov     rbx, [rbp+pExceptionObject]
0x18005535a  test    rbx, rbx
0x18005535d  jnz     short loc_180055363
0x18005535f  xor     eax, eax
0x180055361  jmp     short loc_18005533D
0x180055363  mov     [rsp+60h+var_40], 0
0x18005536b  lea     r9, ??_R0?AUISerializable@UnBCL@@@8; UnBCL::ISerializable `RTTI Type Descriptor'
0x180055372  lea     r8, ??_R0?AVObject@UnBCL@@@8; UnBCL::Object `RTTI Type Descriptor'
0x180055379  xor     edx, edx
0x18005537b  mov     rcx, rbx
0x18005537e  call    __RTDynamicCast_0
0x180055383  test    rax, rax
0x180055386  jz      loc_180055426
0x18005538c  jmp     short loc_18005533D
0x18005538e  mov     rcx, r14
0x180055391  call    ??C?$SmartPtr@VDecoder@UnBCL@@@UnBCL@@QEBAPEAVDecoder@1@XZ; UnBCL::SmartPtr<UnBCL::Decoder>::operator->(void)
0x180055396  mov     rcx, rax; this
0x180055399  call    ?get_IsVM@SystemInfo@UnBCL@@QEBAHXZ; UnBCL::SystemInfo::get_IsVM(void)
0x18005539e  mov     ebx, eax
0x1800553a0  mov     rcx, r14
0x1800553a3  call    ??C?$SmartPtr@VDecoder@UnBCL@@@UnBCL@@QEBAPEAVDecoder@1@XZ; UnBCL::SmartPtr<UnBCL::Decoder>::operator->(void)
0x1800553a8  mov     rcx, rax; this
0x1800553ab  call    ?get_TypeName@SerializationId@UnBCL@@QEBAPEBGXZ; UnBCL::SerializationId::get_TypeName(void)
0x1800553b0  mov     r8d, ebx
0x1800553b3  mov     rdx, rax
0x1800553b6  lea     rcx, aSawUnrecognize_0; "saw unrecognized type/version pair '%s "...
0x1800553bd  call    ?Format@String@UnBCL@@SAPEAV12@PEBGZZ; UnBCL::String::Format(ushort const *,...)
0x1800553c2  mov     rdx, rax
0x1800553c5  lea     rcx, [rbp+var_18]
0x1800553c9  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1800553ce  nop
0x1800553cf  mov     ecx, 38h ; '8'; unsigned __int64
0x1800553d4  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800553d9  mov     rbx, rax
0x1800553dc  mov     [rbp+arg_10], rax
0x1800553e0  test    rax, rax
0x1800553e3  jz      short loc_180055402
0x1800553e5  lea     rcx, [rbp+var_18]
0x1800553e9  call    ??C?$SmartPtr@VDecoder@UnBCL@@@UnBCL@@QEBAPEAVDecoder@1@XZ; UnBCL::SmartPtr<UnBCL::Decoder>::operator->(void)
0x1800553ee  mov     rcx, rax
0x1800553f1  call    ?get_InnerList@?$CollectionBase@PEAVObject@UnBCL@@@UnBCL@@MEBAPEBV?$ArrayList@PEAVObject@UnBCL@@@2@XZ; UnBCL::CollectionBase<UnBCL::Object *>::get_InnerList(void)
0x1800553f6  mov     rdx, rax; unsigned __int16 *
0x1800553f9  mov     rcx, rbx; this
0x1800553fc  call    ??0SerializationException@UnBCL@@QEAA@PEBG@Z; UnBCL::SerializationException::SerializationException(ushort const *)
0x180055401  nop
0x180055402  lea     rdx, aStructUnbclIse; "struct UnBCL::ISerializable *__cdecl Un"...
0x180055409  mov     rcx, rax
0x18005540c  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180055411  mov     [rbp+pExceptionObject], rax
0x180055415  lea     rdx, _TI5PEAVSerializationException@UnBCL@@; pThrowInfo
0x18005541c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180055420  call    _CxxThrowException_0
0x180055426  mov     rax, [rbx]
0x180055429  mov     rcx, rbx
0x18005542c  mov     rax, [rax+20h]
0x180055430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055435  mov     rdx, rax
0x180055438  lea     rcx, [rbp+var_18]
0x18005543c  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180055441  nop
0x180055442  lea     rcx, [rbp+var_18]
0x180055446  call    ??C?$SmartPtr@VDecoder@UnBCL@@@UnBCL@@QEBAPEAVDecoder@1@XZ; UnBCL::SmartPtr<UnBCL::Decoder>::operator->(void)
0x18005544b  mov     rcx, rax
0x18005544e  call    ?get_InnerList@?$CollectionBase@PEAVObject@UnBCL@@@UnBCL@@MEBAPEBV?$ArrayList@PEAVObject@UnBCL@@@2@XZ; UnBCL::CollectionBase<UnBCL::Object *>::get_InnerList(void)
0x180055453  mov     rdx, rax
0x180055456  lea     rcx, aDeserializedNo; "Deserialized non ISerializable object: "...
0x18005545d  call    ?Format@String@UnBCL@@SAPEAV12@PEBGZZ; UnBCL::String::Format(ushort const *,...)
0x180055462  mov     rdx, rax
0x180055465  lea     rcx, [rbp+var_28]
0x180055469  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18005546e  nop
0x18005546f  lea     rdx, [rbp+var_28]
0x180055473  lea     rcx, [rbp+var_18]
0x180055477  call    ??4?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::operator=(UnBCL::SmartPtr<UnBCL::XmlNamespaceManager> const &)
0x18005547c  nop
0x18005547d  lea     rcx, [rbp+var_28]; void *
0x180055481  call    ??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180055486  test    rbx, rbx
0x180055489  jz      short loc_18005549E
0x18005548b  mov     rax, [rbx]
0x18005548e  mov     edx, 1
0x180055493  mov     rcx, rbx
0x180055496  mov     rax, [rax]
0x180055499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005549e  mov     ecx, 38h ; '8'; unsigned __int64
0x1800554a3  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800554a8  mov     rbx, rax
0x1800554ab  mov     [rbp+arg_10], rax
0x1800554af  test    rax, rax
0x1800554b2  jz      short loc_1800554D1
0x1800554b4  lea     rcx, [rbp+var_18]
0x1800554b8  call    ??C?$SmartPtr@VDecoder@UnBCL@@@UnBCL@@QEBAPEAVDecoder@1@XZ; UnBCL::SmartPtr<UnBCL::Decoder>::operator->(void)
0x1800554bd  mov     rcx, rax
0x1800554c0  call    ?get_InnerList@?$CollectionBase@PEAVObject@UnBCL@@@UnBCL@@MEBAPEBV?$ArrayList@PEAVObject@UnBCL@@@2@XZ; UnBCL::CollectionBase<UnBCL::Object *>::get_InnerList(void)
0x1800554c5  mov     rdx, rax; unsigned __int16 *
0x1800554c8  mov     rcx, rbx; this
0x1800554cb  call    ??0SerializationException@UnBCL@@QEAA@PEBG@Z; UnBCL::SerializationException::SerializationException(ushort const *)
0x1800554d0  nop
0x1800554d1  lea     rdx, aStructUnbclIse; "struct UnBCL::ISerializable *__cdecl Un"...
0x1800554d8  mov     rcx, rax
0x1800554db  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x1800554e0  mov     [rbp+pExceptionObject], rax
0x1800554e4  lea     rdx, _TI5PEAVSerializationException@UnBCL@@; pThrowInfo
0x1800554eb  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800554ef  call    _CxxThrowException_0
```
