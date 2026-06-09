# ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)

- ea: `0x1800088fc`
- end: `0x180008930`
- name: `?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002100`

## callees

- `0x180002eb4`
- `0x1800088fc`

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
0x1800088fc  mov     [rsp+arg_0], rbx
0x180008901  push    rdi
0x180008902  sub     rsp, 20h
0x180008906  mov     rbx, rcx
0x180008909  mov     rcx, [rcx]; Block
0x18000890c  test    rcx, rcx
0x18000890f  jz      short loc_18000891D
0x180008911  call    free
0x180008916  mov     qword ptr [rbx], 0
0x18000891d  mov     qword ptr [rbx+8], 0
0x180008925  mov     rbx, [rsp+28h+arg_0]
0x18000892a  add     rsp, 20h
0x18000892e  pop     rdi
0x18000892f  retn
```
