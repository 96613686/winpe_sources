# wmi::AutoRef<SubscriptionConfigSnapshot>::operator=(SubscriptionConfigSnapshot *)

- ea: `0x180003d10`
- end: `0x180003d3f`
- name: `??4?$AutoRef@VSubscriptionConfigSnapshot@@@wmi@@QEAAAEAV01@PEAVSubscriptionConfigSnapshot@@@Z`
- size: `47`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180003840`
- `0x180004b80`
- `0x1800052cc`
- `0x18000a938`
- `0x18000ec24`

## callees

- `0x180003d10`
- `0x18000526c`

## pseudocode

```c
_QWORD *__fastcall wmi::AutoRef<SubscriptionConfigSnapshot>::operator=(_QWORD *a1, __int64 a2)
{
  if ( a2 )
    _InterlockedIncrement((volatile signed __int32 *)(a2 + 8));
  wmi::AutoRef<AbstractEventProcessor>::Release(a1);
  *a1 = a2;
  return a1;
}

```

## disassembly

```asm
0x180003d10  mov     [rsp+arg_0], rbx
0x180003d15  push    rdi
0x180003d16  sub     rsp, 20h
0x180003d1a  mov     rbx, rdx
0x180003d1d  mov     rdi, rcx
0x180003d20  test    rdx, rdx
0x180003d23  jz      short loc_180003D29
0x180003d25  lock inc dword ptr [rdx+8]
0x180003d29  call    ?Release@?$AutoRef@VAbstractEventProcessor@@@wmi@@QEAAXXZ; wmi::AutoRef<AbstractEventProcessor>::Release(void)
0x180003d2e  mov     [rdi], rbx
0x180003d31  mov     rax, rdi
0x180003d34  mov     rbx, [rsp+28h+arg_0]
0x180003d39  add     rsp, 20h
0x180003d3d  pop     rdi
0x180003d3e  retn
```
