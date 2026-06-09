# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180017548`
- end: `0x1800176b5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017fc8`

## callees

- `0x180005cf8`
- `0x180009548`
- `0x180017548`
- `0x180033010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
  __int64 (__fastcall *v5)(__int64, __int64, wil::details **); // rax
  int v6; // edx
  int v7; // eax
  int v8; // edi
  int v9; // eax
  bool v10; // zf
  signed __int32 v11; // edx
  signed __int32 v12; // ecx
  wil::details *v14; // [rsp+40h] [rbp+8h] BYREF

  v14 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(58599532, 3, &v14);
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
    v9 = *(_DWORD *)a2;
    do
    {
      v10 = (_DWORD)v14 == 0;
      v11 = v9;
      *(_DWORD *)a2 = v9;
      if ( !v10 && (v9 & 2) == 0 )
      {
        v9 = (v9
            ^ ((unsigned __int16)v8
             ^ (unsigned __int16)v9)
            & 0x180
            ^ (v8
             ^ v9
             ^ ((unsigned __int16)v8
              ^ (unsigned __int16)v9)
             & 0x180)
            & 0x40
            | 1)
           ^ ((unsigned __int16)v8
            ^ ((unsigned __int16)(v9 ^ (v8 ^ v9) & 0x180 ^ (v8 ^ v9 ^ (v8 ^ v9) & 0x180) & 0x40) | 1))
           & 0x800
           | 2;
        *(_DWORD *)a2 = v9;
      }
      v12 = v9;
      if ( (v11 & 4) == 0 )
      {
        v12 = v9 ^ ((unsigned __int16)v8 ^ (unsigned __int16)v9) & 0x400 | 4;
        *(_DWORD *)a2 = v12;
      }
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_26_01_NonSec__descriptor, 3, v4);
    if ( (*(_BYTE *)a2 & 2) == 0 )
      *(_DWORD *)a2 = (*(_DWORD *)a2
                     ^ ((unsigned __int16)v8
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180
                     ^ (v8
                      ^ *(_DWORD *)a2
                      ^ ((unsigned __int16)v8
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180)
                     & 0x40
                     | 1)
                    ^ ((unsigned __int16)v8
                     ^ (*(_WORD *)a2
                      ^ ((unsigned __int16)v8
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180
                      ^ ((unsigned __int16)v8
                       ^ *(_WORD *)a2
                       ^ ((unsigned __int16)v8
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
0x180017548  mov     [rsp+arg_8], rbx
0x18001754d  mov     [rsp+arg_10], rbp
0x180017552  mov     [rsp+arg_0], rcx
0x180017557  push    rsi
0x180017558  push    rdi
0x180017559  push    r15
0x18001755b  sub     rsp, 20h
0x18001755f  mov     rsi, cs:Feature_Standalone_26_01_NonSec__descriptor
0x180017566  mov     rbx, rdx
0x180017569  mov     qword ptr [rdx], 0
0x180017570  mov     eax, [rsi]
0x180017572  mov     [rdx], eax
0x180017574  and     eax, 6
0x180017577  cmp     al, 6
0x180017579  jz      loc_18001769F
0x18001757f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180017584  mov     ebp, eax
0x180017586  mov     dword ptr [rsp+38h+arg_0], 0
0x18001758e  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180017595  test    rax, rax
0x180017598  jz      short loc_1800175B2
0x18001759a  lea     r8, [rsp+38h+arg_0]
0x18001759f  mov     edx, 3
0x1800175a4  mov     ecx, 37E286Ch
0x1800175a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175ae  mov     edx, eax
0x1800175b0  jmp     short loc_1800175C0
0x1800175b2  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1800175b9  test    rax, rax
0x1800175bc  jnz     short loc_18001759A
0x1800175be  xor     edx, edx
0x1800175c0  mov     r8d, edx
0x1800175c3  mov     eax, edx
0x1800175c5  and     r8d, 0FFFFFF3Fh
0x1800175cc  and     edx, 80h
0x1800175d2  mov     ecx, r8d
0x1800175d5  mov     r15d, 40h ; '@'
0x1800175db  and     ecx, 3
0x1800175de  and     eax, r15d
0x1800175e1  shl     ecx, 2
0x1800175e4  or      ecx, eax
0x1800175e6  shl     ecx, 2
0x1800175e9  or      ecx, edx
0x1800175eb  lea     edi, ds:0[rcx*8]
0x1800175f2  test    r8d, r8d
0x1800175f5  jnz     short loc_1800175FC
0x1800175f7  mov     eax, r15d
0x1800175fa  jmp     short loc_180017606
0x1800175fc  xor     eax, eax
0x1800175fe  cmp     r8d, 2
0x180017602  cmovz   eax, r15d
0x180017606  or      edi, eax
0x180017608  mov     eax, [rbx]
0x18001760a  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001760f  mov     edx, eax
0x180017611  mov     [rbx], eax
0x180017613  jz      short loc_18001763F
0x180017615  test    dl, 2
0x180017618  jnz     short loc_18001763F
0x18001761a  xor     eax, edi
0x18001761c  and     eax, 180h
0x180017621  xor     eax, edx
0x180017623  mov     ecx, eax
0x180017625  xor     ecx, edi
0x180017627  and     ecx, r15d
0x18001762a  xor     ecx, eax
0x18001762c  or      ecx, 1
0x18001762f  mov     eax, ecx
0x180017631  xor     eax, edi
0x180017633  and     eax, 800h
0x180017638  xor     eax, ecx
0x18001763a  or      eax, 2
0x18001763d  mov     [rbx], eax
0x18001763f  mov     r8d, edx
0x180017642  mov     ecx, eax
0x180017644  and     r8d, 4
0x180017648  jnz     short loc_180017659
0x18001764a  xor     ecx, edi
0x18001764c  and     ecx, 400h
0x180017652  xor     ecx, eax
0x180017654  or      ecx, 4
0x180017657  mov     [rbx], ecx
0x180017659  mov     eax, edx
0x18001765b  lock cmpxchg [rsi], ecx
0x18001765f  jnz     short loc_18001760A
0x180017661  test    r8d, r8d
0x180017664  jnz     short loc_180017676
0x180017666  mov     r8d, ebp
0x180017669  mov     edx, 3
0x18001766e  mov     rcx, rsi
0x180017671  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180017676  test    byte ptr [rbx], 2
0x180017679  jnz     short loc_18001769F
0x18001767b  mov     eax, [rbx]
0x18001767d  xor     eax, edi
0x18001767f  and     eax, 180h
0x180017684  xor     eax, [rbx]
0x180017686  mov     ecx, eax
0x180017688  xor     ecx, edi
0x18001768a  and     ecx, r15d
0x18001768d  xor     ecx, eax
0x18001768f  or      ecx, 1
0x180017692  mov     eax, ecx
0x180017694  xor     eax, edi
0x180017696  and     eax, 800h
0x18001769b  xor     eax, ecx
0x18001769d  mov     [rbx], eax
0x18001769f  mov     rbp, [rsp+38h+arg_10]
0x1800176a4  mov     rax, rbx
0x1800176a7  mov     rbx, [rsp+38h+arg_8]
0x1800176ac  add     rsp, 20h
0x1800176b0  pop     r15
0x1800176b2  pop     rdi
0x1800176b3  pop     rsi
0x1800176b4  retn
```
