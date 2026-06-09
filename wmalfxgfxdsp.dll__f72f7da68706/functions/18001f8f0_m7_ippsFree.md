# m7_ippsFree

- ea: `0x18001f8f0`
- end: `0x18001f907`
- name: `m7_ippsFree`
- size: `23`
- prototype: ``
- caller_count: `49`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180018970`
- `0x180018990`
- `0x180018af0`
- `0x180018ccc`
- `0x180019020`
- `0x180019110`
- `0x1800194e0`
- `0x1800196c0`
- `0x18001981c`
- `0x180019b10`
- `0x180019cb0`
- `0x180019eb0`
- `0x18001a220`
- `0x18001a310`
- `0x18001a6e0`
- `0x18001a900`
- `0x18001aa94`
- `0x18001adb0`
- `0x18001af50`
- `0x18001b150`
- `0x18001b4c0`
- `0x18001b5b0`
- `0x18001b980`
- `0x18001bba0`
- `0x18001bd34`
- `0x18001c438`
- `0x18001c560`
- `0x18001c700`
- `0x18001c9d0`
- `0x18001cbe0`
- `0x18001ce80`
- `0x18001d170`
- `0x18001d3d0`
- `0x18001d570`
- `0x18001d830`
- `0x18001da40`
- `0x18001dce0`
- `0x18001dfd0`
- `0x18001e160`
- `0x18001e300`
- `0x18001e5c0`
- `0x18001e7d0`
- `0x18001ea70`
- `0x18001ed60`
- `0x1800556c4`
- `0x180059558`
- `0x18005b08c`
- `0x18005bc88`
- `0x18005e7ec`

## callees

- `0x180015104`
- `0x18001f8f0`

## pseudocode

```c
void __fastcall m7_ippsFree(__int64 a1)
{
  if ( a1 )
    operator delete(*(void **)(a1 - 8));
}

```

## disassembly

```asm
0x18001f8f0  sub     rsp, 28h
0x18001f8f4  test    rcx, rcx
0x18001f8f7  jz      short loc_18001F902
0x18001f8f9  mov     rcx, [rcx-8]; Block
0x18001f8fd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001f902  add     rsp, 28h
0x18001f906  retn
```
