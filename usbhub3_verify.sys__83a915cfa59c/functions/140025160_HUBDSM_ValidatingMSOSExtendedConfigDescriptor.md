# HUBDSM_ValidatingMSOSExtendedConfigDescriptor

- ea: `0x140025160`
- end: `0x1400252fa`
- name: `HUBDSM_ValidatingMSOSExtendedConfigDescriptor`
- size: `410`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x1400024b8`
- `0x1400083b4`
- `0x140025160`
- `0x14003d90c`
- `0x140045570`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400252ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400252ce`

## pseudocode

```c
__int64 __fastcall HUBDSM_ValidatingMSOSExtendedConfigDescriptor(__int64 a1)
{
  __int64 v1; // rdi
  __int64 v2; // rax
  int v3; // ecx
  int v4; // edx
  __int64 v5; // rcx
  unsigned int v6; // ebx
  void *v7; // rcx
  int v9; // [rsp+28h] [rbp-48h]
  __int64 v10; // [rsp+30h] [rbp-40h] BYREF
  __int64 v11; // [rsp+38h] [rbp-38h]
  __int64 v12; // [rsp+40h] [rbp-30h]
  void (__fastcall *v13)(__int64, ULONG); // [rsp+48h] [rbp-28h]
  void (__fastcall *v14)(__int64, ULONG); // [rsp+50h] [rbp-20h]
  __int64 v15; // [rsp+58h] [rbp-18h]
  __int64 v16; // [rsp+60h] [rbp-10h]

  v1 = *(_QWORD *)(a1 + 960);
  v2 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         WdfDriverGlobals->Driver,
         off_14006B2C0);
  v15 = v1;
  v11 = 0;
  WORD1(v10) = 0;
  HIDWORD(v12) = 0;
  LOWORD(v10) = *(_WORD *)(v1 + 1998);
  HIDWORD(v10) = *(_DWORD *)(v1 + 172);
  v3 = *(_DWORD *)(v2 + 4);
  v16 = 0;
  *(_WORD *)((char *)&v11 + 5) = (v3 & 0x20) != 0;
  HIBYTE(v11) = (v3 & 0x2000) != 0;
  LOBYTE(v2) = (v3 & 0x4000) != 0;
  v4 = *(_DWORD *)(v1 + 264);
  LOBYTE(v3) = (*(_DWORD *)(v1 + 1652) & 0x200000) != 0;
  BYTE4(v11) = v2;
  LOBYTE(v16) = v3;
  v5 = *(_QWORD *)(v1 + 8);
  LODWORD(v12) = *(_DWORD *)(v5 + 220);
  v13 = HUBMISC_LogDescriptorValidationErrorForDevice;
  v14 = HUBMISC_LogDescriptorValidationWarningForDevice;
  if ( v4 == *(_DWORD *)(v1 + 1740) )
  {
    v6 = 4077;
    if ( HUBDESC_ValidateMSOSExtendedConfigDescriptor(
           *(_DWORD **)(v1 + 2112),
           v4,
           (__int64)&v10,
           *(_QWORD *)(v5 + 1432)) )
    {
      return v6;
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v9 = v4;
    LOBYTE(v4) = 2;
    WPP_RECORDER_SF_d(
      *(_QWORD *)(v5 + 1432),
      v4,
      5,
      92,
      (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids,
      v9,
      v10,
      v11,
      v12,
      v13,
      v14,
      v15,
      v16);
  }
  v6 = 4065;
  if ( (byte_14006ED41 & 2) != 0 )
    McTemplateK0p_EtwWriteTransfer(
      v5,
      (const EVENT_DESCRIPTOR *)USBHUB3_ETW_EVENT_INVALID_MSOS_EXTENDED_CONFIGURATION_DESCRIPTOR,
      (const GUID *)(v1 + 1524),
      *(_QWORD *)(v1 + 24));
  v7 = *(void **)(v1 + 2112);
  if ( v7 )
  {
    ExFreePoolWithTag(v7, 0x64334855u);
    *(_QWORD *)(v1 + 2112) = 0;
  }
  return v6;
}

```

## disassembly

```asm
0x140025160  mov     [rsp-8+arg_0], rbx
0x140025165  mov     [rsp-8+arg_8], rdi
0x14002516a  push    rbp
0x14002516b  mov     rbp, rsp
0x14002516e  sub     rsp, 70h
0x140025172  mov     rdi, [rcx+3C0h]
0x140025179  mov     rcx, cs:WdfDriverGlobals
0x140025180  mov     rax, cs:WdfFunctions_01015
0x140025187  mov     r8, cs:off_14006B2C0
0x14002518e  mov     rdx, [rcx]
0x140025191  mov     rax, [rax+650h]
0x140025198  call    _guard_dispatch_icall
0x14002519d  xor     ecx, ecx
0x14002519f  mov     [rbp+var_18], rdi
0x1400251a3  mov     [rbp+var_38], rcx
0x1400251a7  xor     edx, edx
0x1400251a9  mov     [rbp+var_3E], cx
0x1400251ad  mov     [rbp+var_2C], ecx
0x1400251b0  movzx   ecx, word ptr [rdi+7CEh]
0x1400251b7  mov     [rbp+var_40], cx
0x1400251bb  lea     r8d, [rdx+1]
0x1400251bf  mov     ecx, [rdi+0ACh]
0x1400251c5  mov     [rbp+var_3C], ecx
0x1400251c8  mov     ecx, [rax+4]
0x1400251cb  test    cl, 20h
0x1400251ce  movzx   eax, byte ptr [rbp+var_38+5]
0x1400251d2  cmovnz  eax, r8d
0x1400251d6  mov     [rbp+var_10], rdx
0x1400251da  mov     byte ptr [rbp+var_38+5], al
0x1400251dd  bt      ecx, 0Dh
0x1400251e1  movzx   eax, byte ptr [rbp+var_38+7]
0x1400251e5  cmovb   eax, r8d
0x1400251e9  bt      ecx, 0Eh
0x1400251ed  mov     byte ptr [rbp+var_38+7], al
0x1400251f0  movzx   eax, byte ptr [rbp+var_38+4]
0x1400251f4  cmovb   eax, r8d
0x1400251f8  movzx   ecx, dl
0x1400251fb  test    dword ptr [rdi+674h], 200000h
0x140025205  mov     edx, [rdi+108h]
0x14002520b  cmovnz  ecx, r8d
0x14002520f  mov     byte ptr [rbp+var_38+4], al
0x140025212  mov     byte ptr [rbp+var_10], cl
0x140025215  mov     rcx, [rdi+8]
0x140025219  mov     eax, [rcx+0DCh]
0x14002521f  mov     [rbp+var_30], eax
0x140025222  lea     rax, HUBMISC_LogDescriptorValidationErrorForDevice
0x140025229  mov     [rbp+var_28], rax
0x14002522d  lea     rax, HUBMISC_LogDescriptorValidationWarningForDevice
0x140025234  mov     [rbp+var_20], rax
0x140025238  cmp     edx, [rdi+6CCh]
0x14002523e  jz      short loc_140025278
0x140025240  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140025247  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002524e  jz      short loc_140025298
0x140025250  mov     rcx, [rcx+598h]
0x140025257  lea     r9d, [r8+5Bh]
0x14002525b  mov     [rsp+70h+var_48], edx
0x14002525f  lea     rax, WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids
0x140025266  lea     r8d, [r9-57h]
0x14002526a  mov     [rsp+70h+var_50], rax
0x14002526f  mov     dl, 2
0x140025271  call    WPP_RECORDER_SF_d
0x140025276  jmp     short loc_140025298
0x140025278  mov     r9, [rcx+598h]
0x14002527f  lea     r8, [rbp+var_40]
0x140025283  mov     rcx, [rdi+840h]
0x14002528a  mov     ebx, 0FEDh
0x14002528f  call    HUBDESC_ValidateMSOSExtendedConfigDescriptor
0x140025294  test    al, al
0x140025296  jnz     short loc_1400252E5
0x140025298  mov     ebx, 0FE1h
0x14002529d  test    cs:byte_14006ED41, 2
0x1400252a4  jz      short loc_1400252BD
0x1400252a6  mov     r9, [rdi+18h]
0x1400252aa  lea     r8, [rdi+5F4h]
0x1400252b1  lea     rdx, USBHUB3_ETW_EVENT_INVALID_MSOS_EXTENDED_CONFIGURATION_DESCRIPTOR
0x1400252b8  call    McTemplateK0p_EtwWriteTransfer
0x1400252bd  mov     rcx, [rdi+840h]; P
0x1400252c4  test    rcx, rcx
0x1400252c7  jz      short loc_1400252E5
0x1400252c9  mov     edx, 64334855h; Tag
0x1400252ce  call    cs:__imp_ExFreePoolWithTag
0x1400252d5  nop     dword ptr [rax+rax+00h]
0x1400252da  mov     qword ptr [rdi+840h], 0
0x1400252e5  lea     r11, [rsp+70h+var_s0]
0x1400252ea  mov     eax, ebx
0x1400252ec  mov     rbx, [r11+10h]
0x1400252f0  mov     rdi, [r11+18h]
0x1400252f4  mov     rsp, r11
0x1400252f7  pop     rbp
0x1400252f8  retn
```
