# wil::details::FeatureImpl<__WilFeatureTraits_Feature_SlowAppStopOnly>::GetCachedFeatureEnabledState(void)

- ea: `0x18001ee7c`
- end: `0x18001f049`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_SlowAppStopOnly@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180025048`

## callees

- `0x18000ca74`
- `0x18000e564`
- `0x18001ee7c`
- `0x180024708`
- `0x180029010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_SlowAppStopOnly>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_SlowAppStopOnly__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_SlowAppStopOnly__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(60682900, 3, &v20);
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
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes2D>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFixes2D>::GetImpl'::`2'::impl);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_SlowAppStopOnly__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_SlowAppStopOnly__descriptor, 3, v4);
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
0x18001ee7c  mov     [rsp+arg_0], rcx
0x18001ee81  push    rbx
0x18001ee82  push    rbp
0x18001ee83  push    rsi
0x18001ee84  push    rdi
0x18001ee85  push    r12
0x18001ee87  push    r14
0x18001ee89  sub     rsp, 28h
0x18001ee8d  mov     r14, cs:Feature_SlowAppStopOnly__descriptor
0x18001ee94  mov     rdi, rdx
0x18001ee97  mov     qword ptr [rdx], 0
0x18001ee9e  mov     eax, [r14]
0x18001eea1  mov     [rdx], eax
0x18001eea3  and     eax, 6
0x18001eea6  cmp     al, 6
0x18001eea8  jz      loc_18001F039
0x18001eeae  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001eeb3  mov     ebp, eax
0x18001eeb5  mov     dword ptr [rsp+58h+arg_0], 0
0x18001eebd  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001eec4  test    rax, rax
0x18001eec7  jz      short loc_18001EEE1
0x18001eec9  lea     r8, [rsp+58h+arg_0]
0x18001eece  mov     edx, 3
0x18001eed3  mov     ecx, 39DF294h
0x18001eed8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eedd  mov     edx, eax
0x18001eedf  jmp     short loc_18001EEEF
0x18001eee1  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001eee8  test    rax, rax
0x18001eeeb  jnz     short loc_18001EEC9
0x18001eeed  xor     edx, edx
0x18001eeef  mov     r8d, edx
0x18001eef2  mov     eax, edx
0x18001eef4  and     r8d, 0FFFFFF3Fh
0x18001eefb  and     edx, 80h
0x18001ef01  mov     ecx, r8d
0x18001ef04  mov     r12d, 40h ; '@'
0x18001ef0a  and     ecx, 3
0x18001ef0d  and     eax, r12d
0x18001ef10  shl     ecx, 2
0x18001ef13  or      ecx, eax
0x18001ef15  shl     ecx, 2
0x18001ef18  or      ecx, edx
0x18001ef1a  lea     ebx, ds:0[rcx*8]
0x18001ef21  test    r8d, r8d
0x18001ef24  jnz     short loc_18001EF2B
0x18001ef26  mov     eax, r12d
0x18001ef29  jmp     short loc_18001EF35
0x18001ef2b  xor     eax, eax
0x18001ef2d  cmp     r8d, 2
0x18001ef31  cmovz   eax, r12d
0x18001ef35  or      ebx, eax
0x18001ef37  mov     ecx, 0C00h
0x18001ef3c  mov     eax, ebx
0x18001ef3e  and     eax, ecx
0x18001ef40  cmp     eax, ecx
0x18001ef42  jnz     short loc_18001EF49
0x18001ef44  mov     sil, 1
0x18001ef47  jmp     short loc_18001EF51
0x18001ef49  xor     sil, sil
0x18001ef4c  test    r12b, bl
0x18001ef4f  jz      short loc_18001EF6C
0x18001ef51  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFixes2D@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixes2D@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes2D> `wil::Feature<__WilFeatureTraits_Feature_BugFixes2D>::GetImpl(void)'::`2'::impl
0x18001ef58  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixes2D@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes2D>::__private_IsEnabled(wil::ReportingKind)
0x18001ef5d  test    sil, sil
0x18001ef60  jz      short loc_18001EF6E
0x18001ef62  test    al, al
0x18001ef64  jnz     short loc_18001EF6E
0x18001ef66  btr     ebx, 0Ah
0x18001ef6a  jmp     short loc_18001EF6E
0x18001ef6c  xor     al, al
0x18001ef6e  test    r12b, bl
0x18001ef71  jz      short loc_18001EF7E
0x18001ef73  test    al, al
0x18001ef75  jz      short loc_18001EF7E
0x18001ef77  mov     esi, 1
0x18001ef7c  jmp     short loc_18001EF80
0x18001ef7e  xor     esi, esi
0x18001ef80  mov     eax, [rdi]
0x18001ef82  or      esi, ebx
0x18001ef84  mov     ebx, 180h
0x18001ef89  cmp     dword ptr [rsp+58h+arg_0], 0
0x18001ef8e  mov     edx, eax
0x18001ef90  mov     [rdi], eax
0x18001ef92  jz      short loc_18001EFCC
0x18001ef94  test    dl, 2
0x18001ef97  jnz     short loc_18001EFCC
0x18001ef99  mov     eax, esi
0x18001ef9b  xor     eax, edx
0x18001ef9d  and     eax, ebx
0x18001ef9f  xor     eax, edx
0x18001efa1  mov     ecx, eax
0x18001efa3  xor     ecx, esi
0x18001efa5  and     ecx, r12d
0x18001efa8  xor     ecx, eax
0x18001efaa  mov     eax, ecx
0x18001efac  xor     eax, esi
0x18001efae  and     eax, 1
0x18001efb1  xor     eax, ecx
0x18001efb3  mov     r8d, eax
0x18001efb6  xor     r8d, esi
0x18001efb9  and     r8d, 800h
0x18001efc0  xor     r8d, eax
0x18001efc3  or      r8d, 2
0x18001efc7  mov     [rdi], r8d
0x18001efca  jmp     short loc_18001EFCF
0x18001efcc  mov     r8d, edx
0x18001efcf  mov     r9d, edx
0x18001efd2  and     r9d, 4
0x18001efd6  jnz     short loc_18001EFED
0x18001efd8  mov     ecx, esi
0x18001efda  xor     ecx, r8d
0x18001efdd  and     ecx, 400h
0x18001efe3  xor     ecx, r8d
0x18001efe6  or      ecx, 4
0x18001efe9  mov     [rdi], ecx
0x18001efeb  jmp     short loc_18001EFF0
0x18001efed  mov     ecx, r8d
0x18001eff0  mov     eax, edx
0x18001eff2  lock cmpxchg [r14], ecx
0x18001eff7  jnz     short loc_18001EF89
0x18001eff9  test    r9d, r9d
0x18001effc  jnz     short loc_18001F00D
0x18001effe  mov     r8d, ebp
0x18001f001  lea     edx, [r9+3]
0x18001f005  mov     rcx, r14
0x18001f008  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001f00d  test    byte ptr [rdi], 2
0x18001f010  jnz     short loc_18001F039
0x18001f012  mov     eax, [rdi]
0x18001f014  xor     eax, esi
0x18001f016  and     eax, ebx
0x18001f018  xor     eax, [rdi]
0x18001f01a  mov     ecx, eax
0x18001f01c  xor     ecx, esi
0x18001f01e  and     ecx, r12d
0x18001f021  xor     ecx, eax
0x18001f023  mov     edx, ecx
0x18001f025  xor     edx, esi
0x18001f027  and     edx, 1
0x18001f02a  xor     edx, ecx
0x18001f02c  mov     eax, edx
0x18001f02e  xor     eax, esi
0x18001f030  and     eax, 800h
0x18001f035  xor     eax, edx
0x18001f037  mov     [rdi], eax
0x18001f039  mov     rax, rdi
0x18001f03c  add     rsp, 28h
0x18001f040  pop     r14
0x18001f042  pop     r12
0x18001f044  pop     rdi
0x18001f045  pop     rsi
0x18001f046  pop     rbp
0x18001f047  pop     rbx
0x18001f048  retn
```
