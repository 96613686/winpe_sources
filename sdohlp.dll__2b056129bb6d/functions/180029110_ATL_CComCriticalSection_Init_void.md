# ATL::CComCriticalSection::Init(void)

- ea: `0x180029110`
- end: `0x180029130`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `21`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800010d0`
- `0x1800011a0`
- `0x1800011e0`
- `0x180026a98`
- `0x180026b90`
- `0x180026c98`
- `0x180026db0`
- `0x180026ecc`
- `0x180026fe4`
- `0x180027100`
- `0x180027230`
- `0x180027348`
- `0x180027460`
- `0x180027584`
- `0x180027644`
- `0x18002d2d0`
- `0x18002f300`
- `0x18003053c`
- `0x18003420c`
- `0x180034328`
- `0x180040ee8`

## callees

- `0x180029110`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180029114`
- `KERNEL32!InitializeCriticalSection` at `0x180029114`

## pseudocode

```c
__int64 __fastcall ATL::CComCriticalSection::Init(struct _RTL_CRITICAL_SECTION *this)
{
  InitializeCriticalSection(this);
  return 0;
}

```

## disassembly

```asm
0x180029110  sub     rsp, 38h
0x180029114  call    cs:__imp_InitializeCriticalSection
0x18002911a  xor     eax, eax
0x18002911c  mov     [rsp+38h+var_18], eax
0x180029120  jmp     short loc_18002912B
0x180029122  mov     eax, 8007000Eh
0x180029127  mov     [rsp+38h+var_18], eax
0x18002912b  add     rsp, 38h
0x18002912f  retn
```
