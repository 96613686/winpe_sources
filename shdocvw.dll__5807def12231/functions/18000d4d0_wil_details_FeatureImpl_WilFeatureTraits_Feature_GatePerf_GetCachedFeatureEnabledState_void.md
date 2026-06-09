# wil::details::FeatureImpl<__WilFeatureTraits_Feature_GatePerf>::GetCachedFeatureEnabledState(void)

- ea: `0x18000d4d0`
- end: `0x18000d628`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_GatePerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `344`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022d98`

## callees

- `0x18000d020`
- `0x18000d4d0`
- `0x1800105e0`
- `0x1800109c4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_GatePerf>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_GatePerf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_GatePerf__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v17) = 0;
    v5 = v4;
    FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                            (wil::details *)0x33B9B30,
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
      v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_GatePerf__descriptor, v15, v14);
    }
    while ( v14 != v12 );
    if ( (v14 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_GatePerf__descriptor,
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
0x18000d4d0  mov     [rsp+arg_8], rbx
0x18000d4d5  mov     [rsp+arg_10], rbp
0x18000d4da  mov     [rsp+arg_0], rcx
0x18000d4df  push    rsi
0x18000d4e0  push    rdi
0x18000d4e1  push    r15
0x18000d4e3  sub     rsp, 20h
0x18000d4e7  mov     rsi, cs:Feature_GatePerf__descriptor
0x18000d4ee  mov     rbx, rdx
0x18000d4f1  mov     qword ptr [rdx], 0
0x18000d4f8  mov     eax, [rsi]
0x18000d4fa  mov     [rdx], eax
0x18000d4fc  and     eax, 6
0x18000d4ff  cmp     al, 6
0x18000d501  jz      loc_18000D612
0x18000d507  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000d50c  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x18000d511  mov     dword ptr [rsp+38h+arg_0], 0
0x18000d519  mov     edx, 3; unsigned int
0x18000d51e  mov     ecx, 33B9B30h; this
0x18000d523  mov     ebp, eax
0x18000d525  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18000d52a  mov     r8d, eax
0x18000d52d  mov     ecx, eax
0x18000d52f  and     r8d, 0FFFFFF3Fh
0x18000d536  and     eax, 80h
0x18000d53b  mov     edx, r8d
0x18000d53e  mov     r15d, 40h ; '@'
0x18000d544  and     edx, 3
0x18000d547  and     ecx, r15d
0x18000d54a  shl     edx, 2
0x18000d54d  or      edx, ecx
0x18000d54f  shl     edx, 2
0x18000d552  or      edx, eax
0x18000d554  lea     edi, ds:0[rdx*8]
0x18000d55b  test    r8d, r8d
0x18000d55e  jnz     short loc_18000D565
0x18000d560  mov     eax, r15d
0x18000d563  jmp     short loc_18000D56F
0x18000d565  xor     eax, eax
0x18000d567  cmp     r8d, 2
0x18000d56b  cmovz   eax, r15d
0x18000d56f  or      edi, eax
0x18000d571  mov     eax, [rbx]
0x18000d573  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000d578  mov     edx, eax
0x18000d57a  mov     [rbx], eax
0x18000d57c  jz      short loc_18000D5AC
0x18000d57e  test    dl, 2
0x18000d581  jnz     short loc_18000D5AC
0x18000d583  mov     eax, edi
0x18000d585  xor     eax, edx
0x18000d587  and     eax, 180h
0x18000d58c  xor     eax, edx
0x18000d58e  mov     ecx, eax
0x18000d590  xor     ecx, edi
0x18000d592  and     ecx, r15d
0x18000d595  xor     ecx, eax
0x18000d597  or      ecx, 1
0x18000d59a  mov     eax, ecx
0x18000d59c  xor     eax, edi
0x18000d59e  and     eax, 800h
0x18000d5a3  xor     eax, ecx
0x18000d5a5  or      eax, 2
0x18000d5a8  mov     [rbx], eax
0x18000d5aa  jmp     short loc_18000D5AE
0x18000d5ac  mov     eax, edx
0x18000d5ae  mov     r8d, edx
0x18000d5b1  and     r8d, 4
0x18000d5b5  jnz     short loc_18000D5CA
0x18000d5b7  mov     ecx, edi
0x18000d5b9  xor     ecx, eax
0x18000d5bb  and     ecx, 400h
0x18000d5c1  xor     ecx, eax
0x18000d5c3  or      ecx, 4
0x18000d5c6  mov     [rbx], ecx
0x18000d5c8  jmp     short loc_18000D5CC
0x18000d5ca  mov     ecx, eax
0x18000d5cc  mov     eax, edx
0x18000d5ce  lock cmpxchg [rsi], ecx
0x18000d5d2  jnz     short loc_18000D573
0x18000d5d4  test    r8d, r8d
0x18000d5d7  jnz     short loc_18000D5E9
0x18000d5d9  mov     r8d, ebp
0x18000d5dc  mov     edx, 3
0x18000d5e1  mov     rcx, rsi
0x18000d5e4  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000d5e9  test    byte ptr [rbx], 2
0x18000d5ec  jnz     short loc_18000D612
0x18000d5ee  mov     eax, [rbx]
0x18000d5f0  xor     eax, edi
0x18000d5f2  and     eax, 180h
0x18000d5f7  xor     eax, [rbx]
0x18000d5f9  mov     ecx, eax
0x18000d5fb  xor     ecx, edi
0x18000d5fd  and     ecx, r15d
0x18000d600  xor     ecx, eax
0x18000d602  or      ecx, 1
0x18000d605  mov     eax, ecx
0x18000d607  xor     eax, edi
0x18000d609  and     eax, 800h
0x18000d60e  xor     eax, ecx
0x18000d610  mov     [rbx], eax
0x18000d612  mov     rbp, [rsp+38h+arg_10]
0x18000d617  mov     rax, rbx
0x18000d61a  mov     rbx, [rsp+38h+arg_8]
0x18000d61f  add     rsp, 20h
0x18000d623  pop     r15
0x18000d625  pop     rdi
0x18000d626  pop     rsi
0x18000d627  retn
```
