# CheckYResAndUpdate(uchar *,_WIA_PROPERTY_CONTEXT *,long)

- ea: `0x180057d44`
- end: `0x18005834d`
- name: `?CheckYResAndUpdate@@YAJPEAEPEAU_WIA_PROPERTY_CONTEXT@@J@Z`
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
- `0x180057d44`
- `0x1800591c0`

## string_xrefs

- `0x180057d6b`: `::CheckYResAndUpdate`
- `0x180057d7a`: `CheckYResAndUpdate`
- `0x18005806d`: `CheckYResAndUpdate`
- `0x18005816e`: `CheckYResAndUpdate`
- `0x180058194`: `CheckYResAndUpdate`
- `0x1800582eb`: `CheckYResAndUpdate`
- `0x180058320`: `CheckYResAndUpdate`
- `0x18005805e`: `could not write value for WIA_IPS_YPOS`
- `0x180058084`: `could not write value for WIA_IPS_YPOS`
- `0x18005815f`: `could not write value for WIA_IPS_YEXTENT`
- `0x180058185`: `could not write value for WIA_IPS_YEXTENT`
- `0x180057ea3`: `could not read WIA_IPS_MIN_VERTICAL`
- `0x180057ec5`: `could not read WIA_IPS_MIN_VERTICAL`

## pseudocode

```c
__int64 __fastcall CheckYResAndUpdate(struct IWiaItem *this, struct _WIA_PROPERTY_CONTEXT *a2, int a3)
{
  char ***v5; // rax
  char *v6; // rdx
  __int64 v7; // r8
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

  v5 = (char ***)WiaTrace_Trace("::CheckYResAndUpdate");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v57, v6, v7, (char **)"CheckYResAndUpdate", lpMem, v5);
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
    || (ChangedValueLong = GetMinAndMaxLong((CWiaItem *)this, 0x1808u, &v49, &v47), ChangedValueLong < 0)
    || (ChangedValueLong = GetMinAndMaxLong((CWiaItem *)this, 0x1806u, 0, &v50), ChangedValueLong < 0) )
  {
    CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v57);
    return (unsigned int)ChangedValueLong;
  }
  PropLong = wiasReadPropLong((CWiaItem *)this, 0);
  if ( PropLong < 0 )
  {
    v12 = (char *)WiaTrace_TraceLog("could not read WIA_IPS_MIN_VERTICAL");
    WriteDbgTraceErrorWI("CheckYResAndUpdate", v12);
    WiaTrcLib::Free((WiaTrcLib *)v12, v13);
    v14 = (void **)WiaTrace_Trace("could not read WIA_IPS_MIN_VERTICAL");
LABEL_36:
    WiaTrace_ProcessTrace_Ex(v16, v15, (void *)"CheckYResAndUpdate", 1, v14);
    goto LABEL_37;
  }
  if ( PropLong )
  {
    v20 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0, 0, "WIA_IPS_MIN_VERTICAL was not present");
    WriteDbgTraceInfoWI("CheckYResAndUpdate", v20);
    WiaTrcLib::Free((WiaTrcLib *)v20, v21);
    v22 = (void **)WiaTrace_TraceWithSubCompTraceLevel(0, 0, "WIA_IPS_MIN_VERTICAL was not present");
    WiaTrace_ProcessTrace_Ex(v24, v23, (void *)"CheckYResAndUpdate", 4, v22);
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
  PropLong = wiasSetValidRangeLong((CWiaItem *)this, 0x1806u, ((unsigned int)v28 >> 31) + (v28 >> 5) - v25, 1);
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
    PropLong = wiasWritePropLong((CWiaItem *)this, 0x1806u, v30);
    if ( PropLong < 0 )
    {
      v31 = (char *)WiaTrace_TraceLog("could not write value for WIA_IPS_YPOS");
      WriteDbgTraceErrorWI("CheckYResAndUpdate", v31);
      WiaTrcLib::Free((WiaTrcLib *)v31, v32);
      v14 = (void **)WiaTrace_Trace("could not write value for WIA_IPS_YPOS");
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
  PropLong = wiasSetValidRangeLong((CWiaItem *)this, 0x1808u, v34, 1);
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
    PropLong = wiasWritePropLong((CWiaItem *)this, 0x1808u, v35);
    if ( PropLong < 0 )
    {
      v36 = (char *)WiaTrace_TraceLog("could not write value for WIA_IPS_YEXTENT");
      WriteDbgTraceErrorWI("CheckYResAndUpdate", v36);
      WiaTrcLib::Free((WiaTrcLib *)v36, v37);
      v14 = (void **)WiaTrace_Trace("could not write value for WIA_IPS_YEXTENT");
      goto LABEL_36;
    }
  }
  PropLong = wiasReadPropLong((CWiaItem *)this, 0);
  if ( PropLong )
    goto LABEL_44;
  v38 = v34 - 1;
  PropLong = wiasSetValidRangeLong((CWiaItem *)this, 0x1813u, v38, 1);
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
  PropLong = GetMinAndMaxLong((CWiaItem *)this, 0x1813u, 0, &v47);
  if ( PropLong < 0 )
    goto LABEL_37;
  if ( !LODWORD(v51[0]) )
  {
    PropLong = wiasWritePropLong((CWiaItem *)this, 0x1813u, LODWORD(v51[1]) * v38 / v47);
LABEL_44:
    if ( PropLong < 0 )
      goto LABEL_37;
  }
LABEL_45:
  v40 = wiasReadPropLong((CWiaItem *)this, 1);
  if ( v40 >= 0 )
  {
    v40 = wiasWritePropLong((CWiaItem *)this, 0x1012u, v59);
    v41 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0, 0, "Set WIA_IPA_NUMBER_OF_LINES to: %u", v59);
    WriteDbgTraceInfoWI("CheckYResAndUpdate", v41);
    WiaTrcLib::Free((WiaTrcLib *)v41, v42);
    v43 = (void **)WiaTrace_TraceWithSubCompTraceLevel(0, 0, "Set WIA_IPA_NUMBER_OF_LINES to: %u", v59);
    WiaTrace_ProcessTrace_Ex(v45, v44, (void *)"CheckYResAndUpdate", 4, v43);
  }
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v57);
  return (unsigned int)v40;
}

```

## disassembly

```asm
0x180057d44  mov     [rsp-8+arg_0], rbx
0x180057d49  mov     [rsp-8+arg_8], rdx
0x180057d4e  push    rbp
0x180057d4f  push    rsi
0x180057d50  push    rdi
0x180057d51  push    r12
0x180057d53  push    r13
0x180057d55  push    r14
0x180057d57  push    r15
0x180057d59  lea     rbp, [rsp-10h]
0x180057d5e  sub     rsp, 110h
0x180057d65  mov     rsi, rcx
0x180057d68  mov     r13d, r8d
0x180057d6b  lea     rcx, aCheckyresandup; "::CheckYResAndUpdate"
0x180057d72  mov     rdi, rdx
0x180057d75  call    WiaTrace_Trace
0x180057d7a  lea     r14, aCheckyresandup_0; "CheckYResAndUpdate"
0x180057d81  mov     [rsp+140h+var_118], rax; struct tagWiaTraceData_Type *
0x180057d86  mov     r9, r14; char *
0x180057d89  lea     rcx, [rbp+40h+var_80]; this
0x180057d8d  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x180057d92  xorps   xmm0, xmm0
0x180057d95  mov     [rbp+40h+arg_18], 64h ; 'd'
0x180057d9c  xor     r15d, r15d
0x180057d9f  lea     rax, [rsp+140h+var_D8]
0x180057da4  xorps   xmm1, xmm1
0x180057da7  mov     [rsp+140h+lpMem], rax; __int64
0x180057dac  mov     r9d, 1804h
0x180057db2  mov     [rsp+140h+var_108], r15d
0x180057db7  xor     r8d, r8d
0x180057dba  mov     [rsp+140h+var_110], r15d
0x180057dbf  mov     rdx, rdi
0x180057dc2  mov     [rsp+140h+var_104], r15d
0x180057dc7  mov     rcx, rsi; this
0x180057dca  mov     [rsp+140h+var_10C], r15d
0x180057dcf  movups  xmmword ptr [rsp+140h+var_D8], xmm0
0x180057dd4  movups  [rsp+140h+var_C8], xmm0
0x180057dd9  movups  xmmword ptr [rbp+40h+var_B0], xmm1
0x180057ddd  movups  [rbp+40h+var_A0], xmm1
0x180057de1  movups  xmmword ptr [rsp+140h+var_100], xmm0
0x180057de6  movups  [rsp+140h+var_F0], xmm0
0x180057deb  call    wiasGetChangedValueLong
0x180057df0  mov     ebx, eax
0x180057df2  test    eax, eax
0x180057df4  jns     short loc_180057E06
0x180057df6  lea     rcx, [rbp+40h+var_80]; this
0x180057dfa  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x180057dff  mov     eax, ebx
0x180057e01  jmp     loc_1800581B0
0x180057e06  xor     r9d, r9d
0x180057e09  mov     dword ptr [rsp+140h+lpMem], r15d; int
0x180057e0e  lea     r8, [rbp+40h+arg_18]
0x180057e12  mov     edx, 0C26h
0x180057e17  mov     rcx, rsi; this
0x180057e1a  call    wiasReadPropLong
0x180057e1f  mov     r12d, dword ptr [rsp+140h+var_D8]
0x180057e24  lea     rax, [rbp+40h+var_B0]
0x180057e28  mov     r9d, 1806h
0x180057e2e  mov     [rsp+140h+lpMem], rax; __int64
0x180057e33  mov     r8d, r12d
0x180057e36  mov     rdx, rdi
0x180057e39  mov     rcx, rsi; this
0x180057e3c  call    wiasGetChangedValueLong
0x180057e41  mov     ebx, eax
0x180057e43  test    eax, eax
0x180057e45  js      short loc_180057DF6
0x180057e47  lea     r9, [rsp+140h+var_110]; int *
0x180057e4c  mov     edx, 1808h; unsigned int
0x180057e51  lea     r8, [rsp+140h+var_108]; int *
0x180057e56  mov     rcx, rsi; this
0x180057e59  call    ?GetMinAndMaxLong@@YAJPEAEKPEAJ1@Z; GetMinAndMaxLong(uchar *,ulong,long *,long *)
0x180057e5e  mov     ebx, eax
0x180057e60  test    eax, eax
0x180057e62  js      short loc_180057DF6
0x180057e64  lea     r9, [rsp+140h+var_104]; int *
0x180057e69  xor     r8d, r8d; int *
0x180057e6c  mov     edx, 1806h; unsigned int
0x180057e71  mov     rcx, rsi; this
0x180057e74  call    ?GetMinAndMaxLong@@YAJPEAEKPEAJ1@Z; GetMinAndMaxLong(uchar *,ulong,long *,long *)
0x180057e79  mov     ebx, eax
0x180057e7b  test    eax, eax
0x180057e7d  js      loc_180057DF6
0x180057e83  xor     r9d, r9d
0x180057e86  mov     dword ptr [rsp+140h+lpMem], r15d; int
0x180057e8b  lea     r8, [rsp+140h+var_10C]
0x180057e90  mov     edx, 1818h
0x180057e95  mov     rcx, rsi; this
0x180057e98  call    wiasReadPropLong
0x180057e9d  mov     edi, eax
0x180057e9f  test    eax, eax
0x180057ea1  jns     short loc_180057EDC
0x180057ea3  lea     rcx, aCouldNotReadWi; "could not read WIA_IPS_MIN_VERTICAL"
0x180057eaa  call    WiaTrace_TraceLog
0x180057eaf  mov     rdx, rax; char *
0x180057eb2  mov     rcx, r14; char *
0x180057eb5  mov     rbx, rax
0x180057eb8  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180057ebd  mov     rcx, rbx; this
0x180057ec0  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180057ec5  lea     rcx, aCouldNotReadWi; "could not read WIA_IPS_MIN_VERTICAL"
0x180057ecc  call    WiaTrace_Trace
0x180057ed1  mov     r9d, 1
0x180057ed7  jmp     loc_180058194
0x180057edc  test    edi, edi
0x180057ede  jnz     short loc_180057F40
0x180057ee0  mov     edx, dword ptr [rbp+40h+var_C8+8]
0x180057ee3  lea     r14d, [rdi+1]
0x180057ee7  movd    xmm0, [rsp+140h+var_10C]
0x180057eed  mov     ecx, r14d
0x180057ef0  cvtdq2ps xmm0, xmm0
0x180057ef3  movd    xmm1, edx
0x180057ef7  cvtdq2ps xmm1, xmm1
0x180057efa  mulss   xmm1, xmm0
0x180057efe  movd    xmm0, [rbp+40h+arg_18]
0x180057f03  cvtdq2ps xmm0, xmm0
0x180057f06  divss   xmm1, cs:__real@447a0000
0x180057f0e  addss   xmm1, cs:__real@3f000000
0x180057f16  cvttss2si eax, xmm1
0x180057f1a  test    eax, eax
0x180057f1c  cmovg   ecx, eax
0x180057f1f  movd    xmm1, ecx
0x180057f23  cvtdq2ps xmm1, xmm1
0x180057f26  mulss   xmm1, xmm0
0x180057f2a  divss   xmm1, cs:__real@42c80000
0x180057f32  addss   xmm1, cs:__real@3f000000
0x180057f3a  cvttss2si eax, xmm1
0x180057f3e  jmp     short loc_180057FBF
0x180057f40  lea     r8, aWiaIpsMinVerti; "WIA_IPS_MIN_VERTICAL was not present"
0x180057f47  xor     edx, edx
0x180057f49  xor     ecx, ecx
0x180057f4b  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180057f50  mov     rdx, rax; char *
0x180057f53  mov     rcx, r14; char *
0x180057f56  mov     rbx, rax
0x180057f59  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180057f5e  mov     rcx, rbx; this
0x180057f61  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180057f66  lea     r8, aWiaIpsMinVerti; "WIA_IPS_MIN_VERTICAL was not present"
0x180057f6d  xor     edx, edx
0x180057f6f  xor     ecx, ecx
0x180057f71  call    WiaTrace_TraceWithSubCompTraceLevel
0x180057f76  mov     r9d, 4; int
0x180057f7c  mov     [rsp+140h+lpMem], rax; lpMem
0x180057f81  mov     r8, r14; int
0x180057f84  call    WiaTrace_ProcessTrace_Ex
0x180057f89  mov     edx, dword ptr [rbp+40h+var_C8+8]
0x180057f8c  mov     r14d, 1
0x180057f92  movd    xmm0, [rsp+140h+var_108]
0x180057f98  movd    xmm1, dword ptr [rsp+140h+var_D8+8]
0x180057f9e  cvtdq2ps xmm0, xmm0
0x180057fa1  movd    xmm2, edx
0x180057fa5  cvtdq2ps xmm2, xmm2
0x180057fa8  cvtdq2ps xmm1, xmm1
0x180057fab  mulss   xmm2, xmm0
0x180057faf  divss   xmm2, xmm1
0x180057fb3  addss   xmm2, cs:__real@3f000000
0x180057fbb  cvttss2si eax, xmm2
0x180057fbf  test    eax, eax
0x180057fc1  mov     r15d, r14d
0x180057fc4  cmovg   r15d, eax
0x180057fc8  imul    edx, r13d
0x180057fcc  mov     r13d, dword ptr [rbp+40h+var_B0]
0x180057fd0  mov     eax, 10624DD3h
0x180057fd5  imul    edx
0x180057fd7  sar     edx, 6
0x180057fda  mov     eax, edx
0x180057fdc  shr     eax, 1Fh
0x180057fdf  add     edx, eax
0x180057fe1  mov     eax, 51EB851Fh
0x180057fe6  imul    edx, [rbp+40h+arg_18]
0x180057fea  imul    edx
0x180057fec  mov     ebx, edx
0x180057fee  sar     ebx, 5
0x180057ff1  mov     eax, ebx
0x180057ff3  shr     eax, 1Fh
0x180057ff6  add     ebx, eax
0x180057ff8  sub     ebx, r15d
0x180057ffb  test    r12d, r12d
0x180057ffe  jz      loc_180058090
0x180058004  mov     dword ptr [rsp+140h+var_118], r14d; int
0x180058009  xor     r9d, r9d
0x18005800c  xor     r8d, r8d
0x18005800f  mov     dword ptr [rsp+140h+lpMem], ebx; int
0x180058013  mov     edx, 1806h; unsigned int
0x180058018  mov     rcx, rsi; this
0x18005801b  call    wiasSetValidRangeLong
0x180058020  mov     edi, eax
0x180058022  test    eax, eax
0x180058024  js      loc_1800581A5
0x18005802a  test    r13d, r13d
0x18005802d  jnz     short loc_180058090
0x18005802f  mov     ecx, [rsp+140h+var_104]
0x180058033  test    ecx, ecx
0x180058035  jz      short loc_180058045
0x180058037  mov     eax, ebx
0x180058039  imul    eax, dword ptr [rbp+40h+var_B0+8]
0x18005803d  cdq
0x18005803e  idiv    ecx
0x180058040  mov     r12d, eax
0x180058043  jmp     short loc_180058048
0x180058045  xor     r12d, r12d
0x180058048  mov     r8d, r12d; int
0x18005804b  mov     edx, 1806h; unsigned int
0x180058050  mov     rcx, rsi; this
0x180058053  call    wiasWritePropLong
0x180058058  mov     edi, eax
0x18005805a  test    eax, eax
0x18005805c  jns     short loc_180058094
0x18005805e  lea     rcx, aCouldNotWriteV_2; "could not write value for WIA_IPS_YPOS"
0x180058065  call    WiaTrace_TraceLog
0x18005806a  mov     rdx, rax; char *
0x18005806d  lea     rcx, aCheckyresandup_0; "CheckYResAndUpdate"
0x180058074  mov     rbx, rax
0x180058077  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005807c  mov     rcx, rbx; this
0x18005807f  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180058084  lea     rcx, aCouldNotWriteV_2; "could not write value for WIA_IPS_YPOS"
0x18005808b  jmp     loc_18005818C
0x180058090  mov     r12d, dword ptr [rbp+40h+var_A0+8]
0x180058094  mov     edi, dword ptr [rsp+140h+var_D8]
0x180058098  test    edi, edi
0x18005809a  jnz     short loc_1800580A6
0x18005809c  test    r13d, r13d
0x18005809f  jnz     short loc_1800580A6
0x1800580a1  xor     r8d, r8d
0x1800580a4  jmp     short loc_1800580A9
0x1800580a6  mov     r8d, r14d
0x1800580a9  mov     rdx, [rbp+40h+arg_8]
0x1800580ad  lea     rax, [rsp+140h+var_100]
0x1800580b2  mov     r9d, 1808h
0x1800580b8  mov     [rsp+140h+lpMem], rax; __int64
0x1800580bd  mov     rcx, rsi; this
0x1800580c0  call    wiasGetChangedValueLong
0x1800580c5  mov     [rbp+40h+arg_18], eax
0x1800580c8  test    eax, eax
0x1800580ca  jns     short loc_1800580DD
0x1800580cc  lea     rcx, [rbp+40h+var_80]; this
0x1800580d0  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x1800580d5  mov     eax, [rbp+40h+arg_18]
0x1800580d8  jmp     loc_1800581B0
0x1800580dd  mov     eax, dword ptr [rsp+140h+var_F0+8]
0x1800580e1  mov     [rbp+40h+arg_18], eax
0x1800580e4  test    edi, edi
0x1800580e6  jnz     short loc_1800580F1
0x1800580e8  test    r13d, r13d
0x1800580eb  jz      loc_18005829F
0x1800580f1  sub     ebx, r12d
0x1800580f4  mov     dword ptr [rsp+140h+var_118], r14d; int
0x1800580f9  add     ebx, r15d
0x1800580fc  mov     r8d, r15d
0x1800580ff  mov     r9d, ebx
0x180058102  mov     [rbp+40h+arg_18], ebx
0x180058105  mov     edx, 1808h; unsigned int
0x18005810a  mov     dword ptr [rsp+140h+lpMem], ebx; int
0x18005810e  mov     rcx, rsi; this
0x180058111  call    wiasSetValidRangeLong
0x180058116  xor     r12d, r12d
0x180058119  mov     edi, eax
0x18005811b  test    eax, eax
0x18005811d  js      loc_1800581A5
0x180058123  cmp     dword ptr [rsp+140h+var_100], r12d
0x180058128  jnz     loc_1800581CB
0x18005812e  mov     eax, ebx
0x180058130  imul    eax, dword ptr [rsp+140h+var_100+8]
0x180058135  cdq
0x180058136  idiv    [rsp+140h+var_110]
0x18005813a  cmp     eax, ebx
0x18005813c  jle     short loc_180058142
0x18005813e  mov     eax, ebx
0x180058140  jmp     short loc_180058149
0x180058142  cmp     eax, r15d
0x180058145  cmovl   eax, r15d
0x180058149  mov     r8d, eax; int
0x18005814c  mov     edx, 1808h; unsigned int
0x180058151  mov     rcx, rsi; this
0x180058154  call    wiasWritePropLong
0x180058159  mov     edi, eax
0x18005815b  test    eax, eax
0x18005815d  jns     short loc_1800581CB
0x18005815f  lea     rcx, aCouldNotWriteV; "could not write value for WIA_IPS_YEXTE"...
0x180058166  call    WiaTrace_TraceLog
0x18005816b  mov     rdx, rax; char *
0x18005816e  lea     rcx, aCheckyresandup_0; "CheckYResAndUpdate"
0x180058175  mov     rbx, rax
0x180058178  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005817d  mov     rcx, rbx; this
0x180058180  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180058185  lea     rcx, aCouldNotWriteV; "could not write value for WIA_IPS_YEXTE"...
0x18005818c  call    WiaTrace_Trace
0x180058191  mov     r9d, r14d; int
0x180058194  lea     r8, aCheckyresandup_0; "CheckYResAndUpdate"
0x18005819b  mov     [rsp+140h+lpMem], rax; lpMem
0x1800581a0  call    WiaTrace_ProcessTrace_Ex
0x1800581a5  lea     rcx, [rbp+40h+var_80]; this
0x1800581a9  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x1800581ae  mov     eax, edi
0x1800581b0  mov     rbx, [rsp+140h+arg_0]
0x1800581b8  add     rsp, 110h
0x1800581bf  pop     r15
0x1800581c1  pop     r14
  ... truncated ...
```
