# ReadRegistrySetting(HKEY__ *,HKEY__ *,ushort const *,ulong *,ulong)

- ea: `0x18004e21c`
- end: `0x18004e2a3`
- name: `?ReadRegistrySetting@@YAHPEAUHKEY__@@0PEBGPEAKK@Z`
- size: `135`
- prototype: `int(HKEY, HKEY, const unsigned __int16 *, unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180069a3c`

## callees

- `0x18004e21c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004e259`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004e259`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004e28d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004e28d`

## pseudocode

```c
_BOOL8 __fastcall ReadRegistrySetting(HKEY a1, HKEY a2, const unsigned __int16 *a3, BYTE *lpData, unsigned int a5)
{
  int v5; // esi
  DWORD v10[14]; // [rsp+30h] [rbp-38h] BYREF
  DWORD v11; // [rsp+88h] [rbp+20h] BYREF

  v5 = *(_DWORD *)lpData;
  v10[0] = 0;
  v11 = 4;
  if ( RegQueryValueExW(a1, a3, 0, v10, lpData, &v11) )
  {
    *(_DWORD *)lpData = a5;
    if ( a2 )
      RegSetValueExW(a2, a3, 0, 4u, lpData, 4u);
  }
  return v5 != *(_DWORD *)lpData;
}

```

## disassembly

```asm
0x18004e21c  mov     r11, rsp
0x18004e21f  push    rbx
0x18004e220  push    rbp
0x18004e221  push    rsi
0x18004e222  push    rdi
0x18004e223  sub     rsp, 48h
0x18004e227  mov     esi, [r9]
0x18004e22a  lea     rax, [r11+20h]
0x18004e22e  mov     rbp, r8
0x18004e231  mov     [r11-40h], rax
0x18004e235  mov     rbx, r9
0x18004e238  mov     [rsp+68h+var_38], 0
0x18004e240  mov     rdi, rdx
0x18004e243  mov     [r11-48h], rbx
0x18004e247  mov     rdx, rbp; lpValueName
0x18004e24a  mov     dword ptr [r11+20h], 4
0x18004e252  lea     r9, [r11-38h]; lpType
0x18004e256  xor     r8d, r8d; lpReserved
0x18004e259  call    cs:__imp_RegQueryValueExW
0x18004e25f  test    eax, eax
0x18004e261  jz      short loc_18004E293
0x18004e263  mov     eax, [rsp+68h+arg_20]
0x18004e26a  mov     [rbx], eax
0x18004e26c  test    rdi, rdi
0x18004e26f  jz      short loc_18004E293
0x18004e271  mov     [rsp+68h+cbData], 4; cbData
0x18004e279  mov     r9d, 4; dwType
0x18004e27f  xor     r8d, r8d; Reserved
0x18004e282  mov     [rsp+68h+lpData], rbx; lpData
0x18004e287  mov     rdx, rbp; lpValueName
0x18004e28a  mov     rcx, rdi; hKey
0x18004e28d  call    cs:__imp_RegSetValueExW
0x18004e293  xor     eax, eax
0x18004e295  cmp     esi, [rbx]
0x18004e297  setnz   al
0x18004e29a  add     rsp, 48h
0x18004e29e  pop     rdi
0x18004e29f  pop     rsi
0x18004e2a0  pop     rbp
0x18004e2a1  pop     rbx
0x18004e2a2  retn
```
