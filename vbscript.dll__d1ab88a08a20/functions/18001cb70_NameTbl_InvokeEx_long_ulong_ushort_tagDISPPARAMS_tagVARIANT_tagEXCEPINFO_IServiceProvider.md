# NameTbl::InvokeEx(long,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,IServiceProvider *)

- ea: `0x18001cb70`
- end: `0x18001e1c1`
- name: `?InvokeEx@NameTbl@@UEAAJJKGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAUIServiceProvider@@@Z`
- size: `5713`
- prototype: `__int64 __fastcall(NameTbl *__hidden this, int, unsigned int, unsigned __int16, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, struct IServiceProvider *)`
- caller_count: `0`
- callee_count: `28`
- tags: `service_task, installer_update`

## callees

- `0x180001970`
- `0x180001c30`
- `0x180002e60`
- `0x180003028`
- `0x1800030e8`
- `0x180003c40`
- `0x1800060c0`
- `0x18001af30`
- `0x18001b5d0`
- `0x18001b9e0`
- `0x18001c8ac`
- `0x18001c9d0`
- `0x18001cb70`
- `0x18001ec7c`
- `0x18001ed10`
- `0x1800310f0`
- `0x180031360`
- `0x180036970`
- `0x180036c18`
- `0x1800376f0`
- `0x18003840c`
- `0x180038644`
- `0x180043ff4`
- `0x18006130c`
- `0x180078100`
- `0x180079436`
- `0x180079490`
- `0x18007a010`

## import_xrefs

- `msvcrt!swprintf_s` at `0x18001ddb8`
- `msvcrt!swprintf_s` at `0x18001e03f`
- `msvcrt!swprintf_s` at `0x18001ddb8`
- `msvcrt!swprintf_s` at `0x18001e03f`
- `msvcrt!_controlfp` at `0x18001d004`
- `msvcrt!_controlfp` at `0x18001d01e`
- `msvcrt!_controlfp` at `0x18001d2a8`
- `msvcrt!_controlfp` at `0x18001d004`
- `msvcrt!_controlfp` at `0x18001d01e`
- `msvcrt!_controlfp` at `0x18001d2a8`
- `msvcrt!malloc` at `0x18001d845`
- `msvcrt!malloc` at `0x18001d845`
- `msvcrt!free` at `0x18001d814`
- `msvcrt!free` at `0x18001d814`
- `OLEAUT32!__imp_VariantCopy` at `0x18001d1bd`
- `OLEAUT32!__imp_VariantCopy` at `0x18001d237`
- `OLEAUT32!__imp_VariantCopy` at `0x18001d1bd`
- `OLEAUT32!__imp_VariantCopy` at `0x18001d237`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18001dcb0`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18001dcb0`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18001dcee`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18001dcee`
- `KERNEL32!QueryPerformanceCounter` at `0x18001ddcd`
- `KERNEL32!QueryPerformanceCounter` at `0x18001e053`
- `KERNEL32!QueryPerformanceCounter` at `0x18001ddcd`
- `KERNEL32!QueryPerformanceCounter` at `0x18001e053`
- `KERNEL32!TlsGetValue` at `0x18001ccab`
- `KERNEL32!TlsGetValue` at `0x18001cf27`
- `KERNEL32!TlsGetValue` at `0x18001d041`
- `KERNEL32!TlsGetValue` at `0x18001d100`
- `KERNEL32!TlsGetValue` at `0x18001d3aa`
- `KERNEL32!TlsGetValue` at `0x18001d3e7`
- `KERNEL32!TlsGetValue` at `0x18001d4c5`
- `KERNEL32!TlsGetValue` at `0x18001ccab`
- `KERNEL32!TlsGetValue` at `0x18001cf27`
- `KERNEL32!TlsGetValue` at `0x18001d041`
- `KERNEL32!TlsGetValue` at `0x18001d100`
- `KERNEL32!TlsGetValue` at `0x18001d3aa`
- `KERNEL32!TlsGetValue` at `0x18001d3e7`
- `KERNEL32!TlsGetValue` at `0x18001d4c5`
- `KERNEL32!GetCurrentThreadId` at `0x18001cc04`
- `KERNEL32!GetCurrentThreadId` at `0x18001cc04`

## pseudocode

```c
__int64 __fastcall NameTbl::InvokeEx(
        NameTbl *this,
        int a2,
        unsigned int a3,
        unsigned __int16 a4,
        struct tagDISPPARAMS *a5,
        struct tagVARIANT *a6,
        struct tagEXCEPINFO *a7,
        struct IServiceProvider *a8)
{
  int v10; // r13d
  bool v11; // zf
  int v12; // ebx
  _QWORD *Value; // rax
  __int64 v14; // r15
  __int64 v15; // rbx
  HRESULT StdVar; // edi
  UINT cNamedArgs; // ecx
  struct tagDISPPARAMS *v18; // rcx
  __int16 v19; // r10
  struct IDispatchEx *v20; // rsi
  int lpVtbl_low; // r8d
  __int16 *v22; // rcx
  __int16 v23; // ax
  struct IEntryPoint *GetTypeInfoCount; // r12
  LARGE_INTEGER *v25; // r13
  NameTbl *v26; // r14
  LARGE_INTEGER v27; // rdi
  DexCaller *v28; // rcx
  __int64 v29; // rax
  __int64 v30; // rcx
  int v31; // edi
  __int64 v32; // rax
  _QWORD *v33; // rax
  AutoCalloutParameterLock *v34; // rsi
  int v35; // eax
  unsigned int v36; // eax
  int LowPart; // r14d
  unsigned int v38; // edi
  void (__fastcall **v39)(struct IEntryPoint *); // rax
  __int64 v40; // rsi
  void (__fastcall *v41)(struct IEntryPoint *); // rax
  int v42; // ecx
  __int64 v43; // rcx
  JAmsi *v44; // rcx
  struct IDispatchEx *v45; // r13
  _QWORD *v46; // rax
  unsigned int v47; // eax
  unsigned int v48; // r14d
  VARIANTARG *v49; // r8
  _OWORD *llVal; // rdx
  LONGLONG v51; // r9
  __int64 v52; // rdi
  _QWORD *v53; // rax
  __int64 v54; // rdx
  signed int v55; // r14d
  __int64 v56; // r8
  const VARIANTARG *v57; // rdx
  VARIANTARG *v58; // r8
  LARGE_INTEGER v59; // rax
  const VARIANTARG *v60; // r14
  struct VAR **v62; // rdx
  __int64 v63; // rcx
  NameTbl *v64; // r12
  __int64 v65; // r14
  __int64 v66; // rsi
  DexCaller *v67; // rcx
  char v68; // r13
  int v69; // r14d
  GcBlockFactory *v70; // rax
  GcBlockFactory *v71; // rcx
  LPVOID v72; // rax
  AutoCalloutParameterLock *v73; // r14
  int v74; // esi
  VARIANTARG *v75; // r8
  _OWORD *v76; // rdx
  LONGLONG v77; // r9
  signed int v78; // r13d
  GcBlockFactory *v79; // rax
  GcBlockFactory *v80; // rcx
  __int64 v81; // rax
  __int64 v82; // r10
  __int64 v83; // r11
  HRESULT v84; // eax
  __int64 v85; // r10
  __int64 v86; // r11
  struct tagVARIANT *v87; // rax
  __int64 v88; // r9
  int v89; // ecx
  struct VAR **v90; // rdx
  _DWORD *v91; // rcx
  __int64 v92; // rdx
  DISPID *rgdispidNamedArgs; // rdx
  struct IDispatchExVtbl *v94; // r12
  __int16 v95; // ax
  int v96; // r14d
  _DWORD *v97; // rax
  struct IDispatchExVtbl *v98; // r12
  __int16 QueryInterface; // ax
  int v100; // eax
  __int64 i; // rsi
  __int128 *v102; // rax
  __int64 v103; // xmm1_8
  __int64 v104; // rdx
  __int64 v105; // rax
  signed int v106; // eax
  __int64 v107; // r14
  wchar_t *v108; // rbx
  __int64 v109; // rax
  __int64 v110; // xmm1_8
  __int64 v111; // rdx
  __int64 v112; // rax
  VARIANTARG *lpVtbl; // r9
  __int64 v114; // rcx
  struct IServiceProvider *QuadPart; // rdi
  struct IDispatchExVtbl *v116; // rax
  VARIANTARG *v117; // rsi
  unsigned int v118; // r14d
  unsigned int v119; // r8d
  struct VAR *v120; // r9
  SAFEARRAY *v121; // rsi
  HRESULT v122; // eax
  int v123; // eax
  __int64 v124; // rdx
  unsigned int v125; // edi
  int v126; // r14d
  int v127; // r8d
  FncInfo *v128; // r9
  __int64 v129; // rax
  int *v130; // r13
  int v131; // edx
  void (__fastcall *v132)(__int64, _QWORD, VARIANTARG **, _QWORD, int, int, _QWORD); // rax
  __int64 v133; // rdx
  unsigned int v134; // r14d
  int v135; // r13d
  int v136; // r8d
  FncInfo *v137; // r9
  __int64 v138; // rax
  VARIANTARG *v139; // rcx
  __int64 v140; // rax
  int v141; // edx
  void (__fastcall *v142)(__int64, __int64, VARIANTARG **, _QWORD, int, int, _QWORD); // rax
  int v143; // eax
  ScriptException *v144; // rbx
  unsigned int v146; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v147; // [rsp+5Ch] [rbp-A4h] BYREF
  struct IDispatchEx *v148; // [rsp+60h] [rbp-A0h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+68h] [rbp-98h] BYREF
  int v150; // [rsp+70h] [rbp-90h] BYREF
  unsigned int NewValue[2]; // [rsp+78h] [rbp-88h]
  struct IEntryPoint *v152; // [rsp+80h] [rbp-80h] BYREF
  __int64 v153; // [rsp+88h] [rbp-78h] BYREF
  struct tagVARIANT *v154; // [rsp+90h] [rbp-70h]
  wchar_t *v155; // [rsp+98h] [rbp-68h] BYREF
  struct tagEXCEPINFO *v156; // [rsp+A0h] [rbp-60h]
  __int128 v157; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v158; // [rsp+B8h] [rbp-48h]
  __int64 v159; // [rsp+C0h] [rbp-40h]
  __int64 v160; // [rsp+C8h] [rbp-38h]
  __int64 v161; // [rsp+D0h] [rbp-30h]
  GUID v162; // [rsp+E0h] [rbp-20h] BYREF
  VARIANTARG *pvargSrc[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v164; // [rsp+100h] [rbp+0h]
  VARIANTARG v165; // [rsp+110h] [rbp+10h] BYREF
  __int128 v166; // [rsp+130h] [rbp+30h] BYREF
  __int64 v167; // [rsp+140h] [rbp+40h]
  __int128 v168; // [rsp+148h] [rbp+48h] BYREF
  __int64 v169; // [rsp+158h] [rbp+58h]
  __int128 v170; // [rsp+160h] [rbp+60h] BYREF
  __int64 v171; // [rsp+170h] [rbp+70h]
  wchar_t Buffer[4]; // [rsp+178h] [rbp+78h] BYREF
  VARIANTARG *pvargDest[2]; // [rsp+180h] [rbp+80h] BYREF
  VARIANTARG *v174; // [rsp+190h] [rbp+90h]

  v10 = a4;
  v11 = *((_QWORD *)this + 3) == 0;
  v146 = a3;
  v154 = a6;
  v156 = a7;
  PerformanceCount.QuadPart = (LONGLONG)a8;
  if ( v11 )
    return 2147942487LL;
  if ( a6 )
    a6->vt = 0;
  if ( a7 )
    memset_0(a7, 0, sizeof(struct tagEXCEPINFO));
  v12 = *((_DWORD *)this + 8);
  if ( GetCurrentThreadId() != v12 )
    return 2147549183LL;
  if ( !a5 )
    return 2147942487LL;
  if ( a5->cArgs < a5->cNamedArgs )
    return 2147942487LL;
  if ( (v10 & 0xFFFFFFF0) != 0 || (v10 & 0xF) == 0 )
    return 2147942487LL;
  LOWORD(v147) = v10 & 3;
  LOWORD(v152) = v147;
  if ( (v10 & 3) != 0 && (v10 & 0xFFFFFFFC) != 0 )
    return 2147942487LL;
  if ( (v10 & 0xC) != 0 && (v10 & 0xFFFFFFF3) != 0 )
    return 2147942487LL;
  v158 = 0;
  v169 = 0;
  v157 = 0;
  v153 = 0;
  v168 = 0;
  Value = TlsGetValue(g_luTls);
  if ( Value )
    v14 = Value[4];
  else
    v14 = 0;
  v15 = *((_QWORD *)this + 3);
  v159 = v15;
  _InterlockedIncrement((volatile signed __int32 *)(v15 + 8));
  if ( a2 < 0 )
  {
    StdVar = -2147352573;
    v64 = this;
    goto LABEL_176;
  }
  StdVar = (*(__int64 (__fastcall **)(NameTbl *, _QWORD, __int64 *))(*(_QWORD *)this + 216LL))(
             this,
             (unsigned int)a2,
             &v153);
  if ( StdVar >= 0 )
  {
    cNamedArgs = a5->cNamedArgs;
    if ( cNamedArgs && (rgdispidNamedArgs = a5->rgdispidNamedArgs, *rgdispidNamedArgs == -613) )
    {
      if ( (v10 & 1) == 0 )
      {
        StdVar = -2147024809;
        goto LABEL_175;
      }
      LODWORD(v158) = a5->cArgs - 1;
      *(_QWORD *)&v157 = a5->rgvarg + 1;
      HIDWORD(v158) = cNamedArgs - 1;
      v18 = (struct tagDISPPARAMS *)&v157;
      *((_QWORD *)&v157 + 1) = rgdispidNamedArgs + 1;
    }
    else
    {
      v18 = a5;
    }
    *(_QWORD *)NewValue = v18;
    if ( (v10 & 0xC) != 0 && (!v18->cNamedArgs || *v18->rgdispidNamedArgs != -3) )
    {
      StdVar = -2147352561;
      goto LABEL_175;
    }
    v150 = 0;
    if ( v14 )
      v150 = *(_DWORD *)(v14 + 24);
    v19 = 16396;
    if ( !(_WORD)v152 && ((v10 & 0xC) == 0 || v18->cArgs == 1 && (*(_BYTE *)(v153 + 24) & 0x20) == 0) )
    {
      v20 = 0;
      v148 = 0;
LABEL_30:
      if ( (v10 & 0xC) == 0 )
        goto LABEL_31;
      v114 = *(_QWORD *)NewValue;
      goto LABEL_237;
    }
    StdVar = (*(__int64 (__fastcall **)(NameTbl *, __int64, __int128 *))(*(_QWORD *)this + 264LL))(this, v153, &v168);
    if ( StdVar < 0 )
    {
      v64 = this;
      goto LABEL_107;
    }
    v19 = 16396;
    if ( (_WORD)v168 == 16396 || (_WORD)v168 == 74 )
      v20 = (struct IDispatchEx *)*((_QWORD *)&v168 + 1);
    else
      v20 = (struct IDispatchEx *)&v168;
    v148 = v20;
    if ( !v20 )
      goto LABEL_30;
    if ( LOWORD(v20->lpVtbl) != 9 )
      goto LABEL_30;
    lpVtbl = (VARIANTARG *)v20[1].lpVtbl;
    pvargSrc[0] = lpVtbl;
    if ( !lpVtbl )
      goto LABEL_30;
    v114 = *(_QWORD *)NewValue;
    if ( ((v10 & 2) == 0 || !*(_DWORD *)(*(_QWORD *)NewValue + 16LL)) && ((v10 & 1) == 0 || (v10 & 2) != 0) )
    {
      if ( (v10 & 0xC) == 0 )
        goto LABEL_31;
      if ( *(_DWORD *)(*(_QWORD *)NewValue + 16LL) == 1 )
      {
LABEL_237:
        if ( (*(_BYTE *)(v153 + 24) & 0x20) == 0 )
        {
          memset(&v165, 0, sizeof(v165));
          _InterlockedIncrement((volatile signed __int32 *)(v15 + 8));
          *(_QWORD *)Buffer = v15;
          v174 = 0;
          *(_OWORD *)pvargDest = 0;
          if ( (v10 & 8) != 0 )
            v118 = ((unsigned __int8)~(_BYTE)v10 >> 1) & 2;
          else
            v118 = 1;
          if ( *(_DWORD *)(v114 + 20) != 1 )
          {
            StdVar = -2147024809;
            VarList::~VarList((VarList *)Buffer);
            goto LABEL_243;
          }
          StdVar = VarList::ImportRgvar((VarList *)Buffer, *(_DWORD *)(v114 + 16), *(struct tagVARIANT **)v114, 0);
          if ( StdVar < 0 )
          {
            VarList::~VarList((VarList *)Buffer);
            v64 = this;
            goto LABEL_107;
          }
          v119 = *(_DWORD *)(*(_QWORD *)NewValue + 16LL);
          v165 = *pvargDest[1];
          if ( v119 <= 1 )
          {
            v64 = this;
            v123 = (*(__int64 (__fastcall **)(NameTbl *, __int64, VARIANTARG *, _QWORD))(*(_QWORD *)this + 272LL))(
                     this,
                     v153,
                     &v165,
                     v118);
          }
          else
          {
            if ( ((__int64)v20->lpVtbl & 0xBFFF) != 0x200C )
            {
              StdVar = -2147352573;
              VarList::~VarList((VarList *)Buffer);
              v64 = this;
              goto LABEL_107;
            }
            v120 = (struct VAR *)(**(_QWORD **)NewValue + 24LL);
            pvargSrc[0] = 0;
            StdVar = AccessArray(
                       (struct VAR **)&v148,
                       (struct VAR *)v20,
                       v119 - 1,
                       v120,
                       (struct tagSAFEARRAY **)pvargSrc);
            if ( StdVar < 0 )
            {
LABEL_250:
              VarList::~VarList((VarList *)Buffer);
              v64 = this;
              goto LABEL_107;
            }
            if ( (v118 & 1) != 0 )
            {
              v121 = (SAFEARRAY *)pvargSrc[0];
              StdVar = SafeArrayLock((SAFEARRAY *)pvargSrc[0]);
              if ( StdVar < 0 )
                goto LABEL_250;
              StdVar = AssignVar((struct CSession *)v15, (struct VAR *)v148, (struct VAR *)&v165, v118);
              v122 = SafeArrayUnlock(v121);
              v64 = this;
              if ( StdVar >= 0 && v122 < 0 )
                StdVar = v122;
LABEL_260:
              VarList::~VarList((VarList *)Buffer);
              goto LABEL_107;
            }
            v123 = AssignVar((struct CSession *)v15, (struct VAR *)v148, (struct VAR *)&v165, v118);
            v64 = this;
          }
          StdVar = v123;
          goto LABEL_260;
        }
LABEL_31:
        if ( *(_DWORD *)(*(_QWORD *)NewValue + 20LL) && (*(_BYTE *)(v153 + 24) & 0x20) == 0 )
        {
          v64 = this;
          StdVar = -2147024809;
          goto LABEL_107;
        }
        lpVtbl_low = LOWORD(v20->lpVtbl);
        if ( (_WORD)lpVtbl_low == 16396 || lpVtbl_low == 74 )
        {
          v22 = (__int16 *)v20[1].lpVtbl;
          v23 = *v22;
        }
        else
        {
          v22 = (__int16 *)v20;
          v23 = (__int16)v20->lpVtbl;
        }
        if ( v23 == 76 )
        {
          GetTypeInfoCount = (struct IEntryPoint *)*((_QWORD *)v22 + 1);
          v152 = GetTypeInfoCount;
LABEL_37:
          v167 = 0;
          v166 = 0;
          if ( (_WORD)lpVtbl_low == v19 || lpVtbl_low == 74 )
            LOWORD(lpVtbl_low) = v20[1].lpVtbl->QueryInterface;
          if ( (_WORD)lpVtbl_low != 80 )
          {
LABEL_40:
            if ( (v10 & 1) == 0 && (*(_BYTE *)(v153 + 24) & 0x20) == 0 )
            {
              v64 = this;
              StdVar = -2147352573;
              goto LABEL_107;
            }
            v25 = *(LARGE_INTEGER **)NewValue;
            if ( a5 == *(struct tagDISPPARAMS **)NewValue )
            {
              v26 = this;
              LOWORD(v166) = 9;
              *((_QWORD *)&v166 + 1) = (*(__int64 (__fastcall **)(NameTbl *))(*(_QWORD *)this + 184LL))(this);
              (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v166 + 1) + 8LL))(*((_QWORD *)&v166 + 1));
              pvargSrc[0] = (VARIANTARG *)&v166;
            }
            else
            {
              pvargSrc[0] = a5->rgvarg;
              if ( (unsigned __int16)(pvargSrc[0]->vt - 73) <= 7u )
              {
                v64 = this;
                StdVar = -2147024809;
                goto LABEL_107;
              }
              v26 = this;
            }
            v27 = PerformanceCount;
            v160 = *(_QWORD *)(v15 + 168);
            *(LARGE_INTEGER *)(v15 + 168) = PerformanceCount;
            if ( v27.QuadPart )
              (*(void (__fastcall **)(LARGE_INTEGER))(*(_QWORD *)v27.QuadPart + 8LL))(v27);
            v28 = *(DexCaller **)(v15 + 160);
            if ( v28 )
            {
              DexCaller::Release(v28);
              *(_QWORD *)(v15 + 160) = 0;
            }
            v29 = *(_QWORD *)(v15 + 192);
            v30 = *(_QWORD *)(v15 + 120);
            *(LARGE_INTEGER *)(v15 + 192) = v27;
            v31 = 0;
            v161 = v29;
            v162 = GUID_ScriptFunctionStart;
            PerformanceCount.QuadPart = 0;
            v147 = 0;
            v146 = 0;
            v148 = 0;
            if ( v30 )
            {
              if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v30 + 40LL))(v30) )
              {
                v147 = 16389;
                v148 = (struct IDispatchEx *)Buffer;
                swprintf_s(Buffer, 0x14u, L"%016I64X", v26);
                v146 = 0;
                QueryPerformanceCounter(&PerformanceCount);
                if ( (*(int (__fastcall **)(_QWORD, GUID *, __int64, unsigned int *, struct IDispatchEx **, unsigned int *, DWORD, LONG, int))(**(_QWORD **)(v15 + 120) + 48LL))(
                       *(_QWORD *)(v15 + 120),
                       &v162,
                       1,
                       &v147,
                       &v148,
                       &v146,
                       PerformanceCount.LowPart,
                       PerformanceCount.HighPart,
                       3) < 0 )
                  CSession::StopDebugEvents((CSession *)v15);
              }
            }
            (**(void (__fastcall ***)(struct IEntryPoint *))GetTypeInfoCount)(GetTypeInfoCount);
            v32 = *(_QWORD *)(v15 + 200);
            if ( !v32 )
            {
              v33 = TlsGetValue(g_luTls);
              if ( v33 )
                v32 = v33[5];
              else
                v32 = 0;
            }
            v34 = *(AutoCalloutParameterLock **)(v32 + 56);
            if ( v34 )
            {
              do
              {
                v35 = AutoCalloutParameterLock::Pin(v34, 1);
                v34 = *(AutoCalloutParameterLock **)v34;
                if ( v35 < 0 )
                  v31 = v35;
              }
              while ( v34 );
              if ( v31 < 0 )
                VBScriptClass_Report_Unexpected_Fatal_Error(v26);
            }
            v36 = (*(__int64 (__fastcall **)(NameTbl *))(*(_QWORD *)v26 + 296LL))(v26);
            LowPart = v25[2].LowPart;
            v38 = v36;
            PerformanceCount = *v25;
            v147 = LowPart;
            _InterlockedIncrement((volatile signed __int32 *)(v15 + 8));
            *(_QWORD *)Buffer = v15;
            v171 = 0;
            v39 = *(void (__fastcall ***)(struct IEntryPoint *))GetTypeInfoCount;
            v40 = 0;
            *(_OWORD *)pvargDest = 0;
            v174 = 0;
            v41 = *v39;
            v170 = 0;
            v41(GetTypeInfoCount);
            v42 = (v38 >> 1) & 2 | 4;
            if ( (v38 & 8) == 0 )
              v42 = (v38 >> 1) & 2;
            LODWORD(v152) = v42;
            v43 = *(_QWORD *)(v15 + 32);
            if ( !v43 )
            {
              (*(void (__fastcall **)(struct IEntryPoint *))(*(_QWORD *)GetTypeInfoCount + 8LL))(GetTypeInfoCount);
              CSession::Release(*(CSession **)Buffer);
              if ( pvargDest[0] )
                VarStack::PopMasterSp((VarStack *)pvargDest[0], v90);
              StdVar = -2147467259;
              goto LABEL_97;
            }
            if ( *(_QWORD *)(v43 + 928) )
            {
              v44 = (JAmsi *)(v43 + 200);
              if ( v44 )
                JAmsi::JAmsiInitialize(v44);
            }
            NewValue[0] = _controlfp(0, 0);
            _controlfp(0x1Fu, 0x30F031Fu);
            v45 = (struct IDispatchEx *)&v170;
            if ( !v154 )
              v45 = 0;
            v148 = v45;
            v46 = TlsGetValue(g_luTls);
            if ( v46 )
            {
              v40 = v46[4];
              v155 = (wchar_t *)v40;
              if ( v40 )
              {
                v47 = *(_DWORD *)(v40 + 24);
                goto LABEL_69;
              }
            }
            else
            {
              v155 = 0;
            }
            v47 = 0;
LABEL_69:
            v146 = v47;
            if ( LowPart < 0 )
            {
              StdVar = -2147024809;
              goto LABEL_125;
            }
            v48 = (pvargSrc[0] != 0) + LowPart;
            if ( v48 < v147 )
            {
              StdVar = -2147467259;
              goto LABEL_125;
            }
            v49 = pvargDest[0];
            if ( pvargDest[0] )
            {
              llVal = (_OWORD *)pvargDest[0][1].llVal;
              v51 = pvargDest[0]->llVal;
              *(_OWORD *)&pvargDest[0][1].vt = *llVal;
              if ( llVal == (_OWORD *)(v51 + 8 * (3LL * *(int *)(v51 + 8) - 1)) )
              {
                v49->llVal = *(_QWORD *)v51;
                *(_QWORD *)v51 = v49->pRecInfo;
                v49->pRecInfo = (IRecordInfo *)v51;
              }
              v174 = 0;
              *(_OWORD *)pvargDest = 0;
            }
            if ( v48 )
            {
              v52 = *(_QWORD *)(*(_QWORD *)Buffer + 200LL);
              if ( v52 || ((v53 = TlsGetValue(g_luTls)) == 0 ? (v52 = 0) : (v52 = v53[5]), v52) )
              {
                v54 = *(_QWORD *)(v52 + 8);
                v55 = v48 + 1;
                if ( v54 )
                {
                  v56 = **(_QWORD **)(v52 + 24);
                  if ( (v56 - v54 - 16) / 24 >= v55 )
                  {
LABEL_82:
                    v57 = pvargSrc[0];
                    v58 = (VARIANTARG *)(v56 - 24);
                    pvargDest[1] = v58;
                    *(_OWORD *)&v58->vt = *(_OWORD *)(v52 + 24);
                    *(_QWORD *)(v52 + 24) = &pvargDest[1];
                    *(_QWORD *)(v52 + 32) = v58;
                    pvargDest[0] = (VARIANTARG *)v52;
                    if ( !v57 )
                      goto LABEL_86;
                    --pvargDest[1];
                    pvargDest[1]->vt = 0;
                    StdVar = VariantCopy(pvargDest[1], v57);
                    if ( StdVar >= 0 )
                    {
                      StdVar = VAR::Import((VAR *)pvargDest[1]);
                      if ( StdVar >= 0 )
                      {
                        v174 = pvargDest[1];
LABEL_86:
                        v59 = PerformanceCount;
                        v60 = (const VARIANTARG *)(PerformanceCount.QuadPart + 24LL * (int)v147);
                        while ( (unsigned __int64)v60 > v59.QuadPart )
                        {
                          --v60;
                          --pvargDest[1];
                          pvargDest[1]->vt = 0;
                          StdVar = VariantCopy(pvargDest[1], v60);
                          if ( StdVar < 0 )
                            goto LABEL_125;
                          StdVar = VAR::Import((VAR *)pvargDest[1]);
                          if ( StdVar < 0 )
                            goto LABEL_125;
                          v59 = PerformanceCount;
                        }
                        v45 = v148;
                        goto LABEL_137;
                      }
                    }
LABEL_125:
                    v75 = pvargDest[0];
                    if ( pvargDest[0] )
                    {
                      v76 = (_OWORD *)pvargDest[0][1].llVal;
                      v77 = pvargDest[0]->llVal;
                      *(_OWORD *)&pvargDest[0][1].vt = *v76;
                      if ( v76 == (_OWORD *)(v77 + 8 * (3LL * *(int *)(v77 + 8) - 1)) )
                      {
                        v75->llVal = *(_QWORD *)v77;
                        *(_QWORD *)v77 = v75->pRecInfo;
                        v75->pRecInfo = (IRecordInfo *)v77;
                      }
                      v174 = 0;
                      *(_OWORD *)pvargDest = 0;
                    }
                    if ( v40 )
                    {
                      v78 = v146;
                      if ( (signed int)v146 < *(_DWORD *)(v40 + 24) )
                      {
                        v79 = (GcBlockFactory *)TlsGetValue(g_luTls);
                        v80 = *(GcBlockFactory **)(v40 + 32);
                        if ( v79 == v80 )
                        {
                          if ( v80 )
                          {
                            v106 = *(_DWORD *)(v40 + 24);
                            v107 = *(_QWORD *)(v40 + 8) + 1200LL;
                            if ( v78 < v106 )
                            {
                              v108 = v155;
                              do
                              {
                                if ( *((_QWORD *)v108 + 2) == v107 )
                                {
                                  v11 = *(_QWORD *)v40 == 0;
                                  v111 = *(_QWORD *)(v40 + 8);
                                  v112 = *(_QWORD *)(v111 + 1200);
                                  *(_QWORD *)(v40 + 8) = v112;
                                  *(_QWORD *)(v40 + 16) = v112;
                                  v107 = v112 + 1200;
                                  if ( v11 )
                                  {
                                    *(_QWORD *)(v111 + 1200) = 0;
                                    *(_QWORD *)v40 = v111;
                                  }
                                  else
                                  {
                                    GcBlockFactory::FreeBlk(v80, (struct GcBlock *)v111);
                                  }
                                }
                                v109 = *((_QWORD *)v108 + 2);
                                *(_OWORD *)pvargSrc = *(_OWORD *)v109;
                                v110 = *(_QWORD *)(v109 + 16);
                                --*(_DWORD *)(v40 + 24);
                                *((_QWORD *)v108 + 2) = v109 + 24;
                                v164 = v110;
                                VAR::Clear((VAR *)pvargSrc);
                                v106 = *(_DWORD *)(v40 + 24);
                              }
                              while ( v78 < v106 );
                              v15 = v159;
                            }
                            if ( !v106 )
                              _InterlockedDecrement(&g_cLibRef);
                          }
                        }
                      }
                    }
                    v81 = *(_QWORD *)(v15 + 32);
                    if ( v81 && *(_QWORD *)(v81 + 928) && v81 != -200 )
                      JAmsi::JAmsiUninitialize((JAmsi *)(v81 + 200));
                    (*(void (__fastcall **)(struct IEntryPoint *))(*(_QWORD *)GetTypeInfoCount + 8LL))(GetTypeInfoCount);
                    if ( StdVar < 0 && v154 )
                      v154->vt = 0;
                    _controlfp(NewValue[0], 0xFFFFFFFF);
                    CSession::Release(*(CSession **)Buffer);
                    if ( pvargDest[0] )
                      VarStack::PopMasterSp((VarStack *)pvargDest[0], v62);
LABEL_97:
                    (*(void (__fastcall **)(struct IEntryPoint *))(*(_QWORD *)GetTypeInfoCount + 8LL))(GetTypeInfoCount);
                    v63 = *(_QWORD *)(v15 + 120);
                    pvargSrc[0] = 0;
                    *(GUID *)&v165.vt = GUID_ScriptFunctionStop;
                    v147 = 0;
                    v146 = 0;
                    v155 = 0;
                    if ( v63 )
                    {
                      v64 = this;
                      if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v63 + 40LL))(v63) )
                      {
                        v147 = 16389;
                        v155 = Buffer;
                        swprintf_s(Buffer, 0x14u, L"%016I64X", this);
                        v146 = 0;
                        QueryPerformanceCounter((LARGE_INTEGER *)pvargSrc);
                        if ( (*(int (__fastcall **)(_QWORD, VARIANTARG *, __int64, unsigned int *, wchar_t **, unsigned int *, _DWORD, _DWORD, int))(**(_QWORD **)(v15 + 120) + 48LL))(
                               *(_QWORD *)(v15 + 120),
                               &v165,
                               1,
                               &v147,
                               &v155,
                               &v146,
                               pvargSrc[0],
                               HIDWORD(pvargSrc[0]),
                               3) < 0 )
                          CSession::StopDebugEvents((CSession *)v15);
                      }
                    }
                    else
                    {
                      v64 = this;
                    }
                    VAR::Clear((VAR *)&v166);
                    v65 = v160;
                    v66 = *(_QWORD *)(v15 + 168);
                    *(_QWORD *)(v15 + 168) = v160;
                    if ( v65 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 8LL))(v65);
                    v67 = *(DexCaller **)(v15 + 160);
                    if ( v67 )
                    {
                      DexCaller::Release(v67);
                      *(_QWORD *)(v15 + 160) = 0;
                    }
                    *(_QWORD *)(v15 + 192) = v161;
                    if ( v65 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
                    if ( v66 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
                    goto LABEL_107;
                  }
                }
                while ( 1 )
                {
                  v91 = *(_DWORD **)(v52 + 16);
                  if ( !v91 )
                    break;
                  if ( v91[2] >= v55 )
                    goto LABEL_164;
                  *(_QWORD *)(v52 + 16) = *(_QWORD *)v91;
                  free(v91);
                }
                v96 = 2 * v55;
                if ( *(_DWORD *)v52 < v96 )
                  *(_DWORD *)v52 = v96;
                else
                  v96 = *(_DWORD *)v52;
                v97 = malloc(24LL * v96 + 40);
                *(_QWORD *)(v52 + 16) = v97;
                if ( v97 )
                {
                  v97[2] = v96;
                  **(_QWORD **)(v52 + 16) = 0;
                  *(_DWORD *)v52 *= 2;
LABEL_164:
                  v92 = *(_QWORD *)(v52 + 16);
                  *(_QWORD *)(v52 + 16) = *(_QWORD *)v92;
                  *(_QWORD *)v92 = *(_QWORD *)(v52 + 8);
                  *(_QWORD *)(v52 + 8) = v92;
                  v56 = v92 + 8 * (*(int *)(v92 + 8) + 2 * (*(int *)(v92 + 8) + 1LL));
                  goto LABEL_82;
                }
                v45 = v148;
                StdVar = -2147024882;
                pvargDest[1] = 0;
              }
              else
              {
                StdVar = -2147467259;
              }
            }
            else
            {
              StdVar = 0;
            }
            if ( StdVar >= 0 )
            {
LABEL_137:
              v82 = *(_QWORD *)(v15 + 32);
              if ( v82 )
              {
                v83 = *(_QWORD *)(v82 + 904);
                if ( v83 )
                {
                  v124 = *(_QWORD *)(v15 + 72);
                  v125 = 0;
                  v126 = 0;
                  v127 = 0;
                  if ( v124 )
                  {
                    if ( *(_QWORD *)(v124 + 464) )
                    {
                      v128 = *(FncInfo **)(v124 + 40);
                      if ( v128 )
                      {
                        v129 = *(_QWORD *)v128;
                        if ( *(_QWORD *)v128 )
                        {
                          v130 = *(int **)(v129 + 64);
                          PerformanceCount.QuadPart = *v130 + *(_QWORD *)(v129 + 72);
                          if ( PerformanceCount.QuadPart && v130[1] == 32 )
                          {
                            v131 = *(_DWORD *)(v124 + 488);
                            pvargSrc[0] = 0;
                            FncInfo::GetBos(v128, v131, (struct BOS *)pvargSrc);
                            v127 = (int)pvargSrc[0];
                            v126 = LODWORD(pvargSrc[0]) + HIDWORD(pvargSrc[0]);
                            v125 = *(_DWORD *)PerformanceCount.QuadPart;
                          }
                          v45 = v148;
                        }
                      }
                    }
                  }
                  v132 = *(void (__fastcall **)(__int64, _QWORD, VARIANTARG **, _QWORD, int, int, _QWORD))(*(_QWORD *)v83 + 24LL);
                  *(_OWORD *)pvargSrc = *(_OWORD *)(v82 + 912);
                  v132(v83, 0, pvargSrc, v125, v127, v126, 0);
                }
              }
              v84 = (*(__int64 (__fastcall **)(struct IEntryPoint *, struct IDispatchEx *, _QWORD, VARIANTARG *, VARIANTARG *, _DWORD))(*(_QWORD *)GetTypeInfoCount + 32LL))(
                      GetTypeInfoCount,
                      v45,
                      v147,
                      pvargDest[1],
                      v174,
                      (_DWORD)v152);
              v85 = *(_QWORD *)(v15 + 32);
              StdVar = v84;
              if ( v85 )
              {
                v86 = *(_QWORD *)(v85 + 904);
                if ( v86 )
                {
                  v133 = *(_QWORD *)(v15 + 72);
                  v134 = 0;
                  v135 = 0;
                  v136 = 0;
                  if ( v133 )
                  {
                    if ( *(_QWORD *)(v133 + 464) )
                    {
                      v137 = *(FncInfo **)(v133 + 40);
                      if ( v137 )
                      {
                        v138 = *(_QWORD *)v137;
                        if ( *(_QWORD *)v137 )
                        {
                          v139 = *(VARIANTARG **)(v138 + 64);
                          v140 = *(_QWORD *)(v138 + 72);
                          pvargSrc[0] = v139;
                          PerformanceCount.QuadPart = *(int *)&v139->vt + v140;
                          if ( PerformanceCount.QuadPart )
                          {
                            if ( pvargSrc[0]->decVal.Hi32 == 32 )
                            {
                              v141 = *(_DWORD *)(v133 + 488);
                              pvargSrc[0] = 0;
                              FncInfo::GetBos(v137, v141, (struct BOS *)pvargSrc);
                              v136 = (int)pvargSrc[0];
                              v135 = LODWORD(pvargSrc[0]) + HIDWORD(pvargSrc[0]);
                              v134 = *(_DWORD *)PerformanceCount.QuadPart;
                            }
                          }
                        }
                      }
                    }
                  }
                  v142 = *(void (__fastcall **)(__int64, __int64, VARIANTARG **, _QWORD, int, int, _QWORD))(*(_QWORD *)v86 + 24LL);
                  *(_OWORD *)pvargSrc = *(_OWORD *)(v85 + 912);
                  v142(v86, 1, pvargSrc, v134, v136, v135, 0);
                  v45 = v148;
                }
              }
              if ( StdVar >= 0 )
              {
                v87 = v154;
                if ( v154 )
                {
                  if ( LOWORD(v45->lpVtbl) == 74 )
                    v45 = (struct IDispatchEx *)v45[1].lpVtbl;
                  *(_OWORD *)&v154->vt = *(_OWORD *)&v45->lpVtbl;
                  *((struct IDispatchEx *)&v87->decVal + 2) = v45[2];
                  LOWORD(v45->lpVtbl) = 0;
                }
              }
              goto LABEL_125;
            }
            goto LABEL_125;
          }
          if ( (v10 & 4) == 0
            || *(_WORD *)VAR::PvarCutAll((VAR *)v20) == 80
            && (v94 = v20[1].lpVtbl, v95 = (__int16)v94->QueryInterface, ((__int64)v94->QueryInterface & 2) != 0)
            && (GetTypeInfoCount = (struct IEntryPoint *)v94->Release, v152 = GetTypeInfoCount, (v95 & 0x20) == 0) )
          {
            if ( (v10 & 8) != 0 )
            {
              if ( !(unsigned int)VAR::IsProperty((VAR *)v20, &v152, 1u)
                || ((__int64)v20[1].lpVtbl->QueryInterface & 0x10) != 0 )
              {
                goto LABEL_169;
              }
              GetTypeInfoCount = v152;
            }
            if ( !(_WORD)v147 )
              goto LABEL_40;
            if ( *(_WORD *)VAR::PvarCutAll((VAR *)v20) == 80 )
            {
              v98 = v20[1].lpVtbl;
              QueryInterface = (__int16)v98->QueryInterface;
              if ( ((__int64)v98->QueryInterface & 4) != 0 )
              {
                GetTypeInfoCount = (struct IEntryPoint *)v98->GetTypeInfoCount;
                if ( (QueryInterface & 0x40) == 0 )
                  goto LABEL_40;
              }
            }
          }
LABEL_169:
          v64 = this;
          StdVar = -2147352573;
          goto LABEL_107;
        }
        GetTypeInfoCount = 0;
        v152 = 0;
        if ( *(_WORD *)VAR::PvarCutAll((VAR *)v20) == 80 )
          goto LABEL_37;
        v89 = *(_DWORD *)(v88 + 16);
        if ( !v89 )
        {
          if ( (v10 & 2) != 0 )
          {
            v64 = this;
            if ( v154 )
              StdVar = VAR::GetStdVar((VAR *)v20, v154);
            else
              StdVar = 0;
          }
          else
          {
            v64 = this;
            StdVar = -2147024809;
          }
          goto LABEL_107;
        }
        if ( (lpVtbl_low & 0xFFFFBFFF) != 0x200C )
        {
          v64 = this;
          StdVar = -2147352573;
LABEL_107:
          v68 = 1;
LABEL_108:
          if ( v14 )
          {
            v69 = v150;
            if ( v150 < *(_DWORD *)(v14 + 24) )
            {
              v70 = (GcBlockFactory *)TlsGetValue(g_luTls);
              v71 = *(GcBlockFactory **)(v14 + 32);
              if ( v70 == v71 )
              {
                if ( v71 )
                {
                  v100 = *(_DWORD *)(v14 + 24);
                  for ( i = *(_QWORD *)(v14 + 8) + 1200LL; v69 < v100; v100 = *(_DWORD *)(v14 + 24) )
                  {
                    if ( *(_QWORD *)(v14 + 16) == i )
                    {
                      v11 = *(_QWORD *)v14 == 0;
                      v104 = *(_QWORD *)(v14 + 8);
                      v105 = *(_QWORD *)(v104 + 1200);
                      *(_QWORD *)(v14 + 8) = v105;
                      *(_QWORD *)(v14 + 16) = v105;
                      i = v105 + 1200;
                      if ( v11 )
                      {
                        *(_QWORD *)(v104 + 1200) = 0;
                        *(_QWORD *)v14 = v104;
                      }
                      else
                      {
                        GcBlockFactory::FreeBlk(v71, (struct GcBlock *)v104);
                      }
                    }
                    v102 = *(__int128 **)(v14 + 16);
                    v166 = *v102;
                    v103 = *((_QWORD *)v102 + 2);
                    --*(_DWORD *)(v14 + 24);
                    *(_QWORD *)(v14 + 16) = (char *)v102 + 24;
                    v167 = v103;
                    VAR::Clear((VAR *)&v166);
                  }
                  if ( !v100 )
                    _InterlockedDecrement(&g_cLibRef);
                }
              }
            }
          }
          goto LABEL_112;
        }
        StdVar = AccessArray((struct VAR **)&v148, (struct VAR *)v20, v89, *(struct VAR **)v88, 0);
        if ( StdVar >= 0 )
        {
          v64 = this;
          if ( v154 )
            StdVar = VAR::GetStdVar((VAR *)v148, v154);
          else
            StdVar = 0;
          goto LABEL_107;
        }
LABEL_243:
        v64 = this;
        goto LABEL_107;
      }
    }
    QuadPart = (struct IServiceProvider *)PerformanceCount.QuadPart;
    v148 = 0;
    if ( a5 != *(struct tagDISPPARAMS **)NewValue || PerformanceCount.QuadPart )
    {
      if ( (**(int (__fastcall ***)(VARIANTARG *, GUID *, struct IDispatchEx **))&lpVtbl->vt)(
             lpVtbl,
             &IID_IDispatchEx,
             &v148) >= 0 )
      {
        StdVar = IDispatchExInvokeEx((struct CSession *)v15, v148, 0, v146, v10, a5, v154, v156, QuadPart);
        v116 = v148->lpVtbl;
LABEL_235:
        ((void (*)(void))v116->Release)();
        v64 = this;
        v68 = 0;
        goto LABEL_108;
      }
      lpVtbl = pvargSrc[0];
    }
    (*(void (__fastcall **)(VARIANTARG *))(*(_QWORD *)&lpVtbl->vt + 8LL))(lpVtbl);
    v117 = pvargSrc[0];
    StdVar = IDispatchInvoke(
               (struct CSession *)v15,
               (struct IDispatch *)pvargSrc[0],
               0,
               *(const struct _GUID **)NewValue,
               v146,
               v10,
               *(struct tagDISPPARAMS **)NewValue,
               v154,
               v156,
               0);
    v116 = *(struct IDispatchExVtbl **)&v117->vt;
    goto LABEL_235;
  }
LABEL_175:
  v64 = this;
LABEL_176:
  v68 = 1;
LABEL_112:
  if ( v15 )
  {
    v72 = *(LPVOID *)(v15 + 200);
    if ( !v72 )
    {
      v72 = TlsGetValue(g_luTls);
      if ( v72 )
        v72 = (LPVOID)*((_QWORD *)v72 + 5);
    }
    v73 = (AutoCalloutParameterLock *)*((_QWORD *)v72 + 7);
    v74 = 0;
    while ( v73 )
    {
      v143 = AutoCalloutParameterLock::Pin(v73, 1);
      v73 = *(AutoCalloutParameterLock **)v73;
      if ( v143 < 0 )
        v74 = v143;
    }
    CSession::Release((CSession *)v15);
    if ( v74 < 0 )
      return (unsigned int)v74;
  }
  else
  {
    CSession::Release(0);
  }
  if ( v68 )
  {
    v150 = StdVar;
    if ( StdVar == -2040119292 )
    {
      v144 = CSession::PseGet(*((CSession **)v64 + 3));
      ScriptException::GetError(v144, &v150, v156);
      RuntimeScriptException::Free(v144);
      return (unsigned int)v150;
    }
  }
  return (unsigned int)StdVar;
}

```

## disassembly

```asm
0x18001cb70  push    rbp
0x18001cb72  push    rbx
0x18001cb73  push    rsi
0x18001cb74  push    rdi
0x18001cb75  push    r12
0x18001cb77  push    r13
0x18001cb79  push    r14
0x18001cb7b  lea     rbp, [rsp-0C0h]
0x18001cb83  sub     rsp, 1C0h
0x18001cb8a  mov     rax, cs:__security_cookie
0x18001cb91  xor     rax, rsp
0x18001cb94  mov     [rbp+0F0h+var_50], rax
0x18001cb9b  mov     rax, [rbp+0F0h+arg_38]
0x18001cba2  mov     rbx, rcx
0x18001cba5  mov     r14, [rbp+0F0h+arg_20]
0x18001cbac  mov     edi, edx
0x18001cbae  movzx   r13d, r9w
0x18001cbb2  mov     r9, [rbp+0F0h+arg_30]
0x18001cbb9  cmp     qword ptr [rbx+18h], 0
0x18001cbbe  mov     [rsp+1F0h+var_1A0], rcx
0x18001cbc3  mov     rcx, [rbp+0F0h+arg_28]
0x18001cbca  mov     [rsp+1F0h+var_198], r8d
0x18001cbcf  mov     [rbp+0F0h+var_160], rcx
0x18001cbd3  mov     [rbp+0F0h+var_150], r9
0x18001cbd7  mov     qword ptr [rsp+1F0h+PerformanceCount], rax
0x18001cbdc  jz      loc_18001E1B7
0x18001cbe2  test    rcx, rcx
0x18001cbe5  jz      short loc_18001CBEC
0x18001cbe7  xor     eax, eax
0x18001cbe9  mov     [rcx], ax
0x18001cbec  test    r9, r9
0x18001cbef  jz      short loc_18001CC01
0x18001cbf1  xor     edx, edx; Val
0x18001cbf3  mov     r8d, 40h ; '@'; Size
0x18001cbf9  mov     rcx, r9; void *
0x18001cbfc  call    memset_0
0x18001cc01  mov     ebx, [rbx+20h]
0x18001cc04  call    cs:__imp_GetCurrentThreadId
0x18001cc0b  nop     dword ptr [rax+rax+00h]
0x18001cc10  cmp     eax, ebx
0x18001cc12  jnz     loc_18001D26A
0x18001cc18  test    r14, r14
0x18001cc1b  jz      loc_18001E1B7
0x18001cc21  mov     eax, [r14+14h]
0x18001cc25  cmp     [r14+10h], eax
0x18001cc29  jb      loc_18001E1B7
0x18001cc2f  test    r13d, 0FFFFFFF0h
0x18001cc36  mov     edx, r13d
0x18001cc39  setz    cl
0x18001cc3c  test    r13b, 0Fh
0x18001cc40  setnz   al
0x18001cc43  test    al, cl
0x18001cc45  jz      loc_18001E1B7
0x18001cc4b  movzx   eax, r13w
0x18001cc4f  and     ax, 3
0x18001cc53  mov     word ptr [rsp+1F0h+var_194], ax
0x18001cc58  mov     word ptr [rbp+0F0h+var_170], ax
0x18001cc5c  jz      short loc_18001CC6A
0x18001cc5e  test    edx, 0FFFFFFFCh
0x18001cc64  jnz     loc_18001E1B7
0x18001cc6a  movzx   r12d, r13w
0x18001cc6e  and     r12w, 0Ch
0x18001cc73  jz      short loc_18001CC81
0x18001cc75  test    edx, 0FFFFFFF3h
0x18001cc7b  jnz     loc_18001E1B7
0x18001cc81  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x18001cc87  xor     eax, eax
0x18001cc89  xorps   xmm0, xmm0
0x18001cc8c  mov     [rbp+0F0h+var_138], rax
0x18001cc90  xorps   xmm1, xmm1
0x18001cc93  mov     [rbp+0F0h+var_98], rax
0x18001cc97  movups  [rbp+0F0h+var_148], xmm0
0x18001cc9b  mov     [rbp+0F0h+var_168], rax
0x18001cc9f  movups  [rbp+0F0h+var_A8], xmm1
0x18001cca3  mov     [rsp+1F0h+var_38], r15
0x18001ccab  call    cs:__imp_TlsGetValue
0x18001ccb2  nop     dword ptr [rax+rax+00h]
0x18001ccb7  test    rax, rax
0x18001ccba  jz      loc_18001D63A
0x18001ccc0  mov     r15, [rax+20h]
0x18001ccc4  mov     rcx, [rsp+1F0h+var_1A0]
0x18001ccc9  mov     rbx, [rcx+18h]
0x18001cccd  mov     [rbp+0F0h+var_130], rbx
0x18001ccd1  lock inc dword ptr [rbx+8]
0x18001ccd5  test    edi, edi
0x18001ccd7  js      loc_18001D9F2
0x18001ccdd  mov     rax, [rcx]
0x18001cce0  lea     r8, [rbp+0F0h+var_168]
0x18001cce4  mov     edx, edi
0x18001cce6  mov     rax, [rax+0D8h]
0x18001cced  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ccf2  mov     edi, eax
0x18001ccf4  test    eax, eax
0x18001ccf6  js      loc_18001D776
0x18001ccfc  mov     ecx, [r14+14h]
0x18001cd00  test    ecx, ecx
0x18001cd02  jnz     loc_18001D757
0x18001cd08  mov     rcx, r14
0x18001cd0b  mov     qword ptr [rsp+1F0h+NewValue], rcx
0x18001cd10  test    r12w, r12w
0x18001cd14  jnz     loc_18001D783
0x18001cd1a  mov     [rsp+1F0h+var_180], 0
0x18001cd22  test    r15, r15
0x18001cd25  jz      short loc_18001CD2F
0x18001cd27  mov     eax, [r15+18h]
0x18001cd2b  mov     [rsp+1F0h+var_180], eax
0x18001cd2f  cmp     word ptr [rbp+0F0h+var_170], 0
0x18001cd34  mov     r10d, 400Ch
0x18001cd3a  jz      loc_18001D600
0x18001cd40  mov     rsi, [rsp+1F0h+var_1A0]
0x18001cd45  lea     r8, [rbp+0F0h+var_A8]
0x18001cd49  mov     rdx, [rbp+0F0h+var_168]
0x18001cd4d  mov     rcx, rsi
0x18001cd50  mov     rax, [rsi]
0x18001cd53  mov     rax, [rax+108h]
0x18001cd5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd5f  mov     edi, eax
0x18001cd61  test    eax, eax
0x18001cd63  js      loc_18001E164
0x18001cd69  movzx   eax, word ptr [rbp+0F0h+var_A8]
0x18001cd6d  mov     r10d, 400Ch
0x18001cd73  cmp     ax, r10w
0x18001cd77  jz      loc_18001D7F0
0x18001cd7d  cmp     ax, 4Ah ; 'J'
0x18001cd81  jz      loc_18001D7F0
0x18001cd87  lea     rsi, [rbp+0F0h+var_A8]
0x18001cd8b  mov     [rsp+1F0h+var_190], rsi
0x18001cd90  test    rsi, rsi
0x18001cd93  jz      short loc_18001CD9F
0x18001cd95  cmp     word ptr [rsi], 9
0x18001cd99  jz      loc_18001DA47
0x18001cd9f  test    r12w, r12w
0x18001cda3  jnz     loc_18001DB75
0x18001cda9  mov     r9, qword ptr [rsp+1F0h+NewValue]
0x18001cdae  cmp     dword ptr [r9+14h], 0
0x18001cdb3  jnz     loc_18001D616
0x18001cdb9  movzx   r8d, word ptr [rsi]
0x18001cdbd  cmp     r8w, r10w
0x18001cdc1  jz      loc_18001D7D7
0x18001cdc7  cmp     r8d, 4Ah ; 'J'
0x18001cdcb  jz      loc_18001D7D7
0x18001cdd1  mov     rcx, rsi
0x18001cdd4  movzx   eax, r8w
0x18001cdd8  cmp     ax, 4Ch ; 'L'
0x18001cddc  jnz     loc_18001D5BA
0x18001cde2  mov     r12, [rcx+8]
0x18001cde6  mov     [rbp+0F0h+var_170], r12
0x18001cdea  xor     eax, eax
0x18001cdec  xorps   xmm0, xmm0
0x18001cdef  mov     [rbp+0F0h+var_B0], rax
0x18001cdf3  movups  [rbp+0F0h+var_C0], xmm0
0x18001cdf7  cmp     r8w, r10w
0x18001cdfb  jz      loc_18001D7E3
0x18001ce01  cmp     r8d, 4Ah ; 'J'
0x18001ce05  jz      loc_18001D7E3
0x18001ce0b  mov     eax, 1
0x18001ce10  cmp     r8w, 50h ; 'P'
0x18001ce15  jz      loc_18001D6F9
0x18001ce1b  test    r13b, 1
0x18001ce1f  jz      loc_18001D73A
0x18001ce25  mov     r13, qword ptr [rsp+1F0h+NewValue]
0x18001ce2a  cmp     r14, r13
0x18001ce2d  jnz     loc_18001D9D0
0x18001ce33  mov     r14, [rsp+1F0h+var_1A0]
0x18001ce38  mov     eax, 9
0x18001ce3d  mov     word ptr [rbp+0F0h+var_C0], ax
0x18001ce41  mov     rcx, r14
0x18001ce44  mov     rax, [r14]
0x18001ce47  mov     rax, [rax+0B8h]
0x18001ce4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce53  mov     qword ptr [rbp+0F0h+var_C0+8], rax
0x18001ce57  mov     rdx, rax
0x18001ce5a  mov     rcx, [rax]
0x18001ce5d  mov     rax, [rcx+8]
0x18001ce61  mov     rcx, rdx
0x18001ce64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce69  lea     rcx, [rbp+0F0h+var_C0]
0x18001ce6d  mov     [rbp+0F0h+pvargSrc], rcx
0x18001ce71  mov     rdi, qword ptr [rsp+1F0h+PerformanceCount]
0x18001ce76  mov     rax, [rbx+0A8h]
0x18001ce7d  mov     [rbp+0F0h+var_128], rax
0x18001ce81  mov     [rbx+0A8h], rdi
0x18001ce88  test    rdi, rdi
0x18001ce8b  jz      short loc_18001CE9C
0x18001ce8d  mov     rax, [rdi]
0x18001ce90  mov     rcx, rdi
0x18001ce93  mov     rax, [rax+8]
0x18001ce97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce9c  mov     rcx, [rbx+0A0h]; this
0x18001cea3  test    rcx, rcx
0x18001cea6  jz      short loc_18001CEB8
0x18001cea8  call    ?Release@DexCaller@@UEAAKXZ; DexCaller::Release(void)
0x18001cead  mov     qword ptr [rbx+0A0h], 0
0x18001ceb8  mov     rax, [rbx+0C0h]
0x18001cebf  movups  xmm0, xmmword ptr cs:GUID_ScriptFunctionStart.Data1
0x18001cec6  mov     rcx, [rbx+78h]
0x18001ceca  mov     [rbx+0C0h], rdi
0x18001ced1  xor     edi, edi
0x18001ced3  mov     [rbp+0F0h+var_120], rax
0x18001ced7  movaps  [rbp+0F0h+var_110], xmm0
0x18001cedb  mov     qword ptr [rsp+1F0h+PerformanceCount], rdi
0x18001cee0  mov     [rsp+1F0h+var_194], edi
0x18001cee4  mov     [rsp+1F0h+var_198], edi
0x18001cee8  mov     [rsp+1F0h+var_190], rdi
0x18001ceed  test    rcx, rcx
0x18001cef0  jz      short loc_18001CF06
0x18001cef2  mov     rax, [rcx]
0x18001cef5  mov     rax, [rax+28h]
0x18001cef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cefe  test    eax, eax
0x18001cf00  jz      loc_18001DD94
0x18001cf06  mov     rax, [r12]
0x18001cf0a  mov     rcx, r12
0x18001cf0d  mov     rax, [rax]
0x18001cf10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf15  mov     rax, [rbx+0C8h]
0x18001cf1c  test    rax, rax
0x18001cf1f  jnz     short loc_18001CF40
0x18001cf21  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x18001cf27  call    cs:__imp_TlsGetValue
0x18001cf2e  nop     dword ptr [rax+rax+00h]
0x18001cf33  test    rax, rax
0x18001cf36  jz      loc_18001D5B2
0x18001cf3c  mov     rax, [rax+28h]
0x18001cf40  mov     rsi, [rax+38h]
0x18001cf44  test    rsi, rsi
0x18001cf47  jz      short loc_18001CF68
0x18001cf49  mov     dl, 1; bool
0x18001cf4b  mov     rcx, rsi; this
0x18001cf4e  call    ?Pin@AutoCalloutParameterLock@@AEAAJ_N@Z; AutoCalloutParameterLock::Pin(bool)
0x18001cf53  mov     rsi, [rsi]
0x18001cf56  test    eax, eax
0x18001cf58  cmovs   edi, eax
0x18001cf5b  test    rsi, rsi
0x18001cf5e  jnz     short loc_18001CF49
0x18001cf60  test    edi, edi
0x18001cf62  js      loc_18001DE3C
0x18001cf68  mov     rax, [r14]
0x18001cf6b  mov     rcx, r14
0x18001cf6e  mov     rax, [rax+128h]
0x18001cf75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf7a  mov     r14d, [r13+10h]
0x18001cf7e  mov     edi, eax
0x18001cf80  mov     rax, [r13+0]
0x18001cf84  mov     qword ptr [rsp+1F0h+PerformanceCount], rax
0x18001cf89  mov     [rsp+1F0h+var_194], r14d
0x18001cf8e  lock inc dword ptr [rbx+8]
0x18001cf92  xor     eax, eax
0x18001cf94  mov     qword ptr [rbp+0F0h+Buffer], rbx
0x18001cf98  mov     [rbp+0F0h+var_80], rax
0x18001cf9c  xorps   xmm0, xmm0
0x18001cf9f  mov     rax, [r12]
0x18001cfa3  xorps   xmm1, xmm1
0x18001cfa6  xor     esi, esi
0x18001cfa8  mov     rcx, r12
0x18001cfab  movdqu  xmmword ptr [rbp+0F0h+pvargDest], xmm0
0x18001cfb3  mov     [rbp+0F0h+var_60], rsi
0x18001cfba  mov     rax, [rax]
0x18001cfbd  movups  [rbp+0F0h+var_90], xmm1
0x18001cfc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cfc6  mov     eax, edi
0x18001cfc8  shr     eax, 1
0x18001cfca  and     eax, 2
0x18001cfcd  mov     ecx, eax
0x18001cfcf  or      ecx, 4
0x18001cfd2  test    dil, 8
0x18001cfd6  cmovz   ecx, eax
0x18001cfd9  mov     dword ptr [rbp+0F0h+var_170], ecx
0x18001cfdc  mov     rcx, [rbx+20h]
0x18001cfe0  test    rcx, rcx
0x18001cfe3  jz      loc_18001D659
0x18001cfe9  cmp     [rcx+3A0h], rsi
0x18001cff0  jz      short loc_18001D000
0x18001cff2  add     rcx, 0C8h; this
0x18001cff9  jz      short loc_18001D000
0x18001cffb  call    ?JAmsiInitialize@JAmsi@@QEAA_NXZ; JAmsi::JAmsiInitialize(void)
0x18001d000  xor     edx, edx; Mask
0x18001d002  xor     ecx, ecx; NewValue
0x18001d004  call    cs:__imp__controlfp
0x18001d00b  nop     dword ptr [rax+rax+00h]
0x18001d010  mov     edx, 30F031Fh; Mask
0x18001d015  mov     ecx, 1Fh; NewValue
0x18001d01a  mov     [rsp+1F0h+NewValue], eax
0x18001d01e  call    cs:__imp__controlfp
0x18001d025  nop     dword ptr [rax+rax+00h]
0x18001d02a  cmp     [rbp+0F0h+var_160], rsi
0x18001d02e  lea     r13, [rbp+0F0h+var_90]
0x18001d032  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x18001d038  cmovz   r13, rsi
0x18001d03c  mov     [rsp+1F0h+var_190], r13
0x18001d041  call    cs:__imp_TlsGetValue
0x18001d048  nop     dword ptr [rax+rax+00h]
0x18001d04d  test    rax, rax
0x18001d050  jz      loc_18001D68C
0x18001d056  mov     rsi, [rax+20h]
0x18001d05a  mov     [rbp+0F0h+var_158], rsi
0x18001d05e  test    rsi, rsi
0x18001d061  jz      loc_18001D690
0x18001d067  mov     eax, [rsi+18h]
0x18001d06a  mov     [rsp+1F0h+var_198], eax
  ... truncated ...
```
