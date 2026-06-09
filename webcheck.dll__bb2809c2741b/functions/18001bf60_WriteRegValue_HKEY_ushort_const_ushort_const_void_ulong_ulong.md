# WriteRegValue(HKEY__ *,ushort const *,ushort const *,void *,ulong,ulong)

- ea: `0x18001bf60`
- end: `0x18001c01c`
- name: `?WriteRegValue@@YAHPEAUHKEY__@@PEBG1PEAXKK@Z`
- size: `188`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, void *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800121f0`
- `0x180022ba0`

## callees

- `0x18001bf60`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18001c004`
- `ADVAPI32!RegCloseKey` at `0x18001c004`
- `ADVAPI32!RegCreateKeyExW` at `0x18001bfc6`
- `ADVAPI32!RegCreateKeyExW` at `0x18001bfc6`
- `ADVAPI32!RegSetValueExW` at `0x18001bff7`
- `ADVAPI32!RegSetValueExW` at `0x18001bff7`

## pseudocode

```c
_BOOL8 __fastcall WriteRegValue(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const BYTE *a4,
        DWORD cbData,
        DWORD dwType)
{
  LSTATUS v9; // ebx
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF
  DWORD v11; // [rsp+68h] [rbp+10h] BYREF
  int v12; // [rsp+6Ch] [rbp+14h]

  v12 = HIDWORD(a2);
  hKey = 0;
  v11 = 0;
  if ( RegCreateKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Webcheck",
         0,
         0,
         0,
         2u,
         0,
         &hKey,
         &v11) )
  {
    return 0;
  }
  v9 = RegSetValueExW(hKey, a3, 0, dwType, a4, cbData);
  RegCloseKey(hKey);
  return v9 == 0;
}

```

## disassembly

```asm
0x18001bf60  mov     r11, rsp
0x18001bf63  mov     [r11+18h], rbx
0x18001bf67  mov     [r11+10h], rdx
0x18001bf6b  mov     [r11+8], rcx
0x18001bf6f  push    rdi
0x18001bf70  sub     rsp, 50h
0x18001bf74  lea     rax, [r11+10h]
0x18001bf78  mov     qword ptr [r11+8], 0
0x18001bf80  mov     [r11-18h], rax
0x18001bf84  lea     rdx, ?c_szRegKey@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001bf8b  lea     rax, [r11+8]
0x18001bf8f  mov     [rsp+58h+arg_8], 0
0x18001bf97  mov     [r11-20h], rax
0x18001bf9b  mov     rbx, r9
0x18001bf9e  mov     qword ptr [r11-28h], 0
0x18001bfa6  mov     rdi, r8
0x18001bfa9  mov     [rsp+58h+samDesired], 2; samDesired
0x18001bfb1  xor     r9d, r9d; lpClass
0x18001bfb4  xor     r8d, r8d; Reserved
0x18001bfb7  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18001bfbf  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001bfc6  call    cs:__imp_RegCreateKeyExW
0x18001bfcc  test    eax, eax
0x18001bfce  jz      short loc_18001BFD4
0x18001bfd0  xor     eax, eax
0x18001bfd2  jmp     short loc_18001C011
0x18001bfd4  mov     eax, [rsp+58h+cbData]
0x18001bfdb  xor     r8d, r8d; Reserved
0x18001bfde  mov     r9d, [rsp+58h+dwType]; dwType
0x18001bfe6  mov     rdx, rdi; lpValueName
0x18001bfe9  mov     rcx, [rsp+58h+hKey]; hKey
0x18001bfee  mov     [rsp+58h+samDesired], eax; cbData
0x18001bff2  mov     qword ptr [rsp+58h+dwOptions], rbx; lpData
0x18001bff7  call    cs:__imp_RegSetValueExW
0x18001bffd  mov     rcx, [rsp+58h+hKey]; hKey
0x18001c002  mov     ebx, eax
0x18001c004  call    cs:__imp_RegCloseKey
0x18001c00a  xor     eax, eax
0x18001c00c  test    ebx, ebx
0x18001c00e  setz    al
0x18001c011  mov     rbx, [rsp+58h+arg_10]
0x18001c016  add     rsp, 50h
0x18001c01a  pop     rdi
0x18001c01b  retn
```
