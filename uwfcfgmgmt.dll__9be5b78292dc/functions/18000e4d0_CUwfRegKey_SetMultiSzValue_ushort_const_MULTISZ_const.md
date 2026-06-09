# CUwfRegKey::SetMultiSzValue(ushort const *,_MULTISZ * const)

- ea: `0x18000e4d0`
- end: `0x18000e52a`
- name: `?SetMultiSzValue@CUwfRegKey@@QEAAJPEBGQEAU_MULTISZ@@@Z`
- size: `90`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *, const BYTE **)`
- caller_count: `12`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180005c80`
- `0x180005f00`
- `0x180008d30`
- `0x180008da0`
- `0x180008f60`
- `0x180009170`
- `0x18000a240`
- `0x18000d420`
- `0x18000ea14`
- `0x18000efbc`
- `0x18000f610`
- `0x180010a5c`

## callees

- `0x18000e4d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000e509`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000e509`

## pseudocode

```c
__int64 __fastcall CUwfRegKey::SetMultiSzValue(HKEY *this, const unsigned __int16 *a2, const BYTE **a3)
{
  unsigned int v3; // ebx
  const BYTE *lpData; // r9
  DWORD cbData; // eax
  LSTATUS v6; // eax

  v3 = 0;
  if ( a3 )
  {
    lpData = *a3;
    cbData = 2 * *((_DWORD *)a3 + 2);
  }
  else
  {
    cbData = 4;
    lpData = (const BYTE *)&dword_18001FAA4;
  }
  v6 = RegSetValueExW(*this, a2, 0, 7u, lpData, cbData);
  if ( v6 )
  {
    if ( v6 > 0 )
      return (unsigned __int16)v6 | 0x80070000;
    else
      return (unsigned int)v6;
  }
  return v3;
}

```

## disassembly

```asm
0x18000e4d0  push    rbx
0x18000e4d2  sub     rsp, 30h
0x18000e4d6  xor     ebx, ebx
0x18000e4d8  test    r8, r8
0x18000e4db  jz      short loc_18000E4E8
0x18000e4dd  mov     eax, [r8+8]
0x18000e4e1  mov     r9, [r8]
0x18000e4e4  add     eax, eax
0x18000e4e6  jmp     short loc_18000E4F4
0x18000e4e8  mov     eax, 4
0x18000e4ed  lea     r9, dword_18001FAA4
0x18000e4f4  mov     rcx, [rcx]; hKey
0x18000e4f7  xor     r8d, r8d; Reserved
0x18000e4fa  mov     [rsp+38h+cbData], eax; cbData
0x18000e4fe  mov     [rsp+38h+lpData], r9; lpData
0x18000e503  mov     r9d, 7; dwType
0x18000e509  call    cs:__imp_RegSetValueExW
0x18000e50f  test    eax, eax
0x18000e511  jz      short loc_18000E522
0x18000e513  jg      short loc_18000E519
0x18000e515  mov     ebx, eax
0x18000e517  jmp     short loc_18000E522
0x18000e519  movzx   ebx, ax
0x18000e51c  or      ebx, 80070000h
0x18000e522  mov     eax, ebx
0x18000e524  add     rsp, 30h
0x18000e528  pop     rbx
0x18000e529  retn
```
