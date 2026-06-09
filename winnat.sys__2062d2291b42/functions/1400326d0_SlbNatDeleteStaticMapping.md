# SlbNatDeleteStaticMapping

- ea: `0x1400326d0`
- end: `0x1400328c4`
- name: `SlbNatDeleteStaticMapping`
- size: `500`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140032228`
- `0x1400328cc`
- `0x1400335e8`

## callees

- `0x14000d648`
- `0x1400149bc`
- `0x140015614`
- `0x14001bcbc`
- `0x14001f320`
- `0x14002f1d8`
- `0x1400326d0`
- `0x140033b60`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140032894`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032894`
- `NETIO!CloseCompartment` at `0x140032787`
- `NETIO!CloseCompartment` at `0x140032787`

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
    (_DWORD)qword_1400273D8,
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
    if ( dword_140027104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x10) != 0 )
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
0x1400326d0  mov     [rsp-8+arg_10], rbx
0x1400326d5  push    rbp
0x1400326d6  push    rsi
0x1400326d7  push    rdi
0x1400326d8  push    r12
0x1400326da  push    r14
0x1400326dc  lea     rbp, [rsp-37h]
0x1400326e1  sub     rsp, 0E0h
0x1400326e8  mov     rax, cs:__security_cookie
0x1400326ef  xor     rax, rsp
0x1400326f2  mov     [rbp+57h+var_30], rax
0x1400326f6  xor     eax, eax
0x1400326f8  lea     r8, [rcx+3Ch]
0x1400326fc  movzx   eax, word ptr [rcx+4Eh]
0x140032700  xorps   xmm0, xmm0
0x140032703  xorps   xmm1, xmm1
0x140032706  ror     ax, 8
0x14003270a  mov     r14, rdx
0x14003270d  mov     word ptr [rsp+100h+var_E0], ax
0x140032712  mov     rdi, rcx
0x140032715  lea     rdx, [rbp+57h+var_70]
0x140032719  movzx   ecx, word ptr [rcx+26h]
0x14003271d  xor     ebx, ebx
0x14003271f  movups  [rbp+57h+var_70], xmm0
0x140032723  mov     r9d, ebx
0x140032726  movups  xmmword ptr [rbp+57h+var_90], xmm1
0x14003272a  movups  [rbp+57h+var_70+0Ch], xmm0
0x14003272e  movups  xmmword ptr [rbp+57h+var_90+0Ch], xmm1
0x140032732  call    INETADDR_SETSOCKADDR
0x140032737  movzx   eax, word ptr [rdi+4Ch]
0x14003273b  lea     r8, [rdi+2Ch]
0x14003273f  movzx   ecx, word ptr [rdi+26h]
0x140032743  lea     rdx, [rbp+57h+var_90]
0x140032747  ror     ax, 8
0x14003274b  mov     r9d, ebx
0x14003274e  mov     word ptr [rsp+100h+var_E0], ax
0x140032753  call    INETADDR_SETSOCKADDR
0x140032758  mov     eax, [rdi+74h]
0x14003275b  lea     r8, [rbp+57h+var_70]
0x14003275f  mov     r9d, [rdi+10h]
0x140032763  lea     rdx, [rbp+57h+var_90]
0x140032767  mov     rcx, cs:qword_1400273D8
0x14003276e  mov     [rsp+100h+var_D8], eax
0x140032772  mov     al, [rdi+24h]
0x140032775  mov     byte ptr [rsp+100h+var_E0], al
0x140032779  call    WinNatLibDeleteStaticBindingEntry
0x14003277e  mov     rcx, [rdi+18h]
0x140032782  test    rcx, rcx
0x140032785  jz      short loc_140032793
0x140032787  call    cs:__imp_CloseCompartment
0x14003278e  nop     dword ptr [rax+rax+00h]
0x140032793  mov     r12d, 10h
0x140032799  test    cs:Microsoft_Windows_WinNatEnableBits, r12b
0x1400327a0  jz      loc_14003284A
0x1400327a6  movzx   ecx, word ptr [rdi+26h]
0x1400327aa  lea     r8, [rdi+64h]
0x1400327ae  xorps   xmm0, xmm0
0x1400327b1  lea     rdx, [rbp+57h+var_50]
0x1400327b5  xor     eax, eax
0x1400327b7  mov     r9d, ebx
0x1400327ba  movups  [rbp+57h+var_50], xmm0
0x1400327be  mov     word ptr [rsp+100h+var_E0], ax
0x1400327c3  movups  [rbp+57h+var_50+0Ch], xmm0
0x1400327c7  call    INETADDR_SETSOCKADDR
0x1400327cc  cmp     cs:dword_140027104, 1
0x1400327d3  jnz     short loc_14003284A
0x1400327d5  test    cs:Microsoft_Windows_WinNatEnableBits, r12b
0x1400327dc  jz      short loc_14003284A
0x1400327de  movzx   eax, byte ptr [rdi+60h]
0x1400327e2  lea     rcx, [rdi+50h]
0x1400327e6  movzx   edx, byte ptr [rdi+24h]
0x1400327ea  lea     r8d, [r12+0Ch]
0x1400327ef  cmp     [rbp+57h+var_90], 2
0x1400327f4  lea     r9, [r14+50h]
0x1400327f8  mov     [rsp+100h+var_A0], eax
0x1400327fc  lea     rax, [rbp+57h+var_50]
0x140032800  mov     [rsp+100h+var_A8], rax
0x140032805  cmovz   r8d, r12d
0x140032809  mov     eax, [rdi+10h]
0x14003280c  mov     [rsp+100h+var_B0], eax
0x140032810  lea     rax, [rbp+57h+var_70]
0x140032814  mov     [rsp+100h+var_B8], rcx
0x140032819  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x140032820  mov     [rsp+100h+var_C0], rax
0x140032825  lea     rax, [rbp+57h+var_90]
0x140032829  mov     [rsp+100h+var_C8], rax
0x14003282e  mov     eax, [rdi+28h]
0x140032831  mov     [rsp+100h+var_D0], r8d
0x140032836  mov     [rsp+100h+var_D8], eax
0x14003283a  mov     dword ptr [rsp+100h+var_E0], edx
0x14003283e  lea     rdx, WINNATM_STATIC_MAPPING_REMOVAL
0x140032845  call    McTemplateK0zqqqbr3br3jqbr3q_EtwWriteTransfer
0x14003284a  cmp     [rdi+78h], rbx
0x14003284e  jz      short loc_14003288F
0x140032850  cmp     [rdi+2Ch], ebx
0x140032853  jnz     short loc_14003288F
0x140032855  mov     r8d, [rdi+74h]
0x140032859  xor     r9d, r9d
0x14003285c  movzx   edx, word ptr [rdi+4Ch]
0x140032860  mov     cl, [rdi+24h]
0x140032863  mov     [rsp+100h+var_E0], rbx
0x140032868  call    SlbNatFindAssociatedStaticMapping
0x14003286d  mov     rcx, [rdi+78h]; P
0x140032871  test    rax, rax
0x140032874  jnz     short loc_14003288A
0x140032876  mov     r8, rcx
0x140032879  lea     rdx, SlbNatAsyncFreePort
0x140032880  mov     rcx, [rcx]
0x140032883  call    SlbNatQueueWorkItem
0x140032888  jmp     short loc_14003288F
0x14003288a  call    SlbNatFreeFreeContext
0x14003288f  xor     edx, edx; Tag
0x140032891  mov     rcx, rdi; P
0x140032894  call    cs:__imp_ExFreePoolWithTag
0x14003289b  nop     dword ptr [rax+rax+00h]
0x1400328a0  mov     rcx, [rbp+57h+var_30]
0x1400328a4  xor     rcx, rsp; StackCookie
0x1400328a7  call    __security_check_cookie
0x1400328ac  mov     rbx, [rsp+100h+arg_10]
0x1400328b4  add     rsp, 0E0h
0x1400328bb  pop     r14
0x1400328bd  pop     r12
0x1400328bf  pop     rdi
0x1400328c0  pop     rsi
0x1400328c1  pop     rbp
0x1400328c2  retn
```
