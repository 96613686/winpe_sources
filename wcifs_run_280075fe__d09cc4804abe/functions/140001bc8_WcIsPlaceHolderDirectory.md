# WcIsPlaceHolderDirectory

- ea: `0x140001bc8`
- end: `0x140001bf2`
- name: `WcIsPlaceHolderDirectory`
- size: `42`
- prototype: ``
- caller_count: `18`
- callee_count: `2`
- tags: ``

## callers

- `0x1400184f0`
- `0x140018e28`
- `0x1400198a0`
- `0x14001ecb8`
- `0x140023840`
- `0x140023c40`
- `0x140024e60`
- `0x140024f60`
- `0x140026080`
- `0x140026de0`
- `0x140027854`
- `0x140027f24`
- `0x140028574`
- `0x1400287d0`
- `0x14002893c`
- `0x14002ef40`
- `0x14002f21c`
- `0x140030a70`

## callees

- `0x140001bc8`
- `0x140001bf8`

## pseudocode

```c
bool __fastcall WcIsPlaceHolderDirectory(__int64 a1, __int64 a2)
{
  return (unsigned __int8)WcIsPlaceHolder(a1) && a2 && (*(_DWORD *)(a2 + 24) & 0x10) != 0;
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
