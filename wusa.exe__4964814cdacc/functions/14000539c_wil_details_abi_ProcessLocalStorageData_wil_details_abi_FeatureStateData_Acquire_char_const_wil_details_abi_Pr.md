# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x14000539c`
- end: `0x14000578d`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1400067f0`

## callees

- `0x140001a63`
- `0x140002a8c`
- `0x140002d84`
- `0x1400033d8`
- `0x140003eb8`
- `0x140004100`
- `0x1400044e0`
- `0x14000456c`
- `0x14000493c`
- `0x14000494c`
- `0x140004c1c`
- `0x14000539c`
- `0x140014910`

## import_xrefs

- `KERNEL32!WaitForSingleObjectEx` at `0x140005434`
- `KERNEL32!WaitForSingleObjectEx` at `0x140005434`
- `KERNEL32!CloseHandle` at `0x1400054db`
- `KERNEL32!CloseHandle` at `0x1400055a9`
- `KERNEL32!CloseHandle` at `0x1400055c1`
- `KERNEL32!CloseHandle` at `0x140005617`
- `KERNEL32!CloseHandle` at `0x1400056b8`
- `KERNEL32!CloseHandle` at `0x1400054db`
- `KERNEL32!CloseHandle` at `0x1400055a9`
- `KERNEL32!CloseHandle` at `0x1400055c1`
- `KERNEL32!CloseHandle` at `0x140005617`
- `KERNEL32!CloseHandle` at `0x1400056b8`
- `KERNEL32!CreateMutexExW` at `0x140005413`
- `KERNEL32!CreateMutexExW` at `0x140005413`
- `KERNEL32!GetCurrentProcessId` at `0x1400053d5`
- `KERNEL32!GetCurrentProcessId` at `0x1400053d5`
- `KERNEL32!HeapFree` at `0x1400055dd`
- `KERNEL32!HeapFree` at `0x1400055dd`
- `KERNEL32!InitializeCriticalSectionEx` at `0x14000566f`
- `KERNEL32!InitializeCriticalSectionEx` at `0x14000566f`
- `KERNEL32!ReleaseMutex` at `0x1400054ca`
- `KERNEL32!ReleaseMutex` at `0x140005606`
- `KERNEL32!ReleaseMutex` at `0x1400056a2`
- `KERNEL32!ReleaseMutex` at `0x1400054ca`
- `KERNEL32!ReleaseMutex` at `0x140005606`
- `KERNEL32!ReleaseMutex` at `0x1400056a2`
- `KERNEL32!GetProcessHeap` at `0x1400055cf`
- `KERNEL32!GetProcessHeap` at `0x1400055cf`

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
0x14000539c  mov     [rsp-8+arg_10], rbx
0x1400053a1  push    rbp
0x1400053a2  push    rsi
0x1400053a3  push    rdi
0x1400053a4  push    r14
0x1400053a6  push    r15
0x1400053a8  lea     rbp, [rsp-160h]
0x1400053b0  sub     rsp, 260h
0x1400053b7  mov     rax, cs:__security_cookie
0x1400053be  xor     rax, rsp
0x1400053c1  mov     [rbp+180h+var_30], rax
0x1400053c8  mov     r15, rdx
0x1400053cb  mov     qword ptr [rdx], 0
0x1400053d2  mov     rbx, rcx
0x1400053d5  call    cs:__imp_GetCurrentProcessId
0x1400053db  mov     r14d, 130h
0x1400053e1  mov     [rsp+280h+var_258], rbx
0x1400053e6  mov     r9d, eax
0x1400053e9  mov     [rsp+280h+var_260], r14d; int
0x1400053ee  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1400053f5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400053fa  lea     edx, [r14-2Ch]; unsigned __int64
0x1400053fe  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140005403  mov     r9d, 1F0001h; dwDesiredAccess
0x140005409  lea     rdx, [rsp+280h+Name]; lpName
0x14000540e  xor     r8d, r8d; dwFlags
0x140005411  xor     ecx, ecx; lpMutexAttributes
0x140005413  call    cs:__imp_CreateMutexExW
0x140005419  mov     rbx, rax
0x14000541c  test    rax, rax
0x14000541f  jnz     short loc_14000542B
0x140005421  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140005426  jmp     loc_1400056C4
0x14000542b  xor     r8d, r8d; bAlertable
0x14000542e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140005431  mov     rcx, rbx; hHandle
0x140005434  call    cs:__imp_WaitForSingleObjectEx
0x14000543a  cmp     eax, 102h
0x14000543f  jz      short loc_140005451
0x140005441  test    eax, 0FFFFFF7Fh
0x140005446  jnz     loc_14000570E
0x14000544c  mov     rdi, rbx
0x14000544f  jmp     short loc_140005453
0x140005451  xor     edi, edi
0x140005453  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140005458  mov     [rsp+280h+hObject], 0
0x140005461  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140005466  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x14000546b  mov     esi, eax
0x14000546d  test    eax, eax
0x14000546f  jns     short loc_1400054F0
0x140005471  mov     rcx, [rbp+188h]; this
0x140005478  lea     r8, aWil; "wil"
0x14000547f  mov     r9d, eax; char *
0x140005482  mov     edx, 66h ; 'f'; void *
0x140005487  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000548c  mov     rcx, [rbp+188h]; this
0x140005493  lea     r8, aWil; "wil"
0x14000549a  mov     r9d, esi; char *
0x14000549d  mov     edx, 6Fh ; 'o'; void *
0x1400054a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400054a7  mov     rcx, [rbp+188h]; this
0x1400054ae  lea     r8, aWil; "wil"
0x1400054b5  mov     r9d, esi; char *
0x1400054b8  mov     edx, 12Eh; void *
0x1400054bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400054c2  test    rdi, rdi
0x1400054c5  jz      short loc_1400054D8
0x1400054c7  mov     rcx, rdi; hMutex
0x1400054ca  call    cs:__imp_ReleaseMutex
0x1400054d0  test    eax, eax
0x1400054d2  jz      loc_14000571B
0x1400054d8  mov     rcx, rbx; hObject
0x1400054db  call    cs:__imp_CloseHandle
0x1400054e1  test    eax, eax
0x1400054e3  jz      loc_14000572D
0x1400054e9  mov     eax, esi
0x1400054eb  jmp     loc_1400056C4
0x1400054f0  mov     rax, [rsp+280h+hObject]
0x1400054f5  lea     rcx, ds:0[rax*4]
0x1400054fd  test    rcx, rcx
0x140005500  jz      short loc_140005510
0x140005502  mov     [r15], rcx
0x140005505  mov     eax, [rcx]
0x140005507  inc     eax
0x140005509  mov     [rcx], eax
0x14000550b  jmp     loc_14000569A
0x140005510  mov     rdx, r14; dwBytes
0x140005513  mov     qword ptr [r15], 0
0x14000551a  mov     ecx, 8; dwFlags
0x14000551f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140005524  mov     r14, rax
0x140005527  test    rax, rax
0x14000552a  jnz     short loc_140005551
0x14000552c  mov     rcx, [rbp+188h]; this
0x140005533  lea     r8, aWil; "wil"
0x14000553a  mov     esi, 8007000Eh
0x14000553f  mov     edx, 14Bh; void *
0x140005544  mov     r9d, esi; char *
0x140005547  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000554c  jmp     loc_1400055E3
0x140005551  xorps   xmm0, xmm0
0x140005554  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x14000555a  test    r14b, 3
0x14000555e  jnz     loc_14000573F
0x140005564  mov     r9, r14
0x140005567  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x14000556c  shr     r9, 2; unsigned __int64
0x140005570  lea     rcx, [rsp+280h+hObject]; this
0x140005575  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x14000557a  mov     esi, eax
0x14000557c  test    eax, eax
0x14000557e  jns     loc_14000562A
0x140005584  mov     rcx, [rbp+188h]; this
0x14000558b  lea     r8, aWil; "wil"
0x140005592  mov     r9d, eax; char *
0x140005595  mov     edx, 14Eh; void *
0x14000559a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000559f  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1400055a4  test    rcx, rcx
0x1400055a7  jz      short loc_1400055B7
0x1400055a9  call    cs:__imp_CloseHandle
0x1400055af  test    eax, eax
0x1400055b1  jz      loc_140005745
0x1400055b7  mov     rcx, [rsp+280h+hObject]; hObject
0x1400055bc  test    rcx, rcx
0x1400055bf  jz      short loc_1400055CF
0x1400055c1  call    cs:__imp_CloseHandle
0x1400055c7  test    eax, eax
0x1400055c9  jz      loc_140005757
0x1400055cf  call    cs:__imp_GetProcessHeap
0x1400055d5  mov     r8, r14; lpMem
0x1400055d8  xor     edx, edx; dwFlags
0x1400055da  mov     rcx, rax; hHeap
0x1400055dd  call    cs:__imp_HeapFree
0x1400055e3  mov     rcx, [rbp+188h]; this
0x1400055ea  lea     r8, aWil; "wil"
0x1400055f1  mov     r9d, esi; char *
0x1400055f4  mov     edx, 137h; void *
0x1400055f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400055fe  test    rdi, rdi
0x140005601  jz      short loc_140005614
0x140005603  mov     rcx, rdi; hMutex
0x140005606  call    cs:__imp_ReleaseMutex
0x14000560c  test    eax, eax
0x14000560e  jz      loc_140005769
0x140005614  mov     rcx, rbx; hObject
0x140005617  call    cs:__imp_CloseHandle
0x14000561d  test    eax, eax
0x14000561f  jz      loc_1400056FC
0x140005625  jmp     loc_1400054E9
0x14000562a  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x14000562f  lea     rcx, [r14+28h]; void *
0x140005633  mov     dword ptr [r14], 1
0x14000563a  xor     edx, edx; Val
0x14000563c  mov     [r14+8], rbx
0x140005640  mov     r8d, 108h; Size
0x140005646  movdqu  xmmword ptr [r14+10h], xmm0
0x14000564c  call    memset_0
0x140005651  xor     eax, eax
0x140005653  lea     rcx, [r14+28h]; this
0x140005657  mov     [r14+20h], rax
0x14000565b  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140005660  lea     rbx, [r14+0E8h]
0x140005667  xor     r8d, r8d; Flags
0x14000566a  mov     rcx, rbx; lpCriticalSection
0x14000566d  xor     edx, edx; dwSpinCount
0x14000566f  call    cs:__imp_InitializeCriticalSectionEx
0x140005675  mov     qword ptr [rbx+28h], 0
0x14000567d  mov     qword ptr [rbx+30h], 0
0x140005685  mov     qword ptr [rbx+38h], 0
0x14000568d  mov     qword ptr [rbx+40h], 0
0x140005695  xor     ebx, ebx
0x140005697  mov     [r15], r14
0x14000569a  test    rdi, rdi
0x14000569d  jz      short loc_1400056B0
0x14000569f  mov     rcx, rdi; hMutex
0x1400056a2  call    cs:__imp_ReleaseMutex
0x1400056a8  test    eax, eax
0x1400056aa  jz      loc_14000577B
0x1400056b0  test    rbx, rbx
0x1400056b3  jz      short loc_1400056C2
0x1400056b5  mov     rcx, rbx; hObject
0x1400056b8  call    cs:__imp_CloseHandle
0x1400056be  test    eax, eax
0x1400056c0  jz      short loc_1400056EA
0x1400056c2  xor     eax, eax
0x1400056c4  mov     rcx, [rbp+180h+var_30]
0x1400056cb  xor     rcx, rsp; StackCookie
0x1400056ce  call    __security_check_cookie
0x1400056d3  mov     rbx, [rsp+280h+arg_10]
0x1400056db  add     rsp, 260h
0x1400056e2  pop     r15
0x1400056e4  pop     r14
0x1400056e6  pop     rdi
0x1400056e7  pop     rsi
0x1400056e8  pop     rbp
0x1400056e9  retn
0x1400056ea  mov     rcx, [rbp+188h]; this
0x1400056f1  mov     edx, 0A0Bh; void *
0x1400056f6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400056fc  mov     rcx, [rbp+188h]; this
0x140005703  mov     edx, 0A0Bh; void *
0x140005708  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000570e  mov     rcx, [rbp+188h]; this
0x140005715  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x14000571b  mov     rcx, [rbp+188h]; this
0x140005722  mov     edx, 0A15h; void *
0x140005727  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000572d  mov     rcx, [rbp+188h]; this
0x140005734  mov     edx, 0A0Bh; void *
0x140005739  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000573f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140005745  mov     rcx, [rbp+188h]; this
0x14000574c  mov     edx, 0A0Bh; void *
0x140005751  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005757  mov     rcx, [rbp+188h]; this
0x14000575e  mov     edx, 0A0Bh; void *
0x140005763  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005769  mov     rcx, [rbp+188h]; this
0x140005770  mov     edx, 0A15h; void *
0x140005775  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000577b  mov     rcx, [rbp+188h]; this
0x140005782  mov     edx, 0A15h; void *
0x140005787  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
