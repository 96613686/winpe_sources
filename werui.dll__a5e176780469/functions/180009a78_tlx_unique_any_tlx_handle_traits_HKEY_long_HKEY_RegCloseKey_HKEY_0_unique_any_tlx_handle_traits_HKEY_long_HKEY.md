# tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)

- ea: `0x180009a78`
- end: `0x180009a8f`
- name: `??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ`
- size: `23`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180009d14`
- `0x18000a32c`
- `0x18000f6cc`
- `0x180012b0c`
- `0x180013d88`
- `0x1800148a8`

## callees

- `0x180009a78`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180009a84`
- `ADVAPI32!RegCloseKey` at `0x180009a84`

## pseudocode

```c
LSTATUS __fastcall tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(
        HKEY *a1)
{
  HKEY v1; // rcx
  LSTATUS result; // eax

  v1 = *a1;
  if ( v1 )
    return RegCloseKey(v1);
  return result;
}

```

## disassembly

```asm
0x180009a78  sub     rsp, 28h
0x180009a7c  mov     rcx, [rcx]; hKey
0x180009a7f  test    rcx, rcx
0x180009a82  jz      short loc_180009A8A
0x180009a84  call    cs:__imp_RegCloseKey
0x180009a8a  add     rsp, 28h
0x180009a8e  retn
```
