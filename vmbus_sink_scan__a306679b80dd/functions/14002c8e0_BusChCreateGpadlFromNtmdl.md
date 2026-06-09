# BusChCreateGpadlFromNtmdl

- ea: `0x14002c8e0`
- end: `0x14002c985`
- name: `BusChCreateGpadlFromNtmdl`
- size: `165`
- prototype: `__int64 __fastcall(_QWORD *, int, int, int, _DWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000ed90`
- `0x14002c8e0`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14002c913`
- `ntoskrnl!KeInitializeEvent` at `0x14002c913`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002c956`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002c956`

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
0x14002c8e0  push    rbx
0x14002c8e2  push    rsi
0x14002c8e3  push    rdi
0x14002c8e4  push    r14
0x14002c8e6  sub     rsp, 68h
0x14002c8ea  xorps   xmm0, xmm0
0x14002c8ed  mov     edi, r8d
0x14002c8f0  mov     rsi, rdx
0x14002c8f3  mov     r14, rcx
0x14002c8f6  xor     eax, eax
0x14002c8f8  lea     rcx, [rsp+88h+Event]; Event
0x14002c8fd  xor     r8d, r8d; State
0x14002c900  mov     [rsp+88h+var_38], eax
0x14002c904  xor     edx, edx; Type
0x14002c906  mov     ebx, r9d
0x14002c909  movups  xmmword ptr [rsp+30h], xmm0
0x14002c90e  movups  xmmword ptr [rsp+88h+Event.Header.WaitListHead.Flink], xmm0
0x14002c913  call    cs:__imp_KeInitializeEvent
0x14002c91a  nop     dword ptr [rax+rax+00h]
0x14002c91f  mov     rcx, [r14]
0x14002c922  lea     rax, [rsp+88h+var_58]
0x14002c927  mov     r9d, ebx
0x14002c92a  mov     [rsp+88h+var_60], rax
0x14002c92f  mov     r8d, edi
0x14002c932  mov     rdx, rsi
0x14002c935  call    ChCreateGpadlFromNtmdl
0x14002c93a  mov     edx, eax
0x14002c93c  test    eax, eax
0x14002c93e  js      short loc_14002C978
0x14002c940  xor     r9d, r9d; Alertable
0x14002c943  mov     [rsp+88h+Timeout], 0; Timeout
0x14002c94c  xor     r8d, r8d; WaitMode
0x14002c94f  lea     rcx, [rsp+88h+Event]; Object
0x14002c954  xor     edx, edx; WaitReason
0x14002c956  call    cs:__imp_KeWaitForSingleObject
0x14002c95d  nop     dword ptr [rax+rax+00h]
0x14002c962  mov     edx, [rsp+88h+var_58]
0x14002c966  test    edx, edx
0x14002c968  js      short loc_14002C978
0x14002c96a  mov     rcx, [rsp+88h+arg_20]
0x14002c972  mov     eax, [rsp+88h+var_38]
0x14002c976  mov     [rcx], eax
0x14002c978  mov     eax, edx
0x14002c97a  add     rsp, 68h
0x14002c97e  pop     r14
0x14002c980  pop     rdi
0x14002c981  pop     rsi
0x14002c982  pop     rbx
0x14002c983  retn
```
