# InitializeCookedUrl(STRU *,_HTTP_REQUEST_V2 *)

- ea: `0x180004118`
- end: `0x1800041fe`
- name: `?InitializeCookedUrl@@YAJPEAVSTRU@@PEAU_HTTP_REQUEST_V2@@@Z`
- size: `230`
- prototype: `__int64 __fastcall(struct STRU *, struct _HTTP_REQUEST_V2 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004204`

## callees

- `0x180004118`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18000413e`
- `msvcrt!_wcsnicmp` at `0x18000413e`
- `msvcrt!wcschr` at `0x180004174`
- `msvcrt!wcschr` at `0x18000418d`
- `msvcrt!wcschr` at `0x180004174`
- `msvcrt!wcschr` at `0x18000418d`

## pseudocode

```c
__int64 __fastcall InitializeCookedUrl(const wchar_t **a1, struct _HTTP_REQUEST_V2 *a2)
{
  unsigned int v4; // ebx
  const WCHAR *v5; // rcx
  USHORT v6; // ax
  wchar_t *v7; // rax
  wchar_t *v8; // rax
  __int64 v9; // rcx
  wchar_t *v10; // rdx
  __int64 v11; // rax
  USHORT v12; // ax
  __int64 v13; // rdx
  USHORT v14; // dx
  PCWSTR pHost; // rax

  if ( _wcsnicmp(a1[4], L"http://", 7u) )
    return (unsigned int)-2147024809;
  v5 = a1[4];
  a2->CookedUrl.pFullUrl = v5;
  v5 += 7;
  v6 = 2 * *((_WORD *)a1 + 24);
  a2->CookedUrl.pHost = v5;
  a2->CookedUrl.FullUrlLength = v6;
  v7 = wcschr(v5, 0x2Fu);
  a2->CookedUrl.pAbsPath = v7;
  if ( !v7 )
  {
    return (unsigned int)-2147024809;
  }
  else
  {
    v4 = 0;
    v8 = wcschr(v7, 0x3Fu);
    v9 = -1;
    a2->CookedUrl.pQueryString = v8;
    v10 = v8;
    if ( v8 )
    {
      v11 = -1;
      do
        ++v11;
      while ( v10[v11] );
      v12 = 2 * v11;
    }
    else
    {
      v12 = 0;
    }
    a2->CookedUrl.QueryStringLength = v12;
    v13 = -1;
    do
      ++v13;
    while ( a2->CookedUrl.pAbsPath[v13] );
    v14 = 2 * v13 - v12;
    pHost = a2->CookedUrl.pHost;
    a2->CookedUrl.AbsPathLength = v14;
    do
      ++v9;
    while ( pHost[v9] );
    a2->CookedUrl.HostLength = 2 * v9 - v14;
  }
  return v4;
}

```

## disassembly

```asm
0x180004118  mov     [rsp+arg_0], rbx
0x18000411d  mov     [rsp+arg_8], rsi
0x180004122  push    rdi
0x180004123  sub     rsp, 20h
0x180004127  mov     rdi, rdx
0x18000412a  mov     rbx, rcx
0x18000412d  mov     rcx, [rcx+20h]; String1
0x180004131  lea     rdx, aHttp; "http://"
0x180004138  mov     r8d, 7; MaxCount
0x18000413e  call    cs:__imp__wcsnicmp
0x180004144  xor     esi, esi
0x180004146  test    eax, eax
0x180004148  jz      short loc_180004154
0x18000414a  mov     ebx, 80070057h
0x18000414f  jmp     loc_1800041EC
0x180004154  mov     rcx, [rbx+20h]
0x180004158  mov     edx, 2Fh ; '/'; Ch
0x18000415d  mov     [rdi+48h], rcx
0x180004161  add     rcx, 0Eh; Str
0x180004165  movzx   eax, word ptr [rbx+30h]
0x180004169  add     ax, ax
0x18000416c  mov     [rdi+50h], rcx
0x180004170  mov     [rdi+40h], ax
0x180004174  call    cs:__imp_wcschr
0x18000417a  mov     [rdi+58h], rax
0x18000417e  test    rax, rax
0x180004181  jz      short loc_18000414A
0x180004183  mov     edx, 3Fh ; '?'; Ch
0x180004188  mov     rcx, rax; Str
0x18000418b  mov     ebx, esi
0x18000418d  call    cs:__imp_wcschr
0x180004193  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180004197  mov     [rdi+60h], rax
0x18000419b  mov     rdx, rax
0x18000419e  test    rax, rax
0x1800041a1  jz      short loc_1800041B4
0x1800041a3  mov     rax, rcx
0x1800041a6  inc     rax
0x1800041a9  cmp     [rdx+rax*2], si
0x1800041ad  jnz     short loc_1800041A6
0x1800041af  add     ax, ax
0x1800041b2  jmp     short loc_1800041B6
0x1800041b4  mov     eax, esi
0x1800041b6  mov     [rdi+46h], ax
0x1800041ba  mov     rdx, rcx
0x1800041bd  mov     r8, [rdi+58h]
0x1800041c1  inc     rdx
0x1800041c4  cmp     [r8+rdx*2], si
0x1800041c9  jnz     short loc_1800041C1
0x1800041cb  add     dx, dx
0x1800041ce  sub     dx, ax
0x1800041d1  mov     rax, [rdi+50h]
0x1800041d5  mov     [rdi+44h], dx
0x1800041d9  inc     rcx
0x1800041dc  cmp     [rax+rcx*2], si
0x1800041e0  jnz     short loc_1800041D9
0x1800041e2  add     cx, cx
0x1800041e5  sub     cx, dx
0x1800041e8  mov     [rdi+42h], cx
0x1800041ec  mov     rsi, [rsp+28h+arg_8]
0x1800041f1  mov     eax, ebx
0x1800041f3  mov     rbx, [rsp+28h+arg_0]
0x1800041f8  add     rsp, 20h
0x1800041fc  pop     rdi
0x1800041fd  retn
```
