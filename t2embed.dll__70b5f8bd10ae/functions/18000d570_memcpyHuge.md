# memcpyHuge

- ea: `0x18000d570`
- end: `0x18000d598`
- name: `memcpyHuge`
- size: `40`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180001f60`
- `0x180002bd0`
- `0x18000bd00`
- `0x18000bde0`
- `0x18000db44`
- `0x18000e2d4`

## callees

- `0x18000d570`

## pseudocode

```c
_BYTE *__fastcall memcpyHuge(_BYTE *a1, _BYTE *a2, unsigned int a3)
{
  unsigned int v3; // r10d
  _BYTE *result; // rax

  v3 = 0;
  for ( result = a1; v3 < a3; ++a2 )
  {
    ++v3;
    *a1++ = *a2;
  }
  return result;
}

```

## disassembly

```asm
0x18000d570  xor     r10d, r10d
0x18000d573  mov     rax, rcx
0x18000d576  test    r8d, r8d
0x18000d579  jz      short locret_18000D597
0x18000d57b  nop     dword ptr [rax+rax+00h]
0x18000d580  movzx   r9d, byte ptr [rdx]
0x18000d584  inc     r10d
0x18000d587  mov     [rcx], r9b
0x18000d58a  lea     rcx, [rcx+1]
0x18000d58e  lea     rdx, [rdx+1]
0x18000d592  cmp     r10d, r8d
0x18000d595  jb      short loc_18000D580
0x18000d597  retn
```
