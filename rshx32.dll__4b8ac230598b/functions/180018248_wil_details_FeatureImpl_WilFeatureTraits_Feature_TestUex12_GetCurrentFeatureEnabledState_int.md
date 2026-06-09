# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180018248`
- end: `0x1800183b1`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestUex12@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800179d8`

## callees

- `0x1800175c4`
- `0x180018248`
- `0x180018ac8`
- `0x1800191f0`
- `0x18001e010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::GetCurrentFeatureEnabledState(
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
    v4 = v2(58989070, 3);
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_UexTest7>::GetImpl'::`2'::impl,
                          v7) )
  {
    v14 = *(_DWORD *)Feature_Standalone_26_04_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_26_04_NonSec__descriptor & 4) == 0 )
    {
      v17 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_04_NonSec>::GetCachedFeatureEnabledState(
               v13,
               &v17);
      v14 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(&qword_1800295F8, 58599559, (v14 >> 10) & 1, (v14 >> 11) & 1, &v16, 1, 0);
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
0x180018248  mov     [rsp+arg_10], rbx
0x18001824d  mov     [rsp+arg_0], rcx
0x180018252  push    rbp
0x180018253  push    rsi
0x180018254  push    rdi
0x180018255  sub     rsp, 40h
0x180018259  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180018260  mov     rbx, rdx
0x180018263  test    rax, rax
0x180018266  jz      short loc_18001827B
0x180018268  mov     edx, 3
0x18001826d  mov     ecx, 3841A0Eh
0x180018272  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018277  mov     edx, eax
0x180018279  jmp     short loc_180018289
0x18001827b  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180018282  test    rax, rax
0x180018285  jnz     short loc_180018268
0x180018287  xor     edx, edx
0x180018289  mov     r8d, edx
0x18001828c  mov     qword ptr [rbx], 0
0x180018293  and     r8d, 0FFFFFF3Fh
0x18001829a  mov     eax, edx
0x18001829c  and     edx, 80h
0x1800182a2  mov     ecx, r8d
0x1800182a5  and     ecx, 3
0x1800182a8  mov     ebp, 40h ; '@'
0x1800182ad  shl     ecx, 2
0x1800182b0  and     eax, ebp
0x1800182b2  or      ecx, eax
0x1800182b4  shl     ecx, 2
0x1800182b7  or      ecx, edx
0x1800182b9  shl     ecx, 3
0x1800182bc  test    r8d, r8d
0x1800182bf  jnz     short loc_1800182C8
0x1800182c1  mov     edx, ebp
0x1800182c3  mov     r8d, ebp
0x1800182c6  jmp     short loc_1800182D4
0x1800182c8  xor     edx, edx
0x1800182ca  cmp     r8d, 2
0x1800182ce  cmovz   edx, ebp
0x1800182d1  mov     r8d, edx
0x1800182d4  mov     eax, ecx
0x1800182d6  mov     edi, 1
0x1800182db  or      eax, r8d
0x1800182de  or      ecx, edx
0x1800182e0  mov     [rbx], eax
0x1800182e2  bt      ecx, 0Ah
0x1800182e6  jnb     short loc_1800182F5
0x1800182e8  cmp     ecx, 800h
0x1800182ee  jb      short loc_1800182F5
0x1800182f0  mov     sil, dil
0x1800182f3  jmp     short loc_180018303
0x1800182f5  xor     sil, sil
0x1800182f8  xor     dl, dl
0x1800182fa  test    bpl, cl
0x1800182fd  jz      loc_18001838D
0x180018303  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UexTest7@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7> `wil::Feature<__WilFeatureTraits_Feature_UexTest7>::GetImpl(void)'::`2'::impl
0x18001830a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::__private_IsEnabled(wil::ReportingKind)
0x18001830f  test    al, al
0x180018311  jz      short loc_18001837E
0x180018313  mov     rax, cs:Feature_Standalone_26_04_NonSec__descriptor
0x18001831a  mov     r8d, [rax]
0x18001831d  test    r8b, 4
0x180018321  jnz     short loc_180018338
0x180018323  lea     rdx, [rsp+58h+arg_8]
0x180018328  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_04_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_04_NonSec>::GetCachedFeatureEnabledState(void)
0x18001832d  mov     rcx, [rax]
0x180018330  mov     [rsp+58h+arg_8], rcx
0x180018335  mov     r8d, ecx
0x180018338  xor     eax, eax
0x18001833a  mov     word ptr [rsp+58h+arg_0+4], 3
0x180018341  mov     r9d, r8d
0x180018344  mov     [rsp+58h+var_28], eax
0x180018348  mov     dword ptr [rsp+58h+arg_0], eax
0x18001834c  lea     rcx, qword_1800295F8
0x180018353  shr     r9d, 0Bh
0x180018357  lea     rax, [rsp+58h+arg_0]
0x18001835c  shr     r8d, 0Ah
0x180018360  and     r9d, edi
0x180018363  and     r8d, edi
0x180018366  mov     [rsp+58h+var_30], edi
0x18001836a  mov     edx, 37E2887h
0x18001836f  mov     [rsp+58h+var_38], rax
0x180018374  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180018379  mov     dl, dil
0x18001837c  jmp     short loc_180018380
0x18001837e  xor     dl, dl
0x180018380  test    sil, sil
0x180018383  jz      short loc_18001838D
0x180018385  test    dl, dl
0x180018387  jnz     short loc_18001838D
0x180018389  btr     dword ptr [rbx], 0Ah
0x18001838d  mov     eax, [rbx]
0x18001838f  test    bpl, al
0x180018392  jz      short loc_180018398
0x180018394  test    dl, dl
0x180018396  jnz     short loc_18001839A
0x180018398  xor     edi, edi
0x18001839a  and     eax, 0FFFFFFFEh
0x18001839d  or      eax, edi
0x18001839f  mov     [rbx], eax
0x1800183a1  mov     rax, rbx
0x1800183a4  mov     rbx, [rsp+58h+arg_10]
0x1800183a9  add     rsp, 40h
0x1800183ad  pop     rdi
0x1800183ae  pop     rsi
0x1800183af  pop     rbp
0x1800183b0  retn
```
