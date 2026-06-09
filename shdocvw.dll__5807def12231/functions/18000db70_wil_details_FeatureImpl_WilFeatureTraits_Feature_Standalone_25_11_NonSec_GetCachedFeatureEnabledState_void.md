# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000db70`
- end: `0x18000dcc8`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `344`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e990`

## callees

- `0x18000d020`
- `0x18000db70`
- `0x1800105e0`
- `0x1800109c4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v17) = 0;
    v5 = v4;
    FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                            (wil::details *)0x2AF34FD,
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
              (volatile signed __int32 *)Feature_Standalone_25_11_NonSec__descriptor,
              v15,
              v14);
    }
    while ( v14 != v12 );
    if ( (v14 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_25_11_NonSec__descriptor,
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
0x18000db70  mov     [rsp+arg_8], rbx
0x18000db75  mov     [rsp+arg_10], rbp
0x18000db7a  mov     [rsp+arg_0], rcx
0x18000db7f  push    rsi
0x18000db80  push    rdi
0x18000db81  push    r15
0x18000db83  sub     rsp, 20h
0x18000db87  mov     rsi, cs:Feature_Standalone_25_11_NonSec__descriptor
0x18000db8e  mov     rbx, rdx
0x18000db91  mov     qword ptr [rdx], 0
0x18000db98  mov     eax, [rsi]
0x18000db9a  mov     [rdx], eax
0x18000db9c  and     eax, 6
0x18000db9f  cmp     al, 6
0x18000dba1  jz      loc_18000DCB2
0x18000dba7  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000dbac  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x18000dbb1  mov     dword ptr [rsp+38h+arg_0], 0
0x18000dbb9  mov     edx, 3; unsigned int
0x18000dbbe  mov     ecx, 2AF34FDh; this
0x18000dbc3  mov     ebp, eax
0x18000dbc5  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18000dbca  mov     r8d, eax
0x18000dbcd  mov     ecx, eax
0x18000dbcf  and     r8d, 0FFFFFF3Fh
0x18000dbd6  and     eax, 80h
0x18000dbdb  mov     edx, r8d
0x18000dbde  mov     r15d, 40h ; '@'
0x18000dbe4  and     edx, 3
0x18000dbe7  and     ecx, r15d
0x18000dbea  shl     edx, 2
0x18000dbed  or      edx, ecx
0x18000dbef  shl     edx, 2
0x18000dbf2  or      edx, eax
0x18000dbf4  lea     edi, ds:0[rdx*8]
0x18000dbfb  test    r8d, r8d
0x18000dbfe  jnz     short loc_18000DC05
0x18000dc00  mov     eax, r15d
0x18000dc03  jmp     short loc_18000DC0F
0x18000dc05  xor     eax, eax
0x18000dc07  cmp     r8d, 2
0x18000dc0b  cmovz   eax, r15d
0x18000dc0f  or      edi, eax
0x18000dc11  mov     eax, [rbx]
0x18000dc13  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000dc18  mov     edx, eax
0x18000dc1a  mov     [rbx], eax
0x18000dc1c  jz      short loc_18000DC4C
0x18000dc1e  test    dl, 2
0x18000dc21  jnz     short loc_18000DC4C
0x18000dc23  mov     eax, edi
0x18000dc25  xor     eax, edx
0x18000dc27  and     eax, 180h
0x18000dc2c  xor     eax, edx
0x18000dc2e  mov     ecx, eax
0x18000dc30  xor     ecx, edi
0x18000dc32  and     ecx, r15d
0x18000dc35  xor     ecx, eax
0x18000dc37  or      ecx, 1
0x18000dc3a  mov     eax, ecx
0x18000dc3c  xor     eax, edi
0x18000dc3e  and     eax, 800h
0x18000dc43  xor     eax, ecx
0x18000dc45  or      eax, 2
0x18000dc48  mov     [rbx], eax
0x18000dc4a  jmp     short loc_18000DC4E
0x18000dc4c  mov     eax, edx
0x18000dc4e  mov     r8d, edx
0x18000dc51  and     r8d, 4
0x18000dc55  jnz     short loc_18000DC6A
0x18000dc57  mov     ecx, edi
0x18000dc59  xor     ecx, eax
0x18000dc5b  and     ecx, 400h
0x18000dc61  xor     ecx, eax
0x18000dc63  or      ecx, 4
0x18000dc66  mov     [rbx], ecx
0x18000dc68  jmp     short loc_18000DC6C
0x18000dc6a  mov     ecx, eax
0x18000dc6c  mov     eax, edx
0x18000dc6e  lock cmpxchg [rsi], ecx
0x18000dc72  jnz     short loc_18000DC13
0x18000dc74  test    r8d, r8d
0x18000dc77  jnz     short loc_18000DC89
0x18000dc79  mov     r8d, ebp
0x18000dc7c  mov     edx, 3
0x18000dc81  mov     rcx, rsi
0x18000dc84  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000dc89  test    byte ptr [rbx], 2
0x18000dc8c  jnz     short loc_18000DCB2
0x18000dc8e  mov     eax, [rbx]
0x18000dc90  xor     eax, edi
0x18000dc92  and     eax, 180h
0x18000dc97  xor     eax, [rbx]
0x18000dc99  mov     ecx, eax
0x18000dc9b  xor     ecx, edi
0x18000dc9d  and     ecx, r15d
0x18000dca0  xor     ecx, eax
0x18000dca2  or      ecx, 1
0x18000dca5  mov     eax, ecx
0x18000dca7  xor     eax, edi
0x18000dca9  and     eax, 800h
0x18000dcae  xor     eax, ecx
0x18000dcb0  mov     [rbx], eax
0x18000dcb2  mov     rbp, [rsp+38h+arg_10]
0x18000dcb7  mov     rax, rbx
0x18000dcba  mov     rbx, [rsp+38h+arg_8]
0x18000dcbf  add     rsp, 20h
0x18000dcc3  pop     r15
0x18000dcc5  pop     rdi
0x18000dcc6  pop     rsi
0x18000dcc7  retn
```
