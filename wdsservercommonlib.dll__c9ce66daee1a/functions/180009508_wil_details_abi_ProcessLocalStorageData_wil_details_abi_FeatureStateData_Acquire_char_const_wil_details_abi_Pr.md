# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180009508`
- end: `0x180009913`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1035`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180009c64`

## callees

- `0x180005830`
- `0x1800089b8`
- `0x180008e94`
- `0x180009508`
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

- `KERNEL32!CloseHandle` at `0x1800095b7`
- `KERNEL32!CloseHandle` at `0x180009680`
- `KERNEL32!CloseHandle` at `0x180009790`
- `KERNEL32!CloseHandle` at `0x18000984f`
- `KERNEL32!CloseHandle` at `0x1800095b7`
- `KERNEL32!CloseHandle` at `0x180009680`
- `KERNEL32!CloseHandle` at `0x180009790`
- `KERNEL32!CloseHandle` at `0x18000984f`
- `KERNEL32!GetProcessHeap` at `0x180009738`
- `KERNEL32!GetProcessHeap` at `0x180009738`
- `KERNEL32!HeapFree` at `0x18000974c`
- `KERNEL32!HeapFree` at `0x18000974c`
- `KERNEL32!ReleaseMutex` at `0x180009660`
- `KERNEL32!ReleaseMutex` at `0x180009774`
- `KERNEL32!ReleaseMutex` at `0x180009833`
- `KERNEL32!ReleaseMutex` at `0x180009660`
- `KERNEL32!ReleaseMutex` at `0x180009774`
- `KERNEL32!ReleaseMutex` at `0x180009833`
- `KERNEL32!WaitForSingleObjectEx` at `0x1800095db`
- `KERNEL32!WaitForSingleObjectEx` at `0x1800095db`
- `KERNEL32!InitializeCriticalSectionEx` at `0x180009802`
- `KERNEL32!InitializeCriticalSectionEx` at `0x180009802`
- `KERNEL32!GetCurrentProcessId` at `0x18000953e`
- `KERNEL32!GetCurrentProcessId` at `0x18000953e`
- `KERNEL32!CreateMutexExW` at `0x180009585`
- `KERNEL32!CreateMutexExW` at `0x180009585`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
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
  char *v24; // rax
  unsigned int v25; // r8d
  char *v26; // rdi
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
  unsigned int v37; // r8d
  const char *v38; // r9
  unsigned int v39; // r8d
  const char *v40; // r9
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  int v43; // [rsp+20h] [rbp-E0h]
  HANDLE hObject; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v45; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v46; // [rsp+48h] [rbp-B8h] BYREF
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
  v46 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v10, &v46, (bool *)v12);
  v7 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x64, v15, (const char *)(unsigned int)ValueInternal, 304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6D, v16, (const char *)v7, v41);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12B, v17, (const char *)v7, v42);
    if ( v13 && !ReleaseMutex(v13) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D7, v18, v19);
    if ( v6 )
    {
      if ( !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v20, v21);
    }
    return v7;
  }
  v22 = (_DWORD *)(4 * v46);
  if ( 4 * v46 )
  {
    *a2 = v22;
    v23 = hObject;
    *(_DWORD *)*a2 = *v22 + 1;
    goto LABEL_26;
  }
  *a2 = 0;
  v24 = (char *)wil::details::ProcessHeapAlloc(8u, 0x130u, v15);
  v26 = v24;
  if ( v24 )
  {
    v45 = 0;
    v29 = wil::details_abi::SemaphoreValue::CreateFromPointer(
            (wil::details_abi::SemaphoreValue *)&v45,
            (char *)Name,
            (unsigned __int64)v24);
    v27 = v29;
    if ( v29 >= 0 )
    {
      *((_QWORD *)v26 + 2) = v45;
      v36 = *((_QWORD *)&v45 + 1);
      *((_QWORD *)v26 + 1) = v6;
      v23 = 0;
      v45 = 0u;
      *((_QWORD *)v26 + 3) = v36;
      *(_DWORD *)v26 = 1;
      memset_0(v26 + 40, 0, 0x108u);
      *((_QWORD *)v26 + 4) = 0;
      wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v26 + 40));
      InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v26 + 232), 0, 0);
      *((_QWORD *)v26 + 34) = 0;
      *((_QWORD *)v26 + 35) = 0;
      *((_QWORD *)v26 + 36) = 0;
      *((_QWORD *)v26 + 37) = 0;
      *a2 = v26;
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)&v45);
LABEL_26:
      if ( v13 && !ReleaseMutex(v13) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D7, v37, v38);
      if ( v23 && !CloseHandle(v23) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v39, v40);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v30, (const char *)(unsigned int)v29, 304);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)&v45);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v26);
  }
  else
  {
    v27 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x148, v25, (const char *)0x8007000ELL, 304);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x134, v28, (const char *)v27, v43);
  if ( v13 && !ReleaseMutex(v13) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D7, v32, v33);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v34, v35);
  return v27;
}

```

## disassembly

```asm
0x180009508  mov     [rsp-8+arg_10], rbx
0x18000950d  push    rbp
0x18000950e  push    rsi
0x18000950f  push    rdi
0x180009510  push    r14
0x180009512  push    r15
0x180009514  lea     rbp, [rsp-170h]
0x18000951c  sub     rsp, 270h
0x180009523  mov     rax, cs:__security_cookie
0x18000952a  xor     rax, rsp
0x18000952d  mov     [rbp+190h+var_30], rax
0x180009534  and     qword ptr [rdx], 0
0x180009538  mov     r15, rdx
0x18000953b  mov     rbx, rcx
0x18000953e  call    cs:__imp_GetCurrentProcessId
0x180009545  nop     dword ptr [rax+rax+00h]
0x18000954a  mov     esi, 130h
0x18000954f  mov     [rsp+290h+var_268], rbx
0x180009554  mov     r9d, eax
0x180009557  mov     [rsp+290h+var_270], esi; int
0x18000955b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180009562  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x180009567  lea     edx, [rsi-2Ch]; unsigned __int64
0x18000956a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000956f  and     [rsp+290h+hObject], 0
0x180009575  lea     rdx, [rsp+290h+Name]; lpName
0x18000957a  mov     r9d, 1F0001h; dwDesiredAccess
0x180009580  xor     r8d, r8d; dwFlags
0x180009583  xor     ecx, ecx; lpMutexAttributes
0x180009585  call    cs:__imp_CreateMutexExW
0x18000958c  nop     dword ptr [rax+rax+00h]
0x180009591  mov     rdx, rax
0x180009594  lea     rcx, [rsp+290h+hObject]
0x180009599  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000959e  mov     rbx, [rsp+290h+hObject]
0x1800095a3  test    rbx, rbx
0x1800095a6  jnz     short loc_1800095D2
0x1800095a8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800095ad  mov     edi, eax
0x1800095af  test    rbx, rbx
0x1800095b2  jz      short loc_1800095CB
0x1800095b4  mov     rcx, rbx; hObject
0x1800095b7  call    cs:__imp_CloseHandle
0x1800095be  nop     dword ptr [rax+rax+00h]
0x1800095c3  test    eax, eax
0x1800095c5  jz      loc_1800098AC
0x1800095cb  mov     eax, edi
0x1800095cd  jmp     loc_180009861
0x1800095d2  xor     r8d, r8d; bAlertable
0x1800095d5  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800095d8  mov     rcx, rbx; hHandle
0x1800095db  call    cs:__imp_WaitForSingleObjectEx
0x1800095e2  nop     dword ptr [rax+rax+00h]
0x1800095e7  cmp     eax, 102h
0x1800095ec  jz      short loc_1800095FE
0x1800095ee  test    eax, 0FFFFFF7Fh
0x1800095f3  jnz     loc_1800098BE
0x1800095f9  mov     r14, rbx
0x1800095fc  jmp     short loc_180009601
0x1800095fe  xor     r14d, r14d
0x180009601  and     [rsp+290h+var_248], 0
0x180009607  lea     r8, [rsp+290h+var_248]; unsigned __int64 *
0x18000960c  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x180009611  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180009616  mov     edi, eax
0x180009618  test    eax, eax
0x18000961a  jns     short loc_180009699
0x18000961c  mov     rcx, [rbp+198h]; this
0x180009623  mov     r9d, eax; char *
0x180009626  mov     edx, 64h ; 'd'; void *
0x18000962b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009630  mov     rcx, [rbp+198h]; this
0x180009637  mov     r9d, edi; char *
0x18000963a  mov     edx, 6Dh ; 'm'; void *
0x18000963f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009644  mov     rcx, [rbp+198h]; this
0x18000964b  mov     r9d, edi; char *
0x18000964e  mov     edx, 12Bh; void *
0x180009653  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009658  test    r14, r14
0x18000965b  jz      short loc_180009674
0x18000965d  mov     rcx, r14; hMutex
0x180009660  call    cs:__imp_ReleaseMutex
0x180009667  nop     dword ptr [rax+rax+00h]
0x18000966c  test    eax, eax
0x18000966e  jz      loc_1800098CB
0x180009674  test    rbx, rbx
0x180009677  jz      loc_1800095CB
0x18000967d  mov     rcx, rbx; hObject
0x180009680  call    cs:__imp_CloseHandle
0x180009687  nop     dword ptr [rax+rax+00h]
0x18000968c  test    eax, eax
0x18000968e  jz      loc_18000989A
0x180009694  jmp     loc_1800095CB
0x180009699  mov     rax, [rsp+290h+var_248]
0x18000969e  lea     rcx, ds:0[rax*4]
0x1800096a6  test    rcx, rcx
0x1800096a9  jz      short loc_1800096C1
0x1800096ab  mov     [r15], rcx
0x1800096ae  mov     ecx, [rcx]
0x1800096b0  mov     rax, [r15]
0x1800096b3  inc     ecx
0x1800096b5  mov     rbx, [rsp+290h+hObject]
0x1800096ba  mov     [rax], ecx
0x1800096bc  jmp     loc_18000982B
0x1800096c1  and     qword ptr [r15], 0
0x1800096c5  mov     rdx, rsi; dwBytes
0x1800096c8  mov     ecx, 8; dwFlags
0x1800096cd  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800096d2  mov     rdi, rax
0x1800096d5  test    rax, rax
0x1800096d8  jnz     short loc_1800096F5
0x1800096da  mov     rcx, [rbp+198h]; this
0x1800096e1  mov     esi, 8007000Eh
0x1800096e6  mov     r9d, esi; char *
0x1800096e9  mov     edx, 148h; void *
0x1800096ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800096f3  jmp     short loc_180009758
0x1800096f5  xorps   xmm0, xmm0
0x1800096f8  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x1800096fd  mov     r8, rdi; void *
0x180009700  lea     rcx, [rsp+290h+var_258]; this
0x180009705  movdqu  [rsp+290h+var_258], xmm0
0x18000970b  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x180009710  mov     esi, eax
0x180009712  test    eax, eax
0x180009714  jns     loc_1800097AB
0x18000971a  mov     rcx, [rbp+198h]; this
0x180009721  mov     r9d, eax; char *
0x180009724  mov     edx, 14Bh; void *
0x180009729  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000972e  lea     rcx, [rsp+290h+var_258]; this
0x180009733  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180009738  call    cs:__imp_GetProcessHeap
0x18000973f  nop     dword ptr [rax+rax+00h]
0x180009744  mov     r8, rdi; lpMem
0x180009747  xor     edx, edx; dwFlags
0x180009749  mov     rcx, rax; hHeap
0x18000974c  call    cs:__imp_HeapFree
0x180009753  nop     dword ptr [rax+rax+00h]
0x180009758  mov     rcx, [rbp+198h]; this
0x18000975f  mov     r9d, esi; char *
0x180009762  mov     edx, 134h; void *
0x180009767  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000976c  test    r14, r14
0x18000976f  jz      short loc_180009788
0x180009771  mov     rcx, r14; hMutex
0x180009774  call    cs:__imp_ReleaseMutex
0x18000977b  nop     dword ptr [rax+rax+00h]
0x180009780  test    eax, eax
0x180009782  jz      loc_1800098DD
0x180009788  test    rbx, rbx
0x18000978b  jz      short loc_1800097A4
0x18000978d  mov     rcx, rbx; hObject
0x180009790  call    cs:__imp_CloseHandle
0x180009797  nop     dword ptr [rax+rax+00h]
0x18000979c  test    eax, eax
0x18000979e  jz      loc_1800098EF
0x1800097a4  mov     eax, esi
0x1800097a6  jmp     loc_180009861
0x1800097ab  mov     rax, qword ptr [rsp+290h+var_258]
0x1800097b0  lea     rcx, [rdi+28h]; void *
0x1800097b4  mov     [rdi+10h], rax
0x1800097b8  xor     edx, edx; Val
0x1800097ba  mov     rax, qword ptr [rsp+290h+var_258+8]
0x1800097bf  mov     r8d, 108h; Size
0x1800097c5  mov     [rdi+8], rbx
0x1800097c9  xor     ebx, ebx
0x1800097cb  and     qword ptr [rsp+290h+var_258], rbx
0x1800097d0  and     qword ptr [rsp+290h+var_258+8], rbx
0x1800097d5  mov     [rdi+18h], rax
0x1800097d9  mov     dword ptr [rdi], 1
0x1800097df  call    memset_0
0x1800097e4  xor     eax, eax
0x1800097e6  lea     rcx, [rdi+28h]; this
0x1800097ea  mov     [rdi+20h], rax
0x1800097ee  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800097f3  lea     rsi, [rdi+0E8h]
0x1800097fa  xor     r8d, r8d; Flags
0x1800097fd  mov     rcx, rsi; lpCriticalSection
0x180009800  xor     edx, edx; dwSpinCount
0x180009802  call    cs:__imp_InitializeCriticalSectionEx
0x180009809  nop     dword ptr [rax+rax+00h]
0x18000980e  and     [rsi+28h], rbx
0x180009812  lea     rcx, [rsp+290h+var_258]; this
0x180009817  and     [rsi+30h], rbx
0x18000981b  and     [rsi+38h], rbx
0x18000981f  and     [rsi+40h], rbx
0x180009823  mov     [r15], rdi
0x180009826  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000982b  test    r14, r14
0x18000982e  jz      short loc_180009847
0x180009830  mov     rcx, r14; hMutex
0x180009833  call    cs:__imp_ReleaseMutex
0x18000983a  nop     dword ptr [rax+rax+00h]
0x18000983f  test    eax, eax
0x180009841  jz      loc_180009901
0x180009847  test    rbx, rbx
0x18000984a  jz      short loc_18000985F
0x18000984c  mov     rcx, rbx; hObject
0x18000984f  call    cs:__imp_CloseHandle
0x180009856  nop     dword ptr [rax+rax+00h]
0x18000985b  test    eax, eax
0x18000985d  jz      short loc_180009888
0x18000985f  xor     eax, eax
0x180009861  mov     rcx, [rbp+190h+var_30]
0x180009868  xor     rcx, rsp; StackCookie
0x18000986b  call    __security_check_cookie
0x180009870  mov     rbx, [rsp+290h+arg_10]
0x180009878  add     rsp, 270h
0x18000987f  pop     r15
0x180009881  pop     r14
0x180009883  pop     rdi
0x180009884  pop     rsi
0x180009885  pop     rbp
0x180009886  retn
0x180009888  mov     rcx, [rbp+198h]; this
0x18000988f  mov     edx, 9CDh; void *
0x180009894  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000989a  mov     rcx, [rbp+198h]; this
0x1800098a1  mov     edx, 9CDh; void *
0x1800098a6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800098ac  mov     rcx, [rbp+198h]; this
0x1800098b3  mov     edx, 9CDh; void *
0x1800098b8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800098be  mov     rcx, [rbp+198h]; this
0x1800098c5  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800098cb  mov     rcx, [rbp+198h]; this
0x1800098d2  mov     edx, 9D7h; void *
0x1800098d7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800098dd  mov     rcx, [rbp+198h]; this
0x1800098e4  mov     edx, 9D7h; void *
0x1800098e9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800098ef  mov     rcx, [rbp+198h]; this
0x1800098f6  mov     edx, 9CDh; void *
0x1800098fb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009901  mov     rcx, [rbp+198h]; this
0x180009908  mov     edx, 9D7h; void *
0x18000990d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
