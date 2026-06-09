# CASFMarkerObject::IsBackwardsCompatible(void)

- ea: `0x1800043e0`
- end: `0x1800043e6`
- name: `?IsBackwardsCompatible@CASFMarkerObject@@UEAAHXZ`
- size: `6`
- prototype: `__int64 __fastcall(CASFMarkerObject *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000175c`

## pseudocode

```c
__int64 __fastcall CASFMarkerObject::IsBackwardsCompatible(CASFMarkerObject *this)
{
  return 1;
}

```

## disassembly

```asm
0x1800043e0  mov     eax, 1
0x1800043e5  retn
```
