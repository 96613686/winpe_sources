# BusChCreateGpadlFromNtmdl

- ea: `0x14002c930`
- end: `0x14002c9d5`
- name: `BusChCreateGpadlFromNtmdl`
- size: `165`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000ed90`
- `0x14002c930`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14002c963`
- `ntoskrnl!KeInitializeEvent` at `0x14002c963`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002c9a6`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002c9a6`

## pseudocode

```c
__int64 __fastcall BusChCreateGpadlFromNtmdl(_QWORD *a1, int a2, int a3, int a4, _DWORD *a5)
{
  int GpadlFromNtmdl; // edx
  _QWORD v11[4]; // [rsp+30h] [rbp-58h] BYREF
  int v12; // [rsp+50h] [rbp-38h]

  v12 = 0;
  memset(v11, 0, sizeof(v11));
  KeInitializeEvent((PRKEVENT)&v11[1], NotificationEvent, 0);
  GpadlFromNtmdl = ChCreateGpadlFromNtmdl(*a1, a2, a3, a4);
  if ( GpadlFromNtmdl >= 0 )
  {
    KeWaitForSingleObject(&v11[1], Executive, 0, 0, 0);
    GpadlFromNtmdl = v11[0];
    if ( SLODWORD(v11[0]) >= 0 )
      *a5 = v12;
  }
  return (unsigned int)GpadlFromNtmdl;
}

```

## disassembly

```asm
0x14002c930  push    rbx
0x14002c932  push    rsi
0x14002c933  push    rdi
0x14002c934  push    r14
0x14002c936  sub     rsp, 68h
0x14002c93a  xorps   xmm0, xmm0
0x14002c93d  mov     edi, r8d
0x14002c940  mov     rsi, rdx
0x14002c943  mov     r14, rcx
0x14002c946  xor     eax, eax
0x14002c948  lea     rcx, [rsp+88h+Event]; Event
0x14002c94d  xor     r8d, r8d; State
0x14002c950  mov     [rsp+88h+var_38], eax
0x14002c954  xor     edx, edx; Type
0x14002c956  mov     ebx, r9d
0x14002c959  movups  xmmword ptr [rsp+30h], xmm0
0x14002c95e  movups  xmmword ptr [rsp+88h+Event.Header.WaitListHead.Flink], xmm0
0x14002c963  call    cs:__imp_KeInitializeEvent
0x14002c96a  nop     dword ptr [rax+rax+00h]
0x14002c96f  mov     rcx, [r14]
0x14002c972  lea     rax, [rsp+88h+var_58]
0x14002c977  mov     r9d, ebx
0x14002c97a  mov     [rsp+88h+var_60], rax
0x14002c97f  mov     r8d, edi
0x14002c982  mov     rdx, rsi
0x14002c985  call    ChCreateGpadlFromNtmdl
0x14002c98a  mov     edx, eax
0x14002c98c  test    eax, eax
0x14002c98e  js      short loc_14002C9C8
0x14002c990  xor     r9d, r9d; Alertable
0x14002c993  mov     [rsp+88h+Timeout], 0; Timeout
0x14002c99c  xor     r8d, r8d; WaitMode
0x14002c99f  lea     rcx, [rsp+88h+Event]; Object
0x14002c9a4  xor     edx, edx; WaitReason
0x14002c9a6  call    cs:__imp_KeWaitForSingleObject
0x14002c9ad  nop     dword ptr [rax+rax+00h]
0x14002c9b2  mov     edx, [rsp+88h+var_58]
0x14002c9b6  test    edx, edx
0x14002c9b8  js      short loc_14002C9C8
0x14002c9ba  mov     rcx, [rsp+88h+arg_20]
0x14002c9c2  mov     eax, [rsp+88h+var_38]
0x14002c9c6  mov     [rcx], eax
0x14002c9c8  mov     eax, edx
0x14002c9ca  add     rsp, 68h
0x14002c9ce  pop     r14
0x14002c9d0  pop     rdi
0x14002c9d1  pop     rsi
0x14002c9d2  pop     rbx
0x14002c9d3  retn
```
