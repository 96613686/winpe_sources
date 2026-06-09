# UnBCL::ArrayList<UnBCL::StringPtr>::RemoveAt(int)

- ea: `0x180045c94`
- end: `0x180045e8f`
- name: `?RemoveAt@?$ArrayList@VStringPtr@UnBCL@@@UnBCL@@UEAAXH@Z`
- size: `507`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x180045c80`

## callees

- `0x18000225c`
- `0x180002f90`
- `0x1800066cc`
- `0x180009b40`
- `0x180009e7c`
- `0x180043508`
- `0x180045278`
- `0x180045c94`
- `0x1800477d0`
- `0x1800600d0`
- `0x18006f010`

## import_xrefs

- `msvcrt!memmove_s` at `0x180045dc8`
- `msvcrt!memmove_s` at `0x180045dc8`

## string_xrefs

- `0x180045e27`: `index out of range to ArrayList#RemoveAt`
- `0x180045e37`: `void __cdecl UnBCL::ArrayList<class UnBCL::StringPtr>::RemoveAt(int)`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
errno_t __fastcall UnBCL::ArrayList<UnBCL::StringPtr>::RemoveAt(__int64 a1, int a2)
{
  unsigned __int64 v2; // rbx
  int (__fastcall ***v4)(_QWORD); // rcx
  _QWORD *v5; // rax
  __int64 v6; // rax
  _QWORD *v7; // rax
  __int64 v8; // rax
  unsigned __int64 v9; // rsi
  unsigned __int64 v10; // rbx
  _QWORD *v11; // rdi
  unsigned __int64 v12; // rbp
  __int64 v13; // rsi
  errno_t result; // eax
  unsigned __int64 v15; // rbp
  UnBCL::ArgumentOutOfRangeException *v16; // rax
  _BYTE v17[64]; // [rsp+28h] [rbp-40h] BYREF
  _BYTE *pExceptionObject; // [rsp+80h] [rbp+18h] BYREF
  UnBCL::ArgumentOutOfRangeException *v19; // [rsp+88h] [rbp+20h]

  v2 = a2;
  if ( a2 < 0
    || (v4 = (int (__fastcall ***)(_QWORD))(a1 + *(int *)(*(_QWORD *)(a1 - 104) + 12LL) - 104LL), a2 >= (**v4)(v4)) )
  {
    v16 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::Object::operator new(0x38u);
    v19 = v16;
    if ( v16 )
      v16 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(
                                                    v16,
                                                    L"index out of range to ArrayList#RemoveAt");
    pExceptionObject = (_BYTE *)AddStackTraceToException<UnBCL::InvalidOperationException>(
                                  v16,
                                  "void __cdecl UnBCL::ArrayList<class UnBCL::StringPtr>::RemoveAt(int)");
    throw (UnBCL::ArgumentOutOfRangeException **)&pExceptionObject;
  }
  ++*(_DWORD *)(a1 - 88);
  if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)(a1 - 112) + 32LL))(a1 - 112) )
  {
    pExceptionObject = v17;
    v5 = *(_QWORD **)(a1 - 96);
    if ( v2 >= v5[1] )
      ATL::AtlThrowImpl(-2147024809);
    v6 = UnBCL::StringPtr::StringPtr((UnBCL::StringPtr *)v17, (const struct UnBCL::StringPtr *)(32 * v2 + *v5));
    if ( !(unsigned int)UnBCL::MP::SmartPtrNull<UnBCL::StringPtr>::IsNull(v6) )
    {
      v7 = *(_QWORD **)(a1 - 96);
      if ( v2 >= v7[1] )
        ATL::AtlThrowImpl(-2147024809);
      v8 = UnBCL::StringPtr::StringPtr((UnBCL::StringPtr *)v17, (const struct UnBCL::StringPtr *)(32 * v2 + *v7));
      *(_QWORD *)(v8 + 16) = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
      UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v8 + 16);
    }
  }
  v9 = v2;
  v10 = v2 + 1;
  if ( v10 < v9 )
    goto LABEL_18;
  if ( !v10 )
    goto LABEL_18;
  v11 = *(_QWORD **)(a1 - 96);
  v12 = v11[1];
  if ( v10 > v12 )
    goto LABEL_18;
  v13 = 32 * v9;
  result = ATL::CAtlArray<UnBCL::StringPtr,ATL::CElementTraits<UnBCL::StringPtr>>::CallDestructors(v13 + *v11, 1);
  v15 = v12 - v10;
  if ( !v15 )
    goto LABEL_17;
  result = memmove_s((void *const)(v13 + *v11), 32 * v15, (const void *const)(*v11 + 32 * v10), 32 * v15);
  switch ( result )
  {
    case 0:
      goto LABEL_17;
    case 12:
      ATL::AtlThrowImpl(-2147024882);
    case 22:
    case 34:
LABEL_18:
      ATL::AtlThrowImpl(-2147024809);
  }
  if ( result != 80 )
    ATL::AtlThrowImpl(-2147467259);
LABEL_17:
  --v11[1];
  return result;
}

```

## disassembly

```asm
0x180045c94  push    rsi
0x180045c96  push    rdi
0x180045c97  push    r14
0x180045c99  sub     rsp, 50h
0x180045c9d  mov     [rsp+68h+var_48], 0FFFFFFFFFFFFFFFEh
0x180045ca6  mov     [rsp+68h+arg_0], rbx
0x180045cab  mov     [rsp+68h+arg_8], rbp
0x180045cb0  movsxd  rbx, edx
0x180045cb3  mov     rdi, rcx
0x180045cb6  test    edx, edx
0x180045cb8  js      loc_180045E10
0x180045cbe  mov     rax, [rcx-68h]
0x180045cc2  movsxd  rcx, dword ptr [rax+0Ch]
0x180045cc6  add     rcx, 0FFFFFFFFFFFFFF98h
0x180045cca  add     rcx, rdi
0x180045ccd  mov     rax, [rcx]
0x180045cd0  mov     rax, [rax]
0x180045cd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045cd8  cmp     ebx, eax
0x180045cda  jge     loc_180045E10
0x180045ce0  inc     dword ptr [rdi-58h]
0x180045ce3  mov     rax, [rdi-70h]
0x180045ce7  lea     rcx, [rdi-70h]
0x180045ceb  mov     rax, [rax+20h]
0x180045cef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045cf4  test    eax, eax
0x180045cf6  jz      short loc_180045D74
0x180045cf8  lea     rax, [rsp+68h+var_40]
0x180045cfd  mov     [rsp+68h+pExceptionObject], rax
0x180045d05  mov     rax, [rdi-60h]
0x180045d09  cmp     rbx, [rax+8]
0x180045d0d  jnb     loc_180045E63
0x180045d13  mov     r14, rbx
0x180045d16  shl     r14, 5
0x180045d1a  mov     rdx, [rax]
0x180045d1d  add     rdx, r14; struct UnBCL::StringPtr *
0x180045d20  mov     r8d, 1
0x180045d26  lea     rcx, [rsp+68h+var_40]; this
0x180045d2b  call    ??0StringPtr@UnBCL@@QEAA@AEBV01@@Z; UnBCL::StringPtr::StringPtr(UnBCL::StringPtr const &)
0x180045d30  nop
0x180045d31  mov     rcx, rax
0x180045d34  call    ?IsNull@?$SmartPtrNull@VStringPtr@UnBCL@@@MP@UnBCL@@SAHVStringPtr@3@@Z; UnBCL::MP::SmartPtrNull<UnBCL::StringPtr>::IsNull(UnBCL::StringPtr)
0x180045d39  test    eax, eax
0x180045d3b  jnz     short loc_180045D74
0x180045d3d  mov     rax, [rdi-60h]
0x180045d41  cmp     rbx, [rax+8]
0x180045d45  jnb     loc_180045E6E
0x180045d4b  mov     rdx, [rax]
0x180045d4e  add     rdx, r14; struct UnBCL::StringPtr *
0x180045d51  mov     r8d, 1
0x180045d57  lea     rcx, [rsp+68h+var_40]; this
0x180045d5c  call    ??0StringPtr@UnBCL@@QEAA@AEBV01@@Z; UnBCL::StringPtr::StringPtr(UnBCL::StringPtr const &)
0x180045d61  lea     rcx, [rax+10h]
0x180045d65  lea     rax, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x180045d6c  mov     [rcx], rax
0x180045d6f  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x180045d74  mov     rsi, rbx
0x180045d77  inc     rbx
0x180045d7a  cmp     rbx, rsi
0x180045d7d  jb      loc_180045E05
0x180045d83  cmp     rbx, 1
0x180045d87  jb      short loc_180045E05
0x180045d89  mov     rdi, [rdi-60h]
0x180045d8d  mov     rbp, [rdi+8]
0x180045d91  cmp     rbx, rbp
0x180045d94  ja      short loc_180045E05
0x180045d96  shl     rsi, 5
0x180045d9a  mov     rcx, [rdi]
0x180045d9d  add     rcx, rsi
0x180045da0  mov     edx, 1
0x180045da5  call    ?CallDestructors@?$CAtlArray@VStringPtr@UnBCL@@V?$CElementTraits@VStringPtr@UnBCL@@@ATL@@@ATL@@CAXPEAVStringPtr@UnBCL@@_K@Z; ATL::CAtlArray<UnBCL::StringPtr,ATL::CElementTraits<UnBCL::StringPtr>>::CallDestructors(UnBCL::StringPtr *,unsigned __int64)
0x180045daa  sub     rbp, rbx
0x180045dad  jz      short loc_180045DEE
0x180045daf  mov     rax, [rdi]
0x180045db2  shl     rbp, 5
0x180045db6  shl     rbx, 5
0x180045dba  lea     r8, [rax+rbx]; Source
0x180045dbe  lea     rcx, [rsi+rax]; Destination
0x180045dc2  mov     r9, rbp; SourceSize
0x180045dc5  mov     rdx, rbp; DestinationSize
0x180045dc8  call    cs:__imp_memmove_s
0x180045dce  test    eax, eax
0x180045dd0  jz      short loc_180045DEE
0x180045dd2  cmp     eax, 0Ch
0x180045dd5  jz      loc_180045E84
0x180045ddb  cmp     eax, 16h
0x180045dde  jz      short loc_180045E05
0x180045de0  cmp     eax, 22h ; '"'
0x180045de3  jz      short loc_180045E05
0x180045de5  cmp     eax, 50h ; 'P'
0x180045de8  jnz     loc_180045E79
0x180045dee  dec     qword ptr [rdi+8]
0x180045df2  mov     rbx, [rsp+68h+arg_0]
0x180045df7  mov     rbp, [rsp+68h+arg_8]
0x180045dfc  add     rsp, 50h
0x180045e00  pop     r14
0x180045e02  pop     rdi
0x180045e03  pop     rsi
0x180045e04  retn
0x180045e05  mov     ecx, 80070057h; int
0x180045e0a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180045e10  mov     ecx, 38h ; '8'; unsigned __int64
0x180045e15  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180045e1a  mov     [rsp+68h+arg_18], rax
0x180045e22  test    rax, rax
0x180045e25  jz      short loc_180045E37
0x180045e27  lea     rdx, aIndexOutOfRang_0; "index out of range to ArrayList#RemoveA"...
0x180045e2e  mov     rcx, rax; this
0x180045e31  call    ??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x180045e36  nop
0x180045e37  lea     rdx, aVoidCdeclUnbcl_32; "void __cdecl UnBCL::ArrayList<class UnB"...
0x180045e3e  mov     rcx, rax
0x180045e41  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180045e46  mov     [rsp+68h+pExceptionObject], rax
0x180045e4e  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x180045e55  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180045e5d  call    _CxxThrowException_0
0x180045e63  mov     ecx, 80070057h; int
0x180045e68  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180045e6e  mov     ecx, 80070057h; int
0x180045e73  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180045e79  mov     ecx, 80004005h; int
0x180045e7e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180045e84  mov     ecx, 8007000Eh; int
0x180045e89  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
