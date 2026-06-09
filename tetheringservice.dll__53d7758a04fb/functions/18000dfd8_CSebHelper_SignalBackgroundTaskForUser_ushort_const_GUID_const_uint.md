# CSebHelper::SignalBackgroundTaskForUser(ushort const *,_GUID const &,uint)

- ea: `0x18000dfd8`
- end: `0x18000e521`
- name: `?SignalBackgroundTaskForUser@CSebHelper@@SAJPEBGAEBU_GUID@@I@Z`
- size: `1353`
- prototype: `__int64 __fastcall(const unsigned __int16 *, GUID *rguid, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000eb20`

## callees

- `0x180002590`
- `0x180002960`
- `0x180003088`
- `0x18000bf4c`
- `0x18000bf74`
- `0x18000dfd8`
- `0x180027130`
- `0x1800272c0`
- `0x180027394`
- `0x18002a3c8`
- `0x18002c5c0`
- `0x18002c7bc`
- `0x18002cb44`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e39c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e39c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e1a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e36f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e40f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e1a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e36f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e40f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e1ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e37d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e41d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e1ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e37d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e41d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e198`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e367`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e198`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e367`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e1b6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e385`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e1b6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e385`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000e22d`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000e22d`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000e1e5`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000e1e5`
- `SystemEventsBrokerClient!SebQueryEventPackage` at `0x18000e177`
- `SystemEventsBrokerClient!SebQueryEventPackage` at `0x18000e177`
- `SystemEventsBrokerClient!SebSignalEvent` at `0x18000e275`
- `SystemEventsBrokerClient!SebSignalEvent` at `0x18000e275`
- `MobileNetworking!GetNetworkAccountIdBoundToInterfaceId` at `0x18000e20c`
- `MobileNetworking!GetNetworkAccountIdBoundToInterfaceId` at `0x18000e20c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CSebHelper::SignalBackgroundTaskForUser(const unsigned __int16 *a1, GUID *rguid, int a3)
{
  int v3; // r14d
  int SimIccidForInterfaceGuidInternal; // edi
  void *v7; // rdx
  TetheringServiceTelemetry *v8; // rax
  __int128 v9; // xmm6
  __int64 v10; // r12
  _QWORD *v11; // r14
  void *v12; // r15
  DWORD LastError; // ebx
  HANDLE ProcessHeap; // rax
  TetheringServiceTelemetry *v15; // rcx
  __int64 v16; // rdx
  int Session; // ebx
  TetheringServiceTelemetry *v18; // rcx
  LPVOID *v19; // rsi
  LPVOID v20; // r15
  void *v21; // r14
  DWORD v22; // ebx
  HANDLE v23; // rax
  struct TetheringSessionTelemetry *v24; // rcx
  void *v25; // rbx
  HANDLE v26; // rax
  __int64 v27; // rdx
  bool v29[8]; // [rsp+28h] [rbp-E0h] BYREF
  struct TetheringSessionTelemetry *v30; // [rsp+30h] [rbp-D8h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-D0h] BYREF
  __int128 v32; // [rsp+48h] [rbp-C0h] BYREF
  char v33; // [rsp+58h] [rbp-B0h]
  void *Block; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD pclsid[3]; // [rsp+70h] [rbp-98h] BYREF
  _OWORD v36[3]; // [rsp+88h] [rbp-80h] BYREF
  int v37; // [rsp+B8h] [rbp-50h]
  OLECHAR v38[24]; // [rsp+C8h] [rbp-40h] BYREF
  LPVOID *v39; // [rsp+F8h] [rbp-10h]
  unsigned __int16 v40[24]; // [rsp+118h] [rbp+10h] BYREF
  OLECHAR sz[40]; // [rsp+148h] [rbp+40h] BYREF

  v3 = a3;
  LODWORD(v30) = a3;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_77a2c26801653a0753b5e21a86582ed6_Traceguids);
  }
  *(GUID *)&pclsid[1] = *rguid;
  SimIccidForInterfaceGuidInternal = TetheringGetSimIccidForInterfaceGuidInternal((struct _GUID *)&pclsid[1], v40);
  if ( SimIccidForInterfaceGuidInternal >= 0 )
  {
    Block = 0;
    *(_QWORD *)&v32 = &Block;
    *((_QWORD *)&v32 + 1) = 0;
    v33 = 1;
    SimIccidForInterfaceGuidInternal = GetUAPEntitlementAppAMUID(v40, (unsigned __int16 **)&v32 + 1);
    if ( v33 )
    {
      v7 = *(void **)v32;
      *(_QWORD *)v32 = *((_QWORD *)&v32 + 1);
      if ( v7 )
        operator delete(v7);
    }
    if ( SimIccidForInterfaceGuidInternal < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_66;
      }
      v27 = 23;
    }
    else
    {
      *(_OWORD *)&pclsid[1] = 0;
      SimIccidForInterfaceGuidInternal = GetTaskGuidFromRegistryForAppForUser(
                                           a1,
                                           (const unsigned __int16 *)Block,
                                           (struct _GUID *)&pclsid[1]);
      if ( SimIccidForInterfaceGuidInternal < 0 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_66;
        }
        v27 = 22;
      }
      else
      {
        v29[0] = 0;
        SimIccidForInterfaceGuidInternal = IsSebBackgroundTaskRegistered((const struct _GUID *)&pclsid[1], v29);
        if ( SimIccidForInterfaceGuidInternal >= 0 )
        {
          if ( !v29[0] )
          {
            SimIccidForInterfaceGuidInternal = -2095972329;
            v8 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_77a2c26801653a0753b5e21a86582ed6_Traceguids);
LABEL_65:
              v8 = WPP_GLOBAL_Control;
            }
LABEL_66:
            if ( Block )
            {
              operator delete(Block);
LABEL_71:
              v8 = WPP_GLOBAL_Control;
              goto LABEL_72;
            }
            goto LABEL_72;
          }
          lpMem = 0;
          *(_QWORD *)&v32 = &lpMem;
          *((_QWORD *)&v32 + 1) = 0;
          v33 = 1;
          v9 = *(_OWORD *)&pclsid[1];
          SimIccidForInterfaceGuidInternal = SebQueryEventPackage(&pclsid[1], (char *)&v32 + 8);
          if ( v33 )
          {
            v10 = *((_QWORD *)&v32 + 1);
            v11 = (_QWORD *)v32;
            v12 = *(void **)v32;
            if ( *(_QWORD *)v32 )
            {
              LastError = GetLastError();
              ProcessHeap = GetProcessHeap();
              HeapFree(ProcessHeap, 0, v12);
              SetLastError(LastError);
            }
            *v11 = v10;
            v3 = (int)v30;
          }
          if ( SimIccidForInterfaceGuidInternal < 0 )
          {
            v8 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                20,
                &WPP_77a2c26801653a0753b5e21a86582ed6_Traceguids,
                (unsigned int)SimIccidForInterfaceGuidInternal);
              v8 = WPP_GLOBAL_Control;
            }
            goto LABEL_53;
          }
          if ( !StringFromGUID2(rguid, sz, 40) )
            goto LABEL_34;
          memset_0(v38, 0, 0x50u);
          SimIccidForInterfaceGuidInternal = GetNetworkAccountIdBoundToInterfaceId(sz, 40, v38);
          if ( SimIccidForInterfaceGuidInternal < 0 )
          {
            v8 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              goto LABEL_35;
            }
            v16 = 19;
          }
          else
          {
            *(_OWORD *)&pclsid[1] = 0;
            SimIccidForInterfaceGuidInternal = CLSIDFromString(v38, (LPCLSID)&pclsid[1]);
            if ( SimIccidForInterfaceGuidInternal < 0 )
            {
              v8 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              {
                goto LABEL_35;
              }
              v16 = 18;
            }
            else
            {
              v36[0] = xmmword_180036F58;
              v36[1] = *(_OWORD *)&pclsid[1];
              v36[2] = *rguid;
              v37 = v3;
              v32 = v9;
              SimIccidForInterfaceGuidInternal = SebSignalEvent(&v32, v36, 52, lpMem);
              if ( SimIccidForInterfaceGuidInternal >= 0 )
              {
LABEL_34:
                v8 = WPP_GLOBAL_Control;
LABEL_35:
                v30 = 0;
                if ( g_lTraceLoggingRegistered >= 0 && *(_QWORD *)&g_pTetheringSessionId.Data1 )
                {
                  Session = TetheringServiceTelemetry::GetSession(
                              v15,
                              *(struct _GUID **)&g_pTetheringSessionId.Data1,
                              &v30);
                  if ( (Session < 0 || v30 && TetheringSessionTelemetry::Initialized((RTL_SRWLOCK *)v30))
                    && Session >= 0 )
                  {
                    memset_0(v38, 0, 0x50u);
                    TetheringServiceTelemetry::AcquireSessionData(
                      v18,
                      (RTL_SRWLOCK *)v30,
                      (struct TetheringServiceTelemetry::SESSION_DATA *)v38);
                    v19 = v39;
                    if ( v39 != &lpMem )
                    {
                      v20 = lpMem;
                      v21 = *v39;
                      if ( *v39 )
                      {
                        v22 = GetLastError();
                        v23 = GetProcessHeap();
                        HeapFree(v23, 0, v21);
                        SetLastError(v22);
                      }
                      *v19 = v20;
                      lpMem = 0;
                    }
                    ReleaseSRWLockExclusive((PSRWLOCK)v30 + 2);
                  }
                  v8 = WPP_GLOBAL_Control;
                }
                v24 = v30;
                if ( v30 )
                {
                  v30 = 0;
                  (*(void (__fastcall **)(struct TetheringSessionTelemetry *))(*(_QWORD *)v24 + 16LL))(v24);
                  v8 = WPP_GLOBAL_Control;
                }
LABEL_53:
                v25 = lpMem;
                if ( !lpMem )
                  goto LABEL_66;
                v26 = GetProcessHeap();
                HeapFree(v26, 0, v25);
                goto LABEL_65;
              }
              v8 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              {
                goto LABEL_35;
              }
              v16 = 17;
            }
          }
          WPP_SF_d(
            *((_QWORD *)v8 + 2),
            v16,
            &WPP_77a2c26801653a0753b5e21a86582ed6_Traceguids,
            (unsigned int)SimIccidForInterfaceGuidInternal);
          goto LABEL_34;
        }
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_66;
        }
        v27 = 21;
      }
    }
    WPP_SF_d(
      *((_QWORD *)v8 + 2),
      v27,
      &WPP_77a2c26801653a0753b5e21a86582ed6_Traceguids,
      (unsigned int)SimIccidForInterfaceGuidInternal);
    goto LABEL_65;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
    return (unsigned int)SimIccidForInterfaceGuidInternal;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      &WPP_77a2c26801653a0753b5e21a86582ed6_Traceguids,
      (unsigned int)SimIccidForInterfaceGuidInternal);
    goto LABEL_71;
  }
LABEL_72:
  if ( v8 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)v8 + 2),
      25,
      &WPP_77a2c26801653a0753b5e21a86582ed6_Traceguids,
      (unsigned int)SimIccidForInterfaceGuidInternal);
  return (unsigned int)SimIccidForInterfaceGuidInternal;
}

```

## disassembly

```asm
0x18000dfd8  mov     rax, rsp
0x18000dfdb  mov     [rax+20h], rbx
0x18000dfdf  push    rbp
0x18000dfe0  push    rsi
0x18000dfe1  push    rdi
0x18000dfe2  push    r12
0x18000dfe4  push    r13
0x18000dfe6  push    r14
0x18000dfe8  push    r15
0x18000dfea  lea     rbp, [rax-0E8h]
0x18000dff1  sub     rsp, 1B0h
0x18000dff8  movaps  xmmword ptr [rax-48h], xmm6
0x18000dffc  mov     rax, cs:__security_cookie
0x18000e003  xor     rax, rsp
0x18000e006  mov     [rbp+0E0h+var_50], rax
0x18000e00d  mov     r14d, r8d
0x18000e010  mov     dword ptr [rsp+1E0h+var_1B8], r8d
0x18000e015  mov     r13, rdx
0x18000e018  mov     rbx, rcx
0x18000e01b  lea     r15, WPP_GLOBAL_Control
0x18000e022  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e029  cmp     rcx, r15
0x18000e02c  jz      short loc_18000E049
0x18000e02e  test    byte ptr [rcx+1Ch], 8
0x18000e032  jz      short loc_18000E049
0x18000e034  mov     edx, 0Fh
0x18000e039  lea     r8, WPP_77a2c26801653a0753b5e21a86582ed6_Traceguids
0x18000e040  mov     rcx, [rcx+10h]
0x18000e044  call    WPP_SF_
0x18000e049  movups  xmm0, xmmword ptr [r13+0]
0x18000e04e  movdqu  xmmword ptr [rsp+1E0h+pclsid+8], xmm0
0x18000e054  lea     rdx, [rbp+0E0h+var_D0]; unsigned __int16 *
0x18000e058  lea     rcx, [rsp+1E0h+pclsid+8]; struct _GUID
0x18000e05d  call    ?TetheringGetSimIccidForInterfaceGuidInternal@@YAJU_GUID@@PEAG@Z; TetheringGetSimIccidForInterfaceGuidInternal(_GUID,ushort *)
0x18000e062  mov     edi, eax
0x18000e064  xor     r12d, r12d
0x18000e067  test    eax, eax
0x18000e069  js      loc_18000E499
0x18000e06f  mov     [rsp+1E0h+Block], r12
0x18000e074  lea     rax, [rsp+1E0h+Block]
0x18000e079  mov     qword ptr [rsp+1E0h+var_1A8+8], rax
0x18000e07e  mov     [rsp+1E0h+var_198], r12
0x18000e083  mov     sil, 1
0x18000e086  mov     [rsp+1E0h+var_190], sil
0x18000e08b  lea     rdx, [rsp+1E0h+var_198]; unsigned __int16 **
0x18000e090  lea     rcx, [rbp+0E0h+var_D0]; unsigned __int16 *
0x18000e094  call    ?GetUAPEntitlementAppAMUID@@YAJPEBGPEAPEAG@Z; GetUAPEntitlementAppAMUID(ushort const *,ushort * *)
0x18000e099  mov     edi, eax
0x18000e09b  cmp     [rsp+1E0h+var_190], r12b
0x18000e0a0  jz      short loc_18000E0BF
0x18000e0a2  mov     rcx, qword ptr [rsp+1E0h+var_1A8+8]
0x18000e0a7  mov     rdx, [rcx]
0x18000e0aa  mov     rax, [rsp+1E0h+var_198]
0x18000e0af  mov     [rcx], rax
0x18000e0b2  test    rdx, rdx
0x18000e0b5  jz      short loc_18000E0BF
0x18000e0b7  mov     rcx, rdx; Block
0x18000e0ba  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000e0bf  test    edi, edi
0x18000e0c1  js      loc_18000E457
0x18000e0c7  xorps   xmm0, xmm0
0x18000e0ca  movups  xmmword ptr [rsp+1E0h+pclsid+8], xmm0
0x18000e0cf  lea     r8, [rsp+1E0h+pclsid+8]; struct _GUID *
0x18000e0d4  mov     rdx, [rsp+1E0h+Block]; unsigned __int16 *
0x18000e0d9  mov     rcx, rbx; unsigned __int16 *
0x18000e0dc  call    ?GetTaskGuidFromRegistryForAppForUser@@YAJPEBG0PEAU_GUID@@@Z; GetTaskGuidFromRegistryForAppForUser(ushort const *,ushort const *,_GUID *)
0x18000e0e1  mov     edi, eax
0x18000e0e3  test    eax, eax
0x18000e0e5  js      loc_18000E43E
0x18000e0eb  mov     [rsp+1E0h+var_1C0], r12b
0x18000e0f0  lea     rdx, [rsp+1E0h+var_1C0]; bool *
0x18000e0f5  lea     rcx, [rsp+1E0h+pclsid+8]; struct _GUID *
0x18000e0fa  call    ?IsSebBackgroundTaskRegistered@@YAJAEBU_GUID@@PEA_N@Z; IsSebBackgroundTaskRegistered(_GUID const &,bool *)
0x18000e0ff  mov     edi, eax
0x18000e101  test    eax, eax
0x18000e103  js      loc_18000E425
0x18000e109  cmp     [rsp+1E0h+var_1C0], r12b
0x18000e10e  jnz     short loc_18000E149
0x18000e110  mov     edi, 83120017h
0x18000e115  mov     rax, cs:WPP_GLOBAL_Control
0x18000e11c  cmp     rax, r15
0x18000e11f  jz      loc_18000E488
0x18000e125  test    [rax+1Ch], sil
0x18000e129  jz      loc_18000E488
0x18000e12f  mov     edx, 10h
0x18000e134  lea     r8, WPP_77a2c26801653a0753b5e21a86582ed6_Traceguids
0x18000e13b  mov     rcx, [rax+10h]
0x18000e13f  call    WPP_SF_
0x18000e144  jmp     loc_18000E481
0x18000e149  mov     [rsp+1E0h+lpMem], r12
0x18000e14e  lea     rax, [rsp+1E0h+lpMem]
0x18000e153  mov     qword ptr [rsp+1E0h+var_1A8+8], rax
0x18000e158  mov     [rsp+1E0h+var_198], r12
0x18000e15d  mov     [rsp+1E0h+var_190], sil
0x18000e162  movaps  xmm6, xmmword ptr [rsp+1E0h+pclsid+8]
0x18000e167  movdqa  xmmword ptr [rsp+1E0h+pclsid+8], xmm6
0x18000e16d  lea     rdx, [rsp+1E0h+var_198]
0x18000e172  lea     rcx, [rsp+1E0h+pclsid+8]
0x18000e177  call    cs:__imp_SebQueryEventPackage
0x18000e17d  mov     edi, eax
0x18000e17f  cmp     [rsp+1E0h+var_190], r12b
0x18000e184  jz      short loc_18000E1CE
0x18000e186  mov     r12, [rsp+1E0h+var_198]
0x18000e18b  mov     r14, qword ptr [rsp+1E0h+var_1A8+8]
0x18000e190  mov     r15, [r14]
0x18000e193  test    r15, r15
0x18000e196  jz      short loc_18000E1BC
0x18000e198  call    cs:__imp_GetLastError
0x18000e19e  mov     ebx, eax
0x18000e1a0  call    cs:__imp_GetProcessHeap
0x18000e1a6  mov     rcx, rax; hHeap
0x18000e1a9  mov     r8, r15; lpMem
0x18000e1ac  xor     edx, edx; dwFlags
0x18000e1ae  call    cs:__imp_HeapFree
0x18000e1b4  mov     ecx, ebx; dwErrCode
0x18000e1b6  call    cs:__imp_SetLastError
0x18000e1bc  mov     [r14], r12
0x18000e1bf  mov     r14d, dword ptr [rsp+1E0h+var_1B8]
0x18000e1c4  xor     r12d, r12d
0x18000e1c7  lea     r15, WPP_GLOBAL_Control
0x18000e1ce  test    edi, edi
0x18000e1d0  js      loc_18000E3D4
0x18000e1d6  mov     ebx, 28h ; '('
0x18000e1db  mov     r8d, ebx; cchMax
0x18000e1de  lea     rdx, [rbp+0E0h+sz]; lpsz
0x18000e1e2  mov     rcx, r13; rguid
0x18000e1e5  call    cs:__imp_StringFromGUID2
0x18000e1eb  test    eax, eax
0x18000e1ed  jz      loc_18000E2DB
0x18000e1f3  xor     edx, edx; Val
0x18000e1f5  lea     r8d, [rbx+28h]; Size
0x18000e1f9  lea     rcx, [rbp+0E0h+var_120]; void *
0x18000e1fd  call    memset_0
0x18000e202  lea     r8, [rbp+0E0h+var_120]
0x18000e206  mov     edx, ebx
0x18000e208  lea     rcx, [rbp+0E0h+sz]
0x18000e20c  call    cs:__imp_GetNetworkAccountIdBoundToInterfaceId
0x18000e212  mov     edi, eax
0x18000e214  test    eax, eax
0x18000e216  js      loc_18000E2B1
0x18000e21c  xorps   xmm0, xmm0
0x18000e21f  movups  xmmword ptr [rsp+1E0h+pclsid+8], xmm0
0x18000e224  lea     rdx, [rsp+1E0h+pclsid+8]; pclsid
0x18000e229  lea     rcx, [rbp+0E0h+var_120]; lpsz
0x18000e22d  call    cs:__imp_CLSIDFromString
0x18000e233  mov     edi, eax
0x18000e235  test    eax, eax
0x18000e237  js      short loc_18000E298
0x18000e239  movups  xmm1, cs:xmmword_180036F58
0x18000e240  movdqu  [rbp+0E0h+var_160], xmm1
0x18000e245  movups  xmm0, xmmword ptr [rsp+1E0h+pclsid+8]
0x18000e24a  movdqu  [rbp+0E0h+var_150], xmm0
0x18000e24f  movups  xmm1, xmmword ptr [r13+0]
0x18000e254  movdqu  [rbp+0E0h+var_140], xmm1
0x18000e259  mov     [rbp+0E0h+var_130], r14d
0x18000e25d  movdqa  [rsp+1E0h+var_1A8+8], xmm6
0x18000e263  mov     r9, [rsp+1E0h+lpMem]
0x18000e268  lea     r8d, [rbx+0Ch]
0x18000e26c  lea     rdx, [rbp+0E0h+var_160]
0x18000e270  lea     rcx, [rsp+1E0h+var_1A8+8]
0x18000e275  call    cs:__imp_SebSignalEvent
0x18000e27b  mov     edi, eax
0x18000e27d  test    eax, eax
0x18000e27f  jns     short loc_18000E2DB
0x18000e281  mov     rax, cs:WPP_GLOBAL_Control
0x18000e288  cmp     rax, r15
0x18000e28b  jz      short loc_18000E2E2
0x18000e28d  test    [rax+1Ch], sil
0x18000e291  jz      short loc_18000E2E2
0x18000e293  lea     edx, [rbx-17h]
0x18000e296  jmp     short loc_18000E2C8
0x18000e298  mov     rax, cs:WPP_GLOBAL_Control
0x18000e29f  cmp     rax, r15
0x18000e2a2  jz      short loc_18000E2E2
0x18000e2a4  test    [rax+1Ch], sil
0x18000e2a8  jz      short loc_18000E2E2
0x18000e2aa  mov     edx, 12h
0x18000e2af  jmp     short loc_18000E2C8
0x18000e2b1  mov     rax, cs:WPP_GLOBAL_Control
0x18000e2b8  cmp     rax, r15
0x18000e2bb  jz      short loc_18000E2E2
0x18000e2bd  test    [rax+1Ch], sil
0x18000e2c1  jz      short loc_18000E2E2
0x18000e2c3  mov     edx, 13h
0x18000e2c8  mov     r9d, edi
0x18000e2cb  lea     r8, WPP_77a2c26801653a0753b5e21a86582ed6_Traceguids
0x18000e2d2  mov     rcx, [rax+10h]
0x18000e2d6  call    WPP_SF_d
0x18000e2db  mov     rax, cs:WPP_GLOBAL_Control
0x18000e2e2  mov     [rsp+1E0h+var_1B8], r12
0x18000e2e7  cmp     cs:?g_lTraceLoggingRegistered@@3JA, r12d; long g_lTraceLoggingRegistered
0x18000e2ee  jl      loc_18000E3A9
0x18000e2f4  mov     rdx, qword ptr cs:?g_pTetheringSessionId@@3PEAU_GUID@@EA.Data1; struct _GUID *
0x18000e2fb  test    rdx, rdx
0x18000e2fe  jz      loc_18000E3A9
0x18000e304  lea     r8, [rsp+1E0h+var_1B8]; struct TetheringSessionTelemetry **
0x18000e309  call    ?GetSession@TetheringServiceTelemetry@@QEAAJPEAU_GUID@@PEAPEAVTetheringSessionTelemetry@@@Z; TetheringServiceTelemetry::GetSession(_GUID *,TetheringSessionTelemetry * *)
0x18000e30e  mov     ebx, eax
0x18000e310  test    eax, eax
0x18000e312  js      short loc_18000E32B
0x18000e314  mov     rcx, [rsp+1E0h+var_1B8]; this
0x18000e319  test    rcx, rcx
0x18000e31c  jz      loc_18000E3A2
0x18000e322  call    ?Initialized@TetheringSessionTelemetry@@QEAAHXZ; TetheringSessionTelemetry::Initialized(void)
0x18000e327  test    eax, eax
0x18000e329  jz      short loc_18000E3A2
0x18000e32b  test    ebx, ebx
0x18000e32d  js      short loc_18000E3A2
0x18000e32f  xor     edx, edx; Val
0x18000e331  lea     r8d, [rdx+50h]; Size
0x18000e335  lea     rcx, [rbp+0E0h+var_120]; void *
0x18000e339  call    memset_0
0x18000e33e  lea     r8, [rbp+0E0h+var_120]; struct TetheringServiceTelemetry::SESSION_DATA *
0x18000e342  mov     rdx, [rsp+1E0h+var_1B8]; struct TetheringSessionTelemetry *
0x18000e347  call    ?AcquireSessionData@TetheringServiceTelemetry@@QEAAXAEAVTetheringSessionTelemetry@@AEAUSESSION_DATA@1@@Z; TetheringServiceTelemetry::AcquireSessionData(TetheringSessionTelemetry &,TetheringServiceTelemetry::SESSION_DATA &)
0x18000e34c  mov     rsi, [rbp+0E0h+var_F0]
0x18000e350  lea     rax, [rsp+1E0h+lpMem]
0x18000e355  cmp     rsi, rax
0x18000e358  jz      short loc_18000E393
0x18000e35a  mov     r15, [rsp+1E0h+lpMem]
0x18000e35f  mov     r14, [rsi]
0x18000e362  test    r14, r14
0x18000e365  jz      short loc_18000E38B
0x18000e367  call    cs:__imp_GetLastError
0x18000e36d  mov     ebx, eax
0x18000e36f  call    cs:__imp_GetProcessHeap
0x18000e375  mov     rcx, rax; hHeap
0x18000e378  mov     r8, r14; lpMem
0x18000e37b  xor     edx, edx; dwFlags
0x18000e37d  call    cs:__imp_HeapFree
0x18000e383  mov     ecx, ebx; dwErrCode
0x18000e385  call    cs:__imp_SetLastError
0x18000e38b  mov     [rsi], r15
0x18000e38e  mov     [rsp+1E0h+lpMem], r12
0x18000e393  mov     rcx, [rsp+1E0h+var_1B8]
0x18000e398  add     rcx, 10h; SRWLock
0x18000e39c  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e3a2  mov     rax, cs:WPP_GLOBAL_Control
0x18000e3a9  mov     rcx, [rsp+1E0h+var_1B8]
0x18000e3ae  test    rcx, rcx
0x18000e3b1  jz      short loc_18000E3CB
0x18000e3b3  mov     [rsp+1E0h+var_1B8], r12
0x18000e3b8  mov     rax, [rcx]
0x18000e3bb  mov     rax, [rax+10h]
0x18000e3bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3c4  mov     rax, cs:WPP_GLOBAL_Control
0x18000e3cb  lea     r15, WPP_GLOBAL_Control
0x18000e3d2  jmp     short loc_18000E405
0x18000e3d4  mov     rax, cs:WPP_GLOBAL_Control
0x18000e3db  cmp     rax, r15
0x18000e3de  jz      short loc_18000E405
0x18000e3e0  test    [rax+1Ch], sil
0x18000e3e4  jz      short loc_18000E405
0x18000e3e6  mov     edx, 14h
0x18000e3eb  mov     r9d, edi
0x18000e3ee  lea     r8, WPP_77a2c26801653a0753b5e21a86582ed6_Traceguids
0x18000e3f5  mov     rcx, [rax+10h]
0x18000e3f9  call    WPP_SF_d
0x18000e3fe  mov     rax, cs:WPP_GLOBAL_Control
0x18000e405  mov     rbx, [rsp+1E0h+lpMem]
0x18000e40a  test    rbx, rbx
0x18000e40d  jz      short loc_18000E488
0x18000e40f  call    cs:__imp_GetProcessHeap
0x18000e415  mov     rcx, rax; hHeap
0x18000e418  mov     r8, rbx; lpMem
0x18000e41b  xor     edx, edx; dwFlags
0x18000e41d  call    cs:__imp_HeapFree
0x18000e423  jmp     short loc_18000E481
0x18000e425  mov     rax, cs:WPP_GLOBAL_Control
0x18000e42c  cmp     rax, r15
0x18000e42f  jz      short loc_18000E488
0x18000e431  test    [rax+1Ch], sil
0x18000e435  jz      short loc_18000E488
0x18000e437  mov     edx, 15h
0x18000e43c  jmp     short loc_18000E46E
0x18000e43e  mov     rax, cs:WPP_GLOBAL_Control
0x18000e445  cmp     rax, r15
0x18000e448  jz      short loc_18000E488
0x18000e44a  test    [rax+1Ch], sil
0x18000e44e  jz      short loc_18000E488
0x18000e450  mov     edx, 16h
0x18000e455  jmp     short loc_18000E46E
0x18000e457  mov     rax, cs:WPP_GLOBAL_Control
0x18000e45e  cmp     rax, r15
0x18000e461  jz      short loc_18000E488
0x18000e463  test    [rax+1Ch], sil
0x18000e467  jz      short loc_18000E488
0x18000e469  mov     edx, 17h
0x18000e46e  mov     r9d, edi
0x18000e471  lea     r8, WPP_77a2c26801653a0753b5e21a86582ed6_Traceguids
0x18000e478  mov     rcx, [rax+10h]
0x18000e47c  call    WPP_SF_d
0x18000e481  mov     rax, cs:WPP_GLOBAL_Control
0x18000e488  mov     rcx, [rsp+1E0h+Block]; Block
0x18000e48d  test    rcx, rcx
0x18000e490  jz      short loc_18000E4CD
0x18000e492  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000e497  jmp     short loc_18000E4C6
0x18000e499  mov     rax, cs:WPP_GLOBAL_Control
0x18000e4a0  cmp     rax, r15
  ... truncated ...
```
