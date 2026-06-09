# CTapiLuaLib::lineRemoveProviderLua(ulong,HWND__ *)

- ea: `0x180004b30`
- end: `0x180004b3c`
- name: `?lineRemoveProviderLua@CTapiLuaLib@@UEAAJKPEAUHWND__@@@Z`
- size: `12`
- prototype: `LONG __fastcall(CTapiLuaLib *this, DWORD, HWND)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `TAPI32!lineRemoveProvider` at `0x180004b35`

## pseudocode

```c
LONG __fastcall CTapiLuaLib::lineRemoveProviderLua(CTapiLuaLib *this, DWORD a2, HWND a3)
{
  return lineRemoveProvider(a2, a3);
}

```

## disassembly

```asm
0x180004b30  mov     ecx, edx
0x180004b32  mov     rdx, r8
0x180004b35  jmp     cs:__imp_lineRemoveProvider
```
