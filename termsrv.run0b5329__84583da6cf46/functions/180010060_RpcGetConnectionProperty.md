# RpcGetConnectionProperty

- ea: `0x180010060`
- end: `0x1800118e3`
- name: `RpcGetConnectionProperty`
- size: `6275`
- prototype: `__int64 __fastcall(__int64, unsigned int, char *, char **)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000fa50`

## callees

- `0x180001688`
- `0x180002b60`
- `0x180002c74`
- `0x18000a210`
- `0x18000bad0`
- `0x180010060`
- `0x180016338`
- `0x1800321f0`
- `0x180032214`
- `0x180032220`
- `0x18003269c`
- `0x180032700`
- `0x1800327a0`
- `0x1800330c4`
- `0x180093828`
- `0x1800c8010`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180010e11`
- `ntdll!EtwEventWriteTransfer` at `0x180010e11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010eb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011855`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010eb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011855`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180010ea8`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001184b`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180010ea8`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001184b`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180010141`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180010262`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180010357`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180010444`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180010523`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180010734`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180010825`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18001093b`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180010a5e`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180010b32`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180010c05`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180010cd3`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180010f2d`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180010ff8`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800110c0`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18001118e`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180011260`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180011365`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180011444`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180011522`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180011602`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800116d8`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18001179e`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180010141`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180010262`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180010357`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180010444`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180010523`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180010734`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180010825`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18001093b`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180010a5e`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180010b32`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180010c05`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180010cd3`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180010f2d`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180010ff8`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800110c0`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18001118e`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180011260`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180011365`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180011444`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180011522`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180011602`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800116d8`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18001179e`
- `RPCRT4!RpcRevertToSelf` at `0x180010bd2`
- `RPCRT4!RpcRevertToSelf` at `0x180010bd2`
- `RPCRT4!RpcImpersonateClient` at `0x18001022a`
- `RPCRT4!RpcImpersonateClient` at `0x18001022a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010111`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001090a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001122e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010111`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001090a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001122e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010e32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010e3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010e32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010e3b`

## string_xrefs

- `0x180010e64`: `%s with Trace ID 0x%x Completed`
- `0x18001028f`: `RpcImpersonateClient`
- `0x180010c2c`: `RpcRevertToSelf failed returning ERROR_ACCESS_DENIED`

## pseudocode

```c
__int64 __fastcall RpcGetConnectionProperty(__int64 a1, unsigned int a2, char *a3, char **a4)
{
  char *v5; // r14
  const char *v6; // r13
  char *v7; // r12
  char *v8; // rsi
  signed int v9; // edi
  RPC_STATUS v10; // eax
  int v11; // r8d
  int v12; // r9d
  signed int v13; // ecx
  const char *v14; // rax
  int v15; // ebx
  RPC_STATUS v16; // eax
  RPC_STATUS v17; // eax
  int v18; // r8d
  int v19; // r9d
  signed int v20; // ecx
  const char *v21; // rax
  __int64 v22; // rbx
  RPC_STATUS v23; // eax
  int v24; // r8d
  int v25; // r9d
  signed int v26; // ecx
  const char *v27; // rax
  RPC_STATUS v28; // eax
  int v29; // r8d
  int v30; // r9d
  signed int v31; // ecx
  const char *v32; // rax
  RPC_STATUS v33; // eax
  int v34; // r8d
  int v35; // r9d
  signed int v36; // ecx
  const char *v37; // rax
  unsigned __int64 v38; // rdi
  __int64 v39; // rax
  bool v40; // cf
  unsigned __int64 v41; // rax
  unsigned __int64 *v42; // rax
  int v43; // ecx
  int v44; // r8d
  int v45; // r9d
  __int64 v46; // rcx
  RPC_STATUS v47; // eax
  int v48; // r8d
  int v49; // r9d
  signed int v50; // ecx
  const char *v51; // rax
  char *v52; // r14
  RPC_STATUS v53; // eax
  int v54; // r8d
  int v55; // r9d
  signed int v56; // ecx
  const char *v57; // rax
  BOOL v58; // r14d
  char *v59; // rax
  RPC_STATUS v60; // eax
  int v61; // r8d
  int v62; // r9d
  signed int v63; // ecx
  const char *v64; // rax
  RPC_STATUS v65; // eax
  int v66; // r8d
  int v67; // r9d
  signed int v68; // ecx
  const char *v69; // rax
  RPC_STATUS v70; // eax
  int v71; // r8d
  int v72; // r9d
  signed int v73; // ecx
  const char *v74; // rax
  RPC_STATUS v75; // eax
  signed int v76; // ebx
  RPC_STATUS v77; // eax
  int v78; // r8d
  int v79; // r9d
  signed int v80; // ecx
  const char *v81; // rax
  RPC_STATUS v82; // eax
  signed int v83; // ecx
  const char *v84; // rax
  void *v85; // rcx
  __int64 v86; // rbx
  RPC_STATUS v87; // eax
  int v88; // r8d
  int v89; // r9d
  signed int v90; // ecx
  const char *v91; // rax
  RPC_STATUS v92; // eax
  int v93; // r8d
  int v94; // r9d
  signed int v95; // ecx
  const char *v96; // rax
  RPC_STATUS v97; // eax
  int v98; // r8d
  int v99; // r9d
  signed int v100; // ecx
  const char *v101; // rax
  RPC_STATUS v102; // eax
  int v103; // r8d
  int v104; // r9d
  signed int v105; // ecx
  const char *v106; // rax
  char *v107; // rax
  RPC_STATUS v108; // eax
  int v109; // r8d
  int v110; // r9d
  signed int v111; // ecx
  const char *v112; // rax
  _WORD *v113; // rbx
  _WORD *v114; // rax
  RPC_STATUS v115; // eax
  int v116; // r8d
  int v117; // r9d
  signed int v118; // ecx
  const char *v119; // rax
  RPC_STATUS v120; // eax
  int v121; // r8d
  int v122; // r9d
  signed int v123; // ecx
  const char *v124; // rax
  RPC_STATUS v125; // eax
  int v126; // r8d
  int v127; // r9d
  signed int v128; // ecx
  const char *v129; // rax
  RPC_STATUS v130; // eax
  int v131; // r8d
  int v132; // r9d
  signed int v133; // ecx
  const char *v134; // rax
  RPC_STATUS v135; // eax
  int v136; // r8d
  int v137; // r9d
  signed int v138; // ecx
  const char *v139; // rax
  RPC_STATUS v140; // eax
  int v141; // r8d
  int v142; // r9d
  signed int v143; // ecx
  const char *v144; // rax
  unsigned int v146[2]; // [rsp+50h] [rbp-B0h] BYREF
  const char *v147; // [rsp+58h] [rbp-A8h] BYREF
  const char *v148; // [rsp+60h] [rbp-A0h] BYREF
  const char *v149; // [rsp+68h] [rbp-98h] BYREF
  const char *v150; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v151[2]; // [rsp+78h] [rbp-88h] BYREF
  size_t Size; // [rsp+88h] [rbp-78h] BYREF
  const char *v153; // [rsp+90h] [rbp-70h] BYREF
  unsigned int Pid[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v155; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v156; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v157; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v158; // [rsp+B8h] [rbp-48h] BYREF
  void **v159; // [rsp+C0h] [rbp-40h] BYREF
  int v160; // [rsp+D8h] [rbp-28h]
  __int64 v161; // [rsp+E0h] [rbp-20h]
  int v162; // [rsp+E8h] [rbp-18h]
  const char *v163; // [rsp+F0h] [rbp-10h]
  int v164; // [rsp+100h] [rbp+0h]
  char *v165; // [rsp+310h] [rbp+210h] BYREF
  int v166; // [rsp+318h] [rbp+218h]
  int v167; // [rsp+31Ch] [rbp+21Ch]
  char *v168; // [rsp+320h] [rbp+220h]
  int v169; // [rsp+328h] [rbp+228h]
  int v170; // [rsp+32Ch] [rbp+22Ch]
  const char *v171; // [rsp+330h] [rbp+230h]
  __int64 v172; // [rsp+338h] [rbp+238h]
  const char **v173; // [rsp+340h] [rbp+240h]
  __int64 v174; // [rsp+348h] [rbp+248h]
  const char **v175; // [rsp+350h] [rbp+250h]
  __int64 v176; // [rsp+358h] [rbp+258h]
  const char *v177; // [rsp+360h] [rbp+260h]
  __int64 v178; // [rsp+368h] [rbp+268h]
  const char **v179; // [rsp+370h] [rbp+270h]
  __int64 v180; // [rsp+378h] [rbp+278h]
  char *v181; // [rsp+380h] [rbp+280h]
  __int64 v182; // [rsp+388h] [rbp+288h]

  v5 = a3;
  v149 = a3;
  v6 = (const char *)a2;
  v7 = 0;
  v158 = 0;
  v157 = 0;
  v156 = 0;
  v155 = 0;
  LODWORD(Size) = 0;
  v8 = 0;
  CRpcCallTrace::CRpcCallTrace((CRpcCallTrace *)&v159, 0, "RpcGetConnectionProperty");
  if ( !a4 )
  {
    v9 = -2147024809;
    goto LABEL_137;
  }
  *a4 = 0;
  if ( PROPERTY_TYPE_IS_VDI_GUEST != *(_QWORD *)v5 || *((_QWORD *)v5 + 1) != 0x32BDE8F9E5552FA1LL )
  {
    if ( PROPERTY_TYPE_LISTENER_STATUS == *(_QWORD *)v5 && *((_QWORD *)v5 + 1) == 0xCE113DFC253F4594uLL )
    {
      if ( (unsigned int)v6 < 0x10000 )
      {
        v9 = -2147024809;
        goto LABEL_137;
      }
      v153 = 0;
      Pid[0] = 0;
      v16 = RpcImpersonateClient(0);
      v9 = v16;
      if ( v16 > 0 )
        v9 = (unsigned __int16)v16 | 0x80070000;
      if ( v9 < 0 )
      {
        if ( (unsigned int)dword_180128170 > 3 )
        {
          v146[0] = 0;
          v17 = I_RpcBindingInqLocalClientPID(0, v146);
          v20 = v17;
          if ( v17 > 0 )
            v20 = (unsigned __int16)v17 | 0x80070000;
          v21 = 0;
          if ( v20 >= 0 )
            v21 = (const char *)v146[0];
          v149 = v21;
          *(_QWORD *)v146 = "RpcGetConnectionProperty";
          LODWORD(v147) = v9;
          v151[0] = "RpcImpersonateClient";
          v148 = "Warning HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
            v20,
            (unsigned int)byte_1801092A1,
            v18,
            v19,
            (__int64)&v148,
            (__int64)v151,
            (__int64)&v147,
            (__int64)v146,
            (__int64)&v149);
        }
        if ( v153 )
          (*(void (__fastcall **)(const char *))(*(_QWORD *)v153 + 16LL))(v153);
        goto LABEL_137;
      }
      v22 = qword_180128DF0;
      if ( !qword_180128DF0 )
      {
        v9 = -2147418113;
        if ( (unsigned int)dword_180128170 > 3 )
        {
          v146[0] = 0;
          v70 = I_RpcBindingInqLocalClientPID(0, v146);
          v73 = v70;
          if ( v70 > 0 )
            v73 = (unsigned __int16)v70 | 0x80070000;
          v74 = 0;
          if ( v73 >= 0 )
            v74 = (const char *)v146[0];
          v150 = v74;
          v148 = "RpcGetConnectionProperty";
          LODWORD(v147) = -2147418113;
          v151[0] = "GetInstanceOfRemoteConnectionManager";
          v149 = "Warning HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
            v73,
            (unsigned int)&dword_180109244,
            v71,
            v72,
            (__int64)&v149,
            (__int64)v151,
            (__int64)&v147,
            (__int64)&v148,
            (__int64)&v150);
        }
        if ( v153 )
          (*(void (__fastcall **)(const char *))(*(_QWORD *)v153 + 16LL))(v153);
        goto LABEL_124;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_180128DF0 + 8LL))(qword_180128DF0);
      v9 = (*(__int64 (__fastcall **)(__int64, const char **))(*(_QWORD *)v22 + 120LL))(v22, &v153);
      if ( v9 >= 0 )
      {
        v9 = (*(__int64 (__fastcall **)(const char *, unsigned int *))(*(_QWORD *)v153 + 32LL))(v153, Pid);
        if ( v9 >= 0 )
        {
          if ( Pid[0] )
          {
            v38 = Pid[0];
            v39 = 8LL * Pid[0];
            if ( !is_mul_ok(Pid[0], 8u) )
              v39 = -1;
            v40 = __CFADD__(v39, 8);
            v41 = v39 + 8;
            if ( v40 )
              v41 = -1;
            v42 = (unsigned __int64 *)operator new[](v41, (const struct std::nothrow_t *)std::nothrow);
            if ( v42
              && (*v42 = v38,
                  v7 = (char *)(v42 + 1),
                  `eh vector constructor iterator'(
                    v42 + 1,
                    8u,
                    v38,
                    SmartPtr<IListener>::SmartPtr<IListener>,
                    SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>),
                  v7) )
            {
              v9 = (*(__int64 (__fastcall **)(const char *, char *, unsigned int *))(*(_QWORD *)v153 + 40LL))(
                     v153,
                     v7,
                     Pid);
              if ( v9 < 0 )
              {
                if ( (unsigned int)dword_180128170 > 3 )
                {
                  v148 = "RpcGetConnectionProperty";
                  LODWORD(v147) = v9;
                  v151[0] = "IListenersList->GetList";
                  v149 = "Warning HResult failed";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                    v43,
                    (unsigned int)&unk_180109088,
                    v44,
                    v45,
                    (__int64)&v149,
                    (__int64)v151,
                    (__int64)&v147,
                    (__int64)&v148);
                }
                if ( v153 )
                  (*(void (__fastcall **)(const char *))(*(_QWORD *)v153 + 16LL))(v153);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
                goto LABEL_124;
              }
              v46 = 0;
              if ( Pid[0] )
              {
                while ( (_DWORD)v6 != (_DWORD)v46 + 0x10000 )
                {
                  v46 = (unsigned int)(v46 + 1);
                  if ( (unsigned int)v46 >= Pid[0] )
                    goto LABEL_75;
                }
                v52 = &v7[8 * v46];
                v9 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v52 + 96LL))(*(_QWORD *)v52, 1);
                if ( v9 >= 0 )
                {
                  v9 = 0;
                  v58 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v52 + 64LL))(*(_QWORD *)v52) == 0;
                  LODWORD(Size) = 24;
                  v59 = (char *)LocalAlloc(0x40u, 0x18u);
                  v8 = v59;
                  if ( v59 )
                  {
                    memset_0(v59, 0, (unsigned int)Size);
                    *(_WORD *)v8 = 1;
                    *((_DWORD *)v8 + 2) = v58;
                    *a4 = v8;
                    if ( v153 )
                      (*(void (__fastcall **)(const char *))(*(_QWORD *)v153 + 16LL))(v153);
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
                    v5 = (char *)v149;
                    goto LABEL_124;
                  }
                  v9 = -2147024882;
                  if ( (unsigned int)dword_180128170 > 3 )
                  {
                    v146[0] = 0;
                    v60 = I_RpcBindingInqLocalClientPID(0, v146);
                    v63 = v60;
                    if ( v60 > 0 )
                      v63 = (unsigned __int16)v60 | 0x80070000;
                    v64 = 0;
                    if ( v63 >= 0 )
                      v64 = (const char *)v146[0];
                    v150 = v64;
                    v148 = "RpcGetConnectionProperty";
                    LODWORD(v147) = -2147024882;
                    v151[0] = "memory allocation - MIDL_user_allocate";
                    *(_QWORD *)v146 = "Warning HResult failed";
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
                      v63,
                      (unsigned int)byte_180108F71,
                      v61,
                      v62,
                      (__int64)v146,
                      (__int64)v151,
                      (__int64)&v147,
                      (__int64)&v148,
                      (__int64)&v150);
                  }
                  if ( v153 )
                    (*(void (__fastcall **)(const char *))(*(_QWORD *)v153 + 16LL))(v153);
                }
                else
                {
                  if ( (unsigned int)dword_180128170 > 3 )
                  {
                    v146[0] = 0;
                    v53 = I_RpcBindingInqLocalClientPID(0, v146);
                    v56 = v53;
                    if ( v53 > 0 )
                      v56 = (unsigned __int16)v53 | 0x80070000;
                    v57 = 0;
                    if ( v56 >= 0 )
                      v57 = (const char *)v146[0];
                    v148 = v57;
                    v151[0] = "RpcGetConnectionProperty";
                    LODWORD(v147) = v9;
                    *(_QWORD *)v146 = "Caller has no QUERY right";
                    v150 = "Warning HResult failed";
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
                      v56,
                      (unsigned int)byte_18010902B,
                      v54,
                      v55,
                      (__int64)&v150,
                      (__int64)v146,
                      (__int64)&v147,
                      (__int64)v151,
                      (__int64)&v148);
                  }
                  if ( v153 )
                    (*(void (__fastcall **)(const char *))(*(_QWORD *)v153 + 16LL))(v153);
                }
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
                v5 = (char *)v149;
LABEL_124:
                v75 = RpcRevertToSelf();
                v76 = v75;
                if ( v75 > 0 )
                  v76 = (unsigned __int16)v75 | 0x80070000;
                if ( v76 < 0 )
                {
                  if ( (unsigned int)dword_180128170 > 2 )
                  {
                    v146[0] = 0;
                    v77 = I_RpcBindingInqLocalClientPID(0, v146);
                    v80 = v77;
                    if ( v77 > 0 )
                      v80 = (unsigned __int16)v77 | 0x80070000;
                    v81 = 0;
                    if ( v80 >= 0 )
                      v81 = (const char *)v146[0];
                    v150 = v81;
                    LODWORD(v147) = v76;
                    v148 = "RpcRevertToSelf failed returning ERROR_ACCESS_DENIED";
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                      v80,
                      (unsigned int)&byte_180108B27,
                      v78,
                      v79,
                      (__int64)&v148,
                      (__int64)&v147,
                      (__int64)&v150);
                  }
                  v9 = -2147024891;
                }
                if ( v7 )
                {
                  `eh vector destructor iterator'(
                    v7,
                    8u,
                    *((_QWORD *)v7 - 1),
                    SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>);
                  operator delete[](v7 - 8, (const struct std::nothrow_t *)(8LL * *((_QWORD *)v7 - 1) + 8));
                }
                goto LABEL_136;
              }
LABEL_75:
              v9 = -2147024894;
              if ( (unsigned int)dword_180128170 > 3 )
              {
                v146[0] = 0;
                v47 = I_RpcBindingInqLocalClientPID(0, v146);
                v50 = v47;
                if ( v47 > 0 )
                  v50 = (unsigned __int16)v47 | 0x80070000;
                v51 = 0;
                if ( v50 >= 0 )
                  v51 = (const char *)v146[0];
                v150 = v51;
                v148 = "RpcGetConnectionProperty";
                LODWORD(v147) = -2147024894;
                v151[0] = "Listener lookup";
                v149 = "Warning HResult failed";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
                  v50,
                  (unsigned int)&word_180108FCE,
                  v48,
                  v49,
                  (__int64)&v149,
                  (__int64)v151,
                  (__int64)&v147,
                  (__int64)&v148,
                  (__int64)&v150);
              }
              if ( v153 )
                (*(void (__fastcall **)(const char *))(*(_QWORD *)v153 + 16LL))(v153);
            }
            else
            {
              v9 = -2147024882;
              if ( (unsigned int)dword_180128170 > 3 )
              {
                v146[0] = 0;
                v65 = I_RpcBindingInqLocalClientPID(0, v146);
                v68 = v65;
                if ( v65 > 0 )
                  v68 = (unsigned __int16)v65 | 0x80070000;
                v69 = 0;
                if ( v68 >= 0 )
                  v69 = (const char *)v146[0];
                v150 = v69;
                v148 = "RpcGetConnectionProperty";
                LODWORD(v147) = -2147024882;
                v151[0] = "memory allocation - new";
                v149 = "Warning HResult failed";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
                  v68,
                  (unsigned int)&unk_1801090D0,
                  v66,
                  v67,
                  (__int64)&v149,
                  (__int64)v151,
                  (__int64)&v147,
                  (__int64)&v148,
                  (__int64)&v150);
              }
              if ( v153 )
                (*(void (__fastcall **)(const char *))(*(_QWORD *)v153 + 16LL))(v153);
            }
          }
          else
          {
            v9 = -2147024894;
            if ( (unsigned int)dword_180128170 > 3 )
            {
              v146[0] = 0;
              v33 = I_RpcBindingInqLocalClientPID(0, v146);
              v36 = v33;
              if ( v33 > 0 )
                v36 = (unsigned __int16)v33 | 0x80070000;
              v37 = 0;
              if ( v36 >= 0 )
                v37 = (const char *)v146[0];
              v148 = v37;
              v151[0] = "RpcGetConnectionProperty";
              LODWORD(v147) = -2147024894;
              v149 = "No listeners";
              *(_QWORD *)v146 = "Warning HResult failed";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
                v36,
                (unsigned int)byte_18010912D,
                v34,
                v35,
                (__int64)v146,
                (__int64)&v149,
                (__int64)&v147,
                (__int64)v151,
                (__int64)&v148);
            }
            if ( v153 )
              (*(void (__fastcall **)(const char *))(*(_QWORD *)v153 + 16LL))(v153);
          }
        }
        else
        {
          if ( (unsigned int)dword_180128170 > 3 )
          {
            v146[0] = 0;
            v28 = I_RpcBindingInqLocalClientPID(0, v146);
            v31 = v28;
            if ( v28 > 0 )
              v31 = (unsigned __int16)v28 | 0x80070000;
            v32 = 0;
            if ( v31 >= 0 )
              v32 = (const char *)v146[0];
            v148 = v32;
            v151[0] = "RpcGetConnectionProperty";
            LODWORD(v147) = v9;
            v149 = "IListenersList->GetNumEntries";
            *(_QWORD *)v146 = "Warning HResult failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
              v31,
              (unsigned int)word_18010918A,
              v29,
              v30,
              (__int64)v146,
              (__int64)&v149,
              (__int64)&v147,
              (__int64)v151,
              (__int64)&v148);
          }
          if ( v153 )
            (*(void (__fastcall **)(const char *))(*(_QWORD *)v153 + 16LL))(v153);
        }
      }
      else
      {
        if ( (unsigned int)dword_180128170 > 3 )
        {
          v146[0] = 0;
          v23 = I_RpcBindingInqLocalClientPID(0, v146);
          v26 = v23;
          if ( v23 > 0 )
            v26 = (unsigned __int16)v23 | 0x80070000;
          v27 = 0;
          if ( v26 >= 0 )
            v27 = (const char *)v146[0];
          v148 = v27;
          v151[0] = "RpcGetConnectionProperty";
          LODWORD(v147) = v9;
          v149 = "IRemoteConnectionManager->GetInstanceOfListenersList";
          *(_QWORD *)v146 = "Warning HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
            v26,
            (unsigned int)&byte_1801091E7,
            v24,
            v25,
            (__int64)v146,
            (__int64)&v149,
            (__int64)&v147,
            (__int64)v151,
            (__int64)&v148);
        }
        if ( v153 )
          (*(void (__fastcall **)(const char *))(*(_QWORD *)v153 + 16LL))(v153);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      goto LABEL_124;
    }
    v86 = 0;
    if ( qword_180128DF0 )
    {
      v86 = qword_180128DF0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_180128DF0 + 8LL))(qword_180128DF0);
    }
    v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v86 + 152LL))(v86, &v158);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
    if ( v9 < 0 )
    {
      if ( (unsigned int)dword_180128170 > 3 )
      {
        v146[0] = 0;
        v87 = I_RpcBindingInqLocalClientPID(0, v146);
        v90 = v87;
        if ( v87 > 0 )
          v90 = (unsigned __int16)v87 | 0x80070000;
        v91 = 0;
        if ( v90 >= 0 )
          v91 = (const char *)v146[0];
        v150 = v91;
        v148 = "RpcGetConnectionProperty";
        LODWORD(v147) = v9;
        v151[0] = "GetSessionList";
        v149 = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
          v90,
          (unsigned int)&dword_180108F14,
          v88,
          v89,
          (__int64)&v149,
          (__int64)v151,
          (__int64)&v147,
          (__int64)&v148,
          (__int64)&v150);
      }
      goto LABEL_137;
    }
    v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v158 + 24LL))(v158, (unsigned int)v6, &v157);
    if ( v9 < 0 )
    {
      if ( (unsigned int)dword_180128170 > 3 )
      {
        v146[0] = 0;
        v92 = I_RpcBindingInqLocalClientPID(0, v146);
        v95 = v92;
        if ( v92 > 0 )
          v95 = (unsigned __int16)v92 | 0x80070000;
        v96 = 0;
        if ( v95 >= 0 )
          v96 = (const char *)v146[0];
        v150 = v96;
        v148 = "RpcGetConnectionProperty";
        LODWORD(v147) = v9;
        v151[0] = "FindSessionById";
        v149 = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
          v95,
          (unsigned int)&byte_180108EB7,
          v93,
          v94,
          (__int64)&v149,
          (__int64)v151,
          (__int64)&v147,
          (__int64)&v148,
          (__int64)&v150);
      }
      goto LABEL_137;
    }
    v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v157 + 104LL))(v157, &v156);
    if ( v9 < 0 )
    {
      if ( (unsigned int)dword_180128170 > 3 )
      {
        v146[0] = 0;
        v97 = I_RpcBindingInqLocalClientPID(0, v146);
        v100 = v97;
        if ( v97 > 0 )
          v100 = (unsigned __int16)v97 | 0x80070000;
        v101 = 0;
        if ( v100 >= 0 )
          v101 = (const char *)v146[0];
        v150 = v101;
        v148 = "RpcGetConnectionProperty";
        LODWORD(v147) = v9;
        v151[0] = "GetTerminal failed for session";
        v149 = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
          v100,
          (unsigned int)word_180108E5A,
          v98,
          v99,
          (__int64)&v149,
          (__int64)v151,
          (__int64)&v147,
          (__int64)&v148,
          (__int64)&v150);
      }
      goto LABEL_137;
    }
    v9 = (**(__int64 (__fastcall ***)(__int64, __int64 *, __int64 *))v156)(v156, qword_1800D7370, &v155);
    if ( v9 < 0 )
    {
      if ( (unsigned int)dword_180128170 > 3 )
      {
        v146[0] = 0;
        v102 = I_RpcBindingInqLocalClientPID(0, v146);
        v105 = v102;
        if ( v102 > 0 )
          v105 = (unsigned __int16)v102 | 0x80070000;
        v106 = 0;
        if ( v105 >= 0 )
          v106 = (const char *)v146[0];
        v150 = v106;
        v148 = "RpcGetConnectionProperty";
        LODWORD(v147) = v9;
        v151[0] = "ptrTerminal->QueryInterface";
        v149 = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
          v105,
          (unsigned int)byte_180108DFD,
          v103,
          v104,
          (__int64)&v149,
          (__int64)v151,
          (__int64)&v147,
          (__int64)&v148,
          (__int64)&v150);
      }
      goto LABEL_137;
    }
    LODWORD(Size) = 24;
    v107 = (char *)LocalAlloc(0x40u, 0x18u);
    v8 = v107;
    if ( !v107 )
    {
      v9 = -2147024882;
      if ( (unsigned int)dword_180128170 > 3 )
      {
        v146[0] = 0;
        v108 = I_RpcBindingInqLocalClientPID(0, v146);
        v111 = v108;
        if ( v108 > 0 )
          v111 = (unsigned __int16)v108 | 0x80070000;
        v112 = 0;
        if ( v111 >= 0 )
          v112 = (const char *)v146[0];
        v150 = v112;
        v148 = "RpcGetConnectionProperty";
        LODWORD(v147) = -2147024882;
        v151[0] = "memory allocation";
        v149 = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
          v111,
          (unsigned int)&unk_180108DA0,
          v109,
          v110,
          (__int64)&v149,
          (__int64)v151,
          (__int64)&v147,
          (__int64)&v148,
          (__int64)&v150);
      }
      goto LABEL_137;
    }
    v113 = 0;
    memset_0(v107, 0, (unsigned int)Size);
    v9 = (*(__int64 (__fastcall **)(__int64, char *, size_t *, char *))(*(_QWORD *)v155 + 400LL))(v155, v5, &Size, v8);
    if ( v9 == -2147024774 )
    {
      v114 = operator new[]((unsigned int)Size, (const struct std::nothrow_t *)std::nothrow);
      v113 = v114;
      if ( !v114 )
      {
        v9 = -2147024882;
        if ( (unsigned int)dword_180128170 > 3 )
        {
          v146[0] = 0;
          v115 = I_RpcBindingInqLocalClientPID(0, v146);
          v118 = v115;
          if ( v115 > 0 )
            v118 = (unsigned __int16)v115 | 0x80070000;
          v119 = 0;
          if ( v118 >= 0 )
            v119 = (const char *)v146[0];
          v150 = v119;
          v148 = "RpcGetConnectionProperty";
          LODWORD(v147) = -2147024882;
          v151[0] = "memory allocation";
          v149 = "Warning HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
            v118,
            (unsigned int)byte_180108D43,
            v116,
            v117,
            (__int64)&v149,
            (__int64)v151,
            (__int64)&v147,
            (__int64)&v148,
            (__int64)&v150);
        }
        goto LABEL_137;
      }
      memset_0(v114, 0, (unsigned int)Size);
      v9 = (*(__int64 (__fastcall **)(__int64, char *, size_t *, _WORD *))(*(_QWORD *)v155 + 400LL))(
             v155,
             v5,
             &Size,
             v113);
      if ( v9 < 0 )
      {
        if ( (unsigned int)dword_180128170 > 3 )
        {
          v146[0] = 0;
          v120 = I_RpcBindingInqLocalClientPID(0, v146);
          v123 = v120;
          if ( v120 > 0 )
            v123 = (unsigned __int16)v120 | 0x80070000;
          v124 = 0;
          if ( v123 >= 0 )
            v124 = (const char *)v146[0];
          v150 = v124;
          v148 = "RpcGetConnectionProperty";
          LODWORD(v147) = v9;
          v151[0] = "ptrRemoteTerminal->GetConnectionProperty after allocating more memory";
          v149 = "Warning HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
            v123,
            (unsigned int)&word_180108CE6,
            v121,
            v122,
            (__int64)&v149,
            (__int64)v151,
            (__int64)&v147,
            (__int64)&v148,
            (__int64)&v150);
          operator delete(v113);
          goto LABEL_136;
        }
LABEL_245:
        operator delete(v113);
        goto LABEL_136;
      }
      switch ( *v113 )
      {
        case 1:
          *((_DWORD *)v8 + 2) = *((_DWORD *)v113 + 2);
          break;
        case 2:
          *((_DWORD *)v8 + 2) = *((_DWORD *)v113 + 2);
          v9 = CRpcUtils::MIDL_mem_dup(
                 (unsigned __int8 **)v8 + 2,
                 *((unsigned __int8 *const *)v113 + 2),
                 2 * *((_DWORD *)v113 + 2));
          if ( v9 < 0 )
          {
            if ( (unsigned int)dword_180128170 <= 3 )
              goto LABEL_245;
            v146[0] = 0;
            v135 = I_RpcBindingInqLocalClientPID(0, v146);
            v138 = v135;
            if ( v135 > 0 )
              v138 = (unsigned __int16)v135 | 0x80070000;
            v139 = 0;
            if ( v138 >= 0 )
              v139 = (const char *)v146[0];
            v150 = v139;
            v148 = "RpcGetConnectionProperty";
            LODWORD(v147) = v9;
            v151[0] = "MIDL_mem_dup";
            v149 = "Warning HResult failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
              v138,
              (unsigned int)byte_180108C89,
              v136,
              v137,
              (__int64)&v149,
              (__int64)v151,
              (__int64)&v147,
              (__int64)&v148,
              (__int64)&v150);
            operator delete(v113);
            goto LABEL_136;
          }
          break;
        case 3:
          *((_DWORD *)v8 + 2) = *((_DWORD *)v113 + 2);
          v9 = CRpcUtils::MIDL_mem_dup(
                 (unsigned __int8 **)v8 + 2,
                 *((unsigned __int8 *const *)v113 + 2),
                 *((_DWORD *)v113 + 2));
          if ( v9 < 0 )
          {
            if ( (unsigned int)dword_180128170 <= 3 )
              goto LABEL_245;
            v146[0] = 0;
            v130 = I_RpcBindingInqLocalClientPID(0, v146);
            v133 = v130;
            if ( v130 > 0 )
              v133 = (unsigned __int16)v130 | 0x80070000;
            v134 = 0;
            if ( v133 >= 0 )
              v134 = (const char *)v146[0];
            v150 = v134;
            v148 = "RpcGetConnectionProperty";
            LODWORD(v147) = v9;
            v151[0] = "MIDL_mem_dup";
            v149 = "Warning HResult failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
              v133,
              (unsigned int)&dword_180108C2C,
              v131,
              v132,
              (__int64)&v149,
              (__int64)v151,
              (__int64)&v147,
              (__int64)&v148,
              (__int64)&v150);
            operator delete(v113);
            goto LABEL_136;
          }
          break;
        case 4:
          *(_OWORD *)(v8 + 8) = *(_OWORD *)(v113 + 4);
          break;
        default:
          v9 = -2147024883;
          if ( (unsigned int)dword_180128170 <= 3 )
            goto LABEL_245;
          v146[0] = 0;
          v125 = I_RpcBindingInqLocalClientPID(0, v146);
          v128 = v125;
          if ( v125 > 0 )
            v128 = (unsigned __int16)v125 | 0x80070000;
          v129 = 0;
          if ( v128 >= 0 )
            v129 = (const char *)v146[0];
          v150 = v129;
          v148 = "RpcGetConnectionProperty";
          LODWORD(v147) = -2147024883;
          v151[0] = "data type check";
          v149 = "Warning HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
            v128,
            (unsigned int)&byte_180108BCF,
            v126,
            v127,
            (__int64)&v149,
            (__int64)v151,
            (__int64)&v147,
            (__int64)&v148,
            (__int64)&v150);
          operator delete(v113);
LABEL_136:
          if ( v9 >= 0 )
            goto LABEL_149;
          goto LABEL_137;
      }
      *(_WORD *)v8 = *v113;
    }
    if ( v9 >= 0 )
    {
      *a4 = v8;
    }
    else if ( (unsigned int)dword_180128170 > 3 )
    {
      v146[0] = 0;
      v140 = I_RpcBindingInqLocalClientPID(0, v146);
      v143 = v140;
      if ( v140 > 0 )
        v143 = (unsigned __int16)v140 | 0x80070000;
      v144 = 0;
      if ( v143 >= 0 )
        v144 = (const char *)v146[0];
      v150 = v144;
      v148 = "RpcGetConnectionProperty";
      LODWORD(v147) = v9;
      v151[0] = "ptrRemoteTerminal->GetConnectionProperty";
      v149 = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        v143,
        (unsigned int)word_180108B72,
        v141,
        v142,
        (__int64)&v149,
        (__int64)v151,
        (__int64)&v147,
        (__int64)&v148,
        (__int64)&v150);
    }
    if ( v113 )
      goto LABEL_245;
    goto LABEL_136;
  }
  LODWORD(Size) = 24;
  v8 = (char *)LocalAlloc(0x40u, 0x18u);
  if ( v8 )
  {
    v15 = IsVMAddedToACollection();
    memset_0(v8, 0, (unsigned int)Size);
    *(_WORD *)v8 = 1;
    *((_DWORD *)v8 + 2) = v15;
    *a4 = v8;
    v9 = 0;
    goto LABEL_149;
  }
  v9 = -2147024882;
  if ( (unsigned int)dword_180128170 > 3 )
  {
    Pid[0] = 0;
    v10 = I_RpcBindingInqLocalClientPID(0, Pid);
    v13 = v10;
    if ( v10 > 0 )
      v13 = (unsigned __int16)v10 | 0x80070000;
    v14 = 0;
    if ( v13 >= 0 )
      v14 = (const char *)Pid[0];
    v149 = v14;
    v153 = "RpcGetConnectionProperty";
    v146[0] = -2147024882;
    v147 = "memory allocation - MIDL_user_allocate";
    *(_QWORD *)Pid = "Warning HResult failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      v13,
      (unsigned int)&word_1801092FE,
      v11,
      v12,
      (__int64)Pid,
      (__int64)&v147,
      (__int64)v146,
      (__int64)&v153,
      (__int64)&v149);
  }
LABEL_137:
  if ( (unsigned int)dword_180128170 > 3 )
  {
    v150 = v6;
    LODWORD(v147) = v9;
    v146[0] = 0;
    v82 = I_RpcBindingInqLocalClientPID(0, v146);
    v83 = v82;
    if ( v82 > 0 )
      v83 = (unsigned __int16)v82 | 0x80070000;
    v84 = 0;
    if ( v83 >= 0 )
      v84 = (const char *)v146[0];
    v148 = v84;
    v181 = v5;
    v182 = 16;
    v179 = &v150;
    v180 = 8;
    v177 = "RpcGetConnectionProperty";
    v178 = 25;
    v175 = &v147;
    v176 = 4;
    v173 = &v148;
    v174 = 8;
    v171 = "RPC call to us failed from another process. It was called with these parameters.";
    v172 = 81;
    v151[0] = 0x14030B000000LL;
    v151[1] = 0;
    v165 = (char *)off_180128178;
    v166 = *(unsigned __int16 *)off_180128178;
    v167 = 2;
    v168 = byte_180108AD1;
    v169 = 85;
    v170 = 1;
    v146[0] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EtwEventWriteTransfer(RegHandle, v151, 0, 0, 8, &v165);
  }
  if ( v8 )
  {
    if ( *(_WORD *)v8 == 2 || *(_WORD *)v8 == 3 )
    {
      v85 = (void *)*((_QWORD *)v8 + 2);
      if ( v85 )
        LocalFree(v85);
    }
    LocalFree(v8);
  }
LABEL_149:
  v159 = &CRpcCallTrace::`vftable';
  if ( v164 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "%s with Trace ID 0x%x Completed", v163, v160);
  v159 = &CTraceBase::`vftable';
  if ( !v162 && CTraceBase::g_bEnabled && CTraceBase::g_TLSIndex != -1 )
  {
    if ( TlsSetValue(CTraceBase::g_TLSIndex, 0) )
    {
      if ( TlsSetValue(CTraceBase::g_CreatorFunctionTLSIndex, 0) )
        goto LABEL_248;
    }
    else
    {
      GetLastError();
    }
    GetLastError();
  }
LABEL_248:
  v161 = 0;
  if ( v155 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v155 + 16LL))(v155);
  if ( v156 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v156 + 16LL))(v156);
  if ( v157 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v157 + 16LL))(v157);
  if ( v158 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v158 + 16LL))(v158);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180010060  mov     [rsp-8+arg_0], rbx
0x180010065  push    rbp
0x180010066  push    rsi
0x180010067  push    rdi
0x180010068  push    r12
0x18001006a  push    r13
0x18001006c  push    r14
0x18001006e  push    r15
0x180010070  lea     rbp, [rsp-2A0h]
0x180010078  sub     rsp, 3A0h
0x18001007f  mov     rax, cs:__security_cookie
0x180010086  xor     rax, rsp
0x180010089  mov     [rbp+2D0h+var_40], rax
0x180010090  mov     r15, r9
0x180010093  mov     r14, r8
0x180010096  mov     [rsp+3D0h+var_368], r8
0x18001009b  mov     r13d, edx
0x18001009e  xor     r12d, r12d
0x1800100a1  mov     [rbp+2D0h+var_318], r12
0x1800100a5  mov     [rbp+2D0h+var_320], r12
0x1800100a9  mov     [rbp+2D0h+var_328], r12
0x1800100ad  mov     [rbp+2D0h+var_330], r12
0x1800100b1  mov     dword ptr [rbp+2D0h+Size], r12d
0x1800100b5  mov     esi, r12d
0x1800100b8  lea     rbx, aRpcgetconnecti; "RpcGetConnectionProperty"
0x1800100bf  mov     r8, rbx; char *
0x1800100c2  xor     edx, edx; int
0x1800100c4  lea     rcx, [rbp+2D0h+var_310]; this
0x1800100c8  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x1800100cd  test    r15, r15
0x1800100d0  jnz     short loc_1800100DC
0x1800100d2  mov     edi, 80070057h
0x1800100d7  jmp     loc_180010CAF
0x1800100dc  mov     [r15], r12
0x1800100df  mov     rax, cs:PROPERTY_TYPE_IS_VDI_GUEST
0x1800100e6  cmp     rax, [r14]
0x1800100e9  jnz     loc_1800101EC
0x1800100ef  mov     rax, cs:qword_1800DA070
0x1800100f6  cmp     rax, [r14+8]
0x1800100fa  jnz     loc_1800101EC
0x180010100  mov     dword ptr [rbp+2D0h+Size], 18h
0x180010107  mov     edx, 18h; uBytes
0x18001010c  mov     ecx, 40h ; '@'; uFlags
0x180010111  call    cs:__imp_LocalAlloc
0x180010117  mov     rsi, rax
0x18001011a  test    rax, rax
0x18001011d  jnz     loc_1800101C4
0x180010123  mov     edi, 8007000Eh
0x180010128  mov     eax, cs:dword_180128170
0x18001012e  cmp     eax, 3
0x180010131  jbe     loc_180010CAF
0x180010137  mov     [rbp+2D0h+Pid], r12d
0x18001013b  lea     rdx, [rbp+2D0h+Pid]; Pid
0x18001013f  xor     ecx, ecx; Binding
0x180010141  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180010147  mov     ecx, eax
0x180010149  test    eax, eax
0x18001014b  jle     short loc_180010156
0x18001014d  movzx   ecx, ax
0x180010150  or      ecx, 80070000h
0x180010156  mov     eax, r12d
0x180010159  test    ecx, ecx
0x18001015b  cmovns  eax, [rbp+2D0h+Pid]
0x18001015f  mov     [rsp+3D0h+var_368], rax
0x180010164  mov     [rbp+2D0h+var_340], rbx
0x180010168  mov     [rsp+3D0h+var_380], edi
0x18001016c  lea     rax, aMemoryAllocati_2; "memory allocation - MIDL_user_allocate"
0x180010173  mov     [rsp+3D0h+var_378], rax
0x180010178  lea     rax, aWarningHresult; "Warning HResult failed"
0x18001017f  mov     qword ptr [rbp+2D0h+Pid], rax
0x180010183  lea     rax, [rsp+3D0h+var_368]
0x180010188  mov     [rsp+3D0h+var_390], rax
0x18001018d  lea     rax, [rbp+2D0h+var_340]
0x180010191  mov     [rsp+3D0h+var_398], rax
0x180010196  lea     rax, [rsp+3D0h+var_380]
0x18001019b  mov     [rsp+3D0h+var_3A0], rax
0x1800101a0  lea     rax, [rsp+3D0h+var_378]
0x1800101a5  mov     [rsp+3D0h+var_3A8], rax
0x1800101aa  lea     rax, [rbp+2D0h+Pid]
0x1800101ae  mov     [rsp+3D0h+var_3B0], rax
0x1800101b3  lea     rdx, word_1801092FE
0x1800101ba  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x1800101bf  jmp     loc_180010CAF
0x1800101c4  call    ?IsVMAddedToACollection@@YAHXZ; IsVMAddedToACollection(void)
0x1800101c9  mov     ebx, eax
0x1800101cb  mov     r8d, dword ptr [rbp+2D0h+Size]; Size
0x1800101cf  xor     edx, edx; Val
0x1800101d1  mov     rcx, rsi; void *
0x1800101d4  call    memset_0
0x1800101d9  mov     word ptr [rsi], 1
0x1800101de  mov     [rsi+8], ebx
0x1800101e1  mov     [r15], rsi
0x1800101e4  mov     edi, r12d
0x1800101e7  jmp     loc_180010E42
0x1800101ec  mov     rax, cs:PROPERTY_TYPE_LISTENER_STATUS
0x1800101f3  cmp     rax, [r14]
0x1800101f6  jnz     loc_180010EC1
0x1800101fc  mov     rax, cs:qword_1800D9CF8
0x180010203  cmp     rax, [r14+8]
0x180010207  jnz     loc_180010EC1
0x18001020d  cmp     r13d, 10000h
0x180010214  jnb     short loc_180010220
0x180010216  mov     edi, 80070057h
0x18001021b  jmp     loc_180010CAF
0x180010220  mov     [rbp+2D0h+var_340], r12
0x180010224  mov     [rbp+2D0h+Pid], r12d
0x180010228  xor     ecx, ecx; BindingHandle
0x18001022a  call    cs:__imp_RpcImpersonateClient
0x180010230  mov     edi, eax
0x180010232  test    eax, eax
0x180010234  jle     short loc_18001023F
0x180010236  movzx   edi, ax
0x180010239  or      edi, 80070000h
0x18001023f  test    edi, edi
0x180010241  jns     loc_180010301
0x180010247  mov     eax, cs:dword_180128170
0x18001024d  cmp     eax, 3
0x180010250  jbe     loc_1800102E6
0x180010256  mov     [rsp+3D0h+var_380], r12d
0x18001025b  lea     rdx, [rsp+3D0h+var_380]; Pid
0x180010260  xor     ecx, ecx; Binding
0x180010262  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180010268  mov     ecx, eax
0x18001026a  test    eax, eax
0x18001026c  jle     short loc_180010277
0x18001026e  movzx   ecx, ax
0x180010271  or      ecx, 80070000h
0x180010277  mov     eax, r12d
0x18001027a  test    ecx, ecx
0x18001027c  cmovns  eax, [rsp+3D0h+var_380]
0x180010281  mov     [rsp+3D0h+var_368], rax
0x180010286  mov     qword ptr [rsp+3D0h+var_380], rbx
0x18001028b  mov     dword ptr [rsp+3D0h+var_378], edi
0x18001028f  lea     rax, aRpcimpersonate_0; "RpcImpersonateClient"
0x180010296  mov     [rsp+3D0h+var_358], rax
0x18001029b  lea     rax, aWarningHresult; "Warning HResult failed"
0x1800102a2  mov     [rsp+3D0h+var_370], rax
0x1800102a7  lea     rax, [rsp+3D0h+var_368]
0x1800102ac  mov     [rsp+3D0h+var_390], rax
0x1800102b1  lea     rax, [rsp+3D0h+var_380]
0x1800102b6  mov     [rsp+3D0h+var_398], rax
0x1800102bb  lea     rax, [rsp+3D0h+var_378]
0x1800102c0  mov     [rsp+3D0h+var_3A0], rax
0x1800102c5  lea     rax, [rsp+3D0h+var_358]
0x1800102ca  mov     [rsp+3D0h+var_3A8], rax
0x1800102cf  lea     rax, [rsp+3D0h+var_370]
0x1800102d4  mov     [rsp+3D0h+var_3B0], rax
0x1800102d9  lea     rdx, byte_1801092A1
0x1800102e0  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x1800102e5  nop
0x1800102e6  mov     rcx, [rbp+2D0h+var_340]
0x1800102ea  test    rcx, rcx
0x1800102ed  jz      short loc_1800102FC
0x1800102ef  mov     rax, [rcx]
0x1800102f2  mov     rax, [rax+10h]
0x1800102f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102fb  nop
0x1800102fc  jmp     loc_180010CAF
0x180010301  mov     rbx, cs:qword_180128DF0
0x180010308  test    rbx, rbx
0x18001030b  jz      loc_180010B13
0x180010311  mov     rax, [rbx]
0x180010314  mov     rcx, rbx
0x180010317  mov     rax, [rax+8]
0x18001031b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010320  mov     rax, [rbx]
0x180010323  lea     rdx, [rbp+2D0h+var_340]
0x180010327  mov     rcx, rbx
0x18001032a  mov     rax, [rax+78h]
0x18001032e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010333  mov     edi, eax
0x180010335  test    eax, eax
0x180010337  jns     loc_18001040C
0x18001033d  mov     ecx, cs:dword_180128170
0x180010343  cmp     ecx, 3
0x180010346  jbe     loc_1800103E1
0x18001034c  mov     [rsp+3D0h+var_380], esi
0x180010350  lea     rdx, [rsp+3D0h+var_380]; Pid
0x180010355  xor     ecx, ecx; Binding
0x180010357  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18001035d  mov     ecx, eax
0x18001035f  test    eax, eax
0x180010361  jle     short loc_18001036C
0x180010363  movzx   ecx, ax
0x180010366  or      ecx, 80070000h
0x18001036c  xor     eax, eax
0x18001036e  test    ecx, ecx
0x180010370  cmovns  eax, [rsp+3D0h+var_380]
0x180010375  mov     [rsp+3D0h+var_370], rax
0x18001037a  lea     rax, aRpcgetconnecti; "RpcGetConnectionProperty"
0x180010381  mov     [rsp+3D0h+var_358], rax
0x180010386  mov     dword ptr [rsp+3D0h+var_378], edi
0x18001038a  lea     rax, aIremoteconnect_0; "IRemoteConnectionManager->GetInstanceOf"...
0x180010391  mov     [rsp+3D0h+var_368], rax
0x180010396  lea     rax, aWarningHresult; "Warning HResult failed"
0x18001039d  mov     qword ptr [rsp+3D0h+var_380], rax
0x1800103a2  lea     rax, [rsp+3D0h+var_370]
0x1800103a7  mov     [rsp+3D0h+var_390], rax
0x1800103ac  lea     rax, [rsp+3D0h+var_358]
0x1800103b1  mov     [rsp+3D0h+var_398], rax
0x1800103b6  lea     rax, [rsp+3D0h+var_378]
0x1800103bb  mov     [rsp+3D0h+var_3A0], rax
0x1800103c0  lea     rax, [rsp+3D0h+var_368]
0x1800103c5  mov     [rsp+3D0h+var_3A8], rax
0x1800103ca  lea     rax, [rsp+3D0h+var_380]
0x1800103cf  mov     [rsp+3D0h+var_3B0], rax
0x1800103d4  lea     rdx, byte_1801091E7
0x1800103db  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x1800103e0  nop
0x1800103e1  mov     rcx, [rbp+2D0h+var_340]
0x1800103e5  test    rcx, rcx
0x1800103e8  jz      short loc_1800103F7
0x1800103ea  mov     rax, [rcx]
0x1800103ed  mov     rax, [rax+10h]
0x1800103f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103f6  nop
0x1800103f7  mov     rax, [rbx]
0x1800103fa  mov     rcx, rbx
0x1800103fd  mov     rax, [rax+10h]
0x180010401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010406  nop
0x180010407  jmp     loc_180010BD2
0x18001040c  mov     rcx, [rbp+2D0h+var_340]
0x180010410  mov     rax, [rcx]
0x180010413  lea     rdx, [rbp+2D0h+Pid]
0x180010417  mov     rax, [rax+20h]
0x18001041b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010420  mov     edi, eax
0x180010422  test    eax, eax
0x180010424  jns     loc_1800104F9
0x18001042a  mov     eax, cs:dword_180128170
0x180010430  cmp     eax, 3
0x180010433  jbe     loc_1800104CE
0x180010439  mov     [rsp+3D0h+var_380], esi
0x18001043d  lea     rdx, [rsp+3D0h+var_380]; Pid
0x180010442  xor     ecx, ecx; Binding
0x180010444  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18001044a  mov     ecx, eax
0x18001044c  test    eax, eax
0x18001044e  jle     short loc_180010459
0x180010450  movzx   ecx, ax
0x180010453  or      ecx, 80070000h
0x180010459  xor     eax, eax
0x18001045b  test    ecx, ecx
0x18001045d  cmovns  eax, [rsp+3D0h+var_380]
0x180010462  mov     [rsp+3D0h+var_370], rax
0x180010467  lea     rax, aRpcgetconnecti; "RpcGetConnectionProperty"
0x18001046e  mov     [rsp+3D0h+var_358], rax
0x180010473  mov     dword ptr [rsp+3D0h+var_378], edi
0x180010477  lea     rax, aIlistenerslist; "IListenersList->GetNumEntries"
0x18001047e  mov     [rsp+3D0h+var_368], rax
0x180010483  lea     rax, aWarningHresult; "Warning HResult failed"
0x18001048a  mov     qword ptr [rsp+3D0h+var_380], rax
0x18001048f  lea     rax, [rsp+3D0h+var_370]
0x180010494  mov     [rsp+3D0h+var_390], rax
0x180010499  lea     rax, [rsp+3D0h+var_358]
0x18001049e  mov     [rsp+3D0h+var_398], rax
0x1800104a3  lea     rax, [rsp+3D0h+var_378]
0x1800104a8  mov     [rsp+3D0h+var_3A0], rax
0x1800104ad  lea     rax, [rsp+3D0h+var_368]
0x1800104b2  mov     [rsp+3D0h+var_3A8], rax
0x1800104b7  lea     rax, [rsp+3D0h+var_380]
0x1800104bc  mov     [rsp+3D0h+var_3B0], rax
0x1800104c1  lea     rdx, word_18010918A
0x1800104c8  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x1800104cd  nop
0x1800104ce  mov     rcx, [rbp+2D0h+var_340]
0x1800104d2  test    rcx, rcx
0x1800104d5  jz      short loc_1800104E4
0x1800104d7  mov     rax, [rcx]
0x1800104da  mov     rax, [rax+10h]
0x1800104de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104e3  nop
0x1800104e4  mov     rax, [rbx]
0x1800104e7  mov     rcx, rbx
0x1800104ea  mov     rax, [rax+10h]
0x1800104ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104f3  nop
0x1800104f4  jmp     loc_180010BD2
0x1800104f9  mov     eax, [rbp+2D0h+Pid]
0x1800104fc  test    eax, eax
0x1800104fe  jnz     loc_1800105D8
0x180010504  mov     edi, 80070002h
0x180010509  mov     eax, cs:dword_180128170
0x18001050f  cmp     eax, 3
0x180010512  jbe     loc_1800105AD
0x180010518  mov     [rsp+3D0h+var_380], esi
0x18001051c  lea     rdx, [rsp+3D0h+var_380]; Pid
0x180010521  xor     ecx, ecx; Binding
0x180010523  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180010529  mov     ecx, eax
0x18001052b  test    eax, eax
0x18001052d  jle     short loc_180010538
0x18001052f  movzx   ecx, ax
0x180010532  or      ecx, 80070000h
0x180010538  xor     eax, eax
0x18001053a  test    ecx, ecx
0x18001053c  cmovns  eax, [rsp+3D0h+var_380]
0x180010541  mov     [rsp+3D0h+var_370], rax
0x180010546  lea     rax, aRpcgetconnecti; "RpcGetConnectionProperty"
  ... truncated ...
```
