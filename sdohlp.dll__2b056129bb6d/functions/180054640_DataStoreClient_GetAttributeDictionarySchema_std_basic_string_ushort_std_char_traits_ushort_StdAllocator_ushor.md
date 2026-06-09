# DataStoreClient::GetAttributeDictionarySchema(std::basic_string<ushort,std::char_traits<ushort>,StdAllocator<ushort>> &)

- ea: `0x180054640`
- end: `0x1800546b1`
- name: `?GetAttributeDictionarySchema@DataStoreClient@@UEBAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$StdAllocator@G@@@std@@@Z`
- size: `113`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x18005102c`
- `0x180054640`
- `0x180058010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18005469e`
- `ole32!CoTaskMemFree` at `0x18005469e`

## pseudocode

```c
__int64 __fastcall DataStoreClient::GetAttributeDictionarySchema(__int64 a1, __int64 a2)
{
  __int64 v2; // rcx
  int v4; // ebx
  int v6; // [rsp+30h] [rbp+8h] BYREF
  LPVOID pv; // [rsp+40h] [rbp+18h] BYREF

  v2 = *(_QWORD *)(a1 + 56);
  v6 = 0;
  v4 = -2147467262;
  pv = 0;
  if ( v2 )
  {
    v4 = (*(__int64 (__fastcall **)(__int64, int *, LPVOID *))(*(_QWORD *)v2 + 24LL))(v2, &v6, &pv);
    if ( v4 >= 0 )
    {
      std::basic_string<unsigned short,std::char_traits<unsigned short>,StdAllocator<unsigned short>>::assign(
        a2,
        pv,
        v6);
      CoTaskMemFree(pv);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180054640  mov     r11, rsp
0x180054643  mov     [r11+10h], rbx
0x180054647  push    rdi
0x180054648  sub     rsp, 20h
0x18005464c  mov     rcx, [rcx+38h]
0x180054650  mov     rdi, rdx
0x180054653  mov     [rsp+28h+arg_0], 0
0x18005465b  mov     ebx, 80004002h
0x180054660  mov     qword ptr [r11+18h], 0
0x180054668  test    rcx, rcx
0x18005466b  jz      short loc_1800546A4
0x18005466d  mov     rax, [rcx]
0x180054670  lea     r8, [r11+18h]
0x180054674  lea     rdx, [r11+8]
0x180054678  mov     rax, [rax+18h]
0x18005467c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054681  mov     ebx, eax
0x180054683  test    eax, eax
0x180054685  js      short loc_1800546A4
0x180054687  movsxd  r8, [rsp+28h+arg_0]
0x18005468c  mov     rcx, rdi
0x18005468f  mov     rdx, [rsp+28h+pv]
0x180054694  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$StdAllocator@G@@@std@@QEAAAEAV12@PEBG_K@Z; std::basic_string<ushort,std::char_traits<ushort>,StdAllocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180054699  mov     rcx, [rsp+28h+pv]; pv
0x18005469e  call    cs:__imp_CoTaskMemFree
0x1800546a4  mov     eax, ebx
0x1800546a6  mov     rbx, [rsp+28h+arg_8]
0x1800546ab  add     rsp, 20h
0x1800546af  pop     rdi
0x1800546b0  retn
```
