# CWebPlatStorageBroker::GetWebPlatStorageManager(IWebPlatStorageCom * *)

- ea: `0x1800513d0`
- end: `0x1800514ad`
- name: `?GetWebPlatStorageManager@CWebPlatStorageBroker@@UEAAJPEAPEAUIWebPlatStorageCom@@@Z`
- size: `221`
- prototype: `int(CWebPlatStorageBroker *__hidden this, struct IWebPlatStorageCom **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800513d0`
- `0x1800514b4`
- `0x180063500`
- `0x180071508`
- `0x180080fb0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005140a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005140a`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180051418`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180051418`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005144b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005144b`

## string_xrefs

- `0x18005147b`: `onecoreuap\inetcore\webplatstorageserver\dll\broker.cpp`
- `0x18005149a`: `onecoreuap\inetcore\webplatstorageserver\dll\broker.cpp`

## pseudocode

```c
__int64 __fastcall CWebPlatStorageBroker::GetWebPlatStorageManager(CWebPlatStorageBroker *this, LPVOID *a2)
{
  int Instance; // ebx
  HANDLE CurrentProcess; // rax
  const char *v5; // r9
  DWORD v6; // r8d
  __int64 v8; // rdx
  int ppv; // [rsp+20h] [rbp-28h]
  WINBOOL Wow64Process; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a2 = 0;
  Instance = CheckComClientUserSid();
  if ( Instance < 0 )
  {
    v8 = 99;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\dll\\broker.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
    return (unsigned int)Instance;
  }
  Wow64Process = 0;
  CurrentProcess = GetCurrentProcess();
  if ( IsWow64Process(CurrentProcess, &Wow64Process) )
  {
    v6 = 4;
    if ( Wow64Process )
      v6 = 524292;
    Instance = CoCreateInstance(&CLSID_WebPlatStorageCom, 0, v6, &GUID_0d67d0a5_4736_4a43_b642_e77f2105b3e2, a2);
    if ( Instance >= 0 )
      return 0;
    v8 = 110;
    goto LABEL_8;
  }
  return wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x66,
           (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\dll\\broker.cpp",
           v5);
}

```

## disassembly

```asm
0x1800513d0  mov     [rsp+arg_0], rbx
0x1800513d5  push    rdi
0x1800513d6  sub     rsp, 40h
0x1800513da  mov     rax, cs:__security_cookie
0x1800513e1  xor     rax, rsp
0x1800513e4  mov     [rsp+48h+var_10], rax
0x1800513e9  mov     rdi, rdx
0x1800513ec  mov     qword ptr [rdx], 0
0x1800513f3  call    CheckComClientUserSid
0x1800513f8  mov     ebx, eax
0x1800513fa  test    eax, eax
0x1800513fc  js      loc_18005148E
0x180051402  mov     [rsp+48h+Wow64Process], 0
0x18005140a  call    cs:__imp_GetCurrentProcess
0x180051410  mov     rcx, rax; hProcess
0x180051413  lea     rdx, [rsp+48h+Wow64Process]; Wow64Process
0x180051418  call    cs:__imp_IsWow64Process
0x18005141e  test    eax, eax
0x180051420  jz      short loc_180051495
0x180051422  cmp     [rsp+48h+Wow64Process], 0
0x180051427  lea     r9, _GUID_0d67d0a5_4736_4a43_b642_e77f2105b3e2; riid
0x18005142e  mov     eax, 80004h
0x180051433  mov     qword ptr [rsp+48h+ppv], rdi; int
0x180051438  mov     r8d, 4
0x18005143e  lea     rcx, CLSID_WebPlatStorageCom; rclsid
0x180051445  cmovnz  r8d, eax; dwClsContext
0x180051449  xor     edx, edx; pUnkOuter
0x18005144b  call    cs:__imp_CoCreateInstance
0x180051451  mov     ebx, eax
0x180051453  test    eax, eax
0x180051455  js      short loc_180051471
0x180051457  xor     eax, eax
0x180051459  mov     rcx, [rsp+48h+var_10]
0x18005145e  xor     rcx, rsp; StackCookie
0x180051461  call    __security_check_cookie
0x180051466  mov     rbx, [rsp+48h+arg_0]
0x18005146b  add     rsp, 40h
0x18005146f  pop     rdi
0x180051470  retn
0x180051471  mov     edx, 6Eh ; 'n'; void *
0x180051476  mov     rcx, [rsp+48h]; this
0x18005147b  lea     r8, aOnecoreuapInet_26; "onecoreuap\\inetcore\\webplatstorageser"...
0x180051482  mov     r9d, ebx; char *
0x180051485  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005148a  mov     eax, ebx
0x18005148c  jmp     short loc_180051459
0x18005148e  mov     edx, 63h ; 'c'
0x180051493  jmp     short loc_180051476
0x180051495  mov     rcx, [rsp+48h]; this
0x18005149a  lea     r8, aOnecoreuapInet_26; "onecoreuap\\inetcore\\webplatstorageser"...
0x1800514a1  mov     edx, 66h ; 'f'; void *
0x1800514a6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800514ab  jmp     short loc_180051459
```
