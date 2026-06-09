# RpcGetAllListeners

- ea: `0x18000d260`
- end: `0x18000da00`
- name: `RpcGetAllListeners`
- size: `1952`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180009940`
- `0x18000d260`
- `0x18000faf0`
- `0x180012070`
- `0x180012d10`
- `0x180012f40`
- `0x1800154a0`
- `0x180033f60`
- `0x180034470`
- `0x180034510`
- `0x180034e64`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000d4d2`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000d4d2`
- `ntdll!NtQueryInformationProcess` at `0x18000d4b0`
- `ntdll!NtQueryInformationProcess` at `0x18000d4b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d971`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d997`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d971`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d997`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000d463`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000d463`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000d961`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000d987`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000d961`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000d987`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d504`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d504`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000d439`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000d439`
- `RPCRT4!RpcRevertToSelf` at `0x18000d782`
- `RPCRT4!RpcRevertToSelf` at `0x18000d782`
- `RPCRT4!RpcImpersonateClient` at `0x18000d586`
- `RPCRT4!RpcImpersonateClient` at `0x18000d586`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000d482`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000d482`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d767`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d767`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d8dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d8dc`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000d2de`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000d2de`

## string_xrefs

- `0x18000d5af`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x18000d928`: `%s with Trace ID 0x%x Completed`
- `0x18000d354`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x18000d533`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  if ( qword_18012EDF8 )
  {
    v7 = qword_18012EDF8;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_18012EDF8 + 8LL))(qword_18012EDF8);
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
0x18000d260  mov     [rsp-8+arg_0], rbx
0x18000d265  push    rbp
0x18000d266  push    rsi
0x18000d267  push    rdi
0x18000d268  push    r12
0x18000d26a  push    r13
0x18000d26c  push    r14
0x18000d26e  push    r15
0x18000d270  lea     rbp, [rsp-2E0h]
0x18000d278  sub     rsp, 3E0h
0x18000d27f  mov     rax, cs:__security_cookie
0x18000d286  xor     rax, rsp
0x18000d289  mov     [rbp+310h+var_40], rax
0x18000d290  mov     r15, r9
0x18000d293  mov     [rsp+410h+var_3B0], r9
0x18000d298  mov     r12d, r8d
0x18000d29b  mov     r14, rdx
0x18000d29e  mov     [rsp+410h+var_3B8], rdx
0x18000d2a3  xor     edi, edi
0x18000d2a5  mov     ebx, edi
0x18000d2a7  mov     [rsp+410h+var_3D0], rdi
0x18000d2ac  mov     dword ptr [rsp+410h+var_3E0], edi
0x18000d2b0  mov     r13d, edi
0x18000d2b3  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x18000d2ba  mov     [rsp+410h+var_3A0], rax
0x18000d2bf  mov     [rbp+310h+var_384], 1
0x18000d2c6  mov     [rbp+310h+var_380], rdi
0x18000d2ca  lea     rsi, aRpcgetallliste; "RpcGetAllListeners"
0x18000d2d1  cmp     cs:?g_bEnabled@CTraceBase@@0HA, edi; int CTraceBase::g_bEnabled
0x18000d2d7  jnz     short loc_18000D301
0x18000d2d9  lea     rcx, [rsp+410h+pguid]; pguid
0x18000d2de  call    cs:__imp_CoCreateGuid
0x18000d2e5  nop     dword ptr [rax+rax+00h]
0x18000d2ea  mov     eax, 1
0x18000d2ef  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, eax; ulong CTraceBase::g_NextShortActivityID
0x18000d2f7  inc     eax
0x18000d2f9  mov     [rbp+310h+var_388], eax
0x18000d2fc  jmp     loc_18000D3CC
0x18000d301  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000d308  jz      short loc_18000D32B
0x18000d30a  mov     [rsp+410h+ReturnLength], rsi
0x18000d30f  mov     r9d, 1
0x18000d315  lea     r8, [rsp+410h+var_3A0]
0x18000d31a  lea     rdx, aAddingTracePDS; "Adding trace %p, %d, %s"
0x18000d321  mov     ecx, 2; int
0x18000d326  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000d32b  mov     [rsp+410h+var_3D8], rdi
0x18000d330  lea     rcx, [rsp+410h+var_3D8]; struct CTraceBase **
0x18000d335  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18000d33a  test    eax, eax
0x18000d33c  js      short loc_18000D365
0x18000d33e  cmp     [rsp+410h+var_3D8], rbx
0x18000d343  jz      short loc_18000D365
0x18000d345  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000d34c  jz      short loc_18000D365
0x18000d34e  mov     r8d, 1
0x18000d354  lea     rdx, aTracecomponent; "TraceComponent %d: Warning TLS should b"...
0x18000d35b  mov     ecx, 2; int
0x18000d360  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000d365  xor     edx, edx; char *
0x18000d367  xor     ecx, ecx; lpTlsValue
0x18000d369  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18000d36e  lea     rcx, [rbp+310h+var_380]; struct CTraceBase **
0x18000d372  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18000d377  test    eax, eax
0x18000d379  js      short loc_18000D3B1
0x18000d37b  mov     rcx, [rbp+310h+var_380]
0x18000d37f  test    rcx, rcx
0x18000d382  jz      short loc_18000D3B1
0x18000d384  mov     rax, [rcx]
0x18000d387  lea     rdx, [rsp+410h+pguid]
0x18000d38c  mov     rax, [rax+20h]
0x18000d390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d395  mov     rcx, [rbp+310h+var_380]
0x18000d399  mov     rax, [rcx]
0x18000d39c  mov     rax, [rax+18h]
0x18000d3a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3a5  mov     [rbp+310h+var_388], eax
0x18000d3a8  mov     [rbp+310h+var_378], 1
0x18000d3af  jmp     short loc_18000D3CF
0x18000d3b1  mov     rdx, rsi; char *
0x18000d3b4  lea     rcx, [rsp+410h+var_3A0]; lpTlsValue
0x18000d3b9  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18000d3be  lea     rdx, [rbp+310h+var_388]; unsigned int *
0x18000d3c2  lea     rcx, [rsp+410h+pguid]; struct _GUID *
0x18000d3c7  call    ?GenerateTraceID@CTraceBase@@KAJPEAU_GUID@@PEAK@Z; CTraceBase::GenerateTraceID(_GUID *,ulong *)
0x18000d3cc  mov     [rbp+310h+var_378], edi
0x18000d3cf  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18000d3d6  mov     [rsp+410h+var_3A0], rax
0x18000d3db  mov     [rbp+310h+var_370], rsi
0x18000d3df  mov     qword ptr [rbp+310h+Pid], 0FFFFFFFFFFFFFFFFh
0x18000d3e7  mov     [rbp+310h+var_360], edi
0x18000d3ea  xor     edx, edx; Val
0x18000d3ec  mov     r8d, 208h; Size
0x18000d3f2  lea     rcx, [rbp+310h+var_35C]; void *
0x18000d3f6  call    memset_0
0x18000d3fb  cmp     [rbp+310h+var_360], ebx
0x18000d3fe  jz      short loc_18000D422
0x18000d400  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000d407  jz      short loc_18000D422
0x18000d409  mov     r9d, [rbp+310h+var_388]
0x18000d40d  mov     r8, [rbp+310h+var_370]
0x18000d411  lea     rdx, aTraceRpcSWithT; "TRACE RPC %s with Trace ID 0x%x"
0x18000d418  mov     ecx, 2; int
0x18000d41d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000d422  mov     esi, cs:?g_DebugTraceComponent@@3KA; ulong g_DebugTraceComponent
0x18000d428  and     esi, 1
0x18000d42b  mov     qword ptr [rbp+310h+Pid], 0FFFFFFFFFFFFFFFFh
0x18000d433  lea     rdx, [rbp+310h+Pid+4]; Pid
0x18000d437  xor     ecx, ecx; Binding
0x18000d439  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000d440  nop     dword ptr [rax+rax+00h]
0x18000d445  mov     edi, eax
0x18000d447  test    eax, eax
0x18000d449  jle     short loc_18000D454
0x18000d44b  movzx   edi, ax
0x18000d44e  or      edi, 80070000h
0x18000d454  test    edi, edi
0x18000d456  js      loc_18000D510
0x18000d45c  lea     rdx, [rbp+310h+Pid]; pSessionId
0x18000d460  mov     ecx, [rbp+310h+Pid+4]; dwProcessId
0x18000d463  call    cs:__imp_ProcessIdToSessionId
0x18000d46a  nop     dword ptr [rax+rax+00h]
0x18000d46f  test    esi, esi
0x18000d471  jz      loc_18000D510
0x18000d477  mov     r8d, [rbp+310h+Pid+4]; dwProcessId
0x18000d47b  xor     edx, edx; bInheritHandle
0x18000d47d  mov     ecx, 400h; dwDesiredAccess
0x18000d482  call    cs:__imp_OpenProcess
0x18000d489  nop     dword ptr [rax+rax+00h]
0x18000d48e  mov     rsi, rax
0x18000d491  test    rax, rax
0x18000d494  jz      short loc_18000D510
0x18000d496  mov     [rsp+410h+ReturnLength], rbx; ReturnLength
0x18000d49b  mov     r9d, 110h; ProcessInformationLength
0x18000d4a1  lea     r8, [rbp+310h+ProcessInformation]; ProcessInformation
0x18000d4a8  mov     edx, 1Bh; ProcessInformationClass
0x18000d4ad  mov     rcx, rax; ProcessHandle
0x18000d4b0  call    cs:__imp_NtQueryInformationProcess
0x18000d4b7  nop     dword ptr [rax+rax+00h]
0x18000d4bc  mov     edi, eax
0x18000d4be  or      edi, 10000000h
0x18000d4c4  jl      short loc_18000D501
0x18000d4c6  mov     edx, 5Ch ; '\'; Ch
0x18000d4cb  mov     rcx, [rbp+310h+Str]; Str
0x18000d4d2  call    cs:__imp_wcsrchr
0x18000d4d9  nop     dword ptr [rax+rax+00h]
0x18000d4de  test    rax, rax
0x18000d4e1  jnz     short loc_18000D4EC
0x18000d4e3  mov     rax, [rbp+310h+Str]
0x18000d4ea  jmp     short loc_18000D4F0
0x18000d4ec  add     rax, 2
0x18000d4f0  mov     r8, rax; unsigned __int16 *
0x18000d4f3  mov     edx, 104h; unsigned __int64
0x18000d4f8  lea     rcx, [rbp+310h+var_35C]; unsigned __int16 *
0x18000d4fc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d501  mov     rcx, rsi; hObject
0x18000d504  call    cs:__imp_CloseHandle
0x18000d50b  nop     dword ptr [rax+rax+00h]
0x18000d510  cmp     [rbp+310h+var_360], ebx
0x18000d513  jz      short loc_18000D560
0x18000d515  test    edi, edi
0x18000d517  js      short loc_18000D546
0x18000d519  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000d520  jz      short loc_18000D560
0x18000d522  lea     rax, [rbp+310h+var_35C]
0x18000d526  mov     [rsp+410h+ReturnLength], rax
0x18000d52b  mov     r9d, [rbp+310h+Pid]
0x18000d52f  mov     r8d, [rbp+310h+Pid+4]
0x18000d533  lea     rdx, aRpcCallerPidDS; "RPC Caller: PID %d, SessID %d, Process "...
0x18000d53a  mov     ecx, 2; int
0x18000d53f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000d544  jmp     short loc_18000D560
0x18000d546  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000d54d  jz      short loc_18000D560
0x18000d54f  lea     rdx, aRpcCallerUnkno; "RPC Caller: Unknown"
0x18000d556  mov     ecx, 2; int
0x18000d55b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000d560  test    r14, r14
0x18000d563  jz      loc_18000D8EA
0x18000d569  test    r15, r15
0x18000d56c  jz      loc_18000D8EA
0x18000d572  cmp     r12d, 1
0x18000d576  jnz     loc_18000D8EA
0x18000d57c  xor     esi, esi
0x18000d57e  mov     [r14], rsi
0x18000d581  mov     [r15], esi
0x18000d584  xor     ecx, ecx; BindingHandle
0x18000d586  call    cs:__imp_RpcImpersonateClient
0x18000d58d  nop     dword ptr [rax+rax+00h]
0x18000d592  mov     edi, eax
0x18000d594  test    eax, eax
0x18000d596  jle     short loc_18000D5A1
0x18000d598  movzx   edi, ax
0x18000d59b  or      edi, 80070000h
0x18000d5a1  test    edi, edi
0x18000d5a3  jns     short loc_18000D5C5
0x18000d5a5  lea     r9, aRpcgetallliste; "RpcGetAllListeners"
0x18000d5ac  mov     r8d, edi
0x18000d5af  lea     rdx, aRpcimpersonate; "RpcImpersonateClient failed: 0x%x in %s"
0x18000d5b6  mov     ecx, 8; int
0x18000d5bb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000d5c0  jmp     loc_18000D8F1
0x18000d5c5  mov     r12, rsi
0x18000d5c8  mov     [rsp+410h+var_3C0], rsi
0x18000d5cd  mov     rax, cs:qword_18012EDF8
0x18000d5d4  test    rax, rax
0x18000d5d7  jz      short loc_18000D5EB
0x18000d5d9  mov     rbx, rax
0x18000d5dc  mov     rax, [rax]
0x18000d5df  mov     rcx, rbx
0x18000d5e2  mov     rax, [rax+8]
0x18000d5e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5eb  mov     rax, [rbx]
0x18000d5ee  lea     rdx, [rsp+410h+var_3D0]
0x18000d5f3  mov     rcx, rbx
0x18000d5f6  mov     rax, [rax+78h]
0x18000d5fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5ff  mov     rcx, [rsp+410h+var_3D0]
0x18000d604  mov     rax, [rcx]
0x18000d607  lea     rdx, [rsp+410h+var_3E0]
0x18000d60c  mov     rax, [rax+20h]
0x18000d610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d615  mov     eax, dword ptr [rsp+410h+var_3E0]
0x18000d619  test    eax, eax
0x18000d61b  jnz     short loc_18000D635
0x18000d61d  mov     edi, esi
0x18000d61f  lea     rdx, aNoListeners; "No listeners"
0x18000d626  mov     ecx, 8; int
0x18000d62b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000d630  jmp     loc_18000D782
0x18000d635  mov     rdi, rax
0x18000d638  mov     eax, 8
0x18000d63d  mul     rdi
0x18000d640  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000d647  cmovb   rax, rcx
0x18000d64b  add     rax, 8
0x18000d64f  cmovb   rax, rcx
0x18000d653  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d65a  mov     rcx, rax; unsigned __int64
0x18000d65d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000d662  test    rax, rax
0x18000d665  jz      loc_18000D77D
0x18000d66b  mov     [rax], rdi
0x18000d66e  lea     r13, [rax+8]
0x18000d672  lea     rax, ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18000d679  mov     [rsp+410h+ReturnLength], rax; void (*)(void *)
0x18000d67e  lea     r9, ??0?$SmartPtr@VIListener@@@@QEAA@XZ; void (*)(void *)
0x18000d685  mov     r8, rdi; unsigned __int64
0x18000d688  mov     edx, 8; unsigned __int64
0x18000d68d  mov     rcx, r13; void *
0x18000d690  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18000d695  test    r13, r13
0x18000d698  jz      loc_18000D77D
0x18000d69e  mov     rcx, [rsp+410h+var_3D0]
0x18000d6a3  mov     rax, [rcx]
0x18000d6a6  lea     r8, [rsp+410h+var_3E0]
0x18000d6ab  mov     rdx, r13
0x18000d6ae  mov     rax, [rax+28h]
0x18000d6b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6b7  mov     edi, eax
0x18000d6b9  test    eax, eax
0x18000d6bb  jns     short loc_18000D6DD
0x18000d6bd  lea     r9, aRpcgetallliste; "RpcGetAllListeners"
0x18000d6c4  mov     r8d, eax
0x18000d6c7  lea     rdx, aListGetlistFai; "List->GetList failed: 0x%x in %s"
0x18000d6ce  mov     ecx, 8; int
0x18000d6d3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000d6d8  jmp     loc_18000D782
0x18000d6dd  cmp     dword ptr [rsp+410h+var_3E0], esi
0x18000d6e1  jbe     loc_18000D8C7
0x18000d6e7  mov     r14d, esi
0x18000d6ea  nop     word ptr [rax+rax+00h]
0x18000d6f0  mov     eax, esi
0x18000d6f2  lea     r12, ds:0[rax*8]
0x18000d6fa  mov     rcx, [r12+r13]
0x18000d6fe  mov     rax, [rcx]
0x18000d701  mov     edx, 1
0x18000d706  mov     rax, [rax+60h]
0x18000d70a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d70f  mov     edi, eax
0x18000d711  test    eax, eax
0x18000d713  jns     short loc_18000D736
0x18000d715  mov     rcx, [r12+r13]
0x18000d719  mov     qword ptr [r12+r13], 0
0x18000d721  test    rcx, rcx
0x18000d724  jz      short loc_18000D732
0x18000d726  mov     rax, [rcx]
0x18000d729  mov     rax, [rax+10h]
0x18000d72d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d732  xor     edi, edi
0x18000d734  jmp     short loc_18000D739
0x18000d736  inc     r14d
0x18000d739  inc     esi
0x18000d73b  cmp     esi, dword ptr [rsp+410h+var_3E0]
0x18000d73f  jb      short loc_18000D6F0
0x18000d741  mov     dword ptr [rsp+410h+var_3D8], r14d
0x18000d746  test    r14d, r14d
0x18000d749  mov     r14, [rsp+410h+var_3B8]
0x18000d74e  jz      loc_18000D8C2
  ... truncated ...
```
