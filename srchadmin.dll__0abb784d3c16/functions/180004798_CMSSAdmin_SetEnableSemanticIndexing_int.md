# CMSSAdmin::SetEnableSemanticIndexing(int)

- ea: `0x180004798`
- end: `0x18000483b`
- name: `?SetEnableSemanticIndexing@CMSSAdmin@@QEAAJH@Z`
- size: `163`
- prototype: `__int64 __fastcall(CMSSAdmin *__hidden this, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004360`

## callees

- `0x180004798`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004813`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004813`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800047d6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800047d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000482d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000482d`

## pseudocode

```c
__int64 __fastcall CMSSAdmin::SetEnableSemanticIndexing(CMSSAdmin *this, int a2)
{
  LSTATUS v2; // eax
  signed int v3; // ebx
  LSTATUS v4; // eax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF
  BOOL Data; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  Data = a2 != 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows Search\\SemanticIndexer", 0, 0xF003Fu, &hKey);
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( v3 >= 0 )
  {
    v4 = RegSetValueExW(hKey, L"EnableSemanticIndexing", 0, 4u, (const BYTE *)&Data, 4u);
    v3 = v4;
    if ( v4 > 0 )
      v3 = (unsigned __int16)v4 | 0x80070000;
    RegCloseKey(hKey);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180004798  mov     r11, rsp
0x18000479b  mov     [r11+8], rcx
0x18000479f  push    rbx
0x1800047a0  sub     rsp, 30h
0x1800047a4  xor     eax, eax
0x1800047a6  mov     qword ptr [r11+8], 0
0x1800047ae  test    edx, edx
0x1800047b0  mov     r9d, 0F003Fh; samDesired
0x1800047b6  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows Search\\Se"...
0x1800047bd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800047c4  setnz   al
0x1800047c7  xor     r8d, r8d; ulOptions
0x1800047ca  mov     [rsp+38h+Data], eax
0x1800047ce  lea     rax, [r11+8]
0x1800047d2  mov     [r11-18h], rax
0x1800047d6  call    cs:__imp_RegOpenKeyExW
0x1800047dc  mov     ebx, eax
0x1800047de  test    eax, eax
0x1800047e0  jle     short loc_1800047EB
0x1800047e2  movzx   ebx, ax
0x1800047e5  or      ebx, 80070000h
0x1800047eb  test    ebx, ebx
0x1800047ed  js      short loc_180004833
0x1800047ef  mov     rcx, [rsp+38h+hKey]; hKey
0x1800047f4  lea     rax, [rsp+38h+Data]
0x1800047f9  mov     r9d, 4; dwType
0x1800047ff  lea     rdx, ValueName; "EnableSemanticIndexing"
0x180004806  mov     [rsp+38h+cbData], r9d; cbData
0x18000480b  xor     r8d, r8d; Reserved
0x18000480e  mov     [rsp+38h+lpData], rax; lpData
0x180004813  call    cs:__imp_RegSetValueExW
0x180004819  mov     ebx, eax
0x18000481b  test    eax, eax
0x18000481d  jle     short loc_180004828
0x18000481f  movzx   ebx, ax
0x180004822  or      ebx, 80070000h
0x180004828  mov     rcx, [rsp+38h+hKey]; hKey
0x18000482d  call    cs:__imp_RegCloseKey
0x180004833  mov     eax, ebx
0x180004835  add     rsp, 30h
0x180004839  pop     rbx
0x18000483a  retn
```
