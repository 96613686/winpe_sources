# GetMitigationConfiguration

- ea: `0x140006568`
- end: `0x140006784`
- name: `GetMitigationConfiguration`
- size: `540`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140005ea0`
- `0x1400068a4`

## callees

- `0x140001bf0`
- `0x140002270`
- `0x140006568`

## string_xrefs

- `0x14000664e`: `ExtensionPointDisablePolicy`
- `0x1400066d0`: `SideChannelIsolationPolicy`

## pseudocode

```c
void __fastcall GetMitigationConfiguration(__int64 a1, _DWORD *a2)
{
  int v4; // esi
  int v5; // eax
  int v6; // r14d
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // [rsp+40h] [rbp+20h] BYREF

  if ( !a1 )
    return;
  v14 = 0;
  v4 = 0;
  if ( (unsigned int)ScIsProcessMitigationPolicyActive(0) )
    v4 = a2[23];
  if ( !(unsigned int)RegQueryDword(a1, L"AslrPolicy", &v14) )
  {
    v5 = v14;
    a2[24] |= 1u;
    a2[25] = v5;
  }
  v6 = 2;
  if ( (unsigned int)RegQueryDword(a1, L"BinarySignaturePolicy", &v14) )
  {
    if ( !v4 )
      goto LABEL_11;
    a2[26] = 1;
  }
  else
  {
    a2[26] = v14;
  }
  a2[24] |= 2u;
LABEL_11:
  if ( !(unsigned int)RegQueryDword(a1, L"ChildProcessPolicy", &v14) )
  {
    v7 = v14;
    a2[24] |= 4u;
    a2[27] = v7;
  }
  if ( (unsigned int)RegQueryDword(a1, L"DynamicCodePolicy", &v14) )
  {
    if ( !v4 )
      goto LABEL_18;
    a2[28] = 1;
  }
  else
  {
    a2[28] = v14;
  }
  a2[24] |= 8u;
LABEL_18:
  if ( !(unsigned int)RegQueryDword(a1, L"ExtensionPointDisablePolicy", &v14) )
  {
    a2[29] = v14;
LABEL_22:
    a2[24] |= 0x10u;
    goto LABEL_23;
  }
  if ( v4 )
  {
    a2[29] = 1;
    goto LABEL_22;
  }
LABEL_23:
  if ( !(unsigned int)RegQueryDword(a1, L"FontDisablePolicy", &v14) )
  {
    v8 = v14;
    a2[24] |= 0x20u;
    a2[30] = v8;
  }
  if ( !(unsigned int)RegQueryDword(a1, L"ImageLoadPolicy", &v14) )
  {
    v9 = v14;
    a2[24] |= 0x40u;
    a2[31] = v9;
  }
  if ( !(unsigned int)RegQueryDword(a1, L"RedirectionTrustPolicy", &v14) )
    v6 = v14;
  a2[32] = v6;
  a2[24] |= 0x80u;
  if ( !(unsigned int)RegQueryDword(a1, L"SideChannelIsolationPolicy", &v14) )
  {
    v10 = v14;
    a2[24] |= 0x100u;
    a2[33] = v10;
  }
  if ( !(unsigned int)RegQueryDword(a1, L"StrictHandleCheckPolicy", &v14) )
  {
    v11 = v14;
    a2[24] |= 0x200u;
    a2[34] = v11;
  }
  if ( !(unsigned int)RegQueryDword(a1, L"SystemCallDisablePolicy", &v14) )
  {
    v12 = v14;
    a2[24] |= 0x400u;
    a2[35] = v12;
  }
  if ( !(unsigned int)RegQueryDword(a1, L"ControlFlowGuardPolicy", &v14) )
  {
    v13 = v14;
    a2[24] |= 0x800u;
    a2[36] = v13;
  }
}

```

## disassembly

```asm
0x140006568  test    rcx, rcx
0x14000656b  jz      locret_140006783
0x140006571  mov     [rsp-18h+arg_8], rbx
0x140006576  mov     [rsp-18h+arg_10], rsi
0x14000657b  push    rbp
0x14000657c  push    rdi
0x14000657d  push    r14
0x14000657f  mov     rbp, rsp
0x140006582  sub     rsp, 20h
0x140006586  mov     rdi, rcx
0x140006589  mov     [rbp+arg_0], 0
0x140006590  xor     ecx, ecx
0x140006592  mov     rbx, rdx
0x140006595  xor     esi, esi
0x140006597  call    ScIsProcessMitigationPolicyActive
0x14000659c  test    eax, eax
0x14000659e  jz      short loc_1400065A3
0x1400065a0  mov     esi, [rbx+5Ch]
0x1400065a3  lea     r8, [rbp+arg_0]
0x1400065a7  mov     rcx, rdi
0x1400065aa  lea     rdx, aAslrpolicy; "AslrPolicy"
0x1400065b1  call    RegQueryDword
0x1400065b6  test    eax, eax
0x1400065b8  jnz     short loc_1400065C4
0x1400065ba  mov     eax, [rbp+arg_0]
0x1400065bd  or      dword ptr [rbx+60h], 1
0x1400065c1  mov     [rbx+64h], eax
0x1400065c4  lea     r8, [rbp+arg_0]
0x1400065c8  mov     rcx, rdi
0x1400065cb  lea     rdx, aBinarysignatur; "BinarySignaturePolicy"
0x1400065d2  call    RegQueryDword
0x1400065d7  mov     r14d, 2
0x1400065dd  test    eax, eax
0x1400065df  jnz     short loc_1400065E9
0x1400065e1  mov     eax, [rbp+arg_0]
0x1400065e4  mov     [rbx+68h], eax
0x1400065e7  jmp     short loc_1400065F4
0x1400065e9  test    esi, esi
0x1400065eb  jz      short loc_1400065F8
0x1400065ed  mov     dword ptr [rbx+68h], 1
0x1400065f4  or      [rbx+60h], r14d
0x1400065f8  lea     r8, [rbp+arg_0]
0x1400065fc  mov     rcx, rdi
0x1400065ff  lea     rdx, aChildprocesspo; "ChildProcessPolicy"
0x140006606  call    RegQueryDword
0x14000660b  test    eax, eax
0x14000660d  jnz     short loc_140006619
0x14000660f  mov     eax, [rbp+arg_0]
0x140006612  or      dword ptr [rbx+60h], 4
0x140006616  mov     [rbx+6Ch], eax
0x140006619  lea     r8, [rbp+arg_0]
0x14000661d  mov     rcx, rdi
0x140006620  lea     rdx, aDynamiccodepol; "DynamicCodePolicy"
0x140006627  call    RegQueryDword
0x14000662c  test    eax, eax
0x14000662e  jnz     short loc_140006638
0x140006630  mov     eax, [rbp+arg_0]
0x140006633  mov     [rbx+70h], eax
0x140006636  jmp     short loc_140006643
0x140006638  test    esi, esi
0x14000663a  jz      short loc_140006647
0x14000663c  mov     dword ptr [rbx+70h], 1
0x140006643  or      dword ptr [rbx+60h], 8
0x140006647  lea     r8, [rbp+arg_0]
0x14000664b  mov     rcx, rdi
0x14000664e  lea     rdx, aExtensionpoint; "ExtensionPointDisablePolicy"
0x140006655  call    RegQueryDword
0x14000665a  test    eax, eax
0x14000665c  jnz     short loc_140006666
0x14000665e  mov     eax, [rbp+arg_0]
0x140006661  mov     [rbx+74h], eax
0x140006664  jmp     short loc_140006671
0x140006666  test    esi, esi
0x140006668  jz      short loc_140006675
0x14000666a  mov     dword ptr [rbx+74h], 1
0x140006671  or      dword ptr [rbx+60h], 10h
0x140006675  lea     r8, [rbp+arg_0]
0x140006679  mov     rcx, rdi
0x14000667c  lea     rdx, aFontdisablepol; "FontDisablePolicy"
0x140006683  call    RegQueryDword
0x140006688  test    eax, eax
0x14000668a  jnz     short loc_140006696
0x14000668c  mov     eax, [rbp+arg_0]
0x14000668f  or      dword ptr [rbx+60h], 20h
0x140006693  mov     [rbx+78h], eax
0x140006696  lea     r8, [rbp+arg_0]
0x14000669a  mov     rcx, rdi
0x14000669d  lea     rdx, aImageloadpolic; "ImageLoadPolicy"
0x1400066a4  call    RegQueryDword
0x1400066a9  test    eax, eax
0x1400066ab  jnz     short loc_1400066B7
0x1400066ad  mov     eax, [rbp+arg_0]
0x1400066b0  or      dword ptr [rbx+60h], 40h
0x1400066b4  mov     [rbx+7Ch], eax
0x1400066b7  lea     r8, [rbp+arg_0]
0x1400066bb  mov     rcx, rdi
0x1400066be  lea     rdx, aRedirectiontru; "RedirectionTrustPolicy"
0x1400066c5  call    RegQueryDword
0x1400066ca  test    eax, eax
0x1400066cc  lea     r8, [rbp+arg_0]
0x1400066d0  lea     rdx, aSidechanneliso; "SideChannelIsolationPolicy"
0x1400066d7  mov     rcx, rdi
0x1400066da  cmovz   r14d, [rbp+arg_0]
0x1400066df  mov     [rbx+80h], r14d
0x1400066e6  bts     dword ptr [rbx+60h], 7
0x1400066eb  call    RegQueryDword
0x1400066f0  test    eax, eax
0x1400066f2  jnz     short loc_140006702
0x1400066f4  mov     eax, [rbp+arg_0]
0x1400066f7  bts     dword ptr [rbx+60h], 8
0x1400066fc  mov     [rbx+84h], eax
0x140006702  lea     r8, [rbp+arg_0]
0x140006706  mov     rcx, rdi
0x140006709  lea     rdx, aStricthandlech; "StrictHandleCheckPolicy"
0x140006710  call    RegQueryDword
0x140006715  test    eax, eax
0x140006717  jnz     short loc_140006727
0x140006719  mov     eax, [rbp+arg_0]
0x14000671c  bts     dword ptr [rbx+60h], 9
0x140006721  mov     [rbx+88h], eax
0x140006727  lea     r8, [rbp+arg_0]
0x14000672b  mov     rcx, rdi
0x14000672e  lea     rdx, aSystemcalldisa; "SystemCallDisablePolicy"
0x140006735  call    RegQueryDword
0x14000673a  test    eax, eax
0x14000673c  jnz     short loc_14000674C
0x14000673e  mov     eax, [rbp+arg_0]
0x140006741  bts     dword ptr [rbx+60h], 0Ah
0x140006746  mov     [rbx+8Ch], eax
0x14000674c  lea     r8, [rbp+arg_0]
0x140006750  mov     rcx, rdi
0x140006753  lea     rdx, aControlflowgua; "ControlFlowGuardPolicy"
0x14000675a  call    RegQueryDword
0x14000675f  test    eax, eax
0x140006761  jnz     short loc_140006771
0x140006763  mov     eax, [rbp+arg_0]
0x140006766  bts     dword ptr [rbx+60h], 0Bh
0x14000676b  mov     [rbx+90h], eax
0x140006771  mov     rbx, [rsp+20h+arg_8]
0x140006776  mov     rsi, [rsp+20h+arg_10]
0x14000677b  add     rsp, 20h
0x14000677f  pop     r14
0x140006781  pop     rdi
0x140006782  pop     rbp
0x140006783  retn
```
