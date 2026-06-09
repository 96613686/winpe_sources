# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180017f68`
- end: `0x1800180d1`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180017818`

## callees

- `0x180016ff4`
- `0x180017f68`
- `0x180018ac8`
- `0x18001928c`
- `0x18001e010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(
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
    v4 = v2(57048237, 3);
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl'::`2'::impl,
                          v7) )
  {
    v14 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor & 4) == 0 )
    {
      v17 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(
               v13,
               &v17);
      v14 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(&qword_1800295B8, 45036797, (v14 >> 10) & 1, (v14 >> 11) & 1, &v16, 1, 0);
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
0x180017f68  mov     [rsp+arg_10], rbx
0x180017f6d  mov     [rsp+arg_0], rcx
0x180017f72  push    rbp
0x180017f73  push    rsi
0x180017f74  push    rdi
0x180017f75  sub     rsp, 40h
0x180017f79  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180017f80  mov     rbx, rdx
0x180017f83  test    rax, rax
0x180017f86  jz      short loc_180017F9B
0x180017f88  mov     edx, 3
0x180017f8d  mov     ecx, 3667CADh
0x180017f92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f97  mov     edx, eax
0x180017f99  jmp     short loc_180017FA9
0x180017f9b  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180017fa2  test    rax, rax
0x180017fa5  jnz     short loc_180017F88
0x180017fa7  xor     edx, edx
0x180017fa9  mov     r8d, edx
0x180017fac  mov     qword ptr [rbx], 0
0x180017fb3  and     r8d, 0FFFFFF3Fh
0x180017fba  mov     eax, edx
0x180017fbc  and     edx, 80h
0x180017fc2  mov     ecx, r8d
0x180017fc5  and     ecx, 3
0x180017fc8  mov     ebp, 40h ; '@'
0x180017fcd  shl     ecx, 2
0x180017fd0  and     eax, ebp
0x180017fd2  or      ecx, eax
0x180017fd4  shl     ecx, 2
0x180017fd7  or      ecx, edx
0x180017fd9  shl     ecx, 3
0x180017fdc  test    r8d, r8d
0x180017fdf  jnz     short loc_180017FE8
0x180017fe1  mov     edx, ebp
0x180017fe3  mov     r8d, ebp
0x180017fe6  jmp     short loc_180017FF4
0x180017fe8  xor     edx, edx
0x180017fea  cmp     r8d, 2
0x180017fee  cmovz   edx, ebp
0x180017ff1  mov     r8d, edx
0x180017ff4  mov     eax, ecx
0x180017ff6  mov     edi, 1
0x180017ffb  or      eax, r8d
0x180017ffe  or      ecx, edx
0x180018000  mov     [rbx], eax
0x180018002  bt      ecx, 0Ah
0x180018006  jnb     short loc_180018015
0x180018008  cmp     ecx, 800h
0x18001800e  jb      short loc_180018015
0x180018010  mov     sil, dil
0x180018013  jmp     short loc_180018023
0x180018015  xor     sil, sil
0x180018018  xor     dl, dl
0x18001801a  test    bpl, cl
0x18001801d  jz      loc_1800180AD
0x180018023  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ValAccTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest> `wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl(void)'::`2'::impl
0x18001802a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(wil::ReportingKind)
0x18001802f  test    al, al
0x180018031  jz      short loc_18001809E
0x180018033  mov     rax, cs:Feature_Standalone_25_11_NonSec__descriptor
0x18001803a  mov     r8d, [rax]
0x18001803d  test    r8b, 4
0x180018041  jnz     short loc_180018058
0x180018043  lea     rdx, [rsp+58h+arg_8]
0x180018048  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)
0x18001804d  mov     rcx, [rax]
0x180018050  mov     [rsp+58h+arg_8], rcx
0x180018055  mov     r8d, ecx
0x180018058  xor     eax, eax
0x18001805a  mov     word ptr [rsp+58h+arg_0+4], 3
0x180018061  mov     r9d, r8d
0x180018064  mov     [rsp+58h+var_28], eax
0x180018068  mov     dword ptr [rsp+58h+arg_0], eax
0x18001806c  lea     rcx, qword_1800295B8
0x180018073  shr     r9d, 0Bh
0x180018077  lea     rax, [rsp+58h+arg_0]
0x18001807c  shr     r8d, 0Ah
0x180018080  and     r9d, edi
0x180018083  and     r8d, edi
0x180018086  mov     [rsp+58h+var_30], edi
0x18001808a  mov     edx, 2AF34FDh
0x18001808f  mov     [rsp+58h+var_38], rax
0x180018094  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180018099  mov     dl, dil
0x18001809c  jmp     short loc_1800180A0
0x18001809e  xor     dl, dl
0x1800180a0  test    sil, sil
0x1800180a3  jz      short loc_1800180AD
0x1800180a5  test    dl, dl
0x1800180a7  jnz     short loc_1800180AD
0x1800180a9  btr     dword ptr [rbx], 0Ah
0x1800180ad  mov     eax, [rbx]
0x1800180af  test    bpl, al
0x1800180b2  jz      short loc_1800180B8
0x1800180b4  test    dl, dl
0x1800180b6  jnz     short loc_1800180BA
0x1800180b8  xor     edi, edi
0x1800180ba  and     eax, 0FFFFFFFEh
0x1800180bd  or      eax, edi
0x1800180bf  mov     [rbx], eax
0x1800180c1  mov     rax, rbx
0x1800180c4  mov     rbx, [rsp+58h+arg_10]
0x1800180c9  add     rsp, 40h
0x1800180cd  pop     rdi
0x1800180ce  pop     rsi
0x1800180cf  pop     rbp
0x1800180d0  retn
```
