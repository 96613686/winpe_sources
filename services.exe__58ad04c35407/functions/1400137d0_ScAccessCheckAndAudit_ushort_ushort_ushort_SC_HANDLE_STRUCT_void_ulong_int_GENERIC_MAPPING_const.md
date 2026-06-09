# ScAccessCheckAndAudit(ushort *,ushort *,ushort *,_SC_HANDLE_STRUCT *,void *,ulong,int,_GENERIC_MAPPING const *)

- ea: `0x1400137d0`
- end: `0x140013b05`
- name: `?ScAccessCheckAndAudit@@YAKPEAG00PEAU_SC_HANDLE_STRUCT@@PEAXKHPEBU_GENERIC_MAPPING@@@Z`
- size: `821`
- prototype: `unsigned int(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, struct _SC_HANDLE_STRUCT *, void *, unsigned int, int, const struct _GENERIC_MAPPING *)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400135b0`

## callees

- `0x140004c58`
- `0x1400137d0`
- `0x140013b0c`
- `0x14004401c`
- `0x140081a28`
- `0x140081db8`
- `0x14008446c`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x140013848`
- `RPCRT4!RpcImpersonateClient` at `0x140013848`
- `RPCRT4!RpcRevertToSelf` at `0x1400138e6`
- `RPCRT4!RpcRevertToSelf` at `0x1400138e6`
- `ntdll!NtAccessCheckAndAuditAlarm` at `0x1400138de`
- `ntdll!NtAccessCheckAndAuditAlarm` at `0x1400138de`
- `ntdll!RtlNtStatusToDosError` at `0x14001396b`
- `ntdll!RtlNtStatusToDosError` at `0x140013ab5`
- `ntdll!RtlNtStatusToDosError` at `0x14001396b`
- `ntdll!RtlNtStatusToDosError` at `0x140013ab5`
- `ntdll!RtlInitUnicodeString` at `0x140013815`
- `ntdll!RtlInitUnicodeString` at `0x140013823`
- `ntdll!RtlInitUnicodeString` at `0x140013831`
- `ntdll!RtlInitUnicodeString` at `0x140013815`
- `ntdll!RtlInitUnicodeString` at `0x140013823`
- `ntdll!RtlInitUnicodeString` at `0x140013831`

## pseudocode

```c
ULONG __fastcall ScAccessCheckAndAudit(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        DWORD *a4,
        PSECURITY_DESCRIPTOR a5,
        ACCESS_MASK a6,
        unsigned int a7,
        struct _GENERIC_MAPPING *a8)
{
  unsigned int v11; // edi
  RPC_STATUS v12; // eax
  RPC_STATUS v13; // ebx
  void *SecurityDescriptor; // rbp
  struct _GENERIC_MAPPING *GenericMapping; // rsi
  ACCESS_MASK DesiredAccess; // ebx
  int v17; // edi
  unsigned int v18; // eax
  unsigned int v19; // ebx
  NTSTATUS v20; // ecx
  int MaximumAllowedAccess; // eax
  unsigned int v23; // eax
  NTSTATUS Status; // [rsp+60h] [rbp-68h] BYREF
  struct _UNICODE_STRING ObjectName; // [rsp+68h] [rbp-60h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-50h] BYREF
  struct _UNICODE_STRING SubsystemName; // [rsp+88h] [rbp-40h] BYREF
  unsigned __int16 *GenerateOnClose; // [rsp+D0h] [rbp+8h] BYREF

  GenerateOnClose = a1;
  LOBYTE(GenerateOnClose) = 0;
  Status = 0;
  SubsystemName = 0;
  DestinationString = 0;
  ObjectName = 0;
  RtlInitUnicodeString(&SubsystemName, L"SC Manager");
  RtlInitUnicodeString(&DestinationString, a2);
  RtlInitUnicodeString(&ObjectName, a3);
  v11 = a7;
  if ( a7 && !*(_DWORD *)&g_ExemptRemoteCaller )
    ScPopulateAllowRemoteAccessServicesExemptionList();
  v12 = RpcImpersonateClient(0);
  v13 = v12;
  if ( v12 )
  {
    ScLogImpersonateFailureEvent(v12);
    return v13;
  }
  SecurityDescriptor = a5;
  GenericMapping = a8;
  if ( !v11 || *(_DWORD *)&g_ExemptRemoteCaller || (unsigned int)ScCheckRemoteCallerIsAllowed(a3) )
  {
    DesiredAccess = a6;
    goto LABEL_5;
  }
  DesiredAccess = a6;
  if ( (a6 & 0xD0072) == 0 )
  {
    if ( (a6 & 0x2000000) != 0 )
    {
      a7 = 0;
      MaximumAllowedAccess = ScGetMaximumAllowedAccess(SecurityDescriptor, GenericMapping, &a7);
      if ( MaximumAllowedAccess < 0 )
      {
        if ( MaximumAllowedAccess != -1073741790 )
        {
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->StubInfo,
              38,
              WPP_8f086be6c6f937952c5e847c48275da5_Traceguids,
              (unsigned int)MaximumAllowedAccess);
          }
          goto LABEL_18;
        }
      }
      else
      {
        v23 = a7 & 0xFFF2FF8D;
        if ( (a7 & 0xFFF2FF8D) != 0 )
          DesiredAccess = v23 | DesiredAccess & 0xFDFFFFFF;
        if ( !v23 )
          goto LABEL_18;
      }
    }
LABEL_5:
    v17 = NtAccessCheckAndAuditAlarm(
            &SubsystemName,
            a4,
            &DestinationString,
            &ObjectName,
            SecurityDescriptor,
            DesiredAccess,
            GenericMapping,
            0,
            a4 + 2,
            &Status,
            (PBOOLEAN)&GenerateOnClose);
    goto LABEL_6;
  }
LABEL_18:
  v17 = -1073741790;
LABEL_6:
  v18 = RpcRevertToSelf();
  v19 = v18;
  if ( v18 )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 39, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids, v18);
    ScLogEvent(5u, L"RpcRevertToSelf", v19);
    return v19;
  }
  else if ( v17 < 0 )
  {
    if ( v17 != -1073741790
      && WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 40, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids, (unsigned int)v17);
    }
    return RtlNtStatusToDosError(v17);
  }
  else
  {
    if ( (_BYTE)GenerateOnClose )
      a4[1] |= 1u;
    v20 = Status;
    if ( Status )
    {
      if ( Status != -1073741790
        && WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 0x10) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->StubInfo,
          41,
          WPP_8f086be6c6f937952c5e847c48275da5_Traceguids,
          (unsigned int)Status);
        v20 = Status;
      }
      return RtlNtStatusToDosError(v20);
    }
    else
    {
      return 0;
    }
  }
}

```

## disassembly

```asm
0x1400137d0  mov     rax, rsp
0x1400137d3  mov     [rax+8], rcx
0x1400137d7  push    rbx
0x1400137d8  push    rdi
0x1400137d9  push    r14
0x1400137db  push    r15
0x1400137dd  sub     rsp, 0A8h
0x1400137e4  xorps   xmm0, xmm0
0x1400137e7  mov     byte ptr [rax+8], 0
0x1400137eb  mov     rbx, rdx
0x1400137ee  mov     dword ptr [rax-68h], 0
0x1400137f5  xorps   xmm1, xmm1
0x1400137f8  lea     rdx, aScManager; "SC Manager"
0x1400137ff  lea     rcx, [rax-40h]; DestinationString
0x140013803  mov     r14, r9
0x140013806  movups  xmmword ptr [rax-40h], xmm0
0x14001380a  mov     r15, r8
0x14001380d  movups  xmmword ptr [rax-50h], xmm1
0x140013811  movups  xmmword ptr [rax-60h], xmm0
0x140013815  call    cs:__imp_RtlInitUnicodeString
0x14001381b  mov     rdx, rbx; SourceString
0x14001381e  lea     rcx, [rsp+0C8h+DestinationString]; DestinationString
0x140013823  call    cs:__imp_RtlInitUnicodeString
0x140013829  mov     rdx, r15; SourceString
0x14001382c  lea     rcx, [rsp+0C8h+ObjectName]; DestinationString
0x140013831  call    cs:__imp_RtlInitUnicodeString
0x140013837  mov     edi, [rsp+0C8h+arg_30]
0x14001383e  test    edi, edi
0x140013840  jnz     loc_140013985
0x140013846  xor     ecx, ecx; BindingHandle
0x140013848  call    cs:__imp_RpcImpersonateClient
0x14001384e  mov     ebx, eax
0x140013850  test    eax, eax
0x140013852  jnz     loc_14001399C
0x140013858  mov     [rsp+0C8h+arg_8], rbp
0x140013860  mov     rbp, [rsp+0C8h+arg_20]
0x140013868  mov     [rsp+0C8h+arg_10], rsi
0x140013870  mov     rsi, [rsp+0C8h+arg_38]
0x140013878  mov     [rsp+0C8h+var_28], r12
0x140013880  lea     r12, WPP_GLOBAL_Control
0x140013887  test    edi, edi
0x140013889  jnz     loc_1400139A7
0x14001388f  mov     ebx, [rsp+0C8h+arg_28]
0x140013896  lea     rcx, [rsp+0C8h+arg_0]
0x14001389e  mov     rdx, r14; HandleId
0x1400138a1  mov     [rsp+0C8h+GenerateOnClose], rcx; GenerateOnClose
0x1400138a6  lea     rax, [r14+8]
0x1400138aa  lea     rcx, [rsp+0C8h+Status]
0x1400138af  mov     [rsp+0C8h+AccessStatus], rcx; AccessStatus
0x1400138b4  lea     r9, [rsp+0C8h+ObjectName]; ObjectName
0x1400138b9  mov     [rsp+0C8h+GrantedAccess], rax; GrantedAccess
0x1400138be  lea     r8, [rsp+0C8h+DestinationString]; ObjectTypeName
0x1400138c3  mov     [rsp+0C8h+ObjectCreation], 0; ObjectCreation
0x1400138c8  lea     rcx, [rsp+0C8h+SubsystemName]; SubsystemName
0x1400138d0  mov     [rsp+0C8h+GenericMapping], rsi; GenericMapping
0x1400138d5  mov     [rsp+0C8h+DesiredAccess], ebx; DesiredAccess
0x1400138d9  mov     [rsp+0C8h+SecurityDescriptor], rbp; SecurityDescriptor
0x1400138de  call    cs:__imp_NtAccessCheckAndAuditAlarm
0x1400138e4  mov     edi, eax
0x1400138e6  call    cs:__imp_RpcRevertToSelf
0x1400138ec  mov     rsi, [rsp+0C8h+arg_10]
0x1400138f4  mov     ebx, eax
0x1400138f6  mov     rbp, [rsp+0C8h+arg_8]
0x1400138fe  test    eax, eax
0x140013900  jnz     short loc_140013937
0x140013902  test    edi, edi
0x140013904  js      loc_140013A81
0x14001390a  cmp     byte ptr [rsp+0C8h+arg_0], al
0x140013911  jnz     loc_140013AC0
0x140013917  mov     ecx, [rsp+0C8h+Status]; Status
0x14001391b  test    ecx, ecx
0x14001391d  jnz     short loc_14001395F
0x14001391f  xor     eax, eax
0x140013921  mov     r12, [rsp+0C8h+var_28]
0x140013929  add     rsp, 0A8h
0x140013930  pop     r15
0x140013932  pop     r14
0x140013934  pop     rdi
0x140013935  pop     rbx
0x140013936  retn
0x140013937  mov     rcx, cs:WPP_GLOBAL_Control
0x14001393e  cmp     rcx, r12
0x140013941  jnz     loc_140013A5A
0x140013947  mov     r8d, ebx
0x14001394a  lea     rdx, aRpcreverttosel; "RpcRevertToSelf"
0x140013951  mov     ecx, 5; unsigned int
0x140013956  call    ?ScLogEvent@@YAXKZZ; ScLogEvent(ulong,...)
0x14001395b  mov     eax, ebx
0x14001395d  jmp     short loc_140013921
0x14001395f  cmp     ecx, 0C0000022h
0x140013965  jnz     loc_140013ACA
0x14001396b  call    cs:__imp_RtlNtStatusToDosError
0x140013971  jmp     short loc_140013921
0x140013973  test    eax, eax
0x140013975  jnz     loc_140013896
0x14001397b  mov     edi, 0C0000022h
0x140013980  jmp     loc_1400138E6
0x140013985  cmp     cs:?g_ExemptRemoteCaller@@3HA, 0; int g_ExemptRemoteCaller
0x14001398c  jnz     loc_140013846
0x140013992  call    ?ScPopulateAllowRemoteAccessServicesExemptionList@@YAXXZ; ScPopulateAllowRemoteAccessServicesExemptionList(void)
0x140013997  jmp     loc_140013846
0x14001399c  mov     ecx, ebx; int
0x14001399e  call    ?ScLogImpersonateFailureEvent@@YAXJ@Z; ScLogImpersonateFailureEvent(long)
0x1400139a3  mov     eax, ebx
0x1400139a5  jmp     short loc_140013929
0x1400139a7  cmp     cs:?g_ExemptRemoteCaller@@3HA, 0; int g_ExemptRemoteCaller
0x1400139ae  jnz     loc_14001388F
0x1400139b4  mov     rcx, r15; unsigned __int16 *
0x1400139b7  call    ?ScCheckRemoteCallerIsAllowed@@YAHPEBG@Z; ScCheckRemoteCallerIsAllowed(ushort const *)
0x1400139bc  test    eax, eax
0x1400139be  jnz     loc_14001388F
0x1400139c4  mov     ebx, [rsp+0C8h+arg_28]
0x1400139cb  test    ebx, 0D0072h
0x1400139d1  jnz     short loc_14001397B
0x1400139d3  bt      ebx, 19h
0x1400139d7  jnb     loc_140013896
0x1400139dd  lea     r8, [rsp+0C8h+arg_30]; unsigned int *
0x1400139e5  mov     [rsp+0C8h+arg_30], eax
0x1400139ec  mov     rdx, rsi; GenericMapping
0x1400139ef  mov     rcx, rbp; SecurityDescriptor
0x1400139f2  call    ?ScGetMaximumAllowedAccess@@YAJPEAXPEBU_GENERIC_MAPPING@@PEAK@Z; ScGetMaximumAllowedAccess(void *,_GENERIC_MAPPING const *,ulong *)
0x1400139f7  test    eax, eax
0x1400139f9  js      short loc_140013A18
0x1400139fb  mov     eax, [rsp+0C8h+arg_30]
0x140013a02  and     eax, 0FFF2FF8Dh
0x140013a07  jz      loc_140013973
0x140013a0d  btr     ebx, 19h
0x140013a11  or      ebx, eax
0x140013a13  jmp     loc_140013973
0x140013a18  cmp     eax, 0C0000022h
0x140013a1d  jz      loc_140013896
0x140013a23  mov     rcx, cs:WPP_GLOBAL_Control
0x140013a2a  cmp     rcx, r12
0x140013a2d  jz      loc_14001397B
0x140013a33  test    byte ptr [rcx+1Ch], 1
0x140013a37  jz      loc_14001397B
0x140013a3d  mov     rcx, [rcx+10h]
0x140013a41  lea     r8, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids
0x140013a48  mov     edx, 26h ; '&'
0x140013a4d  mov     r9d, eax
0x140013a50  call    WPP_SF_d
0x140013a55  jmp     loc_14001397B
0x140013a5a  test    byte ptr [rcx+1Ch], 1
0x140013a5e  jz      loc_140013947
0x140013a64  mov     rcx, [rcx+10h]
0x140013a68  lea     r8, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids
0x140013a6f  mov     edx, 27h ; '''
0x140013a74  mov     r9d, ebx
0x140013a77  call    WPP_SF_d
0x140013a7c  jmp     loc_140013947
0x140013a81  cmp     edi, 0C0000022h
0x140013a87  jz      short loc_140013AB3
0x140013a89  mov     rcx, cs:WPP_GLOBAL_Control
0x140013a90  cmp     rcx, r12
0x140013a93  jz      short loc_140013AB3
0x140013a95  test    byte ptr [rcx+1Ch], 1
0x140013a99  jz      short loc_140013AB3
0x140013a9b  mov     rcx, [rcx+10h]
0x140013a9f  lea     r8, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids
0x140013aa6  mov     edx, 28h ; '('
0x140013aab  mov     r9d, edi
0x140013aae  call    WPP_SF_d
0x140013ab3  mov     ecx, edi; Status
0x140013ab5  call    cs:__imp_RtlNtStatusToDosError
0x140013abb  jmp     loc_140013921
0x140013ac0  or      dword ptr [r14+4], 1
0x140013ac5  jmp     loc_140013917
0x140013aca  mov     rax, cs:WPP_GLOBAL_Control
0x140013ad1  cmp     rax, r12
0x140013ad4  jz      loc_14001396B
0x140013ada  test    byte ptr [rax+1Ch], 10h
0x140013ade  jz      loc_14001396B
0x140013ae4  mov     r9d, ecx
0x140013ae7  lea     r8, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids
0x140013aee  mov     rcx, [rax+10h]
0x140013af2  mov     edx, 29h ; ')'
0x140013af7  call    WPP_SF_d
0x140013afc  mov     ecx, [rsp+0C8h+Status]
0x140013b00  jmp     loc_14001396B
```
