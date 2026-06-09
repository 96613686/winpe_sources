# ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::RemoveAll(void)

- ea: `0x180005db0`
- end: `0x180005dfb`
- name: `?RemoveAll@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEAAXXZ`
- size: `75`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002d94`
- `0x180003d18`

## callees

- `0x180005db0`

## import_xrefs

- `msvcrt!free` at `0x180005dc5`
- `msvcrt!free` at `0x180005ddb`
- `msvcrt!free` at `0x180005dc5`
- `msvcrt!free` at `0x180005ddb`

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
0x180005db0  mov     [rsp+arg_0], rbx
0x180005db5  push    rdi
0x180005db6  sub     rsp, 20h
0x180005dba  mov     rbx, rcx
0x180005dbd  mov     rcx, [rcx]; Block
0x180005dc0  test    rcx, rcx
0x180005dc3  jz      short loc_180005DD2
0x180005dc5  call    cs:__imp_free
0x180005dcb  mov     qword ptr [rbx], 0
0x180005dd2  mov     rcx, [rbx+8]; Block
0x180005dd6  test    rcx, rcx
0x180005dd9  jz      short loc_180005DE9
0x180005ddb  call    cs:__imp_free
0x180005de1  mov     qword ptr [rbx+8], 0
0x180005de9  mov     dword ptr [rbx+10h], 0
0x180005df0  mov     rbx, [rsp+28h+arg_0]
0x180005df5  add     rsp, 20h
0x180005df9  pop     rdi
0x180005dfa  retn
```
