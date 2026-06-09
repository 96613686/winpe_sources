# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000555c`
- end: `0x180005952`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1014`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180005c44`

## callees

- `0x180002590`
- `0x180003088`
- `0x1800046b8`
- `0x18000555c`
- `0x180005958`
- `0x180005e98`
- `0x1800067c8`
- `0x1800071b8`
- `0x180008934`
- `0x1800094bc`
- `0x18000993c`
- `0x18000a20c`
- `0x18000a21c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000568a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800057c6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005862`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000568a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800057c6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005862`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800055f4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800055f4`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000582f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000582f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800055d3`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800055d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000578f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000578f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000579d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000579d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005595`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005595`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000569b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005769`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005781`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800057d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005878`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000569b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005769`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005781`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800057d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005878`

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
  bool v9; // dl
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
      wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xE01, v10, v11);
    v12 = v6;
  }
  hObject[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    v9,
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
0x18000555c  mov     [rsp-8+arg_10], rbx
0x180005561  push    rbp
0x180005562  push    rsi
0x180005563  push    rdi
0x180005564  push    r14
0x180005566  push    r15
0x180005568  lea     rbp, [rsp-160h]
0x180005570  sub     rsp, 260h
0x180005577  mov     rax, cs:__security_cookie
0x18000557e  xor     rax, rsp
0x180005581  mov     [rbp+180h+var_30], rax
0x180005588  mov     r15, rdx
0x18000558b  mov     qword ptr [rdx], 0
0x180005592  mov     rbx, rcx
0x180005595  call    cs:__imp_GetCurrentProcessId
0x18000559b  mov     r14d, 130h
0x1800055a1  mov     [rsp+280h+var_258], rbx
0x1800055a6  mov     r9d, eax
0x1800055a9  mov     [rsp+280h+var_260], r14d; int
0x1800055ae  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800055b5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800055ba  lea     edx, [r14-2Ch]; unsigned __int64
0x1800055be  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800055c3  mov     r9d, 1F0001h; dwDesiredAccess
0x1800055c9  lea     rdx, [rsp+280h+Name]; lpName
0x1800055ce  xor     r8d, r8d; dwFlags
0x1800055d1  xor     ecx, ecx; lpMutexAttributes
0x1800055d3  call    cs:__imp_CreateMutexExW
0x1800055d9  mov     rbx, rax
0x1800055dc  test    rax, rax
0x1800055df  jnz     short loc_1800055EB
0x1800055e1  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800055e6  jmp     loc_180005884
0x1800055eb  xor     r8d, r8d; bAlertable
0x1800055ee  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800055f1  mov     rcx, rbx; hHandle
0x1800055f4  call    cs:__imp_WaitForSingleObjectEx
0x1800055fa  cmp     eax, 102h
0x1800055ff  jz      short loc_180005611
0x180005601  test    eax, 0FFFFFF7Fh
0x180005606  jnz     loc_1800058CE
0x18000560c  mov     rdi, rbx
0x18000560f  jmp     short loc_180005613
0x180005611  xor     edi, edi
0x180005613  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180005618  mov     [rsp+280h+hObject], 0
0x180005621  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005626  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000562b  mov     esi, eax
0x18000562d  test    eax, eax
0x18000562f  jns     short loc_1800056B0
0x180005631  mov     rcx, [rbp+188h]; this
0x180005638  lea     r8, aWil; "wil"
0x18000563f  mov     r9d, eax; char *
0x180005642  mov     edx, 66h ; 'f'; void *
0x180005647  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000564c  mov     rcx, [rbp+188h]; this
0x180005653  lea     r8, aWil; "wil"
0x18000565a  mov     r9d, esi; char *
0x18000565d  mov     edx, 6Fh ; 'o'; void *
0x180005662  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005667  mov     rcx, [rbp+188h]; this
0x18000566e  lea     r8, aWil; "wil"
0x180005675  mov     r9d, esi; char *
0x180005678  mov     edx, 12Eh; void *
0x18000567d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005682  test    rdi, rdi
0x180005685  jz      short loc_180005698
0x180005687  mov     rcx, rdi; hMutex
0x18000568a  call    cs:__imp_ReleaseMutex
0x180005690  test    eax, eax
0x180005692  jz      loc_1800058E0
0x180005698  mov     rcx, rbx; hObject
0x18000569b  call    cs:__imp_CloseHandle
0x1800056a1  test    eax, eax
0x1800056a3  jz      loc_1800058F2
0x1800056a9  mov     eax, esi
0x1800056ab  jmp     loc_180005884
0x1800056b0  mov     rax, [rsp+280h+hObject]
0x1800056b5  lea     rcx, ds:0[rax*4]
0x1800056bd  test    rcx, rcx
0x1800056c0  jz      short loc_1800056D0
0x1800056c2  mov     [r15], rcx
0x1800056c5  mov     eax, [rcx]
0x1800056c7  inc     eax
0x1800056c9  mov     [rcx], eax
0x1800056cb  jmp     loc_18000585A
0x1800056d0  mov     rdx, r14; dwBytes
0x1800056d3  mov     qword ptr [r15], 0
0x1800056da  mov     ecx, 8; dwFlags
0x1800056df  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800056e4  mov     r14, rax
0x1800056e7  test    rax, rax
0x1800056ea  jnz     short loc_180005711
0x1800056ec  mov     rcx, [rbp+188h]; this
0x1800056f3  lea     r8, aWil; "wil"
0x1800056fa  mov     esi, 8007000Eh
0x1800056ff  mov     edx, 14Bh; void *
0x180005704  mov     r9d, esi; char *
0x180005707  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000570c  jmp     loc_1800057A3
0x180005711  xorps   xmm0, xmm0
0x180005714  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x18000571a  test    r14b, 3
0x18000571e  jnz     loc_180005904
0x180005724  mov     r9, r14
0x180005727  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000572c  shr     r9, 2; unsigned __int64
0x180005730  lea     rcx, [rsp+280h+hObject]; this
0x180005735  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18000573a  mov     esi, eax
0x18000573c  test    eax, eax
0x18000573e  jns     loc_1800057EA
0x180005744  mov     rcx, [rbp+188h]; this
0x18000574b  lea     r8, aWil; "wil"
0x180005752  mov     r9d, eax; char *
0x180005755  mov     edx, 14Eh; void *
0x18000575a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000575f  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180005764  test    rcx, rcx
0x180005767  jz      short loc_180005777
0x180005769  call    cs:__imp_CloseHandle
0x18000576f  test    eax, eax
0x180005771  jz      loc_18000590A
0x180005777  mov     rcx, [rsp+280h+hObject]; hObject
0x18000577c  test    rcx, rcx
0x18000577f  jz      short loc_18000578F
0x180005781  call    cs:__imp_CloseHandle
0x180005787  test    eax, eax
0x180005789  jz      loc_18000591C
0x18000578f  call    cs:__imp_GetProcessHeap
0x180005795  mov     r8, r14; lpMem
0x180005798  xor     edx, edx; dwFlags
0x18000579a  mov     rcx, rax; hHeap
0x18000579d  call    cs:__imp_HeapFree
0x1800057a3  mov     rcx, [rbp+188h]; this
0x1800057aa  lea     r8, aWil; "wil"
0x1800057b1  mov     r9d, esi; char *
0x1800057b4  mov     edx, 137h; void *
0x1800057b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800057be  test    rdi, rdi
0x1800057c1  jz      short loc_1800057D4
0x1800057c3  mov     rcx, rdi; hMutex
0x1800057c6  call    cs:__imp_ReleaseMutex
0x1800057cc  test    eax, eax
0x1800057ce  jz      loc_18000592E
0x1800057d4  mov     rcx, rbx; hObject
0x1800057d7  call    cs:__imp_CloseHandle
0x1800057dd  test    eax, eax
0x1800057df  jz      loc_1800058BC
0x1800057e5  jmp     loc_1800056A9
0x1800057ea  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800057ef  lea     rcx, [r14+28h]; void *
0x1800057f3  mov     dword ptr [r14], 1
0x1800057fa  xor     edx, edx; Val
0x1800057fc  mov     [r14+8], rbx
0x180005800  mov     r8d, 108h; Size
0x180005806  movdqu  xmmword ptr [r14+10h], xmm0
0x18000580c  call    memset_0
0x180005811  xor     eax, eax
0x180005813  lea     rcx, [r14+28h]; this
0x180005817  mov     [r14+20h], rax
0x18000581b  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180005820  lea     rbx, [r14+0E8h]
0x180005827  xor     r8d, r8d; Flags
0x18000582a  mov     rcx, rbx; lpCriticalSection
0x18000582d  xor     edx, edx; dwSpinCount
0x18000582f  call    cs:__imp_InitializeCriticalSectionEx
0x180005835  mov     qword ptr [rbx+28h], 0
0x18000583d  mov     qword ptr [rbx+30h], 0
0x180005845  mov     qword ptr [rbx+38h], 0
0x18000584d  mov     qword ptr [rbx+40h], 0
0x180005855  xor     ebx, ebx
0x180005857  mov     [r15], r14
0x18000585a  test    rdi, rdi
0x18000585d  jz      short loc_180005870
0x18000585f  mov     rcx, rdi; hMutex
0x180005862  call    cs:__imp_ReleaseMutex
0x180005868  test    eax, eax
0x18000586a  jz      loc_180005940
0x180005870  test    rbx, rbx
0x180005873  jz      short loc_180005882
0x180005875  mov     rcx, rbx; hObject
0x180005878  call    cs:__imp_CloseHandle
0x18000587e  test    eax, eax
0x180005880  jz      short loc_1800058AA
0x180005882  xor     eax, eax
0x180005884  mov     rcx, [rbp+180h+var_30]
0x18000588b  xor     rcx, rsp; StackCookie
0x18000588e  call    __security_check_cookie
0x180005893  mov     rbx, [rsp+280h+arg_10]
0x18000589b  add     rsp, 260h
0x1800058a2  pop     r15
0x1800058a4  pop     r14
0x1800058a6  pop     rdi
0x1800058a7  pop     rsi
0x1800058a8  pop     rbp
0x1800058a9  retn
0x1800058aa  mov     rcx, [rbp+188h]; this
0x1800058b1  mov     edx, 0A0Bh; void *
0x1800058b6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800058bc  mov     rcx, [rbp+188h]; this
0x1800058c3  mov     edx, 0A0Bh; void *
0x1800058c8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800058ce  mov     rcx, [rbp+188h]; this
0x1800058d5  mov     edx, 0E01h; void *
0x1800058da  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800058e0  mov     rcx, [rbp+188h]; this
0x1800058e7  mov     edx, 0A15h; void *
0x1800058ec  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800058f2  mov     rcx, [rbp+188h]; this
0x1800058f9  mov     edx, 0A0Bh; void *
0x1800058fe  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005904  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000590a  mov     rcx, [rbp+188h]; this
0x180005911  mov     edx, 0A0Bh; void *
0x180005916  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000591c  mov     rcx, [rbp+188h]; this
0x180005923  mov     edx, 0A0Bh; void *
0x180005928  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000592e  mov     rcx, [rbp+188h]; this
0x180005935  mov     edx, 0A15h; void *
0x18000593a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005940  mov     rcx, [rbp+188h]; this
0x180005947  mov     edx, 0A15h; void *
0x18000594c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
