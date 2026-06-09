# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180004f1c`
- end: `0x1800052e4`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180005dc0`

## callees

- `0x180004f1c`
- `0x1800052ec`
- `0x180005530`
- `0x180005ab8`
- `0x180006638`
- `0x1800068f4`
- `0x180006d30`
- `0x180006dbc`
- `0x180007228`
- `0x180007238`
- `0x18001a1d6`
- `0x18001a210`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000504b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005189`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800051f9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000504b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005189`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800051f9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004fb5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004fb5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004f94`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004f94`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005152`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005152`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005160`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005160`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004f55`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004f55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000505c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000512c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005144`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000519a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000520f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000505c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000512c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005144`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000519a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000520f`

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
  __int64 v16; // r8
  const char *v17; // r9
  __int64 v18; // r8
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  bool v23; // r8
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
0x180004f1c  mov     [rsp-8+arg_10], rbx
0x180004f21  push    rbp
0x180004f22  push    rsi
0x180004f23  push    rdi
0x180004f24  push    r14
0x180004f26  push    r15
0x180004f28  lea     rbp, [rsp-160h]
0x180004f30  sub     rsp, 260h
0x180004f37  mov     rax, cs:__security_cookie
0x180004f3e  xor     rax, rsp
0x180004f41  mov     [rbp+180h+var_30], rax
0x180004f48  mov     r15, rdx
0x180004f4b  mov     qword ptr [rdx], 0
0x180004f52  mov     rbx, rcx
0x180004f55  call    cs:__imp_GetCurrentProcessId
0x180004f5b  mov     r14d, 78h ; 'x'
0x180004f61  mov     [rsp+280h+var_258], rbx
0x180004f66  mov     r9d, eax
0x180004f69  mov     [rsp+280h+var_260], r14d; int
0x180004f6e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004f75  mov     edx, 104h; unsigned __int64
0x180004f7a  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180004f7f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004f84  mov     r9d, 1F0001h; dwDesiredAccess
0x180004f8a  lea     rdx, [rsp+280h+Name]; lpName
0x180004f8f  xor     r8d, r8d; dwFlags
0x180004f92  xor     ecx, ecx; lpMutexAttributes
0x180004f94  call    cs:__imp_CreateMutexExW
0x180004f9a  mov     rbx, rax
0x180004f9d  test    rax, rax
0x180004fa0  jnz     short loc_180004FAC
0x180004fa2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004fa7  jmp     loc_18000521B
0x180004fac  xor     r8d, r8d; bAlertable
0x180004faf  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004fb2  mov     rcx, rbx; hHandle
0x180004fb5  call    cs:__imp_WaitForSingleObjectEx
0x180004fbb  cmp     eax, 102h
0x180004fc0  jz      short loc_180004FD2
0x180004fc2  test    eax, 0FFFFFF7Fh
0x180004fc7  jnz     loc_180005253
0x180004fcd  mov     rdi, rbx
0x180004fd0  jmp     short loc_180004FD4
0x180004fd2  xor     edi, edi
0x180004fd4  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180004fd9  mov     [rsp+280h+hObject], 0
0x180004fe2  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180004fe7  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180004fec  mov     esi, eax
0x180004fee  test    eax, eax
0x180004ff0  jns     short loc_180005071
0x180004ff2  mov     rcx, [rbp+188h]; this
0x180004ff9  lea     r8, aWil; "wil"
0x180005000  mov     r9d, eax; char *
0x180005003  mov     edx, 66h ; 'f'; void *
0x180005008  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000500d  mov     rcx, [rbp+188h]; this
0x180005014  lea     r8, aWil; "wil"
0x18000501b  mov     r9d, esi; char *
0x18000501e  mov     edx, 6Fh ; 'o'; void *
0x180005023  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005028  mov     rcx, [rbp+188h]; this
0x18000502f  lea     r8, aWil; "wil"
0x180005036  mov     r9d, esi; char *
0x180005039  mov     edx, 12Eh; void *
0x18000503e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005043  test    rdi, rdi
0x180005046  jz      short loc_180005059
0x180005048  mov     rcx, rdi; hMutex
0x18000504b  call    cs:__imp_ReleaseMutex
0x180005051  test    eax, eax
0x180005053  jz      loc_180005260
0x180005059  mov     rcx, rbx; hObject
0x18000505c  call    cs:__imp_CloseHandle
0x180005062  test    eax, eax
0x180005064  jz      loc_180005272
0x18000506a  mov     eax, esi
0x18000506c  jmp     loc_18000521B
0x180005071  mov     rax, [rsp+280h+hObject]
0x180005076  lea     rcx, ds:0[rax*4]
0x18000507e  test    rcx, rcx
0x180005081  jz      short loc_180005091
0x180005083  mov     [r15], rcx
0x180005086  mov     eax, [rcx]
0x180005088  inc     eax
0x18000508a  mov     [rcx], eax
0x18000508c  jmp     loc_1800051F1
0x180005091  mov     rdx, r14; dwBytes
0x180005094  mov     qword ptr [r15], 0
0x18000509b  mov     ecx, 8; dwFlags
0x1800050a0  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800050a5  mov     rsi, rax
0x1800050a8  test    rax, rax
0x1800050ab  jnz     short loc_1800050D3
0x1800050ad  mov     rcx, [rbp+188h]; this
0x1800050b4  lea     r8, aWil; "wil"
0x1800050bb  mov     r14d, 8007000Eh
0x1800050c1  mov     edx, 14Bh; void *
0x1800050c6  mov     r9d, r14d; char *
0x1800050c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800050ce  jmp     loc_180005166
0x1800050d3  xorps   xmm0, xmm0
0x1800050d6  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800050dc  test    sil, 3
0x1800050e0  jnz     loc_180005284
0x1800050e6  mov     r9, rsi
0x1800050e9  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800050ee  shr     r9, 2; unsigned __int64
0x1800050f2  lea     rcx, [rsp+280h+hObject]; this
0x1800050f7  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800050fc  mov     r14d, eax
0x1800050ff  test    eax, eax
0x180005101  jns     loc_1800051AD
0x180005107  mov     rcx, [rbp+188h]; this
0x18000510e  lea     r8, aWil; "wil"
0x180005115  mov     r9d, eax; char *
0x180005118  mov     edx, 14Eh; void *
0x18000511d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005122  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180005127  test    rcx, rcx
0x18000512a  jz      short loc_18000513A
0x18000512c  call    cs:__imp_CloseHandle
0x180005132  test    eax, eax
0x180005134  jz      loc_18000528A
0x18000513a  mov     rcx, [rsp+280h+hObject]; hObject
0x18000513f  test    rcx, rcx
0x180005142  jz      short loc_180005152
0x180005144  call    cs:__imp_CloseHandle
0x18000514a  test    eax, eax
0x18000514c  jz      loc_18000529C
0x180005152  call    cs:__imp_GetProcessHeap
0x180005158  mov     r8, rsi; lpMem
0x18000515b  xor     edx, edx; dwFlags
0x18000515d  mov     rcx, rax; hHeap
0x180005160  call    cs:__imp_HeapFree
0x180005166  mov     rcx, [rbp+188h]; this
0x18000516d  lea     r8, aWil; "wil"
0x180005174  mov     r9d, r14d; char *
0x180005177  mov     edx, 137h; void *
0x18000517c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005181  test    rdi, rdi
0x180005184  jz      short loc_180005197
0x180005186  mov     rcx, rdi; hMutex
0x180005189  call    cs:__imp_ReleaseMutex
0x18000518f  test    eax, eax
0x180005191  jz      loc_1800052AE
0x180005197  mov     rcx, rbx; hObject
0x18000519a  call    cs:__imp_CloseHandle
0x1800051a0  test    eax, eax
0x1800051a2  jz      loc_1800052C0
0x1800051a8  mov     eax, r14d
0x1800051ab  jmp     short loc_18000521B
0x1800051ad  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800051b2  xor     edx, edx; Val
0x1800051b4  mov     dword ptr [rsi], 1
0x1800051ba  lea     rcx, [rsi+22h]; void *
0x1800051be  mov     [rsi+8], rbx
0x1800051c2  movdqu  xmmword ptr [rsi+10h], xmm0
0x1800051c7  lea     r8d, [rdx+56h]; Size
0x1800051cb  call    memset_0
0x1800051d0  xor     edx, edx; Val
0x1800051d2  mov     word ptr [rsi+20h], 58h ; 'X'
0x1800051d8  lea     rcx, [rsi+28h]; void *
0x1800051dc  mov     dword ptr [rsi+24h], 1
0x1800051e3  lea     r8d, [rdx+50h]; Size
0x1800051e7  call    memset_0
0x1800051ec  xor     ebx, ebx
0x1800051ee  mov     [r15], rsi
0x1800051f1  test    rdi, rdi
0x1800051f4  jz      short loc_180005207
0x1800051f6  mov     rcx, rdi; hMutex
0x1800051f9  call    cs:__imp_ReleaseMutex
0x1800051ff  test    eax, eax
0x180005201  jz      loc_1800052D2
0x180005207  test    rbx, rbx
0x18000520a  jz      short loc_180005219
0x18000520c  mov     rcx, rbx; hObject
0x18000520f  call    cs:__imp_CloseHandle
0x180005215  test    eax, eax
0x180005217  jz      short loc_180005241
0x180005219  xor     eax, eax
0x18000521b  mov     rcx, [rbp+180h+var_30]
0x180005222  xor     rcx, rsp; StackCookie
0x180005225  call    __security_check_cookie
0x18000522a  mov     rbx, [rsp+280h+arg_10]
0x180005232  add     rsp, 260h
0x180005239  pop     r15
0x18000523b  pop     r14
0x18000523d  pop     rdi
0x18000523e  pop     rsi
0x18000523f  pop     rbp
0x180005240  retn
0x180005241  mov     rcx, [rbp+188h]; this
0x180005248  mov     edx, 0A0Bh; void *
0x18000524d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005253  mov     rcx, [rbp+188h]; this
0x18000525a  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180005260  mov     rcx, [rbp+188h]; this
0x180005267  mov     edx, 0A15h; void *
0x18000526c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005272  mov     rcx, [rbp+188h]; this
0x180005279  mov     edx, 0A0Bh; void *
0x18000527e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005284  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000528a  mov     rcx, [rbp+188h]; this
0x180005291  mov     edx, 0A0Bh; void *
0x180005296  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000529c  mov     rcx, [rbp+188h]; this
0x1800052a3  mov     edx, 0A0Bh; void *
0x1800052a8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800052ae  mov     rcx, [rbp+188h]; this
0x1800052b5  mov     edx, 0A15h; void *
0x1800052ba  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800052c0  mov     rcx, [rbp+188h]; this
0x1800052c7  mov     edx, 0A0Bh; void *
0x1800052cc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800052d2  mov     rcx, [rbp+188h]; this
0x1800052d9  mov     edx, 0A15h; void *
0x1800052de  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
