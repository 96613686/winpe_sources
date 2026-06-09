# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000671c`
- end: `0x180006af0`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `980`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1800080ac`

## callees

- `0x180004120`
- `0x180004c80`
- `0x18000671c`
- `0x180006f54`
- `0x1800074e0`
- `0x180007e18`
- `0x180008aec`
- `0x180009fe4`
- `0x18000aae4`
- `0x18000aeac`
- `0x18000b75c`
- `0x18000b76c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000684b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006989`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800069f9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000684b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006989`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800069f9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006794`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006794`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800067b5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800067b5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006960`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006960`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006952`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006952`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006755`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006755`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000685c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000692c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006944`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000699a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006a0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000685c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000692c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006944`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000699a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006a0f`

## string_xrefs

- `0x180006a5a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  char *v10; // r9
  void *v11; // rdi
  int ValueInternal; // eax
  unsigned __int64 v13; // r8
  unsigned int v14; // esi
  unsigned int v15; // r8d
  const char *v16; // r9
  unsigned int v17; // r8d
  const char *v18; // r9
  _DWORD *v19; // rcx
  unsigned __int64 v20; // rax
  wil::details::in1diag3 *v21; // rcx
  bool v22; // r8
  _QWORD *v23; // rsi
  unsigned int v24; // r14d
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
    v11 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v10);
    v11 = v6;
  }
  hObject[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    v9,
                    (unsigned __int64 *)hObject,
                    (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v40);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v41);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v15, v16);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v17, v18);
    return v14;
  }
  v19 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v19;
    ++*v19;
    goto LABEL_28;
  }
  *a2 = 0;
  v20 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v13);
  v23 = (_QWORD *)v20;
  if ( v20 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v20 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v21);
    v25 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v22,
            v20 >> 2);
    v24 = v25;
    if ( v25 >= 0 )
    {
      v35 = *(_OWORD *)hObject;
      *(_DWORD *)v23 = 1;
      v23[1] = v6;
      *((_OWORD *)v23 + 1) = v35;
      memset_0((char *)v23 + 34, 0, 0x56u);
      *((_WORD *)v23 + 16) = 88;
      *((_DWORD *)v23 + 9) = 1;
      memset_0(v23 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v23;
LABEL_28:
      if ( v11 && !ReleaseMutex(v11) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v25, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v23);
  }
  else
  {
    v24 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v24, v42);
  if ( v11 && !ReleaseMutex(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v31, v32);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
  return v24;
}

```

## disassembly

```asm
0x18000671c  mov     [rsp-8+arg_10], rbx
0x180006721  push    rbp
0x180006722  push    rsi
0x180006723  push    rdi
0x180006724  push    r14
0x180006726  push    r15
0x180006728  lea     rbp, [rsp-160h]
0x180006730  sub     rsp, 260h
0x180006737  mov     rax, cs:__security_cookie
0x18000673e  xor     rax, rsp
0x180006741  mov     [rbp+180h+var_30], rax
0x180006748  mov     r15, rdx
0x18000674b  mov     qword ptr [rdx], 0
0x180006752  mov     rbx, rcx
0x180006755  call    cs:__imp_GetCurrentProcessId
0x18000675b  mov     r14d, 78h ; 'x'
0x180006761  mov     [rsp+280h+var_258], rbx
0x180006766  mov     r9d, eax
0x180006769  mov     [rsp+280h+var_260], r14d; int
0x18000676e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180006775  mov     edx, 104h; unsigned __int64
0x18000677a  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000677f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006784  mov     r9d, 1F0001h; dwDesiredAccess
0x18000678a  lea     rdx, [rsp+280h+Name]; lpName
0x18000678f  xor     r8d, r8d; dwFlags
0x180006792  xor     ecx, ecx; lpMutexAttributes
0x180006794  call    cs:__imp_CreateMutexExW
0x18000679a  mov     rbx, rax
0x18000679d  test    rax, rax
0x1800067a0  jnz     short loc_1800067AC
0x1800067a2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800067a7  jmp     loc_180006A1B
0x1800067ac  xor     r8d, r8d; bAlertable
0x1800067af  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800067b2  mov     rcx, rbx; hHandle
0x1800067b5  call    cs:__imp_WaitForSingleObjectEx
0x1800067bb  cmp     eax, 102h
0x1800067c0  jz      short loc_1800067D2
0x1800067c2  test    eax, 0FFFFFF7Fh
0x1800067c7  jnz     loc_180006A53
0x1800067cd  mov     rdi, rbx
0x1800067d0  jmp     short loc_1800067D4
0x1800067d2  xor     edi, edi
0x1800067d4  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800067d9  mov     [rsp+280h+hObject], 0
0x1800067e2  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800067e7  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800067ec  mov     esi, eax
0x1800067ee  test    eax, eax
0x1800067f0  jns     short loc_180006871
0x1800067f2  mov     rcx, [rbp+188h]; this
0x1800067f9  lea     r8, aWil; "wil"
0x180006800  mov     r9d, eax; char *
0x180006803  mov     edx, 66h ; 'f'; void *
0x180006808  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000680d  mov     rcx, [rbp+188h]; this
0x180006814  lea     r8, aWil; "wil"
0x18000681b  mov     r9d, esi; char *
0x18000681e  mov     edx, 6Fh ; 'o'; void *
0x180006823  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006828  mov     rcx, [rbp+188h]; this
0x18000682f  lea     r8, aWil; "wil"
0x180006836  mov     r9d, esi; char *
0x180006839  mov     edx, 12Eh; void *
0x18000683e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006843  test    rdi, rdi
0x180006846  jz      short loc_180006859
0x180006848  mov     rcx, rdi; hMutex
0x18000684b  call    cs:__imp_ReleaseMutex
0x180006851  test    eax, eax
0x180006853  jz      loc_180006A6C
0x180006859  mov     rcx, rbx; hObject
0x18000685c  call    cs:__imp_CloseHandle
0x180006862  test    eax, eax
0x180006864  jz      loc_180006A7E
0x18000686a  mov     eax, esi
0x18000686c  jmp     loc_180006A1B
0x180006871  mov     rax, [rsp+280h+hObject]
0x180006876  lea     rcx, ds:0[rax*4]
0x18000687e  test    rcx, rcx
0x180006881  jz      short loc_180006891
0x180006883  mov     [r15], rcx
0x180006886  mov     eax, [rcx]
0x180006888  inc     eax
0x18000688a  mov     [rcx], eax
0x18000688c  jmp     loc_1800069F1
0x180006891  mov     rdx, r14; dwBytes
0x180006894  mov     qword ptr [r15], 0
0x18000689b  mov     ecx, 8; dwFlags
0x1800068a0  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800068a5  mov     rsi, rax
0x1800068a8  test    rax, rax
0x1800068ab  jnz     short loc_1800068D3
0x1800068ad  mov     rcx, [rbp+188h]; this
0x1800068b4  lea     r8, aWil; "wil"
0x1800068bb  mov     r14d, 8007000Eh
0x1800068c1  mov     edx, 14Bh; void *
0x1800068c6  mov     r9d, r14d; char *
0x1800068c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800068ce  jmp     loc_180006966
0x1800068d3  xorps   xmm0, xmm0
0x1800068d6  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800068dc  test    sil, 3
0x1800068e0  jnz     loc_180006A90
0x1800068e6  mov     r9, rsi
0x1800068e9  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800068ee  shr     r9, 2; unsigned __int64
0x1800068f2  lea     rcx, [rsp+280h+hObject]; this
0x1800068f7  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800068fc  mov     r14d, eax
0x1800068ff  test    eax, eax
0x180006901  jns     loc_1800069AD
0x180006907  mov     rcx, [rbp+188h]; this
0x18000690e  lea     r8, aWil; "wil"
0x180006915  mov     r9d, eax; char *
0x180006918  mov     edx, 14Eh; void *
0x18000691d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006922  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180006927  test    rcx, rcx
0x18000692a  jz      short loc_18000693A
0x18000692c  call    cs:__imp_CloseHandle
0x180006932  test    eax, eax
0x180006934  jz      loc_180006A96
0x18000693a  mov     rcx, [rsp+280h+hObject]; hObject
0x18000693f  test    rcx, rcx
0x180006942  jz      short loc_180006952
0x180006944  call    cs:__imp_CloseHandle
0x18000694a  test    eax, eax
0x18000694c  jz      loc_180006AA8
0x180006952  call    cs:__imp_GetProcessHeap
0x180006958  mov     r8, rsi; lpMem
0x18000695b  xor     edx, edx; dwFlags
0x18000695d  mov     rcx, rax; hHeap
0x180006960  call    cs:__imp_HeapFree
0x180006966  mov     rcx, [rbp+188h]; this
0x18000696d  lea     r8, aWil; "wil"
0x180006974  mov     r9d, r14d; char *
0x180006977  mov     edx, 137h; void *
0x18000697c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006981  test    rdi, rdi
0x180006984  jz      short loc_180006997
0x180006986  mov     rcx, rdi; hMutex
0x180006989  call    cs:__imp_ReleaseMutex
0x18000698f  test    eax, eax
0x180006991  jz      loc_180006ABA
0x180006997  mov     rcx, rbx; hObject
0x18000699a  call    cs:__imp_CloseHandle
0x1800069a0  test    eax, eax
0x1800069a2  jz      loc_180006ACC
0x1800069a8  mov     eax, r14d
0x1800069ab  jmp     short loc_180006A1B
0x1800069ad  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800069b2  xor     edx, edx; Val
0x1800069b4  mov     dword ptr [rsi], 1
0x1800069ba  lea     rcx, [rsi+22h]; void *
0x1800069be  mov     [rsi+8], rbx
0x1800069c2  movdqu  xmmword ptr [rsi+10h], xmm0
0x1800069c7  lea     r8d, [rdx+56h]; Size
0x1800069cb  call    memset_0
0x1800069d0  xor     edx, edx; Val
0x1800069d2  mov     word ptr [rsi+20h], 58h ; 'X'
0x1800069d8  lea     rcx, [rsi+28h]; void *
0x1800069dc  mov     dword ptr [rsi+24h], 1
0x1800069e3  lea     r8d, [rdx+50h]; Size
0x1800069e7  call    memset_0
0x1800069ec  xor     ebx, ebx
0x1800069ee  mov     [r15], rsi
0x1800069f1  test    rdi, rdi
0x1800069f4  jz      short loc_180006A07
0x1800069f6  mov     rcx, rdi; hMutex
0x1800069f9  call    cs:__imp_ReleaseMutex
0x1800069ff  test    eax, eax
0x180006a01  jz      loc_180006ADE
0x180006a07  test    rbx, rbx
0x180006a0a  jz      short loc_180006A19
0x180006a0c  mov     rcx, rbx; hObject
0x180006a0f  call    cs:__imp_CloseHandle
0x180006a15  test    eax, eax
0x180006a17  jz      short loc_180006A41
0x180006a19  xor     eax, eax
0x180006a1b  mov     rcx, [rbp+180h+var_30]
0x180006a22  xor     rcx, rsp; StackCookie
0x180006a25  call    __security_check_cookie
0x180006a2a  mov     rbx, [rsp+280h+arg_10]
0x180006a32  add     rsp, 260h
0x180006a39  pop     r15
0x180006a3b  pop     r14
0x180006a3d  pop     rdi
0x180006a3e  pop     rsi
0x180006a3f  pop     rbp
0x180006a40  retn
0x180006a41  mov     rcx, [rbp+188h]; this
0x180006a48  mov     edx, 0A0Bh; void *
0x180006a4d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006a53  mov     rcx, [rbp+188h]; this
0x180006a5a  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006a61  mov     edx, 0E01h; void *
0x180006a66  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180006a6c  mov     rcx, [rbp+188h]; this
0x180006a73  mov     edx, 0A15h; void *
0x180006a78  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006a7e  mov     rcx, [rbp+188h]; this
0x180006a85  mov     edx, 0A0Bh; void *
0x180006a8a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006a90  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180006a96  mov     rcx, [rbp+188h]; this
0x180006a9d  mov     edx, 0A0Bh; void *
0x180006aa2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006aa8  mov     rcx, [rbp+188h]; this
0x180006aaf  mov     edx, 0A0Bh; void *
0x180006ab4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006aba  mov     rcx, [rbp+188h]; this
0x180006ac1  mov     edx, 0A15h; void *
0x180006ac6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006acc  mov     rcx, [rbp+188h]; this
0x180006ad3  mov     edx, 0A0Bh; void *
0x180006ad8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006ade  mov     rcx, [rbp+188h]; this
0x180006ae5  mov     edx, 0A15h; void *
0x180006aea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
