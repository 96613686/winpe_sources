# TdiRegisterPnPHandlers

- ea: `0x140002630`
- end: `0x140002834`
- name: `TdiRegisterPnPHandlers`
- size: `516`
- prototype: `NTSTATUS __stdcall(PTDI_CLIENT_INTERFACE_INFO ClientInterfaceInfo, ULONG InterfaceInfoSize, HANDLE *BindingHandle)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140005380`
- `0x1400053c0`

## callees

- `0x140002630`
- `0x140002f50`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140002673`
- `ntoskrnl!ExAllocatePool2` at `0x140002697`
- `ntoskrnl!ExAllocatePool2` at `0x1400026f0`
- `ntoskrnl!ExAllocatePool2` at `0x140002673`
- `ntoskrnl!ExAllocatePool2` at `0x140002697`
- `ntoskrnl!ExAllocatePool2` at `0x1400026f0`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140002753`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140002753`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400026b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000270a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000271b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400027e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400027f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002808`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400026b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000270a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000271b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400027e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400027f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002808`

## pseudocode

```c
NTSTATUS __stdcall TdiRegisterPnPHandlers(
        PTDI_CLIENT_INTERFACE_INFO ClientInterfaceInfo,
        ULONG InterfaceInfoSize,
        HANDLE *BindingHandle)
{
  __int64 Pool2; // rbx
  __int64 v7; // rax
  PUNICODE_STRING ClientName; // rax
  void *v9; // rbp
  USHORT TdiVersion; // cx
  TDI_PNP_POWER_HANDLER PnPPowerHandler; // rax
  NTSTATUS v12; // edi

  if ( ClientInterfaceInfo->MajorTdiVersion > 2u )
    return -1073676284;
  if ( InterfaceInfoSize < 0x38 )
    return -1073676283;
  Pool2 = ExAllocatePool2(64, 120, 1716077652);
  if ( !Pool2 )
    return -1073741670;
  v7 = ExAllocatePool2(64, 136, 1632191572);
  *(_QWORD *)(Pool2 + 112) = v7;
  if ( !v7 )
  {
    ExFreePoolWithTag((PVOID)Pool2, 0);
    return -1073741670;
  }
  ClientName = ClientInterfaceInfo->ClientName;
  if ( ClientName )
  {
    v9 = (void *)ExAllocatePool2(64, ClientName->MaximumLength, 1732854868);
    if ( !v9 )
    {
      ExFreePoolWithTag(*(PVOID *)(Pool2 + 112), 0);
      ExFreePoolWithTag((PVOID)Pool2, 0);
      return -1073741670;
    }
    *(_WORD *)(Pool2 + 32) = ClientInterfaceInfo->ClientName->Length;
    *(_WORD *)(Pool2 + 34) = ClientInterfaceInfo->ClientName->MaximumLength;
    *(_QWORD *)(Pool2 + 40) = v9;
    RtlCopyUnicodeString((PUNICODE_STRING)(Pool2 + 32), ClientInterfaceInfo->ClientName);
  }
  else
  {
    v9 = 0;
    *(_DWORD *)(Pool2 + 32) = 0;
    *(_QWORD *)(Pool2 + 40) = 0;
  }
  *(_WORD *)(Pool2 + 24) = ClientInterfaceInfo->TdiVersion;
  *(_BYTE *)(Pool2 + 16) = 2;
  TdiVersion = ClientInterfaceInfo->TdiVersion;
  *(_QWORD *)(Pool2 + 48) = ClientInterfaceInfo->BindingHandler;
  if ( TdiVersion == 1 )
  {
    *(_QWORD *)(Pool2 + 56) = ClientInterfaceInfo->UnBindHandler;
    *(_QWORD *)(Pool2 + 64) = ClientInterfaceInfo->AddAddressHandlerV2;
    *(_QWORD *)(Pool2 + 72) = ClientInterfaceInfo->DelAddressHandlerV2;
    PnPPowerHandler = 0;
  }
  else
  {
    *(_QWORD *)(Pool2 + 64) = ClientInterfaceInfo->AddAddressHandlerV2;
    *(_QWORD *)(Pool2 + 72) = ClientInterfaceInfo->DelAddressHandlerV2;
    PnPPowerHandler = ClientInterfaceInfo->PnPPowerHandler;
  }
  *(_QWORD *)(Pool2 + 80) = PnPPowerHandler;
  *(_QWORD *)(Pool2 + 104) = 0;
  *BindingHandle = (HANDLE)Pool2;
  v12 = TdiHandleSerializedRequest(Pool2, 8);
  if ( v12 )
  {
    if ( v9 )
      ExFreePoolWithTag(v9, 0);
    ExFreePoolWithTag(*(PVOID *)(Pool2 + 112), 0);
    ExFreePoolWithTag((PVOID)Pool2, 0);
    *BindingHandle = 0;
  }
  return v12;
}

```

## disassembly

```asm
0x140002630  mov     [rsp+arg_18], rsi
0x140002635  push    rdi
0x140002636  sub     rsp, 20h
0x14000263a  cmp     byte ptr [rcx], 2
0x14000263d  mov     rsi, r8
0x140002640  mov     rdi, rcx
0x140002643  jbe     short loc_14000264F
0x140002645  mov     eax, 0C0010004h
0x14000264a  jmp     loc_140002828
0x14000264f  cmp     edx, 38h ; '8'
0x140002652  jnb     short loc_14000265E
0x140002654  mov     eax, 0C0010005h
0x140002659  jmp     loc_140002828
0x14000265e  mov     edx, 78h ; 'x'
0x140002663  mov     [rsp+28h+arg_0], rbx
0x140002668  mov     ecx, 40h ; '@'
0x14000266d  mov     r8d, 66494454h
0x140002673  call    cs:__imp_ExAllocatePool2
0x14000267a  nop     dword ptr [rax+rax+00h]
0x14000267f  mov     rbx, rax
0x140002682  test    rax, rax
0x140002685  jz      short loc_1400026BD
0x140002687  mov     edx, 88h
0x14000268c  mov     ecx, 40h ; '@'
0x140002691  mov     r8d, 61494454h
0x140002697  call    cs:__imp_ExAllocatePool2
0x14000269e  nop     dword ptr [rax+rax+00h]
0x1400026a3  mov     [rbx+70h], rax
0x1400026a7  test    rax, rax
0x1400026aa  jnz     short loc_1400026C7
0x1400026ac  xor     edx, edx; Tag
0x1400026ae  mov     rcx, rbx; P
0x1400026b1  call    cs:__imp_ExFreePoolWithTag
0x1400026b8  nop     dword ptr [rax+rax+00h]
0x1400026bd  mov     eax, 0C000009Ah
0x1400026c2  jmp     loc_140002823
0x1400026c7  mov     rax, [rdi+8]
0x1400026cb  mov     [rsp+28h+arg_8], rbp
0x1400026d0  mov     [rsp+28h+arg_10], r14
0x1400026d5  xor     r14d, r14d
0x1400026d8  test    rax, rax
0x1400026db  jz      loc_140002761
0x1400026e1  movzx   edx, word ptr [rax+2]
0x1400026e5  mov     ecx, 40h ; '@'
0x1400026ea  mov     r8d, 67494454h
0x1400026f0  call    cs:__imp_ExAllocatePool2
0x1400026f7  nop     dword ptr [rax+rax+00h]
0x1400026fc  mov     rbp, rax
0x1400026ff  test    rax, rax
0x140002702  jnz     short loc_140002731
0x140002704  mov     rcx, [rbx+70h]; P
0x140002708  xor     edx, edx; Tag
0x14000270a  call    cs:__imp_ExFreePoolWithTag
0x140002711  nop     dword ptr [rax+rax+00h]
0x140002716  xor     edx, edx; Tag
0x140002718  mov     rcx, rbx; P
0x14000271b  call    cs:__imp_ExFreePoolWithTag
0x140002722  nop     dword ptr [rax+rax+00h]
0x140002727  mov     eax, 0C000009Ah
0x14000272c  jmp     loc_140002819
0x140002731  mov     rax, [rdi+8]
0x140002735  lea     rcx, [rbx+20h]; DestinationString
0x140002739  movzx   edx, word ptr [rax]
0x14000273c  mov     [rcx], dx
0x14000273f  mov     rax, [rdi+8]
0x140002743  movzx   edx, word ptr [rax+2]
0x140002747  mov     [rbx+22h], dx
0x14000274b  mov     [rbx+28h], rbp
0x14000274f  mov     rdx, [rdi+8]; SourceString
0x140002753  call    cs:__imp_RtlCopyUnicodeString
0x14000275a  nop     dword ptr [rax+rax+00h]
0x14000275f  jmp     short loc_14000276C
0x140002761  mov     rbp, r14
0x140002764  mov     [rbx+20h], r14d
0x140002768  mov     [rbx+28h], r14
0x14000276c  movzx   eax, word ptr [rdi]
0x14000276f  mov     [rbx+18h], ax
0x140002773  mov     byte ptr [rbx+10h], 2
0x140002777  mov     rax, [rdi+18h]
0x14000277b  movzx   ecx, word ptr [rdi]
0x14000277e  mov     [rbx+30h], rax
0x140002782  mov     eax, 1
0x140002787  cmp     ax, cx
0x14000278a  jnz     short loc_1400027A9
0x14000278c  mov     rax, [rdi+20h]
0x140002790  mov     [rbx+38h], rax
0x140002794  mov     rax, [rdi+28h]
0x140002798  mov     [rbx+40h], rax
0x14000279c  mov     rax, [rdi+30h]
0x1400027a0  mov     [rbx+48h], rax
0x1400027a4  mov     rax, r14
0x1400027a7  jmp     short loc_1400027BD
0x1400027a9  mov     rax, [rdi+28h]
0x1400027ad  mov     [rbx+40h], rax
0x1400027b1  mov     rax, [rdi+30h]
0x1400027b5  mov     [rbx+48h], rax
0x1400027b9  mov     rax, [rdi+10h]
0x1400027bd  mov     [rbx+50h], rax
0x1400027c1  mov     edx, 8
0x1400027c6  mov     [rbx+68h], r14
0x1400027ca  mov     rcx, rbx
0x1400027cd  mov     [rsi], rbx
0x1400027d0  call    TdiHandleSerializedRequest
0x1400027d5  mov     edi, eax
0x1400027d7  test    eax, eax
0x1400027d9  jz      short loc_140002817
0x1400027db  test    rbp, rbp
0x1400027de  jz      short loc_1400027F1
0x1400027e0  xor     edx, edx; Tag
0x1400027e2  mov     rcx, rbp; P
0x1400027e5  call    cs:__imp_ExFreePoolWithTag
0x1400027ec  nop     dword ptr [rax+rax+00h]
0x1400027f1  mov     rcx, [rbx+70h]; P
0x1400027f5  xor     edx, edx; Tag
0x1400027f7  call    cs:__imp_ExFreePoolWithTag
0x1400027fe  nop     dword ptr [rax+rax+00h]
0x140002803  xor     edx, edx; Tag
0x140002805  mov     rcx, rbx; P
0x140002808  call    cs:__imp_ExFreePoolWithTag
0x14000280f  nop     dword ptr [rax+rax+00h]
0x140002814  mov     [rsi], r14
0x140002817  mov     eax, edi
0x140002819  mov     rbp, [rsp+28h+arg_8]
0x14000281e  mov     r14, [rsp+28h+arg_10]
0x140002823  mov     rbx, [rsp+28h+arg_0]
0x140002828  mov     rsi, [rsp+28h+arg_18]
0x14000282d  add     rsp, 20h
0x140002831  pop     rdi
0x140002832  retn
```
