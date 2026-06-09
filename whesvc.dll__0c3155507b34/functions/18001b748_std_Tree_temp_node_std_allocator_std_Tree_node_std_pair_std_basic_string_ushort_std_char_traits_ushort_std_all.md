# std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,_unnamed_tag_::AppRefreshState>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,_unnamed_tag_::AppRefreshState>,void *>>>(void)

- ea: `0x18001b748`
- end: `0x18001b797`
- name: `??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UAppRefreshState@_unnamed_tag_@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180027907`

## callees

- `0x180003304`
- `0x1800066dc`
- `0x1800115e0`
- `0x18001b748`

## pseudocode

```c
void __fastcall std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,_unnamed_tag_::AppRefreshState>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,_unnamed_tag_::AppRefreshState>,void *>>>(
        __int64 a1)
{
  __int64 v1; // rbx
  void *v3; // rcx

  v1 = *(_QWORD *)(a1 + 8);
  if ( v1 )
  {
    if ( *(_QWORD *)(v1 + 152) )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(v1 + 152);
    std::wstring::~wstring(v1 + 32);
  }
  v3 = *(void **)(a1 + 8);
  if ( v3 )
    operator delete(v3, 0xA0u);
}

```

## disassembly

```asm
0x18001b748  mov     [rsp+arg_0], rbx
0x18001b74d  push    rdi
0x18001b74e  sub     rsp, 20h
0x18001b752  mov     rbx, [rcx+8]
0x18001b756  mov     rdi, rcx
0x18001b759  test    rbx, rbx
0x18001b75c  jz      short loc_18001B779
0x18001b75e  lea     rcx, [rbx+98h]
0x18001b765  cmp     qword ptr [rcx], 0
0x18001b769  jz      short loc_18001B770
0x18001b76b  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x18001b770  lea     rcx, [rbx+20h]
0x18001b774  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b779  mov     rcx, [rdi+8]; void *
0x18001b77d  test    rcx, rcx
0x18001b780  jz      short loc_18001B78C
0x18001b782  mov     edx, 0A0h; unsigned __int64
0x18001b787  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001b78c  mov     rbx, [rsp+28h+arg_0]
0x18001b791  add     rsp, 20h
0x18001b795  pop     rdi
0x18001b796  retn
```
