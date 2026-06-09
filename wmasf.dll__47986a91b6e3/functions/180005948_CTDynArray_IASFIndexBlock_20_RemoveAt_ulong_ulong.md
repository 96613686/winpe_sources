# CTDynArray<IASFIndexBlock *,20>::RemoveAt(ulong,ulong)

- ea: `0x180005948`
- end: `0x18000599d`
- name: `?RemoveAt@?$CTDynArray@PEAUIASFIndexBlock@@$0BE@@@QEAAHKK@Z`
- size: `85`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800059b0`
- `0x18002f320`
- `0x18003288c`
- `0x18003d4a0`

## callees

- `0x180005948`
- `0x180005a5c`

## pseudocode

```c
_BOOL8 __fastcall CTDynArray<IASFIndexBlock *,20>::RemoveAt(__int64 a1, unsigned int a2)
{
  int v5; // edi
  int v6; // eax

  if ( a2 + 1 > *(_DWORD *)(a1 + 216) )
    return 0;
  v5 = 0;
  do
  {
    v6 = CTSparseBlock<unsigned long,IASFIndexBlock *,20,0>::RemoveValue(a1, a2);
    if ( v6 < 0 )
      break;
    --*(_DWORD *)(a1 + 216);
    ++v5;
  }
  while ( !v5 );
  return v6 >= 0;
}

```

## disassembly

```asm
0x180005948  mov     [rsp+arg_0], rbx
0x18000594d  mov     [rsp+arg_8], rsi
0x180005952  push    rdi
0x180005953  sub     rsp, 20h
0x180005957  lea     eax, [rdx+1]
0x18000595a  mov     esi, edx
0x18000595c  mov     rbx, rcx
0x18000595f  cmp     eax, [rcx+0D8h]
0x180005965  jbe     short loc_18000596B
0x180005967  xor     eax, eax
0x180005969  jmp     short loc_18000598D
0x18000596b  xor     edi, edi
0x18000596d  mov     edx, esi
0x18000596f  mov     rcx, rbx
0x180005972  call    ?RemoveValue@?$CTSparseBlock@KPEAUIASFIndexBlock@@$0BE@$0A@@@QEAAJK@Z; CTSparseBlock<ulong,IASFIndexBlock *,20,0>::RemoveValue(ulong)
0x180005977  test    eax, eax
0x180005979  js      short loc_180005988
0x18000597b  dec     dword ptr [rbx+0D8h]
0x180005981  inc     edi
0x180005983  cmp     edi, 1
0x180005986  jb      short loc_18000596D
0x180005988  not     eax
0x18000598a  shr     eax, 1Fh
0x18000598d  mov     rbx, [rsp+28h+arg_0]
0x180005992  mov     rsi, [rsp+28h+arg_8]
0x180005997  add     rsp, 20h
0x18000599b  pop     rdi
0x18000599c  retn
```
