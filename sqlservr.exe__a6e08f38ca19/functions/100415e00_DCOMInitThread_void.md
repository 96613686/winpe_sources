# DCOMInitThread(void *)

- ea: `0x100415e00`
- end: `0x100415f40`
- name: `?DCOMInitThread@@YAKPEAX@Z`
- size: `320`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x100401580`
- `0x100415e00`
- `0x10041eac0`
- `0x10044aad0`

## import_xrefs

- `KERNEL32!Sleep` at `0x100415f17`
- `KERNEL32!Sleep` at `0x100415f17`
- `KERNEL32!SetEvent` at `0x100415f0c`
- `KERNEL32!SetEvent` at `0x100415f0c`
- `ole32!CoInitializeSecurity` at `0x100415eac`
- `ole32!CoInitializeSecurity` at `0x100415eac`
- `ole32!CoInitializeEx` at `0x100415e26`
- `ole32!CoInitializeEx` at `0x100415e26`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x100415e37`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x100415ebd`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x100415e37`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x100415ebd`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100415e3d`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100415ec3`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100415e3d`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100415ec3`

## string_xrefs

- `0x100415ed4`: `CoInitializeSecurity failure.`

## pseudocode

```c
__int64 __fastcall DCOMInitThread(LPVOID lpThreadParameter)
{
  HRESULT v2; // eax
  HRESULT v3; // ebx
  struct __crt_locale_pointers *DefaultLocale; // rax
  int v5; // eax
  char *v6; // rcx
  HRESULT v7; // eax
  HRESULT v8; // ebx
  struct __crt_locale_pointers *v9; // rax
  int v10; // eax
  char *v11; // rcx
  DWORD dwImpLevela; // [rsp+28h] [rbp-440h]
  __int64 dwImpLevel; // [rsp+28h] [rbp-440h]
  char Buffer[512]; // [rsp+50h] [rbp-418h] BYREF
  char v16[512]; // [rsp+250h] [rbp-218h] BYREF

  v2 = CoInitializeEx(0, 0);
  v3 = v2;
  if ( v2 < 0 )
  {
    _mm_lfence();
    SetWin32ExitCode(v2);
    DefaultLocale = GetDefaultLocale();
    dwImpLevela = v3;
    v5 = StringCchPrintf_lA(Buffer, 0x200u, "%hs (HRESULT 0x%x)", DefaultLocale, "CoInitializeEx failure.", dwImpLevela);
    v6 = "CoInitializeEx failure.";
    if ( v5 >= 0 )
      v6 = Buffer;
    FailAndExit(v6);
  }
  v7 = CoInitializeSecurity(0, -1, 0, 0, 6u, 2u, 0, 0x40u, 0);
  v8 = v7;
  if ( v7 < 0 )
  {
    _mm_lfence();
    SetWin32ExitCode(v7);
    v9 = GetDefaultLocale();
    LODWORD(dwImpLevel) = v8;
    v10 = StringCchPrintf_lA(v16, 0x200u, "%hs (HRESULT 0x%x)", v9, "CoInitializeSecurity failure.", dwImpLevel);
    v11 = "CoInitializeSecurity failure.";
    if ( v10 >= 0 )
      v11 = v16;
    FailAndExit(v11);
  }
  SetEvent(lpThreadParameter);
  Sleep(0xFFFFFFFF);
  return 0;
}

```

## disassembly

```asm
0x100415e00  mov     [rsp+arg_8], rbx
0x100415e05  push    rdi
0x100415e06  sub     rsp, 460h
0x100415e0d  mov     rax, cs:__security_cookie
0x100415e14  xor     rax, rsp
0x100415e17  mov     [rsp+468h+var_18], rax
0x100415e1f  mov     rdi, rcx
0x100415e22  xor     edx, edx; dwCoInit
0x100415e24  xor     ecx, ecx; pvReserved
0x100415e26  call    cs:__imp_CoInitializeEx
0x100415e2c  mov     ebx, eax
0x100415e2e  test    eax, eax
0x100415e30  jns     short loc_100415E7D
0x100415e32  lfence
0x100415e35  mov     ecx, eax
0x100415e37  call    cs:__imp_?SetWin32ExitCode@@YAXK@Z; SetWin32ExitCode(ulong)
0x100415e3d  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x100415e43  mov     dword ptr [rsp+468h+dwImpLevel], ebx
0x100415e47  lea     r8, aHsHresult0xX; "%hs (HRESULT 0x%x)"
0x100415e4e  lea     rbx, aCoinitializeex; "CoInitializeEx failure."
0x100415e55  mov     r9, rax; struct __crt_locale_pointers *
0x100415e58  mov     edx, 200h; unsigned __int64
0x100415e5d  mov     qword ptr [rsp+468h+dwAuthnLevel], rbx
0x100415e62  lea     rcx, [rsp+468h+Buffer]; Buffer
0x100415e67  call    ?StringCchPrintf_lA@@YAJPEAD_KPEBDPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lA(char *,unsigned __int64,char const *,__crt_locale_pointers *,...)
0x100415e6c  mov     rcx, rbx
0x100415e6f  test    eax, eax
0x100415e71  js      short loc_100415E78
0x100415e73  lea     rcx, [rsp+468h+Buffer]; char *
0x100415e78  call    ?FailAndExit@@YAXPEBD@Z; FailAndExit(char const *)
0x100415e7d  xor     eax, eax
0x100415e7f  xor     r9d, r9d; pReserved1
0x100415e82  mov     [rsp+468h+pReserved3], rax; pReserved3
0x100415e87  xor     r8d, r8d; asAuthSvc
0x100415e8a  mov     [rsp+468h+dwCapabilities], 40h ; '@'; dwCapabilities
0x100415e92  xor     ecx, ecx; pSecDesc
0x100415e94  mov     [rsp+468h+pAuthList], rax; pAuthList
0x100415e99  mov     dword ptr [rsp+468h+dwImpLevel], 2; dwImpLevel
0x100415ea1  lea     edx, [rax-1]; cAuthSvc
0x100415ea4  mov     [rsp+468h+dwAuthnLevel], 6; dwAuthnLevel
0x100415eac  call    cs:__imp_CoInitializeSecurity
0x100415eb2  mov     ebx, eax
0x100415eb4  test    eax, eax
0x100415eb6  jns     short loc_100415F09
0x100415eb8  lfence
0x100415ebb  mov     ecx, eax
0x100415ebd  call    cs:__imp_?SetWin32ExitCode@@YAXK@Z; SetWin32ExitCode(ulong)
0x100415ec3  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x100415ec9  mov     dword ptr [rsp+468h+dwImpLevel], ebx
0x100415ecd  lea     r8, aHsHresult0xX; "%hs (HRESULT 0x%x)"
0x100415ed4  lea     rbx, aCoinitializese; "CoInitializeSecurity failure."
0x100415edb  mov     r9, rax; struct __crt_locale_pointers *
0x100415ede  mov     edx, 200h; unsigned __int64
0x100415ee3  mov     qword ptr [rsp+468h+dwAuthnLevel], rbx
0x100415ee8  lea     rcx, [rsp+468h+var_218]; Buffer
0x100415ef0  call    ?StringCchPrintf_lA@@YAJPEAD_KPEBDPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lA(char *,unsigned __int64,char const *,__crt_locale_pointers *,...)
0x100415ef5  mov     rcx, rbx
0x100415ef8  test    eax, eax
0x100415efa  js      short loc_100415F04
0x100415efc  lea     rcx, [rsp+468h+var_218]; char *
0x100415f04  call    ?FailAndExit@@YAXPEBD@Z; FailAndExit(char const *)
0x100415f09  mov     rcx, rdi; hEvent
0x100415f0c  call    cs:__imp_SetEvent
0x100415f12  mov     ecx, 0FFFFFFFFh; dwMilliseconds
0x100415f17  call    cs:__imp_Sleep
0x100415f1d  xor     eax, eax
0x100415f1f  mov     rcx, [rsp+468h+var_18]
0x100415f27  xor     rcx, rsp; StackCookie
0x100415f2a  call    __security_check_cookie
0x100415f2f  mov     rbx, [rsp+468h+arg_8]
0x100415f37  add     rsp, 460h
0x100415f3e  pop     rdi
0x100415f3f  retn
```
