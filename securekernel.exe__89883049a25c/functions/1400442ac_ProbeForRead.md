# ProbeForRead

- ea: `0x1400442ac`
- end: `0x1400442e4`
- name: `ProbeForRead`
- size: `56`
- prototype: `void __stdcall(volatile void *Address, SIZE_T Length, ULONG Alignment)`
- caller_count: `37`
- callee_count: `2`
- tags: ``

## callers

- `0x1400134f4`
- `0x14002a2d4`
- `0x140040250`
- `0x1400406a4`
- `0x140040cc4`
- `0x1400434b8`
- `0x140043c70`
- `0x1400972bc`
- `0x14009c610`
- `0x1400ad5c4`
- `0x1400ae76c`
- `0x1400b6c24`
- `0x1400bc2dc`
- `0x1400be778`
- `0x1400be910`
- `0x1400d4e8c`
- `0x1400dcac4`
- `0x1400de648`
- `0x1400deb54`
- `0x1400df038`
- `0x1400df8e4`
- `0x1400e04c8`
- `0x1400e1000`
- `0x1400e1a84`
- `0x1400e1bf4`
- `0x1400fc554`
- `0x1400fc5b8`
- `0x1400fc62c`
- `0x1400fc664`
- `0x1400fc6a0`
- `0x1400fc6dc`
- `0x1400fc718`
- `0x1400fc778`
- `0x1400fc7c0`
- `0x1400fc808`
- `0x1400fc84c`
- `0x1400fdb7c`

## callees

- `0x140040c7c`
- `0x1400442ac`

## pseudocode

```c
void __stdcall ProbeForRead(volatile void *Address, SIZE_T Length, ULONG Alignment)
{
  if ( Length )
  {
    if ( ((Alignment - 1) & (unsigned int)Address) != 0 )
      ExRaiseDatatypeMisalignment();
  }
}

```

## disassembly

```asm
0x1400442ac  sub     rsp, 28h
0x1400442b0  test    rdx, rdx
0x1400442b3  jz      short loc_1400442DE
0x1400442b5  dec     r8d
0x1400442b8  test    rcx, r8
0x1400442bb  jz      short loc_1400442C3
0x1400442bd  call    ExRaiseDatatypeMisalignment
0x1400442c3  lea     rax, [rcx+rdx]
0x1400442c7  mov     rdx, 7FFFFFFF0000h
0x1400442d1  cmp     rax, rcx
0x1400442d4  jbe     short loc_1400442DB
0x1400442d6  cmp     rax, rdx
0x1400442d9  jbe     short loc_1400442DE
0x1400442db  mov     eax, [rdx]
0x1400442dd  nop
0x1400442de  add     rsp, 28h
0x1400442e2  retn
```
