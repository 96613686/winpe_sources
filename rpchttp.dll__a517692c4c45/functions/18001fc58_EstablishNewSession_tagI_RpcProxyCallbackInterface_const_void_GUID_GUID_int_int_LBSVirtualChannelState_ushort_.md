# EstablishNewSession(tagI_RpcProxyCallbackInterface const *,void *,_GUID *,_GUID *,int,int,LBSVirtualChannelState * *,ushort * *,ushort *)

- ea: `0x18001fc58`
- end: `0x1800206ba`
- name: `?EstablishNewSession@@YAJPEBUtagI_RpcProxyCallbackInterface@@PEAXPEAU_GUID@@2HHPEAPEAVLBSVirtualChannelState@@PEAPEAGPEAG@Z`
- size: `2658`
- prototype: `__int64 __fastcall(const struct tagI_RpcProxyCallbackInterface *, void *, struct _GUID *, struct _GUID *, int, int, struct LBSVirtualChannelState **, unsigned __int16 **, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `22`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180005788`
- `0x1800058a0`

## callees

- `0x18001b930`
- `0x18001e3d4`
- `0x18001e4a4`
- `0x18001e524`
- `0x18001f50c`
- `0x18001f848`
- `0x18001f870`
- `0x18001f984`
- `0x18001fc58`
- `0x1800207e8`
- `0x180020a9c`
- `0x180020c3c`
- `0x180021238`
- `0x18002129c`
- `0x1800217e4`
- `0x180021f7c`
- `0x180022208`
- `0x1800242e8`
- `0x180024368`
- `0x180024408`
- `0x180024640`
- `0x180025010`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x18001fdce`
- `ntdll!RtlDeleteCriticalSection` at `0x18001fdce`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x18001fdad`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x18001fdad`
- `KERNEL32!GetLastError` at `0x18002065f`
- `KERNEL32!GetLastError` at `0x18002065f`
- `KERNEL32!CloseHandle` at `0x180020676`
- `KERNEL32!CloseHandle` at `0x180020676`
- `ADVAPI32!EventActivityIdControl` at `0x18002034d`
- `ADVAPI32!EventActivityIdControl` at `0x180020378`
- `ADVAPI32!EventActivityIdControl` at `0x1800203ec`
- `ADVAPI32!EventActivityIdControl` at `0x180020416`
- `ADVAPI32!EventActivityIdControl` at `0x18002052d`
- `ADVAPI32!EventActivityIdControl` at `0x180020558`
- `ADVAPI32!EventActivityIdControl` at `0x18002034d`
- `ADVAPI32!EventActivityIdControl` at `0x180020378`
- `ADVAPI32!EventActivityIdControl` at `0x1800203ec`
- `ADVAPI32!EventActivityIdControl` at `0x180020416`
- `ADVAPI32!EventActivityIdControl` at `0x18002052d`
- `ADVAPI32!EventActivityIdControl` at `0x180020558`
- `ADVAPI32!SetThreadToken` at `0x180020655`
- `ADVAPI32!SetThreadToken` at `0x180020655`
- `Secur32!GetUserNameExW` at `0x180020320`
- `Secur32!GetUserNameExW` at `0x180020320`
- `RPCRT4!I_RpcFree` at `0x18001fdd7`
- `RPCRT4!I_RpcFree` at `0x18002032d`
- `RPCRT4!I_RpcFree` at `0x180020493`
- `RPCRT4!I_RpcFree` at `0x180020588`
- `RPCRT4!I_RpcFree` at `0x1800205c5`
- `RPCRT4!I_RpcFree` at `0x1800205fe`
- `RPCRT4!I_RpcFree` at `0x180020613`
- `RPCRT4!I_RpcFree` at `0x180020624`
- `RPCRT4!I_RpcFree` at `0x180020639`
- `RPCRT4!I_RpcFree` at `0x180020692`
- `RPCRT4!I_RpcFree` at `0x18001fdd7`
- `RPCRT4!I_RpcFree` at `0x18002032d`
- `RPCRT4!I_RpcFree` at `0x180020493`
- `RPCRT4!I_RpcFree` at `0x180020588`
- `RPCRT4!I_RpcFree` at `0x1800205c5`
- `RPCRT4!I_RpcFree` at `0x1800205fe`
- `RPCRT4!I_RpcFree` at `0x180020613`
- `RPCRT4!I_RpcFree` at `0x180020624`
- `RPCRT4!I_RpcFree` at `0x180020639`
- `RPCRT4!I_RpcFree` at `0x180020692`
- `RPCRT4!I_RpcAllocate` at `0x18001fd93`
- `RPCRT4!I_RpcAllocate` at `0x18001ffc4`
- `RPCRT4!I_RpcAllocate` at `0x18002002f`
- `RPCRT4!I_RpcAllocate` at `0x1800201dd`
- `RPCRT4!I_RpcAllocate` at `0x1800201f7`
- `RPCRT4!I_RpcAllocate` at `0x180020273`
- `RPCRT4!I_RpcAllocate` at `0x180020302`
- `RPCRT4!I_RpcAllocate` at `0x18001fd93`
- `RPCRT4!I_RpcAllocate` at `0x18001ffc4`
- `RPCRT4!I_RpcAllocate` at `0x18002002f`
- `RPCRT4!I_RpcAllocate` at `0x1800201dd`
- `RPCRT4!I_RpcAllocate` at `0x1800201f7`
- `RPCRT4!I_RpcAllocate` at `0x180020273`
- `RPCRT4!I_RpcAllocate` at `0x180020302`

## pseudocode

```c
__int64 __fastcall EstablishNewSession(
        struct tagI_RpcProxyCallbackInterface *a1,
        void *a2,
        struct _GUID *a3,
        struct _GUID *a4,
        int a5,
        int a6,
        struct LBSVirtualChannelState **a7,
        unsigned __int16 **a8,
        unsigned __int16 *a9)
{
  bool v10; // zf
  void *v12; // r11
  int v13; // r12d
  unsigned int v14; // eax
  unsigned int v15; // ebx
  unsigned __int16 v16; // r8
  unsigned int v17; // edx
  unsigned int v18; // eax
  struct _RTL_CRITICAL_SECTION *v19; // rax
  signed __int64 v20; // rbx
  struct LB_RPCHTTP_SERVER **v21; // r13
  unsigned int v22; // edi
  struct LBSVirtualChannelState *v23; // rsi
  BOOL v24; // edx
  unsigned __int64 v25; // rcx
  struct _GUID *v26; // r10
  BOOL *v27; // r9
  BOOL *v28; // rdx
  struct _GUID *v29; // r8
  unsigned int v30; // eax
  unsigned __int16 v31; // r8
  unsigned int v32; // r12d
  _DWORD *v33; // r15
  int v34; // eax
  unsigned int v35; // r14d
  unsigned int ConfiguredSet; // eax
  unsigned int v37; // eax
  unsigned int v38; // eax
  unsigned int v39; // r9d
  unsigned int v40; // r8d
  unsigned int v41; // eax
  unsigned int v42; // r10d
  unsigned int i; // ecx
  __int64 v44; // rax
  unsigned int j; // r8d
  unsigned int v46; // r9d
  unsigned int k; // ecx
  __int64 v48; // rcx
  unsigned int m; // ecx
  __int64 v50; // r8
  signed int v51; // eax
  unsigned int n; // ecx
  __int64 v53; // rbx
  unsigned __int16 *v54; // r15
  unsigned int v55; // ebx
  struct LB_RPCHTTP_SERVER **v56; // rsi
  unsigned int v57; // edx
  unsigned int ii; // eax
  LB_RPCHTTP_SERVER *v59; // rcx
  unsigned int v60; // eax
  struct LBSVirtualChannelState *v61; // rax
  struct LB_RPCHTTP_SERVER **v62; // rbx
  LB_ARBITRATOR *v63; // rax
  LB_ARBITRATOR *v64; // rax
  LB_ARBITRATOR *v65; // r14
  void *v66; // rax
  void *v67; // r15
  __int64 v68; // rcx
  __int64 v69; // rcx
  __int16 v70; // r15
  unsigned __int16 v71; // ax
  unsigned int v72; // r10d
  unsigned int v73; // r9d
  void **v74; // r11
  __int64 v75; // r8
  unsigned __int16 *v76; // r14
  unsigned __int16 **v77; // rcx
  _WORD *v78; // rax
  unsigned __int16 *v79; // r14
  __int64 v80; // rdx
  __int64 v81; // rcx
  unsigned int jj; // r14d
  struct LB_RPCHTTP_SERVER **v83; // rdx
  unsigned int kk; // edi
  LB_RPCHTTP_SERVER *v85; // rcx
  unsigned __int16 v87[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v88; // [rsp+44h] [rbp-BCh] BYREF
  void *v89; // [rsp+48h] [rbp-B8h]
  unsigned __int16 **v90; // [rsp+50h] [rbp-B0h]
  BOOL v91; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v92; // [rsp+5Ch] [rbp-A4h] BYREF
  GUID v93; // [rsp+60h] [rbp-A0h] BYREF
  BOOL v94; // [rsp+70h] [rbp-90h] BYREF
  int v95; // [rsp+74h] [rbp-8Ch] BYREF
  struct LB_RPCHTTP_SERVER **v96; // [rsp+78h] [rbp-88h]
  int v97; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v98; // [rsp+84h] [rbp-7Ch] BYREF
  struct LB_RPCHTTP_SERVER **v99; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v100; // [rsp+90h] [rbp-70h] BYREF
  LB_ARBITRATOR *v101; // [rsp+98h] [rbp-68h]
  void *v102; // [rsp+A0h] [rbp-60h]
  void **v103; // [rsp+A8h] [rbp-58h]
  void *Object; // [rsp+B0h] [rbp-50h]
  HANDLE Token; // [rsp+B8h] [rbp-48h] BYREF
  int v106; // [rsp+C0h] [rbp-40h]
  int v107; // [rsp+C4h] [rbp-3Ch]
  ULONG nSize; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int16 *v109; // [rsp+D0h] [rbp-30h] BYREF
  GUID ActivityId; // [rsp+E0h] [rbp-20h] BYREF
  struct tagI_RpcProxyCallbackInterface *v111; // [rsp+F0h] [rbp-10h]
  unsigned __int16 *v112; // [rsp+F8h] [rbp-8h]
  struct LBSVirtualChannelState **v113; // [rsp+100h] [rbp+0h]
  struct _GUID v114; // [rsp+108h] [rbp+8h] BYREF
  struct _GUID v115; // [rsp+118h] [rbp+18h] BYREF

  v107 = a5;
  v10 = g_LBClientInitialized == 0;
  v106 = a6;
  v111 = a1;
  v12 = a2;
  v13 = 0;
  v113 = a7;
  v112 = a9;
  v102 = a2;
  v90 = a8;
  v115 = 0;
  v91 = 0;
  v114 = 0;
  v94 = 0;
  v100 = 0;
  v87[0] = 0;
  v98 = 0;
  v97 = 0;
  v95 = 0;
  v109 = 0;
  Token = 0;
  nSize = 260;
  *(_QWORD *)&v93.Data1 = 0;
  *(_QWORD *)v93.Data4 = 0;
  *a8 = 0;
  if ( v10 )
  {
    v14 = RevertAndSaveToken(&Token);
    v15 = v14;
    if ( v14 )
    {
      v16 = 4100;
      v17 = v14;
LABEL_4:
      CompRpcpErrorAddRecord(0xFu, v17, v16);
      goto LABEL_171;
    }
    v18 = InitializeConfigurationManager();
    v15 = v18;
    if ( v18 )
    {
      if ( v18 - 1726 <= 1 || v18 == 258 || v18 == 1753 )
        v15 = 1722;
      v16 = 4101;
      goto LABEL_11;
    }
    if ( !g_pAbandonedCallManager )
    {
      v19 = (struct _RTL_CRITICAL_SECTION *)I_RpcAllocate(0x38u);
      v20 = (signed __int64)v19;
      if ( !v19 )
      {
        v15 = 14;
        v16 = 4102;
LABEL_11:
        v17 = v15;
        goto LABEL_4;
      }
      RtlInitializeCriticalSectionAndSpinCount(v19, 0xBB8u);
      *(_QWORD *)(v20 + 48) = v20 + 40;
      *(_QWORD *)(v20 + 40) = v20 + 40;
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_pAbandonedCallManager, v20, 0) )
      {
        RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)v20);
        I_RpcFree((void *)v20);
      }
    }
    v12 = v102;
    v13 = 1;
    g_LBClientInitialized = 1;
  }
  if ( !g_LBActive )
    goto LABEL_170;
  v101 = 0;
  v21 = 0;
  v99 = 0;
  v22 = 0;
  v92 = 0;
  v23 = 0;
  *(_QWORD *)&ActivityId.Data1 = 0;
  v103 = 0;
  Object = 0;
  v96 = 0;
  if ( a3 )
    v115 = *a3;
  v102 = 0;
  v24 = a3 != 0;
  v94 = v24;
  if ( a4 )
    v114 = *a4;
  v25 = a4 != 0;
  v91 = a4 != 0;
  if ( !a3 || !a4 )
  {
    v26 = &v114;
    v27 = &v91;
    v28 = &v94;
    if ( a4 )
    {
      v26 = 0;
      v27 = 0;
    }
    v29 = &v115;
    if ( a3 )
    {
      v29 = 0;
      v28 = 0;
    }
    v30 = ((__int64 (__fastcall *)(void *, BOOL *, struct _GUID *, BOOL *, struct _GUID *))v111->GetClientSessionAndResourceUUIDFn)(
            v12,
            v28,
            v29,
            v27,
            v26);
    v15 = v30;
    if ( v30 )
    {
      v31 = 4103;
LABEL_30:
      CompRpcpErrorAddRecord(0xFu, v30, v31);
LABEL_31:
      v32 = 0;
      v33 = 0;
      goto LABEL_143;
    }
    v25 = v91;
    v24 = v94;
  }
  v34 = 0;
  if ( !(_DWORD)v25 )
  {
    if ( !g_fAssumeResourceUUIDPresent )
      goto LABEL_170;
    v34 = 1;
    v91 = 1;
    v114 = g_AssumeResourceUUID;
  }
  if ( !v24 )
  {
    v15 = v34 == 0 ? 0x6C0 : 0;
    goto LABEL_31;
  }
  if ( v13 )
  {
    v35 = 0;
  }
  else
  {
    v30 = RevertAndSaveToken(&Token);
    v35 = 0;
    v15 = v30;
    if ( v30 )
    {
      v31 = 4104;
      goto LABEL_30;
    }
  }
  ConfiguredSet = LB_CONFIGURATION_MANAGER::GetConfiguredSet((LB_CONFIGURATION_MANAGER *)v25, &v114, &v92, &v99);
  v15 = ConfiguredSet;
  if ( ConfiguredSet == 1168 )
  {
LABEL_170:
    v15 = 0;
    goto LABEL_171;
  }
  if ( ConfiguredSet )
  {
    v21 = 0;
    CompRpcpErrorAddRecord(0xFu, ConfiguredSet, 0x1009u, v114.Data1);
    v22 = v92;
    goto LABEL_31;
  }
  v22 = v92;
  if ( !v92 )
  {
    v15 = 1722;
    CompRpcpErrorAddRecord(0xFu, 0x6BAu, 0x100Au, v114.Data1);
    v21 = v99;
    goto LABEL_31;
  }
  v37 = 16 * v92;
  if ( !is_mul_ok(v92, 0x10u) )
    v37 = -1;
  v89 = I_RpcAllocate(v37);
  v33 = v89;
  if ( v89 )
  {
    v32 = g_NumberOfServersInRelevantSet;
    if ( !g_NumberOfServersInRelevantSet )
    {
      v38 = UlongSqrt(v22);
      if ( v38 <= v40 )
      {
        v38 = v22;
        if ( v22 > v39 )
          v38 = v39;
      }
      v32 = v38 + 1;
    }
    if ( v32 > v22 )
      v32 = v22;
    v41 = 8 * v32;
    if ( !is_mul_ok(v32, 8u) )
      v41 = -1;
    v96 = (struct LB_RPCHTTP_SERVER **)I_RpcAllocate(v41);
    if ( v96 )
    {
      v42 = 0;
      for ( i = 0; i < v22; v33[4 * v44 + 2] = 0 )
        v44 = i++;
      v21 = v99;
      for ( j = v22; j; --j )
      {
        v46 = 0;
        for ( k = 0; k < v22; ++k )
        {
          if ( !v33[4 * k + 2]
            && (*((_DWORD *)v21[k] + 9)
              ^ *((_DWORD *)v21[k] + 10)
              ^ (unsigned int)(*((_DWORD *)v21[k] + 11) ^ *((_DWORD *)v21[k] + 12))) >= v46 )
          {
            v46 = *((_DWORD *)v21[k] + 9)
                ^ *((_DWORD *)v21[k] + 10)
                ^ *((_DWORD *)v21[k] + 11)
                ^ *((_DWORD *)v21[k] + 12);
            v42 = k;
          }
        }
        v48 = 2LL * v42;
        v33[2 * v48 + 1] = v22 - j;
        v33[2 * v48 + 2] = 1;
      }
      for ( m = 0; m < v22; v33[2 * v50 + 3] = 0 )
      {
        v50 = 2LL * m;
        v51 = v33[4 * m + 1]
            - (unsigned int)((*(unsigned int *)&v115.Data4[4]
                            ^ (unsigned __int64)(*(_DWORD *)v115.Data4 ^ *(_DWORD *)&v115.Data2 ^ v115.Data1))
                           / v22)
            % v22;
        if ( v51 < 0 )
          v51 += v22;
        ++m;
        v33[2 * v50] = v51;
      }
      for ( n = 0; n < v22; ++n )
      {
        v53 = n;
        if ( *((_DWORD *)v21[n] + 51) )
        {
          _mm_lfence();
          v100 = DuplicateString(*((const unsigned __int16 **)v21[n] + 3));
          v54 = v100;
          if ( v100 )
          {
            _mm_lfence();
            v87[0] = *((_WORD *)v21[v53] + 16);
            goto LABEL_83;
          }
          goto LABEL_141;
        }
      }
      v54 = v100;
LABEL_83:
      v55 = 0;
      if ( v32 )
      {
        v56 = v96;
        do
        {
          v57 = 0;
          for ( ii = 0; ii < v22; ++ii )
          {
            if ( !*((_DWORD *)v89 + 4 * ii + 3) && *((_DWORD *)v89 + 4 * ii) >= v57 )
            {
              v57 = *((_DWORD *)v89 + 4 * ii);
              v35 = ii;
            }
          }
          *((_DWORD *)v89 + 4 * v35 + 3) = 1;
          v59 = v21[v35];
          v56[v55] = v59;
          LB_RPCHTTP_SERVER::AddReference(v59);
          ++v55;
        }
        while ( v55 < v32 );
        v23 = *(struct LBSVirtualChannelState **)&ActivityId.Data1;
      }
      v60 = 8 * v32;
      if ( !is_mul_ok(v32, 8u) )
        v60 = -1;
      v103 = (void **)I_RpcAllocate(v60);
      if ( v103 )
      {
        v61 = (struct LBSVirtualChannelState *)I_RpcAllocate(0x28u);
        v23 = v61;
        if ( !v61 )
        {
          v23 = 0;
          goto LABEL_141;
        }
        *(_DWORD *)v61 = 1;
        *((_QWORD *)v61 + 1) = 0;
        *((_DWORD *)v61 + 4) = 0;
        *((_QWORD *)v61 + 3) = 0;
        *((_QWORD *)v61 + 4) = 0;
        v88 = LBSVirtualChannelState::Initialize(v61, v32);
        v15 = v88;
        if ( !v88 )
        {
          v62 = v96;
          if ( !v54 )
          {
            v100 = DuplicateString(*((const unsigned __int16 **)*v96 + 3));
            v54 = v100;
            if ( !v100 )
              goto LABEL_141;
            v87[0] = *((_WORD *)*v62 + 16);
          }
          Object = v54;
          v63 = (LB_ARBITRATOR *)I_RpcAllocate(0x70u);
          if ( !v63 )
          {
            v101 = 0;
            goto LABEL_141;
          }
          v64 = LB_ARBITRATOR::LB_ARBITRATOR(v63, v32, v62, v107, v106, &v115, v111, (int *)&v88);
          v101 = v64;
          v65 = v64;
          if ( !v64 )
            goto LABEL_141;
          v15 = v88;
          if ( v88 )
          {
            CompRpcpErrorAddRecord(0xFu, v88, 0x100Bu, v114.Data1);
            v101 = v65;
          }
          else
          {
            v93 = *(GUID *)((char *)v64 + 68);
            v66 = I_RpcAllocate(0x208u);
            v102 = v66;
            v67 = v66;
            if ( v66 && !GetUserNameExW(NameSamCompatible, (LPWSTR)v66, &nSize) )
            {
              I_RpcFree(v67);
              v67 = 0;
              v102 = 0;
            }
            ActivityId = v93;
            if ( !EventActivityIdControl(4u, &ActivityId) )
            {
              if ( (Microsoft_Windows_RPC_Proxy_LBSEnableBits & 1) != 0 )
                McTemplateU0z_EventWriteTransfer(v68, RpcProxyLbsArbitrationStart, v67);
              EventActivityIdControl(2u, &ActivityId);
            }
            v15 = LB_ARBITRATOR::PerformArbitration(v65, &v100, v87, &v97, &v95, &v98, v103);
            if ( v97 )
              v65 = 0;
            v101 = v65;
            if ( v95 )
            {
              if ( v65 )
              {
                if ( !(unsigned int)LB_ARBITRATOR::GetServersInRelevantSet(v65, &v109) )
                {
                  ActivityId = v93;
                  if ( !EventActivityIdControl(4u, &ActivityId) )
                  {
                    if ( (Microsoft_Windows_RPC_Proxy_LBSEnableBits & 2) != 0 )
                      McTemplateU0zz_EventWriteTransfer(v69, 0, v67, v109);
                    EventActivityIdControl(2u, &ActivityId);
                  }
                }
              }
            }
            if ( !v15 )
            {
              v70 = 593;
              if ( *v112 != 593 )
              {
                v71 = v87[0];
                if ( !v87[0] )
                  v71 = *v112;
                v70 = v71;
              }
              v72 = v98;
              v73 = 0;
              if ( v98 )
              {
                v74 = v103;
                do
                {
                  v75 = v73++;
                  *(_QWORD *)(*((_QWORD *)v23 + 1) + 144 * v75 + 112) = v74[v75];
                  v74[v75] = 0;
                }
                while ( v73 < v72 );
                v22 = v92;
              }
              v76 = v100;
              if ( Object != v100 )
              {
                I_RpcFree(Object);
                Object = 0;
              }
              v77 = v90;
              *v113 = v23;
              v23 = 0;
              v78 = v112;
              *v77 = v76;
              *v78 = v70;
              v33 = v89;
              goto LABEL_144;
            }
            if ( v15 - 1726 <= 1 || v15 == 6 || v15 == 2 || v15 == 1753 )
              v15 = 1722;
            CompRpcpErrorAddRecord(0xFu, v15, 0x100Cu, v114.Data1);
          }
        }
        v33 = v89;
        goto LABEL_143;
      }
LABEL_141:
      v33 = v89;
    }
    else
    {
      v21 = v99;
    }
  }
  else
  {
    v21 = v99;
    v32 = 0;
  }
  v15 = 14;
LABEL_143:
  v77 = v90;
LABEL_144:
  v79 = *v77;
  if ( !EventActivityIdControl(4u, &v93) )
  {
    if ( (Microsoft_Windows_RPC_Proxy_LBSEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v81, v80, v79, v15);
    EventActivityIdControl(2u, &v93);
  }
  for ( jj = 0; jj < v22; ++jj )
    LB_RPCHTTP_SERVER::RemoveReference(v21[jj]);
  if ( v21 )
    I_RpcFree(v21);
  v83 = v96;
  if ( v96 )
  {
    for ( kk = 0; kk < v32; ++kk )
    {
      v85 = v83[kk];
      if ( v85 )
      {
        LB_RPCHTTP_SERVER::RemoveReference(v85);
        v83 = v96;
      }
    }
    I_RpcFree(v83);
  }
  if ( v101 )
    LB_ARBITRATOR::`scalar deleting destructor'(v101, (unsigned int)v83);
  if ( v23 )
    LBSVirtualChannelState::`scalar deleting destructor'(v23, (unsigned int)v83);
  if ( v103 )
    I_RpcFree(v103);
  if ( Object )
    I_RpcFree(Object);
  if ( v33 )
    I_RpcFree(v33);
  if ( v102 )
    I_RpcFree(v102);
LABEL_171:
  if ( Token )
  {
    if ( !SetThreadToken(0, Token) )
    {
      GetLastError();
      RpcpReportFatalError(21);
      __debugbreak();
    }
    CloseHandle(Token);
  }
  if ( v95 && v109 )
    I_RpcFree(v109);
  return v15;
}

```

## disassembly

```asm
0x18001fc58  push    rbp
0x18001fc5a  push    rbx
0x18001fc5b  push    rsi
0x18001fc5c  push    rdi
0x18001fc5d  push    r12
0x18001fc5f  push    r13
0x18001fc61  push    r14
0x18001fc63  push    r15
0x18001fc65  lea     rbp, [rsp-38h]
0x18001fc6a  sub     rsp, 138h
0x18001fc71  mov     rax, cs:__security_cookie
0x18001fc78  xor     rax, rsp
0x18001fc7b  mov     [rbp+70h+var_48], rax
0x18001fc7f  mov     eax, [rbp+70h+arg_20]
0x18001fc85  mov     r14, r8
0x18001fc88  xor     r8d, r8d
0x18001fc8b  mov     [rbp+70h+var_AC], eax
0x18001fc8e  cmp     cs:?g_LBClientInitialized@@3HA, r8d; int g_LBClientInitialized
0x18001fc95  xorps   xmm0, xmm0
0x18001fc98  mov     eax, [rbp+70h+arg_28]
0x18001fc9e  xorps   xmm1, xmm1
0x18001fca1  mov     [rbp+70h+var_B0], eax
0x18001fca4  mov     r15, r9
0x18001fca7  mov     rax, [rbp+70h+arg_30]
0x18001fcae  lea     edi, [r8+1]
0x18001fcb2  mov     [rbp+70h+var_80], rcx
0x18001fcb6  mov     r11, rdx
0x18001fcb9  mov     rcx, [rbp+70h+arg_38]
0x18001fcc0  mov     r12d, r8d
0x18001fcc3  mov     [rbp+70h+var_70], rax
0x18001fcc7  mov     rax, [rbp+70h+arg_40]
0x18001fcce  mov     [rbp+70h+var_78], rax
0x18001fcd2  mov     [rbp+70h+var_D0], rdx
0x18001fcd6  mov     [rsp+170h+var_120], rcx
0x18001fcdb  movups  xmmword ptr [rbp+70h+var_58.Data1], xmm0
0x18001fcdf  mov     dword ptr [rsp+170h+var_118], r8d
0x18001fce4  movups  xmmword ptr [rbp+70h+var_68.Data1], xmm1
0x18001fce8  mov     [rsp+170h+var_100], r8d
0x18001fced  mov     [rbp+70h+var_E0], r8
0x18001fcf1  mov     [rsp+170h+var_130], r8w
0x18001fcf7  mov     [rbp+70h+var_EC], r8d
0x18001fcfb  mov     [rbp+70h+var_F0], r8d
0x18001fcff  mov     [rsp+170h+var_FC], r8d
0x18001fd04  mov     [rbp+70h+var_A0], r8
0x18001fd08  mov     [rbp+70h+Token], r8
0x18001fd0c  mov     [rbp+70h+nSize], 104h
0x18001fd13  mov     qword ptr [rsp+170h+var_110.Data1], r8
0x18001fd18  mov     qword ptr [rsp+170h+var_110.Data4], r8
0x18001fd1d  mov     [rcx], r8
0x18001fd20  jnz     loc_18001FDED
0x18001fd26  lea     rcx, [rbp+70h+Token]; void **
0x18001fd2a  call    ?RevertAndSaveToken@@YAJPEAPEAX@Z; RevertAndSaveToken(void * *)
0x18001fd2f  mov     ebx, eax
0x18001fd31  test    eax, eax
0x18001fd33  jz      short loc_18001FD4F
0x18001fd35  mov     r8d, 1004h; unsigned __int16
0x18001fd3b  mov     edx, eax; unsigned int
0x18001fd3d  mov     ecx, 0Fh; unsigned int
0x18001fd42  call    ?CompRpcpErrorAddRecord@@YAXKKG@Z; CompRpcpErrorAddRecord(ulong,ulong,ushort)
0x18001fd47  xor     r8d, r8d
0x18001fd4a  jmp     loc_18002064A
0x18001fd4f  call    ?InitializeConfigurationManager@@YAJXZ; InitializeConfigurationManager(void)
0x18001fd54  xor     r8d, r8d
0x18001fd57  mov     ebx, eax
0x18001fd59  test    eax, eax
0x18001fd5b  jz      short loc_18001FD85
0x18001fd5d  add     eax, 0FFFFF942h
0x18001fd62  cmp     eax, edi
0x18001fd64  jbe     short loc_18001FD76
0x18001fd66  cmp     ebx, 102h
0x18001fd6c  jz      short loc_18001FD76
0x18001fd6e  cmp     ebx, 6D9h
0x18001fd74  jnz     short loc_18001FD7B
0x18001fd76  mov     ebx, 6BAh
0x18001fd7b  mov     r8d, 1005h
0x18001fd81  mov     edx, ebx
0x18001fd83  jmp     short loc_18001FD3D
0x18001fd85  cmp     cs:?g_pAbandonedCallManager@@3PEAVLB_ABANDONED_CALL_MANAGER@@EA, r8; LB_ABANDONED_CALL_MANAGER * g_pAbandonedCallManager
0x18001fd8c  jnz     short loc_18001FDE0
0x18001fd8e  mov     ecx, 38h ; '8'; Size
0x18001fd93  call    cs:__imp_I_RpcAllocate
0x18001fd99  mov     rbx, rax
0x18001fd9c  test    rax, rax
0x18001fd9f  jz      loc_18001FECA
0x18001fda5  mov     edx, 0BB8h; SpinCount
0x18001fdaa  mov     rcx, rax; CriticalSection
0x18001fdad  call    cs:__imp_RtlInitializeCriticalSectionAndSpinCount
0x18001fdb3  lea     rax, [rbx+28h]
0x18001fdb7  mov     [rax+8], rax
0x18001fdbb  mov     [rax], rax
0x18001fdbe  xor     eax, eax
0x18001fdc0  lock cmpxchg cs:?g_pAbandonedCallManager@@3PEAVLB_ABANDONED_CALL_MANAGER@@EA, rbx; LB_ABANDONED_CALL_MANAGER * g_pAbandonedCallManager
0x18001fdc9  jz      short loc_18001FDDD
0x18001fdcb  mov     rcx, rbx; CriticalSection
0x18001fdce  call    cs:__imp_RtlDeleteCriticalSection
0x18001fdd4  mov     rcx, rbx; Object
0x18001fdd7  call    cs:__imp_I_RpcFree
0x18001fddd  xor     r8d, r8d
0x18001fde0  mov     r11, [rbp+70h+var_D0]
0x18001fde4  mov     r12d, edi
0x18001fde7  mov     cs:?g_LBClientInitialized@@3HA, edi; int g_LBClientInitialized
0x18001fded  cmp     cs:?g_LBActive@@3HA, r8d; int g_LBActive
0x18001fdf4  jz      loc_180020647
0x18001fdfa  mov     [rbp+70h+var_D8], r8
0x18001fdfe  mov     r13, r8
0x18001fe01  mov     [rbp+70h+var_E8], r8
0x18001fe05  mov     edi, r8d
0x18001fe08  mov     dword ptr [rsp+170h+var_118+4], r8d
0x18001fe0d  mov     rsi, r8
0x18001fe10  mov     qword ptr [rbp+70h+ActivityId.Data1], r8
0x18001fe14  mov     [rbp+70h+var_C8], r8
0x18001fe18  mov     [rbp+70h+Object], r8
0x18001fe1c  mov     [rsp+170h+var_F8], r8
0x18001fe21  test    r14, r14
0x18001fe24  jz      short loc_18001FE2F
0x18001fe26  movups  xmm0, xmmword ptr [r14]
0x18001fe2a  movdqu  xmmword ptr [rbp+70h+var_58.Data1], xmm0
0x18001fe2f  test    r14, r14
0x18001fe32  mov     [rbp+70h+var_D0], r8
0x18001fe36  mov     edx, r8d
0x18001fe39  setnz   dl
0x18001fe3c  mov     [rsp+170h+var_100], edx
0x18001fe40  test    r15, r15
0x18001fe43  jz      short loc_18001FE4E
0x18001fe45  movups  xmm0, xmmword ptr [r15]
0x18001fe49  movdqu  xmmword ptr [rbp+70h+var_68.Data1], xmm0
0x18001fe4e  test    r15, r15
0x18001fe51  mov     ecx, r8d
0x18001fe54  setnz   cl
0x18001fe57  mov     dword ptr [rsp+170h+var_118], ecx
0x18001fe5b  test    r14, r14
0x18001fe5e  jz      short loc_18001FE65
0x18001fe60  test    r15, r15
0x18001fe63  jnz     short loc_18001FEE2
0x18001fe65  mov     rax, [rbp+70h+var_80]
0x18001fe69  lea     r10, [rbp+70h+var_68]
0x18001fe6d  test    r15, r15
0x18001fe70  lea     r9, [rsp+170h+var_118]
0x18001fe75  lea     rdx, [rsp+170h+var_100]
0x18001fe7a  cmovnz  r10, r8
0x18001fe7e  cmovnz  r9, r8
0x18001fe82  mov     rax, [rax+28h]
0x18001fe86  lea     r8, [rbp+70h+var_58]
0x18001fe8a  xor     ecx, ecx
0x18001fe8c  mov     [rsp+170h+var_150], r10
0x18001fe91  test    r14, r14
0x18001fe94  cmovnz  r8, rcx
0x18001fe98  cmovnz  rdx, rcx
0x18001fe9c  mov     rcx, r11
0x18001fe9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fea4  xor     r8d, r8d
0x18001fea7  mov     ebx, eax
0x18001fea9  test    eax, eax
0x18001feab  jz      short loc_18001FEDA
0x18001fead  mov     r8d, 1007h; unsigned __int16
0x18001feb3  mov     edx, eax; unsigned int
0x18001feb5  mov     ecx, 0Fh; unsigned int
0x18001feba  call    ?CompRpcpErrorAddRecord@@YAXKKG@Z; CompRpcpErrorAddRecord(ulong,ulong,ushort)
0x18001febf  mov     r12d, esi
0x18001fec2  mov     r15, rsi
0x18001fec5  jmp     loc_180020510
0x18001feca  mov     ebx, 0Eh
0x18001fecf  mov     r8d, 1006h
0x18001fed5  jmp     loc_18001FD81
0x18001feda  mov     ecx, dword ptr [rsp+170h+var_118]; this
0x18001fede  mov     edx, [rsp+170h+var_100]
0x18001fee2  mov     eax, r8d
0x18001fee5  test    ecx, ecx
0x18001fee7  jnz     short loc_18001FF09
0x18001fee9  cmp     cs:?g_fAssumeResourceUUIDPresent@@3HA, r8d; int g_fAssumeResourceUUIDPresent
0x18001fef0  jz      loc_180020647
0x18001fef6  movups  xmm0, xmmword ptr cs:?g_AssumeResourceUUID@@3U_GUID@@A.Data1; _GUID g_AssumeResourceUUID ...
0x18001fefd  lea     eax, [rcx+1]
0x18001ff00  mov     dword ptr [rsp+170h+var_118], eax
0x18001ff04  movdqu  xmmword ptr [rbp+70h+var_68.Data1], xmm0
0x18001ff09  test    edx, edx
0x18001ff0b  jnz     short loc_18001FF1B
0x18001ff0d  neg     eax
0x18001ff0f  sbb     ebx, ebx
0x18001ff11  not     ebx
0x18001ff13  and     ebx, 6C0h
0x18001ff19  jmp     short loc_18001FEBF
0x18001ff1b  test    r12d, r12d
0x18001ff1e  jnz     short loc_18001FF3D
0x18001ff20  lea     rcx, [rbp+70h+Token]; void **
0x18001ff24  call    ?RevertAndSaveToken@@YAJPEAPEAX@Z; RevertAndSaveToken(void * *)
0x18001ff29  xor     r14d, r14d
0x18001ff2c  mov     ebx, eax
0x18001ff2e  test    eax, eax
0x18001ff30  jz      short loc_18001FF40
0x18001ff32  mov     r8d, 1008h
0x18001ff38  jmp     loc_18001FEB3
0x18001ff3d  xor     r14d, r14d
0x18001ff40  lea     r9, [rbp+70h+var_E8]; struct LB_RPCHTTP_SERVER ***
0x18001ff44  lea     r8, [rsp+170h+var_118+4]; unsigned int *
0x18001ff49  lea     rdx, [rbp+70h+var_68]; struct _GUID *
0x18001ff4d  call    ?GetConfiguredSet@LB_CONFIGURATION_MANAGER@@QEAAJPEAU_GUID@@PEAKPEAPEAPEAVLB_RPCHTTP_SERVER@@@Z; LB_CONFIGURATION_MANAGER::GetConfiguredSet(_GUID *,ulong *,LB_RPCHTTP_SERVER * * *)
0x18001ff52  mov     ebx, eax
0x18001ff54  cmp     eax, 490h
0x18001ff59  jz      loc_180020644
0x18001ff5f  test    eax, eax
0x18001ff61  jz      short loc_18001FF85
0x18001ff63  mov     r9d, [rbp+70h+var_68.Data1]; unsigned int
0x18001ff67  mov     r8d, 1009h; unsigned __int16
0x18001ff6d  mov     edx, eax; unsigned int
0x18001ff6f  mov     ecx, 0Fh; unsigned int
0x18001ff74  mov     r13, r14
0x18001ff77  call    ?CompRpcpErrorAddRecord@@YAXKKGK@Z; CompRpcpErrorAddRecord(ulong,ulong,ushort,ulong)
0x18001ff7c  mov     edi, dword ptr [rsp+170h+var_118+4]
0x18001ff80  jmp     loc_18001FEBF
0x18001ff85  mov     edi, dword ptr [rsp+170h+var_118+4]
0x18001ff89  test    edi, edi
0x18001ff8b  jnz     short loc_18001FFAF
0x18001ff8d  mov     r9d, [rbp+70h+var_68.Data1]; unsigned int
0x18001ff91  lea     ecx, [rdi+0Fh]; unsigned int
0x18001ff94  mov     ebx, 6BAh
0x18001ff99  mov     r8d, 100Ah; unsigned __int16
0x18001ff9f  mov     edx, ebx; unsigned int
0x18001ffa1  call    ?CompRpcpErrorAddRecord@@YAXKKGK@Z; CompRpcpErrorAddRecord(ulong,ulong,ushort,ulong)
0x18001ffa6  mov     r13, [rbp+70h+var_E8]
0x18001ffaa  jmp     loc_18001FEBF
0x18001ffaf  mov     eax, 10h
0x18001ffb4  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18001ffbb  mul     rdi
0x18001ffbe  cmovb   rax, rbx
0x18001ffc2  mov     ecx, eax; Size
0x18001ffc4  call    cs:__imp_I_RpcAllocate
0x18001ffca  mov     [rsp+170h+var_128], rax
0x18001ffcf  mov     r15, rax
0x18001ffd2  test    rax, rax
0x18001ffd5  jnz     short loc_18001FFE3
0x18001ffd7  mov     r13, [rbp+70h+var_E8]
0x18001ffdb  mov     r12d, esi
0x18001ffde  jmp     loc_18002050B
0x18001ffe3  mov     r12d, cs:?g_NumberOfServersInRelevantSet@@3KA; ulong g_NumberOfServersInRelevantSet
0x18001ffea  test    r12d, r12d
0x18001ffed  jnz     short loc_180020017
0x18001ffef  lea     r9d, [r12+3]
0x18001fff4  mov     r8d, edi
0x18001fff7  cmp     edi, r9d
0x18001fffa  mov     ecx, edi; unsigned int
0x18001fffc  cmova   r8d, r9d
0x180020000  call    ?UlongSqrt@@YAKK@Z; UlongSqrt(ulong)
0x180020005  cmp     eax, r8d
0x180020008  ja      short loc_180020013
0x18002000a  cmp     edi, r9d
0x18002000d  mov     eax, edi
0x18002000f  cmova   eax, r9d
0x180020013  lea     r12d, [rax+1]
0x180020017  cmp     r12d, edi
0x18002001a  mov     eax, 8
0x18002001f  cmova   r12d, edi
0x180020023  mov     ecx, r12d
0x180020026  mul     rcx
0x180020029  cmovb   rax, rbx
0x18002002d  mov     ecx, eax; Size
0x18002002f  call    cs:__imp_I_RpcAllocate
0x180020035  mov     [rsp+170h+var_F8], rax
0x18002003a  test    rax, rax
0x18002003d  jnz     short loc_180020048
0x18002003f  mov     r13, [rbp+70h+var_E8]
0x180020043  jmp     loc_18002050B
0x180020048  mov     r10d, r14d
0x18002004b  mov     ecx, r14d
0x18002004e  test    edi, edi
0x180020050  jz      short loc_180020062
0x180020052  mov     eax, ecx
0x180020054  inc     ecx
0x180020056  add     rax, rax
0x180020059  mov     [r15+rax*8+8], r14d
0x18002005e  cmp     ecx, edi
0x180020060  jb      short loc_180020052
0x180020062  mov     r13, [rbp+70h+var_E8]
0x180020066  mov     r8d, edi
0x180020069  test    edi, edi
0x18002006b  jz      short loc_1800200C6
0x18002006d  mov     r9d, r14d
0x180020070  mov     ecx, r14d
0x180020073  test    edi, edi
0x180020075  jz      short loc_1800200A7
0x180020077  mov     eax, ecx
0x180020079  add     rax, rax
0x18002007c  mov     edx, ecx
0x18002007e  cmp     [r15+rax*8+8], r14d
0x180020083  jnz     short loc_1800200A1
0x180020085  mov     rax, [r13+rdx*8+0]
0x18002008a  mov     edx, [rax+30h]
0x18002008d  xor     edx, [rax+2Ch]
0x180020090  xor     edx, [rax+28h]
0x180020093  xor     edx, [rax+24h]
0x180020096  cmp     edx, r9d
0x180020099  jb      short loc_1800200A1
0x18002009b  mov     r9d, edx
0x18002009e  mov     r10d, ecx
0x1800200a1  inc     ecx
0x1800200a3  cmp     ecx, edi
0x1800200a5  jb      short loc_180020077
0x1800200a7  mov     ecx, r10d
0x1800200aa  mov     eax, edi
0x1800200ac  add     rcx, rcx
  ... truncated ...
```
