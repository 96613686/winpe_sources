# std::_Ref_count_base::_Decref(void)

- ea: `0x180006630`
- end: `0x180006660`
- name: `?_Decref@_Ref_count_base@std@@QEAAXXZ`
- size: `48`
- prototype: `void __fastcall(std::_Ref_count_base *__hidden this)`
- caller_count: `83`
- callee_count: `3`
- tags: ``

## callers

- `0x180005a70`
- `0x180005df8`
- `0x180006360`
- `0x180009f4c`
- `0x18000a0f4`
- `0x18000a2c4`
- `0x18000a4b0`
- `0x18000a664`
- `0x18000a804`
- `0x18000aa00`
- `0x18000ab90`
- `0x18000ad2c`
- `0x18000aecc`
- `0x18000b030`
- `0x18000b2dc`
- `0x18000b494`
- `0x18000cec8`
- `0x18000ed64`
- `0x18000ef94`
- `0x18000f264`
- `0x180011784`
- `0x180011914`
- `0x180011960`
- `0x1800119f0`
- `0x180011d40`
- `0x180012594`
- `0x180012c94`
- `0x180012f18`
- `0x1800130d8`
- `0x180013964`
- `0x180013f60`
- `0x180014450`
- `0x180015358`
- `0x180016170`
- `0x180016424`
- `0x180016684`
- `0x180016e4c`
- `0x180019388`
- `0x180019584`
- `0x180019cf0`
- `0x18001a0fc`
- `0x18001db88`
- `0x18001dff4`
- `0x18001e200`
- `0x18001e390`
- `0x18001e5d4`
- `0x18001e88c`
- `0x18001ea08`
- `0x18001ebd0`
- `0x18001ed30`

## callees

- `0x180006630`
- `0x180006668`
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
0x180006630  push    rbx
0x180006632  sub     rsp, 20h
0x180006636  mov     rbx, rcx
0x180006639  or      eax, 0FFFFFFFFh
0x18000663c  lock xadd [rcx+8], eax
0x180006641  cmp     eax, 1
0x180006644  jnz     short loc_180006659
0x180006646  mov     rax, [rcx]
0x180006649  mov     rax, [rax]
0x18000664c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006651  mov     rcx, rbx; this
0x180006654  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180006659  add     rsp, 20h
0x18000665d  pop     rbx
0x18000665e  retn
```
