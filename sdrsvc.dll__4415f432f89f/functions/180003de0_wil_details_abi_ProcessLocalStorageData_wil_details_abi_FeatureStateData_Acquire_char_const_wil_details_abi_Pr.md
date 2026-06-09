# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180003de0`
- end: `0x1800041a7`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180004494`

## callees

- `0x1800031e0`
- `0x180003de0`
- `0x1800041b0`
- `0x1800046e8`
- `0x180005008`
- `0x180005ce8`
- `0x180007204`
- `0x180007758`
- `0x180007b34`
- `0x1800083ec`
- `0x1800083fc`
- `0x18002170a`
- `0x180021740`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180004089`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180004089`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003e57`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003e57`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003e78`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003e78`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003ef9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004020`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800040bc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003ef9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004020`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800040bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003ff0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003ff0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003ffe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003ffe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003e19`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003e19`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003fca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003fe2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004031`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003fca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003fe2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004031`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040d2`

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
0x180003de0  mov     [rsp-8+arg_10], rbx
0x180003de5  push    rbp
0x180003de6  push    rsi
0x180003de7  push    rdi
0x180003de8  push    r14
0x180003dea  push    r15
0x180003dec  lea     rbp, [rsp-160h]
0x180003df4  sub     rsp, 260h
0x180003dfb  mov     rax, cs:__security_cookie
0x180003e02  xor     rax, rsp
0x180003e05  mov     [rbp+180h+var_30], rax
0x180003e0c  mov     r15, rdx
0x180003e0f  mov     qword ptr [rdx], 0
0x180003e16  mov     rbx, rcx
0x180003e19  call    cs:__imp_GetCurrentProcessId
0x180003e1f  mov     r14d, 130h
0x180003e25  mov     [rsp+280h+var_258], rbx
0x180003e2a  mov     r9d, eax
0x180003e2d  mov     [rsp+280h+var_260], r14d; int
0x180003e32  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003e39  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003e3e  lea     edx, [r14-2Ch]; unsigned __int64
0x180003e42  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003e47  mov     r9d, 1F0001h; dwDesiredAccess
0x180003e4d  lea     rdx, [rsp+280h+Name]; lpName
0x180003e52  xor     r8d, r8d; dwFlags
0x180003e55  xor     ecx, ecx; lpMutexAttributes
0x180003e57  call    cs:__imp_CreateMutexExW
0x180003e5d  mov     rbx, rax
0x180003e60  test    rax, rax
0x180003e63  jnz     short loc_180003E6F
0x180003e65  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003e6a  jmp     loc_1800040DE
0x180003e6f  xor     r8d, r8d; bAlertable
0x180003e72  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003e75  mov     rcx, rbx; hHandle
0x180003e78  call    cs:__imp_WaitForSingleObjectEx
0x180003e7e  cmp     eax, 102h
0x180003e83  jz      short loc_180003E95
0x180003e85  test    eax, 0FFFFFF7Fh
0x180003e8a  jnz     loc_180004128
0x180003e90  mov     rdi, rbx
0x180003e93  jmp     short loc_180003E97
0x180003e95  xor     edi, edi
0x180003e97  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003e9c  mov     [rsp+280h+hObject], 0
0x180003ea5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003eaa  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003eaf  mov     esi, eax
0x180003eb1  test    eax, eax
0x180003eb3  jns     short loc_180003F1F
0x180003eb5  mov     rcx, [rbp+188h]; this
0x180003ebc  mov     r9d, eax; char *
0x180003ebf  mov     edx, 66h ; 'f'; void *
0x180003ec4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003ec9  mov     rcx, [rbp+188h]; this
0x180003ed0  mov     r9d, esi; char *
0x180003ed3  mov     edx, 6Fh ; 'o'; void *
0x180003ed8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003edd  mov     rcx, [rbp+188h]; this
0x180003ee4  mov     r9d, esi; char *
0x180003ee7  mov     edx, 12Eh; void *
0x180003eec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003ef1  test    rdi, rdi
0x180003ef4  jz      short loc_180003F07
0x180003ef6  mov     rcx, rdi; hMutex
0x180003ef9  call    cs:__imp_ReleaseMutex
0x180003eff  test    eax, eax
0x180003f01  jz      loc_180004135
0x180003f07  mov     rcx, rbx; hObject
0x180003f0a  call    cs:__imp_CloseHandle
0x180003f10  test    eax, eax
0x180003f12  jz      loc_180004147
0x180003f18  mov     eax, esi
0x180003f1a  jmp     loc_1800040DE
0x180003f1f  mov     rax, [rsp+280h+hObject]
0x180003f24  lea     rcx, ds:0[rax*4]
0x180003f2c  test    rcx, rcx
0x180003f2f  jz      short loc_180003F3F
0x180003f31  mov     [r15], rcx
0x180003f34  mov     eax, [rcx]
0x180003f36  inc     eax
0x180003f38  mov     [rcx], eax
0x180003f3a  jmp     loc_1800040B4
0x180003f3f  mov     rdx, r14; dwBytes
0x180003f42  mov     qword ptr [r15], 0
0x180003f49  mov     ecx, 8; dwFlags
0x180003f4e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003f53  mov     r14, rax
0x180003f56  test    rax, rax
0x180003f59  jnz     short loc_180003F79
0x180003f5b  mov     rcx, [rbp+188h]; this
0x180003f62  mov     esi, 8007000Eh
0x180003f67  mov     r9d, esi; char *
0x180003f6a  mov     edx, 14Bh; void *
0x180003f6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003f74  jmp     loc_180004004
0x180003f79  xorps   xmm0, xmm0
0x180003f7c  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003f82  test    r14b, 3
0x180003f86  jnz     loc_180004159
0x180003f8c  mov     r9, r14
0x180003f8f  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180003f94  shr     r9, 2; unsigned __int64
0x180003f98  lea     rcx, [rsp+280h+hObject]; this
0x180003f9d  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180003fa2  mov     esi, eax
0x180003fa4  test    eax, eax
0x180003fa6  jns     loc_180004044
0x180003fac  mov     rcx, [rbp+188h]; this
0x180003fb3  mov     r9d, eax; char *
0x180003fb6  mov     edx, 14Eh; void *
0x180003fbb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003fc0  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180003fc5  test    rcx, rcx
0x180003fc8  jz      short loc_180003FD8
0x180003fca  call    cs:__imp_CloseHandle
0x180003fd0  test    eax, eax
0x180003fd2  jz      loc_18000415F
0x180003fd8  mov     rcx, [rsp+280h+hObject]; hObject
0x180003fdd  test    rcx, rcx
0x180003fe0  jz      short loc_180003FF0
0x180003fe2  call    cs:__imp_CloseHandle
0x180003fe8  test    eax, eax
0x180003fea  jz      loc_180004171
0x180003ff0  call    cs:__imp_GetProcessHeap
0x180003ff6  mov     r8, r14; lpMem
0x180003ff9  xor     edx, edx; dwFlags
0x180003ffb  mov     rcx, rax; hHeap
0x180003ffe  call    cs:__imp_HeapFree
0x180004004  mov     rcx, [rbp+188h]; this
0x18000400b  mov     r9d, esi; char *
0x18000400e  mov     edx, 137h; void *
0x180004013  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004018  test    rdi, rdi
0x18000401b  jz      short loc_18000402E
0x18000401d  mov     rcx, rdi; hMutex
0x180004020  call    cs:__imp_ReleaseMutex
0x180004026  test    eax, eax
0x180004028  jz      loc_180004183
0x18000402e  mov     rcx, rbx; hObject
0x180004031  call    cs:__imp_CloseHandle
0x180004037  test    eax, eax
0x180004039  jz      loc_180004116
0x18000403f  jmp     loc_180003F18
0x180004044  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180004049  lea     rcx, [r14+28h]; void *
0x18000404d  mov     dword ptr [r14], 1
0x180004054  xor     edx, edx; Val
0x180004056  mov     [r14+8], rbx
0x18000405a  mov     r8d, 108h; Size
0x180004060  movdqu  xmmword ptr [r14+10h], xmm0
0x180004066  call    memset_0
0x18000406b  xor     eax, eax
0x18000406d  lea     rcx, [r14+28h]; this
0x180004071  mov     [r14+20h], rax
0x180004075  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000407a  lea     rbx, [r14+0E8h]
0x180004081  xor     r8d, r8d; Flags
0x180004084  mov     rcx, rbx; lpCriticalSection
0x180004087  xor     edx, edx; dwSpinCount
0x180004089  call    cs:__imp_InitializeCriticalSectionEx
0x18000408f  mov     qword ptr [rbx+28h], 0
0x180004097  mov     qword ptr [rbx+30h], 0
0x18000409f  mov     qword ptr [rbx+38h], 0
0x1800040a7  mov     qword ptr [rbx+40h], 0
0x1800040af  xor     ebx, ebx
0x1800040b1  mov     [r15], r14
0x1800040b4  test    rdi, rdi
0x1800040b7  jz      short loc_1800040CA
0x1800040b9  mov     rcx, rdi; hMutex
0x1800040bc  call    cs:__imp_ReleaseMutex
0x1800040c2  test    eax, eax
0x1800040c4  jz      loc_180004195
0x1800040ca  test    rbx, rbx
0x1800040cd  jz      short loc_1800040DC
0x1800040cf  mov     rcx, rbx; hObject
0x1800040d2  call    cs:__imp_CloseHandle
0x1800040d8  test    eax, eax
0x1800040da  jz      short loc_180004104
0x1800040dc  xor     eax, eax
0x1800040de  mov     rcx, [rbp+180h+var_30]
0x1800040e5  xor     rcx, rsp; StackCookie
0x1800040e8  call    __security_check_cookie
0x1800040ed  mov     rbx, [rsp+280h+arg_10]
0x1800040f5  add     rsp, 260h
0x1800040fc  pop     r15
0x1800040fe  pop     r14
0x180004100  pop     rdi
0x180004101  pop     rsi
0x180004102  pop     rbp
0x180004103  retn
0x180004104  mov     rcx, [rbp+188h]; this
0x18000410b  mov     edx, 0A0Bh; void *
0x180004110  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004116  mov     rcx, [rbp+188h]; this
0x18000411d  mov     edx, 0A0Bh; void *
0x180004122  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004128  mov     rcx, [rbp+188h]; this
0x18000412f  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180004135  mov     rcx, [rbp+188h]; this
0x18000413c  mov     edx, 0A15h; void *
0x180004141  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004147  mov     rcx, [rbp+188h]; this
0x18000414e  mov     edx, 0A0Bh; void *
0x180004153  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004159  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000415f  mov     rcx, [rbp+188h]; this
0x180004166  mov     edx, 0A0Bh; void *
0x18000416b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004171  mov     rcx, [rbp+188h]; this
0x180004178  mov     edx, 0A0Bh; void *
0x18000417d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004183  mov     rcx, [rbp+188h]; this
0x18000418a  mov     edx, 0A15h; void *
0x18000418f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004195  mov     rcx, [rbp+188h]; this
0x18000419c  mov     edx, 0A15h; void *
0x1800041a1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
