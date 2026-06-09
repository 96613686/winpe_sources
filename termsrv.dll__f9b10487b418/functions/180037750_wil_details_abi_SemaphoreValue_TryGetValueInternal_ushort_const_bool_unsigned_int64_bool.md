# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180037750`
- end: `0x18003790e`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `446`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800359b8`

## callees

- `0x1800127b0`
- `0x180024d34`
- `0x1800321f0`
- `0x180035898`
- `0x180036578`
- `0x180036fa4`
- `0x18003747c`
- `0x180037750`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800377b9`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180037859`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800377b9`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180037859`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800377c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800377c9`

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
0x180037750  mov     [rsp-8+arg_8], rbx
0x180037755  push    rbp
0x180037756  push    rdi
0x180037757  push    r14
0x180037759  lea     rbp, [rsp-160h]
0x180037761  sub     rsp, 260h
0x180037768  mov     rax, cs:__security_cookie
0x18003776f  xor     rax, rsp
0x180037772  mov     [rbp+170h+var_20], rax
0x180037779  mov     rdi, r8
0x18003777c  mov     qword ptr [r8], 0
0x180037783  mov     r8, rcx; unsigned __int16 *
0x180037786  mov     r14d, 104h
0x18003778c  mov     edx, r14d; unsigned __int64
0x18003778f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180037794  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180037799  lea     r8, aP0; "_p0"
0x1800377a0  mov     edx, r14d; unsigned __int64
0x1800377a3  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800377a8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800377ad  lea     r8, [rsp+270h+Name]; lpName
0x1800377b2  xor     edx, edx; bInheritHandle
0x1800377b4  mov     ecx, 1F0003h; dwDesiredAccess
0x1800377b9  call    cs:__imp_OpenSemaphoreW
0x1800377bf  mov     [rsp+270h+var_240], rax
0x1800377c4  test    rax, rax
0x1800377c7  jnz     short loc_1800377F6
0x1800377c9  call    cs:__imp_GetLastError
0x1800377cf  cmp     eax, 2
0x1800377d2  jz      loc_1800378DD
0x1800377d8  mov     rcx, [rbp+178h]; this
0x1800377df  lea     r8, aWil; "wil"
0x1800377e6  lea     edx, [r14-34h]; void *
0x1800377ea  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800377ef  mov     ebx, eax
0x1800377f1  jmp     loc_1800378DF
0x1800377f6  lea     rdx, [rsp+270h+var_24C]; int *
0x1800377fb  mov     [rsp+270h+var_24C], 0
0x180037803  mov     rcx, rax; hHandle
0x180037806  mov     [rsp+270h+var_250], 0; int
0x18003780e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180037813  mov     ebx, eax
0x180037815  test    eax, eax
0x180037817  jns     short loc_180037839
0x180037819  mov     rcx, [rbp+178h]; this
0x180037820  lea     r8, aWil; "wil"
0x180037827  mov     r9d, eax; char *
0x18003782a  mov     edx, 0D6h; void *
0x18003782f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037834  jmp     loc_1800378DF
0x180037839  lea     r8, asc_1800D9C68; "h"
0x180037840  mov     rdx, r14; unsigned __int64
0x180037843  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180037848  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003784d  lea     r8, [rsp+270h+Name]; lpName
0x180037852  xor     edx, edx; bInheritHandle
0x180037854  mov     ecx, 1F0003h; dwDesiredAccess
0x180037859  call    cs:__imp_OpenSemaphoreW
0x18003785f  mov     [rsp+270h+var_248], rax
0x180037864  test    rax, rax
0x180037867  jnz     short loc_18003788F
0x180037869  mov     rcx, [rbp+178h]; this
0x180037870  lea     r8, aWil; "wil"
0x180037877  mov     edx, 0DCh; void *
0x18003787c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180037881  mov     ebx, eax
0x180037883  lea     rcx, [rsp+270h+var_248]
0x180037888  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003788d  jmp     short loc_1800378DF
0x18003788f  lea     rdx, [rsp+270h+var_250]; int *
0x180037894  mov     rcx, rax; hHandle
0x180037897  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18003789c  mov     ebx, eax
0x18003789e  test    eax, eax
0x1800378a0  jns     short loc_1800378BF
0x1800378a2  mov     rcx, [rbp+178h]; this
0x1800378a9  lea     r8, aWil; "wil"
0x1800378b0  mov     r9d, eax; char *
0x1800378b3  mov     edx, 0DEh; void *
0x1800378b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800378bd  jmp     short loc_180037883
0x1800378bf  lea     rcx, [rsp+270h+var_248]
0x1800378c4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800378c9  movsxd  rcx, [rsp+270h+var_250]
0x1800378ce  movsxd  rax, [rsp+270h+var_24C]
0x1800378d3  shl     rcx, 1Fh
0x1800378d7  or      rcx, rax
0x1800378da  mov     [rdi], rcx
0x1800378dd  xor     ebx, ebx
0x1800378df  lea     rcx, [rsp+270h+var_240]
0x1800378e4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800378e9  mov     eax, ebx
0x1800378eb  mov     rcx, [rbp+170h+var_20]
0x1800378f2  xor     rcx, rsp; StackCookie
0x1800378f5  call    __security_check_cookie
0x1800378fa  mov     rbx, [rsp+270h+arg_8]
0x180037902  add     rsp, 260h
0x180037909  pop     r14
0x18003790b  pop     rdi
0x18003790c  pop     rbp
0x18003790d  retn
```
