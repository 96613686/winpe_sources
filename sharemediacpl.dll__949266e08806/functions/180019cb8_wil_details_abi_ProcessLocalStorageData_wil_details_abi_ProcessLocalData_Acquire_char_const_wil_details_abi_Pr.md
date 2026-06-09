# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180019cb8`
- end: `0x18001a056`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18001ae4c`

## callees

- `0x180001d60`
- `0x18000291e`
- `0x180006ca8`
- `0x180019cb8`
- `0x18001a05c`
- `0x18001a498`
- `0x18001abe8`
- `0x18001ba20`
- `0x18001c2e0`
- `0x18001c66c`
- `0x18001cb88`
- `0x18001cb98`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180019ed9`
- `KERNEL32!HeapFree` at `0x180019ed9`
- `KERNEL32!CloseHandle` at `0x180019de3`
- `KERNEL32!CloseHandle` at `0x180019ea5`
- `KERNEL32!CloseHandle` at `0x180019ebd`
- `KERNEL32!CloseHandle` at `0x180019f0c`
- `KERNEL32!CloseHandle` at `0x180019f81`
- `KERNEL32!CloseHandle` at `0x180019de3`
- `KERNEL32!CloseHandle` at `0x180019ea5`
- `KERNEL32!CloseHandle` at `0x180019ebd`
- `KERNEL32!CloseHandle` at `0x180019f0c`
- `KERNEL32!CloseHandle` at `0x180019f81`
- `KERNEL32!CreateMutexExW` at `0x180019d30`
- `KERNEL32!CreateMutexExW` at `0x180019d30`
- `KERNEL32!ReleaseMutex` at `0x180019dd2`
- `KERNEL32!ReleaseMutex` at `0x180019efb`
- `KERNEL32!ReleaseMutex` at `0x180019f6b`
- `KERNEL32!ReleaseMutex` at `0x180019dd2`
- `KERNEL32!ReleaseMutex` at `0x180019efb`
- `KERNEL32!ReleaseMutex` at `0x180019f6b`
- `KERNEL32!GetProcessHeap` at `0x180019ecb`
- `KERNEL32!GetProcessHeap` at `0x180019ecb`
- `KERNEL32!WaitForSingleObjectEx` at `0x180019d51`
- `KERNEL32!WaitForSingleObjectEx` at `0x180019d51`
- `KERNEL32!GetCurrentProcessId` at `0x180019cf1`
- `KERNEL32!GetCurrentProcessId` at `0x180019cf1`

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
0x180019cb8  mov     [rsp-8+arg_10], rbx
0x180019cbd  push    rbp
0x180019cbe  push    rsi
0x180019cbf  push    rdi
0x180019cc0  push    r14
0x180019cc2  push    r15
0x180019cc4  lea     rbp, [rsp-160h]
0x180019ccc  sub     rsp, 260h
0x180019cd3  mov     rax, cs:__security_cookie
0x180019cda  xor     rax, rsp
0x180019cdd  mov     [rbp+180h+var_30], rax
0x180019ce4  mov     r15, rdx
0x180019ce7  mov     qword ptr [rdx], 0
0x180019cee  mov     rbx, rcx
0x180019cf1  call    cs:__imp_GetCurrentProcessId
0x180019cf7  mov     r14d, 78h ; 'x'
0x180019cfd  mov     [rsp+280h+var_258], rbx
0x180019d02  mov     r9d, eax
0x180019d05  mov     [rsp+280h+var_260], r14d; int
0x180019d0a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180019d11  mov     edx, 104h; unsigned __int64
0x180019d16  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180019d1b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180019d20  mov     r9d, 1F0001h; dwDesiredAccess
0x180019d26  lea     rdx, [rsp+280h+Name]; lpName
0x180019d2b  xor     r8d, r8d; dwFlags
0x180019d2e  xor     ecx, ecx; lpMutexAttributes
0x180019d30  call    cs:__imp_CreateMutexExW
0x180019d36  mov     rbx, rax
0x180019d39  test    rax, rax
0x180019d3c  jnz     short loc_180019D48
0x180019d3e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180019d43  jmp     loc_180019F8D
0x180019d48  xor     r8d, r8d; bAlertable
0x180019d4b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180019d4e  mov     rcx, rbx; hHandle
0x180019d51  call    cs:__imp_WaitForSingleObjectEx
0x180019d57  cmp     eax, 102h
0x180019d5c  jz      short loc_180019D6E
0x180019d5e  test    eax, 0FFFFFF7Fh
0x180019d63  jnz     loc_180019FC5
0x180019d69  mov     rdi, rbx
0x180019d6c  jmp     short loc_180019D70
0x180019d6e  xor     edi, edi
0x180019d70  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180019d75  mov     [rsp+280h+hObject], 0
0x180019d7e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180019d83  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180019d88  mov     esi, eax
0x180019d8a  test    eax, eax
0x180019d8c  jns     short loc_180019DF8
0x180019d8e  mov     rcx, [rbp+188h]; this
0x180019d95  mov     r9d, eax; char *
0x180019d98  mov     edx, 66h ; 'f'; void *
0x180019d9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019da2  mov     rcx, [rbp+188h]; this
0x180019da9  mov     r9d, esi; char *
0x180019dac  mov     edx, 6Fh ; 'o'; void *
0x180019db1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019db6  mov     rcx, [rbp+188h]; this
0x180019dbd  mov     r9d, esi; char *
0x180019dc0  mov     edx, 12Eh; void *
0x180019dc5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019dca  test    rdi, rdi
0x180019dcd  jz      short loc_180019DE0
0x180019dcf  mov     rcx, rdi; hMutex
0x180019dd2  call    cs:__imp_ReleaseMutex
0x180019dd8  test    eax, eax
0x180019dda  jz      loc_180019FD2
0x180019de0  mov     rcx, rbx; hObject
0x180019de3  call    cs:__imp_CloseHandle
0x180019de9  test    eax, eax
0x180019deb  jz      loc_180019FE4
0x180019df1  mov     eax, esi
0x180019df3  jmp     loc_180019F8D
0x180019df8  mov     rax, [rsp+280h+hObject]
0x180019dfd  lea     rcx, ds:0[rax*4]
0x180019e05  test    rcx, rcx
0x180019e08  jz      short loc_180019E18
0x180019e0a  mov     [r15], rcx
0x180019e0d  mov     eax, [rcx]
0x180019e0f  inc     eax
0x180019e11  mov     [rcx], eax
0x180019e13  jmp     loc_180019F63
0x180019e18  mov     rdx, r14; dwBytes
0x180019e1b  mov     qword ptr [r15], 0
0x180019e22  mov     ecx, 8; dwFlags
0x180019e27  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180019e2c  mov     rsi, rax
0x180019e2f  test    rax, rax
0x180019e32  jnz     short loc_180019E53
0x180019e34  mov     rcx, [rbp+188h]; this
0x180019e3b  mov     r14d, 8007000Eh
0x180019e41  mov     r9d, r14d; char *
0x180019e44  mov     edx, 14Bh; void *
0x180019e49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019e4e  jmp     loc_180019EDF
0x180019e53  xorps   xmm0, xmm0
0x180019e56  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180019e5c  test    sil, 3
0x180019e60  jnz     loc_180019FF6
0x180019e66  mov     r9, rsi
0x180019e69  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180019e6e  shr     r9, 2; unsigned __int64
0x180019e72  lea     rcx, [rsp+280h+hObject]; this
0x180019e77  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180019e7c  mov     r14d, eax
0x180019e7f  test    eax, eax
0x180019e81  jns     loc_180019F1F
0x180019e87  mov     rcx, [rbp+188h]; this
0x180019e8e  mov     r9d, eax; char *
0x180019e91  mov     edx, 14Eh; void *
0x180019e96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019e9b  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180019ea0  test    rcx, rcx
0x180019ea3  jz      short loc_180019EB3
0x180019ea5  call    cs:__imp_CloseHandle
0x180019eab  test    eax, eax
0x180019ead  jz      loc_180019FFC
0x180019eb3  mov     rcx, [rsp+280h+hObject]; hObject
0x180019eb8  test    rcx, rcx
0x180019ebb  jz      short loc_180019ECB
0x180019ebd  call    cs:__imp_CloseHandle
0x180019ec3  test    eax, eax
0x180019ec5  jz      loc_18001A00E
0x180019ecb  call    cs:__imp_GetProcessHeap
0x180019ed1  mov     r8, rsi; lpMem
0x180019ed4  xor     edx, edx; dwFlags
0x180019ed6  mov     rcx, rax; hHeap
0x180019ed9  call    cs:__imp_HeapFree
0x180019edf  mov     rcx, [rbp+188h]; this
0x180019ee6  mov     r9d, r14d; char *
0x180019ee9  mov     edx, 137h; void *
0x180019eee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019ef3  test    rdi, rdi
0x180019ef6  jz      short loc_180019F09
0x180019ef8  mov     rcx, rdi; hMutex
0x180019efb  call    cs:__imp_ReleaseMutex
0x180019f01  test    eax, eax
0x180019f03  jz      loc_18001A020
0x180019f09  mov     rcx, rbx; hObject
0x180019f0c  call    cs:__imp_CloseHandle
0x180019f12  test    eax, eax
0x180019f14  jz      loc_18001A032
0x180019f1a  mov     eax, r14d
0x180019f1d  jmp     short loc_180019F8D
0x180019f1f  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180019f24  xor     edx, edx; Val
0x180019f26  mov     dword ptr [rsi], 1
0x180019f2c  lea     rcx, [rsi+22h]; void *
0x180019f30  mov     [rsi+8], rbx
0x180019f34  movdqu  xmmword ptr [rsi+10h], xmm0
0x180019f39  lea     r8d, [rdx+56h]; Size
0x180019f3d  call    memset_0
0x180019f42  xor     edx, edx; Val
0x180019f44  mov     word ptr [rsi+20h], 58h ; 'X'
0x180019f4a  lea     rcx, [rsi+28h]; void *
0x180019f4e  mov     dword ptr [rsi+24h], 1
0x180019f55  lea     r8d, [rdx+50h]; Size
0x180019f59  call    memset_0
0x180019f5e  xor     ebx, ebx
0x180019f60  mov     [r15], rsi
0x180019f63  test    rdi, rdi
0x180019f66  jz      short loc_180019F79
0x180019f68  mov     rcx, rdi; hMutex
0x180019f6b  call    cs:__imp_ReleaseMutex
0x180019f71  test    eax, eax
0x180019f73  jz      loc_18001A044
0x180019f79  test    rbx, rbx
0x180019f7c  jz      short loc_180019F8B
0x180019f7e  mov     rcx, rbx; hObject
0x180019f81  call    cs:__imp_CloseHandle
0x180019f87  test    eax, eax
0x180019f89  jz      short loc_180019FB3
0x180019f8b  xor     eax, eax
0x180019f8d  mov     rcx, [rbp+180h+var_30]
0x180019f94  xor     rcx, rsp; StackCookie
0x180019f97  call    __security_check_cookie
0x180019f9c  mov     rbx, [rsp+280h+arg_10]
0x180019fa4  add     rsp, 260h
0x180019fab  pop     r15
0x180019fad  pop     r14
0x180019faf  pop     rdi
0x180019fb0  pop     rsi
0x180019fb1  pop     rbp
0x180019fb2  retn
0x180019fb3  mov     rcx, [rbp+188h]; this
0x180019fba  mov     edx, 0A0Bh; void *
0x180019fbf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180019fc5  mov     rcx, [rbp+188h]; this
0x180019fcc  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180019fd2  mov     rcx, [rbp+188h]; this
0x180019fd9  mov     edx, 0A15h; void *
0x180019fde  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180019fe4  mov     rcx, [rbp+188h]; this
0x180019feb  mov     edx, 0A0Bh; void *
0x180019ff0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180019ff6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180019ffc  mov     rcx, [rbp+188h]; this
0x18001a003  mov     edx, 0A0Bh; void *
0x18001a008  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001a00e  mov     rcx, [rbp+188h]; this
0x18001a015  mov     edx, 0A0Bh; void *
0x18001a01a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001a020  mov     rcx, [rbp+188h]; this
0x18001a027  mov     edx, 0A15h; void *
0x18001a02c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001a032  mov     rcx, [rbp+188h]; this
0x18001a039  mov     edx, 0A0Bh; void *
0x18001a03e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001a044  mov     rcx, [rbp+188h]; this
0x18001a04b  mov     edx, 0A15h; void *
0x18001a050  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
