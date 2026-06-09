# ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)

- ea: `0x180006a1c`
- end: `0x180006a51`
- name: `?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800069a8`

## callees

- `0x180006a1c`

## import_xrefs

- `msvcrt!free` at `0x180006a31`
- `msvcrt!free` at `0x180006a31`

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
0x180006a1c  mov     [rsp+arg_0], rbx
0x180006a21  push    rdi
0x180006a22  sub     rsp, 20h
0x180006a26  mov     rbx, rcx
0x180006a29  mov     rcx, [rcx]; Block
0x180006a2c  test    rcx, rcx
0x180006a2f  jz      short loc_180006A3E
0x180006a31  call    cs:__imp_free
0x180006a37  mov     qword ptr [rbx], 0
0x180006a3e  mov     qword ptr [rbx+8], 0
0x180006a46  mov     rbx, [rsp+28h+arg_0]
0x180006a4b  add     rsp, 20h
0x180006a4f  pop     rdi
0x180006a50  retn
```
