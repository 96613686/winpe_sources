# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800540fc`
- end: `0x18005429e`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180054088`

## callees

- `0x1800045e4`
- `0x18001d778`
- `0x18004a410`
- `0x18004ed58`
- `0x180051934`
- `0x180051954`
- `0x1800540fc`
- `0x180091ef0`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x180054165`
- `KERNEL32!OpenSemaphoreW` at `0x1800541f7`
- `KERNEL32!OpenSemaphoreW` at `0x180054165`
- `KERNEL32!OpenSemaphoreW` at `0x1800541f7`
- `KERNEL32!GetLastError` at `0x180054175`
- `KERNEL32!GetLastError` at `0x180054175`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
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
0x1800540fc  mov     [rsp-8+arg_8], rbx
0x180054101  push    rbp
0x180054102  push    rdi
0x180054103  push    r14
0x180054105  lea     rbp, [rsp-160h]
0x18005410d  sub     rsp, 260h
0x180054114  mov     rax, cs:__security_cookie
0x18005411b  xor     rax, rsp
0x18005411e  mov     [rbp+170h+var_20], rax
0x180054125  mov     rdi, r8
0x180054128  mov     qword ptr [r8], 0
0x18005412f  mov     r8, rcx; unsigned __int16 *
0x180054132  mov     r14d, 104h
0x180054138  mov     edx, r14d; unsigned __int64
0x18005413b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180054140  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180054145  lea     r8, aP0; "_p0"
0x18005414c  mov     edx, r14d; unsigned __int64
0x18005414f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180054154  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180054159  lea     r8, [rsp+270h+Name]; lpName
0x18005415e  xor     edx, edx; bInheritHandle
0x180054160  mov     ecx, 1F0003h; dwDesiredAccess
0x180054165  call    cs:__imp_OpenSemaphoreW
0x18005416b  mov     [rsp+270h+var_240], rax
0x180054170  test    rax, rax
0x180054173  jnz     short loc_18005419B
0x180054175  call    cs:__imp_GetLastError
0x18005417b  cmp     eax, 2
0x18005417e  jz      loc_18005426D
0x180054184  mov     rcx, [rbp+178h]; this
0x18005418b  lea     edx, [r14-34h]; void *
0x18005418f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180054194  mov     ebx, eax
0x180054196  jmp     loc_18005426F
0x18005419b  lea     rdx, [rsp+270h+var_24C]; int *
0x1800541a0  mov     [rsp+270h+var_24C], 0
0x1800541a8  mov     rcx, rax; hHandle
0x1800541ab  mov     [rsp+270h+var_250], 0; int
0x1800541b3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800541b8  mov     ebx, eax
0x1800541ba  test    eax, eax
0x1800541bc  jns     short loc_1800541D7
0x1800541be  mov     rcx, [rbp+178h]; this
0x1800541c5  mov     r9d, eax; char *
0x1800541c8  mov     edx, 0D6h; void *
0x1800541cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800541d2  jmp     loc_18005426F
0x1800541d7  lea     r8, asc_18009D120; "h"
0x1800541de  mov     rdx, r14; unsigned __int64
0x1800541e1  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800541e6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800541eb  lea     r8, [rsp+270h+Name]; lpName
0x1800541f0  xor     edx, edx; bInheritHandle
0x1800541f2  mov     ecx, 1F0003h; dwDesiredAccess
0x1800541f7  call    cs:__imp_OpenSemaphoreW
0x1800541fd  mov     [rsp+270h+var_248], rax
0x180054202  test    rax, rax
0x180054205  jnz     short loc_180054226
0x180054207  mov     rcx, [rbp+178h]; this
0x18005420e  mov     edx, 0DCh; void *
0x180054213  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180054218  mov     ebx, eax
0x18005421a  lea     rcx, [rsp+270h+var_248]
0x18005421f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180054224  jmp     short loc_18005426F
0x180054226  lea     rdx, [rsp+270h+var_250]; int *
0x18005422b  mov     rcx, rax; hHandle
0x18005422e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180054233  mov     ebx, eax
0x180054235  test    eax, eax
0x180054237  jns     short loc_18005424F
0x180054239  mov     rcx, [rbp+178h]; this
0x180054240  mov     r9d, eax; char *
0x180054243  mov     edx, 0DEh; void *
0x180054248  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005424d  jmp     short loc_18005421A
0x18005424f  lea     rcx, [rsp+270h+var_248]
0x180054254  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180054259  movsxd  rcx, [rsp+270h+var_250]
0x18005425e  movsxd  rax, [rsp+270h+var_24C]
0x180054263  shl     rcx, 1Fh
0x180054267  or      rcx, rax
0x18005426a  mov     [rdi], rcx
0x18005426d  xor     ebx, ebx
0x18005426f  lea     rcx, [rsp+270h+var_240]
0x180054274  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180054279  mov     eax, ebx
0x18005427b  mov     rcx, [rbp+170h+var_20]
0x180054282  xor     rcx, rsp; StackCookie
0x180054285  call    __security_check_cookie
0x18005428a  mov     rbx, [rsp+270h+arg_8]
0x180054292  add     rsp, 260h
0x180054299  pop     r14
0x18005429b  pop     rdi
0x18005429c  pop     rbp
0x18005429d  retn
```
