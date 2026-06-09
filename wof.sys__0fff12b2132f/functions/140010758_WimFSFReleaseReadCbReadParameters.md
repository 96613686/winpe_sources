# WimFSFReleaseReadCbReadParameters

- ea: `0x140010758`
- end: `0x14001076b`
- name: `WimFSFReleaseReadCbReadParameters`
- size: `19`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14002d678`
- `0x14003d2d0`

## callees

- `0x14000cfe0`

## pseudocode

```c
__int64 __fastcall WimFSFReleaseReadCbReadParameters(__int64 a1)
{
  return WimFSFReleaseReadCompletionContext((volatile signed __int32 *)(a1 - 24));
}

```

## disassembly

```asm
0x140010758  sub     rsp, 28h
0x14001075c  add     rcx, 0FFFFFFFFFFFFFFE8h; Entry
0x140010760  call    WimFSFReleaseReadCompletionContext
0x140010765  add     rsp, 28h
0x140010769  retn
```
