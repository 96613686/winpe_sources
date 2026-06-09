# _dynamic_initializer_for__g_wuapicoreForwarder__

- ea: `0x1800019b0`
- end: `0x180001a2f`
- name: `_dynamic_initializer_for__g_wuapicoreForwarder__`
- size: `127`
- prototype: `int()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800019b0`
- `0x18000fcc0`
- `0x1800100b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800019c2`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800019c2`

## string_xrefs

- `0x1800019d1`: `wuapicore.dll`

## pseudocode

```c
int dynamic_initializer_for__g_wuapicoreForwarder__()
{
  InitializeCriticalSectionEx(&CriticalSection, 0, 0);
  byte_1800224B8 = 1;
  hLibModule = 0;
  if ( wcscpy_s(&Src, 0x104u, L"wuapicore.dll") || wcscpy_s(&word_180022278, 0x104u, L"wu.core.wuapi") )
  {
    Src = 0;
    word_180022278 = 0;
  }
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__g_wuapicoreForwarder__);
}

```

## disassembly

```asm
0x1800019b0  push    rbx
0x1800019b2  sub     rsp, 20h
0x1800019b6  xor     r8d, r8d; Flags
0x1800019b9  lea     rcx, CriticalSection; lpCriticalSection
0x1800019c0  xor     edx, edx; dwSpinCount
0x1800019c2  call    cs:__imp_InitializeCriticalSectionEx
0x1800019c8  xor     ebx, ebx
0x1800019ca  mov     cs:byte_1800224B8, 1
0x1800019d1  lea     r8, aWuapicoreDll; "wuapicore.dll"
0x1800019d8  mov     cs:hLibModule, rbx
0x1800019df  mov     edx, 104h; SizeInWords
0x1800019e4  lea     rcx, Src; Destination
0x1800019eb  call    wcscpy_s
0x1800019f0  test    eax, eax
0x1800019f2  jnz     short loc_180001A10
0x1800019f4  lea     r8, aWuCoreWuapi; "wu.core.wuapi"
0x1800019fb  mov     edx, 104h; SizeInWords
0x180001a00  lea     rcx, word_180022278; Destination
0x180001a07  call    wcscpy_s
0x180001a0c  test    eax, eax
0x180001a0e  jz      short loc_180001A1E
0x180001a10  mov     cs:Src, bx
0x180001a17  mov     cs:word_180022278, bx
0x180001a1e  lea     rcx, _dynamic_atexit_destructor_for__g_wuapicoreForwarder__
0x180001a25  add     rsp, 20h
0x180001a29  pop     rbx
0x180001a2a  jmp     atexit
```
