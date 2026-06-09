# BusChCreateGpadl

- ea: `0x14002c7d0`
- end: `0x14002c877`
- name: `BusChCreateGpadl`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000ec8c`
- `0x14002c7d0`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14002c804`
- `ntoskrnl!KeInitializeEvent` at `0x14002c804`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002c84a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002c84a`

## pseudocode

```c
__int64 __fastcall BusChCreateGpadl(__int64 *a1, int a2, _DWORD *a3)
{
  int Gpadl; // ecx
  _QWORD v8[4]; // [rsp+30h] [rbp-38h] BYREF
  int v9; // [rsp+50h] [rbp-18h]

  v9 = 0;
  memset(v8, 0, sizeof(v8));
  KeInitializeEvent((PRKEVENT)&v8[1], NotificationEvent, 0);
  Gpadl = ChCreateGpadl(*a1, a2, (__int64)BusChGpadlCreated, (__int64)v8, 0);
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
0x14002c7d0  mov     [rsp+arg_0], rbx
0x14002c7d5  mov     [rsp+arg_8], rsi
0x14002c7da  push    rdi
0x14002c7db  sub     rsp, 60h
0x14002c7df  xorps   xmm0, xmm0
0x14002c7e2  mov     rsi, r8
0x14002c7e5  mov     ebx, edx
0x14002c7e7  mov     rdi, rcx
0x14002c7ea  xor     eax, eax
0x14002c7ec  lea     rcx, [rsp+68h+Event]; Event
0x14002c7f1  xor     r8d, r8d; State
0x14002c7f4  mov     [rsp+68h+var_18], eax
0x14002c7f8  xor     edx, edx; Type
0x14002c7fa  movups  xmmword ptr [rsp+30h], xmm0
0x14002c7ff  movups  xmmword ptr [rsp+68h+Event.Header.WaitListHead.Flink], xmm0
0x14002c804  call    cs:__imp_KeInitializeEvent
0x14002c80b  nop     dword ptr [rax+rax+00h]
0x14002c810  mov     rcx, [rdi]
0x14002c813  lea     r9, [rsp+68h+var_38]
0x14002c818  lea     r8, BusChGpadlCreated
0x14002c81f  mov     dword ptr [rsp+68h+Timeout], 0
0x14002c827  mov     edx, ebx
0x14002c829  call    ChCreateGpadl
0x14002c82e  mov     ecx, eax
0x14002c830  test    eax, eax
0x14002c832  js      short loc_14002C864
0x14002c834  xor     r9d, r9d; Alertable
0x14002c837  mov     [rsp+68h+Timeout], 0; Timeout
0x14002c840  xor     r8d, r8d; WaitMode
0x14002c843  lea     rcx, [rsp+68h+Event]; Object
0x14002c848  xor     edx, edx; WaitReason
0x14002c84a  call    cs:__imp_KeWaitForSingleObject
0x14002c851  nop     dword ptr [rax+rax+00h]
0x14002c856  mov     ecx, [rsp+68h+var_38]
0x14002c85a  test    ecx, ecx
0x14002c85c  js      short loc_14002C864
0x14002c85e  mov     eax, [rsp+68h+var_18]
0x14002c862  mov     [rsi], eax
0x14002c864  mov     rbx, [rsp+68h+arg_0]
0x14002c869  mov     eax, ecx
0x14002c86b  mov     rsi, [rsp+68h+arg_8]
0x14002c870  add     rsp, 60h
0x14002c874  pop     rdi
0x14002c875  retn
```
