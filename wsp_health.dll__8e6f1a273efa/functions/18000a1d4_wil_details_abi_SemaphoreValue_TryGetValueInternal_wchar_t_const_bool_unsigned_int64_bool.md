# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000a1d4`
- end: `0x18000a389`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `437`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000a15c`

## callees

- `0x180002b50`
- `0x180006530`
- `0x180007bfc`
- `0x18000970c`
- `0x18000972c`
- `0x180009e24`
- `0x180009e80`
- `0x18000a1d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a23d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a2db`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a23d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a2db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a253`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a253`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const wchar_t *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  HANDLE v5; // rax
  unsigned int v6; // r8d
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned int v10; // r8d
  HANDLE v11; // rax
  unsigned int v12; // r8d
  const char *v13; // r9
  int v14; // eax
  unsigned int v15; // r8d
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v19; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v20[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20[0] = v5;
  if ( v5 )
  {
    v18 = 0;
    v17 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v18);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v10, (const char *)(unsigned int)ValueFromSemaphore, v17);
      goto LABEL_13;
    }
    StringCchCatW(Name, 0x104u, L"h");
    v11 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v19 = v11;
    if ( v11 )
    {
      v14 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v11, &v17);
      LastError = v14;
      if ( v14 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
        *a3 = v18 | (unsigned __int64)((__int64)v17 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v15, (const char *)(unsigned int)v14, v17);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v12, v13);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v6, v7);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v20);
  return LastError;
}

```

## disassembly

```asm
0x18000a1d4  mov     [rsp-8+arg_8], rbx
0x18000a1d9  push    rbp
0x18000a1da  push    rdi
0x18000a1db  push    r14
0x18000a1dd  lea     rbp, [rsp-160h]
0x18000a1e5  sub     rsp, 260h
0x18000a1ec  mov     rax, cs:__security_cookie
0x18000a1f3  xor     rax, rsp
0x18000a1f6  mov     [rbp+170h+var_20], rax
0x18000a1fd  mov     rdi, r8
0x18000a200  mov     qword ptr [r8], 0
0x18000a207  mov     r8, rcx; wchar_t *
0x18000a20a  mov     r14d, 104h
0x18000a210  mov     edx, r14d; unsigned __int64
0x18000a213  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18000a218  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000a21d  lea     r8, aP0; "_p0"
0x18000a224  mov     edx, r14d; unsigned __int64
0x18000a227  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18000a22c  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000a231  lea     r8, [rsp+270h+Name]; lpName
0x18000a236  xor     edx, edx; bInheritHandle
0x18000a238  mov     ecx, 1F0003h; dwDesiredAccess
0x18000a23d  call    cs:__imp_OpenSemaphoreW
0x18000a244  nop     dword ptr [rax+rax+00h]
0x18000a249  mov     [rsp+270h+var_240], rax
0x18000a24e  test    rax, rax
0x18000a251  jnz     short loc_18000A27F
0x18000a253  call    cs:__imp_GetLastError
0x18000a25a  nop     dword ptr [rax+rax+00h]
0x18000a25f  cmp     eax, 2
0x18000a262  jz      loc_18000A357
0x18000a268  mov     rcx, [rbp+178h]; this
0x18000a26f  lea     edx, [r14-34h]; void *
0x18000a273  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a278  mov     ebx, eax
0x18000a27a  jmp     loc_18000A359
0x18000a27f  lea     rdx, [rsp+270h+var_24C]; int *
0x18000a284  mov     [rsp+270h+var_24C], 0
0x18000a28c  mov     rcx, rax; hHandle
0x18000a28f  mov     [rsp+270h+var_250], 0; int
0x18000a297  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000a29c  mov     ebx, eax
0x18000a29e  test    eax, eax
0x18000a2a0  jns     short loc_18000A2BB
0x18000a2a2  mov     rcx, [rbp+178h]; this
0x18000a2a9  mov     r9d, eax; char *
0x18000a2ac  mov     edx, 0D6h; void *
0x18000a2b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a2b6  jmp     loc_18000A359
0x18000a2bb  lea     r8, asc_1800CE7D0; "h"
0x18000a2c2  mov     rdx, r14; unsigned __int64
0x18000a2c5  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18000a2ca  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000a2cf  lea     r8, [rsp+270h+Name]; lpName
0x18000a2d4  xor     edx, edx; bInheritHandle
0x18000a2d6  mov     ecx, 1F0003h; dwDesiredAccess
0x18000a2db  call    cs:__imp_OpenSemaphoreW
0x18000a2e2  nop     dword ptr [rax+rax+00h]
0x18000a2e7  mov     [rsp+270h+var_248], rax
0x18000a2ec  test    rax, rax
0x18000a2ef  jnz     short loc_18000A310
0x18000a2f1  mov     rcx, [rbp+178h]; this
0x18000a2f8  mov     edx, 0DCh; void *
0x18000a2fd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a302  mov     ebx, eax
0x18000a304  lea     rcx, [rsp+270h+var_248]
0x18000a309  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a30e  jmp     short loc_18000A359
0x18000a310  lea     rdx, [rsp+270h+var_250]; int *
0x18000a315  mov     rcx, rax; hHandle
0x18000a318  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000a31d  mov     ebx, eax
0x18000a31f  test    eax, eax
0x18000a321  jns     short loc_18000A339
0x18000a323  mov     rcx, [rbp+178h]; this
0x18000a32a  mov     r9d, eax; char *
0x18000a32d  mov     edx, 0DEh; void *
0x18000a332  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a337  jmp     short loc_18000A304
0x18000a339  lea     rcx, [rsp+270h+var_248]
0x18000a33e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a343  movsxd  rcx, [rsp+270h+var_250]
0x18000a348  movsxd  rax, [rsp+270h+var_24C]
0x18000a34d  shl     rcx, 1Fh
0x18000a351  or      rcx, rax
0x18000a354  mov     [rdi], rcx
0x18000a357  xor     ebx, ebx
0x18000a359  lea     rcx, [rsp+270h+var_240]
0x18000a35e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a363  mov     eax, ebx
0x18000a365  mov     rcx, [rbp+170h+var_20]
0x18000a36c  xor     rcx, rsp; StackCookie
0x18000a36f  call    __security_check_cookie
0x18000a374  mov     rbx, [rsp+270h+arg_8]
0x18000a37c  add     rsp, 260h
0x18000a383  pop     r14
0x18000a385  pop     rdi
0x18000a386  pop     rbp
0x18000a387  retn
```
