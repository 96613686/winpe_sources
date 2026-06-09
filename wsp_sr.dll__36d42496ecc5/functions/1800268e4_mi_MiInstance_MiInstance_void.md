# mi::MiInstance::~MiInstance(void)

- ea: `0x1800268e4`
- end: `0x18002691e`
- name: `??1MiInstance@mi@@QEAA@XZ`
- size: `58`
- prototype: `void __fastcall(std::_Ref_count_base **this)`
- caller_count: `94`
- callee_count: `4`
- tags: ``

## callers

- `0x180006320`
- `0x18000885c`
- `0x180009a88`
- `0x180009c48`
- `0x18000a89c`
- `0x18000cfa4`
- `0x18000fc98`
- `0x180011670`
- `0x1800118c0`
- `0x180011a20`
- `0x1800126cc`
- `0x180012dc4`
- `0x180013048`
- `0x180014050`
- `0x1800167c8`
- `0x180016f84`
- `0x180019550`
- `0x18001a0c4`
- `0x18001ce94`
- `0x18001d308`
- `0x18001d8d4`
- `0x18001da60`
- `0x18001decc`
- `0x18001e0d4`
- `0x18001e264`
- `0x18001e4a8`
- `0x18001e75c`
- `0x18001e8d8`
- `0x18001eaa0`
- `0x18001ec00`
- `0x18001ed90`
- `0x18001f058`
- `0x18001f220`
- `0x18001f3b0`
- `0x18001f540`
- `0x18001f6a0`
- `0x18001f910`
- `0x18002004c`
- `0x180020098`
- `0x180020130`
- `0x180020600`
- `0x1800206a8`
- `0x18002095c`
- `0x180021010`
- `0x180021080`
- `0x180021560`
- `0x1800215ac`
- `0x180021618`
- `0x180021664`
- `0x1800216b0`

## callees

- `0x1800065ec`
- `0x180025e64`
- `0x1800268e4`
- `0x180026f30`

## pseudocode

```c
void __fastcall mi::MiInstance::~MiInstance(std::_Ref_count_base **this)
{
  std::_Ref_count_base *v2; // rcx
  std::_Ref_count_base *v3; // rcx

  mi::MiInstance::Close((mi::MiInstance *)this);
  v2 = this[5];
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  v3 = this[3];
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
  mi::MiObjectPtr<_MI_Instance>::Close(this);
}

```

## disassembly

```asm
0x1800268e4  push    rbx
0x1800268e6  sub     rsp, 20h
0x1800268ea  mov     rbx, rcx
0x1800268ed  call    ?Close@MiInstance@mi@@AEAAXXZ; mi::MiInstance::Close(void)
0x1800268f2  mov     rcx, [rbx+28h]; this
0x1800268f6  test    rcx, rcx
0x1800268f9  jz      short loc_180026900
0x1800268fb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180026900  mov     rcx, [rbx+18h]; this
0x180026904  test    rcx, rcx
0x180026907  jz      short loc_18002690F
0x180026909  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002690e  nop
0x18002690f  mov     rcx, rbx
0x180026912  call    ?Close@?$MiObjectPtr@U_MI_Instance@@@mi@@AEAAXXZ; mi::MiObjectPtr<_MI_Instance>::Close(void)
0x180026917  nop
0x180026918  add     rsp, 20h
0x18002691c  pop     rbx
0x18002691d  retn
```
