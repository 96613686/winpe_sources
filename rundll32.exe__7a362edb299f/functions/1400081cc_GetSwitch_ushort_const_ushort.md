# _GetSwitch(ushort const *,ushort * *)

- ea: `0x1400081cc`
- end: `0x140008247`
- name: `?_GetSwitch@@YAHPEBGPEAPEAG@Z`
- size: `123`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, const WCHAR **)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140007da8`

## callees

- `0x1400081cc`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140008219`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140008219`

## pseudocode

```c
__int64 __fastcall _GetSwitch(PCNZWCH lpString1, const WCHAR **a2)
{
  __int64 v4; // rax
  unsigned int v5; // esi
  __int64 cchCount2; // rbx
  const WCHAR *lpString2; // rcx

  v4 = -1;
  v5 = 0;
  cchCount2 = -1;
  do
    ++cchCount2;
  while ( lpString1[cchCount2] );
  lpString2 = *a2;
  do
    ++v4;
  while ( lpString2[v4] );
  if ( (int)cchCount2 <= (int)v4 && CompareStringW(0x7Fu, 1u, lpString1, cchCount2, lpString2, cchCount2) == 2 )
  {
    v5 = 1;
    *a2 += (int)cchCount2 - 1;
  }
  return v5;
}

```

## disassembly

```asm
0x1400081cc  mov     [rsp+arg_0], rbx
0x1400081d1  mov     [rsp+arg_8], rsi
0x1400081d6  push    rdi
0x1400081d7  sub     rsp, 30h
0x1400081db  mov     rdi, rdx
0x1400081de  mov     r8, rcx; lpString1
0x1400081e1  xor     edx, edx
0x1400081e3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400081e7  mov     esi, edx
0x1400081e9  mov     rbx, rax
0x1400081ec  inc     rbx
0x1400081ef  cmp     [rcx+rbx*2], dx
0x1400081f3  jnz     short loc_1400081EC
0x1400081f5  mov     rcx, [rdi]
0x1400081f8  inc     rax
0x1400081fb  cmp     [rcx+rax*2], dx
0x1400081ff  jnz     short loc_1400081F8
0x140008201  cmp     ebx, eax
0x140008203  jg      short loc_140008235
0x140008205  mov     edx, 1; dwCmpFlags
0x14000820a  mov     [rsp+38h+cchCount2], ebx; cchCount2
0x14000820e  mov     [rsp+38h+lpString2], rcx; lpString2
0x140008213  mov     r9d, ebx; cchCount1
0x140008216  lea     ecx, [rdx+7Eh]; Locale
0x140008219  call    cs:__imp_CompareStringW
0x14000821f  cmp     eax, 2
0x140008222  jnz     short loc_140008235
0x140008224  lea     eax, [rbx-1]
0x140008227  mov     esi, 1
0x14000822c  movsxd  rcx, eax
0x14000822f  add     rcx, rcx
0x140008232  add     [rdi], rcx
0x140008235  mov     rbx, [rsp+38h+arg_0]
0x14000823a  mov     eax, esi
0x14000823c  mov     rsi, [rsp+38h+arg_8]
0x140008241  add     rsp, 30h
0x140008245  pop     rdi
0x140008246  retn
```
