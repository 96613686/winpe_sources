# HUBDTX_ValidateAndCacheProductIdStringDescriptor

- ea: `0x14002cda0`
- end: `0x14002cf5a`
- name: `HUBDTX_ValidateAndCacheProductIdStringDescriptor`
- size: `442`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140024d90`

## callees

- `0x1400067ac`
- `0x1400083b4`
- `0x14002cda0`
- `0x1400399c4`
- `0x140045570`
- `0x140045640`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14002cec0`
- `ntoskrnl!ExAllocatePool2` at `0x14002cec0`

## pseudocode

```c
__int64 __fastcall HUBDTX_ValidateAndCacheProductIdStringDescriptor(__int64 a1)
{
  unsigned int v1; // ebx
  unsigned __int8 *v2; // r14
  __int64 v4; // rax
  int v5; // ecx
  bool v6; // zf
  __int64 v7; // rcx
  __int64 v8; // r9
  __int64 v9; // rcx
  size_t v10; // rsi
  void *Pool2; // rax
  int v12; // edx
  unsigned int v13; // ebx
  _WORD v15[2]; // [rsp+30h] [rbp-48h] BYREF
  int v16; // [rsp+34h] [rbp-44h]
  __int64 v17; // [rsp+38h] [rbp-40h]
  int v18; // [rsp+40h] [rbp-38h]
  int v19; // [rsp+44h] [rbp-34h]
  void (__fastcall *v20)(__int64, ULONG, __int64, __int64); // [rsp+48h] [rbp-30h]
  void (__fastcall *v21)(__int64, ULONG, __int64, __int64); // [rsp+50h] [rbp-28h]
  __int64 v22; // [rsp+58h] [rbp-20h]
  _BOOL8 v23; // [rsp+60h] [rbp-18h]
  unsigned int v24; // [rsp+B0h] [rbp+38h] BYREF

  v1 = *(_DWORD *)(a1 + 264);
  v2 = (unsigned __int8 *)(a1 + 1740);
  v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         WdfDriverGlobals->Driver,
         off_14006B2C0);
  v22 = a1;
  v17 = 0;
  v15[1] = 0;
  v19 = 0;
  v15[0] = *(_WORD *)(a1 + 1998);
  v16 = *(_DWORD *)(a1 + 172);
  v5 = *(_DWORD *)(v4 + 4);
  v23 = 0;
  *(_WORD *)((char *)&v17 + 5) = (v5 & 0x20) != 0;
  v24 = 0;
  HIBYTE(v17) = (v5 & 0x2000) != 0;
  v6 = (*(_DWORD *)(a1 + 1652) & 0x200000) == 0;
  BYTE4(v17) = (v5 & 0x4000) != 0;
  v23 = !v6;
  v7 = *(_QWORD *)(a1 + 8);
  v18 = *(_DWORD *)(v7 + 220);
  v20 = HUBMISC_LogDescriptorValidationErrorForDevice;
  v21 = HUBMISC_LogDescriptorValidationWarningForDevice;
  if ( HUBDESC_InternalValidateStringDescriptor((char *)v2, v1, &v24, v8, *(_QWORD *)(v7 + 1432), (__int64)v15) )
  {
    v10 = *v2;
    Pool2 = (void *)ExAllocatePool2(64, v10, 1681082453);
    *(_QWORD *)(a1 + 2040) = Pool2;
    if ( Pool2 )
    {
      v13 = 4077;
      memmove(Pool2, v2, v10);
      return v13;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_(
        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL),
        v12,
        5,
        93,
        (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids);
    }
  }
  else
  {
    *(_DWORD *)(a1 + 2440) = 1073807383;
  }
  v13 = 4065;
  if ( (byte_14006ED41 & 1) != 0 )
    McTemplateK0p_EtwWriteTransfer(
      v9,
      (const EVENT_DESCRIPTOR *)USBHUB3_ETW_EVENT_INVALID_PRODUCT_ID_STRING_DESCRIPTOR,
      (const GUID *)(a1 + 1524),
      *(_QWORD *)(a1 + 24));
  return v13;
}

```

## disassembly

```asm
0x14002cda0  push    rbp
0x14002cda2  push    rbx
0x14002cda3  push    rsi
0x14002cda4  push    rdi
0x14002cda5  push    r12
0x14002cda7  push    r14
0x14002cda9  mov     rbp, rsp
0x14002cdac  sub     rsp, 78h
0x14002cdb0  mov     ebx, [rcx+108h]
0x14002cdb6  lea     r14, [rcx+6CCh]
0x14002cdbd  mov     rax, cs:WdfFunctions_01015
0x14002cdc4  mov     rdi, rcx
0x14002cdc7  mov     rcx, cs:WdfDriverGlobals
0x14002cdce  mov     r8, cs:off_14006B2C0
0x14002cdd5  mov     rax, [rax+650h]
0x14002cddc  mov     rdx, [rcx]
0x14002cddf  call    _guard_dispatch_icall
0x14002cde4  xor     ecx, ecx
0x14002cde6  mov     [rbp+var_20], rdi
0x14002cdea  mov     [rbp+var_40], rcx
0x14002cdee  lea     r8, [rbp+arg_0]
0x14002cdf2  xor     edx, edx
0x14002cdf4  mov     [rbp+var_46], cx
0x14002cdf8  mov     [rbp+var_34], ecx
0x14002cdfb  movzx   ecx, word ptr [rdi+7CEh]
0x14002ce02  mov     [rbp+var_48], cx
0x14002ce06  mov     ecx, [rdi+0ACh]
0x14002ce0c  lea     r12d, [rdx+1]
0x14002ce10  mov     [rbp+var_44], ecx
0x14002ce13  mov     ecx, [rax+4]
0x14002ce16  test    cl, 20h
0x14002ce19  movzx   eax, byte ptr [rbp+var_40+5]
0x14002ce1d  cmovnz  eax, r12d
0x14002ce21  mov     [rbp+var_18], rdx
0x14002ce25  mov     byte ptr [rbp+var_40+5], al
0x14002ce28  bt      ecx, 0Dh
0x14002ce2c  movzx   eax, byte ptr [rbp+var_40+7]
0x14002ce30  cmovb   eax, r12d
0x14002ce34  mov     [rbp+arg_0], edx
0x14002ce37  mov     byte ptr [rbp+var_40+7], al
0x14002ce3a  bt      ecx, 0Eh
0x14002ce3e  movzx   eax, byte ptr [rbp+var_40+4]
0x14002ce42  cmovb   eax, r12d
0x14002ce46  movzx   ecx, dl
0x14002ce49  test    dword ptr [rdi+674h], 200000h
0x14002ce53  mov     edx, ebx
0x14002ce55  mov     byte ptr [rbp+var_40+4], al
0x14002ce58  cmovnz  ecx, r12d
0x14002ce5c  mov     byte ptr [rbp+var_18], cl
0x14002ce5f  mov     rcx, [rdi+8]
0x14002ce63  mov     eax, [rcx+0DCh]
0x14002ce69  mov     [rbp+var_38], eax
0x14002ce6c  lea     rax, HUBMISC_LogDescriptorValidationErrorForDevice
0x14002ce73  mov     [rbp+var_30], rax
0x14002ce77  lea     rax, HUBMISC_LogDescriptorValidationWarningForDevice
0x14002ce7e  mov     [rbp+var_28], rax
0x14002ce82  lea     rax, [rbp+var_48]
0x14002ce86  mov     [rsp+78h+var_50], rax
0x14002ce8b  mov     rax, [rcx+598h]
0x14002ce92  mov     rcx, r14
0x14002ce95  mov     [rsp+78h+var_58], rax
0x14002ce9a  call    HUBDESC_InternalValidateStringDescriptor
0x14002ce9f  test    al, al
0x14002cea1  jnz     short loc_14002CEAF
0x14002cea3  mov     dword ptr [rdi+988h], 40010017h
0x14002cead  jmp     short loc_14002CF10
0x14002ceaf  movzx   esi, byte ptr [r14]
0x14002ceb3  mov     r8d, 64334855h
0x14002ceb9  mov     edx, esi
0x14002cebb  mov     ecx, 40h ; '@'
0x14002cec0  call    cs:__imp_ExAllocatePool2
0x14002cec7  nop     dword ptr [rax+rax+00h]
0x14002cecc  mov     [rdi+7F8h], rax
0x14002ced3  test    rax, rax
0x14002ced6  jnz     short loc_14002CF37
0x14002ced8  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002cedf  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002cee6  jz      short loc_14002CF10
0x14002cee8  mov     rcx, [rdi+8]
0x14002ceec  lea     rax, WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids
0x14002cef3  mov     r9d, 5Dh ; ']'
0x14002cef9  mov     [rsp+78h+var_58], rax
0x14002cefe  mov     dl, 2
0x14002cf00  mov     rcx, [rcx+598h]
0x14002cf07  lea     r8d, [r9-58h]
0x14002cf0b  call    WPP_RECORDER_SF_
0x14002cf10  test    cs:byte_14006ED41, r12b
0x14002cf17  mov     ebx, 0FE1h
0x14002cf1c  jz      short loc_14002CF4A
0x14002cf1e  mov     r9, [rdi+18h]
0x14002cf22  lea     r8, [rdi+5F4h]
0x14002cf29  lea     rdx, USBHUB3_ETW_EVENT_INVALID_PRODUCT_ID_STRING_DESCRIPTOR
0x14002cf30  call    McTemplateK0p_EtwWriteTransfer
0x14002cf35  jmp     short loc_14002CF4A
0x14002cf37  mov     r8, rsi; Size
0x14002cf3a  mov     rdx, r14; Src
0x14002cf3d  mov     rcx, rax; void *
0x14002cf40  mov     ebx, 0FEDh
0x14002cf45  call    memmove
0x14002cf4a  mov     eax, ebx
0x14002cf4c  add     rsp, 78h
0x14002cf50  pop     r14
0x14002cf52  pop     r12
0x14002cf54  pop     rdi
0x14002cf55  pop     rsi
0x14002cf56  pop     rbx
0x14002cf57  pop     rbp
0x14002cf58  retn
```
