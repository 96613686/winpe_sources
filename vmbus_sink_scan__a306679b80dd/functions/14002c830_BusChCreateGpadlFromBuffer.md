# BusChCreateGpadlFromBuffer

- ea: `0x14002c830`
- end: `0x14002c8d5`
- name: `BusChCreateGpadlFromBuffer`
- size: `165`
- prototype: `__int64 __fastcall(_QWORD *, __int64, unsigned int, unsigned int, _DWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14002c830`
- `0x14002d744`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14002c863`
- `ntoskrnl!KeInitializeEvent` at `0x14002c863`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002c8a6`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002c8a6`

## pseudocode

```c
__int64 __fastcall BusChCreateGpadlFromBuffer(_QWORD *a1, __int64 a2, unsigned int a3, unsigned int a4, _DWORD *a5)
{
  int GpadlFromBuffer; // edx
  _QWORD v11[4]; // [rsp+30h] [rbp-58h] BYREF
  int v12; // [rsp+50h] [rbp-38h]

  v12 = 0;
  memset(v11, 0, sizeof(v11));
  KeInitializeEvent((PRKEVENT)&v11[1], NotificationEvent, 0);
  GpadlFromBuffer = ChCreateGpadlFromBuffer(*a1, a2, a3, a4);
  if ( GpadlFromBuffer >= 0 )
  {
    KeWaitForSingleObject(&v11[1], Executive, 0, 0, 0);
    GpadlFromBuffer = v11[0];
    if ( SLODWORD(v11[0]) >= 0 )
      *a5 = v12;
  }
  return (unsigned int)GpadlFromBuffer;
}

```

## disassembly

```asm
0x14002c830  push    rbx
0x14002c832  push    rsi
0x14002c833  push    rdi
0x14002c834  push    r14
0x14002c836  sub     rsp, 68h
0x14002c83a  xorps   xmm0, xmm0
0x14002c83d  mov     edi, r8d
0x14002c840  mov     rsi, rdx
0x14002c843  mov     r14, rcx
0x14002c846  xor     eax, eax
0x14002c848  lea     rcx, [rsp+88h+Event]; Event
0x14002c84d  xor     r8d, r8d; State
0x14002c850  mov     [rsp+88h+var_38], eax
0x14002c854  xor     edx, edx; Type
0x14002c856  mov     ebx, r9d
0x14002c859  movups  xmmword ptr [rsp+30h], xmm0
0x14002c85e  movups  xmmword ptr [rsp+88h+Event.Header.WaitListHead.Flink], xmm0
0x14002c863  call    cs:__imp_KeInitializeEvent
0x14002c86a  nop     dword ptr [rax+rax+00h]
0x14002c86f  mov     rcx, [r14]
0x14002c872  lea     rax, [rsp+88h+var_58]
0x14002c877  mov     r9d, ebx
0x14002c87a  mov     [rsp+88h+var_60], rax
0x14002c87f  mov     r8d, edi
0x14002c882  mov     rdx, rsi
0x14002c885  call    ChCreateGpadlFromBuffer
0x14002c88a  mov     edx, eax
0x14002c88c  test    eax, eax
0x14002c88e  js      short loc_14002C8C8
0x14002c890  xor     r9d, r9d; Alertable
0x14002c893  mov     [rsp+88h+Timeout], 0; Timeout
0x14002c89c  xor     r8d, r8d; WaitMode
0x14002c89f  lea     rcx, [rsp+88h+Event]; Object
0x14002c8a4  xor     edx, edx; WaitReason
0x14002c8a6  call    cs:__imp_KeWaitForSingleObject
0x14002c8ad  nop     dword ptr [rax+rax+00h]
0x14002c8b2  mov     edx, [rsp+88h+var_58]
0x14002c8b6  test    edx, edx
0x14002c8b8  js      short loc_14002C8C8
0x14002c8ba  mov     rcx, [rsp+88h+arg_20]
0x14002c8c2  mov     eax, [rsp+88h+var_38]
0x14002c8c6  mov     [rcx], eax
0x14002c8c8  mov     eax, edx
0x14002c8ca  add     rsp, 68h
0x14002c8ce  pop     r14
0x14002c8d0  pop     rdi
0x14002c8d1  pop     rsi
0x14002c8d2  pop     rbx
0x14002c8d3  retn
```
