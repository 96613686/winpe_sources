# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800061b8`
- end: `0x180006580`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180009914`

## callees

- `0x180002810`
- `0x180003384`
- `0x1800061b8`
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

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006230`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006230`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800062e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006425`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006495`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800062e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006425`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006495`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006251`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006251`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800063fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800063fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800063ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800063ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800061f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800061f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800062f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800063c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800063e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006436`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800064ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800062f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800063c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800063e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006436`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800064ab`

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
0x1800061b8  mov     [rsp-8+arg_10], rbx
0x1800061bd  push    rbp
0x1800061be  push    rsi
0x1800061bf  push    rdi
0x1800061c0  push    r14
0x1800061c2  push    r15
0x1800061c4  lea     rbp, [rsp-160h]
0x1800061cc  sub     rsp, 260h
0x1800061d3  mov     rax, cs:__security_cookie
0x1800061da  xor     rax, rsp
0x1800061dd  mov     [rbp+180h+var_30], rax
0x1800061e4  mov     r15, rdx
0x1800061e7  mov     qword ptr [rdx], 0
0x1800061ee  mov     rbx, rcx
0x1800061f1  call    cs:__imp_GetCurrentProcessId
0x1800061f7  mov     r14d, 78h ; 'x'
0x1800061fd  mov     [rsp+280h+var_258], rbx
0x180006202  mov     r9d, eax
0x180006205  mov     [rsp+280h+var_260], r14d; int
0x18000620a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180006211  mov     edx, 104h; unsigned __int64
0x180006216  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000621b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006220  mov     r9d, 1F0001h; dwDesiredAccess
0x180006226  lea     rdx, [rsp+280h+Name]; lpName
0x18000622b  xor     r8d, r8d; dwFlags
0x18000622e  xor     ecx, ecx; lpMutexAttributes
0x180006230  call    cs:__imp_CreateMutexExW
0x180006236  mov     rbx, rax
0x180006239  test    rax, rax
0x18000623c  jnz     short loc_180006248
0x18000623e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006243  jmp     loc_1800064B7
0x180006248  xor     r8d, r8d; bAlertable
0x18000624b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000624e  mov     rcx, rbx; hHandle
0x180006251  call    cs:__imp_WaitForSingleObjectEx
0x180006257  cmp     eax, 102h
0x18000625c  jz      short loc_18000626E
0x18000625e  test    eax, 0FFFFFF7Fh
0x180006263  jnz     loc_1800064EF
0x180006269  mov     rdi, rbx
0x18000626c  jmp     short loc_180006270
0x18000626e  xor     edi, edi
0x180006270  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180006275  mov     [rsp+280h+hObject], 0
0x18000627e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006283  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180006288  mov     esi, eax
0x18000628a  test    eax, eax
0x18000628c  jns     short loc_18000630D
0x18000628e  mov     rcx, [rbp+188h]; this
0x180006295  lea     r8, aWil; "wil"
0x18000629c  mov     r9d, eax; char *
0x18000629f  mov     edx, 66h ; 'f'; void *
0x1800062a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800062a9  mov     rcx, [rbp+188h]; this
0x1800062b0  lea     r8, aWil; "wil"
0x1800062b7  mov     r9d, esi; char *
0x1800062ba  mov     edx, 6Fh ; 'o'; void *
0x1800062bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800062c4  mov     rcx, [rbp+188h]; this
0x1800062cb  lea     r8, aWil; "wil"
0x1800062d2  mov     r9d, esi; char *
0x1800062d5  mov     edx, 12Eh; void *
0x1800062da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800062df  test    rdi, rdi
0x1800062e2  jz      short loc_1800062F5
0x1800062e4  mov     rcx, rdi; hMutex
0x1800062e7  call    cs:__imp_ReleaseMutex
0x1800062ed  test    eax, eax
0x1800062ef  jz      loc_1800064FC
0x1800062f5  mov     rcx, rbx; hObject
0x1800062f8  call    cs:__imp_CloseHandle
0x1800062fe  test    eax, eax
0x180006300  jz      loc_18000650E
0x180006306  mov     eax, esi
0x180006308  jmp     loc_1800064B7
0x18000630d  mov     rax, [rsp+280h+hObject]
0x180006312  lea     rcx, ds:0[rax*4]
0x18000631a  test    rcx, rcx
0x18000631d  jz      short loc_18000632D
0x18000631f  mov     [r15], rcx
0x180006322  mov     eax, [rcx]
0x180006324  inc     eax
0x180006326  mov     [rcx], eax
0x180006328  jmp     loc_18000648D
0x18000632d  mov     rdx, r14; dwBytes
0x180006330  mov     qword ptr [r15], 0
0x180006337  mov     ecx, 8; dwFlags
0x18000633c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006341  mov     rsi, rax
0x180006344  test    rax, rax
0x180006347  jnz     short loc_18000636F
0x180006349  mov     rcx, [rbp+188h]; this
0x180006350  lea     r8, aWil; "wil"
0x180006357  mov     r14d, 8007000Eh
0x18000635d  mov     edx, 14Bh; void *
0x180006362  mov     r9d, r14d; char *
0x180006365  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000636a  jmp     loc_180006402
0x18000636f  xorps   xmm0, xmm0
0x180006372  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180006378  test    sil, 3
0x18000637c  jnz     loc_180006520
0x180006382  mov     r9, rsi
0x180006385  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000638a  shr     r9, 2; unsigned __int64
0x18000638e  lea     rcx, [rsp+280h+hObject]; this
0x180006393  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180006398  mov     r14d, eax
0x18000639b  test    eax, eax
0x18000639d  jns     loc_180006449
0x1800063a3  mov     rcx, [rbp+188h]; this
0x1800063aa  lea     r8, aWil; "wil"
0x1800063b1  mov     r9d, eax; char *
0x1800063b4  mov     edx, 14Eh; void *
0x1800063b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800063be  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800063c3  test    rcx, rcx
0x1800063c6  jz      short loc_1800063D6
0x1800063c8  call    cs:__imp_CloseHandle
0x1800063ce  test    eax, eax
0x1800063d0  jz      loc_180006526
0x1800063d6  mov     rcx, [rsp+280h+hObject]; hObject
0x1800063db  test    rcx, rcx
0x1800063de  jz      short loc_1800063EE
0x1800063e0  call    cs:__imp_CloseHandle
0x1800063e6  test    eax, eax
0x1800063e8  jz      loc_180006538
0x1800063ee  call    cs:__imp_GetProcessHeap
0x1800063f4  mov     r8, rsi; lpMem
0x1800063f7  xor     edx, edx; dwFlags
0x1800063f9  mov     rcx, rax; hHeap
0x1800063fc  call    cs:__imp_HeapFree
0x180006402  mov     rcx, [rbp+188h]; this
0x180006409  lea     r8, aWil; "wil"
0x180006410  mov     r9d, r14d; char *
0x180006413  mov     edx, 137h; void *
0x180006418  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000641d  test    rdi, rdi
0x180006420  jz      short loc_180006433
0x180006422  mov     rcx, rdi; hMutex
0x180006425  call    cs:__imp_ReleaseMutex
0x18000642b  test    eax, eax
0x18000642d  jz      loc_18000654A
0x180006433  mov     rcx, rbx; hObject
0x180006436  call    cs:__imp_CloseHandle
0x18000643c  test    eax, eax
0x18000643e  jz      loc_18000655C
0x180006444  mov     eax, r14d
0x180006447  jmp     short loc_1800064B7
0x180006449  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000644e  xor     edx, edx; Val
0x180006450  mov     dword ptr [rsi], 1
0x180006456  lea     rcx, [rsi+22h]; void *
0x18000645a  mov     [rsi+8], rbx
0x18000645e  movdqu  xmmword ptr [rsi+10h], xmm0
0x180006463  lea     r8d, [rdx+56h]; Size
0x180006467  call    memset_0
0x18000646c  xor     edx, edx; Val
0x18000646e  mov     word ptr [rsi+20h], 58h ; 'X'
0x180006474  lea     rcx, [rsi+28h]; void *
0x180006478  mov     dword ptr [rsi+24h], 1
0x18000647f  lea     r8d, [rdx+50h]; Size
0x180006483  call    memset_0
0x180006488  xor     ebx, ebx
0x18000648a  mov     [r15], rsi
0x18000648d  test    rdi, rdi
0x180006490  jz      short loc_1800064A3
0x180006492  mov     rcx, rdi; hMutex
0x180006495  call    cs:__imp_ReleaseMutex
0x18000649b  test    eax, eax
0x18000649d  jz      loc_18000656E
0x1800064a3  test    rbx, rbx
0x1800064a6  jz      short loc_1800064B5
0x1800064a8  mov     rcx, rbx; hObject
0x1800064ab  call    cs:__imp_CloseHandle
0x1800064b1  test    eax, eax
0x1800064b3  jz      short loc_1800064DD
0x1800064b5  xor     eax, eax
0x1800064b7  mov     rcx, [rbp+180h+var_30]
0x1800064be  xor     rcx, rsp; StackCookie
0x1800064c1  call    __security_check_cookie
0x1800064c6  mov     rbx, [rsp+280h+arg_10]
0x1800064ce  add     rsp, 260h
0x1800064d5  pop     r15
0x1800064d7  pop     r14
0x1800064d9  pop     rdi
0x1800064da  pop     rsi
0x1800064db  pop     rbp
0x1800064dc  retn
0x1800064dd  mov     rcx, [rbp+188h]; this
0x1800064e4  mov     edx, 0A0Bh; void *
0x1800064e9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800064ef  mov     rcx, [rbp+188h]; this
0x1800064f6  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800064fc  mov     rcx, [rbp+188h]; this
0x180006503  mov     edx, 0A15h; void *
0x180006508  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000650e  mov     rcx, [rbp+188h]; this
0x180006515  mov     edx, 0A0Bh; void *
0x18000651a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006520  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180006526  mov     rcx, [rbp+188h]; this
0x18000652d  mov     edx, 0A0Bh; void *
0x180006532  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006538  mov     rcx, [rbp+188h]; this
0x18000653f  mov     edx, 0A0Bh; void *
0x180006544  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000654a  mov     rcx, [rbp+188h]; this
0x180006551  mov     edx, 0A15h; void *
0x180006556  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000655c  mov     rcx, [rbp+188h]; this
0x180006563  mov     edx, 0A0Bh; void *
0x180006568  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000656e  mov     rcx, [rbp+188h]; this
0x180006575  mov     edx, 0A15h; void *
0x18000657a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
