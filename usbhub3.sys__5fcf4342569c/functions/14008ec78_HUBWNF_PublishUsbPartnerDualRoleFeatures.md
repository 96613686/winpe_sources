# HUBWNF_PublishUsbPartnerDualRoleFeatures

- ea: `0x14008ec78`
- end: `0x14008ecd9`
- name: `HUBWNF_PublishUsbPartnerDualRoleFeatures`
- size: `97`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x14002bc18`
- `0x140081660`

## callees

- `0x140045530`

## import_xrefs

- `ntoskrnl!ZwUpdateWnfStateData` at `0x14008ecba`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x14008ecba`

## pseudocode

```c
__int64 __fastcall HUBWNF_PublishUsbPartnerDualRoleFeatures(__int64 a1, char a2, int a3)
{
  __int64 v4; // [rsp+40h] [rbp-28h] BYREF
  char v5; // [rsp+48h] [rbp-20h]
  int v6; // [rsp+49h] [rbp-1Fh]

  v4 = a1;
  v5 = a2;
  v6 = a3;
  return ZwUpdateWnfStateData(&WNF_USB_TYPE_C_PARTNER_STATE, &v4, 13, 0, 0, 0, 0);
}

```

## disassembly

```asm
0x14008ec78  mov     r11, rsp
0x14008ec7b  sub     rsp, 68h
0x14008ec7f  mov     rax, cs:__security_cookie
0x14008ec86  xor     rax, rsp
0x14008ec89  mov     [rsp+68h+var_18], rax
0x14008ec8e  xor     eax, eax
0x14008ec90  mov     [r11-28h], rcx
0x14008ec94  mov     [rsp+68h+var_20], dl
0x14008ec98  lea     rcx, WNF_USB_TYPE_C_PARTNER_STATE
0x14008ec9f  mov     [rsp+68h+var_38], eax
0x14008eca3  lea     rdx, [r11-28h]
0x14008eca7  mov     [r11-1Fh], r8d
0x14008ecab  xor     r9d, r9d
0x14008ecae  mov     [rsp+68h+var_40], eax
0x14008ecb2  lea     r8d, [rax+0Dh]
0x14008ecb6  mov     [r11-48h], rax
0x14008ecba  call    cs:__imp_ZwUpdateWnfStateData
0x14008ecc1  nop     dword ptr [rax+rax+00h]
0x14008ecc6  mov     rcx, [rsp+68h+var_18]
0x14008eccb  xor     rcx, rsp; StackCookie
0x14008ecce  call    __security_check_cookie
0x14008ecd3  add     rsp, 68h
0x14008ecd7  retn
```
