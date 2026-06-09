# RegWriteExpandStringValueNoThrow(HKEY__ *,wchar_t const *,tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>)

- ea: `0x14001b6d0`
- end: `0x14001b6ff`
- name: `?RegWriteExpandStringValueNoThrow@@YAJPEAUHKEY__@@PEB_WV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@@Z`
- size: `47`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x140009b58`
- `0x14001eb9c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001b6f4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001b6f4`

## pseudocode

```c
LSTATUS __fastcall RegWriteExpandStringValueNoThrow(HKEY a1, const WCHAR *a2, __int64 a3)
{
  return RegSetValueExW(a1, a2, 0, 2u, *(const BYTE **)a3, 2 * *(_DWORD *)(a3 + 8) + 2);
}

```

## disassembly

```asm
0x14001b6d0  sub     rsp, 38h
0x14001b6d4  mov     eax, [r8+8]
0x14001b6d8  mov     r9d, 2; dwType
0x14001b6de  lea     eax, ds:2[rax*2]
0x14001b6e5  mov     [rsp+38h+cbData], eax; cbData
0x14001b6e9  mov     rax, [r8]
0x14001b6ec  xor     r8d, r8d; Reserved
0x14001b6ef  mov     [rsp+38h+lpData], rax; lpData
0x14001b6f4  call    cs:__imp_RegSetValueExW
0x14001b6fa  add     rsp, 38h
0x14001b6fe  retn
```
