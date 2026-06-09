# InterlockedAutoRef<ITaskHandler>::operator=(ITaskHandler *)

- ea: `0x140006ca0`
- end: `0x140006cc8`
- name: `??4?$InterlockedAutoRef@UITaskHandler@@@@QEAAAEAV0@PEAUITaskHandler@@@Z`
- size: `40`
- prototype: `volatile __int64 *__fastcall(volatile __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x140006c80`

## callees

- `0x140006ca0`
- `0x14000c010`

## pseudocode

```c
volatile __int64 *__fastcall InterlockedAutoRef<ITaskHandler>::operator=(volatile __int64 *a1)
{
  __int64 v2; // rcx

  v2 = _InterlockedExchange64(a1, 0);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  return a1;
}

```

## disassembly

```asm
0x140006ca0  push    rbx
0x140006ca2  sub     rsp, 20h
0x140006ca6  mov     rbx, rcx
0x140006ca9  xor     ecx, ecx
0x140006cab  xchg    rcx, [rbx]
0x140006cae  test    rcx, rcx
0x140006cb1  jz      short loc_140006CBF
0x140006cb3  mov     rax, [rcx]
0x140006cb6  mov     rax, [rax+10h]
0x140006cba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006cbf  mov     rax, rbx
0x140006cc2  add     rsp, 20h
0x140006cc6  pop     rbx
0x140006cc7  retn
```
