# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180009c30`
- end: `0x180009ff7`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x18000b030`

## callees

- `0x180002978`
- `0x180008f60`
- `0x180009c30`
- `0x18000aa8c`
- `0x18000b2dc`
- `0x18000bd6c`
- `0x18000e5e4`
- `0x18000ffb4`
- `0x1800111dc`
- `0x1800125a4`
- `0x1800125b4`
- `0x180029882`
- `0x1800298c0`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180009e40`
- `KERNEL32!GetProcessHeap` at `0x180009e40`
- `KERNEL32!HeapFree` at `0x180009e4e`
- `KERNEL32!HeapFree` at `0x180009e4e`
- `KERNEL32!CloseHandle` at `0x180009d5a`
- `KERNEL32!CloseHandle` at `0x180009e1a`
- `KERNEL32!CloseHandle` at `0x180009e32`
- `KERNEL32!CloseHandle` at `0x180009e81`
- `KERNEL32!CloseHandle` at `0x180009f22`
- `KERNEL32!CloseHandle` at `0x180009d5a`
- `KERNEL32!CloseHandle` at `0x180009e1a`
- `KERNEL32!CloseHandle` at `0x180009e32`
- `KERNEL32!CloseHandle` at `0x180009e81`
- `KERNEL32!CloseHandle` at `0x180009f22`
- `KERNEL32!ReleaseMutex` at `0x180009d49`
- `KERNEL32!ReleaseMutex` at `0x180009e70`
- `KERNEL32!ReleaseMutex` at `0x180009f0c`
- `KERNEL32!ReleaseMutex` at `0x180009d49`
- `KERNEL32!ReleaseMutex` at `0x180009e70`
- `KERNEL32!ReleaseMutex` at `0x180009f0c`
- `KERNEL32!WaitForSingleObjectEx` at `0x180009cc8`
- `KERNEL32!WaitForSingleObjectEx` at `0x180009cc8`
- `KERNEL32!InitializeCriticalSectionEx` at `0x180009ed9`
- `KERNEL32!InitializeCriticalSectionEx` at `0x180009ed9`
- `KERNEL32!GetCurrentProcessId` at `0x180009c69`
- `KERNEL32!GetCurrentProcessId` at `0x180009c69`
- `KERNEL32!CreateMutexExW` at `0x180009ca7`
- `KERNEL32!CreateMutexExW` at `0x180009ca7`

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
0x180009c30  mov     [rsp-8+arg_10], rbx
0x180009c35  push    rbp
0x180009c36  push    rsi
0x180009c37  push    rdi
0x180009c38  push    r14
0x180009c3a  push    r15
0x180009c3c  lea     rbp, [rsp-160h]
0x180009c44  sub     rsp, 260h
0x180009c4b  mov     rax, cs:__security_cookie
0x180009c52  xor     rax, rsp
0x180009c55  mov     [rbp+180h+var_30], rax
0x180009c5c  mov     r15, rdx
0x180009c5f  mov     qword ptr [rdx], 0
0x180009c66  mov     rbx, rcx
0x180009c69  call    cs:__imp_GetCurrentProcessId
0x180009c6f  mov     r14d, 130h
0x180009c75  mov     [rsp+280h+var_258], rbx
0x180009c7a  mov     r9d, eax
0x180009c7d  mov     [rsp+280h+var_260], r14d; int
0x180009c82  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180009c89  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180009c8e  lea     edx, [r14-2Ch]; unsigned __int64
0x180009c92  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009c97  mov     r9d, 1F0001h; dwDesiredAccess
0x180009c9d  lea     rdx, [rsp+280h+Name]; lpName
0x180009ca2  xor     r8d, r8d; dwFlags
0x180009ca5  xor     ecx, ecx; lpMutexAttributes
0x180009ca7  call    cs:__imp_CreateMutexExW
0x180009cad  mov     rbx, rax
0x180009cb0  test    rax, rax
0x180009cb3  jnz     short loc_180009CBF
0x180009cb5  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009cba  jmp     loc_180009F2E
0x180009cbf  xor     r8d, r8d; bAlertable
0x180009cc2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180009cc5  mov     rcx, rbx; hHandle
0x180009cc8  call    cs:__imp_WaitForSingleObjectEx
0x180009cce  cmp     eax, 102h
0x180009cd3  jz      short loc_180009CE5
0x180009cd5  test    eax, 0FFFFFF7Fh
0x180009cda  jnz     loc_180009F78
0x180009ce0  mov     rdi, rbx
0x180009ce3  jmp     short loc_180009CE7
0x180009ce5  xor     edi, edi
0x180009ce7  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180009cec  mov     [rsp+280h+hObject], 0
0x180009cf5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180009cfa  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180009cff  mov     esi, eax
0x180009d01  test    eax, eax
0x180009d03  jns     short loc_180009D6F
0x180009d05  mov     rcx, [rbp+188h]; this
0x180009d0c  mov     r9d, eax; char *
0x180009d0f  mov     edx, 66h ; 'f'; void *
0x180009d14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009d19  mov     rcx, [rbp+188h]; this
0x180009d20  mov     r9d, esi; char *
0x180009d23  mov     edx, 6Fh ; 'o'; void *
0x180009d28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009d2d  mov     rcx, [rbp+188h]; this
0x180009d34  mov     r9d, esi; char *
0x180009d37  mov     edx, 12Eh; void *
0x180009d3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009d41  test    rdi, rdi
0x180009d44  jz      short loc_180009D57
0x180009d46  mov     rcx, rdi; hMutex
0x180009d49  call    cs:__imp_ReleaseMutex
0x180009d4f  test    eax, eax
0x180009d51  jz      loc_180009F85
0x180009d57  mov     rcx, rbx; hObject
0x180009d5a  call    cs:__imp_CloseHandle
0x180009d60  test    eax, eax
0x180009d62  jz      loc_180009F97
0x180009d68  mov     eax, esi
0x180009d6a  jmp     loc_180009F2E
0x180009d6f  mov     rax, [rsp+280h+hObject]
0x180009d74  lea     rcx, ds:0[rax*4]
0x180009d7c  test    rcx, rcx
0x180009d7f  jz      short loc_180009D8F
0x180009d81  mov     [r15], rcx
0x180009d84  mov     eax, [rcx]
0x180009d86  inc     eax
0x180009d88  mov     [rcx], eax
0x180009d8a  jmp     loc_180009F04
0x180009d8f  mov     rdx, r14; dwBytes
0x180009d92  mov     qword ptr [r15], 0
0x180009d99  mov     ecx, 8; dwFlags
0x180009d9e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009da3  mov     r14, rax
0x180009da6  test    rax, rax
0x180009da9  jnz     short loc_180009DC9
0x180009dab  mov     rcx, [rbp+188h]; this
0x180009db2  mov     esi, 8007000Eh
0x180009db7  mov     r9d, esi; char *
0x180009dba  mov     edx, 14Bh; void *
0x180009dbf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009dc4  jmp     loc_180009E54
0x180009dc9  xorps   xmm0, xmm0
0x180009dcc  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180009dd2  test    r14b, 3
0x180009dd6  jnz     loc_180009FA9
0x180009ddc  mov     r9, r14
0x180009ddf  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180009de4  shr     r9, 2; unsigned __int64
0x180009de8  lea     rcx, [rsp+280h+hObject]; this
0x180009ded  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180009df2  mov     esi, eax
0x180009df4  test    eax, eax
0x180009df6  jns     loc_180009E94
0x180009dfc  mov     rcx, [rbp+188h]; this
0x180009e03  mov     r9d, eax; char *
0x180009e06  mov     edx, 14Eh; void *
0x180009e0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009e10  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180009e15  test    rcx, rcx
0x180009e18  jz      short loc_180009E28
0x180009e1a  call    cs:__imp_CloseHandle
0x180009e20  test    eax, eax
0x180009e22  jz      loc_180009FAF
0x180009e28  mov     rcx, [rsp+280h+hObject]; hObject
0x180009e2d  test    rcx, rcx
0x180009e30  jz      short loc_180009E40
0x180009e32  call    cs:__imp_CloseHandle
0x180009e38  test    eax, eax
0x180009e3a  jz      loc_180009FC1
0x180009e40  call    cs:__imp_GetProcessHeap
0x180009e46  mov     r8, r14; lpMem
0x180009e49  xor     edx, edx; dwFlags
0x180009e4b  mov     rcx, rax; hHeap
0x180009e4e  call    cs:__imp_HeapFree
0x180009e54  mov     rcx, [rbp+188h]; this
0x180009e5b  mov     r9d, esi; char *
0x180009e5e  mov     edx, 137h; void *
0x180009e63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009e68  test    rdi, rdi
0x180009e6b  jz      short loc_180009E7E
0x180009e6d  mov     rcx, rdi; hMutex
0x180009e70  call    cs:__imp_ReleaseMutex
0x180009e76  test    eax, eax
0x180009e78  jz      loc_180009FD3
0x180009e7e  mov     rcx, rbx; hObject
0x180009e81  call    cs:__imp_CloseHandle
0x180009e87  test    eax, eax
0x180009e89  jz      loc_180009F66
0x180009e8f  jmp     loc_180009D68
0x180009e94  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180009e99  lea     rcx, [r14+28h]; void *
0x180009e9d  mov     dword ptr [r14], 1
0x180009ea4  xor     edx, edx; Val
0x180009ea6  mov     [r14+8], rbx
0x180009eaa  mov     r8d, 108h; Size
0x180009eb0  movdqu  xmmword ptr [r14+10h], xmm0
0x180009eb6  call    memset_0
0x180009ebb  xor     eax, eax
0x180009ebd  lea     rcx, [r14+28h]; this
0x180009ec1  mov     [r14+20h], rax
0x180009ec5  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180009eca  lea     rbx, [r14+0E8h]
0x180009ed1  xor     r8d, r8d; Flags
0x180009ed4  mov     rcx, rbx; lpCriticalSection
0x180009ed7  xor     edx, edx; dwSpinCount
0x180009ed9  call    cs:__imp_InitializeCriticalSectionEx
0x180009edf  mov     qword ptr [rbx+28h], 0
0x180009ee7  mov     qword ptr [rbx+30h], 0
0x180009eef  mov     qword ptr [rbx+38h], 0
0x180009ef7  mov     qword ptr [rbx+40h], 0
0x180009eff  xor     ebx, ebx
0x180009f01  mov     [r15], r14
0x180009f04  test    rdi, rdi
0x180009f07  jz      short loc_180009F1A
0x180009f09  mov     rcx, rdi; hMutex
0x180009f0c  call    cs:__imp_ReleaseMutex
0x180009f12  test    eax, eax
0x180009f14  jz      loc_180009FE5
0x180009f1a  test    rbx, rbx
0x180009f1d  jz      short loc_180009F2C
0x180009f1f  mov     rcx, rbx; hObject
0x180009f22  call    cs:__imp_CloseHandle
0x180009f28  test    eax, eax
0x180009f2a  jz      short loc_180009F54
0x180009f2c  xor     eax, eax
0x180009f2e  mov     rcx, [rbp+180h+var_30]
0x180009f35  xor     rcx, rsp; StackCookie
0x180009f38  call    __security_check_cookie
0x180009f3d  mov     rbx, [rsp+280h+arg_10]
0x180009f45  add     rsp, 260h
0x180009f4c  pop     r15
0x180009f4e  pop     r14
0x180009f50  pop     rdi
0x180009f51  pop     rsi
0x180009f52  pop     rbp
0x180009f53  retn
0x180009f54  mov     rcx, [rbp+188h]; this
0x180009f5b  mov     edx, 0A0Bh; void *
0x180009f60  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009f66  mov     rcx, [rbp+188h]; this
0x180009f6d  mov     edx, 0A0Bh; void *
0x180009f72  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009f78  mov     rcx, [rbp+188h]; this
0x180009f7f  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180009f85  mov     rcx, [rbp+188h]; this
0x180009f8c  mov     edx, 0A15h; void *
0x180009f91  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009f97  mov     rcx, [rbp+188h]; this
0x180009f9e  mov     edx, 0A0Bh; void *
0x180009fa3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009fa9  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180009faf  mov     rcx, [rbp+188h]; this
0x180009fb6  mov     edx, 0A0Bh; void *
0x180009fbb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009fc1  mov     rcx, [rbp+188h]; this
0x180009fc8  mov     edx, 0A0Bh; void *
0x180009fcd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009fd3  mov     rcx, [rbp+188h]; this
0x180009fda  mov     edx, 0A15h; void *
0x180009fdf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009fe5  mov     rcx, [rbp+188h]; this
0x180009fec  mov     edx, 0A15h; void *
0x180009ff1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
