# WxpObfuscateKey

- ea: `0x1800b5b4c`
- end: `0x1800b5f49`
- name: `WxpObfuscateKey`
- size: `1021`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180093d5c`

## callees

- `0x18002cd80`
- `0x1800b53c4`
- `0x1800b5ac8`
- `0x1800b5b4c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800b5c8a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800b5d56`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800b5e1f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800b5f0e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800b5c8a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800b5d56`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800b5e1f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800b5f0e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b5c94`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b5d60`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b5e29`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b5ee8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b5f18`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b5f24`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b5c94`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b5d60`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b5e29`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b5ee8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b5f18`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b5f24`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800b5c57`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800b5d2a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800b5df0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800b5ec9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800b5c57`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800b5d2a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800b5df0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800b5ec9`
- `api-ms-win-security-systemfunctions-l1-1-0!SystemFunction036` at `0x1800b5bd7`
- `api-ms-win-security-systemfunctions-l1-1-0!SystemFunction036` at `0x1800b5cac`
- `api-ms-win-security-systemfunctions-l1-1-0!SystemFunction036` at `0x1800b5d6d`
- `api-ms-win-security-systemfunctions-l1-1-0!SystemFunction036` at `0x1800b5e38`
- `api-ms-win-security-systemfunctions-l1-1-0!SystemFunction036` at `0x1800b5e4d`
- `api-ms-win-security-systemfunctions-l1-1-0!SystemFunction036` at `0x1800b5eda`
- `api-ms-win-security-systemfunctions-l1-1-0!SystemFunction036` at `0x1800b5bd7`
- `api-ms-win-security-systemfunctions-l1-1-0!SystemFunction036` at `0x1800b5cac`
- `api-ms-win-security-systemfunctions-l1-1-0!SystemFunction036` at `0x1800b5d6d`
- `api-ms-win-security-systemfunctions-l1-1-0!SystemFunction036` at `0x1800b5e38`
- `api-ms-win-security-systemfunctions-l1-1-0!SystemFunction036` at `0x1800b5e4d`
- `api-ms-win-security-systemfunctions-l1-1-0!SystemFunction036` at `0x1800b5eda`

## pseudocode

```c
char __fastcall WxpObfuscateKey(__int64 a1)
{
  __int64 v2; // rax
  HKEY v3; // rbx
  __int64 i; // rdx
  char v5; // r14
  CHAR *v6; // rdx
  __int64 v7; // r8
  unsigned int v8; // ecx
  int v9; // edi
  CHAR *v10; // rsi
  unsigned __int64 v11; // rax
  CHAR *v12; // rdx
  __int64 v13; // r8
  unsigned int v14; // ecx
  CHAR *v15; // rdx
  __int64 v16; // r8
  unsigned int v17; // ecx
  HKEY hKey; // [rsp+50h] [rbp-29h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-21h] BYREF
  __int128 RandomBuffer; // [rsp+60h] [rbp-19h] BYREF
  __int128 v22; // [rsp+70h] [rbp-9h] BYREF
  CHAR Class[16]; // [rsp+80h] [rbp+7h] BYREF

  hKey = 0;
  dwDisposition = 0;
  v22 = 0;
  RandomBuffer = 0;
  v2 = OpenLsaKey();
  v3 = (HKEY)v2;
  if ( v2 )
  {
    for ( i = 0; i != 16; ++i )
      Class[i - 16] = *(_BYTE *)(*((unsigned __int8 *)qword_1800D86C0 + i) + a1);
    WxpDeleteLocalKey();
    v5 = 0;
    Class[8] = 0;
    if ( !SystemFunction036(&RandomBuffer, 0x10u) )
      goto LABEL_28;
    v6 = Class;
    v7 = 0;
    do
    {
      v8 = (unsigned __int8)Class[v7++ - 16];
      *v6 = a0123456789abcd_1[(unsigned __int64)v8 >> 4];
      v6 += 2;
      *(v6 - 1) = a0123456789abcd_1[v8 & 0xF];
    }
    while ( v7 != 4 );
    if ( RegCreateKeyExA(v3, "JD", 0, Class, 0, 0x20006u, 0, &hKey, &dwDisposition) )
      goto LABEL_28;
    RegSetValueExA(hKey, "Lookup", 0, 3u, (const BYTE *)&RandomBuffer, 6u);
    RegCloseKey(hKey);
    v9 = 0;
    v10 = Class;
    while ( v9 < 4 )
    {
      if ( !SystemFunction036(&RandomBuffer, 0x10u) )
        goto LABEL_28;
      v11 = (unsigned __int8)Class[v9 - 12];
      *v10 = a0123456789abcd_1[v11 >> 4];
      v10[1] = a0123456789abcd_1[v11 & 0xF];
      v10 += 2;
      ++v9;
    }
    if ( !RegCreateKeyExA(v3, "Skew1", 0, Class, 0, 0x20006u, 0, &hKey, &dwDisposition) )
    {
      RegSetValueExA(hKey, "SkewMatrix", 0, 3u, (const BYTE *)&RandomBuffer, 0x10u);
      RegCloseKey(hKey);
    }
    if ( !SystemFunction036(&RandomBuffer, 0x10u) )
      goto LABEL_28;
    v12 = Class;
    v13 = 0;
    do
    {
      v14 = (unsigned __int8)Class[v13++ - 8];
      *v12 = a0123456789abcd_1[(unsigned __int64)v14 >> 4];
      v12 += 2;
      *(v12 - 1) = a0123456789abcd_1[v14 & 0xF];
    }
    while ( v13 != 4 );
    if ( !RegCreateKeyExA(v3, "GBG", 0, Class, 0, 0x20006u, 0, &hKey, &dwDisposition) )
    {
      RegSetValueExA(hKey, "GrafBlumGroup", 0, 3u, (const BYTE *)&RandomBuffer, 9u);
      RegCloseKey(hKey);
    }
    if ( !SystemFunction036(&v22, 8u) || !SystemFunction036(&RandomBuffer, 0x10u) )
      goto LABEL_28;
    v15 = Class;
    v16 = 0;
    do
    {
      v17 = (unsigned __int8)Class[v16++ - 4];
      *v15 = a0123456789abcd_1[(unsigned __int64)v17 >> 4];
      v15 += 2;
      *(v15 - 1) = a0123456789abcd_1[v17 & 0xF];
    }
    while ( v16 != 4 );
    if ( !RegCreateKeyExA(v3, "Data", 0, Class, 0, 0x20006u, 0, &hKey, &dwDisposition) )
    {
      if ( !SystemFunction036(&v22, 0x10u) )
      {
        RegCloseKey(hKey);
LABEL_28:
        RegCloseKey(v3);
        LOBYTE(v2) = v5;
        return v2;
      }
      RegSetValueExA(hKey, "Pattern", 0, 3u, (const BYTE *)&RandomBuffer, 0x10u);
      RegCloseKey(hKey);
    }
    v5 = 1;
    goto LABEL_28;
  }
  return v2;
}

```

## disassembly

```asm
0x1800b5b4c  push    rbp
0x1800b5b4e  push    rbx
0x1800b5b4f  push    rsi
0x1800b5b50  push    rdi
0x1800b5b51  push    r12
0x1800b5b53  push    r14
0x1800b5b55  lea     rbp, [rsp-2Fh]
0x1800b5b5a  sub     rsp, 0A8h
0x1800b5b61  mov     rax, cs:__security_cookie
0x1800b5b68  xor     rax, rsp
0x1800b5b6b  mov     [rbp+57h+var_40], rax
0x1800b5b6f  xorps   xmm0, xmm0
0x1800b5b72  mov     [rbp+57h+hKey], 0
0x1800b5b7a  xorps   xmm1, xmm1
0x1800b5b7d  mov     [rbp+57h+dwDisposition], 0
0x1800b5b84  movups  [rbp+57h+var_60], xmm0
0x1800b5b88  mov     rdi, rcx
0x1800b5b8b  movups  [rbp+57h+RandomBuffer], xmm1
0x1800b5b8f  call    OpenLsaKey
0x1800b5b94  mov     rbx, rax
0x1800b5b97  test    rax, rax
0x1800b5b9a  jz      loc_1800B5F2D
0x1800b5ba0  xor     edx, edx
0x1800b5ba2  lea     rsi, __ImageBase
0x1800b5ba9  lea     r12d, [rdx+10h]
0x1800b5bad  movzx   eax, byte ptr [rdx+rsi+0D86C0h]
0x1800b5bb5  mov     cl, [rax+rdi]
0x1800b5bb8  mov     byte ptr [rbp+rdx+57h+var_60], cl
0x1800b5bbc  inc     rdx
0x1800b5bbf  cmp     rdx, r12
0x1800b5bc2  jnz     short loc_1800B5BAD
0x1800b5bc4  call    WxpDeleteLocalKey
0x1800b5bc9  xor     r14b, r14b
0x1800b5bcc  lea     rcx, [rbp+57h+RandomBuffer]; RandomBuffer
0x1800b5bd0  mov     edx, r12d; RandomBufferLength
0x1800b5bd3  mov     [rbp+57h+var_48], r14b
0x1800b5bd7  call    cs:__imp_SystemFunction036
0x1800b5bdd  test    al, al
0x1800b5bdf  jz      loc_1800B5F21
0x1800b5be5  lea     rdx, [rbp+57h+Class]
0x1800b5be9  xor     r8d, r8d
0x1800b5bec  movzx   ecx, byte ptr [rbp+r8+57h+var_60]
0x1800b5bf2  inc     r8
0x1800b5bf5  mov     eax, ecx
0x1800b5bf7  and     ecx, 0Fh
0x1800b5bfa  shr     rax, 4
0x1800b5bfe  mov     al, [rax+rsi+0D86A0h]
0x1800b5c05  mov     [rdx], al
0x1800b5c07  lea     rdx, [rdx+2]
0x1800b5c0b  mov     al, [rcx+rsi+0D86A0h]
0x1800b5c12  mov     [rdx-1], al
0x1800b5c15  cmp     r8, 4
0x1800b5c19  jnz     short loc_1800B5BEC
0x1800b5c1b  lea     rax, [rbp+57h+dwDisposition]
0x1800b5c1f  xor     r8d, r8d; Reserved
0x1800b5c22  mov     [rsp+0D0h+lpdwDisposition], rax; lpdwDisposition
0x1800b5c27  lea     r9, [rbp+57h+Class]; lpClass
0x1800b5c2b  lea     rax, [rbp+57h+hKey]
0x1800b5c2f  mov     rcx, rbx; hKey
0x1800b5c32  mov     [rsp+0D0h+phkResult], rax; phkResult
0x1800b5c37  lea     rdx, aJd; "JD"
0x1800b5c3e  mov     [rsp+0D0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800b5c47  mov     [rsp+0D0h+samDesired], 20006h; samDesired
0x1800b5c4f  mov     [rsp+0D0h+dwOptions], 0; dwOptions
0x1800b5c57  call    cs:__imp_RegCreateKeyExA
0x1800b5c5d  test    eax, eax
0x1800b5c5f  jnz     loc_1800B5F21
0x1800b5c65  mov     rcx, [rbp+57h+hKey]; hKey
0x1800b5c69  lea     rax, [rbp+57h+RandomBuffer]
0x1800b5c6d  mov     [rsp+0D0h+samDesired], 6; cbData
0x1800b5c75  lea     rdx, aLookup; "Lookup"
0x1800b5c7c  mov     r9d, 3; dwType
0x1800b5c82  mov     qword ptr [rsp+0D0h+dwOptions], rax; lpData
0x1800b5c87  xor     r8d, r8d; Reserved
0x1800b5c8a  call    cs:__imp_RegSetValueExA
0x1800b5c90  mov     rcx, [rbp+57h+hKey]; hKey
0x1800b5c94  call    cs:__imp_RegCloseKey
0x1800b5c9a  xor     edi, edi
0x1800b5c9c  lea     rsi, [rbp+57h+Class]
0x1800b5ca0  cmp     edi, 4
0x1800b5ca3  jge     short loc_1800B5CED
0x1800b5ca5  mov     edx, r12d; RandomBufferLength
0x1800b5ca8  lea     rcx, [rbp+57h+RandomBuffer]; RandomBuffer
0x1800b5cac  call    cs:__imp_SystemFunction036
0x1800b5cb2  test    al, al
0x1800b5cb4  jz      loc_1800B5F21
0x1800b5cba  movsxd  rax, edi
0x1800b5cbd  lea     rdx, __ImageBase
0x1800b5cc4  movzx   ecx, byte ptr [rbp+rax+57h+var_60+4]
0x1800b5cc9  mov     eax, ecx
0x1800b5ccb  and     ecx, 0Fh
0x1800b5cce  shr     rax, 4
0x1800b5cd2  mov     al, [rax+rdx+0D86A0h]
0x1800b5cd9  mov     [rsi], al
0x1800b5cdb  mov     al, [rcx+rdx+0D86A0h]
0x1800b5ce2  mov     [rsi+1], al
0x1800b5ce5  add     rsi, 2
0x1800b5ce9  inc     edi
0x1800b5ceb  jmp     short loc_1800B5CA0
0x1800b5ced  lea     rax, [rbp+57h+dwDisposition]
0x1800b5cf1  mov     esi, 20006h
0x1800b5cf6  mov     [rsp+0D0h+lpdwDisposition], rax; lpdwDisposition
0x1800b5cfb  lea     r9, [rbp+57h+Class]; lpClass
0x1800b5cff  lea     rax, [rbp+57h+hKey]
0x1800b5d03  xor     r8d, r8d; Reserved
0x1800b5d06  mov     [rsp+0D0h+phkResult], rax; phkResult
0x1800b5d0b  lea     rdx, aSkew1; "Skew1"
0x1800b5d12  mov     [rsp+0D0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800b5d1b  mov     rcx, rbx; hKey
0x1800b5d1e  mov     [rsp+0D0h+samDesired], esi; samDesired
0x1800b5d22  mov     [rsp+0D0h+dwOptions], 0; dwOptions
0x1800b5d2a  call    cs:__imp_RegCreateKeyExA
0x1800b5d30  test    eax, eax
0x1800b5d32  jnz     short loc_1800B5D66
0x1800b5d34  mov     rcx, [rbp+57h+hKey]; hKey
0x1800b5d38  lea     rax, [rbp+57h+RandomBuffer]
0x1800b5d3c  mov     [rsp+0D0h+samDesired], r12d; cbData
0x1800b5d41  lea     rdx, aSkewmatrix; "SkewMatrix"
0x1800b5d48  mov     r9d, 3; dwType
0x1800b5d4e  mov     qword ptr [rsp+0D0h+dwOptions], rax; lpData
0x1800b5d53  xor     r8d, r8d; Reserved
0x1800b5d56  call    cs:__imp_RegSetValueExA
0x1800b5d5c  mov     rcx, [rbp+57h+hKey]; hKey
0x1800b5d60  call    cs:__imp_RegCloseKey
0x1800b5d66  mov     edx, r12d; RandomBufferLength
0x1800b5d69  lea     rcx, [rbp+57h+RandomBuffer]; RandomBuffer
0x1800b5d6d  call    cs:__imp_SystemFunction036
0x1800b5d73  test    al, al
0x1800b5d75  jz      loc_1800B5F21
0x1800b5d7b  lea     rdx, [rbp+57h+Class]
0x1800b5d7f  xor     r8d, r8d
0x1800b5d82  lea     rdi, __ImageBase
0x1800b5d89  movzx   ecx, byte ptr [rbp+r8+57h+var_60+8]
0x1800b5d8f  inc     r8
0x1800b5d92  mov     eax, ecx
0x1800b5d94  and     ecx, 0Fh
0x1800b5d97  shr     rax, 4
0x1800b5d9b  mov     al, [rax+rdi+0D86A0h]
0x1800b5da2  mov     [rdx], al
0x1800b5da4  lea     rdx, [rdx+2]
0x1800b5da8  mov     al, [rcx+rdi+0D86A0h]
0x1800b5daf  mov     [rdx-1], al
0x1800b5db2  cmp     r8, 4
0x1800b5db6  jnz     short loc_1800B5D89
0x1800b5db8  lea     rax, [rbp+57h+dwDisposition]
0x1800b5dbc  xor     r8d, r8d; Reserved
0x1800b5dbf  mov     [rsp+0D0h+lpdwDisposition], rax; lpdwDisposition
0x1800b5dc4  lea     r9, [rbp+57h+Class]; lpClass
0x1800b5dc8  lea     rax, [rbp+57h+hKey]
0x1800b5dcc  mov     rcx, rbx; hKey
0x1800b5dcf  mov     [rsp+0D0h+phkResult], rax; phkResult
0x1800b5dd4  lea     rdx, aGbg; "GBG"
0x1800b5ddb  mov     [rsp+0D0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800b5de4  mov     [rsp+0D0h+samDesired], esi; samDesired
0x1800b5de8  mov     [rsp+0D0h+dwOptions], 0; dwOptions
0x1800b5df0  call    cs:__imp_RegCreateKeyExA
0x1800b5df6  test    eax, eax
0x1800b5df8  jnz     short loc_1800B5E2F
0x1800b5dfa  mov     rcx, [rbp+57h+hKey]; hKey
0x1800b5dfe  lea     rax, [rbp+57h+RandomBuffer]
0x1800b5e02  mov     [rsp+0D0h+samDesired], 9; cbData
0x1800b5e0a  lea     rdx, aGrafblumgroup; "GrafBlumGroup"
0x1800b5e11  mov     r9d, 3; dwType
0x1800b5e17  mov     qword ptr [rsp+0D0h+dwOptions], rax; lpData
0x1800b5e1c  xor     r8d, r8d; Reserved
0x1800b5e1f  call    cs:__imp_RegSetValueExA
0x1800b5e25  mov     rcx, [rbp+57h+hKey]; hKey
0x1800b5e29  call    cs:__imp_RegCloseKey
0x1800b5e2f  mov     edx, 8; RandomBufferLength
0x1800b5e34  lea     rcx, [rbp+57h+var_60]; RandomBuffer
0x1800b5e38  call    cs:__imp_SystemFunction036
0x1800b5e3e  test    al, al
0x1800b5e40  jz      loc_1800B5F21
0x1800b5e46  mov     edx, r12d; RandomBufferLength
0x1800b5e49  lea     rcx, [rbp+57h+RandomBuffer]; RandomBuffer
0x1800b5e4d  call    cs:__imp_SystemFunction036
0x1800b5e53  test    al, al
0x1800b5e55  jz      loc_1800B5F21
0x1800b5e5b  lea     rdx, [rbp+57h+Class]
0x1800b5e5f  xor     r8d, r8d
0x1800b5e62  movzx   ecx, byte ptr [rbp+r8+57h+var_60+0Ch]
0x1800b5e68  inc     r8
0x1800b5e6b  mov     eax, ecx
0x1800b5e6d  and     ecx, 0Fh
0x1800b5e70  shr     rax, 4
0x1800b5e74  mov     al, [rax+rdi+0D86A0h]
0x1800b5e7b  mov     [rdx], al
0x1800b5e7d  lea     rdx, [rdx+2]
0x1800b5e81  mov     al, [rcx+rdi+0D86A0h]
0x1800b5e88  mov     [rdx-1], al
0x1800b5e8b  cmp     r8, 4
0x1800b5e8f  jnz     short loc_1800B5E62
0x1800b5e91  lea     rax, [rbp+57h+dwDisposition]
0x1800b5e95  xor     r8d, r8d; Reserved
0x1800b5e98  mov     [rsp+0D0h+lpdwDisposition], rax; lpdwDisposition
0x1800b5e9d  lea     r9, [rbp+57h+Class]; lpClass
0x1800b5ea1  lea     rax, [rbp+57h+hKey]
0x1800b5ea5  mov     rcx, rbx; hKey
0x1800b5ea8  mov     [rsp+0D0h+phkResult], rax; phkResult
0x1800b5ead  lea     rdx, aData; "Data"
0x1800b5eb4  mov     [rsp+0D0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800b5ebd  mov     [rsp+0D0h+samDesired], esi; samDesired
0x1800b5ec1  mov     [rsp+0D0h+dwOptions], 0; dwOptions
0x1800b5ec9  call    cs:__imp_RegCreateKeyExA
0x1800b5ecf  test    eax, eax
0x1800b5ed1  jnz     short loc_1800B5F1E
0x1800b5ed3  mov     edx, r12d; RandomBufferLength
0x1800b5ed6  lea     rcx, [rbp+57h+var_60]; RandomBuffer
0x1800b5eda  call    cs:__imp_SystemFunction036
0x1800b5ee0  mov     rcx, [rbp+57h+hKey]; hKey
0x1800b5ee4  test    al, al
0x1800b5ee6  jnz     short loc_1800B5EF0
0x1800b5ee8  call    cs:__imp_RegCloseKey
0x1800b5eee  jmp     short loc_1800B5F21
0x1800b5ef0  lea     rax, [rbp+57h+RandomBuffer]
0x1800b5ef4  mov     [rsp+0D0h+samDesired], r12d; cbData
0x1800b5ef9  mov     r9d, 3; dwType
0x1800b5eff  mov     qword ptr [rsp+0D0h+dwOptions], rax; lpData
0x1800b5f04  xor     r8d, r8d; Reserved
0x1800b5f07  lea     rdx, aPattern; "Pattern"
0x1800b5f0e  call    cs:__imp_RegSetValueExA
0x1800b5f14  mov     rcx, [rbp+57h+hKey]; hKey
0x1800b5f18  call    cs:__imp_RegCloseKey
0x1800b5f1e  mov     r14b, 1
0x1800b5f21  mov     rcx, rbx; hKey
0x1800b5f24  call    cs:__imp_RegCloseKey
0x1800b5f2a  mov     al, r14b
0x1800b5f2d  mov     rcx, [rbp+57h+var_40]
0x1800b5f31  xor     rcx, rsp; StackCookie
0x1800b5f34  call    __security_check_cookie
0x1800b5f39  add     rsp, 0A8h
0x1800b5f40  pop     r14
0x1800b5f42  pop     r12
0x1800b5f44  pop     rdi
0x1800b5f45  pop     rsi
0x1800b5f46  pop     rbx
0x1800b5f47  pop     rbp
0x1800b5f48  retn
```
