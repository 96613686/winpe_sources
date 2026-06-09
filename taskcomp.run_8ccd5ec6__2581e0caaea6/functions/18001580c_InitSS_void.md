# InitSS(void)

- ea: `0x18001580c`
- end: `0x180015b0a`
- name: `?InitSS@@YAJXZ`
- size: `766`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180011958`

## callees

- `0x1800040c0`
- `0x180007994`
- `0x1800089f8`
- `0x18001580c`
- `0x180030700`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180015ae3`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180015ae3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015871`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015884`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015897`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015871`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015884`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015897`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015a14`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015a14`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001596f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001596f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001592b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001592b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015a04`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015a04`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180015861`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180015861`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800159a2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800159a2`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180015a34`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180015a34`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180015a5e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180015a5e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180015a70`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180015a70`

## string_xrefs

- `0x18001591d`: `SOFTWARE\Microsoft\SchedulingAgent`

## pseudocode

```c
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
    word_180060230 = 0;
    v6 = 43;
    if ( (((_BYTE)gccComputerName - 1) & 1) == 0 )
      v6 = 45;
    word_18006022E = v6;
    v7 = byte_18006022C;
    if ( byte_18006022C > (char *)v0 )
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
0x18001580c  push    rbp
0x18001580e  push    rbx
0x18001580f  push    rsi
0x180015810  push    rdi
0x180015811  lea     rbp, [rsp-3Fh]
0x180015816  sub     rsp, 0B8h
0x18001581d  mov     rax, cs:__security_cookie
0x180015824  xor     rax, rsp
0x180015827  mov     [rbp+57h+var_30], rax
0x18001582b  xorps   xmm0, xmm0
0x18001582e  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180015836  lea     rdi, ?gwszComputerName@@3PAGA; ushort near * gwszComputerName
0x18001583d  mov     cs:?gccComputerName@@3KA, 11h; ulong gccComputerName
0x180015847  xor     esi, esi
0x180015849  lea     rdx, ?gccComputerName@@3KA; nSize
0x180015850  mov     rcx, rdi; lpBuffer
0x180015853  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], rsi
0x180015857  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.RootDirectory], xmm0
0x18001585c  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180015861  call    cs:__imp_GetComputerNameW
0x180015868  nop     dword ptr [rax+rax+00h]
0x18001586d  test    eax, eax
0x18001586f  jnz     short loc_1800158BB
0x180015871  call    cs:__imp_GetLastError
0x180015878  nop     dword ptr [rax+rax+00h]
0x18001587d  test    eax, 1FFF0000h
0x180015882  jz      short loc_180015897
0x180015884  call    cs:__imp_GetLastError
0x18001588b  nop     dword ptr [rax+rax+00h]
0x180015890  mov     ebx, eax
0x180015892  jmp     loc_180015AEF
0x180015897  call    cs:__imp_GetLastError
0x18001589e  nop     dword ptr [rax+rax+00h]
0x1800158a3  mov     ebx, eax
0x1800158a5  test    eax, eax
0x1800158a7  jle     loc_180015AEF
0x1800158ad  movzx   ebx, ax
0x1800158b0  or      ebx, 80070000h
0x1800158b6  jmp     loc_180015AEF
0x1800158bb  mov     ecx, cs:?gccComputerName@@3KA; ulong gccComputerName
0x1800158c1  mov     eax, 2
0x1800158c6  inc     ecx
0x1800158c8  mul     rcx
0x1800158cb  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800158d2  cmovb   rax, rcx
0x1800158d6  mov     rcx, rax; unsigned __int64
0x1800158d9  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800158de  mov     cs:?gpwszComputerName@@3PEAGEA, rax; ushort * gpwszComputerName
0x1800158e5  mov     rcx, rax; unsigned __int16 *
0x1800158e8  test    rax, rax
0x1800158eb  jnz     short loc_1800158F7
0x1800158ed  mov     ebx, 8007000Eh
0x1800158f2  jmp     loc_180015AEF
0x1800158f7  mov     edx, cs:?gccComputerName@@3KA; ulong gccComputerName
0x1800158fd  mov     r8, rdi; unsigned __int16 *
0x180015900  inc     edx; unsigned __int64
0x180015902  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180015907  lea     rax, [rbp+57h+hKey]
0x18001590b  mov     [rbp+57h+hKey], rsi
0x18001590f  mov     r9d, 3; samDesired
0x180015915  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18001591a  xor     r8d, r8d; ulOptions
0x18001591d  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\SchedulingAgent"
0x180015924  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001592b  call    cs:__imp_RegOpenKeyExW
0x180015932  nop     dword ptr [rax+rax+00h]
0x180015937  mov     ebx, eax
0x180015939  test    eax, eax
0x18001593b  jnz     loc_1800158A7
0x180015941  mov     rcx, [rbp+57h+hKey]; hKey
0x180015945  lea     rax, [rbp+57h+cbData]
0x180015949  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x18001594e  lea     r9, [rbp+57h+Type]; lpType
0x180015952  lea     rax, [rbp+57h+Data]
0x180015956  mov     [rbp+57h+Type], esi
0x180015959  xor     r8d, r8d; lpReserved
0x18001595c  mov     [rsp+0D0h+phkResult], rax; lpData
0x180015961  lea     rdx, aOldname; "OldName"
0x180015968  mov     [rbp+57h+cbData], 22h ; '"'
0x18001596f  call    cs:__imp_RegQueryValueExW
0x180015976  nop     dword ptr [rax+rax+00h]
0x18001597b  test    eax, eax
0x18001597d  jnz     short loc_1800159DA
0x18001597f  cmp     [rbp+57h+Type], 1
0x180015983  jnz     short loc_1800159DA
0x180015985  mov     ecx, [rbp+57h+cbData]
0x180015988  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18001598c  add     rcx, 0FFFFFFFFFFFFFFFEh
0x180015990  cmp     rcx, 22h ; '"'
0x180015994  jnb     short loc_1800159D4
0x180015996  mov     word ptr [rbp+rcx+57h+Data], si
0x18001599b  lea     rdx, [rbp+57h+Data]; lpString2
0x18001599f  mov     rcx, rdi; lpString1
0x1800159a2  call    cs:__imp_lstrcmpiW
0x1800159a9  nop     dword ptr [rax+rax+00h]
0x1800159ae  test    eax, eax
0x1800159b0  jz      short loc_180015A10
0x1800159b2  lea     r8, [rbp+57h+Data]; unsigned __int16 *
0x1800159b6  mov     rcx, rdi; unsigned __int16 *
0x1800159b9  lea     edx, [rbx+11h]; unsigned __int64
0x1800159bc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800159c1  mov     r10d, [rbp+57h+cbData]
0x1800159c5  shr     r10d, 1
0x1800159c8  dec     r10d
0x1800159cb  mov     cs:?gccComputerName@@3KA, r10d; ulong gccComputerName
0x1800159d2  jmp     short loc_180015A10
0x1800159d4  call    __report_rangecheckfailure
0x1800159da  mov     eax, cs:?gccComputerName@@3KA; ulong gccComputerName
0x1800159e0  lea     rdx, aOldname; "OldName"
0x1800159e7  mov     rcx, [rbp+57h+hKey]; hKey
0x1800159eb  mov     r9d, 1; dwType
0x1800159f1  xor     r8d, r8d; Reserved
0x1800159f4  lea     eax, ds:2[rax*2]
0x1800159fb  mov     dword ptr [rsp+0D0h+lpcbData], eax; cbData
0x1800159ff  mov     [rsp+0D0h+phkResult], rdi; lpData
0x180015a04  call    cs:__imp_RegSetValueExW
0x180015a0b  nop     dword ptr [rax+rax+00h]
0x180015a10  mov     rcx, [rbp+57h+hKey]; hKey
0x180015a14  call    cs:__imp_RegCloseKey
0x180015a1b  nop     dword ptr [rax+rax+00h]
0x180015a20  lea     r9, [rbp+57h+PolicyHandle]; PolicyHandle
0x180015a24  mov     [rbp+57h+PolicyHandle], rsi
0x180015a28  mov     r8d, 1; DesiredAccess
0x180015a2e  lea     rdx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180015a32  xor     ecx, ecx; SystemName
0x180015a34  call    cs:__imp_LsaOpenPolicy
0x180015a3b  nop     dword ptr [rax+rax+00h]
0x180015a40  test    eax, eax
0x180015a42  jns     short loc_180015A4E
0x180015a44  mov     ebx, 8000FFFFh
0x180015a49  jmp     loc_180015AEF
0x180015a4e  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x180015a52  lea     r8, ?gpDomainInfo@@3PEAU_POLICY_ACCOUNT_DOMAIN_INFO@@EA; Buffer
0x180015a59  mov     edx, 5; InformationClass
0x180015a5e  call    cs:__imp_LsaQueryInformationPolicy
0x180015a65  nop     dword ptr [rax+rax+00h]
0x180015a6a  mov     rcx, [rbp+57h+PolicyHandle]; ObjectHandle
0x180015a6e  mov     ebx, eax
0x180015a70  call    cs:__imp_LsaClose
0x180015a77  nop     dword ptr [rax+rax+00h]
0x180015a7c  test    ebx, ebx
0x180015a7e  js      short loc_180015A44
0x180015a80  cmp     cs:?gwszComputerName@@3PAGA, si; ushort near * gwszComputerName
0x180015a87  jz      short loc_180015A92
0x180015a89  add     rdi, 2
0x180015a8d  cmp     [rdi], si
0x180015a90  jnz     short loc_180015A89
0x180015a92  mov     eax, cs:?gccComputerName@@3KA; ulong gccComputerName
0x180015a98  mov     ebx, esi
0x180015a9a  dec     eax
0x180015a9c  mov     cs:word_180060230, si
0x180015aa3  test    al, 1
0x180015aa5  mov     eax, 2Bh ; '+'
0x180015aaa  jnz     short loc_180015AB1
0x180015aac  mov     eax, 2Dh ; '-'
0x180015ab1  mov     cs:word_18006022E, ax
0x180015ab8  mov     ecx, 20h ; ' '
0x180015abd  lea     rax, byte_18006022C
0x180015ac4  cmp     rax, rdi
0x180015ac7  jbe     short loc_180015AD5
0x180015ac9  mov     [rax], cx
0x180015acc  sub     rax, 2
0x180015ad0  cmp     rax, rdi
0x180015ad3  jnz     short loc_180015AC9
0x180015ad5  mov     [rdi], cx
0x180015ad8  mov     rcx, cs:?gpDomainInfo@@3PEAU_POLICY_ACCOUNT_DOMAIN_INFO@@EA; _POLICY_ACCOUNT_DOMAIN_INFO * gpDomainInfo
0x180015adf  mov     rcx, [rcx+10h]; pSid
0x180015ae3  call    cs:__imp_GetLengthSid
0x180015aea  nop     dword ptr [rax+rax+00h]
0x180015aef  mov     eax, ebx
0x180015af1  mov     rcx, [rbp+57h+var_30]
0x180015af5  xor     rcx, rsp; StackCookie
0x180015af8  call    __security_check_cookie
0x180015afd  add     rsp, 0B8h
0x180015b04  pop     rdi
0x180015b05  pop     rsi
0x180015b06  pop     rbx
0x180015b07  pop     rbp
0x180015b08  retn
```
