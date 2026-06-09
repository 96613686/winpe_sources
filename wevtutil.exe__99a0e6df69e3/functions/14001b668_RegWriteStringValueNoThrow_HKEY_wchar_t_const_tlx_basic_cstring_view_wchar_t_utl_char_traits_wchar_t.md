# RegWriteStringValueNoThrow(HKEY__ *,wchar_t const *,tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>)

- ea: `0x14001b668`
- end: `0x14001b697`
- name: `?RegWriteStringValueNoThrow@@YAJPEAUHKEY__@@PEB_WV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@@Z`
- size: `47`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x140009b58`
- `0x14001291c`
- `0x140013658`
- `0x14001eb9c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001b68c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001b68c`

## pseudocode

```c
LSTATUS __fastcall RegWriteStringValueNoThrow(HKEY a1, const WCHAR *a2, __int64 a3)
{
  return RegSetValueExW(a1, a2, 0, 1u, *(const BYTE **)a3, 2 * *(_DWORD *)(a3 + 8) + 2);
}

```

## disassembly

```asm
0x14001b668  sub     rsp, 38h
0x14001b66c  mov     eax, [r8+8]
0x14001b670  mov     r9d, 1; dwType
0x14001b676  lea     eax, ds:2[rax*2]
0x14001b67d  mov     [rsp+38h+cbData], eax; cbData
0x14001b681  mov     rax, [r8]
0x14001b684  xor     r8d, r8d; Reserved
0x14001b687  mov     [rsp+38h+lpData], rax; lpData
0x14001b68c  call    cs:__imp_RegSetValueExW
0x14001b692  add     rsp, 38h
0x14001b696  retn
```
