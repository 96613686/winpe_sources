# CUwfRegKey::SetDWORDValue(ushort const *,ulong)

- ea: `0x18000e480`
- end: `0x18000e4c5`
- name: `?SetDWORDValue@CUwfRegKey@@QEAAJPEBGK@Z`
- size: `69`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *, int)`
- caller_count: `13`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180006c80`
- `0x1800079a0`
- `0x180008d30`
- `0x180009170`
- `0x1800092a8`
- `0x180009a50`
- `0x18000a150`
- `0x18000d370`
- `0x18000e780`
- `0x18000ef58`
- `0x18000efbc`
- `0x18000f17c`
- `0x180010a5c`

## callees

- `0x18000e480`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000e4a4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000e4a4`

## pseudocode

```c
__int64 __fastcall CUwfRegKey::SetDWORDValue(HKEY *this, const unsigned __int16 *a2, int a3)
{
  unsigned int v3; // ebx
  LSTATUS v4; // eax
  int v6; // [rsp+50h] [rbp+18h] BYREF

  v6 = a3;
  v3 = 0;
  v4 = RegSetValueExW(*this, a2, 0, 4u, (const BYTE *)&v6, 4u);
  if ( v4 )
  {
    if ( v4 > 0 )
      return (unsigned __int16)v4 | 0x80070000;
    else
      return (unsigned int)v4;
  }
  return v3;
}

```

## disassembly

```asm
0x18000e480  mov     r11, rsp
0x18000e483  mov     [r11+18h], r8d
0x18000e487  push    rbx
0x18000e488  sub     rsp, 30h
0x18000e48c  mov     rcx, [rcx]; hKey
0x18000e48f  lea     rax, [r11+18h]
0x18000e493  xor     ebx, ebx
0x18000e495  xor     r8d, r8d; Reserved
0x18000e498  lea     r9d, [rbx+4]; dwType
0x18000e49c  mov     [r11-10h], r9d
0x18000e4a0  mov     [r11-18h], rax
0x18000e4a4  call    cs:__imp_RegSetValueExW
0x18000e4aa  test    eax, eax
0x18000e4ac  jz      short loc_18000E4BD
0x18000e4ae  jg      short loc_18000E4B4
0x18000e4b0  mov     ebx, eax
0x18000e4b2  jmp     short loc_18000E4BD
0x18000e4b4  movzx   ebx, ax
0x18000e4b7  or      ebx, 80070000h
0x18000e4bd  mov     eax, ebx
0x18000e4bf  add     rsp, 30h
0x18000e4c3  pop     rbx
0x18000e4c4  retn
```
