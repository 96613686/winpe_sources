# __uncaught_exceptions

- ea: `0x1800147a8`
- end: `0x1800147c3`
- name: `__uncaught_exceptions`
- size: `27`
- prototype: `__int64()`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180008f78`
- `0x180009320`
- `0x180009534`
- `0x18000960c`
- `0x1800096f4`

## callees

- `0x18001208c`
- `0x1800147a8`

## pseudocode

```c
__int64 _uncaught_exceptions()
{
  __int64 v0; // rcx
  __int64 result; // rax

  v0 = _vcrt_getptd_noinit();
  result = 0;
  if ( v0 )
    return *(unsigned int *)(v0 + 48);
  return result;
}

```

## disassembly

```asm
0x1800147a8  sub     rsp, 28h
0x1800147ac  call    __vcrt_getptd_noinit
0x1800147b1  mov     rcx, rax
0x1800147b4  xor     eax, eax
0x1800147b6  test    rcx, rcx
0x1800147b9  jz      short loc_1800147BE
0x1800147bb  mov     eax, [rcx+30h]
0x1800147be  add     rsp, 28h
0x1800147c2  retn
```
