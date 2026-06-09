# UnBCL::_::HTEnumerator<UnBCL::String *,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::TableKey,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::KeyTraits,&UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::RetrieveValue(ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::TableKey,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::KeyTraits,ATL::CElementTraits<UnBCL::String *>> const *,__POSITION * const &)>::CopyToArray(UnBCL::Hashtable<UnBCL::String *,UnBCL::String *> const *,UnBCL::Array<UnBCL::String *> *,int)

- ea: `0x180035cc4`
- end: `0x180035e6e`
- name: `?CopyToArray@?$HTEnumerator@PEAVString@UnBCL@@PEAV12@UTableKey@?$Hashtable@PEAVString@UnBCL@@PEAV12@@2@PEAV12@UKeyTraits@42@$1?RetrieveValue@42@KAPEAV12@PEBV?$CAtlMap@UTableKey@?$Hashtable@PEAVString@UnBCL@@PEAV12@@UnBCL@@PEAVString@3@UKeyTraits@23@V?$CElementTraits@PEAVString@UnBCL@@@ATL@@@ATL@@AEBQEAU__POSITION@@@Z@_@UnBCL@@SAXPEBV?$Hashtable@PEAVString@UnBCL@@PEAV12@@3@PEAV?$Array@PEAVString@UnBCL@@@3@H@Z`
- size: `426`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180035b04`

## callees

- `0x18000225c`
- `0x1800066cc`
- `0x1800098b0`
- `0x1800099b0`
- `0x180009b40`
- `0x180009e7c`
- `0x180035cc4`
- `0x180036ba0`
- `0x180036f94`
- `0x1800477d0`
- `0x18006f010`

## string_xrefs

- `0x180035dac`: `null array to Hashtable#CopyTo`
- `0x180035df3`: `negative start index to CopyTo`
- `0x180035e3a`: `array of insufficient size to CopyTo`
- `0x180035dbc`: `void __cdecl UnBCL::_::HTEnumerator<class UnBCL::String *,class UnBCL::String *,struct UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>::TableKey,class UnBCL::String *,struct UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>::KeyTraits,&protected: static class UnBCL::String * __cdecl UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>::RetrieveValue(class ATL::CAtlMap<struct UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>::TableKey,class UnBCL::St`
- `0x180035e03`: `void __cdecl UnBCL::_::HTEnumerator<class UnBCL::String *,class UnBCL::String *,struct UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>::TableKey,class UnBCL::String *,struct UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>::KeyTraits,&protected: static class UnBCL::String * __cdecl UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>::RetrieveValue(class ATL::CAtlMap<struct UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>::TableKey,class UnBCL::St`
- `0x180035e4a`: `void __cdecl UnBCL::_::HTEnumerator<class UnBCL::String *,class UnBCL::String *,struct UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>::TableKey,class UnBCL::String *,struct UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>::KeyTraits,&protected: static class UnBCL::String * __cdecl UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>::RetrieveValue(class ATL::CAtlMap<struct UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>::TableKey,class UnBCL::St`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UnBCL::_::HTEnumerator<UnBCL::String *,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::TableKey,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::KeyTraits,&protected: static UnBCL::String * UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::RetrieveValue(ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::TableKey,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::KeyTraits,ATL::CElementTraits<UnBCL::String *>> const *,__POSITION * const &)>::CopyToArray(
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
                         "eValue(class ATL::CAtlMap<struct UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>:"
                         ":TableKey,class UnBCL::String *,struct UnBCL::Hashtable<class UnBCL::String *,class UnBCL::Stri"
                         "ng *>::KeyTraits,class ATL::CElementTraits<class UnBCL::String *> > const *,struct __POSITION *"
                         " const &)>::CopyToArray(const class UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String "
                         "*> *,class UnBCL::Array<class UnBCL::String *> *,int)");
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
                         "eValue(class ATL::CAtlMap<struct UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>:"
                         ":TableKey,class UnBCL::String *,struct UnBCL::Hashtable<class UnBCL::String *,class UnBCL::Stri"
                         "ng *>::KeyTraits,class ATL::CElementTraits<class UnBCL::String *> > const *,struct __POSITION *"
                         " const &)>::CopyToArray(const class UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String "
                         "*> *,class UnBCL::Array<class UnBCL::String *> *,int)");
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
                         "eValue(class ATL::CAtlMap<struct UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String *>:"
                         ":TableKey,class UnBCL::String *,struct UnBCL::Hashtable<class UnBCL::String *,class UnBCL::Stri"
                         "ng *>::KeyTraits,class ATL::CElementTraits<class UnBCL::String *> > const *,struct __POSITION *"
                         " const &)>::CopyToArray(const class UnBCL::Hashtable<class UnBCL::String *,class UnBCL::String "
                         "*> *,class UnBCL::Array<class UnBCL::String *> *,int)");
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
0x180035cc4  push    rbp
0x180035cc6  push    rdi
0x180035cc7  push    r14
0x180035cc9  mov     rbp, rsp
0x180035ccc  sub     rsp, 30h
0x180035cd0  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFEh
0x180035cd8  mov     [rsp+30h+arg_0], rbx
0x180035cdd  mov     [rsp+30h+arg_10], rsi
0x180035ce2  mov     edi, r8d
0x180035ce5  mov     rsi, rdx
0x180035ce8  mov     r14, rcx
0x180035ceb  test    rdx, rdx
0x180035cee  jz      loc_180035D99
0x180035cf4  test    r8d, r8d
0x180035cf7  js      loc_180035DE0
0x180035cfd  mov     rax, [rcx+8]
0x180035d01  movsxd  rcx, dword ptr [rax+0Ch]
0x180035d05  add     rcx, 8
0x180035d09  add     rcx, r14
0x180035d0c  mov     rax, [rcx]
0x180035d0f  mov     rax, [rax]
0x180035d12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035d17  mov     ebx, eax
0x180035d19  mov     rcx, [rsi]
0x180035d1c  mov     rax, [rcx]
0x180035d1f  mov     rcx, rsi
0x180035d22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035d27  sub     eax, edi
0x180035d29  cmp     eax, ebx
0x180035d2b  jl      loc_180035E27
0x180035d31  mov     rcx, [r14+28h]
0x180035d35  call    ?GetStartPosition@?$CAtlMap@UTableKey@?$Hashtable@PEAVString@UnBCL@@PEAV12@@UnBCL@@PEAVString@3@UKeyTraits@23@V?$CElementTraits@PEAVString@UnBCL@@@ATL@@@ATL@@QEBAPEAU__POSITION@@XZ; ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::TableKey,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::KeyTraits,ATL::CElementTraits<UnBCL::String *>>::GetStartPosition(void)
0x180035d3a  mov     rcx, rax
0x180035d3d  mov     [rbp+pExceptionObject], rax
0x180035d41  test    rax, rax
0x180035d44  jz      short loc_180035D7B
0x180035d46  test    rcx, rcx
0x180035d49  jz      short loc_180035D8E
0x180035d4b  mov     rax, [rsi]
0x180035d4e  mov     r8d, edi
0x180035d51  mov     rdx, [rcx+10h]
0x180035d55  mov     rcx, rsi
0x180035d58  mov     rax, [rax+28h]
0x180035d5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035d61  lea     rdx, [rbp+pExceptionObject]
0x180035d65  mov     rcx, [r14+28h]
0x180035d69  call    ?GetNext@?$CAtlMap@UTableKey@?$Hashtable@PEAVSerializationId@UnBCL@@PEAVTypeFactoryList@SerializationStream@2@@UnBCL@@PEAVTypeFactoryList@SerializationStream@3@UKeyTraits@23@V?$CElementTraits@PEAVTypeFactoryList@SerializationStream@UnBCL@@@ATL@@@ATL@@QEAAPEAVCPair@12@AEAPEAU__POSITION@@@Z; ATL::CAtlMap<UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::TableKey,UnBCL::SerializationStream::TypeFactoryList *,UnBCL::Hashtable<UnBCL::SerializationId *,UnBCL::SerializationStream::TypeFactoryList *>::KeyTraits,ATL::CElementTraits<UnBCL::SerializationStream::TypeFactoryList *>>::GetNext(__POSITION * &)
0x180035d6e  mov     rcx, [rbp+pExceptionObject]
0x180035d72  test    rcx, rcx
0x180035d75  jz      short loc_180035D7B
0x180035d77  inc     edi
0x180035d79  jmp     short loc_180035D46
0x180035d7b  mov     rbx, [rsp+30h+arg_0]
0x180035d80  mov     rsi, [rsp+30h+arg_10]
0x180035d85  add     rsp, 30h
0x180035d89  pop     r14
0x180035d8b  pop     rdi
0x180035d8c  pop     rbp
0x180035d8d  retn
0x180035d8e  mov     ecx, 80004005h; int
0x180035d93  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180035d99  mov     ecx, 38h ; '8'; unsigned __int64
0x180035d9e  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180035da3  mov     [rbp+arg_18], rax
0x180035da7  test    rax, rax
0x180035daa  jz      short loc_180035DBC
0x180035dac  lea     rdx, aNullArrayToHas; "null array to Hashtable#CopyTo"
0x180035db3  mov     rcx, rax; this
0x180035db6  call    ??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x180035dbb  nop
0x180035dbc  lea     rdx, aVoidCdeclUnbcl_173; "void __cdecl UnBCL::_::HTEnumerator<cla"...
0x180035dc3  mov     rcx, rax
0x180035dc6  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180035dcb  mov     [rbp+pExceptionObject], rax
0x180035dcf  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x180035dd6  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180035dda  call    _CxxThrowException_0
0x180035de0  mov     ecx, 38h ; '8'; unsigned __int64
0x180035de5  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180035dea  mov     [rbp+arg_18], rax
0x180035dee  test    rax, rax
0x180035df1  jz      short loc_180035E03
0x180035df3  lea     rdx, aNegativeStartI; "negative start index to CopyTo"
0x180035dfa  mov     rcx, rax; this
0x180035dfd  call    ??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x180035e02  nop
0x180035e03  lea     rdx, aVoidCdeclUnbcl_173; "void __cdecl UnBCL::_::HTEnumerator<cla"...
0x180035e0a  mov     rcx, rax
0x180035e0d  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180035e12  mov     [rbp+pExceptionObject], rax
0x180035e16  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x180035e1d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180035e21  call    _CxxThrowException_0
0x180035e27  mov     ecx, 38h ; '8'; unsigned __int64
0x180035e2c  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180035e31  mov     [rbp+arg_18], rax
0x180035e35  test    rax, rax
0x180035e38  jz      short loc_180035E4A
0x180035e3a  lea     rdx, aArrayOfInsuffi; "array of insufficient size to CopyTo"
0x180035e41  mov     rcx, rax; this
0x180035e44  call    ??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x180035e49  nop
0x180035e4a  lea     rdx, aVoidCdeclUnbcl_173; "void __cdecl UnBCL::_::HTEnumerator<cla"...
0x180035e51  mov     rcx, rax
0x180035e54  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180035e59  mov     [rbp+pExceptionObject], rax
0x180035e5d  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x180035e64  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180035e68  call    _CxxThrowException_0
```
