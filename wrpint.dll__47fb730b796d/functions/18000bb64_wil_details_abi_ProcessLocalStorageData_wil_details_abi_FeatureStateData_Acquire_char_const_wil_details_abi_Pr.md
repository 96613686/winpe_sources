# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000bb64`
- end: `0x18000bf55`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x18000c344`

## callees

- `0x18000b0bc`
- `0x18000bb64`
- `0x18000bf5c`
- `0x18000c4f0`
- `0x18000ce18`
- `0x18000da6c`
- `0x18000ed74`
- `0x18000f2f4`
- `0x18000f648`
- `0x18000ff0c`
- `0x18000ff1c`
- `0x18001b77a`
- `0x18001b7b0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bca3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bd71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bd89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bddf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000be80`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bca3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bd71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bd89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bddf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000be80`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000bb9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000bb9d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000bc92`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000bdce`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000be6a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000bc92`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000bdce`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000be6a`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000bbdb`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000bbdb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000bbfc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000bbfc`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000be37`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000be37`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bd97`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bd97`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bda5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bda5`

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
  __int64 v16; // r8
  const char *v17; // r9
  __int64 v18; // r8
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  bool v23; // r8
  _DWORD *v24; // r14
  int v25; // eax
  __int64 v26; // r8
  const char *v27; // r9
  __int64 v28; // r8
  const char *v29; // r9
  HANDLE ProcessHeap; // rax
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
  const char *v34; // r9
  __int128 v35; // xmm0
  __int64 v36; // r8
  const char *v37; // r9
  __int64 v38; // r8
  const char *v39; // r9
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
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
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v40);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v41);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v16, v17);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v18, v19);
    return v15;
  }
  v20 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v20;
    ++*v20;
    goto LABEL_28;
  }
  *a2 = 0;
  v21 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v24 = (_DWORD *)v21;
  if ( !v21 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
LABEL_23:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v15, v42);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v31, v32);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    return v15;
  }
  *(_OWORD *)hObject = 0;
  if ( (v21 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
  v25 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)hObject,
          Name,
          v23,
          v21 >> 2);
  v15 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v25, 304);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
    goto LABEL_23;
  }
  v35 = *(_OWORD *)hObject;
  *v24 = 1;
  *((_QWORD *)v24 + 1) = v6;
  *((_OWORD *)v24 + 1) = v35;
  memset_0(v24 + 10, 0, 0x108u);
  *((_QWORD *)v24 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v24 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v24 + 58), 0, 0);
  *((_QWORD *)v24 + 34) = 0;
  *((_QWORD *)v24 + 35) = 0;
  *((_QWORD *)v24 + 36) = 0;
  *((_QWORD *)v24 + 37) = 0;
  v6 = 0;
  *a2 = v24;
LABEL_28:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
  return 0;
}

```

## disassembly

```asm
0x18000bb64  mov     [rsp-8+arg_10], rbx
0x18000bb69  push    rbp
0x18000bb6a  push    rsi
0x18000bb6b  push    rdi
0x18000bb6c  push    r14
0x18000bb6e  push    r15
0x18000bb70  lea     rbp, [rsp-160h]
0x18000bb78  sub     rsp, 260h
0x18000bb7f  mov     rax, cs:__security_cookie
0x18000bb86  xor     rax, rsp
0x18000bb89  mov     [rbp+180h+var_30], rax
0x18000bb90  mov     r15, rdx
0x18000bb93  mov     qword ptr [rdx], 0
0x18000bb9a  mov     rbx, rcx
0x18000bb9d  call    cs:__imp_GetCurrentProcessId
0x18000bba3  mov     r14d, 130h
0x18000bba9  mov     [rsp+280h+var_258], rbx
0x18000bbae  mov     r9d, eax
0x18000bbb1  mov     [rsp+280h+var_260], r14d; int
0x18000bbb6  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000bbbd  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000bbc2  lea     edx, [r14-2Ch]; unsigned __int64
0x18000bbc6  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18000bbcb  mov     r9d, 1F0001h; dwDesiredAccess
0x18000bbd1  lea     rdx, [rsp+280h+Name]; lpName
0x18000bbd6  xor     r8d, r8d; dwFlags
0x18000bbd9  xor     ecx, ecx; lpMutexAttributes
0x18000bbdb  call    cs:__imp_CreateMutexExW
0x18000bbe1  mov     rbx, rax
0x18000bbe4  test    rax, rax
0x18000bbe7  jnz     short loc_18000BBF3
0x18000bbe9  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000bbee  jmp     loc_18000BE8C
0x18000bbf3  xor     r8d, r8d; bAlertable
0x18000bbf6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000bbf9  mov     rcx, rbx; hHandle
0x18000bbfc  call    cs:__imp_WaitForSingleObjectEx
0x18000bc02  cmp     eax, 102h
0x18000bc07  jz      short loc_18000BC19
0x18000bc09  test    eax, 0FFFFFF7Fh
0x18000bc0e  jnz     loc_18000BED6
0x18000bc14  mov     rdi, rbx
0x18000bc17  jmp     short loc_18000BC1B
0x18000bc19  xor     edi, edi
0x18000bc1b  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x18000bc20  mov     [rsp+280h+hObject], 0
0x18000bc29  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000bc2e  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x18000bc33  mov     esi, eax
0x18000bc35  test    eax, eax
0x18000bc37  jns     short loc_18000BCB8
0x18000bc39  mov     rcx, [rbp+188h]; this
0x18000bc40  lea     r8, aWil; "wil"
0x18000bc47  mov     r9d, eax; char *
0x18000bc4a  mov     edx, 66h ; 'f'; void *
0x18000bc4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bc54  mov     rcx, [rbp+188h]; this
0x18000bc5b  lea     r8, aWil; "wil"
0x18000bc62  mov     r9d, esi; char *
0x18000bc65  mov     edx, 6Fh ; 'o'; void *
0x18000bc6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bc6f  mov     rcx, [rbp+188h]; this
0x18000bc76  lea     r8, aWil; "wil"
0x18000bc7d  mov     r9d, esi; char *
0x18000bc80  mov     edx, 12Eh; void *
0x18000bc85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bc8a  test    rdi, rdi
0x18000bc8d  jz      short loc_18000BCA0
0x18000bc8f  mov     rcx, rdi; hMutex
0x18000bc92  call    cs:__imp_ReleaseMutex
0x18000bc98  test    eax, eax
0x18000bc9a  jz      loc_18000BEE3
0x18000bca0  mov     rcx, rbx; hObject
0x18000bca3  call    cs:__imp_CloseHandle
0x18000bca9  test    eax, eax
0x18000bcab  jz      loc_18000BEF5
0x18000bcb1  mov     eax, esi
0x18000bcb3  jmp     loc_18000BE8C
0x18000bcb8  mov     rax, [rsp+280h+hObject]
0x18000bcbd  lea     rcx, ds:0[rax*4]
0x18000bcc5  test    rcx, rcx
0x18000bcc8  jz      short loc_18000BCD8
0x18000bcca  mov     [r15], rcx
0x18000bccd  mov     eax, [rcx]
0x18000bccf  inc     eax
0x18000bcd1  mov     [rcx], eax
0x18000bcd3  jmp     loc_18000BE62
0x18000bcd8  mov     rdx, r14; dwBytes
0x18000bcdb  mov     qword ptr [r15], 0
0x18000bce2  mov     ecx, 8; dwFlags
0x18000bce7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000bcec  mov     r14, rax
0x18000bcef  test    rax, rax
0x18000bcf2  jnz     short loc_18000BD19
0x18000bcf4  mov     rcx, [rbp+188h]; this
0x18000bcfb  lea     r8, aWil; "wil"
0x18000bd02  mov     esi, 8007000Eh
0x18000bd07  mov     edx, 14Bh; void *
0x18000bd0c  mov     r9d, esi; char *
0x18000bd0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bd14  jmp     loc_18000BDAB
0x18000bd19  xorps   xmm0, xmm0
0x18000bd1c  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x18000bd22  test    r14b, 3
0x18000bd26  jnz     loc_18000BF07
0x18000bd2c  mov     r9, r14
0x18000bd2f  lea     rdx, [rsp+280h+Name]; wchar_t *
0x18000bd34  shr     r9, 2; unsigned __int64
0x18000bd38  lea     rcx, [rsp+280h+hObject]; this
0x18000bd3d  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x18000bd42  mov     esi, eax
0x18000bd44  test    eax, eax
0x18000bd46  jns     loc_18000BDF2
0x18000bd4c  mov     rcx, [rbp+188h]; this
0x18000bd53  lea     r8, aWil; "wil"
0x18000bd5a  mov     r9d, eax; char *
0x18000bd5d  mov     edx, 14Eh; void *
0x18000bd62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bd67  mov     rcx, [rsp+280h+hObject+8]; hObject
0x18000bd6c  test    rcx, rcx
0x18000bd6f  jz      short loc_18000BD7F
0x18000bd71  call    cs:__imp_CloseHandle
0x18000bd77  test    eax, eax
0x18000bd79  jz      loc_18000BF0D
0x18000bd7f  mov     rcx, [rsp+280h+hObject]; hObject
0x18000bd84  test    rcx, rcx
0x18000bd87  jz      short loc_18000BD97
0x18000bd89  call    cs:__imp_CloseHandle
0x18000bd8f  test    eax, eax
0x18000bd91  jz      loc_18000BF1F
0x18000bd97  call    cs:__imp_GetProcessHeap
0x18000bd9d  mov     r8, r14; lpMem
0x18000bda0  xor     edx, edx; dwFlags
0x18000bda2  mov     rcx, rax; hHeap
0x18000bda5  call    cs:__imp_HeapFree
0x18000bdab  mov     rcx, [rbp+188h]; this
0x18000bdb2  lea     r8, aWil; "wil"
0x18000bdb9  mov     r9d, esi; char *
0x18000bdbc  mov     edx, 137h; void *
0x18000bdc1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bdc6  test    rdi, rdi
0x18000bdc9  jz      short loc_18000BDDC
0x18000bdcb  mov     rcx, rdi; hMutex
0x18000bdce  call    cs:__imp_ReleaseMutex
0x18000bdd4  test    eax, eax
0x18000bdd6  jz      loc_18000BF31
0x18000bddc  mov     rcx, rbx; hObject
0x18000bddf  call    cs:__imp_CloseHandle
0x18000bde5  test    eax, eax
0x18000bde7  jz      loc_18000BEC4
0x18000bded  jmp     loc_18000BCB1
0x18000bdf2  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000bdf7  lea     rcx, [r14+28h]; void *
0x18000bdfb  mov     dword ptr [r14], 1
0x18000be02  xor     edx, edx; Val
0x18000be04  mov     [r14+8], rbx
0x18000be08  mov     r8d, 108h; Size
0x18000be0e  movdqu  xmmword ptr [r14+10h], xmm0
0x18000be14  call    memset_0
0x18000be19  xor     eax, eax
0x18000be1b  lea     rcx, [r14+28h]; this
0x18000be1f  mov     [r14+20h], rax
0x18000be23  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000be28  lea     rbx, [r14+0E8h]
0x18000be2f  xor     r8d, r8d; Flags
0x18000be32  mov     rcx, rbx; lpCriticalSection
0x18000be35  xor     edx, edx; dwSpinCount
0x18000be37  call    cs:__imp_InitializeCriticalSectionEx
0x18000be3d  mov     qword ptr [rbx+28h], 0
0x18000be45  mov     qword ptr [rbx+30h], 0
0x18000be4d  mov     qword ptr [rbx+38h], 0
0x18000be55  mov     qword ptr [rbx+40h], 0
0x18000be5d  xor     ebx, ebx
0x18000be5f  mov     [r15], r14
0x18000be62  test    rdi, rdi
0x18000be65  jz      short loc_18000BE78
0x18000be67  mov     rcx, rdi; hMutex
0x18000be6a  call    cs:__imp_ReleaseMutex
0x18000be70  test    eax, eax
0x18000be72  jz      loc_18000BF43
0x18000be78  test    rbx, rbx
0x18000be7b  jz      short loc_18000BE8A
0x18000be7d  mov     rcx, rbx; hObject
0x18000be80  call    cs:__imp_CloseHandle
0x18000be86  test    eax, eax
0x18000be88  jz      short loc_18000BEB2
0x18000be8a  xor     eax, eax
0x18000be8c  mov     rcx, [rbp+180h+var_30]
0x18000be93  xor     rcx, rsp; StackCookie
0x18000be96  call    __security_check_cookie
0x18000be9b  mov     rbx, [rsp+280h+arg_10]
0x18000bea3  add     rsp, 260h
0x18000beaa  pop     r15
0x18000beac  pop     r14
0x18000beae  pop     rdi
0x18000beaf  pop     rsi
0x18000beb0  pop     rbp
0x18000beb1  retn
0x18000beb2  mov     rcx, [rbp+188h]; this
0x18000beb9  mov     edx, 0A0Bh; void *
0x18000bebe  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bec4  mov     rcx, [rbp+188h]; this
0x18000becb  mov     edx, 0A0Bh; void *
0x18000bed0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bed6  mov     rcx, [rbp+188h]; this
0x18000bedd  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000bee3  mov     rcx, [rbp+188h]; this
0x18000beea  mov     edx, 0A15h; void *
0x18000beef  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bef5  mov     rcx, [rbp+188h]; this
0x18000befc  mov     edx, 0A0Bh; void *
0x18000bf01  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bf07  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000bf0d  mov     rcx, [rbp+188h]; this
0x18000bf14  mov     edx, 0A0Bh; void *
0x18000bf19  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bf1f  mov     rcx, [rbp+188h]; this
0x18000bf26  mov     edx, 0A0Bh; void *
0x18000bf2b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bf31  mov     rcx, [rbp+188h]; this
0x18000bf38  mov     edx, 0A15h; void *
0x18000bf3d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bf43  mov     rcx, [rbp+188h]; this
0x18000bf4a  mov     edx, 0A15h; void *
0x18000bf4f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
