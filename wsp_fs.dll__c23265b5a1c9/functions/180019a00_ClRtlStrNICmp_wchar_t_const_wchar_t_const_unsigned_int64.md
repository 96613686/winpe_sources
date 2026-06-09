# ClRtlStrNICmp(wchar_t const *,wchar_t const *,unsigned __int64)

- ea: `0x180019a00`
- end: `0x180019a55`
- name: `?ClRtlStrNICmp@@YAHPEB_W0_K@Z`
- size: `85`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, PCNZWCH lpString2, unsigned __int64 cchCount2)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180052b44`

## callees

- `0x180019a00`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180019a40`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180019a40`

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
0x180019a00  sub     rsp, 38h
0x180019a04  xor     r9d, r9d
0x180019a07  mov     eax, r9d
0x180019a0a  cmp     rax, r8
0x180019a0d  jnb     short loc_180019A26
0x180019a0f  cmp     [rcx+rax*2], r9w
0x180019a14  jz      short loc_180019A22
0x180019a16  cmp     [rdx+rax*2], r9w
0x180019a1b  jz      short loc_180019A22
0x180019a1d  inc     rax
0x180019a20  jmp     short loc_180019A0A
0x180019a22  lea     r8, [rax+1]
0x180019a26  mov     [rsp+38h+cchCount2], r8d; cchCount2
0x180019a2b  mov     r9d, r8d; cchCount1
0x180019a2e  mov     [rsp+38h+lpString2], rdx; lpString2
0x180019a33  mov     r8, rcx; lpString1
0x180019a36  mov     edx, 1; dwCmpFlags
0x180019a3b  mov     ecx, 400h; Locale
0x180019a40  call    cs:__imp_CompareStringW
0x180019a47  nop     dword ptr [rax+rax+00h]
0x180019a4c  sub     eax, 2
0x180019a4f  add     rsp, 38h
0x180019a53  retn
```
