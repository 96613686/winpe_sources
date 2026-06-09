# HUBDTX_ValidateAndCacheBOSDescriptor

- ea: `0x14002bc18`
- end: `0x14002c0b0`
- name: `HUBDTX_ValidateAndCacheBOSDescriptor`
- size: `1176`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1400248f0`

## callees

- `0x1400067ac`
- `0x1400083b4`
- `0x140029990`
- `0x14002bc18`
- `0x14003c828`
- `0x140044054`
- `0x140045570`
- `0x140045640`
- `0x140045940`
- `0x14008ec78`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14002be4c`
- `ntoskrnl!ExAllocatePool2` at `0x14002bff3`
- `ntoskrnl!ExAllocatePool2` at `0x14002be4c`
- `ntoskrnl!ExAllocatePool2` at `0x14002bff3`

## pseudocode

```c
__int64 __fastcall HUBDTX_ValidateAndCacheBOSDescriptor(__int64 a1)
{
  unsigned __int16 *v2; // r14
  __int64 v3; // rax
  __int64 v4; // rbx
  int v5; // r12d
  volatile signed __int32 *v6; // rsi
  int v7; // ecx
  bool v8; // zf
  __int64 v9; // rax
  bool v10; // al
  __int64 v11; // rcx
  __int64 *v12; // rdx
  unsigned int v13; // r15d
  void *Pool2; // rax
  int v15; // edx
  char v16; // r12
  __int64 v17; // r8
  __int64 v18; // rcx
  char v19; // al
  __int64 v20; // rax
  char v21; // r9
  char v22; // al
  void *v23; // rax
  int v24; // edx
  unsigned int v25; // ebx
  __int64 v27; // [rsp+68h] [rbp-51h]
  _WORD v28[2]; // [rsp+70h] [rbp-49h] BYREF
  int v29; // [rsp+74h] [rbp-45h]
  int v30; // [rsp+78h] [rbp-41h]
  int v31; // [rsp+7Ch] [rbp-3Dh]
  int v32; // [rsp+80h] [rbp-39h]
  int v33; // [rsp+84h] [rbp-35h]
  void (__fastcall *v34)(__int64, ULONG); // [rsp+88h] [rbp-31h]
  void (__fastcall *v35)(__int64, ULONG); // [rsp+90h] [rbp-29h]
  __int64 v36; // [rsp+98h] [rbp-21h]
  _BOOL8 v37; // [rsp+A0h] [rbp-19h]
  _QWORD v38[8]; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v39; // [rsp+120h] [rbp+67h] BYREF

  memset(v38, 0, sizeof(v38));
  v2 = *(unsigned __int16 **)(a1 + 2064);
  LOBYTE(v39) = 0;
  if ( !v2 )
    v2 = (unsigned __int16 *)(a1 + 1740);
  v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         WdfDriverGlobals->Driver,
         off_14006B2C0);
  v4 = *(_QWORD *)(a1 + 8);
  v5 = *(_DWORD *)(a1 + 2472);
  v36 = a1;
  v31 = 0;
  v28[1] = 0;
  v33 = 0;
  v6 = (volatile signed __int32 *)(a1 + 1640);
  v29 = *(_DWORD *)(a1 + 172);
  v7 = *(_DWORD *)(v3 + 4);
  v37 = 0;
  *(_WORD *)((char *)&v31 + 1) = (v7 & 0x20) != 0;
  HIBYTE(v31) = (v7 & 0x2000) != 0;
  v8 = (*(_DWORD *)(a1 + 1652) & 0x200000) == 0;
  LOBYTE(v31) = (v7 & 0x4000) != 0;
  v32 = *(_DWORD *)(v4 + 220);
  v34 = HUBMISC_LogDescriptorValidationErrorForDevice;
  v35 = HUBMISC_LogDescriptorValidationWarningForDevice;
  v28[0] = *(_WORD *)(a1 + 1998);
  v9 = *(_QWORD *)a1;
  v37 = !v8;
  v27 = *(_QWORD *)(v4 + 1432);
  v30 = *(_DWORD *)(v9 + 92);
  v10 = HUBDESC_ValidateBOSDescriptorSet(
          a1,
          (__int64)v2,
          a1 + 1996,
          *(_DWORD *)(a1 + 264),
          (__int64)v28,
          v38,
          (_WORD *)(a1 + 2200),
          (_WORD *)(a1 + 2202),
          (__int64)&v39,
          a1 + 2448,
          (_DWORD *)(a1 + 1640),
          (_BYTE *)(a1 + 2720),
          (_BYTE *)(a1 + 2721),
          v27);
  v12 = WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids;
  if ( !v10 )
  {
    if ( (*(_DWORD *)(a1 + 1652) & 0x40) == 0 )
    {
      *(_DWORD *)(a1 + 2440) = 1073807378;
LABEL_40:
      v25 = 4065;
      if ( (byte_14006ED41 & 1) != 0 )
        McTemplateK0p_EtwWriteTransfer(
          v11,
          (const EVENT_DESCRIPTOR *)USBHUB3_ETW_EVENT_INVALID_BOS_DESCRIPTOR,
          (const GUID *)(a1 + 1524),
          *(_QWORD *)(a1 + 24));
      return v25;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = 4;
      WPP_RECORDER_SF_(
        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL),
        (_DWORD)v12,
        5,
        57,
        (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids);
    }
  }
  if ( (_BYTE)v39 )
    _InterlockedOr(v6, 0x100000u);
  if ( v38[2] && !*(_QWORD *)(a1 + 2576) )
  {
    v13 = (*(_DWORD *)(v38[2] + 4LL) & 0x1F) + 1;
    Pool2 = (void *)ExAllocatePool2(64, 4LL * v13, 1681082453);
    *(_QWORD *)(a1 + 2576) = Pool2;
    if ( !Pool2 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v15) = 2;
        WPP_RECORDER_SF_(
          *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL),
          v15,
          5,
          58,
          (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids);
      }
      goto LABEL_40;
    }
    memmove(Pool2, (const void *)(v38[2] + 12LL), 4LL * v13);
    *(_DWORD *)(a1 + 2584) = v13;
  }
  v16 = v5 & 1;
  if ( v38[3] )
  {
    _InterlockedOr(v6, 0x10u);
    if ( (*v6 & 8) == 0 )
      *(_OWORD *)(a1 + 2072) = *(_OWORD *)(v38[3] + 4LL);
  }
  if ( v38[4] )
    HUBDTX_CacheBillboardInfo(a1);
  if ( v38[7] )
  {
    _InterlockedOr(v6, 0x40000u);
    *(_BYTE *)(a1 + 2681) = *(_BYTE *)(v38[7] + 21LL);
    UsbDualRoleFeaturesQueryLocalMachine(a1 + 2673);
    v17 = v38[7];
    v18 = *(_QWORD *)(a1 + 8);
    *(_DWORD *)(a1 + 2677) = *(_DWORD *)(v38[7] + 22LL);
    HUBWNF_PublishUsbPartnerDualRoleFeatures(*(_QWORD *)(v18 + 1416), 1, *(_DWORD *)(v17 + 22));
  }
  if ( *(_BYTE *)(*(_QWORD *)(a1 + 2024) + 4LL) > 1u && LOBYTE(v38[5]) == 1 )
  {
    v19 = *(_BYTE *)(a1 + 2000);
    if ( !v19 || v19 == -17 && *(_BYTE *)(a1 + 2001) == 2 && *(_BYTE *)(a1 + 2002) == 1 )
      _InterlockedOr(v6, 4u);
  }
  if ( !v16 )
  {
    if ( v38[6] )
    {
      v20 = *(_QWORD *)v38[6];
      *(_DWORD *)(a1 + 2472) |= 1u;
      *(_QWORD *)(a1 + 2488) = v20;
      v21 = *(_BYTE *)(a1 + 2495);
      if ( v21 )
      {
        if ( (*(_DWORD *)(a1 + 2476) & 4) == 0 )
        {
          v22 = *(_BYTE *)(a1 + 2494);
          *(_DWORD *)(a1 + 2472) |= 4u;
          *(_BYTE *)(a1 + 2060) = v22;
          *(_BYTE *)(a1 + 2480) = v21;
        }
      }
    }
  }
  if ( !*(_QWORD *)(a1 + 2064) )
  {
    v23 = (void *)ExAllocatePool2(64, v2[1], 1681082453);
    *(_QWORD *)(a1 + 2064) = v23;
    if ( !v23 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v24) = 2;
        WPP_RECORDER_SF_(
          *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL),
          v24,
          5,
          59,
          (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids);
      }
      goto LABEL_40;
    }
    memmove(v23, v2, v2[1]);
  }
  if ( (*v6 & 0x800) != 0 )
    _InterlockedOr((volatile signed __int32 *)(a1 + 1648), 0x200u);
  v25 = 4077;
  _InterlockedOr((volatile signed __int32 *)(a1 + 1648), 0x20u);
  return v25;
}

```

## disassembly

```asm
0x14002bc18  mov     [rsp-8+arg_8], rbx
0x14002bc1d  mov     [rsp-8+arg_10], rsi
0x14002bc22  push    rbp
0x14002bc23  push    rdi
0x14002bc24  push    r12
0x14002bc26  push    r14
0x14002bc28  push    r15
0x14002bc2a  lea     rbp, [rsp-37h]
0x14002bc2f  sub     rsp, 0F0h
0x14002bc36  xor     edx, edx; Val
0x14002bc38  mov     rdi, rcx
0x14002bc3b  lea     rcx, [rbp+57h+var_60]; void *
0x14002bc3f  lea     r8d, [rdx+40h]; Size
0x14002bc43  call    memset
0x14002bc48  mov     r14, [rdi+810h]
0x14002bc4f  mov     byte ptr [rbp+57h+arg_0], 0
0x14002bc53  test    r14, r14
0x14002bc56  jnz     short loc_14002BC5F
0x14002bc58  lea     r14, [rdi+6CCh]
0x14002bc5f  mov     rax, cs:WdfFunctions_01015
0x14002bc66  mov     rcx, cs:WdfDriverGlobals
0x14002bc6d  mov     r8, cs:off_14006B2C0
0x14002bc74  mov     rax, [rax+650h]
0x14002bc7b  mov     rdx, [rcx]
0x14002bc7e  call    _guard_dispatch_icall
0x14002bc83  mov     rbx, [rdi+8]
0x14002bc87  lea     r9, [rdi+990h]
0x14002bc8e  mov     r12d, [rdi+9A8h]
0x14002bc95  lea     r10, [rdi+89Ah]
0x14002bc9c  xor     ecx, ecx
0x14002bc9e  mov     [rbp+57h+var_78], rdi
0x14002bca2  mov     [rbp+57h+var_94], ecx
0x14002bca5  lea     r11, [rdi+898h]
0x14002bcac  xor     edx, edx
0x14002bcae  mov     word ptr [rbp+57h+var_A0+2], cx
0x14002bcb2  mov     [rbp+57h+var_8C], ecx
0x14002bcb5  lea     rsi, [rdi+668h]
0x14002bcbc  mov     ecx, [rdi+0ACh]
0x14002bcc2  lea     r8, [rdi+7CCh]; int
0x14002bcc9  mov     dword ptr [rbp+57h+var_A0+4], ecx
0x14002bccc  mov     ecx, [rax+4]
0x14002bccf  lea     r15d, [rdx+1]
0x14002bcd3  movzx   eax, byte ptr [rbp+57h+var_94+1]
0x14002bcd7  test    cl, 20h
0x14002bcda  mov     [rbp+57h+var_70], rdx
0x14002bcde  cmovnz  eax, r15d
0x14002bce2  bt      ecx, 0Dh
0x14002bce6  mov     byte ptr [rbp+57h+var_94+1], al
0x14002bce9  movzx   eax, byte ptr [rbp+57h+var_94+3]
0x14002bced  cmovb   eax, r15d
0x14002bcf1  bt      ecx, 0Eh
0x14002bcf5  mov     byte ptr [rbp+57h+var_94+3], al
0x14002bcf8  movzx   eax, byte ptr [rbp+57h+var_94]
0x14002bcfc  cmovb   eax, r15d
0x14002bd00  movzx   ecx, dl
0x14002bd03  test    dword ptr [rdi+674h], 200000h
0x14002bd0d  lea     rdx, [rdi+0AA0h]
0x14002bd14  mov     byte ptr [rbp+57h+var_94], al
0x14002bd17  mov     eax, [rbx+0DCh]
0x14002bd1d  cmovnz  ecx, r15d
0x14002bd21  mov     [rbp+57h+var_90], eax
0x14002bd24  lea     rax, HUBMISC_LogDescriptorValidationErrorForDevice
0x14002bd2b  mov     [rbp+57h+var_88], rax
0x14002bd2f  lea     rax, HUBMISC_LogDescriptorValidationWarningForDevice
0x14002bd36  mov     [rbp+57h+var_80], rax
0x14002bd3a  movzx   eax, word ptr [rdi+7CEh]
0x14002bd41  mov     word ptr [rbp+57h+var_A0], ax
0x14002bd45  mov     rax, [rdi]
0x14002bd48  mov     byte ptr [rbp+57h+var_70], cl
0x14002bd4b  mov     ecx, [rax+5Ch]
0x14002bd4e  mov     rax, [rbx+598h]
0x14002bd55  mov     [rsp+110h+var_A8], rax; __int64
0x14002bd5a  lea     rax, [rbp+57h+arg_0]
0x14002bd5e  mov     [rbp+57h+var_98], ecx
0x14002bd61  lea     rcx, [rdi+0AA1h]
0x14002bd68  mov     [rsp+110h+var_B0], rcx; __int64
0x14002bd6d  mov     rcx, rdi; int
0x14002bd70  mov     [rsp+110h+var_B8], rdx; __int64
0x14002bd75  mov     rdx, r14; int
0x14002bd78  mov     [rsp+110h+var_C0], rsi; __int64
0x14002bd7d  mov     [rsp+110h+var_C8], r9; __int64
0x14002bd82  mov     r9d, [rdi+108h]; int
0x14002bd89  mov     [rsp+110h+var_D0], rax; __int64
0x14002bd8e  lea     rax, [rbp+57h+var_60]
0x14002bd92  mov     [rsp+110h+var_D8], r10; __int64
0x14002bd97  mov     [rsp+110h+var_E0], r11; __int64
0x14002bd9c  mov     [rsp+110h+var_E8], rax; void *
0x14002bda1  lea     rax, [rbp+57h+var_A0]
0x14002bda5  mov     [rsp+110h+var_F0], rax; __int64
0x14002bdaa  call    HUBDESC_ValidateBOSDescriptorSet
0x14002bdaf  lea     rdx, WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids
0x14002bdb6  lea     rbx, WPP_RECORDER_INITIALIZED
0x14002bdbd  test    al, al
0x14002bdbf  jnz     short loc_14002BE04
0x14002bdc1  mov     eax, [rdi+674h]
0x14002bdc7  test    al, 40h
0x14002bdc9  jnz     short loc_14002BDDA
0x14002bdcb  mov     dword ptr [rdi+988h], 40010012h
0x14002bdd5  jmp     loc_14002C03A
0x14002bdda  cmp     cs:WPP_RECORDER_INITIALIZED, rbx; __annotation("TMF:",
0x14002bde1  jz      short loc_14002BE04
0x14002bde3  mov     rcx, [rdi+8]
0x14002bde7  mov     r9d, 39h ; '9'
0x14002bded  mov     [rsp+110h+var_F0], rdx
0x14002bdf2  mov     dl, 4
0x14002bdf4  mov     rcx, [rcx+598h]
0x14002bdfb  lea     r8d, [r9-34h]
0x14002bdff  call    WPP_RECORDER_SF_
0x14002be04  cmp     byte ptr [rbp+57h+arg_0], 0
0x14002be08  jz      short loc_14002BE11
0x14002be0a  lock or dword ptr [rsi], 100000h
0x14002be11  mov     rax, [rbp+57h+var_50]
0x14002be15  test    rax, rax
0x14002be18  jz      loc_14002BECE
0x14002be1e  cmp     qword ptr [rdi+0A10h], 0
0x14002be26  jnz     loc_14002BECE
0x14002be2c  mov     r15d, [rax+4]
0x14002be30  mov     r8d, 64334855h
0x14002be36  and     r15d, 1Fh
0x14002be3a  mov     ecx, 40h ; '@'
0x14002be3f  inc     r15d
0x14002be42  mov     ebx, r15d
0x14002be45  shl     rbx, 2
0x14002be49  mov     rdx, rbx
0x14002be4c  call    cs:__imp_ExAllocatePool2
0x14002be53  nop     dword ptr [rax+rax+00h]
0x14002be58  mov     [rdi+0A10h], rax
0x14002be5f  test    rax, rax
0x14002be62  jnz     short loc_14002BEA7
0x14002be64  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002be6b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002be72  jz      short loc_14002BE9C
0x14002be74  mov     rcx, [rdi+8]
0x14002be78  lea     rax, WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids
0x14002be7f  mov     r9d, 3Ah ; ':'
0x14002be85  mov     [rsp+110h+var_F0], rax
0x14002be8a  mov     dl, 2
0x14002be8c  mov     rcx, [rcx+598h]
0x14002be93  lea     r8d, [r9-35h]
0x14002be97  call    WPP_RECORDER_SF_
0x14002be9c  mov     r15d, 1
0x14002bea2  jmp     loc_14002C03A
0x14002bea7  mov     rdx, [rbp+57h+var_50]
0x14002beab  mov     r8, rbx; Size
0x14002beae  add     rdx, 0Ch; Src
0x14002beb2  mov     rcx, rax; void *
0x14002beb5  call    memmove
0x14002beba  mov     [rdi+0A18h], r15d
0x14002bec1  lea     rbx, WPP_RECORDER_INITIALIZED
0x14002bec8  mov     r15d, 1
0x14002bece  and     r12b, r15b
0x14002bed1  cmp     [rbp+57h+var_48], 0
0x14002bed6  jz      short loc_14002BEF2
0x14002bed8  lock or dword ptr [rsi], 10h
0x14002bedc  mov     eax, [rsi]
0x14002bede  test    al, 8
0x14002bee0  jnz     short loc_14002BEF2
0x14002bee2  mov     rax, [rbp+57h+var_48]
0x14002bee6  movups  xmm0, xmmword ptr [rax+4]
0x14002beea  movdqu  xmmword ptr [rdi+818h], xmm0
0x14002bef2  mov     rdx, [rbp+57h+var_40]
0x14002bef6  test    rdx, rdx
0x14002bef9  jz      short loc_14002BF03
0x14002befb  mov     rcx, rdi
0x14002befe  call    HUBDTX_CacheBillboardInfo
0x14002bf03  cmp     [rbp+57h+var_28], 0
0x14002bf08  jz      short loc_14002BF4F
0x14002bf0a  lock or dword ptr [rsi], 40000h
0x14002bf11  mov     rax, [rbp+57h+var_28]
0x14002bf15  mov     cl, [rax+15h]
0x14002bf18  mov     [rdi+0A79h], cl
0x14002bf1e  lea     rcx, [rdi+0A71h]
0x14002bf25  call    UsbDualRoleFeaturesQueryLocalMachine
0x14002bf2a  mov     r8, [rbp+57h+var_28]
0x14002bf2e  mov     dl, r15b
0x14002bf31  mov     rcx, [rdi+8]
0x14002bf35  mov     eax, [r8+16h]
0x14002bf39  mov     [rdi+0A75h], eax
0x14002bf3f  mov     r8d, [r8+16h]
0x14002bf43  mov     rcx, [rcx+588h]
0x14002bf4a  call    HUBWNF_PublishUsbPartnerDualRoleFeatures
0x14002bf4f  mov     rax, [rdi+7E8h]
0x14002bf56  cmp     [rax+4], r15b
0x14002bf5a  jbe     short loc_14002BF86
0x14002bf5c  cmp     [rbp+57h+var_38], r15b
0x14002bf60  jnz     short loc_14002BF86
0x14002bf62  mov     al, [rdi+7D0h]
0x14002bf68  test    al, al
0x14002bf6a  jz      short loc_14002BF82
0x14002bf6c  cmp     al, 0EFh
0x14002bf6e  jnz     short loc_14002BF86
0x14002bf70  cmp     byte ptr [rdi+7D1h], 2
0x14002bf77  jnz     short loc_14002BF86
0x14002bf79  cmp     [rdi+7D2h], r15b
0x14002bf80  jnz     short loc_14002BF86
0x14002bf82  lock or dword ptr [rsi], 4
0x14002bf86  test    r12b, r12b
0x14002bf89  jnz     short loc_14002BFD5
0x14002bf8b  mov     rax, [rbp+57h+var_30]
0x14002bf8f  test    rax, rax
0x14002bf92  jz      short loc_14002BFD5
0x14002bf94  mov     rax, [rax]
0x14002bf97  or      [rdi+9A8h], r15d
0x14002bf9e  mov     [rdi+9B8h], rax
0x14002bfa5  mov     r9b, [rdi+9BFh]
0x14002bfac  test    r9b, r9b
0x14002bfaf  jz      short loc_14002BFD5
0x14002bfb1  mov     eax, [rdi+9ACh]
0x14002bfb7  test    al, 4
0x14002bfb9  jnz     short loc_14002BFD5
0x14002bfbb  mov     al, [rdi+9BEh]
0x14002bfc1  or      dword ptr [rdi+9A8h], 4
0x14002bfc8  mov     [rdi+80Ch], al
0x14002bfce  mov     [rdi+9B0h], r9b
0x14002bfd5  cmp     qword ptr [rdi+810h], 0
0x14002bfdd  jnz     loc_14002C071
0x14002bfe3  movzx   edx, word ptr [r14+2]
0x14002bfe8  mov     ecx, 40h ; '@'
0x14002bfed  mov     r8d, 64334855h
0x14002bff3  call    cs:__imp_ExAllocatePool2
0x14002bffa  nop     dword ptr [rax+rax+00h]
0x14002bfff  mov     [rdi+810h], rax
0x14002c006  test    rax, rax
0x14002c009  jnz     short loc_14002C061
0x14002c00b  cmp     cs:WPP_RECORDER_INITIALIZED, rbx; __annotation("TMF:",
0x14002c012  jz      short loc_14002C03A
0x14002c014  mov     rcx, [rdi+8]
0x14002c018  lea     r9d, [rax+3Bh]
0x14002c01c  lea     rax, WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids
0x14002c023  mov     dl, 2
0x14002c025  lea     r8d, [r9-36h]
0x14002c029  mov     [rsp+110h+var_F0], rax
0x14002c02e  mov     rcx, [rcx+598h]
0x14002c035  call    WPP_RECORDER_SF_
0x14002c03a  test    cs:byte_14006ED41, r15b
0x14002c041  mov     ebx, 0FE1h
0x14002c046  jz      short loc_14002C091
0x14002c048  mov     r9, [rdi+18h]
0x14002c04c  lea     r8, [rdi+5F4h]
0x14002c053  lea     rdx, USBHUB3_ETW_EVENT_INVALID_BOS_DESCRIPTOR
0x14002c05a  call    McTemplateK0p_EtwWriteTransfer
0x14002c05f  jmp     short loc_14002C091
0x14002c061  movzx   r8d, word ptr [r14+2]; Size
0x14002c066  mov     rdx, r14; Src
0x14002c069  mov     rcx, rax; void *
0x14002c06c  call    memmove
0x14002c071  test    dword ptr [rsi], 800h
0x14002c077  jz      short loc_14002C084
0x14002c079  lock or dword ptr [rdi+670h], 200h
0x14002c084  mov     ebx, 0FEDh
0x14002c089  lock or dword ptr [rdi+670h], 20h
0x14002c091  lea     r11, [rsp+110h+var_20]
0x14002c099  mov     eax, ebx
0x14002c09b  mov     rbx, [r11+38h]
0x14002c09f  mov     rsi, [r11+40h]
0x14002c0a3  mov     rsp, r11
0x14002c0a6  pop     r15
0x14002c0a8  pop     r14
0x14002c0aa  pop     r12
0x14002c0ac  pop     rdi
0x14002c0ad  pop     rbp
0x14002c0ae  retn
```
