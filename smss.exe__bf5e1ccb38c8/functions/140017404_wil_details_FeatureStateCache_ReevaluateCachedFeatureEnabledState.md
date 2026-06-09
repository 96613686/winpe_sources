# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x140017404`
- end: `0x140017515`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `273`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140016e9c`
- `0x1400176c0`

## callees

- `0x140017404`
- `0x140017570`
- `0x14001e010`

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
0x140017404  mov     [rsp+arg_10], rbx
0x140017409  mov     [rsp+arg_18], rbp
0x14001740e  push    rsi
0x14001740f  push    rdi
0x140017410  push    r12
0x140017412  push    r14
0x140017414  push    r15
0x140017416  sub     rsp, 20h
0x14001741a  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x140017421  xor     r14d, r14d
0x140017424  mov     [rsp+48h+arg_0], r14d
0x140017429  mov     r15, r8
0x14001742c  mov     [rsp+48h+arg_8], rdx
0x140017431  mov     rbx, rdx
0x140017434  mov     r12, rcx
0x140017437  test    rax, rax
0x14001743a  jz      short loc_140017444
0x14001743c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017441  mov     r14d, eax
0x140017444  lea     rdx, [rsp+48h+arg_0]
0x140017449  mov     rcx, r15
0x14001744c  call    wil_details_GetCurrentFeatureEnabledState
0x140017451  cmp     byte ptr [r15+1Ch], 0
0x140017456  mov     rdi, rax
0x140017459  jnz     short loc_140017468
0x14001745b  mov     ecx, r14d
0x14001745e  neg     ecx
0x140017460  sbb     ebp, ebp
0x140017462  and     ebp, [rsp+48h+arg_0]
0x140017466  jmp     short loc_14001746C
0x140017468  mov     ebp, [rsp+48h+arg_0]
0x14001746c  mov     dword ptr [rsp+48h+arg_8], ebx
0x140017470  mov     esi, ebx
0x140017472  test    ebp, ebp
0x140017474  jz      short loc_140017495
0x140017476  mov     dword ptr [rsp+48h+arg_8], ebx
0x14001747a  test    bl, 2
0x14001747d  jnz     short loc_140017495
0x14001747f  and     esi, 0FFFFF63Eh
0x140017485  mov     eax, edi
0x140017487  and     eax, 9C1h
0x14001748c  or      esi, eax
0x14001748e  or      esi, 2
0x140017491  mov     dword ptr [rsp+48h+arg_8], esi
0x140017495  mov     edx, ebx
0x140017497  and     edx, 4
0x14001749a  jnz     short loc_1400174B5
0x14001749c  mov     eax, esi
0x14001749e  mov     ecx, edi
0x1400174a0  and     ecx, 400h
0x1400174a6  btr     eax, 0Ah
0x1400174aa  mov     esi, ecx
0x1400174ac  or      esi, eax
0x1400174ae  or      esi, 4
0x1400174b1  mov     dword ptr [rsp+48h+arg_8], esi
0x1400174b5  mov     eax, ebx
0x1400174b7  lock cmpxchg [r12], esi
0x1400174bd  jz      short loc_1400174C3
0x1400174bf  mov     ebx, eax
0x1400174c1  jmp     short loc_14001746C
0x1400174c3  test    edx, edx
0x1400174c5  jnz     short loc_1400174E3
0x1400174c7  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x1400174ce  test    rax, rax
0x1400174d1  jz      short loc_1400174E3
0x1400174d3  movzx   edx, byte ptr [r15+1Ch]
0x1400174d8  mov     r8d, r14d
0x1400174db  mov     rcx, r12
0x1400174de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400174e3  test    ebp, ebp
0x1400174e5  jnz     short loc_1400174F9
0x1400174e7  and     esi, 0FFFFF63Eh
0x1400174ed  and     edi, 9C1h
0x1400174f3  or      esi, edi
0x1400174f5  mov     dword ptr [rsp+48h+arg_8], esi
0x1400174f9  mov     rax, [rsp+48h+arg_8]
0x1400174fe  mov     rbx, [rsp+48h+arg_10]
0x140017503  mov     rbp, [rsp+48h+arg_18]
0x140017508  add     rsp, 20h
0x14001750c  pop     r15
0x14001750e  pop     r14
0x140017510  pop     r12
0x140017512  pop     rdi
0x140017513  pop     rsi
0x140017514  retn
```
