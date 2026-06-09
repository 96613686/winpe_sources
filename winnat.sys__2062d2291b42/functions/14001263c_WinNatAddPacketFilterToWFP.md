# WinNatAddPacketFilterToWFP

- ea: `0x14001263c`
- end: `0x1400129f2`
- name: `WinNatAddPacketFilterToWFP`
- size: `950`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000eb80`

## callees

- `0x14000caa0`
- `0x14000e4b0`
- `0x14001263c`
- `0x140012fb4`
- `0x140013250`
- `0x14001f320`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400126f3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400126f3`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140012699`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140012699`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012997`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012997`
- `ntoskrnl!ExAllocatePool2` at `0x140012742`
- `ntoskrnl!ExAllocatePool2` at `0x140012742`
- `NETIO!ConvertLengthToIpv4Mask` at `0x140012824`
- `NETIO!ConvertLengthToIpv4Mask` at `0x1400128b4`
- `NETIO!ConvertLengthToIpv4Mask` at `0x140012824`
- `NETIO!ConvertLengthToIpv4Mask` at `0x1400128b4`
- `fwpkclnt!FwpmFilterAdd0` at `0x14001297d`
- `fwpkclnt!FwpmFilterAdd0` at `0x14001297d`
- `fwpkclnt!FwpmEngineClose0` at `0x1400129b1`
- `fwpkclnt!FwpmEngineClose0` at `0x1400129b1`
- `fwpkclnt!FwpmEngineOpen0` at `0x14001271c`
- `fwpkclnt!FwpmEngineOpen0` at `0x14001271c`

## pseudocode

```c
__int64 __fastcall WinNatAddPacketFilterToWFP(__int64 a1)
{
  int v2; // eax
  char v3; // si
  NTSTATUS v4; // ebx
  __int64 Pool2; // rax
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r14
  __int64 v10; // rbx
  unsigned int v11; // r15d
  GUID v12; // xmm0
  __int128 v13; // xmm0
  __int16 v14; // ax
  ULONG v15; // ecx
  ULONG *v16; // rax
  __int128 v17; // xmm0
  __int64 v18; // r12
  __int16 v19; // ax
  ULONG v20; // ecx
  ULONG *v21; // rax
  __int128 v22; // xmm0
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rax
  __int128 v26; // xmm0
  ULONG Mask[2]; // [rsp+30h] [rbp-50h] BYREF
  ULONG v29[2]; // [rsp+38h] [rbp-48h] BYREF
  HANDLE engineHandle; // [rsp+40h] [rbp-40h] BYREF
  __int128 v31; // [rsp+48h] [rbp-38h] BYREF
  char v32; // [rsp+58h] [rbp-28h]
  __int128 v33; // [rsp+60h] [rbp-20h] BYREF
  char v34; // [rsp+70h] [rbp-10h]

  engineHandle = 0;
  v32 = 0;
  *(_QWORD *)v29 = 0;
  v34 = 0;
  *(_QWORD *)Mask = 0;
  v31 = 0;
  v33 = 0;
  ExAcquirePushLockExclusiveEx(&PushLock, 0);
  v2 = dword_1400272F0;
  v3 = 1;
  if ( dword_1400272F0 )
  {
    v4 = 0;
    goto LABEL_7;
  }
  v4 = 0;
  if ( !EnableXlat )
  {
    v4 = WinNatConfigureFiltersForAddressPool(1);
    if ( v4 < 0 )
      goto LABEL_7;
    v2 = dword_1400272F0;
  }
  dword_1400272F0 = v2 + 1;
LABEL_7:
  ExReleasePushLockExclusiveEx(&PushLock, 0);
  if ( v4 < 0 )
  {
    v3 = 0;
  }
  else
  {
    v4 = FwpmEngineOpen0(0, 0xAu, 0, 0, &engineHandle);
    if ( v4 >= 0 )
    {
      Pool2 = ExAllocatePool2(64, 320, 1719094871);
      v9 = Pool2;
      if ( Pool2 )
      {
        v10 = Pool2 + 200;
        v11 = 0;
        *(_QWORD *)(Pool2 + 16) = L"Windows NAT forward layer filter";
        *(_QWORD *)(Pool2 + 24) = L"Filters IP packets that require translation in the internal to external direction";
        if ( *(_WORD *)(a1 + 8) == 2 )
          v12 = FWPM_LAYER_IPFORWARD_V4;
        else
          v12 = FWPM_LAYER_IPFORWARD_V6;
        *(GUID *)(Pool2 + 64) = v12;
        if ( *(_WORD *)(a1 + 8) == 2 )
          v13 = WINNAT_WFP_FORWARD_SUBLAYER_IPV4;
        else
          v13 = WINNAT_WFP_FORWARD_SUBLAYER_IPV6;
        *(_DWORD *)(Pool2 + 96) = 4;
        *(_QWORD *)(Pool2 + 104) = a1 + 104;
        *(_OWORD *)(Pool2 + 80) = v13;
        if ( *(_BYTE *)(a1 + 68) )
        {
          *(_DWORD *)(Pool2 + 216) = 0;
          *(GUID *)v10 = FWPM_CONDITION_IP_DESTINATION_ADDRESS;
          v14 = *(_WORD *)(a1 + 8);
          if ( v14 == 2 )
          {
            *(_DWORD *)(v10 + 24) = 256;
            v15 = *(unsigned __int8 *)(a1 + 68);
            Mask[0] = _byteswap_ulong(*(_DWORD *)(a1 + 52));
            ConvertLengthToIpv4Mask(v15, &Mask[1]);
            Mask[1] = _byteswap_ulong(Mask[1]);
            v16 = Mask;
          }
          else
          {
            if ( v14 != 23 )
              MicrosoftTelemetryAssertTriggeredNoArgsKM(v7, v6, v8);
            *(_DWORD *)(v10 + 24) = 257;
            v17 = *(_OWORD *)(a1 + 52);
            v32 = *(_BYTE *)(a1 + 68);
            v16 = (ULONG *)&v31;
            v31 = v17;
          }
          *(_QWORD *)(v10 + 32) = v16;
          v11 = 1;
        }
        if ( *(_BYTE *)(a1 + 48) )
        {
          v18 = 5LL * v11;
          *(GUID *)(v10 + 8 * v18) = FWPM_CONDITION_IP_SOURCE_ADDRESS;
          *(_DWORD *)(v10 + 8 * v18 + 16) = 0;
          v19 = *(_WORD *)(a1 + 8);
          if ( v19 == 2 )
          {
            *(_DWORD *)(v10 + 40LL * v11 + 24) = 256;
            v20 = *(unsigned __int8 *)(a1 + 48);
            v29[0] = _byteswap_ulong(*(_DWORD *)(a1 + 32));
            ConvertLengthToIpv4Mask(v20, &v29[1]);
            v29[1] = _byteswap_ulong(v29[1]);
            v21 = v29;
          }
          else
          {
            if ( v19 != 23 )
              MicrosoftTelemetryAssertTriggeredNoArgsKM(v7, v6, v8);
            *(_DWORD *)(v10 + 40LL * v11 + 24) = 257;
            v22 = *(_OWORD *)(a1 + 32);
            v34 = *(_BYTE *)(a1 + 48);
            v21 = (ULONG *)&v33;
            v33 = v22;
          }
          *(_QWORD *)(v10 + 40LL * v11++ + 32) = v21;
        }
        if ( *(_QWORD *)(a1 + 88) )
        {
          v23 = v11++;
          v24 = 5 * v23;
          *(GUID *)(v10 + 8 * v24) = FWPM_CONDITION_SOURCE_INTERFACE_INDEX;
          *(_DWORD *)(v10 + 8 * v24 + 16) = 0;
          *(_DWORD *)(v10 + 8 * v24 + 24) = 3;
          *(_DWORD *)(v10 + 8 * v24 + 32) = *(_DWORD *)(a1 + 96);
        }
        v25 = 0;
        *(_DWORD *)(v9 + 112) = v11;
        *(_QWORD *)(v9 + 120) = v10;
        *(_DWORD *)(v9 + 128) = 20483;
        if ( *(_WORD *)(a1 + 8) == 2 )
          v25 = 72;
        v26 = **(_OWORD **)((char *)&off_140027008 + v25);
        *(_QWORD *)(v9 + 152) = a1;
        *(_OWORD *)(v9 + 132) = v26;
        v4 = FwpmFilterAdd0(engineHandle, (const FWPM_FILTER0 *)v9, 0, (UINT64 *)(a1 + 112));
        if ( v4 >= 0 )
          v3 = 0;
        ExFreePoolWithTag((PVOID)v9, 0);
      }
      else
      {
        if ( dword_140027104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x20) != 0 )
          McTemplateK0z_EtwWriteTransfer(
            &MICROSOFT_WINNAT_ETW_PROVIDER_Context,
            v6,
            v8,
            L"Filter characteristics buffer allocation failed");
        v4 = -1073741670;
      }
    }
  }
  if ( engineHandle )
    FwpmEngineClose0(engineHandle);
  if ( v3 )
    WinNatDereferenceWFPFilters();
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14001263c  mov     [rsp-28h+arg_8], rbx
0x140012641  mov     [rsp-28h+arg_10], rsi
0x140012646  push    rbp
0x140012647  push    rdi
0x140012648  push    r12
0x14001264a  push    r14
0x14001264c  push    r15
0x14001264e  mov     rbp, rsp
0x140012651  sub     rsp, 80h
0x140012658  mov     rax, cs:__security_cookie
0x14001265f  xor     rax, rsp
0x140012662  mov     [rbp+var_8], rax
0x140012666  xor     eax, eax
0x140012668  mov     [rbp+var_40], 0
0x140012670  xorps   xmm0, xmm0
0x140012673  mov     [rbp+var_28], al
0x140012676  mov     rdi, rcx
0x140012679  mov     qword ptr [rbp+var_48], rax
0x14001267d  lea     rcx, PushLock
0x140012684  mov     [rbp+var_10], al
0x140012687  xor     edx, edx
0x140012689  mov     qword ptr [rbp+Mask], 0
0x140012691  movups  [rbp+var_38], xmm0
0x140012695  movups  [rbp+var_20], xmm0
0x140012699  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400126a0  nop     dword ptr [rax+rax+00h]
0x1400126a5  mov     eax, cs:dword_1400272F0
0x1400126ab  mov     esi, 1
0x1400126b0  test    eax, eax
0x1400126b2  jz      short loc_1400126B8
0x1400126b4  xor     ebx, ebx
0x1400126b6  jmp     short loc_1400126EA
0x1400126b8  cmp     eax, 0FFFFFFFFh
0x1400126bb  jnz     short loc_1400126C4
0x1400126bd  mov     ebx, 0C0000095h
0x1400126c2  jmp     short loc_1400126EA
0x1400126c4  xor     ebx, ebx
0x1400126c6  cmp     cs:EnableXlat, ebx
0x1400126cc  jnz     short loc_1400126E2
0x1400126ce  mov     cl, sil
0x1400126d1  call    WinNatConfigureFiltersForAddressPool
0x1400126d6  mov     ebx, eax
0x1400126d8  test    eax, eax
0x1400126da  js      short loc_1400126EA
0x1400126dc  mov     eax, cs:dword_1400272F0
0x1400126e2  add     eax, esi
0x1400126e4  mov     cs:dword_1400272F0, eax
0x1400126ea  xor     edx, edx
0x1400126ec  lea     rcx, PushLock
0x1400126f3  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400126fa  nop     dword ptr [rax+rax+00h]
0x1400126ff  test    ebx, ebx
0x140012701  js      loc_1400129A5
0x140012707  xor     r9d, r9d; session
0x14001270a  lea     rax, [rbp+var_40]
0x14001270e  xor     r8d, r8d; authIdentity
0x140012711  mov     [rsp+80h+engineHandle], rax; engineHandle
0x140012716  xor     ecx, ecx; serverName
0x140012718  lea     edx, [r9+0Ah]; authnService
0x14001271c  call    cs:__imp_FwpmEngineOpen0
0x140012723  nop     dword ptr [rax+rax+00h]
0x140012728  mov     ebx, eax
0x14001272a  test    eax, eax
0x14001272c  js      loc_1400129A8
0x140012732  mov     edx, 140h
0x140012737  mov     ecx, 40h ; '@'
0x14001273c  mov     r8d, 66774E57h
0x140012742  call    cs:__imp_ExAllocatePool2
0x140012749  nop     dword ptr [rax+rax+00h]
0x14001274e  mov     r14, rax
0x140012751  test    rax, rax
0x140012754  jnz     short loc_140012784
0x140012756  cmp     cs:dword_140027104, esi
0x14001275c  jnz     short loc_14001277A
0x14001275e  test    cs:Microsoft_Windows_WinNatEnableBits, 20h
0x140012765  jz      short loc_14001277A
0x140012767  lea     r9, aFilterCharacte; "Filter characteristics buffer allocatio"...
0x14001276e  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x140012775  call    McTemplateK0z_EtwWriteTransfer
0x14001277a  mov     ebx, 0C000009Ah
0x14001277f  jmp     loc_1400129A8
0x140012784  lea     rbx, [rax+0C8h]
0x14001278b  xor     r15d, r15d
0x14001278e  lea     rax, aWindowsNatForw_0; "Windows NAT forward layer filter"
0x140012795  mov     [r14+10h], rax
0x140012799  lea     rax, aFiltersIpPacke; "Filters IP packets that require transla"...
0x1400127a0  mov     [r14+18h], rax
0x1400127a4  cmp     word ptr [rdi+8], 2
0x1400127a9  jnz     short loc_1400127B4
0x1400127ab  movups  xmm0, xmmword ptr cs:FWPM_LAYER_IPFORWARD_V4.Data1
0x1400127b2  jmp     short loc_1400127BB
0x1400127b4  movups  xmm0, xmmword ptr cs:FWPM_LAYER_IPFORWARD_V6.Data1
0x1400127bb  movdqu  xmmword ptr [r14+40h], xmm0
0x1400127c1  cmp     word ptr [rdi+8], 2
0x1400127c6  jnz     short loc_1400127D1
0x1400127c8  movups  xmm0, cs:WINNAT_WFP_FORWARD_SUBLAYER_IPV4
0x1400127cf  jmp     short loc_1400127D8
0x1400127d1  movups  xmm0, cs:WINNAT_WFP_FORWARD_SUBLAYER_IPV6
0x1400127d8  lea     rax, [rdi+68h]
0x1400127dc  mov     dword ptr [r14+60h], 4
0x1400127e4  mov     [r14+68h], rax
0x1400127e8  movdqu  xmmword ptr [r14+50h], xmm0
0x1400127ee  cmp     [rdi+44h], r15b
0x1400127f2  jz      short loc_14001286A
0x1400127f4  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_DESTINATION_ADDRESS.Data1
0x1400127fb  mov     [rbx+10h], r15d
0x1400127ff  movdqu  xmmword ptr [rbx], xmm0
0x140012803  movzx   eax, word ptr [rdi+8]
0x140012807  cmp     ax, 2
0x14001280b  jnz     short loc_14001283E
0x14001280d  mov     dword ptr [rbx+18h], 100h
0x140012814  lea     rdx, [rbp+Mask+4]; Mask
0x140012818  mov     eax, [rdi+34h]
0x14001281b  movzx   ecx, byte ptr [rdi+44h]; MaskLength
0x14001281f  bswap   eax
0x140012821  mov     [rbp+Mask], eax
0x140012824  call    cs:__imp_ConvertLengthToIpv4Mask
0x14001282b  nop     dword ptr [rax+rax+00h]
0x140012830  mov     eax, [rbp+Mask+4]
0x140012833  bswap   eax
0x140012835  mov     [rbp+Mask+4], eax
0x140012838  lea     rax, [rbp+Mask]
0x14001283c  jmp     short loc_140012863
0x14001283e  cmp     ax, 17h
0x140012842  jz      short loc_140012849
0x140012844  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140012849  mov     dword ptr [rbx+18h], 101h
0x140012850  mov     al, [rdi+44h]
0x140012853  movups  xmm0, xmmword ptr [rdi+34h]
0x140012857  mov     [rbp+var_28], al
0x14001285a  lea     rax, [rbp+var_38]
0x14001285e  movdqu  [rbp+var_38], xmm0
0x140012863  mov     [rbx+20h], rax
0x140012867  mov     r15d, esi
0x14001286a  cmp     byte ptr [rdi+30h], 0
0x14001286e  jz      loc_1400128FD
0x140012874  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_SOURCE_ADDRESS.Data1
0x14001287b  mov     eax, r15d
0x14001287e  lea     r12, [rax+rax*4]
0x140012882  movdqu  xmmword ptr [rbx+r12*8], xmm0
0x140012888  mov     dword ptr [rbx+r12*8+10h], 0
0x140012891  movzx   eax, word ptr [rdi+8]
0x140012895  cmp     ax, 2
0x140012899  jnz     short loc_1400128CE
0x14001289b  mov     dword ptr [rbx+r12*8+18h], 100h
0x1400128a4  lea     rdx, [rbp+var_48+4]; Mask
0x1400128a8  mov     eax, [rdi+20h]
0x1400128ab  movzx   ecx, byte ptr [rdi+30h]; MaskLength
0x1400128af  bswap   eax
0x1400128b1  mov     [rbp+var_48], eax
0x1400128b4  call    cs:__imp_ConvertLengthToIpv4Mask
0x1400128bb  nop     dword ptr [rax+rax+00h]
0x1400128c0  mov     eax, [rbp+var_48+4]
0x1400128c3  bswap   eax
0x1400128c5  mov     [rbp+var_48+4], eax
0x1400128c8  lea     rax, [rbp+var_48]
0x1400128cc  jmp     short loc_1400128F5
0x1400128ce  cmp     ax, 17h
0x1400128d2  jz      short loc_1400128D9
0x1400128d4  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400128d9  mov     dword ptr [rbx+r12*8+18h], 101h
0x1400128e2  mov     al, [rdi+30h]
0x1400128e5  movups  xmm0, xmmword ptr [rdi+20h]
0x1400128e9  mov     [rbp+var_10], al
0x1400128ec  lea     rax, [rbp+var_20]
0x1400128f0  movdqu  [rbp+var_20], xmm0
0x1400128f5  mov     [rbx+r12*8+20h], rax
0x1400128fa  add     r15d, esi
0x1400128fd  cmp     qword ptr [rdi+58h], 0
0x140012902  jz      short loc_140012931
0x140012904  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_SOURCE_INTERFACE_INDEX.Data1
0x14001290b  mov     eax, r15d
0x14001290e  add     r15d, esi
0x140012911  lea     rcx, [rax+rax*4]
0x140012915  movdqu  xmmword ptr [rbx+rcx*8], xmm0
0x14001291a  mov     dword ptr [rbx+rcx*8+10h], 0
0x140012922  mov     dword ptr [rbx+rcx*8+18h], 3
0x14001292a  mov     eax, [rdi+60h]
0x14001292d  mov     [rbx+rcx*8+20h], eax
0x140012931  xor     eax, eax
0x140012933  mov     [r14+70h], r15d
0x140012937  mov     [r14+78h], rbx
0x14001293b  lea     r9, [rdi+70h]; id
0x14001293f  mov     dword ptr [r14+80h], 5003h
0x14001294a  mov     rdx, r14; filter
0x14001294d  cmp     word ptr [rdi+8], 2
0x140012952  lea     ecx, [rax+48h]
0x140012955  cmovz   eax, ecx
0x140012958  lea     rcx, off_140027008
0x14001295f  xor     r8d, r8d; sd
0x140012962  mov     rax, [rax+rcx]
0x140012966  movups  xmm0, xmmword ptr [rax]
0x140012969  mov     [r14+98h], rdi
0x140012970  movdqu  xmmword ptr [r14+84h], xmm0
0x140012979  mov     rcx, [rbp+var_40]; engineHandle
0x14001297d  call    cs:__imp_FwpmFilterAdd0
0x140012984  nop     dword ptr [rax+rax+00h]
0x140012989  mov     ebx, eax
0x14001298b  test    eax, eax
0x14001298d  js      short loc_140012992
0x14001298f  xor     sil, sil
0x140012992  xor     edx, edx; Tag
0x140012994  mov     rcx, r14; P
0x140012997  call    cs:__imp_ExFreePoolWithTag
0x14001299e  nop     dword ptr [rax+rax+00h]
0x1400129a3  jmp     short loc_1400129A8
0x1400129a5  xor     sil, sil
0x1400129a8  mov     rcx, [rbp+var_40]; engineHandle
0x1400129ac  test    rcx, rcx
0x1400129af  jz      short loc_1400129BD
0x1400129b1  call    cs:__imp_FwpmEngineClose0
0x1400129b8  nop     dword ptr [rax+rax+00h]
0x1400129bd  test    sil, sil
0x1400129c0  jz      short loc_1400129C7
0x1400129c2  call    WinNatDereferenceWFPFilters
0x1400129c7  mov     eax, ebx
0x1400129c9  mov     rcx, [rbp+var_8]
0x1400129cd  xor     rcx, rsp; StackCookie
0x1400129d0  call    __security_check_cookie
0x1400129d5  lea     r11, [rsp+80h+var_s0]
0x1400129dd  mov     rbx, [r11+38h]
0x1400129e1  mov     rsi, [r11+40h]
0x1400129e5  mov     rsp, r11
0x1400129e8  pop     r15
0x1400129ea  pop     r14
0x1400129ec  pop     r12
0x1400129ee  pop     rdi
0x1400129ef  pop     rbp
0x1400129f0  retn
```
