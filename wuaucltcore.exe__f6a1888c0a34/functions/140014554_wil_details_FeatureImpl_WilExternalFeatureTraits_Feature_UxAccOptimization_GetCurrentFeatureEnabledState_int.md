# wil::details::FeatureImpl<__WilExternalFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)

- ea: `0x140014554`
- end: `0x14001466b`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilExternalFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140014674`

## callees

- `0x140009f10`
- `0x140014554`
- `0x1400206e0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilExternalFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // eax
  unsigned int v5; // r8d
  int v6; // ecx
  int v7; // eax
  int v8; // edx
  unsigned int v9; // eax
  bool v10; // dl
  int v11; // esi
  char v12; // bp
  bool v13; // al
  _QWORD *result; // rax

  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( !g_wil_details_internalGetFeatureEnabledState )
  {
    v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState;
    if ( !g_wil_details_apiGetFeatureEnabledState )
    {
      *a2 = 0;
      v6 = 0;
      goto LABEL_8;
    }
  }
  v4 = v2(48433719, 64);
  *a2 = 0;
  v5 = v4 & 0xFFFFFF3F;
  v6 = 8 * (v4 & 0x80 | (4 * (v4 & 0x40 | (4 * (v4 & 3)))));
  if ( (v4 & 0xFFFFFF3F) == 0 )
  {
LABEL_8:
    v7 = 0;
    v8 = v6;
    goto LABEL_9;
  }
  v7 = 0;
  if ( v5 == 2 )
    v7 = 64;
  v8 = v6 | v7;
LABEL_9:
  *(_DWORD *)a2 = v8;
  v9 = v6 | v7;
  v10 = 0;
  v11 = 1;
  if ( (v9 & 0x400) != 0 && v9 >= 0x800 )
  {
    v12 = 1;
  }
  else
  {
    v12 = 0;
    if ( (v9 & 0x40) == 0 )
      goto LABEL_16;
  }
  v13 = wil::Wil_Staging_AreExternalFeatureDependenciesEnabled((wil *)0x2E30A37);
  v10 = v13;
  if ( v12 && !v13 )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_16:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v10 )
    v11 = 0;
  result = a2;
  *(_DWORD *)a2 = v11 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return result;
}

```

## disassembly

```asm
0x140014554  mov     [rsp+arg_0], rbx
0x140014559  mov     [rsp+arg_8], rbp
0x14001455e  mov     [rsp+arg_10], rsi
0x140014563  push    rdi
0x140014564  sub     rsp, 20h
0x140014568  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x14001456f  mov     rbx, rdx
0x140014572  test    rax, rax
0x140014575  jnz     short loc_140014583
0x140014577  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x14001457e  test    rax, rax
0x140014581  jz      short loc_1400145D6
0x140014583  mov     edi, 40h ; '@'
0x140014588  mov     ecx, 2E30A37h
0x14001458d  mov     edx, edi
0x14001458f  call    _guard_dispatch_icall
0x140014594  mov     r8d, eax
0x140014597  mov     qword ptr [rbx], 0
0x14001459e  and     r8d, 0FFFFFF3Fh
0x1400145a5  mov     edx, eax
0x1400145a7  and     eax, edi
0x1400145a9  and     edx, 80h
0x1400145af  mov     ecx, r8d
0x1400145b2  and     ecx, 3
0x1400145b5  shl     ecx, 2
0x1400145b8  or      ecx, eax
0x1400145ba  shl     ecx, 2
0x1400145bd  or      ecx, edx
0x1400145bf  shl     ecx, 3
0x1400145c2  test    r8d, r8d
0x1400145c5  jz      short loc_1400145FD
0x1400145c7  xor     eax, eax
0x1400145c9  cmp     r8d, 2
0x1400145cd  cmovz   eax, edi
0x1400145d0  mov     edx, eax
0x1400145d2  or      edx, ecx
0x1400145d4  jmp     short loc_140014601
0x1400145d6  xor     ecx, ecx
0x1400145d8  mov     qword ptr [rdx], 0
0x1400145df  xor     eax, eax
0x1400145e1  and     ecx, 3
0x1400145e4  shl     ecx, 2
0x1400145e7  lea     edi, [rax+40h]
0x1400145ea  and     eax, edi
0x1400145ec  or      ecx, eax
0x1400145ee  xor     eax, eax
0x1400145f0  and     eax, 80h
0x1400145f5  shl     ecx, 2
0x1400145f8  or      ecx, eax
0x1400145fa  shl     ecx, 3
0x1400145fd  xor     eax, eax
0x1400145ff  mov     edx, ecx
0x140014601  mov     [rbx], edx
0x140014603  or      eax, ecx
0x140014605  xor     dl, dl; unsigned int
0x140014607  mov     esi, 1
0x14001460c  bt      eax, 0Ah
0x140014610  jnb     short loc_14001461E
0x140014612  cmp     eax, 800h
0x140014617  jb      short loc_14001461E
0x140014619  mov     bpl, sil
0x14001461c  jmp     short loc_140014626
0x14001461e  xor     bpl, bpl
0x140014621  test    dil, al
0x140014624  jz      short loc_14001463F
0x140014626  mov     ecx, 2E30A37h; this
0x14001462b  call    ?Wil_Staging_AreExternalFeatureDependenciesEnabled@wil@@YA_NI@Z; wil::Wil_Staging_AreExternalFeatureDependenciesEnabled(uint)
0x140014630  mov     dl, al
0x140014632  test    bpl, bpl
0x140014635  jz      short loc_14001463F
0x140014637  test    al, al
0x140014639  jnz     short loc_14001463F
0x14001463b  btr     dword ptr [rbx], 0Ah
0x14001463f  mov     ecx, [rbx]
0x140014641  test    dil, cl
0x140014644  jz      short loc_14001464A
0x140014646  test    dl, dl
0x140014648  jnz     short loc_14001464C
0x14001464a  xor     esi, esi
0x14001464c  mov     rbp, [rsp+28h+arg_8]
0x140014651  and     ecx, 0FFFFFFFEh
0x140014654  or      ecx, esi
0x140014656  mov     rax, rbx
0x140014659  mov     rsi, [rsp+28h+arg_10]
0x14001465e  mov     [rbx], ecx
0x140014660  mov     rbx, [rsp+28h+arg_0]
0x140014665  add     rsp, 20h
0x140014669  pop     rdi
0x14001466a  retn
```
