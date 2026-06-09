# WcIsSourcedStream

- ea: `0x140001fd0`
- end: `0x140001ff5`
- name: `WcIsSourcedStream`
- size: `37`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x140018e28`
- `0x14001ecb8`
- `0x140023840`
- `0x140023c40`
- `0x140027854`
- `0x14002f21c`
- `0x140030a70`

## callees

- `0x140001fd0`
- `0x140001ffc`

## pseudocode

```c
bool __fastcall WcIsSourcedStream(__int64 a1)
{
  return *(_QWORD *)(a1 + 56) != a1 + 56 && (unsigned __int8)WcIsExpanded(*(_QWORD *)(a1 + 32)) == 0;
}

```

## disassembly

```asm
0x140001fd0  sub     rsp, 28h
0x140001fd4  lea     rax, [rcx+38h]
0x140001fd8  cmp     [rax], rax
0x140001fdb  jz      short loc_140001FF1
0x140001fdd  mov     rcx, [rcx+20h]
0x140001fe1  call    WcIsExpanded
0x140001fe6  test    al, al
0x140001fe8  setz    al
0x140001feb  add     rsp, 28h
0x140001fef  retn
0x140001ff1  xor     al, al
0x140001ff3  jmp     short loc_140001FEB
```
