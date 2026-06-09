# WinNatAddPacketFilterToWFP

- ea: `0x140011cfc`
- end: `0x1400120b2`
- name: `WinNatAddPacketFilterToWFP`
- size: `950`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000eb50`

## callees

- `0x14000caa0`
- `0x14000e488`
- `0x140011cfc`
- `0x140012674`
- `0x140012910`
- `0x14001ede0`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140011db3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140011db3`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140011d59`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140011d59`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012057`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012057`
- `ntoskrnl!ExAllocatePool2` at `0x140011e02`
- `ntoskrnl!ExAllocatePool2` at `0x140011e02`
- `NETIO!ConvertLengthToIpv4Mask` at `0x140011ee4`
- `NETIO!ConvertLengthToIpv4Mask` at `0x140011f74`
- `NETIO!ConvertLengthToIpv4Mask` at `0x140011ee4`
- `NETIO!ConvertLengthToIpv4Mask` at `0x140011f74`
- `fwpkclnt!FwpmFilterAdd0` at `0x14001203d`
- `fwpkclnt!FwpmFilterAdd0` at `0x14001203d`
- `fwpkclnt!FwpmEngineClose0` at `0x140012071`
- `fwpkclnt!FwpmEngineClose0` at `0x140012071`
- `fwpkclnt!FwpmEngineOpen0` at `0x140011ddc`
- `fwpkclnt!FwpmEngineOpen0` at `0x140011ddc`

## pseudocode

```c
__int64 __fastcall WinNatAddPacketFilterToWFP(__int64 a1)
{
  __int64 v2; // rcx
  int v3; // eax
  char v4; // si
  NTSTATUS v5; // ebx
  __int64 Pool2; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r14
  __int64 v11; // rbx
  unsigned int v12; // r15d
  GUID v13; // xmm0
  __int128 v14; // xmm0
  __int16 v15; // ax
  ULONG v16; // ecx
  ULONG *v17; // rax
  __int128 v18; // xmm0
  __int64 v19; // r12
  __int16 v20; // ax
  ULONG v21; // ecx
  ULONG *v22; // rax
  __int128 v23; // xmm0
  __int64 v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rax
  __int128 v27; // xmm0
  ULONG Mask[2]; // [rsp+30h] [rbp-50h] BYREF
  ULONG v30[2]; // [rsp+38h] [rbp-48h] BYREF
  HANDLE engineHandle; // [rsp+40h] [rbp-40h] BYREF
  __int128 v32; // [rsp+48h] [rbp-38h] BYREF
  char v33; // [rsp+58h] [rbp-28h]
  __int128 v34; // [rsp+60h] [rbp-20h] BYREF
  char v35; // [rsp+70h] [rbp-10h]

  engineHandle = 0;
  v33 = 0;
  *(_QWORD *)v30 = 0;
  v35 = 0;
  *(_QWORD *)Mask = 0;
  v32 = 0;
  v34 = 0;
  ExAcquirePushLockExclusiveEx(&PushLock, 0);
  v3 = dword_1400262F0;
  v4 = 1;
  if ( dword_1400262F0 )
  {
    v5 = 0;
    goto LABEL_7;
  }
  v5 = 0;
  if ( !EnableXlat )
  {
    LOBYTE(v2) = 1;
    v5 = WinNatConfigureFiltersForAddressPool(v2);
    if ( v5 < 0 )
      goto LABEL_7;
    v3 = dword_1400262F0;
  }
  dword_1400262F0 = v3 + 1;
LABEL_7:
  ExReleasePushLockExclusiveEx(&PushLock, 0);
  if ( v5 < 0 )
  {
    v4 = 0;
  }
  else
  {
    v5 = FwpmEngineOpen0(0, 0xAu, 0, 0, &engineHandle);
    if ( v5 >= 0 )
    {
      Pool2 = ExAllocatePool2(64, 320, 1719094871);
      v10 = Pool2;
      if ( Pool2 )
      {
        v11 = Pool2 + 200;
        v12 = 0;
        *(_QWORD *)(Pool2 + 16) = L"Windows NAT forward layer filter";
        *(_QWORD *)(Pool2 + 24) = L"Filters IP packets that require translation in the internal to external direction";
        if ( *(_WORD *)(a1 + 8) == 2 )
          v13 = FWPM_LAYER_IPFORWARD_V4;
        else
          v13 = FWPM_LAYER_IPFORWARD_V6;
        *(GUID *)(Pool2 + 64) = v13;
        if ( *(_WORD *)(a1 + 8) == 2 )
          v14 = WINNAT_WFP_FORWARD_SUBLAYER_IPV4;
        else
          v14 = WINNAT_WFP_FORWARD_SUBLAYER_IPV6;
        *(_DWORD *)(Pool2 + 96) = 4;
        *(_QWORD *)(Pool2 + 104) = a1 + 104;
        *(_OWORD *)(Pool2 + 80) = v14;
        if ( *(_BYTE *)(a1 + 68) )
        {
          *(_DWORD *)(Pool2 + 216) = 0;
          *(GUID *)v11 = FWPM_CONDITION_IP_DESTINATION_ADDRESS;
          v15 = *(_WORD *)(a1 + 8);
          if ( v15 == 2 )
          {
            *(_DWORD *)(v11 + 24) = 256;
            v16 = *(unsigned __int8 *)(a1 + 68);
            Mask[0] = _byteswap_ulong(*(_DWORD *)(a1 + 52));
            ConvertLengthToIpv4Mask(v16, &Mask[1]);
            Mask[1] = _byteswap_ulong(Mask[1]);
            v17 = Mask;
          }
          else
          {
            if ( v15 != 23 )
              MicrosoftTelemetryAssertTriggeredNoArgsKM(v8, v7);
            *(_DWORD *)(v11 + 24) = 257;
            v18 = *(_OWORD *)(a1 + 52);
            v33 = *(_BYTE *)(a1 + 68);
            v17 = (ULONG *)&v32;
            v32 = v18;
          }
          *(_QWORD *)(v11 + 32) = v17;
          v12 = 1;
        }
        if ( *(_BYTE *)(a1 + 48) )
        {
          v19 = 5LL * v12;
          *(GUID *)(v11 + 8 * v19) = FWPM_CONDITION_IP_SOURCE_ADDRESS;
          *(_DWORD *)(v11 + 8 * v19 + 16) = 0;
          v20 = *(_WORD *)(a1 + 8);
          if ( v20 == 2 )
          {
            *(_DWORD *)(v11 + 40LL * v12 + 24) = 256;
            v21 = *(unsigned __int8 *)(a1 + 48);
            v30[0] = _byteswap_ulong(*(_DWORD *)(a1 + 32));
            ConvertLengthToIpv4Mask(v21, &v30[1]);
            v30[1] = _byteswap_ulong(v30[1]);
            v22 = v30;
          }
          else
          {
            if ( v20 != 23 )
              MicrosoftTelemetryAssertTriggeredNoArgsKM(v8, v7);
            *(_DWORD *)(v11 + 40LL * v12 + 24) = 257;
            v23 = *(_OWORD *)(a1 + 32);
            v35 = *(_BYTE *)(a1 + 48);
            v22 = (ULONG *)&v34;
            v34 = v23;
          }
          *(_QWORD *)(v11 + 40LL * v12++ + 32) = v22;
        }
        if ( *(_QWORD *)(a1 + 88) )
        {
          v24 = v12++;
          v25 = 5 * v24;
          *(GUID *)(v11 + 8 * v25) = FWPM_CONDITION_SOURCE_INTERFACE_INDEX;
          *(_DWORD *)(v11 + 8 * v25 + 16) = 0;
          *(_DWORD *)(v11 + 8 * v25 + 24) = 3;
          *(_DWORD *)(v11 + 8 * v25 + 32) = *(_DWORD *)(a1 + 96);
        }
        v26 = 0;
        *(_DWORD *)(v10 + 112) = v12;
        *(_QWORD *)(v10 + 120) = v11;
        *(_DWORD *)(v10 + 128) = 20483;
        if ( *(_WORD *)(a1 + 8) == 2 )
          v26 = 72;
        v27 = **(_OWORD **)((char *)&off_140026008 + v26);
        *(_QWORD *)(v10 + 152) = a1;
        *(_OWORD *)(v10 + 132) = v27;
        v5 = FwpmFilterAdd0(engineHandle, (const FWPM_FILTER0 *)v10, 0, (UINT64 *)(a1 + 112));
        if ( v5 >= 0 )
          v4 = 0;
        ExFreePoolWithTag((PVOID)v10, 0);
      }
      else
      {
        if ( dword_140026104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x20) != 0 )
          McTemplateK0z_EtwWriteTransfer(
            &MICROSOFT_WINNAT_ETW_PROVIDER_Context,
            v7,
            v9,
            L"Filter characteristics buffer allocation failed");
        v5 = -1073741670;
      }
    }
  }
  if ( engineHandle )
    FwpmEngineClose0(engineHandle);
  if ( v4 )
    WinNatDereferenceWFPFilters();
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140011cfc  mov     [rsp-28h+arg_8], rbx
0x140011d01  mov     [rsp-28h+arg_10], rsi
0x140011d06  push    rbp
0x140011d07  push    rdi
0x140011d08  push    r12
0x140011d0a  push    r14
0x140011d0c  push    r15
0x140011d0e  mov     rbp, rsp
0x140011d11  sub     rsp, 80h
0x140011d18  mov     rax, cs:__security_cookie
0x140011d1f  xor     rax, rsp
0x140011d22  mov     [rbp+var_8], rax
0x140011d26  xor     eax, eax
0x140011d28  mov     [rbp+var_40], 0
0x140011d30  xorps   xmm0, xmm0
0x140011d33  mov     [rbp+var_28], al
0x140011d36  mov     rdi, rcx
0x140011d39  mov     qword ptr [rbp+var_48], rax
0x140011d3d  lea     rcx, PushLock
0x140011d44  mov     [rbp+var_10], al
0x140011d47  xor     edx, edx
0x140011d49  mov     qword ptr [rbp+Mask], 0
0x140011d51  movups  [rbp+var_38], xmm0
0x140011d55  movups  [rbp+var_20], xmm0
0x140011d59  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140011d60  nop     dword ptr [rax+rax+00h]
0x140011d65  mov     eax, cs:dword_1400262F0
0x140011d6b  mov     esi, 1
0x140011d70  test    eax, eax
0x140011d72  jz      short loc_140011D78
0x140011d74  xor     ebx, ebx
0x140011d76  jmp     short loc_140011DAA
0x140011d78  cmp     eax, 0FFFFFFFFh
0x140011d7b  jnz     short loc_140011D84
0x140011d7d  mov     ebx, 0C0000095h
0x140011d82  jmp     short loc_140011DAA
0x140011d84  xor     ebx, ebx
0x140011d86  cmp     cs:EnableXlat, ebx
0x140011d8c  jnz     short loc_140011DA2
0x140011d8e  mov     cl, sil
0x140011d91  call    WinNatConfigureFiltersForAddressPool
0x140011d96  mov     ebx, eax
0x140011d98  test    eax, eax
0x140011d9a  js      short loc_140011DAA
0x140011d9c  mov     eax, cs:dword_1400262F0
0x140011da2  add     eax, esi
0x140011da4  mov     cs:dword_1400262F0, eax
0x140011daa  xor     edx, edx
0x140011dac  lea     rcx, PushLock
0x140011db3  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140011dba  nop     dword ptr [rax+rax+00h]
0x140011dbf  test    ebx, ebx
0x140011dc1  js      loc_140012065
0x140011dc7  xor     r9d, r9d; session
0x140011dca  lea     rax, [rbp+var_40]
0x140011dce  xor     r8d, r8d; authIdentity
0x140011dd1  mov     [rsp+80h+engineHandle], rax; engineHandle
0x140011dd6  xor     ecx, ecx; serverName
0x140011dd8  lea     edx, [r9+0Ah]; authnService
0x140011ddc  call    cs:__imp_FwpmEngineOpen0
0x140011de3  nop     dword ptr [rax+rax+00h]
0x140011de8  mov     ebx, eax
0x140011dea  test    eax, eax
0x140011dec  js      loc_140012068
0x140011df2  mov     edx, 140h
0x140011df7  mov     ecx, 40h ; '@'
0x140011dfc  mov     r8d, 66774E57h
0x140011e02  call    cs:__imp_ExAllocatePool2
0x140011e09  nop     dword ptr [rax+rax+00h]
0x140011e0e  mov     r14, rax
0x140011e11  test    rax, rax
0x140011e14  jnz     short loc_140011E44
0x140011e16  cmp     cs:dword_140026104, esi
0x140011e1c  jnz     short loc_140011E3A
0x140011e1e  test    cs:Microsoft_Windows_WinNatEnableBits, 20h
0x140011e25  jz      short loc_140011E3A
0x140011e27  lea     r9, aFilterCharacte; "Filter characteristics buffer allocatio"...
0x140011e2e  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x140011e35  call    McTemplateK0z_EtwWriteTransfer
0x140011e3a  mov     ebx, 0C000009Ah
0x140011e3f  jmp     loc_140012068
0x140011e44  lea     rbx, [rax+0C8h]
0x140011e4b  xor     r15d, r15d
0x140011e4e  lea     rax, aWindowsNatForw_0; "Windows NAT forward layer filter"
0x140011e55  mov     [r14+10h], rax
0x140011e59  lea     rax, aFiltersIpPacke; "Filters IP packets that require transla"...
0x140011e60  mov     [r14+18h], rax
0x140011e64  cmp     word ptr [rdi+8], 2
0x140011e69  jnz     short loc_140011E74
0x140011e6b  movups  xmm0, xmmword ptr cs:FWPM_LAYER_IPFORWARD_V4.Data1
0x140011e72  jmp     short loc_140011E7B
0x140011e74  movups  xmm0, xmmword ptr cs:FWPM_LAYER_IPFORWARD_V6.Data1
0x140011e7b  movdqu  xmmword ptr [r14+40h], xmm0
0x140011e81  cmp     word ptr [rdi+8], 2
0x140011e86  jnz     short loc_140011E91
0x140011e88  movups  xmm0, cs:WINNAT_WFP_FORWARD_SUBLAYER_IPV4
0x140011e8f  jmp     short loc_140011E98
0x140011e91  movups  xmm0, cs:WINNAT_WFP_FORWARD_SUBLAYER_IPV6
0x140011e98  lea     rax, [rdi+68h]
0x140011e9c  mov     dword ptr [r14+60h], 4
0x140011ea4  mov     [r14+68h], rax
0x140011ea8  movdqu  xmmword ptr [r14+50h], xmm0
0x140011eae  cmp     [rdi+44h], r15b
0x140011eb2  jz      short loc_140011F2A
0x140011eb4  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_DESTINATION_ADDRESS.Data1
0x140011ebb  mov     [rbx+10h], r15d
0x140011ebf  movdqu  xmmword ptr [rbx], xmm0
0x140011ec3  movzx   eax, word ptr [rdi+8]
0x140011ec7  cmp     ax, 2
0x140011ecb  jnz     short loc_140011EFE
0x140011ecd  mov     dword ptr [rbx+18h], 100h
0x140011ed4  lea     rdx, [rbp+Mask+4]; Mask
0x140011ed8  mov     eax, [rdi+34h]
0x140011edb  movzx   ecx, byte ptr [rdi+44h]; MaskLength
0x140011edf  bswap   eax
0x140011ee1  mov     [rbp+Mask], eax
0x140011ee4  call    cs:__imp_ConvertLengthToIpv4Mask
0x140011eeb  nop     dword ptr [rax+rax+00h]
0x140011ef0  mov     eax, [rbp+Mask+4]
0x140011ef3  bswap   eax
0x140011ef5  mov     [rbp+Mask+4], eax
0x140011ef8  lea     rax, [rbp+Mask]
0x140011efc  jmp     short loc_140011F23
0x140011efe  cmp     ax, 17h
0x140011f02  jz      short loc_140011F09
0x140011f04  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140011f09  mov     dword ptr [rbx+18h], 101h
0x140011f10  mov     al, [rdi+44h]
0x140011f13  movups  xmm0, xmmword ptr [rdi+34h]
0x140011f17  mov     [rbp+var_28], al
0x140011f1a  lea     rax, [rbp+var_38]
0x140011f1e  movdqu  [rbp+var_38], xmm0
0x140011f23  mov     [rbx+20h], rax
0x140011f27  mov     r15d, esi
0x140011f2a  cmp     byte ptr [rdi+30h], 0
0x140011f2e  jz      loc_140011FBD
0x140011f34  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_SOURCE_ADDRESS.Data1
0x140011f3b  mov     eax, r15d
0x140011f3e  lea     r12, [rax+rax*4]
0x140011f42  movdqu  xmmword ptr [rbx+r12*8], xmm0
0x140011f48  mov     dword ptr [rbx+r12*8+10h], 0
0x140011f51  movzx   eax, word ptr [rdi+8]
0x140011f55  cmp     ax, 2
0x140011f59  jnz     short loc_140011F8E
0x140011f5b  mov     dword ptr [rbx+r12*8+18h], 100h
0x140011f64  lea     rdx, [rbp+var_48+4]; Mask
0x140011f68  mov     eax, [rdi+20h]
0x140011f6b  movzx   ecx, byte ptr [rdi+30h]; MaskLength
0x140011f6f  bswap   eax
0x140011f71  mov     [rbp+var_48], eax
0x140011f74  call    cs:__imp_ConvertLengthToIpv4Mask
0x140011f7b  nop     dword ptr [rax+rax+00h]
0x140011f80  mov     eax, [rbp+var_48+4]
0x140011f83  bswap   eax
0x140011f85  mov     [rbp+var_48+4], eax
0x140011f88  lea     rax, [rbp+var_48]
0x140011f8c  jmp     short loc_140011FB5
0x140011f8e  cmp     ax, 17h
0x140011f92  jz      short loc_140011F99
0x140011f94  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140011f99  mov     dword ptr [rbx+r12*8+18h], 101h
0x140011fa2  mov     al, [rdi+30h]
0x140011fa5  movups  xmm0, xmmword ptr [rdi+20h]
0x140011fa9  mov     [rbp+var_10], al
0x140011fac  lea     rax, [rbp+var_20]
0x140011fb0  movdqu  [rbp+var_20], xmm0
0x140011fb5  mov     [rbx+r12*8+20h], rax
0x140011fba  add     r15d, esi
0x140011fbd  cmp     qword ptr [rdi+58h], 0
0x140011fc2  jz      short loc_140011FF1
0x140011fc4  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_SOURCE_INTERFACE_INDEX.Data1
0x140011fcb  mov     eax, r15d
0x140011fce  add     r15d, esi
0x140011fd1  lea     rcx, [rax+rax*4]
0x140011fd5  movdqu  xmmword ptr [rbx+rcx*8], xmm0
0x140011fda  mov     dword ptr [rbx+rcx*8+10h], 0
0x140011fe2  mov     dword ptr [rbx+rcx*8+18h], 3
0x140011fea  mov     eax, [rdi+60h]
0x140011fed  mov     [rbx+rcx*8+20h], eax
0x140011ff1  xor     eax, eax
0x140011ff3  mov     [r14+70h], r15d
0x140011ff7  mov     [r14+78h], rbx
0x140011ffb  lea     r9, [rdi+70h]; id
0x140011fff  mov     dword ptr [r14+80h], 5003h
0x14001200a  mov     rdx, r14; filter
0x14001200d  cmp     word ptr [rdi+8], 2
0x140012012  lea     ecx, [rax+48h]
0x140012015  cmovz   eax, ecx
0x140012018  lea     rcx, off_140026008
0x14001201f  xor     r8d, r8d; sd
0x140012022  mov     rax, [rax+rcx]
0x140012026  movups  xmm0, xmmword ptr [rax]
0x140012029  mov     [r14+98h], rdi
0x140012030  movdqu  xmmword ptr [r14+84h], xmm0
0x140012039  mov     rcx, [rbp+var_40]; engineHandle
0x14001203d  call    cs:__imp_FwpmFilterAdd0
0x140012044  nop     dword ptr [rax+rax+00h]
0x140012049  mov     ebx, eax
0x14001204b  test    eax, eax
0x14001204d  js      short loc_140012052
0x14001204f  xor     sil, sil
0x140012052  xor     edx, edx; Tag
0x140012054  mov     rcx, r14; P
0x140012057  call    cs:__imp_ExFreePoolWithTag
0x14001205e  nop     dword ptr [rax+rax+00h]
0x140012063  jmp     short loc_140012068
0x140012065  xor     sil, sil
0x140012068  mov     rcx, [rbp+var_40]; engineHandle
0x14001206c  test    rcx, rcx
0x14001206f  jz      short loc_14001207D
0x140012071  call    cs:__imp_FwpmEngineClose0
0x140012078  nop     dword ptr [rax+rax+00h]
0x14001207d  test    sil, sil
0x140012080  jz      short loc_140012087
0x140012082  call    WinNatDereferenceWFPFilters
0x140012087  mov     eax, ebx
0x140012089  mov     rcx, [rbp+var_8]
0x14001208d  xor     rcx, rsp; StackCookie
0x140012090  call    __security_check_cookie
0x140012095  lea     r11, [rsp+80h+var_s0]
0x14001209d  mov     rbx, [r11+38h]
0x1400120a1  mov     rsi, [r11+40h]
0x1400120a5  mov     rsp, r11
0x1400120a8  pop     r15
0x1400120aa  pop     r14
0x1400120ac  pop     r12
0x1400120ae  pop     rdi
0x1400120af  pop     rbp
0x1400120b0  retn
```
