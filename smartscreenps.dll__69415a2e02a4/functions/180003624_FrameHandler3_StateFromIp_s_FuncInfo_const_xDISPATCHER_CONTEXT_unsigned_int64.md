# __FrameHandler3::StateFromIp(_s_FuncInfo const *,_xDISPATCHER_CONTEXT *,unsigned __int64)

- ea: `0x180003624`
- end: `0x18000367f`
- name: `?StateFromIp@__FrameHandler3@@SAHPEBU_s_FuncInfo@@PEAU_xDISPATCHER_CONTEXT@@_K@Z`
- size: `91`
- prototype: `__int64 __fastcall(const struct _s_FuncInfo *, struct _xDISPATCHER_CONTEXT *, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000353c`
- `0x180003604`
- `0x180004f94`

## callees

- `0x180003624`
- `0x18000693e`

## pseudocode

```c
__int64 __fastcall __FrameHandler3::StateFromIp(
        const struct _s_FuncInfo *a1,
        struct _xDISPATCHER_CONTEXT *a2,
        unsigned __int64 a3)
{
  __int64 dispIPtoStateMap; // r11
  __int64 ImageBase; // r9
  unsigned int nIPMapEntries; // r10d
  __int64 v6; // rdx

  if ( !a1 || (dispIPtoStateMap = a1->dispIPtoStateMap, ImageBase = a2->ImageBase, !(ImageBase + dispIPtoStateMap)) )
    abort_0();
  nIPMapEntries = a1->nIPMapEntries;
  if ( !nIPMapEntries )
    return 0xFFFFFFFFLL;
  v6 = 0;
  do
  {
    if ( a3 < ImageBase + *(int *)(ImageBase + dispIPtoStateMap + 8 * v6) )
      break;
    v6 = (unsigned int)(v6 + 1);
  }
  while ( (unsigned int)v6 < nIPMapEntries );
  if ( (_DWORD)v6 )
    return *(unsigned int *)(ImageBase + 8LL * (unsigned int)(v6 - 1) + dispIPtoStateMap + 4);
  else
    return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x180003624  push    rbx
0x180003626  sub     rsp, 20h
0x18000362a  test    rcx, rcx
0x18000362d  jz      short loc_180003679
0x18000362f  movsxd  r11, dword ptr [rcx+18h]
0x180003633  mov     r9, [rdx+8]
0x180003637  lea     rbx, [r9+r11]
0x18000363b  test    rbx, rbx
0x18000363e  jz      short loc_180003679
0x180003640  mov     r10d, [rcx+14h]
0x180003644  test    r10d, r10d
0x180003647  jz      short loc_180003674
0x180003649  xor     edx, edx
0x18000364b  movsxd  rcx, dword ptr [rbx+rdx*8]
0x18000364f  add     rcx, r9
0x180003652  cmp     r8, rcx
0x180003655  jb      short loc_18000365E
0x180003657  inc     edx
0x180003659  cmp     edx, r10d
0x18000365c  jb      short loc_18000364B
0x18000365e  test    edx, edx
0x180003660  jz      short loc_180003674
0x180003662  lea     ecx, [rdx-1]
0x180003665  lea     rax, [r9+rcx*8]
0x180003669  mov     eax, [rax+r11+4]
0x18000366e  add     rsp, 20h
0x180003672  pop     rbx
0x180003673  retn
0x180003674  or      eax, 0FFFFFFFFh
0x180003677  jmp     short loc_18000366E
0x180003679  call    abort_0
```
