# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000383c`
- end: `0x180003bda`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18000477c`

## callees

- `0x18000383c`
- `0x180003be0`
- `0x180003ec4`
- `0x180004518`
- `0x180004fe8`
- `0x180005230`
- `0x180005684`
- `0x180005710`
- `0x180005acc`
- `0x180005adc`
- `0x18001d33a`
- `0x18001d370`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800038b4`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800038b4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800038d5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800038d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003956`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003a7f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003aef`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003956`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003a7f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003aef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003a4f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003a4f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003a5d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003a5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003875`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003875`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003967`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003967`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b05`

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
0x18000383c  mov     [rsp-8+arg_10], rbx
0x180003841  push    rbp
0x180003842  push    rsi
0x180003843  push    rdi
0x180003844  push    r14
0x180003846  push    r15
0x180003848  lea     rbp, [rsp-160h]
0x180003850  sub     rsp, 260h
0x180003857  mov     rax, cs:__security_cookie
0x18000385e  xor     rax, rsp
0x180003861  mov     [rbp+180h+var_30], rax
0x180003868  mov     r15, rdx
0x18000386b  mov     qword ptr [rdx], 0
0x180003872  mov     rbx, rcx
0x180003875  call    cs:__imp_GetCurrentProcessId
0x18000387b  mov     r14d, 78h ; 'x'
0x180003881  mov     [rsp+280h+var_258], rbx
0x180003886  mov     r9d, eax
0x180003889  mov     [rsp+280h+var_260], r14d; int
0x18000388e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003895  mov     edx, 104h; unsigned __int64
0x18000389a  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000389f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800038a4  mov     r9d, 1F0001h; dwDesiredAccess
0x1800038aa  lea     rdx, [rsp+280h+Name]; lpName
0x1800038af  xor     r8d, r8d; dwFlags
0x1800038b2  xor     ecx, ecx; lpMutexAttributes
0x1800038b4  call    cs:__imp_CreateMutexExW
0x1800038ba  mov     rbx, rax
0x1800038bd  test    rax, rax
0x1800038c0  jnz     short loc_1800038CC
0x1800038c2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800038c7  jmp     loc_180003B11
0x1800038cc  xor     r8d, r8d; bAlertable
0x1800038cf  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800038d2  mov     rcx, rbx; hHandle
0x1800038d5  call    cs:__imp_WaitForSingleObjectEx
0x1800038db  cmp     eax, 102h
0x1800038e0  jz      short loc_1800038F2
0x1800038e2  test    eax, 0FFFFFF7Fh
0x1800038e7  jnz     loc_180003B49
0x1800038ed  mov     rdi, rbx
0x1800038f0  jmp     short loc_1800038F4
0x1800038f2  xor     edi, edi
0x1800038f4  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800038f9  mov     [rsp+280h+hObject], 0
0x180003902  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003907  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000390c  mov     esi, eax
0x18000390e  test    eax, eax
0x180003910  jns     short loc_18000397C
0x180003912  mov     rcx, [rbp+188h]; this
0x180003919  mov     r9d, eax; char *
0x18000391c  mov     edx, 66h ; 'f'; void *
0x180003921  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003926  mov     rcx, [rbp+188h]; this
0x18000392d  mov     r9d, esi; char *
0x180003930  mov     edx, 6Fh ; 'o'; void *
0x180003935  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000393a  mov     rcx, [rbp+188h]; this
0x180003941  mov     r9d, esi; char *
0x180003944  mov     edx, 12Eh; void *
0x180003949  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000394e  test    rdi, rdi
0x180003951  jz      short loc_180003964
0x180003953  mov     rcx, rdi; hMutex
0x180003956  call    cs:__imp_ReleaseMutex
0x18000395c  test    eax, eax
0x18000395e  jz      loc_180003B56
0x180003964  mov     rcx, rbx; hObject
0x180003967  call    cs:__imp_CloseHandle
0x18000396d  test    eax, eax
0x18000396f  jz      loc_180003B68
0x180003975  mov     eax, esi
0x180003977  jmp     loc_180003B11
0x18000397c  mov     rax, [rsp+280h+hObject]
0x180003981  lea     rcx, ds:0[rax*4]
0x180003989  test    rcx, rcx
0x18000398c  jz      short loc_18000399C
0x18000398e  mov     [r15], rcx
0x180003991  mov     eax, [rcx]
0x180003993  inc     eax
0x180003995  mov     [rcx], eax
0x180003997  jmp     loc_180003AE7
0x18000399c  mov     rdx, r14; dwBytes
0x18000399f  mov     qword ptr [r15], 0
0x1800039a6  mov     ecx, 8; dwFlags
0x1800039ab  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800039b0  mov     rsi, rax
0x1800039b3  test    rax, rax
0x1800039b6  jnz     short loc_1800039D7
0x1800039b8  mov     rcx, [rbp+188h]; this
0x1800039bf  mov     r14d, 8007000Eh
0x1800039c5  mov     r9d, r14d; char *
0x1800039c8  mov     edx, 14Bh; void *
0x1800039cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800039d2  jmp     loc_180003A63
0x1800039d7  xorps   xmm0, xmm0
0x1800039da  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800039e0  test    sil, 3
0x1800039e4  jnz     loc_180003B7A
0x1800039ea  mov     r9, rsi
0x1800039ed  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800039f2  shr     r9, 2; unsigned __int64
0x1800039f6  lea     rcx, [rsp+280h+hObject]; this
0x1800039fb  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180003a00  mov     r14d, eax
0x180003a03  test    eax, eax
0x180003a05  jns     loc_180003AA3
0x180003a0b  mov     rcx, [rbp+188h]; this
0x180003a12  mov     r9d, eax; char *
0x180003a15  mov     edx, 14Eh; void *
0x180003a1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003a1f  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180003a24  test    rcx, rcx
0x180003a27  jz      short loc_180003A37
0x180003a29  call    cs:__imp_CloseHandle
0x180003a2f  test    eax, eax
0x180003a31  jz      loc_180003B80
0x180003a37  mov     rcx, [rsp+280h+hObject]; hObject
0x180003a3c  test    rcx, rcx
0x180003a3f  jz      short loc_180003A4F
0x180003a41  call    cs:__imp_CloseHandle
0x180003a47  test    eax, eax
0x180003a49  jz      loc_180003B92
0x180003a4f  call    cs:__imp_GetProcessHeap
0x180003a55  mov     r8, rsi; lpMem
0x180003a58  xor     edx, edx; dwFlags
0x180003a5a  mov     rcx, rax; hHeap
0x180003a5d  call    cs:__imp_HeapFree
0x180003a63  mov     rcx, [rbp+188h]; this
0x180003a6a  mov     r9d, r14d; char *
0x180003a6d  mov     edx, 137h; void *
0x180003a72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003a77  test    rdi, rdi
0x180003a7a  jz      short loc_180003A8D
0x180003a7c  mov     rcx, rdi; hMutex
0x180003a7f  call    cs:__imp_ReleaseMutex
0x180003a85  test    eax, eax
0x180003a87  jz      loc_180003BA4
0x180003a8d  mov     rcx, rbx; hObject
0x180003a90  call    cs:__imp_CloseHandle
0x180003a96  test    eax, eax
0x180003a98  jz      loc_180003BB6
0x180003a9e  mov     eax, r14d
0x180003aa1  jmp     short loc_180003B11
0x180003aa3  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180003aa8  xor     edx, edx; Val
0x180003aaa  mov     dword ptr [rsi], 1
0x180003ab0  lea     rcx, [rsi+22h]; void *
0x180003ab4  mov     [rsi+8], rbx
0x180003ab8  movdqu  xmmword ptr [rsi+10h], xmm0
0x180003abd  lea     r8d, [rdx+56h]; Size
0x180003ac1  call    memset_0
0x180003ac6  xor     edx, edx; Val
0x180003ac8  mov     word ptr [rsi+20h], 58h ; 'X'
0x180003ace  lea     rcx, [rsi+28h]; void *
0x180003ad2  mov     dword ptr [rsi+24h], 1
0x180003ad9  lea     r8d, [rdx+50h]; Size
0x180003add  call    memset_0
0x180003ae2  xor     ebx, ebx
0x180003ae4  mov     [r15], rsi
0x180003ae7  test    rdi, rdi
0x180003aea  jz      short loc_180003AFD
0x180003aec  mov     rcx, rdi; hMutex
0x180003aef  call    cs:__imp_ReleaseMutex
0x180003af5  test    eax, eax
0x180003af7  jz      loc_180003BC8
0x180003afd  test    rbx, rbx
0x180003b00  jz      short loc_180003B0F
0x180003b02  mov     rcx, rbx; hObject
0x180003b05  call    cs:__imp_CloseHandle
0x180003b0b  test    eax, eax
0x180003b0d  jz      short loc_180003B37
0x180003b0f  xor     eax, eax
0x180003b11  mov     rcx, [rbp+180h+var_30]
0x180003b18  xor     rcx, rsp; StackCookie
0x180003b1b  call    __security_check_cookie
0x180003b20  mov     rbx, [rsp+280h+arg_10]
0x180003b28  add     rsp, 260h
0x180003b2f  pop     r15
0x180003b31  pop     r14
0x180003b33  pop     rdi
0x180003b34  pop     rsi
0x180003b35  pop     rbp
0x180003b36  retn
0x180003b37  mov     rcx, [rbp+188h]; this
0x180003b3e  mov     edx, 0A0Bh; void *
0x180003b43  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003b49  mov     rcx, [rbp+188h]; this
0x180003b50  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180003b56  mov     rcx, [rbp+188h]; this
0x180003b5d  mov     edx, 0A15h; void *
0x180003b62  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003b68  mov     rcx, [rbp+188h]; this
0x180003b6f  mov     edx, 0A0Bh; void *
0x180003b74  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003b7a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003b80  mov     rcx, [rbp+188h]; this
0x180003b87  mov     edx, 0A0Bh; void *
0x180003b8c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003b92  mov     rcx, [rbp+188h]; this
0x180003b99  mov     edx, 0A0Bh; void *
0x180003b9e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003ba4  mov     rcx, [rbp+188h]; this
0x180003bab  mov     edx, 0A15h; void *
0x180003bb0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003bb6  mov     rcx, [rbp+188h]; this
0x180003bbd  mov     edx, 0A0Bh; void *
0x180003bc2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003bc8  mov     rcx, [rbp+188h]; this
0x180003bcf  mov     edx, 0A15h; void *
0x180003bd4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
