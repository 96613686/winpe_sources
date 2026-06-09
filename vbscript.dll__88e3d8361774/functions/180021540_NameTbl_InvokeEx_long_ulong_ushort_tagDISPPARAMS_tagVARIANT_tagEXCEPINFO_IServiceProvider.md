# NameTbl::InvokeEx(long,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,IServiceProvider *)

- ea: `0x180021540`
- end: `0x180022b11`
- name: `?InvokeEx@NameTbl@@UEAAJJKGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAUIServiceProvider@@@Z`
- size: `5585`
- prototype: `__int64 __fastcall(NameTbl *__hidden this, int, unsigned int, unsigned __int16, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, struct IServiceProvider *)`
- caller_count: `0`
- callee_count: `28`
- tags: `service_task, installer_update`

## callees

- `0x180004d80`
- `0x18000524c`
- `0x18000530c`
- `0x180005e00`
- `0x180008040`
- `0x18001bd20`
- `0x1800200dc`
- `0x1800203e0`
- `0x1800209f0`
- `0x180020a50`
- `0x180021540`
- `0x180022b20`
- `0x180023868`
- `0x180028090`
- `0x18002c730`
- `0x18002c9c0`
- `0x18002cc60`
- `0x180035468`
- `0x180035d84`
- `0x180036f90`
- `0x180037914`
- `0x180037934`
- `0x180042974`
- `0x18005f68c`
- `0x18007552c`
- `0x180076746`
- `0x1800767a0`
- `0x180077010`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180022720`
- `msvcrt!swprintf_s` at `0x18002299b`
- `msvcrt!swprintf_s` at `0x180022720`
- `msvcrt!swprintf_s` at `0x18002299b`
- `msvcrt!_controlfp` at `0x1800219c2`
- `msvcrt!_controlfp` at `0x1800219d6`
- `msvcrt!_controlfp` at `0x180021c42`
- `msvcrt!_controlfp` at `0x1800219c2`
- `msvcrt!_controlfp` at `0x1800219d6`
- `msvcrt!_controlfp` at `0x180021c42`
- `msvcrt!malloc` at `0x1800221bf`
- `msvcrt!malloc` at `0x1800221bf`
- `msvcrt!free` at `0x180022194`
- `msvcrt!free` at `0x180022194`
- `OLEAUT32!__imp_VariantCopy` at `0x180021b63`
- `OLEAUT32!__imp_VariantCopy` at `0x180021bd7`
- `OLEAUT32!__imp_VariantCopy` at `0x180021b63`
- `OLEAUT32!__imp_VariantCopy` at `0x180021bd7`
- `OLEAUT32!__imp_SafeArrayLock` at `0x180022624`
- `OLEAUT32!__imp_SafeArrayLock` at `0x180022624`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18002265c`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18002265c`
- `KERNEL32!QueryPerformanceCounter` at `0x18002272f`
- `KERNEL32!QueryPerformanceCounter` at `0x1800229a9`
- `KERNEL32!QueryPerformanceCounter` at `0x18002272f`
- `KERNEL32!QueryPerformanceCounter` at `0x1800229a9`
- `KERNEL32!TlsGetValue` at `0x180021675`
- `KERNEL32!TlsGetValue` at `0x1800218eb`
- `KERNEL32!TlsGetValue` at `0x1800219f3`
- `KERNEL32!TlsGetValue` at `0x180021aac`
- `KERNEL32!TlsGetValue` at `0x180021d3e`
- `KERNEL32!TlsGetValue` at `0x180021d75`
- `KERNEL32!TlsGetValue` at `0x180021e4c`
- `KERNEL32!TlsGetValue` at `0x180021675`
- `KERNEL32!TlsGetValue` at `0x1800218eb`
- `KERNEL32!TlsGetValue` at `0x1800219f3`
- `KERNEL32!TlsGetValue` at `0x180021aac`
- `KERNEL32!TlsGetValue` at `0x180021d3e`
- `KERNEL32!TlsGetValue` at `0x180021d75`
- `KERNEL32!TlsGetValue` at `0x180021e4c`
- `KERNEL32!GetCurrentThreadId` at `0x1800215d4`
- `KERNEL32!GetCurrentThreadId` at `0x1800215d4`

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
  int StdVar; // edi
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
  int v84; // eax
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
  VARIANTARG *v120; // r9
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
            v120 = (VARIANTARG *)(**(_QWORD **)NewValue + 24LL);
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
        StdVar = AccessArray((struct VAR **)&v148, (struct VAR *)v20, v89, *(VARIANTARG **)v88, 0);
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
0x180021540  push    rbp
0x180021542  push    rbx
0x180021543  push    rsi
0x180021544  push    rdi
0x180021545  push    r12
0x180021547  push    r13
0x180021549  push    r14
0x18002154b  lea     rbp, [rsp-0C0h]
0x180021553  sub     rsp, 1C0h
0x18002155a  mov     rax, cs:__security_cookie
0x180021561  xor     rax, rsp
0x180021564  mov     [rbp+0F0h+var_50], rax
0x18002156b  mov     rax, [rbp+0F0h+arg_38]
0x180021572  mov     rbx, rcx
0x180021575  mov     r14, [rbp+0F0h+arg_20]
0x18002157c  mov     edi, edx
0x18002157e  movzx   r13d, r9w
0x180021582  mov     r9, [rbp+0F0h+arg_30]
0x180021589  cmp     qword ptr [rbx+18h], 0
0x18002158e  mov     [rsp+1F0h+var_1A0], rcx
0x180021593  mov     rcx, [rbp+0F0h+arg_28]
0x18002159a  mov     [rsp+1F0h+var_198], r8d
0x18002159f  mov     [rbp+0F0h+var_160], rcx
0x1800215a3  mov     [rbp+0F0h+var_150], r9
0x1800215a7  mov     qword ptr [rsp+1F0h+PerformanceCount], rax
0x1800215ac  jz      loc_180022B07
0x1800215b2  test    rcx, rcx
0x1800215b5  jz      short loc_1800215BC
0x1800215b7  xor     eax, eax
0x1800215b9  mov     [rcx], ax
0x1800215bc  test    r9, r9
0x1800215bf  jz      short loc_1800215D1
0x1800215c1  xor     edx, edx; Val
0x1800215c3  mov     r8d, 40h ; '@'; Size
0x1800215c9  mov     rcx, r9; void *
0x1800215cc  call    memset_0
0x1800215d1  mov     ebx, [rbx+20h]
0x1800215d4  call    cs:__imp_GetCurrentThreadId
0x1800215da  cmp     eax, ebx
0x1800215dc  jnz     loc_180021C04
0x1800215e2  test    r14, r14
0x1800215e5  jz      loc_180022B07
0x1800215eb  mov     eax, [r14+14h]
0x1800215ef  cmp     [r14+10h], eax
0x1800215f3  jb      loc_180022B07
0x1800215f9  test    r13d, 0FFFFFFF0h
0x180021600  mov     edx, r13d
0x180021603  setz    cl
0x180021606  test    r13b, 0Fh
0x18002160a  setnz   al
0x18002160d  test    al, cl
0x18002160f  jz      loc_180022B07
0x180021615  movzx   eax, r13w
0x180021619  and     ax, 3
0x18002161d  mov     word ptr [rsp+1F0h+var_194], ax
0x180021622  mov     word ptr [rbp+0F0h+var_170], ax
0x180021626  jz      short loc_180021634
0x180021628  test    edx, 0FFFFFFFCh
0x18002162e  jnz     loc_180022B07
0x180021634  movzx   r12d, r13w
0x180021638  and     r12w, 0Ch
0x18002163d  jz      short loc_18002164B
0x18002163f  test    edx, 0FFFFFFF3h
0x180021645  jnz     loc_180022B07
0x18002164b  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x180021651  xor     eax, eax
0x180021653  xorps   xmm0, xmm0
0x180021656  mov     [rbp+0F0h+var_138], rax
0x18002165a  xorps   xmm1, xmm1
0x18002165d  mov     [rbp+0F0h+var_98], rax
0x180021661  movups  [rbp+0F0h+var_148], xmm0
0x180021665  mov     [rbp+0F0h+var_168], rax
0x180021669  movups  [rbp+0F0h+var_A8], xmm1
0x18002166d  mov     [rsp+1F0h+var_38], r15
0x180021675  call    cs:__imp_TlsGetValue
0x18002167b  test    rax, rax
0x18002167e  jz      loc_180021FBB
0x180021684  mov     r15, [rax+20h]
0x180021688  mov     rcx, [rsp+1F0h+var_1A0]
0x18002168d  mov     rbx, [rcx+18h]
0x180021691  mov     [rbp+0F0h+var_130], rbx
0x180021695  lock inc dword ptr [rbx+8]
0x180021699  test    edi, edi
0x18002169b  js      loc_180022366
0x1800216a1  mov     rax, [rcx]
0x1800216a4  lea     r8, [rbp+0F0h+var_168]
0x1800216a8  mov     edx, edi
0x1800216aa  mov     rax, [rax+0D8h]
0x1800216b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800216b6  mov     edi, eax
0x1800216b8  test    eax, eax
0x1800216ba  js      loc_1800220F6
0x1800216c0  mov     ecx, [r14+14h]
0x1800216c4  test    ecx, ecx
0x1800216c6  jnz     loc_1800220D7
0x1800216cc  mov     rcx, r14
0x1800216cf  mov     qword ptr [rsp+1F0h+NewValue], rcx
0x1800216d4  test    r12w, r12w
0x1800216d8  jnz     loc_180022103
0x1800216de  mov     [rsp+1F0h+var_180], 0
0x1800216e6  test    r15, r15
0x1800216e9  jz      short loc_1800216F3
0x1800216eb  mov     eax, [r15+18h]
0x1800216ef  mov     [rsp+1F0h+var_180], eax
0x1800216f3  cmp     word ptr [rbp+0F0h+var_170], 0
0x1800216f8  mov     r10d, 400Ch
0x1800216fe  jz      loc_180021F81
0x180021704  mov     rsi, [rsp+1F0h+var_1A0]
0x180021709  lea     r8, [rbp+0F0h+var_A8]
0x18002170d  mov     rdx, [rbp+0F0h+var_168]
0x180021711  mov     rcx, rsi
0x180021714  mov     rax, [rsi]
0x180021717  mov     rax, [rax+108h]
0x18002171e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021723  mov     edi, eax
0x180021725  test    eax, eax
0x180021727  js      loc_180022AB4
0x18002172d  movzx   eax, word ptr [rbp+0F0h+var_A8]
0x180021731  mov     r10d, 400Ch
0x180021737  cmp     ax, r10w
0x18002173b  jz      loc_180022170
0x180021741  cmp     ax, 4Ah ; 'J'
0x180021745  jz      loc_180022170
0x18002174b  lea     rsi, [rbp+0F0h+var_A8]
0x18002174f  mov     [rsp+1F0h+var_190], rsi
0x180021754  test    rsi, rsi
0x180021757  jz      short loc_180021763
0x180021759  cmp     word ptr [rsi], 9
0x18002175d  jz      loc_1800223BB
0x180021763  test    r12w, r12w
0x180021767  jnz     loc_1800224E9
0x18002176d  mov     r9, qword ptr [rsp+1F0h+NewValue]
0x180021772  cmp     dword ptr [r9+14h], 0
0x180021777  jnz     loc_180021F97
0x18002177d  movzx   r8d, word ptr [rsi]
0x180021781  cmp     r8w, r10w
0x180021785  jz      loc_180022157
0x18002178b  cmp     r8d, 4Ah ; 'J'
0x18002178f  jz      loc_180022157
0x180021795  mov     rcx, rsi
0x180021798  movzx   eax, r8w
0x18002179c  cmp     ax, 4Ch ; 'L'
0x1800217a0  jnz     loc_180021F3B
0x1800217a6  mov     r12, [rcx+8]
0x1800217aa  mov     [rbp+0F0h+var_170], r12
0x1800217ae  xor     eax, eax
0x1800217b0  xorps   xmm0, xmm0
0x1800217b3  mov     [rbp+0F0h+var_B0], rax
0x1800217b7  movups  [rbp+0F0h+var_C0], xmm0
0x1800217bb  cmp     r8w, r10w
0x1800217bf  jz      loc_180022163
0x1800217c5  cmp     r8d, 4Ah ; 'J'
0x1800217c9  jz      loc_180022163
0x1800217cf  mov     eax, 1
0x1800217d4  cmp     r8w, 50h ; 'P'
0x1800217d9  jz      loc_180022079
0x1800217df  test    r13b, 1
0x1800217e3  jz      loc_1800220BA
0x1800217e9  mov     r13, qword ptr [rsp+1F0h+NewValue]
0x1800217ee  cmp     r14, r13
0x1800217f1  jnz     loc_180022344
0x1800217f7  mov     r14, [rsp+1F0h+var_1A0]
0x1800217fc  mov     eax, 9
0x180021801  mov     word ptr [rbp+0F0h+var_C0], ax
0x180021805  mov     rcx, r14
0x180021808  mov     rax, [r14]
0x18002180b  mov     rax, [rax+0B8h]
0x180021812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021817  mov     qword ptr [rbp+0F0h+var_C0+8], rax
0x18002181b  mov     rdx, rax
0x18002181e  mov     rcx, [rax]
0x180021821  mov     rax, [rcx+8]
0x180021825  mov     rcx, rdx
0x180021828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002182d  lea     rcx, [rbp+0F0h+var_C0]
0x180021831  mov     [rbp+0F0h+pvargSrc], rcx
0x180021835  mov     rdi, qword ptr [rsp+1F0h+PerformanceCount]
0x18002183a  mov     rax, [rbx+0A8h]
0x180021841  mov     [rbp+0F0h+var_128], rax
0x180021845  mov     [rbx+0A8h], rdi
0x18002184c  test    rdi, rdi
0x18002184f  jz      short loc_180021860
0x180021851  mov     rax, [rdi]
0x180021854  mov     rcx, rdi
0x180021857  mov     rax, [rax+8]
0x18002185b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021860  mov     rcx, [rbx+0A0h]; this
0x180021867  test    rcx, rcx
0x18002186a  jz      short loc_18002187C
0x18002186c  call    ?Release@DexCaller@@UEAAKXZ; DexCaller::Release(void)
0x180021871  mov     qword ptr [rbx+0A0h], 0
0x18002187c  mov     rax, [rbx+0C0h]
0x180021883  movups  xmm0, xmmword ptr cs:GUID_ScriptFunctionStart.Data1
0x18002188a  mov     rcx, [rbx+78h]
0x18002188e  mov     [rbx+0C0h], rdi
0x180021895  xor     edi, edi
0x180021897  mov     [rbp+0F0h+var_120], rax
0x18002189b  movaps  [rbp+0F0h+var_110], xmm0
0x18002189f  mov     qword ptr [rsp+1F0h+PerformanceCount], rdi
0x1800218a4  mov     [rsp+1F0h+var_194], edi
0x1800218a8  mov     [rsp+1F0h+var_198], edi
0x1800218ac  mov     [rsp+1F0h+var_190], rdi
0x1800218b1  test    rcx, rcx
0x1800218b4  jz      short loc_1800218CA
0x1800218b6  mov     rax, [rcx]
0x1800218b9  mov     rax, [rax+28h]
0x1800218bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218c2  test    eax, eax
0x1800218c4  jz      loc_1800226FC
0x1800218ca  mov     rax, [r12]
0x1800218ce  mov     rcx, r12
0x1800218d1  mov     rax, [rax]
0x1800218d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218d9  mov     rax, [rbx+0C8h]
0x1800218e0  test    rax, rax
0x1800218e3  jnz     short loc_1800218FE
0x1800218e5  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x1800218eb  call    cs:__imp_TlsGetValue
0x1800218f1  test    rax, rax
0x1800218f4  jz      loc_180021F33
0x1800218fa  mov     rax, [rax+28h]
0x1800218fe  mov     rsi, [rax+38h]
0x180021902  test    rsi, rsi
0x180021905  jz      short loc_180021926
0x180021907  mov     dl, 1; bool
0x180021909  mov     rcx, rsi; this
0x18002190c  call    ?Pin@AutoCalloutParameterLock@@AEAAJ_N@Z; AutoCalloutParameterLock::Pin(bool)
0x180021911  mov     rsi, [rsi]
0x180021914  test    eax, eax
0x180021916  cmovs   edi, eax
0x180021919  test    rsi, rsi
0x18002191c  jnz     short loc_180021907
0x18002191e  test    edi, edi
0x180021920  js      loc_180022798
0x180021926  mov     rax, [r14]
0x180021929  mov     rcx, r14
0x18002192c  mov     rax, [rax+128h]
0x180021933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021938  mov     r14d, [r13+10h]
0x18002193c  mov     edi, eax
0x18002193e  mov     rax, [r13+0]
0x180021942  mov     qword ptr [rsp+1F0h+PerformanceCount], rax
0x180021947  mov     [rsp+1F0h+var_194], r14d
0x18002194c  lock inc dword ptr [rbx+8]
0x180021950  xor     eax, eax
0x180021952  mov     qword ptr [rbp+0F0h+Buffer], rbx
0x180021956  mov     [rbp+0F0h+var_80], rax
0x18002195a  xorps   xmm0, xmm0
0x18002195d  mov     rax, [r12]
0x180021961  xorps   xmm1, xmm1
0x180021964  xor     esi, esi
0x180021966  mov     rcx, r12
0x180021969  movdqu  xmmword ptr [rbp+0F0h+pvargDest], xmm0
0x180021971  mov     [rbp+0F0h+var_60], rsi
0x180021978  mov     rax, [rax]
0x18002197b  movups  [rbp+0F0h+var_90], xmm1
0x18002197f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021984  mov     eax, edi
0x180021986  shr     eax, 1
0x180021988  and     eax, 2
0x18002198b  mov     ecx, eax
0x18002198d  or      ecx, 4
0x180021990  test    dil, 8
0x180021994  cmovz   ecx, eax
0x180021997  mov     dword ptr [rbp+0F0h+var_170], ecx
0x18002199a  mov     rcx, [rbx+20h]
0x18002199e  test    rcx, rcx
0x1800219a1  jz      loc_180021FDA
0x1800219a7  cmp     [rcx+3A0h], rsi
0x1800219ae  jz      short loc_1800219BE
0x1800219b0  add     rcx, 0C8h; this
0x1800219b7  jz      short loc_1800219BE
0x1800219b9  call    ?JAmsiInitialize@JAmsi@@QEAA_NXZ; JAmsi::JAmsiInitialize(void)
0x1800219be  xor     edx, edx; Mask
0x1800219c0  xor     ecx, ecx; NewValue
0x1800219c2  call    cs:__imp__controlfp
0x1800219c8  mov     edx, 30F031Fh; Mask
0x1800219cd  mov     ecx, 1Fh; NewValue
0x1800219d2  mov     [rsp+1F0h+NewValue], eax
0x1800219d6  call    cs:__imp__controlfp
0x1800219dc  cmp     [rbp+0F0h+var_160], rsi
0x1800219e0  lea     r13, [rbp+0F0h+var_90]
0x1800219e4  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x1800219ea  cmovz   r13, rsi
0x1800219ee  mov     [rsp+1F0h+var_190], r13
0x1800219f3  call    cs:__imp_TlsGetValue
0x1800219f9  test    rax, rax
0x1800219fc  jz      loc_18002200D
0x180021a02  mov     rsi, [rax+20h]
0x180021a06  mov     [rbp+0F0h+var_158], rsi
0x180021a0a  test    rsi, rsi
0x180021a0d  jz      loc_180022011
0x180021a13  mov     eax, [rsi+18h]
0x180021a16  mov     [rsp+1F0h+var_198], eax
0x180021a1a  test    r14d, r14d
0x180021a1d  js      loc_180022183
0x180021a23  xor     eax, eax
0x180021a25  cmp     [rbp+0F0h+pvargSrc], rax
0x180021a29  setnz   al
0x180021a2c  add     r14d, eax
  ... truncated ...
```
