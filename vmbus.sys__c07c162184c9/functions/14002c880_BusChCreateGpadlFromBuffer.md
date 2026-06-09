# BusChCreateGpadlFromBuffer

- ea: `0x14002c880`
- end: `0x14002c925`
- name: `BusChCreateGpadlFromBuffer`
- size: `165`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14002c880`
- `0x14002d794`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14002c8b3`
- `ntoskrnl!KeInitializeEvent` at `0x14002c8b3`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002c8f6`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002c8f6`

## pseudocode

```c
__int64 __fastcall BusChCreateGpadlFromBuffer(__int64 *a1, void *a2, ULONG a3, LOCK_OPERATION a4, _DWORD *a5)
{
  int GpadlFromBuffer; // edx
  PLARGE_INTEGER Timeout; // [rsp+20h] [rbp-68h]
  _QWORD v12[4]; // [rsp+30h] [rbp-58h] BYREF
  int v13; // [rsp+50h] [rbp-38h]

  v13 = 0;
  memset(v12, 0, sizeof(v12));
  KeInitializeEvent((PRKEVENT)&v12[1], NotificationEvent, 0);
  GpadlFromBuffer = ChCreateGpadlFromBuffer(*a1, a2, a3, a4, (__int64)Timeout, (__int64)v12);
  if ( GpadlFromBuffer >= 0 )
  {
    KeWaitForSingleObject(&v12[1], Executive, 0, 0, 0);
    GpadlFromBuffer = v12[0];
    if ( SLODWORD(v12[0]) >= 0 )
      *a5 = v13;
  }
  return (unsigned int)GpadlFromBuffer;
}

```

## disassembly

```asm
0x14002c880  push    rbx
0x14002c882  push    rsi
0x14002c883  push    rdi
0x14002c884  push    r14
0x14002c886  sub     rsp, 68h
0x14002c88a  xorps   xmm0, xmm0
0x14002c88d  mov     edi, r8d
0x14002c890  mov     rsi, rdx
0x14002c893  mov     r14, rcx
0x14002c896  xor     eax, eax
0x14002c898  lea     rcx, [rsp+88h+Event]; Event
0x14002c89d  xor     r8d, r8d; State
0x14002c8a0  mov     [rsp+88h+var_38], eax
0x14002c8a4  xor     edx, edx; Type
0x14002c8a6  mov     ebx, r9d
0x14002c8a9  movups  xmmword ptr [rsp+30h], xmm0
0x14002c8ae  movups  xmmword ptr [rsp+88h+Event.Header.WaitListHead.Flink], xmm0
0x14002c8b3  call    cs:__imp_KeInitializeEvent
0x14002c8ba  nop     dword ptr [rax+rax+00h]
0x14002c8bf  mov     rcx, [r14]
0x14002c8c2  lea     rax, [rsp+88h+var_58]
0x14002c8c7  mov     r9d, ebx
0x14002c8ca  mov     [rsp+88h+var_60], rax
0x14002c8cf  mov     r8d, edi
0x14002c8d2  mov     rdx, rsi
0x14002c8d5  call    ChCreateGpadlFromBuffer
0x14002c8da  mov     edx, eax
0x14002c8dc  test    eax, eax
0x14002c8de  js      short loc_14002C918
0x14002c8e0  xor     r9d, r9d; Alertable
0x14002c8e3  mov     [rsp+88h+Timeout], 0; Timeout
0x14002c8ec  xor     r8d, r8d; WaitMode
0x14002c8ef  lea     rcx, [rsp+88h+Event]; Object
0x14002c8f4  xor     edx, edx; WaitReason
0x14002c8f6  call    cs:__imp_KeWaitForSingleObject
0x14002c8fd  nop     dword ptr [rax+rax+00h]
0x14002c902  mov     edx, [rsp+88h+var_58]
0x14002c906  test    edx, edx
0x14002c908  js      short loc_14002C918
0x14002c90a  mov     rcx, [rsp+88h+arg_20]
0x14002c912  mov     eax, [rsp+88h+var_38]
0x14002c916  mov     [rcx], eax
0x14002c918  mov     eax, edx
0x14002c91a  add     rsp, 68h
0x14002c91e  pop     r14
0x14002c920  pop     rdi
0x14002c921  pop     rsi
0x14002c922  pop     rbx
0x14002c923  retn
```
