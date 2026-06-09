# __scrt_initialize_onexit_tables

- ea: `0x180004f68`
- end: `0x180004ff3`
- name: `__scrt_initialize_onexit_tables`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180004e28`

## callees

- `0x180004f68`
- `0x180005108`
- `0x18000544c`
- `0x1800054e2`

## pseudocode

```c
char __fastcall _scrt_initialize_onexit_tables(unsigned int a1)
{
  if ( !byte_18000D4B0 )
  {
    if ( a1 > 1 )
      _scrt_fastfail(5);
    if ( !_scrt_is_ucrt_dll_in_use() || a1 )
    {
      *(__m128i *)&Table._first = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
      Table._end = (_PVFV *)-1LL;
      *(_OWORD *)&stru_18000D498._first = *(_OWORD *)&Table._first;
      stru_18000D498._end = (_PVFV *)-1LL;
    }
    else if ( initialize_onexit_table(&Table) || initialize_onexit_table(&stru_18000D498) )
    {
      return 0;
    }
    byte_18000D4B0 = 1;
  }
  return 1;
}

```

## disassembly

```asm
0x180004f68  push    rbx
0x180004f6a  sub     rsp, 20h
0x180004f6e  cmp     cs:byte_18000D4B0, 0
0x180004f75  mov     ebx, ecx
0x180004f77  jnz     short loc_180004FE0
0x180004f79  cmp     ecx, 1
0x180004f7c  ja      short loc_180004FE8
0x180004f7e  call    __scrt_is_ucrt_dll_in_use
0x180004f83  test    eax, eax
0x180004f85  jz      short loc_180004FAF
0x180004f87  test    ebx, ebx
0x180004f89  jnz     short loc_180004FAF
0x180004f8b  lea     rcx, Table; Table
0x180004f92  call    _initialize_onexit_table
0x180004f97  test    eax, eax
0x180004f99  jnz     short loc_180004FAB
0x180004f9b  lea     rcx, stru_18000D498; Table
0x180004fa2  call    _initialize_onexit_table
0x180004fa7  test    eax, eax
0x180004fa9  jz      short loc_180004FD9
0x180004fab  xor     al, al
0x180004fad  jmp     short loc_180004FE2
0x180004faf  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180004fb7  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004fbb  movdqu  xmmword ptr cs:Table._first, xmm0
0x180004fc3  mov     cs:Table._end, rax
0x180004fca  movdqu  xmmword ptr cs:stru_18000D498._first, xmm0
0x180004fd2  mov     cs:stru_18000D498._end, rax
0x180004fd9  mov     cs:byte_18000D4B0, 1
0x180004fe0  mov     al, 1
0x180004fe2  add     rsp, 20h
0x180004fe6  pop     rbx
0x180004fe7  retn
0x180004fe8  mov     ecx, 5
0x180004fed  call    __scrt_fastfail
```
