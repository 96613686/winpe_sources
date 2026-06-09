# SubscriptionWriteData::SetEventSources(_EventSources const &)

- ea: `0x18001f258`
- end: `0x18001f331`
- name: `?SetEventSources@SubscriptionWriteData@@QEAAXAEBU_EventSources@@@Z`
- size: `217`
- prototype: `void __fastcall(SubscriptionWriteData *__hidden this, const struct _EventSources *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18001483c`

## callees

- `0x180003430`
- `0x180003d8c`
- `0x18001e24c`
- `0x18001e2fc`
- `0x18001e41c`
- `0x18001f258`

## pseudocode

```c
void __fastcall SubscriptionWriteData::SetEventSources(SubscriptionWriteData *this, const struct _EventSources *a2)
{
  __int64 v4; // rsi
  void *v5; // rax
  unsigned int v6; // r11d
  __int64 v7; // rax
  __int64 v8; // r11
  __int64 v9; // rdx
  _QWORD v10[3]; // [rsp+20h] [rbp-18h] BYREF

  InitializeMetadataProp(*(_QWORD *)this, a2, a2);
  InitializeMetadataProp(*(_QWORD *)this, 2, (char *)a2 + 56);
  v4 = *(_QWORD *)this;
  v5 = operator new(*((_QWORD *)a2 + 6));
  v6 = 0;
  *(_QWORD *)(*(_QWORD *)(v4 + 8) + 88LL) = v5;
  for ( *(_DWORD *)(*(_QWORD *)(v4 + 8) + 80LL) = *((_DWORD *)a2 + 12);
        (unsigned __int64)v6 < *((_QWORD *)a2 + 6);
        v6 = v8 + 1 )
  {
    v10[0] = *((_QWORD *)a2 + 3);
    v10[1] = 0;
    v7 = std::_Vb_const_iterator<std::_Wrap_alloc<std::allocator<unsigned int>>>::operator+=(v10, v6);
    *(_BYTE *)(v8 + *(_QWORD *)(*(_QWORD *)(v4 + 8) + 88LL)) = ((1 << *(_QWORD *)(v7 + 8)) & **(_DWORD **)v7) != 0;
  }
  *(_DWORD *)(*(_QWORD *)(v4 + 8) + 72LL) = 5;
  InitializeMetadataProp(*(_QWORD *)this, 4, (char *)a2 + 80);
  InitializeMetadataProp(*(_QWORD *)this, v9, (char *)a2 + 104);
}

```

## disassembly

```asm
0x18001f258  mov     [rsp+arg_0], rbx
0x18001f25d  mov     [rsp+arg_8], rsi
0x18001f262  push    rdi
0x18001f263  sub     rsp, 30h
0x18001f267  mov     rdi, rcx
0x18001f26a  mov     r8, rdx
0x18001f26d  mov     rcx, [rcx]
0x18001f270  mov     rbx, rdx
0x18001f273  call    ?InitializeMetadataProp@@YAXAEAUtag_EcRpcMetadataPropertyList@@KAEBV?$vector@KV?$allocator@K@std@@@std@@@Z; InitializeMetadataProp(tag_EcRpcMetadataPropertyList &,ulong,std::vector<ulong> const &)
0x18001f278  mov     rcx, [rdi]
0x18001f27b  lea     r8, [rbx+38h]
0x18001f27f  mov     edx, 2
0x18001f284  call    ?InitializeMetadataProp@@YAXAEAUtag_EcRpcMetadataPropertyList@@KAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; InitializeMetadataProp(tag_EcRpcMetadataPropertyList &,ulong,std::vector<std::wstring> const &)
0x18001f289  mov     rcx, [rbx+30h]; dwBytes
0x18001f28d  mov     rsi, [rdi]
0x18001f290  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f295  mov     rcx, [rsi+8]
0x18001f299  xor     r11d, r11d
0x18001f29c  mov     [rcx+58h], rax
0x18001f2a0  mov     rcx, [rsi+8]
0x18001f2a4  mov     eax, [rbx+30h]
0x18001f2a7  mov     [rcx+50h], eax
0x18001f2aa  cmp     [rbx+30h], r11
0x18001f2ae  jbe     short loc_18001F2FA
0x18001f2b0  mov     rax, [rbx+18h]
0x18001f2b4  lea     rcx, [rsp+38h+var_18]
0x18001f2b9  mov     edx, r11d
0x18001f2bc  mov     [rsp+38h+var_18], rax
0x18001f2c1  mov     [rsp+38h+var_10], 0
0x18001f2ca  call    ??Y?$_Vb_const_iterator@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@std@@QEAAAEAV01@_J@Z; std::_Vb_const_iterator<std::_Wrap_alloc<std::allocator<uint>>>::operator+=(__int64)
0x18001f2cf  mov     edx, 1
0x18001f2d4  mov     rcx, [rax+8]
0x18001f2d8  mov     rax, [rax]
0x18001f2db  shl     edx, cl
0x18001f2dd  test    [rax], edx
0x18001f2df  mov     rax, [rsi+8]
0x18001f2e3  setnz   dl
0x18001f2e6  mov     rcx, [rax+58h]
0x18001f2ea  mov     [r11+rcx], dl
0x18001f2ee  inc     r11d
0x18001f2f1  mov     eax, r11d
0x18001f2f4  cmp     rax, [rbx+30h]
0x18001f2f8  jb      short loc_18001F2B0
0x18001f2fa  mov     rax, [rsi+8]
0x18001f2fe  lea     r8, [rbx+50h]
0x18001f302  mov     edx, 4
0x18001f307  mov     dword ptr [rax+48h], 5
0x18001f30e  mov     rcx, [rdi]
0x18001f311  call    ?InitializeMetadataProp@@YAXAEAUtag_EcRpcMetadataPropertyList@@KAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; InitializeMetadataProp(tag_EcRpcMetadataPropertyList &,ulong,std::vector<std::wstring> const &)
0x18001f316  mov     rcx, [rdi]
0x18001f319  lea     r8, [rbx+68h]
0x18001f31d  mov     rbx, [rsp+38h+arg_0]
0x18001f322  mov     rsi, [rsp+38h+arg_8]
0x18001f327  add     rsp, 30h
0x18001f32b  pop     rdi
0x18001f32c  jmp     ?InitializeMetadataProp@@YAXAEAUtag_EcRpcMetadataPropertyList@@KAEBV?$vector@V?$vector@GV?$allocator@G@std@@@std@@V?$allocator@V?$vector@GV?$allocator@G@std@@@std@@@2@@std@@@Z; InitializeMetadataProp(tag_EcRpcMetadataPropertyList &,ulong,std::vector<std::vector<ushort>> const &)
```
