# wil::details::FeatureImpl<__WilFeatureTraits_Feature_WerHangTraceSignal>::GetCachedFeatureEnabledState(void)

- ea: `0x18001fc50`
- end: `0x18001fe18`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_WerHangTraceSignal@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `456`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800254a0`

## callees

- `0x18000ca74`
- `0x18000e564`
- `0x18001fc50`
- `0x180025404`
- `0x180029010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_WerHangTraceSignal>::GetCachedFeatureEnabledState(
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
  unsigned __int8 IsEnabled; // al
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
  v3 = *(_DWORD *)Feature_WerHangTraceSignal__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_WerHangTraceSignal__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(61439893, 3, &v20);
  }
  else
  {
    v6 = 0;
  }
  v7 = 0;
  if ( (v6 & 0xFFFFFF3F) == 2 )
    v7 = 64;
  v8 = v7 | (8 * (v6 & 0x80 | (4 * (v6 & 0x40 | (4 * (v6 & 3))))));
  if ( (v8 & 0xC00) == 0xC00 )
  {
    v9 = 1;
LABEL_11:
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl'::`2'::impl);
    if ( v9 && !IsEnabled )
      v8 &= ~0x400u;
    goto LABEL_15;
  }
  v9 = 0;
  if ( (v8 & 0x40) != 0 )
    goto LABEL_11;
  IsEnabled = 0;
LABEL_15:
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_WerHangTraceSignal__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_WerHangTraceSignal__descriptor, 3, v4);
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
0x18001fc50  mov     [rsp+arg_0], rcx
0x18001fc55  push    rbx
0x18001fc56  push    rbp
0x18001fc57  push    rsi
0x18001fc58  push    rdi
0x18001fc59  push    r12
0x18001fc5b  push    r14
0x18001fc5d  sub     rsp, 28h
0x18001fc61  mov     r14, cs:Feature_WerHangTraceSignal__descriptor
0x18001fc68  mov     rdi, rdx
0x18001fc6b  mov     qword ptr [rdx], 0
0x18001fc72  mov     eax, [r14]
0x18001fc75  mov     [rdx], eax
0x18001fc77  and     eax, 6
0x18001fc7a  cmp     al, 6
0x18001fc7c  jz      loc_18001FE08
0x18001fc82  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001fc87  mov     ebp, eax
0x18001fc89  mov     dword ptr [rsp+58h+arg_0], 0
0x18001fc91  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001fc98  test    rax, rax
0x18001fc9b  jz      short loc_18001FCB5
0x18001fc9d  lea     r8, [rsp+58h+arg_0]
0x18001fca2  mov     edx, 3
0x18001fca7  mov     ecx, 3A97F95h
0x18001fcac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fcb1  mov     edx, eax
0x18001fcb3  jmp     short loc_18001FCC3
0x18001fcb5  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001fcbc  test    rax, rax
0x18001fcbf  jnz     short loc_18001FC9D
0x18001fcc1  xor     edx, edx
0x18001fcc3  mov     r8d, edx
0x18001fcc6  mov     eax, edx
0x18001fcc8  and     r8d, 0FFFFFF3Fh
0x18001fccf  and     edx, 80h
0x18001fcd5  mov     ecx, r8d
0x18001fcd8  mov     r12d, 40h ; '@'
0x18001fcde  and     ecx, 3
0x18001fce1  and     eax, r12d
0x18001fce4  shl     ecx, 2
0x18001fce7  or      ecx, eax
0x18001fce9  xor     eax, eax
0x18001fceb  shl     ecx, 2
0x18001fcee  or      ecx, edx
0x18001fcf0  lea     ebx, ds:0[rcx*8]
0x18001fcf7  test    r8d, r8d
0x18001fcfa  jz      short loc_18001FD04
0x18001fcfc  cmp     r8d, 2
0x18001fd00  cmovz   eax, r12d
0x18001fd04  or      ebx, eax
0x18001fd06  mov     ecx, 0C00h
0x18001fd0b  mov     eax, ebx
0x18001fd0d  and     eax, ecx
0x18001fd0f  cmp     eax, ecx
0x18001fd11  jnz     short loc_18001FD18
0x18001fd13  mov     sil, 1
0x18001fd16  jmp     short loc_18001FD20
0x18001fd18  xor     sil, sil
0x18001fd1b  test    r12b, bl
0x18001fd1e  jz      short loc_18001FD3B
0x18001fd20  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UxAccOptimization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization> `wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl(void)'::`2'::impl
0x18001fd27  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(wil::ReportingKind)
0x18001fd2c  test    sil, sil
0x18001fd2f  jz      short loc_18001FD3D
0x18001fd31  test    al, al
0x18001fd33  jnz     short loc_18001FD3D
0x18001fd35  btr     ebx, 0Ah
0x18001fd39  jmp     short loc_18001FD3D
0x18001fd3b  xor     al, al
0x18001fd3d  test    r12b, bl
0x18001fd40  jz      short loc_18001FD4D
0x18001fd42  test    al, al
0x18001fd44  jz      short loc_18001FD4D
0x18001fd46  mov     esi, 1
0x18001fd4b  jmp     short loc_18001FD4F
0x18001fd4d  xor     esi, esi
0x18001fd4f  mov     eax, [rdi]
0x18001fd51  or      esi, ebx
0x18001fd53  mov     ebx, 180h
0x18001fd58  cmp     dword ptr [rsp+58h+arg_0], 0
0x18001fd5d  mov     edx, eax
0x18001fd5f  mov     [rdi], eax
0x18001fd61  jz      short loc_18001FD9B
0x18001fd63  test    dl, 2
0x18001fd66  jnz     short loc_18001FD9B
0x18001fd68  mov     eax, esi
0x18001fd6a  xor     eax, edx
0x18001fd6c  and     eax, ebx
0x18001fd6e  xor     eax, edx
0x18001fd70  mov     ecx, eax
0x18001fd72  xor     ecx, esi
0x18001fd74  and     ecx, r12d
0x18001fd77  xor     ecx, eax
0x18001fd79  mov     eax, ecx
0x18001fd7b  xor     eax, esi
0x18001fd7d  and     eax, 1
0x18001fd80  xor     eax, ecx
0x18001fd82  mov     r8d, eax
0x18001fd85  xor     r8d, esi
0x18001fd88  and     r8d, 800h
0x18001fd8f  xor     r8d, eax
0x18001fd92  or      r8d, 2
0x18001fd96  mov     [rdi], r8d
0x18001fd99  jmp     short loc_18001FD9E
0x18001fd9b  mov     r8d, edx
0x18001fd9e  mov     r9d, edx
0x18001fda1  and     r9d, 4
0x18001fda5  jnz     short loc_18001FDBC
0x18001fda7  mov     ecx, esi
0x18001fda9  xor     ecx, r8d
0x18001fdac  and     ecx, 400h
0x18001fdb2  xor     ecx, r8d
0x18001fdb5  or      ecx, 4
0x18001fdb8  mov     [rdi], ecx
0x18001fdba  jmp     short loc_18001FDBF
0x18001fdbc  mov     ecx, r8d
0x18001fdbf  mov     eax, edx
0x18001fdc1  lock cmpxchg [r14], ecx
0x18001fdc6  jnz     short loc_18001FD58
0x18001fdc8  test    r9d, r9d
0x18001fdcb  jnz     short loc_18001FDDC
0x18001fdcd  mov     r8d, ebp
0x18001fdd0  lea     edx, [r9+3]
0x18001fdd4  mov     rcx, r14
0x18001fdd7  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001fddc  test    byte ptr [rdi], 2
0x18001fddf  jnz     short loc_18001FE08
0x18001fde1  mov     eax, [rdi]
0x18001fde3  xor     eax, esi
0x18001fde5  and     eax, ebx
0x18001fde7  xor     eax, [rdi]
0x18001fde9  mov     ecx, eax
0x18001fdeb  xor     ecx, esi
0x18001fded  and     ecx, r12d
0x18001fdf0  xor     ecx, eax
0x18001fdf2  mov     edx, ecx
0x18001fdf4  xor     edx, esi
0x18001fdf6  and     edx, 1
0x18001fdf9  xor     edx, ecx
0x18001fdfb  mov     eax, edx
0x18001fdfd  xor     eax, esi
0x18001fdff  and     eax, 800h
0x18001fe04  xor     eax, edx
0x18001fe06  mov     [rdi], eax
0x18001fe08  mov     rax, rdi
0x18001fe0b  add     rsp, 28h
0x18001fe0f  pop     r14
0x18001fe11  pop     r12
0x18001fe13  pop     rdi
0x18001fe14  pop     rsi
0x18001fe15  pop     rbp
0x18001fe16  pop     rbx
0x18001fe17  retn
```
