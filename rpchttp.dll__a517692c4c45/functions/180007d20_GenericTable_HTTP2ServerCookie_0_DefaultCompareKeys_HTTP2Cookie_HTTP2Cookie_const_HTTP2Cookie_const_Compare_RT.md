# GenericTable<HTTP2ServerCookie,0,&DefaultCompareKeys<HTTP2Cookie>(HTTP2Cookie const &,HTTP2Cookie const &)>::Compare(_RTL_AVL_TABLE *,void *,void *)

- ea: `0x180007d20`
- end: `0x180007d4f`
- name: `?Compare@?$GenericTable@VHTTP2ServerCookie@@$0A@$1??$DefaultCompareKeys@VHTTP2Cookie@@@@YAHAEBVHTTP2Cookie@@0@Z@@CA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z`
- size: `47`
- prototype: `RTL_AVL_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180007d20`
- `0x180024611`

## pseudocode

```c
__int64 __fastcall GenericTable<HTTP2ServerCookie,0,&int DefaultCompareKeys<HTTP2Cookie>(HTTP2Cookie const &,HTTP2Cookie const &)>::Compare(
        struct _RTL_AVL_TABLE *Table,
        PVOID FirstStruct,
        PVOID SecondStruct)
{
  int v3; // ecx

  v3 = memcmp_0(FirstStruct, SecondStruct, 0x10u);
  if ( v3 )
    return v3 >= 0;
  else
    return 2;
}

```

## disassembly

```asm
0x180007d20  sub     rsp, 28h
0x180007d24  mov     rax, r8
0x180007d27  mov     rcx, rdx; Buf1
0x180007d2a  mov     rdx, rax; Buf2
0x180007d2d  mov     r8d, 10h; Size
0x180007d33  call    memcmp_0
0x180007d38  mov     ecx, eax
0x180007d3a  test    eax, eax
0x180007d3c  jnz     short loc_180007D43
0x180007d3e  lea     eax, [rcx+2]
0x180007d41  jmp     short loc_180007D4A
0x180007d43  xor     eax, eax
0x180007d45  test    ecx, ecx
0x180007d47  setns   al
0x180007d4a  add     rsp, 28h
0x180007d4e  retn
```
