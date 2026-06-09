# WinHvpTerminateVpDispatchLoop

- ea: `0x14001b1e4`
- end: `0x14001b349`
- name: `WinHvpTerminateVpDispatchLoop`
- size: `357`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14002648c`

## callees

- `0x140008e70`
- `0x14000bfb0`
- `0x14001b1e4`
- `0x140023c90`
- `0x140023d00`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001b255`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001b255`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001b266`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001b266`
- `ntoskrnl!KeSetEvent` at `0x14001b22e`
- `ntoskrnl!KeSetEvent` at `0x14001b22e`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14001b2df`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14001b2df`
- `ntoskrnl!ExRundownCompleted` at `0x14001b2ee`
- `ntoskrnl!ExRundownCompleted` at `0x14001b2ee`
- `ntoskrnl!ExBlockOnAddressPushLock` at `0x14001b2bb`
- `ntoskrnl!ExBlockOnAddressPushLock` at `0x14001b2bb`
- `ntoskrnl!ExDeleteTimer` at `0x14001b30b`
- `ntoskrnl!ExDeleteTimer` at `0x14001b30b`

## pseudocode

```c
__int64 __fastcall WinHvpTerminateVpDispatchLoop(__int64 a1)
{
  __int64 v1; // rdi
  __int64 result; // rax
  signed __int64 v4; // rax
  bool i; // zf
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 v8; // [rsp+40h] [rbp+8h] BYREF
  __int64 v9; // [rsp+48h] [rbp+10h] BYREF

  v1 = a1 + 24;
  v9 = 0;
  i = *(_BYTE *)(a1 + 38) == 0;
  v8 = 0;
  if ( i )
  {
    result = WinHvpTransitionVpDispatchLoopState(a1 + 24, 3);
    if ( (int)result < 0 )
      return result;
    KeSetEvent((PRKEVENT)(v1 + 136), 0, 0);
  }
  result = WinHvpDisableVpDispatch(a1);
  if ( (int)result >= 0 )
  {
    if ( !*(_BYTE *)(v1 + 14) )
    {
      ExAcquirePushLockExclusiveEx(v1, 0);
      ExReleasePushLockExclusiveEx(v1, 0);
    }
    result = WinHvpGetHypervisorVpSignalCount(a1, &v8);
    if ( (int)result >= 0 )
    {
      v4 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v1 + 32), -v8);
      v6 = v4 - v8;
      for ( i = v6 == 0; ; i = v6 == 0 )
      {
        v9 = v6;
        if ( i )
          break;
        ExBlockOnAddressPushLock(&qword_140016190, v1 + 32, &v9, 8, 0);
        v6 = *(_QWORD *)(v1 + 32);
      }
      ExWaitForRundownProtectionRelease((PEX_RUNDOWN_REF)(v1 + 160));
      ExRundownCompleted((PEX_RUNDOWN_REF)(v1 + 160));
      v7 = *(_QWORD *)(v1 + 48);
      if ( v7 )
      {
        ExDeleteTimer(v7, 0, 0, 0);
        *(_QWORD *)(v1 + 48) = 0;
      }
      if ( *(_QWORD *)(v1 + 184) )
      {
        WinHvpDereferencePartitionData();
        *(_QWORD *)(v1 + 184) = 0;
      }
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14001b1e4  mov     [rsp+arg_10], rbx
0x14001b1e9  push    rdi
0x14001b1ea  sub     rsp, 30h
0x14001b1ee  lea     rdi, [rcx+18h]
0x14001b1f2  mov     [rsp+38h+arg_8], 0
0x14001b1fb  cmp     byte ptr [rdi+0Eh], 0
0x14001b1ff  mov     rbx, rcx
0x14001b202  mov     [rsp+38h+arg_0], 0
0x14001b20b  jnz     short loc_14001B23A
0x14001b20d  mov     edx, 3
0x14001b212  mov     rcx, rdi
0x14001b215  call    WinHvpTransitionVpDispatchLoopState
0x14001b21a  test    eax, eax
0x14001b21c  js      loc_14001B33D
0x14001b222  lea     rcx, [rdi+88h]; Event
0x14001b229  xor     r8d, r8d; Wait
0x14001b22c  xor     edx, edx; Increment
0x14001b22e  call    cs:__imp_KeSetEvent
0x14001b235  nop     dword ptr [rax+rax+00h]
0x14001b23a  mov     rcx, rbx
0x14001b23d  call    WinHvpDisableVpDispatch
0x14001b242  test    eax, eax
0x14001b244  js      loc_14001B33D
0x14001b24a  cmp     byte ptr [rdi+0Eh], 0
0x14001b24e  jnz     short loc_14001B272
0x14001b250  xor     edx, edx
0x14001b252  mov     rcx, rdi
0x14001b255  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14001b25c  nop     dword ptr [rax+rax+00h]
0x14001b261  xor     edx, edx
0x14001b263  mov     rcx, rdi
0x14001b266  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14001b26d  nop     dword ptr [rax+rax+00h]
0x14001b272  lea     rdx, [rsp+38h+arg_0]
0x14001b277  mov     rcx, rbx
0x14001b27a  call    WinHvpGetHypervisorVpSignalCount
0x14001b27f  test    eax, eax
0x14001b281  js      loc_14001B33D
0x14001b287  mov     rax, [rsp+38h+arg_0]
0x14001b28c  neg     rax
0x14001b28f  lock xadd [rdi+20h], rax
0x14001b295  sub     rax, [rsp+38h+arg_0]
0x14001b29a  jmp     short loc_14001B2CE
0x14001b29c  mov     r9d, 8
0x14001b2a2  mov     [rsp+38h+var_18], 0
0x14001b2ab  lea     r8, [rsp+38h+arg_8]
0x14001b2b0  lea     rdx, [rdi+20h]
0x14001b2b4  lea     rcx, qword_140016190
0x14001b2bb  call    cs:__imp_ExBlockOnAddressPushLock
0x14001b2c2  nop     dword ptr [rax+rax+00h]
0x14001b2c7  mov     rax, [rdi+20h]
0x14001b2cb  test    rax, rax
0x14001b2ce  mov     [rsp+38h+arg_8], rax
0x14001b2d3  jnz     short loc_14001B29C
0x14001b2d5  lea     rbx, [rdi+0A0h]
0x14001b2dc  mov     rcx, rbx; RunRef
0x14001b2df  call    cs:__imp_ExWaitForRundownProtectionRelease
0x14001b2e6  nop     dword ptr [rax+rax+00h]
0x14001b2eb  mov     rcx, rbx; RunRef
0x14001b2ee  call    cs:__imp_ExRundownCompleted
0x14001b2f5  nop     dword ptr [rax+rax+00h]
0x14001b2fa  mov     rcx, [rdi+30h]
0x14001b2fe  test    rcx, rcx
0x14001b301  jz      short loc_14001B31F
0x14001b303  xor     r9d, r9d
0x14001b306  xor     r8d, r8d
0x14001b309  xor     edx, edx
0x14001b30b  call    cs:__imp_ExDeleteTimer
0x14001b312  nop     dword ptr [rax+rax+00h]
0x14001b317  mov     qword ptr [rdi+30h], 0
0x14001b31f  mov     rcx, [rdi+0B8h]
0x14001b326  test    rcx, rcx
0x14001b329  jz      short loc_14001B33B
0x14001b32b  call    WinHvpDereferencePartitionData
0x14001b330  mov     qword ptr [rdi+0B8h], 0
0x14001b33b  xor     eax, eax
0x14001b33d  mov     rbx, [rsp+38h+arg_10]
0x14001b342  add     rsp, 30h
0x14001b346  pop     rdi
0x14001b347  retn
```
