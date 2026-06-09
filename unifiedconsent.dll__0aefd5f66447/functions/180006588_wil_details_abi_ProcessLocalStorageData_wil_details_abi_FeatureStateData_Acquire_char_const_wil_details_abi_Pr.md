# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180006588`
- end: `0x180006979`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1800072b0`

## callees

- `0x180002810`
- `0x180003384`
- `0x180005184`
- `0x180006588`
- `0x1800069b4`
- `0x180007504`
- `0x1800095b8`
- `0x18000a2ec`
- `0x18000c784`
- `0x18000d3b4`
- `0x18000d93c`
- `0x18000e434`
- `0x18000e444`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800065ff`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800065ff`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800066b6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800067f2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000688e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800066b6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800067f2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000688e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006620`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006620`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000685b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000685b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800067c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800067c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800067bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800067bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800065c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800065c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800066c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006795`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800067ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006803`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800068a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800066c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006795`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800067ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006803`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800068a4`

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
  const char *v17; // r9
  unsigned int v18; // r8d
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  __int64 v23; // r8
  _DWORD *v24; // r14
  int v25; // eax
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  __int128 v35; // xmm0
  unsigned int v36; // r8d
  const char *v37; // r9
  unsigned int v38; // r8d
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
0x180006588  mov     [rsp-8+arg_10], rbx
0x18000658d  push    rbp
0x18000658e  push    rsi
0x18000658f  push    rdi
0x180006590  push    r14
0x180006592  push    r15
0x180006594  lea     rbp, [rsp-160h]
0x18000659c  sub     rsp, 260h
0x1800065a3  mov     rax, cs:__security_cookie
0x1800065aa  xor     rax, rsp
0x1800065ad  mov     [rbp+180h+var_30], rax
0x1800065b4  mov     r15, rdx
0x1800065b7  mov     qword ptr [rdx], 0
0x1800065be  mov     rbx, rcx
0x1800065c1  call    cs:__imp_GetCurrentProcessId
0x1800065c7  mov     r14d, 130h
0x1800065cd  mov     [rsp+280h+var_258], rbx
0x1800065d2  mov     r9d, eax
0x1800065d5  mov     [rsp+280h+var_260], r14d; int
0x1800065da  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800065e1  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800065e6  lea     edx, [r14-2Ch]; unsigned __int64
0x1800065ea  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800065ef  mov     r9d, 1F0001h; dwDesiredAccess
0x1800065f5  lea     rdx, [rsp+280h+Name]; lpName
0x1800065fa  xor     r8d, r8d; dwFlags
0x1800065fd  xor     ecx, ecx; lpMutexAttributes
0x1800065ff  call    cs:__imp_CreateMutexExW
0x180006605  mov     rbx, rax
0x180006608  test    rax, rax
0x18000660b  jnz     short loc_180006617
0x18000660d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006612  jmp     loc_1800068B0
0x180006617  xor     r8d, r8d; bAlertable
0x18000661a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000661d  mov     rcx, rbx; hHandle
0x180006620  call    cs:__imp_WaitForSingleObjectEx
0x180006626  cmp     eax, 102h
0x18000662b  jz      short loc_18000663D
0x18000662d  test    eax, 0FFFFFF7Fh
0x180006632  jnz     loc_1800068FA
0x180006638  mov     rdi, rbx
0x18000663b  jmp     short loc_18000663F
0x18000663d  xor     edi, edi
0x18000663f  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180006644  mov     [rsp+280h+hObject], 0
0x18000664d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006652  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180006657  mov     esi, eax
0x180006659  test    eax, eax
0x18000665b  jns     short loc_1800066DC
0x18000665d  mov     rcx, [rbp+188h]; this
0x180006664  lea     r8, aWil; "wil"
0x18000666b  mov     r9d, eax; char *
0x18000666e  mov     edx, 66h ; 'f'; void *
0x180006673  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006678  mov     rcx, [rbp+188h]; this
0x18000667f  lea     r8, aWil; "wil"
0x180006686  mov     r9d, esi; char *
0x180006689  mov     edx, 6Fh ; 'o'; void *
0x18000668e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006693  mov     rcx, [rbp+188h]; this
0x18000669a  lea     r8, aWil; "wil"
0x1800066a1  mov     r9d, esi; char *
0x1800066a4  mov     edx, 12Eh; void *
0x1800066a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800066ae  test    rdi, rdi
0x1800066b1  jz      short loc_1800066C4
0x1800066b3  mov     rcx, rdi; hMutex
0x1800066b6  call    cs:__imp_ReleaseMutex
0x1800066bc  test    eax, eax
0x1800066be  jz      loc_180006907
0x1800066c4  mov     rcx, rbx; hObject
0x1800066c7  call    cs:__imp_CloseHandle
0x1800066cd  test    eax, eax
0x1800066cf  jz      loc_180006919
0x1800066d5  mov     eax, esi
0x1800066d7  jmp     loc_1800068B0
0x1800066dc  mov     rax, [rsp+280h+hObject]
0x1800066e1  lea     rcx, ds:0[rax*4]
0x1800066e9  test    rcx, rcx
0x1800066ec  jz      short loc_1800066FC
0x1800066ee  mov     [r15], rcx
0x1800066f1  mov     eax, [rcx]
0x1800066f3  inc     eax
0x1800066f5  mov     [rcx], eax
0x1800066f7  jmp     loc_180006886
0x1800066fc  mov     rdx, r14; dwBytes
0x1800066ff  mov     qword ptr [r15], 0
0x180006706  mov     ecx, 8; dwFlags
0x18000670b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006710  mov     r14, rax
0x180006713  test    rax, rax
0x180006716  jnz     short loc_18000673D
0x180006718  mov     rcx, [rbp+188h]; this
0x18000671f  lea     r8, aWil; "wil"
0x180006726  mov     esi, 8007000Eh
0x18000672b  mov     edx, 14Bh; void *
0x180006730  mov     r9d, esi; char *
0x180006733  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006738  jmp     loc_1800067CF
0x18000673d  xorps   xmm0, xmm0
0x180006740  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180006746  test    r14b, 3
0x18000674a  jnz     loc_18000692B
0x180006750  mov     r9, r14
0x180006753  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180006758  shr     r9, 2; unsigned __int64
0x18000675c  lea     rcx, [rsp+280h+hObject]; this
0x180006761  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180006766  mov     esi, eax
0x180006768  test    eax, eax
0x18000676a  jns     loc_180006816
0x180006770  mov     rcx, [rbp+188h]; this
0x180006777  lea     r8, aWil; "wil"
0x18000677e  mov     r9d, eax; char *
0x180006781  mov     edx, 14Eh; void *
0x180006786  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000678b  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180006790  test    rcx, rcx
0x180006793  jz      short loc_1800067A3
0x180006795  call    cs:__imp_CloseHandle
0x18000679b  test    eax, eax
0x18000679d  jz      loc_180006931
0x1800067a3  mov     rcx, [rsp+280h+hObject]; hObject
0x1800067a8  test    rcx, rcx
0x1800067ab  jz      short loc_1800067BB
0x1800067ad  call    cs:__imp_CloseHandle
0x1800067b3  test    eax, eax
0x1800067b5  jz      loc_180006943
0x1800067bb  call    cs:__imp_GetProcessHeap
0x1800067c1  mov     r8, r14; lpMem
0x1800067c4  xor     edx, edx; dwFlags
0x1800067c6  mov     rcx, rax; hHeap
0x1800067c9  call    cs:__imp_HeapFree
0x1800067cf  mov     rcx, [rbp+188h]; this
0x1800067d6  lea     r8, aWil; "wil"
0x1800067dd  mov     r9d, esi; char *
0x1800067e0  mov     edx, 137h; void *
0x1800067e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800067ea  test    rdi, rdi
0x1800067ed  jz      short loc_180006800
0x1800067ef  mov     rcx, rdi; hMutex
0x1800067f2  call    cs:__imp_ReleaseMutex
0x1800067f8  test    eax, eax
0x1800067fa  jz      loc_180006955
0x180006800  mov     rcx, rbx; hObject
0x180006803  call    cs:__imp_CloseHandle
0x180006809  test    eax, eax
0x18000680b  jz      loc_1800068E8
0x180006811  jmp     loc_1800066D5
0x180006816  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000681b  lea     rcx, [r14+28h]; void *
0x18000681f  mov     dword ptr [r14], 1
0x180006826  xor     edx, edx; Val
0x180006828  mov     [r14+8], rbx
0x18000682c  mov     r8d, 108h; Size
0x180006832  movdqu  xmmword ptr [r14+10h], xmm0
0x180006838  call    memset_0
0x18000683d  xor     eax, eax
0x18000683f  lea     rcx, [r14+28h]; this
0x180006843  mov     [r14+20h], rax
0x180006847  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000684c  lea     rbx, [r14+0E8h]
0x180006853  xor     r8d, r8d; Flags
0x180006856  mov     rcx, rbx; lpCriticalSection
0x180006859  xor     edx, edx; dwSpinCount
0x18000685b  call    cs:__imp_InitializeCriticalSectionEx
0x180006861  mov     qword ptr [rbx+28h], 0
0x180006869  mov     qword ptr [rbx+30h], 0
0x180006871  mov     qword ptr [rbx+38h], 0
0x180006879  mov     qword ptr [rbx+40h], 0
0x180006881  xor     ebx, ebx
0x180006883  mov     [r15], r14
0x180006886  test    rdi, rdi
0x180006889  jz      short loc_18000689C
0x18000688b  mov     rcx, rdi; hMutex
0x18000688e  call    cs:__imp_ReleaseMutex
0x180006894  test    eax, eax
0x180006896  jz      loc_180006967
0x18000689c  test    rbx, rbx
0x18000689f  jz      short loc_1800068AE
0x1800068a1  mov     rcx, rbx; hObject
0x1800068a4  call    cs:__imp_CloseHandle
0x1800068aa  test    eax, eax
0x1800068ac  jz      short loc_1800068D6
0x1800068ae  xor     eax, eax
0x1800068b0  mov     rcx, [rbp+180h+var_30]
0x1800068b7  xor     rcx, rsp; StackCookie
0x1800068ba  call    __security_check_cookie
0x1800068bf  mov     rbx, [rsp+280h+arg_10]
0x1800068c7  add     rsp, 260h
0x1800068ce  pop     r15
0x1800068d0  pop     r14
0x1800068d2  pop     rdi
0x1800068d3  pop     rsi
0x1800068d4  pop     rbp
0x1800068d5  retn
0x1800068d6  mov     rcx, [rbp+188h]; this
0x1800068dd  mov     edx, 0A0Bh; void *
0x1800068e2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800068e8  mov     rcx, [rbp+188h]; this
0x1800068ef  mov     edx, 0A0Bh; void *
0x1800068f4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800068fa  mov     rcx, [rbp+188h]; this
0x180006901  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180006907  mov     rcx, [rbp+188h]; this
0x18000690e  mov     edx, 0A15h; void *
0x180006913  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006919  mov     rcx, [rbp+188h]; this
0x180006920  mov     edx, 0A0Bh; void *
0x180006925  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000692b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180006931  mov     rcx, [rbp+188h]; this
0x180006938  mov     edx, 0A0Bh; void *
0x18000693d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006943  mov     rcx, [rbp+188h]; this
0x18000694a  mov     edx, 0A0Bh; void *
0x18000694f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006955  mov     rcx, [rbp+188h]; this
0x18000695c  mov     edx, 0A15h; void *
0x180006961  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006967  mov     rcx, [rbp+188h]; this
0x18000696e  mov     edx, 0A15h; void *
0x180006973  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
