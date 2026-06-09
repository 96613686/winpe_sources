# RCloseServiceHandle

- ea: `0x1400127f0`
- end: `0x1400129ec`
- name: `RCloseServiceHandle`
- size: `508`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x1400127d0`

## callees

- `0x140004c58`
- `0x1400083f0`
- `0x1400127f0`
- `0x1400129f4`
- `0x140012dc8`
- `0x140012e3c`
- `0x140013b0c`
- `0x14008196c`

## import_xrefs

- `RPCRT4!RpcServerInqBindingHandle` at `0x140012824`
- `RPCRT4!RpcServerInqBindingHandle` at `0x140012824`
- `RPCRT4!RpcImpersonateClient` at `0x140012906`
- `RPCRT4!RpcImpersonateClient` at `0x140012906`
- `RPCRT4!RpcRevertToSelf` at `0x140012940`
- `RPCRT4!RpcRevertToSelf` at `0x140012940`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1400129b8`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1400129b8`
- `ntdll!NtCloseObjectAuditAlarm` at `0x14001292e`
- `ntdll!NtCloseObjectAuditAlarm` at `0x14001292e`
- `ntdll!RtlInitUnicodeString` at `0x140012919`
- `ntdll!RtlInitUnicodeString` at `0x140012919`
- `ntdll!RtlFreeHeap` at `0x1400128bc`
- `ntdll!RtlFreeHeap` at `0x1400128bc`

## pseudocode

```c
__int64 __fastcall RCloseServiceHandle(PVOID *a1)
{
  struct _SC_HANDLE_STRUCT *v2; // rcx
  __int64 result; // rax
  CServiceRecord *v4; // rbx
  RPC_STATUS v5; // ebx
  NTSTATUS v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // ebx
  RPC_STATUS v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  unsigned int v12; // ecx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v14; // [rsp+60h] [rbp+20h] BYREF
  unsigned int Pid; // [rsp+68h] [rbp+28h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+70h] [rbp+30h] BYREF

  Pid = 0;
  v14 = 0;
  Binding = 0;
  DestinationString = 0;
  if ( !RpcServerInqBindingHandle(&Binding) )
    ScSetTcpKeepalive();
  v2 = (struct _SC_HANDLE_STRUCT *)*a1;
  if ( !*a1 )
    return 6;
  if ( *(_DWORD *)v2 == 1215456627 )
  {
    ScProcessServiceHandleClose(v2, 0, &v14);
    v4 = (CServiceRecord *)*((_QWORD *)*a1 + 2);
    CServiceRecord::RemoveHandleTrackingEntryForPid(v4, *((_DWORD *)*a1 + 3));
    ScDecrementServiceHandlesCountAndRelease(v4, 1);
    v5 = RpcImpersonateClient(0);
    RtlInitUnicodeString(&DestinationString, L"SC Manager");
    v6 = NtCloseObjectAuditAlarm(&DestinationString, *a1, *((_BYTE *)*a1 + 4) & 1);
    if ( v6 < 0
      && WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 14, WPP_1e8a53e398193c11e9533327b920648d_Traceguids, (unsigned int)v6);
    }
    if ( !v5 )
    {
      v7 = RpcRevertToSelf();
      v8 = v7;
      if ( v7 )
      {
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 15, WPP_1e8a53e398193c11e9533327b920648d_Traceguids, v7);
        }
        ScLogEvent(5u, L"RpcRevertToSelf", v8);
      }
    }
    goto LABEL_9;
  }
  if ( *(_DWORD *)v2 != 1215456115 )
    return 6;
  ScProcessServiceHandleClose(v2, 1, &v14);
LABEL_9:
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->UserInfo) & 0x40000) != 0 )
  {
    v9 = I_RpcBindingInqLocalClientPID(0, &Pid);
    v12 = 0;
    if ( !v9 )
      v12 = Pid;
    WPP_SF_qL(WPP_GLOBAL_Control->StubInfo, v10, v11, *a1, v12);
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *a1);
  result = v14;
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x1400127f0  mov     [rsp-18h+arg_18], rbx
0x1400127f5  push    rbp
0x1400127f6  push    rdi
0x1400127f7  push    r14
0x1400127f9  mov     rbp, rsp
0x1400127fc  sub     rsp, 40h
0x140012800  mov     rdi, rcx
0x140012803  mov     [rbp+Pid], 0
0x14001280a  xorps   xmm0, xmm0
0x14001280d  mov     [rbp+arg_0], 0
0x140012814  lea     rcx, [rbp+Binding]; Binding
0x140012818  mov     [rbp+Binding], 0
0x140012820  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140012824  call    cs:__imp_RpcServerInqBindingHandle
0x14001282a  test    eax, eax
0x14001282c  jz      loc_140012955
0x140012832  mov     rcx, [rdi]; struct _SC_HANDLE_STRUCT *
0x140012835  test    rcx, rcx
0x140012838  jz      loc_1400129E2
0x14001283e  cmp     dword ptr [rcx], 48726573h
0x140012844  lea     r14, WPP_GLOBAL_Control
0x14001284b  jz      loc_1400128DA
0x140012851  cmp     dword ptr [rcx], 48726373h
0x140012857  jnz     loc_1400129E2
0x14001285d  lea     r8, [rbp+arg_0]; unsigned int *
0x140012861  mov     edx, 1; int
0x140012866  call    ?ScProcessServiceHandleClose@@YAXPEAU_SC_HANDLE_STRUCT@@HPEAK@Z; ScProcessServiceHandleClose(_SC_HANDLE_STRUCT *,int,ulong *)
0x14001286b  jmp     short loc_140012891
0x14001286d  mov     rcx, cs:WPP_GLOBAL_Control
0x140012874  cmp     rcx, r14
0x140012877  jnz     loc_14001298B
0x14001287d  mov     r8d, ebx
0x140012880  lea     rdx, aRpcreverttosel; "RpcRevertToSelf"
0x140012887  mov     ecx, 5; unsigned int
0x14001288c  call    ?ScLogEvent@@YAXKZZ; ScLogEvent(ulong,...)
0x140012891  mov     rcx, cs:WPP_GLOBAL_Control
0x140012898  cmp     rcx, r14
0x14001289b  jz      short loc_1400128AA
0x14001289d  test    dword ptr [rcx+1Ch], 40000h
0x1400128a4  jnz     loc_1400129B2
0x1400128aa  mov     rcx, gs:60h
0x1400128b3  xor     edx, edx; Flags
0x1400128b5  mov     r8, [rdi]; P
0x1400128b8  mov     rcx, [rcx+30h]; HeapHandle
0x1400128bc  call    cs:__imp_RtlFreeHeap
0x1400128c2  mov     eax, [rbp+arg_0]
0x1400128c5  mov     qword ptr [rdi], 0
0x1400128cc  mov     rbx, [rsp+40h+arg_18]
0x1400128d1  add     rsp, 40h
0x1400128d5  pop     r14
0x1400128d7  pop     rdi
0x1400128d8  pop     rbp
0x1400128d9  retn
0x1400128da  lea     r8, [rbp+arg_0]; unsigned int *
0x1400128de  xor     edx, edx; int
0x1400128e0  call    ?ScProcessServiceHandleClose@@YAXPEAU_SC_HANDLE_STRUCT@@HPEAK@Z; ScProcessServiceHandleClose(_SC_HANDLE_STRUCT *,int,ulong *)
0x1400128e5  mov     rdx, [rdi]
0x1400128e8  mov     rbx, [rdx+10h]
0x1400128ec  mov     edx, [rdx+0Ch]; unsigned int
0x1400128ef  mov     rcx, rbx; this
0x1400128f2  call    ?RemoveHandleTrackingEntryForPid@CServiceRecord@@QEAAXK@Z; CServiceRecord::RemoveHandleTrackingEntryForPid(ulong)
0x1400128f7  mov     edx, 1; int
0x1400128fc  mov     rcx, rbx; struct CServiceRecord *
0x1400128ff  call    ?ScDecrementServiceHandlesCountAndRelease@@YAXPEAVCServiceRecord@@H@Z; ScDecrementServiceHandlesCountAndRelease(CServiceRecord *,int)
0x140012904  xor     ecx, ecx; BindingHandle
0x140012906  call    cs:__imp_RpcImpersonateClient
0x14001290c  lea     rdx, aScManager; "SC Manager"
0x140012913  mov     ebx, eax
0x140012915  lea     rcx, [rbp+DestinationString]; DestinationString
0x140012919  call    cs:__imp_RtlInitUnicodeString
0x14001291f  mov     rdx, [rdi]; HandleId
0x140012922  lea     rcx, [rbp+DestinationString]; SubsystemName
0x140012926  mov     r8b, [rdx+4]
0x14001292a  and     r8b, 1; GenerateOnClose
0x14001292e  call    cs:__imp_NtCloseObjectAuditAlarm
0x140012934  test    eax, eax
0x140012936  js      short loc_14001295F
0x140012938  test    ebx, ebx
0x14001293a  jnz     loc_140012891
0x140012940  call    cs:__imp_RpcRevertToSelf
0x140012946  mov     ebx, eax
0x140012948  test    eax, eax
0x14001294a  jz      loc_140012891
0x140012950  jmp     loc_14001286D
0x140012955  call    ?ScSetTcpKeepalive@@YAXXZ; ScSetTcpKeepalive(void)
0x14001295a  jmp     loc_140012832
0x14001295f  mov     rcx, cs:WPP_GLOBAL_Control
0x140012966  cmp     rcx, r14
0x140012969  jz      short loc_140012938
0x14001296b  test    byte ptr [rcx+1Ch], 1
0x14001296f  jz      short loc_140012938
0x140012971  mov     rcx, [rcx+10h]
0x140012975  lea     r8, WPP_1e8a53e398193c11e9533327b920648d_Traceguids
0x14001297c  mov     edx, 0Eh
0x140012981  mov     r9d, eax
0x140012984  call    WPP_SF_d
0x140012989  jmp     short loc_140012938
0x14001298b  test    byte ptr [rcx+1Ch], 1
0x14001298f  jz      loc_14001287D
0x140012995  mov     rcx, [rcx+10h]
0x140012999  lea     r8, WPP_1e8a53e398193c11e9533327b920648d_Traceguids
0x1400129a0  mov     edx, 0Fh
0x1400129a5  mov     r9d, ebx
0x1400129a8  call    WPP_SF_d
0x1400129ad  jmp     loc_14001287D
0x1400129b2  lea     rdx, [rbp+Pid]; Pid
0x1400129b6  xor     ecx, ecx; Binding
0x1400129b8  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x1400129be  mov     r9, [rdi]
0x1400129c1  xor     ecx, ecx
0x1400129c3  test    eax, eax
0x1400129c5  cmovz   ecx, [rbp+Pid]
0x1400129c9  mov     [rsp+40h+var_20], ecx
0x1400129cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400129d4  mov     rcx, [rcx+10h]
0x1400129d8  call    WPP_SF_qL
0x1400129dd  jmp     loc_1400128AA
0x1400129e2  mov     eax, 6
0x1400129e7  jmp     loc_1400128CC
```
