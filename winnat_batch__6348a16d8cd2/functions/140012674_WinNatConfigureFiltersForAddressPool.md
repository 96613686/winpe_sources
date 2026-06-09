# WinNatConfigureFiltersForAddressPool

- ea: `0x140012674`
- end: `0x1400127ad`
- name: `WinNatConfigureFiltersForAddressPool`
- size: `313`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140011cfc`
- `0x140012910`

## callees

- `0x14000caa0`
- `0x140012674`
- `0x14001ede0`
- `0x14001f440`

## import_xrefs

- `fwpkclnt!FwpmFilterDeleteById0` at `0x14001275a`
- `fwpkclnt!FwpmFilterDeleteById0` at `0x14001275a`
- `fwpkclnt!FwpmFilterAdd0` at `0x140012739`
- `fwpkclnt!FwpmFilterAdd0` at `0x140012739`
- `fwpkclnt!FwpmEngineClose0` at `0x140012781`
- `fwpkclnt!FwpmEngineClose0` at `0x140012781`
- `fwpkclnt!FwpmEngineOpen0` at `0x1400126c7`
- `fwpkclnt!FwpmEngineOpen0` at `0x1400126c7`

## pseudocode

```c
NTSTATUS __fastcall WinNatConfigureFiltersForAddressPool(char a1)
{
  NTSTATUS result; // eax
  NTSTATUS v3; // ebx
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
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
      filter.action.4 = *(union FWPM_ACTION0_::$6EA882394A24E7F0D0D0A8FACB4240B6 *)off_140026098;
      v3 = FwpmFilterAdd0(engineHandle, &filter, 0, &id);
    }
    else
    {
      if ( id )
      {
        if ( FwpmFilterDeleteById0(engineHandle, id) < 0 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v5, v4, v6, v7);
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
0x140012674  mov     [rsp-8+arg_0], rbx
0x140012679  push    rbp
0x14001267a  lea     rbp, [rsp-20h]
0x14001267f  sub     rsp, 120h
0x140012686  mov     rax, cs:__security_cookie
0x14001268d  xor     rax, rsp
0x140012690  mov     [rbp+20h+var_10], rax
0x140012694  mov     bl, cl
0x140012696  mov     [rsp+120h+var_F0], 0
0x14001269f  lea     rcx, [rsp+120h+filter]; void *
0x1400126a4  xor     edx, edx; Val
0x1400126a6  mov     r8d, 0C8h; Size
0x1400126ac  call    memset
0x1400126b1  xor     r9d, r9d; session
0x1400126b4  lea     rax, [rsp+120h+var_F0]
0x1400126b9  xor     r8d, r8d; authIdentity
0x1400126bc  mov     [rsp+120h+engineHandle], rax; engineHandle
0x1400126c1  xor     ecx, ecx; serverName
0x1400126c3  lea     edx, [r9+0Ah]; authnService
0x1400126c7  call    cs:__imp_FwpmEngineOpen0
0x1400126ce  nop     dword ptr [rax+rax+00h]
0x1400126d3  test    eax, eax
0x1400126d5  js      loc_14001278F
0x1400126db  test    bl, bl
0x1400126dd  jz      short loc_140012749
0x1400126df  movups  xmm0, xmmword ptr cs:FWPM_LAYER_INBOUND_IPPACKET_V4.Data1
0x1400126e6  mov     rcx, [rsp+120h+var_F0]; engineHandle
0x1400126eb  lea     rax, aWindowsNatIpLa; "Windows NAT IP layer filter"
0x1400126f2  movups  xmm1, cs:WINNAT_WFP_INBOUND_IP_SUBLAYER_IPV4
0x1400126f9  mov     [rsp+120h+filter.displayData.name], rax
0x1400126fe  lea     r9, id; id
0x140012705  lea     rax, aFiltersIpPacke_0; "Filters IP packets that require transla"...
0x14001270c  mov     [rbp+20h+filter.action.type], 5003h
0x140012713  mov     [rsp+120h+filter.displayData.description], rax
0x140012718  lea     rdx, [rsp+120h+filter]; filter
0x14001271d  mov     rax, cs:off_140026098
0x140012724  xor     r8d, r8d; sd
0x140012727  movdqu  xmmword ptr [rbp+20h+filter.layerKey.Data1], xmm0
0x14001272c  movdqu  xmmword ptr [rbp+20h+filter.subLayerKey.Data1], xmm1
0x140012731  movups  xmm0, xmmword ptr [rax]
0x140012734  movdqu  xmmword ptr [rbp+20h+filter.action.4], xmm0
0x140012739  call    cs:__imp_FwpmFilterAdd0
0x140012740  nop     dword ptr [rax+rax+00h]
0x140012745  mov     ebx, eax
0x140012747  jmp     short loc_14001277C
0x140012749  mov     rdx, cs:id; id
0x140012750  test    rdx, rdx
0x140012753  jz      short loc_14001277A
0x140012755  mov     rcx, [rsp+120h+var_F0]; engineHandle
0x14001275a  call    cs:__imp_FwpmFilterDeleteById0
0x140012761  nop     dword ptr [rax+rax+00h]
0x140012766  test    eax, eax
0x140012768  jns     short loc_14001276F
0x14001276a  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001276f  mov     cs:id, 0
0x14001277a  xor     ebx, ebx
0x14001277c  mov     rcx, [rsp+120h+var_F0]; engineHandle
0x140012781  call    cs:__imp_FwpmEngineClose0
0x140012788  nop     dword ptr [rax+rax+00h]
0x14001278d  mov     eax, ebx
0x14001278f  mov     rcx, [rbp+20h+var_10]
0x140012793  xor     rcx, rsp; StackCookie
0x140012796  call    __security_check_cookie
0x14001279b  mov     rbx, [rsp+120h+arg_0]
0x1400127a3  add     rsp, 120h
0x1400127aa  pop     rbp
0x1400127ab  retn
```
