# InitSS(void)

- ea: `0x180014b04`
- end: `0x180014db3`
- name: `?InitSS@@YAJXZ`
- size: `687`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180010efc`

## callees

- `0x180003ef0`
- `0x1800074d4`
- `0x180008538`
- `0x180014b04`
- `0x18002e5b0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180014d93`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180014d93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b7d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014cdc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014cdc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014c49`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014c49`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014c0b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014c0b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180014cd2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180014cd2`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180014b59`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180014b59`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180014c76`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180014c76`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180014cf6`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180014cf6`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180014d1a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180014d1a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180014d26`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180014d26`

## string_xrefs

- `0x180014bfd`: `SOFTWARE\Microsoft\SchedulingAgent`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 InitSS(void)
{
  WCHAR *v0; // rdi
  unsigned int v1; // ebx
  signed int LastError; // eax
  bool v3; // cc
  unsigned __int64 v4; // rcx
  NTSTATUS InformationPolicy; // ebx
  __int16 v6; // ax
  char *v7; // rax
  DWORD cbData; // [rsp+30h] [rbp-49h] BYREF
  DWORD Type; // [rsp+34h] [rbp-45h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-41h] BYREF
  PVOID PolicyHandle; // [rsp+40h] [rbp-39h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-31h] BYREF
  BYTE Data[2]; // [rsp+78h] [rbp-1h] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  v0 = &gwszComputerName;
  gccComputerName = 17;
  memset(&ObjectAttributes.RootDirectory, 0, 40);
  if ( !GetComputerNameW(&gwszComputerName, &gccComputerName) )
  {
    if ( (GetLastError() & 0x1FFF0000) != 0 )
      return GetLastError();
    LastError = GetLastError();
    v1 = LastError;
    v3 = LastError <= 0;
    goto LABEL_5;
  }
  gpwszComputerName = operator new[](saturated_mul(gccComputerName + 1, 2u));
  if ( !gpwszComputerName )
    return (unsigned int)-2147024882;
  StringCchCopyW((unsigned __int16 *)gpwszComputerName, gccComputerName + 1, &gwszComputerName);
  hKey = 0;
  LastError = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\SchedulingAgent", 0, 3u, &hKey);
  v1 = LastError;
  v3 = LastError <= 0;
  if ( LastError )
  {
LABEL_5:
    if ( !v3 )
      return (unsigned __int16)LastError | 0x80070000;
    return v1;
  }
  Type = 0;
  cbData = 34;
  if ( RegQueryValueExW(hKey, L"OldName", 0, &Type, Data, &cbData) || Type != 1 )
  {
    RegSetValueExW(hKey, L"OldName", 0, 1u, (const BYTE *)&gwszComputerName, 2 * gccComputerName + 2);
  }
  else
  {
    v4 = (cbData & 0xFFFFFFFE) - 2LL;
    if ( v4 >= 0x22 )
      _report_rangecheckfailure();
    *(_WORD *)&Data[v4] = 0;
    if ( lstrcmpiW(&gwszComputerName, (LPCWSTR)Data) )
    {
      StringCchCopyW(&gwszComputerName, v1 + 17, (const unsigned __int16 *)Data);
      gccComputerName = (cbData >> 1) - 1;
    }
  }
  RegCloseKey(hKey);
  PolicyHandle = 0;
  if ( LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle) < 0 )
    return (unsigned int)-2147418113;
  InformationPolicy = LsaQueryInformationPolicy(PolicyHandle, PolicyAccountDomainInformation, &gpDomainInfo);
  LsaClose(PolicyHandle);
  if ( InformationPolicy < 0 )
  {
    return (unsigned int)-2147418113;
  }
  else
  {
    if ( gwszComputerName )
    {
      do
        ++v0;
      while ( *v0 );
    }
    v1 = 0;
    word_18005E230 = 0;
    v6 = 43;
    if ( (((_BYTE)gccComputerName - 1) & 1) == 0 )
      v6 = 45;
    word_18005E22E = v6;
    v7 = byte_18005E22C;
    if ( byte_18005E22C > (char *)v0 )
    {
      do
      {
        *(_WORD *)v7 = 32;
        v7 -= 2;
      }
      while ( v7 != (char *)v0 );
    }
    *v0 = 32;
    GetLengthSid(*((PSID *)gpDomainInfo + 2));
  }
  return v1;
}

```

## disassembly

```asm
0x180014b04  push    rbp
0x180014b06  push    rbx
0x180014b07  push    rsi
0x180014b08  push    rdi
0x180014b09  lea     rbp, [rsp-3Fh]
0x180014b0e  sub     rsp, 0B8h
0x180014b15  mov     rax, cs:__security_cookie
0x180014b1c  xor     rax, rsp
0x180014b1f  mov     [rbp+57h+var_30], rax
0x180014b23  xorps   xmm0, xmm0
0x180014b26  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180014b2e  lea     rdi, ?gwszComputerName@@3PAGA; ushort near * gwszComputerName
0x180014b35  mov     cs:?gccComputerName@@3KA, 11h; ulong gccComputerName
0x180014b3f  xor     esi, esi
0x180014b41  lea     rdx, ?gccComputerName@@3KA; nSize
0x180014b48  mov     rcx, rdi; lpBuffer
0x180014b4b  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], rsi
0x180014b4f  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.RootDirectory], xmm0
0x180014b54  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180014b59  call    cs:__imp_GetComputerNameW
0x180014b5f  test    eax, eax
0x180014b61  jnz     short loc_180014B9B
0x180014b63  call    cs:__imp_GetLastError
0x180014b69  test    eax, 1FFF0000h
0x180014b6e  jz      short loc_180014B7D
0x180014b70  call    cs:__imp_GetLastError
0x180014b76  mov     ebx, eax
0x180014b78  jmp     loc_180014D99
0x180014b7d  call    cs:__imp_GetLastError
0x180014b83  mov     ebx, eax
0x180014b85  test    eax, eax
0x180014b87  jle     loc_180014D99
0x180014b8d  movzx   ebx, ax
0x180014b90  or      ebx, 80070000h
0x180014b96  jmp     loc_180014D99
0x180014b9b  mov     ecx, cs:?gccComputerName@@3KA; ulong gccComputerName
0x180014ba1  mov     eax, 2
0x180014ba6  inc     ecx
0x180014ba8  mul     rcx
0x180014bab  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180014bb2  cmovb   rax, rcx
0x180014bb6  mov     rcx, rax; unsigned __int64
0x180014bb9  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180014bbe  mov     cs:?gpwszComputerName@@3PEAGEA, rax; ushort * gpwszComputerName
0x180014bc5  mov     rcx, rax; unsigned __int16 *
0x180014bc8  test    rax, rax
0x180014bcb  jnz     short loc_180014BD7
0x180014bcd  mov     ebx, 8007000Eh
0x180014bd2  jmp     loc_180014D99
0x180014bd7  mov     edx, cs:?gccComputerName@@3KA; ulong gccComputerName
0x180014bdd  mov     r8, rdi; unsigned __int16 *
0x180014be0  inc     edx; unsigned __int64
0x180014be2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180014be7  lea     rax, [rbp+57h+hKey]
0x180014beb  mov     [rbp+57h+hKey], rsi
0x180014bef  mov     r9d, 3; samDesired
0x180014bf5  mov     [rsp+0D0h+phkResult], rax; phkResult
0x180014bfa  xor     r8d, r8d; ulOptions
0x180014bfd  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\SchedulingAgent"
0x180014c04  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014c0b  call    cs:__imp_RegOpenKeyExW
0x180014c11  mov     ebx, eax
0x180014c13  test    eax, eax
0x180014c15  jnz     loc_180014B87
0x180014c1b  mov     rcx, [rbp+57h+hKey]; hKey
0x180014c1f  lea     rax, [rbp+57h+cbData]
0x180014c23  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x180014c28  lea     r9, [rbp+57h+Type]; lpType
0x180014c2c  lea     rax, [rbp+57h+Data]
0x180014c30  mov     [rbp+57h+Type], esi
0x180014c33  xor     r8d, r8d; lpReserved
0x180014c36  mov     [rsp+0D0h+phkResult], rax; lpData
0x180014c3b  lea     rdx, aOldname; "OldName"
0x180014c42  mov     [rbp+57h+cbData], 22h ; '"'
0x180014c49  call    cs:__imp_RegQueryValueExW
0x180014c4f  test    eax, eax
0x180014c51  jnz     short loc_180014CA8
0x180014c53  cmp     [rbp+57h+Type], 1
0x180014c57  jnz     short loc_180014CA8
0x180014c59  mov     ecx, [rbp+57h+cbData]
0x180014c5c  and     rcx, 0FFFFFFFFFFFFFFFEh
0x180014c60  add     rcx, 0FFFFFFFFFFFFFFFEh
0x180014c64  cmp     rcx, 22h ; '"'
0x180014c68  jnb     short loc_180014CA2
0x180014c6a  mov     word ptr [rbp+rcx+57h+Data], si
0x180014c6f  lea     rdx, [rbp+57h+Data]; lpString2
0x180014c73  mov     rcx, rdi; lpString1
0x180014c76  call    cs:__imp_lstrcmpiW
0x180014c7c  test    eax, eax
0x180014c7e  jz      short loc_180014CD8
0x180014c80  lea     r8, [rbp+57h+Data]; unsigned __int16 *
0x180014c84  mov     rcx, rdi; unsigned __int16 *
0x180014c87  lea     edx, [rbx+11h]; unsigned __int64
0x180014c8a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180014c8f  mov     r10d, [rbp+57h+cbData]
0x180014c93  shr     r10d, 1
0x180014c96  dec     r10d
0x180014c99  mov     cs:?gccComputerName@@3KA, r10d; ulong gccComputerName
0x180014ca0  jmp     short loc_180014CD8
0x180014ca2  call    __report_rangecheckfailure
0x180014ca8  mov     eax, cs:?gccComputerName@@3KA; ulong gccComputerName
0x180014cae  lea     rdx, aOldname; "OldName"
0x180014cb5  mov     rcx, [rbp+57h+hKey]; hKey
0x180014cb9  mov     r9d, 1; dwType
0x180014cbf  xor     r8d, r8d; Reserved
0x180014cc2  lea     eax, ds:2[rax*2]
0x180014cc9  mov     dword ptr [rsp+0D0h+lpcbData], eax; cbData
0x180014ccd  mov     [rsp+0D0h+phkResult], rdi; lpData
0x180014cd2  call    cs:__imp_RegSetValueExW
0x180014cd8  mov     rcx, [rbp+57h+hKey]; hKey
0x180014cdc  call    cs:__imp_RegCloseKey
0x180014ce2  lea     r9, [rbp+57h+PolicyHandle]; PolicyHandle
0x180014ce6  mov     [rbp+57h+PolicyHandle], rsi
0x180014cea  mov     r8d, 1; DesiredAccess
0x180014cf0  lea     rdx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180014cf4  xor     ecx, ecx; SystemName
0x180014cf6  call    cs:__imp_LsaOpenPolicy
0x180014cfc  test    eax, eax
0x180014cfe  jns     short loc_180014D0A
0x180014d00  mov     ebx, 8000FFFFh
0x180014d05  jmp     loc_180014D99
0x180014d0a  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x180014d0e  lea     r8, ?gpDomainInfo@@3PEAU_POLICY_ACCOUNT_DOMAIN_INFO@@EA; Buffer
0x180014d15  mov     edx, 5; InformationClass
0x180014d1a  call    cs:__imp_LsaQueryInformationPolicy
0x180014d20  mov     rcx, [rbp+57h+PolicyHandle]; ObjectHandle
0x180014d24  mov     ebx, eax
0x180014d26  call    cs:__imp_LsaClose
0x180014d2c  test    ebx, ebx
0x180014d2e  js      short loc_180014D00
0x180014d30  cmp     cs:?gwszComputerName@@3PAGA, si; ushort near * gwszComputerName
0x180014d37  jz      short loc_180014D42
0x180014d39  add     rdi, 2
0x180014d3d  cmp     [rdi], si
0x180014d40  jnz     short loc_180014D39
0x180014d42  mov     eax, cs:?gccComputerName@@3KA; ulong gccComputerName
0x180014d48  mov     ebx, esi
0x180014d4a  dec     eax
0x180014d4c  mov     cs:word_18005E230, si
0x180014d53  test    al, 1
0x180014d55  mov     eax, 2Bh ; '+'
0x180014d5a  jnz     short loc_180014D61
0x180014d5c  mov     eax, 2Dh ; '-'
0x180014d61  mov     cs:word_18005E22E, ax
0x180014d68  mov     ecx, 20h ; ' '
0x180014d6d  lea     rax, byte_18005E22C
0x180014d74  cmp     rax, rdi
0x180014d77  jbe     short loc_180014D85
0x180014d79  mov     [rax], cx
0x180014d7c  sub     rax, 2
0x180014d80  cmp     rax, rdi
0x180014d83  jnz     short loc_180014D79
0x180014d85  mov     [rdi], cx
0x180014d88  mov     rcx, cs:?gpDomainInfo@@3PEAU_POLICY_ACCOUNT_DOMAIN_INFO@@EA; _POLICY_ACCOUNT_DOMAIN_INFO * gpDomainInfo
0x180014d8f  mov     rcx, [rcx+10h]; pSid
0x180014d93  call    cs:__imp_GetLengthSid
0x180014d99  mov     eax, ebx
0x180014d9b  mov     rcx, [rbp+57h+var_30]
0x180014d9f  xor     rcx, rsp; StackCookie
0x180014da2  call    __security_check_cookie
0x180014da7  add     rsp, 0B8h
0x180014dae  pop     rdi
0x180014daf  pop     rsi
0x180014db0  pop     rbx
0x180014db1  pop     rbp
0x180014db2  retn
```
