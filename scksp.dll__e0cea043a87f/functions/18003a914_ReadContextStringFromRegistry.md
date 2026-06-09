# ReadContextStringFromRegistry

- ea: `0x18003a914`
- end: `0x18003ab98`
- name: `ReadContextStringFromRegistry`
- size: `644`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpString@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003a1a4`

## callees

- `0x18000b0b0`
- `0x18000b170`
- `0x18000d9d0`
- `0x18002b140`
- `0x18002c188`
- `0x18003a868`
- `0x18003a914`
- `0x18003c240`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003aa1b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003aa1b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003aa48`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003aaa5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003aa48`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003aaa5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ab6b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ab6b`
- `KERNEL32!lstrlenW` at `0x18003a966`
- `KERNEL32!lstrlenW` at `0x18003a971`
- `KERNEL32!lstrlenW` at `0x18003aae3`
- `KERNEL32!lstrlenW` at `0x18003a966`
- `KERNEL32!lstrlenW` at `0x18003a971`
- `KERNEL32!lstrlenW` at `0x18003aae3`

## pseudocode

```c
__int64 __fastcall ReadContextStringFromRegistry(
        LPCWSTR lpString,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        wchar_t **a5)
{
  int v7; // ebx
  unsigned int v8; // eax
  unsigned int v9; // ecx
  __int64 v10; // rax
  unsigned __int64 v11; // rax
  size_t v12; // rbx
  wchar_t *v13; // rax
  const WCHAR *v14; // r14
  unsigned int v15; // ebx
  wchar_t *v16; // rdi
  size_t v17; // rcx
  BYTE *v18; // rsi
  const wchar_t *v19; // rbx
  unsigned int v20; // eax
  unsigned __int64 v21; // rax
  size_t v22; // r15
  wchar_t *v23; // rax
  DWORD cbData; // [rsp+30h] [rbp-40h] BYREF
  DWORD Type; // [rsp+34h] [rbp-3Ch] BYREF
  HKEY hKey; // [rsp+38h] [rbp-38h] BYREF
  LPCWSTR lpStringa; // [rsp+40h] [rbp-30h] BYREF
  wchar_t pszDest[8]; // [rsp+48h] [rbp-28h] BYREF
  int v30; // [rsp+58h] [rbp-18h]

  v30 = 0;
  hKey = 0;
  cbData = 0;
  *(_OWORD *)pszDest = 0;
  Type = 0;
  lpStringa = 0;
  v7 = lstrlenW(L"SOFTWARE\\Microsoft\\Cryptography\\Calais\\SmartCards");
  v8 = lstrlenW(lpString);
  v9 = v8 + v7;
  if ( v8 + v7 < v8 || (v10 = v9 + 2, (unsigned int)v10 < v9) || (v11 = 2 * v10, v11 > 0xFFFFFFFF) )
  {
    v15 = -2147024362;
  }
  else
  {
    v12 = (unsigned int)v11;
    v13 = (wchar_t *)MIDL_user_allocate((unsigned int)v11);
    v14 = v13;
    if ( v13 )
    {
      v16 = 0;
      v15 = StringCbPrintfW(v13, v12, L"%s\\%s", L"SOFTWARE\\Microsoft\\Cryptography\\Calais\\SmartCards", lpString);
      if ( !v15 )
      {
        v15 = StringCchPrintfW(pszDest, 0xAu, L"%x", a2);
        if ( !v15 )
        {
          v15 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v14, 0, 1u, &hKey);
          if ( !v15 )
          {
            v15 = RegQueryValueExW(hKey, pszDest, 0, &Type, 0, &cbData);
            if ( !v15 )
            {
              if ( Type == 1 )
              {
                v17 = cbData + 2;
                if ( (unsigned int)v17 < cbData )
                {
                  v15 = -2147024362;
                }
                else
                {
                  v18 = (BYTE *)MIDL_user_allocate(v17);
                  if ( v18 )
                  {
                    v15 = RegQueryValueExW(hKey, pszDest, 0, 0, v18, &cbData);
                    if ( !v15 )
                    {
                      *(_WORD *)&v18[2 * ((unsigned __int64)cbData >> 1)] = 0;
                      I_GetLocalizedString(v18, cbData >> 1, &lpStringa);
                      v19 = lpStringa;
                      if ( lpStringa )
                      {
                        v20 = lstrlenW(lpStringa);
                        if ( v20 + 1 < v20 || (v21 = 2LL * (v20 + 1), v21 > 0xFFFFFFFF) )
                        {
                          v15 = -2147024362;
                        }
                        else
                        {
                          v22 = (unsigned int)v21;
                          v23 = (wchar_t *)MIDL_user_allocate((unsigned int)v21);
                          v16 = v23;
                          if ( v23 )
                          {
                            v15 = StringCchCopyW(v23, v22, v19);
                            if ( !v15 )
                            {
                              *a5 = v16;
                              v16 = 0;
                            }
                          }
                          else
                          {
                            v15 = 8;
                          }
                        }
                      }
                      else
                      {
                        v15 = 1168;
                      }
                    }
                    CspFreeH(v18);
                  }
                  else
                  {
                    v15 = 8;
                  }
                }
              }
              else
              {
                v15 = 13;
              }
            }
          }
        }
      }
      CspFreeH(v14);
      if ( v16 )
        CspFreeH(v16);
    }
    else
    {
      v15 = 8;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v15;
}

```

## disassembly

```asm
0x18003a914  mov     [rsp-28h+arg_10], rbx
0x18003a919  mov     [rsp-28h+arg_18], rsi
0x18003a91e  push    rbp
0x18003a91f  push    rdi
0x18003a920  push    r12
0x18003a922  push    r14
0x18003a924  push    r15
0x18003a926  mov     rbp, rsp
0x18003a929  sub     rsp, 70h
0x18003a92d  mov     rax, cs:__security_cookie
0x18003a934  xor     rax, rsp
0x18003a937  mov     [rbp+var_10], rax
0x18003a93b  mov     r12, [rbp+arg_20]
0x18003a93f  xor     eax, eax
0x18003a941  mov     rsi, rcx
0x18003a944  mov     [rbp+var_18], eax
0x18003a947  xorps   xmm0, xmm0
0x18003a94a  mov     [rbp+hKey], rax
0x18003a94e  lea     rcx, String; "SOFTWARE\\Microsoft\\Cryptography\\Cala"...
0x18003a955  mov     [rbp+cbData], eax
0x18003a958  movups  xmmword ptr [rbp+pszDest], xmm0
0x18003a95c  mov     [rbp+Type], eax
0x18003a95f  mov     r15d, edx
0x18003a962  mov     [rbp+lpString], rax
0x18003a966  call    cs:__imp_lstrlenW
0x18003a96c  mov     rcx, rsi; lpString
0x18003a96f  mov     ebx, eax
0x18003a971  call    cs:__imp_lstrlenW
0x18003a977  lea     ecx, [rax+rbx]
0x18003a97a  cmp     ecx, eax
0x18003a97c  jb      loc_18003AB5D
0x18003a982  lea     eax, [rcx+2]
0x18003a985  cmp     eax, ecx
0x18003a987  jb      loc_18003AB5D
0x18003a98d  add     rax, rax
0x18003a990  mov     ecx, 0FFFFFFFFh
0x18003a995  cmp     rax, rcx
0x18003a998  ja      loc_18003AB5D
0x18003a99e  mov     ecx, eax; size
0x18003a9a0  mov     ebx, eax
0x18003a9a2  call    MIDL_user_allocate
0x18003a9a7  mov     r14, rax
0x18003a9aa  test    rax, rax
0x18003a9ad  jnz     short loc_18003A9B7
0x18003a9af  lea     ebx, [rax+8]
0x18003a9b2  jmp     loc_18003AB62
0x18003a9b7  lea     r9, String; "SOFTWARE\\Microsoft\\Cryptography\\Cala"...
0x18003a9be  mov     [rsp+70h+phkResult], rsi
0x18003a9c3  lea     r8, aSS; "%s\\%s"
0x18003a9ca  mov     rdx, rbx; cbDest
0x18003a9cd  mov     rcx, r14; pszDest
0x18003a9d0  xor     edi, edi
0x18003a9d2  call    StringCbPrintfW
0x18003a9d7  mov     ebx, eax
0x18003a9d9  test    eax, eax
0x18003a9db  jnz     loc_18003AB46
0x18003a9e1  mov     r9d, r15d
0x18003a9e4  lea     r8, asc_180044EB4; "%x"
0x18003a9eb  lea     edx, [rdi+0Ah]; cchDest
0x18003a9ee  lea     rcx, [rbp+pszDest]; pszDest
0x18003a9f2  call    StringCchPrintfW
0x18003a9f7  mov     ebx, eax
0x18003a9f9  test    eax, eax
0x18003a9fb  jnz     loc_18003AB46
0x18003aa01  lea     rax, [rbp+hKey]
0x18003aa05  xor     r8d, r8d; ulOptions
0x18003aa08  lea     r9d, [rdi+1]; samDesired
0x18003aa0c  mov     [rsp+70h+phkResult], rax; phkResult
0x18003aa11  mov     rdx, r14; lpSubKey
0x18003aa14  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003aa1b  call    cs:__imp_RegOpenKeyExW
0x18003aa21  mov     ebx, eax
0x18003aa23  test    eax, eax
0x18003aa25  jnz     loc_18003AB46
0x18003aa2b  mov     rcx, [rbp+hKey]; hKey
0x18003aa2f  lea     rax, [rbp+cbData]
0x18003aa33  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18003aa38  lea     r9, [rbp+Type]; lpType
0x18003aa3c  xor     r8d, r8d; lpReserved
0x18003aa3f  mov     [rsp+70h+phkResult], rdi; lpData
0x18003aa44  lea     rdx, [rbp+pszDest]; lpValueName
0x18003aa48  call    cs:__imp_RegQueryValueExW
0x18003aa4e  mov     ebx, eax
0x18003aa50  test    eax, eax
0x18003aa52  jnz     loc_18003AB46
0x18003aa58  cmp     [rbp+Type], 1
0x18003aa5c  jz      short loc_18003AA66
0x18003aa5e  lea     ebx, [rdi+0Dh]
0x18003aa61  jmp     loc_18003AB46
0x18003aa66  mov     eax, [rbp+cbData]
0x18003aa69  lea     ecx, [rax+2]; size
0x18003aa6c  cmp     ecx, eax
0x18003aa6e  jb      loc_18003AB41
0x18003aa74  call    MIDL_user_allocate
0x18003aa79  mov     rsi, rax
0x18003aa7c  test    rax, rax
0x18003aa7f  jnz     short loc_18003AA89
0x18003aa81  lea     ebx, [rax+8]
0x18003aa84  jmp     loc_18003AB46
0x18003aa89  mov     rcx, [rbp+hKey]; hKey
0x18003aa8d  lea     rax, [rbp+cbData]
0x18003aa91  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18003aa96  lea     rdx, [rbp+pszDest]; lpValueName
0x18003aa9a  xor     r9d, r9d; lpType
0x18003aa9d  mov     [rsp+70h+phkResult], rsi; lpData
0x18003aaa2  xor     r8d, r8d; lpReserved
0x18003aaa5  call    cs:__imp_RegQueryValueExW
0x18003aaab  mov     ebx, eax
0x18003aaad  test    eax, eax
0x18003aaaf  jnz     loc_18003AB37
0x18003aab5  mov     ecx, [rbp+cbData]
0x18003aab8  lea     r8, [rbp+lpString]
0x18003aabc  shr     rcx, 1
0x18003aabf  mov     [rsi+rcx*2], ax
0x18003aac3  mov     rcx, rsi
0x18003aac6  mov     edx, [rbp+cbData]
0x18003aac9  shr     edx, 1
0x18003aacb  call    I_GetLocalizedString
0x18003aad0  mov     rbx, [rbp+lpString]
0x18003aad4  test    rbx, rbx
0x18003aad7  jnz     short loc_18003AAE0
0x18003aad9  mov     ebx, 490h
0x18003aade  jmp     short loc_18003AB37
0x18003aae0  mov     rcx, rbx; lpString
0x18003aae3  call    cs:__imp_lstrlenW
0x18003aae9  lea     ecx, [rax+1]
0x18003aaec  cmp     ecx, eax
0x18003aaee  jb      short loc_18003AB32
0x18003aaf0  mov     eax, ecx
0x18003aaf2  mov     ecx, 0FFFFFFFFh
0x18003aaf7  add     rax, rax
0x18003aafa  cmp     rax, rcx
0x18003aafd  ja      short loc_18003AB32
0x18003aaff  mov     ecx, eax; size
0x18003ab01  mov     r15d, eax
0x18003ab04  call    MIDL_user_allocate
0x18003ab09  mov     rdi, rax
0x18003ab0c  test    rax, rax
0x18003ab0f  jnz     short loc_18003AB16
0x18003ab11  lea     ebx, [rax+8]
0x18003ab14  jmp     short loc_18003AB37
0x18003ab16  mov     r8, rbx; pszSrc
0x18003ab19  mov     rdx, r15; cchDest
0x18003ab1c  mov     rcx, rdi; pszDest
0x18003ab1f  call    StringCchCopyW
0x18003ab24  mov     ebx, eax
0x18003ab26  test    eax, eax
0x18003ab28  jnz     short loc_18003AB37
0x18003ab2a  mov     [r12], rdi
0x18003ab2e  xor     edi, edi
0x18003ab30  jmp     short loc_18003AB37
0x18003ab32  mov     ebx, 80070216h
0x18003ab37  mov     rcx, rsi
0x18003ab3a  call    CspFreeH
0x18003ab3f  jmp     short loc_18003AB46
0x18003ab41  mov     ebx, 80070216h
0x18003ab46  mov     rcx, r14
0x18003ab49  call    CspFreeH
0x18003ab4e  test    rdi, rdi
0x18003ab51  jz      short loc_18003AB62
0x18003ab53  mov     rcx, rdi
0x18003ab56  call    CspFreeH
0x18003ab5b  jmp     short loc_18003AB62
0x18003ab5d  mov     ebx, 80070216h
0x18003ab62  mov     rcx, [rbp+hKey]; hKey
0x18003ab66  test    rcx, rcx
0x18003ab69  jz      short loc_18003AB71
0x18003ab6b  call    cs:__imp_RegCloseKey
0x18003ab71  mov     eax, ebx
0x18003ab73  mov     rcx, [rbp+var_10]
0x18003ab77  xor     rcx, rsp; StackCookie
0x18003ab7a  call    __security_check_cookie
0x18003ab7f  lea     r11, [rsp+70h+var_s0]
0x18003ab84  mov     rbx, [r11+40h]
0x18003ab88  mov     rsi, [r11+48h]
0x18003ab8c  mov     rsp, r11
0x18003ab8f  pop     r15
0x18003ab91  pop     r14
0x18003ab93  pop     r12
0x18003ab95  pop     rdi
0x18003ab96  pop     rbp
0x18003ab97  retn
```
