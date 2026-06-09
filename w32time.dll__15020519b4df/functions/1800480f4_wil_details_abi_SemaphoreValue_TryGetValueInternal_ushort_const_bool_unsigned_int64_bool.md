# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800480f4`
- end: `0x1800482c7`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `467`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180048070`

## callees

- `0x180001680`
- `0x18000bde0`
- `0x18003d270`
- `0x180041818`
- `0x180043230`
- `0x180045a9c`
- `0x180045abc`
- `0x1800480f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18004815d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180048205`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18004815d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180048205`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048173`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048173`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  wil::details *v5; // rax
  void *v6; // rdx
  unsigned int v7; // r8d
  const char *v8; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  wil::details *v11; // rax
  unsigned int v12; // r8d
  const char *v13; // r9
  void *v14; // rdx
  int v15; // eax
  void *v16; // rdx
  void *v17; // rdx
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v21; // [rsp+28h] [rbp-D8h] BYREF
  wil::details *v22; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v22 = v5;
  if ( v5 )
  {
    v20 = 0;
    v19 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v20);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v19);
      goto LABEL_12;
    }
    StringCchCatW(Name, 0x104u, L"h");
    v11 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
    v21 = v11;
    if ( !v11 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v12, v13);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
        &v21,
        v14);
      goto LABEL_12;
    }
    v15 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v11, &v19);
    LastError = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v15,
        v19);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
        &v21,
        v17);
      goto LABEL_12;
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v21,
      v16);
    *a3 = v20 | (unsigned __int64)((__int64)v19 << 31);
LABEL_11:
    LastError = 0;
    goto LABEL_12;
  }
  if ( GetLastError() == 2 )
    goto LABEL_11;
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v7, v8);
LABEL_12:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v22,
    v6);
  return LastError;
}

```

## disassembly

```asm
0x1800480f4  mov     [rsp-8+arg_8], rbx
0x1800480f9  push    rbp
0x1800480fa  push    rdi
0x1800480fb  push    r14
0x1800480fd  lea     rbp, [rsp-160h]
0x180048105  sub     rsp, 260h
0x18004810c  mov     rax, cs:__security_cookie
0x180048113  xor     rax, rsp
0x180048116  mov     [rbp+170h+var_20], rax
0x18004811d  mov     rdi, r8
0x180048120  mov     qword ptr [r8], 0
0x180048127  mov     r8, rcx; unsigned __int16 *
0x18004812a  mov     r14d, 104h
0x180048130  mov     edx, r14d; unsigned __int64
0x180048133  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180048138  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004813d  lea     r8, aP0; "_p0"
0x180048144  mov     edx, r14d; unsigned __int64
0x180048147  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18004814c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180048151  lea     r8, [rsp+270h+Name]; lpName
0x180048156  xor     edx, edx; bInheritHandle
0x180048158  mov     ecx, 1F0003h; dwDesiredAccess
0x18004815d  call    cs:__imp_OpenSemaphoreW
0x180048164  nop     dword ptr [rax+rax+00h]
0x180048169  mov     [rsp+270h+var_240], rax
0x18004816e  test    rax, rax
0x180048171  jnz     short loc_1800481A1
0x180048173  call    cs:__imp_GetLastError
0x18004817a  nop     dword ptr [rax+rax+00h]
0x18004817f  cmp     eax, 2
0x180048182  jnz     short loc_180048189
0x180048184  jmp     loc_180048295
0x180048189  mov     rcx, [rbp+178h]; this
0x180048190  mov     edx, 0D0h; void *
0x180048195  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004819a  mov     ebx, eax
0x18004819c  jmp     loc_180048297
0x1800481a1  mov     [rsp+270h+var_24C], 0
0x1800481a9  mov     [rsp+270h+var_250], 0; int
0x1800481b1  lea     rdx, [rsp+270h+var_24C]; int *
0x1800481b6  mov     rcx, rax; hHandle
0x1800481b9  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800481be  mov     ebx, eax
0x1800481c0  test    eax, eax
0x1800481c2  jns     short loc_1800481E5
0x1800481c4  mov     rcx, [rbp+178h]; this
0x1800481cb  mov     r9d, eax; char *
0x1800481ce  lea     r8, aWil; "wil"
0x1800481d5  mov     edx, 0D6h; void *
0x1800481da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800481df  nop
0x1800481e0  jmp     loc_180048297
0x1800481e5  lea     r8, asc_180073CA0; "h"
0x1800481ec  mov     rdx, r14; unsigned __int64
0x1800481ef  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800481f4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800481f9  lea     r8, [rsp+270h+Name]; lpName
0x1800481fe  xor     edx, edx; bInheritHandle
0x180048200  mov     ecx, 1F0003h; dwDesiredAccess
0x180048205  call    cs:__imp_OpenSemaphoreW
0x18004820c  nop     dword ptr [rax+rax+00h]
0x180048211  mov     [rsp+270h+var_248], rax
0x180048216  test    rax, rax
0x180048219  jnz     short loc_18004823B
0x18004821b  mov     rcx, [rbp+178h]; this
0x180048222  mov     edx, 0DCh; void *
0x180048227  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004822c  mov     ebx, eax
0x18004822e  lea     rcx, [rsp+270h+var_248]
0x180048233  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180048238  nop
0x180048239  jmp     short loc_180048297
0x18004823b  lea     rdx, [rsp+270h+var_250]; int *
0x180048240  mov     rcx, rax; hHandle
0x180048243  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180048248  mov     ebx, eax
0x18004824a  test    eax, eax
0x18004824c  jns     short loc_180048277
0x18004824e  mov     rcx, [rbp+178h]; this
0x180048255  mov     r9d, eax; char *
0x180048258  lea     r8, aWil; "wil"
0x18004825f  mov     edx, 0DEh; void *
0x180048264  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048269  nop
0x18004826a  lea     rcx, [rsp+270h+var_248]
0x18004826f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180048274  nop
0x180048275  jmp     short loc_180048297
0x180048277  lea     rcx, [rsp+270h+var_248]
0x18004827c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180048281  movsxd  rcx, [rsp+270h+var_250]
0x180048286  shl     rcx, 1Fh
0x18004828a  movsxd  rax, [rsp+270h+var_24C]
0x18004828f  or      rcx, rax
0x180048292  mov     [rdi], rcx
0x180048295  xor     ebx, ebx
0x180048297  lea     rcx, [rsp+270h+var_240]
0x18004829c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800482a1  mov     eax, ebx
0x1800482a3  mov     rcx, [rbp+170h+var_20]
0x1800482aa  xor     rcx, rsp; StackCookie
0x1800482ad  call    __security_check_cookie
0x1800482b2  mov     rbx, [rsp+270h+arg_8]
0x1800482ba  add     rsp, 260h
0x1800482c1  pop     r14
0x1800482c3  pop     rdi
0x1800482c4  pop     rbp
0x1800482c5  retn
```
