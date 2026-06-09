# SOCKADDR_SIZE

- ea: `0x1400034c0`
- end: `0x1400034e1`
- name: `SOCKADDR_SIZE`
- size: `33`
- prototype: `UCHAR __stdcall(ADDRESS_FAMILY af)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x140001550`
- `0x140001a70`
- `0x140001ce0`
- `0x140002920`
- `0x140002fb0`
- `0x140004df4`
- `0x140006608`
- `0x140007b90`
- `0x140011cb4`

## callees

- `0x1400034c0`

## pseudocode

```c
UCHAR __stdcall SOCKADDR_SIZE(ADDRESS_FAMILY af)
{
  if ( af >= 0x23u )
    return sockaddr_size[0];
  else
    return sockaddr_size[af];
}

```

## disassembly

```asm
0x1400034c0  cmp     cx, 23h ; '#'
0x1400034c4  jnb     short loc_1400034D6
0x1400034c6  movzx   eax, cx
0x1400034c9  lea     rcx, sockaddr_size
0x1400034d0  movzx   eax, byte ptr [rax+rcx]
0x1400034d4  retn
0x1400034d6  lea     rcx, sockaddr_size
0x1400034dd  movzx   eax, byte ptr [rcx]
0x1400034e0  retn
```
