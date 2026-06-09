# operator delete(void *,unsigned __int64)

- ea: `0x1800086f0`
- end: `0x1800086f5`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `23`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004230`
- `0x18000a2e0`
- `0x18000a320`
- `0x18000c8fc`
- `0x18000cc30`
- `0x18000cc70`
- `0x180014e94`
- `0x180014eb8`
- `0x180015740`
- `0x180015780`
- `0x1800157b0`
- `0x1800157f0`
- `0x180015820`
- `0x180015850`
- `0x1800158b0`
- `0x1800158f0`
- `0x180015930`
- `0x18001a530`
- `0x18001a550`
- `0x18001e8d0`
- `0x18001fc70`
- `0x180021a50`
- `0x180021aa0`

## callees

- `0x1800042a0`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *a1)
{
  ??3@YAXPEAX@Z(a1);
}

```

## disassembly

```asm
0x1800086f0  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
