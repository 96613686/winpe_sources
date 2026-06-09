# RegDeleteKeyRecursive(HKEY__ *,ushort const *)

- ea: `0x1800120f8`
- end: `0x1800121f6`
- name: `?RegDeleteKeyRecursive@@YAKPEAUHKEY__@@PEBG@Z`
- size: `254`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180003f08`
- `0x18000b300`
- `0x1800120f8`
- `0x180020923`

## callees

- `0x1800120f8`
- `0x18001fe50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800121ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800121ad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001213e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001213e`
- `ADVAPI32!RegDeleteKeyExW` at `0x1800121c7`
- `ADVAPI32!RegDeleteKeyExW` at `0x1800121c7`
- `ADVAPI32!RegEnumKeyExW` at `0x180012187`
- `ADVAPI32!RegEnumKeyExW` at `0x180012187`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RegDeleteKeyRecursive(HKEY a1, const unsigned __int16 *a2)
{
  unsigned int v4; // ebx
  HKEY hKey; // [rsp+40h] [rbp-238h] BYREF
  DWORD cchName; // [rsp+48h] [rbp-230h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-228h] BYREF

  hKey = 0;
  v4 = RegOpenKeyExW(a1, a2, 0, 0x2001Fu, &hKey);
  if ( !v4 )
  {
    do
    {
      cchName = 260;
      v4 = RegEnumKeyExW(hKey, 0, Name, &cchName, 0, 0, 0, 0);
      if ( v4 )
        break;
      v4 = RegDeleteKeyRecursive(hKey, Name);
    }
    while ( !v4 );
    RegCloseKey(hKey);
  }
  if ( v4 == 259 )
    return (unsigned int)RegDeleteKeyExW(a1, a2, 0, 0);
  return v4;
}

```

## disassembly

```asm
0x1800120f8  mov     [rsp+arg_10], rbx
0x1800120fd  mov     [rsp+arg_18], rsi
0x180012102  push    rdi
0x180012103  sub     rsp, 270h
0x18001210a  mov     rax, cs:__security_cookie
0x180012111  xor     rax, rsp
0x180012114  mov     [rsp+278h+var_18], rax
0x18001211c  lea     rax, [rsp+278h+hKey]
0x180012121  mov     [rsp+278h+hKey], 0
0x18001212a  mov     r9d, 2001Fh; samDesired
0x180012130  mov     [rsp+278h+phkResult], rax; phkResult
0x180012135  xor     r8d, r8d; ulOptions
0x180012138  mov     rsi, rdx
0x18001213b  mov     rdi, rcx
0x18001213e  call    cs:__imp_RegOpenKeyExW
0x180012144  mov     ebx, eax
0x180012146  test    eax, eax
0x180012148  jnz     short loc_1800121B3
0x18001214a  mov     rcx, [rsp+278h+hKey]; hKey
0x18001214f  lea     r9, [rsp+278h+cchName]; lpcchName
0x180012154  mov     [rsp+278h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18001215d  lea     r8, [rsp+278h+Name]; lpName
0x180012162  mov     [rsp+278h+lpcchClass], 0; lpcchClass
0x18001216b  xor     edx, edx; dwIndex
0x18001216d  mov     [rsp+278h+lpClass], 0; lpClass
0x180012176  mov     [rsp+278h+phkResult], 0; lpReserved
0x18001217f  mov     [rsp+278h+cchName], 104h
0x180012187  call    cs:__imp_RegEnumKeyExW
0x18001218d  mov     ebx, eax
0x18001218f  test    eax, eax
0x180012191  jnz     short loc_1800121A8
0x180012193  mov     rcx, [rsp+278h+hKey]; HKEY
0x180012198  lea     rdx, [rsp+278h+Name]; unsigned __int16 *
0x18001219d  call    ?RegDeleteKeyRecursive@@YAKPEAUHKEY__@@PEBG@Z; RegDeleteKeyRecursive(HKEY__ *,ushort const *)
0x1800121a2  mov     ebx, eax
0x1800121a4  test    eax, eax
0x1800121a6  jz      short loc_18001214A
0x1800121a8  mov     rcx, [rsp+278h+hKey]; hKey
0x1800121ad  call    cs:__imp_RegCloseKey
0x1800121b3  cmp     ebx, 103h
0x1800121b9  jnz     short loc_1800121CF
0x1800121bb  xor     r9d, r9d; Reserved
0x1800121be  xor     r8d, r8d; samDesired
0x1800121c1  mov     rdx, rsi; lpSubKey
0x1800121c4  mov     rcx, rdi; hKey
0x1800121c7  call    cs:__imp_RegDeleteKeyExW
0x1800121cd  mov     ebx, eax
0x1800121cf  mov     eax, ebx
0x1800121d1  mov     rcx, [rsp+278h+var_18]
0x1800121d9  xor     rcx, rsp; StackCookie
0x1800121dc  call    __security_check_cookie
0x1800121e1  lea     r11, [rsp+278h+var_8]
0x1800121e9  mov     rbx, [r11+20h]
0x1800121ed  mov     rsi, [r11+28h]
0x1800121f1  mov     rsp, r11
0x1800121f4  pop     rdi
0x1800121f5  retn
```
