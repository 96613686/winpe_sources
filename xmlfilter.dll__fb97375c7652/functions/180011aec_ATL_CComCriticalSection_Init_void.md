# ATL::CComCriticalSection::Init(void)

- ea: `0x180011aec`
- end: `0x180011b0c`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001af0`
- `0x180001b60`
- `0x180001b90`
- `0x180001bd0`
- `0x180011574`
- `0x1800116b0`
- `0x1800117d0`

## callees

- `0x180011aec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180011af0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180011af0`

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
0x180011aec  sub     rsp, 38h
0x180011af0  call    cs:__imp_InitializeCriticalSection
0x180011af6  xor     eax, eax
0x180011af8  mov     [rsp+38h+var_18], eax
0x180011afc  jmp     short loc_180011B07
0x180011afe  mov     eax, 8007000Eh
0x180011b03  mov     [rsp+38h+var_18], eax
0x180011b07  add     rsp, 38h
0x180011b0b  retn
```
