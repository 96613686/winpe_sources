# UnBCL::_::HTEnumerator<UnBCL::String *,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::TableKey,UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *>,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::KeyTraits,&UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::RetrieveEntry(ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::TableKey,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::KeyTraits,ATL::CElementTraits<UnBCL::String *>> const *,__POSITION * const &)>::CopyToArray(UnBCL::Hashtable<UnBCL::String *,UnBCL::String *> const *,UnBCL::Array<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *>> *,int)

- ea: `0x180035e74`
- end: `0x1800360d6`
- name: `?CopyToArray@?$HTEnumerator@PEAVString@UnBCL@@PEAV12@UTableKey@?$Hashtable@PEAVString@UnBCL@@PEAV12@@2@V?$DictionaryEntry@PEAVString@UnBCL@@PEAV12@@2@UKeyTraits@42@$1?RetrieveEntry@42@KA?AV52@PEBV?$CAtlMap@UTableKey@?$Hashtable@PEAVString@UnBCL@@PEAV12@@UnBCL@@PEAVString@3@UKeyTraits@23@V?$CElementTraits@PEAVString@UnBCL@@@ATL@@@ATL@@AEBQEAU__POSITION@@@Z@_@UnBCL@@SAXPEBV?$Hashtable@PEAVString@UnBCL@@PEAV12@@3@PEAV?$Array@V?$DictionaryEntry@PEAVString@UnBCL@@PEAV12@@UnBCL@@@3@H@Z`
- size: `610`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x180035ab0`

## callees

- `0x18000225c`
- `0x1800098b0`
- `0x1800099b0`
- `0x180009b40`
- `0x180009e7c`
- `0x180034588`
- `0x180035e74`
- `0x180036ba0`
- `0x180036f94`
- `0x180038fa0`
- `0x1800477d0`
- `0x18006f010`

## string_xrefs

- `0x180036024`: `void __cdecl UnBCL::_::HTEnumerator<class UnBCL::String *,class UnBCL::String *,struct UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>::TableKey,class UnBCL::DictionaryEntry<class UnBCL::String *,class UnBCL::String *>,struct UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>::KeyTraits,&protected: static class UnBCL::DictionaryEntry<class UnBCL::String *,class UnBCL::String *> __cdecl UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>::RetrieveEntry(class ATL`
- `0x18003606b`: `void __cdecl UnBCL::_::HTEnumerator<class UnBCL::String *,class UnBCL::String *,struct UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>::TableKey,class UnBCL::DictionaryEntry<class UnBCL::String *,class UnBCL::String *>,struct UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>::KeyTraits,&protected: static class UnBCL::DictionaryEntry<class UnBCL::String *,class UnBCL::String *> __cdecl UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>::RetrieveEntry(class ATL`
- `0x1800360b2`: `void __cdecl UnBCL::_::HTEnumerator<class UnBCL::String *,class UnBCL::String *,struct UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>::TableKey,class UnBCL::DictionaryEntry<class UnBCL::String *,class UnBCL::String *>,struct UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>::KeyTraits,&protected: static class UnBCL::DictionaryEntry<class UnBCL::String *,class UnBCL::String *> __cdecl UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>::RetrieveEntry(class ATL`
- `0x18003605b`: `null array to Hashtable#CopyTo`
- `0x1800360a2`: `negative start index to CopyTo`
- `0x180036014`: `array of insufficient size to CopyTo`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall UnBCL::_::HTEnumerator<UnBCL::String *,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::TableKey,UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *>,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::KeyTraits,&protected: static UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::RetrieveEntry(ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::TableKey,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::KeyTraits,ATL::CElementTraits<UnBCL::String *>> const *,__POSITION * const &)>::CopyToArray(
        __int64 a1,
        __int64 a2,
        int a3)
{
  unsigned int v3; // r14d
  int v6; // r15d
  __int64 (__fastcall ***v7)(_QWORD); // rcx
  signed int v8; // ebx
  __int64 result; // rax
  void (__fastcall *v10)(__int64, void ***, __int64); // r9
  __int64 v11; // r8
  UnBCL::ArgumentException *v12; // rax
  UnBCL::ArgumentNullException *v13; // rax
  UnBCL::ArgumentOutOfRangeException *v14; // rax
  void **v15; // [rsp+30h] [rbp-51h] BYREF
  _QWORD v16[3]; // [rsp+38h] [rbp-49h]
  int v17; // [rsp+50h] [rbp-31h]
  int v18; // [rsp+54h] [rbp-2Dh]
  void **v19; // [rsp+60h] [rbp-21h]
  int v20; // [rsp+68h] [rbp-19h]
  signed __int32 v21; // [rsp+6Ch] [rbp-15h]
  __int64 v22; // [rsp+70h] [rbp-11h]
  _BYTE v23[16]; // [rsp+78h] [rbp-9h] BYREF
  __int64 v24; // [rsp+88h] [rbp+7h]
  __int64 v25; // [rsp+90h] [rbp+Fh]
  int v26; // [rsp+98h] [rbp+17h]
  int v27; // [rsp+9Ch] [rbp+1Bh]
  void **v28; // [rsp+A8h] [rbp+27h] BYREF
  __int64 pExceptionObject; // [rsp+F0h] [rbp+6Fh] BYREF
  void ***v30; // [rsp+100h] [rbp+7Fh]

  v22 = -2;
  v3 = a3;
  v6 = 0;
  if ( !a2 )
  {
    v13 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v30 = (void ***)v13;
    if ( v13 )
      v13 = (UnBCL::ArgumentNullException *)UnBCL::ArgumentNullException::ArgumentNullException(
                                              v13,
                                              L"null array to Hashtable#CopyTo");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v13,
                         "void __cdecl UnBCL::_::HTEnumerator<class UnBCL::String *,class UnBCL::String *,struct UnBCL::H"
                         "ashtable<class UnBCL::String *,class UnBCL::String *>::TableKey,class UnBCL::DictionaryEntry<cl"
                         "ass UnBCL::String *,class UnBCL::String *>,struct UnBCL::Hashtable<class UnBCL::String *,class "
                         "UnBCL::String *>::KeyTraits,&protected: static class UnBCL::DictionaryEntry<class UnBCL::String"
                         " *,class UnBCL::String *> __cdecl UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>"
                         "::RetrieveEntry(class ATL::CAtlMap<struct UnBCL::Hashtable<class UnBCL::String *,class UnBCL::S"
                         "tring *>::TableKey,class UnBCL::String *,struct UnBCL::Hashtable<class UnBCL::String *,class Un"
                         "BCL::String *>::KeyTraits,class ATL::CElementTraits<class UnBCL::String *> > const *,struct __P"
                         "OSITION * const &)>::CopyToArray(const class UnBCL::Hashtable<class UnBCL::String *,class UnBCL"
                         "::String *> *,class UnBCL::Array<class UnBCL::DictionaryEntry<class UnBCL::String *,class UnBCL"
                         "::String *> > *,int)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  if ( a3 < 0 )
  {
    v14 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::Object::operator new(0x38u);
    v30 = (void ***)v14;
    if ( v14 )
      v14 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(
                                                    v14,
                                                    L"negative start index to CopyTo");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v14,
                         "void __cdecl UnBCL::_::HTEnumerator<class UnBCL::String *,class UnBCL::String *,struct UnBCL::H"
                         "ashtable<class UnBCL::String *,class UnBCL::String *>::TableKey,class UnBCL::DictionaryEntry<cl"
                         "ass UnBCL::String *,class UnBCL::String *>,struct UnBCL::Hashtable<class UnBCL::String *,class "
                         "UnBCL::String *>::KeyTraits,&protected: static class UnBCL::DictionaryEntry<class UnBCL::String"
                         " *,class UnBCL::String *> __cdecl UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>"
                         "::RetrieveEntry(class ATL::CAtlMap<struct UnBCL::Hashtable<class UnBCL::String *,class UnBCL::S"
                         "tring *>::TableKey,class UnBCL::String *,struct UnBCL::Hashtable<class UnBCL::String *,class Un"
                         "BCL::String *>::KeyTraits,class ATL::CElementTraits<class UnBCL::String *> > const *,struct __P"
                         "OSITION * const &)>::CopyToArray(const class UnBCL::Hashtable<class UnBCL::String *,class UnBCL"
                         "::String *> *,class UnBCL::Array<class UnBCL::DictionaryEntry<class UnBCL::String *,class UnBCL"
                         "::String *> > *,int)");
    throw (UnBCL::ArgumentOutOfRangeException **)&pExceptionObject;
  }
  v7 = (__int64 (__fastcall ***)(_QWORD))(a1 + *(int *)(*(_QWORD *)(a1 + 8) + 12LL) + 8LL);
  v8 = (**v7)(v7);
  if ( (int)((**(__int64 (__fastcall ***)(__int64))a2)(a2) - v3) < v8 )
  {
    v12 = (UnBCL::ArgumentException *)UnBCL::Object::operator new(0x38u);
    v30 = (void ***)v12;
    if ( v12 )
      v12 = (UnBCL::ArgumentException *)UnBCL::ArgumentException::ArgumentException(
                                          v12,
                                          L"array of insufficient size to CopyTo");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v12,
                         "void __cdecl UnBCL::_::HTEnumerator<class UnBCL::String *,class UnBCL::String *,struct UnBCL::H"
                         "ashtable<class UnBCL::String *,class UnBCL::String *>::TableKey,class UnBCL::DictionaryEntry<cl"
                         "ass UnBCL::String *,class UnBCL::String *>,struct UnBCL::Hashtable<class UnBCL::String *,class "
                         "UnBCL::String *>::KeyTraits,&protected: static class UnBCL::DictionaryEntry<class UnBCL::String"
                         " *,class UnBCL::String *> __cdecl UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>"
                         "::RetrieveEntry(class ATL::CAtlMap<struct UnBCL::Hashtable<class UnBCL::String *,class UnBCL::S"
                         "tring *>::TableKey,class UnBCL::String *,struct UnBCL::Hashtable<class UnBCL::String *,class Un"
                         "BCL::String *>::KeyTraits,class ATL::CElementTraits<class UnBCL::String *> > const *,struct __P"
                         "OSITION * const &)>::CopyToArray(const class UnBCL::Hashtable<class UnBCL::String *,class UnBCL"
                         "::String *> *,class UnBCL::Array<class UnBCL::DictionaryEntry<class UnBCL::String *,class UnBCL"
                         "::String *> > *,int)");
    throw (UnBCL::ArgumentException **)&pExceptionObject;
  }
  result = ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::TableKey,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::KeyTraits,ATL::CElementTraits<UnBCL::String *>>::GetStartPosition(*(_QWORD *)(a1 + 40));
  for ( pExceptionObject = result; pExceptionObject; v28 = &UnBCL::Object::`vftable' )
  {
    UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::RetrieveEntry(v23, *(_QWORD *)(a1 + 40), &pExceptionObject);
    v10 = *(void (__fastcall **)(__int64, void ***, __int64))(*(_QWORD *)a2 + 40LL);
    v11 = v3++;
    v30 = &v15;
    v16[0] = &UnBCL::DictionaryEntry<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::`vbtable';
    v19 = &UnBCL::Object::`vftable';
    v20 = 0;
    v21 = _InterlockedIncrement(&dword_1800FFC68);
    v6 |= 1u;
    v15 = &UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *>::`vftable'{for `UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *>'};
    *(_QWORD *)((char *)v16
              + SHIDWORD(UnBCL::DictionaryEntry<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::`vbtable')) = &UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *>::`vftable'{for `UnBCL::Object'};
    *(_DWORD *)((char *)&v15 + *(int *)(v16[0] + 4LL) + 4) = 0;
    v16[1] = v24;
    v16[2] = v25;
    v17 = v26;
    v18 = v27;
    v10(a2, &v15, v11);
    ATL::CAtlMap<UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::TableKey,UnBCL::SerializationStream::TypeFactoryList *,UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::KeyTraits,ATL::CElementTraits<UnBCL::SerializationStream::TypeFactoryList *>>::GetNext(
      *(_QWORD *)(a1 + 40),
      &pExceptionObject);
    result = UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *>::~DictionaryEntry<UnBCL::String *,UnBCL::String *>(&v28);
  }
  return result;
}

```

## disassembly

```asm
0x180035e74  mov     rax, rsp
0x180035e77  push    rbp
0x180035e78  push    rdi
0x180035e79  push    r13
0x180035e7b  push    r14
0x180035e7d  push    r15
0x180035e7f  lea     rbp, [rax-5Fh]
0x180035e83  sub     rsp, 0B0h
0x180035e8a  mov     [rbp+57h+var_68], 0FFFFFFFFFFFFFFFEh
0x180035e92  mov     [rax+8], rbx
0x180035e96  mov     [rax+18h], rsi
0x180035e9a  mov     r14d, r8d
0x180035e9d  mov     rdi, rdx
0x180035ea0  mov     rsi, rcx
0x180035ea3  xor     r15d, r15d
0x180035ea6  mov     [rbp+57h+var_B0], r15d
0x180035eaa  test    rdx, rdx
0x180035ead  jz      loc_180036048
0x180035eb3  test    r8d, r8d
0x180035eb6  js      loc_18003608F
0x180035ebc  mov     rax, [rcx+8]
0x180035ec0  movsxd  rcx, dword ptr [rax+0Ch]
0x180035ec4  add     rcx, 8
0x180035ec8  add     rcx, rsi
0x180035ecb  mov     rax, [rcx]
0x180035ece  mov     rax, [rax]
0x180035ed1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035ed6  mov     ebx, eax
0x180035ed8  mov     rcx, [rdi]
0x180035edb  mov     rax, [rcx]
0x180035ede  mov     rcx, rdi
0x180035ee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035ee6  sub     eax, r14d
0x180035ee9  cmp     eax, ebx
0x180035eeb  jl      loc_180036001
0x180035ef1  mov     rcx, [rsi+28h]
0x180035ef5  call    ?GetStartPosition@?$CAtlMap@UTableKey@?$Hashtable@PEAVString@UnBCL@@PEAV12@@UnBCL@@PEAVString@3@UKeyTraits@23@V?$CElementTraits@PEAVString@UnBCL@@@ATL@@@ATL@@QEBAPEAU__POSITION@@XZ; ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::TableKey,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::KeyTraits,ATL::CElementTraits<UnBCL::String *>>::GetStartPosition(void)
0x180035efa  mov     [rbp+57h+pExceptionObject], rax
0x180035efe  test    rax, rax
0x180035f01  jz      loc_180035FE5
0x180035f07  lea     ebx, [r15+1]
0x180035f0b  lea     r13, ??_7Object@UnBCL@@6B@; const UnBCL::Object::`vftable'
0x180035f12  lea     r8, [rbp+57h+pExceptionObject]
0x180035f16  mov     rdx, [rsi+28h]
0x180035f1a  lea     rcx, [rbp+57h+var_60]
0x180035f1e  call    ?RetrieveEntry@?$Hashtable@PEAVString@UnBCL@@PEAV12@@UnBCL@@KA?AV?$DictionaryEntry@PEAVString@UnBCL@@PEAV12@@2@PEBV?$CAtlMap@UTableKey@?$Hashtable@PEAVString@UnBCL@@PEAV12@@UnBCL@@PEAVString@3@UKeyTraits@23@V?$CElementTraits@PEAVString@UnBCL@@@ATL@@@ATL@@AEBQEAU__POSITION@@@Z; UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::RetrieveEntry(ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::TableKey,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::KeyTraits,ATL::CElementTraits<UnBCL::String *>> const *,__POSITION * const &)
0x180035f23  nop
0x180035f24  mov     rax, [rdi]
0x180035f27  mov     r9, [rax+28h]
0x180035f2b  mov     r8d, r14d
0x180035f2e  add     r14d, ebx
0x180035f31  lea     rax, [rbp+57h+var_A8]
0x180035f35  mov     [rbp+57h+arg_18], rax
0x180035f39  lea     rax, ??_8?$DictionaryEntry@PEAVSerializationId@UnBCL@@PEAVTypeFactoryList@SerializationStream@2@@UnBCL@@7B@; const UnBCL::DictionaryEntry<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::`vbtable'
0x180035f40  mov     [rbp+57h+var_A0], rax
0x180035f44  mov     [rbp+57h+var_78], r13
0x180035f48  mov     [rbp+57h+var_70], 0
0x180035f4f  mov     eax, ebx
0x180035f51  lock xadd cs:dword_1800FFC68, eax
0x180035f59  add     eax, ebx
0x180035f5b  mov     [rbp+57h+var_6C], eax
0x180035f5e  or      r15d, ebx
0x180035f61  mov     [rbp+57h+var_B0], r15d
0x180035f65  lea     rax, ??_7?$DictionaryEntry@PEAVString@UnBCL@@PEAV12@@UnBCL@@6B01@@; const UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *>::`vftable'{for `UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *>'}
0x180035f6c  mov     [rbp+57h+var_A8], rax
0x180035f70  mov     rax, [rbp+57h+var_A0]
0x180035f74  movsxd  rcx, dword ptr [rax+4]
0x180035f78  lea     rax, ??_7?$DictionaryEntry@PEAVString@UnBCL@@PEAV12@@UnBCL@@6BObject@1@@; const UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *>::`vftable'{for `UnBCL::Object'}
0x180035f7f  mov     [rbp+rcx+57h+var_A0], rax
0x180035f84  mov     rax, [rbp+57h+var_A0]
0x180035f88  movsxd  rcx, dword ptr [rax+4]
0x180035f8c  mov     dword ptr [rbp+rcx+57h+var_A8+4], 0
0x180035f94  mov     rax, [rbp+57h+var_50]
0x180035f98  mov     [rbp+57h+var_98], rax
0x180035f9c  mov     rax, [rbp+57h+var_48]
0x180035fa0  mov     [rbp+57h+var_90], rax
0x180035fa4  mov     ecx, [rbp+57h+var_40]
0x180035fa7  mov     [rbp+57h+var_88], ecx
0x180035faa  mov     ecx, [rbp+57h+var_3C]
0x180035fad  mov     [rbp+57h+var_84], ecx
0x180035fb0  lea     rdx, [rbp+57h+var_A8]
0x180035fb4  mov     rcx, rdi
0x180035fb7  mov     rax, r9
0x180035fba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035fbf  lea     rdx, [rbp+57h+pExceptionObject]
0x180035fc3  mov     rcx, [rsi+28h]
0x180035fc7  call    ?GetNext@?$CAtlMap@UTableKey@?$Hashtable@PEAVSerializationId@UnBCL@@PEAVTypeFactoryList@SerializationStream@2@@UnBCL@@PEAVTypeFactoryList@SerializationStream@3@UKeyTraits@23@V?$CElementTraits@PEAVTypeFactoryList@SerializationStream@UnBCL@@@ATL@@@ATL@@QEAAPEAVCPair@12@AEAPEAU__POSITION@@@Z; ATL::CAtlMap<UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::TableKey,UnBCL::SerializationStream::TypeFactoryList *,UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::KeyTraits,ATL::CElementTraits<UnBCL::SerializationStream::TypeFactoryList *>>::GetNext(__POSITION * &)
0x180035fcc  nop
0x180035fcd  lea     rcx, [rbp+57h+var_30]
0x180035fd1  call    ??1?$DictionaryEntry@PEAVString@UnBCL@@PEAV12@@UnBCL@@UEAA@XZ; UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *>::~DictionaryEntry<UnBCL::String *,UnBCL::String *>(void)
0x180035fd6  mov     [rbp+57h+var_30], r13
0x180035fda  cmp     [rbp+57h+pExceptionObject], 0
0x180035fdf  jnz     loc_180035F12
0x180035fe5  lea     r11, [rsp+0D0h+var_20]
0x180035fed  mov     rbx, [r11+30h]
0x180035ff1  mov     rsi, [r11+40h]
0x180035ff5  mov     rsp, r11
0x180035ff8  pop     r15
0x180035ffa  pop     r14
0x180035ffc  pop     r13
0x180035ffe  pop     rdi
0x180035fff  pop     rbp
0x180036000  retn
0x180036001  mov     ecx, 38h ; '8'; unsigned __int64
0x180036006  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003600b  mov     [rbp+57h+arg_18], rax
0x18003600f  test    rax, rax
0x180036012  jz      short loc_180036024
0x180036014  lea     rdx, aArrayOfInsuffi; "array of insufficient size to CopyTo"
0x18003601b  mov     rcx, rax; this
0x18003601e  call    ??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x180036023  nop
0x180036024  lea     rdx, aVoidCdeclUnbcl_43; "void __cdecl UnBCL::_::HTEnumerator<cla"...
0x18003602b  mov     rcx, rax
0x18003602e  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180036033  mov     [rbp+57h+pExceptionObject], rax
0x180036037  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x18003603e  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180036042  call    _CxxThrowException_0
0x180036048  mov     ecx, 38h ; '8'; unsigned __int64
0x18003604d  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180036052  mov     [rbp+57h+arg_18], rax
0x180036056  test    rax, rax
0x180036059  jz      short loc_18003606B
0x18003605b  lea     rdx, aNullArrayToHas; "null array to Hashtable#CopyTo"
0x180036062  mov     rcx, rax; this
0x180036065  call    ??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x18003606a  nop
0x18003606b  lea     rdx, aVoidCdeclUnbcl_43; "void __cdecl UnBCL::_::HTEnumerator<cla"...
0x180036072  mov     rcx, rax
0x180036075  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003607a  mov     [rbp+57h+pExceptionObject], rax
0x18003607e  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x180036085  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180036089  call    _CxxThrowException_0
0x18003608f  mov     ecx, 38h ; '8'; unsigned __int64
0x180036094  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180036099  mov     [rbp+57h+arg_18], rax
0x18003609d  test    rax, rax
0x1800360a0  jz      short loc_1800360B2
0x1800360a2  lea     rdx, aNegativeStartI; "negative start index to CopyTo"
0x1800360a9  mov     rcx, rax; this
0x1800360ac  call    ??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x1800360b1  nop
0x1800360b2  lea     rdx, aVoidCdeclUnbcl_43; "void __cdecl UnBCL::_::HTEnumerator<cla"...
0x1800360b9  mov     rcx, rax
0x1800360bc  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x1800360c1  mov     [rbp+57h+pExceptionObject], rax
0x1800360c5  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x1800360cc  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800360d0  call    _CxxThrowException_0
```
