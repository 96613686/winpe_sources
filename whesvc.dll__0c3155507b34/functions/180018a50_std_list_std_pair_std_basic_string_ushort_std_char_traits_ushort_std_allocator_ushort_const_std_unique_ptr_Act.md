# std::list<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<ActionPlugin,std::default_delete<ActionPlugin>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<ActionPlugin,std::default_delete<ActionPlugin>>>>>::~list<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<ActionPlugin,std::default_delete<ActionPlugin>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<ActionPlugin,std::default_delete<ActionPlugin>>>>>(void)

- ea: `0x180018a50`
- end: `0x180018ad0`
- name: `??1?$list@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VActionPlugin@@U?$default_delete@VActionPlugin@@@std@@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VActionPlugin@@U?$default_delete@VActionPlugin@@@std@@@2@@std@@@2@@std@@QEAA@XZ`
- size: `128`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x180027662`
- `0x1800284b0`

## callees

- `0x180003304`
- `0x1800115e0`
- `0x180018a50`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180018a88`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180018a88`

## pseudocode

```c
void __fastcall std::list<std::pair<std::wstring const,std::unique_ptr<ActionPlugin>>>::~list<std::pair<std::wstring const,std::unique_ptr<ActionPlugin>>>(
        void **a1)
{
  void **v1; // rdx
  void *v3; // rbx
  HMODULE *v4; // rdi
  void *v5; // r14

  v1 = (void **)*a1;
  **((_QWORD **)*a1 + 1) = 0;
  v3 = *v1;
  if ( *v1 )
  {
    do
    {
      v4 = (HMODULE *)*((_QWORD *)v3 + 6);
      v5 = *(void **)v3;
      if ( v4 )
      {
        if ( *v4 )
          FreeLibrary(*v4);
        operator delete(v4, 0x10u);
      }
      std::wstring::~wstring((char **)v3 + 2);
      operator delete(v3, 0x38u);
      v3 = v5;
    }
    while ( v5 );
  }
  operator delete(*a1, 0x38u);
}

```

## disassembly

```asm
0x180018a50  push    rbx
0x180018a52  push    rbp
0x180018a53  push    rsi
0x180018a54  push    rdi
0x180018a55  push    r14
0x180018a57  sub     rsp, 20h
0x180018a5b  mov     rdx, [rcx]
0x180018a5e  mov     rsi, rcx
0x180018a61  mov     rax, [rdx+8]
0x180018a65  mov     qword ptr [rax], 0
0x180018a6c  mov     rbx, [rdx]
0x180018a6f  test    rbx, rbx
0x180018a72  jz      short loc_180018AB9
0x180018a74  mov     rdi, [rbx+30h]
0x180018a78  mov     r14, [rbx]
0x180018a7b  test    rdi, rdi
0x180018a7e  jz      short loc_180018A9B
0x180018a80  mov     rcx, [rdi]; hLibModule
0x180018a83  test    rcx, rcx
0x180018a86  jz      short loc_180018A8E
0x180018a88  call    cs:__imp_FreeLibrary
0x180018a8e  mov     edx, 10h; unsigned __int64
0x180018a93  mov     rcx, rdi; void *
0x180018a96  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180018a9b  lea     rcx, [rbx+10h]
0x180018a9f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180018aa4  mov     edx, 38h ; '8'; unsigned __int64
0x180018aa9  mov     rcx, rbx; void *
0x180018aac  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180018ab1  mov     rbx, r14
0x180018ab4  test    r14, r14
0x180018ab7  jnz     short loc_180018A74
0x180018ab9  mov     rcx, [rsi]; void *
0x180018abc  mov     edx, 38h ; '8'; unsigned __int64
0x180018ac1  add     rsp, 20h
0x180018ac5  pop     r14
0x180018ac7  pop     rdi
0x180018ac8  pop     rsi
0x180018ac9  pop     rbp
0x180018aca  pop     rbx
0x180018acb  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
