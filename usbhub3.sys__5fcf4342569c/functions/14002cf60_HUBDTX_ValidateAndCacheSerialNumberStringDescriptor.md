# HUBDTX_ValidateAndCacheSerialNumberStringDescriptor

- ea: `0x14002cf60`
- end: `0x14002d286`
- name: `HUBDTX_ValidateAndCacheSerialNumberStringDescriptor`
- size: `806`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140025750`

## callees

- `0x1400024b8`
- `0x1400067ac`
- `0x1400083b4`
- `0x14002cf60`
- `0x1400302d0`
- `0x1400399c4`
- `0x140045570`
- `0x140045640`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002d17d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d17d`
- `ntoskrnl!ExAllocatePool2` at `0x14002d1a6`
- `ntoskrnl!ExAllocatePool2` at `0x14002d1a6`

## pseudocode

```c
__int64 __fastcall HUBDTX_ValidateAndCacheSerialNumberStringDescriptor(__int64 a1)
{
  __int64 v2; // rax
  unsigned int v3; // r12d
  int v4; // ecx
  int v5; // ecx
  bool v6; // zf
  __int64 v7; // rcx
  __int64 v8; // r14
  __int64 v9; // r9
  int v10; // edx
  __int64 v11; // rcx
  char v12; // r15
  unsigned int v13; // r13d
  unsigned int v14; // edi
  int v15; // r12d
  void *v16; // rcx
  unsigned int v17; // eax
  unsigned int v18; // edi
  __int64 Pool2; // rax
  int v20; // eax
  int v21; // eax
  unsigned int v22; // edi
  __int64 v24; // [rsp+28h] [rbp-48h]
  __int64 v25; // [rsp+30h] [rbp-40h] BYREF
  __int64 v26; // [rsp+38h] [rbp-38h]
  int v27; // [rsp+40h] [rbp-30h]
  int v28; // [rsp+44h] [rbp-2Ch]
  void (__fastcall *v29)(__int64, ULONG); // [rsp+48h] [rbp-28h]
  void (__fastcall *v30)(__int64, ULONG); // [rsp+50h] [rbp-20h]
  __int64 v31; // [rsp+58h] [rbp-18h]
  _BOOL8 v32; // [rsp+60h] [rbp-10h]
  unsigned int v33; // [rsp+B0h] [rbp+40h] BYREF
  unsigned int v34; // [rsp+B8h] [rbp+48h]
  __int64 v35; // [rsp+C0h] [rbp+50h]

  v2 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         WdfDriverGlobals->Driver,
         off_14006B2C0);
  v3 = *(_DWORD *)(a1 + 264);
  LODWORD(v25) = *(unsigned __int16 *)(a1 + 1998);
  v4 = *(_DWORD *)(a1 + 172);
  v26 = 0;
  HIDWORD(v25) = v4;
  v5 = *(_DWORD *)(v2 + 4);
  v32 = 0;
  *(_WORD *)((char *)&v26 + 5) = (v5 & 0x20) != 0;
  HIBYTE(v26) = (v5 & 0x2000) != 0;
  v6 = (*(_DWORD *)(a1 + 1652) & 0x200000) == 0;
  BYTE4(v26) = (v5 & 0x4000) != 0;
  v28 = 0;
  v32 = !v6;
  v7 = *(_QWORD *)(a1 + 8);
  v31 = a1;
  v34 = v3;
  v33 = 0;
  v8 = *(_QWORD *)(v7 + 1432);
  v27 = *(_DWORD *)(v7 + 220);
  v29 = HUBMISC_LogDescriptorValidationErrorForDevice;
  v30 = HUBMISC_LogDescriptorValidationWarningForDevice;
  v35 = v8;
  v12 = HUBDESC_InternalValidateStringDescriptor((char *)(a1 + 1740), v3, &v33, v9, v8, (__int64)&v25);
  if ( !v12 )
    goto LABEL_15;
  v13 = *(unsigned __int8 *)(a1 + 1740);
  v10 = 0;
  v33 = v13;
  v14 = 0;
  if ( (v13 - 2) >> 1 )
  {
    v15 = v35;
    do
    {
      v11 = *(unsigned __int16 *)(a1 + 2LL * v14 + 1742);
      if ( !(_WORD)v11 )
        break;
      if ( (unsigned __int16)(v11 - 32) > 0x5Fu || (_DWORD)v11 == 44 )
      {
        v12 = 0;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LODWORD(v24) = *(unsigned __int16 *)(a1 + 2LL * v14 + 1742);
          LOBYTE(v10) = 2;
          WPP_RECORDER_SF_d(v15, v10, 5, 292, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v24, v25, v26);
        }
        HUBMISC_LogDescriptorValidationErrorForDevice(a1, 0x84u);
        v10 = 0;
      }
      ++v14;
    }
    while ( v14 < (v13 - 2) >> 1 );
    v13 = v33;
    v3 = v34;
    if ( !v12 )
    {
      LODWORD(v8) = v35;
LABEL_15:
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v10) = 2;
        WPP_RECORDER_SF_(v8, v10, 5, 293, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
      }
      *(_DWORD *)(a1 + 2440) = 1073807384;
      goto LABEL_30;
    }
  }
  v16 = *(void **)(a1 + 2160);
  if ( v16 )
    ExFreePoolWithTag(v16, 0x64334855u);
  v17 = v3 + 12;
  if ( !_bittest((const signed __int32 *)(a1 + 1644), 0xBu) )
    v17 = v3;
  v18 = v17;
  Pool2 = ExAllocatePool2(64, v17, 1681082453);
  *(_QWORD *)(a1 + 2160) = Pool2;
  v11 = Pool2;
  if ( Pool2 )
  {
    v20 = *(_DWORD *)(a1 + 1640);
    *(_DWORD *)(a1 + 2156) = v18;
    if ( (v20 & 2) != 0 )
    {
      if ( *(_WORD *)(a1 + 1998) < 0x300u )
      {
        *(_QWORD *)v11 = *(_QWORD *)L"MSFT20";
        v21 = *(_DWORD *)L"20";
LABEL_27:
        *(_DWORD *)(v11 + 8) = v21;
        v11 += 12;
        goto LABEL_28;
      }
    }
    else if ( !_bittest((const signed __int32 *)(a1 + 1644), 0xBu) )
    {
LABEL_28:
      memmove((void *)v11, (const void *)(a1 + 1742), v13 - 2LL);
      _InterlockedOr((volatile signed __int32 *)(a1 + 1640), 0x40u);
      return 4077;
    }
    *(_QWORD *)v11 = *(_QWORD *)L"MSFT30";
    v21 = *(_DWORD *)L"30";
    goto LABEL_27;
  }
LABEL_30:
  v22 = 4065;
  if ( (byte_14006ED41 & 1) != 0 )
    McTemplateK0p_EtwWriteTransfer(
      v11,
      (const EVENT_DESCRIPTOR *)USBHUB3_ETW_EVENT_INVALID_SERIAL_NUMBER_STRING_DESCRIPTOR,
      (const GUID *)(a1 + 1524),
      *(_QWORD *)(a1 + 24));
  return v22;
}

```

## disassembly

```asm
0x14002cf60  mov     [rsp-38h+arg_18], rbx
0x14002cf65  push    rbp
0x14002cf66  push    rsi
0x14002cf67  push    rdi
0x14002cf68  push    r12
0x14002cf6a  push    r13
0x14002cf6c  push    r14
0x14002cf6e  push    r15
0x14002cf70  mov     rbp, rsp
0x14002cf73  sub     rsp, 70h
0x14002cf77  mov     rax, cs:WdfFunctions_01015
0x14002cf7e  mov     rbx, rcx
0x14002cf81  mov     rcx, cs:WdfDriverGlobals
0x14002cf88  mov     r8, cs:off_14006B2C0
0x14002cf8f  mov     rax, [rax+650h]
0x14002cf96  mov     rdx, [rcx]
0x14002cf99  call    _guard_dispatch_icall
0x14002cf9e  movzx   ecx, word ptr [rbx+7CEh]
0x14002cfa5  lea     rdi, [rbx+6CCh]
0x14002cfac  mov     r12d, [rbx+108h]
0x14002cfb3  xor     r13d, r13d
0x14002cfb6  mov     [rbp+var_40], cx
0x14002cfba  mov     edx, r12d
0x14002cfbd  mov     ecx, [rbx+0ACh]
0x14002cfc3  mov     [rbp+var_38], r13
0x14002cfc7  mov     [rbp+var_3C], ecx
0x14002cfca  lea     r8d, [r13+1]
0x14002cfce  mov     ecx, [rax+4]
0x14002cfd1  test    cl, 20h
0x14002cfd4  movzx   eax, byte ptr [rbp+var_38+5]
0x14002cfd8  cmovnz  eax, r8d
0x14002cfdc  mov     [rbp+var_10], r13
0x14002cfe0  mov     byte ptr [rbp+var_38+5], al
0x14002cfe3  bt      ecx, 0Dh
0x14002cfe7  movzx   eax, byte ptr [rbp+var_38+7]
0x14002cfeb  cmovb   eax, r8d
0x14002cfef  mov     [rbp+var_3E], r13w
0x14002cff4  mov     byte ptr [rbp+var_38+7], al
0x14002cff7  bt      ecx, 0Eh
0x14002cffb  movzx   eax, byte ptr [rbp+var_38+4]
0x14002cfff  cmovb   eax, r8d
0x14002d003  movzx   ecx, r13b
0x14002d007  test    dword ptr [rbx+674h], 200000h
0x14002d011  mov     byte ptr [rbp+var_38+4], al
0x14002d014  cmovnz  ecx, r8d
0x14002d018  mov     [rbp+var_2C], r13d
0x14002d01c  mov     byte ptr [rbp+var_10], cl
0x14002d01f  lea     r8, [rbp+arg_0]
0x14002d023  mov     rcx, [rbx+8]
0x14002d027  mov     [rbp+var_18], rbx
0x14002d02b  mov     [rbp+arg_8], r12d
0x14002d02f  mov     [rbp+arg_0], r13d
0x14002d033  mov     eax, [rcx+0DCh]
0x14002d039  mov     r14, [rcx+598h]
0x14002d040  mov     rcx, rdi
0x14002d043  mov     [rbp+var_30], eax
0x14002d046  lea     rax, HUBMISC_LogDescriptorValidationErrorForDevice
0x14002d04d  mov     [rbp+var_28], rax
0x14002d051  lea     rax, HUBMISC_LogDescriptorValidationWarningForDevice
0x14002d058  mov     [rbp+var_20], rax
0x14002d05c  lea     rax, [rbp+var_40]
0x14002d060  mov     [rsp+70h+var_48], rax
0x14002d065  mov     [rsp+70h+var_50], r14
0x14002d06a  mov     [rbp+arg_10], r14
0x14002d06e  call    HUBDESC_InternalValidateStringDescriptor
0x14002d073  mov     r15b, al
0x14002d076  lea     r8, WPP_RECORDER_INITIALIZED
0x14002d07d  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14002d084  test    r15b, r15b
0x14002d087  jz      loc_14002D127
0x14002d08d  movzx   r13d, byte ptr [rdi]
0x14002d091  xor     edx, edx
0x14002d093  mov     [rbp+arg_0], r13d
0x14002d097  mov     edi, edx
0x14002d099  lea     esi, [r13-2]
0x14002d09d  mov     r14d, esi
0x14002d0a0  shr     r14d, 1
0x14002d0a3  jz      short loc_14002D122
0x14002d0a5  mov     r12, [rbp+arg_10]
0x14002d0a9  lea     r13, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14002d0b0  mov     eax, edi
0x14002d0b2  movzx   ecx, word ptr [rbx+rax*2+6CEh]
0x14002d0ba  test    cx, cx
0x14002d0bd  jz      short loc_14002D115
0x14002d0bf  lea     eax, [rcx-20h]
0x14002d0c2  cmp     ax, 5Fh ; '_'
0x14002d0c6  ja      short loc_14002D0CD
0x14002d0c8  cmp     ecx, 2Ch ; ','
0x14002d0cb  jnz     short loc_14002D10E
0x14002d0cd  mov     r15b, dl
0x14002d0d0  cmp     cs:WPP_RECORDER_INITIALIZED, r8; __annotation("TMF:",
0x14002d0d7  jz      short loc_14002D0F8
0x14002d0d9  mov     dword ptr [rsp+70h+var_48], ecx
0x14002d0dd  mov     r9d, 124h
0x14002d0e3  mov     rcx, r12
0x14002d0e6  mov     [rsp+70h+var_50], r13
0x14002d0eb  mov     r8d, 5
0x14002d0f1  mov     dl, 2
0x14002d0f3  call    WPP_RECORDER_SF_d
0x14002d0f8  mov     edx, 84h
0x14002d0fd  mov     rcx, rbx
0x14002d100  call    HUBMISC_LogDescriptorValidationErrorForDevice
0x14002d105  xor     edx, edx
0x14002d107  lea     r8, WPP_RECORDER_INITIALIZED
0x14002d10e  inc     edi
0x14002d110  cmp     edi, r14d
0x14002d113  jb      short loc_14002D0B0
0x14002d115  mov     r13d, [rbp+arg_0]
0x14002d119  mov     r12d, [rbp+arg_8]
0x14002d11d  test    r15b, r15b
0x14002d120  jz      short loc_14002D12C
0x14002d122  mov     esi, r13d
0x14002d125  jmp     short loc_14002D168
0x14002d127  mov     esi, r12d
0x14002d12a  jmp     short loc_14002D137
0x14002d12c  mov     r14, [rbp+arg_10]
0x14002d130  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14002d137  cmp     cs:WPP_RECORDER_INITIALIZED, r8; __annotation("TMF:",
0x14002d13e  jz      loc_14002D23C
0x14002d144  mov     r9d, 125h
0x14002d14a  mov     [rsp+70h+var_50], rax
0x14002d14f  mov     r8d, 5
0x14002d155  mov     dl, 2
0x14002d157  mov     rcx, r14
0x14002d15a  call    WPP_RECORDER_SF_
0x14002d15f  test    r15b, r15b
0x14002d162  jz      loc_14002D23C
0x14002d168  mov     rcx, [rbx+870h]; P
0x14002d16f  mov     r14d, 64334855h
0x14002d175  test    rcx, rcx
0x14002d178  jz      short loc_14002D189
0x14002d17a  mov     edx, r14d; Tag
0x14002d17d  call    cs:__imp_ExFreePoolWithTag
0x14002d184  nop     dword ptr [rax+rax+00h]
0x14002d189  bt      dword ptr [rbx+66Ch], 0Bh
0x14002d191  lea     eax, [r12+0Ch]
0x14002d196  mov     r8d, r14d
0x14002d199  mov     ecx, 40h ; '@'
0x14002d19e  cmovnb  eax, r12d
0x14002d1a2  mov     edx, eax
0x14002d1a4  mov     edi, eax
0x14002d1a6  call    cs:__imp_ExAllocatePool2
0x14002d1ad  nop     dword ptr [rax+rax+00h]
0x14002d1b2  mov     [rbx+870h], rax
0x14002d1b9  mov     rcx, rax
0x14002d1bc  test    rax, rax
0x14002d1bf  jz      loc_14002D246
0x14002d1c5  mov     eax, [rbx+668h]
0x14002d1cb  mov     [rbx+86Ch], edi
0x14002d1d1  test    al, 2
0x14002d1d3  jz      short loc_14002D1F7
0x14002d1d5  mov     eax, 300h
0x14002d1da  cmp     [rbx+7CEh], ax
0x14002d1e1  jnb     short loc_14002D201
0x14002d1e3  movsd   xmm0, qword ptr cs:aMsft20; "MSFT20"
0x14002d1eb  movsd   qword ptr [rcx], xmm0
0x14002d1ef  mov     eax, dword ptr cs:aMsft20+8; "20"
0x14002d1f5  jmp     short loc_14002D213
0x14002d1f7  bt      dword ptr [rbx+66Ch], 0Bh
0x14002d1ff  jnb     short loc_14002D21A
0x14002d201  movsd   xmm0, qword ptr cs:aMsft30; "MSFT30"
0x14002d209  movsd   qword ptr [rcx], xmm0
0x14002d20d  mov     eax, dword ptr cs:aMsft30+8; "30"
0x14002d213  mov     [rcx+8], eax
0x14002d216  add     rcx, 0Ch; void *
0x14002d21a  mov     r8d, esi
0x14002d21d  lea     rdx, [rbx+6CEh]; Src
0x14002d224  sub     r8, 2; Size
0x14002d228  call    memmove
0x14002d22d  lock or dword ptr [rbx+668h], 40h
0x14002d235  mov     edi, 0FEDh
0x14002d23a  jmp     short loc_14002D26B
0x14002d23c  mov     dword ptr [rbx+988h], 40010018h
0x14002d246  test    cs:byte_14006ED41, 1
0x14002d24d  mov     edi, 0FE1h
0x14002d252  jz      short loc_14002D26B
0x14002d254  mov     r9, [rbx+18h]
0x14002d258  lea     r8, [rbx+5F4h]
0x14002d25f  lea     rdx, USBHUB3_ETW_EVENT_INVALID_SERIAL_NUMBER_STRING_DESCRIPTOR
0x14002d266  call    McTemplateK0p_EtwWriteTransfer
0x14002d26b  mov     rbx, [rsp+70h+arg_18]
0x14002d273  mov     eax, edi
0x14002d275  add     rsp, 70h
0x14002d279  pop     r15
0x14002d27b  pop     r14
0x14002d27d  pop     r13
0x14002d27f  pop     r12
0x14002d281  pop     rdi
0x14002d282  pop     rsi
0x14002d283  pop     rbp
0x14002d284  retn
```
