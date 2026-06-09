# ATL::CAtlDllModuleT<CPrincipalProviderLibModule>::~CAtlDllModuleT<CPrincipalProviderLibModule>(void)

- ea: `0x1800036ac`
- end: `0x1800036c9`
- name: `??1?$CAtlDllModuleT@VCPrincipalProviderLibModule@@@ATL@@UEAA@XZ`
- size: `29`
- prototype: `void __fastcall(ATL::CAtlModule *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003750`
- `0x1800113a0`

## callees

- `0x180004168`
- `0x1800043bc`

## pseudocode

```c
void __fastcall ATL::CAtlDllModuleT<CPrincipalProviderLibModule>::~CAtlDllModuleT<CPrincipalProviderLibModule>(
        ATL::CAtlModule *this)
{
  ATL::CAtlComModule::ExecuteObjectMain(this, 0);
  ATL::CAtlModule::Term(this);
}

```

## disassembly

```asm
0x1800036ac  push    rbx
0x1800036ae  sub     rsp, 20h
0x1800036b2  mov     rbx, rcx
0x1800036b5  xor     edx, edx; bool
0x1800036b7  call    ?ExecuteObjectMain@CAtlComModule@ATL@@QEAAX_N@Z; ATL::CAtlComModule::ExecuteObjectMain(bool)
0x1800036bc  mov     rcx, rbx; this
0x1800036bf  add     rsp, 20h
0x1800036c3  pop     rbx
0x1800036c4  jmp     ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
```
