# DataStoreClient::GetConfiguration(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,StdAllocator<ushort>> &)

- ea: `0x1800546c0`
- end: `0x180054731`
- name: `?GetConfiguration@DataStoreClient@@UEBAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$StdAllocator@G@@@std@@@Z`
- size: `113`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task`

## callees

- `0x18005102c`
- `0x1800546c0`
- `0x180058010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18005471e`
- `ole32!CoTaskMemFree` at `0x18005471e`

## pseudocode

```c
__int64 __fastcall DataStoreClient::GetConfiguration(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rcx
  int v5; // ebx
  int v7; // [rsp+40h] [rbp+8h] BYREF
  LPVOID pv; // [rsp+58h] [rbp+20h] BYREF

  v3 = *(_QWORD *)(a1 + 56);
  v7 = 0;
  v5 = -2147467262;
  pv = 0;
  if ( v3 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64, __int64, int *, LPVOID *))(*(_QWORD *)v3 + 40LL))(v3, a2, &v7, &pv);
    if ( v5 >= 0 )
    {
      std::basic_string<unsigned short,std::char_traits<unsigned short>,StdAllocator<unsigned short>>::assign(
        a3,
        pv,
        v7);
      CoTaskMemFree(pv);
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800546c0  mov     r11, rsp
0x1800546c3  mov     [r11+10h], rbx
0x1800546c7  push    rdi
0x1800546c8  sub     rsp, 30h
0x1800546cc  mov     rcx, [rcx+38h]
0x1800546d0  mov     rdi, r8
0x1800546d3  mov     [rsp+38h+arg_0], 0
0x1800546db  mov     ebx, 80004002h
0x1800546e0  mov     qword ptr [r11+20h], 0
0x1800546e8  test    rcx, rcx
0x1800546eb  jz      short loc_180054724
0x1800546ed  mov     rax, [rcx]
0x1800546f0  lea     r9, [r11+20h]
0x1800546f4  lea     r8, [r11+8]
0x1800546f8  mov     rax, [rax+28h]
0x1800546fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054701  mov     ebx, eax
0x180054703  test    eax, eax
0x180054705  js      short loc_180054724
0x180054707  movsxd  r8, [rsp+38h+arg_0]
0x18005470c  mov     rcx, rdi
0x18005470f  mov     rdx, [rsp+38h+pv]
0x180054714  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$StdAllocator@G@@@std@@QEAAAEAV12@PEBG_K@Z; std::basic_string<ushort,std::char_traits<ushort>,StdAllocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180054719  mov     rcx, [rsp+38h+pv]; pv
0x18005471e  call    cs:__imp_CoTaskMemFree
0x180054724  mov     eax, ebx
0x180054726  mov     rbx, [rsp+38h+arg_8]
0x18005472b  add     rsp, 30h
0x18005472f  pop     rdi
0x180054730  retn
```
