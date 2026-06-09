# UnBCL::String::Replace(ushort const *,ushort const *,UnBCL::String::StringCasing)

- ea: `0x18005d720`
- end: `0x18005d991`
- name: `?Replace@String@UnBCL@@QEBAPEAV12@PEBG0W4StringCasing@12@@Z`
- size: `625`
- prototype: ``
- caller_count: `18`
- callee_count: `12`
- tags: ``

## callers

- `0x180018a70`
- `0x180018bb0`
- `0x180018cf0`
- `0x180018e30`
- `0x180018f70`
- `0x1800190b0`
- `0x1800191f0`
- `0x180019330`
- `0x180037b70`
- `0x180037c70`
- `0x180037d70`
- `0x180044a00`
- `0x1800558c0`
- `0x180056630`
- `0x180056810`
- `0x180058e60`
- `0x18005d5f0`
- `0x18005ecc0`

## callees

- `0x18000225c`
- `0x180007fa0`
- `0x1800080e0`
- `0x180008680`
- `0x180008c10`
- `0x1800098b0`
- `0x1800099b0`
- `0x180009e7c`
- `0x1800477d0`
- `0x18005b650`
- `0x18005d720`
- `0x18006f010`

## string_xrefs

- `0x18005d922`: `class UnBCL::String *__cdecl UnBCL::String::Replace(const unsigned short *,const unsigned short *,enum UnBCL::String::StringCasing) const`
- `0x18005d96d`: `class UnBCL::String *__cdecl UnBCL::String::Replace(const unsigned short *,const unsigned short *,enum UnBCL::String::StringCasing) const`
- `0x18005d90e`: `empty old string to String#Replace`
- `0x18005d959`: `null old or NEW string to String#Replace`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall UnBCL::String::Replace(const struct UnBCL::String *a1, char *a2, char *a3, int a4)
{
  char *v5; // rdi
  char *v6; // rbx
  char *v8; // rax
  __int64 v9; // rsi
  char *v10; // r14
  char *v11; // r15
  __int64 v12; // r8
  __int64 v13; // r8
  __int64 v14; // r8
  __int64 v15; // r8
  UnBCL::ArgumentException *v17; // rax
  __int64 v18; // rax
  UnBCL::ArgumentNullException *v19; // rax
  __int64 v20; // rax
  char *v21[2]; // [rsp+20h] [rbp-28h] BYREF
  UnBCL::ArgumentNullException *v22; // [rsp+30h] [rbp-18h]
  char *pExceptionObject; // [rsp+98h] [rbp+50h] BYREF

  v21[1] = (char *)-2LL;
  v5 = a3;
  v6 = a2;
  if ( !a2 || !a3 )
  {
    v19 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v22 = v19;
    if ( v19 )
      v20 = UnBCL::ArgumentNullException::ArgumentNullException(v19, L"null old or NEW string to String#Replace");
    else
      v20 = 0;
    pExceptionObject = (char *)AddStackTraceToException<UnBCL::InvalidOperationException>(
                                 v20,
                                 "class UnBCL::String *__cdecl UnBCL::String::Replace(const unsigned short *,const unsign"
                                 "ed short *,enum UnBCL::String::StringCasing) const");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  if ( !*(_WORD *)a2 )
  {
    v17 = (UnBCL::ArgumentException *)UnBCL::Object::operator new(0x38u);
    v22 = v17;
    if ( v17 )
      v18 = UnBCL::ArgumentException::ArgumentException(v17, L"empty old string to String#Replace");
    else
      v18 = 0;
    pExceptionObject = (char *)AddStackTraceToException<UnBCL::InvalidOperationException>(
                                 v18,
                                 "class UnBCL::String *__cdecl UnBCL::String::Replace(const unsigned short *,const unsign"
                                 "ed short *,enum UnBCL::String::StringCasing) const");
    throw (UnBCL::ArgumentException **)&pExceptionObject;
  }
  v8 = (char *)UnBCL::Object::operator new(0x18u);
  pExceptionObject = v8;
  if ( v8 )
    v9 = UnBCL::String::String((UnBCL::String *)v8, a1);
  else
    v9 = 0;
  v10 = (char *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  v21[0] = v10;
  v11 = (char *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  pExceptionObject = v11;
  if ( a4 == 1 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::MakeLower(v9 + 16);
    v12 = -1;
    do
      ++v12;
    while ( *(_WORD *)&v6[2 * v12] );
    ATL::CSimpleStringT<unsigned short,0>::SetString(v21, v6, v12);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::MakeLower(v21);
    v6 = v21[0];
    v13 = -1;
    do
      ++v13;
    while ( *(_WORD *)&v5[2 * v13] );
    ATL::CSimpleStringT<unsigned short,0>::SetString(&pExceptionObject, v5, v13);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::MakeLower(&pExceptionObject);
LABEL_13:
    v5 = pExceptionObject;
    v11 = pExceptionObject;
    v10 = v6;
    goto LABEL_20;
  }
  if ( a4 == 2 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::MakeUpper(v9 + 16);
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)&v6[2 * v14] );
    ATL::CSimpleStringT<unsigned short,0>::SetString(v21, v6, v14);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::MakeUpper(v21);
    v6 = v21[0];
    v15 = -1;
    do
      ++v15;
    while ( *(_WORD *)&v5[2 * v15] );
    ATL::CSimpleStringT<unsigned short,0>::SetString(&pExceptionObject, v5, v15);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::MakeUpper(&pExceptionObject);
    goto LABEL_13;
  }
LABEL_20:
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace(
    (const wchar_t **)(v9 + 16),
    (const wchar_t *)v6,
    v5);
  if ( _InterlockedDecrement((volatile signed __int32 *)v11 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v11 - 3) + 8LL))(*((_QWORD *)v11 - 3));
  if ( _InterlockedDecrement((volatile signed __int32 *)v10 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v10 - 3) + 8LL))(*((_QWORD *)v10 - 3));
  return v9;
}

```

## disassembly

```asm
0x18005d720  push    rbp
0x18005d722  push    rbx
0x18005d723  push    rsi
0x18005d724  push    rdi
0x18005d725  push    r12
0x18005d727  push    r13
0x18005d729  push    r14
0x18005d72b  push    r15
0x18005d72d  mov     rbp, rsp
0x18005d730  sub     rsp, 48h
0x18005d734  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFEh
0x18005d73c  mov     r12d, r9d
0x18005d73f  mov     rdi, r8
0x18005d742  mov     rbx, rdx
0x18005d745  mov     rsi, rcx
0x18005d748  xor     r13d, r13d
0x18005d74b  test    rdx, rdx
0x18005d74e  jz      loc_18005D946
0x18005d754  test    r8, r8
0x18005d757  jz      loc_18005D946
0x18005d75d  cmp     [rdx], r13w
0x18005d761  jz      loc_18005D8FB
0x18005d767  lea     ecx, [r13+18h]; unsigned __int64
0x18005d76b  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18005d770  mov     [rbp+pExceptionObject], rax
0x18005d774  test    rax, rax
0x18005d777  jz      short loc_18005D789
0x18005d779  mov     rdx, rsi; struct UnBCL::String *
0x18005d77c  mov     rcx, rax; this
0x18005d77f  call    ??0String@UnBCL@@QEAA@PEBV01@@Z; UnBCL::String::String(UnBCL::String const *)
0x18005d784  mov     rsi, rax
0x18005d787  jmp     short loc_18005D78C
0x18005d789  mov     rsi, r13
0x18005d78c  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18005d793  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18005d79a  mov     rax, [rax+18h]
0x18005d79e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d7a3  lea     r14, [rax+18h]
0x18005d7a7  mov     [rbp+var_28], r14
0x18005d7ab  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18005d7b2  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18005d7b9  mov     rax, [rax+18h]
0x18005d7bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d7c2  lea     r15, [rax+18h]
0x18005d7c6  mov     [rbp+pExceptionObject], r15
0x18005d7ca  cmp     r12d, 1
0x18005d7ce  jnz     short loc_18005D831
0x18005d7d0  lea     rcx, [rsi+10h]
0x18005d7d4  call    ?MakeLower@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::MakeLower(void)
0x18005d7d9  or      r12, 0FFFFFFFFFFFFFFFFh
0x18005d7dd  mov     r8, r12
0x18005d7e0  inc     r8
0x18005d7e3  cmp     [rbx+r8*2], r13w
0x18005d7e8  jnz     short loc_18005D7E0
0x18005d7ea  mov     rdx, rbx
0x18005d7ed  lea     rcx, [rbp+var_28]
0x18005d7f1  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18005d7f6  lea     rcx, [rbp+var_28]
0x18005d7fa  call    ?MakeLower@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::MakeLower(void)
0x18005d7ff  mov     rbx, [rbp+var_28]
0x18005d803  mov     r8, r12
0x18005d806  inc     r8
0x18005d809  cmp     [rdi+r8*2], r13w
0x18005d80e  jnz     short loc_18005D806
0x18005d810  mov     rdx, rdi
0x18005d813  lea     rcx, [rbp+pExceptionObject]
0x18005d817  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18005d81c  lea     rcx, [rbp+pExceptionObject]
0x18005d820  call    ?MakeLower@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::MakeLower(void)
0x18005d825  mov     rdi, [rbp+pExceptionObject]
0x18005d829  mov     r15, rdi
0x18005d82c  mov     r14, rbx
0x18005d82f  jmp     short loc_18005D892
0x18005d831  cmp     r12d, 2
0x18005d835  jnz     short loc_18005D88E
0x18005d837  lea     rcx, [rsi+10h]
0x18005d83b  call    ?MakeUpper@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::MakeUpper(void)
0x18005d840  or      r12, 0FFFFFFFFFFFFFFFFh
0x18005d844  mov     r8, r12
0x18005d847  inc     r8
0x18005d84a  cmp     [rbx+r8*2], r13w
0x18005d84f  jnz     short loc_18005D847
0x18005d851  mov     rdx, rbx
0x18005d854  lea     rcx, [rbp+var_28]
0x18005d858  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18005d85d  lea     rcx, [rbp+var_28]
0x18005d861  call    ?MakeUpper@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::MakeUpper(void)
0x18005d866  mov     rbx, [rbp+var_28]
0x18005d86a  mov     r8, r12
0x18005d86d  inc     r8
0x18005d870  cmp     [rdi+r8*2], r13w
0x18005d875  jnz     short loc_18005D86D
0x18005d877  mov     rdx, rdi
0x18005d87a  lea     rcx, [rbp+pExceptionObject]
0x18005d87e  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18005d883  lea     rcx, [rbp+pExceptionObject]
0x18005d887  call    ?MakeUpper@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::MakeUpper(void)
0x18005d88c  jmp     short loc_18005D825
0x18005d88e  or      r12, 0FFFFFFFFFFFFFFFFh
0x18005d892  lea     rcx, [rsi+10h]
0x18005d896  mov     r8, rdi
0x18005d899  mov     rdx, rbx
0x18005d89c  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort const *,ushort const *)
0x18005d8a1  nop
0x18005d8a2  lea     rdx, [r15-18h]
0x18005d8a6  mov     eax, r12d
0x18005d8a9  lock xadd [rdx+10h], eax
0x18005d8ae  add     eax, r12d
0x18005d8b1  test    eax, eax
0x18005d8b3  jg      short loc_18005D8C5
0x18005d8b5  mov     rcx, [rdx]
0x18005d8b8  mov     rax, [rcx]
0x18005d8bb  mov     rax, [rax+8]
0x18005d8bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d8c4  nop
0x18005d8c5  lea     rdx, [r14-18h]
0x18005d8c9  mov     eax, r12d
0x18005d8cc  lock xadd [rdx+10h], eax
0x18005d8d1  add     eax, r12d
0x18005d8d4  test    eax, eax
0x18005d8d6  jg      short loc_18005D8E7
0x18005d8d8  mov     rcx, [rdx]
0x18005d8db  mov     rax, [rcx]
0x18005d8de  mov     rax, [rax+8]
0x18005d8e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d8e7  mov     rax, rsi
0x18005d8ea  add     rsp, 48h
0x18005d8ee  pop     r15
0x18005d8f0  pop     r14
0x18005d8f2  pop     r13
0x18005d8f4  pop     r12
0x18005d8f6  pop     rdi
0x18005d8f7  pop     rsi
0x18005d8f8  pop     rbx
0x18005d8f9  pop     rbp
0x18005d8fa  retn
0x18005d8fb  mov     ecx, 38h ; '8'; unsigned __int64
0x18005d900  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18005d905  mov     [rbp+var_18], rax
0x18005d909  test    rax, rax
0x18005d90c  jz      short loc_18005D91F
0x18005d90e  lea     rdx, aEmptyOldString; "empty old string to String#Replace"
0x18005d915  mov     rcx, rax; this
0x18005d918  call    ??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x18005d91d  jmp     short loc_18005D922
0x18005d91f  mov     rax, r13
0x18005d922  lea     rdx, aClassUnbclStri_10; "class UnBCL::String *__cdecl UnBCL::Str"...
0x18005d929  mov     rcx, rax
0x18005d92c  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18005d931  mov     [rbp+pExceptionObject], rax
0x18005d935  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x18005d93c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18005d940  call    _CxxThrowException_0
0x18005d946  mov     ecx, 38h ; '8'; unsigned __int64
0x18005d94b  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18005d950  mov     [rbp+var_18], rax
0x18005d954  test    rax, rax
0x18005d957  jz      short loc_18005D96A
0x18005d959  lea     rdx, aNullOldOrNewSt; "null old or NEW string to String#Replac"...
0x18005d960  mov     rcx, rax; this
0x18005d963  call    ??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x18005d968  jmp     short loc_18005D96D
0x18005d96a  mov     rax, r13
0x18005d96d  lea     rdx, aClassUnbclStri_10; "class UnBCL::String *__cdecl UnBCL::Str"...
0x18005d974  mov     rcx, rax
0x18005d977  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18005d97c  mov     [rbp+pExceptionObject], rax
0x18005d980  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x18005d987  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18005d98b  call    _CxxThrowException_0
```
