# CTpThrottlingSamplingStore::Throttle(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,ulong,int)

- ea: `0x1800a7df0`
- end: `0x1800a8101`
- name: `?Throttle@CTpThrottlingSamplingStore@@SAJPEB_W0000KH@Z`
- size: `785`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *, const wchar_t *, const wchar_t *, LPCWSTR lpValueName, unsigned int, enum THROTTLE_NAMESPACE_LEVEL *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a4314`

## callees

- `0x18000cf50`
- `0x18000da00`
- `0x18000db80`
- `0x180010280`
- `0x1800172c0`
- `0x18001cb20`
- `0x1800201f0`
- `0x1800282e8`
- `0x1800a7948`
- `0x1800a7b5c`
- `0x1800a7df0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800a7fcf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800a7fcf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a8057`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a8057`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a80b9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a80b9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800a8088`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800a8088`

## pseudocode

```c
__int64 __fastcall CTpThrottlingSamplingStore::Throttle(
        wchar_t *a1,
        wchar_t *a2,
        wchar_t *a3,
        wchar_t *a4,
        LPCWSTR lpValueName,
        unsigned int a6,
        enum THROTTLE_NAMESPACE_LEVEL *a7)
{
  unsigned __int64 v11; // r13
  signed int ThrottlingState; // ebx
  const WCHAR *v13; // r12
  int v14; // edi
  __int64 v15; // rax
  unsigned __int64 v16; // r9
  HKEY *phkResult; // rax
  bool v18; // cf
  LSTATUS v19; // eax
  bool v20; // cc
  enum THROTTLE_NAMESPACE_LEVEL *samDesired; // [rsp+28h] [rbp-69h]
  DWORD dwDisposition; // [rsp+50h] [rbp-41h] BYREF
  int v24; // [rsp+54h] [rbp-3Dh] BYREF
  BYTE Data[8]; // [rsp+58h] [rbp-39h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-31h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+68h] [rbp-29h] BYREF
  LPCWSTR lpSubKey[12]; // [rsp+70h] [rbp-21h] BYREF

  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpSubKey);
  v11 = a6;
  hKey = 0;
  *(_QWORD *)Data = 0;
  SystemTimeAsFileTime = 0;
  dwDisposition = 0;
  if ( a6 - 1 <= 0x3E7 || a6 == -1 )
  {
    v13 = lpValueName;
    a6 = 0;
    v24 = 0;
    ThrottlingState = CTpThrottlingSamplingStore::GetThrottlingState(a1, a2, a3, a4, lpValueName, (int)a7, (int *)&a6);
    if ( ThrottlingState >= 0 )
    {
      ThrottlingState = CTpThrottlingSamplingStore::GetSamplingState(a1, a2, a3, a4, &v24, samDesired);
      if ( ThrottlingState >= 0 && !a6 )
      {
        if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                lpSubKey,
                                L"SOFTWARE\\Microsoft\\TelemetryClient\\ThrottleStore")
          && (!a1
           || !*a1
           || (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                                 lpSubKey,
                                 92)
           && (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                                 lpSubKey,
                                 a1))
          && (!a2
           || !*a2
           || (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                                 lpSubKey,
                                 92)
           && (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                                 lpSubKey,
                                 a2))
          && (!a3
           || !*a3
           || (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                                 lpSubKey,
                                 92)
           && (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                                 lpSubKey,
                                 a3))
          && (!a4
           || !*a4
           || (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                                 lpSubKey,
                                 92)
           && (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                                 lpSubKey,
                                 a4)) )
        {
          if ( lpValueName && *lpValueName )
          {
            v14 = 0;
          }
          else
          {
            v14 = 1;
            v13 = L"ThrottleExpiryTime";
          }
          if ( (_DWORD)v11 == -1 )
          {
            v15 = -1;
          }
          else
          {
            GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
            ThrottlingState = ULongLongMult(v11, 0xC92A69C000uLL, (unsigned __int64 *)Data);
            if ( ThrottlingState < 0 )
              goto LABEL_44;
            v15 = v16 + *(_QWORD *)Data;
            if ( v16 + *(_QWORD *)Data < v16 )
            {
              ThrottlingState = -2147024362;
              *(_QWORD *)Data = -1;
              goto LABEL_44;
            }
            ThrottlingState = 0;
          }
          *(_QWORD *)Data = v15;
          phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
          v18 = (_DWORD)a7 != 0;
          LODWORD(a7) = -(int)a7;
          v19 = RegCreateKeyExW(
                  (HKEY)(v18 - 0x7FFFFFFFLL),
                  lpSubKey[0],
                  0,
                  0,
                  0,
                  0xF013Fu,
                  0,
                  phkResult,
                  &dwDisposition);
          v20 = v19 <= 0;
          if ( v19
            || v14 && dwDisposition == 2 && (v19 = RegDeleteTreeW(hKey, 0), v20 = v19 <= 0, v19)
            || (v19 = RegSetValueExW(hKey, v13, 0, 0xBu, Data, 8u), v20 = v19 <= 0, v19) )
          {
            if ( v20 )
              ThrottlingState = v19;
            else
              ThrottlingState = (unsigned __int16)v19 | 0x80070000;
          }
        }
        else
        {
          ThrottlingState = -2147024882;
        }
      }
    }
  }
  else
  {
    ThrottlingState = -2147024809;
  }
LABEL_44:
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpSubKey);
  return (unsigned int)ThrottlingState;
}

```

## disassembly

```asm
0x1800a7df0  push    rbp
0x1800a7df2  push    rbx
0x1800a7df3  push    rsi
0x1800a7df4  push    rdi
0x1800a7df5  push    r12
0x1800a7df7  push    r13
0x1800a7df9  push    r14
0x1800a7dfb  push    r15
0x1800a7dfd  lea     rbp, [rsp-7]
0x1800a7e02  sub     rsp, 98h
0x1800a7e09  mov     rdi, rcx
0x1800a7e0c  mov     r15, r9
0x1800a7e0f  lea     rcx, [rbp+3Fh+lpSubKey]; void *
0x1800a7e13  mov     r14, r8
0x1800a7e16  mov     rsi, rdx
0x1800a7e19  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800a7e1e  mov     r13d, [rbp+3Fh+arg_28]
0x1800a7e22  xor     ecx, ecx
0x1800a7e24  mov     [rbp+3Fh+hKey], rcx
0x1800a7e28  mov     qword ptr [rbp+3Fh+Data], rcx
0x1800a7e2c  mov     qword ptr [rbp+3Fh+SystemTimeAsFileTime.dwLowDateTime], rcx
0x1800a7e30  lea     eax, [r13-1]
0x1800a7e34  mov     [rbp+3Fh+dwDisposition], ecx
0x1800a7e37  cmp     eax, 3E7h
0x1800a7e3c  jbe     short loc_1800A7E4E
0x1800a7e3e  cmp     r13d, 0FFFFFFFFh
0x1800a7e42  jz      short loc_1800A7E4E
0x1800a7e44  mov     ebx, 80070057h
0x1800a7e49  jmp     loc_1800A80D8
0x1800a7e4e  mov     r12, [rbp+3Fh+lpValueName]
0x1800a7e52  lea     rax, [rbp+3Fh+arg_28]
0x1800a7e56  mov     [rsp+0D0h+lpSecurityAttributes], rax; int *
0x1800a7e5b  mov     r9, r15; wchar_t *
0x1800a7e5e  mov     eax, dword ptr [rbp+3Fh+arg_30]
0x1800a7e61  mov     r8, r14; wchar_t *
0x1800a7e64  mov     [rbp+3Fh+arg_28], ecx
0x1800a7e67  mov     rdx, rsi; wchar_t *
0x1800a7e6a  mov     [rbp+3Fh+var_7C], ecx
0x1800a7e6d  mov     rcx, rdi; wchar_t *
0x1800a7e70  mov     dword ptr [rsp+0D0h+samDesired], eax; enum THROTTLE_NAMESPACE_LEVEL *
0x1800a7e74  mov     qword ptr [rsp+0D0h+dwOptions], r12; lpValueName
0x1800a7e79  call    ?GetThrottlingState@CTpThrottlingSamplingStore@@CAJPEB_W0000HPEAH@Z; CTpThrottlingSamplingStore::GetThrottlingState(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,int,int *)
0x1800a7e7e  mov     ebx, eax
0x1800a7e80  xor     eax, eax
0x1800a7e82  test    ebx, ebx
0x1800a7e84  js      loc_1800A80D8
0x1800a7e8a  lea     rax, [rbp+3Fh+var_7C]
0x1800a7e8e  mov     r9, r15; wchar_t *
0x1800a7e91  mov     r8, r14; wchar_t *
0x1800a7e94  mov     qword ptr [rsp+0D0h+dwOptions], rax; int *
0x1800a7e99  mov     rdx, rsi; wchar_t *
0x1800a7e9c  mov     rcx, rdi; wchar_t *
0x1800a7e9f  call    ?GetSamplingState@CTpThrottlingSamplingStore@@CAJPEB_W000PEAHPEAW4THROTTLE_NAMESPACE_LEVEL@@@Z; CTpThrottlingSamplingStore::GetSamplingState(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,int *,THROTTLE_NAMESPACE_LEVEL *)
0x1800a7ea4  mov     ebx, eax
0x1800a7ea6  xor     eax, eax
0x1800a7ea8  test    ebx, ebx
0x1800a7eaa  js      loc_1800A80D8
0x1800a7eb0  cmp     [rbp+3Fh+arg_28], eax
0x1800a7eb3  jnz     loc_1800A80D8
0x1800a7eb9  lea     rdx, aSoftwareMicros_31; "SOFTWARE\\Microsoft\\TelemetryClient\\T"...
0x1800a7ec0  lea     rcx, [rbp+3Fh+lpSubKey]
0x1800a7ec4  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x1800a7ec9  xor     ecx, ecx
0x1800a7ecb  test    al, al
0x1800a7ecd  jnz     short loc_1800A7ED9
0x1800a7ecf  mov     ebx, 8007000Eh
0x1800a7ed4  jmp     loc_1800A80D8
0x1800a7ed9  test    rdi, rdi
0x1800a7edc  jz      short loc_1800A7F07
0x1800a7ede  cmp     [rdi], cx
0x1800a7ee1  jz      short loc_1800A7F07
0x1800a7ee3  mov     edx, 5Ch ; '\'
0x1800a7ee8  lea     rcx, [rbp+3Fh+lpSubKey]
0x1800a7eec  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x1800a7ef1  test    al, al
0x1800a7ef3  jz      short loc_1800A7ECF
0x1800a7ef5  mov     rdx, rdi
0x1800a7ef8  lea     rcx, [rbp+3Fh+lpSubKey]
0x1800a7efc  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *)
0x1800a7f01  xor     ecx, ecx
0x1800a7f03  test    al, al
0x1800a7f05  jz      short loc_1800A7ECF
0x1800a7f07  test    rsi, rsi
0x1800a7f0a  jz      short loc_1800A7F37
0x1800a7f0c  cmp     [rsi], cx
0x1800a7f0f  jz      short loc_1800A7F37
0x1800a7f11  mov     edx, 5Ch ; '\'
0x1800a7f16  lea     rcx, [rbp+3Fh+lpSubKey]
0x1800a7f1a  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x1800a7f1f  test    al, al
0x1800a7f21  jz      short loc_1800A7ECF
0x1800a7f23  mov     rdx, rsi
0x1800a7f26  lea     rcx, [rbp+3Fh+lpSubKey]
0x1800a7f2a  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *)
0x1800a7f2f  xor     esi, esi
0x1800a7f31  test    al, al
0x1800a7f33  jnz     short loc_1800A7F39
0x1800a7f35  jmp     short loc_1800A7ECF
0x1800a7f37  xor     esi, esi
0x1800a7f39  test    r14, r14
0x1800a7f3c  jz      short loc_1800A7F6E
0x1800a7f3e  cmp     [r14], si
0x1800a7f42  jz      short loc_1800A7F6E
0x1800a7f44  mov     edx, 5Ch ; '\'
0x1800a7f49  lea     rcx, [rbp+3Fh+lpSubKey]
0x1800a7f4d  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x1800a7f52  test    al, al
0x1800a7f54  jz      loc_1800A7ECF
0x1800a7f5a  mov     rdx, r14
0x1800a7f5d  lea     rcx, [rbp+3Fh+lpSubKey]
0x1800a7f61  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *)
0x1800a7f66  test    al, al
0x1800a7f68  jz      loc_1800A7ECF
0x1800a7f6e  test    r15, r15
0x1800a7f71  jz      short loc_1800A7FA3
0x1800a7f73  cmp     [r15], si
0x1800a7f77  jz      short loc_1800A7FA3
0x1800a7f79  mov     edx, 5Ch ; '\'
0x1800a7f7e  lea     rcx, [rbp+3Fh+lpSubKey]
0x1800a7f82  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x1800a7f87  test    al, al
0x1800a7f89  jz      loc_1800A7ECF
0x1800a7f8f  mov     rdx, r15
0x1800a7f92  lea     rcx, [rbp+3Fh+lpSubKey]
0x1800a7f96  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *)
0x1800a7f9b  test    al, al
0x1800a7f9d  jz      loc_1800A7ECF
0x1800a7fa3  test    r12, r12
0x1800a7fa6  jz      short loc_1800A7FB3
0x1800a7fa8  cmp     [r12], si
0x1800a7fad  jz      short loc_1800A7FB3
0x1800a7faf  mov     edi, esi
0x1800a7fb1  jmp     short loc_1800A7FBF
0x1800a7fb3  mov     edi, 1
0x1800a7fb8  lea     r12, aThrottleexpiry; "ThrottleExpiryTime"
0x1800a7fbf  cmp     r13d, 0FFFFFFFFh
0x1800a7fc3  jnz     short loc_1800A7FCB
0x1800a7fc5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a7fc9  jmp     short loc_1800A8011
0x1800a7fcb  lea     rcx, [rbp+3Fh+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800a7fcf  call    cs:__imp_GetSystemTimeAsFileTime
0x1800a7fd6  nop     dword ptr [rax+rax+00h]
0x1800a7fdb  mov     r9, qword ptr [rbp+3Fh+SystemTimeAsFileTime.dwLowDateTime]
0x1800a7fdf  lea     r8, [rbp+3Fh+Data]; unsigned __int64 *
0x1800a7fe3  mov     rcx, r13; unsigned __int64
0x1800a7fe6  mov     rdx, 0C92A69C000h; unsigned __int64
0x1800a7ff0  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800a7ff5  mov     ebx, eax
0x1800a7ff7  test    eax, eax
0x1800a7ff9  js      loc_1800A80D8
0x1800a7fff  mov     rax, qword ptr [rbp+3Fh+Data]
0x1800a8003  add     rax, r9
0x1800a8006  cmp     rax, r9
0x1800a8009  jb      loc_1800A80CB
0x1800a800f  mov     ebx, esi
0x1800a8011  lea     rcx, [rbp+3Fh+hKey]
0x1800a8015  mov     qword ptr [rbp+3Fh+Data], rax
0x1800a8019  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1800a801e  neg     dword ptr [rbp+3Fh+arg_30]
0x1800a8021  lea     rdx, [rbp+3Fh+dwDisposition]
0x1800a8025  mov     [rsp+0D0h+lpdwDisposition], rdx; lpdwDisposition
0x1800a802a  mov     rdx, [rbp+3Fh+lpSubKey]; lpSubKey
0x1800a802e  sbb     rcx, rcx
0x1800a8031  mov     [rsp+0D0h+phkResult], rax; phkResult
0x1800a8036  neg     rcx
0x1800a8039  mov     [rsp+0D0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x1800a803e  add     rcx, 0FFFFFFFF80000001h; hKey
0x1800a8045  mov     dword ptr [rsp+0D0h+samDesired], 0F013Fh; samDesired
0x1800a804d  xor     r9d, r9d; lpClass
0x1800a8050  xor     r8d, r8d; Reserved
0x1800a8053  mov     [rsp+0D0h+dwOptions], esi; dwOptions
0x1800a8057  call    cs:__imp_RegCreateKeyExW
0x1800a805e  nop     dword ptr [rax+rax+00h]
0x1800a8063  test    eax, eax
0x1800a8065  jz      short loc_1800A8078
0x1800a8067  jg      short loc_1800A806D
0x1800a8069  mov     ebx, eax
0x1800a806b  jmp     short loc_1800A80D8
0x1800a806d  movzx   ebx, ax
0x1800a8070  or      ebx, 80070000h
0x1800a8076  jmp     short loc_1800A80D8
0x1800a8078  test    edi, edi
0x1800a807a  jz      short loc_1800A8098
0x1800a807c  cmp     [rbp+3Fh+dwDisposition], 2
0x1800a8080  jnz     short loc_1800A8098
0x1800a8082  mov     rcx, [rbp+3Fh+hKey]; hKey
0x1800a8086  xor     edx, edx; lpSubKey
0x1800a8088  call    cs:__imp_RegDeleteTreeW
0x1800a808f  nop     dword ptr [rax+rax+00h]
0x1800a8094  test    eax, eax
0x1800a8096  jnz     short loc_1800A8067
0x1800a8098  mov     rcx, [rbp+3Fh+hKey]; hKey
0x1800a809c  lea     rax, [rbp+3Fh+Data]
0x1800a80a0  mov     dword ptr [rsp+0D0h+samDesired], 8; cbData
0x1800a80a8  mov     r9d, 0Bh; dwType
0x1800a80ae  xor     r8d, r8d; Reserved
0x1800a80b1  mov     qword ptr [rsp+0D0h+dwOptions], rax; lpData
0x1800a80b6  mov     rdx, r12; lpValueName
0x1800a80b9  call    cs:__imp_RegSetValueExW
0x1800a80c0  nop     dword ptr [rax+rax+00h]
0x1800a80c5  test    eax, eax
0x1800a80c7  jz      short loc_1800A80D8
0x1800a80c9  jmp     short loc_1800A8067
0x1800a80cb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a80cf  mov     ebx, 80070216h
0x1800a80d4  mov     qword ptr [rbp+3Fh+Data], rax
0x1800a80d8  lea     rcx, [rbp+3Fh+hKey]
0x1800a80dc  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x1800a80e1  lea     rcx, [rbp+3Fh+lpSubKey]; void *
0x1800a80e5  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800a80ea  mov     eax, ebx
0x1800a80ec  add     rsp, 98h
0x1800a80f3  pop     r15
0x1800a80f5  pop     r14
0x1800a80f7  pop     r13
0x1800a80f9  pop     r12
0x1800a80fb  pop     rdi
0x1800a80fc  pop     rsi
0x1800a80fd  pop     rbx
0x1800a80fe  pop     rbp
0x1800a80ff  retn
```
