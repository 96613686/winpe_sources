# wil::details::FeatureImpl<__WilFeatureTraits_Feature_56038648>::GetCachedFeatureEnabledState(void)

- ea: `0x140055514`
- end: `0x1400556b5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_56038648@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `417`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14005a4cc`
- `0x14005d32c`

## callees

- `0x14004693c`
- `0x140049d0c`
- `0x140055514`
- `0x14005c0d4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_56038648>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  int v5; // ebp
  int *v6; // r9
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  unsigned int v8; // r8d
  int v9; // edx
  int v10; // eax
  int v11; // edi
  char v12; // al
  int v13; // eax
  int v14; // edi
  signed __int32 v15; // eax
  bool v16; // zf
  signed __int32 v17; // edx
  int v18; // r8d
  int v19; // r9d
  signed __int32 v20; // ecx
  wil::details *v22; // [rsp+40h] [rbp+8h] BYREF

  v22 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_56038648__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_56038648__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v22) = 0;
  v5 = v4;
  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                          (wil::details *)0x35714F8,
                          3u,
                          (enum FEATURE_CHANGE_TIME)&v22,
                          v6);
  v8 = FeatureEnabledState & 0xFFFFFF3F;
  v9 = FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3))));
  v10 = 0;
  if ( v8 == 2 )
    v10 = 64;
  v11 = v10 | (8 * v9);
  if ( (v11 & 0xC00) == 0xC00 )
  {
    v12 = 1;
  }
  else
  {
    if ( (v11 & 0x40) != 0 )
      goto LABEL_11;
    v12 = 0;
  }
  if ( (v11 & 0x40) == 0 || !v12 )
  {
    v13 = 0;
    goto LABEL_12;
  }
LABEL_11:
  v13 = 1;
LABEL_12:
  v14 = v13 | v11;
  v15 = *(_DWORD *)a2;
  do
  {
    v16 = (_DWORD)v22 == 0;
    v17 = v15;
    *(_DWORD *)a2 = v15;
    if ( v16 || (v15 & 2) != 0 )
    {
      v18 = v15;
    }
    else
    {
      v18 = v15
          ^ ((unsigned __int16)v15
           ^ (unsigned __int16)v14)
          & 0x180
          ^ (v14
           ^ v15
           ^ ((unsigned __int16)v15
            ^ (unsigned __int16)v14)
           & 0x180)
          & 0x40
          ^ ((unsigned __int8)v14
           ^ (unsigned __int8)(v15 ^ (v15 ^ v14) & 0x80 ^ (v14 ^ v15 ^ (v15 ^ v14) & 0x80) & 0x40))
          & 1
          ^ ((unsigned __int16)v14
           ^ (unsigned __int16)(v15
                              ^ (v15
                               ^ v14)
                              & 0x180
                              ^ (v14
                               ^ v15
                               ^ (v15
                                ^ v14)
                               & 0x180)
                              & 0x40
                              ^ ((unsigned __int8)v14
                               ^ (unsigned __int8)(v15 ^ (v15 ^ v14) & 0x80 ^ (v14 ^ v15 ^ (v15 ^ v14) & 0x80) & 0x40))
                              & 1))
          & 0x800
          | 2;
      *(_DWORD *)a2 = v18;
    }
    v19 = v15 & 4;
    if ( (v15 & 4) != 0 )
    {
      v20 = v18;
    }
    else
    {
      v20 = v18 ^ ((unsigned __int16)v18 ^ (unsigned __int16)v14) & 0x400 | 4;
      *(_DWORD *)a2 = v20;
    }
    v15 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_56038648__descriptor, v20, v15);
  }
  while ( v17 != v15 );
  if ( !v19 )
    wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
      (RTL_SRWLOCK *)wil::details::g_enabledStateManager,
      (volatile signed __int32 *)Feature_56038648__descriptor,
      3,
      v5);
  if ( (*(_BYTE *)a2 & 2) == 0 )
    *(_DWORD *)a2 ^= ((unsigned __int16)v14
                    ^ (unsigned __int16)*(_DWORD *)a2)
                   & 0x180
                   ^ (v14
                    ^ *(_DWORD *)a2
                    ^ ((unsigned __int16)v14
                     ^ (unsigned __int16)*(_DWORD *)a2)
                    & 0x180)
                   & 0x40
                   ^ ((unsigned __int8)v14
                    ^ *(_BYTE *)a2
                    ^ ((unsigned __int8)v14
                     ^ (unsigned __int8)*(_DWORD *)a2)
                    & 0x80
                    ^ ((unsigned __int8)v14
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v14
                      ^ (unsigned __int8)*(_DWORD *)a2)
                     & 0x80)
                    & 0x40)
                   & 1
                   ^ ((unsigned __int16)v14
                    ^ *(_WORD *)a2
                    ^ ((unsigned __int16)v14
                     ^ (unsigned __int16)*(_DWORD *)a2)
                    & 0x180
                    ^ ((unsigned __int16)v14
                     ^ *(_WORD *)a2
                     ^ ((unsigned __int16)v14
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180)
                    & 0x40
                    ^ ((unsigned __int8)v14
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v14
                      ^ (unsigned __int8)*(_DWORD *)a2)
                     & 0x80
                     ^ ((unsigned __int8)v14
                      ^ *(_BYTE *)a2
                      ^ ((unsigned __int8)v14
                       ^ (unsigned __int8)*(_DWORD *)a2)
                      & 0x80)
                     & 0x40)
                    & 1)
                   & 0x800;
  return a2;
}

```

## disassembly

```asm
0x140055514  mov     [rsp+arg_8], rbx
0x140055519  mov     [rsp+arg_10], rbp
0x14005551e  mov     [rsp+arg_0], rcx
0x140055523  push    rsi
0x140055524  push    rdi
0x140055525  push    r15
0x140055527  sub     rsp, 20h
0x14005552b  mov     rsi, cs:Feature_56038648__descriptor
0x140055532  mov     rbx, rdx
0x140055535  mov     qword ptr [rdx], 0
0x14005553c  mov     eax, [rsi]
0x14005553e  mov     [rdx], eax
0x140055540  and     eax, 6
0x140055543  cmp     al, 6
0x140055545  jz      loc_14005569F
0x14005554b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140055550  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x140055555  mov     dword ptr [rsp+38h+arg_0], 0
0x14005555d  mov     edx, 3; unsigned int
0x140055562  mov     ecx, 35714F8h; this
0x140055567  mov     ebp, eax
0x140055569  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x14005556e  mov     r8d, eax
0x140055571  mov     ecx, eax
0x140055573  and     eax, 80h
0x140055578  and     r8d, 0FFFFFF3Fh
0x14005557f  mov     edx, r8d
0x140055582  mov     r15d, 40h ; '@'
0x140055588  and     edx, 3
0x14005558b  and     ecx, r15d
0x14005558e  shl     edx, 2
0x140055591  or      edx, ecx
0x140055593  shl     edx, 2
0x140055596  or      edx, eax
0x140055598  xor     eax, eax
0x14005559a  lea     edi, ds:0[rdx*8]
0x1400555a1  test    r8d, r8d
0x1400555a4  jz      short loc_1400555AE
0x1400555a6  cmp     r8d, 2
0x1400555aa  cmovz   eax, r15d
0x1400555ae  or      edi, eax
0x1400555b0  mov     edx, 0C00h
0x1400555b5  mov     ecx, edi
0x1400555b7  mov     eax, edi
0x1400555b9  and     ecx, r15d
0x1400555bc  and     eax, edx
0x1400555be  cmp     eax, edx
0x1400555c0  jnz     short loc_1400555C6
0x1400555c2  mov     al, 1
0x1400555c4  jmp     short loc_1400555CC
0x1400555c6  test    ecx, ecx
0x1400555c8  jnz     short loc_1400555D8
0x1400555ca  xor     al, al
0x1400555cc  test    ecx, ecx
0x1400555ce  jz      short loc_1400555D4
0x1400555d0  test    al, al
0x1400555d2  jnz     short loc_1400555D8
0x1400555d4  xor     eax, eax
0x1400555d6  jmp     short loc_1400555DD
0x1400555d8  mov     eax, 1
0x1400555dd  or      edi, eax
0x1400555df  mov     eax, [rbx]
0x1400555e1  cmp     dword ptr [rsp+38h+arg_0], 0
0x1400555e6  mov     edx, eax
0x1400555e8  mov     [rbx], eax
0x1400555ea  jz      short loc_140055627
0x1400555ec  test    dl, 2
0x1400555ef  jnz     short loc_140055627
0x1400555f1  mov     eax, edi
0x1400555f3  xor     eax, edx
0x1400555f5  and     eax, 180h
0x1400555fa  xor     eax, edx
0x1400555fc  mov     ecx, eax
0x1400555fe  xor     ecx, edi
0x140055600  and     ecx, r15d
0x140055603  xor     ecx, eax
0x140055605  mov     eax, ecx
0x140055607  xor     eax, edi
0x140055609  and     eax, 1
0x14005560c  xor     eax, ecx
0x14005560e  mov     r8d, eax
0x140055611  xor     r8d, edi
0x140055614  and     r8d, 800h
0x14005561b  xor     r8d, eax
0x14005561e  or      r8d, 2
0x140055622  mov     [rbx], r8d
0x140055625  jmp     short loc_14005562A
0x140055627  mov     r8d, edx
0x14005562a  mov     r9d, edx
0x14005562d  and     r9d, 4
0x140055631  jnz     short loc_140055648
0x140055633  mov     ecx, edi
0x140055635  xor     ecx, r8d
0x140055638  and     ecx, 400h
0x14005563e  xor     ecx, r8d
0x140055641  or      ecx, 4
0x140055644  mov     [rbx], ecx
0x140055646  jmp     short loc_14005564B
0x140055648  mov     ecx, r8d
0x14005564b  mov     eax, edx
0x14005564d  lock cmpxchg [rsi], ecx
0x140055651  jnz     short loc_1400555E1
0x140055653  test    r9d, r9d
0x140055656  jnz     short loc_140055670
0x140055658  mov     r9d, ebp
0x14005565b  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140055662  mov     r8d, 3
0x140055668  mov     rdx, rsi
0x14005566b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140055670  test    byte ptr [rbx], 2
0x140055673  jnz     short loc_14005569F
0x140055675  mov     eax, [rbx]
0x140055677  xor     eax, edi
0x140055679  and     eax, 180h
0x14005567e  xor     eax, [rbx]
0x140055680  mov     ecx, eax
0x140055682  xor     ecx, edi
0x140055684  and     ecx, r15d
0x140055687  xor     ecx, eax
0x140055689  mov     edx, ecx
0x14005568b  xor     edx, edi
0x14005568d  and     edx, 1
0x140055690  xor     edx, ecx
0x140055692  mov     eax, edx
0x140055694  xor     eax, edi
0x140055696  and     eax, 800h
0x14005569b  xor     eax, edx
0x14005569d  mov     [rbx], eax
0x14005569f  mov     rbp, [rsp+38h+arg_10]
0x1400556a4  mov     rax, rbx
0x1400556a7  mov     rbx, [rsp+38h+arg_8]
0x1400556ac  add     rsp, 20h
0x1400556b0  pop     r15
0x1400556b2  pop     rdi
0x1400556b3  pop     rsi
0x1400556b4  retn
```
