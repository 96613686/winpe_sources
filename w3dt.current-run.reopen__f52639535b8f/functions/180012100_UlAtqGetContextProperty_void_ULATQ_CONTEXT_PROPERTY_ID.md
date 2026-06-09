# UlAtqGetContextProperty(void *,ULATQ_CONTEXT_PROPERTY_ID)

- ea: `0x180012100`
- end: `0x18001216f`
- name: `?UlAtqGetContextProperty@@YAPEAXPEAXW4ULATQ_CONTEXT_PROPERTY_ID@@@Z`
- size: `111`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180012100`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180012136`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180012136`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180012167`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180012167`
- `iisutil!?QueryOutstandingAllocationCount@ALLOC_CACHE_HANDLER@@QEBAKXZ` at `0x18001214a`
- `iisutil!?QueryOutstandingAllocationCount@ALLOC_CACHE_HANDLER@@QEBAKXZ` at `0x18001214a`

## pseudocode

```c
unsigned __int16 *__fastcall UlAtqGetContextProperty(__int64 a1, int a2)
{
  int v3; // edx
  int v4; // edx
  ALLOC_CACHE_HANDLER *v5; // rcx

  if ( a2 == 1 )
    return *(unsigned __int16 **)(a1 + 2944);
  v3 = a2 - 2;
  if ( !v3 )
    return (unsigned __int16 *)STRU::QueryStr(g_pwpContext);
  v4 = v3 - 1;
  if ( v4 )
  {
    if ( v4 == 1 )
      return STRU::QueryStr((WP_CONTEXT *)((char *)g_pwpContext + 184));
    else
      return 0;
  }
  else
  {
    v5 = UL_NATIVE_REQUEST::sm_pachNativeRequests;
    if ( UL_NATIVE_REQUEST::sm_pachNativeRequests )
      return (unsigned __int16 *)(ALLOC_CACHE_HANDLER::QueryOutstandingAllocationCount(UL_NATIVE_REQUEST::sm_pachNativeRequests) != UL_NATIVE_REQUEST::sm_cRequestsPending);
    return (unsigned __int16 *)v5;
  }
}

```

## disassembly

```asm
0x180012100  sub     rsp, 28h
0x180012104  cmp     edx, 1
0x180012107  jnz     short loc_180012115
0x180012109  mov     rax, [rcx+0B80h]
0x180012110  add     rsp, 28h
0x180012114  retn
0x180012115  sub     edx, 2
0x180012118  jz      short loc_180012160
0x18001211a  sub     edx, 1
0x18001211d  jz      short loc_18001213E
0x18001211f  cmp     edx, 1
0x180012122  jz      short loc_180012128
0x180012124  xor     eax, eax
0x180012126  jmp     short loc_180012110
0x180012128  mov     rcx, cs:?g_pwpContext@@3PEAVWP_CONTEXT@@EA; WP_CONTEXT * g_pwpContext
0x18001212f  add     rcx, 0B8h
0x180012136  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001213c  jmp     short loc_180012110
0x18001213e  mov     rcx, cs:?sm_pachNativeRequests@UL_NATIVE_REQUEST@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * UL_NATIVE_REQUEST::sm_pachNativeRequests
0x180012145  test    rcx, rcx
0x180012148  jz      short loc_18001215B
0x18001214a  call    cs:__imp_?QueryOutstandingAllocationCount@ALLOC_CACHE_HANDLER@@QEBAKXZ; ALLOC_CACHE_HANDLER::QueryOutstandingAllocationCount(void)
0x180012150  xor     ecx, ecx
0x180012152  cmp     eax, cs:?sm_cRequestsPending@UL_NATIVE_REQUEST@@0KA; ulong UL_NATIVE_REQUEST::sm_cRequestsPending
0x180012158  setnz   cl
0x18001215b  mov     rax, rcx
0x18001215e  jmp     short loc_180012110
0x180012160  mov     rcx, cs:?g_pwpContext@@3PEAVWP_CONTEXT@@EA; WP_CONTEXT * g_pwpContext
0x180012167  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18001216d  jmp     short loc_180012110
```
