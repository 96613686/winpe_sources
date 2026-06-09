# ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)

- ea: `0x180001b40`
- end: `0x180001b6a`
- name: `?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ`
- size: `42`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001770`
- `0x18000b160`

## callees

- `0x180001b40`

## import_xrefs

- `msvcrt!free` at `0x180001b51`
- `msvcrt!free` at `0x180001b51`

## pseudocode

```c
__int64 __fastcall ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll(
        __int64 a1)
{
  void *v2; // rcx
  __int64 result; // rax

  v2 = *(void **)a1;
  if ( v2 )
  {
    free(v2);
    result = 0;
    *(_QWORD *)a1 = 0;
  }
  else
  {
    result = 0;
  }
  *(_QWORD *)(a1 + 8) = 0;
  return result;
}

```

## disassembly

```asm
0x180001b40  push    rbx
0x180001b42  sub     rsp, 20h
0x180001b46  mov     rbx, rcx
0x180001b49  mov     rcx, [rcx]; Block
0x180001b4c  test    rcx, rcx
0x180001b4f  jz      short loc_180001B5E
0x180001b51  call    cs:__imp_free
0x180001b57  xor     eax, eax
0x180001b59  mov     [rbx], rax
0x180001b5c  jmp     short loc_180001B60
0x180001b5e  xor     eax, eax
0x180001b60  mov     [rbx+8], rax
0x180001b64  add     rsp, 20h
0x180001b68  pop     rbx
0x180001b69  retn
```
