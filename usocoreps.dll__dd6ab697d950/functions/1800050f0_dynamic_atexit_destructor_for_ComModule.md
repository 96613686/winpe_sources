# _dynamic_atexit_destructor_for__ComModule__

- ea: `0x1800050f0`
- end: `0x18000510a`
- name: `_dynamic_atexit_destructor_for__ComModule__`
- size: `26`
- prototype: `void __fastcall(__int64, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002248`

## pseudocode

```c
void __fastcall dynamic_atexit_destructor_for__ComModule__(__int64 a1, unsigned int a2)
{
  ComModule = &ATL::CComModule::`vftable';
  ATL::CAtlModule::~CAtlModule((ATL::CAtlModule *)&ComModule, a2);
}

```

## disassembly

```asm
0x1800050f0  lea     rax, ??_7CComModule@ATL@@6B@; const ATL::CComModule::`vftable'
0x1800050f7  lea     rcx, ?ComModule@@3VCComModule@ATL@@A; this
0x1800050fe  mov     cs:?ComModule@@3VCComModule@ATL@@A, rax; ATL::CComModule ComModule
0x180005105  jmp     ??1CAtlModule@ATL@@UEAA@XZ; ATL::CAtlModule::~CAtlModule(void)
```
