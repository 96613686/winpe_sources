# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ScenarioBasedDisconnectedStandby>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001c128`
- end: `0x18001c1ab`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ScenarioBasedDisconnectedStandby@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001c034`

## callees

- `0x180016cd4`
- `0x18001c128`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ScenarioBasedDisconnectedStandby>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x3599CD2, (unsigned int)a2, a3, a4);
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
0x18001c128  push    rbx
0x18001c12a  sub     rsp, 20h
0x18001c12e  mov     ecx, 3599CD2h; this
0x18001c133  mov     rbx, rdx
0x18001c136  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18001c13b  mov     edx, eax
0x18001c13d  mov     qword ptr [rbx], 0
0x18001c144  mov     ecx, eax
0x18001c146  and     edx, 0FFFFFF3Fh
0x18001c14c  and     eax, 80h
0x18001c151  mov     r8d, edx
0x18001c154  and     r8d, 3
0x18001c158  mov     r9d, 40h ; '@'
0x18001c15e  shl     r8d, 2
0x18001c162  and     ecx, r9d
0x18001c165  or      r8d, ecx
0x18001c168  shl     r8d, 2
0x18001c16c  or      r8d, eax
0x18001c16f  xor     eax, eax
0x18001c171  shl     r8d, 3
0x18001c175  test    edx, edx
0x18001c177  jz      short loc_18001C180
0x18001c179  cmp     edx, 2
0x18001c17c  cmovz   eax, r9d
0x18001c180  or      r8d, eax
0x18001c183  mov     ecx, 0C00h
0x18001c188  mov     eax, r8d
0x18001c18b  and     eax, ecx
0x18001c18d  test    r9b, r8b
0x18001c190  jz      short loc_18001C199
0x18001c192  mov     eax, 1
0x18001c197  jmp     short loc_18001C19B
0x18001c199  xor     eax, eax
0x18001c19b  or      r8d, eax
0x18001c19e  mov     rax, rbx
0x18001c1a1  mov     [rbx], r8d
0x18001c1a4  add     rsp, 20h
0x18001c1a8  pop     rbx
0x18001c1a9  retn
```
