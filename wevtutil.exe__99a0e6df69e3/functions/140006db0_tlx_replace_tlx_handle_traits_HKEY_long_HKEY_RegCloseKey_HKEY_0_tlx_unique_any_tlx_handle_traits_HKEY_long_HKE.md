# tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)

- ea: `0x140006db0`
- end: `0x140006dd7`
- name: `??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z`
- size: `39`
- prototype: ``
- caller_count: `20`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140003b50`
- `0x140006008`
- `0x140006de0`
- `0x140009b58`
- `0x14001291c`
- `0x140013658`
- `0x140014988`
- `0x1400151ec`
- `0x140015cac`
- `0x14001663c`
- `0x140018f58`
- `0x14001aa58`
- `0x14001e0c0`
- `0x14001e458`
- `0x14002ab70`
- `0x14002b3b8`
- `0x14002bd08`
- `0x14002cc9c`
- `0x14002e0cc`
- `0x14002ecf4`

## callees

- `0x140006db0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006dc8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006dc8`

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
0x140006db0  push    rbx
0x140006db2  sub     rsp, 20h
0x140006db6  mov     rbx, rcx
0x140006db9  mov     rcx, [rcx]; hKey
0x140006dbc  mov     qword ptr [rbx], 0
0x140006dc3  test    rcx, rcx
0x140006dc6  jz      short loc_140006DCE
0x140006dc8  call    cs:__imp_RegCloseKey
0x140006dce  mov     rax, rbx
0x140006dd1  add     rsp, 20h
0x140006dd5  pop     rbx
0x140006dd6  retn
```
