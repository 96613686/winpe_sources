# BusChCreateGpadlFromPfnList

- ea: `0x14002c990`
- end: `0x14002ca41`
- name: `BusChCreateGpadlFromPfnList`
- size: `177`
- prototype: `__int64 __fastcall(_QWORD *, __int64, unsigned int, _DWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14002c990`
- `0x14002d838`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14002c9da`
- `ntoskrnl!KeInitializeEvent` at `0x14002c9da`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002ca1a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002ca1a`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002c9b9`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002c9b9`

## pseudocode

```c
__int64 __fastcall BusChCreateGpadlFromPfnList(_QWORD *a1, __int64 a2, unsigned int a3, _DWORD *a4)
{
  int GpadlFromPfnList; // ecx
  _QWORD Event[4]; // [rsp+30h] [rbp-58h] BYREF
  int v11; // [rsp+50h] [rbp-38h]

  memset(Event, 0, sizeof(Event));
  v11 = 0;
  if ( KeGetCurrentIrql() > 1u )
    return 3221225800LL;
  KeInitializeEvent((PRKEVENT)&Event[1], NotificationEvent, 0);
  GpadlFromPfnList = ChCreateGpadlFromPfnList(*a1, a2, a3);
  if ( GpadlFromPfnList >= 0 )
  {
    KeWaitForSingleObject(&Event[1], Executive, 0, 0, 0);
    GpadlFromPfnList = Event[0];
    if ( SLODWORD(Event[0]) >= 0 )
      *a4 = v11;
  }
  return (unsigned int)GpadlFromPfnList;
}

```

## disassembly

```asm
0x14002c990  push    rbx
0x14002c992  push    rsi
0x14002c993  push    rdi
0x14002c994  push    r14
0x14002c996  sub     rsp, 68h
0x14002c99a  xorps   xmm0, xmm0
0x14002c99d  xor     eax, eax
0x14002c99f  movups  xmmword ptr [rsp+88h+Event], xmm0
0x14002c9a4  mov     [rsp+88h+var_38], eax
0x14002c9a8  mov     rbx, r9
0x14002c9ab  movups  xmmword ptr [rsp+88h+Event+10h], xmm0
0x14002c9b0  mov     edi, r8d
0x14002c9b3  mov     rsi, rdx
0x14002c9b6  mov     r14, rcx
0x14002c9b9  call    cs:__imp_KeGetCurrentIrql
0x14002c9c0  nop     dword ptr [rax+rax+00h]
0x14002c9c5  cmp     al, 1
0x14002c9c7  jbe     short loc_14002C9D0
0x14002c9c9  mov     eax, 0C0000148h
0x14002c9ce  jmp     short loc_14002CA36
0x14002c9d0  xor     r8d, r8d; State
0x14002c9d3  lea     rcx, [rsp+88h+Event+8]; Event
0x14002c9d8  xor     edx, edx; Type
0x14002c9da  call    cs:__imp_KeInitializeEvent
0x14002c9e1  nop     dword ptr [rax+rax+00h]
0x14002c9e6  mov     rcx, [r14]
0x14002c9e9  lea     rax, [rsp+88h+Event]
0x14002c9ee  mov     r8d, edi
0x14002c9f1  mov     [rsp+88h+Timeout], rax
0x14002c9f6  mov     rdx, rsi
0x14002c9f9  call    ChCreateGpadlFromPfnList
0x14002c9fe  mov     ecx, eax
0x14002ca00  test    eax, eax
0x14002ca02  js      short loc_14002CA34
0x14002ca04  xor     r9d, r9d; Alertable
0x14002ca07  mov     [rsp+88h+Timeout], 0; Timeout
0x14002ca10  xor     r8d, r8d; WaitMode
0x14002ca13  lea     rcx, [rsp+88h+Event+8]; Object
0x14002ca18  xor     edx, edx; WaitReason
0x14002ca1a  call    cs:__imp_KeWaitForSingleObject
0x14002ca21  nop     dword ptr [rax+rax+00h]
0x14002ca26  mov     ecx, dword ptr [rsp+88h+Event]
0x14002ca2a  test    ecx, ecx
0x14002ca2c  js      short loc_14002CA34
0x14002ca2e  mov     eax, [rsp+88h+var_38]
0x14002ca32  mov     [rbx], eax
0x14002ca34  mov     eax, ecx
0x14002ca36  add     rsp, 68h
0x14002ca3a  pop     r14
0x14002ca3c  pop     rdi
0x14002ca3d  pop     rsi
0x14002ca3e  pop     rbx
0x14002ca3f  retn
```
