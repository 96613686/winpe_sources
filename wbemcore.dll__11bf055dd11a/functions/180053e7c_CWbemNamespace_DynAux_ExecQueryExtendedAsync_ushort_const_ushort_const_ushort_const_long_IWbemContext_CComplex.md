# CWbemNamespace::DynAux_ExecQueryExtendedAsync(ushort const *,ushort const *,ushort const *,long,IWbemContext *,CComplexProjectionSink *)

- ea: `0x180053e7c`
- end: `0x180054465`
- name: `?DynAux_ExecQueryExtendedAsync@CWbemNamespace@@QEAAJPEBG00JPEAUIWbemContext@@PEAVCComplexProjectionSink@@@Z`
- size: `1513`
- prototype: `__int64 __usercall@<rax>(CWbemNamespace *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, int, struct IWbemContext *, struct CComplexProjectionSink *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180053530`

## callees

- `0x18000aadc`
- `0x18000b140`
- `0x18001307c`
- `0x180039c50`
- `0x180039d40`
- `0x180039f68`
- `0x18003be20`
- `0x18003cfe0`
- `0x180053e7c`
- `0x1800da010`

## import_xrefs

- `wbemcomn!?GetFirst_ms_XXX_Locale@CMUILocaleList@@QEAAJPEAPEAG@Z` at `0x180053f24`
- `wbemcomn!?GetFirst_ms_XXX_Locale@CMUILocaleList@@QEAAJPEAPEAG@Z` at `0x180053f24`
- `wbemcomn!?_Free@CMUILocale@@SAHPEAX@Z` at `0x180053f38`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800541a6`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800541a6`
- `wbemcomn!GetMemLogObject` at `0x180054124`
- `wbemcomn!GetMemLogObject` at `0x1800542ce`
- `wbemcomn!GetMemLogObject` at `0x180054330`
- `wbemcomn!GetMemLogObject` at `0x180054389`
- `wbemcomn!GetMemLogObject` at `0x1800543e4`
- `wbemcomn!GetMemLogObject` at `0x180054124`
- `wbemcomn!GetMemLogObject` at `0x1800542ce`
- `wbemcomn!GetMemLogObject` at `0x180054330`
- `wbemcomn!GetMemLogObject` at `0x180054389`
- `wbemcomn!GetMemLogObject` at `0x1800543e4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005412f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800542de`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005433b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180054395`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800543f4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005412f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800542de`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005433b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180054395`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800543f4`
- `OLEAUT32!__imp_SysAllocString` at `0x1800541e7`
- `OLEAUT32!__imp_SysAllocString` at `0x1800541fb`
- `OLEAUT32!__imp_SysAllocString` at `0x1800541e7`
- `OLEAUT32!__imp_SysAllocString` at `0x1800541fb`
- `OLEAUT32!__imp_SysFreeString` at `0x180054239`
- `OLEAUT32!__imp_SysFreeString` at `0x180054248`
- `OLEAUT32!__imp_SysFreeString` at `0x180054239`
- `OLEAUT32!__imp_SysFreeString` at `0x180054248`
- `OLEAUT32!__imp_VariantInit` at `0x18005402b`
- `OLEAUT32!__imp_VariantInit` at `0x18005402b`
- `OLEAUT32!__imp_VariantClear` at `0x180054080`
- `OLEAUT32!__imp_VariantClear` at `0x180054080`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CWbemNamespace::DynAux_ExecQueryExtendedAsync(
        CWbemNamespace *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned int a5,
        struct IWbemContext *a6,
        struct CComplexProjectionSink *a7)
{
  CBasicObjectSink *v10; // r15
  unsigned int First_ms_XXX_Locale; // ebx
  IRecordInfo *v12; // rdi
  __int64 v13; // rcx
  int v14; // r12d
  unsigned __int16 *v15; // rbx
  CDecoratingSink *v16; // r12
  __int64 v17; // rdi
  struct IWbemContext *v18; // rsi
  int v19; // esi
  CObjectSink *v20; // rcx
  CMemoryLog *v22; // rax
  CDecoratingSink *v23; // rax
  OLECHAR *v24; // r15
  OLECHAR *v25; // r13
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v27; // rax
  CMemoryLog *v28; // rax
  int v29; // edx
  CMemoryLog *v30; // rax
  unsigned __int16 *v31; // [rsp+70h] [rbp-59h] BYREF
  __int64 v32; // [rsp+78h] [rbp-51h] BYREF
  __int64 v33; // [rsp+80h] [rbp-49h] BYREF
  CDecoratingSink *v34; // [rsp+88h] [rbp-41h]
  _BYTE v35[8]; // [rsp+90h] [rbp-39h] BYREF
  CObjectSink *v36; // [rsp+98h] [rbp-31h]
  VARIANTARG pvarg; // [rsp+A0h] [rbp-29h] BYREF
  __int128 v38; // [rsp+B8h] [rbp-11h] BYREF
  OLECHAR *v39; // [rsp+C8h] [rbp-1h]
  IRecordInfo *v41; // [rsp+130h] [rbp+67h] BYREF

  v41 = (IRecordInfo *)a4;
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_SSS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      385,
      (unsigned int)WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
      (_DWORD)a2,
      (__int64)a3,
      (__int64)L"WQL");
  }
  v10 = a7;
  COperationError::COperationError((COperationError *)v35, a7, L"ExecQuery", a3, 0);
  if ( !v35[0] )
  {
    MemLogObject = GetMemLogObject();
    First_ms_XXX_Locale = -2147217402;
    CMemoryLog::Write(MemLogObject, -2147217402);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 386, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749894LL);
    }
    goto LABEL_71;
  }
  v31 = 0;
  if ( !*((_QWORD *)this + 31) )
  {
    v14 = -2147217398;
LABEL_59:
    v28 = GetMemLogObject();
    CMemoryLog::Write(v28, v14);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        388,
        WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
        (unsigned int)v14);
    }
    v29 = v14;
    goto LABEL_65;
  }
  v41 = 0;
  First_ms_XXX_Locale = CMUILocaleList::GetFirst_ms_XXX_Locale(
                          (CWbemNamespace *)((char *)this + 176),
                          (unsigned __int16 **)&v41);
  if ( (First_ms_XXX_Locale & 0x80000000) != 0 )
  {
    v27 = GetMemLogObject();
    CMemoryLog::Write(v27, First_ms_XXX_Locale);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        387,
        WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
        First_ms_XXX_Locale);
    }
    (*(void (__fastcall **)(CBasicObjectSink *, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v10 + 32LL))(
      v10,
      0,
      First_ms_XXX_Locale,
      0,
      0);
    if ( v36 )
      CObjectSink::Release(v36);
    return First_ms_XXX_Locale;
  }
  v12 = v41;
  LOBYTE(pvarg.vt) = 0;
  pvarg.llVal = (LONGLONG)CMUILocale::_Free;
  pvarg.pRecInfo = v41;
  v13 = *((_QWORD *)this + 31);
  v38 = 0;
  v14 = (*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD, struct IWbemContext *, _QWORD, _QWORD, IRecordInfo *, _QWORD, const unsigned __int16 *, GUID *, unsigned __int16 **))(*(_QWORD *)v13 + 40LL))(
          v13,
          &v38,
          0,
          a6,
          0,
          *((_QWORD *)this + 14),
          v41,
          0,
          a2,
          &IID_IWbemServices,
          &v31);
  ((void (__fastcall *)(IRecordInfo *))CMUILocale::_Free)(v12);
  if ( v14 < 0 )
    goto LABEL_59;
  v15 = v31;
  v16 = 0;
  if ( !v31 )
  {
    v29 = -2147217402;
LABEL_65:
    First_ms_XXX_Locale = CBasicObjectSink::Return(v10, v29, 0);
LABEL_71:
    COperationError::~COperationError((COperationError *)v35);
    return First_ms_XXX_Locale;
  }
  v41 = (IRecordInfo *)v31;
  v32 = 0;
  if ( (**(int (__fastcall ***)(unsigned __int16 *, GUID *, __int64 *))v31)(v31, &IID__IWmiProviderConfiguration, &v32) < 0 )
  {
    v19 = -2147217379;
LABEL_25:
    v22 = GetMemLogObject();
    CMemoryLog::Write(v22, v19);
    goto LABEL_26;
  }
  v17 = v32;
  v33 = v32;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v18 = a6;
  if ( (*(int (__fastcall **)(__int64, CWbemNamespace *, _QWORD, struct IWbemContext *, _DWORD, _DWORD, VARIANTARG *))(*(_QWORD *)v32 + 72LL))(
         v32,
         this,
         a5,
         a6,
         0,
         0,
         &pvarg) >= 0 )
  {
    if ( pvarg.iVal != -1 )
    {
      v19 = -2147217385;
LABEL_12:
      VariantClear(&pvarg);
      goto LABEL_13;
    }
    v23 = (CDecoratingSink *)CWin32DefaultArena::WbemMemAlloc(0x38u);
    v34 = v23;
    if ( v23 )
      v16 = CDecoratingSink::CDecoratingSink(v23, v10, this);
    if ( v16 )
    {
      (*(void (__fastcall **)(CDecoratingSink *))(*(_QWORD *)v16 + 8LL))(v16);
      v34 = v16;
      v24 = SysAllocString(a3);
      v39 = v24;
      v25 = SysAllocString(L"WQL");
      *(_QWORD *)&v38 = v25;
      v19 = (*(__int64 (__fastcall **)(unsigned __int16 *, OLECHAR *, OLECHAR *, _QWORD, struct IWbemContext *, CDecoratingSink *))(*(_QWORD *)v31 + 168LL))(
              v31,
              v25,
              v24,
              a5,
              v18,
              v16);
      if ( v25 )
        SysFreeString(v25);
      if ( v24 )
        SysFreeString(v24);
      (*(void (__fastcall **)(CDecoratingSink *))(*(_QWORD *)v16 + 16LL))(v16);
      v34 = 0;
      goto LABEL_12;
    }
    v30 = GetMemLogObject();
    CMemoryLog::Write(v30, -2147217402);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 389, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749894LL);
    }
    First_ms_XXX_Locale = CBasicObjectSink::Return(v10, -2147217402, 0);
    CReleaseMe::release((CReleaseMe *)&v33);
    CReleaseMe::release((CReleaseMe *)&v41);
    goto LABEL_71;
  }
  v19 = -2147217379;
LABEL_13:
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  v33 = 0;
  if ( v19 == -2147217385 )
  {
    if ( v15 )
      (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v15 + 16LL))(v15);
    v41 = 0;
    v20 = v36;
    if ( v36 && _InterlockedExchangeAdd((volatile signed __int32 *)v36 + 4, 0xFFFFFFFF) == 1 )
    {
      if ( v20 )
        (*(void (__fastcall **)(CObjectSink *, __int64))(*(_QWORD *)v20 + 80LL))(v20, 1);
    }
    return 2147749911LL;
  }
  if ( v19 < 0 )
    goto LABEL_25;
LABEL_26:
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      390,
      WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
      (unsigned int)v19);
  }
  if ( v15 )
    (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v15 + 16LL))(v15);
  v41 = 0;
  if ( v36 )
    CObjectSink::Release(v36);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x180053e7c  mov     rax, rsp
0x180053e7f  mov     [rax+8], rbx
0x180053e83  mov     [rax+10h], rsi
0x180053e87  mov     [rax+20h], r9
0x180053e8b  mov     [rax+18h], r8
0x180053e8f  push    rbp
0x180053e90  push    rdi
0x180053e91  push    r12
0x180053e93  push    r13
0x180053e95  push    r15
0x180053e97  lea     rbp, [rax-47h]
0x180053e9b  sub     rsp, 0E0h
0x180053ea2  movaps  xmmword ptr [rax-38h], xmm6
0x180053ea6  mov     rbx, r8
0x180053ea9  mov     r12, rdx
0x180053eac  mov     r13, rcx
0x180053eaf  xor     edi, edi
0x180053eb1  mov     [rbp+3Fh+var_A0], edi
0x180053eb4  lea     rsi, WPP_GLOBAL_Control
0x180053ebb  lea     rax, aWql; "WQL"
0x180053ec2  mov     rcx, cs:WPP_GLOBAL_Control
0x180053ec9  cmp     rcx, rsi
0x180053ecc  jz      short loc_180053ED8
0x180053ece  test    byte ptr [rcx+1Ch], 1
0x180053ed2  jnz     loc_18005429D
0x180053ed8  mov     [rsp+100h+var_E0], edi; int
0x180053edc  mov     r9, rbx; unsigned __int16 *
0x180053edf  lea     r8, aExecquery; "ExecQuery"
0x180053ee6  mov     r15, [rbp+3Fh+arg_30]
0x180053eea  mov     rdx, r15; struct CBasicObjectSink *
0x180053eed  lea     rcx, [rbp+3Fh+var_78]; this
0x180053ef1  call    ??0COperationError@@QEAA@PEAVCBasicObjectSink@@PEBG1H@Z; COperationError::COperationError(CBasicObjectSink *,ushort const *,ushort const *,int)
0x180053ef6  nop
0x180053ef7  cmp     [rbp+3Fh+var_78], dil
0x180053efb  jz      loc_1800542CE
0x180053f01  mov     [rbp+3Fh+var_98], rdi
0x180053f05  cmp     [r13+0F8h], rdi
0x180053f0c  jz      loc_180054328
0x180053f12  xorps   xmm6, xmm6
0x180053f15  mov     [rbp+3Fh+arg_18], rdi
0x180053f19  lea     rcx, [r13+0B0h]
0x180053f20  lea     rdx, [rbp+3Fh+arg_18]
0x180053f24  call    cs:__imp_?GetFirst_ms_XXX_Locale@CMUILocaleList@@QEAAJPEAPEAG@Z; CMUILocaleList::GetFirst_ms_XXX_Locale(ushort * *)
0x180053f2a  mov     ebx, eax
0x180053f2c  test    eax, eax
0x180053f2e  js      loc_180054330
0x180053f34  mov     rdi, [rbp+3Fh+arg_18]
0x180053f38  mov     rsi, cs:__imp_?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x180053f3f  xor     r8d, r8d
0x180053f42  mov     byte ptr [rbp+3Fh+pvarg], r8b
0x180053f46  mov     qword ptr [rbp+3Fh+pvarg+8], rsi
0x180053f4a  mov     qword ptr [rbp+3Fh+pvarg+10h], rdi
0x180053f4e  mov     [rbp+3Fh+var_A0], 2
0x180053f55  lea     ebx, [r8+2]
0x180053f59  and     ebx, 0FFFFFFFDh
0x180053f5c  mov     [rbp+3Fh+var_A0], ebx
0x180053f5f  or      ebx, 1
0x180053f62  mov     [rbp+3Fh+var_A0], ebx
0x180053f65  mov     rcx, [r13+0F8h]
0x180053f6c  movdqa  [rbp+3Fh+var_50], xmm6
0x180053f71  mov     rax, [rcx]
0x180053f74  lea     rdx, [rbp+3Fh+var_98]
0x180053f78  mov     [rsp+100h+var_B0], rdx
0x180053f7d  lea     rdx, IID_IWbemServices
0x180053f84  mov     [rsp+100h+var_B8], rdx
0x180053f89  mov     [rsp+100h+var_C0], r12
0x180053f8e  mov     [rsp+100h+var_C8], r8
0x180053f93  mov     rdx, [rbp+3Fh+arg_18]
0x180053f97  mov     [rsp+100h+var_D0], rdx
0x180053f9c  mov     rdx, [r13+70h]
0x180053fa0  mov     [rsp+100h+var_D8], rdx
0x180053fa5  mov     qword ptr [rsp+100h+var_E0], r8
0x180053faa  mov     r9, [rbp+3Fh+arg_28]
0x180053fae  lea     rdx, [rbp+3Fh+var_50]
0x180053fb2  mov     rax, [rax+28h]
0x180053fb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053fbb  mov     r12d, eax
0x180053fbe  and     ebx, 0FFFFFFFEh
0x180053fc1  mov     [rbp+3Fh+var_A0], ebx
0x180053fc4  mov     rcx, rdi
0x180053fc7  mov     rax, rsi
0x180053fca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053fcf  test    r12d, r12d
0x180053fd2  js      loc_180054382
0x180053fd8  mov     rbx, [rbp+3Fh+var_98]
0x180053fdc  xor     r12d, r12d
0x180053fdf  test    rbx, rbx
0x180053fe2  jz      loc_1800543D0
0x180053fe8  mov     [rbp+3Fh+arg_18], rbx
0x180053fec  mov     [rbp+3Fh+var_90], r12
0x180053ff0  mov     rcx, [rbp+3Fh+var_98]
0x180053ff4  mov     rax, [rcx]
0x180053ff7  lea     r8, [rbp+3Fh+var_90]
0x180053ffb  lea     rdx, IID__IWmiProviderConfiguration
0x180054002  mov     rax, [rax]
0x180054005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005400a  test    eax, eax
0x18005400c  js      loc_18005411F
0x180054012  mov     rdi, [rbp+3Fh+var_90]
0x180054016  mov     [rbp+3Fh+var_88], rdi
0x18005401a  xorps   xmm0, xmm0
0x18005401d  xor     eax, eax
0x18005401f  movups  xmmword ptr [rbp+3Fh+pvarg], xmm0
0x180054023  mov     qword ptr [rbp+3Fh+pvarg+10h], rax
0x180054027  lea     rcx, [rbp+3Fh+pvarg]; pvarg
0x18005402b  call    cs:__imp_VariantInit
0x180054031  mov     rcx, [rbp+3Fh+var_90]
0x180054035  mov     rax, [rcx]
0x180054038  lea     rdx, [rbp+3Fh+pvarg]
0x18005403c  mov     [rsp+100h+var_D0], rdx
0x180054041  mov     dword ptr [rsp+100h+var_D8], r12d
0x180054046  mov     [rsp+100h+var_E0], r12d
0x18005404b  mov     rsi, [rbp+3Fh+arg_28]
0x18005404f  mov     r9, rsi
0x180054052  mov     r8d, [rbp+3Fh+arg_20]
0x180054056  mov     rdx, r13
0x180054059  mov     rax, [rax+48h]
0x18005405d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054062  or      ecx, 0FFFFFFFFh
0x180054065  test    eax, eax
0x180054067  js      loc_180054115
0x18005406d  cmp     word ptr [rbp+3Fh+pvarg+8], cx
0x180054071  jz      loc_1800541A1
0x180054077  mov     esi, 80041017h
0x18005407c  lea     rcx, [rbp+3Fh+pvarg]; pvarg
0x180054080  call    cs:__imp_VariantClear
0x180054086  nop
0x180054087  test    rdi, rdi
0x18005408a  jz      short loc_18005409B
0x18005408c  mov     rax, [rdi]
0x18005408f  mov     rcx, rdi
0x180054092  mov     rax, [rax+10h]
0x180054096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005409b  mov     [rbp+3Fh+var_88], r12
0x18005409f  mov     edi, 80041017h
0x1800540a4  cmp     esi, edi
0x1800540a6  jnz     loc_18005417B
0x1800540ac  test    rbx, rbx
0x1800540af  jz      short loc_1800540C0
0x1800540b1  mov     rax, [rbx]
0x1800540b4  mov     rcx, rbx
0x1800540b7  mov     rax, [rax+10h]
0x1800540bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800540c0  mov     [rbp+3Fh+arg_18], r12
0x1800540c4  mov     rcx, [rbp+3Fh+var_70]
0x1800540c8  test    rcx, rcx
0x1800540cb  jz      short loc_1800540DA
0x1800540cd  or      eax, 0FFFFFFFFh
0x1800540d0  lock xadd [rcx+10h], eax
0x1800540d5  cmp     eax, 1
0x1800540d8  jz      short loc_1800540FD
0x1800540da  mov     eax, edi
0x1800540dc  lea     r11, [rsp+100h+var_20]
0x1800540e4  mov     rbx, [r11+30h]
0x1800540e8  mov     rsi, [r11+38h]
0x1800540ec  movaps  xmm6, xmmword ptr [r11-10h]
0x1800540f1  mov     rsp, r11
0x1800540f4  pop     r15
0x1800540f6  pop     r13
0x1800540f8  pop     r12
0x1800540fa  pop     rdi
0x1800540fb  pop     rbp
0x1800540fc  retn
0x1800540fd  test    rcx, rcx
0x180054100  jz      short loc_1800540DA
0x180054102  mov     r8, [rcx]
0x180054105  mov     edx, 1
0x18005410a  mov     rax, [r8+50h]
0x18005410e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054113  jmp     short loc_1800540DA
0x180054115  mov     esi, 8004101Dh
0x18005411a  jmp     loc_180054087
0x18005411f  mov     esi, 8004101Dh
0x180054124  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18005412a  mov     edx, esi
0x18005412c  mov     rcx, rax
0x18005412f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180054135  mov     rcx, cs:WPP_GLOBAL_Control
0x18005413c  lea     rax, WPP_GLOBAL_Control
0x180054143  cmp     rcx, rax
0x180054146  jz      short loc_18005414E
0x180054148  test    byte ptr [rcx+1Ch], 1
0x18005414c  jnz     short loc_180054181
0x18005414e  test    rbx, rbx
0x180054151  jz      short loc_180054162
0x180054153  mov     rax, [rbx]
0x180054156  mov     rcx, rbx
0x180054159  mov     rax, [rax+10h]
0x18005415d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054162  mov     [rbp+3Fh+arg_18], r12
0x180054166  mov     rcx, [rbp+3Fh+var_70]; this
0x18005416a  test    rcx, rcx
0x18005416d  jz      short loc_180054174
0x18005416f  call    ?Release@CObjectSink@@UEAAKXZ; CObjectSink::Release(void)
0x180054174  mov     eax, esi
0x180054176  jmp     loc_1800540DC
0x18005417b  test    esi, esi
0x18005417d  js      short loc_180054124
0x18005417f  jmp     short loc_180054135
0x180054181  cmp     byte ptr [rcx+19h], 2
0x180054185  jb      short loc_18005414E
0x180054187  mov     edx, 186h
0x18005418c  mov     r9d, esi
0x18005418f  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180054196  mov     rcx, [rcx+10h]
0x18005419a  call    WPP_SF_d
0x18005419f  jmp     short loc_18005414E
0x1800541a1  mov     ecx, 38h ; '8'
0x1800541a6  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800541ac  mov     [rbp+3Fh+var_80], rax
0x1800541b0  test    rax, rax
0x1800541b3  jz      short loc_1800541C6
0x1800541b5  mov     r8, r13; struct CWbemNamespace *
0x1800541b8  mov     rdx, r15; struct CBasicObjectSink *
0x1800541bb  mov     rcx, rax; this
0x1800541be  call    ??0CDecoratingSink@@QEAA@PEAVCBasicObjectSink@@PEAVCWbemNamespace@@@Z; CDecoratingSink::CDecoratingSink(CBasicObjectSink *,CWbemNamespace *)
0x1800541c3  mov     r12, rax
0x1800541c6  test    r12, r12
0x1800541c9  jz      loc_1800543E4
0x1800541cf  mov     rax, [r12]
0x1800541d3  mov     rcx, r12
0x1800541d6  mov     rax, [rax+8]
0x1800541da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800541df  mov     [rbp+3Fh+var_80], r12
0x1800541e3  mov     rcx, [rbp+3Fh+psz]; psz
0x1800541e7  call    cs:__imp_SysAllocString
0x1800541ed  mov     r15, rax
0x1800541f0  mov     [rbp+3Fh+var_40], rax
0x1800541f4  lea     rcx, aWql; "WQL"
0x1800541fb  call    cs:__imp_SysAllocString
0x180054201  mov     r13, rax
0x180054204  mov     qword ptr [rbp+3Fh+var_50], rax
0x180054208  mov     rcx, [rbp+3Fh+var_98]
0x18005420c  mov     rdx, [rcx]
0x18005420f  mov     rax, [rdx+0A8h]
0x180054216  mov     [rsp+100h+var_D8], r12
0x18005421b  mov     qword ptr [rsp+100h+var_E0], rsi
0x180054220  mov     r9d, [rbp+3Fh+arg_20]
0x180054224  mov     r8, r15
0x180054227  mov     rdx, r13
0x18005422a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005422f  mov     esi, eax
0x180054231  test    r13, r13
0x180054234  jz      short loc_180054240
0x180054236  mov     rcx, r13; bstrString
0x180054239  call    cs:__imp_SysFreeString
0x18005423f  nop
0x180054240  test    r15, r15
0x180054243  jz      short loc_18005424F
0x180054245  mov     rcx, r15; bstrString
0x180054248  call    cs:__imp_SysFreeString
0x18005424e  nop
0x18005424f  mov     rax, [r12]
0x180054253  mov     rcx, r12
0x180054256  mov     rax, [rax+10h]
0x18005425a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005425f  xor     r12d, r12d
0x180054262  mov     [rbp+3Fh+var_80], r12
0x180054266  jmp     loc_18005407C
0x18005426b  mov     rax, [r15]
0x18005426e  mov     qword ptr [rsp+100h+var_E0], rdi
0x180054273  xor     r9d, r9d
0x180054276  mov     r8d, ebx
0x180054279  xor     edx, edx
0x18005427b  mov     rcx, r15
0x18005427e  mov     rax, [rax+20h]
0x180054282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054287  nop
0x180054288  mov     rcx, [rbp+3Fh+var_70]; this
0x18005428c  test    rcx, rcx
0x18005428f  jz      short loc_180054296
0x180054291  call    ?Release@CObjectSink@@UEAAKXZ; CObjectSink::Release(void)
0x180054296  mov     eax, ebx
0x180054298  jmp     loc_1800540DC
0x18005429d  cmp     byte ptr [rcx+19h], 5
0x1800542a1  jb      loc_180053ED8
0x1800542a7  mov     edx, 181h
0x1800542ac  mov     [rsp+100h+var_D8], rax
0x1800542b1  mov     qword ptr [rsp+100h+var_E0], rbx
0x1800542b6  mov     r9, r12
0x1800542b9  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x1800542c0  mov     rcx, [rcx+10h]
0x1800542c4  call    WPP_SF_SSS
0x1800542c9  jmp     loc_180053ED8
0x1800542ce  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800542d4  mov     ebx, 80041006h
0x1800542d9  mov     edx, ebx
0x1800542db  mov     rcx, rax
0x1800542de  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800542e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800542eb  cmp     rcx, rsi
0x1800542ee  jz      loc_180054457
0x1800542f4  test    byte ptr [rcx+1Ch], 1
0x1800542f8  jz      loc_180054457
0x1800542fe  cmp     byte ptr [rcx+19h], 2
0x180054302  jb      loc_180054457
0x180054308  mov     edx, 182h
0x18005430d  mov     r9d, 80041006h
0x180054313  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18005431a  mov     rcx, [rcx+10h]
  ... truncated ...
```
