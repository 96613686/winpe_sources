# wil::details::FeatureImpl<__WilFeatureTraits_Feature_53693389>::GetCachedFeatureEnabledState(void)

- ea: `0x1800124a4`
- end: `0x18001261b`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_53693389@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `375`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800131e0`
- `0x1800133b4`

## callees

- `0x180005dd8`
- `0x18000b3d8`
- `0x1800124a4`
- `0x18001b010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_53693389>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
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
  v3 = *(_DWORD *)Feature_53693389__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_53693389__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(53693389, 3, &v14);
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
            ^ ((unsigned __int16)v9
             ^ (unsigned __int16)v8)
            & 0x180
            ^ (v8
             ^ v9
             ^ ((unsigned __int16)v9
              ^ (unsigned __int16)v8)
             & 0x180)
            & 0x40
            | 1)
           ^ ((unsigned __int16)v8
            ^ ((unsigned __int16)(v9 ^ (v9 ^ v8) & 0x180 ^ (v8 ^ v9 ^ (v9 ^ v8) & 0x180) & 0x40) | 1))
           & 0x800
           | 2;
        *(_DWORD *)a2 = v9;
      }
      if ( (v11 & 4) != 0 )
      {
        v12 = v9;
      }
      else
      {
        v12 = v9 ^ ((unsigned __int16)v9 ^ (unsigned __int16)v8) & 0x400 | 4;
        *(_DWORD *)a2 = v12;
      }
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_53693389__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_53693389__descriptor,
        3u,
        v4);
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
0x1800124a4  mov     [rsp+arg_8], rbx
0x1800124a9  mov     [rsp+arg_10], rbp
0x1800124ae  mov     [rsp+arg_0], rcx
0x1800124b3  push    rsi
0x1800124b4  push    rdi
0x1800124b5  push    r15
0x1800124b7  sub     rsp, 20h
0x1800124bb  mov     rsi, cs:Feature_53693389__descriptor
0x1800124c2  mov     rbx, rdx
0x1800124c5  mov     qword ptr [rdx], 0
0x1800124cc  mov     eax, [rsi]
0x1800124ce  mov     [rdx], eax
0x1800124d0  and     eax, 6
0x1800124d3  cmp     al, 6
0x1800124d5  jz      loc_180012605
0x1800124db  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800124e0  mov     ebp, eax
0x1800124e2  mov     dword ptr [rsp+38h+arg_0], 0
0x1800124ea  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800124f1  test    rax, rax
0x1800124f4  jz      short loc_18001250E
0x1800124f6  lea     r8, [rsp+38h+arg_0]
0x1800124fb  mov     edx, 3
0x180012500  mov     ecx, 3334BCDh
0x180012505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001250a  mov     edx, eax
0x18001250c  jmp     short loc_18001251C
0x18001250e  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180012515  test    rax, rax
0x180012518  jnz     short loc_1800124F6
0x18001251a  xor     edx, edx
0x18001251c  mov     r8d, edx
0x18001251f  mov     eax, edx
0x180012521  and     r8d, 0FFFFFF3Fh
0x180012528  and     edx, 80h
0x18001252e  mov     ecx, r8d
0x180012531  mov     r15d, 40h ; '@'
0x180012537  and     ecx, 3
0x18001253a  and     eax, r15d
0x18001253d  shl     ecx, 2
0x180012540  or      ecx, eax
0x180012542  shl     ecx, 2
0x180012545  or      ecx, edx
0x180012547  lea     edi, ds:0[rcx*8]
0x18001254e  test    r8d, r8d
0x180012551  jnz     short loc_180012558
0x180012553  mov     eax, r15d
0x180012556  jmp     short loc_180012562
0x180012558  xor     eax, eax
0x18001255a  cmp     r8d, 2
0x18001255e  cmovz   eax, r15d
0x180012562  or      edi, eax
0x180012564  mov     eax, [rbx]
0x180012566  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001256b  mov     edx, eax
0x18001256d  mov     [rbx], eax
0x18001256f  jz      short loc_18001259F
0x180012571  test    dl, 2
0x180012574  jnz     short loc_18001259F
0x180012576  mov     eax, edi
0x180012578  xor     eax, edx
0x18001257a  and     eax, 180h
0x18001257f  xor     eax, edx
0x180012581  mov     ecx, eax
0x180012583  xor     ecx, edi
0x180012585  and     ecx, r15d
0x180012588  xor     ecx, eax
0x18001258a  or      ecx, 1
0x18001258d  mov     eax, ecx
0x18001258f  xor     eax, edi
0x180012591  and     eax, 800h
0x180012596  xor     eax, ecx
0x180012598  or      eax, 2
0x18001259b  mov     [rbx], eax
0x18001259d  jmp     short loc_1800125A1
0x18001259f  mov     eax, edx
0x1800125a1  mov     r8d, edx
0x1800125a4  and     r8d, 4
0x1800125a8  jnz     short loc_1800125BD
0x1800125aa  mov     ecx, edi
0x1800125ac  xor     ecx, eax
0x1800125ae  and     ecx, 400h
0x1800125b4  xor     ecx, eax
0x1800125b6  or      ecx, 4
0x1800125b9  mov     [rbx], ecx
0x1800125bb  jmp     short loc_1800125BF
0x1800125bd  mov     ecx, eax
0x1800125bf  mov     eax, edx
0x1800125c1  lock cmpxchg [rsi], ecx
0x1800125c5  jnz     short loc_180012566
0x1800125c7  test    r8d, r8d
0x1800125ca  jnz     short loc_1800125DC
0x1800125cc  mov     r8d, ebp
0x1800125cf  mov     edx, 3
0x1800125d4  mov     rcx, rsi
0x1800125d7  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800125dc  test    byte ptr [rbx], 2
0x1800125df  jnz     short loc_180012605
0x1800125e1  mov     eax, [rbx]
0x1800125e3  xor     eax, edi
0x1800125e5  and     eax, 180h
0x1800125ea  xor     eax, [rbx]
0x1800125ec  mov     ecx, eax
0x1800125ee  xor     ecx, edi
0x1800125f0  and     ecx, r15d
0x1800125f3  xor     ecx, eax
0x1800125f5  or      ecx, 1
0x1800125f8  mov     eax, ecx
0x1800125fa  xor     eax, edi
0x1800125fc  and     eax, 800h
0x180012601  xor     eax, ecx
0x180012603  mov     [rbx], eax
0x180012605  mov     rbp, [rsp+38h+arg_10]
0x18001260a  mov     rax, rbx
0x18001260d  mov     rbx, [rsp+38h+arg_8]
0x180012612  add     rsp, 20h
0x180012616  pop     r15
0x180012618  pop     rdi
0x180012619  pop     rsi
0x18001261a  retn
```
