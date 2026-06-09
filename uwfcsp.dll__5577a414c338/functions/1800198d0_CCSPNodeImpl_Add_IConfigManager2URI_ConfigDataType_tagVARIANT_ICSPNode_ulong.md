# CCSPNodeImpl::Add(IConfigManager2URI *,ConfigDataType,tagVARIANT,ICSPNode * *,ulong *)

- ea: `0x1800198d0`
- end: `0x180019987`
- name: `?Add@CCSPNodeImpl@@UEAAJPEAUIConfigManager2URI@@W4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAK@Z`
- size: `183`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e610`

## callees

- `0x1800198d0`
- `0x180019d6c`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall CCSPNodeImpl::Add(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _QWORD *a5, _DWORD *a6)
{
  struct IConfigManager2URI *v7; // rcx
  int v8; // ebx
  const struct CspNodeMapBase *v9; // rcx
  const struct CSP_NODEMAP_ENTRY *NodeMapEntryForURI; // rax
  struct IConfigManager2URI *v12; // [rsp+30h] [rbp-18h] BYREF

  v7 = 0;
  v12 = 0;
  if ( a5 && a6 )
  {
    *a5 = 0;
    *a6 = 0;
    v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, struct IConfigManager2URI **))(**(_QWORD **)(a1 + 24)
                                                                                                  + 168LL))(
           *(_QWORD *)(a1 + 24),
           a2,
           0,
           0,
           &v12);
    if ( v8 >= 0 )
    {
      v9 = *(const struct CspNodeMapBase **)(*(_QWORD *)(a1 + 16) + 32LL);
      if ( v9 && (NodeMapEntryForURI = CspGetNodeMapEntryForURI(v9, v12)) != 0 )
        v8 = (*((_DWORD *)NodeMapEntryForURI + 5) & 4) != 0 ? -2147467263 : -2046820335;
      else
        v8 = -2046820335;
    }
    v7 = v12;
  }
  else
  {
    v8 = -2147024809;
  }
  if ( v7 )
    (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)v7 + 16LL))(v7);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800198d0  mov     r11, rsp
0x1800198d3  mov     [r11+8], rbx
0x1800198d7  push    rdi
0x1800198d8  sub     rsp, 40h
0x1800198dc  mov     r8, [rsp+48h+arg_20]
0x1800198e1  mov     rdi, rcx
0x1800198e4  xor     ecx, ecx
0x1800198e6  mov     [r11-18h], rcx
0x1800198ea  test    r8, r8
0x1800198ed  jz      short loc_180019964
0x1800198ef  mov     rax, [rsp+48h+arg_28]
0x1800198f4  test    rax, rax
0x1800198f7  jz      short loc_180019964
0x1800198f9  mov     [r8], rcx
0x1800198fc  xor     r9d, r9d
0x1800198ff  mov     [rax], ecx
0x180019901  lea     r8, [r11-18h]
0x180019905  mov     rcx, [rdi+18h]
0x180019909  mov     [r11-28h], r8
0x18001990d  xor     r8d, r8d
0x180019910  mov     rax, [rcx]
0x180019913  mov     rax, [rax+0A8h]
0x18001991a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001991f  mov     ebx, eax
0x180019921  test    eax, eax
0x180019923  js      short loc_180019956
0x180019925  mov     rax, [rdi+10h]
0x180019929  mov     rcx, [rax+20h]; struct CspNodeMapBase *
0x18001992d  test    rcx, rcx
0x180019930  jz      short loc_18001995D
0x180019932  mov     rdx, [rsp+48h+var_18]; struct IConfigManager2URI *
0x180019937  call    ?CspGetNodeMapEntryForURI@@YAPEBUCSP_NODEMAP_ENTRY@@PEBVCspNodeMapBase@@PEAUIConfigManager2URI@@@Z; CspGetNodeMapEntryForURI(CspNodeMapBase const *,IConfigManager2URI *)
0x18001993c  test    rax, rax
0x18001993f  jz      short loc_18001995D
0x180019941  mov     eax, [rax+14h]
0x180019944  and     al, 4
0x180019946  neg     al
0x180019948  sbb     ebx, ebx
0x18001994a  and     ebx, 0FA003FF0h
0x180019950  add     ebx, 86000011h
0x180019956  mov     rcx, [rsp+48h+var_18]
0x18001995b  jmp     short loc_180019969
0x18001995d  mov     ebx, 86000011h
0x180019962  jmp     short loc_180019956
0x180019964  mov     ebx, 80070057h
0x180019969  test    rcx, rcx
0x18001996c  jz      short loc_18001997A
0x18001996e  mov     rax, [rcx]
0x180019971  mov     rax, [rax+10h]
0x180019975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001997a  mov     eax, ebx
0x18001997c  mov     rbx, [rsp+48h+arg_0]
0x180019981  add     rsp, 40h
0x180019985  pop     rdi
0x180019986  retn
```
