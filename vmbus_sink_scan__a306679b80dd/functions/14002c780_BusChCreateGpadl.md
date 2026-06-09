# BusChCreateGpadl

- ea: `0x14002c780`
- end: `0x14002c827`
- name: `BusChCreateGpadl`
- size: `167`
- prototype: `__int64 __fastcall(_QWORD *, int, _DWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000ec8c`
- `0x14002c780`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14002c7b4`
- `ntoskrnl!KeInitializeEvent` at `0x14002c7b4`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002c7fa`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002c7fa`

## pseudocode

```c
__int64 __fastcall BusChCreateGpadl(_QWORD *a1, int a2, _DWORD *a3)
{
  int Gpadl; // ecx
  _QWORD v8[4]; // [rsp+30h] [rbp-38h] BYREF
  int v9; // [rsp+50h] [rbp-18h]

  v9 = 0;
  memset(v8, 0, sizeof(v8));
  KeInitializeEvent((PRKEVENT)&v8[1], NotificationEvent, 0);
  Gpadl = ChCreateGpadl(*a1, a2, (unsigned int)BusChGpadlCreated, (unsigned int)v8, 0);
  if ( Gpadl >= 0 )
  {
    KeWaitForSingleObject(&v8[1], Executive, 0, 0, 0);
    Gpadl = v8[0];
    if ( SLODWORD(v8[0]) >= 0 )
      *a3 = v9;
  }
  return (unsigned int)Gpadl;
}

```

## disassembly

```asm
0x14002c780  mov     [rsp+arg_0], rbx
0x14002c785  mov     [rsp+arg_8], rsi
0x14002c78a  push    rdi
0x14002c78b  sub     rsp, 60h
0x14002c78f  xorps   xmm0, xmm0
0x14002c792  mov     rsi, r8
0x14002c795  mov     ebx, edx
0x14002c797  mov     rdi, rcx
0x14002c79a  xor     eax, eax
0x14002c79c  lea     rcx, [rsp+68h+Event]; Event
0x14002c7a1  xor     r8d, r8d; State
0x14002c7a4  mov     [rsp+68h+var_18], eax
0x14002c7a8  xor     edx, edx; Type
0x14002c7aa  movups  xmmword ptr [rsp+30h], xmm0
0x14002c7af  movups  xmmword ptr [rsp+68h+Event.Header.WaitListHead.Flink], xmm0
0x14002c7b4  call    cs:__imp_KeInitializeEvent
0x14002c7bb  nop     dword ptr [rax+rax+00h]
0x14002c7c0  mov     rcx, [rdi]
0x14002c7c3  lea     r9, [rsp+68h+var_38]
0x14002c7c8  lea     r8, BusChGpadlCreated
0x14002c7cf  mov     dword ptr [rsp+68h+Timeout], 0
0x14002c7d7  mov     edx, ebx
0x14002c7d9  call    ChCreateGpadl
0x14002c7de  mov     ecx, eax
0x14002c7e0  test    eax, eax
0x14002c7e2  js      short loc_14002C814
0x14002c7e4  xor     r9d, r9d; Alertable
0x14002c7e7  mov     [rsp+68h+Timeout], 0; Timeout
0x14002c7f0  xor     r8d, r8d; WaitMode
0x14002c7f3  lea     rcx, [rsp+68h+Event]; Object
0x14002c7f8  xor     edx, edx; WaitReason
0x14002c7fa  call    cs:__imp_KeWaitForSingleObject
0x14002c801  nop     dword ptr [rax+rax+00h]
0x14002c806  mov     ecx, [rsp+68h+var_38]
0x14002c80a  test    ecx, ecx
0x14002c80c  js      short loc_14002C814
0x14002c80e  mov     eax, [rsp+68h+var_18]
0x14002c812  mov     [rsi], eax
0x14002c814  mov     rbx, [rsp+68h+arg_0]
0x14002c819  mov     eax, ecx
0x14002c81b  mov     rsi, [rsp+68h+arg_8]
0x14002c820  add     rsp, 60h
0x14002c824  pop     rdi
0x14002c825  retn
```
