# tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)

- ea: `0x180007cc8`
- end: `0x180007cef`
- name: `??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z`
- size: `39`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000ff1c`
- `0x18000fff0`
- `0x1800133dc`
- `0x18002cd78`
- `0x18002d1f0`
- `0x180031000`
- `0x180031610`
- `0x180031a48`

## callees

- `0x180007cc8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007ce0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007ce0`

## pseudocode

```c
HKEY *__fastcall tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(HKEY *a1)
{
  HKEY v2; // rcx

  v2 = *a1;
  *a1 = 0;
  if ( v2 )
    RegCloseKey(v2);
  return a1;
}

```

## disassembly

```asm
0x180007cc8  push    rbx
0x180007cca  sub     rsp, 20h
0x180007cce  mov     rbx, rcx
0x180007cd1  mov     rcx, [rcx]; hKey
0x180007cd4  mov     qword ptr [rbx], 0
0x180007cdb  test    rcx, rcx
0x180007cde  jz      short loc_180007CE6
0x180007ce0  call    cs:__imp_RegCloseKey
0x180007ce6  mov     rax, rbx
0x180007ce9  add     rsp, 20h
0x180007ced  pop     rbx
0x180007cee  retn
```
