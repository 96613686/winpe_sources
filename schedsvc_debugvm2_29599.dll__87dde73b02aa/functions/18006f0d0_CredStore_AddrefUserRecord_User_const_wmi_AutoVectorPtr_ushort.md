# CredStore::AddrefUserRecord(User const &,wmi::AutoVectorPtr<ushort> &)

- ea: `0x18006f0d0`
- end: `0x18006f482`
- name: `?AddrefUserRecord@CredStore@@AEAAJAEBVUser@@AEAV?$AutoVectorPtr@G@wmi@@@Z`
- size: `946`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, User *this)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180055720`

## callees

- `0x18000dc30`
- `0x180021300`
- `0x1800290f0`
- `0x18002a9e0`
- `0x180030f80`
- `0x180037e10`
- `0x18003f940`
- `0x1800408b0`
- `0x18005790c`
- `0x18006f0d0`
- `0x18007e68a`
- `0x18007e6d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006f43a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006f43a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006f18f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006f18f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006f269`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006f29d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006f38e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006f269`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006f29d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006f38e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006f2f1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006f331`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006f2f1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006f331`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006f1e0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006f1e0`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18006f21e`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18006f21e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18006f23c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18006f23c`

## string_xrefs

- `0x18006f409`: `TaskScheduler:Task:`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CredStore::AddrefUserRecord(LPCRITICAL_SECTION lpCriticalSection, User *this, unsigned __int16 **a3)
{
  int SidString; // ebx
  const WCHAR *v7; // rdx
  LSTATUS v8; // eax
  bool v9; // cc
  bool v10; // sf
  void *v11; // rax
  BYTE v13[8]; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[4]; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cbData; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  DWORD dwDisposition; // [rsp+70h] [rbp-90h] BYREF
  const WCHAR **v18; // [rsp+78h] [rbp-88h] BYREF
  __int64 v19; // [rsp+80h] [rbp-80h] BYREF
  void **pExceptionObject; // [rsp+88h] [rbp-78h] BYREF
  char v21; // [rsp+90h] [rbp-70h]
  const unsigned __int16 *v22; // [rsp+98h] [rbp-68h]
  __int64 v23; // [rsp+A0h] [rbp-60h]
  __int64 v24; // [rsp+A8h] [rbp-58h]
  int v25; // [rsp+B0h] [rbp-50h]
  __int64 v26; // [rsp+B4h] [rbp-4Ch]
  GUID pguid; // [rsp+C0h] [rbp-40h] BYREF
  OLECHAR sz; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v29[78]; // [rsp+D2h] [rbp-2Eh] BYREF

  v19 = 0;
  sz = 0;
  memset_0(v29, 0, sizeof(v29));
  SidString = User::GetSidString(this, (struct _bstr_t *)&v19);
  if ( SidString >= 0 )
  {
    hKey = 0;
    dwDisposition = 0;
    _bstr_t::_bstr_t((_bstr_t *)&v18, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Schedule\\CredWom");
    _bstr_t::_bstr_t((_bstr_t *)Data, L"\\");
    _bstr_t::operator+=(&v18, Data);
    _bstr_t::~_bstr_t((_bstr_t *)Data);
    _bstr_t::operator+=(&v18, &v19);
    EnterCriticalSection(lpCriticalSection);
    if ( v18 )
      v7 = *v18;
    else
      v7 = 0;
    v8 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v7, 0, 0, 0, 0x2001Fu, 0, &hKey, &dwDisposition);
    SidString = v8;
    v9 = v8 <= 0;
    if ( v8 )
      goto LABEL_6;
    if ( dwDisposition == 1 )
    {
      *(_DWORD *)Data = 1;
      pguid = 0;
      SidString = CoCreateGuid(&pguid);
      if ( SidString >= 0 )
      {
        StringFromGUID2(&pguid, &sz, 39);
        SidString = RegSetValueExW(hKey, L"Count", 0, 4u, Data, 4u);
        if ( !SidString )
        {
          SidString = RegSetValueExW(hKey, L"Index", 0, 1u, (const BYTE *)&sz, 0x4Eu);
          if ( !SidString )
          {
LABEL_23:
            v11 = operator new(0x74u);
            wmi::AutoVectorPtr<unsigned short>::operator=(a3, v11);
            if ( !*a3 )
            {
              v21 = 0;
              v22 = &qword_1800A4718;
              v23 = 0;
              v24 = 0;
              v25 = 14;
              v26 = -1;
              pExceptionObject = &wmi::GenericException::`vftable';
              throw (wmi::OutOfMemoryException *)&pExceptionObject;
            }
            SidString = StringCchCopyW(*a3, 0x3Au, L"TaskScheduler:Task:");
            if ( SidString >= 0 )
              SidString = StringCchCopyW(*a3 + 19, 0x27u, &sz);
            goto LABEL_27;
          }
        }
LABEL_20:
        v10 = SidString < 0;
        if ( SidString > 0 )
        {
          SidString = (unsigned __int16)SidString | 0x80070000;
          v10 = SidString < 0;
        }
        if ( v10 )
          goto LABEL_27;
        goto LABEL_23;
      }
    }
    else
    {
      *(_DWORD *)Data = 0;
      *(_DWORD *)v13 = 0;
      cbData = 78;
      v8 = RegQueryValueExW(hKey, L"Index", 0, (LPDWORD)Data, (LPBYTE)&sz, &cbData);
      SidString = v8;
      v9 = v8 <= 0;
      if ( v8 )
      {
LABEL_6:
        if ( !v9 )
          SidString = (unsigned __int16)v8 | 0x80070000;
        goto LABEL_27;
      }
      cbData = 4;
      SidString = RegQueryValueExW(hKey, L"Count", 0, (LPDWORD)Data, v13, &cbData);
      if ( SidString )
        goto LABEL_20;
      if ( *(_DWORD *)Data == 4 )
      {
        if ( *(_DWORD *)v13 != -1 )
        {
          ++*(_DWORD *)v13;
          SidString = RegSetValueExW(hKey, L"Count", 0, 4u, v13, 4u);
          goto LABEL_20;
        }
        SidString = -2147024362;
      }
      else
      {
        SidString = -2147216623;
      }
    }
LABEL_27:
    LeaveCriticalSection(lpCriticalSection);
    _bstr_t::~_bstr_t((_bstr_t *)&v18);
    wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
  }
  _bstr_t::~_bstr_t((_bstr_t *)&v19);
  return (unsigned int)SidString;
}

```

## disassembly

```asm
0x18006f0d0  mov     [rsp-8+arg_18], rbx
0x18006f0d5  push    rbp
0x18006f0d6  push    rsi
0x18006f0d7  push    r14
0x18006f0d9  lea     rbp, [rsp-30h]
0x18006f0de  sub     rsp, 130h
0x18006f0e5  mov     rax, cs:__security_cookie
0x18006f0ec  xor     rax, rsp
0x18006f0ef  mov     [rbp+40h+var_20], rax
0x18006f0f3  mov     rsi, r8
0x18006f0f6  mov     rbx, rdx
0x18006f0f9  mov     r14, rcx
0x18006f0fc  mov     [rbp+40h+var_C0], 0
0x18006f104  xor     eax, eax
0x18006f106  mov     [rbp+40h+sz], ax
0x18006f10a  xor     edx, edx; Val
0x18006f10c  lea     r8d, [rax+4Eh]; Size
0x18006f110  lea     rcx, [rbp+40h+var_6E]; void *
0x18006f114  call    memset_0
0x18006f119  lea     rdx, [rbp+40h+var_C0]; struct _bstr_t *
0x18006f11d  mov     rcx, rbx; this
0x18006f120  call    ?GetSidString@User@@QEBAJAEAV_bstr_t@@@Z; User::GetSidString(_bstr_t &)
0x18006f125  mov     ebx, eax
0x18006f127  test    eax, eax
0x18006f129  js      loc_18006F457
0x18006f12f  mov     [rsp+140h+hKey], 0
0x18006f138  mov     [rsp+140h+dwDisposition], 0
0x18006f140  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18006f147  lea     rcx, [rsp+140h+var_C8]; this
0x18006f14c  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18006f151  nop
0x18006f152  lea     rdx, asc_1800A3DA8; "\\"
0x18006f159  lea     rcx, [rsp+140h+Data]; this
0x18006f15e  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18006f163  nop
0x18006f164  lea     rdx, [rsp+140h+Data]
0x18006f169  lea     rcx, [rsp+140h+var_C8]
0x18006f16e  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x18006f173  nop
0x18006f174  lea     rcx, [rsp+140h+Data]; this
0x18006f179  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18006f17e  lea     rdx, [rbp+40h+var_C0]
0x18006f182  lea     rcx, [rsp+140h+var_C8]
0x18006f187  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x18006f18c  mov     rcx, r14; lpCriticalSection
0x18006f18f  call    cs:__imp_EnterCriticalSection
0x18006f195  mov     rax, [rsp+140h+var_C8]
0x18006f19a  test    rax, rax
0x18006f19d  jz      short loc_18006F1A4
0x18006f19f  mov     rdx, [rax]
0x18006f1a2  jmp     short loc_18006F1A6
0x18006f1a4  xor     edx, edx; lpSubKey
0x18006f1a6  lea     rax, [rsp+140h+dwDisposition]
0x18006f1ab  mov     [rsp+140h+lpdwDisposition], rax; lpdwDisposition
0x18006f1b0  lea     rax, [rsp+140h+hKey]
0x18006f1b5  mov     [rsp+140h+phkResult], rax; phkResult
0x18006f1ba  mov     [rsp+140h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18006f1c3  mov     [rsp+140h+samDesired], 2001Fh; samDesired
0x18006f1cb  mov     [rsp+140h+dwOptions], 0; dwOptions
0x18006f1d3  xor     r9d, r9d; lpClass
0x18006f1d6  xor     r8d, r8d; Reserved
0x18006f1d9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006f1e0  call    cs:__imp_RegCreateKeyExW
0x18006f1e6  mov     ebx, eax
0x18006f1e8  test    eax, eax
0x18006f1ea  jz      short loc_18006F200
0x18006f1ec  jle     loc_18006F437
0x18006f1f2  movzx   ebx, ax
0x18006f1f5  or      ebx, 80070000h
0x18006f1fb  jmp     loc_18006F437
0x18006f200  cmp     [rsp+140h+dwDisposition], 1
0x18006f205  jnz     loc_18006F2B2
0x18006f20b  mov     dword ptr [rsp+140h+Data], 1
0x18006f213  xorps   xmm0, xmm0
0x18006f216  movups  xmmword ptr [rbp+40h+pguid.Data1], xmm0
0x18006f21a  lea     rcx, [rbp+40h+pguid]; pguid
0x18006f21e  call    cs:__imp_CoCreateGuid
0x18006f224  mov     ebx, eax
0x18006f226  test    eax, eax
0x18006f228  js      loc_18006F437
0x18006f22e  mov     r8d, 27h ; '''; cchMax
0x18006f234  lea     rdx, [rbp+40h+sz]; lpsz
0x18006f238  lea     rcx, [rbp+40h+pguid]; rguid
0x18006f23c  call    cs:__imp_StringFromGUID2
0x18006f242  mov     [rsp+140h+samDesired], 4; cbData
0x18006f24a  lea     rax, [rsp+140h+Data]
0x18006f24f  mov     qword ptr [rsp+140h+dwOptions], rax; lpData
0x18006f254  mov     r9d, 4; dwType
0x18006f25a  xor     r8d, r8d; Reserved
0x18006f25d  lea     rdx, aCount; "Count"
0x18006f264  mov     rcx, [rsp+140h+hKey]; hKey
0x18006f269  call    cs:__imp_RegSetValueExW
0x18006f26f  mov     ebx, eax
0x18006f271  test    eax, eax
0x18006f273  jnz     loc_18006F396
0x18006f279  mov     [rsp+140h+samDesired], 4Eh ; 'N'; cbData
0x18006f281  lea     rax, [rbp+40h+sz]
0x18006f285  mov     qword ptr [rsp+140h+dwOptions], rax; lpData
0x18006f28a  lea     r9d, [rbx+1]; dwType
0x18006f28e  xor     r8d, r8d; Reserved
0x18006f291  lea     rdx, aIndex; "Index"
0x18006f298  mov     rcx, [rsp+140h+hKey]; hKey
0x18006f29d  call    cs:__imp_RegSetValueExW
0x18006f2a3  mov     ebx, eax
0x18006f2a5  test    eax, eax
0x18006f2a7  jz      loc_18006F3AB
0x18006f2ad  jmp     loc_18006F396
0x18006f2b2  mov     dword ptr [rsp+140h+Data], 0
0x18006f2ba  mov     dword ptr [rsp+140h+var_F0], 0
0x18006f2c2  mov     [rsp+140h+cbData], 4Eh ; 'N'
0x18006f2ca  lea     rax, [rsp+140h+cbData]
0x18006f2cf  mov     qword ptr [rsp+140h+samDesired], rax; lpcbData
0x18006f2d4  lea     rax, [rbp+40h+sz]
0x18006f2d8  mov     qword ptr [rsp+140h+dwOptions], rax; lpData
0x18006f2dd  lea     r9, [rsp+140h+Data]; lpType
0x18006f2e2  xor     r8d, r8d; lpReserved
0x18006f2e5  lea     rdx, aIndex; "Index"
0x18006f2ec  mov     rcx, [rsp+140h+hKey]; hKey
0x18006f2f1  call    cs:__imp_RegQueryValueExW
0x18006f2f7  mov     ebx, eax
0x18006f2f9  test    eax, eax
0x18006f2fb  jnz     loc_18006F1EC
0x18006f301  mov     [rsp+140h+cbData], 4
0x18006f309  lea     rax, [rsp+140h+cbData]
0x18006f30e  mov     qword ptr [rsp+140h+samDesired], rax; lpcbData
0x18006f313  lea     rax, [rsp+140h+var_F0]
0x18006f318  mov     qword ptr [rsp+140h+dwOptions], rax; lpData
0x18006f31d  lea     r9, [rsp+140h+Data]; lpType
0x18006f322  xor     r8d, r8d; lpReserved
0x18006f325  lea     rdx, aCount; "Count"
0x18006f32c  mov     rcx, [rsp+140h+hKey]; hKey
0x18006f331  call    cs:__imp_RegQueryValueExW
0x18006f337  mov     ebx, eax
0x18006f339  test    eax, eax
0x18006f33b  jnz     short loc_18006F396
0x18006f33d  cmp     dword ptr [rsp+140h+Data], 4
0x18006f342  jz      short loc_18006F34E
0x18006f344  mov     ebx, 80041311h
0x18006f349  jmp     loc_18006F437
0x18006f34e  mov     eax, dword ptr [rsp+140h+var_F0]
0x18006f352  cmp     eax, 0FFFFFFFFh
0x18006f355  jnz     short loc_18006F361
0x18006f357  mov     ebx, 80070216h
0x18006f35c  jmp     loc_18006F437
0x18006f361  inc     eax
0x18006f363  mov     dword ptr [rsp+140h+var_F0], eax
0x18006f367  mov     [rsp+140h+samDesired], 4; cbData
0x18006f36f  lea     rax, [rsp+140h+var_F0]
0x18006f374  mov     qword ptr [rsp+140h+dwOptions], rax; lpData
0x18006f379  mov     r9d, 4; dwType
0x18006f37f  xor     r8d, r8d; Reserved
0x18006f382  lea     rdx, aCount; "Count"
0x18006f389  mov     rcx, [rsp+140h+hKey]; hKey
0x18006f38e  call    cs:__imp_RegSetValueExW
0x18006f394  mov     ebx, eax
0x18006f396  test    ebx, ebx
0x18006f398  jle     short loc_18006F3A5
0x18006f39a  movzx   ebx, bx
0x18006f39d  or      ebx, 80070000h
0x18006f3a3  test    ebx, ebx
0x18006f3a5  js      loc_18006F437
0x18006f3ab  mov     ecx, 74h ; 't'; dwBytes
0x18006f3b0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006f3b5  mov     rdx, rax
0x18006f3b8  mov     rcx, rsi
0x18006f3bb  call    ??4?$AutoVectorPtr@G@wmi@@QEAAAEAV01@PEAG@Z; wmi::AutoVectorPtr<ushort>::operator=(ushort *)
0x18006f3c0  mov     rcx, [rsi]; unsigned __int16 *
0x18006f3c3  test    rcx, rcx
0x18006f3c6  jnz     short loc_18006F409
0x18006f3c8  mov     [rbp+40h+var_B0], cl
0x18006f3cb  lea     rax, qword_1800A4718
0x18006f3d2  mov     [rbp+40h+var_A8], rax
0x18006f3d6  mov     [rbp+40h+var_A0], rcx
0x18006f3da  mov     [rbp+40h+var_98], rcx
0x18006f3de  mov     [rbp+40h+var_90], 0Eh
0x18006f3e5  mov     [rbp+40h+var_8C], 0FFFFFFFFFFFFFFFFh
0x18006f3ed  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18006f3f4  mov     [rbp+40h+pExceptionObject], rax
0x18006f3f8  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18006f3ff  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x18006f403  call    _CxxThrowException_0
0x18006f409  lea     r8, aTaskschedulerT; "TaskScheduler:Task:"
0x18006f410  mov     edx, 3Ah ; ':'; unsigned __int64
0x18006f415  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006f41a  mov     ebx, eax
0x18006f41c  test    eax, eax
0x18006f41e  js      short loc_18006F437
0x18006f420  mov     rcx, [rsi]
0x18006f423  add     rcx, 26h ; '&'; unsigned __int16 *
0x18006f427  lea     r8, [rbp+40h+sz]; unsigned __int16 *
0x18006f42b  mov     edx, 27h ; '''; unsigned __int64
0x18006f430  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006f435  mov     ebx, eax
0x18006f437  mov     rcx, r14; lpCriticalSection
0x18006f43a  call    cs:__imp_LeaveCriticalSection
0x18006f440  nop
0x18006f441  lea     rcx, [rsp+140h+var_C8]; this
0x18006f446  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18006f44b  nop
0x18006f44c  lea     rcx, [rsp+140h+hKey]; this
0x18006f451  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x18006f456  nop
0x18006f457  lea     rcx, [rbp+40h+var_C0]; this
0x18006f45b  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18006f460  mov     eax, ebx
0x18006f462  mov     rcx, [rbp+40h+var_20]
0x18006f466  xor     rcx, rsp; StackCookie
0x18006f469  call    __security_check_cookie
0x18006f46e  mov     rbx, [rsp+140h+arg_18]
0x18006f476  add     rsp, 130h
0x18006f47d  pop     r14
0x18006f47f  pop     rsi
0x18006f480  pop     rbp
0x18006f481  retn
```
