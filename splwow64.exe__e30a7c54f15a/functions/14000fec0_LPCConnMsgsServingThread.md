# LPCConnMsgsServingThread

- ea: `0x14000fec0`
- end: `0x14001003e`
- name: `LPCConnMsgsServingThread`
- size: `382`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x1400028b8`
- `0x1400086e0`
- `0x14000faa4`
- `0x14000fec0`
- `0x140011624`
- `0x1400120f8`

## import_xrefs

- `ntdll!NtAlpcCancelMessage` at `0x140010033`
- `ntdll!NtAlpcCancelMessage` at `0x140010033`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x14000ff7e`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x14000ff7e`
- `ntdll!NtAlpcDeleteSectionView` at `0x140010014`
- `ntdll!NtAlpcDeleteSectionView` at `0x140010014`

## string_xrefs

- `0x14000ff84`: `LPCConnnMsgServingThread active.`
- `0x14000ff8d`: `LPCConnMsgsServingThread`

## pseudocode

```c
void __fastcall __noreturn LPCConnMsgsServingThread(void ***Parameter)
{
  void **v1; // rsi
  void *v2; // rdi
  int v3; // ebx
  __int64 v4; // [rsp+40h] [rbp-C0h] BYREF
  int v5; // [rsp+50h] [rbp-B0h] BYREF
  int v6; // [rsp+54h] [rbp-ACh]
  _BYTE v7[16]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v8; // [rsp+68h] [rbp-98h]
  void *v9; // [rsp+78h] [rbp-88h] BYREF
  _PORT_MESSAGE v10; // [rsp+A0h] [rbp-60h] BYREF

  v1 = *Parameter;
  memset_0(&v5, 0, 0x48u);
  v4 = 0;
  v2 = v1[8];
  memset_0(&v10, 0, 0x48u);
  while ( 1 )
  {
    do
    {
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::GetImpl'::`2'::impl);
      memset_0(&v5, 0, 0x48u);
      v5 = 1610612736;
      v4 = 512;
      v3 = NtAlpcSendWaitReceivePort(v2, 0, 0, 0, &v10, &v4, &v5, 0);
      SplWow64Telemetry::WriteDbgTraceInfo("LPCConnMsgsServingThread", L"LPCConnnMsgServingThread active.");
      v2 = v1[8];
    }
    while ( v3 < 0 );
    if ( LOBYTE(v10.u2.ZeroInit) == 1 || LOBYTE(v10.u2.ZeroInit) == 5 || LOBYTE(v10.u2.ZeroInit) == 6 )
    {
      if ( !v9 )
        goto LABEL_11;
      if ( (v6 & 0x40000000) != 0 )
        goto LABEL_12;
      if ( TLPCMgr::QueueRequest((TLPCMgr *)v1, v9, (struct PROXY_MSG *)&v10) < 0 )
        goto LABEL_11;
    }
    else if ( LOBYTE(v10.u2.ZeroInit) == 10 )
    {
      TLPCMgr::ProcessConnectionRequest((TLPCMgr *)v1, v1[8], &v10, (struct _ALPC_DATA_VIEW_ATTR *)v7);
    }
    else
    {
LABEL_11:
      if ( (v6 & 0x40000000) != 0 )
LABEL_12:
        NtAlpcDeleteSectionView(v2, 0, v8);
      if ( (v10.u2.s2.Type & 0x2000) != 0 )
        NtAlpcCancelMessage(v2, 0, &v9);
    }
  }
}

```

## disassembly

```asm
0x14000fec0  mov     [rsp-8+arg_8], rbx
0x14000fec5  mov     [rsp-8+arg_10], rsi
0x14000feca  push    rbp
0x14000fecb  push    rdi
0x14000fecc  push    r15
0x14000fece  lea     rbp, [rsp-1B0h]
0x14000fed6  sub     rsp, 2B0h
0x14000fedd  mov     rax, cs:__security_cookie
0x14000fee4  xor     rax, rsp
0x14000fee7  mov     [rbp+1C0h+var_20], rax
0x14000feee  mov     rsi, [rcx]
0x14000fef1  mov     r15d, 48h ; 'H'
0x14000fef7  mov     r8d, r15d; Size
0x14000fefa  lea     rcx, [rsp+2C0h+var_270]; void *
0x14000feff  xor     edx, edx; Val
0x14000ff01  call    memset_0
0x14000ff06  mov     r8d, r15d; Size
0x14000ff09  mov     [rsp+2C0h+var_280], 0
0x14000ff12  mov     rdi, [rsi+40h]
0x14000ff16  lea     rcx, [rbp+1C0h+var_220]; void *
0x14000ff1a  xor     edx, edx; Val
0x14000ff1c  call    memset_0
0x14000ff21  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1> `wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::GetImpl(void)'::`2'::impl
0x14000ff28  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::__private_IsEnabled(void)
0x14000ff2d  mov     r8, r15; Size
0x14000ff30  lea     rcx, [rsp+2C0h+var_270]; void *
0x14000ff35  xor     edx, edx; Val
0x14000ff37  call    memset_0
0x14000ff3c  mov     [rsp+2C0h+var_288], 0
0x14000ff45  lea     rax, [rsp+2C0h+var_270]
0x14000ff4a  mov     [rsp+2C0h+var_290], rax
0x14000ff4f  xor     r9d, r9d
0x14000ff52  lea     rax, [rsp+2C0h+var_280]
0x14000ff57  mov     [rsp+2C0h+var_270], 60000000h
0x14000ff5f  mov     [rsp+2C0h+var_298], rax
0x14000ff64  xor     r8d, r8d
0x14000ff67  lea     rax, [rbp+1C0h+var_220]
0x14000ff6b  mov     [rsp+2C0h+var_280], 200h
0x14000ff74  xor     edx, edx
0x14000ff76  mov     [rsp+2C0h+var_2A0], rax
0x14000ff7b  mov     rcx, rdi
0x14000ff7e  call    cs:__imp_NtAlpcSendWaitReceivePort
0x14000ff84  lea     rdx, aLpcconnnmsgser; "LPCConnnMsgServingThread active."
0x14000ff8b  mov     ebx, eax
0x14000ff8d  lea     rcx, aLpcconnmsgsser; "LPCConnMsgsServingThread"
0x14000ff94  call    ?WriteDbgTraceInfo@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14000ff99  mov     rdi, [rsi+40h]
0x14000ff9d  test    ebx, ebx
0x14000ff9f  js      short loc_14000FF21
0x14000ffa1  movzx   ecx, word ptr [rbp+1C0h+var_220.u2]
0x14000ffa5  and     ecx, 0FFFF00FFh
0x14000ffab  sub     ecx, 1
0x14000ffae  jz      short loc_14000FFD8
0x14000ffb0  sub     ecx, 4
0x14000ffb3  jz      short loc_14000FFD8
0x14000ffb5  sub     ecx, 1
0x14000ffb8  jz      short loc_14000FFD8
0x14000ffba  cmp     ecx, 4
0x14000ffbd  jnz     short loc_140010000
0x14000ffbf  lea     r9, [rsp+2C0h+var_268]; struct _ALPC_DATA_VIEW_ATTR *
0x14000ffc4  mov     rdx, rdi; void *
0x14000ffc7  lea     r8, [rbp+1C0h+var_220]; struct _PORT_MESSAGE *
0x14000ffcb  mov     rcx, rsi; this
0x14000ffce  call    ?ProcessConnectionRequest@TLPCMgr@@QEAAKPEAXPEAU_PORT_MESSAGE@@PEAU_ALPC_DATA_VIEW_ATTR@@@Z; TLPCMgr::ProcessConnectionRequest(void *,_PORT_MESSAGE *,_ALPC_DATA_VIEW_ATTR *)
0x14000ffd3  jmp     loc_14000FF21
0x14000ffd8  mov     rdx, [rsp+2C0h+var_248]; void *
0x14000ffdd  test    rdx, rdx
0x14000ffe0  jz      short loc_140010000
0x14000ffe2  test    [rsp+2C0h+var_26C], 40000000h
0x14000ffea  jnz     short loc_14001000A
0x14000ffec  lea     r8, [rbp+1C0h+var_220]; struct PROXY_MSG *
0x14000fff0  mov     rcx, rsi; this
0x14000fff3  call    ?QueueRequest@TLPCMgr@@QEAAJPEAXPEAUPROXY_MSG@@@Z; TLPCMgr::QueueRequest(void *,PROXY_MSG *)
0x14000fff8  test    eax, eax
0x14000fffa  jns     loc_14000FF21
0x140010000  test    [rsp+2C0h+var_26C], 40000000h
0x140010008  jz      short loc_14001001A
0x14001000a  mov     r8, [rsp+2C0h+var_258]
0x14001000f  xor     edx, edx
0x140010011  mov     rcx, rdi
0x140010014  call    cs:__imp_NtAlpcDeleteSectionView
0x14001001a  mov     eax, 2000h
0x14001001f  test    word ptr [rbp+1C0h+var_220.u2], ax
0x140010023  jz      loc_14000FF21
0x140010029  lea     r8, [rsp+2C0h+var_248]
0x14001002e  xor     edx, edx
0x140010030  mov     rcx, rdi
0x140010033  call    cs:__imp_NtAlpcCancelMessage
0x140010039  jmp     loc_14000FF21
```
