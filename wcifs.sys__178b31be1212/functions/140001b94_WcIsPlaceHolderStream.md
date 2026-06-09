# WcIsPlaceHolderStream

- ea: `0x140001b94`
- end: `0x140001bc0`
- name: `WcIsPlaceHolderStream`
- size: `44`
- prototype: `bool __fastcall(__int64, __int64)`
- caller_count: `16`
- callee_count: `2`
- tags: ``

## callers

- `0x140006340`
- `0x1400184f0`
- `0x140018e28`
- `0x1400196e0`
- `0x1400198a0`
- `0x140019f1c`
- `0x14001a02c`
- `0x140023890`
- `0x140023aa4`
- `0x140023c90`
- `0x140024fb0`
- `0x1400260d0`
- `0x140026e30`
- `0x1400278a4`
- `0x140027f74`
- `0x14002f26c`

## callees

- `0x140001b94`
- `0x140001bf8`

## pseudocode

```c
bool __fastcall WcIsPlaceHolderStream(__int64 a1, __int64 a2)
{
  return WcIsPlaceHolder(a1) && a2 && (*(_DWORD *)(a2 + 24) & 0x10) == 0;
}

```

## disassembly

```asm
0x140001b94  push    rbx
0x140001b96  sub     rsp, 20h
0x140001b9a  mov     rbx, rdx
0x140001b9d  call    WcIsPlaceHolder
0x140001ba2  test    al, al
0x140001ba4  jz      short loc_140001BBC
0x140001ba6  test    rbx, rbx
0x140001ba9  jz      short loc_140001BBC
0x140001bab  mov     eax, [rbx+18h]
0x140001bae  shr     eax, 4
0x140001bb1  not     al
0x140001bb3  and     al, 1
0x140001bb5  add     rsp, 20h
0x140001bb9  pop     rbx
0x140001bba  retn
0x140001bbc  xor     al, al
0x140001bbe  jmp     short loc_140001BB5
```
