# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18001ffec`
- end: `0x1800201c4`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `472`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001ff34`

## callees

- `0x18001ffec`
- `0x1800201cc`
- `0x18002c9e8`
- `0x18002cda4`
- `0x18003d68c`
- `0x18003db78`
- `0x18003ec1c`
- `0x18003ecfc`
- `0x18003ed18`
- `0x18004a53c`
- `0x18004b3b4`
- `0x180050db0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180020027`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180020027`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180020089`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180020089`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180020063`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180020063`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  wil::details *Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rbx
  DWORD v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  wil::details *v12; // rsi
  int ValueInternal; // eax
  void *v14; // rdx
  unsigned int v15; // edi
  unsigned __int64 v16; // r9
  __int64 v17; // rdx
  _DWORD *v18; // rcx
  int v19; // eax
  int v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+20h] [rbp-E0h]
  wil::details *v22; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v23; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v24; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v20 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v22 = Mutex;
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
  v24 = v12;
  v23 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (__int64)v9, &v23, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v21);
    v16 = v15;
    v17 = 302;
LABEL_14:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)v17, (unsigned int)"wil", (const char *)v16, v20);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v24);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v22);
    return v15;
  }
  v18 = (_DWORD *)(4 * v23);
  if ( 4 * v23 )
  {
    *a2 = v18;
    ++*v18;
  }
  else
  {
    v19 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
    v15 = v19;
    if ( v19 < 0 )
    {
      v16 = (unsigned int)v19;
      v17 = 311;
      goto LABEL_14;
    }
    v6 = v22;
  }
  if ( v12 )
    wil::details::ReleaseMutex(v12, v14);
  if ( v6 )
    wil::details::CloseHandle(v6, v14);
  return 0;
}

```

## disassembly

```asm
0x18001ffec  mov     [rsp-8+arg_10], rbx
0x18001fff1  mov     [rsp-8+arg_18], rsi
0x18001fff6  push    rbp
0x18001fff7  push    rdi
0x18001fff8  push    r14
0x18001fffa  lea     rbp, [rsp-170h]
0x180020002  sub     rsp, 270h
0x180020009  mov     rax, cs:__security_cookie
0x180020010  xor     rax, rsp
0x180020013  mov     [rbp+180h+var_20], rax
0x18002001a  mov     r14, rdx
0x18002001d  mov     qword ptr [rdx], 0
0x180020024  mov     rbx, rcx
0x180020027  call    cs:__imp_GetCurrentProcessId
0x18002002d  mov     [rsp+280h+var_258], rbx
0x180020032  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180020039  mov     r9d, eax
0x18002003c  mov     [rsp+280h+var_260], 78h ; 'x'; int
0x180020044  mov     edx, 104h; unsigned __int64
0x180020049  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18002004e  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180020053  mov     r9d, 1F0001h; dwDesiredAccess
0x180020059  lea     rdx, [rsp+280h+Name]; lpName
0x18002005e  xor     r8d, r8d; dwFlags
0x180020061  xor     ecx, ecx; lpMutexAttributes
0x180020063  call    cs:__imp_CreateMutexExW
0x180020069  mov     [rsp+280h+var_250], rax
0x18002006e  mov     rbx, rax
0x180020071  test    rax, rax
0x180020074  jnz     short loc_180020080
0x180020076  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002007b  jmp     loc_18002019D
0x180020080  xor     r8d, r8d; bAlertable
0x180020083  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180020086  mov     rcx, rbx; hHandle
0x180020089  call    cs:__imp_WaitForSingleObjectEx
0x18002008f  cmp     eax, 102h
0x180020094  jz      short loc_1800200AF
0x180020096  test    eax, 0FFFFFF7Fh
0x18002009b  jz      short loc_1800200AA
0x18002009d  mov     rcx, [rbp+188h]; this
0x1800200a4  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800200aa  mov     rsi, rbx
0x1800200ad  jmp     short loc_1800200B1
0x1800200af  xor     esi, esi
0x1800200b1  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x1800200b6  mov     [rsp+280h+var_240], rsi
0x1800200bb  lea     rcx, [rsp+280h+Name]; wchar_t *
0x1800200c0  mov     [rsp+280h+var_248], 0
0x1800200c9  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x1800200ce  mov     edi, eax
0x1800200d0  test    eax, eax
0x1800200d2  jns     short loc_180020114
0x1800200d4  mov     rcx, [rbp+188h]; this
0x1800200db  lea     r8, aWil; "wil"
0x1800200e2  mov     r9d, eax; char *
0x1800200e5  mov     edx, 66h ; 'f'; void *
0x1800200ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800200ef  mov     rcx, [rbp+188h]; this
0x1800200f6  lea     r8, aWil; "wil"
0x1800200fd  mov     r9d, edi; char *
0x180020100  mov     edx, 6Fh ; 'o'; void *
0x180020105  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002010a  mov     r9d, edi
0x18002010d  mov     edx, 12Eh
0x180020112  jmp     short loc_180020151
0x180020114  mov     rax, [rsp+280h+var_248]
0x180020119  lea     rcx, ds:0[rax*4]
0x180020121  test    rcx, rcx
0x180020124  jz      short loc_180020131
0x180020126  mov     [r14], rcx
0x180020129  mov     eax, [rcx]
0x18002012b  inc     eax
0x18002012d  mov     [rcx], eax
0x18002012f  jmp     short loc_180020181
0x180020131  mov     r8, r14
0x180020134  lea     rdx, [rsp+280h+var_250]
0x180020139  lea     rcx, [rsp+280h+Name]
0x18002013e  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180020143  mov     edi, eax
0x180020145  test    eax, eax
0x180020147  jns     short loc_18002017C
0x180020149  mov     r9d, eax; char *
0x18002014c  mov     edx, 137h; void *
0x180020151  mov     rcx, [rbp+188h]; this
0x180020158  lea     r8, aWil; "wil"
0x18002015f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020164  lea     rcx, [rsp+280h+var_240]
0x180020169  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002016e  lea     rcx, [rsp+280h+var_250]
0x180020173  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180020178  mov     eax, edi
0x18002017a  jmp     short loc_18002019D
0x18002017c  mov     rbx, [rsp+280h+var_250]
0x180020181  test    rsi, rsi
0x180020184  jz      short loc_18002018E
0x180020186  mov     rcx, rsi; this
0x180020189  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18002018e  test    rbx, rbx
0x180020191  jz      short loc_18002019B
0x180020193  mov     rcx, rbx; this
0x180020196  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18002019b  xor     eax, eax
0x18002019d  mov     rcx, [rbp+180h+var_20]
0x1800201a4  xor     rcx, rsp; StackCookie
0x1800201a7  call    __security_check_cookie
0x1800201ac  lea     r11, [rsp+280h+var_10]
0x1800201b4  mov     rbx, [r11+30h]
0x1800201b8  mov     rsi, [r11+38h]
0x1800201bc  mov     rsp, r11
0x1800201bf  pop     r14
0x1800201c1  pop     rdi
0x1800201c2  pop     rbp
0x1800201c3  retn
```
