# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180027620`
- end: `0x1800279df`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `959`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18002d498`

## callees

- `0x180027108`
- `0x180027620`
- `0x18002974c`
- `0x18002ccb8`
- `0x18002f0ac`
- `0x18002fcac`
- `0x180030974`
- `0x180030a88`
- `0x180030f64`
- `0x180030f74`
- `0x180031028`
- `0x180068fe6`
- `0x180069020`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180027829`
- `KERNEL32!GetProcessHeap` at `0x180027829`
- `KERNEL32!GetCurrentProcessId` at `0x180027662`
- `KERNEL32!GetCurrentProcessId` at `0x180027662`
- `KERNEL32!CreateMutexExW` at `0x1800276a1`
- `KERNEL32!CreateMutexExW` at `0x1800276a1`
- `KERNEL32!CloseHandle` at `0x180027747`
- `KERNEL32!CloseHandle` at `0x18002787d`
- `KERNEL32!CloseHandle` at `0x180027950`
- `KERNEL32!CloseHandle` at `0x180027747`
- `KERNEL32!CloseHandle` at `0x18002787d`
- `KERNEL32!CloseHandle` at `0x180027950`
- `KERNEL32!HeapFree` at `0x180027837`
- `KERNEL32!HeapFree` at `0x180027837`
- `KERNEL32!ReleaseMutex` at `0x18002772f`
- `KERNEL32!ReleaseMutex` at `0x18002785c`
- `KERNEL32!ReleaseMutex` at `0x180027933`
- `KERNEL32!ReleaseMutex` at `0x18002772f`
- `KERNEL32!ReleaseMutex` at `0x18002785c`
- `KERNEL32!ReleaseMutex` at `0x180027933`

## pseudocode

```c
// Hidden C++ exception states: #wind=37
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        unsigned __int64 *a2)
{
  DWORD CurrentProcessId; // eax
  wil::details *v4; // rcx
  HANDLE Mutex; // rbx
  bool v7; // dl
  bool *v8; // r9
  int ValueInternal; // eax
  unsigned __int64 v10; // r8
  unsigned int v11; // edi
  unsigned int v12; // r8d
  unsigned int v13; // r8d
  unsigned int v14; // r8d
  const char *v15; // r9
  unsigned int v16; // r8d
  const char *v17; // r9
  _DWORD *v18; // rcx
  wil::details::in1diag3 *v19; // rcx
  unsigned __int64 v20; // rsi
  __int64 v21; // r8
  unsigned int v22; // r8d
  int v23; // eax
  unsigned int v24; // r8d
  HANDLE ProcessHeap; // rax
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  int v34; // [rsp+28h] [rbp-E0h]
  int v35; // [rsp+28h] [rbp-E0h]
  int v36; // [rsp+28h] [rbp-E0h]
  __int64 v37; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v38; // [rsp+40h] [rbp-C8h] BYREF
  unsigned __int64 v39; // [rsp+48h] [rbp-C0h]
  unsigned __int64 v40; // [rsp+50h] [rbp-B8h] BYREF
  HANDLE v41; // [rsp+58h] [rbp-B0h] BYREF
  HANDLE v42; // [rsp+60h] [rbp-A8h] BYREF
  __int64 *v43; // [rsp+70h] [rbp-98h]
  __int64 v44; // [rsp+78h] [rbp-90h]
  _DWORD *v45; // [rsp+80h] [rbp-88h]
  _DWORD *v46; // [rsp+88h] [rbp-80h]
  _DWORD *v47; // [rsp+90h] [rbp-78h]
  _DWORD *v48; // [rsp+98h] [rbp-70h]
  WCHAR Name[264]; // [rsp+A8h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F0h] [rbp+1E8h]

  v44 = -2;
  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  v41 = Mutex;
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v4);
  _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
    &v41,
    &v42);
  v40 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v7, &v40, v8);
  v11 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v10, (const char *)(unsigned int)ValueInternal, 120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v12, (const char *)v11, v34);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v13, (const char *)v11, v35);
    if ( v42 && !ReleaseMutex(v42) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v14, v15);
    if ( !CloseHandle(Mutex) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v16, v17);
    return v11;
  }
  v18 = (_DWORD *)(4 * v40);
  if ( 4 * v40 )
  {
    *a2 = (unsigned __int64)v18;
    ++*v18;
    goto LABEL_20;
  }
  *a2 = 0;
  v20 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v10);
  v39 = v20;
  if ( !v20 )
  {
    v11 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v21, (const char *)0x8007000ELL, 120);
    v39 = 0;
    goto LABEL_15;
  }
  v40 = (unsigned __int64)&v37;
  v37 = 0;
  v43 = &v38;
  v38 = 0;
  if ( (v20 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v19);
  v23 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)&v37,
          Name,
          v21,
          v20 >> 2);
  v11 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v24, (const char *)(unsigned int)v23, 120);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)&v37);
    v39 = 0;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)v20);
LABEL_15:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v22, (const char *)v11, v36);
    if ( v42 && !ReleaseMutex(v42) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v26, v27);
    if ( !CloseHandle(Mutex) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    return v11;
  }
  v43 = (__int64 *)v20;
  *(_DWORD *)v20 = 1;
  v40 = v20 + 8;
  *(_QWORD *)(v20 + 8) = Mutex;
  Mutex = 0;
  v41 = 0;
  v45 = (_DWORD *)(v20 + 16);
  v46 = (_DWORD *)(v20 + 16);
  *(_QWORD *)(v20 + 16) = v37;
  v37 = 0;
  v47 = (_DWORD *)(v20 + 24);
  *(_QWORD *)(v20 + 24) = v38;
  v38 = 0;
  memset_0((void *)(v20 + 34), 0, 0x56u);
  v48 = (_DWORD *)(v20 + 32);
  *(_WORD *)(v20 + 32) = 88;
  *(_DWORD *)(v20 + 36) = 1;
  memset_0((void *)(v20 + 40), 0, 0x50u);
  v39 = 0;
  *a2 = v20;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)&v37);
  v39 = 0;
LABEL_20:
  if ( v42 && !ReleaseMutex(v42) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v30, v31);
  if ( Mutex && !CloseHandle(Mutex) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
  return 0;
}

```

## disassembly

```asm
0x180027620  mov     rax, rsp
0x180027623  push    rbp
0x180027624  push    rsi
0x180027625  push    rdi
0x180027626  push    r14
0x180027628  push    r15
0x18002762a  lea     rbp, [rax-1E8h]
0x180027631  sub     rsp, 2C0h
0x180027638  mov     [rsp+2E0h+var_270], 0FFFFFFFFFFFFFFFEh
0x180027641  mov     [rax+18h], rbx
0x180027645  mov     rax, cs:__security_cookie
0x18002764c  xor     rax, rsp
0x18002764f  mov     [rbp+1E0h+var_30], rax
0x180027656  mov     r14, rdx
0x180027659  mov     rbx, rcx
0x18002765c  xor     r15d, r15d
0x18002765f  mov     [rdx], r15
0x180027662  call    cs:__imp_GetCurrentProcessId
0x180027668  mov     r9d, eax
0x18002766b  mov     [rsp+2E0h+var_2B8], rbx
0x180027670  lea     esi, [r15+78h]
0x180027674  mov     [rsp+2E0h+var_2C0], esi; int
0x180027678  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18002767f  mov     edx, 104h; unsigned __int64
0x180027684  lea     rcx, [rbp+1E0h+Name]; unsigned __int16 *
0x180027688  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002768d  mov     [rsp+2E0h+var_290], r15
0x180027692  mov     r9d, 1F0001h; dwDesiredAccess
0x180027698  xor     r8d, r8d; dwFlags
0x18002769b  lea     rdx, [rbp+1E0h+Name]; lpName
0x18002769f  xor     ecx, ecx; lpMutexAttributes
0x1800276a1  call    cs:__imp_CreateMutexExW
0x1800276a7  mov     rbx, rax
0x1800276aa  mov     [rsp+2E0h+var_290], rax
0x1800276af  test    rax, rax
0x1800276b2  jnz     short loc_1800276BF
0x1800276b4  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800276b9  nop
0x1800276ba  jmp     loc_18002795C
0x1800276bf  lea     rdx, [rsp+2E0h+var_288]
0x1800276c4  lea     rcx, [rsp+2E0h+var_290]
0x1800276c9  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800276ce  nop
0x1800276cf  mov     [rsp+2E0h+var_298], r15
0x1800276d4  lea     r8, [rsp+2E0h+var_298]; unsigned __int64 *
0x1800276d9  lea     rcx, [rbp+1E0h+Name]; unsigned __int16 *
0x1800276dd  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800276e2  mov     edi, eax
0x1800276e4  test    eax, eax
0x1800276e6  jns     short loc_18002775C
0x1800276e8  mov     rcx, [rbp+1E8h]; this
0x1800276ef  mov     r9d, eax; char *
0x1800276f2  mov     edx, 66h ; 'f'; void *
0x1800276f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800276fc  mov     rcx, [rbp+1E8h]; this
0x180027703  mov     r9d, edi; char *
0x180027706  mov     edx, 6Fh ; 'o'; void *
0x18002770b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027710  mov     rcx, [rbp+1E8h]; this
0x180027717  mov     r9d, edi; char *
0x18002771a  mov     edx, 12Eh; void *
0x18002771f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027724  nop
0x180027725  mov     rcx, [rsp+2E0h+var_288]; hMutex
0x18002772a  test    rcx, rcx
0x18002772d  jz      short loc_180027744
0x18002772f  call    cs:__imp_ReleaseMutex
0x180027735  mov     rcx, [rbp+1E8h]; this
0x18002773c  test    eax, eax
0x18002773e  jz      loc_1800279A6
0x180027744  mov     rcx, rbx; hObject
0x180027747  call    cs:__imp_CloseHandle
0x18002774d  test    eax, eax
0x18002774f  jz      loc_1800279B1
0x180027755  mov     eax, edi
0x180027757  jmp     loc_18002795C
0x18002775c  mov     rax, [rsp+2E0h+var_298]
0x180027761  lea     rcx, ds:0[rax*4]
0x180027769  test    rcx, rcx
0x18002776c  jz      short loc_18002777C
0x18002776e  mov     [r14], rcx
0x180027771  mov     eax, [rcx]
0x180027773  inc     eax
0x180027775  mov     [rcx], eax
0x180027777  jmp     loc_180027929
0x18002777c  mov     [r14], r15
0x18002777f  mov     rdx, rsi; dwBytes
0x180027782  mov     ecx, 8; dwFlags
0x180027787  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18002778c  mov     rsi, rax
0x18002778f  mov     [rsp+2E0h+var_2A0], rax
0x180027794  test    rax, rax
0x180027797  jnz     short loc_1800277BD
0x180027799  mov     rcx, [rbp+1E8h]; this
0x1800277a0  mov     edi, 8007000Eh
0x1800277a5  mov     r9d, edi; char *
0x1800277a8  mov     edx, 14Bh; void *
0x1800277ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800277b2  nop
0x1800277b3  mov     [rsp+2E0h+var_2A0], r15
0x1800277b8  jmp     loc_18002783D
0x1800277bd  lea     rax, [rsp+2E0h+var_2B0]
0x1800277c2  mov     [rsp+2E0h+var_298], rax
0x1800277c7  mov     [rsp+2E0h+var_2B0], r15
0x1800277cc  lea     rax, [rsp+2E0h+var_2A8]
0x1800277d1  mov     [rsp+2E0h+var_278], rax
0x1800277d6  mov     [rsp+2E0h+var_2A8], r15
0x1800277db  test    sil, 3
0x1800277df  jnz     loc_1800279C3
0x1800277e5  mov     r9, rsi
0x1800277e8  shr     r9, 2; unsigned __int64
0x1800277ec  lea     rdx, [rbp+1E0h+Name]; unsigned __int16 *
0x1800277f0  lea     rcx, [rsp+2E0h+var_2B0]; this
0x1800277f5  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800277fa  mov     edi, eax
0x1800277fc  test    eax, eax
0x1800277fe  jns     loc_180027890
0x180027804  mov     rcx, [rbp+1E8h]; this
0x18002780b  mov     r9d, eax; char *
0x18002780e  mov     edx, 14Eh; void *
0x180027813  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027818  nop
0x180027819  lea     rcx, [rsp+2E0h+var_2B0]; this
0x18002781e  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180027823  nop
0x180027824  mov     [rsp+2E0h+var_2A0], r15
0x180027829  call    cs:__imp_GetProcessHeap
0x18002782f  mov     rcx, rax; hHeap
0x180027832  mov     r8, rsi; lpMem
0x180027835  xor     edx, edx; dwFlags
0x180027837  call    cs:__imp_HeapFree
0x18002783d  mov     rcx, [rbp+1E8h]; this
0x180027844  mov     r9d, edi; char *
0x180027847  mov     edx, 137h; void *
0x18002784c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027851  nop
0x180027852  mov     rcx, [rsp+2E0h+var_288]; hMutex
0x180027857  test    rcx, rcx
0x18002785a  jz      short loc_180027871
0x18002785c  call    cs:__imp_ReleaseMutex
0x180027862  mov     rcx, [rbp+1E8h]; this
0x180027869  test    eax, eax
0x18002786b  jz      loc_1800279C9
0x180027871  test    rbx, rbx
0x180027874  jz      loc_180027755
0x18002787a  mov     rcx, rbx; hObject
0x18002787d  call    cs:__imp_CloseHandle
0x180027883  test    eax, eax
0x180027885  jz      loc_180027994
0x18002788b  jmp     loc_180027755
0x180027890  mov     [rsp+2E0h+var_278], rsi
0x180027895  mov     dword ptr [rsi], 1
0x18002789b  lea     rax, [rsi+8]
0x18002789f  mov     [rsp+2E0h+var_298], rax
0x1800278a4  mov     [rax], rbx
0x1800278a7  mov     rbx, r15
0x1800278aa  mov     [rsp+2E0h+var_290], rbx
0x1800278af  lea     rcx, [rsi+10h]
0x1800278b3  mov     [rsp+2E0h+var_268], rcx
0x1800278b8  mov     [rbp+1E0h+var_260], rcx
0x1800278bc  mov     rax, [rsp+2E0h+var_2B0]
0x1800278c1  mov     [rcx], rax
0x1800278c4  mov     [rsp+2E0h+var_2B0], r15
0x1800278c9  add     rcx, 8
0x1800278cd  mov     [rbp+1E0h+var_258], rcx
0x1800278d1  mov     rax, [rsp+2E0h+var_2A8]
0x1800278d6  mov     [rcx], rax
0x1800278d9  mov     [rsp+2E0h+var_2A8], r15
0x1800278de  lea     rdi, [rsi+20h]
0x1800278e2  lea     rcx, [rsi+22h]; void *
0x1800278e6  xor     edx, edx; Val
0x1800278e8  lea     r8d, [rdx+56h]; Size
0x1800278ec  call    memset_0
0x1800278f1  mov     [rbp+1E0h+var_250], rdi
0x1800278f5  mov     word ptr [rdi], 58h ; 'X'
0x1800278fa  mov     dword ptr [rdi+4], 1
0x180027901  lea     rcx, [rdi+8]; void *
0x180027905  xor     edx, edx; Val
0x180027907  lea     r8d, [rdx+50h]; Size
0x18002790b  call    memset_0
0x180027910  nop
0x180027911  mov     [rsp+2E0h+var_2A0], r15
0x180027916  mov     [r14], rsi
0x180027919  lea     rcx, [rsp+2E0h+var_2B0]; this
0x18002791e  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180027923  nop
0x180027924  mov     [rsp+2E0h+var_2A0], r15
0x180027929  mov     rcx, [rsp+2E0h+var_288]; hMutex
0x18002792e  test    rcx, rcx
0x180027931  jz      short loc_180027948
0x180027933  call    cs:__imp_ReleaseMutex
0x180027939  mov     rcx, [rbp+1E8h]; this
0x180027940  test    eax, eax
0x180027942  jz      loc_1800279D4
0x180027948  test    rbx, rbx
0x18002794b  jz      short loc_18002795A
0x18002794d  mov     rcx, rbx; hObject
0x180027950  call    cs:__imp_CloseHandle
0x180027956  test    eax, eax
0x180027958  jz      short loc_180027982
0x18002795a  xor     eax, eax
0x18002795c  mov     rcx, [rbp+1E0h+var_30]
0x180027963  xor     rcx, rsp; StackCookie
0x180027966  call    __security_check_cookie
0x18002796b  mov     rbx, [rsp+2E0h+arg_10]
0x180027973  add     rsp, 2C0h
0x18002797a  pop     r15
0x18002797c  pop     r14
0x18002797e  pop     rdi
0x18002797f  pop     rsi
0x180027980  pop     rbp
0x180027981  retn
0x180027982  mov     rcx, [rbp+1E8h]; this
0x180027989  mov     edx, 0A0Bh; void *
0x18002798e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180027994  mov     rcx, [rbp+1E8h]; this
0x18002799b  mov     edx, 0A0Bh; void *
0x1800279a0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800279a6  mov     edx, 0A15h; void *
0x1800279ab  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800279b1  mov     rcx, [rbp+1E8h]; this
0x1800279b8  mov     edx, 0A0Bh; void *
0x1800279bd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800279c3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800279c9  mov     edx, 0A15h; void *
0x1800279ce  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800279d4  mov     edx, 0A15h; void *
0x1800279d9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
