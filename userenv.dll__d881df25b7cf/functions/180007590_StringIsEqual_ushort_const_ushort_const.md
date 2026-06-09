# StringIsEqual(ushort const *,ushort const *)

- ea: `0x180007590`
- end: `0x1800075c4`
- name: `?StringIsEqual@@YAHPEBG0@Z`
- size: `52`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800070c8`
- `0x180008fe4`
- `0x18000ab88`
- `0x18000bd3c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800075a8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800075a8`

## pseudocode

```c
_BOOL8 __fastcall StringIsEqual(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  return CompareStringOrdinal(a1, -1, a2, -1, 1) == 2;
}

```

## disassembly

```asm
0x180007590  sub     rsp, 38h
0x180007594  mov     r9d, 0FFFFFFFFh; cchCount2
0x18000759a  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x1800075a2  mov     r8, rdx; lpString2
0x1800075a5  mov     edx, r9d; cchCount1
0x1800075a8  call    cs:__imp_CompareStringOrdinal
0x1800075af  nop     dword ptr [rax+rax+00h]
0x1800075b4  xor     ecx, ecx
0x1800075b6  cmp     eax, 2
0x1800075b9  setz    cl
0x1800075bc  mov     eax, ecx
0x1800075be  add     rsp, 38h
0x1800075c2  retn
```
