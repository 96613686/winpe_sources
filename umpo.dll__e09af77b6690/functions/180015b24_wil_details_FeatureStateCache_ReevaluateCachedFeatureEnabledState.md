# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x180015b24`
- end: `0x180015c35`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `273`
- prototype: `__int64 __fastcall(volatile signed __int32 *, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000caac`
- `0x180015de8`

## callees

- `0x180015b24`
- `0x180015c90`
- `0x180019010`

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
0x180015b24  mov     [rsp+arg_10], rbx
0x180015b29  mov     [rsp+arg_18], rbp
0x180015b2e  push    rsi
0x180015b2f  push    rdi
0x180015b30  push    r12
0x180015b32  push    r14
0x180015b34  push    r15
0x180015b36  sub     rsp, 20h
0x180015b3a  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x180015b41  xor     r14d, r14d
0x180015b44  mov     [rsp+48h+arg_0], r14d
0x180015b49  mov     r15, r8
0x180015b4c  mov     [rsp+48h+arg_8], rdx
0x180015b51  mov     rbx, rdx
0x180015b54  mov     r12, rcx
0x180015b57  test    rax, rax
0x180015b5a  jz      short loc_180015B64
0x180015b5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b61  mov     r14d, eax
0x180015b64  lea     rdx, [rsp+48h+arg_0]
0x180015b69  mov     rcx, r15
0x180015b6c  call    wil_details_GetCurrentFeatureEnabledState
0x180015b71  cmp     byte ptr [r15+1Ch], 0
0x180015b76  mov     rdi, rax
0x180015b79  jnz     short loc_180015B88
0x180015b7b  mov     ecx, r14d
0x180015b7e  neg     ecx
0x180015b80  sbb     ebp, ebp
0x180015b82  and     ebp, [rsp+48h+arg_0]
0x180015b86  jmp     short loc_180015B8C
0x180015b88  mov     ebp, [rsp+48h+arg_0]
0x180015b8c  mov     dword ptr [rsp+48h+arg_8], ebx
0x180015b90  mov     esi, ebx
0x180015b92  test    ebp, ebp
0x180015b94  jz      short loc_180015BB5
0x180015b96  mov     dword ptr [rsp+48h+arg_8], ebx
0x180015b9a  test    bl, 2
0x180015b9d  jnz     short loc_180015BB5
0x180015b9f  and     esi, 0FFFFF63Eh
0x180015ba5  mov     eax, edi
0x180015ba7  and     eax, 9C1h
0x180015bac  or      esi, eax
0x180015bae  or      esi, 2
0x180015bb1  mov     dword ptr [rsp+48h+arg_8], esi
0x180015bb5  mov     edx, ebx
0x180015bb7  and     edx, 4
0x180015bba  jnz     short loc_180015BD5
0x180015bbc  mov     eax, esi
0x180015bbe  mov     ecx, edi
0x180015bc0  and     ecx, 400h
0x180015bc6  btr     eax, 0Ah
0x180015bca  mov     esi, ecx
0x180015bcc  or      esi, eax
0x180015bce  or      esi, 4
0x180015bd1  mov     dword ptr [rsp+48h+arg_8], esi
0x180015bd5  mov     eax, ebx
0x180015bd7  lock cmpxchg [r12], esi
0x180015bdd  jz      short loc_180015BE3
0x180015bdf  mov     ebx, eax
0x180015be1  jmp     short loc_180015B8C
0x180015be3  test    edx, edx
0x180015be5  jnz     short loc_180015C03
0x180015be7  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x180015bee  test    rax, rax
0x180015bf1  jz      short loc_180015C03
0x180015bf3  movzx   edx, byte ptr [r15+1Ch]
0x180015bf8  mov     r8d, r14d
0x180015bfb  mov     rcx, r12
0x180015bfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c03  test    ebp, ebp
0x180015c05  jnz     short loc_180015C19
0x180015c07  and     esi, 0FFFFF63Eh
0x180015c0d  and     edi, 9C1h
0x180015c13  or      esi, edi
0x180015c15  mov     dword ptr [rsp+48h+arg_8], esi
0x180015c19  mov     rax, [rsp+48h+arg_8]
0x180015c1e  mov     rbx, [rsp+48h+arg_10]
0x180015c23  mov     rbp, [rsp+48h+arg_18]
0x180015c28  add     rsp, 20h
0x180015c2c  pop     r15
0x180015c2e  pop     r14
0x180015c30  pop     r12
0x180015c32  pop     rdi
0x180015c33  pop     rsi
0x180015c34  retn
```
