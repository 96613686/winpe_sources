# ATL::CAtlDllModuleT<TpmVCardManagerModule>::~CAtlDllModuleT<TpmVCardManagerModule>(void)

- ea: `0x18001b144`
- end: `0x18001b161`
- name: `??1?$CAtlDllModuleT@VTpmVCardManagerModule@@@ATL@@UEAA@XZ`
- size: `29`
- prototype: `void __fastcall(ATL::CAtlModule *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001b420`
- `0x180036c20`

## callees

- `0x18001be38`
- `0x18001c0bc`

## pseudocode

```c
void __fastcall ATL::CAtlDllModuleT<TpmVCardManagerModule>::~CAtlDllModuleT<TpmVCardManagerModule>(
        ATL::CAtlModule *this)
{
  ATL::CAtlComModule::ExecuteObjectMain(this, 0);
  ATL::CAtlModule::Term(this);
}

```

## disassembly

```asm
0x18001b144  push    rbx
0x18001b146  sub     rsp, 20h
0x18001b14a  mov     rbx, rcx
0x18001b14d  xor     edx, edx; bool
0x18001b14f  call    ?ExecuteObjectMain@CAtlComModule@ATL@@QEAAX_N@Z; ATL::CAtlComModule::ExecuteObjectMain(bool)
0x18001b154  mov     rcx, rbx; this
0x18001b157  add     rsp, 20h
0x18001b15b  pop     rbx
0x18001b15c  jmp     ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
```
