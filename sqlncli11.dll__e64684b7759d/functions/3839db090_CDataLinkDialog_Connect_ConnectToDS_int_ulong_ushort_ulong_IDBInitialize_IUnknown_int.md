# CDataLinkDialog_Connect::ConnectToDS(int *,ulong *,ushort *,ulong,IDBInitialize * *,IUnknown * *,int)

- ea: `0x3839db090`
- end: `0x3839dbd1d`
- name: `?ConnectToDS@CDataLinkDialog_Connect@@AEAAJPEAHPEAKPEAGKPEAPEAUIDBInitialize@@PEAPEAUIUnknown@@H@Z`
- size: `3213`
- prototype: `__int64 __fastcall(CDataLinkDialog_Connect *__hidden this, int *, unsigned int *, unsigned __int16 *, unsigned int, struct IDBInitialize **, struct IUnknown **, int)`
- caller_count: `3`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x3839da820`
- `0x3839dc2d0`
- `0x3839dc450`

## callees

- `0x3838434c0`
- `0x3838435e0`
- `0x383844d50`
- `0x38387da60`
- `0x38391ac10`
- `0x38391aed0`
- `0x38391afe0`
- `0x3839db090`
- `0x3839dbd60`
- `0x3839dd720`
- `0x383ade150`

## import_xrefs

- `USER32!LoadStringW` at `0x3839db31e`
- `USER32!LoadStringW` at `0x3839db686`
- `USER32!LoadStringW` at `0x3839db8f5`
- `USER32!LoadStringW` at `0x3839db932`
- `USER32!LoadStringW` at `0x3839db31e`
- `USER32!LoadStringW` at `0x3839db686`
- `USER32!LoadStringW` at `0x3839db8f5`
- `USER32!LoadStringW` at `0x3839db932`
- `USER32!MessageBoxW` at `0x3839db952`
- `USER32!MessageBoxW` at `0x3839db952`
- `ole32!CoCreateInstance` at `0x3839db1a8`
- `ole32!CoCreateInstance` at `0x3839db1a8`
- `ole32!CoTaskMemFree` at `0x3839dbc88`
- `ole32!CoTaskMemFree` at `0x3839dbc97`
- `ole32!CoTaskMemFree` at `0x3839dbc88`
- `ole32!CoTaskMemFree` at `0x3839dbc97`
- `OLEAUT32!__imp_VariantClear` at `0x3839dbc74`
- `OLEAUT32!__imp_VariantClear` at `0x3839dbc74`

## pseudocode

```c
__int64 __fastcall CDataLinkDialog_Connect::ConnectToDS(
        CDataLinkDialog_Connect *this,
        int *a2,
        unsigned int *a3,
        unsigned __int16 *a4,
        _QWORD *a5,
        struct IDBInitialize **a6,
        struct IUnknown **a7,
        int a8)
{
  unsigned __int16 *v8; // rdi
  unsigned int *v9; // r15
  CDataLinkDialog_Connect *v10; // r14
  _QWORD *v11; // r12
  HRESULT v12; // eax
  int v13; // eax
  __int64 v14; // r9
  unsigned __int64 v15; // rdx
  int StringW; // eax
  __int64 v17; // rdx
  WCHAR *v18; // r12
  unsigned __int64 v19; // rdi
  unsigned int i; // r13d
  int v21; // r14d
  unsigned __int16 *PropDescription; // r15
  __int64 v23; // r11
  __int64 v24; // rcx
  const wchar_t *v25; // r8
  unsigned __int64 v26; // rdx
  WCHAR *v27; // r9
  __int64 v28; // r10
  __int64 v29; // r11
  __int64 v30; // rcx
  unsigned __int16 *v31; // r8
  unsigned __int64 v32; // rdx
  WCHAR *v33; // r9
  __int64 v34; // r10
  __int64 v35; // r11
  __int64 v36; // rcx
  const wchar_t *v37; // r8
  unsigned __int64 v38; // rdx
  WCHAR *v39; // r9
  __int64 v40; // r10
  UINT v41; // edx
  __int64 v42; // r11
  const wchar_t *v43; // r9
  unsigned __int64 v44; // r8
  WCHAR *v45; // rcx
  __int64 v46; // r10
  __int64 v47; // r11
  WCHAR *v48; // r9
  unsigned __int64 v49; // r8
  WCHAR *v50; // rcx
  __int64 v51; // r10
  __int64 v52; // r11
  const wchar_t *v53; // r9
  unsigned __int64 v54; // r8
  WCHAR *v55; // rcx
  __int64 v56; // r10
  int v57; // eax
  __int64 v58; // rdx
  __int64 v59; // r8
  int v60; // ebx
  const struct _GUID *v61; // r8
  struct IUnknown *v62; // rcx
  int v63; // eax
  int v64; // eax
  _BYTE v66[32]; // [rsp+0h] [rbp-3198h] BYREF
  LPVOID *ppv; // [rsp+20h] [rbp-3178h]
  unsigned int v68; // [rsp+30h] [rbp-3168h]
  int v69; // [rsp+34h] [rbp-3164h]
  WCHAR *v70; // [rsp+38h] [rbp-3160h] BYREF
  unsigned __int64 v71; // [rsp+40h] [rbp-3158h]
  struct IUnknown *v72; // [rsp+48h] [rbp-3150h] BYREF
  LPVOID v73; // [rsp+50h] [rbp-3148h] BYREF
  int v74; // [rsp+58h] [rbp-3140h]
  int v75; // [rsp+5Ch] [rbp-313Ch]
  _QWORD v76[2]; // [rsp+60h] [rbp-3138h] BYREF
  int v77; // [rsp+70h] [rbp-3128h] BYREF
  unsigned int *v78; // [rsp+78h] [rbp-3120h]
  __int64 v79; // [rsp+80h] [rbp-3118h] BYREF
  __int64 v80; // [rsp+88h] [rbp-3110h]
  __int64 v81; // [rsp+90h] [rbp-3108h] BYREF
  _QWORD v82[2]; // [rsp+98h] [rbp-3100h] BYREF
  __int64 v83; // [rsp+A8h] [rbp-30F0h]
  __int64 v84; // [rsp+B0h] [rbp-30E8h]
  unsigned __int16 *v85; // [rsp+B8h] [rbp-30E0h]
  __int64 v86; // [rsp+C0h] [rbp-30D8h] BYREF
  __int64 v87; // [rsp+C8h] [rbp-30D0h] BYREF
  __int64 v88; // [rsp+D0h] [rbp-30C8h] BYREF
  __int64 v89; // [rsp+D8h] [rbp-30C0h] BYREF
  __int64 pExceptionObject; // [rsp+E8h] [rbp-30B0h] BYREF
  int *v91; // [rsp+F0h] [rbp-30A8h]
  __int64 v92; // [rsp+F8h] [rbp-30A0h] BYREF
  unsigned int *v93; // [rsp+100h] [rbp-3098h]
  _QWORD *v94; // [rsp+108h] [rbp-3090h]
  CDataLinkDialog_Connect *v95; // [rsp+110h] [rbp-3088h]
  _QWORD v96[3]; // [rsp+118h] [rbp-3080h] BYREF
  int v97; // [rsp+130h] [rbp-3068h]
  GUID v98; // [rsp+134h] [rbp-3064h]
  WCHAR v99[512]; // [rsp+150h] [rbp-3048h] BYREF
  WCHAR Caption[512]; // [rsp+550h] [rbp-2C48h] BYREF
  WCHAR Buffer[5120]; // [rsp+950h] [rbp-2848h] BYREF

  v96[1] = -2;
  v8 = a4;
  v85 = a4;
  v9 = a3;
  v93 = a3;
  v91 = a2;
  v10 = this;
  v95 = this;
  v82[1] = a2;
  v78 = a3;
  v11 = a5;
  v94 = a5;
  v75 = 0;
  v69 = 0;
  *(_QWORD *)a4 = 0;
  *a5 = 0;
  v74 = 0;
  v76[1] = 0;
  v77 = 41;
  v96[2] = &v77;
  v97 = 1;
  v98 = DBPROPSET_DATASOURCEINFO;
  v72 = 0;
  v73 = 0;
  v76[0] = 0;
  v12 = CoCreateInstance(&CLSID_SQLNCLI11, 0, 1u, &IID_IDBProperties, &v73);
  v68 = v12;
  if ( v12 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( off_383B49128[0] )
      {
        LODWORD(ppv) = 2527;
        bidTraceW(off_383B432A8[0], 2587689, off_383B49128[0], (unsigned int)v12);
      }
    }
    v73 = 0;
    v69 = 40070;
    pExceptionObject = 0;
    throw (__int64 *)&pExceptionObject;
  }
  v13 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD))(*(_QWORD *)v73 + 40LL))(v73, 2, *((_QWORD *)v10 + 3));
  v14 = (unsigned int)v13;
  v68 = v13;
  if ( v13 == -2147217887 || v13 == 265946 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      v15 = 2596873;
      if ( off_383B49128[0] )
      {
        if ( v13 < 0 )
          v15 = 2596905;
        LODWORD(ppv) = v15 >> 10;
        bidTraceW(off_383B432A8[0], v15, off_383B49128[0], (unsigned int)v13);
      }
    }
    memset(Buffer, 0, 10236);
    v75 = 1;
    StringW = LoadStringW(g_hinstance_language, 0x9C8Fu, Buffer, 5118);
    v18 = &Buffer[StringW];
    v70 = v18;
    v19 = 5118LL - StringW;
    v71 = v19;
    for ( i = 0; i < 0xB; ++i )
    {
      v21 = *((_DWORD *)v10 + 18 * i + 10);
      if ( v21 )
      {
        PropDescription = CDataLinkDialog_Connect::GetPropDescription((CDataLinkDialog_Connect *)i, v17);
        if ( v19 )
        {
          if ( v19 <= 0x7FFFFFFF )
          {
            v23 = 0;
            v84 = 0;
            v24 = 2147483646;
            v25 = L"\"";
            v26 = v19;
            v27 = v18;
            v28 = 0;
            while ( v26 )
            {
              if ( !v24 || !*v25 )
                goto LABEL_28;
              *v27++ = *v25++;
              --v26;
              --v24;
              ++v28;
            }
            --v27;
            --v28;
LABEL_28:
            *v27 = 0;
            if ( v66 != (_BYTE *)-176LL )
            {
              v84 = v28;
              v23 = v28;
            }
            if ( v66 != (_BYTE *)-56LL )
            {
              v70 = &v18[v23];
              v18 = v70;
            }
            if ( v66 != (_BYTE *)-64LL )
            {
              v71 = v19 - v23;
              v19 -= v23;
            }
          }
          if ( v19 )
          {
            if ( v19 <= 0x7FFFFFFF )
            {
              v29 = 0;
              v80 = 0;
              v30 = 2147483646;
              v31 = PropDescription;
              v32 = v19;
              v33 = v18;
              v34 = 0;
              while ( v32 )
              {
                if ( !v30 || !*v31 )
                  goto LABEL_42;
                *v33++ = *v31++;
                --v32;
                --v30;
                ++v34;
              }
              --v33;
              --v34;
LABEL_42:
              *v33 = 0;
              if ( v66 != (_BYTE *)-136LL )
              {
                v80 = v34;
                v29 = v34;
              }
              if ( v66 != (_BYTE *)-56LL )
              {
                v70 = &v18[v29];
                v18 = v70;
              }
              if ( v66 != (_BYTE *)-64LL )
              {
                v71 = v19 - v29;
                v19 -= v29;
              }
            }
            if ( v19 && v19 <= 0x7FFFFFFF )
            {
              v35 = 0;
              v83 = 0;
              v36 = 2147483646;
              v37 = L"\"\t";
              v38 = v19;
              v39 = v18;
              v40 = 0;
              while ( v38 )
              {
                if ( !v36 || !*v37 )
                  goto LABEL_56;
                *v39++ = *v37++;
                --v38;
                --v36;
                ++v40;
              }
              --v39;
              --v40;
LABEL_56:
              *v39 = 0;
              if ( v66 != (_BYTE *)-168LL )
              {
                v83 = v40;
                v35 = v40;
              }
              if ( v66 != (_BYTE *)-56LL )
              {
                v70 = &v18[v35];
                v18 = v70;
              }
              if ( v66 != (_BYTE *)-64LL )
              {
                v71 = v19 - v35;
                v19 -= v35;
              }
            }
          }
        }
        memset(v99, 0, sizeof(v99));
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( off_383B49700[0] )
          {
            LODWORD(ppv) = v21;
            bidTraceW(off_383B432A8[0], 2632704, off_383B49700[0], PropDescription);
          }
          v19 = v71;
          v18 = v70;
        }
        switch ( v21 )
        {
          case 1:
            v41 = 40082;
            break;
          case 2:
            v41 = 40083;
            break;
          case 3:
            v41 = 40084;
            break;
          case 4:
            v41 = 40085;
            break;
          case 5:
            v41 = 40086;
            break;
          case 6:
            v41 = 40087;
            break;
          case 7:
            v41 = 40088;
            break;
          case 8:
            v41 = 40089;
            break;
          default:
            v41 = 40090;
            break;
        }
        LoadStringW(g_hinstance_language, v41, v99, 512);
        if ( v19 && v19 <= 0x7FFFFFFF )
        {
          v42 = 0;
          v82[0] = 0;
          v17 = 2147483646;
          v43 = L"(";
          v44 = v19;
          v45 = v18;
          v46 = 0;
          while ( v44 )
          {
            if ( !v17 || !*v43 )
              goto LABEL_84;
            *v45++ = *v43++;
            --v44;
            --v17;
            ++v46;
          }
          --v45;
          --v46;
LABEL_84:
          *v45 = 0;
          if ( v82 )
          {
            v82[0] = v46;
            v42 = v46;
          }
          if ( &v70 )
          {
            v70 = &v18[v42];
            v18 = v70;
          }
          if ( v66 != (_BYTE *)-64LL )
          {
            v71 = v19 - v42;
            v19 -= v42;
          }
        }
        if ( v19 && v19 <= 0x7FFFFFFF )
        {
          v47 = 0;
          v79 = 0;
          v17 = 2147483646;
          v48 = v99;
          v49 = v19;
          v50 = v18;
          v51 = 0;
          while ( v49 )
          {
            if ( !v17 || !*v48 )
              goto LABEL_98;
            *v50++ = *v48++;
            --v49;
            --v17;
            ++v51;
          }
          --v50;
          --v51;
LABEL_98:
          *v50 = 0;
          if ( &v79 )
          {
            v79 = v51;
            v47 = v51;
          }
          if ( &v70 )
          {
            v70 = &v18[v47];
            v18 = v70;
          }
          if ( v66 != (_BYTE *)-64LL )
          {
            v71 = v19 - v47;
            v19 -= v47;
          }
        }
        if ( v19 && v19 <= 0x7FFFFFFF )
        {
          v52 = 0;
          v81 = 0;
          v17 = 2147483646;
          v53 = L")\n\r";
          v54 = v19;
          v55 = v18;
          v56 = 0;
          while ( v54 )
          {
            if ( !v17 || !*v53 )
              goto LABEL_112;
            *v55++ = *v53++;
            --v54;
            --v17;
            ++v56;
          }
          --v55;
          --v56;
LABEL_112:
          *v55 = 0;
          if ( &v81 )
          {
            v81 = v56;
            v52 = v56;
          }
          if ( &v70 )
          {
            v70 = &v18[v52];
            v18 = v70;
          }
          if ( v66 != (_BYTE *)-64LL )
          {
            v71 = v19 - v52;
            v19 -= v52;
          }
        }
      }
      v10 = v95;
    }
    LoadStringW(g_hinstance_language, 0x9C90u, v18, v19);
    memset(Caption, 0, sizeof(Caption));
    LoadStringW(g_hinstance_language, 0x9C83u, Caption, 512);
    if ( MessageBoxW(*((HWND *)v10 + 2), Buffer, Caption, 0x14u) != 6 )
    {
      if ( (bidGblFlags & 2) != 0 && off_383B496F8[0] && bidID != -1 )
      {
        ppv = 0;
        off_383B15040();
      }
      v69 = 40071;
      v89 = 0;
      throw (__int64 *)&v89;
    }
    v9 = v93;
    v8 = v85;
    v11 = v94;
  }
  else if ( v13 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
      bidTraceHR(off_383B432A8[0], 2700297, (unsigned int)v13);
    v69 = 40071;
    v87 = 0;
    throw (__int64 *)&v87;
  }
  v57 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, struct IUnknown **, __int64))v73)(
          v73,
          &IID_IDBInitialize,
          &v72,
          v14);
  v68 = v57;
  if ( v57 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
    {
      LODWORD(ppv) = 2644;
      bidTraceW(off_383B432A8[0], 2707497, off_383B49128[0], (unsigned int)v57);
    }
    v69 = 40072;
    v72 = 0;
    v92 = 0;
    throw (__int64 *)&v92;
  }
  v60 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64, _QWORD))v72->lpVtbl[1].QueryInterface)(
          v72,
          v58,
          v59,
          (unsigned int)v57);
  v68 = v60;
  if ( v60 < 0 )
  {
    if ( (_DWORD)a6 )
      CDataLinkDialog_Connect::ConnectionMessageBox(v10, v72, v61);
    if ( (bidGblFlags & 2) != 0 )
      bidTraceHR(off_383B432A8[0], 2717705, (unsigned int)v60);
    if ( v60 != -2147217842 )
    {
      ((void (__fastcall *)(struct IUnknown *))v72->lpVtbl->Release)(v72);
      v72 = 0;
      v69 = 40073;
    }
    v96[0] = 0;
    throw (__int64 *)v96;
  }
  v62 = v72;
  *(_QWORD *)v8 = v72;
  v63 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, _QWORD *))v62->lpVtbl->QueryInterface)(
          v62,
          &IID_IDBCreateSession,
          v76);
  v68 = v63;
  if ( v63 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
      bidTraceHR(off_383B432A8[0], 2732041, (unsigned int)v63);
    v69 = 40072;
    v76[0] = 0;
    v86 = 0;
    throw (__int64 *)&v86;
  }
  v64 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, GUID *, _QWORD *))(*(_QWORD *)v76[0] + 24LL))(
          v76[0],
          0,
          &IID_IUnknown,
          v11);
  v68 = v64;
  if ( v64 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
      bidTraceHR(off_383B432A8[0], 2740233, (unsigned int)v64);
    v69 = 40073;
    v88 = 0;
    throw (__int64 *)&v88;
  }
  v68 = 0;
  if ( v91 )
    *v91 = v75;
  if ( v9 )
    *v9 = v69;
  if ( v73 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v73 + 16LL))(v73);
    v73 = 0;
  }
  if ( v76[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v76[0] + 16LL))(v76[0]);
  return v68;
}

```

## disassembly

```asm
0x3839db090  push    rbx
0x3839db092  push    rsi
0x3839db093  push    rdi
0x3839db094  push    r12
0x3839db096  push    r13
0x3839db098  push    r14
0x3839db09a  push    r15
0x3839db09c  mov     eax, 3160h
0x3839db0a1  call    _alloca_probe
0x3839db0a6  sub     rsp, rax
0x3839db0a9  mov     [rsp+3198h+var_3078], 0FFFFFFFFFFFFFFFEh
0x3839db0b5  mov     rax, cs:__security_cookie
0x3839db0bc  xor     rax, rsp
0x3839db0bf  mov     [rsp+3198h+var_48], rax
0x3839db0c7  mov     rdi, r9
0x3839db0ca  mov     [rsp+3198h+var_30E0], r9
0x3839db0d2  mov     r15, r8
0x3839db0d5  mov     [rsp+3198h+var_3098], r8
0x3839db0dd  mov     [rsp+3198h+var_30A8], rdx
0x3839db0e5  mov     r14, rcx
0x3839db0e8  mov     [rsp+3198h+var_3088], rcx
0x3839db0f0  mov     [rsp+3198h+var_30F8], rdx
0x3839db0f8  mov     [rsp+3198h+var_3120], r8
0x3839db0fd  mov     r12, [rsp+3198h+arg_20]
0x3839db105  mov     [rsp+3198h+var_3090], r12
0x3839db10d  xor     esi, esi
0x3839db10f  mov     [rsp+3198h+var_313C], esi
0x3839db113  mov     [rsp+3198h+var_3164], esi
0x3839db117  mov     [r9], rsi
0x3839db11a  mov     [r12], rsi
0x3839db11e  mov     [rsp+3198h+var_3140], esi
0x3839db122  mov     [rsp+3198h+pv], rsi
0x3839db127  mov     [rsp+3198h+var_3128], 29h ; ')'
0x3839db12f  lea     rax, [rsp+3198h+var_3128]
0x3839db134  mov     [rsp+3198h+var_3070], rax
0x3839db13c  mov     [rsp+3198h+var_3068], 1
0x3839db147  mov     eax, cs:DBPROPSET_DATASOURCEINFO.Data1
0x3839db14d  mov     [rsp+3198h+var_3064], eax
0x3839db154  mov     eax, dword ptr cs:DBPROPSET_DATASOURCEINFO.Data2
0x3839db15a  mov     [rsp+3198h+var_3060], eax
0x3839db161  mov     eax, dword ptr cs:DBPROPSET_DATASOURCEINFO.Data4
0x3839db167  mov     [rsp+3198h+var_305C], eax
0x3839db16e  mov     eax, dword ptr cs:DBPROPSET_DATASOURCEINFO.Data4+4
0x3839db174  mov     [rsp+3198h+var_3058], eax
0x3839db17b  mov     [rsp+3198h+var_3150], rsi
0x3839db180  mov     [rsp+3198h+var_3148], rsi
0x3839db185  mov     [rsp+3198h+var_3138], rsi
0x3839db18a  lea     rax, [rsp+3198h+var_3148]
0x3839db18f  mov     [rsp+3198h+ppv], rax; ppv
0x3839db194  lea     r9, IID_IDBProperties; riid
0x3839db19b  xor     edx, edx; pUnkOuter
0x3839db19d  lea     r8d, [rsi+1]; dwClsContext
0x3839db1a1  lea     rcx, CLSID_SQLNCLI11; rclsid
0x3839db1a8  call    cs:__imp_CoCreateInstance
0x3839db1ae  mov     [rsp+3198h+var_3168], eax
0x3839db1b2  test    eax, eax
0x3839db1b4  jns     short loc_3839DB21A
0x3839db1b6  test    byte ptr cs:_bidGblFlags, 2
0x3839db1bd  jz      short loc_3839DB1F1
0x3839db1bf  mov     r10, cs:off_383B432A8; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839db1c6  mov     rcx, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839db1cd  test    rcx, rcx
0x3839db1d0  jz      short loc_3839DB1F1
0x3839db1d2  mov     dword ptr [rsp+3198h+ppv], 9DFh
0x3839db1da  mov     r9d, eax
0x3839db1dd  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839db1e4  mov     edx, 277C29h
0x3839db1e9  mov     rcx, r10
0x3839db1ec  call    _bidTraceW
0x3839db1f1  mov     [rsp+3198h+var_3148], rsi
0x3839db1f6  mov     [rsp+3198h+var_3164], 9C86h
0x3839db1fe  mov     [rsp+3198h+pExceptionObject], rsi
0x3839db206  lea     rdx, _TI1_J; pThrowInfo
0x3839db20d  lea     rcx, [rsp+3198h+pExceptionObject]; pExceptionObject
0x3839db215  call    _CxxThrowException
0x3839db21a  mov     rcx, [rsp+3198h+var_3148]
0x3839db21f  mov     rax, [rcx]
0x3839db222  mov     r8, [r14+18h]
0x3839db226  mov     edx, 2
0x3839db22b  call    qword ptr [rax+28h]
0x3839db22e  mov     r9d, eax
0x3839db231  mov     [rsp+3198h+var_3168], eax
0x3839db235  cmp     eax, 80040E21h
0x3839db23a  jz      short loc_3839DB28C
0x3839db23c  cmp     eax, 40EDAh
0x3839db241  jz      short loc_3839DB28C
0x3839db243  test    eax, eax
0x3839db245  jns     loc_3839DB9DE
0x3839db24b  test    byte ptr cs:_bidGblFlags, 2
0x3839db252  jz      short loc_3839DB268
0x3839db254  mov     r8d, eax
0x3839db257  mov     edx, 293409h
0x3839db25c  mov     rcx, cs:off_383B432A8; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839db263  call    _bidTraceHR
0x3839db268  mov     [rsp+3198h+var_3164], 9C87h
0x3839db270  mov     [rsp+3198h+var_30D0], rsi
0x3839db278  lea     rdx, _TI1_J; pThrowInfo
0x3839db27f  lea     rcx, [rsp+3198h+var_30D0]; pExceptionObject
0x3839db287  call    _CxxThrowException
0x3839db28c  test    byte ptr cs:_bidGblFlags, 2
0x3839db293  jz      short loc_3839DB2DD
0x3839db295  mov     edx, 27A009h
0x3839db29a  mov     rcx, cs:off_383B432A8; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839db2a1  test    eax, eax
0x3839db2a3  jnz     short loc_3839DB2AE
0x3839db2a5  test    byte ptr cs:_bidGblFlags, 40h
0x3839db2ac  jz      short loc_3839DB2DD
0x3839db2ae  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839db2b5  test    rax, rax
0x3839db2b8  jz      short loc_3839DB2DD
0x3839db2ba  mov     eax, 27A029h
0x3839db2bf  test    r9d, r9d
0x3839db2c2  cmovs   rdx, rax
0x3839db2c6  mov     rax, rdx
0x3839db2c9  shr     rax, 0Ah
0x3839db2cd  mov     dword ptr [rsp+3198h+ppv], eax
0x3839db2d1  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839db2d8  call    _bidTraceW
0x3839db2dd  mov     [rsp+3198h+Buffer], si
0x3839db2e5  xor     edx, edx; Val
0x3839db2e7  mov     r8d, 27FAh; Size
0x3839db2ed  lea     rcx, [rsp+3198h+var_2846]; void *
0x3839db2f5  call    memset
0x3839db2fa  mov     [rsp+3198h+var_313C], 1
0x3839db302  mov     edi, 13FEh
0x3839db307  mov     r9d, edi; cchBufferMax
0x3839db30a  lea     r8, [rsp+3198h+Buffer]; lpBuffer
0x3839db312  mov     edx, 9C8Fh; uID
0x3839db317  mov     rcx, cs:?g_hinstance_language@@3PEAUHINSTANCE__@@EA; hInstance
0x3839db31e  call    cs:__imp_LoadStringW
0x3839db324  movsxd  rcx, eax
0x3839db327  lea     r12, [rsp+3198h+Buffer]
0x3839db32f  lea     r12, [r12+rcx*2]
0x3839db333  mov     [rsp+3198h+var_3160], r12
0x3839db338  sub     rdi, rcx
0x3839db33b  mov     [rsp+3198h+var_3158], rdi
0x3839db340  mov     r13d, esi
0x3839db343  cmp     r13d, 0Bh
0x3839db347  jnb     loc_3839DB8E3
0x3839db34d  mov     eax, r13d
0x3839db350  lea     rcx, [rax+rax*8]
0x3839db354  mov     r14d, [r14+rcx*8+28h]
0x3839db359  test    r14d, r14d
0x3839db35c  jz      loc_3839DB8D3
0x3839db362  mov     ecx, r13d; this
0x3839db365  call    ?GetPropDescription@CDataLinkDialog_Connect@@AEAAPEAGK@Z; CDataLinkDialog_Connect::GetPropDescription(ulong)
0x3839db36a  mov     r15, rax
0x3839db36d  test    rdi, rdi
0x3839db370  jz      loc_3839DB5BC
0x3839db376  cmp     rdi, 7FFFFFFFh
0x3839db37d  ja      loc_3839DB431
0x3839db383  mov     r11, rsi
0x3839db386  mov     [rsp+3198h+var_30E8], rsi
0x3839db38e  mov     ecx, 7FFFFFFEh
0x3839db393  lea     r8, asc_383917E10; "\""
0x3839db39a  mov     rdx, rdi
0x3839db39d  mov     r9, r12
0x3839db3a0  mov     ebx, esi
0x3839db3a2  mov     r10, rsi
0x3839db3a5  test    rdx, rdx
0x3839db3a8  jz      short loc_3839DB3CF
0x3839db3aa  test    rcx, rcx
0x3839db3ad  jz      short loc_3839DB3DB
0x3839db3af  movzx   eax, word ptr [r8]
0x3839db3b3  test    ax, ax
0x3839db3b6  jz      short loc_3839DB3DB
0x3839db3b8  mov     [r9], ax
0x3839db3bc  add     r9, 2
0x3839db3c0  add     r8, 2
0x3839db3c4  dec     rdx
0x3839db3c7  dec     rcx
0x3839db3ca  inc     r10
0x3839db3cd  jmp     short loc_3839DB3A5
0x3839db3cf  sub     r9, 2
0x3839db3d3  dec     r10
0x3839db3d6  mov     ebx, 8007007Ah
0x3839db3db  mov     [r9], si
0x3839db3df  lea     rax, [rsp+3198h+var_30E8]
0x3839db3e7  test    rax, rax
0x3839db3ea  jz      short loc_3839DB3F7
0x3839db3ec  mov     [rax], r10
0x3839db3ef  mov     r11, [rsp+3198h+var_30E8]
0x3839db3f7  lea     rcx, [r12+r11*2]
0x3839db3fb  mov     rax, rdi
0x3839db3fe  sub     rax, r11
0x3839db401  test    ebx, ebx
0x3839db403  jns     short loc_3839DB40D
0x3839db405  cmp     ebx, 8007007Ah
0x3839db40b  jnz     short loc_3839DB431
0x3839db40d  lea     rdx, [rsp+3198h+var_3160]
0x3839db412  test    rdx, rdx
0x3839db415  jz      short loc_3839DB41F
0x3839db417  mov     [rdx], rcx
0x3839db41a  mov     r12, [rsp+3198h+var_3160]
0x3839db41f  lea     rcx, [rsp+3198h+var_3158]
0x3839db424  test    rcx, rcx
0x3839db427  jz      short loc_3839DB431
0x3839db429  mov     [rcx], rax
0x3839db42c  mov     rdi, [rsp+3198h+var_3158]
0x3839db431  test    rdi, rdi
0x3839db434  jz      loc_3839DB5BC
0x3839db43a  cmp     rdi, 7FFFFFFFh
0x3839db441  ja      loc_3839DB4F1
0x3839db447  mov     r11, rsi
0x3839db44a  mov     [rsp+3198h+var_3110], rsi
0x3839db452  mov     ecx, 7FFFFFFEh
0x3839db457  mov     r8, r15
0x3839db45a  mov     rdx, rdi
0x3839db45d  mov     r9, r12
0x3839db460  mov     ebx, esi
0x3839db462  mov     r10, rsi
0x3839db465  test    rdx, rdx
0x3839db468  jz      short loc_3839DB48F
0x3839db46a  test    rcx, rcx
0x3839db46d  jz      short loc_3839DB49B
0x3839db46f  movzx   eax, word ptr [r8]
0x3839db473  test    ax, ax
0x3839db476  jz      short loc_3839DB49B
0x3839db478  mov     [r9], ax
0x3839db47c  add     r9, 2
0x3839db480  add     r8, 2
0x3839db484  dec     rdx
0x3839db487  dec     rcx
0x3839db48a  inc     r10
0x3839db48d  jmp     short loc_3839DB465
0x3839db48f  sub     r9, 2
0x3839db493  dec     r10
0x3839db496  mov     ebx, 8007007Ah
0x3839db49b  mov     [r9], si
0x3839db49f  lea     rax, [rsp+3198h+var_3110]
0x3839db4a7  test    rax, rax
0x3839db4aa  jz      short loc_3839DB4B7
0x3839db4ac  mov     [rax], r10
0x3839db4af  mov     r11, [rsp+3198h+var_3110]
0x3839db4b7  lea     rcx, [r12+r11*2]
0x3839db4bb  mov     rax, rdi
0x3839db4be  sub     rax, r11
0x3839db4c1  test    ebx, ebx
0x3839db4c3  jns     short loc_3839DB4CD
0x3839db4c5  cmp     ebx, 8007007Ah
0x3839db4cb  jnz     short loc_3839DB4F1
0x3839db4cd  lea     rdx, [rsp+3198h+var_3160]
0x3839db4d2  test    rdx, rdx
0x3839db4d5  jz      short loc_3839DB4DF
0x3839db4d7  mov     [rdx], rcx
0x3839db4da  mov     r12, [rsp+3198h+var_3160]
0x3839db4df  lea     rcx, [rsp+3198h+var_3158]
0x3839db4e4  test    rcx, rcx
0x3839db4e7  jz      short loc_3839DB4F1
0x3839db4e9  mov     [rcx], rax
0x3839db4ec  mov     rdi, [rsp+3198h+var_3158]
0x3839db4f1  test    rdi, rdi
0x3839db4f4  jz      loc_3839DB5BC
0x3839db4fa  cmp     rdi, 7FFFFFFFh
0x3839db501  ja      loc_3839DB5BC
0x3839db507  mov     r11, rsi
0x3839db50a  mov     [rsp+3198h+var_30F0], rsi
0x3839db512  mov     ecx, 7FFFFFFEh
0x3839db517  lea     r8, asc_3839DBD40; "\"\t"
0x3839db51e  mov     rdx, rdi
0x3839db521  mov     r9, r12
0x3839db524  mov     ebx, esi
0x3839db526  mov     r10, rsi
0x3839db529  nop     dword ptr [rax+00000000h]
0x3839db530  test    rdx, rdx
0x3839db533  jz      short loc_3839DB55A
0x3839db535  test    rcx, rcx
0x3839db538  jz      short loc_3839DB566
0x3839db53a  movzx   eax, word ptr [r8]
0x3839db53e  test    ax, ax
0x3839db541  jz      short loc_3839DB566
0x3839db543  mov     [r9], ax
0x3839db547  add     r9, 2
0x3839db54b  add     r8, 2
0x3839db54f  dec     rdx
0x3839db552  dec     rcx
0x3839db555  inc     r10
0x3839db558  jmp     short loc_3839DB530
0x3839db55a  sub     r9, 2
0x3839db55e  dec     r10
0x3839db561  mov     ebx, 8007007Ah
0x3839db566  mov     [r9], si
0x3839db56a  lea     rax, [rsp+3198h+var_30F0]
0x3839db572  test    rax, rax
0x3839db575  jz      short loc_3839DB582
0x3839db577  mov     [rax], r10
0x3839db57a  mov     r11, [rsp+3198h+var_30F0]
0x3839db582  lea     rcx, [r12+r11*2]
0x3839db586  mov     rax, rdi
0x3839db589  sub     rax, r11
0x3839db58c  test    ebx, ebx
0x3839db58e  jns     short loc_3839DB598
0x3839db590  cmp     ebx, 8007007Ah
0x3839db596  jnz     short loc_3839DB5BC
0x3839db598  lea     rdx, [rsp+3198h+var_3160]
0x3839db59d  test    rdx, rdx
0x3839db5a0  jz      short loc_3839DB5AA
0x3839db5a2  mov     [rdx], rcx
0x3839db5a5  mov     r12, [rsp+3198h+var_3160]
0x3839db5aa  lea     rcx, [rsp+3198h+var_3158]
  ... truncated ...
```
