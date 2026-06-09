# OnDelete<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *)>::~OnDelete<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *)>(void)

- ea: `0x18000fa64`
- end: `0x18000fa77`
- name: `??1?$OnDelete@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z@@QEAA@XZ`
- size: `19`
- prototype: `LSTATUS __fastcall(HKEY *)`
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180016b77`
- `0x180016bad`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fa6b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fa6b`

## pseudocode

```c
LSTATUS __fastcall OnDelete<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *)>::~OnDelete<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *)>(
        HKEY *a1)
{
  return RegCloseKey(*a1);
}

```

## disassembly

```asm
0x18000fa64  sub     rsp, 28h
0x18000fa68  mov     rcx, [rcx]; hKey
0x18000fa6b  call    cs:__imp_RegCloseKey
0x18000fa71  nop
0x18000fa72  add     rsp, 28h
0x18000fa76  retn
```
