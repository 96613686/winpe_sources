# __scrt_initialize_onexit_tables

- ea: `0x180002c68`
- end: `0x180002cf3`
- name: `__scrt_initialize_onexit_tables`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180002b28`

## callees

- `0x180002c68`
- `0x180002e08`
- `0x180003158`
- `0x1800031d6`

## pseudocode

```c
char __fastcall _scrt_initialize_onexit_tables(unsigned int a1)
{
  if ( !byte_1800070F0 )
  {
    if ( a1 > 1 )
      _scrt_fastfail(5);
    if ( !_scrt_is_ucrt_dll_in_use() || a1 )
    {
      *(__m128i *)&Table._first = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
      Table._end = (_PVFV *)-1LL;
      *(_OWORD *)&stru_1800070D8._first = *(_OWORD *)&Table._first;
      stru_1800070D8._end = (_PVFV *)-1LL;
    }
    else if ( initialize_onexit_table(&Table) || initialize_onexit_table(&stru_1800070D8) )
    {
      return 0;
    }
    byte_1800070F0 = 1;
  }
  return 1;
}

```

## disassembly

```asm
0x180002c68  push    rbx
0x180002c6a  sub     rsp, 20h
0x180002c6e  cmp     cs:byte_1800070F0, 0
0x180002c75  mov     ebx, ecx
0x180002c77  jnz     short loc_180002CE0
0x180002c79  cmp     ecx, 1
0x180002c7c  ja      short loc_180002CE8
0x180002c7e  call    __scrt_is_ucrt_dll_in_use
0x180002c83  test    eax, eax
0x180002c85  jz      short loc_180002CAF
0x180002c87  test    ebx, ebx
0x180002c89  jnz     short loc_180002CAF
0x180002c8b  lea     rcx, Table; Table
0x180002c92  call    _initialize_onexit_table
0x180002c97  test    eax, eax
0x180002c99  jnz     short loc_180002CAB
0x180002c9b  lea     rcx, stru_1800070D8; Table
0x180002ca2  call    _initialize_onexit_table
0x180002ca7  test    eax, eax
0x180002ca9  jz      short loc_180002CD9
0x180002cab  xor     al, al
0x180002cad  jmp     short loc_180002CE2
0x180002caf  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180002cb7  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002cbb  movdqu  xmmword ptr cs:Table._first, xmm0
0x180002cc3  mov     cs:Table._end, rax
0x180002cca  movdqu  xmmword ptr cs:stru_1800070D8._first, xmm0
0x180002cd2  mov     cs:stru_1800070D8._end, rax
0x180002cd9  mov     cs:byte_1800070F0, 1
0x180002ce0  mov     al, 1
0x180002ce2  add     rsp, 20h
0x180002ce6  pop     rbx
0x180002ce7  retn
0x180002ce8  mov     ecx, 5
0x180002ced  call    __scrt_fastfail
```
