# CMSSAdmin::GetEnableSemanticIndexing(int *)

- ea: `0x1800039f4`
- end: `0x180003abf`
- name: `?GetEnableSemanticIndexing@CMSSAdmin@@QEAAJPEAH@Z`
- size: `203`
- prototype: `__int64 __fastcall(CMSSAdmin *__hidden this, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019dcc`

## callees

- `0x1800039f4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003a94`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003a94`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003a4b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003a4b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003ab0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003ab0`

## pseudocode

```c
__int64 __fastcall CMSSAdmin::GetEnableSemanticIndexing(CMSSAdmin *this, int *a2)
{
  LSTATUS v4; // eax
  int v5; // ebx
  CMSSAdmin *Data; // [rsp+50h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+10h] BYREF
  DWORD Type; // [rsp+60h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  Data = this;
  if ( !a2 )
    return 2147942487LL;
  hKey = 0;
  LODWORD(Data) = 0;
  cbData = 4;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows Search\\SemanticIndexer", 0, 0x20119u, &hKey);
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  if ( v5 >= 0 )
  {
    Type = 0;
    v5 = RegQueryValueExW(hKey, L"EnableSemanticIndexing", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( v5 >= 0 )
      *a2 = (_DWORD)Data != 0;
    RegCloseKey(hKey);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800039f4  mov     [rsp+Data], rcx
0x1800039f9  push    rbx
0x1800039fa  push    rdi
0x1800039fb  sub     rsp, 38h
0x1800039ff  mov     rdi, rdx
0x180003a02  test    rdx, rdx
0x180003a05  jnz     short loc_180003A11
0x180003a07  mov     eax, 80070057h
0x180003a0c  jmp     loc_180003AB8
0x180003a11  lea     rax, [rsp+48h+hKey]
0x180003a16  mov     [rsp+48h+hKey], 0
0x180003a1f  mov     r9d, 20119h; samDesired
0x180003a25  mov     [rsp+48h+phkResult], rax; phkResult
0x180003a2a  xor     r8d, r8d; ulOptions
0x180003a2d  mov     dword ptr [rsp+48h+Data], 0
0x180003a35  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows Search\\Se"...
0x180003a3c  mov     [rsp+48h+cbData], 4
0x180003a44  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180003a4b  call    cs:__imp_RegOpenKeyExW
0x180003a51  mov     ebx, eax
0x180003a53  test    eax, eax
0x180003a55  jle     short loc_180003A60
0x180003a57  movzx   ebx, ax
0x180003a5a  or      ebx, 80070000h
0x180003a60  test    ebx, ebx
0x180003a62  js      short loc_180003AB6
0x180003a64  mov     rcx, [rsp+48h+hKey]; hKey
0x180003a69  lea     rax, [rsp+48h+cbData]
0x180003a6e  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180003a73  lea     r9, [rsp+48h+Type]; lpType
0x180003a78  lea     rax, [rsp+48h+Data]
0x180003a7d  mov     [rsp+48h+Type], 0
0x180003a85  xor     r8d, r8d; lpReserved
0x180003a88  mov     [rsp+48h+phkResult], rax; lpData
0x180003a8d  lea     rdx, ValueName; "EnableSemanticIndexing"
0x180003a94  call    cs:__imp_RegQueryValueExW
0x180003a9a  mov     ebx, eax
0x180003a9c  test    eax, eax
0x180003a9e  js      short loc_180003AAB
0x180003aa0  xor     ecx, ecx
0x180003aa2  cmp     dword ptr [rsp+48h+Data], ecx
0x180003aa6  setnz   cl
0x180003aa9  mov     [rdi], ecx
0x180003aab  mov     rcx, [rsp+48h+hKey]; hKey
0x180003ab0  call    cs:__imp_RegCloseKey
0x180003ab6  mov     eax, ebx
0x180003ab8  add     rsp, 38h
0x180003abc  pop     rdi
0x180003abd  pop     rbx
0x180003abe  retn
```
