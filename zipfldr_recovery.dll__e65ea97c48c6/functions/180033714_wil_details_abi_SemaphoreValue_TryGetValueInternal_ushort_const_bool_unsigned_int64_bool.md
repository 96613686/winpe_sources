# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180033714`
- end: `0x1800338d2`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `446`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18003a89c`

## callees

- `0x18000f530`
- `0x180010c30`
- `0x180031e94`
- `0x180033714`
- `0x1800338d8`
- `0x180033aa8`
- `0x180036f50`
- `0x180039fa4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003377d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003381d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003377d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003381d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003378d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003378d`

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
        (const char *)(unsigned int)ValueFromSemaphore);
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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v11);
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
0x180033714  mov     [rsp-8+arg_8], rbx
0x180033719  push    rbp
0x18003371a  push    rdi
0x18003371b  push    r14
0x18003371d  lea     rbp, [rsp-160h]
0x180033725  sub     rsp, 260h
0x18003372c  mov     rax, cs:__security_cookie
0x180033733  xor     rax, rsp
0x180033736  mov     [rbp+170h+var_20], rax
0x18003373d  mov     rdi, r8
0x180033740  mov     qword ptr [r8], 0
0x180033747  mov     r8, rcx; unsigned __int16 *
0x18003374a  mov     r14d, 104h
0x180033750  mov     edx, r14d; unsigned __int64
0x180033753  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180033758  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003375d  lea     r8, aP0; "_p0"
0x180033764  mov     edx, r14d; unsigned __int64
0x180033767  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003376c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180033771  lea     r8, [rsp+270h+Name]; lpName
0x180033776  xor     edx, edx; bInheritHandle
0x180033778  mov     ecx, 1F0003h; dwDesiredAccess
0x18003377d  call    cs:__imp_OpenSemaphoreW
0x180033783  mov     [rsp+270h+var_240], rax
0x180033788  test    rax, rax
0x18003378b  jnz     short loc_1800337BA
0x18003378d  call    cs:__imp_GetLastError
0x180033793  cmp     eax, 2
0x180033796  jz      loc_1800338A1
0x18003379c  mov     rcx, [rbp+178h]; this
0x1800337a3  lea     r8, aWil; "wil"
0x1800337aa  lea     edx, [r14-34h]; void *
0x1800337ae  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800337b3  mov     ebx, eax
0x1800337b5  jmp     loc_1800338A3
0x1800337ba  lea     rdx, [rsp+270h+var_24C]; int *
0x1800337bf  mov     [rsp+270h+var_24C], 0
0x1800337c7  mov     rcx, rax; hHandle
0x1800337ca  mov     [rsp+270h+var_250], 0
0x1800337d2  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800337d7  mov     ebx, eax
0x1800337d9  test    eax, eax
0x1800337db  jns     short loc_1800337FD
0x1800337dd  mov     rcx, [rbp+178h]
0x1800337e4  lea     r8, aWil; "wil"
0x1800337eb  mov     r9d, eax
0x1800337ee  mov     edx, 0D6h
0x1800337f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800337f8  jmp     loc_1800338A3
0x1800337fd  lea     r8, asc_180079278; "h"
0x180033804  mov     rdx, r14; unsigned __int64
0x180033807  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003380c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180033811  lea     r8, [rsp+270h+Name]; lpName
0x180033816  xor     edx, edx; bInheritHandle
0x180033818  mov     ecx, 1F0003h; dwDesiredAccess
0x18003381d  call    cs:__imp_OpenSemaphoreW
0x180033823  mov     [rsp+270h+var_248], rax
0x180033828  test    rax, rax
0x18003382b  jnz     short loc_180033853
0x18003382d  mov     rcx, [rbp+178h]; this
0x180033834  lea     r8, aWil; "wil"
0x18003383b  mov     edx, 0DCh; void *
0x180033840  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180033845  mov     ebx, eax
0x180033847  lea     rcx, [rsp+270h+var_248]
0x18003384c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180033851  jmp     short loc_1800338A3
0x180033853  lea     rdx, [rsp+270h+var_250]; int *
0x180033858  mov     rcx, rax; hHandle
0x18003385b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180033860  mov     ebx, eax
0x180033862  test    eax, eax
0x180033864  jns     short loc_180033883
0x180033866  mov     rcx, [rbp+178h]
0x18003386d  lea     r8, aWil; "wil"
0x180033874  mov     r9d, eax
0x180033877  mov     edx, 0DEh
0x18003387c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033881  jmp     short loc_180033847
0x180033883  lea     rcx, [rsp+270h+var_248]
0x180033888  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003388d  movsxd  rcx, [rsp+270h+var_250]
0x180033892  movsxd  rax, [rsp+270h+var_24C]
0x180033897  shl     rcx, 1Fh
0x18003389b  or      rcx, rax
0x18003389e  mov     [rdi], rcx
0x1800338a1  xor     ebx, ebx
0x1800338a3  lea     rcx, [rsp+270h+var_240]
0x1800338a8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800338ad  mov     eax, ebx
0x1800338af  mov     rcx, [rbp+170h+var_20]
0x1800338b6  xor     rcx, rsp; StackCookie
0x1800338b9  call    __security_check_cookie
0x1800338be  mov     rbx, [rsp+270h+arg_8]
0x1800338c6  add     rsp, 260h
0x1800338cd  pop     r14
0x1800338cf  pop     rdi
0x1800338d0  pop     rbp
0x1800338d1  retn
```
