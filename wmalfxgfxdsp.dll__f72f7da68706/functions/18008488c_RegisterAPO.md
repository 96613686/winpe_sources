# RegisterAPO

- ea: `0x18008488c`
- end: `0x180084d5d`
- name: `RegisterAPO`
- size: `1233`
- prototype: `HRESULT __stdcall(const APO_REG_PROPERTIES *pProperties)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180079690`
- `0x1800796c0`
- `0x1800796f0`
- `0x180079710`

## callees

- `0x180015190`
- `0x1800847d4`
- `0x180084800`
- `0x18008488c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180084d1f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180084d2a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180084d1f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180084d2a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180084a0b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180084a6e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180084a9f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180084ad1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180084b00`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180084b32`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180084b64`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180084b96`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180084bc8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180084bfa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180084c2c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180084cc7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180084a0b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180084a6e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180084a9f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180084ad1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180084b00`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180084b32`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180084b64`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180084b96`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180084bc8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180084bfa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180084c2c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180084cc7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18008496b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18008496b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180084918`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18008499e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180084918`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18008499e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180084d0a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180084d0a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180084949`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180084c85`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180084949`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180084c85`

## string_xrefs

- `0x180084a58`: `Copyright`

## pseudocode

```c
HRESULT __stdcall RegisterAPO(const APO_REG_PROPERTIES *pProperties)
{
  HRESULT v2; // ebx
  LSTATUS v3; // eax
  LSTATUS v4; // eax
  __int64 v5; // rsi
  __int64 v6; // rax
  unsigned __int64 v7; // rax
  LSTATUS v8; // eax
  bool v9; // cc
  unsigned __int64 v10; // rsi
  __int64 v11; // rcx
  UINT32 i; // esi
  int v13; // eax
  unsigned __int64 v14; // rax
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE *v18; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v19; // [rsp+68h] [rbp-98h] BYREF
  OLECHAR sz[512]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR ValueName[512]; // [rsp+470h] [rbp+370h] BYREF

  hKey = 0;
  phkResult = 0;
  v18 = 0;
  if ( !pProperties )
    return -2147467261;
  v3 = RegCreateKeyExW(HKEY_CLASSES_ROOT, L"AudioEngine\\AudioProcessingObjects", 0, 0, 0, 0x20006u, 0, &hKey, 0);
  v2 = v3;
  if ( !v3 )
  {
    if ( !StringFromGUID2(&pProperties->clsid, sz, 512) )
    {
      v2 = 0;
LABEL_44:
      RegCloseKey(hKey);
      return v2;
    }
    RegDeleteKeyExW(hKey, sz, 0, 0);
    v4 = RegCreateKeyExW(hKey, sz, 0, 0, 0, 0x20006u, 0, &phkResult, 0);
    v2 = v4;
    if ( v4 )
    {
      if ( v4 > 0 )
        v2 = (unsigned __int16)v4 | 0x80070000;
      goto LABEL_44;
    }
    v5 = -1;
    v6 = -1;
    do
      ++v6;
    while ( pProperties->szFriendlyName[v6] );
    v7 = 2 * v6 + 2;
    if ( v7 > 0x200 )
    {
      v2 = -2147024809;
      goto LABEL_44;
    }
    v8 = RegSetValueExW(phkResult, L"FriendlyName", 0, 1u, (const BYTE *)pProperties->szFriendlyName, v7);
    v2 = v8;
    v9 = v8 <= 0;
    if ( !v8 )
    {
      do
        ++v5;
      while ( pProperties->szCopyrightInfo[v5] );
      v10 = 2 * v5 + 2;
      if ( v10 > 0x200 )
      {
LABEL_20:
        v2 = -2147024809;
LABEL_43:
        RegCloseKey(phkResult);
        goto LABEL_44;
      }
      v8 = RegSetValueExW(phkResult, L"Copyright", 0, 1u, (const BYTE *)pProperties->szCopyrightInfo, v10);
      v2 = v8;
      v9 = v8 <= 0;
      if ( !v8 )
      {
        v8 = RegSetValueExW(phkResult, L"MajorVersion", 0, 4u, (const BYTE *)&pProperties->u32MajorVersion, 4u);
        v2 = v8;
        v9 = v8 <= 0;
        if ( !v8 )
        {
          v8 = RegSetValueExW(phkResult, L"MinorVersion", 0, 4u, (const BYTE *)&pProperties->u32MinorVersion, 4u);
          v2 = v8;
          v9 = v8 <= 0;
          if ( !v8 )
          {
            v8 = RegSetValueExW(phkResult, L"Flags", 0, 4u, (const BYTE *)&pProperties->Flags, 4u);
            v2 = v8;
            v9 = v8 <= 0;
            if ( !v8 )
            {
              v8 = RegSetValueExW(
                     phkResult,
                     L"MinInputConnections",
                     0,
                     4u,
                     (const BYTE *)&pProperties->u32MinInputConnections,
                     4u);
              v2 = v8;
              v9 = v8 <= 0;
              if ( !v8 )
              {
                v8 = RegSetValueExW(
                       phkResult,
                       L"MaxInputConnections",
                       0,
                       4u,
                       (const BYTE *)&pProperties->u32MaxInputConnections,
                       4u);
                v2 = v8;
                v9 = v8 <= 0;
                if ( !v8 )
                {
                  v8 = RegSetValueExW(
                         phkResult,
                         L"MinOutputConnections",
                         0,
                         4u,
                         (const BYTE *)&pProperties->u32MinOutputConnections,
                         4u);
                  v2 = v8;
                  v9 = v8 <= 0;
                  if ( !v8 )
                  {
                    v8 = RegSetValueExW(
                           phkResult,
                           L"MaxOutputConnections",
                           0,
                           4u,
                           (const BYTE *)&pProperties->u32MaxOutputConnections,
                           4u);
                    v2 = v8;
                    v9 = v8 <= 0;
                    if ( !v8 )
                    {
                      v8 = RegSetValueExW(
                             phkResult,
                             L"MaxInstances",
                             0,
                             4u,
                             (const BYTE *)&pProperties->u32MaxInstances,
                             4u);
                      v2 = v8;
                      v9 = v8 <= 0;
                      if ( !v8 )
                      {
                        v8 = RegSetValueExW(
                               phkResult,
                               L"NumAPOInterfaces",
                               0,
                               4u,
                               (const BYTE *)&pProperties->u32NumAPOInterfaces,
                               4u);
                        v2 = v8;
                        v9 = v8 <= 0;
                        if ( !v8 )
                        {
                          for ( i = 0; i < pProperties->u32NumAPOInterfaces; ++i )
                          {
                            v2 = StringCbPrintfW(ValueName, 0x400u, L"APOInterface%u", i);
                            if ( v2 < 0 )
                              return v2;
                            v13 = StringFromGUID2(&pProperties->iidAPOInterfaceList[i], sz, 512);
                            if ( !v13 )
                              goto LABEL_42;
                            v14 = 2LL * v13;
                            if ( v14 > 0x400 )
                              goto LABEL_20;
                            v8 = RegSetValueExW(phkResult, ValueName, 0, 1u, (const BYTE *)sz, v14);
                            v2 = v8;
                            v9 = v8 <= 0;
                            if ( v8 )
                              goto LABEL_16;
                          }
                          v19 = qword_1801B95F8;
                          while ( v19 )
                          {
                            if ( (unsigned int)TList<APOHandle>::GetNext(v11, &v19, &v18) )
                              SetEvent(*v18);
                          }
LABEL_42:
                          v2 = 0;
                          goto LABEL_43;
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
LABEL_16:
    if ( !v9 )
      v2 = (unsigned __int16)v8 | 0x80070000;
    goto LABEL_43;
  }
  if ( v3 > 0 )
    return (unsigned __int16)v3 | 0x80070000;
  return v2;
}

```

## disassembly

```asm
0x18008488c  mov     [rsp-8+arg_8], rbx
0x180084891  mov     [rsp-8+arg_10], rsi
0x180084896  push    rbp
0x180084897  push    rdi
0x180084898  push    r13
0x18008489a  push    r14
0x18008489c  push    r15
0x18008489e  lea     rbp, [rsp-780h]
0x1800848a6  sub     rsp, 880h
0x1800848ad  mov     rax, cs:__security_cookie
0x1800848b4  xor     rax, rsp
0x1800848b7  mov     [rbp+7A0h+var_30], rax
0x1800848be  xor     r15d, r15d
0x1800848c1  mov     rdi, rcx
0x1800848c4  mov     [rsp+8A0h+hKey], r15
0x1800848c9  mov     [rsp+8A0h+var_850], r15
0x1800848ce  mov     [rsp+8A0h+var_840], r15
0x1800848d3  test    rcx, rcx
0x1800848d6  jnz     short loc_1800848E2
0x1800848d8  mov     ebx, 80004003h
0x1800848dd  jmp     loc_180084D30
0x1800848e2  mov     [rsp+8A0h+lpdwDisposition], r15; lpdwDisposition
0x1800848e7  lea     rax, [rsp+8A0h+hKey]
0x1800848ec  mov     [rsp+8A0h+phkResult], rax; phkResult
0x1800848f1  lea     rdx, SubKey; "AudioEngine\\AudioProcessingObjects"
0x1800848f8  mov     [rsp+8A0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x1800848fd  mov     esi, 20006h
0x180084902  mov     [rsp+8A0h+samDesired], esi; samDesired
0x180084906  xor     r9d, r9d; lpClass
0x180084909  xor     r8d, r8d; Reserved
0x18008490c  mov     [rsp+8A0h+dwOptions], r15d; dwOptions
0x180084911  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180084918  call    cs:__imp_RegCreateKeyExW
0x18008491e  mov     ebx, eax
0x180084920  test    eax, eax
0x180084922  jz      short loc_180084938
0x180084924  jle     loc_180084D30
0x18008492a  movzx   ebx, ax
0x18008492d  or      ebx, 80070000h
0x180084933  jmp     loc_180084D30
0x180084938  mov     r13d, 200h
0x18008493e  lea     rdx, [rsp+8A0h+sz]; lpsz
0x180084943  mov     r8d, r13d; cchMax
0x180084946  mov     rcx, rdi; rguid
0x180084949  call    cs:__imp_StringFromGUID2
0x18008494f  test    eax, eax
0x180084951  jnz     short loc_18008495B
0x180084953  mov     ebx, r15d
0x180084956  jmp     loc_180084D25
0x18008495b  mov     rcx, [rsp+8A0h+hKey]; hKey
0x180084960  lea     rdx, [rsp+8A0h+sz]; lpSubKey
0x180084965  xor     r9d, r9d; Reserved
0x180084968  xor     r8d, r8d; samDesired
0x18008496b  call    cs:__imp_RegDeleteKeyExW
0x180084971  mov     rcx, [rsp+8A0h+hKey]; hKey
0x180084976  lea     rax, [rsp+8A0h+var_850]
0x18008497b  mov     [rsp+8A0h+lpdwDisposition], r15; lpdwDisposition
0x180084980  lea     rdx, [rsp+8A0h+sz]; lpSubKey
0x180084985  mov     [rsp+8A0h+phkResult], rax; phkResult
0x18008498a  xor     r9d, r9d; lpClass
0x18008498d  mov     [rsp+8A0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180084992  xor     r8d, r8d; Reserved
0x180084995  mov     [rsp+8A0h+samDesired], esi; samDesired
0x180084999  mov     [rsp+8A0h+dwOptions], r15d; dwOptions
0x18008499e  call    cs:__imp_RegCreateKeyExW
0x1800849a4  mov     ebx, eax
0x1800849a6  test    eax, eax
0x1800849a8  jz      short loc_1800849BE
0x1800849aa  jle     loc_180084D25
0x1800849b0  movzx   ebx, ax
0x1800849b3  or      ebx, 80070000h
0x1800849b9  jmp     loc_180084D25
0x1800849be  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800849c2  lea     rcx, [rdi+14h]
0x1800849c6  mov     rax, rsi
0x1800849c9  inc     rax
0x1800849cc  cmp     [rcx+rax*2], r15w
0x1800849d1  jnz     short loc_1800849C9
0x1800849d3  lea     rax, ds:2[rax*2]
0x1800849db  cmp     rax, r13
0x1800849de  jbe     short loc_1800849EA
0x1800849e0  mov     ebx, 80070057h
0x1800849e5  jmp     loc_180084D25
0x1800849ea  mov     [rsp+8A0h+samDesired], eax; cbData
0x1800849ee  lea     rdx, aFriendlyname; "FriendlyName"
0x1800849f5  mov     qword ptr [rsp+8A0h+dwOptions], rcx; lpData
0x1800849fa  mov     r14d, 1
0x180084a00  mov     rcx, [rsp+8A0h+var_850]; hKey
0x180084a05  mov     r9d, r14d; dwType
0x180084a08  xor     r8d, r8d; Reserved
0x180084a0b  call    cs:__imp_RegSetValueExW
0x180084a11  mov     ebx, eax
0x180084a13  test    eax, eax
0x180084a15  jz      short loc_180084A2B
0x180084a17  jle     loc_180084D1A
0x180084a1d  movzx   ebx, ax
0x180084a20  or      ebx, 80070000h
0x180084a26  jmp     loc_180084D1A
0x180084a2b  lea     rax, [rdi+214h]
0x180084a32  inc     rsi
0x180084a35  cmp     [rax+rsi*2], r15w
0x180084a3a  jnz     short loc_180084A32
0x180084a3c  lea     rsi, ds:2[rsi*2]
0x180084a44  cmp     rsi, r13
0x180084a47  jbe     short loc_180084A53
0x180084a49  mov     ebx, 80070057h
0x180084a4e  jmp     loc_180084D1A
0x180084a53  mov     rcx, [rsp+8A0h+var_850]; hKey
0x180084a58  lea     rdx, aCopyright; "Copyright"
0x180084a5f  mov     [rsp+8A0h+samDesired], esi; cbData
0x180084a63  mov     r9d, r14d; dwType
0x180084a66  xor     r8d, r8d; Reserved
0x180084a69  mov     qword ptr [rsp+8A0h+dwOptions], rax; lpData
0x180084a6e  call    cs:__imp_RegSetValueExW
0x180084a74  mov     ebx, eax
0x180084a76  test    eax, eax
0x180084a78  jnz     short loc_180084A17
0x180084a7a  mov     rcx, [rsp+8A0h+var_850]; hKey
0x180084a7f  lea     esi, [rbx+4]
0x180084a82  lea     rax, [rdi+414h]
0x180084a89  mov     [rsp+8A0h+samDesired], esi; cbData
0x180084a8d  mov     r9d, esi; dwType
0x180084a90  mov     qword ptr [rsp+8A0h+dwOptions], rax; lpData
0x180084a95  xor     r8d, r8d; Reserved
0x180084a98  lea     rdx, aMajorversion; "MajorVersion"
0x180084a9f  call    cs:__imp_RegSetValueExW
0x180084aa5  mov     ebx, eax
0x180084aa7  test    eax, eax
0x180084aa9  jnz     loc_180084A17
0x180084aaf  mov     rcx, [rsp+8A0h+var_850]; hKey
0x180084ab4  lea     rax, [rdi+418h]
0x180084abb  mov     [rsp+8A0h+samDesired], esi; cbData
0x180084abf  lea     rdx, aMinorversion; "MinorVersion"
0x180084ac6  mov     r9d, esi; dwType
0x180084ac9  mov     qword ptr [rsp+8A0h+dwOptions], rax; lpData
0x180084ace  xor     r8d, r8d; Reserved
0x180084ad1  call    cs:__imp_RegSetValueExW
0x180084ad7  mov     ebx, eax
0x180084ad9  test    eax, eax
0x180084adb  jnz     loc_180084A17
0x180084ae1  mov     rcx, [rsp+8A0h+var_850]; hKey
0x180084ae6  lea     rax, [rdi+10h]
0x180084aea  mov     [rsp+8A0h+samDesired], esi; cbData
0x180084aee  lea     rdx, aFlags; "Flags"
0x180084af5  mov     r9d, esi; dwType
0x180084af8  mov     qword ptr [rsp+8A0h+dwOptions], rax; lpData
0x180084afd  xor     r8d, r8d; Reserved
0x180084b00  call    cs:__imp_RegSetValueExW
0x180084b06  mov     ebx, eax
0x180084b08  test    eax, eax
0x180084b0a  jnz     loc_180084A17
0x180084b10  mov     rcx, [rsp+8A0h+var_850]; hKey
0x180084b15  lea     rax, [rdi+41Ch]
0x180084b1c  mov     [rsp+8A0h+samDesired], esi; cbData
0x180084b20  lea     rdx, aMininputconnec; "MinInputConnections"
0x180084b27  mov     r9d, esi; dwType
0x180084b2a  mov     qword ptr [rsp+8A0h+dwOptions], rax; lpData
0x180084b2f  xor     r8d, r8d; Reserved
0x180084b32  call    cs:__imp_RegSetValueExW
0x180084b38  mov     ebx, eax
0x180084b3a  test    eax, eax
0x180084b3c  jnz     loc_180084A17
0x180084b42  mov     rcx, [rsp+8A0h+var_850]; hKey
0x180084b47  lea     rax, [rdi+420h]
0x180084b4e  mov     [rsp+8A0h+samDesired], esi; cbData
0x180084b52  lea     rdx, aMaxinputconnec; "MaxInputConnections"
0x180084b59  mov     r9d, esi; dwType
0x180084b5c  mov     qword ptr [rsp+8A0h+dwOptions], rax; lpData
0x180084b61  xor     r8d, r8d; Reserved
0x180084b64  call    cs:__imp_RegSetValueExW
0x180084b6a  mov     ebx, eax
0x180084b6c  test    eax, eax
0x180084b6e  jnz     loc_180084A17
0x180084b74  mov     rcx, [rsp+8A0h+var_850]; hKey
0x180084b79  lea     rax, [rdi+424h]
0x180084b80  mov     [rsp+8A0h+samDesired], esi; cbData
0x180084b84  lea     rdx, aMinoutputconne; "MinOutputConnections"
0x180084b8b  mov     r9d, esi; dwType
0x180084b8e  mov     qword ptr [rsp+8A0h+dwOptions], rax; lpData
0x180084b93  xor     r8d, r8d; Reserved
0x180084b96  call    cs:__imp_RegSetValueExW
0x180084b9c  mov     ebx, eax
0x180084b9e  test    eax, eax
0x180084ba0  jnz     loc_180084A17
0x180084ba6  mov     rcx, [rsp+8A0h+var_850]; hKey
0x180084bab  lea     rax, [rdi+428h]
0x180084bb2  mov     [rsp+8A0h+samDesired], esi; cbData
0x180084bb6  lea     rdx, aMaxoutputconne; "MaxOutputConnections"
0x180084bbd  mov     r9d, esi; dwType
0x180084bc0  mov     qword ptr [rsp+8A0h+dwOptions], rax; lpData
0x180084bc5  xor     r8d, r8d; Reserved
0x180084bc8  call    cs:__imp_RegSetValueExW
0x180084bce  mov     ebx, eax
0x180084bd0  test    eax, eax
0x180084bd2  jnz     loc_180084A17
0x180084bd8  mov     rcx, [rsp+8A0h+var_850]; hKey
0x180084bdd  lea     rax, [rdi+42Ch]
0x180084be4  mov     [rsp+8A0h+samDesired], esi; cbData
0x180084be8  lea     rdx, aMaxinstances; "MaxInstances"
0x180084bef  mov     r9d, esi; dwType
0x180084bf2  mov     qword ptr [rsp+8A0h+dwOptions], rax; lpData
0x180084bf7  xor     r8d, r8d; Reserved
0x180084bfa  call    cs:__imp_RegSetValueExW
0x180084c00  mov     ebx, eax
0x180084c02  test    eax, eax
0x180084c04  jnz     loc_180084A17
0x180084c0a  mov     rcx, [rsp+8A0h+var_850]; hKey
0x180084c0f  lea     r14, [rdi+430h]
0x180084c16  mov     [rsp+8A0h+samDesired], esi; cbData
0x180084c1a  lea     rdx, aNumapointerfac; "NumAPOInterfaces"
0x180084c21  mov     r9d, esi; dwType
0x180084c24  mov     qword ptr [rsp+8A0h+dwOptions], r14; lpData
0x180084c29  xor     r8d, r8d; Reserved
0x180084c2c  call    cs:__imp_RegSetValueExW
0x180084c32  mov     ebx, eax
0x180084c34  test    eax, eax
0x180084c36  jnz     loc_180084A17
0x180084c3c  mov     esi, r15d
0x180084c3f  cmp     esi, [r14]
0x180084c42  jnb     loc_180084CDE
0x180084c48  mov     r9d, esi
0x180084c4b  lea     r8, aApointerfaceU; "APOInterface%u"
0x180084c52  mov     edx, 400h; unsigned __int64
0x180084c57  lea     rcx, [rbp+7A0h+ValueName]; unsigned __int16 *
0x180084c5e  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180084c63  mov     ebx, eax
0x180084c65  test    eax, eax
0x180084c67  js      loc_180084D30
0x180084c6d  mov     ecx, esi
0x180084c6f  lea     rdx, [rsp+8A0h+sz]; lpsz
0x180084c74  shl     rcx, 4
0x180084c78  mov     r8d, r13d; cchMax
0x180084c7b  add     rcx, 434h
0x180084c82  add     rcx, rdi; rguid
0x180084c85  call    cs:__imp_StringFromGUID2
0x180084c8b  test    eax, eax
0x180084c8d  jz      loc_180084D17
0x180084c93  cdqe
0x180084c95  add     rax, rax
0x180084c98  cmp     rax, 400h
0x180084c9e  ja      loc_180084A49
0x180084ca4  mov     rcx, [rsp+8A0h+var_850]; hKey
0x180084ca9  lea     rdx, [rbp+7A0h+ValueName]; lpValueName
0x180084cb0  mov     [rsp+8A0h+samDesired], eax; cbData
0x180084cb4  mov     r9d, 1; dwType
0x180084cba  lea     rax, [rsp+8A0h+sz]
0x180084cbf  xor     r8d, r8d; Reserved
0x180084cc2  mov     qword ptr [rsp+8A0h+dwOptions], rax; lpData
0x180084cc7  call    cs:__imp_RegSetValueExW
0x180084ccd  mov     ebx, eax
0x180084ccf  test    eax, eax
0x180084cd1  jnz     loc_180084A17
0x180084cd7  inc     esi
0x180084cd9  jmp     loc_180084C3F
0x180084cde  mov     rax, cs:qword_1801B95F8
0x180084ce5  mov     [rsp+8A0h+var_838], rax
0x180084cea  test    rax, rax
0x180084ced  jz      short loc_180084D17
0x180084cef  lea     r8, [rsp+8A0h+var_840]
0x180084cf4  lea     rdx, [rsp+8A0h+var_838]
0x180084cf9  call    ?GetNext@?$TList@UAPOHandle@@@@QEBAHAEAPEAXPEAPEAUAPOHandle@@@Z; TList<APOHandle>::GetNext(void * &,APOHandle * *)
0x180084cfe  test    eax, eax
0x180084d00  jz      short loc_180084D10
0x180084d02  mov     rcx, [rsp+8A0h+var_840]
0x180084d07  mov     rcx, [rcx]; hEvent
0x180084d0a  call    cs:__imp_SetEvent
0x180084d10  cmp     [rsp+8A0h+var_838], r15
0x180084d15  jnz     short loc_180084CEF
0x180084d17  mov     ebx, r15d
0x180084d1a  mov     rcx, [rsp+8A0h+var_850]; hKey
0x180084d1f  call    cs:__imp_RegCloseKey
0x180084d25  mov     rcx, [rsp+8A0h+hKey]; hKey
0x180084d2a  call    cs:__imp_RegCloseKey
0x180084d30  mov     eax, ebx
0x180084d32  mov     rcx, [rbp+7A0h+var_30]
0x180084d39  xor     rcx, rsp; StackCookie
0x180084d3c  call    __security_check_cookie
0x180084d41  lea     r11, [rsp+8A0h+var_20]
0x180084d49  mov     rbx, [r11+38h]
0x180084d4d  mov     rsi, [r11+40h]
0x180084d51  mov     rsp, r11
0x180084d54  pop     r15
0x180084d56  pop     r14
0x180084d58  pop     r13
0x180084d5a  pop     rdi
0x180084d5b  pop     rbp
0x180084d5c  retn
```
