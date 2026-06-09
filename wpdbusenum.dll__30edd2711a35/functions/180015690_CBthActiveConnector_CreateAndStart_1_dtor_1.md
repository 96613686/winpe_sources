# _CBthActiveConnector::CreateAndStart_::_1_::dtor$1

- ea: `0x180015690`
- end: `0x18001569c`
- name: `_CBthActiveConnector::CreateAndStart_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180008ac4`

## pseudocode

```c
__int64 __fastcall CBthActiveConnector::CreateAndStart_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return ATL::CAutoPtr<CBthActiveConnector>::~CAutoPtr<CBthActiveConnector>(a2 + 80);
}

```

## disassembly

```asm
0x180015690  lea     rcx, [rdx+50h]
0x180015697  jmp     ??1?$CAutoPtr@VCBthActiveConnector@@@ATL@@QEAA@XZ; ATL::CAutoPtr<CBthActiveConnector>::~CAutoPtr<CBthActiveConnector>(void)
```
