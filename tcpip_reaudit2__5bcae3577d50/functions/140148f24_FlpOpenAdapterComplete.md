# FlpOpenAdapterComplete

- ea: `0x140148f24`
- end: `0x1401492e9`
- name: `FlpOpenAdapterComplete`
- size: `965`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140147f80`

## callees

- `0x1400c4ba0`
- `0x1400c4cec`
- `0x1400c5fe4`
- `0x1400c6448`
- `0x1400c64e0`
- `0x1400c83b4`
- `0x140116c94`
- `0x1401174c0`
- `0x1401280fc`
- `0x140148728`
- `0x140148f24`
- `0x1401bf700`

## import_xrefs

- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x140148f88`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x14014913b`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x140148f88`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x14014913b`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401492c2`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401492c2`
- `NETIO!NetioRegisterTriageDumpDataCallback` at `0x14014917a`
- `NETIO!NetioRegisterTriageDumpDataCallback` at `0x14014917a`
- `NETIO!NetioNcmStoreBaseSupportedSlots` at `0x140149115`
- `NETIO!NetioNcmStoreBaseSupportedSlots` at `0x140149115`
- `NDIS!NdisCloseAdapterEx` at `0x140149299`
- `NDIS!NdisCloseAdapterEx` at `0x140149299`
- `NDIS!NdisAcquireRWLockWrite` at `0x140148f5d`
- `NDIS!NdisAcquireRWLockWrite` at `0x140148f5d`
- `NDIS!NdisReleaseRWLock` at `0x140148f78`
- `NDIS!NdisReleaseRWLock` at `0x140148f78`

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
0x140148f24  mov     [rsp-38h+arg_18], rbx
0x140148f29  push    rbp
0x140148f2a  push    rsi
0x140148f2b  push    rdi
0x140148f2c  push    r12
0x140148f2e  push    r13
0x140148f30  push    r14
0x140148f32  push    r15
0x140148f34  mov     rbp, rsp
0x140148f37  sub     rsp, 40h
0x140148f3b  mov     r14, [rcx+20h]
0x140148f3f  lea     rdx, [rbp+LockState]; LockState
0x140148f43  xor     eax, eax
0x140148f45  mov     rbx, rcx
0x140148f48  mov     rcx, [rcx+28h]; Lock
0x140148f4c  xor     r15d, r15d
0x140148f4f  xor     r8d, r8d; Flags
0x140148f52  mov     [rbp+arg_10], r15d
0x140148f56  mov     word ptr [rbp+LockState.OldIrql], ax
0x140148f5a  mov     [rbp+LockState.Flags], al
0x140148f5d  call    cs:__imp_NdisAcquireRWLockWrite
0x140148f64  nop     dword ptr [rax+rax+00h]
0x140148f69  mov     rcx, [rbx+28h]; Lock
0x140148f6d  lea     rdx, [rbp+LockState]; LockState
0x140148f71  and     dword ptr [rbx+0C4h], 0FFFFFFFEh
0x140148f78  call    cs:__imp_NdisReleaseRWLock
0x140148f7f  nop     dword ptr [rax+rax+00h]
0x140148f84  mov     rcx, [rbx+50h]; RunRefCacheAware
0x140148f88  call    cs:__imp_ExReInitializeRundownProtectionCacheAware
0x140148f8f  nop     dword ptr [rax+rax+00h]
0x140148f94  mov     eax, [rbx+138h]
0x140148f9a  lea     esi, [r15+3]
0x140148f9e  lea     r13d, [r15+2]
0x140148fa2  mov     ecx, [r14+rax*4+1E4h]
0x140148faa  mov     [rbx+138h], ecx
0x140148fb0  cmp     [rbx+4E0h], esi
0x140148fb6  jnz     short loc_140148FD5
0x140148fb8  cmp     [r14+5Ch], r13w
0x140148fbd  jnz     short loc_140148FD5
0x140148fbf  sub     ecx, 9
0x140148fc2  jz      short loc_140148FCE
0x140148fc4  sub     ecx, 9
0x140148fc7  jz      short loc_140148FCE
0x140148fc9  cmp     ecx, 1
0x140148fcc  jnz     short loc_140148FD5
0x140148fce  and     dword ptr [rbx+4F4h], 0FFFFFFAFh
0x140148fd5  mov     rax, [r14+188h]
0x140148fdc  mov     rcx, rbx
0x140148fdf  call    _guard_dispatch_icall
0x140148fe4  mov     edx, 4
0x140148fe9  mov     edi, eax
0x140148feb  lea     r12d, [rdx-3]
0x140148fef  test    eax, eax
0x140148ff1  js      loc_14014908B
0x140148ff7  mov     eax, [r14+17Ch]
0x140148ffe  cmp     [rbx+4C0h], eax
0x140149004  jnb     short loc_14014900F
0x140149006  mov     edi, 0C0000001h
0x14014900b  mov     esi, edx
0x14014900d  jmp     short loc_14014908B
0x14014900f  cmp     [r14+5Ch], r13w
0x140149014  mov     eax, 3Ch ; '<'
0x140149019  mov     [rsp+40h+var_10], r15
0x14014901e  mov     r9d, 1010Fh
0x140149024  mov     [rsp+40h+var_18], edx
0x140149028  mov     r8d, r12d
0x14014902b  lea     ecx, [rax-14h]
0x14014902e  cmovnz  eax, ecx
0x140149031  xor     edx, edx
0x140149033  mov     [rbp+arg_10], eax
0x140149036  mov     rcx, rbx
0x140149039  lea     rax, [rbp+arg_10]
0x14014903d  mov     [rsp+40h+Timeout], rax
0x140149042  call    FlpNdisRequestUnderReference
0x140149047  mov     edi, eax
0x140149049  test    eax, eax
0x14014904b  jns     short loc_140149054
0x14014904d  mov     esi, 5
0x140149052  jmp     short loc_14014908B
0x140149054  lea     rax, [rbx+4F8h]
0x14014905b  mov     [rsp+40h+var_10], r15
0x140149060  mov     [rsp+40h+var_18], 4
0x140149068  mov     r9d, 1010Eh
0x14014906e  mov     r8d, r12d
0x140149071  mov     [rsp+40h+Timeout], rax
0x140149076  xor     edx, edx
0x140149078  mov     rcx, rbx
0x14014907b  call    FlpNdisRequestUnderReference
0x140149080  mov     edi, eax
0x140149082  test    eax, eax
0x140149084  jns     short loc_1401490A6
0x140149086  mov     esi, 6
0x14014908b  movzx   edx, word ptr [r14+5Ch]
0x140149090  mov     r9d, edi
0x140149093  mov     ecx, [rbx+498h]
0x140149099  mov     r8d, esi
0x14014909c  call    FlpLogInterfaceBindFailure
0x1401490a1  jmp     loc_140149226
0x1401490a6  cmp     dword ptr [rbx+4E4h], 18h
0x1401490ad  jz      short loc_1401490B7
0x1401490af  mov     rcx, rbx
0x1401490b2  call    FlpEnableWakeupCapabilities
0x1401490b7  lea     rdx, [rbx+528h]
0x1401490be  mov     rcx, rbx
0x1401490c1  call    FlpModifyTaskOffloadCapabilities
0x1401490c6  cmp     [rbx+321h], r13b
0x1401490cd  jnz     short loc_140149121
0x1401490cf  mov     eax, [rbx+328h]
0x1401490d5  test    r12b, al
0x1401490d8  jz      short loc_140149121
0x1401490da  mov     ecx, [rbx+32Ch]
0x1401490e0  cmp     ecx, 10h
0x1401490e3  jb      short loc_140149121
0x1401490e5  cmp     dword ptr [rbx+330h], 4Ah ; 'J'
0x1401490ec  jb      short loc_140149121
0x1401490ee  mov     eax, [rbx+34Ch]
0x1401490f4  sub     eax, esi
0x1401490f6  cmp     eax, r12d
0x1401490f9  ja      short loc_140149121
0x1401490fb  mov     eax, [rbx+358h]
0x140149101  and     eax, esi
0x140149103  cmp     al, sil
0x140149106  jnz     short loc_140149121
0x140149108  mov     eax, [rbx+33Ch]
0x14014910e  and     eax, esi
0x140149110  cmp     al, sil
0x140149113  jnz     short loc_140149121
0x140149115  call    cs:__imp_NetioNcmStoreBaseSupportedSlots
0x14014911c  nop     dword ptr [rax+rax+00h]
0x140149121  mov     rcx, [rbx+120h]; Entry
0x140149128  call    FlpAddInterface
0x14014912d  mov     edi, eax
0x14014912f  test    eax, eax
0x140149131  js      loc_140149226
0x140149137  mov     rcx, [rbx+48h]; RunRefCacheAware
0x14014913b  call    cs:__imp_ExReInitializeRundownProtectionCacheAware
0x140149142  nop     dword ptr [rax+rax+00h]
0x140149147  mov     rcx, [rbx+20h]
0x14014914b  mov     rdx, rbx
0x14014914e  add     rcx, 1B8h
0x140149155  call    FlpInsertInterface
0x14014915a  lea     rax, aFlif; "FLIf"
0x140149161  mov     r9, rbx
0x140149164  lea     rcx, [rbx+440h]
0x14014916b  mov     [rsp+40h+Timeout], rax
0x140149170  lea     r8, FlpPopulateInterfaceTriageDumpData
0x140149177  mov     edx, r12d
0x14014917a  call    cs:__imp_NetioRegisterTriageDumpDataCallback
0x140149181  nop     dword ptr [rax+rax+00h]
0x140149186  cmp     [r14+290h], r15b
0x14014918d  jz      short loc_14014919F
0x14014918f  mov     rcx, rbx
0x140149192  call    FlpProcessIsolationConfiguration
0x140149197  test    eax, eax
0x140149199  mov     edi, eax
0x14014919b  cmovs   edi, r15d
0x14014919f  mov     eax, [rbx+138h]
0x1401491a5  cmp     eax, 13h
0x1401491a8  ja      short loc_14014921E
0x1401491aa  mov     ecx, 0C0201h
0x1401491af  bt      ecx, eax
0x1401491b2  jnb     short loc_14014921E
0x1401491b4  cmp     [rbx+3B0h], r15d
0x1401491bb  jnz     short loc_14014921E
0x1401491bd  mov     [rsp+40h+var_10], r15
0x1401491c2  lea     rax, [rbp+arg_0]
0x1401491c6  mov     [rsp+40h+var_18], r13d
0x1401491cb  mov     r9d, 10110h
0x1401491d1  xor     r8d, r8d
0x1401491d4  mov     [rsp+40h+Timeout], rax
0x1401491d9  xor     edx, edx
0x1401491db  mov     word ptr [rbp+arg_0], r15w
0x1401491e0  mov     rcx, rbx
0x1401491e3  call    FlpNdisRequestUnderReference
0x1401491e8  test    eax, eax
0x1401491ea  js      short loc_14014921E
0x1401491ec  mov     eax, 61Eh
0x1401491f1  cmp     word ptr [rbp+arg_0], ax
0x1401491f5  jb      short loc_14014921E
0x1401491f7  mov     [rbx+5Ch], r12b
0x1401491fb  cmp     [rbx+5B8h], r15b
0x140149202  jnz     short loc_140149211
0x140149204  cmp     [rbx+5B9h], r15b
0x14014920b  jnz     short loc_140149211
0x14014920d  mov     [rbx+5Eh], r12b
0x140149211  cmp     [rbx+600h], r15b
0x140149218  jnz     short loc_14014921E
0x14014921a  mov     [rbx+5Dh], r12b
0x14014921e  test    edi, edi
0x140149220  jns     loc_1401492CE
0x140149226  mov     eax, [rbx+3D0h]
0x14014922c  test    r12b, al
0x14014922f  jz      short loc_140149245
0x140149231  mov     rax, [r14+278h]
0x140149238  mov     edx, 8
0x14014923d  mov     rcx, rbx
0x140149240  call    _guard_dispatch_icall
0x140149245  mov     eax, [rbx+394h]
0x14014924b  test    eax, eax
0x14014924d  jz      short loc_140149282
0x14014924f  mov     [rbp+arg_0], eax
0x140149252  mov     r9d, 0FD01010Bh
0x140149258  lea     rax, [rbp+arg_0]
0x14014925c  mov     [rsp+40h+var_10], r15
0x140149261  mov     [rsp+40h+var_18], 4
0x140149269  mov     r8d, r12d
0x14014926c  xor     edx, edx
0x14014926e  mov     [rsp+40h+Timeout], rax
0x140149273  mov     rcx, rbx
0x140149276  call    FlpNdisRequest
0x14014927b  mov     [rbx+394h], r15d
0x140149282  mov     rcx, rbx
0x140149285  call    FlpCleanupPortCoalescedWakePatterns
0x14014928a  mov     rcx, rbx
0x14014928d  call    FlpCleanupL2UnicastWakePatterns
0x140149292  mov     rcx, [rbx+500h]; NdisBindingHandle
0x140149299  call    cs:__imp_NdisCloseAdapterEx
0x1401492a0  nop     dword ptr [rax+rax+00h]
0x1401492a5  cmp     eax, 103h
0x1401492aa  jnz     short loc_1401492CE
0x1401492ac  xor     r9d, r9d; Alertable
0x1401492af  mov     [rsp+40h+Timeout], r15; Timeout
0x1401492b4  lea     rcx, [rbx+0A8h]; Object
0x1401492bb  xor     r8d, r8d; WaitMode
0x1401492be  lea     edx, [r9+6]; WaitReason
0x1401492c2  call    cs:__imp_KeWaitForSingleObject
0x1401492c9  nop     dword ptr [rax+rax+00h]
0x1401492ce  mov     rbx, [rsp+40h+arg_18]
0x1401492d6  mov     eax, edi
0x1401492d8  add     rsp, 40h
0x1401492dc  pop     r15
0x1401492de  pop     r14
0x1401492e0  pop     r13
0x1401492e2  pop     r12
0x1401492e4  pop     rdi
0x1401492e5  pop     rsi
0x1401492e6  pop     rbp
0x1401492e7  retn
```
