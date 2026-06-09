# SlbNatCreateStaticMapping

- ea: `0x1400308ac`
- end: `0x140030fe2`
- name: `SlbNatCreateStaticMapping`
- size: `1846`
- prototype: `__int64 __fastcall(wchar_t *Str2, __int64)`
- caller_count: `2`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x14002f9a0`
- `0x140035580`

## callees

- `0x1400080a8`
- `0x14000c7a0`
- `0x14000caa0`
- `0x14000d678`
- `0x14000d7f8`
- `0x14001407c`
- `0x14001492c`
- `0x14001b50c`
- `0x14001b7dc`
- `0x14001ede0`
- `0x14002ffe4`
- `0x1400308ac`
- `0x140030fe8`
- `0x1400310f8`
- `0x140032a30`
- `0x140032b0c`
- `0x140032b5c`
- `0x140032e78`
- `0x140034274`
- `0x1400344f8`

## import_xrefs

- `ntoskrnl!IoAllocateWorkItem` at `0x140030d42`
- `ntoskrnl!IoAllocateWorkItem` at `0x140030d42`
- `ntoskrnl!ExAllocatePool2` at `0x140030c46`
- `ntoskrnl!ExAllocatePool2` at `0x140030d0f`
- `ntoskrnl!ExAllocatePool2` at `0x140030c46`
- `ntoskrnl!ExAllocatePool2` at `0x140030d0f`
- `ntoskrnl!IoFreeIrp` at `0x140030fac`
- `ntoskrnl!IoFreeIrp` at `0x140030fac`
- `ntoskrnl!IoAllocateIrp` at `0x14003092c`
- `ntoskrnl!IoAllocateIrp` at `0x14003092c`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14003099d`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140030f38`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14003099d`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140030f38`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140030918`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x1400309ff`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140030918`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x1400309ff`
- `NETIO!CloseCompartment` at `0x140030f25`
- `NETIO!CloseCompartment` at `0x140030f25`

## string_xrefs

- `0x140030f5e`: `Create static mapping`

## pseudocode

```c
__int64 __fastcall SlbNatCreateStaticMapping(wchar_t *Str2, __int64 a2)
{
  IRP *v4; // rbx
  int StaticBindingEntry; // edi
  __int64 Instance; // rax
  bool v7; // zf
  char v8; // bl
  int Ports; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // r13
  unsigned __int16 v14; // ax
  __int64 v15; // rcx
  __int64 ExternalAddressByAddressAndPort; // rax
  __int64 v17; // r15
  __int64 v18; // rdx
  __int64 v19; // rcx
  int v20; // eax
  unsigned __int8 v21; // al
  __int16 v22; // cx
  bool v23; // cc
  unsigned int v24; // r12d
  unsigned int v25; // eax
  __int64 Pool2; // rax
  int v27; // ecx
  int v28; // r9d
  __int64 v29; // r14
  __int64 AssociatedStaticMapping; // rax
  int v31; // edi
  __int64 v32; // rcx
  __int64 v33; // rdi
  __int64 *v34; // rcx
  __int16 v35; // cx
  int v36; // r8d
  int v37; // eax
  __int64 v38; // rax
  _QWORD *v39; // rcx
  int v40; // edx
  int v41; // r8d
  char v43; // [rsp+70h] [rbp-90h]
  char v44; // [rsp+71h] [rbp-8Fh]
  char v45; // [rsp+72h] [rbp-8Eh]
  char v46[5]; // [rsp+73h] [rbp-8Dh] BYREF
  PIRP Irp; // [rsp+78h] [rbp-88h]
  int v48; // [rsp+80h] [rbp-80h]
  __int64 v49; // [rsp+88h] [rbp-78h]
  __int64 v50; // [rsp+90h] [rbp-70h] BYREF
  wchar_t *v51; // [rsp+98h] [rbp-68h]
  __int128 v52; // [rsp+A0h] [rbp-60h] BYREF
  _OWORD v53[2]; // [rsp+B0h] [rbp-50h] BYREF
  _WORD v54[16]; // [rsp+D0h] [rbp-30h] BYREF
  __int16 v55[16]; // [rsp+F0h] [rbp-10h] BYREF

  v51 = Str2;
  v49 = 0;
  memset(v54, 0, 28);
  memset(v55, 0, 28);
  v45 = 0;
  v46[0] = 0;
  v53[0] = 0;
  v52 = 0;
  ExEnterCriticalRegionAndAcquireResourceExclusive(&Resource);
  Irp = IoAllocateIrp(1, 0);
  v4 = Irp;
  if ( !Irp )
  {
    StaticBindingEntry = -1073741823;
    goto LABEL_91;
  }
  Instance = SlbNatFindInstance(Str2);
  if ( !Instance )
  {
    StaticBindingEntry = -1073741275;
    goto LABEL_91;
  }
  if ( *(_BYTE *)(Instance + 182) )
  {
    v7 = *(_DWORD *)(a2 + 80) == 0;
  }
  else
  {
    if ( !*(_DWORD *)(a2 + 80) )
      goto LABEL_11;
    v7 = *(_DWORD *)(a2 + 8) == 0;
  }
  if ( !v7 )
  {
    StaticBindingEntry = -1073741811;
    goto LABEL_91;
  }
LABEL_11:
  v8 = *(_BYTE *)(Instance + 230);
  ExReleaseResourceAndLeaveCriticalRegion(&Resource);
  if ( v8 )
  {
    Ports = SlbNatAllocatePorts(*(_BYTE *)a2 == 6, (unsigned __int16 *)&v52, __ROR2__(*(_WORD *)(a2 + 40), 8), 1);
    v48 = Ports;
    v45 = 1;
    if ( !*(_WORD *)(a2 + 40) && Ports >= 0 )
    {
      v11 = (unsigned __int16)v52;
      *(_WORD *)(a2 + 40) = v52;
      if ( WORD1(v52) != 1 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v11, v10);
    }
  }
  else
  {
    v48 = -1073741823;
  }
  ExEnterCriticalRegionAndAcquireResourceExclusive(&Resource);
  v12 = SlbNatFindInstance(Str2);
  v13 = v12;
  if ( v12 )
  {
    v14 = *(unsigned __int8 *)(v12 + 230);
    if ( (_BYTE)v14 && !(unsigned __int8)SlbNatIPPrefixMatch(v13 + 232, a2 + 24, v14) )
    {
      StaticBindingEntry = -1073741811;
      goto LABEL_90;
    }
    if ( SlbNatFindStaticMappingInInstance(v13, *((unsigned int *)Str2 + 20), 0) )
    {
      StaticBindingEntry = -1073741635;
      goto LABEL_90;
    }
    v15 = *(unsigned __int16 *)(a2 + 40);
    v44 = 0;
    if ( *(_DWORD *)(a2 + 8) )
      ExternalAddressByAddressAndPort = SlbNatFindExternalAddressByAddressAndPort(
                                          v13,
                                          a2 + 8,
                                          *(unsigned __int16 *)(a2 + 2),
                                          (unsigned __int16)v15,
                                          0);
    else
      ExternalAddressByAddressAndPort = SlbNatFindWildcardExternalAddressByPort(v15);
    v50 = ExternalAddressByAddressAndPort;
    v17 = ExternalAddressByAddressAndPort;
    if ( !ExternalAddressByAddressAndPort )
    {
      if ( *(_BYTE *)(v13 + 230) && *(_WORD *)(a2 + 2) == 2 && !*(_DWORD *)(a2 + 8) )
      {
        StaticBindingEntry = SlbNatCreateWildcardExternalAddress(v13, 2, *(unsigned __int16 *)(a2 + 40), &v50);
        if ( StaticBindingEntry < 0 )
          goto LABEL_90;
        v17 = v50;
        v44 = 1;
        if ( !v50 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v19, v18);
      }
      if ( !v17 )
      {
        StaticBindingEntry = -1073741198;
        goto LABEL_86;
      }
    }
    if ( *(_BYTE *)a2 != 6 && *(_BYTE *)a2 != 17 )
    {
LABEL_38:
      StaticBindingEntry = -1073741811;
      goto LABEL_86;
    }
    v20 = *(_DWORD *)(a2 + 4);
    if ( v20 != 2 )
    {
      v43 = 0;
      if ( v20 != 1 )
      {
        StaticBindingEntry = -1073741637;
        goto LABEL_86;
      }
LABEL_47:
      v24 = *(_DWORD *)(v13 + 68);
      if ( !v24 )
      {
        v25 = SlbNatConvertRdIdtoCompartmentId((GUID *)(a2 + 44));
        v24 = v25;
        if ( !v25 )
        {
          StaticBindingEntry = -1073741264;
          goto LABEL_86;
        }
        if ( v25 == 1 )
        {
          StaticBindingEntry = -1073741637;
          goto LABEL_86;
        }
      }
      StaticBindingEntry = SlbNatVerifyStaticMapping(v17, a2, v24);
      if ( StaticBindingEntry < 0 )
        goto LABEL_86;
      INETADDR_SETSOCKADDR(*(_WORD *)(a2 + 2), (__int64)v55, (IN6_ADDR *)(a2 + 24), 0, __ROR2__(*(_WORD *)(a2 + 42), 8));
      INETADDR_SETSOCKADDR(*(_WORD *)(a2 + 2), (__int64)v54, (IN6_ADDR *)(a2 + 8), 0, __ROR2__(*(_WORD *)(a2 + 40), 8));
      StaticBindingEntry = WinNatLibCreateStaticBindingEntry(
                             qword_1400263D8,
                             v55,
                             (__int64)v54,
                             v24,
                             *(_BYTE *)a2,
                             v43,
                             (unsigned __int8 *)v53,
                             *(_DWORD *)(a2 + 80));
      if ( StaticBindingEntry < 0 )
        goto LABEL_86;
      Pool2 = ExAllocatePool2(256, 136, 1836273235);
      v29 = Pool2;
      if ( !Pool2 )
      {
        StaticBindingEntry = -1073741670;
LABEL_85:
        WinNatLibDeleteStaticBindingEntry(
          (__int64)qword_1400263D8,
          (__int64)v54,
          v55,
          v24,
          *(_BYTE *)a2,
          *(_DWORD *)(a2 + 80));
        goto LABEL_86;
      }
      *(_DWORD *)(Pool2 + 32) = *((_DWORD *)v51 + 20);
      *(_DWORD *)(Pool2 + 16) = v24;
      *(_QWORD *)(Pool2 + 24) = v49;
      *(_QWORD *)(Pool2 + 128) = *(_QWORD *)(v13 + 288);
      if ( !*(_BYTE *)(v13 + 230) )
      {
LABEL_74:
        *(_OWORD *)(v29 + 36) = *(_OWORD *)a2;
        *(_OWORD *)(v29 + 52) = *(_OWORD *)(a2 + 16);
        *(_OWORD *)(v29 + 68) = *(_OWORD *)(a2 + 32);
        *(_OWORD *)(v29 + 84) = *(_OWORD *)(a2 + 48);
        *(_OWORD *)(v29 + 100) = *(_OWORD *)(a2 + 64);
        *(_DWORD *)(v29 + 116) = *(_DWORD *)(a2 + 80);
        v34 = *(__int64 **)(v17 + 24);
        if ( *v34 != v17 + 16 )
          goto LABEL_99;
        *(_QWORD *)v29 = v17 + 16;
        *(_QWORD *)(v29 + 8) = v34;
        StaticBindingEntry = 0;
        *v34 = v29;
        *(_QWORD *)(v17 + 24) = v29;
        ++*(_DWORD *)(v17 + 32);
        v49 = 0;
        v44 = 0;
        if ( (Microsoft_Windows_WinNatEnableBits & 0x10) != 0 )
        {
          v35 = *(_WORD *)(v29 + 38);
          memset(v53, 0, 28);
          INETADDR_SETSOCKADDR(v35, (__int64)v53, (IN6_ADDR *)(v29 + 100), 0, 0);
          if ( dword_140026104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x10) != 0 )
          {
            v36 = 28;
            if ( v54[0] == 2 )
              v36 = 16;
            McTemplateK0zqqqbr3br3jqbr3q_EtwWriteTransfer(
              (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
              (unsigned int)WINNATM_STATIC_MAPPING_ADDITION,
              v36,
              v13 + 80,
              *(_BYTE *)(v29 + 36),
              *(_DWORD *)(v29 + 40),
              v36,
              (__int64)v54,
              (__int64)v55,
              v29 + 80,
              *(_DWORD *)(v29 + 16),
              (__int64)v53,
              *(_BYTE *)(v29 + 96));
          }
        }
        v37 = *((_DWORD *)v51 + 20);
        if ( *(_DWORD *)(v13 + 260) < (unsigned int)(v37 + 1) || v37 == -1 )
          *(_DWORD *)(v13 + 260) = v37 + 1;
LABEL_86:
        if ( !v44 )
          goto LABEL_90;
        v38 = *(_QWORD *)v17;
        if ( *(_QWORD *)(*(_QWORD *)v17 + 8LL) == v17 )
        {
          v39 = *(_QWORD **)(v17 + 8);
          if ( *v39 == v17 )
          {
            *v39 = v38;
            *(_QWORD *)(v38 + 8) = v39;
            SlbNatDeleteExternalAddress((char *)v17, v13);
            goto LABEL_90;
          }
        }
LABEL_99:
        __fastfail(3u);
      }
      AssociatedStaticMapping = 0;
      if ( !*(_DWORD *)(a2 + 8) )
      {
        v31 = *(_DWORD *)(a2 + 80);
        LOBYTE(v27) = *(_BYTE *)a2;
        LOBYTE(v28) = 1;
        AssociatedStaticMapping = SlbNatFindAssociatedStaticMapping(
                                    v27,
                                    *(unsigned __int16 *)(a2 + 40),
                                    v31,
                                    v28,
                                    (__int64)v46);
        if ( v46[0] )
        {
          StaticBindingEntry = -1073741635;
          goto LABEL_85;
        }
        if ( AssociatedStaticMapping )
        {
          if ( *(_DWORD *)(AssociatedStaticMapping + 116) )
          {
            if ( !v31 )
              goto LABEL_72;
          }
          else if ( v31 )
          {
            goto LABEL_72;
          }
        }
      }
      StaticBindingEntry = v48;
      if ( v48 >= 0 )
      {
LABEL_69:
        v33 = ExAllocatePool2(256, 40, 1634750035);
        if ( !v33 )
        {
          StaticBindingEntry = -1073741801;
          goto LABEL_85;
        }
        *(_QWORD *)v33 = IoAllocateWorkItem(deviceObject);
        *(_QWORD *)(v33 + 24) = Irp;
        v7 = *(_BYTE *)a2 == 6;
        Irp = 0;
        *(_BYTE *)(v33 + 32) = v7;
        *(_OWORD *)(v33 + 8) = v52;
        *(_QWORD *)(v29 + 120) = v33;
        goto LABEL_74;
      }
      v45 = 0;
      if ( !AssociatedStaticMapping )
        goto LABEL_85;
      v32 = *(_QWORD *)(AssociatedStaticMapping + 120);
      if ( v32 )
      {
        v52 = *(_OWORD *)(v32 + 8);
        goto LABEL_69;
      }
LABEL_72:
      StaticBindingEntry = -1073741811;
      goto LABEL_85;
    }
    v21 = *(_BYTE *)(a2 + 60);
    if ( !v21 )
      goto LABEL_38;
    v22 = *(_WORD *)(a2 + 2);
    if ( v22 == 2 )
    {
      v23 = v21 <= 0x20u;
    }
    else
    {
      if ( v22 != 23 )
      {
LABEL_46:
        LOBYTE(v53[0]) = *(_BYTE *)(a2 + 60);
        *((_QWORD *)&v53[0] + 1) = a2 + 64;
        v43 = 1;
        goto LABEL_47;
      }
      v23 = v21 <= 0x80u;
    }
    if ( !v23 )
      goto LABEL_38;
    goto LABEL_46;
  }
  StaticBindingEntry = -1073741275;
LABEL_90:
  v4 = Irp;
LABEL_91:
  if ( v49 )
    CloseCompartment();
  ExReleaseResourceAndLeaveCriticalRegion(&Resource);
  if ( StaticBindingEntry >= 0 )
    goto LABEL_100;
  if ( dword_140026104 == 1 && (byte_140026BED & 0x10) != 0 )
    McTemplateK0qzqq_EtwWriteTransfer(
      (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
      v40,
      v41,
      3008,
      (__int64)L"Create static mapping",
      0,
      StaticBindingEntry);
  if ( v45 )
  {
    SlbNatFreePortReservationWithIrp(v4);
  }
  else
  {
LABEL_100:
    if ( v4 )
      IoFreeIrp(v4);
  }
  return (unsigned int)StaticBindingEntry;
}

```

## disassembly

```asm
0x1400308ac  mov     [rsp-8+arg_10], rbx
0x1400308b1  push    rbp
0x1400308b2  push    rsi
0x1400308b3  push    rdi
0x1400308b4  push    r12
0x1400308b6  push    r13
0x1400308b8  push    r14
0x1400308ba  push    r15
0x1400308bc  lea     rbp, [rsp-20h]
0x1400308c1  sub     rsp, 120h
0x1400308c8  mov     rax, cs:__security_cookie
0x1400308cf  xor     rax, rsp
0x1400308d2  mov     [rbp+50h+var_40], rax
0x1400308d6  xorps   xmm0, xmm0
0x1400308d9  mov     [rbp+50h+var_B8], rcx
0x1400308dd  xorps   xmm1, xmm1
0x1400308e0  xor     r12d, r12d
0x1400308e3  mov     r14, rcx
0x1400308e6  mov     [rbp+50h+var_C8], r12
0x1400308ea  movups  xmmword ptr [rbp+50h+var_80], xmm0
0x1400308ee  xor     eax, eax
0x1400308f0  lea     rcx, Resource; Resource
0x1400308f7  movups  xmmword ptr [rbp+50h+var_60], xmm1
0x1400308fb  mov     rsi, rdx
0x1400308fe  mov     [rsp+150h+var_DE], r12b
0x140030903  movups  xmmword ptr [rbp+50h+var_80+0Ch], xmm0
0x140030907  mov     [rsp+150h+var_DD], r12b
0x14003090c  movups  xmmword ptr [rbp+50h+var_60+0Ch], xmm1
0x140030910  movups  [rbp+50h+var_A0], xmm0
0x140030914  movups  [rbp+50h+var_B0], xmm1
0x140030918  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x14003091f  nop     dword ptr [rax+rax+00h]
0x140030924  xor     edx, edx; ChargeQuota
0x140030926  lea     edi, [rdx+1]
0x140030929  mov     cl, dil; StackSize
0x14003092c  call    cs:__imp_IoAllocateIrp
0x140030933  nop     dword ptr [rax+rax+00h]
0x140030938  mov     [rsp+150h+var_D8], rax
0x14003093d  mov     rbx, rax
0x140030940  lea     r15d, [r12+10h]
0x140030945  test    rax, rax
0x140030948  jnz     short loc_140030954
0x14003094a  mov     edi, 0C0000001h
0x14003094f  jmp     loc_140030F1C
0x140030954  mov     rcx, r14; Str2
0x140030957  call    SlbNatFindInstance
0x14003095c  test    rax, rax
0x14003095f  jnz     short loc_14003096B
0x140030961  mov     edi, 0C0000225h
0x140030966  jmp     loc_140030F1C
0x14003096b  cmp     [rax+0B6h], r12b
0x140030972  jbe     short loc_140030984
0x140030974  cmp     [rsi+50h], r12d
0x140030978  jz      short loc_140030990
0x14003097a  mov     edi, 0C000000Dh
0x14003097f  jmp     loc_140030F1C
0x140030984  cmp     [rsi+50h], r12d
0x140030988  jz      short loc_140030990
0x14003098a  cmp     [rsi+8], r12d
0x14003098e  jmp     short loc_140030978
0x140030990  mov     bl, [rax+0E6h]
0x140030996  lea     rcx, Resource; Resource
0x14003099d  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x1400309a4  nop     dword ptr [rax+rax+00h]
0x1400309a9  test    bl, bl
0x1400309ab  jz      short loc_1400309F1
0x1400309ad  movzx   r8d, word ptr [rsi+28h]
0x1400309b2  lea     rdx, [rbp+50h+var_B0]
0x1400309b6  ror     r8w, 8
0x1400309bb  mov     r9b, dil
0x1400309be  cmp     byte ptr [rsi], 6
0x1400309c1  setz    cl
0x1400309c4  call    SlbNatAllocatePorts
0x1400309c9  mov     [rbp+50h+var_D0], eax
0x1400309cc  mov     [rsp+150h+var_DE], dil
0x1400309d1  cmp     [rsi+28h], r12w
0x1400309d6  jnz     short loc_1400309F8
0x1400309d8  test    eax, eax
0x1400309da  js      short loc_1400309F8
0x1400309dc  movzx   ecx, word ptr [rbp+50h+var_B0]
0x1400309e0  mov     [rsi+28h], cx
0x1400309e4  cmp     word ptr [rbp+50h+var_B0+2], di
0x1400309e8  jz      short loc_1400309F8
0x1400309ea  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400309ef  jmp     short loc_1400309F8
0x1400309f1  mov     [rbp+50h+var_D0], 0C0000001h
0x1400309f8  lea     rcx, Resource; Resource
0x1400309ff  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x140030a06  nop     dword ptr [rax+rax+00h]
0x140030a0b  mov     rcx, r14; Str2
0x140030a0e  call    SlbNatFindInstance
0x140030a13  mov     r13, rax
0x140030a16  test    rax, rax
0x140030a19  jnz     short loc_140030A25
0x140030a1b  mov     edi, 0C0000225h
0x140030a20  jmp     loc_140030F17
0x140030a25  movzx   eax, byte ptr [rax+0E6h]
0x140030a2c  test    al, al
0x140030a2e  jz      short loc_140030A52
0x140030a30  movzx   r8d, ax
0x140030a34  lea     rdx, [rsi+18h]
0x140030a38  lea     rcx, [r13+0E8h]
0x140030a3f  call    SlbNatIPPrefixMatch
0x140030a44  test    al, al
0x140030a46  jnz     short loc_140030A52
0x140030a48  mov     edi, 0C000000Dh
0x140030a4d  jmp     loc_140030F17
0x140030a52  mov     edx, [r14+50h]
0x140030a56  xor     r8d, r8d
0x140030a59  mov     rcx, r13
0x140030a5c  call    SlbNatFindStaticMappingInInstance
0x140030a61  test    rax, rax
0x140030a64  jz      short loc_140030A70
0x140030a66  mov     edi, 0C00000BDh
0x140030a6b  jmp     loc_140030F17
0x140030a70  movzx   ecx, word ptr [rsi+28h]
0x140030a74  lea     r14, [rsi+8]
0x140030a78  mov     [rsp+150h+var_DF], r12b
0x140030a7d  cmp     [r14], r12d
0x140030a80  jnz     short loc_140030A89
0x140030a82  call    SlbNatFindWildcardExternalAddressByPort
0x140030a87  jmp     short loc_140030AA2
0x140030a89  movzx   r8d, word ptr [rsi+2]
0x140030a8e  movzx   r9d, cx
0x140030a92  mov     rcx, r13
0x140030a95  mov     byte ptr [rsp+150h+var_130], r12b
0x140030a9a  mov     rdx, r14
0x140030a9d  call    SlbNatFindExternalAddressByAddressAndPort
0x140030aa2  mov     [rbp+50h+var_C0], rax
0x140030aa6  mov     r15, rax
0x140030aa9  mov     edx, 2
0x140030aae  test    rax, rax
0x140030ab1  jnz     short loc_140030B0D
0x140030ab3  cmp     [r13+0E6h], r12b
0x140030aba  jbe     short loc_140030AFE
0x140030abc  cmp     [rsi+2], dx
0x140030ac0  jnz     short loc_140030AFE
0x140030ac2  cmp     [r14], r12d
0x140030ac5  jnz     short loc_140030AFE
0x140030ac7  movzx   r8d, word ptr [rsi+28h]
0x140030acc  lea     r9, [rbp+50h+var_C0]
0x140030ad0  mov     rcx, r13
0x140030ad3  call    SlbNatCreateWildcardExternalAddress
0x140030ad8  mov     edi, eax
0x140030ada  test    eax, eax
0x140030adc  js      loc_140030F11
0x140030ae2  lea     edi, [r15+1]
0x140030ae6  mov     r15, [rbp+50h+var_C0]
0x140030aea  mov     [rsp+150h+var_DF], dil
0x140030aef  test    r15, r15
0x140030af2  jnz     short loc_140030AF9
0x140030af4  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140030af9  mov     edx, 2
0x140030afe  test    r15, r15
0x140030b01  jnz     short loc_140030B0D
0x140030b03  mov     edi, 0C0000272h
0x140030b08  jmp     loc_140030EDE
0x140030b0d  mov     al, [rsi]
0x140030b0f  cmp     al, 6
0x140030b11  jz      short loc_140030B21
0x140030b13  cmp     al, 11h
0x140030b15  jz      short loc_140030B21
0x140030b17  mov     edi, 0C000000Dh
0x140030b1c  jmp     loc_140030EDE
0x140030b21  mov     eax, [rsi+4]
0x140030b24  cmp     eax, edx
0x140030b26  jnz     short loc_140030B7D
0x140030b28  mov     al, [rsi+3Ch]
0x140030b2b  test    al, al
0x140030b2d  jz      short loc_140030B17
0x140030b2f  movzx   ecx, word ptr [rsi+2]
0x140030b33  cmp     cx, dx
0x140030b36  jnz     short loc_140030B3C
0x140030b38  cmp     al, 20h ; ' '
0x140030b3a  jmp     short loc_140030B44
0x140030b3c  cmp     cx, 17h
0x140030b40  jnz     short loc_140030B46
0x140030b42  cmp     al, 80h
0x140030b44  ja      short loc_140030B17
0x140030b46  mov     byte ptr [rbp+50h+var_A0], al
0x140030b49  lea     rax, [rsi+40h]
0x140030b4d  mov     qword ptr [rbp+50h+var_A0+8], rax
0x140030b51  mov     [rsp+150h+var_E0], dil
0x140030b56  mov     r12d, [r13+44h]
0x140030b5a  test    r12d, r12d
0x140030b5d  jnz     short loc_140030B9E
0x140030b5f  lea     rcx, [rsi+2Ch]; CompartmentGuid
0x140030b63  lea     rdx, [rbp+50h+var_C8]
0x140030b67  call    SlbNatConvertRdIdtoCompartmentId
0x140030b6c  mov     r12d, eax
0x140030b6f  test    eax, eax
0x140030b71  jnz     short loc_140030B90
0x140030b73  mov     edi, 0C0000230h
0x140030b78  jmp     loc_140030EDB
0x140030b7d  mov     [rsp+150h+var_E0], r12b
0x140030b82  cmp     eax, edi
0x140030b84  jz      short loc_140030B56
0x140030b86  mov     edi, 0C00000BBh
0x140030b8b  jmp     loc_140030EDE
0x140030b90  cmp     eax, edi
0x140030b92  jnz     short loc_140030B9E
0x140030b94  mov     edi, 0C00000BBh
0x140030b99  jmp     loc_140030EDB
0x140030b9e  mov     r8d, r12d
0x140030ba1  mov     rdx, rsi
0x140030ba4  mov     rcx, r15
0x140030ba7  call    SlbNatVerifyStaticMapping
0x140030bac  mov     edi, eax
0x140030bae  test    eax, eax
0x140030bb0  js      loc_140030EDB
0x140030bb6  movzx   eax, word ptr [rsi+2Ah]
0x140030bba  lea     r8, [rsi+18h]
0x140030bbe  movzx   ecx, word ptr [rsi+2]
0x140030bc2  lea     rdx, [rbp+50h+var_60]
0x140030bc6  ror     ax, 8
0x140030bca  xor     ebx, ebx
0x140030bcc  mov     r9d, ebx
0x140030bcf  mov     word ptr [rsp+150h+var_130], ax
0x140030bd4  call    INETADDR_SETSOCKADDR
0x140030bd9  movzx   eax, word ptr [rsi+28h]
0x140030bdd  lea     rdx, [rbp+50h+var_80]
0x140030be1  movzx   ecx, word ptr [rsi+2]
0x140030be5  mov     r9d, ebx
0x140030be8  ror     ax, 8
0x140030bec  mov     r8, r14
0x140030bef  mov     word ptr [rsp+150h+var_130], ax
0x140030bf4  call    INETADDR_SETSOCKADDR
0x140030bf9  mov     eax, [rsi+50h]
0x140030bfc  lea     r8, [rbp+50h+var_80]
0x140030c00  mov     rcx, cs:qword_1400263D8
0x140030c07  lea     rdx, [rbp+50h+var_60]
0x140030c0b  mov     dword ptr [rsp+150h+var_118], eax
0x140030c0f  mov     r9d, r12d
0x140030c12  lea     rax, [rbp+50h+var_A0]
0x140030c16  mov     [rsp+150h+var_120], rax
0x140030c1b  mov     al, [rsp+150h+var_E0]
0x140030c1f  mov     byte ptr [rsp+150h+var_128], al
0x140030c23  mov     al, [rsi]
0x140030c25  mov     byte ptr [rsp+150h+var_130], al
0x140030c29  call    WinNatLibCreateStaticBindingEntry
0x140030c2e  mov     edi, eax
0x140030c30  test    eax, eax
0x140030c32  js      loc_140030EDB
0x140030c38  mov     edx, 88h
0x140030c3d  mov     r8d, 6D734E53h
0x140030c43  lea     ecx, [rdx+78h]
0x140030c46  call    cs:__imp_ExAllocatePool2
0x140030c4d  nop     dword ptr [rax+rax+00h]
0x140030c52  mov     r14, rax
0x140030c55  test    rax, rax
0x140030c58  jnz     short loc_140030C64
0x140030c5a  mov     edi, 0C000009Ah
0x140030c5f  jmp     loc_140030EB7
0x140030c64  mov     rax, [rbp+50h+var_B8]
0x140030c68  mov     eax, [rax+50h]
0x140030c6b  mov     [r14+20h], eax
0x140030c6f  mov     [r14+10h], r12d
0x140030c73  mov     rax, [rbp+50h+var_C8]
0x140030c77  mov     [r14+18h], rax
0x140030c7b  mov     rax, [r13+120h]
0x140030c82  mov     [r14+80h], rax
0x140030c89  cmp     [r13+0E6h], bl
0x140030c90  jbe     loc_140030D77
0x140030c96  xor     eax, eax
0x140030c98  cmp     [rsi+8], eax
0x140030c9b  jnz     short loc_140030CD9
0x140030c9d  mov     edi, [rsi+50h]
0x140030ca0  lea     rax, [rsp+150h+var_DD]
0x140030ca5  movzx   edx, word ptr [rsi+28h]
0x140030ca9  mov     r8d, edi
0x140030cac  mov     cl, [rsi]
0x140030cae  mov     r9b, 1
0x140030cb1  mov     [rsp+150h+var_130], rax
0x140030cb6  call    SlbNatFindAssociatedStaticMapping
0x140030cbb  cmp     [rsp+150h+var_DD], bl
0x140030cbf  jz      short loc_140030CCB
0x140030cc1  mov     edi, 0C00000BDh
0x140030cc6  jmp     loc_140030EB7
0x140030ccb  test    rax, rax
0x140030cce  jz      short loc_140030CD9
0x140030cd0  cmp     [rax+74h], ebx
0x140030cd3  jz      short loc_140030D2D
0x140030cd5  test    edi, edi
0x140030cd7  jz      short loc_140030D31
0x140030cd9  mov     edi, [rbp+50h+var_D0]
0x140030cdc  test    edi, edi
0x140030cde  jns     short loc_140030CFF
0x140030ce0  mov     [rsp+150h+var_DE], bl
0x140030ce4  test    rax, rax
0x140030ce7  jz      loc_140030EB7
0x140030ced  mov     rcx, [rax+78h]
0x140030cf1  test    rcx, rcx
0x140030cf4  jz      short loc_140030D31
0x140030cf6  movups  xmm0, xmmword ptr [rcx+8]
0x140030cfa  movdqu  [rbp+50h+var_B0], xmm0
0x140030cff  mov     edx, 28h ; '('
0x140030d04  mov     ecx, 100h
0x140030d09  mov     r8d, 61704E53h
0x140030d0f  call    cs:__imp_ExAllocatePool2
0x140030d16  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
