# std::_Ref_count_base::_Decref(void)

- ea: `0x1800065ec`
- end: `0x18000661b`
- name: `?_Decref@_Ref_count_base@std@@QEAAXXZ`
- size: `47`
- prototype: `void __fastcall(std::_Ref_count_base *__hidden this)`
- caller_count: `83`
- callee_count: `3`
- tags: ``

## callers

- `0x180005a30`
- `0x180005db8`
- `0x180006320`
- `0x180009df4`
- `0x180009f9c`
- `0x18000a16c`
- `0x18000a354`
- `0x18000a508`
- `0x18000a6a8`
- `0x18000a89c`
- `0x18000aa28`
- `0x18000abc4`
- `0x18000ad64`
- `0x18000aec8`
- `0x18000b174`
- `0x18000b328`
- `0x18000cfa4`
- `0x18000ed90`
- `0x18000efc0`
- `0x18000f290`
- `0x1800118c0`
- `0x180011a50`
- `0x180011a9c`
- `0x180011b2c`
- `0x180011e78`
- `0x1800126cc`
- `0x180012dc4`
- `0x180013048`
- `0x180013208`
- `0x180013a5c`
- `0x180014050`
- `0x180014540`
- `0x1800154a4`
- `0x1800162b8`
- `0x180016568`
- `0x1800167c8`
- `0x180016f84`
- `0x18001935c`
- `0x180019550`
- `0x180019cb8`
- `0x18001a0c4`
- `0x18001da60`
- `0x18001decc`
- `0x18001e0d4`
- `0x18001e264`
- `0x18001e4a8`
- `0x18001e75c`
- `0x18001e8d8`
- `0x18001eaa0`
- `0x18001ec00`

## callees

- `0x1800065ec`
- `0x180006624`
- `0x18002d010`

## pseudocode

```c
void __fastcall std::_Ref_count_base::_Decref(std::_Ref_count_base *this)
{
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(std::_Ref_count_base *))this)(this);
    std::_Ref_count_base::_Decwref(this);
  }
}

```

## disassembly

```asm
0x1800065ec  push    rbx
0x1800065ee  sub     rsp, 20h
0x1800065f2  mov     rbx, rcx
0x1800065f5  or      eax, 0FFFFFFFFh
0x1800065f8  lock xadd [rcx+8], eax
0x1800065fd  cmp     eax, 1
0x180006600  jnz     short loc_180006615
0x180006602  mov     rax, [rcx]
0x180006605  mov     rax, [rax]
0x180006608  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000660d  mov     rcx, rbx; this
0x180006610  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180006615  add     rsp, 20h
0x180006619  pop     rbx
0x18000661a  retn
```
