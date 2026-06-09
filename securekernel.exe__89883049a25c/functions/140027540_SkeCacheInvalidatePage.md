# SkeCacheInvalidatePage

- ea: `0x140027540`
- end: `0x140027561`
- name: `SkeCacheInvalidatePage`
- size: `33`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x140025854`
- `0x1400273c8`
- `0x14005bd70`
- `0x14005c1e0`
- `0x14005ef50`
- `0x140063ca8`
- `0x140085e00`

## callees

- `0x140027540`
- `0x1400f0520`
- `0x1400f0550`

## pseudocode

```c
__int64 SkeCacheInvalidatePage()
{
  if ( _bittest64(&SkeFeatureBits, 0x23u) )
    return SkiCacheInvalidatePageOpt();
  else
    return SkiCacheInvalidatePage();
}

```

## disassembly

```asm
0x140027540  sub     rsp, 28h
0x140027544  bt      cs:SkeFeatureBits, 23h ; '#'
0x14002754d  jnb     short loc_140027556
0x14002754f  call    SkiCacheInvalidatePageOpt
0x140027554  jmp     short loc_14002755B
0x140027556  call    SkiCacheInvalidatePage
0x14002755b  add     rsp, 28h
0x14002755f  retn
```
