# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope>::GetCurrentFeatureEnabledState(int *)

- ea: `0x1800028c0`
- end: `0x1800029d5`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Calliope@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `277`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800029dc`

## callees

- `0x180002884`
- `0x1800028c0`
- `0x1800148e0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // eax
  unsigned int v5; // r8d
  int v6; // ecx
  int v7; // eax
  unsigned int v8; // ecx
  int v9; // esi
  char IsEnabled; // al
  char v11; // bp
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
  v4 = v2(56757185, 3);
  *a2 = 0;
  v5 = v4 & 0xFFFFFF3F;
  v6 = 8 * (v4 & 0x80 | (4 * (v4 & 0x40 | (4 * (v4 & 3)))));
  if ( (v4 & 0xFFFFFF3F) == 0 )
  {
LABEL_8:
    v7 = 64;
    goto LABEL_9;
  }
  v7 = 0;
  if ( v5 == 2 )
    v7 = 64;
LABEL_9:
  v8 = v7 | v6;
  v9 = 1;
  IsEnabled = 0;
  *(_DWORD *)a2 = v8;
  if ( (v8 & 0x400) != 0 && v8 >= 0x800 )
  {
    v11 = 1;
  }
  else
  {
    v11 = 0;
    if ( (v8 & 0x40) == 0 )
      goto LABEL_16;
  }
  IsEnabled = wil::details::FeatureImpl<__WilExternalFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(`wil::Feature<__WilExternalFeatureTraits_Feature_UxAccOptimization>::GetImpl'::`2'::impl);
  if ( v11 && !IsEnabled )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_16:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !IsEnabled )
    v9 = 0;
  result = a2;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return result;
}

```

## disassembly

```asm
0x1800028c0  mov     [rsp+arg_0], rbx
0x1800028c5  mov     [rsp+arg_8], rbp
0x1800028ca  mov     [rsp+arg_10], rsi
0x1800028cf  push    rdi
0x1800028d0  sub     rsp, 20h
0x1800028d4  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800028db  mov     rbx, rdx
0x1800028de  test    rax, rax
0x1800028e1  jnz     short loc_1800028EF
0x1800028e3  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1800028ea  test    rax, rax
0x1800028ed  jz      short loc_180002941
0x1800028ef  mov     edx, 3
0x1800028f4  mov     ecx, 3620BC1h
0x1800028f9  call    _guard_dispatch_icall
0x1800028fe  mov     r8d, eax
0x180002901  mov     qword ptr [rbx], 0
0x180002908  and     r8d, 0FFFFFF3Fh
0x18000290f  mov     edx, eax
0x180002911  and     edx, 80h
0x180002917  mov     ecx, r8d
0x18000291a  and     ecx, 3
0x18000291d  mov     edi, 40h ; '@'
0x180002922  shl     ecx, 2
0x180002925  and     eax, edi
0x180002927  or      ecx, eax
0x180002929  shl     ecx, 2
0x18000292c  or      ecx, edx
0x18000292e  shl     ecx, 3
0x180002931  test    r8d, r8d
0x180002934  jz      short loc_180002968
0x180002936  xor     eax, eax
0x180002938  cmp     r8d, 2
0x18000293c  cmovz   eax, edi
0x18000293f  jmp     short loc_18000296A
0x180002941  xor     ecx, ecx
0x180002943  mov     qword ptr [rdx], 0
0x18000294a  xor     eax, eax
0x18000294c  and     ecx, 3
0x18000294f  shl     ecx, 2
0x180002952  lea     edi, [rax+40h]
0x180002955  and     eax, edi
0x180002957  or      ecx, eax
0x180002959  xor     eax, eax
0x18000295b  and     eax, 80h
0x180002960  shl     ecx, 2
0x180002963  or      ecx, eax
0x180002965  shl     ecx, 3
0x180002968  mov     eax, edi
0x18000296a  or      ecx, eax
0x18000296c  mov     esi, 1
0x180002971  xor     al, al
0x180002973  mov     [rbx], ecx
0x180002975  bt      ecx, 0Ah
0x180002979  jnb     short loc_180002988
0x18000297b  cmp     ecx, 800h
0x180002981  jb      short loc_180002988
0x180002983  mov     bpl, sil
0x180002986  jmp     short loc_180002990
0x180002988  xor     bpl, bpl
0x18000298b  test    dil, cl
0x18000298e  jz      short loc_1800029A9
0x180002990  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilExternalFeatureTraits_Feature_UxAccOptimization@@@wil@@CAAEAV?$FeatureImpl@U__WilExternalFeatureTraits_Feature_UxAccOptimization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilExternalFeatureTraits_Feature_UxAccOptimization> `wil::Feature<__WilExternalFeatureTraits_Feature_UxAccOptimization>::GetImpl(void)'::`2'::impl
0x180002997  call    ?__private_IsEnabled@?$FeatureImpl@U__WilExternalFeatureTraits_Feature_UxAccOptimization@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilExternalFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(wil::ReportingKind)
0x18000299c  test    bpl, bpl
0x18000299f  jz      short loc_1800029A9
0x1800029a1  test    al, al
0x1800029a3  jnz     short loc_1800029A9
0x1800029a5  btr     dword ptr [rbx], 0Ah
0x1800029a9  mov     ecx, [rbx]
0x1800029ab  test    dil, cl
0x1800029ae  jz      short loc_1800029B4
0x1800029b0  test    al, al
0x1800029b2  jnz     short loc_1800029B6
0x1800029b4  xor     esi, esi
0x1800029b6  mov     rbp, [rsp+28h+arg_8]
0x1800029bb  and     ecx, 0FFFFFFFEh
0x1800029be  or      ecx, esi
0x1800029c0  mov     rax, rbx
0x1800029c3  mov     rsi, [rsp+28h+arg_10]
0x1800029c8  mov     [rbx], ecx
0x1800029ca  mov     rbx, [rsp+28h+arg_0]
0x1800029cf  add     rsp, 20h
0x1800029d3  pop     rdi
0x1800029d4  retn
```
