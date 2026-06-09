# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180009110`
- end: `0x180009502`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1010`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000a924`

## callees

- `0x180005830`
- `0x180008e94`
- `0x180009110`
- `0x180009a84`
- `0x180009df4`
- `0x18000a688`
- `0x18000b3f0`
- `0x18000c788`
- `0x18000d250`
- `0x18000da78`
- `0x18000dd20`
- `0x18002f3ba`
- `0x18002f3e0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800091c1`
- `KERNEL32!CloseHandle` at `0x18000928a`
- `KERNEL32!CloseHandle` at `0x18000939a`
- `KERNEL32!CloseHandle` at `0x18000943e`
- `KERNEL32!CloseHandle` at `0x1800091c1`
- `KERNEL32!CloseHandle` at `0x18000928a`
- `KERNEL32!CloseHandle` at `0x18000939a`
- `KERNEL32!CloseHandle` at `0x18000943e`
- `KERNEL32!GetProcessHeap` at `0x180009342`
- `KERNEL32!GetProcessHeap` at `0x180009342`
- `KERNEL32!HeapFree` at `0x180009356`
- `KERNEL32!HeapFree` at `0x180009356`
- `KERNEL32!ReleaseMutex` at `0x18000926a`
- `KERNEL32!ReleaseMutex` at `0x18000937e`
- `KERNEL32!ReleaseMutex` at `0x180009422`
- `KERNEL32!ReleaseMutex` at `0x18000926a`
- `KERNEL32!ReleaseMutex` at `0x18000937e`
- `KERNEL32!ReleaseMutex` at `0x180009422`
- `KERNEL32!WaitForSingleObjectEx` at `0x1800091e5`
- `KERNEL32!WaitForSingleObjectEx` at `0x1800091e5`
- `KERNEL32!GetCurrentProcessId` at `0x180009146`
- `KERNEL32!GetCurrentProcessId` at `0x180009146`
- `KERNEL32!CreateMutexExW` at `0x18000918f`
- `KERNEL32!CreateMutexExW` at `0x18000918f`

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
0x180009110  mov     [rsp-8+arg_10], rbx
0x180009115  push    rbp
0x180009116  push    rsi
0x180009117  push    rdi
0x180009118  push    r14
0x18000911a  push    r15
0x18000911c  lea     rbp, [rsp-170h]
0x180009124  sub     rsp, 270h
0x18000912b  mov     rax, cs:__security_cookie
0x180009132  xor     rax, rsp
0x180009135  mov     [rbp+190h+var_30], rax
0x18000913c  and     qword ptr [rdx], 0
0x180009140  mov     r15, rdx
0x180009143  mov     rbx, rcx
0x180009146  call    cs:__imp_GetCurrentProcessId
0x18000914d  nop     dword ptr [rax+rax+00h]
0x180009152  mov     esi, 78h ; 'x'
0x180009157  mov     [rsp+290h+var_268], rbx
0x18000915c  mov     r9d, eax
0x18000915f  mov     [rsp+290h+var_270], esi; int
0x180009163  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000916a  mov     edx, 104h; unsigned __int64
0x18000916f  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x180009174  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009179  and     [rsp+290h+hObject], 0
0x18000917f  lea     rdx, [rsp+290h+Name]; lpName
0x180009184  mov     r9d, 1F0001h; dwDesiredAccess
0x18000918a  xor     r8d, r8d; dwFlags
0x18000918d  xor     ecx, ecx; lpMutexAttributes
0x18000918f  call    cs:__imp_CreateMutexExW
0x180009196  nop     dword ptr [rax+rax+00h]
0x18000919b  mov     rdx, rax
0x18000919e  lea     rcx, [rsp+290h+hObject]
0x1800091a3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800091a8  mov     rbx, [rsp+290h+hObject]
0x1800091ad  test    rbx, rbx
0x1800091b0  jnz     short loc_1800091DC
0x1800091b2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800091b7  mov     edi, eax
0x1800091b9  test    rbx, rbx
0x1800091bc  jz      short loc_1800091D5
0x1800091be  mov     rcx, rbx; hObject
0x1800091c1  call    cs:__imp_CloseHandle
0x1800091c8  nop     dword ptr [rax+rax+00h]
0x1800091cd  test    eax, eax
0x1800091cf  jz      loc_18000949B
0x1800091d5  mov     eax, edi
0x1800091d7  jmp     loc_180009450
0x1800091dc  xor     r8d, r8d; bAlertable
0x1800091df  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800091e2  mov     rcx, rbx; hHandle
0x1800091e5  call    cs:__imp_WaitForSingleObjectEx
0x1800091ec  nop     dword ptr [rax+rax+00h]
0x1800091f1  cmp     eax, 102h
0x1800091f6  jz      short loc_180009208
0x1800091f8  test    eax, 0FFFFFF7Fh
0x1800091fd  jnz     loc_1800094AD
0x180009203  mov     r14, rbx
0x180009206  jmp     short loc_18000920B
0x180009208  xor     r14d, r14d
0x18000920b  and     [rsp+290h+var_248], 0
0x180009211  lea     r8, [rsp+290h+var_248]; unsigned __int64 *
0x180009216  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x18000921b  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180009220  mov     edi, eax
0x180009222  test    eax, eax
0x180009224  jns     short loc_1800092A3
0x180009226  mov     rcx, [rbp+198h]; this
0x18000922d  mov     r9d, eax; char *
0x180009230  mov     edx, 64h ; 'd'; void *
0x180009235  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000923a  mov     rcx, [rbp+198h]; this
0x180009241  mov     r9d, edi; char *
0x180009244  mov     edx, 6Dh ; 'm'; void *
0x180009249  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000924e  mov     rcx, [rbp+198h]; this
0x180009255  mov     r9d, edi; char *
0x180009258  mov     edx, 12Bh; void *
0x18000925d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009262  test    r14, r14
0x180009265  jz      short loc_18000927E
0x180009267  mov     rcx, r14; hMutex
0x18000926a  call    cs:__imp_ReleaseMutex
0x180009271  nop     dword ptr [rax+rax+00h]
0x180009276  test    eax, eax
0x180009278  jz      loc_1800094BA
0x18000927e  test    rbx, rbx
0x180009281  jz      loc_1800091D5
0x180009287  mov     rcx, rbx; hObject
0x18000928a  call    cs:__imp_CloseHandle
0x180009291  nop     dword ptr [rax+rax+00h]
0x180009296  test    eax, eax
0x180009298  jz      loc_180009489
0x18000929e  jmp     loc_1800091D5
0x1800092a3  mov     rax, [rsp+290h+var_248]
0x1800092a8  lea     rcx, ds:0[rax*4]
0x1800092b0  test    rcx, rcx
0x1800092b3  jz      short loc_1800092CB
0x1800092b5  mov     [r15], rcx
0x1800092b8  mov     ecx, [rcx]
0x1800092ba  mov     rax, [r15]
0x1800092bd  inc     ecx
0x1800092bf  mov     rbx, [rsp+290h+hObject]
0x1800092c4  mov     [rax], ecx
0x1800092c6  jmp     loc_18000941A
0x1800092cb  and     qword ptr [r15], 0
0x1800092cf  mov     rdx, rsi; dwBytes
0x1800092d2  mov     ecx, 8; dwFlags
0x1800092d7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800092dc  mov     rdi, rax
0x1800092df  test    rax, rax
0x1800092e2  jnz     short loc_1800092FF
0x1800092e4  mov     rcx, [rbp+198h]; this
0x1800092eb  mov     esi, 8007000Eh
0x1800092f0  mov     r9d, esi; char *
0x1800092f3  mov     edx, 148h; void *
0x1800092f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800092fd  jmp     short loc_180009362
0x1800092ff  xorps   xmm0, xmm0
0x180009302  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180009307  mov     r8, rdi; void *
0x18000930a  lea     rcx, [rsp+290h+var_258]; this
0x18000930f  movdqu  [rsp+290h+var_258], xmm0
0x180009315  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x18000931a  mov     esi, eax
0x18000931c  test    eax, eax
0x18000931e  jns     loc_1800093B5
0x180009324  mov     rcx, [rbp+198h]; this
0x18000932b  mov     r9d, eax; char *
0x18000932e  mov     edx, 14Bh; void *
0x180009333  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009338  lea     rcx, [rsp+290h+var_258]; this
0x18000933d  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180009342  call    cs:__imp_GetProcessHeap
0x180009349  nop     dword ptr [rax+rax+00h]
0x18000934e  mov     r8, rdi; lpMem
0x180009351  xor     edx, edx; dwFlags
0x180009353  mov     rcx, rax; hHeap
0x180009356  call    cs:__imp_HeapFree
0x18000935d  nop     dword ptr [rax+rax+00h]
0x180009362  mov     rcx, [rbp+198h]; this
0x180009369  mov     r9d, esi; char *
0x18000936c  mov     edx, 134h; void *
0x180009371  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009376  test    r14, r14
0x180009379  jz      short loc_180009392
0x18000937b  mov     rcx, r14; hMutex
0x18000937e  call    cs:__imp_ReleaseMutex
0x180009385  nop     dword ptr [rax+rax+00h]
0x18000938a  test    eax, eax
0x18000938c  jz      loc_1800094CC
0x180009392  test    rbx, rbx
0x180009395  jz      short loc_1800093AE
0x180009397  mov     rcx, rbx; hObject
0x18000939a  call    cs:__imp_CloseHandle
0x1800093a1  nop     dword ptr [rax+rax+00h]
0x1800093a6  test    eax, eax
0x1800093a8  jz      loc_1800094DE
0x1800093ae  mov     eax, esi
0x1800093b0  jmp     loc_180009450
0x1800093b5  mov     rax, qword ptr [rsp+290h+var_258]
0x1800093ba  lea     rcx, [rdi+22h]; void *
0x1800093be  mov     [rdi+8], rbx
0x1800093c2  xor     edx, edx; Val
0x1800093c4  xor     ebx, ebx
0x1800093c6  mov     [rdi+10h], rax
0x1800093ca  mov     rax, qword ptr [rsp+290h+var_258+8]
0x1800093cf  and     qword ptr [rsp+290h+var_258], rbx
0x1800093d4  and     qword ptr [rsp+290h+var_258+8], rbx
0x1800093d9  lea     r8d, [rbx+56h]; Size
0x1800093dd  mov     dword ptr [rdi], 1
0x1800093e3  mov     [rsp+290h+hObject], rbx
0x1800093e8  mov     [rdi+18h], rax
0x1800093ec  call    memset_0
0x1800093f1  mov     word ptr [rdi+20h], 58h ; 'X'
0x1800093f7  lea     rcx, [rdi+28h]; void *
0x1800093fb  xor     edx, edx; Val
0x1800093fd  mov     dword ptr [rdi+24h], 1
0x180009404  lea     r8d, [rbx+50h]; Size
0x180009408  call    memset_0
0x18000940d  lea     rcx, [rsp+290h+var_258]; this
0x180009412  mov     [r15], rdi
0x180009415  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000941a  test    r14, r14
0x18000941d  jz      short loc_180009436
0x18000941f  mov     rcx, r14; hMutex
0x180009422  call    cs:__imp_ReleaseMutex
0x180009429  nop     dword ptr [rax+rax+00h]
0x18000942e  test    eax, eax
0x180009430  jz      loc_1800094F0
0x180009436  test    rbx, rbx
0x180009439  jz      short loc_18000944E
0x18000943b  mov     rcx, rbx; hObject
0x18000943e  call    cs:__imp_CloseHandle
0x180009445  nop     dword ptr [rax+rax+00h]
0x18000944a  test    eax, eax
0x18000944c  jz      short loc_180009477
0x18000944e  xor     eax, eax
0x180009450  mov     rcx, [rbp+190h+var_30]
0x180009457  xor     rcx, rsp; StackCookie
0x18000945a  call    __security_check_cookie
0x18000945f  mov     rbx, [rsp+290h+arg_10]
0x180009467  add     rsp, 270h
0x18000946e  pop     r15
0x180009470  pop     r14
0x180009472  pop     rdi
0x180009473  pop     rsi
0x180009474  pop     rbp
0x180009475  retn
0x180009477  mov     rcx, [rbp+198h]; this
0x18000947e  mov     edx, 9CDh; void *
0x180009483  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009489  mov     rcx, [rbp+198h]; this
0x180009490  mov     edx, 9CDh; void *
0x180009495  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000949b  mov     rcx, [rbp+198h]; this
0x1800094a2  mov     edx, 9CDh; void *
0x1800094a7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800094ad  mov     rcx, [rbp+198h]; this
0x1800094b4  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800094ba  mov     rcx, [rbp+198h]; this
0x1800094c1  mov     edx, 9D7h; void *
0x1800094c6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800094cc  mov     rcx, [rbp+198h]; this
0x1800094d3  mov     edx, 9D7h; void *
0x1800094d8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800094de  mov     rcx, [rbp+198h]; this
0x1800094e5  mov     edx, 9CDh; void *
0x1800094ea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800094f0  mov     rcx, [rbp+198h]; this
0x1800094f7  mov     edx, 9D7h; void *
0x1800094fc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
