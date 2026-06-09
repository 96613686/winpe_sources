# CPicturePasswordVault::GetEnrollmentStatus(void *)

- ea: `0x1800191c4`
- end: `0x18001926b`
- name: `?GetEnrollmentStatus@CPicturePasswordVault@@SAJPEAX@Z`
- size: `167`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800071c0`
- `0x180018f10`

## callees

- `0x180005a2c`
- `0x1800092b8`
- `0x1800191c4`
- `0x1800197cc`
- `0x1800198d4`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800191dd`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800191dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019244`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019244`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001922a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001922a`

## pseudocode

```c
__int64 __fastcall CPicturePasswordVault::GetEnrollmentStatus(void *a1)
{
  const unsigned __int16 *v1; // r8
  int Error; // ebx
  LSTATUS v3; // eax
  bool v4; // sf
  _BYTE v6[8]; // [rsp+30h] [rbp-30h] BYREF
  LPCWSTR lpSubKey; // [rsp+38h] [rbp-28h]
  int v8; // [rsp+40h] [rbp-20h]
  HKEY hKey; // [rsp+48h] [rbp-18h]
  LPWSTR StringSid; // [rsp+78h] [rbp+18h] BYREF
  HKEY phkResult; // [rsp+80h] [rbp+20h] BYREF

  StringSid = 0;
  if ( ConvertSidToStringSidW(a1, &StringSid) || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    CConvenienceLogonEnrollmentData::CConvenienceLogonEnrollmentData(
      (CConvenienceLogonEnrollmentData *)v6,
      StringSid,
      v1);
    Error = v8;
    if ( v8 >= 0 )
    {
      Error = 1;
      phkResult = 0;
      v3 = RegOpenKeyExW(hKey, lpSubKey, 0, 1u, &phkResult);
      v4 = v3 < 0;
      if ( v3 > 0 )
        v4 = 1;
      if ( !v4 )
      {
        RegCloseKey(phkResult);
        Error = 0;
      }
    }
    CConvenienceLogonEnrollmentData::~CConvenienceLogonEnrollmentData((CConvenienceLogonEnrollmentData *)v6);
  }
  CLocalMemPtr<unsigned short>::~CLocalMemPtr<unsigned short>((void **)&StringSid);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800191c4  mov     [rsp-8+arg_0], rbx
0x1800191c9  push    rbp
0x1800191ca  mov     rbp, rsp
0x1800191cd  sub     rsp, 60h
0x1800191d1  lea     rdx, [rbp+StringSid]; StringSid
0x1800191d5  mov     [rbp+StringSid], 0
0x1800191dd  call    cs:__imp_ConvertSidToStringSidW
0x1800191e3  test    eax, eax
0x1800191e5  jnz     short loc_1800191F2
0x1800191e7  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800191ec  mov     ebx, eax
0x1800191ee  test    eax, eax
0x1800191f0  js      short loc_180019255
0x1800191f2  mov     rdx, [rbp+StringSid]; unsigned __int16 *
0x1800191f6  lea     rcx, [rbp+var_30]; this
0x1800191fa  call    ??0CConvenienceLogonEnrollmentData@@QEAA@PEBG0@Z; CConvenienceLogonEnrollmentData::CConvenienceLogonEnrollmentData(ushort const *,ushort const *)
0x1800191ff  mov     ebx, [rbp+var_20]
0x180019202  test    ebx, ebx
0x180019204  js      short loc_18001924C
0x180019206  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18001920a  lea     rax, [rbp+arg_10]
0x18001920e  mov     rcx, [rbp+hKey]; hKey
0x180019212  mov     ebx, 1
0x180019217  mov     r9d, ebx; samDesired
0x18001921a  mov     [rbp+arg_10], 0
0x180019222  xor     r8d, r8d; ulOptions
0x180019225  mov     [rsp+60h+phkResult], rax; phkResult
0x18001922a  call    cs:__imp_RegOpenKeyExW
0x180019230  test    eax, eax
0x180019232  jle     short loc_18001923E
0x180019234  movzx   eax, ax
0x180019237  or      eax, 80070000h
0x18001923c  test    eax, eax
0x18001923e  js      short loc_18001924C
0x180019240  mov     rcx, [rbp+arg_10]; hKey
0x180019244  call    cs:__imp_RegCloseKey
0x18001924a  xor     ebx, ebx
0x18001924c  lea     rcx, [rbp+var_30]; this
0x180019250  call    ??1CConvenienceLogonEnrollmentData@@UEAA@XZ; CConvenienceLogonEnrollmentData::~CConvenienceLogonEnrollmentData(void)
0x180019255  lea     rcx, [rbp+StringSid]
0x180019259  call    ??1?$CLocalMemPtr@G@@QEAA@XZ; CLocalMemPtr<ushort>::~CLocalMemPtr<ushort>(void)
0x18001925e  mov     eax, ebx
0x180019260  mov     rbx, [rsp+60h+arg_0]
0x180019265  add     rsp, 60h
0x180019269  pop     rbp
0x18001926a  retn
```
