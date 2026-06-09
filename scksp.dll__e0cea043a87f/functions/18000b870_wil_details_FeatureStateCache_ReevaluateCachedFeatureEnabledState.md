# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x18000b870`
- end: `0x18000b981`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `273`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b3b4`
- `0x18000bb28`

## callees

- `0x18000b870`
- `0x18000b9cc`
- `0x18003d010`

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
0x18000b870  mov     [rsp+arg_10], rbx
0x18000b875  mov     [rsp+arg_18], rbp
0x18000b87a  push    rsi
0x18000b87b  push    rdi
0x18000b87c  push    r12
0x18000b87e  push    r14
0x18000b880  push    r15
0x18000b882  sub     rsp, 20h
0x18000b886  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x18000b88d  xor     r14d, r14d
0x18000b890  mov     [rsp+48h+arg_0], r14d
0x18000b895  mov     r15, r8
0x18000b898  mov     [rsp+48h+arg_8], rdx
0x18000b89d  mov     rbx, rdx
0x18000b8a0  mov     r12, rcx
0x18000b8a3  test    rax, rax
0x18000b8a6  jz      short loc_18000B8B0
0x18000b8a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8ad  mov     r14d, eax
0x18000b8b0  lea     rdx, [rsp+48h+arg_0]
0x18000b8b5  mov     rcx, r15
0x18000b8b8  call    wil_details_GetCurrentFeatureEnabledState
0x18000b8bd  cmp     byte ptr [r15+1Ch], 0
0x18000b8c2  mov     rdi, rax
0x18000b8c5  jnz     short loc_18000B8D4
0x18000b8c7  mov     ecx, r14d
0x18000b8ca  neg     ecx
0x18000b8cc  sbb     ebp, ebp
0x18000b8ce  and     ebp, [rsp+48h+arg_0]
0x18000b8d2  jmp     short loc_18000B8D8
0x18000b8d4  mov     ebp, [rsp+48h+arg_0]
0x18000b8d8  mov     dword ptr [rsp+48h+arg_8], ebx
0x18000b8dc  mov     esi, ebx
0x18000b8de  test    ebp, ebp
0x18000b8e0  jz      short loc_18000B901
0x18000b8e2  mov     dword ptr [rsp+48h+arg_8], ebx
0x18000b8e6  test    bl, 2
0x18000b8e9  jnz     short loc_18000B901
0x18000b8eb  and     esi, 0FFFFF63Eh
0x18000b8f1  mov     eax, edi
0x18000b8f3  and     eax, 9C1h
0x18000b8f8  or      esi, eax
0x18000b8fa  or      esi, 2
0x18000b8fd  mov     dword ptr [rsp+48h+arg_8], esi
0x18000b901  mov     edx, ebx
0x18000b903  and     edx, 4
0x18000b906  jnz     short loc_18000B921
0x18000b908  mov     eax, esi
0x18000b90a  mov     ecx, edi
0x18000b90c  and     ecx, 400h
0x18000b912  btr     eax, 0Ah
0x18000b916  mov     esi, ecx
0x18000b918  or      esi, eax
0x18000b91a  or      esi, 4
0x18000b91d  mov     dword ptr [rsp+48h+arg_8], esi
0x18000b921  mov     eax, ebx
0x18000b923  lock cmpxchg [r12], esi
0x18000b929  jz      short loc_18000B92F
0x18000b92b  mov     ebx, eax
0x18000b92d  jmp     short loc_18000B8D8
0x18000b92f  test    edx, edx
0x18000b931  jnz     short loc_18000B94F
0x18000b933  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x18000b93a  test    rax, rax
0x18000b93d  jz      short loc_18000B94F
0x18000b93f  movzx   edx, byte ptr [r15+1Ch]
0x18000b944  mov     r8d, r14d
0x18000b947  mov     rcx, r12
0x18000b94a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b94f  test    ebp, ebp
0x18000b951  jnz     short loc_18000B965
0x18000b953  and     esi, 0FFFFF63Eh
0x18000b959  and     edi, 9C1h
0x18000b95f  or      esi, edi
0x18000b961  mov     dword ptr [rsp+48h+arg_8], esi
0x18000b965  mov     rax, [rsp+48h+arg_8]
0x18000b96a  mov     rbx, [rsp+48h+arg_10]
0x18000b96f  mov     rbp, [rsp+48h+arg_18]
0x18000b974  add     rsp, 20h
0x18000b978  pop     r15
0x18000b97a  pop     r14
0x18000b97c  pop     r12
0x18000b97e  pop     rdi
0x18000b97f  pop     rsi
0x18000b980  retn
```
