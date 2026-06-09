# WinNARemoveWFPFiltersAtPassive

- ea: `0x14000e980`
- end: `0x14000eb42`
- name: `WinNARemoveWFPFiltersAtPassive`
- size: `450`
- prototype: `__int64 __fastcall(_QWORD *P)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140011870`

## callees

- `0x14000caa0`
- `0x14000e510`
- `0x14000e980`
- `0x14000f99c`
- `0x1400130bc`
- `0x14001ede0`
- `0x14001f140`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000eb0b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000eb0b`

## pseudocode

```c
__int64 __fastcall WinNARemoveWFPFiltersAtPassive(_QWORD *P)
{
  __int64 v1; // rdi
  int v2; // esi
  __int64 v4; // rdx
  __int64 v5; // rcx
  int v6; // r15d
  __int16 v7; // r12
  _BYTE *v8; // rcx
  unsigned int v9; // ebx
  _BYTE *v10; // rcx
  int v11; // r11d
  _BYTE v13[28]; // [rsp+80h] [rbp-19h] BYREF
  _BYTE v14[28]; // [rsp+A0h] [rbp+7h] BYREF

  v1 = P[2];
  v2 = 0;
  if ( (*(_BYTE *)(v1 + 77) & 2) != 0 )
  {
    v2 = WinNatRemovePacketFilterFromWFP(v1);
    if ( v2 < 0 && (*(_BYTE *)(v1 + 77) & 1) == 0 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v5, v4);
  }
  *(_BYTE *)(v1 + 77) &= ~2u;
  v6 = dword_140026104;
  if ( dword_140026104 )
  {
    v7 = *(_WORD *)(v1 + 8);
    v8 = &v13[8];
    *(_OWORD *)v14 = 0;
    *(_WORD *)v14 = v7;
    v9 = 4;
    *(_OWORD *)v13 = 0;
    *(_WORD *)v13 = v7;
    if ( v7 == 2 )
      v8 = &v13[4];
    else
      v9 = 16;
    *(_OWORD *)&v14[12] = 0;
    *(_OWORD *)&v13[12] = 0;
    memmove(v8, (const void *)(v1 + 32), v9);
    v10 = &v14[8];
    if ( v7 == 2 )
      v10 = &v14[4];
    memmove(v10, (const void *)(v1 + 52), v9);
    if ( v6 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x10) != 0 )
    {
      v11 = 28;
      if ( *(_WORD *)v13 == 2 )
        v11 = 16;
      McTemplateK0zqbr1qbr1qqqtxxqq_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
        (unsigned int)WINNAT_WFP_FILTER_EVENT,
        *(unsigned __int8 *)(v1 + 48),
        *(_QWORD *)(v1 + 80) + 344,
        v11,
        (__int64)v13,
        *(_BYTE *)(v1 + 48),
        (__int64)v14,
        *(_BYTE *)(v1 + 68),
        *(_DWORD *)(v1 + 72),
        *(_BYTE *)(v1 + 76),
        v7 == 23,
        *(_QWORD *)(v1 + 88),
        *(_QWORD *)(v1 + 112),
        3,
        v2);
    }
  }
  WinNatDereferencePacketFilter((PVOID)v1);
  ExFreePoolWithTag(P, 0);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14000e980  mov     [rsp-8+arg_8], rbx
0x14000e985  mov     [rsp-8+arg_10], rsi
0x14000e98a  push    rbp
0x14000e98b  push    rdi
0x14000e98c  push    r12
0x14000e98e  push    r14
0x14000e990  push    r15
0x14000e992  lea     rbp, [rsp-37h]
0x14000e997  sub     rsp, 0D0h
0x14000e99e  mov     rax, cs:__security_cookie
0x14000e9a5  xor     rax, rsp
0x14000e9a8  mov     [rbp+57h+var_30], rax
0x14000e9ac  mov     rdi, [rcx+10h]
0x14000e9b0  xor     esi, esi
0x14000e9b2  mov     r14, rcx
0x14000e9b5  test    byte ptr [rdi+4Dh], 2
0x14000e9b9  jz      short loc_14000E9D4
0x14000e9bb  mov     rcx, rdi
0x14000e9be  call    WinNatRemovePacketFilterFromWFP
0x14000e9c3  mov     esi, eax
0x14000e9c5  test    eax, eax
0x14000e9c7  jns     short loc_14000E9D4
0x14000e9c9  test    byte ptr [rdi+4Dh], 1
0x14000e9cd  jnz     short loc_14000E9D4
0x14000e9cf  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14000e9d4  and     byte ptr [rdi+4Dh], 0FDh
0x14000e9d8  mov     r15d, cs:dword_140026104
0x14000e9df  test    r15d, r15d
0x14000e9e2  jz      loc_14000EAFE
0x14000e9e8  movzx   r12d, word ptr [rdi+8]
0x14000e9ed  lea     rcx, [rbp+57h+var_70+8]
0x14000e9f1  xor     eax, eax
0x14000e9f3  lea     rdx, [rdi+20h]; Src
0x14000e9f7  xorps   xmm0, xmm0
0x14000e9fa  xorps   xmm1, xmm1
0x14000e9fd  movups  [rbp+57h+var_50], xmm0
0x14000ea01  cmp     r12w, 2
0x14000ea06  mov     word ptr [rbp+57h+var_50], r12w
0x14000ea0b  lea     ebx, [rax+4]
0x14000ea0e  movups  [rbp+57h+var_70], xmm1
0x14000ea12  lea     eax, [rbx+0Ch]
0x14000ea15  mov     word ptr [rbp+57h+var_70], r12w
0x14000ea1a  cmovnz  ebx, eax
0x14000ea1d  lea     rax, [rbp+57h+var_70+4]
0x14000ea21  cmovz   rcx, rax; void *
0x14000ea25  mov     r8d, ebx; Size
0x14000ea28  movups  [rbp+57h+var_50+0Ch], xmm0
0x14000ea2c  movups  [rbp+57h+var_70+0Ch], xmm1
0x14000ea30  call    memmove
0x14000ea35  lea     rax, [rbp+57h+var_50+4]
0x14000ea39  cmp     r12w, 2
0x14000ea3e  lea     rcx, [rbp+57h+var_50+8]
0x14000ea42  mov     r8d, ebx; Size
0x14000ea45  cmovz   rcx, rax; void *
0x14000ea49  lea     rdx, [rdi+34h]; Src
0x14000ea4d  call    memmove
0x14000ea52  cmp     r15d, 1
0x14000ea56  jnz     loc_14000EAFE
0x14000ea5c  lea     ecx, [r15+0Fh]
0x14000ea60  test    cs:Microsoft_Windows_WinNatEnableBits, cl
0x14000ea66  jz      loc_14000EAFE
0x14000ea6c  mov     rax, [rdi+70h]
0x14000ea70  lea     r11d, [r15+1Bh]
0x14000ea74  movzx   edx, byte ptr [rdi+44h]
0x14000ea78  xor     r10d, r10d
0x14000ea7b  movzx   r8d, byte ptr [rdi+30h]
0x14000ea80  cmp     r12w, 17h
0x14000ea85  mov     r9, [rdi+50h]
0x14000ea89  mov     [rsp+0F0h+var_78], esi
0x14000ea8d  setz    r10b
0x14000ea91  cmp     word ptr [rbp+57h+var_70], 2
0x14000ea96  mov     [rsp+0F0h+var_80], 3
0x14000ea9e  mov     [rsp+0F0h+var_88], rax
0x14000eaa3  cmovz   r11d, ecx
0x14000eaa7  mov     rax, [rdi+58h]
0x14000eaab  add     r9, 158h
0x14000eab2  movzx   ecx, byte ptr [rdi+4Ch]
0x14000eab6  mov     [rsp+0F0h+var_90], rax
0x14000eabb  mov     eax, [rdi+48h]
0x14000eabe  mov     [rsp+0F0h+var_98], r10d
0x14000eac3  mov     [rsp+0F0h+var_A0], ecx
0x14000eac7  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x14000eace  mov     [rsp+0F0h+var_A8], eax
0x14000ead2  lea     rax, [rbp+57h+var_50]
0x14000ead6  mov     [rsp+0F0h+var_B0], edx
0x14000eada  lea     rdx, WINNAT_WFP_FILTER_EVENT
0x14000eae1  mov     [rsp+0F0h+var_B8], rax
0x14000eae6  lea     rax, [rbp+57h+var_70]
0x14000eaea  mov     [rsp+0F0h+var_C0], r8d
0x14000eaef  mov     [rsp+0F0h+var_C8], rax
0x14000eaf4  mov     [rsp+0F0h+var_D0], r11d
0x14000eaf9  call    McTemplateK0zqbr1qbr1qqqtxxqq_EtwWriteTransfer
0x14000eafe  mov     rcx, rdi; P
0x14000eb01  call    WinNatDereferencePacketFilter
0x14000eb06  xor     edx, edx; Tag
0x14000eb08  mov     rcx, r14; P
0x14000eb0b  call    cs:__imp_ExFreePoolWithTag
0x14000eb12  nop     dword ptr [rax+rax+00h]
0x14000eb17  mov     eax, esi
0x14000eb19  mov     rcx, [rbp+57h+var_30]
0x14000eb1d  xor     rcx, rsp; StackCookie
0x14000eb20  call    __security_check_cookie
0x14000eb25  lea     r11, [rsp+0F0h+var_20]
0x14000eb2d  mov     rbx, [r11+38h]
0x14000eb31  mov     rsi, [r11+40h]
0x14000eb35  mov     rsp, r11
0x14000eb38  pop     r15
0x14000eb3a  pop     r14
0x14000eb3c  pop     r12
0x14000eb3e  pop     rdi
0x14000eb3f  pop     rbp
0x14000eb40  retn
```
