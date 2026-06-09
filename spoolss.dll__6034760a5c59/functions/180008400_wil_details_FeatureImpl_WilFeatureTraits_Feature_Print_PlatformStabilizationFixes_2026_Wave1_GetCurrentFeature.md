# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180008400`
- end: `0x180008482`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007fd8`

## callees

- `0x180008400`
- `0x18000b744`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  unsigned int v6; // edx
  int v7; // r8d
  int v8; // eax
  int v9; // r8d
  int v10; // r8d
  _QWORD *result; // rax

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x3710FA3, (unsigned int)a2, a3, a4);
  *a2 = 0;
  v6 = FeatureEnabledState & 0xFFFFFF3F;
  v7 = FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3))));
  v8 = 0;
  v9 = 8 * v7;
  if ( v6 == 2 )
    v8 = 64;
  v10 = v8 | v9;
  result = a2;
  *(_DWORD *)a2 = ((v10 & 0x40) != 0) | v10;
  return result;
}

```

## disassembly

```asm
0x180008400  push    rbx
0x180008402  sub     rsp, 20h
0x180008406  mov     ecx, 3710FA3h; this
0x18000840b  mov     rbx, rdx
0x18000840e  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180008413  mov     edx, eax
0x180008415  mov     qword ptr [rbx], 0
0x18000841c  mov     ecx, eax
0x18000841e  and     edx, 0FFFFFF3Fh
0x180008424  and     eax, 80h
0x180008429  mov     r8d, edx
0x18000842c  and     r8d, 3
0x180008430  mov     r9d, 40h ; '@'
0x180008436  shl     r8d, 2
0x18000843a  and     ecx, r9d
0x18000843d  or      r8d, ecx
0x180008440  shl     r8d, 2
0x180008444  or      r8d, eax
0x180008447  xor     eax, eax
0x180008449  shl     r8d, 3
0x18000844d  test    edx, edx
0x18000844f  jz      short loc_180008458
0x180008451  cmp     edx, 2
0x180008454  cmovz   eax, r9d
0x180008458  or      r8d, eax
0x18000845b  mov     ecx, 0C00h
0x180008460  mov     eax, r8d
0x180008463  and     eax, ecx
0x180008465  test    r9b, r8b
0x180008468  jz      short loc_180008471
0x18000846a  mov     eax, 1
0x18000846f  jmp     short loc_180008473
0x180008471  xor     eax, eax
0x180008473  or      r8d, eax
0x180008476  mov     rax, rbx
0x180008479  mov     [rbx], r8d
0x18000847c  add     rsp, 20h
0x180008480  pop     rbx
0x180008481  retn
```
