# ATL::CComCriticalSection::Init(void)

- ea: `0x180007ffc`
- end: `0x18000801c`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001040`
- `0x1800010f0`
- `0x180001130`
- `0x180002aac`
- `0x1800080a0`
- `0x1800265d0`

## callees

- `0x180007ffc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180008000`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180008000`

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
0x180007ffc  sub     rsp, 38h
0x180008000  call    cs:__imp_InitializeCriticalSection
0x180008006  xor     eax, eax
0x180008008  mov     [rsp+38h+var_18], eax
0x18000800c  jmp     short loc_180008017
0x18000800e  mov     eax, 8007000Eh
0x180008013  mov     [rsp+38h+var_18], eax
0x180008017  add     rsp, 38h
0x18000801b  retn
```
