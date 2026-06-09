# DrvGetProfileString(ushort const *,ushort const *,ushort const *,ushort *,unsigned __int64)

- ea: `0x38388e8a4`
- end: `0x38388e966`
- name: `?DrvGetProfileString@@YA_KPEBG00PEAG_K@Z`
- size: `194`
- prototype: `unsigned __int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName, const unsigned __int16 *, unsigned __int16 *, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x383889910`
- `0x383895dbc`
- `0x38389f6e0`
- `0x3838a1bf0`
- `0x38393a860`

## callees

- `0x3838434c0`
- `0x38388e8a4`
- `0x38388e970`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x38388e8fd`
- `ADVAPI32!RegOpenKeyExW` at `0x38388e8fd`
- `ADVAPI32!RegQueryValueExW` at `0x3838f3371`
- `ADVAPI32!RegQueryValueExW` at `0x3838f3371`
- `ADVAPI32!RegEnumValueW` at `0x3838f329c`
- `ADVAPI32!RegEnumValueW` at `0x3838f3303`
- `ADVAPI32!RegEnumValueW` at `0x3838f329c`
- `ADVAPI32!RegEnumValueW` at `0x3838f3303`
- `ADVAPI32!RegCloseKey` at `0x3838f33f4`
- `ADVAPI32!RegCloseKey` at `0x3838f33f4`

## pseudocode

```c
unsigned __int64 __fastcall DrvGetProfileString(
        LPCWSTR lpSubKey,
        LPCWSTR lpValueName,
        const unsigned __int16 *a3,
        BYTE *a4,
        unsigned __int64 a5)
{
  unsigned __int64 v5; // rbx
  unsigned __int64 v10; // rdi
  DWORD v11; // r14d
  LSTATUS v12; // eax
  __int64 v13; // rax
  LSTATUS Value; // eax
  unsigned __int64 v15; // rdi
  unsigned __int64 v16; // rdi
  unsigned __int64 v17; // rcx
  DWORD cchValueName; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v19; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cbData[2]; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  DWORD Type[4]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR ValueName[136]; // [rsp+70h] [rbp-90h] BYREF

  v5 = a5;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey) )
  {
    if ( lpValueName )
    {
      cbData[0] = 2 * a5;
      Value = RegQueryValueExW(hKey, lpValueName, 0, Type, a4, cbData);
      v15 = (unsigned __int64)cbData[0] >> 1;
      if ( Value != 234 )
      {
        if ( Value )
        {
          StringCchCopyExW((unsigned __int16 *)a4, a5, a3, 0, &v19, 0);
          v16 = a5 - v19;
        }
        else if ( Type[0] == 1 )
        {
          if ( *(_WORD *)&a4[2 * v15 - 2] )
          {
            v17 = a5 - 1;
            if ( v15 < a5 )
              v17 = (unsigned __int64)cbData[0] >> 1;
            v16 = v17;
            *(_WORD *)&a4[2 * v17] = 0;
          }
          else
          {
            v16 = v15 - 1;
          }
        }
        else
        {
          v16 = 0;
          *(_WORD *)a4 = 0;
        }
        goto LABEL_27;
      }
      *(_WORD *)&a4[2 * a5 - 2] = 0;
    }
    else
    {
      v10 = a5 - 1;
      *(_QWORD *)cbData = a4;
      v11 = 0;
      v19 = a5 - 1;
      if ( a5 != 1 )
      {
        while ( 1 )
        {
          cchValueName = v10;
          v12 = RegEnumValueW(hKey, v11++, (LPWSTR)a4, &cchValueName, 0, 0, 0, 0);
          if ( v12 )
            break;
          if ( cchValueName )
          {
            v13 = cchValueName + 1;
            a4 += 2 * v13;
            v10 -= (unsigned int)v13;
            *(_QWORD *)cbData = a4;
            v19 = v10;
          }
        }
        if ( v12 == 234 )
        {
          if ( v10 )
          {
            cchValueName = 129;
            if ( !RegEnumValueW(hKey, v11 - 1, ValueName, &cchValueName, 0, 0, 0, 0) )
            {
              StringCchCopyExW((unsigned __int16 *)a4, v10, ValueName, (unsigned __int16 **)cbData, &v19, 0);
              a4 = (BYTE *)(*(_QWORD *)cbData + 2LL);
              v10 = v19 - 1;
            }
          }
        }
      }
      *(_WORD *)a4 = 0;
      v5 = a5 - v10;
    }
    v16 = v5 - 1;
LABEL_27:
    RegCloseKey(hKey);
    return v16;
  }
  if ( (int)StringCchCopyExW((unsigned __int16 *)a4, a5, a3, 0, &v19, 0) < 0 )
    return 0;
  else
    return a5 - v19;
}

```

## disassembly

```asm
0x38388e8a4  mov     [rsp-8+arg_10], rbx
0x38388e8a9  push    rbp
0x38388e8aa  push    rsi
0x38388e8ab  push    rdi
0x38388e8ac  push    r14
0x38388e8ae  push    r15
0x38388e8b0  lea     rbp, [rsp-90h]
0x38388e8b8  sub     rsp, 190h
0x38388e8bf  mov     rax, cs:__security_cookie
0x38388e8c6  xor     rax, rsp
0x38388e8c9  mov     [rbp+0B0h+var_30], rax
0x38388e8d0  mov     rbx, [rbp+0B0h+arg_20]
0x38388e8d7  lea     rax, [rsp+1B0h+hKey]
0x38388e8dc  mov     rdi, rdx
0x38388e8df  mov     rsi, r9
0x38388e8e2  mov     r14, r8
0x38388e8e5  mov     rdx, rcx; lpSubKey
0x38388e8e8  mov     r9d, 20019h; samDesired
0x38388e8ee  xor     r8d, r8d; ulOptions
0x38388e8f1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x38388e8f8  mov     [rsp+1B0h+phkResult], rax; phkResult
0x38388e8fd  call    cs:__imp_RegOpenKeyExW
0x38388e903  xor     r15d, r15d
0x38388e906  test    eax, eax
0x38388e908  jz      loc_3838F3251
0x38388e90e  lea     rax, [rsp+1B0h+var_168]
0x38388e913  xor     r9d, r9d; unsigned __int16 **
0x38388e916  mov     r8, r14; unsigned __int16 *
0x38388e919  mov     rdx, rbx; unsigned __int64
0x38388e91c  mov     rcx, rsi; unsigned __int16 *
0x38388e91f  mov     dword ptr [rsp+1B0h+lpType], r15d; unsigned int
0x38388e924  mov     [rsp+1B0h+phkResult], rax; unsigned __int64 *
0x38388e929  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x38388e92e  test    eax, eax
0x38388e930  js      loc_3838F324A
0x38388e936  sub     rbx, [rsp+1B0h+var_168]
0x38388e93b  mov     rax, rbx
0x38388e93e  jmp     short $+2
0x38388e940  mov     rcx, [rbp+0B0h+var_30]
0x38388e947  xor     rcx, rsp; StackCookie
0x38388e94a  call    __security_check_cookie
0x38388e94f  mov     rbx, [rsp+1B0h+arg_10]
0x38388e957  add     rsp, 190h
0x38388e95e  pop     r15
0x38388e960  pop     r14
0x38388e962  pop     rdi
0x38388e963  pop     rsi
0x38388e964  pop     rbp
0x38388e965  retn
0x3838f324a  xor     eax, eax
0x3838f324c  jmp     loc_38388E940
0x3838f3251  test    rdi, rdi
0x3838f3254  jnz     loc_3838F334B
0x3838f325a  lea     rdi, [rbx-1]
0x3838f325e  mov     qword ptr [rsp+1B0h+cbData], rsi
0x3838f3263  mov     r14d, r15d
0x3838f3266  mov     [rsp+1B0h+var_168], rdi
0x3838f326b  test    rdi, rdi
0x3838f326e  jz      loc_3838F3342
0x3838f3274  mov     rcx, [rsp+1B0h+hKey]; hKey
0x3838f3279  mov     [rsp+1B0h+lpcbData], r15; lpcbData
0x3838f327e  mov     [rsp+1B0h+lpData], r15; lpData
0x3838f3283  lea     r9, [rsp+1B0h+cchValueName]; lpcchValueName
0x3838f3288  mov     r8, rsi; lpValueName
0x3838f328b  mov     edx, r14d; dwIndex
0x3838f328e  mov     [rsp+1B0h+lpType], r15; lpType
0x3838f3293  mov     [rsp+1B0h+cchValueName], edi
0x3838f3297  mov     [rsp+1B0h+phkResult], r15; lpReserved
0x3838f329c  call    cs:__imp_RegEnumValueW
0x3838f32a2  inc     r14d
0x3838f32a5  test    eax, eax
0x3838f32a7  jnz     short loc_3838F32C8
0x3838f32a9  mov     eax, [rsp+1B0h+cchValueName]
0x3838f32ad  test    eax, eax
0x3838f32af  jz      short loc_3838F3274
0x3838f32b1  inc     eax
0x3838f32b3  mov     ecx, eax
0x3838f32b5  lea     rsi, [rsi+rax*2]
0x3838f32b9  sub     rdi, rcx
0x3838f32bc  mov     qword ptr [rsp+1B0h+cbData], rsi
0x3838f32c1  mov     [rsp+1B0h+var_168], rdi
0x3838f32c6  jmp     short loc_3838F3274
0x3838f32c8  cmp     eax, 0EAh
0x3838f32cd  jnz     short loc_3838F3342
0x3838f32cf  test    rdi, rdi
0x3838f32d2  jz      short loc_3838F3342
0x3838f32d4  mov     rcx, [rsp+1B0h+hKey]; hKey
0x3838f32d9  mov     [rsp+1B0h+lpcbData], r15; lpcbData
0x3838f32de  mov     [rsp+1B0h+lpData], r15; lpData
0x3838f32e3  lea     edx, [r14-1]; dwIndex
0x3838f32e7  lea     r9, [rsp+1B0h+cchValueName]; lpcchValueName
0x3838f32ec  lea     r8, [rsp+1B0h+ValueName]; lpValueName
0x3838f32f1  mov     [rsp+1B0h+lpType], r15; lpType
0x3838f32f6  mov     [rsp+1B0h+cchValueName], 81h
0x3838f32fe  mov     [rsp+1B0h+phkResult], r15; lpReserved
0x3838f3303  call    cs:__imp_RegEnumValueW
0x3838f3309  test    eax, eax
0x3838f330b  jnz     short loc_3838F3342
0x3838f330d  lea     rax, [rsp+1B0h+var_168]
0x3838f3312  lea     r9, [rsp+1B0h+cbData]; unsigned __int16 **
0x3838f3317  lea     r8, [rsp+1B0h+ValueName]; unsigned __int16 *
0x3838f331c  mov     rdx, rdi; unsigned __int64
0x3838f331f  mov     rcx, rsi; unsigned __int16 *
0x3838f3322  mov     dword ptr [rsp+1B0h+lpType], r15d; unsigned int
0x3838f3327  mov     [rsp+1B0h+phkResult], rax; unsigned __int64 *
0x3838f332c  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x3838f3331  mov     rsi, qword ptr [rsp+1B0h+cbData]
0x3838f3336  mov     rdi, [rsp+1B0h+var_168]
0x3838f333b  add     rsi, 2
0x3838f333f  dec     rdi
0x3838f3342  mov     [rsi], r15w
0x3838f3346  sub     rbx, rdi
0x3838f3349  jmp     short loc_3838F338B
0x3838f334b  mov     rcx, [rsp+1B0h+hKey]; hKey
0x3838f3350  lea     eax, [rbx+rbx]
0x3838f3353  lea     r9, [rsp+1B0h+Type]; lpType
0x3838f3358  mov     [rsp+1B0h+cbData], eax
0x3838f335c  lea     rax, [rsp+1B0h+cbData]
0x3838f3361  xor     r8d, r8d; lpReserved
0x3838f3364  mov     [rsp+1B0h+lpType], rax; lpcbData
0x3838f3369  mov     rdx, rdi; lpValueName
0x3838f336c  mov     [rsp+1B0h+phkResult], rsi; lpData
0x3838f3371  call    cs:__imp_RegQueryValueExW
0x3838f3377  mov     edi, [rsp+1B0h+cbData]
0x3838f337b  shr     rdi, 1
0x3838f337e  cmp     eax, 0EAh
0x3838f3383  jnz     short loc_3838F3391
0x3838f3385  mov     [rsi+rbx*2-2], r15w
0x3838f338b  lea     rdi, [rbx-1]
0x3838f338f  jmp     short loc_3838F33EF
0x3838f3391  test    eax, eax
0x3838f3393  jz      short loc_3838F33BF
0x3838f3395  lea     rax, [rsp+1B0h+var_168]
0x3838f339a  xor     r9d, r9d; unsigned __int16 **
0x3838f339d  mov     r8, r14; unsigned __int16 *
0x3838f33a0  mov     rdx, rbx; unsigned __int64
0x3838f33a3  mov     rcx, rsi; unsigned __int16 *
0x3838f33a6  mov     dword ptr [rsp+1B0h+lpType], r15d; unsigned int
0x3838f33ab  mov     [rsp+1B0h+phkResult], rax; unsigned __int64 *
0x3838f33b0  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x3838f33b5  mov     rdi, rbx
0x3838f33b8  sub     rdi, [rsp+1B0h+var_168]
0x3838f33bd  jmp     short loc_3838F33EF
0x3838f33bf  cmp     [rsp+1B0h+Type], 1
0x3838f33c4  jz      short loc_3838F33CF
0x3838f33c6  mov     rdi, r15
0x3838f33c9  mov     [rsi], r15w
0x3838f33cd  jmp     short loc_3838F33EF
0x3838f33cf  cmp     [rsi+rdi*2-2], r15w
0x3838f33d5  jnz     short loc_3838F33DC
0x3838f33d7  dec     rdi
0x3838f33da  jmp     short loc_3838F33EF
0x3838f33dc  cmp     rdi, rbx
0x3838f33df  lea     rcx, [rbx-1]
0x3838f33e3  cmovb   rcx, rdi
0x3838f33e7  mov     rdi, rcx
0x3838f33ea  mov     [rsi+rcx*2], r15w
0x3838f33ef  mov     rcx, [rsp+1B0h+hKey]; hKey
0x3838f33f4  call    cs:__imp_RegCloseKey
0x3838f33fa  mov     rax, rdi
0x3838f33fd  jmp     loc_38388E940
```
