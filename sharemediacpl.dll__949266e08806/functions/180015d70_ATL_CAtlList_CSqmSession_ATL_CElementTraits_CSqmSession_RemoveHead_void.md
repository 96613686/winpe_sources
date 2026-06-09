# ATL::CAtlList<CSqmSession *,ATL::CElementTraits<CSqmSession *>>::RemoveHead(void)

- ea: `0x180015d70`
- end: `0x180015dd0`
- name: `?RemoveHead@?$CAtlList@PEAVCSqmSession@@V?$CElementTraits@PEAVCSqmSession@@@ATL@@@ATL@@QEAAPEAVCSqmSession@@XZ`
- size: `96`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800154d4`
- `0x180015dd8`

## callees

- `0x180014564`
- `0x180015cdc`
- `0x180015d70`

## pseudocode

```c
__int64 __fastcall ATL::CAtlList<CSqmSession *,ATL::CElementTraits<CSqmSession *>>::RemoveHead(__int64 **a1)
{
  __int64 *v1; // rdx
  __int64 v3; // rcx
  __int64 v4; // rbx
  bool v5; // zf

  v1 = *a1;
  if ( !*a1 )
    ATL::AtlThrowImpl(-2147467259);
  v3 = *v1;
  v4 = v1[2];
  *a1 = (__int64 *)*v1;
  if ( v3 )
    *(_QWORD *)(v3 + 8) = 0;
  else
    a1[1] = 0;
  *v1 = (__int64)a1[4];
  v5 = a1[2] == (__int64 *)1;
  a1[2] = (__int64 *)((char *)a1[2] - 1);
  a1[4] = v1;
  if ( v5 )
    ATL::CAtlList<CSqmSession *,ATL::CElementTraits<CSqmSession *>>::RemoveAll((__int64)a1);
  return v4;
}

```

## disassembly

```asm
0x180015d70  push    rbx
0x180015d72  sub     rsp, 20h
0x180015d76  mov     rdx, [rcx]
0x180015d79  mov     rax, rcx
0x180015d7c  test    rdx, rdx
0x180015d7f  jz      short loc_180015DC5
0x180015d81  mov     rcx, [rdx]
0x180015d84  mov     rbx, [rdx+10h]
0x180015d88  mov     [rax], rcx
0x180015d8b  test    rcx, rcx
0x180015d8e  jz      short loc_180015D9A
0x180015d90  mov     qword ptr [rcx+8], 0
0x180015d98  jmp     short loc_180015DA2
0x180015d9a  mov     qword ptr [rax+8], 0
0x180015da2  mov     rcx, [rax+20h]
0x180015da6  mov     [rdx], rcx
0x180015da9  sub     qword ptr [rax+10h], 1
0x180015dae  mov     [rax+20h], rdx
0x180015db2  jnz     short loc_180015DBC
0x180015db4  mov     rcx, rax
0x180015db7  call    ?RemoveAll@?$CAtlList@PEAVCSqmSession@@V?$CElementTraits@PEAVCSqmSession@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<CSqmSession *,ATL::CElementTraits<CSqmSession *>>::RemoveAll(void)
0x180015dbc  mov     rax, rbx
0x180015dbf  add     rsp, 20h
0x180015dc3  pop     rbx
0x180015dc4  retn
0x180015dc5  mov     ecx, 80004005h; int
0x180015dca  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
