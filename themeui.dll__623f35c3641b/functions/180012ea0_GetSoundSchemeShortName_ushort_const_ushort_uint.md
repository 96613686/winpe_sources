# GetSoundSchemeShortName(ushort const *,ushort *,uint)

- ea: `0x180012ea0`
- end: `0x18001318a`
- name: `?GetSoundSchemeShortName@@YAJPEBGPEAGI@Z`
- size: `746`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008a50`
- `0x180010b20`
- `0x180033e7c`

## callees

- `0x180012ea0`
- `0x1800358c0`

## import_xrefs

- `SHLWAPI!__imp_SHLoadIndirectString` at `0x1800130b5`
- `SHLWAPI!__imp_SHLoadIndirectString` at `0x1800130b5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800130e0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800130e0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012fb1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012fb1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012f0f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012f0f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180012f88`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180012f88`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001308c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001308c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001303a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001303a`

## pseudocode

```c
int __fastcall GetSoundSchemeShortName(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  int result; // eax
  bool v5; // sf
  __int64 v6; // rbx
  LSTATUS v7; // eax
  int v8; // edi
  char v9; // r9
  LSTATUS v10; // eax
  LSTATUS ValueW; // eax
  WCHAR *v12; // rdx
  __int64 v13; // rax
  unsigned __int16 *v14; // r8
  unsigned __int16 *v15; // rcx
  DWORD i; // r14d
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  DWORD cchClass; // [rsp+70h] [rbp-90h] BYREF
  DWORD cchName; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD pcbData; // [rsp+78h] [rbp-88h] BYREF
  WCHAR pvData[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Name[264]; // [rsp+290h] [rbp+190h] BYREF
  WCHAR pszOutBuf[264]; // [rsp+4A0h] [rbp+3A0h] BYREF
  WCHAR Class[264]; // [rsp+6B0h] [rbp+5B0h] BYREF

  if ( !a1 || !a2 )
    return -2147024809;
  hKey = 0;
  result = RegOpenKeyExW(HKEY_CURRENT_USER, L"AppEvents\\Schemes\\Names", 0, 0x20019u, &hKey);
  v5 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v5 = result < 0;
  }
  if ( !v5 )
  {
    v6 = 260;
    cchClass = 260;
    cSubKeys = 0;
    v7 = RegQueryInfoKeyW(hKey, Class, &cchClass, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
    v8 = v7;
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
    if ( v8 < 0 )
      goto LABEL_9;
    for ( i = 0; ; ++i )
    {
      v9 = 0;
      if ( i >= cSubKeys )
        break;
      cchName = 260;
      v10 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
      v8 = v10;
      if ( v10 > 0 )
        v8 = (unsigned __int16)v10 | 0x80070000;
      if ( v8 >= 0 )
      {
        pcbData = 520;
        ValueW = RegGetValueW(hKey, Name, 0, 2u, 0, pvData, &pcbData);
        v8 = ValueW;
        if ( ValueW )
        {
          pvData[0] = 0;
          if ( ValueW > 0 )
            v8 = (unsigned __int16)ValueW | 0x80070000;
        }
        if ( v8 >= 0 )
        {
          v8 = SHLoadIndirectString(pvData, pszOutBuf, 0x104u, 0);
          if ( v8 >= 0 && CompareStringOrdinal(pszOutBuf, -1, a1, -1, 1) == 2 )
          {
            v9 = 1;
            v12 = Name;
            v13 = 2147483646;
            v14 = a2;
            do
            {
              if ( !v13 )
                break;
              if ( !*v12 )
                break;
              *v14++ = *v12++;
              --v13;
              --v6;
            }
            while ( v6 );
            v15 = v14 - 1;
            v8 = -2147024774;
            if ( v6 )
            {
              v15 = v14;
              v8 = 0;
            }
            *v15 = 0;
            break;
          }
        }
      }
    }
    if ( v8 < 0 || !v9 )
    {
LABEL_9:
      *a2 = 0;
      v8 = 0;
    }
    RegCloseKey(hKey);
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x180012ea0  push    rbp
0x180012ea2  push    rsi
0x180012ea3  push    r15
0x180012ea5  lea     rbp, [rsp-7E0h]
0x180012ead  sub     rsp, 8E0h
0x180012eb4  mov     rax, cs:__security_cookie
0x180012ebb  xor     rax, rsp
0x180012ebe  mov     [rbp+7F0h+var_30], rax
0x180012ec5  mov     r15, rdx
0x180012ec8  mov     rsi, rcx
0x180012ecb  test    rcx, rcx
0x180012ece  jnz     loc_180012FEC
0x180012ed4  mov     eax, 80070057h
0x180012ed9  jmp     loc_180012FD1
0x180012ede  lea     rax, [rsp+8F0h+hKey]
0x180012ee3  mov     [rsp+8F0h+var_18], r12
0x180012eeb  xor     r12d, r12d
0x180012eee  mov     [rsp+8F0h+phkResult], rax; phkResult
0x180012ef3  mov     r9d, 20019h; samDesired
0x180012ef9  mov     [rsp+8F0h+hKey], r12
0x180012efe  xor     r8d, r8d; ulOptions
0x180012f01  lea     rdx, aAppeventsSchem_14; "AppEvents\\Schemes\\Names"
0x180012f08  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180012f0f  call    cs:__imp_RegOpenKeyExW
0x180012f15  test    eax, eax
0x180012f17  jle     short loc_180012F23
0x180012f19  movzx   eax, ax
0x180012f1c  or      eax, 80070000h
0x180012f21  test    eax, eax
0x180012f23  js      loc_180012FC9
0x180012f29  mov     rcx, [rsp+8F0h+hKey]; hKey
0x180012f2e  lea     rax, [rsp+8F0h+cSubKeys]
0x180012f33  mov     [rsp+8F0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180012f38  lea     r8, [rsp+8F0h+cchClass]; lpcchClass
0x180012f3d  mov     [rsp+8F0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180012f42  lea     rdx, [rbp+7F0h+Class]; lpClass
0x180012f49  mov     [rsp+8F0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x180012f4e  xor     r9d, r9d; lpReserved
0x180012f51  mov     [rsp+8F0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x180012f56  mov     [rsp+8F0h+lpcValues], r12; lpcValues
0x180012f5b  mov     [rsp+8F0h+arg_10], rbx
0x180012f63  mov     ebx, 104h
0x180012f68  mov     [rsp+8F0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x180012f6d  mov     [rsp+8F0h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x180012f72  mov     [rsp+8F0h+phkResult], rax; lpcSubKeys
0x180012f77  mov     [rsp+8F0h+arg_18], rdi
0x180012f7f  mov     [rsp+8F0h+cchClass], ebx
0x180012f83  mov     [rsp+8F0h+cSubKeys], r12d
0x180012f88  call    cs:__imp_RegQueryInfoKeyW
0x180012f8e  mov     edi, eax
0x180012f90  test    eax, eax
0x180012f92  jle     short loc_180012F9D
0x180012f94  movzx   edi, ax
0x180012f97  or      edi, 80070000h
0x180012f9d  test    edi, edi
0x180012f9f  jns     loc_18001317A
0x180012fa5  mov     [r15], r12w
0x180012fa9  mov     edi, r12d
0x180012fac  mov     rcx, [rsp+8F0h+hKey]; hKey
0x180012fb1  call    cs:__imp_RegCloseKey
0x180012fb7  mov     rbx, [rsp+8F0h+arg_10]
0x180012fbf  mov     eax, edi
0x180012fc1  mov     rdi, [rsp+8F0h+arg_18]
0x180012fc9  mov     r12, [rsp+8F0h+var_18]
0x180012fd1  mov     rcx, [rbp+7F0h+var_30]
0x180012fd8  xor     rcx, rsp; StackCookie
0x180012fdb  call    __security_check_cookie
0x180012fe0  add     rsp, 8E0h
0x180012fe7  pop     r15
0x180012fe9  pop     rsi
0x180012fea  pop     rbp
0x180012feb  retn
0x180012fec  test    r15, r15
0x180012fef  jz      loc_180012ED4
0x180012ff5  jmp     loc_180012EDE
0x180013000  xor     r9b, r9b
0x180013003  cmp     r14d, [rsp+8F0h+cSubKeys]
0x180013008  jnb     loc_18001313B
0x18001300e  mov     rcx, [rsp+8F0h+hKey]; hKey
0x180013013  lea     r9, [rsp+8F0h+cchName]; lpcchName
0x180013018  mov     [rsp+8F0h+lpcValues], r12; lpftLastWriteTime
0x18001301d  lea     r8, [rbp+7F0h+Name]; lpName
0x180013024  mov     [rsp+8F0h+lpcbMaxClassLen], r12; lpcchClass
0x180013029  mov     edx, r14d; dwIndex
0x18001302c  mov     [rsp+8F0h+lpcbMaxSubKeyLen], r12; lpClass
0x180013031  mov     [rsp+8F0h+phkResult], r12; lpReserved
0x180013036  mov     [rsp+8F0h+cchName], ebx
0x18001303a  call    cs:__imp_RegEnumKeyExW
0x180013040  mov     edi, eax
0x180013042  test    eax, eax
0x180013044  jle     short loc_18001304F
0x180013046  movzx   edi, ax
0x180013049  or      edi, 80070000h
0x18001304f  test    edi, edi
0x180013051  js      loc_180013172
0x180013057  mov     rcx, [rsp+8F0h+hKey]; hkey
0x18001305c  lea     rax, [rsp+8F0h+pcbData]
0x180013061  mov     [rsp+8F0h+lpcbMaxClassLen], rax; pcbData
0x180013066  lea     rdx, [rbp+7F0h+Name]; lpSubKey
0x18001306d  lea     rax, [rbp+7F0h+pvData]
0x180013071  mov     [rsp+8F0h+pcbData], 208h
0x180013079  mov     [rsp+8F0h+lpcbMaxSubKeyLen], rax; pvData
0x18001307e  mov     r9d, 2; dwFlags
0x180013084  xor     r8d, r8d; lpValue
0x180013087  mov     [rsp+8F0h+phkResult], r12; pdwType
0x18001308c  call    cs:__imp_RegGetValueW
0x180013092  mov     edi, eax
0x180013094  test    eax, eax
0x180013096  jnz     loc_180013159
0x18001309c  test    edi, edi
0x18001309e  js      loc_180013172
0x1800130a4  xor     r9d, r9d; ppvReserved
0x1800130a7  lea     rdx, [rbp+7F0h+pszOutBuf]; pszOutBuf
0x1800130ae  mov     r8d, ebx; cchOutBuf
0x1800130b1  lea     rcx, [rbp+7F0h+pvData]; pszSource
0x1800130b5  call    cs:__imp_SHLoadIndirectString
0x1800130bb  mov     edi, eax
0x1800130bd  test    eax, eax
0x1800130bf  js      loc_180013172
0x1800130c5  mov     r9d, 0FFFFFFFFh; cchCount2
0x1800130cb  mov     dword ptr [rsp+8F0h+phkResult], 1; bIgnoreCase
0x1800130d3  mov     edx, r9d; cchCount1
0x1800130d6  lea     rcx, [rbp+7F0h+pszOutBuf]; lpString1
0x1800130dd  mov     r8, rsi; lpString2
0x1800130e0  call    cs:__imp_CompareStringOrdinal
0x1800130e6  cmp     eax, 2
0x1800130e9  jnz     loc_180013172
0x1800130ef  mov     r9b, 1
0x1800130f2  lea     rdx, [rbp+7F0h+Name]
0x1800130f9  mov     eax, 7FFFFFFEh
0x1800130fe  mov     r8, r15
0x180013101  test    rax, rax
0x180013104  jz      short loc_180013123
0x180013106  movzx   ecx, word ptr [rdx]
0x180013109  test    cx, cx
0x18001310c  jz      short loc_180013123
0x18001310e  mov     [r8], cx
0x180013112  add     rdx, 2
0x180013116  add     r8, 2
0x18001311a  dec     rax
0x18001311d  sub     rbx, 1
0x180013121  jnz     short loc_180013101
0x180013123  test    rbx, rbx
0x180013126  lea     rcx, [r8-2]
0x18001312a  mov     edi, 8007007Ah
0x18001312f  cmovnz  rcx, r8
0x180013133  cmovnz  edi, r12d
0x180013137  mov     [rcx], r12w
0x18001313b  mov     r14, [rsp+8F0h+var_20]
0x180013143  test    edi, edi
0x180013145  js      loc_180012FA5
0x18001314b  test    r9b, r9b
0x18001314e  jnz     loc_180012FAC
0x180013154  jmp     loc_180012FA5
0x180013159  mov     [rbp+7F0h+pvData], r12w
0x18001315e  jle     loc_18001309C
0x180013164  movzx   edi, ax
0x180013167  or      edi, 80070000h
0x18001316d  jmp     loc_18001309C
0x180013172  inc     r14d
0x180013175  jmp     loc_180013000
0x18001317a  mov     [rsp+8F0h+var_20], r14
0x180013182  mov     r14d, r12d
0x180013185  jmp     loc_180013000
```
