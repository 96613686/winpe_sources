# SrvNetConnectionScavengerThread

- ea: `0x14001b6e0`
- end: `0x14001b7d6`
- name: `SrvNetConnectionScavengerThread`
- size: `246`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x14000de5c`
- `0x14001b6e0`
- `0x140047ab0`
- `0x140055028`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14001b7be`
- `ntoskrnl!KeSetEvent` at `0x14001b7be`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001b76e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001b76e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001b72f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001b72f`
- `ntoskrnl!KeSetCoalescableTimer` at `0x14001b7a1`
- `ntoskrnl!KeSetCoalescableTimer` at `0x14001b7a1`

## pseudocode

```c
void SrvNetConnectionScavengerThread()
{
  char v0; // bl
  KIRQL v1; // al
  char v2; // di
  __int64 v3; // [rsp+48h] [rbp+10h] BYREF

  v0 = 0;
  if ( byte_14003708A
    || (v3 = MEMORY[0xFFFFF78000000014] - 300000000LL, (v0 = SrvNetTerminateIdleConnections(&v3)) == 0) )
  {
    SrvNetFlushBufferLookasides();
  }
  else
  {
    SrvNetTrimBufferLookasides();
  }
  v1 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  if ( byte_14003708A )
  {
    v0 = 0;
    v2 = 1;
    LOBYTE(word_140037088) = 0;
  }
  else
  {
    v2 = 0;
    LOBYTE(word_140037088) = v0;
    if ( !v0 )
      word_140037088 = 0;
  }
  KeReleaseSpinLock(&SpinLock, v1);
  if ( v0 )
    KeSetCoalescableTimer(&Timer, (LARGE_INTEGER)-600000000LL, 0, 0x1388u, &Dpc);
  if ( v2 )
    KeSetEvent(&Event, 0, 0);
}

```

## disassembly

```asm
0x14001b6e0  mov     [rsp+arg_0], rbx
0x14001b6e5  push    rdi
0x14001b6e6  sub     rsp, 30h
0x14001b6ea  mov     rax, 0FFFFF78000000014h
0x14001b6f4  xor     bl, bl
0x14001b6f6  mov     rax, [rax]
0x14001b6f9  cmp     cs:byte_14003708A, bl
0x14001b6ff  jnz     short loc_14001B723
0x14001b701  add     rax, 0FFFFFFFFEE1E5D00h
0x14001b707  lea     rcx, [rsp+38h+arg_8]
0x14001b70c  mov     [rsp+38h+arg_8], rax
0x14001b711  call    SrvNetTerminateIdleConnections
0x14001b716  mov     bl, al
0x14001b718  test    al, al
0x14001b71a  jz      short loc_14001B723
0x14001b71c  call    SrvNetTrimBufferLookasides
0x14001b721  jmp     short loc_14001B728
0x14001b723  call    SrvNetFlushBufferLookasides
0x14001b728  lea     rcx, SpinLock; SpinLock
0x14001b72f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001b736  nop     dword ptr [rax+rax+00h]
0x14001b73b  cmp     cs:byte_14003708A, 0
0x14001b742  jz      short loc_14001B751
0x14001b744  xor     bl, bl
0x14001b746  mov     dil, 1
0x14001b749  mov     byte ptr cs:word_140037088, bl
0x14001b74f  jmp     short loc_14001B765
0x14001b751  xor     dil, dil
0x14001b754  mov     byte ptr cs:word_140037088, bl
0x14001b75a  test    bl, bl
0x14001b75c  jnz     short loc_14001B765
0x14001b75e  mov     byte ptr cs:word_140037088+1, dil
0x14001b765  mov     dl, al; NewIrql
0x14001b767  lea     rcx, SpinLock; SpinLock
0x14001b76e  call    cs:__imp_KeReleaseSpinLock
0x14001b775  nop     dword ptr [rax+rax+00h]
0x14001b77a  test    bl, bl
0x14001b77c  jz      short loc_14001B7AD
0x14001b77e  lea     rax, Dpc
0x14001b785  mov     r9d, 1388h; TolerableDelay
0x14001b78b  xor     r8d, r8d; Period
0x14001b78e  mov     [rsp+38h+Dpc], rax; Dpc
0x14001b793  mov     rdx, 0FFFFFFFFDC3CBA00h; DueTime
0x14001b79a  lea     rcx, Timer; Timer
0x14001b7a1  call    cs:__imp_KeSetCoalescableTimer
0x14001b7a8  nop     dword ptr [rax+rax+00h]
0x14001b7ad  test    dil, dil
0x14001b7b0  jz      short loc_14001B7CA
0x14001b7b2  xor     r8d, r8d; Wait
0x14001b7b5  lea     rcx, Event; Event
0x14001b7bc  xor     edx, edx; Increment
0x14001b7be  call    cs:__imp_KeSetEvent
0x14001b7c5  nop     dword ptr [rax+rax+00h]
0x14001b7ca  mov     rbx, [rsp+38h+arg_0]
0x14001b7cf  add     rsp, 30h
0x14001b7d3  pop     rdi
0x14001b7d4  retn
```
