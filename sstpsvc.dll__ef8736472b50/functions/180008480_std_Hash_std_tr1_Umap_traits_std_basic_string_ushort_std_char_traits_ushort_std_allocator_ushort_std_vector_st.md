# std::_Hash<std::tr1::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::_Hash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>>,0>>::~_Hash<std::tr1::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::_Hash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>>,0>>(void)

- ea: `0x180008480`
- end: `0x1800084a0`
- name: `??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@$0A@@tr1@std@@@std@@QEAA@XZ`
- size: `32`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008020`
- `0x180008474`

## callees

- `0x1800084a8`
- `0x1800084ec`

## pseudocode

```c
__int64 __fastcall __1___Hash_V___Umap_traits_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__vector_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__allocator_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2__2_V___Hash_compare_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__UCaseInsensitiveStringHash__UCaseInsensitiveStringEquality___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__vector_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__allocator_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2__2__std___2__0A__tr1_std___std__QEAA_XZ(
        __int64 a1)
{
  std::vector<_SSTP_TENANT_GATEWAY_ENTRY *>::~vector<_SSTP_TENANT_GATEWAY_ENTRY *>(a1 + 32);
  return std::list<std::pair<std::wstring const,std::vector<std::wstring>>>::~list<std::pair<std::wstring const,std::vector<std::wstring>>>(a1 + 8);
}

```

## disassembly

```asm
0x180008480  push    rbx
0x180008482  sub     rsp, 20h
0x180008486  mov     rbx, rcx
0x180008489  add     rcx, 20h ; ' '
0x18000848d  call    ??1?$vector@PEAU_SSTP_TENANT_GATEWAY_ENTRY@@V?$allocator@PEAU_SSTP_TENANT_GATEWAY_ENTRY@@@std@@@std@@QEAA@XZ; std::vector<_SSTP_TENANT_GATEWAY_ENTRY *>::~vector<_SSTP_TENANT_GATEWAY_ENTRY *>(void)
0x180008492  lea     rcx, [rbx+8]
0x180008496  add     rsp, 20h
0x18000849a  pop     rbx
0x18000849b  jmp     ??1?$list@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@QEAA@XZ; std::list<std::pair<std::wstring const,std::vector<std::wstring>>>::~list<std::pair<std::wstring const,std::vector<std::wstring>>>(void)
```
