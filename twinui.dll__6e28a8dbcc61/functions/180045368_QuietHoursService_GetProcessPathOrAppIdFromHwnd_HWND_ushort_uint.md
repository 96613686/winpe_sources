# QuietHoursService::GetProcessPathOrAppIdFromHwnd(HWND__ *,ushort *,uint)

- ea: `0x180045368`
- end: `0x18004558b`
- name: `?GetProcessPathOrAppIdFromHwnd@QuietHoursService@@AEAAJPEAUHWND__@@PEAGI@Z`
- size: `547`
- prototype: `int(QuietHoursService *__hidden this, HWND, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800174b0`

## callees

- `0x180044e40`
- `0x180045368`
- `0x1800456b0`
- `0x180058a44`
- `0x1800e5344`
- `0x1800ead54`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180045434`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180045434`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045414`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045414`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800453c9`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004547e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800453c9`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004547e`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180045400`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180045400`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045514`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045543`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045559`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045514`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045543`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045559`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18004539a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18004539a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnumChildWindows` at `0x18004545a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnumChildWindows` at `0x18004545a`
- `api-ms-win-appmodel-runtime-l1-1-0!GetApplicationUserModelId` at `0x1800454a6`
- `api-ms-win-appmodel-runtime-l1-1-0!GetApplicationUserModelId` at `0x1800454e5`
- `api-ms-win-appmodel-runtime-l1-1-0!GetApplicationUserModelId` at `0x1800454a6`
- `api-ms-win-appmodel-runtime-l1-1-0!GetApplicationUserModelId` at `0x1800454e5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180045424`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180045424`

## string_xrefs

- `0x1800453a8`: `shell\twinui\quiethoursservice\lib\quiethoursservice.cpp`

## pseudocode

```c
__int64 __fastcall QuietHoursService::GetProcessPathOrAppIdFromHwnd(
        QuietHoursService *this,
        HWND a2,
        unsigned __int16 *a3)
{
  const char *v5; // r9
  wil::details *v7; // rcx
  HANDLE v8; // rbx
  unsigned int v9; // ebx
  wil::details *v10; // rcx
  unsigned int LastErrorFailHr; // edi
  LPWSTR FileNameW; // rax
  char *v13; // rdi
  PWSTR v14; // rbx
  LONG v15; // eax
  bool v16; // sf
  unsigned __int64 v17; // rax
  int v18; // edi
  DWORD dwSize; // [rsp+20h] [rbp-30h] BYREF
  LPARAM lParam; // [rsp+28h] [rbp-28h] BYREF
  char *v21; // [rsp+30h] [rbp-20h] BYREF
  PWSTR applicationUserModelId; // [rsp+38h] [rbp-18h] BYREF
  HANDLE v23[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  QuietHoursService *applicationUserModelIdLength; // [rsp+70h] [rbp+20h] BYREF
  DWORD dwProcessId; // [rsp+88h] [rbp+38h] BYREF

  applicationUserModelIdLength = this;
  dwProcessId = 0;
  if ( !GetWindowThreadProcessId(a2, &dwProcessId) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xAD,
             (unsigned int)"shell\\twinui\\quiethoursservice\\lib\\quiethoursservice.cpp",
             v5);
  v8 = OpenProcess(0x1000u, 0, dwProcessId);
  v23[0] = v8;
  if ( (((unsigned __int64)v8 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    dwSize = 260;
    if ( !QueryFullProcessImageNameW(v8, 0, a3, &dwSize) )
    {
      LastErrorFailHr = wil::details::GetLastErrorFailHr(v10);
      CloseHandle(v8);
      return LastErrorFailHr;
    }
    FileNameW = PathFindFileNameW(a3);
    if ( !(unsigned int)_o__wcsicmp(L"ApplicationFrameHost.exe", FileNameW) )
    {
      lParam = dwProcessId;
      EnumChildWindows(a2, EnumChildWindowsCallback, (LPARAM)&lParam);
      if ( HIDWORD(lParam) )
      {
        if ( HIDWORD(lParam) != (_DWORD)lParam )
        {
          v13 = (char *)OpenProcess(0x1000u, 0, HIDWORD(lParam));
          v21 = v13;
          if ( (unsigned __int64)(v13 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          {
            LODWORD(applicationUserModelIdLength) = 0;
            if ( GetApplicationUserModelId(v13, (UINT32 *)&applicationUserModelIdLength, 0) == 122 )
            {
              if ( (_DWORD)applicationUserModelIdLength )
              {
                wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                  &applicationUserModelId,
                  0,
                  (unsigned int)applicationUserModelIdLength);
                v14 = applicationUserModelId;
                if ( applicationUserModelId )
                {
                  v15 = GetApplicationUserModelId(v13, (UINT32 *)&applicationUserModelIdLength, applicationUserModelId);
                  v16 = v15 < 0;
                  if ( v15 > 0 )
                    v16 = 1;
                  if ( !v16 )
                  {
                    v17 = -1;
                    do
                      ++v17;
                    while ( v14[v17] );
                    if ( v17 >= 0x104 )
                    {
                      CoTaskMemFree(v14);
                      Windows::Internal::MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v21);
                      v9 = -2147024774;
                      goto LABEL_26;
                    }
                    v18 = StringCchCopyW(a3, 0x104u, v14);
                    if ( v18 < 0 )
                    {
                      CoTaskMemFree(v14);
                      Windows::Internal::MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v21);
                      v9 = v18;
                      goto LABEL_26;
                    }
                  }
                  CoTaskMemFree(v14);
                }
              }
            }
          }
          Windows::Internal::MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v21);
        }
      }
    }
    v9 = 0;
    goto LABEL_26;
  }
  v9 = wil::details::GetLastErrorFailHr(v7);
LABEL_26:
  Windows::Internal::MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(v23);
  return v9;
}

```

## disassembly

```asm
0x180045368  mov     rax, rsp
0x18004536b  mov     [rax+10h], rbx
0x18004536f  mov     [rax+18h], rsi
0x180045373  mov     [rax+20h], r9d
0x180045377  mov     [rax+8], rcx
0x18004537b  push    rbp
0x18004537c  push    rdi
0x18004537d  push    r14
0x18004537f  mov     rbp, rsp
0x180045382  sub     rsp, 50h
0x180045386  mov     rsi, r8
0x180045389  mov     rdi, rdx
0x18004538c  xor     r14d, r14d
0x18004538f  mov     [rbp+dwProcessId], r14d
0x180045393  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x180045397  mov     rcx, rdi; hWnd
0x18004539a  call    cs:__imp_GetWindowThreadProcessId
0x1800453a0  test    eax, eax
0x1800453a2  jnz     short loc_1800453BE
0x1800453a4  mov     rcx, [rbp+18h]; this
0x1800453a8  lea     r8, aShellTwinuiQui; "shell\\twinui\\quiethoursservice\\lib\\"...
0x1800453af  mov     edx, 0ADh; void *
0x1800453b4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800453b9  jmp     loc_180045576
0x1800453be  mov     r8d, [rbp+dwProcessId]; dwProcessId
0x1800453c2  xor     edx, edx; bInheritHandle
0x1800453c4  mov     ecx, 1000h; dwDesiredAccess
0x1800453c9  call    cs:__imp_OpenProcess
0x1800453cf  mov     rbx, rax
0x1800453d2  mov     [rbp+var_10], rax
0x1800453d6  inc     rax
0x1800453d9  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800453df  jnz     short loc_1800453ED
0x1800453e1  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800453e6  mov     ebx, eax
0x1800453e8  jmp     loc_18004556B
0x1800453ed  mov     [rbp+dwSize], 104h
0x1800453f4  lea     r9, [rbp+dwSize]; lpdwSize
0x1800453f8  mov     r8, rsi; lpExeName
0x1800453fb  xor     edx, edx; dwFlags
0x1800453fd  mov     rcx, rbx; hProcess
0x180045400  call    cs:__imp_QueryFullProcessImageNameW
0x180045406  test    eax, eax
0x180045408  jnz     short loc_180045421
0x18004540a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18004540f  mov     edi, eax
0x180045411  mov     rcx, rbx; hObject
0x180045414  call    cs:__imp_CloseHandle
0x18004541a  mov     eax, edi
0x18004541c  jmp     loc_180045576
0x180045421  mov     rcx, rsi; pszPath
0x180045424  call    cs:__imp_PathFindFileNameW
0x18004542a  mov     rdx, rax
0x18004542d  lea     rcx, aApplicationfra_0; "ApplicationFrameHost.exe"
0x180045434  call    cs:__imp__o__wcsicmp
0x18004543a  test    eax, eax
0x18004543c  jnz     loc_180045568
0x180045442  mov     eax, [rbp+dwProcessId]
0x180045445  mov     dword ptr [rbp+lParam], eax
0x180045448  mov     dword ptr [rbp+lParam+4], r14d
0x18004544c  lea     r8, [rbp+lParam]; lParam
0x180045450  lea     rdx, ?EnumChildWindowsCallback@@YAHPEAUHWND__@@_J@Z; lpEnumFunc
0x180045457  mov     rcx, rdi; hWndParent
0x18004545a  call    cs:__imp_EnumChildWindows
0x180045460  mov     r8d, dword ptr [rbp+lParam+4]; dwProcessId
0x180045464  test    r8d, r8d
0x180045467  jz      loc_180045568
0x18004546d  cmp     r8d, dword ptr [rbp+lParam]
0x180045471  jz      loc_180045568
0x180045477  xor     edx, edx; bInheritHandle
0x180045479  mov     ecx, 1000h; dwDesiredAccess
0x18004547e  call    cs:__imp_OpenProcess
0x180045484  mov     rdi, rax
0x180045487  mov     [rbp+var_20], rax
0x18004548b  dec     rax
0x18004548e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180045492  ja      loc_18004555F
0x180045498  mov     dword ptr [rbp+applicationUserModelIdLength], r14d
0x18004549c  xor     r8d, r8d; applicationUserModelId
0x18004549f  lea     rdx, [rbp+applicationUserModelIdLength]; applicationUserModelIdLength
0x1800454a3  mov     rcx, rdi; hProcess
0x1800454a6  call    cs:__imp_GetApplicationUserModelId
0x1800454ac  cmp     eax, 7Ah ; 'z'
0x1800454af  jnz     loc_18004555F
0x1800454b5  mov     eax, dword ptr [rbp+applicationUserModelIdLength]
0x1800454b8  test    eax, eax
0x1800454ba  jz      loc_18004555F
0x1800454c0  mov     r8d, eax
0x1800454c3  xor     edx, edx
0x1800454c5  lea     rcx, [rbp+applicationUserModelId]
0x1800454c9  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800454ce  mov     rbx, [rbp+applicationUserModelId]
0x1800454d2  test    rbx, rbx
0x1800454d5  jz      loc_18004555F
0x1800454db  mov     r8, rbx; applicationUserModelId
0x1800454de  lea     rdx, [rbp+applicationUserModelIdLength]; applicationUserModelIdLength
0x1800454e2  mov     rcx, rdi; hProcess
0x1800454e5  call    cs:__imp_GetApplicationUserModelId
0x1800454eb  test    eax, eax
0x1800454ed  jle     short loc_1800454F9
0x1800454ef  movzx   eax, ax
0x1800454f2  or      eax, 80070000h
0x1800454f7  test    eax, eax
0x1800454f9  js      short loc_180045556
0x1800454fb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800454ff  inc     rax
0x180045502  cmp     [rbx+rax*2], r14w
0x180045507  jnz     short loc_1800454FF
0x180045509  cmp     rax, 104h
0x18004550f  jb      short loc_18004552A
0x180045511  mov     rcx, rbx; pv
0x180045514  call    cs:__imp_CoTaskMemFree
0x18004551a  lea     rcx, [rbp+var_20]
0x18004551e  call    ??1?$MoveOnCopy@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Internal@Windows@@QEAA@XZ; Windows::Internal::MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x180045523  mov     ebx, 8007007Ah
0x180045528  jmp     short loc_18004556B
0x18004552a  mov     r8, rbx; unsigned __int16 *
0x18004552d  mov     edx, 104h; unsigned __int64
0x180045532  mov     rcx, rsi; unsigned __int16 *
0x180045535  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004553a  mov     edi, eax
0x18004553c  test    eax, eax
0x18004553e  jns     short loc_180045556
0x180045540  mov     rcx, rbx; pv
0x180045543  call    cs:__imp_CoTaskMemFree
0x180045549  lea     rcx, [rbp+var_20]
0x18004554d  call    ??1?$MoveOnCopy@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Internal@Windows@@QEAA@XZ; Windows::Internal::MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x180045552  mov     ebx, edi
0x180045554  jmp     short loc_18004556B
0x180045556  mov     rcx, rbx; pv
0x180045559  call    cs:__imp_CoTaskMemFree
0x18004555f  lea     rcx, [rbp+var_20]
0x180045563  call    ??1?$MoveOnCopy@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Internal@Windows@@QEAA@XZ; Windows::Internal::MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x180045568  mov     ebx, r14d
0x18004556b  lea     rcx, [rbp+var_10]
0x18004556f  call    ??1?$MoveOnCopy@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Internal@Windows@@QEAA@XZ; Windows::Internal::MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x180045574  mov     eax, ebx
0x180045576  lea     r11, [rsp+50h+var_s0]
0x18004557b  mov     rbx, [r11+28h]
0x18004557f  mov     rsi, [r11+30h]
0x180045583  mov     rsp, r11
0x180045586  pop     r14
0x180045588  pop     rdi
0x180045589  pop     rbp
0x18004558a  retn
```
