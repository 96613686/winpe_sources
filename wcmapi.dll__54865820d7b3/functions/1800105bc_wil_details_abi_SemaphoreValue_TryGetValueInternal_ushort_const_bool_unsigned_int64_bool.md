# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800105bc`
- end: `0x18001076b`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `431`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180010544`

## callees

- `0x180005280`
- `0x180008a90`
- `0x18000bfb4`
- `0x18000d6d4`
- `0x18000fda0`
- `0x18000fdc0`
- `0x1800101f4`
- `0x1800105bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010636`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010636`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180010620`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800106bc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180010620`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800106bc`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned __int64 v5; // rdx
  HANDLE v6; // rax
  unsigned int v7; // r8d
  const char *v8; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v11; // rdx
  unsigned int v12; // r8d
  HANDLE v13; // rax
  unsigned int v14; // r8d
  const char *v15; // r9
  int v16; // eax
  unsigned int v17; // r8d
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v21; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v22[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v22[0] = v6;
  if ( v6 )
  {
    v20 = 0;
    v19 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v20);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore, v19);
      goto LABEL_13;
    }
    StringCchCatW(Name, v11, L"h");
    v13 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v21 = v13;
    if ( v13 )
    {
      v16 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, &v19);
      LastError = v16;
      if ( v16 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
        *a3 = v20 | (unsigned __int64)((__int64)v19 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v17, (const char *)(unsigned int)v16, v19);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v14, v15);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v7, v8);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v22);
  return LastError;
}

```

## disassembly

```asm
0x1800105bc  mov     [rsp-8+arg_8], rbx
0x1800105c1  mov     [rsp-8+arg_18], rdi
0x1800105c6  push    rbp
0x1800105c7  lea     rbp, [rsp-160h]
0x1800105cf  sub     rsp, 260h
0x1800105d6  mov     rax, cs:__security_cookie
0x1800105dd  xor     rax, rsp
0x1800105e0  mov     [rbp+160h+var_10], rax
0x1800105e7  mov     rdi, r8
0x1800105ea  mov     qword ptr [r8], 0
0x1800105f1  mov     r8, rcx; unsigned __int16 *
0x1800105f4  mov     edx, 104h; unsigned __int64
0x1800105f9  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800105fe  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180010603  lea     r8, aP0; "_p0"
0x18001060a  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18001060f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180010614  lea     r8, [rsp+260h+Name]; lpName
0x180010619  xor     edx, edx; bInheritHandle
0x18001061b  mov     ecx, 1F0003h; dwDesiredAccess
0x180010620  call    cs:__imp_OpenSemaphoreW
0x180010627  nop     dword ptr [rax+rax+00h]
0x18001062c  mov     [rsp+260h+var_230], rax
0x180010631  test    rax, rax
0x180010634  jnz     short loc_180010663
0x180010636  call    cs:__imp_GetLastError
0x18001063d  nop     dword ptr [rax+rax+00h]
0x180010642  cmp     eax, 2
0x180010645  jz      loc_180010738
0x18001064b  mov     rcx, [rbp+168h]; this
0x180010652  mov     edx, 0D0h; void *
0x180010657  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001065c  mov     ebx, eax
0x18001065e  jmp     loc_18001073A
0x180010663  lea     rdx, [rsp+260h+var_23C]; int *
0x180010668  mov     [rsp+260h+var_23C], 0
0x180010670  mov     rcx, rax; hHandle
0x180010673  mov     [rsp+260h+var_240], 0; int
0x18001067b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180010680  mov     ebx, eax
0x180010682  test    eax, eax
0x180010684  jns     short loc_18001069F
0x180010686  mov     rcx, [rbp+168h]; this
0x18001068d  mov     r9d, eax; char *
0x180010690  mov     edx, 0D6h; void *
0x180010695  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001069a  jmp     loc_18001073A
0x18001069f  lea     r8, asc_180022420; "h"
0x1800106a6  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800106ab  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800106b0  lea     r8, [rsp+260h+Name]; lpName
0x1800106b5  xor     edx, edx; bInheritHandle
0x1800106b7  mov     ecx, 1F0003h; dwDesiredAccess
0x1800106bc  call    cs:__imp_OpenSemaphoreW
0x1800106c3  nop     dword ptr [rax+rax+00h]
0x1800106c8  mov     [rsp+260h+var_238], rax
0x1800106cd  test    rax, rax
0x1800106d0  jnz     short loc_1800106F1
0x1800106d2  mov     rcx, [rbp+168h]; this
0x1800106d9  mov     edx, 0DCh; void *
0x1800106de  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800106e3  mov     ebx, eax
0x1800106e5  lea     rcx, [rsp+260h+var_238]
0x1800106ea  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800106ef  jmp     short loc_18001073A
0x1800106f1  lea     rdx, [rsp+260h+var_240]; int *
0x1800106f6  mov     rcx, rax; hHandle
0x1800106f9  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800106fe  mov     ebx, eax
0x180010700  test    eax, eax
0x180010702  jns     short loc_18001071A
0x180010704  mov     rcx, [rbp+168h]; this
0x18001070b  mov     r9d, eax; char *
0x18001070e  mov     edx, 0DEh; void *
0x180010713  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010718  jmp     short loc_1800106E5
0x18001071a  lea     rcx, [rsp+260h+var_238]
0x18001071f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180010724  movsxd  rcx, [rsp+260h+var_240]
0x180010729  movsxd  rax, [rsp+260h+var_23C]
0x18001072e  shl     rcx, 1Fh
0x180010732  or      rcx, rax
0x180010735  mov     [rdi], rcx
0x180010738  xor     ebx, ebx
0x18001073a  lea     rcx, [rsp+260h+var_230]
0x18001073f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180010744  mov     eax, ebx
0x180010746  mov     rcx, [rbp+160h+var_10]
0x18001074d  xor     rcx, rsp; StackCookie
0x180010750  call    __security_check_cookie
0x180010755  lea     r11, [rsp+260h+var_s0]
0x18001075d  mov     rbx, [r11+18h]
0x180010761  mov     rdi, [r11+28h]
0x180010765  mov     rsp, r11
0x180010768  pop     rbp
0x180010769  retn
```
