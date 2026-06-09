# GetExecutableIconFromHwnd(HWND__ *,HICON__ * *)

- ea: `0x18001e028`
- end: `0x18001e19b`
- name: `?GetExecutableIconFromHwnd@@YAJPEAUHWND__@@PEAPEAUHICON__@@@Z`
- size: `371`
- prototype: `__int64 __fastcall(HWND, HICON *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18006aa20`

## callees

- `0x180019534`
- `0x18001cc38`
- `0x18001e028`
- `0x18001e340`
- `0x18002b1b0`
- `0x18002bc68`

## import_xrefs

- `Windows.Storage!SHGetFileInfoW` at `0x18001e12c`
- `Windows.Storage!SHGetFileInfoW` at `0x18001e12c`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18001e0d8`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18001e0d8`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001e0a0`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001e0a0`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18001e065`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18001e065`

## pseudocode

```c
__int64 __fastcall GetExecutableIconFromHwnd(HWND a1, HICON *a2)
{
  unsigned int LastError; // ebx
  HANDLE v4; // rax
  const char *v5; // r9
  __int64 v6; // rdx
  __int64 v7; // rdx
  UINT uFlags; // [rsp+20h] [rbp-E0h]
  UINT uFlagsa; // [rsp+20h] [rbp-E0h]
  DWORD dwProcessId; // [rsp+30h] [rbp-D0h] BYREF
  DWORD dwSize; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v13; // [rsp+38h] [rbp-C8h] BYREF
  SHFILEINFOW psfi; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR ExeName[264]; // [rsp+300h] [rbp+200h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+528h] [rbp+428h]

  *a2 = 0;
  dwProcessId = 0;
  if ( GetWindowThreadProcessId(a1, &dwProcessId) )
  {
    v4 = OpenProcess(0x1000u, 0, dwProcessId);
    v13 = v4;
    if ( (((unsigned __int64)v4 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      dwSize = 260;
      if ( QueryFullProcessImageNameW(v4, 0, ExeName, &dwSize) )
      {
        memset_0(&psfi, 0, sizeof(psfi));
        if ( SHGetFileInfoW(ExeName, 0, &psfi, 0x2B8u, 0x100u) )
        {
          if ( psfi.hIcon )
          {
            *a2 = psfi.hIcon;
            LastError = 0;
            goto LABEL_14;
          }
          v7 = 456;
        }
        else
        {
          v7 = 455;
        }
        LastError = -2147023728;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v7,
          (unsigned int)"onecoreuap\\shell\\twinui\\sharinganddevices\\platform\\sharingmanager.cpp",
          (const char *)0x80070490LL,
          uFlagsa);
LABEL_14:
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v13);
        return LastError;
      }
      v6 = 452;
    }
    else
    {
      v6 = 448;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v6,
                  (unsigned int)"onecoreuap\\shell\\twinui\\sharinganddevices\\platform\\sharingmanager.cpp",
                  v5);
    goto LABEL_14;
  }
  LastError = -2147023728;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1BD,
    (unsigned int)"onecoreuap\\shell\\twinui\\sharinganddevices\\platform\\sharingmanager.cpp",
    (const char *)0x80070490LL,
    uFlags);
  return LastError;
}

```

## disassembly

```asm
0x18001e028  mov     [rsp-8+arg_10], rbx
0x18001e02d  push    rbp
0x18001e02e  lea     rbp, [rsp-420h]
0x18001e036  sub     rsp, 520h
0x18001e03d  mov     rax, cs:__security_cookie
0x18001e044  xor     rax, rsp
0x18001e047  mov     [rbp+420h+var_10], rax
0x18001e04e  mov     rbx, rdx
0x18001e051  mov     qword ptr [rdx], 0
0x18001e058  lea     rdx, [rsp+520h+dwProcessId]; lpdwProcessId
0x18001e05d  mov     [rsp+520h+dwProcessId], 0
0x18001e065  call    cs:__imp_GetWindowThreadProcessId
0x18001e06b  test    eax, eax
0x18001e06d  jnz     short loc_18001E094
0x18001e06f  mov     rcx, [rbp+428h]; this
0x18001e076  lea     r8, aOnecoreuapShel_12; "onecoreuap\\shell\\twinui\\sharingandde"...
0x18001e07d  mov     ebx, 80070490h
0x18001e082  mov     edx, 1BDh; void *
0x18001e087  mov     r9d, ebx; char *
0x18001e08a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e08f  jmp     loc_18001E179
0x18001e094  mov     r8d, [rsp+520h+dwProcessId]; dwProcessId
0x18001e099  xor     edx, edx; bInheritHandle
0x18001e09b  mov     ecx, 1000h; dwDesiredAccess
0x18001e0a0  call    cs:__imp_OpenProcess
0x18001e0a6  mov     [rsp+520h+var_4E8], rax
0x18001e0ab  lea     rcx, [rax+1]
0x18001e0af  test    rcx, 0FFFFFFFFFFFFFFFEh
0x18001e0b6  jnz     short loc_18001E0BF
0x18001e0b8  mov     edx, 1C0h
0x18001e0bd  jmp     short loc_18001E0E7
0x18001e0bf  lea     r9, [rsp+520h+dwSize]; lpdwSize
0x18001e0c4  mov     [rsp+520h+dwSize], 104h
0x18001e0cc  lea     r8, [rbp+420h+ExeName]; lpExeName
0x18001e0d3  xor     edx, edx; dwFlags
0x18001e0d5  mov     rcx, rax; hProcess
0x18001e0d8  call    cs:__imp_QueryFullProcessImageNameW
0x18001e0de  test    eax, eax
0x18001e0e0  jnz     short loc_18001E0FE
0x18001e0e2  mov     edx, 1C4h; void *
0x18001e0e7  mov     rcx, [rbp+428h]; this
0x18001e0ee  lea     r8, aOnecoreuapShel_12; "onecoreuap\\shell\\twinui\\sharingandde"...
0x18001e0f5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001e0fa  mov     ebx, eax
0x18001e0fc  jmp     short loc_18001E16F
0x18001e0fe  xor     edx, edx; Val
0x18001e100  lea     rcx, [rsp+520h+psfi]; void *
0x18001e105  mov     r8d, 2B8h; Size
0x18001e10b  call    memset_0
0x18001e110  mov     r9d, 2B8h; cbFileInfo
0x18001e116  mov     [rsp+520h+uFlags], 100h; int
0x18001e11e  lea     r8, [rsp+520h+psfi]; psfi
0x18001e123  xor     edx, edx; dwFileAttributes
0x18001e125  lea     rcx, [rbp+420h+ExeName]; pszPath
0x18001e12c  call    cs:__imp_SHGetFileInfoW
0x18001e132  test    rax, rax
0x18001e135  jnz     short loc_18001E159
0x18001e137  mov     edx, 1C7h; void *
0x18001e13c  mov     rcx, [rbp+428h]; this
0x18001e143  lea     r8, aOnecoreuapShel_12; "onecoreuap\\shell\\twinui\\sharingandde"...
0x18001e14a  mov     ebx, 80070490h
0x18001e14f  mov     r9d, ebx; char *
0x18001e152  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e157  jmp     short loc_18001E16F
0x18001e159  mov     rax, [rsp+520h+psfi.hIcon]
0x18001e15e  test    rax, rax
0x18001e161  jnz     short loc_18001E16A
0x18001e163  mov     edx, 1C8h
0x18001e168  jmp     short loc_18001E13C
0x18001e16a  mov     [rbx], rax
0x18001e16d  xor     ebx, ebx
0x18001e16f  lea     rcx, [rsp+520h+var_4E8]
0x18001e174  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001e179  mov     eax, ebx
0x18001e17b  mov     rcx, [rbp+420h+var_10]
0x18001e182  xor     rcx, rsp; StackCookie
0x18001e185  call    __security_check_cookie
0x18001e18a  mov     rbx, [rsp+520h+arg_10]
0x18001e192  add     rsp, 520h
0x18001e199  pop     rbp
0x18001e19a  retn
```
