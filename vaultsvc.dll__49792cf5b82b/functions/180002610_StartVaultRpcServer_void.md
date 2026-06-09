# StartVaultRpcServer(void)

- ea: `0x180002610`
- end: `0x180002807`
- name: `?StartVaultRpcServer@@YAJXZ`
- size: `503`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001aa0`

## callees

- `0x180002610`
- `0x18003b7b0`
- `0x18003b7d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002660`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002660`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800027fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004b53f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800027fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004b53f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000263d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000263d`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x1800026ad`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x1800026ad`
- `RPCRT4!RpcServerRegisterIf3` at `0x18000273a`
- `RPCRT4!RpcServerRegisterIf3` at `0x18000273a`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x1800027e3`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x18004b529`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x1800027e3`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x18004b529`

## pseudocode

```c
__int64 StartVaultRpcServer(void)
{
  DWORD LastError; // eax
  unsigned int v2; // eax
  unsigned int v3; // edi
  PVOID *v4; // rcx
  __int64 v5; // rdx
  void *SecurityDescriptor; // [rsp+60h] [rbp+8h] BYREF

  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"D:(A;;GA;;;WD)(A;;GA;;;S-1-15-2-1)",
          1u,
          &SecurityDescriptor,
          0) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_e7f8043feac3354e84ee43f895a5e6cf_Traceguids, LastError);
    }
    return 1766;
  }
  v2 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncalrpc", 0xAu, (RPC_WSTR)L"Vault", SecurityDescriptor);
  v3 = v2;
  if ( !v2 || v2 == 1740 )
  {
    v2 = RpcServerRegisterIf3(qword_18004E1F0, 0, 0, 105, 1234, -1, VaultRpcSecurityCallback, SecurityDescriptor, v2);
    v3 = v2;
    if ( !v2 )
    {
      byte_18005F910 = 1;
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_20;
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_e7f8043feac3354e84ee43f895a5e6cf_Traceguids);
      goto LABEL_19;
    }
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_20;
    v5 = 12;
  }
  else
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_20;
    v5 = 11;
  }
  WPP_SF_d(v4[2], v5, WPP_e7f8043feac3354e84ee43f895a5e6cf_Traceguids, v2);
LABEL_19:
  v4 = (PVOID *)WPP_GLOBAL_Control;
LABEL_20:
  if ( v3 )
  {
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 )
      WPP_SF_d(v4[2], 14, WPP_e7f8043feac3354e84ee43f895a5e6cf_Traceguids, v3);
    if ( byte_18005F910 )
    {
      RpcServerUnregisterIfEx(qword_18004E1F0, 0, 1);
      byte_18005F910 = 0;
    }
  }
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return v3;
}

```

## disassembly

```asm
0x180002610  mov     rax, rsp
0x180002613  mov     [rax+10h], rbx
0x180002617  push    rdi
0x180002618  sub     rsp, 50h
0x18000261c  mov     dword ptr [rax-18h], 0
0x180002623  mov     qword ptr [rax+8], 0
0x18000262b  xor     r9d, r9d; SecurityDescriptorSize
0x18000262e  lea     r8, [rax+8]; SecurityDescriptor
0x180002632  lea     edx, [r9+1]; StringSDRevision
0x180002636  lea     rcx, StringSecurityDescriptor; "D:(A;;GA;;;WD)(A;;GA;;;S-1-15-2-1)"
0x18000263d  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180002643  test    eax, eax
0x180002645  jnz     short loc_180002695
0x180002647  lea     rbx, WPP_GLOBAL_Control
0x18000264e  mov     rax, cs:WPP_GLOBAL_Control
0x180002655  cmp     rax, rbx
0x180002658  jz      short loc_180002685
0x18000265a  test    byte ptr [rax+1Ch], 2
0x18000265e  jz      short loc_180002685
0x180002660  call    cs:__imp_GetLastError
0x180002666  mov     edx, 0Ah
0x18000266b  mov     r9d, eax
0x18000266e  lea     r8, WPP_e7f8043feac3354e84ee43f895a5e6cf_Traceguids
0x180002675  mov     rcx, cs:WPP_GLOBAL_Control
0x18000267c  mov     rcx, [rcx+10h]
0x180002680  call    WPP_SF_d
0x180002685  mov     eax, 6E6h
0x18000268a  mov     rbx, [rsp+58h+arg_8]
0x18000268f  add     rsp, 50h
0x180002693  pop     rdi
0x180002694  retn
0x180002695  mov     r9, [rsp+58h+SecurityDescriptor]; SecurityDescriptor
0x18000269a  lea     r8, Endpoint; "Vault"
0x1800026a1  mov     edx, 0Ah; MaxCalls
0x1800026a6  lea     rcx, Protseq; "ncalrpc"
0x1800026ad  call    cs:__imp_RpcServerUseProtseqEpW
0x1800026b3  mov     edi, eax
0x1800026b5  mov     [rsp+58h+var_18], eax
0x1800026b9  test    eax, eax
0x1800026bb  jz      short loc_180002702
0x1800026bd  cmp     eax, 6CCh
0x1800026c2  jz      short loc_180002702
0x1800026c4  lea     rbx, WPP_GLOBAL_Control
0x1800026cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800026d2  cmp     rcx, rbx
0x1800026d5  jz      loc_1800027A6
0x1800026db  test    byte ptr [rcx+1Ch], 1
0x1800026df  jz      loc_1800027A6
0x1800026e5  mov     edx, 0Bh
0x1800026ea  mov     r9d, eax
0x1800026ed  lea     r8, WPP_e7f8043feac3354e84ee43f895a5e6cf_Traceguids
0x1800026f4  mov     rcx, [rcx+10h]
0x1800026f8  call    WPP_SF_d
0x1800026fd  jmp     loc_18000279F
0x180002702  mov     rax, [rsp+58h+SecurityDescriptor]
0x180002707  mov     [rsp+58h+var_20], rax
0x18000270c  lea     rax, ?VaultRpcSecurityCallback@@YAJPEAX0@Z; VaultRpcSecurityCallback(void *,void *)
0x180002713  mov     [rsp+58h+var_28], rax
0x180002718  mov     [rsp+58h+var_30], 0FFFFFFFFh
0x180002720  mov     [rsp+58h+var_38], 4D2h
0x180002728  mov     r9d, 69h ; 'i'
0x18000272e  xor     r8d, r8d
0x180002731  xor     edx, edx
0x180002733  lea     rcx, qword_18004E1F0
0x18000273a  call    cs:__imp_RpcServerRegisterIf3
0x180002740  mov     edi, eax
0x180002742  mov     [rsp+58h+var_18], eax
0x180002746  test    eax, eax
0x180002748  jz      short loc_18000276A
0x18000274a  lea     rbx, WPP_GLOBAL_Control
0x180002751  mov     rcx, cs:WPP_GLOBAL_Control
0x180002758  cmp     rcx, rbx
0x18000275b  jz      short loc_1800027A6
0x18000275d  test    byte ptr [rcx+1Ch], 1
0x180002761  jz      short loc_1800027A6
0x180002763  mov     edx, 0Ch
0x180002768  jmp     short loc_1800026EA
0x18000276a  mov     cs:byte_18005F910, 1
0x180002771  lea     rbx, WPP_GLOBAL_Control
0x180002778  mov     rcx, cs:WPP_GLOBAL_Control
0x18000277f  cmp     rcx, rbx
0x180002782  jz      short loc_1800027A6
0x180002784  test    byte ptr [rcx+1Ch], 8
0x180002788  jz      short loc_1800027A6
0x18000278a  mov     edx, 0Dh
0x18000278f  lea     r8, WPP_e7f8043feac3354e84ee43f895a5e6cf_Traceguids
0x180002796  mov     rcx, [rcx+10h]
0x18000279a  call    WPP_SF_
0x18000279f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800027a6  test    edi, edi
0x1800027a8  jz      short loc_1800027F0
0x1800027aa  cmp     rcx, rbx
0x1800027ad  jz      short loc_1800027CD
0x1800027af  test    byte ptr [rcx+1Ch], 8
0x1800027b3  jz      short loc_1800027CD
0x1800027b5  mov     edx, 0Eh
0x1800027ba  mov     r9d, edi
0x1800027bd  lea     r8, WPP_e7f8043feac3354e84ee43f895a5e6cf_Traceguids
0x1800027c4  mov     rcx, [rcx+10h]
0x1800027c8  call    WPP_SF_d
0x1800027cd  cmp     cs:byte_18005F910, 0
0x1800027d4  jz      short loc_1800027F0
0x1800027d6  xor     edx, edx; MgrTypeUuid
0x1800027d8  lea     r8d, [rdx+1]; RundownContextHandles
0x1800027dc  lea     rcx, qword_18004E1F0; IfSpec
0x1800027e3  call    cs:__imp_RpcServerUnregisterIfEx
0x1800027e9  mov     cs:byte_18005F910, 0
0x1800027f0  mov     rcx, [rsp+58h+SecurityDescriptor]; hMem
0x1800027f5  test    rcx, rcx
0x1800027f8  jz      short loc_180002800
0x1800027fa  call    cs:__imp_LocalFree
0x180002800  mov     eax, edi
0x180002802  jmp     loc_18000268A
0x18004b4d2  push    rbp
0x18004b4d4  sub     rsp, 40h
0x18004b4d8  mov     rbp, rdx
0x18004b4db  mov     r9d, [rbp+40h]
0x18004b4df  test    r9d, r9d
0x18004b4e2  jz      short loc_18004B536
0x18004b4e4  lea     rax, WPP_GLOBAL_Control
0x18004b4eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b4f2  cmp     rcx, rax
0x18004b4f5  jz      short loc_18004B513
0x18004b4f7  test    byte ptr [rcx+1Ch], 8
0x18004b4fb  jz      short loc_18004B513
0x18004b4fd  mov     edx, 0Eh
0x18004b502  lea     r8, WPP_e7f8043feac3354e84ee43f895a5e6cf_Traceguids
0x18004b509  mov     rcx, [rcx+10h]
0x18004b50d  call    WPP_SF_d
0x18004b512  nop
0x18004b513  cmp     cs:byte_18005F910, 0
0x18004b51a  jz      short loc_18004B536
0x18004b51c  xor     edx, edx; MgrTypeUuid
0x18004b51e  lea     r8d, [rdx+1]; RundownContextHandles
0x18004b522  lea     rcx, qword_18004E1F0; IfSpec
0x18004b529  call    cs:__imp_RpcServerUnregisterIfEx
0x18004b52f  mov     cs:byte_18005F910, 0
0x18004b536  mov     rcx, [rbp+60h]; hMem
0x18004b53a  test    rcx, rcx
0x18004b53d  jz      short loc_18004B546
0x18004b53f  call    cs:__imp_LocalFree
0x18004b545  nop
0x18004b546  add     rsp, 40h
0x18004b54a  pop     rbp
0x18004b54b  retn
```
