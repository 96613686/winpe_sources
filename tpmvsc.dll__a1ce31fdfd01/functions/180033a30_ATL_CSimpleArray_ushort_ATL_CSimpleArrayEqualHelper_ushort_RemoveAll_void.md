# ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)

- ea: `0x180033a30`
- end: `0x180033a64`
- name: `?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ`
- size: `52`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800339bc`

## callees

- `0x180002a54`
- `0x180033a30`

## pseudocode

```c
void __fastcall ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll(__int64 a1)
{
  void *v2; // rcx

  v2 = *(void **)a1;
  if ( v2 )
  {
    free(v2);
    *(_QWORD *)a1 = 0;
  }
  *(_QWORD *)(a1 + 8) = 0;
}

```

## disassembly

```asm
0x180033a30  mov     [rsp+arg_0], rbx
0x180033a35  push    rdi
0x180033a36  sub     rsp, 20h
0x180033a3a  mov     rbx, rcx
0x180033a3d  mov     rcx, [rcx]; Block
0x180033a40  test    rcx, rcx
0x180033a43  jz      short loc_180033A51
0x180033a45  call    free
0x180033a4a  mov     qword ptr [rbx], 0
0x180033a51  mov     qword ptr [rbx+8], 0
0x180033a59  mov     rbx, [rsp+28h+arg_0]
0x180033a5e  add     rsp, 20h
0x180033a62  pop     rdi
0x180033a63  retn
```
