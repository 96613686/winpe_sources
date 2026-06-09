# CWbemNamespace::GetContextPutExtensions(IWbemContext *,int &,int &,int &,CWStringArray &)

- ea: `0x1800822c8`
- end: `0x180082740`
- name: `?GetContextPutExtensions@CWbemNamespace@@SAJPEAUIWbemContext@@AEAH11AEAVCWStringArray@@@Z`
- size: `1144`
- prototype: `__int64 __fastcall(struct IWbemContext *, int *, int *, int *, struct CWStringArray *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800820a0`

## callees

- `0x18000b140`
- `0x18000b46c`
- `0x18005edf4`
- `0x180064d28`
- `0x1800822c8`
- `0x1800da010`

## import_xrefs

- `wbemcomn!?Size@CSafeArray@@QEAAHXZ` at `0x180082638`
- `wbemcomn!?Size@CSafeArray@@QEAAHXZ` at `0x180082638`
- `wbemcomn!?Empty@CWStringArray@@QEAAXXZ` at `0x18008233b`
- `wbemcomn!?Empty@CWStringArray@@QEAAXXZ` at `0x18008233b`
- `wbemcomn!??0CSafeArray@@QEAA@PEAUtagSAFEARRAY@@HHH@Z` at `0x18008262b`
- `wbemcomn!??0CSafeArray@@QEAA@PEAUtagSAFEARRAY@@HHH@Z` at `0x18008262b`
- `wbemcomn!?GetBSTRAt@CSafeArray@@QEAAPEAGH@Z` at `0x18008264c`
- `wbemcomn!?GetBSTRAt@CSafeArray@@QEAAPEAGH@Z` at `0x18008264c`
- `wbemcomn!??1CSafeArray@@QEAA@XZ` at `0x1800826d8`
- `wbemcomn!??1CSafeArray@@QEAA@XZ` at `0x18008271c`
- `wbemcomn!??1CSafeArray@@QEAA@XZ` at `0x1800826d8`
- `wbemcomn!??1CSafeArray@@QEAA@XZ` at `0x18008271c`
- `wbemcomn!?Add@CWStringArray@@QEAAHPEBG@Z` at `0x180082662`
- `wbemcomn!?Add@CWStringArray@@QEAAHPEBG@Z` at `0x180082662`
- `wbemcomn!GetMemLogObject` at `0x180082359`
- `wbemcomn!GetMemLogObject` at `0x18008240d`
- `wbemcomn!GetMemLogObject` at `0x1800824d5`
- `wbemcomn!GetMemLogObject` at `0x18008251e`
- `wbemcomn!GetMemLogObject` at `0x18008257f`
- `wbemcomn!GetMemLogObject` at `0x180082679`
- `wbemcomn!GetMemLogObject` at `0x180082359`
- `wbemcomn!GetMemLogObject` at `0x18008240d`
- `wbemcomn!GetMemLogObject` at `0x1800824d5`
- `wbemcomn!GetMemLogObject` at `0x18008251e`
- `wbemcomn!GetMemLogObject` at `0x18008257f`
- `wbemcomn!GetMemLogObject` at `0x180082679`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180082364`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180082418`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800824e1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180082529`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008258b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180082689`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180082364`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180082418`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800824e1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180082529`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008258b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180082689`
- `OLEAUT32!__imp_VariantInit` at `0x180082464`
- `OLEAUT32!__imp_VariantInit` at `0x180082464`
- `OLEAUT32!__imp_VariantClear` at `0x180082728`
- `OLEAUT32!__imp_VariantClear` at `0x180082728`

## string_xrefs

- `0x180082344`: `__PUT_EXTENSIONS`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWbemNamespace::GetContextPutExtensions(
        struct IWbemContext *a1,
        int *a2,
        int *a3,
        int *a4,
        struct CWStringArray *a5)
{
  CClientCnt *v9; // rcx
  __int64 v10; // rdx
  unsigned int ContextBoolean; // edi
  CMemoryLog *MemLogObject; // rax
  CClientCnt *v13; // rcx
  __int64 v14; // rdx
  CMemoryLog *v16; // rax
  int v17; // eax
  CClientCnt *v18; // rcx
  __int64 v19; // rdx
  CMemoryLog *v20; // rax
  CMemoryLog *v21; // rax
  CMemoryLog *v22; // rax
  int i; // ebx
  const unsigned __int16 *BSTRAt; // rax
  CMemoryLog *v25; // rax
  VARIANTARG pvarg; // [rsp+38h] [rbp-29h] BYREF
  _BYTE v27[96]; // [rsp+50h] [rbp-11h] BYREF
  const unsigned __int16 *v28; // [rsp+C0h] [rbp+5Fh] BYREF

  *a2 = 0;
  if ( !a1 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v10 = 427;
LABEL_17:
    WPP_SF_d(*((_QWORD *)v9 + 2), v10, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 0);
    return 0;
  }
  *a3 = 0;
  *a4 = 0;
  CWStringArray::Empty(a5);
  ContextBoolean = CWbemNamespace::GetContextBoolean(a1, L"__PUT_EXTENSIONS", a2);
  if ( (ContextBoolean & 0x80000000) != 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, ContextBoolean);
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return ContextBoolean;
    }
    v14 = 429;
    goto LABEL_11;
  }
  if ( !*a2 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v10 = 430;
    goto LABEL_17;
  }
  ContextBoolean = CWbemNamespace::GetContextBoolean(a1, L"__PUT_EXT_STRICT_NULLS", a3);
  if ( (ContextBoolean & 0x80000000) == 0 )
  {
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    v17 = ((__int64 (__fastcall *)(struct IWbemContext *, const wchar_t *, _QWORD, VARIANTARG *))a1->lpVtbl->GetValue)(
            a1,
            L"__PUT_EXT_PROPERTIES",
            0,
            &pvarg);
    ContextBoolean = v17;
    if ( v17 >= 0 )
    {
      if ( pvarg.vt == 8200 )
      {
        *a4 = 1;
        CSafeArray::CSafeArray((CSafeArray *)v27, pvarg.parray, 8, 5, 32);
        for ( i = 0; i < CSafeArray::Size((CSafeArray *)v27); ++i )
        {
          BSTRAt = CSafeArray::GetBSTRAt((CSafeArray *)v27, i);
          v28 = BSTRAt;
          if ( BSTRAt && CWStringArray::Add(a5, BSTRAt) )
          {
            v25 = GetMemLogObject();
            ContextBoolean = -2147217402;
            CMemoryLog::Write(v25, -2147217402);
            if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                437,
                WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                2147749894LL);
            }
            CSysFreeMe::~CSysFreeMe((CSysFreeMe *)&v28);
            CSafeArray::~CSafeArray((CSafeArray *)v27);
            goto LABEL_64;
          }
          CSysFreeMe::~CSysFreeMe((CSysFreeMe *)&v28);
        }
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 438, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 0);
        }
        CSafeArray::~CSafeArray((CSafeArray *)v27);
        goto LABEL_63;
      }
      v22 = GetMemLogObject();
      CMemoryLog::Write(v22, -1);
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 435, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids);
          v18 = WPP_GLOBAL_Control;
        }
        if ( v18 != (CClientCnt *)&WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 1) != 0 && *((_BYTE *)v18 + 25) >= 2u )
        {
          v19 = 436;
          goto LABEL_47;
        }
      }
    }
    else
    {
      if ( v17 != -2147217406 )
      {
        v20 = GetMemLogObject();
        CMemoryLog::Write(v20, -1);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            433,
            WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
            ContextBoolean);
        }
        v21 = GetMemLogObject();
        CMemoryLog::Write(v21, ContextBoolean);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            434,
            WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
            ContextBoolean);
        }
        goto LABEL_64;
      }
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v19 = 432;
LABEL_47:
        WPP_SF_d(*((_QWORD *)v18 + 2), v19, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 0);
      }
    }
LABEL_63:
    ContextBoolean = 0;
LABEL_64:
    VariantClear(&pvarg);
    return ContextBoolean;
  }
  v16 = GetMemLogObject();
  CMemoryLog::Write(v16, ContextBoolean);
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    return ContextBoolean;
  }
  v14 = 431;
LABEL_11:
  WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, ContextBoolean);
  return ContextBoolean;
}

```

## disassembly

```asm
0x1800822c8  push    rbp
0x1800822ca  push    rbx
0x1800822cb  push    rsi
0x1800822cc  push    rdi
0x1800822cd  push    r14
0x1800822cf  push    r15
0x1800822d1  lea     rbp, [rsp-27h]
0x1800822d6  sub     rsp, 88h
0x1800822dd  mov     r15, r9
0x1800822e0  mov     r14, r8
0x1800822e3  mov     rsi, rdx
0x1800822e6  mov     rbx, rcx
0x1800822e9  mov     dword ptr [rdx], 0
0x1800822ef  test    rcx, rcx
0x1800822f2  jnz     short loc_180082329
0x1800822f4  lea     rbx, WPP_GLOBAL_Control
0x1800822fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180082302  cmp     rcx, rbx
0x180082305  jz      loc_1800823EE
0x18008230b  test    byte ptr [rcx+1Ch], 1
0x18008230f  jz      loc_1800823EE
0x180082315  cmp     byte ptr [rcx+19h], 2
0x180082319  jb      loc_1800823EE
0x18008231f  mov     edx, 1ABh
0x180082324  jmp     loc_1800823DB
0x180082329  mov     dword ptr [r8], 0
0x180082330  mov     dword ptr [r9], 0
0x180082337  mov     rcx, [rbp+4Fh+arg_20]
0x18008233b  call    cs:__imp_?Empty@CWStringArray@@QEAAXXZ; CWStringArray::Empty(void)
0x180082341  mov     r8, rsi; int *
0x180082344  lea     rdx, aPutExtensions; "__PUT_EXTENSIONS"
0x18008234b  mov     rcx, rbx; struct IWbemContext *
0x18008234e  call    ?GetContextBoolean@CWbemNamespace@@SAJPEAUIWbemContext@@PEBGPEAH@Z; CWbemNamespace::GetContextBoolean(IWbemContext *,ushort const *,int *)
0x180082353  mov     edi, eax
0x180082355  test    eax, eax
0x180082357  jns     short loc_1800823B2
0x180082359  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008235f  mov     edx, edi
0x180082361  mov     rcx, rax
0x180082364  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008236a  lea     rbx, WPP_GLOBAL_Control
0x180082371  mov     rcx, cs:WPP_GLOBAL_Control
0x180082378  cmp     rcx, rbx
0x18008237b  jz      loc_18008272E
0x180082381  test    byte ptr [rcx+1Ch], 1
0x180082385  jz      loc_18008272E
0x18008238b  cmp     byte ptr [rcx+19h], 2
0x18008238f  jb      loc_18008272E
0x180082395  mov     edx, 1ADh
0x18008239a  mov     r9d, edi
0x18008239d  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x1800823a4  mov     rcx, [rcx+10h]
0x1800823a8  call    WPP_SF_d
0x1800823ad  jmp     loc_18008272E
0x1800823b2  cmp     dword ptr [rsi], 0
0x1800823b5  jnz     short loc_1800823F5
0x1800823b7  lea     rbx, WPP_GLOBAL_Control
0x1800823be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800823c5  cmp     rcx, rbx
0x1800823c8  jz      short loc_1800823EE
0x1800823ca  test    byte ptr [rcx+1Ch], 1
0x1800823ce  jz      short loc_1800823EE
0x1800823d0  cmp     byte ptr [rcx+19h], 2
0x1800823d4  jb      short loc_1800823EE
0x1800823d6  mov     edx, 1AEh
0x1800823db  xor     r9d, r9d
0x1800823de  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x1800823e5  mov     rcx, [rcx+10h]
0x1800823e9  call    WPP_SF_d
0x1800823ee  xor     eax, eax
0x1800823f0  jmp     loc_180082730
0x1800823f5  mov     r8, r14; int *
0x1800823f8  lea     rdx, aPutExtStrictNu; "__PUT_EXT_STRICT_NULLS"
0x1800823ff  mov     rcx, rbx; struct IWbemContext *
0x180082402  call    ?GetContextBoolean@CWbemNamespace@@SAJPEAUIWbemContext@@PEBGPEAH@Z; CWbemNamespace::GetContextBoolean(IWbemContext *,ushort const *,int *)
0x180082407  mov     edi, eax
0x180082409  test    eax, eax
0x18008240b  jns     short loc_180082453
0x18008240d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180082413  mov     edx, edi
0x180082415  mov     rcx, rax
0x180082418  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008241e  lea     rbx, WPP_GLOBAL_Control
0x180082425  mov     rcx, cs:WPP_GLOBAL_Control
0x18008242c  cmp     rcx, rbx
0x18008242f  jz      loc_18008272E
0x180082435  test    byte ptr [rcx+1Ch], 1
0x180082439  jz      loc_18008272E
0x18008243f  cmp     byte ptr [rcx+19h], 2
0x180082443  jb      loc_18008272E
0x180082449  mov     edx, 1AFh
0x18008244e  jmp     loc_18008239A
0x180082453  xorps   xmm0, xmm0
0x180082456  xor     eax, eax
0x180082458  movups  xmmword ptr [rbp+4Fh+pvarg], xmm0
0x18008245c  mov     qword ptr [rbp+4Fh+pvarg+10h], rax
0x180082460  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x180082464  call    cs:__imp_VariantInit
0x18008246a  lea     rax, [rbp+4Fh+pvarg]
0x18008246e  mov     [rbp+4Fh+var_80], rax
0x180082472  mov     rax, [rbx]
0x180082475  lea     r9, [rbp+4Fh+pvarg]
0x180082479  xor     r8d, r8d
0x18008247c  lea     rdx, aPutExtProperti; "__PUT_EXT_PROPERTIES"
0x180082483  mov     rcx, rbx
0x180082486  mov     rax, [rax+48h]
0x18008248a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008248f  mov     edi, eax
0x180082491  test    eax, eax
0x180082493  jns     loc_180082570
0x180082499  cmp     eax, 80041002h
0x18008249e  jnz     short loc_1800824D5
0x1800824a0  lea     rbx, WPP_GLOBAL_Control
0x1800824a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800824ae  cmp     rcx, rbx
0x1800824b1  jz      loc_180082722
0x1800824b7  test    byte ptr [rcx+1Ch], 1
0x1800824bb  jz      loc_180082722
0x1800824c1  cmp     byte ptr [rcx+19h], 2
0x1800824c5  jb      loc_180082722
0x1800824cb  mov     edx, 1B0h
0x1800824d0  jmp     loc_1800825F2
0x1800824d5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800824db  or      edx, 0FFFFFFFFh
0x1800824de  mov     rcx, rax
0x1800824e1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800824e7  lea     rbx, WPP_GLOBAL_Control
0x1800824ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800824f5  cmp     rcx, rbx
0x1800824f8  jz      short loc_18008251E
0x1800824fa  test    byte ptr [rcx+1Ch], 1
0x1800824fe  jz      short loc_18008251E
0x180082500  cmp     byte ptr [rcx+19h], 2
0x180082504  jb      short loc_18008251E
0x180082506  mov     edx, 1B1h
0x18008250b  mov     r9d, edi
0x18008250e  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180082515  mov     rcx, [rcx+10h]
0x180082519  call    WPP_SF_d
0x18008251e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180082524  mov     edx, edi
0x180082526  mov     rcx, rax
0x180082529  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008252f  mov     rcx, cs:WPP_GLOBAL_Control
0x180082536  cmp     rcx, rbx
0x180082539  jz      loc_180082724
0x18008253f  test    byte ptr [rcx+1Ch], 1
0x180082543  jz      loc_180082724
0x180082549  cmp     byte ptr [rcx+19h], 2
0x18008254d  jb      loc_180082724
0x180082553  mov     edx, 1B2h
0x180082558  mov     r9d, edi
0x18008255b  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180082562  mov     rcx, [rcx+10h]
0x180082566  call    WPP_SF_d
0x18008256b  jmp     loc_180082724
0x180082570  mov     eax, 2008h
0x180082575  cmp     word ptr [rbp+4Fh+pvarg], ax
0x180082579  jz      loc_18008260A
0x18008257f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180082585  or      edx, 0FFFFFFFFh
0x180082588  mov     rcx, rax
0x18008258b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180082591  lea     rbx, WPP_GLOBAL_Control
0x180082598  mov     rcx, cs:WPP_GLOBAL_Control
0x18008259f  cmp     rcx, rbx
0x1800825a2  jz      loc_180082722
0x1800825a8  test    byte ptr [rcx+1Ch], 1
0x1800825ac  jz      short loc_1800825D0
0x1800825ae  cmp     byte ptr [rcx+19h], 2
0x1800825b2  jb      short loc_1800825D0
0x1800825b4  mov     edx, 1B3h
0x1800825b9  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x1800825c0  mov     rcx, [rcx+10h]
0x1800825c4  call    WPP_SF_
0x1800825c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800825d0  cmp     rcx, rbx
0x1800825d3  jz      loc_180082722
0x1800825d9  test    byte ptr [rcx+1Ch], 1
0x1800825dd  jz      loc_180082722
0x1800825e3  cmp     byte ptr [rcx+19h], 2
0x1800825e7  jb      loc_180082722
0x1800825ed  mov     edx, 1B4h
0x1800825f2  xor     r9d, r9d
0x1800825f5  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x1800825fc  mov     rcx, [rcx+10h]
0x180082600  call    WPP_SF_d
0x180082605  jmp     loc_180082722
0x18008260a  mov     dword ptr [r15], 1
0x180082611  mov     [rsp+0B0h+var_90], 20h ; ' '
0x180082619  mov     r9d, 5
0x18008261f  lea     r8d, [r9+3]
0x180082623  mov     rdx, qword ptr [rbp+4Fh+pvarg+8]
0x180082627  lea     rcx, [rbp+4Fh+var_60]
0x18008262b  call    cs:__imp_??0CSafeArray@@QEAA@PEAUtagSAFEARRAY@@HHH@Z; CSafeArray::CSafeArray(tagSAFEARRAY *,int,int,int)
0x180082631  nop
0x180082632  xor     ebx, ebx
0x180082634  lea     rcx, [rbp+4Fh+var_60]
0x180082638  call    cs:__imp_?Size@CSafeArray@@QEAAHXZ; CSafeArray::Size(void)
0x18008263e  cmp     ebx, eax
0x180082640  jge     loc_1800826E0
0x180082646  mov     edx, ebx
0x180082648  lea     rcx, [rbp+4Fh+var_60]
0x18008264c  call    cs:__imp_?GetBSTRAt@CSafeArray@@QEAAPEAGH@Z; CSafeArray::GetBSTRAt(int)
0x180082652  mov     [rbp+4Fh+arg_0], rax
0x180082656  test    rax, rax
0x180082659  jz      short loc_18008266C
0x18008265b  mov     rdx, rax
0x18008265e  mov     rcx, [rbp+4Fh+arg_20]
0x180082662  call    cs:__imp_?Add@CWStringArray@@QEAAHPEBG@Z; CWStringArray::Add(ushort const *)
0x180082668  test    eax, eax
0x18008266a  jnz     short loc_180082679
0x18008266c  lea     rcx, [rbp+4Fh+arg_0]; this
0x180082670  call    ??1CSysFreeMe@@QEAA@XZ; CSysFreeMe::~CSysFreeMe(void)
0x180082675  inc     ebx
0x180082677  jmp     short loc_180082634
0x180082679  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008267f  mov     edi, 80041006h
0x180082684  mov     edx, edi
0x180082686  mov     rcx, rax
0x180082689  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008268f  lea     rbx, WPP_GLOBAL_Control
0x180082696  mov     rcx, cs:WPP_GLOBAL_Control
0x18008269d  cmp     rcx, rbx
0x1800826a0  jz      short loc_1800826CA
0x1800826a2  test    byte ptr [rcx+1Ch], 1
0x1800826a6  jz      short loc_1800826CA
0x1800826a8  cmp     byte ptr [rcx+19h], 2
0x1800826ac  jb      short loc_1800826CA
0x1800826ae  mov     edx, 1B5h
0x1800826b3  mov     r9d, 80041006h
0x1800826b9  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x1800826c0  mov     rcx, [rcx+10h]
0x1800826c4  call    WPP_SF_d
0x1800826c9  nop
0x1800826ca  lea     rcx, [rbp+4Fh+arg_0]; this
0x1800826ce  call    ??1CSysFreeMe@@QEAA@XZ; CSysFreeMe::~CSysFreeMe(void)
0x1800826d3  nop
0x1800826d4  lea     rcx, [rbp+4Fh+var_60]
0x1800826d8  call    cs:__imp_??1CSafeArray@@QEAA@XZ; CSafeArray::~CSafeArray(void)
0x1800826de  jmp     short loc_180082724
0x1800826e0  lea     rbx, WPP_GLOBAL_Control
0x1800826e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800826ee  cmp     rcx, rbx
0x1800826f1  jz      short loc_180082718
0x1800826f3  test    byte ptr [rcx+1Ch], 1
0x1800826f7  jz      short loc_180082718
0x1800826f9  cmp     byte ptr [rcx+19h], 2
0x1800826fd  jb      short loc_180082718
0x1800826ff  mov     edx, 1B6h
0x180082704  xor     r9d, r9d
0x180082707  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18008270e  mov     rcx, [rcx+10h]
0x180082712  call    WPP_SF_d
0x180082717  nop
0x180082718  lea     rcx, [rbp+4Fh+var_60]
0x18008271c  call    cs:__imp_??1CSafeArray@@QEAA@XZ; CSafeArray::~CSafeArray(void)
0x180082722  xor     edi, edi
0x180082724  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x180082728  call    cs:__imp_VariantClear
0x18008272e  mov     eax, edi
0x180082730  add     rsp, 88h
0x180082737  pop     r15
0x180082739  pop     r14
0x18008273b  pop     rdi
0x18008273c  pop     rsi
0x18008273d  pop     rbx
0x18008273e  pop     rbp
0x18008273f  retn
```
