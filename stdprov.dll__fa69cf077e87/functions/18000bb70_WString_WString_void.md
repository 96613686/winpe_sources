# WString::~WString(void)

- ea: `0x18000bb70`
- end: `0x18000bb83`
- name: `??1WString@@QEAA@XZ`
- size: `19`
- prototype: `void __fastcall(WString *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180015f46`
- `0x1800163d8`
- `0x1800163f1`
- `0x180016d75`

## import_xrefs

- `wbemcomn!?DeleteString@WString@@AEAAXPEAG@Z` at `0x18000bb77`
- `wbemcomn!?DeleteString@WString@@AEAAXPEAG@Z` at `0x18000bb77`

## pseudocode

```c
void __fastcall WString::~WString(WString *this)
{
  WString::DeleteString(this, *(unsigned __int16 **)this);
}

```

## disassembly

```asm
0x18000bb70  sub     rsp, 28h
0x18000bb74  mov     rdx, [rcx]
0x18000bb77  call    cs:__imp_?DeleteString@WString@@AEAAXPEAG@Z; WString::DeleteString(ushort *)
0x18000bb7d  nop
0x18000bb7e  add     rsp, 28h
0x18000bb82  retn
```
