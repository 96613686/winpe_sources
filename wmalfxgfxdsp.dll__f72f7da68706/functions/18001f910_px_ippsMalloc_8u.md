# px_ippsMalloc_8u

- ea: `0x18001f910`
- end: `0x18001f939`
- name: `px_ippsMalloc_8u`
- size: `41`
- prototype: ``
- caller_count: `54`
- callee_count: `2`
- tags: ``

## callers

- `0x180018990`
- `0x180018af0`
- `0x180018ccc`
- `0x180019020`
- `0x180019110`
- `0x1800194e0`
- `0x1800196c0`
- `0x18001981c`
- `0x180019b10`
- `0x180019cb0`
- `0x180019eb0`
- `0x18001a220`
- `0x18001a310`
- `0x18001a6e0`
- `0x18001a900`
- `0x18001aa94`
- `0x18001adb0`
- `0x18001af50`
- `0x18001b150`
- `0x18001b4c0`
- `0x18001b5b0`
- `0x18001b980`
- `0x18001bba0`
- `0x18001bd34`
- `0x18001c560`
- `0x18001c700`
- `0x18001c9d0`
- `0x18001cbe0`
- `0x18001ce80`
- `0x18001d170`
- `0x18001d3d0`
- `0x18001d570`
- `0x18001d830`
- `0x18001da40`
- `0x18001dce0`
- `0x18001dfd0`
- `0x18001e160`
- `0x18001e300`
- `0x18001e5c0`
- `0x18001e7d0`
- `0x18001ea70`
- `0x18001ed60`
- `0x180050900`
- `0x180050b60`
- `0x1800556c4`
- `0x1800590f8`
- `0x180059188`
- `0x180059558`
- `0x180059a60`
- `0x18005b08c`

## callees

- `0x1800150c4`
- `0x18001f910`

## pseudocode

```c
_QWORD *__fastcall px_ippsMalloc_8u(int a1)
{
  _QWORD *result; // rax
  _QWORD *v2; // rcx

  result = operator new(a1 + 40LL);
  v2 = result;
  if ( result )
  {
    result = (_QWORD *)(((unsigned __int64)result + 39) & 0xFFFFFFFFFFFFFFE0uLL);
    *(result - 1) = v2;
  }
  return result;
}

```

## disassembly

```asm
0x18001f910  sub     rsp, 28h
0x18001f914  movsxd  rcx, ecx
0x18001f917  add     rcx, 28h ; '('; Size
0x18001f91b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f920  mov     rcx, rax
0x18001f923  test    rax, rax
0x18001f926  jz      short loc_18001F934
0x18001f928  add     rax, 27h ; '''
0x18001f92c  and     rax, 0FFFFFFFFFFFFFFE0h
0x18001f930  mov     [rax-8], rcx
0x18001f934  add     rsp, 28h
0x18001f938  retn
```
