# UmpoInternalReadSettingFromUserStore

- ea: `0x1800051e0`
- end: `0x18000547a`
- name: `UmpoInternalReadSettingFromUserStore`
- size: `666`
- prototype: `__int64 __fastcall(HKEY, UUID *, UUID *, UUID *, unsigned int, LPDWORD lpType, LPBYTE lpData, LPDWORD lpcbData)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005cb4`

## callees

- `0x1800051e0`
- `0x180005480`
- `0x18000681c`
- `0x18000f3dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005369`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005369`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005310`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005320`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800053db`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005310`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005320`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800053db`
- `RPCRT4!UuidEqual` at `0x180005261`
- `RPCRT4!UuidEqual` at `0x180005261`

## pseudocode

```c
__int64 __fastcall UmpoInternalReadSettingFromUserStore(
        HKEY a1,
        UUID *a2,
        UUID *a3,
        UUID *a4,
        unsigned int a5,
        LPDWORD lpType,
        LPBYTE lpData,
        LPDWORD lpcbData)
{
  unsigned int v10; // edi
  unsigned int Value; // ebx
  HKEY v12; // rcx
  const WCHAR *v14; // rdx
  bool v15; // zf
  LPDWORD v16; // r15
  LPBYTE v17; // rdi
  int v18; // eax
  __int64 v19; // [rsp+68h] [rbp-19h] BYREF
  RPC_STATUS Status; // [rsp+70h] [rbp-11h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-9h] BYREF
  HKEY v22; // [rsp+80h] [rbp-1h] BYREF
  HKEY phkResult; // [rsp+88h] [rbp+7h] BYREF
  DWORD v24; // [rsp+C8h] [rbp+47h] BYREF

  hKey = 0;
  v22 = 0;
  phkResult = 0;
  Status = 0;
  if ( (unsigned __int64)a1 - 1 > 0xFFFFFFFFFFFFFFFDuLL )
    return 87;
  v10 = a5;
  if ( a5 > 1 )
    return 87;
  Value = UmpoInternalOpenGUIDSubKey(a1, a2, &hKey, 0x20019u, 1, 0);
  if ( !Value
    && (!a3
     || UuidEqual(a3, (UUID *)&NO_SUBGROUP_GUID, &Status)
     || (Value = UmpoInternalOpenGUIDSubKey(hKey, a3, &phkResult, 0x20019u, 1, 0)) == 0) )
  {
    v12 = hKey;
    if ( phkResult )
      v12 = phkResult;
    Value = UmpoInternalOpenGUIDSubKey(v12, a4, &v22, 0x20019u, 1, 0);
    if ( !Value )
    {
      v14 = L"ACSettingIndex";
      v15 = v10 == 0;
      v16 = lpcbData;
      v17 = lpData;
      if ( !v15 )
        v14 = L"DCSettingIndex";
      Value = RegQueryValueExW(v22, v14, 0, lpType, lpData, lpcbData);
      if ( !Value )
      {
        if ( v17 )
        {
          v19 = 0;
          v24 = 4;
          if ( !(unsigned int)UmpoReadFromSystemPowerKey(0, a3, 0, 9, 0, 0, (__int64)&v19, &v24, 0) )
          {
            v24 = 4;
            if ( !(unsigned int)UmpoReadFromSystemPowerKey(0, a3, 0, 10, 0, 0, (__int64)&v19 + 4, &v24, 0) )
            {
              if ( *v16 != 4 )
              {
                MicrosoftTelemetryAssertTriggeredNoArgs();
                if ( *v16 < 4 )
                {
                  Value = 13;
                  goto LABEL_10;
                }
              }
              v18 = v19;
              if ( *(_DWORD *)v17 < (unsigned int)v19 || (v18 = HIDWORD(v19), *(_DWORD *)v17 > HIDWORD(v19)) )
                *(_DWORD *)v17 = v18;
            }
          }
          Value = 0;
        }
      }
    }
  }
LABEL_10:
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  }
  if ( (unsigned __int64)v22 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(v22);
    v22 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  }
  if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(phkResult);
  return Value;
}

```

## disassembly

```asm
0x1800051e0  mov     r11, rsp
0x1800051e3  push    rbp
0x1800051e4  push    rsi
0x1800051e5  push    r12
0x1800051e7  push    r14
0x1800051e9  lea     rbp, [r11-3Fh]
0x1800051ed  sub     rsp, 98h
0x1800051f4  xor     r12d, r12d
0x1800051f7  lea     rax, [rcx-1]
0x1800051fb  mov     [rbp+37h+hKey], r12
0x1800051ff  mov     r14, r9
0x180005202  mov     [rbp+37h+var_38], r12
0x180005206  mov     rsi, r8
0x180005209  mov     [rbp+37h+phkResult], r12
0x18000520d  mov     [rbp+37h+Status], r12d
0x180005211  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180005215  ja      loc_180005470
0x18000521b  mov     [r11+18h], rdi
0x18000521f  mov     edi, [rbp+37h+arg_20]
0x180005222  cmp     edi, 1
0x180005225  ja      loc_180005466
0x18000522b  mov     [rsp+0B0h+lpcbData], r12; __int64
0x180005230  lea     r8, [rbp+37h+hKey]; phkResult
0x180005234  mov     r9d, 20019h; samDesired
0x18000523a  mov     byte ptr [rsp+0B0h+lpData], 1; char
0x18000523f  mov     [r11+10h], rbx
0x180005243  call    UmpoInternalOpenGUIDSubKey
0x180005248  mov     ebx, eax
0x18000524a  test    eax, eax
0x18000524c  jnz     short loc_1800052C2
0x18000524e  test    rsi, rsi
0x180005251  jz      short loc_180005291
0x180005253  lea     r8, [rbp+37h+Status]; Status
0x180005257  mov     rcx, rsi; Uuid1
0x18000525a  lea     rdx, NO_SUBGROUP_GUID; Uuid2
0x180005261  call    cs:__imp_UuidEqual
0x180005267  test    eax, eax
0x180005269  jnz     short loc_180005291
0x18000526b  mov     rcx, [rbp+37h+hKey]; hKey
0x18000526f  lea     r8, [rbp+37h+phkResult]; phkResult
0x180005273  mov     [rsp+0B0h+lpcbData], r12; __int64
0x180005278  mov     r9d, 20019h; samDesired
0x18000527e  mov     rdx, rsi; Uuid2
0x180005281  mov     byte ptr [rsp+0B0h+lpData], 1; char
0x180005286  call    UmpoInternalOpenGUIDSubKey
0x18000528b  mov     ebx, eax
0x18000528d  test    eax, eax
0x18000528f  jnz     short loc_1800052C2
0x180005291  mov     rax, [rbp+37h+phkResult]
0x180005295  lea     r8, [rbp+37h+var_38]; phkResult
0x180005299  mov     rcx, [rbp+37h+hKey]
0x18000529d  test    rax, rax
0x1800052a0  mov     [rsp+0B0h+lpcbData], r12; __int64
0x1800052a5  mov     r9d, 20019h; samDesired
0x1800052ab  cmovnz  rcx, rax; hKey
0x1800052af  mov     byte ptr [rsp+0B0h+lpData], 1; char
0x1800052b4  mov     rdx, r14; Uuid2
0x1800052b7  call    UmpoInternalOpenGUIDSubKey
0x1800052bc  mov     ebx, eax
0x1800052be  test    eax, eax
0x1800052c0  jz      short loc_180005330
0x1800052c2  mov     rcx, [rbp+37h+hKey]; hKey
0x1800052c6  lea     rax, [rcx-1]
0x1800052ca  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800052ce  jbe     short loc_180005310
0x1800052d0  mov     rcx, [rbp+37h+var_38]; hKey
0x1800052d4  lea     rax, [rcx-1]
0x1800052d8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800052dc  jbe     short loc_180005320
0x1800052de  mov     rcx, [rbp+37h+phkResult]; hKey
0x1800052e2  lea     rax, [rcx-1]
0x1800052e6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800052ea  jbe     loc_1800053DB
0x1800052f0  mov     eax, ebx
0x1800052f2  mov     rbx, [rsp+0B0h+arg_8]
0x1800052fa  mov     rdi, [rsp+0B0h+arg_10]
0x180005302  add     rsp, 98h
0x180005309  pop     r14
0x18000530b  pop     r12
0x18000530d  pop     rsi
0x18000530e  pop     rbp
0x18000530f  retn
0x180005310  call    cs:__imp_RegCloseKey
0x180005316  mov     [rbp+37h+hKey], 0FFFFFFFFFFFFFFFFh
0x18000531e  jmp     short loc_1800052D0
0x180005320  call    cs:__imp_RegCloseKey
0x180005326  mov     [rbp+37h+var_38], 0FFFFFFFFFFFFFFFFh
0x18000532e  jmp     short loc_1800052DE
0x180005330  mov     r9, [rbp+37h+lpType]; lpType
0x180005334  lea     rax, aDcsettingindex; "DCSettingIndex"
0x18000533b  mov     rcx, [rbp+37h+var_38]; hKey
0x18000533f  lea     rdx, aAcsettingindex; "ACSettingIndex"
0x180005346  test    edi, edi
0x180005348  mov     [rsp+90h], r15
0x180005350  mov     r15, [rbp+37h+arg_38]
0x180005354  mov     rdi, [rbp+37h+arg_30]
0x180005358  cmovnz  rdx, rax; lpValueName
0x18000535c  xor     r8d, r8d; lpReserved
0x18000535f  mov     [rsp+0B0h+lpcbData], r15; lpcbData
0x180005364  mov     [rsp+0B0h+lpData], rdi; lpData
0x180005369  call    cs:__imp_RegQueryValueExW
0x18000536f  mov     ebx, eax
0x180005371  test    eax, eax
0x180005373  jnz     short loc_1800053CE
0x180005375  test    rdi, rdi
0x180005378  jz      short loc_1800053CE
0x18000537a  mov     [rsp+50h], r12; __int64
0x18000537f  lea     rax, [rbp+37h+arg_0]
0x180005383  mov     [rsp+0B0h+var_68], rax; LPDWORD
0x180005388  mov     r9, r14
0x18000538b  lea     rax, [rbp+37h+var_50]
0x18000538f  mov     dword ptr [rbp+37h+var_50], r12d
0x180005393  mov     [rsp+0B0h+var_70], rax; __int64
0x180005398  xor     r8d, r8d
0x18000539b  mov     [rsp+0B0h+var_78], r12d; int
0x1800053a0  mov     rdx, rsi; Uuid1
0x1800053a3  mov     [rsp+0B0h+var_80], r12; __int64
0x1800053a8  xor     ecx, ecx; __int64
0x1800053aa  mov     dword ptr [rsp+0B0h+lpcbData], 9; int
0x1800053b2  mov     byte ptr [rsp+0B0h+lpData], r12b; char
0x1800053b7  mov     dword ptr [rbp+37h+var_50+4], r12d
0x1800053bb  mov     [rbp+37h+arg_0], 4
0x1800053c2  call    UmpoReadFromSystemPowerKey
0x1800053c7  test    eax, eax
0x1800053c9  jz      short loc_1800053E6
0x1800053cb  mov     ebx, r12d
0x1800053ce  mov     r15, [rsp+90h]
0x1800053d6  jmp     loc_1800052C2
0x1800053db  call    cs:__imp_RegCloseKey
0x1800053e1  jmp     loc_1800052F0
0x1800053e6  mov     [rsp+50h], r12; __int64
0x1800053eb  lea     rax, [rbp+37h+arg_0]
0x1800053ef  mov     [rsp+0B0h+var_68], rax; LPDWORD
0x1800053f4  mov     r9, r14
0x1800053f7  lea     rax, [rbp+37h+var_50+4]
0x1800053fb  mov     [rbp+37h+arg_0], 4
0x180005402  mov     [rsp+0B0h+var_70], rax; __int64
0x180005407  xor     r8d, r8d
0x18000540a  mov     [rsp+0B0h+var_78], r12d; int
0x18000540f  mov     rdx, rsi; Uuid1
0x180005412  mov     [rsp+0B0h+var_80], r12; __int64
0x180005417  xor     ecx, ecx; __int64
0x180005419  mov     dword ptr [rsp+0B0h+lpcbData], 0Ah; int
0x180005421  mov     byte ptr [rsp+0B0h+lpData], r12b; char
0x180005426  call    UmpoReadFromSystemPowerKey
0x18000542b  test    eax, eax
0x18000542d  jnz     short loc_1800053CB
0x18000542f  cmp     dword ptr [r15], 4
0x180005433  jnz     short loc_180005449
0x180005435  mov     eax, dword ptr [rbp+37h+var_50]
0x180005438  mov     ecx, [rdi]
0x18000543a  cmp     ecx, eax
0x18000543c  jb      short loc_180005445
0x18000543e  mov     eax, dword ptr [rbp+37h+var_50+4]
0x180005441  cmp     ecx, eax
0x180005443  jbe     short loc_1800053CB
0x180005445  mov     [rdi], eax
0x180005447  jmp     short loc_1800053CB
0x180005449  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000544e  cmp     dword ptr [r15], 4
0x180005452  jnb     short loc_180005435
0x180005454  mov     r15, [rsp+90h]
0x18000545c  mov     ebx, 0Dh
0x180005461  jmp     loc_1800052C2
0x180005466  mov     eax, 57h ; 'W'
0x18000546b  jmp     loc_1800052FA
0x180005470  mov     eax, 57h ; 'W'
0x180005475  jmp     loc_180005302
```
