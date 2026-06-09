# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18001392c`
- end: `0x180013d22`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1014`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180014218`

## callees

- `0x180005420`
- `0x180005714`
- `0x180005ca8`
- `0x180006828`
- `0x180006a74`
- `0x180006f2c`
- `0x180006fb8`
- `0x180007448`
- `0x180007458`
- `0x1800131b4`
- `0x18001392c`
- `0x18007728a`
- `0x1800772c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800139c4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800139c4`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800139a3`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800139a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180013a5a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180013b96`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180013c32`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180013a5a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180013b96`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180013c32`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180013bff`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180013bff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013b6d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013b6d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013b5f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013b5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180013965`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180013965`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013a6b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013b39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013b51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013ba7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013c48`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013a6b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013b39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013b51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013ba7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013c48`

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
  __int64 v23; // r8
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
0x18001392c  mov     [rsp-8+arg_10], rbx
0x180013931  push    rbp
0x180013932  push    rsi
0x180013933  push    rdi
0x180013934  push    r14
0x180013936  push    r15
0x180013938  lea     rbp, [rsp-160h]
0x180013940  sub     rsp, 260h
0x180013947  mov     rax, cs:__security_cookie
0x18001394e  xor     rax, rsp
0x180013951  mov     [rbp+180h+var_30], rax
0x180013958  mov     r15, rdx
0x18001395b  mov     qword ptr [rdx], 0
0x180013962  mov     rbx, rcx
0x180013965  call    cs:__imp_GetCurrentProcessId
0x18001396b  mov     r14d, 130h
0x180013971  mov     [rsp+280h+var_258], rbx
0x180013976  mov     r9d, eax
0x180013979  mov     [rsp+280h+var_260], r14d; int
0x18001397e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180013985  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001398a  lea     edx, [r14-2Ch]; unsigned __int64
0x18001398e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013993  mov     r9d, 1F0001h; dwDesiredAccess
0x180013999  lea     rdx, [rsp+280h+Name]; lpName
0x18001399e  xor     r8d, r8d; dwFlags
0x1800139a1  xor     ecx, ecx; lpMutexAttributes
0x1800139a3  call    cs:__imp_CreateMutexExW
0x1800139a9  mov     rbx, rax
0x1800139ac  test    rax, rax
0x1800139af  jnz     short loc_1800139BB
0x1800139b1  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800139b6  jmp     loc_180013C54
0x1800139bb  xor     r8d, r8d; bAlertable
0x1800139be  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800139c1  mov     rcx, rbx; hHandle
0x1800139c4  call    cs:__imp_WaitForSingleObjectEx
0x1800139ca  cmp     eax, 102h
0x1800139cf  jz      short loc_1800139E1
0x1800139d1  test    eax, 0FFFFFF7Fh
0x1800139d6  jnz     loc_180013C9E
0x1800139dc  mov     rdi, rbx
0x1800139df  jmp     short loc_1800139E3
0x1800139e1  xor     edi, edi
0x1800139e3  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800139e8  mov     [rsp+280h+hObject], 0
0x1800139f1  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800139f6  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800139fb  mov     esi, eax
0x1800139fd  test    eax, eax
0x1800139ff  jns     short loc_180013A80
0x180013a01  mov     rcx, [rbp+188h]; this
0x180013a08  lea     r8, aWil; "wil"
0x180013a0f  mov     r9d, eax; char *
0x180013a12  mov     edx, 66h ; 'f'; void *
0x180013a17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013a1c  mov     rcx, [rbp+188h]; this
0x180013a23  lea     r8, aWil; "wil"
0x180013a2a  mov     r9d, esi; char *
0x180013a2d  mov     edx, 6Fh ; 'o'; void *
0x180013a32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013a37  mov     rcx, [rbp+188h]; this
0x180013a3e  lea     r8, aWil; "wil"
0x180013a45  mov     r9d, esi; char *
0x180013a48  mov     edx, 12Eh; void *
0x180013a4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013a52  test    rdi, rdi
0x180013a55  jz      short loc_180013A68
0x180013a57  mov     rcx, rdi; hMutex
0x180013a5a  call    cs:__imp_ReleaseMutex
0x180013a60  test    eax, eax
0x180013a62  jz      loc_180013CB0
0x180013a68  mov     rcx, rbx; hObject
0x180013a6b  call    cs:__imp_CloseHandle
0x180013a71  test    eax, eax
0x180013a73  jz      loc_180013CC2
0x180013a79  mov     eax, esi
0x180013a7b  jmp     loc_180013C54
0x180013a80  mov     rax, [rsp+280h+hObject]
0x180013a85  lea     rcx, ds:0[rax*4]
0x180013a8d  test    rcx, rcx
0x180013a90  jz      short loc_180013AA0
0x180013a92  mov     [r15], rcx
0x180013a95  mov     eax, [rcx]
0x180013a97  inc     eax
0x180013a99  mov     [rcx], eax
0x180013a9b  jmp     loc_180013C2A
0x180013aa0  mov     rdx, r14; dwBytes
0x180013aa3  mov     qword ptr [r15], 0
0x180013aaa  mov     ecx, 8; dwFlags
0x180013aaf  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180013ab4  mov     r14, rax
0x180013ab7  test    rax, rax
0x180013aba  jnz     short loc_180013AE1
0x180013abc  mov     rcx, [rbp+188h]; this
0x180013ac3  lea     r8, aWil; "wil"
0x180013aca  mov     esi, 8007000Eh
0x180013acf  mov     edx, 14Bh; void *
0x180013ad4  mov     r9d, esi; char *
0x180013ad7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013adc  jmp     loc_180013B73
0x180013ae1  xorps   xmm0, xmm0
0x180013ae4  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180013aea  test    r14b, 3
0x180013aee  jnz     loc_180013CD4
0x180013af4  mov     r9, r14
0x180013af7  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180013afc  shr     r9, 2; unsigned __int64
0x180013b00  lea     rcx, [rsp+280h+hObject]; this
0x180013b05  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180013b0a  mov     esi, eax
0x180013b0c  test    eax, eax
0x180013b0e  jns     loc_180013BBA
0x180013b14  mov     rcx, [rbp+188h]; this
0x180013b1b  lea     r8, aWil; "wil"
0x180013b22  mov     r9d, eax; char *
0x180013b25  mov     edx, 14Eh; void *
0x180013b2a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013b2f  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180013b34  test    rcx, rcx
0x180013b37  jz      short loc_180013B47
0x180013b39  call    cs:__imp_CloseHandle
0x180013b3f  test    eax, eax
0x180013b41  jz      loc_180013CDA
0x180013b47  mov     rcx, [rsp+280h+hObject]; hObject
0x180013b4c  test    rcx, rcx
0x180013b4f  jz      short loc_180013B5F
0x180013b51  call    cs:__imp_CloseHandle
0x180013b57  test    eax, eax
0x180013b59  jz      loc_180013CEC
0x180013b5f  call    cs:__imp_GetProcessHeap
0x180013b65  mov     r8, r14; lpMem
0x180013b68  xor     edx, edx; dwFlags
0x180013b6a  mov     rcx, rax; hHeap
0x180013b6d  call    cs:__imp_HeapFree
0x180013b73  mov     rcx, [rbp+188h]; this
0x180013b7a  lea     r8, aWil; "wil"
0x180013b81  mov     r9d, esi; char *
0x180013b84  mov     edx, 137h; void *
0x180013b89  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013b8e  test    rdi, rdi
0x180013b91  jz      short loc_180013BA4
0x180013b93  mov     rcx, rdi; hMutex
0x180013b96  call    cs:__imp_ReleaseMutex
0x180013b9c  test    eax, eax
0x180013b9e  jz      loc_180013CFE
0x180013ba4  mov     rcx, rbx; hObject
0x180013ba7  call    cs:__imp_CloseHandle
0x180013bad  test    eax, eax
0x180013baf  jz      loc_180013C8C
0x180013bb5  jmp     loc_180013A79
0x180013bba  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180013bbf  lea     rcx, [r14+28h]; void *
0x180013bc3  mov     dword ptr [r14], 1
0x180013bca  xor     edx, edx; Val
0x180013bcc  mov     [r14+8], rbx
0x180013bd0  mov     r8d, 108h; Size
0x180013bd6  movdqu  xmmword ptr [r14+10h], xmm0
0x180013bdc  call    memset_0
0x180013be1  xor     eax, eax
0x180013be3  lea     rcx, [r14+28h]; this
0x180013be7  mov     [r14+20h], rax
0x180013beb  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180013bf0  lea     rbx, [r14+0E8h]
0x180013bf7  xor     r8d, r8d; Flags
0x180013bfa  mov     rcx, rbx; lpCriticalSection
0x180013bfd  xor     edx, edx; dwSpinCount
0x180013bff  call    cs:__imp_InitializeCriticalSectionEx
0x180013c05  mov     qword ptr [rbx+28h], 0
0x180013c0d  mov     qword ptr [rbx+30h], 0
0x180013c15  mov     qword ptr [rbx+38h], 0
0x180013c1d  mov     qword ptr [rbx+40h], 0
0x180013c25  xor     ebx, ebx
0x180013c27  mov     [r15], r14
0x180013c2a  test    rdi, rdi
0x180013c2d  jz      short loc_180013C40
0x180013c2f  mov     rcx, rdi; hMutex
0x180013c32  call    cs:__imp_ReleaseMutex
0x180013c38  test    eax, eax
0x180013c3a  jz      loc_180013D10
0x180013c40  test    rbx, rbx
0x180013c43  jz      short loc_180013C52
0x180013c45  mov     rcx, rbx; hObject
0x180013c48  call    cs:__imp_CloseHandle
0x180013c4e  test    eax, eax
0x180013c50  jz      short loc_180013C7A
0x180013c52  xor     eax, eax
0x180013c54  mov     rcx, [rbp+180h+var_30]
0x180013c5b  xor     rcx, rsp; StackCookie
0x180013c5e  call    __security_check_cookie
0x180013c63  mov     rbx, [rsp+280h+arg_10]
0x180013c6b  add     rsp, 260h
0x180013c72  pop     r15
0x180013c74  pop     r14
0x180013c76  pop     rdi
0x180013c77  pop     rsi
0x180013c78  pop     rbp
0x180013c79  retn
0x180013c7a  mov     rcx, [rbp+188h]; this
0x180013c81  mov     edx, 0A0Bh; void *
0x180013c86  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180013c8c  mov     rcx, [rbp+188h]; this
0x180013c93  mov     edx, 0A0Bh; void *
0x180013c98  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180013c9e  mov     rcx, [rbp+188h]; this
0x180013ca5  mov     edx, 0E01h; void *
0x180013caa  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180013cb0  mov     rcx, [rbp+188h]; this
0x180013cb7  mov     edx, 0A15h; void *
0x180013cbc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180013cc2  mov     rcx, [rbp+188h]; this
0x180013cc9  mov     edx, 0A0Bh; void *
0x180013cce  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180013cd4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180013cda  mov     rcx, [rbp+188h]; this
0x180013ce1  mov     edx, 0A0Bh; void *
0x180013ce6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180013cec  mov     rcx, [rbp+188h]; this
0x180013cf3  mov     edx, 0A0Bh; void *
0x180013cf8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180013cfe  mov     rcx, [rbp+188h]; this
0x180013d05  mov     edx, 0A15h; void *
0x180013d0a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180013d10  mov     rcx, [rbp+188h]; this
0x180013d17  mov     edx, 0A15h; void *
0x180013d1c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
