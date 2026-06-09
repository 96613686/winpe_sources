# WxpDeObfuscateKey

- ea: `0x180016900`
- end: `0x180016e29`
- name: `WxpDeObfuscateKey`
- size: `1321`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800127a0`

## callees

- `0x180006620`
- `0x18001672c`
- `0x180016900`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x1800169c1`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x180016ade`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x180016c01`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x180016d24`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x1800169c1`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x180016ade`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x180016c01`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x180016d24`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18001696d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180016a92`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180016bb5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180016cd8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18001696d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180016a92`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180016bb5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180016cd8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800169cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016aea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016c0d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016d30`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016e00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800169cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016aea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016c0d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016d30`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016e00`

## pseudocode

```c
char __fastcall WxpDeObfuscateKey(__int64 a1, __int64 a2)
{
  HKEY v3; // rax
  HKEY v4; // r14
  __int128 *v5; // rsi
  char v6; // di
  LSTATUS v7; // ebx
  unsigned int i; // r9d
  CHAR v9; // dl
  char v10; // dl
  CHAR v11; // r8
  char v12; // r8
  LSTATUS v13; // ebx
  unsigned int j; // r9d
  CHAR v15; // dl
  char v16; // dl
  CHAR v17; // r8
  char v18; // r8
  LSTATUS v19; // ebx
  unsigned int k; // r9d
  CHAR v21; // dl
  char v22; // dl
  CHAR v23; // r8
  char v24; // r8
  LSTATUS v25; // ebx
  unsigned int m; // r9d
  CHAR v27; // dl
  char v28; // dl
  CHAR v29; // r8
  char v30; // r8
  __int64 n; // r9
  CHAR v32; // dl
  __int64 v33; // r8
  DWORD cchClass; // [rsp+60h] [rbp-29h] BYREF
  HKEY hKey[2]; // [rsp+68h] [rbp-21h] BYREF
  __int128 v37; // [rsp+78h] [rbp-11h] BYREF
  CHAR Class[16]; // [rsp+88h] [rbp-1h] BYREF

  v37 = 0;
  hKey[0] = 0;
  cchClass = 0;
  v3 = (HKEY)OpenLsaKey();
  v4 = v3;
  if ( v3 )
  {
    v5 = &v37;
    v6 = 1;
    if ( !RegOpenKeyExA(v3, "JD", 0, 0x20019u, hKey) )
    {
      cchClass = 9;
      v7 = RegQueryInfoKeyA(hKey[0], Class, &cchClass, 0, 0, 0, 0, 0, 0, 0, 0, 0);
      RegCloseKey(hKey[0]);
      if ( !v7 )
      {
        for ( i = 0; i < 8; i += 2 )
        {
          v9 = Class[i];
          if ( (unsigned __int8)(v9 - 48) > 9u )
          {
            if ( (unsigned __int8)(v9 - 97) > 5u )
            {
              if ( (unsigned __int8)(v9 - 65) > 5u )
                v10 = -1;
              else
                v10 = v9 - 55;
            }
            else
            {
              v10 = v9 - 87;
            }
          }
          else
          {
            v10 = v9 - 48;
          }
          v11 = Class[i + 1];
          if ( (unsigned __int8)(v11 - 48) > 9u )
          {
            if ( (unsigned __int8)(v11 - 97) > 5u )
            {
              if ( (unsigned __int8)(v11 - 65) > 5u )
                v12 = -1;
              else
                v12 = v11 - 55;
            }
            else
            {
              v12 = v11 - 87;
            }
          }
          else
          {
            v12 = v11 - 48;
          }
          if ( (unsigned __int8)v10 > 0xFu || (unsigned __int8)v12 > 0xFu )
          {
LABEL_86:
            v6 = 0;
            goto LABEL_89;
          }
          *(_BYTE *)v5 = v12 + 16 * v10;
          v5 = (__int128 *)((char *)v5 + 1);
        }
      }
    }
    if ( !RegOpenKeyExA(v4, "Skew1", 0, 0x20019u, hKey) )
    {
      cchClass = 9;
      v13 = RegQueryInfoKeyA(hKey[0], Class, &cchClass, 0, 0, 0, 0, 0, 0, 0, 0, 0);
      RegCloseKey(hKey[0]);
      if ( !v13 )
      {
        for ( j = 0; j < 8; j += 2 )
        {
          v15 = Class[j];
          if ( (unsigned __int8)(v15 - 48) > 9u )
          {
            if ( (unsigned __int8)(v15 - 97) > 5u )
            {
              if ( (unsigned __int8)(v15 - 65) > 5u )
                v16 = -1;
              else
                v16 = v15 - 55;
            }
            else
            {
              v16 = v15 - 87;
            }
          }
          else
          {
            v16 = v15 - 48;
          }
          v17 = Class[j + 1];
          if ( (unsigned __int8)(v17 - 48) > 9u )
          {
            if ( (unsigned __int8)(v17 - 97) > 5u )
            {
              if ( (unsigned __int8)(v17 - 65) > 5u )
                v18 = -1;
              else
                v18 = v17 - 55;
            }
            else
            {
              v18 = v17 - 87;
            }
          }
          else
          {
            v18 = v17 - 48;
          }
          if ( (unsigned __int8)v16 > 0xFu || (unsigned __int8)v18 > 0xFu )
            goto LABEL_86;
          *(_BYTE *)v5 = v18 + 16 * v16;
          v5 = (__int128 *)((char *)v5 + 1);
        }
      }
    }
    if ( !RegOpenKeyExA(v4, "GBG", 0, 0x20019u, hKey) )
    {
      cchClass = 9;
      v19 = RegQueryInfoKeyA(hKey[0], Class, &cchClass, 0, 0, 0, 0, 0, 0, 0, 0, 0);
      RegCloseKey(hKey[0]);
      if ( !v19 )
      {
        for ( k = 0; k < 8; k += 2 )
        {
          v21 = Class[k];
          if ( (unsigned __int8)(v21 - 48) > 9u )
          {
            if ( (unsigned __int8)(v21 - 97) > 5u )
            {
              if ( (unsigned __int8)(v21 - 65) > 5u )
                v22 = -1;
              else
                v22 = v21 - 55;
            }
            else
            {
              v22 = v21 - 87;
            }
          }
          else
          {
            v22 = v21 - 48;
          }
          v23 = Class[k + 1];
          if ( (unsigned __int8)(v23 - 48) > 9u )
          {
            if ( (unsigned __int8)(v23 - 97) > 5u )
            {
              if ( (unsigned __int8)(v23 - 65) > 5u )
                v24 = -1;
              else
                v24 = v23 - 55;
            }
            else
            {
              v24 = v23 - 87;
            }
          }
          else
          {
            v24 = v23 - 48;
          }
          if ( (unsigned __int8)v22 > 0xFu || (unsigned __int8)v24 > 0xFu )
            goto LABEL_86;
          *(_BYTE *)v5 = v24 + 16 * v22;
          v5 = (__int128 *)((char *)v5 + 1);
        }
      }
    }
    if ( !RegOpenKeyExA(v4, "Data", 0, 0x20019u, hKey) )
    {
      cchClass = 9;
      v25 = RegQueryInfoKeyA(hKey[0], Class, &cchClass, 0, 0, 0, 0, 0, 0, 0, 0, 0);
      RegCloseKey(hKey[0]);
      if ( !v25 )
      {
        for ( m = 0; m < 8; m += 2 )
        {
          v27 = Class[m];
          if ( (unsigned __int8)(v27 - 48) > 9u )
          {
            if ( (unsigned __int8)(v27 - 97) > 5u )
            {
              if ( (unsigned __int8)(v27 - 65) > 5u )
                v28 = -1;
              else
                v28 = v27 - 55;
            }
            else
            {
              v28 = v27 - 87;
            }
          }
          else
          {
            v28 = v27 - 48;
          }
          v29 = Class[m + 1];
          if ( (unsigned __int8)(v29 - 48) > 9u )
          {
            if ( (unsigned __int8)(v29 - 97) > 5u )
            {
              if ( (unsigned __int8)(v29 - 65) > 5u )
                v30 = -1;
              else
                v30 = v29 - 55;
            }
            else
            {
              v30 = v29 - 87;
            }
          }
          else
          {
            v30 = v29 - 48;
          }
          if ( (unsigned __int8)v28 > 0xFu || (unsigned __int8)v30 > 0xFu )
            goto LABEL_86;
          *(_BYTE *)v5 = v30 + 16 * v28;
          v5 = (__int128 *)((char *)v5 + 1);
        }
      }
    }
    for ( n = 0; n != 16; ++n )
    {
      v32 = Class[n - 16];
      v33 = *((unsigned __int8 *)qword_180022530 + n);
      *(_BYTE *)(v33 + a2) = v32;
    }
LABEL_89:
    RegCloseKey(v4);
    LOBYTE(v3) = v6;
  }
  return (char)v3;
}

```

## disassembly

```asm
0x180016900  push    rbp
0x180016902  push    rbx
0x180016903  push    rsi
0x180016904  push    rdi
0x180016905  push    r12
0x180016907  push    r13
0x180016909  push    r14
0x18001690b  push    r15
0x18001690d  lea     rbp, [rsp-1Fh]
0x180016912  sub     rsp, 0A8h
0x180016919  mov     rax, cs:__security_cookie
0x180016920  xor     rax, rsp
0x180016923  mov     [rbp+57h+var_48], rax
0x180016927  xorps   xmm0, xmm0
0x18001692a  xor     r12d, r12d
0x18001692d  movups  [rbp+57h+var_68], xmm0
0x180016931  mov     [rbp+57h+hKey], r12
0x180016935  mov     r15, rdx
0x180016938  mov     [rbp+57h+cchClass], r12d
0x18001693c  call    OpenLsaKey
0x180016941  mov     r14, rax
0x180016944  test    rax, rax
0x180016947  jz      loc_180016E09
0x18001694d  lea     rax, [rbp+57h+hKey]
0x180016951  mov     r9d, 20019h; samDesired
0x180016957  xor     r8d, r8d; ulOptions
0x18001695a  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18001695f  lea     rdx, aJd; "JD"
0x180016966  mov     rcx, r14; hKey
0x180016969  lea     rsi, [rbp+57h+var_68]
0x18001696d  call    cs:__imp_RegOpenKeyExA
0x180016973  mov     r13b, 5
0x180016976  mov     edi, 1
0x18001697b  test    eax, eax
0x18001697d  jnz     loc_180016A76
0x180016983  mov     rcx, [rbp+57h+hKey]; hKey
0x180016987  lea     r8, [rbp+57h+cchClass]; lpcchClass
0x18001698b  mov     [rsp+0E0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180016990  lea     rdx, [rbp+57h+Class]; lpClass
0x180016994  mov     [rsp+0E0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180016999  xor     r9d, r9d; lpReserved
0x18001699c  mov     [rsp+0E0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x1800169a1  mov     [rsp+0E0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x1800169a6  mov     [rsp+0E0h+lpcValues], r12; lpcValues
0x1800169ab  mov     [rsp+0E0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x1800169b0  mov     [rsp+0E0h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x1800169b5  mov     [rsp+0E0h+phkResult], r12; lpcSubKeys
0x1800169ba  mov     [rbp+57h+cchClass], 9
0x1800169c1  call    cs:__imp_RegQueryInfoKeyA
0x1800169c7  mov     rcx, [rbp+57h+hKey]; hKey
0x1800169cb  mov     ebx, eax
0x1800169cd  call    cs:__imp_RegCloseKey
0x1800169d3  test    ebx, ebx
0x1800169d5  jnz     loc_180016A76
0x1800169db  mov     r9d, r12d
0x1800169de  cmp     r9d, 8
0x1800169e2  jnb     loc_180016A76
0x1800169e8  mov     eax, r9d
0x1800169eb  mov     dl, [rbp+rax+57h+Class]
0x1800169ef  lea     eax, [rdx-30h]
0x1800169f2  cmp     al, 9
0x1800169f4  ja      short loc_1800169FB
0x1800169f6  sub     dl, 30h ; '0'
0x1800169f9  jmp     short loc_180016A17
0x1800169fb  lea     eax, [rdx-61h]
0x1800169fe  cmp     al, r13b
0x180016a01  ja      short loc_180016A08
0x180016a03  sub     dl, 57h ; 'W'
0x180016a06  jmp     short loc_180016A17
0x180016a08  lea     eax, [rdx-41h]
0x180016a0b  cmp     al, r13b
0x180016a0e  ja      short loc_180016A15
0x180016a10  sub     dl, 37h ; '7'
0x180016a13  jmp     short loc_180016A17
0x180016a15  mov     dl, 0FFh
0x180016a17  lea     eax, [r9+1]
0x180016a1b  mov     r8b, [rbp+rax+57h+Class]
0x180016a20  lea     eax, [r8-30h]
0x180016a24  cmp     al, 9
0x180016a26  ja      short loc_180016A2E
0x180016a28  sub     r8b, 30h ; '0'
0x180016a2c  jmp     short loc_180016A4F
0x180016a2e  lea     eax, [r8-61h]
0x180016a32  cmp     al, r13b
0x180016a35  ja      short loc_180016A3D
0x180016a37  sub     r8b, 57h ; 'W'
0x180016a3b  jmp     short loc_180016A4F
0x180016a3d  lea     eax, [r8-41h]
0x180016a41  cmp     al, r13b
0x180016a44  ja      short loc_180016A4C
0x180016a46  sub     r8b, 37h ; '7'
0x180016a4a  jmp     short loc_180016A4F
0x180016a4c  mov     r8b, 0FFh
0x180016a4f  cmp     dl, 0Fh
0x180016a52  ja      loc_180016DD7
0x180016a58  cmp     r8b, 0Fh
0x180016a5c  ja      loc_180016DD7
0x180016a62  shl     dl, 4
0x180016a65  add     dl, r8b
0x180016a68  mov     [rsi], dl
0x180016a6a  add     rsi, rdi
0x180016a6d  add     r9d, 2
0x180016a71  jmp     loc_1800169DE
0x180016a76  lea     rax, [rbp+57h+hKey]
0x180016a7a  mov     r9d, 20019h; samDesired
0x180016a80  xor     r8d, r8d; ulOptions
0x180016a83  mov     [rsp+0E0h+phkResult], rax; phkResult
0x180016a88  lea     rdx, aSkew1; "Skew1"
0x180016a8f  mov     rcx, r14; hKey
0x180016a92  call    cs:__imp_RegOpenKeyExA
0x180016a98  test    eax, eax
0x180016a9a  jnz     loc_180016B99
0x180016aa0  mov     rcx, [rbp+57h+hKey]; hKey
0x180016aa4  lea     r8, [rbp+57h+cchClass]; lpcchClass
0x180016aa8  mov     [rsp+0E0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180016aad  lea     rdx, [rbp+57h+Class]; lpClass
0x180016ab1  mov     [rsp+0E0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180016ab6  xor     r9d, r9d; lpReserved
0x180016ab9  mov     [rsp+0E0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x180016abe  mov     [rsp+0E0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x180016ac3  mov     [rsp+0E0h+lpcValues], r12; lpcValues
0x180016ac8  mov     [rsp+0E0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x180016acd  mov     [rsp+0E0h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x180016ad2  mov     [rsp+0E0h+phkResult], r12; lpcSubKeys
0x180016ad7  mov     [rbp+57h+cchClass], 9
0x180016ade  call    cs:__imp_RegQueryInfoKeyA
0x180016ae4  mov     rcx, [rbp+57h+hKey]; hKey
0x180016ae8  mov     ebx, eax
0x180016aea  call    cs:__imp_RegCloseKey
0x180016af0  test    ebx, ebx
0x180016af2  jnz     loc_180016B99
0x180016af8  mov     r9d, r12d
0x180016afb  mov     r10b, 30h ; '0'
0x180016afe  cmp     r9d, 8
0x180016b02  jnb     loc_180016B99
0x180016b08  mov     eax, r9d
0x180016b0b  mov     dl, [rbp+rax+57h+Class]
0x180016b0f  mov     al, dl
0x180016b11  sub     al, r10b
0x180016b14  cmp     al, 9
0x180016b16  ja      short loc_180016B1D
0x180016b18  sub     dl, r10b
0x180016b1b  jmp     short loc_180016B39
0x180016b1d  lea     eax, [rdx-61h]
0x180016b20  cmp     al, r13b
0x180016b23  ja      short loc_180016B2A
0x180016b25  sub     dl, 57h ; 'W'
0x180016b28  jmp     short loc_180016B39
0x180016b2a  lea     eax, [rdx-41h]
0x180016b2d  cmp     al, r13b
0x180016b30  ja      short loc_180016B37
0x180016b32  sub     dl, 37h ; '7'
0x180016b35  jmp     short loc_180016B39
0x180016b37  mov     dl, 0FFh
0x180016b39  lea     eax, [r9+1]
0x180016b3d  mov     r8b, [rbp+rax+57h+Class]
0x180016b42  mov     al, r8b
0x180016b45  sub     al, r10b
0x180016b48  cmp     al, 9
0x180016b4a  ja      short loc_180016B51
0x180016b4c  sub     r8b, r10b
0x180016b4f  jmp     short loc_180016B72
0x180016b51  lea     eax, [r8-61h]
0x180016b55  cmp     al, r13b
0x180016b58  ja      short loc_180016B60
0x180016b5a  sub     r8b, 57h ; 'W'
0x180016b5e  jmp     short loc_180016B72
0x180016b60  lea     eax, [r8-41h]
0x180016b64  cmp     al, r13b
0x180016b67  ja      short loc_180016B6F
0x180016b69  sub     r8b, 37h ; '7'
0x180016b6d  jmp     short loc_180016B72
0x180016b6f  mov     r8b, 0FFh
0x180016b72  cmp     dl, 0Fh
0x180016b75  ja      loc_180016DD7
0x180016b7b  cmp     r8b, 0Fh
0x180016b7f  ja      loc_180016DD7
0x180016b85  shl     dl, 4
0x180016b88  add     dl, r8b
0x180016b8b  mov     [rsi], dl
0x180016b8d  add     rsi, rdi
0x180016b90  add     r9d, 2
0x180016b94  jmp     loc_180016AFE
0x180016b99  lea     rax, [rbp+57h+hKey]
0x180016b9d  mov     r9d, 20019h; samDesired
0x180016ba3  xor     r8d, r8d; ulOptions
0x180016ba6  mov     [rsp+0E0h+phkResult], rax; phkResult
0x180016bab  lea     rdx, aGbg; "GBG"
0x180016bb2  mov     rcx, r14; hKey
0x180016bb5  call    cs:__imp_RegOpenKeyExA
0x180016bbb  test    eax, eax
0x180016bbd  jnz     loc_180016CBC
0x180016bc3  mov     rcx, [rbp+57h+hKey]; hKey
0x180016bc7  lea     r8, [rbp+57h+cchClass]; lpcchClass
0x180016bcb  mov     [rsp+0E0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180016bd0  lea     rdx, [rbp+57h+Class]; lpClass
0x180016bd4  mov     [rsp+0E0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180016bd9  xor     r9d, r9d; lpReserved
0x180016bdc  mov     [rsp+0E0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x180016be1  mov     [rsp+0E0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x180016be6  mov     [rsp+0E0h+lpcValues], r12; lpcValues
0x180016beb  mov     [rsp+0E0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x180016bf0  mov     [rsp+0E0h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x180016bf5  mov     [rsp+0E0h+phkResult], r12; lpcSubKeys
0x180016bfa  mov     [rbp+57h+cchClass], 9
0x180016c01  call    cs:__imp_RegQueryInfoKeyA
0x180016c07  mov     rcx, [rbp+57h+hKey]; hKey
0x180016c0b  mov     ebx, eax
0x180016c0d  call    cs:__imp_RegCloseKey
0x180016c13  test    ebx, ebx
0x180016c15  jnz     loc_180016CBC
0x180016c1b  mov     r9d, r12d
0x180016c1e  mov     r10b, 30h ; '0'
0x180016c21  cmp     r9d, 8
0x180016c25  jnb     loc_180016CBC
0x180016c2b  mov     eax, r9d
0x180016c2e  mov     dl, [rbp+rax+57h+Class]
0x180016c32  mov     al, dl
0x180016c34  sub     al, r10b
0x180016c37  cmp     al, 9
0x180016c39  ja      short loc_180016C40
0x180016c3b  sub     dl, r10b
0x180016c3e  jmp     short loc_180016C5C
0x180016c40  lea     eax, [rdx-61h]
0x180016c43  cmp     al, r13b
0x180016c46  ja      short loc_180016C4D
0x180016c48  sub     dl, 57h ; 'W'
0x180016c4b  jmp     short loc_180016C5C
0x180016c4d  lea     eax, [rdx-41h]
0x180016c50  cmp     al, r13b
0x180016c53  ja      short loc_180016C5A
0x180016c55  sub     dl, 37h ; '7'
0x180016c58  jmp     short loc_180016C5C
0x180016c5a  mov     dl, 0FFh
0x180016c5c  lea     eax, [r9+1]
0x180016c60  mov     r8b, [rbp+rax+57h+Class]
0x180016c65  mov     al, r8b
0x180016c68  sub     al, r10b
0x180016c6b  cmp     al, 9
0x180016c6d  ja      short loc_180016C74
0x180016c6f  sub     r8b, r10b
0x180016c72  jmp     short loc_180016C95
0x180016c74  lea     eax, [r8-61h]
0x180016c78  cmp     al, r13b
0x180016c7b  ja      short loc_180016C83
0x180016c7d  sub     r8b, 57h ; 'W'
0x180016c81  jmp     short loc_180016C95
0x180016c83  lea     eax, [r8-41h]
0x180016c87  cmp     al, r13b
0x180016c8a  ja      short loc_180016C92
0x180016c8c  sub     r8b, 37h ; '7'
0x180016c90  jmp     short loc_180016C95
0x180016c92  mov     r8b, 0FFh
0x180016c95  cmp     dl, 0Fh
0x180016c98  ja      loc_180016DD7
0x180016c9e  cmp     r8b, 0Fh
0x180016ca2  ja      loc_180016DD7
0x180016ca8  shl     dl, 4
0x180016cab  add     dl, r8b
0x180016cae  mov     [rsi], dl
0x180016cb0  add     rsi, rdi
0x180016cb3  add     r9d, 2
0x180016cb7  jmp     loc_180016C21
0x180016cbc  lea     rax, [rbp+57h+hKey]
0x180016cc0  mov     r9d, 20019h; samDesired
0x180016cc6  xor     r8d, r8d; ulOptions
0x180016cc9  mov     [rsp+0E0h+phkResult], rax; phkResult
0x180016cce  lea     rdx, aData; "Data"
0x180016cd5  mov     rcx, r14; hKey
0x180016cd8  call    cs:__imp_RegOpenKeyExA
0x180016cde  test    eax, eax
0x180016ce0  jnz     loc_180016DDC
0x180016ce6  mov     rcx, [rbp+57h+hKey]; hKey
0x180016cea  lea     r8, [rbp+57h+cchClass]; lpcchClass
0x180016cee  mov     [rsp+0E0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180016cf3  lea     rdx, [rbp+57h+Class]; lpClass
0x180016cf7  mov     [rsp+0E0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180016cfc  xor     r9d, r9d; lpReserved
0x180016cff  mov     [rsp+0E0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x180016d04  mov     [rsp+0E0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x180016d09  mov     [rsp+0E0h+lpcValues], r12; lpcValues
0x180016d0e  mov     [rsp+0E0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x180016d13  mov     [rsp+0E0h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x180016d18  mov     [rsp+0E0h+phkResult], r12; lpcSubKeys
0x180016d1d  mov     [rbp+57h+cchClass], 9
0x180016d24  call    cs:__imp_RegQueryInfoKeyA
0x180016d2a  mov     rcx, [rbp+57h+hKey]; hKey
0x180016d2e  mov     ebx, eax
0x180016d30  call    cs:__imp_RegCloseKey
0x180016d36  test    ebx, ebx
0x180016d38  jnz     loc_180016DDC
0x180016d3e  mov     r9d, r12d
0x180016d41  mov     r10b, 30h ; '0'
0x180016d44  cmp     r9d, 8
0x180016d48  jnb     loc_180016DDC
0x180016d4e  mov     eax, r9d
0x180016d51  mov     dl, [rbp+rax+57h+Class]
0x180016d55  mov     al, dl
0x180016d57  sub     al, r10b
0x180016d5a  cmp     al, 9
  ... truncated ...
```
