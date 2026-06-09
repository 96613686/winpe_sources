# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x140011b58`
- end: `0x140011c6a`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `274`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140010c94`
- `0x140011cc4`

## callees

- `0x140011b58`
- `0x140011cc4`
- `0x140014d50`

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
0x140011b58  mov     [rsp+arg_10], rbx
0x140011b5d  mov     [rsp+arg_18], rbp
0x140011b62  push    rsi
0x140011b63  push    rdi
0x140011b64  push    r12
0x140011b66  push    r14
0x140011b68  push    r15
0x140011b6a  sub     rsp, 20h
0x140011b6e  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x140011b75  xor     r14d, r14d
0x140011b78  mov     [rsp+48h+arg_0], r14d
0x140011b7d  mov     r15, r8
0x140011b80  mov     [rsp+48h+arg_8], rdx
0x140011b85  mov     rbx, rdx
0x140011b88  mov     r12, rcx
0x140011b8b  test    rax, rax
0x140011b8e  jz      short loc_140011B98
0x140011b90  call    _guard_dispatch_icall
0x140011b95  mov     r14d, eax
0x140011b98  lea     rdx, [rsp+48h+arg_0]
0x140011b9d  mov     rcx, r15
0x140011ba0  call    wil_details_GetCurrentFeatureEnabledState
0x140011ba5  cmp     byte ptr [r15+1Ch], 0
0x140011baa  mov     rdi, rax
0x140011bad  jnz     short loc_140011BBC
0x140011baf  mov     ecx, r14d
0x140011bb2  neg     ecx
0x140011bb4  sbb     ebp, ebp
0x140011bb6  and     ebp, [rsp+48h+arg_0]
0x140011bba  jmp     short loc_140011BC0
0x140011bbc  mov     ebp, [rsp+48h+arg_0]
0x140011bc0  mov     dword ptr [rsp+48h+arg_8], ebx
0x140011bc4  mov     esi, ebx
0x140011bc6  test    ebp, ebp
0x140011bc8  jz      short loc_140011BE9
0x140011bca  mov     dword ptr [rsp+48h+arg_8], ebx
0x140011bce  test    bl, 2
0x140011bd1  jnz     short loc_140011BE9
0x140011bd3  and     esi, 0FFFFF63Eh
0x140011bd9  mov     eax, edi
0x140011bdb  and     eax, 9C1h
0x140011be0  or      esi, eax
0x140011be2  or      esi, 2
0x140011be5  mov     dword ptr [rsp+48h+arg_8], esi
0x140011be9  mov     edx, ebx
0x140011beb  and     edx, 4
0x140011bee  jnz     short loc_140011C09
0x140011bf0  mov     eax, esi
0x140011bf2  mov     ecx, edi
0x140011bf4  and     ecx, 400h
0x140011bfa  btr     eax, 0Ah
0x140011bfe  mov     esi, ecx
0x140011c00  or      esi, eax
0x140011c02  or      esi, 4
0x140011c05  mov     dword ptr [rsp+48h+arg_8], esi
0x140011c09  mov     eax, ebx
0x140011c0b  lock cmpxchg [r12], esi
0x140011c11  jz      short loc_140011C17
0x140011c13  mov     ebx, eax
0x140011c15  jmp     short loc_140011BC0
0x140011c17  test    edx, edx
0x140011c19  jnz     short loc_140011C37
0x140011c1b  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x140011c22  test    rax, rax
0x140011c25  jz      short loc_140011C37
0x140011c27  movzx   edx, byte ptr [r15+1Ch]
0x140011c2c  mov     r8d, r14d
0x140011c2f  mov     rcx, r12
0x140011c32  call    _guard_dispatch_icall
0x140011c37  test    ebp, ebp
0x140011c39  jnz     short loc_140011C4D
0x140011c3b  and     esi, 0FFFFF63Eh
0x140011c41  and     edi, 9C1h
0x140011c47  or      esi, edi
0x140011c49  mov     dword ptr [rsp+48h+arg_8], esi
0x140011c4d  mov     rax, [rsp+48h+arg_8]
0x140011c52  mov     rbx, [rsp+48h+arg_10]
0x140011c57  mov     rbp, [rsp+48h+arg_18]
0x140011c5c  add     rsp, 20h
0x140011c60  pop     r15
0x140011c62  pop     r14
0x140011c64  pop     r12
0x140011c66  pop     rdi
0x140011c67  pop     rsi
0x140011c68  retn
```
