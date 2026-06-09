# RPC_SERVER::UseRpcProtocolSequence(ushort *,ushort *,uint,ushort *,void *,ulong,ulong,ushort * *,int,MTMLinkSymmetric *,RPCP_INTERFACE_GROUP *)

- ea: `0x18008f718`
- end: `0x18008ffaf`
- name: `?UseRpcProtocolSequence@RPC_SERVER@@QEAAJPEAG0I0PEAXKKPEAPEAGHPEAVMTMLinkSymmetric@@PEAVRPCP_INTERFACE_GROUP@@@Z`
- size: `2199`
- prototype: `__int64 __usercall@<rax>(PRTL_CRITICAL_SECTION CriticalSection@<rcx>, unsigned __int16 *@<rdx>, unsigned __int16 *@<r8>, unsigned int@<r9d>, unsigned __int16 *Src, struct _SECURITY_DESCRIPTOR *, unsigned int, unsigned int, unsigned __int16 **, int, struct MTMLinkSymmetric *, struct RPCP_INTERFACE_GROUP *)`
- caller_count: `5`
- callee_count: `29`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18008f200`
- `0x18008f2fc`
- `0x18008f670`
- `0x1800ad640`
- `0x1800b7800`

## callees

- `0x18000fd70`
- `0x18000fe44`
- `0x1800167d8`
- `0x18001e7d0`
- `0x180023a40`
- `0x18002cab0`
- `0x18002e750`
- `0x180068818`
- `0x180072f50`
- `0x18008f718`
- `0x180090a6c`
- `0x1800947e0`
- `0x180094994`
- `0x180096e78`
- `0x18009746c`
- `0x180097f68`
- `0x1800995e8`
- `0x180099608`
- `0x18009a570`
- `0x18009d1ac`
- `0x18009d77c`
- `0x1800a086c`
- `0x1800ada90`
- `0x1800adb74`
- `0x1800adc00`
- `0x1800b7c90`
- `0x1800b7ce4`
- `0x1800ce5d0`
- `0x1800d7010`

## import_xrefs

- `ntdll!_wcsicmp` at `0x18008f7c5`
- `ntdll!_wcsicmp` at `0x18008fa25`
- `ntdll!_wcsicmp` at `0x18008f7c5`
- `ntdll!_wcsicmp` at `0x18008fa25`
- `ntdll!DbgPrint` at `0x18008f83f`
- `ntdll!DbgPrint` at `0x18008f859`
- `ntdll!DbgPrint` at `0x18008f8b1`
- `ntdll!DbgPrint` at `0x18008f8cc`
- `ntdll!DbgPrint` at `0x18008f9aa`
- `ntdll!DbgPrint` at `0x18008f9bd`
- `ntdll!DbgPrint` at `0x18008f9db`
- `ntdll!DbgPrint` at `0x18008f83f`
- `ntdll!DbgPrint` at `0x18008f859`
- `ntdll!DbgPrint` at `0x18008f8b1`
- `ntdll!DbgPrint` at `0x18008f8cc`
- `ntdll!DbgPrint` at `0x18008f9aa`
- `ntdll!DbgPrint` at `0x18008f9bd`
- `ntdll!DbgPrint` at `0x18008f9db`
- `ntdll!_wcsnicmp` at `0x18008fa07`
- `ntdll!_wcsnicmp` at `0x18008fa07`
- `ntdll!RtlLeaveCriticalSection` at `0x18008f8f4`
- `ntdll!RtlLeaveCriticalSection` at `0x18008f961`
- `ntdll!RtlLeaveCriticalSection` at `0x18008fae7`
- `ntdll!RtlLeaveCriticalSection` at `0x18008fb3a`
- `ntdll!RtlLeaveCriticalSection` at `0x18008fc1c`
- `ntdll!RtlLeaveCriticalSection` at `0x18008fca2`
- `ntdll!RtlLeaveCriticalSection` at `0x18008fe13`
- `ntdll!RtlLeaveCriticalSection` at `0x18008fe49`
- `ntdll!RtlLeaveCriticalSection` at `0x18008ff1e`
- `ntdll!RtlLeaveCriticalSection` at `0x18008ff9c`
- `ntdll!RtlLeaveCriticalSection` at `0x18008f8f4`
- `ntdll!RtlLeaveCriticalSection` at `0x18008f961`
- `ntdll!RtlLeaveCriticalSection` at `0x18008fae7`
- `ntdll!RtlLeaveCriticalSection` at `0x18008fb3a`
- `ntdll!RtlLeaveCriticalSection` at `0x18008fc1c`
- `ntdll!RtlLeaveCriticalSection` at `0x18008fca2`
- `ntdll!RtlLeaveCriticalSection` at `0x18008fe13`
- `ntdll!RtlLeaveCriticalSection` at `0x18008fe49`
- `ntdll!RtlLeaveCriticalSection` at `0x18008ff1e`
- `ntdll!RtlLeaveCriticalSection` at `0x18008ff9c`
- `ntdll!RtlEnterCriticalSection` at `0x18008f868`
- `ntdll!RtlEnterCriticalSection` at `0x18008f911`
- `ntdll!RtlEnterCriticalSection` at `0x18008faa8`
- `ntdll!RtlEnterCriticalSection` at `0x18008fb8d`
- `ntdll!RtlEnterCriticalSection` at `0x18008fddb`
- `ntdll!RtlEnterCriticalSection` at `0x18008fefb`
- `ntdll!RtlEnterCriticalSection` at `0x18008ff36`
- `ntdll!RtlEnterCriticalSection` at `0x18008f868`
- `ntdll!RtlEnterCriticalSection` at `0x18008f911`
- `ntdll!RtlEnterCriticalSection` at `0x18008faa8`
- `ntdll!RtlEnterCriticalSection` at `0x18008fb8d`
- `ntdll!RtlEnterCriticalSection` at `0x18008fddb`
- `ntdll!RtlEnterCriticalSection` at `0x18008fefb`
- `ntdll!RtlEnterCriticalSection` at `0x18008ff36`

## string_xrefs

- `0x18008f9d4`: `RPC: To determine the symbolic stack, do an "ln" on the above addresses in the context of the faulting process.\n\n`
- `0x18008f831`: `Possible security threat: Insecure interface becomes remotely accessible`
- `0x18008f99c`: `Possible security threat: Server is forced to listen on all interfaces circumventing the firewall`

## pseudocode

```c
__int64 __fastcall RPC_SERVER::UseRpcProtocolSequence(
        PRTL_CRITICAL_SECTION CriticalSection,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned int a4,
        unsigned __int16 *Src,
        struct _SECURITY_DESCRIPTOR *a6,
        unsigned int a7,
        unsigned int a8,
        unsigned __int16 **a9,
        int a10,
        struct MTMLinkSymmetric *a11,
        struct RPCP_INTERFACE_GROUP *a12)
{
  unsigned int v12; // r15d
  wchar_t *v13; // r12
  __int64 result; // rax
  int v17; // eax
  struct MTMLinkSymmetric *v18; // r13
  void *v19; // r14
  struct RPC_ADDRESS *RpcAddress; // rdi
  __int64 v21; // rdx
  struct _GUID *v22; // rbx
  RPC_INTERFACE *v23; // rax
  __int64 FirewallTableCopy; // rax
  unsigned int FirewallExtensionIfNecessary; // eax
  unsigned int v26; // ebx
  struct RPC_ADDRESS *v27; // rax
  RPC_ADDRESS *v28; // rax
  RPC_ADDRESS *v29; // rbx
  struct RPC_ADDRESS *v30; // rcx
  unsigned int v31; // r14d
  RPC_ADDRESS *v32; // rbx
  unsigned int v33; // eax
  int v34; // r12d
  unsigned int v35; // r14d
  unsigned int v36; // r15d
  unsigned int v37; // ebx
  unsigned int v38; // r15d
  unsigned __int16 *v39; // rbx
  unsigned __int16 *v40; // rax
  struct RPCP_INTERFACE_GROUP *v41; // r15
  unsigned int v42; // eax
  int v43; // eax
  unsigned __int16 *v44; // rax
  int v45; // ebx
  struct _RTL_CRITICAL_SECTION *v46; // rcx
  int v47; // [rsp+50h] [rbp-10h] BYREF
  struct TRANS_INFO *v48; // [rsp+58h] [rbp-8h] BYREF

  v12 = a7;
  v13 = a3;
  v48 = 0;
  v47 = 0;
  if ( (Microsoft_Windows_RPCEnableBits & 2) != 0 )
    McTemplateU0zzzqqq_EtwEventWriteTransfer(
      (_DWORD)CriticalSection,
      (_DWORD)a2,
      (_DWORD)a3,
      (_DWORD)Src,
      (__int64)a2,
      a4,
      a7,
      a8);
  if ( !ThreadSelf() )
    return 14;
  RpcpPurgeEEInfo();
  if ( g_fServerSideDebugInfoEnabled )
  {
    result = InitializeServerSideCellHeapIfNecessary();
    if ( (_DWORD)result )
      return result;
  }
  if ( a10 && a12 )
    return 87;
  v17 = _wcsicmp(v13, L"ncalrpc");
  v18 = a11;
  if ( !v17 )
  {
    v19 = 0;
    RpcAddress = LrpcCreateRpcAddress();
    a7 = v12 & 0xFFFFFFFB;
    goto LABEL_45;
  }
  if ( gfRPCVerifierEnabled && !*((_DWORD *)pRpcVerifierSettings + 33) && !gfRemoteProtseqRegistered )
  {
    if ( gfUnsecureInterfaceRegistered )
    {
      DbgPrint("%s : type (0x%x)", "Possible security threat: Insecure interface becomes remotely accessible", 16);
      DbgPrint("RPC: Starting to listen on protseq: %S endpoint: %S\n", v13, Src);
      RtlEnterCriticalSection(CriticalSection);
      LODWORD(a9) = 0;
      while ( 1 )
      {
        v23 = (RPC_INTERFACE *)SIMPLE_DICT::Next((SIMPLE_DICT *)&CriticalSection[7].LockCount, (unsigned int *)&a9);
        if ( !v23 )
          break;
        if ( !(unsigned int)RPC_INTERFACE::IsSecure(v23) && (*(_DWORD *)(v21 + 8) & 2) == 0 )
        {
          v22 = (struct _GUID *)(v21 + 84);
          if ( !(unsigned int)IsInterfaceExempt((struct _GUID *)(v21 + 84), 1u) )
          {
            DbgPrint("RPC: Insecure interface UUID: ");
            DbgPrintUUID(v22);
            DbgPrint("\n");
          }
        }
      }
      RtlLeaveCriticalSection(CriticalSection);
    }
    gfRemoteProtseqRegistered = 1;
  }
  RtlEnterCriticalSection(&GlobalMutex);
  if ( !(unsigned int)DoFirewallInit()
    || (FirewallTableCopy = GetFirewallTableCopy(), v19 = (void *)FirewallTableCopy, pFirewallTable)
    && !FirewallTableCopy )
  {
    v26 = 14;
LABEL_106:
    v46 = &GlobalMutex;
    goto LABEL_107;
  }
  FirewallExtensionIfNecessary = LoadFirewallExtensionIfNecessary();
  v26 = FirewallExtensionIfNecessary;
  if ( FirewallExtensionIfNecessary && FirewallExtensionIfNecessary != 1764 )
    goto LABEL_106;
  RtlLeaveCriticalSection(&GlobalMutex);
  if ( !a2 && v19 && a8 == 1 )
  {
    if ( gfRPCVerifierEnabled && !*((_DWORD *)pRpcVerifierSettings + 33) )
    {
      DbgPrint(
        "%s : type (0x%x)",
        "Possible security threat: Server is forced to listen on all interfaces circumventing the firewall",
        32);
      DbgPrint("RPC: Offending Stack:\n");
      PrintCurrentStackTrace(2u, 4u);
      DbgPrint(
        "RPC: To determine the symbolic stack, do an \"ln\" on the above addresses in the context of the faulting process.\n\n");
    }
    if ( (unsigned int)IsCurrentUserAdmin() )
    {
      v26 = 5;
LABEL_41:
      FreeWrapper(v19);
      return v26;
    }
  }
  if ( _wcsnicmp(L"ncacn_", v13, 6u) )
  {
    FreeWrapper(v19);
    return 1703;
  }
  if ( _wcsicmp(L"ncacn_http", v13) && (v12 & 8) != 0 )
  {
    v26 = 87;
    goto LABEL_41;
  }
  v26 = LoadableTransportInfo(v13, &v48);
  if ( v26 )
    goto LABEL_41;
  v27 = OsfCreateRpcAddress(v48);
  RpcAddress = v27;
  if ( v27 && v18 )
    *((_DWORD *)v27 + 15) = 1;
LABEL_45:
  FreeWrapper(v19);
  if ( !RpcAddress )
    return 14;
  LODWORD(a9) = 0;
  if ( Src )
  {
    RtlEnterCriticalSection(CriticalSection);
    do
    {
      v28 = (RPC_ADDRESS *)SIMPLE_DICT::Next((SIMPLE_DICT *)&CriticalSection[1].SpinCount, (unsigned int *)&a9);
      v29 = v28;
      if ( !v28 )
      {
        RtlLeaveCriticalSection(CriticalSection);
        Src = DuplicateString(Src);
        if ( !Src )
          goto LABEL_51;
        v31 = 1;
        goto LABEL_66;
      }
    }
    while ( !RPC_ADDRESS::SameEndpointAndProtocolSequence(v28, a2, v13, Src) );
    RtlLeaveCriticalSection(CriticalSection);
    (*(void (__fastcall **)(struct RPC_ADDRESS *, __int64))(*(_QWORD *)RpcAddress + 8LL))(RpcAddress, 1);
    if ( !a10 )
      return 1740;
    if ( !v18 || (unsigned int)RPC_ADDRESS::LinkToInterfaceIfNecessary(v29, v18) )
      return 0;
    return 14;
  }
  RtlEnterCriticalSection(CriticalSection);
  v32 = (RPC_ADDRESS *)SIMPLE_DICT::Next((SIMPLE_DICT *)&CriticalSection[1].SpinCount, (unsigned int *)&a9);
  if ( !v32 )
  {
LABEL_65:
    RtlLeaveCriticalSection(CriticalSection);
    v31 = 0;
LABEL_66:
    v36 = a7;
    v37 = a7 & 4;
    if ( (a7 & 4) != 0 )
      (*(void (__fastcall **)(struct RPC_ADDRESS *))(*(_QWORD *)RpcAddress + 56LL))(RpcAddress);
    v38 = (*(__int64 (__fastcall **)(struct RPC_ADDRESS *, unsigned __int16 *, unsigned __int16 **, _QWORD, struct _SECURITY_DESCRIPTOR *, unsigned int, unsigned int))(*(_QWORD *)RpcAddress + 40LL))(
            RpcAddress,
            a2,
            &Src,
            a4,
            a6,
            v36,
            a8);
    if ( !v38 )
    {
      v39 = DuplicateString(v13);
      if ( !v39 )
      {
LABEL_70:
        FreeWrapper(Src);
        goto LABEL_51;
      }
      v40 = 0;
      if ( a2 )
      {
        v40 = DuplicateString(a2);
        if ( !v40 )
        {
LABEL_82:
          FreeWrapper(Src);
          (*(void (__fastcall **)(struct RPC_ADDRESS *, __int64))(*(_QWORD *)RpcAddress + 8LL))(RpcAddress, 1);
          FreeWrapper(v39);
          return 14;
        }
      }
      v41 = a12;
      v26 = RPC_ADDRESS::SetEndpointAndStuff(RpcAddress, v40, Src, v39, v31, a4, a6, a7, a8, a12);
      if ( v26 )
        goto LABEL_84;
      if ( v41 )
      {
        v42 = SIMPLE_DICT::Insert((struct RPCP_INTERFACE_GROUP *)((char *)v41 + 112), RpcAddress);
        v30 = RpcAddress;
        if ( v42 == -1 )
          goto LABEL_52;
        REFERENCED_OBJECT::AddReference(RpcAddress);
      }
      v43 = RPC_SERVER::AddAddress(CriticalSection, RpcAddress);
      if ( v43 == -1 )
      {
LABEL_51:
        v30 = RpcAddress;
LABEL_52:
        (*(void (__fastcall **)(struct RPC_ADDRESS *, __int64))(*(_QWORD *)RpcAddress + 8LL))(v30, 1);
        return 14;
      }
      *((_DWORD *)RpcAddress + 50) = v43;
      RtlEnterCriticalSection(CriticalSection);
      if ( v18 )
      {
        if ( !(unsigned int)MTMLinkSymmetric::Link((struct RPC_ADDRESS *)((char *)RpcAddress + 64), v18) )
        {
          (*(void (__fastcall **)(struct RPC_ADDRESS *, __int64))(*(_QWORD *)RpcAddress + 8LL))(RpcAddress, 1);
          RtlLeaveCriticalSection(CriticalSection);
          return 14;
        }
        *((_DWORD *)RpcAddress + 15) = 1;
      }
      v26 = (*(__int64 (__fastcall **)(struct RPC_ADDRESS *, _QWORD, _QWORD))(*(_QWORD *)RpcAddress + 88LL))(
              RpcAddress,
              (unsigned int)CriticalSection[1].LockCount,
              LODWORD(CriticalSection[6].OwningThread));
      RtlLeaveCriticalSection(CriticalSection);
      if ( !v26 )
      {
        (*(void (__fastcall **)(struct RPC_ADDRESS *))(*(_QWORD *)RpcAddress + 72LL))(RpcAddress);
        return 0;
      }
      return v26;
    }
    if ( !v37 )
    {
      (*(void (__fastcall **)(struct RPC_ADDRESS *, __int64))(*(_QWORD *)RpcAddress + 8LL))(RpcAddress, 1);
      return v38;
    }
    v39 = DuplicateString(v13);
    if ( !v39 )
      goto LABEL_70;
    v44 = 0;
    if ( a2 )
    {
      v44 = DuplicateString(a2);
      if ( !v44 )
        goto LABEL_82;
    }
    v26 = RPC_ADDRESS::SetEndpointAndStuff(RpcAddress, v44, Src, v39, v31, a4, a6, a7, a8, 0);
    if ( v26 )
    {
      FreeWrapper(Src);
LABEL_84:
      (*(void (__fastcall **)(struct RPC_ADDRESS *, __int64))(*(_QWORD *)RpcAddress + 8LL))(RpcAddress, 1);
      return v26;
    }
    RtlEnterCriticalSection(CriticalSection);
    v45 = QUEUE::PutOnQueue((QUEUE *)&CriticalSection[3].LockCount, RpcAddress, 0);
    RtlLeaveCriticalSection(CriticalSection);
    if ( v45 == 1 )
      goto LABEL_70;
    RtlEnterCriticalSection(CriticalSection);
    v26 = (*(__int64 (__fastcall **)(struct RPC_ADDRESS *, _QWORD, _QWORD))(*(_QWORD *)RpcAddress + 88LL))(
            RpcAddress,
            (unsigned int)CriticalSection[1].LockCount,
            LODWORD(CriticalSection[6].OwningThread));
    v46 = CriticalSection;
LABEL_107:
    RtlLeaveCriticalSection(v46);
    return v26;
  }
  while ( 1 )
  {
    v33 = RPC_ADDRESS::EquivalentDynamicEndpoint(v32, a2, v13, a6, a7, a12, a4, &v47);
    v34 = v47;
    v35 = v33;
    if ( v33 || v47 )
      break;
    v13 = a3;
    v32 = (RPC_ADDRESS *)SIMPLE_DICT::Next((SIMPLE_DICT *)&CriticalSection[1].SpinCount, (unsigned int *)&a9);
    if ( !v32 )
      goto LABEL_65;
  }
  RtlLeaveCriticalSection(CriticalSection);
  (*(void (__fastcall **)(struct RPC_ADDRESS *, __int64))(*(_QWORD *)RpcAddress + 8LL))(RpcAddress, 1);
  if ( !v35 && v34 )
  {
    if ( v18 )
    {
      if ( !(unsigned int)RPC_ADDRESS::LinkToInterfaceIfNecessary(v32, v18) )
        return 14;
    }
    else if ( *((_DWORD *)v32 + 15) )
    {
      *((_DWORD *)v32 + 15) = 0;
    }
  }
  return v35;
}

```

## disassembly

```asm
0x18008f718  mov     r11, rsp
0x18008f71b  mov     [r11+8], rbx
0x18008f71f  mov     [r11+20h], r9d
0x18008f723  mov     [r11+18h], r8
0x18008f727  mov     [r11+10h], rdx
0x18008f72b  push    rbp
0x18008f72c  push    rsi
0x18008f72d  push    rdi
0x18008f72e  push    r12
0x18008f730  push    r13
0x18008f732  push    r14
0x18008f734  push    r15
0x18008f736  mov     rbp, rsp
0x18008f739  sub     rsp, 60h
0x18008f73d  mov     r15d, [rbp+arg_30]
0x18008f741  xor     ebx, ebx
0x18008f743  test    cs:Microsoft_Windows_RPCEnableBits, 2
0x18008f74a  mov     r12, r8
0x18008f74d  mov     rdi, rdx
0x18008f750  mov     [rbp+var_8], rbx
0x18008f754  mov     rsi, rcx
0x18008f757  mov     [rbp+var_10], ebx
0x18008f75a  jz      short loc_18008F778
0x18008f75c  mov     eax, [rbp+arg_38]
0x18008f75f  mov     dword ptr [rsp+60h+var_28], eax
0x18008f763  mov     [r11-68h], r15d
0x18008f767  mov     [r11-70h], r9d
0x18008f76b  mov     r9, [rbp+Src]
0x18008f76f  mov     [r11-78h], rdx
0x18008f773  call    McTemplateU0zzzqqq_EtwEventWriteTransfer
0x18008f778  call    ?ThreadSelf@@YAPEAVTHREAD@@XZ; ThreadSelf(void)
0x18008f77d  test    rax, rax
0x18008f780  jz      loc_18008FB19
0x18008f786  call    ?RpcpPurgeEEInfo@@YAXXZ; RpcpPurgeEEInfo(void)
0x18008f78b  cmp     cs:?g_fServerSideDebugInfoEnabled@@3HA, ebx; int g_fServerSideDebugInfoEnabled
0x18008f791  jz      short loc_18008F7A0
0x18008f793  call    ?InitializeServerSideCellHeapIfNecessary@@YAJXZ; InitializeServerSideCellHeapIfNecessary(void)
0x18008f798  test    eax, eax
0x18008f79a  jnz     loc_18008FB1E
0x18008f7a0  cmp     [rbp+arg_48], ebx
0x18008f7a6  jz      short loc_18008F7BB
0x18008f7a8  cmp     [rbp+arg_58], rbx
0x18008f7af  jz      short loc_18008F7BB
0x18008f7b1  mov     eax, 57h ; 'W'
0x18008f7b6  jmp     loc_18008FB1E
0x18008f7bb  lea     rdx, aNcalrpc; "ncalrpc"
0x18008f7c2  mov     rcx, r12; String1
0x18008f7c5  call    cs:__imp__wcsicmp
0x18008f7cc  nop     dword ptr [rax+rax+00h]
0x18008f7d1  mov     r13, [rbp+arg_50]
0x18008f7d8  test    eax, eax
0x18008f7da  jnz     short loc_18008F7F4
0x18008f7dc  mov     r14, rbx
0x18008f7df  call    ?LrpcCreateRpcAddress@@YAPEAVRPC_ADDRESS@@XZ; LrpcCreateRpcAddress(void)
0x18008f7e4  and     r15d, 0FFFFFFFBh
0x18008f7e8  mov     rdi, rax
0x18008f7eb  mov     [rbp+arg_30], r15d
0x18008f7ef  jmp     loc_18008FA80
0x18008f7f4  cmp     cs:?gfRPCVerifierEnabled@@3HA, ebx; int gfRPCVerifierEnabled
0x18008f7fa  jz      loc_18008F90A
0x18008f800  mov     rax, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x18008f807  cmp     [rax+84h], ebx
0x18008f80d  jnz     loc_18008F90A
0x18008f813  cmp     cs:?gfRemoteProtseqRegistered@@3HA, ebx; int gfRemoteProtseqRegistered
0x18008f819  jnz     loc_18008F90A
0x18008f81f  cmp     cs:?gfUnsecureInterfaceRegistered@@3HA, ebx; int gfUnsecureInterfaceRegistered
0x18008f825  jz      loc_18008F900
0x18008f82b  mov     r8d, 10h
0x18008f831  lea     rdx, aPossibleSecuri_0; "Possible security threat: Insecure inte"...
0x18008f838  lea     rcx, Format; "%s : type (0x%x)"
0x18008f83f  call    cs:__imp_DbgPrint
0x18008f846  nop     dword ptr [rax+rax+00h]
0x18008f84b  mov     r8, [rbp+Src]
0x18008f84f  lea     rcx, aRpcStartingToL; "RPC: Starting to listen on protseq: %S "...
0x18008f856  mov     rdx, r12
0x18008f859  call    cs:__imp_DbgPrint
0x18008f860  nop     dword ptr [rax+rax+00h]
0x18008f865  mov     rcx, rsi; CriticalSection
0x18008f868  call    cs:__imp_RtlEnterCriticalSection
0x18008f86f  nop     dword ptr [rax+rax+00h]
0x18008f874  mov     dword ptr [rbp+arg_40], ebx
0x18008f87a  lea     r14, [rsi+120h]
0x18008f881  jmp     short loc_18008F8DA
0x18008f883  mov     rcx, rdx; this
0x18008f886  call    ?IsSecure@RPC_INTERFACE@@QEAAHXZ; RPC_INTERFACE::IsSecure(void)
0x18008f88b  test    eax, eax
0x18008f88d  jnz     short loc_18008F8DA
0x18008f88f  mov     ecx, [rdx+8]
0x18008f892  test    cl, 2
0x18008f895  jnz     short loc_18008F8DA
0x18008f897  lea     rbx, [rdx+54h]
0x18008f89b  mov     rcx, rbx; struct _GUID *
0x18008f89e  lea     edx, [rax+1]; unsigned int
0x18008f8a1  call    ?IsInterfaceExempt@@YAHPEAU_GUID@@K@Z; IsInterfaceExempt(_GUID *,ulong)
0x18008f8a6  test    eax, eax
0x18008f8a8  jnz     short loc_18008F8D8
0x18008f8aa  lea     rcx, aRpcInsecureInt; "RPC: Insecure interface UUID: "
0x18008f8b1  call    cs:__imp_DbgPrint
0x18008f8b8  nop     dword ptr [rax+rax+00h]
0x18008f8bd  mov     rcx, rbx; struct _GUID *
0x18008f8c0  call    ?DbgPrintUUID@@YAXPEAU_GUID@@@Z; DbgPrintUUID(_GUID *)
0x18008f8c5  lea     rcx, asc_1800E9378; "\n"
0x18008f8cc  call    cs:__imp_DbgPrint
0x18008f8d3  nop     dword ptr [rax+rax+00h]
0x18008f8d8  xor     ebx, ebx
0x18008f8da  lea     rdx, [rbp+arg_40]; unsigned int *
0x18008f8e1  mov     rcx, r14; this
0x18008f8e4  call    ?Next@SIMPLE_DICT@@QEAAPEAXAEAI@Z; SIMPLE_DICT::Next(uint &)
0x18008f8e9  mov     rdx, rax
0x18008f8ec  test    rax, rax
0x18008f8ef  jnz     short loc_18008F883
0x18008f8f1  mov     rcx, rsi; CriticalSection
0x18008f8f4  call    cs:__imp_RtlLeaveCriticalSection
0x18008f8fb  nop     dword ptr [rax+rax+00h]
0x18008f900  mov     cs:?gfRemoteProtseqRegistered@@3HA, 1; int gfRemoteProtseqRegistered
0x18008f90a  lea     rcx, ?GlobalMutex@@3PADA; CriticalSection
0x18008f911  call    cs:__imp_RtlEnterCriticalSection
0x18008f918  nop     dword ptr [rax+rax+00h]
0x18008f91d  call    DoFirewallInit
0x18008f922  test    eax, eax
0x18008f924  jz      loc_18008FF90
0x18008f92a  call    GetFirewallTableCopy
0x18008f92f  cmp     cs:pFirewallTable, rbx
0x18008f936  mov     r14, rax
0x18008f939  jz      short loc_18008F944
0x18008f93b  test    rax, rax
0x18008f93e  jz      loc_18008FF90
0x18008f944  call    ?LoadFirewallExtensionIfNecessary@@YAJXZ; LoadFirewallExtensionIfNecessary(void)
0x18008f949  mov     ebx, eax
0x18008f94b  test    eax, eax
0x18008f94d  jz      short loc_18008F95A
0x18008f94f  cmp     eax, 6E4h
0x18008f954  jnz     loc_18008FF95
0x18008f95a  lea     rcx, ?GlobalMutex@@3PADA; CriticalSection
0x18008f961  call    cs:__imp_RtlLeaveCriticalSection
0x18008f968  nop     dword ptr [rax+rax+00h]
0x18008f96d  test    rdi, rdi
0x18008f970  jnz     loc_18008F9F7
0x18008f976  test    r14, r14
0x18008f979  jz      short loc_18008F9F7
0x18008f97b  cmp     [rbp+arg_38], 1
0x18008f97f  jnz     short loc_18008F9F7
0x18008f981  cmp     cs:?gfRPCVerifierEnabled@@3HA, edi; int gfRPCVerifierEnabled
0x18008f987  jz      short loc_18008F9E7
0x18008f989  mov     rax, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x18008f990  cmp     [rax+84h], edi
0x18008f996  jnz     short loc_18008F9E7
0x18008f998  lea     r8d, [rdi+20h]
0x18008f99c  lea     rdx, aPossibleSecuri; "Possible security threat: Server is for"...
0x18008f9a3  lea     rcx, Format; "%s : type (0x%x)"
0x18008f9aa  call    cs:__imp_DbgPrint
0x18008f9b1  nop     dword ptr [rax+rax+00h]
0x18008f9b6  lea     rcx, aRpcOffendingSt; "RPC: Offending Stack:\n"
0x18008f9bd  call    cs:__imp_DbgPrint
0x18008f9c4  nop     dword ptr [rax+rax+00h]
0x18008f9c9  lea     edx, [rdi+4]; FramesToCapture
0x18008f9cc  lea     ecx, [rdi+2]; FramesToSkip
0x18008f9cf  call    ?PrintCurrentStackTrace@@YAXII@Z; PrintCurrentStackTrace(uint,uint)
0x18008f9d4  lea     rcx, aRpcToDetermine_0; "RPC: To determine the symbolic stack, d"...
0x18008f9db  call    cs:__imp_DbgPrint
0x18008f9e2  nop     dword ptr [rax+rax+00h]
0x18008f9e7  call    ?IsCurrentUserAdmin@@YAJXZ; IsCurrentUserAdmin(void)
0x18008f9ec  test    eax, eax
0x18008f9ee  jz      short loc_18008F9F7
0x18008f9f0  mov     ebx, 5
0x18008f9f5  jmp     short loc_18008FA54
0x18008f9f7  mov     r8d, 6; MaxCount
0x18008f9fd  lea     rcx, aNcacn; "ncacn_"
0x18008fa04  mov     rdx, r12; String2
0x18008fa07  call    cs:__imp__wcsnicmp
0x18008fa0e  nop     dword ptr [rax+rax+00h]
0x18008fa13  test    eax, eax
0x18008fa15  jnz     loc_18008FF7E
0x18008fa1b  mov     rdx, r12; String2
0x18008fa1e  lea     rcx, aNcacnHttp; "ncacn_http"
0x18008fa25  call    cs:__imp__wcsicmp
0x18008fa2c  nop     dword ptr [rax+rax+00h]
0x18008fa31  test    eax, eax
0x18008fa33  jz      short loc_18008FA42
0x18008fa35  test    r15b, 8
0x18008fa39  jz      short loc_18008FA42
0x18008fa3b  mov     ebx, 57h ; 'W'
0x18008fa40  jmp     short loc_18008FA54
0x18008fa42  lea     rdx, [rbp+var_8]; struct TRANS_INFO **
0x18008fa46  mov     rcx, r12; unsigned __int16 *
0x18008fa49  call    ?LoadableTransportInfo@@YAJPEAGPEAPEAVTRANS_INFO@@@Z; LoadableTransportInfo(ushort *,TRANS_INFO * *)
0x18008fa4e  mov     ebx, eax
0x18008fa50  test    eax, eax
0x18008fa52  jz      short loc_18008FA61
0x18008fa54  mov     rcx, r14; lpMem
0x18008fa57  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18008fa5c  jmp     loc_18008FFA8
0x18008fa61  mov     rcx, [rbp+var_8]; struct TRANS_INFO *
0x18008fa65  call    ?OsfCreateRpcAddress@@YAPEAVRPC_ADDRESS@@PEAVTRANS_INFO@@@Z; OsfCreateRpcAddress(TRANS_INFO *)
0x18008fa6a  xor     ebx, ebx
0x18008fa6c  mov     rdi, rax
0x18008fa6f  test    rax, rax
0x18008fa72  jz      short loc_18008FA80
0x18008fa74  test    r13, r13
0x18008fa77  jz      short loc_18008FA80
0x18008fa79  mov     dword ptr [rax+3Ch], 1
0x18008fa80  mov     rcx, r14; lpMem
0x18008fa83  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18008fa88  test    rdi, rdi
0x18008fa8b  jz      loc_18008FB19
0x18008fa91  lea     r15, [rsi+48h]
0x18008fa95  mov     dword ptr [rbp+arg_40], ebx
0x18008fa9b  mov     rcx, rsi; CriticalSection
0x18008fa9e  cmp     [rbp+Src], rbx
0x18008faa2  jz      loc_18008FB8D
0x18008faa8  call    cs:__imp_RtlEnterCriticalSection
0x18008faaf  nop     dword ptr [rax+rax+00h]
0x18008fab4  jmp     short loc_18008FACD
0x18008fab6  mov     r9, [rbp+Src]; unsigned __int16 *
0x18008faba  mov     r8, r12; unsigned __int16 *
0x18008fabd  mov     rdx, [rbp+arg_8]; unsigned __int16 *
0x18008fac1  mov     rcx, rbx; this
0x18008fac4  call    ?SameEndpointAndProtocolSequence@RPC_ADDRESS@@QEAAHPEAG00@Z; RPC_ADDRESS::SameEndpointAndProtocolSequence(ushort *,ushort *,ushort *)
0x18008fac9  test    eax, eax
0x18008facb  jnz     short loc_18008FB37
0x18008facd  lea     rdx, [rbp+arg_40]; unsigned int *
0x18008fad4  mov     rcx, r15; this
0x18008fad7  call    ?Next@SIMPLE_DICT@@QEAAPEAXAEAI@Z; SIMPLE_DICT::Next(uint &)
0x18008fadc  mov     rbx, rax
0x18008fadf  test    rax, rax
0x18008fae2  jnz     short loc_18008FAB6
0x18008fae4  mov     rcx, rsi; CriticalSection
0x18008fae7  call    cs:__imp_RtlLeaveCriticalSection
0x18008faee  nop     dword ptr [rax+rax+00h]
0x18008faf3  mov     rcx, [rbp+Src]; Src
0x18008faf7  call    ?DuplicateString@@YAPEAGPEBG@Z; DuplicateString(ushort const *)
0x18008fafc  mov     [rbp+Src], rax
0x18008fb00  test    rax, rax
0x18008fb03  jnz     short loc_18008FB82
0x18008fb05  mov     rcx, rdi
0x18008fb08  mov     rax, [rdi]
0x18008fb0b  mov     edx, 1
0x18008fb10  mov     rax, [rax+8]
0x18008fb14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fb19  mov     eax, 0Eh
0x18008fb1e  mov     rbx, [rsp+60h+arg_0]
0x18008fb26  add     rsp, 60h
0x18008fb2a  pop     r15
0x18008fb2c  pop     r14
0x18008fb2e  pop     r13
0x18008fb30  pop     r12
0x18008fb32  pop     rdi
0x18008fb33  pop     rsi
0x18008fb34  pop     rbp
0x18008fb35  retn
0x18008fb37  mov     rcx, rsi; CriticalSection
0x18008fb3a  call    cs:__imp_RtlLeaveCriticalSection
0x18008fb41  nop     dword ptr [rax+rax+00h]
0x18008fb46  mov     rax, [rdi]
0x18008fb49  mov     edx, 1
0x18008fb4e  mov     rcx, rdi
0x18008fb51  mov     rax, [rax+8]
0x18008fb55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fb5a  cmp     [rbp+arg_48], 0
0x18008fb61  jz      short loc_18008FB7B
0x18008fb63  test    r13, r13
0x18008fb66  jz      short loc_18008FB77
0x18008fb68  mov     rdx, r13; struct MTMLinkSymmetric *
0x18008fb6b  mov     rcx, rbx; this
0x18008fb6e  call    ?LinkToInterfaceIfNecessary@RPC_ADDRESS@@QEAAHPEAVMTMLinkSymmetric@@@Z; RPC_ADDRESS::LinkToInterfaceIfNecessary(MTMLinkSymmetric *)
0x18008fb73  test    eax, eax
0x18008fb75  jz      short loc_18008FB19
0x18008fb77  xor     eax, eax
0x18008fb79  jmp     short loc_18008FB1E
0x18008fb7b  mov     eax, 6CCh
0x18008fb80  jmp     short loc_18008FB1E
0x18008fb82  mov     r14d, 1
0x18008fb88  jmp     loc_18008FC2B
0x18008fb8d  call    cs:__imp_RtlEnterCriticalSection
0x18008fb94  nop     dword ptr [rax+rax+00h]
0x18008fb99  lea     rdx, [rbp+arg_40]; unsigned int *
0x18008fba0  mov     rcx, r15; this
0x18008fba3  call    ?Next@SIMPLE_DICT@@QEAAPEAXAEAI@Z; SIMPLE_DICT::Next(uint &)
0x18008fba8  mov     rbx, rax
0x18008fbab  test    rax, rax
0x18008fbae  jz      short loc_18008FC19
0x18008fbb0  mov     r9, [rbp+arg_28]; struct _SECURITY_DESCRIPTOR *
0x18008fbb4  lea     rax, [rbp+var_10]
0x18008fbb8  mov     rdx, [rbp+arg_8]; unsigned __int16 *
0x18008fbbc  mov     r8, r12; unsigned __int16 *
0x18008fbbf  mov     [rsp+60h+var_28], rax; int *
0x18008fbc4  mov     rcx, rbx; this
0x18008fbc7  mov     eax, [rbp+arg_18]
0x18008fbca  mov     dword ptr [rsp+60h+var_30], eax; unsigned int
0x18008fbce  mov     rax, [rbp+arg_58]
0x18008fbd5  mov     [rsp+60h+var_38], rax; struct RPCP_INTERFACE_GROUP *
0x18008fbda  mov     eax, [rbp+arg_30]
0x18008fbdd  mov     [rsp+60h+var_40], eax; unsigned int
0x18008fbe1  call    ?EquivalentDynamicEndpoint@RPC_ADDRESS@@QEAAJPEAG0PEAU_SECURITY_DESCRIPTOR@@KPEAVRPCP_INTERFACE_GROUP@@IPEAH@Z; RPC_ADDRESS::EquivalentDynamicEndpoint(ushort *,ushort *,_SECURITY_DESCRIPTOR *,ulong,RPCP_INTERFACE_GROUP *,uint,int *)
0x18008fbe6  mov     r12d, [rbp+var_10]
0x18008fbea  mov     r14d, eax
0x18008fbed  test    eax, eax
0x18008fbef  jnz     loc_18008FC9F
0x18008fbf5  test    r12d, r12d
0x18008fbf8  jnz     loc_18008FC9F
  ... truncated ...
```
