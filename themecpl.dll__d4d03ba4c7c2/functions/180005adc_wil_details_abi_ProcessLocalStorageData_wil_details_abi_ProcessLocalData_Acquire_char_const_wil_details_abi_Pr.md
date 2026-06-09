# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180005adc`
- end: `0x180005eaf`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `979`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1800069d8`

## callees

- `0x180002280`
- `0x180002f34`
- `0x1800058b4`
- `0x180005adc`
- `0x180005eb8`
- `0x1800060ec`
- `0x1800066b0`
- `0x180007344`
- `0x180007824`
- `0x180008110`
- `0x1800081ec`
- `0x1800086d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005b81`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005b81`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005c21`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005d3e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005de1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005c21`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005d3e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005de1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005b5a`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005b5a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005d0f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005d0f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005cfb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005cfb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005b15`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005b15`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005c38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005dfd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005c38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005dfd`

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
  _DWORD *v21; // rax
  _DWORD *v22; // r14
  int v23; // eax
  HANDLE ProcessHeap; // rax
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned __int64 v29; // rax
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  int v34; // [rsp+20h] [rbp-E0h]
  int v35; // [rsp+20h] [rbp-E0h]
  int v36; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v37[2]; // [rsp+30h] [rbp-D0h] BYREF
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
  v37[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, v37, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v34);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v35);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v16, v17);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v18, v19);
    return v15;
  }
  v20 = (_DWORD *)(4 * v37[0]);
  if ( 4 * v37[0] )
  {
    *a2 = v20;
    ++*v20;
    goto LABEL_23;
  }
  *a2 = 0;
  v21 = wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v22 = v21;
  if ( !v21 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
    goto LABEL_18;
  }
  *(_OWORD *)v37 = 0;
  v23 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)v37, Name, v21);
  v15 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v23, 120);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v37);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v22);
LABEL_18:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v15, v36);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v25, v26);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    return v15;
  }
  *((_QWORD *)v22 + 2) = v37[0];
  v29 = v37[1];
  *v22 = 1;
  *((_QWORD *)v22 + 1) = v6;
  v37[0] = 0;
  *((_QWORD *)v22 + 3) = v29;
  v37[1] = 0;
  memset_0((char *)v22 + 34, 0, 0x56u);
  *((_WORD *)v22 + 16) = 88;
  v22[9] = 1;
  memset_0(v22 + 10, 0, 0x50u);
  *a2 = v22;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v37);
  v6 = 0;
LABEL_23:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v30, v31);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
  return 0;
}

```

## disassembly

```asm
0x180005adc  mov     [rsp-8+arg_10], rbx
0x180005ae1  push    rbp
0x180005ae2  push    rsi
0x180005ae3  push    rdi
0x180005ae4  push    r14
0x180005ae6  push    r15
0x180005ae8  lea     rbp, [rsp-160h]
0x180005af0  sub     rsp, 260h
0x180005af7  mov     rax, cs:__security_cookie
0x180005afe  xor     rax, rsp
0x180005b01  mov     [rbp+180h+var_30], rax
0x180005b08  mov     r15, rdx
0x180005b0b  mov     qword ptr [rdx], 0
0x180005b12  mov     rbx, rcx
0x180005b15  call    cs:__imp_GetCurrentProcessId
0x180005b1c  nop     dword ptr [rax+rax+00h]
0x180005b21  mov     r14d, 78h ; 'x'
0x180005b27  mov     [rsp+280h+var_258], rbx
0x180005b2c  mov     r9d, eax
0x180005b2f  mov     [rsp+280h+var_260], r14d; int
0x180005b34  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180005b3b  mov     edx, 104h; unsigned __int64
0x180005b40  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005b45  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005b4a  mov     r9d, 1F0001h; dwDesiredAccess
0x180005b50  lea     rdx, [rsp+280h+Name]; lpName
0x180005b55  xor     r8d, r8d; dwFlags
0x180005b58  xor     ecx, ecx; lpMutexAttributes
0x180005b5a  call    cs:__imp_CreateMutexExW
0x180005b61  nop     dword ptr [rax+rax+00h]
0x180005b66  mov     rbx, rax
0x180005b69  test    rax, rax
0x180005b6c  jnz     short loc_180005B78
0x180005b6e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005b73  jmp     loc_180005E0F
0x180005b78  xor     r8d, r8d; bAlertable
0x180005b7b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180005b7e  mov     rcx, rbx; hHandle
0x180005b81  call    cs:__imp_WaitForSingleObjectEx
0x180005b88  nop     dword ptr [rax+rax+00h]
0x180005b8d  cmp     eax, 102h
0x180005b92  jz      short loc_180005BA4
0x180005b94  test    eax, 0FFFFFF7Fh
0x180005b99  jnz     loc_180005E5A
0x180005b9f  mov     rdi, rbx
0x180005ba2  jmp     short loc_180005BA6
0x180005ba4  xor     edi, edi
0x180005ba6  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x180005bab  mov     [rsp+280h+var_250], 0
0x180005bb4  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005bb9  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180005bbe  mov     esi, eax
0x180005bc0  test    eax, eax
0x180005bc2  jns     loc_180005C53
0x180005bc8  mov     rcx, [rbp+188h]; this
0x180005bcf  lea     r8, aWil; "wil"
0x180005bd6  mov     r9d, eax; char *
0x180005bd9  mov     edx, 66h ; 'f'; void *
0x180005bde  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005be3  mov     rcx, [rbp+188h]; this
0x180005bea  lea     r8, aWil; "wil"
0x180005bf1  mov     r9d, esi; char *
0x180005bf4  mov     edx, 6Fh ; 'o'; void *
0x180005bf9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005bfe  mov     rcx, [rbp+188h]; this
0x180005c05  lea     r8, aWil; "wil"
0x180005c0c  mov     r9d, esi; char *
0x180005c0f  mov     edx, 12Eh; void *
0x180005c14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005c19  test    rdi, rdi
0x180005c1c  jz      short loc_180005C35
0x180005c1e  mov     rcx, rdi; hMutex
0x180005c21  call    cs:__imp_ReleaseMutex
0x180005c28  nop     dword ptr [rax+rax+00h]
0x180005c2d  test    eax, eax
0x180005c2f  jz      loc_180005E67
0x180005c35  mov     rcx, rbx; hObject
0x180005c38  call    cs:__imp_CloseHandle
0x180005c3f  nop     dword ptr [rax+rax+00h]
0x180005c44  test    eax, eax
0x180005c46  jz      loc_180005E79
0x180005c4c  mov     eax, esi
0x180005c4e  jmp     loc_180005E0F
0x180005c53  mov     rax, [rsp+280h+var_250]
0x180005c58  lea     rcx, ds:0[rax*4]
0x180005c60  test    rcx, rcx
0x180005c63  jz      short loc_180005C73
0x180005c65  mov     [r15], rcx
0x180005c68  mov     eax, [rcx]
0x180005c6a  inc     eax
0x180005c6c  mov     [rcx], eax
0x180005c6e  jmp     loc_180005DD9
0x180005c73  mov     rdx, r14; dwBytes
0x180005c76  mov     qword ptr [r15], 0
0x180005c7d  mov     ecx, 8; dwFlags
0x180005c82  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005c87  mov     r14, rax
0x180005c8a  test    rax, rax
0x180005c8d  jnz     short loc_180005CB1
0x180005c8f  mov     rcx, [rbp+188h]; this
0x180005c96  lea     r8, aWil; "wil"
0x180005c9d  mov     esi, 8007000Eh
0x180005ca2  mov     edx, 14Bh; void *
0x180005ca7  mov     r9d, esi; char *
0x180005caa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005caf  jmp     short loc_180005D1B
0x180005cb1  xorps   xmm0, xmm0
0x180005cb4  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180005cb9  mov     r8, r14; void *
0x180005cbc  lea     rcx, [rsp+280h+var_250]; this
0x180005cc1  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x180005cc7  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x180005ccc  mov     esi, eax
0x180005cce  test    eax, eax
0x180005cd0  jns     loc_180005D6E
0x180005cd6  mov     rcx, [rbp+188h]; this
0x180005cdd  lea     r8, aWil; "wil"
0x180005ce4  mov     r9d, eax; char *
0x180005ce7  mov     edx, 14Eh; void *
0x180005cec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005cf1  lea     rcx, [rsp+280h+var_250]; this
0x180005cf6  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180005cfb  call    cs:__imp_GetProcessHeap
0x180005d02  nop     dword ptr [rax+rax+00h]
0x180005d07  mov     r8, r14; lpMem
0x180005d0a  xor     edx, edx; dwFlags
0x180005d0c  mov     rcx, rax; hHeap
0x180005d0f  call    cs:__imp_HeapFree
0x180005d16  nop     dword ptr [rax+rax+00h]
0x180005d1b  mov     rcx, [rbp+188h]; this
0x180005d22  lea     r8, aWil; "wil"
0x180005d29  mov     r9d, esi; char *
0x180005d2c  mov     edx, 137h; void *
0x180005d31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005d36  test    rdi, rdi
0x180005d39  jz      short loc_180005D52
0x180005d3b  mov     rcx, rdi; hMutex
0x180005d3e  call    cs:__imp_ReleaseMutex
0x180005d45  nop     dword ptr [rax+rax+00h]
0x180005d4a  test    eax, eax
0x180005d4c  jz      loc_180005E8B
0x180005d52  mov     rcx, rbx; hObject
0x180005d55  call    cs:__imp_CloseHandle
0x180005d5c  nop     dword ptr [rax+rax+00h]
0x180005d61  test    eax, eax
0x180005d63  jz      loc_180005E48
0x180005d69  jmp     loc_180005C4C
0x180005d6e  mov     rax, [rsp+280h+var_250]
0x180005d73  lea     rcx, [r14+22h]; void *
0x180005d77  xor     edx, edx; Val
0x180005d79  mov     [r14+10h], rax
0x180005d7d  mov     rax, [rsp+280h+var_250+8]
0x180005d82  mov     dword ptr [r14], 1
0x180005d89  mov     [r14+8], rbx
0x180005d8d  lea     r8d, [rdx+56h]; Size
0x180005d91  mov     [rsp+280h+var_250], 0
0x180005d9a  mov     [r14+18h], rax
0x180005d9e  mov     [rsp+280h+var_250+8], 0
0x180005da7  call    memset_0
0x180005dac  xor     edx, edx; Val
0x180005dae  mov     word ptr [r14+20h], 58h ; 'X'
0x180005db5  lea     rcx, [r14+28h]; void *
0x180005db9  mov     dword ptr [r14+24h], 1
0x180005dc1  lea     r8d, [rdx+50h]; Size
0x180005dc5  call    memset_0
0x180005dca  lea     rcx, [rsp+280h+var_250]; this
0x180005dcf  mov     [r15], r14
0x180005dd2  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180005dd7  xor     ebx, ebx
0x180005dd9  test    rdi, rdi
0x180005ddc  jz      short loc_180005DF5
0x180005dde  mov     rcx, rdi; hMutex
0x180005de1  call    cs:__imp_ReleaseMutex
0x180005de8  nop     dword ptr [rax+rax+00h]
0x180005ded  test    eax, eax
0x180005def  jz      loc_180005E9D
0x180005df5  test    rbx, rbx
0x180005df8  jz      short loc_180005E0D
0x180005dfa  mov     rcx, rbx; hObject
0x180005dfd  call    cs:__imp_CloseHandle
0x180005e04  nop     dword ptr [rax+rax+00h]
0x180005e09  test    eax, eax
0x180005e0b  jz      short loc_180005E36
0x180005e0d  xor     eax, eax
0x180005e0f  mov     rcx, [rbp+180h+var_30]
0x180005e16  xor     rcx, rsp; StackCookie
0x180005e19  call    __security_check_cookie
0x180005e1e  mov     rbx, [rsp+280h+arg_10]
0x180005e26  add     rsp, 260h
0x180005e2d  pop     r15
0x180005e2f  pop     r14
0x180005e31  pop     rdi
0x180005e32  pop     rsi
0x180005e33  pop     rbp
0x180005e34  retn
0x180005e36  mov     rcx, [rbp+188h]; this
0x180005e3d  mov     edx, 0A0Bh; void *
0x180005e42  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005e48  mov     rcx, [rbp+188h]; this
0x180005e4f  mov     edx, 0A0Bh; void *
0x180005e54  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005e5a  mov     rcx, [rbp+188h]; this
0x180005e61  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180005e67  mov     rcx, [rbp+188h]; this
0x180005e6e  mov     edx, 0A15h; void *
0x180005e73  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005e79  mov     rcx, [rbp+188h]; this
0x180005e80  mov     edx, 0A0Bh; void *
0x180005e85  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005e8b  mov     rcx, [rbp+188h]; this
0x180005e92  mov     edx, 0A15h; void *
0x180005e97  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005e9d  mov     rcx, [rbp+188h]; this
0x180005ea4  mov     edx, 0A15h; void *
0x180005ea9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
