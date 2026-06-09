# wil::details::FeatureImpl<__WilFeatureTraits_Feature_SleepOffenders>::GetCachedFeatureEnabledState(void)

- ea: `0x18001eca8`
- end: `0x18001ee75`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_SleepOffenders@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024fa8`

## callees

- `0x18000ca74`
- `0x18000e564`
- `0x18001772c`
- `0x18001eca8`
- `0x180029010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_SleepOffenders>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_SleepOffenders__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_SleepOffenders__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(59993183, 3, &v20);
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
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UexTest7>::GetImpl'::`2'::impl);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_SleepOffenders__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_SleepOffenders__descriptor, 3, v4);
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
0x18001eca8  mov     [rsp+arg_0], rcx
0x18001ecad  push    rbx
0x18001ecae  push    rbp
0x18001ecaf  push    rsi
0x18001ecb0  push    rdi
0x18001ecb1  push    r12
0x18001ecb3  push    r14
0x18001ecb5  sub     rsp, 28h
0x18001ecb9  mov     r14, cs:Feature_SleepOffenders__descriptor
0x18001ecc0  mov     rdi, rdx
0x18001ecc3  mov     qword ptr [rdx], 0
0x18001ecca  mov     eax, [r14]
0x18001eccd  mov     [rdx], eax
0x18001eccf  and     eax, 6
0x18001ecd2  cmp     al, 6
0x18001ecd4  jz      loc_18001EE65
0x18001ecda  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001ecdf  mov     ebp, eax
0x18001ece1  mov     dword ptr [rsp+58h+arg_0], 0
0x18001ece9  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001ecf0  test    rax, rax
0x18001ecf3  jz      short loc_18001ED0D
0x18001ecf5  lea     r8, [rsp+58h+arg_0]
0x18001ecfa  mov     edx, 3
0x18001ecff  mov     ecx, 3936C5Fh
0x18001ed04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed09  mov     edx, eax
0x18001ed0b  jmp     short loc_18001ED1B
0x18001ed0d  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001ed14  test    rax, rax
0x18001ed17  jnz     short loc_18001ECF5
0x18001ed19  xor     edx, edx
0x18001ed1b  mov     r8d, edx
0x18001ed1e  mov     eax, edx
0x18001ed20  and     r8d, 0FFFFFF3Fh
0x18001ed27  and     edx, 80h
0x18001ed2d  mov     ecx, r8d
0x18001ed30  mov     r12d, 40h ; '@'
0x18001ed36  and     ecx, 3
0x18001ed39  and     eax, r12d
0x18001ed3c  shl     ecx, 2
0x18001ed3f  or      ecx, eax
0x18001ed41  shl     ecx, 2
0x18001ed44  or      ecx, edx
0x18001ed46  lea     ebx, ds:0[rcx*8]
0x18001ed4d  test    r8d, r8d
0x18001ed50  jnz     short loc_18001ED57
0x18001ed52  mov     eax, r12d
0x18001ed55  jmp     short loc_18001ED61
0x18001ed57  xor     eax, eax
0x18001ed59  cmp     r8d, 2
0x18001ed5d  cmovz   eax, r12d
0x18001ed61  or      ebx, eax
0x18001ed63  mov     ecx, 0C00h
0x18001ed68  mov     eax, ebx
0x18001ed6a  and     eax, ecx
0x18001ed6c  cmp     eax, ecx
0x18001ed6e  jnz     short loc_18001ED75
0x18001ed70  mov     sil, 1
0x18001ed73  jmp     short loc_18001ED7D
0x18001ed75  xor     sil, sil
0x18001ed78  test    r12b, bl
0x18001ed7b  jz      short loc_18001ED98
0x18001ed7d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UexTest7@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7> `wil::Feature<__WilFeatureTraits_Feature_UexTest7>::GetImpl(void)'::`2'::impl
0x18001ed84  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::__private_IsEnabled(wil::ReportingKind)
0x18001ed89  test    sil, sil
0x18001ed8c  jz      short loc_18001ED9A
0x18001ed8e  test    al, al
0x18001ed90  jnz     short loc_18001ED9A
0x18001ed92  btr     ebx, 0Ah
0x18001ed96  jmp     short loc_18001ED9A
0x18001ed98  xor     al, al
0x18001ed9a  test    r12b, bl
0x18001ed9d  jz      short loc_18001EDAA
0x18001ed9f  test    al, al
0x18001eda1  jz      short loc_18001EDAA
0x18001eda3  mov     esi, 1
0x18001eda8  jmp     short loc_18001EDAC
0x18001edaa  xor     esi, esi
0x18001edac  mov     eax, [rdi]
0x18001edae  or      esi, ebx
0x18001edb0  mov     ebx, 180h
0x18001edb5  cmp     dword ptr [rsp+58h+arg_0], 0
0x18001edba  mov     edx, eax
0x18001edbc  mov     [rdi], eax
0x18001edbe  jz      short loc_18001EDF8
0x18001edc0  test    dl, 2
0x18001edc3  jnz     short loc_18001EDF8
0x18001edc5  mov     eax, esi
0x18001edc7  xor     eax, edx
0x18001edc9  and     eax, ebx
0x18001edcb  xor     eax, edx
0x18001edcd  mov     ecx, eax
0x18001edcf  xor     ecx, esi
0x18001edd1  and     ecx, r12d
0x18001edd4  xor     ecx, eax
0x18001edd6  mov     eax, ecx
0x18001edd8  xor     eax, esi
0x18001edda  and     eax, 1
0x18001eddd  xor     eax, ecx
0x18001eddf  mov     r8d, eax
0x18001ede2  xor     r8d, esi
0x18001ede5  and     r8d, 800h
0x18001edec  xor     r8d, eax
0x18001edef  or      r8d, 2
0x18001edf3  mov     [rdi], r8d
0x18001edf6  jmp     short loc_18001EDFB
0x18001edf8  mov     r8d, edx
0x18001edfb  mov     r9d, edx
0x18001edfe  and     r9d, 4
0x18001ee02  jnz     short loc_18001EE19
0x18001ee04  mov     ecx, esi
0x18001ee06  xor     ecx, r8d
0x18001ee09  and     ecx, 400h
0x18001ee0f  xor     ecx, r8d
0x18001ee12  or      ecx, 4
0x18001ee15  mov     [rdi], ecx
0x18001ee17  jmp     short loc_18001EE1C
0x18001ee19  mov     ecx, r8d
0x18001ee1c  mov     eax, edx
0x18001ee1e  lock cmpxchg [r14], ecx
0x18001ee23  jnz     short loc_18001EDB5
0x18001ee25  test    r9d, r9d
0x18001ee28  jnz     short loc_18001EE39
0x18001ee2a  mov     r8d, ebp
0x18001ee2d  lea     edx, [r9+3]
0x18001ee31  mov     rcx, r14
0x18001ee34  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001ee39  test    byte ptr [rdi], 2
0x18001ee3c  jnz     short loc_18001EE65
0x18001ee3e  mov     eax, [rdi]
0x18001ee40  xor     eax, esi
0x18001ee42  and     eax, ebx
0x18001ee44  xor     eax, [rdi]
0x18001ee46  mov     ecx, eax
0x18001ee48  xor     ecx, esi
0x18001ee4a  and     ecx, r12d
0x18001ee4d  xor     ecx, eax
0x18001ee4f  mov     edx, ecx
0x18001ee51  xor     edx, esi
0x18001ee53  and     edx, 1
0x18001ee56  xor     edx, ecx
0x18001ee58  mov     eax, edx
0x18001ee5a  xor     eax, esi
0x18001ee5c  and     eax, 800h
0x18001ee61  xor     eax, edx
0x18001ee63  mov     [rdi], eax
0x18001ee65  mov     rax, rdi
0x18001ee68  add     rsp, 28h
0x18001ee6c  pop     r14
0x18001ee6e  pop     r12
0x18001ee70  pop     rdi
0x18001ee71  pop     rsi
0x18001ee72  pop     rbp
0x18001ee73  pop     rbx
0x18001ee74  retn
```
