# wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceHealth>::GetCachedFeatureEnabledState(void)

- ea: `0x18001dc40`
- end: `0x18001de0d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_DeviceHealth@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024a08`

## callees

- `0x18000ca74`
- `0x18000e564`
- `0x180017690`
- `0x18001dc40`
- `0x180029010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceHealth>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_DeviceHealth__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_DeviceHealth__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(60497802, 3, &v20);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_DeviceHealth__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_DeviceHealth__descriptor, 3, v4);
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
0x18001dc40  mov     [rsp+arg_0], rcx
0x18001dc45  push    rbx
0x18001dc46  push    rbp
0x18001dc47  push    rsi
0x18001dc48  push    rdi
0x18001dc49  push    r12
0x18001dc4b  push    r14
0x18001dc4d  sub     rsp, 28h
0x18001dc51  mov     r14, cs:Feature_DeviceHealth__descriptor
0x18001dc58  mov     rdi, rdx
0x18001dc5b  mov     qword ptr [rdx], 0
0x18001dc62  mov     eax, [r14]
0x18001dc65  mov     [rdx], eax
0x18001dc67  and     eax, 6
0x18001dc6a  cmp     al, 6
0x18001dc6c  jz      loc_18001DDFD
0x18001dc72  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001dc77  mov     ebp, eax
0x18001dc79  mov     dword ptr [rsp+58h+arg_0], 0
0x18001dc81  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001dc88  test    rax, rax
0x18001dc8b  jz      short loc_18001DCA5
0x18001dc8d  lea     r8, [rsp+58h+arg_0]
0x18001dc92  mov     edx, 3
0x18001dc97  mov     ecx, 39B1F8Ah
0x18001dc9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dca1  mov     edx, eax
0x18001dca3  jmp     short loc_18001DCB3
0x18001dca5  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001dcac  test    rax, rax
0x18001dcaf  jnz     short loc_18001DC8D
0x18001dcb1  xor     edx, edx
0x18001dcb3  mov     r8d, edx
0x18001dcb6  mov     eax, edx
0x18001dcb8  and     r8d, 0FFFFFF3Fh
0x18001dcbf  and     edx, 80h
0x18001dcc5  mov     ecx, r8d
0x18001dcc8  mov     r12d, 40h ; '@'
0x18001dcce  and     ecx, 3
0x18001dcd1  and     eax, r12d
0x18001dcd4  shl     ecx, 2
0x18001dcd7  or      ecx, eax
0x18001dcd9  shl     ecx, 2
0x18001dcdc  or      ecx, edx
0x18001dcde  lea     ebx, ds:0[rcx*8]
0x18001dce5  test    r8d, r8d
0x18001dce8  jnz     short loc_18001DCEF
0x18001dcea  mov     eax, r12d
0x18001dced  jmp     short loc_18001DCF9
0x18001dcef  xor     eax, eax
0x18001dcf1  cmp     r8d, 2
0x18001dcf5  cmovz   eax, r12d
0x18001dcf9  or      ebx, eax
0x18001dcfb  mov     ecx, 0C00h
0x18001dd00  mov     eax, ebx
0x18001dd02  and     eax, ecx
0x18001dd04  cmp     eax, ecx
0x18001dd06  jnz     short loc_18001DD0D
0x18001dd08  mov     sil, 1
0x18001dd0b  jmp     short loc_18001DD15
0x18001dd0d  xor     sil, sil
0x18001dd10  test    r12b, bl
0x18001dd13  jz      short loc_18001DD30
0x18001dd15  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestUex12@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestUex12@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12> `wil::Feature<__WilFeatureTraits_Feature_TestUex12>::GetImpl(void)'::`2'::impl
0x18001dd1c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestUex12@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::__private_IsEnabled(wil::ReportingKind)
0x18001dd21  test    sil, sil
0x18001dd24  jz      short loc_18001DD32
0x18001dd26  test    al, al
0x18001dd28  jnz     short loc_18001DD32
0x18001dd2a  btr     ebx, 0Ah
0x18001dd2e  jmp     short loc_18001DD32
0x18001dd30  xor     al, al
0x18001dd32  test    r12b, bl
0x18001dd35  jz      short loc_18001DD42
0x18001dd37  test    al, al
0x18001dd39  jz      short loc_18001DD42
0x18001dd3b  mov     esi, 1
0x18001dd40  jmp     short loc_18001DD44
0x18001dd42  xor     esi, esi
0x18001dd44  mov     eax, [rdi]
0x18001dd46  or      esi, ebx
0x18001dd48  mov     ebx, 180h
0x18001dd4d  cmp     dword ptr [rsp+58h+arg_0], 0
0x18001dd52  mov     edx, eax
0x18001dd54  mov     [rdi], eax
0x18001dd56  jz      short loc_18001DD90
0x18001dd58  test    dl, 2
0x18001dd5b  jnz     short loc_18001DD90
0x18001dd5d  mov     eax, esi
0x18001dd5f  xor     eax, edx
0x18001dd61  and     eax, ebx
0x18001dd63  xor     eax, edx
0x18001dd65  mov     ecx, eax
0x18001dd67  xor     ecx, esi
0x18001dd69  and     ecx, r12d
0x18001dd6c  xor     ecx, eax
0x18001dd6e  mov     eax, ecx
0x18001dd70  xor     eax, esi
0x18001dd72  and     eax, 1
0x18001dd75  xor     eax, ecx
0x18001dd77  mov     r8d, eax
0x18001dd7a  xor     r8d, esi
0x18001dd7d  and     r8d, 800h
0x18001dd84  xor     r8d, eax
0x18001dd87  or      r8d, 2
0x18001dd8b  mov     [rdi], r8d
0x18001dd8e  jmp     short loc_18001DD93
0x18001dd90  mov     r8d, edx
0x18001dd93  mov     r9d, edx
0x18001dd96  and     r9d, 4
0x18001dd9a  jnz     short loc_18001DDB1
0x18001dd9c  mov     ecx, esi
0x18001dd9e  xor     ecx, r8d
0x18001dda1  and     ecx, 400h
0x18001dda7  xor     ecx, r8d
0x18001ddaa  or      ecx, 4
0x18001ddad  mov     [rdi], ecx
0x18001ddaf  jmp     short loc_18001DDB4
0x18001ddb1  mov     ecx, r8d
0x18001ddb4  mov     eax, edx
0x18001ddb6  lock cmpxchg [r14], ecx
0x18001ddbb  jnz     short loc_18001DD4D
0x18001ddbd  test    r9d, r9d
0x18001ddc0  jnz     short loc_18001DDD1
0x18001ddc2  mov     r8d, ebp
0x18001ddc5  lea     edx, [r9+3]
0x18001ddc9  mov     rcx, r14
0x18001ddcc  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001ddd1  test    byte ptr [rdi], 2
0x18001ddd4  jnz     short loc_18001DDFD
0x18001ddd6  mov     eax, [rdi]
0x18001ddd8  xor     eax, esi
0x18001ddda  and     eax, ebx
0x18001dddc  xor     eax, [rdi]
0x18001ddde  mov     ecx, eax
0x18001dde0  xor     ecx, esi
0x18001dde2  and     ecx, r12d
0x18001dde5  xor     ecx, eax
0x18001dde7  mov     edx, ecx
0x18001dde9  xor     edx, esi
0x18001ddeb  and     edx, 1
0x18001ddee  xor     edx, ecx
0x18001ddf0  mov     eax, edx
0x18001ddf2  xor     eax, esi
0x18001ddf4  and     eax, 800h
0x18001ddf9  xor     eax, edx
0x18001ddfb  mov     [rdi], eax
0x18001ddfd  mov     rax, rdi
0x18001de00  add     rsp, 28h
0x18001de04  pop     r14
0x18001de06  pop     r12
0x18001de08  pop     rdi
0x18001de09  pop     rsi
0x18001de0a  pop     rbp
0x18001de0b  pop     rbx
0x18001de0c  retn
```
