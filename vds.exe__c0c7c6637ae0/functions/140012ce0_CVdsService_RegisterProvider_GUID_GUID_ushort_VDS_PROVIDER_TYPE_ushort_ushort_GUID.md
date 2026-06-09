# CVdsService::RegisterProvider(_GUID,_GUID,ushort *,_VDS_PROVIDER_TYPE,ushort *,ushort *,_GUID)

- ea: `0x140012ce0`
- end: `0x140013291`
- name: `?RegisterProvider@CVdsService@@UEAAJU_GUID@@0PEAGW4_VDS_PROVIDER_TYPE@@110@Z`
- size: `1457`
- prototype: `int(CVdsService *__hidden this, struct _GUID *__struct_ptr, struct _GUID *__struct_ptr, unsigned __int16 *, enum _VDS_PROVIDER_TYPE, unsigned __int16 *, unsigned __int16 *, struct _GUID *__struct_ptr)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x140012ce0`
- `0x140013298`
- `0x140052e46`
- `0x140052e80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400131d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140013208`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400131d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140013208`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140012e25`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140012e25`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140012f2f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140012fd9`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140013104`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140012f2f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140012fd9`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140013104`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400131a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400131b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400131c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400131e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400131ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400131fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400131a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400131b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400131c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400131e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400131ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400131fa`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x140013199`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x140013199`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140012e4d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140012e4d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001300f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001306f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400130ca`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001313a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001300f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001306f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400130ca`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001313a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140012eef`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140012f6a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140012eef`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140012f6a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140012db7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140012dde`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140012fe3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140013042`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1400130a2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14001310e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140012db7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140012dde`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140012fe3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140013042`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1400130a2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14001310e`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140012d42`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140012d42`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140013241`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001325f`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140013241`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001325f`
- `vdsutil!VdsTraceW` at `0x140012d69`
- `vdsutil!VdsTraceW` at `0x140012d9b`
- `vdsutil!VdsTraceW` at `0x140012e0e`
- `vdsutil!VdsTraceW` at `0x140012e65`
- `vdsutil!VdsTraceW` at `0x140012f07`
- `vdsutil!VdsTraceW` at `0x140012f82`
- `vdsutil!VdsTraceW` at `0x140012fb7`
- `vdsutil!VdsTraceW` at `0x140013027`
- `vdsutil!VdsTraceW` at `0x140013087`
- `vdsutil!VdsTraceW` at `0x1400130e2`
- `vdsutil!VdsTraceW` at `0x140013156`
- `vdsutil!VdsTraceW` at `0x14001321c`
- `vdsutil!VdsTraceW` at `0x140013232`
- `vdsutil!VdsTraceW` at `0x140013254`
- `vdsutil!VdsTraceW` at `0x140012d69`
- `vdsutil!VdsTraceW` at `0x140012d9b`
- `vdsutil!VdsTraceW` at `0x140012e0e`
- `vdsutil!VdsTraceW` at `0x140012e65`
- `vdsutil!VdsTraceW` at `0x140012f07`
- `vdsutil!VdsTraceW` at `0x140012f82`
- `vdsutil!VdsTraceW` at `0x140012fb7`
- `vdsutil!VdsTraceW` at `0x140013027`
- `vdsutil!VdsTraceW` at `0x140013087`
- `vdsutil!VdsTraceW` at `0x1400130e2`
- `vdsutil!VdsTraceW` at `0x140013156`
- `vdsutil!VdsTraceW` at `0x14001321c`
- `vdsutil!VdsTraceW` at `0x140013232`
- `vdsutil!VdsTraceW` at `0x140013254`

## string_xrefs

- `0x140012d34`: `CVdsService::RegisterProvider()`
- `0x140012f79`: `CVdsService::RegisterProvider, 9, error=%ld`
- `0x14001314d`: `CVdsService::RegisterProvider, 14, error=%ld`
- `0x14001307e`: `CVdsService::RegisterProvider, 12, error=%ld`
- `0x140012e5c`: `CVdsService::RegisterProvider, 7, error=%ld`
- `0x1400130d9`: `CVdsService::RegisterProvider, 13, error=%ld`
- `0x14001301e`: `CVdsService::RegisterProvider, 11, error=%ld`
- `0x140012efe`: `CVdsService::RegisterProvider, 8, error=%ld`
- `0x140012d60`: `CVdsService::RegisterProvider, 1`
- `0x140012d92`: `CVdsService::RegisterProvider, 2`
- `0x14001324b`: `CVdsService::RegisterProvider, 3`
- `0x140013229`: `CVdsService::RegisterProvider, 4`
- `0x140013213`: `CVdsService::RegisterProvider, 5`
- `0x140012e05`: `CVdsService::RegisterProvider, 6`
- `0x140012fae`: `CVdsService::RegisterProvider, 10`
- `0x140013003`: `Clsid`
- `0x140012e3f`: `System\CurrentControlSet\Services\vds`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVdsService::RegisterProvider(
        CVdsService *this,
        struct _GUID *a2,
        struct _GUID *a3,
        unsigned __int16 *a4,
        enum _VDS_PROVIDER_TYPE a5,
        unsigned __int16 *a6,
        unsigned __int16 *lpString,
        struct _GUID *Buf1)
{
  int v11; // ebx
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  int v15; // r14d
  int v16; // eax
  unsigned int v17; // eax
  int v18; // eax
  unsigned int v19; // eax
  int v20; // eax
  unsigned int v21; // eax
  int v22; // eax
  unsigned int v23; // eax
  HKEY v25; // [rsp+50h] [rbp-99h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-91h] BYREF
  HKEY v27; // [rsp+60h] [rbp-89h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-81h] BYREF
  _BYTE v29[16]; // [rsp+70h] [rbp-79h] BYREF
  OLECHAR sz[52]; // [rsp+80h] [rbp-69h] BYREF

  v27 = 0;
  v25 = 0;
  hKey = 0;
  dwDisposition = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v29, 0x5Eu, "CVdsService::RegisterProvider()");
  if ( !memcmp_0(a2, &GUID_NULL, 0x10u) )
  {
    VdsTraceW(0, L"CVdsService::RegisterProvider, 1");
    v11 = -2147211929;
LABEL_48:
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v29);
    return (unsigned int)v11;
  }
  if ( !memcmp_0(a3, &GUID_NULL, 0x10u) )
  {
    VdsTraceW(0, L"CVdsService::RegisterProvider, 2");
    v11 = -2147211930;
    goto LABEL_48;
  }
  if ( a4 && lstrlenW(a4) )
  {
    if ( (unsigned int)(a5 - 1) > 2 )
    {
      VdsTraceW(0, L"CVdsService::RegisterProvider, 4");
      v11 = -2147211927;
      goto LABEL_48;
    }
    if ( !lpString || !lstrlenW(lpString) )
    {
      VdsTraceW(0, L"CVdsService::RegisterProvider, 5");
      v11 = -2147211925;
      goto LABEL_48;
    }
    if ( !memcmp_0(Buf1, &GUID_NULL, 0x10u) )
    {
      VdsTraceW(0, L"CVdsService::RegisterProvider, 6");
      v11 = -2147211926;
      goto LABEL_48;
    }
    EnterCriticalSection(&g_GlobalCriticalSection);
    v12 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, g_wszVdsKey, 0, 0xF003Fu, &hKey);
    v11 = v12;
    if ( v12 )
    {
      VdsTraceW(0, L"CVdsService::RegisterProvider, 7, error=%ld", v12);
      VdsLogError(0xC2000001, 0, 0, v11, 0x2000024u, 0);
      goto LABEL_14;
    }
    v13 = RegCreateKeyExW(hKey, (LPCWSTR)&(&g_wszVdsProviderKeys)[25 * a5], 0, 0, 0, 0xF003Fu, 0, &v27, &dwDisposition);
    v11 = v13;
    if ( v13 )
    {
      VdsTraceW(0, L"CVdsService::RegisterProvider, 8, error=%ld", v13);
      VdsLogError(0xC2000001, 0, 0, v11, 0x2000025u, 0);
      goto LABEL_14;
    }
    StringFromGUID2(a2, sz, 45);
    v14 = RegCreateKeyExW(v27, sz, 0, 0, 0, 0xF003Fu, 0, &v25, &dwDisposition);
    v11 = v14;
    if ( v14 )
    {
      VdsTraceW(0, L"CVdsService::RegisterProvider, 9, error=%ld", v14);
      VdsLogError(0xC2000001, 0, 0, v11, 0x2000028u, 0);
LABEL_14:
      if ( v11 > 0 )
        v11 = (unsigned __int16)v11 | 0x80070000;
      goto LABEL_38;
    }
    if ( dwDisposition == 1 )
    {
      v15 = 1;
    }
    else
    {
      if ( dwDisposition == 2 )
      {
        v11 = -2147212285;
        goto LABEL_38;
      }
      v15 = 0;
      VdsTraceW(0, L"CVdsService::RegisterProvider, 10");
    }
    StringFromGUID2(a3, sz, 45);
    v16 = lstrlenW(sz);
    v17 = RegSetValueExW(v25, g_wszVdsProviderClassId, 0, 1u, (const BYTE *)sz, 2 * v16 + 2);
    v11 = v17;
    if ( v17 )
    {
      VdsTraceW(0, L"CVdsService::RegisterProvider, 11, error=%ld", v17);
      VdsLogError(0xC2000001, 0, 0, v11, 0x2000029u, 0);
    }
    else
    {
      v18 = lstrlenW(a4);
      v19 = RegSetValueExW(v25, &g_wszVdsProviderValueName, 0, 1u, (const BYTE *)a4, 2 * v18 + 2);
      v11 = v19;
      if ( v19 )
      {
        VdsTraceW(0, L"CVdsService::RegisterProvider, 12, error=%ld", v19);
        VdsLogError(0xC2000001, 0, 0, v11, 0x200002Au, 0);
      }
      else
      {
        v20 = lstrlenW(lpString);
        v21 = RegSetValueExW(v25, g_wszVdsProviderValueVersion, 0, 1u, (const BYTE *)lpString, 2 * v20 + 2);
        v11 = v21;
        if ( v21 )
        {
          VdsTraceW(0, L"CVdsService::RegisterProvider, 13, error=%ld", v21);
          VdsLogError(0xC2000001, 0, 0, v11, 0x200002Bu, 0);
        }
        else
        {
          StringFromGUID2(Buf1, sz, 45);
          v22 = lstrlenW(sz);
          v23 = RegSetValueExW(v25, g_wszVdsProviderValueVersionId, 0, 1u, (const BYTE *)sz, 2 * v22 + 2);
          v11 = v23;
          if ( !v23 )
          {
            RegCloseKey(v25);
            RegCloseKey(v27);
            RegCloseKey(hKey);
            LeaveCriticalSection(&g_GlobalCriticalSection);
            v11 = 0;
            goto LABEL_48;
          }
          VdsTraceW(0, L"CVdsService::RegisterProvider, 14, error=%ld", v23);
          VdsLogError(0xC2000001, 0, 0, v11, 0x200002Cu, 0);
        }
      }
    }
    if ( v11 > 0 )
      v11 = (unsigned __int16)v11 | 0x80070000;
    if ( v15 )
    {
      if ( !v25 )
      {
LABEL_40:
        if ( v27 )
          RegCloseKey(v27);
        if ( hKey )
          RegCloseKey(hKey);
        LeaveCriticalSection(&g_GlobalCriticalSection);
        goto LABEL_48;
      }
      RegDeleteTreeW(v25, 0);
    }
LABEL_38:
    if ( v25 )
      RegCloseKey(v25);
    goto LABEL_40;
  }
  VdsTraceW(0, L"CVdsService::RegisterProvider, 3");
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v29);
  return 2147755368LL;
}

```

## disassembly

```asm
0x140012ce0  mov     [rsp-8+arg_0], rbx
0x140012ce5  push    rbp
0x140012ce6  push    rsi
0x140012ce7  push    rdi
0x140012ce8  push    r12
0x140012cea  push    r13
0x140012cec  push    r14
0x140012cee  push    r15
0x140012cf0  lea     rbp, [rsp-7]
0x140012cf5  sub     rsp, 0F0h
0x140012cfc  mov     rax, cs:__security_cookie
0x140012d03  xor     rax, rsp
0x140012d06  mov     [rbp+37h+var_38], rax
0x140012d0a  mov     rdi, r9
0x140012d0d  mov     r15, r8
0x140012d10  mov     r12, rdx
0x140012d13  movsxd  r14, [rbp+37h+arg_20]
0x140012d17  mov     rsi, [rbp+37h+lpString]
0x140012d1b  mov     r13, [rbp+37h+Buf1]
0x140012d1f  xor     ebx, ebx
0x140012d21  mov     [rsp+120h+var_C0], rbx
0x140012d26  mov     [rsp+120h+var_D0], rbx
0x140012d2b  mov     [rsp+120h+hKey], rbx
0x140012d30  mov     [rsp+120h+dwDisposition], ebx
0x140012d34  lea     r8, aCvdsserviceReg_0; "CVdsService::RegisterProvider()"
0x140012d3b  lea     edx, [rbx+5Eh]
0x140012d3e  lea     rcx, [rbp+37h+var_B0]
0x140012d42  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140012d48  nop
0x140012d49  lea     r8d, [rbx+10h]; Size
0x140012d4d  lea     rdx, GUID_NULL; Buf2
0x140012d54  mov     rcx, r12; Buf1
0x140012d57  call    memcmp_0
0x140012d5c  test    eax, eax
0x140012d5e  jnz     short loc_140012D79
0x140012d60  lea     rdx, aCvdsserviceReg_11; "CVdsService::RegisterProvider, 1"
0x140012d67  xor     ecx, ecx
0x140012d69  call    cs:__imp_VdsTraceW
0x140012d6f  mov     ebx, 80042567h
0x140012d74  jmp     loc_14001323D
0x140012d79  mov     r8d, 10h; Size
0x140012d7f  lea     rdx, GUID_NULL; Buf2
0x140012d86  mov     rcx, r15; Buf1
0x140012d89  call    memcmp_0
0x140012d8e  test    eax, eax
0x140012d90  jnz     short loc_140012DAB
0x140012d92  lea     rdx, aCvdsserviceReg; "CVdsService::RegisterProvider, 2"
0x140012d99  xor     ecx, ecx
0x140012d9b  call    cs:__imp_VdsTraceW
0x140012da1  mov     ebx, 80042566h
0x140012da6  jmp     loc_14001323D
0x140012dab  test    rdi, rdi
0x140012dae  jz      loc_14001324B
0x140012db4  mov     rcx, rdi; lpString
0x140012db7  call    cs:__imp_lstrlenW
0x140012dbd  test    eax, eax
0x140012dbf  jz      loc_14001324B
0x140012dc5  lea     eax, [r14-1]
0x140012dc9  cmp     eax, 2
0x140012dcc  ja      loc_140013229
0x140012dd2  test    rsi, rsi
0x140012dd5  jz      loc_140013213
0x140012ddb  mov     rcx, rsi; lpString
0x140012dde  call    cs:__imp_lstrlenW
0x140012de4  test    eax, eax
0x140012de6  jz      loc_140013213
0x140012dec  mov     r8d, 10h; Size
0x140012df2  lea     rdx, GUID_NULL; Buf2
0x140012df9  mov     rcx, r13; Buf1
0x140012dfc  call    memcmp_0
0x140012e01  test    eax, eax
0x140012e03  jnz     short loc_140012E1E
0x140012e05  lea     rdx, aCvdsserviceReg_8; "CVdsService::RegisterProvider, 6"
0x140012e0c  xor     ecx, ecx
0x140012e0e  call    cs:__imp_VdsTraceW
0x140012e14  mov     ebx, 8004256Ah
0x140012e19  jmp     loc_14001323D
0x140012e1e  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140012e25  call    cs:__imp_EnterCriticalSection
0x140012e2b  nop
0x140012e2c  lea     rax, [rsp+120h+hKey]
0x140012e31  mov     [rsp+120h+phkResult], rax; phkResult
0x140012e36  mov     r9d, 0F003Fh; samDesired
0x140012e3c  xor     r8d, r8d; ulOptions
0x140012e3f  lea     rdx, ?g_wszVdsKey@@3PAGA; "System\\CurrentControlSet\\Services\\vd"...
0x140012e46  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140012e4d  call    cs:__imp_RegOpenKeyExW
0x140012e53  mov     ebx, eax
0x140012e55  test    eax, eax
0x140012e57  jz      short loc_140012EA3
0x140012e59  mov     r8d, eax
0x140012e5c  lea     rdx, aCvdsserviceReg_10; "CVdsService::RegisterProvider, 7, error"...
0x140012e63  xor     ecx, ecx
0x140012e65  call    cs:__imp_VdsTraceW
0x140012e6b  xor     r12d, r12d
0x140012e6e  mov     qword ptr [rsp+120h+samDesired], r12; unsigned __int16 *
0x140012e73  mov     dword ptr [rsp+120h+phkResult], 2000024h; unsigned int
0x140012e7b  mov     r9d, ebx; unsigned int
0x140012e7e  xor     r8d, r8d; void *
0x140012e81  xor     edx, edx; unsigned int
0x140012e83  mov     ecx, 0C2000001h; unsigned int
0x140012e88  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x140012e8d  test    ebx, ebx
0x140012e8f  jle     loc_14001319F
0x140012e95  movzx   ebx, bx
0x140012e98  or      ebx, 80070000h
0x140012e9e  jmp     loc_14001319F
0x140012ea3  imul    rdx, r14, 0C8h
0x140012eaa  lea     rax, ?g_wszVdsProviderKeys@@3PAY0GE@GA; "Uknown"
0x140012eb1  add     rdx, rax; lpSubKey
0x140012eb4  lea     rax, [rsp+120h+dwDisposition]
0x140012eb9  mov     [rsp+120h+lpdwDisposition], rax; lpdwDisposition
0x140012ebe  lea     rax, [rsp+120h+var_C0]
0x140012ec3  mov     [rsp+120h+var_E8], rax; phkResult
0x140012ec8  mov     [rsp+120h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140012ed1  mov     r14d, 0F003Fh
0x140012ed7  mov     [rsp+120h+samDesired], r14d; samDesired
0x140012edc  mov     dword ptr [rsp+120h+phkResult], 0; dwOptions
0x140012ee4  xor     r9d, r9d; lpClass
0x140012ee7  xor     r8d, r8d; Reserved
0x140012eea  mov     rcx, [rsp+120h+hKey]; hKey
0x140012eef  call    cs:__imp_RegCreateKeyExW
0x140012ef5  mov     ebx, eax
0x140012ef7  test    eax, eax
0x140012ef9  jz      short loc_140012F22
0x140012efb  mov     r8d, eax
0x140012efe  lea     rdx, aCvdsserviceReg_3; "CVdsService::RegisterProvider, 8, error"...
0x140012f05  xor     ecx, ecx
0x140012f07  call    cs:__imp_VdsTraceW
0x140012f0d  xor     r12d, r12d
0x140012f10  mov     qword ptr [rsp+120h+samDesired], r12
0x140012f15  mov     dword ptr [rsp+120h+phkResult], 2000025h
0x140012f1d  jmp     loc_140012E7B
0x140012f22  mov     r8d, 2Dh ; '-'; cchMax
0x140012f28  lea     rdx, [rbp+37h+sz]; lpsz
0x140012f2c  mov     rcx, r12; rguid
0x140012f2f  call    cs:__imp_StringFromGUID2
0x140012f35  lea     rax, [rsp+120h+dwDisposition]
0x140012f3a  mov     [rsp+120h+lpdwDisposition], rax; lpdwDisposition
0x140012f3f  lea     rax, [rsp+120h+var_D0]
0x140012f44  mov     [rsp+120h+var_E8], rax; phkResult
0x140012f49  xor     r12d, r12d
0x140012f4c  mov     [rsp+120h+lpSecurityAttributes], r12; lpSecurityAttributes
0x140012f51  mov     [rsp+120h+samDesired], r14d; samDesired
0x140012f56  mov     dword ptr [rsp+120h+phkResult], r12d; dwOptions
0x140012f5b  xor     r9d, r9d; lpClass
0x140012f5e  xor     r8d, r8d; Reserved
0x140012f61  lea     rdx, [rbp+37h+sz]; lpSubKey
0x140012f65  mov     rcx, [rsp+120h+var_C0]; hKey
0x140012f6a  call    cs:__imp_RegCreateKeyExW
0x140012f70  mov     ebx, eax
0x140012f72  test    eax, eax
0x140012f74  jz      short loc_140012F9A
0x140012f76  mov     r8d, eax
0x140012f79  lea     rdx, aCvdsserviceReg_5; "CVdsService::RegisterProvider, 9, error"...
0x140012f80  xor     ecx, ecx
0x140012f82  call    cs:__imp_VdsTraceW
0x140012f88  mov     qword ptr [rsp+120h+samDesired], r12
0x140012f8d  mov     dword ptr [rsp+120h+phkResult], 2000028h
0x140012f95  jmp     loc_140012E7B
0x140012f9a  mov     eax, [rsp+120h+dwDisposition]
0x140012f9e  mov     ebx, 1
0x140012fa3  sub     eax, ebx
0x140012fa5  jz      short loc_140012FC9
0x140012fa7  cmp     eax, ebx
0x140012fa9  jz      short loc_140012FBF
0x140012fab  mov     r14d, r12d
0x140012fae  lea     rdx, aCvdsserviceReg_12; "CVdsService::RegisterProvider, 10"
0x140012fb5  xor     ecx, ecx
0x140012fb7  call    cs:__imp_VdsTraceW
0x140012fbd  jmp     short loc_140012FCC
0x140012fbf  mov     ebx, 80042403h
0x140012fc4  jmp     loc_14001319F
0x140012fc9  mov     r14d, ebx
0x140012fcc  mov     r8d, 2Dh ; '-'; cchMax
0x140012fd2  lea     rdx, [rbp+37h+sz]; lpsz
0x140012fd6  mov     rcx, r15; rguid
0x140012fd9  call    cs:__imp_StringFromGUID2
0x140012fdf  lea     rcx, [rbp+37h+sz]; lpString
0x140012fe3  call    cs:__imp_lstrlenW
0x140012fe9  lea     eax, ds:2[rax*2]
0x140012ff0  mov     [rsp+120h+samDesired], eax; cbData
0x140012ff4  lea     rax, [rbp+37h+sz]
0x140012ff8  mov     [rsp+120h+phkResult], rax; lpData
0x140012ffd  mov     r9d, ebx; dwType
0x140013000  xor     r8d, r8d; Reserved
0x140013003  lea     rdx, ?g_wszVdsProviderClassId@@3PAGA; "Clsid"
0x14001300a  mov     rcx, [rsp+120h+var_D0]; hKey
0x14001300f  call    cs:__imp_RegSetValueExW
0x140013015  mov     ebx, eax
0x140013017  test    eax, eax
0x140013019  jz      short loc_14001303F
0x14001301b  mov     r8d, eax
0x14001301e  lea     rdx, aCvdsserviceReg_2; "CVdsService::RegisterProvider, 11, erro"...
0x140013025  xor     ecx, ecx
0x140013027  call    cs:__imp_VdsTraceW
0x14001302d  mov     qword ptr [rsp+120h+samDesired], r12
0x140013032  mov     dword ptr [rsp+120h+phkResult], 2000029h
0x14001303a  jmp     loc_140013169
0x14001303f  mov     rcx, rdi; lpString
0x140013042  call    cs:__imp_lstrlenW
0x140013048  lea     eax, ds:2[rax*2]
0x14001304f  mov     [rsp+120h+samDesired], eax; cbData
0x140013053  mov     [rsp+120h+phkResult], rdi; lpData
0x140013058  mov     edi, 1
0x14001305d  mov     r9d, edi; dwType
0x140013060  xor     r8d, r8d; Reserved
0x140013063  lea     rdx, ?g_wszVdsProviderValueName@@3PAGA; lpValueName
0x14001306a  mov     rcx, [rsp+120h+var_D0]; hKey
0x14001306f  call    cs:__imp_RegSetValueExW
0x140013075  mov     ebx, eax
0x140013077  test    eax, eax
0x140013079  jz      short loc_14001309F
0x14001307b  mov     r8d, eax
0x14001307e  lea     rdx, aCvdsserviceReg_6; "CVdsService::RegisterProvider, 12, erro"...
0x140013085  xor     ecx, ecx
0x140013087  call    cs:__imp_VdsTraceW
0x14001308d  mov     qword ptr [rsp+120h+samDesired], r12
0x140013092  mov     dword ptr [rsp+120h+phkResult], 200002Ah
0x14001309a  jmp     loc_140013169
0x14001309f  mov     rcx, rsi; lpString
0x1400130a2  call    cs:__imp_lstrlenW
0x1400130a8  lea     eax, ds:2[rax*2]
0x1400130af  mov     [rsp+120h+samDesired], eax; cbData
0x1400130b3  mov     [rsp+120h+phkResult], rsi; lpData
0x1400130b8  mov     r9d, edi; dwType
0x1400130bb  xor     r8d, r8d; Reserved
0x1400130be  lea     rdx, ?g_wszVdsProviderValueVersion@@3PAGA; "Version"
0x1400130c5  mov     rcx, [rsp+120h+var_D0]; hKey
0x1400130ca  call    cs:__imp_RegSetValueExW
0x1400130d0  mov     ebx, eax
0x1400130d2  test    eax, eax
0x1400130d4  jz      short loc_1400130F7
0x1400130d6  mov     r8d, eax
0x1400130d9  lea     rdx, aCvdsserviceReg_7; "CVdsService::RegisterProvider, 13, erro"...
0x1400130e0  xor     ecx, ecx
0x1400130e2  call    cs:__imp_VdsTraceW
0x1400130e8  mov     qword ptr [rsp+120h+samDesired], r12
0x1400130ed  mov     dword ptr [rsp+120h+phkResult], 200002Bh
0x1400130f5  jmp     short loc_140013169
0x1400130f7  mov     r8d, 2Dh ; '-'; cchMax
0x1400130fd  lea     rdx, [rbp+37h+sz]; lpsz
0x140013101  mov     rcx, r13; rguid
0x140013104  call    cs:__imp_StringFromGUID2
0x14001310a  lea     rcx, [rbp+37h+sz]; lpString
0x14001310e  call    cs:__imp_lstrlenW
0x140013114  lea     eax, ds:2[rax*2]
0x14001311b  mov     [rsp+120h+samDesired], eax; cbData
0x14001311f  lea     rax, [rbp+37h+sz]
0x140013123  mov     [rsp+120h+phkResult], rax; lpData
0x140013128  mov     r9d, edi; dwType
0x14001312b  xor     r8d, r8d; Reserved
0x14001312e  lea     rdx, ?g_wszVdsProviderValueVersionId@@3PAGA; "VersionId"
0x140013135  mov     rcx, [rsp+120h+var_D0]; hKey
0x14001313a  call    cs:__imp_RegSetValueExW
0x140013140  mov     ebx, eax
0x140013142  test    eax, eax
0x140013144  jz      loc_1400131DF
0x14001314a  mov     r8d, eax
0x14001314d  lea     rdx, aCvdsserviceReg_1; "CVdsService::RegisterProvider, 14, erro"...
0x140013154  xor     ecx, ecx
0x140013156  call    cs:__imp_VdsTraceW
0x14001315c  mov     qword ptr [rsp+120h+samDesired], r12; unsigned __int16 *
0x140013161  mov     dword ptr [rsp+120h+phkResult], 200002Ch; unsigned int
0x140013169  mov     r9d, ebx; unsigned int
0x14001316c  xor     r8d, r8d; void *
0x14001316f  xor     edx, edx; unsigned int
0x140013171  mov     ecx, 0C2000001h; unsigned int
0x140013176  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x14001317b  test    ebx, ebx
0x14001317d  jle     short loc_140013188
0x14001317f  movzx   ebx, bx
0x140013182  or      ebx, 80070000h
0x140013188  test    r14d, r14d
0x14001318b  jz      short loc_14001319F
0x14001318d  mov     rcx, [rsp+120h+var_D0]; hKey
0x140013192  test    rcx, rcx
0x140013195  jz      short loc_1400131AF
0x140013197  xor     edx, edx; lpSubKey
0x140013199  call    cs:__imp_RegDeleteTreeW
0x14001319f  mov     rcx, [rsp+120h+var_D0]; hKey
0x1400131a4  test    rcx, rcx
0x1400131a7  jz      short loc_1400131AF
0x1400131a9  call    cs:__imp_RegCloseKey
0x1400131af  mov     rcx, [rsp+120h+var_C0]; hKey
0x1400131b4  test    rcx, rcx
0x1400131b7  jz      short loc_1400131BF
0x1400131b9  call    cs:__imp_RegCloseKey
0x1400131bf  mov     rcx, [rsp+120h+hKey]; hKey
0x1400131c4  test    rcx, rcx
0x1400131c7  jz      short loc_1400131D0
0x1400131c9  call    cs:__imp_RegCloseKey
0x1400131cf  nop
0x1400131d0  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400131d7  call    cs:__imp_LeaveCriticalSection
0x1400131dd  jmp     short loc_14001323D
0x1400131df  mov     rcx, [rsp+120h+var_D0]; hKey
0x1400131e4  call    cs:__imp_RegCloseKey
0x1400131ea  mov     rcx, [rsp+120h+var_C0]; hKey
0x1400131ef  call    cs:__imp_RegCloseKey
  ... truncated ...
```
