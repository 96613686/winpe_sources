# VmsOmFindSwitchInitialized

- ea: `0x140047038`
- end: `0x1400471fe`
- name: `VmsOmFindSwitchInitialized`
- size: `454`
- prototype: ``
- caller_count: `28`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140035480`
- `0x1400359fc`
- `0x14003985c`
- `0x14006c5a4`
- `0x14007cd4c`
- `0x1400b3a4c`
- `0x1400b3e68`
- `0x1400b43d4`
- `0x1400b4828`
- `0x1400b9cbc`
- `0x1400cbc60`
- `0x1400cd400`
- `0x1400cd8d8`
- `0x1400cded4`
- `0x1400ce2c4`
- `0x1400cea70`
- `0x1400cef88`
- `0x1400cf500`
- `0x1400cfc6c`
- `0x1400d01d8`
- `0x1400d05d4`
- `0x1400d0ddc`
- `0x1400d13a8`
- `0x1400d7a68`
- `0x1400d7db8`
- `0x140106604`
- `0x140108c00`
- `0x1401222c0`

## callees

- `0x140014988`
- `0x140027a64`
- `0x140046e5c`
- `0x140047038`
- `0x140047204`
- `0x140066bec`
- `0x14008497c`
- `0x1401bbbd4`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1400470ad`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004714d`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400470ad`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004714d`
- `NDIS!NdisAcquireRWLockRead` at `0x140047083`
- `NDIS!NdisAcquireRWLockRead` at `0x140047083`
- `NDIS!NdisReleaseRWLock` at `0x140047187`
- `NDIS!NdisReleaseRWLock` at `0x1400471bc`
- `NDIS!NdisReleaseRWLock` at `0x1401bc93e`
- `NDIS!NdisReleaseRWLock` at `0x140047187`
- `NDIS!NdisReleaseRWLock` at `0x1400471bc`
- `NDIS!NdisReleaseRWLock` at `0x1401bc93e`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400470cc`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400470cc`

## pseudocode

```c
__int64 __fastcall VmsOmFindSwitchInitialized(__int64 a1, char a2, _QWORD *a3)
{
  __int64 v6; // rbx
  int v7; // edx
  __int64 v8; // rdx
  int v9; // edx
  unsigned int v10; // ebx
  __int64 v12; // [rsp+0h] [rbp-68h] BYREF
  struct _LOCK_STATE_EX v13; // [rsp+40h] [rbp-28h] BYREF
  int SwitchUnsafe; // [rsp+44h] [rbp-24h]
  __int64 v15; // [rsp+48h] [rbp-20h] BYREF
  __int64 *v16; // [rsp+50h] [rbp-18h]
  struct _LOCK_STATE_EX LockState; // [rsp+88h] [rbp+20h] BYREF

  v16 = &v12;
  v15 = 0;
  *(_WORD *)&v13.OldIrql = 0;
  v13.Flags = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  NdisAcquireRWLockRead(VmsOmObjectListLock, &v13, 0);
  SwitchUnsafe = VmsOmFindSwitchUnsafe(a1, &v15);
  if ( !SwitchUnsafe )
  {
    v6 = v15;
    if ( KeGetCurrentIrql() != 2 )
      goto LABEL_5;
    while ( 1 )
    {
      NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(v6 + 56), &LockState, 1u);
      if ( *(_DWORD *)(v6 + 68) != 2 )
        break;
      LOBYTE(v8) = 2;
      WPP_RECORDER_SF_(VmsIfrLog, v8, 20, 43, (__int64)WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids);
      SwitchUnsafe = -1073741738;
      local_unwind_0(v16, &loc_14004717B);
LABEL_5:
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        v7,
        19,
        23,
        (__int64)WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids,
        (__int64)"KeGetCurrentIrql() == DISPATCH_LEVEL");
      if ( KeGetCurrentIrql() != 2 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    LOBYTE(v8) = a2;
    VmsOmpObjectReference(v6, v8);
    *a3 = v6;
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v6 + 56), &LockState);
  }
  NdisReleaseRWLock(VmsOmObjectListLock, &v13);
  v10 = SwitchUnsafe;
  if ( SwitchUnsafe < 0 )
  {
    LOBYTE(v9) = 2;
    WPP_RECORDER_SF_Zd(
      VmsIfrLog,
      v9,
      20,
      44,
      (__int64)WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids,
      a1,
      SwitchUnsafe);
  }
  return v10;
}

```

## disassembly

```asm
0x140047038  mov     r11, rsp
0x14004703b  mov     [r11+10h], rbx
0x14004703f  mov     [r11+18h], rsi
0x140047043  mov     [r11+8], rcx
0x140047047  push    rdi
0x140047048  sub     rsp, 60h
0x14004704c  mov     [rsp+68h+var_18], rsp
0x140047051  mov     rdi, r8
0x140047054  mov     esi, edx
0x140047056  mov     rbx, rcx
0x140047059  mov     qword ptr [r11-20h], 0
0x140047061  xor     eax, eax
0x140047063  mov     word ptr [rsp+68h+var_28.OldIrql], ax
0x140047068  mov     [rsp+68h+var_28.Flags], al
0x14004706c  mov     [r11+20h], ax
0x140047071  mov     [r11+22h], al
0x140047075  mov     rcx, cs:VmsOmObjectListLock; Lock
0x14004707c  xor     r8d, r8d; Flags
0x14004707f  lea     rdx, [r11-28h]; LockState
0x140047083  call    cs:__imp_NdisAcquireRWLockRead
0x14004708a  nop     dword ptr [rax+rax+00h]
0x14004708f  lea     rdx, [rsp+68h+var_20]
0x140047094  mov     rcx, rbx
0x140047097  call    VmsOmFindSwitchUnsafe
0x14004709c  mov     [rsp+68h+var_24], eax
0x1400470a0  test    eax, eax
0x1400470a2  jnz     loc_14004717B
0x1400470a8  mov     rbx, [rsp+68h+var_20]
0x1400470ad  call    cs:__imp_KeGetCurrentIrql
0x1400470b4  nop     dword ptr [rax+rax+00h]
0x1400470b9  cmp     al, 2
0x1400470bb  jnz     short loc_14004711F
0x1400470bd  mov     r8b, 1; Flags
0x1400470c0  lea     rdx, [rsp+68h+LockState]; LockState
0x1400470c8  mov     rcx, [rbx+38h]; Lock
0x1400470cc  call    cs:__imp_NdisAcquireRWLockWrite
0x1400470d3  nop     dword ptr [rax+rax+00h]
0x1400470d8  cmp     dword ptr [rbx+44h], 2
0x1400470dc  jnz     loc_14004716B
0x1400470e2  mov     r9d, 2Bh ; '+'
0x1400470e8  lea     rax, WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids
0x1400470ef  mov     [rsp+68h+var_48], rax
0x1400470f4  lea     r8d, [r9-17h]
0x1400470f8  mov     dl, 2
0x1400470fa  mov     rcx, cs:VmsIfrLog
0x140047101  call    WPP_RECORDER_SF_
0x140047106  mov     [rsp+68h+var_24], 0C0000056h
0x14004710e  lea     rdx, loc_14004717B
0x140047115  mov     rcx, [rsp+68h+var_18]
0x14004711a  call    _local_unwind_0
0x14004711f  mov     r9d, 17h
0x140047125  lea     rax, aKegetcurrentir; "KeGetCurrentIrql() == DISPATCH_LEVEL"
0x14004712c  mov     [rsp+68h+var_40], rax
0x140047131  lea     rax, WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids
0x140047138  mov     [rsp+68h+var_48], rax
0x14004713d  lea     r8d, [r9-4]
0x140047141  mov     rcx, cs:VmsIfrLog
0x140047148  call    WPP_RECORDER_SF_s
0x14004714d  call    cs:__imp_KeGetCurrentIrql
0x140047154  nop     dword ptr [rax+rax+00h]
0x140047159  cmp     al, 2
0x14004715b  jz      loc_1400470BD
0x140047161  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "KeGetCurrentIrql() == 2")
0x140047166  jmp     loc_1400470BD
0x14004716b  mov     dl, sil
0x14004716e  mov     rcx, rbx
0x140047171  call    VmsOmpObjectReference
0x140047176  mov     [rdi], rbx
0x140047179  jmp     short loc_1400471B0
0x14004717b  lea     rdx, [rsp+68h+var_28]; LockState
0x140047180  mov     rcx, cs:VmsOmObjectListLock; Lock
0x140047187  call    cs:__imp_NdisReleaseRWLock
0x14004718e  nop     dword ptr [rax+rax+00h]
0x140047193  mov     ebx, [rsp+68h+var_24]
0x140047197  test    ebx, ebx
0x140047199  js      short loc_1400471CA
0x14004719b  mov     eax, ebx
0x14004719d  lea     r11, [rsp+68h+var_8]
0x1400471a2  mov     rbx, [r11+18h]
0x1400471a6  mov     rsi, [r11+20h]
0x1400471aa  mov     rsp, r11
0x1400471ad  pop     rdi
0x1400471ae  retn
0x1400471b0  lea     rdx, [rsp+68h+LockState]; LockState
0x1400471b8  mov     rcx, [rbx+38h]; Lock
0x1400471bc  call    cs:__imp_NdisReleaseRWLock
0x1400471c3  nop     dword ptr [rax+rax+00h]
0x1400471c8  jmp     short loc_14004717B
0x1400471ca  mov     r9d, 2Ch ; ','
0x1400471d0  mov     [rsp+68h+var_38], ebx
0x1400471d4  mov     rcx, [rsp+68h+arg_0]
0x1400471d9  mov     [rsp+68h+var_40], rcx
0x1400471de  lea     rax, WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids
0x1400471e5  mov     [rsp+68h+var_48], rax
0x1400471ea  lea     r8d, [r9-18h]
0x1400471ee  mov     dl, 2
0x1400471f0  mov     rcx, cs:VmsIfrLog
0x1400471f7  call    WPP_RECORDER_SF_Zd
0x1400471fc  jmp     short loc_14004719B
0x1401bc926  push    rbp
0x1401bc928  sub     rsp, 40h
0x1401bc92c  mov     rbp, rdx
0x1401bc92f  mov     rcx, [rbp+48h]
0x1401bc933  lea     rdx, [rbp+88h]; LockState
0x1401bc93a  mov     rcx, [rcx+38h]; Lock
0x1401bc93e  call    cs:__imp_NdisReleaseRWLock
0x1401bc945  nop     dword ptr [rax+rax+00h]
0x1401bc94a  nop
0x1401bc94b  add     rsp, 40h
0x1401bc94f  pop     rbp
0x1401bc950  retn
```
