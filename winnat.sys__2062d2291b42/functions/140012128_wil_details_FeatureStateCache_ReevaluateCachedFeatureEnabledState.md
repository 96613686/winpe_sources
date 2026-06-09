# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x140012128`
- end: `0x14001223a`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `274`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140011bf0`
- `0x1400123b0`

## callees

- `0x140012128`
- `0x140012298`
- `0x14001f4b0`

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
0x140012128  mov     [rsp+arg_10], rbx
0x14001212d  mov     [rsp+arg_18], rbp
0x140012132  push    rsi
0x140012133  push    rdi
0x140012134  push    r12
0x140012136  push    r14
0x140012138  push    r15
0x14001213a  sub     rsp, 20h
0x14001213e  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x140012145  xor     r14d, r14d
0x140012148  mov     [rsp+48h+arg_0], r14d
0x14001214d  mov     r15, r8
0x140012150  mov     [rsp+48h+arg_8], rdx
0x140012155  mov     rbx, rdx
0x140012158  mov     r12, rcx
0x14001215b  test    rax, rax
0x14001215e  jz      short loc_140012168
0x140012160  call    _guard_dispatch_icall
0x140012165  mov     r14d, eax
0x140012168  lea     rdx, [rsp+48h+arg_0]
0x14001216d  mov     rcx, r15
0x140012170  call    wil_details_GetCurrentFeatureEnabledState
0x140012175  cmp     byte ptr [r15+1Ch], 0
0x14001217a  mov     rdi, rax
0x14001217d  jnz     short loc_14001218C
0x14001217f  mov     ecx, r14d
0x140012182  neg     ecx
0x140012184  sbb     ebp, ebp
0x140012186  and     ebp, [rsp+48h+arg_0]
0x14001218a  jmp     short loc_140012190
0x14001218c  mov     ebp, [rsp+48h+arg_0]
0x140012190  mov     dword ptr [rsp+48h+arg_8], ebx
0x140012194  mov     esi, ebx
0x140012196  test    ebp, ebp
0x140012198  jz      short loc_1400121B9
0x14001219a  mov     dword ptr [rsp+48h+arg_8], ebx
0x14001219e  test    bl, 2
0x1400121a1  jnz     short loc_1400121B9
0x1400121a3  and     esi, 0FFFFF63Eh
0x1400121a9  mov     eax, edi
0x1400121ab  and     eax, 9C1h
0x1400121b0  or      esi, eax
0x1400121b2  or      esi, 2
0x1400121b5  mov     dword ptr [rsp+48h+arg_8], esi
0x1400121b9  mov     edx, ebx
0x1400121bb  and     edx, 4
0x1400121be  jnz     short loc_1400121D9
0x1400121c0  mov     eax, esi
0x1400121c2  mov     ecx, edi
0x1400121c4  and     ecx, 400h
0x1400121ca  btr     eax, 0Ah
0x1400121ce  mov     esi, ecx
0x1400121d0  or      esi, eax
0x1400121d2  or      esi, 4
0x1400121d5  mov     dword ptr [rsp+48h+arg_8], esi
0x1400121d9  mov     eax, ebx
0x1400121db  lock cmpxchg [r12], esi
0x1400121e1  jz      short loc_1400121E7
0x1400121e3  mov     ebx, eax
0x1400121e5  jmp     short loc_140012190
0x1400121e7  test    edx, edx
0x1400121e9  jnz     short loc_140012207
0x1400121eb  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x1400121f2  test    rax, rax
0x1400121f5  jz      short loc_140012207
0x1400121f7  movzx   edx, byte ptr [r15+1Ch]
0x1400121fc  mov     r8d, r14d
0x1400121ff  mov     rcx, r12
0x140012202  call    _guard_dispatch_icall
0x140012207  test    ebp, ebp
0x140012209  jnz     short loc_14001221D
0x14001220b  and     esi, 0FFFFF63Eh
0x140012211  and     edi, 9C1h
0x140012217  or      esi, edi
0x140012219  mov     dword ptr [rsp+48h+arg_8], esi
0x14001221d  mov     rax, [rsp+48h+arg_8]
0x140012222  mov     rbx, [rsp+48h+arg_10]
0x140012227  mov     rbp, [rsp+48h+arg_18]
0x14001222c  add     rsp, 20h
0x140012230  pop     r15
0x140012232  pop     r14
0x140012234  pop     r12
0x140012236  pop     rdi
0x140012237  pop     rsi
0x140012238  retn
```
