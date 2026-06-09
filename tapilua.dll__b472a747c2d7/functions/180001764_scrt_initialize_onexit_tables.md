# __scrt_initialize_onexit_tables

- ea: `0x180001764`
- end: `0x1800017ef`
- name: `__scrt_initialize_onexit_tables`
- size: `139`
- prototype: `char __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001624`

## callees

- `0x180001764`
- `0x180001904`
- `0x180001c54`
- `0x180001cde`

## pseudocode

```c
char __fastcall _scrt_initialize_onexit_tables(unsigned int a1)
{
  if ( !byte_18000A210 )
  {
    if ( a1 > 1 )
      _scrt_fastfail(5u);
    if ( !(unsigned int)_scrt_is_ucrt_dll_in_use() || a1 )
    {
      *(__m128i *)&Table._first = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
      Table._end = (_PVFV *)-1LL;
      *(_OWORD *)&stru_18000A1F8._first = *(_OWORD *)&Table._first;
      stru_18000A1F8._end = (_PVFV *)-1LL;
    }
    else if ( initialize_onexit_table(&Table) || initialize_onexit_table(&stru_18000A1F8) )
    {
      return 0;
    }
    byte_18000A210 = 1;
  }
  return 1;
}

```

## disassembly

```asm
0x180001764  push    rbx
0x180001766  sub     rsp, 20h
0x18000176a  cmp     cs:byte_18000A210, 0
0x180001771  mov     ebx, ecx
0x180001773  jnz     short loc_1800017DC
0x180001775  cmp     ecx, 1
0x180001778  ja      short loc_1800017E4
0x18000177a  call    __scrt_is_ucrt_dll_in_use
0x18000177f  test    eax, eax
0x180001781  jz      short loc_1800017AB
0x180001783  test    ebx, ebx
0x180001785  jnz     short loc_1800017AB
0x180001787  lea     rcx, Table; Table
0x18000178e  call    _initialize_onexit_table
0x180001793  test    eax, eax
0x180001795  jnz     short loc_1800017A7
0x180001797  lea     rcx, stru_18000A1F8; Table
0x18000179e  call    _initialize_onexit_table
0x1800017a3  test    eax, eax
0x1800017a5  jz      short loc_1800017D5
0x1800017a7  xor     al, al
0x1800017a9  jmp     short loc_1800017DE
0x1800017ab  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1800017b3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800017b7  movdqu  xmmword ptr cs:Table._first, xmm0
0x1800017bf  mov     cs:Table._end, rax
0x1800017c6  movdqu  xmmword ptr cs:stru_18000A1F8._first, xmm0
0x1800017ce  mov     cs:stru_18000A1F8._end, rax
0x1800017d5  mov     cs:byte_18000A210, 1
0x1800017dc  mov     al, 1
0x1800017de  add     rsp, 20h
0x1800017e2  pop     rbx
0x1800017e3  retn
0x1800017e4  mov     ecx, 5
0x1800017e9  call    __scrt_fastfail
```
