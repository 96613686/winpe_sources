# WinNatConfigureFiltersForAddressPool

- ea: `0x140012fb4`
- end: `0x1400130ed`
- name: `WinNatConfigureFiltersForAddressPool`
- size: `313`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001263c`
- `0x140013250`

## callees

- `0x14000caa0`
- `0x140012fb4`
- `0x14001f320`
- `0x14001f980`

## import_xrefs

- `fwpkclnt!FwpmFilterDeleteById0` at `0x14001309a`
- `fwpkclnt!FwpmFilterDeleteById0` at `0x14001309a`
- `fwpkclnt!FwpmFilterAdd0` at `0x140013079`
- `fwpkclnt!FwpmFilterAdd0` at `0x140013079`
- `fwpkclnt!FwpmEngineClose0` at `0x1400130c1`
- `fwpkclnt!FwpmEngineClose0` at `0x1400130c1`
- `fwpkclnt!FwpmEngineOpen0` at `0x140013007`
- `fwpkclnt!FwpmEngineOpen0` at `0x140013007`

## pseudocode

```c
NTSTATUS __fastcall WinNatConfigureFiltersForAddressPool(char a1)
{
  NTSTATUS result; // eax
  NTSTATUS v3; // ebx
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  HANDLE engineHandle; // [rsp+30h] [rbp-D0h] BYREF
  FWPM_FILTER0 filter; // [rsp+40h] [rbp-C0h] BYREF

  engineHandle = 0;
  memset(&filter, 0, sizeof(filter));
  result = FwpmEngineOpen0(0, 0xAu, 0, 0, &engineHandle);
  if ( result >= 0 )
  {
    if ( a1 )
    {
      filter.displayData.name = L"Windows NAT IP layer filter";
      filter.action.type = 20483;
      filter.displayData.description = L"Filters IP packets that require translation in the external to internal direction";
      filter.layerKey = FWPM_LAYER_INBOUND_IPPACKET_V4;
      filter.subLayerKey = (GUID)WINNAT_WFP_INBOUND_IP_SUBLAYER_IPV4;
      filter.action.4 = *(union FWPM_ACTION0_::$6EA882394A24E7F0D0D0A8FACB4240B6 *)off_140027098;
      v3 = FwpmFilterAdd0(engineHandle, &filter, 0, &id);
    }
    else
    {
      if ( id )
      {
        if ( FwpmFilterDeleteById0(engineHandle, id) < 0 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v5, v4, v6);
        id = 0;
      }
      v3 = 0;
    }
    FwpmEngineClose0(engineHandle);
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x140012fb4  mov     [rsp-8+arg_0], rbx
0x140012fb9  push    rbp
0x140012fba  lea     rbp, [rsp-20h]
0x140012fbf  sub     rsp, 120h
0x140012fc6  mov     rax, cs:__security_cookie
0x140012fcd  xor     rax, rsp
0x140012fd0  mov     [rbp+20h+var_10], rax
0x140012fd4  mov     bl, cl
0x140012fd6  mov     [rsp+120h+var_F0], 0
0x140012fdf  lea     rcx, [rsp+120h+filter]; void *
0x140012fe4  xor     edx, edx; Val
0x140012fe6  mov     r8d, 0C8h; Size
0x140012fec  call    memset
0x140012ff1  xor     r9d, r9d; session
0x140012ff4  lea     rax, [rsp+120h+var_F0]
0x140012ff9  xor     r8d, r8d; authIdentity
0x140012ffc  mov     [rsp+120h+engineHandle], rax; engineHandle
0x140013001  xor     ecx, ecx; serverName
0x140013003  lea     edx, [r9+0Ah]; authnService
0x140013007  call    cs:__imp_FwpmEngineOpen0
0x14001300e  nop     dword ptr [rax+rax+00h]
0x140013013  test    eax, eax
0x140013015  js      loc_1400130CF
0x14001301b  test    bl, bl
0x14001301d  jz      short loc_140013089
0x14001301f  movups  xmm0, xmmword ptr cs:FWPM_LAYER_INBOUND_IPPACKET_V4.Data1
0x140013026  mov     rcx, [rsp+120h+var_F0]; engineHandle
0x14001302b  lea     rax, aWindowsNatIpLa; "Windows NAT IP layer filter"
0x140013032  movups  xmm1, cs:WINNAT_WFP_INBOUND_IP_SUBLAYER_IPV4
0x140013039  mov     [rsp+120h+filter.displayData.name], rax
0x14001303e  lea     r9, id; id
0x140013045  lea     rax, aFiltersIpPacke_0; "Filters IP packets that require transla"...
0x14001304c  mov     [rbp+20h+filter.action.type], 5003h
0x140013053  mov     [rsp+120h+filter.displayData.description], rax
0x140013058  lea     rdx, [rsp+120h+filter]; filter
0x14001305d  mov     rax, cs:off_140027098
0x140013064  xor     r8d, r8d; sd
0x140013067  movdqu  xmmword ptr [rbp+20h+filter.layerKey.Data1], xmm0
0x14001306c  movdqu  xmmword ptr [rbp+20h+filter.subLayerKey.Data1], xmm1
0x140013071  movups  xmm0, xmmword ptr [rax]
0x140013074  movdqu  xmmword ptr [rbp+20h+filter.action.4], xmm0
0x140013079  call    cs:__imp_FwpmFilterAdd0
0x140013080  nop     dword ptr [rax+rax+00h]
0x140013085  mov     ebx, eax
0x140013087  jmp     short loc_1400130BC
0x140013089  mov     rdx, cs:id; id
0x140013090  test    rdx, rdx
0x140013093  jz      short loc_1400130BA
0x140013095  mov     rcx, [rsp+120h+var_F0]; engineHandle
0x14001309a  call    cs:__imp_FwpmFilterDeleteById0
0x1400130a1  nop     dword ptr [rax+rax+00h]
0x1400130a6  test    eax, eax
0x1400130a8  jns     short loc_1400130AF
0x1400130aa  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400130af  mov     cs:id, 0
0x1400130ba  xor     ebx, ebx
0x1400130bc  mov     rcx, [rsp+120h+var_F0]; engineHandle
0x1400130c1  call    cs:__imp_FwpmEngineClose0
0x1400130c8  nop     dword ptr [rax+rax+00h]
0x1400130cd  mov     eax, ebx
0x1400130cf  mov     rcx, [rbp+20h+var_10]
0x1400130d3  xor     rcx, rsp; StackCookie
0x1400130d6  call    __security_check_cookie
0x1400130db  mov     rbx, [rsp+120h+arg_0]
0x1400130e3  add     rsp, 120h
0x1400130ea  pop     rbp
0x1400130eb  retn
```
