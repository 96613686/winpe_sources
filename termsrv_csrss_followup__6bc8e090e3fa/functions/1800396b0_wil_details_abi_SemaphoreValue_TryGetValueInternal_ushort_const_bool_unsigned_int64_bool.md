# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800396b0`
- end: `0x180039881`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `465`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18003774c`

## callees

- `0x180012d10`
- `0x18002609c`
- `0x180033f60`
- `0x18003760c`
- `0x18003841c`
- `0x180038ee4`
- `0x1800393d8`
- `0x1800396b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180039719`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800397c5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180039719`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800397c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003972f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003972f`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  HANDLE v5; // rax
  const char *v6; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  HANDLE v9; // rax
  const char *v10; // r9
  int v11; // eax
  int v13; // [rsp+20h] [rbp-E0h] BYREF
  int v14; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v15; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v16[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v16[0] = v5;
  if ( v5 )
  {
    v14 = 0;
    v13 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v14);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v13);
      goto LABEL_13;
    }
    StringCchCatW(Name, 0x104u, L"h");
    v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v15 = v9;
    if ( v9 )
    {
      v11 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, &v13);
      LastError = v11;
      if ( v11 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v15);
        *a3 = v14 | (unsigned __int64)((__int64)v13 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v11,
        v13);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v10);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v15);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v6);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v16);
  return LastError;
}

```

## disassembly

```asm
0x1800396b0  mov     [rsp-8+arg_8], rbx
0x1800396b5  push    rbp
0x1800396b6  push    rdi
0x1800396b7  push    r14
0x1800396b9  lea     rbp, [rsp-160h]
0x1800396c1  sub     rsp, 260h
0x1800396c8  mov     rax, cs:__security_cookie
0x1800396cf  xor     rax, rsp
0x1800396d2  mov     [rbp+170h+var_20], rax
0x1800396d9  mov     rdi, r8
0x1800396dc  mov     qword ptr [r8], 0
0x1800396e3  mov     r8, rcx; unsigned __int16 *
0x1800396e6  mov     r14d, 104h
0x1800396ec  mov     edx, r14d; unsigned __int64
0x1800396ef  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800396f4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800396f9  lea     r8, aP0; "_p0"
0x180039700  mov     edx, r14d; unsigned __int64
0x180039703  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180039708  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003970d  lea     r8, [rsp+270h+Name]; lpName
0x180039712  xor     edx, edx; bInheritHandle
0x180039714  mov     ecx, 1F0003h; dwDesiredAccess
0x180039719  call    cs:__imp_OpenSemaphoreW
0x180039720  nop     dword ptr [rax+rax+00h]
0x180039725  mov     [rsp+270h+var_240], rax
0x18003972a  test    rax, rax
0x18003972d  jnz     short loc_180039762
0x18003972f  call    cs:__imp_GetLastError
0x180039736  nop     dword ptr [rax+rax+00h]
0x18003973b  cmp     eax, 2
0x18003973e  jz      loc_18003984F
0x180039744  mov     rcx, [rbp+178h]; this
0x18003974b  lea     r8, aWil; "wil"
0x180039752  lea     edx, [r14-34h]; void *
0x180039756  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003975b  mov     ebx, eax
0x18003975d  jmp     loc_180039851
0x180039762  lea     rdx, [rsp+270h+var_24C]; int *
0x180039767  mov     [rsp+270h+var_24C], 0
0x18003976f  mov     rcx, rax; hHandle
0x180039772  mov     [rsp+270h+var_250], 0; int
0x18003977a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18003977f  mov     ebx, eax
0x180039781  test    eax, eax
0x180039783  jns     short loc_1800397A5
0x180039785  mov     rcx, [rbp+178h]; this
0x18003978c  lea     r8, aWil; "wil"
0x180039793  mov     r9d, eax; char *
0x180039796  mov     edx, 0D6h; void *
0x18003979b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800397a0  jmp     loc_180039851
0x1800397a5  lea     r8, asc_1800DFCB8; "h"
0x1800397ac  mov     rdx, r14; unsigned __int64
0x1800397af  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800397b4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800397b9  lea     r8, [rsp+270h+Name]; lpName
0x1800397be  xor     edx, edx; bInheritHandle
0x1800397c0  mov     ecx, 1F0003h; dwDesiredAccess
0x1800397c5  call    cs:__imp_OpenSemaphoreW
0x1800397cc  nop     dword ptr [rax+rax+00h]
0x1800397d1  mov     [rsp+270h+var_248], rax
0x1800397d6  test    rax, rax
0x1800397d9  jnz     short loc_180039801
0x1800397db  mov     rcx, [rbp+178h]; this
0x1800397e2  lea     r8, aWil; "wil"
0x1800397e9  mov     edx, 0DCh; void *
0x1800397ee  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800397f3  mov     ebx, eax
0x1800397f5  lea     rcx, [rsp+270h+var_248]
0x1800397fa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800397ff  jmp     short loc_180039851
0x180039801  lea     rdx, [rsp+270h+var_250]; int *
0x180039806  mov     rcx, rax; hHandle
0x180039809  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18003980e  mov     ebx, eax
0x180039810  test    eax, eax
0x180039812  jns     short loc_180039831
0x180039814  mov     rcx, [rbp+178h]; this
0x18003981b  lea     r8, aWil; "wil"
0x180039822  mov     r9d, eax; char *
0x180039825  mov     edx, 0DEh; void *
0x18003982a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003982f  jmp     short loc_1800397F5
0x180039831  lea     rcx, [rsp+270h+var_248]
0x180039836  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003983b  movsxd  rcx, [rsp+270h+var_250]
0x180039840  movsxd  rax, [rsp+270h+var_24C]
0x180039845  shl     rcx, 1Fh
0x180039849  or      rcx, rax
0x18003984c  mov     [rdi], rcx
0x18003984f  xor     ebx, ebx
0x180039851  lea     rcx, [rsp+270h+var_240]
0x180039856  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003985b  mov     eax, ebx
0x18003985d  mov     rcx, [rbp+170h+var_20]
0x180039864  xor     rcx, rsp; StackCookie
0x180039867  call    __security_check_cookie
0x18003986c  mov     rbx, [rsp+270h+arg_8]
0x180039874  add     rsp, 260h
0x18003987b  pop     r14
0x18003987d  pop     rdi
0x18003987e  pop     rbp
0x18003987f  retn
```
