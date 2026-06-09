# CVdsSubSystem::SetImportTarget(ushort *)

- ea: `0x140014a50`
- end: `0x140014fbb`
- name: `?SetImportTarget@CVdsSubSystem@@UEAAJPEAG@Z`
- size: `1387`
- prototype: `int(CVdsSubSystem *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1400069e8`
- `0x140012c48`
- `0x140013298`
- `0x140014a50`
- `0x140015360`
- `0x14001f220`
- `0x140052e46`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x140014e10`
- `msvcrt!_wcsicmp` at `0x140014e10`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140014b78`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140014b78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140014dc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140014dd7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140014f10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140014f23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140014f37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140014f4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140014f5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140014dc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140014dd7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140014f10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140014f23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140014f37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140014f4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140014f5e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140014ed6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140014ed6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140014bd2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140014bd2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140014e4b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140014e4b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140014c4b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140014c4b`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140014ada`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140014ada`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140014f6c`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140014f6c`
- `vdsutil!VdsTraceW` at `0x140014b3b`
- `vdsutil!VdsTraceW` at `0x140014bea`
- `vdsutil!VdsTraceW` at `0x140014c63`
- `vdsutil!VdsTraceW` at `0x140014ca4`
- `vdsutil!VdsTraceW` at `0x140014d0d`
- `vdsutil!VdsTraceW` at `0x140014e8b`
- `vdsutil!VdsTraceW` at `0x140014efc`
- `vdsutil!VdsTraceW` at `0x140014b3b`
- `vdsutil!VdsTraceW` at `0x140014bea`
- `vdsutil!VdsTraceW` at `0x140014c63`
- `vdsutil!VdsTraceW` at `0x140014ca4`
- `vdsutil!VdsTraceW` at `0x140014d0d`
- `vdsutil!VdsTraceW` at `0x140014e8b`
- `vdsutil!VdsTraceW` at `0x140014efc`

## string_xrefs

- `0x140014b93`: `System\CurrentControlSet\Services\vds`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CVdsSubSystem::SetImportTarget(CVdsSubSystem *this, unsigned __int16 *a2)
{
  unsigned int v4; // ebx
  unsigned int v5; // eax
  unsigned int v6; // ebx
  int v7; // eax
  int v8; // eax
  int v9; // eax
  __int64 (__fastcall ***v10)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v11; // rdx
  int v12; // eax
  int v13; // eax
  __int64 v14; // rax
  __int64 v16; // [rsp+50h] [rbp-B0h] BYREF
  int v17; // [rsp+58h] [rbp-A8h] BYREF
  __int64 (__fastcall ***v18)(_QWORD, GUID *, __int64 *); // [rsp+60h] [rbp-A0h] BYREF
  __int64 v19; // [rsp+68h] [rbp-98h] BYREF
  HKEY v20; // [rsp+70h] [rbp-90h] BYREF
  LPVOID v21; // [rsp+78h] [rbp-88h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v23[16]; // [rsp+88h] [rbp-78h] BYREF
  struct _GUID v24; // [rsp+98h] [rbp-68h] BYREF
  __int128 v25; // [rsp+A8h] [rbp-58h] BYREF
  LPVOID pv[2]; // [rsp+B8h] [rbp-48h]
  __int64 v27; // [rsp+C8h] [rbp-38h]
  __int128 v28; // [rsp+D0h] [rbp-30h] BYREF
  LPCWSTR lpValueName[2]; // [rsp+E0h] [rbp-20h]
  __int128 v30; // [rsp+F0h] [rbp-10h]
  __int64 v31; // [rsp+100h] [rbp+0h]
  GUID Buf2; // [rsp+108h] [rbp+8h] BYREF
  OLECHAR sz[48]; // [rsp+120h] [rbp+20h] BYREF
  WCHAR SubKey[152]; // [rsp+180h] [rbp+80h] BYREF

  Buf2 = 0;
  hKey = 0;
  v20 = 0;
  v28 = 0;
  *(_OWORD *)lpValueName = 0;
  v30 = 0;
  v31 = 0;
  v21 = 0;
  v19 = 0;
  v17 = 0;
  v18 = 0;
  v16 = 0;
  v25 = 0;
  *(_OWORD *)pv = 0;
  v27 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v23, 0x5Eu, "CVdsSubSystem::SetImportTarget()");
  v28 = 0;
  *(_OWORD *)lpValueName = 0;
  v30 = 0;
  v31 = 0;
  v25 = 0;
  *(_OWORD *)pv = 0;
  v27 = 0;
  Buf2 = *CVdsSubSystem::GetProviderId((CVdsSubSystem *)((char *)this - 32), &v24);
  if ( !memcmp_0(&GUID_NULL, &Buf2, 0x10u) )
  {
    VdsTraceW(0, L"CVdsSubSystem::SetImportTarget, 1, hr=%lX");
    VdsLogError(0xC2000001, 0, 0, 0, 0x2090011u, 0);
    v4 = -2147211929;
    goto LABEL_48;
  }
  StringFromGUID2(&Buf2, sz, 45);
  StringCchPrintfW(SubKey, 0x96u, L"%s\\%s\\%s", g_wszVdsKey, aHardwareprovid, sz);
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x2000000u, &hKey);
  v6 = v5;
  if ( v5 )
  {
    VdsTraceW(0, L"CVdsSubSystem::SetImportTarget, 2, error=%ld", v5);
    VdsLogError(0xC2000001, 0, 0, v6, 0x2090012u, 0);
    v4 = -2147418113;
    goto LABEL_48;
  }
  v4 = RegCreateKeyExW(hKey, g_wszVdsImportTargets, 0, 0, 0, 0xF003Fu, 0, &v20, 0);
  if ( v4 )
  {
    VdsTraceW(0, L"CVdsSubSystem::SetImportTarget, 3, error=%ld", v4);
    goto LABEL_7;
  }
  v7 = (*(__int64 (__fastcall **)(char *, __int128 *))(*((_QWORD *)this - 4) + 24LL))((char *)this - 32, &v28);
  v4 = v7;
  if ( v7 < 0 )
  {
    VdsTraceW(0, L"CVdsSubSystem::SetImportTarget, 4, hr=%lX", (unsigned int)v7);
    goto LABEL_48;
  }
  if ( !lpValueName[1] || !*lpValueName[1] )
  {
    VdsTraceW(0, L"CVdsSubSystem::SetImportTarget, 5");
    v4 = -2147211001;
    goto LABEL_48;
  }
  if ( !a2 || !*a2 )
  {
    if ( (*(int (__fastcall **)(CVdsSubSystem *, LPVOID *))(*(_QWORD *)this + 24LL))(this, &v21) >= 0 )
    {
      v4 = RegDeleteValueW(v20, lpValueName[1]);
      if ( v4 )
      {
        VdsTraceW(0, L"CVdsSubSystem::SetImportTarget, 6, error=%ld", v4);
LABEL_7:
        if ( (int)v4 > 0 )
          v4 = (unsigned __int16)v4 | 0x80070000;
        goto LABEL_48;
      }
    }
LABEL_46:
    v4 = 0;
    goto LABEL_48;
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 14) + 24LL))(*((_QWORD *)this + 14), &v19);
  v4 = v8;
  if ( v8 < 0 )
  {
    VdsTraceW(0, L"CVdsSubSystem::SetImportTarget, 7, %lX", (unsigned int)v8);
    goto LABEL_48;
  }
  if ( v19 )
  {
    do
    {
      v17 = 0;
      ATL::CComPtrBase<IVdsIscsiPortal>::Release(&v18);
      v9 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *), int *))(*(_QWORD *)v19 + 24LL))(
             v19,
             1,
             &v18,
             &v17);
      v4 = v9;
      if ( v9 < 0 )
      {
        VdsTraceW(0, L"CVdsSubSystem::SetImportTarget, 9, hr=%lX", (unsigned int)v9);
        goto LABEL_48;
      }
      v10 = v18;
      if ( !v18 )
      {
        VdsTraceW(0, L"CVdsSubSystem::SetImportTarget, 10");
        goto LABEL_19;
      }
      if ( v9 == 1 )
      {
        v4 = -2147024809;
        goto LABEL_48;
      }
      v11 = v16;
      if ( v16 )
      {
        v16 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        v10 = v18;
      }
      v12 = (**v10)(v10, &IID_IVdsIscsiTarget, &v16);
      if ( v12 < 0 )
      {
        VdsTraceW(0, L"CVdsSubSystem::SetImportTarget, 11, %lX", (unsigned int)v12);
        goto LABEL_19;
      }
      if ( !v16 )
      {
        VdsTraceW(0, L"CVdsSubSystem::SetImportTarget, 12");
        goto LABEL_19;
      }
      if ( pv[0] )
      {
        CoTaskMemFree(pv[0]);
        pv[0] = 0;
      }
      if ( pv[1] )
        CoTaskMemFree(pv[1]);
      v25 = 0;
      *(_OWORD *)pv = 0;
      v27 = 0;
      v13 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v16 + 24LL))(v16, &v25);
      v4 = v13;
      if ( v13 < 0 )
      {
        VdsTraceW(0, L"CVdsSubSystem::SetImportTarget, 13, hr=%lX", (unsigned int)v13);
        goto LABEL_48;
      }
    }
    while ( _wcsicmp(a2, (const wchar_t *)pv[0]) );
    v14 = -1;
    do
      ++v14;
    while ( a2[v14] );
    v4 = RegSetValueExW(v20, lpValueName[1], 0, 1u, (const BYTE *)a2, 2 * v14 + 2);
    if ( v4 )
    {
      VdsTraceW(0, L"CVdsSubSystem::SetImportTarget, 14, error=%ld", v4);
      goto LABEL_7;
    }
    goto LABEL_46;
  }
  VdsTraceW(0, L"CVdsSubSystem::SetImportTarget, 8");
LABEL_19:
  v4 = -2147212222;
LABEL_48:
  if ( lpValueName[0] )
  {
    CoTaskMemFree((LPVOID)lpValueName[0]);
    lpValueName[0] = 0;
  }
  if ( lpValueName[1] )
  {
    CoTaskMemFree((LPVOID)lpValueName[1]);
    lpValueName[1] = 0;
  }
  if ( v21 )
  {
    CoTaskMemFree(v21);
    v21 = 0;
  }
  if ( pv[0] )
  {
    CoTaskMemFree(pv[0]);
    pv[0] = 0;
  }
  if ( pv[1] )
  {
    CoTaskMemFree(pv[1]);
    pv[1] = 0;
  }
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v23);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v18);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
  return v4;
}

```

## disassembly

```asm
0x140014a50  mov     [rsp-8+arg_10], rbx
0x140014a55  push    rbp
0x140014a56  push    rsi
0x140014a57  push    rdi
0x140014a58  push    r14
0x140014a5a  push    r15
0x140014a5c  lea     rbp, [rsp-1C0h]
0x140014a64  sub     rsp, 2C0h
0x140014a6b  mov     rax, cs:__security_cookie
0x140014a72  xor     rax, rsp
0x140014a75  mov     [rbp+1E0h+var_30], rax
0x140014a7c  mov     rdi, rdx
0x140014a7f  mov     rsi, rcx
0x140014a82  xorps   xmm0, xmm0
0x140014a85  movups  xmmword ptr [rbp+1E0h+Buf2.Data1], xmm0
0x140014a89  xor     r15d, r15d
0x140014a8c  mov     [rbp+1E0h+hKey], r15
0x140014a90  mov     [rsp+2E0h+var_270], r15
0x140014a95  xor     eax, eax
0x140014a97  movups  [rbp+1E0h+var_210], xmm0
0x140014a9b  movups  xmmword ptr [rbp+1E0h+lpValueName], xmm0
0x140014a9f  movups  [rbp+1E0h+var_1F0], xmm0
0x140014aa3  mov     [rbp+1E0h+var_1E0], rax
0x140014aa7  mov     [rsp+2E0h+var_268], r15
0x140014aac  mov     [rsp+2E0h+var_278], r15
0x140014ab1  mov     [rsp+2E0h+var_288], r15d
0x140014ab6  mov     [rsp+2E0h+var_280], r15
0x140014abb  mov     [rsp+2E0h+var_290], r15
0x140014ac0  movups  [rbp+1E0h+var_238], xmm0
0x140014ac4  movups  xmmword ptr [rbp+1E0h+pv], xmm0
0x140014ac8  mov     [rbp+1E0h+var_218], rax
0x140014acc  lea     r8, aCvdssubsystemS_14; "CVdsSubSystem::SetImportTarget()"
0x140014ad3  lea     edx, [rax+5Eh]
0x140014ad6  lea     rcx, [rbp+1E0h+var_258]
0x140014ada  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140014ae0  nop
0x140014ae1  xorps   xmm0, xmm0
0x140014ae4  xor     eax, eax
0x140014ae6  movups  [rbp+1E0h+var_210], xmm0
0x140014aea  movups  xmmword ptr [rbp+1E0h+lpValueName], xmm0
0x140014aee  movups  [rbp+1E0h+var_1F0], xmm0
0x140014af2  mov     [rbp+1E0h+var_1E0], rax
0x140014af6  movups  [rbp+1E0h+var_238], xmm0
0x140014afa  movups  xmmword ptr [rbp+1E0h+pv], xmm0
0x140014afe  mov     [rbp+1E0h+var_218], rax
0x140014b02  lea     r14, [rsi-20h]
0x140014b06  lea     rdx, [rbp+1E0h+var_248]; retstr
0x140014b0a  mov     rcx, r14; this
0x140014b0d  call    ?GetProviderId@CVdsSubSystem@@QEAA?AU_GUID@@XZ; CVdsSubSystem::GetProviderId(void)
0x140014b12  movups  xmm0, xmmword ptr [rax]
0x140014b15  movdqu  xmmword ptr [rbp+1E0h+Buf2.Data1], xmm0
0x140014b1a  lea     r8d, [r15+10h]; Size
0x140014b1e  lea     rdx, [rbp+1E0h+Buf2]; Buf2
0x140014b22  lea     rcx, GUID_NULL; Buf1
0x140014b29  call    memcmp_0
0x140014b2e  test    eax, eax
0x140014b30  jnz     short loc_140014B6A
0x140014b32  lea     rdx, aCvdssubsystemS_24; "CVdsSubSystem::SetImportTarget, 1, hr=%"...
0x140014b39  xor     ecx, ecx
0x140014b3b  call    cs:__imp_VdsTraceW
0x140014b41  mov     qword ptr [rsp+2E0h+samDesired], r15; unsigned __int16 *
0x140014b46  mov     dword ptr [rsp+2E0h+phkResult], 2090011h; unsigned int
0x140014b4e  xor     r9d, r9d; unsigned int
0x140014b51  xor     r8d, r8d; void *
0x140014b54  xor     edx, edx; unsigned int
0x140014b56  mov     ecx, 0C2000001h; unsigned int
0x140014b5b  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x140014b60  mov     ebx, 80042567h
0x140014b65  jmp     loc_140014F07
0x140014b6a  mov     r8d, 2Dh ; '-'; cchMax
0x140014b70  lea     rdx, [rbp+1E0h+sz]; lpsz
0x140014b74  lea     rcx, [rbp+1E0h+Buf2]; rguid
0x140014b78  call    cs:__imp_StringFromGUID2
0x140014b7e  lea     rax, [rbp+1E0h+sz]
0x140014b82  mov     qword ptr [rsp+2E0h+samDesired], rax
0x140014b87  lea     rax, aHardwareprovid; "HardwareProviders"
0x140014b8e  mov     [rsp+2E0h+phkResult], rax
0x140014b93  lea     r9, ?g_wszVdsKey@@3PAGA; "System\\CurrentControlSet\\Services\\vd"...
0x140014b9a  lea     r8, aSSS; "%s\\%s\\%s"
0x140014ba1  mov     edx, 96h; unsigned __int64
0x140014ba6  lea     rcx, [rbp+1E0h+SubKey]; unsigned __int16 *
0x140014bad  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140014bb2  lea     rax, [rbp+1E0h+hKey]
0x140014bb6  mov     [rsp+2E0h+phkResult], rax; phkResult
0x140014bbb  mov     r9d, 2000000h; samDesired
0x140014bc1  xor     r8d, r8d; ulOptions
0x140014bc4  lea     rdx, [rbp+1E0h+SubKey]; lpSubKey
0x140014bcb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140014bd2  call    cs:__imp_RegOpenKeyExW
0x140014bd8  mov     ebx, eax
0x140014bda  test    eax, eax
0x140014bdc  jz      short loc_140014C19
0x140014bde  mov     r8d, eax
0x140014be1  lea     rdx, aCvdssubsystemS_22; "CVdsSubSystem::SetImportTarget, 2, erro"...
0x140014be8  xor     ecx, ecx
0x140014bea  call    cs:__imp_VdsTraceW
0x140014bf0  mov     qword ptr [rsp+2E0h+samDesired], r15; unsigned __int16 *
0x140014bf5  mov     dword ptr [rsp+2E0h+phkResult], 2090012h; unsigned int
0x140014bfd  mov     r9d, ebx; unsigned int
0x140014c00  xor     r8d, r8d; void *
0x140014c03  xor     edx, edx; unsigned int
0x140014c05  mov     ecx, 0C2000001h; unsigned int
0x140014c0a  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x140014c0f  mov     ebx, 8000FFFFh
0x140014c14  jmp     loc_140014F07
0x140014c19  mov     [rsp+2E0h+lpdwDisposition], r15; lpdwDisposition
0x140014c1e  lea     rax, [rsp+2E0h+var_270]
0x140014c23  mov     [rsp+2E0h+var_2A8], rax; phkResult
0x140014c28  mov     [rsp+2E0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x140014c2d  mov     [rsp+2E0h+samDesired], 0F003Fh; samDesired
0x140014c35  mov     dword ptr [rsp+2E0h+phkResult], r15d; dwOptions
0x140014c3a  xor     r9d, r9d; lpClass
0x140014c3d  xor     r8d, r8d; Reserved
0x140014c40  lea     rdx, ?g_wszVdsImportTargets@@3PAGA; "ImportTargets"
0x140014c47  mov     rcx, [rbp+1E0h+hKey]; hKey
0x140014c4b  call    cs:__imp_RegCreateKeyExW
0x140014c51  mov     ebx, eax
0x140014c53  test    eax, eax
0x140014c55  jz      short loc_140014C7F
0x140014c57  lea     rdx, aCvdssubsystemS_11; "CVdsSubSystem::SetImportTarget, 3, erro"...
0x140014c5e  mov     r8d, ebx
0x140014c61  xor     ecx, ecx
0x140014c63  call    cs:__imp_VdsTraceW
0x140014c69  test    ebx, ebx
0x140014c6b  jle     loc_140014F07
0x140014c71  movzx   ebx, bx
0x140014c74  or      ebx, 80070000h
0x140014c7a  jmp     loc_140014F07
0x140014c7f  mov     rax, [r14]
0x140014c82  lea     rdx, [rbp+1E0h+var_210]
0x140014c86  mov     rcx, r14
0x140014c89  mov     rax, [rax+18h]
0x140014c8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014c92  mov     ebx, eax
0x140014c94  test    eax, eax
0x140014c96  jns     short loc_140014CAF
0x140014c98  lea     rdx, aCvdssubsystemS_18; "CVdsSubSystem::SetImportTarget, 4, hr=%"...
0x140014c9f  mov     r8d, eax
0x140014ca2  xor     ecx, ecx
0x140014ca4  call    cs:__imp_VdsTraceW
0x140014caa  jmp     loc_140014F07
0x140014caf  mov     rcx, [rbp+1E0h+lpValueName+8]
0x140014cb3  test    rcx, rcx
0x140014cb6  jz      loc_140014EF3
0x140014cbc  cmp     r15w, [rcx]
0x140014cc0  jz      loc_140014EF3
0x140014cc6  test    rdi, rdi
0x140014cc9  jz      loc_140014EB5
0x140014ccf  cmp     r15w, [rdi]
0x140014cd3  jz      loc_140014EB5
0x140014cd9  mov     rcx, [rsi+70h]
0x140014cdd  mov     rax, [rcx]
0x140014ce0  lea     rdx, [rsp+2E0h+var_278]
0x140014ce5  mov     rax, [rax+18h]
0x140014ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014cee  mov     ebx, eax
0x140014cf0  test    eax, eax
0x140014cf2  jns     short loc_140014CFD
0x140014cf4  lea     rdx, aCvdssubsystemS_17; "CVdsSubSystem::SetImportTarget, 7, %lX"
0x140014cfb  jmp     short loc_140014C9F
0x140014cfd  cmp     [rsp+2E0h+var_278], r15
0x140014d02  jnz     short loc_140014D1D
0x140014d04  lea     rdx, aCvdssubsystemS_23; "CVdsSubSystem::SetImportTarget, 8"
0x140014d0b  xor     ecx, ecx
0x140014d0d  call    cs:__imp_VdsTraceW
0x140014d13  mov     ebx, 80042442h
0x140014d18  jmp     loc_140014F07
0x140014d1d  mov     esi, 1
0x140014d22  mov     [rsp+2E0h+var_288], r15d
0x140014d27  lea     rcx, [rsp+2E0h+var_280]
0x140014d2c  call    ?Release@?$CComPtrBase@UIVdsIscsiPortal@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IVdsIscsiPortal>::Release(void)
0x140014d31  mov     rcx, [rsp+2E0h+var_278]
0x140014d36  mov     rax, [rcx]
0x140014d39  lea     r9, [rsp+2E0h+var_288]
0x140014d3e  lea     r8, [rsp+2E0h+var_280]
0x140014d43  mov     edx, esi
0x140014d45  mov     rax, [rax+18h]
0x140014d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014d4e  mov     ebx, eax
0x140014d50  test    eax, eax
0x140014d52  js      loc_140014EA9
0x140014d58  mov     rcx, [rsp+2E0h+var_280]
0x140014d5d  test    rcx, rcx
0x140014d60  jz      loc_140014E9D
0x140014d66  cmp     eax, esi
0x140014d68  jz      loc_140014E96
0x140014d6e  mov     rdx, [rsp+2E0h+var_290]
0x140014d73  test    rdx, rdx
0x140014d76  jz      short loc_140014D91
0x140014d78  mov     [rsp+2E0h+var_290], r15
0x140014d7d  mov     rax, [rdx]
0x140014d80  mov     rcx, rdx
0x140014d83  mov     rax, [rax+10h]
0x140014d87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014d8c  mov     rcx, [rsp+2E0h+var_280]
0x140014d91  mov     rax, [rcx]
0x140014d94  lea     r8, [rsp+2E0h+var_290]
0x140014d99  lea     rdx, IID_IVdsIscsiTarget
0x140014da0  mov     rax, [rax]
0x140014da3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014da8  test    eax, eax
0x140014daa  js      loc_140014E7F
0x140014db0  cmp     [rsp+2E0h+var_290], r15
0x140014db5  jz      loc_140014E73
0x140014dbb  mov     rcx, [rbp+1E0h+pv]; pv
0x140014dbf  test    rcx, rcx
0x140014dc2  jz      short loc_140014DCE
0x140014dc4  call    cs:__imp_CoTaskMemFree
0x140014dca  mov     [rbp+1E0h+pv], r15
0x140014dce  mov     rcx, [rbp+1E0h+pv+8]; pv
0x140014dd2  test    rcx, rcx
0x140014dd5  jz      short loc_140014DDD
0x140014dd7  call    cs:__imp_CoTaskMemFree
0x140014ddd  xorps   xmm0, xmm0
0x140014de0  xor     eax, eax
0x140014de2  movups  [rbp+1E0h+var_238], xmm0
0x140014de6  movups  xmmword ptr [rbp+1E0h+pv], xmm0
0x140014dea  mov     [rbp+1E0h+var_218], rax
0x140014dee  mov     rcx, [rsp+2E0h+var_290]
0x140014df3  mov     rax, [rcx]
0x140014df6  lea     rdx, [rbp+1E0h+var_238]
0x140014dfa  mov     rax, [rax+18h]
0x140014dfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014e03  mov     ebx, eax
0x140014e05  test    eax, eax
0x140014e07  js      short loc_140014E67
0x140014e09  mov     rdx, [rbp+1E0h+pv]; String2
0x140014e0d  mov     rcx, rdi; String1
0x140014e10  call    cs:__imp__wcsicmp
0x140014e16  test    eax, eax
0x140014e18  jnz     loc_140014D22
0x140014e1e  or      rax, 0FFFFFFFFFFFFFFFFh
0x140014e22  inc     rax
0x140014e25  cmp     [rdi+rax*2], r15w
0x140014e2a  jnz     short loc_140014E22
0x140014e2c  lea     eax, ds:2[rax*2]
0x140014e33  mov     [rsp+2E0h+samDesired], eax; cbData
0x140014e37  mov     [rsp+2E0h+phkResult], rdi; lpData
0x140014e3c  mov     r9d, esi; dwType
0x140014e3f  xor     r8d, r8d; Reserved
0x140014e42  mov     rdx, [rbp+1E0h+lpValueName+8]; lpValueName
0x140014e46  mov     rcx, [rsp+2E0h+var_270]; hKey
0x140014e4b  call    cs:__imp_RegSetValueExW
0x140014e51  mov     ebx, eax
0x140014e53  test    eax, eax
0x140014e55  jz      loc_140014EEE
0x140014e5b  lea     rdx, aCvdssubsystemS_21; "CVdsSubSystem::SetImportTarget, 14, err"...
0x140014e62  jmp     loc_140014C5E
0x140014e67  lea     rdx, aCvdssubsystemS_13; "CVdsSubSystem::SetImportTarget, 13, hr="...
0x140014e6e  jmp     loc_140014C9F
0x140014e73  lea     rdx, aCvdssubsystemS_19; "CVdsSubSystem::SetImportTarget, 12"
0x140014e7a  jmp     loc_140014D0B
0x140014e7f  mov     r8d, eax
0x140014e82  lea     rdx, aCvdssubsystemS_1; "CVdsSubSystem::SetImportTarget, 11, %lX"
0x140014e89  xor     ecx, ecx
0x140014e8b  call    cs:__imp_VdsTraceW
0x140014e91  jmp     loc_140014D13
0x140014e96  mov     ebx, 80070057h
0x140014e9b  jmp     short loc_140014F07
0x140014e9d  lea     rdx, aCvdssubsystemS_5; "CVdsSubSystem::SetImportTarget, 10"
0x140014ea4  jmp     loc_140014D0B
0x140014ea9  lea     rdx, aCvdssubsystemS_15; "CVdsSubSystem::SetImportTarget, 9, hr=%"...
0x140014eb0  jmp     loc_140014C9F
0x140014eb5  mov     rax, [rsi]
0x140014eb8  lea     rdx, [rsp+2E0h+var_268]
0x140014ebd  mov     rcx, rsi
0x140014ec0  mov     rax, [rax+18h]
0x140014ec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014ec9  test    eax, eax
0x140014ecb  js      short loc_140014EEE
0x140014ecd  mov     rdx, [rbp+1E0h+lpValueName+8]; lpValueName
0x140014ed1  mov     rcx, [rsp+2E0h+var_270]; hKey
0x140014ed6  call    cs:__imp_RegDeleteValueW
0x140014edc  mov     ebx, eax
0x140014ede  test    eax, eax
0x140014ee0  jz      short loc_140014EEE
0x140014ee2  lea     rdx, aCvdssubsystemS_7; "CVdsSubSystem::SetImportTarget, 6, erro"...
0x140014ee9  jmp     loc_140014C5E
0x140014eee  mov     ebx, r15d
0x140014ef1  jmp     short loc_140014F07
0x140014ef3  lea     rdx, aCvdssubsystemS_10; "CVdsSubSystem::SetImportTarget, 5"
0x140014efa  xor     ecx, ecx
0x140014efc  call    cs:__imp_VdsTraceW
0x140014f02  mov     ebx, 80042907h
0x140014f07  mov     rcx, [rbp+1E0h+lpValueName]; pv
0x140014f0b  test    rcx, rcx
0x140014f0e  jz      short loc_140014F1A
0x140014f10  call    cs:__imp_CoTaskMemFree
0x140014f16  mov     [rbp+1E0h+lpValueName], r15
0x140014f1a  mov     rcx, [rbp+1E0h+lpValueName+8]; pv
0x140014f1e  test    rcx, rcx
0x140014f21  jz      short loc_140014F2D
0x140014f23  call    cs:__imp_CoTaskMemFree
0x140014f29  mov     [rbp+1E0h+lpValueName+8], r15
0x140014f2d  mov     rcx, [rsp+2E0h+var_268]; pv
0x140014f32  test    rcx, rcx
0x140014f35  jz      short loc_140014F42
0x140014f37  call    cs:__imp_CoTaskMemFree
0x140014f3d  mov     [rsp+2E0h+var_268], r15
0x140014f42  mov     rcx, [rbp+1E0h+pv]; pv
  ... truncated ...
```
