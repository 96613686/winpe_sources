# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x14001eb1c`
- end: `0x14001ec2f`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `275`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140019420`
- `0x14001e5b8`

## callees

- `0x14001eb1c`
- `0x14001ec8c`
- `0x140039780`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState(
        volatile signed __int32 *a1,
        __int64 a2,
        __int64 a3)
{
  unsigned int v3; // r14d
  signed __int32 v5; // edi
  __int16 CurrentFeatureEnabledState; // bx
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
    LODWORD(v13) = v9 & 0xFFFFF63E | CurrentFeatureEnabledState & 0x9C1;
  return v13;
}

```

## disassembly

```asm
0x14001eb1c  mov     [rsp+arg_10], rbx
0x14001eb21  mov     [rsp+arg_18], rbp
0x14001eb26  push    rsi
0x14001eb27  push    rdi
0x14001eb28  push    r12
0x14001eb2a  push    r14
0x14001eb2c  push    r15
0x14001eb2e  sub     rsp, 20h
0x14001eb32  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x14001eb39  xor     r14d, r14d
0x14001eb3c  mov     [rsp+48h+arg_0], r14d
0x14001eb41  mov     r15, r8
0x14001eb44  mov     [rsp+48h+arg_8], rdx
0x14001eb49  mov     rdi, rdx
0x14001eb4c  mov     r12, rcx
0x14001eb4f  test    rax, rax
0x14001eb52  jz      short loc_14001EB5C
0x14001eb54  call    _guard_dispatch_icall
0x14001eb59  mov     r14d, eax
0x14001eb5c  lea     rdx, [rsp+48h+arg_0]
0x14001eb61  mov     rcx, r15
0x14001eb64  call    wil_details_GetCurrentFeatureEnabledState
0x14001eb69  cmp     byte ptr [r15+1Ch], 0
0x14001eb6e  mov     rbx, rax
0x14001eb71  jnz     short loc_14001EB80
0x14001eb73  mov     ecx, r14d
0x14001eb76  neg     ecx
0x14001eb78  sbb     ebp, ebp
0x14001eb7a  and     ebp, [rsp+48h+arg_0]
0x14001eb7e  jmp     short loc_14001EB84
0x14001eb80  mov     ebp, [rsp+48h+arg_0]
0x14001eb84  mov     dword ptr [rsp+48h+arg_8], edi
0x14001eb88  mov     esi, edi
0x14001eb8a  test    ebp, ebp
0x14001eb8c  jz      short loc_14001EBAE
0x14001eb8e  mov     dword ptr [rsp+48h+arg_8], edi
0x14001eb92  test    dil, 2
0x14001eb96  jnz     short loc_14001EBAE
0x14001eb98  and     esi, 0FFFFF63Eh
0x14001eb9e  mov     eax, ebx
0x14001eba0  and     eax, 9C1h
0x14001eba5  or      esi, eax
0x14001eba7  or      esi, 2
0x14001ebaa  mov     dword ptr [rsp+48h+arg_8], esi
0x14001ebae  mov     edx, edi
0x14001ebb0  and     edx, 4
0x14001ebb3  jnz     short loc_14001EBCE
0x14001ebb5  mov     eax, esi
0x14001ebb7  mov     ecx, ebx
0x14001ebb9  and     ecx, 400h
0x14001ebbf  btr     eax, 0Ah
0x14001ebc3  mov     esi, ecx
0x14001ebc5  or      esi, eax
0x14001ebc7  or      esi, 4
0x14001ebca  mov     dword ptr [rsp+48h+arg_8], esi
0x14001ebce  mov     eax, edi
0x14001ebd0  lock cmpxchg [r12], esi
0x14001ebd6  jz      short loc_14001EBDC
0x14001ebd8  mov     edi, eax
0x14001ebda  jmp     short loc_14001EB84
0x14001ebdc  test    edx, edx
0x14001ebde  jnz     short loc_14001EBFC
0x14001ebe0  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x14001ebe7  test    rax, rax
0x14001ebea  jz      short loc_14001EBFC
0x14001ebec  movzx   edx, byte ptr [r15+1Ch]
0x14001ebf1  mov     r8d, r14d
0x14001ebf4  mov     rcx, r12
0x14001ebf7  call    _guard_dispatch_icall
0x14001ebfc  test    ebp, ebp
0x14001ebfe  jnz     short loc_14001EC12
0x14001ec00  and     ebx, 9C1h
0x14001ec06  and     esi, 0FFFFF63Eh
0x14001ec0c  or      ebx, esi
0x14001ec0e  mov     dword ptr [rsp+48h+arg_8], ebx
0x14001ec12  mov     rax, [rsp+48h+arg_8]
0x14001ec17  mov     rbx, [rsp+48h+arg_10]
0x14001ec1c  mov     rbp, [rsp+48h+arg_18]
0x14001ec21  add     rsp, 20h
0x14001ec25  pop     r15
0x14001ec27  pop     r14
0x14001ec29  pop     r12
0x14001ec2b  pop     rdi
0x14001ec2c  pop     rsi
0x14001ec2d  retn
```
