# PnpRpcStartup

- ea: `0x18000d550`
- end: `0x18000d735`
- name: `PnpRpcStartup`
- size: `485`
- prototype: `_BOOL8()`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x18000cf30`

## callees

- `0x18000d550`
- `0x18000f6f0`
- `0x1800117d4`
- `0x180011964`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d71b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d71b`
- `RPCRT4!RpcServerInterfaceGroupActivate` at `0x18000d6a8`
- `RPCRT4!RpcServerInterfaceGroupActivate` at `0x18000d6a8`
- `RPCRT4!RpcServerInterfaceGroupCreateW` at `0x18000d65b`
- `RPCRT4!RpcServerInterfaceGroupCreateW` at `0x18000d65b`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000d6de`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000d6de`

## string_xrefs

- `0x18000d5fd`: `Device Install Service RPC Interface`

## pseudocode

```c
_BOOL8 PnpRpcStartup()
{
  unsigned int v0; // eax
  RPC_STATUS v1; // ebx
  RPC_STATUS v2; // ecx
  DWORD v3; // ebx
  unsigned int v4; // eax
  RPC_STATUS v5; // edi
  __int128 v7; // [rsp+40h] [rbp-59h] BYREF
  int v8; // [rsp+50h] [rbp-49h] BYREF
  __int64 *v9; // [rsp+58h] [rbp-41h]
  __int128 v10; // [rsp+60h] [rbp-39h]
  int v11; // [rsp+70h] [rbp-29h]
  __int64 v12; // [rsp+74h] [rbp-25h]
  __int64 (__fastcall *v13)(__int64, void *); // [rsp+80h] [rbp-19h]
  __int128 *v14; // [rsp+88h] [rbp-11h]
  const wchar_t *v15; // [rsp+90h] [rbp-9h]
  __int64 v16; // [rsp+98h] [rbp-1h]
  int v17; // [rsp+A0h] [rbp+7h] BYREF
  const WCHAR *v18; // [rsp+A8h] [rbp+Fh]
  __int128 v19; // [rsp+B0h] [rbp+17h]
  int v20; // [rsp+C0h] [rbp+27h]

  v7 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_e24a5924780b3529dc5978c305634275_Traceguids);
  PnpRpcIdle = 0;
  LODWORD(v7) = 1;
  *((_QWORD *)&v7 + 1) = DEVICEINSTALLSERVICE_OBJECT_NAME;
  v8 = 0;
  v9 = qword_18001B000;
  v10 = 0;
  v13 = PnPRpcIfCallback;
  v11 = 49;
  v14 = &v7;
  v12 = 1234;
  v15 = L"Device Install Service RPC Interface";
  v18 = L"ncalrpc";
  v16 = 0;
  v17 = 0;
  v19 = 0;
  v20 = 10;
  v0 = RpcServerInterfaceGroupCreateW(&v8, 1, &v17);
  v1 = v0;
  if ( v0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_e24a5924780b3529dc5978c305634275_Traceguids, v0);
    v2 = v1;
  }
  else
  {
    v3 = 0;
    PnpRpcInterfaceGroupCreated = 1;
    v4 = RpcServerInterfaceGroupActivate(PnpRpcInterfaceGroup);
    v5 = v4;
    if ( !v4 )
      goto LABEL_16;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_e24a5924780b3529dc5978c305634275_Traceguids, v4);
    v2 = v5;
  }
  v3 = I_RpcMapWin32Status(v2);
  if ( v3 )
    PnpRpcShutdown();
LABEL_16:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_e24a5924780b3529dc5978c305634275_Traceguids);
  SetLastError(v3);
  return v3 == 0;
}

```

## disassembly

```asm
0x18000d550  push    rbp
0x18000d552  push    rbx
0x18000d553  push    rdi
0x18000d554  push    r14
0x18000d556  lea     rbp, [rsp-3Fh]
0x18000d55b  sub     rsp, 0D8h
0x18000d562  xorps   xmm0, xmm0
0x18000d565  movups  [rbp+57h+var_B0], xmm0
0x18000d569  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d570  lea     r14, WPP_GLOBAL_Control
0x18000d577  mov     ebx, 0Ah
0x18000d57c  cmp     rcx, r14
0x18000d57f  jz      short loc_18000D59C
0x18000d581  test    dword ptr [rcx+1Ch], 10000000h
0x18000d588  jz      short loc_18000D59C
0x18000d58a  mov     rcx, [rcx+10h]
0x18000d58e  lea     r8, WPP_e24a5924780b3529dc5978c305634275_Traceguids
0x18000d595  mov     edx, ebx
0x18000d597  call    WPP_SF_
0x18000d59c  xorps   xmm0, xmm0
0x18000d59f  mov     cs:PnpRpcIdle, 0
0x18000d5a9  lea     rax, DEVICEINSTALLSERVICE_OBJECT_NAME
0x18000d5b0  mov     dword ptr [rbp+57h+var_B0], 1
0x18000d5b7  mov     qword ptr [rbp+57h+var_B0+8], rax
0x18000d5bb  lea     r8, [rbp+57h+var_50]
0x18000d5bf  lea     rax, qword_18001B000
0x18000d5c6  mov     [rbp+57h+var_A0], 0
0x18000d5cd  mov     [rbp+57h+var_98], rax
0x18000d5d1  lea     rcx, [rbp+57h+var_A0]
0x18000d5d5  lea     rax, PnPRpcIfCallback
0x18000d5dc  movdqa  [rbp+57h+var_90], xmm0
0x18000d5e1  mov     [rbp+57h+var_70], rax
0x18000d5e5  mov     r9d, 1
0x18000d5eb  lea     rax, [rbp+57h+var_B0]
0x18000d5ef  mov     [rbp+57h+var_80], 31h ; '1'
0x18000d5f6  mov     [rbp+57h+var_68], rax
0x18000d5fa  mov     edx, r9d
0x18000d5fd  lea     rax, aDeviceInstallS_0; "Device Install Service RPC Interface"
0x18000d604  mov     [rbp+57h+var_7C], 4D2h
0x18000d60c  mov     [rbp+57h+var_60], rax
0x18000d610  lea     rax, String2; "ncalrpc"
0x18000d617  mov     [rbp+57h+var_48], rax
0x18000d61b  lea     rax, PnpRpcInterfaceGroup
0x18000d622  mov     [rsp+0F0h+var_B8], rax
0x18000d627  lea     rax, PnpRpcInterfaceGroupIdleCallback
0x18000d62e  mov     [rsp+0F0h+var_C0], 0
0x18000d637  mov     [rsp+0F0h+var_C8], rax
0x18000d63c  mov     [rsp+0F0h+var_D0], 1Eh
0x18000d644  mov     [rbp+57h+var_58], 0
0x18000d64c  mov     [rbp+57h+var_50], 0
0x18000d653  movdqu  [rbp+57h+var_40], xmm0
0x18000d658  mov     [rbp+57h+var_30], ebx
0x18000d65b  call    cs:__imp_RpcServerInterfaceGroupCreateW
0x18000d661  mov     ebx, eax
0x18000d663  test    eax, eax
0x18000d665  jz      short loc_18000D695
0x18000d667  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d66e  cmp     rcx, r14
0x18000d671  jz      short loc_18000D691
0x18000d673  test    byte ptr [rcx+1Ch], 1
0x18000d677  jz      short loc_18000D691
0x18000d679  mov     rcx, [rcx+10h]
0x18000d67d  lea     r8, WPP_e24a5924780b3529dc5978c305634275_Traceguids
0x18000d684  mov     edx, 0Bh
0x18000d689  mov     r9d, eax
0x18000d68c  call    WPP_SF_d
0x18000d691  mov     ecx, ebx
0x18000d693  jmp     short loc_18000D6DE
0x18000d695  mov     rcx, cs:PnpRpcInterfaceGroup
0x18000d69c  xor     ebx, ebx
0x18000d69e  mov     cs:PnpRpcInterfaceGroupCreated, 1
0x18000d6a8  call    cs:__imp_RpcServerInterfaceGroupActivate
0x18000d6ae  mov     edi, eax
0x18000d6b0  test    eax, eax
0x18000d6b2  jz      short loc_18000D6EF
0x18000d6b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d6bb  cmp     rcx, r14
0x18000d6be  jz      short loc_18000D6DC
0x18000d6c0  test    byte ptr [rcx+1Ch], 1
0x18000d6c4  jz      short loc_18000D6DC
0x18000d6c6  mov     rcx, [rcx+10h]
0x18000d6ca  lea     edx, [rbx+0Ch]
0x18000d6cd  mov     r9d, eax
0x18000d6d0  lea     r8, WPP_e24a5924780b3529dc5978c305634275_Traceguids
0x18000d6d7  call    WPP_SF_d
0x18000d6dc  mov     ecx, edi; Status
0x18000d6de  call    cs:__imp_I_RpcMapWin32Status
0x18000d6e4  mov     ebx, eax
0x18000d6e6  test    eax, eax
0x18000d6e8  jz      short loc_18000D6EF
0x18000d6ea  call    PnpRpcShutdown
0x18000d6ef  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d6f6  cmp     rcx, r14
0x18000d6f9  jz      short loc_18000D719
0x18000d6fb  test    dword ptr [rcx+1Ch], 10000000h
0x18000d702  jz      short loc_18000D719
0x18000d704  mov     rcx, [rcx+10h]
0x18000d708  lea     r8, WPP_e24a5924780b3529dc5978c305634275_Traceguids
0x18000d70f  mov     edx, 0Dh
0x18000d714  call    WPP_SF_
0x18000d719  mov     ecx, ebx; dwErrCode
0x18000d71b  call    cs:__imp_SetLastError
0x18000d721  xor     eax, eax
0x18000d723  test    ebx, ebx
0x18000d725  setz    al
0x18000d728  add     rsp, 0D8h
0x18000d72f  pop     r14
0x18000d731  pop     rdi
0x18000d732  pop     rbx
0x18000d733  pop     rbp
0x18000d734  retn
```
