# CredStore::ReleaseRefUserRecord(User const &,wmi::AutoVectorPtr<ushort> &)

- ea: `0x1800538f4`
- end: `0x180053c07`
- name: `?ReleaseRefUserRecord@CredStore@@AEAAJAEBVUser@@AEAV?$AutoVectorPtr@G@wmi@@@Z`
- size: `787`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, User *this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18006f488`

## callees

- `0x18000dc30`
- `0x180021300`
- `0x1800290f0`
- `0x18002a9e0`
- `0x180030f80`
- `0x180037e10`
- `0x18003f940`
- `0x1800408b0`
- `0x1800538f4`
- `0x18005790c`
- `0x18007e68a`
- `0x18007e6d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053bbe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053bbe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800539be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800539be`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180053b78`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180053b78`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180053ad8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180053ad8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800539ed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800539ed`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180053a41`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180053a8b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180053a41`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180053a8b`

## string_xrefs

- `0x180053b8d`: `TaskScheduler:Task:`

## pseudocode

```c
__int64 __fastcall CredStore::ReleaseRefUserRecord(
        LPCRITICAL_SECTION lpCriticalSection,
        User *this,
        unsigned __int16 **a3)
{
  int SidString; // ebx
  const WCHAR **v8; // rbx
  const WCHAR *v9; // rdx
  LSTATUS v10; // eax
  signed int v11; // edi
  LSTATUS v12; // eax
  int v13; // eax
  const WCHAR *v14; // rdx
  LSTATUS v15; // eax
  bool v16; // cc
  void *v17; // rax
  BYTE v18[4]; // [rsp+30h] [rbp-89h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-85h] BYREF
  DWORD Type; // [rsp+38h] [rbp-81h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-79h] BYREF
  const WCHAR **v22; // [rsp+48h] [rbp-71h] BYREF
  __int64 v23; // [rsp+50h] [rbp-69h] BYREF
  void **pExceptionObject; // [rsp+58h] [rbp-61h] BYREF
  char v25; // [rsp+60h] [rbp-59h]
  const unsigned __int16 *v26; // [rsp+68h] [rbp-51h]
  __int64 v27; // [rsp+70h] [rbp-49h]
  __int64 v28; // [rsp+78h] [rbp-41h]
  int v29; // [rsp+80h] [rbp-39h]
  __int64 v30; // [rsp+84h] [rbp-35h]
  BYTE Data[2]; // [rsp+90h] [rbp-29h] BYREF
  _BYTE v32[78]; // [rsp+92h] [rbp-27h] BYREF

  v23 = 0;
  *(_WORD *)Data = 0;
  memset_0(v32, 0, sizeof(v32));
  *(_DWORD *)v18 = 0;
  SidString = User::GetSidString(this, (struct _bstr_t *)&v23);
  if ( SidString < 0 )
  {
    _bstr_t::~_bstr_t((_bstr_t *)&v23);
    return (unsigned int)SidString;
  }
  hKey = 0;
  _bstr_t::_bstr_t((_bstr_t *)&v22, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Schedule\\CredWom");
  _bstr_t::_bstr_t((_bstr_t *)&Type, L"\\");
  _bstr_t::operator+=(&v22, &Type);
  _bstr_t::~_bstr_t((_bstr_t *)&Type);
  _bstr_t::operator+=(&v22, &v23);
  EnterCriticalSection(lpCriticalSection);
  v8 = v22;
  if ( v22 )
    v9 = *v22;
  else
    v9 = 0;
  v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v9, 0, 0xF003Fu, &hKey);
  if ( v10 > 0 )
    v11 = (unsigned __int16)v10 | 0x80070000;
  else
    v11 = v10;
  if ( v10 )
    goto LABEL_24;
  Type = 0;
  cbData = 78;
  v12 = RegQueryValueExW(hKey, L"Index", 0, &Type, Data, &cbData);
  if ( !v12 )
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"Count", 0, &Type, v18, &cbData) )
    {
      if ( Type != 4 )
      {
        v11 = -2147216623;
        goto LABEL_32;
      }
      v13 = *(_DWORD *)v18;
      if ( *(_DWORD *)v18 && (--*(_DWORD *)v18, v13 != 1) )
      {
        v15 = RegSetValueExW(hKey, L"Count", 0, 4u, v18, 4u);
        v11 = v15;
        v16 = v15 <= 0;
        if ( !v15 )
        {
          v11 = 1;
          goto LABEL_32;
        }
      }
      else
      {
        wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
        if ( v8 )
          v14 = *v8;
        else
          v14 = 0;
        v15 = RegDeleteTreeW(HKEY_LOCAL_MACHINE, v14);
        v11 = v15;
        v16 = v15 <= 0;
        if ( !v15 )
        {
LABEL_25:
          v17 = operator new(0x74u);
          wmi::AutoVectorPtr<unsigned short>::operator=(a3, v17);
          if ( !*a3 )
          {
            v25 = 0;
            v26 = &qword_1800A4718;
            v27 = 0;
            v28 = 0;
            v29 = 14;
            v30 = -1;
            pExceptionObject = &wmi::GenericException::`vftable';
            throw (wmi::OutOfMemoryException *)&pExceptionObject;
          }
          v11 = StringCchCopyW(*a3, 0x3Au, L"TaskScheduler:Task:");
          if ( v11 < 0 )
            goto LABEL_32;
          v12 = StringCchCopyW(*a3 + 19, 0x27u, (const unsigned __int16 *)Data);
          goto LABEL_31;
        }
      }
      if ( !v16 )
        v11 = (unsigned __int16)v15 | 0x80070000;
    }
LABEL_24:
    if ( v11 )
      goto LABEL_32;
    goto LABEL_25;
  }
  if ( v12 <= 0 )
  {
LABEL_31:
    v11 = v12;
    goto LABEL_32;
  }
  v11 = (unsigned __int16)v12 | 0x80070000;
LABEL_32:
  LeaveCriticalSection(lpCriticalSection);
  _bstr_t::~_bstr_t((_bstr_t *)&v22);
  wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
  _bstr_t::~_bstr_t((_bstr_t *)&v23);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800538f4  mov     [rsp-8+arg_18], rbx
0x1800538f9  push    rbp
0x1800538fa  push    rsi
0x1800538fb  push    rdi
0x1800538fc  push    r12
0x1800538fe  push    r14
0x180053900  lea     rbp, [rsp-37h]
0x180053905  sub     rsp, 0F0h
0x18005390c  mov     rax, cs:__security_cookie
0x180053913  xor     rax, rsp
0x180053916  mov     [rbp+57h+var_30], rax
0x18005391a  mov     rsi, r8
0x18005391d  mov     rbx, rdx
0x180053920  mov     r14, rcx
0x180053923  mov     [rbp+57h+var_C0], 0
0x18005392b  xor     eax, eax
0x18005392d  mov     word ptr [rbp+57h+Data], ax
0x180053931  xor     edx, edx; Val
0x180053933  lea     r8d, [rax+4Eh]; Size
0x180053937  lea     rcx, [rbp+57h+var_7E]; void *
0x18005393b  call    memset_0
0x180053940  mov     dword ptr [rsp+110h+var_E0], 0
0x180053948  lea     rdx, [rbp+57h+var_C0]; struct _bstr_t *
0x18005394c  mov     rcx, rbx; this
0x18005394f  call    ?GetSidString@User@@QEBAJAEAV_bstr_t@@@Z; User::GetSidString(_bstr_t &)
0x180053954  mov     ebx, eax
0x180053956  test    eax, eax
0x180053958  jns     short loc_18005396A
0x18005395a  lea     rcx, [rbp+57h+var_C0]; this
0x18005395e  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180053963  mov     eax, ebx
0x180053965  jmp     loc_180053BE4
0x18005396a  mov     [rbp+57h+hKey], 0
0x180053972  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180053979  lea     rcx, [rbp+57h+var_C8]; this
0x18005397d  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180053982  nop
0x180053983  lea     rdx, asc_1800A3DA8; "\\"
0x18005398a  lea     rcx, [rsp+110h+Type]; this
0x18005398f  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180053994  nop
0x180053995  lea     rdx, [rsp+110h+Type]
0x18005399a  lea     rcx, [rbp+57h+var_C8]
0x18005399e  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x1800539a3  nop
0x1800539a4  lea     rcx, [rsp+110h+Type]; this
0x1800539a9  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800539ae  lea     rdx, [rbp+57h+var_C0]
0x1800539b2  lea     rcx, [rbp+57h+var_C8]
0x1800539b6  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x1800539bb  mov     rcx, r14; lpCriticalSection
0x1800539be  call    cs:__imp_EnterCriticalSection
0x1800539c4  mov     rbx, [rbp+57h+var_C8]
0x1800539c8  test    rbx, rbx
0x1800539cb  jz      short loc_1800539D2
0x1800539cd  mov     rdx, [rbx]
0x1800539d0  jmp     short loc_1800539D4
0x1800539d2  xor     edx, edx; lpSubKey
0x1800539d4  lea     rax, [rbp+57h+hKey]
0x1800539d8  mov     [rsp+110h+phkResult], rax; phkResult
0x1800539dd  mov     r9d, 0F003Fh; samDesired
0x1800539e3  xor     r8d, r8d; ulOptions
0x1800539e6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800539ed  call    cs:__imp_RegOpenKeyExW
0x1800539f3  mov     r12d, 80070000h
0x1800539f9  test    eax, eax
0x1800539fb  jg      short loc_180053A01
0x1800539fd  mov     edi, eax
0x1800539ff  jmp     short loc_180053A07
0x180053a01  movzx   edi, ax
0x180053a04  or      edi, r12d
0x180053a07  test    eax, eax
0x180053a09  jnz     loc_180053AEC
0x180053a0f  mov     [rsp+110h+Type], eax
0x180053a13  mov     [rsp+110h+cbData], 4Eh ; 'N'
0x180053a1b  lea     rax, [rsp+110h+cbData]
0x180053a20  mov     [rsp+110h+lpcbData], rax; lpcbData
0x180053a25  lea     rax, [rbp+57h+Data]
0x180053a29  mov     [rsp+110h+phkResult], rax; lpData
0x180053a2e  lea     r9, [rsp+110h+Type]; lpType
0x180053a33  xor     r8d, r8d; lpReserved
0x180053a36  lea     rdx, aIndex; "Index"
0x180053a3d  mov     rcx, [rbp+57h+hKey]; hKey
0x180053a41  call    cs:__imp_RegQueryValueExW
0x180053a47  test    eax, eax
0x180053a49  jz      short loc_180053A5C
0x180053a4b  jle     loc_180053BB9
0x180053a51  movzx   edi, ax
0x180053a54  or      edi, r12d
0x180053a57  jmp     loc_180053BBB
0x180053a5c  mov     [rsp+110h+cbData], 4
0x180053a64  lea     rax, [rsp+110h+cbData]
0x180053a69  mov     [rsp+110h+lpcbData], rax; lpcbData
0x180053a6e  lea     rax, [rsp+110h+var_E0]
0x180053a73  mov     [rsp+110h+phkResult], rax; lpData
0x180053a78  lea     r9, [rsp+110h+Type]; lpType
0x180053a7d  xor     r8d, r8d; lpReserved
0x180053a80  lea     rdx, aCount; "Count"
0x180053a87  mov     rcx, [rbp+57h+hKey]; hKey
0x180053a8b  call    cs:__imp_RegQueryValueExW
0x180053a91  test    eax, eax
0x180053a93  jnz     short loc_180053AEC
0x180053a95  cmp     [rsp+110h+Type], 4
0x180053a9a  jz      short loc_180053AA6
0x180053a9c  mov     edi, 80041311h
0x180053aa1  jmp     loc_180053BBB
0x180053aa6  mov     eax, dword ptr [rsp+110h+var_E0]
0x180053aaa  test    eax, eax
0x180053aac  jz      short loc_180053ABC
0x180053aae  dec     eax
0x180053ab0  mov     dword ptr [rsp+110h+var_E0], eax
0x180053ab4  test    eax, eax
0x180053ab6  jnz     loc_180053B52
0x180053abc  lea     rcx, [rbp+57h+hKey]; this
0x180053ac0  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x180053ac5  test    rbx, rbx
0x180053ac8  jz      short loc_180053ACF
0x180053aca  mov     rdx, [rbx]
0x180053acd  jmp     short loc_180053AD1
0x180053acf  xor     edx, edx; lpSubKey
0x180053ad1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180053ad8  call    cs:__imp_RegDeleteTreeW
0x180053ade  mov     edi, eax
0x180053ae0  test    eax, eax
0x180053ae2  jz      short loc_180053AF4
0x180053ae4  jle     short loc_180053AEC
0x180053ae6  movzx   edi, ax
0x180053ae9  or      edi, r12d
0x180053aec  test    edi, edi
0x180053aee  jnz     loc_180053BBB
0x180053af4  mov     ecx, 74h ; 't'; dwBytes
0x180053af9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180053afe  mov     rdx, rax
0x180053b01  mov     rcx, rsi
0x180053b04  call    ??4?$AutoVectorPtr@G@wmi@@QEAAAEAV01@PEAG@Z; wmi::AutoVectorPtr<ushort>::operator=(ushort *)
0x180053b09  mov     rcx, [rsi]; unsigned __int16 *
0x180053b0c  test    rcx, rcx
0x180053b0f  jnz     short loc_180053B8D
0x180053b11  mov     [rbp+57h+var_B0], cl
0x180053b14  lea     rax, qword_1800A4718
0x180053b1b  mov     [rbp+57h+var_A8], rax
0x180053b1f  mov     [rbp+57h+var_A0], rcx
0x180053b23  mov     [rbp+57h+var_98], rcx
0x180053b27  mov     [rbp+57h+var_90], 0Eh
0x180053b2e  mov     [rbp+57h+var_8C], 0FFFFFFFFFFFFFFFFh
0x180053b36  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180053b3d  mov     [rbp+57h+pExceptionObject], rax
0x180053b41  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x180053b48  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180053b4c  call    _CxxThrowException_0
0x180053b52  mov     dword ptr [rsp+110h+lpcbData], 4; cbData
0x180053b5a  lea     rax, [rsp+110h+var_E0]
0x180053b5f  mov     [rsp+110h+phkResult], rax; lpData
0x180053b64  mov     r9d, 4; dwType
0x180053b6a  xor     r8d, r8d; Reserved
0x180053b6d  lea     rdx, aCount; "Count"
0x180053b74  mov     rcx, [rbp+57h+hKey]; hKey
0x180053b78  call    cs:__imp_RegSetValueExW
0x180053b7e  mov     edi, eax
0x180053b80  test    eax, eax
0x180053b82  jnz     loc_180053AE4
0x180053b88  lea     edi, [rax+1]
0x180053b8b  jmp     short loc_180053BBB
0x180053b8d  lea     r8, aTaskschedulerT; "TaskScheduler:Task:"
0x180053b94  mov     edx, 3Ah ; ':'; unsigned __int64
0x180053b99  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180053b9e  mov     edi, eax
0x180053ba0  test    eax, eax
0x180053ba2  js      short loc_180053BBB
0x180053ba4  mov     rcx, [rsi]
0x180053ba7  add     rcx, 26h ; '&'; unsigned __int16 *
0x180053bab  lea     r8, [rbp+57h+Data]; unsigned __int16 *
0x180053baf  mov     edx, 27h ; '''; unsigned __int64
0x180053bb4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180053bb9  mov     edi, eax
0x180053bbb  mov     rcx, r14; lpCriticalSection
0x180053bbe  call    cs:__imp_LeaveCriticalSection
0x180053bc4  nop
0x180053bc5  lea     rcx, [rbp+57h+var_C8]; this
0x180053bc9  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180053bce  nop
0x180053bcf  lea     rcx, [rbp+57h+hKey]; this
0x180053bd3  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x180053bd8  nop
0x180053bd9  lea     rcx, [rbp+57h+var_C0]; this
0x180053bdd  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180053be2  mov     eax, edi
0x180053be4  mov     rcx, [rbp+57h+var_30]
0x180053be8  xor     rcx, rsp; StackCookie
0x180053beb  call    __security_check_cookie
0x180053bf0  mov     rbx, [rsp+110h+arg_18]
0x180053bf8  add     rsp, 0F0h
0x180053bff  pop     r14
0x180053c01  pop     r12
0x180053c03  pop     rdi
0x180053c04  pop     rsi
0x180053c05  pop     rbp
0x180053c06  retn
```
