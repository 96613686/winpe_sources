# wil::details::FeatureImpl<__WilFeatureTraits_Feature_51365605>::GetCachedFeatureEnabledState(void)

- ea: `0x18001201c`
- end: `0x1800121e9`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_51365605@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014dd0`
- `0x1800152c8`
- `0x180015308`

## callees

- `0x180005dd8`
- `0x18000b3d8`
- `0x18001201c`
- `0x18001522c`
- `0x18001b010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_51365605>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_51365605__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_51365605__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(51365605, 3, &v20);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_51365605__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
      (volatile signed __int32 *)Feature_51365605__descriptor,
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
0x18001201c  mov     [rsp+arg_0], rcx
0x180012021  push    rbx
0x180012022  push    rbp
0x180012023  push    rsi
0x180012024  push    rdi
0x180012025  push    r12
0x180012027  push    r14
0x180012029  sub     rsp, 28h
0x18001202d  mov     r14, cs:Feature_51365605__descriptor
0x180012034  mov     rdi, rdx
0x180012037  mov     qword ptr [rdx], 0
0x18001203e  mov     eax, [r14]
0x180012041  mov     [rdx], eax
0x180012043  and     eax, 6
0x180012046  cmp     al, 6
0x180012048  jz      loc_1800121D9
0x18001204e  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180012053  mov     ebp, eax
0x180012055  mov     dword ptr [rsp+58h+arg_0], 0
0x18001205d  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180012064  test    rax, rax
0x180012067  jz      short loc_180012081
0x180012069  lea     r8, [rsp+58h+arg_0]
0x18001206e  mov     edx, 3
0x180012073  mov     ecx, 30FC6E5h
0x180012078  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001207d  mov     edx, eax
0x18001207f  jmp     short loc_18001208F
0x180012081  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180012088  test    rax, rax
0x18001208b  jnz     short loc_180012069
0x18001208d  xor     edx, edx
0x18001208f  mov     r8d, edx
0x180012092  mov     eax, edx
0x180012094  and     r8d, 0FFFFFF3Fh
0x18001209b  and     edx, 80h
0x1800120a1  mov     ecx, r8d
0x1800120a4  mov     r12d, 40h ; '@'
0x1800120aa  and     ecx, 3
0x1800120ad  and     eax, r12d
0x1800120b0  shl     ecx, 2
0x1800120b3  or      ecx, eax
0x1800120b5  shl     ecx, 2
0x1800120b8  or      ecx, edx
0x1800120ba  lea     ebx, ds:0[rcx*8]
0x1800120c1  test    r8d, r8d
0x1800120c4  jnz     short loc_1800120CB
0x1800120c6  mov     eax, r12d
0x1800120c9  jmp     short loc_1800120D5
0x1800120cb  xor     eax, eax
0x1800120cd  cmp     r8d, 2
0x1800120d1  cmovz   eax, r12d
0x1800120d5  or      ebx, eax
0x1800120d7  mov     ecx, 0C00h
0x1800120dc  mov     eax, ebx
0x1800120de  and     eax, ecx
0x1800120e0  cmp     eax, ecx
0x1800120e2  jnz     short loc_1800120E9
0x1800120e4  mov     sil, 1
0x1800120e7  jmp     short loc_1800120F1
0x1800120e9  xor     sil, sil
0x1800120ec  test    r12b, bl
0x1800120ef  jz      short loc_18001210C
0x1800120f1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_49093927@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_49093927@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_49093927> `wil::Feature<__WilFeatureTraits_Feature_49093927>::GetImpl(void)'::`2'::impl
0x1800120f8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_49093927@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_49093927>::__private_IsEnabled(wil::ReportingKind)
0x1800120fd  test    sil, sil
0x180012100  jz      short loc_18001210E
0x180012102  test    al, al
0x180012104  jnz     short loc_18001210E
0x180012106  btr     ebx, 0Ah
0x18001210a  jmp     short loc_18001210E
0x18001210c  xor     al, al
0x18001210e  test    r12b, bl
0x180012111  jz      short loc_18001211E
0x180012113  test    al, al
0x180012115  jz      short loc_18001211E
0x180012117  mov     esi, 1
0x18001211c  jmp     short loc_180012120
0x18001211e  xor     esi, esi
0x180012120  mov     eax, [rdi]
0x180012122  or      esi, ebx
0x180012124  mov     ebx, 180h
0x180012129  cmp     dword ptr [rsp+58h+arg_0], 0
0x18001212e  mov     edx, eax
0x180012130  mov     [rdi], eax
0x180012132  jz      short loc_18001216C
0x180012134  test    dl, 2
0x180012137  jnz     short loc_18001216C
0x180012139  mov     eax, esi
0x18001213b  xor     eax, edx
0x18001213d  and     eax, ebx
0x18001213f  xor     eax, edx
0x180012141  mov     ecx, eax
0x180012143  xor     ecx, esi
0x180012145  and     ecx, r12d
0x180012148  xor     ecx, eax
0x18001214a  mov     eax, ecx
0x18001214c  xor     eax, esi
0x18001214e  and     eax, 1
0x180012151  xor     eax, ecx
0x180012153  mov     r8d, eax
0x180012156  xor     r8d, esi
0x180012159  and     r8d, 800h
0x180012160  xor     r8d, eax
0x180012163  or      r8d, 2
0x180012167  mov     [rdi], r8d
0x18001216a  jmp     short loc_18001216F
0x18001216c  mov     r8d, edx
0x18001216f  mov     r9d, edx
0x180012172  and     r9d, 4
0x180012176  jnz     short loc_18001218D
0x180012178  mov     ecx, esi
0x18001217a  xor     ecx, r8d
0x18001217d  and     ecx, 400h
0x180012183  xor     ecx, r8d
0x180012186  or      ecx, 4
0x180012189  mov     [rdi], ecx
0x18001218b  jmp     short loc_180012190
0x18001218d  mov     ecx, r8d
0x180012190  mov     eax, edx
0x180012192  lock cmpxchg [r14], ecx
0x180012197  jnz     short loc_180012129
0x180012199  test    r9d, r9d
0x18001219c  jnz     short loc_1800121AD
0x18001219e  mov     r8d, ebp
0x1800121a1  lea     edx, [r9+3]
0x1800121a5  mov     rcx, r14
0x1800121a8  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800121ad  test    byte ptr [rdi], 2
0x1800121b0  jnz     short loc_1800121D9
0x1800121b2  mov     eax, [rdi]
0x1800121b4  xor     eax, esi
0x1800121b6  and     eax, ebx
0x1800121b8  xor     eax, [rdi]
0x1800121ba  mov     ecx, eax
0x1800121bc  xor     ecx, esi
0x1800121be  and     ecx, r12d
0x1800121c1  xor     ecx, eax
0x1800121c3  mov     edx, ecx
0x1800121c5  xor     edx, esi
0x1800121c7  and     edx, 1
0x1800121ca  xor     edx, ecx
0x1800121cc  mov     eax, edx
0x1800121ce  xor     eax, esi
0x1800121d0  and     eax, 800h
0x1800121d5  xor     eax, edx
0x1800121d7  mov     [rdi], eax
0x1800121d9  mov     rax, rdi
0x1800121dc  add     rsp, 28h
0x1800121e0  pop     r14
0x1800121e2  pop     r12
0x1800121e4  pop     rdi
0x1800121e5  pop     rsi
0x1800121e6  pop     rbp
0x1800121e7  pop     rbx
0x1800121e8  retn
```
