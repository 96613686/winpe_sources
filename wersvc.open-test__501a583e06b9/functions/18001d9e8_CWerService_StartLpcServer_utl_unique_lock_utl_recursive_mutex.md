# CWerService::_StartLpcServer(utl::unique_lock<utl::recursive_mutex> &)

- ea: `0x18001d9e8`
- end: `0x18001df61`
- name: `?_StartLpcServer@CWerService@@AEAAJAEAV?$unique_lock@Vrecursive_mutex@utl@@@utl@@@Z`
- size: `1401`
- prototype: `__int64 __fastcall(CWerService *this)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001df68`

## callees

- `0x1800029d0`
- `0x1800035e8`
- `0x180006a80`
- `0x180011ef8`
- `0x180013df4`
- `0x180013e9c`
- `0x180013f54`
- `0x18001c258`
- `0x18001c6b0`
- `0x18001c9f8`
- `0x18001d9e8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001de49`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001de49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dc0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001deb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dc0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001deb7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001dc5d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001dc5d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001dcfc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001dcfc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dc7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001de66`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dc7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001de66`
- `ntdll!NtClose` at `0x18001ddc7`
- `ntdll!NtClose` at `0x18001ddc7`
- `ntdll!RtlInitUnicodeString` at `0x18001dcb1`
- `ntdll!RtlInitUnicodeString` at `0x18001dcb1`
- `ntdll!NtAlpcCreatePort` at `0x18001ddd8`
- `ntdll!NtAlpcCreatePort` at `0x18001ddd8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001da7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001da8b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001df21`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001df32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001da7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001da8b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001df21`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001df32`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001dc01`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001dd34`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001dc01`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001dd34`

## string_xrefs

- `0x18001dc4c`: `WerSvc\WerSvcSystemPermissionsEvent`
- `0x18001dca5`: `\WindowsErrorReportingServicePort`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWerService::_StartLpcServer(CWerService *this, __int64 a2, __int64 a3, __int64 a4)
{
  HLOCAL v6; // rcx
  void **v7; // r15
  int PrivateNamespace; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  int v14; // ebx
  __int64 *v15; // rbx
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r8
  __int64 v19; // rcx
  unsigned __int64 v20; // r12
  __int64 v21; // rdx
  __int64 v22; // rax
  PSECURITY_DESCRIPTOR *v23; // rax
  signed int LastError; // eax
  HANDLE v25; // rax
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  void *v29; // rcx
  const WCHAR *v30; // rbx
  const wchar_t *v31; // rax
  PSECURITY_DESCRIPTOR *v32; // rax
  void *v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // rcx
  int Port; // ebx
  __int64 v37; // r8
  __int64 v38; // r9
  _QWORD *v39; // rcx
  __int64 v40; // rdx
  HANDLE v41; // rax
  void *v42; // rcx
  signed int v43; // eax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  int pvData; // [rsp+44h] [rbp-BCh] BYREF
  DWORD ThreadId; // [rsp+48h] [rbp-B8h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL v48; // [rsp+58h] [rbp-A8h] BYREF
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v51[7]; // [rsp+88h] [rbp-78h] BYREF
  __int128 v52; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v53; // [rsp+E0h] [rbp-20h]
  __int128 v54; // [rsp+F0h] [rbp-10h]
  __int64 v55; // [rsp+100h] [rbp+0h]
  _OWORD v56[2]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v57; // [rsp+130h] [rbp+30h]
  __int64 v58; // [rsp+138h] [rbp+38h]
  __int128 v59; // [rsp+140h] [rbp+40h]
  __int64 v60; // [rsp+150h] [rbp+50h]

  v48 = 0;
  v6 = 0;
  hMem = 0;
  memset(&EventAttributes, 0, sizeof(EventAttributes));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids);
    v6 = hMem;
  }
  v7 = (void **)((char *)this + 392);
  if ( *((_QWORD *)this + 49) )
    return 0;
  memset(&EventAttributes, 0, sizeof(EventAttributes));
  if ( *((_QWORD *)this + 48) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v6, a2, a3, a4);
  PrivateNamespace = CWerService::_CreatePrivateNamespace(this);
  v14 = PrivateNamespace;
  if ( PrivateNamespace < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        73,
        WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids,
        (unsigned int)PrivateNamespace);
    goto LABEL_66;
  }
  v15 = (__int64 *)((char *)this + 360);
  if ( *((_QWORD *)this + 45) != *((_QWORD *)this + 46) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v11, v10, v12, v13);
  v16 = *v15;
  v17 = *((_QWORD *)this + 46);
  *((_QWORD *)this + 46) = *((_QWORD *)this + 45);
  utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CWerService::LpcConnection,utl::default_delete<CWerService::LpcConnection>>>>(
    v11,
    v16,
    (v17 - v16) >> 3);
  v18 = *((_QWORD *)this + 46);
  v19 = *v15;
  v20 = (v18 - *((_QWORD *)this + 45)) >> 3;
  if ( v20 < 0x40 )
  {
    if ( (unsigned __int64)((*((_QWORD *)this + 47) - v19) >> 3) < 0x40
      && !(unsigned __int8)utl::vector<utl::unique_ptr<CWerService::LpcConnection,utl::default_delete<CWerService::LpcConnection>>,utl::allocator<utl::unique_ptr<CWerService::LpcConnection,utl::default_delete<CWerService::LpcConnection>>>>::_GrowMinimum((char *)this + 360) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids);
      v14 = -2147024882;
      goto LABEL_66;
    }
    v21 = *((_QWORD *)this + 46);
    v22 = 0;
    if ( 64 != v20 )
    {
      do
        *(_QWORD *)(v21 + 8 * v22++) = 0;
      while ( v22 != 64 - v20 );
    }
    utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CWerService::LpcConnection,utl::default_delete<CWerService::LpcConnection>>>>(
      v19,
      v21,
      0);
    *((_QWORD *)this + 46) = *v15 + 512;
  }
  else
  {
    *((_QWORD *)this + 46) = v19 + 512;
    utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CWerService::LpcConnection,utl::default_delete<CWerService::LpcConnection>>>>(
      v19,
      v19 + 512,
      (v18 - (v19 + 512)) >> 3);
  }
  v23 = (PSECURITY_DESCRIPTOR *)___replace_XU__generic_delete_XU__generic_deallocate__MP6APEAXPEAX_Z1_LocalFree__YAPEAX0_ZPEAX_tlx___tlx___utl__YAPEAPEAXAEAV__unique_ptr_XU__generic_delete_XU__generic_deallocate__MP6APEAXPEAX_Z1_LocalFree__YAPEAX0_ZPEAX_tlx___tlx___0__Z(&hMem);
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:(A;OICI;GR;;;SY)", 1u, v23, 0) )
  {
LABEL_26:
    LastError = GetLastError();
    v14 = LastError;
    if ( LastError > 0 )
      v14 = (unsigned __int16)LastError | 0x80070000;
    if ( v14 >= 0 )
      v14 = -2147467259;
    goto LABEL_66;
  }
  EventAttributes.nLength = 24;
  EventAttributes.bInheritHandle = 0;
  EventAttributes.lpSecurityDescriptor = hMem;
  v25 = CreateEventW(&EventAttributes, 0, 0, L"WerSvc\\WerSvcSystemPermissionsEvent");
  v29 = (void *)*((_QWORD *)this + 51);
  *((_QWORD *)this + 51) = v25;
  if ( (unsigned __int64)v29 + 1 > 1 )
    CloseHandle(v29);
  if ( (unsigned __int64)(*((_QWORD *)this + 51) + 1LL) <= 1 )
  {
    v43 = GetLastError();
    v14 = v43;
    if ( v43 > 0 )
      v14 = (unsigned __int16)v43 | 0x80070000;
    if ( v14 >= 0 )
      v14 = -2147467259;
    v39 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_66;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v40 = 75;
      goto LABEL_64;
    }
  }
  else
  {
    if ( *v7 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v29, v26, v27, v28);
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"\\WindowsErrorReportingServicePort");
    v30 = L"D:P(D;OICI;GA;;;NU)(A;OICI;GR;;;AU)(A;OICI;GR;;;BG)(A;OICI;GA;;;S-1-5-80-3299868208-4286319593-1091140620-3583"
           "751967-1732444380)(A;OICI;GR;;;WD)(A;OICI;GR;;;S-1-15-2-1)(A;OICI;GR;;;S-1-15-3-1024-3153509613-960666767-372"
           "4611135-2725662640-12138253-543910227-1950414635-4190290187)";
    pvData = 0;
    pcbData = 4;
    if ( !RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\Windows Error Reporting",
            L"AllowNetworkUserConnections",
            0x18u,
            0,
            &pvData,
            &pcbData)
      && pcbData == 4 )
    {
      v31 = L"D:P(A;OICI;GR;;;AU)(A;OICI;GR;;;BG)(A;OICI;GA;;;S-1-5-80-3299868208-4286319593-1091140620-3583751967-1732444"
             "380)(A;OICI;GR;;;WD)(A;OICI;GR;;;S-1-15-2-1)(A;OICI;GR;;;S-1-15-3-1024-3153509613-960666767-3724611135-2725"
             "662640-12138253-543910227-1950414635-4190290187)";
      if ( pvData != 1 )
        v31 = L"D:P(D;OICI;GA;;;NU)(A;OICI;GR;;;AU)(A;OICI;GR;;;BG)(A;OICI;GA;;;S-1-5-80-3299868208-4286319593-1091140620-"
               "3583751967-1732444380)(A;OICI;GR;;;WD)(A;OICI;GR;;;S-1-15-2-1)(A;OICI;GR;;;S-1-15-3-1024-3153509613-96066"
               "6767-3724611135-2725662640-12138253-543910227-1950414635-4190290187)";
      v30 = v31;
    }
    v32 = (PSECURITY_DESCRIPTOR *)___replace_XU__generic_delete_XU__generic_deallocate__MP6APEAXPEAX_Z1_LocalFree__YAPEAX0_ZPEAX_tlx___tlx___utl__YAPEAPEAXAEAV__unique_ptr_XU__generic_delete_XU__generic_deallocate__MP6APEAXPEAX_Z1_LocalFree__YAPEAX0_ZPEAX_tlx___tlx___0__Z(&v48);
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v30, 1u, v32, 0) )
      goto LABEL_26;
    v51[0] = 48;
    v51[3] = 0;
    v51[1] = 0;
    v51[2] = &DestinationString;
    v51[4] = v48;
    v51[5] = 0;
    memset_0(&v52, 0, 0x48u);
    v56[0] = v52;
    v58 = *((_QWORD *)&v53 + 1);
    v59 = v54;
    v60 = v55;
    LODWORD(v56[0]) = 0x20000;
    v56[1] = 0x578u;
    v57 = 89600;
    v33 = *v7;
    *v7 = 0;
    if ( v33 )
      NtClose(v33);
    Port = NtAlpcCreatePort((char *)this + 392, v51, v56);
    if ( Port >= 0 )
    {
      ThreadId = 0;
      if ( (unsigned __int64)(*((_QWORD *)this + 50) + 1LL) > 1 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v35, v34, v37, v38);
      v41 = CreateThread(0, 0, CWerService::StaticLpcServerThread, this, 0, &ThreadId);
      v42 = (void *)*((_QWORD *)this + 50);
      *((_QWORD *)this + 50) = v41;
      if ( (unsigned __int64)v42 + 1 > 1 )
        CloseHandle(v42);
      if ( (unsigned __int64)(*((_QWORD *)this + 50) + 1LL) > 1 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids, ThreadId);
        v14 = 0;
        goto LABEL_67;
      }
      goto LABEL_26;
    }
    v14 = Port | 0x10000000;
    v39 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v40 = 76;
LABEL_64:
      WPP_SF_d(v39[2], v40, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids, (unsigned int)v14);
    }
  }
  if ( v14 < 0 )
LABEL_66:
    CWerService::_CleanupLpcServer(this, a2);
LABEL_67:
  if ( hMem )
    LocalFree(hMem);
  if ( v48 )
    LocalFree(v48);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18001d9e8  mov     [rsp-8+arg_10], rbx
0x18001d9ed  push    rbp
0x18001d9ee  push    rsi
0x18001d9ef  push    rdi
0x18001d9f0  push    r12
0x18001d9f2  push    r13
0x18001d9f4  push    r14
0x18001d9f6  push    r15
0x18001d9f8  lea     rbp, [rsp-70h]
0x18001d9fd  sub     rsp, 170h
0x18001da04  mov     rax, cs:__security_cookie
0x18001da0b  xor     rax, rsp
0x18001da0e  mov     [rbp+0A0h+var_40], rax
0x18001da12  mov     r13, rdx
0x18001da15  mov     rsi, rcx
0x18001da18  xor     r14d, r14d
0x18001da1b  mov     [rsp+1A0h+var_148], r14
0x18001da20  mov     ecx, r14d
0x18001da23  mov     [rsp+1A0h+hMem], rcx
0x18001da28  xorps   xmm0, xmm0
0x18001da2b  xor     eax, eax
0x18001da2d  movups  xmmword ptr [rsp+1A0h+EventAttributes.nLength], xmm0
0x18001da32  mov     qword ptr [rsp+1A0h+EventAttributes.bInheritHandle], rax
0x18001da37  lea     rdi, WPP_GLOBAL_Control
0x18001da3e  mov     rax, cs:WPP_GLOBAL_Control
0x18001da45  cmp     rax, rdi
0x18001da48  jz      short loc_18001DA69
0x18001da4a  test    byte ptr [rax+1Ch], 4
0x18001da4e  jz      short loc_18001DA69
0x18001da50  lea     edx, [r14+48h]
0x18001da54  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x18001da5b  mov     rcx, [rax+10h]
0x18001da5f  call    WPP_SF_
0x18001da64  mov     rcx, [rsp+1A0h+hMem]; hMem
0x18001da69  lea     r15, [rsi+188h]
0x18001da70  cmp     [r15], r14
0x18001da73  jz      short loc_18001DA98
0x18001da75  test    rcx, rcx
0x18001da78  jz      short loc_18001DA81
0x18001da7a  call    cs:__imp_LocalFree
0x18001da80  nop
0x18001da81  mov     rcx, [rsp+1A0h+var_148]; hMem
0x18001da86  test    rcx, rcx
0x18001da89  jz      short loc_18001DA91
0x18001da8b  call    cs:__imp_LocalFree
0x18001da91  xor     eax, eax
0x18001da93  jmp     loc_18001DF3A
0x18001da98  xorps   xmm0, xmm0
0x18001da9b  xor     eax, eax
0x18001da9d  movups  xmmword ptr [rsp+1A0h+EventAttributes.nLength], xmm0
0x18001daa2  mov     qword ptr [rsp+1A0h+EventAttributes.bInheritHandle], rax
0x18001daa7  cmp     [rsi+180h], r14
0x18001daae  jz      short loc_18001DAB5
0x18001dab0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001dab5  mov     rcx, rsi; this
0x18001dab8  call    ?_CreatePrivateNamespace@CWerService@@AEAAJXZ; CWerService::_CreatePrivateNamespace(void)
0x18001dabd  mov     ebx, eax
0x18001dabf  test    eax, eax
0x18001dac1  jns     short loc_18001DAFD
0x18001dac3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001daca  cmp     rcx, rdi
0x18001dacd  jz      loc_18001DF0B
0x18001dad3  mov     edi, 1
0x18001dad8  test    [rcx+1Ch], dil
0x18001dadc  jz      loc_18001DF0B
0x18001dae2  lea     edx, [rdi+48h]
0x18001dae5  mov     r9d, eax
0x18001dae8  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x18001daef  mov     rcx, [rcx+10h]
0x18001daf3  call    WPP_SF_d
0x18001daf8  jmp     loc_18001DF0B
0x18001dafd  lea     rbx, [rsi+168h]
0x18001db04  mov     rax, [rbx+8]
0x18001db08  cmp     [rbx], rax
0x18001db0b  jz      short loc_18001DB12
0x18001db0d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001db12  mov     rdx, [rbx]
0x18001db15  mov     r8, [rbx+8]
0x18001db19  mov     [rbx+8], rdx
0x18001db1d  sub     r8, rdx
0x18001db20  sar     r8, 3
0x18001db24  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@ULpcConnection@CWerService@@U?$default_delete@ULpcConnection@CWerService@@@utl@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@ULpcConnection@CWerService@@U?$default_delete@ULpcConnection@CWerService@@@utl@@@utl@@@0@PEAV?$unique_ptr@ULpcConnection@CWerService@@U?$default_delete@ULpcConnection@CWerService@@@utl@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CWerService::LpcConnection,utl::default_delete<CWerService::LpcConnection>>>>(utl::allocator<utl::unique_ptr<CWerService::LpcConnection,utl::default_delete<CWerService::LpcConnection>>> &,utl::unique_ptr<CWerService::LpcConnection,utl::default_delete<CWerService::LpcConnection>> *,unsigned __int64)
0x18001db29  mov     r8, [rbx+8]
0x18001db2d  mov     rcx, [rbx]
0x18001db30  mov     r12, r8
0x18001db33  sub     r12, rcx
0x18001db36  sar     r12, 3
0x18001db3a  mov     edi, 1
0x18001db3f  lea     r14d, [rdi+3Fh]
0x18001db43  cmp     r12, r14
0x18001db46  jb      short loc_18001DB64
0x18001db48  lea     rdx, [rcx+200h]
0x18001db4f  mov     [rbx+8], rdx
0x18001db53  sub     r8, rdx
0x18001db56  sar     r8, 3
0x18001db5a  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@ULpcConnection@CWerService@@U?$default_delete@ULpcConnection@CWerService@@@utl@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@ULpcConnection@CWerService@@U?$default_delete@ULpcConnection@CWerService@@@utl@@@utl@@@0@PEAV?$unique_ptr@ULpcConnection@CWerService@@U?$default_delete@ULpcConnection@CWerService@@@utl@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CWerService::LpcConnection,utl::default_delete<CWerService::LpcConnection>>>>(utl::allocator<utl::unique_ptr<CWerService::LpcConnection,utl::default_delete<CWerService::LpcConnection>>> &,utl::unique_ptr<CWerService::LpcConnection,utl::default_delete<CWerService::LpcConnection>> *,unsigned __int64)
0x18001db5f  jmp     loc_18001DBE8
0x18001db64  mov     rax, [rbx+10h]
0x18001db68  sub     rax, rcx
0x18001db6b  sar     rax, 3
0x18001db6f  cmp     rax, r14
0x18001db72  jnb     short loc_18001DBB8
0x18001db74  mov     rcx, rbx
0x18001db77  call    ?_GrowMinimum@?$vector@V?$unique_ptr@ULpcConnection@CWerService@@U?$default_delete@ULpcConnection@CWerService@@@utl@@@utl@@V?$allocator@V?$unique_ptr@ULpcConnection@CWerService@@U?$default_delete@ULpcConnection@CWerService@@@utl@@@utl@@@2@@utl@@AEAA_N_K@Z; utl::vector<utl::unique_ptr<CWerService::LpcConnection,utl::default_delete<CWerService::LpcConnection>>,utl::allocator<utl::unique_ptr<CWerService::LpcConnection,utl::default_delete<CWerService::LpcConnection>>>>::_GrowMinimum(unsigned __int64)
0x18001db7c  test    al, al
0x18001db7e  jnz     short loc_18001DBB8
0x18001db80  mov     rcx, cs:WPP_GLOBAL_Control
0x18001db87  lea     rax, WPP_GLOBAL_Control
0x18001db8e  cmp     rcx, rax
0x18001db91  jz      short loc_18001DBAE
0x18001db93  test    [rcx+1Ch], dil
0x18001db97  jz      short loc_18001DBAE
0x18001db99  mov     edx, 4Ah ; 'J'
0x18001db9e  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x18001dba5  mov     rcx, [rcx+10h]
0x18001dba9  call    WPP_SF_
0x18001dbae  mov     ebx, 8007000Eh
0x18001dbb3  jmp     loc_18001DF0B
0x18001dbb8  mov     rdx, [rbx+8]
0x18001dbbc  xor     eax, eax
0x18001dbbe  sub     r14, r12
0x18001dbc1  jz      short loc_18001DBD3
0x18001dbc3  mov     qword ptr [rdx+rax*8], 0
0x18001dbcb  add     rax, rdi
0x18001dbce  cmp     rax, r14
0x18001dbd1  jnz     short loc_18001DBC3
0x18001dbd3  xor     r8d, r8d
0x18001dbd6  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@ULpcConnection@CWerService@@U?$default_delete@ULpcConnection@CWerService@@@utl@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@ULpcConnection@CWerService@@U?$default_delete@ULpcConnection@CWerService@@@utl@@@utl@@@0@PEAV?$unique_ptr@ULpcConnection@CWerService@@U?$default_delete@ULpcConnection@CWerService@@@utl@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CWerService::LpcConnection,utl::default_delete<CWerService::LpcConnection>>>>(utl::allocator<utl::unique_ptr<CWerService::LpcConnection,utl::default_delete<CWerService::LpcConnection>>> &,utl::unique_ptr<CWerService::LpcConnection,utl::default_delete<CWerService::LpcConnection>> *,unsigned __int64)
0x18001dbdb  mov     rax, [rbx]
0x18001dbde  add     rax, 200h
0x18001dbe4  mov     [rbx+8], rax
0x18001dbe8  lea     rcx, [rsp+1A0h+hMem]
0x18001dbed  call    ??$replace@XU?$generic_delete@XU?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@utl@@YAPEAPEAXAEAV?$unique_ptr@XU?$generic_delete@XU?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@0@@Z
0x18001dbf2  xor     r9d, r9d; SecurityDescriptorSize
0x18001dbf5  mov     r8, rax; SecurityDescriptor
0x18001dbf8  mov     edx, edi; StringSDRevision
0x18001dbfa  lea     rcx, aDAOiciGrSy; "D:(A;OICI;GR;;;SY)"
0x18001dc01  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001dc07  xor     r14d, r14d
0x18001dc0a  test    eax, eax
0x18001dc0c  jnz     short loc_18001DC32
0x18001dc0e  call    cs:__imp_GetLastError
0x18001dc14  mov     ebx, eax
0x18001dc16  test    eax, eax
0x18001dc18  jle     short loc_18001DC23
0x18001dc1a  movzx   ebx, ax
0x18001dc1d  or      ebx, 80070000h
0x18001dc23  mov     eax, 80004005h
0x18001dc28  test    ebx, ebx
0x18001dc2a  cmovns  ebx, eax
0x18001dc2d  jmp     loc_18001DF0B
0x18001dc32  mov     r12d, 18h
0x18001dc38  mov     [rsp+1A0h+EventAttributes.nLength], r12d
0x18001dc3d  mov     [rsp+1A0h+EventAttributes.bInheritHandle], r14d
0x18001dc42  mov     rax, [rsp+1A0h+hMem]
0x18001dc47  mov     [rsp+1A0h+EventAttributes.lpSecurityDescriptor], rax
0x18001dc4c  lea     r9, aWersvcWersvcsy; "WerSvc\\WerSvcSystemPermissionsEvent"
0x18001dc53  xor     r8d, r8d; bInitialState
0x18001dc56  xor     edx, edx; bManualReset
0x18001dc58  lea     rcx, [rsp+1A0h+EventAttributes]; lpEventAttributes
0x18001dc5d  call    cs:__imp_CreateEventW
0x18001dc63  mov     rcx, [rsi+198h]; hObject
0x18001dc6a  mov     [rsi+198h], rax
0x18001dc71  lea     rax, [rcx+1]
0x18001dc75  cmp     rax, rdi
0x18001dc78  jbe     short loc_18001DC80
0x18001dc7a  call    cs:__imp_CloseHandle
0x18001dc80  mov     rax, [rsi+198h]
0x18001dc87  add     rax, rdi
0x18001dc8a  cmp     rax, rdi
0x18001dc8d  jbe     loc_18001DEB7
0x18001dc93  cmp     [r15], r14
0x18001dc96  jz      short loc_18001DC9D
0x18001dc98  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001dc9d  xorps   xmm0, xmm0
0x18001dca0  movups  xmmword ptr [rsp+1A0h+DestinationString.Length], xmm0
0x18001dca5  lea     rdx, aWindowserrorre; "\\WindowsErrorReportingServicePort"
0x18001dcac  lea     rcx, [rsp+1A0h+DestinationString]; DestinationString
0x18001dcb1  call    cs:__imp_RtlInitUnicodeString
0x18001dcb7  lea     rbx, aDPDOiciGaNuAOi; "D:P(D;OICI;GA;;;NU)(A;OICI;GR;;;AU)(A;O"...
0x18001dcbe  mov     [rsp+1A0h+var_15C], r14d
0x18001dcc3  mov     [rsp+1A0h+var_160], 4
0x18001dccb  lea     rax, [rsp+1A0h+var_160]
0x18001dcd0  mov     [rsp+1A0h+pcbData], rax; pcbData
0x18001dcd5  lea     rax, [rsp+1A0h+var_15C]
0x18001dcda  mov     [rsp+1A0h+pvData], rax; pvData
0x18001dcdf  mov     [rsp+1A0h+pdwType], r14; pdwType
0x18001dce4  mov     r9d, r12d; dwFlags
0x18001dce7  lea     r8, aAllownetworkus; "AllowNetworkUserConnections"
0x18001dcee  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows\\Windows E"...
0x18001dcf5  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001dcfc  call    cs:__imp_RegGetValueW
0x18001dd02  test    eax, eax
0x18001dd04  jnz     short loc_18001DD1F
0x18001dd06  cmp     [rsp+1A0h+var_160], 4
0x18001dd0b  jnz     short loc_18001DD1F
0x18001dd0d  lea     rax, aDPAOiciGrAuAOi; "D:P(A;OICI;GR;;;AU)(A;OICI;GR;;;BG)(A;O"...
0x18001dd14  cmp     [rsp+1A0h+var_15C], edi
0x18001dd18  cmovnz  rax, rbx
0x18001dd1c  mov     rbx, rax
0x18001dd1f  lea     rcx, [rsp+1A0h+var_148]
0x18001dd24  call    ??$replace@XU?$generic_delete@XU?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@utl@@YAPEAPEAXAEAV?$unique_ptr@XU?$generic_delete@XU?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@0@@Z
0x18001dd29  mov     r8, rax; SecurityDescriptor
0x18001dd2c  xor     r9d, r9d; SecurityDescriptorSize
0x18001dd2f  mov     edx, edi; StringSDRevision
0x18001dd31  mov     rcx, rbx; StringSecurityDescriptor
0x18001dd34  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001dd3a  test    eax, eax
0x18001dd3c  jz      loc_18001DC0E
0x18001dd42  mov     [rbp+0A0h+var_118], 30h ; '0'
0x18001dd4a  mov     [rbp+0A0h+var_100], r14
0x18001dd4e  mov     [rbp+0A0h+var_110], r14
0x18001dd52  lea     rax, [rsp+1A0h+DestinationString]
0x18001dd57  mov     [rbp+0A0h+var_108], rax
0x18001dd5b  mov     rax, [rsp+1A0h+var_148]
0x18001dd60  mov     [rbp+0A0h+var_F8], rax
0x18001dd64  mov     [rbp+0A0h+var_F0], r14
0x18001dd68  xor     edx, edx; Val
0x18001dd6a  lea     r8d, [rdx+48h]; Size
0x18001dd6e  lea     rcx, [rbp+0A0h+var_E0]; void *
0x18001dd72  call    memset_0
0x18001dd77  movaps  xmm0, [rbp+0A0h+var_E0]
0x18001dd7b  movaps  [rbp+0A0h+var_90], xmm0
0x18001dd7f  movaps  xmm1, [rbp+0A0h+var_D0]
0x18001dd83  movaps  [rbp+0A0h+var_80], xmm1
0x18001dd87  movaps  xmm0, [rbp+0A0h+var_C0]
0x18001dd8b  movaps  [rbp+0A0h+var_70], xmm0
0x18001dd8f  movaps  xmm1, [rbp+0A0h+var_B0]
0x18001dd93  movaps  [rbp+0A0h+var_60], xmm1
0x18001dd97  movsd   xmm0, [rbp+0A0h+var_A0]
0x18001dd9c  movsd   [rbp+0A0h+var_50], xmm0
0x18001dda1  mov     dword ptr [rbp+0A0h+var_90], 20000h
0x18001dda8  mov     qword ptr [rbp+0A0h+var_80], 578h
0x18001ddb0  mov     qword ptr [rbp+0A0h+var_80+8], r14
0x18001ddb4  mov     qword ptr [rbp+0A0h+var_70], 15E00h
0x18001ddbc  mov     rcx, [r15]; Handle
0x18001ddbf  mov     [r15], r14
0x18001ddc2  test    rcx, rcx
0x18001ddc5  jz      short loc_18001DDCD
0x18001ddc7  call    cs:__imp_NtClose
0x18001ddcd  lea     r8, [rbp+0A0h+var_90]
0x18001ddd1  lea     rdx, [rbp+0A0h+var_118]
0x18001ddd5  mov     rcx, r15
0x18001ddd8  call    cs:__imp_NtAlpcCreatePort
0x18001ddde  mov     ebx, eax
0x18001dde0  test    eax, eax
0x18001dde2  jns     short loc_18001DE13
0x18001dde4  bts     ebx, 1Ch
0x18001dde8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ddef  lea     rax, WPP_GLOBAL_Control
0x18001ddf6  cmp     rcx, rax
0x18001ddf9  jz      loc_18001DF07
0x18001ddff  test    [rcx+1Ch], dil
0x18001de03  jz      loc_18001DF07
0x18001de09  mov     edx, 4Ch ; 'L'
0x18001de0e  jmp     loc_18001DEF4
0x18001de13  mov     [rsp+1A0h+ThreadId], r14d
0x18001de18  mov     rax, [rsi+190h]
0x18001de1f  add     rax, rdi
0x18001de22  cmp     rax, rdi
0x18001de25  jbe     short loc_18001DE2C
0x18001de27  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001de2c  lea     rax, [rsp+1A0h+ThreadId]
0x18001de31  mov     [rsp+1A0h+pvData], rax; lpThreadId
0x18001de36  mov     dword ptr [rsp+1A0h+pdwType], r14d; dwCreationFlags
0x18001de3b  mov     r9, rsi; lpParameter
0x18001de3e  lea     r8, ?StaticLpcServerThread@CWerService@@CAKPEAX@Z; lpStartAddress
0x18001de45  xor     edx, edx; dwStackSize
0x18001de47  xor     ecx, ecx; lpThreadAttributes
0x18001de49  call    cs:__imp_CreateThread
0x18001de4f  mov     rcx, [rsi+190h]; hObject
0x18001de56  mov     [rsi+190h], rax
0x18001de5d  lea     rax, [rcx+1]
0x18001de61  cmp     rax, rdi
0x18001de64  jbe     short loc_18001DE6C
0x18001de66  call    cs:__imp_CloseHandle
0x18001de6c  mov     rax, [rsi+190h]
0x18001de73  add     rax, rdi
0x18001de76  cmp     rax, rdi
0x18001de79  jbe     loc_18001DC0E
0x18001de7f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001de86  lea     rax, WPP_GLOBAL_Control
0x18001de8d  cmp     rcx, rax
0x18001de90  jz      short loc_18001DEB2
0x18001de92  test    byte ptr [rcx+1Ch], 4
0x18001de96  jz      short loc_18001DEB2
0x18001de98  mov     edx, 4Dh ; 'M'
0x18001de9d  mov     r9d, [rsp+1A0h+ThreadId]
0x18001dea2  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x18001dea9  mov     rcx, [rcx+10h]
0x18001dead  call    WPP_SF_d
0x18001deb2  mov     ebx, r14d
0x18001deb5  jmp     short loc_18001DF17
0x18001deb7  call    cs:__imp_GetLastError
0x18001debd  mov     ebx, eax
0x18001debf  test    eax, eax
0x18001dec1  jle     short loc_18001DECC
0x18001dec3  movzx   ebx, ax
0x18001dec6  or      ebx, 80070000h
0x18001decc  mov     eax, 80004005h
  ... truncated ...
```
