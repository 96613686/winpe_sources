# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1400026bc`
- end: `0x140002a84`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x14000363c`

## callees

- `0x140001a63`
- `0x1400026bc`
- `0x140002a8c`
- `0x140002d84`
- `0x1400033d8`
- `0x140003eb8`
- `0x140004100`
- `0x1400044e0`
- `0x14000456c`
- `0x14000493c`
- `0x14000494c`
- `0x140014910`

## import_xrefs

- `KERNEL32!WaitForSingleObjectEx` at `0x140002755`
- `KERNEL32!WaitForSingleObjectEx` at `0x140002755`
- `KERNEL32!CloseHandle` at `0x1400027fc`
- `KERNEL32!CloseHandle` at `0x1400028cc`
- `KERNEL32!CloseHandle` at `0x1400028e4`
- `KERNEL32!CloseHandle` at `0x14000293a`
- `KERNEL32!CloseHandle` at `0x1400029af`
- `KERNEL32!CloseHandle` at `0x1400027fc`
- `KERNEL32!CloseHandle` at `0x1400028cc`
- `KERNEL32!CloseHandle` at `0x1400028e4`
- `KERNEL32!CloseHandle` at `0x14000293a`
- `KERNEL32!CloseHandle` at `0x1400029af`
- `KERNEL32!CreateMutexExW` at `0x140002734`
- `KERNEL32!CreateMutexExW` at `0x140002734`
- `KERNEL32!GetCurrentProcessId` at `0x1400026f5`
- `KERNEL32!GetCurrentProcessId` at `0x1400026f5`
- `KERNEL32!HeapFree` at `0x140002900`
- `KERNEL32!HeapFree` at `0x140002900`
- `KERNEL32!ReleaseMutex` at `0x1400027eb`
- `KERNEL32!ReleaseMutex` at `0x140002929`
- `KERNEL32!ReleaseMutex` at `0x140002999`
- `KERNEL32!ReleaseMutex` at `0x1400027eb`
- `KERNEL32!ReleaseMutex` at `0x140002929`
- `KERNEL32!ReleaseMutex` at `0x140002999`
- `KERNEL32!GetProcessHeap` at `0x1400028f2`
- `KERNEL32!GetProcessHeap` at `0x1400028f2`

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
0x1400026bc  mov     [rsp-8+arg_10], rbx
0x1400026c1  push    rbp
0x1400026c2  push    rsi
0x1400026c3  push    rdi
0x1400026c4  push    r14
0x1400026c6  push    r15
0x1400026c8  lea     rbp, [rsp-160h]
0x1400026d0  sub     rsp, 260h
0x1400026d7  mov     rax, cs:__security_cookie
0x1400026de  xor     rax, rsp
0x1400026e1  mov     [rbp+180h+var_30], rax
0x1400026e8  mov     r15, rdx
0x1400026eb  mov     qword ptr [rdx], 0
0x1400026f2  mov     rbx, rcx
0x1400026f5  call    cs:__imp_GetCurrentProcessId
0x1400026fb  mov     r14d, 78h ; 'x'
0x140002701  mov     [rsp+280h+var_258], rbx
0x140002706  mov     r9d, eax
0x140002709  mov     [rsp+280h+var_260], r14d; int
0x14000270e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140002715  mov     edx, 104h; unsigned __int64
0x14000271a  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000271f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140002724  mov     r9d, 1F0001h; dwDesiredAccess
0x14000272a  lea     rdx, [rsp+280h+Name]; lpName
0x14000272f  xor     r8d, r8d; dwFlags
0x140002732  xor     ecx, ecx; lpMutexAttributes
0x140002734  call    cs:__imp_CreateMutexExW
0x14000273a  mov     rbx, rax
0x14000273d  test    rax, rax
0x140002740  jnz     short loc_14000274C
0x140002742  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140002747  jmp     loc_1400029BB
0x14000274c  xor     r8d, r8d; bAlertable
0x14000274f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140002752  mov     rcx, rbx; hHandle
0x140002755  call    cs:__imp_WaitForSingleObjectEx
0x14000275b  cmp     eax, 102h
0x140002760  jz      short loc_140002772
0x140002762  test    eax, 0FFFFFF7Fh
0x140002767  jnz     loc_1400029F3
0x14000276d  mov     rdi, rbx
0x140002770  jmp     short loc_140002774
0x140002772  xor     edi, edi
0x140002774  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140002779  mov     [rsp+280h+hObject], 0
0x140002782  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140002787  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x14000278c  mov     esi, eax
0x14000278e  test    eax, eax
0x140002790  jns     short loc_140002811
0x140002792  mov     rcx, [rbp+188h]; this
0x140002799  lea     r8, aWil; "wil"
0x1400027a0  mov     r9d, eax; char *
0x1400027a3  mov     edx, 66h ; 'f'; void *
0x1400027a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400027ad  mov     rcx, [rbp+188h]; this
0x1400027b4  lea     r8, aWil; "wil"
0x1400027bb  mov     r9d, esi; char *
0x1400027be  mov     edx, 6Fh ; 'o'; void *
0x1400027c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400027c8  mov     rcx, [rbp+188h]; this
0x1400027cf  lea     r8, aWil; "wil"
0x1400027d6  mov     r9d, esi; char *
0x1400027d9  mov     edx, 12Eh; void *
0x1400027de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400027e3  test    rdi, rdi
0x1400027e6  jz      short loc_1400027F9
0x1400027e8  mov     rcx, rdi; hMutex
0x1400027eb  call    cs:__imp_ReleaseMutex
0x1400027f1  test    eax, eax
0x1400027f3  jz      loc_140002A00
0x1400027f9  mov     rcx, rbx; hObject
0x1400027fc  call    cs:__imp_CloseHandle
0x140002802  test    eax, eax
0x140002804  jz      loc_140002A12
0x14000280a  mov     eax, esi
0x14000280c  jmp     loc_1400029BB
0x140002811  mov     rax, [rsp+280h+hObject]
0x140002816  lea     rcx, ds:0[rax*4]
0x14000281e  test    rcx, rcx
0x140002821  jz      short loc_140002831
0x140002823  mov     [r15], rcx
0x140002826  mov     eax, [rcx]
0x140002828  inc     eax
0x14000282a  mov     [rcx], eax
0x14000282c  jmp     loc_140002991
0x140002831  mov     rdx, r14; dwBytes
0x140002834  mov     qword ptr [r15], 0
0x14000283b  mov     ecx, 8; dwFlags
0x140002840  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140002845  mov     rsi, rax
0x140002848  test    rax, rax
0x14000284b  jnz     short loc_140002873
0x14000284d  mov     rcx, [rbp+188h]; this
0x140002854  lea     r8, aWil; "wil"
0x14000285b  mov     r14d, 8007000Eh
0x140002861  mov     edx, 14Bh; void *
0x140002866  mov     r9d, r14d; char *
0x140002869  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000286e  jmp     loc_140002906
0x140002873  xorps   xmm0, xmm0
0x140002876  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x14000287c  test    sil, 3
0x140002880  jnz     loc_140002A24
0x140002886  mov     r9, rsi
0x140002889  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x14000288e  shr     r9, 2; unsigned __int64
0x140002892  lea     rcx, [rsp+280h+hObject]; this
0x140002897  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x14000289c  mov     r14d, eax
0x14000289f  test    eax, eax
0x1400028a1  jns     loc_14000294D
0x1400028a7  mov     rcx, [rbp+188h]; this
0x1400028ae  lea     r8, aWil; "wil"
0x1400028b5  mov     r9d, eax; char *
0x1400028b8  mov     edx, 14Eh; void *
0x1400028bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400028c2  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1400028c7  test    rcx, rcx
0x1400028ca  jz      short loc_1400028DA
0x1400028cc  call    cs:__imp_CloseHandle
0x1400028d2  test    eax, eax
0x1400028d4  jz      loc_140002A2A
0x1400028da  mov     rcx, [rsp+280h+hObject]; hObject
0x1400028df  test    rcx, rcx
0x1400028e2  jz      short loc_1400028F2
0x1400028e4  call    cs:__imp_CloseHandle
0x1400028ea  test    eax, eax
0x1400028ec  jz      loc_140002A3C
0x1400028f2  call    cs:__imp_GetProcessHeap
0x1400028f8  mov     r8, rsi; lpMem
0x1400028fb  xor     edx, edx; dwFlags
0x1400028fd  mov     rcx, rax; hHeap
0x140002900  call    cs:__imp_HeapFree
0x140002906  mov     rcx, [rbp+188h]; this
0x14000290d  lea     r8, aWil; "wil"
0x140002914  mov     r9d, r14d; char *
0x140002917  mov     edx, 137h; void *
0x14000291c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002921  test    rdi, rdi
0x140002924  jz      short loc_140002937
0x140002926  mov     rcx, rdi; hMutex
0x140002929  call    cs:__imp_ReleaseMutex
0x14000292f  test    eax, eax
0x140002931  jz      loc_140002A4E
0x140002937  mov     rcx, rbx; hObject
0x14000293a  call    cs:__imp_CloseHandle
0x140002940  test    eax, eax
0x140002942  jz      loc_140002A60
0x140002948  mov     eax, r14d
0x14000294b  jmp     short loc_1400029BB
0x14000294d  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x140002952  xor     edx, edx; Val
0x140002954  mov     dword ptr [rsi], 1
0x14000295a  lea     rcx, [rsi+22h]; void *
0x14000295e  mov     [rsi+8], rbx
0x140002962  movdqu  xmmword ptr [rsi+10h], xmm0
0x140002967  lea     r8d, [rdx+56h]; Size
0x14000296b  call    memset_0
0x140002970  xor     edx, edx; Val
0x140002972  mov     word ptr [rsi+20h], 58h ; 'X'
0x140002978  lea     rcx, [rsi+28h]; void *
0x14000297c  mov     dword ptr [rsi+24h], 1
0x140002983  lea     r8d, [rdx+50h]; Size
0x140002987  call    memset_0
0x14000298c  xor     ebx, ebx
0x14000298e  mov     [r15], rsi
0x140002991  test    rdi, rdi
0x140002994  jz      short loc_1400029A7
0x140002996  mov     rcx, rdi; hMutex
0x140002999  call    cs:__imp_ReleaseMutex
0x14000299f  test    eax, eax
0x1400029a1  jz      loc_140002A72
0x1400029a7  test    rbx, rbx
0x1400029aa  jz      short loc_1400029B9
0x1400029ac  mov     rcx, rbx; hObject
0x1400029af  call    cs:__imp_CloseHandle
0x1400029b5  test    eax, eax
0x1400029b7  jz      short loc_1400029E1
0x1400029b9  xor     eax, eax
0x1400029bb  mov     rcx, [rbp+180h+var_30]
0x1400029c2  xor     rcx, rsp; StackCookie
0x1400029c5  call    __security_check_cookie
0x1400029ca  mov     rbx, [rsp+280h+arg_10]
0x1400029d2  add     rsp, 260h
0x1400029d9  pop     r15
0x1400029db  pop     r14
0x1400029dd  pop     rdi
0x1400029de  pop     rsi
0x1400029df  pop     rbp
0x1400029e0  retn
0x1400029e1  mov     rcx, [rbp+188h]; this
0x1400029e8  mov     edx, 0A0Bh; void *
0x1400029ed  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400029f3  mov     rcx, [rbp+188h]; this
0x1400029fa  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140002a00  mov     rcx, [rbp+188h]; this
0x140002a07  mov     edx, 0A15h; void *
0x140002a0c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140002a12  mov     rcx, [rbp+188h]; this
0x140002a19  mov     edx, 0A0Bh; void *
0x140002a1e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140002a24  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140002a2a  mov     rcx, [rbp+188h]; this
0x140002a31  mov     edx, 0A0Bh; void *
0x140002a36  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140002a3c  mov     rcx, [rbp+188h]; this
0x140002a43  mov     edx, 0A0Bh; void *
0x140002a48  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140002a4e  mov     rcx, [rbp+188h]; this
0x140002a55  mov     edx, 0A15h; void *
0x140002a5a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140002a60  mov     rcx, [rbp+188h]; this
0x140002a67  mov     edx, 0A0Bh; void *
0x140002a6c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140002a72  mov     rcx, [rbp+188h]; this
0x140002a79  mov     edx, 0A15h; void *
0x140002a7e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
