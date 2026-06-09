# _dynamic_initializer_for__g_updatePolicyCoreForwarder__

- ea: `0x180001160`
- end: `0x1800011df`
- name: `_dynamic_initializer_for__g_updatePolicyCoreForwarder__`
- size: `127`
- prototype: `int()`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001160`
- `0x18000ed24`
- `0x18000f190`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180001172`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180001172`

## string_xrefs

- `0x180001181`: `UpdatePolicyCore.dll`
- `0x1800011a4`: `wu.updatepolicy`

## pseudocode

```c
int dynamic_initializer_for__g_updatePolicyCoreForwarder__()
{
  InitializeCriticalSectionEx(&CriticalSection, 0, 0);
  byte_1800204C8 = 1;
  hLibModule = 0;
  if ( wcscpy_s(&Src, 0x104u, L"UpdatePolicyCore.dll") || wcscpy_s(&word_180020288, 0x104u, L"wu.updatepolicy") )
  {
    Src = 0;
    word_180020288 = 0;
  }
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__g_updatePolicyCoreForwarder__);
}

```

## disassembly

```asm
0x180001160  push    rbx
0x180001162  sub     rsp, 20h
0x180001166  xor     r8d, r8d; Flags
0x180001169  lea     rcx, CriticalSection; lpCriticalSection
0x180001170  xor     edx, edx; dwSpinCount
0x180001172  call    cs:__imp_InitializeCriticalSectionEx
0x180001178  xor     ebx, ebx
0x18000117a  mov     cs:byte_1800204C8, 1
0x180001181  lea     r8, aUpdatepolicyco; "UpdatePolicyCore.dll"
0x180001188  mov     cs:hLibModule, rbx
0x18000118f  mov     edx, 104h; SizeInWords
0x180001194  lea     rcx, Src; Destination
0x18000119b  call    wcscpy_s
0x1800011a0  test    eax, eax
0x1800011a2  jnz     short loc_1800011C0
0x1800011a4  lea     r8, aWuUpdatepolicy; "wu.updatepolicy"
0x1800011ab  mov     edx, 104h; SizeInWords
0x1800011b0  lea     rcx, word_180020288; Destination
0x1800011b7  call    wcscpy_s
0x1800011bc  test    eax, eax
0x1800011be  jz      short loc_1800011CE
0x1800011c0  mov     cs:Src, bx
0x1800011c7  mov     cs:word_180020288, bx
0x1800011ce  lea     rcx, _dynamic_atexit_destructor_for__g_updatePolicyCoreForwarder__
0x1800011d5  add     rsp, 20h
0x1800011d9  pop     rbx
0x1800011da  jmp     atexit
```
