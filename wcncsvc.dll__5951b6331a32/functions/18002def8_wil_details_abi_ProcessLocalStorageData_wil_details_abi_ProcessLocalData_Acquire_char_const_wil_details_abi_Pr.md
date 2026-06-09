# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18002def8`
- end: `0x18002e296`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180030410`

## callees

- `0x18002def8`
- `0x18002e66c`
- `0x18002eb90`
- `0x1800301a8`
- `0x180030e88`
- `0x180032864`
- `0x180033200`
- `0x18003360c`
- `0x18003426c`
- `0x18003427c`
- `0x180056df2`
- `0x180056e30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002df70`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002df70`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002df91`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002df91`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002e012`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002e13b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002e1ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002e012`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002e13b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002e1ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e023`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e0e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e0fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e14c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e1c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e023`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e0e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e0fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e14c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e1c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002df31`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002df31`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e10b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e10b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002e119`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002e119`

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
  unsigned int v17; // r8d
  __int64 v18; // r8
  const char *v19; // r9
  __int64 v20; // r8
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  unsigned int v25; // r8d
  _QWORD *v26; // rsi
  unsigned int v27; // r14d
  unsigned int v28; // r8d
  int v29; // eax
  unsigned int v30; // r8d
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
  const char *v34; // r9
  HANDLE ProcessHeap; // rax
  __int64 v36; // r8
  const char *v37; // r9
  __int64 v38; // r8
  const char *v39; // r9
  __int128 v40; // xmm0
  __int64 v41; // r8
  const char *v42; // r9
  __int64 v43; // r8
  const char *v44; // r9
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
  int v47; // [rsp+20h] [rbp-E0h]
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v45);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v46);
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
  v23 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v26 = (_QWORD *)v23;
  if ( v23 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v23 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    v29 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v25,
            v23 >> 2);
    v27 = v29;
    if ( v29 >= 0 )
    {
      v40 = *(_OWORD *)hObject;
      *(_DWORD *)v26 = 1;
      v26[1] = v6;
      *((_OWORD *)v26 + 1) = v40;
      memset_0((char *)v26 + 34, 0, 0x56u);
      *((_WORD *)v26 + 16) = 88;
      *((_DWORD *)v26 + 9) = 1;
      memset_0(v26 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v26;
LABEL_28:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v41, v42);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v43, v44);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v30, (const char *)(unsigned int)v29, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v26);
  }
  else
  {
    v27 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v25, (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v28, (const char *)v27, v47);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
  return v27;
}

```

## disassembly

```asm
0x18002def8  mov     [rsp-8+arg_10], rbx
0x18002defd  push    rbp
0x18002defe  push    rsi
0x18002deff  push    rdi
0x18002df00  push    r14
0x18002df02  push    r15
0x18002df04  lea     rbp, [rsp-160h]
0x18002df0c  sub     rsp, 260h
0x18002df13  mov     rax, cs:__security_cookie
0x18002df1a  xor     rax, rsp
0x18002df1d  mov     [rbp+180h+var_30], rax
0x18002df24  mov     r15, rdx
0x18002df27  mov     qword ptr [rdx], 0
0x18002df2e  mov     rbx, rcx
0x18002df31  call    cs:__imp_GetCurrentProcessId
0x18002df37  mov     r14d, 78h ; 'x'
0x18002df3d  mov     [rsp+280h+var_258], rbx
0x18002df42  mov     r9d, eax
0x18002df45  mov     [rsp+280h+var_260], r14d; int
0x18002df4a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18002df51  mov     edx, 104h; unsigned __int64
0x18002df56  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18002df5b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002df60  mov     r9d, 1F0001h; dwDesiredAccess
0x18002df66  lea     rdx, [rsp+280h+Name]; lpName
0x18002df6b  xor     r8d, r8d; dwFlags
0x18002df6e  xor     ecx, ecx; lpMutexAttributes
0x18002df70  call    cs:__imp_CreateMutexExW
0x18002df76  mov     rbx, rax
0x18002df79  test    rax, rax
0x18002df7c  jnz     short loc_18002DF88
0x18002df7e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002df83  jmp     loc_18002E1CD
0x18002df88  xor     r8d, r8d; bAlertable
0x18002df8b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002df8e  mov     rcx, rbx; hHandle
0x18002df91  call    cs:__imp_WaitForSingleObjectEx
0x18002df97  cmp     eax, 102h
0x18002df9c  jz      short loc_18002DFAE
0x18002df9e  test    eax, 0FFFFFF7Fh
0x18002dfa3  jnz     loc_18002E205
0x18002dfa9  mov     rdi, rbx
0x18002dfac  jmp     short loc_18002DFB0
0x18002dfae  xor     edi, edi
0x18002dfb0  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x18002dfb5  mov     [rsp+280h+hObject], 0
0x18002dfbe  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18002dfc3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18002dfc8  mov     esi, eax
0x18002dfca  test    eax, eax
0x18002dfcc  jns     short loc_18002E038
0x18002dfce  mov     rcx, [rbp+188h]; this
0x18002dfd5  mov     r9d, eax; char *
0x18002dfd8  mov     edx, 66h ; 'f'; void *
0x18002dfdd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002dfe2  mov     rcx, [rbp+188h]; this
0x18002dfe9  mov     r9d, esi; char *
0x18002dfec  mov     edx, 6Fh ; 'o'; void *
0x18002dff1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002dff6  mov     rcx, [rbp+188h]; this
0x18002dffd  mov     r9d, esi; char *
0x18002e000  mov     edx, 12Eh; void *
0x18002e005  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e00a  test    rdi, rdi
0x18002e00d  jz      short loc_18002E020
0x18002e00f  mov     rcx, rdi; hMutex
0x18002e012  call    cs:__imp_ReleaseMutex
0x18002e018  test    eax, eax
0x18002e01a  jz      loc_18002E212
0x18002e020  mov     rcx, rbx; hObject
0x18002e023  call    cs:__imp_CloseHandle
0x18002e029  test    eax, eax
0x18002e02b  jz      loc_18002E224
0x18002e031  mov     eax, esi
0x18002e033  jmp     loc_18002E1CD
0x18002e038  mov     rax, [rsp+280h+hObject]
0x18002e03d  lea     rcx, ds:0[rax*4]
0x18002e045  test    rcx, rcx
0x18002e048  jz      short loc_18002E058
0x18002e04a  mov     [r15], rcx
0x18002e04d  mov     eax, [rcx]
0x18002e04f  inc     eax
0x18002e051  mov     [rcx], eax
0x18002e053  jmp     loc_18002E1A3
0x18002e058  mov     rdx, r14; dwBytes
0x18002e05b  mov     qword ptr [r15], 0
0x18002e062  mov     ecx, 8; dwFlags
0x18002e067  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18002e06c  mov     rsi, rax
0x18002e06f  test    rax, rax
0x18002e072  jnz     short loc_18002E093
0x18002e074  mov     rcx, [rbp+188h]; this
0x18002e07b  mov     r14d, 8007000Eh
0x18002e081  mov     r9d, r14d; char *
0x18002e084  mov     edx, 14Bh; void *
0x18002e089  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e08e  jmp     loc_18002E11F
0x18002e093  xorps   xmm0, xmm0
0x18002e096  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x18002e09c  test    sil, 3
0x18002e0a0  jnz     loc_18002E236
0x18002e0a6  mov     r9, rsi
0x18002e0a9  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18002e0ae  shr     r9, 2; unsigned __int64
0x18002e0b2  lea     rcx, [rsp+280h+hObject]; this
0x18002e0b7  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18002e0bc  mov     r14d, eax
0x18002e0bf  test    eax, eax
0x18002e0c1  jns     loc_18002E15F
0x18002e0c7  mov     rcx, [rbp+188h]; this
0x18002e0ce  mov     r9d, eax; char *
0x18002e0d1  mov     edx, 14Eh; void *
0x18002e0d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e0db  mov     rcx, [rsp+280h+hObject+8]; hObject
0x18002e0e0  test    rcx, rcx
0x18002e0e3  jz      short loc_18002E0F3
0x18002e0e5  call    cs:__imp_CloseHandle
0x18002e0eb  test    eax, eax
0x18002e0ed  jz      loc_18002E23C
0x18002e0f3  mov     rcx, [rsp+280h+hObject]; hObject
0x18002e0f8  test    rcx, rcx
0x18002e0fb  jz      short loc_18002E10B
0x18002e0fd  call    cs:__imp_CloseHandle
0x18002e103  test    eax, eax
0x18002e105  jz      loc_18002E24E
0x18002e10b  call    cs:__imp_GetProcessHeap
0x18002e111  mov     r8, rsi; lpMem
0x18002e114  xor     edx, edx; dwFlags
0x18002e116  mov     rcx, rax; hHeap
0x18002e119  call    cs:__imp_HeapFree
0x18002e11f  mov     rcx, [rbp+188h]; this
0x18002e126  mov     r9d, r14d; char *
0x18002e129  mov     edx, 137h; void *
0x18002e12e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e133  test    rdi, rdi
0x18002e136  jz      short loc_18002E149
0x18002e138  mov     rcx, rdi; hMutex
0x18002e13b  call    cs:__imp_ReleaseMutex
0x18002e141  test    eax, eax
0x18002e143  jz      loc_18002E260
0x18002e149  mov     rcx, rbx; hObject
0x18002e14c  call    cs:__imp_CloseHandle
0x18002e152  test    eax, eax
0x18002e154  jz      loc_18002E272
0x18002e15a  mov     eax, r14d
0x18002e15d  jmp     short loc_18002E1CD
0x18002e15f  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18002e164  xor     edx, edx; Val
0x18002e166  mov     dword ptr [rsi], 1
0x18002e16c  lea     rcx, [rsi+22h]; void *
0x18002e170  mov     [rsi+8], rbx
0x18002e174  movdqu  xmmword ptr [rsi+10h], xmm0
0x18002e179  lea     r8d, [rdx+56h]; Size
0x18002e17d  call    memset_0
0x18002e182  xor     edx, edx; Val
0x18002e184  mov     word ptr [rsi+20h], 58h ; 'X'
0x18002e18a  lea     rcx, [rsi+28h]; void *
0x18002e18e  mov     dword ptr [rsi+24h], 1
0x18002e195  lea     r8d, [rdx+50h]; Size
0x18002e199  call    memset_0
0x18002e19e  xor     ebx, ebx
0x18002e1a0  mov     [r15], rsi
0x18002e1a3  test    rdi, rdi
0x18002e1a6  jz      short loc_18002E1B9
0x18002e1a8  mov     rcx, rdi; hMutex
0x18002e1ab  call    cs:__imp_ReleaseMutex
0x18002e1b1  test    eax, eax
0x18002e1b3  jz      loc_18002E284
0x18002e1b9  test    rbx, rbx
0x18002e1bc  jz      short loc_18002E1CB
0x18002e1be  mov     rcx, rbx; hObject
0x18002e1c1  call    cs:__imp_CloseHandle
0x18002e1c7  test    eax, eax
0x18002e1c9  jz      short loc_18002E1F3
0x18002e1cb  xor     eax, eax
0x18002e1cd  mov     rcx, [rbp+180h+var_30]
0x18002e1d4  xor     rcx, rsp; StackCookie
0x18002e1d7  call    __security_check_cookie
0x18002e1dc  mov     rbx, [rsp+280h+arg_10]
0x18002e1e4  add     rsp, 260h
0x18002e1eb  pop     r15
0x18002e1ed  pop     r14
0x18002e1ef  pop     rdi
0x18002e1f0  pop     rsi
0x18002e1f1  pop     rbp
0x18002e1f2  retn
0x18002e1f3  mov     rcx, [rbp+188h]; this
0x18002e1fa  mov     edx, 0A0Bh; void *
0x18002e1ff  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002e205  mov     rcx, [rbp+188h]; this
0x18002e20c  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18002e212  mov     rcx, [rbp+188h]; this
0x18002e219  mov     edx, 0A15h; void *
0x18002e21e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002e224  mov     rcx, [rbp+188h]; this
0x18002e22b  mov     edx, 0A0Bh; void *
0x18002e230  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002e236  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18002e23c  mov     rcx, [rbp+188h]; this
0x18002e243  mov     edx, 0A0Bh; void *
0x18002e248  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002e24e  mov     rcx, [rbp+188h]; this
0x18002e255  mov     edx, 0A0Bh; void *
0x18002e25a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002e260  mov     rcx, [rbp+188h]; this
0x18002e267  mov     edx, 0A15h; void *
0x18002e26c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002e272  mov     rcx, [rbp+188h]; this
0x18002e279  mov     edx, 0A0Bh; void *
0x18002e27e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002e284  mov     rcx, [rbp+188h]; this
0x18002e28b  mov     edx, 0A15h; void *
0x18002e290  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
