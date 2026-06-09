# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000900c`
- end: `0x1800093d4`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18000a8a4`

## callees

- `0x1800029d0`
- `0x1800035e8`
- `0x180006134`
- `0x18000900c`
- `0x1800097d4`
- `0x180009cfc`
- `0x18000a768`
- `0x18000ae30`
- `0x18000cb10`
- `0x18000d324`
- `0x18001140c`
- `0x18001141c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009242`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009242`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009250`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009250`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009045`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009045`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000913b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009279`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800092e9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000913b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009279`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800092e9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009084`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009084`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800090a5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800090a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000914c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000921c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009234`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000928a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800092ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000914c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000921c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009234`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000928a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800092ff`

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
  _QWORD *v24; // rsi
  unsigned int v25; // r14d
  int v26; // eax
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  __int128 v36; // xmm0
  unsigned int v37; // r8d
  const char *v38; // r9
  unsigned int v39; // r8d
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
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v9, v10, v11);
    v12 = v6;
  }
  hObject[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    (__int64)v9,
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
0x18000900c  mov     [rsp-8+arg_10], rbx
0x180009011  push    rbp
0x180009012  push    rsi
0x180009013  push    rdi
0x180009014  push    r14
0x180009016  push    r15
0x180009018  lea     rbp, [rsp-160h]
0x180009020  sub     rsp, 260h
0x180009027  mov     rax, cs:__security_cookie
0x18000902e  xor     rax, rsp
0x180009031  mov     [rbp+180h+var_30], rax
0x180009038  mov     r15, rdx
0x18000903b  mov     qword ptr [rdx], 0
0x180009042  mov     rbx, rcx
0x180009045  call    cs:__imp_GetCurrentProcessId
0x18000904b  mov     r14d, 78h ; 'x'
0x180009051  mov     [rsp+280h+var_258], rbx
0x180009056  mov     r9d, eax
0x180009059  mov     [rsp+280h+var_260], r14d; int
0x18000905e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180009065  mov     edx, 104h; unsigned __int64
0x18000906a  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000906f  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180009074  mov     r9d, 1F0001h; dwDesiredAccess
0x18000907a  lea     rdx, [rsp+280h+Name]; lpName
0x18000907f  xor     r8d, r8d; dwFlags
0x180009082  xor     ecx, ecx; lpMutexAttributes
0x180009084  call    cs:__imp_CreateMutexExW
0x18000908a  mov     rbx, rax
0x18000908d  test    rax, rax
0x180009090  jnz     short loc_18000909C
0x180009092  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009097  jmp     loc_18000930B
0x18000909c  xor     r8d, r8d; bAlertable
0x18000909f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800090a2  mov     rcx, rbx; hHandle
0x1800090a5  call    cs:__imp_WaitForSingleObjectEx
0x1800090ab  cmp     eax, 102h
0x1800090b0  jz      short loc_1800090C2
0x1800090b2  test    eax, 0FFFFFF7Fh
0x1800090b7  jnz     loc_180009343
0x1800090bd  mov     rdi, rbx
0x1800090c0  jmp     short loc_1800090C4
0x1800090c2  xor     edi, edi
0x1800090c4  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800090c9  mov     [rsp+280h+hObject], 0
0x1800090d2  lea     rcx, [rsp+280h+Name]; wchar_t *
0x1800090d7  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x1800090dc  mov     esi, eax
0x1800090de  test    eax, eax
0x1800090e0  jns     short loc_180009161
0x1800090e2  mov     rcx, [rbp+188h]; this
0x1800090e9  lea     r8, aWil; "wil"
0x1800090f0  mov     r9d, eax; char *
0x1800090f3  mov     edx, 66h ; 'f'; void *
0x1800090f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800090fd  mov     rcx, [rbp+188h]; this
0x180009104  lea     r8, aWil; "wil"
0x18000910b  mov     r9d, esi; char *
0x18000910e  mov     edx, 6Fh ; 'o'; void *
0x180009113  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009118  mov     rcx, [rbp+188h]; this
0x18000911f  lea     r8, aWil; "wil"
0x180009126  mov     r9d, esi; char *
0x180009129  mov     edx, 12Eh; void *
0x18000912e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009133  test    rdi, rdi
0x180009136  jz      short loc_180009149
0x180009138  mov     rcx, rdi; hMutex
0x18000913b  call    cs:__imp_ReleaseMutex
0x180009141  test    eax, eax
0x180009143  jz      loc_180009350
0x180009149  mov     rcx, rbx; hObject
0x18000914c  call    cs:__imp_CloseHandle
0x180009152  test    eax, eax
0x180009154  jz      loc_180009362
0x18000915a  mov     eax, esi
0x18000915c  jmp     loc_18000930B
0x180009161  mov     rax, [rsp+280h+hObject]
0x180009166  lea     rcx, ds:0[rax*4]
0x18000916e  test    rcx, rcx
0x180009171  jz      short loc_180009181
0x180009173  mov     [r15], rcx
0x180009176  mov     eax, [rcx]
0x180009178  inc     eax
0x18000917a  mov     [rcx], eax
0x18000917c  jmp     loc_1800092E1
0x180009181  mov     rdx, r14; dwBytes
0x180009184  mov     qword ptr [r15], 0
0x18000918b  mov     ecx, 8; dwFlags
0x180009190  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009195  mov     rsi, rax
0x180009198  test    rax, rax
0x18000919b  jnz     short loc_1800091C3
0x18000919d  mov     rcx, [rbp+188h]; this
0x1800091a4  lea     r8, aWil; "wil"
0x1800091ab  mov     r14d, 8007000Eh
0x1800091b1  mov     edx, 14Bh; void *
0x1800091b6  mov     r9d, r14d; char *
0x1800091b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800091be  jmp     loc_180009256
0x1800091c3  xorps   xmm0, xmm0
0x1800091c6  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800091cc  test    sil, 3
0x1800091d0  jnz     loc_180009374
0x1800091d6  mov     r9, rsi
0x1800091d9  lea     rdx, [rsp+280h+Name]; wchar_t *
0x1800091de  shr     r9, 2; unsigned __int64
0x1800091e2  lea     rcx, [rsp+280h+hObject]; this
0x1800091e7  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x1800091ec  mov     r14d, eax
0x1800091ef  test    eax, eax
0x1800091f1  jns     loc_18000929D
0x1800091f7  mov     rcx, [rbp+188h]; this
0x1800091fe  lea     r8, aWil; "wil"
0x180009205  mov     r9d, eax; char *
0x180009208  mov     edx, 14Eh; void *
0x18000920d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009212  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180009217  test    rcx, rcx
0x18000921a  jz      short loc_18000922A
0x18000921c  call    cs:__imp_CloseHandle
0x180009222  test    eax, eax
0x180009224  jz      loc_18000937A
0x18000922a  mov     rcx, [rsp+280h+hObject]; hObject
0x18000922f  test    rcx, rcx
0x180009232  jz      short loc_180009242
0x180009234  call    cs:__imp_CloseHandle
0x18000923a  test    eax, eax
0x18000923c  jz      loc_18000938C
0x180009242  call    cs:__imp_GetProcessHeap
0x180009248  mov     r8, rsi; lpMem
0x18000924b  xor     edx, edx; dwFlags
0x18000924d  mov     rcx, rax; hHeap
0x180009250  call    cs:__imp_HeapFree
0x180009256  mov     rcx, [rbp+188h]; this
0x18000925d  lea     r8, aWil; "wil"
0x180009264  mov     r9d, r14d; char *
0x180009267  mov     edx, 137h; void *
0x18000926c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009271  test    rdi, rdi
0x180009274  jz      short loc_180009287
0x180009276  mov     rcx, rdi; hMutex
0x180009279  call    cs:__imp_ReleaseMutex
0x18000927f  test    eax, eax
0x180009281  jz      loc_18000939E
0x180009287  mov     rcx, rbx; hObject
0x18000928a  call    cs:__imp_CloseHandle
0x180009290  test    eax, eax
0x180009292  jz      loc_1800093B0
0x180009298  mov     eax, r14d
0x18000929b  jmp     short loc_18000930B
0x18000929d  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800092a2  xor     edx, edx; Val
0x1800092a4  mov     dword ptr [rsi], 1
0x1800092aa  lea     rcx, [rsi+22h]; void *
0x1800092ae  mov     [rsi+8], rbx
0x1800092b2  movdqu  xmmword ptr [rsi+10h], xmm0
0x1800092b7  lea     r8d, [rdx+56h]; Size
0x1800092bb  call    memset_0
0x1800092c0  xor     edx, edx; Val
0x1800092c2  mov     word ptr [rsi+20h], 58h ; 'X'
0x1800092c8  lea     rcx, [rsi+28h]; void *
0x1800092cc  mov     dword ptr [rsi+24h], 1
0x1800092d3  lea     r8d, [rdx+50h]; Size
0x1800092d7  call    memset_0
0x1800092dc  xor     ebx, ebx
0x1800092de  mov     [r15], rsi
0x1800092e1  test    rdi, rdi
0x1800092e4  jz      short loc_1800092F7
0x1800092e6  mov     rcx, rdi; hMutex
0x1800092e9  call    cs:__imp_ReleaseMutex
0x1800092ef  test    eax, eax
0x1800092f1  jz      loc_1800093C2
0x1800092f7  test    rbx, rbx
0x1800092fa  jz      short loc_180009309
0x1800092fc  mov     rcx, rbx; hObject
0x1800092ff  call    cs:__imp_CloseHandle
0x180009305  test    eax, eax
0x180009307  jz      short loc_180009331
0x180009309  xor     eax, eax
0x18000930b  mov     rcx, [rbp+180h+var_30]
0x180009312  xor     rcx, rsp; StackCookie
0x180009315  call    __security_check_cookie
0x18000931a  mov     rbx, [rsp+280h+arg_10]
0x180009322  add     rsp, 260h
0x180009329  pop     r15
0x18000932b  pop     r14
0x18000932d  pop     rdi
0x18000932e  pop     rsi
0x18000932f  pop     rbp
0x180009330  retn
0x180009331  mov     rcx, [rbp+188h]; this
0x180009338  mov     edx, 0A0Bh; void *
0x18000933d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009343  mov     rcx, [rbp+188h]; this
0x18000934a  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180009350  mov     rcx, [rbp+188h]; this
0x180009357  mov     edx, 0A15h; void *
0x18000935c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009362  mov     rcx, [rbp+188h]; this
0x180009369  mov     edx, 0A0Bh; void *
0x18000936e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009374  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000937a  mov     rcx, [rbp+188h]; this
0x180009381  mov     edx, 0A0Bh; void *
0x180009386  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000938c  mov     rcx, [rbp+188h]; this
0x180009393  mov     edx, 0A0Bh; void *
0x180009398  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000939e  mov     rcx, [rbp+188h]; this
0x1800093a5  mov     edx, 0A15h; void *
0x1800093aa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800093b0  mov     rcx, [rbp+188h]; this
0x1800093b7  mov     edx, 0A0Bh; void *
0x1800093bc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800093c2  mov     rcx, [rbp+188h]; this
0x1800093c9  mov     edx, 0A15h; void *
0x1800093ce  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
