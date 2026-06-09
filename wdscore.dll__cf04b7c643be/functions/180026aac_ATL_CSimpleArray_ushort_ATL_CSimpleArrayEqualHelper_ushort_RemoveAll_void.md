# ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)

- ea: `0x180026aac`
- end: `0x180026ae8`
- name: `?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180026910`

## callees

- `0x180026aac`

## import_xrefs

- `msvcrt!free` at `0x180026ac1`
- `msvcrt!free` at `0x180026ac1`

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
0x180026aac  mov     [rsp+arg_0], rbx
0x180026ab1  push    rdi
0x180026ab2  sub     rsp, 20h
0x180026ab6  mov     rbx, rcx
0x180026ab9  mov     rcx, [rcx]; Block
0x180026abc  test    rcx, rcx
0x180026abf  jz      short loc_180026AD4
0x180026ac1  call    cs:__imp_free
0x180026ac8  nop     dword ptr [rax+rax+00h]
0x180026acd  mov     qword ptr [rbx], 0
0x180026ad4  mov     qword ptr [rbx+8], 0
0x180026adc  mov     rbx, [rsp+28h+arg_0]
0x180026ae1  add     rsp, 20h
0x180026ae5  pop     rdi
0x180026ae6  retn
```
