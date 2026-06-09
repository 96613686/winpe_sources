# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x1800180d8`
- end: `0x180018241`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800178f8`

## callees

- `0x180017168`
- `0x1800180d8`
- `0x180018ac8`
- `0x18001901c`
- `0x18001e010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // edx
  unsigned int v5; // r8d
  int v6; // ecx
  __int64 v7; // rdx
  int v8; // r8d
  int v9; // edi
  int v10; // eax
  unsigned int v11; // ecx
  char v12; // si
  wil::details *v13; // rcx
  unsigned int v14; // r8d
  __int64 v16; // [rsp+60h] [rbp+8h] BYREF
  __int64 v17; // [rsp+68h] [rbp+10h] BYREF

  v16 = a1;
  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(58988972, 3);
  }
  else
  {
    v4 = 0;
  }
  *a2 = 0;
  v5 = v4 & 0xFFFFFF3F;
  v6 = 8 * (v4 & 0x80 | (4 * (v4 & 0x40 | (4 * (v4 & 3)))));
  if ( (v4 & 0xFFFFFF3F) != 0 )
  {
    v7 = 0;
    if ( v5 == 2 )
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
  if ( (v11 & 0x400) != 0 && v11 >= 0x800 )
  {
    v12 = 1;
  }
  else
  {
    v12 = 0;
    LOBYTE(v7) = 0;
    if ( (v11 & 0x40) == 0 )
      goto LABEL_22;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl'::`2'::impl,
                          v7) )
  {
    v14 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor & 4) == 0 )
    {
      v17 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
               v13,
               &v17);
      v14 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(&qword_1800295C8, 58599532, (v14 >> 10) & 1, (v14 >> 11) & 1, &v16, 1, 0);
    LOBYTE(v7) = 1;
  }
  else
  {
    LOBYTE(v7) = 0;
  }
  if ( v12 && !(_BYTE)v7 )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_22:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !(_BYTE)v7 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x1800180d8  mov     [rsp+arg_10], rbx
0x1800180dd  mov     [rsp+arg_0], rcx
0x1800180e2  push    rbp
0x1800180e3  push    rsi
0x1800180e4  push    rdi
0x1800180e5  sub     rsp, 40h
0x1800180e9  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800180f0  mov     rbx, rdx
0x1800180f3  test    rax, rax
0x1800180f6  jz      short loc_18001810B
0x1800180f8  mov     edx, 3
0x1800180fd  mov     ecx, 38419ACh
0x180018102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018107  mov     edx, eax
0x180018109  jmp     short loc_180018119
0x18001810b  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180018112  test    rax, rax
0x180018115  jnz     short loc_1800180F8
0x180018117  xor     edx, edx
0x180018119  mov     r8d, edx
0x18001811c  mov     qword ptr [rbx], 0
0x180018123  and     r8d, 0FFFFFF3Fh
0x18001812a  mov     eax, edx
0x18001812c  and     edx, 80h
0x180018132  mov     ecx, r8d
0x180018135  and     ecx, 3
0x180018138  mov     ebp, 40h ; '@'
0x18001813d  shl     ecx, 2
0x180018140  and     eax, ebp
0x180018142  or      ecx, eax
0x180018144  shl     ecx, 2
0x180018147  or      ecx, edx
0x180018149  shl     ecx, 3
0x18001814c  test    r8d, r8d
0x18001814f  jnz     short loc_180018158
0x180018151  mov     edx, ebp
0x180018153  mov     r8d, ebp
0x180018156  jmp     short loc_180018164
0x180018158  xor     edx, edx
0x18001815a  cmp     r8d, 2
0x18001815e  cmovz   edx, ebp
0x180018161  mov     r8d, edx
0x180018164  mov     eax, ecx
0x180018166  mov     edi, 1
0x18001816b  or      eax, r8d
0x18001816e  or      ecx, edx
0x180018170  mov     [rbx], eax
0x180018172  bt      ecx, 0Ah
0x180018176  jnb     short loc_180018185
0x180018178  cmp     ecx, 800h
0x18001817e  jb      short loc_180018185
0x180018180  mov     sil, dil
0x180018183  jmp     short loc_180018193
0x180018185  xor     sil, sil
0x180018188  xor     dl, dl
0x18001818a  test    bpl, cl
0x18001818d  jz      loc_18001821D
0x180018193  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestAccPerf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf> `wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl(void)'::`2'::impl
0x18001819a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(wil::ReportingKind)
0x18001819f  test    al, al
0x1800181a1  jz      short loc_18001820E
0x1800181a3  mov     rax, cs:Feature_Standalone_26_01_NonSec__descriptor
0x1800181aa  mov     r8d, [rax]
0x1800181ad  test    r8b, 4
0x1800181b1  jnz     short loc_1800181C8
0x1800181b3  lea     rdx, [rsp+58h+arg_8]
0x1800181b8  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)
0x1800181bd  mov     rcx, [rax]
0x1800181c0  mov     [rsp+58h+arg_8], rcx
0x1800181c5  mov     r8d, ecx
0x1800181c8  xor     eax, eax
0x1800181ca  mov     word ptr [rsp+58h+arg_0+4], 3
0x1800181d1  mov     r9d, r8d
0x1800181d4  mov     [rsp+58h+var_28], eax
0x1800181d8  mov     dword ptr [rsp+58h+arg_0], eax
0x1800181dc  lea     rcx, qword_1800295C8
0x1800181e3  shr     r9d, 0Bh
0x1800181e7  lea     rax, [rsp+58h+arg_0]
0x1800181ec  shr     r8d, 0Ah
0x1800181f0  and     r9d, edi
0x1800181f3  and     r8d, edi
0x1800181f6  mov     [rsp+58h+var_30], edi
0x1800181fa  mov     edx, 37E286Ch
0x1800181ff  mov     [rsp+58h+var_38], rax
0x180018204  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180018209  mov     dl, dil
0x18001820c  jmp     short loc_180018210
0x18001820e  xor     dl, dl
0x180018210  test    sil, sil
0x180018213  jz      short loc_18001821D
0x180018215  test    dl, dl
0x180018217  jnz     short loc_18001821D
0x180018219  btr     dword ptr [rbx], 0Ah
0x18001821d  mov     eax, [rbx]
0x18001821f  test    bpl, al
0x180018222  jz      short loc_180018228
0x180018224  test    dl, dl
0x180018226  jnz     short loc_18001822A
0x180018228  xor     edi, edi
0x18001822a  and     eax, 0FFFFFFFEh
0x18001822d  or      eax, edi
0x18001822f  mov     [rbx], eax
0x180018231  mov     rax, rbx
0x180018234  mov     rbx, [rsp+58h+arg_10]
0x180018239  add     rsp, 40h
0x18001823d  pop     rdi
0x18001823e  pop     rsi
0x18001823f  pop     rbp
0x180018240  retn
```
