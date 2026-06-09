# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000794c`
- end: `0x180007d3e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1010`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800098c8`

## callees

- `0x180007648`
- `0x18000794c`
- `0x180008288`
- `0x1800088b4`
- `0x180009508`
- `0x18000ada8`
- `0x18000cb0c`
- `0x18000d9dc`
- `0x18000dec0`
- `0x18000eac4`
- `0x18000ee68`
- `0x18001c12a`
- `0x18001c150`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800079fd`
- `KERNEL32!CloseHandle` at `0x180007ac6`
- `KERNEL32!CloseHandle` at `0x180007bd6`
- `KERNEL32!CloseHandle` at `0x180007c7a`
- `KERNEL32!CloseHandle` at `0x1800079fd`
- `KERNEL32!CloseHandle` at `0x180007ac6`
- `KERNEL32!CloseHandle` at `0x180007bd6`
- `KERNEL32!CloseHandle` at `0x180007c7a`
- `KERNEL32!GetProcessHeap` at `0x180007b7e`
- `KERNEL32!GetProcessHeap` at `0x180007b7e`
- `KERNEL32!HeapFree` at `0x180007b92`
- `KERNEL32!HeapFree` at `0x180007b92`
- `KERNEL32!ReleaseMutex` at `0x180007aa6`
- `KERNEL32!ReleaseMutex` at `0x180007bba`
- `KERNEL32!ReleaseMutex` at `0x180007c5e`
- `KERNEL32!ReleaseMutex` at `0x180007aa6`
- `KERNEL32!ReleaseMutex` at `0x180007bba`
- `KERNEL32!ReleaseMutex` at `0x180007c5e`
- `KERNEL32!WaitForSingleObjectEx` at `0x180007a21`
- `KERNEL32!WaitForSingleObjectEx` at `0x180007a21`
- `KERNEL32!GetCurrentProcessId` at `0x180007982`
- `KERNEL32!GetCurrentProcessId` at `0x180007982`
- `KERNEL32!CreateMutexExW` at `0x1800079cb`
- `KERNEL32!CreateMutexExW` at `0x1800079cb`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  HANDLE v6; // rbx
  unsigned int v7; // edi
  DWORD v9; // eax
  void *v10; // rdx
  unsigned int v11; // r8d
  char *v12; // r9
  void *v13; // r14
  int ValueInternal; // eax
  unsigned __int64 v15; // r8
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // r8d
  const char *v21; // r9
  _DWORD *v22; // rcx
  HANDLE v23; // rbx
  _QWORD *v24; // rax
  unsigned int v25; // r8d
  _QWORD *v26; // rdi
  unsigned int v27; // esi
  unsigned int v28; // r8d
  int v29; // eax
  unsigned int v30; // r8d
  HANDLE ProcessHeap; // rax
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  __int64 v36; // rax
  __int64 v37; // rax
  unsigned int v38; // r8d
  const char *v39; // r9
  unsigned int v40; // r8d
  const char *v41; // r9
  int v42; // [rsp+20h] [rbp-E0h]
  int v43; // [rsp+20h] [rbp-E0h]
  int v44; // [rsp+20h] [rbp-E0h]
  HANDLE hObject; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v46; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v47; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  hObject = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &hObject,
    Mutex);
  v6 = hObject;
  if ( !hObject )
    return (unsigned int)wil::details::GetLastErrorFailHr(v5);
  v9 = WaitForSingleObjectEx(hObject, 0xFFFFFFFF, 0);
  if ( v9 == 258 )
  {
    v13 = 0;
  }
  else
  {
    if ( (v9 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v10, v11, v12);
    v13 = v6;
  }
  v47 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v10, &v47, (bool *)v12);
  v7 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x64, v15, (const char *)(unsigned int)ValueInternal, 120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6D, v16, (const char *)v7, v42);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12B, v17, (const char *)v7, v43);
    if ( v13 && !ReleaseMutex(v13) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D7, v18, v19);
    if ( v6 )
    {
      if ( !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v20, v21);
    }
    return v7;
  }
  v22 = (_DWORD *)(4 * v47);
  if ( 4 * v47 )
  {
    *a2 = v22;
    v23 = hObject;
    *(_DWORD *)*a2 = *v22 + 1;
    goto LABEL_26;
  }
  *a2 = 0;
  v24 = wil::details::ProcessHeapAlloc(8u, 0x78u, v15);
  v26 = v24;
  if ( v24 )
  {
    v46 = 0;
    v29 = wil::details_abi::SemaphoreValue::CreateFromPointer(
            (wil::details_abi::SemaphoreValue *)&v46,
            (char *)Name,
            (unsigned __int64)v24);
    v27 = v29;
    if ( v29 >= 0 )
    {
      v36 = v46;
      v26[1] = v6;
      v23 = 0;
      v26[2] = v36;
      v37 = *((_QWORD *)&v46 + 1);
      v46 = 0u;
      *(_DWORD *)v26 = 1;
      hObject = 0;
      v26[3] = v37;
      memset_0((char *)v26 + 34, 0, 0x56u);
      *((_WORD *)v26 + 16) = 88;
      *((_DWORD *)v26 + 9) = 1;
      memset_0(v26 + 5, 0, 0x50u);
      *a2 = v26;
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)&v46);
LABEL_26:
      if ( v13 && !ReleaseMutex(v13) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D7, v38, v39);
      if ( v23 && !CloseHandle(v23) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v40, v41);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v30, (const char *)(unsigned int)v29, 120);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)&v46);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v26);
  }
  else
  {
    v27 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x148, v25, (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x134, v28, (const char *)v27, v44);
  if ( v13 && !ReleaseMutex(v13) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D7, v32, v33);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v34, v35);
  return v27;
}

```

## disassembly

```asm
0x18000794c  mov     [rsp-8+arg_10], rbx
0x180007951  push    rbp
0x180007952  push    rsi
0x180007953  push    rdi
0x180007954  push    r14
0x180007956  push    r15
0x180007958  lea     rbp, [rsp-170h]
0x180007960  sub     rsp, 270h
0x180007967  mov     rax, cs:__security_cookie
0x18000796e  xor     rax, rsp
0x180007971  mov     [rbp+190h+var_30], rax
0x180007978  and     qword ptr [rdx], 0
0x18000797c  mov     r15, rdx
0x18000797f  mov     rbx, rcx
0x180007982  call    cs:__imp_GetCurrentProcessId
0x180007989  nop     dword ptr [rax+rax+00h]
0x18000798e  mov     esi, 78h ; 'x'
0x180007993  mov     [rsp+290h+var_268], rbx
0x180007998  mov     r9d, eax
0x18000799b  mov     [rsp+290h+var_270], esi; int
0x18000799f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800079a6  mov     edx, 104h; unsigned __int64
0x1800079ab  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x1800079b0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800079b5  and     [rsp+290h+hObject], 0
0x1800079bb  lea     rdx, [rsp+290h+Name]; lpName
0x1800079c0  mov     r9d, 1F0001h; dwDesiredAccess
0x1800079c6  xor     r8d, r8d; dwFlags
0x1800079c9  xor     ecx, ecx; lpMutexAttributes
0x1800079cb  call    cs:__imp_CreateMutexExW
0x1800079d2  nop     dword ptr [rax+rax+00h]
0x1800079d7  mov     rdx, rax
0x1800079da  lea     rcx, [rsp+290h+hObject]
0x1800079df  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800079e4  mov     rbx, [rsp+290h+hObject]
0x1800079e9  test    rbx, rbx
0x1800079ec  jnz     short loc_180007A18
0x1800079ee  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800079f3  mov     edi, eax
0x1800079f5  test    rbx, rbx
0x1800079f8  jz      short loc_180007A11
0x1800079fa  mov     rcx, rbx; hObject
0x1800079fd  call    cs:__imp_CloseHandle
0x180007a04  nop     dword ptr [rax+rax+00h]
0x180007a09  test    eax, eax
0x180007a0b  jz      loc_180007CD7
0x180007a11  mov     eax, edi
0x180007a13  jmp     loc_180007C8C
0x180007a18  xor     r8d, r8d; bAlertable
0x180007a1b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180007a1e  mov     rcx, rbx; hHandle
0x180007a21  call    cs:__imp_WaitForSingleObjectEx
0x180007a28  nop     dword ptr [rax+rax+00h]
0x180007a2d  cmp     eax, 102h
0x180007a32  jz      short loc_180007A44
0x180007a34  test    eax, 0FFFFFF7Fh
0x180007a39  jnz     loc_180007CE9
0x180007a3f  mov     r14, rbx
0x180007a42  jmp     short loc_180007A47
0x180007a44  xor     r14d, r14d
0x180007a47  and     [rsp+290h+var_248], 0
0x180007a4d  lea     r8, [rsp+290h+var_248]; unsigned __int64 *
0x180007a52  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x180007a57  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180007a5c  mov     edi, eax
0x180007a5e  test    eax, eax
0x180007a60  jns     short loc_180007ADF
0x180007a62  mov     rcx, [rbp+198h]; this
0x180007a69  mov     r9d, eax; char *
0x180007a6c  mov     edx, 64h ; 'd'; void *
0x180007a71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007a76  mov     rcx, [rbp+198h]; this
0x180007a7d  mov     r9d, edi; char *
0x180007a80  mov     edx, 6Dh ; 'm'; void *
0x180007a85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007a8a  mov     rcx, [rbp+198h]; this
0x180007a91  mov     r9d, edi; char *
0x180007a94  mov     edx, 12Bh; void *
0x180007a99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007a9e  test    r14, r14
0x180007aa1  jz      short loc_180007ABA
0x180007aa3  mov     rcx, r14; hMutex
0x180007aa6  call    cs:__imp_ReleaseMutex
0x180007aad  nop     dword ptr [rax+rax+00h]
0x180007ab2  test    eax, eax
0x180007ab4  jz      loc_180007CF6
0x180007aba  test    rbx, rbx
0x180007abd  jz      loc_180007A11
0x180007ac3  mov     rcx, rbx; hObject
0x180007ac6  call    cs:__imp_CloseHandle
0x180007acd  nop     dword ptr [rax+rax+00h]
0x180007ad2  test    eax, eax
0x180007ad4  jz      loc_180007CC5
0x180007ada  jmp     loc_180007A11
0x180007adf  mov     rax, [rsp+290h+var_248]
0x180007ae4  lea     rcx, ds:0[rax*4]
0x180007aec  test    rcx, rcx
0x180007aef  jz      short loc_180007B07
0x180007af1  mov     [r15], rcx
0x180007af4  mov     ecx, [rcx]
0x180007af6  mov     rax, [r15]
0x180007af9  inc     ecx
0x180007afb  mov     rbx, [rsp+290h+hObject]
0x180007b00  mov     [rax], ecx
0x180007b02  jmp     loc_180007C56
0x180007b07  and     qword ptr [r15], 0
0x180007b0b  mov     rdx, rsi; dwBytes
0x180007b0e  mov     ecx, 8; dwFlags
0x180007b13  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007b18  mov     rdi, rax
0x180007b1b  test    rax, rax
0x180007b1e  jnz     short loc_180007B3B
0x180007b20  mov     rcx, [rbp+198h]; this
0x180007b27  mov     esi, 8007000Eh
0x180007b2c  mov     r9d, esi; char *
0x180007b2f  mov     edx, 148h; void *
0x180007b34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007b39  jmp     short loc_180007B9E
0x180007b3b  xorps   xmm0, xmm0
0x180007b3e  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180007b43  mov     r8, rdi; void *
0x180007b46  lea     rcx, [rsp+290h+var_258]; this
0x180007b4b  movdqu  [rsp+290h+var_258], xmm0
0x180007b51  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x180007b56  mov     esi, eax
0x180007b58  test    eax, eax
0x180007b5a  jns     loc_180007BF1
0x180007b60  mov     rcx, [rbp+198h]; this
0x180007b67  mov     r9d, eax; char *
0x180007b6a  mov     edx, 14Bh; void *
0x180007b6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007b74  lea     rcx, [rsp+290h+var_258]; this
0x180007b79  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180007b7e  call    cs:__imp_GetProcessHeap
0x180007b85  nop     dword ptr [rax+rax+00h]
0x180007b8a  mov     r8, rdi; lpMem
0x180007b8d  xor     edx, edx; dwFlags
0x180007b8f  mov     rcx, rax; hHeap
0x180007b92  call    cs:__imp_HeapFree
0x180007b99  nop     dword ptr [rax+rax+00h]
0x180007b9e  mov     rcx, [rbp+198h]; this
0x180007ba5  mov     r9d, esi; char *
0x180007ba8  mov     edx, 134h; void *
0x180007bad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007bb2  test    r14, r14
0x180007bb5  jz      short loc_180007BCE
0x180007bb7  mov     rcx, r14; hMutex
0x180007bba  call    cs:__imp_ReleaseMutex
0x180007bc1  nop     dword ptr [rax+rax+00h]
0x180007bc6  test    eax, eax
0x180007bc8  jz      loc_180007D08
0x180007bce  test    rbx, rbx
0x180007bd1  jz      short loc_180007BEA
0x180007bd3  mov     rcx, rbx; hObject
0x180007bd6  call    cs:__imp_CloseHandle
0x180007bdd  nop     dword ptr [rax+rax+00h]
0x180007be2  test    eax, eax
0x180007be4  jz      loc_180007D1A
0x180007bea  mov     eax, esi
0x180007bec  jmp     loc_180007C8C
0x180007bf1  mov     rax, qword ptr [rsp+290h+var_258]
0x180007bf6  lea     rcx, [rdi+22h]; void *
0x180007bfa  mov     [rdi+8], rbx
0x180007bfe  xor     edx, edx; Val
0x180007c00  xor     ebx, ebx
0x180007c02  mov     [rdi+10h], rax
0x180007c06  mov     rax, qword ptr [rsp+290h+var_258+8]
0x180007c0b  and     qword ptr [rsp+290h+var_258], rbx
0x180007c10  and     qword ptr [rsp+290h+var_258+8], rbx
0x180007c15  lea     r8d, [rbx+56h]; Size
0x180007c19  mov     dword ptr [rdi], 1
0x180007c1f  mov     [rsp+290h+hObject], rbx
0x180007c24  mov     [rdi+18h], rax
0x180007c28  call    memset_0
0x180007c2d  mov     word ptr [rdi+20h], 58h ; 'X'
0x180007c33  lea     rcx, [rdi+28h]; void *
0x180007c37  xor     edx, edx; Val
0x180007c39  mov     dword ptr [rdi+24h], 1
0x180007c40  lea     r8d, [rbx+50h]; Size
0x180007c44  call    memset_0
0x180007c49  lea     rcx, [rsp+290h+var_258]; this
0x180007c4e  mov     [r15], rdi
0x180007c51  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180007c56  test    r14, r14
0x180007c59  jz      short loc_180007C72
0x180007c5b  mov     rcx, r14; hMutex
0x180007c5e  call    cs:__imp_ReleaseMutex
0x180007c65  nop     dword ptr [rax+rax+00h]
0x180007c6a  test    eax, eax
0x180007c6c  jz      loc_180007D2C
0x180007c72  test    rbx, rbx
0x180007c75  jz      short loc_180007C8A
0x180007c77  mov     rcx, rbx; hObject
0x180007c7a  call    cs:__imp_CloseHandle
0x180007c81  nop     dword ptr [rax+rax+00h]
0x180007c86  test    eax, eax
0x180007c88  jz      short loc_180007CB3
0x180007c8a  xor     eax, eax
0x180007c8c  mov     rcx, [rbp+190h+var_30]
0x180007c93  xor     rcx, rsp; StackCookie
0x180007c96  call    __security_check_cookie
0x180007c9b  mov     rbx, [rsp+290h+arg_10]
0x180007ca3  add     rsp, 270h
0x180007caa  pop     r15
0x180007cac  pop     r14
0x180007cae  pop     rdi
0x180007caf  pop     rsi
0x180007cb0  pop     rbp
0x180007cb1  retn
0x180007cb3  mov     rcx, [rbp+198h]; this
0x180007cba  mov     edx, 9CDh; void *
0x180007cbf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007cc5  mov     rcx, [rbp+198h]; this
0x180007ccc  mov     edx, 9CDh; void *
0x180007cd1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007cd7  mov     rcx, [rbp+198h]; this
0x180007cde  mov     edx, 9CDh; void *
0x180007ce3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007ce9  mov     rcx, [rbp+198h]; this
0x180007cf0  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180007cf6  mov     rcx, [rbp+198h]; this
0x180007cfd  mov     edx, 9D7h; void *
0x180007d02  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007d08  mov     rcx, [rbp+198h]; this
0x180007d0f  mov     edx, 9D7h; void *
0x180007d14  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007d1a  mov     rcx, [rbp+198h]; this
0x180007d21  mov     edx, 9CDh; void *
0x180007d26  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007d2c  mov     rcx, [rbp+198h]; this
0x180007d33  mov     edx, 9D7h; void *
0x180007d38  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
