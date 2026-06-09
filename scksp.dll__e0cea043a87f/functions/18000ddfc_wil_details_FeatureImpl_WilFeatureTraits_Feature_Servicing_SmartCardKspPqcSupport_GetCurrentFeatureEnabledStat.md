# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000ddfc`
- end: `0x18000ded5`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18000da28`

## callees

- `0x18000ddfc`
- `0x1800122f0`
- `0x18003d010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // edi
  int v5; // edx
  int v6; // eax
  int v7; // ecx
  char v8; // si
  char IsEnabled; // al
  _QWORD *result; // rax

  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  v4 = 1;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v5 = v2(59873727, 1);
  }
  else
  {
    v5 = 0;
  }
  *a2 = 0;
  if ( (v5 & 0xFFFFFF3F) != 0 )
  {
    v6 = 0;
    if ( (v5 & 0xFFFFFF3F) == 2 )
      v6 = 64;
  }
  else
  {
    v6 = 64;
  }
  v7 = v6 | (8 * (v5 & 0x80 | (4 * (v5 & 0x40 | (4 * (v5 & 3))))));
  *(_DWORD *)a2 = v7;
  if ( (v7 & 0xC00) == 0xC00 )
  {
    v8 = 1;
  }
  else
  {
    v8 = 0;
    IsEnabled = 0;
    if ( (v7 & 0x40) == 0 )
      goto LABEL_15;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl'::`2'::impl);
  if ( v8 && !IsEnabled )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_15:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !IsEnabled )
    v4 = 0;
  result = a2;
  *(_DWORD *)a2 = v4 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return result;
}

```

## disassembly

```asm
0x18000ddfc  push    rbx
0x18000ddfe  push    rbp
0x18000ddff  push    rsi
0x18000de00  push    rdi
0x18000de01  sub     rsp, 28h
0x18000de05  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000de0c  mov     rbx, rdx
0x18000de0f  mov     edi, 1
0x18000de14  test    rax, rax
0x18000de17  jz      short loc_18000DE29
0x18000de19  mov     edx, edi
0x18000de1b  mov     ecx, 39199BFh
0x18000de20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de25  mov     edx, eax
0x18000de27  jmp     short loc_18000DE37
0x18000de29  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000de30  test    rax, rax
0x18000de33  jnz     short loc_18000DE19
0x18000de35  xor     edx, edx
0x18000de37  mov     r8d, edx
0x18000de3a  mov     qword ptr [rbx], 0
0x18000de41  and     r8d, 0FFFFFF3Fh
0x18000de48  mov     eax, edx
0x18000de4a  and     edx, 80h
0x18000de50  mov     ecx, r8d
0x18000de53  and     ecx, 3
0x18000de56  mov     ebp, 40h ; '@'
0x18000de5b  shl     ecx, 2
0x18000de5e  and     eax, ebp
0x18000de60  or      ecx, eax
0x18000de62  shl     ecx, 2
0x18000de65  or      ecx, edx
0x18000de67  shl     ecx, 3
0x18000de6a  test    r8d, r8d
0x18000de6d  jnz     short loc_18000DE73
0x18000de6f  mov     eax, ebp
0x18000de71  jmp     short loc_18000DE7C
0x18000de73  xor     eax, eax
0x18000de75  cmp     r8d, 2
0x18000de79  cmovz   eax, ebp
0x18000de7c  or      ecx, eax
0x18000de7e  mov     edx, 0C00h
0x18000de83  mov     eax, ecx
0x18000de85  mov     [rbx], ecx
0x18000de87  and     eax, edx
0x18000de89  cmp     eax, edx
0x18000de8b  jnz     short loc_18000DE92
0x18000de8d  mov     sil, dil
0x18000de90  jmp     short loc_18000DE9C
0x18000de92  xor     sil, sil
0x18000de95  xor     al, al
0x18000de97  test    bpl, cl
0x18000de9a  jz      short loc_18000DEB5
0x18000de9c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UxAccOptimization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization> `wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl(void)'::`2'::impl
0x18000dea3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(wil::ReportingKind)
0x18000dea8  test    sil, sil
0x18000deab  jz      short loc_18000DEB5
0x18000dead  test    al, al
0x18000deaf  jnz     short loc_18000DEB5
0x18000deb1  btr     dword ptr [rbx], 0Ah
0x18000deb5  mov     ecx, [rbx]
0x18000deb7  test    bpl, cl
0x18000deba  jz      short loc_18000DEC0
0x18000debc  test    al, al
0x18000debe  jnz     short loc_18000DEC2
0x18000dec0  xor     edi, edi
0x18000dec2  and     ecx, 0FFFFFFFEh
0x18000dec5  mov     rax, rbx
0x18000dec8  or      ecx, edi
0x18000deca  mov     [rbx], ecx
0x18000decc  add     rsp, 28h
0x18000ded0  pop     rdi
0x18000ded1  pop     rsi
0x18000ded2  pop     rbp
0x18000ded3  pop     rbx
0x18000ded4  retn
```
