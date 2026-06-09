# CheckXResAndUpdate(uchar *,_WIA_PROPERTY_CONTEXT *,long)

- ea: `0x180057734`
- end: `0x180057d3d`
- name: `?CheckXResAndUpdate@@YAJPEAEPEAU_WIA_PROPERTY_CONTEXT@@J@Z`
- size: `1545`
- prototype: `__int64 __fastcall(struct IWiaItem *this, struct _WIA_PROPERTY_CONTEXT *, int)`
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180043b00`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000da10`
- `0x18000dd00`
- `0x1800178b0`
- `0x180018390`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002de18`
- `0x18002def8`
- `0x180040750`
- `0x180043880`
- `0x180057734`
- `0x1800591c0`

## string_xrefs

- `0x18005775b`: `::CheckXResAndUpdate`
- `0x180057a4e`: `could not write value for WIA_IPS_XPOS`
- `0x180057a74`: `could not write value for WIA_IPS_XPOS`
- `0x18005776a`: `CheckXResAndUpdate`
- `0x180057a5d`: `CheckXResAndUpdate`
- `0x180057b5e`: `CheckXResAndUpdate`
- `0x180057b84`: `CheckXResAndUpdate`
- `0x180057cdb`: `CheckXResAndUpdate`
- `0x180057d10`: `CheckXResAndUpdate`
- `0x180057893`: `could not read WIA_IPS_MIN_HORIZONTAL_SIZE`
- `0x1800578b5`: `could not read WIA_IPS_MIN_HORIZONTAL_SIZE`
- `0x180057b4f`: `could not write value for WIA_IPS_XEXTENT`
- `0x180057b75`: `could not write value for WIA_IPS_XEXTENT`

## pseudocode

```c
__int64 __fastcall CheckXResAndUpdate(struct IWiaItem *this, struct _WIA_PROPERTY_CONTEXT *a2, int a3)
{
  struct tagWiaTraceData_Type *v5; // rax
  char *v6; // rdx
  unsigned int v7; // r8d
  int ChangedValueLong; // ebx
  int v10; // r12d
  int PropLong; // edi
  char *v12; // rbx
  void *v13; // rdx
  void **v14; // rax
  void *v15; // rdx
  __int64 v16; // rcx
  int v17; // edx
  int v18; // ecx
  int v19; // eax
  char *v20; // rbx
  void *v21; // rdx
  void **v22; // rax
  void *v23; // rdx
  __int64 v24; // rcx
  int v25; // r15d
  int v26; // edx
  int v27; // r13d
  int v28; // edx
  unsigned int v29; // ebx
  int v30; // r12d
  char *v31; // rbx
  void *v32; // rdx
  int v33; // edi
  int v34; // ebx
  int v35; // eax
  char *v36; // rbx
  void *v37; // rdx
  int v38; // ebx
  int v39; // eax
  int v40; // r14d
  char *v41; // rbx
  void *v42; // rdx
  void **v43; // rax
  void *v44; // rdx
  __int64 v45; // rcx
  unsigned int lpMem; // [rsp+20h] [rbp-E0h]
  int v47; // [rsp+30h] [rbp-D0h] BYREF
  int v48; // [rsp+34h] [rbp-CCh]
  int v49; // [rsp+38h] [rbp-C8h] BYREF
  int v50; // [rsp+3Ch] [rbp-C4h] BYREF
  __int64 v51[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v52; // [rsp+50h] [rbp-B0h]
  __int64 v53[2]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v54; // [rsp+78h] [rbp-88h]
  __int64 v55[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v56; // [rsp+A0h] [rbp-60h]
  _BYTE v57[128]; // [rsp+C0h] [rbp-40h] BYREF
  int v58; // [rsp+168h] [rbp+68h]
  int v59; // [rsp+168h] [rbp+68h]

  v5 = (struct tagWiaTraceData_Type *)WiaTrace_Trace("::CheckXResAndUpdate");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v57, v6, v7, "CheckXResAndUpdate", lpMem, v5);
  v49 = 0;
  v47 = 0;
  v50 = 0;
  v48 = 0;
  *(_OWORD *)v53 = 0;
  v54 = 0;
  *(_OWORD *)v55 = 0;
  v56 = 0;
  *(_OWORD *)v51 = 0;
  v52 = 0;
  ChangedValueLong = wiasGetChangedValueLong(this, (__int64)v53);
  if ( ChangedValueLong < 0
    || (wiasReadPropLong((CWiaItem *)this, 0),
        v10 = v53[0],
        ChangedValueLong = wiasGetChangedValueLong(this, (__int64)v55),
        ChangedValueLong < 0)
    || (ChangedValueLong = GetMinAndMaxLong((CWiaItem *)this, 0x1807u, &v49, &v47), ChangedValueLong < 0)
    || (ChangedValueLong = GetMinAndMaxLong((CWiaItem *)this, 0x1805u, 0, &v50), ChangedValueLong < 0) )
  {
    CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v57);
    return (unsigned int)ChangedValueLong;
  }
  PropLong = wiasReadPropLong((CWiaItem *)this, 0);
  if ( PropLong < 0 )
  {
    v12 = (char *)WiaTrace_TraceLog("could not read WIA_IPS_MIN_HORIZONTAL_SIZE");
    WriteDbgTraceErrorWI("CheckXResAndUpdate", v12);
    WiaTrcLib::Free((WiaTrcLib *)v12, v13);
    v14 = (void **)WiaTrace_Trace("could not read WIA_IPS_MIN_HORIZONTAL_SIZE");
LABEL_36:
    WiaTrace_ProcessTrace_Ex(v16, v15, (void *)"CheckXResAndUpdate", 1, v14);
    goto LABEL_37;
  }
  if ( PropLong )
  {
    v20 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0, 0, "WIA_IPS_MIN_HORIZONTAL_SIZE was not present");
    WriteDbgTraceInfoWI("CheckXResAndUpdate", v20);
    WiaTrcLib::Free((WiaTrcLib *)v20, v21);
    v22 = (void **)WiaTrace_TraceWithSubCompTraceLevel(0, 0, "WIA_IPS_MIN_HORIZONTAL_SIZE was not present");
    WiaTrace_ProcessTrace_Ex(v24, v23, (void *)"CheckXResAndUpdate", 4, v22);
    v17 = DWORD2(v54);
    v19 = (int)(float)((float)((float)((float)SDWORD2(v54) * (float)v49) / (float)SLODWORD(v53[1])) + 0.5);
  }
  else
  {
    v17 = DWORD2(v54);
    v18 = 1;
    if ( (int)(float)((float)((float)((float)SDWORD2(v54) * (float)v48) / 1000.0) + 0.5) > 0 )
      v18 = (int)(float)((float)((float)((float)SDWORD2(v54) * (float)v48) / 1000.0) + 0.5);
    v19 = (int)(float)((float)((float)((float)v18 * (float)100) / 100.0) + 0.5);
  }
  v25 = 1;
  if ( v19 > 0 )
    v25 = v19;
  v26 = a3 * v17;
  v27 = v55[0];
  v28 = (unsigned __int64)(137438953500LL * (v26 / 1000)) >> 32;
  v29 = ((unsigned int)v28 >> 31) + (v28 >> 5) - v25;
  if ( !v10 )
    goto LABEL_23;
  PropLong = wiasSetValidRangeLong((CWiaItem *)this, 0x1805u, ((unsigned int)v28 >> 31) + (v28 >> 5) - v25, 1);
  if ( PropLong < 0 )
    goto LABEL_37;
  if ( v27 )
  {
LABEL_23:
    v30 = DWORD2(v56);
  }
  else
  {
    if ( v50 )
      v30 = (int)(LODWORD(v55[1]) * v29) / v50;
    else
      v30 = 0;
    PropLong = wiasWritePropLong(this, 0x1805u, v30);
    if ( PropLong < 0 )
    {
      v31 = (char *)WiaTrace_TraceLog("could not write value for WIA_IPS_XPOS");
      WriteDbgTraceErrorWI("CheckXResAndUpdate", v31);
      WiaTrcLib::Free((WiaTrcLib *)v31, v32);
      v14 = (void **)WiaTrace_Trace("could not write value for WIA_IPS_XPOS");
      goto LABEL_36;
    }
  }
  v33 = v53[0];
  v58 = wiasGetChangedValueLong(this, (__int64)v51);
  if ( v58 < 0 )
  {
    CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v57);
    return (unsigned int)v58;
  }
  v59 = DWORD2(v52);
  if ( !v33 && !v27 )
    goto LABEL_45;
  v34 = v25 + v29 - v30;
  v59 = v34;
  PropLong = wiasSetValidRangeLong((CWiaItem *)this, 0x1807u, v34, 1);
  if ( PropLong < 0 )
  {
LABEL_37:
    CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v57);
    return (unsigned int)PropLong;
  }
  if ( !LODWORD(v51[0]) )
  {
    v35 = LODWORD(v51[1]) * v34 / v47;
    if ( v35 <= v34 )
    {
      if ( v35 < v25 )
        v35 = v25;
    }
    else
    {
      v35 = v34;
    }
    PropLong = wiasWritePropLong(this, 0x1807u, v35);
    if ( PropLong < 0 )
    {
      v36 = (char *)WiaTrace_TraceLog("could not write value for WIA_IPS_XEXTENT");
      WriteDbgTraceErrorWI("CheckXResAndUpdate", v36);
      WiaTrcLib::Free((WiaTrcLib *)v36, v37);
      v14 = (void **)WiaTrace_Trace("could not write value for WIA_IPS_XEXTENT");
      goto LABEL_36;
    }
  }
  PropLong = wiasReadPropLong((CWiaItem *)this, 0);
  if ( PropLong )
    goto LABEL_44;
  v38 = v34 - 1;
  PropLong = wiasSetValidRangeLong((CWiaItem *)this, 0x1812u, v38, 1);
  if ( PropLong < 0 )
    goto LABEL_37;
  *(_OWORD *)v51 = 0;
  v39 = wiasGetChangedValueLong(this, (__int64)v51);
  PropLong = v39;
  if ( v39 < 0 )
  {
    if ( v39 != -2147024809 )
      goto LABEL_37;
    goto LABEL_45;
  }
  v47 = 0;
  PropLong = GetMinAndMaxLong((CWiaItem *)this, 0x1812u, 0, &v47);
  if ( PropLong < 0 )
    goto LABEL_37;
  if ( !LODWORD(v51[0]) )
  {
    PropLong = wiasWritePropLong(this, 0x1812u, LODWORD(v51[1]) * v38 / v47);
LABEL_44:
    if ( PropLong < 0 )
      goto LABEL_37;
  }
LABEL_45:
  v40 = wiasReadPropLong((CWiaItem *)this, 1);
  if ( v40 >= 0 )
  {
    v40 = wiasWritePropLong(this, 0x1010u, v59);
    v41 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0, 0, "Set WIA_IPA_PIXELS_PER_LINE to: %u", v59);
    WriteDbgTraceInfoWI("CheckXResAndUpdate", v41);
    WiaTrcLib::Free((WiaTrcLib *)v41, v42);
    v43 = (void **)WiaTrace_TraceWithSubCompTraceLevel(0, 0, "Set WIA_IPA_PIXELS_PER_LINE to: %u", v59);
    WiaTrace_ProcessTrace_Ex(v45, v44, (void *)"CheckXResAndUpdate", 4, v43);
  }
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v57);
  return (unsigned int)v40;
}

```

## disassembly

```asm
0x180057734  mov     [rsp-8+arg_0], rbx
0x180057739  mov     [rsp-8+arg_8], rdx
0x18005773e  push    rbp
0x18005773f  push    rsi
0x180057740  push    rdi
0x180057741  push    r12
0x180057743  push    r13
0x180057745  push    r14
0x180057747  push    r15
0x180057749  lea     rbp, [rsp-10h]
0x18005774e  sub     rsp, 110h
0x180057755  mov     rsi, rcx
0x180057758  mov     r13d, r8d
0x18005775b  lea     rcx, aCheckxresandup; "::CheckXResAndUpdate"
0x180057762  mov     rdi, rdx
0x180057765  call    WiaTrace_Trace
0x18005776a  lea     r14, aCheckxresandup_0; "CheckXResAndUpdate"
0x180057771  mov     [rsp+140h+var_118], rax; struct tagWiaTraceData_Type *
0x180057776  mov     r9, r14; char *
0x180057779  lea     rcx, [rbp+40h+var_80]; this
0x18005777d  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x180057782  xorps   xmm0, xmm0
0x180057785  mov     [rbp+40h+arg_18], 64h ; 'd'
0x18005778c  xor     r15d, r15d
0x18005778f  lea     rax, [rsp+140h+var_D8]
0x180057794  xorps   xmm1, xmm1
0x180057797  mov     [rsp+140h+lpMem], rax; __int64
0x18005779c  mov     r9d, 1803h
0x1800577a2  mov     [rsp+140h+var_108], r15d
0x1800577a7  xor     r8d, r8d
0x1800577aa  mov     [rsp+140h+var_110], r15d
0x1800577af  mov     rdx, rdi
0x1800577b2  mov     [rsp+140h+var_104], r15d
0x1800577b7  mov     rcx, rsi; this
0x1800577ba  mov     [rsp+140h+var_10C], r15d
0x1800577bf  movups  xmmword ptr [rsp+140h+var_D8], xmm0
0x1800577c4  movups  [rsp+140h+var_C8], xmm0
0x1800577c9  movups  xmmword ptr [rbp+40h+var_B0], xmm1
0x1800577cd  movups  [rbp+40h+var_A0], xmm1
0x1800577d1  movups  xmmword ptr [rsp+140h+var_100], xmm0
0x1800577d6  movups  [rsp+140h+var_F0], xmm0
0x1800577db  call    wiasGetChangedValueLong
0x1800577e0  mov     ebx, eax
0x1800577e2  test    eax, eax
0x1800577e4  jns     short loc_1800577F6
0x1800577e6  lea     rcx, [rbp+40h+var_80]; this
0x1800577ea  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x1800577ef  mov     eax, ebx
0x1800577f1  jmp     loc_180057BA0
0x1800577f6  xor     r9d, r9d
0x1800577f9  mov     dword ptr [rsp+140h+lpMem], r15d; int
0x1800577fe  lea     r8, [rbp+40h+arg_18]
0x180057802  mov     edx, 0C25h
0x180057807  mov     rcx, rsi; this
0x18005780a  call    wiasReadPropLong
0x18005780f  mov     r12d, dword ptr [rsp+140h+var_D8]
0x180057814  lea     rax, [rbp+40h+var_B0]
0x180057818  mov     r9d, 1805h
0x18005781e  mov     [rsp+140h+lpMem], rax; __int64
0x180057823  mov     r8d, r12d
0x180057826  mov     rdx, rdi
0x180057829  mov     rcx, rsi; this
0x18005782c  call    wiasGetChangedValueLong
0x180057831  mov     ebx, eax
0x180057833  test    eax, eax
0x180057835  js      short loc_1800577E6
0x180057837  lea     r9, [rsp+140h+var_110]; int *
0x18005783c  mov     edx, 1807h; unsigned int
0x180057841  lea     r8, [rsp+140h+var_108]; int *
0x180057846  mov     rcx, rsi; this
0x180057849  call    ?GetMinAndMaxLong@@YAJPEAEKPEAJ1@Z; GetMinAndMaxLong(uchar *,ulong,long *,long *)
0x18005784e  mov     ebx, eax
0x180057850  test    eax, eax
0x180057852  js      short loc_1800577E6
0x180057854  lea     r9, [rsp+140h+var_104]; int *
0x180057859  xor     r8d, r8d; int *
0x18005785c  mov     edx, 1805h; unsigned int
0x180057861  mov     rcx, rsi; this
0x180057864  call    ?GetMinAndMaxLong@@YAJPEAEKPEAJ1@Z; GetMinAndMaxLong(uchar *,ulong,long *,long *)
0x180057869  mov     ebx, eax
0x18005786b  test    eax, eax
0x18005786d  js      loc_1800577E6
0x180057873  xor     r9d, r9d
0x180057876  mov     dword ptr [rsp+140h+lpMem], r15d; int
0x18005787b  lea     r8, [rsp+140h+var_10C]
0x180057880  mov     edx, 1817h
0x180057885  mov     rcx, rsi; this
0x180057888  call    wiasReadPropLong
0x18005788d  mov     edi, eax
0x18005788f  test    eax, eax
0x180057891  jns     short loc_1800578CC
0x180057893  lea     rcx, aCouldNotReadWi_0; "could not read WIA_IPS_MIN_HORIZONTAL_S"...
0x18005789a  call    WiaTrace_TraceLog
0x18005789f  mov     rdx, rax; char *
0x1800578a2  mov     rcx, r14; char *
0x1800578a5  mov     rbx, rax
0x1800578a8  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800578ad  mov     rcx, rbx; this
0x1800578b0  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800578b5  lea     rcx, aCouldNotReadWi_0; "could not read WIA_IPS_MIN_HORIZONTAL_S"...
0x1800578bc  call    WiaTrace_Trace
0x1800578c1  mov     r9d, 1
0x1800578c7  jmp     loc_180057B84
0x1800578cc  test    edi, edi
0x1800578ce  jnz     short loc_180057930
0x1800578d0  mov     edx, dword ptr [rbp+40h+var_C8+8]
0x1800578d3  lea     r14d, [rdi+1]
0x1800578d7  movd    xmm0, [rsp+140h+var_10C]
0x1800578dd  mov     ecx, r14d
0x1800578e0  cvtdq2ps xmm0, xmm0
0x1800578e3  movd    xmm1, edx
0x1800578e7  cvtdq2ps xmm1, xmm1
0x1800578ea  mulss   xmm1, xmm0
0x1800578ee  movd    xmm0, [rbp+40h+arg_18]
0x1800578f3  cvtdq2ps xmm0, xmm0
0x1800578f6  divss   xmm1, cs:__real@447a0000
0x1800578fe  addss   xmm1, cs:__real@3f000000
0x180057906  cvttss2si eax, xmm1
0x18005790a  test    eax, eax
0x18005790c  cmovg   ecx, eax
0x18005790f  movd    xmm1, ecx
0x180057913  cvtdq2ps xmm1, xmm1
0x180057916  mulss   xmm1, xmm0
0x18005791a  divss   xmm1, cs:__real@42c80000
0x180057922  addss   xmm1, cs:__real@3f000000
0x18005792a  cvttss2si eax, xmm1
0x18005792e  jmp     short loc_1800579AF
0x180057930  lea     r8, aWiaIpsMinHoriz; "WIA_IPS_MIN_HORIZONTAL_SIZE was not pre"...
0x180057937  xor     edx, edx
0x180057939  xor     ecx, ecx
0x18005793b  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180057940  mov     rdx, rax; char *
0x180057943  mov     rcx, r14; char *
0x180057946  mov     rbx, rax
0x180057949  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18005794e  mov     rcx, rbx; this
0x180057951  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180057956  lea     r8, aWiaIpsMinHoriz; "WIA_IPS_MIN_HORIZONTAL_SIZE was not pre"...
0x18005795d  xor     edx, edx
0x18005795f  xor     ecx, ecx
0x180057961  call    WiaTrace_TraceWithSubCompTraceLevel
0x180057966  mov     r9d, 4; int
0x18005796c  mov     [rsp+140h+lpMem], rax; lpMem
0x180057971  mov     r8, r14; int
0x180057974  call    WiaTrace_ProcessTrace_Ex
0x180057979  mov     edx, dword ptr [rbp+40h+var_C8+8]
0x18005797c  mov     r14d, 1
0x180057982  movd    xmm0, [rsp+140h+var_108]
0x180057988  movd    xmm1, dword ptr [rsp+140h+var_D8+8]
0x18005798e  cvtdq2ps xmm0, xmm0
0x180057991  movd    xmm2, edx
0x180057995  cvtdq2ps xmm2, xmm2
0x180057998  cvtdq2ps xmm1, xmm1
0x18005799b  mulss   xmm2, xmm0
0x18005799f  divss   xmm2, xmm1
0x1800579a3  addss   xmm2, cs:__real@3f000000
0x1800579ab  cvttss2si eax, xmm2
0x1800579af  test    eax, eax
0x1800579b1  mov     r15d, r14d
0x1800579b4  cmovg   r15d, eax
0x1800579b8  imul    edx, r13d
0x1800579bc  mov     r13d, dword ptr [rbp+40h+var_B0]
0x1800579c0  mov     eax, 10624DD3h
0x1800579c5  imul    edx
0x1800579c7  sar     edx, 6
0x1800579ca  mov     eax, edx
0x1800579cc  shr     eax, 1Fh
0x1800579cf  add     edx, eax
0x1800579d1  mov     eax, 51EB851Fh
0x1800579d6  imul    edx, [rbp+40h+arg_18]
0x1800579da  imul    edx
0x1800579dc  mov     ebx, edx
0x1800579de  sar     ebx, 5
0x1800579e1  mov     eax, ebx
0x1800579e3  shr     eax, 1Fh
0x1800579e6  add     ebx, eax
0x1800579e8  sub     ebx, r15d
0x1800579eb  test    r12d, r12d
0x1800579ee  jz      loc_180057A80
0x1800579f4  mov     dword ptr [rsp+140h+var_118], r14d; int
0x1800579f9  xor     r9d, r9d
0x1800579fc  xor     r8d, r8d
0x1800579ff  mov     dword ptr [rsp+140h+lpMem], ebx; int
0x180057a03  mov     edx, 1805h; unsigned int
0x180057a08  mov     rcx, rsi; this
0x180057a0b  call    wiasSetValidRangeLong
0x180057a10  mov     edi, eax
0x180057a12  test    eax, eax
0x180057a14  js      loc_180057B95
0x180057a1a  test    r13d, r13d
0x180057a1d  jnz     short loc_180057A80
0x180057a1f  mov     ecx, [rsp+140h+var_104]
0x180057a23  test    ecx, ecx
0x180057a25  jz      short loc_180057A35
0x180057a27  mov     eax, ebx
0x180057a29  imul    eax, dword ptr [rbp+40h+var_B0+8]
0x180057a2d  cdq
0x180057a2e  idiv    ecx
0x180057a30  mov     r12d, eax
0x180057a33  jmp     short loc_180057A38
0x180057a35  xor     r12d, r12d
0x180057a38  mov     r8d, r12d; int
0x180057a3b  mov     edx, 1805h; unsigned int
0x180057a40  mov     rcx, rsi; this
0x180057a43  call    wiasWritePropLong
0x180057a48  mov     edi, eax
0x180057a4a  test    eax, eax
0x180057a4c  jns     short loc_180057A84
0x180057a4e  lea     rcx, aCouldNotWriteV_1; "could not write value for WIA_IPS_XPOS"
0x180057a55  call    WiaTrace_TraceLog
0x180057a5a  mov     rdx, rax; char *
0x180057a5d  lea     rcx, aCheckxresandup_0; "CheckXResAndUpdate"
0x180057a64  mov     rbx, rax
0x180057a67  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180057a6c  mov     rcx, rbx; this
0x180057a6f  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180057a74  lea     rcx, aCouldNotWriteV_1; "could not write value for WIA_IPS_XPOS"
0x180057a7b  jmp     loc_180057B7C
0x180057a80  mov     r12d, dword ptr [rbp+40h+var_A0+8]
0x180057a84  mov     edi, dword ptr [rsp+140h+var_D8]
0x180057a88  test    edi, edi
0x180057a8a  jnz     short loc_180057A96
0x180057a8c  test    r13d, r13d
0x180057a8f  jnz     short loc_180057A96
0x180057a91  xor     r8d, r8d
0x180057a94  jmp     short loc_180057A99
0x180057a96  mov     r8d, r14d
0x180057a99  mov     rdx, [rbp+40h+arg_8]
0x180057a9d  lea     rax, [rsp+140h+var_100]
0x180057aa2  mov     r9d, 1807h
0x180057aa8  mov     [rsp+140h+lpMem], rax; __int64
0x180057aad  mov     rcx, rsi; this
0x180057ab0  call    wiasGetChangedValueLong
0x180057ab5  mov     [rbp+40h+arg_18], eax
0x180057ab8  test    eax, eax
0x180057aba  jns     short loc_180057ACD
0x180057abc  lea     rcx, [rbp+40h+var_80]; this
0x180057ac0  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x180057ac5  mov     eax, [rbp+40h+arg_18]
0x180057ac8  jmp     loc_180057BA0
0x180057acd  mov     eax, dword ptr [rsp+140h+var_F0+8]
0x180057ad1  mov     [rbp+40h+arg_18], eax
0x180057ad4  test    edi, edi
0x180057ad6  jnz     short loc_180057AE1
0x180057ad8  test    r13d, r13d
0x180057adb  jz      loc_180057C8F
0x180057ae1  sub     ebx, r12d
0x180057ae4  mov     dword ptr [rsp+140h+var_118], r14d; int
0x180057ae9  add     ebx, r15d
0x180057aec  mov     r8d, r15d
0x180057aef  mov     r9d, ebx
0x180057af2  mov     [rbp+40h+arg_18], ebx
0x180057af5  mov     edx, 1807h; unsigned int
0x180057afa  mov     dword ptr [rsp+140h+lpMem], ebx; int
0x180057afe  mov     rcx, rsi; this
0x180057b01  call    wiasSetValidRangeLong
0x180057b06  xor     r12d, r12d
0x180057b09  mov     edi, eax
0x180057b0b  test    eax, eax
0x180057b0d  js      loc_180057B95
0x180057b13  cmp     dword ptr [rsp+140h+var_100], r12d
0x180057b18  jnz     loc_180057BBB
0x180057b1e  mov     eax, ebx
0x180057b20  imul    eax, dword ptr [rsp+140h+var_100+8]
0x180057b25  cdq
0x180057b26  idiv    [rsp+140h+var_110]
0x180057b2a  cmp     eax, ebx
0x180057b2c  jle     short loc_180057B32
0x180057b2e  mov     eax, ebx
0x180057b30  jmp     short loc_180057B39
0x180057b32  cmp     eax, r15d
0x180057b35  cmovl   eax, r15d
0x180057b39  mov     r8d, eax; int
0x180057b3c  mov     edx, 1807h; unsigned int
0x180057b41  mov     rcx, rsi; this
0x180057b44  call    wiasWritePropLong
0x180057b49  mov     edi, eax
0x180057b4b  test    eax, eax
0x180057b4d  jns     short loc_180057BBB
0x180057b4f  lea     rcx, aCouldNotWriteV_0; "could not write value for WIA_IPS_XEXTE"...
0x180057b56  call    WiaTrace_TraceLog
0x180057b5b  mov     rdx, rax; char *
0x180057b5e  lea     rcx, aCheckxresandup_0; "CheckXResAndUpdate"
0x180057b65  mov     rbx, rax
0x180057b68  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180057b6d  mov     rcx, rbx; this
0x180057b70  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180057b75  lea     rcx, aCouldNotWriteV_0; "could not write value for WIA_IPS_XEXTE"...
0x180057b7c  call    WiaTrace_Trace
0x180057b81  mov     r9d, r14d; int
0x180057b84  lea     r8, aCheckxresandup_0; "CheckXResAndUpdate"
0x180057b8b  mov     [rsp+140h+lpMem], rax; lpMem
0x180057b90  call    WiaTrace_ProcessTrace_Ex
0x180057b95  lea     rcx, [rbp+40h+var_80]; this
0x180057b99  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x180057b9e  mov     eax, edi
0x180057ba0  mov     rbx, [rsp+140h+arg_0]
0x180057ba8  add     rsp, 110h
0x180057baf  pop     r15
0x180057bb1  pop     r14
  ... truncated ...
```
