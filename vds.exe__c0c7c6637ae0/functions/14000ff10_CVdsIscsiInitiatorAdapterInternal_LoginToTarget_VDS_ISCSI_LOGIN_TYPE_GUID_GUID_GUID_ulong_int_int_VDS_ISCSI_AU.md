# CVdsIscsiInitiatorAdapterInternal::LoginToTarget(_VDS_ISCSI_LOGIN_TYPE,_GUID,_GUID,_GUID,ulong,int,int,_VDS_ISCSI_AUTH_TYPE,IVdsAsync * *)

- ea: `0x14000ff10`
- end: `0x140010afb`
- name: `?LoginToTarget@CVdsIscsiInitiatorAdapterInternal@@UEAAJW4_VDS_ISCSI_LOGIN_TYPE@@U_GUID@@11KHHW4_VDS_ISCSI_AUTH_TYPE@@PEAPEAUIVdsAsync@@@Z`
- size: `3051`
- prototype: `__int64 __usercall@<rax>(CVdsIscsiInitiatorAdapterInternal *__hidden this@<rcx>, enum _VDS_ISCSI_LOGIN_TYPE@<edx>, struct _GUID *__struct_ptr@<r8>, struct _GUID *__struct_ptr@<r9>, struct _GUID *Buf2, unsigned int, int, int, enum _VDS_ISCSI_AUTH_TYPE, struct IVdsAsync **)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140006e60`
- `0x14000dd3c`
- `0x14000f98c`
- `0x14000ff10`
- `0x140011a60`
- `0x140012c48`
- `0x140012c70`
- `0x14001350c`
- `0x14001f220`
- `0x14002e123`
- `0x14003e858`
- `0x140052e46`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400104c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400104c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140010944`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140010984`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140010997`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140010944`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140010984`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140010997`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400100d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010169`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001031f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010489`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400109cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400109e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010a05`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010a1d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400100d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010169`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001031f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010489`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400109cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400109e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010a05`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010a1d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140010090`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400100ab`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140010090`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400100ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400108f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400108f5`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400108dd`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400108dd`
- `vdsutil!VdsIscsiIpAddressToString` at `0x140010383`
- `vdsutil!VdsIscsiIpAddressToString` at `0x1400107fa`
- `vdsutil!VdsIscsiIpAddressToString` at `0x140010383`
- `vdsutil!VdsIscsiIpAddressToString` at `0x1400107fa`
- `vdsutil!VdsHeapAlloc` at `0x1400100e6`
- `vdsutil!VdsHeapAlloc` at `0x140010177`
- `vdsutil!VdsHeapAlloc` at `0x140010330`
- `vdsutil!VdsHeapAlloc` at `0x140010497`
- `vdsutil!VdsHeapAlloc` at `0x1400100e6`
- `vdsutil!VdsHeapAlloc` at `0x140010177`
- `vdsutil!VdsHeapAlloc` at `0x140010330`
- `vdsutil!VdsHeapAlloc` at `0x140010497`
- `vdsutil!VdsHeapFree` at `0x1400109db`
- `vdsutil!VdsHeapFree` at `0x1400109f7`
- `vdsutil!VdsHeapFree` at `0x140010a13`
- `vdsutil!VdsHeapFree` at `0x140010a2b`
- `vdsutil!VdsHeapFree` at `0x1400109db`
- `vdsutil!VdsHeapFree` at `0x1400109f7`
- `vdsutil!VdsHeapFree` at `0x140010a13`
- `vdsutil!VdsHeapFree` at `0x140010a2b`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14001000f`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14001000f`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140010a36`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140010a36`
- `vdsutil!VdsTraceW` at `0x14001006b`
- `vdsutil!VdsTraceW` at `0x1400100fd`
- `vdsutil!VdsTraceW` at `0x14001020a`
- `vdsutil!VdsTraceW` at `0x140010348`
- `vdsutil!VdsTraceW` at `0x1400103a7`
- `vdsutil!VdsTraceW` at `0x140010468`
- `vdsutil!VdsTraceW` at `0x140010611`
- `vdsutil!VdsTraceW` at `0x14001081f`
- `vdsutil!VdsTraceW` at `0x14001085a`
- `vdsutil!VdsTraceW` at `0x14001088d`
- `vdsutil!VdsTraceW` at `0x140010931`
- `vdsutil!VdsTraceW` at `0x14001096d`
- `vdsutil!VdsTraceW` at `0x14001006b`
- `vdsutil!VdsTraceW` at `0x1400100fd`
- `vdsutil!VdsTraceW` at `0x14001020a`
- `vdsutil!VdsTraceW` at `0x140010348`
- `vdsutil!VdsTraceW` at `0x1400103a7`
- `vdsutil!VdsTraceW` at `0x140010468`
- `vdsutil!VdsTraceW` at `0x140010611`
- `vdsutil!VdsTraceW` at `0x14001081f`
- `vdsutil!VdsTraceW` at `0x14001085a`
- `vdsutil!VdsTraceW` at `0x14001088d`
- `vdsutil!VdsTraceW` at `0x140010931`
- `vdsutil!VdsTraceW` at `0x14001096d`

## string_xrefs

- `0x140010964`: `CVdsIscsiInitiatorAdapterInternal::LoginToTarget: Could not access necessary functions in iSCSI library.`
- `0x140010884`: `CVdsIscsiInitiatorAdapterInternal::LoginToTarget: spAsync CreateInstance: Out of memory.`
- `0x1400108fe`: `CVdsIscsiInitiatorAdapterInternal::LoginToTarget: CreateThread failed: %X`

## pseudocode

```c
// Hidden C++ exception states: #wind=28
__int64 __fastcall CVdsIscsiInitiatorAdapterInternal::LoginToTarget(
        CVdsIscsiInitiatorAdapterInternal *this,
        enum _VDS_ISCSI_LOGIN_TYPE a2,
        struct _GUID *a3,
        struct _GUID *a4,
        struct _GUID *Buf2,
        unsigned int a6,
        int a7,
        int a8,
        enum _VDS_ISCSI_AUTH_TYPE a9,
        struct IVdsAsync **a10)
{
  _QWORD *v13; // rsi
  int v14; // edi
  FARPROC v15; // rax
  HANDLE ProcessHeap; // rax
  __int64 v17; // r14
  __int64 v18; // rax
  unsigned __int64 v19; // r15
  HANDLE v20; // rax
  unsigned __int16 *v21; // rax
  int InitiatorPortal; // eax
  int v23; // eax
  int v24; // eax
  int ObjectFromProviders; // eax
  int v26; // eax
  HANDLE v27; // rax
  _WORD *v28; // rax
  int v29; // eax
  int v30; // eax
  int v31; // eax
  unsigned __int64 v32; // r14
  HANDLE v33; // rax
  unsigned __int16 *v34; // rax
  _DWORD *v35; // rax
  _DWORD *v36; // r14
  int v37; // eax
  __int64 v38; // r9
  _OWORD *v39; // rax
  _OWORD *v40; // rcx
  __int64 v41; // rdx
  __int64 (__fastcall *v42)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD); // rdi
  int v43; // r8d
  __int64 v44; // r9
  int v45; // eax
  __int64 (__fastcall ***v46)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v47; // rdx
  int v48; // eax
  int v49; // eax
  __int64 v50; // rcx
  int v51; // eax
  _DWORD *v52; // rbx
  HANDLE Thread; // rax
  __int64 v54; // rcx
  __int64 v55; // rbx
  HANDLE v56; // rax
  __int64 v57; // rbx
  HANDLE v58; // rax
  __int64 v59; // rbx
  HANDLE v60; // rax
  HANDLE v61; // rax
  __int64 v63; // [rsp+40h] [rbp-C0h] BYREF
  int v64; // [rsp+48h] [rbp-B8h] BYREF
  int v65; // [rsp+4Ch] [rbp-B4h] BYREF
  __int64 (__fastcall ***v66)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-B0h] BYREF
  __int64 (__fastcall ***v67)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp-A8h] BYREF
  __int64 v68; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v69; // [rsp+68h] [rbp-98h] BYREF
  __int64 v70; // [rsp+70h] [rbp-90h] BYREF
  __int64 v71; // [rsp+78h] [rbp-88h] BYREF
  struct IUnknown *v72; // [rsp+80h] [rbp-80h] BYREF
  __int64 v73; // [rsp+88h] [rbp-78h] BYREF
  struct IUnknown *v74; // [rsp+90h] [rbp-70h] BYREF
  __int64 v75; // [rsp+98h] [rbp-68h] BYREF
  struct IUnknown *v76; // [rsp+A0h] [rbp-60h] BYREF
  void *v77; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v78[2]; // [rsp+B0h] [rbp-50h] BYREF
  struct _GUID v79; // [rsp+C0h] [rbp-40h] BYREF
  struct _GUID *v80; // [rsp+D0h] [rbp-30h]
  FARPROC ProcAddress; // [rsp+D8h] [rbp-28h]
  struct IVdsAsync **v82; // [rsp+E0h] [rbp-20h]
  _BYTE v83[24]; // [rsp+E8h] [rbp-18h] BYREF
  _DWORD v84[16]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v85; // [rsp+140h] [rbp+40h] BYREF
  LPVOID pv[2]; // [rsp+150h] [rbp+50h]
  __int64 v87; // [rsp+160h] [rbp+60h]
  _BYTE v88[16]; // [rsp+170h] [rbp+70h] BYREF
  char v89[548]; // [rsp+180h] [rbp+80h] BYREF
  __int16 v90; // [rsp+3A4h] [rbp+2A4h]
  _BYTE v91[568]; // [rsp+3B0h] [rbp+2B0h] BYREF
  int v92; // [rsp+5E8h] [rbp+4E8h]
  _BYTE v93[16]; // [rsp+5F0h] [rbp+4F0h] BYREF
  char v94[548]; // [rsp+600h] [rbp+500h] BYREF
  __int16 v95; // [rsp+824h] [rbp+724h]

  v80 = a3;
  v82 = a10;
  memset_0(v84, 0, sizeof(v84));
  v78[0] = 0;
  v13 = 0;
  v77 = 0;
  v76 = 0;
  v75 = 0;
  memset_0(v91, 0, 0x23Cu);
  v74 = 0;
  v73 = 0;
  memset_0(v93, 0, 0x23Cu);
  v64 = 0;
  v65 = 0;
  v71 = 0;
  v68 = 0;
  v72 = 0;
  v67 = 0;
  v66 = 0;
  v70 = 0;
  v63 = 0;
  v69 = 0;
  v85 = 0;
  *(_OWORD *)pv = 0;
  v87 = 0;
  memset_0(v88, 0, 0x23Cu);
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v83, 0x5Eu, "CVdsIscsiInitiatorAdapterInternal::LoginToTarget()");
  memset_0(v84, 0, sizeof(v84));
  memset_0(v91, 0, 0x23Cu);
  v85 = 0;
  *(_OWORD *)pv = 0;
  v87 = 0;
  memset_0(v88, 0, 0x23Cu);
  if ( !a10 )
  {
    v14 = -2147024809;
    VdsTraceW(0, L"CVdsIscsiInitiatorAdapterInternal::LoginToTarget: NULL input arguments");
    goto LABEL_106;
  }
  *a10 = 0;
  if ( !CVdsService::m_hIscsidscModule
    || (ProcAddress = GetProcAddress(CVdsService::m_hIscsidscModule, "AddIScsiStaticTargetW"),
        v15 = GetProcAddress(CVdsService::m_hIscsidscModule, "LoginIScsiTargetW"),
        !ProcAddress)
    || !v15 )
  {
    VdsTraceW(
      0,
      L"CVdsIscsiInitiatorAdapterInternal::LoginToTarget: Could not access necessary functions in iSCSI library.");
    v14 = -2147212288;
    goto LABEL_106;
  }
  v84[0] = 0;
  v84[1] = 128;
  v84[3] = a9;
  ProcessHeap = GetProcessHeap();
  v13 = (_QWORD *)VdsHeapAlloc(ProcessHeap, 0, 112);
  if ( !v13 )
  {
    VdsTraceW(0, L"CVdsIscsiInitiatorAdapterInternal::LoginToTarget: pLoginParam Alloc: Out of memory.");
LABEL_8:
    v14 = -2147024882;
    goto LABEL_106;
  }
  v17 = -1;
  v18 = -1;
  do
    ++v18;
  while ( *(_WORD *)(*((_QWORD *)this + 10) + 2 * v18) );
  v19 = v18 + 1;
  memset_0(v13, 0, 0x70u);
  *((_DWORD *)v13 + 2) = a2;
  *((_DWORD *)v13 + 5) = 3;
  *((_DWORD *)v13 + 6) = a6;
  *((_DWORD *)v13 + 8) = a7 != 0;
  *((_DWORD *)v13 + 9) = a8 != 0;
  v20 = GetProcessHeap();
  v21 = (unsigned __int16 *)VdsHeapAlloc(v20, 0, 2 * v19);
  v13[10] = v21;
  if ( !v21 )
  {
    VdsTraceW(
      0,
      L"CVdsIscsiInitiatorAdapterInternal::LoginToTarget: pLoginParam->pwszInitiatorName Alloc: Out of memory.");
    goto LABEL_8;
  }
  StringCchCopyW(v21, v19, *((const unsigned __int16 **)this + 10));
  *((_DWORD *)v13 + 22) = -1;
  if ( memcmp_0(&GUID_NULL, Buf2, 0x10u) )
  {
    v79 = *Buf2;
    InitiatorPortal = CVdsIscsiInitiatorAdapterInternal::GetInitiatorPortal(this, &v79, &v76);
    v14 = InitiatorPortal;
    if ( InitiatorPortal == -2147212283 )
    {
LABEL_15:
      v14 = -2147024809;
      goto LABEL_106;
    }
    if ( InitiatorPortal < 0 )
    {
      VdsTraceW(
        0,
        L"CVdsIscsiInitiatorAdapterInternal::LoginToTarget: GetInitiatorPortal: %X",
        (unsigned int)InitiatorPortal);
      goto LABEL_106;
    }
    v23 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v76->lpVtbl->QueryInterface)(
            v76,
            &IID_IVdsIscsiInitiatorPortal,
            &v75);
    v14 = v23;
    if ( v23 < 0 )
    {
      VdsTraceW(
        0,
        L"CVdsIscsiInitiatorAdapterInternal::LoginToTarget: spInitPortalUnk->QueryInterface IID_IVdsIscsiInitiatorPortal: %X",
        (unsigned int)v23);
      goto LABEL_106;
    }
    v24 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v75 + 24LL))(v75, v91);
    v14 = v24;
    if ( v24 < 0 )
    {
      VdsTraceW(
        0,
        L"CVdsIscsiInitiatorAdapterInternal::LoginToTarget: spInitPortal->GetProperties: %X",
        (unsigned int)v24);
      goto LABEL_106;
    }
    *((_DWORD *)v13 + 22) = v92;
  }
  if ( !memcmp_0(&GUID_NULL, a4, 0x10u) )
    goto LABEL_40;
  v79 = *a4;
  ObjectFromProviders = CVdsService::GetObjectFromProviders(&v79, VDS_OT_PORTAL, &v74);
  v14 = ObjectFromProviders;
  if ( ObjectFromProviders == -2147212283 )
    goto LABEL_15;
  if ( ObjectFromProviders >= 0 && v74 )
  {
    v14 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v74->lpVtbl->QueryInterface)(
            v74,
            &IID_IVdsIscsiPortal,
            &v73);
    if ( v14 >= 0 && v73 )
    {
      v26 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v73 + 24LL))(v73, v93);
      v14 = v26;
      if ( v26 < 0 )
      {
        VdsTraceW(
          0,
          L"CVdsIscsiInitiatorAdapterInternal::LoginToTarget: spTargetPortal->GetProperties: %X",
          (unsigned int)v26);
        goto LABEL_106;
      }
      v27 = GetProcessHeap();
      v28 = (_WORD *)VdsHeapAlloc(v27, 0, 1026);
      v13[13] = v28;
      if ( !v28 )
      {
        VdsTraceW(
          0,
          L"CVdsIscsiInitiatorAdapterInternal::LoginToTarget: pLoginParam->pIscsiTargetPortal Alloc: Out of memory.");
LABEL_33:
        v14 = -2147024882;
        goto LABEL_106;
      }
      *v28 = 0;
      *(_WORD *)(v13[13] + 1024LL) = v95;
      v29 = VdsIscsiIpAddressToString(v94, 256, v13[13] + 512LL);
      v14 = v29;
      if ( v29 < 0 )
      {
        VdsTraceW(
          0,
          L"CVdsIscsiInitiatorAdapterInternal::LoginToTarget: VdsIscsiIpAddressToString &vdsTargetPortalProp.address: %X",
          (unsigned int)v29);
        goto LABEL_106;
      }
LABEL_40:
      v79 = *v80;
      v30 = CVdsService::GetObjectFromProviders(&v79, VDS_OT_TARGET, &v72);
      v14 = v30;
      if ( v30 == -2147212283 )
        goto LABEL_15;
      if ( v30 >= 0 && v72 )
      {
        v14 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v72->lpVtbl->QueryInterface)(
                v72,
                &IID_IVdsIscsiTarget,
                &v70);
        if ( v14 >= 0 && v70 )
        {
          v31 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v70 + 24LL))(v70, &v85);
          v14 = v31;
          if ( v31 < 0 )
          {
            VdsTraceW(
              0,
              L"CVdsIscsiInitiatorAdapterInternal::LoginToTarget: spTarget->GetProperties: %X",
              (unsigned int)v31);
            goto LABEL_106;
          }
          if ( !pv[0] )
          {
            VdsTraceW(
              0,
              L"CVdsIscsiInitiatorAdapterInternal::LoginToTarget: Invalid target iSCSI name retrieved from provider.");
            v14 = -2147211005;
            goto LABEL_106;
          }
          do
            ++v17;
          while ( *((_WORD *)pv[0] + v17) );
          v32 = v17 + 1;
          v33 = GetProcessHeap();
          v34 = (unsigned __int16 *)VdsHeapAlloc(v33, 0, 2 * v32);
          v13[12] = v34;
          if ( !v34 )
          {
            VdsTraceW(
              0,
              L"CVdsIscsiInitiatorAdapterInternal::LoginToTarget: pLoginParam->pwszTargetName Alloc: Out of memory.");
            goto LABEL_33;
          }
          StringCchCopyW(v34, v32, (const unsigned __int16 *)pv[0]);
          v35 = CoTaskMemAlloc(0x2C1Cu);
          v36 = v35;
          if ( !v35 )
          {
            VdsTraceW(
              0,
              L"CVdsIscsiInitiatorAdapterInternal::LoginToTarget: pIscsiTargetPortalGroup Alloc: Out of memory.");
            goto LABEL_33;
          }
          *v35 = 0;
          v37 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v70 + 40LL))(v70, &v71);
          v14 = v37;
          if ( v37 < 0 || !v71 )
          {
            VdsTraceW(
              0,
              L"CVdsIscsiInitiatorAdapterInternal::LoginToTarget: spTarget->QueryPortalGroups: %X",
              (unsigned int)v37);
            if ( v14 >= 0 )
              v14 = -2147467259;
            goto LABEL_102;
          }
          if ( !v13[13] )
          {
            while ( 1 )
            {
              if ( v14 < 0 )
                goto LABEL_60;
              if ( *v36 )
                goto LABEL_60;
              v64 = 0;
              ATL::CComPtrBase<IVdsIscsiPortal>::Release(&v67);
              v45 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *), int *))(*(_QWORD *)v71 + 24LL))(
                      v71,
                      1,
                      &v67,
                      &v64);
              v14 = v45;
              if ( v45 == 1 )
                goto LABEL_60;
              if ( v45 < 0 )
                break;
              v46 = v67;
              if ( !v67 )
                break;
              v47 = v63;
              if ( v63 )
              {
                v63 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
                v46 = v67;
              }
              v14 = (**v46)(v46, &IID_IVdsIscsiPortalGroup, &v63);
              if ( v14 < 0 || !v63 )
              {
                VdsTraceW(
                  0,
                  L"CVdsIscsiInitiatorAdapterInternal::LoginToTarget: spPortalGroupUnk->QueryInterface IID_IVdsIscsiPortalGroup: %X",
                  (unsigned int)v14);
                goto LABEL_93;
              }
              ATL::CComPtrBase<IVdsIscsiPortal>::Release(&v68);
              v14 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v63 + 40LL))(v63, &v68);
              if ( v14 < 0 || !v68 )
              {
                VdsTraceW(
                  0,
                  L"CVdsIscsiInitiatorAdapterInternal::LoginToTarget: spPortalGroup->QueryAssociatedPortals: %X",
                  (unsigned int)v14);
                goto LABEL_93;
              }
              while ( !*v36 )
              {
                v65 = 0;
                ATL::CComPtrBase<IVdsIscsiPortal>::Release(&v66);
                v48 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *), int *))(*(_QWORD *)v68 + 24LL))(
                        v68,
                        1,
                        &v66,
                        &v65);
                v14 = v48;
                if ( v48 == 1 )
                  break;
                if ( v48 < 0 || !v66 )
                {
                  VdsTraceW(
                    0,
                    L"CVdsIscsiInitiatorAdapterInternal::LoginToTarget: spEnumPortal->Next: %X",
                    (unsigned int)v48);
                  goto LABEL_93;
                }
                ATL::CComPtrBase<IVdsIscsiPortal>::Release(&v69);
                v14 = (**v66)(v66, &IID_IVdsIscsiPortal, &v69);
                if ( v14 < 0 || !v69 )
                {
                  VdsTraceW(
                    0,
                    L"CVdsIscsiInitiatorAdapterInternal::LoginToTarget: spPortalUnk->QueryInterface IID_IVdsIscsiPortal: %X",
                    (unsigned int)v14);
                  goto LABEL_93;
                }
                v49 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v69 + 24LL))(v69, v88);
                v14 = v49;
                if ( v49 < 0 )
                {
                  VdsTraceW(
                    0,
                    L"CVdsIscsiInitiatorAdapterInternal::LoginToTarget: spPortal->GetProperties: %X",
                    (unsigned int)v49);
                  goto LABEL_102;
                }
                v50 = (unsigned int)*v36;
                *v36 = v50 + 1;
                *((_WORD *)v36 + 513 * v50 + 2) = 0;
                *((_WORD *)v36 + 513 * (unsigned int)(*v36 - 1) + 514) = v90;
                v51 = VdsIscsiIpAddressToString(v89, 256, (char *)v36 + 1026 * (unsigned int)(*v36 - 1) + 516);
                v14 = v51;
                if ( v51 < 0 )
                {
                  VdsTraceW(
                    0,
                    L"CVdsIscsiInitiatorAdapterInternal::LoginToTarget: VdsIscsiIpAddressToString &vdsPortalProp.address: %X",
                    (unsigned int)v51);
                  goto LABEL_102;
                }
              }
            }
            VdsTraceW(
              0,
              L"CVdsIscsiInitiatorAdapterInternal::LoginToTarget: spEnumPortalGroup->Next: %X",
              (unsigned int)v45);
LABEL_93:
            if ( v14 >= 0 )
              v14 = -2147467259;
            goto LABEL_102;
          }
          *v36 = 1;
          v39 = (_OWORD *)v13[13];
          v40 = v36 + 1;
          v41 = 8;
          do
          {
            *v40 = *v39;
            v40[1] = v39[1];
            v40[2] = v39[2];
            v40[3] = v39[3];
            v40[4] = v39[4];
            v40[5] = v39[5];
            v40[6] = v39[6];
            v40[7] = v39[7];
            v40 += 8;
            v39 += 8;
            --v41;
          }
          while ( v41 );
          *(_WORD *)v40 = *(_WORD *)v39;
LABEL_60:
          LOBYTE(v38) = 1;
          v42 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))ProcAddress;
          v43 = ((__int64 (__fastcall *)(LPVOID, LPVOID, __int64, __int64, _QWORD, _DWORD *, _DWORD *))ProcAddress)(
                  pv[0],
                  pv[1],
                  4,
                  v38,
                  0,
                  v84,
                  v36);
          if ( v43 == -268500951 )
          {
            LOBYTE(v44) = 1;
            v43 = v42(pv[0], pv[1], 0, v44, 0, v84, v36);
          }
          if ( v43 && ((v43 & 0xFFF0000) == 0 || (v43 & 0xC0000000) == 0xC0000000) )
          {
            VdsTraceW(0, L"CVdsIscsiInitiatorAdapterInternal::LoginToTarget: AddIScsiStaticTarget failed: %X");
          }
          else
          {
            ATL::CComObject<CVdsServiceAsyncObject>::CreateInstance(v78);
            v52 = (_DWORD *)v78[0];
            if ( !v78[0] )
            {
              VdsTraceW(0, L"CVdsIscsiInitiatorAdapterInternal::LoginToTarget: spAsync CreateInstance: Out of memory.");
              v14 = -2147024882;
              goto LABEL_102;
            }
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v78[0] + 8LL))(v78[0]);
            v52[20] = 60;
            *v13 = v52;
            (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v52 + 8LL))(v52);
            Thread = CreateThread(0, 0, CVdsIscsiInitiatorAdapterInternal::LoginToTargetThread, v13, 0, 0);
            CVdsHandleImpl<0>::operator=(&v77, Thread);
            if ( v77 )
            {
              v54 = *v13;
              *v82 = (struct IVdsAsync *)*v13;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 8LL))(v54);
              v14 = 0;
              goto LABEL_102;
            }
            GetLastError();
            VdsTraceW(0, L"CVdsIscsiInitiatorAdapterInternal::LoginToTarget: CreateThread failed: %X");
          }
          v14 = -2147211512;
LABEL_102:
          CoTaskMemFree(v36);
          goto LABEL_106;
        }
        VdsTraceW(
          0,
          L"CVdsIscsiInitiatorAdapterInternal::LoginToTarget: spTargetUnk->QueryInterface IID_IVdsIscsiTarget: %X",
          (unsigned int)v14);
      }
      else
      {
        VdsTraceW(
          0,
          L"CVdsIscsiInitiatorAdapterInternal::LoginToTarget: Could not retrieve target object from provider: %X",
          (unsigned int)v30);
      }
      goto LABEL_37;
    }
    VdsTraceW(
      0,
      L"CVdsIscsiInitiatorAdapterInternal::LoginToTarget: spTargetPortalUnk->QueryInterface IID_IVdsIscsiPortal: %X",
      (unsigned int)v14);
  }
  else
  {
    VdsTraceW(
      0,
      L"CVdsIscsiInitiatorAdapterInternal::LoginToTarget: Could not retrieve target portal object from provider: %X",
      (unsigned int)ObjectFromProviders);
  }
LABEL_37:
  if ( v14 >= 0 )
    v14 = -2147467259;
LABEL_106:
  if ( pv[0] )
  {
    CoTaskMemFree(pv[0]);
    pv[0] = 0;
  }
  if ( pv[1] )
  {
    CoTaskMemFree(pv[1]);
    pv[1] = 0;
  }
  if ( v14 < 0 && v13 )
  {
    if ( *v13 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v13 + 16LL))(*v13);
      *v13 = 0;
    }
    v55 = v13[10];
    v56 = GetProcessHeap();
    VdsHeapFree(v56, 0, v55);
    v13[10] = 0;
    v57 = v13[12];
    v58 = GetProcessHeap();
    VdsHeapFree(v58, 0, v57);
    v13[12] = 0;
    v59 = v13[13];
    v60 = GetProcessHeap();
    VdsHeapFree(v60, 0, v59);
    v13[13] = 0;
    v61 = GetProcessHeap();
    VdsHeapFree(v61, 0, v13);
  }
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v83);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v69);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v63);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v70);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v66);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v67);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v72);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v68);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v71);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v73);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v74);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v75);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v76);
  CVdsHandleImpl<0>::~CVdsHandleImpl<0>(&v77);
  ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(v78);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x14000ff10  mov     [rsp-8+arg_8], rbx
0x14000ff15  push    rbp
0x14000ff16  push    rsi
0x14000ff17  push    rdi
0x14000ff18  push    r12
0x14000ff1a  push    r13
0x14000ff1c  push    r14
0x14000ff1e  push    r15
0x14000ff20  lea     rbp, [rsp-740h]
0x14000ff28  sub     rsp, 840h
0x14000ff2f  mov     rax, cs:__security_cookie
0x14000ff36  xor     rax, rsp
0x14000ff39  mov     [rbp+770h+var_40], rax
0x14000ff40  mov     r13, r9
0x14000ff43  mov     [rbp+770h+var_7A0], r8
0x14000ff47  mov     ebx, edx
0x14000ff49  mov     rdi, rcx
0x14000ff4c  mov     r12, [rbp+770h+Buf2]
0x14000ff53  mov     r14, [rbp+770h+arg_48]
0x14000ff5a  mov     [rbp+770h+var_790], r14
0x14000ff5e  xor     edx, edx; Val
0x14000ff60  lea     r8d, [rdx+40h]; Size
0x14000ff64  lea     rcx, [rbp+770h+var_770]; void *
0x14000ff68  call    memset_0
0x14000ff6d  xor     eax, eax
0x14000ff6f  mov     [rbp+770h+var_7C0], rax
0x14000ff73  mov     esi, eax
0x14000ff75  mov     [rbp+770h+var_7C8], rax
0x14000ff79  mov     [rbp+770h+var_7D0], rax
0x14000ff7d  mov     [rbp+770h+var_7D8], rax
0x14000ff81  mov     r15d, 23Ch
0x14000ff87  mov     r8d, r15d; Size
0x14000ff8a  xor     edx, edx; Val
0x14000ff8c  lea     rcx, [rbp+770h+var_4C0]; void *
0x14000ff93  call    memset_0
0x14000ff98  xor     eax, eax
0x14000ff9a  mov     [rbp+770h+var_7E0], rax
0x14000ff9e  mov     [rbp+770h+var_7E8], rax
0x14000ffa2  mov     r8d, r15d; Size
0x14000ffa5  xor     edx, edx; Val
0x14000ffa7  lea     rcx, [rbp+770h+var_280]; void *
0x14000ffae  call    memset_0
0x14000ffb3  xor     eax, eax
0x14000ffb5  mov     [rsp+870h+var_828], eax
0x14000ffb9  mov     [rsp+870h+var_824], eax
0x14000ffbd  mov     [rsp+870h+var_7F8], rax
0x14000ffc2  mov     [rsp+870h+var_810], rax
0x14000ffc7  mov     [rbp+770h+var_7F0], rax
0x14000ffcb  mov     [rsp+870h+var_818], rax
0x14000ffd0  mov     [rsp+870h+var_820], rax
0x14000ffd5  mov     [rsp+870h+var_800], rax
0x14000ffda  mov     [rsp+870h+var_830], rax
0x14000ffdf  mov     [rsp+870h+var_808], rax
0x14000ffe4  xorps   xmm0, xmm0
0x14000ffe7  movups  [rbp+770h+var_730], xmm0
0x14000ffeb  movups  xmmword ptr [rbp+770h+pv], xmm0
0x14000ffef  mov     [rbp+770h+var_710], rax
0x14000fff3  mov     r8d, r15d; Size
0x14000fff6  xor     edx, edx; Val
0x14000fff8  lea     rcx, [rbp+770h+var_700]; void *
0x14000fffc  call    memset_0
0x140010001  lea     r8, aCvdsiscsiiniti_122; "CVdsIscsiInitiatorAdapterInternal::Logi"...
0x140010008  lea     edx, [rsi+5Eh]
0x14001000b  lea     rcx, [rbp+770h+var_788]
0x14001000f  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140010015  nop
0x140010016  xor     edx, edx; Val
0x140010018  lea     r8d, [rsi+40h]; Size
0x14001001c  lea     rcx, [rbp+770h+var_770]; void *
0x140010020  call    memset_0
0x140010025  mov     r8d, r15d; Size
0x140010028  xor     edx, edx; Val
0x14001002a  lea     rcx, [rbp+770h+var_4C0]; void *
0x140010031  call    memset_0
0x140010036  xorps   xmm0, xmm0
0x140010039  xor     eax, eax
0x14001003b  movups  [rbp+770h+var_730], xmm0
0x14001003f  movups  xmmword ptr [rbp+770h+pv], xmm0
0x140010043  mov     [rbp+770h+var_710], rax
0x140010047  mov     r8d, r15d; Size
0x14001004a  xor     edx, edx; Val
0x14001004c  lea     rcx, [rbp+770h+var_700]; void *
0x140010050  call    memset_0
0x140010055  xor     r15d, r15d
0x140010058  test    r14, r14
0x14001005b  jnz     short loc_140010076
0x14001005d  mov     edi, 80070057h
0x140010062  lea     rdx, aCvdsiscsiiniti_140; "CVdsIscsiInitiatorAdapterInternal::Logi"...
0x140010069  xor     ecx, ecx
0x14001006b  call    cs:__imp_VdsTraceW
0x140010071  jmp     loc_140010978
0x140010076  mov     [r14], r15
0x140010079  mov     rcx, cs:?m_hIscsidscModule@CVdsService@@2PEAUHINSTANCE__@@EA; hModule
0x140010080  test    rcx, rcx
0x140010083  jz      loc_140010964
0x140010089  lea     rdx, aAddiscsistatic; "AddIScsiStaticTargetW"
0x140010090  call    cs:__imp_GetProcAddress
0x140010096  mov     r14, rax
0x140010099  mov     [rbp+770h+var_798], rax
0x14001009d  lea     rdx, aLoginiscsitarg; "LoginIScsiTargetW"
0x1400100a4  mov     rcx, cs:?m_hIscsidscModule@CVdsService@@2PEAUHINSTANCE__@@EA; hModule
0x1400100ab  call    cs:__imp_GetProcAddress
0x1400100b1  test    r14, r14
0x1400100b4  jz      loc_140010964
0x1400100ba  test    rax, rax
0x1400100bd  jz      loc_140010964
0x1400100c3  mov     [rbp+770h+var_770], r15d
0x1400100c7  mov     [rbp+770h+var_76C], 80h
0x1400100ce  mov     eax, [rbp+770h+arg_40]
0x1400100d4  mov     [rbp+770h+var_764], eax
0x1400100d7  call    cs:__imp_GetProcessHeap
0x1400100dd  mov     rcx, rax
0x1400100e0  xor     edx, edx
0x1400100e2  lea     r8d, [rdx+70h]
0x1400100e6  call    cs:__imp_VdsHeapAlloc
0x1400100ec  mov     rsi, rax
0x1400100ef  test    rax, rax
0x1400100f2  jnz     short loc_14001010D
0x1400100f4  lea     rdx, aCvdsiscsiiniti_75; "CVdsIscsiInitiatorAdapterInternal::Logi"...
0x1400100fb  xor     ecx, ecx
0x1400100fd  call    cs:__imp_VdsTraceW
0x140010103  mov     edi, 8007000Eh
0x140010108  jmp     loc_140010978
0x14001010d  mov     rcx, [rdi+50h]
0x140010111  or      r14, 0FFFFFFFFFFFFFFFFh
0x140010115  mov     rax, r14
0x140010118  inc     rax
0x14001011b  cmp     [rcx+rax*2], r15w
0x140010120  jnz     short loc_140010118
0x140010122  lea     r15, [rax+1]
0x140010126  xor     edx, edx; Val
0x140010128  lea     r8d, [rdx+70h]; Size
0x14001012c  mov     rcx, rsi; void *
0x14001012f  call    memset_0
0x140010134  mov     [rsi+8], ebx
0x140010137  mov     dword ptr [rsi+14h], 3
0x14001013e  mov     eax, [rbp+770h+arg_28]
0x140010144  mov     [rsi+18h], eax
0x140010147  xor     ecx, ecx
0x140010149  mov     eax, ecx
0x14001014b  cmp     [rbp+770h+arg_30], ecx
0x140010151  setnz   al
0x140010154  mov     [rsi+20h], eax
0x140010157  mov     eax, ecx
0x140010159  cmp     [rbp+770h+arg_38], ecx
0x14001015f  setnz   al
0x140010162  mov     [rsi+24h], eax
0x140010165  lea     rbx, [r15+r15]
0x140010169  call    cs:__imp_GetProcessHeap
0x14001016f  mov     rcx, rax
0x140010172  mov     r8, rbx
0x140010175  xor     edx, edx
0x140010177  call    cs:__imp_VdsHeapAlloc
0x14001017d  mov     [rsi+50h], rax
0x140010181  test    rax, rax
0x140010184  jnz     short loc_140010192
0x140010186  lea     rdx, aCvdsiscsiiniti_77; "CVdsIscsiInitiatorAdapterInternal::Logi"...
0x14001018d  jmp     loc_1400100FB
0x140010192  mov     r8, [rdi+50h]; unsigned __int16 *
0x140010196  mov     rdx, r15; unsigned __int64
0x140010199  mov     rcx, rax; unsigned __int16 *
0x14001019c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400101a1  mov     dword ptr [rsi+58h], 0FFFFFFFFh
0x1400101a8  mov     r15d, 10h
0x1400101ae  mov     r8d, r15d; Size
0x1400101b1  mov     rdx, r12; Buf2
0x1400101b4  lea     rcx, GUID_NULL; Buf1
0x1400101bb  call    memcmp_0
0x1400101c0  mov     ebx, 80042405h
0x1400101c5  test    eax, eax
0x1400101c7  jz      loc_14001026F
0x1400101cd  movups  xmm0, xmmword ptr [r12]
0x1400101d2  movdqu  xmmword ptr [rbp+770h+var_7B0.Data1], xmm0
0x1400101d7  lea     r8, [rbp+770h+var_7D0]; struct IUnknown **
0x1400101db  lea     rdx, [rbp+770h+var_7B0]; struct _GUID
0x1400101df  mov     rcx, rdi; this
0x1400101e2  call    ?GetInitiatorPortal@CVdsIscsiInitiatorAdapterInternal@@QEAAJU_GUID@@PEAPEAUIUnknown@@@Z; CVdsIscsiInitiatorAdapterInternal::GetInitiatorPortal(_GUID,IUnknown * *)
0x1400101e7  mov     edi, eax
0x1400101e9  xor     r12d, r12d
0x1400101ec  cmp     eax, ebx
0x1400101ee  jnz     short loc_1400101FA
0x1400101f0  mov     edi, 80070057h
0x1400101f5  jmp     loc_14001097B
0x1400101fa  test    eax, eax
0x1400101fc  jns     short loc_140010215
0x1400101fe  lea     rdx, aCvdsiscsiiniti_117; "CVdsIscsiInitiatorAdapterInternal::Logi"...
0x140010205  mov     r8d, eax
0x140010208  xor     ecx, ecx
0x14001020a  call    cs:__imp_VdsTraceW
0x140010210  jmp     loc_14001097B
0x140010215  mov     rcx, [rbp+770h+var_7D0]
0x140010219  mov     rax, [rcx]
0x14001021c  lea     r8, [rbp+770h+var_7D8]
0x140010220  lea     rdx, IID_IVdsIscsiInitiatorPortal
0x140010227  mov     rax, [rax]
0x14001022a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001022f  mov     edi, eax
0x140010231  test    eax, eax
0x140010233  jns     short loc_14001023E
0x140010235  lea     rdx, aCvdsiscsiiniti_25; "CVdsIscsiInitiatorAdapterInternal::Logi"...
0x14001023c  jmp     short loc_140010205
0x14001023e  mov     rcx, [rbp+770h+var_7D8]
0x140010242  mov     rax, [rcx]
0x140010245  lea     rdx, [rbp+770h+var_4C0]
0x14001024c  mov     rax, [rax+18h]
0x140010250  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010255  mov     edi, eax
0x140010257  test    eax, eax
0x140010259  jns     short loc_140010264
0x14001025b  lea     rdx, aCvdsiscsiiniti_28; "CVdsIscsiInitiatorAdapterInternal::Logi"...
0x140010262  jmp     short loc_140010205
0x140010264  mov     eax, [rbp+770h+var_288]
0x14001026a  mov     [rsi+58h], eax
0x14001026d  jmp     short loc_140010272
0x14001026f  xor     r12d, r12d
0x140010272  mov     r8, r15; Size
0x140010275  mov     rdx, r13; Buf2
0x140010278  lea     rcx, GUID_NULL; Buf1
0x14001027f  call    memcmp_0
0x140010284  mov     r15d, 100h
0x14001028a  test    eax, eax
0x14001028c  jz      loc_1400103C8
0x140010292  movups  xmm0, xmmword ptr [r13+0]
0x140010297  movdqu  xmmword ptr [rbp+770h+var_7B0.Data1], xmm0
0x14001029c  lea     r8, [rbp+770h+var_7E0]; struct IUnknown **
0x1400102a0  mov     edx, 24h ; '$'; enum _VDS_OBJECT_TYPE
0x1400102a5  lea     rcx, [rbp+770h+var_7B0]; struct _GUID
0x1400102a9  call    ?GetObjectFromProviders@CVdsService@@SAJU_GUID@@W4_VDS_OBJECT_TYPE@@PEAPEAUIUnknown@@@Z; CVdsService::GetObjectFromProviders(_GUID,_VDS_OBJECT_TYPE,IUnknown * *)
0x1400102ae  mov     edi, eax
0x1400102b0  cmp     eax, ebx
0x1400102b2  jz      loc_1400101F0
0x1400102b8  test    eax, eax
0x1400102ba  js      loc_1400103BF
0x1400102c0  mov     rcx, [rbp+770h+var_7E0]
0x1400102c4  test    rcx, rcx
0x1400102c7  jz      loc_1400103BF
0x1400102cd  mov     rax, [rcx]
0x1400102d0  lea     r8, [rbp+770h+var_7E8]
0x1400102d4  lea     rdx, IID_IVdsIscsiPortal
0x1400102db  mov     rax, [rax]
0x1400102de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400102e3  mov     edi, eax
0x1400102e5  test    eax, eax
0x1400102e7  js      loc_14001039B
0x1400102ed  mov     rcx, [rbp+770h+var_7E8]
0x1400102f1  test    rcx, rcx
0x1400102f4  jz      loc_14001039B
0x1400102fa  mov     rax, [rcx]
0x1400102fd  lea     rdx, [rbp+770h+var_280]
0x140010304  mov     rax, [rax+18h]
0x140010308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001030d  mov     edi, eax
0x14001030f  test    eax, eax
0x140010311  jns     short loc_14001031F
0x140010313  lea     rdx, aCvdsiscsiiniti_47; "CVdsIscsiInitiatorAdapterInternal::Logi"...
0x14001031a  jmp     loc_140010205
0x14001031f  call    cs:__imp_GetProcessHeap
0x140010325  mov     rcx, rax
0x140010328  xor     edx, edx
0x14001032a  mov     r8d, 402h
0x140010330  call    cs:__imp_VdsHeapAlloc
0x140010336  mov     [rsi+68h], rax
0x14001033a  test    rax, rax
0x14001033d  jnz     short loc_140010358
0x14001033f  lea     rdx, aCvdsiscsiiniti_123; "CVdsIscsiInitiatorAdapterInternal::Logi"...
0x140010346  xor     ecx, ecx
0x140010348  call    cs:__imp_VdsTraceW
0x14001034e  mov     edi, 8007000Eh
0x140010353  jmp     loc_14001097B
0x140010358  mov     [rax], r12w
0x14001035c  mov     rcx, [rsi+68h]
0x140010360  movzx   eax, [rbp+770h+var_4C]
0x140010367  mov     [rcx+400h], ax
0x14001036e  mov     r8, [rsi+68h]
0x140010372  add     r8, 200h
0x140010379  mov     edx, r15d
0x14001037c  lea     rcx, [rbp+770h+var_270]
0x140010383  call    cs:__imp_VdsIscsiIpAddressToString
0x140010389  mov     edi, eax
0x14001038b  test    eax, eax
0x14001038d  jns     short loc_1400103C8
0x14001038f  lea     rdx, aCvdsiscsiiniti_81; "CVdsIscsiInitiatorAdapterInternal::Logi"...
0x140010396  jmp     loc_140010205
0x14001039b  lea     rdx, aCvdsiscsiiniti_30; "CVdsIscsiInitiatorAdapterInternal::Logi"...
0x1400103a2  mov     r8d, edi
0x1400103a5  xor     ecx, ecx
0x1400103a7  call    cs:__imp_VdsTraceW
0x1400103ad  test    edi, edi
0x1400103af  js      loc_14001097B
0x1400103b5  mov     edi, 80004005h
0x1400103ba  jmp     loc_14001097B
0x1400103bf  lea     rdx, aCvdsiscsiiniti_68; "CVdsIscsiInitiatorAdapterInternal::Logi"...
0x1400103c6  jmp     short loc_1400103A2
0x1400103c8  mov     rax, [rbp+770h+var_7A0]
0x1400103cc  movups  xmm0, xmmword ptr [rax]
0x1400103cf  movdqu  xmmword ptr [rbp+770h+var_7B0.Data1], xmm0
0x1400103d4  lea     r8, [rbp+770h+var_7F0]; struct IUnknown **
0x1400103d8  mov     edx, 25h ; '%'; enum _VDS_OBJECT_TYPE
0x1400103dd  lea     rcx, [rbp+770h+var_7B0]; struct _GUID
0x1400103e1  call    ?GetObjectFromProviders@CVdsService@@SAJU_GUID@@W4_VDS_OBJECT_TYPE@@PEAPEAUIUnknown@@@Z; CVdsService::GetObjectFromProviders(_GUID,_VDS_OBJECT_TYPE,IUnknown * *)
  ... truncated ...
```
