# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180005cd0`
- end: `0x180005d92`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `194`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005984`

## callees

- `0x180005cd0`
- `0x1800084a0`
- `0x180009b84`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  int v6; // r8d
  int v7; // ecx
  int v8; // edx
  int v9; // edi
  int v10; // eax
  unsigned int v11; // r8d
  char v12; // cl

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x2E30A37, (unsigned int)a2, a3, a4);
  *a2 = 0;
  v6 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
  if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
  {
    v7 = 0;
    if ( (FeatureEnabledState & 0xFFFFFF3F) == 2 )
      v7 = 64;
    v8 = v7;
  }
  else
  {
    v7 = 64;
    v8 = 64;
  }
  v9 = 1;
  v10 = v8 | v6;
  v11 = v7 | v6;
  *(_DWORD *)a2 = v10;
  if ( (v11 & 0x400) != 0 && v11 >= 0x800 || (v12 = 0, (v11 & 0x40) != 0) )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::ReportUsage(`wil::Feature<__WilFeatureTraits_Feature_Standalone_Future>::GetImpl'::`2'::impl);
    v12 = 1;
  }
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v12 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x180005cd0  mov     [rsp+arg_0], rbx
0x180005cd5  mov     [rsp+arg_8], rsi
0x180005cda  push    rdi
0x180005cdb  sub     rsp, 20h
0x180005cdf  mov     ecx, 2E30A37h; this
0x180005ce4  mov     rbx, rdx
0x180005ce7  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180005cec  mov     edx, eax
0x180005cee  mov     qword ptr [rbx], 0
0x180005cf5  and     edx, 0FFFFFF3Fh
0x180005cfb  mov     ecx, eax
0x180005cfd  and     eax, 80h
0x180005d02  mov     r8d, edx
0x180005d05  and     r8d, 3
0x180005d09  mov     esi, 40h ; '@'
0x180005d0e  shl     r8d, 2
0x180005d12  and     ecx, esi
0x180005d14  or      r8d, ecx
0x180005d17  shl     r8d, 2
0x180005d1b  or      r8d, eax
0x180005d1e  shl     r8d, 3
0x180005d22  test    edx, edx
0x180005d24  jnz     short loc_180005D2C
0x180005d26  mov     ecx, esi
0x180005d28  mov     edx, esi
0x180005d2a  jmp     short loc_180005D36
0x180005d2c  xor     ecx, ecx
0x180005d2e  cmp     edx, 2
0x180005d31  cmovz   ecx, esi
0x180005d34  mov     edx, ecx
0x180005d36  mov     eax, r8d
0x180005d39  mov     edi, 1
0x180005d3e  or      eax, edx
0x180005d40  or      r8d, ecx
0x180005d43  mov     [rbx], eax
0x180005d45  bt      r8d, 0Ah
0x180005d4a  jnb     short loc_180005D55
0x180005d4c  cmp     r8d, 800h
0x180005d53  jnb     short loc_180005D5C
0x180005d55  xor     cl, cl
0x180005d57  test    sil, r8b
0x180005d5a  jz      short loc_180005D6B
0x180005d5c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_Future@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future> `wil::Feature<__WilFeatureTraits_Feature_Standalone_Future>::GetImpl(void)'::`2'::impl
0x180005d63  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180005d68  mov     cl, dil
0x180005d6b  mov     eax, [rbx]
0x180005d6d  test    sil, al
0x180005d70  jz      short loc_180005D76
0x180005d72  test    cl, cl
0x180005d74  jnz     short loc_180005D78
0x180005d76  xor     edi, edi
0x180005d78  mov     rsi, [rsp+28h+arg_8]
0x180005d7d  and     eax, 0FFFFFFFEh
0x180005d80  or      eax, edi
0x180005d82  mov     [rbx], eax
0x180005d84  mov     rax, rbx
0x180005d87  mov     rbx, [rsp+28h+arg_0]
0x180005d8c  add     rsp, 20h
0x180005d90  pop     rdi
0x180005d91  retn
```
