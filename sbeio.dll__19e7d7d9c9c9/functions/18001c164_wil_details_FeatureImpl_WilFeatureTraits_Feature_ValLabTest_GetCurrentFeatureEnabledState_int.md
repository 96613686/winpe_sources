# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001c164`
- end: `0x18001c1d2`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001b924`

## callees

- `0x18001c164`
- `0x180026d60`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  unsigned int v6; // r9d
  int v7; // edx
  int v8; // r8d
  int v9; // eax
  _QWORD *result; // rax

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x3667CA2, (unsigned int)a2, a3, a4);
  *a2 = 0;
  v6 = FeatureEnabledState & 0xFFFFFF3F;
  v7 = 64;
  v8 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
  if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
  {
    v9 = 0;
    if ( v6 == 2 )
      v9 = 64;
    v7 = v9;
  }
  result = a2;
  *(_DWORD *)a2 = v7 | v8 | 1;
  return result;
}

```

## disassembly

```asm
0x18001c164  push    rbx
0x18001c166  sub     rsp, 20h
0x18001c16a  mov     ecx, 3667CA2h; this
0x18001c16f  mov     rbx, rdx
0x18001c172  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18001c177  mov     r9d, eax
0x18001c17a  mov     qword ptr [rbx], 0
0x18001c181  and     r9d, 0FFFFFF3Fh
0x18001c188  mov     ecx, eax
0x18001c18a  and     eax, 80h
0x18001c18f  mov     r8d, r9d
0x18001c192  and     r8d, 3
0x18001c196  mov     edx, 40h ; '@'
0x18001c19b  shl     r8d, 2
0x18001c19f  and     ecx, edx
0x18001c1a1  or      r8d, ecx
0x18001c1a4  shl     r8d, 2
0x18001c1a8  or      r8d, eax
0x18001c1ab  shl     r8d, 3
0x18001c1af  test    r9d, r9d
0x18001c1b2  jz      short loc_18001C1BF
0x18001c1b4  xor     eax, eax
0x18001c1b6  cmp     r9d, 2
0x18001c1ba  cmovz   eax, edx
0x18001c1bd  mov     edx, eax
0x18001c1bf  or      r8d, edx
0x18001c1c2  mov     rax, rbx
0x18001c1c5  or      r8d, 1
0x18001c1c9  mov     [rbx], r8d
0x18001c1cc  add     rsp, 20h
0x18001c1d0  pop     rbx
0x18001c1d1  retn
```
