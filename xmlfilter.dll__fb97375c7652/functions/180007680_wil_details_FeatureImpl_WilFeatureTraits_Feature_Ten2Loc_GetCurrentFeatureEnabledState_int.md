# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180007680`
- end: `0x1800077e9`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180006dec`

## callees

- `0x180006b04`
- `0x180007680`
- `0x18000b2e0`
- `0x18000d4cc`
- `0x180017010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(
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
    v4 = v2(58989002, 3);
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl'::`2'::impl,
                          v7) )
  {
    v14 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor & 4) == 0 )
    {
      v17 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(
               v13,
               &v17);
      v14 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(&qword_180021898, 58599550, (v14 >> 10) & 1, (v14 >> 11) & 1, &v16, 1, 0);
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
0x180007680  mov     [rsp+arg_10], rbx
0x180007685  mov     [rsp+arg_0], rcx
0x18000768a  push    rbp
0x18000768b  push    rsi
0x18000768c  push    rdi
0x18000768d  sub     rsp, 40h
0x180007691  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180007698  mov     rbx, rdx
0x18000769b  test    rax, rax
0x18000769e  jz      short loc_1800076B3
0x1800076a0  mov     edx, 3
0x1800076a5  mov     ecx, 38419CAh
0x1800076aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076af  mov     edx, eax
0x1800076b1  jmp     short loc_1800076C1
0x1800076b3  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1800076ba  test    rax, rax
0x1800076bd  jnz     short loc_1800076A0
0x1800076bf  xor     edx, edx
0x1800076c1  mov     r8d, edx
0x1800076c4  mov     qword ptr [rbx], 0
0x1800076cb  and     r8d, 0FFFFFF3Fh
0x1800076d2  mov     eax, edx
0x1800076d4  and     edx, 80h
0x1800076da  mov     ecx, r8d
0x1800076dd  and     ecx, 3
0x1800076e0  mov     ebp, 40h ; '@'
0x1800076e5  shl     ecx, 2
0x1800076e8  and     eax, ebp
0x1800076ea  or      ecx, eax
0x1800076ec  shl     ecx, 2
0x1800076ef  or      ecx, edx
0x1800076f1  shl     ecx, 3
0x1800076f4  test    r8d, r8d
0x1800076f7  jnz     short loc_180007700
0x1800076f9  mov     edx, ebp
0x1800076fb  mov     r8d, ebp
0x1800076fe  jmp     short loc_18000770C
0x180007700  xor     edx, edx
0x180007702  cmp     r8d, 2
0x180007706  cmovz   edx, ebp
0x180007709  mov     r8d, edx
0x18000770c  mov     eax, ecx
0x18000770e  mov     edi, 1
0x180007713  or      eax, r8d
0x180007716  or      ecx, edx
0x180007718  mov     [rbx], eax
0x18000771a  bt      ecx, 0Ah
0x18000771e  jnb     short loc_18000772D
0x180007720  cmp     ecx, 800h
0x180007726  jb      short loc_18000772D
0x180007728  mov     sil, dil
0x18000772b  jmp     short loc_18000773B
0x18000772d  xor     sil, sil
0x180007730  xor     dl, dl
0x180007732  test    bpl, cl
0x180007735  jz      loc_1800077C5
0x18000773b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestLoc1Perf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf> `wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl(void)'::`2'::impl
0x180007742  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(wil::ReportingKind)
0x180007747  test    al, al
0x180007749  jz      short loc_1800077B6
0x18000774b  mov     rax, cs:Feature_Standalone_26_02_NonSec__descriptor
0x180007752  mov     r8d, [rax]
0x180007755  test    r8b, 4
0x180007759  jnz     short loc_180007770
0x18000775b  lea     rdx, [rsp+58h+arg_8]
0x180007760  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)
0x180007765  mov     rcx, [rax]
0x180007768  mov     [rsp+58h+arg_8], rcx
0x18000776d  mov     r8d, ecx
0x180007770  xor     eax, eax
0x180007772  mov     word ptr [rsp+58h+arg_0+4], 3
0x180007779  mov     r9d, r8d
0x18000777c  mov     [rsp+58h+var_28], eax
0x180007780  mov     dword ptr [rsp+58h+arg_0], eax
0x180007784  lea     rcx, qword_180021898
0x18000778b  shr     r9d, 0Bh
0x18000778f  lea     rax, [rsp+58h+arg_0]
0x180007794  shr     r8d, 0Ah
0x180007798  and     r9d, edi
0x18000779b  and     r8d, edi
0x18000779e  mov     [rsp+58h+var_30], edi
0x1800077a2  mov     edx, 37E287Eh
0x1800077a7  mov     [rsp+58h+var_38], rax
0x1800077ac  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x1800077b1  mov     dl, dil
0x1800077b4  jmp     short loc_1800077B8
0x1800077b6  xor     dl, dl
0x1800077b8  test    sil, sil
0x1800077bb  jz      short loc_1800077C5
0x1800077bd  test    dl, dl
0x1800077bf  jnz     short loc_1800077C5
0x1800077c1  btr     dword ptr [rbx], 0Ah
0x1800077c5  mov     eax, [rbx]
0x1800077c7  test    bpl, al
0x1800077ca  jz      short loc_1800077D0
0x1800077cc  test    dl, dl
0x1800077ce  jnz     short loc_1800077D2
0x1800077d0  xor     edi, edi
0x1800077d2  and     eax, 0FFFFFFFEh
0x1800077d5  or      eax, edi
0x1800077d7  mov     [rbx], eax
0x1800077d9  mov     rax, rbx
0x1800077dc  mov     rbx, [rsp+58h+arg_10]
0x1800077e1  add     rsp, 40h
0x1800077e5  pop     rdi
0x1800077e6  pop     rsi
0x1800077e7  pop     rbp
0x1800077e8  retn
```
