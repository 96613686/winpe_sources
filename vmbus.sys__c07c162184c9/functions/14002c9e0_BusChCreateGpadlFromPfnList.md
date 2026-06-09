# BusChCreateGpadlFromPfnList

- ea: `0x14002c9e0`
- end: `0x14002ca91`
- name: `BusChCreateGpadlFromPfnList`
- size: `177`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14002c9e0`
- `0x14002d888`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14002ca2a`
- `ntoskrnl!KeInitializeEvent` at `0x14002ca2a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002ca6a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002ca6a`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002ca09`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002ca09`

## pseudocode

```c
__int64 __fastcall BusChCreateGpadlFromPfnList(__int64 *a1, const void *a2, unsigned int a3, _DWORD *a4)
{
  __int64 v9; // r9
  int GpadlFromPfnList; // ecx
  _QWORD Event[4]; // [rsp+30h] [rbp-58h] BYREF
  int v12; // [rsp+50h] [rbp-38h]

  memset(Event, 0, sizeof(Event));
  v12 = 0;
  if ( KeGetCurrentIrql() > 1u )
    return 3221225800LL;
  KeInitializeEvent((PRKEVENT)&Event[1], NotificationEvent, 0);
  GpadlFromPfnList = ChCreateGpadlFromPfnList(*a1, a2, a3, v9, (__int64)Event);
  if ( GpadlFromPfnList >= 0 )
  {
    KeWaitForSingleObject(&Event[1], Executive, 0, 0, 0);
    GpadlFromPfnList = Event[0];
    if ( SLODWORD(Event[0]) >= 0 )
      *a4 = v12;
  }
  return (unsigned int)GpadlFromPfnList;
}

```

## disassembly

```asm
0x14002c9e0  push    rbx
0x14002c9e2  push    rsi
0x14002c9e3  push    rdi
0x14002c9e4  push    r14
0x14002c9e6  sub     rsp, 68h
0x14002c9ea  xorps   xmm0, xmm0
0x14002c9ed  xor     eax, eax
0x14002c9ef  movups  xmmword ptr [rsp+88h+Event], xmm0
0x14002c9f4  mov     [rsp+88h+var_38], eax
0x14002c9f8  mov     rbx, r9
0x14002c9fb  movups  xmmword ptr [rsp+88h+Event+10h], xmm0
0x14002ca00  mov     edi, r8d
0x14002ca03  mov     rsi, rdx
0x14002ca06  mov     r14, rcx
0x14002ca09  call    cs:__imp_KeGetCurrentIrql
0x14002ca10  nop     dword ptr [rax+rax+00h]
0x14002ca15  cmp     al, 1
0x14002ca17  jbe     short loc_14002CA20
0x14002ca19  mov     eax, 0C0000148h
0x14002ca1e  jmp     short loc_14002CA86
0x14002ca20  xor     r8d, r8d; State
0x14002ca23  lea     rcx, [rsp+88h+Event+8]; Event
0x14002ca28  xor     edx, edx; Type
0x14002ca2a  call    cs:__imp_KeInitializeEvent
0x14002ca31  nop     dword ptr [rax+rax+00h]
0x14002ca36  mov     rcx, [r14]
0x14002ca39  lea     rax, [rsp+88h+Event]
0x14002ca3e  mov     r8d, edi
0x14002ca41  mov     [rsp+88h+Timeout], rax
0x14002ca46  mov     rdx, rsi
0x14002ca49  call    ChCreateGpadlFromPfnList
0x14002ca4e  mov     ecx, eax
0x14002ca50  test    eax, eax
0x14002ca52  js      short loc_14002CA84
0x14002ca54  xor     r9d, r9d; Alertable
0x14002ca57  mov     [rsp+88h+Timeout], 0; Timeout
0x14002ca60  xor     r8d, r8d; WaitMode
0x14002ca63  lea     rcx, [rsp+88h+Event+8]; Object
0x14002ca68  xor     edx, edx; WaitReason
0x14002ca6a  call    cs:__imp_KeWaitForSingleObject
0x14002ca71  nop     dword ptr [rax+rax+00h]
0x14002ca76  mov     ecx, dword ptr [rsp+88h+Event]
0x14002ca7a  test    ecx, ecx
0x14002ca7c  js      short loc_14002CA84
0x14002ca7e  mov     eax, [rsp+88h+var_38]
0x14002ca82  mov     [rbx], eax
0x14002ca84  mov     eax, ecx
0x14002ca86  add     rsp, 68h
0x14002ca8a  pop     r14
0x14002ca8c  pop     rdi
0x14002ca8d  pop     rsi
0x14002ca8e  pop     rbx
0x14002ca8f  retn
```
