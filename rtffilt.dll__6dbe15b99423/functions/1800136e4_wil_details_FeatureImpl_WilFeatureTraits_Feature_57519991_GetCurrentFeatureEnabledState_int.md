# wil::details::FeatureImpl<__WilFeatureTraits_Feature_57519991>::GetCurrentFeatureEnabledState(int *)

- ea: `0x1800136e4`
- end: `0x1800137e0`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_57519991@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800129cc`

## callees

- `0x18000c6b4`
- `0x1800136e4`
- `0x180015190`
- `0x18001b010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_57519991>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // edx
  unsigned int v5; // r8d
  int v6; // eax
  int v7; // edx
  int v8; // ecx
  __int16 v9; // dx
  int v10; // edi
  char v11; // si
  bool v12; // cl

  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(57519991, 3);
  }
  else
  {
    v4 = 0;
  }
  *a2 = 0;
  v5 = v4 & 0xFFFFFF3F;
  v6 = 0;
  v7 = 8 * (v4 & 0x80 | (4 * (v4 & 0x40 | (4 * (v4 & 3)))));
  v8 = v7;
  if ( v5 )
  {
    if ( v5 == 2 )
      v6 = 64;
    v8 = v6 | v7;
  }
  v9 = v6 | v7;
  *(_DWORD *)a2 = v8;
  v10 = 1;
  if ( (v9 & 0xC00) == 0xC00 )
  {
    v11 = 1;
  }
  else
  {
    v11 = 0;
    v12 = 0;
    if ( (v9 & 0x40) == 0 )
      goto LABEL_19;
  }
  v12 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_47942714>::GetImpl'::`2'::impl)
     && (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl'::`2'::impl);
  if ( v11 && !v12 )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_19:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v12 )
    v10 = 0;
  *(_DWORD *)a2 = v10 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x1800136e4  push    rbx
0x1800136e6  push    rbp
0x1800136e7  push    rsi
0x1800136e8  push    rdi
0x1800136e9  sub     rsp, 28h
0x1800136ed  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800136f4  mov     rbx, rdx
0x1800136f7  mov     edi, 3
0x1800136fc  test    rax, rax
0x1800136ff  jz      short loc_180013711
0x180013701  mov     edx, edi
0x180013703  mov     ecx, 36DAF77h
0x180013708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001370d  mov     edx, eax
0x18001370f  jmp     short loc_18001371F
0x180013711  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180013718  test    rax, rax
0x18001371b  jnz     short loc_180013701
0x18001371d  xor     edx, edx
0x18001371f  mov     r8d, edx
0x180013722  mov     qword ptr [rbx], 0
0x180013729  mov     eax, edx
0x18001372b  and     r8d, 0FFFFFF3Fh
0x180013732  and     edx, 80h
0x180013738  mov     ecx, r8d
0x18001373b  and     ecx, edi
0x18001373d  mov     ebp, 40h ; '@'
0x180013742  shl     ecx, 2
0x180013745  and     eax, ebp
0x180013747  or      ecx, eax
0x180013749  xor     eax, eax
0x18001374b  shl     ecx, 2
0x18001374e  or      ecx, edx
0x180013750  lea     edx, ds:0[rcx*8]
0x180013757  mov     ecx, edx
0x180013759  test    r8d, r8d
0x18001375c  jz      short loc_180013767
0x18001375e  cmp     r8d, 2
0x180013762  cmovz   eax, ebp
0x180013765  or      ecx, eax
0x180013767  or      edx, eax
0x180013769  mov     [rbx], ecx
0x18001376b  mov     ecx, 0C00h
0x180013770  mov     eax, edx
0x180013772  and     eax, ecx
0x180013774  mov     edi, 1
0x180013779  cmp     eax, ecx
0x18001377b  jnz     short loc_180013782
0x18001377d  mov     sil, dil
0x180013780  jmp     short loc_18001378C
0x180013782  xor     sil, sil
0x180013785  xor     cl, cl
0x180013787  test    bpl, dl
0x18001378a  jz      short loc_1800137C0
0x18001378c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_47942714@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_47942714@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714> `wil::Feature<__WilFeatureTraits_Feature_47942714>::GetImpl(void)'::`2'::impl
0x180013793  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_47942714@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::__private_IsEnabled(wil::ReportingKind)
0x180013798  test    al, al
0x18001379a  jz      short loc_1800137B1
0x18001379c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UxAccOptimization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization> `wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl(void)'::`2'::impl
0x1800137a3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(wil::ReportingKind)
0x1800137a8  test    al, al
0x1800137aa  jz      short loc_1800137B1
0x1800137ac  mov     cl, dil
0x1800137af  jmp     short loc_1800137B3
0x1800137b1  xor     cl, cl
0x1800137b3  test    sil, sil
0x1800137b6  jz      short loc_1800137C0
0x1800137b8  test    cl, cl
0x1800137ba  jnz     short loc_1800137C0
0x1800137bc  btr     dword ptr [rbx], 0Ah
0x1800137c0  mov     eax, [rbx]
0x1800137c2  test    bpl, al
0x1800137c5  jz      short loc_1800137CB
0x1800137c7  test    cl, cl
0x1800137c9  jnz     short loc_1800137CD
0x1800137cb  xor     edi, edi
0x1800137cd  and     eax, 0FFFFFFFEh
0x1800137d0  or      eax, edi
0x1800137d2  mov     [rbx], eax
0x1800137d4  mov     rax, rbx
0x1800137d7  add     rsp, 28h
0x1800137db  pop     rdi
0x1800137dc  pop     rsi
0x1800137dd  pop     rbp
0x1800137de  pop     rbx
0x1800137df  retn
```
