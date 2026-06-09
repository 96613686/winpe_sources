# ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::RemoveAll(void)

- ea: `0x180007f30`
- end: `0x180007f7b`
- name: `?RemoveAll@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEAAXXZ`
- size: `75`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800058b4`
- `0x1800069e4`

## callees

- `0x180007f30`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007f45`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007f5b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007f45`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007f5b`

## pseudocode

```c
void __fastcall ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::RemoveAll(
        __int64 a1)
{
  void *v2; // rcx
  void *v3; // rcx

  v2 = *(void **)a1;
  if ( v2 )
  {
    free(v2);
    *(_QWORD *)a1 = 0;
  }
  v3 = *(void **)(a1 + 8);
  if ( v3 )
  {
    free(v3);
    *(_QWORD *)(a1 + 8) = 0;
  }
  *(_DWORD *)(a1 + 16) = 0;
}

```

## disassembly

```asm
0x180007f30  mov     [rsp+arg_0], rbx
0x180007f35  push    rdi
0x180007f36  sub     rsp, 20h
0x180007f3a  mov     rbx, rcx
0x180007f3d  mov     rcx, [rcx]; Block
0x180007f40  test    rcx, rcx
0x180007f43  jz      short loc_180007F52
0x180007f45  call    cs:__imp_free
0x180007f4b  mov     qword ptr [rbx], 0
0x180007f52  mov     rcx, [rbx+8]; Block
0x180007f56  test    rcx, rcx
0x180007f59  jz      short loc_180007F69
0x180007f5b  call    cs:__imp_free
0x180007f61  mov     qword ptr [rbx+8], 0
0x180007f69  mov     dword ptr [rbx+10h], 0
0x180007f70  mov     rbx, [rsp+28h+arg_0]
0x180007f75  add     rsp, 20h
0x180007f79  pop     rdi
0x180007f7a  retn
```
