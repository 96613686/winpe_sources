# wil::details::FeatureImpl<__WilFeatureTraits_Feature_51718004>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001359c`
- end: `0x1800136de`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_51718004@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `322`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800121f0`

## callees

- `0x18000a358`
- `0x180012c80`
- `0x18001359c`
- `0x18001b010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_51718004>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // edx
  unsigned int v5; // r8d
  int v6; // ecx
  int v7; // edx
  int v8; // r8d
  int v9; // edi
  int v10; // eax
  wil::details *v11; // rcx
  char v12; // dl
  unsigned int v13; // r8d
  __int64 v15; // [rsp+50h] [rbp+8h] BYREF
  __int64 v16; // [rsp+58h] [rbp+10h] BYREF

  v15 = a1;
  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(51718004, 3);
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
  v11 = (wil::details *)(v7 | (unsigned int)v6);
  *(_DWORD *)a2 = v10;
  if ( ((unsigned __int16)v11 & 0x400) != 0 && (unsigned int)v11 >= 0x800
    || (v12 = 0, ((unsigned __int8)v11 & 0x40) != 0) )
  {
    v13 = *(_DWORD *)Feature_ID56699092__descriptor;
    if ( (*(_DWORD *)Feature_ID56699092__descriptor & 4) == 0 )
    {
      v16 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56699092>::GetCachedFeatureEnabledState(v11, &v16);
      v13 = v16;
    }
    WORD2(v15) = 3;
    LODWORD(v15) = 0;
    wil::details::ReportUsageToService(
      (__int64)&qword_180023968,
      0x36128D4u,
      (v13 >> 10) & 1,
      (v13 >> 11) & 1,
      (__int64)&v15,
      1u,
      0);
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
0x18001359c  mov     [rsp+arg_10], rbx
0x1800135a1  mov     [rsp+arg_18], rsi
0x1800135a6  mov     [rsp+arg_0], rcx
0x1800135ab  push    rdi
0x1800135ac  sub     rsp, 40h
0x1800135b0  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800135b7  mov     rbx, rdx
0x1800135ba  test    rax, rax
0x1800135bd  jz      short loc_1800135D2
0x1800135bf  mov     edx, 3
0x1800135c4  mov     ecx, 3152774h
0x1800135c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800135ce  mov     edx, eax
0x1800135d0  jmp     short loc_1800135E0
0x1800135d2  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1800135d9  test    rax, rax
0x1800135dc  jnz     short loc_1800135BF
0x1800135de  xor     edx, edx
0x1800135e0  mov     r8d, edx
0x1800135e3  mov     qword ptr [rbx], 0
0x1800135ea  and     r8d, 0FFFFFF3Fh
0x1800135f1  mov     eax, edx
0x1800135f3  and     edx, 80h
0x1800135f9  mov     ecx, r8d
0x1800135fc  and     ecx, 3
0x1800135ff  mov     esi, 40h ; '@'
0x180013604  shl     ecx, 2
0x180013607  and     eax, esi
0x180013609  or      ecx, eax
0x18001360b  shl     ecx, 2
0x18001360e  or      ecx, edx
0x180013610  shl     ecx, 3
0x180013613  test    r8d, r8d
0x180013616  jnz     short loc_18001361F
0x180013618  mov     edx, esi
0x18001361a  mov     r8d, esi
0x18001361d  jmp     short loc_18001362B
0x18001361f  xor     edx, edx
0x180013621  cmp     r8d, 2
0x180013625  cmovz   edx, esi
0x180013628  mov     r8d, edx
0x18001362b  mov     eax, ecx
0x18001362d  mov     edi, 1
0x180013632  or      eax, r8d
0x180013635  or      ecx, edx
0x180013637  mov     [rbx], eax
0x180013639  bt      ecx, 0Ah
0x18001363d  jnb     short loc_180013647
0x18001363f  cmp     ecx, 800h
0x180013645  jnb     short loc_18001364E
0x180013647  xor     dl, dl
0x180013649  test    sil, cl
0x18001364c  jz      short loc_1800136B7
0x18001364e  mov     rax, cs:Feature_ID56699092__descriptor
0x180013655  mov     r8d, [rax]
0x180013658  test    r8b, 4
0x18001365c  jnz     short loc_180013673
0x18001365e  lea     rdx, [rsp+48h+arg_8]
0x180013663  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ID56699092@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56699092>::GetCachedFeatureEnabledState(void)
0x180013668  mov     rcx, [rax]
0x18001366b  mov     [rsp+48h+arg_8], rcx
0x180013670  mov     r8d, ecx
0x180013673  xor     eax, eax
0x180013675  mov     word ptr [rsp+48h+arg_0+4], 3
0x18001367c  mov     r9d, r8d
0x18001367f  mov     [rsp+48h+var_18], eax
0x180013683  mov     dword ptr [rsp+48h+arg_0], eax
0x180013687  lea     rcx, qword_180023968
0x18001368e  shr     r9d, 0Bh
0x180013692  lea     rax, [rsp+48h+arg_0]
0x180013697  shr     r8d, 0Ah
0x18001369b  and     r9d, edi
0x18001369e  and     r8d, edi
0x1800136a1  mov     [rsp+48h+var_20], edi
0x1800136a5  mov     edx, 36128D4h
0x1800136aa  mov     [rsp+48h+var_28], rax
0x1800136af  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x1800136b4  mov     dl, dil
0x1800136b7  mov     eax, [rbx]
0x1800136b9  test    sil, al
0x1800136bc  jz      short loc_1800136C2
0x1800136be  test    dl, dl
0x1800136c0  jnz     short loc_1800136C4
0x1800136c2  xor     edi, edi
0x1800136c4  mov     rsi, [rsp+48h+arg_18]
0x1800136c9  and     eax, 0FFFFFFFEh
0x1800136cc  or      eax, edi
0x1800136ce  mov     [rbx], eax
0x1800136d0  mov     rax, rbx
0x1800136d3  mov     rbx, [rsp+48h+arg_10]
0x1800136d8  add     rsp, 40h
0x1800136dc  pop     rdi
0x1800136dd  retn
```
