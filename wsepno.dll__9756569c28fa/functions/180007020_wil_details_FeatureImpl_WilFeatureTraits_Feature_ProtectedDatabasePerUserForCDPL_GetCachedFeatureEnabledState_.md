# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ProtectedDatabasePerUserForCDPL>::GetCachedFeatureEnabledState(void)

- ea: `0x180007020`
- end: `0x18000718f`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ProtectedDatabasePerUserForCDPL@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `367`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a0e0`

## callees

- `0x180006740`
- `0x180007020`
- `0x18000a780`
- `0x18000f010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ProtectedDatabasePerUserForCDPL>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
  __int64 (__fastcall *v5)(__int64, _QWORD, wil::details **); // rax
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
  v3 = *(_DWORD *)Feature_ProtectedDatabasePerUserForCDPL__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ProtectedDatabasePerUserForCDPL__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, _QWORD, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    v6 = 0;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, _QWORD, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(16372493, 0, &v14);
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
    if ( !v4 )
      LODWORD(v14) = 0;
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
      if ( (v11 & 4) != 0 )
      {
        v12 = v9;
      }
      else
      {
        v12 = v9 ^ ((unsigned __int16)v9 ^ (unsigned __int16)v8) & 0x400 | 4;
        *(_DWORD *)a2 = v12;
      }
      v9 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_ProtectedDatabasePerUserForCDPL__descriptor,
             v12,
             v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_ProtectedDatabasePerUserForCDPL__descriptor,
        0,
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
0x180007020  mov     [rsp+arg_8], rbx
0x180007025  mov     [rsp+arg_10], rbp
0x18000702a  mov     [rsp+arg_0], rcx
0x18000702f  push    rsi
0x180007030  push    rdi
0x180007031  push    r15
0x180007033  sub     rsp, 20h
0x180007037  mov     rsi, cs:Feature_ProtectedDatabasePerUserForCDPL__descriptor
0x18000703e  mov     rbx, rdx
0x180007041  mov     qword ptr [rdx], 0
0x180007048  mov     eax, [rsi]
0x18000704a  mov     [rdx], eax
0x18000704c  and     eax, 6
0x18000704f  cmp     al, 6
0x180007051  jz      loc_180007179
0x180007057  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000705c  mov     ebp, eax
0x18000705e  mov     dword ptr [rsp+38h+arg_0], 0
0x180007066  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000706d  xor     edx, edx
0x18000706f  test    rax, rax
0x180007072  jnz     short loc_180007080
0x180007074  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000707b  test    rax, rax
0x18000707e  jz      short loc_180007091
0x180007080  lea     r8, [rsp+38h+arg_0]
0x180007085  mov     ecx, 0F9D30Dh
0x18000708a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000708f  mov     edx, eax
0x180007091  mov     r8d, edx
0x180007094  mov     eax, edx
0x180007096  and     r8d, 0FFFFFF3Fh
0x18000709d  and     edx, 80h
0x1800070a3  mov     ecx, r8d
0x1800070a6  mov     r15d, 40h ; '@'
0x1800070ac  and     ecx, 3
0x1800070af  and     eax, r15d
0x1800070b2  shl     ecx, 2
0x1800070b5  or      ecx, eax
0x1800070b7  shl     ecx, 2
0x1800070ba  or      ecx, edx
0x1800070bc  lea     edi, ds:0[rcx*8]
0x1800070c3  test    r8d, r8d
0x1800070c6  jnz     short loc_1800070CD
0x1800070c8  mov     eax, r15d
0x1800070cb  jmp     short loc_1800070D7
0x1800070cd  xor     eax, eax
0x1800070cf  cmp     r8d, 2
0x1800070d3  cmovz   eax, r15d
0x1800070d7  or      edi, eax
0x1800070d9  test    ebp, ebp
0x1800070db  jnz     short loc_1800070E1
0x1800070dd  mov     dword ptr [rsp+38h+arg_0], ebp
0x1800070e1  mov     eax, [rbx]
0x1800070e3  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800070e8  mov     edx, eax
0x1800070ea  mov     [rbx], eax
0x1800070ec  jz      short loc_180007118
0x1800070ee  test    dl, 2
0x1800070f1  jnz     short loc_180007118
0x1800070f3  xor     eax, edi
0x1800070f5  and     eax, 180h
0x1800070fa  xor     eax, edx
0x1800070fc  mov     ecx, eax
0x1800070fe  xor     ecx, edi
0x180007100  and     ecx, r15d
0x180007103  xor     ecx, eax
0x180007105  or      ecx, 1
0x180007108  mov     eax, ecx
0x18000710a  xor     eax, edi
0x18000710c  and     eax, 800h
0x180007111  xor     eax, ecx
0x180007113  or      eax, 2
0x180007116  mov     [rbx], eax
0x180007118  mov     r8d, edx
0x18000711b  and     r8d, 4
0x18000711f  jnz     short loc_180007134
0x180007121  mov     ecx, edi
0x180007123  xor     ecx, eax
0x180007125  and     ecx, 400h
0x18000712b  xor     ecx, eax
0x18000712d  or      ecx, 4
0x180007130  mov     [rbx], ecx
0x180007132  jmp     short loc_180007136
0x180007134  mov     ecx, eax
0x180007136  mov     eax, edx
0x180007138  lock cmpxchg [rsi], ecx
0x18000713c  jnz     short loc_1800070E3
0x18000713e  test    r8d, r8d
0x180007141  jnz     short loc_180007150
0x180007143  mov     r8d, ebp
0x180007146  xor     edx, edx
0x180007148  mov     rcx, rsi
0x18000714b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180007150  test    byte ptr [rbx], 2
0x180007153  jnz     short loc_180007179
0x180007155  mov     eax, [rbx]
0x180007157  xor     eax, edi
0x180007159  and     eax, 180h
0x18000715e  xor     eax, [rbx]
0x180007160  mov     ecx, eax
0x180007162  xor     ecx, edi
0x180007164  and     ecx, r15d
0x180007167  xor     ecx, eax
0x180007169  or      ecx, 1
0x18000716c  mov     eax, ecx
0x18000716e  xor     eax, edi
0x180007170  and     eax, 800h
0x180007175  xor     eax, ecx
0x180007177  mov     [rbx], eax
0x180007179  mov     rbp, [rsp+38h+arg_10]
0x18000717e  mov     rax, rbx
0x180007181  mov     rbx, [rsp+38h+arg_8]
0x180007186  add     rsp, 20h
0x18000718a  pop     r15
0x18000718c  pop     rdi
0x18000718d  pop     rsi
0x18000718e  retn
```
