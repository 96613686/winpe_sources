# tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)

- ea: `0x180002a18`
- end: `0x180002a3f`
- name: `??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z`
- size: `39`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180002ff0`
- `0x1800030d0`
- `0x180003fb0`
- `0x1800041b0`
- `0x1800042c0`
- `0x180005c28`

## callees

- `0x180002a18`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002a30`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002a30`

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
0x180002a18  push    rbx
0x180002a1a  sub     rsp, 20h
0x180002a1e  mov     rbx, rcx
0x180002a21  mov     rcx, [rcx]; hKey
0x180002a24  mov     qword ptr [rbx], 0
0x180002a2b  test    rcx, rcx
0x180002a2e  jz      short loc_180002A36
0x180002a30  call    cs:__imp_RegCloseKey
0x180002a36  mov     rax, rbx
0x180002a39  add     rsp, 20h
0x180002a3d  pop     rbx
0x180002a3e  retn
```
