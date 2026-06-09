# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UnifiedTracing>::GetCachedFeatureEnabledState(void)

- ea: `0x18001f99c`
- end: `0x18001fb69`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UnifiedTracing@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180025364`

## callees

- `0x18000ca74`
- `0x18000e564`
- `0x1800175f4`
- `0x18001f99c`
- `0x180029010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UnifiedTracing>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_UnifiedTracing__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UnifiedTracing__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(59387726, 3, &v20);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UnifiedTracing__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_UnifiedTracing__descriptor, 3, v4);
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
0x18001f99c  mov     [rsp+arg_0], rcx
0x18001f9a1  push    rbx
0x18001f9a2  push    rbp
0x18001f9a3  push    rsi
0x18001f9a4  push    rdi
0x18001f9a5  push    r12
0x18001f9a7  push    r14
0x18001f9a9  sub     rsp, 28h
0x18001f9ad  mov     r14, cs:Feature_UnifiedTracing__descriptor
0x18001f9b4  mov     rdi, rdx
0x18001f9b7  mov     qword ptr [rdx], 0
0x18001f9be  mov     eax, [r14]
0x18001f9c1  mov     [rdx], eax
0x18001f9c3  and     eax, 6
0x18001f9c6  cmp     al, 6
0x18001f9c8  jz      loc_18001FB59
0x18001f9ce  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001f9d3  mov     ebp, eax
0x18001f9d5  mov     dword ptr [rsp+58h+arg_0], 0
0x18001f9dd  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001f9e4  test    rax, rax
0x18001f9e7  jz      short loc_18001FA01
0x18001f9e9  lea     r8, [rsp+58h+arg_0]
0x18001f9ee  mov     edx, 3
0x18001f9f3  mov     ecx, 38A2F4Eh
0x18001f9f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f9fd  mov     edx, eax
0x18001f9ff  jmp     short loc_18001FA0F
0x18001fa01  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001fa08  test    rax, rax
0x18001fa0b  jnz     short loc_18001F9E9
0x18001fa0d  xor     edx, edx
0x18001fa0f  mov     r8d, edx
0x18001fa12  mov     eax, edx
0x18001fa14  and     r8d, 0FFFFFF3Fh
0x18001fa1b  and     edx, 80h
0x18001fa21  mov     ecx, r8d
0x18001fa24  mov     r12d, 40h ; '@'
0x18001fa2a  and     ecx, 3
0x18001fa2d  and     eax, r12d
0x18001fa30  shl     ecx, 2
0x18001fa33  or      ecx, eax
0x18001fa35  shl     ecx, 2
0x18001fa38  or      ecx, edx
0x18001fa3a  lea     ebx, ds:0[rcx*8]
0x18001fa41  test    r8d, r8d
0x18001fa44  jnz     short loc_18001FA4B
0x18001fa46  mov     eax, r12d
0x18001fa49  jmp     short loc_18001FA55
0x18001fa4b  xor     eax, eax
0x18001fa4d  cmp     r8d, 2
0x18001fa51  cmovz   eax, r12d
0x18001fa55  or      ebx, eax
0x18001fa57  mov     ecx, 0C00h
0x18001fa5c  mov     eax, ebx
0x18001fa5e  and     eax, ecx
0x18001fa60  cmp     eax, ecx
0x18001fa62  jnz     short loc_18001FA69
0x18001fa64  mov     sil, 1
0x18001fa67  jmp     short loc_18001FA71
0x18001fa69  xor     sil, sil
0x18001fa6c  test    r12b, bl
0x18001fa6f  jz      short loc_18001FA8C
0x18001fa71  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestLoc1Perf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf> `wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl(void)'::`2'::impl
0x18001fa78  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(wil::ReportingKind)
0x18001fa7d  test    sil, sil
0x18001fa80  jz      short loc_18001FA8E
0x18001fa82  test    al, al
0x18001fa84  jnz     short loc_18001FA8E
0x18001fa86  btr     ebx, 0Ah
0x18001fa8a  jmp     short loc_18001FA8E
0x18001fa8c  xor     al, al
0x18001fa8e  test    r12b, bl
0x18001fa91  jz      short loc_18001FA9E
0x18001fa93  test    al, al
0x18001fa95  jz      short loc_18001FA9E
0x18001fa97  mov     esi, 1
0x18001fa9c  jmp     short loc_18001FAA0
0x18001fa9e  xor     esi, esi
0x18001faa0  mov     eax, [rdi]
0x18001faa2  or      esi, ebx
0x18001faa4  mov     ebx, 180h
0x18001faa9  cmp     dword ptr [rsp+58h+arg_0], 0
0x18001faae  mov     edx, eax
0x18001fab0  mov     [rdi], eax
0x18001fab2  jz      short loc_18001FAEC
0x18001fab4  test    dl, 2
0x18001fab7  jnz     short loc_18001FAEC
0x18001fab9  mov     eax, esi
0x18001fabb  xor     eax, edx
0x18001fabd  and     eax, ebx
0x18001fabf  xor     eax, edx
0x18001fac1  mov     ecx, eax
0x18001fac3  xor     ecx, esi
0x18001fac5  and     ecx, r12d
0x18001fac8  xor     ecx, eax
0x18001faca  mov     eax, ecx
0x18001facc  xor     eax, esi
0x18001face  and     eax, 1
0x18001fad1  xor     eax, ecx
0x18001fad3  mov     r8d, eax
0x18001fad6  xor     r8d, esi
0x18001fad9  and     r8d, 800h
0x18001fae0  xor     r8d, eax
0x18001fae3  or      r8d, 2
0x18001fae7  mov     [rdi], r8d
0x18001faea  jmp     short loc_18001FAEF
0x18001faec  mov     r8d, edx
0x18001faef  mov     r9d, edx
0x18001faf2  and     r9d, 4
0x18001faf6  jnz     short loc_18001FB0D
0x18001faf8  mov     ecx, esi
0x18001fafa  xor     ecx, r8d
0x18001fafd  and     ecx, 400h
0x18001fb03  xor     ecx, r8d
0x18001fb06  or      ecx, 4
0x18001fb09  mov     [rdi], ecx
0x18001fb0b  jmp     short loc_18001FB10
0x18001fb0d  mov     ecx, r8d
0x18001fb10  mov     eax, edx
0x18001fb12  lock cmpxchg [r14], ecx
0x18001fb17  jnz     short loc_18001FAA9
0x18001fb19  test    r9d, r9d
0x18001fb1c  jnz     short loc_18001FB2D
0x18001fb1e  mov     r8d, ebp
0x18001fb21  lea     edx, [r9+3]
0x18001fb25  mov     rcx, r14
0x18001fb28  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001fb2d  test    byte ptr [rdi], 2
0x18001fb30  jnz     short loc_18001FB59
0x18001fb32  mov     eax, [rdi]
0x18001fb34  xor     eax, esi
0x18001fb36  and     eax, ebx
0x18001fb38  xor     eax, [rdi]
0x18001fb3a  mov     ecx, eax
0x18001fb3c  xor     ecx, esi
0x18001fb3e  and     ecx, r12d
0x18001fb41  xor     ecx, eax
0x18001fb43  mov     edx, ecx
0x18001fb45  xor     edx, esi
0x18001fb47  and     edx, 1
0x18001fb4a  xor     edx, ecx
0x18001fb4c  mov     eax, edx
0x18001fb4e  xor     eax, esi
0x18001fb50  and     eax, 800h
0x18001fb55  xor     eax, edx
0x18001fb57  mov     [rdi], eax
0x18001fb59  mov     rax, rdi
0x18001fb5c  add     rsp, 28h
0x18001fb60  pop     r14
0x18001fb62  pop     r12
0x18001fb64  pop     rdi
0x18001fb65  pop     rsi
0x18001fb66  pop     rbp
0x18001fb67  pop     rbx
0x18001fb68  retn
```
