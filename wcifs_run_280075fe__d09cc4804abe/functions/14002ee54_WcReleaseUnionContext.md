# WcReleaseUnionContext

- ea: `0x14002ee54`
- end: `0x14002ee71`
- name: `WcReleaseUnionContext`
- size: `29`
- prototype: ``
- caller_count: `21`
- callee_count: `2`
- tags: ``

## callers

- `0x1400016b4`
- `0x140001710`
- `0x14000696c`
- `0x1400184f0`
- `0x140018970`
- `0x140018e28`
- `0x14001bcec`
- `0x14001e700`
- `0x14001f1c8`
- `0x14001fe40`
- `0x140020e60`
- `0x140023c40`
- `0x140026210`
- `0x140026c9c`
- `0x140026de0`
- `0x140027854`
- `0x140027f24`
- `0x140030060`
- `0x1400303e8`
- `0x140030a70`
- `0x1400318f0`

## callees

- `0x14001d390`
- `0x14002ee54`

## pseudocode

```c
void __fastcall WcReleaseUnionContext(volatile signed __int32 *a1)
{
  if ( _InterlockedExchangeAdd(a1, 0xFFFFFFFF) == 1 )
    WcCleanupUnionContext(a1);
}

```

## disassembly

```asm
0x14002ee54  sub     rsp, 28h
0x14002ee58  or      eax, 0FFFFFFFFh
0x14002ee5b  lock xadd [rcx], eax
0x14002ee5f  cmp     eax, 1
0x14002ee62  jz      short loc_14002EE6A
0x14002ee64  add     rsp, 28h
0x14002ee68  retn
0x14002ee6a  call    WcCleanupUnionContext
0x14002ee6f  jmp     short loc_14002EE64
```
