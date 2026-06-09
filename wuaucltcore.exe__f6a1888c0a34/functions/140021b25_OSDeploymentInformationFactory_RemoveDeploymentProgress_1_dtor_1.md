# _OSDeploymentInformationFactory::RemoveDeploymentProgress_::_1_::dtor$1

- ea: `0x140021b25`
- end: `0x140021b31`
- name: `_OSDeploymentInformationFactory::RemoveDeploymentProgress_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14001a550`

## pseudocode

```c
void __fastcall OSDeploymentInformationFactory::RemoveDeploymentProgress_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  CAutoUnlock::~CAutoUnlock((CAutoUnlock *)(a2 + 48));
}

```

## disassembly

```asm
0x140021b25  lea     rcx, [rdx+30h]; this
0x140021b2c  jmp     ??1CAutoUnlock@@QEAA@XZ; CAutoUnlock::~CAutoUnlock(void)
```
