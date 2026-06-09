# DataStoreClient::GetAttributeDictionary(std::basic_string<ushort,std::char_traits<ushort>,StdAllocator<ushort>> &)

- ea: `0x1800545c0`
- end: `0x180054631`
- name: `?GetAttributeDictionary@DataStoreClient@@UEBAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$StdAllocator@G@@@std@@@Z`
- size: `113`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x18005102c`
- `0x1800545c0`
- `0x180058010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18005461e`
- `ole32!CoTaskMemFree` at `0x18005461e`

## pseudocode

```c
__int64 __fastcall DataStoreClient::GetAttributeDictionary(__int64 a1, __int64 a2)
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
    v4 = (*(__int64 (__fastcall **)(__int64, int *, LPVOID *))(*(_QWORD *)v2 + 32LL))(v2, &v6, &pv);
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
0x1800545c0  mov     r11, rsp
0x1800545c3  mov     [r11+10h], rbx
0x1800545c7  push    rdi
0x1800545c8  sub     rsp, 20h
0x1800545cc  mov     rcx, [rcx+38h]
0x1800545d0  mov     rdi, rdx
0x1800545d3  mov     [rsp+28h+arg_0], 0
0x1800545db  mov     ebx, 80004002h
0x1800545e0  mov     qword ptr [r11+18h], 0
0x1800545e8  test    rcx, rcx
0x1800545eb  jz      short loc_180054624
0x1800545ed  mov     rax, [rcx]
0x1800545f0  lea     r8, [r11+18h]
0x1800545f4  lea     rdx, [r11+8]
0x1800545f8  mov     rax, [rax+20h]
0x1800545fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054601  mov     ebx, eax
0x180054603  test    eax, eax
0x180054605  js      short loc_180054624
0x180054607  movsxd  r8, [rsp+28h+arg_0]
0x18005460c  mov     rcx, rdi
0x18005460f  mov     rdx, [rsp+28h+pv]
0x180054614  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$StdAllocator@G@@@std@@QEAAAEAV12@PEBG_K@Z; std::basic_string<ushort,std::char_traits<ushort>,StdAllocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180054619  mov     rcx, [rsp+28h+pv]; pv
0x18005461e  call    cs:__imp_CoTaskMemFree
0x180054624  mov     eax, ebx
0x180054626  mov     rbx, [rsp+28h+arg_8]
0x18005462b  add     rsp, 20h
0x18005462f  pop     rdi
0x180054630  retn
```
