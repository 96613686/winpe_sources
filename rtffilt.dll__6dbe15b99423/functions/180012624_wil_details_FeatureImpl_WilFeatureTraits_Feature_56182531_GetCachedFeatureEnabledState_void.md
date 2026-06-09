# wil::details::FeatureImpl<__WilFeatureTraits_Feature_56182531>::GetCachedFeatureEnabledState(void)

- ea: `0x180012624`
- end: `0x1800127f1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_56182531@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015484`

## callees

- `0x180005dd8`
- `0x18000b3d8`
- `0x180012624`
- `0x18001522c`
- `0x18001b010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_56182531>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
  __int64 (__fastcall *v5)(__int64, __int64, wil::details **); // rax
  int v6; // edx
  int v7; // eax
  int v8; // ebx
  char v9; // si
  char IsEnabled; // al
  BOOL v11; // esi
  signed __int32 v12; // eax
  int v13; // esi
  bool v14; // zf
  signed __int32 v15; // edx
  int v16; // r8d
  int v17; // r9d
  signed __int32 v18; // ecx
  wil::details *v20; // [rsp+60h] [rbp+8h] BYREF

  v20 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_56182531__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_56182531__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(56182531, 3, &v20);
  }
  else
  {
    v6 = 0;
  }
  if ( (v6 & 0xFFFFFF3F) != 0 )
  {
    v7 = 0;
    if ( (v6 & 0xFFFFFF3F) == 2 )
      v7 = 64;
  }
  else
  {
    v7 = 64;
  }
  v8 = v7 | (8 * (v6 & 0x80 | (4 * (v6 & 0x40 | (4 * (v6 & 3))))));
  if ( (v8 & 0xC00) == 0xC00 )
  {
    v9 = 1;
LABEL_13:
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_49093927>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_49093927>::GetImpl'::`2'::impl);
    if ( v9 && !IsEnabled )
      v8 &= ~0x400u;
    goto LABEL_17;
  }
  v9 = 0;
  if ( (v8 & 0x40) != 0 )
    goto LABEL_13;
  IsEnabled = 0;
LABEL_17:
  v11 = (v8 & 0x40) != 0 && IsEnabled;
  v12 = *(_DWORD *)a2;
  v13 = v8 | v11;
  do
  {
    v14 = (_DWORD)v20 == 0;
    v15 = v12;
    *(_DWORD *)a2 = v12;
    if ( v14 || (v12 & 2) != 0 )
    {
      v16 = v12;
    }
    else
    {
      v16 = v12
          ^ (v12
           ^ v13)
          & 0x180
          ^ (v13
           ^ v12
           ^ (v12
            ^ v13)
           & 0x180)
          & 0x40
          ^ ((unsigned __int8)v13
           ^ (unsigned __int8)(v12 ^ (v12 ^ v13) & 0x80 ^ (v13 ^ v12 ^ (v12 ^ v13) & 0x80) & 0x40))
          & 1
          ^ ((unsigned __int16)v13
           ^ (unsigned __int16)(v12
                              ^ (v12
                               ^ v13)
                              & 0x180
                              ^ (v13
                               ^ v12
                               ^ (v12
                                ^ v13)
                               & 0x180)
                              & 0x40
                              ^ ((unsigned __int8)v13
                               ^ (unsigned __int8)(v12 ^ (v12 ^ v13) & 0x80 ^ (v13 ^ v12 ^ (v12 ^ v13) & 0x80) & 0x40))
                              & 1))
          & 0x800
          | 2;
      *(_DWORD *)a2 = v16;
    }
    v17 = v12 & 4;
    if ( (v12 & 4) != 0 )
    {
      v18 = v16;
    }
    else
    {
      v18 = v16 ^ ((unsigned __int16)v16 ^ (unsigned __int16)v13) & 0x400 | 4;
      *(_DWORD *)a2 = v18;
    }
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_56182531__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
      (volatile signed __int32 *)Feature_56182531__descriptor,
      3u,
      v4);
  if ( (*(_BYTE *)a2 & 2) == 0 )
    *(_DWORD *)a2 ^= (v13
                    ^ *(_DWORD *)a2)
                   & 0x180
                   ^ (v13
                    ^ *(_DWORD *)a2
                    ^ (v13
                     ^ *(_DWORD *)a2)
                    & 0x180)
                   & 0x40
                   ^ ((unsigned __int8)v13
                    ^ *(_BYTE *)a2
                    ^ ((unsigned __int8)v13
                     ^ *(_BYTE *)a2)
                    & 0x80
                    ^ ((unsigned __int8)v13
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v13
                      ^ *(_BYTE *)a2)
                     & 0x80)
                    & 0x40)
                   & 1
                   ^ ((unsigned __int16)v13
                    ^ *(_WORD *)a2
                    ^ ((unsigned __int16)v13
                     ^ *(_WORD *)a2)
                    & 0x180
                    ^ ((unsigned __int16)v13
                     ^ *(_WORD *)a2
                     ^ ((unsigned __int16)v13
                      ^ *(_WORD *)a2)
                     & 0x180)
                    & 0x40
                    ^ ((unsigned __int8)v13
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v13
                      ^ *(_BYTE *)a2)
                     & 0x80
                     ^ ((unsigned __int8)v13
                      ^ *(_BYTE *)a2
                      ^ ((unsigned __int8)v13
                       ^ *(_BYTE *)a2)
                      & 0x80)
                     & 0x40)
                    & 1)
                   & 0x800;
  return a2;
}

```

## disassembly

```asm
0x180012624  mov     [rsp+arg_0], rcx
0x180012629  push    rbx
0x18001262a  push    rbp
0x18001262b  push    rsi
0x18001262c  push    rdi
0x18001262d  push    r12
0x18001262f  push    r14
0x180012631  sub     rsp, 28h
0x180012635  mov     r14, cs:Feature_56182531__descriptor
0x18001263c  mov     rdi, rdx
0x18001263f  mov     qword ptr [rdx], 0
0x180012646  mov     eax, [r14]
0x180012649  mov     [rdx], eax
0x18001264b  and     eax, 6
0x18001264e  cmp     al, 6
0x180012650  jz      loc_1800127E1
0x180012656  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001265b  mov     ebp, eax
0x18001265d  mov     dword ptr [rsp+58h+arg_0], 0
0x180012665  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001266c  test    rax, rax
0x18001266f  jz      short loc_180012689
0x180012671  lea     r8, [rsp+58h+arg_0]
0x180012676  mov     edx, 3
0x18001267b  mov     ecx, 3594703h
0x180012680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012685  mov     edx, eax
0x180012687  jmp     short loc_180012697
0x180012689  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180012690  test    rax, rax
0x180012693  jnz     short loc_180012671
0x180012695  xor     edx, edx
0x180012697  mov     r8d, edx
0x18001269a  mov     eax, edx
0x18001269c  and     r8d, 0FFFFFF3Fh
0x1800126a3  and     edx, 80h
0x1800126a9  mov     ecx, r8d
0x1800126ac  mov     r12d, 40h ; '@'
0x1800126b2  and     ecx, 3
0x1800126b5  and     eax, r12d
0x1800126b8  shl     ecx, 2
0x1800126bb  or      ecx, eax
0x1800126bd  shl     ecx, 2
0x1800126c0  or      ecx, edx
0x1800126c2  lea     ebx, ds:0[rcx*8]
0x1800126c9  test    r8d, r8d
0x1800126cc  jnz     short loc_1800126D3
0x1800126ce  mov     eax, r12d
0x1800126d1  jmp     short loc_1800126DD
0x1800126d3  xor     eax, eax
0x1800126d5  cmp     r8d, 2
0x1800126d9  cmovz   eax, r12d
0x1800126dd  or      ebx, eax
0x1800126df  mov     ecx, 0C00h
0x1800126e4  mov     eax, ebx
0x1800126e6  and     eax, ecx
0x1800126e8  cmp     eax, ecx
0x1800126ea  jnz     short loc_1800126F1
0x1800126ec  mov     sil, 1
0x1800126ef  jmp     short loc_1800126F9
0x1800126f1  xor     sil, sil
0x1800126f4  test    r12b, bl
0x1800126f7  jz      short loc_180012714
0x1800126f9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_49093927@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_49093927@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_49093927> `wil::Feature<__WilFeatureTraits_Feature_49093927>::GetImpl(void)'::`2'::impl
0x180012700  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_49093927@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_49093927>::__private_IsEnabled(wil::ReportingKind)
0x180012705  test    sil, sil
0x180012708  jz      short loc_180012716
0x18001270a  test    al, al
0x18001270c  jnz     short loc_180012716
0x18001270e  btr     ebx, 0Ah
0x180012712  jmp     short loc_180012716
0x180012714  xor     al, al
0x180012716  test    r12b, bl
0x180012719  jz      short loc_180012726
0x18001271b  test    al, al
0x18001271d  jz      short loc_180012726
0x18001271f  mov     esi, 1
0x180012724  jmp     short loc_180012728
0x180012726  xor     esi, esi
0x180012728  mov     eax, [rdi]
0x18001272a  or      esi, ebx
0x18001272c  mov     ebx, 180h
0x180012731  cmp     dword ptr [rsp+58h+arg_0], 0
0x180012736  mov     edx, eax
0x180012738  mov     [rdi], eax
0x18001273a  jz      short loc_180012774
0x18001273c  test    dl, 2
0x18001273f  jnz     short loc_180012774
0x180012741  mov     eax, esi
0x180012743  xor     eax, edx
0x180012745  and     eax, ebx
0x180012747  xor     eax, edx
0x180012749  mov     ecx, eax
0x18001274b  xor     ecx, esi
0x18001274d  and     ecx, r12d
0x180012750  xor     ecx, eax
0x180012752  mov     eax, ecx
0x180012754  xor     eax, esi
0x180012756  and     eax, 1
0x180012759  xor     eax, ecx
0x18001275b  mov     r8d, eax
0x18001275e  xor     r8d, esi
0x180012761  and     r8d, 800h
0x180012768  xor     r8d, eax
0x18001276b  or      r8d, 2
0x18001276f  mov     [rdi], r8d
0x180012772  jmp     short loc_180012777
0x180012774  mov     r8d, edx
0x180012777  mov     r9d, edx
0x18001277a  and     r9d, 4
0x18001277e  jnz     short loc_180012795
0x180012780  mov     ecx, esi
0x180012782  xor     ecx, r8d
0x180012785  and     ecx, 400h
0x18001278b  xor     ecx, r8d
0x18001278e  or      ecx, 4
0x180012791  mov     [rdi], ecx
0x180012793  jmp     short loc_180012798
0x180012795  mov     ecx, r8d
0x180012798  mov     eax, edx
0x18001279a  lock cmpxchg [r14], ecx
0x18001279f  jnz     short loc_180012731
0x1800127a1  test    r9d, r9d
0x1800127a4  jnz     short loc_1800127B5
0x1800127a6  mov     r8d, ebp
0x1800127a9  lea     edx, [r9+3]
0x1800127ad  mov     rcx, r14
0x1800127b0  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800127b5  test    byte ptr [rdi], 2
0x1800127b8  jnz     short loc_1800127E1
0x1800127ba  mov     eax, [rdi]
0x1800127bc  xor     eax, esi
0x1800127be  and     eax, ebx
0x1800127c0  xor     eax, [rdi]
0x1800127c2  mov     ecx, eax
0x1800127c4  xor     ecx, esi
0x1800127c6  and     ecx, r12d
0x1800127c9  xor     ecx, eax
0x1800127cb  mov     edx, ecx
0x1800127cd  xor     edx, esi
0x1800127cf  and     edx, 1
0x1800127d2  xor     edx, ecx
0x1800127d4  mov     eax, edx
0x1800127d6  xor     eax, esi
0x1800127d8  and     eax, 800h
0x1800127dd  xor     eax, edx
0x1800127df  mov     [rdi], eax
0x1800127e1  mov     rax, rdi
0x1800127e4  add     rsp, 28h
0x1800127e8  pop     r14
0x1800127ea  pop     r12
0x1800127ec  pop     rdi
0x1800127ed  pop     rsi
0x1800127ee  pop     rbp
0x1800127ef  pop     rbx
0x1800127f0  retn
```
