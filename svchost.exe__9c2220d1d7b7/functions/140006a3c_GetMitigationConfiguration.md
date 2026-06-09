# GetMitigationConfiguration

- ea: `0x140006a3c`
- end: `0x140006c59`
- name: `GetMitigationConfiguration`
- size: `541`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140006320`
- `0x140006d84`

## callees

- `0x140001900`
- `0x140002830`
- `0x140006a3c`

## string_xrefs

- `0x140006b22`: `ExtensionPointDisablePolicy`
- `0x140006ba4`: `SideChannelIsolationPolicy`

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
0x140006a3c  test    rcx, rcx
0x140006a3f  jz      locret_140006C57
0x140006a45  mov     [rsp-18h+arg_8], rbx
0x140006a4a  mov     [rsp-18h+arg_10], rsi
0x140006a4f  push    rbp
0x140006a50  push    rdi
0x140006a51  push    r14
0x140006a53  mov     rbp, rsp
0x140006a56  sub     rsp, 20h
0x140006a5a  mov     rdi, rcx
0x140006a5d  mov     [rbp+arg_0], 0
0x140006a64  xor     ecx, ecx
0x140006a66  mov     rbx, rdx
0x140006a69  xor     esi, esi
0x140006a6b  call    ScIsProcessMitigationPolicyActive
0x140006a70  test    eax, eax
0x140006a72  jz      short loc_140006A77
0x140006a74  mov     esi, [rbx+5Ch]
0x140006a77  lea     r8, [rbp+arg_0]
0x140006a7b  mov     rcx, rdi
0x140006a7e  lea     rdx, aAslrpolicy; "AslrPolicy"
0x140006a85  call    RegQueryDword
0x140006a8a  test    eax, eax
0x140006a8c  jnz     short loc_140006A98
0x140006a8e  mov     eax, [rbp+arg_0]
0x140006a91  or      dword ptr [rbx+60h], 1
0x140006a95  mov     [rbx+64h], eax
0x140006a98  lea     r8, [rbp+arg_0]
0x140006a9c  mov     rcx, rdi
0x140006a9f  lea     rdx, aBinarysignatur; "BinarySignaturePolicy"
0x140006aa6  call    RegQueryDword
0x140006aab  mov     r14d, 2
0x140006ab1  test    eax, eax
0x140006ab3  jnz     short loc_140006ABD
0x140006ab5  mov     eax, [rbp+arg_0]
0x140006ab8  mov     [rbx+68h], eax
0x140006abb  jmp     short loc_140006AC8
0x140006abd  test    esi, esi
0x140006abf  jz      short loc_140006ACC
0x140006ac1  mov     dword ptr [rbx+68h], 1
0x140006ac8  or      [rbx+60h], r14d
0x140006acc  lea     r8, [rbp+arg_0]
0x140006ad0  mov     rcx, rdi
0x140006ad3  lea     rdx, aChildprocesspo; "ChildProcessPolicy"
0x140006ada  call    RegQueryDword
0x140006adf  test    eax, eax
0x140006ae1  jnz     short loc_140006AED
0x140006ae3  mov     eax, [rbp+arg_0]
0x140006ae6  or      dword ptr [rbx+60h], 4
0x140006aea  mov     [rbx+6Ch], eax
0x140006aed  lea     r8, [rbp+arg_0]
0x140006af1  mov     rcx, rdi
0x140006af4  lea     rdx, aDynamiccodepol; "DynamicCodePolicy"
0x140006afb  call    RegQueryDword
0x140006b00  test    eax, eax
0x140006b02  jnz     short loc_140006B0C
0x140006b04  mov     eax, [rbp+arg_0]
0x140006b07  mov     [rbx+70h], eax
0x140006b0a  jmp     short loc_140006B17
0x140006b0c  test    esi, esi
0x140006b0e  jz      short loc_140006B1B
0x140006b10  mov     dword ptr [rbx+70h], 1
0x140006b17  or      dword ptr [rbx+60h], 8
0x140006b1b  lea     r8, [rbp+arg_0]
0x140006b1f  mov     rcx, rdi
0x140006b22  lea     rdx, aExtensionpoint; "ExtensionPointDisablePolicy"
0x140006b29  call    RegQueryDword
0x140006b2e  test    eax, eax
0x140006b30  jnz     short loc_140006B3A
0x140006b32  mov     eax, [rbp+arg_0]
0x140006b35  mov     [rbx+74h], eax
0x140006b38  jmp     short loc_140006B45
0x140006b3a  test    esi, esi
0x140006b3c  jz      short loc_140006B49
0x140006b3e  mov     dword ptr [rbx+74h], 1
0x140006b45  or      dword ptr [rbx+60h], 10h
0x140006b49  lea     r8, [rbp+arg_0]
0x140006b4d  mov     rcx, rdi
0x140006b50  lea     rdx, aFontdisablepol; "FontDisablePolicy"
0x140006b57  call    RegQueryDword
0x140006b5c  test    eax, eax
0x140006b5e  jnz     short loc_140006B6A
0x140006b60  mov     eax, [rbp+arg_0]
0x140006b63  or      dword ptr [rbx+60h], 20h
0x140006b67  mov     [rbx+78h], eax
0x140006b6a  lea     r8, [rbp+arg_0]
0x140006b6e  mov     rcx, rdi
0x140006b71  lea     rdx, aImageloadpolic; "ImageLoadPolicy"
0x140006b78  call    RegQueryDword
0x140006b7d  test    eax, eax
0x140006b7f  jnz     short loc_140006B8B
0x140006b81  mov     eax, [rbp+arg_0]
0x140006b84  or      dword ptr [rbx+60h], 40h
0x140006b88  mov     [rbx+7Ch], eax
0x140006b8b  lea     r8, [rbp+arg_0]
0x140006b8f  mov     rcx, rdi
0x140006b92  lea     rdx, aRedirectiontru; "RedirectionTrustPolicy"
0x140006b99  call    RegQueryDword
0x140006b9e  test    eax, eax
0x140006ba0  lea     r8, [rbp+arg_0]
0x140006ba4  lea     rdx, aSidechanneliso; "SideChannelIsolationPolicy"
0x140006bab  mov     rcx, rdi
0x140006bae  cmovz   r14d, [rbp+arg_0]
0x140006bb3  mov     [rbx+80h], r14d
0x140006bba  bts     dword ptr [rbx+60h], 7
0x140006bbf  call    RegQueryDword
0x140006bc4  test    eax, eax
0x140006bc6  jnz     short loc_140006BD6
0x140006bc8  mov     eax, [rbp+arg_0]
0x140006bcb  bts     dword ptr [rbx+60h], 8
0x140006bd0  mov     [rbx+84h], eax
0x140006bd6  lea     r8, [rbp+arg_0]
0x140006bda  mov     rcx, rdi
0x140006bdd  lea     rdx, aStricthandlech; "StrictHandleCheckPolicy"
0x140006be4  call    RegQueryDword
0x140006be9  test    eax, eax
0x140006beb  jnz     short loc_140006BFB
0x140006bed  mov     eax, [rbp+arg_0]
0x140006bf0  bts     dword ptr [rbx+60h], 9
0x140006bf5  mov     [rbx+88h], eax
0x140006bfb  lea     r8, [rbp+arg_0]
0x140006bff  mov     rcx, rdi
0x140006c02  lea     rdx, aSystemcalldisa; "SystemCallDisablePolicy"
0x140006c09  call    RegQueryDword
0x140006c0e  test    eax, eax
0x140006c10  jnz     short loc_140006C20
0x140006c12  mov     eax, [rbp+arg_0]
0x140006c15  bts     dword ptr [rbx+60h], 0Ah
0x140006c1a  mov     [rbx+8Ch], eax
0x140006c20  lea     r8, [rbp+arg_0]
0x140006c24  mov     rcx, rdi
0x140006c27  lea     rdx, aControlflowgua; "ControlFlowGuardPolicy"
0x140006c2e  call    RegQueryDword
0x140006c33  test    eax, eax
0x140006c35  jnz     short loc_140006C45
0x140006c37  mov     eax, [rbp+arg_0]
0x140006c3a  bts     dword ptr [rbx+60h], 0Bh
0x140006c3f  mov     [rbx+90h], eax
0x140006c45  mov     rbx, [rsp+20h+arg_8]
0x140006c4a  mov     rsi, [rsp+20h+arg_10]
0x140006c4f  add     rsp, 20h
0x140006c53  pop     r14
0x140006c55  pop     rdi
0x140006c56  pop     rbp
0x140006c57  retn
```
