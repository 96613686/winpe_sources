# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800124cc`
- end: `0x18001269d`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `465`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180012448`

## callees

- `0x18000778c`
- `0x18000db08`
- `0x18000db88`
- `0x18000dc30`
- `0x18000e640`
- `0x18001145c`
- `0x180011a58`
- `0x1800124cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180012535`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800125e1`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180012535`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800125e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001254b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001254b`

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
0x1800124cc  mov     [rsp-8+arg_8], rbx
0x1800124d1  push    rbp
0x1800124d2  push    rdi
0x1800124d3  push    r14
0x1800124d5  lea     rbp, [rsp-160h]
0x1800124dd  sub     rsp, 260h
0x1800124e4  mov     rax, cs:__security_cookie
0x1800124eb  xor     rax, rsp
0x1800124ee  mov     [rbp+170h+var_20], rax
0x1800124f5  mov     rdi, r8
0x1800124f8  mov     qword ptr [r8], 0
0x1800124ff  mov     r8, rcx; unsigned __int16 *
0x180012502  mov     r14d, 104h
0x180012508  mov     edx, r14d; unsigned __int64
0x18001250b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180012510  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180012515  lea     r8, aP0; "_p0"
0x18001251c  mov     edx, r14d; unsigned __int64
0x18001251f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180012524  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180012529  lea     r8, [rsp+270h+Name]; lpName
0x18001252e  xor     edx, edx; bInheritHandle
0x180012530  mov     ecx, 1F0003h; dwDesiredAccess
0x180012535  call    cs:__imp_OpenSemaphoreW
0x18001253c  nop     dword ptr [rax+rax+00h]
0x180012541  mov     [rsp+270h+var_240], rax
0x180012546  test    rax, rax
0x180012549  jnz     short loc_18001257E
0x18001254b  call    cs:__imp_GetLastError
0x180012552  nop     dword ptr [rax+rax+00h]
0x180012557  cmp     eax, 2
0x18001255a  jz      loc_18001266B
0x180012560  mov     rcx, [rbp+178h]; this
0x180012567  lea     r8, aWil; "wil"
0x18001256e  lea     edx, [r14-34h]; void *
0x180012572  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180012577  mov     ebx, eax
0x180012579  jmp     loc_18001266D
0x18001257e  lea     rdx, [rsp+270h+var_24C]; int *
0x180012583  mov     [rsp+270h+var_24C], 0
0x18001258b  mov     rcx, rax; hHandle
0x18001258e  mov     [rsp+270h+var_250], 0; int
0x180012596  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001259b  mov     ebx, eax
0x18001259d  test    eax, eax
0x18001259f  jns     short loc_1800125C1
0x1800125a1  mov     rcx, [rbp+178h]; this
0x1800125a8  lea     r8, aWil; "wil"
0x1800125af  mov     r9d, eax; char *
0x1800125b2  mov     edx, 0D6h; void *
0x1800125b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800125bc  jmp     loc_18001266D
0x1800125c1  lea     r8, asc_1800202F8; "h"
0x1800125c8  mov     rdx, r14; unsigned __int64
0x1800125cb  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800125d0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800125d5  lea     r8, [rsp+270h+Name]; lpName
0x1800125da  xor     edx, edx; bInheritHandle
0x1800125dc  mov     ecx, 1F0003h; dwDesiredAccess
0x1800125e1  call    cs:__imp_OpenSemaphoreW
0x1800125e8  nop     dword ptr [rax+rax+00h]
0x1800125ed  mov     [rsp+270h+var_248], rax
0x1800125f2  test    rax, rax
0x1800125f5  jnz     short loc_18001261D
0x1800125f7  mov     rcx, [rbp+178h]; this
0x1800125fe  lea     r8, aWil; "wil"
0x180012605  mov     edx, 0DCh; void *
0x18001260a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001260f  mov     ebx, eax
0x180012611  lea     rcx, [rsp+270h+var_248]
0x180012616  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001261b  jmp     short loc_18001266D
0x18001261d  lea     rdx, [rsp+270h+var_250]; int *
0x180012622  mov     rcx, rax; hHandle
0x180012625  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001262a  mov     ebx, eax
0x18001262c  test    eax, eax
0x18001262e  jns     short loc_18001264D
0x180012630  mov     rcx, [rbp+178h]; this
0x180012637  lea     r8, aWil; "wil"
0x18001263e  mov     r9d, eax; char *
0x180012641  mov     edx, 0DEh; void *
0x180012646  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001264b  jmp     short loc_180012611
0x18001264d  lea     rcx, [rsp+270h+var_248]
0x180012652  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180012657  movsxd  rcx, [rsp+270h+var_250]
0x18001265c  movsxd  rax, [rsp+270h+var_24C]
0x180012661  shl     rcx, 1Fh
0x180012665  or      rcx, rax
0x180012668  mov     [rdi], rcx
0x18001266b  xor     ebx, ebx
0x18001266d  lea     rcx, [rsp+270h+var_240]
0x180012672  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180012677  mov     eax, ebx
0x180012679  mov     rcx, [rbp+170h+var_20]
0x180012680  xor     rcx, rsp; StackCookie
0x180012683  call    __security_check_cookie
0x180012688  mov     rbx, [rsp+270h+arg_8]
0x180012690  add     rsp, 260h
0x180012697  pop     r14
0x180012699  pop     rdi
0x18001269a  pop     rbp
0x18001269b  retn
```
