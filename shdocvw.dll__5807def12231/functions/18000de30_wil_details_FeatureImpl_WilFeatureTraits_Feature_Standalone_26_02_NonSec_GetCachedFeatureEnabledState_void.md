# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000de30`
- end: `0x18000df88`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `344`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e83c`

## callees

- `0x18000d020`
- `0x18000de30`
- `0x1800105e0`
- `0x1800109c4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  int v5; // ebp
  int *v6; // r9
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  unsigned int v8; // r8d
  int v9; // edi
  int v10; // eax
  int v11; // edi
  int v12; // eax
  bool v13; // zf
  signed __int32 v14; // edx
  signed __int32 v15; // ecx
  wil::details *v17; // [rsp+40h] [rbp+8h] BYREF

  v17 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v17) = 0;
    v5 = v4;
    FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                            (wil::details *)0x37E287E,
                            3u,
                            (enum FEATURE_CHANGE_TIME)&v17,
                            v6);
    v8 = FeatureEnabledState & 0xFFFFFF3F;
    v9 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
    if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
    {
      v10 = 0;
      if ( v8 == 2 )
        v10 = 64;
    }
    else
    {
      v10 = 64;
    }
    v11 = v10 | v9;
    v12 = *(_DWORD *)a2;
    do
    {
      v13 = (_DWORD)v17 == 0;
      v14 = v12;
      *(_DWORD *)a2 = v12;
      if ( !v13 && (v12 & 2) == 0 )
      {
        v12 = (v12
             ^ ((unsigned __int16)v12
              ^ (unsigned __int16)v11)
             & 0x180
             ^ (v11
              ^ v12
              ^ ((unsigned __int16)v12
               ^ (unsigned __int16)v11)
              & 0x180)
             & 0x40
             | 1)
            ^ ((unsigned __int16)v11
             ^ ((unsigned __int16)(v12 ^ (v12 ^ v11) & 0x180 ^ (v11 ^ v12 ^ (v12 ^ v11) & 0x180) & 0x40) | 1))
            & 0x800
            | 2;
        *(_DWORD *)a2 = v12;
      }
      if ( (v14 & 4) != 0 )
      {
        v15 = v12;
      }
      else
      {
        v15 = v12 ^ ((unsigned __int16)v12 ^ (unsigned __int16)v11) & 0x400 | 4;
        *(_DWORD *)a2 = v15;
      }
      v12 = _InterlockedCompareExchange(
              (volatile signed __int32 *)Feature_Standalone_26_02_NonSec__descriptor,
              v15,
              v14);
    }
    while ( v14 != v12 );
    if ( (v14 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_26_02_NonSec__descriptor,
        3,
        v5);
    if ( (*(_BYTE *)a2 & 2) == 0 )
      *(_DWORD *)a2 = (*(_DWORD *)a2
                     ^ ((unsigned __int16)v11
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180
                     ^ (v11
                      ^ *(_DWORD *)a2
                      ^ ((unsigned __int16)v11
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180)
                     & 0x40
                     | 1)
                    ^ ((unsigned __int16)v11
                     ^ (*(_WORD *)a2
                      ^ ((unsigned __int16)v11
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180
                      ^ ((unsigned __int16)v11
                       ^ *(_WORD *)a2
                       ^ ((unsigned __int16)v11
                        ^ (unsigned __int16)*(_DWORD *)a2)
                       & 0x180)
                      & 0x40
                      | 1))
                    & 0x800;
  }
  return a2;
}

```

## disassembly

```asm
0x18000de30  mov     [rsp+arg_8], rbx
0x18000de35  mov     [rsp+arg_10], rbp
0x18000de3a  mov     [rsp+arg_0], rcx
0x18000de3f  push    rsi
0x18000de40  push    rdi
0x18000de41  push    r15
0x18000de43  sub     rsp, 20h
0x18000de47  mov     rsi, cs:Feature_Standalone_26_02_NonSec__descriptor
0x18000de4e  mov     rbx, rdx
0x18000de51  mov     qword ptr [rdx], 0
0x18000de58  mov     eax, [rsi]
0x18000de5a  mov     [rdx], eax
0x18000de5c  and     eax, 6
0x18000de5f  cmp     al, 6
0x18000de61  jz      loc_18000DF72
0x18000de67  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000de6c  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x18000de71  mov     dword ptr [rsp+38h+arg_0], 0
0x18000de79  mov     edx, 3; unsigned int
0x18000de7e  mov     ecx, 37E287Eh; this
0x18000de83  mov     ebp, eax
0x18000de85  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18000de8a  mov     r8d, eax
0x18000de8d  mov     ecx, eax
0x18000de8f  and     r8d, 0FFFFFF3Fh
0x18000de96  and     eax, 80h
0x18000de9b  mov     edx, r8d
0x18000de9e  mov     r15d, 40h ; '@'
0x18000dea4  and     edx, 3
0x18000dea7  and     ecx, r15d
0x18000deaa  shl     edx, 2
0x18000dead  or      edx, ecx
0x18000deaf  shl     edx, 2
0x18000deb2  or      edx, eax
0x18000deb4  lea     edi, ds:0[rdx*8]
0x18000debb  test    r8d, r8d
0x18000debe  jnz     short loc_18000DEC5
0x18000dec0  mov     eax, r15d
0x18000dec3  jmp     short loc_18000DECF
0x18000dec5  xor     eax, eax
0x18000dec7  cmp     r8d, 2
0x18000decb  cmovz   eax, r15d
0x18000decf  or      edi, eax
0x18000ded1  mov     eax, [rbx]
0x18000ded3  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000ded8  mov     edx, eax
0x18000deda  mov     [rbx], eax
0x18000dedc  jz      short loc_18000DF0C
0x18000dede  test    dl, 2
0x18000dee1  jnz     short loc_18000DF0C
0x18000dee3  mov     eax, edi
0x18000dee5  xor     eax, edx
0x18000dee7  and     eax, 180h
0x18000deec  xor     eax, edx
0x18000deee  mov     ecx, eax
0x18000def0  xor     ecx, edi
0x18000def2  and     ecx, r15d
0x18000def5  xor     ecx, eax
0x18000def7  or      ecx, 1
0x18000defa  mov     eax, ecx
0x18000defc  xor     eax, edi
0x18000defe  and     eax, 800h
0x18000df03  xor     eax, ecx
0x18000df05  or      eax, 2
0x18000df08  mov     [rbx], eax
0x18000df0a  jmp     short loc_18000DF0E
0x18000df0c  mov     eax, edx
0x18000df0e  mov     r8d, edx
0x18000df11  and     r8d, 4
0x18000df15  jnz     short loc_18000DF2A
0x18000df17  mov     ecx, edi
0x18000df19  xor     ecx, eax
0x18000df1b  and     ecx, 400h
0x18000df21  xor     ecx, eax
0x18000df23  or      ecx, 4
0x18000df26  mov     [rbx], ecx
0x18000df28  jmp     short loc_18000DF2C
0x18000df2a  mov     ecx, eax
0x18000df2c  mov     eax, edx
0x18000df2e  lock cmpxchg [rsi], ecx
0x18000df32  jnz     short loc_18000DED3
0x18000df34  test    r8d, r8d
0x18000df37  jnz     short loc_18000DF49
0x18000df39  mov     r8d, ebp
0x18000df3c  mov     edx, 3
0x18000df41  mov     rcx, rsi
0x18000df44  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000df49  test    byte ptr [rbx], 2
0x18000df4c  jnz     short loc_18000DF72
0x18000df4e  mov     eax, [rbx]
0x18000df50  xor     eax, edi
0x18000df52  and     eax, 180h
0x18000df57  xor     eax, [rbx]
0x18000df59  mov     ecx, eax
0x18000df5b  xor     ecx, edi
0x18000df5d  and     ecx, r15d
0x18000df60  xor     ecx, eax
0x18000df62  or      ecx, 1
0x18000df65  mov     eax, ecx
0x18000df67  xor     eax, edi
0x18000df69  and     eax, 800h
0x18000df6e  xor     eax, ecx
0x18000df70  mov     [rbx], eax
0x18000df72  mov     rbp, [rsp+38h+arg_10]
0x18000df77  mov     rax, rbx
0x18000df7a  mov     rbx, [rsp+38h+arg_8]
0x18000df7f  add     rsp, 20h
0x18000df83  pop     r15
0x18000df85  pop     rdi
0x18000df86  pop     rsi
0x18000df87  retn
```
