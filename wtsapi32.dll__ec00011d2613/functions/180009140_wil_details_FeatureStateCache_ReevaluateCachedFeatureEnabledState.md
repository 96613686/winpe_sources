# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x180009140`
- end: `0x180009251`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `273`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008c48`
- `0x1800093f0`

## callees

- `0x180009140`
- `0x180009298`
- `0x180016010`

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
0x180009140  mov     [rsp+arg_10], rbx
0x180009145  mov     [rsp+arg_18], rbp
0x18000914a  push    rsi
0x18000914b  push    rdi
0x18000914c  push    r12
0x18000914e  push    r14
0x180009150  push    r15
0x180009152  sub     rsp, 20h
0x180009156  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x18000915d  xor     r14d, r14d
0x180009160  mov     [rsp+48h+arg_0], r14d
0x180009165  mov     r15, r8
0x180009168  mov     [rsp+48h+arg_8], rdx
0x18000916d  mov     rbx, rdx
0x180009170  mov     r12, rcx
0x180009173  test    rax, rax
0x180009176  jz      short loc_180009180
0x180009178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000917d  mov     r14d, eax
0x180009180  lea     rdx, [rsp+48h+arg_0]
0x180009185  mov     rcx, r15
0x180009188  call    wil_details_GetCurrentFeatureEnabledState
0x18000918d  cmp     byte ptr [r15+1Ch], 0
0x180009192  mov     rdi, rax
0x180009195  jnz     short loc_1800091A4
0x180009197  mov     ecx, r14d
0x18000919a  neg     ecx
0x18000919c  sbb     ebp, ebp
0x18000919e  and     ebp, [rsp+48h+arg_0]
0x1800091a2  jmp     short loc_1800091A8
0x1800091a4  mov     ebp, [rsp+48h+arg_0]
0x1800091a8  mov     dword ptr [rsp+48h+arg_8], ebx
0x1800091ac  mov     esi, ebx
0x1800091ae  test    ebp, ebp
0x1800091b0  jz      short loc_1800091D1
0x1800091b2  mov     dword ptr [rsp+48h+arg_8], ebx
0x1800091b6  test    bl, 2
0x1800091b9  jnz     short loc_1800091D1
0x1800091bb  and     esi, 0FFFFF63Eh
0x1800091c1  mov     eax, edi
0x1800091c3  and     eax, 9C1h
0x1800091c8  or      esi, eax
0x1800091ca  or      esi, 2
0x1800091cd  mov     dword ptr [rsp+48h+arg_8], esi
0x1800091d1  mov     edx, ebx
0x1800091d3  and     edx, 4
0x1800091d6  jnz     short loc_1800091F1
0x1800091d8  mov     eax, esi
0x1800091da  mov     ecx, edi
0x1800091dc  and     ecx, 400h
0x1800091e2  btr     eax, 0Ah
0x1800091e6  mov     esi, ecx
0x1800091e8  or      esi, eax
0x1800091ea  or      esi, 4
0x1800091ed  mov     dword ptr [rsp+48h+arg_8], esi
0x1800091f1  mov     eax, ebx
0x1800091f3  lock cmpxchg [r12], esi
0x1800091f9  jz      short loc_1800091FF
0x1800091fb  mov     ebx, eax
0x1800091fd  jmp     short loc_1800091A8
0x1800091ff  test    edx, edx
0x180009201  jnz     short loc_18000921F
0x180009203  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x18000920a  test    rax, rax
0x18000920d  jz      short loc_18000921F
0x18000920f  movzx   edx, byte ptr [r15+1Ch]
0x180009214  mov     r8d, r14d
0x180009217  mov     rcx, r12
0x18000921a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000921f  test    ebp, ebp
0x180009221  jnz     short loc_180009235
0x180009223  and     esi, 0FFFFF63Eh
0x180009229  and     edi, 9C1h
0x18000922f  or      esi, edi
0x180009231  mov     dword ptr [rsp+48h+arg_8], esi
0x180009235  mov     rax, [rsp+48h+arg_8]
0x18000923a  mov     rbx, [rsp+48h+arg_10]
0x18000923f  mov     rbp, [rsp+48h+arg_18]
0x180009244  add     rsp, 20h
0x180009248  pop     r15
0x18000924a  pop     r14
0x18000924c  pop     r12
0x18000924e  pop     rdi
0x18000924f  pop     rsi
0x180009250  retn
```
