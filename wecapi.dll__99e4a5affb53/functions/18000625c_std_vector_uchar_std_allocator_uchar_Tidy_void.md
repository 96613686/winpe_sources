# std::vector<uchar,std::allocator<uchar>>::_Tidy(void)

- ea: `0x18000625c`
- end: `0x18000628f`
- name: `?_Tidy@?$vector@EV?$allocator@E@std@@@std@@IEAAXXZ`
- size: `51`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000c4f2`
- `0x18000c594`
- `0x18000c6ac`
- `0x18000c71a`

## callees

- `0x1800026c0`
- `0x18000625c`

## pseudocode

```c
void __fastcall std::vector<unsigned char>::_Tidy(__int64 a1)
{
  void *v2; // rcx

  v2 = *(void **)a1;
  if ( v2 )
  {
    operator delete(v2);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x18000625c  push    rbx
0x18000625e  sub     rsp, 20h
0x180006262  mov     rbx, rcx
0x180006265  mov     rcx, [rcx]; void *
0x180006268  test    rcx, rcx
0x18000626b  jz      short loc_180006289
0x18000626d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006272  mov     qword ptr [rbx], 0
0x180006279  mov     qword ptr [rbx+8], 0
0x180006281  mov     qword ptr [rbx+10h], 0
0x180006289  add     rsp, 20h
0x18000628d  pop     rbx
0x18000628e  retn
```
