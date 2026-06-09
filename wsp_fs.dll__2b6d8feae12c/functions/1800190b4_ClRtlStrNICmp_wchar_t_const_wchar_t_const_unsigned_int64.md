# ClRtlStrNICmp(wchar_t const *,wchar_t const *,unsigned __int64)

- ea: `0x1800190b4`
- end: `0x180019102`
- name: `?ClRtlStrNICmp@@YAHPEB_W0_K@Z`
- size: `78`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, PCNZWCH lpString2, unsigned __int64 cchCount2)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180051b64`

## callees

- `0x1800190b4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800190f4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800190f4`

## pseudocode

```c
__int64 __fastcall ClRtlStrNICmp(PCNZWCH lpString1, PCNZWCH lpString2, unsigned __int64 cchCount2)
{
  unsigned __int64 i; // rax

  for ( i = 0; i < cchCount2; ++i )
  {
    if ( !lpString1[i] || !lpString2[i] )
    {
      LODWORD(cchCount2) = i + 1;
      return (unsigned int)(CompareStringW(0x400u, 1u, lpString1, cchCount2, lpString2, cchCount2) - 2);
    }
  }
  return (unsigned int)(CompareStringW(0x400u, 1u, lpString1, cchCount2, lpString2, cchCount2) - 2);
}

```

## disassembly

```asm
0x1800190b4  sub     rsp, 38h
0x1800190b8  xor     r9d, r9d
0x1800190bb  mov     eax, r9d
0x1800190be  cmp     rax, r8
0x1800190c1  jnb     short loc_1800190DA
0x1800190c3  cmp     [rcx+rax*2], r9w
0x1800190c8  jz      short loc_1800190D6
0x1800190ca  cmp     [rdx+rax*2], r9w
0x1800190cf  jz      short loc_1800190D6
0x1800190d1  inc     rax
0x1800190d4  jmp     short loc_1800190BE
0x1800190d6  lea     r8, [rax+1]
0x1800190da  mov     [rsp+38h+cchCount2], r8d; cchCount2
0x1800190df  mov     r9d, r8d; cchCount1
0x1800190e2  mov     [rsp+38h+lpString2], rdx; lpString2
0x1800190e7  mov     r8, rcx; lpString1
0x1800190ea  mov     edx, 1; dwCmpFlags
0x1800190ef  mov     ecx, 400h; Locale
0x1800190f4  call    cs:__imp_CompareStringW
0x1800190fa  sub     eax, 2
0x1800190fd  add     rsp, 38h
0x180019101  retn
```
