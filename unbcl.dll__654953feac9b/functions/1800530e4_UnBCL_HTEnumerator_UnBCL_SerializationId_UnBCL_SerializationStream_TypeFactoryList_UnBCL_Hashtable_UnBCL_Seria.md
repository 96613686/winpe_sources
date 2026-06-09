# UnBCL::_::HTEnumerator<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *,UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::TableKey,UnBCL::SerializationId *,UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::KeyTraits,&UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::RetrieveKey(ATL::CAtlMap<UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::TableKey,UnBCL::SerializationStream::TypeFactoryList *,UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::KeyTraits,ATL::CElementTraits<UnBCL::SerializationStream::TypeFactoryList *>> const *,__POSITION * const &)>::CopyToArray(UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *> const *,UnBCL::Array<UnBCL::SerializationId *> *,int)

- ea: `0x1800530e4`
- end: `0x18005328e`
- name: `?CopyToArray@?$HTEnumerator@PEAVSerializationId@UnBCL@@PEAVTypeFactoryList@SerializationStream@2@UTableKey@?$Hashtable@PEAVSerializationId@UnBCL@@PEAVTypeFactoryList@SerializationStream@2@@2@PEAV12@UKeyTraits@62@$1?RetrieveKey@62@KAPEAV12@PEBV?$CAtlMap@UTableKey@?$Hashtable@PEAVSerializationId@UnBCL@@PEAVTypeFactoryList@SerializationStream@2@@UnBCL@@PEAVTypeFactoryList@SerializationStream@3@UKeyTraits@23@V?$CElementTraits@PEAVTypeFactoryList@SerializationStream@UnBCL@@@ATL@@@ATL@@AEBQEAU__POSITION@@@Z@_@UnBCL@@SAXPEBV?$Hashtable@PEAVSerializationId@UnBCL@@PEAVTypeFactoryList@SerializationStream@2@@3@PEAV?$Array@PEAVSerializationId@UnBCL@@@3@H@Z`
- size: `426`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180053044`

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
- `0x1800530e4`
- `0x18006f010`

## string_xrefs

- `0x1800531cc`: `null array to Hashtable#CopyTo`
- `0x180053213`: `negative start index to CopyTo`
- `0x18005325a`: `array of insufficient size to CopyTo`
- `0x1800531dc`: `void __cdecl UnBCL::_::HTEnumerator<class UnBCL::SerializationId *,class UnBCL::SerializationStream::TypeFactoryList *,struct UnBCL::Hashtable<class UnBCL::SerializationId *,class UnBCL::SerializationStream::TypeFactoryList *>::TableKey,class UnBCL::SerializationId *,struct UnBCL::Hashtable<class UnBCL::SerializationId *,class UnBCL::SerializationStream::TypeFactoryList *>::KeyTraits,&protected: static class UnBCL::SerializationId * __cdecl UnBCL::Hashtable<class UnBCL::SerializationId *,class U`
- `0x180053223`: `void __cdecl UnBCL::_::HTEnumerator<class UnBCL::SerializationId *,class UnBCL::SerializationStream::TypeFactoryList *,struct UnBCL::Hashtable<class UnBCL::SerializationId *,class UnBCL::SerializationStream::TypeFactoryList *>::TableKey,class UnBCL::SerializationId *,struct UnBCL::Hashtable<class UnBCL::SerializationId *,class UnBCL::SerializationStream::TypeFactoryList *>::KeyTraits,&protected: static class UnBCL::SerializationId * __cdecl UnBCL::Hashtable<class UnBCL::SerializationId *,class U`
- `0x18005326a`: `void __cdecl UnBCL::_::HTEnumerator<class UnBCL::SerializationId *,class UnBCL::SerializationStream::TypeFactoryList *,struct UnBCL::Hashtable<class UnBCL::SerializationId *,class UnBCL::SerializationStream::TypeFactoryList *>::TableKey,class UnBCL::SerializationId *,struct UnBCL::Hashtable<class UnBCL::SerializationId *,class UnBCL::SerializationStream::TypeFactoryList *>::KeyTraits,&protected: static class UnBCL::SerializationId * __cdecl UnBCL::Hashtable<class UnBCL::SerializationId *,class U`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UnBCL::_::HTEnumerator<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *,UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::TableKey,UnBCL::SerializationId *,UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::KeyTraits,&protected: static UnBCL::SerializationId * UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::RetrieveKey(ATL::CAtlMap<UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::TableKey,UnBCL::SerializationStream::TypeFactoryList *,UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::KeyTraits,ATL::CElementTraits<UnBCL::SerializationStream::TypeFactoryList *>> const *,__POSITION * const &)>::CopyToArray(
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
                         "ializationStream::TypeFactoryList *>::TableKey,class UnBCL::SerializationId *,struct UnBCL::Has"
                         "htable<class UnBCL::SerializationId *,class UnBCL::SerializationStream::TypeFactoryList *>::Key"
                         "Traits,&protected: static class UnBCL::SerializationId * __cdecl UnBCL::Hashtable<class UnBCL::"
                         "SerializationId *,class UnBCL::SerializationStream::TypeFactoryList *>::RetrieveKey(class ATL::"
                         "CAtlMap<struct UnBCL::Hashtable<class UnBCL::SerializationId *,class UnBCL::SerializationStream"
                         "::TypeFactoryList *>::TableKey,class UnBCL::SerializationStream::TypeFactoryList *,struct UnBCL"
                         "::Hashtable<class UnBCL::SerializationId *,class UnBCL::SerializationStream::TypeFactoryList *>"
                         "::KeyTraits,class ATL::CElementTraits<class UnBCL::SerializationStream::TypeFactoryList *> > co"
                         "nst *,struct __POSITION * const &)>::CopyToArray(const class UnBCL::Hashtable<class UnBCL::Seri"
                         "alizationId *,class UnBCL::SerializationStream::TypeFactoryList *> *,class UnBCL::Array<class U"
                         "nBCL::SerializationId *> *,int)");
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
                         "ializationStream::TypeFactoryList *>::TableKey,class UnBCL::SerializationId *,struct UnBCL::Has"
                         "htable<class UnBCL::SerializationId *,class UnBCL::SerializationStream::TypeFactoryList *>::Key"
                         "Traits,&protected: static class UnBCL::SerializationId * __cdecl UnBCL::Hashtable<class UnBCL::"
                         "SerializationId *,class UnBCL::SerializationStream::TypeFactoryList *>::RetrieveKey(class ATL::"
                         "CAtlMap<struct UnBCL::Hashtable<class UnBCL::SerializationId *,class UnBCL::SerializationStream"
                         "::TypeFactoryList *>::TableKey,class UnBCL::SerializationStream::TypeFactoryList *,struct UnBCL"
                         "::Hashtable<class UnBCL::SerializationId *,class UnBCL::SerializationStream::TypeFactoryList *>"
                         "::KeyTraits,class ATL::CElementTraits<class UnBCL::SerializationStream::TypeFactoryList *> > co"
                         "nst *,struct __POSITION * const &)>::CopyToArray(const class UnBCL::Hashtable<class UnBCL::Seri"
                         "alizationId *,class UnBCL::SerializationStream::TypeFactoryList *> *,class UnBCL::Array<class U"
                         "nBCL::SerializationId *> *,int)");
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
                         "ializationStream::TypeFactoryList *>::TableKey,class UnBCL::SerializationId *,struct UnBCL::Has"
                         "htable<class UnBCL::SerializationId *,class UnBCL::SerializationStream::TypeFactoryList *>::Key"
                         "Traits,&protected: static class UnBCL::SerializationId * __cdecl UnBCL::Hashtable<class UnBCL::"
                         "SerializationId *,class UnBCL::SerializationStream::TypeFactoryList *>::RetrieveKey(class ATL::"
                         "CAtlMap<struct UnBCL::Hashtable<class UnBCL::SerializationId *,class UnBCL::SerializationStream"
                         "::TypeFactoryList *>::TableKey,class UnBCL::SerializationStream::TypeFactoryList *,struct UnBCL"
                         "::Hashtable<class UnBCL::SerializationId *,class UnBCL::SerializationStream::TypeFactoryList *>"
                         "::KeyTraits,class ATL::CElementTraits<class UnBCL::SerializationStream::TypeFactoryList *> > co"
                         "nst *,struct __POSITION * const &)>::CopyToArray(const class UnBCL::Hashtable<class UnBCL::Seri"
                         "alizationId *,class UnBCL::SerializationStream::TypeFactoryList *> *,class UnBCL::Array<class U"
                         "nBCL::SerializationId *> *,int)");
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
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)a2 + 40LL))(a2, *(_QWORD *)(v9 + 8), v3);
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
0x1800530e4  push    rbp
0x1800530e6  push    rdi
0x1800530e7  push    r14
0x1800530e9  mov     rbp, rsp
0x1800530ec  sub     rsp, 30h
0x1800530f0  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFEh
0x1800530f8  mov     [rsp+30h+arg_0], rbx
0x1800530fd  mov     [rsp+30h+arg_10], rsi
0x180053102  mov     edi, r8d
0x180053105  mov     rsi, rdx
0x180053108  mov     r14, rcx
0x18005310b  test    rdx, rdx
0x18005310e  jz      loc_1800531B9
0x180053114  test    r8d, r8d
0x180053117  js      loc_180053200
0x18005311d  mov     rax, [rcx+8]
0x180053121  movsxd  rcx, dword ptr [rax+0Ch]
0x180053125  add     rcx, 8
0x180053129  add     rcx, r14
0x18005312c  mov     rax, [rcx]
0x18005312f  mov     rax, [rax]
0x180053132  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053137  mov     ebx, eax
0x180053139  mov     rcx, [rsi]
0x18005313c  mov     rax, [rcx]
0x18005313f  mov     rcx, rsi
0x180053142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053147  sub     eax, edi
0x180053149  cmp     eax, ebx
0x18005314b  jl      loc_180053247
0x180053151  mov     rcx, [r14+28h]
0x180053155  call    ?GetStartPosition@?$CAtlMap@UTableKey@?$Hashtable@PEAVString@UnBCL@@PEAV12@@UnBCL@@PEAVString@3@UKeyTraits@23@V?$CElementTraits@PEAVString@UnBCL@@@ATL@@@ATL@@QEBAPEAU__POSITION@@XZ; ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::TableKey,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::KeyTraits,ATL::CElementTraits<UnBCL::String *>>::GetStartPosition(void)
0x18005315a  mov     rcx, rax
0x18005315d  mov     [rbp+pExceptionObject], rax
0x180053161  test    rax, rax
0x180053164  jz      short loc_18005319B
0x180053166  test    rcx, rcx
0x180053169  jz      short loc_1800531AE
0x18005316b  mov     rax, [rsi]
0x18005316e  mov     r8d, edi
0x180053171  mov     rdx, [rcx+8]
0x180053175  mov     rcx, rsi
0x180053178  mov     rax, [rax+28h]
0x18005317c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053181  lea     rdx, [rbp+pExceptionObject]
0x180053185  mov     rcx, [r14+28h]
0x180053189  call    ?GetNext@?$CAtlMap@UTableKey@?$Hashtable@PEAVSerializationId@UnBCL@@PEAVTypeFactoryList@SerializationStream@2@@UnBCL@@PEAVTypeFactoryList@SerializationStream@3@UKeyTraits@23@V?$CElementTraits@PEAVTypeFactoryList@SerializationStream@UnBCL@@@ATL@@@ATL@@QEAAPEAVCPair@12@AEAPEAU__POSITION@@@Z; ATL::CAtlMap<UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::TableKey,UnBCL::SerializationStream::TypeFactoryList *,UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::KeyTraits,ATL::CElementTraits<UnBCL::SerializationStream::TypeFactoryList *>>::GetNext(__POSITION * &)
0x18005318e  mov     rcx, [rbp+pExceptionObject]
0x180053192  test    rcx, rcx
0x180053195  jz      short loc_18005319B
0x180053197  inc     edi
0x180053199  jmp     short loc_180053166
0x18005319b  mov     rbx, [rsp+30h+arg_0]
0x1800531a0  mov     rsi, [rsp+30h+arg_10]
0x1800531a5  add     rsp, 30h
0x1800531a9  pop     r14
0x1800531ab  pop     rdi
0x1800531ac  pop     rbp
0x1800531ad  retn
0x1800531ae  mov     ecx, 80004005h; int
0x1800531b3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800531b9  mov     ecx, 38h ; '8'; unsigned __int64
0x1800531be  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800531c3  mov     [rbp+arg_18], rax
0x1800531c7  test    rax, rax
0x1800531ca  jz      short loc_1800531DC
0x1800531cc  lea     rdx, aNullArrayToHas; "null array to Hashtable#CopyTo"
0x1800531d3  mov     rcx, rax; this
0x1800531d6  call    ??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x1800531db  nop
0x1800531dc  lea     rdx, aVoidCdeclUnbcl_60; "void __cdecl UnBCL::_::HTEnumerator<cla"...
0x1800531e3  mov     rcx, rax
0x1800531e6  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x1800531eb  mov     [rbp+pExceptionObject], rax
0x1800531ef  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x1800531f6  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800531fa  call    _CxxThrowException_0
0x180053200  mov     ecx, 38h ; '8'; unsigned __int64
0x180053205  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18005320a  mov     [rbp+arg_18], rax
0x18005320e  test    rax, rax
0x180053211  jz      short loc_180053223
0x180053213  lea     rdx, aNegativeStartI; "negative start index to CopyTo"
0x18005321a  mov     rcx, rax; this
0x18005321d  call    ??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x180053222  nop
0x180053223  lea     rdx, aVoidCdeclUnbcl_60; "void __cdecl UnBCL::_::HTEnumerator<cla"...
0x18005322a  mov     rcx, rax
0x18005322d  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180053232  mov     [rbp+pExceptionObject], rax
0x180053236  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x18005323d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180053241  call    _CxxThrowException_0
0x180053247  mov     ecx, 38h ; '8'; unsigned __int64
0x18005324c  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180053251  mov     [rbp+arg_18], rax
0x180053255  test    rax, rax
0x180053258  jz      short loc_18005326A
0x18005325a  lea     rdx, aArrayOfInsuffi; "array of insufficient size to CopyTo"
0x180053261  mov     rcx, rax; this
0x180053264  call    ??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x180053269  nop
0x18005326a  lea     rdx, aVoidCdeclUnbcl_60; "void __cdecl UnBCL::_::HTEnumerator<cla"...
0x180053271  mov     rcx, rax
0x180053274  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180053279  mov     [rbp+pExceptionObject], rax
0x18005327d  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x180053284  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180053288  call    _CxxThrowException_0
```
