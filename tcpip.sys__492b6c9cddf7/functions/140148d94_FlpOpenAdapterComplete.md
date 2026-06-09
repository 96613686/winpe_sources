# FlpOpenAdapterComplete

- ea: `0x140148d94`
- end: `0x140149159`
- name: `FlpOpenAdapterComplete`
- size: `965`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140147df0`

## callees

- `0x1400c4dc0`
- `0x1400c4f0c`
- `0x1400c6204`
- `0x1400c6668`
- `0x1400c6700`
- `0x1400c85d4`
- `0x140116b54`
- `0x140117380`
- `0x140127fbc`
- `0x140148598`
- `0x140148d94`
- `0x1401bf5c0`

## import_xrefs

- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x140148df8`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x140148fab`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x140148df8`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x140148fab`
- `ntoskrnl!KeWaitForSingleObject` at `0x140149132`
- `ntoskrnl!KeWaitForSingleObject` at `0x140149132`
- `NETIO!NetioRegisterTriageDumpDataCallback` at `0x140148fea`
- `NETIO!NetioRegisterTriageDumpDataCallback` at `0x140148fea`
- `NETIO!NetioNcmStoreBaseSupportedSlots` at `0x140148f85`
- `NETIO!NetioNcmStoreBaseSupportedSlots` at `0x140148f85`
- `NDIS!NdisCloseAdapterEx` at `0x140149109`
- `NDIS!NdisCloseAdapterEx` at `0x140149109`
- `NDIS!NdisAcquireRWLockWrite` at `0x140148dcd`
- `NDIS!NdisAcquireRWLockWrite` at `0x140148dcd`
- `NDIS!NdisReleaseRWLock` at `0x140148de8`
- `NDIS!NdisReleaseRWLock` at `0x140148de8`

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
0x140148d94  mov     [rsp-38h+arg_18], rbx
0x140148d99  push    rbp
0x140148d9a  push    rsi
0x140148d9b  push    rdi
0x140148d9c  push    r12
0x140148d9e  push    r13
0x140148da0  push    r14
0x140148da2  push    r15
0x140148da4  mov     rbp, rsp
0x140148da7  sub     rsp, 40h
0x140148dab  mov     r14, [rcx+20h]
0x140148daf  lea     rdx, [rbp+LockState]; LockState
0x140148db3  xor     eax, eax
0x140148db5  mov     rbx, rcx
0x140148db8  mov     rcx, [rcx+28h]; Lock
0x140148dbc  xor     r15d, r15d
0x140148dbf  xor     r8d, r8d; Flags
0x140148dc2  mov     [rbp+arg_10], r15d
0x140148dc6  mov     word ptr [rbp+LockState.OldIrql], ax
0x140148dca  mov     [rbp+LockState.Flags], al
0x140148dcd  call    cs:__imp_NdisAcquireRWLockWrite
0x140148dd4  nop     dword ptr [rax+rax+00h]
0x140148dd9  mov     rcx, [rbx+28h]; Lock
0x140148ddd  lea     rdx, [rbp+LockState]; LockState
0x140148de1  and     dword ptr [rbx+0C4h], 0FFFFFFFEh
0x140148de8  call    cs:__imp_NdisReleaseRWLock
0x140148def  nop     dword ptr [rax+rax+00h]
0x140148df4  mov     rcx, [rbx+50h]; RunRefCacheAware
0x140148df8  call    cs:__imp_ExReInitializeRundownProtectionCacheAware
0x140148dff  nop     dword ptr [rax+rax+00h]
0x140148e04  mov     eax, [rbx+138h]
0x140148e0a  lea     esi, [r15+3]
0x140148e0e  lea     r13d, [r15+2]
0x140148e12  mov     ecx, [r14+rax*4+1E4h]
0x140148e1a  mov     [rbx+138h], ecx
0x140148e20  cmp     [rbx+4E0h], esi
0x140148e26  jnz     short loc_140148E45
0x140148e28  cmp     [r14+5Ch], r13w
0x140148e2d  jnz     short loc_140148E45
0x140148e2f  sub     ecx, 9
0x140148e32  jz      short loc_140148E3E
0x140148e34  sub     ecx, 9
0x140148e37  jz      short loc_140148E3E
0x140148e39  cmp     ecx, 1
0x140148e3c  jnz     short loc_140148E45
0x140148e3e  and     dword ptr [rbx+4F4h], 0FFFFFFAFh
0x140148e45  mov     rax, [r14+188h]
0x140148e4c  mov     rcx, rbx
0x140148e4f  call    _guard_dispatch_icall
0x140148e54  mov     edx, 4
0x140148e59  mov     edi, eax
0x140148e5b  lea     r12d, [rdx-3]
0x140148e5f  test    eax, eax
0x140148e61  js      loc_140148EFB
0x140148e67  mov     eax, [r14+17Ch]
0x140148e6e  cmp     [rbx+4C0h], eax
0x140148e74  jnb     short loc_140148E7F
0x140148e76  mov     edi, 0C0000001h
0x140148e7b  mov     esi, edx
0x140148e7d  jmp     short loc_140148EFB
0x140148e7f  cmp     [r14+5Ch], r13w
0x140148e84  mov     eax, 3Ch ; '<'
0x140148e89  mov     [rsp+40h+var_10], r15
0x140148e8e  mov     r9d, 1010Fh
0x140148e94  mov     [rsp+40h+var_18], edx
0x140148e98  mov     r8d, r12d
0x140148e9b  lea     ecx, [rax-14h]
0x140148e9e  cmovnz  eax, ecx
0x140148ea1  xor     edx, edx
0x140148ea3  mov     [rbp+arg_10], eax
0x140148ea6  mov     rcx, rbx
0x140148ea9  lea     rax, [rbp+arg_10]
0x140148ead  mov     [rsp+40h+Timeout], rax
0x140148eb2  call    FlpNdisRequestUnderReference
0x140148eb7  mov     edi, eax
0x140148eb9  test    eax, eax
0x140148ebb  jns     short loc_140148EC4
0x140148ebd  mov     esi, 5
0x140148ec2  jmp     short loc_140148EFB
0x140148ec4  lea     rax, [rbx+4F8h]
0x140148ecb  mov     [rsp+40h+var_10], r15
0x140148ed0  mov     [rsp+40h+var_18], 4
0x140148ed8  mov     r9d, 1010Eh
0x140148ede  mov     r8d, r12d
0x140148ee1  mov     [rsp+40h+Timeout], rax
0x140148ee6  xor     edx, edx
0x140148ee8  mov     rcx, rbx
0x140148eeb  call    FlpNdisRequestUnderReference
0x140148ef0  mov     edi, eax
0x140148ef2  test    eax, eax
0x140148ef4  jns     short loc_140148F16
0x140148ef6  mov     esi, 6
0x140148efb  movzx   edx, word ptr [r14+5Ch]
0x140148f00  mov     r9d, edi
0x140148f03  mov     ecx, [rbx+498h]
0x140148f09  mov     r8d, esi
0x140148f0c  call    FlpLogInterfaceBindFailure
0x140148f11  jmp     loc_140149096
0x140148f16  cmp     dword ptr [rbx+4E4h], 18h
0x140148f1d  jz      short loc_140148F27
0x140148f1f  mov     rcx, rbx
0x140148f22  call    FlpEnableWakeupCapabilities
0x140148f27  lea     rdx, [rbx+528h]
0x140148f2e  mov     rcx, rbx
0x140148f31  call    FlpModifyTaskOffloadCapabilities
0x140148f36  cmp     [rbx+321h], r13b
0x140148f3d  jnz     short loc_140148F91
0x140148f3f  mov     eax, [rbx+328h]
0x140148f45  test    r12b, al
0x140148f48  jz      short loc_140148F91
0x140148f4a  mov     ecx, [rbx+32Ch]
0x140148f50  cmp     ecx, 10h
0x140148f53  jb      short loc_140148F91
0x140148f55  cmp     dword ptr [rbx+330h], 4Ah ; 'J'
0x140148f5c  jb      short loc_140148F91
0x140148f5e  mov     eax, [rbx+34Ch]
0x140148f64  sub     eax, esi
0x140148f66  cmp     eax, r12d
0x140148f69  ja      short loc_140148F91
0x140148f6b  mov     eax, [rbx+358h]
0x140148f71  and     eax, esi
0x140148f73  cmp     al, sil
0x140148f76  jnz     short loc_140148F91
0x140148f78  mov     eax, [rbx+33Ch]
0x140148f7e  and     eax, esi
0x140148f80  cmp     al, sil
0x140148f83  jnz     short loc_140148F91
0x140148f85  call    cs:__imp_NetioNcmStoreBaseSupportedSlots
0x140148f8c  nop     dword ptr [rax+rax+00h]
0x140148f91  mov     rcx, [rbx+120h]; Entry
0x140148f98  call    FlpAddInterface
0x140148f9d  mov     edi, eax
0x140148f9f  test    eax, eax
0x140148fa1  js      loc_140149096
0x140148fa7  mov     rcx, [rbx+48h]; RunRefCacheAware
0x140148fab  call    cs:__imp_ExReInitializeRundownProtectionCacheAware
0x140148fb2  nop     dword ptr [rax+rax+00h]
0x140148fb7  mov     rcx, [rbx+20h]
0x140148fbb  mov     rdx, rbx
0x140148fbe  add     rcx, 1B8h
0x140148fc5  call    FlpInsertInterface
0x140148fca  lea     rax, aFlif; "FLIf"
0x140148fd1  mov     r9, rbx
0x140148fd4  lea     rcx, [rbx+440h]
0x140148fdb  mov     [rsp+40h+Timeout], rax
0x140148fe0  lea     r8, FlpPopulateInterfaceTriageDumpData
0x140148fe7  mov     edx, r12d
0x140148fea  call    cs:__imp_NetioRegisterTriageDumpDataCallback
0x140148ff1  nop     dword ptr [rax+rax+00h]
0x140148ff6  cmp     [r14+290h], r15b
0x140148ffd  jz      short loc_14014900F
0x140148fff  mov     rcx, rbx
0x140149002  call    FlpProcessIsolationConfiguration
0x140149007  test    eax, eax
0x140149009  mov     edi, eax
0x14014900b  cmovs   edi, r15d
0x14014900f  mov     eax, [rbx+138h]
0x140149015  cmp     eax, 13h
0x140149018  ja      short loc_14014908E
0x14014901a  mov     ecx, 0C0201h
0x14014901f  bt      ecx, eax
0x140149022  jnb     short loc_14014908E
0x140149024  cmp     [rbx+3B0h], r15d
0x14014902b  jnz     short loc_14014908E
0x14014902d  mov     [rsp+40h+var_10], r15
0x140149032  lea     rax, [rbp+arg_0]
0x140149036  mov     [rsp+40h+var_18], r13d
0x14014903b  mov     r9d, 10110h
0x140149041  xor     r8d, r8d
0x140149044  mov     [rsp+40h+Timeout], rax
0x140149049  xor     edx, edx
0x14014904b  mov     word ptr [rbp+arg_0], r15w
0x140149050  mov     rcx, rbx
0x140149053  call    FlpNdisRequestUnderReference
0x140149058  test    eax, eax
0x14014905a  js      short loc_14014908E
0x14014905c  mov     eax, 61Eh
0x140149061  cmp     word ptr [rbp+arg_0], ax
0x140149065  jb      short loc_14014908E
0x140149067  mov     [rbx+5Ch], r12b
0x14014906b  cmp     [rbx+5B8h], r15b
0x140149072  jnz     short loc_140149081
0x140149074  cmp     [rbx+5B9h], r15b
0x14014907b  jnz     short loc_140149081
0x14014907d  mov     [rbx+5Eh], r12b
0x140149081  cmp     [rbx+600h], r15b
0x140149088  jnz     short loc_14014908E
0x14014908a  mov     [rbx+5Dh], r12b
0x14014908e  test    edi, edi
0x140149090  jns     loc_14014913E
0x140149096  mov     eax, [rbx+3D0h]
0x14014909c  test    r12b, al
0x14014909f  jz      short loc_1401490B5
0x1401490a1  mov     rax, [r14+278h]
0x1401490a8  mov     edx, 8
0x1401490ad  mov     rcx, rbx
0x1401490b0  call    _guard_dispatch_icall
0x1401490b5  mov     eax, [rbx+394h]
0x1401490bb  test    eax, eax
0x1401490bd  jz      short loc_1401490F2
0x1401490bf  mov     [rbp+arg_0], eax
0x1401490c2  mov     r9d, 0FD01010Bh
0x1401490c8  lea     rax, [rbp+arg_0]
0x1401490cc  mov     [rsp+40h+var_10], r15
0x1401490d1  mov     [rsp+40h+var_18], 4
0x1401490d9  mov     r8d, r12d
0x1401490dc  xor     edx, edx
0x1401490de  mov     [rsp+40h+Timeout], rax
0x1401490e3  mov     rcx, rbx
0x1401490e6  call    FlpNdisRequest
0x1401490eb  mov     [rbx+394h], r15d
0x1401490f2  mov     rcx, rbx
0x1401490f5  call    FlpCleanupPortCoalescedWakePatterns
0x1401490fa  mov     rcx, rbx
0x1401490fd  call    FlpCleanupL2UnicastWakePatterns
0x140149102  mov     rcx, [rbx+500h]; NdisBindingHandle
0x140149109  call    cs:__imp_NdisCloseAdapterEx
0x140149110  nop     dword ptr [rax+rax+00h]
0x140149115  cmp     eax, 103h
0x14014911a  jnz     short loc_14014913E
0x14014911c  xor     r9d, r9d; Alertable
0x14014911f  mov     [rsp+40h+Timeout], r15; Timeout
0x140149124  lea     rcx, [rbx+0A8h]; Object
0x14014912b  xor     r8d, r8d; WaitMode
0x14014912e  lea     edx, [r9+6]; WaitReason
0x140149132  call    cs:__imp_KeWaitForSingleObject
0x140149139  nop     dword ptr [rax+rax+00h]
0x14014913e  mov     rbx, [rsp+40h+arg_18]
0x140149146  mov     eax, edi
0x140149148  add     rsp, 40h
0x14014914c  pop     r15
0x14014914e  pop     r14
0x140149150  pop     r13
0x140149152  pop     r12
0x140149154  pop     rdi
0x140149155  pop     rsi
0x140149156  pop     rbp
0x140149157  retn
```
