# RpcGetAllListeners

- ea: `0x18000d810`
- end: `0x18000df55`
- name: `RpcGetAllListeners`
- size: `1861`
- prototype: `__int64 __fastcall(__int64, _QWORD *, int, _DWORD *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000a210`
- `0x18000d810`
- `0x18000f790`
- `0x1800119a0`
- `0x1800127b0`
- `0x180012880`
- `0x180014de0`
- `0x1800321f0`
- `0x180032700`
- `0x1800327a0`
- `0x1800330c4`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000da64`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000da64`
- `ntdll!NtQueryInformationProcess` at `0x18000da48`
- `ntdll!NtQueryInformationProcess` at `0x18000da48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ded9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000def3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ded9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000def3`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000da07`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000da07`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000decf`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000dee9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000decf`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000dee9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000da90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000da90`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000d9e3`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000d9e3`
- `RPCRT4!RpcRevertToSelf` at `0x18000dcfc`
- `RPCRT4!RpcRevertToSelf` at `0x18000dcfc`
- `RPCRT4!RpcImpersonateClient` at `0x18000db0c`
- `RPCRT4!RpcImpersonateClient` at `0x18000db0c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000da20`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000da20`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000dce7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000dce7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000de50`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000de50`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000d88e`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000d88e`

## string_xrefs

- `0x18000db2f`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x18000de96`: `%s with Trace ID 0x%x Completed`
- `0x18000d8fe`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x18000dab9`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

## pseudocode

```c
__int64 __fastcall RpcGetAllListeners(__int64 a1, _QWORD *a2, int a3, _DWORD *a4)
{
  _DWORD *v4; // r15
  _QWORD *v6; // r14
  __int64 v7; // rbx
  _QWORD *v8; // r13
  unsigned int v9; // esi
  RPC_STATUS v10; // eax
  int v11; // edi
  HANDLE v12; // rax
  void *v13; // rsi
  NTSTATUS InformationProcess; // eax
  wchar_t *v15; // rax
  wchar_t *v16; // rax
  unsigned int v17; // esi
  RPC_STATUS v18; // eax
  signed int v19; // edi
  char *v20; // r12
  unsigned __int64 v21; // rdi
  __int64 v22; // rax
  bool v23; // cf
  unsigned __int64 v24; // rax
  unsigned __int64 *v25; // rax
  int v26; // eax
  int v27; // r14d
  __int64 v28; // r12
  __int64 v29; // rcx
  bool v30; // zf
  SIZE_T v31; // rsi
  int v32; // eax
  bool v33; // sf
  unsigned __int64 v34; // rdx
  __int64 v35; // rsi
  int v36; // eax
  unsigned int v37; // ecx
  unsigned int v38; // r14d
  unsigned int v39; // r15d
  struct CTraceBase *v40; // rdx
  char *v41; // rax
  __int64 v42; // rcx
  int v43; // eax
  char *v44; // rdx
  unsigned __int64 v46; // [rsp+30h] [rbp-D0h] BYREF
  struct CTraceBase *v47; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v48; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v49; // [rsp+48h] [rbp-B8h]
  char *v50; // [rsp+50h] [rbp-B0h]
  _QWORD *v51; // [rsp+58h] [rbp-A8h]
  _DWORD *v52; // [rsp+60h] [rbp-A0h]
  void **v53; // [rsp+70h] [rbp-90h] BYREF
  GUID pguid; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v55[2]; // [rsp+88h] [rbp-78h] BYREF
  struct CTraceBase *v56; // [rsp+90h] [rbp-70h] BYREF
  int v57; // [rsp+98h] [rbp-68h]
  const char *v58; // [rsp+A0h] [rbp-60h]
  unsigned int Pid[2]; // [rsp+A8h] [rbp-58h] BYREF
  int v60; // [rsp+B0h] [rbp-50h]
  unsigned __int16 v61[262]; // [rsp+B4h] [rbp-4Ch] BYREF
  char ProcessInformation[8]; // [rsp+2C0h] [rbp+1C0h] BYREF
  wchar_t *Str; // [rsp+2C8h] [rbp+1C8h]

  v4 = a4;
  v52 = a4;
  v6 = a2;
  v51 = a2;
  v7 = 0;
  v48 = 0;
  LODWORD(v46) = 0;
  v8 = 0;
  v53 = &CTraceBase::`vftable';
  v55[1] = 1;
  v56 = 0;
  if ( !CTraceBase::g_bEnabled )
  {
    CoCreateGuid(&pguid);
    v55[0] = _InterlockedIncrement((volatile signed __int32 *)&CTraceBase::g_NextShortActivityID);
LABEL_13:
    v57 = 0;
    goto LABEL_14;
  }
  if ( (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "Adding trace %p, %d, %s", &v53, 1, "RpcGetAllListeners");
  v47 = 0;
  if ( (int)CTraceBase::GetThreadCurrentOperationTrace(&v47) >= 0 && v47 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(
      2,
      "TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC",
      1);
  CTraceBase::ResetThreadCurrentOperationTrace(0, 0);
  if ( (int)CTraceBase::GetThreadCurrentOperationTrace(&v56) < 0 || !v56 )
  {
    CTraceBase::ResetThreadCurrentOperationTrace((struct CTraceBase *)&v53, "RpcGetAllListeners");
    CTraceBase::GenerateTraceID(&pguid, v55);
    goto LABEL_13;
  }
  (*(void (__fastcall **)(struct CTraceBase *, GUID *))(*(_QWORD *)v56 + 32LL))(v56, &pguid);
  v55[0] = (*(__int64 (__fastcall **)(struct CTraceBase *))(*(_QWORD *)v56 + 24LL))(v56);
  v57 = 1;
LABEL_14:
  v53 = &CRpcCallTrace::`vftable';
  v58 = "RpcGetAllListeners";
  *(_QWORD *)Pid = -1;
  v60 = 0;
  memset_0(v61, 0, 0x208u);
  if ( v60 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "TRACE RPC %s with Trace ID 0x%x", v58, v55[0]);
  v9 = g_DebugTraceComponent & 1;
  *(_QWORD *)Pid = -1;
  v10 = I_RpcBindingInqLocalClientPID(0, &Pid[1]);
  v11 = v10;
  if ( v10 > 0 )
    v11 = (unsigned __int16)v10 | 0x80070000;
  if ( v11 >= 0 )
  {
    ProcessIdToSessionId(Pid[1], Pid);
    if ( v9 )
    {
      v12 = OpenProcess(0x400u, 0, Pid[1]);
      v13 = v12;
      if ( v12 )
      {
        InformationProcess = NtQueryInformationProcess(v12, ProcessImageFileName, ProcessInformation, 0x110u, 0);
        v11 = InformationProcess | 0x10000000;
        if ( InformationProcess >= 0 )
        {
          v15 = wcsrchr(Str, 0x5Cu);
          if ( v15 )
            v16 = v15 + 1;
          else
            v16 = Str;
          StringCchCopyW(v61, 0x104u, v16);
        }
        CloseHandle(v13);
      }
    }
  }
  if ( v60 )
  {
    if ( v11 < 0 )
    {
      if ( (g_DebugTraceComponent & 1) != 0 )
        _DbgPrintMessage(2, "RPC Caller: Unknown");
    }
    else if ( (g_DebugTraceComponent & 1) != 0 )
    {
      _DbgPrintMessage(2, "RPC Caller: PID %d, SessID %d, Process Name: <%S>", Pid[1], Pid[0], v61);
    }
  }
  if ( !v6 || !v4 || a3 != 1 )
  {
    v19 = -2147024809;
    goto LABEL_84;
  }
  v17 = 0;
  *v6 = 0;
  *v4 = 0;
  v18 = RpcImpersonateClient(0);
  v19 = v18;
  if ( v18 > 0 )
    v19 = (unsigned __int16)v18 | 0x80070000;
  if ( v19 < 0 )
  {
    _DbgPrintMessage(8, "RpcImpersonateClient failed: 0x%x in %s", v19, "RpcGetAllListeners");
    goto LABEL_84;
  }
  v20 = 0;
  v50 = 0;
  if ( qword_180128DF0 )
  {
    v7 = qword_180128DF0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_180128DF0 + 8LL))(qword_180128DF0);
  }
  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v7 + 120LL))(v7, &v48);
  (*(void (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v48 + 32LL))(v48, &v46);
  if ( (_DWORD)v46 )
  {
    v21 = (unsigned int)v46;
    v22 = 8LL * (unsigned int)v46;
    if ( !is_mul_ok((unsigned int)v46, 8u) )
      v22 = -1;
    v23 = __CFADD__(v22, 8);
    v24 = v22 + 8;
    if ( v23 )
      v24 = -1;
    v25 = (unsigned __int64 *)operator new[](v24, (const struct std::nothrow_t *)std::nothrow);
    if ( v25 )
    {
      *v25 = v21;
      v8 = v25 + 1;
      `eh vector constructor iterator'(
        v25 + 1,
        8u,
        v21,
        SmartPtr<IListener>::SmartPtr<IListener>,
        SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>);
      if ( v8 )
      {
        v26 = (*(__int64 (__fastcall **)(__int64, _QWORD *, unsigned __int64 *))(*(_QWORD *)v48 + 40LL))(v48, v8, &v46);
        v19 = v26;
        if ( v26 < 0 )
        {
          _DbgPrintMessage(8, "List->GetList failed: 0x%x in %s", v26, "RpcGetAllListeners");
          goto LABEL_64;
        }
        if ( (_DWORD)v46 )
        {
          v27 = 0;
          do
          {
            v28 = v17;
            v19 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v8[v28] + 96LL))(v8[v28], 1);
            if ( v19 >= 0 )
            {
              ++v27;
            }
            else
            {
              v29 = v8[v28];
              v8[v28] = 0;
              if ( v29 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
              v19 = 0;
            }
            ++v17;
          }
          while ( v17 < (unsigned int)v46 );
          LODWORD(v47) = v27;
          v30 = v27 == 0;
          v6 = v51;
          if ( !v30 )
          {
            v31 = (unsigned int)(80 * (_DWORD)v47);
            v20 = (char *)LocalAlloc(0x40u, v31);
            if ( v20 )
            {
              v34 = v31 / 0x50;
              v49 = v31 / 0x50;
              v35 = 0;
              v36 = 0;
              v37 = v46;
              if ( (_DWORD)v46 )
              {
                v38 = 0;
                v39 = v34;
                do
                {
                  if ( v38 >= v39 )
                    break;
                  v40 = (struct CTraceBase *)&v8[v35];
                  v47 = v40;
                  if ( *(_QWORD *)v40 )
                  {
                    v41 = &v20[80 * v38];
                    v50 = v41;
                    *(_DWORD *)v41 = 1;
                    v42 = *(_QWORD *)v40;
                    v49 = (unsigned __int64)(v41 + 12);
                    if ( (*(int (__fastcall **)(__int64, _DWORD *, __int64))(*(_QWORD *)v42 + 72LL))(
                           v42,
                           (_DWORD *)v41 + 3,
                           33) < 0 )
                    {
                      _DbgPrintMessage(8, "Failed to get a listener's name");
                      *(_WORD *)v49 = 0;
                    }
                    v43 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v47 + 64LL))(*(_QWORD *)v47);
                    v44 = v50;
                    *((_DWORD *)v50 + 2) = v43 == 0;
                    *((_DWORD *)v44 + 1) = v35 + 0x10000;
                    ++v38;
                    v37 = v46;
                  }
                  v35 = (unsigned int)(v35 + 1);
                }
                while ( (unsigned int)v35 < v37 );
                LODWORD(v47) = v38;
                v6 = v51;
                v4 = v52;
                v36 = (int)v47;
              }
              *v6 = v20;
              *v4 = v36;
              goto LABEL_64;
            }
            goto LABEL_63;
          }
          v20 = v50;
        }
        v19 = 0;
        goto LABEL_64;
      }
    }
LABEL_63:
    v19 = -2147024882;
    goto LABEL_64;
  }
  v19 = 0;
  _DbgPrintMessage(8, "No listeners");
LABEL_64:
  v32 = RpcRevertToSelf();
  v33 = v32 < 0;
  if ( v32 > 0 )
  {
    v32 = (unsigned __int16)v32 | 0x80070000;
    v33 = v32 < 0;
  }
  if ( v33 )
  {
    _DbgPrintMessage(8, "RpcRevertToSelf failed: 0x%x", v32);
    v19 = -2147024891;
  }
  else if ( v19 >= 0 )
  {
    goto LABEL_85;
  }
  if ( v20 )
    LocalFree(v20);
LABEL_84:
  *v6 = 0;
  *v4 = 0;
LABEL_85:
  if ( v8 )
    SmartPtr<IListener>::`vector deleting destructor'(v8);
  v53 = &CRpcCallTrace::`vftable';
  if ( v60 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "%s with Trace ID 0x%x Completed", v58, v55[0]);
  v53 = &CTraceBase::`vftable';
  if ( CTraceBase::g_bEnabled && !v57 && CTraceBase::g_TLSIndex != -1 )
  {
    if ( TlsSetValue(CTraceBase::g_TLSIndex, 0) )
    {
      if ( TlsSetValue(CTraceBase::g_CreatorFunctionTLSIndex, 0) )
        goto LABEL_97;
    }
    else
    {
      GetLastError();
    }
    GetLastError();
  }
LABEL_97:
  v56 = 0;
  if ( v48 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x18000d810  mov     [rsp-8+arg_0], rbx
0x18000d815  push    rbp
0x18000d816  push    rsi
0x18000d817  push    rdi
0x18000d818  push    r12
0x18000d81a  push    r13
0x18000d81c  push    r14
0x18000d81e  push    r15
0x18000d820  lea     rbp, [rsp-2E0h]
0x18000d828  sub     rsp, 3E0h
0x18000d82f  mov     rax, cs:__security_cookie
0x18000d836  xor     rax, rsp
0x18000d839  mov     [rbp+310h+var_40], rax
0x18000d840  mov     r15, r9
0x18000d843  mov     [rsp+410h+var_3B0], r9
0x18000d848  mov     r12d, r8d
0x18000d84b  mov     r14, rdx
0x18000d84e  mov     [rsp+410h+var_3B8], rdx
0x18000d853  xor     edi, edi
0x18000d855  mov     ebx, edi
0x18000d857  mov     [rsp+410h+var_3D0], rdi
0x18000d85c  mov     dword ptr [rsp+410h+var_3E0], edi
0x18000d860  mov     r13d, edi
0x18000d863  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x18000d86a  mov     [rsp+410h+var_3A0], rax
0x18000d86f  mov     [rbp+310h+var_384], 1
0x18000d876  mov     [rbp+310h+var_380], rdi
0x18000d87a  lea     rsi, aRpcgetallliste; "RpcGetAllListeners"
0x18000d881  cmp     cs:?g_bEnabled@CTraceBase@@0HA, edi; int CTraceBase::g_bEnabled
0x18000d887  jnz     short loc_18000D8AB
0x18000d889  lea     rcx, [rsp+410h+pguid]; pguid
0x18000d88e  call    cs:__imp_CoCreateGuid
0x18000d894  mov     eax, 1
0x18000d899  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, eax; ulong CTraceBase::g_NextShortActivityID
0x18000d8a1  inc     eax
0x18000d8a3  mov     [rbp+310h+var_388], eax
0x18000d8a6  jmp     loc_18000D976
0x18000d8ab  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000d8b2  jz      short loc_18000D8D5
0x18000d8b4  mov     [rsp+410h+ReturnLength], rsi
0x18000d8b9  mov     r9d, 1
0x18000d8bf  lea     r8, [rsp+410h+var_3A0]
0x18000d8c4  lea     rdx, aAddingTracePDS; "Adding trace %p, %d, %s"
0x18000d8cb  mov     ecx, 2; int
0x18000d8d0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000d8d5  mov     [rsp+410h+var_3D8], rdi
0x18000d8da  lea     rcx, [rsp+410h+var_3D8]; struct CTraceBase **
0x18000d8df  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18000d8e4  test    eax, eax
0x18000d8e6  js      short loc_18000D90F
0x18000d8e8  cmp     [rsp+410h+var_3D8], rbx
0x18000d8ed  jz      short loc_18000D90F
0x18000d8ef  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000d8f6  jz      short loc_18000D90F
0x18000d8f8  mov     r8d, 1
0x18000d8fe  lea     rdx, aTracecomponent; "TraceComponent %d: Warning TLS should b"...
0x18000d905  mov     ecx, 2; int
0x18000d90a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000d90f  xor     edx, edx; char *
0x18000d911  xor     ecx, ecx; lpTlsValue
0x18000d913  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18000d918  lea     rcx, [rbp+310h+var_380]; struct CTraceBase **
0x18000d91c  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18000d921  test    eax, eax
0x18000d923  js      short loc_18000D95B
0x18000d925  mov     rcx, [rbp+310h+var_380]
0x18000d929  test    rcx, rcx
0x18000d92c  jz      short loc_18000D95B
0x18000d92e  mov     rax, [rcx]
0x18000d931  lea     rdx, [rsp+410h+pguid]
0x18000d936  mov     rax, [rax+20h]
0x18000d93a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d93f  mov     rcx, [rbp+310h+var_380]
0x18000d943  mov     rax, [rcx]
0x18000d946  mov     rax, [rax+18h]
0x18000d94a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d94f  mov     [rbp+310h+var_388], eax
0x18000d952  mov     [rbp+310h+var_378], 1
0x18000d959  jmp     short loc_18000D979
0x18000d95b  mov     rdx, rsi; char *
0x18000d95e  lea     rcx, [rsp+410h+var_3A0]; lpTlsValue
0x18000d963  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18000d968  lea     rdx, [rbp+310h+var_388]; unsigned int *
0x18000d96c  lea     rcx, [rsp+410h+pguid]; struct _GUID *
0x18000d971  call    ?GenerateTraceID@CTraceBase@@KAJPEAU_GUID@@PEAK@Z; CTraceBase::GenerateTraceID(_GUID *,ulong *)
0x18000d976  mov     [rbp+310h+var_378], edi
0x18000d979  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18000d980  mov     [rsp+410h+var_3A0], rax
0x18000d985  mov     [rbp+310h+var_370], rsi
0x18000d989  mov     qword ptr [rbp+310h+Pid], 0FFFFFFFFFFFFFFFFh
0x18000d991  mov     [rbp+310h+var_360], edi
0x18000d994  xor     edx, edx; Val
0x18000d996  mov     r8d, 208h; Size
0x18000d99c  lea     rcx, [rbp+310h+var_35C]; void *
0x18000d9a0  call    memset_0
0x18000d9a5  cmp     [rbp+310h+var_360], ebx
0x18000d9a8  jz      short loc_18000D9CC
0x18000d9aa  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000d9b1  jz      short loc_18000D9CC
0x18000d9b3  mov     r9d, [rbp+310h+var_388]
0x18000d9b7  mov     r8, [rbp+310h+var_370]
0x18000d9bb  lea     rdx, aTraceRpcSWithT; "TRACE RPC %s with Trace ID 0x%x"
0x18000d9c2  mov     ecx, 2; int
0x18000d9c7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000d9cc  mov     esi, cs:?g_DebugTraceComponent@@3KA; ulong g_DebugTraceComponent
0x18000d9d2  and     esi, 1
0x18000d9d5  mov     qword ptr [rbp+310h+Pid], 0FFFFFFFFFFFFFFFFh
0x18000d9dd  lea     rdx, [rbp+310h+Pid+4]; Pid
0x18000d9e1  xor     ecx, ecx; Binding
0x18000d9e3  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000d9e9  mov     edi, eax
0x18000d9eb  test    eax, eax
0x18000d9ed  jle     short loc_18000D9F8
0x18000d9ef  movzx   edi, ax
0x18000d9f2  or      edi, 80070000h
0x18000d9f8  test    edi, edi
0x18000d9fa  js      loc_18000DA96
0x18000da00  lea     rdx, [rbp+310h+Pid]; pSessionId
0x18000da04  mov     ecx, [rbp+310h+Pid+4]; dwProcessId
0x18000da07  call    cs:__imp_ProcessIdToSessionId
0x18000da0d  test    esi, esi
0x18000da0f  jz      loc_18000DA96
0x18000da15  mov     r8d, [rbp+310h+Pid+4]; dwProcessId
0x18000da19  xor     edx, edx; bInheritHandle
0x18000da1b  mov     ecx, 400h; dwDesiredAccess
0x18000da20  call    cs:__imp_OpenProcess
0x18000da26  mov     rsi, rax
0x18000da29  test    rax, rax
0x18000da2c  jz      short loc_18000DA96
0x18000da2e  mov     [rsp+410h+ReturnLength], rbx; ReturnLength
0x18000da33  mov     r9d, 110h; ProcessInformationLength
0x18000da39  lea     r8, [rbp+310h+ProcessInformation]; ProcessInformation
0x18000da40  mov     edx, 1Bh; ProcessInformationClass
0x18000da45  mov     rcx, rax; ProcessHandle
0x18000da48  call    cs:__imp_NtQueryInformationProcess
0x18000da4e  mov     edi, eax
0x18000da50  or      edi, 10000000h
0x18000da56  jl      short loc_18000DA8D
0x18000da58  mov     edx, 5Ch ; '\'; Ch
0x18000da5d  mov     rcx, [rbp+310h+Str]; Str
0x18000da64  call    cs:__imp_wcsrchr
0x18000da6a  test    rax, rax
0x18000da6d  jnz     short loc_18000DA78
0x18000da6f  mov     rax, [rbp+310h+Str]
0x18000da76  jmp     short loc_18000DA7C
0x18000da78  add     rax, 2
0x18000da7c  mov     r8, rax; unsigned __int16 *
0x18000da7f  mov     edx, 104h; unsigned __int64
0x18000da84  lea     rcx, [rbp+310h+var_35C]; unsigned __int16 *
0x18000da88  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000da8d  mov     rcx, rsi; hObject
0x18000da90  call    cs:__imp_CloseHandle
0x18000da96  cmp     [rbp+310h+var_360], ebx
0x18000da99  jz      short loc_18000DAE6
0x18000da9b  test    edi, edi
0x18000da9d  js      short loc_18000DACC
0x18000da9f  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000daa6  jz      short loc_18000DAE6
0x18000daa8  lea     rax, [rbp+310h+var_35C]
0x18000daac  mov     [rsp+410h+ReturnLength], rax
0x18000dab1  mov     r9d, [rbp+310h+Pid]
0x18000dab5  mov     r8d, [rbp+310h+Pid+4]
0x18000dab9  lea     rdx, aRpcCallerPidDS; "RPC Caller: PID %d, SessID %d, Process "...
0x18000dac0  mov     ecx, 2; int
0x18000dac5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000daca  jmp     short loc_18000DAE6
0x18000dacc  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000dad3  jz      short loc_18000DAE6
0x18000dad5  lea     rdx, aRpcCallerUnkno; "RPC Caller: Unknown"
0x18000dadc  mov     ecx, 2; int
0x18000dae1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000dae6  test    r14, r14
0x18000dae9  jz      loc_18000DE58
0x18000daef  test    r15, r15
0x18000daf2  jz      loc_18000DE58
0x18000daf8  cmp     r12d, 1
0x18000dafc  jnz     loc_18000DE58
0x18000db02  xor     esi, esi
0x18000db04  mov     [r14], rsi
0x18000db07  mov     [r15], esi
0x18000db0a  xor     ecx, ecx; BindingHandle
0x18000db0c  call    cs:__imp_RpcImpersonateClient
0x18000db12  mov     edi, eax
0x18000db14  test    eax, eax
0x18000db16  jle     short loc_18000DB21
0x18000db18  movzx   edi, ax
0x18000db1b  or      edi, 80070000h
0x18000db21  test    edi, edi
0x18000db23  jns     short loc_18000DB45
0x18000db25  lea     r9, aRpcgetallliste; "RpcGetAllListeners"
0x18000db2c  mov     r8d, edi
0x18000db2f  lea     rdx, aRpcimpersonate; "RpcImpersonateClient failed: 0x%x in %s"
0x18000db36  mov     ecx, 8; int
0x18000db3b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000db40  jmp     loc_18000DE5F
0x18000db45  mov     r12, rsi
0x18000db48  mov     [rsp+410h+var_3C0], rsi
0x18000db4d  mov     rax, cs:qword_180128DF0
0x18000db54  test    rax, rax
0x18000db57  jz      short loc_18000DB6B
0x18000db59  mov     rbx, rax
0x18000db5c  mov     rax, [rax]
0x18000db5f  mov     rcx, rbx
0x18000db62  mov     rax, [rax+8]
0x18000db66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db6b  mov     rax, [rbx]
0x18000db6e  lea     rdx, [rsp+410h+var_3D0]
0x18000db73  mov     rcx, rbx
0x18000db76  mov     rax, [rax+78h]
0x18000db7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db7f  mov     rcx, [rsp+410h+var_3D0]
0x18000db84  mov     rax, [rcx]
0x18000db87  lea     rdx, [rsp+410h+var_3E0]
0x18000db8c  mov     rax, [rax+20h]
0x18000db90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db95  mov     eax, dword ptr [rsp+410h+var_3E0]
0x18000db99  test    eax, eax
0x18000db9b  jnz     short loc_18000DBB5
0x18000db9d  mov     edi, esi
0x18000db9f  lea     rdx, aNoListeners; "No listeners"
0x18000dba6  mov     ecx, 8; int
0x18000dbab  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000dbb0  jmp     loc_18000DCFC
0x18000dbb5  mov     rdi, rax
0x18000dbb8  mov     eax, 8
0x18000dbbd  mul     rdi
0x18000dbc0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000dbc7  cmovb   rax, rcx
0x18000dbcb  add     rax, 8
0x18000dbcf  cmovb   rax, rcx
0x18000dbd3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000dbda  mov     rcx, rax; unsigned __int64
0x18000dbdd  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000dbe2  test    rax, rax
0x18000dbe5  jz      loc_18000DCF7
0x18000dbeb  mov     [rax], rdi
0x18000dbee  lea     r13, [rax+8]
0x18000dbf2  lea     rax, ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18000dbf9  mov     [rsp+410h+ReturnLength], rax; void (*)(void *)
0x18000dbfe  lea     r9, ??0?$SmartPtr@VIListener@@@@QEAA@XZ; void (*)(void *)
0x18000dc05  mov     r8, rdi; unsigned __int64
0x18000dc08  mov     edx, 8; unsigned __int64
0x18000dc0d  mov     rcx, r13; void *
0x18000dc10  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18000dc15  test    r13, r13
0x18000dc18  jz      loc_18000DCF7
0x18000dc1e  mov     rcx, [rsp+410h+var_3D0]
0x18000dc23  mov     rax, [rcx]
0x18000dc26  lea     r8, [rsp+410h+var_3E0]
0x18000dc2b  mov     rdx, r13
0x18000dc2e  mov     rax, [rax+28h]
0x18000dc32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc37  mov     edi, eax
0x18000dc39  test    eax, eax
0x18000dc3b  jns     short loc_18000DC5D
0x18000dc3d  lea     r9, aRpcgetallliste; "RpcGetAllListeners"
0x18000dc44  mov     r8d, eax
0x18000dc47  lea     rdx, aListGetlistFai; "List->GetList failed: 0x%x in %s"
0x18000dc4e  mov     ecx, 8; int
0x18000dc53  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000dc58  jmp     loc_18000DCFC
0x18000dc5d  cmp     dword ptr [rsp+410h+var_3E0], esi
0x18000dc61  jbe     loc_18000DE3B
0x18000dc67  mov     r14d, esi
0x18000dc6a  nop     word ptr [rax+rax+00h]
0x18000dc70  mov     eax, esi
0x18000dc72  lea     r12, ds:0[rax*8]
0x18000dc7a  mov     rcx, [r12+r13]
0x18000dc7e  mov     rax, [rcx]
0x18000dc81  mov     edx, 1
0x18000dc86  mov     rax, [rax+60h]
0x18000dc8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc8f  mov     edi, eax
0x18000dc91  test    eax, eax
0x18000dc93  jns     short loc_18000DCB6
0x18000dc95  mov     rcx, [r12+r13]
0x18000dc99  mov     qword ptr [r12+r13], 0
0x18000dca1  test    rcx, rcx
0x18000dca4  jz      short loc_18000DCB2
0x18000dca6  mov     rax, [rcx]
0x18000dca9  mov     rax, [rax+10h]
0x18000dcad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dcb2  xor     edi, edi
0x18000dcb4  jmp     short loc_18000DCB9
0x18000dcb6  inc     r14d
0x18000dcb9  inc     esi
0x18000dcbb  cmp     esi, dword ptr [rsp+410h+var_3E0]
0x18000dcbf  jb      short loc_18000DC70
0x18000dcc1  mov     dword ptr [rsp+410h+var_3D8], r14d
0x18000dcc6  test    r14d, r14d
0x18000dcc9  mov     r14, [rsp+410h+var_3B8]
0x18000dcce  jz      loc_18000DE36
0x18000dcd4  mov     eax, dword ptr [rsp+410h+var_3D8]
0x18000dcd8  lea     eax, [rax+rax*4]
0x18000dcdb  shl     eax, 4
0x18000dcde  mov     esi, eax
0x18000dce0  mov     edx, eax; uBytes
0x18000dce2  mov     ecx, 40h ; '@'; uFlags
0x18000dce7  call    cs:__imp_LocalAlloc
0x18000dced  mov     r12, rax
  ... truncated ...
```
