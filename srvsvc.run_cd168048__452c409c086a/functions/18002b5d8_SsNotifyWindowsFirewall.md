# SsNotifyWindowsFirewall

- ea: `0x18002b5d8`
- end: `0x18002b7af`
- name: `SsNotifyWindowsFirewall`
- size: `471`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task, installer_update`

## callers

- `0x180003f60`

## callees

- `0x18001deb0`
- `0x180020cb0`
- `0x180020de8`
- `0x18002a28c`
- `0x18002b3bc`
- `0x18002b5d8`
- `0x18004112c`
- `0x1800411cc`

## import_xrefs

- `ntdll!RtlGetNtProductType` at `0x18002b60e`
- `ntdll!RtlGetNtProductType` at `0x18002b60e`
- `RPCRT4!RpcImpersonateClient` at `0x18002b65c`
- `RPCRT4!RpcImpersonateClient` at `0x18002b65c`
- `RPCRT4!RpcRevertToSelf` at `0x18002b77a`
- `RPCRT4!RpcRevertToSelf` at `0x18002b77a`

## pseudocode

```c
__int64 SsNotifyWindowsFirewall()
{
  int IsFirewallServiceRunning; // eax
  unsigned int v1; // eax
  unsigned int v2; // esi
  unsigned int v3; // r14d
  __int64 v4; // rcx
  int v5; // eax
  __int64 v6; // rcx
  __int64 v7; // r8
  enum _NT_PRODUCT_TYPE ProductType; // [rsp+30h] [rbp-38h] BYREF
  int v10; // [rsp+34h] [rbp-34h] BYREF
  _DWORD v11[4]; // [rsp+38h] [rbp-30h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+48h] [rbp-20h] BYREF

  v10 = 1;
  v11[0] = 0;
  ProductType = RtlGetNtProductType(&ProductType) == 0;
  if ( ProductType == NtProductWinNt && !DWORD2(xmmword_18005CBE0) )
    return 0;
  if ( dword_18005E550 )
    return 0;
  IsFirewallServiceRunning = SsIsFirewallServiceRunning();
  if ( IsFirewallServiceRunning == 1077 || IsFirewallServiceRunning == 1060 )
    return 0;
  v1 = RpcImpersonateClient(0);
  v2 = v1;
  v11[3] = v1;
  if ( !v1 || v1 == 1725 )
  {
    if ( IsSMB1ServerInstalled(v11) >= 0 && v11[0] )
      v5 = WindowsFireall_EnableFileAndPrinterSharing(v4, &v10);
    else
      v5 = WindowsFireall_EnableFileAndPrinterSharingV2(v4, &v10);
    v11[1] = v5;
    v3 = (unsigned __int16)v5;
    v11[2] = (unsigned __int16)v5;
    if ( v5 >= 0 )
    {
      if ( !v10 && (byte_18005FE1A & 4) != 0 )
        McGenEventWrite_EventWriteTransfer(
          v6,
          (const EVENT_DESCRIPTOR *)SMB2_EVENT_FILE_SHARING_FIREWALL_RULE_ENABLED,
          v7,
          1u,
          &v12);
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        40,
        WPP_cee36e08cc873b175cea1cc8b33051d6_Traceguids,
        (unsigned int)v5);
    }
    if ( !v2 )
      RpcRevertToSelf();
  }
  else
  {
    v3 = v1;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_cee36e08cc873b175cea1cc8b33051d6_Traceguids, v1);
    }
  }
  if ( dword_18005E554 )
    return 0;
  return v3;
}

```

## disassembly

```asm
0x18002b5d8  mov     [rsp+arg_0], rbx
0x18002b5dd  mov     [rsp+arg_8], rsi
0x18002b5e2  push    r14
0x18002b5e4  sub     rsp, 60h
0x18002b5e8  mov     rax, cs:__security_cookie
0x18002b5ef  xor     rax, rsp
0x18002b5f2  mov     [rsp+68h+var_10], rax
0x18002b5f7  xor     ebx, ebx
0x18002b5f9  mov     [rsp+68h+ProductType], ebx
0x18002b5fd  mov     [rsp+68h+var_34], 1
0x18002b605  mov     [rsp+68h+var_30], ebx
0x18002b609  lea     rcx, [rsp+68h+ProductType]; ProductType
0x18002b60e  call    cs:__imp_RtlGetNtProductType
0x18002b614  test    al, al
0x18002b616  jnz     short loc_18002B620
0x18002b618  mov     [rsp+68h+ProductType], 1
0x18002b620  cmp     [rsp+68h+ProductType], 1
0x18002b625  jnz     short loc_18002B633
0x18002b627  cmp     dword ptr cs:xmmword_18005CBE0+8, ebx
0x18002b62d  jz      loc_18002B78F
0x18002b633  cmp     cs:dword_18005E550, ebx
0x18002b639  jnz     loc_18002B78F
0x18002b63f  call    SsIsFirewallServiceRunning
0x18002b644  cmp     eax, 435h
0x18002b649  jz      loc_18002B78F
0x18002b64f  cmp     eax, 424h
0x18002b654  jz      loc_18002B78F
0x18002b65a  xor     ecx, ecx; BindingHandle
0x18002b65c  call    cs:__imp_RpcImpersonateClient
0x18002b662  mov     esi, eax
0x18002b664  mov     [rsp+68h+var_24], eax
0x18002b668  test    eax, eax
0x18002b66a  jz      short loc_18002B6BE
0x18002b66c  cmp     eax, 6BDh
0x18002b671  jz      short loc_18002B6BE
0x18002b673  mov     r14d, eax
0x18002b676  lea     rdx, WPP_GLOBAL_Control
0x18002b67d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b684  cmp     rcx, rdx
0x18002b687  jz      loc_18002B780
0x18002b68d  test    byte ptr [rcx+1Ch], 4
0x18002b691  jz      loc_18002B780
0x18002b697  cmp     byte ptr [rcx+19h], 1
0x18002b69b  jb      loc_18002B780
0x18002b6a1  mov     edx, 27h ; '''
0x18002b6a6  mov     r9d, eax
0x18002b6a9  lea     r8, WPP_cee36e08cc873b175cea1cc8b33051d6_Traceguids
0x18002b6b0  mov     rcx, [rcx+10h]
0x18002b6b4  call    WPP_SF_d
0x18002b6b9  jmp     loc_18002B780
0x18002b6be  lea     rcx, [rsp+68h+var_30]
0x18002b6c3  call    IsSMB1ServerInstalled
0x18002b6c8  test    eax, eax
0x18002b6ca  js      short loc_18002B6DE
0x18002b6cc  cmp     [rsp+68h+var_30], ebx
0x18002b6d0  jz      short loc_18002B6DE
0x18002b6d2  lea     rdx, [rsp+68h+var_34]
0x18002b6d7  call    WindowsFireall_EnableFileAndPrinterSharing
0x18002b6dc  jmp     short loc_18002B6E8
0x18002b6de  lea     rdx, [rsp+68h+var_34]
0x18002b6e3  call    WindowsFireall_EnableFileAndPrinterSharingV2
0x18002b6e8  mov     [rsp+68h+var_2C], eax
0x18002b6ec  movzx   r14d, ax
0x18002b6f0  mov     [rsp+68h+var_28], r14d
0x18002b6f5  jmp     short loc_18002B70E
0x18002b6f7  mov     r14d, eax
0x18002b6fa  mov     eax, 80004005h
0x18002b6ff  mov     [rsp+68h+var_2C], eax
0x18002b703  mov     [rsp+68h+var_28], r14d
0x18002b708  xor     ebx, ebx
0x18002b70a  mov     esi, [rsp+68h+var_24]
0x18002b70e  test    eax, eax
0x18002b710  jns     short loc_18002B74B
0x18002b712  lea     rdx, WPP_GLOBAL_Control
0x18002b719  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b720  cmp     rcx, rdx
0x18002b723  jz      short loc_18002B776
0x18002b725  test    byte ptr [rcx+1Ch], 4
0x18002b729  jz      short loc_18002B776
0x18002b72b  cmp     byte ptr [rcx+19h], 1
0x18002b72f  jb      short loc_18002B776
0x18002b731  mov     edx, 28h ; '('
0x18002b736  mov     r9d, eax
0x18002b739  lea     r8, WPP_cee36e08cc873b175cea1cc8b33051d6_Traceguids
0x18002b740  mov     rcx, [rcx+10h]
0x18002b744  call    WPP_SF_d
0x18002b749  jmp     short loc_18002B776
0x18002b74b  cmp     [rsp+68h+var_34], ebx
0x18002b74f  jnz     short loc_18002B776
0x18002b751  test    cs:byte_18005FE1A, 4
0x18002b758  jz      short loc_18002B776
0x18002b75a  lea     rax, [rsp+68h+var_20]
0x18002b75f  mov     [rsp+68h+var_48], rax
0x18002b764  mov     r9d, 1
0x18002b76a  lea     rdx, SMB2_EVENT_FILE_SHARING_FIREWALL_RULE_ENABLED
0x18002b771  call    McGenEventWrite_EventWriteTransfer
0x18002b776  test    esi, esi
0x18002b778  jnz     short loc_18002B780
0x18002b77a  call    cs:__imp_RpcRevertToSelf
0x18002b780  cmp     cs:dword_18005E554, ebx
0x18002b786  cmovnz  r14d, ebx
0x18002b78a  mov     eax, r14d
0x18002b78d  jmp     short loc_18002B791
0x18002b78f  xor     eax, eax
0x18002b791  mov     rcx, [rsp+68h+var_10]
0x18002b796  xor     rcx, rsp; StackCookie
0x18002b799  call    __security_check_cookie
0x18002b79e  mov     rbx, [rsp+68h+arg_0]
0x18002b7a3  mov     rsi, [rsp+68h+arg_8]
0x18002b7a8  add     rsp, 60h
0x18002b7ac  pop     r14
0x18002b7ae  retn
```
