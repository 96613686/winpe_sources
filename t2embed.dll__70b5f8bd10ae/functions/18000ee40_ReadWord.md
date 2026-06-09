# ReadWord

- ea: `0x18000ee40`
- end: `0x18000ee77`
- name: `ReadWord`
- size: `55`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f298`
- `0x1800110d0`
- `0x1800121e4`
- `0x1800132ac`
- `0x18001400c`
- `0x1800156e8`
- `0x18001cb94`
- `0x18001ce6c`
- `0x180029228`
- `0x1800297f8`
- `0x180029ea4`

## callees

- `0x18000ee40`

## pseudocode

```c
__int64 __fastcall ReadWord(__int64 a1, _WORD *a2, unsigned int a3)
{
  __int64 result; // rax

  if ( !*(_QWORD *)a1 || a3 + 2 < a3 || a3 + 2 > *(_DWORD *)(a1 + 8) )
    return 1001;
  result = 0;
  *a2 = _byteswap_ushort(*(_WORD *)(a3 + *(_QWORD *)a1));
  return result;
}

```

## disassembly

```asm
0x18000ee40  mov     r9, [rcx]
0x18000ee43  test    r9, r9
0x18000ee46  jz      short loc_18000EE56
0x18000ee48  lea     eax, [r8+2]
0x18000ee4c  cmp     eax, r8d
0x18000ee4f  jb      short loc_18000EE56
0x18000ee51  cmp     eax, [rcx+8]
0x18000ee54  jbe     short loc_18000EE5C
0x18000ee56  mov     eax, 3E9h
0x18000ee5b  retn
0x18000ee5c  mov     eax, r8d
0x18000ee5f  movzx   ecx, byte ptr [rax+r9]
0x18000ee64  movzx   eax, byte ptr [rax+r9+1]
0x18000ee6a  shl     cx, 8
0x18000ee6e  or      cx, ax
0x18000ee71  xor     eax, eax
0x18000ee73  mov     [rdx], cx
0x18000ee76  retn
```
