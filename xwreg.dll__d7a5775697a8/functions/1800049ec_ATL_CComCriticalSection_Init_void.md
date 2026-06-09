# ATL::CComCriticalSection::Init(void)

- ea: `0x1800049ec`
- end: `0x180004a0c`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001070`
- `0x1800010c0`
- `0x180001120`
- `0x180004a90`
- `0x1800068f8`

## callees

- `0x1800049ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800049f0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800049f0`

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
0x1800049ec  sub     rsp, 38h
0x1800049f0  call    cs:__imp_InitializeCriticalSection
0x1800049f6  xor     eax, eax
0x1800049f8  mov     [rsp+38h+var_18], eax
0x1800049fc  jmp     short loc_180004A07
0x1800049fe  mov     eax, 8007000Eh
0x180004a03  mov     [rsp+38h+var_18], eax
0x180004a07  add     rsp, 38h
0x180004a0b  retn
```
