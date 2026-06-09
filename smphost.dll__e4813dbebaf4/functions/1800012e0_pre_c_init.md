# pre_c_init

- ea: `0x1800012e0`
- end: `0x180001317`
- name: `pre_c_init`
- size: `55`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800012e0`

## import_xrefs

- `msvcrt!malloc` at `0x1800012e9`
- `msvcrt!malloc` at `0x1800012e9`

## pseudocode

```c
__int64 pre_c_init()
{
  _QWORD *v0; // rax

  v0 = malloc(0x100u);
  _onexitbegin = v0;
  _onexitend = (__int64)v0;
  if ( !v0 )
    return 1;
  *v0 = 0;
  return 0;
}

```

## disassembly

```asm
0x1800012e0  sub     rsp, 28h
0x1800012e4  mov     ecx, 100h; Size
0x1800012e9  call    cs:__imp_malloc
0x1800012ef  mov     cs:__onexitbegin, rax
0x1800012f6  mov     cs:__onexitend, rax
0x1800012fd  test    rax, rax
0x180001300  jnz     short loc_180001309
0x180001302  mov     eax, 1
0x180001307  jmp     short loc_180001312
0x180001309  mov     qword ptr [rax], 0
0x180001310  xor     eax, eax
0x180001312  add     rsp, 28h
0x180001316  retn
```
