# CCabDecompressor::CSusSortedArrayListItemOpsLPCSTRNoDelete::Compare(char const * const &,char const * const &)

- ea: `0x180016060`
- end: `0x1800160b8`
- name: `?Compare@CSusSortedArrayListItemOpsLPCSTRNoDelete@CCabDecompressor@@SAHAEBQEBD0@Z`
- size: `88`
- prototype: `__int64 __fastcall(const char *const *, const char *const *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180015098`
- `0x1800160c0`
- `0x18001634c`

## callees

- `0x180016060`

## import_xrefs

- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180016087`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180016087`

## pseudocode

```c
__int64 __fastcall CCabDecompressor::CSusSortedArrayListItemOpsLPCSTRNoDelete::Compare(PCNZCH *a1, PCNZCH *a2)
{
  int v2; // eax

  if ( *a1 == *a2 )
    return 0;
  v2 = CompareStringA(0x7Fu, 1u, *a1, -1, *a2, -1);
  switch ( v2 )
  {
    case 1:
      return 0xFFFFFFFFLL;
    case 2:
      return 0;
    case 3:
      return 1;
  }
  return 4294967294LL;
}

```

## disassembly

```asm
0x180016060  sub     rsp, 38h
0x180016064  mov     rax, [rdx]
0x180016067  cmp     [rcx], rax
0x18001606a  jz      short loc_1800160B1
0x18001606c  mov     r8, [rcx]; lpString1
0x18001606f  or      r9d, 0FFFFFFFFh; cchCount1
0x180016073  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x18001607b  mov     [rsp+38h+lpString2], rax; lpString2
0x180016080  lea     edx, [r9+2]; dwCmpFlags
0x180016084  lea     ecx, [rdx+7Eh]; Locale
0x180016087  call    cs:__imp_CompareStringA
0x18001608d  mov     ecx, eax
0x18001608f  sub     ecx, 1
0x180016092  jz      short loc_1800160AC
0x180016094  sub     ecx, 1
0x180016097  jz      short loc_1800160B1
0x180016099  cmp     ecx, 1
0x18001609c  jz      short loc_1800160A5
0x18001609e  mov     eax, 0FFFFFFFEh
0x1800160a3  jmp     short loc_1800160B3
0x1800160a5  mov     eax, 1
0x1800160aa  jmp     short loc_1800160B3
0x1800160ac  or      eax, 0FFFFFFFFh
0x1800160af  jmp     short loc_1800160B3
0x1800160b1  xor     eax, eax
0x1800160b3  add     rsp, 38h
0x1800160b7  retn
```
