# wil::details::FeatureImpl<__WilFeatureTraits_Feature_CopyStartupSummary>::GetCachedFeatureEnabledState(void)

- ea: `0x18001da6c`
- end: `0x18001dc39`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CopyStartupSummary@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024968`

## callees

- `0x18000ca74`
- `0x18000e564`
- `0x18001da6c`
- `0x1800245cc`
- `0x180029010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_CopyStartupSummary>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_CopyStartupSummary__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_CopyStartupSummary__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(59032513, 3, &v20);
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
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::GetImpl'::`2'::impl);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_CopyStartupSummary__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_CopyStartupSummary__descriptor, 3, v4);
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
0x18001da6c  mov     [rsp+arg_0], rcx
0x18001da71  push    rbx
0x18001da72  push    rbp
0x18001da73  push    rsi
0x18001da74  push    rdi
0x18001da75  push    r12
0x18001da77  push    r14
0x18001da79  sub     rsp, 28h
0x18001da7d  mov     r14, cs:Feature_CopyStartupSummary__descriptor
0x18001da84  mov     rdi, rdx
0x18001da87  mov     qword ptr [rdx], 0
0x18001da8e  mov     eax, [r14]
0x18001da91  mov     [rdx], eax
0x18001da93  and     eax, 6
0x18001da96  cmp     al, 6
0x18001da98  jz      loc_18001DC29
0x18001da9e  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001daa3  mov     ebp, eax
0x18001daa5  mov     dword ptr [rsp+58h+arg_0], 0
0x18001daad  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001dab4  test    rax, rax
0x18001dab7  jz      short loc_18001DAD1
0x18001dab9  lea     r8, [rsp+58h+arg_0]
0x18001dabe  mov     edx, 3
0x18001dac3  mov     ecx, 384C3C1h
0x18001dac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dacd  mov     edx, eax
0x18001dacf  jmp     short loc_18001DADF
0x18001dad1  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001dad8  test    rax, rax
0x18001dadb  jnz     short loc_18001DAB9
0x18001dadd  xor     edx, edx
0x18001dadf  mov     r8d, edx
0x18001dae2  mov     eax, edx
0x18001dae4  and     r8d, 0FFFFFF3Fh
0x18001daeb  and     edx, 80h
0x18001daf1  mov     ecx, r8d
0x18001daf4  mov     r12d, 40h ; '@'
0x18001dafa  and     ecx, 3
0x18001dafd  and     eax, r12d
0x18001db00  shl     ecx, 2
0x18001db03  or      ecx, eax
0x18001db05  shl     ecx, 2
0x18001db08  or      ecx, edx
0x18001db0a  lea     ebx, ds:0[rcx*8]
0x18001db11  test    r8d, r8d
0x18001db14  jnz     short loc_18001DB1B
0x18001db16  mov     eax, r12d
0x18001db19  jmp     short loc_18001DB25
0x18001db1b  xor     eax, eax
0x18001db1d  cmp     r8d, 2
0x18001db21  cmovz   eax, r12d
0x18001db25  or      ebx, eax
0x18001db27  mov     ecx, 0C00h
0x18001db2c  mov     eax, ebx
0x18001db2e  and     eax, ecx
0x18001db30  cmp     eax, ecx
0x18001db32  jnz     short loc_18001DB39
0x18001db34  mov     sil, 1
0x18001db37  jmp     short loc_18001DB41
0x18001db39  xor     sil, sil
0x18001db3c  test    r12b, bl
0x18001db3f  jz      short loc_18001DB5C
0x18001db41  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AddMemInfoToBootTrace@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AddMemInfoToBootTrace@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddMemInfoToBootTrace> `wil::Feature<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::GetImpl(void)'::`2'::impl
0x18001db48  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AddMemInfoToBootTrace@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::__private_IsEnabled(wil::ReportingKind)
0x18001db4d  test    sil, sil
0x18001db50  jz      short loc_18001DB5E
0x18001db52  test    al, al
0x18001db54  jnz     short loc_18001DB5E
0x18001db56  btr     ebx, 0Ah
0x18001db5a  jmp     short loc_18001DB5E
0x18001db5c  xor     al, al
0x18001db5e  test    r12b, bl
0x18001db61  jz      short loc_18001DB6E
0x18001db63  test    al, al
0x18001db65  jz      short loc_18001DB6E
0x18001db67  mov     esi, 1
0x18001db6c  jmp     short loc_18001DB70
0x18001db6e  xor     esi, esi
0x18001db70  mov     eax, [rdi]
0x18001db72  or      esi, ebx
0x18001db74  mov     ebx, 180h
0x18001db79  cmp     dword ptr [rsp+58h+arg_0], 0
0x18001db7e  mov     edx, eax
0x18001db80  mov     [rdi], eax
0x18001db82  jz      short loc_18001DBBC
0x18001db84  test    dl, 2
0x18001db87  jnz     short loc_18001DBBC
0x18001db89  mov     eax, esi
0x18001db8b  xor     eax, edx
0x18001db8d  and     eax, ebx
0x18001db8f  xor     eax, edx
0x18001db91  mov     ecx, eax
0x18001db93  xor     ecx, esi
0x18001db95  and     ecx, r12d
0x18001db98  xor     ecx, eax
0x18001db9a  mov     eax, ecx
0x18001db9c  xor     eax, esi
0x18001db9e  and     eax, 1
0x18001dba1  xor     eax, ecx
0x18001dba3  mov     r8d, eax
0x18001dba6  xor     r8d, esi
0x18001dba9  and     r8d, 800h
0x18001dbb0  xor     r8d, eax
0x18001dbb3  or      r8d, 2
0x18001dbb7  mov     [rdi], r8d
0x18001dbba  jmp     short loc_18001DBBF
0x18001dbbc  mov     r8d, edx
0x18001dbbf  mov     r9d, edx
0x18001dbc2  and     r9d, 4
0x18001dbc6  jnz     short loc_18001DBDD
0x18001dbc8  mov     ecx, esi
0x18001dbca  xor     ecx, r8d
0x18001dbcd  and     ecx, 400h
0x18001dbd3  xor     ecx, r8d
0x18001dbd6  or      ecx, 4
0x18001dbd9  mov     [rdi], ecx
0x18001dbdb  jmp     short loc_18001DBE0
0x18001dbdd  mov     ecx, r8d
0x18001dbe0  mov     eax, edx
0x18001dbe2  lock cmpxchg [r14], ecx
0x18001dbe7  jnz     short loc_18001DB79
0x18001dbe9  test    r9d, r9d
0x18001dbec  jnz     short loc_18001DBFD
0x18001dbee  mov     r8d, ebp
0x18001dbf1  lea     edx, [r9+3]
0x18001dbf5  mov     rcx, r14
0x18001dbf8  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001dbfd  test    byte ptr [rdi], 2
0x18001dc00  jnz     short loc_18001DC29
0x18001dc02  mov     eax, [rdi]
0x18001dc04  xor     eax, esi
0x18001dc06  and     eax, ebx
0x18001dc08  xor     eax, [rdi]
0x18001dc0a  mov     ecx, eax
0x18001dc0c  xor     ecx, esi
0x18001dc0e  and     ecx, r12d
0x18001dc11  xor     ecx, eax
0x18001dc13  mov     edx, ecx
0x18001dc15  xor     edx, esi
0x18001dc17  and     edx, 1
0x18001dc1a  xor     edx, ecx
0x18001dc1c  mov     eax, edx
0x18001dc1e  xor     eax, esi
0x18001dc20  and     eax, 800h
0x18001dc25  xor     eax, edx
0x18001dc27  mov     [rdi], eax
0x18001dc29  mov     rax, rdi
0x18001dc2c  add     rsp, 28h
0x18001dc30  pop     r14
0x18001dc32  pop     r12
0x18001dc34  pop     rdi
0x18001dc35  pop     rsi
0x18001dc36  pop     rbp
0x18001dc37  pop     rbx
0x18001dc38  retn
```
