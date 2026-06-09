# UnBCL::ArrayList<UnBCL::SmartPtr<UnBCL::String>>::RemoveAt(int)

- ea: `0x18002f904`
- end: `0x18002fae5`
- name: `?RemoveAt@?$ArrayList@V?$SmartPtr@VString@UnBCL@@@UnBCL@@@UnBCL@@UEAAXH@Z`
- size: `481`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18002f8f0`

## callees

- `0x18000225c`
- `0x180002f90`
- `0x1800066cc`
- `0x180009b40`
- `0x180009e7c`
- `0x180011530`
- `0x180028090`
- `0x18002e2b8`
- `0x18002f904`
- `0x1800477d0`
- `0x18006f010`

## import_xrefs

- `msvcrt!memmove_s` at `0x18002fa27`
- `msvcrt!memmove_s` at `0x18002fa27`

## string_xrefs

- `0x18002fa83`: `index out of range to ArrayList#RemoveAt`
- `0x18002fa93`: `void __cdecl UnBCL::ArrayList<class UnBCL::SmartPtr<class UnBCL::String> >::RemoveAt(int)`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
errno_t __fastcall UnBCL::ArrayList<UnBCL::SmartPtr<UnBCL::String>>::RemoveAt(__int64 a1, int a2)
{
  unsigned __int64 v2; // rbx
  int (__fastcall ***v4)(_QWORD); // rcx
  _QWORD *v5; // rax
  __int64 v6; // rax
  _QWORD *v7; // rax
  _QWORD *v8; // rax
  unsigned __int64 v9; // rsi
  unsigned __int64 v10; // rbx
  _QWORD *v11; // rdi
  unsigned __int64 v12; // rbp
  __int64 v13; // rsi
  errno_t result; // eax
  unsigned __int64 v15; // rbp
  UnBCL::ArgumentOutOfRangeException *v16; // rax
  _BYTE v17[48]; // [rsp+28h] [rbp-30h] BYREF
  _BYTE *pExceptionObject; // [rsp+70h] [rbp+18h] BYREF
  UnBCL::ArgumentOutOfRangeException *v19; // [rsp+78h] [rbp+20h]

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
                                  "void __cdecl UnBCL::ArrayList<class UnBCL::SmartPtr<class UnBCL::String> >::RemoveAt(int)");
    throw (UnBCL::ArgumentOutOfRangeException **)&pExceptionObject;
  }
  ++*(_DWORD *)(a1 - 88);
  if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)(a1 - 112) + 32LL))(a1 - 112) )
  {
    pExceptionObject = v17;
    v5 = *(_QWORD **)(a1 - 96);
    if ( v2 >= v5[1] )
      ATL::AtlThrowImpl(-2147024809);
    v6 = UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v17, 16 * v2 + *v5);
    if ( !(unsigned int)UnBCL::MP::SmartPtrNull<UnBCL::SmartPtr<UnBCL::String>>::IsNull(v6) )
    {
      v7 = *(_QWORD **)(a1 - 96);
      if ( v2 >= v7[1] )
        ATL::AtlThrowImpl(-2147024809);
      v8 = (_QWORD *)UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v17, 16 * v2 + *v7);
      *v8 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
      UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v8);
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
  v13 = 16 * v9;
  result = ATL::CAtlArray<UnBCL::SmartPtr<UnBCL::String>,ATL::CElementTraits<UnBCL::SmartPtr<UnBCL::String>>>::CallDestructors(
             v13 + *v11,
             1);
  v15 = v12 - v10;
  if ( !v15 )
    goto LABEL_17;
  result = memmove_s((void *const)(v13 + *v11), 16 * v15, (const void *const)(*v11 + 16 * v10), 16 * v15);
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
0x18002f904  push    rsi
0x18002f906  push    rdi
0x18002f907  push    r14
0x18002f909  sub     rsp, 40h
0x18002f90d  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x18002f916  mov     [rsp+58h+arg_0], rbx
0x18002f91b  mov     [rsp+58h+arg_8], rbp
0x18002f920  movsxd  rbx, edx
0x18002f923  mov     rdi, rcx
0x18002f926  test    edx, edx
0x18002f928  js      loc_18002FA6F
0x18002f92e  mov     rax, [rcx-68h]
0x18002f932  movsxd  rcx, dword ptr [rax+0Ch]
0x18002f936  add     rcx, 0FFFFFFFFFFFFFF98h
0x18002f93a  add     rcx, rdi
0x18002f93d  mov     rax, [rcx]
0x18002f940  mov     rax, [rax]
0x18002f943  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f948  cmp     ebx, eax
0x18002f94a  jge     loc_18002FA6F
0x18002f950  inc     dword ptr [rdi-58h]
0x18002f953  mov     rax, [rdi-70h]
0x18002f957  lea     rcx, [rdi-70h]
0x18002f95b  mov     rax, [rax+20h]
0x18002f95f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f964  test    eax, eax
0x18002f966  jz      short loc_18002F9D4
0x18002f968  lea     rax, [rsp+58h+var_30]
0x18002f96d  mov     [rsp+58h+pExceptionObject], rax
0x18002f972  mov     rax, [rdi-60h]
0x18002f976  cmp     rbx, [rax+8]
0x18002f97a  jnb     loc_18002FAB9
0x18002f980  mov     r14, rbx
0x18002f983  shl     r14, 4
0x18002f987  mov     rdx, [rax]
0x18002f98a  add     rdx, r14
0x18002f98d  lea     rcx, [rsp+58h+var_30]
0x18002f992  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::SmartPtr<UnBCL::String> const &)
0x18002f997  nop
0x18002f998  mov     rcx, rax
0x18002f99b  call    ?IsNull@?$SmartPtrNull@V?$SmartPtr@VString@UnBCL@@@UnBCL@@@MP@UnBCL@@SAHV?$SmartPtr@VString@UnBCL@@@3@@Z; UnBCL::MP::SmartPtrNull<UnBCL::SmartPtr<UnBCL::String>>::IsNull(UnBCL::SmartPtr<UnBCL::String>)
0x18002f9a0  test    eax, eax
0x18002f9a2  jnz     short loc_18002F9D4
0x18002f9a4  mov     rax, [rdi-60h]
0x18002f9a8  cmp     rbx, [rax+8]
0x18002f9ac  jnb     loc_18002FAC4
0x18002f9b2  mov     rdx, [rax]
0x18002f9b5  add     rdx, r14
0x18002f9b8  lea     rcx, [rsp+58h+var_30]
0x18002f9bd  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::SmartPtr<UnBCL::String> const &)
0x18002f9c2  lea     rcx, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x18002f9c9  mov     [rax], rcx
0x18002f9cc  mov     rcx, rax
0x18002f9cf  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18002f9d4  mov     rsi, rbx
0x18002f9d7  inc     rbx
0x18002f9da  cmp     rbx, rsi
0x18002f9dd  jb      loc_18002FA64
0x18002f9e3  cmp     rbx, 1
0x18002f9e7  jb      short loc_18002FA64
0x18002f9e9  mov     rdi, [rdi-60h]
0x18002f9ed  mov     rbp, [rdi+8]
0x18002f9f1  cmp     rbx, rbp
0x18002f9f4  ja      short loc_18002FA64
0x18002f9f6  shl     rsi, 4
0x18002f9fa  mov     rcx, [rdi]
0x18002f9fd  add     rcx, rsi
0x18002fa00  mov     edx, 1
0x18002fa05  call    ?CallDestructors@?$CAtlArray@V?$SmartPtr@VString@UnBCL@@@UnBCL@@V?$CElementTraits@V?$SmartPtr@VString@UnBCL@@@UnBCL@@@ATL@@@ATL@@CAXPEAV?$SmartPtr@VString@UnBCL@@@UnBCL@@_K@Z; ATL::CAtlArray<UnBCL::SmartPtr<UnBCL::String>,ATL::CElementTraits<UnBCL::SmartPtr<UnBCL::String>>>::CallDestructors(UnBCL::SmartPtr<UnBCL::String> *,unsigned __int64)
0x18002fa0a  sub     rbp, rbx
0x18002fa0d  jz      short loc_18002FA4D
0x18002fa0f  mov     rax, [rdi]
0x18002fa12  shl     rbp, 4
0x18002fa16  add     rbx, rbx
0x18002fa19  lea     r8, [rax+rbx*8]; Source
0x18002fa1d  lea     rcx, [rsi+rax]; Destination
0x18002fa21  mov     r9, rbp; SourceSize
0x18002fa24  mov     rdx, rbp; DestinationSize
0x18002fa27  call    cs:__imp_memmove_s
0x18002fa2d  test    eax, eax
0x18002fa2f  jz      short loc_18002FA4D
0x18002fa31  cmp     eax, 0Ch
0x18002fa34  jz      loc_18002FADA
0x18002fa3a  cmp     eax, 16h
0x18002fa3d  jz      short loc_18002FA64
0x18002fa3f  cmp     eax, 22h ; '"'
0x18002fa42  jz      short loc_18002FA64
0x18002fa44  cmp     eax, 50h ; 'P'
0x18002fa47  jnz     loc_18002FACF
0x18002fa4d  dec     qword ptr [rdi+8]
0x18002fa51  mov     rbx, [rsp+58h+arg_0]
0x18002fa56  mov     rbp, [rsp+58h+arg_8]
0x18002fa5b  add     rsp, 40h
0x18002fa5f  pop     r14
0x18002fa61  pop     rdi
0x18002fa62  pop     rsi
0x18002fa63  retn
0x18002fa64  mov     ecx, 80070057h; int
0x18002fa69  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002fa6f  mov     ecx, 38h ; '8'; unsigned __int64
0x18002fa74  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002fa79  mov     [rsp+58h+arg_18], rax
0x18002fa7e  test    rax, rax
0x18002fa81  jz      short loc_18002FA93
0x18002fa83  lea     rdx, aIndexOutOfRang_0; "index out of range to ArrayList#RemoveA"...
0x18002fa8a  mov     rcx, rax; this
0x18002fa8d  call    ??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x18002fa92  nop
0x18002fa93  lea     rdx, aVoidCdeclUnbcl_25; "void __cdecl UnBCL::ArrayList<class UnB"...
0x18002fa9a  mov     rcx, rax
0x18002fa9d  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002faa2  mov     [rsp+58h+pExceptionObject], rax
0x18002faa7  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x18002faae  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18002fab3  call    _CxxThrowException_0
0x18002fab9  mov     ecx, 80070057h; int
0x18002fabe  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002fac4  mov     ecx, 80070057h; int
0x18002fac9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002facf  mov     ecx, 80004005h; int
0x18002fad4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002fada  mov     ecx, 8007000Eh; int
0x18002fadf  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
