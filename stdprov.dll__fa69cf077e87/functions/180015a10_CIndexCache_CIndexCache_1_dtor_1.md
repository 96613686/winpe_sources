# _CIndexCache::CIndexCache_::_1_::dtor$1

- ea: `0x180015a10`
- end: `0x180015a22`
- name: `_CIndexCache::CIndexCache_::_1_::dtor$1`
- size: `18`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `wbemcomn!??1CFlexArray@@QEAA@XZ` at `0x180015a1b`

## pseudocode

```c
void __fastcall CIndexCache::CIndexCache_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  CFlexArray::~CFlexArray((CFlexArray *)(*(_QWORD *)(a2 + 48) + 8LL));
}

```

## disassembly

```asm
0x180015a10  mov     rcx, [rdx+30h]
0x180015a17  add     rcx, 8
0x180015a1b  jmp     cs:__imp_??1CFlexArray@@QEAA@XZ; CFlexArray::~CFlexArray(void)
```
