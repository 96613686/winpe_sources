# tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)

- ea: `0x1800098f8`
- end: `0x18000991f`
- name: `??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z`
- size: `39`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180009d14`
- `0x18000a32c`
- `0x180012b0c`
- `0x180013ce8`
- `0x180013d88`
- `0x1800148a8`

## callees

- `0x1800098f8`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180009910`
- `ADVAPI32!RegCloseKey` at `0x180009910`

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
0x1800098f8  push    rbx
0x1800098fa  sub     rsp, 20h
0x1800098fe  mov     rbx, rcx
0x180009901  mov     rcx, [rcx]; hKey
0x180009904  mov     qword ptr [rbx], 0
0x18000990b  test    rcx, rcx
0x18000990e  jz      short loc_180009916
0x180009910  call    cs:__imp_RegCloseKey
0x180009916  mov     rax, rbx
0x180009919  add     rsp, 20h
0x18000991d  pop     rbx
0x18000991e  retn
```
