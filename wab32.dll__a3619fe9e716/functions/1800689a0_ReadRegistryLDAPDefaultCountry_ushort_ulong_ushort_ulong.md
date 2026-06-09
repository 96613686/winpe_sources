# ReadRegistryLDAPDefaultCountry(ushort *,ulong,ushort *,ulong)

- ea: `0x1800689a0`
- end: `0x180068c46`
- name: `?ReadRegistryLDAPDefaultCountry@@YAHPEAGK0K@Z`
- size: `678`
- prototype: `int(unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180027564`
- `0x180029c18`

## callees

- `0x1800045e4`
- `0x1800689a0`
- `0x18006b3a8`
- `0x180091e86`
- `0x180091ef0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180068a21`
- `ADVAPI32!RegOpenKeyExW` at `0x180068a21`
- `ADVAPI32!RegCloseKey` at `0x180068c14`
- `ADVAPI32!RegCloseKey` at `0x180068c14`
- `ADVAPI32!RegQueryValueExW` at `0x180068a57`
- `ADVAPI32!RegQueryValueExW` at `0x180068a57`
- `KERNEL32!GetLocaleInfoW` at `0x180068a77`
- `KERNEL32!GetLocaleInfoW` at `0x180068a77`
- `USER32!LoadStringW` at `0x180068ab8`
- `USER32!LoadStringW` at `0x180068af7`
- `USER32!LoadStringW` at `0x180068ab8`
- `USER32!LoadStringW` at `0x180068af7`
- `USER32!CharNextW` at `0x180068b5b`
- `USER32!CharNextW` at `0x180068b72`
- `USER32!CharNextW` at `0x180068bba`
- `USER32!CharNextW` at `0x180068bd1`
- `USER32!CharNextW` at `0x180068b5b`
- `USER32!CharNextW` at `0x180068b72`
- `USER32!CharNextW` at `0x180068bba`
- `USER32!CharNextW` at `0x180068bd1`

## pseudocode

```c
__int64 __fastcall ReadRegistryLDAPDefaultCountry(
        unsigned __int16 *a1,
        __int64 a2,
        unsigned __int16 *a3,
        unsigned int a4)
{
  unsigned __int64 v4; // r12
  unsigned int v6; // esi
  __int64 v7; // rdi
  int v8; // r15d
  int v9; // r14d
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // r8
  WCHAR v12; // ax
  const WCHAR *v13; // rcx
  WCHAR v14; // ax
  const WCHAR *v15; // rcx
  __int64 v16; // rdi
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Data[200]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 Buf2[200]; // [rsp+1D0h] [rbp+D0h] BYREF

  v4 = a4;
  hKey = 0;
  cbData = 200;
  Type = 0;
  v6 = 0;
  if ( !a3 )
    return v6;
  *(_DWORD *)a3 = 0;
  a3[2] = 0;
  if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\WAB", 0, 0x20019u, &hKey) )
  {
    if ( RegQueryValueExW(hKey, L"LDAP Default Country", 0, &Type, (LPBYTE)Data, &cbData) )
    {
      cbData = GetLocaleInfoW(0x400u, 0x1002u, Data, 200);
      if ( cbData )
      {
        Buf2[0] = 0;
        StringCchCopyW(Buf2, 0xC8u, Data);
        LoadStringW(hinstMapiX, 0x1C21u, Data, 200);
        v7 = -1;
        v8 = my_atoi(Data);
        v9 = 0;
        v6 = 1;
        while ( v9 < v8 )
        {
          LoadStringW(hinstMapiX, v9 + 7202, Data, 200);
          v10 = -1;
          do
            ++v10;
          while ( Data[v10] );
          v11 = -1;
          do
            ++v11;
          while ( Buf2[v11] );
          if ( v10 >= v11 && !memcmp_0(Data, Buf2, 2 * v11) )
          {
            v12 = Data[0];
            v13 = Data;
            *a3 = 0;
            while ( v12 && v12 != 40 )
            {
              v13 = CharNextW(v13);
              v12 = *v13;
            }
            if ( *v13 == 40 )
            {
              *(_DWORD *)a3 = *(_DWORD *)CharNextW(v13);
              a3[2] = 0;
            }
            goto LABEL_20;
          }
          ++v9;
        }
        do
LABEL_20:
          ++v7;
        while ( a3[v7] );
        if ( !v7 )
          StringCchCopyW(a3, v4, L"US");
        goto LABEL_34;
      }
    }
    else
    {
      v14 = Data[0];
      v15 = Data;
      *a3 = 0;
      while ( v14 && v14 != 40 )
      {
        v15 = CharNextW(v15);
        v14 = *v15;
      }
      if ( *v15 == 40 )
      {
        *(_DWORD *)a3 = *(_DWORD *)CharNextW(v15);
        a3[2] = 0;
      }
      v16 = -1;
      do
        ++v16;
      while ( a3[v16] );
      if ( !v16 )
        StringCchCopyW(a3, v4, L"US");
    }
    v6 = 1;
  }
LABEL_34:
  if ( hKey )
    RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x1800689a0  mov     [rsp-8+arg_0], rbx
0x1800689a5  push    rbp
0x1800689a6  push    rsi
0x1800689a7  push    rdi
0x1800689a8  push    r12
0x1800689aa  push    r13
0x1800689ac  push    r14
0x1800689ae  push    r15
0x1800689b0  lea     rbp, [rsp-270h]
0x1800689b8  sub     rsp, 370h
0x1800689bf  mov     rax, cs:__security_cookie
0x1800689c6  xor     rax, rsp
0x1800689c9  mov     [rbp+2A0h+var_40], rax
0x1800689d0  xor     r13d, r13d
0x1800689d3  mov     r12d, r9d
0x1800689d6  mov     [rsp+3A0h+hKey], r13
0x1800689db  mov     edi, 0C8h
0x1800689e0  mov     [rsp+3A0h+cbData], edi
0x1800689e4  mov     rbx, r8
0x1800689e7  mov     [rsp+3A0h+Type], r13d
0x1800689ec  mov     esi, r13d
0x1800689ef  test    r8, r8
0x1800689f2  jz      loc_180068C1A
0x1800689f8  mov     [r8], r13d
0x1800689fb  lea     rax, [rsp+3A0h+hKey]
0x180068a00  mov     [r8+4], r13w
0x180068a05  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\WAB"
0x180068a0c  xor     r8d, r8d; ulOptions
0x180068a0f  mov     [rsp+3A0h+phkResult], rax; phkResult
0x180068a14  mov     r9d, 20019h; samDesired
0x180068a1a  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180068a21  call    cs:__imp_RegOpenKeyExW
0x180068a27  test    eax, eax
0x180068a29  jnz     loc_180068C0A
0x180068a2f  mov     rcx, [rsp+3A0h+hKey]; hKey
0x180068a34  lea     rax, [rsp+3A0h+cbData]
0x180068a39  mov     [rsp+3A0h+lpcbData], rax; lpcbData
0x180068a3e  lea     r9, [rsp+3A0h+Type]; lpType
0x180068a43  lea     rax, [rsp+3A0h+Data]
0x180068a48  xor     r8d, r8d; lpReserved
0x180068a4b  lea     rdx, aLdapDefaultCou; "LDAP Default Country"
0x180068a52  mov     [rsp+3A0h+phkResult], rax; lpData
0x180068a57  call    cs:__imp_RegQueryValueExW
0x180068a5d  test    eax, eax
0x180068a5f  jz      loc_180068BA4
0x180068a65  mov     r9d, edi; cchData
0x180068a68  lea     r8, [rsp+3A0h+Data]; lpLCData
0x180068a6d  mov     edx, 1002h; LCType
0x180068a72  mov     ecx, 400h; Locale
0x180068a77  call    cs:__imp_GetLocaleInfoW
0x180068a7d  mov     [rsp+3A0h+cbData], eax
0x180068a81  test    eax, eax
0x180068a83  jz      loc_180068C05
0x180068a89  lea     r8, [rsp+3A0h+Data]; unsigned __int16 *
0x180068a8e  mov     [rbp+2A0h+Buf2], r13w
0x180068a96  mov     edx, edi; unsigned __int64
0x180068a98  lea     rcx, [rbp+2A0h+Buf2]; unsigned __int16 *
0x180068a9f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180068aa4  mov     rcx, cs:hinstMapiX; hInstance
0x180068aab  lea     r8, [rsp+3A0h+Data]; lpBuffer
0x180068ab0  mov     r9d, edi; cchBufferMax
0x180068ab3  mov     edx, 1C21h; uID
0x180068ab8  call    cs:__imp_LoadStringW
0x180068abe  lea     rcx, [rsp+3A0h+Data]; unsigned __int16 *
0x180068ac3  call    ?my_atoi@@YAHPEAG@Z; my_atoi(ushort *)
0x180068ac8  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180068acc  mov     r15d, eax
0x180068acf  mov     r14d, r13d
0x180068ad2  lea     esi, [rdi+2]
0x180068ad5  cmp     r14d, r15d
0x180068ad8  jge     loc_180068B81
0x180068ade  mov     rcx, cs:hinstMapiX; hInstance
0x180068ae5  lea     edx, [r14+1C22h]; uID
0x180068aec  mov     r9d, 0C8h; cchBufferMax
0x180068af2  lea     r8, [rsp+3A0h+Data]; lpBuffer
0x180068af7  call    cs:__imp_LoadStringW
0x180068afd  lea     rcx, [rsp+3A0h+Data]
0x180068b02  mov     rax, rdi
0x180068b05  inc     rax
0x180068b08  cmp     [rcx+rax*2], r13w
0x180068b0d  jnz     short loc_180068B05
0x180068b0f  lea     rcx, [rbp+2A0h+Buf2]
0x180068b16  mov     r8, rdi
0x180068b19  inc     r8
0x180068b1c  cmp     [rcx+r8*2], r13w
0x180068b21  jnz     short loc_180068B19
0x180068b23  cmp     rax, r8
0x180068b26  jb      short loc_180068B40
0x180068b28  add     r8, r8; Size
0x180068b2b  lea     rdx, [rbp+2A0h+Buf2]; Buf2
0x180068b32  lea     rcx, [rsp+3A0h+Data]; Buf1
0x180068b37  call    memcmp_0
0x180068b3c  test    eax, eax
0x180068b3e  jz      short loc_180068B45
0x180068b40  add     r14d, esi
0x180068b43  jmp     short loc_180068AD5
0x180068b45  movzx   eax, [rsp+3A0h+Data]
0x180068b4a  lea     rcx, [rsp+3A0h+Data]
0x180068b4f  mov     [rbx], r13w
0x180068b53  jmp     short loc_180068B67
0x180068b55  cmp     ax, 28h ; '('
0x180068b59  jz      short loc_180068B6C
0x180068b5b  call    cs:__imp_CharNextW
0x180068b61  mov     rcx, rax; lpsz
0x180068b64  movzx   eax, word ptr [rax]
0x180068b67  test    ax, ax
0x180068b6a  jnz     short loc_180068B55
0x180068b6c  cmp     word ptr [rcx], 28h ; '('
0x180068b70  jnz     short loc_180068B81
0x180068b72  call    cs:__imp_CharNextW
0x180068b78  mov     ecx, [rax]
0x180068b7a  mov     [rbx], ecx
0x180068b7c  mov     [rbx+4], r13w
0x180068b81  inc     rdi
0x180068b84  cmp     [rbx+rdi*2], r13w
0x180068b89  jnz     short loc_180068B81
0x180068b8b  test    rdi, rdi
0x180068b8e  jnz     short loc_180068C0A
0x180068b90  mov     rdx, r12; unsigned __int64
0x180068b93  lea     r8, aUs; "US"
0x180068b9a  mov     rcx, rbx; unsigned __int16 *
0x180068b9d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180068ba2  jmp     short loc_180068C0A
0x180068ba4  movzx   eax, [rsp+3A0h+Data]
0x180068ba9  lea     rcx, [rsp+3A0h+Data]
0x180068bae  mov     [rbx], r13w
0x180068bb2  jmp     short loc_180068BC6
0x180068bb4  cmp     ax, 28h ; '('
0x180068bb8  jz      short loc_180068BCB
0x180068bba  call    cs:__imp_CharNextW
0x180068bc0  mov     rcx, rax; lpsz
0x180068bc3  movzx   eax, word ptr [rax]
0x180068bc6  test    ax, ax
0x180068bc9  jnz     short loc_180068BB4
0x180068bcb  cmp     word ptr [rcx], 28h ; '('
0x180068bcf  jnz     short loc_180068BE0
0x180068bd1  call    cs:__imp_CharNextW
0x180068bd7  mov     ecx, [rax]
0x180068bd9  mov     [rbx], ecx
0x180068bdb  mov     [rbx+4], r13w
0x180068be0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180068be4  inc     rdi
0x180068be7  cmp     [rbx+rdi*2], r13w
0x180068bec  jnz     short loc_180068BE4
0x180068bee  test    rdi, rdi
0x180068bf1  jnz     short loc_180068C05
0x180068bf3  mov     rdx, r12; unsigned __int64
0x180068bf6  lea     r8, aUs; "US"
0x180068bfd  mov     rcx, rbx; unsigned __int16 *
0x180068c00  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180068c05  mov     esi, 1
0x180068c0a  mov     rcx, [rsp+3A0h+hKey]; hKey
0x180068c0f  test    rcx, rcx
0x180068c12  jz      short loc_180068C1A
0x180068c14  call    cs:__imp_RegCloseKey
0x180068c1a  mov     eax, esi
0x180068c1c  mov     rcx, [rbp+2A0h+var_40]
0x180068c23  xor     rcx, rsp; StackCookie
0x180068c26  call    __security_check_cookie
0x180068c2b  mov     rbx, [rsp+3A0h+arg_0]
0x180068c33  add     rsp, 370h
0x180068c3a  pop     r15
0x180068c3c  pop     r14
0x180068c3e  pop     r13
0x180068c40  pop     r12
0x180068c42  pop     rdi
0x180068c43  pop     rsi
0x180068c44  pop     rbp
0x180068c45  retn
```
