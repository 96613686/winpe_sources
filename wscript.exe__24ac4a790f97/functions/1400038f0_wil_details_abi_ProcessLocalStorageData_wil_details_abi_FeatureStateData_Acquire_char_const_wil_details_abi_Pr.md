# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1400038f0`
- end: `0x140003cb7`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x140003ed4`

## callees

- `0x140003828`
- `0x1400038f0`
- `0x140003cc0`
- `0x140003f88`
- `0x140004300`
- `0x140004aa8`
- `0x140004bd4`
- `0x140004ca8`
- `0x140004ee8`
- `0x140005464`
- `0x140005474`
- `0x14001755a`
- `0x1400175a0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140003b0e`
- `KERNEL32!HeapFree` at `0x140003b0e`
- `KERNEL32!InitializeCriticalSectionEx` at `0x140003b99`
- `KERNEL32!InitializeCriticalSectionEx` at `0x140003b99`
- `KERNEL32!ReleaseMutex` at `0x140003a09`
- `KERNEL32!ReleaseMutex` at `0x140003b30`
- `KERNEL32!ReleaseMutex` at `0x140003bcc`
- `KERNEL32!ReleaseMutex` at `0x140003a09`
- `KERNEL32!ReleaseMutex` at `0x140003b30`
- `KERNEL32!ReleaseMutex` at `0x140003bcc`
- `KERNEL32!WaitForSingleObjectEx` at `0x140003988`
- `KERNEL32!WaitForSingleObjectEx` at `0x140003988`
- `KERNEL32!CloseHandle` at `0x140003a1a`
- `KERNEL32!CloseHandle` at `0x140003ada`
- `KERNEL32!CloseHandle` at `0x140003af2`
- `KERNEL32!CloseHandle` at `0x140003b41`
- `KERNEL32!CloseHandle` at `0x140003be2`
- `KERNEL32!CloseHandle` at `0x140003a1a`
- `KERNEL32!CloseHandle` at `0x140003ada`
- `KERNEL32!CloseHandle` at `0x140003af2`
- `KERNEL32!CloseHandle` at `0x140003b41`
- `KERNEL32!CloseHandle` at `0x140003be2`
- `KERNEL32!CreateMutexExW` at `0x140003967`
- `KERNEL32!CreateMutexExW` at `0x140003967`
- `KERNEL32!GetCurrentProcessId` at `0x140003929`
- `KERNEL32!GetCurrentProcessId` at `0x140003929`
- `KERNEL32!GetProcessHeap` at `0x140003b00`
- `KERNEL32!GetProcessHeap` at `0x140003b00`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
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
  _DWORD *v26; // r14
  unsigned int v27; // r8d
  int v28; // eax
  unsigned int v29; // r8d
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v35; // r8d
  const char *v36; // r9
  unsigned int v37; // r8d
  const char *v38; // r9
  __int128 v39; // xmm0
  unsigned int v40; // r8d
  const char *v41; // r9
  unsigned int v42; // r8d
  const char *v43; // r9
  int v44; // [rsp+20h] [rbp-E0h]
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v44);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v45);
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
  v23 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v26 = (_DWORD *)v23;
  if ( !v23 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v25, (const char *)0x8007000ELL, 304);
LABEL_23:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v27, (const char *)v15, v46);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v35, v36);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v37, v38);
    return v15;
  }
  *(_OWORD *)hObject = 0;
  if ( (v23 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
  v28 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)hObject,
          Name,
          v25,
          v23 >> 2);
  v15 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v29, (const char *)(unsigned int)v28, 304);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v26);
    goto LABEL_23;
  }
  v39 = *(_OWORD *)hObject;
  *v26 = 1;
  *((_QWORD *)v26 + 1) = v6;
  *((_OWORD *)v26 + 1) = v39;
  memset_0(v26 + 10, 0, 0x108u);
  *((_QWORD *)v26 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v26 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v26 + 58), 0, 0);
  *((_QWORD *)v26 + 34) = 0;
  *((_QWORD *)v26 + 35) = 0;
  *((_QWORD *)v26 + 36) = 0;
  *((_QWORD *)v26 + 37) = 0;
  v6 = 0;
  *a2 = v26;
LABEL_28:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v40, v41);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v42, v43);
  return 0;
}

```

## disassembly

```asm
0x1400038f0  mov     [rsp-8+arg_10], rbx
0x1400038f5  push    rbp
0x1400038f6  push    rsi
0x1400038f7  push    rdi
0x1400038f8  push    r14
0x1400038fa  push    r15
0x1400038fc  lea     rbp, [rsp-160h]
0x140003904  sub     rsp, 260h
0x14000390b  mov     rax, cs:__security_cookie
0x140003912  xor     rax, rsp
0x140003915  mov     [rbp+180h+var_30], rax
0x14000391c  mov     r15, rdx
0x14000391f  mov     qword ptr [rdx], 0
0x140003926  mov     rbx, rcx
0x140003929  call    cs:__imp_GetCurrentProcessId
0x14000392f  mov     r14d, 130h
0x140003935  mov     [rsp+280h+var_258], rbx
0x14000393a  mov     r9d, eax
0x14000393d  mov     [rsp+280h+var_260], r14d; int
0x140003942  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140003949  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000394e  lea     edx, [r14-2Ch]; unsigned __int64
0x140003952  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140003957  mov     r9d, 1F0001h; dwDesiredAccess
0x14000395d  lea     rdx, [rsp+280h+Name]; lpName
0x140003962  xor     r8d, r8d; dwFlags
0x140003965  xor     ecx, ecx; lpMutexAttributes
0x140003967  call    cs:__imp_CreateMutexExW
0x14000396d  mov     rbx, rax
0x140003970  test    rax, rax
0x140003973  jnz     short loc_14000397F
0x140003975  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000397a  jmp     loc_140003BEE
0x14000397f  xor     r8d, r8d; bAlertable
0x140003982  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140003985  mov     rcx, rbx; hHandle
0x140003988  call    cs:__imp_WaitForSingleObjectEx
0x14000398e  cmp     eax, 102h
0x140003993  jz      short loc_1400039A5
0x140003995  test    eax, 0FFFFFF7Fh
0x14000399a  jnz     loc_140003C38
0x1400039a0  mov     rdi, rbx
0x1400039a3  jmp     short loc_1400039A7
0x1400039a5  xor     edi, edi
0x1400039a7  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1400039ac  mov     [rsp+280h+hObject], 0
0x1400039b5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400039ba  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1400039bf  mov     esi, eax
0x1400039c1  test    eax, eax
0x1400039c3  jns     short loc_140003A2F
0x1400039c5  mov     rcx, [rbp+188h]; this
0x1400039cc  mov     r9d, eax; char *
0x1400039cf  mov     edx, 66h ; 'f'; void *
0x1400039d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400039d9  mov     rcx, [rbp+188h]; this
0x1400039e0  mov     r9d, esi; char *
0x1400039e3  mov     edx, 6Fh ; 'o'; void *
0x1400039e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400039ed  mov     rcx, [rbp+188h]; this
0x1400039f4  mov     r9d, esi; char *
0x1400039f7  mov     edx, 12Eh; void *
0x1400039fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003a01  test    rdi, rdi
0x140003a04  jz      short loc_140003A17
0x140003a06  mov     rcx, rdi; hMutex
0x140003a09  call    cs:__imp_ReleaseMutex
0x140003a0f  test    eax, eax
0x140003a11  jz      loc_140003C45
0x140003a17  mov     rcx, rbx; hObject
0x140003a1a  call    cs:__imp_CloseHandle
0x140003a20  test    eax, eax
0x140003a22  jz      loc_140003C57
0x140003a28  mov     eax, esi
0x140003a2a  jmp     loc_140003BEE
0x140003a2f  mov     rax, [rsp+280h+hObject]
0x140003a34  lea     rcx, ds:0[rax*4]
0x140003a3c  test    rcx, rcx
0x140003a3f  jz      short loc_140003A4F
0x140003a41  mov     [r15], rcx
0x140003a44  mov     eax, [rcx]
0x140003a46  inc     eax
0x140003a48  mov     [rcx], eax
0x140003a4a  jmp     loc_140003BC4
0x140003a4f  mov     rdx, r14; dwBytes
0x140003a52  mov     qword ptr [r15], 0
0x140003a59  mov     ecx, 8; dwFlags
0x140003a5e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140003a63  mov     r14, rax
0x140003a66  test    rax, rax
0x140003a69  jnz     short loc_140003A89
0x140003a6b  mov     rcx, [rbp+188h]; this
0x140003a72  mov     esi, 8007000Eh
0x140003a77  mov     r9d, esi; char *
0x140003a7a  mov     edx, 14Bh; void *
0x140003a7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003a84  jmp     loc_140003B14
0x140003a89  xorps   xmm0, xmm0
0x140003a8c  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x140003a92  test    r14b, 3
0x140003a96  jnz     loc_140003C69
0x140003a9c  mov     r9, r14
0x140003a9f  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140003aa4  shr     r9, 2; unsigned __int64
0x140003aa8  lea     rcx, [rsp+280h+hObject]; this
0x140003aad  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140003ab2  mov     esi, eax
0x140003ab4  test    eax, eax
0x140003ab6  jns     loc_140003B54
0x140003abc  mov     rcx, [rbp+188h]; this
0x140003ac3  mov     r9d, eax; char *
0x140003ac6  mov     edx, 14Eh; void *
0x140003acb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003ad0  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140003ad5  test    rcx, rcx
0x140003ad8  jz      short loc_140003AE8
0x140003ada  call    cs:__imp_CloseHandle
0x140003ae0  test    eax, eax
0x140003ae2  jz      loc_140003C6F
0x140003ae8  mov     rcx, [rsp+280h+hObject]; hObject
0x140003aed  test    rcx, rcx
0x140003af0  jz      short loc_140003B00
0x140003af2  call    cs:__imp_CloseHandle
0x140003af8  test    eax, eax
0x140003afa  jz      loc_140003C81
0x140003b00  call    cs:__imp_GetProcessHeap
0x140003b06  mov     r8, r14; lpMem
0x140003b09  xor     edx, edx; dwFlags
0x140003b0b  mov     rcx, rax; hHeap
0x140003b0e  call    cs:__imp_HeapFree
0x140003b14  mov     rcx, [rbp+188h]; this
0x140003b1b  mov     r9d, esi; char *
0x140003b1e  mov     edx, 137h; void *
0x140003b23  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003b28  test    rdi, rdi
0x140003b2b  jz      short loc_140003B3E
0x140003b2d  mov     rcx, rdi; hMutex
0x140003b30  call    cs:__imp_ReleaseMutex
0x140003b36  test    eax, eax
0x140003b38  jz      loc_140003C93
0x140003b3e  mov     rcx, rbx; hObject
0x140003b41  call    cs:__imp_CloseHandle
0x140003b47  test    eax, eax
0x140003b49  jz      loc_140003C26
0x140003b4f  jmp     loc_140003A28
0x140003b54  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x140003b59  lea     rcx, [r14+28h]; void *
0x140003b5d  mov     dword ptr [r14], 1
0x140003b64  xor     edx, edx; Val
0x140003b66  mov     [r14+8], rbx
0x140003b6a  mov     r8d, 108h; Size
0x140003b70  movdqu  xmmword ptr [r14+10h], xmm0
0x140003b76  call    memset_0
0x140003b7b  xor     eax, eax
0x140003b7d  lea     rcx, [r14+28h]; this
0x140003b81  mov     [r14+20h], rax
0x140003b85  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140003b8a  lea     rbx, [r14+0E8h]
0x140003b91  xor     r8d, r8d; Flags
0x140003b94  mov     rcx, rbx; lpCriticalSection
0x140003b97  xor     edx, edx; dwSpinCount
0x140003b99  call    cs:__imp_InitializeCriticalSectionEx
0x140003b9f  mov     qword ptr [rbx+28h], 0
0x140003ba7  mov     qword ptr [rbx+30h], 0
0x140003baf  mov     qword ptr [rbx+38h], 0
0x140003bb7  mov     qword ptr [rbx+40h], 0
0x140003bbf  xor     ebx, ebx
0x140003bc1  mov     [r15], r14
0x140003bc4  test    rdi, rdi
0x140003bc7  jz      short loc_140003BDA
0x140003bc9  mov     rcx, rdi; hMutex
0x140003bcc  call    cs:__imp_ReleaseMutex
0x140003bd2  test    eax, eax
0x140003bd4  jz      loc_140003CA5
0x140003bda  test    rbx, rbx
0x140003bdd  jz      short loc_140003BEC
0x140003bdf  mov     rcx, rbx; hObject
0x140003be2  call    cs:__imp_CloseHandle
0x140003be8  test    eax, eax
0x140003bea  jz      short loc_140003C14
0x140003bec  xor     eax, eax
0x140003bee  mov     rcx, [rbp+180h+var_30]
0x140003bf5  xor     rcx, rsp; StackCookie
0x140003bf8  call    __security_check_cookie
0x140003bfd  mov     rbx, [rsp+280h+arg_10]
0x140003c05  add     rsp, 260h
0x140003c0c  pop     r15
0x140003c0e  pop     r14
0x140003c10  pop     rdi
0x140003c11  pop     rsi
0x140003c12  pop     rbp
0x140003c13  retn
0x140003c14  mov     rcx, [rbp+188h]; this
0x140003c1b  mov     edx, 0A0Bh; void *
0x140003c20  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003c26  mov     rcx, [rbp+188h]; this
0x140003c2d  mov     edx, 0A0Bh; void *
0x140003c32  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003c38  mov     rcx, [rbp+188h]; this
0x140003c3f  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140003c45  mov     rcx, [rbp+188h]; this
0x140003c4c  mov     edx, 0A15h; void *
0x140003c51  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003c57  mov     rcx, [rbp+188h]; this
0x140003c5e  mov     edx, 0A0Bh; void *
0x140003c63  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003c69  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140003c6f  mov     rcx, [rbp+188h]; this
0x140003c76  mov     edx, 0A0Bh; void *
0x140003c7b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003c81  mov     rcx, [rbp+188h]; this
0x140003c88  mov     edx, 0A0Bh; void *
0x140003c8d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003c93  mov     rcx, [rbp+188h]; this
0x140003c9a  mov     edx, 0A15h; void *
0x140003c9f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003ca5  mov     rcx, [rbp+188h]; this
0x140003cac  mov     edx, 0A15h; void *
0x140003cb1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
