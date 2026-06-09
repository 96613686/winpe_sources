# wil::details::FeatureImpl<__WilFeatureTraits_Feature_NetworkUX_BugFix_56366472>::GetCachedFeatureEnabledState(void)

- ea: `0x18001708c`
- end: `0x180017259`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_NetworkUX_BugFix_56366472@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800215b0`

## callees

- `0x180005cf8`
- `0x180009548`
- `0x18001708c`
- `0x1800216ec`
- `0x180033010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_NetworkUX_BugFix_56366472>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
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
  v3 = *(_DWORD *)Feature_NetworkUX_BugFix_56366472__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_NetworkUX_BugFix_56366472__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(56366472, 3, &v20);
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
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl'::`2'::impl);
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
    v12 = _InterlockedCompareExchange(
            (volatile signed __int32 *)Feature_NetworkUX_BugFix_56366472__descriptor,
            v18,
            v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_NetworkUX_BugFix_56366472__descriptor, 3, v4);
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
0x18001708c  mov     [rsp+arg_0], rcx
0x180017091  push    rbx
0x180017092  push    rbp
0x180017093  push    rsi
0x180017094  push    rdi
0x180017095  push    r12
0x180017097  push    r14
0x180017099  sub     rsp, 28h
0x18001709d  mov     r14, cs:Feature_NetworkUX_BugFix_56366472__descriptor
0x1800170a4  mov     rdi, rdx
0x1800170a7  mov     qword ptr [rdx], 0
0x1800170ae  mov     eax, [r14]
0x1800170b1  mov     [rdx], eax
0x1800170b3  and     eax, 6
0x1800170b6  cmp     al, 6
0x1800170b8  jz      loc_180017249
0x1800170be  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800170c3  mov     ebp, eax
0x1800170c5  mov     dword ptr [rsp+58h+arg_0], 0
0x1800170cd  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800170d4  test    rax, rax
0x1800170d7  jz      short loc_1800170F1
0x1800170d9  lea     r8, [rsp+58h+arg_0]
0x1800170de  mov     edx, 3
0x1800170e3  mov     ecx, 35C1588h
0x1800170e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170ed  mov     edx, eax
0x1800170ef  jmp     short loc_1800170FF
0x1800170f1  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1800170f8  test    rax, rax
0x1800170fb  jnz     short loc_1800170D9
0x1800170fd  xor     edx, edx
0x1800170ff  mov     r8d, edx
0x180017102  mov     eax, edx
0x180017104  and     r8d, 0FFFFFF3Fh
0x18001710b  and     edx, 80h
0x180017111  mov     ecx, r8d
0x180017114  mov     r12d, 40h ; '@'
0x18001711a  and     ecx, 3
0x18001711d  and     eax, r12d
0x180017120  shl     ecx, 2
0x180017123  or      ecx, eax
0x180017125  shl     ecx, 2
0x180017128  or      ecx, edx
0x18001712a  lea     ebx, ds:0[rcx*8]
0x180017131  test    r8d, r8d
0x180017134  jnz     short loc_18001713B
0x180017136  mov     eax, r12d
0x180017139  jmp     short loc_180017145
0x18001713b  xor     eax, eax
0x18001713d  cmp     r8d, 2
0x180017141  cmovz   eax, r12d
0x180017145  or      ebx, eax
0x180017147  mov     ecx, 0C00h
0x18001714c  mov     eax, ebx
0x18001714e  and     eax, ecx
0x180017150  cmp     eax, ecx
0x180017152  jnz     short loc_180017159
0x180017154  mov     sil, 1
0x180017157  jmp     short loc_180017161
0x180017159  xor     sil, sil
0x18001715c  test    r12b, bl
0x18001715f  jz      short loc_18001717C
0x180017161  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestLoc1Perf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf> `wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl(void)'::`2'::impl
0x180017168  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(wil::ReportingKind)
0x18001716d  test    sil, sil
0x180017170  jz      short loc_18001717E
0x180017172  test    al, al
0x180017174  jnz     short loc_18001717E
0x180017176  btr     ebx, 0Ah
0x18001717a  jmp     short loc_18001717E
0x18001717c  xor     al, al
0x18001717e  test    r12b, bl
0x180017181  jz      short loc_18001718E
0x180017183  test    al, al
0x180017185  jz      short loc_18001718E
0x180017187  mov     esi, 1
0x18001718c  jmp     short loc_180017190
0x18001718e  xor     esi, esi
0x180017190  mov     eax, [rdi]
0x180017192  or      esi, ebx
0x180017194  mov     ebx, 180h
0x180017199  cmp     dword ptr [rsp+58h+arg_0], 0
0x18001719e  mov     edx, eax
0x1800171a0  mov     [rdi], eax
0x1800171a2  jz      short loc_1800171DC
0x1800171a4  test    dl, 2
0x1800171a7  jnz     short loc_1800171DC
0x1800171a9  mov     eax, esi
0x1800171ab  xor     eax, edx
0x1800171ad  and     eax, ebx
0x1800171af  xor     eax, edx
0x1800171b1  mov     ecx, eax
0x1800171b3  xor     ecx, esi
0x1800171b5  and     ecx, r12d
0x1800171b8  xor     ecx, eax
0x1800171ba  mov     eax, ecx
0x1800171bc  xor     eax, esi
0x1800171be  and     eax, 1
0x1800171c1  xor     eax, ecx
0x1800171c3  mov     r8d, eax
0x1800171c6  xor     r8d, esi
0x1800171c9  and     r8d, 800h
0x1800171d0  xor     r8d, eax
0x1800171d3  or      r8d, 2
0x1800171d7  mov     [rdi], r8d
0x1800171da  jmp     short loc_1800171DF
0x1800171dc  mov     r8d, edx
0x1800171df  mov     r9d, edx
0x1800171e2  and     r9d, 4
0x1800171e6  jnz     short loc_1800171FD
0x1800171e8  mov     ecx, esi
0x1800171ea  xor     ecx, r8d
0x1800171ed  and     ecx, 400h
0x1800171f3  xor     ecx, r8d
0x1800171f6  or      ecx, 4
0x1800171f9  mov     [rdi], ecx
0x1800171fb  jmp     short loc_180017200
0x1800171fd  mov     ecx, r8d
0x180017200  mov     eax, edx
0x180017202  lock cmpxchg [r14], ecx
0x180017207  jnz     short loc_180017199
0x180017209  test    r9d, r9d
0x18001720c  jnz     short loc_18001721D
0x18001720e  mov     r8d, ebp
0x180017211  lea     edx, [r9+3]
0x180017215  mov     rcx, r14
0x180017218  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001721d  test    byte ptr [rdi], 2
0x180017220  jnz     short loc_180017249
0x180017222  mov     eax, [rdi]
0x180017224  xor     eax, esi
0x180017226  and     eax, ebx
0x180017228  xor     eax, [rdi]
0x18001722a  mov     ecx, eax
0x18001722c  xor     ecx, esi
0x18001722e  and     ecx, r12d
0x180017231  xor     ecx, eax
0x180017233  mov     edx, ecx
0x180017235  xor     edx, esi
0x180017237  and     edx, 1
0x18001723a  xor     edx, ecx
0x18001723c  mov     eax, edx
0x18001723e  xor     eax, esi
0x180017240  and     eax, 800h
0x180017245  xor     eax, edx
0x180017247  mov     [rdi], eax
0x180017249  mov     rax, rdi
0x18001724c  add     rsp, 28h
0x180017250  pop     r14
0x180017252  pop     r12
0x180017254  pop     rdi
0x180017255  pop     rsi
0x180017256  pop     rbp
0x180017257  pop     rbx
0x180017258  retn
```
