# CPicturePasswordVault::ClearEnrollment(void *)

- ea: `0x180018dac`
- end: `0x180018f0a`
- name: `?ClearEnrollment@CPicturePasswordVault@@SAJPEAX@Z`
- size: `350`
- prototype: `__int64 __fastcall(PSID pSid)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180006480`

## callees

- `0x180002610`
- `0x180005a2c`
- `0x1800092b8`
- `0x180018dac`
- `0x180019610`
- `0x1800197cc`
- `0x1800198d4`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180018dda`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180018dda`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180018e15`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180018e15`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180018e69`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180018e69`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultRemoveItem` at `0x180018eba`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultRemoveItem` at `0x180018eba`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultCloseVault` at `0x180018ed3`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultCloseVault` at `0x180018ed3`

## pseudocode

```c
__int64 __fastcall CPicturePasswordVault::ClearEnrollment(PSID pSid)
{
  const unsigned __int16 *v2; // r8
  signed int Error; // ebx
  signed int v4; // edi
  LSTATUS v5; // eax
  DWORD LengthSid; // eax
  int v7; // eax
  void *v9; // [rsp+30h] [rbp-69h] BYREF
  LPWSTR StringSid; // [rsp+38h] [rbp-61h] BYREF
  __int128 v11; // [rsp+40h] [rbp-59h] BYREF
  __int128 v12; // [rsp+50h] [rbp-49h]
  _QWORD v13[4]; // [rsp+60h] [rbp-39h] BYREF
  _BYTE v14[8]; // [rsp+80h] [rbp-19h] BYREF
  LPCWSTR lpSubKey; // [rsp+88h] [rbp-11h]
  int v16; // [rsp+A0h] [rbp+7h]
  HKEY hKey; // [rsp+A8h] [rbp+Fh]
  __int128 v18; // [rsp+B0h] [rbp+17h] BYREF

  StringSid = 0;
  if ( ConvertSidToStringSidW(pSid, &StringSid) || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    CConvenienceLogonEnrollmentData::CConvenienceLogonEnrollmentData(
      (CConvenienceLogonEnrollmentData *)v14,
      StringSid,
      v2);
    v4 = v16;
    if ( v16 >= 0 )
    {
      v5 = RegDeleteKeyExW(hKey, lpSubKey, 0, 0);
      v4 = v5;
      if ( v5 > 0 )
        v4 = (unsigned __int16)v5 | 0x80070000;
    }
    v13[0] = 1;
    v11 = 0;
    LODWORD(v11) = 2;
    DWORD2(v11) = 8;
    v13[1] = 7;
    v13[3] = 0;
    v13[2] = L"Picture Password Vault Resource";
    v12 = 0;
    LengthSid = GetLengthSid(pSid);
    *((_QWORD *)&v12 + 1) = pSid;
    LODWORD(v12) = LengthSid;
    v9 = 0;
    Error = _OpenPicturePasswordVault(&v9);
    if ( Error >= 0 )
    {
      v18 = c_guidPicturePasswordVaultSchema;
      v7 = VaultRemoveItem(v9, &v18, v13, &v11, 0, 0);
      Error = v7;
      if ( v7 > 0 )
        Error = (unsigned __int16)v7 | 0x80070000;
      VaultCloseVault(&v9);
    }
    CConvenienceLogonEnrollmentData::~CConvenienceLogonEnrollmentData((CConvenienceLogonEnrollmentData *)v14);
    if ( v4 < 0 )
      Error = v4;
  }
  CLocalMemPtr<unsigned short>::~CLocalMemPtr<unsigned short>(&StringSid);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180018dac  push    rbp
0x180018dae  push    rbx
0x180018daf  push    rsi
0x180018db0  push    rdi
0x180018db1  lea     rbp, [rsp-3Fh]
0x180018db6  sub     rsp, 0D8h
0x180018dbd  mov     rax, cs:__security_cookie
0x180018dc4  xor     rax, rsp
0x180018dc7  mov     [rbp+57h+var_30], rax
0x180018dcb  lea     rdx, [rbp+57h+StringSid]; StringSid
0x180018dcf  mov     [rbp+57h+StringSid], 0
0x180018dd7  mov     rsi, rcx
0x180018dda  call    cs:__imp_ConvertSidToStringSidW
0x180018de0  test    eax, eax
0x180018de2  jnz     short loc_180018DF3
0x180018de4  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180018de9  mov     ebx, eax
0x180018deb  test    eax, eax
0x180018ded  js      loc_180018EE7
0x180018df3  mov     rdx, [rbp+57h+StringSid]; unsigned __int16 *
0x180018df7  lea     rcx, [rbp+57h+var_70]; this
0x180018dfb  call    ??0CConvenienceLogonEnrollmentData@@QEAA@PEBG0@Z; CConvenienceLogonEnrollmentData::CConvenienceLogonEnrollmentData(ushort const *,ushort const *)
0x180018e00  mov     edi, [rbp+57h+var_50]
0x180018e03  test    edi, edi
0x180018e05  js      short loc_180018E2A
0x180018e07  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x180018e0b  xor     r9d, r9d; Reserved
0x180018e0e  mov     rcx, [rbp+57h+hKey]; hKey
0x180018e12  xor     r8d, r8d; samDesired
0x180018e15  call    cs:__imp_RegDeleteKeyExW
0x180018e1b  mov     edi, eax
0x180018e1d  test    eax, eax
0x180018e1f  jle     short loc_180018E2A
0x180018e21  movzx   edi, ax
0x180018e24  or      edi, 80070000h
0x180018e2a  xorps   xmm0, xmm0
0x180018e2d  mov     [rbp+57h+var_90], 1
0x180018e35  movups  [rbp+57h+var_B0], xmm0
0x180018e39  lea     rax, aPicturePasswor_1; "Picture Password Vault Resource"
0x180018e40  mov     dword ptr [rbp+57h+var_B0], 2
0x180018e47  mov     rcx, rsi; pSid
0x180018e4a  mov     dword ptr [rbp+57h+var_B0+8], 8
0x180018e51  mov     [rbp+57h+var_88], 7
0x180018e59  mov     [rbp+57h+var_78], 0
0x180018e61  mov     [rbp+57h+var_80], rax
0x180018e65  movups  [rbp+57h+var_A0], xmm0
0x180018e69  call    cs:__imp_GetLengthSid
0x180018e6f  lea     rcx, [rbp+57h+var_C0]; void **
0x180018e73  mov     qword ptr [rbp+57h+var_A0+8], rsi
0x180018e77  mov     dword ptr [rbp+57h+var_A0], eax
0x180018e7a  mov     [rbp+57h+var_C0], 0
0x180018e82  call    ?_OpenPicturePasswordVault@@YAJPEAPEAX@Z; _OpenPicturePasswordVault(void * *)
0x180018e87  mov     ebx, eax
0x180018e89  test    eax, eax
0x180018e8b  js      short loc_180018ED9
0x180018e8d  movups  xmm0, cs:c_guidPicturePasswordVaultSchema
0x180018e94  mov     rcx, [rbp+57h+var_C0]
0x180018e98  lea     r9, [rbp+57h+var_B0]
0x180018e9c  mov     [rsp+0F0h+var_C8], 0
0x180018ea4  lea     r8, [rbp+57h+var_90]
0x180018ea8  lea     rdx, [rbp+57h+var_40]
0x180018eac  mov     [rsp+0F0h+var_D0], 0
0x180018eb5  movdqu  [rbp+57h+var_40], xmm0
0x180018eba  call    cs:__imp_VaultRemoveItem
0x180018ec0  mov     ebx, eax
0x180018ec2  test    eax, eax
0x180018ec4  jle     short loc_180018ECF
0x180018ec6  movzx   ebx, ax
0x180018ec9  or      ebx, 80070000h
0x180018ecf  lea     rcx, [rbp+57h+var_C0]
0x180018ed3  call    cs:__imp_VaultCloseVault
0x180018ed9  lea     rcx, [rbp+57h+var_70]; this
0x180018edd  call    ??1CConvenienceLogonEnrollmentData@@UEAA@XZ; CConvenienceLogonEnrollmentData::~CConvenienceLogonEnrollmentData(void)
0x180018ee2  test    edi, edi
0x180018ee4  cmovs   ebx, edi
0x180018ee7  lea     rcx, [rbp+57h+StringSid]
0x180018eeb  call    ??1?$CLocalMemPtr@G@@QEAA@XZ; CLocalMemPtr<ushort>::~CLocalMemPtr<ushort>(void)
0x180018ef0  mov     eax, ebx
0x180018ef2  mov     rcx, [rbp+57h+var_30]
0x180018ef6  xor     rcx, rsp; StackCookie
0x180018ef9  call    __security_check_cookie
0x180018efe  add     rsp, 0D8h
0x180018f05  pop     rdi
0x180018f06  pop     rsi
0x180018f07  pop     rbx
0x180018f08  pop     rbp
0x180018f09  retn
```
