# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x14000764c`
- end: `0x14000775d`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `273`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400070b4`
- `0x140007900`

## callees

- `0x14000764c`
- `0x1400077a8`
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
0x14000764c  mov     [rsp+arg_10], rbx
0x140007651  mov     [rsp+arg_18], rbp
0x140007656  push    rsi
0x140007657  push    rdi
0x140007658  push    r12
0x14000765a  push    r14
0x14000765c  push    r15
0x14000765e  sub     rsp, 20h
0x140007662  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x140007669  xor     r14d, r14d
0x14000766c  mov     [rsp+48h+arg_0], r14d
0x140007671  mov     r15, r8
0x140007674  mov     [rsp+48h+arg_8], rdx
0x140007679  mov     rbx, rdx
0x14000767c  mov     r12, rcx
0x14000767f  test    rax, rax
0x140007682  jz      short loc_14000768C
0x140007684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007689  mov     r14d, eax
0x14000768c  lea     rdx, [rsp+48h+arg_0]
0x140007691  mov     rcx, r15
0x140007694  call    wil_details_GetCurrentFeatureEnabledState
0x140007699  cmp     byte ptr [r15+1Ch], 0
0x14000769e  mov     rdi, rax
0x1400076a1  jnz     short loc_1400076B0
0x1400076a3  mov     ecx, r14d
0x1400076a6  neg     ecx
0x1400076a8  sbb     ebp, ebp
0x1400076aa  and     ebp, [rsp+48h+arg_0]
0x1400076ae  jmp     short loc_1400076B4
0x1400076b0  mov     ebp, [rsp+48h+arg_0]
0x1400076b4  mov     dword ptr [rsp+48h+arg_8], ebx
0x1400076b8  mov     esi, ebx
0x1400076ba  test    ebp, ebp
0x1400076bc  jz      short loc_1400076DD
0x1400076be  mov     dword ptr [rsp+48h+arg_8], ebx
0x1400076c2  test    bl, 2
0x1400076c5  jnz     short loc_1400076DD
0x1400076c7  and     esi, 0FFFFF63Eh
0x1400076cd  mov     eax, edi
0x1400076cf  and     eax, 9C1h
0x1400076d4  or      esi, eax
0x1400076d6  or      esi, 2
0x1400076d9  mov     dword ptr [rsp+48h+arg_8], esi
0x1400076dd  mov     edx, ebx
0x1400076df  and     edx, 4
0x1400076e2  jnz     short loc_1400076FD
0x1400076e4  mov     eax, esi
0x1400076e6  mov     ecx, edi
0x1400076e8  and     ecx, 400h
0x1400076ee  btr     eax, 0Ah
0x1400076f2  mov     esi, ecx
0x1400076f4  or      esi, eax
0x1400076f6  or      esi, 4
0x1400076f9  mov     dword ptr [rsp+48h+arg_8], esi
0x1400076fd  mov     eax, ebx
0x1400076ff  lock cmpxchg [r12], esi
0x140007705  jz      short loc_14000770B
0x140007707  mov     ebx, eax
0x140007709  jmp     short loc_1400076B4
0x14000770b  test    edx, edx
0x14000770d  jnz     short loc_14000772B
0x14000770f  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x140007716  test    rax, rax
0x140007719  jz      short loc_14000772B
0x14000771b  movzx   edx, byte ptr [r15+1Ch]
0x140007720  mov     r8d, r14d
0x140007723  mov     rcx, r12
0x140007726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000772b  test    ebp, ebp
0x14000772d  jnz     short loc_140007741
0x14000772f  and     esi, 0FFFFF63Eh
0x140007735  and     edi, 9C1h
0x14000773b  or      esi, edi
0x14000773d  mov     dword ptr [rsp+48h+arg_8], esi
0x140007741  mov     rax, [rsp+48h+arg_8]
0x140007746  mov     rbx, [rsp+48h+arg_10]
0x14000774b  mov     rbp, [rsp+48h+arg_18]
0x140007750  add     rsp, 20h
0x140007754  pop     r15
0x140007756  pop     r14
0x140007758  pop     r12
0x14000775a  pop     rdi
0x14000775b  pop     rsi
0x14000775c  retn
```
