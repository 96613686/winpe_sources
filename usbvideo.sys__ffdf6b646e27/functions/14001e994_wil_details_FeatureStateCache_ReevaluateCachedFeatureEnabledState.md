# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x14001e994`
- end: `0x14001eaa6`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `274`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140017148`
- `0x14001eb00`

## callees

- `0x14001e994`
- `0x14001eb00`
- `0x140040a70`

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
0x14001e994  mov     [rsp+arg_10], rbx
0x14001e999  mov     [rsp+arg_18], rbp
0x14001e99e  push    rsi
0x14001e99f  push    rdi
0x14001e9a0  push    r12
0x14001e9a2  push    r14
0x14001e9a4  push    r15
0x14001e9a6  sub     rsp, 20h
0x14001e9aa  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x14001e9b1  xor     r14d, r14d
0x14001e9b4  mov     [rsp+48h+arg_0], r14d
0x14001e9b9  mov     r15, r8
0x14001e9bc  mov     [rsp+48h+arg_8], rdx
0x14001e9c1  mov     rbx, rdx
0x14001e9c4  mov     r12, rcx
0x14001e9c7  test    rax, rax
0x14001e9ca  jz      short loc_14001E9D4
0x14001e9cc  call    _guard_dispatch_icall
0x14001e9d1  mov     r14d, eax
0x14001e9d4  lea     rdx, [rsp+48h+arg_0]
0x14001e9d9  mov     rcx, r15
0x14001e9dc  call    wil_details_GetCurrentFeatureEnabledState
0x14001e9e1  cmp     byte ptr [r15+1Ch], 0
0x14001e9e6  mov     rdi, rax
0x14001e9e9  jnz     short loc_14001E9F8
0x14001e9eb  mov     ecx, r14d
0x14001e9ee  neg     ecx
0x14001e9f0  sbb     ebp, ebp
0x14001e9f2  and     ebp, [rsp+48h+arg_0]
0x14001e9f6  jmp     short loc_14001E9FC
0x14001e9f8  mov     ebp, [rsp+48h+arg_0]
0x14001e9fc  mov     dword ptr [rsp+48h+arg_8], ebx
0x14001ea00  mov     esi, ebx
0x14001ea02  test    ebp, ebp
0x14001ea04  jz      short loc_14001EA25
0x14001ea06  mov     dword ptr [rsp+48h+arg_8], ebx
0x14001ea0a  test    bl, 2
0x14001ea0d  jnz     short loc_14001EA25
0x14001ea0f  and     esi, 0FFFFF63Eh
0x14001ea15  mov     eax, edi
0x14001ea17  and     eax, 9C1h
0x14001ea1c  or      esi, eax
0x14001ea1e  or      esi, 2
0x14001ea21  mov     dword ptr [rsp+48h+arg_8], esi
0x14001ea25  mov     edx, ebx
0x14001ea27  and     edx, 4
0x14001ea2a  jnz     short loc_14001EA45
0x14001ea2c  mov     eax, esi
0x14001ea2e  mov     ecx, edi
0x14001ea30  and     ecx, 400h
0x14001ea36  btr     eax, 0Ah
0x14001ea3a  mov     esi, ecx
0x14001ea3c  or      esi, eax
0x14001ea3e  or      esi, 4
0x14001ea41  mov     dword ptr [rsp+48h+arg_8], esi
0x14001ea45  mov     eax, ebx
0x14001ea47  lock cmpxchg [r12], esi
0x14001ea4d  jz      short loc_14001EA53
0x14001ea4f  mov     ebx, eax
0x14001ea51  jmp     short loc_14001E9FC
0x14001ea53  test    edx, edx
0x14001ea55  jnz     short loc_14001EA73
0x14001ea57  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x14001ea5e  test    rax, rax
0x14001ea61  jz      short loc_14001EA73
0x14001ea63  movzx   edx, byte ptr [r15+1Ch]
0x14001ea68  mov     r8d, r14d
0x14001ea6b  mov     rcx, r12
0x14001ea6e  call    _guard_dispatch_icall
0x14001ea73  test    ebp, ebp
0x14001ea75  jnz     short loc_14001EA89
0x14001ea77  and     esi, 0FFFFF63Eh
0x14001ea7d  and     edi, 9C1h
0x14001ea83  or      esi, edi
0x14001ea85  mov     dword ptr [rsp+48h+arg_8], esi
0x14001ea89  mov     rax, [rsp+48h+arg_8]
0x14001ea8e  mov     rbx, [rsp+48h+arg_10]
0x14001ea93  mov     rbp, [rsp+48h+arg_18]
0x14001ea98  add     rsp, 20h
0x14001ea9c  pop     r15
0x14001ea9e  pop     r14
0x14001eaa0  pop     r12
0x14001eaa2  pop     rdi
0x14001eaa3  pop     rsi
0x14001eaa4  retn
```
