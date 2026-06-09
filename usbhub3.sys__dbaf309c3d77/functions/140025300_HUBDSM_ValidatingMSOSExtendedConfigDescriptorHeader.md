# HUBDSM_ValidatingMSOSExtendedConfigDescriptorHeader

- ea: `0x140025300`
- end: `0x14002542c`
- name: `HUBDSM_ValidatingMSOSExtendedConfigDescriptorHeader`
- size: `300`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1400083b4`
- `0x140025300`
- `0x14003daa0`
- `0x140045570`

## pseudocode

```c
__int64 __fastcall HUBDSM_ValidatingMSOSExtendedConfigDescriptorHeader(__int64 a1)
{
  __int64 v1; // rbx
  unsigned int v2; // edi
  __int64 v3; // rax
  __int64 v4; // r9
  int v5; // edx
  bool v6; // cf
  int v7; // edx
  bool v8; // zf
  __int64 v9; // r9
  __int64 v10; // rcx
  __int64 v12; // [rsp+20h] [rbp-48h] BYREF
  __int64 v13; // [rsp+28h] [rbp-40h]
  int v14; // [rsp+30h] [rbp-38h]
  int v15; // [rsp+34h] [rbp-34h]
  void (__fastcall *v16)(__int64, ULONG); // [rsp+38h] [rbp-30h]
  void (__fastcall *v17)(__int64, ULONG); // [rsp+40h] [rbp-28h]
  __int64 v18; // [rsp+48h] [rbp-20h]
  _BOOL8 v19; // [rsp+50h] [rbp-18h]

  v1 = *(_QWORD *)(a1 + 960);
  v2 = 4077;
  v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         WdfDriverGlobals->Driver,
         off_14006B2C0);
  v4 = *(_QWORD *)(v1 + 8);
  v19 = 0;
  v5 = *(_DWORD *)(v3 + 4);
  v13 = 0;
  WORD1(v12) = 0;
  v15 = 0;
  LOWORD(v12) = *(_WORD *)(v1 + 1998);
  HIDWORD(v12) = *(_DWORD *)(v1 + 172);
  v18 = v1;
  *(_WORD *)((char *)&v13 + 5) = (v5 & 0x20) != 0;
  LOBYTE(v3) = (v5 & 0x2000) != 0;
  v6 = (v5 & 0x4000) != 0;
  v7 = *(_DWORD *)(v1 + 264);
  HIBYTE(v13) = v3;
  v8 = (*(_DWORD *)(v1 + 1652) & 0x200000) == 0;
  BYTE4(v13) = v6;
  LODWORD(v3) = *(_DWORD *)(v4 + 220);
  v9 = *(_QWORD *)(v4 + 1432);
  v14 = v3;
  v16 = HUBMISC_LogDescriptorValidationErrorForDevice;
  v19 = !v8;
  v17 = HUBMISC_LogDescriptorValidationWarningForDevice;
  if ( !HUBDESC_ValidateMSOSExtendedConfigDescriptorHeader(v1 + 1740, v7, (__int64)&v12, v9) )
  {
    *(_DWORD *)(v1 + 2440) = 1073807382;
    v2 = 4065;
    if ( (byte_14006ED41 & 1) != 0 )
      McTemplateK0p_EtwWriteTransfer(
        v10,
        (const EVENT_DESCRIPTOR *)USBHUB3_ETW_EVENT_INVALID_MSOS_EXTENDED_CONFIGURATION_DESCRIPTOR_HEADER,
        (const GUID *)(v1 + 1524),
        *(_QWORD *)(v1 + 24),
        v12,
        v13);
  }
  return v2;
}

```

## disassembly

```asm
0x140025300  push    rbp
0x140025302  push    rbx
0x140025303  push    rsi
0x140025304  push    rdi
0x140025305  mov     rbp, rsp
0x140025308  sub     rsp, 68h
0x14002530c  mov     rbx, [rcx+3C0h]
0x140025313  mov     edi, 0FEDh
0x140025318  mov     rcx, cs:WdfDriverGlobals
0x14002531f  mov     rax, cs:WdfFunctions_01015
0x140025326  mov     r8, cs:off_14006B2C0
0x14002532d  mov     rdx, [rcx]
0x140025330  mov     rax, [rax+650h]
0x140025337  call    _guard_dispatch_icall
0x14002533c  mov     r9, [rbx+8]
0x140025340  xor     r8d, r8d
0x140025343  movzx   ecx, r8b
0x140025347  mov     [rbp+var_18], r8
0x14002534b  mov     edx, [rax+4]
0x14002534e  xor     eax, eax
0x140025350  mov     [rbp+var_40], rax
0x140025354  lea     esi, [r8+1]
0x140025358  mov     [rbp+var_46], ax
0x14002535c  lea     r8, [rbp+var_48]
0x140025360  mov     [rbp+var_34], eax
0x140025363  test    dl, 20h
0x140025366  movzx   eax, word ptr [rbx+7CEh]
0x14002536d  mov     [rbp+var_48], ax
0x140025371  mov     eax, [rbx+0ACh]
0x140025377  mov     [rbp+var_44], eax
0x14002537a  movzx   eax, byte ptr [rbp+var_40+5]
0x14002537e  cmovnz  eax, esi
0x140025381  mov     [rbp+var_20], rbx
0x140025385  mov     byte ptr [rbp+var_40+5], al
0x140025388  bt      edx, 0Dh
0x14002538c  movzx   eax, byte ptr [rbp+var_40+7]
0x140025390  cmovb   eax, esi
0x140025393  bt      edx, 0Eh
0x140025397  mov     edx, [rbx+108h]
0x14002539d  mov     byte ptr [rbp+var_40+7], al
0x1400253a0  movzx   eax, byte ptr [rbp+var_40+4]
0x1400253a4  cmovb   eax, esi
0x1400253a7  test    dword ptr [rbx+674h], 200000h
0x1400253b1  mov     byte ptr [rbp+var_40+4], al
0x1400253b4  mov     eax, [r9+0DCh]
0x1400253bb  cmovnz  ecx, esi
0x1400253be  mov     r9, [r9+598h]
0x1400253c5  mov     [rbp+var_38], eax
0x1400253c8  lea     rax, HUBMISC_LogDescriptorValidationErrorForDevice
0x1400253cf  mov     [rbp+var_30], rax
0x1400253d3  lea     rax, HUBMISC_LogDescriptorValidationWarningForDevice
0x1400253da  mov     byte ptr [rbp+var_18], cl
0x1400253dd  lea     rcx, [rbx+6CCh]
0x1400253e4  mov     [rbp+var_28], rax
0x1400253e8  call    HUBDESC_ValidateMSOSExtendedConfigDescriptorHeader
0x1400253ed  test    al, al
0x1400253ef  jnz     short loc_140025420
0x1400253f1  mov     dword ptr [rbx+988h], 40010016h
0x1400253fb  mov     edi, 0FE1h
0x140025400  test    cs:byte_14006ED41, sil
0x140025407  jz      short loc_140025420
0x140025409  mov     r9, [rbx+18h]
0x14002540d  lea     r8, [rbx+5F4h]
0x140025414  lea     rdx, USBHUB3_ETW_EVENT_INVALID_MSOS_EXTENDED_CONFIGURATION_DESCRIPTOR_HEADER
0x14002541b  call    McTemplateK0p_EtwWriteTransfer
0x140025420  mov     eax, edi
0x140025422  add     rsp, 68h
0x140025426  pop     rdi
0x140025427  pop     rsi
0x140025428  pop     rbx
0x140025429  pop     rbp
0x14002542a  retn
```
