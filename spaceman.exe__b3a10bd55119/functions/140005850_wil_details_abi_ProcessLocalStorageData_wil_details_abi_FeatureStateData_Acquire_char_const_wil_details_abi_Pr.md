# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x140005850`
- end: `0x140005c17`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1400060a4`

## callees

- `0x140004d60`
- `0x140005850`
- `0x140005dd0`
- `0x140006234`
- `0x140006b58`
- `0x140007748`
- `0x1400089e0`
- `0x1400090b0`
- `0x140009838`
- `0x14000a00c`
- `0x14000a01c`
- `0x14000d1be`
- `0x14000d1f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x140005af9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x140005af9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400058c7`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400058c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140005969`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140005a90`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140005b2c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140005969`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140005a90`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140005b2c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400058e8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400058e8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140005889`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140005889`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005a6e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005a6e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005a60`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005a60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000597a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005a3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005a52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005aa1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005b42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000597a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005a3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005a52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005aa1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005b42`

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
0x140005850  mov     [rsp-8+arg_10], rbx
0x140005855  push    rbp
0x140005856  push    rsi
0x140005857  push    rdi
0x140005858  push    r14
0x14000585a  push    r15
0x14000585c  lea     rbp, [rsp-160h]
0x140005864  sub     rsp, 260h
0x14000586b  mov     rax, cs:__security_cookie
0x140005872  xor     rax, rsp
0x140005875  mov     [rbp+180h+var_30], rax
0x14000587c  mov     r15, rdx
0x14000587f  mov     qword ptr [rdx], 0
0x140005886  mov     rbx, rcx
0x140005889  call    cs:__imp_GetCurrentProcessId
0x14000588f  mov     r14d, 130h
0x140005895  mov     [rsp+280h+var_258], rbx
0x14000589a  mov     r9d, eax
0x14000589d  mov     [rsp+280h+var_260], r14d; int
0x1400058a2  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1400058a9  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400058ae  lea     edx, [r14-2Ch]; unsigned __int64
0x1400058b2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400058b7  mov     r9d, 1F0001h; dwDesiredAccess
0x1400058bd  lea     rdx, [rsp+280h+Name]; lpName
0x1400058c2  xor     r8d, r8d; dwFlags
0x1400058c5  xor     ecx, ecx; lpMutexAttributes
0x1400058c7  call    cs:__imp_CreateMutexExW
0x1400058cd  mov     rbx, rax
0x1400058d0  test    rax, rax
0x1400058d3  jnz     short loc_1400058DF
0x1400058d5  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400058da  jmp     loc_140005B4E
0x1400058df  xor     r8d, r8d; bAlertable
0x1400058e2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400058e5  mov     rcx, rbx; hHandle
0x1400058e8  call    cs:__imp_WaitForSingleObjectEx
0x1400058ee  cmp     eax, 102h
0x1400058f3  jz      short loc_140005905
0x1400058f5  test    eax, 0FFFFFF7Fh
0x1400058fa  jnz     loc_140005B98
0x140005900  mov     rdi, rbx
0x140005903  jmp     short loc_140005907
0x140005905  xor     edi, edi
0x140005907  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x14000590c  mov     [rsp+280h+hObject], 0
0x140005915  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000591a  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x14000591f  mov     esi, eax
0x140005921  test    eax, eax
0x140005923  jns     short loc_14000598F
0x140005925  mov     rcx, [rbp+188h]; this
0x14000592c  mov     r9d, eax; char *
0x14000592f  mov     edx, 66h ; 'f'; void *
0x140005934  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005939  mov     rcx, [rbp+188h]; this
0x140005940  mov     r9d, esi; char *
0x140005943  mov     edx, 6Fh ; 'o'; void *
0x140005948  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000594d  mov     rcx, [rbp+188h]; this
0x140005954  mov     r9d, esi; char *
0x140005957  mov     edx, 12Eh; void *
0x14000595c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005961  test    rdi, rdi
0x140005964  jz      short loc_140005977
0x140005966  mov     rcx, rdi; hMutex
0x140005969  call    cs:__imp_ReleaseMutex
0x14000596f  test    eax, eax
0x140005971  jz      loc_140005BA5
0x140005977  mov     rcx, rbx; hObject
0x14000597a  call    cs:__imp_CloseHandle
0x140005980  test    eax, eax
0x140005982  jz      loc_140005BB7
0x140005988  mov     eax, esi
0x14000598a  jmp     loc_140005B4E
0x14000598f  mov     rax, [rsp+280h+hObject]
0x140005994  lea     rcx, ds:0[rax*4]
0x14000599c  test    rcx, rcx
0x14000599f  jz      short loc_1400059AF
0x1400059a1  mov     [r15], rcx
0x1400059a4  mov     eax, [rcx]
0x1400059a6  inc     eax
0x1400059a8  mov     [rcx], eax
0x1400059aa  jmp     loc_140005B24
0x1400059af  mov     rdx, r14; dwBytes
0x1400059b2  mov     qword ptr [r15], 0
0x1400059b9  mov     ecx, 8; dwFlags
0x1400059be  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400059c3  mov     r14, rax
0x1400059c6  test    rax, rax
0x1400059c9  jnz     short loc_1400059E9
0x1400059cb  mov     rcx, [rbp+188h]; this
0x1400059d2  mov     esi, 8007000Eh
0x1400059d7  mov     r9d, esi; char *
0x1400059da  mov     edx, 14Bh; void *
0x1400059df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400059e4  jmp     loc_140005A74
0x1400059e9  xorps   xmm0, xmm0
0x1400059ec  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1400059f2  test    r14b, 3
0x1400059f6  jnz     loc_140005BC9
0x1400059fc  mov     r9, r14
0x1400059ff  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140005a04  shr     r9, 2; unsigned __int64
0x140005a08  lea     rcx, [rsp+280h+hObject]; this
0x140005a0d  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140005a12  mov     esi, eax
0x140005a14  test    eax, eax
0x140005a16  jns     loc_140005AB4
0x140005a1c  mov     rcx, [rbp+188h]; this
0x140005a23  mov     r9d, eax; char *
0x140005a26  mov     edx, 14Eh; void *
0x140005a2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005a30  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140005a35  test    rcx, rcx
0x140005a38  jz      short loc_140005A48
0x140005a3a  call    cs:__imp_CloseHandle
0x140005a40  test    eax, eax
0x140005a42  jz      loc_140005BCF
0x140005a48  mov     rcx, [rsp+280h+hObject]; hObject
0x140005a4d  test    rcx, rcx
0x140005a50  jz      short loc_140005A60
0x140005a52  call    cs:__imp_CloseHandle
0x140005a58  test    eax, eax
0x140005a5a  jz      loc_140005BE1
0x140005a60  call    cs:__imp_GetProcessHeap
0x140005a66  mov     r8, r14; lpMem
0x140005a69  xor     edx, edx; dwFlags
0x140005a6b  mov     rcx, rax; hHeap
0x140005a6e  call    cs:__imp_HeapFree
0x140005a74  mov     rcx, [rbp+188h]; this
0x140005a7b  mov     r9d, esi; char *
0x140005a7e  mov     edx, 137h; void *
0x140005a83  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005a88  test    rdi, rdi
0x140005a8b  jz      short loc_140005A9E
0x140005a8d  mov     rcx, rdi; hMutex
0x140005a90  call    cs:__imp_ReleaseMutex
0x140005a96  test    eax, eax
0x140005a98  jz      loc_140005BF3
0x140005a9e  mov     rcx, rbx; hObject
0x140005aa1  call    cs:__imp_CloseHandle
0x140005aa7  test    eax, eax
0x140005aa9  jz      loc_140005B86
0x140005aaf  jmp     loc_140005988
0x140005ab4  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x140005ab9  lea     rcx, [r14+28h]; void *
0x140005abd  mov     dword ptr [r14], 1
0x140005ac4  xor     edx, edx; Val
0x140005ac6  mov     [r14+8], rbx
0x140005aca  mov     r8d, 108h; Size
0x140005ad0  movdqu  xmmword ptr [r14+10h], xmm0
0x140005ad6  call    memset_0
0x140005adb  xor     eax, eax
0x140005add  lea     rcx, [r14+28h]; this
0x140005ae1  mov     [r14+20h], rax
0x140005ae5  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140005aea  lea     rbx, [r14+0E8h]
0x140005af1  xor     r8d, r8d; Flags
0x140005af4  mov     rcx, rbx; lpCriticalSection
0x140005af7  xor     edx, edx; dwSpinCount
0x140005af9  call    cs:__imp_InitializeCriticalSectionEx
0x140005aff  mov     qword ptr [rbx+28h], 0
0x140005b07  mov     qword ptr [rbx+30h], 0
0x140005b0f  mov     qword ptr [rbx+38h], 0
0x140005b17  mov     qword ptr [rbx+40h], 0
0x140005b1f  xor     ebx, ebx
0x140005b21  mov     [r15], r14
0x140005b24  test    rdi, rdi
0x140005b27  jz      short loc_140005B3A
0x140005b29  mov     rcx, rdi; hMutex
0x140005b2c  call    cs:__imp_ReleaseMutex
0x140005b32  test    eax, eax
0x140005b34  jz      loc_140005C05
0x140005b3a  test    rbx, rbx
0x140005b3d  jz      short loc_140005B4C
0x140005b3f  mov     rcx, rbx; hObject
0x140005b42  call    cs:__imp_CloseHandle
0x140005b48  test    eax, eax
0x140005b4a  jz      short loc_140005B74
0x140005b4c  xor     eax, eax
0x140005b4e  mov     rcx, [rbp+180h+var_30]
0x140005b55  xor     rcx, rsp; StackCookie
0x140005b58  call    __security_check_cookie
0x140005b5d  mov     rbx, [rsp+280h+arg_10]
0x140005b65  add     rsp, 260h
0x140005b6c  pop     r15
0x140005b6e  pop     r14
0x140005b70  pop     rdi
0x140005b71  pop     rsi
0x140005b72  pop     rbp
0x140005b73  retn
0x140005b74  mov     rcx, [rbp+188h]; this
0x140005b7b  mov     edx, 0A0Bh; void *
0x140005b80  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005b86  mov     rcx, [rbp+188h]; this
0x140005b8d  mov     edx, 0A0Bh; void *
0x140005b92  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005b98  mov     rcx, [rbp+188h]; this
0x140005b9f  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140005ba5  mov     rcx, [rbp+188h]; this
0x140005bac  mov     edx, 0A15h; void *
0x140005bb1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005bb7  mov     rcx, [rbp+188h]; this
0x140005bbe  mov     edx, 0A0Bh; void *
0x140005bc3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005bc9  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140005bcf  mov     rcx, [rbp+188h]; this
0x140005bd6  mov     edx, 0A0Bh; void *
0x140005bdb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005be1  mov     rcx, [rbp+188h]; this
0x140005be8  mov     edx, 0A0Bh; void *
0x140005bed  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005bf3  mov     rcx, [rbp+188h]; this
0x140005bfa  mov     edx, 0A15h; void *
0x140005bff  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005c05  mov     rcx, [rbp+188h]; this
0x140005c0c  mov     edx, 0A15h; void *
0x140005c11  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
