# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000dcd0`
- end: `0x18000de28`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `344`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000eae4`

## callees

- `0x18000d020`
- `0x18000dcd0`
- `0x1800105e0`
- `0x1800109c4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v17) = 0;
    v5 = v4;
    FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                            (wil::details *)0x37E286C,
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
              (volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor,
              v15,
              v14);
    }
    while ( v14 != v12 );
    if ( (v14 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor,
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
0x18000dcd0  mov     [rsp+arg_8], rbx
0x18000dcd5  mov     [rsp+arg_10], rbp
0x18000dcda  mov     [rsp+arg_0], rcx
0x18000dcdf  push    rsi
0x18000dce0  push    rdi
0x18000dce1  push    r15
0x18000dce3  sub     rsp, 20h
0x18000dce7  mov     rsi, cs:Feature_Standalone_26_01_NonSec__descriptor
0x18000dcee  mov     rbx, rdx
0x18000dcf1  mov     qword ptr [rdx], 0
0x18000dcf8  mov     eax, [rsi]
0x18000dcfa  mov     [rdx], eax
0x18000dcfc  and     eax, 6
0x18000dcff  cmp     al, 6
0x18000dd01  jz      loc_18000DE12
0x18000dd07  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000dd0c  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x18000dd11  mov     dword ptr [rsp+38h+arg_0], 0
0x18000dd19  mov     edx, 3; unsigned int
0x18000dd1e  mov     ecx, 37E286Ch; this
0x18000dd23  mov     ebp, eax
0x18000dd25  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18000dd2a  mov     r8d, eax
0x18000dd2d  mov     ecx, eax
0x18000dd2f  and     r8d, 0FFFFFF3Fh
0x18000dd36  and     eax, 80h
0x18000dd3b  mov     edx, r8d
0x18000dd3e  mov     r15d, 40h ; '@'
0x18000dd44  and     edx, 3
0x18000dd47  and     ecx, r15d
0x18000dd4a  shl     edx, 2
0x18000dd4d  or      edx, ecx
0x18000dd4f  shl     edx, 2
0x18000dd52  or      edx, eax
0x18000dd54  lea     edi, ds:0[rdx*8]
0x18000dd5b  test    r8d, r8d
0x18000dd5e  jnz     short loc_18000DD65
0x18000dd60  mov     eax, r15d
0x18000dd63  jmp     short loc_18000DD6F
0x18000dd65  xor     eax, eax
0x18000dd67  cmp     r8d, 2
0x18000dd6b  cmovz   eax, r15d
0x18000dd6f  or      edi, eax
0x18000dd71  mov     eax, [rbx]
0x18000dd73  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000dd78  mov     edx, eax
0x18000dd7a  mov     [rbx], eax
0x18000dd7c  jz      short loc_18000DDAC
0x18000dd7e  test    dl, 2
0x18000dd81  jnz     short loc_18000DDAC
0x18000dd83  mov     eax, edi
0x18000dd85  xor     eax, edx
0x18000dd87  and     eax, 180h
0x18000dd8c  xor     eax, edx
0x18000dd8e  mov     ecx, eax
0x18000dd90  xor     ecx, edi
0x18000dd92  and     ecx, r15d
0x18000dd95  xor     ecx, eax
0x18000dd97  or      ecx, 1
0x18000dd9a  mov     eax, ecx
0x18000dd9c  xor     eax, edi
0x18000dd9e  and     eax, 800h
0x18000dda3  xor     eax, ecx
0x18000dda5  or      eax, 2
0x18000dda8  mov     [rbx], eax
0x18000ddaa  jmp     short loc_18000DDAE
0x18000ddac  mov     eax, edx
0x18000ddae  mov     r8d, edx
0x18000ddb1  and     r8d, 4
0x18000ddb5  jnz     short loc_18000DDCA
0x18000ddb7  mov     ecx, edi
0x18000ddb9  xor     ecx, eax
0x18000ddbb  and     ecx, 400h
0x18000ddc1  xor     ecx, eax
0x18000ddc3  or      ecx, 4
0x18000ddc6  mov     [rbx], ecx
0x18000ddc8  jmp     short loc_18000DDCC
0x18000ddca  mov     ecx, eax
0x18000ddcc  mov     eax, edx
0x18000ddce  lock cmpxchg [rsi], ecx
0x18000ddd2  jnz     short loc_18000DD73
0x18000ddd4  test    r8d, r8d
0x18000ddd7  jnz     short loc_18000DDE9
0x18000ddd9  mov     r8d, ebp
0x18000dddc  mov     edx, 3
0x18000dde1  mov     rcx, rsi
0x18000dde4  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000dde9  test    byte ptr [rbx], 2
0x18000ddec  jnz     short loc_18000DE12
0x18000ddee  mov     eax, [rbx]
0x18000ddf0  xor     eax, edi
0x18000ddf2  and     eax, 180h
0x18000ddf7  xor     eax, [rbx]
0x18000ddf9  mov     ecx, eax
0x18000ddfb  xor     ecx, edi
0x18000ddfd  and     ecx, r15d
0x18000de00  xor     ecx, eax
0x18000de02  or      ecx, 1
0x18000de05  mov     eax, ecx
0x18000de07  xor     eax, edi
0x18000de09  and     eax, 800h
0x18000de0e  xor     eax, ecx
0x18000de10  mov     [rbx], eax
0x18000de12  mov     rbp, [rsp+38h+arg_10]
0x18000de17  mov     rax, rbx
0x18000de1a  mov     rbx, [rsp+38h+arg_8]
0x18000de1f  add     rsp, 20h
0x18000de23  pop     r15
0x18000de25  pop     rdi
0x18000de26  pop     rsi
0x18000de27  retn
```
