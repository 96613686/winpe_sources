# CStringMap::find(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)

- ea: `0x140019d3c`
- end: `0x140019e35`
- name: `?find@CStringMap@@QEAA?AV?$_DlistIt@U?$_DlistNode@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@utl@@@utl@@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@2@@utl@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@3@@Z`
- size: `249`
- prototype: `void ***__fastcall(__int64, void ***, __int64 *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140018b6c`
- `0x1400190d0`
- `0x140019238`

## callees

- `0x140019d3c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140019daa`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140019e0f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140019daa`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140019e0f`

## pseudocode

```c
void ***__fastcall CStringMap::find(__int64 a1, void ***a2, __int64 *a3)
{
  void ***v3; // rbx
  void **v5; // rbp
  void **v6; // rdi
  void ***v7; // rsi
  __int64 v8; // r13
  __int64 v9; // r15
  __int64 v10; // r12
  unsigned __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rcx
  __int64 v14; // rax
  unsigned __int64 v15; // r9
  __int64 v16; // r8

  v3 = (void ***)(a1 + 24);
  v5 = (void **)a1;
  if ( *(_QWORD *)(a1 + 40) != a1 + 24 )
  {
    v6 = *v3;
    v7 = (void ***)(a1 + 24);
    v8 = *a3;
    v9 = 2;
    v10 = a3[1];
    do
    {
      v11 = (unsigned __int64)v6[4];
      if ( (v10 | v11) > 0x7FFFFFFF )
        __int2c();
      v12 = 2;
      v13 = 2;
      if ( v8 )
        v12 = v8;
      if ( v6[3] )
        v13 = (__int64)v6[3];
      if ( CompareStringOrdinal((LPCWCH)v13, v11, (LPCWCH)v12, v10, 1) == 1 )
      {
        v14 = 2;
      }
      else
      {
        v7 = (void ***)v6;
        v14 = 1;
      }
      v6 = (void **)v6[v14];
    }
    while ( v6 != &utl::_TreeSentinel );
    if ( v7 != v3 )
    {
      v15 = (unsigned __int64)v7[4];
      if ( (v10 | v15) > 0x7FFFFFFF )
        __int2c();
      v16 = 2;
      if ( v7[3] )
        v16 = (__int64)v7[3];
      if ( v8 )
        v9 = v8;
      if ( CompareStringOrdinal((LPCWCH)v9, v10, (LPCWCH)v16, v15, 1) != 1 )
        v5 = v7[5];
    }
  }
  *a2 = v5;
  return a2;
}

```

## disassembly

```asm
0x140019d3c  push    rbx
0x140019d3e  push    rbp
0x140019d3f  push    rsi
0x140019d40  push    rdi
0x140019d41  push    r12
0x140019d43  push    r13
0x140019d45  push    r14
0x140019d47  push    r15
0x140019d49  sub     rsp, 38h
0x140019d4d  lea     rbx, [rcx+18h]
0x140019d51  mov     r14, rdx
0x140019d54  mov     rbp, rcx
0x140019d57  cmp     [rbx+10h], rbx
0x140019d5b  jz      loc_140019E1E
0x140019d61  mov     rdi, [rbx]
0x140019d64  mov     rsi, rbx
0x140019d67  mov     r13, [r8]
0x140019d6a  mov     r15d, 2
0x140019d70  mov     r12, [r8+8]
0x140019d74  mov     rdx, [rdi+20h]; cchCount1
0x140019d78  mov     rax, rdx
0x140019d7b  or      rax, r12
0x140019d7e  cmp     rax, 7FFFFFFFh
0x140019d84  jbe     short loc_140019D88
0x140019d86  int     2Ch; Windows NT - assertion failure
0x140019d88  test    r13, r13
0x140019d8b  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x140019d93  mov     r8, r15
0x140019d96  mov     rcx, r15
0x140019d99  cmovnz  r8, r13; lpString2
0x140019d9d  mov     r9d, r12d; cchCount2
0x140019da0  cmp     qword ptr [rdi+18h], 0
0x140019da5  cmovnz  rcx, [rdi+18h]; lpString1
0x140019daa  call    cs:__imp_CompareStringOrdinal
0x140019db0  cmp     eax, 1
0x140019db3  jnz     short loc_140019DBC
0x140019db5  mov     eax, 10h
0x140019dba  jmp     short loc_140019DC4
0x140019dbc  mov     rsi, rdi
0x140019dbf  mov     eax, 8
0x140019dc4  mov     rdi, [rax+rdi]
0x140019dc8  lea     rax, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x140019dcf  cmp     rdi, rax
0x140019dd2  jnz     short loc_140019D74
0x140019dd4  cmp     rsi, rbx
0x140019dd7  jz      short loc_140019E1E
0x140019dd9  mov     r9, [rsi+20h]; cchCount2
0x140019ddd  mov     rax, r9
0x140019de0  or      rax, r12
0x140019de3  cmp     rax, 7FFFFFFFh
0x140019de9  jbe     short loc_140019DED
0x140019deb  int     2Ch; Windows NT - assertion failure
0x140019ded  cmp     qword ptr [rsi+18h], 0
0x140019df2  mov     r8, r15
0x140019df5  mov     edx, r12d; cchCount1
0x140019df8  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x140019e00  cmovnz  r8, [rsi+18h]; lpString2
0x140019e05  test    r13, r13
0x140019e08  cmovnz  r15, r13
0x140019e0c  mov     rcx, r15; lpString1
0x140019e0f  call    cs:__imp_CompareStringOrdinal
0x140019e15  cmp     eax, 1
0x140019e18  jz      short loc_140019E1E
0x140019e1a  mov     rbp, [rsi+28h]
0x140019e1e  mov     [r14], rbp
0x140019e21  mov     rax, r14
0x140019e24  add     rsp, 38h
0x140019e28  pop     r15
0x140019e2a  pop     r14
0x140019e2c  pop     r13
0x140019e2e  pop     r12
0x140019e30  pop     rdi
0x140019e31  pop     rsi
0x140019e32  pop     rbp
0x140019e33  pop     rbx
0x140019e34  retn
```
