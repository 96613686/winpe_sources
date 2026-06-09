# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800097ac`
- end: `0x18000996a`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `446`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180009728`

## callees

- `0x180004fdc`
- `0x180005cc0`
- `0x1800078b0`
- `0x1800084b4`
- `0x180008fd4`
- `0x1800094f0`
- `0x18000957c`
- `0x1800097ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009815`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800098b5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009815`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800098b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009825`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009825`

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
0x1800097ac  mov     [rsp-8+arg_8], rbx
0x1800097b1  push    rbp
0x1800097b2  push    rdi
0x1800097b3  push    r14
0x1800097b5  lea     rbp, [rsp-160h]
0x1800097bd  sub     rsp, 260h
0x1800097c4  mov     rax, cs:__security_cookie
0x1800097cb  xor     rax, rsp
0x1800097ce  mov     [rbp+170h+var_20], rax
0x1800097d5  mov     rdi, r8
0x1800097d8  mov     qword ptr [r8], 0
0x1800097df  mov     r8, rcx; unsigned __int16 *
0x1800097e2  mov     r14d, 104h
0x1800097e8  mov     edx, r14d; unsigned __int64
0x1800097eb  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800097f0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800097f5  lea     r8, aP0; "_p0"
0x1800097fc  mov     edx, r14d; unsigned __int64
0x1800097ff  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180009804  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009809  lea     r8, [rsp+270h+Name]; lpName
0x18000980e  xor     edx, edx; bInheritHandle
0x180009810  mov     ecx, 1F0003h; dwDesiredAccess
0x180009815  call    cs:__imp_OpenSemaphoreW
0x18000981b  mov     [rsp+270h+var_240], rax
0x180009820  test    rax, rax
0x180009823  jnz     short loc_180009852
0x180009825  call    cs:__imp_GetLastError
0x18000982b  cmp     eax, 2
0x18000982e  jz      loc_180009939
0x180009834  mov     rcx, [rbp+178h]; this
0x18000983b  lea     r8, aWil; "wil"
0x180009842  lea     edx, [r14-34h]; void *
0x180009846  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000984b  mov     ebx, eax
0x18000984d  jmp     loc_18000993B
0x180009852  lea     rdx, [rsp+270h+var_24C]; int *
0x180009857  mov     [rsp+270h+var_24C], 0
0x18000985f  mov     rcx, rax; hHandle
0x180009862  mov     [rsp+270h+var_250], 0; int
0x18000986a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000986f  mov     ebx, eax
0x180009871  test    eax, eax
0x180009873  jns     short loc_180009895
0x180009875  mov     rcx, [rbp+178h]; this
0x18000987c  lea     r8, aWil; "wil"
0x180009883  mov     r9d, eax; char *
0x180009886  mov     edx, 0D6h; void *
0x18000988b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009890  jmp     loc_18000993B
0x180009895  lea     r8, asc_180036128; "h"
0x18000989c  mov     rdx, r14; unsigned __int64
0x18000989f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800098a4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800098a9  lea     r8, [rsp+270h+Name]; lpName
0x1800098ae  xor     edx, edx; bInheritHandle
0x1800098b0  mov     ecx, 1F0003h; dwDesiredAccess
0x1800098b5  call    cs:__imp_OpenSemaphoreW
0x1800098bb  mov     [rsp+270h+var_248], rax
0x1800098c0  test    rax, rax
0x1800098c3  jnz     short loc_1800098EB
0x1800098c5  mov     rcx, [rbp+178h]; this
0x1800098cc  lea     r8, aWil; "wil"
0x1800098d3  mov     edx, 0DCh; void *
0x1800098d8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800098dd  mov     ebx, eax
0x1800098df  lea     rcx, [rsp+270h+var_248]
0x1800098e4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800098e9  jmp     short loc_18000993B
0x1800098eb  lea     rdx, [rsp+270h+var_250]; int *
0x1800098f0  mov     rcx, rax; hHandle
0x1800098f3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800098f8  mov     ebx, eax
0x1800098fa  test    eax, eax
0x1800098fc  jns     short loc_18000991B
0x1800098fe  mov     rcx, [rbp+178h]; this
0x180009905  lea     r8, aWil; "wil"
0x18000990c  mov     r9d, eax; char *
0x18000990f  mov     edx, 0DEh; void *
0x180009914  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009919  jmp     short loc_1800098DF
0x18000991b  lea     rcx, [rsp+270h+var_248]
0x180009920  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009925  movsxd  rcx, [rsp+270h+var_250]
0x18000992a  movsxd  rax, [rsp+270h+var_24C]
0x18000992f  shl     rcx, 1Fh
0x180009933  or      rcx, rax
0x180009936  mov     [rdi], rcx
0x180009939  xor     ebx, ebx
0x18000993b  lea     rcx, [rsp+270h+var_240]
0x180009940  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009945  mov     eax, ebx
0x180009947  mov     rcx, [rbp+170h+var_20]
0x18000994e  xor     rcx, rsp; StackCookie
0x180009951  call    __security_check_cookie
0x180009956  mov     rbx, [rsp+270h+arg_8]
0x18000995e  add     rsp, 260h
0x180009965  pop     r14
0x180009967  pop     rdi
0x180009968  pop     rbp
0x180009969  retn
```
