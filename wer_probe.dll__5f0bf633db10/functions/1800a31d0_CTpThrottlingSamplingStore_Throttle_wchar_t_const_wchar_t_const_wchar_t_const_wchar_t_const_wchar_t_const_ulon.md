# CTpThrottlingSamplingStore::Throttle(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,ulong,int)

- ea: `0x1800a31d0`
- end: `0x1800a34c8`
- name: `?Throttle@CTpThrottlingSamplingStore@@SAJPEB_W0000KH@Z`
- size: `760`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *, const wchar_t *, const wchar_t *, LPCWSTR lpValueName, unsigned int, enum THROTTLE_NAMESPACE_LEVEL *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18009f8d4`

## callees

- `0x18000bc10`
- `0x18000c390`
- `0x18000dad0`
- `0x18000e7fc`
- `0x180013a20`
- `0x18001c6d8`
- `0x18001f8c8`
- `0x180027344`
- `0x1800a2d94`
- `0x1800a2f88`
- `0x1800a31d0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800a33af`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800a33af`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a3431`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a3431`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a3487`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a3487`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800a345c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800a345c`

## pseudocode

```c
__int64 __fastcall CTpThrottlingSamplingStore::Throttle(
        const wchar_t *a1,
        const wchar_t *a2,
        const wchar_t *a3,
        const wchar_t *a4,
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
        if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(lpSubKey)
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
0x1800a31d0  push    rbp
0x1800a31d2  push    rbx
0x1800a31d3  push    rsi
0x1800a31d4  push    rdi
0x1800a31d5  push    r12
0x1800a31d7  push    r13
0x1800a31d9  push    r14
0x1800a31db  push    r15
0x1800a31dd  lea     rbp, [rsp-7]
0x1800a31e2  sub     rsp, 98h
0x1800a31e9  mov     rdi, rcx
0x1800a31ec  mov     r15, r9
0x1800a31ef  lea     rcx, [rbp+3Fh+lpSubKey]; void *
0x1800a31f3  mov     r14, r8
0x1800a31f6  mov     rsi, rdx
0x1800a31f9  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800a31fe  mov     r13d, [rbp+3Fh+arg_28]
0x1800a3202  xor     ecx, ecx
0x1800a3204  mov     [rbp+3Fh+hKey], rcx
0x1800a3208  mov     qword ptr [rbp+3Fh+Data], rcx
0x1800a320c  mov     qword ptr [rbp+3Fh+SystemTimeAsFileTime.dwLowDateTime], rcx
0x1800a3210  lea     eax, [r13-1]
0x1800a3214  mov     [rbp+3Fh+dwDisposition], ecx
0x1800a3217  cmp     eax, 3E7h
0x1800a321c  jbe     short loc_1800A322E
0x1800a321e  cmp     r13d, 0FFFFFFFFh
0x1800a3222  jz      short loc_1800A322E
0x1800a3224  mov     ebx, 80070057h
0x1800a3229  jmp     loc_1800A34A0
0x1800a322e  mov     r12, [rbp+3Fh+lpValueName]
0x1800a3232  lea     rax, [rbp+3Fh+arg_28]
0x1800a3236  mov     [rsp+0D0h+lpSecurityAttributes], rax; int *
0x1800a323b  mov     r9, r15; wchar_t *
0x1800a323e  mov     eax, dword ptr [rbp+3Fh+arg_30]
0x1800a3241  mov     r8, r14; wchar_t *
0x1800a3244  mov     [rbp+3Fh+arg_28], ecx
0x1800a3247  mov     rdx, rsi; wchar_t *
0x1800a324a  mov     [rbp+3Fh+var_7C], ecx
0x1800a324d  mov     rcx, rdi; wchar_t *
0x1800a3250  mov     dword ptr [rsp+0D0h+samDesired], eax; enum THROTTLE_NAMESPACE_LEVEL *
0x1800a3254  mov     qword ptr [rsp+0D0h+dwOptions], r12; lpValueName
0x1800a3259  call    ?GetThrottlingState@CTpThrottlingSamplingStore@@CAJPEB_W0000HPEAH@Z; CTpThrottlingSamplingStore::GetThrottlingState(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,int,int *)
0x1800a325e  mov     ebx, eax
0x1800a3260  xor     eax, eax
0x1800a3262  test    ebx, ebx
0x1800a3264  js      loc_1800A34A0
0x1800a326a  lea     rax, [rbp+3Fh+var_7C]
0x1800a326e  mov     r9, r15; wchar_t *
0x1800a3271  mov     r8, r14; wchar_t *
0x1800a3274  mov     qword ptr [rsp+0D0h+dwOptions], rax; int *
0x1800a3279  mov     rdx, rsi; wchar_t *
0x1800a327c  mov     rcx, rdi; wchar_t *
0x1800a327f  call    ?GetSamplingState@CTpThrottlingSamplingStore@@CAJPEB_W000PEAHPEAW4THROTTLE_NAMESPACE_LEVEL@@@Z; CTpThrottlingSamplingStore::GetSamplingState(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,int *,THROTTLE_NAMESPACE_LEVEL *)
0x1800a3284  mov     ebx, eax
0x1800a3286  xor     eax, eax
0x1800a3288  test    ebx, ebx
0x1800a328a  js      loc_1800A34A0
0x1800a3290  cmp     [rbp+3Fh+arg_28], eax
0x1800a3293  jnz     loc_1800A34A0
0x1800a3299  lea     rdx, aSoftwareMicros_30; "SOFTWARE\\Microsoft\\TelemetryClient\\T"...
0x1800a32a0  lea     rcx, [rbp+3Fh+lpSubKey]
0x1800a32a4  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x1800a32a9  xor     ecx, ecx
0x1800a32ab  test    al, al
0x1800a32ad  jnz     short loc_1800A32B9
0x1800a32af  mov     ebx, 8007000Eh
0x1800a32b4  jmp     loc_1800A34A0
0x1800a32b9  test    rdi, rdi
0x1800a32bc  jz      short loc_1800A32E7
0x1800a32be  cmp     [rdi], cx
0x1800a32c1  jz      short loc_1800A32E7
0x1800a32c3  mov     edx, 5Ch ; '\'
0x1800a32c8  lea     rcx, [rbp+3Fh+lpSubKey]
0x1800a32cc  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x1800a32d1  test    al, al
0x1800a32d3  jz      short loc_1800A32AF
0x1800a32d5  mov     rdx, rdi
0x1800a32d8  lea     rcx, [rbp+3Fh+lpSubKey]
0x1800a32dc  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *)
0x1800a32e1  xor     ecx, ecx
0x1800a32e3  test    al, al
0x1800a32e5  jz      short loc_1800A32AF
0x1800a32e7  test    rsi, rsi
0x1800a32ea  jz      short loc_1800A3317
0x1800a32ec  cmp     [rsi], cx
0x1800a32ef  jz      short loc_1800A3317
0x1800a32f1  mov     edx, 5Ch ; '\'
0x1800a32f6  lea     rcx, [rbp+3Fh+lpSubKey]
0x1800a32fa  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x1800a32ff  test    al, al
0x1800a3301  jz      short loc_1800A32AF
0x1800a3303  mov     rdx, rsi
0x1800a3306  lea     rcx, [rbp+3Fh+lpSubKey]
0x1800a330a  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *)
0x1800a330f  xor     esi, esi
0x1800a3311  test    al, al
0x1800a3313  jnz     short loc_1800A3319
0x1800a3315  jmp     short loc_1800A32AF
0x1800a3317  xor     esi, esi
0x1800a3319  test    r14, r14
0x1800a331c  jz      short loc_1800A334E
0x1800a331e  cmp     [r14], si
0x1800a3322  jz      short loc_1800A334E
0x1800a3324  mov     edx, 5Ch ; '\'
0x1800a3329  lea     rcx, [rbp+3Fh+lpSubKey]
0x1800a332d  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x1800a3332  test    al, al
0x1800a3334  jz      loc_1800A32AF
0x1800a333a  mov     rdx, r14
0x1800a333d  lea     rcx, [rbp+3Fh+lpSubKey]
0x1800a3341  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *)
0x1800a3346  test    al, al
0x1800a3348  jz      loc_1800A32AF
0x1800a334e  test    r15, r15
0x1800a3351  jz      short loc_1800A3383
0x1800a3353  cmp     [r15], si
0x1800a3357  jz      short loc_1800A3383
0x1800a3359  mov     edx, 5Ch ; '\'
0x1800a335e  lea     rcx, [rbp+3Fh+lpSubKey]
0x1800a3362  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x1800a3367  test    al, al
0x1800a3369  jz      loc_1800A32AF
0x1800a336f  mov     rdx, r15
0x1800a3372  lea     rcx, [rbp+3Fh+lpSubKey]
0x1800a3376  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *)
0x1800a337b  test    al, al
0x1800a337d  jz      loc_1800A32AF
0x1800a3383  test    r12, r12
0x1800a3386  jz      short loc_1800A3393
0x1800a3388  cmp     [r12], si
0x1800a338d  jz      short loc_1800A3393
0x1800a338f  mov     edi, esi
0x1800a3391  jmp     short loc_1800A339F
0x1800a3393  mov     edi, 1
0x1800a3398  lea     r12, aThrottleexpiry; "ThrottleExpiryTime"
0x1800a339f  cmp     r13d, 0FFFFFFFFh
0x1800a33a3  jnz     short loc_1800A33AB
0x1800a33a5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a33a9  jmp     short loc_1800A33EB
0x1800a33ab  lea     rcx, [rbp+3Fh+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800a33af  call    cs:__imp_GetSystemTimeAsFileTime
0x1800a33b5  mov     r9, qword ptr [rbp+3Fh+SystemTimeAsFileTime.dwLowDateTime]
0x1800a33b9  lea     r8, [rbp+3Fh+Data]; unsigned __int64 *
0x1800a33bd  mov     rcx, r13; unsigned __int64
0x1800a33c0  mov     rdx, 0C92A69C000h; unsigned __int64
0x1800a33ca  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800a33cf  mov     ebx, eax
0x1800a33d1  test    eax, eax
0x1800a33d3  js      loc_1800A34A0
0x1800a33d9  mov     rax, qword ptr [rbp+3Fh+Data]
0x1800a33dd  add     rax, r9
0x1800a33e0  cmp     rax, r9
0x1800a33e3  jb      loc_1800A3493
0x1800a33e9  mov     ebx, esi
0x1800a33eb  lea     rcx, [rbp+3Fh+hKey]
0x1800a33ef  mov     qword ptr [rbp+3Fh+Data], rax
0x1800a33f3  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1800a33f8  neg     dword ptr [rbp+3Fh+arg_30]
0x1800a33fb  lea     rdx, [rbp+3Fh+dwDisposition]
0x1800a33ff  mov     [rsp+0D0h+lpdwDisposition], rdx; lpdwDisposition
0x1800a3404  mov     rdx, [rbp+3Fh+lpSubKey]; lpSubKey
0x1800a3408  sbb     rcx, rcx
0x1800a340b  mov     [rsp+0D0h+phkResult], rax; phkResult
0x1800a3410  neg     rcx
0x1800a3413  mov     [rsp+0D0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x1800a3418  add     rcx, 0FFFFFFFF80000001h; hKey
0x1800a341f  mov     dword ptr [rsp+0D0h+samDesired], 0F013Fh; samDesired
0x1800a3427  xor     r9d, r9d; lpClass
0x1800a342a  xor     r8d, r8d; Reserved
0x1800a342d  mov     [rsp+0D0h+dwOptions], esi; dwOptions
0x1800a3431  call    cs:__imp_RegCreateKeyExW
0x1800a3437  test    eax, eax
0x1800a3439  jz      short loc_1800A344C
0x1800a343b  jg      short loc_1800A3441
0x1800a343d  mov     ebx, eax
0x1800a343f  jmp     short loc_1800A34A0
0x1800a3441  movzx   ebx, ax
0x1800a3444  or      ebx, 80070000h
0x1800a344a  jmp     short loc_1800A34A0
0x1800a344c  test    edi, edi
0x1800a344e  jz      short loc_1800A3466
0x1800a3450  cmp     [rbp+3Fh+dwDisposition], 2
0x1800a3454  jnz     short loc_1800A3466
0x1800a3456  mov     rcx, [rbp+3Fh+hKey]; hKey
0x1800a345a  xor     edx, edx; lpSubKey
0x1800a345c  call    cs:__imp_RegDeleteTreeW
0x1800a3462  test    eax, eax
0x1800a3464  jnz     short loc_1800A343B
0x1800a3466  mov     rcx, [rbp+3Fh+hKey]; hKey
0x1800a346a  lea     rax, [rbp+3Fh+Data]
0x1800a346e  mov     dword ptr [rsp+0D0h+samDesired], 8; cbData
0x1800a3476  mov     r9d, 0Bh; dwType
0x1800a347c  xor     r8d, r8d; Reserved
0x1800a347f  mov     qword ptr [rsp+0D0h+dwOptions], rax; lpData
0x1800a3484  mov     rdx, r12; lpValueName
0x1800a3487  call    cs:__imp_RegSetValueExW
0x1800a348d  test    eax, eax
0x1800a348f  jz      short loc_1800A34A0
0x1800a3491  jmp     short loc_1800A343B
0x1800a3493  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a3497  mov     ebx, 80070216h
0x1800a349c  mov     qword ptr [rbp+3Fh+Data], rax
0x1800a34a0  lea     rcx, [rbp+3Fh+hKey]
0x1800a34a4  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x1800a34a9  lea     rcx, [rbp+3Fh+lpSubKey]; void *
0x1800a34ad  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800a34b2  mov     eax, ebx
0x1800a34b4  add     rsp, 98h
0x1800a34bb  pop     r15
0x1800a34bd  pop     r14
0x1800a34bf  pop     r13
0x1800a34c1  pop     r12
0x1800a34c3  pop     rdi
0x1800a34c4  pop     rsi
0x1800a34c5  pop     rbx
0x1800a34c6  pop     rbp
0x1800a34c7  retn
```
