# RpcLicensingServerPing

- ea: `0x180099bd0`
- end: `0x180099d00`
- name: `RpcLicensingServerPing`
- size: `304`
- prototype: `char __fastcall(__int64, _DWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callees

- `0x18000a210`
- `0x1800241a4`
- `0x180093fc0`
- `0x180099bd0`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099c5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099c5a`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180099c50`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180099c50`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180099bfc`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180099bfc`
- `RPCRT4!RpcRevertToSelf` at `0x180099c74`
- `RPCRT4!RpcRevertToSelf` at `0x180099c7c`
- `RPCRT4!RpcRevertToSelf` at `0x180099c74`
- `RPCRT4!RpcRevertToSelf` at `0x180099c7c`
- `RPCRT4!RpcImpersonateClient` at `0x180099c36`
- `RPCRT4!RpcImpersonateClient` at `0x180099c36`

## string_xrefs

- `0x180099c40`: `RpcLicensingServerPing FAILED - Error in RpcImpersonateClient: 0x%x`
- `0x180099c60`: `RpcLicensingServerPing FAILED - Error in ProcessIdToSessionId: 0x%x`

## pseudocode

```c
char __fastcall RpcLicensingServerPing(__int64 a1, _DWORD *a2)
{
  unsigned int v3; // eax
  unsigned int v4; // eax
  DWORD LastError; // eax
  int InstanceOfLicenseManager; // eax
  unsigned int Pid; // [rsp+38h] [rbp+18h] BYREF
  DWORD pSessionId; // [rsp+40h] [rbp+20h] BYREF
  struct IEnfLicenseManager *v10; // [rsp+48h] [rbp+28h] BYREF

  v10 = 0;
  Pid = 0;
  pSessionId = 0;
  v3 = I_RpcBindingInqLocalClientPID(0, &Pid);
  if ( v3 )
  {
    _DbgPrintMessage(8, "RpcLicensingServerPing FAILED - Error in I_RpcBindingInqLocalClientPID: 0x%x", v3);
    goto LABEL_14;
  }
  _DbgPrintMessage(1, "TSENF: Ping is received from Process ID 0x%x", Pid);
  v4 = RpcImpersonateClient(0);
  if ( v4 )
    goto LABEL_5;
  if ( !ProcessIdToSessionId(Pid, &pSessionId) )
  {
    LastError = GetLastError();
    _DbgPrintMessage(8, "RpcLicensingServerPing FAILED - Error in ProcessIdToSessionId: 0x%x", LastError);
    RpcRevertToSelf();
    goto LABEL_14;
  }
  v4 = RpcRevertToSelf();
  if ( v4 )
  {
LABEL_5:
    _DbgPrintMessage(8, "RpcLicensingServerPing FAILED - Error in RpcImpersonateClient: 0x%x", v4);
  }
  else if ( g_pEnfCore )
  {
    InstanceOfLicenseManager = CEnforcementCore::GetInstanceOfLicenseManager(g_pEnfCore, &v10);
    if ( InstanceOfLicenseManager >= 0 )
      (*(void (__fastcall **)(struct IEnfLicenseManager *, _QWORD, _QWORD))(*(_QWORD *)v10 + 72LL))(
        v10,
        pSessionId,
        Pid);
    else
      _DbgPrintMessage(
        8,
        "GetInstanceOfLicenseManager failed: 0x%x in %s",
        InstanceOfLicenseManager,
        "RpcLicensingServerPing");
  }
  else
  {
    _DbgPrintMessage(8, "RpcLicensingServerPing FAILED - Enforcement core not started");
  }
LABEL_14:
  *a2 = 0;
  SmartPtr<ITSLicensePolicy>::~SmartPtr<ITSLicensePolicy>(&v10);
  return 1;
}

```

## disassembly

```asm
0x180099bd0  mov     [rsp-8+arg_0], rbx
0x180099bd5  push    rbp
0x180099bd6  mov     rbp, rsp
0x180099bd9  sub     rsp, 20h
0x180099bdd  mov     rbx, rdx
0x180099be0  mov     [rbp+arg_18], 0
0x180099be8  lea     rdx, [rbp+Pid]; Pid
0x180099bec  mov     [rbp+Pid], 0
0x180099bf3  xor     ecx, ecx; Binding
0x180099bf5  mov     [rbp+pSessionId], 0
0x180099bfc  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180099c02  test    eax, eax
0x180099c04  jz      short loc_180099C1F
0x180099c06  lea     rdx, aRpclicensingse_2; "RpcLicensingServerPing FAILED - Error i"...
0x180099c0d  mov     r8d, eax
0x180099c10  mov     ecx, 8; int
0x180099c15  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180099c1a  jmp     loc_180099CE4
0x180099c1f  mov     r8d, [rbp+Pid]
0x180099c23  lea     rdx, aTsenfPingIsRec; "TSENF: Ping is received from Process ID"...
0x180099c2a  mov     ecx, 1; int
0x180099c2f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180099c34  xor     ecx, ecx; BindingHandle
0x180099c36  call    cs:__imp_RpcImpersonateClient
0x180099c3c  test    eax, eax
0x180099c3e  jz      short loc_180099C49
0x180099c40  lea     rdx, aRpclicensingse_6; "RpcLicensingServerPing FAILED - Error i"...
0x180099c47  jmp     short loc_180099C0D
0x180099c49  mov     ecx, [rbp+Pid]; dwProcessId
0x180099c4c  lea     rdx, [rbp+pSessionId]; pSessionId
0x180099c50  call    cs:__imp_ProcessIdToSessionId
0x180099c56  test    eax, eax
0x180099c58  jnz     short loc_180099C7C
0x180099c5a  call    cs:__imp_GetLastError
0x180099c60  lea     rdx, aRpclicensingse_3; "RpcLicensingServerPing FAILED - Error i"...
0x180099c67  mov     ecx, 8; int
0x180099c6c  mov     r8d, eax
0x180099c6f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180099c74  call    cs:__imp_RpcRevertToSelf
0x180099c7a  jmp     short loc_180099CE4
0x180099c7c  call    cs:__imp_RpcRevertToSelf
0x180099c82  test    eax, eax
0x180099c84  jnz     short loc_180099C40
0x180099c86  mov     rcx, cs:?g_pEnfCore@@3PEAVCEnforcementCore@@EA; this
0x180099c8d  test    rcx, rcx
0x180099c90  jnz     short loc_180099CA3
0x180099c92  lea     rdx, aRpclicensingse_1; "RpcLicensingServerPing FAILED - Enforce"...
0x180099c99  lea     ecx, [rax+8]; int
0x180099c9c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180099ca1  jmp     short loc_180099CE4
0x180099ca3  lea     rdx, [rbp+arg_18]; struct IEnfLicenseManager **
0x180099ca7  call    ?GetInstanceOfLicenseManager@CEnforcementCore@@UEAAJPEAPEAVIEnfLicenseManager@@@Z; CEnforcementCore::GetInstanceOfLicenseManager(IEnfLicenseManager * *)
0x180099cac  test    eax, eax
0x180099cae  jns     short loc_180099CCD
0x180099cb0  lea     r9, aRpclicensingse_7; "RpcLicensingServerPing"
0x180099cb7  mov     r8d, eax
0x180099cba  lea     rdx, aGetinstanceofl_0; "GetInstanceOfLicenseManager failed: 0x%"...
0x180099cc1  mov     ecx, 8; int
0x180099cc6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180099ccb  jmp     short loc_180099CE4
0x180099ccd  mov     rcx, [rbp+arg_18]
0x180099cd1  mov     r8d, [rbp+Pid]
0x180099cd5  mov     rdx, [rcx]
0x180099cd8  mov     rax, [rdx+48h]
0x180099cdc  mov     edx, [rbp+pSessionId]
0x180099cdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099ce4  lea     rcx, [rbp+arg_18]
0x180099ce8  mov     dword ptr [rbx], 0
0x180099cee  call    ??1?$SmartPtr@VITSLicensePolicy@@@@QEAA@XZ; SmartPtr<ITSLicensePolicy>::~SmartPtr<ITSLicensePolicy>(void)
0x180099cf3  mov     rbx, [rsp+20h+arg_0]
0x180099cf8  mov     al, 1
0x180099cfa  add     rsp, 20h
0x180099cfe  pop     rbp
0x180099cff  retn
```
