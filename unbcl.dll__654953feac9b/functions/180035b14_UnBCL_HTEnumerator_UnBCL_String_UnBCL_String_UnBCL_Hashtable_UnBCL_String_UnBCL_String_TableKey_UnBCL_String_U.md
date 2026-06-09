# UnBCL::_::HTEnumerator<UnBCL::String *,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::TableKey,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::KeyTraits,&UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::RetrieveKey(ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::TableKey,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::KeyTraits,ATL::CElementTraits<UnBCL::String *>> const *,__POSITION * const &)>::CopyToArray(UnBCL::Hashtable<UnBCL::String *,UnBCL::String *> const *,UnBCL::Array<UnBCL::String *> *,int)

- ea: `0x180035b14`
- end: `0x180035cbe`
- name: `?CopyToArray@?$HTEnumerator@PEAVString@UnBCL@@PEAV12@UTableKey@?$Hashtable@PEAVString@UnBCL@@PEAV12@@2@PEAV12@UKeyTraits@42@$1?RetrieveKey@42@KAPEAV12@PEBV?$CAtlMap@UTableKey@?$Hashtable@PEAVString@UnBCL@@PEAV12@@UnBCL@@PEAVString@3@UKeyTraits@23@V?$CElementTraits@PEAVString@UnBCL@@@ATL@@@ATL@@AEBQEAU__POSITION@@@Z@_@UnBCL@@SAXPEBV?$Hashtable@PEAVString@UnBCL@@PEAV12@@3@PEAV?$Array@PEAVString@UnBCL@@@3@H@Z`
- size: `426`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180035ad4`

## callees

- `0x18000225c`
- `0x1800066cc`
- `0x1800098b0`
- `0x1800099b0`
- `0x180009b40`
- `0x180009e7c`
- `0x180035b14`
- `0x180036ba0`
- `0x180036f94`
- `0x1800477d0`
- `0x18006f010`

## string_xrefs

- `0x180035bfc`: `null array to Hashtable#CopyTo`
- `0x180035c43`: `negative start index to CopyTo`
- `0x180035c8a`: `array of insufficient size to CopyTo`
- `0x180035c0c`: `void __cdecl UnBCL::_::HTEnumerator<class UnBCL::String *,class UnBCL::String *,struct UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>::TableKey,class UnBCL::String *,struct UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>::KeyTraits,&protected: static class UnBCL::String * __cdecl UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>::RetrieveKey(class ATL::CAtlMap<struct UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>::TableKey,class UnBCL::Stri`
- `0x180035c53`: `void __cdecl UnBCL::_::HTEnumerator<class UnBCL::String *,class UnBCL::String *,struct UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>::TableKey,class UnBCL::String *,struct UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>::KeyTraits,&protected: static class UnBCL::String * __cdecl UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>::RetrieveKey(class ATL::CAtlMap<struct UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>::TableKey,class UnBCL::Stri`
- `0x180035c9a`: `void __cdecl UnBCL::_::HTEnumerator<class UnBCL::String *,class UnBCL::String *,struct UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>::TableKey,class UnBCL::String *,struct UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>::KeyTraits,&protected: static class UnBCL::String * __cdecl UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>::RetrieveKey(class ATL::CAtlMap<struct UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>::TableKey,class UnBCL::Stri`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UnBCL::_::HTEnumerator<UnBCL::String *,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::TableKey,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::KeyTraits,&protected: static UnBCL::String * UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::RetrieveKey(ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::TableKey,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::KeyTraits,ATL::CElementTraits<UnBCL::String *>> const *,__POSITION * const &)>::CopyToArray(
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
                         "void __cdecl UnBCL::_::HTEnumerator<class UnBCL::String *,class UnBCL::String *,struct UnBCL::H"
                         "ashtable<class UnBCL::String *,class UnBCL::String *>::TableKey,class UnBCL::String *,struct Un"
                         "BCL::Hashtable<class UnBCL::String *,class UnBCL::String *>::KeyTraits,&protected: static class"
                         " UnBCL::String * __cdecl UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>::Retriev"
                         "eKey(class ATL::CAtlMap<struct UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>::T"
                         "ableKey,class UnBCL::String *,struct UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String"
                         " *>::KeyTraits,class ATL::CElementTraits<class UnBCL::String *> > const *,struct __POSITION * c"
                         "onst &)>::CopyToArray(const class UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>"
                         " *,class UnBCL::Array<class UnBCL::String *> *,int)");
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
                         "void __cdecl UnBCL::_::HTEnumerator<class UnBCL::String *,class UnBCL::String *,struct UnBCL::H"
                         "ashtable<class UnBCL::String *,class UnBCL::String *>::TableKey,class UnBCL::String *,struct Un"
                         "BCL::Hashtable<class UnBCL::String *,class UnBCL::String *>::KeyTraits,&protected: static class"
                         " UnBCL::String * __cdecl UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>::Retriev"
                         "eKey(class ATL::CAtlMap<struct UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>::T"
                         "ableKey,class UnBCL::String *,struct UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String"
                         " *>::KeyTraits,class ATL::CElementTraits<class UnBCL::String *> > const *,struct __POSITION * c"
                         "onst &)>::CopyToArray(const class UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>"
                         " *,class UnBCL::Array<class UnBCL::String *> *,int)");
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
                         "void __cdecl UnBCL::_::HTEnumerator<class UnBCL::String *,class UnBCL::String *,struct UnBCL::H"
                         "ashtable<class UnBCL::String *,class UnBCL::String *>::TableKey,class UnBCL::String *,struct Un"
                         "BCL::Hashtable<class UnBCL::String *,class UnBCL::String *>::KeyTraits,&protected: static class"
                         " UnBCL::String * __cdecl UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>::Retriev"
                         "eKey(class ATL::CAtlMap<struct UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>::T"
                         "ableKey,class UnBCL::String *,struct UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String"
                         " *>::KeyTraits,class ATL::CElementTraits<class UnBCL::String *> > const *,struct __POSITION * c"
                         "onst &)>::CopyToArray(const class UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>"
                         " *,class UnBCL::Array<class UnBCL::String *> *,int)");
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
0x180035b14  push    rbp
0x180035b16  push    rdi
0x180035b17  push    r14
0x180035b19  mov     rbp, rsp
0x180035b1c  sub     rsp, 30h
0x180035b20  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFEh
0x180035b28  mov     [rsp+30h+arg_0], rbx
0x180035b2d  mov     [rsp+30h+arg_10], rsi
0x180035b32  mov     edi, r8d
0x180035b35  mov     rsi, rdx
0x180035b38  mov     r14, rcx
0x180035b3b  test    rdx, rdx
0x180035b3e  jz      loc_180035BE9
0x180035b44  test    r8d, r8d
0x180035b47  js      loc_180035C30
0x180035b4d  mov     rax, [rcx+8]
0x180035b51  movsxd  rcx, dword ptr [rax+0Ch]
0x180035b55  add     rcx, 8
0x180035b59  add     rcx, r14
0x180035b5c  mov     rax, [rcx]
0x180035b5f  mov     rax, [rax]
0x180035b62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035b67  mov     ebx, eax
0x180035b69  mov     rcx, [rsi]
0x180035b6c  mov     rax, [rcx]
0x180035b6f  mov     rcx, rsi
0x180035b72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035b77  sub     eax, edi
0x180035b79  cmp     eax, ebx
0x180035b7b  jl      loc_180035C77
0x180035b81  mov     rcx, [r14+28h]
0x180035b85  call    ?GetStartPosition@?$CAtlMap@UTableKey@?$Hashtable@PEAVString@UnBCL@@PEAV12@@UnBCL@@PEAVString@3@UKeyTraits@23@V?$CElementTraits@PEAVString@UnBCL@@@ATL@@@ATL@@QEBAPEAU__POSITION@@XZ; ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::TableKey,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::KeyTraits,ATL::CElementTraits<UnBCL::String *>>::GetStartPosition(void)
0x180035b8a  mov     rcx, rax
0x180035b8d  mov     [rbp+pExceptionObject], rax
0x180035b91  test    rax, rax
0x180035b94  jz      short loc_180035BCB
0x180035b96  test    rcx, rcx
0x180035b99  jz      short loc_180035BDE
0x180035b9b  mov     rax, [rsi]
0x180035b9e  mov     r8d, edi
0x180035ba1  mov     rdx, [rcx+8]
0x180035ba5  mov     rcx, rsi
0x180035ba8  mov     rax, [rax+28h]
0x180035bac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035bb1  lea     rdx, [rbp+pExceptionObject]
0x180035bb5  mov     rcx, [r14+28h]
0x180035bb9  call    ?GetNext@?$CAtlMap@UTableKey@?$Hashtable@PEAVSerializationId@UnBCL@@PEAVTypeFactoryList@SerializationStream@2@@UnBCL@@PEAVTypeFactoryList@SerializationStream@3@UKeyTraits@23@V?$CElementTraits@PEAVTypeFactoryList@SerializationStream@UnBCL@@@ATL@@@ATL@@QEAAPEAVCPair@12@AEAPEAU__POSITION@@@Z; ATL::CAtlMap<UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::TableKey,UnBCL::SerializationStream::TypeFactoryList *,UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::KeyTraits,ATL::CElementTraits<UnBCL::SerializationStream::TypeFactoryList *>>::GetNext(__POSITION * &)
0x180035bbe  mov     rcx, [rbp+pExceptionObject]
0x180035bc2  test    rcx, rcx
0x180035bc5  jz      short loc_180035BCB
0x180035bc7  inc     edi
0x180035bc9  jmp     short loc_180035B96
0x180035bcb  mov     rbx, [rsp+30h+arg_0]
0x180035bd0  mov     rsi, [rsp+30h+arg_10]
0x180035bd5  add     rsp, 30h
0x180035bd9  pop     r14
0x180035bdb  pop     rdi
0x180035bdc  pop     rbp
0x180035bdd  retn
0x180035bde  mov     ecx, 80004005h; int
0x180035be3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180035be9  mov     ecx, 38h ; '8'; unsigned __int64
0x180035bee  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180035bf3  mov     [rbp+arg_18], rax
0x180035bf7  test    rax, rax
0x180035bfa  jz      short loc_180035C0C
0x180035bfc  lea     rdx, aNullArrayToHas; "null array to Hashtable#CopyTo"
0x180035c03  mov     rcx, rax; this
0x180035c06  call    ??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x180035c0b  nop
0x180035c0c  lea     rdx, aVoidCdeclUnbcl_154; "void __cdecl UnBCL::_::HTEnumerator<cla"...
0x180035c13  mov     rcx, rax
0x180035c16  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180035c1b  mov     [rbp+pExceptionObject], rax
0x180035c1f  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x180035c26  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180035c2a  call    _CxxThrowException_0
0x180035c30  mov     ecx, 38h ; '8'; unsigned __int64
0x180035c35  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180035c3a  mov     [rbp+arg_18], rax
0x180035c3e  test    rax, rax
0x180035c41  jz      short loc_180035C53
0x180035c43  lea     rdx, aNegativeStartI; "negative start index to CopyTo"
0x180035c4a  mov     rcx, rax; this
0x180035c4d  call    ??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x180035c52  nop
0x180035c53  lea     rdx, aVoidCdeclUnbcl_154; "void __cdecl UnBCL::_::HTEnumerator<cla"...
0x180035c5a  mov     rcx, rax
0x180035c5d  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180035c62  mov     [rbp+pExceptionObject], rax
0x180035c66  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x180035c6d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180035c71  call    _CxxThrowException_0
0x180035c77  mov     ecx, 38h ; '8'; unsigned __int64
0x180035c7c  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180035c81  mov     [rbp+arg_18], rax
0x180035c85  test    rax, rax
0x180035c88  jz      short loc_180035C9A
0x180035c8a  lea     rdx, aArrayOfInsuffi; "array of insufficient size to CopyTo"
0x180035c91  mov     rcx, rax; this
0x180035c94  call    ??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x180035c99  nop
0x180035c9a  lea     rdx, aVoidCdeclUnbcl_154; "void __cdecl UnBCL::_::HTEnumerator<cla"...
0x180035ca1  mov     rcx, rax
0x180035ca4  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180035ca9  mov     [rbp+pExceptionObject], rax
0x180035cad  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x180035cb4  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180035cb8  call    _CxxThrowException_0
```
