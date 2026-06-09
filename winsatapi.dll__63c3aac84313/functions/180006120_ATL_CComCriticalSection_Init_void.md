# ATL::CComCriticalSection::Init(void)

- ea: `0x180006120`
- end: `0x180006140`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x180001060`
- `0x1800010a0`
- `0x180005af0`
- `0x180005c20`
- `0x180005f50`
- `0x18000e010`

## callees

- `0x180006120`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180006124`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180006124`

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
0x180006120  sub     rsp, 38h
0x180006124  call    cs:__imp_InitializeCriticalSection
0x18000612a  xor     eax, eax
0x18000612c  mov     [rsp+38h+var_18], eax
0x180006130  jmp     short loc_18000613B
0x180006132  mov     eax, 8007000Eh
0x180006137  mov     [rsp+38h+var_18], eax
0x18000613b  add     rsp, 38h
0x18000613f  retn
```
