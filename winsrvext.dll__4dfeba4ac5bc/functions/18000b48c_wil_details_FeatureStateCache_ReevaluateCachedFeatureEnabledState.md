# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x18000b48c`
- end: `0x18000b59e`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `274`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b5fc`
- `0x18000b830`

## callees

- `0x18000b48c`
- `0x18000b5fc`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState(
        volatile signed __int32 *a1,
        __int64 a2,
        __int64 a3)
{
  unsigned int v3; // r14d
  signed __int32 v5; // ebx
  __int16 CurrentFeatureEnabledState; // di
  int v8; // ebp
  unsigned int v9; // esi
  signed __int32 v10; // eax
  int v12; // [rsp+50h] [rbp+8h] BYREF
  __int64 v13; // [rsp+58h] [rbp+10h]

  v3 = 0;
  v12 = 0;
  v13 = a2;
  v5 = a2;
  if ( g_wil_details_ensureSubscribedToFeatureConfigurationChanges )
    v3 = g_wil_details_ensureSubscribedToFeatureConfigurationChanges();
  CurrentFeatureEnabledState = wil_details_GetCurrentFeatureEnabledState(a3, &v12);
  if ( *(_BYTE *)(a3 + 28) )
    v8 = v12;
  else
    v8 = v3 != 0 ? v12 : 0;
  while ( 1 )
  {
    LODWORD(v13) = v5;
    v9 = v5;
    if ( v8 )
    {
      LODWORD(v13) = v5;
      if ( (v5 & 2) == 0 )
      {
        v9 = CurrentFeatureEnabledState & 0x9C1 | v5 & 0xFFFFF63E | 2;
        LODWORD(v13) = v9;
      }
    }
    if ( (v5 & 4) == 0 )
    {
      v9 = v9 & 0xFFFFFBFF | CurrentFeatureEnabledState & 0x400 | 4;
      LODWORD(v13) = v9;
    }
    v10 = _InterlockedCompareExchange(a1, v9, v5);
    if ( v5 == v10 )
      break;
    v5 = v10;
  }
  if ( (v5 & 4) == 0 && g_wil_details_subscribeFeatureStateCacheToConfigurationChanges )
    g_wil_details_subscribeFeatureStateCacheToConfigurationChanges(a1, *(unsigned __int8 *)(a3 + 28), v3);
  if ( !v8 )
    LODWORD(v13) = CurrentFeatureEnabledState & 0x9C1 | v9 & 0xFFFFF63E;
  return v13;
}

```

## disassembly

```asm
0x18000b48c  mov     [rsp+arg_10], rbx
0x18000b491  mov     [rsp+arg_18], rbp
0x18000b496  push    rsi
0x18000b497  push    rdi
0x18000b498  push    r12
0x18000b49a  push    r14
0x18000b49c  push    r15
0x18000b49e  sub     rsp, 20h
0x18000b4a2  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x18000b4a9  xor     r14d, r14d
0x18000b4ac  mov     [rsp+48h+arg_0], r14d
0x18000b4b1  mov     r15, r8
0x18000b4b4  mov     [rsp+48h+arg_8], rdx
0x18000b4b9  mov     rbx, rdx
0x18000b4bc  mov     r12, rcx
0x18000b4bf  test    rax, rax
0x18000b4c2  jz      short loc_18000B4CC
0x18000b4c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4c9  mov     r14d, eax
0x18000b4cc  lea     rdx, [rsp+48h+arg_0]
0x18000b4d1  mov     rcx, r15
0x18000b4d4  call    wil_details_GetCurrentFeatureEnabledState
0x18000b4d9  cmp     byte ptr [r15+1Ch], 0
0x18000b4de  mov     rdi, rax
0x18000b4e1  jnz     short loc_18000B4F0
0x18000b4e3  mov     ecx, r14d
0x18000b4e6  neg     ecx
0x18000b4e8  sbb     ebp, ebp
0x18000b4ea  and     ebp, [rsp+48h+arg_0]
0x18000b4ee  jmp     short loc_18000B4F4
0x18000b4f0  mov     ebp, [rsp+48h+arg_0]
0x18000b4f4  mov     dword ptr [rsp+48h+arg_8], ebx
0x18000b4f8  mov     esi, ebx
0x18000b4fa  test    ebp, ebp
0x18000b4fc  jz      short loc_18000B51D
0x18000b4fe  mov     dword ptr [rsp+48h+arg_8], ebx
0x18000b502  test    bl, 2
0x18000b505  jnz     short loc_18000B51D
0x18000b507  and     esi, 0FFFFF63Eh
0x18000b50d  mov     eax, edi
0x18000b50f  and     eax, 9C1h
0x18000b514  or      esi, eax
0x18000b516  or      esi, 2
0x18000b519  mov     dword ptr [rsp+48h+arg_8], esi
0x18000b51d  mov     edx, ebx
0x18000b51f  and     edx, 4
0x18000b522  jnz     short loc_18000B53D
0x18000b524  mov     eax, esi
0x18000b526  mov     ecx, edi
0x18000b528  and     ecx, 400h
0x18000b52e  btr     eax, 0Ah
0x18000b532  mov     esi, ecx
0x18000b534  or      esi, eax
0x18000b536  or      esi, 4
0x18000b539  mov     dword ptr [rsp+48h+arg_8], esi
0x18000b53d  mov     eax, ebx
0x18000b53f  lock cmpxchg [r12], esi
0x18000b545  jz      short loc_18000B54B
0x18000b547  mov     ebx, eax
0x18000b549  jmp     short loc_18000B4F4
0x18000b54b  test    edx, edx
0x18000b54d  jnz     short loc_18000B56B
0x18000b54f  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x18000b556  test    rax, rax
0x18000b559  jz      short loc_18000B56B
0x18000b55b  movzx   edx, byte ptr [r15+1Ch]
0x18000b560  mov     r8d, r14d
0x18000b563  mov     rcx, r12
0x18000b566  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b56b  test    ebp, ebp
0x18000b56d  jnz     short loc_18000B581
0x18000b56f  and     esi, 0FFFFF63Eh
0x18000b575  and     edi, 9C1h
0x18000b57b  or      esi, edi
0x18000b57d  mov     dword ptr [rsp+48h+arg_8], esi
0x18000b581  mov     rax, [rsp+48h+arg_8]
0x18000b586  mov     rbx, [rsp+48h+arg_10]
0x18000b58b  mov     rbp, [rsp+48h+arg_18]
0x18000b590  add     rsp, 20h
0x18000b594  pop     r15
0x18000b596  pop     r14
0x18000b598  pop     r12
0x18000b59a  pop     rdi
0x18000b59b  pop     rsi
0x18000b59c  retn
```
