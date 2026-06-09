# operator delete(void *,unsigned __int64)

- ea: `0x14000fab8`
- end: `0x14000fabd`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `260`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140001e80`
- `0x140002350`
- `0x140002820`
- `0x140003290`
- `0x140003450`
- `0x140003640`
- `0x1400038e0`
- `0x140004140`
- `0x1400049a0`
- `0x1400053f0`
- `0x140005a40`
- `0x140005da0`
- `0x140006100`
- `0x140006460`
- `0x140006820`
- `0x140006ab0`
- `0x1400083f0`
- `0x1400086a0`
- `0x140008a90`
- `0x1400091b4`
- `0x1400091f0`
- `0x140009220`
- `0x140009280`
- `0x14000934c`
- `0x1400094c0`
- `0x14000a190`
- `0x14000a1f8`
- `0x14000aae0`
- `0x14000b360`
- `0x140012590`
- `0x140012a50`
- `0x140012ae0`
- `0x140013030`
- `0x1400130e0`
- `0x1400132b0`
- `0x140013440`
- `0x140013600`
- `0x140014080`
- `0x1400142b0`
- `0x1400144e0`
- `0x140014710`
- `0x140014bb0`
- `0x140014e20`
- `0x1400150d0`
- `0x140015330`
- `0x140015500`
- `0x1400162d0`
- `0x140016c00`
- `0x140016e00`
- `0x140017000`

## callees

- `0x14000fb20`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x14000fab8  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
