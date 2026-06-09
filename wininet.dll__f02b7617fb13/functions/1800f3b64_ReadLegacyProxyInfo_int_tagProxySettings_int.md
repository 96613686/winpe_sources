# ReadLegacyProxyInfo(int *,tagProxySettings *,int *)

- ea: `0x1800f3b64`
- end: `0x1800f4084`
- name: `?ReadLegacyProxyInfo@@YAHPEAHPEAUtagProxySettings@@0@Z`
- size: `1312`
- prototype: `__int64 __fastcall(int *, struct tagProxySettings *, int *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180006ed0`
- `0x1800073c0`

## callees

- `0x180009cf0`
- `0x1800c14f4`
- `0x1800f3b64`
- `0x1800f408c`
- `0x1800f40d4`
- `0x18014a7a0`
- `0x18014b3b4`
- `0x1801b1b2c`
- `0x1801d1f2c`
- `0x1801e1790`
- `0x1801e3c24`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800f3e69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800f3e69`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800f3c91`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800f3c91`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800f3cc9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800f3d48`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800f3db1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800f3e17`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800f3ef5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800f3cc9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800f3d48`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800f3db1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800f3e17`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800f3ef5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f3cff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f3d6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f3dd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f3cff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f3d6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f3dd1`

## string_xrefs

- `0x1800f3e00`: `AutoConfigURL`

## pseudocode

```c
__int64 __fastcall ReadLegacyProxyInfo(int *a1, struct tagProxySettings *a2, int *a3)
{
  unsigned int v6; // r15d
  _WORD *v7; // rsi
  _WORD *v8; // rdi
  _WORD *v9; // rbx
  struct CRefdKey *BaseProxyKey; // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  HKEY *v14; // r13
  LSTATUS v15; // eax
  void *v16; // rax
  void *v17; // r15
  _WORD *v18; // rax
  _WORD *v19; // rax
  LSTATUS v21; // eax
  int v22; // r9d
  const wchar_t *v23; // rdx
  const wchar_t *v24; // rcx
  const wchar_t *v25; // rax
  __int64 v26; // rcx
  int PersistedRegistryLocation; // eax
  BOOL v28; // [rsp+54h] [rbp-ACh]
  void *v29; // [rsp+60h] [rbp-A0h] BYREF
  void *v30; // [rsp+68h] [rbp-98h] BYREF
  void *v31; // [rsp+70h] [rbp-90h] BYREF
  int *v32; // [rsp+78h] [rbp-88h]
  DWORD cbData; // [rsp+80h] [rbp-80h] BYREF
  BYTE Data[4]; // [rsp+84h] [rbp-7Ch] BYREF
  HKEY hKey; // [rsp+88h] [rbp-78h] BYREF
  DWORD Type[4]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR SubKey[60]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v38[408]; // [rsp+118h] [rbp+18h] BYREF

  wcscpy(SubKey, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings");
  v6 = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v32 = a1;
  cbData = 0;
  *(_DWORD *)Data = 0;
  Type[0] = 0;
  hKey = 0;
  v31 = 0;
  v30 = 0;
  v29 = 0;
  memset_0(v38, 0, 0x190u);
  if ( (xmmword_180266B60 & 0x10) != 0 )
    WPP_SF_q(1028, 16, WPP_ffb36679dc07312dd2ab286372984303_Traceguids, a2);
  *a1 = 0;
  if ( a3 )
    *a3 = 0;
  *((_DWORD *)a2 + 1) = 1;
  BaseProxyKey = FindBaseProxyKey();
  v14 = (HKEY *)BaseProxyKey;
  if ( BaseProxyKey )
  {
    if ( *((_QWORD *)BaseProxyKey + 1) == -2147483646 )
    {
      PersistedRegistryLocation = WxGetPersistedRegistryLocation(v12, v11, v13, SubKey);
      if ( PersistedRegistryLocation < 0 )
      {
        v26 = (unsigned int)PersistedRegistryLocation;
LABEL_53:
        WX_WIN32_FROM_HR(v26);
        goto LABEL_17;
      }
    }
    if ( RegOpenKeyExW(v14[1], SubKey, 0, 0x20019u, &hKey) )
      goto LABEL_17;
    cbData = 4;
    v15 = RegQueryValueExW(hKey, L"ProxyEnable", 0, 0, Data, &cbData);
    if ( (v15 & 0xFFFFFFFD) != 0 )
      goto LABEL_17;
    v28 = v15 == 2;
    if ( *(_DWORD *)Data )
      *((_DWORD *)a2 + 1) |= 2u;
    cbData = 4168;
    v16 = CoTaskMemAlloc(0x1048u);
    v17 = v16;
    if ( v16 )
    {
      memset_0(v16, 0, 0x1048u);
      v31 = v17;
      v7 = v17;
      if ( (RegQueryValueExW(hKey, L"ProxyServer", 0, 0, (LPBYTE)v17, &cbData) & 0xFFFFFFFD) != 0 )
        goto LABEL_31;
      v6 = 0;
      cbData = 4168;
      v18 = CoTaskMemAlloc(0x1048u);
      v8 = v18;
      if ( v18 )
      {
        memset_0(v18, 0, 0x1048u);
        v30 = v8;
        if ( (RegQueryValueExW(hKey, L"ProxyOverride", 0, 0, (LPBYTE)v8, &cbData) & 0xFFFFFFFD) == 0 )
        {
          cbData = 4168;
          v19 = CoTaskMemAlloc(0x1048u);
          v9 = v19;
          if ( v19 )
          {
            memset_0(v19, 0, 0x1048u);
            v29 = v9;
            if ( (RegQueryValueExW(hKey, L"AutoConfigURL", 0, 0, (LPBYTE)v9, &cbData) & 0xFFFFFFFD) == 0 )
            {
              cbData = 4;
              v21 = RegQueryValueExW(hKey, L"AutoDetect", 0, Type, Data, &cbData);
              if ( (v21 & 0xFFFFFFFD) == 0 )
              {
                v22 = 0;
                if ( !v21 && Type[0] == 4 )
                {
                  v22 = 1;
                  if ( *(_DWORD *)Data )
                    *((_DWORD *)a2 + 1) |= 8u;
                }
                if ( *v7 )
                {
                  *((_QWORD *)a2 + 3) = v7;
                  v7 = 0;
                  v31 = 0;
                }
                if ( *v8 )
                {
                  *((_QWORD *)a2 + 4) = v8;
                  v8 = 0;
                  v30 = 0;
                }
                if ( *v9 )
                {
                  *((_DWORD *)a2 + 1) |= 4u;
                  *((_QWORD *)a2 + 5) = v9;
                  v9 = 0;
                  v29 = 0;
                }
                if ( !*((_DWORD *)a2 + 2) )
                  *((_DWORD *)a2 + 2) = 1;
                *v32 = v22;
                if ( a3 )
                  *a3 = v28;
                v6 = 1;
                if ( (xmmword_180266B60 & 0x10) != 0 )
                {
                  v23 = L"<none>";
                  v24 = L"<none>";
                  v25 = L"<none>";
                  if ( *((_QWORD *)a2 + 5) )
                    v24 = (const wchar_t *)*((_QWORD *)a2 + 5);
                  if ( *((_QWORD *)a2 + 4) )
                    v25 = (const wchar_t *)*((_QWORD *)a2 + 4);
                  if ( *((_QWORD *)a2 + 3) )
                    v23 = (const wchar_t *)*((_QWORD *)a2 + 3);
                  WPP_SF_llDSSS(
                    (_DWORD)v24,
                    (_DWORD)v23,
                    v28,
                    v22,
                    v28,
                    *((_DWORD *)a2 + 1),
                    (__int64)v23,
                    (__int64)v25,
                    (__int64)v24);
                }
              }
            }
            goto LABEL_17;
          }
          v9 = 0;
          v29 = 0;
          v26 = 2147942414LL;
          goto LABEL_53;
        }
LABEL_31:
        v6 = 0;
LABEL_17:
        CRefdKey::Release((CRefdKey *)v14);
        goto LABEL_18;
      }
      v8 = 0;
      v30 = 0;
    }
    WX_WIN32_FROM_HR(2147942414LL);
    goto LABEL_31;
  }
LABEL_18:
  if ( (xmmword_180266B60 & 0x10) != 0 )
    WPP_SF_d(1028, 18, WPP_ffb36679dc07312dd2ab286372984303_Traceguids, v6);
  if ( v9 )
    WxCoTaskAllocator::Free(&v29);
  if ( v8 )
    WxCoTaskAllocator::Free(&v30);
  if ( v7 )
    WxCoTaskAllocator::Free(&v31);
  if ( hKey )
    RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x1800f3b64  mov     [rsp-8+arg_18], rbx
0x1800f3b69  push    rbp
0x1800f3b6a  push    rsi
0x1800f3b6b  push    rdi
0x1800f3b6c  push    r12
0x1800f3b6e  push    r13
0x1800f3b70  push    r14
0x1800f3b72  push    r15
0x1800f3b74  lea     rbp, [rsp-1C0h]
0x1800f3b7c  sub     rsp, 2C0h
0x1800f3b83  mov     rax, cs:__security_cookie
0x1800f3b8a  xor     rax, rsp
0x1800f3b8d  mov     [rbp+1F0h+var_40], rax
0x1800f3b94  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800f3b9b  xor     eax, eax
0x1800f3b9d  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_6+10h; "\\Microsoft\\Windows\\CurrentVersion\\I"...
0x1800f3ba4  mov     r12, r8
0x1800f3ba7  movaps  xmmword ptr [rbp+1F0h+SubKey], xmm0
0x1800f3bab  mov     r14, rdx
0x1800f3bae  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_6+20h; "ft\\Windows\\CurrentVersion\\Internet S"...
0x1800f3bb5  mov     r13, rcx
0x1800f3bb8  movaps  [rbp+1F0h+var_240], xmm1
0x1800f3bbc  xor     edx, edx; Val
0x1800f3bbe  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_6+30h; "ws\\CurrentVersion\\Internet Settings"
0x1800f3bc5  mov     r8d, 190h; Size
0x1800f3bcb  movaps  [rbp+1F0h+var_230], xmm0
0x1800f3bcf  mov     r15d, eax
0x1800f3bd2  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_6+40h; "ntVersion\\Internet Settings"
0x1800f3bd9  mov     esi, eax
0x1800f3bdb  movaps  [rbp+1F0h+var_220], xmm1
0x1800f3bdf  mov     edi, eax
0x1800f3be1  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_6+50h; "n\\Internet Settings"
0x1800f3be8  mov     ebx, eax
0x1800f3bea  movaps  [rbp+1F0h+var_210], xmm0
0x1800f3bee  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_6+60h; "et Settings"
0x1800f3bf5  movaps  [rbp+1F0h+var_200], xmm1
0x1800f3bf9  movsd   xmm1, qword ptr cs:aSoftwareMicros_6+70h; "ngs"
0x1800f3c01  mov     [rsp+2F0h+var_278], rcx
0x1800f3c06  lea     rcx, [rbp+1F0h+var_1D8]; void *
0x1800f3c0a  movaps  [rbp+1F0h+var_1F0], xmm0
0x1800f3c0e  movsd   [rbp+1F0h+var_1E0], xmm1
0x1800f3c13  mov     [rbp+1F0h+cbData], eax
0x1800f3c16  mov     dword ptr [rbp+1F0h+Data], eax
0x1800f3c19  mov     [rbp+1F0h+Type], eax
0x1800f3c1c  mov     [rbp+1F0h+hKey], rax
0x1800f3c20  mov     [rsp+2F0h+var_280], rax
0x1800f3c25  mov     [rsp+2F0h+var_288], rax
0x1800f3c2a  mov     [rsp+2F0h+var_290], rax
0x1800f3c2f  call    memset_0
0x1800f3c34  test    byte ptr cs:xmmword_180266B60, 10h
0x1800f3c3b  jnz     loc_1800F3FEF
0x1800f3c41  xor     eax, eax
0x1800f3c43  mov     [r13+0], eax
0x1800f3c47  test    r12, r12
0x1800f3c4a  jz      short loc_1800F3C50
0x1800f3c4c  mov     [r12], eax
0x1800f3c50  mov     dword ptr [r14+4], 1
0x1800f3c58  call    ?FindBaseProxyKey@@YAPEAVCRefdKey@@XZ; FindBaseProxyKey(void)
0x1800f3c5d  mov     r13, rax
0x1800f3c60  test    rax, rax
0x1800f3c63  jz      loc_1800F3E30
0x1800f3c69  cmp     qword ptr [rax+8], 0FFFFFFFF80000002h
0x1800f3c71  jz      loc_1800F400D
0x1800f3c77  mov     rcx, [r13+8]; hKey
0x1800f3c7b  lea     rax, [rbp+1F0h+hKey]
0x1800f3c7f  mov     r9d, 20019h; samDesired
0x1800f3c85  mov     [rsp+2F0h+phkResult], rax; phkResult
0x1800f3c8a  xor     r8d, r8d; ulOptions
0x1800f3c8d  lea     rdx, [rbp+1F0h+SubKey]; lpSubKey
0x1800f3c91  call    cs:__imp_RegOpenKeyExW
0x1800f3c97  test    eax, eax
0x1800f3c99  jnz     loc_1800F3E28
0x1800f3c9f  mov     rcx, [rbp+1F0h+hKey]; hKey
0x1800f3ca3  lea     rax, [rbp+1F0h+cbData]
0x1800f3ca7  mov     [rsp+2F0h+lpcbData], rax; lpcbData
0x1800f3cac  lea     rdx, aProxyenable; "ProxyEnable"
0x1800f3cb3  lea     rax, [rbp+1F0h+Data]
0x1800f3cb7  mov     [rbp+1F0h+cbData], 4
0x1800f3cbe  xor     r9d, r9d; lpType
0x1800f3cc1  mov     [rsp+2F0h+phkResult], rax; lpData
0x1800f3cc6  xor     r8d, r8d; lpReserved
0x1800f3cc9  call    cs:__imp_RegQueryValueExW
0x1800f3ccf  test    eax, 0FFFFFFFDh
0x1800f3cd4  jnz     loc_1800F3E28
0x1800f3cda  xor     edx, edx
0x1800f3cdc  cmp     eax, 2
0x1800f3cdf  mov     ecx, edx
0x1800f3ce1  setz    cl
0x1800f3ce4  mov     [rsp+2F0h+var_29C], ecx
0x1800f3ce8  cmp     dword ptr [rbp+1F0h+Data], edx
0x1800f3ceb  jnz     loc_1800F4022
0x1800f3cf1  mov     eax, 1048h
0x1800f3cf6  mov     [rbp+1F0h+cbData], eax
0x1800f3cf9  mov     ecx, eax; cb
0x1800f3cfb  mov     [rsp+2F0h+var_294], edx
0x1800f3cff  call    cs:__imp_CoTaskMemAlloc
0x1800f3d05  mov     r15, rax
0x1800f3d08  test    rax, rax
0x1800f3d0b  jz      loc_1800F3EA4
0x1800f3d11  xor     edx, edx; Val
0x1800f3d13  mov     r8d, 1048h; Size
0x1800f3d19  mov     rcx, rax; void *
0x1800f3d1c  call    memset_0
0x1800f3d21  mov     rcx, [rbp+1F0h+hKey]; hKey
0x1800f3d25  lea     rax, [rbp+1F0h+cbData]
0x1800f3d29  mov     [rsp+2F0h+lpcbData], rax; lpcbData
0x1800f3d2e  lea     rdx, aProxyserver; "ProxyServer"
0x1800f3d35  xor     r9d, r9d; lpType
0x1800f3d38  mov     [rsp+2F0h+phkResult], r15; lpData
0x1800f3d3d  xor     r8d, r8d; lpReserved
0x1800f3d40  mov     [rsp+2F0h+var_280], r15
0x1800f3d45  mov     rsi, r15
0x1800f3d48  call    cs:__imp_RegQueryValueExW
0x1800f3d4e  test    eax, 0FFFFFFFDh
0x1800f3d53  jnz     loc_1800F3EB6
0x1800f3d59  mov     eax, 1048h
0x1800f3d5e  xor     r15d, r15d
0x1800f3d61  mov     [rbp+1F0h+cbData], eax
0x1800f3d64  mov     ecx, eax; cb
0x1800f3d66  mov     [rsp+2F0h+var_294], r15d
0x1800f3d6b  call    cs:__imp_CoTaskMemAlloc
0x1800f3d71  mov     rdi, rax
0x1800f3d74  test    rax, rax
0x1800f3d77  jz      loc_1800F3E9C
0x1800f3d7d  xor     edx, edx; Val
0x1800f3d7f  mov     r8d, 1048h; Size
0x1800f3d85  mov     rcx, rax; void *
0x1800f3d88  call    memset_0
0x1800f3d8d  mov     rcx, [rbp+1F0h+hKey]; hKey
0x1800f3d91  lea     rax, [rbp+1F0h+cbData]
0x1800f3d95  mov     [rsp+2F0h+lpcbData], rax; lpcbData
0x1800f3d9a  lea     rdx, aProxyoverride; "ProxyOverride"
0x1800f3da1  xor     r9d, r9d; lpType
0x1800f3da4  mov     [rsp+2F0h+phkResult], rdi; lpData
0x1800f3da9  xor     r8d, r8d; lpReserved
0x1800f3dac  mov     [rsp+2F0h+var_288], rdi
0x1800f3db1  call    cs:__imp_RegQueryValueExW
0x1800f3db7  test    eax, 0FFFFFFFDh
0x1800f3dbc  jnz     loc_1800F3EB6
0x1800f3dc2  mov     eax, 1048h
0x1800f3dc7  mov     [rbp+1F0h+cbData], eax
0x1800f3dca  mov     ecx, eax; cb
0x1800f3dcc  mov     [rsp+2F0h+var_294], r15d
0x1800f3dd1  call    cs:__imp_CoTaskMemAlloc
0x1800f3dd7  mov     rbx, rax
0x1800f3dda  test    rax, rax
0x1800f3ddd  jz      loc_1800F3FBF
0x1800f3de3  xor     edx, edx; Val
0x1800f3de5  mov     r8d, 1048h; Size
0x1800f3deb  mov     rcx, rax; void *
0x1800f3dee  call    memset_0
0x1800f3df3  mov     rcx, [rbp+1F0h+hKey]; hKey
0x1800f3df7  lea     rax, [rbp+1F0h+cbData]
0x1800f3dfb  mov     [rsp+2F0h+lpcbData], rax; lpcbData
0x1800f3e00  lea     rdx, aAutoconfigurl; "AutoConfigURL"
0x1800f3e07  xor     r9d, r9d; lpType
0x1800f3e0a  mov     [rsp+2F0h+phkResult], rbx; lpData
0x1800f3e0f  xor     r8d, r8d; lpReserved
0x1800f3e12  mov     [rsp+2F0h+var_290], rbx
0x1800f3e17  call    cs:__imp_RegQueryValueExW
0x1800f3e1d  test    eax, 0FFFFFFFDh
0x1800f3e22  jz      loc_1800F3ECA
0x1800f3e28  mov     rcx, r13; this
0x1800f3e2b  call    ?Release@CRefdKey@@QEAAKXZ; CRefdKey::Release(void)
0x1800f3e30  test    byte ptr cs:xmmword_180266B60, 10h
0x1800f3e37  jnz     loc_1800F4066
0x1800f3e3d  test    rbx, rbx
0x1800f3e40  jz      short loc_1800F3E4C
0x1800f3e42  lea     rcx, [rsp+2F0h+var_290]; void **
0x1800f3e47  call    ?Free@WxCoTaskAllocator@@SAXPEAPEAX@Z; WxCoTaskAllocator::Free(void * *)
0x1800f3e4c  test    rdi, rdi
0x1800f3e4f  jz      short loc_1800F3E5B
0x1800f3e51  lea     rcx, [rsp+2F0h+var_288]; void **
0x1800f3e56  call    ?Free@WxCoTaskAllocator@@SAXPEAPEAX@Z; WxCoTaskAllocator::Free(void * *)
0x1800f3e5b  test    rsi, rsi
0x1800f3e5e  jnz     short loc_1800F3EBE
0x1800f3e60  mov     rcx, [rbp+1F0h+hKey]; hKey
0x1800f3e64  test    rcx, rcx
0x1800f3e67  jz      short loc_1800F3E6F
0x1800f3e69  call    cs:__imp_RegCloseKey
0x1800f3e6f  mov     eax, r15d
0x1800f3e72  mov     rcx, [rbp+1F0h+var_40]
0x1800f3e79  xor     rcx, rsp; StackCookie
0x1800f3e7c  call    __security_check_cookie
0x1800f3e81  mov     rbx, [rsp+2F0h+arg_18]
0x1800f3e89  add     rsp, 2C0h
0x1800f3e90  pop     r15
0x1800f3e92  pop     r14
0x1800f3e94  pop     r13
0x1800f3e96  pop     r12
0x1800f3e98  pop     rdi
0x1800f3e99  pop     rsi
0x1800f3e9a  pop     rbp
0x1800f3e9b  retn
0x1800f3e9c  mov     rdi, r15
0x1800f3e9f  mov     [rsp+2F0h+var_288], r15
0x1800f3ea4  mov     ecx, 8007000Eh
0x1800f3ea9  mov     [rsp+2F0h+var_294], 4Ch ; 'L'
0x1800f3eb1  call    WX_WIN32_FROM_HR
0x1800f3eb6  mov     r15d, ebx
0x1800f3eb9  jmp     loc_1800F3E28
0x1800f3ebe  lea     rcx, [rsp+2F0h+var_280]; void **
0x1800f3ec3  call    ?Free@WxCoTaskAllocator@@SAXPEAPEAX@Z; WxCoTaskAllocator::Free(void * *)
0x1800f3ec8  jmp     short loc_1800F3E60
0x1800f3eca  mov     rcx, [rbp+1F0h+hKey]; hKey
0x1800f3ece  lea     rax, [rbp+1F0h+cbData]
0x1800f3ed2  mov     [rsp+2F0h+lpcbData], rax; lpcbData
0x1800f3ed7  lea     r9, [rbp+1F0h+Type]; lpType
0x1800f3edb  lea     rax, [rbp+1F0h+Data]
0x1800f3edf  mov     [rbp+1F0h+cbData], 4
0x1800f3ee6  xor     r8d, r8d; lpReserved
0x1800f3ee9  mov     [rsp+2F0h+phkResult], rax; lpData
0x1800f3eee  lea     rdx, aAutodetect; "AutoDetect"
0x1800f3ef5  call    cs:__imp_RegQueryValueExW
0x1800f3efb  test    eax, 0FFFFFFFDh
0x1800f3f00  jnz     loc_1800F3E28
0x1800f3f06  mov     r9d, r15d
0x1800f3f09  test    eax, eax
0x1800f3f0b  jz      loc_1800F402C
0x1800f3f11  cmp     [rsi], r15w
0x1800f3f15  jnz     loc_1800F3FDE
0x1800f3f1b  cmp     [rdi], r15w
0x1800f3f1f  jz      short loc_1800F3F2D
0x1800f3f21  mov     [r14+20h], rdi
0x1800f3f25  mov     rdi, r15
0x1800f3f28  mov     [rsp+2F0h+var_288], r15
0x1800f3f2d  cmp     [rbx], r15w
0x1800f3f31  jnz     loc_1800F4050
0x1800f3f37  cmp     [r14+8], r15d
0x1800f3f3b  jnz     short loc_1800F3F45
0x1800f3f3d  mov     dword ptr [r14+8], 1
0x1800f3f45  mov     rax, [rsp+2F0h+var_278]
0x1800f3f4a  mov     r8d, [rsp+2F0h+var_29C]
0x1800f3f4f  mov     [rax], r9d
0x1800f3f52  test    r12, r12
0x1800f3f55  jz      short loc_1800F3F5B
0x1800f3f57  mov     [r12], r8d
0x1800f3f5b  mov     r15d, 1
0x1800f3f61  test    byte ptr cs:xmmword_180266B60, 10h
0x1800f3f68  jz      loc_1800F3E28
0x1800f3f6e  xor     r10d, r10d
0x1800f3f71  lea     rdx, aNone; "<none>"
0x1800f3f78  cmp     [r14+28h], r10
0x1800f3f7c  mov     rcx, rdx
0x1800f3f7f  mov     rax, rdx
0x1800f3f82  cmovnz  rcx, [r14+28h]
0x1800f3f87  cmp     [r14+20h], r10
0x1800f3f8b  mov     [rsp+2F0h+var_2B0], rcx
0x1800f3f90  cmovnz  rax, [r14+20h]
0x1800f3f95  cmp     [r14+18h], r10
0x1800f3f99  mov     [rsp+2F0h+var_2B8], rax
0x1800f3f9e  cmovnz  rdx, [r14+18h]
0x1800f3fa3  mov     eax, [r14+4]
0x1800f3fa7  mov     [rsp+2F0h+var_2C0], rdx
0x1800f3fac  mov     dword ptr [rsp+2F0h+lpcbData], eax
0x1800f3fb0  mov     dword ptr [rsp+2F0h+phkResult], r8d
0x1800f3fb5  call    WPP_SF_llDSSS
0x1800f3fba  jmp     loc_1800F3E28
0x1800f3fbf  mov     rbx, r15
0x1800f3fc2  mov     [rsp+2F0h+var_294], 4Ch ; 'L'
0x1800f3fca  mov     [rsp+2F0h+var_290], rbx
0x1800f3fcf  mov     ecx, 8007000Eh
0x1800f3fd4  call    WX_WIN32_FROM_HR
0x1800f3fd9  jmp     loc_1800F3E28
0x1800f3fde  mov     [r14+18h], rsi
0x1800f3fe2  mov     rsi, r15
0x1800f3fe5  mov     [rsp+2F0h+var_280], r15
0x1800f3fea  jmp     loc_1800F3F1B
0x1800f3fef  mov     edx, 10h
0x1800f3ff4  lea     r8, WPP_ffb36679dc07312dd2ab286372984303_Traceguids
0x1800f3ffb  mov     ecx, 404h
0x1800f4000  mov     r9, r14
0x1800f4003  call    WPP_SF_q
0x1800f4008  jmp     loc_1800F3C41
0x1800f400d  lea     r9, [rbp+1F0h+SubKey]
0x1800f4011  call    WxGetPersistedRegistryLocation
0x1800f4016  test    eax, eax
0x1800f4018  jns     loc_1800F3C77
0x1800f401e  mov     ecx, eax
0x1800f4020  jmp     short loc_1800F3FD4
0x1800f4022  or      dword ptr [r14+4], 2
0x1800f4027  jmp     loc_1800F3CF1
0x1800f402c  cmp     [rbp+1F0h+Type], 4
0x1800f4030  jnz     loc_1800F3F11
0x1800f4036  mov     r9d, 1
0x1800f403c  cmp     dword ptr [rbp+1F0h+Data], r15d
0x1800f4040  jz      loc_1800F3F11
0x1800f4046  or      dword ptr [r14+4], 8
0x1800f404b  jmp     loc_1800F3F11
0x1800f4050  or      dword ptr [r14+4], 4
0x1800f4055  mov     [r14+28h], rbx
0x1800f4059  mov     rbx, r15
0x1800f405c  mov     [rsp+2F0h+var_290], rbx
0x1800f4061  jmp     loc_1800F3F37
0x1800f4066  mov     edx, 12h
0x1800f406b  lea     r8, WPP_ffb36679dc07312dd2ab286372984303_Traceguids
0x1800f4072  mov     ecx, 404h
0x1800f4077  mov     r9d, r15d
0x1800f407a  call    WPP_SF_d
0x1800f407f  jmp     loc_1800F3E3D
  ... truncated ...
```
