# CTapiLuaLib::lineConfigProviderLua(HWND__ *,ulong)

- ea: `0x180004b10`
- end: `0x180004b1d`
- name: `?lineConfigProviderLua@CTapiLuaLib@@UEAAJPEAUHWND__@@K@Z`
- size: `13`
- prototype: `LONG __fastcall(CTapiLuaLib *this, HWND, DWORD)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `TAPI32!lineConfigProvider` at `0x180004b16`

## pseudocode

```c
LONG __fastcall CTapiLuaLib::lineConfigProviderLua(CTapiLuaLib *this, HWND a2, DWORD a3)
{
  return lineConfigProvider(a2, a3);
}

```

## disassembly

```asm
0x180004b10  mov     rcx, rdx
0x180004b13  mov     edx, r8d
0x180004b16  jmp     cs:__imp_lineConfigProvider
```
