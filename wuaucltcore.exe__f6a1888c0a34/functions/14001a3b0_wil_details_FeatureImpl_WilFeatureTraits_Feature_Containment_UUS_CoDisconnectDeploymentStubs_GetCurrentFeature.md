# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs>::GetCurrentFeatureEnabledState(int *)

- ea: `0x14001a3b0`
- end: `0x14001a4c5`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `277`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14001a220`

## callees

- `0x140014800`
- `0x14001a3b0`
- `0x1400206e0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs>::GetCurrentFeatureEnabledState(
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
  v4 = v2(54448981, 3);
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
0x14001a3b0  mov     [rsp+arg_0], rbx
0x14001a3b5  mov     [rsp+arg_8], rbp
0x14001a3ba  mov     [rsp+arg_10], rsi
0x14001a3bf  push    rdi
0x14001a3c0  sub     rsp, 20h
0x14001a3c4  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x14001a3cb  mov     rbx, rdx
0x14001a3ce  test    rax, rax
0x14001a3d1  jnz     short loc_14001A3DF
0x14001a3d3  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x14001a3da  test    rax, rax
0x14001a3dd  jz      short loc_14001A431
0x14001a3df  mov     edx, 3
0x14001a3e4  mov     ecx, 33ED355h
0x14001a3e9  call    _guard_dispatch_icall
0x14001a3ee  mov     r8d, eax
0x14001a3f1  mov     qword ptr [rbx], 0
0x14001a3f8  and     r8d, 0FFFFFF3Fh
0x14001a3ff  mov     edx, eax
0x14001a401  and     edx, 80h
0x14001a407  mov     ecx, r8d
0x14001a40a  and     ecx, 3
0x14001a40d  mov     edi, 40h ; '@'
0x14001a412  shl     ecx, 2
0x14001a415  and     eax, edi
0x14001a417  or      ecx, eax
0x14001a419  shl     ecx, 2
0x14001a41c  or      ecx, edx
0x14001a41e  shl     ecx, 3
0x14001a421  test    r8d, r8d
0x14001a424  jz      short loc_14001A458
0x14001a426  xor     eax, eax
0x14001a428  cmp     r8d, 2
0x14001a42c  cmovz   eax, edi
0x14001a42f  jmp     short loc_14001A45A
0x14001a431  xor     ecx, ecx
0x14001a433  mov     qword ptr [rdx], 0
0x14001a43a  xor     eax, eax
0x14001a43c  and     ecx, 3
0x14001a43f  shl     ecx, 2
0x14001a442  lea     edi, [rax+40h]
0x14001a445  and     eax, edi
0x14001a447  or      ecx, eax
0x14001a449  xor     eax, eax
0x14001a44b  and     eax, 80h
0x14001a450  shl     ecx, 2
0x14001a453  or      ecx, eax
0x14001a455  shl     ecx, 3
0x14001a458  mov     eax, edi
0x14001a45a  or      ecx, eax
0x14001a45c  mov     esi, 1
0x14001a461  xor     al, al
0x14001a463  mov     [rbx], ecx
0x14001a465  bt      ecx, 0Ah
0x14001a469  jnb     short loc_14001A478
0x14001a46b  cmp     ecx, 800h
0x14001a471  jb      short loc_14001A478
0x14001a473  mov     bpl, sil
0x14001a476  jmp     short loc_14001A480
0x14001a478  xor     bpl, bpl
0x14001a47b  test    dil, cl
0x14001a47e  jz      short loc_14001A499
0x14001a480  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilExternalFeatureTraits_Feature_UxAccOptimization@@@wil@@CAAEAV?$FeatureImpl@U__WilExternalFeatureTraits_Feature_UxAccOptimization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilExternalFeatureTraits_Feature_UxAccOptimization> `wil::Feature<__WilExternalFeatureTraits_Feature_UxAccOptimization>::GetImpl(void)'::`2'::impl
0x14001a487  call    ?__private_IsEnabled@?$FeatureImpl@U__WilExternalFeatureTraits_Feature_UxAccOptimization@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilExternalFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(wil::ReportingKind)
0x14001a48c  test    bpl, bpl
0x14001a48f  jz      short loc_14001A499
0x14001a491  test    al, al
0x14001a493  jnz     short loc_14001A499
0x14001a495  btr     dword ptr [rbx], 0Ah
0x14001a499  mov     ecx, [rbx]
0x14001a49b  test    dil, cl
0x14001a49e  jz      short loc_14001A4A4
0x14001a4a0  test    al, al
0x14001a4a2  jnz     short loc_14001A4A6
0x14001a4a4  xor     esi, esi
0x14001a4a6  mov     rbp, [rsp+28h+arg_8]
0x14001a4ab  and     ecx, 0FFFFFFFEh
0x14001a4ae  or      ecx, esi
0x14001a4b0  mov     rax, rbx
0x14001a4b3  mov     rsi, [rsp+28h+arg_10]
0x14001a4b8  mov     [rbx], ecx
0x14001a4ba  mov     rbx, [rsp+28h+arg_0]
0x14001a4bf  add     rsp, 20h
0x14001a4c3  pop     rdi
0x14001a4c4  retn
```
