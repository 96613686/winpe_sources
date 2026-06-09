# FlpOpenAdapterComplete

- ea: `0x14014b014`
- end: `0x14014b3d9`
- name: `FlpOpenAdapterComplete`
- size: `965`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14014a070`

## callees

- `0x1400fb308`
- `0x1401020f0`
- `0x14010223c`
- `0x140103024`
- `0x140103488`
- `0x140103520`
- `0x1401213d4`
- `0x140121860`
- `0x140131bfc`
- `0x14014a818`
- `0x14014b014`
- `0x1401c1200`

## import_xrefs

- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x14014b078`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x14014b22b`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x14014b078`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x14014b22b`
- `ntoskrnl!KeWaitForSingleObject` at `0x14014b3b2`
- `ntoskrnl!KeWaitForSingleObject` at `0x14014b3b2`
- `NETIO!NetioRegisterTriageDumpDataCallback` at `0x14014b26a`
- `NETIO!NetioRegisterTriageDumpDataCallback` at `0x14014b26a`
- `NETIO!NetioNcmStoreBaseSupportedSlots` at `0x14014b205`
- `NETIO!NetioNcmStoreBaseSupportedSlots` at `0x14014b205`
- `NDIS!NdisCloseAdapterEx` at `0x14014b389`
- `NDIS!NdisCloseAdapterEx` at `0x14014b389`
- `NDIS!NdisAcquireRWLockWrite` at `0x14014b04d`
- `NDIS!NdisAcquireRWLockWrite` at `0x14014b04d`
- `NDIS!NdisReleaseRWLock` at `0x14014b068`
- `NDIS!NdisReleaseRWLock` at `0x14014b068`

## pseudocode

```c
__int64 __fastcall FlpOpenAdapterComplete(__int64 a1)
{
  __int64 v1; // r14
  struct _NDIS_RW_LOCK_EX *v3; // rcx
  struct _NDIS_RW_LOCK_EX *v4; // rcx
  unsigned int v5; // esi
  int v6; // ecx
  int v7; // ecx
  int v8; // edi
  int v9; // eax
  unsigned int v10; // eax
  int v11; // ecx
  int v13; // [rsp+80h] [rbp+40h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+88h] [rbp+48h] BYREF
  int v15; // [rsp+90h] [rbp+50h] BYREF

  v1 = *(_QWORD *)(a1 + 32);
  v3 = *(struct _NDIS_RW_LOCK_EX **)(a1 + 40);
  v15 = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  NdisAcquireRWLockWrite(v3, &LockState, 0);
  v4 = *(struct _NDIS_RW_LOCK_EX **)(a1 + 40);
  *(_DWORD *)(a1 + 196) &= ~1u;
  NdisReleaseRWLock(v4, &LockState);
  ExReInitializeRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 80));
  v5 = 3;
  v6 = *(_DWORD *)(v1 + 4LL * *(unsigned int *)(a1 + 312) + 484);
  *(_DWORD *)(a1 + 312) = v6;
  if ( *(_DWORD *)(a1 + 1248) == 3 && *(_WORD *)(v1 + 92) == 2 )
  {
    v7 = v6 - 9;
    if ( !v7 || (unsigned int)(v7 - 9) <= 1 )
      *(_DWORD *)(a1 + 1268) &= 0xFFFFFFAF;
  }
  v8 = (*(__int64 (__fastcall **)(__int64))(v1 + 392))(a1);
  if ( v8 < 0 )
    goto LABEL_15;
  if ( *(_DWORD *)(a1 + 1216) < *(_DWORD *)(v1 + 380) )
  {
    v8 = -1073741823;
    v5 = 4;
LABEL_15:
    FlpLogInterfaceBindFailure(*(unsigned int *)(a1 + 1176), *(unsigned __int16 *)(v1 + 92), v5, (unsigned int)v8);
LABEL_41:
    if ( (*(_DWORD *)(a1 + 976) & 1) != 0 )
      (*(void (__fastcall **)(__int64, __int64))(v1 + 632))(a1, 8);
    if ( *(_DWORD *)(a1 + 916) )
    {
      v13 = *(_DWORD *)(a1 + 916);
      FlpNdisRequest(a1, 0, 1, -50265845, (__int64)&v13, 4, 0);
      *(_DWORD *)(a1 + 916) = 0;
    }
    FlpCleanupPortCoalescedWakePatterns(a1);
    FlpCleanupL2UnicastWakePatterns(a1);
    if ( NdisCloseAdapterEx(*(NDIS_HANDLE *)(a1 + 1280)) == 259 )
      KeWaitForSingleObject((PVOID)(a1 + 168), UserRequest, 0, 0, 0);
    return (unsigned int)v8;
  }
  v9 = 60;
  if ( *(_WORD *)(v1 + 92) != 2 )
    v9 = 40;
  v15 = v9;
  v8 = FlpNdisRequestUnderReference(a1, 0, 1, 65807, (__int64)&v15, 4, 0);
  if ( v8 < 0 )
  {
    v5 = 5;
    goto LABEL_15;
  }
  v8 = FlpNdisRequestUnderReference(a1, 0, 1, 65806, a1 + 1272, 4, 0);
  if ( v8 < 0 )
  {
    v5 = 6;
    goto LABEL_15;
  }
  if ( *(_DWORD *)(a1 + 1252) != 24 )
    FlpEnableWakeupCapabilities(a1);
  FlpModifyTaskOffloadCapabilities(a1, a1 + 1320);
  if ( *(_BYTE *)(a1 + 801) == 2
    && (*(_DWORD *)(a1 + 808) & 1) != 0
    && *(_DWORD *)(a1 + 812) >= 0x10u
    && *(_DWORD *)(a1 + 816) >= 0x4Au
    && (unsigned int)(*(_DWORD *)(a1 + 844) - 3) <= 1
    && (*(_BYTE *)(a1 + 856) & 3) == 3
    && (*(_BYTE *)(a1 + 828) & 3) == 3 )
  {
    NetioNcmStoreBaseSupportedSlots();
  }
  v8 = FlpAddInterface(*(PRTL_DYNAMIC_HASH_TABLE_ENTRY *)(a1 + 288));
  if ( v8 < 0 )
    goto LABEL_41;
  ExReInitializeRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 72));
  FlpInsertInterface(*(_QWORD *)(a1 + 32) + 440LL, a1);
  NetioRegisterTriageDumpDataCallback(a1 + 1088, 1, FlpPopulateInterfaceTriageDumpData, a1, "FLIf");
  if ( *(_BYTE *)(v1 + 656) )
  {
    v8 = FlpProcessIsolationConfiguration(a1);
    if ( v8 < 0 )
      v8 = 0;
  }
  v10 = *(_DWORD *)(a1 + 312);
  if ( v10 <= 0x13 )
  {
    v11 = 786945;
    if ( _bittest(&v11, v10) )
    {
      if ( !*(_DWORD *)(a1 + 944) )
      {
        LOWORD(v13) = 0;
        if ( (int)FlpNdisRequestUnderReference(a1, 0, 0, 65808, (__int64)&v13, 2, 0) >= 0
          && (unsigned __int16)v13 >= 0x61Eu )
        {
          *(_BYTE *)(a1 + 92) = 1;
          if ( !*(_BYTE *)(a1 + 1464) && !*(_BYTE *)(a1 + 1465) )
            *(_BYTE *)(a1 + 94) = 1;
          if ( !*(_BYTE *)(a1 + 1536) )
            *(_BYTE *)(a1 + 93) = 1;
        }
      }
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14014b014  mov     [rsp-38h+arg_18], rbx
0x14014b019  push    rbp
0x14014b01a  push    rsi
0x14014b01b  push    rdi
0x14014b01c  push    r12
0x14014b01e  push    r13
0x14014b020  push    r14
0x14014b022  push    r15
0x14014b024  mov     rbp, rsp
0x14014b027  sub     rsp, 40h
0x14014b02b  mov     r14, [rcx+20h]
0x14014b02f  lea     rdx, [rbp+LockState]; LockState
0x14014b033  xor     eax, eax
0x14014b035  mov     rbx, rcx
0x14014b038  mov     rcx, [rcx+28h]; Lock
0x14014b03c  xor     r15d, r15d
0x14014b03f  xor     r8d, r8d; Flags
0x14014b042  mov     [rbp+arg_10], r15d
0x14014b046  mov     word ptr [rbp+LockState.OldIrql], ax
0x14014b04a  mov     [rbp+LockState.Flags], al
0x14014b04d  call    cs:__imp_NdisAcquireRWLockWrite
0x14014b054  nop     dword ptr [rax+rax+00h]
0x14014b059  mov     rcx, [rbx+28h]; Lock
0x14014b05d  lea     rdx, [rbp+LockState]; LockState
0x14014b061  and     dword ptr [rbx+0C4h], 0FFFFFFFEh
0x14014b068  call    cs:__imp_NdisReleaseRWLock
0x14014b06f  nop     dword ptr [rax+rax+00h]
0x14014b074  mov     rcx, [rbx+50h]; RunRefCacheAware
0x14014b078  call    cs:__imp_ExReInitializeRundownProtectionCacheAware
0x14014b07f  nop     dword ptr [rax+rax+00h]
0x14014b084  mov     eax, [rbx+138h]
0x14014b08a  lea     esi, [r15+3]
0x14014b08e  lea     r13d, [r15+2]
0x14014b092  mov     ecx, [r14+rax*4+1E4h]
0x14014b09a  mov     [rbx+138h], ecx
0x14014b0a0  cmp     [rbx+4E0h], esi
0x14014b0a6  jnz     short loc_14014B0C5
0x14014b0a8  cmp     [r14+5Ch], r13w
0x14014b0ad  jnz     short loc_14014B0C5
0x14014b0af  sub     ecx, 9
0x14014b0b2  jz      short loc_14014B0BE
0x14014b0b4  sub     ecx, 9
0x14014b0b7  jz      short loc_14014B0BE
0x14014b0b9  cmp     ecx, 1
0x14014b0bc  jnz     short loc_14014B0C5
0x14014b0be  and     dword ptr [rbx+4F4h], 0FFFFFFAFh
0x14014b0c5  mov     rax, [r14+188h]
0x14014b0cc  mov     rcx, rbx
0x14014b0cf  call    _guard_dispatch_icall
0x14014b0d4  mov     edx, 4
0x14014b0d9  mov     edi, eax
0x14014b0db  lea     r12d, [rdx-3]
0x14014b0df  test    eax, eax
0x14014b0e1  js      loc_14014B17B
0x14014b0e7  mov     eax, [r14+17Ch]
0x14014b0ee  cmp     [rbx+4C0h], eax
0x14014b0f4  jnb     short loc_14014B0FF
0x14014b0f6  mov     edi, 0C0000001h
0x14014b0fb  mov     esi, edx
0x14014b0fd  jmp     short loc_14014B17B
0x14014b0ff  cmp     [r14+5Ch], r13w
0x14014b104  mov     eax, 3Ch ; '<'
0x14014b109  mov     [rsp+40h+var_10], r15
0x14014b10e  mov     r9d, 1010Fh
0x14014b114  mov     [rsp+40h+var_18], edx
0x14014b118  mov     r8d, r12d
0x14014b11b  lea     ecx, [rax-14h]
0x14014b11e  cmovnz  eax, ecx
0x14014b121  xor     edx, edx
0x14014b123  mov     [rbp+arg_10], eax
0x14014b126  mov     rcx, rbx
0x14014b129  lea     rax, [rbp+arg_10]
0x14014b12d  mov     [rsp+40h+Timeout], rax
0x14014b132  call    FlpNdisRequestUnderReference
0x14014b137  mov     edi, eax
0x14014b139  test    eax, eax
0x14014b13b  jns     short loc_14014B144
0x14014b13d  mov     esi, 5
0x14014b142  jmp     short loc_14014B17B
0x14014b144  lea     rax, [rbx+4F8h]
0x14014b14b  mov     [rsp+40h+var_10], r15
0x14014b150  mov     [rsp+40h+var_18], 4
0x14014b158  mov     r9d, 1010Eh
0x14014b15e  mov     r8d, r12d
0x14014b161  mov     [rsp+40h+Timeout], rax
0x14014b166  xor     edx, edx
0x14014b168  mov     rcx, rbx
0x14014b16b  call    FlpNdisRequestUnderReference
0x14014b170  mov     edi, eax
0x14014b172  test    eax, eax
0x14014b174  jns     short loc_14014B196
0x14014b176  mov     esi, 6
0x14014b17b  movzx   edx, word ptr [r14+5Ch]
0x14014b180  mov     r9d, edi
0x14014b183  mov     ecx, [rbx+498h]
0x14014b189  mov     r8d, esi
0x14014b18c  call    FlpLogInterfaceBindFailure
0x14014b191  jmp     loc_14014B316
0x14014b196  cmp     dword ptr [rbx+4E4h], 18h
0x14014b19d  jz      short loc_14014B1A7
0x14014b19f  mov     rcx, rbx
0x14014b1a2  call    FlpEnableWakeupCapabilities
0x14014b1a7  lea     rdx, [rbx+528h]
0x14014b1ae  mov     rcx, rbx
0x14014b1b1  call    FlpModifyTaskOffloadCapabilities
0x14014b1b6  cmp     [rbx+321h], r13b
0x14014b1bd  jnz     short loc_14014B211
0x14014b1bf  mov     eax, [rbx+328h]
0x14014b1c5  test    r12b, al
0x14014b1c8  jz      short loc_14014B211
0x14014b1ca  mov     ecx, [rbx+32Ch]
0x14014b1d0  cmp     ecx, 10h
0x14014b1d3  jb      short loc_14014B211
0x14014b1d5  cmp     dword ptr [rbx+330h], 4Ah ; 'J'
0x14014b1dc  jb      short loc_14014B211
0x14014b1de  mov     eax, [rbx+34Ch]
0x14014b1e4  sub     eax, esi
0x14014b1e6  cmp     eax, r12d
0x14014b1e9  ja      short loc_14014B211
0x14014b1eb  mov     eax, [rbx+358h]
0x14014b1f1  and     eax, esi
0x14014b1f3  cmp     al, sil
0x14014b1f6  jnz     short loc_14014B211
0x14014b1f8  mov     eax, [rbx+33Ch]
0x14014b1fe  and     eax, esi
0x14014b200  cmp     al, sil
0x14014b203  jnz     short loc_14014B211
0x14014b205  call    cs:__imp_NetioNcmStoreBaseSupportedSlots
0x14014b20c  nop     dword ptr [rax+rax+00h]
0x14014b211  mov     rcx, [rbx+120h]; Entry
0x14014b218  call    FlpAddInterface
0x14014b21d  mov     edi, eax
0x14014b21f  test    eax, eax
0x14014b221  js      loc_14014B316
0x14014b227  mov     rcx, [rbx+48h]; RunRefCacheAware
0x14014b22b  call    cs:__imp_ExReInitializeRundownProtectionCacheAware
0x14014b232  nop     dword ptr [rax+rax+00h]
0x14014b237  mov     rcx, [rbx+20h]
0x14014b23b  mov     rdx, rbx
0x14014b23e  add     rcx, 1B8h
0x14014b245  call    FlpInsertInterface
0x14014b24a  lea     rax, aFlif; "FLIf"
0x14014b251  mov     r9, rbx
0x14014b254  lea     rcx, [rbx+440h]
0x14014b25b  mov     [rsp+40h+Timeout], rax
0x14014b260  lea     r8, FlpPopulateInterfaceTriageDumpData
0x14014b267  mov     edx, r12d
0x14014b26a  call    cs:__imp_NetioRegisterTriageDumpDataCallback
0x14014b271  nop     dword ptr [rax+rax+00h]
0x14014b276  cmp     [r14+290h], r15b
0x14014b27d  jz      short loc_14014B28F
0x14014b27f  mov     rcx, rbx
0x14014b282  call    FlpProcessIsolationConfiguration
0x14014b287  test    eax, eax
0x14014b289  mov     edi, eax
0x14014b28b  cmovs   edi, r15d
0x14014b28f  mov     eax, [rbx+138h]
0x14014b295  cmp     eax, 13h
0x14014b298  ja      short loc_14014B30E
0x14014b29a  mov     ecx, 0C0201h
0x14014b29f  bt      ecx, eax
0x14014b2a2  jnb     short loc_14014B30E
0x14014b2a4  cmp     [rbx+3B0h], r15d
0x14014b2ab  jnz     short loc_14014B30E
0x14014b2ad  mov     [rsp+40h+var_10], r15
0x14014b2b2  lea     rax, [rbp+arg_0]
0x14014b2b6  mov     [rsp+40h+var_18], r13d
0x14014b2bb  mov     r9d, 10110h
0x14014b2c1  xor     r8d, r8d
0x14014b2c4  mov     [rsp+40h+Timeout], rax
0x14014b2c9  xor     edx, edx
0x14014b2cb  mov     word ptr [rbp+arg_0], r15w
0x14014b2d0  mov     rcx, rbx
0x14014b2d3  call    FlpNdisRequestUnderReference
0x14014b2d8  test    eax, eax
0x14014b2da  js      short loc_14014B30E
0x14014b2dc  mov     eax, 61Eh
0x14014b2e1  cmp     word ptr [rbp+arg_0], ax
0x14014b2e5  jb      short loc_14014B30E
0x14014b2e7  mov     [rbx+5Ch], r12b
0x14014b2eb  cmp     [rbx+5B8h], r15b
0x14014b2f2  jnz     short loc_14014B301
0x14014b2f4  cmp     [rbx+5B9h], r15b
0x14014b2fb  jnz     short loc_14014B301
0x14014b2fd  mov     [rbx+5Eh], r12b
0x14014b301  cmp     [rbx+600h], r15b
0x14014b308  jnz     short loc_14014B30E
0x14014b30a  mov     [rbx+5Dh], r12b
0x14014b30e  test    edi, edi
0x14014b310  jns     loc_14014B3BE
0x14014b316  mov     eax, [rbx+3D0h]
0x14014b31c  test    r12b, al
0x14014b31f  jz      short loc_14014B335
0x14014b321  mov     rax, [r14+278h]
0x14014b328  mov     edx, 8
0x14014b32d  mov     rcx, rbx
0x14014b330  call    _guard_dispatch_icall
0x14014b335  mov     eax, [rbx+394h]
0x14014b33b  test    eax, eax
0x14014b33d  jz      short loc_14014B372
0x14014b33f  mov     [rbp+arg_0], eax
0x14014b342  mov     r9d, 0FD01010Bh
0x14014b348  lea     rax, [rbp+arg_0]
0x14014b34c  mov     [rsp+40h+var_10], r15
0x14014b351  mov     [rsp+40h+var_18], 4
0x14014b359  mov     r8d, r12d
0x14014b35c  xor     edx, edx
0x14014b35e  mov     [rsp+40h+Timeout], rax
0x14014b363  mov     rcx, rbx
0x14014b366  call    FlpNdisRequest
0x14014b36b  mov     [rbx+394h], r15d
0x14014b372  mov     rcx, rbx
0x14014b375  call    FlpCleanupPortCoalescedWakePatterns
0x14014b37a  mov     rcx, rbx
0x14014b37d  call    FlpCleanupL2UnicastWakePatterns
0x14014b382  mov     rcx, [rbx+500h]; NdisBindingHandle
0x14014b389  call    cs:__imp_NdisCloseAdapterEx
0x14014b390  nop     dword ptr [rax+rax+00h]
0x14014b395  cmp     eax, 103h
0x14014b39a  jnz     short loc_14014B3BE
0x14014b39c  xor     r9d, r9d; Alertable
0x14014b39f  mov     [rsp+40h+Timeout], r15; Timeout
0x14014b3a4  lea     rcx, [rbx+0A8h]; Object
0x14014b3ab  xor     r8d, r8d; WaitMode
0x14014b3ae  lea     edx, [r9+6]; WaitReason
0x14014b3b2  call    cs:__imp_KeWaitForSingleObject
0x14014b3b9  nop     dword ptr [rax+rax+00h]
0x14014b3be  mov     rbx, [rsp+40h+arg_18]
0x14014b3c6  mov     eax, edi
0x14014b3c8  add     rsp, 40h
0x14014b3cc  pop     r15
0x14014b3ce  pop     r14
0x14014b3d0  pop     r13
0x14014b3d2  pop     r12
0x14014b3d4  pop     rdi
0x14014b3d5  pop     rsi
0x14014b3d6  pop     rbp
0x14014b3d7  retn
```
