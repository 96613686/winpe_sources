# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18001dd6c`
- end: `0x18001e15d`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x180025b10`

## callees

- `0x180002ad0`
- `0x18000346c`
- `0x180014a14`
- `0x180018128`
- `0x18001dd6c`
- `0x180023474`
- `0x180026250`
- `0x180031454`
- `0x18003d9b8`
- `0x180048954`
- `0x18004eb30`
- `0x18004f148`
- `0x180052f18`
- `0x180052f28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001dde3`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001dde3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001de04`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001de04`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001de9a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001dfad`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001e06c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001de9a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001dfad`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001e06c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18001e02f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18001e02f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001dda5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001dda5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001df84`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001df84`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001df76`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001df76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001deab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dfbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e082`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001deab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dfbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e082`

## string_xrefs

- `0x18001e0bb`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18001e0d4`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18001e0fa`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18001e113`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18001e132`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18001e14b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  const char *v16; // r9
  const char *v17; // r9
  _DWORD *v18; // rcx
  unsigned __int64 v19; // rax
  wil::details::in1diag3 *v20; // rcx
  bool v21; // r8
  _DWORD *v22; // r14
  int v23; // eax
  HANDLE ProcessHeap; // rax
  const char *v25; // r9
  const char *v26; // r9
  const char *v27; // r9
  const char *v28; // r9
  int v29; // [rsp+20h] [rbp-E0h]
  int v30; // [rsp+20h] [rbp-E0h]
  int v31; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v32[2]; // [rsp+30h] [rbp-D0h] BYREF
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
  v32[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, v32, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v29);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v30);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v16);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v17);
    return v15;
  }
  v18 = (_DWORD *)(4 * v32[0]);
  if ( 4 * v32[0] )
  {
    *a2 = v18;
    ++*v18;
    goto LABEL_24;
  }
  *a2 = 0;
  v19 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v22 = (_DWORD *)v19;
  if ( !v19 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
    goto LABEL_19;
  }
  *(_OWORD *)v32 = 0;
  if ( (v19 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v20);
  v23 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)v32,
          Name,
          v21,
          v19 >> 2);
  v15 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v23, 304);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v32);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v22);
LABEL_19:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v15, v31);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v25);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v26);
    return v15;
  }
  *((_QWORD *)v22 + 2) = v32[0];
  *((_QWORD *)v22 + 3) = v32[1];
  *v22 = 1;
  *((_QWORD *)v22 + 1) = v6;
  v32[0] = 0;
  v32[1] = 0;
  memset_0(v22 + 10, 0, 0x108u);
  *((_QWORD *)v22 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v22 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v22 + 58), 0, 0);
  *((_QWORD *)v22 + 34) = 0;
  *((_QWORD *)v22 + 35) = 0;
  *((_QWORD *)v22 + 36) = 0;
  *((_QWORD *)v22 + 37) = 0;
  *a2 = v22;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v32);
  v6 = 0;
LABEL_24:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA15,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v27);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v28);
  return 0;
}

```

## disassembly

```asm
0x18001dd6c  mov     [rsp-8+arg_10], rbx
0x18001dd71  push    rbp
0x18001dd72  push    rsi
0x18001dd73  push    rdi
0x18001dd74  push    r14
0x18001dd76  push    r15
0x18001dd78  lea     rbp, [rsp-160h]
0x18001dd80  sub     rsp, 260h
0x18001dd87  mov     rax, cs:__security_cookie
0x18001dd8e  xor     rax, rsp
0x18001dd91  mov     [rbp+180h+var_30], rax
0x18001dd98  mov     r15, rdx
0x18001dd9b  mov     qword ptr [rdx], 0
0x18001dda2  mov     rbx, rcx
0x18001dda5  call    cs:__imp_GetCurrentProcessId
0x18001ddab  mov     r14d, 130h
0x18001ddb1  mov     [rsp+280h+var_258], rbx
0x18001ddb6  mov     r9d, eax
0x18001ddb9  mov     [rsp+280h+var_260], r14d; int
0x18001ddbe  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001ddc5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001ddca  lea     edx, [r14-2Ch]; unsigned __int64
0x18001ddce  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001ddd3  mov     r9d, 1F0001h; dwDesiredAccess
0x18001ddd9  lea     rdx, [rsp+280h+Name]; lpName
0x18001ddde  xor     r8d, r8d; dwFlags
0x18001dde1  xor     ecx, ecx; lpMutexAttributes
0x18001dde3  call    cs:__imp_CreateMutexExW
0x18001dde9  mov     rbx, rax
0x18001ddec  test    rax, rax
0x18001ddef  jnz     short loc_18001DDFB
0x18001ddf1  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001ddf6  jmp     loc_18001E08E
0x18001ddfb  xor     r8d, r8d; bAlertable
0x18001ddfe  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001de01  mov     rcx, rbx; hHandle
0x18001de04  call    cs:__imp_WaitForSingleObjectEx
0x18001de0a  cmp     eax, 102h
0x18001de0f  jz      short loc_18001DE21
0x18001de11  test    eax, 0FFFFFF7Fh
0x18001de16  jnz     loc_18001E0E6
0x18001de1c  mov     rdi, rbx
0x18001de1f  jmp     short loc_18001DE23
0x18001de21  xor     edi, edi
0x18001de23  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x18001de28  mov     [rsp+280h+var_250], 0
0x18001de31  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001de36  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18001de3b  mov     esi, eax
0x18001de3d  test    eax, eax
0x18001de3f  jns     short loc_18001DEC0
0x18001de41  mov     rcx, [rbp+188h]; this
0x18001de48  lea     r8, aWil; "wil"
0x18001de4f  mov     r9d, eax; char *
0x18001de52  mov     edx, 66h ; 'f'; void *
0x18001de57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001de5c  mov     rcx, [rbp+188h]; this
0x18001de63  lea     r8, aWil; "wil"
0x18001de6a  mov     r9d, esi; char *
0x18001de6d  mov     edx, 6Fh ; 'o'; void *
0x18001de72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001de77  mov     rcx, [rbp+188h]; this
0x18001de7e  lea     r8, aWil; "wil"
0x18001de85  mov     r9d, esi; char *
0x18001de88  mov     edx, 12Eh; void *
0x18001de8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001de92  test    rdi, rdi
0x18001de95  jz      short loc_18001DEA8
0x18001de97  mov     rcx, rdi; hMutex
0x18001de9a  call    cs:__imp_ReleaseMutex
0x18001dea0  test    eax, eax
0x18001dea2  jz      loc_18001E0F3
0x18001dea8  mov     rcx, rbx; hObject
0x18001deab  call    cs:__imp_CloseHandle
0x18001deb1  test    eax, eax
0x18001deb3  jz      loc_18001E10C
0x18001deb9  mov     eax, esi
0x18001debb  jmp     loc_18001E08E
0x18001dec0  mov     rax, [rsp+280h+var_250]
0x18001dec5  lea     rcx, ds:0[rax*4]
0x18001decd  test    rcx, rcx
0x18001ded0  jz      short loc_18001DEE0
0x18001ded2  mov     [r15], rcx
0x18001ded5  mov     eax, [rcx]
0x18001ded7  inc     eax
0x18001ded9  mov     [rcx], eax
0x18001dedb  jmp     loc_18001E064
0x18001dee0  mov     rdx, r14; dwBytes
0x18001dee3  mov     qword ptr [r15], 0
0x18001deea  mov     ecx, 8; dwFlags
0x18001deef  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18001def4  mov     r14, rax
0x18001def7  test    rax, rax
0x18001defa  jnz     short loc_18001DF1E
0x18001defc  mov     rcx, [rbp+188h]; this
0x18001df03  lea     r8, aWil; "wil"
0x18001df0a  mov     esi, 8007000Eh
0x18001df0f  mov     edx, 14Bh; void *
0x18001df14  mov     r9d, esi; char *
0x18001df17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001df1c  jmp     short loc_18001DF8A
0x18001df1e  xorps   xmm0, xmm0
0x18001df21  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x18001df27  test    r14b, 3
0x18001df2b  jnz     loc_18001E125
0x18001df31  mov     r9, r14
0x18001df34  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18001df39  shr     r9, 2; unsigned __int64
0x18001df3d  lea     rcx, [rsp+280h+var_250]; this
0x18001df42  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18001df47  mov     esi, eax
0x18001df49  test    eax, eax
0x18001df4b  jns     loc_18001DFD1
0x18001df51  mov     rcx, [rbp+188h]; this
0x18001df58  lea     r8, aWil; "wil"
0x18001df5f  mov     r9d, eax; char *
0x18001df62  mov     edx, 14Eh; void *
0x18001df67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001df6c  lea     rcx, [rsp+280h+var_250]; this
0x18001df71  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18001df76  call    cs:__imp_GetProcessHeap
0x18001df7c  mov     r8, r14; lpMem
0x18001df7f  xor     edx, edx; dwFlags
0x18001df81  mov     rcx, rax; hHeap
0x18001df84  call    cs:__imp_HeapFree
0x18001df8a  mov     rcx, [rbp+188h]; this
0x18001df91  lea     r8, aWil; "wil"
0x18001df98  mov     r9d, esi; char *
0x18001df9b  mov     edx, 137h; void *
0x18001dfa0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dfa5  test    rdi, rdi
0x18001dfa8  jz      short loc_18001DFBB
0x18001dfaa  mov     rcx, rdi; hMutex
0x18001dfad  call    cs:__imp_ReleaseMutex
0x18001dfb3  test    eax, eax
0x18001dfb5  jz      loc_18001E12B
0x18001dfbb  mov     rcx, rbx; hObject
0x18001dfbe  call    cs:__imp_CloseHandle
0x18001dfc4  test    eax, eax
0x18001dfc6  jz      loc_18001E0CD
0x18001dfcc  jmp     loc_18001DEB9
0x18001dfd1  mov     rax, [rsp+280h+var_250]
0x18001dfd6  lea     rcx, [r14+28h]; void *
0x18001dfda  mov     [r14+10h], rax
0x18001dfde  xor     edx, edx; Val
0x18001dfe0  mov     rax, [rsp+280h+var_250+8]
0x18001dfe5  mov     r8d, 108h; Size
0x18001dfeb  mov     [r14+18h], rax
0x18001dfef  mov     dword ptr [r14], 1
0x18001dff6  mov     [r14+8], rbx
0x18001dffa  mov     [rsp+280h+var_250], 0
0x18001e003  mov     [rsp+280h+var_250+8], 0
0x18001e00c  call    memset_0
0x18001e011  xor     eax, eax
0x18001e013  lea     rcx, [r14+28h]; this
0x18001e017  mov     [r14+20h], rax
0x18001e01b  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18001e020  lea     rbx, [r14+0E8h]
0x18001e027  xor     r8d, r8d; Flags
0x18001e02a  mov     rcx, rbx; lpCriticalSection
0x18001e02d  xor     edx, edx; dwSpinCount
0x18001e02f  call    cs:__imp_InitializeCriticalSectionEx
0x18001e035  mov     qword ptr [rbx+28h], 0
0x18001e03d  lea     rcx, [rsp+280h+var_250]; this
0x18001e042  mov     qword ptr [rbx+30h], 0
0x18001e04a  mov     qword ptr [rbx+38h], 0
0x18001e052  mov     qword ptr [rbx+40h], 0
0x18001e05a  mov     [r15], r14
0x18001e05d  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18001e062  xor     ebx, ebx
0x18001e064  test    rdi, rdi
0x18001e067  jz      short loc_18001E07A
0x18001e069  mov     rcx, rdi; hMutex
0x18001e06c  call    cs:__imp_ReleaseMutex
0x18001e072  test    eax, eax
0x18001e074  jz      loc_18001E144
0x18001e07a  test    rbx, rbx
0x18001e07d  jz      short loc_18001E08C
0x18001e07f  mov     rcx, rbx; hObject
0x18001e082  call    cs:__imp_CloseHandle
0x18001e088  test    eax, eax
0x18001e08a  jz      short loc_18001E0B4
0x18001e08c  xor     eax, eax
0x18001e08e  mov     rcx, [rbp+180h+var_30]
0x18001e095  xor     rcx, rsp; StackCookie
0x18001e098  call    __security_check_cookie
0x18001e09d  mov     rbx, [rsp+280h+arg_10]
0x18001e0a5  add     rsp, 260h
0x18001e0ac  pop     r15
0x18001e0ae  pop     r14
0x18001e0b0  pop     rdi
0x18001e0b1  pop     rsi
0x18001e0b2  pop     rbp
0x18001e0b3  retn
0x18001e0b4  mov     rcx, [rbp+188h]; this
0x18001e0bb  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001e0c2  mov     edx, 0A0Bh; void *
0x18001e0c7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001e0cd  mov     rcx, [rbp+188h]; this
0x18001e0d4  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001e0db  mov     edx, 0A0Bh; void *
0x18001e0e0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001e0e6  mov     rcx, [rbp+188h]; this
0x18001e0ed  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18001e0f3  mov     rcx, [rbp+188h]; this
0x18001e0fa  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001e101  mov     edx, 0A15h; void *
0x18001e106  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001e10c  mov     rcx, [rbp+188h]; this
0x18001e113  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001e11a  mov     edx, 0A0Bh; void *
0x18001e11f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001e125  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18001e12b  mov     rcx, [rbp+188h]; this
0x18001e132  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001e139  mov     edx, 0A15h; void *
0x18001e13e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001e144  mov     rcx, [rbp+188h]; this
0x18001e14b  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001e152  mov     edx, 0A15h; void *
0x18001e157  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
