# InvokeDispatch(CSession *,IDispatch *,long,ulong,VAR *,int,VAR *)

- ea: `0x180006550`
- end: `0x18000798c`
- name: `?InvokeDispatch@@YAJPEAVCSession@@PEAUIDispatch@@JKPEAVVAR@@H2@Z`
- size: `5180`
- prototype: `__int64 __usercall@<rax>(struct CSession *this@<rcx>, struct IDispatch *@<rdx>, int@<r8d>, unsigned int@<r9d>, struct VAR *, int, struct VAR *)`
- caller_count: `7`
- callee_count: `23`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180006230`
- `0x180021160`
- `0x180023ad0`
- `0x180036fe0`
- `0x180041c00`
- `0x18006b020`
- `0x18006c8ac`

## callees

- `0x180003930`
- `0x180004a50`
- `0x1800051f0`
- `0x1800060b0`
- `0x180006180`
- `0x180006550`
- `0x180007a10`
- `0x180007a80`
- `0x180007b38`
- `0x180007d78`
- `0x180007de0`
- `0x180008cc0`
- `0x18001ff14`
- `0x1800209f0`
- `0x180022b20`
- `0x180035468`
- `0x180037b80`
- `0x180045490`
- `0x1800663d8`
- `0x1800692dc`
- `0x18007552c`
- `0x1800767a0`
- `0x180077010`

## import_xrefs

- `msvcrt!calloc` at `0x18000661d`
- `msvcrt!calloc` at `0x180006633`
- `msvcrt!calloc` at `0x18000664c`
- `msvcrt!calloc` at `0x18000661d`
- `msvcrt!calloc` at `0x180006633`
- `msvcrt!calloc` at `0x18000664c`
- `msvcrt!free` at `0x1800077b1`
- `msvcrt!free` at `0x1800077ba`
- `msvcrt!free` at `0x1800077c5`
- `msvcrt!free` at `0x18000795e`
- `msvcrt!free` at `0x180076985`
- `msvcrt!free` at `0x18007698e`
- `msvcrt!free` at `0x180076997`
- `msvcrt!free` at `0x1800769f4`
- `msvcrt!free` at `0x1800077b1`
- `msvcrt!free` at `0x1800077ba`
- `msvcrt!free` at `0x1800077c5`
- `msvcrt!free` at `0x18000795e`
- `msvcrt!free` at `0x180076985`
- `msvcrt!free` at `0x18007698e`
- `msvcrt!free` at `0x180076997`
- `msvcrt!free` at `0x1800769f4`
- `OLEAUT32!SafeArrayReleaseDescriptor` at `0x180007911`
- `OLEAUT32!SafeArrayReleaseDescriptor` at `0x180076950`
- `OLEAUT32!SafeArrayReleaseDescriptor` at `0x180007911`
- `OLEAUT32!SafeArrayReleaseDescriptor` at `0x180076950`
- `OLEAUT32!SafeArrayAddRef` at `0x180007190`
- `OLEAUT32!SafeArrayAddRef` at `0x180007190`
- `OLEAUT32!SafeArrayReleaseData` at `0x18000793a`
- `OLEAUT32!SafeArrayReleaseData` at `0x180076975`
- `OLEAUT32!SafeArrayReleaseData` at `0x18000793a`
- `OLEAUT32!SafeArrayReleaseData` at `0x180076975`
- `OLEAUT32!__imp_VariantClear` at `0x1800076e1`
- `OLEAUT32!__imp_VariantClear` at `0x1800076e1`
- `KERNEL32!TlsGetValue` at `0x1800067dc`
- `KERNEL32!TlsGetValue` at `0x1800069d8`
- `KERNEL32!TlsGetValue` at `0x180006da2`
- `KERNEL32!TlsGetValue` at `0x1800067dc`
- `KERNEL32!TlsGetValue` at `0x1800069d8`
- `KERNEL32!TlsGetValue` at `0x180006da2`
- `OLE32!CoTaskMemAlloc` at `0x1800068c5`
- `OLE32!CoTaskMemAlloc` at `0x180007065`
- `OLE32!CoTaskMemAlloc` at `0x1800068c5`
- `OLE32!CoTaskMemAlloc` at `0x180007065`
- `OLE32!CoTaskMemFree` at `0x180007053`
- `OLE32!CoTaskMemFree` at `0x1800078d3`
- `OLE32!CoTaskMemFree` at `0x180007053`
- `OLE32!CoTaskMemFree` at `0x1800078d3`

## pseudocode

```c
__int64 __fastcall InvokeDispatch(
        struct CSession *this,
        struct IDispatch *a2,
        int a3,
        char a4,
        VARIANTARG *a5,
        int a6,
        struct VAR *a7)
{
  struct IDispatch *v8; // r15
  VARIANTARG *v10; // r12
  int v11; // r14d
  void *v12; // r13
  void *v13; // rax
  int v14; // r8d
  int v15; // ecx
  __int64 v16; // rdx
  unsigned int v17; // r13d
  VARIANTARG *v18; // rcx
  __int64 v19; // rdx
  int v20; // edi
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // rax
  UINT cArgs; // edi
  VARIANTARG *rgvarg; // r14
  unsigned int v26; // r8d
  __int64 i; // rdx
  unsigned int v28; // esi
  __int64 j; // rdx
  __int64 v30; // rcx
  _QWORD *Value; // rax
  unsigned int v32; // esi
  char *v33; // r15
  __int16 *v34; // rax
  __int16 v35; // cx
  __int64 v36; // rdx
  int v37; // eax
  __int64 v38; // rcx
  char *v39; // rax
  _QWORD *v40; // r14
  int v41; // r12d
  _QWORD *v42; // rax
  int v43; // edi
  CSession *v44; // rcx
  const struct _GUID *v45; // r9
  __int64 v46; // rdx
  struct IServiceProvider *v47; // r14
  __int64 v48; // rdi
  CSession *v49; // rax
  CSession *v50; // rcx
  __int64 v51; // rcx
  int (__fastcall ***v52)(_QWORD, GUID *); // rcx
  bool v53; // si
  __int64 v54; // r11
  __int64 v55; // rsi
  int v56; // esi
  struct IDispatch *v57; // rdi
  bool v58; // si
  __int64 v59; // rax
  __int64 v60; // r11
  __int64 v61; // rsi
  DexCaller *v62; // rcx
  __int64 v63; // rcx
  int vt; // edx
  int (__fastcall ***llVal)(_QWORD, GUID *, VARIANTARG **); // rcx
  _QWORD *v66; // rax
  __int64 v67; // rdi
  GcBlockFactory *v68; // rcx
  _WORD *v69; // rcx
  LONGLONG v70; // rax
  __int64 v71; // rax
  __int64 v72; // rax
  VARIANTARG *v73; // r8
  __int64 v74; // rcx
  char *v75; // rax
  int v76; // r8d
  int v77; // r8d
  bool v78; // al
  __int64 v79; // rdx
  int (__fastcall ***v80)(_QWORD, GUID *, struct IDispatch **); // rcx
  SAFEARRAY *v81; // rsi
  int v82; // eax
  struct GcBlock *v83; // rdx
  _QWORD *v84; // rcx
  _QWORD *v85; // rax
  __int64 v86; // rax
  __int64 v87; // rsi
  int v88; // eax
  __int64 v89; // r10
  FncInfo *v90; // r15
  __int64 v91; // rcx
  int *v92; // r12
  int *v93; // r13
  void (__fastcall *v94)(__int64, __int64, __int128 *); // r10
  __int64 v95; // r9
  int v96; // eax
  int v97; // edx
  __int64 v98; // r10
  FncInfo *v99; // r14
  __int64 v100; // rcx
  int *v101; // r15
  int *v102; // r12
  void (__fastcall *v103)(__int64, __int64, __int128 *, __int64, int, int, _QWORD); // r10
  int v104; // esi
  _QWORD **v105; // r13
  int v106; // esi
  int v107; // r12d
  SAFEARRAY **v108; // r15
  unsigned int v109; // esi
  unsigned int k; // ebx
  int v112; // r15d
  unsigned int v113; // [rsp+50h] [rbp-3C8h]
  int v114; // [rsp+54h] [rbp-3C4h] BYREF
  int v115; // [rsp+58h] [rbp-3C0h]
  int v116; // [rsp+5Ch] [rbp-3BCh]
  bool v117; // [rsp+60h] [rbp-3B8h]
  bool v118; // [rsp+61h] [rbp-3B7h]
  void *v119; // [rsp+68h] [rbp-3B0h]
  VARIANTARG *pvarg; // [rsp+70h] [rbp-3A8h] BYREF
  int v121; // [rsp+78h] [rbp-3A0h]
  int v122; // [rsp+7Ch] [rbp-39Ch]
  int v123; // [rsp+80h] [rbp-398h]
  unsigned int v124; // [rsp+84h] [rbp-394h]
  int v125; // [rsp+88h] [rbp-390h]
  VAR *v126; // [rsp+90h] [rbp-388h] BYREF
  void *Block; // [rsp+98h] [rbp-380h]
  int v128; // [rsp+A0h] [rbp-378h]
  int v129; // [rsp+A4h] [rbp-374h]
  int v130; // [rsp+A8h] [rbp-370h]
  int v131; // [rsp+ACh] [rbp-36Ch]
  struct IDispatch *v132; // [rsp+B0h] [rbp-368h] BYREF
  __int128 v133; // [rsp+B8h] [rbp-360h]
  __int128 v134; // [rsp+C8h] [rbp-350h]
  struct tagDISPPARAMS v135; // [rsp+D8h] [rbp-340h] BYREF
  int v136; // [rsp+F0h] [rbp-328h] BYREF
  int v137; // [rsp+F4h] [rbp-324h]
  __int64 v138; // [rsp+F8h] [rbp-320h] BYREF
  struct IDispatch *v139; // [rsp+100h] [rbp-318h] BYREF
  __int64 v140; // [rsp+108h] [rbp-310h] BYREF
  void *v141; // [rsp+110h] [rbp-308h]
  _QWORD *v142; // [rsp+118h] [rbp-300h]
  __int64 v143; // [rsp+120h] [rbp-2F8h]
  void *v144; // [rsp+128h] [rbp-2F0h]
  unsigned int v145; // [rsp+130h] [rbp-2E8h]
  int v146; // [rsp+134h] [rbp-2E4h]
  int v147; // [rsp+138h] [rbp-2E0h]
  void *v148; // [rsp+140h] [rbp-2D8h]
  PVOID ppDataToRelease[3]; // [rsp+148h] [rbp-2D0h] BYREF
  struct tagEXCEPINFO v150; // [rsp+160h] [rbp-2B8h] BYREF
  __int128 v151; // [rsp+1A0h] [rbp-278h] BYREF
  __int128 v152; // [rsp+1B0h] [rbp-268h] BYREF
  __int64 v153; // [rsp+1C0h] [rbp-258h] BYREF
  __int64 v154; // [rsp+1C8h] [rbp-250h]
  LPVOID pv; // [rsp+1D0h] [rbp-248h]
  unsigned int v156; // [rsp+1D8h] [rbp-240h]
  _BYTE v157[256]; // [rsp+1E0h] [rbp-238h] BYREF
  char v158[240]; // [rsp+2E0h] [rbp-138h] BYREF

  v116 = a3;
  v8 = a2;
  v132 = a2;
  ppDataToRelease[2] = this;
  v10 = a5;
  pvarg = a5;
  v11 = a6;
  v123 = a6;
  v126 = a7;
  memset(&v135, 0, sizeof(v135));
  memset(&v150, 0, sizeof(v150));
  v139 = 0;
  v144 = 0;
  AutoCalloutParameterLock::AutoCalloutParameterLock((AutoCalloutParameterLock *)&v153);
  Block = calloc(a6, 8u);
  v12 = calloc(a6, 8u);
  v141 = v12;
  v13 = calloc(a6, 8u);
  v119 = v13;
  if ( !Block || (ppDataToRelease[1] = v12) == 0 || (v148 = v13) == 0 )
  {
    AutoCalloutParameterLock::~AutoCalloutParameterLock((AutoCalloutParameterLock *)&v153);
    return 2147942414LL;
  }
  v14 = 0;
  v142 = 0;
  v15 = 0;
  v115 = 0;
  v122 = 0;
  v16 = 0;
  v113 = 0;
  v125 = 0;
  v143 = 0;
  v17 = a4 & 0xF;
  v147 = v17;
  if ( !v8 )
  {
    v20 = -2146827864;
    v114 = -2146827864;
    goto LABEL_237;
  }
  if ( (v17 & 0xC) != 0 )
  {
    v136 = -3;
    v135.rgdispidNamedArgs = &v136;
    v135.cNamedArgs = 1;
    v18 = (VARIANTARG *)v126;
    if ( (a4 & 8) != 0 && !(unsigned int)VAR::IsIDispatch(v126) )
    {
      if ( (a4 & 4) == 0 )
      {
        v20 = -2146827864;
        v114 = -2146827864;
        goto LABEL_157;
      }
      v17 = 4;
      v147 = 4;
    }
  }
  else
  {
    v135.rgdispidNamedArgs = 0;
    v135.cNamedArgs = 0;
    v18 = (VARIANTARG *)v126;
  }
  v135.cArgs = a6;
  v135.rgvarg = v18;
  v20 = MungeArgs(v17, v8, &v135, v158);
  v114 = v20;
  if ( v20 < 0 )
    goto LABEL_156;
  v23 = *((_QWORD *)this + 4);
  if ( !v23 || !*(_DWORD *)(v23 + 260) )
  {
    if ( v8->lpVtbl < ImageEnd && v8->lpVtbl >= (struct IDispatchVtbl *)&_ImageBase )
    {
      v20 = 1;
      goto LABEL_39;
    }
    cArgs = v135.cArgs;
    rgvarg = v135.rgvarg;
    v121 = 0;
    v26 = 0;
    v124 = 0;
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      v121 = i;
      if ( (unsigned int)i >= v135.cArgs )
        break;
      if ( (v135.rgvarg[i].vt & 0x4000) != 0 )
        v124 = ++v26;
    }
    if ( v26 > 8 )
    {
      pv = CoTaskMemAlloc(32LL * v26);
      if ( !pv )
      {
        v20 = -2147024882;
LABEL_38:
        v11 = v123;
LABEL_39:
        v114 = v20;
        if ( v20 >= 0 )
          goto LABEL_40;
LABEL_156:
        v14 = 0;
LABEL_157:
        v13 = v119;
        v15 = v115;
        v16 = v113;
        goto LABEL_237;
      }
    }
    else
    {
      pv = v157;
    }
    v28 = 0;
    v124 = 0;
    for ( j = 0; ; j = (unsigned int)(j + 1) )
    {
      v121 = j;
      if ( (unsigned int)j >= cArgs )
        break;
      v73 = &rgvarg[j];
      if ( (v73->vt & 0x4000) != 0 )
      {
        v74 = 32LL * v28;
        v75 = (char *)pv;
        *(_OWORD *)((char *)pv + v74) = *(_OWORD *)&v73->vt;
        *(_OWORD *)&v75[v74 + 16] = (unsigned __int64)v73->pRecInfo;
        v124 = ++v28;
      }
    }
    v30 = *((_QWORD *)this + 25);
    if ( !v30 )
    {
      Value = TlsGetValue(g_luTls);
      if ( Value )
        v30 = Value[5];
      else
        v30 = 0;
    }
    v154 = v30;
    v153 = *(_QWORD *)(v30 + 56);
    *(_QWORD *)(v30 + 56) = &v153;
    v156 = v28;
    v20 = 0;
    v137 = 0;
    v32 = 0;
    v19 = 16396;
    v21 = 24588;
    v22 = 24576;
    while ( 1 )
    {
      v145 = v32;
      if ( v32 >= v156 )
      {
        v10 = pvarg;
        v8 = v132;
        goto LABEL_38;
      }
      v33 = (char *)pv + 32 * v32;
      v133 = 0;
      v134 = 0;
      if ( *(_WORD *)v33 == 16396 )
      {
        v34 = (__int16 *)*((_QWORD *)v33 + 1);
        v35 = *v34;
        if ( *v34 == 8 )
        {
          if ( !*((_QWORD *)v34 + 1) )
            goto LABEL_36;
          LODWORD(v133) = 0;
          v36 = *((_QWORD *)v34 + 1);
          *((_QWORD *)&v133 + 1) = v36;
          v37 = 0;
          goto LABEL_26;
        }
        if ( v35 == 9 || v35 == 13 )
        {
          if ( *((_QWORD *)v34 + 1) )
          {
            LODWORD(v133) = 2;
            v36 = *((_QWORD *)v34 + 1);
            *((_QWORD *)&v133 + 1) = v36;
            v37 = 2;
            goto LABEL_26;
          }
        }
        else if ( v35 == 24588 )
        {
          v84 = (_QWORD *)*((_QWORD *)v34 + 1);
          if ( v84 && *v84 )
          {
            LODWORD(v133) = 1;
            v36 = **((_QWORD **)v34 + 1);
            *((_QWORD *)&v133 + 1) = v36;
            if ( v36 )
              goto LABEL_195;
            goto LABEL_196;
          }
        }
        else if ( (v35 & 0x6000) == 0x2000 && *((_QWORD *)v34 + 1) )
        {
          LODWORD(v133) = 1;
          v36 = *((_QWORD *)v34 + 1);
          *((_QWORD *)&v133 + 1) = v36;
          if ( v36 )
            goto LABEL_195;
          goto LABEL_196;
        }
      }
      else if ( *(_WORD *)v33 == 24588 )
      {
        v85 = (_QWORD *)*((_QWORD *)v33 + 1);
        if ( v85 )
        {
          if ( *v85 )
          {
            LODWORD(v133) = 1;
            v36 = **((_QWORD **)v33 + 1);
            *((_QWORD *)&v133 + 1) = v36;
            if ( v36 )
LABEL_195:
              *(_QWORD *)&v134 = *(_QWORD *)(v36 + 16);
LABEL_196:
            v37 = 1;
LABEL_26:
            v38 = *((_QWORD *)v33 + 3);
            if ( v38 )
            {
              v76 = *(_DWORD *)(v38 + 8);
              if ( v76 == v37 )
              {
                if ( !v76 )
                  goto LABEL_139;
                v77 = v76 - 1;
                if ( v77 )
                {
                  if ( v77 == 1 )
                  {
LABEL_139:
                    v78 = *(_QWORD *)(v38 + 16) == v36;
                    goto LABEL_140;
                  }
LABEL_201:
                  v78 = 0;
                }
                else
                {
                  v86 = *(_QWORD *)(v38 + 16);
                  if ( v86 != v36 || v86 && *(_QWORD *)(v38 + 24) != (_QWORD)v134 )
                    goto LABEL_201;
                  v78 = 1;
                }
LABEL_140:
                if ( v78 )
                {
LABEL_35:
                  v19 = 16396;
                  v21 = 24588;
                  goto LABEL_36;
                }
              }
            }
            v39 = (char *)CoTaskMemAlloc(0x28u);
            v40 = v39;
            if ( !v39 )
            {
              v20 = -2147024882;
              goto LABEL_33;
            }
            *(_OWORD *)(v39 + 8) = v133;
            *(_OWORD *)(v39 + 24) = v134;
            v41 = AutoVariantRef::PinnableData::Pin((AutoVariantRef::PinnableData *)(v39 + 8));
            if ( v41 < 0 )
            {
              CoTaskMemFree(v40);
            }
            else
            {
              *v40 = *((_QWORD *)v33 + 3);
              *((_QWORD *)v33 + 3) = v40;
            }
            if ( v41 < 0 )
            {
              v20 = v41;
LABEL_33:
              v137 = v20;
            }
            v22 = 24576;
            goto LABEL_35;
          }
        }
      }
LABEL_36:
      ++v32;
    }
  }
LABEL_40:
  if ( v10 )
    v10->vt = 0;
  memset(&v150, 0, sizeof(v150));
  ((void (__fastcall *)(struct IDispatch *, __int64, __int64, __int64))v8->lpVtbl->AddRef)(v8, v19, v21, v22);
  if ( v8->lpVtbl >= ImageEnd || v8->lpVtbl < (struct IDispatchVtbl *)&_ImageBase )
  {
    ++*(_DWORD *)this;
    v125 = 1;
  }
  if ( *(_DWORD *)this == -1 )
    VBScriptClass_Report_Unexpected_Fatal_Error(this);
  v42 = TlsGetValue(g_luTls);
  v142 = v42;
  if ( v42 )
  {
    v143 = v42[6];
    v42[6] = this;
  }
  ppDataToRelease[0] = 0;
  v43 = 0;
  while ( 1 )
  {
    v146 = v43;
    if ( v43 >= v11 )
      break;
    if ( *((_WORD *)v126 + 12 * v43) == 16396 && (v79 = *((_QWORD *)v126 + 3 * v43 + 1)) != 0 )
    {
      if ( *(_WORD *)v79 == 9 || *(_WORD *)v79 == 13 )
      {
        v87 = *(_QWORD *)(v79 + 8);
        if ( v87 )
        {
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v87 + 8LL))(*(_QWORD *)(v79 + 8));
          v88 = v115;
          *((_QWORD *)Block + v115) = v87;
          v115 = v88 + 1;
        }
      }
      else if ( *(_WORD *)v79 == 0x2000 || *(_WORD *)v79 == 8204 )
      {
        v81 = *(SAFEARRAY **)(v79 + 8);
        if ( v81 )
        {
          SafeArrayAddRef(v81, ppDataToRelease);
          v82 = v122;
          *((_QWORD *)v141 + v122) = v81;
          v122 = v82 + 1;
          if ( ppDataToRelease[0] )
            *((PVOID *)v119 + (int)v113++) = ppDataToRelease[0];
        }
      }
      ++v43;
    }
    else
    {
      ++v43;
    }
  }
  if ( ((__int64 (__fastcall *)(struct IDispatch *, GUID *, struct IDispatch **))v8->lpVtbl->QueryInterface)(
         v8,
         &IID_IDispatchEx,
         &v139) >= 0 )
  {
    v46 = *((_QWORD *)this + 20);
    if ( v46 )
    {
      v50 = *(CSession **)(*(_QWORD *)(v46 + 32) + 72LL);
      *(_QWORD *)(v46 + 56) = v50;
    }
    else
    {
      v47 = 0;
      v48 = *((_QWORD *)this + 21);
      v49 = (CSession *)operator new(0x58u);
      v50 = v49;
      if ( v49 )
      {
        *(_QWORD *)v49 = &DexCaller::`vftable'{for `IServiceProvider'};
        *((_QWORD *)v49 + 1) = &DexCaller::`vftable'{for `ICanHandleException'};
        *((_QWORD *)v49 + 2) = &DexCaller::`vftable'{for `IProvideRuntimeContext'};
        *((_DWORD *)v49 + 6) = 1;
        *((_QWORD *)v49 + 4) = 0;
        *((_QWORD *)v49 + 5) = 0;
        *((_QWORD *)v49 + 6) = 0;
        *((_DWORD *)v49 + 16) &= ~1u;
        *((_DWORD *)v49 + 16) &= ~2u;
        *((_QWORD *)v49 + 9) = 0;
        *((_QWORD *)v49 + 10) = 0;
      }
      else
      {
        v50 = 0;
      }
      *((_QWORD *)this + 20) = v50;
      if ( !v50 )
      {
        v20 = -2147024882;
        goto LABEL_73;
      }
      *((_QWORD *)v50 + 4) = this;
      _InterlockedIncrement((volatile signed __int32 *)this + 2);
      *(_QWORD *)(*((_QWORD *)this + 20) + 56LL) = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 20) + 32LL) + 72LL);
      if ( v48 )
      {
        *(_QWORD *)(*((_QWORD *)this + 20) + 40LL) = v48;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 8LL))(v48);
      }
      v51 = *((_QWORD *)this + 4);
      if ( !v51
        || *((_QWORD *)this + 20) == -48
        || (*(_QWORD *)(*((_QWORD *)this + 20) + 48LL) = 0,
            (v52 = *(int (__fastcall ****)(_QWORD, GUID *))(v51 + 160)) != 0)
        && (**v52)(v52, &IID_IUnknown) < 0 )
      {
        *(_QWORD *)(*((_QWORD *)this + 20) + 48LL) = 0;
      }
      v50 = (CSession *)*((_QWORD *)this + 21);
      if ( v50 )
      {
        (*(void (__fastcall **)(CSession *))(*(_QWORD *)v50 + 16LL))(v50);
        *((_QWORD *)this + 21) = 0;
      }
    }
    v47 = (struct IServiceProvider *)*((_QWORD *)this + 20);
    v20 = 0;
LABEL_73:
    *((_QWORD *)this + 20) = 0;
    v114 = v20;
    if ( v20 >= 0 )
    {
      v57 = v139;
      v58 = 0;
      v118 = 0;
      v59 = *((_QWORD *)this + 4);
      if ( v59 )
      {
        if ( *(_QWORD *)(v59 + 904) )
        {
          v58 = CSession::IsResponseDotWrite(v50, v139, v116);
          v118 = v58;
          if ( !v58 )
            CSession::SendRuntimeScriptInfoToHost(this, SCRIPTTRACEINFO_COMCALLSTART);
        }
      }
      v20 = IDispatchExInvokeEx2(this, (struct IDispatchEx *)v57, v116, 0x409u, v17, &v135, v10, &v150, v47);
      if ( !v58 )
      {
        v60 = *((_QWORD *)this + 4);
        if ( v60 )
        {
          v61 = *(_QWORD *)(v60 + 904);
          if ( v61 )
          {
            v129 = 0;
            v116 = 0;
            v128 = 0;
            v89 = *((_QWORD *)this + 9);
            if ( v89 )
            {
              v129 = 0;
              v116 = 0;
              v128 = 0;
              if ( *(_QWORD *)(v89 + 464) )
              {
                v90 = *(FncInfo **)(v89 + 40);
                if ( v90 )
                {
                  v91 = *(_QWORD *)v90;
                  if ( *(_QWORD *)v90 )
                  {
                    v92 = *(int **)(v91 + 64);
                    v93 = (int *)(*v92 + *(_QWORD *)(v91 + 72));
                    if ( v93 && v92[1] == 32 )
                    {
                      v138 = 0;
                      FncInfo::GetBos(v90, *(_DWORD *)(v89 + 488), (struct BOS *)&v138);
                      v116 = v138;
                      v128 = v138 + HIDWORD(v138);
                      v129 = *v93;
                    }
                    v10 = pvarg;
                  }
                }
              }
            }
            v94 = *(void (__fastcall **)(__int64, __int64, __int128 *))(*(_QWORD *)v61 + 24LL);
            v151 = *(_OWORD *)(v60 + 912);
            v94(v61, 3, &v151);
          }
        }
      }
      v114 = v20;
      v62 = (DexCaller *)*((_QWORD *)this + 20);
      if ( v62 )
      {
        DexCaller::Release(v62);
        *((_QWORD *)this + 20) = 0;
      }
      v63 = *((_QWORD *)this + 21);
      if ( v63 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
        *((_QWORD *)this + 21) = 0;
      }
      *((_QWORD *)this + 20) = v47;
    }
    v56 = v20;
    ((void (__fastcall *)(struct IDispatch *))v139->lpVtbl->Release)(v139);
    goto LABEL_85;
  }
  LODWORD(v126) = 0;
  v53 = 0;
  v117 = 0;
  if ( this )
  {
    v72 = *((_QWORD *)this + 4);
    if ( v72 )
    {
      if ( *(_QWORD *)(v72 + 904) )
      {
        v53 = CSession::IsResponseDotWrite(v44, v8, v116);
        v117 = v53;
        if ( !v53 )
          CSession::SendRuntimeScriptInfoToHost(this, SCRIPTTRACEINFO_COMCALLSTART);
      }
    }
  }
  v20 = IDispatchInvoke2(this, v8, v116, v45, 0x409u, v17, &v135, v10, &v150, (unsigned int *)&v126);
  if ( this )
  {
    if ( !v53 )
    {
      v54 = *((_QWORD *)this + 4);
      if ( v54 )
      {
        v55 = *(_QWORD *)(v54 + 904);
        if ( v55 )
        {
          v95 = 0;
          v123 = 0;
          v96 = 0;
          v130 = 0;
          v97 = 0;
          v131 = 0;
          v98 = *((_QWORD *)this + 9);
          if ( v98 )
          {
            v123 = 0;
            v130 = 0;
            v131 = 0;
            if ( *(_QWORD *)(v98 + 464) )
            {
              v99 = *(FncInfo **)(v98 + 40);
              if ( v99 )
              {
                v100 = *(_QWORD *)v99;
                if ( *(_QWORD *)v99 )
                {
                  v101 = *(int **)(v100 + 64);
                  v102 = (int *)(*v101 + *(_QWORD *)(v100 + 72));
                  if ( v102 && v101[1] == 32 )
                  {
                    v140 = 0;
                    FncInfo::GetBos(v99, *(_DWORD *)(v98 + 488), (struct BOS *)&v140);
                    v96 = v140;
                    v130 = v140;
                    v97 = v140 + HIDWORD(v140);
                    v131 = v140 + HIDWORD(v140);
                    v95 = (unsigned int)*v102;
                    v123 = *v102;
                  }
                  v10 = pvarg;
                }
              }
            }
          }
          v103 = *(void (__fastcall **)(__int64, __int64, __int128 *, __int64, int, int, _QWORD))(*(_QWORD *)v55 + 24LL);
          v152 = *(_OWORD *)(v54 + 912);
          v103(v55, 3, &v152, v95, v96, v97, 0);
        }
      }
    }
  }
  v114 = v20;
  v56 = v20;
LABEL_85:
  ((void (__fastcall *)(struct IDispatch *))v132->lpVtbl->Release)(v132);
  if ( v56 < 0 )
  {
    if ( v10 )
      VAR::Clear((VAR *)v10);
    if ( v56 != -2147352567 )
      goto LABEL_104;
    CSession::RecordExcepInfoAndClear(this, &v150, &v114);
    v20 = v114;
    goto LABEL_156;
  }
  if ( v10 )
  {
    vt = v10->vt;
    if ( (vt & 0x4000) == 0 )
    {
      switch ( vt )
      {
        case 9:
          llVal = (int (__fastcall ***)(_QWORD, GUID *, VARIANTARG **))v10->llVal;
          if ( llVal )
          {
            pvarg = 0;
            if ( (**llVal)(llVal, &IID_IDispatchEx, &pvarg) >= 0 )
            {
              (*(void (__fastcall **)(LONGLONG))(*v10->pllVal + 16))(v10->llVal);
              v10->llVal = (LONGLONG)pvarg;
            }
          }
          v66 = TlsGetValue(g_luTls);
          if ( v66 )
            v67 = v66[4];
          else
            v67 = 0;
          if ( !v67 )
          {
            VAR::Clear((VAR *)v10);
            v20 = -2147024882;
            goto LABEL_102;
          }
          v68 = *(GcBlockFactory **)(v67 + 16);
          if ( v68 == *(GcBlockFactory **)(v67 + 8) )
          {
            v83 = *(struct GcBlock **)v67;
            if ( *(_QWORD *)v67 )
            {
              *(_QWORD *)v67 = *((_QWORD *)v83 + 150);
            }
            else
            {
              v83 = GcBlockFactory::PblkAlloc(v68);
              if ( !v83 )
              {
                v70 = 0;
                goto LABEL_99;
              }
            }
            v68 = (struct GcBlock *)((char *)v83 + 1200);
            *((_QWORD *)v83 + 150) = *(_QWORD *)(v67 + 8);
            *(_QWORD *)(v67 + 8) = v83;
            *(_QWORD *)(v67 + 16) = (char *)v83 + 1200;
          }
          ++*(_DWORD *)(v67 + 24);
          v69 = (_WORD *)((char *)v68 - 24);
          *(_QWORD *)(v67 + 16) = v69;
          *v69 = 0;
          if ( *(_DWORD *)(v67 + 24) == 1 )
            _InterlockedIncrement(&g_cLibRef);
          v70 = *(_QWORD *)(v67 + 16);
LABEL_99:
          if ( v70 )
          {
            *(_OWORD *)v70 = *(_OWORD *)&v10->vt;
            *(_QWORD *)(v70 + 16) = v10->pRecInfo;
            v10->vt = 74;
            v10->llVal = v70;
            v20 = 0;
          }
          else
          {
            VAR::Clear((VAR *)v10);
            v20 = -2147024882;
          }
          if ( v20 < 0 )
            goto LABEL_102;
LABEL_114:
          v20 = 0;
          goto LABEL_102;
        case 13:
          v80 = (int (__fastcall ***)(_QWORD, GUID *, struct IDispatch **))v10->llVal;
          if ( v80 )
          {
            v132 = 0;
            if ( (**v80)(v80, &IID_IDispatch, &v132) >= 0 )
            {
              (*(void (__fastcall **)(LONGLONG))(*v10->pllVal + 16))(v10->llVal);
              v10->vt = 9;
              v10->llVal = (LONGLONG)v132;
            }
          }
          v20 = VAR::MoveToHeap((VAR *)v10);
          if ( v20 >= 0 )
            v20 = 0;
          goto LABEL_102;
        case 20:
          v71 = v10->llVal;
          if ( v71 < (__int64)0xFFFFFFFF80000000uLL || v71 > 0x7FFFFFFF )
            goto LABEL_108;
          v10->vt = 3;
          LOWORD(vt) = 3;
          break;
        case 21:
          v71 = v10->llVal;
          if ( (unsigned __int64)v71 > 0xFFFFFFFF )
            goto LABEL_108;
          LOWORD(vt) = 19;
          v10->vt = 19;
          break;
        default:
          goto LABEL_108;
      }
      v10->lVal = v71;
LABEL_108:
      if ( (unsigned __int16)vt >= 0x49u && (unsigned __int16)vt < 0x51u )
      {
        VariantClear(v10);
        v20 = -2147467259;
        goto LABEL_102;
      }
      if ( (unsigned __int16)vt == 14 )
        goto LABEL_114;
      switch ( (__int16)vt )
      {
        case 0:
        case 1:
        case 2:
        case 3:
        case 4:
        case 5:
        case 6:
        case 7:
        case 10:
        case 11:
        case 16:
        case 17:
        case 18:
        case 19:
        case 22:
        case 23:
          goto LABEL_114;
        default:
          if ( (vt & 0x4000) != 0 )
            goto LABEL_114;
          v20 = VAR::MoveToHeap((VAR *)v10);
          if ( v20 >= 0 )
            v20 = 0;
          break;
      }
LABEL_102:
      v114 = v20;
      if ( v20 >= 0 )
        goto LABEL_103;
LABEL_104:
      v13 = v119;
      v15 = v115;
      v16 = v113;
      v14 = 0;
      goto LABEL_237;
    }
    VAR::Clear((VAR *)v10);
    v20 = -2146828275;
    v114 = -2146828275;
    goto LABEL_156;
  }
LABEL_103:
  v14 = 0;
  v20 = 0;
  v114 = 0;
  v13 = v119;
  v15 = v115;
  v16 = v113;
LABEL_237:
  v104 = v14;
  v105 = (_QWORD **)Block;
  if ( v15 > 0 )
  {
    v112 = v115;
    do
    {
      (*(void (__fastcall **)(_QWORD *, __int64))(*v105[v104] + 16LL))(v105[v104], v16);
      ++v104;
    }
    while ( v104 < v112 );
    v13 = v119;
    LODWORD(v16) = v113;
    v14 = 0;
  }
  v106 = v14;
  v107 = v122;
  v108 = (SAFEARRAY **)v141;
  if ( v122 > 0 )
  {
    do
      SafeArrayReleaseDescriptor(v108[v106++]);
    while ( v106 < v107 );
    v13 = v119;
    LODWORD(v16) = v113;
    v14 = 0;
  }
  v109 = v14;
  if ( (int)v16 > 0 )
  {
    do
    {
      SafeArrayReleaseData(*((PVOID *)v13 + v109++));
      v13 = v119;
    }
    while ( (int)v109 < (int)v113 );
  }
  free(v105);
  free(v108);
  free(v119);
  if ( v125 )
  {
    if ( !*(_DWORD *)this )
      VBScriptClass_Report_Unexpected_Fatal_Error(this);
    if ( v142 )
      v142[6] = v143;
    CSession::ClearVBSClassQueueAtCurrentDepth(this);
    --*(_DWORD *)this;
  }
  if ( v154 )
    *(_QWORD *)(v154 + 56) = **(_QWORD **)(v154 + 56);
  if ( v156 )
  {
    for ( k = 0; k < v156; ++k )
      AutoVariantRef::~AutoVariantRef((VARIANTARG *)((char *)pv + 32 * k));
    if ( pv && pv != v157 )
      CoTaskMemFree(pv);
    v156 = 0;
  }
  if ( v144 )
    free(v144);
  AutoCalloutParameterLock::~AutoCalloutParameterLock((AutoCalloutParameterLock *)&v153);
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x180006550  push    rbx
0x180006552  push    rsi
0x180006553  push    rdi
0x180006554  push    r12
0x180006556  push    r13
0x180006558  push    r14
0x18000655a  push    r15
0x18000655c  sub     rsp, 3E0h
0x180006563  mov     rax, cs:__security_cookie
0x18000656a  xor     rax, rsp
0x18000656d  mov     [rsp+418h+var_48], rax
0x180006575  mov     esi, r9d
0x180006578  mov     [rsp+418h+var_3BC], r8d
0x18000657d  mov     r15, rdx
0x180006580  mov     [rsp+418h+var_368], rdx
0x180006588  mov     rbx, rcx
0x18000658b  mov     [rsp+418h+var_2C0], rcx
0x180006593  mov     r12, [rsp+418h+arg_20]
0x18000659b  mov     [rsp+418h+pvarg], r12
0x1800065a0  movsxd  r14, [rsp+418h+arg_28]
0x1800065a8  mov     [rsp+418h+var_398], r14d
0x1800065b0  mov     rax, [rsp+418h+arg_30]
0x1800065b8  mov     [rsp+418h+var_388], rax
0x1800065c0  xorps   xmm0, xmm0
0x1800065c3  xor     eax, eax
0x1800065c5  movups  xmmword ptr [rsp+418h+var_340.rgvarg], xmm0
0x1800065cd  mov     qword ptr [rsp+418h+var_340.cArgs], rax
0x1800065d5  xorps   xmm1, xmm1
0x1800065d8  movups  xmmword ptr [rsp+418h+var_2B8.wCode], xmm1
0x1800065e0  movups  xmmword ptr [rsp+418h+var_2B8.bstrDescription], xmm1
0x1800065e8  movups  xmmword ptr [rsp+418h+var_2B8.dwHelpContext], xmm1
0x1800065f0  movups  xmmword ptr [rsp+418h+var_2B8.pfnDeferredFillIn], xmm1
0x1800065f8  mov     [rsp+418h+var_318], rax
0x180006600  mov     [rsp+418h+var_2F0], rax
0x180006608  lea     rcx, [rsp+418h+var_258]; this
0x180006610  call    ??0AutoCalloutParameterLock@@QEAA@XZ; AutoCalloutParameterLock::AutoCalloutParameterLock(void)
0x180006615  mov     edx, 8; Size
0x18000661a  mov     rcx, r14; Count
0x18000661d  call    cs:__imp_calloc
0x180006623  mov     [rsp+418h+Block], rax
0x18000662b  mov     edx, 8; Size
0x180006630  mov     rcx, r14; Count
0x180006633  call    cs:__imp_calloc
0x180006639  mov     r13, rax
0x18000663c  mov     [rsp+418h+var_308], rax
0x180006644  mov     edx, 8; Size
0x180006649  mov     rcx, r14; Count
0x18000664c  call    cs:__imp_calloc
0x180006652  mov     [rsp+418h+var_3B0], rax
0x180006657  cmp     [rsp+418h+Block], 0
0x180006660  jz      loc_180007871
0x180006666  mov     [rsp+418h+var_2C8], r13
0x18000666e  test    r13, r13
0x180006671  jz      loc_180007871
0x180006677  mov     [rsp+418h+var_2D8], rax
0x18000667f  test    rax, rax
0x180006682  jz      loc_180007871
0x180006688  xor     r8d, r8d
0x18000668b  mov     [rsp+418h+var_300], r8
0x180006693  mov     ecx, r8d
0x180006696  mov     [rsp+418h+var_3C0], ecx
0x18000669a  mov     [rsp+418h+var_39C], r8d
0x18000669f  mov     edx, r8d
0x1800066a2  mov     [rsp+418h+var_3C8], edx
0x1800066a6  mov     [rsp+418h+var_390], r8d
0x1800066ae  mov     [rsp+418h+var_2F8], r8
0x1800066b6  mov     r13d, esi
0x1800066b9  and     r13d, 0Fh
0x1800066bd  mov     [rsp+418h+var_2E0], r13d
0x1800066c5  test    r15, r15
0x1800066c8  jz      loc_18000727D
0x1800066ce  test    r13b, 0Ch
0x1800066d2  jnz     loc_180007291
0x1800066d8  mov     [rsp+418h+var_340.rgdispidNamedArgs], r8
0x1800066e0  mov     [rsp+418h+var_340.cNamedArgs], r8d
0x1800066e8  mov     rcx, [rsp+418h+var_388]
0x1800066f0  mov     [rsp+418h+var_340.cArgs], r14d
0x1800066f8  mov     [rsp+418h+var_340.rgvarg], rcx
0x180006700  lea     rax, [rsp+418h+var_2F0]
0x180006708  mov     [rsp+418h+var_3F0], rax
0x18000670d  lea     r9, [rsp+418h+var_138]
0x180006715  lea     r8, [rsp+418h+var_340]
0x18000671d  mov     rdx, r15
0x180006720  mov     ecx, r13d
0x180006723  call    MungeArgs
0x180006728  mov     edi, eax
0x18000672a  mov     [rsp+418h+var_3C4], eax
0x18000672e  test    eax, eax
0x180006730  js      loc_180007102
0x180006736  mov     rax, [rbx+20h]
0x18000673a  test    rax, rax
0x18000673d  jz      short loc_18000674C
0x18000673f  cmp     dword ptr [rax+104h], 0
0x180006746  jnz     loc_1800072FD
0x18000674c  mov     rax, [r15]
0x18000674f  lea     rcx, __ImageBase
0x180006756  cmp     rax, cs:?ImageEnd@@3PEBXEB; void const * const ImageEnd
0x18000675d  jb      loc_180006F4D
0x180006763  mov     edi, [rsp+418h+var_340.cArgs]
0x18000676a  mov     r14, [rsp+418h+var_340.rgvarg]
0x180006772  mov     [rsp+418h+var_3A0], 0
0x18000677a  xor     r8d, r8d
0x18000677d  mov     [rsp+418h+var_394], r8d
0x180006785  xor     edx, edx
0x180006787  mov     r9d, 4000h
0x18000678d  mov     [rsp+418h+var_3A0], edx
0x180006791  cmp     edx, edi
0x180006793  jb      loc_180006FAB
0x180006799  cmp     r8d, 8
0x18000679d  ja      loc_18000705E
0x1800067a3  lea     rax, [rsp+418h+var_238]
0x1800067ab  mov     [rsp+418h+pv], rax
0x1800067b3  xor     esi, esi
0x1800067b5  mov     [rsp+418h+var_394], esi
0x1800067bc  xor     edx, edx
0x1800067be  mov     [rsp+418h+var_3A0], edx
0x1800067c2  cmp     edx, edi
0x1800067c4  jb      loc_180006F60
0x1800067ca  mov     rcx, [rbx+0C8h]
0x1800067d1  test    rcx, rcx
0x1800067d4  jnz     short loc_1800067EF
0x1800067d6  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x1800067dc  call    cs:__imp_TlsGetValue
0x1800067e2  test    rax, rax
0x1800067e5  jz      loc_180006FCA
0x1800067eb  mov     rcx, [rax+28h]
0x1800067ef  mov     [rsp+418h+var_250], rcx
0x1800067f7  mov     rax, [rcx+38h]
0x1800067fb  mov     [rsp+418h+var_258], rax
0x180006803  lea     rax, [rsp+418h+var_258]
0x18000680b  mov     [rcx+38h], rax
0x18000680f  mov     [rsp+418h+var_240], esi
0x180006816  xor     edi, edi
0x180006818  mov     [rsp+418h+var_324], edi
0x18000681f  xor     esi, esi
0x180006821  mov     edx, 400Ch
0x180006826  mov     r8d, 600Ch
0x18000682c  mov     r9d, 6000h
0x180006832  mov     r10d, 2000h
0x180006838  mov     [rsp+418h+var_2E8], esi
0x18000683f  cmp     esi, [rsp+418h+var_240]
0x180006846  jnb     loc_18000693D
0x18000684c  mov     r15d, esi
0x18000684f  shl     r15, 5
0x180006853  mov     rax, [rsp+418h+pv]
0x18000685b  add     r15, rax
0x18000685e  xorps   xmm0, xmm0
0x180006861  movups  [rsp+418h+var_360], xmm0
0x180006869  movups  [rsp+418h+var_350], xmm0
0x180006871  movzx   eax, word ptr [r15]
0x180006875  cmp     ax, dx
0x180006878  jnz     loc_18000736A
0x18000687e  mov     rax, [r15+8]
0x180006882  movzx   ecx, word ptr [rax]
0x180006885  cmp     cx, 8
0x180006889  jnz     loc_180007220
0x18000688f  cmp     qword ptr [rax+8], 0
0x180006894  jz      loc_180006936
0x18000689a  mov     dword ptr [rsp+418h+var_360], 0
0x1800068a5  mov     rdx, [rax+8]
0x1800068a9  mov     qword ptr [rsp+418h+var_360+8], rdx
0x1800068b1  xor     eax, eax
0x1800068b3  mov     rcx, [r15+18h]
0x1800068b7  test    rcx, rcx
0x1800068ba  jnz     loc_180007009
0x1800068c0  mov     ecx, 28h ; '('; cb
0x1800068c5  call    cs:__imp_CoTaskMemAlloc
0x1800068cb  mov     r14, rax
0x1800068ce  test    rax, rax
0x1800068d1  jnz     short loc_1800068DA
0x1800068d3  mov     edi, 8007000Eh
0x1800068d8  jmp     short loc_180006918
0x1800068da  lea     rcx, [rax+8]; this
0x1800068de  movups  xmm0, [rsp+418h+var_360]
0x1800068e6  movups  xmmword ptr [rcx], xmm0
0x1800068e9  movups  xmm1, [rsp+418h+var_350]
0x1800068f1  movups  xmmword ptr [rcx+10h], xmm1
0x1800068f5  call    ?Pin@PinnableData@AutoVariantRef@@QEAAJXZ; AutoVariantRef::PinnableData::Pin(void)
0x1800068fa  mov     r12d, eax
0x1800068fd  test    eax, eax
0x1800068ff  js      loc_180007050
0x180006905  mov     rcx, [r15+18h]
0x180006909  mov     [r14], rcx
0x18000690c  mov     [r15+18h], r14
0x180006910  test    r12d, r12d
0x180006913  jns     short loc_18000691F
0x180006915  mov     edi, r12d
0x180006918  mov     [rsp+418h+var_324], edi
0x18000691f  mov     r10d, 2000h
0x180006925  mov     r9d, 6000h
0x18000692b  mov     edx, 400Ch
0x180006930  mov     r8d, 600Ch
0x180006936  inc     esi
0x180006938  jmp     loc_180006838
0x18000693d  mov     r12, [rsp+418h+pvarg]
0x180006942  mov     r15, [rsp+418h+var_368]
0x18000694a  mov     r14d, [rsp+418h+var_398]
0x180006952  mov     esi, 400Ch
0x180006957  mov     [rsp+418h+var_3C4], edi
0x18000695b  test    edi, edi
0x18000695d  js      loc_180007102
0x180006963  lea     rdi, __ImageBase
0x18000696a  test    r12, r12
0x18000696d  jz      short loc_180006976
0x18000696f  xor     eax, eax
0x180006971  mov     [r12], ax
0x180006976  xorps   xmm0, xmm0
0x180006979  movups  xmmword ptr [rsp+418h+var_2B8.wCode], xmm0
0x180006981  movups  xmmword ptr [rsp+418h+var_2B8.bstrDescription], xmm0
0x180006989  movups  xmmword ptr [rsp+418h+var_2B8.dwHelpContext], xmm0
0x180006991  movups  xmmword ptr [rsp+418h+var_2B8.pfnDeferredFillIn], xmm0
0x180006999  mov     rax, [r15]
0x18000699c  mov     rcx, r15
0x18000699f  mov     rax, [rax+8]
0x1800069a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069a8  mov     rax, [r15]
0x1800069ab  cmp     rax, cs:?ImageEnd@@3PEBXEB; void const * const ImageEnd
0x1800069b2  jb      loc_180006B71
0x1800069b8  inc     dword ptr [rbx]
0x1800069ba  mov     [rsp+418h+var_390], 1
0x1800069c5  mov     eax, 0FFFFFFFFh
0x1800069ca  cmp     [rbx], eax
0x1800069cc  jz      loc_180007043
0x1800069d2  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x1800069d8  call    cs:__imp_TlsGetValue
0x1800069de  mov     [rsp+418h+var_300], rax
0x1800069e6  test    rax, rax
0x1800069e9  jz      short loc_1800069FB
0x1800069eb  mov     rcx, [rax+30h]
0x1800069ef  mov     [rsp+418h+var_2F8], rcx
0x1800069f7  mov     [rax+30h], rbx
0x1800069fb  mov     [rsp+418h+ppDataToRelease], 0
0x180006a07  xor     edi, edi
0x180006a09  mov     [rsp+418h+var_2E4], edi
0x180006a10  cmp     edi, r14d
0x180006a13  jl      loc_180006EE5
0x180006a19  mov     rax, [r15]
0x180006a1c  lea     r8, [rsp+418h+var_318]
0x180006a24  lea     rdx, IID_IDispatchEx
0x180006a2b  mov     rcx, r15
0x180006a2e  mov     rax, [rax]
0x180006a31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a36  test    eax, eax
0x180006a38  js      loc_180006B7F
0x180006a3e  mov     rdx, [rbx+0A0h]
0x180006a45  xor     esi, esi
0x180006a47  test    rdx, rdx
0x180006a4a  jnz     loc_180006C1B
0x180006a50  mov     r14d, esi
0x180006a53  mov     rdi, [rbx+0A8h]
0x180006a5a  mov     ecx, 58h ; 'X'; Size
0x180006a5f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006a64  mov     rcx, rax
0x180006a67  test    rax, rax
0x180006a6a  jz      loc_180007170
0x180006a70  lea     rax, ??_7DexCaller@@6BIServiceProvider@@@; const DexCaller::`vftable'{for `IServiceProvider'}
0x180006a77  mov     [rcx], rax
0x180006a7a  lea     rax, ??_7DexCaller@@6BICanHandleException@@@; const DexCaller::`vftable'{for `ICanHandleException'}
0x180006a81  mov     [rcx+8], rax
0x180006a85  lea     rax, ??_7DexCaller@@6BIProvideRuntimeContext@@@; const DexCaller::`vftable'{for `IProvideRuntimeContext'}
0x180006a8c  mov     [rcx+10h], rax
0x180006a90  mov     dword ptr [rcx+18h], 1
0x180006a97  mov     [rcx+20h], rsi
0x180006a9b  mov     [rcx+28h], rsi
0x180006a9f  mov     [rcx+30h], rsi
0x180006aa3  and     dword ptr [rcx+40h], 0FFFFFFFEh
0x180006aa7  mov     eax, [rcx+40h]
0x180006aaa  and     eax, 0FFFFFFFDh
0x180006aad  mov     [rcx+40h], eax
0x180006ab0  mov     [rcx+48h], rsi
0x180006ab4  mov     [rcx+50h], rsi
0x180006ab8  mov     [rbx+0A0h], rcx
0x180006abf  test    rcx, rcx
0x180006ac2  jz      loc_180006FF7
0x180006ac8  mov     [rcx+20h], rbx
0x180006acc  lock inc dword ptr [rbx+8]
0x180006ad0  mov     rdx, [rbx+0A0h]
0x180006ad7  mov     rax, [rdx+20h]
0x180006adb  mov     rcx, [rax+48h]
0x180006adf  mov     [rdx+38h], rcx
0x180006ae3  test    rdi, rdi
0x180006ae6  jz      short loc_180006B02
0x180006ae8  mov     rax, [rbx+0A0h]
0x180006aef  mov     [rax+28h], rdi
0x180006af3  mov     rax, [rdi]
0x180006af6  mov     rcx, rdi
0x180006af9  mov     rax, [rax+8]
0x180006afd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b02  mov     rcx, [rbx+20h]
0x180006b06  test    rcx, rcx
0x180006b09  jz      loc_180007426
0x180006b0f  mov     r8, [rbx+0A0h]
0x180006b16  add     r8, 30h ; '0'
0x180006b1a  jz      loc_180007426
0x180006b20  mov     [r8], rsi
0x180006b23  mov     rcx, [rcx+0A0h]
0x180006b2a  test    rcx, rcx
0x180006b2d  jz      short loc_180006B49
0x180006b2f  mov     rax, [rcx]
0x180006b32  lea     rdx, IID_IUnknown
  ... truncated ...
```
