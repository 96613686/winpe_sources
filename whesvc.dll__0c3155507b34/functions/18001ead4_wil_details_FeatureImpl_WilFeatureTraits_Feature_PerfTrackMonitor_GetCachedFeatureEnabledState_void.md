# wil::details::FeatureImpl<__WilFeatureTraits_Feature_PerfTrackMonitor>::GetCachedFeatureEnabledState(void)

- ea: `0x18001ead4`
- end: `0x18001eca1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_PerfTrackMonitor@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024f08`

## callees

- `0x18000ca74`
- `0x18000e564`
- `0x180017690`
- `0x18001ead4`
- `0x180029010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_PerfTrackMonitor>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_PerfTrackMonitor__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_PerfTrackMonitor__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(60813023, 3, &v20);
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
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TestUex12>::GetImpl'::`2'::impl);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_PerfTrackMonitor__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_PerfTrackMonitor__descriptor, 3, v4);
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
0x18001ead4  mov     [rsp+arg_0], rcx
0x18001ead9  push    rbx
0x18001eada  push    rbp
0x18001eadb  push    rsi
0x18001eadc  push    rdi
0x18001eadd  push    r12
0x18001eadf  push    r14
0x18001eae1  sub     rsp, 28h
0x18001eae5  mov     r14, cs:Feature_PerfTrackMonitor__descriptor
0x18001eaec  mov     rdi, rdx
0x18001eaef  mov     qword ptr [rdx], 0
0x18001eaf6  mov     eax, [r14]
0x18001eaf9  mov     [rdx], eax
0x18001eafb  and     eax, 6
0x18001eafe  cmp     al, 6
0x18001eb00  jz      loc_18001EC91
0x18001eb06  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001eb0b  mov     ebp, eax
0x18001eb0d  mov     dword ptr [rsp+58h+arg_0], 0
0x18001eb15  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001eb1c  test    rax, rax
0x18001eb1f  jz      short loc_18001EB39
0x18001eb21  lea     r8, [rsp+58h+arg_0]
0x18001eb26  mov     edx, 3
0x18001eb2b  mov     ecx, 39FEEDFh
0x18001eb30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb35  mov     edx, eax
0x18001eb37  jmp     short loc_18001EB47
0x18001eb39  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001eb40  test    rax, rax
0x18001eb43  jnz     short loc_18001EB21
0x18001eb45  xor     edx, edx
0x18001eb47  mov     r8d, edx
0x18001eb4a  mov     eax, edx
0x18001eb4c  and     r8d, 0FFFFFF3Fh
0x18001eb53  and     edx, 80h
0x18001eb59  mov     ecx, r8d
0x18001eb5c  mov     r12d, 40h ; '@'
0x18001eb62  and     ecx, 3
0x18001eb65  and     eax, r12d
0x18001eb68  shl     ecx, 2
0x18001eb6b  or      ecx, eax
0x18001eb6d  shl     ecx, 2
0x18001eb70  or      ecx, edx
0x18001eb72  lea     ebx, ds:0[rcx*8]
0x18001eb79  test    r8d, r8d
0x18001eb7c  jnz     short loc_18001EB83
0x18001eb7e  mov     eax, r12d
0x18001eb81  jmp     short loc_18001EB8D
0x18001eb83  xor     eax, eax
0x18001eb85  cmp     r8d, 2
0x18001eb89  cmovz   eax, r12d
0x18001eb8d  or      ebx, eax
0x18001eb8f  mov     ecx, 0C00h
0x18001eb94  mov     eax, ebx
0x18001eb96  and     eax, ecx
0x18001eb98  cmp     eax, ecx
0x18001eb9a  jnz     short loc_18001EBA1
0x18001eb9c  mov     sil, 1
0x18001eb9f  jmp     short loc_18001EBA9
0x18001eba1  xor     sil, sil
0x18001eba4  test    r12b, bl
0x18001eba7  jz      short loc_18001EBC4
0x18001eba9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestUex12@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestUex12@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12> `wil::Feature<__WilFeatureTraits_Feature_TestUex12>::GetImpl(void)'::`2'::impl
0x18001ebb0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestUex12@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::__private_IsEnabled(wil::ReportingKind)
0x18001ebb5  test    sil, sil
0x18001ebb8  jz      short loc_18001EBC6
0x18001ebba  test    al, al
0x18001ebbc  jnz     short loc_18001EBC6
0x18001ebbe  btr     ebx, 0Ah
0x18001ebc2  jmp     short loc_18001EBC6
0x18001ebc4  xor     al, al
0x18001ebc6  test    r12b, bl
0x18001ebc9  jz      short loc_18001EBD6
0x18001ebcb  test    al, al
0x18001ebcd  jz      short loc_18001EBD6
0x18001ebcf  mov     esi, 1
0x18001ebd4  jmp     short loc_18001EBD8
0x18001ebd6  xor     esi, esi
0x18001ebd8  mov     eax, [rdi]
0x18001ebda  or      esi, ebx
0x18001ebdc  mov     ebx, 180h
0x18001ebe1  cmp     dword ptr [rsp+58h+arg_0], 0
0x18001ebe6  mov     edx, eax
0x18001ebe8  mov     [rdi], eax
0x18001ebea  jz      short loc_18001EC24
0x18001ebec  test    dl, 2
0x18001ebef  jnz     short loc_18001EC24
0x18001ebf1  mov     eax, esi
0x18001ebf3  xor     eax, edx
0x18001ebf5  and     eax, ebx
0x18001ebf7  xor     eax, edx
0x18001ebf9  mov     ecx, eax
0x18001ebfb  xor     ecx, esi
0x18001ebfd  and     ecx, r12d
0x18001ec00  xor     ecx, eax
0x18001ec02  mov     eax, ecx
0x18001ec04  xor     eax, esi
0x18001ec06  and     eax, 1
0x18001ec09  xor     eax, ecx
0x18001ec0b  mov     r8d, eax
0x18001ec0e  xor     r8d, esi
0x18001ec11  and     r8d, 800h
0x18001ec18  xor     r8d, eax
0x18001ec1b  or      r8d, 2
0x18001ec1f  mov     [rdi], r8d
0x18001ec22  jmp     short loc_18001EC27
0x18001ec24  mov     r8d, edx
0x18001ec27  mov     r9d, edx
0x18001ec2a  and     r9d, 4
0x18001ec2e  jnz     short loc_18001EC45
0x18001ec30  mov     ecx, esi
0x18001ec32  xor     ecx, r8d
0x18001ec35  and     ecx, 400h
0x18001ec3b  xor     ecx, r8d
0x18001ec3e  or      ecx, 4
0x18001ec41  mov     [rdi], ecx
0x18001ec43  jmp     short loc_18001EC48
0x18001ec45  mov     ecx, r8d
0x18001ec48  mov     eax, edx
0x18001ec4a  lock cmpxchg [r14], ecx
0x18001ec4f  jnz     short loc_18001EBE1
0x18001ec51  test    r9d, r9d
0x18001ec54  jnz     short loc_18001EC65
0x18001ec56  mov     r8d, ebp
0x18001ec59  lea     edx, [r9+3]
0x18001ec5d  mov     rcx, r14
0x18001ec60  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001ec65  test    byte ptr [rdi], 2
0x18001ec68  jnz     short loc_18001EC91
0x18001ec6a  mov     eax, [rdi]
0x18001ec6c  xor     eax, esi
0x18001ec6e  and     eax, ebx
0x18001ec70  xor     eax, [rdi]
0x18001ec72  mov     ecx, eax
0x18001ec74  xor     ecx, esi
0x18001ec76  and     ecx, r12d
0x18001ec79  xor     ecx, eax
0x18001ec7b  mov     edx, ecx
0x18001ec7d  xor     edx, esi
0x18001ec7f  and     edx, 1
0x18001ec82  xor     edx, ecx
0x18001ec84  mov     eax, edx
0x18001ec86  xor     eax, esi
0x18001ec88  and     eax, 800h
0x18001ec8d  xor     eax, edx
0x18001ec8f  mov     [rdi], eax
0x18001ec91  mov     rax, rdi
0x18001ec94  add     rsp, 28h
0x18001ec98  pop     r14
0x18001ec9a  pop     r12
0x18001ec9c  pop     rdi
0x18001ec9d  pop     rsi
0x18001ec9e  pop     rbp
0x18001ec9f  pop     rbx
0x18001eca0  retn
```
