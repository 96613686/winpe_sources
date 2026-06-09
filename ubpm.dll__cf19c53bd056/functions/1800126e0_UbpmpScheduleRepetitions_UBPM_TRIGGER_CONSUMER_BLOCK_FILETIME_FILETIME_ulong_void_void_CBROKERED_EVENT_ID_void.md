# UbpmpScheduleRepetitions(_UBPM_TRIGGER_CONSUMER_BLOCK *,_FILETIME *,_FILETIME *,ulong,void *,void *,_CBROKERED_EVENT_ID *,void * *,void * *,_CBROKERED_EVENT_ID *,void * *)

- ea: `0x1800126e0`
- end: `0x180012f77`
- name: `?UbpmpScheduleRepetitions@@YAKPEAU_UBPM_TRIGGER_CONSUMER_BLOCK@@PEAU_FILETIME@@1KPEAX2PEAU_CBROKERED_EVENT_ID@@PEAPEAX434@Z`
- size: `2199`
- prototype: `unsigned int(struct _UBPM_TRIGGER_CONSUMER_BLOCK *, struct _FILETIME *, struct _FILETIME *, unsigned int, void *, void *, struct _CBROKERED_EVENT_ID *, void **, void **, struct _CBROKERED_EVENT_ID *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180013244`

## callees

- `0x1800126e0`
- `0x18001e9f4`
- `0x18003d7de`
- `0x18003d810`

## import_xrefs

- `EventAggregation!EaCreateAggregation` at `0x180012adf`
- `EventAggregation!EaCreateAggregation` at `0x180012b28`
- `EventAggregation!EaCreateAggregation` at `0x180012dce`
- `EventAggregation!EaCreateAggregation` at `0x180012e91`
- `EventAggregation!EaCreateAggregation` at `0x180012adf`
- `EventAggregation!EaCreateAggregation` at `0x180012b28`
- `EventAggregation!EaCreateAggregation` at `0x180012dce`
- `EventAggregation!EaCreateAggregation` at `0x180012e91`
- `EventAggregation!EaDeleteAggregation` at `0x180012f36`
- `EventAggregation!EaDeleteAggregation` at `0x180012f41`
- `EventAggregation!EaDeleteAggregation` at `0x180012f57`
- `EventAggregation!EaDeleteAggregation` at `0x180012f36`
- `EventAggregation!EaDeleteAggregation` at `0x180012f41`
- `EventAggregation!EaDeleteAggregation` at `0x180012f57`
- `EventAggregation!EaGetAggregation` at `0x180012a4b`
- `EventAggregation!EaGetAggregation` at `0x180012b9c`
- `EventAggregation!EaGetAggregation` at `0x180012a4b`
- `EventAggregation!EaGetAggregation` at `0x180012b9c`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180012899`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180012c77`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180012899`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180012c77`
- `TimeBrokerClient!TbDeleteCEvent` at `0x180012f4c`
- `TimeBrokerClient!TbDeleteCEvent` at `0x180012f62`
- `TimeBrokerClient!TbDeleteCEvent` at `0x180012f4c`
- `TimeBrokerClient!TbDeleteCEvent` at `0x180012f62`
- `TimeBrokerClient!TbCreateCEvent` at `0x180012969`
- `TimeBrokerClient!TbCreateCEvent` at `0x180012d47`
- `TimeBrokerClient!TbCreateCEvent` at `0x180012969`
- `TimeBrokerClient!TbCreateCEvent` at `0x180012d47`

## pseudocode

```c
__int64 __fastcall UbpmpScheduleRepetitions(
        struct _UBPM_TRIGGER_CONSUMER_BLOCK *a1,
        struct _FILETIME *a2,
        struct _FILETIME *a3,
        unsigned int a4,
        void *a5,
        void *a6,
        struct _CBROKERED_EVENT_ID *a7,
        void **a8,
        void **a9,
        struct _CBROKERED_EVENT_ID *a10,
        void **a11)
{
  __int64 v15; // rdi
  const wchar_t *v16; // rdx
  __int64 v17; // rsi
  _WORD *v18; // r8
  __int64 v19; // rcx
  __int64 v20; // r9
  _WORD *v21; // rcx
  __int64 v22; // rax
  _BYTE *v23; // rax
  unsigned int Aggregation; // ebx
  _QWORD *v25; // rcx
  int v27; // edx
  const wchar_t *v28; // rcx
  _WORD *v29; // rdx
  _WORD *v30; // rcx
  __int64 v31; // rax
  _BYTE *v32; // rax
  __int64 v33; // [rsp+50h] [rbp-B8h] BYREF
  void *v34; // [rsp+58h] [rbp-B0h]
  void *v35; // [rsp+60h] [rbp-A8h]
  __int64 v36; // [rsp+68h] [rbp-A0h] BYREF
  void *v37; // [rsp+70h] [rbp-98h]
  void **v38; // [rsp+78h] [rbp-90h]
  struct _CBROKERED_EVENT_ID *v39; // [rsp+80h] [rbp-88h]
  void **v40; // [rsp+88h] [rbp-80h]
  struct _CBROKERED_EVENT_ID *v41; // [rsp+90h] [rbp-78h]
  void **v42; // [rsp+98h] [rbp-70h]
  _OWORD v43[3]; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v44; // [rsp+D0h] [rbp-38h]
  struct _SYSTEMTIME v45; // [rsp+D8h] [rbp-30h] BYREF
  __int128 v46; // [rsp+E8h] [rbp-20h]
  __int128 v47; // [rsp+F8h] [rbp-10h]
  __int128 v48; // [rsp+108h] [rbp+0h]
  __int128 v49; // [rsp+118h] [rbp+10h]
  __int128 v50; // [rsp+128h] [rbp+20h]
  __int128 v51; // [rsp+138h] [rbp+30h]
  __int128 v52; // [rsp+148h] [rbp+40h]
  __int128 v53; // [rsp+158h] [rbp+50h]
  __int128 v54; // [rsp+168h] [rbp+60h]
  __int128 v55; // [rsp+178h] [rbp+70h]
  __int128 v56; // [rsp+188h] [rbp+80h]
  __int128 v57; // [rsp+198h] [rbp+90h]
  __int128 v58; // [rsp+1A8h] [rbp+A0h]
  __int128 v59; // [rsp+1B8h] [rbp+B0h]
  __int64 v60; // [rsp+1C8h] [rbp+C0h]
  _OWORD v61[3]; // [rsp+1D8h] [rbp+D0h] BYREF
  __int64 v62; // [rsp+208h] [rbp+100h]
  __int64 v63; // [rsp+210h] [rbp+108h] BYREF
  __int64 v64; // [rsp+218h] [rbp+110h] BYREF
  __int128 v65; // [rsp+220h] [rbp+118h] BYREF
  __int128 v66; // [rsp+230h] [rbp+128h]
  __int64 v67; // [rsp+240h] [rbp+138h]
  struct _SYSTEMTIME SystemTime; // [rsp+248h] [rbp+140h] BYREF
  __int128 v69; // [rsp+258h] [rbp+150h]
  __int128 v70; // [rsp+268h] [rbp+160h]
  __int128 v71; // [rsp+278h] [rbp+170h]
  __int128 v72; // [rsp+288h] [rbp+180h]
  __int128 v73; // [rsp+298h] [rbp+190h]
  __int128 v74; // [rsp+2A8h] [rbp+1A0h]
  __int128 v75; // [rsp+2B8h] [rbp+1B0h] BYREF
  __int128 v76; // [rsp+2C8h] [rbp+1C0h]
  __int128 v77; // [rsp+2D8h] [rbp+1D0h]
  __int128 v78; // [rsp+2E8h] [rbp+1E0h]
  __int128 v79; // [rsp+2F8h] [rbp+1F0h]
  __int128 v80; // [rsp+308h] [rbp+200h]
  __int128 v81; // [rsp+318h] [rbp+210h]
  __int128 v82; // [rsp+328h] [rbp+220h]
  __int64 v83; // [rsp+338h] [rbp+230h]

  v37 = a5;
  v39 = a7;
  v38 = a8;
  v42 = a9;
  v41 = a10;
  v40 = a11;
  v44 = 0;
  v33 = 0;
  v63 = 0;
  v35 = 0;
  v36 = 0;
  v62 = 0;
  v34 = 0;
  v64 = 0;
  v67 = 0;
  memset(v43, 0, sizeof(v43));
  memset(v61, 0, sizeof(v61));
  v65 = 0;
  v66 = 0;
  if ( a2 && a3 )
  {
    memset_0(&SystemTime, 0, 0xF8u);
    v15 = 2147483646;
    v16 = L"TsRepetition";
    v17 = 64;
    v18 = (_WORD *)&v75 + 2;
    v19 = 2147483646;
    v20 = 64;
    do
    {
      if ( !v19 )
        break;
      if ( !*v16 )
        break;
      *v18++ = *v16++;
      --v19;
      --v20;
    }
    while ( v20 );
    v21 = v18 - 1;
    if ( v20 )
      v21 = v18;
    *v21 = 0;
    DWORD2(v73) = 0;
    v22 = *((_QWORD *)a1 + 3);
    *(_DWORD *)&SystemTime.wYear = 4;
    *((_QWORD *)&v69 + 1) = a4 | 0x100000000LL;
    v23 = *(_BYTE **)(*(_QWORD *)(v22 + 40) + 32LL);
    BYTE5(v71) = v23 && (*v23 & 0x10) != 0;
    FileTimeToSystemTime(a2, (LPSYSTEMTIME)&SystemTime.wHour);
    v45 = SystemTime;
    v60 = v83;
    v47 = v70;
    v46 = v69;
    v49 = v72;
    v48 = v71;
    v51 = v74;
    v50 = v73;
    v53 = v76;
    v52 = v75;
    v55 = v78;
    v54 = v77;
    v57 = v80;
    v56 = v79;
    v59 = v82;
    v58 = v81;
    Aggregation = TbCreateCEvent(&v45, &v63);
    if ( Aggregation )
    {
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_13;
      v27 = 40;
    }
    else if ( a6 && (Aggregation = EaGetAggregation(a6, &v36)) != 0 )
    {
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_13;
      v27 = 41;
    }
    else
    {
      Aggregation = EaGetAggregation(v37, &v33);
      if ( !Aggregation )
      {
        *((_QWORD *)&v65 + 1) = v63;
        *(_QWORD *)&v43[0] = &v65;
        *(_QWORD *)&v65 = 0;
        v67 = 0;
        v66 = 0;
        *((_QWORD *)&v43[0] + 1) = *(_QWORD *)(v33 + 8);
        if ( a6 )
        {
          Aggregation = EaCreateAggregation(v43, UbpmpRepetitionArrived, 0);
          if ( Aggregation )
          {
            v25 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_13;
            v27 = 43;
            goto LABEL_49;
          }
          *((_QWORD *)&v43[0] + 1) = *(_QWORD *)(v36 + 8);
          Aggregation = EaCreateAggregation(v43, 0, &UbpmpRepetitionsStopped);
          if ( Aggregation )
          {
            v25 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_13;
            v27 = 44;
            goto LABEL_49;
          }
        }
        else
        {
          Aggregation = EaCreateAggregation(v43, UbpmpRepetitionArrived, &UbpmpRepetitionsStopped);
          if ( Aggregation )
          {
            v25 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_13;
            v27 = 45;
            goto LABEL_49;
          }
        }
        if ( a3->dwLowDateTime || a3->dwHighDateTime )
        {
          memset_0(&SystemTime, 0, 0xF8u);
          v28 = L"TsDuration";
          v29 = (_WORD *)&v75 + 2;
          do
          {
            if ( !v15 )
              break;
            if ( !*v28 )
              break;
            *v29++ = *v28++;
            --v15;
            --v17;
          }
          while ( v17 );
          v30 = v29 - 1;
          if ( v17 )
            v30 = v29;
          *v30 = 0;
          DWORD2(v73) = 0;
          *((_QWORD *)&v69 + 1) = 0x100000000LL;
          v31 = *((_QWORD *)a1 + 3);
          *(_DWORD *)&SystemTime.wYear = 4;
          v32 = *(_BYTE **)(*(_QWORD *)(v31 + 40) + 32LL);
          BYTE5(v71) = v32 && (*v32 & 0x10) != 0;
          FileTimeToSystemTime(a3, (LPSYSTEMTIME)&SystemTime.wHour);
          v45 = SystemTime;
          v60 = v83;
          v47 = v70;
          v46 = v69;
          v49 = v72;
          v48 = v71;
          v51 = v74;
          v50 = v73;
          v53 = v76;
          v52 = v75;
          v55 = v78;
          v54 = v77;
          v57 = v80;
          v56 = v79;
          v59 = v82;
          v58 = v81;
          Aggregation = TbCreateCEvent(&v45, &v64);
          if ( Aggregation )
          {
            v25 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_13;
            v27 = 46;
            goto LABEL_49;
          }
          *((_QWORD *)&v65 + 1) = v64;
          *(_QWORD *)&v65 = 0;
          *(_QWORD *)&v61[0] = &v65;
          v67 = 0;
          v66 = 0;
          Aggregation = EaCreateAggregation(v61, UbpmpDurationEndArrived, 0);
          if ( Aggregation )
          {
            v25 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_13;
            v27 = 47;
            goto LABEL_49;
          }
        }
        *v38 = 0;
        *(_QWORD *)v39 = v63;
        *v40 = v34;
        *(_QWORD *)v41 = v64;
        *v42 = v35;
        return Aggregation;
      }
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_13;
      v27 = 42;
    }
LABEL_49:
    WPP_SF_Sd(
      v25[2],
      v27,
      (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
      *(_QWORD *)(*((_QWORD *)a1 + 3) + 8LL),
      Aggregation);
LABEL_13:
    if ( v35 )
      EaDeleteAggregation();
    if ( v63 != __PAIR64__(v63, 0) )
      TbDeleteCEvent();
    if ( v34 )
      EaDeleteAggregation();
    if ( v64 != __PAIR64__(v64, 0) )
      TbDeleteCEvent();
    return Aggregation;
  }
  return 87;
}

```

## disassembly

```asm
0x1800126e0  mov     r11, rsp
0x1800126e3  push    rbp
0x1800126e4  push    rbx
0x1800126e5  push    r12
0x1800126e7  push    r13
0x1800126e9  push    r14
0x1800126eb  push    r15
0x1800126ed  lea     rbp, [r11-298h]
0x1800126f4  sub     rsp, 368h
0x1800126fb  mov     rax, cs:__security_cookie
0x180012702  xor     rax, rsp
0x180012705  mov     [rbp+290h+var_50], rax
0x18001270c  mov     rax, [rbp+290h+arg_20]
0x180012713  xorps   xmm0, xmm0
0x180012716  mov     r12, [rbp+290h+arg_28]
0x18001271d  mov     r13, rcx
0x180012720  xor     ecx, ecx
0x180012722  mov     [rsp+390h+var_328], rax
0x180012727  mov     rax, [rbp+290h+arg_30]
0x18001272e  mov     r15d, r9d
0x180012731  mov     [rsp+390h+var_318], rax
0x180012736  mov     r14, r8
0x180012739  mov     rax, [rbp+290h+arg_38]
0x180012740  mov     rbx, rdx
0x180012743  mov     [rsp+390h+var_320], rax
0x180012748  mov     rax, [rbp+290h+arg_40]
0x18001274f  mov     [rbp+290h+var_300], rax
0x180012753  mov     rax, [rbp+290h+arg_48]
0x18001275a  mov     [rbp+290h+var_308], rax
0x18001275e  mov     rax, [rbp+290h+arg_50]
0x180012765  mov     [rbp+290h+var_310], rax
0x180012769  xor     eax, eax
0x18001276b  mov     [rbp+290h+var_2C8], rax
0x18001276f  mov     [rsp+390h+var_350], rcx
0x180012774  mov     [rsp+390h+var_348], rcx
0x180012779  mov     [rbp+290h+var_188], rcx
0x180012780  mov     [rsp+390h+var_338], rcx
0x180012785  mov     [rsp+390h+var_330], rcx
0x18001278a  mov     [rbp+290h+var_190], rax
0x180012791  mov     [rsp+390h+var_340], rcx
0x180012796  mov     [rbp+290h+var_180], rcx
0x18001279d  mov     [rbp+290h+var_158], rax
0x1800127a4  movups  [rbp+290h+var_2F8], xmm0
0x1800127a8  movups  [rbp+290h+var_2E8], xmm0
0x1800127ac  movups  [rbp+290h+var_2D8], xmm0
0x1800127b0  movups  [rbp+290h+var_1C0], xmm0
0x1800127b7  movups  [rbp+290h+var_1B0], xmm0
0x1800127be  movups  [rbp+290h+var_1A0], xmm0
0x1800127c5  movups  [rbp+290h+var_178], xmm0
0x1800127cc  movups  [rbp+290h+var_168], xmm0
0x1800127d3  test    rdx, rdx
0x1800127d6  jz      loc_180012F6D
0x1800127dc  test    r8, r8
0x1800127df  jz      loc_180012F6D
0x1800127e5  mov     [r11-38h], rsi
0x1800127e9  lea     rcx, [rbp+290h+SystemTime]; void *
0x1800127f0  xor     edx, edx; Val
0x1800127f2  mov     [r11-40h], rdi
0x1800127f6  mov     r8d, 0F8h; Size
0x1800127fc  call    memset_0
0x180012801  mov     edi, 7FFFFFFEh
0x180012806  lea     rdx, aTsrepetition; "TsRepetition"
0x18001280d  mov     esi, 40h ; '@'
0x180012812  lea     r8, [rbp+290h+var_DC]
0x180012819  mov     ecx, edi
0x18001281b  mov     r9d, esi
0x18001281e  xchg    ax, ax
0x180012820  test    rcx, rcx
0x180012823  jz      short loc_180012842
0x180012825  movzx   eax, word ptr [rdx]
0x180012828  test    ax, ax
0x18001282b  jz      short loc_180012842
0x18001282d  mov     [r8], ax
0x180012831  add     rdx, 2
0x180012835  add     r8, 2
0x180012839  dec     rcx
0x18001283c  sub     r9, 1
0x180012840  jnz     short loc_180012820
0x180012842  test    r9, r9
0x180012845  lea     rcx, [r8-2]
0x180012849  cmovnz  rcx, r8
0x18001284d  xor     eax, eax
0x18001284f  mov     [rcx], ax
0x180012852  mov     [rbp+290h+var_F8], eax
0x180012858  mov     rax, [r13+18h]
0x18001285c  mov     dword ptr [rbp+290h+SystemTime.wYear], 4
0x180012866  mov     [rbp+290h+var_138], r15d
0x18001286d  mov     [rbp+290h+var_134], 1
0x180012877  mov     rcx, [rax+28h]
0x18001287b  mov     rax, [rcx+20h]
0x18001287f  test    rax, rax
0x180012882  jnz     loc_180012A23
0x180012888  mov     [rbp+290h+var_11B], 0
0x18001288f  lea     rdx, [rbp+290h+SystemTime.wHour]; lpSystemTime
0x180012896  mov     rcx, rbx; lpFileTime
0x180012899  call    cs:__imp_FileTimeToSystemTime
0x18001289f  movaps  xmm0, xmmword ptr [rbp+290h+SystemTime.wYear]
0x1800128a6  lea     rdx, [rbp+290h+var_188]
0x1800128ad  movaps  xmm1, xmmword ptr [rbp+150h]
0x1800128b4  lea     rcx, [rbp+290h+var_2C0]
0x1800128b8  mov     rax, [rbp+290h+var_60]
0x1800128bf  movups  [rbp+290h+var_2C0], xmm0
0x1800128c3  mov     [rbp+290h+var_1D0], rax
0x1800128ca  movaps  xmm0, [rbp+290h+var_130]
0x1800128d1  movups  [rbp+290h+var_2A0], xmm0
0x1800128d5  movaps  xmm0, [rbp+290h+var_110]
0x1800128dc  movups  [rbp+290h+var_2B0], xmm1
0x1800128e0  movaps  xmm1, xmmword ptr [rbp+170h]
0x1800128e7  movups  [rbp+290h+var_280], xmm0
0x1800128eb  movaps  xmm0, [rbp+290h+var_F0]
0x1800128f2  movups  [rbp+290h+var_290], xmm1
0x1800128f6  movaps  xmm1, xmmword ptr [rbp+190h]
0x1800128fd  movups  [rbp+290h+var_260], xmm0
0x180012901  movaps  xmm0, [rbp+290h+var_D0]
0x180012908  movups  [rbp+290h+var_270], xmm1
0x18001290c  movaps  xmm1, xmmword ptr [rbp+1B0h]
0x180012913  movups  [rbp+290h+var_240], xmm0
0x180012917  movaps  xmm0, [rbp+290h+var_B0]
0x18001291e  movups  [rbp+290h+var_250], xmm1
0x180012922  movaps  xmm1, [rbp+290h+var_C0]
0x180012929  movups  [rbp+290h+var_220], xmm0
0x18001292d  movaps  xmm0, [rbp+290h+var_90]
0x180012934  movups  [rbp+290h+var_230], xmm1
0x180012938  movaps  xmm1, [rbp+290h+var_A0]
0x18001293f  movups  [rbp+290h+var_200], xmm0
0x180012946  movaps  xmm0, [rbp+290h+var_70]
0x18001294d  movups  [rbp+290h+var_210], xmm1
0x180012954  movaps  xmm1, [rbp+290h+var_80]
0x18001295b  movups  [rbp+290h+var_1E0], xmm0
0x180012962  movups  [rbp+290h+var_1F0], xmm1
0x180012969  call    cs:__imp_TbCreateCEvent
0x18001296f  mov     ebx, eax
0x180012971  test    eax, eax
0x180012973  jz      loc_180012A38
0x180012979  mov     rcx, cs:WPP_GLOBAL_Control
0x180012980  lea     rax, WPP_GLOBAL_Control
0x180012987  cmp     rcx, rax
0x18001298a  jnz     loc_180012ECC
0x180012990  mov     rcx, [rsp+390h+var_350]
0x180012995  test    rcx, rcx
0x180012998  jnz     loc_180012F36
0x18001299e  mov     rcx, [rsp+390h+var_338]
0x1800129a3  test    rcx, rcx
0x1800129a6  jnz     loc_180012F41
0x1800129ac  mov     rcx, [rbp+290h+var_188]
0x1800129b3  test    ecx, ecx
0x1800129b5  jnz     loc_180012F4C
0x1800129bb  cmp     dword ptr [rbp+290h+var_188+4], ecx
0x1800129c1  jnz     loc_180012F4C
0x1800129c7  mov     rcx, [rsp+390h+var_340]
0x1800129cc  test    rcx, rcx
0x1800129cf  jnz     loc_180012F57
0x1800129d5  mov     rcx, [rbp+290h+var_180]
0x1800129dc  test    ecx, ecx
0x1800129de  jnz     loc_180012F62
0x1800129e4  cmp     dword ptr [rbp+290h+var_180+4], ecx
0x1800129ea  jnz     loc_180012F62
0x1800129f0  mov     rsi, [rsp+360h]
0x1800129f8  mov     eax, ebx
0x1800129fa  mov     rdi, [rsp+390h+var_38]
0x180012a02  mov     rcx, [rbp+290h+var_50]
0x180012a09  xor     rcx, rsp; StackCookie
0x180012a0c  call    __security_check_cookie
0x180012a11  add     rsp, 368h
0x180012a18  pop     r15
0x180012a1a  pop     r14
0x180012a1c  pop     r13
0x180012a1e  pop     r12
0x180012a20  pop     rbx
0x180012a21  pop     rbp
0x180012a22  retn
0x180012a23  test    byte ptr [rax], 10h
0x180012a26  jz      loc_180012888
0x180012a2c  mov     [rbp+290h+var_11B], 1
0x180012a33  jmp     loc_18001288F
0x180012a38  test    r12, r12
0x180012a3b  jnz     loc_180012B94
0x180012a41  mov     rcx, [rsp+390h+var_328]
0x180012a46  lea     rdx, [rsp+390h+var_348]
0x180012a4b  call    cs:__imp_EaGetAggregation
0x180012a51  mov     ebx, eax
0x180012a53  test    eax, eax
0x180012a55  jnz     loc_180012EE0
0x180012a5b  mov     eax, dword ptr [rbp+290h+var_188]
0x180012a61  lea     rdx, UbpmpRepetitionArrived
0x180012a68  mov     dword ptr [rbp+290h+var_178+8], eax
0x180012a6e  xor     r9d, r9d
0x180012a71  mov     eax, dword ptr [rbp+290h+var_188+4]
0x180012a77  xorps   xmm0, xmm0
0x180012a7a  mov     dword ptr [rbp+290h+var_178+0Ch], eax
0x180012a80  lea     rax, [rbp+290h+var_178]
0x180012a87  mov     qword ptr [rbp+290h+var_2F8], rax
0x180012a8b  mov     rax, [rsp+390h+var_348]
0x180012a90  mov     qword ptr [rbp+290h+var_178], 0
0x180012a9b  mov     [rbp+290h+var_158], 0
0x180012aa6  movdqu  [rbp+290h+var_168], xmm0
0x180012aae  mov     rcx, [rax+8]
0x180012ab2  lea     rax, [rsp+390h+var_350]
0x180012ab7  mov     [rsp+390h+var_358], rax
0x180012abc  mov     dword ptr [rsp+390h+var_360], r9d
0x180012ac1  mov     qword ptr [rsp+390h+var_368], r13
0x180012ac6  mov     qword ptr [rbp+290h+var_2F8+8], rcx
0x180012aca  lea     rcx, [rbp+290h+var_2F8]
0x180012ace  mov     [rsp+390h+var_370], r9
0x180012ad3  test    r12, r12
0x180012ad6  jz      loc_180012E8A
0x180012adc  xor     r8d, r8d
0x180012adf  call    cs:__imp_EaCreateAggregation
0x180012ae5  mov     ebx, eax
0x180012ae7  test    eax, eax
0x180012ae9  jnz     loc_180012E25
0x180012aef  mov     rax, [rsp+390h+var_330]
0x180012af4  lea     r8, UbpmpRepetitionsStopped
0x180012afb  xor     r9d, r9d
0x180012afe  xor     edx, edx
0x180012b00  mov     rcx, [rax+8]
0x180012b04  lea     rax, [rsp+390h+var_338]
0x180012b09  mov     [rsp+390h+var_358], rax
0x180012b0e  mov     dword ptr [rsp+390h+var_360], ebx
0x180012b12  mov     qword ptr [rbp+290h+var_2F8+8], rcx
0x180012b16  lea     rcx, [rbp+290h+var_2F8]
0x180012b1a  mov     qword ptr [rsp+390h+var_368], r13
0x180012b1f  mov     [rsp+390h+var_370], 0
0x180012b28  call    cs:__imp_EaCreateAggregation
0x180012b2e  mov     ebx, eax
0x180012b30  test    eax, eax
0x180012b32  jnz     loc_180012E4D
0x180012b38  cmp     dword ptr [r14], 0
0x180012b3c  jnz     loc_180012BD7
0x180012b42  cmp     dword ptr [r14+4], 0
0x180012b47  jnz     loc_180012BD7
0x180012b4d  mov     rcx, [rsp+390h+var_320]
0x180012b52  mov     rax, [rsp+390h+var_350]
0x180012b57  mov     [rcx], rax
0x180012b5a  mov     rcx, [rsp+390h+var_318]
0x180012b5f  mov     rax, [rbp+290h+var_188]
0x180012b66  mov     [rcx], rax
0x180012b69  mov     rcx, [rbp+290h+var_310]
0x180012b6d  mov     rax, [rsp+390h+var_340]
0x180012b72  mov     [rcx], rax
0x180012b75  mov     rcx, [rbp+290h+var_308]
0x180012b79  mov     rax, [rbp+290h+var_180]
0x180012b80  mov     [rcx], rax
0x180012b83  mov     rcx, [rbp+290h+var_300]
0x180012b87  mov     rax, [rsp+390h+var_338]
0x180012b8c  mov     [rcx], rax
0x180012b8f  jmp     loc_1800129F0
0x180012b94  lea     rdx, [rsp+390h+var_330]
0x180012b99  mov     rcx, r12
0x180012b9c  call    cs:__imp_EaGetAggregation
0x180012ba2  mov     ebx, eax
0x180012ba4  test    eax, eax
0x180012ba6  jz      loc_180012A41
0x180012bac  mov     rcx, cs:WPP_GLOBAL_Control
0x180012bb3  lea     rax, WPP_GLOBAL_Control
0x180012bba  cmp     rcx, rax
0x180012bbd  jz      loc_180012990
0x180012bc3  test    byte ptr [rcx+1Ch], 1
0x180012bc7  jz      loc_180012990
0x180012bcd  mov     edx, 29h ; ')'
0x180012bd2  jmp     loc_180012E04
0x180012bd7  xor     edx, edx; Val
0x180012bd9  lea     rcx, [rbp+290h+SystemTime]; void *
0x180012be0  mov     r8d, 0F8h; Size
0x180012be6  call    memset_0
0x180012beb  lea     rcx, aTsduration; "TsDuration"
0x180012bf2  lea     rdx, [rbp+290h+var_DC]
0x180012bf9  nop     dword ptr [rax+00000000h]
0x180012c00  test    rdi, rdi
0x180012c03  jz      short loc_180012C21
0x180012c05  movzx   eax, word ptr [rcx]
0x180012c08  test    ax, ax
0x180012c0b  jz      short loc_180012C21
0x180012c0d  mov     [rdx], ax
0x180012c10  add     rcx, 2
0x180012c14  add     rdx, 2
0x180012c18  dec     rdi
0x180012c1b  sub     rsi, 1
0x180012c1f  jnz     short loc_180012C00
0x180012c21  test    rsi, rsi
0x180012c24  lea     rcx, [rdx-2]
0x180012c28  cmovnz  rcx, rdx
0x180012c2c  xor     eax, eax
0x180012c2e  mov     [rcx], ax
0x180012c31  mov     [rbp+290h+var_F8], eax
0x180012c37  mov     [rbp+290h+var_138], eax
0x180012c3d  mov     rax, [r13+18h]
0x180012c41  mov     dword ptr [rbp+290h+SystemTime.wYear], 4
0x180012c4b  mov     [rbp+290h+var_134], 1
0x180012c55  mov     rcx, [rax+28h]
0x180012c59  mov     rax, [rcx+20h]
0x180012c5d  test    rax, rax
0x180012c60  jnz     loc_180012E75
0x180012c66  mov     [rbp+290h+var_11B], 0
0x180012c6d  lea     rdx, [rbp+290h+SystemTime.wHour]; lpSystemTime
0x180012c74  mov     rcx, r14; lpFileTime
0x180012c77  call    cs:__imp_FileTimeToSystemTime
0x180012c7d  movaps  xmm0, xmmword ptr [rbp+290h+SystemTime.wYear]
0x180012c84  lea     rdx, [rbp+290h+var_180]
0x180012c8b  movaps  xmm1, xmmword ptr [rbp+150h]
  ... truncated ...
```
