# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180024a60`
- end: `0x180024d25`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `709`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x180025b40`

## callees

- `0x18000955c`
- `0x180024a60`
- `0x180025354`
- `0x1800258b4`
- `0x1800263f0`
- `0x180027300`
- `0x180027f74`
- `0x180028824`
- `0x1800319f0`

## import_xrefs

- `KERNEL32!ReleaseMutex` at `0x180024b90`
- `KERNEL32!ReleaseMutex` at `0x180024c13`
- `KERNEL32!ReleaseMutex` at `0x180024c56`
- `KERNEL32!ReleaseMutex` at `0x180024b90`
- `KERNEL32!ReleaseMutex` at `0x180024c13`
- `KERNEL32!ReleaseMutex` at `0x180024c56`
- `KERNEL32!CloseHandle` at `0x180024ba7`
- `KERNEL32!CloseHandle` at `0x180024c31`
- `KERNEL32!CloseHandle` at `0x180024c72`
- `KERNEL32!CloseHandle` at `0x180024ba7`
- `KERNEL32!CloseHandle` at `0x180024c31`
- `KERNEL32!CloseHandle` at `0x180024c72`
- `KERNEL32!GetCurrentProcessId` at `0x180024a9b`
- `KERNEL32!GetCurrentProcessId` at `0x180024a9b`
- `KERNEL32!CreateMutexExW` at `0x180024add`
- `KERNEL32!CreateMutexExW` at `0x180024add`
- `KERNEL32!WaitForSingleObjectEx` at `0x180024b09`
- `KERNEL32!WaitForSingleObjectEx` at `0x180024b09`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  HANDLE v6; // rbx
  DWORD v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  void *v12; // rdi
  int ValueInternal; // eax
  unsigned int v14; // r8d
  unsigned int v15; // esi
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // r8d
  const char *v21; // r9
  _DWORD *v22; // rcx
  int v23; // eax
  unsigned int v24; // r8d
  unsigned int v25; // ebx
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  int v34; // [rsp+20h] [rbp-E0h]
  int v35; // [rsp+20h] [rbp-E0h]
  HANDLE hObject; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v37; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  hObject = Mutex;
  v6 = Mutex;
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v5);
  v8 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v8 == 258 )
  {
    v12 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v9, v10, v11);
    v12 = v6;
  }
  v37 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, &v37, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v34);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v35);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v18, v19);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
    return v15;
  }
  v22 = (_DWORD *)(4 * v37);
  if ( 4 * v37 )
  {
    *a2 = v22;
    ++*v22;
    goto LABEL_21;
  }
  v23 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(
          Name,
          &hObject,
          a2);
  v25 = v23;
  if ( v23 >= 0 )
  {
    v6 = hObject;
LABEL_21:
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v30, v31);
    if ( v6 && !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v24, (const char *)(unsigned int)v23, 120);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v26, v27);
  if ( hObject && !CloseHandle(hObject) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
  return v25;
}

```

## disassembly

```asm
0x180024a60  mov     [rsp-8+arg_10], rbx
0x180024a65  mov     [rsp-8+arg_18], rsi
0x180024a6a  push    rbp
0x180024a6b  push    rdi
0x180024a6c  push    r14
0x180024a6e  lea     rbp, [rsp-160h]
0x180024a76  sub     rsp, 260h
0x180024a7d  mov     rax, cs:__security_cookie
0x180024a84  xor     rax, rsp
0x180024a87  mov     [rbp+170h+var_20], rax
0x180024a8e  mov     r14, rdx
0x180024a91  mov     qword ptr [rdx], 0
0x180024a98  mov     rbx, rcx
0x180024a9b  call    cs:__imp_GetCurrentProcessId
0x180024aa2  nop     dword ptr [rax+rax+00h]
0x180024aa7  mov     [rsp+270h+var_248], rbx
0x180024aac  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180024ab3  mov     r9d, eax
0x180024ab6  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180024abe  mov     edx, 104h; unsigned __int64
0x180024ac3  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180024ac8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180024acd  mov     r9d, 1F0001h; dwDesiredAccess
0x180024ad3  lea     rdx, [rsp+270h+Name]; lpName
0x180024ad8  xor     r8d, r8d; dwFlags
0x180024adb  xor     ecx, ecx; lpMutexAttributes
0x180024add  call    cs:__imp_CreateMutexExW
0x180024ae4  nop     dword ptr [rax+rax+00h]
0x180024ae9  mov     [rsp+270h+hObject], rax
0x180024aee  mov     rbx, rax
0x180024af1  test    rax, rax
0x180024af4  jnz     short loc_180024B00
0x180024af6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180024afb  jmp     loc_180024C84
0x180024b00  xor     r8d, r8d; bAlertable
0x180024b03  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180024b06  mov     rcx, rbx; hHandle
0x180024b09  call    cs:__imp_WaitForSingleObjectEx
0x180024b10  nop     dword ptr [rax+rax+00h]
0x180024b15  cmp     eax, 102h
0x180024b1a  jz      short loc_180024B2C
0x180024b1c  test    eax, 0FFFFFF7Fh
0x180024b21  jnz     loc_180024CBE
0x180024b27  mov     rdi, rbx
0x180024b2a  jmp     short loc_180024B2E
0x180024b2c  xor     edi, edi
0x180024b2e  lea     r8, [rsp+270h+var_238]; unsigned __int64 *
0x180024b33  mov     [rsp+270h+var_238], 0
0x180024b3c  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180024b41  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180024b46  mov     esi, eax
0x180024b48  test    eax, eax
0x180024b4a  jns     short loc_180024BC2
0x180024b4c  mov     rcx, [rbp+178h]; this
0x180024b53  mov     r9d, eax; char *
0x180024b56  mov     edx, 66h ; 'f'; void *
0x180024b5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024b60  mov     rcx, [rbp+178h]; this
0x180024b67  mov     r9d, esi; char *
0x180024b6a  mov     edx, 6Fh ; 'o'; void *
0x180024b6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024b74  mov     rcx, [rbp+178h]; this
0x180024b7b  mov     r9d, esi; char *
0x180024b7e  mov     edx, 12Eh; void *
0x180024b83  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024b88  test    rdi, rdi
0x180024b8b  jz      short loc_180024BA4
0x180024b8d  mov     rcx, rdi; hMutex
0x180024b90  call    cs:__imp_ReleaseMutex
0x180024b97  nop     dword ptr [rax+rax+00h]
0x180024b9c  test    eax, eax
0x180024b9e  jz      loc_180024CCB
0x180024ba4  mov     rcx, rbx; hObject
0x180024ba7  call    cs:__imp_CloseHandle
0x180024bae  nop     dword ptr [rax+rax+00h]
0x180024bb3  test    eax, eax
0x180024bb5  jz      loc_180024CDD
0x180024bbb  mov     eax, esi
0x180024bbd  jmp     loc_180024C84
0x180024bc2  mov     rax, [rsp+270h+var_238]
0x180024bc7  lea     rcx, ds:0[rax*4]
0x180024bcf  test    rcx, rcx
0x180024bd2  jz      short loc_180024BDF
0x180024bd4  mov     [r14], rcx
0x180024bd7  mov     eax, [rcx]
0x180024bd9  inc     eax
0x180024bdb  mov     [rcx], eax
0x180024bdd  jmp     short loc_180024C4E
0x180024bdf  mov     r8, r14
0x180024be2  lea     rdx, [rsp+270h+hObject]
0x180024be7  lea     rcx, [rsp+270h+Name]
0x180024bec  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180024bf1  mov     ebx, eax
0x180024bf3  test    eax, eax
0x180024bf5  jns     short loc_180024C49
0x180024bf7  mov     rcx, [rbp+178h]; this
0x180024bfe  mov     r9d, eax; char *
0x180024c01  mov     edx, 137h; void *
0x180024c06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024c0b  test    rdi, rdi
0x180024c0e  jz      short loc_180024C27
0x180024c10  mov     rcx, rdi; hMutex
0x180024c13  call    cs:__imp_ReleaseMutex
0x180024c1a  nop     dword ptr [rax+rax+00h]
0x180024c1f  test    eax, eax
0x180024c21  jz      loc_180024CEF
0x180024c27  mov     rcx, [rsp+270h+hObject]; hObject
0x180024c2c  test    rcx, rcx
0x180024c2f  jz      short loc_180024C45
0x180024c31  call    cs:__imp_CloseHandle
0x180024c38  nop     dword ptr [rax+rax+00h]
0x180024c3d  test    eax, eax
0x180024c3f  jz      loc_180024D01
0x180024c45  mov     eax, ebx
0x180024c47  jmp     short loc_180024C84
0x180024c49  mov     rbx, [rsp+270h+hObject]
0x180024c4e  test    rdi, rdi
0x180024c51  jz      short loc_180024C6A
0x180024c53  mov     rcx, rdi; hMutex
0x180024c56  call    cs:__imp_ReleaseMutex
0x180024c5d  nop     dword ptr [rax+rax+00h]
0x180024c62  test    eax, eax
0x180024c64  jz      loc_180024D13
0x180024c6a  test    rbx, rbx
0x180024c6d  jz      short loc_180024C82
0x180024c6f  mov     rcx, rbx; hObject
0x180024c72  call    cs:__imp_CloseHandle
0x180024c79  nop     dword ptr [rax+rax+00h]
0x180024c7e  test    eax, eax
0x180024c80  jz      short loc_180024CAC
0x180024c82  xor     eax, eax
0x180024c84  mov     rcx, [rbp+170h+var_20]
0x180024c8b  xor     rcx, rsp; StackCookie
0x180024c8e  call    __security_check_cookie
0x180024c93  lea     r11, [rsp+270h+var_10]
0x180024c9b  mov     rbx, [r11+30h]
0x180024c9f  mov     rsi, [r11+38h]
0x180024ca3  mov     rsp, r11
0x180024ca6  pop     r14
0x180024ca8  pop     rdi
0x180024ca9  pop     rbp
0x180024caa  retn
0x180024cac  mov     rcx, [rbp+178h]; this
0x180024cb3  mov     edx, 0A0Bh; void *
0x180024cb8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180024cbe  mov     rcx, [rbp+178h]; this
0x180024cc5  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180024ccb  mov     rcx, [rbp+178h]; this
0x180024cd2  mov     edx, 0A15h; void *
0x180024cd7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180024cdd  mov     rcx, [rbp+178h]; this
0x180024ce4  mov     edx, 0A0Bh; void *
0x180024ce9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180024cef  mov     rcx, [rbp+178h]; this
0x180024cf6  mov     edx, 0A15h; void *
0x180024cfb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180024d01  mov     rcx, [rbp+178h]; this
0x180024d08  mov     edx, 0A0Bh; void *
0x180024d0d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180024d13  mov     rcx, [rbp+178h]; this
0x180024d1a  mov     edx, 0A15h; void *
0x180024d1f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
