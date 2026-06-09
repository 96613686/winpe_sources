# UnBCL::_::HTEnumerator<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *,UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::TableKey,UnBCL::SerializationStream::TypeFactoryList *,UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::KeyTraits,&UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::RetrieveValue(ATL::CAtlMap<UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::TableKey,UnBCL::SerializationStream::TypeFactoryList *,UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::KeyTraits,ATL::CElementTraits<UnBCL::SerializationStream::TypeFactoryList *>> const *,__POSITION * const &)>::CopyToArray(UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *> const *,UnBCL::Array<UnBCL::SerializationStream::TypeFactoryList *> *,int)

- ea: `0x180053294`
- end: `0x18005343e`
- name: `?CopyToArray@?$HTEnumerator@PEAVSerializationId@UnBCL@@PEAVTypeFactoryList@SerializationStream@2@UTableKey@?$Hashtable@PEAVSerializationId@UnBCL@@PEAVTypeFactoryList@SerializationStream@2@@2@PEAV342@UKeyTraits@62@$1?RetrieveValue@62@KAPEAV342@PEBV?$CAtlMap@UTableKey@?$Hashtable@PEAVSerializationId@UnBCL@@PEAVTypeFactoryList@SerializationStream@2@@UnBCL@@PEAVTypeFactoryList@SerializationStream@3@UKeyTraits@23@V?$CElementTraits@PEAVTypeFactoryList@SerializationStream@UnBCL@@@ATL@@@ATL@@AEBQEAU__POSITION@@@Z@_@UnBCL@@SAXPEBV?$Hashtable@PEAVSerializationId@UnBCL@@PEAVTypeFactoryList@SerializationStream@2@@3@PEAV?$Array@PEAVTypeFactoryList@SerializationStream@UnBCL@@@3@H@Z`
- size: `426`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x1800530a4`

## callees

- `0x18000225c`
- `0x1800066cc`
- `0x1800098b0`
- `0x1800099b0`
- `0x180009b40`
- `0x180009e7c`
- `0x180036ba0`
- `0x180036f94`
- `0x1800477d0`
- `0x180053294`
- `0x18006f010`

## string_xrefs

- `0x18005337c`: `null array to Hashtable#CopyTo`
- `0x1800533c3`: `negative start index to CopyTo`
- `0x18005340a`: `array of insufficient size to CopyTo`
- `0x18005338c`: `void __cdecl UnBCL::_::HTEnumerator<class UnBCL::SerializationId *,class UnBCL::SerializationStream::TypeFactoryList *,struct UnBCL::Hashtable<class UnBCL::SerializationId *,class UnBCL::SerializationStream::TypeFactoryList *>::TableKey,class UnBCL::SerializationStream::TypeFactoryList *,struct UnBCL::Hashtable<class UnBCL::SerializationId *,class UnBCL::SerializationStream::TypeFactoryList *>::KeyTraits,&protected: static class UnBCL::SerializationStream::TypeFactoryList * __cdecl UnBCL::Hashta`
- `0x1800533d3`: `void __cdecl UnBCL::_::HTEnumerator<class UnBCL::SerializationId *,class UnBCL::SerializationStream::TypeFactoryList *,struct UnBCL::Hashtable<class UnBCL::SerializationId *,class UnBCL::SerializationStream::TypeFactoryList *>::TableKey,class UnBCL::SerializationStream::TypeFactoryList *,struct UnBCL::Hashtable<class UnBCL::SerializationId *,class UnBCL::SerializationStream::TypeFactoryList *>::KeyTraits,&protected: static class UnBCL::SerializationStream::TypeFactoryList * __cdecl UnBCL::Hashta`
- `0x18005341a`: `void __cdecl UnBCL::_::HTEnumerator<class UnBCL::SerializationId *,class UnBCL::SerializationStream::TypeFactoryList *,struct UnBCL::Hashtable<class UnBCL::SerializationId *,class UnBCL::SerializationStream::TypeFactoryList *>::TableKey,class UnBCL::SerializationStream::TypeFactoryList *,struct UnBCL::Hashtable<class UnBCL::SerializationId *,class UnBCL::SerializationStream::TypeFactoryList *>::KeyTraits,&protected: static class UnBCL::SerializationStream::TypeFactoryList * __cdecl UnBCL::Hashta`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UnBCL::_::HTEnumerator<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *,UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::TableKey,UnBCL::SerializationStream::TypeFactoryList *,UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::KeyTraits,&protected: static UnBCL::SerializationStream::TypeFactoryList * UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::RetrieveValue(ATL::CAtlMap<UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::TableKey,UnBCL::SerializationStream::TypeFactoryList *,UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::KeyTraits,ATL::CElementTraits<UnBCL::SerializationStream::TypeFactoryList *>> const *,__POSITION * const &)>::CopyToArray(
        __int64 a1,
        __int64 a2,
        int a3)
{
  unsigned int v3; // edi
  __int64 (__fastcall ***v6)(_QWORD); // rcx
  signed int v7; // ebx
  __int64 result; // rax
  __int64 v9; // rcx
  UnBCL::ArgumentNullException *v10; // rax
  UnBCL::ArgumentOutOfRangeException *v11; // rax
  UnBCL::ArgumentException *v12; // rax
  __int64 pExceptionObject; // [rsp+58h] [rbp+28h] BYREF
  UnBCL::ArgumentNullException *v14; // [rsp+68h] [rbp+38h]

  v3 = a3;
  if ( !a2 )
  {
    v10 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v14 = v10;
    if ( v10 )
      v10 = (UnBCL::ArgumentNullException *)UnBCL::ArgumentNullException::ArgumentNullException(
                                              v10,
                                              L"null array to Hashtable#CopyTo");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v10,
                         "void __cdecl UnBCL::_::HTEnumerator<class UnBCL::SerializationId *,class UnBCL::SerializationSt"
                         "ream::TypeFactoryList *,struct UnBCL::Hashtable<class UnBCL::SerializationId *,class UnBCL::Ser"
                         "ializationStream::TypeFactoryList *>::TableKey,class UnBCL::SerializationStream::TypeFactoryLis"
                         "t *,struct UnBCL::Hashtable<class UnBCL::SerializationId *,class UnBCL::SerializationStream::Ty"
                         "peFactoryList *>::KeyTraits,&protected: static class UnBCL::SerializationStream::TypeFactoryLis"
                         "t * __cdecl UnBCL::Hashtable<class UnBCL::SerializationId *,class UnBCL::SerializationStream::T"
                         "ypeFactoryList *>::RetrieveValue(class ATL::CAtlMap<struct UnBCL::Hashtable<class UnBCL::Serial"
                         "izationId *,class UnBCL::SerializationStream::TypeFactoryList *>::TableKey,class UnBCL::Seriali"
                         "zationStream::TypeFactoryList *,struct UnBCL::Hashtable<class UnBCL::SerializationId *,class Un"
                         "BCL::SerializationStream::TypeFactoryList *>::KeyTraits,class ATL::CElementTraits<class UnBCL::"
                         "SerializationStream::TypeFactoryList *> > const *,struct __POSITION * const &)>::CopyToArray(co"
                         "nst class UnBCL::Hashtable<class UnBCL::SerializationId *,class UnBCL::SerializationStream::Typ"
                         "eFactoryList *> *,class UnBCL::Array<class UnBCL::SerializationStream::TypeFactoryList *> *,int)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  if ( a3 < 0 )
  {
    v11 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::Object::operator new(0x38u);
    v14 = v11;
    if ( v11 )
      v11 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(
                                                    v11,
                                                    L"negative start index to CopyTo");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v11,
                         "void __cdecl UnBCL::_::HTEnumerator<class UnBCL::SerializationId *,class UnBCL::SerializationSt"
                         "ream::TypeFactoryList *,struct UnBCL::Hashtable<class UnBCL::SerializationId *,class UnBCL::Ser"
                         "ializationStream::TypeFactoryList *>::TableKey,class UnBCL::SerializationStream::TypeFactoryLis"
                         "t *,struct UnBCL::Hashtable<class UnBCL::SerializationId *,class UnBCL::SerializationStream::Ty"
                         "peFactoryList *>::KeyTraits,&protected: static class UnBCL::SerializationStream::TypeFactoryLis"
                         "t * __cdecl UnBCL::Hashtable<class UnBCL::SerializationId *,class UnBCL::SerializationStream::T"
                         "ypeFactoryList *>::RetrieveValue(class ATL::CAtlMap<struct UnBCL::Hashtable<class UnBCL::Serial"
                         "izationId *,class UnBCL::SerializationStream::TypeFactoryList *>::TableKey,class UnBCL::Seriali"
                         "zationStream::TypeFactoryList *,struct UnBCL::Hashtable<class UnBCL::SerializationId *,class Un"
                         "BCL::SerializationStream::TypeFactoryList *>::KeyTraits,class ATL::CElementTraits<class UnBCL::"
                         "SerializationStream::TypeFactoryList *> > const *,struct __POSITION * const &)>::CopyToArray(co"
                         "nst class UnBCL::Hashtable<class UnBCL::SerializationId *,class UnBCL::SerializationStream::Typ"
                         "eFactoryList *> *,class UnBCL::Array<class UnBCL::SerializationStream::TypeFactoryList *> *,int)");
    throw (UnBCL::ArgumentOutOfRangeException **)&pExceptionObject;
  }
  v6 = (__int64 (__fastcall ***)(_QWORD))(a1 + *(int *)(*(_QWORD *)(a1 + 8) + 12LL) + 8LL);
  v7 = (**v6)(v6);
  if ( (int)((**(__int64 (__fastcall ***)(__int64))a2)(a2) - v3) < v7 )
  {
    v12 = (UnBCL::ArgumentException *)UnBCL::Object::operator new(0x38u);
    v14 = v12;
    if ( v12 )
      v12 = (UnBCL::ArgumentException *)UnBCL::ArgumentException::ArgumentException(
                                          v12,
                                          L"array of insufficient size to CopyTo");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v12,
                         "void __cdecl UnBCL::_::HTEnumerator<class UnBCL::SerializationId *,class UnBCL::SerializationSt"
                         "ream::TypeFactoryList *,struct UnBCL::Hashtable<class UnBCL::SerializationId *,class UnBCL::Ser"
                         "ializationStream::TypeFactoryList *>::TableKey,class UnBCL::SerializationStream::TypeFactoryLis"
                         "t *,struct UnBCL::Hashtable<class UnBCL::SerializationId *,class UnBCL::SerializationStream::Ty"
                         "peFactoryList *>::KeyTraits,&protected: static class UnBCL::SerializationStream::TypeFactoryLis"
                         "t * __cdecl UnBCL::Hashtable<class UnBCL::SerializationId *,class UnBCL::SerializationStream::T"
                         "ypeFactoryList *>::RetrieveValue(class ATL::CAtlMap<struct UnBCL::Hashtable<class UnBCL::Serial"
                         "izationId *,class UnBCL::SerializationStream::TypeFactoryList *>::TableKey,class UnBCL::Seriali"
                         "zationStream::TypeFactoryList *,struct UnBCL::Hashtable<class UnBCL::SerializationId *,class Un"
                         "BCL::SerializationStream::TypeFactoryList *>::KeyTraits,class ATL::CElementTraits<class UnBCL::"
                         "SerializationStream::TypeFactoryList *> > const *,struct __POSITION * const &)>::CopyToArray(co"
                         "nst class UnBCL::Hashtable<class UnBCL::SerializationId *,class UnBCL::SerializationStream::Typ"
                         "eFactoryList *> *,class UnBCL::Array<class UnBCL::SerializationStream::TypeFactoryList *> *,int)");
    throw (UnBCL::ArgumentException **)&pExceptionObject;
  }
  result = ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::TableKey,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::KeyTraits,ATL::CElementTraits<UnBCL::String *>>::GetStartPosition(*(_QWORD *)(a1 + 40));
  v9 = result;
  pExceptionObject = result;
  if ( result )
  {
    while ( 1 )
    {
      if ( !v9 )
        ATL::AtlThrowImpl(-2147467259);
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)a2 + 40LL))(a2, *(_QWORD *)(v9 + 16), v3);
      result = ATL::CAtlMap<UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::TableKey,UnBCL::SerializationStream::TypeFactoryList *,UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::KeyTraits,ATL::CElementTraits<UnBCL::SerializationStream::TypeFactoryList *>>::GetNext(
                 *(_QWORD *)(a1 + 40),
                 &pExceptionObject);
      v9 = pExceptionObject;
      if ( !pExceptionObject )
        break;
      ++v3;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180053294  push    rbp
0x180053296  push    rdi
0x180053297  push    r14
0x180053299  mov     rbp, rsp
0x18005329c  sub     rsp, 30h
0x1800532a0  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFEh
0x1800532a8  mov     [rsp+30h+arg_0], rbx
0x1800532ad  mov     [rsp+30h+arg_10], rsi
0x1800532b2  mov     edi, r8d
0x1800532b5  mov     rsi, rdx
0x1800532b8  mov     r14, rcx
0x1800532bb  test    rdx, rdx
0x1800532be  jz      loc_180053369
0x1800532c4  test    r8d, r8d
0x1800532c7  js      loc_1800533B0
0x1800532cd  mov     rax, [rcx+8]
0x1800532d1  movsxd  rcx, dword ptr [rax+0Ch]
0x1800532d5  add     rcx, 8
0x1800532d9  add     rcx, r14
0x1800532dc  mov     rax, [rcx]
0x1800532df  mov     rax, [rax]
0x1800532e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800532e7  mov     ebx, eax
0x1800532e9  mov     rcx, [rsi]
0x1800532ec  mov     rax, [rcx]
0x1800532ef  mov     rcx, rsi
0x1800532f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800532f7  sub     eax, edi
0x1800532f9  cmp     eax, ebx
0x1800532fb  jl      loc_1800533F7
0x180053301  mov     rcx, [r14+28h]
0x180053305  call    ?GetStartPosition@?$CAtlMap@UTableKey@?$Hashtable@PEAVString@UnBCL@@PEAV12@@UnBCL@@PEAVString@3@UKeyTraits@23@V?$CElementTraits@PEAVString@UnBCL@@@ATL@@@ATL@@QEBAPEAU__POSITION@@XZ; ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::TableKey,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::KeyTraits,ATL::CElementTraits<UnBCL::String *>>::GetStartPosition(void)
0x18005330a  mov     rcx, rax
0x18005330d  mov     [rbp+pExceptionObject], rax
0x180053311  test    rax, rax
0x180053314  jz      short loc_18005334B
0x180053316  test    rcx, rcx
0x180053319  jz      short loc_18005335E
0x18005331b  mov     rax, [rsi]
0x18005331e  mov     r8d, edi
0x180053321  mov     rdx, [rcx+10h]
0x180053325  mov     rcx, rsi
0x180053328  mov     rax, [rax+28h]
0x18005332c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053331  lea     rdx, [rbp+pExceptionObject]
0x180053335  mov     rcx, [r14+28h]
0x180053339  call    ?GetNext@?$CAtlMap@UTableKey@?$Hashtable@PEAVSerializationId@UnBCL@@PEAVTypeFactoryList@SerializationStream@2@@UnBCL@@PEAVTypeFactoryList@SerializationStream@3@UKeyTraits@23@V?$CElementTraits@PEAVTypeFactoryList@SerializationStream@UnBCL@@@ATL@@@ATL@@QEAAPEAVCPair@12@AEAPEAU__POSITION@@@Z; ATL::CAtlMap<UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::TableKey,UnBCL::SerializationStream::TypeFactoryList *,UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::KeyTraits,ATL::CElementTraits<UnBCL::SerializationStream::TypeFactoryList *>>::GetNext(__POSITION * &)
0x18005333e  mov     rcx, [rbp+pExceptionObject]
0x180053342  test    rcx, rcx
0x180053345  jz      short loc_18005334B
0x180053347  inc     edi
0x180053349  jmp     short loc_180053316
0x18005334b  mov     rbx, [rsp+30h+arg_0]
0x180053350  mov     rsi, [rsp+30h+arg_10]
0x180053355  add     rsp, 30h
0x180053359  pop     r14
0x18005335b  pop     rdi
0x18005335c  pop     rbp
0x18005335d  retn
0x18005335e  mov     ecx, 80004005h; int
0x180053363  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180053369  mov     ecx, 38h ; '8'; unsigned __int64
0x18005336e  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180053373  mov     [rbp+arg_18], rax
0x180053377  test    rax, rax
0x18005337a  jz      short loc_18005338C
0x18005337c  lea     rdx, aNullArrayToHas; "null array to Hashtable#CopyTo"
0x180053383  mov     rcx, rax; this
0x180053386  call    ??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x18005338b  nop
0x18005338c  lea     rdx, aVoidCdeclUnbcl_145; "void __cdecl UnBCL::_::HTEnumerator<cla"...
0x180053393  mov     rcx, rax
0x180053396  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18005339b  mov     [rbp+pExceptionObject], rax
0x18005339f  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x1800533a6  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800533aa  call    _CxxThrowException_0
0x1800533b0  mov     ecx, 38h ; '8'; unsigned __int64
0x1800533b5  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800533ba  mov     [rbp+arg_18], rax
0x1800533be  test    rax, rax
0x1800533c1  jz      short loc_1800533D3
0x1800533c3  lea     rdx, aNegativeStartI; "negative start index to CopyTo"
0x1800533ca  mov     rcx, rax; this
0x1800533cd  call    ??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x1800533d2  nop
0x1800533d3  lea     rdx, aVoidCdeclUnbcl_145; "void __cdecl UnBCL::_::HTEnumerator<cla"...
0x1800533da  mov     rcx, rax
0x1800533dd  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x1800533e2  mov     [rbp+pExceptionObject], rax
0x1800533e6  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x1800533ed  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800533f1  call    _CxxThrowException_0
0x1800533f7  mov     ecx, 38h ; '8'; unsigned __int64
0x1800533fc  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180053401  mov     [rbp+arg_18], rax
0x180053405  test    rax, rax
0x180053408  jz      short loc_18005341A
0x18005340a  lea     rdx, aArrayOfInsuffi; "array of insufficient size to CopyTo"
0x180053411  mov     rcx, rax; this
0x180053414  call    ??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x180053419  nop
0x18005341a  lea     rdx, aVoidCdeclUnbcl_145; "void __cdecl UnBCL::_::HTEnumerator<cla"...
0x180053421  mov     rcx, rax
0x180053424  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180053429  mov     [rbp+pExceptionObject], rax
0x18005342d  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x180053434  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180053438  call    _CxxThrowException_0
```
