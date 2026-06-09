# ATL::InlineIsEqualUnknown(_GUID const &)

- ea: `0x180004ab4`
- end: `0x180004ad7`
- name: `?InlineIsEqualUnknown@ATL@@YAHAEBU_GUID@@@Z`
- size: `35`
- prototype: `__int64 __fastcall(const struct _GUID *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180003bcc`
- `0x180004600`
- `0x180004f90`
- `0x180004ff0`
- `0x180005050`

## callees

- `0x180004ab4`

## pseudocode

```c
_BOOL8 __fastcall ATL::InlineIsEqualUnknown(const struct _GUID *a1)
{
  _BOOL8 result; // rax

  result = 0;
  if ( !a1->Data1 && !*(_DWORD *)&a1->Data2 && *(_DWORD *)a1->Data4 == 192 )
    return *(_DWORD *)&a1->Data4[4] == 1174405120;
  return result;
}

```

## disassembly

```asm
0x180004ab4  xor     eax, eax
0x180004ab6  cmp     [rcx], eax
0x180004ab8  jnz     short locret_180004AD6
0x180004aba  cmp     [rcx+4], eax
0x180004abd  jnz     short locret_180004AD6
0x180004abf  cmp     dword ptr [rcx+8], 0C0h
0x180004ac6  jnz     short locret_180004AD6
0x180004ac8  cmp     dword ptr [rcx+0Ch], 46000000h
0x180004acf  jnz     short locret_180004AD6
0x180004ad1  mov     eax, 1
0x180004ad6  retn
```
