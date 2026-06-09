# wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix52931714>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180005b9c`
- end: `0x180005c55`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix52931714@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `185`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800057c4`

## callees

- `0x180005b9c`
- `0x180009b84`
- `0x18000af60`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix52931714>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  unsigned int v6; // edx
  int v7; // r8d
  int v8; // eax
  int v9; // edi
  char v10; // si
  char IsEnabled; // al
  _QWORD *result; // rax

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x327AC82, (unsigned int)a2, a3, a4);
  *a2 = 0;
  v6 = FeatureEnabledState & 0xFFFFFF3F;
  v7 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
  if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
  {
    v8 = 0;
    if ( v6 == 2 )
      v8 = 64;
    v7 |= v8;
  }
  *(_DWORD *)a2 = v7;
  v9 = 1;
  if ( (v7 & 0xC00) == 0xC00 )
  {
    v10 = 1;
  }
  else
  {
    v10 = 0;
    IsEnabled = 0;
    if ( (v7 & 0x40) == 0 )
      goto LABEL_11;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl'::`2'::impl);
  if ( v10 && !IsEnabled )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_11:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !IsEnabled )
    v9 = 0;
  result = a2;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return result;
}

```

## disassembly

```asm
0x180005b9c  push    rbx
0x180005b9e  push    rbp
0x180005b9f  push    rsi
0x180005ba0  push    rdi
0x180005ba1  sub     rsp, 28h
0x180005ba5  mov     ecx, 327AC82h; this
0x180005baa  mov     rbx, rdx
0x180005bad  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180005bb2  mov     edx, eax
0x180005bb4  mov     qword ptr [rbx], 0
0x180005bbb  and     edx, 0FFFFFF3Fh
0x180005bc1  mov     ecx, eax
0x180005bc3  and     eax, 80h
0x180005bc8  mov     r8d, edx
0x180005bcb  and     r8d, 3
0x180005bcf  mov     ebp, 40h ; '@'
0x180005bd4  shl     r8d, 2
0x180005bd8  and     ecx, ebp
0x180005bda  or      r8d, ecx
0x180005bdd  shl     r8d, 2
0x180005be1  or      r8d, eax
0x180005be4  shl     r8d, 3
0x180005be8  test    edx, edx
0x180005bea  jz      short loc_180005BF7
0x180005bec  xor     eax, eax
0x180005bee  cmp     edx, 2
0x180005bf1  cmovz   eax, ebp
0x180005bf4  or      r8d, eax
0x180005bf7  mov     ecx, 0C00h
0x180005bfc  mov     [rbx], r8d
0x180005bff  mov     eax, r8d
0x180005c02  mov     edi, 1
0x180005c07  and     eax, ecx
0x180005c09  cmp     eax, ecx
0x180005c0b  jnz     short loc_180005C12
0x180005c0d  mov     sil, dil
0x180005c10  jmp     short loc_180005C1C
0x180005c12  xor     sil, sil
0x180005c15  xor     al, al
0x180005c17  test    bpl, r8b
0x180005c1a  jz      short loc_180005C35
0x180005c1c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UxAccOptimization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization> `wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl(void)'::`2'::impl
0x180005c23  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(wil::ReportingKind)
0x180005c28  test    sil, sil
0x180005c2b  jz      short loc_180005C35
0x180005c2d  test    al, al
0x180005c2f  jnz     short loc_180005C35
0x180005c31  btr     dword ptr [rbx], 0Ah
0x180005c35  mov     ecx, [rbx]
0x180005c37  test    bpl, cl
0x180005c3a  jz      short loc_180005C40
0x180005c3c  test    al, al
0x180005c3e  jnz     short loc_180005C42
0x180005c40  xor     edi, edi
0x180005c42  and     ecx, 0FFFFFFFEh
0x180005c45  mov     rax, rbx
0x180005c48  or      ecx, edi
0x180005c4a  mov     [rbx], ecx
0x180005c4c  add     rsp, 28h
0x180005c50  pop     rdi
0x180005c51  pop     rsi
0x180005c52  pop     rbp
0x180005c53  pop     rbx
0x180005c54  retn
```
