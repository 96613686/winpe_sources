# WxpDeObfuscateKey

- ea: `0x1800b5598`
- end: `0x1800b5ac1`
- name: `WxpDeObfuscateKey`
- size: `1321`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180093d5c`

## callees

- `0x18002cd80`
- `0x1800b53c4`
- `0x1800b5598`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800b5605`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800b572a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800b584d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800b5970`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800b5605`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800b572a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800b584d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800b5970`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x1800b5659`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x1800b5776`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x1800b5899`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x1800b59bc`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x1800b5659`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x1800b5776`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x1800b5899`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x1800b59bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b5665`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b5782`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b58a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b59c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b5a98`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b5665`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b5782`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b58a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b59c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b5a98`

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
      v33 = *((unsigned __int8 *)qword_1800D86C0 + n);
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
0x1800b5598  push    rbp
0x1800b559a  push    rbx
0x1800b559b  push    rsi
0x1800b559c  push    rdi
0x1800b559d  push    r12
0x1800b559f  push    r13
0x1800b55a1  push    r14
0x1800b55a3  push    r15
0x1800b55a5  lea     rbp, [rsp-1Fh]
0x1800b55aa  sub     rsp, 0A8h
0x1800b55b1  mov     rax, cs:__security_cookie
0x1800b55b8  xor     rax, rsp
0x1800b55bb  mov     [rbp+57h+var_48], rax
0x1800b55bf  xorps   xmm0, xmm0
0x1800b55c2  xor     r12d, r12d
0x1800b55c5  movups  [rbp+57h+var_68], xmm0
0x1800b55c9  mov     [rbp+57h+hKey], r12
0x1800b55cd  mov     r15, rdx
0x1800b55d0  mov     [rbp+57h+cchClass], r12d
0x1800b55d4  call    OpenLsaKey
0x1800b55d9  mov     r14, rax
0x1800b55dc  test    rax, rax
0x1800b55df  jz      loc_1800B5AA1
0x1800b55e5  lea     rax, [rbp+57h+hKey]
0x1800b55e9  mov     r9d, 20019h; samDesired
0x1800b55ef  xor     r8d, r8d; ulOptions
0x1800b55f2  mov     [rsp+0E0h+phkResult], rax; phkResult
0x1800b55f7  lea     rdx, aJd; "JD"
0x1800b55fe  mov     rcx, r14; hKey
0x1800b5601  lea     rsi, [rbp+57h+var_68]
0x1800b5605  call    cs:__imp_RegOpenKeyExA
0x1800b560b  mov     r13b, 5
0x1800b560e  mov     edi, 1
0x1800b5613  test    eax, eax
0x1800b5615  jnz     loc_1800B570E
0x1800b561b  mov     rcx, [rbp+57h+hKey]; hKey
0x1800b561f  lea     r8, [rbp+57h+cchClass]; lpcchClass
0x1800b5623  mov     [rsp+0E0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x1800b5628  lea     rdx, [rbp+57h+Class]; lpClass
0x1800b562c  mov     [rsp+0E0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x1800b5631  xor     r9d, r9d; lpReserved
0x1800b5634  mov     [rsp+0E0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x1800b5639  mov     [rsp+0E0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x1800b563e  mov     [rsp+0E0h+lpcValues], r12; lpcValues
0x1800b5643  mov     [rsp+0E0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x1800b5648  mov     [rsp+0E0h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x1800b564d  mov     [rsp+0E0h+phkResult], r12; lpcSubKeys
0x1800b5652  mov     [rbp+57h+cchClass], 9
0x1800b5659  call    cs:__imp_RegQueryInfoKeyA
0x1800b565f  mov     rcx, [rbp+57h+hKey]; hKey
0x1800b5663  mov     ebx, eax
0x1800b5665  call    cs:__imp_RegCloseKey
0x1800b566b  test    ebx, ebx
0x1800b566d  jnz     loc_1800B570E
0x1800b5673  mov     r9d, r12d
0x1800b5676  cmp     r9d, 8
0x1800b567a  jnb     loc_1800B570E
0x1800b5680  mov     eax, r9d
0x1800b5683  mov     dl, [rbp+rax+57h+Class]
0x1800b5687  lea     eax, [rdx-30h]
0x1800b568a  cmp     al, 9
0x1800b568c  ja      short loc_1800B5693
0x1800b568e  sub     dl, 30h ; '0'
0x1800b5691  jmp     short loc_1800B56AF
0x1800b5693  lea     eax, [rdx-61h]
0x1800b5696  cmp     al, r13b
0x1800b5699  ja      short loc_1800B56A0
0x1800b569b  sub     dl, 57h ; 'W'
0x1800b569e  jmp     short loc_1800B56AF
0x1800b56a0  lea     eax, [rdx-41h]
0x1800b56a3  cmp     al, r13b
0x1800b56a6  ja      short loc_1800B56AD
0x1800b56a8  sub     dl, 37h ; '7'
0x1800b56ab  jmp     short loc_1800B56AF
0x1800b56ad  mov     dl, 0FFh
0x1800b56af  lea     eax, [r9+1]
0x1800b56b3  mov     r8b, [rbp+rax+57h+Class]
0x1800b56b8  lea     eax, [r8-30h]
0x1800b56bc  cmp     al, 9
0x1800b56be  ja      short loc_1800B56C6
0x1800b56c0  sub     r8b, 30h ; '0'
0x1800b56c4  jmp     short loc_1800B56E7
0x1800b56c6  lea     eax, [r8-61h]
0x1800b56ca  cmp     al, r13b
0x1800b56cd  ja      short loc_1800B56D5
0x1800b56cf  sub     r8b, 57h ; 'W'
0x1800b56d3  jmp     short loc_1800B56E7
0x1800b56d5  lea     eax, [r8-41h]
0x1800b56d9  cmp     al, r13b
0x1800b56dc  ja      short loc_1800B56E4
0x1800b56de  sub     r8b, 37h ; '7'
0x1800b56e2  jmp     short loc_1800B56E7
0x1800b56e4  mov     r8b, 0FFh
0x1800b56e7  cmp     dl, 0Fh
0x1800b56ea  ja      loc_1800B5A6F
0x1800b56f0  cmp     r8b, 0Fh
0x1800b56f4  ja      loc_1800B5A6F
0x1800b56fa  shl     dl, 4
0x1800b56fd  add     dl, r8b
0x1800b5700  mov     [rsi], dl
0x1800b5702  add     rsi, rdi
0x1800b5705  add     r9d, 2
0x1800b5709  jmp     loc_1800B5676
0x1800b570e  lea     rax, [rbp+57h+hKey]
0x1800b5712  mov     r9d, 20019h; samDesired
0x1800b5718  xor     r8d, r8d; ulOptions
0x1800b571b  mov     [rsp+0E0h+phkResult], rax; phkResult
0x1800b5720  lea     rdx, aSkew1; "Skew1"
0x1800b5727  mov     rcx, r14; hKey
0x1800b572a  call    cs:__imp_RegOpenKeyExA
0x1800b5730  test    eax, eax
0x1800b5732  jnz     loc_1800B5831
0x1800b5738  mov     rcx, [rbp+57h+hKey]; hKey
0x1800b573c  lea     r8, [rbp+57h+cchClass]; lpcchClass
0x1800b5740  mov     [rsp+0E0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x1800b5745  lea     rdx, [rbp+57h+Class]; lpClass
0x1800b5749  mov     [rsp+0E0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x1800b574e  xor     r9d, r9d; lpReserved
0x1800b5751  mov     [rsp+0E0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x1800b5756  mov     [rsp+0E0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x1800b575b  mov     [rsp+0E0h+lpcValues], r12; lpcValues
0x1800b5760  mov     [rsp+0E0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x1800b5765  mov     [rsp+0E0h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x1800b576a  mov     [rsp+0E0h+phkResult], r12; lpcSubKeys
0x1800b576f  mov     [rbp+57h+cchClass], 9
0x1800b5776  call    cs:__imp_RegQueryInfoKeyA
0x1800b577c  mov     rcx, [rbp+57h+hKey]; hKey
0x1800b5780  mov     ebx, eax
0x1800b5782  call    cs:__imp_RegCloseKey
0x1800b5788  test    ebx, ebx
0x1800b578a  jnz     loc_1800B5831
0x1800b5790  mov     r9d, r12d
0x1800b5793  mov     r10b, 30h ; '0'
0x1800b5796  cmp     r9d, 8
0x1800b579a  jnb     loc_1800B5831
0x1800b57a0  mov     eax, r9d
0x1800b57a3  mov     dl, [rbp+rax+57h+Class]
0x1800b57a7  mov     al, dl
0x1800b57a9  sub     al, r10b
0x1800b57ac  cmp     al, 9
0x1800b57ae  ja      short loc_1800B57B5
0x1800b57b0  sub     dl, r10b
0x1800b57b3  jmp     short loc_1800B57D1
0x1800b57b5  lea     eax, [rdx-61h]
0x1800b57b8  cmp     al, r13b
0x1800b57bb  ja      short loc_1800B57C2
0x1800b57bd  sub     dl, 57h ; 'W'
0x1800b57c0  jmp     short loc_1800B57D1
0x1800b57c2  lea     eax, [rdx-41h]
0x1800b57c5  cmp     al, r13b
0x1800b57c8  ja      short loc_1800B57CF
0x1800b57ca  sub     dl, 37h ; '7'
0x1800b57cd  jmp     short loc_1800B57D1
0x1800b57cf  mov     dl, 0FFh
0x1800b57d1  lea     eax, [r9+1]
0x1800b57d5  mov     r8b, [rbp+rax+57h+Class]
0x1800b57da  mov     al, r8b
0x1800b57dd  sub     al, r10b
0x1800b57e0  cmp     al, 9
0x1800b57e2  ja      short loc_1800B57E9
0x1800b57e4  sub     r8b, r10b
0x1800b57e7  jmp     short loc_1800B580A
0x1800b57e9  lea     eax, [r8-61h]
0x1800b57ed  cmp     al, r13b
0x1800b57f0  ja      short loc_1800B57F8
0x1800b57f2  sub     r8b, 57h ; 'W'
0x1800b57f6  jmp     short loc_1800B580A
0x1800b57f8  lea     eax, [r8-41h]
0x1800b57fc  cmp     al, r13b
0x1800b57ff  ja      short loc_1800B5807
0x1800b5801  sub     r8b, 37h ; '7'
0x1800b5805  jmp     short loc_1800B580A
0x1800b5807  mov     r8b, 0FFh
0x1800b580a  cmp     dl, 0Fh
0x1800b580d  ja      loc_1800B5A6F
0x1800b5813  cmp     r8b, 0Fh
0x1800b5817  ja      loc_1800B5A6F
0x1800b581d  shl     dl, 4
0x1800b5820  add     dl, r8b
0x1800b5823  mov     [rsi], dl
0x1800b5825  add     rsi, rdi
0x1800b5828  add     r9d, 2
0x1800b582c  jmp     loc_1800B5796
0x1800b5831  lea     rax, [rbp+57h+hKey]
0x1800b5835  mov     r9d, 20019h; samDesired
0x1800b583b  xor     r8d, r8d; ulOptions
0x1800b583e  mov     [rsp+0E0h+phkResult], rax; phkResult
0x1800b5843  lea     rdx, aGbg; "GBG"
0x1800b584a  mov     rcx, r14; hKey
0x1800b584d  call    cs:__imp_RegOpenKeyExA
0x1800b5853  test    eax, eax
0x1800b5855  jnz     loc_1800B5954
0x1800b585b  mov     rcx, [rbp+57h+hKey]; hKey
0x1800b585f  lea     r8, [rbp+57h+cchClass]; lpcchClass
0x1800b5863  mov     [rsp+0E0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x1800b5868  lea     rdx, [rbp+57h+Class]; lpClass
0x1800b586c  mov     [rsp+0E0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x1800b5871  xor     r9d, r9d; lpReserved
0x1800b5874  mov     [rsp+0E0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x1800b5879  mov     [rsp+0E0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x1800b587e  mov     [rsp+0E0h+lpcValues], r12; lpcValues
0x1800b5883  mov     [rsp+0E0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x1800b5888  mov     [rsp+0E0h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x1800b588d  mov     [rsp+0E0h+phkResult], r12; lpcSubKeys
0x1800b5892  mov     [rbp+57h+cchClass], 9
0x1800b5899  call    cs:__imp_RegQueryInfoKeyA
0x1800b589f  mov     rcx, [rbp+57h+hKey]; hKey
0x1800b58a3  mov     ebx, eax
0x1800b58a5  call    cs:__imp_RegCloseKey
0x1800b58ab  test    ebx, ebx
0x1800b58ad  jnz     loc_1800B5954
0x1800b58b3  mov     r9d, r12d
0x1800b58b6  mov     r10b, 30h ; '0'
0x1800b58b9  cmp     r9d, 8
0x1800b58bd  jnb     loc_1800B5954
0x1800b58c3  mov     eax, r9d
0x1800b58c6  mov     dl, [rbp+rax+57h+Class]
0x1800b58ca  mov     al, dl
0x1800b58cc  sub     al, r10b
0x1800b58cf  cmp     al, 9
0x1800b58d1  ja      short loc_1800B58D8
0x1800b58d3  sub     dl, r10b
0x1800b58d6  jmp     short loc_1800B58F4
0x1800b58d8  lea     eax, [rdx-61h]
0x1800b58db  cmp     al, r13b
0x1800b58de  ja      short loc_1800B58E5
0x1800b58e0  sub     dl, 57h ; 'W'
0x1800b58e3  jmp     short loc_1800B58F4
0x1800b58e5  lea     eax, [rdx-41h]
0x1800b58e8  cmp     al, r13b
0x1800b58eb  ja      short loc_1800B58F2
0x1800b58ed  sub     dl, 37h ; '7'
0x1800b58f0  jmp     short loc_1800B58F4
0x1800b58f2  mov     dl, 0FFh
0x1800b58f4  lea     eax, [r9+1]
0x1800b58f8  mov     r8b, [rbp+rax+57h+Class]
0x1800b58fd  mov     al, r8b
0x1800b5900  sub     al, r10b
0x1800b5903  cmp     al, 9
0x1800b5905  ja      short loc_1800B590C
0x1800b5907  sub     r8b, r10b
0x1800b590a  jmp     short loc_1800B592D
0x1800b590c  lea     eax, [r8-61h]
0x1800b5910  cmp     al, r13b
0x1800b5913  ja      short loc_1800B591B
0x1800b5915  sub     r8b, 57h ; 'W'
0x1800b5919  jmp     short loc_1800B592D
0x1800b591b  lea     eax, [r8-41h]
0x1800b591f  cmp     al, r13b
0x1800b5922  ja      short loc_1800B592A
0x1800b5924  sub     r8b, 37h ; '7'
0x1800b5928  jmp     short loc_1800B592D
0x1800b592a  mov     r8b, 0FFh
0x1800b592d  cmp     dl, 0Fh
0x1800b5930  ja      loc_1800B5A6F
0x1800b5936  cmp     r8b, 0Fh
0x1800b593a  ja      loc_1800B5A6F
0x1800b5940  shl     dl, 4
0x1800b5943  add     dl, r8b
0x1800b5946  mov     [rsi], dl
0x1800b5948  add     rsi, rdi
0x1800b594b  add     r9d, 2
0x1800b594f  jmp     loc_1800B58B9
0x1800b5954  lea     rax, [rbp+57h+hKey]
0x1800b5958  mov     r9d, 20019h; samDesired
0x1800b595e  xor     r8d, r8d; ulOptions
0x1800b5961  mov     [rsp+0E0h+phkResult], rax; phkResult
0x1800b5966  lea     rdx, aData; "Data"
0x1800b596d  mov     rcx, r14; hKey
0x1800b5970  call    cs:__imp_RegOpenKeyExA
0x1800b5976  test    eax, eax
0x1800b5978  jnz     loc_1800B5A74
0x1800b597e  mov     rcx, [rbp+57h+hKey]; hKey
0x1800b5982  lea     r8, [rbp+57h+cchClass]; lpcchClass
0x1800b5986  mov     [rsp+0E0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x1800b598b  lea     rdx, [rbp+57h+Class]; lpClass
0x1800b598f  mov     [rsp+0E0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x1800b5994  xor     r9d, r9d; lpReserved
0x1800b5997  mov     [rsp+0E0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x1800b599c  mov     [rsp+0E0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x1800b59a1  mov     [rsp+0E0h+lpcValues], r12; lpcValues
0x1800b59a6  mov     [rsp+0E0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x1800b59ab  mov     [rsp+0E0h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x1800b59b0  mov     [rsp+0E0h+phkResult], r12; lpcSubKeys
0x1800b59b5  mov     [rbp+57h+cchClass], 9
0x1800b59bc  call    cs:__imp_RegQueryInfoKeyA
0x1800b59c2  mov     rcx, [rbp+57h+hKey]; hKey
0x1800b59c6  mov     ebx, eax
0x1800b59c8  call    cs:__imp_RegCloseKey
0x1800b59ce  test    ebx, ebx
0x1800b59d0  jnz     loc_1800B5A74
0x1800b59d6  mov     r9d, r12d
0x1800b59d9  mov     r10b, 30h ; '0'
0x1800b59dc  cmp     r9d, 8
0x1800b59e0  jnb     loc_1800B5A74
0x1800b59e6  mov     eax, r9d
0x1800b59e9  mov     dl, [rbp+rax+57h+Class]
0x1800b59ed  mov     al, dl
0x1800b59ef  sub     al, r10b
0x1800b59f2  cmp     al, 9
  ... truncated ...
```
