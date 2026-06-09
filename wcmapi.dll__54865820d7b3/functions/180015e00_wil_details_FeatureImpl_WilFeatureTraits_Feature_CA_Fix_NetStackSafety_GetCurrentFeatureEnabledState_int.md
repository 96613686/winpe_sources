# wil::details::FeatureImpl<__WilFeatureTraits_Feature_CA_Fix_NetStackSafety>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180015e00`
- end: `0x180015ec0`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CA_Fix_NetStackSafety@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180015660`

## callees

- `0x180015e00`
- `0x180016cd4`
- `0x180016d78`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_CA_Fix_NetStackSafety>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  unsigned int v6; // edx
  int v7; // r8d
  int v8; // eax
  unsigned int v9; // r8d
  int v10; // edi
  char v11; // si
  char IsEnabled; // al
  _QWORD *result; // rax

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x389B267, (unsigned int)a2, a3, a4);
  *a2 = 0;
  v6 = FeatureEnabledState & 0xFFFFFF3F;
  v7 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
  if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
  {
    v8 = 0;
    if ( v6 == 2 )
      v8 = 64;
  }
  else
  {
    v8 = 64;
  }
  v9 = v8 | v7;
  v10 = 1;
  *(_DWORD *)a2 = v9;
  if ( (v9 & 0x400) != 0 && v9 >= 0x800 )
  {
    v11 = 1;
  }
  else
  {
    v11 = 0;
    IsEnabled = 0;
    if ( (v9 & 0x40) == 0 )
      goto LABEL_12;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl'::`2'::impl);
  if ( v11 && !IsEnabled )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_12:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !IsEnabled )
    v10 = 0;
  result = a2;
  *(_DWORD *)a2 = v10 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return result;
}

```

## disassembly

```asm
0x180015e00  push    rbx
0x180015e02  push    rbp
0x180015e03  push    rsi
0x180015e04  push    rdi
0x180015e05  sub     rsp, 28h
0x180015e09  mov     ecx, 389B267h; this
0x180015e0e  mov     rbx, rdx
0x180015e11  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180015e16  mov     edx, eax
0x180015e18  mov     qword ptr [rbx], 0
0x180015e1f  and     edx, 0FFFFFF3Fh
0x180015e25  mov     ecx, eax
0x180015e27  and     eax, 80h
0x180015e2c  mov     r8d, edx
0x180015e2f  and     r8d, 3
0x180015e33  mov     ebp, 40h ; '@'
0x180015e38  shl     r8d, 2
0x180015e3c  and     ecx, ebp
0x180015e3e  or      r8d, ecx
0x180015e41  shl     r8d, 2
0x180015e45  or      r8d, eax
0x180015e48  shl     r8d, 3
0x180015e4c  test    edx, edx
0x180015e4e  jnz     short loc_180015E54
0x180015e50  mov     eax, ebp
0x180015e52  jmp     short loc_180015E5C
0x180015e54  xor     eax, eax
0x180015e56  cmp     edx, 2
0x180015e59  cmovz   eax, ebp
0x180015e5c  or      r8d, eax
0x180015e5f  mov     edi, 1
0x180015e64  mov     [rbx], r8d
0x180015e67  bt      r8d, 0Ah
0x180015e6c  jnb     short loc_180015E7C
0x180015e6e  cmp     r8d, 800h
0x180015e75  jb      short loc_180015E7C
0x180015e77  mov     sil, dil
0x180015e7a  jmp     short loc_180015E86
0x180015e7c  xor     sil, sil
0x180015e7f  xor     al, al
0x180015e81  test    bpl, r8b
0x180015e84  jz      short loc_180015E9F
0x180015e86  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestLoc1Perf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf> `wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl(void)'::`2'::impl
0x180015e8d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(wil::ReportingKind)
0x180015e92  test    sil, sil
0x180015e95  jz      short loc_180015E9F
0x180015e97  test    al, al
0x180015e99  jnz     short loc_180015E9F
0x180015e9b  btr     dword ptr [rbx], 0Ah
0x180015e9f  mov     ecx, [rbx]
0x180015ea1  test    bpl, cl
0x180015ea4  jz      short loc_180015EAA
0x180015ea6  test    al, al
0x180015ea8  jnz     short loc_180015EAC
0x180015eaa  xor     edi, edi
0x180015eac  and     ecx, 0FFFFFFFEh
0x180015eaf  mov     rax, rbx
0x180015eb2  or      ecx, edi
0x180015eb4  mov     [rbx], ecx
0x180015eb6  add     rsp, 28h
0x180015eba  pop     rdi
0x180015ebb  pop     rsi
0x180015ebc  pop     rbp
0x180015ebd  pop     rbx
0x180015ebe  retn
```
