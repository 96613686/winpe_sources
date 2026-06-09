# HUBDTX_ValidateAndCacheLanguageIdStringDescriptor

- ea: `0x14002cbe0`
- end: `0x14002cd9a`
- name: `HUBDTX_ValidateAndCacheLanguageIdStringDescriptor`
- size: `442`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140024d70`

## callees

- `0x1400067ac`
- `0x1400083b4`
- `0x14002cbe0`
- `0x1400399c4`
- `0x140045570`
- `0x140045640`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14002cd00`
- `ntoskrnl!ExAllocatePool2` at `0x14002cd00`

## pseudocode

```c
__int64 __fastcall HUBDTX_ValidateAndCacheLanguageIdStringDescriptor(__int64 a1)
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
  void (__fastcall *v20)(__int64, ULONG); // [rsp+48h] [rbp-30h]
  void (__fastcall *v21)(__int64, ULONG); // [rsp+50h] [rbp-28h]
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
    *(_QWORD *)(a1 + 2032) = Pool2;
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
        88,
        (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids);
    }
  }
  else
  {
    *(_DWORD *)(a1 + 2440) = 1073807380;
  }
  v13 = 4065;
  if ( (byte_14006ED41 & 1) != 0 )
    McTemplateK0p_EtwWriteTransfer(
      v9,
      (const EVENT_DESCRIPTOR *)USBHUB3_ETW_EVENT_INVALID_LANGUAGE_ID_DESCRIPTOR,
      (const GUID *)(a1 + 1524),
      *(_QWORD *)(a1 + 24));
  return v13;
}

```

## disassembly

```asm
0x14002cbe0  push    rbp
0x14002cbe2  push    rbx
0x14002cbe3  push    rsi
0x14002cbe4  push    rdi
0x14002cbe5  push    r12
0x14002cbe7  push    r14
0x14002cbe9  mov     rbp, rsp
0x14002cbec  sub     rsp, 78h
0x14002cbf0  mov     ebx, [rcx+108h]
0x14002cbf6  lea     r14, [rcx+6CCh]
0x14002cbfd  mov     rax, cs:WdfFunctions_01015
0x14002cc04  mov     rdi, rcx
0x14002cc07  mov     rcx, cs:WdfDriverGlobals
0x14002cc0e  mov     r8, cs:off_14006B2C0
0x14002cc15  mov     rax, [rax+650h]
0x14002cc1c  mov     rdx, [rcx]
0x14002cc1f  call    _guard_dispatch_icall
0x14002cc24  xor     ecx, ecx
0x14002cc26  mov     [rbp+var_20], rdi
0x14002cc2a  mov     [rbp+var_40], rcx
0x14002cc2e  lea     r8, [rbp+arg_0]
0x14002cc32  xor     edx, edx
0x14002cc34  mov     [rbp+var_46], cx
0x14002cc38  mov     [rbp+var_34], ecx
0x14002cc3b  movzx   ecx, word ptr [rdi+7CEh]
0x14002cc42  mov     [rbp+var_48], cx
0x14002cc46  mov     ecx, [rdi+0ACh]
0x14002cc4c  lea     r12d, [rdx+1]
0x14002cc50  mov     [rbp+var_44], ecx
0x14002cc53  mov     ecx, [rax+4]
0x14002cc56  test    cl, 20h
0x14002cc59  movzx   eax, byte ptr [rbp+var_40+5]
0x14002cc5d  cmovnz  eax, r12d
0x14002cc61  mov     [rbp+var_18], rdx
0x14002cc65  mov     byte ptr [rbp+var_40+5], al
0x14002cc68  bt      ecx, 0Dh
0x14002cc6c  movzx   eax, byte ptr [rbp+var_40+7]
0x14002cc70  cmovb   eax, r12d
0x14002cc74  mov     [rbp+arg_0], edx
0x14002cc77  mov     byte ptr [rbp+var_40+7], al
0x14002cc7a  bt      ecx, 0Eh
0x14002cc7e  movzx   eax, byte ptr [rbp+var_40+4]
0x14002cc82  cmovb   eax, r12d
0x14002cc86  movzx   ecx, dl
0x14002cc89  test    dword ptr [rdi+674h], 200000h
0x14002cc93  mov     edx, ebx
0x14002cc95  mov     byte ptr [rbp+var_40+4], al
0x14002cc98  cmovnz  ecx, r12d
0x14002cc9c  mov     byte ptr [rbp+var_18], cl
0x14002cc9f  mov     rcx, [rdi+8]
0x14002cca3  mov     eax, [rcx+0DCh]
0x14002cca9  mov     [rbp+var_38], eax
0x14002ccac  lea     rax, HUBMISC_LogDescriptorValidationErrorForDevice
0x14002ccb3  mov     [rbp+var_30], rax
0x14002ccb7  lea     rax, HUBMISC_LogDescriptorValidationWarningForDevice
0x14002ccbe  mov     [rbp+var_28], rax
0x14002ccc2  lea     rax, [rbp+var_48]
0x14002ccc6  mov     [rsp+78h+var_50], rax
0x14002cccb  mov     rax, [rcx+598h]
0x14002ccd2  mov     rcx, r14
0x14002ccd5  mov     [rsp+78h+var_58], rax
0x14002ccda  call    HUBDESC_InternalValidateStringDescriptor
0x14002ccdf  test    al, al
0x14002cce1  jnz     short loc_14002CCEF
0x14002cce3  mov     dword ptr [rdi+988h], 40010014h
0x14002cced  jmp     short loc_14002CD50
0x14002ccef  movzx   esi, byte ptr [r14]
0x14002ccf3  mov     r8d, 64334855h
0x14002ccf9  mov     edx, esi
0x14002ccfb  mov     ecx, 40h ; '@'
0x14002cd00  call    cs:__imp_ExAllocatePool2
0x14002cd07  nop     dword ptr [rax+rax+00h]
0x14002cd0c  mov     [rdi+7F0h], rax
0x14002cd13  test    rax, rax
0x14002cd16  jnz     short loc_14002CD77
0x14002cd18  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002cd1f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002cd26  jz      short loc_14002CD50
0x14002cd28  mov     rcx, [rdi+8]
0x14002cd2c  lea     rax, WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids
0x14002cd33  mov     r9d, 58h ; 'X'
0x14002cd39  mov     [rsp+78h+var_58], rax
0x14002cd3e  mov     dl, 2
0x14002cd40  mov     rcx, [rcx+598h]
0x14002cd47  lea     r8d, [r9-53h]
0x14002cd4b  call    WPP_RECORDER_SF_
0x14002cd50  test    cs:byte_14006ED41, r12b
0x14002cd57  mov     ebx, 0FE1h
0x14002cd5c  jz      short loc_14002CD8A
0x14002cd5e  mov     r9, [rdi+18h]
0x14002cd62  lea     r8, [rdi+5F4h]
0x14002cd69  lea     rdx, USBHUB3_ETW_EVENT_INVALID_LANGUAGE_ID_DESCRIPTOR
0x14002cd70  call    McTemplateK0p_EtwWriteTransfer
0x14002cd75  jmp     short loc_14002CD8A
0x14002cd77  mov     r8, rsi; Size
0x14002cd7a  mov     rdx, r14; Src
0x14002cd7d  mov     rcx, rax; void *
0x14002cd80  mov     ebx, 0FEDh
0x14002cd85  call    memmove
0x14002cd8a  mov     eax, ebx
0x14002cd8c  add     rsp, 78h
0x14002cd90  pop     r14
0x14002cd92  pop     r12
0x14002cd94  pop     rdi
0x14002cd95  pop     rsi
0x14002cd96  pop     rbx
0x14002cd97  pop     rbp
0x14002cd98  retn
```
