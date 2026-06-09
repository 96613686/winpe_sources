# CUwfRegKey::DeleteValue(ushort const *)

- ea: `0x18000dd80`
- end: `0x18000ddac`
- name: `?DeleteValue@CUwfRegKey@@QEAAJPEBG@Z`
- size: `44`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800071d0`
- `0x1800072b0`
- `0x1800092a8`
- `0x180009a50`
- `0x18000f17c`

## callees

- `0x18000dd80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000dd8b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000dd8b`

## pseudocode

```c
__int64 __fastcall CUwfRegKey::DeleteValue(HKEY *this, const unsigned __int16 *a2)
{
  unsigned int v2; // ebx
  LSTATUS v3; // eax

  v2 = 0;
  v3 = RegDeleteValueW(*this, a2);
  if ( v3 )
  {
    if ( v3 > 0 )
      return (unsigned __int16)v3 | 0x80070000;
    else
      return (unsigned int)v3;
  }
  return v2;
}

```

## disassembly

```asm
0x18000dd80  push    rbx
0x18000dd82  sub     rsp, 20h
0x18000dd86  mov     rcx, [rcx]; hKey
0x18000dd89  xor     ebx, ebx
0x18000dd8b  call    cs:__imp_RegDeleteValueW
0x18000dd91  test    eax, eax
0x18000dd93  jz      short loc_18000DDA4
0x18000dd95  jg      short loc_18000DD9B
0x18000dd97  mov     ebx, eax
0x18000dd99  jmp     short loc_18000DDA4
0x18000dd9b  movzx   ebx, ax
0x18000dd9e  or      ebx, 80070000h
0x18000dda4  mov     eax, ebx
0x18000dda6  add     rsp, 20h
0x18000ddaa  pop     rbx
0x18000ddab  retn
```
