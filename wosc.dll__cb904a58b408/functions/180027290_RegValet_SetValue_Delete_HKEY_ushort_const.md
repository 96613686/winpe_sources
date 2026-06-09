# RegValet::SetValue::Delete(HKEY__ *,ushort const *)

- ea: `0x180027290`
- end: `0x1800272b6`
- name: `?Delete@SetValue@RegValet@@SAJPEAUHKEY__@@PEBG@Z`
- size: `38`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops, registry_config`

## callers

- `0x1800269bc`
- `0x180026e6c`
- `0x18002b140`
- `0x1800504c0`

## callees

- `0x180027290`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180027294`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180027294`

## pseudocode

```c
__int64 __fastcall RegValet::SetValue::Delete(HKEY a1, const unsigned __int16 *a2)
{
  LSTATUS v2; // eax
  int v3; // ecx

  v2 = RegDeleteValueW(a1, a2);
  v3 = 0;
  if ( v2 != 2 )
    v3 = v2;
  if ( v3 > 0 )
    return (unsigned __int16)v3 | 0x80070000;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180027290  sub     rsp, 28h
0x180027294  call    cs:__imp_RegDeleteValueW
0x18002729a  xor     ecx, ecx
0x18002729c  cmp     eax, 2
0x18002729f  cmovnz  ecx, eax
0x1800272a2  test    ecx, ecx
0x1800272a4  jle     short loc_1800272AF
0x1800272a6  movzx   ecx, cx
0x1800272a9  or      ecx, 80070000h
0x1800272af  mov     eax, ecx
0x1800272b1  add     rsp, 28h
0x1800272b5  retn
```
