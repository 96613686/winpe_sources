# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800460dc`
- end: `0x180046291`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `437`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180046064`

## callees

- `0x180014550`
- `0x180015740`
- `0x18003cb60`
- `0x18003f2fc`
- `0x180042384`
- `0x1800450e0`
- `0x180045100`
- `0x1800460dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180046145`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800461e3`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180046145`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800461e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004615b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004615b`

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
0x1800460dc  mov     [rsp-8+arg_8], rbx
0x1800460e1  push    rbp
0x1800460e2  push    rdi
0x1800460e3  push    r14
0x1800460e5  lea     rbp, [rsp-160h]
0x1800460ed  sub     rsp, 260h
0x1800460f4  mov     rax, cs:__security_cookie
0x1800460fb  xor     rax, rsp
0x1800460fe  mov     [rbp+170h+var_20], rax
0x180046105  mov     rdi, r8
0x180046108  mov     qword ptr [r8], 0
0x18004610f  mov     r8, rcx; unsigned __int16 *
0x180046112  mov     r14d, 104h
0x180046118  mov     edx, r14d; unsigned __int64
0x18004611b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180046120  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180046125  lea     r8, aP0; "_p0"
0x18004612c  mov     edx, r14d; unsigned __int64
0x18004612f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180046134  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180046139  lea     r8, [rsp+270h+Name]; lpName
0x18004613e  xor     edx, edx; bInheritHandle
0x180046140  mov     ecx, 1F0003h; dwDesiredAccess
0x180046145  call    cs:__imp_OpenSemaphoreW
0x18004614c  nop     dword ptr [rax+rax+00h]
0x180046151  mov     [rsp+270h+var_240], rax
0x180046156  test    rax, rax
0x180046159  jnz     short loc_180046187
0x18004615b  call    cs:__imp_GetLastError
0x180046162  nop     dword ptr [rax+rax+00h]
0x180046167  cmp     eax, 2
0x18004616a  jz      loc_18004625F
0x180046170  mov     rcx, [rbp+178h]; this
0x180046177  lea     edx, [r14-34h]; void *
0x18004617b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180046180  mov     ebx, eax
0x180046182  jmp     loc_180046261
0x180046187  lea     rdx, [rsp+270h+var_24C]; int *
0x18004618c  mov     [rsp+270h+var_24C], 0
0x180046194  mov     rcx, rax; hHandle
0x180046197  mov     [rsp+270h+var_250], 0; int
0x18004619f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800461a4  mov     ebx, eax
0x1800461a6  test    eax, eax
0x1800461a8  jns     short loc_1800461C3
0x1800461aa  mov     rcx, [rbp+178h]; this
0x1800461b1  mov     r9d, eax; char *
0x1800461b4  mov     edx, 0D6h; void *
0x1800461b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800461be  jmp     loc_180046261
0x1800461c3  lea     r8, asc_180068AC0; "h"
0x1800461ca  mov     rdx, r14; unsigned __int64
0x1800461cd  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800461d2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800461d7  lea     r8, [rsp+270h+Name]; lpName
0x1800461dc  xor     edx, edx; bInheritHandle
0x1800461de  mov     ecx, 1F0003h; dwDesiredAccess
0x1800461e3  call    cs:__imp_OpenSemaphoreW
0x1800461ea  nop     dword ptr [rax+rax+00h]
0x1800461ef  mov     [rsp+270h+var_248], rax
0x1800461f4  test    rax, rax
0x1800461f7  jnz     short loc_180046218
0x1800461f9  mov     rcx, [rbp+178h]; this
0x180046200  mov     edx, 0DCh; void *
0x180046205  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004620a  mov     ebx, eax
0x18004620c  lea     rcx, [rsp+270h+var_248]
0x180046211  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180046216  jmp     short loc_180046261
0x180046218  lea     rdx, [rsp+270h+var_250]; int *
0x18004621d  mov     rcx, rax; hHandle
0x180046220  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180046225  mov     ebx, eax
0x180046227  test    eax, eax
0x180046229  jns     short loc_180046241
0x18004622b  mov     rcx, [rbp+178h]; this
0x180046232  mov     r9d, eax; char *
0x180046235  mov     edx, 0DEh; void *
0x18004623a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004623f  jmp     short loc_18004620C
0x180046241  lea     rcx, [rsp+270h+var_248]
0x180046246  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004624b  movsxd  rcx, [rsp+270h+var_250]
0x180046250  movsxd  rax, [rsp+270h+var_24C]
0x180046255  shl     rcx, 1Fh
0x180046259  or      rcx, rax
0x18004625c  mov     [rdi], rcx
0x18004625f  xor     ebx, ebx
0x180046261  lea     rcx, [rsp+270h+var_240]
0x180046266  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004626b  mov     eax, ebx
0x18004626d  mov     rcx, [rbp+170h+var_20]
0x180046274  xor     rcx, rsp; StackCookie
0x180046277  call    __security_check_cookie
0x18004627c  mov     rbx, [rsp+270h+arg_8]
0x180046284  add     rsp, 260h
0x18004628b  pop     r14
0x18004628d  pop     rdi
0x18004628e  pop     rbp
0x18004628f  retn
```
