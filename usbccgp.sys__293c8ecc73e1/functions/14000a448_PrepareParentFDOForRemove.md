# PrepareParentFDOForRemove

- ea: `0x14000a448`
- end: `0x14000a6a6`
- name: `PrepareParentFDOForRemove`
- size: `606`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x140028cc0`

## callees

- `0x1400054a0`
- `0x140006d40`
- `0x1400088b4`
- `0x14000a448`
- `0x14000a6ac`
- `0x14000a6cc`
- `0x140014d50`
- `0x140029a38`
- `0x140029dac`
- `0x140029e6c`
- `0x14002d948`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000a62f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a62f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a522`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a603`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a522`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a603`
- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x14000a501`
- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x14000a501`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a57c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a5eb`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a57c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a5eb`
- `ntoskrnl!KeCancelTimer` at `0x14000a46c`
- `ntoskrnl!KeCancelTimer` at `0x14000a46c`
- `ntoskrnl!DbgPrintEx` at `0x14000a695`
- `ntoskrnl!DbgPrintEx` at `0x14000a695`

## string_xrefs

- `0x14000a688`: `UsbdHandleInfo->PendingDelete should be set here UsbdHandleInfo 0x%p\n`

## pseudocode

```c
void __fastcall PrepareParentFDOForRemove(__int64 a1, void *a2)
{
  int v2; // esi
  __int64 v5; // rdx
  int v6; // edx
  int v7; // eax
  KIRQL v8; // al
  int v9; // edx
  _DWORD *v10; // rcx
  KIRQL v11; // bp
  _DWORD *v12; // rcx
  __int64 v13; // rbx
  unsigned int *v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rbx
  void (__fastcall *v18)(_QWORD); // rax
  __int64 v19; // rcx

  v2 = *(_DWORD *)(a1 + 12);
  *(_DWORD *)(a1 + 12) = 7;
  KeCancelTimer((PKTIMER)(a1 + 992));
  TerminateIdleTimer(a1);
  LOBYTE(v5) = 1;
  CancelFdoIdleIrp(a1, v5);
  CancelParentWaitWake(a1);
  USBC_UnregisterWmi(a1);
  if ( *(_BYTE *)(a1 + 1361) )
    UnregisterCompositeDevice(a1);
  v7 = *(_DWORD *)(a1 + 1228);
  if ( (v7 & 2) != 0 )
  {
    v19 = *(_QWORD *)(a1 + 1248);
    *(_DWORD *)(a1 + 1228) = v7 & 0xFFFFFFFD;
    (*(void (__fastcall **)(__int64))(a1 + 1264))(v19);
  }
  if ( (unsigned int)(v2 - 7) > 1 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v6) = 4;
      WPP_RECORDER_SF_(*(_QWORD *)(a1 + 1368), v6, 2, 35, (__int64)WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids);
    }
    IoReleaseRemoveLockAndWaitEx((PIO_REMOVE_LOCK)(a1 + 200), a2, 0x20u);
    UsbcReleaseRemoveLock(a1, a2);
  }
  v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 584));
  v10 = *(_DWORD **)(a1 + 128);
  v11 = v8;
  if ( v10 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 4;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(a1 + 1368),
        v9,
        2,
        36,
        (__int64)WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids,
        *v10);
    }
    while ( 1 )
    {
      v12 = *(_DWORD **)(a1 + 128);
      if ( !*v12 )
        break;
      --*v12;
      v14 = *(unsigned int **)(a1 + 128);
      v15 = *v14;
      v16 = *(_QWORD *)&v14[2 * v15 + 2];
      *(_QWORD *)&v14[2 * v15 + 2] = 0;
      v17 = *(_QWORD *)(v16 + 64);
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 584), v11);
      FreeFunctionPDOResources(v17 + 8);
      v11 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 584));
    }
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 584), v11);
  v13 = *(_QWORD *)(a1 + 1344);
  if ( v13 )
  {
    *(_BYTE *)(v13 + 225) = 1;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v13 + 220), 0xFFFFFFFF) <= 1 )
    {
      if ( *(_BYTE *)(v13 + 225) )
      {
        v18 = *(void (__fastcall **)(_QWORD))(v13 + 112);
        if ( v18 )
          v18(*(_QWORD *)(v13 + 48));
        ExFreePoolWithTag((PVOID)v13, *(_DWORD *)(v13 + 64));
      }
      else if ( g_EnableDbgPrints )
      {
        DbgPrintEx(
          0x4Du,
          0,
          "UsbdHandleInfo->PendingDelete should be set here UsbdHandleInfo 0x%p\n",
          (const void *)v13);
      }
    }
    *(_QWORD *)(a1 + 1344) = 0;
  }
}

```

## disassembly

```asm
0x14000a448  push    rbx
0x14000a44a  push    rbp
0x14000a44b  push    rsi
0x14000a44c  push    rdi
0x14000a44d  push    r12
0x14000a44f  push    r13
0x14000a451  sub     rsp, 38h
0x14000a455  mov     esi, [rcx+0Ch]
0x14000a458  mov     rdi, rcx
0x14000a45b  mov     dword ptr [rcx+0Ch], 7
0x14000a462  mov     rbx, rdx
0x14000a465  add     rcx, 3E0h; PKTIMER
0x14000a46c  call    cs:__imp_KeCancelTimer
0x14000a473  nop     dword ptr [rax+rax+00h]
0x14000a478  mov     rcx, rdi
0x14000a47b  call    TerminateIdleTimer
0x14000a480  mov     dl, 1
0x14000a482  mov     rcx, rdi
0x14000a485  call    CancelFdoIdleIrp
0x14000a48a  mov     rcx, rdi
0x14000a48d  call    CancelParentWaitWake
0x14000a492  mov     rcx, rdi
0x14000a495  call    USBC_UnregisterWmi
0x14000a49a  cmp     byte ptr [rdi+551h], 0
0x14000a4a1  jnz     loc_14000A64B
0x14000a4a7  mov     eax, [rdi+4CCh]
0x14000a4ad  test    al, 2
0x14000a4af  jnz     loc_14000A658
0x14000a4b5  lea     eax, [rsi-7]
0x14000a4b8  lea     r12, WPP_RECORDER_INITIALIZED
0x14000a4bf  lea     r13, WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids
0x14000a4c6  cmp     eax, 1
0x14000a4c9  jbe     short loc_14000A518
0x14000a4cb  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14000a4d2  jz      short loc_14000A4F1
0x14000a4d4  mov     rcx, [rdi+558h]
0x14000a4db  mov     r9d, 23h ; '#'
0x14000a4e1  mov     dl, 4
0x14000a4e3  mov     [rsp+68h+var_48], r13
0x14000a4e8  lea     r8d, [r9-21h]
0x14000a4ec  call    WPP_RECORDER_SF_
0x14000a4f1  lea     rcx, [rdi+0C8h]; RemoveLock
0x14000a4f8  mov     r8d, 20h ; ' '; RemlockSize
0x14000a4fe  mov     rdx, rbx; Tag
0x14000a501  call    cs:__imp_IoReleaseRemoveLockAndWaitEx
0x14000a508  nop     dword ptr [rax+rax+00h]
0x14000a50d  mov     rdx, rbx
0x14000a510  mov     rcx, rdi
0x14000a513  call    UsbcReleaseRemoveLock
0x14000a518  lea     rsi, [rdi+248h]
0x14000a51f  mov     rcx, rsi; SpinLock
0x14000a522  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000a529  nop     dword ptr [rax+rax+00h]
0x14000a52e  mov     rcx, [rdi+80h]
0x14000a535  mov     bpl, al
0x14000a538  test    rcx, rcx
0x14000a53b  jz      short loc_14000A576
0x14000a53d  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14000a544  jz      short loc_14000A569
0x14000a546  mov     ecx, [rcx]
0x14000a548  mov     r9d, 24h ; '$'
0x14000a54e  mov     [rsp+68h+var_40], ecx
0x14000a552  mov     dl, 4
0x14000a554  mov     rcx, [rdi+558h]
0x14000a55b  mov     [rsp+68h+var_48], r13
0x14000a560  lea     r8d, [r9-22h]
0x14000a564  call    WPP_RECORDER_SF_d
0x14000a569  mov     rcx, [rdi+80h]
0x14000a570  mov     eax, [rcx]
0x14000a572  test    eax, eax
0x14000a574  jnz     short loc_14000A5C6
0x14000a576  mov     dl, bpl; NewIrql
0x14000a579  mov     rcx, rsi; SpinLock
0x14000a57c  call    cs:__imp_KeReleaseSpinLock
0x14000a583  nop     dword ptr [rax+rax+00h]
0x14000a588  mov     rbx, [rdi+540h]
0x14000a58f  test    rbx, rbx
0x14000a592  jnz     short loc_14000A5A2
0x14000a594  add     rsp, 38h
0x14000a598  pop     r13
0x14000a59a  pop     r12
0x14000a59c  pop     rdi
0x14000a59d  pop     rsi
0x14000a59e  pop     rbp
0x14000a59f  pop     rbx
0x14000a5a0  retn
0x14000a5a2  mov     byte ptr [rbx+0E1h], 1
0x14000a5a9  or      eax, 0FFFFFFFFh
0x14000a5ac  lock xadd [rbx+0DCh], eax
0x14000a5b4  sub     eax, 1
0x14000a5b7  jle     short loc_14000A617
0x14000a5b9  mov     qword ptr [rdi+540h], 0
0x14000a5c4  jmp     short loc_14000A594
0x14000a5c6  dec     eax
0x14000a5c8  mov     [rcx], eax
0x14000a5ca  mov     rdx, [rdi+80h]
0x14000a5d1  mov     ecx, [rdx]
0x14000a5d3  mov     rax, [rdx+rcx*8+8]
0x14000a5d8  mov     qword ptr [rdx+rcx*8+8], 0
0x14000a5e1  mov     dl, bpl; NewIrql
0x14000a5e4  mov     rcx, rsi; SpinLock
0x14000a5e7  mov     rbx, [rax+40h]
0x14000a5eb  call    cs:__imp_KeReleaseSpinLock
0x14000a5f2  nop     dword ptr [rax+rax+00h]
0x14000a5f7  lea     rcx, [rbx+8]
0x14000a5fb  call    FreeFunctionPDOResources
0x14000a600  mov     rcx, rsi; SpinLock
0x14000a603  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000a60a  nop     dword ptr [rax+rax+00h]
0x14000a60f  mov     bpl, al
0x14000a612  jmp     loc_14000A569
0x14000a617  cmp     byte ptr [rbx+0E1h], 0
0x14000a61e  jz      short loc_14000A679
0x14000a620  mov     rax, [rbx+70h]
0x14000a624  test    rax, rax
0x14000a627  jnz     short loc_14000A640
0x14000a629  mov     edx, [rbx+40h]; Tag
0x14000a62c  mov     rcx, rbx; P
0x14000a62f  call    cs:__imp_ExFreePoolWithTag
0x14000a636  nop     dword ptr [rax+rax+00h]
0x14000a63b  jmp     loc_14000A5B9
0x14000a640  mov     rcx, [rbx+30h]
0x14000a644  call    _guard_dispatch_icall
0x14000a649  jmp     short loc_14000A629
0x14000a64b  mov     rcx, rdi
0x14000a64e  call    UnregisterCompositeDevice
0x14000a653  jmp     loc_14000A4A7
0x14000a658  mov     rcx, [rdi+4E0h]
0x14000a65f  and     eax, 0FFFFFFFDh
0x14000a662  mov     [rdi+4CCh], eax
0x14000a668  mov     rax, [rdi+4F0h]
0x14000a66f  call    _guard_dispatch_icall
0x14000a674  jmp     loc_14000A4B5
0x14000a679  cmp     cs:g_EnableDbgPrints, 0
0x14000a680  jz      loc_14000A5B9
0x14000a686  xor     edx, edx; Level
0x14000a688  lea     r8, aUsbdhandleinfo_1; "UsbdHandleInfo->PendingDelete should be"...
0x14000a68f  mov     r9, rbx
0x14000a692  lea     ecx, [rdx+4Dh]; ComponentId
0x14000a695  call    cs:__imp_DbgPrintEx
0x14000a69c  nop     dword ptr [rax+rax+00h]
0x14000a6a1  jmp     loc_14000A5B9
```
