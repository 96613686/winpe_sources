# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180009c54`
- end: `0x18000a046`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1010`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000b464`

## callees

- `0x180006310`
- `0x1800099d8`
- `0x180009c54`
- `0x18000a5c4`
- `0x18000a934`
- `0x18000b1c8`
- `0x18000bf30`
- `0x18000d2c8`
- `0x18000dd90`
- `0x18000e5b8`
- `0x18000e860`
- `0x180030362`
- `0x180030390`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180009d05`
- `KERNEL32!CloseHandle` at `0x180009dce`
- `KERNEL32!CloseHandle` at `0x180009ede`
- `KERNEL32!CloseHandle` at `0x180009f82`
- `KERNEL32!CloseHandle` at `0x180009d05`
- `KERNEL32!CloseHandle` at `0x180009dce`
- `KERNEL32!CloseHandle` at `0x180009ede`
- `KERNEL32!CloseHandle` at `0x180009f82`
- `KERNEL32!GetProcessHeap` at `0x180009e86`
- `KERNEL32!GetProcessHeap` at `0x180009e86`
- `KERNEL32!HeapFree` at `0x180009e9a`
- `KERNEL32!HeapFree` at `0x180009e9a`
- `KERNEL32!ReleaseMutex` at `0x180009dae`
- `KERNEL32!ReleaseMutex` at `0x180009ec2`
- `KERNEL32!ReleaseMutex` at `0x180009f66`
- `KERNEL32!ReleaseMutex` at `0x180009dae`
- `KERNEL32!ReleaseMutex` at `0x180009ec2`
- `KERNEL32!ReleaseMutex` at `0x180009f66`
- `KERNEL32!WaitForSingleObjectEx` at `0x180009d29`
- `KERNEL32!WaitForSingleObjectEx` at `0x180009d29`
- `KERNEL32!GetCurrentProcessId` at `0x180009c8a`
- `KERNEL32!GetCurrentProcessId` at `0x180009c8a`
- `KERNEL32!CreateMutexExW` at `0x180009cd3`
- `KERNEL32!CreateMutexExW` at `0x180009cd3`

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
0x180009c54  mov     [rsp-8+arg_10], rbx
0x180009c59  push    rbp
0x180009c5a  push    rsi
0x180009c5b  push    rdi
0x180009c5c  push    r14
0x180009c5e  push    r15
0x180009c60  lea     rbp, [rsp-170h]
0x180009c68  sub     rsp, 270h
0x180009c6f  mov     rax, cs:__security_cookie
0x180009c76  xor     rax, rsp
0x180009c79  mov     [rbp+190h+var_30], rax
0x180009c80  and     qword ptr [rdx], 0
0x180009c84  mov     r15, rdx
0x180009c87  mov     rbx, rcx
0x180009c8a  call    cs:__imp_GetCurrentProcessId
0x180009c91  nop     dword ptr [rax+rax+00h]
0x180009c96  mov     esi, 78h ; 'x'
0x180009c9b  mov     [rsp+290h+var_268], rbx
0x180009ca0  mov     r9d, eax
0x180009ca3  mov     [rsp+290h+var_270], esi; int
0x180009ca7  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180009cae  mov     edx, 104h; unsigned __int64
0x180009cb3  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x180009cb8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009cbd  and     [rsp+290h+hObject], 0
0x180009cc3  lea     rdx, [rsp+290h+Name]; lpName
0x180009cc8  mov     r9d, 1F0001h; dwDesiredAccess
0x180009cce  xor     r8d, r8d; dwFlags
0x180009cd1  xor     ecx, ecx; lpMutexAttributes
0x180009cd3  call    cs:__imp_CreateMutexExW
0x180009cda  nop     dword ptr [rax+rax+00h]
0x180009cdf  mov     rdx, rax
0x180009ce2  lea     rcx, [rsp+290h+hObject]
0x180009ce7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180009cec  mov     rbx, [rsp+290h+hObject]
0x180009cf1  test    rbx, rbx
0x180009cf4  jnz     short loc_180009D20
0x180009cf6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009cfb  mov     edi, eax
0x180009cfd  test    rbx, rbx
0x180009d00  jz      short loc_180009D19
0x180009d02  mov     rcx, rbx; hObject
0x180009d05  call    cs:__imp_CloseHandle
0x180009d0c  nop     dword ptr [rax+rax+00h]
0x180009d11  test    eax, eax
0x180009d13  jz      loc_180009FDF
0x180009d19  mov     eax, edi
0x180009d1b  jmp     loc_180009F94
0x180009d20  xor     r8d, r8d; bAlertable
0x180009d23  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180009d26  mov     rcx, rbx; hHandle
0x180009d29  call    cs:__imp_WaitForSingleObjectEx
0x180009d30  nop     dword ptr [rax+rax+00h]
0x180009d35  cmp     eax, 102h
0x180009d3a  jz      short loc_180009D4C
0x180009d3c  test    eax, 0FFFFFF7Fh
0x180009d41  jnz     loc_180009FF1
0x180009d47  mov     r14, rbx
0x180009d4a  jmp     short loc_180009D4F
0x180009d4c  xor     r14d, r14d
0x180009d4f  and     [rsp+290h+var_248], 0
0x180009d55  lea     r8, [rsp+290h+var_248]; unsigned __int64 *
0x180009d5a  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x180009d5f  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180009d64  mov     edi, eax
0x180009d66  test    eax, eax
0x180009d68  jns     short loc_180009DE7
0x180009d6a  mov     rcx, [rbp+198h]; this
0x180009d71  mov     r9d, eax; char *
0x180009d74  mov     edx, 64h ; 'd'; void *
0x180009d79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009d7e  mov     rcx, [rbp+198h]; this
0x180009d85  mov     r9d, edi; char *
0x180009d88  mov     edx, 6Dh ; 'm'; void *
0x180009d8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009d92  mov     rcx, [rbp+198h]; this
0x180009d99  mov     r9d, edi; char *
0x180009d9c  mov     edx, 12Bh; void *
0x180009da1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009da6  test    r14, r14
0x180009da9  jz      short loc_180009DC2
0x180009dab  mov     rcx, r14; hMutex
0x180009dae  call    cs:__imp_ReleaseMutex
0x180009db5  nop     dword ptr [rax+rax+00h]
0x180009dba  test    eax, eax
0x180009dbc  jz      loc_180009FFE
0x180009dc2  test    rbx, rbx
0x180009dc5  jz      loc_180009D19
0x180009dcb  mov     rcx, rbx; hObject
0x180009dce  call    cs:__imp_CloseHandle
0x180009dd5  nop     dword ptr [rax+rax+00h]
0x180009dda  test    eax, eax
0x180009ddc  jz      loc_180009FCD
0x180009de2  jmp     loc_180009D19
0x180009de7  mov     rax, [rsp+290h+var_248]
0x180009dec  lea     rcx, ds:0[rax*4]
0x180009df4  test    rcx, rcx
0x180009df7  jz      short loc_180009E0F
0x180009df9  mov     [r15], rcx
0x180009dfc  mov     ecx, [rcx]
0x180009dfe  mov     rax, [r15]
0x180009e01  inc     ecx
0x180009e03  mov     rbx, [rsp+290h+hObject]
0x180009e08  mov     [rax], ecx
0x180009e0a  jmp     loc_180009F5E
0x180009e0f  and     qword ptr [r15], 0
0x180009e13  mov     rdx, rsi; dwBytes
0x180009e16  mov     ecx, 8; dwFlags
0x180009e1b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009e20  mov     rdi, rax
0x180009e23  test    rax, rax
0x180009e26  jnz     short loc_180009E43
0x180009e28  mov     rcx, [rbp+198h]; this
0x180009e2f  mov     esi, 8007000Eh
0x180009e34  mov     r9d, esi; char *
0x180009e37  mov     edx, 148h; void *
0x180009e3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009e41  jmp     short loc_180009EA6
0x180009e43  xorps   xmm0, xmm0
0x180009e46  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180009e4b  mov     r8, rdi; void *
0x180009e4e  lea     rcx, [rsp+290h+var_258]; this
0x180009e53  movdqu  [rsp+290h+var_258], xmm0
0x180009e59  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x180009e5e  mov     esi, eax
0x180009e60  test    eax, eax
0x180009e62  jns     loc_180009EF9
0x180009e68  mov     rcx, [rbp+198h]; this
0x180009e6f  mov     r9d, eax; char *
0x180009e72  mov     edx, 14Bh; void *
0x180009e77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009e7c  lea     rcx, [rsp+290h+var_258]; this
0x180009e81  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180009e86  call    cs:__imp_GetProcessHeap
0x180009e8d  nop     dword ptr [rax+rax+00h]
0x180009e92  mov     r8, rdi; lpMem
0x180009e95  xor     edx, edx; dwFlags
0x180009e97  mov     rcx, rax; hHeap
0x180009e9a  call    cs:__imp_HeapFree
0x180009ea1  nop     dword ptr [rax+rax+00h]
0x180009ea6  mov     rcx, [rbp+198h]; this
0x180009ead  mov     r9d, esi; char *
0x180009eb0  mov     edx, 134h; void *
0x180009eb5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009eba  test    r14, r14
0x180009ebd  jz      short loc_180009ED6
0x180009ebf  mov     rcx, r14; hMutex
0x180009ec2  call    cs:__imp_ReleaseMutex
0x180009ec9  nop     dword ptr [rax+rax+00h]
0x180009ece  test    eax, eax
0x180009ed0  jz      loc_18000A010
0x180009ed6  test    rbx, rbx
0x180009ed9  jz      short loc_180009EF2
0x180009edb  mov     rcx, rbx; hObject
0x180009ede  call    cs:__imp_CloseHandle
0x180009ee5  nop     dword ptr [rax+rax+00h]
0x180009eea  test    eax, eax
0x180009eec  jz      loc_18000A022
0x180009ef2  mov     eax, esi
0x180009ef4  jmp     loc_180009F94
0x180009ef9  mov     rax, qword ptr [rsp+290h+var_258]
0x180009efe  lea     rcx, [rdi+22h]; void *
0x180009f02  mov     [rdi+8], rbx
0x180009f06  xor     edx, edx; Val
0x180009f08  xor     ebx, ebx
0x180009f0a  mov     [rdi+10h], rax
0x180009f0e  mov     rax, qword ptr [rsp+290h+var_258+8]
0x180009f13  and     qword ptr [rsp+290h+var_258], rbx
0x180009f18  and     qword ptr [rsp+290h+var_258+8], rbx
0x180009f1d  lea     r8d, [rbx+56h]; Size
0x180009f21  mov     dword ptr [rdi], 1
0x180009f27  mov     [rsp+290h+hObject], rbx
0x180009f2c  mov     [rdi+18h], rax
0x180009f30  call    memset_0
0x180009f35  mov     word ptr [rdi+20h], 58h ; 'X'
0x180009f3b  lea     rcx, [rdi+28h]; void *
0x180009f3f  xor     edx, edx; Val
0x180009f41  mov     dword ptr [rdi+24h], 1
0x180009f48  lea     r8d, [rbx+50h]; Size
0x180009f4c  call    memset_0
0x180009f51  lea     rcx, [rsp+290h+var_258]; this
0x180009f56  mov     [r15], rdi
0x180009f59  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180009f5e  test    r14, r14
0x180009f61  jz      short loc_180009F7A
0x180009f63  mov     rcx, r14; hMutex
0x180009f66  call    cs:__imp_ReleaseMutex
0x180009f6d  nop     dword ptr [rax+rax+00h]
0x180009f72  test    eax, eax
0x180009f74  jz      loc_18000A034
0x180009f7a  test    rbx, rbx
0x180009f7d  jz      short loc_180009F92
0x180009f7f  mov     rcx, rbx; hObject
0x180009f82  call    cs:__imp_CloseHandle
0x180009f89  nop     dword ptr [rax+rax+00h]
0x180009f8e  test    eax, eax
0x180009f90  jz      short loc_180009FBB
0x180009f92  xor     eax, eax
0x180009f94  mov     rcx, [rbp+190h+var_30]
0x180009f9b  xor     rcx, rsp; StackCookie
0x180009f9e  call    __security_check_cookie
0x180009fa3  mov     rbx, [rsp+290h+arg_10]
0x180009fab  add     rsp, 270h
0x180009fb2  pop     r15
0x180009fb4  pop     r14
0x180009fb6  pop     rdi
0x180009fb7  pop     rsi
0x180009fb8  pop     rbp
0x180009fb9  retn
0x180009fbb  mov     rcx, [rbp+198h]; this
0x180009fc2  mov     edx, 9CDh; void *
0x180009fc7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009fcd  mov     rcx, [rbp+198h]; this
0x180009fd4  mov     edx, 9CDh; void *
0x180009fd9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009fdf  mov     rcx, [rbp+198h]; this
0x180009fe6  mov     edx, 9CDh; void *
0x180009feb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009ff1  mov     rcx, [rbp+198h]; this
0x180009ff8  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180009ffe  mov     rcx, [rbp+198h]; this
0x18000a005  mov     edx, 9D7h; void *
0x18000a00a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a010  mov     rcx, [rbp+198h]; this
0x18000a017  mov     edx, 9D7h; void *
0x18000a01c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a022  mov     rcx, [rbp+198h]; this
0x18000a029  mov     edx, 9CDh; void *
0x18000a02e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a034  mov     rcx, [rbp+198h]; this
0x18000a03b  mov     edx, 9D7h; void *
0x18000a040  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
