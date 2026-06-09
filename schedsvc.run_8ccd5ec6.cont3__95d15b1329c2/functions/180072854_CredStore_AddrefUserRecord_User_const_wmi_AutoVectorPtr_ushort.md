# CredStore::AddrefUserRecord(User const &,wmi::AutoVectorPtr<ushort> &)

- ea: `0x180072854`
- end: `0x180072c43`
- name: `?AddrefUserRecord@CredStore@@AEAAJAEBVUser@@AEAV?$AutoVectorPtr@G@wmi@@@Z`
- size: `1007`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, User *this)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180058010`

## callees

- `0x180011e40`
- `0x180027910`
- `0x18002db40`
- `0x1800301f0`
- `0x180039fd0`
- `0x18003bd70`
- `0x180041020`
- `0x1800423e0`
- `0x18005a2bc`
- `0x180072854`
- `0x1800829fa`
- `0x180082a40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180072bf4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180072bf4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180072913`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180072913`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180072a05`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180072a3f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180072b42`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180072a05`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180072a3f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180072b42`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180072a99`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180072adf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180072a99`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180072adf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007296a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007296a`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800729ae`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800729ae`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800729d2`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800729d2`

## string_xrefs

- `0x180072bc3`: `TaskScheduler:Task:`

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
              v22 = &qword_1800A8718;
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
0x180072854  mov     [rsp-8+arg_18], rbx
0x180072859  push    rbp
0x18007285a  push    rsi
0x18007285b  push    r14
0x18007285d  lea     rbp, [rsp-30h]
0x180072862  sub     rsp, 130h
0x180072869  mov     rax, cs:__security_cookie
0x180072870  xor     rax, rsp
0x180072873  mov     [rbp+40h+var_20], rax
0x180072877  mov     rsi, r8
0x18007287a  mov     rbx, rdx
0x18007287d  mov     r14, rcx
0x180072880  mov     [rbp+40h+var_C0], 0
0x180072888  xor     eax, eax
0x18007288a  mov     [rbp+40h+sz], ax
0x18007288e  xor     edx, edx; Val
0x180072890  lea     r8d, [rax+4Eh]; Size
0x180072894  lea     rcx, [rbp+40h+var_6E]; void *
0x180072898  call    memset_0
0x18007289d  lea     rdx, [rbp+40h+var_C0]; struct _bstr_t *
0x1800728a1  mov     rcx, rbx; this
0x1800728a4  call    ?GetSidString@User@@QEBAJAEAV_bstr_t@@@Z; User::GetSidString(_bstr_t &)
0x1800728a9  mov     ebx, eax
0x1800728ab  test    eax, eax
0x1800728ad  js      loc_180072C17
0x1800728b3  mov     [rsp+140h+hKey], 0
0x1800728bc  mov     [rsp+140h+dwDisposition], 0
0x1800728c4  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800728cb  lea     rcx, [rsp+140h+var_C8]; this
0x1800728d0  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800728d5  nop
0x1800728d6  lea     rdx, asc_1800A7EC0; "\\"
0x1800728dd  lea     rcx, [rsp+140h+Data]; this
0x1800728e2  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800728e7  nop
0x1800728e8  lea     rdx, [rsp+140h+Data]
0x1800728ed  lea     rcx, [rsp+140h+var_C8]
0x1800728f2  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x1800728f7  nop
0x1800728f8  lea     rcx, [rsp+140h+Data]; this
0x1800728fd  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180072902  lea     rdx, [rbp+40h+var_C0]
0x180072906  lea     rcx, [rsp+140h+var_C8]
0x18007290b  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x180072910  mov     rcx, r14; lpCriticalSection
0x180072913  call    cs:__imp_EnterCriticalSection
0x18007291a  nop     dword ptr [rax+rax+00h]
0x18007291f  mov     rax, [rsp+140h+var_C8]
0x180072924  test    rax, rax
0x180072927  jz      short loc_18007292E
0x180072929  mov     rdx, [rax]
0x18007292c  jmp     short loc_180072930
0x18007292e  xor     edx, edx; lpSubKey
0x180072930  lea     rax, [rsp+140h+dwDisposition]
0x180072935  mov     [rsp+140h+lpdwDisposition], rax; lpdwDisposition
0x18007293a  lea     rax, [rsp+140h+hKey]
0x18007293f  mov     [rsp+140h+phkResult], rax; phkResult
0x180072944  mov     [rsp+140h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18007294d  mov     [rsp+140h+samDesired], 2001Fh; samDesired
0x180072955  mov     [rsp+140h+dwOptions], 0; dwOptions
0x18007295d  xor     r9d, r9d; lpClass
0x180072960  xor     r8d, r8d; Reserved
0x180072963  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007296a  call    cs:__imp_RegCreateKeyExW
0x180072971  nop     dword ptr [rax+rax+00h]
0x180072976  mov     ebx, eax
0x180072978  test    eax, eax
0x18007297a  jz      short loc_180072990
0x18007297c  jle     loc_180072BF1
0x180072982  movzx   ebx, ax
0x180072985  or      ebx, 80070000h
0x18007298b  jmp     loc_180072BF1
0x180072990  cmp     [rsp+140h+dwDisposition], 1
0x180072995  jnz     loc_180072A5A
0x18007299b  mov     dword ptr [rsp+140h+Data], 1
0x1800729a3  xorps   xmm0, xmm0
0x1800729a6  movups  xmmword ptr [rbp+40h+pguid.Data1], xmm0
0x1800729aa  lea     rcx, [rbp+40h+pguid]; pguid
0x1800729ae  call    cs:__imp_CoCreateGuid
0x1800729b5  nop     dword ptr [rax+rax+00h]
0x1800729ba  mov     ebx, eax
0x1800729bc  test    eax, eax
0x1800729be  js      loc_180072BF1
0x1800729c4  mov     r8d, 27h ; '''; cchMax
0x1800729ca  lea     rdx, [rbp+40h+sz]; lpsz
0x1800729ce  lea     rcx, [rbp+40h+pguid]; rguid
0x1800729d2  call    cs:__imp_StringFromGUID2
0x1800729d9  nop     dword ptr [rax+rax+00h]
0x1800729de  mov     [rsp+140h+samDesired], 4; cbData
0x1800729e6  lea     rax, [rsp+140h+Data]
0x1800729eb  mov     qword ptr [rsp+140h+dwOptions], rax; lpData
0x1800729f0  mov     r9d, 4; dwType
0x1800729f6  xor     r8d, r8d; Reserved
0x1800729f9  lea     rdx, aCount; "Count"
0x180072a00  mov     rcx, [rsp+140h+hKey]; hKey
0x180072a05  call    cs:__imp_RegSetValueExW
0x180072a0c  nop     dword ptr [rax+rax+00h]
0x180072a11  mov     ebx, eax
0x180072a13  test    eax, eax
0x180072a15  jnz     loc_180072B50
0x180072a1b  mov     [rsp+140h+samDesired], 4Eh ; 'N'; cbData
0x180072a23  lea     rax, [rbp+40h+sz]
0x180072a27  mov     qword ptr [rsp+140h+dwOptions], rax; lpData
0x180072a2c  lea     r9d, [rbx+1]; dwType
0x180072a30  xor     r8d, r8d; Reserved
0x180072a33  lea     rdx, aIndex; "Index"
0x180072a3a  mov     rcx, [rsp+140h+hKey]; hKey
0x180072a3f  call    cs:__imp_RegSetValueExW
0x180072a46  nop     dword ptr [rax+rax+00h]
0x180072a4b  mov     ebx, eax
0x180072a4d  test    eax, eax
0x180072a4f  jz      loc_180072B65
0x180072a55  jmp     loc_180072B50
0x180072a5a  mov     dword ptr [rsp+140h+Data], 0
0x180072a62  mov     dword ptr [rsp+140h+var_F0], 0
0x180072a6a  mov     [rsp+140h+cbData], 4Eh ; 'N'
0x180072a72  lea     rax, [rsp+140h+cbData]
0x180072a77  mov     qword ptr [rsp+140h+samDesired], rax; lpcbData
0x180072a7c  lea     rax, [rbp+40h+sz]
0x180072a80  mov     qword ptr [rsp+140h+dwOptions], rax; lpData
0x180072a85  lea     r9, [rsp+140h+Data]; lpType
0x180072a8a  xor     r8d, r8d; lpReserved
0x180072a8d  lea     rdx, aIndex; "Index"
0x180072a94  mov     rcx, [rsp+140h+hKey]; hKey
0x180072a99  call    cs:__imp_RegQueryValueExW
0x180072aa0  nop     dword ptr [rax+rax+00h]
0x180072aa5  mov     ebx, eax
0x180072aa7  test    eax, eax
0x180072aa9  jnz     loc_18007297C
0x180072aaf  mov     [rsp+140h+cbData], 4
0x180072ab7  lea     rax, [rsp+140h+cbData]
0x180072abc  mov     qword ptr [rsp+140h+samDesired], rax; lpcbData
0x180072ac1  lea     rax, [rsp+140h+var_F0]
0x180072ac6  mov     qword ptr [rsp+140h+dwOptions], rax; lpData
0x180072acb  lea     r9, [rsp+140h+Data]; lpType
0x180072ad0  xor     r8d, r8d; lpReserved
0x180072ad3  lea     rdx, aCount; "Count"
0x180072ada  mov     rcx, [rsp+140h+hKey]; hKey
0x180072adf  call    cs:__imp_RegQueryValueExW
0x180072ae6  nop     dword ptr [rax+rax+00h]
0x180072aeb  mov     ebx, eax
0x180072aed  test    eax, eax
0x180072aef  jnz     short loc_180072B50
0x180072af1  cmp     dword ptr [rsp+140h+Data], 4
0x180072af6  jz      short loc_180072B02
0x180072af8  mov     ebx, 80041311h
0x180072afd  jmp     loc_180072BF1
0x180072b02  mov     eax, dword ptr [rsp+140h+var_F0]
0x180072b06  cmp     eax, 0FFFFFFFFh
0x180072b09  jnz     short loc_180072B15
0x180072b0b  mov     ebx, 80070216h
0x180072b10  jmp     loc_180072BF1
0x180072b15  inc     eax
0x180072b17  mov     dword ptr [rsp+140h+var_F0], eax
0x180072b1b  mov     [rsp+140h+samDesired], 4; cbData
0x180072b23  lea     rax, [rsp+140h+var_F0]
0x180072b28  mov     qword ptr [rsp+140h+dwOptions], rax; lpData
0x180072b2d  mov     r9d, 4; dwType
0x180072b33  xor     r8d, r8d; Reserved
0x180072b36  lea     rdx, aCount; "Count"
0x180072b3d  mov     rcx, [rsp+140h+hKey]; hKey
0x180072b42  call    cs:__imp_RegSetValueExW
0x180072b49  nop     dword ptr [rax+rax+00h]
0x180072b4e  mov     ebx, eax
0x180072b50  test    ebx, ebx
0x180072b52  jle     short loc_180072B5F
0x180072b54  movzx   ebx, bx
0x180072b57  or      ebx, 80070000h
0x180072b5d  test    ebx, ebx
0x180072b5f  js      loc_180072BF1
0x180072b65  mov     ecx, 74h ; 't'; dwBytes
0x180072b6a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180072b6f  mov     rdx, rax
0x180072b72  mov     rcx, rsi
0x180072b75  call    ??4?$AutoVectorPtr@G@wmi@@QEAAAEAV01@PEAG@Z; wmi::AutoVectorPtr<ushort>::operator=(ushort *)
0x180072b7a  mov     rcx, [rsi]; unsigned __int16 *
0x180072b7d  test    rcx, rcx
0x180072b80  jnz     short loc_180072BC3
0x180072b82  mov     [rbp+40h+var_B0], cl
0x180072b85  lea     rax, qword_1800A8718
0x180072b8c  mov     [rbp+40h+var_A8], rax
0x180072b90  mov     [rbp+40h+var_A0], rcx
0x180072b94  mov     [rbp+40h+var_98], rcx
0x180072b98  mov     [rbp+40h+var_90], 0Eh
0x180072b9f  mov     [rbp+40h+var_8C], 0FFFFFFFFFFFFFFFFh
0x180072ba7  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180072bae  mov     [rbp+40h+pExceptionObject], rax
0x180072bb2  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x180072bb9  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x180072bbd  call    _CxxThrowException_0
0x180072bc3  lea     r8, aTaskschedulerT; "TaskScheduler:Task:"
0x180072bca  mov     edx, 3Ah ; ':'; unsigned __int64
0x180072bcf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180072bd4  mov     ebx, eax
0x180072bd6  test    eax, eax
0x180072bd8  js      short loc_180072BF1
0x180072bda  mov     rcx, [rsi]
0x180072bdd  add     rcx, 26h ; '&'; unsigned __int16 *
0x180072be1  lea     r8, [rbp+40h+sz]; unsigned __int16 *
0x180072be5  mov     edx, 27h ; '''; unsigned __int64
0x180072bea  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180072bef  mov     ebx, eax
0x180072bf1  mov     rcx, r14; lpCriticalSection
0x180072bf4  call    cs:__imp_LeaveCriticalSection
0x180072bfb  nop     dword ptr [rax+rax+00h]
0x180072c00  nop
0x180072c01  lea     rcx, [rsp+140h+var_C8]; this
0x180072c06  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180072c0b  nop
0x180072c0c  lea     rcx, [rsp+140h+hKey]; this
0x180072c11  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x180072c16  nop
0x180072c17  lea     rcx, [rbp+40h+var_C0]; this
0x180072c1b  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180072c20  mov     eax, ebx
0x180072c22  mov     rcx, [rbp+40h+var_20]
0x180072c26  xor     rcx, rsp; StackCookie
0x180072c29  call    __security_check_cookie
0x180072c2e  mov     rbx, [rsp+140h+arg_18]
0x180072c36  add     rsp, 130h
0x180072c3d  pop     r14
0x180072c3f  pop     rsi
0x180072c40  pop     rbp
0x180072c41  retn
```
