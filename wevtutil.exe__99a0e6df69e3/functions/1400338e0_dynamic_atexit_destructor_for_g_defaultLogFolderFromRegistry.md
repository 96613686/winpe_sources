# _dynamic_atexit_destructor_for__g_defaultLogFolderFromRegistry__

- ea: `0x1400338e0`
- end: `0x140033938`
- name: `_dynamic_atexit_destructor_for__g_defaultLogFolderFromRegistry__`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140004ae0`
- `0x1400338e0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140033927`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x140033907`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x140033907`

## pseudocode

```c
int dynamic_atexit_destructor_for__g_defaultLogFolderFromRegistry__()
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  LPVOID v2; // [rsp+38h] [rbp+10h] BYREF

  v1 = 0;
  v2 = 0;
  InitOnceBeginInitialize(&stru_1400425F8, 0, &v1, &v2);
  if ( v2 )
    return utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v2);
  else
    return InitOnceComplete(&stru_1400425F8, 0, 0);
}

```

## disassembly

```asm
0x1400338e0  mov     rax, rsp
0x1400338e3  sub     rsp, 28h
0x1400338e7  lea     r9, [rax+10h]; lpContext
0x1400338eb  mov     dword ptr [rax+8], 0
0x1400338f2  lea     r8, [rax+8]; fPending
0x1400338f6  mov     qword ptr [rax+10h], 0
0x1400338fe  xor     edx, edx; dwFlags
0x140033900  lea     rcx, stru_1400425F8; lpInitOnce
0x140033907  call    cs:__imp_InitOnceBeginInitialize
0x14003390d  mov     rcx, [rsp+28h+arg_8]
0x140033912  test    rcx, rcx
0x140033915  jnz     short loc_14003392E
0x140033917  xor     r8d, r8d
0x14003391a  lea     rcx, stru_1400425F8
0x140033921  xor     edx, edx
0x140033923  add     rsp, 28h
0x140033927  jmp     cs:__imp_InitOnceComplete
0x14003392e  call    ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x140033933  add     rsp, 28h
0x140033937  retn
```
