# UnBCL::_::HTEnumerator<UnBCL::SerializationStream::UniqueObject,int,UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::TableKey,UnBCL::DictionaryEntry<UnBCL::SerializationStream::UniqueObject,int>,UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::KeyTraits,&UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::RetrieveEntry(ATL::CAtlMap<UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::TableKey,int,UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::KeyTraits,ATL::CElementTraits<int>> const *,__POSITION * const &)>::CopyToArray(UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int> const *,UnBCL::Array<UnBCL::DictionaryEntry<UnBCL::SerializationStream::UniqueObject,int>> *,int)

- ea: `0x180053a14`
- end: `0x180053c9a`
- name: `?CopyToArray@?$HTEnumerator@UUniqueObject@SerializationStream@UnBCL@@HUTableKey@?$Hashtable@UUniqueObject@SerializationStream@UnBCL@@H@3@V?$DictionaryEntry@UUniqueObject@SerializationStream@UnBCL@@H@3@UKeyTraits@53@$1?RetrieveEntry@53@KA?AV63@PEBV?$CAtlMap@UTableKey@?$Hashtable@UUniqueObject@SerializationStream@UnBCL@@H@UnBCL@@HUKeyTraits@23@V?$CElementTraits@H@ATL@@@ATL@@AEBQEAU__POSITION@@@Z@_@UnBCL@@SAXPEBV?$Hashtable@UUniqueObject@SerializationStream@UnBCL@@H@3@PEAV?$Array@V?$DictionaryEntry@UUniqueObject@SerializationStream@UnBCL@@H@UnBCL@@@3@H@Z`
- size: `646`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180053014`

## callees

- `0x18000225c`
- `0x1800098b0`
- `0x1800099b0`
- `0x180009b40`
- `0x180009e7c`
- `0x180036f94`
- `0x1800477d0`
- `0x180053a14`
- `0x180054618`
- `0x180056550`
- `0x18006f010`

## string_xrefs

- `0x180053c1f`: `null array to Hashtable#CopyTo`
- `0x180053c66`: `negative start index to CopyTo`
- `0x180053bd8`: `array of insufficient size to CopyTo`
- `0x180053be8`: `void __cdecl UnBCL::_::HTEnumerator<struct UnBCL::SerializationStream::UniqueObject,int,struct UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::TableKey,class UnBCL::DictionaryEntry<struct UnBCL::SerializationStream::UniqueObject,int>,struct UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::KeyTraits,&protected: static class UnBCL::DictionaryEntry<struct UnBCL::SerializationStream::UniqueObject,int> __cdecl UnBCL::Hashtable<struct UnBCL::SerializationSt`
- `0x180053c2f`: `void __cdecl UnBCL::_::HTEnumerator<struct UnBCL::SerializationStream::UniqueObject,int,struct UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::TableKey,class UnBCL::DictionaryEntry<struct UnBCL::SerializationStream::UniqueObject,int>,struct UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::KeyTraits,&protected: static class UnBCL::DictionaryEntry<struct UnBCL::SerializationStream::UniqueObject,int> __cdecl UnBCL::Hashtable<struct UnBCL::SerializationSt`
- `0x180053c76`: `void __cdecl UnBCL::_::HTEnumerator<struct UnBCL::SerializationStream::UniqueObject,int,struct UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::TableKey,class UnBCL::DictionaryEntry<struct UnBCL::SerializationStream::UniqueObject,int>,struct UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::KeyTraits,&protected: static class UnBCL::DictionaryEntry<struct UnBCL::SerializationStream::UniqueObject,int> __cdecl UnBCL::Hashtable<struct UnBCL::SerializationSt`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall UnBCL::_::HTEnumerator<UnBCL::SerializationStream::UniqueObject,int,UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::TableKey,UnBCL::DictionaryEntry<UnBCL::SerializationStream::UniqueObject,int>,UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::KeyTraits,&protected: static UnBCL::DictionaryEntry<UnBCL::SerializationStream::UniqueObject,int> UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::RetrieveEntry(ATL::CAtlMap<UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::TableKey,int,UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::KeyTraits,ATL::CElementTraits<int>> const *,__POSITION * const &)>::CopyToArray(
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
  void **v15; // [rsp+30h] [rbp-71h] BYREF
  __int64 *v16; // [rsp+38h] [rbp-69h]
  __int128 v17; // [rsp+40h] [rbp-61h]
  int v18; // [rsp+50h] [rbp-51h]
  int v19; // [rsp+54h] [rbp-4Dh]
  int v20; // [rsp+58h] [rbp-49h]
  void **v21; // [rsp+68h] [rbp-39h]
  int v22; // [rsp+70h] [rbp-31h]
  signed __int32 v23; // [rsp+74h] [rbp-2Dh]
  void **v24; // [rsp+78h] [rbp-29h] BYREF
  __int64 v25; // [rsp+80h] [rbp-21h]
  __int128 v26; // [rsp+88h] [rbp-19h]
  int v27; // [rsp+98h] [rbp-9h]
  int v28; // [rsp+9Ch] [rbp-5h]
  int v29; // [rsp+A0h] [rbp-1h]
  void **v30; // [rsp+B0h] [rbp+Fh]
  __int64 v31; // [rsp+C8h] [rbp+27h]
  __int64 pExceptionObject; // [rsp+110h] [rbp+6Fh] BYREF
  void ***v33; // [rsp+120h] [rbp+7Fh]

  v31 = -2;
  v3 = a3;
  v6 = 0;
  if ( !a2 )
  {
    v13 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v33 = (void ***)v13;
    if ( v13 )
      v13 = (UnBCL::ArgumentNullException *)UnBCL::ArgumentNullException::ArgumentNullException(
                                              v13,
                                              L"null array to Hashtable#CopyTo");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v13,
                         "void __cdecl UnBCL::_::HTEnumerator<struct UnBCL::SerializationStream::UniqueObject,int,struct "
                         "UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::TableKey,class UnBCL::Di"
                         "ctionaryEntry<struct UnBCL::SerializationStream::UniqueObject,int>,struct UnBCL::Hashtable<stru"
                         "ct UnBCL::SerializationStream::UniqueObject,int>::KeyTraits,&protected: static class UnBCL::Dic"
                         "tionaryEntry<struct UnBCL::SerializationStream::UniqueObject,int> __cdecl UnBCL::Hashtable<stru"
                         "ct UnBCL::SerializationStream::UniqueObject,int>::RetrieveEntry(class ATL::CAtlMap<struct UnBCL"
                         "::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::TableKey,int,struct UnBCL::Ha"
                         "shtable<struct UnBCL::SerializationStream::UniqueObject,int>::KeyTraits,class ATL::CElementTrai"
                         "ts<int> > const *,struct __POSITION * const &)>::CopyToArray(const class UnBCL::Hashtable<struc"
                         "t UnBCL::SerializationStream::UniqueObject,int> *,class UnBCL::Array<class UnBCL::DictionaryEnt"
                         "ry<struct UnBCL::SerializationStream::UniqueObject,int> > *,int)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  if ( a3 < 0 )
  {
    v14 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::Object::operator new(0x38u);
    v33 = (void ***)v14;
    if ( v14 )
      v14 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(
                                                    v14,
                                                    L"negative start index to CopyTo");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v14,
                         "void __cdecl UnBCL::_::HTEnumerator<struct UnBCL::SerializationStream::UniqueObject,int,struct "
                         "UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::TableKey,class UnBCL::Di"
                         "ctionaryEntry<struct UnBCL::SerializationStream::UniqueObject,int>,struct UnBCL::Hashtable<stru"
                         "ct UnBCL::SerializationStream::UniqueObject,int>::KeyTraits,&protected: static class UnBCL::Dic"
                         "tionaryEntry<struct UnBCL::SerializationStream::UniqueObject,int> __cdecl UnBCL::Hashtable<stru"
                         "ct UnBCL::SerializationStream::UniqueObject,int>::RetrieveEntry(class ATL::CAtlMap<struct UnBCL"
                         "::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::TableKey,int,struct UnBCL::Ha"
                         "shtable<struct UnBCL::SerializationStream::UniqueObject,int>::KeyTraits,class ATL::CElementTrai"
                         "ts<int> > const *,struct __POSITION * const &)>::CopyToArray(const class UnBCL::Hashtable<struc"
                         "t UnBCL::SerializationStream::UniqueObject,int> *,class UnBCL::Array<class UnBCL::DictionaryEnt"
                         "ry<struct UnBCL::SerializationStream::UniqueObject,int> > *,int)");
    throw (UnBCL::ArgumentOutOfRangeException **)&pExceptionObject;
  }
  v7 = (__int64 (__fastcall ***)(_QWORD))(a1 + *(int *)(*(_QWORD *)(a1 + 8) + 12LL) + 8LL);
  v8 = (**v7)(v7);
  if ( (int)((**(__int64 (__fastcall ***)(__int64))a2)(a2) - v3) < v8 )
  {
    v12 = (UnBCL::ArgumentException *)UnBCL::Object::operator new(0x38u);
    v33 = (void ***)v12;
    if ( v12 )
      v12 = (UnBCL::ArgumentException *)UnBCL::ArgumentException::ArgumentException(
                                          v12,
                                          L"array of insufficient size to CopyTo");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v12,
                         "void __cdecl UnBCL::_::HTEnumerator<struct UnBCL::SerializationStream::UniqueObject,int,struct "
                         "UnBCL::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::TableKey,class UnBCL::Di"
                         "ctionaryEntry<struct UnBCL::SerializationStream::UniqueObject,int>,struct UnBCL::Hashtable<stru"
                         "ct UnBCL::SerializationStream::UniqueObject,int>::KeyTraits,&protected: static class UnBCL::Dic"
                         "tionaryEntry<struct UnBCL::SerializationStream::UniqueObject,int> __cdecl UnBCL::Hashtable<stru"
                         "ct UnBCL::SerializationStream::UniqueObject,int>::RetrieveEntry(class ATL::CAtlMap<struct UnBCL"
                         "::Hashtable<struct UnBCL::SerializationStream::UniqueObject,int>::TableKey,int,struct UnBCL::Ha"
                         "shtable<struct UnBCL::SerializationStream::UniqueObject,int>::KeyTraits,class ATL::CElementTrai"
                         "ts<int> > const *,struct __POSITION * const &)>::CopyToArray(const class UnBCL::Hashtable<struc"
                         "t UnBCL::SerializationStream::UniqueObject,int> *,class UnBCL::Array<class UnBCL::DictionaryEnt"
                         "ry<struct UnBCL::SerializationStream::UniqueObject,int> > *,int)");
    throw (UnBCL::ArgumentException **)&pExceptionObject;
  }
  result = ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::TableKey,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::KeyTraits,ATL::CElementTraits<UnBCL::String *>>::GetStartPosition(*(_QWORD *)(a1 + 40));
  for ( pExceptionObject = result; pExceptionObject; v30 = &UnBCL::Object::`vftable' )
  {
    UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::RetrieveEntry(
      &v24,
      *(_QWORD *)(a1 + 40),
      &pExceptionObject);
    v10 = *(void (__fastcall **)(__int64, void ***, __int64))(*(_QWORD *)a2 + 40LL);
    v11 = v3++;
    v33 = &v15;
    v16 = &UnBCL::DictionaryEntry<UnBCL::SerializationStream::UniqueObject,int>::`vbtable';
    v21 = &UnBCL::Object::`vftable';
    v22 = 0;
    v23 = _InterlockedIncrement(&dword_1800FFC68);
    v6 |= 1u;
    v15 = &UnBCL::DictionaryEntry<UnBCL::SerializationStream::UniqueObject,int>::`vftable'{for `UnBCL::DictionaryEntry<UnBCL::SerializationStream::UniqueObject,int>'};
    *(__int64 **)((char *)&v16
                + SHIDWORD(UnBCL::DictionaryEntry<UnBCL::SerializationStream::UniqueObject,int>::`vbtable')) = (__int64 *)&UnBCL::DictionaryEntry<UnBCL::SerializationStream::UniqueObject,int>::`vftable'{for `UnBCL::Object'};
    *(_DWORD *)((char *)&v15 + *((int *)v16 + 1) + 4) = 0;
    v17 = v26;
    v18 = v27;
    v19 = v28;
    v20 = v29;
    v10(a2, &v15, v11);
    ATL::CAtlMap<UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::TableKey,int,UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::KeyTraits,ATL::CElementTraits<int>>::GetNext(
      *(_QWORD *)(a1 + 40),
      &pExceptionObject);
    v24 = &UnBCL::DictionaryEntry<UnBCL::SerializationStream::UniqueObject,int>::`vftable'{for `UnBCL::DictionaryEntry<UnBCL::SerializationStream::UniqueObject,int>'};
    *(__int64 *)((char *)&v25 + *(int *)(v25 + 4)) = (__int64)&UnBCL::DictionaryEntry<UnBCL::SerializationStream::UniqueObject,int>::`vftable'{for `UnBCL::Object'};
    result = v25;
    *(_DWORD *)((char *)&v24 + *(int *)(v25 + 4) + 4) = *(_DWORD *)(v25 + 4) - 48;
  }
  return result;
}

```

## disassembly

```asm
0x180053a14  mov     rax, rsp
0x180053a17  push    rbp
0x180053a18  push    rdi
0x180053a19  push    r13
0x180053a1b  push    r14
0x180053a1d  push    r15
0x180053a1f  lea     rbp, [rax-5Fh]
0x180053a23  sub     rsp, 0D0h
0x180053a2a  mov     [rbp+57h+var_30], 0FFFFFFFFFFFFFFFEh
0x180053a32  mov     [rax+8], rbx
0x180053a36  mov     [rax+18h], rsi
0x180053a3a  mov     r14d, r8d
0x180053a3d  mov     rdi, rdx
0x180053a40  mov     rsi, rcx
0x180053a43  xor     r15d, r15d
0x180053a46  mov     [rbp+57h+var_D0], r15d
0x180053a4a  test    rdx, rdx
0x180053a4d  jz      loc_180053C0C
0x180053a53  test    r8d, r8d
0x180053a56  js      loc_180053C53
0x180053a5c  mov     rax, [rcx+8]
0x180053a60  movsxd  rcx, dword ptr [rax+0Ch]
0x180053a64  add     rcx, 8
0x180053a68  add     rcx, rsi
0x180053a6b  mov     rax, [rcx]
0x180053a6e  mov     rax, [rax]
0x180053a71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053a76  mov     ebx, eax
0x180053a78  mov     rcx, [rdi]
0x180053a7b  mov     rax, [rcx]
0x180053a7e  mov     rcx, rdi
0x180053a81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053a86  sub     eax, r14d
0x180053a89  cmp     eax, ebx
0x180053a8b  jl      loc_180053BC5
0x180053a91  mov     rcx, [rsi+28h]
0x180053a95  call    ?GetStartPosition@?$CAtlMap@UTableKey@?$Hashtable@PEAVString@UnBCL@@PEAV12@@UnBCL@@PEAVString@3@UKeyTraits@23@V?$CElementTraits@PEAVString@UnBCL@@@ATL@@@ATL@@QEBAPEAU__POSITION@@XZ; ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::TableKey,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::KeyTraits,ATL::CElementTraits<UnBCL::String *>>::GetStartPosition(void)
0x180053a9a  mov     [rbp+57h+pExceptionObject], rax
0x180053a9e  test    rax, rax
0x180053aa1  jz      loc_180053BA9
0x180053aa7  lea     ebx, [r15+1]
0x180053aab  lea     r13, ??_7Object@UnBCL@@6B@; const UnBCL::Object::`vftable'
0x180053ab2  lea     r8, [rbp+57h+pExceptionObject]
0x180053ab6  mov     rdx, [rsi+28h]
0x180053aba  lea     rcx, [rbp+57h+var_80]
0x180053abe  call    ?RetrieveEntry@?$Hashtable@UUniqueObject@SerializationStream@UnBCL@@H@UnBCL@@KA?AV?$DictionaryEntry@UUniqueObject@SerializationStream@UnBCL@@H@2@PEBV?$CAtlMap@UTableKey@?$Hashtable@UUniqueObject@SerializationStream@UnBCL@@H@UnBCL@@HUKeyTraits@23@V?$CElementTraits@H@ATL@@@ATL@@AEBQEAU__POSITION@@@Z; UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::RetrieveEntry(ATL::CAtlMap<UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::TableKey,int,UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::KeyTraits,ATL::CElementTraits<int>> const *,__POSITION * const &)
0x180053ac3  nop
0x180053ac4  mov     rax, [rdi]
0x180053ac7  mov     r9, [rax+28h]
0x180053acb  mov     r8d, r14d
0x180053ace  add     r14d, ebx
0x180053ad1  lea     rax, [rbp+57h+var_C8]
0x180053ad5  mov     [rbp+57h+arg_18], rax
0x180053ad9  lea     rax, ??_8?$DictionaryEntry@UUniqueObject@SerializationStream@UnBCL@@H@UnBCL@@7B@; const UnBCL::DictionaryEntry<UnBCL::SerializationStream::UniqueObject,int>::`vbtable'
0x180053ae0  mov     [rbp+57h+var_C0], rax
0x180053ae4  mov     [rbp+57h+var_90], r13
0x180053ae8  mov     [rbp+57h+var_88], 0
0x180053aef  mov     eax, ebx
0x180053af1  lock xadd cs:dword_1800FFC68, eax
0x180053af9  add     eax, ebx
0x180053afb  mov     [rbp+57h+var_84], eax
0x180053afe  or      r15d, ebx
0x180053b01  mov     [rbp+57h+var_D0], r15d
0x180053b05  lea     rax, ??_7?$DictionaryEntry@UUniqueObject@SerializationStream@UnBCL@@H@UnBCL@@6B01@@; const UnBCL::DictionaryEntry<UnBCL::SerializationStream::UniqueObject,int>::`vftable'{for `UnBCL::DictionaryEntry<UnBCL::SerializationStream::UniqueObject,int>'}
0x180053b0c  mov     [rbp+57h+var_C8], rax
0x180053b10  mov     rax, [rbp+57h+var_C0]
0x180053b14  movsxd  rcx, dword ptr [rax+4]
0x180053b18  lea     rax, ??_7?$DictionaryEntry@UUniqueObject@SerializationStream@UnBCL@@H@UnBCL@@6BObject@1@@; const UnBCL::DictionaryEntry<UnBCL::SerializationStream::UniqueObject,int>::`vftable'{for `UnBCL::Object'}
0x180053b1f  mov     [rbp+rcx+57h+var_C0], rax
0x180053b24  mov     rax, [rbp+57h+var_C0]
0x180053b28  movsxd  rcx, dword ptr [rax+4]
0x180053b2c  mov     dword ptr [rbp+rcx+57h+var_C8+4], 0
0x180053b34  movaps  xmm0, [rbp+57h+var_70]
0x180053b38  movdqu  [rbp+57h+var_B8], xmm0
0x180053b3d  mov     eax, [rbp+57h+var_60]
0x180053b40  mov     [rbp+57h+var_A8], eax
0x180053b43  mov     ecx, [rbp+57h+var_5C]
0x180053b46  mov     [rbp+57h+var_A4], ecx
0x180053b49  mov     ecx, [rbp+57h+var_58]
0x180053b4c  mov     [rbp+57h+var_A0], ecx
0x180053b4f  lea     rdx, [rbp+57h+var_C8]
0x180053b53  mov     rcx, rdi
0x180053b56  mov     rax, r9
0x180053b59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053b5e  lea     rdx, [rbp+57h+pExceptionObject]
0x180053b62  mov     rcx, [rsi+28h]
0x180053b66  call    ?GetNext@?$CAtlMap@UTableKey@?$Hashtable@UUniqueObject@SerializationStream@UnBCL@@H@UnBCL@@HUKeyTraits@23@V?$CElementTraits@H@ATL@@@ATL@@QEAAPEAVCPair@12@AEAPEAU__POSITION@@@Z; ATL::CAtlMap<UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::TableKey,int,UnBCL::Hashtable<UnBCL::SerializationStream::UniqueObject,int>::KeyTraits,ATL::CElementTraits<int>>::GetNext(__POSITION * &)
0x180053b6b  nop
0x180053b6c  lea     rax, ??_7?$DictionaryEntry@UUniqueObject@SerializationStream@UnBCL@@H@UnBCL@@6B01@@; const UnBCL::DictionaryEntry<UnBCL::SerializationStream::UniqueObject,int>::`vftable'{for `UnBCL::DictionaryEntry<UnBCL::SerializationStream::UniqueObject,int>'}
0x180053b73  mov     [rbp+57h+var_80], rax
0x180053b77  mov     rax, [rbp+57h+var_78]
0x180053b7b  movsxd  rcx, dword ptr [rax+4]
0x180053b7f  lea     rax, ??_7?$DictionaryEntry@UUniqueObject@SerializationStream@UnBCL@@H@UnBCL@@6BObject@1@@; const UnBCL::DictionaryEntry<UnBCL::SerializationStream::UniqueObject,int>::`vftable'{for `UnBCL::Object'}
0x180053b86  mov     [rbp+rcx+57h+var_78], rax
0x180053b8b  mov     rax, [rbp+57h+var_78]
0x180053b8f  movsxd  rcx, dword ptr [rax+4]
0x180053b93  lea     edx, [rcx-30h]
0x180053b96  mov     dword ptr [rbp+rcx+57h+var_80+4], edx
0x180053b9a  mov     [rbp+57h+var_48], r13
0x180053b9e  cmp     [rbp+57h+pExceptionObject], 0
0x180053ba3  jnz     loc_180053AB2
0x180053ba9  lea     r11, [rsp+0F0h+var_20]
0x180053bb1  mov     rbx, [r11+30h]
0x180053bb5  mov     rsi, [r11+40h]
0x180053bb9  mov     rsp, r11
0x180053bbc  pop     r15
0x180053bbe  pop     r14
0x180053bc0  pop     r13
0x180053bc2  pop     rdi
0x180053bc3  pop     rbp
0x180053bc4  retn
0x180053bc5  mov     ecx, 38h ; '8'; unsigned __int64
0x180053bca  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180053bcf  mov     [rbp+57h+arg_18], rax
0x180053bd3  test    rax, rax
0x180053bd6  jz      short loc_180053BE8
0x180053bd8  lea     rdx, aArrayOfInsuffi; "array of insufficient size to CopyTo"
0x180053bdf  mov     rcx, rax; this
0x180053be2  call    ??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x180053be7  nop
0x180053be8  lea     rdx, aVoidCdeclUnbcl_113; "void __cdecl UnBCL::_::HTEnumerator<str"...
0x180053bef  mov     rcx, rax
0x180053bf2  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180053bf7  mov     [rbp+57h+pExceptionObject], rax
0x180053bfb  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x180053c02  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180053c06  call    _CxxThrowException_0
0x180053c0c  mov     ecx, 38h ; '8'; unsigned __int64
0x180053c11  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180053c16  mov     [rbp+57h+arg_18], rax
0x180053c1a  test    rax, rax
0x180053c1d  jz      short loc_180053C2F
0x180053c1f  lea     rdx, aNullArrayToHas; "null array to Hashtable#CopyTo"
0x180053c26  mov     rcx, rax; this
0x180053c29  call    ??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x180053c2e  nop
0x180053c2f  lea     rdx, aVoidCdeclUnbcl_113; "void __cdecl UnBCL::_::HTEnumerator<str"...
0x180053c36  mov     rcx, rax
0x180053c39  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180053c3e  mov     [rbp+57h+pExceptionObject], rax
0x180053c42  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x180053c49  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180053c4d  call    _CxxThrowException_0
0x180053c53  mov     ecx, 38h ; '8'; unsigned __int64
0x180053c58  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180053c5d  mov     [rbp+57h+arg_18], rax
0x180053c61  test    rax, rax
0x180053c64  jz      short loc_180053C76
0x180053c66  lea     rdx, aNegativeStartI; "negative start index to CopyTo"
0x180053c6d  mov     rcx, rax; this
0x180053c70  call    ??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x180053c75  nop
0x180053c76  lea     rdx, aVoidCdeclUnbcl_113; "void __cdecl UnBCL::_::HTEnumerator<str"...
0x180053c7d  mov     rcx, rax
0x180053c80  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180053c85  mov     [rbp+57h+pExceptionObject], rax
0x180053c89  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x180053c90  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180053c94  call    _CxxThrowException_0
```
