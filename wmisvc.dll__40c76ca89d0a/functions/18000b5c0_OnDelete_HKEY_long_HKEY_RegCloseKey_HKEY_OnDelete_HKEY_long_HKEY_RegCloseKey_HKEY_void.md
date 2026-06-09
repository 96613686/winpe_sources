# OnDelete<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *)>::~OnDelete<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *)>(void)

- ea: `0x18000b5c0`
- end: `0x18000b5d3`
- name: `??1?$OnDelete@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z@@QEAA@XZ`
- size: `19`
- prototype: `LSTATUS __fastcall(HKEY *)`
- caller_count: `8`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x18001dd3b`
- `0x18001df9a`
- `0x18001e165`
- `0x18001ea93`
- `0x18001eaa5`
- `0x18001eaed`
- `0x18001eb23`
- `0x18001eb6b`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b5c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b5c7`

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
0x18000b5c0  sub     rsp, 28h
0x18000b5c4  mov     rcx, [rcx]; hKey
0x18000b5c7  call    cs:__imp_RegCloseKey
0x18000b5cd  nop
0x18000b5ce  add     rsp, 28h
0x18000b5d2  retn
```
