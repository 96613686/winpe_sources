# CredStore::ReleaseRefUserRecord(User const &,wmi::AutoVectorPtr<ushort> &)

- ea: `0x18005616c`
- end: `0x1800564ae`
- name: `?ReleaseRefUserRecord@CredStore@@AEAAJAEBVUser@@AEAV?$AutoVectorPtr@G@wmi@@@Z`
- size: `834`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, User *this)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180072c4c`

## callees

- `0x180011e40`
- `0x180027910`
- `0x18002db40`
- `0x1800301f0`
- `0x180039fd0`
- `0x18003bd70`
- `0x180041020`
- `0x1800423e0`
- `0x18005616c`
- `0x18005a2bc`
- `0x1800829fa`
- `0x180082a40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005645e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005645e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180056236`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180056236`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180056412`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180056412`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180056368`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180056368`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005626b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005626b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800562c5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180056315`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800562c5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180056315`

## string_xrefs

- `0x18005642d`: `TaskScheduler:Task:`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
            v26 = &qword_1800A8718;
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
0x18005616c  mov     [rsp-8+arg_18], rbx
0x180056171  push    rbp
0x180056172  push    rsi
0x180056173  push    rdi
0x180056174  push    r12
0x180056176  push    r14
0x180056178  lea     rbp, [rsp-37h]
0x18005617d  sub     rsp, 0F0h
0x180056184  mov     rax, cs:__security_cookie
0x18005618b  xor     rax, rsp
0x18005618e  mov     [rbp+57h+var_30], rax
0x180056192  mov     rsi, r8
0x180056195  mov     rbx, rdx
0x180056198  mov     r14, rcx
0x18005619b  mov     [rbp+57h+var_C0], 0
0x1800561a3  xor     eax, eax
0x1800561a5  mov     word ptr [rbp+57h+Data], ax
0x1800561a9  xor     edx, edx; Val
0x1800561ab  lea     r8d, [rax+4Eh]; Size
0x1800561af  lea     rcx, [rbp+57h+var_7E]; void *
0x1800561b3  call    memset_0
0x1800561b8  mov     dword ptr [rsp+110h+var_E0], 0
0x1800561c0  lea     rdx, [rbp+57h+var_C0]; struct _bstr_t *
0x1800561c4  mov     rcx, rbx; this
0x1800561c7  call    ?GetSidString@User@@QEBAJAEAV_bstr_t@@@Z; User::GetSidString(_bstr_t &)
0x1800561cc  mov     ebx, eax
0x1800561ce  test    eax, eax
0x1800561d0  jns     short loc_1800561E2
0x1800561d2  lea     rcx, [rbp+57h+var_C0]; this
0x1800561d6  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800561db  mov     eax, ebx
0x1800561dd  jmp     loc_18005648A
0x1800561e2  mov     [rbp+57h+hKey], 0
0x1800561ea  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800561f1  lea     rcx, [rbp+57h+var_C8]; this
0x1800561f5  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800561fa  nop
0x1800561fb  lea     rdx, asc_1800A7EC0; "\\"
0x180056202  lea     rcx, [rsp+110h+Type]; this
0x180056207  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18005620c  nop
0x18005620d  lea     rdx, [rsp+110h+Type]
0x180056212  lea     rcx, [rbp+57h+var_C8]
0x180056216  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x18005621b  nop
0x18005621c  lea     rcx, [rsp+110h+Type]; this
0x180056221  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180056226  lea     rdx, [rbp+57h+var_C0]
0x18005622a  lea     rcx, [rbp+57h+var_C8]
0x18005622e  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x180056233  mov     rcx, r14; lpCriticalSection
0x180056236  call    cs:__imp_EnterCriticalSection
0x18005623d  nop     dword ptr [rax+rax+00h]
0x180056242  mov     rbx, [rbp+57h+var_C8]
0x180056246  test    rbx, rbx
0x180056249  jz      short loc_180056250
0x18005624b  mov     rdx, [rbx]
0x18005624e  jmp     short loc_180056252
0x180056250  xor     edx, edx; lpSubKey
0x180056252  lea     rax, [rbp+57h+hKey]
0x180056256  mov     [rsp+110h+phkResult], rax; phkResult
0x18005625b  mov     r9d, 0F003Fh; samDesired
0x180056261  xor     r8d, r8d; ulOptions
0x180056264  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005626b  call    cs:__imp_RegOpenKeyExW
0x180056272  nop     dword ptr [rax+rax+00h]
0x180056277  mov     r12d, 80070000h
0x18005627d  test    eax, eax
0x18005627f  jg      short loc_180056285
0x180056281  mov     edi, eax
0x180056283  jmp     short loc_18005628B
0x180056285  movzx   edi, ax
0x180056288  or      edi, r12d
0x18005628b  test    eax, eax
0x18005628d  jnz     loc_180056382
0x180056293  mov     [rsp+110h+Type], eax
0x180056297  mov     [rsp+110h+cbData], 4Eh ; 'N'
0x18005629f  lea     rax, [rsp+110h+cbData]
0x1800562a4  mov     [rsp+110h+lpcbData], rax; lpcbData
0x1800562a9  lea     rax, [rbp+57h+Data]
0x1800562ad  mov     [rsp+110h+phkResult], rax; lpData
0x1800562b2  lea     r9, [rsp+110h+Type]; lpType
0x1800562b7  xor     r8d, r8d; lpReserved
0x1800562ba  lea     rdx, aIndex; "Index"
0x1800562c1  mov     rcx, [rbp+57h+hKey]; hKey
0x1800562c5  call    cs:__imp_RegQueryValueExW
0x1800562cc  nop     dword ptr [rax+rax+00h]
0x1800562d1  test    eax, eax
0x1800562d3  jz      short loc_1800562E6
0x1800562d5  jle     loc_180056459
0x1800562db  movzx   edi, ax
0x1800562de  or      edi, r12d
0x1800562e1  jmp     loc_18005645B
0x1800562e6  mov     [rsp+110h+cbData], 4
0x1800562ee  lea     rax, [rsp+110h+cbData]
0x1800562f3  mov     [rsp+110h+lpcbData], rax; lpcbData
0x1800562f8  lea     rax, [rsp+110h+var_E0]
0x1800562fd  mov     [rsp+110h+phkResult], rax; lpData
0x180056302  lea     r9, [rsp+110h+Type]; lpType
0x180056307  xor     r8d, r8d; lpReserved
0x18005630a  lea     rdx, aCount; "Count"
0x180056311  mov     rcx, [rbp+57h+hKey]; hKey
0x180056315  call    cs:__imp_RegQueryValueExW
0x18005631c  nop     dword ptr [rax+rax+00h]
0x180056321  test    eax, eax
0x180056323  jnz     short loc_180056382
0x180056325  cmp     [rsp+110h+Type], 4
0x18005632a  jz      short loc_180056336
0x18005632c  mov     edi, 80041311h
0x180056331  jmp     loc_18005645B
0x180056336  mov     eax, dword ptr [rsp+110h+var_E0]
0x18005633a  test    eax, eax
0x18005633c  jz      short loc_18005634C
0x18005633e  dec     eax
0x180056340  mov     dword ptr [rsp+110h+var_E0], eax
0x180056344  test    eax, eax
0x180056346  jnz     loc_1800563EC
0x18005634c  lea     rcx, [rbp+57h+hKey]; this
0x180056350  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x180056355  test    rbx, rbx
0x180056358  jz      short loc_18005635F
0x18005635a  mov     rdx, [rbx]
0x18005635d  jmp     short loc_180056361
0x18005635f  xor     edx, edx; lpSubKey
0x180056361  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180056368  call    cs:__imp_RegDeleteTreeW
0x18005636f  nop     dword ptr [rax+rax+00h]
0x180056374  mov     edi, eax
0x180056376  test    eax, eax
0x180056378  jz      short loc_18005638A
0x18005637a  jle     short loc_180056382
0x18005637c  movzx   edi, ax
0x18005637f  or      edi, r12d
0x180056382  test    edi, edi
0x180056384  jnz     loc_18005645B
0x18005638a  mov     ecx, 74h ; 't'; dwBytes
0x18005638f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180056394  mov     rdx, rax
0x180056397  mov     rcx, rsi
0x18005639a  call    ??4?$AutoVectorPtr@G@wmi@@QEAAAEAV01@PEAG@Z; wmi::AutoVectorPtr<ushort>::operator=(ushort *)
0x18005639f  mov     rcx, [rsi]; unsigned __int16 *
0x1800563a2  test    rcx, rcx
0x1800563a5  jnz     loc_18005642D
0x1800563ab  mov     [rbp+57h+var_B0], cl
0x1800563ae  lea     rax, qword_1800A8718
0x1800563b5  mov     [rbp+57h+var_A8], rax
0x1800563b9  mov     [rbp+57h+var_A0], rcx
0x1800563bd  mov     [rbp+57h+var_98], rcx
0x1800563c1  mov     [rbp+57h+var_90], 0Eh
0x1800563c8  mov     [rbp+57h+var_8C], 0FFFFFFFFFFFFFFFFh
0x1800563d0  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800563d7  mov     [rbp+57h+pExceptionObject], rax
0x1800563db  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x1800563e2  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800563e6  call    _CxxThrowException_0
0x1800563ec  mov     dword ptr [rsp+110h+lpcbData], 4; cbData
0x1800563f4  lea     rax, [rsp+110h+var_E0]
0x1800563f9  mov     [rsp+110h+phkResult], rax; lpData
0x1800563fe  mov     r9d, 4; dwType
0x180056404  xor     r8d, r8d; Reserved
0x180056407  lea     rdx, aCount; "Count"
0x18005640e  mov     rcx, [rbp+57h+hKey]; hKey
0x180056412  call    cs:__imp_RegSetValueExW
0x180056419  nop     dword ptr [rax+rax+00h]
0x18005641e  mov     edi, eax
0x180056420  test    eax, eax
0x180056422  jnz     loc_18005637A
0x180056428  lea     edi, [rax+1]
0x18005642b  jmp     short loc_18005645B
0x18005642d  lea     r8, aTaskschedulerT; "TaskScheduler:Task:"
0x180056434  mov     edx, 3Ah ; ':'; unsigned __int64
0x180056439  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005643e  mov     edi, eax
0x180056440  test    eax, eax
0x180056442  js      short loc_18005645B
0x180056444  mov     rcx, [rsi]
0x180056447  add     rcx, 26h ; '&'; unsigned __int16 *
0x18005644b  lea     r8, [rbp+57h+Data]; unsigned __int16 *
0x18005644f  mov     edx, 27h ; '''; unsigned __int64
0x180056454  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180056459  mov     edi, eax
0x18005645b  mov     rcx, r14; lpCriticalSection
0x18005645e  call    cs:__imp_LeaveCriticalSection
0x180056465  nop     dword ptr [rax+rax+00h]
0x18005646a  nop
0x18005646b  lea     rcx, [rbp+57h+var_C8]; this
0x18005646f  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180056474  nop
0x180056475  lea     rcx, [rbp+57h+hKey]; this
0x180056479  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x18005647e  nop
0x18005647f  lea     rcx, [rbp+57h+var_C0]; this
0x180056483  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180056488  mov     eax, edi
0x18005648a  mov     rcx, [rbp+57h+var_30]
0x18005648e  xor     rcx, rsp; StackCookie
0x180056491  call    __security_check_cookie
0x180056496  mov     rbx, [rsp+110h+arg_18]
0x18005649e  add     rsp, 0F0h
0x1800564a5  pop     r14
0x1800564a7  pop     r12
0x1800564a9  pop     rdi
0x1800564aa  pop     rsi
0x1800564ab  pop     rbp
0x1800564ac  retn
```
