# std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<ActionPlugin,std::default_delete<ActionPlugin>>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<ActionPlugin,std::default_delete<ActionPlugin>>>,void *>>>(void)

- ea: `0x180018970`
- end: `0x1800189de`
- name: `??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VActionPlugin@@U?$default_delete@VActionPlugin@@@std@@@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `110`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x1800181b4`
- `0x180027608`

## callees

- `0x180003304`
- `0x1800115e0`
- `0x180018970`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800189a0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800189a0`

## pseudocode

```c
void __fastcall std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::unique_ptr<ActionPlugin>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::unique_ptr<ActionPlugin>>,void *>>>(
        __int64 a1)
{
  __int64 v1; // rax
  __int64 v3; // rdi
  HMODULE *v4; // rbx
  void *v5; // rcx

  v1 = *(_QWORD *)(a1 + 8);
  if ( v1 )
  {
    v3 = v1 + 16;
    v4 = *(HMODULE **)(v1 + 48);
    if ( v4 )
    {
      if ( *v4 )
        FreeLibrary(*v4);
      operator delete(v4, 0x10u);
    }
    std::wstring::~wstring(v3);
  }
  v5 = *(void **)(a1 + 8);
  if ( v5 )
    operator delete(v5, 0x38u);
}

```

## disassembly

```asm
0x180018970  mov     [rsp+arg_0], rbx
0x180018975  mov     [rsp+arg_8], rsi
0x18001897a  push    rdi
0x18001897b  sub     rsp, 20h
0x18001897f  mov     rax, [rcx+8]
0x180018983  mov     rsi, rcx
0x180018986  test    rax, rax
0x180018989  jz      short loc_1800189BB
0x18001898b  lea     rdi, [rax+10h]
0x18001898f  mov     rbx, [rdi+20h]
0x180018993  test    rbx, rbx
0x180018996  jz      short loc_1800189B3
0x180018998  mov     rcx, [rbx]; hLibModule
0x18001899b  test    rcx, rcx
0x18001899e  jz      short loc_1800189A6
0x1800189a0  call    cs:__imp_FreeLibrary
0x1800189a6  mov     edx, 10h; unsigned __int64
0x1800189ab  mov     rcx, rbx; void *
0x1800189ae  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800189b3  mov     rcx, rdi
0x1800189b6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800189bb  mov     rcx, [rsi+8]; void *
0x1800189bf  test    rcx, rcx
0x1800189c2  jz      short loc_1800189CE
0x1800189c4  mov     edx, 38h ; '8'; unsigned __int64
0x1800189c9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800189ce  mov     rbx, [rsp+28h+arg_0]
0x1800189d3  mov     rsi, [rsp+28h+arg_8]
0x1800189d8  add     rsp, 20h
0x1800189dc  pop     rdi
0x1800189dd  retn
```
