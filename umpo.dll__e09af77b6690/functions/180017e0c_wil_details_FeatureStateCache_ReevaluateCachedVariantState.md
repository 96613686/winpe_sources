# wil_details_FeatureStateCache_ReevaluateCachedVariantState

- ea: `0x180017e0c`
- end: `0x180017f06`
- name: `wil_details_FeatureStateCache_ReevaluateCachedVariantState`
- size: `250`
- prototype: `unsigned __int64 __fastcall(__int64, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017d54`

## callees

- `0x180017e0c`
- `0x180017f0c`
- `0x180019010`

## pseudocode

```c
unsigned __int64 __fastcall wil_details_FeatureStateCache_ReevaluateCachedVariantState(
        __int64 a1,
        unsigned __int64 a2,
        __int64 a3)
{
  unsigned int v3; // esi
  unsigned __int64 v4; // rdi
  unsigned int v5; // ebx
  __int64 CurrentVariantState; // rax
  int v7; // ecx
  unsigned int v8; // r9d
  unsigned int v9; // r8d
  unsigned __int64 v10; // rdi
  signed __int64 v11; // rax
  signed __int64 v12; // rtt
  signed __int64 v14; // [rsp+48h] [rbp+10h]
  int v15; // [rsp+50h] [rbp+18h] BYREF
  int v16; // [rsp+54h] [rbp+1Ch]
  __int64 v17; // [rsp+58h] [rbp+20h]

  v16 = HIDWORD(a3);
  v3 = 0;
  v15 = 0;
  v4 = HIDWORD(a2);
  v5 = a2;
  if ( g_wil_details_ensureSubscribedToFeatureConfigurationChanges )
    v3 = g_wil_details_ensureSubscribedToFeatureConfigurationChanges();
  CurrentVariantState = wil_details_GetCurrentVariantState(a1, &v15);
  v7 = CurrentVariantState;
  v17 = CurrentVariantState;
  while ( 1 )
  {
    if ( (v5 & 8) != 0 )
    {
      v8 = v4;
      v9 = v5;
    }
    else
    {
      v8 = HIDWORD(v17);
      v9 = (v15 != 0 ? 8 : 0) | v5 & 0xFFFC07F7 | v7 & 0x3F800;
    }
    if ( (v5 & 4) == 0 )
      v9 = v7 & 0x400 | v9 & 0xFFFFFBFF | 4;
    v14 = __PAIR64__(v4, v5);
    v10 = __PAIR64__(v8, v9);
    v12 = v14;
    v11 = _InterlockedCompareExchange64(
            &Feature_SmartSuspend_Thresholds__private_featureState,
            __SPAIR64__(v8, v9),
            v14);
    if ( v12 == v11 )
      break;
    v5 = v11;
    LODWORD(v4) = HIDWORD(v11);
  }
  if ( (v5 & 4) == 0 && g_wil_details_subscribeFeatureStateCacheToConfigurationChanges )
    g_wil_details_subscribeFeatureStateCacheToConfigurationChanges(
      &Feature_SmartSuspend_Thresholds__private_featureState,
      3,
      v3);
  return v10;
}

```

## disassembly

```asm
0x180017e0c  mov     [rsp+arg_10], r8
0x180017e11  mov     [rsp+arg_0], rcx
0x180017e16  push    rbx
0x180017e17  push    rsi
0x180017e18  push    rdi
0x180017e19  sub     rsp, 20h
0x180017e1d  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x180017e24  xor     esi, esi
0x180017e26  mov     rdi, rdx
0x180017e29  mov     dword ptr [rsp+38h+arg_10], esi
0x180017e2d  shr     rdi, 20h
0x180017e31  mov     rbx, rdx
0x180017e34  test    rax, rax
0x180017e37  jz      short loc_180017E40
0x180017e39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e3e  mov     esi, eax
0x180017e40  lea     rdx, [rsp+38h+arg_10]
0x180017e45  call    wil_details_GetCurrentVariantState
0x180017e4a  mov     rcx, rax
0x180017e4d  mov     [rsp+38h+arg_18], rax
0x180017e52  test    bl, 8
0x180017e55  jnz     short loc_180017E84
0x180017e57  mov     r9d, dword ptr [rsp+38h+arg_18+4]
0x180017e5c  mov     r8d, ecx
0x180017e5f  and     r8d, 3F800h
0x180017e66  mov     eax, ebx
0x180017e68  and     eax, 0FFFC07FFh
0x180017e6d  or      r8d, eax
0x180017e70  mov     eax, dword ptr [rsp+38h+arg_10]
0x180017e74  neg     eax
0x180017e76  sbb     edx, edx
0x180017e78  and     r8d, 0FFFFFFF7h
0x180017e7c  and     edx, 8
0x180017e7f  or      r8d, edx
0x180017e82  jmp     short loc_180017E8A
0x180017e84  mov     r9d, edi
0x180017e87  mov     r8d, ebx
0x180017e8a  test    bl, 4
0x180017e8d  jnz     short loc_180017EA2
0x180017e8f  btr     r8d, 0Ah
0x180017e94  mov     eax, ecx
0x180017e96  and     eax, 400h
0x180017e9b  or      r8d, eax
0x180017e9e  or      r8d, 4
0x180017ea2  mov     dword ptr [rsp+38h+arg_8+4], edi
0x180017ea6  mov     dword ptr [rsp+38h+arg_8], ebx
0x180017eaa  mov     rax, [rsp+38h+arg_8]
0x180017eaf  mov     dword ptr [rsp+38h+arg_0], r8d
0x180017eb4  mov     dword ptr [rsp+38h+arg_0+4], r9d
0x180017eb9  mov     rdi, [rsp+38h+arg_0]
0x180017ebe  lock cmpxchg cs:Feature_SmartSuspend_Thresholds__private_featureState, rdi
0x180017ec7  jz      short loc_180017ED6
0x180017ec9  mov     ebx, eax
0x180017ecb  shr     rax, 20h
0x180017ecf  mov     edi, eax
0x180017ed1  jmp     loc_180017E52
0x180017ed6  test    bl, 4
0x180017ed9  jnz     short loc_180017EFB
0x180017edb  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x180017ee2  test    rax, rax
0x180017ee5  jz      short loc_180017EFB
0x180017ee7  mov     r8d, esi
0x180017eea  lea     rcx, Feature_SmartSuspend_Thresholds__private_featureState
0x180017ef1  mov     edx, 3
0x180017ef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017efb  mov     rax, rdi
0x180017efe  add     rsp, 20h
0x180017f02  pop     rdi
0x180017f03  pop     rsi
0x180017f04  pop     rbx
0x180017f05  retn
```
