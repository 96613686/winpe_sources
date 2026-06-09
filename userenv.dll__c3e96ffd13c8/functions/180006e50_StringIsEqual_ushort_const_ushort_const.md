# StringIsEqual(ushort const *,ushort const *)

- ea: `0x180006e50`
- end: `0x180006e7d`
- name: `?StringIsEqual@@YAHPEBG0@Z`
- size: `45`
- prototype: `_BOOL8 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180008798`
- `0x18000a200`
- `0x18000b2d0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180006e68`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180006e68`

## pseudocode

```c
_BOOL8 __fastcall StringIsEqual(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  return CompareStringOrdinal(a1, -1, a2, -1, 1) == 2;
}

```

## disassembly

```asm
0x180006e50  sub     rsp, 38h
0x180006e54  mov     r9d, 0FFFFFFFFh; cchCount2
0x180006e5a  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180006e62  mov     r8, rdx; lpString2
0x180006e65  mov     edx, r9d; cchCount1
0x180006e68  call    cs:__imp_CompareStringOrdinal
0x180006e6e  xor     ecx, ecx
0x180006e70  cmp     eax, 2
0x180006e73  setz    cl
0x180006e76  mov     eax, ecx
0x180006e78  add     rsp, 38h
0x180006e7c  retn
```
