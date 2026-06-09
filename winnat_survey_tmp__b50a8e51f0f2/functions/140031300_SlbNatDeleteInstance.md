# SlbNatDeleteInstance

- ea: `0x140031300`
- end: `0x1400314cb`
- name: `SlbNatDeleteInstance`
- size: `459`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1400323e8`
- `0x140032d2c`

## callees

- `0x14000c440`
- `0x14000caa0`
- `0x140013c08`
- `0x140018f48`
- `0x14002e560`
- `0x14002f9fc`
- `0x1400310f8`
- `0x140031300`
- `0x1400314d4`
- `0x14003179c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400314a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400314a9`
- `NETIO!CloseCompartment` at `0x1400313bf`
- `NETIO!CloseCompartment` at `0x1400313bf`

## pseudocode

```c
void __fastcall SlbNatDeleteInstance(char *P, char a2)
{
  char **v4; // rdi
  char *v5; // rcx
  __int64 v6; // rax
  _QWORD **v7; // rdi
  _QWORD *v8; // rcx
  _QWORD *v9; // rax
  __int64 v10; // rcx
  volatile signed __int32 *v11; // rcx
  int v12; // r8d

  SlbNatChangeInstanceExternalInterface(P, 0);
  v4 = (char **)(P + 24);
  while ( 1 )
  {
    v5 = *v4;
    if ( *v4 == (char *)v4 )
      break;
    if ( *((char ***)v5 + 1) != v4 || (v6 = *(_QWORD *)v5, *(char **)(*(_QWORD *)v5 + 8LL) != v5) )
LABEL_11:
      __fastfail(3u);
    *v4 = (char *)v6;
    *(_QWORD *)(v6 + 8) = v4;
    SlbNatDeleteExternalAddress(v5, (__int64)P);
  }
  SlbNatDeleteWildcardStaticMappingsForInstance(P);
  v7 = (_QWORD **)(P + 48);
  while ( 1 )
  {
    v8 = *v7;
    if ( *v7 == v7 )
      break;
    if ( (_QWORD **)v8[1] != v7 )
      goto LABEL_11;
    v9 = (_QWORD *)*v8;
    if ( *(_QWORD **)(*v8 + 8LL) != v8 )
      goto LABEL_11;
    *v7 = v9;
    v9[1] = v7;
    --*((_DWORD *)P + 16);
    SlbNatDeleteInternalAddress(v8);
  }
  if ( !a2 && dword_1400264E8 > 1 )
    SlbNatClassifyInterfaces(2, 0, 0);
  WinNatLibDeleteAddressPool(qword_1400263D8);
  v10 = *((_QWORD *)P + 9);
  if ( v10 )
    CloseCompartment(v10);
  v11 = &dword_1400264EC;
  if ( !P[182] )
    v11 = &dword_1400264E8;
  if ( _InterlockedDecrement(v11) < 0 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v11, &dword_1400264E8);
  WinNatDereferenceGlobal();
  if ( dword_140026104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x10) != 0 )
    McTemplateK0zjqqqqqqqqqqt_EtwWriteTransfer(
      (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
      (unsigned int)WINNATM_INSTANCE_DELETION,
      v12,
      (_DWORD)P + 80,
      (__int64)(P + 164),
      P[182],
      *((_DWORD *)P + 46),
      *((_DWORD *)P + 17),
      *((_DWORD *)P + 68),
      *((_DWORD *)P + 50),
      *((_DWORD *)P + 53),
      *((_DWORD *)P + 54),
      *((_DWORD *)P + 56),
      *((_DWORD *)P + 55),
      *((_DWORD *)P + 52),
      P[204]);
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x140031300  mov     [rsp+arg_0], rbx
0x140031305  mov     [rsp+arg_8], rsi
0x14003130a  push    rdi
0x14003130b  sub     rsp, 80h
0x140031312  mov     sil, dl
0x140031315  mov     rbx, rcx
0x140031318  xor     edx, edx
0x14003131a  call    SlbNatChangeInstanceExternalInterface
0x14003131f  lea     rdi, [rbx+18h]
0x140031323  mov     rcx, [rdi]; P
0x140031326  cmp     rcx, rdi
0x140031329  jz      short loc_14003134B
0x14003132b  cmp     [rcx+8], rdi
0x14003132f  jnz     short loc_140031382
0x140031331  mov     rax, [rcx]
0x140031334  cmp     [rax+8], rcx
0x140031338  jnz     short loc_140031382
0x14003133a  mov     [rdi], rax
0x14003133d  mov     rdx, rbx
0x140031340  mov     [rax+8], rdi
0x140031344  call    SlbNatDeleteExternalAddress
0x140031349  jmp     short loc_140031323
0x14003134b  mov     rcx, rbx
0x14003134e  call    SlbNatDeleteWildcardStaticMappingsForInstance
0x140031353  lea     rdi, [rbx+30h]
0x140031357  mov     rcx, [rdi]; P
0x14003135a  cmp     rcx, rdi
0x14003135d  jz      short loc_140031389
0x14003135f  cmp     [rcx+8], rdi
0x140031363  jnz     short loc_140031382
0x140031365  mov     rax, [rcx]
0x140031368  cmp     [rax+8], rcx
0x14003136c  jnz     short loc_140031382
0x14003136e  mov     [rdi], rax
0x140031371  mov     rdx, rbx
0x140031374  mov     [rax+8], rdi
0x140031378  dec     dword ptr [rbx+40h]
0x14003137b  call    SlbNatDeleteInternalAddress
0x140031380  jmp     short loc_140031357
0x140031382  mov     ecx, 3
0x140031387  int     29h; Win8: RtlFailFast(ecx)
0x140031389  test    sil, sil
0x14003138c  jnz     short loc_1400313A6
0x14003138e  cmp     cs:dword_1400264E8, 1
0x140031395  jle     short loc_1400313A6
0x140031397  mov     ecx, 2
0x14003139c  xor     r8d, r8d
0x14003139f  xor     edx, edx
0x1400313a1  call    SlbNatClassifyInterfaces
0x1400313a6  mov     rdx, [rbx+10h]
0x1400313aa  mov     rcx, cs:qword_1400263D8
0x1400313b1  call    WinNatLibDeleteAddressPool
0x1400313b6  mov     rcx, [rbx+48h]
0x1400313ba  test    rcx, rcx
0x1400313bd  jz      short loc_1400313CB
0x1400313bf  call    cs:__imp_CloseCompartment
0x1400313c6  nop     dword ptr [rax+rax+00h]
0x1400313cb  cmp     byte ptr [rbx+0B6h], 0
0x1400313d2  lea     rdx, dword_1400264E8
0x1400313d9  lea     rcx, dword_1400264EC
0x1400313e0  cmovz   rcx, rdx
0x1400313e4  or      eax, 0FFFFFFFFh
0x1400313e7  lock xadd [rcx], eax
0x1400313eb  cmp     eax, 1
0x1400313ee  jns     short loc_1400313F5
0x1400313f0  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400313f5  call    WinNatDereferenceGlobal
0x1400313fa  cmp     cs:dword_140026104, 1
0x140031401  jnz     loc_1400314A4
0x140031407  test    cs:Microsoft_Windows_WinNatEnableBits, 10h
0x14003140e  jz      loc_1400314A4
0x140031414  movzx   eax, byte ptr [rbx+0CCh]
0x14003141b  lea     rdx, [rbx+0A4h]
0x140031422  movzx   ecx, byte ptr [rbx+0B6h]
0x140031429  lea     r9, [rbx+50h]
0x14003142d  mov     [rsp+88h+var_10], eax
0x140031431  mov     eax, [rbx+0D0h]
0x140031437  mov     [rsp+88h+var_18], eax
0x14003143b  mov     eax, [rbx+0DCh]
0x140031441  mov     [rsp+88h+var_20], eax
0x140031445  mov     eax, [rbx+0E0h]
0x14003144b  mov     [rsp+88h+var_28], eax
0x14003144f  mov     eax, [rbx+0D8h]
0x140031455  mov     [rsp+88h+var_30], eax
0x140031459  mov     eax, [rbx+0D4h]
0x14003145f  mov     [rsp+88h+var_38], eax
0x140031463  mov     eax, [rbx+0C8h]
0x140031469  mov     [rsp+88h+var_40], eax
0x14003146d  mov     eax, [rbx+110h]
0x140031473  mov     [rsp+88h+var_48], eax
0x140031477  mov     eax, [rbx+44h]
0x14003147a  mov     [rsp+88h+var_50], eax
0x14003147e  mov     eax, [rbx+0B8h]
0x140031484  mov     [rsp+88h+var_58], eax
0x140031488  mov     [rsp+88h+var_60], ecx
0x14003148c  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x140031493  mov     [rsp+88h+var_68], rdx
0x140031498  lea     rdx, WINNATM_INSTANCE_DELETION
0x14003149f  call    McTemplateK0zjqqqqqqqqqqt_EtwWriteTransfer
0x1400314a4  xor     edx, edx; Tag
0x1400314a6  mov     rcx, rbx; P
0x1400314a9  call    cs:__imp_ExFreePoolWithTag
0x1400314b0  nop     dword ptr [rax+rax+00h]
0x1400314b5  lea     r11, [rsp+88h+var_8]
0x1400314bd  mov     rbx, [r11+10h]
0x1400314c1  mov     rsi, [r11+18h]
0x1400314c5  mov     rsp, r11
0x1400314c8  pop     rdi
0x1400314c9  retn
```
