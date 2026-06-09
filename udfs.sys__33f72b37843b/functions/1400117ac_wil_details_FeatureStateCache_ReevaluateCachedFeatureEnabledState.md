# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x1400117ac`
- end: `0x1400118be`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `274`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140011270`
- `0x140011a20`

## callees

- `0x1400117ac`
- `0x140011908`
- `0x14001bd10`

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
0x1400117ac  mov     [rsp+arg_10], rbx
0x1400117b1  mov     [rsp+arg_18], rbp
0x1400117b6  push    rsi
0x1400117b7  push    rdi
0x1400117b8  push    r12
0x1400117ba  push    r14
0x1400117bc  push    r15
0x1400117be  sub     rsp, 20h
0x1400117c2  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x1400117c9  xor     r14d, r14d
0x1400117cc  mov     [rsp+48h+arg_0], r14d
0x1400117d1  mov     r15, r8
0x1400117d4  mov     [rsp+48h+arg_8], rdx
0x1400117d9  mov     rbx, rdx
0x1400117dc  mov     r12, rcx
0x1400117df  test    rax, rax
0x1400117e2  jz      short loc_1400117EC
0x1400117e4  call    _guard_dispatch_icall
0x1400117e9  mov     r14d, eax
0x1400117ec  lea     rdx, [rsp+48h+arg_0]
0x1400117f1  mov     rcx, r15
0x1400117f4  call    wil_details_GetCurrentFeatureEnabledState
0x1400117f9  cmp     byte ptr [r15+1Ch], 0
0x1400117fe  mov     rdi, rax
0x140011801  jnz     short loc_140011810
0x140011803  mov     ecx, r14d
0x140011806  neg     ecx
0x140011808  sbb     ebp, ebp
0x14001180a  and     ebp, [rsp+48h+arg_0]
0x14001180e  jmp     short loc_140011814
0x140011810  mov     ebp, [rsp+48h+arg_0]
0x140011814  mov     dword ptr [rsp+48h+arg_8], ebx
0x140011818  mov     esi, ebx
0x14001181a  test    ebp, ebp
0x14001181c  jz      short loc_14001183D
0x14001181e  mov     dword ptr [rsp+48h+arg_8], ebx
0x140011822  test    bl, 2
0x140011825  jnz     short loc_14001183D
0x140011827  and     esi, 0FFFFF63Eh
0x14001182d  mov     eax, edi
0x14001182f  and     eax, 9C1h
0x140011834  or      esi, eax
0x140011836  or      esi, 2
0x140011839  mov     dword ptr [rsp+48h+arg_8], esi
0x14001183d  mov     edx, ebx
0x14001183f  and     edx, 4
0x140011842  jnz     short loc_14001185D
0x140011844  mov     eax, esi
0x140011846  mov     ecx, edi
0x140011848  and     ecx, 400h
0x14001184e  btr     eax, 0Ah
0x140011852  mov     esi, ecx
0x140011854  or      esi, eax
0x140011856  or      esi, 4
0x140011859  mov     dword ptr [rsp+48h+arg_8], esi
0x14001185d  mov     eax, ebx
0x14001185f  lock cmpxchg [r12], esi
0x140011865  jz      short loc_14001186B
0x140011867  mov     ebx, eax
0x140011869  jmp     short loc_140011814
0x14001186b  test    edx, edx
0x14001186d  jnz     short loc_14001188B
0x14001186f  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x140011876  test    rax, rax
0x140011879  jz      short loc_14001188B
0x14001187b  movzx   edx, byte ptr [r15+1Ch]
0x140011880  mov     r8d, r14d
0x140011883  mov     rcx, r12
0x140011886  call    _guard_dispatch_icall
0x14001188b  test    ebp, ebp
0x14001188d  jnz     short loc_1400118A1
0x14001188f  and     esi, 0FFFFF63Eh
0x140011895  and     edi, 9C1h
0x14001189b  or      esi, edi
0x14001189d  mov     dword ptr [rsp+48h+arg_8], esi
0x1400118a1  mov     rax, [rsp+48h+arg_8]
0x1400118a6  mov     rbx, [rsp+48h+arg_10]
0x1400118ab  mov     rbp, [rsp+48h+arg_18]
0x1400118b0  add     rsp, 20h
0x1400118b4  pop     r15
0x1400118b6  pop     r14
0x1400118b8  pop     r12
0x1400118ba  pop     rdi
0x1400118bb  pop     rsi
0x1400118bc  retn
```
