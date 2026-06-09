# WcIsPlaceHolderDirectory

- ea: `0x140001bc8`
- end: `0x140001bf2`
- name: `WcIsPlaceHolderDirectory`
- size: `42`
- prototype: `bool __fastcall(__int64, __int64)`
- caller_count: `18`
- callee_count: `2`
- tags: ``

## callers

- `0x1400184f0`
- `0x140018e28`
- `0x1400198a0`
- `0x14001ecb8`
- `0x140023890`
- `0x140023c90`
- `0x140024eb0`
- `0x140024fb0`
- `0x1400260d0`
- `0x140026e30`
- `0x1400278a4`
- `0x140027f74`
- `0x1400285c4`
- `0x140028820`
- `0x14002898c`
- `0x14002ef90`
- `0x14002f26c`
- `0x140030ac0`

## callees

- `0x140001bc8`
- `0x140001bf8`

## pseudocode

```c
bool __fastcall WcIsPlaceHolderDirectory(__int64 a1, __int64 a2)
{
  return WcIsPlaceHolder(a1) && a2 && (*(_DWORD *)(a2 + 24) & 0x10) != 0;
}

```

## disassembly

```asm
0x140001bc8  push    rbx
0x140001bca  sub     rsp, 20h
0x140001bce  mov     rbx, rdx
0x140001bd1  call    WcIsPlaceHolder
0x140001bd6  test    al, al
0x140001bd8  jz      short loc_140001BEE
0x140001bda  test    rbx, rbx
0x140001bdd  jz      short loc_140001BEE
0x140001bdf  mov     eax, [rbx+18h]
0x140001be2  shr     eax, 4
0x140001be5  and     al, 1
0x140001be7  add     rsp, 20h
0x140001beb  pop     rbx
0x140001bec  retn
0x140001bee  xor     al, al
0x140001bf0  jmp     short loc_140001BE7
```
