# SetRegValueString(HKEY__ *,ushort const *,ushort const *,ushort const *)

- ea: `0x1800206ac`
- end: `0x18002074f`
- name: `?SetRegValueString@@YAHPEAUHKEY__@@PEBG11@Z`
- size: `163`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001edb4`

## callees

- `0x1800206ac`

## import_xrefs

- `SHCORE!SHRegSetPathW` at `0x180020727`
- `SHCORE!SHRegSetPathW` at `0x180020727`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002070c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002070c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020737`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020737`

## string_xrefs

- `0x1800206d4`: `Control Panel\Accessibility\HighContrast`

## pseudocode

```c
__int64 __fastcall SetRegValueString(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  unsigned int v4; // ebx
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF
  DWORD v9; // [rsp+68h] [rbp+10h] BYREF
  int v10; // [rsp+6Ch] [rbp+14h]

  v10 = HIDWORD(a2);
  hKey = 0;
  v4 = 0;
  v9 = 0;
  if ( !RegCreateKeyExW(HKEY_CURRENT_USER, L"Control Panel\\Accessibility\\HighContrast", 0, 0, 0, 2u, 0, &hKey, &v9) )
  {
    LOBYTE(v4) = SHRegSetPathW(hKey, 0, a3, a4, 0) == 0;
    RegCloseKey(hKey);
  }
  return v4;
}

```

## disassembly

```asm
0x1800206ac  mov     r11, rsp
0x1800206af  mov     [r11+18h], rbx
0x1800206b3  mov     [r11+20h], rsi
0x1800206b7  mov     [r11+10h], rdx
0x1800206bb  mov     [r11+8], rcx
0x1800206bf  push    rdi
0x1800206c0  sub     rsp, 50h
0x1800206c4  lea     rax, [r11+10h]
0x1800206c8  mov     qword ptr [r11+8], 0
0x1800206d0  mov     [r11-18h], rax
0x1800206d4  lea     rdx, aControlPanelAc; "Control Panel\\Accessibility\\HighContr"...
0x1800206db  xor     ebx, ebx
0x1800206dd  lea     rax, [r11+8]
0x1800206e1  mov     [r11-20h], rax
0x1800206e5  mov     rdi, r9
0x1800206e8  mov     [r11-28h], rbx
0x1800206ec  mov     rsi, r8
0x1800206ef  mov     [rsp+58h+samDesired], 2; samDesired
0x1800206f7  xor     r9d, r9d; lpClass
0x1800206fa  xor     r8d, r8d; Reserved
0x1800206fd  mov     [rsp+58h+dwOptions], ebx; dwOptions
0x180020701  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180020708  mov     [rsp+58h+arg_8], ebx
0x18002070c  call    cs:__imp_RegCreateKeyExW
0x180020712  test    eax, eax
0x180020714  jnz     short loc_18002073D
0x180020716  mov     rcx, [rsp+58h+hKey]; hKey
0x18002071b  mov     r9, rdi; pcszPath
0x18002071e  mov     r8, rsi; pcszValue
0x180020721  mov     [rsp+58h+dwOptions], ebx; dwFlags
0x180020725  xor     edx, edx; pcszSubKey
0x180020727  call    cs:__imp_SHRegSetPathW
0x18002072d  mov     rcx, [rsp+58h+hKey]; hKey
0x180020732  test    eax, eax
0x180020734  setz    bl
0x180020737  call    cs:__imp_RegCloseKey
0x18002073d  mov     rsi, [rsp+58h+arg_18]
0x180020742  mov     eax, ebx
0x180020744  mov     rbx, [rsp+58h+arg_10]
0x180020749  add     rsp, 50h
0x18002074d  pop     rdi
0x18002074e  retn
```
