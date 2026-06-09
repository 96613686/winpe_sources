# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003e4c`
- end: `0x1800041ea`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1800058dc`

## callees

- `0x180001670`
- `0x180001fa4`
- `0x180003e4c`
- `0x180004830`
- `0x180004d58`
- `0x180005678`
- `0x180006678`
- `0x180007b90`
- `0x18000805c`
- `0x180008434`
- `0x180008d08`
- `0x180008d18`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003f66`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000408f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800040ff`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003f66`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000408f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800040ff`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003ee5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003ee5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003ec4`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003ec4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000406d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000406d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000405f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000405f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003e85`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003e85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004039`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004051`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004115`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004039`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004051`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004115`

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
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // r8d
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  __int64 v25; // r8
  _QWORD *v26; // rsi
  unsigned int v27; // r14d
  unsigned int v28; // r8d
  int v29; // eax
  unsigned int v30; // r8d
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v36; // r8d
  const char *v37; // r9
  unsigned int v38; // r8d
  const char *v39; // r9
  __int128 v40; // xmm0
  unsigned int v41; // r8d
  const char *v42; // r9
  unsigned int v43; // r8d
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
0x180003e4c  mov     [rsp-8+arg_10], rbx
0x180003e51  push    rbp
0x180003e52  push    rsi
0x180003e53  push    rdi
0x180003e54  push    r14
0x180003e56  push    r15
0x180003e58  lea     rbp, [rsp-160h]
0x180003e60  sub     rsp, 260h
0x180003e67  mov     rax, cs:__security_cookie
0x180003e6e  xor     rax, rsp
0x180003e71  mov     [rbp+180h+var_30], rax
0x180003e78  mov     r15, rdx
0x180003e7b  mov     qword ptr [rdx], 0
0x180003e82  mov     rbx, rcx
0x180003e85  call    cs:__imp_GetCurrentProcessId
0x180003e8b  mov     r14d, 78h ; 'x'
0x180003e91  mov     [rsp+280h+var_258], rbx
0x180003e96  mov     r9d, eax
0x180003e99  mov     [rsp+280h+var_260], r14d; int
0x180003e9e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003ea5  mov     edx, 104h; unsigned __int64
0x180003eaa  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003eaf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003eb4  mov     r9d, 1F0001h; dwDesiredAccess
0x180003eba  lea     rdx, [rsp+280h+Name]; lpName
0x180003ebf  xor     r8d, r8d; dwFlags
0x180003ec2  xor     ecx, ecx; lpMutexAttributes
0x180003ec4  call    cs:__imp_CreateMutexExW
0x180003eca  mov     rbx, rax
0x180003ecd  test    rax, rax
0x180003ed0  jnz     short loc_180003EDC
0x180003ed2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003ed7  jmp     loc_180004121
0x180003edc  xor     r8d, r8d; bAlertable
0x180003edf  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003ee2  mov     rcx, rbx; hHandle
0x180003ee5  call    cs:__imp_WaitForSingleObjectEx
0x180003eeb  cmp     eax, 102h
0x180003ef0  jz      short loc_180003F02
0x180003ef2  test    eax, 0FFFFFF7Fh
0x180003ef7  jnz     loc_180004159
0x180003efd  mov     rdi, rbx
0x180003f00  jmp     short loc_180003F04
0x180003f02  xor     edi, edi
0x180003f04  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003f09  mov     [rsp+280h+hObject], 0
0x180003f12  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003f17  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003f1c  mov     esi, eax
0x180003f1e  test    eax, eax
0x180003f20  jns     short loc_180003F8C
0x180003f22  mov     rcx, [rbp+188h]; this
0x180003f29  mov     r9d, eax; char *
0x180003f2c  mov     edx, 66h ; 'f'; void *
0x180003f31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003f36  mov     rcx, [rbp+188h]; this
0x180003f3d  mov     r9d, esi; char *
0x180003f40  mov     edx, 6Fh ; 'o'; void *
0x180003f45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003f4a  mov     rcx, [rbp+188h]; this
0x180003f51  mov     r9d, esi; char *
0x180003f54  mov     edx, 12Eh; void *
0x180003f59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003f5e  test    rdi, rdi
0x180003f61  jz      short loc_180003F74
0x180003f63  mov     rcx, rdi; hMutex
0x180003f66  call    cs:__imp_ReleaseMutex
0x180003f6c  test    eax, eax
0x180003f6e  jz      loc_180004166
0x180003f74  mov     rcx, rbx; hObject
0x180003f77  call    cs:__imp_CloseHandle
0x180003f7d  test    eax, eax
0x180003f7f  jz      loc_180004178
0x180003f85  mov     eax, esi
0x180003f87  jmp     loc_180004121
0x180003f8c  mov     rax, [rsp+280h+hObject]
0x180003f91  lea     rcx, ds:0[rax*4]
0x180003f99  test    rcx, rcx
0x180003f9c  jz      short loc_180003FAC
0x180003f9e  mov     [r15], rcx
0x180003fa1  mov     eax, [rcx]
0x180003fa3  inc     eax
0x180003fa5  mov     [rcx], eax
0x180003fa7  jmp     loc_1800040F7
0x180003fac  mov     rdx, r14; dwBytes
0x180003faf  mov     qword ptr [r15], 0
0x180003fb6  mov     ecx, 8; dwFlags
0x180003fbb  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003fc0  mov     rsi, rax
0x180003fc3  test    rax, rax
0x180003fc6  jnz     short loc_180003FE7
0x180003fc8  mov     rcx, [rbp+188h]; this
0x180003fcf  mov     r14d, 8007000Eh
0x180003fd5  mov     r9d, r14d; char *
0x180003fd8  mov     edx, 14Bh; void *
0x180003fdd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003fe2  jmp     loc_180004073
0x180003fe7  xorps   xmm0, xmm0
0x180003fea  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003ff0  test    sil, 3
0x180003ff4  jnz     loc_18000418A
0x180003ffa  mov     r9, rsi
0x180003ffd  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180004002  shr     r9, 2; unsigned __int64
0x180004006  lea     rcx, [rsp+280h+hObject]; this
0x18000400b  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180004010  mov     r14d, eax
0x180004013  test    eax, eax
0x180004015  jns     loc_1800040B3
0x18000401b  mov     rcx, [rbp+188h]; this
0x180004022  mov     r9d, eax; char *
0x180004025  mov     edx, 14Eh; void *
0x18000402a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000402f  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180004034  test    rcx, rcx
0x180004037  jz      short loc_180004047
0x180004039  call    cs:__imp_CloseHandle
0x18000403f  test    eax, eax
0x180004041  jz      loc_180004190
0x180004047  mov     rcx, [rsp+280h+hObject]; hObject
0x18000404c  test    rcx, rcx
0x18000404f  jz      short loc_18000405F
0x180004051  call    cs:__imp_CloseHandle
0x180004057  test    eax, eax
0x180004059  jz      loc_1800041A2
0x18000405f  call    cs:__imp_GetProcessHeap
0x180004065  mov     r8, rsi; lpMem
0x180004068  xor     edx, edx; dwFlags
0x18000406a  mov     rcx, rax; hHeap
0x18000406d  call    cs:__imp_HeapFree
0x180004073  mov     rcx, [rbp+188h]; this
0x18000407a  mov     r9d, r14d; char *
0x18000407d  mov     edx, 137h; void *
0x180004082  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004087  test    rdi, rdi
0x18000408a  jz      short loc_18000409D
0x18000408c  mov     rcx, rdi; hMutex
0x18000408f  call    cs:__imp_ReleaseMutex
0x180004095  test    eax, eax
0x180004097  jz      loc_1800041B4
0x18000409d  mov     rcx, rbx; hObject
0x1800040a0  call    cs:__imp_CloseHandle
0x1800040a6  test    eax, eax
0x1800040a8  jz      loc_1800041C6
0x1800040ae  mov     eax, r14d
0x1800040b1  jmp     short loc_180004121
0x1800040b3  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800040b8  xor     edx, edx; Val
0x1800040ba  mov     dword ptr [rsi], 1
0x1800040c0  lea     rcx, [rsi+22h]; void *
0x1800040c4  mov     [rsi+8], rbx
0x1800040c8  movdqu  xmmword ptr [rsi+10h], xmm0
0x1800040cd  lea     r8d, [rdx+56h]; Size
0x1800040d1  call    memset_0
0x1800040d6  xor     edx, edx; Val
0x1800040d8  mov     word ptr [rsi+20h], 58h ; 'X'
0x1800040de  lea     rcx, [rsi+28h]; void *
0x1800040e2  mov     dword ptr [rsi+24h], 1
0x1800040e9  lea     r8d, [rdx+50h]; Size
0x1800040ed  call    memset_0
0x1800040f2  xor     ebx, ebx
0x1800040f4  mov     [r15], rsi
0x1800040f7  test    rdi, rdi
0x1800040fa  jz      short loc_18000410D
0x1800040fc  mov     rcx, rdi; hMutex
0x1800040ff  call    cs:__imp_ReleaseMutex
0x180004105  test    eax, eax
0x180004107  jz      loc_1800041D8
0x18000410d  test    rbx, rbx
0x180004110  jz      short loc_18000411F
0x180004112  mov     rcx, rbx; hObject
0x180004115  call    cs:__imp_CloseHandle
0x18000411b  test    eax, eax
0x18000411d  jz      short loc_180004147
0x18000411f  xor     eax, eax
0x180004121  mov     rcx, [rbp+180h+var_30]
0x180004128  xor     rcx, rsp; StackCookie
0x18000412b  call    __security_check_cookie
0x180004130  mov     rbx, [rsp+280h+arg_10]
0x180004138  add     rsp, 260h
0x18000413f  pop     r15
0x180004141  pop     r14
0x180004143  pop     rdi
0x180004144  pop     rsi
0x180004145  pop     rbp
0x180004146  retn
0x180004147  mov     rcx, [rbp+188h]; this
0x18000414e  mov     edx, 0A0Bh; void *
0x180004153  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004159  mov     rcx, [rbp+188h]; this
0x180004160  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180004166  mov     rcx, [rbp+188h]; this
0x18000416d  mov     edx, 0A15h; void *
0x180004172  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004178  mov     rcx, [rbp+188h]; this
0x18000417f  mov     edx, 0A0Bh; void *
0x180004184  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000418a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004190  mov     rcx, [rbp+188h]; this
0x180004197  mov     edx, 0A0Bh; void *
0x18000419c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800041a2  mov     rcx, [rbp+188h]; this
0x1800041a9  mov     edx, 0A0Bh; void *
0x1800041ae  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800041b4  mov     rcx, [rbp+188h]; this
0x1800041bb  mov     edx, 0A15h; void *
0x1800041c0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800041c6  mov     rcx, [rbp+188h]; this
0x1800041cd  mov     edx, 0A0Bh; void *
0x1800041d2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800041d8  mov     rcx, [rbp+188h]; this
0x1800041df  mov     edx, 0A15h; void *
0x1800041e4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
