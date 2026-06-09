# wil::details::FeatureImpl<__WilFeatureTraits_Feature_AckWOSC>::GetCachedFeatureEnabledState(void)

- ea: `0x18001267c`
- end: `0x180012849`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_AckWOSC@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001737c`

## callees

- `0x18000ca74`
- `0x18000e564`
- `0x18001267c`
- `0x180017690`
- `0x180029010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_AckWOSC>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_AckWOSC__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_AckWOSC__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(60940139, 3, &v20);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_AckWOSC__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_AckWOSC__descriptor, 3, v4);
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
0x18001267c  mov     [rsp+arg_0], rcx
0x180012681  push    rbx
0x180012682  push    rbp
0x180012683  push    rsi
0x180012684  push    rdi
0x180012685  push    r12
0x180012687  push    r14
0x180012689  sub     rsp, 28h
0x18001268d  mov     r14, cs:Feature_AckWOSC__descriptor
0x180012694  mov     rdi, rdx
0x180012697  mov     qword ptr [rdx], 0
0x18001269e  mov     eax, [r14]
0x1800126a1  mov     [rdx], eax
0x1800126a3  and     eax, 6
0x1800126a6  cmp     al, 6
0x1800126a8  jz      loc_180012839
0x1800126ae  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800126b3  mov     ebp, eax
0x1800126b5  mov     dword ptr [rsp+58h+arg_0], 0
0x1800126bd  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800126c4  test    rax, rax
0x1800126c7  jz      short loc_1800126E1
0x1800126c9  lea     r8, [rsp+58h+arg_0]
0x1800126ce  mov     edx, 3
0x1800126d3  mov     ecx, 3A1DF6Bh
0x1800126d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126dd  mov     edx, eax
0x1800126df  jmp     short loc_1800126EF
0x1800126e1  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1800126e8  test    rax, rax
0x1800126eb  jnz     short loc_1800126C9
0x1800126ed  xor     edx, edx
0x1800126ef  mov     r8d, edx
0x1800126f2  mov     eax, edx
0x1800126f4  and     r8d, 0FFFFFF3Fh
0x1800126fb  and     edx, 80h
0x180012701  mov     ecx, r8d
0x180012704  mov     r12d, 40h ; '@'
0x18001270a  and     ecx, 3
0x18001270d  and     eax, r12d
0x180012710  shl     ecx, 2
0x180012713  or      ecx, eax
0x180012715  shl     ecx, 2
0x180012718  or      ecx, edx
0x18001271a  lea     ebx, ds:0[rcx*8]
0x180012721  test    r8d, r8d
0x180012724  jnz     short loc_18001272B
0x180012726  mov     eax, r12d
0x180012729  jmp     short loc_180012735
0x18001272b  xor     eax, eax
0x18001272d  cmp     r8d, 2
0x180012731  cmovz   eax, r12d
0x180012735  or      ebx, eax
0x180012737  mov     ecx, 0C00h
0x18001273c  mov     eax, ebx
0x18001273e  and     eax, ecx
0x180012740  cmp     eax, ecx
0x180012742  jnz     short loc_180012749
0x180012744  mov     sil, 1
0x180012747  jmp     short loc_180012751
0x180012749  xor     sil, sil
0x18001274c  test    r12b, bl
0x18001274f  jz      short loc_18001276C
0x180012751  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestUex12@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestUex12@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12> `wil::Feature<__WilFeatureTraits_Feature_TestUex12>::GetImpl(void)'::`2'::impl
0x180012758  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestUex12@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::__private_IsEnabled(wil::ReportingKind)
0x18001275d  test    sil, sil
0x180012760  jz      short loc_18001276E
0x180012762  test    al, al
0x180012764  jnz     short loc_18001276E
0x180012766  btr     ebx, 0Ah
0x18001276a  jmp     short loc_18001276E
0x18001276c  xor     al, al
0x18001276e  test    r12b, bl
0x180012771  jz      short loc_18001277E
0x180012773  test    al, al
0x180012775  jz      short loc_18001277E
0x180012777  mov     esi, 1
0x18001277c  jmp     short loc_180012780
0x18001277e  xor     esi, esi
0x180012780  mov     eax, [rdi]
0x180012782  or      esi, ebx
0x180012784  mov     ebx, 180h
0x180012789  cmp     dword ptr [rsp+58h+arg_0], 0
0x18001278e  mov     edx, eax
0x180012790  mov     [rdi], eax
0x180012792  jz      short loc_1800127CC
0x180012794  test    dl, 2
0x180012797  jnz     short loc_1800127CC
0x180012799  mov     eax, esi
0x18001279b  xor     eax, edx
0x18001279d  and     eax, ebx
0x18001279f  xor     eax, edx
0x1800127a1  mov     ecx, eax
0x1800127a3  xor     ecx, esi
0x1800127a5  and     ecx, r12d
0x1800127a8  xor     ecx, eax
0x1800127aa  mov     eax, ecx
0x1800127ac  xor     eax, esi
0x1800127ae  and     eax, 1
0x1800127b1  xor     eax, ecx
0x1800127b3  mov     r8d, eax
0x1800127b6  xor     r8d, esi
0x1800127b9  and     r8d, 800h
0x1800127c0  xor     r8d, eax
0x1800127c3  or      r8d, 2
0x1800127c7  mov     [rdi], r8d
0x1800127ca  jmp     short loc_1800127CF
0x1800127cc  mov     r8d, edx
0x1800127cf  mov     r9d, edx
0x1800127d2  and     r9d, 4
0x1800127d6  jnz     short loc_1800127ED
0x1800127d8  mov     ecx, esi
0x1800127da  xor     ecx, r8d
0x1800127dd  and     ecx, 400h
0x1800127e3  xor     ecx, r8d
0x1800127e6  or      ecx, 4
0x1800127e9  mov     [rdi], ecx
0x1800127eb  jmp     short loc_1800127F0
0x1800127ed  mov     ecx, r8d
0x1800127f0  mov     eax, edx
0x1800127f2  lock cmpxchg [r14], ecx
0x1800127f7  jnz     short loc_180012789
0x1800127f9  test    r9d, r9d
0x1800127fc  jnz     short loc_18001280D
0x1800127fe  mov     r8d, ebp
0x180012801  lea     edx, [r9+3]
0x180012805  mov     rcx, r14
0x180012808  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001280d  test    byte ptr [rdi], 2
0x180012810  jnz     short loc_180012839
0x180012812  mov     eax, [rdi]
0x180012814  xor     eax, esi
0x180012816  and     eax, ebx
0x180012818  xor     eax, [rdi]
0x18001281a  mov     ecx, eax
0x18001281c  xor     ecx, esi
0x18001281e  and     ecx, r12d
0x180012821  xor     ecx, eax
0x180012823  mov     edx, ecx
0x180012825  xor     edx, esi
0x180012827  and     edx, 1
0x18001282a  xor     edx, ecx
0x18001282c  mov     eax, edx
0x18001282e  xor     eax, esi
0x180012830  and     eax, 800h
0x180012835  xor     eax, edx
0x180012837  mov     [rdi], eax
0x180012839  mov     rax, rdi
0x18001283c  add     rsp, 28h
0x180012840  pop     r14
0x180012842  pop     r12
0x180012844  pop     rdi
0x180012845  pop     rsi
0x180012846  pop     rbp
0x180012847  pop     rbx
0x180012848  retn
```
