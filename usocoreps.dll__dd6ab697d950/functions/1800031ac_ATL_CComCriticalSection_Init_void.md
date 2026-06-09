# ATL::CComCriticalSection::Init(void)

- ea: `0x1800031ac`
- end: `0x1800031cc`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x180001060`
- `0x1800010a0`
- `0x1800010d0`
- `0x1800043ec`
- `0x180004714`

## callees

- `0x1800031ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800031b0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800031b0`

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
0x1800031ac  sub     rsp, 38h
0x1800031b0  call    cs:__imp_InitializeCriticalSection
0x1800031b6  xor     eax, eax
0x1800031b8  mov     [rsp+38h+var_18], eax
0x1800031bc  jmp     short loc_1800031C7
0x1800031be  mov     eax, 8007000Eh
0x1800031c3  mov     [rsp+38h+var_18], eax
0x1800031c7  add     rsp, 38h
0x1800031cb  retn
```
