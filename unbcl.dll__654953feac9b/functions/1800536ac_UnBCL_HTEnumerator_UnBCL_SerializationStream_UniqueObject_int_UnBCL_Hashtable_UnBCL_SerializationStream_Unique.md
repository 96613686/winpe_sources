# UnBCL::_::HTEnumerator<UnBCL::SerializationStream::UniqueObject,int,UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::TableKey,int,UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::KeyTraits,&UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::RetrieveValue(ATL::CAtlMap<UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::TableKey,int,UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::KeyTraits,ATL::CElementTraits<int>> const *,__POSITION * const &)>::CopyToArray(UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int> const *,UnBCL::Array<int> *,int)

- ea: `0x1800536ac`
- end: `0x180053855`
- name: `?CopyToArray@?$HTEnumerator@UUniqueObject@SerializationStream@UnBCL@@HUTableKey@?$Hashtable@UUniqueObject@SerializationStream@UnBCL@@H@3@HUKeyTraits@53@$1?RetrieveValue@53@KAHPEBV?$CAtlMap@UTableKey@?$Hashtable@UUniqueObject@SerializationStream@UnBCL@@H@UnBCL@@HUKeyTraits@23@V?$CElementTraits@H@ATL@@@ATL@@AEBQEAU__POSITION@@@Z@_@UnBCL@@SAXPEBV?$Hashtable@UUniqueObject@SerializationStream@UnBCL@@H@3@PEAV?$Array@H@3@H@Z`
- size: `425`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x1800530d4`

## callees

- `0x18000225c`
- `0x1800066cc`
- `0x1800098b0`
- `0x1800099b0`
- `0x180009b40`
- `0x180009e7c`
- `0x180036f94`
- `0x1800477d0`
- `0x1800536ac`
- `0x180054618`
- `0x18006f010`

## string_xrefs

- `0x180053793`: `null array to Hashtable#CopyTo`
- `0x1800537da`: `negative start index to CopyTo`
- `0x180053821`: `array of insufficient size to CopyTo`
- `0x1800537a3`: `void __cdecl UnBCL::_::HTEnumerator<struct UnBCL::SerializationStream::UniqueObject,int,struct UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::TableKey,int,struct UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::KeyTraits,&protected: static int __cdecl UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::RetrieveValue(class ATL::CAtlMap<struct UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::TableKey,int,struct `
- `0x1800537ea`: `void __cdecl UnBCL::_::HTEnumerator<struct UnBCL::SerializationStream::UniqueObject,int,struct UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::TableKey,int,struct UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::KeyTraits,&protected: static int __cdecl UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::RetrieveValue(class ATL::CAtlMap<struct UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::TableKey,int,struct `
- `0x180053831`: `void __cdecl UnBCL::_::HTEnumerator<struct UnBCL::SerializationStream::UniqueObject,int,struct UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::TableKey,int,struct UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::KeyTraits,&protected: static int __cdecl UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::RetrieveValue(class ATL::CAtlMap<struct UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::TableKey,int,struct `

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UnBCL::_::HTEnumerator<UnBCL::SerializationStream::UniqueObject,int,UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::TableKey,int,UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::KeyTraits,&protected: static int UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::RetrieveValue(ATL::CAtlMap<UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::TableKey,int,UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::KeyTraits,ATL::CElementTraits<int>> const *,__POSITION * const &)>::CopyToArray(
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
                         "void __cdecl UnBCL::_::HTEnumerator<struct UnBCL::SerializationStream::UniqueObject,int,struct "
                         "UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::TableKey,int,struct UnBC"
                         "L::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::KeyTraits,&protected: static"
                         " int __cdecl UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::RetrieveVal"
                         "ue(class ATL::CAtlMap<struct UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,i"
                         "nt>::TableKey,int,struct UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>:"
                         ":KeyTraits,class ATL::CElementTraits<int> > const *,struct __POSITION * const &)>::CopyToArray("
                         "const class UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int> *,class UnBCL"
                         "::Array<int> *,int)");
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
                         "void __cdecl UnBCL::_::HTEnumerator<struct UnBCL::SerializationStream::UniqueObject,int,struct "
                         "UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::TableKey,int,struct UnBC"
                         "L::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::KeyTraits,&protected: static"
                         " int __cdecl UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::RetrieveVal"
                         "ue(class ATL::CAtlMap<struct UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,i"
                         "nt>::TableKey,int,struct UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>:"
                         ":KeyTraits,class ATL::CElementTraits<int> > const *,struct __POSITION * const &)>::CopyToArray("
                         "const class UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int> *,class UnBCL"
                         "::Array<int> *,int)");
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
                         "void __cdecl UnBCL::_::HTEnumerator<struct UnBCL::SerializationStream::UniqueObject,int,struct "
                         "UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::TableKey,int,struct UnBC"
                         "L::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::KeyTraits,&protected: static"
                         " int __cdecl UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::RetrieveVal"
                         "ue(class ATL::CAtlMap<struct UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,i"
                         "nt>::TableKey,int,struct UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>:"
                         ":KeyTraits,class ATL::CElementTraits<int> > const *,struct __POSITION * const &)>::CopyToArray("
                         "const class UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int> *,class UnBCL"
                         "::Array<int> *,int)");
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
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)a2 + 40LL))(a2, *(unsigned int *)(v9 + 24), v3);
      result = ATL::CAtlMap<UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::TableKey,int,UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::KeyTraits,ATL::CElementTraits<int>>::GetNext(
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
0x1800536ac  push    rbp
0x1800536ae  push    rdi
0x1800536af  push    r14
0x1800536b1  mov     rbp, rsp
0x1800536b4  sub     rsp, 30h
0x1800536b8  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFEh
0x1800536c0  mov     [rsp+30h+arg_0], rbx
0x1800536c5  mov     [rsp+30h+arg_10], rsi
0x1800536ca  mov     edi, r8d
0x1800536cd  mov     rsi, rdx
0x1800536d0  mov     r14, rcx
0x1800536d3  test    rdx, rdx
0x1800536d6  jz      loc_180053780
0x1800536dc  test    r8d, r8d
0x1800536df  js      loc_1800537C7
0x1800536e5  mov     rax, [rcx+8]
0x1800536e9  movsxd  rcx, dword ptr [rax+0Ch]
0x1800536ed  add     rcx, 8
0x1800536f1  add     rcx, r14
0x1800536f4  mov     rax, [rcx]
0x1800536f7  mov     rax, [rax]
0x1800536fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800536ff  mov     ebx, eax
0x180053701  mov     rcx, [rsi]
0x180053704  mov     rax, [rcx]
0x180053707  mov     rcx, rsi
0x18005370a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005370f  sub     eax, edi
0x180053711  cmp     eax, ebx
0x180053713  jl      loc_18005380E
0x180053719  mov     rcx, [r14+28h]
0x18005371d  call    ?GetStartPosition@?$CAtlMap@UTableKey@?$Hashtable@PEAVString@UnBCL@@PEAV12@@UnBCL@@PEAVString@3@UKeyTraits@23@V?$CElementTraits@PEAVString@UnBCL@@@ATL@@@ATL@@QEBAPEAU__POSITION@@XZ; ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::TableKey,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::KeyTraits,ATL::CElementTraits<UnBCL::String *>>::GetStartPosition(void)
0x180053722  mov     rcx, rax
0x180053725  mov     [rbp+pExceptionObject], rax
0x180053729  test    rax, rax
0x18005372c  jz      short loc_180053762
0x18005372e  test    rcx, rcx
0x180053731  jz      short loc_180053775
0x180053733  mov     rax, [rsi]
0x180053736  mov     r8d, edi
0x180053739  mov     edx, [rcx+18h]
0x18005373c  mov     rcx, rsi
0x18005373f  mov     rax, [rax+28h]
0x180053743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053748  lea     rdx, [rbp+pExceptionObject]
0x18005374c  mov     rcx, [r14+28h]
0x180053750  call    ?GetNext@?$CAtlMap@UTableKey@?$Hashtable@UUniqueObject@SerializationStream@UnBCL@@H@UnBCL@@HUKeyTraits@23@V?$CElementTraits@H@ATL@@@ATL@@QEAAPEAVCPair@12@AEAPEAU__POSITION@@@Z; ATL::CAtlMap<UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::TableKey,int,UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::KeyTraits,ATL::CElementTraits<int>>::GetNext(__POSITION * &)
0x180053755  mov     rcx, [rbp+pExceptionObject]
0x180053759  test    rcx, rcx
0x18005375c  jz      short loc_180053762
0x18005375e  inc     edi
0x180053760  jmp     short loc_18005372E
0x180053762  mov     rbx, [rsp+30h+arg_0]
0x180053767  mov     rsi, [rsp+30h+arg_10]
0x18005376c  add     rsp, 30h
0x180053770  pop     r14
0x180053772  pop     rdi
0x180053773  pop     rbp
0x180053774  retn
0x180053775  mov     ecx, 80004005h; int
0x18005377a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180053780  mov     ecx, 38h ; '8'; unsigned __int64
0x180053785  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18005378a  mov     [rbp+arg_18], rax
0x18005378e  test    rax, rax
0x180053791  jz      short loc_1800537A3
0x180053793  lea     rdx, aNullArrayToHas; "null array to Hashtable#CopyTo"
0x18005379a  mov     rcx, rax; this
0x18005379d  call    ??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x1800537a2  nop
0x1800537a3  lea     rdx, aVoidCdeclUnbcl_130; "void __cdecl UnBCL::_::HTEnumerator<str"...
0x1800537aa  mov     rcx, rax
0x1800537ad  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x1800537b2  mov     [rbp+pExceptionObject], rax
0x1800537b6  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x1800537bd  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800537c1  call    _CxxThrowException_0
0x1800537c7  mov     ecx, 38h ; '8'; unsigned __int64
0x1800537cc  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800537d1  mov     [rbp+arg_18], rax
0x1800537d5  test    rax, rax
0x1800537d8  jz      short loc_1800537EA
0x1800537da  lea     rdx, aNegativeStartI; "negative start index to CopyTo"
0x1800537e1  mov     rcx, rax; this
0x1800537e4  call    ??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x1800537e9  nop
0x1800537ea  lea     rdx, aVoidCdeclUnbcl_130; "void __cdecl UnBCL::_::HTEnumerator<str"...
0x1800537f1  mov     rcx, rax
0x1800537f4  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x1800537f9  mov     [rbp+pExceptionObject], rax
0x1800537fd  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x180053804  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180053808  call    _CxxThrowException_0
0x18005380e  mov     ecx, 38h ; '8'; unsigned __int64
0x180053813  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180053818  mov     [rbp+arg_18], rax
0x18005381c  test    rax, rax
0x18005381f  jz      short loc_180053831
0x180053821  lea     rdx, aArrayOfInsuffi; "array of insufficient size to CopyTo"
0x180053828  mov     rcx, rax; this
0x18005382b  call    ??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x180053830  nop
0x180053831  lea     rdx, aVoidCdeclUnbcl_130; "void __cdecl UnBCL::_::HTEnumerator<str"...
0x180053838  mov     rcx, rax
0x18005383b  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180053840  mov     [rbp+pExceptionObject], rax
0x180053844  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x18005384b  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18005384f  call    _CxxThrowException_0
```
