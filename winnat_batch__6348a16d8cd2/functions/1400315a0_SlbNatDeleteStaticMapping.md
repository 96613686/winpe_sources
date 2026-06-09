# SlbNatDeleteStaticMapping

- ea: `0x1400315a0`
- end: `0x140031794`
- name: `SlbNatDeleteStaticMapping`
- size: `500`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400310f8`
- `0x14003179c`
- `0x1400324b8`

## callees

- `0x14000d678`
- `0x14001407c`
- `0x140014cd4`
- `0x14001b7dc`
- `0x14001ede0`
- `0x14002e1d8`
- `0x1400315a0`
- `0x140032a30`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140031764`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031764`
- `NETIO!CloseCompartment` at `0x140031657`
- `NETIO!CloseCompartment` at `0x140031657`

## pseudocode

```c
void __fastcall SlbNatDeleteStaticMapping(unsigned __int16 *P, int a2)
{
  int v2; // r8d
  int v5; // ecx
  __int64 v6; // rcx
  int v7; // ecx
  int v8; // r8d
  __int64 AssociatedStaticMapping; // rax
  _QWORD *v10; // rcx
  __int16 v11; // [rsp+20h] [rbp-89h]
  _WORD v12[16]; // [rsp+70h] [rbp-39h] BYREF
  _OWORD v13[2]; // [rsp+90h] [rbp-19h] BYREF
  _OWORD v14[2]; // [rsp+B0h] [rbp+7h] BYREF

  v2 = (_DWORD)P + 60;
  v11 = __ROR2__(P[39], 8);
  v5 = P[19];
  memset(v13, 0, 28);
  memset(v12, 0, 28);
  INETADDR_SETSOCKADDR(v5, (unsigned int)v13, v2, 0, v11);
  INETADDR_SETSOCKADDR(P[19], (unsigned int)v12, (_DWORD)P + 44, 0, __ROR2__(P[38], 8));
  WinNatLibDeleteStaticBindingEntry(
    (_DWORD)qword_1400263D8,
    (unsigned int)v12,
    (unsigned int)v13,
    *((_DWORD *)P + 4),
    *((_BYTE *)P + 36),
    *((_DWORD *)P + 29));
  v6 = *((_QWORD *)P + 3);
  if ( v6 )
    CloseCompartment(v6);
  if ( (Microsoft_Windows_WinNatEnableBits & 0x10) != 0 )
  {
    v7 = P[19];
    memset(v14, 0, 28);
    INETADDR_SETSOCKADDR(v7, (unsigned int)v14, (_DWORD)P + 100, 0, 0);
    if ( dword_140026104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x10) != 0 )
    {
      v8 = 28;
      if ( v12[0] == 2 )
        v8 = 16;
      McTemplateK0zqqqbr3br3jqbr3q_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
        (unsigned int)WINNATM_STATIC_MAPPING_REMOVAL,
        v8,
        a2 + 80,
        *((_BYTE *)P + 36),
        *((_DWORD *)P + 10),
        v8,
        (__int64)v12,
        (__int64)v13,
        (__int64)(P + 40),
        *((_DWORD *)P + 4),
        (__int64)v14,
        *((_BYTE *)P + 96));
    }
  }
  if ( *((_QWORD *)P + 15) && !*((_DWORD *)P + 11) )
  {
    LOBYTE(v6) = *((_BYTE *)P + 36);
    AssociatedStaticMapping = SlbNatFindAssociatedStaticMapping(v6, P[38], *((_DWORD *)P + 29), 0, 0);
    v10 = (_QWORD *)*((_QWORD *)P + 15);
    if ( AssociatedStaticMapping )
      SlbNatFreeFreeContext(v10);
    else
      SlbNatQueueWorkItem(*v10, &SlbNatAsyncFreePort, *((_QWORD *)P + 15));
  }
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x1400315a0  mov     [rsp-8+arg_10], rbx
0x1400315a5  push    rbp
0x1400315a6  push    rsi
0x1400315a7  push    rdi
0x1400315a8  push    r12
0x1400315aa  push    r14
0x1400315ac  lea     rbp, [rsp-37h]
0x1400315b1  sub     rsp, 0E0h
0x1400315b8  mov     rax, cs:__security_cookie
0x1400315bf  xor     rax, rsp
0x1400315c2  mov     [rbp+57h+var_30], rax
0x1400315c6  xor     eax, eax
0x1400315c8  lea     r8, [rcx+3Ch]
0x1400315cc  movzx   eax, word ptr [rcx+4Eh]
0x1400315d0  xorps   xmm0, xmm0
0x1400315d3  xorps   xmm1, xmm1
0x1400315d6  ror     ax, 8
0x1400315da  mov     r14, rdx
0x1400315dd  mov     word ptr [rsp+100h+var_E0], ax
0x1400315e2  mov     rdi, rcx
0x1400315e5  lea     rdx, [rbp+57h+var_70]
0x1400315e9  movzx   ecx, word ptr [rcx+26h]
0x1400315ed  xor     ebx, ebx
0x1400315ef  movups  [rbp+57h+var_70], xmm0
0x1400315f3  mov     r9d, ebx
0x1400315f6  movups  xmmword ptr [rbp+57h+var_90], xmm1
0x1400315fa  movups  [rbp+57h+var_70+0Ch], xmm0
0x1400315fe  movups  xmmword ptr [rbp+57h+var_90+0Ch], xmm1
0x140031602  call    INETADDR_SETSOCKADDR
0x140031607  movzx   eax, word ptr [rdi+4Ch]
0x14003160b  lea     r8, [rdi+2Ch]
0x14003160f  movzx   ecx, word ptr [rdi+26h]
0x140031613  lea     rdx, [rbp+57h+var_90]
0x140031617  ror     ax, 8
0x14003161b  mov     r9d, ebx
0x14003161e  mov     word ptr [rsp+100h+var_E0], ax
0x140031623  call    INETADDR_SETSOCKADDR
0x140031628  mov     eax, [rdi+74h]
0x14003162b  lea     r8, [rbp+57h+var_70]
0x14003162f  mov     r9d, [rdi+10h]
0x140031633  lea     rdx, [rbp+57h+var_90]
0x140031637  mov     rcx, cs:qword_1400263D8
0x14003163e  mov     [rsp+100h+var_D8], eax
0x140031642  mov     al, [rdi+24h]
0x140031645  mov     byte ptr [rsp+100h+var_E0], al
0x140031649  call    WinNatLibDeleteStaticBindingEntry
0x14003164e  mov     rcx, [rdi+18h]
0x140031652  test    rcx, rcx
0x140031655  jz      short loc_140031663
0x140031657  call    cs:__imp_CloseCompartment
0x14003165e  nop     dword ptr [rax+rax+00h]
0x140031663  mov     r12d, 10h
0x140031669  test    cs:Microsoft_Windows_WinNatEnableBits, r12b
0x140031670  jz      loc_14003171A
0x140031676  movzx   ecx, word ptr [rdi+26h]
0x14003167a  lea     r8, [rdi+64h]
0x14003167e  xorps   xmm0, xmm0
0x140031681  lea     rdx, [rbp+57h+var_50]
0x140031685  xor     eax, eax
0x140031687  mov     r9d, ebx
0x14003168a  movups  [rbp+57h+var_50], xmm0
0x14003168e  mov     word ptr [rsp+100h+var_E0], ax
0x140031693  movups  [rbp+57h+var_50+0Ch], xmm0
0x140031697  call    INETADDR_SETSOCKADDR
0x14003169c  cmp     cs:dword_140026104, 1
0x1400316a3  jnz     short loc_14003171A
0x1400316a5  test    cs:Microsoft_Windows_WinNatEnableBits, r12b
0x1400316ac  jz      short loc_14003171A
0x1400316ae  movzx   eax, byte ptr [rdi+60h]
0x1400316b2  lea     rcx, [rdi+50h]
0x1400316b6  movzx   edx, byte ptr [rdi+24h]
0x1400316ba  lea     r8d, [r12+0Ch]
0x1400316bf  cmp     [rbp+57h+var_90], 2
0x1400316c4  lea     r9, [r14+50h]
0x1400316c8  mov     [rsp+100h+var_A0], eax
0x1400316cc  lea     rax, [rbp+57h+var_50]
0x1400316d0  mov     [rsp+100h+var_A8], rax
0x1400316d5  cmovz   r8d, r12d
0x1400316d9  mov     eax, [rdi+10h]
0x1400316dc  mov     [rsp+100h+var_B0], eax
0x1400316e0  lea     rax, [rbp+57h+var_70]
0x1400316e4  mov     [rsp+100h+var_B8], rcx
0x1400316e9  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x1400316f0  mov     [rsp+100h+var_C0], rax
0x1400316f5  lea     rax, [rbp+57h+var_90]
0x1400316f9  mov     [rsp+100h+var_C8], rax
0x1400316fe  mov     eax, [rdi+28h]
0x140031701  mov     [rsp+100h+var_D0], r8d
0x140031706  mov     [rsp+100h+var_D8], eax
0x14003170a  mov     dword ptr [rsp+100h+var_E0], edx
0x14003170e  lea     rdx, WINNATM_STATIC_MAPPING_REMOVAL
0x140031715  call    McTemplateK0zqqqbr3br3jqbr3q_EtwWriteTransfer
0x14003171a  cmp     [rdi+78h], rbx
0x14003171e  jz      short loc_14003175F
0x140031720  cmp     [rdi+2Ch], ebx
0x140031723  jnz     short loc_14003175F
0x140031725  mov     r8d, [rdi+74h]
0x140031729  xor     r9d, r9d
0x14003172c  movzx   edx, word ptr [rdi+4Ch]
0x140031730  mov     cl, [rdi+24h]
0x140031733  mov     [rsp+100h+var_E0], rbx
0x140031738  call    SlbNatFindAssociatedStaticMapping
0x14003173d  mov     rcx, [rdi+78h]; P
0x140031741  test    rax, rax
0x140031744  jnz     short loc_14003175A
0x140031746  mov     r8, rcx
0x140031749  lea     rdx, SlbNatAsyncFreePort
0x140031750  mov     rcx, [rcx]
0x140031753  call    SlbNatQueueWorkItem
0x140031758  jmp     short loc_14003175F
0x14003175a  call    SlbNatFreeFreeContext
0x14003175f  xor     edx, edx; Tag
0x140031761  mov     rcx, rdi; P
0x140031764  call    cs:__imp_ExFreePoolWithTag
0x14003176b  nop     dword ptr [rax+rax+00h]
0x140031770  mov     rcx, [rbp+57h+var_30]
0x140031774  xor     rcx, rsp; StackCookie
0x140031777  call    __security_check_cookie
0x14003177c  mov     rbx, [rsp+100h+arg_10]
0x140031784  add     rsp, 0E0h
0x14003178b  pop     r14
0x14003178d  pop     r12
0x14003178f  pop     rdi
0x140031790  pop     rsi
0x140031791  pop     rbp
0x140031792  retn
```
