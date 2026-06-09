# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800036bc`
- end: `0x180003a5a`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18000455c`

## callees

- `0x1800036bc`
- `0x180003a88`
- `0x180003cb0`
- `0x1800042f8`
- `0x180004dd8`
- `0x180005094`
- `0x1800054d0`
- `0x18000555c`
- `0x180005924`
- `0x180005934`
- `0x18001afe2`
- `0x18001b020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003734`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003734`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003755`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003755`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800037d6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800038ff`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000396f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800037d6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800038ff`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000396f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800038cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800038cf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800038dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800038dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800036f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800036f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800037e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800038a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800038c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003910`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003985`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800037e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800038a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800038c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003910`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003985`

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
0x1800036bc  mov     [rsp-8+arg_10], rbx
0x1800036c1  push    rbp
0x1800036c2  push    rsi
0x1800036c3  push    rdi
0x1800036c4  push    r14
0x1800036c6  push    r15
0x1800036c8  lea     rbp, [rsp-160h]
0x1800036d0  sub     rsp, 260h
0x1800036d7  mov     rax, cs:__security_cookie
0x1800036de  xor     rax, rsp
0x1800036e1  mov     [rbp+180h+var_30], rax
0x1800036e8  mov     r15, rdx
0x1800036eb  mov     qword ptr [rdx], 0
0x1800036f2  mov     rbx, rcx
0x1800036f5  call    cs:__imp_GetCurrentProcessId
0x1800036fb  mov     r14d, 78h ; 'x'
0x180003701  mov     [rsp+280h+var_258], rbx
0x180003706  mov     r9d, eax
0x180003709  mov     [rsp+280h+var_260], r14d; int
0x18000370e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003715  mov     edx, 104h; unsigned __int64
0x18000371a  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000371f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003724  mov     r9d, 1F0001h; dwDesiredAccess
0x18000372a  lea     rdx, [rsp+280h+Name]; lpName
0x18000372f  xor     r8d, r8d; dwFlags
0x180003732  xor     ecx, ecx; lpMutexAttributes
0x180003734  call    cs:__imp_CreateMutexExW
0x18000373a  mov     rbx, rax
0x18000373d  test    rax, rax
0x180003740  jnz     short loc_18000374C
0x180003742  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003747  jmp     loc_180003991
0x18000374c  xor     r8d, r8d; bAlertable
0x18000374f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003752  mov     rcx, rbx; hHandle
0x180003755  call    cs:__imp_WaitForSingleObjectEx
0x18000375b  cmp     eax, 102h
0x180003760  jz      short loc_180003772
0x180003762  test    eax, 0FFFFFF7Fh
0x180003767  jnz     loc_1800039C9
0x18000376d  mov     rdi, rbx
0x180003770  jmp     short loc_180003774
0x180003772  xor     edi, edi
0x180003774  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003779  mov     [rsp+280h+hObject], 0
0x180003782  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003787  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000378c  mov     esi, eax
0x18000378e  test    eax, eax
0x180003790  jns     short loc_1800037FC
0x180003792  mov     rcx, [rbp+188h]; this
0x180003799  mov     r9d, eax; char *
0x18000379c  mov     edx, 66h ; 'f'; void *
0x1800037a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800037a6  mov     rcx, [rbp+188h]; this
0x1800037ad  mov     r9d, esi; char *
0x1800037b0  mov     edx, 6Fh ; 'o'; void *
0x1800037b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800037ba  mov     rcx, [rbp+188h]; this
0x1800037c1  mov     r9d, esi; char *
0x1800037c4  mov     edx, 12Eh; void *
0x1800037c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800037ce  test    rdi, rdi
0x1800037d1  jz      short loc_1800037E4
0x1800037d3  mov     rcx, rdi; hMutex
0x1800037d6  call    cs:__imp_ReleaseMutex
0x1800037dc  test    eax, eax
0x1800037de  jz      loc_1800039D6
0x1800037e4  mov     rcx, rbx; hObject
0x1800037e7  call    cs:__imp_CloseHandle
0x1800037ed  test    eax, eax
0x1800037ef  jz      loc_1800039E8
0x1800037f5  mov     eax, esi
0x1800037f7  jmp     loc_180003991
0x1800037fc  mov     rax, [rsp+280h+hObject]
0x180003801  lea     rcx, ds:0[rax*4]
0x180003809  test    rcx, rcx
0x18000380c  jz      short loc_18000381C
0x18000380e  mov     [r15], rcx
0x180003811  mov     eax, [rcx]
0x180003813  inc     eax
0x180003815  mov     [rcx], eax
0x180003817  jmp     loc_180003967
0x18000381c  mov     rdx, r14; dwBytes
0x18000381f  mov     qword ptr [r15], 0
0x180003826  mov     ecx, 8; dwFlags
0x18000382b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003830  mov     rsi, rax
0x180003833  test    rax, rax
0x180003836  jnz     short loc_180003857
0x180003838  mov     rcx, [rbp+188h]; this
0x18000383f  mov     r14d, 8007000Eh
0x180003845  mov     r9d, r14d; char *
0x180003848  mov     edx, 14Bh; void *
0x18000384d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003852  jmp     loc_1800038E3
0x180003857  xorps   xmm0, xmm0
0x18000385a  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003860  test    sil, 3
0x180003864  jnz     loc_1800039FA
0x18000386a  mov     r9, rsi
0x18000386d  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180003872  shr     r9, 2; unsigned __int64
0x180003876  lea     rcx, [rsp+280h+hObject]; this
0x18000387b  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180003880  mov     r14d, eax
0x180003883  test    eax, eax
0x180003885  jns     loc_180003923
0x18000388b  mov     rcx, [rbp+188h]; this
0x180003892  mov     r9d, eax; char *
0x180003895  mov     edx, 14Eh; void *
0x18000389a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000389f  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800038a4  test    rcx, rcx
0x1800038a7  jz      short loc_1800038B7
0x1800038a9  call    cs:__imp_CloseHandle
0x1800038af  test    eax, eax
0x1800038b1  jz      loc_180003A00
0x1800038b7  mov     rcx, [rsp+280h+hObject]; hObject
0x1800038bc  test    rcx, rcx
0x1800038bf  jz      short loc_1800038CF
0x1800038c1  call    cs:__imp_CloseHandle
0x1800038c7  test    eax, eax
0x1800038c9  jz      loc_180003A12
0x1800038cf  call    cs:__imp_GetProcessHeap
0x1800038d5  mov     r8, rsi; lpMem
0x1800038d8  xor     edx, edx; dwFlags
0x1800038da  mov     rcx, rax; hHeap
0x1800038dd  call    cs:__imp_HeapFree
0x1800038e3  mov     rcx, [rbp+188h]; this
0x1800038ea  mov     r9d, r14d; char *
0x1800038ed  mov     edx, 137h; void *
0x1800038f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800038f7  test    rdi, rdi
0x1800038fa  jz      short loc_18000390D
0x1800038fc  mov     rcx, rdi; hMutex
0x1800038ff  call    cs:__imp_ReleaseMutex
0x180003905  test    eax, eax
0x180003907  jz      loc_180003A24
0x18000390d  mov     rcx, rbx; hObject
0x180003910  call    cs:__imp_CloseHandle
0x180003916  test    eax, eax
0x180003918  jz      loc_180003A36
0x18000391e  mov     eax, r14d
0x180003921  jmp     short loc_180003991
0x180003923  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180003928  xor     edx, edx; Val
0x18000392a  mov     dword ptr [rsi], 1
0x180003930  lea     rcx, [rsi+22h]; void *
0x180003934  mov     [rsi+8], rbx
0x180003938  movdqu  xmmword ptr [rsi+10h], xmm0
0x18000393d  lea     r8d, [rdx+56h]; Size
0x180003941  call    memset_0
0x180003946  xor     edx, edx; Val
0x180003948  mov     word ptr [rsi+20h], 58h ; 'X'
0x18000394e  lea     rcx, [rsi+28h]; void *
0x180003952  mov     dword ptr [rsi+24h], 1
0x180003959  lea     r8d, [rdx+50h]; Size
0x18000395d  call    memset_0
0x180003962  xor     ebx, ebx
0x180003964  mov     [r15], rsi
0x180003967  test    rdi, rdi
0x18000396a  jz      short loc_18000397D
0x18000396c  mov     rcx, rdi; hMutex
0x18000396f  call    cs:__imp_ReleaseMutex
0x180003975  test    eax, eax
0x180003977  jz      loc_180003A48
0x18000397d  test    rbx, rbx
0x180003980  jz      short loc_18000398F
0x180003982  mov     rcx, rbx; hObject
0x180003985  call    cs:__imp_CloseHandle
0x18000398b  test    eax, eax
0x18000398d  jz      short loc_1800039B7
0x18000398f  xor     eax, eax
0x180003991  mov     rcx, [rbp+180h+var_30]
0x180003998  xor     rcx, rsp; StackCookie
0x18000399b  call    __security_check_cookie
0x1800039a0  mov     rbx, [rsp+280h+arg_10]
0x1800039a8  add     rsp, 260h
0x1800039af  pop     r15
0x1800039b1  pop     r14
0x1800039b3  pop     rdi
0x1800039b4  pop     rsi
0x1800039b5  pop     rbp
0x1800039b6  retn
0x1800039b7  mov     rcx, [rbp+188h]; this
0x1800039be  mov     edx, 0A0Bh; void *
0x1800039c3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800039c9  mov     rcx, [rbp+188h]; this
0x1800039d0  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800039d6  mov     rcx, [rbp+188h]; this
0x1800039dd  mov     edx, 0A15h; void *
0x1800039e2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800039e8  mov     rcx, [rbp+188h]; this
0x1800039ef  mov     edx, 0A0Bh; void *
0x1800039f4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800039fa  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003a00  mov     rcx, [rbp+188h]; this
0x180003a07  mov     edx, 0A0Bh; void *
0x180003a0c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003a12  mov     rcx, [rbp+188h]; this
0x180003a19  mov     edx, 0A0Bh; void *
0x180003a1e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003a24  mov     rcx, [rbp+188h]; this
0x180003a2b  mov     edx, 0A15h; void *
0x180003a30  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003a36  mov     rcx, [rbp+188h]; this
0x180003a3d  mov     edx, 0A0Bh; void *
0x180003a42  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003a48  mov     rcx, [rbp+188h]; this
0x180003a4f  mov     edx, 0A15h; void *
0x180003a54  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
