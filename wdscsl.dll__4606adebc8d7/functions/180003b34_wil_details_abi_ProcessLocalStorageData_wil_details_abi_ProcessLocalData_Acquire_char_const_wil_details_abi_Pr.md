# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003b34`
- end: `0x180003f26`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1010`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180006998`

## callees

- `0x180003870`
- `0x180003b34`
- `0x180004e8c`
- `0x180005d08`
- `0x180006608`
- `0x180008344`
- `0x180009a04`
- `0x18000abcc`
- `0x18000b008`
- `0x18000b828`
- `0x18000bae8`
- `0x18000d6d2`
- `0x18000d700`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180003d7a`
- `KERNEL32!HeapFree` at `0x180003d7a`
- `KERNEL32!ReleaseMutex` at `0x180003c8e`
- `KERNEL32!ReleaseMutex` at `0x180003da2`
- `KERNEL32!ReleaseMutex` at `0x180003e46`
- `KERNEL32!ReleaseMutex` at `0x180003c8e`
- `KERNEL32!ReleaseMutex` at `0x180003da2`
- `KERNEL32!ReleaseMutex` at `0x180003e46`
- `KERNEL32!WaitForSingleObjectEx` at `0x180003c09`
- `KERNEL32!WaitForSingleObjectEx` at `0x180003c09`
- `KERNEL32!CloseHandle` at `0x180003be5`
- `KERNEL32!CloseHandle` at `0x180003cae`
- `KERNEL32!CloseHandle` at `0x180003dbe`
- `KERNEL32!CloseHandle` at `0x180003e62`
- `KERNEL32!CloseHandle` at `0x180003be5`
- `KERNEL32!CloseHandle` at `0x180003cae`
- `KERNEL32!CloseHandle` at `0x180003dbe`
- `KERNEL32!CloseHandle` at `0x180003e62`
- `KERNEL32!CreateMutexExW` at `0x180003bb3`
- `KERNEL32!CreateMutexExW` at `0x180003bb3`
- `KERNEL32!GetCurrentProcessId` at `0x180003b6a`
- `KERNEL32!GetCurrentProcessId` at `0x180003b6a`
- `KERNEL32!GetProcessHeap` at `0x180003d66`
- `KERNEL32!GetProcessHeap` at `0x180003d66`

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
0x180003b34  mov     [rsp-8+arg_10], rbx
0x180003b39  push    rbp
0x180003b3a  push    rsi
0x180003b3b  push    rdi
0x180003b3c  push    r14
0x180003b3e  push    r15
0x180003b40  lea     rbp, [rsp-170h]
0x180003b48  sub     rsp, 270h
0x180003b4f  mov     rax, cs:__security_cookie
0x180003b56  xor     rax, rsp
0x180003b59  mov     [rbp+190h+var_30], rax
0x180003b60  and     qword ptr [rdx], 0
0x180003b64  mov     r15, rdx
0x180003b67  mov     rbx, rcx
0x180003b6a  call    cs:__imp_GetCurrentProcessId
0x180003b71  nop     dword ptr [rax+rax+00h]
0x180003b76  mov     esi, 78h ; 'x'
0x180003b7b  mov     [rsp+290h+var_268], rbx
0x180003b80  mov     r9d, eax
0x180003b83  mov     [rsp+290h+var_270], esi; int
0x180003b87  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003b8e  mov     edx, 104h; unsigned __int64
0x180003b93  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x180003b98  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003b9d  and     [rsp+290h+hObject], 0
0x180003ba3  lea     rdx, [rsp+290h+Name]; lpName
0x180003ba8  mov     r9d, 1F0001h; dwDesiredAccess
0x180003bae  xor     r8d, r8d; dwFlags
0x180003bb1  xor     ecx, ecx; lpMutexAttributes
0x180003bb3  call    cs:__imp_CreateMutexExW
0x180003bba  nop     dword ptr [rax+rax+00h]
0x180003bbf  mov     rdx, rax
0x180003bc2  lea     rcx, [rsp+290h+hObject]
0x180003bc7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180003bcc  mov     rbx, [rsp+290h+hObject]
0x180003bd1  test    rbx, rbx
0x180003bd4  jnz     short loc_180003C00
0x180003bd6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003bdb  mov     edi, eax
0x180003bdd  test    rbx, rbx
0x180003be0  jz      short loc_180003BF9
0x180003be2  mov     rcx, rbx; hObject
0x180003be5  call    cs:__imp_CloseHandle
0x180003bec  nop     dword ptr [rax+rax+00h]
0x180003bf1  test    eax, eax
0x180003bf3  jz      loc_180003EBF
0x180003bf9  mov     eax, edi
0x180003bfb  jmp     loc_180003E74
0x180003c00  xor     r8d, r8d; bAlertable
0x180003c03  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003c06  mov     rcx, rbx; hHandle
0x180003c09  call    cs:__imp_WaitForSingleObjectEx
0x180003c10  nop     dword ptr [rax+rax+00h]
0x180003c15  cmp     eax, 102h
0x180003c1a  jz      short loc_180003C2C
0x180003c1c  test    eax, 0FFFFFF7Fh
0x180003c21  jnz     loc_180003ED1
0x180003c27  mov     r14, rbx
0x180003c2a  jmp     short loc_180003C2F
0x180003c2c  xor     r14d, r14d
0x180003c2f  and     [rsp+290h+var_248], 0
0x180003c35  lea     r8, [rsp+290h+var_248]; unsigned __int64 *
0x180003c3a  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x180003c3f  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003c44  mov     edi, eax
0x180003c46  test    eax, eax
0x180003c48  jns     short loc_180003CC7
0x180003c4a  mov     rcx, [rbp+198h]; this
0x180003c51  mov     r9d, eax; char *
0x180003c54  mov     edx, 64h ; 'd'; void *
0x180003c59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003c5e  mov     rcx, [rbp+198h]; this
0x180003c65  mov     r9d, edi; char *
0x180003c68  mov     edx, 6Dh ; 'm'; void *
0x180003c6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003c72  mov     rcx, [rbp+198h]; this
0x180003c79  mov     r9d, edi; char *
0x180003c7c  mov     edx, 12Bh; void *
0x180003c81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003c86  test    r14, r14
0x180003c89  jz      short loc_180003CA2
0x180003c8b  mov     rcx, r14; hMutex
0x180003c8e  call    cs:__imp_ReleaseMutex
0x180003c95  nop     dword ptr [rax+rax+00h]
0x180003c9a  test    eax, eax
0x180003c9c  jz      loc_180003EDE
0x180003ca2  test    rbx, rbx
0x180003ca5  jz      loc_180003BF9
0x180003cab  mov     rcx, rbx; hObject
0x180003cae  call    cs:__imp_CloseHandle
0x180003cb5  nop     dword ptr [rax+rax+00h]
0x180003cba  test    eax, eax
0x180003cbc  jz      loc_180003EAD
0x180003cc2  jmp     loc_180003BF9
0x180003cc7  mov     rax, [rsp+290h+var_248]
0x180003ccc  lea     rcx, ds:0[rax*4]
0x180003cd4  test    rcx, rcx
0x180003cd7  jz      short loc_180003CEF
0x180003cd9  mov     [r15], rcx
0x180003cdc  mov     ecx, [rcx]
0x180003cde  mov     rax, [r15]
0x180003ce1  inc     ecx
0x180003ce3  mov     rbx, [rsp+290h+hObject]
0x180003ce8  mov     [rax], ecx
0x180003cea  jmp     loc_180003E3E
0x180003cef  and     qword ptr [r15], 0
0x180003cf3  mov     rdx, rsi; dwBytes
0x180003cf6  mov     ecx, 8; dwFlags
0x180003cfb  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003d00  mov     rdi, rax
0x180003d03  test    rax, rax
0x180003d06  jnz     short loc_180003D23
0x180003d08  mov     rcx, [rbp+198h]; this
0x180003d0f  mov     esi, 8007000Eh
0x180003d14  mov     r9d, esi; char *
0x180003d17  mov     edx, 148h; void *
0x180003d1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003d21  jmp     short loc_180003D86
0x180003d23  xorps   xmm0, xmm0
0x180003d26  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180003d2b  mov     r8, rdi; void *
0x180003d2e  lea     rcx, [rsp+290h+var_258]; this
0x180003d33  movdqu  [rsp+290h+var_258], xmm0
0x180003d39  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x180003d3e  mov     esi, eax
0x180003d40  test    eax, eax
0x180003d42  jns     loc_180003DD9
0x180003d48  mov     rcx, [rbp+198h]; this
0x180003d4f  mov     r9d, eax; char *
0x180003d52  mov     edx, 14Bh; void *
0x180003d57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003d5c  lea     rcx, [rsp+290h+var_258]; this
0x180003d61  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180003d66  call    cs:__imp_GetProcessHeap
0x180003d6d  nop     dword ptr [rax+rax+00h]
0x180003d72  mov     r8, rdi; lpMem
0x180003d75  xor     edx, edx; dwFlags
0x180003d77  mov     rcx, rax; hHeap
0x180003d7a  call    cs:__imp_HeapFree
0x180003d81  nop     dword ptr [rax+rax+00h]
0x180003d86  mov     rcx, [rbp+198h]; this
0x180003d8d  mov     r9d, esi; char *
0x180003d90  mov     edx, 134h; void *
0x180003d95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003d9a  test    r14, r14
0x180003d9d  jz      short loc_180003DB6
0x180003d9f  mov     rcx, r14; hMutex
0x180003da2  call    cs:__imp_ReleaseMutex
0x180003da9  nop     dword ptr [rax+rax+00h]
0x180003dae  test    eax, eax
0x180003db0  jz      loc_180003EF0
0x180003db6  test    rbx, rbx
0x180003db9  jz      short loc_180003DD2
0x180003dbb  mov     rcx, rbx; hObject
0x180003dbe  call    cs:__imp_CloseHandle
0x180003dc5  nop     dword ptr [rax+rax+00h]
0x180003dca  test    eax, eax
0x180003dcc  jz      loc_180003F02
0x180003dd2  mov     eax, esi
0x180003dd4  jmp     loc_180003E74
0x180003dd9  mov     rax, qword ptr [rsp+290h+var_258]
0x180003dde  lea     rcx, [rdi+22h]; void *
0x180003de2  mov     [rdi+8], rbx
0x180003de6  xor     edx, edx; Val
0x180003de8  xor     ebx, ebx
0x180003dea  mov     [rdi+10h], rax
0x180003dee  mov     rax, qword ptr [rsp+290h+var_258+8]
0x180003df3  and     qword ptr [rsp+290h+var_258], rbx
0x180003df8  and     qword ptr [rsp+290h+var_258+8], rbx
0x180003dfd  lea     r8d, [rbx+56h]; Size
0x180003e01  mov     dword ptr [rdi], 1
0x180003e07  mov     [rsp+290h+hObject], rbx
0x180003e0c  mov     [rdi+18h], rax
0x180003e10  call    memset_0
0x180003e15  mov     word ptr [rdi+20h], 58h ; 'X'
0x180003e1b  lea     rcx, [rdi+28h]; void *
0x180003e1f  xor     edx, edx; Val
0x180003e21  mov     dword ptr [rdi+24h], 1
0x180003e28  lea     r8d, [rbx+50h]; Size
0x180003e2c  call    memset_0
0x180003e31  lea     rcx, [rsp+290h+var_258]; this
0x180003e36  mov     [r15], rdi
0x180003e39  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180003e3e  test    r14, r14
0x180003e41  jz      short loc_180003E5A
0x180003e43  mov     rcx, r14; hMutex
0x180003e46  call    cs:__imp_ReleaseMutex
0x180003e4d  nop     dword ptr [rax+rax+00h]
0x180003e52  test    eax, eax
0x180003e54  jz      loc_180003F14
0x180003e5a  test    rbx, rbx
0x180003e5d  jz      short loc_180003E72
0x180003e5f  mov     rcx, rbx; hObject
0x180003e62  call    cs:__imp_CloseHandle
0x180003e69  nop     dword ptr [rax+rax+00h]
0x180003e6e  test    eax, eax
0x180003e70  jz      short loc_180003E9B
0x180003e72  xor     eax, eax
0x180003e74  mov     rcx, [rbp+190h+var_30]
0x180003e7b  xor     rcx, rsp; StackCookie
0x180003e7e  call    __security_check_cookie
0x180003e83  mov     rbx, [rsp+290h+arg_10]
0x180003e8b  add     rsp, 270h
0x180003e92  pop     r15
0x180003e94  pop     r14
0x180003e96  pop     rdi
0x180003e97  pop     rsi
0x180003e98  pop     rbp
0x180003e99  retn
0x180003e9b  mov     rcx, [rbp+198h]; this
0x180003ea2  mov     edx, 9CDh; void *
0x180003ea7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003ead  mov     rcx, [rbp+198h]; this
0x180003eb4  mov     edx, 9CDh; void *
0x180003eb9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003ebf  mov     rcx, [rbp+198h]; this
0x180003ec6  mov     edx, 9CDh; void *
0x180003ecb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003ed1  mov     rcx, [rbp+198h]; this
0x180003ed8  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180003ede  mov     rcx, [rbp+198h]; this
0x180003ee5  mov     edx, 9D7h; void *
0x180003eea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003ef0  mov     rcx, [rbp+198h]; this
0x180003ef7  mov     edx, 9D7h; void *
0x180003efc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f02  mov     rcx, [rbp+198h]; this
0x180003f09  mov     edx, 9CDh; void *
0x180003f0e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f14  mov     rcx, [rbp+198h]; this
0x180003f1b  mov     edx, 9D7h; void *
0x180003f20  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
