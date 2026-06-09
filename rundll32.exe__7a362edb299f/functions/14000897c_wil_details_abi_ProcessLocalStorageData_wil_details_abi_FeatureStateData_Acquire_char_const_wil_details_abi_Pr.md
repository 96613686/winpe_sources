# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x14000897c`
- end: `0x140008d43`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x140008d4c`

## callees

- `0x1400015a0`
- `0x140002254`
- `0x140003ffc`
- `0x140004498`
- `0x140004c88`
- `0x1400058a8`
- `0x140005ed8`
- `0x140006328`
- `0x1400064cc`
- `0x140006ce8`
- `0x140006cf8`
- `0x1400083b8`
- `0x14000897c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400089f3`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400089f3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x140008c25`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x140008c25`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140008a95`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140008bbc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140008c58`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140008a95`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140008bbc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140008c58`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140008a14`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140008a14`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008b9a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008b9a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008b8c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008b8c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400089b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400089b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008aa6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008b66`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008b7e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008bcd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008c6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008aa6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008b66`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008b7e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008bcd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008c6e`

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
0x14000897c  mov     [rsp-8+arg_10], rbx
0x140008981  push    rbp
0x140008982  push    rsi
0x140008983  push    rdi
0x140008984  push    r14
0x140008986  push    r15
0x140008988  lea     rbp, [rsp-160h]
0x140008990  sub     rsp, 260h
0x140008997  mov     rax, cs:__security_cookie
0x14000899e  xor     rax, rsp
0x1400089a1  mov     [rbp+180h+var_30], rax
0x1400089a8  mov     r15, rdx
0x1400089ab  mov     qword ptr [rdx], 0
0x1400089b2  mov     rbx, rcx
0x1400089b5  call    cs:__imp_GetCurrentProcessId
0x1400089bb  mov     r14d, 130h
0x1400089c1  mov     [rsp+280h+var_258], rbx
0x1400089c6  mov     r9d, eax
0x1400089c9  mov     [rsp+280h+var_260], r14d; int
0x1400089ce  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1400089d5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400089da  lea     edx, [r14-2Ch]; unsigned __int64
0x1400089de  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400089e3  mov     r9d, 1F0001h; dwDesiredAccess
0x1400089e9  lea     rdx, [rsp+280h+Name]; lpName
0x1400089ee  xor     r8d, r8d; dwFlags
0x1400089f1  xor     ecx, ecx; lpMutexAttributes
0x1400089f3  call    cs:__imp_CreateMutexExW
0x1400089f9  mov     rbx, rax
0x1400089fc  test    rax, rax
0x1400089ff  jnz     short loc_140008A0B
0x140008a01  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140008a06  jmp     loc_140008C7A
0x140008a0b  xor     r8d, r8d; bAlertable
0x140008a0e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140008a11  mov     rcx, rbx; hHandle
0x140008a14  call    cs:__imp_WaitForSingleObjectEx
0x140008a1a  cmp     eax, 102h
0x140008a1f  jz      short loc_140008A31
0x140008a21  test    eax, 0FFFFFF7Fh
0x140008a26  jnz     loc_140008CC4
0x140008a2c  mov     rdi, rbx
0x140008a2f  jmp     short loc_140008A33
0x140008a31  xor     edi, edi
0x140008a33  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140008a38  mov     [rsp+280h+hObject], 0
0x140008a41  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140008a46  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140008a4b  mov     esi, eax
0x140008a4d  test    eax, eax
0x140008a4f  jns     short loc_140008ABB
0x140008a51  mov     rcx, [rbp+188h]; this
0x140008a58  mov     r9d, eax; char *
0x140008a5b  mov     edx, 66h ; 'f'; void *
0x140008a60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008a65  mov     rcx, [rbp+188h]; this
0x140008a6c  mov     r9d, esi; char *
0x140008a6f  mov     edx, 6Fh ; 'o'; void *
0x140008a74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008a79  mov     rcx, [rbp+188h]; this
0x140008a80  mov     r9d, esi; char *
0x140008a83  mov     edx, 12Eh; void *
0x140008a88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008a8d  test    rdi, rdi
0x140008a90  jz      short loc_140008AA3
0x140008a92  mov     rcx, rdi; hMutex
0x140008a95  call    cs:__imp_ReleaseMutex
0x140008a9b  test    eax, eax
0x140008a9d  jz      loc_140008CD1
0x140008aa3  mov     rcx, rbx; hObject
0x140008aa6  call    cs:__imp_CloseHandle
0x140008aac  test    eax, eax
0x140008aae  jz      loc_140008CE3
0x140008ab4  mov     eax, esi
0x140008ab6  jmp     loc_140008C7A
0x140008abb  mov     rax, [rsp+280h+hObject]
0x140008ac0  lea     rcx, ds:0[rax*4]
0x140008ac8  test    rcx, rcx
0x140008acb  jz      short loc_140008ADB
0x140008acd  mov     [r15], rcx
0x140008ad0  mov     eax, [rcx]
0x140008ad2  inc     eax
0x140008ad4  mov     [rcx], eax
0x140008ad6  jmp     loc_140008C50
0x140008adb  mov     rdx, r14; dwBytes
0x140008ade  mov     qword ptr [r15], 0
0x140008ae5  mov     ecx, 8; dwFlags
0x140008aea  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140008aef  mov     r14, rax
0x140008af2  test    rax, rax
0x140008af5  jnz     short loc_140008B15
0x140008af7  mov     rcx, [rbp+188h]; this
0x140008afe  mov     esi, 8007000Eh
0x140008b03  mov     r9d, esi; char *
0x140008b06  mov     edx, 14Bh; void *
0x140008b0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008b10  jmp     loc_140008BA0
0x140008b15  xorps   xmm0, xmm0
0x140008b18  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x140008b1e  test    r14b, 3
0x140008b22  jnz     loc_140008CF5
0x140008b28  mov     r9, r14
0x140008b2b  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140008b30  shr     r9, 2; unsigned __int64
0x140008b34  lea     rcx, [rsp+280h+hObject]; this
0x140008b39  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140008b3e  mov     esi, eax
0x140008b40  test    eax, eax
0x140008b42  jns     loc_140008BE0
0x140008b48  mov     rcx, [rbp+188h]; this
0x140008b4f  mov     r9d, eax; char *
0x140008b52  mov     edx, 14Eh; void *
0x140008b57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008b5c  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140008b61  test    rcx, rcx
0x140008b64  jz      short loc_140008B74
0x140008b66  call    cs:__imp_CloseHandle
0x140008b6c  test    eax, eax
0x140008b6e  jz      loc_140008CFB
0x140008b74  mov     rcx, [rsp+280h+hObject]; hObject
0x140008b79  test    rcx, rcx
0x140008b7c  jz      short loc_140008B8C
0x140008b7e  call    cs:__imp_CloseHandle
0x140008b84  test    eax, eax
0x140008b86  jz      loc_140008D0D
0x140008b8c  call    cs:__imp_GetProcessHeap
0x140008b92  mov     r8, r14; lpMem
0x140008b95  xor     edx, edx; dwFlags
0x140008b97  mov     rcx, rax; hHeap
0x140008b9a  call    cs:__imp_HeapFree
0x140008ba0  mov     rcx, [rbp+188h]; this
0x140008ba7  mov     r9d, esi; char *
0x140008baa  mov     edx, 137h; void *
0x140008baf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008bb4  test    rdi, rdi
0x140008bb7  jz      short loc_140008BCA
0x140008bb9  mov     rcx, rdi; hMutex
0x140008bbc  call    cs:__imp_ReleaseMutex
0x140008bc2  test    eax, eax
0x140008bc4  jz      loc_140008D1F
0x140008bca  mov     rcx, rbx; hObject
0x140008bcd  call    cs:__imp_CloseHandle
0x140008bd3  test    eax, eax
0x140008bd5  jz      loc_140008CB2
0x140008bdb  jmp     loc_140008AB4
0x140008be0  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x140008be5  lea     rcx, [r14+28h]; void *
0x140008be9  mov     dword ptr [r14], 1
0x140008bf0  xor     edx, edx; Val
0x140008bf2  mov     [r14+8], rbx
0x140008bf6  mov     r8d, 108h; Size
0x140008bfc  movdqu  xmmword ptr [r14+10h], xmm0
0x140008c02  call    memset_0
0x140008c07  xor     eax, eax
0x140008c09  lea     rcx, [r14+28h]; this
0x140008c0d  mov     [r14+20h], rax
0x140008c11  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140008c16  lea     rbx, [r14+0E8h]
0x140008c1d  xor     r8d, r8d; Flags
0x140008c20  mov     rcx, rbx; lpCriticalSection
0x140008c23  xor     edx, edx; dwSpinCount
0x140008c25  call    cs:__imp_InitializeCriticalSectionEx
0x140008c2b  mov     qword ptr [rbx+28h], 0
0x140008c33  mov     qword ptr [rbx+30h], 0
0x140008c3b  mov     qword ptr [rbx+38h], 0
0x140008c43  mov     qword ptr [rbx+40h], 0
0x140008c4b  xor     ebx, ebx
0x140008c4d  mov     [r15], r14
0x140008c50  test    rdi, rdi
0x140008c53  jz      short loc_140008C66
0x140008c55  mov     rcx, rdi; hMutex
0x140008c58  call    cs:__imp_ReleaseMutex
0x140008c5e  test    eax, eax
0x140008c60  jz      loc_140008D31
0x140008c66  test    rbx, rbx
0x140008c69  jz      short loc_140008C78
0x140008c6b  mov     rcx, rbx; hObject
0x140008c6e  call    cs:__imp_CloseHandle
0x140008c74  test    eax, eax
0x140008c76  jz      short loc_140008CA0
0x140008c78  xor     eax, eax
0x140008c7a  mov     rcx, [rbp+180h+var_30]
0x140008c81  xor     rcx, rsp; StackCookie
0x140008c84  call    __security_check_cookie
0x140008c89  mov     rbx, [rsp+280h+arg_10]
0x140008c91  add     rsp, 260h
0x140008c98  pop     r15
0x140008c9a  pop     r14
0x140008c9c  pop     rdi
0x140008c9d  pop     rsi
0x140008c9e  pop     rbp
0x140008c9f  retn
0x140008ca0  mov     rcx, [rbp+188h]; this
0x140008ca7  mov     edx, 0A0Bh; void *
0x140008cac  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008cb2  mov     rcx, [rbp+188h]; this
0x140008cb9  mov     edx, 0A0Bh; void *
0x140008cbe  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008cc4  mov     rcx, [rbp+188h]; this
0x140008ccb  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140008cd1  mov     rcx, [rbp+188h]; this
0x140008cd8  mov     edx, 0A15h; void *
0x140008cdd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008ce3  mov     rcx, [rbp+188h]; this
0x140008cea  mov     edx, 0A0Bh; void *
0x140008cef  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008cf5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140008cfb  mov     rcx, [rbp+188h]; this
0x140008d02  mov     edx, 0A0Bh; void *
0x140008d07  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008d0d  mov     rcx, [rbp+188h]; this
0x140008d14  mov     edx, 0A0Bh; void *
0x140008d19  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008d1f  mov     rcx, [rbp+188h]; this
0x140008d26  mov     edx, 0A15h; void *
0x140008d2b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008d31  mov     rcx, [rbp+188h]; this
0x140008d38  mov     edx, 0A15h; void *
0x140008d3d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
