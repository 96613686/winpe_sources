# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x180009ec0`
- end: `0x18000a062`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180009e4c`

## callees

- `0x180002ae0`
- `0x1800063ec`
- `0x180007958`
- `0x1800093cc`
- `0x1800093ec`
- `0x180009ab4`
- `0x180009b10`
- `0x180009ec0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009f29`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009fbb`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009f29`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009fbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f39`

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
0x180009ec0  mov     [rsp-8+arg_8], rbx
0x180009ec5  push    rbp
0x180009ec6  push    rdi
0x180009ec7  push    r14
0x180009ec9  lea     rbp, [rsp-160h]
0x180009ed1  sub     rsp, 260h
0x180009ed8  mov     rax, cs:__security_cookie
0x180009edf  xor     rax, rsp
0x180009ee2  mov     [rbp+170h+var_20], rax
0x180009ee9  mov     rdi, r8
0x180009eec  mov     qword ptr [r8], 0
0x180009ef3  mov     r8, rcx; wchar_t *
0x180009ef6  mov     r14d, 104h
0x180009efc  mov     edx, r14d; unsigned __int64
0x180009eff  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180009f04  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180009f09  lea     r8, aP0; "_p0"
0x180009f10  mov     edx, r14d; unsigned __int64
0x180009f13  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180009f18  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180009f1d  lea     r8, [rsp+270h+Name]; lpName
0x180009f22  xor     edx, edx; bInheritHandle
0x180009f24  mov     ecx, 1F0003h; dwDesiredAccess
0x180009f29  call    cs:__imp_OpenSemaphoreW
0x180009f2f  mov     [rsp+270h+var_240], rax
0x180009f34  test    rax, rax
0x180009f37  jnz     short loc_180009F5F
0x180009f39  call    cs:__imp_GetLastError
0x180009f3f  cmp     eax, 2
0x180009f42  jz      loc_18000A031
0x180009f48  mov     rcx, [rbp+178h]; this
0x180009f4f  lea     edx, [r14-34h]; void *
0x180009f53  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009f58  mov     ebx, eax
0x180009f5a  jmp     loc_18000A033
0x180009f5f  lea     rdx, [rsp+270h+var_24C]; int *
0x180009f64  mov     [rsp+270h+var_24C], 0
0x180009f6c  mov     rcx, rax; hHandle
0x180009f6f  mov     [rsp+270h+var_250], 0; int
0x180009f77  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009f7c  mov     ebx, eax
0x180009f7e  test    eax, eax
0x180009f80  jns     short loc_180009F9B
0x180009f82  mov     rcx, [rbp+178h]; this
0x180009f89  mov     r9d, eax; char *
0x180009f8c  mov     edx, 0D6h; void *
0x180009f91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009f96  jmp     loc_18000A033
0x180009f9b  lea     r8, asc_1800CC7B0; "h"
0x180009fa2  mov     rdx, r14; unsigned __int64
0x180009fa5  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180009faa  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180009faf  lea     r8, [rsp+270h+Name]; lpName
0x180009fb4  xor     edx, edx; bInheritHandle
0x180009fb6  mov     ecx, 1F0003h; dwDesiredAccess
0x180009fbb  call    cs:__imp_OpenSemaphoreW
0x180009fc1  mov     [rsp+270h+var_248], rax
0x180009fc6  test    rax, rax
0x180009fc9  jnz     short loc_180009FEA
0x180009fcb  mov     rcx, [rbp+178h]; this
0x180009fd2  mov     edx, 0DCh; void *
0x180009fd7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009fdc  mov     ebx, eax
0x180009fde  lea     rcx, [rsp+270h+var_248]
0x180009fe3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009fe8  jmp     short loc_18000A033
0x180009fea  lea     rdx, [rsp+270h+var_250]; int *
0x180009fef  mov     rcx, rax; hHandle
0x180009ff2  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009ff7  mov     ebx, eax
0x180009ff9  test    eax, eax
0x180009ffb  jns     short loc_18000A013
0x180009ffd  mov     rcx, [rbp+178h]; this
0x18000a004  mov     r9d, eax; char *
0x18000a007  mov     edx, 0DEh; void *
0x18000a00c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a011  jmp     short loc_180009FDE
0x18000a013  lea     rcx, [rsp+270h+var_248]
0x18000a018  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a01d  movsxd  rcx, [rsp+270h+var_250]
0x18000a022  movsxd  rax, [rsp+270h+var_24C]
0x18000a027  shl     rcx, 1Fh
0x18000a02b  or      rcx, rax
0x18000a02e  mov     [rdi], rcx
0x18000a031  xor     ebx, ebx
0x18000a033  lea     rcx, [rsp+270h+var_240]
0x18000a038  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a03d  mov     eax, ebx
0x18000a03f  mov     rcx, [rbp+170h+var_20]
0x18000a046  xor     rcx, rsp; StackCookie
0x18000a049  call    __security_check_cookie
0x18000a04e  mov     rbx, [rsp+270h+arg_8]
0x18000a056  add     rsp, 260h
0x18000a05d  pop     r14
0x18000a05f  pop     rdi
0x18000a060  pop     rbp
0x18000a061  retn
```
