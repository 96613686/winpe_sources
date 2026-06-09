# RegisterAClassAndExt(SClassEntry const &,wchar_t const *,int,int)

- ea: `0x180009894`
- end: `0x180009b65`
- name: `?RegisterAClassAndExt@@YAJAEBUSClassEntry@@PEB_WHH@Z`
- size: `721`
- prototype: `__int64 __fastcall(const struct SClassEntry *, const wchar_t *, int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18000cff4`

## callees

- `0x180001e40`
- `0x180009490`
- `0x180009894`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009a49`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009ace`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009a49`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009ace`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009ae0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009af3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009b3e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009ae0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009af3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009b3e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800099a7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180009a9c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800099a7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180009a9c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800099e9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800099e9`

## pseudocode

```c
__int64 __fastcall RegisterAClassAndExt(const struct SClassEntry *a1, const wchar_t *a2, int a3)
{
  WCHAR *v4; // r8
  __int64 v5; // rdx
  __int64 v7; // rcx
  __int64 v8; // rax
  WCHAR *v9; // r9
  WCHAR *v10; // r8
  unsigned int v11; // ebx
  WCHAR *v12; // rcx
  WCHAR *v13; // rdx
  WCHAR *v14; // rcx
  LSTATUS v15; // eax
  const BYTE *v16; // rcx
  __int64 v17; // rax
  WCHAR *v18; // r8
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cbData; // [rsp+5Ch] [rbp-A4h] BYREF
  DWORD Type; // [rsp+60h] [rbp-A0h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-98h] BYREF
  WCHAR SubKey[264]; // [rsp+70h] [rbp-90h] BYREF

  dwDisposition = 0;
  v4 = *(WCHAR **)a1;
  v5 = -1;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  Type = 0;
  v7 = 2147483646;
  cbData = 0;
  v8 = 260;
  if ( v4 )
  {
    v13 = SubKey;
    do
    {
      if ( !v7 )
        break;
      if ( !*v4 )
        break;
      *v13++ = *v4++;
      --v7;
      --v8;
    }
    while ( v8 );
    v14 = v13 - 1;
    if ( v8 )
      v14 = v13;
    *v14 = 0;
    v11 = RegCreateKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0, 0, 0x2001Fu, 0, &hKey, &dwDisposition);
    if ( v11 )
      goto LABEL_38;
    if ( dwDisposition == 2 )
    {
      cbData = 520;
      v15 = RegQueryValueExW(hKey, 0, 0, &Type, (LPBYTE)SubKey, &cbData);
      v11 = v15;
      if ( !v15 )
      {
        if ( Type != 1 )
        {
          v11 = -2147467259;
          goto LABEL_38;
        }
LABEL_27:
        phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
        v11 = RegCreateKeyExW(hKey, L"PersistentHandler", 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
        if ( !v11 )
        {
          v11 = RegSetValueExW(phkResult, 0, 0, 1u, L"{2e2294a9-50d7-4fe7-a09f-e6492e185884}", 0x4Eu);
          if ( phkResult != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
            RegCloseKey(phkResult);
          v5 = (__int64)hKey;
          if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
          {
            RegCloseKey(hKey);
            v5 = -1;
            hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
          }
          if ( v11 )
            goto LABEL_39;
          goto LABEL_33;
        }
LABEL_38:
        v5 = (__int64)hKey;
        goto LABEL_39;
      }
      if ( v15 == 2 )
      {
        SubKey[0] = 0;
        v11 = 0;
      }
    }
    if ( !a3 )
    {
      v16 = (const BYTE *)*((_QWORD *)a1 + 1);
      v17 = -1;
      do
        ++v17;
      while ( *(_WORD *)&v16[2 * v17] );
      v11 = RegSetValueExW(hKey, 0, 0, 1u, v16, 2 * v17 + 2);
      SubKey[0] = 0;
    }
    if ( v11 )
      goto LABEL_38;
    goto LABEL_27;
  }
  v9 = (WCHAR *)*((_QWORD *)a1 + 1);
  v10 = SubKey;
  v11 = 0;
  do
  {
    if ( !v7 )
      break;
    if ( !*v9 )
      break;
    *v10++ = *v9++;
    --v7;
    --v8;
  }
  while ( v8 );
  v12 = v10 - 1;
  if ( v8 )
    v12 = v10;
  *v12 = 0;
LABEL_33:
  if ( SubKey[0] || !a3 )
  {
    v18 = SubKey;
    if ( !SubKey[0] )
      v18 = 0;
    v11 = RegisterAClass(a1, (const wchar_t *)v5, v18, a3);
    goto LABEL_38;
  }
LABEL_39:
  if ( v5 != -1 )
    RegCloseKey((HKEY)v5);
  return v11;
}

```

## disassembly

```asm
0x180009894  push    rbp
0x180009896  push    rbx
0x180009897  push    rsi
0x180009898  push    rdi
0x180009899  push    r14
0x18000989b  push    r15
0x18000989d  lea     rbp, [rsp-198h]
0x1800098a5  sub     rsp, 298h
0x1800098ac  mov     rax, cs:__security_cookie
0x1800098b3  xor     rax, rsp
0x1800098b6  mov     [rbp+1C0h+var_40], rax
0x1800098bd  xor     r14d, r14d
0x1800098c0  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800098c4  mov     esi, r8d
0x1800098c7  mov     [rsp+2C0h+dwDisposition], r14d
0x1800098cc  mov     r8, [rcx]
0x1800098cf  mov     rdx, r15
0x1800098d2  mov     [rsp+2C0h+hKey], rdx
0x1800098d7  mov     rdi, rcx
0x1800098da  mov     [rsp+2C0h+Type], r14d
0x1800098df  mov     ecx, 7FFFFFFEh
0x1800098e4  mov     [rsp+2C0h+cbData], r14d
0x1800098e9  mov     eax, 104h
0x1800098ee  test    r8, r8
0x1800098f1  jnz     short loc_180009937
0x1800098f3  mov     r9, [rdi+8]
0x1800098f7  lea     r8, [rsp+2C0h+SubKey]
0x1800098fc  mov     ebx, r14d
0x1800098ff  test    rcx, rcx
0x180009902  jz      short loc_180009923
0x180009904  movzx   r10d, word ptr [r9]
0x180009908  test    r10w, r10w
0x18000990c  jz      short loc_180009923
0x18000990e  mov     [r8], r10w
0x180009912  add     r9, 2
0x180009916  add     r8, 2
0x18000991a  dec     rcx
0x18000991d  sub     rax, 1
0x180009921  jnz     short loc_1800098FF
0x180009923  test    rax, rax
0x180009926  lea     rcx, [r8-2]
0x18000992a  cmovnz  rcx, r8
0x18000992e  mov     [rcx], r14w
0x180009932  jmp     loc_180009B05
0x180009937  lea     rdx, [rsp+2C0h+SubKey]
0x18000993c  test    rcx, rcx
0x18000993f  jz      short loc_180009960
0x180009941  movzx   r9d, word ptr [r8]
0x180009945  test    r9w, r9w
0x180009949  jz      short loc_180009960
0x18000994b  mov     [rdx], r9w
0x18000994f  add     r8, 2
0x180009953  add     rdx, 2
0x180009957  dec     rcx
0x18000995a  sub     rax, 1
0x18000995e  jnz     short loc_18000993C
0x180009960  test    rax, rax
0x180009963  lea     rcx, [rdx-2]
0x180009967  lea     rax, [rsp+2C0h+dwDisposition]
0x18000996c  cmovnz  rcx, rdx
0x180009970  mov     [rsp+2C0h+lpdwDisposition], rax; lpdwDisposition
0x180009975  lea     rax, [rsp+2C0h+hKey]
0x18000997a  xor     r9d, r9d; lpClass
0x18000997d  mov     [rsp+2C0h+phkResult], rax; phkResult
0x180009982  lea     rdx, [rsp+2C0h+SubKey]; lpSubKey
0x180009987  mov     [rsp+2C0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18000998c  xor     r8d, r8d; Reserved
0x18000998f  mov     [rcx], r14w
0x180009993  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000999a  mov     [rsp+2C0h+samDesired], 2001Fh; samDesired
0x1800099a2  mov     [rsp+2C0h+dwOptions], r14d; dwOptions
0x1800099a7  call    cs:__imp_RegCreateKeyExW
0x1800099ad  mov     ebx, eax
0x1800099af  test    eax, eax
0x1800099b1  jnz     loc_180009B31
0x1800099b7  cmp     [rsp+2C0h+dwDisposition], 2
0x1800099bc  jnz     short loc_180009A14
0x1800099be  mov     rcx, [rsp+2C0h+hKey]; hKey
0x1800099c3  lea     rax, [rsp+2C0h+cbData]
0x1800099c8  mov     qword ptr [rsp+2C0h+samDesired], rax; lpcbData
0x1800099cd  lea     r9, [rsp+2C0h+Type]; lpType
0x1800099d2  lea     rax, [rsp+2C0h+SubKey]
0x1800099d7  mov     [rsp+2C0h+cbData], 208h
0x1800099df  xor     r8d, r8d; lpReserved
0x1800099e2  mov     qword ptr [rsp+2C0h+dwOptions], rax; lpData
0x1800099e7  xor     edx, edx; lpValueName
0x1800099e9  call    cs:__imp_RegQueryValueExW
0x1800099ef  mov     ebx, eax
0x1800099f1  test    eax, eax
0x1800099f3  jnz     short loc_180009A06
0x1800099f5  cmp     [rsp+2C0h+Type], 1
0x1800099fa  jz      short loc_180009A5F
0x1800099fc  mov     ebx, 80004005h
0x180009a01  jmp     loc_180009B31
0x180009a06  cmp     eax, 2
0x180009a09  jnz     short loc_180009A14
0x180009a0b  mov     [rsp+2C0h+SubKey], r14w
0x180009a11  mov     ebx, r14d
0x180009a14  test    esi, esi
0x180009a16  jnz     short loc_180009A57
0x180009a18  mov     rcx, [rdi+8]
0x180009a1c  mov     rax, r15
0x180009a1f  inc     rax
0x180009a22  cmp     [rcx+rax*2], r14w
0x180009a27  jnz     short loc_180009A1F
0x180009a29  lea     eax, ds:2[rax*2]
0x180009a30  mov     r9d, 1; dwType
0x180009a36  mov     [rsp+2C0h+samDesired], eax; cbData
0x180009a3a  xor     r8d, r8d; Reserved
0x180009a3d  mov     qword ptr [rsp+2C0h+dwOptions], rcx; lpData
0x180009a42  xor     edx, edx; lpValueName
0x180009a44  mov     rcx, [rsp+2C0h+hKey]; hKey
0x180009a49  call    cs:__imp_RegSetValueExW
0x180009a4f  mov     ebx, eax
0x180009a51  mov     [rsp+2C0h+SubKey], r14w
0x180009a57  test    ebx, ebx
0x180009a59  jnz     loc_180009B31
0x180009a5f  mov     rcx, [rsp+2C0h+hKey]; hKey
0x180009a64  lea     rax, [rsp+2C0h+dwDisposition]
0x180009a69  mov     [rsp+2C0h+lpdwDisposition], rax; lpdwDisposition
0x180009a6e  lea     rdx, SubKey; "PersistentHandler"
0x180009a75  lea     rax, [rsp+2C0h+var_258]
0x180009a7a  mov     [rsp+2C0h+var_258], r15
0x180009a7f  mov     [rsp+2C0h+phkResult], rax; phkResult
0x180009a84  xor     r9d, r9d; lpClass
0x180009a87  mov     [rsp+2C0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180009a8c  xor     r8d, r8d; Reserved
0x180009a8f  mov     [rsp+2C0h+samDesired], 2001Fh; samDesired
0x180009a97  mov     [rsp+2C0h+dwOptions], r14d; dwOptions
0x180009a9c  call    cs:__imp_RegCreateKeyExW
0x180009aa2  mov     ebx, eax
0x180009aa4  test    eax, eax
0x180009aa6  jnz     loc_180009B31
0x180009aac  mov     rcx, [rsp+2C0h+var_258]; hKey
0x180009ab1  lea     rax, Data; "{2e2294a9-50d7-4fe7-a09f-e6492e185884}"
0x180009ab8  mov     [rsp+2C0h+samDesired], 4Eh ; 'N'; cbData
0x180009ac0  lea     r9d, [rbx+1]; dwType
0x180009ac4  xor     r8d, r8d; Reserved
0x180009ac7  mov     qword ptr [rsp+2C0h+dwOptions], rax; lpData
0x180009acc  xor     edx, edx; lpValueName
0x180009ace  call    cs:__imp_RegSetValueExW
0x180009ad4  mov     rcx, [rsp+2C0h+var_258]; hKey
0x180009ad9  mov     ebx, eax
0x180009adb  cmp     rcx, r15
0x180009ade  jz      short loc_180009AE6
0x180009ae0  call    cs:__imp_RegCloseKey
0x180009ae6  mov     rdx, [rsp+2C0h+hKey]
0x180009aeb  cmp     rdx, r15
0x180009aee  jz      short loc_180009B01
0x180009af0  mov     rcx, rdx; hKey
0x180009af3  call    cs:__imp_RegCloseKey
0x180009af9  mov     rdx, r15; wchar_t *
0x180009afc  mov     [rsp+2C0h+hKey], rdx
0x180009b01  test    ebx, ebx
0x180009b03  jnz     short loc_180009B36
0x180009b05  movzx   r9d, [rsp+2C0h+SubKey]
0x180009b0b  test    r9w, r9w
0x180009b0f  jnz     short loc_180009B15
0x180009b11  test    esi, esi
0x180009b13  jnz     short loc_180009B36
0x180009b15  xor     ecx, ecx
0x180009b17  lea     r8, [rsp+2C0h+SubKey]
0x180009b1c  cmp     cx, r9w
0x180009b20  mov     r9d, esi; int
0x180009b23  mov     rcx, rdi; struct SClassEntry *
0x180009b26  cmovz   r8, r14; wchar_t *
0x180009b2a  call    ?RegisterAClass@@YAJAEBUSClassEntry@@PEB_W1H@Z; RegisterAClass(SClassEntry const &,wchar_t const *,wchar_t const *,int)
0x180009b2f  mov     ebx, eax
0x180009b31  mov     rdx, [rsp+2C0h+hKey]
0x180009b36  cmp     rdx, r15
0x180009b39  jz      short loc_180009B44
0x180009b3b  mov     rcx, rdx; hKey
0x180009b3e  call    cs:__imp_RegCloseKey
0x180009b44  mov     eax, ebx
0x180009b46  mov     rcx, [rbp+1C0h+var_40]
0x180009b4d  xor     rcx, rsp; StackCookie
0x180009b50  call    __security_check_cookie
0x180009b55  add     rsp, 298h
0x180009b5c  pop     r15
0x180009b5e  pop     r14
0x180009b60  pop     rdi
0x180009b61  pop     rsi
0x180009b62  pop     rbx
0x180009b63  pop     rbp
0x180009b64  retn
```
