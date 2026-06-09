# wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceHotTrace>::GetCachedFeatureEnabledState(void)

- ea: `0x18001de14`
- end: `0x18001dfe1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_DeviceHotTrace@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024aa8`

## callees

- `0x18000ca74`
- `0x18000e564`
- `0x1800174bc`
- `0x18001de14`
- `0x180029010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceHotTrace>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_DeviceHotTrace__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_DeviceHotTrace__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(58497816, 3, &v20);
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
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Ten2Loc>::GetImpl'::`2'::impl);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_DeviceHotTrace__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_DeviceHotTrace__descriptor, 3, v4);
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
0x18001de14  mov     [rsp+arg_0], rcx
0x18001de19  push    rbx
0x18001de1a  push    rbp
0x18001de1b  push    rsi
0x18001de1c  push    rdi
0x18001de1d  push    r12
0x18001de1f  push    r14
0x18001de21  sub     rsp, 28h
0x18001de25  mov     r14, cs:Feature_DeviceHotTrace__descriptor
0x18001de2c  mov     rdi, rdx
0x18001de2f  mov     qword ptr [rdx], 0
0x18001de36  mov     eax, [r14]
0x18001de39  mov     [rdx], eax
0x18001de3b  and     eax, 6
0x18001de3e  cmp     al, 6
0x18001de40  jz      loc_18001DFD1
0x18001de46  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001de4b  mov     ebp, eax
0x18001de4d  mov     dword ptr [rsp+58h+arg_0], 0
0x18001de55  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001de5c  test    rax, rax
0x18001de5f  jz      short loc_18001DE79
0x18001de61  lea     r8, [rsp+58h+arg_0]
0x18001de66  mov     edx, 3
0x18001de6b  mov     ecx, 37C9B18h
0x18001de70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de75  mov     edx, eax
0x18001de77  jmp     short loc_18001DE87
0x18001de79  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001de80  test    rax, rax
0x18001de83  jnz     short loc_18001DE61
0x18001de85  xor     edx, edx
0x18001de87  mov     r8d, edx
0x18001de8a  mov     eax, edx
0x18001de8c  and     r8d, 0FFFFFF3Fh
0x18001de93  and     edx, 80h
0x18001de99  mov     ecx, r8d
0x18001de9c  mov     r12d, 40h ; '@'
0x18001dea2  and     ecx, 3
0x18001dea5  and     eax, r12d
0x18001dea8  shl     ecx, 2
0x18001deab  or      ecx, eax
0x18001dead  shl     ecx, 2
0x18001deb0  or      ecx, edx
0x18001deb2  lea     ebx, ds:0[rcx*8]
0x18001deb9  test    r8d, r8d
0x18001debc  jnz     short loc_18001DEC3
0x18001debe  mov     eax, r12d
0x18001dec1  jmp     short loc_18001DECD
0x18001dec3  xor     eax, eax
0x18001dec5  cmp     r8d, 2
0x18001dec9  cmovz   eax, r12d
0x18001decd  or      ebx, eax
0x18001decf  mov     ecx, 0C00h
0x18001ded4  mov     eax, ebx
0x18001ded6  and     eax, ecx
0x18001ded8  cmp     eax, ecx
0x18001deda  jnz     short loc_18001DEE1
0x18001dedc  mov     sil, 1
0x18001dedf  jmp     short loc_18001DEE9
0x18001dee1  xor     sil, sil
0x18001dee4  test    r12b, bl
0x18001dee7  jz      short loc_18001DF04
0x18001dee9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Ten2Loc@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc> `wil::Feature<__WilFeatureTraits_Feature_Ten2Loc>::GetImpl(void)'::`2'::impl
0x18001def0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::__private_IsEnabled(wil::ReportingKind)
0x18001def5  test    sil, sil
0x18001def8  jz      short loc_18001DF06
0x18001defa  test    al, al
0x18001defc  jnz     short loc_18001DF06
0x18001defe  btr     ebx, 0Ah
0x18001df02  jmp     short loc_18001DF06
0x18001df04  xor     al, al
0x18001df06  test    r12b, bl
0x18001df09  jz      short loc_18001DF16
0x18001df0b  test    al, al
0x18001df0d  jz      short loc_18001DF16
0x18001df0f  mov     esi, 1
0x18001df14  jmp     short loc_18001DF18
0x18001df16  xor     esi, esi
0x18001df18  mov     eax, [rdi]
0x18001df1a  or      esi, ebx
0x18001df1c  mov     ebx, 180h
0x18001df21  cmp     dword ptr [rsp+58h+arg_0], 0
0x18001df26  mov     edx, eax
0x18001df28  mov     [rdi], eax
0x18001df2a  jz      short loc_18001DF64
0x18001df2c  test    dl, 2
0x18001df2f  jnz     short loc_18001DF64
0x18001df31  mov     eax, esi
0x18001df33  xor     eax, edx
0x18001df35  and     eax, ebx
0x18001df37  xor     eax, edx
0x18001df39  mov     ecx, eax
0x18001df3b  xor     ecx, esi
0x18001df3d  and     ecx, r12d
0x18001df40  xor     ecx, eax
0x18001df42  mov     eax, ecx
0x18001df44  xor     eax, esi
0x18001df46  and     eax, 1
0x18001df49  xor     eax, ecx
0x18001df4b  mov     r8d, eax
0x18001df4e  xor     r8d, esi
0x18001df51  and     r8d, 800h
0x18001df58  xor     r8d, eax
0x18001df5b  or      r8d, 2
0x18001df5f  mov     [rdi], r8d
0x18001df62  jmp     short loc_18001DF67
0x18001df64  mov     r8d, edx
0x18001df67  mov     r9d, edx
0x18001df6a  and     r9d, 4
0x18001df6e  jnz     short loc_18001DF85
0x18001df70  mov     ecx, esi
0x18001df72  xor     ecx, r8d
0x18001df75  and     ecx, 400h
0x18001df7b  xor     ecx, r8d
0x18001df7e  or      ecx, 4
0x18001df81  mov     [rdi], ecx
0x18001df83  jmp     short loc_18001DF88
0x18001df85  mov     ecx, r8d
0x18001df88  mov     eax, edx
0x18001df8a  lock cmpxchg [r14], ecx
0x18001df8f  jnz     short loc_18001DF21
0x18001df91  test    r9d, r9d
0x18001df94  jnz     short loc_18001DFA5
0x18001df96  mov     r8d, ebp
0x18001df99  lea     edx, [r9+3]
0x18001df9d  mov     rcx, r14
0x18001dfa0  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001dfa5  test    byte ptr [rdi], 2
0x18001dfa8  jnz     short loc_18001DFD1
0x18001dfaa  mov     eax, [rdi]
0x18001dfac  xor     eax, esi
0x18001dfae  and     eax, ebx
0x18001dfb0  xor     eax, [rdi]
0x18001dfb2  mov     ecx, eax
0x18001dfb4  xor     ecx, esi
0x18001dfb6  and     ecx, r12d
0x18001dfb9  xor     ecx, eax
0x18001dfbb  mov     edx, ecx
0x18001dfbd  xor     edx, esi
0x18001dfbf  and     edx, 1
0x18001dfc2  xor     edx, ecx
0x18001dfc4  mov     eax, edx
0x18001dfc6  xor     eax, esi
0x18001dfc8  and     eax, 800h
0x18001dfcd  xor     eax, edx
0x18001dfcf  mov     [rdi], eax
0x18001dfd1  mov     rax, rdi
0x18001dfd4  add     rsp, 28h
0x18001dfd8  pop     r14
0x18001dfda  pop     r12
0x18001dfdc  pop     rdi
0x18001dfdd  pop     rsi
0x18001dfde  pop     rbp
0x18001dfdf  pop     rbx
0x18001dfe0  retn
```
