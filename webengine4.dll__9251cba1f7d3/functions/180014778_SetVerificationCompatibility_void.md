# SetVerificationCompatibility(void)

- ea: `0x180014778`
- end: `0x180014829`
- name: `?SetVerificationCompatibility@@YAJXZ`
- size: `177`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016c88`

## callees

- `0x180014778`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18001481a`
- `ADVAPI32!RegCloseKey` at `0x18001481a`
- `ADVAPI32!RegOpenKeyExW` at `0x1800147b1`
- `ADVAPI32!RegOpenKeyExW` at `0x1800147b1`
- `ADVAPI32!RegQueryValueExW` at `0x1800147f3`
- `ADVAPI32!RegQueryValueExW` at `0x1800147f3`

## string_xrefs

- `0x1800147e7`: `VerificationCompatibility`

## pseudocode

```c
__int64 SetVerificationCompatibility(void)
{
  unsigned int v0; // ebx
  LSTATUS v1; // eax
  int v2; // ecx
  DWORD cbData; // [rsp+50h] [rbp+8h] BYREF
  DWORD Type; // [rsp+58h] [rbp+10h] BYREF
  int Data; // [rsp+60h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  v0 = 0;
  cbData = 4;
  hKey = 0;
  Type = 0;
  v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\ASP.NET", 0, 1u, &hKey);
  if ( v1 || (v1 = RegQueryValueExW(hKey, L"VerificationCompatibility", 0, &Type, (LPBYTE)&Data, &cbData)) != 0 )
  {
    v0 = (unsigned __int16)v1 | 0x80070000;
    if ( v1 <= 0 )
      v0 = v1;
  }
  else
  {
    v2 = g_fVerificationCompatibility;
    if ( Data )
      v2 = 1;
    g_fVerificationCompatibility = v2;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x180014778  mov     rax, rsp
0x18001477b  push    rbx
0x18001477c  push    rsi
0x18001477d  sub     rsp, 38h
0x180014781  xor     ebx, ebx
0x180014783  mov     dword ptr [rax+8], 4
0x18001478a  and     [rax+20h], rbx
0x18001478e  xor     r8d, r8d; ulOptions
0x180014791  and     [rax+10h], ebx
0x180014794  lea     rax, [rax+20h]
0x180014798  lea     rdx, aSoftwareMicros_9; "Software\\Microsoft\\ASP.NET"
0x18001479f  mov     [rsp+48h+phkResult], rax; phkResult
0x1800147a4  lea     esi, [rbx+1]
0x1800147a7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800147ae  mov     r9d, esi; samDesired
0x1800147b1  call    cs:__imp_RegOpenKeyExW
0x1800147b7  test    eax, eax
0x1800147b9  jz      short loc_1800147CB
0x1800147bb  movzx   ebx, ax
0x1800147be  or      ebx, 80070000h
0x1800147c4  test    eax, eax
0x1800147c6  cmovle  ebx, eax
0x1800147c9  jmp     short loc_180014810
0x1800147cb  mov     rcx, [rsp+48h+hKey]; hKey
0x1800147d0  lea     rax, [rsp+48h+cbData]
0x1800147d5  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800147da  lea     r9, [rsp+48h+Type]; lpType
0x1800147df  lea     rax, [rsp+48h+Data]
0x1800147e4  xor     r8d, r8d; lpReserved
0x1800147e7  lea     rdx, aVerificationco; "VerificationCompatibility"
0x1800147ee  mov     [rsp+48h+phkResult], rax; lpData
0x1800147f3  call    cs:__imp_RegQueryValueExW
0x1800147f9  test    eax, eax
0x1800147fb  jnz     short loc_1800147BB
0x1800147fd  mov     ecx, cs:?g_fVerificationCompatibility@@3HA; int g_fVerificationCompatibility
0x180014803  cmp     [rsp+48h+Data], ebx
0x180014807  cmovnz  ecx, esi
0x18001480a  mov     cs:?g_fVerificationCompatibility@@3HA, ecx; int g_fVerificationCompatibility
0x180014810  mov     rcx, [rsp+48h+hKey]; hKey
0x180014815  test    rcx, rcx
0x180014818  jz      short loc_180014820
0x18001481a  call    cs:__imp_RegCloseKey
0x180014820  mov     eax, ebx
0x180014822  add     rsp, 38h
0x180014826  pop     rsi
0x180014827  pop     rbx
0x180014828  retn
```
