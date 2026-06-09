# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x140007a54`
- end: `0x140007b66`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `274`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140007bb0`
- `0x140007d4c`

## callees

- `0x140007a54`
- `0x140007bb0`
- `0x140009010`

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
0x140007a54  mov     [rsp+arg_10], rbx
0x140007a59  mov     [rsp+arg_18], rbp
0x140007a5e  push    rsi
0x140007a5f  push    rdi
0x140007a60  push    r12
0x140007a62  push    r14
0x140007a64  push    r15
0x140007a66  sub     rsp, 20h
0x140007a6a  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x140007a71  xor     r14d, r14d
0x140007a74  mov     [rsp+48h+arg_0], r14d
0x140007a79  mov     r15, r8
0x140007a7c  mov     [rsp+48h+arg_8], rdx
0x140007a81  mov     rbx, rdx
0x140007a84  mov     r12, rcx
0x140007a87  test    rax, rax
0x140007a8a  jz      short loc_140007A94
0x140007a8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007a91  mov     r14d, eax
0x140007a94  lea     rdx, [rsp+48h+arg_0]
0x140007a99  mov     rcx, r15
0x140007a9c  call    wil_details_GetCurrentFeatureEnabledState
0x140007aa1  cmp     byte ptr [r15+1Ch], 0
0x140007aa6  mov     rdi, rax
0x140007aa9  jnz     short loc_140007AB8
0x140007aab  mov     ecx, r14d
0x140007aae  neg     ecx
0x140007ab0  sbb     ebp, ebp
0x140007ab2  and     ebp, [rsp+48h+arg_0]
0x140007ab6  jmp     short loc_140007ABC
0x140007ab8  mov     ebp, [rsp+48h+arg_0]
0x140007abc  mov     dword ptr [rsp+48h+arg_8], ebx
0x140007ac0  mov     esi, ebx
0x140007ac2  test    ebp, ebp
0x140007ac4  jz      short loc_140007AE5
0x140007ac6  mov     dword ptr [rsp+48h+arg_8], ebx
0x140007aca  test    bl, 2
0x140007acd  jnz     short loc_140007AE5
0x140007acf  and     esi, 0FFFFF63Eh
0x140007ad5  mov     eax, edi
0x140007ad7  and     eax, 9C1h
0x140007adc  or      esi, eax
0x140007ade  or      esi, 2
0x140007ae1  mov     dword ptr [rsp+48h+arg_8], esi
0x140007ae5  mov     edx, ebx
0x140007ae7  and     edx, 4
0x140007aea  jnz     short loc_140007B05
0x140007aec  mov     eax, esi
0x140007aee  mov     ecx, edi
0x140007af0  and     ecx, 400h
0x140007af6  btr     eax, 0Ah
0x140007afa  mov     esi, ecx
0x140007afc  or      esi, eax
0x140007afe  or      esi, 4
0x140007b01  mov     dword ptr [rsp+48h+arg_8], esi
0x140007b05  mov     eax, ebx
0x140007b07  lock cmpxchg [r12], esi
0x140007b0d  jz      short loc_140007B13
0x140007b0f  mov     ebx, eax
0x140007b11  jmp     short loc_140007ABC
0x140007b13  test    edx, edx
0x140007b15  jnz     short loc_140007B33
0x140007b17  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x140007b1e  test    rax, rax
0x140007b21  jz      short loc_140007B33
0x140007b23  movzx   edx, byte ptr [r15+1Ch]
0x140007b28  mov     r8d, r14d
0x140007b2b  mov     rcx, r12
0x140007b2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007b33  test    ebp, ebp
0x140007b35  jnz     short loc_140007B49
0x140007b37  and     esi, 0FFFFF63Eh
0x140007b3d  and     edi, 9C1h
0x140007b43  or      esi, edi
0x140007b45  mov     dword ptr [rsp+48h+arg_8], esi
0x140007b49  mov     rax, [rsp+48h+arg_8]
0x140007b4e  mov     rbx, [rsp+48h+arg_10]
0x140007b53  mov     rbp, [rsp+48h+arg_18]
0x140007b58  add     rsp, 20h
0x140007b5c  pop     r15
0x140007b5e  pop     r14
0x140007b60  pop     r12
0x140007b62  pop     rdi
0x140007b63  pop     rsi
0x140007b64  retn
```
