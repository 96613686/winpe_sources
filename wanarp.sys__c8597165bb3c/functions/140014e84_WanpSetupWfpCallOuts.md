# WanpSetupWfpCallOuts

- ea: `0x140014e84`
- end: `0x1400150f0`
- name: `WanpSetupWfpCallOuts`
- size: `620`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140011618`

## callees

- `0x1400050b0`
- `0x1400054c0`
- `0x140014ddc`
- `0x140014e84`

## import_xrefs

- `fwpkclnt!FwpiCalloutRegisterAndAddWithoutDevice0` at `0x140014f6c`
- `fwpkclnt!FwpiCalloutRegisterAndAddWithoutDevice0` at `0x140014fd8`
- `fwpkclnt!FwpiCalloutRegisterAndAddWithoutDevice0` at `0x140015052`
- `fwpkclnt!FwpiCalloutRegisterAndAddWithoutDevice0` at `0x1400150ba`
- `fwpkclnt!FwpiCalloutRegisterAndAddWithoutDevice0` at `0x140014f6c`
- `fwpkclnt!FwpiCalloutRegisterAndAddWithoutDevice0` at `0x140014fd8`
- `fwpkclnt!FwpiCalloutRegisterAndAddWithoutDevice0` at `0x140015052`
- `fwpkclnt!FwpiCalloutRegisterAndAddWithoutDevice0` at `0x1400150ba`
- `fwpkclnt!FwpmEngineOpen0` at `0x140014eeb`
- `fwpkclnt!FwpmEngineOpen0` at `0x140014eeb`

## pseudocode

```c
__int64 WanpSetupWfpCallOuts()
{
  NTSTATUS v0; // ebx
  __int128 v2; // [rsp+30h] [rbp-69h] BYREF
  __int128 v3; // [rsp+40h] [rbp-59h]
  __int128 v4; // [rsp+50h] [rbp-49h]
  _OWORD v5[6]; // [rsp+60h] [rbp-39h] BYREF

  v0 = 0;
  if ( !engineHandle )
  {
    v2 = 0;
    v3 = 0;
    v4 = 0;
    memset(v5, 0, 0x58u);
    v0 = FwpmEngineOpen0(0, 0xAu, 0, 0, &engineHandle);
    if ( v0 >= 0 )
    {
      LODWORD(v3) = 32;
      v2 = xmmword_140007668;
      v5[0] = xmmword_140007668;
      *((_QWORD *)&v3 + 1) = WanIpv4ClassifyDemandDialCallOut;
      *(_QWORD *)&v4 = WanIpv4NotifyDemandDialCallOut;
      *(_QWORD *)&v5[1] = L"WANARP Ipv4 Send Callout";
      v5[4] = FWPM_LAYER_OUTBOUND_IPPACKET_V4;
      *((_QWORD *)&v5[1] + 1) = L"WANARP Callout for Demand Dial";
      v0 = FwpiCalloutRegisterAndAddWithoutDevice0(engineHandle, &v2, v5, 0, 0);
      if ( v0 < 0 )
        goto LABEL_7;
      *((_QWORD *)&v3 + 1) = WanIpv4ClassifyDemandDialCallOut;
      v2 = xmmword_140007688;
      *(_QWORD *)&v4 = WanIpv4NotifyDemandDialCallOut;
      v5[0] = xmmword_140007688;
      LODWORD(v3) = 32;
      *(_QWORD *)&v5[1] = L"WANARP Ipv4 Forward Callout";
      *((_QWORD *)&v5[1] + 1) = L"WANARP Callout for Demand Dial";
      v5[4] = FWPM_LAYER_IPFORWARD_V4;
      v0 = FwpiCalloutRegisterAndAddWithoutDevice0(engineHandle, &v2, v5, 0, 0);
      if ( v0 < 0 )
        goto LABEL_7;
      LODWORD(v3) = 32;
      v2 = xmmword_140007658;
      v5[0] = xmmword_140007658;
      *((_QWORD *)&v3 + 1) = WanIpv4ClassifyDemandDialCallOut;
      *(_QWORD *)&v4 = WanIpv4NotifyDemandDialCallOut;
      *(_QWORD *)&v5[1] = L"WANARP Ipv6 Send Callout";
      v5[4] = FWPM_LAYER_OUTBOUND_IPPACKET_V6;
      *((_QWORD *)&v5[1] + 1) = L"WANARP Callout for Demand Dial";
      v0 = FwpiCalloutRegisterAndAddWithoutDevice0(engineHandle, &v2, v5, 0, 0);
      if ( v0 < 0 )
        goto LABEL_7;
      *((_QWORD *)&v3 + 1) = WanIpv4ClassifyDemandDialCallOut;
      v2 = xmmword_140007678;
      *(_QWORD *)&v4 = WanIpv4NotifyDemandDialCallOut;
      v5[0] = xmmword_140007678;
      LODWORD(v3) = 32;
      *(_QWORD *)&v5[1] = L"WANARP Ipv6 Forward Callout";
      *((_QWORD *)&v5[1] + 1) = L"WANARP Callout for Demand Dial";
      v5[4] = FWPM_LAYER_IPFORWARD_V6;
      v0 = FwpiCalloutRegisterAndAddWithoutDevice0(engineHandle, &v2, v5, 0, 0);
      if ( v0 < 0 )
LABEL_7:
        WanpRemoveWfpCallOuts();
    }
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x140014e84  push    rbp
0x140014e86  push    rbx
0x140014e87  push    r12
0x140014e89  push    r14
0x140014e8b  push    r15
0x140014e8d  lea     rbp, [rsp-37h]
0x140014e92  sub     rsp, 0D0h
0x140014e99  mov     rax, cs:__security_cookie
0x140014ea0  xor     rax, rsp
0x140014ea3  mov     [rbp+57h+var_30], rax
0x140014ea7  xor     ebx, ebx
0x140014ea9  cmp     cs:engineHandle, rbx
0x140014eb0  jnz     loc_1400150D1
0x140014eb6  xorps   xmm0, xmm0
0x140014eb9  lea     r8d, [rbx+58h]; Size
0x140014ebd  xor     edx, edx; Val
0x140014ebf  lea     rcx, [rbp+57h+var_90]; void *
0x140014ec3  movups  [rbp+57h+var_C0], xmm0
0x140014ec7  movups  [rbp+57h+var_B0], xmm0
0x140014ecb  movups  [rbp+57h+var_A0], xmm0
0x140014ecf  call    memset
0x140014ed4  lea     rax, engineHandle
0x140014edb  xor     r9d, r9d; session
0x140014ede  xor     r8d, r8d; authIdentity
0x140014ee1  mov     [rsp+0F0h+engineHandle], rax; engineHandle
0x140014ee6  lea     edx, [rbx+0Ah]; authnService
0x140014ee9  xor     ecx, ecx; serverName
0x140014eeb  call    cs:__imp_FwpmEngineOpen0
0x140014ef2  nop     dword ptr [rax+rax+00h]
0x140014ef7  mov     ebx, eax
0x140014ef9  test    eax, eax
0x140014efb  js      loc_1400150D1
0x140014f01  movups  xmm0, cs:xmmword_140007668
0x140014f08  mov     rcx, cs:engineHandle
0x140014f0f  lea     rax, aWanarpIpv4Send; "WANARP Ipv4 Send Callout"
0x140014f16  lea     r15, WanIpv4ClassifyDemandDialCallOut
0x140014f1d  mov     dword ptr [rbp+57h+var_B0], 20h ; ' '
0x140014f24  movdqu  [rbp+57h+var_C0], xmm0
0x140014f29  lea     r12, WanIpv4NotifyDemandDialCallOut
0x140014f30  xor     r9d, r9d
0x140014f33  movdqu  [rbp+57h+var_90], xmm0
0x140014f38  lea     r14, aWanarpCalloutF; "WANARP Callout for Demand Dial"
0x140014f3f  mov     qword ptr [rbp+57h+var_B0+8], r15
0x140014f43  movups  xmm0, xmmword ptr cs:FWPM_LAYER_OUTBOUND_IPPACKET_V4.Data1
0x140014f4a  lea     r8, [rbp+57h+var_90]
0x140014f4e  mov     qword ptr [rbp+57h+var_A0], r12
0x140014f52  lea     rdx, [rbp+57h+var_C0]
0x140014f56  mov     [rbp+57h+var_80], rax
0x140014f5a  movdqu  [rbp+57h+var_50], xmm0
0x140014f5f  mov     [rbp+57h+var_78], r14
0x140014f63  mov     [rsp+0F0h+engineHandle], 0
0x140014f6c  call    cs:__imp_FwpiCalloutRegisterAndAddWithoutDevice0
0x140014f73  nop     dword ptr [rax+rax+00h]
0x140014f78  mov     ebx, eax
0x140014f7a  test    eax, eax
0x140014f7c  js      loc_1400150CC
0x140014f82  movups  xmm0, cs:xmmword_140007688
0x140014f89  mov     rcx, cs:engineHandle
0x140014f90  lea     rax, aWanarpIpv4Forw; "WANARP Ipv4 Forward Callout"
0x140014f97  xor     r9d, r9d
0x140014f9a  mov     qword ptr [rbp+57h+var_B0+8], r15
0x140014f9e  movdqu  [rbp+57h+var_C0], xmm0
0x140014fa3  lea     r8, [rbp+57h+var_90]
0x140014fa7  mov     qword ptr [rbp+57h+var_A0], r12
0x140014fab  movdqu  [rbp+57h+var_90], xmm0
0x140014fb0  lea     rdx, [rbp+57h+var_C0]
0x140014fb4  mov     dword ptr [rbp+57h+var_B0], 20h ; ' '
0x140014fbb  movups  xmm0, xmmword ptr cs:FWPM_LAYER_IPFORWARD_V4.Data1
0x140014fc2  mov     [rbp+57h+var_80], rax
0x140014fc6  mov     [rbp+57h+var_78], r14
0x140014fca  movdqu  [rbp+57h+var_50], xmm0
0x140014fcf  mov     [rsp+0F0h+engineHandle], 0
0x140014fd8  call    cs:__imp_FwpiCalloutRegisterAndAddWithoutDevice0
0x140014fdf  nop     dword ptr [rax+rax+00h]
0x140014fe4  mov     ebx, eax
0x140014fe6  test    eax, eax
0x140014fe8  js      loc_1400150CC
0x140014fee  movups  xmm0, cs:xmmword_140007658
0x140014ff5  mov     rcx, cs:engineHandle
0x140014ffc  lea     rax, aWanarpIpv6Send; "WANARP Ipv6 Send Callout"
0x140015003  lea     r15, WanIpv4ClassifyDemandDialCallOut
0x14001500a  mov     dword ptr [rbp+57h+var_B0], 20h ; ' '
0x140015011  movdqu  [rbp+57h+var_C0], xmm0
0x140015016  lea     r12, WanIpv4NotifyDemandDialCallOut
0x14001501d  xor     r9d, r9d
0x140015020  movdqu  [rbp+57h+var_90], xmm0
0x140015025  lea     r8, [rbp+57h+var_90]
0x140015029  mov     qword ptr [rbp+57h+var_B0+8], r15
0x14001502d  movups  xmm0, xmmword ptr cs:FWPM_LAYER_OUTBOUND_IPPACKET_V6.Data1
0x140015034  lea     rdx, [rbp+57h+var_C0]
0x140015038  mov     qword ptr [rbp+57h+var_A0], r12
0x14001503c  mov     [rbp+57h+var_80], rax
0x140015040  movdqu  [rbp+57h+var_50], xmm0
0x140015045  mov     [rbp+57h+var_78], r14
0x140015049  mov     [rsp+0F0h+engineHandle], 0
0x140015052  call    cs:__imp_FwpiCalloutRegisterAndAddWithoutDevice0
0x140015059  nop     dword ptr [rax+rax+00h]
0x14001505e  mov     ebx, eax
0x140015060  test    eax, eax
0x140015062  js      short loc_1400150CC
0x140015064  movups  xmm0, cs:xmmword_140007678
0x14001506b  mov     rcx, cs:engineHandle
0x140015072  lea     rax, aWanarpIpv6Forw; "WANARP Ipv6 Forward Callout"
0x140015079  xor     r9d, r9d
0x14001507c  mov     qword ptr [rbp+57h+var_B0+8], r15
0x140015080  movdqu  [rbp+57h+var_C0], xmm0
0x140015085  lea     r8, [rbp+57h+var_90]
0x140015089  mov     qword ptr [rbp+57h+var_A0], r12
0x14001508d  movdqu  [rbp+57h+var_90], xmm0
0x140015092  lea     rdx, [rbp+57h+var_C0]
0x140015096  mov     dword ptr [rbp+57h+var_B0], 20h ; ' '
0x14001509d  movups  xmm0, xmmword ptr cs:FWPM_LAYER_IPFORWARD_V6.Data1
0x1400150a4  mov     [rbp+57h+var_80], rax
0x1400150a8  mov     [rbp+57h+var_78], r14
0x1400150ac  movdqu  [rbp+57h+var_50], xmm0
0x1400150b1  mov     [rsp+0F0h+engineHandle], 0
0x1400150ba  call    cs:__imp_FwpiCalloutRegisterAndAddWithoutDevice0
0x1400150c1  nop     dword ptr [rax+rax+00h]
0x1400150c6  mov     ebx, eax
0x1400150c8  test    eax, eax
0x1400150ca  jns     short loc_1400150D1
0x1400150cc  call    WanpRemoveWfpCallOuts
0x1400150d1  mov     eax, ebx
0x1400150d3  mov     rcx, [rbp+57h+var_30]
0x1400150d7  xor     rcx, rsp; StackCookie
0x1400150da  call    __security_check_cookie
0x1400150df  add     rsp, 0D0h
0x1400150e6  pop     r15
0x1400150e8  pop     r14
0x1400150ea  pop     r12
0x1400150ec  pop     rbx
0x1400150ed  pop     rbp
0x1400150ee  retn
```
