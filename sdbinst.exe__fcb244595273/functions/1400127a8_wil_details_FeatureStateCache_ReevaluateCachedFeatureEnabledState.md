# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x1400127a8`
- end: `0x1400128b9`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `273`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140012914`
- `0x140012b60`

## callees

- `0x1400127a8`
- `0x140012914`
- `0x14002f010`

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
0x1400127a8  mov     [rsp+arg_10], rbx
0x1400127ad  mov     [rsp+arg_18], rbp
0x1400127b2  push    rsi
0x1400127b3  push    rdi
0x1400127b4  push    r12
0x1400127b6  push    r14
0x1400127b8  push    r15
0x1400127ba  sub     rsp, 20h
0x1400127be  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x1400127c5  xor     r14d, r14d
0x1400127c8  mov     [rsp+48h+arg_0], r14d
0x1400127cd  mov     r15, r8
0x1400127d0  mov     [rsp+48h+arg_8], rdx
0x1400127d5  mov     rbx, rdx
0x1400127d8  mov     r12, rcx
0x1400127db  test    rax, rax
0x1400127de  jz      short loc_1400127E8
0x1400127e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400127e5  mov     r14d, eax
0x1400127e8  lea     rdx, [rsp+48h+arg_0]
0x1400127ed  mov     rcx, r15
0x1400127f0  call    wil_details_GetCurrentFeatureEnabledState
0x1400127f5  cmp     byte ptr [r15+1Ch], 0
0x1400127fa  mov     rdi, rax
0x1400127fd  jnz     short loc_14001280C
0x1400127ff  mov     ecx, r14d
0x140012802  neg     ecx
0x140012804  sbb     ebp, ebp
0x140012806  and     ebp, [rsp+48h+arg_0]
0x14001280a  jmp     short loc_140012810
0x14001280c  mov     ebp, [rsp+48h+arg_0]
0x140012810  mov     dword ptr [rsp+48h+arg_8], ebx
0x140012814  mov     esi, ebx
0x140012816  test    ebp, ebp
0x140012818  jz      short loc_140012839
0x14001281a  mov     dword ptr [rsp+48h+arg_8], ebx
0x14001281e  test    bl, 2
0x140012821  jnz     short loc_140012839
0x140012823  and     esi, 0FFFFF63Eh
0x140012829  mov     eax, edi
0x14001282b  and     eax, 9C1h
0x140012830  or      esi, eax
0x140012832  or      esi, 2
0x140012835  mov     dword ptr [rsp+48h+arg_8], esi
0x140012839  mov     edx, ebx
0x14001283b  and     edx, 4
0x14001283e  jnz     short loc_140012859
0x140012840  mov     eax, esi
0x140012842  mov     ecx, edi
0x140012844  and     ecx, 400h
0x14001284a  btr     eax, 0Ah
0x14001284e  mov     esi, ecx
0x140012850  or      esi, eax
0x140012852  or      esi, 4
0x140012855  mov     dword ptr [rsp+48h+arg_8], esi
0x140012859  mov     eax, ebx
0x14001285b  lock cmpxchg [r12], esi
0x140012861  jz      short loc_140012867
0x140012863  mov     ebx, eax
0x140012865  jmp     short loc_140012810
0x140012867  test    edx, edx
0x140012869  jnz     short loc_140012887
0x14001286b  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x140012872  test    rax, rax
0x140012875  jz      short loc_140012887
0x140012877  movzx   edx, byte ptr [r15+1Ch]
0x14001287c  mov     r8d, r14d
0x14001287f  mov     rcx, r12
0x140012882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012887  test    ebp, ebp
0x140012889  jnz     short loc_14001289D
0x14001288b  and     esi, 0FFFFF63Eh
0x140012891  and     edi, 9C1h
0x140012897  or      esi, edi
0x140012899  mov     dword ptr [rsp+48h+arg_8], esi
0x14001289d  mov     rax, [rsp+48h+arg_8]
0x1400128a2  mov     rbx, [rsp+48h+arg_10]
0x1400128a7  mov     rbp, [rsp+48h+arg_18]
0x1400128ac  add     rsp, 20h
0x1400128b0  pop     r15
0x1400128b2  pop     r14
0x1400128b4  pop     r12
0x1400128b6  pop     rdi
0x1400128b7  pop     rsi
0x1400128b8  retn
```
