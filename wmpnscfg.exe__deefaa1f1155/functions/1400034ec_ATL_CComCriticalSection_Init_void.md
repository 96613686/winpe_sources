# ATL::CComCriticalSection::Init(void)

- ea: `0x1400034ec`
- end: `0x14000350c`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001010`
- `0x1400010c0`
- `0x1400010f0`
- `0x140001130`
- `0x140004d0c`
- `0x140005034`

## callees

- `0x1400034ec`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x1400034f0`
- `KERNEL32!InitializeCriticalSection` at `0x1400034f0`

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
0x1400034ec  sub     rsp, 38h
0x1400034f0  call    cs:__imp_InitializeCriticalSection
0x1400034f6  xor     eax, eax
0x1400034f8  mov     [rsp+38h+var_18], eax
0x1400034fc  jmp     short loc_140003507
0x1400034fe  mov     eax, 8007000Eh
0x140003503  mov     [rsp+38h+var_18], eax
0x140003507  add     rsp, 38h
0x14000350b  retn
```
