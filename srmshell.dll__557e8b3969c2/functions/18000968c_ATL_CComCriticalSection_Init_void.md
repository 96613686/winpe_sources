# ATL::CComCriticalSection::Init(void)

- ea: `0x18000968c`
- end: `0x1800096ac`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800010c0`
- `0x180001150`
- `0x180001190`
- `0x1800011d0`
- `0x18000688c`
- `0x180013c80`
- `0x1800157a0`

## callees

- `0x18000968c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180009690`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180009690`

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
0x18000968c  sub     rsp, 38h
0x180009690  call    cs:__imp_InitializeCriticalSection
0x180009696  xor     eax, eax
0x180009698  mov     [rsp+38h+var_18], eax
0x18000969c  jmp     short loc_1800096A7
0x18000969e  mov     eax, 8007000Eh
0x1800096a3  mov     [rsp+38h+var_18], eax
0x1800096a7  add     rsp, 38h
0x1800096ab  retn
```
