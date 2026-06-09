# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000a204`
- end: `0x18000a5f6`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1010`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000c080`

## callees

- `0x180009f7c`
- `0x18000a204`
- `0x18000aa10`
- `0x18000b268`
- `0x18000bc24`
- `0x18000ce30`
- `0x18000ea18`
- `0x18000fce4`
- `0x180010120`
- `0x180010a48`
- `0x180010d18`
- `0x180011a62`
- `0x180011a90`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x18000a23a`
- `KERNEL32!GetCurrentProcessId` at `0x18000a23a`
- `KERNEL32!CreateMutexExW` at `0x18000a283`
- `KERNEL32!CreateMutexExW` at `0x18000a283`
- `KERNEL32!GetProcessHeap` at `0x18000a436`
- `KERNEL32!GetProcessHeap` at `0x18000a436`
- `KERNEL32!HeapFree` at `0x18000a44a`
- `KERNEL32!HeapFree` at `0x18000a44a`
- `KERNEL32!CloseHandle` at `0x18000a2b5`
- `KERNEL32!CloseHandle` at `0x18000a37e`
- `KERNEL32!CloseHandle` at `0x18000a48e`
- `KERNEL32!CloseHandle` at `0x18000a532`
- `KERNEL32!CloseHandle` at `0x18000a2b5`
- `KERNEL32!CloseHandle` at `0x18000a37e`
- `KERNEL32!CloseHandle` at `0x18000a48e`
- `KERNEL32!CloseHandle` at `0x18000a532`
- `KERNEL32!ReleaseMutex` at `0x18000a35e`
- `KERNEL32!ReleaseMutex` at `0x18000a472`
- `KERNEL32!ReleaseMutex` at `0x18000a516`
- `KERNEL32!ReleaseMutex` at `0x18000a35e`
- `KERNEL32!ReleaseMutex` at `0x18000a472`
- `KERNEL32!ReleaseMutex` at `0x18000a516`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000a2d9`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000a2d9`

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
0x18000a204  mov     [rsp-8+arg_10], rbx
0x18000a209  push    rbp
0x18000a20a  push    rsi
0x18000a20b  push    rdi
0x18000a20c  push    r14
0x18000a20e  push    r15
0x18000a210  lea     rbp, [rsp-170h]
0x18000a218  sub     rsp, 270h
0x18000a21f  mov     rax, cs:__security_cookie
0x18000a226  xor     rax, rsp
0x18000a229  mov     [rbp+190h+var_30], rax
0x18000a230  and     qword ptr [rdx], 0
0x18000a234  mov     r15, rdx
0x18000a237  mov     rbx, rcx
0x18000a23a  call    cs:__imp_GetCurrentProcessId
0x18000a241  nop     dword ptr [rax+rax+00h]
0x18000a246  mov     esi, 78h ; 'x'
0x18000a24b  mov     [rsp+290h+var_268], rbx
0x18000a250  mov     r9d, eax
0x18000a253  mov     [rsp+290h+var_270], esi; int
0x18000a257  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000a25e  mov     edx, 104h; unsigned __int64
0x18000a263  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x18000a268  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a26d  and     [rsp+290h+hObject], 0
0x18000a273  lea     rdx, [rsp+290h+Name]; lpName
0x18000a278  mov     r9d, 1F0001h; dwDesiredAccess
0x18000a27e  xor     r8d, r8d; dwFlags
0x18000a281  xor     ecx, ecx; lpMutexAttributes
0x18000a283  call    cs:__imp_CreateMutexExW
0x18000a28a  nop     dword ptr [rax+rax+00h]
0x18000a28f  mov     rdx, rax
0x18000a292  lea     rcx, [rsp+290h+hObject]
0x18000a297  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000a29c  mov     rbx, [rsp+290h+hObject]
0x18000a2a1  test    rbx, rbx
0x18000a2a4  jnz     short loc_18000A2D0
0x18000a2a6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000a2ab  mov     edi, eax
0x18000a2ad  test    rbx, rbx
0x18000a2b0  jz      short loc_18000A2C9
0x18000a2b2  mov     rcx, rbx; hObject
0x18000a2b5  call    cs:__imp_CloseHandle
0x18000a2bc  nop     dword ptr [rax+rax+00h]
0x18000a2c1  test    eax, eax
0x18000a2c3  jz      loc_18000A58F
0x18000a2c9  mov     eax, edi
0x18000a2cb  jmp     loc_18000A544
0x18000a2d0  xor     r8d, r8d; bAlertable
0x18000a2d3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000a2d6  mov     rcx, rbx; hHandle
0x18000a2d9  call    cs:__imp_WaitForSingleObjectEx
0x18000a2e0  nop     dword ptr [rax+rax+00h]
0x18000a2e5  cmp     eax, 102h
0x18000a2ea  jz      short loc_18000A2FC
0x18000a2ec  test    eax, 0FFFFFF7Fh
0x18000a2f1  jnz     loc_18000A5A1
0x18000a2f7  mov     r14, rbx
0x18000a2fa  jmp     short loc_18000A2FF
0x18000a2fc  xor     r14d, r14d
0x18000a2ff  and     [rsp+290h+var_248], 0
0x18000a305  lea     r8, [rsp+290h+var_248]; unsigned __int64 *
0x18000a30a  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x18000a30f  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000a314  mov     edi, eax
0x18000a316  test    eax, eax
0x18000a318  jns     short loc_18000A397
0x18000a31a  mov     rcx, [rbp+198h]; this
0x18000a321  mov     r9d, eax; char *
0x18000a324  mov     edx, 64h ; 'd'; void *
0x18000a329  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a32e  mov     rcx, [rbp+198h]; this
0x18000a335  mov     r9d, edi; char *
0x18000a338  mov     edx, 6Dh ; 'm'; void *
0x18000a33d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a342  mov     rcx, [rbp+198h]; this
0x18000a349  mov     r9d, edi; char *
0x18000a34c  mov     edx, 12Bh; void *
0x18000a351  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a356  test    r14, r14
0x18000a359  jz      short loc_18000A372
0x18000a35b  mov     rcx, r14; hMutex
0x18000a35e  call    cs:__imp_ReleaseMutex
0x18000a365  nop     dword ptr [rax+rax+00h]
0x18000a36a  test    eax, eax
0x18000a36c  jz      loc_18000A5AE
0x18000a372  test    rbx, rbx
0x18000a375  jz      loc_18000A2C9
0x18000a37b  mov     rcx, rbx; hObject
0x18000a37e  call    cs:__imp_CloseHandle
0x18000a385  nop     dword ptr [rax+rax+00h]
0x18000a38a  test    eax, eax
0x18000a38c  jz      loc_18000A57D
0x18000a392  jmp     loc_18000A2C9
0x18000a397  mov     rax, [rsp+290h+var_248]
0x18000a39c  lea     rcx, ds:0[rax*4]
0x18000a3a4  test    rcx, rcx
0x18000a3a7  jz      short loc_18000A3BF
0x18000a3a9  mov     [r15], rcx
0x18000a3ac  mov     ecx, [rcx]
0x18000a3ae  mov     rax, [r15]
0x18000a3b1  inc     ecx
0x18000a3b3  mov     rbx, [rsp+290h+hObject]
0x18000a3b8  mov     [rax], ecx
0x18000a3ba  jmp     loc_18000A50E
0x18000a3bf  and     qword ptr [r15], 0
0x18000a3c3  mov     rdx, rsi; dwBytes
0x18000a3c6  mov     ecx, 8; dwFlags
0x18000a3cb  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000a3d0  mov     rdi, rax
0x18000a3d3  test    rax, rax
0x18000a3d6  jnz     short loc_18000A3F3
0x18000a3d8  mov     rcx, [rbp+198h]; this
0x18000a3df  mov     esi, 8007000Eh
0x18000a3e4  mov     r9d, esi; char *
0x18000a3e7  mov     edx, 148h; void *
0x18000a3ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a3f1  jmp     short loc_18000A456
0x18000a3f3  xorps   xmm0, xmm0
0x18000a3f6  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x18000a3fb  mov     r8, rdi; void *
0x18000a3fe  lea     rcx, [rsp+290h+var_258]; this
0x18000a403  movdqu  [rsp+290h+var_258], xmm0
0x18000a409  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x18000a40e  mov     esi, eax
0x18000a410  test    eax, eax
0x18000a412  jns     loc_18000A4A9
0x18000a418  mov     rcx, [rbp+198h]; this
0x18000a41f  mov     r9d, eax; char *
0x18000a422  mov     edx, 14Bh; void *
0x18000a427  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a42c  lea     rcx, [rsp+290h+var_258]; this
0x18000a431  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000a436  call    cs:__imp_GetProcessHeap
0x18000a43d  nop     dword ptr [rax+rax+00h]
0x18000a442  mov     r8, rdi; lpMem
0x18000a445  xor     edx, edx; dwFlags
0x18000a447  mov     rcx, rax; hHeap
0x18000a44a  call    cs:__imp_HeapFree
0x18000a451  nop     dword ptr [rax+rax+00h]
0x18000a456  mov     rcx, [rbp+198h]; this
0x18000a45d  mov     r9d, esi; char *
0x18000a460  mov     edx, 134h; void *
0x18000a465  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a46a  test    r14, r14
0x18000a46d  jz      short loc_18000A486
0x18000a46f  mov     rcx, r14; hMutex
0x18000a472  call    cs:__imp_ReleaseMutex
0x18000a479  nop     dword ptr [rax+rax+00h]
0x18000a47e  test    eax, eax
0x18000a480  jz      loc_18000A5C0
0x18000a486  test    rbx, rbx
0x18000a489  jz      short loc_18000A4A2
0x18000a48b  mov     rcx, rbx; hObject
0x18000a48e  call    cs:__imp_CloseHandle
0x18000a495  nop     dword ptr [rax+rax+00h]
0x18000a49a  test    eax, eax
0x18000a49c  jz      loc_18000A5D2
0x18000a4a2  mov     eax, esi
0x18000a4a4  jmp     loc_18000A544
0x18000a4a9  mov     rax, qword ptr [rsp+290h+var_258]
0x18000a4ae  lea     rcx, [rdi+22h]; void *
0x18000a4b2  mov     [rdi+8], rbx
0x18000a4b6  xor     edx, edx; Val
0x18000a4b8  xor     ebx, ebx
0x18000a4ba  mov     [rdi+10h], rax
0x18000a4be  mov     rax, qword ptr [rsp+290h+var_258+8]
0x18000a4c3  and     qword ptr [rsp+290h+var_258], rbx
0x18000a4c8  and     qword ptr [rsp+290h+var_258+8], rbx
0x18000a4cd  lea     r8d, [rbx+56h]; Size
0x18000a4d1  mov     dword ptr [rdi], 1
0x18000a4d7  mov     [rsp+290h+hObject], rbx
0x18000a4dc  mov     [rdi+18h], rax
0x18000a4e0  call    memset_0
0x18000a4e5  mov     word ptr [rdi+20h], 58h ; 'X'
0x18000a4eb  lea     rcx, [rdi+28h]; void *
0x18000a4ef  xor     edx, edx; Val
0x18000a4f1  mov     dword ptr [rdi+24h], 1
0x18000a4f8  lea     r8d, [rbx+50h]; Size
0x18000a4fc  call    memset_0
0x18000a501  lea     rcx, [rsp+290h+var_258]; this
0x18000a506  mov     [r15], rdi
0x18000a509  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000a50e  test    r14, r14
0x18000a511  jz      short loc_18000A52A
0x18000a513  mov     rcx, r14; hMutex
0x18000a516  call    cs:__imp_ReleaseMutex
0x18000a51d  nop     dword ptr [rax+rax+00h]
0x18000a522  test    eax, eax
0x18000a524  jz      loc_18000A5E4
0x18000a52a  test    rbx, rbx
0x18000a52d  jz      short loc_18000A542
0x18000a52f  mov     rcx, rbx; hObject
0x18000a532  call    cs:__imp_CloseHandle
0x18000a539  nop     dword ptr [rax+rax+00h]
0x18000a53e  test    eax, eax
0x18000a540  jz      short loc_18000A56B
0x18000a542  xor     eax, eax
0x18000a544  mov     rcx, [rbp+190h+var_30]
0x18000a54b  xor     rcx, rsp; StackCookie
0x18000a54e  call    __security_check_cookie
0x18000a553  mov     rbx, [rsp+290h+arg_10]
0x18000a55b  add     rsp, 270h
0x18000a562  pop     r15
0x18000a564  pop     r14
0x18000a566  pop     rdi
0x18000a567  pop     rsi
0x18000a568  pop     rbp
0x18000a569  retn
0x18000a56b  mov     rcx, [rbp+198h]; this
0x18000a572  mov     edx, 9CDh; void *
0x18000a577  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a57d  mov     rcx, [rbp+198h]; this
0x18000a584  mov     edx, 9CDh; void *
0x18000a589  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a58f  mov     rcx, [rbp+198h]; this
0x18000a596  mov     edx, 9CDh; void *
0x18000a59b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a5a1  mov     rcx, [rbp+198h]; this
0x18000a5a8  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000a5ae  mov     rcx, [rbp+198h]; this
0x18000a5b5  mov     edx, 9D7h; void *
0x18000a5ba  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a5c0  mov     rcx, [rbp+198h]; this
0x18000a5c7  mov     edx, 9D7h; void *
0x18000a5cc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a5d2  mov     rcx, [rbp+198h]; this
0x18000a5d9  mov     edx, 9CDh; void *
0x18000a5de  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a5e4  mov     rcx, [rbp+198h]; this
0x18000a5eb  mov     edx, 9D7h; void *
0x18000a5f0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
