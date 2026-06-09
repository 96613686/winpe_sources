# SampCreateBindingHandle(ushort *,void * *)

- ea: `0x180005ca0`
- end: `0x180005e89`
- name: `?SampCreateBindingHandle@@YAJPEAGPEAPEAX@Z`
- size: `489`
- prototype: `__int64 __fastcall(LPCWSTR ServiceName, RPC_BINDING_HANDLE *Binding)`
- caller_count: `5`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005ab0`
- `0x180006060`
- `0x18000f4a0`
- `0x180012520`
- `0x180013980`

## callees

- `0x180005ca0`
- `0x18000807c`
- `0x180015d48`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005e62`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005e62`
- `RPCRT4!I_RpcMapWin32Status` at `0x180005cfd`
- `RPCRT4!I_RpcMapWin32Status` at `0x180005d3e`
- `RPCRT4!I_RpcMapWin32Status` at `0x180005d8e`
- `RPCRT4!I_RpcMapWin32Status` at `0x180005e1d`
- `RPCRT4!I_RpcMapWin32Status` at `0x180005cfd`
- `RPCRT4!I_RpcMapWin32Status` at `0x180005d3e`
- `RPCRT4!I_RpcMapWin32Status` at `0x180005d8e`
- `RPCRT4!I_RpcMapWin32Status` at `0x180005e1d`
- `RPCRT4!RpcBindingFree` at `0x180005e57`
- `RPCRT4!RpcBindingFree` at `0x180005e57`
- `RPCRT4!RpcStringBindingComposeW` at `0x180005cf5`
- `RPCRT4!RpcStringBindingComposeW` at `0x180005cf5`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180005d36`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180005d36`
- `RPCRT4!RpcBindingSetOption` at `0x180005d86`
- `RPCRT4!RpcBindingSetOption` at `0x180005d86`
- `RPCRT4!RpcBindingSetAuthInfoW` at `0x180005e15`
- `RPCRT4!RpcBindingSetAuthInfoW` at `0x180005e15`
- `RPCRT4!RpcStringFreeW` at `0x180005e74`
- `RPCRT4!RpcStringFreeW` at `0x180005e74`

## pseudocode

```c
__int64 __fastcall SampCreateBindingHandle(unsigned __int16 *ServiceName, RPC_BINDING_HANDLE *Binding)
{
  unsigned __int16 *v4; // rdx
  unsigned __int16 *v5; // r9
  RPC_STATUS v6; // eax
  int SpnW; // eax
  unsigned int v8; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  RPC_STATUS v11; // eax
  RPC_STATUS v12; // eax
  unsigned __int16 *v13; // r8
  unsigned __int16 v14; // r9
  RPC_STATUS v15; // eax
  unsigned __int16 *Options; // [rsp+20h] [rbp-28h]
  RPC_WSTR String; // [rsp+50h] [rbp+8h] BYREF
  RPC_WSTR ServerPrincName; // [rsp+58h] [rbp+10h] BYREF

  *Binding = 0;
  String = 0;
  ServerPrincName = 0;
  v4 = L"ncalrpc";
  if ( ServiceName )
    v4 = L"ncacn_ip_tcp";
  v5 = L"samss lpc";
  if ( ServiceName )
    v5 = 0;
  v6 = RpcStringBindingComposeW(0, v4, ServiceName, v5, 0, &String);
  SpnW = I_RpcMapWin32Status(v6);
  v8 = SpnW;
  if ( SpnW < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_27;
    v10 = 358;
    goto LABEL_26;
  }
  v11 = RpcBindingFromStringBindingW(String, Binding);
  SpnW = I_RpcMapWin32Status(v11);
  v8 = SpnW;
  if ( SpnW < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_27;
    v10 = 359;
    goto LABEL_26;
  }
  if ( !ServiceName )
    goto LABEL_28;
  v12 = RpcBindingSetOption(*Binding, 5u, 1u);
  SpnW = I_RpcMapWin32Status(v12);
  v8 = SpnW;
  if ( SpnW < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_27;
    v10 = 360;
    goto LABEL_26;
  }
  SpnW = SampDsMakeSpnW(L"HOST", ServiceName, v13, v14, Options, &ServerPrincName);
  v8 = SpnW;
  if ( SpnW < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_27;
    v10 = 361;
    goto LABEL_26;
  }
  v15 = RpcBindingSetAuthInfoW(*Binding, ServerPrincName, 6u, 9u, 0, 0);
  SpnW = I_RpcMapWin32Status(v15);
  v8 = SpnW;
  if ( SpnW >= 0 )
    goto LABEL_28;
  v9 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v10 = 362;
LABEL_26:
    WPP_SF_D(v9[2], v10, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, (unsigned int)SpnW);
  }
LABEL_27:
  RpcBindingFree(Binding);
LABEL_28:
  LocalFree(ServerPrincName);
  if ( String )
    RpcStringFreeW(&String);
  return v8;
}

```

## disassembly

```asm
0x180005ca0  mov     [rsp+arg_10], rbx
0x180005ca5  push    rbp
0x180005ca6  push    rsi
0x180005ca7  push    rdi
0x180005ca8  sub     rsp, 30h
0x180005cac  xor     ebp, ebp
0x180005cae  lea     rax, aNcacnIpTcp; "ncacn_ip_tcp"
0x180005cb5  test    rcx, rcx
0x180005cb8  mov     [rdx], rbp
0x180005cbb  mov     rsi, rdx
0x180005cbe  mov     [rsp+48h+String], rbp
0x180005cc3  mov     rdi, rcx
0x180005cc6  mov     [rsp+48h+ServerPrincName], rbp
0x180005ccb  mov     r8, rcx; NetworkAddr
0x180005cce  lea     rdx, aNcalrpc; "ncalrpc"
0x180005cd5  cmovnz  rdx, rax; ProtSeq
0x180005cd9  lea     r9, Endpoint; "samss lpc"
0x180005ce0  lea     rax, [rsp+48h+String]
0x180005ce5  cmovnz  r9, rbp; Endpoint
0x180005ce9  mov     [rsp+48h+StringBinding], rax; StringBinding
0x180005cee  xor     ecx, ecx; ObjUuid
0x180005cf0  mov     [rsp+48h+Options], rbp; unsigned __int16 *
0x180005cf5  call    cs:__imp_RpcStringBindingComposeW
0x180005cfb  mov     ecx, eax; Status
0x180005cfd  call    cs:__imp_I_RpcMapWin32Status
0x180005d03  mov     ebx, eax
0x180005d05  test    eax, eax
0x180005d07  jns     short loc_180005D2E
0x180005d09  mov     rcx, cs:WPP_GLOBAL_Control
0x180005d10  test    byte ptr [rcx+1Ch], 2
0x180005d14  jz      loc_180005E54
0x180005d1a  cmp     byte ptr [rcx+19h], 2
0x180005d1e  jb      loc_180005E54
0x180005d24  mov     edx, 166h
0x180005d29  jmp     loc_180005E41
0x180005d2e  mov     rcx, [rsp+48h+String]; StringBinding
0x180005d33  mov     rdx, rsi; Binding
0x180005d36  call    cs:__imp_RpcBindingFromStringBindingW
0x180005d3c  mov     ecx, eax; Status
0x180005d3e  call    cs:__imp_I_RpcMapWin32Status
0x180005d44  mov     ebx, eax
0x180005d46  test    eax, eax
0x180005d48  jns     short loc_180005D6F
0x180005d4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180005d51  test    byte ptr [rcx+1Ch], 2
0x180005d55  jz      loc_180005E54
0x180005d5b  cmp     byte ptr [rcx+19h], 2
0x180005d5f  jb      loc_180005E54
0x180005d65  mov     edx, 167h
0x180005d6a  jmp     loc_180005E41
0x180005d6f  test    rdi, rdi
0x180005d72  jz      loc_180005E5D
0x180005d78  mov     rcx, [rsi]; hBinding
0x180005d7b  mov     edx, 5; option
0x180005d80  mov     r8d, 1; optionValue
0x180005d86  call    cs:__imp_RpcBindingSetOption
0x180005d8c  mov     ecx, eax; Status
0x180005d8e  call    cs:__imp_I_RpcMapWin32Status
0x180005d94  mov     ebx, eax
0x180005d96  test    eax, eax
0x180005d98  jns     short loc_180005DBF
0x180005d9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180005da1  test    byte ptr [rcx+1Ch], 2
0x180005da5  jz      loc_180005E54
0x180005dab  cmp     byte ptr [rcx+19h], 2
0x180005daf  jb      loc_180005E54
0x180005db5  mov     edx, 168h
0x180005dba  jmp     loc_180005E41
0x180005dbf  lea     rax, [rsp+48h+ServerPrincName]
0x180005dc4  mov     rdx, rdi; ServiceName
0x180005dc7  lea     rcx, ServiceClass; "HOST"
0x180005dce  mov     [rsp+48h+StringBinding], rax; unsigned __int16 **
0x180005dd3  call    ?SampDsMakeSpnW@@YAJPEAG00G0PEAPEAG@Z; SampDsMakeSpnW(ushort *,ushort *,ushort *,ushort,ushort *,ushort * *)
0x180005dd8  mov     ebx, eax
0x180005dda  test    eax, eax
0x180005ddc  jns     short loc_180005DF8
0x180005dde  mov     rcx, cs:WPP_GLOBAL_Control
0x180005de5  test    byte ptr [rcx+1Ch], 2
0x180005de9  jz      short loc_180005E54
0x180005deb  cmp     byte ptr [rcx+19h], 2
0x180005def  jb      short loc_180005E54
0x180005df1  mov     edx, 169h
0x180005df6  jmp     short loc_180005E41
0x180005df8  mov     rdx, [rsp+48h+ServerPrincName]; ServerPrincName
0x180005dfd  mov     r9d, 9; AuthnSvc
0x180005e03  mov     rcx, [rsi]; Binding
0x180005e06  mov     r8d, 6; AuthnLevel
0x180005e0c  mov     dword ptr [rsp+48h+StringBinding], ebp; AuthzSvc
0x180005e10  mov     [rsp+48h+Options], rbp; AuthIdentity
0x180005e15  call    cs:__imp_RpcBindingSetAuthInfoW
0x180005e1b  mov     ecx, eax; Status
0x180005e1d  call    cs:__imp_I_RpcMapWin32Status
0x180005e23  mov     ebx, eax
0x180005e25  test    eax, eax
0x180005e27  jns     short loc_180005E5D
0x180005e29  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e30  test    byte ptr [rcx+1Ch], 2
0x180005e34  jz      short loc_180005E54
0x180005e36  cmp     byte ptr [rcx+19h], 2
0x180005e3a  jb      short loc_180005E54
0x180005e3c  mov     edx, 16Ah
0x180005e41  mov     rcx, [rcx+10h]
0x180005e45  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180005e4c  mov     r9d, eax
0x180005e4f  call    WPP_SF_D
0x180005e54  mov     rcx, rsi; Binding
0x180005e57  call    cs:__imp_RpcBindingFree
0x180005e5d  mov     rcx, [rsp+48h+ServerPrincName]; hMem
0x180005e62  call    cs:__imp_LocalFree
0x180005e68  cmp     [rsp+48h+String], rbp
0x180005e6d  jz      short loc_180005E7A
0x180005e6f  lea     rcx, [rsp+48h+String]; String
0x180005e74  call    cs:__imp_RpcStringFreeW
0x180005e7a  mov     eax, ebx
0x180005e7c  mov     rbx, [rsp+48h+arg_10]
0x180005e81  add     rsp, 30h
0x180005e85  pop     rdi
0x180005e86  pop     rsi
0x180005e87  pop     rbp
0x180005e88  retn
```
