# WinNARemoveWFPFiltersAtPassive

- ea: `0x14000e9b0`
- end: `0x14000eb72`
- name: `WinNARemoveWFPFiltersAtPassive`
- size: `450`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400118d0`

## callees

- `0x14000caa0`
- `0x14000e538`
- `0x14000e9b0`
- `0x14000f9f4`
- `0x1400139fc`
- `0x14001f320`
- `0x14001f680`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000eb3b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000eb3b`

## pseudocode

```c
__int64 __fastcall WinNARemoveWFPFiltersAtPassive(_QWORD *P)
{
  __int64 v1; // rdi
  int v2; // esi
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  int v7; // r15d
  __int16 v8; // r12
  _BYTE *v9; // rcx
  unsigned int v10; // ebx
  _BYTE *v11; // rcx
  int v12; // r11d
  _BYTE v14[28]; // [rsp+80h] [rbp-19h] BYREF
  _BYTE v15[28]; // [rsp+A0h] [rbp+7h] BYREF

  v1 = P[2];
  v2 = 0;
  if ( (*(_BYTE *)(v1 + 77) & 2) != 0 )
  {
    v2 = WinNatRemovePacketFilterFromWFP(v1);
    if ( v2 < 0 && (*(_BYTE *)(v1 + 77) & 1) == 0 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v5, v4, v6);
  }
  *(_BYTE *)(v1 + 77) &= ~2u;
  v7 = dword_140027104;
  if ( dword_140027104 )
  {
    v8 = *(_WORD *)(v1 + 8);
    v9 = &v14[8];
    *(_OWORD *)v15 = 0;
    *(_WORD *)v15 = v8;
    v10 = 4;
    *(_OWORD *)v14 = 0;
    *(_WORD *)v14 = v8;
    if ( v8 == 2 )
      v9 = &v14[4];
    else
      v10 = 16;
    *(_OWORD *)&v15[12] = 0;
    *(_OWORD *)&v14[12] = 0;
    memmove(v9, (const void *)(v1 + 32), v10);
    v11 = &v15[8];
    if ( v8 == 2 )
      v11 = &v15[4];
    memmove(v11, (const void *)(v1 + 52), v10);
    if ( v7 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x10) != 0 )
    {
      v12 = 28;
      if ( *(_WORD *)v14 == 2 )
        v12 = 16;
      McTemplateK0zqbr1qbr1qqqtxxqq_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
        (unsigned int)WINNAT_WFP_FILTER_EVENT,
        *(unsigned __int8 *)(v1 + 48),
        *(_QWORD *)(v1 + 80) + 344,
        v12,
        (__int64)v14,
        *(_BYTE *)(v1 + 48),
        (__int64)v15,
        *(_BYTE *)(v1 + 68),
        *(_DWORD *)(v1 + 72),
        *(_BYTE *)(v1 + 76),
        v8 == 23,
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
0x14000e9b0  mov     [rsp-8+arg_8], rbx
0x14000e9b5  mov     [rsp-8+arg_10], rsi
0x14000e9ba  push    rbp
0x14000e9bb  push    rdi
0x14000e9bc  push    r12
0x14000e9be  push    r14
0x14000e9c0  push    r15
0x14000e9c2  lea     rbp, [rsp-37h]
0x14000e9c7  sub     rsp, 0D0h
0x14000e9ce  mov     rax, cs:__security_cookie
0x14000e9d5  xor     rax, rsp
0x14000e9d8  mov     [rbp+57h+var_30], rax
0x14000e9dc  mov     rdi, [rcx+10h]
0x14000e9e0  xor     esi, esi
0x14000e9e2  mov     r14, rcx
0x14000e9e5  test    byte ptr [rdi+4Dh], 2
0x14000e9e9  jz      short loc_14000EA04
0x14000e9eb  mov     rcx, rdi
0x14000e9ee  call    WinNatRemovePacketFilterFromWFP
0x14000e9f3  mov     esi, eax
0x14000e9f5  test    eax, eax
0x14000e9f7  jns     short loc_14000EA04
0x14000e9f9  test    byte ptr [rdi+4Dh], 1
0x14000e9fd  jnz     short loc_14000EA04
0x14000e9ff  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14000ea04  and     byte ptr [rdi+4Dh], 0FDh
0x14000ea08  mov     r15d, cs:dword_140027104
0x14000ea0f  test    r15d, r15d
0x14000ea12  jz      loc_14000EB2E
0x14000ea18  movzx   r12d, word ptr [rdi+8]
0x14000ea1d  lea     rcx, [rbp+57h+var_70+8]
0x14000ea21  xor     eax, eax
0x14000ea23  lea     rdx, [rdi+20h]; Src
0x14000ea27  xorps   xmm0, xmm0
0x14000ea2a  xorps   xmm1, xmm1
0x14000ea2d  movups  [rbp+57h+var_50], xmm0
0x14000ea31  cmp     r12w, 2
0x14000ea36  mov     word ptr [rbp+57h+var_50], r12w
0x14000ea3b  lea     ebx, [rax+4]
0x14000ea3e  movups  [rbp+57h+var_70], xmm1
0x14000ea42  lea     eax, [rbx+0Ch]
0x14000ea45  mov     word ptr [rbp+57h+var_70], r12w
0x14000ea4a  cmovnz  ebx, eax
0x14000ea4d  lea     rax, [rbp+57h+var_70+4]
0x14000ea51  cmovz   rcx, rax; void *
0x14000ea55  mov     r8d, ebx; Size
0x14000ea58  movups  [rbp+57h+var_50+0Ch], xmm0
0x14000ea5c  movups  [rbp+57h+var_70+0Ch], xmm1
0x14000ea60  call    memmove
0x14000ea65  lea     rax, [rbp+57h+var_50+4]
0x14000ea69  cmp     r12w, 2
0x14000ea6e  lea     rcx, [rbp+57h+var_50+8]
0x14000ea72  mov     r8d, ebx; Size
0x14000ea75  cmovz   rcx, rax; void *
0x14000ea79  lea     rdx, [rdi+34h]; Src
0x14000ea7d  call    memmove
0x14000ea82  cmp     r15d, 1
0x14000ea86  jnz     loc_14000EB2E
0x14000ea8c  lea     ecx, [r15+0Fh]
0x14000ea90  test    cs:Microsoft_Windows_WinNatEnableBits, cl
0x14000ea96  jz      loc_14000EB2E
0x14000ea9c  mov     rax, [rdi+70h]
0x14000eaa0  lea     r11d, [r15+1Bh]
0x14000eaa4  movzx   edx, byte ptr [rdi+44h]
0x14000eaa8  xor     r10d, r10d
0x14000eaab  movzx   r8d, byte ptr [rdi+30h]
0x14000eab0  cmp     r12w, 17h
0x14000eab5  mov     r9, [rdi+50h]
0x14000eab9  mov     [rsp+0F0h+var_78], esi
0x14000eabd  setz    r10b
0x14000eac1  cmp     word ptr [rbp+57h+var_70], 2
0x14000eac6  mov     [rsp+0F0h+var_80], 3
0x14000eace  mov     [rsp+0F0h+var_88], rax
0x14000ead3  cmovz   r11d, ecx
0x14000ead7  mov     rax, [rdi+58h]
0x14000eadb  add     r9, 158h
0x14000eae2  movzx   ecx, byte ptr [rdi+4Ch]
0x14000eae6  mov     [rsp+0F0h+var_90], rax
0x14000eaeb  mov     eax, [rdi+48h]
0x14000eaee  mov     [rsp+0F0h+var_98], r10d
0x14000eaf3  mov     [rsp+0F0h+var_A0], ecx
0x14000eaf7  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x14000eafe  mov     [rsp+0F0h+var_A8], eax
0x14000eb02  lea     rax, [rbp+57h+var_50]
0x14000eb06  mov     [rsp+0F0h+var_B0], edx
0x14000eb0a  lea     rdx, WINNAT_WFP_FILTER_EVENT
0x14000eb11  mov     [rsp+0F0h+var_B8], rax
0x14000eb16  lea     rax, [rbp+57h+var_70]
0x14000eb1a  mov     [rsp+0F0h+var_C0], r8d
0x14000eb1f  mov     [rsp+0F0h+var_C8], rax
0x14000eb24  mov     [rsp+0F0h+var_D0], r11d
0x14000eb29  call    McTemplateK0zqbr1qbr1qqqtxxqq_EtwWriteTransfer
0x14000eb2e  mov     rcx, rdi; P
0x14000eb31  call    WinNatDereferencePacketFilter
0x14000eb36  xor     edx, edx; Tag
0x14000eb38  mov     rcx, r14; P
0x14000eb3b  call    cs:__imp_ExFreePoolWithTag
0x14000eb42  nop     dword ptr [rax+rax+00h]
0x14000eb47  mov     eax, esi
0x14000eb49  mov     rcx, [rbp+57h+var_30]
0x14000eb4d  xor     rcx, rsp; StackCookie
0x14000eb50  call    __security_check_cookie
0x14000eb55  lea     r11, [rsp+0F0h+var_20]
0x14000eb5d  mov     rbx, [r11+38h]
0x14000eb61  mov     rsi, [r11+40h]
0x14000eb65  mov     rsp, r11
0x14000eb68  pop     r15
0x14000eb6a  pop     r14
0x14000eb6c  pop     r12
0x14000eb6e  pop     rdi
0x14000eb6f  pop     rbp
0x14000eb70  retn
```
