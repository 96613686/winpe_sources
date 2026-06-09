# ATL::CAtlDllModuleT<CWdsTptMgmtModule>::~CAtlDllModuleT<CWdsTptMgmtModule>(void)

- ea: `0x180002ac4`
- end: `0x180002ae1`
- name: `??1?$CAtlDllModuleT@VCWdsTptMgmtModule@@@ATL@@UEAA@XZ`
- size: `29`
- prototype: `__int64 __fastcall(ATL::CAtlModule *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002cb0`
- `0x18001f2b0`

## callees

- `0x18000434c`
- `0x180005748`

## pseudocode

```c
void __fastcall ATL::CAtlDllModuleT<CWdsTptMgmtModule>::~CAtlDllModuleT<CWdsTptMgmtModule>(ATL::CAtlModule *this)
{
  unsigned int v2; // edx

  ATL::CAtlComModule::ExecuteObjectMain(this, 0);
  ATL::CAtlModule::Term(this, v2);
}

```

## disassembly

```asm
0x180002ac4  push    rbx
0x180002ac6  sub     rsp, 20h
0x180002aca  mov     rbx, rcx
0x180002acd  xor     edx, edx; bool
0x180002acf  call    ?ExecuteObjectMain@CAtlComModule@ATL@@QEAAX_N@Z; ATL::CAtlComModule::ExecuteObjectMain(bool)
0x180002ad4  mov     rcx, rbx; this
0x180002ad7  add     rsp, 20h
0x180002adb  pop     rbx
0x180002adc  jmp     ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
```
