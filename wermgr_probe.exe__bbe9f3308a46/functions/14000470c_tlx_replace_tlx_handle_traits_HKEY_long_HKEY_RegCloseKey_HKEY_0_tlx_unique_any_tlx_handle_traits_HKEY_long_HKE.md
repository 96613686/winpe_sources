# tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)

- ea: `0x14000470c`
- end: `0x140004733`
- name: `??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z`
- size: `39`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140004e18`
- `0x140008220`
- `0x1400084f4`
- `0x14000964c`
- `0x14000a098`
- `0x14000c394`
- `0x14000c488`
- `0x140015ddc`

## callees

- `0x14000470c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004724`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004724`

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
0x14000470c  push    rbx
0x14000470e  sub     rsp, 20h
0x140004712  mov     rbx, rcx
0x140004715  mov     rcx, [rcx]; hKey
0x140004718  mov     qword ptr [rbx], 0
0x14000471f  test    rcx, rcx
0x140004722  jz      short loc_14000472A
0x140004724  call    cs:__imp_RegCloseKey
0x14000472a  mov     rax, rbx
0x14000472d  add     rsp, 20h
0x140004731  pop     rbx
0x140004732  retn
```
