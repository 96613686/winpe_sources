# HUBHTX_ValidateAndCacheHubConfigDescriptor

- ea: `0x1400063b4`
- end: `0x1400065aa`
- name: `HUBHTX_ValidateAndCacheHubConfigDescriptor`
- size: `502`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x14000a100`

## callees

- `0x1400025a4`
- `0x1400063b4`
- `0x1400067ac`
- `0x14003cce8`
- `0x140045570`
- `0x140045640`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140006550`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006571`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006550`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006571`
- `ntoskrnl!ExAllocatePool2` at `0x140006435`
- `ntoskrnl!ExAllocatePool2` at `0x140006435`

## pseudocode

```c
__int64 __fastcall HUBHTX_ValidateAndCacheHubConfigDescriptor(__int64 a1)
{
  unsigned __int16 *v1; // rbx
  unsigned __int16 *v3; // rsi
  unsigned int v4; // eax
  void *Pool2; // rax
  int v6; // edx
  int v7; // ebx
  unsigned int v8; // edx
  __int64 v9; // rcx
  __int16 v10; // cx
  int v11; // edx
  void *v12; // rcx
  _WORD v14[2]; // [rsp+40h] [rbp-48h] BYREF
  int v15; // [rsp+44h] [rbp-44h]
  __int128 v16; // [rsp+48h] [rbp-40h]
  __int64 (__fastcall *v17)(); // [rsp+58h] [rbp-30h]
  __int64 (__fastcall *v18)(); // [rsp+60h] [rbp-28h]
  __int64 v19; // [rsp+68h] [rbp-20h]
  __int64 v20; // [rsp+70h] [rbp-18h]

  v1 = *(unsigned __int16 **)(a1 + 1272);
  v14[1] = 0;
  v16 = 0;
  v20 = 0;
  v3 = 0;
  v14[0] = *(_WORD *)(a1 + 2474);
  v15 = *(_DWORD *)(a1 + 256);
  v17 = HUBMISC_LogDescriptorValidationErrorForHub;
  v18 = HUBMISC_LogDescriptorValidationWarningForHub;
  v4 = v1[1];
  v19 = a1;
  if ( (unsigned __int16)v4 >= 0xFFu )
  {
LABEL_7:
    v8 = *(unsigned __int16 *)(a1 + 2620);
    v9 = *(_QWORD *)(a1 + 1272);
    if ( (unsigned __int16)v8 >= *(_WORD *)(v9 + 2) )
      v8 = *(unsigned __int16 *)(v9 + 2);
    if ( HUBDESC_ValidateConfigurationDescriptorSet(v9, v8, (__int64)v14, *(_QWORD *)(a1 + 2536), 0) )
    {
      v10 = *(_WORD *)(a1 + 2620);
      v11 = *(unsigned __int16 *)(*(_QWORD *)(a1 + 1272) + 2LL);
      if ( (_WORD)v11 == v10 )
      {
        v7 = 0;
        goto LABEL_16;
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v11) = 2;
        WPP_RECORDER_SF_dD(
          *(_QWORD *)(a1 + 2536),
          v11,
          3,
          22,
          (__int64)WPP_70469c384dd13630d566350a6f2705ad_Traceguids,
          *(_WORD *)(*(_QWORD *)(a1 + 1272) + 2LL),
          v10);
      }
      ((void (__fastcall *)(__int64, __int64))v17)(v19, 61);
    }
    v7 = -1073741823;
    goto LABEL_16;
  }
  v3 = v1;
  Pool2 = (void *)ExAllocatePool2(64, v4, 1748191317);
  *(_QWORD *)(a1 + 1272) = Pool2;
  if ( Pool2 )
  {
    memmove(Pool2, v1, v1[1]);
    goto LABEL_7;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v6) = 2;
    WPP_RECORDER_SF_(*(_QWORD *)(a1 + 2536), v6, 3, 21, (__int64)WPP_70469c384dd13630d566350a6f2705ad_Traceguids);
  }
  v7 = -1073741670;
LABEL_16:
  if ( v3 )
    ExFreePoolWithTag(v3, 0x68334855u);
  if ( v7 < 0 )
  {
    v12 = *(void **)(a1 + 1272);
    if ( v12 )
    {
      ExFreePoolWithTag(v12, 0x68334855u);
      *(_QWORD *)(a1 + 1272) = 0;
    }
  }
  return ((v7 >> 31) & 0xFFFFFFF8) + 2053;
}

```

## disassembly

```asm
0x1400063b4  mov     r11, rsp
0x1400063b7  mov     [r11+8], rbx
0x1400063bb  mov     [r11+10h], rsi
0x1400063bf  push    rdi
0x1400063c0  sub     rsp, 80h
0x1400063c7  mov     rbx, [rcx+4F8h]
0x1400063ce  xor     eax, eax
0x1400063d0  mov     [rsp+88h+var_46], ax
0x1400063d5  xorps   xmm0, xmm0
0x1400063d8  movdqu  [rsp+88h+var_40], xmm0
0x1400063de  mov     [r11-18h], rax
0x1400063e2  mov     rdi, rcx
0x1400063e5  movzx   eax, word ptr [rcx+9AAh]
0x1400063ec  xor     esi, esi
0x1400063ee  mov     [rsp+88h+var_48], ax
0x1400063f3  mov     eax, [rcx+100h]
0x1400063f9  mov     [rsp+88h+var_44], eax
0x1400063fd  lea     rax, HUBMISC_LogDescriptorValidationErrorForHub
0x140006404  mov     [r11-30h], rax
0x140006408  lea     rax, HUBMISC_LogDescriptorValidationWarningForHub
0x14000640f  mov     [r11-28h], rax
0x140006413  movzx   eax, word ptr [rbx+2]
0x140006417  mov     [r11-20h], rcx
0x14000641b  mov     ecx, 0FFh
0x140006420  cmp     ax, cx
0x140006423  jnb     short loc_14000649B
0x140006425  mov     edx, eax
0x140006427  mov     ecx, 40h ; '@'
0x14000642c  mov     r8d, 68334855h
0x140006432  mov     rsi, rbx
0x140006435  call    cs:__imp_ExAllocatePool2
0x14000643c  nop     dword ptr [rax+rax+00h]
0x140006441  mov     [rdi+4F8h], rax
0x140006448  test    rax, rax
0x14000644b  jnz     short loc_14000648B
0x14000644d  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140006454  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000645b  jz      short loc_140006481
0x14000645d  mov     rcx, [rdi+9E8h]
0x140006464  lea     rax, WPP_70469c384dd13630d566350a6f2705ad_Traceguids
0x14000646b  mov     r9d, 15h
0x140006471  mov     [rsp+88h+var_68], rax
0x140006476  mov     dl, 2
0x140006478  lea     r8d, [r9-12h]
0x14000647c  call    WPP_RECORDER_SF_
0x140006481  mov     ebx, 0C000009Ah
0x140006486  jmp     loc_140006543
0x14000648b  movzx   r8d, word ptr [rbx+2]; Size
0x140006490  mov     rdx, rbx; Src
0x140006493  mov     rcx, rax; void *
0x140006496  call    memmove
0x14000649b  movzx   edx, word ptr [rdi+0A3Ch]
0x1400064a2  lea     r8, [rsp+88h+var_48]
0x1400064a7  mov     rcx, [rdi+4F8h]
0x1400064ae  mov     r9, [rdi+9E8h]
0x1400064b5  mov     [rsp+88h+var_68], 0
0x1400064be  movzx   eax, word ptr [rcx+2]
0x1400064c2  cmp     dx, ax
0x1400064c5  cmovnb  edx, eax
0x1400064c8  call    HUBDESC_ValidateConfigurationDescriptorSet
0x1400064cd  test    al, al
0x1400064cf  jnz     short loc_1400064D8
0x1400064d1  mov     ebx, 0C0000001h
0x1400064d6  jmp     short loc_140006543
0x1400064d8  mov     rax, [rdi+4F8h]
0x1400064df  movzx   ecx, word ptr [rdi+0A3Ch]
0x1400064e6  movzx   edx, word ptr [rax+2]
0x1400064ea  cmp     dx, cx
0x1400064ed  jz      short loc_140006541
0x1400064ef  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400064f6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400064fd  jz      short loc_14000652B
0x1400064ff  mov     [rsp+88h+var_58], ecx
0x140006503  lea     rax, WPP_70469c384dd13630d566350a6f2705ad_Traceguids
0x14000650a  mov     rcx, [rdi+9E8h]
0x140006511  mov     r9d, 16h
0x140006517  mov     [rsp+88h+var_60], edx
0x14000651b  mov     dl, 2
0x14000651d  mov     [rsp+88h+var_68], rax
0x140006522  lea     r8d, [r9-13h]
0x140006526  call    WPP_RECORDER_SF_dD
0x14000652b  mov     rcx, [rsp+88h+var_20]
0x140006530  mov     edx, 3Dh ; '='
0x140006535  mov     rax, [rsp+88h+var_30]
0x14000653a  call    _guard_dispatch_icall
0x14000653f  jmp     short loc_1400064D1
0x140006541  xor     ebx, ebx
0x140006543  test    rsi, rsi
0x140006546  jz      short loc_14000655C
0x140006548  mov     edx, 68334855h; Tag
0x14000654d  mov     rcx, rsi; P
0x140006550  call    cs:__imp_ExFreePoolWithTag
0x140006557  nop     dword ptr [rax+rax+00h]
0x14000655c  test    ebx, ebx
0x14000655e  jns     short loc_140006588
0x140006560  mov     rcx, [rdi+4F8h]; P
0x140006567  test    rcx, rcx
0x14000656a  jz      short loc_140006588
0x14000656c  mov     edx, 68334855h; Tag
0x140006571  call    cs:__imp_ExFreePoolWithTag
0x140006578  nop     dword ptr [rax+rax+00h]
0x14000657d  mov     qword ptr [rdi+4F8h], 0
0x140006588  sar     ebx, 1Fh
0x14000658b  lea     r11, [rsp+88h+var_8]
0x140006593  mov     rsi, [r11+18h]
0x140006597  and     ebx, 0FFFFFFF8h
0x14000659a  lea     eax, [rbx+805h]
0x1400065a0  mov     rbx, [r11+10h]
0x1400065a4  mov     rsp, r11
0x1400065a7  pop     rdi
0x1400065a8  retn
```
