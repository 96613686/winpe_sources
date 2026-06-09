# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180004f48`
- end: `0x180005339`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180005d24`

## callees

- `0x180001e40`
- `0x1800028b4`
- `0x180003d24`
- `0x180004f48`
- `0x1800057f0`
- `0x180005f78`
- `0x180006e28`
- `0x180007d28`
- `0x18000a844`
- `0x18000b34c`
- `0x18000b7e8`
- `0x18000c558`
- `0x18000c568`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004fbf`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004fbf`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005076`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800051b2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000524e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005076`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800051b2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000524e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004fe0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004fe0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000521b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000521b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000517b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000517b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005189`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005189`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004f81`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004f81`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005087`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005155`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000516d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800051c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005264`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005087`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005155`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000516d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800051c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005264`

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
0x180004f48  mov     [rsp-8+arg_10], rbx
0x180004f4d  push    rbp
0x180004f4e  push    rsi
0x180004f4f  push    rdi
0x180004f50  push    r14
0x180004f52  push    r15
0x180004f54  lea     rbp, [rsp-160h]
0x180004f5c  sub     rsp, 260h
0x180004f63  mov     rax, cs:__security_cookie
0x180004f6a  xor     rax, rsp
0x180004f6d  mov     [rbp+180h+var_30], rax
0x180004f74  mov     r15, rdx
0x180004f77  mov     qword ptr [rdx], 0
0x180004f7e  mov     rbx, rcx
0x180004f81  call    cs:__imp_GetCurrentProcessId
0x180004f87  mov     r14d, 130h
0x180004f8d  mov     [rsp+280h+var_258], rbx
0x180004f92  mov     r9d, eax
0x180004f95  mov     [rsp+280h+var_260], r14d; int
0x180004f9a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004fa1  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180004fa6  lea     edx, [r14-2Ch]; unsigned __int64
0x180004faa  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180004faf  mov     r9d, 1F0001h; dwDesiredAccess
0x180004fb5  lea     rdx, [rsp+280h+Name]; lpName
0x180004fba  xor     r8d, r8d; dwFlags
0x180004fbd  xor     ecx, ecx; lpMutexAttributes
0x180004fbf  call    cs:__imp_CreateMutexExW
0x180004fc5  mov     rbx, rax
0x180004fc8  test    rax, rax
0x180004fcb  jnz     short loc_180004FD7
0x180004fcd  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004fd2  jmp     loc_180005270
0x180004fd7  xor     r8d, r8d; bAlertable
0x180004fda  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004fdd  mov     rcx, rbx; hHandle
0x180004fe0  call    cs:__imp_WaitForSingleObjectEx
0x180004fe6  cmp     eax, 102h
0x180004feb  jz      short loc_180004FFD
0x180004fed  test    eax, 0FFFFFF7Fh
0x180004ff2  jnz     loc_1800052BA
0x180004ff8  mov     rdi, rbx
0x180004ffb  jmp     short loc_180004FFF
0x180004ffd  xor     edi, edi
0x180004fff  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180005004  mov     [rsp+280h+hObject], 0
0x18000500d  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180005012  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x180005017  mov     esi, eax
0x180005019  test    eax, eax
0x18000501b  jns     short loc_18000509C
0x18000501d  mov     rcx, [rbp+188h]; this
0x180005024  lea     r8, aWil; "wil"
0x18000502b  mov     r9d, eax; char *
0x18000502e  mov     edx, 66h ; 'f'; void *
0x180005033  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005038  mov     rcx, [rbp+188h]; this
0x18000503f  lea     r8, aWil; "wil"
0x180005046  mov     r9d, esi; char *
0x180005049  mov     edx, 6Fh ; 'o'; void *
0x18000504e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005053  mov     rcx, [rbp+188h]; this
0x18000505a  lea     r8, aWil; "wil"
0x180005061  mov     r9d, esi; char *
0x180005064  mov     edx, 12Eh; void *
0x180005069  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000506e  test    rdi, rdi
0x180005071  jz      short loc_180005084
0x180005073  mov     rcx, rdi; hMutex
0x180005076  call    cs:__imp_ReleaseMutex
0x18000507c  test    eax, eax
0x18000507e  jz      loc_1800052C7
0x180005084  mov     rcx, rbx; hObject
0x180005087  call    cs:__imp_CloseHandle
0x18000508d  test    eax, eax
0x18000508f  jz      loc_1800052D9
0x180005095  mov     eax, esi
0x180005097  jmp     loc_180005270
0x18000509c  mov     rax, [rsp+280h+hObject]
0x1800050a1  lea     rcx, ds:0[rax*4]
0x1800050a9  test    rcx, rcx
0x1800050ac  jz      short loc_1800050BC
0x1800050ae  mov     [r15], rcx
0x1800050b1  mov     eax, [rcx]
0x1800050b3  inc     eax
0x1800050b5  mov     [rcx], eax
0x1800050b7  jmp     loc_180005246
0x1800050bc  mov     rdx, r14; dwBytes
0x1800050bf  mov     qword ptr [r15], 0
0x1800050c6  mov     ecx, 8; dwFlags
0x1800050cb  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800050d0  mov     r14, rax
0x1800050d3  test    rax, rax
0x1800050d6  jnz     short loc_1800050FD
0x1800050d8  mov     rcx, [rbp+188h]; this
0x1800050df  lea     r8, aWil; "wil"
0x1800050e6  mov     esi, 8007000Eh
0x1800050eb  mov     edx, 14Bh; void *
0x1800050f0  mov     r9d, esi; char *
0x1800050f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800050f8  jmp     loc_18000518F
0x1800050fd  xorps   xmm0, xmm0
0x180005100  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180005106  test    r14b, 3
0x18000510a  jnz     loc_1800052EB
0x180005110  mov     r9, r14
0x180005113  lea     rdx, [rsp+280h+Name]; wchar_t *
0x180005118  shr     r9, 2; unsigned __int64
0x18000511c  lea     rcx, [rsp+280h+hObject]; this
0x180005121  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x180005126  mov     esi, eax
0x180005128  test    eax, eax
0x18000512a  jns     loc_1800051D6
0x180005130  mov     rcx, [rbp+188h]; this
0x180005137  lea     r8, aWil; "wil"
0x18000513e  mov     r9d, eax; char *
0x180005141  mov     edx, 14Eh; void *
0x180005146  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000514b  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180005150  test    rcx, rcx
0x180005153  jz      short loc_180005163
0x180005155  call    cs:__imp_CloseHandle
0x18000515b  test    eax, eax
0x18000515d  jz      loc_1800052F1
0x180005163  mov     rcx, [rsp+280h+hObject]; hObject
0x180005168  test    rcx, rcx
0x18000516b  jz      short loc_18000517B
0x18000516d  call    cs:__imp_CloseHandle
0x180005173  test    eax, eax
0x180005175  jz      loc_180005303
0x18000517b  call    cs:__imp_GetProcessHeap
0x180005181  mov     r8, r14; lpMem
0x180005184  xor     edx, edx; dwFlags
0x180005186  mov     rcx, rax; hHeap
0x180005189  call    cs:__imp_HeapFree
0x18000518f  mov     rcx, [rbp+188h]; this
0x180005196  lea     r8, aWil; "wil"
0x18000519d  mov     r9d, esi; char *
0x1800051a0  mov     edx, 137h; void *
0x1800051a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800051aa  test    rdi, rdi
0x1800051ad  jz      short loc_1800051C0
0x1800051af  mov     rcx, rdi; hMutex
0x1800051b2  call    cs:__imp_ReleaseMutex
0x1800051b8  test    eax, eax
0x1800051ba  jz      loc_180005315
0x1800051c0  mov     rcx, rbx; hObject
0x1800051c3  call    cs:__imp_CloseHandle
0x1800051c9  test    eax, eax
0x1800051cb  jz      loc_1800052A8
0x1800051d1  jmp     loc_180005095
0x1800051d6  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800051db  lea     rcx, [r14+28h]; void *
0x1800051df  mov     dword ptr [r14], 1
0x1800051e6  xor     edx, edx; Val
0x1800051e8  mov     [r14+8], rbx
0x1800051ec  mov     r8d, 108h; Size
0x1800051f2  movdqu  xmmword ptr [r14+10h], xmm0
0x1800051f8  call    memset_0
0x1800051fd  xor     eax, eax
0x1800051ff  lea     rcx, [r14+28h]; this
0x180005203  mov     [r14+20h], rax
0x180005207  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000520c  lea     rbx, [r14+0E8h]
0x180005213  xor     r8d, r8d; Flags
0x180005216  mov     rcx, rbx; lpCriticalSection
0x180005219  xor     edx, edx; dwSpinCount
0x18000521b  call    cs:__imp_InitializeCriticalSectionEx
0x180005221  mov     qword ptr [rbx+28h], 0
0x180005229  mov     qword ptr [rbx+30h], 0
0x180005231  mov     qword ptr [rbx+38h], 0
0x180005239  mov     qword ptr [rbx+40h], 0
0x180005241  xor     ebx, ebx
0x180005243  mov     [r15], r14
0x180005246  test    rdi, rdi
0x180005249  jz      short loc_18000525C
0x18000524b  mov     rcx, rdi; hMutex
0x18000524e  call    cs:__imp_ReleaseMutex
0x180005254  test    eax, eax
0x180005256  jz      loc_180005327
0x18000525c  test    rbx, rbx
0x18000525f  jz      short loc_18000526E
0x180005261  mov     rcx, rbx; hObject
0x180005264  call    cs:__imp_CloseHandle
0x18000526a  test    eax, eax
0x18000526c  jz      short loc_180005296
0x18000526e  xor     eax, eax
0x180005270  mov     rcx, [rbp+180h+var_30]
0x180005277  xor     rcx, rsp; StackCookie
0x18000527a  call    __security_check_cookie
0x18000527f  mov     rbx, [rsp+280h+arg_10]
0x180005287  add     rsp, 260h
0x18000528e  pop     r15
0x180005290  pop     r14
0x180005292  pop     rdi
0x180005293  pop     rsi
0x180005294  pop     rbp
0x180005295  retn
0x180005296  mov     rcx, [rbp+188h]; this
0x18000529d  mov     edx, 0A0Bh; void *
0x1800052a2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800052a8  mov     rcx, [rbp+188h]; this
0x1800052af  mov     edx, 0A0Bh; void *
0x1800052b4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800052ba  mov     rcx, [rbp+188h]; this
0x1800052c1  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800052c7  mov     rcx, [rbp+188h]; this
0x1800052ce  mov     edx, 0A15h; void *
0x1800052d3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800052d9  mov     rcx, [rbp+188h]; this
0x1800052e0  mov     edx, 0A0Bh; void *
0x1800052e5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800052eb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800052f1  mov     rcx, [rbp+188h]; this
0x1800052f8  mov     edx, 0A0Bh; void *
0x1800052fd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005303  mov     rcx, [rbp+188h]; this
0x18000530a  mov     edx, 0A0Bh; void *
0x18000530f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005315  mov     rcx, [rbp+188h]; this
0x18000531c  mov     edx, 0A15h; void *
0x180005321  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005327  mov     rcx, [rbp+188h]; this
0x18000532e  mov     edx, 0A15h; void *
0x180005333  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
