# ATL::CAtlList<CSqmSession *,ATL::CElementTraits<CSqmSession *>>::RemoveAll(void)

- ea: `0x180015cdc`
- end: `0x180015d6a`
- name: `?RemoveAll@?$CAtlList@PEAVCSqmSession@@V?$CElementTraits@PEAVCSqmSession@@@ATL@@@ATL@@QEAAXXZ`
- size: `142`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800153ac`
- `0x180015cdc`
- `0x180015d70`

## callees

- `0x180014564`
- `0x180015cdc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180015d42`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180015d42`

## pseudocode

```c
void __fastcall ATL::CAtlList<CSqmSession *,ATL::CElementTraits<CSqmSession *>>::RemoveAll(__int64 a1)
{
  _QWORD *v2; // rcx
  bool v3; // zf
  _QWORD *v4; // rcx
  _QWORD *v5; // rbx

  while ( *(_QWORD *)(a1 + 16) )
  {
    v2 = *(_QWORD **)a1;
    if ( !*(_QWORD *)a1 )
      ATL::AtlThrowImpl(-2147467259);
    *(_QWORD *)a1 = *v2;
    *v2 = *(_QWORD *)(a1 + 32);
    v3 = (*(_QWORD *)(a1 + 16))-- == 1;
    *(_QWORD *)(a1 + 32) = v2;
    if ( v3 )
      ATL::CAtlList<CSqmSession *,ATL::CElementTraits<CSqmSession *>>::RemoveAll(a1);
  }
  v4 = *(_QWORD **)(a1 + 24);
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  if ( v4 )
  {
    do
    {
      v5 = (_QWORD *)*v4;
      free(v4);
      v4 = v5;
    }
    while ( v5 );
    *(_QWORD *)(a1 + 24) = 0;
  }
}

```

## disassembly

```asm
0x180015cdc  mov     [rsp+arg_8], rbx
0x180015ce1  push    rdi
0x180015ce2  sub     rsp, 20h
0x180015ce6  cmp     qword ptr [rcx+10h], 0
0x180015ceb  mov     rdi, rcx
0x180015cee  jbe     short loc_180015D1F
0x180015cf0  mov     rcx, [rdi]
0x180015cf3  test    rcx, rcx
0x180015cf6  jz      short loc_180015D5F
0x180015cf8  mov     rax, [rcx]
0x180015cfb  mov     [rdi], rax
0x180015cfe  mov     rax, [rdi+20h]
0x180015d02  mov     [rcx], rax
0x180015d05  sub     qword ptr [rdi+10h], 1
0x180015d0a  mov     [rdi+20h], rcx
0x180015d0e  jnz     short loc_180015D18
0x180015d10  mov     rcx, rdi
0x180015d13  call    ?RemoveAll@?$CAtlList@PEAVCSqmSession@@V?$CElementTraits@PEAVCSqmSession@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<CSqmSession *,ATL::CElementTraits<CSqmSession *>>::RemoveAll(void)
0x180015d18  cmp     qword ptr [rdi+10h], 0
0x180015d1d  ja      short loc_180015CF0
0x180015d1f  mov     rcx, [rdi+18h]; Block
0x180015d23  mov     qword ptr [rdi], 0
0x180015d2a  mov     qword ptr [rdi+8], 0
0x180015d32  mov     qword ptr [rdi+20h], 0
0x180015d3a  test    rcx, rcx
0x180015d3d  jz      short loc_180015D54
0x180015d3f  mov     rbx, [rcx]
0x180015d42  call    cs:__imp_free
0x180015d48  mov     rcx, rbx
0x180015d4b  test    rbx, rbx
0x180015d4e  jnz     short loc_180015D3F
0x180015d50  mov     [rdi+18h], rbx
0x180015d54  mov     rbx, [rsp+28h+arg_8]
0x180015d59  add     rsp, 20h
0x180015d5d  pop     rdi
0x180015d5e  retn
0x180015d5f  mov     ecx, 80004005h; int
0x180015d64  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
