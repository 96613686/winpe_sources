# UbpmUtilsSearchMultiString(ushort const *,ushort const *)

- ea: `0x180013180`
- end: `0x18001323d`
- name: `?UbpmUtilsSearchMultiString@@YAEPEBG0@Z`
- size: `189`
- prototype: `unsigned __int8 __fastcall(PCNZWCH lpString2, PCNZWCH lpString1)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001764`
- `0x180008030`
- `0x18000c3d4`
- `0x180013b60`
- `0x18002cc50`

## callees

- `0x180013180`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800131f9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013230`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800131f9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013230`

## pseudocode

```c
unsigned __int8 __fastcall UbpmUtilsSearchMultiString(PCNZWCH lpString2, PCNZWCH lpString1)
{
  const WCHAR *v2; // rdi
  __int64 cchCount2; // rsi
  __int64 v5; // rbx
  __int64 v6; // r9

  v2 = lpString1;
  if ( lpString1 && lpString2 )
  {
    cchCount2 = -1;
    do
      ++cchCount2;
    while ( lpString2[cchCount2] );
    while ( *v2 )
    {
      v5 = -1;
      do
        ++v5;
      while ( v2[v5] );
      if ( (unsigned int)cchCount2 >= (unsigned int)v5 )
      {
        v6 = (unsigned int)(v5 - 1);
        if ( v2[v6] == 42 )
        {
          if ( CompareStringW(0x7Fu, 1u, v2, v6, lpString2, v5 - 1) == 2 )
            return 1;
        }
        else if ( (_DWORD)cchCount2 == (_DWORD)v5 && CompareStringW(0x7Fu, 1u, v2, v5, lpString2, cchCount2) == 2 )
        {
          return 1;
        }
      }
      v2 += (unsigned int)(v5 + 1);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180013180  push    rbx
0x180013182  push    rbp
0x180013183  push    rsi
0x180013184  push    rdi
0x180013185  sub     rsp, 38h
0x180013189  mov     rdi, rdx
0x18001318c  mov     rbp, rcx
0x18001318f  test    rdx, rdx
0x180013192  jz      short loc_18001320F
0x180013194  test    rcx, rcx
0x180013197  jz      short loc_18001320F
0x180013199  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1800131a0  inc     rsi
0x1800131a3  cmp     word ptr [rcx+rsi*2], 0
0x1800131a8  jnz     short loc_1800131A0
0x1800131aa  nop     word ptr [rax+rax+00h]
0x1800131b0  cmp     word ptr [rdi], 0
0x1800131b4  jz      short loc_18001320F
0x1800131b6  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800131bd  nop     dword ptr [rax]
0x1800131c0  inc     rbx
0x1800131c3  cmp     word ptr [rdi+rbx*2], 0
0x1800131c8  jnz     short loc_1800131C0
0x1800131ca  cmp     esi, ebx
0x1800131cc  jnb     short loc_1800131D6
0x1800131ce  inc     ebx
0x1800131d0  lea     rdi, [rdi+rbx*2]
0x1800131d4  jmp     short loc_1800131B0
0x1800131d6  lea     r9d, [rbx-1]; cchCount1
0x1800131da  cmp     word ptr [rdi+r9*2], 2Ah ; '*'
0x1800131e0  jnz     short loc_180013213
0x1800131e2  mov     [rsp+58h+cchCount2], r9d; cchCount2
0x1800131e7  mov     r8, rdi; lpString1
0x1800131ea  mov     edx, 1; dwCmpFlags
0x1800131ef  mov     [rsp+58h+lpString2], rbp; lpString2
0x1800131f4  mov     ecx, 7Fh; Locale
0x1800131f9  call    cs:__imp_CompareStringW
0x1800131ff  cmp     eax, 2
0x180013202  jnz     short loc_1800131CE
0x180013204  mov     al, 1
0x180013206  add     rsp, 38h
0x18001320a  pop     rdi
0x18001320b  pop     rsi
0x18001320c  pop     rbp
0x18001320d  pop     rbx
0x18001320e  retn
0x18001320f  xor     al, al
0x180013211  jmp     short loc_180013206
0x180013213  cmp     esi, ebx
0x180013215  jnz     short loc_1800131CE
0x180013217  mov     [rsp+58h+cchCount2], esi; cchCount2
0x18001321b  mov     r9d, ebx; cchCount1
0x18001321e  mov     r8, rdi; lpString1
0x180013221  mov     [rsp+58h+lpString2], rbp; lpString2
0x180013226  mov     edx, 1; dwCmpFlags
0x18001322b  mov     ecx, 7Fh; Locale
0x180013230  call    cs:__imp_CompareStringW
0x180013236  cmp     eax, 2
0x180013239  jnz     short loc_1800131CE
0x18001323b  jmp     short loc_180013204
```
