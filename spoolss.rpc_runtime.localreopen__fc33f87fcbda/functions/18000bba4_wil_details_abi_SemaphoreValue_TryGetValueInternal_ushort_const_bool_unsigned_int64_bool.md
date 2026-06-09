# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000bba4`
- end: `0x18000bd53`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `431`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000bb2c`

## callees

- `0x180004728`
- `0x180004a64`
- `0x180005680`
- `0x180007660`
- `0x1800092d8`
- `0x18000ac0c`
- `0x18000b710`
- `0x18000bba4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000bc08`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000bca4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000bc08`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000bca4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc1e`

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
0x18000bba4  mov     [rsp-8+arg_8], rbx
0x18000bba9  mov     [rsp-8+arg_18], rdi
0x18000bbae  push    rbp
0x18000bbaf  lea     rbp, [rsp-160h]
0x18000bbb7  sub     rsp, 260h
0x18000bbbe  mov     rax, cs:__security_cookie
0x18000bbc5  xor     rax, rsp
0x18000bbc8  mov     [rbp+160h+var_10], rax
0x18000bbcf  mov     rdi, r8
0x18000bbd2  mov     qword ptr [r8], 0
0x18000bbd9  mov     r8, rcx; unsigned __int16 *
0x18000bbdc  mov     edx, 104h; unsigned __int64
0x18000bbe1  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000bbe6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000bbeb  lea     r8, aP0; "_p0"
0x18000bbf2  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000bbf7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000bbfc  lea     r8, [rsp+260h+Name]; lpName
0x18000bc01  xor     edx, edx; bInheritHandle
0x18000bc03  mov     ecx, 1F0003h; dwDesiredAccess
0x18000bc08  call    cs:__imp_OpenSemaphoreW
0x18000bc0f  nop     dword ptr [rax+rax+00h]
0x18000bc14  mov     [rsp+260h+var_230], rax
0x18000bc19  test    rax, rax
0x18000bc1c  jnz     short loc_18000BC4B
0x18000bc1e  call    cs:__imp_GetLastError
0x18000bc25  nop     dword ptr [rax+rax+00h]
0x18000bc2a  cmp     eax, 2
0x18000bc2d  jz      loc_18000BD20
0x18000bc33  mov     rcx, [rbp+168h]; this
0x18000bc3a  mov     edx, 0D0h; void *
0x18000bc3f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000bc44  mov     ebx, eax
0x18000bc46  jmp     loc_18000BD22
0x18000bc4b  lea     rdx, [rsp+260h+var_23C]; int *
0x18000bc50  mov     [rsp+260h+var_23C], 0
0x18000bc58  mov     rcx, rax; hHandle
0x18000bc5b  mov     [rsp+260h+var_240], 0; int
0x18000bc63  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000bc68  mov     ebx, eax
0x18000bc6a  test    eax, eax
0x18000bc6c  jns     short loc_18000BC87
0x18000bc6e  mov     rcx, [rbp+168h]; this
0x18000bc75  mov     r9d, eax; char *
0x18000bc78  mov     edx, 0D6h; void *
0x18000bc7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bc82  jmp     loc_18000BD22
0x18000bc87  lea     r8, asc_180019630; "h"
0x18000bc8e  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000bc93  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000bc98  lea     r8, [rsp+260h+Name]; lpName
0x18000bc9d  xor     edx, edx; bInheritHandle
0x18000bc9f  mov     ecx, 1F0003h; dwDesiredAccess
0x18000bca4  call    cs:__imp_OpenSemaphoreW
0x18000bcab  nop     dword ptr [rax+rax+00h]
0x18000bcb0  mov     [rsp+260h+var_238], rax
0x18000bcb5  test    rax, rax
0x18000bcb8  jnz     short loc_18000BCD9
0x18000bcba  mov     rcx, [rbp+168h]; this
0x18000bcc1  mov     edx, 0DCh; void *
0x18000bcc6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000bccb  mov     ebx, eax
0x18000bccd  lea     rcx, [rsp+260h+var_238]
0x18000bcd2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000bcd7  jmp     short loc_18000BD22
0x18000bcd9  lea     rdx, [rsp+260h+var_240]; int *
0x18000bcde  mov     rcx, rax; hHandle
0x18000bce1  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000bce6  mov     ebx, eax
0x18000bce8  test    eax, eax
0x18000bcea  jns     short loc_18000BD02
0x18000bcec  mov     rcx, [rbp+168h]; this
0x18000bcf3  mov     r9d, eax; char *
0x18000bcf6  mov     edx, 0DEh; void *
0x18000bcfb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bd00  jmp     short loc_18000BCCD
0x18000bd02  lea     rcx, [rsp+260h+var_238]
0x18000bd07  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000bd0c  movsxd  rcx, [rsp+260h+var_240]
0x18000bd11  movsxd  rax, [rsp+260h+var_23C]
0x18000bd16  shl     rcx, 1Fh
0x18000bd1a  or      rcx, rax
0x18000bd1d  mov     [rdi], rcx
0x18000bd20  xor     ebx, ebx
0x18000bd22  lea     rcx, [rsp+260h+var_230]
0x18000bd27  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000bd2c  mov     eax, ebx
0x18000bd2e  mov     rcx, [rbp+160h+var_10]
0x18000bd35  xor     rcx, rsp; StackCookie
0x18000bd38  call    __security_check_cookie
0x18000bd3d  lea     r11, [rsp+260h+var_s0]
0x18000bd45  mov     rbx, [r11+18h]
0x18000bd49  mov     rdi, [r11+28h]
0x18000bd4d  mov     rsp, r11
0x18000bd50  pop     rbp
0x18000bd51  retn
```
