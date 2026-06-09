# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180010b30`
- end: `0x180010ef7`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1800111d4`

## callees

- `0x18000465c`
- `0x18001007c`
- `0x180010b30`
- `0x180010f00`
- `0x180011364`
- `0x180011c88`
- `0x180012878`
- `0x180013b10`
- `0x1800141ac`
- `0x18001498c`
- `0x18001499c`
- `0x1800157be`
- `0x1800157f0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180010c5a`
- `KERNEL32!CloseHandle` at `0x180010d1a`
- `KERNEL32!CloseHandle` at `0x180010d32`
- `KERNEL32!CloseHandle` at `0x180010d81`
- `KERNEL32!CloseHandle` at `0x180010e22`
- `KERNEL32!CloseHandle` at `0x180010c5a`
- `KERNEL32!CloseHandle` at `0x180010d1a`
- `KERNEL32!CloseHandle` at `0x180010d32`
- `KERNEL32!CloseHandle` at `0x180010d81`
- `KERNEL32!CloseHandle` at `0x180010e22`
- `KERNEL32!GetCurrentProcessId` at `0x180010b69`
- `KERNEL32!GetCurrentProcessId` at `0x180010b69`
- `KERNEL32!HeapFree` at `0x180010d4e`
- `KERNEL32!HeapFree` at `0x180010d4e`
- `KERNEL32!InitializeCriticalSectionEx` at `0x180010dd9`
- `KERNEL32!InitializeCriticalSectionEx` at `0x180010dd9`
- `KERNEL32!ReleaseMutex` at `0x180010c49`
- `KERNEL32!ReleaseMutex` at `0x180010d70`
- `KERNEL32!ReleaseMutex` at `0x180010e0c`
- `KERNEL32!ReleaseMutex` at `0x180010c49`
- `KERNEL32!ReleaseMutex` at `0x180010d70`
- `KERNEL32!ReleaseMutex` at `0x180010e0c`
- `KERNEL32!WaitForSingleObjectEx` at `0x180010bc8`
- `KERNEL32!WaitForSingleObjectEx` at `0x180010bc8`
- `KERNEL32!GetProcessHeap` at `0x180010d40`
- `KERNEL32!GetProcessHeap` at `0x180010d40`
- `KERNEL32!CreateMutexExW` at `0x180010ba7`
- `KERNEL32!CreateMutexExW` at `0x180010ba7`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rbx
  DWORD v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  void *v12; // rdi
  int ValueInternal; // eax
  unsigned __int64 v14; // r8
  unsigned int v15; // esi
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  __int64 v18; // r8
  const char *v19; // r9
  __int64 v20; // r8
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  unsigned int v25; // r8d
  _DWORD *v26; // r14
  unsigned int v27; // r8d
  int v28; // eax
  unsigned int v29; // r8d
  __int64 v30; // r8
  const char *v31; // r9
  __int64 v32; // r8
  const char *v33; // r9
  HANDLE ProcessHeap; // rax
  __int64 v35; // r8
  const char *v36; // r9
  __int64 v37; // r8
  const char *v38; // r9
  __int128 v39; // xmm0
  __int64 v40; // r8
  const char *v41; // r9
  __int64 v42; // r8
  const char *v43; // r9
  int v44; // [rsp+20h] [rbp-E0h]
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
  HANDLE hObject[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
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
  hObject[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    (bool)v9,
                    (unsigned __int64 *)hObject,
                    (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v44);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v45);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v18, v19);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
    return v15;
  }
  v22 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v22;
    ++*v22;
    goto LABEL_28;
  }
  *a2 = 0;
  v23 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v26 = (_DWORD *)v23;
  if ( !v23 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v25, (const char *)0x8007000ELL, 304);
LABEL_23:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v27, (const char *)v15, v46);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v35, v36);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v37, v38);
    return v15;
  }
  *(_OWORD *)hObject = 0;
  if ( (v23 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
  v28 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)hObject,
          Name,
          v25,
          v23 >> 2);
  v15 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v29, (const char *)(unsigned int)v28, 304);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v26);
    goto LABEL_23;
  }
  v39 = *(_OWORD *)hObject;
  *v26 = 1;
  *((_QWORD *)v26 + 1) = v6;
  *((_OWORD *)v26 + 1) = v39;
  memset_0(v26 + 10, 0, 0x108u);
  *((_QWORD *)v26 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v26 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v26 + 58), 0, 0);
  *((_QWORD *)v26 + 34) = 0;
  *((_QWORD *)v26 + 35) = 0;
  *((_QWORD *)v26 + 36) = 0;
  *((_QWORD *)v26 + 37) = 0;
  v6 = 0;
  *a2 = v26;
LABEL_28:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v40, v41);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v42, v43);
  return 0;
}

```

## disassembly

```asm
0x180010b30  mov     [rsp-8+arg_10], rbx
0x180010b35  push    rbp
0x180010b36  push    rsi
0x180010b37  push    rdi
0x180010b38  push    r14
0x180010b3a  push    r15
0x180010b3c  lea     rbp, [rsp-160h]
0x180010b44  sub     rsp, 260h
0x180010b4b  mov     rax, cs:__security_cookie
0x180010b52  xor     rax, rsp
0x180010b55  mov     [rbp+180h+var_30], rax
0x180010b5c  mov     r15, rdx
0x180010b5f  mov     qword ptr [rdx], 0
0x180010b66  mov     rbx, rcx
0x180010b69  call    cs:__imp_GetCurrentProcessId
0x180010b6f  mov     r14d, 130h
0x180010b75  mov     [rsp+280h+var_258], rbx
0x180010b7a  mov     r9d, eax
0x180010b7d  mov     [rsp+280h+var_260], r14d; int
0x180010b82  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180010b89  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180010b8e  lea     edx, [r14-2Ch]; unsigned __int64
0x180010b92  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010b97  mov     r9d, 1F0001h; dwDesiredAccess
0x180010b9d  lea     rdx, [rsp+280h+Name]; lpName
0x180010ba2  xor     r8d, r8d; dwFlags
0x180010ba5  xor     ecx, ecx; lpMutexAttributes
0x180010ba7  call    cs:__imp_CreateMutexExW
0x180010bad  mov     rbx, rax
0x180010bb0  test    rax, rax
0x180010bb3  jnz     short loc_180010BBF
0x180010bb5  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180010bba  jmp     loc_180010E2E
0x180010bbf  xor     r8d, r8d; bAlertable
0x180010bc2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180010bc5  mov     rcx, rbx; hHandle
0x180010bc8  call    cs:__imp_WaitForSingleObjectEx
0x180010bce  cmp     eax, 102h
0x180010bd3  jz      short loc_180010BE5
0x180010bd5  test    eax, 0FFFFFF7Fh
0x180010bda  jnz     loc_180010E78
0x180010be0  mov     rdi, rbx
0x180010be3  jmp     short loc_180010BE7
0x180010be5  xor     edi, edi
0x180010be7  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180010bec  mov     [rsp+280h+hObject], 0
0x180010bf5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180010bfa  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180010bff  mov     esi, eax
0x180010c01  test    eax, eax
0x180010c03  jns     short loc_180010C6F
0x180010c05  mov     rcx, [rbp+188h]; this
0x180010c0c  mov     r9d, eax; char *
0x180010c0f  mov     edx, 66h ; 'f'; void *
0x180010c14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010c19  mov     rcx, [rbp+188h]; this
0x180010c20  mov     r9d, esi; char *
0x180010c23  mov     edx, 6Fh ; 'o'; void *
0x180010c28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010c2d  mov     rcx, [rbp+188h]; this
0x180010c34  mov     r9d, esi; char *
0x180010c37  mov     edx, 12Eh; void *
0x180010c3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010c41  test    rdi, rdi
0x180010c44  jz      short loc_180010C57
0x180010c46  mov     rcx, rdi; hMutex
0x180010c49  call    cs:__imp_ReleaseMutex
0x180010c4f  test    eax, eax
0x180010c51  jz      loc_180010E85
0x180010c57  mov     rcx, rbx; hObject
0x180010c5a  call    cs:__imp_CloseHandle
0x180010c60  test    eax, eax
0x180010c62  jz      loc_180010E97
0x180010c68  mov     eax, esi
0x180010c6a  jmp     loc_180010E2E
0x180010c6f  mov     rax, [rsp+280h+hObject]
0x180010c74  lea     rcx, ds:0[rax*4]
0x180010c7c  test    rcx, rcx
0x180010c7f  jz      short loc_180010C8F
0x180010c81  mov     [r15], rcx
0x180010c84  mov     eax, [rcx]
0x180010c86  inc     eax
0x180010c88  mov     [rcx], eax
0x180010c8a  jmp     loc_180010E04
0x180010c8f  mov     rdx, r14; dwBytes
0x180010c92  mov     qword ptr [r15], 0
0x180010c99  mov     ecx, 8; dwFlags
0x180010c9e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180010ca3  mov     r14, rax
0x180010ca6  test    rax, rax
0x180010ca9  jnz     short loc_180010CC9
0x180010cab  mov     rcx, [rbp+188h]; this
0x180010cb2  mov     esi, 8007000Eh
0x180010cb7  mov     r9d, esi; char *
0x180010cba  mov     edx, 14Bh; void *
0x180010cbf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010cc4  jmp     loc_180010D54
0x180010cc9  xorps   xmm0, xmm0
0x180010ccc  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180010cd2  test    r14b, 3
0x180010cd6  jnz     loc_180010EA9
0x180010cdc  mov     r9, r14
0x180010cdf  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180010ce4  shr     r9, 2; unsigned __int64
0x180010ce8  lea     rcx, [rsp+280h+hObject]; this
0x180010ced  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180010cf2  mov     esi, eax
0x180010cf4  test    eax, eax
0x180010cf6  jns     loc_180010D94
0x180010cfc  mov     rcx, [rbp+188h]; this
0x180010d03  mov     r9d, eax; char *
0x180010d06  mov     edx, 14Eh; void *
0x180010d0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010d10  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180010d15  test    rcx, rcx
0x180010d18  jz      short loc_180010D28
0x180010d1a  call    cs:__imp_CloseHandle
0x180010d20  test    eax, eax
0x180010d22  jz      loc_180010EAF
0x180010d28  mov     rcx, [rsp+280h+hObject]; hObject
0x180010d2d  test    rcx, rcx
0x180010d30  jz      short loc_180010D40
0x180010d32  call    cs:__imp_CloseHandle
0x180010d38  test    eax, eax
0x180010d3a  jz      loc_180010EC1
0x180010d40  call    cs:__imp_GetProcessHeap
0x180010d46  mov     r8, r14; lpMem
0x180010d49  xor     edx, edx; dwFlags
0x180010d4b  mov     rcx, rax; hHeap
0x180010d4e  call    cs:__imp_HeapFree
0x180010d54  mov     rcx, [rbp+188h]; this
0x180010d5b  mov     r9d, esi; char *
0x180010d5e  mov     edx, 137h; void *
0x180010d63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010d68  test    rdi, rdi
0x180010d6b  jz      short loc_180010D7E
0x180010d6d  mov     rcx, rdi; hMutex
0x180010d70  call    cs:__imp_ReleaseMutex
0x180010d76  test    eax, eax
0x180010d78  jz      loc_180010ED3
0x180010d7e  mov     rcx, rbx; hObject
0x180010d81  call    cs:__imp_CloseHandle
0x180010d87  test    eax, eax
0x180010d89  jz      loc_180010E66
0x180010d8f  jmp     loc_180010C68
0x180010d94  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180010d99  lea     rcx, [r14+28h]; void *
0x180010d9d  mov     dword ptr [r14], 1
0x180010da4  xor     edx, edx; Val
0x180010da6  mov     [r14+8], rbx
0x180010daa  mov     r8d, 108h; Size
0x180010db0  movdqu  xmmword ptr [r14+10h], xmm0
0x180010db6  call    memset_0
0x180010dbb  xor     eax, eax
0x180010dbd  lea     rcx, [r14+28h]; this
0x180010dc1  mov     [r14+20h], rax
0x180010dc5  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180010dca  lea     rbx, [r14+0E8h]
0x180010dd1  xor     r8d, r8d; Flags
0x180010dd4  mov     rcx, rbx; lpCriticalSection
0x180010dd7  xor     edx, edx; dwSpinCount
0x180010dd9  call    cs:__imp_InitializeCriticalSectionEx
0x180010ddf  mov     qword ptr [rbx+28h], 0
0x180010de7  mov     qword ptr [rbx+30h], 0
0x180010def  mov     qword ptr [rbx+38h], 0
0x180010df7  mov     qword ptr [rbx+40h], 0
0x180010dff  xor     ebx, ebx
0x180010e01  mov     [r15], r14
0x180010e04  test    rdi, rdi
0x180010e07  jz      short loc_180010E1A
0x180010e09  mov     rcx, rdi; hMutex
0x180010e0c  call    cs:__imp_ReleaseMutex
0x180010e12  test    eax, eax
0x180010e14  jz      loc_180010EE5
0x180010e1a  test    rbx, rbx
0x180010e1d  jz      short loc_180010E2C
0x180010e1f  mov     rcx, rbx; hObject
0x180010e22  call    cs:__imp_CloseHandle
0x180010e28  test    eax, eax
0x180010e2a  jz      short loc_180010E54
0x180010e2c  xor     eax, eax
0x180010e2e  mov     rcx, [rbp+180h+var_30]
0x180010e35  xor     rcx, rsp; StackCookie
0x180010e38  call    __security_check_cookie
0x180010e3d  mov     rbx, [rsp+280h+arg_10]
0x180010e45  add     rsp, 260h
0x180010e4c  pop     r15
0x180010e4e  pop     r14
0x180010e50  pop     rdi
0x180010e51  pop     rsi
0x180010e52  pop     rbp
0x180010e53  retn
0x180010e54  mov     rcx, [rbp+188h]; this
0x180010e5b  mov     edx, 0A0Bh; void *
0x180010e60  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010e66  mov     rcx, [rbp+188h]; this
0x180010e6d  mov     edx, 0A0Bh; void *
0x180010e72  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010e78  mov     rcx, [rbp+188h]; this
0x180010e7f  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180010e85  mov     rcx, [rbp+188h]; this
0x180010e8c  mov     edx, 0A15h; void *
0x180010e91  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010e97  mov     rcx, [rbp+188h]; this
0x180010e9e  mov     edx, 0A0Bh; void *
0x180010ea3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010ea9  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180010eaf  mov     rcx, [rbp+188h]; this
0x180010eb6  mov     edx, 0A0Bh; void *
0x180010ebb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010ec1  mov     rcx, [rbp+188h]; this
0x180010ec8  mov     edx, 0A0Bh; void *
0x180010ecd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010ed3  mov     rcx, [rbp+188h]; this
0x180010eda  mov     edx, 0A15h; void *
0x180010edf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010ee5  mov     rcx, [rbp+188h]; this
0x180010eec  mov     edx, 0A15h; void *
0x180010ef1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
