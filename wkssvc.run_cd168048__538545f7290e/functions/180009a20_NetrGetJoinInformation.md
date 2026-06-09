# NetrGetJoinInformation

- ea: `0x180009a20`
- end: `0x18000a1ae`
- name: `NetrGetJoinInformation`
- size: `1934`
- prototype: `__int64 __fastcall(PCWSTR SourceString, LPVOID *Buffer)`
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180009a20`
- `0x180031878`
- `0x180036191`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180009ab7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180009ad2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180009aed`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180009ab7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180009ad2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180009aed`
- `ntdll!RtlNtStatusToDosError` at `0x180009fef`
- `ntdll!RtlNtStatusToDosError` at `0x180009fef`
- `ntdll!RtlAdjustPrivilege` at `0x180009bc4`
- `ntdll!RtlAdjustPrivilege` at `0x180009bc4`
- `ntdll!NtAccessCheckAndAuditAlarm` at `0x180009c2d`
- `ntdll!NtAccessCheckAndAuditAlarm` at `0x180009c2d`
- `ntdll!RtlInitUnicodeString` at `0x180009b7c`
- `ntdll!RtlInitUnicodeString` at `0x180009b93`
- `ntdll!RtlInitUnicodeString` at `0x180009baa`
- `ntdll!RtlInitUnicodeString` at `0x180009e0e`
- `ntdll!RtlInitUnicodeString` at `0x180009b7c`
- `ntdll!RtlInitUnicodeString` at `0x180009b93`
- `ntdll!RtlInitUnicodeString` at `0x180009baa`
- `ntdll!RtlInitUnicodeString` at `0x180009e0e`
- `RPCRT4!RpcStringFreeW` at `0x180009b08`
- `RPCRT4!RpcStringFreeW` at `0x180009b1e`
- `RPCRT4!RpcStringFreeW` at `0x180009b08`
- `RPCRT4!RpcStringFreeW` at `0x180009b1e`
- `RPCRT4!RpcStringBindingParseW` at `0x180009a9a`
- `RPCRT4!RpcStringBindingParseW` at `0x180009a9a`
- `RPCRT4!RpcImpersonateClient` at `0x180009bd2`
- `RPCRT4!RpcImpersonateClient` at `0x180009c67`
- `RPCRT4!RpcImpersonateClient` at `0x180009bd2`
- `RPCRT4!RpcImpersonateClient` at `0x180009c67`
- `RPCRT4!RpcBindingServerFromClient` at `0x180009a53`
- `RPCRT4!RpcBindingServerFromClient` at `0x180009a53`
- `RPCRT4!RpcBindingFree` at `0x180009b34`
- `RPCRT4!RpcBindingFree` at `0x180009b34`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180009a71`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180009a71`
- `RPCRT4!RpcRevertToSelf` at `0x180009c3b`
- `RPCRT4!RpcRevertToSelf` at `0x180009d7f`
- `RPCRT4!RpcRevertToSelf` at `0x180009c3b`
- `RPCRT4!RpcRevertToSelf` at `0x180009d7f`
- `netutils!NetApiBufferAllocate` at `0x180009db2`
- `netutils!NetApiBufferAllocate` at `0x180009db2`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180009cd6`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180009cd6`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180009cf5`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180009cf5`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180009d07`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180009d07`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180009d73`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180009d73`

## pseudocode

```c
__int64 __fastcall NetrGetJoinInformation(PCWSTR SourceString, LPVOID *Buffer, _DWORD *a3)
{
  DWORD v6; // ebx
  PSECURITY_DESCRIPTOR v7; // rbx
  NTSTATUS v8; // ebx
  RPC_STATUS v9; // eax
  int v10; // r8d
  struct _UNICODE_STRING *p_DestinationString; // rcx
  int InformationPolicy; // esi
  RPC_WSTR v13; // rdx
  unsigned __int16 v14; // cx
  unsigned int v15; // eax
  int v16; // eax
  RPC_STATUS v17; // eax
  int v18; // r8d
  const void *v20; // r14
  unsigned int v21; // esi
  ULONG v22; // eax
  unsigned __int8 GenerateOnClose[8]; // [rsp+60h] [rbp-59h] BYREF
  RPC_WSTR StringBinding; // [rsp+68h] [rbp-51h] BYREF
  RPC_BINDING_HANDLE ServerBinding; // [rsp+70h] [rbp-49h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-41h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-31h] BYREF
  struct _UNICODE_STRING ObjectName; // [rsp+B8h] [rbp-1h] BYREF
  struct _UNICODE_STRING ObjectTypeName; // [rsp+C8h] [rbp+Fh] BYREF
  RPC_WSTR Protseq; // [rsp+138h] [rbp+7Fh] BYREF

  ServerBinding = 0;
  StringBinding = 0;
  Protseq = 0;
  v6 = RpcBindingServerFromClient(0, &ServerBinding);
  if ( !v6 )
  {
    v6 = RpcBindingToStringBindingW(ServerBinding, &StringBinding);
    if ( !v6 )
    {
      v6 = RpcStringBindingParseW(StringBinding, 0, &Protseq, 0, 0, 0);
      if ( !v6 && (unsigned int)_o__wcsicmp(L"ncacn_nb_tcp", Protseq) && (unsigned int)_o__wcsicmp(L"ncacn_np", Protseq) )
      {
        _o__wcsicmp(L"ncalrpc", Protseq);
        v6 = 1703;
      }
    }
  }
  if ( StringBinding )
    RpcStringFreeW(&StringBinding);
  if ( Protseq )
    RpcStringFreeW(&Protseq);
  if ( ServerBinding )
    RpcBindingFree(&ServerBinding);
  if ( v6 )
    return v6;
  v7 = NetApiSd;
  LOBYTE(Protseq) = 0;
  LODWORD(StringBinding) = 0;
  GenerateOnClose[0] = 0;
  DestinationString = 0;
  LODWORD(ServerBinding) = 0;
  ObjectTypeName = 0;
  ObjectName = 0;
  RtlInitUnicodeString(&DestinationString, L"Workstation");
  RtlInitUnicodeString(&ObjectTypeName, L"NetAPI");
  RtlInitUnicodeString(&ObjectName, L"-");
  RtlAdjustPrivilege(0x15u, 1u, 0, (PBOOLEAN)&Protseq);
  if ( RpcImpersonateClient(0) )
    return 5;
  v8 = NtAccessCheckAndAuditAlarm(
         &DestinationString,
         0,
         &ObjectTypeName,
         &ObjectName,
         v7,
         2u,
         &WsNetApiMapping,
         0,
         (PACCESS_MASK)&StringBinding,
         (PNTSTATUS)&ServerBinding,
         GenerateOnClose);
  RpcRevertToSelf();
  if ( v8 < 0 || (_DWORD)ServerBinding )
    return 5;
  if ( Buffer )
  {
    *Buffer = 0;
    v9 = RpcImpersonateClient(0);
    if ( v9 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_sdL(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v10, (unsigned int)"unknown", 0, v9);
      }
      return 5;
    }
    Protseq = 0;
    StringBinding = 0;
    DestinationString = 0;
    memset(&ObjectAttributes, 0, 44);
    if ( a3 )
    {
      p_DestinationString = 0;
      if ( SourceString )
      {
        RtlInitUnicodeString(&DestinationString, SourceString);
        p_DestinationString = &DestinationString;
      }
      ObjectAttributes.Length = 48;
      memset(&ObjectAttributes.RootDirectory, 0, 20);
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      InformationPolicy = LsaOpenPolicy(
                            (PLSA_UNICODE_STRING)p_DestinationString,
                            &ObjectAttributes,
                            0x2000000u,
                            (PLSA_HANDLE)&Protseq);
      if ( InformationPolicy >= 0 )
      {
        InformationPolicy = LsaQueryInformationPolicy(Protseq, PolicyDnsDomainInformation, (PVOID *)&StringBinding);
        LsaClose(Protseq);
        Protseq = 0;
      }
      if ( !InformationPolicy || InformationPolicy == -2147483611 )
      {
        v6 = 0;
        goto LABEL_27;
      }
      if ( InformationPolicy <= -1073741531 )
      {
        if ( InformationPolicy != -1073741531 )
        {
          switch ( InformationPolicy )
          {
            case -1073741789:
              v6 = 2123;
              break;
            case -1073741727:
              v6 = 5;
              break;
            case -1073741726:
              v6 = 2202;
              break;
            case -1073741725:
              v6 = 2224;
              break;
            case -1073741724:
              v6 = 2221;
              break;
            case -1073741723:
              v6 = 2223;
              break;
            case -1073741722:
            case -1073741709:
              v6 = 2220;
              break;
            case -1073741721:
              v6 = 2236;
              break;
            case -1073741720:
              v6 = 2237;
              break;
            case -1073741716:
              v6 = 2245;
              break;
            case -1073741713:
              v6 = 2241;
              break;
            case -1073741712:
              v6 = 2240;
              break;
            case -1073741711:
              v6 = 2242;
              break;
            case -1073741604:
            case -1073741602:
              goto LABEL_90;
            case -1073741603:
              v6 = 2227;
              break;
            case -1073741596:
              v6 = 2247;
              break;
            case -1073741573:
              v6 = 2102;
              break;
            case -1073741561:
              v6 = 2401;
              break;
            case -1073741560:
              v6 = 2404;
              break;
            default:
              goto LABEL_87;
          }
          goto LABEL_35;
        }
        goto LABEL_81;
      }
      if ( InformationPolicy > -1073741495 )
      {
        switch ( InformationPolicy )
        {
          case -1073741433:
LABEL_90:
            v6 = 2226;
            goto LABEL_35;
          case -1073741421:
            v6 = 2239;
            goto LABEL_35;
          case -1073741261:
            v6 = 2453;
            goto LABEL_35;
        }
      }
      else
      {
        switch ( InformationPolicy )
        {
          case -1073741495:
            v6 = 2403;
            goto LABEL_35;
          case -1073741529:
LABEL_81:
            v6 = 2234;
            goto LABEL_35;
          case -1073741518:
            v6 = 2210;
            goto LABEL_35;
          case -1073741517:
            v6 = 2457;
            goto LABEL_35;
          case -1073741516:
            v6 = 2249;
            goto LABEL_35;
        }
      }
LABEL_87:
      v22 = RtlNtStatusToDosError(InformationPolicy);
      v6 = v22;
      if ( v22 == InformationPolicy )
      {
        v6 = 2140;
      }
      else if ( !v22 )
      {
LABEL_27:
        v13 = StringBinding;
        if ( *((_QWORD *)StringBinding + 8) )
        {
          if ( !*StringBinding )
          {
            *a3 = 1;
            goto LABEL_33;
          }
          *a3 = 3;
        }
        else
        {
          v14 = *StringBinding;
          *a3 = (*StringBinding != 0) + 1;
          if ( !v14 )
            goto LABEL_33;
        }
        v15 = *v13;
        if ( (_WORD)v15 )
        {
          v16 = (v15 >> 1) + 1;
          if ( v16 )
          {
            v20 = (const void *)*((_QWORD *)v13 + 1);
            v21 = 2 * v16;
            v6 = NetApiBufferAllocate(2 * v16, Buffer);
            if ( !v6 )
              memcpy_0(*Buffer, v20, v21);
            v13 = StringBinding;
          }
          else
          {
            v6 = 534;
          }
          goto LABEL_34;
        }
LABEL_33:
        *Buffer = 0;
LABEL_34:
        LsaFreeMemory(v13);
      }
    }
    else
    {
      v6 = 87;
    }
LABEL_35:
    v17 = RpcRevertToSelf();
    if ( v17 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
          WPP_SF_sdL(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v18, (unsigned int)"unknown", 0, v17);
      }
      __fastfail(7u);
    }
    return v6;
  }
  return 87;
}

```

## disassembly

```asm
0x180009a20  push    rbp
0x180009a22  push    rbx
0x180009a23  push    rsi
0x180009a24  push    rdi
0x180009a25  push    r14
0x180009a27  push    r15
0x180009a29  lea     rbp, [rsp-2Fh]
0x180009a2e  sub     rsp, 0E8h
0x180009a35  xor     r15d, r15d
0x180009a38  mov     rdi, rdx
0x180009a3b  mov     rsi, rcx
0x180009a3e  mov     [rbp+57h+ServerBinding], r15
0x180009a42  lea     rdx, [rbp+57h+ServerBinding]; ServerBinding
0x180009a46  mov     [rbp+57h+StringBinding], r15
0x180009a4a  xor     ecx, ecx; ClientBinding
0x180009a4c  mov     [rbp+57h+Protseq], r15
0x180009a50  mov     r14, r8
0x180009a53  call    cs:__imp_RpcBindingServerFromClient
0x180009a5a  nop     dword ptr [rax+rax+00h]
0x180009a5f  mov     ebx, eax
0x180009a61  test    eax, eax
0x180009a63  jnz     loc_180009AFE
0x180009a69  mov     rcx, [rbp+57h+ServerBinding]; Binding
0x180009a6d  lea     rdx, [rbp+57h+StringBinding]; StringBinding
0x180009a71  call    cs:__imp_RpcBindingToStringBindingW
0x180009a78  nop     dword ptr [rax+rax+00h]
0x180009a7d  mov     ebx, eax
0x180009a7f  test    eax, eax
0x180009a81  jnz     short loc_180009AFE
0x180009a83  mov     rcx, [rbp+57h+StringBinding]; StringBinding
0x180009a87  lea     r8, [rbp+57h+Protseq]; Protseq
0x180009a8b  mov     [rsp+110h+NetworkOptions], r15; NetworkOptions
0x180009a90  xor     r9d, r9d; NetworkAddr
0x180009a93  xor     edx, edx; ObjUuid
0x180009a95  mov     [rsp+110h+Endpoint], r15; Endpoint
0x180009a9a  call    cs:__imp_RpcStringBindingParseW
0x180009aa1  nop     dword ptr [rax+rax+00h]
0x180009aa6  mov     ebx, eax
0x180009aa8  test    eax, eax
0x180009aaa  jnz     short loc_180009AFE
0x180009aac  mov     rdx, [rbp+57h+Protseq]
0x180009ab0  lea     rcx, aNcacnNbTcp; "ncacn_nb_tcp"
0x180009ab7  call    cs:__imp__o__wcsicmp
0x180009abe  nop     dword ptr [rax+rax+00h]
0x180009ac3  test    eax, eax
0x180009ac5  jz      short loc_180009AFE
0x180009ac7  mov     rdx, [rbp+57h+Protseq]
0x180009acb  lea     rcx, Protseq; "ncacn_np"
0x180009ad2  call    cs:__imp__o__wcsicmp
0x180009ad9  nop     dword ptr [rax+rax+00h]
0x180009ade  test    eax, eax
0x180009ae0  jz      short loc_180009AFE
0x180009ae2  mov     rdx, [rbp+57h+Protseq]
0x180009ae6  lea     rcx, String2; "ncalrpc"
0x180009aed  call    cs:__imp__o__wcsicmp
0x180009af4  nop     dword ptr [rax+rax+00h]
0x180009af9  mov     ebx, 6A7h
0x180009afe  cmp     [rbp+57h+StringBinding], r15
0x180009b02  jz      short loc_180009B14
0x180009b04  lea     rcx, [rbp+57h+StringBinding]; String
0x180009b08  call    cs:__imp_RpcStringFreeW
0x180009b0f  nop     dword ptr [rax+rax+00h]
0x180009b14  cmp     [rbp+57h+Protseq], r15
0x180009b18  jz      short loc_180009B2A
0x180009b1a  lea     rcx, [rbp+57h+Protseq]; String
0x180009b1e  call    cs:__imp_RpcStringFreeW
0x180009b25  nop     dword ptr [rax+rax+00h]
0x180009b2a  cmp     [rbp+57h+ServerBinding], r15
0x180009b2e  jz      short loc_180009B40
0x180009b30  lea     rcx, [rbp+57h+ServerBinding]; Binding
0x180009b34  call    cs:__imp_RpcBindingFree
0x180009b3b  nop     dword ptr [rax+rax+00h]
0x180009b40  test    ebx, ebx
0x180009b42  jnz     loc_180009D93
0x180009b48  mov     rbx, cs:NetApiSd
0x180009b4f  lea     rdx, SourceName; "Workstation"
0x180009b56  xorps   xmm0, xmm0
0x180009b59  mov     byte ptr [rbp+57h+Protseq], r15b
0x180009b5d  xorps   xmm1, xmm1
0x180009b60  mov     dword ptr [rbp+57h+StringBinding], r15d
0x180009b64  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180009b68  mov     [rbp+57h+var_B0], r15b
0x180009b6c  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180009b70  mov     dword ptr [rbp+57h+ServerBinding], r15d
0x180009b74  movups  xmmword ptr [rbp+57h+ObjectTypeName.Length], xmm1
0x180009b78  movups  xmmword ptr [rbp+57h+ObjectName.Length], xmm0
0x180009b7c  call    cs:__imp_RtlInitUnicodeString
0x180009b83  nop     dword ptr [rax+rax+00h]
0x180009b88  lea     rdx, aNetapi; "NetAPI"
0x180009b8f  lea     rcx, [rbp+57h+ObjectTypeName]; DestinationString
0x180009b93  call    cs:__imp_RtlInitUnicodeString
0x180009b9a  nop     dword ptr [rax+rax+00h]
0x180009b9f  lea     rdx, asc_18003DB90; "-"
0x180009ba6  lea     rcx, [rbp+57h+ObjectName]; DestinationString
0x180009baa  call    cs:__imp_RtlInitUnicodeString
0x180009bb1  nop     dword ptr [rax+rax+00h]
0x180009bb6  lea     r9, [rbp+57h+Protseq]; OldValue
0x180009bba  xor     r8d, r8d; ForThread
0x180009bbd  mov     dl, 1; NewValue
0x180009bbf  mov     ecx, 15h; Privilege
0x180009bc4  call    cs:__imp_RtlAdjustPrivilege
0x180009bcb  nop     dword ptr [rax+rax+00h]
0x180009bd0  xor     ecx, ecx; BindingHandle
0x180009bd2  call    cs:__imp_RpcImpersonateClient
0x180009bd9  nop     dword ptr [rax+rax+00h]
0x180009bde  test    eax, eax
0x180009be0  jnz     loc_180009E00
0x180009be6  lea     rax, [rbp+57h+var_B0]
0x180009bea  xor     edx, edx; HandleId
0x180009bec  mov     [rsp+110h+GenerateOnClose], rax; GenerateOnClose
0x180009bf1  lea     r9, [rbp+57h+ObjectName]; ObjectName
0x180009bf5  lea     rax, [rbp+57h+ServerBinding]
0x180009bf9  mov     [rsp+110h+AccessStatus], rax; AccessStatus
0x180009bfe  lea     r8, [rbp+57h+ObjectTypeName]; ObjectTypeName
0x180009c02  lea     rax, [rbp+57h+StringBinding]
0x180009c06  mov     [rsp+110h+GrantedAccess], rax; GrantedAccess
0x180009c0b  lea     rcx, [rbp+57h+DestinationString]; SubsystemName
0x180009c0f  mov     [rsp+110h+ObjectCreation], r15b; ObjectCreation
0x180009c14  lea     rax, WsNetApiMapping
0x180009c1b  mov     [rsp+110h+GenericMapping], rax; GenericMapping
0x180009c20  mov     dword ptr [rsp+110h+NetworkOptions], 2; DesiredAccess
0x180009c28  mov     [rsp+110h+Endpoint], rbx; SecurityDescriptor
0x180009c2d  call    cs:__imp_NtAccessCheckAndAuditAlarm
0x180009c34  nop     dword ptr [rax+rax+00h]
0x180009c39  mov     ebx, eax
0x180009c3b  call    cs:__imp_RpcRevertToSelf
0x180009c42  nop     dword ptr [rax+rax+00h]
0x180009c47  test    ebx, ebx
0x180009c49  js      loc_180009E00
0x180009c4f  cmp     dword ptr [rbp+57h+ServerBinding], r15d
0x180009c53  jnz     loc_180009E00
0x180009c59  test    rdi, rdi
0x180009c5c  jz      loc_180009DEA
0x180009c62  xor     ecx, ecx; BindingHandle
0x180009c64  mov     [rdi], r15
0x180009c67  call    cs:__imp_RpcImpersonateClient
0x180009c6e  nop     dword ptr [rax+rax+00h]
0x180009c73  test    eax, eax
0x180009c75  jnz     loc_180009E30
0x180009c7b  xorps   xmm0, xmm0
0x180009c7e  mov     [rbp+57h+Protseq], r15
0x180009c82  xor     eax, eax
0x180009c84  mov     [rbp+57h+StringBinding], r15
0x180009c88  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180009c8c  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180009c90  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180009c94  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180009c98  test    r14, r14
0x180009c9b  jz      loc_18000A023
0x180009ca1  mov     rcx, r15; SystemName
0x180009ca4  test    rsi, rsi
0x180009ca7  jnz     loc_180009E07
0x180009cad  xorps   xmm0, xmm0
0x180009cb0  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180009cb7  lea     r9, [rbp+57h+Protseq]; PolicyHandle
0x180009cbb  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x180009cbf  mov     r8d, 2000000h; DesiredAccess
0x180009cc5  mov     [rbp+57h+ObjectAttributes.Attributes], r15d
0x180009cc9  lea     rdx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180009ccd  mov     [rbp+57h+ObjectAttributes.ObjectName], r15
0x180009cd1  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180009cd6  call    cs:__imp_LsaOpenPolicy
0x180009cdd  nop     dword ptr [rax+rax+00h]
0x180009ce2  mov     esi, eax
0x180009ce4  test    eax, eax
0x180009ce6  js      short loc_180009D17
0x180009ce8  mov     rcx, [rbp+57h+Protseq]; PolicyHandle
0x180009cec  lea     r8, [rbp+57h+StringBinding]; Buffer
0x180009cf0  mov     edx, 0Ch; InformationClass
0x180009cf5  call    cs:__imp_LsaQueryInformationPolicy
0x180009cfc  nop     dword ptr [rax+rax+00h]
0x180009d01  mov     rcx, [rbp+57h+Protseq]; ObjectHandle
0x180009d05  mov     esi, eax
0x180009d07  call    cs:__imp_LsaClose
0x180009d0e  nop     dword ptr [rax+rax+00h]
0x180009d13  mov     [rbp+57h+Protseq], r15
0x180009d17  test    esi, esi
0x180009d19  jz      short loc_180009D27
0x180009d1b  cmp     esi, 80000025h
0x180009d21  jnz     loc_180009E77
0x180009d27  mov     ebx, r15d
0x180009d2a  mov     rdx, [rbp+57h+StringBinding]
0x180009d2e  cmp     [rdx+40h], r15
0x180009d32  jnz     loc_180009DD8
0x180009d38  movzx   ecx, word ptr [rdx]
0x180009d3b  mov     eax, r15d
0x180009d3e  test    cx, cx
0x180009d41  setnz   al
0x180009d44  inc     eax
0x180009d46  mov     [r14], eax
0x180009d49  test    cx, cx
0x180009d4c  jz      short loc_180009D6D
0x180009d4e  movzx   eax, word ptr [rdx]
0x180009d51  test    ax, ax
0x180009d54  jz      short loc_180009D6D
0x180009d56  shr     eax, 1
0x180009d58  inc     eax
0x180009d5a  cmp     eax, 1
0x180009d5d  jnb     short loc_180009DA6
0x180009d5f  mov     ebx, 216h
0x180009d64  jmp     short loc_180009D70
0x180009d66  mov     dword ptr [r14], 1
0x180009d6d  mov     [rdi], r15
0x180009d70  mov     rcx, rdx; Buffer
0x180009d73  call    cs:__imp_LsaFreeMemory
0x180009d7a  nop     dword ptr [rax+rax+00h]
0x180009d7f  call    cs:__imp_RpcRevertToSelf
0x180009d86  nop     dword ptr [rax+rax+00h]
0x180009d8b  test    eax, eax
0x180009d8d  jnz     loc_18000A02D
0x180009d93  mov     eax, ebx
0x180009d95  add     rsp, 0E8h
0x180009d9c  pop     r15
0x180009d9e  pop     r14
0x180009da0  pop     rdi
0x180009da1  pop     rsi
0x180009da2  pop     rbx
0x180009da3  pop     rbp
0x180009da4  retn
0x180009da6  mov     r14, [rdx+8]
0x180009daa  lea     esi, [rax+rax]
0x180009dad  mov     ecx, esi; ByteCount
0x180009daf  mov     rdx, rdi; Buffer
0x180009db2  call    cs:__imp_NetApiBufferAllocate
0x180009db9  nop     dword ptr [rax+rax+00h]
0x180009dbe  mov     ebx, eax
0x180009dc0  test    eax, eax
0x180009dc2  jnz     short loc_180009DD2
0x180009dc4  mov     rcx, [rdi]; void *
0x180009dc7  mov     rdx, r14; Src
0x180009dca  mov     r8d, esi; Size
0x180009dcd  call    memcpy_0
0x180009dd2  mov     rdx, [rbp+57h+StringBinding]
0x180009dd6  jmp     short loc_180009D70
0x180009dd8  cmp     [rdx], r15w
0x180009ddc  jz      short loc_180009D66
0x180009dde  mov     dword ptr [r14], 3
0x180009de5  jmp     loc_180009D4E
0x180009dea  mov     eax, 57h ; 'W'
0x180009def  add     rsp, 0E8h
0x180009df6  pop     r15
0x180009df8  pop     r14
0x180009dfa  pop     rdi
0x180009dfb  pop     rsi
0x180009dfc  pop     rbx
0x180009dfd  pop     rbp
0x180009dfe  retn
0x180009e00  mov     eax, 5
0x180009e05  jmp     short loc_180009D95
0x180009e07  mov     rdx, rsi; SourceString
0x180009e0a  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180009e0e  call    cs:__imp_RtlInitUnicodeString
0x180009e15  nop     dword ptr [rax+rax+00h]
0x180009e1a  lea     rcx, [rbp+57h+DestinationString]
0x180009e1e  jmp     loc_180009CAD
0x180009e23  test    eax, eax
0x180009e25  jz      loc_180009D2A
0x180009e2b  jmp     loc_180009D7F
0x180009e30  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180009e37  lea     rdx, WPP_GLOBAL_Control
0x180009e3e  cmp     rcx, rdx
0x180009e41  jz      short loc_180009E6D
0x180009e43  test    byte ptr [rcx+1Ch], 4
0x180009e47  jz      short loc_180009E6D
0x180009e49  cmp     byte ptr [rcx+19h], 1
0x180009e4d  jb      short loc_180009E6D
0x180009e4f  mov     rcx, [rcx+10h]
0x180009e53  lea     r9, aUnknown; "unknown"
0x180009e5a  mov     dword ptr [rsp+110h+NetworkOptions], eax
0x180009e5e  mov     edx, 0Ah
0x180009e63  mov     dword ptr [rsp+110h+Endpoint], r15d
0x180009e68  call    WPP_SF_sdL
0x180009e6d  mov     ebx, 5
0x180009e72  jmp     loc_180009D93
0x180009e77  cmp     esi, 0C0000125h
0x180009e7d  jg      loc_180009F6F
0x180009e83  jz      loc_180009FB7
0x180009e89  lea     eax, [rsi+3FFFFFDDh]; switch 230 cases
0x180009e8f  cmp     eax, 0E5h
0x180009e94  ja      def_180009EB5; jumptable 0000000180009EB5 default case, cases -1073741788--1073741728,-1073741719--1073741717,-1073741715,-1073741714,-1073741710,-1073741708--1073741605,-1073741601--1073741597,-1073741595--1073741574,-1073741572--1073741562
0x180009e9a  lea     rdx, __ImageBase
0x180009ea1  cdqe
0x180009ea3  movzx   eax, ds:(byte_18000A0C8 - 180000000h)[rdx+rax]
0x180009eab  mov     ecx, ds:(jpt_180009EB5 - 180000000h)[rdx+rax*4]
0x180009eb2  add     rcx, rdx
0x180009eb5  jmp     rcx; switch jump
0x180009ebb  mov     ebx, 84Bh; jumptable 0000000180009EB5 case -1073741789
0x180009ec0  jmp     loc_180009D7F
0x180009ec5  mov     ebx, 961h; jumptable 0000000180009EB5 case -1073741561
0x180009eca  jmp     loc_180009D7F
0x180009ecf  mov     ebx, 964h; jumptable 0000000180009EB5 case -1073741560
0x180009ed4  jmp     loc_180009D7F
0x180009ed9  mov     ebx, 8C1h; jumptable 0000000180009EB5 case -1073741713
0x180009ede  jmp     loc_180009D7F
0x180009ee3  mov     ebx, 8C0h; jumptable 0000000180009EB5 case -1073741712
0x180009ee8  jmp     loc_180009D7F
0x180009eed  mov     ebx, 8C2h; jumptable 0000000180009EB5 case -1073741711
0x180009ef2  jmp     loc_180009D7F
0x180009ef7  mov     ebx, 836h; jumptable 0000000180009EB5 case -1073741573
0x180009efc  jmp     loc_180009D7F
  ... truncated ...
```
