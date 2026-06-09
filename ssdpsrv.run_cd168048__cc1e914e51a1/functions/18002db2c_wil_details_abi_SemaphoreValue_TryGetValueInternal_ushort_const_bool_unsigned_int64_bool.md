# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18002db2c`
- end: `0x18002dce1`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `437`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18002dab4`

## callees

- `0x18001d018`
- `0x18001db80`
- `0x1800287d0`
- `0x18002a86c`
- `0x18002ba78`
- `0x18002d37c`
- `0x18002d39c`
- `0x18002db2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002db95`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002dc33`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002db95`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002dc33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dbab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dbab`

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
0x18002db2c  mov     [rsp-8+arg_8], rbx
0x18002db31  push    rbp
0x18002db32  push    rdi
0x18002db33  push    r14
0x18002db35  lea     rbp, [rsp-160h]
0x18002db3d  sub     rsp, 260h
0x18002db44  mov     rax, cs:__security_cookie
0x18002db4b  xor     rax, rsp
0x18002db4e  mov     [rbp+170h+var_20], rax
0x18002db55  mov     rdi, r8
0x18002db58  mov     qword ptr [r8], 0
0x18002db5f  mov     r8, rcx; unsigned __int16 *
0x18002db62  mov     r14d, 104h
0x18002db68  mov     edx, r14d; unsigned __int64
0x18002db6b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002db70  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002db75  lea     r8, aP0; "_p0"
0x18002db7c  mov     edx, r14d; unsigned __int64
0x18002db7f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002db84  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002db89  lea     r8, [rsp+270h+Name]; lpName
0x18002db8e  xor     edx, edx; bInheritHandle
0x18002db90  mov     ecx, 1F0003h; dwDesiredAccess
0x18002db95  call    cs:__imp_OpenSemaphoreW
0x18002db9c  nop     dword ptr [rax+rax+00h]
0x18002dba1  mov     [rsp+270h+var_240], rax
0x18002dba6  test    rax, rax
0x18002dba9  jnz     short loc_18002DBD7
0x18002dbab  call    cs:__imp_GetLastError
0x18002dbb2  nop     dword ptr [rax+rax+00h]
0x18002dbb7  cmp     eax, 2
0x18002dbba  jz      loc_18002DCAF
0x18002dbc0  mov     rcx, [rbp+178h]; this
0x18002dbc7  lea     edx, [r14-34h]; void *
0x18002dbcb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002dbd0  mov     ebx, eax
0x18002dbd2  jmp     loc_18002DCB1
0x18002dbd7  lea     rdx, [rsp+270h+var_24C]; int *
0x18002dbdc  mov     [rsp+270h+var_24C], 0
0x18002dbe4  mov     rcx, rax; hHandle
0x18002dbe7  mov     [rsp+270h+var_250], 0; int
0x18002dbef  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18002dbf4  mov     ebx, eax
0x18002dbf6  test    eax, eax
0x18002dbf8  jns     short loc_18002DC13
0x18002dbfa  mov     rcx, [rbp+178h]; this
0x18002dc01  mov     r9d, eax; char *
0x18002dc04  mov     edx, 0D6h; void *
0x18002dc09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002dc0e  jmp     loc_18002DCB1
0x18002dc13  lea     r8, asc_18003D518; "h"
0x18002dc1a  mov     rdx, r14; unsigned __int64
0x18002dc1d  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002dc22  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002dc27  lea     r8, [rsp+270h+Name]; lpName
0x18002dc2c  xor     edx, edx; bInheritHandle
0x18002dc2e  mov     ecx, 1F0003h; dwDesiredAccess
0x18002dc33  call    cs:__imp_OpenSemaphoreW
0x18002dc3a  nop     dword ptr [rax+rax+00h]
0x18002dc3f  mov     [rsp+270h+var_248], rax
0x18002dc44  test    rax, rax
0x18002dc47  jnz     short loc_18002DC68
0x18002dc49  mov     rcx, [rbp+178h]; this
0x18002dc50  mov     edx, 0DCh; void *
0x18002dc55  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002dc5a  mov     ebx, eax
0x18002dc5c  lea     rcx, [rsp+270h+var_248]
0x18002dc61  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002dc66  jmp     short loc_18002DCB1
0x18002dc68  lea     rdx, [rsp+270h+var_250]; int *
0x18002dc6d  mov     rcx, rax; hHandle
0x18002dc70  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18002dc75  mov     ebx, eax
0x18002dc77  test    eax, eax
0x18002dc79  jns     short loc_18002DC91
0x18002dc7b  mov     rcx, [rbp+178h]; this
0x18002dc82  mov     r9d, eax; char *
0x18002dc85  mov     edx, 0DEh; void *
0x18002dc8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002dc8f  jmp     short loc_18002DC5C
0x18002dc91  lea     rcx, [rsp+270h+var_248]
0x18002dc96  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002dc9b  movsxd  rcx, [rsp+270h+var_250]
0x18002dca0  movsxd  rax, [rsp+270h+var_24C]
0x18002dca5  shl     rcx, 1Fh
0x18002dca9  or      rcx, rax
0x18002dcac  mov     [rdi], rcx
0x18002dcaf  xor     ebx, ebx
0x18002dcb1  lea     rcx, [rsp+270h+var_240]
0x18002dcb6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002dcbb  mov     eax, ebx
0x18002dcbd  mov     rcx, [rbp+170h+var_20]
0x18002dcc4  xor     rcx, rsp; StackCookie
0x18002dcc7  call    __security_check_cookie
0x18002dccc  mov     rbx, [rsp+270h+arg_8]
0x18002dcd4  add     rsp, 260h
0x18002dcdb  pop     r14
0x18002dcdd  pop     rdi
0x18002dcde  pop     rbp
0x18002dcdf  retn
```
