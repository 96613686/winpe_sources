# CTPtrArray<uchar,20>::RemoveAt(ulong,ulong)

- ea: `0x180010268`
- end: `0x1800102ad`
- name: `?RemoveAt@?$CTPtrArray@E$0BE@@@QEAAHKK@Z`
- size: `69`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000fe30`
- `0x180010060`

## callees

- `0x180010268`
- `0x1800102b4`

## pseudocode

```c
_BOOL8 __fastcall CTPtrArray<unsigned char,20>::RemoveAt(__int64 a1)
{
  int v3; // edi
  int v4; // eax

  if ( !*(_DWORD *)(a1 + 216) )
    return 0;
  v3 = 0;
  do
  {
    v4 = CTSparseBlock<unsigned long,unsigned char *,20,1>::RemoveValue(a1);
    if ( v4 < 0 )
      break;
    --*(_DWORD *)(a1 + 216);
    ++v3;
  }
  while ( !v3 );
  return v4 >= 0;
}

```

## disassembly

```asm
0x180010268  mov     [rsp+arg_0], rbx
0x18001026d  push    rdi
0x18001026e  sub     rsp, 20h
0x180010272  cmp     dword ptr [rcx+0D8h], 1
0x180010279  mov     rbx, rcx
0x18001027c  jnb     short loc_180010282
0x18001027e  xor     eax, eax
0x180010280  jmp     short loc_1800102A2
0x180010282  xor     edi, edi
0x180010284  mov     rcx, rbx
0x180010287  call    ?RemoveValue@?$CTSparseBlock@KPEAE$0BE@$00@@QEAAJK@Z; CTSparseBlock<ulong,uchar *,20,1>::RemoveValue(ulong)
0x18001028c  test    eax, eax
0x18001028e  js      short loc_18001029D
0x180010290  dec     dword ptr [rbx+0D8h]
0x180010296  inc     edi
0x180010298  cmp     edi, 1
0x18001029b  jb      short loc_180010284
0x18001029d  not     eax
0x18001029f  shr     eax, 1Fh
0x1800102a2  mov     rbx, [rsp+28h+arg_0]
0x1800102a7  add     rsp, 20h
0x1800102ab  pop     rdi
0x1800102ac  retn
```
