# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000504c`
- end: `0x180005419`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `973`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180005fb0`

## callees

- `0x18000504c`
- `0x180005420`
- `0x180005714`
- `0x180005ca8`
- `0x180006828`
- `0x180006a74`
- `0x180006f2c`
- `0x180006fb8`
- `0x180007448`
- `0x180007458`
- `0x18007728a`
- `0x1800772c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800050e5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800050e5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800050c4`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800050c4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000517b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800052b9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005329`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000517b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800052b9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005329`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005290`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005290`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005282`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005282`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005085`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005085`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000518c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000525c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005274`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000533f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000518c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000525c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005274`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000533f`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
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
  _QWORD *v24; // rsi
  unsigned int v25; // r14d
  int v26; // eax
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  HANDLE ProcessHeap; // rax
  __int64 v32; // r8
  const char *v33; // r9
  __int64 v34; // r8
  const char *v35; // r9
  __int128 v36; // xmm0
  __int64 v37; // r8
  const char *v38; // r9
  __int64 v39; // r8
  const char *v40; // r9
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  int v43; // [rsp+20h] [rbp-E0h]
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
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v41);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v42);
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
  v21 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v24 = (_QWORD *)v21;
  if ( v21 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v21 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    v26 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v23,
            v21 >> 2);
    v25 = v26;
    if ( v26 >= 0 )
    {
      v36 = *(_OWORD *)hObject;
      *(_DWORD *)v24 = 1;
      v24[1] = v6;
      *((_OWORD *)v24 + 1) = v36;
      memset_0((char *)v24 + 34, 0, 0x56u);
      *((_WORD *)v24 + 16) = 88;
      *((_DWORD *)v24 + 9) = 1;
      memset_0(v24 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v24;
LABEL_28:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v37, v38);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v39, v40);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v26, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
  }
  else
  {
    v25 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v25, v43);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v32, v33);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v34, v35);
  return v25;
}

```

## disassembly

```asm
0x18000504c  mov     [rsp-8+arg_10], rbx
0x180005051  push    rbp
0x180005052  push    rsi
0x180005053  push    rdi
0x180005054  push    r14
0x180005056  push    r15
0x180005058  lea     rbp, [rsp-160h]
0x180005060  sub     rsp, 260h
0x180005067  mov     rax, cs:__security_cookie
0x18000506e  xor     rax, rsp
0x180005071  mov     [rbp+180h+var_30], rax
0x180005078  mov     r15, rdx
0x18000507b  mov     qword ptr [rdx], 0
0x180005082  mov     rbx, rcx
0x180005085  call    cs:__imp_GetCurrentProcessId
0x18000508b  mov     r14d, 78h ; 'x'
0x180005091  mov     [rsp+280h+var_258], rbx
0x180005096  mov     r9d, eax
0x180005099  mov     [rsp+280h+var_260], r14d; int
0x18000509e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800050a5  mov     edx, 104h; unsigned __int64
0x1800050aa  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800050af  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800050b4  mov     r9d, 1F0001h; dwDesiredAccess
0x1800050ba  lea     rdx, [rsp+280h+Name]; lpName
0x1800050bf  xor     r8d, r8d; dwFlags
0x1800050c2  xor     ecx, ecx; lpMutexAttributes
0x1800050c4  call    cs:__imp_CreateMutexExW
0x1800050ca  mov     rbx, rax
0x1800050cd  test    rax, rax
0x1800050d0  jnz     short loc_1800050DC
0x1800050d2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800050d7  jmp     loc_18000534B
0x1800050dc  xor     r8d, r8d; bAlertable
0x1800050df  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800050e2  mov     rcx, rbx; hHandle
0x1800050e5  call    cs:__imp_WaitForSingleObjectEx
0x1800050eb  cmp     eax, 102h
0x1800050f0  jz      short loc_180005102
0x1800050f2  test    eax, 0FFFFFF7Fh
0x1800050f7  jnz     loc_180005383
0x1800050fd  mov     rdi, rbx
0x180005100  jmp     short loc_180005104
0x180005102  xor     edi, edi
0x180005104  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180005109  mov     [rsp+280h+hObject], 0
0x180005112  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005117  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000511c  mov     esi, eax
0x18000511e  test    eax, eax
0x180005120  jns     short loc_1800051A1
0x180005122  mov     rcx, [rbp+188h]; this
0x180005129  lea     r8, aWil; "wil"
0x180005130  mov     r9d, eax; char *
0x180005133  mov     edx, 66h ; 'f'; void *
0x180005138  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000513d  mov     rcx, [rbp+188h]; this
0x180005144  lea     r8, aWil; "wil"
0x18000514b  mov     r9d, esi; char *
0x18000514e  mov     edx, 6Fh ; 'o'; void *
0x180005153  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005158  mov     rcx, [rbp+188h]; this
0x18000515f  lea     r8, aWil; "wil"
0x180005166  mov     r9d, esi; char *
0x180005169  mov     edx, 12Eh; void *
0x18000516e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005173  test    rdi, rdi
0x180005176  jz      short loc_180005189
0x180005178  mov     rcx, rdi; hMutex
0x18000517b  call    cs:__imp_ReleaseMutex
0x180005181  test    eax, eax
0x180005183  jz      loc_180005395
0x180005189  mov     rcx, rbx; hObject
0x18000518c  call    cs:__imp_CloseHandle
0x180005192  test    eax, eax
0x180005194  jz      loc_1800053A7
0x18000519a  mov     eax, esi
0x18000519c  jmp     loc_18000534B
0x1800051a1  mov     rax, [rsp+280h+hObject]
0x1800051a6  lea     rcx, ds:0[rax*4]
0x1800051ae  test    rcx, rcx
0x1800051b1  jz      short loc_1800051C1
0x1800051b3  mov     [r15], rcx
0x1800051b6  mov     eax, [rcx]
0x1800051b8  inc     eax
0x1800051ba  mov     [rcx], eax
0x1800051bc  jmp     loc_180005321
0x1800051c1  mov     rdx, r14; dwBytes
0x1800051c4  mov     qword ptr [r15], 0
0x1800051cb  mov     ecx, 8; dwFlags
0x1800051d0  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800051d5  mov     rsi, rax
0x1800051d8  test    rax, rax
0x1800051db  jnz     short loc_180005203
0x1800051dd  mov     rcx, [rbp+188h]; this
0x1800051e4  lea     r8, aWil; "wil"
0x1800051eb  mov     r14d, 8007000Eh
0x1800051f1  mov     edx, 14Bh; void *
0x1800051f6  mov     r9d, r14d; char *
0x1800051f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800051fe  jmp     loc_180005296
0x180005203  xorps   xmm0, xmm0
0x180005206  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x18000520c  test    sil, 3
0x180005210  jnz     loc_1800053B9
0x180005216  mov     r9, rsi
0x180005219  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000521e  shr     r9, 2; unsigned __int64
0x180005222  lea     rcx, [rsp+280h+hObject]; this
0x180005227  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18000522c  mov     r14d, eax
0x18000522f  test    eax, eax
0x180005231  jns     loc_1800052DD
0x180005237  mov     rcx, [rbp+188h]; this
0x18000523e  lea     r8, aWil; "wil"
0x180005245  mov     r9d, eax; char *
0x180005248  mov     edx, 14Eh; void *
0x18000524d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005252  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180005257  test    rcx, rcx
0x18000525a  jz      short loc_18000526A
0x18000525c  call    cs:__imp_CloseHandle
0x180005262  test    eax, eax
0x180005264  jz      loc_1800053BF
0x18000526a  mov     rcx, [rsp+280h+hObject]; hObject
0x18000526f  test    rcx, rcx
0x180005272  jz      short loc_180005282
0x180005274  call    cs:__imp_CloseHandle
0x18000527a  test    eax, eax
0x18000527c  jz      loc_1800053D1
0x180005282  call    cs:__imp_GetProcessHeap
0x180005288  mov     r8, rsi; lpMem
0x18000528b  xor     edx, edx; dwFlags
0x18000528d  mov     rcx, rax; hHeap
0x180005290  call    cs:__imp_HeapFree
0x180005296  mov     rcx, [rbp+188h]; this
0x18000529d  lea     r8, aWil; "wil"
0x1800052a4  mov     r9d, r14d; char *
0x1800052a7  mov     edx, 137h; void *
0x1800052ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800052b1  test    rdi, rdi
0x1800052b4  jz      short loc_1800052C7
0x1800052b6  mov     rcx, rdi; hMutex
0x1800052b9  call    cs:__imp_ReleaseMutex
0x1800052bf  test    eax, eax
0x1800052c1  jz      loc_1800053E3
0x1800052c7  mov     rcx, rbx; hObject
0x1800052ca  call    cs:__imp_CloseHandle
0x1800052d0  test    eax, eax
0x1800052d2  jz      loc_1800053F5
0x1800052d8  mov     eax, r14d
0x1800052db  jmp     short loc_18000534B
0x1800052dd  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800052e2  xor     edx, edx; Val
0x1800052e4  mov     dword ptr [rsi], 1
0x1800052ea  lea     rcx, [rsi+22h]; void *
0x1800052ee  mov     [rsi+8], rbx
0x1800052f2  movdqu  xmmword ptr [rsi+10h], xmm0
0x1800052f7  lea     r8d, [rdx+56h]; Size
0x1800052fb  call    memset_0
0x180005300  xor     edx, edx; Val
0x180005302  mov     word ptr [rsi+20h], 58h ; 'X'
0x180005308  lea     rcx, [rsi+28h]; void *
0x18000530c  mov     dword ptr [rsi+24h], 1
0x180005313  lea     r8d, [rdx+50h]; Size
0x180005317  call    memset_0
0x18000531c  xor     ebx, ebx
0x18000531e  mov     [r15], rsi
0x180005321  test    rdi, rdi
0x180005324  jz      short loc_180005337
0x180005326  mov     rcx, rdi; hMutex
0x180005329  call    cs:__imp_ReleaseMutex
0x18000532f  test    eax, eax
0x180005331  jz      loc_180005407
0x180005337  test    rbx, rbx
0x18000533a  jz      short loc_180005349
0x18000533c  mov     rcx, rbx; hObject
0x18000533f  call    cs:__imp_CloseHandle
0x180005345  test    eax, eax
0x180005347  jz      short loc_180005371
0x180005349  xor     eax, eax
0x18000534b  mov     rcx, [rbp+180h+var_30]
0x180005352  xor     rcx, rsp; StackCookie
0x180005355  call    __security_check_cookie
0x18000535a  mov     rbx, [rsp+280h+arg_10]
0x180005362  add     rsp, 260h
0x180005369  pop     r15
0x18000536b  pop     r14
0x18000536d  pop     rdi
0x18000536e  pop     rsi
0x18000536f  pop     rbp
0x180005370  retn
0x180005371  mov     rcx, [rbp+188h]; this
0x180005378  mov     edx, 0A0Bh; void *
0x18000537d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005383  mov     rcx, [rbp+188h]; this
0x18000538a  mov     edx, 0E01h; void *
0x18000538f  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180005395  mov     rcx, [rbp+188h]; this
0x18000539c  mov     edx, 0A15h; void *
0x1800053a1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800053a7  mov     rcx, [rbp+188h]; this
0x1800053ae  mov     edx, 0A0Bh; void *
0x1800053b3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800053b9  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800053bf  mov     rcx, [rbp+188h]; this
0x1800053c6  mov     edx, 0A0Bh; void *
0x1800053cb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800053d1  mov     rcx, [rbp+188h]; this
0x1800053d8  mov     edx, 0A0Bh; void *
0x1800053dd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800053e3  mov     rcx, [rbp+188h]; this
0x1800053ea  mov     edx, 0A15h; void *
0x1800053ef  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800053f5  mov     rcx, [rbp+188h]; this
0x1800053fc  mov     edx, 0A0Bh; void *
0x180005401  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005407  mov     rcx, [rbp+188h]; this
0x18000540e  mov     edx, 0A15h; void *
0x180005413  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
