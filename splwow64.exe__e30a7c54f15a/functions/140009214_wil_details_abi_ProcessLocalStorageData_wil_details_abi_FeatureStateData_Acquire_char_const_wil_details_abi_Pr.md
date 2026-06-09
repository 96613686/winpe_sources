# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x140009214`
- end: `0x1400095db`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1400095e4`

## callees

- `0x140001ee0`
- `0x1400028b8`
- `0x140003ad0`
- `0x140003ff4`
- `0x140004698`
- `0x14000542c`
- `0x140005b54`
- `0x140005f18`
- `0x140005fa4`
- `0x14000635c`
- `0x14000636c`
- `0x140008abc`
- `0x140009214`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140009432`
- `KERNEL32!HeapFree` at `0x140009432`
- `KERNEL32!ReleaseMutex` at `0x14000932d`
- `KERNEL32!ReleaseMutex` at `0x140009454`
- `KERNEL32!ReleaseMutex` at `0x1400094f0`
- `KERNEL32!ReleaseMutex` at `0x14000932d`
- `KERNEL32!ReleaseMutex` at `0x140009454`
- `KERNEL32!ReleaseMutex` at `0x1400094f0`
- `KERNEL32!WaitForSingleObjectEx` at `0x1400092ac`
- `KERNEL32!WaitForSingleObjectEx` at `0x1400092ac`
- `KERNEL32!CloseHandle` at `0x14000933e`
- `KERNEL32!CloseHandle` at `0x1400093fe`
- `KERNEL32!CloseHandle` at `0x140009416`
- `KERNEL32!CloseHandle` at `0x140009465`
- `KERNEL32!CloseHandle` at `0x140009506`
- `KERNEL32!CloseHandle` at `0x14000933e`
- `KERNEL32!CloseHandle` at `0x1400093fe`
- `KERNEL32!CloseHandle` at `0x140009416`
- `KERNEL32!CloseHandle` at `0x140009465`
- `KERNEL32!CloseHandle` at `0x140009506`
- `KERNEL32!CreateMutexExW` at `0x14000928b`
- `KERNEL32!CreateMutexExW` at `0x14000928b`
- `KERNEL32!GetCurrentProcessId` at `0x14000924d`
- `KERNEL32!GetCurrentProcessId` at `0x14000924d`
- `KERNEL32!GetProcessHeap` at `0x140009424`
- `KERNEL32!GetProcessHeap` at `0x140009424`
- `KERNEL32!InitializeCriticalSectionEx` at `0x1400094bd`
- `KERNEL32!InitializeCriticalSectionEx` at `0x1400094bd`

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
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // r8d
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  __int64 v25; // r8
  _DWORD *v26; // r14
  unsigned int v27; // r8d
  int v28; // eax
  unsigned int v29; // r8d
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v35; // r8d
  const char *v36; // r9
  unsigned int v37; // r8d
  const char *v38; // r9
  __int128 v39; // xmm0
  unsigned int v40; // r8d
  const char *v41; // r9
  unsigned int v42; // r8d
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
0x140009214  mov     [rsp-8+arg_10], rbx
0x140009219  push    rbp
0x14000921a  push    rsi
0x14000921b  push    rdi
0x14000921c  push    r14
0x14000921e  push    r15
0x140009220  lea     rbp, [rsp-160h]
0x140009228  sub     rsp, 260h
0x14000922f  mov     rax, cs:__security_cookie
0x140009236  xor     rax, rsp
0x140009239  mov     [rbp+180h+var_30], rax
0x140009240  mov     r15, rdx
0x140009243  mov     qword ptr [rdx], 0
0x14000924a  mov     rbx, rcx
0x14000924d  call    cs:__imp_GetCurrentProcessId
0x140009253  mov     r14d, 130h
0x140009259  mov     [rsp+280h+var_258], rbx
0x14000925e  mov     r9d, eax
0x140009261  mov     [rsp+280h+var_260], r14d; int
0x140009266  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x14000926d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140009272  lea     edx, [r14-2Ch]; unsigned __int64
0x140009276  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000927b  mov     r9d, 1F0001h; dwDesiredAccess
0x140009281  lea     rdx, [rsp+280h+Name]; lpName
0x140009286  xor     r8d, r8d; dwFlags
0x140009289  xor     ecx, ecx; lpMutexAttributes
0x14000928b  call    cs:__imp_CreateMutexExW
0x140009291  mov     rbx, rax
0x140009294  test    rax, rax
0x140009297  jnz     short loc_1400092A3
0x140009299  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000929e  jmp     loc_140009512
0x1400092a3  xor     r8d, r8d; bAlertable
0x1400092a6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400092a9  mov     rcx, rbx; hHandle
0x1400092ac  call    cs:__imp_WaitForSingleObjectEx
0x1400092b2  cmp     eax, 102h
0x1400092b7  jz      short loc_1400092C9
0x1400092b9  test    eax, 0FFFFFF7Fh
0x1400092be  jnz     loc_14000955C
0x1400092c4  mov     rdi, rbx
0x1400092c7  jmp     short loc_1400092CB
0x1400092c9  xor     edi, edi
0x1400092cb  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1400092d0  mov     [rsp+280h+hObject], 0
0x1400092d9  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400092de  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1400092e3  mov     esi, eax
0x1400092e5  test    eax, eax
0x1400092e7  jns     short loc_140009353
0x1400092e9  mov     rcx, [rbp+188h]; this
0x1400092f0  mov     r9d, eax; char *
0x1400092f3  mov     edx, 66h ; 'f'; void *
0x1400092f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400092fd  mov     rcx, [rbp+188h]; this
0x140009304  mov     r9d, esi; char *
0x140009307  mov     edx, 6Fh ; 'o'; void *
0x14000930c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009311  mov     rcx, [rbp+188h]; this
0x140009318  mov     r9d, esi; char *
0x14000931b  mov     edx, 12Eh; void *
0x140009320  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009325  test    rdi, rdi
0x140009328  jz      short loc_14000933B
0x14000932a  mov     rcx, rdi; hMutex
0x14000932d  call    cs:__imp_ReleaseMutex
0x140009333  test    eax, eax
0x140009335  jz      loc_140009569
0x14000933b  mov     rcx, rbx; hObject
0x14000933e  call    cs:__imp_CloseHandle
0x140009344  test    eax, eax
0x140009346  jz      loc_14000957B
0x14000934c  mov     eax, esi
0x14000934e  jmp     loc_140009512
0x140009353  mov     rax, [rsp+280h+hObject]
0x140009358  lea     rcx, ds:0[rax*4]
0x140009360  test    rcx, rcx
0x140009363  jz      short loc_140009373
0x140009365  mov     [r15], rcx
0x140009368  mov     eax, [rcx]
0x14000936a  inc     eax
0x14000936c  mov     [rcx], eax
0x14000936e  jmp     loc_1400094E8
0x140009373  mov     rdx, r14; dwBytes
0x140009376  mov     qword ptr [r15], 0
0x14000937d  mov     ecx, 8; dwFlags
0x140009382  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140009387  mov     r14, rax
0x14000938a  test    rax, rax
0x14000938d  jnz     short loc_1400093AD
0x14000938f  mov     rcx, [rbp+188h]; this
0x140009396  mov     esi, 8007000Eh
0x14000939b  mov     r9d, esi; char *
0x14000939e  mov     edx, 14Bh; void *
0x1400093a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400093a8  jmp     loc_140009438
0x1400093ad  xorps   xmm0, xmm0
0x1400093b0  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1400093b6  test    r14b, 3
0x1400093ba  jnz     loc_14000958D
0x1400093c0  mov     r9, r14
0x1400093c3  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1400093c8  shr     r9, 2; unsigned __int64
0x1400093cc  lea     rcx, [rsp+280h+hObject]; this
0x1400093d1  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1400093d6  mov     esi, eax
0x1400093d8  test    eax, eax
0x1400093da  jns     loc_140009478
0x1400093e0  mov     rcx, [rbp+188h]; this
0x1400093e7  mov     r9d, eax; char *
0x1400093ea  mov     edx, 14Eh; void *
0x1400093ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400093f4  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1400093f9  test    rcx, rcx
0x1400093fc  jz      short loc_14000940C
0x1400093fe  call    cs:__imp_CloseHandle
0x140009404  test    eax, eax
0x140009406  jz      loc_140009593
0x14000940c  mov     rcx, [rsp+280h+hObject]; hObject
0x140009411  test    rcx, rcx
0x140009414  jz      short loc_140009424
0x140009416  call    cs:__imp_CloseHandle
0x14000941c  test    eax, eax
0x14000941e  jz      loc_1400095A5
0x140009424  call    cs:__imp_GetProcessHeap
0x14000942a  mov     r8, r14; lpMem
0x14000942d  xor     edx, edx; dwFlags
0x14000942f  mov     rcx, rax; hHeap
0x140009432  call    cs:__imp_HeapFree
0x140009438  mov     rcx, [rbp+188h]; this
0x14000943f  mov     r9d, esi; char *
0x140009442  mov     edx, 137h; void *
0x140009447  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000944c  test    rdi, rdi
0x14000944f  jz      short loc_140009462
0x140009451  mov     rcx, rdi; hMutex
0x140009454  call    cs:__imp_ReleaseMutex
0x14000945a  test    eax, eax
0x14000945c  jz      loc_1400095B7
0x140009462  mov     rcx, rbx; hObject
0x140009465  call    cs:__imp_CloseHandle
0x14000946b  test    eax, eax
0x14000946d  jz      loc_14000954A
0x140009473  jmp     loc_14000934C
0x140009478  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x14000947d  lea     rcx, [r14+28h]; void *
0x140009481  mov     dword ptr [r14], 1
0x140009488  xor     edx, edx; Val
0x14000948a  mov     [r14+8], rbx
0x14000948e  mov     r8d, 108h; Size
0x140009494  movdqu  xmmword ptr [r14+10h], xmm0
0x14000949a  call    memset_0
0x14000949f  xor     eax, eax
0x1400094a1  lea     rcx, [r14+28h]; this
0x1400094a5  mov     [r14+20h], rax
0x1400094a9  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1400094ae  lea     rbx, [r14+0E8h]
0x1400094b5  xor     r8d, r8d; Flags
0x1400094b8  mov     rcx, rbx; lpCriticalSection
0x1400094bb  xor     edx, edx; dwSpinCount
0x1400094bd  call    cs:__imp_InitializeCriticalSectionEx
0x1400094c3  mov     qword ptr [rbx+28h], 0
0x1400094cb  mov     qword ptr [rbx+30h], 0
0x1400094d3  mov     qword ptr [rbx+38h], 0
0x1400094db  mov     qword ptr [rbx+40h], 0
0x1400094e3  xor     ebx, ebx
0x1400094e5  mov     [r15], r14
0x1400094e8  test    rdi, rdi
0x1400094eb  jz      short loc_1400094FE
0x1400094ed  mov     rcx, rdi; hMutex
0x1400094f0  call    cs:__imp_ReleaseMutex
0x1400094f6  test    eax, eax
0x1400094f8  jz      loc_1400095C9
0x1400094fe  test    rbx, rbx
0x140009501  jz      short loc_140009510
0x140009503  mov     rcx, rbx; hObject
0x140009506  call    cs:__imp_CloseHandle
0x14000950c  test    eax, eax
0x14000950e  jz      short loc_140009538
0x140009510  xor     eax, eax
0x140009512  mov     rcx, [rbp+180h+var_30]
0x140009519  xor     rcx, rsp; StackCookie
0x14000951c  call    __security_check_cookie
0x140009521  mov     rbx, [rsp+280h+arg_10]
0x140009529  add     rsp, 260h
0x140009530  pop     r15
0x140009532  pop     r14
0x140009534  pop     rdi
0x140009535  pop     rsi
0x140009536  pop     rbp
0x140009537  retn
0x140009538  mov     rcx, [rbp+188h]; this
0x14000953f  mov     edx, 0A0Bh; void *
0x140009544  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000954a  mov     rcx, [rbp+188h]; this
0x140009551  mov     edx, 0A0Bh; void *
0x140009556  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000955c  mov     rcx, [rbp+188h]; this
0x140009563  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140009569  mov     rcx, [rbp+188h]; this
0x140009570  mov     edx, 0A15h; void *
0x140009575  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000957b  mov     rcx, [rbp+188h]; this
0x140009582  mov     edx, 0A0Bh; void *
0x140009587  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000958d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140009593  mov     rcx, [rbp+188h]; this
0x14000959a  mov     edx, 0A0Bh; void *
0x14000959f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400095a5  mov     rcx, [rbp+188h]; this
0x1400095ac  mov     edx, 0A0Bh; void *
0x1400095b1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400095b7  mov     rcx, [rbp+188h]; this
0x1400095be  mov     edx, 0A15h; void *
0x1400095c3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400095c9  mov     rcx, [rbp+188h]; this
0x1400095d0  mov     edx, 0A15h; void *
0x1400095d5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
