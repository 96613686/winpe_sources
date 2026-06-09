# ATL::CAtlDllModuleT<CSecurityCenterUIModule>::~CAtlDllModuleT<CSecurityCenterUIModule>(void)

- ea: `0x1800019c0`
- end: `0x1800019dd`
- name: `??1?$CAtlDllModuleT@VCSecurityCenterUIModule@@@ATL@@UEAA@XZ`
- size: `29`
- prototype: `__int64 __fastcall(ATL::CAtlModule *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004300`

## callees

- `0x1800019f0`
- `0x180001a60`

## pseudocode

```c
void __fastcall ATL::CAtlDllModuleT<CSecurityCenterUIModule>::~CAtlDllModuleT<CSecurityCenterUIModule>(
        ATL::CAtlModule *this)
{
  ATL::CAtlComModule::ExecuteObjectMain(this, 0);
  ATL::CAtlModule::~CAtlModule(this);
}

```

## disassembly

```asm
0x1800019c0  push    rbx
0x1800019c2  sub     rsp, 20h
0x1800019c6  mov     rbx, rcx
0x1800019c9  xor     edx, edx; bool
0x1800019cb  call    ?ExecuteObjectMain@CAtlComModule@ATL@@QEAAX_N@Z; ATL::CAtlComModule::ExecuteObjectMain(bool)
0x1800019d0  mov     rcx, rbx; this
0x1800019d3  add     rsp, 20h
0x1800019d7  pop     rbx
0x1800019d8  jmp     ??1CAtlModule@ATL@@UEAA@XZ; ATL::CAtlModule::~CAtlModule(void)
```
