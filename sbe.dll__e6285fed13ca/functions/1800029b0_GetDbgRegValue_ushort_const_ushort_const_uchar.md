# GetDbgRegValue(ushort const *,ushort const *,uchar *)

- ea: `0x1800029b0`
- end: `0x180002a45`
- name: `?GetDbgRegValue@@YA_NPEBG0PEAE@Z`
- size: `149`
- prototype: `bool(const unsigned __int16 *, const unsigned __int16 *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002a4c`

## callees

- `0x1800029b0`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x180002a27`
- `ADVAPI32!RegQueryValueExW` at `0x180002a27`
- `ADVAPI32!RegCloseKey` at `0x180002a32`
- `ADVAPI32!RegCloseKey` at `0x180002a32`
- `ADVAPI32!RegOpenKeyExW` at `0x1800029ed`
- `ADVAPI32!RegOpenKeyExW` at `0x1800029ed`

## string_xrefs

- `0x1800029d9`: `Software\Microsoft\DVR\AppCompat`

## pseudocode

```c
char __fastcall GetDbgRegValue(const unsigned __int16 *a1, const unsigned __int16 *a2, unsigned __int8 *a3)
{
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF
  const unsigned __int16 *cbData; // [rsp+50h] [rbp+8h] BYREF
  DWORD Type; // [rsp+68h] [rbp+20h] BYREF

  cbData = a1;
  hKey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\DVR\\AppCompat", 0, 1u, &hKey) )
    return 0;
  Type = 4;
  LODWORD(cbData) = 4;
  RegQueryValueExW(hKey, a2, 0, &Type, a3, (LPDWORD)&cbData);
  RegCloseKey(hKey);
  return 1;
}

```

## disassembly

```asm
0x1800029b0  mov     r11, rsp
0x1800029b3  mov     [r11+10h], rbx
0x1800029b7  mov     [r11+8], rcx
0x1800029bb  push    rdi
0x1800029bc  sub     rsp, 40h
0x1800029c0  mov     rbx, r8
0x1800029c3  mov     qword ptr [r11-18h], 0
0x1800029cb  mov     rdi, rdx
0x1800029ce  lea     rax, [r11-18h]
0x1800029d2  xor     r8d, r8d; ulOptions
0x1800029d5  mov     [r11-28h], rax
0x1800029d9  lea     rdx, SubKey; "Software\\Microsoft\\DVR\\AppCompat"
0x1800029e0  mov     r9d, 1; samDesired
0x1800029e6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800029ed  call    cs:__imp_RegOpenKeyExW
0x1800029f3  test    eax, eax
0x1800029f5  jz      short loc_1800029FB
0x1800029f7  xor     al, al
0x1800029f9  jmp     short loc_180002A3A
0x1800029fb  mov     ecx, 4
0x180002a00  lea     r9, [rsp+48h+Type]; lpType
0x180002a05  mov     [rsp+48h+Type], ecx
0x180002a09  xor     r8d, r8d; lpReserved
0x180002a0c  mov     dword ptr [rsp+48h+cbData], ecx
0x180002a10  mov     rdx, rdi; lpValueName
0x180002a13  lea     rcx, [rsp+48h+cbData]
0x180002a18  mov     [rsp+48h+lpcbData], rcx; lpcbData
0x180002a1d  mov     rcx, [rsp+48h+hKey]; hKey
0x180002a22  mov     [rsp+48h+lpData], rbx; lpData
0x180002a27  call    cs:__imp_RegQueryValueExW
0x180002a2d  mov     rcx, [rsp+48h+hKey]; hKey
0x180002a32  call    cs:__imp_RegCloseKey
0x180002a38  mov     al, 1
0x180002a3a  mov     rbx, [rsp+48h+arg_8]
0x180002a3f  add     rsp, 40h
0x180002a43  pop     rdi
0x180002a44  retn
```
