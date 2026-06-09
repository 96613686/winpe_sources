# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x140017cfc`
- end: `0x140017e0e`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `274`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140017e6c`
- `0x140017fbc`

## callees

- `0x140017cfc`
- `0x140017e6c`
- `0x14001ef70`

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
0x140017cfc  mov     [rsp+arg_10], rbx
0x140017d01  mov     [rsp+arg_18], rbp
0x140017d06  push    rsi
0x140017d07  push    rdi
0x140017d08  push    r12
0x140017d0a  push    r14
0x140017d0c  push    r15
0x140017d0e  sub     rsp, 20h
0x140017d12  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x140017d19  xor     r14d, r14d
0x140017d1c  mov     [rsp+48h+arg_0], r14d
0x140017d21  mov     r15, r8
0x140017d24  mov     [rsp+48h+arg_8], rdx
0x140017d29  mov     rbx, rdx
0x140017d2c  mov     r12, rcx
0x140017d2f  test    rax, rax
0x140017d32  jz      short loc_140017D3C
0x140017d34  call    _guard_dispatch_icall
0x140017d39  mov     r14d, eax
0x140017d3c  lea     rdx, [rsp+48h+arg_0]
0x140017d41  mov     rcx, r15
0x140017d44  call    wil_details_GetCurrentFeatureEnabledState
0x140017d49  cmp     byte ptr [r15+1Ch], 0
0x140017d4e  mov     rdi, rax
0x140017d51  jnz     short loc_140017D60
0x140017d53  mov     ecx, r14d
0x140017d56  neg     ecx
0x140017d58  sbb     ebp, ebp
0x140017d5a  and     ebp, [rsp+48h+arg_0]
0x140017d5e  jmp     short loc_140017D64
0x140017d60  mov     ebp, [rsp+48h+arg_0]
0x140017d64  mov     dword ptr [rsp+48h+arg_8], ebx
0x140017d68  mov     esi, ebx
0x140017d6a  test    ebp, ebp
0x140017d6c  jz      short loc_140017D8D
0x140017d6e  mov     dword ptr [rsp+48h+arg_8], ebx
0x140017d72  test    bl, 2
0x140017d75  jnz     short loc_140017D8D
0x140017d77  and     esi, 0FFFFF63Eh
0x140017d7d  mov     eax, edi
0x140017d7f  and     eax, 9C1h
0x140017d84  or      esi, eax
0x140017d86  or      esi, 2
0x140017d89  mov     dword ptr [rsp+48h+arg_8], esi
0x140017d8d  mov     edx, ebx
0x140017d8f  and     edx, 4
0x140017d92  jnz     short loc_140017DAD
0x140017d94  mov     eax, esi
0x140017d96  mov     ecx, edi
0x140017d98  and     ecx, 400h
0x140017d9e  btr     eax, 0Ah
0x140017da2  mov     esi, ecx
0x140017da4  or      esi, eax
0x140017da6  or      esi, 4
0x140017da9  mov     dword ptr [rsp+48h+arg_8], esi
0x140017dad  mov     eax, ebx
0x140017daf  lock cmpxchg [r12], esi
0x140017db5  jz      short loc_140017DBB
0x140017db7  mov     ebx, eax
0x140017db9  jmp     short loc_140017D64
0x140017dbb  test    edx, edx
0x140017dbd  jnz     short loc_140017DDB
0x140017dbf  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x140017dc6  test    rax, rax
0x140017dc9  jz      short loc_140017DDB
0x140017dcb  movzx   edx, byte ptr [r15+1Ch]
0x140017dd0  mov     r8d, r14d
0x140017dd3  mov     rcx, r12
0x140017dd6  call    _guard_dispatch_icall
0x140017ddb  test    ebp, ebp
0x140017ddd  jnz     short loc_140017DF1
0x140017ddf  and     esi, 0FFFFF63Eh
0x140017de5  and     edi, 9C1h
0x140017deb  or      esi, edi
0x140017ded  mov     dword ptr [rsp+48h+arg_8], esi
0x140017df1  mov     rax, [rsp+48h+arg_8]
0x140017df6  mov     rbx, [rsp+48h+arg_10]
0x140017dfb  mov     rbp, [rsp+48h+arg_18]
0x140017e00  add     rsp, 20h
0x140017e04  pop     r15
0x140017e06  pop     r14
0x140017e08  pop     r12
0x140017e0a  pop     rdi
0x140017e0b  pop     rsi
0x140017e0c  retn
```
