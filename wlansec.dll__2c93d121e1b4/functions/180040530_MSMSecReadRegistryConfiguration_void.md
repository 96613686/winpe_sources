# MSMSecReadRegistryConfiguration(void)

- ea: `0x180040530`
- end: `0x18004067f`
- name: `?MSMSecReadRegistryConfiguration@@YAXXZ`
- size: `335`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003ae08`

## callees

- `0x180040530`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800405ba`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004061c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800405ba`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004061c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004066b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004066b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040562`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040562`

## pseudocode

```c
void MSMSecReadRegistryConfiguration(void)
{
  int v0; // ebx
  __int64 i; // rax
  int Data; // [rsp+50h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+20h] BYREF
  DWORD Type; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  hKey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Wlansvc", 0, 1u, &hKey) )
    hKey = 0;
  v0 = 0;
  Data = 0;
  Type = 0;
  if ( hKey )
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"ExtendedUIRequestTimeoutSeconds", 0, &Type, (LPBYTE)&Data, &cbData)
      && (unsigned int)(Data - 120) <= 0x30C )
    {
      v0 = Data;
    }
  }
  g_MSMSecRegistryConfig = v0;
  Data = 0;
  Type = 0;
  if ( hKey )
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"EnableWepTkipCipher", 0, &Type, (LPBYTE)&Data, &cbData) )
    {
      if ( Data )
      {
        for ( i = 0; i != 24; ++i )
        {
          if ( *((_DWORD *)&g_osCapabilities + 4 * i + 1) == 2 || *((_DWORD *)&g_osCapabilities + 4 * i + 1) == 257 )
            *((_DWORD *)&g_osCapabilities + 4 * i + 3) = 1;
        }
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x180040530  push    rbp
0x180040532  push    rbx
0x180040533  mov     rbp, rsp
0x180040536  sub     rsp, 38h
0x18004053a  lea     rax, [rbp+hKey]
0x18004053e  mov     [rbp+hKey], 0
0x180040546  mov     r9d, 1; samDesired
0x18004054c  mov     [rsp+38h+phkResult], rax; phkResult
0x180040551  xor     r8d, r8d; ulOptions
0x180040554  lea     rdx, SubKey; "Software\\Microsoft\\Wlansvc"
0x18004055b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180040562  call    cs:__imp_RegOpenKeyExW
0x180040569  nop     dword ptr [rax+rax+00h]
0x18004056e  test    eax, eax
0x180040570  jz      short loc_18004057A
0x180040572  mov     [rbp+hKey], 0
0x18004057a  mov     rcx, [rbp+hKey]; hKey
0x18004057e  xor     ebx, ebx
0x180040580  mov     [rbp+Data], 0
0x180040587  mov     [rbp+Type], 0
0x18004058e  test    rcx, rcx
0x180040591  jz      short loc_1800405D8
0x180040593  lea     rax, [rbp+cbData]
0x180040597  mov     [rbp+cbData], 4
0x18004059e  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800405a3  lea     r9, [rbp+Type]; lpType
0x1800405a7  lea     rax, [rbp+Data]
0x1800405ab  xor     r8d, r8d; lpReserved
0x1800405ae  lea     rdx, ValueName; "ExtendedUIRequestTimeoutSeconds"
0x1800405b5  mov     [rsp+38h+phkResult], rax; lpData
0x1800405ba  call    cs:__imp_RegQueryValueExW
0x1800405c1  nop     dword ptr [rax+rax+00h]
0x1800405c6  test    eax, eax
0x1800405c8  jnz     short loc_1800405D8
0x1800405ca  mov     ecx, [rbp+Data]
0x1800405cd  lea     eax, [rcx-78h]
0x1800405d0  cmp     eax, 30Ch
0x1800405d5  cmovbe  ebx, ecx
0x1800405d8  mov     rcx, [rbp+hKey]; hKey
0x1800405dc  mov     cs:?g_MSMSecRegistryConfig@@3U_MSMSEC_REGISTRY_CONFIGURATION@@A, ebx; _MSMSEC_REGISTRY_CONFIGURATION g_MSMSecRegistryConfig
0x1800405e2  mov     [rbp+Data], 0
0x1800405e9  mov     [rbp+Type], 0
0x1800405f0  test    rcx, rcx
0x1800405f3  jz      short loc_180040662
0x1800405f5  lea     rax, [rbp+cbData]
0x1800405f9  mov     [rbp+cbData], 4
0x180040600  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180040605  lea     r9, [rbp+Type]; lpType
0x180040609  lea     rax, [rbp+Data]
0x18004060d  xor     r8d, r8d; lpReserved
0x180040610  lea     rdx, aEnableweptkipc; "EnableWepTkipCipher"
0x180040617  mov     [rsp+38h+phkResult], rax; lpData
0x18004061c  call    cs:__imp_RegQueryValueExW
0x180040623  nop     dword ptr [rax+rax+00h]
0x180040628  test    eax, eax
0x18004062a  jnz     short loc_180040662
0x18004062c  cmp     [rbp+Data], eax
0x18004062f  jz      short loc_180040662
0x180040631  xor     eax, eax
0x180040633  lea     rdx, ?g_osCapabilities@@3PAUSUPPORTED_CAPABILITY_AUTH_CIPHER_1X@@A; SUPPORTED_CAPABILITY_AUTH_CIPHER_1X near * g_osCapabilities
0x18004063a  mov     rcx, rax
0x18004063d  add     rcx, rcx
0x180040640  cmp     dword ptr [rdx+rcx*8+4], 2
0x180040645  jz      short loc_180040651
0x180040647  cmp     dword ptr [rdx+rcx*8+4], 101h
0x18004064f  jnz     short loc_180040659
0x180040651  mov     dword ptr [rdx+rcx*8+0Ch], 1
0x180040659  inc     rax
0x18004065c  cmp     rax, 18h
0x180040660  jnz     short loc_18004063A
0x180040662  mov     rcx, [rbp+hKey]; hKey
0x180040666  test    rcx, rcx
0x180040669  jz      short loc_180040677
0x18004066b  call    cs:__imp_RegCloseKey
0x180040672  nop     dword ptr [rax+rax+00h]
0x180040677  add     rsp, 38h
0x18004067b  pop     rbx
0x18004067c  pop     rbp
0x18004067d  retn
```
