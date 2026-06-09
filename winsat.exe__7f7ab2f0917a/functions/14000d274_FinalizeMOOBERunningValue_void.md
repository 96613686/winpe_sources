# FinalizeMOOBERunningValue(void)

- ea: `0x14000d274`
- end: `0x14000d353`
- name: `?FinalizeMOOBERunningValue@@YAXXZ`
- size: `223`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001a54c`

## callees

- `0x14000d274`
- `0x14003ec14`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x14000d31a`
- `ADVAPI32!RegSetValueExW` at `0x14000d31a`
- `ADVAPI32!RegCreateKeyExW` at `0x14000d2c7`
- `ADVAPI32!RegCreateKeyExW` at `0x14000d2c7`
- `ADVAPI32!RegFlushKey` at `0x14000d325`
- `ADVAPI32!RegFlushKey` at `0x14000d325`
- `ADVAPI32!RegCloseKey` at `0x14000d330`
- `ADVAPI32!RegCloseKey` at `0x14000d330`

## string_xrefs

- `0x14000d2d4`: `ERROR: could not create MOOBE reg key during finalize. error = %u`

## pseudocode

```c
void FinalizeMOOBERunningValue(void)
{
  LSTATUS v0; // eax
  DWORD v1; // [rsp+60h] [rbp+8h] BYREF
  int Data; // [rsp+68h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  hKey = 0;
  v1 = 0;
  v0 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WinSAT",
         0,
         0,
         0,
         0xF003Fu,
         0,
         &hKey,
         &v1);
  if ( v0 )
  {
    Log_Text_F(
      "base\\winsat\\exe\\main.cpp",
      2337,
      "ERROR: could not create MOOBE reg key during finalize. error = %u",
      v0);
  }
  else
  {
    Data = 2;
    RegSetValueExW(hKey, L"MOOBE", 0, 4u, (const BYTE *)&Data, 4u);
    RegFlushKey(hKey);
    RegCloseKey(hKey);
    Log_Text_F("base\\winsat\\exe\\main.cpp", 2362, "> Finalized MOOBE key");
  }
}

```

## disassembly

```asm
0x14000d274  mov     r11, rsp
0x14000d277  sub     rsp, 58h
0x14000d27b  lea     rax, [r11+8]
0x14000d27f  mov     qword ptr [r11+18h], 0
0x14000d287  mov     [r11-18h], rax
0x14000d28b  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14000d292  lea     rax, [r11+18h]
0x14000d296  mov     [rsp+58h+arg_0], 0
0x14000d29e  mov     [r11-20h], rax
0x14000d2a2  xor     r9d, r9d; lpClass
0x14000d2a5  mov     qword ptr [r11-28h], 0
0x14000d2ad  xor     r8d, r8d; Reserved
0x14000d2b0  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x14000d2b8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000d2bf  mov     [rsp+58h+dwOptions], 0; dwOptions
0x14000d2c7  call    cs:__imp_RegCreateKeyExW
0x14000d2cd  test    eax, eax
0x14000d2cf  jz      short loc_14000D2EE
0x14000d2d1  mov     r9d, eax
0x14000d2d4  lea     r8, aErrorCouldNotC_0; "ERROR: could not create MOOBE reg key d"...
0x14000d2db  mov     edx, 921h
0x14000d2e0  lea     rcx, aBaseWinsatExeM; "base\\winsat\\exe\\main.cpp"
0x14000d2e7  call    Log_Text_F
0x14000d2ec  jmp     short loc_14000D34E
0x14000d2ee  mov     rcx, [rsp+58h+hKey]; hKey
0x14000d2f3  lea     rax, [rsp+58h+Data]
0x14000d2f8  mov     r9d, 4; dwType
0x14000d2fe  mov     [rsp+58h+Data], 2
0x14000d306  mov     [rsp+58h+samDesired], r9d; cbData
0x14000d30b  lea     rdx, ValueName; "MOOBE"
0x14000d312  xor     r8d, r8d; Reserved
0x14000d315  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x14000d31a  call    cs:__imp_RegSetValueExW
0x14000d320  mov     rcx, [rsp+58h+hKey]; hKey
0x14000d325  call    cs:__imp_RegFlushKey
0x14000d32b  mov     rcx, [rsp+58h+hKey]; hKey
0x14000d330  call    cs:__imp_RegCloseKey
0x14000d336  lea     r8, aFinalizedMoobe; "> Finalized MOOBE key"
0x14000d33d  mov     edx, 93Ah
0x14000d342  lea     rcx, aBaseWinsatExeM; "base\\winsat\\exe\\main.cpp"
0x14000d349  call    Log_Text_F
0x14000d34e  add     rsp, 58h
0x14000d352  retn
```
