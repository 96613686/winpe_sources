# UnBCL::_::HTEnumerator<UnBCL::SerializationStream::UniqueObject,int,UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::TableKey,UnBCL::SerializationStream::UniqueObject,UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::KeyTraits,&UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::RetrieveKey(ATL::CAtlMap<UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::TableKey,int,UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::KeyTraits,ATL::CElementTraits<int>> const *,__POSITION * const &)>::CopyToArray(UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int> const *,UnBCL::Array<UnBCL::SerializationStream::UniqueObject> *,int)

- ea: `0x18005385c`
- end: `0x180053a0c`
- name: `?CopyToArray@?$HTEnumerator@UUniqueObject@SerializationStream@UnBCL@@HUTableKey@?$Hashtable@UUniqueObject@SerializationStream@UnBCL@@H@3@U123@UKeyTraits@53@$1?RetrieveKey@53@KA?AU123@PEBV?$CAtlMap@UTableKey@?$Hashtable@UUniqueObject@SerializationStream@UnBCL@@H@UnBCL@@HUKeyTraits@23@V?$CElementTraits@H@ATL@@@ATL@@AEBQEAU__POSITION@@@Z@_@UnBCL@@SAXPEBV?$Hashtable@UUniqueObject@SerializationStream@UnBCL@@H@3@PEAV?$Array@UUniqueObject@SerializationStream@UnBCL@@@3@H@Z`
- size: `432`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180053074`

## callees

- `0x18000225c`
- `0x1800066cc`
- `0x1800098b0`
- `0x1800099b0`
- `0x180009b40`
- `0x180009e7c`
- `0x180036f94`
- `0x1800477d0`
- `0x18005385c`
- `0x180054618`
- `0x18006f010`

## string_xrefs

- `0x18005394a`: `null array to Hashtable#CopyTo`
- `0x180053991`: `negative start index to CopyTo`
- `0x1800539d8`: `array of insufficient size to CopyTo`
- `0x18005395a`: `void __cdecl UnBCL::_::HTEnumerator<struct UnBCL::SerializationStream::UniqueObject,int,struct UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::TableKey,struct UnBCL::SerializationStream::UniqueObject,struct UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::KeyTraits,&protected: static struct UnBCL::SerializationStream::UniqueObject __cdecl UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::RetrieveKey(class ATL::CAtlMap<struct UnBCL`
- `0x1800539a1`: `void __cdecl UnBCL::_::HTEnumerator<struct UnBCL::SerializationStream::UniqueObject,int,struct UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::TableKey,struct UnBCL::SerializationStream::UniqueObject,struct UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::KeyTraits,&protected: static struct UnBCL::SerializationStream::UniqueObject __cdecl UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::RetrieveKey(class ATL::CAtlMap<struct UnBCL`
- `0x1800539e8`: `void __cdecl UnBCL::_::HTEnumerator<struct UnBCL::SerializationStream::UniqueObject,int,struct UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::TableKey,struct UnBCL::SerializationStream::UniqueObject,struct UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::KeyTraits,&protected: static struct UnBCL::SerializationStream::UniqueObject __cdecl UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::RetrieveKey(class ATL::CAtlMap<struct UnBCL`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UnBCL::_::HTEnumerator<UnBCL::SerializationStream::UniqueObject,int,UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::TableKey,UnBCL::SerializationStream::UniqueObject,UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::KeyTraits,&protected: static UnBCL::SerializationStream::UniqueObject UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::RetrieveKey(ATL::CAtlMap<UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::TableKey,int,UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::KeyTraits,ATL::CElementTraits<int>> const *,__POSITION * const &)>::CopyToArray(
        __int64 a1,
        __int64 a2,
        int a3)
{
  unsigned int v3; // edi
  __int64 (__fastcall ***v6)(_QWORD); // rcx
  signed int v7; // ebx
  __int64 result; // rax
  UnBCL::ArgumentNullException *v9; // rax
  UnBCL::ArgumentOutOfRangeException *v10; // rax
  UnBCL::ArgumentException *v11; // rax
  __int128 v12; // [rsp+30h] [rbp-10h] BYREF
  __int64 pExceptionObject; // [rsp+68h] [rbp+28h] BYREF
  UnBCL::ArgumentNullException *v14; // [rsp+78h] [rbp+38h]

  v3 = a3;
  if ( !a2 )
  {
    v9 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v14 = v9;
    if ( v9 )
      v9 = (UnBCL::ArgumentNullException *)UnBCL::ArgumentNullException::ArgumentNullException(
                                             v9,
                                             L"null array to Hashtable#CopyTo");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v9,
                         "void __cdecl UnBCL::_::HTEnumerator<struct UnBCL::SerializationStream::UniqueObject,int,struct "
                         "UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::TableKey,struct UnBCL::S"
                         "erializationStream::UniqueObject,struct UnBCL::Hashtable<struct UnBCL::SerializationStream::Uni"
                         "queObject,int>::KeyTraits,&protected: static struct UnBCL::SerializationStream::UniqueObject __"
                         "cdecl UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::RetrieveKey(class "
                         "ATL::CAtlMap<struct UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::Tabl"
                         "eKey,int,struct UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::KeyTrait"
                         "s,class ATL::CElementTraits<int> > const *,struct __POSITION * const &)>::CopyToArray(const cla"
                         "ss UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int> *,class UnBCL::Array<s"
                         "truct UnBCL::SerializationStream::UniqueObject> *,int)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  if ( a3 < 0 )
  {
    v10 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::Object::operator new(0x38u);
    v14 = v10;
    if ( v10 )
      v10 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(
                                                    v10,
                                                    L"negative start index to CopyTo");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v10,
                         "void __cdecl UnBCL::_::HTEnumerator<struct UnBCL::SerializationStream::UniqueObject,int,struct "
                         "UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::TableKey,struct UnBCL::S"
                         "erializationStream::UniqueObject,struct UnBCL::Hashtable<struct UnBCL::SerializationStream::Uni"
                         "queObject,int>::KeyTraits,&protected: static struct UnBCL::SerializationStream::UniqueObject __"
                         "cdecl UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::RetrieveKey(class "
                         "ATL::CAtlMap<struct UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::Tabl"
                         "eKey,int,struct UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::KeyTrait"
                         "s,class ATL::CElementTraits<int> > const *,struct __POSITION * const &)>::CopyToArray(const cla"
                         "ss UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int> *,class UnBCL::Array<s"
                         "truct UnBCL::SerializationStream::UniqueObject> *,int)");
    throw (UnBCL::ArgumentOutOfRangeException **)&pExceptionObject;
  }
  v6 = (__int64 (__fastcall ***)(_QWORD))(a1 + *(int *)(*(_QWORD *)(a1 + 8) + 12LL) + 8LL);
  v7 = (**v6)(v6);
  if ( (int)((**(__int64 (__fastcall ***)(__int64))a2)(a2) - v3) < v7 )
  {
    v11 = (UnBCL::ArgumentException *)UnBCL::Object::operator new(0x38u);
    v14 = v11;
    if ( v11 )
      v11 = (UnBCL::ArgumentException *)UnBCL::ArgumentException::ArgumentException(
                                          v11,
                                          L"array of insufficient size to CopyTo");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v11,
                         "void __cdecl UnBCL::_::HTEnumerator<struct UnBCL::SerializationStream::UniqueObject,int,struct "
                         "UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::TableKey,struct UnBCL::S"
                         "erializationStream::UniqueObject,struct UnBCL::Hashtable<struct UnBCL::SerializationStream::Uni"
                         "queObject,int>::KeyTraits,&protected: static struct UnBCL::SerializationStream::UniqueObject __"
                         "cdecl UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::RetrieveKey(class "
                         "ATL::CAtlMap<struct UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::Tabl"
                         "eKey,int,struct UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::KeyTrait"
                         "s,class ATL::CElementTraits<int> > const *,struct __POSITION * const &)>::CopyToArray(const cla"
                         "ss UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int> *,class UnBCL::Array<s"
                         "truct UnBCL::SerializationStream::UniqueObject> *,int)");
    throw (UnBCL::ArgumentException **)&pExceptionObject;
  }
  result = ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::TableKey,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::KeyTraits,ATL::CElementTraits<UnBCL::String *>>::GetStartPosition(*(_QWORD *)(a1 + 40));
  pExceptionObject = result;
  if ( result )
  {
    while ( 1 )
    {
      if ( !result )
        ATL::AtlThrowImpl(-2147467259);
      v12 = *(_OWORD *)(result + 8);
      (*(void (__fastcall **)(__int64, __int128 *, _QWORD))(*(_QWORD *)a2 + 40LL))(a2, &v12, v3);
      ATL::CAtlMap<UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::TableKey,int,UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::KeyTraits,ATL::CElementTraits<int>>::GetNext(
        *(_QWORD *)(a1 + 40),
        &pExceptionObject);
      result = pExceptionObject;
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
0x18005385c  push    rbp
0x18005385e  push    rdi
0x18005385f  push    r14
0x180053861  mov     rbp, rsp
0x180053864  sub     rsp, 40h
0x180053868  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFEh
0x180053870  mov     [rsp+40h+arg_0], rbx
0x180053875  mov     [rsp+40h+arg_10], rsi
0x18005387a  mov     edi, r8d
0x18005387d  mov     rsi, rdx
0x180053880  mov     r14, rcx
0x180053883  test    rdx, rdx
0x180053886  jz      loc_180053937
0x18005388c  test    r8d, r8d
0x18005388f  js      loc_18005397E
0x180053895  mov     rax, [rcx+8]
0x180053899  movsxd  rcx, dword ptr [rax+0Ch]
0x18005389d  add     rcx, 8
0x1800538a1  add     rcx, r14
0x1800538a4  mov     rax, [rcx]
0x1800538a7  mov     rax, [rax]
0x1800538aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800538af  mov     ebx, eax
0x1800538b1  mov     rcx, [rsi]
0x1800538b4  mov     rax, [rcx]
0x1800538b7  mov     rcx, rsi
0x1800538ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800538bf  sub     eax, edi
0x1800538c1  cmp     eax, ebx
0x1800538c3  jl      loc_1800539C5
0x1800538c9  mov     rcx, [r14+28h]
0x1800538cd  call    ?GetStartPosition@?$CAtlMap@UTableKey@?$Hashtable@PEAVString@UnBCL@@PEAV12@@UnBCL@@PEAVString@3@UKeyTraits@23@V?$CElementTraits@PEAVString@UnBCL@@@ATL@@@ATL@@QEBAPEAU__POSITION@@XZ; ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::TableKey,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::KeyTraits,ATL::CElementTraits<UnBCL::String *>>::GetStartPosition(void)
0x1800538d2  mov     [rbp+pExceptionObject], rax
0x1800538d6  test    rax, rax
0x1800538d9  jz      short loc_180053919
0x1800538db  test    rax, rax
0x1800538de  jz      short loc_18005392C
0x1800538e0  movups  xmm0, xmmword ptr [rax+8]
0x1800538e4  movdqu  [rbp+var_10], xmm0
0x1800538e9  mov     rax, [rsi]
0x1800538ec  mov     r8d, edi
0x1800538ef  lea     rdx, [rbp+var_10]
0x1800538f3  mov     rcx, rsi
0x1800538f6  mov     rax, [rax+28h]
0x1800538fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800538ff  lea     rdx, [rbp+pExceptionObject]
0x180053903  mov     rcx, [r14+28h]
0x180053907  call    ?GetNext@?$CAtlMap@UTableKey@?$Hashtable@UUniqueObject@SerializationStream@UnBCL@@H@UnBCL@@HUKeyTraits@23@V?$CElementTraits@H@ATL@@@ATL@@QEAAPEAVCPair@12@AEAPEAU__POSITION@@@Z; ATL::CAtlMap<UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::TableKey,int,UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::KeyTraits,ATL::CElementTraits<int>>::GetNext(__POSITION * &)
0x18005390c  mov     rax, [rbp+pExceptionObject]
0x180053910  test    rax, rax
0x180053913  jz      short loc_180053919
0x180053915  inc     edi
0x180053917  jmp     short loc_1800538DB
0x180053919  mov     rbx, [rsp+40h+arg_0]
0x18005391e  mov     rsi, [rsp+40h+arg_10]
0x180053923  add     rsp, 40h
0x180053927  pop     r14
0x180053929  pop     rdi
0x18005392a  pop     rbp
0x18005392b  retn
0x18005392c  mov     ecx, 80004005h; int
0x180053931  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180053937  mov     ecx, 38h ; '8'; unsigned __int64
0x18005393c  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180053941  mov     [rbp+arg_18], rax
0x180053945  test    rax, rax
0x180053948  jz      short loc_18005395A
0x18005394a  lea     rdx, aNullArrayToHas; "null array to Hashtable#CopyTo"
0x180053951  mov     rcx, rax; this
0x180053954  call    ??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x180053959  nop
0x18005395a  lea     rdx, aVoidCdeclUnbcl_44; "void __cdecl UnBCL::_::HTEnumerator<str"...
0x180053961  mov     rcx, rax
0x180053964  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180053969  mov     [rbp+pExceptionObject], rax
0x18005396d  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x180053974  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180053978  call    _CxxThrowException_0
0x18005397e  mov     ecx, 38h ; '8'; unsigned __int64
0x180053983  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180053988  mov     [rbp+arg_18], rax
0x18005398c  test    rax, rax
0x18005398f  jz      short loc_1800539A1
0x180053991  lea     rdx, aNegativeStartI; "negative start index to CopyTo"
0x180053998  mov     rcx, rax; this
0x18005399b  call    ??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x1800539a0  nop
0x1800539a1  lea     rdx, aVoidCdeclUnbcl_44; "void __cdecl UnBCL::_::HTEnumerator<str"...
0x1800539a8  mov     rcx, rax
0x1800539ab  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x1800539b0  mov     [rbp+pExceptionObject], rax
0x1800539b4  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x1800539bb  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800539bf  call    _CxxThrowException_0
0x1800539c5  mov     ecx, 38h ; '8'; unsigned __int64
0x1800539ca  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800539cf  mov     [rbp+arg_18], rax
0x1800539d3  test    rax, rax
0x1800539d6  jz      short loc_1800539E8
0x1800539d8  lea     rdx, aArrayOfInsuffi; "array of insufficient size to CopyTo"
0x1800539df  mov     rcx, rax; this
0x1800539e2  call    ??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x1800539e7  nop
0x1800539e8  lea     rdx, aVoidCdeclUnbcl_44; "void __cdecl UnBCL::_::HTEnumerator<str"...
0x1800539ef  mov     rcx, rax
0x1800539f2  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x1800539f7  mov     [rbp+pExceptionObject], rax
0x1800539fb  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x180053a02  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180053a06  call    _CxxThrowException_0
```
