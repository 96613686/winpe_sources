# wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData>::GetShared(void)

- ea: `0x14000b830`
- end: `0x14000bb79`
- name: `?GetShared@?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUProcessLocalData@23@XZ`
- size: `841`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config`

## callers

- `0x14000b6e4`

## callees

- `0x14000aa04`
- `0x14000aa60`
- `0x14000af14`
- `0x14000af44`
- `0x14000b830`
- `0x14000d4e0`
- `0x140028554`
- `0x14003c8b0`
- `0x14003f384`
- `0x140049e34`
- `0x140053720`
- `0x1400544e0`
- `0x140057638`
- `0x1400587c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14000b95f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14000b95f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x14000b8cc`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x14000b8cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000baef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000baef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000bae1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000bae1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000b890`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000b890`

## pseudocode

```c
__int64 wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData>::GetShared()
{
  __int64 v0; // rbx
  __int64 v1; // rdx
  __int64 result; // rax
  DWORD CurrentProcessId; // eax
  wil::details *Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rbp
  int LastErrorFailHr; // esi
  void *v8; // rdx
  _DWORD *v9; // rdi
  DWORD v10; // eax
  void *v11; // rdx
  unsigned int v12; // r8d
  char *v13; // r9
  wil::details *v14; // r14
  int ValueInternal; // eax
  void *v16; // rdx
  unsigned __int64 v17; // r8
  unsigned int v18; // edi
  void *v19; // rdx
  unsigned __int64 v20; // rax
  wil::details::in1diag3 *v21; // rcx
  bool v22; // r8
  int v23; // eax
  HANDLE ProcessHeap; // rax
  unsigned __int64 v25; // rax
  int v26; // [rsp+20h] [rbp-278h]
  int v27; // [rsp+20h] [rbp-278h]
  int v28; // [rsp+20h] [rbp-278h]
  unsigned __int64 v29[2]; // [rsp+30h] [rbp-268h] BYREF
  _QWORD v30[2]; // [rsp+40h] [rbp-258h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+0h]

  v0 = wil::details_abi::g_pProcessLocalData;
  if ( *(_QWORD *)(wil::details_abi::g_pProcessLocalData + 8) )
    goto LABEL_2;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v30[0] = Mutex;
  v6 = Mutex;
  if ( !Mutex )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
    goto LABEL_11;
  }
  v10 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v10 == 258 )
  {
    v14 = 0;
  }
  else
  {
    if ( (v10 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v11, v12, v13);
    v14 = v6;
  }
  v29[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v11, v29, (bool *)v13);
  v18 = ValueInternal;
  if ( ValueInternal >= 0 )
  {
    v9 = (_DWORD *)(4 * v29[0]);
    if ( 4 * v29[0] )
    {
      ++*v9;
    }
    else
    {
      v20 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v17);
      v9 = (_DWORD *)v20;
      if ( !v20 )
      {
        LastErrorFailHr = -2147024882;
        wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
LABEL_8:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x137,
          (unsigned int)"wil",
          (const char *)(unsigned int)LastErrorFailHr,
          v26);
        if ( v14 )
          wil::details::ReleaseMutex(v14, v8);
        wil::details::CloseHandle(v6, v8);
LABEL_11:
        v9 = 0;
        if ( LastErrorFailHr < 0 )
          goto LABEL_2;
        goto LABEL_12;
      }
      *(_OWORD *)v29 = 0;
      if ( (v20 & 3) != 0 )
        wil::details::in1diag3::_FailFastImmediate_Unexpected(v21);
      v23 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
              (wil::details_abi::SemaphoreValue *)v29,
              Name,
              v22,
              v20 >> 2);
      LastErrorFailHr = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x14E,
          (unsigned int)"wil",
          (const char *)(unsigned int)v23,
          120);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v29[1]);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v29);
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v9);
        goto LABEL_8;
      }
      v25 = v29[0];
      *v9 = 1;
      *((_QWORD *)v9 + 1) = v6;
      *((_QWORD *)v9 + 2) = v25;
      *((_QWORD *)v9 + 3) = v29[1];
      v30[0] = 0;
      v29[0] = 0;
      v29[1] = 0;
      memset_0((char *)v9 + 34, 0, 0x56u);
      *((_WORD *)v9 + 16) = 88;
      v9[9] = 1;
      memset_0(v9 + 10, 0, 0x50u);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v29[1]);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v29);
    }
    if ( v14 )
      wil::details::ReleaseMutex(v14, v16);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v30);
LABEL_12:
    if ( !*(_QWORD *)(v0 + 8) )
      *(_QWORD *)(v0 + 8) = v9;
    goto LABEL_2;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x66,
    (unsigned int)"wil",
    (const char *)(unsigned int)ValueInternal,
    120);
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v18, v27);
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v18, v28);
  if ( v14 )
    wil::details::ReleaseMutex(v14, v19);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v30);
LABEL_2:
  v1 = *(_QWORD *)(v0 + 8);
  result = v1 + 32;
  if ( !v1 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x14000b830  push    rbx
0x14000b832  push    rbp
0x14000b833  push    rsi
0x14000b834  push    rdi
0x14000b835  push    r14
0x14000b837  sub     rsp, 270h
0x14000b83e  mov     rax, cs:__security_cookie
0x14000b845  xor     rax, rsp
0x14000b848  mov     [rsp+298h+var_38], rax
0x14000b850  mov     rbx, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x14000b857  cmp     qword ptr [rbx+8], 0
0x14000b85c  jz      short loc_14000B88D
0x14000b85e  mov     rdx, [rbx+8]
0x14000b862  xor     ecx, ecx
0x14000b864  test    rdx, rdx
0x14000b867  lea     rax, [rdx+20h]
0x14000b86b  cmovz   rax, rcx
0x14000b86f  mov     rcx, [rsp+298h+var_38]
0x14000b877  xor     rcx, rsp; StackCookie
0x14000b87a  call    __security_check_cookie
0x14000b87f  add     rsp, 270h
0x14000b886  pop     r14
0x14000b888  pop     rdi
0x14000b889  pop     rsi
0x14000b88a  pop     rbp
0x14000b88b  pop     rbx
0x14000b88c  retn
0x14000b88d  mov     rdi, [rbx]
0x14000b890  call    cs:__imp_GetCurrentProcessId
0x14000b896  mov     [rsp+298h+var_270], rdi
0x14000b89b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x14000b8a2  mov     r9d, eax
0x14000b8a5  mov     [rsp+298h+var_278], 78h ; 'x'; int
0x14000b8ad  mov     edx, 104h; unsigned __int64
0x14000b8b2  lea     rcx, [rsp+298h+Name]; unsigned __int16 *
0x14000b8b7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000b8bc  mov     r9d, 1F0001h; dwDesiredAccess
0x14000b8c2  lea     rdx, [rsp+298h+Name]; lpName
0x14000b8c7  xor     r8d, r8d; dwFlags
0x14000b8ca  xor     ecx, ecx; lpMutexAttributes
0x14000b8cc  call    cs:__imp_CreateMutexExW
0x14000b8d2  mov     [rsp+298h+var_258], rax
0x14000b8d7  mov     rbp, rax
0x14000b8da  test    rax, rax
0x14000b8dd  jnz     short loc_14000B954
0x14000b8df  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000b8e4  mov     esi, eax
0x14000b8e6  jmp     short loc_14000B936
0x14000b8e8  mov     rcx, [rsp+298h]; this
0x14000b8f0  lea     r8, aWil; "wil"
0x14000b8f7  mov     esi, 8007000Eh
0x14000b8fc  mov     edx, 14Bh; void *
0x14000b901  mov     r9d, esi; char *
0x14000b904  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b909  mov     rcx, [rsp+298h]; this
0x14000b911  lea     r8, aWil; "wil"
0x14000b918  mov     r9d, esi; char *
0x14000b91b  mov     edx, 137h; void *
0x14000b920  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b925  test    r14, r14
0x14000b928  jnz     loc_14000BA14
0x14000b92e  mov     rcx, rbp; this
0x14000b931  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x14000b936  xor     edi, edi
0x14000b938  test    esi, esi
0x14000b93a  js      loc_14000B85E
0x14000b940  cmp     qword ptr [rbx+8], 0
0x14000b945  jnz     loc_14000B85E
0x14000b94b  mov     [rbx+8], rdi
0x14000b94f  jmp     loc_14000B85E
0x14000b954  xor     r8d, r8d; bAlertable
0x14000b957  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x14000b95c  mov     rcx, rbp; hHandle
0x14000b95f  call    cs:__imp_WaitForSingleObjectEx
0x14000b965  cmp     eax, 102h
0x14000b96a  jnz     loc_14000BA05
0x14000b970  xor     r14d, r14d
0x14000b973  lea     r8, [rsp+298h+var_268]; unsigned __int64 *
0x14000b978  mov     [rsp+298h+var_268], 0
0x14000b981  lea     rcx, [rsp+298h+Name]; unsigned __int16 *
0x14000b986  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x14000b98b  mov     edi, eax
0x14000b98d  test    eax, eax
0x14000b98f  jns     loc_14000BA21
0x14000b995  mov     rcx, [rsp+298h]; this
0x14000b99d  lea     r8, aWil; "wil"
0x14000b9a4  mov     r9d, eax; char *
0x14000b9a7  mov     edx, 66h ; 'f'; void *
0x14000b9ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b9b1  mov     rcx, [rsp+298h]; this
0x14000b9b9  lea     r8, aWil; "wil"
0x14000b9c0  mov     r9d, edi; char *
0x14000b9c3  mov     edx, 6Fh ; 'o'; void *
0x14000b9c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b9cd  mov     rcx, [rsp+298h]; this
0x14000b9d5  lea     r8, aWil; "wil"
0x14000b9dc  mov     r9d, edi; char *
0x14000b9df  mov     edx, 12Eh; void *
0x14000b9e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b9e9  test    r14, r14
0x14000b9ec  jz      short loc_14000B9F6
0x14000b9ee  mov     rcx, r14; this
0x14000b9f1  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x14000b9f6  lea     rcx, [rsp+298h+var_258]
0x14000b9fb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000ba00  jmp     loc_14000B85E
0x14000ba05  test    eax, 0FFFFFF7Fh
0x14000ba0a  jnz     short loc_14000BA7F
0x14000ba0c  mov     r14, rbp
0x14000ba0f  jmp     loc_14000B973
0x14000ba14  mov     rcx, r14; this
0x14000ba17  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x14000ba1c  jmp     loc_14000B92E
0x14000ba21  mov     rax, [rsp+298h+var_268]
0x14000ba26  lea     rdi, ds:0[rax*4]
0x14000ba2e  test    rdi, rdi
0x14000ba31  jnz     short loc_14000BA8D
0x14000ba33  mov     edx, 78h ; 'x'; dwBytes
0x14000ba38  mov     ecx, 8; dwFlags
0x14000ba3d  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000ba42  mov     rdi, rax
0x14000ba45  test    rax, rax
0x14000ba48  jz      loc_14000B8E8
0x14000ba4e  xorps   xmm0, xmm0
0x14000ba51  movdqu  xmmword ptr [rsp+298h+var_268], xmm0
0x14000ba57  test    dil, 3
0x14000ba5b  jz      short loc_14000BA95
0x14000ba5d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000ba63  test    r14, r14
0x14000ba66  jz      short loc_14000BA70
0x14000ba68  mov     rcx, r14; this
0x14000ba6b  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x14000ba70  lea     rcx, [rsp+298h+var_258]
0x14000ba75  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000ba7a  jmp     loc_14000B940
0x14000ba7f  mov     rcx, [rsp+298h]; this
0x14000ba87  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x14000ba8d  mov     eax, [rdi]
0x14000ba8f  inc     eax
0x14000ba91  mov     [rdi], eax
0x14000ba93  jmp     short loc_14000BA63
0x14000ba95  mov     r9, rdi
0x14000ba98  lea     rdx, [rsp+298h+Name]; unsigned __int16 *
0x14000ba9d  shr     r9, 2; unsigned __int64
0x14000baa1  lea     rcx, [rsp+298h+var_268]; this
0x14000baa6  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x14000baab  mov     esi, eax
0x14000baad  test    eax, eax
0x14000baaf  jns     short loc_14000BAFA
0x14000bab1  mov     rcx, [rsp+298h]; this
0x14000bab9  lea     r8, aWil; "wil"
0x14000bac0  mov     r9d, eax; char *
0x14000bac3  mov     edx, 14Eh; void *
0x14000bac8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000bacd  lea     rcx, [rsp+298h+var_268+8]
0x14000bad2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000bad7  lea     rcx, [rsp+298h+var_268]
0x14000badc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000bae1  call    cs:__imp_GetProcessHeap
0x14000bae7  mov     r8, rdi; lpMem
0x14000baea  xor     edx, edx; dwFlags
0x14000baec  mov     rcx, rax; hHeap
0x14000baef  call    cs:__imp_HeapFree
0x14000baf5  jmp     loc_14000B909
0x14000bafa  mov     rax, [rsp+298h+var_268]
0x14000baff  lea     rcx, [rdi+22h]; void *
0x14000bb03  mov     dword ptr [rdi], 1
0x14000bb09  xor     edx, edx; Val
0x14000bb0b  mov     [rdi+8], rbp
0x14000bb0f  mov     r8d, 56h ; 'V'; Size
0x14000bb15  mov     [rdi+10h], rax
0x14000bb19  mov     rax, [rsp+298h+var_268+8]
0x14000bb1e  mov     [rdi+18h], rax
0x14000bb22  mov     [rsp+298h+var_258], 0
0x14000bb2b  mov     [rsp+298h+var_268], 0
0x14000bb34  mov     [rsp+298h+var_268+8], 0
0x14000bb3d  call    memset_0
0x14000bb42  mov     word ptr [rdi+20h], 58h ; 'X'
0x14000bb48  lea     rcx, [rdi+28h]; void *
0x14000bb4c  xor     edx, edx; Val
0x14000bb4e  mov     dword ptr [rdi+24h], 1
0x14000bb55  mov     r8d, 50h ; 'P'; Size
0x14000bb5b  call    memset_0
0x14000bb60  lea     rcx, [rsp+298h+var_268+8]
0x14000bb65  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000bb6a  lea     rcx, [rsp+298h+var_268]
0x14000bb6f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000bb74  jmp     loc_14000BA63
```
