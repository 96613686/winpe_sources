# SlbNatDeleteInstance

- ea: `0x140032430`
- end: `0x1400325fb`
- name: `SlbNatDeleteInstance`
- size: `459`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140033518`
- `0x140033e5c`

## callees

- `0x14000c440`
- `0x14000caa0`
- `0x140014548`
- `0x140019428`
- `0x14002f560`
- `0x140030b2c`
- `0x140032228`
- `0x140032430`
- `0x140032604`
- `0x1400328cc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400325d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400325d9`
- `NETIO!CloseCompartment` at `0x1400324ef`
- `NETIO!CloseCompartment` at `0x1400324ef`

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
  __int64 v10; // r8
  __int64 v11; // rcx
  volatile signed __int32 *v12; // rcx
  int v13; // r8d

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
  if ( !a2 && dword_1400274E8 > 1 )
    SlbNatClassifyInterfaces(2, 0, 0);
  WinNatLibDeleteAddressPool(qword_1400273D8);
  v11 = *((_QWORD *)P + 9);
  if ( v11 )
    CloseCompartment(v11);
  v12 = &dword_1400274EC;
  if ( !P[182] )
    v12 = &dword_1400274E8;
  if ( _InterlockedDecrement(v12) < 0 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v12, &dword_1400274E8, v10);
  WinNatDereferenceGlobal();
  if ( dword_140027104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x10) != 0 )
    McTemplateK0zjqqqqqqqqqqt_EtwWriteTransfer(
      (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
      (unsigned int)WINNATM_INSTANCE_DELETION,
      v13,
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
0x140032430  mov     [rsp+arg_0], rbx
0x140032435  mov     [rsp+arg_8], rsi
0x14003243a  push    rdi
0x14003243b  sub     rsp, 80h
0x140032442  mov     sil, dl
0x140032445  mov     rbx, rcx
0x140032448  xor     edx, edx
0x14003244a  call    SlbNatChangeInstanceExternalInterface
0x14003244f  lea     rdi, [rbx+18h]
0x140032453  mov     rcx, [rdi]; P
0x140032456  cmp     rcx, rdi
0x140032459  jz      short loc_14003247B
0x14003245b  cmp     [rcx+8], rdi
0x14003245f  jnz     short loc_1400324B2
0x140032461  mov     rax, [rcx]
0x140032464  cmp     [rax+8], rcx
0x140032468  jnz     short loc_1400324B2
0x14003246a  mov     [rdi], rax
0x14003246d  mov     rdx, rbx
0x140032470  mov     [rax+8], rdi
0x140032474  call    SlbNatDeleteExternalAddress
0x140032479  jmp     short loc_140032453
0x14003247b  mov     rcx, rbx
0x14003247e  call    SlbNatDeleteWildcardStaticMappingsForInstance
0x140032483  lea     rdi, [rbx+30h]
0x140032487  mov     rcx, [rdi]; P
0x14003248a  cmp     rcx, rdi
0x14003248d  jz      short loc_1400324B9
0x14003248f  cmp     [rcx+8], rdi
0x140032493  jnz     short loc_1400324B2
0x140032495  mov     rax, [rcx]
0x140032498  cmp     [rax+8], rcx
0x14003249c  jnz     short loc_1400324B2
0x14003249e  mov     [rdi], rax
0x1400324a1  mov     rdx, rbx
0x1400324a4  mov     [rax+8], rdi
0x1400324a8  dec     dword ptr [rbx+40h]
0x1400324ab  call    SlbNatDeleteInternalAddress
0x1400324b0  jmp     short loc_140032487
0x1400324b2  mov     ecx, 3
0x1400324b7  int     29h; Win8: RtlFailFast(ecx)
0x1400324b9  test    sil, sil
0x1400324bc  jnz     short loc_1400324D6
0x1400324be  cmp     cs:dword_1400274E8, 1
0x1400324c5  jle     short loc_1400324D6
0x1400324c7  mov     ecx, 2
0x1400324cc  xor     r8d, r8d
0x1400324cf  xor     edx, edx
0x1400324d1  call    SlbNatClassifyInterfaces
0x1400324d6  mov     rdx, [rbx+10h]
0x1400324da  mov     rcx, cs:qword_1400273D8
0x1400324e1  call    WinNatLibDeleteAddressPool
0x1400324e6  mov     rcx, [rbx+48h]
0x1400324ea  test    rcx, rcx
0x1400324ed  jz      short loc_1400324FB
0x1400324ef  call    cs:__imp_CloseCompartment
0x1400324f6  nop     dword ptr [rax+rax+00h]
0x1400324fb  cmp     byte ptr [rbx+0B6h], 0
0x140032502  lea     rdx, dword_1400274E8
0x140032509  lea     rcx, dword_1400274EC
0x140032510  cmovz   rcx, rdx
0x140032514  or      eax, 0FFFFFFFFh
0x140032517  lock xadd [rcx], eax
0x14003251b  cmp     eax, 1
0x14003251e  jns     short loc_140032525
0x140032520  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140032525  call    WinNatDereferenceGlobal
0x14003252a  cmp     cs:dword_140027104, 1
0x140032531  jnz     loc_1400325D4
0x140032537  test    cs:Microsoft_Windows_WinNatEnableBits, 10h
0x14003253e  jz      loc_1400325D4
0x140032544  movzx   eax, byte ptr [rbx+0CCh]
0x14003254b  lea     rdx, [rbx+0A4h]
0x140032552  movzx   ecx, byte ptr [rbx+0B6h]
0x140032559  lea     r9, [rbx+50h]
0x14003255d  mov     [rsp+88h+var_10], eax
0x140032561  mov     eax, [rbx+0D0h]
0x140032567  mov     [rsp+88h+var_18], eax
0x14003256b  mov     eax, [rbx+0DCh]
0x140032571  mov     [rsp+88h+var_20], eax
0x140032575  mov     eax, [rbx+0E0h]
0x14003257b  mov     [rsp+88h+var_28], eax
0x14003257f  mov     eax, [rbx+0D8h]
0x140032585  mov     [rsp+88h+var_30], eax
0x140032589  mov     eax, [rbx+0D4h]
0x14003258f  mov     [rsp+88h+var_38], eax
0x140032593  mov     eax, [rbx+0C8h]
0x140032599  mov     [rsp+88h+var_40], eax
0x14003259d  mov     eax, [rbx+110h]
0x1400325a3  mov     [rsp+88h+var_48], eax
0x1400325a7  mov     eax, [rbx+44h]
0x1400325aa  mov     [rsp+88h+var_50], eax
0x1400325ae  mov     eax, [rbx+0B8h]
0x1400325b4  mov     [rsp+88h+var_58], eax
0x1400325b8  mov     [rsp+88h+var_60], ecx
0x1400325bc  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x1400325c3  mov     [rsp+88h+var_68], rdx
0x1400325c8  lea     rdx, WINNATM_INSTANCE_DELETION
0x1400325cf  call    McTemplateK0zjqqqqqqqqqqt_EtwWriteTransfer
0x1400325d4  xor     edx, edx; Tag
0x1400325d6  mov     rcx, rbx; P
0x1400325d9  call    cs:__imp_ExFreePoolWithTag
0x1400325e0  nop     dword ptr [rax+rax+00h]
0x1400325e5  lea     r11, [rsp+88h+var_8]
0x1400325ed  mov     rbx, [r11+10h]
0x1400325f1  mov     rsi, [r11+18h]
0x1400325f5  mov     rsp, r11
0x1400325f8  pop     rdi
0x1400325f9  retn
```
