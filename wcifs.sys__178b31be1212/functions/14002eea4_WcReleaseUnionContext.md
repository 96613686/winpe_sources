# WcReleaseUnionContext

- ea: `0x14002eea4`
- end: `0x14002eec1`
- name: `WcReleaseUnionContext`
- size: `29`
- prototype: `void __fastcall(volatile signed __int32 *)`
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
- `0x140023c90`
- `0x140026260`
- `0x140026cec`
- `0x140026e30`
- `0x1400278a4`
- `0x140027f74`
- `0x1400300b0`
- `0x140030438`
- `0x140030ac0`
- `0x140031940`

## callees

- `0x14001d390`
- `0x14002eea4`

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
0x14002eea4  sub     rsp, 28h
0x14002eea8  or      eax, 0FFFFFFFFh
0x14002eeab  lock xadd [rcx], eax
0x14002eeaf  cmp     eax, 1
0x14002eeb2  jz      short loc_14002EEBA
0x14002eeb4  add     rsp, 28h
0x14002eeb8  retn
0x14002eeba  call    WcCleanupUnionContext
0x14002eebf  jmp     short loc_14002EEB4
```
