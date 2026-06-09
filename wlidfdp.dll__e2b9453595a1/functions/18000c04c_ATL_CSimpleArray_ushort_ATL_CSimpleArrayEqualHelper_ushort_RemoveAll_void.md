# ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)

- ea: `0x18000c04c`
- end: `0x18000c080`
- name: `?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ`
- size: `52`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000be9c`
- `0x18000bf34`

## callees

- `0x180003384`
- `0x18000c04c`

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
0x18000c04c  mov     [rsp+arg_0], rbx
0x18000c051  push    rdi
0x18000c052  sub     rsp, 20h
0x18000c056  mov     rbx, rcx
0x18000c059  mov     rcx, [rcx]; Block
0x18000c05c  test    rcx, rcx
0x18000c05f  jz      short loc_18000C06D
0x18000c061  call    free
0x18000c066  mov     qword ptr [rbx], 0
0x18000c06d  mov     qword ptr [rbx+8], 0
0x18000c075  mov     rbx, [rsp+28h+arg_0]
0x18000c07a  add     rsp, 20h
0x18000c07e  pop     rdi
0x18000c07f  retn
```
