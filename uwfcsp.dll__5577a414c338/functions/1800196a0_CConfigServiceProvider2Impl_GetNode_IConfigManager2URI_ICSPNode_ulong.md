# CConfigServiceProvider2Impl::GetNode(IConfigManager2URI *,ICSPNode * *,ulong *)

- ea: `0x1800196a0`
- end: `0x180019795`
- name: `?GetNode@CConfigServiceProvider2Impl@@UEAAJPEAUIConfigManager2URI@@PEAPEAUICSPNode@@PEAK@Z`
- size: `245`
- prototype: `__int64 __fastcall(const struct CspNodeMapBase **this, struct IConfigManager2URI *, struct ICSPNode **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800073c0`

## callees

- `0x1800196a0`
- `0x180019d6c`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall CConfigServiceProvider2Impl::GetNode(
        const struct CspNodeMapBase **this,
        struct IConfigManager2URI *a2,
        struct ICSPNode **a3,
        unsigned int *a4)
{
  int v8; // ecx
  const struct CspNodeMapBase *v9; // rcx
  const struct CSP_NODEMAP_ENTRY *NodeMapEntryForURI; // rax
  const struct CSP_NODEMAP_ENTRY *v11; // r8
  __int64 (__fastcall *v12)(CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODEMAP_ENTRY *, _QWORD, struct ICSPNode **, unsigned int *); // rax
  unsigned int v14; // [rsp+40h] [rbp-38h] BYREF
  struct ICSPNode *v15; // [rsp+48h] [rbp-30h] BYREF
  int v16; // [rsp+88h] [rbp+10h] BYREF

  v16 = 0;
  if ( a2 && a3 && (*a3 = 0, a4) )
  {
    *a4 = 0;
    v8 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, int *))(*(_QWORD *)a2 + 136LL))(a2, &v16);
    if ( v8 >= 0 )
    {
      if ( v16 && (v9 = this[4]) != 0 && (NodeMapEntryForURI = CspGetNodeMapEntryForURI(v9, a2)) != 0 )
      {
        v15 = 0;
        v11 = NodeMapEntryForURI;
        v12 = (__int64 (__fastcall *)(CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODEMAP_ENTRY *, _QWORD, struct ICSPNode **, unsigned int *))*((_QWORD *)NodeMapEntryForURI + 4);
        v14 = 0;
        v8 = v12((CConfigServiceProvider2Impl *)this, a2, v11, 0, &v15, &v14);
        if ( v8 >= 0 )
        {
          if ( v15 )
          {
            *a3 = v15;
            *a4 = v14;
          }
          else
          {
            return (unsigned int)-2147024882;
          }
        }
      }
      else
      {
        return (unsigned int)-2046820350;
      }
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800196a0  mov     rax, rsp
0x1800196a3  push    rbx
0x1800196a4  push    rbp
0x1800196a5  push    rsi
0x1800196a6  push    rdi
0x1800196a7  sub     rsp, 58h
0x1800196ab  mov     dword ptr [rax+10h], 0
0x1800196b2  mov     rsi, r9
0x1800196b5  mov     rbx, r8
0x1800196b8  mov     rdi, rdx
0x1800196bb  mov     rbp, rcx
0x1800196be  test    rdx, rdx
0x1800196c1  jnz     short loc_1800196CD
0x1800196c3  mov     ecx, 80004003h
0x1800196c8  jmp     loc_18001978A
0x1800196cd  test    rbx, rbx
0x1800196d0  jz      short loc_1800196C3
0x1800196d2  mov     qword ptr [r8], 0
0x1800196d9  test    rsi, rsi
0x1800196dc  jz      short loc_1800196C3
0x1800196de  mov     dword ptr [r9], 0
0x1800196e5  mov     rcx, rdi
0x1800196e8  mov     rax, [rdx]
0x1800196eb  lea     rdx, [rsp+78h+arg_8]
0x1800196f3  mov     rax, [rax+88h]
0x1800196fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196ff  mov     ecx, eax
0x180019701  test    eax, eax
0x180019703  js      loc_18001978A
0x180019709  cmp     [rsp+78h+arg_8], 0
0x180019711  jz      short loc_180019785
0x180019713  mov     rcx, [rbp+20h]; struct CspNodeMapBase *
0x180019717  test    rcx, rcx
0x18001971a  jz      short loc_180019785
0x18001971c  mov     rdx, rdi; struct IConfigManager2URI *
0x18001971f  call    ?CspGetNodeMapEntryForURI@@YAPEBUCSP_NODEMAP_ENTRY@@PEBVCspNodeMapBase@@PEAUIConfigManager2URI@@@Z; CspGetNodeMapEntryForURI(CspNodeMapBase const *,IConfigManager2URI *)
0x180019724  test    rax, rax
0x180019727  jz      short loc_180019785
0x180019729  lea     rcx, [rsp+78h+var_38]
0x18001972e  mov     [rsp+78h+var_30], 0
0x180019737  mov     [rsp+78h+var_50], rcx
0x18001973c  mov     r8, rax
0x18001973f  mov     rax, [rax+20h]
0x180019743  lea     rcx, [rsp+78h+var_30]
0x180019748  mov     [rsp+78h+var_58], rcx
0x18001974d  xor     r9d, r9d
0x180019750  mov     rcx, rbp
0x180019753  mov     [rsp+78h+var_38], 0
0x18001975b  mov     rdx, rdi
0x18001975e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019763  mov     ecx, eax
0x180019765  test    eax, eax
0x180019767  js      short loc_18001978A
0x180019769  mov     rax, [rsp+78h+var_30]
0x18001976e  test    rax, rax
0x180019771  jnz     short loc_18001977A
0x180019773  mov     ecx, 8007000Eh
0x180019778  jmp     short loc_18001978A
0x18001977a  mov     [rbx], rax
0x18001977d  mov     eax, [rsp+78h+var_38]
0x180019781  mov     [rsi], eax
0x180019783  jmp     short loc_18001978A
0x180019785  mov     ecx, 86000002h
0x18001978a  mov     eax, ecx
0x18001978c  add     rsp, 58h
0x180019790  pop     rdi
0x180019791  pop     rsi
0x180019792  pop     rbp
0x180019793  pop     rbx
0x180019794  retn
```
