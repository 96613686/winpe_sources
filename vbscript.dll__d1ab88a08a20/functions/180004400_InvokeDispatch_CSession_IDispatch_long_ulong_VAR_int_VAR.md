# InvokeDispatch(CSession *,IDispatch *,long,ulong,VAR *,int,VAR *)

- ea: `0x180004400`
- end: `0x1800059e4`
- name: `?InvokeDispatch@@YAJPEAVCSession@@PEAUIDispatch@@JKPEAVVAR@@H2@Z`
- size: `5604`
- prototype: `__int64 __fastcall(struct CSession *this, struct IDispatch *, int, char, VARIANTARG *pvarg, int, struct VAR *)`
- caller_count: `7`
- callee_count: `28`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180002db0`
- `0x1800040a0`
- `0x18001b5f0`
- `0x18001f0f0`
- `0x180042f8c`
- `0x18006d184`
- `0x18006ea20`

## callees

- `0x180002f40`
- `0x180002fc0`
- `0x180003f00`
- `0x180003fe0`
- `0x180004400`
- `0x180005a60`
- `0x180005ad0`
- `0x180005b90`
- `0x180005dd8`
- `0x180005e40`
- `0x180006d80`
- `0x18001b340`
- `0x18001b5d0`
- `0x18001c358`
- `0x18001c8ac`
- `0x18001c9d0`
- `0x18001e32c`
- `0x18001ed10`
- `0x180025cf0`
- `0x180036970`
- `0x180038678`
- `0x180046884`
- `0x1800682b8`
- `0x18006b41c`
- `0x180078100`
- `0x180079436`
- `0x180079490`
- `0x18007a010`

## import_xrefs

- `msvcrt!calloc` at `0x1800044c2`
- `msvcrt!calloc` at `0x1800044de`
- `msvcrt!calloc` at `0x1800044fd`
- `msvcrt!calloc` at `0x1800044c2`
- `msvcrt!calloc` at `0x1800044de`
- `msvcrt!calloc` at `0x1800044fd`
- `msvcrt!free` at `0x1800057df`
- `msvcrt!free` at `0x1800057ee`
- `msvcrt!free` at `0x1800057ff`
- `msvcrt!free` at `0x1800059b1`
- `msvcrt!free` at `0x180079661`
- `msvcrt!free` at `0x180079670`
- `msvcrt!free` at `0x18007967f`
- `msvcrt!free` at `0x1800796e2`
- `msvcrt!free` at `0x1800057df`
- `msvcrt!free` at `0x1800057ee`
- `msvcrt!free` at `0x1800057ff`
- `msvcrt!free` at `0x1800059b1`
- `msvcrt!free` at `0x180079661`
- `msvcrt!free` at `0x180079670`
- `msvcrt!free` at `0x18007967f`
- `msvcrt!free` at `0x1800796e2`
- `OLEAUT32!SafeArrayReleaseDescriptor` at `0x180005958`
- `OLEAUT32!SafeArrayReleaseDescriptor` at `0x180079620`
- `OLEAUT32!SafeArrayReleaseDescriptor` at `0x180005958`
- `OLEAUT32!SafeArrayReleaseDescriptor` at `0x180079620`
- `OLEAUT32!SafeArrayAddRef` at `0x18000511a`
- `OLEAUT32!SafeArrayAddRef` at `0x18000511a`
- `OLEAUT32!SafeArrayReleaseData` at `0x180005987`
- `OLEAUT32!SafeArrayReleaseData` at `0x18007964b`
- `OLEAUT32!SafeArrayReleaseData` at `0x180005987`
- `OLEAUT32!SafeArrayReleaseData` at `0x18007964b`
- `OLEAUT32!__imp_VariantClear` at `0x1800056fe`
- `OLEAUT32!__imp_VariantClear` at `0x1800056fe`
- `KERNEL32!TlsGetValue` at `0x180004698`
- `KERNEL32!TlsGetValue` at `0x1800048ad`
- `KERNEL32!TlsGetValue` at `0x180004c71`
- `KERNEL32!TlsGetValue` at `0x180004698`
- `KERNEL32!TlsGetValue` at `0x1800048ad`
- `KERNEL32!TlsGetValue` at `0x180004c71`
- `OLE32!CoTaskMemAlloc` at `0x180004794`
- `OLE32!CoTaskMemAlloc` at `0x180004f55`
- `OLE32!CoTaskMemAlloc` at `0x180004794`
- `OLE32!CoTaskMemAlloc` at `0x180004f55`
- `OLE32!CoTaskMemFree` at `0x180004f3d`
- `OLE32!CoTaskMemFree` at `0x180005914`
- `OLE32!CoTaskMemFree` at `0x180004f3d`
- `OLE32!CoTaskMemFree` at `0x180005914`

## pseudocode

```c
__int64 __fastcall InvokeDispatch(
        struct CSession *this,
        struct IDispatch *a2,
        int a3,
        char a4,
        VARIANTARG *pvarg,
        int a6,
        struct VAR *a7)
{
  struct IDispatch *v8; // r15
  int v10; // r12d
  void *v11; // r14
  void *v12; // rax
  int v13; // r10d
  int v14; // ecx
  __int64 v15; // rdx
  unsigned int v16; // r14d
  VARIANTARG *v17; // rcx
  __int64 v18; // rdx
  int v19; // edi
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // rax
  UINT cArgs; // edi
  VARIANTARG *rgvarg; // r14
  unsigned int v25; // r8d
  UINT i; // edx
  unsigned int v27; // esi
  UINT j; // edx
  __int64 v29; // rcx
  _QWORD *Value; // rax
  unsigned int v31; // esi
  char *v32; // r15
  __int16 *v33; // rax
  __int16 v34; // cx
  __int64 v35; // rdx
  int v36; // eax
  __int64 v37; // rcx
  char *v38; // rax
  _QWORD *v39; // r14
  int v40; // r12d
  _QWORD *v41; // rax
  int v42; // edi
  CSession *v43; // rcx
  const struct _GUID *v44; // r9
  __int64 v45; // rdx
  __int64 v46; // rdi
  _QWORD *v47; // rax
  _QWORD *v48; // rcx
  __int64 v49; // rcx
  int (__fastcall ***v50)(_QWORD, GUID *); // rcx
  CSession *v51; // rcx
  bool v52; // si
  __int64 v53; // r11
  __int64 v54; // rsi
  struct IServiceProvider *v55; // r15
  struct IDispatch *v56; // rdi
  bool v57; // si
  __int64 v58; // rax
  __int64 v59; // r11
  __int64 v60; // rsi
  DexCaller *v61; // rcx
  __int64 v62; // rcx
  int vt; // edx
  int (__fastcall ***v64)(_QWORD, GUID *, unsigned int **); // rcx
  _QWORD *v65; // rax
  __int64 v66; // rdi
  GcBlockFactory *v67; // rcx
  _WORD *v68; // rcx
  LONGLONG v69; // rax
  __int64 v70; // rax
  __int64 v71; // rax
  VARIANTARG *v72; // r8
  __int64 v73; // rcx
  char *v74; // rax
  unsigned __int64 ullVal; // rax
  int v76; // r8d
  int v77; // r8d
  bool v78; // al
  __int64 v79; // rdx
  SCODE scode; // edi
  int (__fastcall ***llVal)(_QWORD, GUID *, struct IDispatch **); // rcx
  struct RuntimeScriptException *v82; // rdi
  CScriptRuntime *v83; // rcx
  SAFEARRAY *v84; // rsi
  struct GcBlock *v85; // rdx
  _QWORD *v86; // rcx
  _QWORD *v87; // rax
  __int64 v88; // rax
  __int64 v89; // rsi
  __int64 v90; // r9
  int v91; // eax
  int v92; // edx
  __int64 v93; // r10
  FncInfo *v94; // r14
  __int64 v95; // rcx
  int *v96; // r12
  void (__fastcall *v97)(__int64, __int64, __int128 *, __int64, int, int, _QWORD); // r10
  __int64 v98; // r10
  FncInfo *v99; // r14
  __int64 v100; // rcx
  int *v101; // r15
  void (__fastcall *v102)(__int64, __int64, __int128 *); // r10
  int v103; // esi
  _QWORD **v104; // r13
  int v105; // esi
  SAFEARRAY **v106; // r15
  int v107; // esi
  unsigned int k; // ebx
  unsigned int v110; // [rsp+50h] [rbp-3B8h]
  int v111; // [rsp+54h] [rbp-3B4h]
  void *v113; // [rsp+60h] [rbp-3A8h]
  __int16 v114; // [rsp+68h] [rbp-3A0h]
  int v115; // [rsp+70h] [rbp-398h]
  struct IDispatch *v116; // [rsp+78h] [rbp-390h] BYREF
  unsigned int v117; // [rsp+80h] [rbp-388h]
  int v118; // [rsp+84h] [rbp-384h]
  VAR *v119; // [rsp+88h] [rbp-380h] BYREF
  void *Block; // [rsp+90h] [rbp-378h]
  int v121; // [rsp+98h] [rbp-370h]
  int v122; // [rsp+9Ch] [rbp-36Ch]
  int v123; // [rsp+A0h] [rbp-368h]
  unsigned int *v124; // [rsp+A8h] [rbp-360h] BYREF
  __int128 v125; // [rsp+B0h] [rbp-358h]
  __int128 v126; // [rsp+C0h] [rbp-348h]
  struct tagDISPPARAMS v127; // [rsp+D0h] [rbp-338h] BYREF
  int v128; // [rsp+E8h] [rbp-320h] BYREF
  int v129; // [rsp+ECh] [rbp-31Ch]
  int v130; // [rsp+F0h] [rbp-318h]
  int v131; // [rsp+F4h] [rbp-314h]
  __int64 v132; // [rsp+F8h] [rbp-310h] BYREF
  struct IDispatch *v133; // [rsp+100h] [rbp-308h] BYREF
  __int64 v134; // [rsp+108h] [rbp-300h] BYREF
  void *v135; // [rsp+110h] [rbp-2F8h]
  _QWORD *v136; // [rsp+118h] [rbp-2F0h]
  __int64 v137; // [rsp+120h] [rbp-2E8h]
  void *v138; // [rsp+128h] [rbp-2E0h]
  struct tagEXCEPINFO v139; // [rsp+130h] [rbp-2D8h] BYREF
  PVOID ppDataToRelease[4]; // [rsp+170h] [rbp-298h] BYREF
  __int128 v141; // [rsp+190h] [rbp-278h] BYREF
  __int128 v142; // [rsp+1A0h] [rbp-268h] BYREF
  __int64 v143; // [rsp+1B0h] [rbp-258h] BYREF
  __int64 v144; // [rsp+1B8h] [rbp-250h]
  LPVOID pv; // [rsp+1C0h] [rbp-248h]
  unsigned int v146; // [rsp+1C8h] [rbp-240h]
  _BYTE v147[256]; // [rsp+1D0h] [rbp-238h] BYREF
  char v148[240]; // [rsp+2D0h] [rbp-138h] BYREF

  v8 = a2;
  v116 = a2;
  ppDataToRelease[3] = this;
  v10 = a6;
  v119 = a7;
  memset(&v127, 0, sizeof(v127));
  memset(&v139, 0, sizeof(v139));
  v133 = 0;
  v138 = 0;
  AutoCalloutParameterLock::AutoCalloutParameterLock((AutoCalloutParameterLock *)&v143);
  Block = calloc(a6, 8u);
  v11 = calloc(a6, 8u);
  v135 = v11;
  v12 = calloc(a6, 8u);
  v113 = v12;
  if ( !Block || (ppDataToRelease[1] = v11) == 0 || (ppDataToRelease[2] = v12) == 0 )
  {
    AutoCalloutParameterLock::~AutoCalloutParameterLock((AutoCalloutParameterLock *)&v143);
    return 2147942414LL;
  }
  v13 = 0;
  v136 = 0;
  v14 = 0;
  v111 = 0;
  v115 = 0;
  v15 = 0;
  v110 = 0;
  v118 = 0;
  v137 = 0;
  v16 = a4 & 0xF;
  v114 = a4 & 0xF;
  if ( !v8 )
  {
    v19 = -2146827864;
    goto LABEL_243;
  }
  if ( (a4 & 0xC) != 0 )
  {
    v128 = -3;
    v127.rgdispidNamedArgs = &v128;
    v127.cNamedArgs = 1;
    v17 = (VARIANTARG *)v119;
    if ( (a4 & 8) != 0 && !(unsigned int)VAR::IsIDispatch(v119) )
    {
      if ( (a4 & 4) == 0 )
      {
        v19 = -2146827864;
        goto LABEL_154;
      }
      v16 = 4;
      v114 = 4;
    }
  }
  else
  {
    v127.rgdispidNamedArgs = 0;
    v127.cNamedArgs = 0;
    v17 = (VARIANTARG *)v119;
  }
  v127.cArgs = a6;
  v127.rgvarg = v17;
  v19 = MungeArgs(v16, v8, &v127, v148);
  if ( v19 < 0 )
  {
LABEL_153:
    v13 = 0;
LABEL_154:
    v12 = v113;
    v14 = v111;
    v15 = v110;
    goto LABEL_243;
  }
  v22 = *((_QWORD *)this + 4);
  if ( (!v22 || !*(_DWORD *)(v22 + 260)) && (v8->lpVtbl >= ImageEnd || v8->lpVtbl < (struct IDispatchVtbl *)&_ImageBase) )
  {
    cArgs = v127.cArgs;
    rgvarg = v127.rgvarg;
    v13 = 0;
    v25 = 0;
    v117 = 0;
    for ( i = 0; i < v127.cArgs; ++i )
    {
      if ( (v127.rgvarg[i].vt & 0x4000) != 0 )
        v117 = ++v25;
    }
    if ( v25 > 8 )
    {
      pv = CoTaskMemAlloc(32LL * v25);
      v13 = 0;
      if ( !pv )
      {
        v19 = -2147024882;
LABEL_38:
        if ( v19 < 0 )
          goto LABEL_154;
        LOWORD(v16) = v114;
        goto LABEL_40;
      }
    }
    else
    {
      pv = v147;
    }
    v27 = 0;
    v117 = 0;
    for ( j = 0; j < cArgs; ++j )
    {
      v72 = &rgvarg[j];
      if ( (v72->vt & 0x4000) != 0 )
      {
        v73 = 32LL * v27;
        v74 = (char *)pv;
        *(_OWORD *)((char *)pv + v73) = *(_OWORD *)&v72->vt;
        *(_OWORD *)&v74[v73 + 16] = (unsigned __int64)v72->pRecInfo;
        v117 = ++v27;
      }
    }
    v29 = *((_QWORD *)this + 25);
    if ( !v29 )
    {
      Value = TlsGetValue(g_luTls);
      v13 = 0;
      v29 = 0;
      if ( Value )
        v29 = Value[5];
    }
    v144 = v29;
    v143 = *(_QWORD *)(v29 + 56);
    *(_QWORD *)(v29 + 56) = &v143;
    v146 = v27;
    v19 = 0;
    v129 = 0;
    v31 = 0;
    v130 = 0;
    v18 = 16396;
    v20 = 24588;
    v21 = 24576;
    while ( 1 )
    {
      if ( v31 >= v146 )
      {
        v8 = v116;
        v10 = a6;
        goto LABEL_38;
      }
      v32 = (char *)pv + 32 * v31;
      v125 = 0;
      v126 = 0;
      if ( *(_WORD *)v32 == 16396 )
      {
        v33 = (__int16 *)*((_QWORD *)v32 + 1);
        v34 = *v33;
        if ( *v33 == 8 )
        {
          if ( !*((_QWORD *)v33 + 1) )
            goto LABEL_36;
          LODWORD(v125) = 0;
          v35 = *((_QWORD *)v33 + 1);
          *((_QWORD *)&v125 + 1) = v35;
          v36 = 0;
          goto LABEL_26;
        }
        if ( v34 == 9 || v34 == 13 )
        {
          if ( *((_QWORD *)v33 + 1) )
          {
            LODWORD(v125) = 2;
            v35 = *((_QWORD *)v33 + 1);
            *((_QWORD *)&v125 + 1) = v35;
            v36 = 2;
            goto LABEL_26;
          }
        }
        else if ( v34 == 24588 )
        {
          v86 = (_QWORD *)*((_QWORD *)v33 + 1);
          if ( v86 && *v86 )
          {
            LODWORD(v125) = 1;
            v35 = **((_QWORD **)v33 + 1);
            *((_QWORD *)&v125 + 1) = v35;
            if ( v35 )
              goto LABEL_196;
            goto LABEL_197;
          }
        }
        else if ( (v34 & 0x6000) == 0x2000 && *((_QWORD *)v33 + 1) )
        {
          LODWORD(v125) = 1;
          v35 = *((_QWORD *)v33 + 1);
          *((_QWORD *)&v125 + 1) = v35;
          if ( v35 )
            goto LABEL_196;
          goto LABEL_197;
        }
      }
      else if ( *(_WORD *)v32 == 24588 )
      {
        v87 = (_QWORD *)*((_QWORD *)v32 + 1);
        if ( v87 )
        {
          if ( *v87 )
          {
            LODWORD(v125) = 1;
            v35 = **((_QWORD **)v32 + 1);
            *((_QWORD *)&v125 + 1) = v35;
            if ( v35 )
LABEL_196:
              *(_QWORD *)&v126 = *(_QWORD *)(v35 + 16);
LABEL_197:
            v36 = 1;
LABEL_26:
            v37 = *((_QWORD *)v32 + 3);
            if ( v37 )
            {
              v76 = *(_DWORD *)(v37 + 8);
              if ( v76 == v36 )
              {
                if ( !v76 )
                  goto LABEL_135;
                v77 = v76 - 1;
                if ( v77 )
                {
                  if ( v77 == 1 )
                  {
LABEL_135:
                    v78 = *(_QWORD *)(v37 + 16) == v35;
                    goto LABEL_136;
                  }
LABEL_202:
                  v78 = 0;
                }
                else
                {
                  v88 = *(_QWORD *)(v37 + 16);
                  if ( v88 != v35 || v88 && *(_QWORD *)(v37 + 24) != (_QWORD)v126 )
                    goto LABEL_202;
                  v78 = 1;
                }
LABEL_136:
                if ( v78 )
                {
LABEL_35:
                  v18 = 16396;
                  v20 = 24588;
                  goto LABEL_36;
                }
              }
            }
            v38 = (char *)CoTaskMemAlloc(0x28u);
            v39 = v38;
            if ( !v38 )
            {
              v19 = -2147024882;
              goto LABEL_33;
            }
            *(_OWORD *)(v38 + 8) = v125;
            *(_OWORD *)(v38 + 24) = v126;
            v40 = AutoVariantRef::PinnableData::Pin((AutoVariantRef::PinnableData *)(v38 + 8));
            if ( v40 < 0 )
            {
              CoTaskMemFree(v39);
            }
            else
            {
              *v39 = *((_QWORD *)v32 + 3);
              *((_QWORD *)v32 + 3) = v39;
            }
            if ( v40 < 0 )
            {
              v19 = v40;
LABEL_33:
              v129 = v19;
            }
            v21 = 24576;
            v13 = 0;
            goto LABEL_35;
          }
        }
      }
LABEL_36:
      v130 = ++v31;
    }
  }
LABEL_40:
  if ( pvarg )
    pvarg->vt = 0;
  memset(&v139, 0, sizeof(v139));
  ((void (__fastcall *)(struct IDispatch *, __int64, __int64, __int64))v8->lpVtbl->AddRef)(v8, v18, v20, v21);
  if ( v8->lpVtbl >= ImageEnd || v8->lpVtbl < (struct IDispatchVtbl *)&_ImageBase )
  {
    ++*(_DWORD *)this;
    v118 = 1;
  }
  if ( *(_DWORD *)this == -1 )
    VBScriptClass_Report_Unexpected_Fatal_Error(this);
  v41 = TlsGetValue(g_luTls);
  v136 = v41;
  if ( v41 )
  {
    v137 = v41[6];
    v41[6] = this;
  }
  ppDataToRelease[0] = 0;
  v42 = 0;
  while ( 1 )
  {
    v131 = v42;
    if ( v42 >= v10 )
      break;
    if ( *((_WORD *)v119 + 12 * v42) == 16396 && (v79 = *((_QWORD *)v119 + 3 * v42 + 1)) != 0 )
    {
      if ( *(_WORD *)v79 == 9 || *(_WORD *)v79 == 13 )
      {
        v89 = *(_QWORD *)(v79 + 8);
        if ( v89 )
        {
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v89 + 8LL))(*(_QWORD *)(v79 + 8));
          *((_QWORD *)Block + v111++) = v89;
        }
      }
      else if ( *(_WORD *)v79 == 0x2000 || *(_WORD *)v79 == 8204 )
      {
        v84 = *(SAFEARRAY **)(v79 + 8);
        if ( v84 )
        {
          SafeArrayAddRef(v84, ppDataToRelease);
          *((_QWORD *)v135 + v115++) = v84;
          if ( ppDataToRelease[0] )
            *((PVOID *)v113 + (int)v110++) = ppDataToRelease[0];
        }
      }
      ++v42;
    }
    else
    {
      ++v42;
    }
  }
  if ( ((__int64 (__fastcall *)(struct IDispatch *, GUID *, struct IDispatch **))v8->lpVtbl->QueryInterface)(
         v8,
         &IID_IDispatchEx,
         &v133) >= 0 )
  {
    v45 = *((_QWORD *)this + 20);
    if ( v45 )
    {
      v51 = *(CSession **)(*(_QWORD *)(v45 + 32) + 72LL);
      *(_QWORD *)(v45 + 56) = v51;
    }
    else
    {
      v46 = *((_QWORD *)this + 21);
      v47 = operator new(0x58u);
      v48 = v47;
      if ( v47 )
      {
        *v47 = &DexCaller::`vftable'{for `IServiceProvider'};
        v47[1] = &DexCaller::`vftable'{for `ICanHandleException'};
        v47[2] = &DexCaller::`vftable'{for `IProvideRuntimeContext'};
        *((_DWORD *)v47 + 6) = 1;
        v47[4] = 0;
        v47[5] = 0;
        v47[6] = 0;
        *((_DWORD *)v47 + 16) &= ~1u;
        *((_DWORD *)v47 + 16) &= ~2u;
        v47[9] = 0;
        v47[10] = 0;
      }
      else
      {
        v48 = 0;
      }
      *((_QWORD *)this + 20) = v48;
      if ( !v48 )
      {
        *((_QWORD *)this + 20) = 0;
        v19 = -2147024882;
LABEL_82:
        ((void (__fastcall *)(struct IDispatch *))v133->lpVtbl->Release)(v133);
        goto LABEL_83;
      }
      v48[4] = this;
      _InterlockedIncrement((volatile signed __int32 *)this + 2);
      *(_QWORD *)(*((_QWORD *)this + 20) + 56LL) = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 20) + 32LL) + 72LL);
      if ( v46 )
      {
        *(_QWORD *)(*((_QWORD *)this + 20) + 40LL) = v46;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 8LL))(v46);
      }
      v49 = *((_QWORD *)this + 4);
      if ( !v49
        || *((_QWORD *)this + 20) == -48
        || (*(_QWORD *)(*((_QWORD *)this + 20) + 48LL) = 0,
            (v50 = *(int (__fastcall ****)(_QWORD, GUID *))(v49 + 160)) != 0)
        && (**v50)(v50, &IID_IUnknown) < 0 )
      {
        *(_QWORD *)(*((_QWORD *)this + 20) + 48LL) = 0;
      }
      v51 = (CSession *)*((_QWORD *)this + 21);
      if ( v51 )
      {
        (*(void (__fastcall **)(CSession *))(*(_QWORD *)v51 + 16LL))(v51);
        *((_QWORD *)this + 21) = 0;
      }
    }
    v55 = (struct IServiceProvider *)*((_QWORD *)this + 20);
    *((_QWORD *)this + 20) = 0;
    v56 = v133;
    v57 = 0;
    v58 = *((_QWORD *)this + 4);
    if ( v58 )
    {
      if ( *(_QWORD *)(v58 + 904) )
      {
        v57 = CSession::IsResponseDotWrite(v51, v133, a3);
        if ( !v57 )
          CSession::SendRuntimeScriptInfoToHost(this, SCRIPTTRACEINFO_COMCALLSTART);
      }
    }
    v19 = IDispatchExInvokeEx2(this, (struct IDispatchEx *)v56, a3, 0x409u, v16, &v127, pvarg, &v139, v55);
    if ( !v57 )
    {
      v59 = *((_QWORD *)this + 4);
      if ( v59 )
      {
        v60 = *(_QWORD *)(v59 + 904);
        if ( v60 )
        {
          v90 = 0;
          v121 = 0;
          v91 = 0;
          v92 = 0;
          v93 = *((_QWORD *)this + 9);
          if ( v93 )
          {
            v121 = 0;
            if ( *(_QWORD *)(v93 + 464) )
            {
              v94 = *(FncInfo **)(v93 + 40);
              if ( v94 )
              {
                v95 = *(_QWORD *)v94;
                if ( *(_QWORD *)v94 )
                {
                  v96 = *(int **)(v95 + 64);
                  v124 = (unsigned int *)(*v96 + *(_QWORD *)(v95 + 72));
                  if ( v124 )
                  {
                    if ( v96[1] == 32 )
                    {
                      v132 = 0;
                      FncInfo::GetBos(v94, *(_DWORD *)(v93 + 488), (struct BOS *)&v132);
                      v91 = v132;
                      v92 = v132 + HIDWORD(v132);
                      v90 = *v124;
                      v121 = *v124;
                    }
                  }
                }
              }
            }
          }
          v97 = *(void (__fastcall **)(__int64, __int64, __int128 *, __int64, int, int, _QWORD))(*(_QWORD *)v60 + 24LL);
          v141 = *(_OWORD *)(v59 + 912);
          v97(v60, 3, &v141, v90, v91, v92, 0);
        }
      }
    }
    v61 = (DexCaller *)*((_QWORD *)this + 20);
    if ( v61 )
    {
      DexCaller::Release(v61);
      *((_QWORD *)this + 20) = 0;
    }
    v62 = *((_QWORD *)this + 21);
    if ( v62 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
      *((_QWORD *)this + 21) = 0;
    }
    *((_QWORD *)this + 20) = v55;
    v8 = v116;
    goto LABEL_82;
  }
  LODWORD(v119) = 0;
  v52 = 0;
  if ( this )
  {
    v71 = *((_QWORD *)this + 4);
    if ( v71 )
    {
      if ( *(_QWORD *)(v71 + 904) )
      {
        v52 = CSession::IsResponseDotWrite(v43, v8, a3);
        if ( !v52 )
          CSession::SendRuntimeScriptInfoToHost(this, SCRIPTTRACEINFO_COMCALLSTART);
      }
    }
  }
  v19 = IDispatchInvoke2(this, v8, a3, v44, 0x409u, v16, &v127, pvarg, &v139, (unsigned int *)&v119);
  if ( this )
  {
    if ( !v52 )
    {
      v53 = *((_QWORD *)this + 4);
      if ( v53 )
      {
        v54 = *(_QWORD *)(v53 + 904);
        if ( v54 )
        {
          v122 = 0;
          v123 = 0;
          v98 = *((_QWORD *)this + 9);
          if ( v98 )
          {
            v122 = 0;
            v123 = 0;
            if ( *(_QWORD *)(v98 + 464) )
            {
              v99 = *(FncInfo **)(v98 + 40);
              if ( v99 )
              {
                v100 = *(_QWORD *)v99;
                if ( *(_QWORD *)v99 )
                {
                  v101 = *(int **)(v100 + 64);
                  if ( *v101 + *(_QWORD *)(v100 + 72) && v101[1] == 32 )
                  {
                    v134 = 0;
                    FncInfo::GetBos(v99, *(_DWORD *)(v98 + 488), (struct BOS *)&v134);
                    v122 = v134;
                    v123 = v134 + HIDWORD(v134);
                  }
                  v8 = v116;
                }
              }
            }
          }
          v102 = *(void (__fastcall **)(__int64, __int64, __int128 *))(*(_QWORD *)v54 + 24LL);
          v142 = *(_OWORD *)(v53 + 912);
          v102(v54, 3, &v142);
        }
      }
    }
  }
LABEL_83:
  ((void (__fastcall *)(struct IDispatch *))v8->lpVtbl->Release)(v8);
  if ( v19 < 0 )
  {
    if ( pvarg )
      VAR::Clear((VAR *)pvarg);
    if ( v19 == -2147352567 )
    {
      scode = v139.scode;
      if ( v139.scode >= 0 )
      {
        if ( v139.wCode )
        {
          scode = v139.wCode | 0x800A0000;
          v139.scode = scode;
          v139.wCode = 0;
        }
        else
        {
          FreeExcepInfo(&v139);
          scode = -2147467259;
          v139.scode = -2147467259;
        }
      }
      if ( scode == -2147352318 )
      {
        FreeExcepInfo(&v139);
        v19 = -2147352318;
      }
      else
      {
        if ( !v139.bstrDescription && !v139.pfnDeferredFillIn )
        {
          if ( (scode & 0x1FFF0000) != 0xA0000 )
            v139.scode = MapHr(scode);
          v139.pfnDeferredFillIn = (HRESULT (__stdcall *)(struct tagEXCEPINFO *))ExcepInfoDeferredFillIn;
        }
        v82 = CSession::PseGet(this);
        RuntimeScriptException::Free(v82);
        *(struct tagEXCEPINFO *)((char *)v82 + 8) = v139;
        memset_0(&v139, 0, sizeof(v139));
        v83 = (CScriptRuntime *)*((_QWORD *)this + 9);
        if ( v83 )
          CScriptRuntime::RecordErrorContext(v83, v82);
        v19 = -2040119292;
      }
    }
    goto LABEL_153;
  }
  if ( !pvarg )
    goto LABEL_101;
  vt = pvarg->vt;
  if ( (vt & 0x4000) != 0 )
  {
    VAR::Clear((VAR *)pvarg);
    v19 = -2146828275;
    goto LABEL_153;
  }
  if ( vt != 9 )
  {
    switch ( vt )
    {
      case 13:
        llVal = (int (__fastcall ***)(_QWORD, GUID *, struct IDispatch **))pvarg->llVal;
        if ( llVal )
        {
          v116 = 0;
          if ( (**llVal)(llVal, &IID_IDispatch, &v116) >= 0 )
          {
            (*(void (__fastcall **)(LONGLONG))(*pvarg->pllVal + 16))(pvarg->llVal);
            pvarg->vt = 9;
            pvarg->llVal = (LONGLONG)v116;
          }
        }
        v19 = VAR::MoveToHeap((VAR *)pvarg);
        v13 = 0;
        if ( v19 >= 0 )
        {
          v19 = 0;
          v12 = v113;
          v14 = v111;
          v15 = v110;
          goto LABEL_243;
        }
        goto LABEL_100;
      case 20:
        v70 = pvarg->llVal;
        if ( v70 >= (__int64)0xFFFFFFFF80000000uLL && v70 <= 0x7FFFFFFF )
        {
          pvarg->vt = 3;
          pvarg->lVal = v70;
          LOWORD(vt) = 3;
        }
        break;
      case 21:
        ullVal = pvarg->ullVal;
        if ( ullVal <= 0xFFFFFFFF )
        {
          LOWORD(vt) = 19;
          pvarg->vt = 19;
          pvarg->lVal = ullVal;
        }
        break;
    }
    if ( (unsigned __int16)vt >= 0x49u && (unsigned __int16)vt < 0x51u )
    {
      VariantClear(pvarg);
      v19 = -2147467259;
      v13 = 0;
      goto LABEL_100;
    }
    if ( (unsigned __int16)vt != 14 )
    {
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
          goto LABEL_101;
        default:
          if ( (vt & 0x4000) != 0 )
            goto LABEL_101;
          v19 = VAR::MoveToHeap((VAR *)pvarg);
          v13 = 0;
          if ( v19 < 0 )
            goto LABEL_100;
          v19 = 0;
          v12 = v113;
          v14 = v111;
          v15 = v110;
          break;
      }
      goto LABEL_243;
    }
LABEL_101:
    v13 = 0;
    v19 = 0;
    v12 = v113;
    v14 = v111;
    v15 = v110;
    goto LABEL_243;
  }
  v64 = (int (__fastcall ***)(_QWORD, GUID *, unsigned int **))pvarg->llVal;
  if ( v64 )
  {
    v124 = 0;
    if ( (**v64)(v64, &IID_IDispatchEx, &v124) >= 0 )
    {
      (*(void (__fastcall **)(LONGLONG))(*pvarg->pllVal + 16))(pvarg->llVal);
      pvarg->llVal = (LONGLONG)v124;
    }
  }
  v65 = TlsGetValue(g_luTls);
  v13 = 0;
  if ( v65 )
    v66 = v65[4];
  else
    v66 = 0;
  if ( v66 )
  {
    v67 = *(GcBlockFactory **)(v66 + 16);
    if ( v67 == *(GcBlockFactory **)(v66 + 8) )
    {
      v85 = *(struct GcBlock **)v66;
      if ( *(_QWORD *)v66 )
      {
        *(_QWORD *)v66 = *((_QWORD *)v85 + 150);
      }
      else
      {
        v85 = GcBlockFactory::PblkAlloc(v67);
        v13 = 0;
        if ( !v85 )
        {
          v69 = 0;
          goto LABEL_97;
        }
      }
      v67 = (struct GcBlock *)((char *)v85 + 1200);
      *((_QWORD *)v85 + 150) = *(_QWORD *)(v66 + 8);
      *(_QWORD *)(v66 + 8) = v85;
      *(_QWORD *)(v66 + 16) = (char *)v85 + 1200;
    }
    ++*(_DWORD *)(v66 + 24);
    v68 = (_WORD *)((char *)v67 - 24);
    *(_QWORD *)(v66 + 16) = v68;
    *v68 = 0;
    if ( *(_DWORD *)(v66 + 24) == 1 )
      _InterlockedIncrement(&g_cLibRef);
    v69 = *(_QWORD *)(v66 + 16);
LABEL_97:
    if ( v69 )
    {
      *(_OWORD *)v69 = *(_OWORD *)&pvarg->vt;
      *(_QWORD *)(v69 + 16) = pvarg->pRecInfo;
      pvarg->vt = 74;
      pvarg->llVal = v69;
      v19 = 0;
    }
    else
    {
      VAR::Clear((VAR *)pvarg);
      v19 = -2147024882;
      v13 = 0;
    }
    if ( v19 >= 0 )
    {
      v19 = 0;
      v12 = v113;
      v14 = v111;
      v15 = v110;
      goto LABEL_243;
    }
    goto LABEL_100;
  }
  VAR::Clear((VAR *)pvarg);
  v19 = -2147024882;
  v13 = 0;
LABEL_100:
  v12 = v113;
  v14 = v111;
  v15 = v110;
LABEL_243:
  v103 = v13;
  v104 = (_QWORD **)Block;
  if ( v14 > 0 )
  {
    do
    {
      (*(void (__fastcall **)(_QWORD *, __int64))(*v104[v103] + 16LL))(v104[v103], v15);
      ++v103;
    }
    while ( v103 < v111 );
    v12 = v113;
    LODWORD(v15) = v110;
    v13 = 0;
  }
  v105 = v13;
  v106 = (SAFEARRAY **)v135;
  if ( v115 > 0 )
  {
    do
      SafeArrayReleaseDescriptor(v106[v105++]);
    while ( v105 < v115 );
    v12 = v113;
    LODWORD(v15) = v110;
    v13 = 0;
  }
  v107 = v13;
  if ( (int)v15 > 0 )
  {
    do
    {
      SafeArrayReleaseData(*((PVOID *)v12 + (unsigned int)v107++));
      v12 = v113;
    }
    while ( v107 < (int)v110 );
  }
  free(v104);
  free(v106);
  free(v113);
  if ( v118 )
  {
    if ( !*(_DWORD *)this )
      VBScriptClass_Report_Unexpected_Fatal_Error(this);
    if ( v136 )
      v136[6] = v137;
    CSession::ClearVBSClassQueueAtCurrentDepth(this);
    --*(_DWORD *)this;
  }
  if ( v144 )
    *(_QWORD *)(v144 + 56) = **(_QWORD **)(v144 + 56);
  if ( v146 )
  {
    for ( k = 0; k < v146; ++k )
      AutoVariantRef::~AutoVariantRef((VARIANTARG *)((char *)pv + 32 * k));
    if ( pv && pv != v147 )
      CoTaskMemFree(pv);
    v146 = 0;
  }
  if ( v138 )
    free(v138);
  AutoCalloutParameterLock::~AutoCalloutParameterLock((AutoCalloutParameterLock *)&v143);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x180004400  push    rbx
0x180004402  push    rsi
0x180004403  push    rdi
0x180004404  push    r12
0x180004406  push    r13
0x180004408  push    r14
0x18000440a  push    r15
0x18000440c  sub     rsp, 3D0h
0x180004413  mov     rax, cs:__security_cookie
0x18000441a  xor     rax, rsp
0x18000441d  mov     [rsp+408h+var_48], rax
0x180004425  mov     esi, r9d
0x180004428  mov     [rsp+408h+var_3B0], r8d
0x18000442d  mov     r15, rdx
0x180004430  mov     [rsp+408h+var_390], rdx
0x180004435  mov     rbx, rcx
0x180004438  mov     [rsp+408h+var_280], rcx
0x180004440  mov     r13, [rsp+408h+pvarg]
0x180004448  movsxd  r12, [rsp+408h+arg_28]
0x180004450  mov     [rsp+408h+var_394], r12d
0x180004455  mov     rax, [rsp+408h+arg_30]
0x18000445d  mov     [rsp+408h+var_380], rax
0x180004465  xorps   xmm0, xmm0
0x180004468  xor     eax, eax
0x18000446a  movups  xmmword ptr [rsp+408h+var_338.rgvarg], xmm0
0x180004472  mov     qword ptr [rsp+408h+var_338.cArgs], rax
0x18000447a  xorps   xmm1, xmm1
0x18000447d  movups  xmmword ptr [rsp+408h+var_2D8.wCode], xmm1
0x180004485  movups  xmmword ptr [rsp+408h+var_2D8.bstrDescription], xmm1
0x18000448d  movups  xmmword ptr [rsp+408h+var_2D8.dwHelpContext], xmm1
0x180004495  movups  xmmword ptr [rsp+408h+var_2D8.pfnDeferredFillIn], xmm1
0x18000449d  mov     [rsp+408h+var_308], rax
0x1800044a5  mov     [rsp+408h+var_2E0], rax
0x1800044ad  lea     rcx, [rsp+408h+var_258]; this
0x1800044b5  call    ??0AutoCalloutParameterLock@@QEAA@XZ; AutoCalloutParameterLock::AutoCalloutParameterLock(void)
0x1800044ba  mov     edx, 8; Size
0x1800044bf  mov     rcx, r12; Count
0x1800044c2  call    cs:__imp_calloc
0x1800044c9  nop     dword ptr [rax+rax+00h]
0x1800044ce  mov     [rsp+408h+Block], rax
0x1800044d6  mov     edx, 8; Size
0x1800044db  mov     rcx, r12; Count
0x1800044de  call    cs:__imp_calloc
0x1800044e5  nop     dword ptr [rax+rax+00h]
0x1800044ea  mov     r14, rax
0x1800044ed  mov     [rsp+408h+var_2F8], rax
0x1800044f5  mov     edx, 8; Size
0x1800044fa  mov     rcx, r12; Count
0x1800044fd  call    cs:__imp_calloc
0x180004504  nop     dword ptr [rax+rax+00h]
0x180004509  mov     [rsp+408h+var_3A8], rax
0x18000450e  cmp     [rsp+408h+Block], 0
0x180004517  jz      loc_1800058B2
0x18000451d  mov     [rsp+408h+var_290], r14
0x180004525  test    r14, r14
0x180004528  jz      loc_1800058B2
0x18000452e  mov     [rsp+408h+var_288], rax
0x180004536  test    rax, rax
0x180004539  jz      loc_1800058B2
0x18000453f  xor     r10d, r10d
0x180004542  mov     [rsp+408h+var_2F0], r10
0x18000454a  mov     ecx, r10d
0x18000454d  mov     [rsp+408h+var_3B4], ecx
0x180004551  mov     [rsp+408h+var_398], r10d
0x180004556  mov     edx, r10d
0x180004559  mov     [rsp+408h+var_3B8], edx
0x18000455d  mov     [rsp+408h+var_384], r10d
0x180004565  mov     [rsp+408h+var_2E8], r10
0x18000456d  mov     r14d, esi
0x180004570  and     r14d, 0Fh
0x180004574  mov     dword ptr [rsp+408h+var_3A0], r14d
0x180004579  mov     [rsp+408h+arg_18], r14d
0x180004581  test    r15, r15
0x180004584  jz      loc_18000520D
0x18000458a  test    r14b, 0Ch
0x18000458e  jnz     loc_18000521D
0x180004594  mov     [rsp+408h+var_338.rgdispidNamedArgs], r10
0x18000459c  mov     [rsp+408h+var_338.cNamedArgs], r10d
0x1800045a4  mov     rcx, [rsp+408h+var_380]
0x1800045ac  mov     [rsp+408h+var_338.cArgs], r12d
0x1800045b4  mov     [rsp+408h+var_338.rgvarg], rcx
0x1800045bc  lea     rax, [rsp+408h+var_2E0]
0x1800045c4  mov     [rsp+408h+var_3E0], rax
0x1800045c9  lea     r9, [rsp+408h+var_138]
0x1800045d1  lea     r8, [rsp+408h+var_338]
0x1800045d9  mov     rdx, r15
0x1800045dc  mov     ecx, r14d
0x1800045df  call    MungeArgs
0x1800045e4  mov     edi, eax
0x1800045e6  test    eax, eax
0x1800045e8  js      loc_180005000
0x1800045ee  mov     rax, [rbx+20h]
0x1800045f2  test    rax, rax
0x1800045f5  jz      short loc_180004604
0x1800045f7  cmp     dword ptr [rax+104h], 0
0x1800045fe  jnz     loc_18000528A
0x180004604  mov     rax, [r15]
0x180004607  lea     rdi, __ImageBase
0x18000460e  cmp     rax, cs:?ImageEnd@@3PEBXEB; void const * const ImageEnd
0x180004615  jb      loc_180004E11
0x18000461b  mov     edi, [rsp+408h+var_338.cArgs]
0x180004622  mov     r14, [rsp+408h+var_338.rgvarg]
0x18000462a  xor     r10d, r10d
0x18000462d  mov     [rsp+408h+var_39C], r10d
0x180004632  mov     r8d, r10d
0x180004635  mov     [rsp+408h+var_388], r10d
0x18000463d  mov     edx, r10d
0x180004640  mov     r9d, 4000h
0x180004646  mov     [rsp+408h+var_39C], edx
0x18000464a  cmp     edx, edi
0x18000464c  jb      loc_180004E6B
0x180004652  cmp     r8d, 8
0x180004656  ja      loc_180004F4E
0x18000465c  lea     rax, [rsp+408h+var_238]
0x180004664  mov     [rsp+408h+pv], rax
0x18000466c  mov     esi, r10d
0x18000466f  mov     [rsp+408h+var_388], r10d
0x180004677  mov     edx, r10d
0x18000467a  mov     [rsp+408h+var_39C], edx
0x18000467e  cmp     edx, edi
0x180004680  jb      loc_180004E24
0x180004686  mov     rcx, [rbx+0C8h]
0x18000468d  test    rcx, rcx
0x180004690  jnz     short loc_1800046B3
0x180004692  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x180004698  call    cs:__imp_TlsGetValue
0x18000469f  nop     dword ptr [rax+rax+00h]
0x1800046a4  xor     r10d, r10d
0x1800046a7  test    rax, rax
0x1800046aa  mov     ecx, r10d
0x1800046ad  jz      short loc_1800046B3
0x1800046af  mov     rcx, [rax+28h]
0x1800046b3  mov     [rsp+408h+var_250], rcx
0x1800046bb  mov     rax, [rcx+38h]
0x1800046bf  mov     [rsp+408h+var_258], rax
0x1800046c7  lea     rax, [rsp+408h+var_258]
0x1800046cf  mov     [rcx+38h], rax
0x1800046d3  mov     [rsp+408h+var_240], esi
0x1800046da  mov     edi, r10d
0x1800046dd  mov     [rsp+408h+var_31C], r10d
0x1800046e5  mov     esi, r10d
0x1800046e8  mov     [rsp+408h+var_318], r10d
0x1800046f0  mov     edx, 400Ch
0x1800046f5  mov     r8d, 600Ch
0x1800046fb  mov     r9d, 6000h
0x180004701  mov     r11d, 2000h
0x180004707  nop     word ptr [rax+rax+00000000h]
0x180004710  cmp     esi, [rsp+408h+var_240]
0x180004717  jnb     loc_18000481C
0x18000471d  mov     r15d, esi
0x180004720  shl     r15, 5
0x180004724  mov     rax, [rsp+408h+pv]
0x18000472c  add     r15, rax
0x18000472f  xorps   xmm0, xmm0
0x180004732  movups  [rsp+408h+var_358], xmm0
0x18000473a  movups  [rsp+408h+var_348], xmm0
0x180004742  movzx   eax, word ptr [r15]
0x180004746  cmp     ax, dx
0x180004749  jnz     loc_1800052F7
0x18000474f  mov     rax, [r15+8]
0x180004753  movzx   ecx, word ptr [rax]
0x180004756  cmp     cx, 8
0x18000475a  jnz     loc_1800051B0
0x180004760  cmp     qword ptr [rax+8], 0
0x180004765  jz      loc_18000480E
0x18000476b  mov     dword ptr [rsp+408h+var_358], r10d
0x180004773  mov     rdx, [rax+8]
0x180004777  mov     qword ptr [rsp+408h+var_358+8], rdx
0x18000477f  mov     eax, r10d
0x180004782  mov     rcx, [r15+18h]
0x180004786  test    rcx, rcx
0x180004789  jnz     loc_180004EF3
0x18000478f  mov     ecx, 28h ; '('; cb
0x180004794  call    cs:__imp_CoTaskMemAlloc
0x18000479b  nop     dword ptr [rax+rax+00h]
0x1800047a0  mov     r14, rax
0x1800047a3  test    rax, rax
0x1800047a6  jnz     short loc_1800047AF
0x1800047a8  mov     edi, 8007000Eh
0x1800047ad  jmp     short loc_1800047ED
0x1800047af  lea     rcx, [rax+8]; this
0x1800047b3  movups  xmm0, [rsp+408h+var_358]
0x1800047bb  movups  xmmword ptr [rcx], xmm0
0x1800047be  movups  xmm1, [rsp+408h+var_348]
0x1800047c6  movups  xmmword ptr [rcx+10h], xmm1
0x1800047ca  call    ?Pin@PinnableData@AutoVariantRef@@QEAAJXZ; AutoVariantRef::PinnableData::Pin(void)
0x1800047cf  mov     r12d, eax
0x1800047d2  test    eax, eax
0x1800047d4  js      loc_180004F3A
0x1800047da  mov     rcx, [r15+18h]
0x1800047de  mov     [r14], rcx
0x1800047e1  mov     [r15+18h], r14
0x1800047e5  test    r12d, r12d
0x1800047e8  jns     short loc_1800047F4
0x1800047ea  mov     edi, r12d
0x1800047ed  mov     [rsp+408h+var_31C], edi
0x1800047f4  mov     r11d, 2000h
0x1800047fa  mov     r9d, 6000h
0x180004800  xor     r10d, r10d
0x180004803  mov     edx, 400Ch
0x180004808  mov     r8d, 600Ch
0x18000480e  inc     esi
0x180004810  mov     [rsp+408h+var_318], esi
0x180004817  jmp     loc_180004710
0x18000481c  mov     r15, [rsp+408h+var_390]
0x180004821  mov     r12d, [rsp+408h+var_394]
0x180004826  mov     esi, 400Ch
0x18000482b  test    edi, edi
0x18000482d  js      loc_180005003
0x180004833  mov     r14d, dword ptr [rsp+408h+var_3A0]
0x180004838  lea     rdi, __ImageBase
0x18000483f  test    r13, r13
0x180004842  jz      short loc_18000484B
0x180004844  xor     eax, eax
0x180004846  mov     [r13+0], ax
0x18000484b  xorps   xmm0, xmm0
0x18000484e  movups  xmmword ptr [rsp+408h+var_2D8.wCode], xmm0
0x180004856  movups  xmmword ptr [rsp+408h+var_2D8.bstrDescription], xmm0
0x18000485e  movups  xmmword ptr [rsp+408h+var_2D8.dwHelpContext], xmm0
0x180004866  movups  xmmword ptr [rsp+408h+var_2D8.pfnDeferredFillIn], xmm0
0x18000486e  mov     rax, [r15]
0x180004871  mov     rcx, r15
0x180004874  mov     rax, [rax+8]
0x180004878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000487d  mov     rax, [r15]
0x180004880  cmp     rax, cs:?ImageEnd@@3PEBXEB; void const * const ImageEnd
0x180004887  jb      loc_180004A4A
0x18000488d  inc     dword ptr [rbx]
0x18000488f  mov     [rsp+408h+var_384], 1
0x18000489a  mov     eax, 0FFFFFFFFh
0x18000489f  cmp     [rbx], eax
0x1800048a1  jz      loc_180004F2D
0x1800048a7  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x1800048ad  call    cs:__imp_TlsGetValue
0x1800048b4  nop     dword ptr [rax+rax+00h]
0x1800048b9  mov     [rsp+408h+var_2F0], rax
0x1800048c1  test    rax, rax
0x1800048c4  jz      short loc_1800048D6
0x1800048c6  mov     rcx, [rax+30h]
0x1800048ca  mov     [rsp+408h+var_2E8], rcx
0x1800048d2  mov     [rax+30h], rbx
0x1800048d6  mov     [rsp+408h+ppDataToRelease], 0
0x1800048e2  xor     edi, edi
0x1800048e4  mov     [rsp+408h+var_314], edi
0x1800048eb  cmp     edi, r12d
0x1800048ee  jl      loc_180004DAA
0x1800048f4  mov     rax, [r15]
0x1800048f7  lea     r8, [rsp+408h+var_308]
0x1800048ff  lea     rdx, IID_IDispatchEx
0x180004906  mov     rcx, r15
0x180004909  mov     rax, [rax]
0x18000490c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004911  test    eax, eax
0x180004913  js      loc_180004A58
0x180004919  mov     rdx, [rbx+0A0h]
0x180004920  test    rdx, rdx
0x180004923  jnz     loc_180004AF1
0x180004929  mov     rdi, [rbx+0A8h]
0x180004930  mov     ecx, 58h ; 'X'; Size
0x180004935  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000493a  mov     rcx, rax
0x18000493d  xor     r12d, r12d
0x180004940  test    rax, rax
0x180004943  jz      loc_1800050FA
0x180004949  lea     rax, ??_7DexCaller@@6BIServiceProvider@@@; const DexCaller::`vftable'{for `IServiceProvider'}
0x180004950  mov     [rcx], rax
0x180004953  lea     rax, ??_7DexCaller@@6BICanHandleException@@@; const DexCaller::`vftable'{for `ICanHandleException'}
0x18000495a  mov     [rcx+8], rax
0x18000495e  lea     rax, ??_7DexCaller@@6BIProvideRuntimeContext@@@; const DexCaller::`vftable'{for `IProvideRuntimeContext'}
0x180004965  mov     [rcx+10h], rax
0x180004969  mov     dword ptr [rcx+18h], 1
0x180004970  mov     [rcx+20h], r12
0x180004974  mov     [rcx+28h], r12
0x180004978  mov     [rcx+30h], r12
0x18000497c  and     dword ptr [rcx+40h], 0FFFFFFFEh
0x180004980  mov     eax, [rcx+40h]
0x180004983  and     eax, 0FFFFFFFDh
0x180004986  mov     [rcx+40h], eax
0x180004989  mov     [rcx+48h], r12
0x18000498d  mov     [rcx+50h], r12
0x180004991  mov     [rbx+0A0h], rcx
0x180004998  test    rcx, rcx
0x18000499b  jz      loc_180004EB9
0x1800049a1  mov     [rcx+20h], rbx
0x1800049a5  lock inc dword ptr [rbx+8]
0x1800049a9  mov     rdx, [rbx+0A0h]
0x1800049b0  mov     rax, [rdx+20h]
0x1800049b4  mov     rcx, [rax+48h]
0x1800049b8  mov     [rdx+38h], rcx
0x1800049bc  test    rdi, rdi
0x1800049bf  jz      short loc_1800049DB
0x1800049c1  mov     rax, [rbx+0A0h]
0x1800049c8  mov     [rax+28h], rdi
0x1800049cc  mov     rax, [rdi]
0x1800049cf  mov     rcx, rdi
0x1800049d2  mov     rax, [rax+8]
0x1800049d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049db  mov     rcx, [rbx+20h]
0x1800049df  test    rcx, rcx
0x1800049e2  jz      loc_1800053B3
  ... truncated ...
```
