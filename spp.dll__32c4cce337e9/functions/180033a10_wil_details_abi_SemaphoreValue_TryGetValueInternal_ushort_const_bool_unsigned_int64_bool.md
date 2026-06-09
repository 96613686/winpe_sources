# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180033a10`
- end: `0x180033bb2`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18003399c`

## callees

- `0x180026cf4`
- `0x180027d5c`
- `0x1800305ec`
- `0x180031914`
- `0x180033224`
- `0x180033244`
- `0x180033a10`
- `0x180035bd0`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x180033a79`
- `KERNEL32!OpenSemaphoreW` at `0x180033b0b`
- `KERNEL32!OpenSemaphoreW` at `0x180033a79`
- `KERNEL32!OpenSemaphoreW` at `0x180033b0b`
- `KERNEL32!GetLastError` at `0x180033a89`
- `KERNEL32!GetLastError` at `0x180033a89`

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
0x180033a10  mov     [rsp-8+arg_8], rbx
0x180033a15  push    rbp
0x180033a16  push    rdi
0x180033a17  push    r14
0x180033a19  lea     rbp, [rsp-160h]
0x180033a21  sub     rsp, 260h
0x180033a28  mov     rax, cs:__security_cookie
0x180033a2f  xor     rax, rsp
0x180033a32  mov     [rbp+170h+var_20], rax
0x180033a39  mov     rdi, r8
0x180033a3c  mov     qword ptr [r8], 0
0x180033a43  mov     r8, rcx; unsigned __int16 *
0x180033a46  mov     r14d, 104h
0x180033a4c  mov     edx, r14d; unsigned __int64
0x180033a4f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180033a54  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180033a59  lea     r8, aP0; "_p0"
0x180033a60  mov     edx, r14d; unsigned __int64
0x180033a63  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180033a68  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180033a6d  lea     r8, [rsp+270h+Name]; lpName
0x180033a72  xor     edx, edx; bInheritHandle
0x180033a74  mov     ecx, 1F0003h; dwDesiredAccess
0x180033a79  call    cs:__imp_OpenSemaphoreW
0x180033a7f  mov     [rsp+270h+var_240], rax
0x180033a84  test    rax, rax
0x180033a87  jnz     short loc_180033AAF
0x180033a89  call    cs:__imp_GetLastError
0x180033a8f  cmp     eax, 2
0x180033a92  jz      loc_180033B81
0x180033a98  mov     rcx, [rbp+178h]; this
0x180033a9f  lea     edx, [r14-34h]; void *
0x180033aa3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180033aa8  mov     ebx, eax
0x180033aaa  jmp     loc_180033B83
0x180033aaf  lea     rdx, [rsp+270h+var_24C]; int *
0x180033ab4  mov     [rsp+270h+var_24C], 0
0x180033abc  mov     rcx, rax; hHandle
0x180033abf  mov     [rsp+270h+var_250], 0; int
0x180033ac7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180033acc  mov     ebx, eax
0x180033ace  test    eax, eax
0x180033ad0  jns     short loc_180033AEB
0x180033ad2  mov     rcx, [rbp+178h]; this
0x180033ad9  mov     r9d, eax; char *
0x180033adc  mov     edx, 0D6h; void *
0x180033ae1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033ae6  jmp     loc_180033B83
0x180033aeb  lea     r8, asc_18003DAC0; "h"
0x180033af2  mov     rdx, r14; unsigned __int64
0x180033af5  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180033afa  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180033aff  lea     r8, [rsp+270h+Name]; lpName
0x180033b04  xor     edx, edx; bInheritHandle
0x180033b06  mov     ecx, 1F0003h; dwDesiredAccess
0x180033b0b  call    cs:__imp_OpenSemaphoreW
0x180033b11  mov     [rsp+270h+var_248], rax
0x180033b16  test    rax, rax
0x180033b19  jnz     short loc_180033B3A
0x180033b1b  mov     rcx, [rbp+178h]; this
0x180033b22  mov     edx, 0DCh; void *
0x180033b27  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180033b2c  mov     ebx, eax
0x180033b2e  lea     rcx, [rsp+270h+var_248]
0x180033b33  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180033b38  jmp     short loc_180033B83
0x180033b3a  lea     rdx, [rsp+270h+var_250]; int *
0x180033b3f  mov     rcx, rax; hHandle
0x180033b42  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180033b47  mov     ebx, eax
0x180033b49  test    eax, eax
0x180033b4b  jns     short loc_180033B63
0x180033b4d  mov     rcx, [rbp+178h]; this
0x180033b54  mov     r9d, eax; char *
0x180033b57  mov     edx, 0DEh; void *
0x180033b5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033b61  jmp     short loc_180033B2E
0x180033b63  lea     rcx, [rsp+270h+var_248]
0x180033b68  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180033b6d  movsxd  rcx, [rsp+270h+var_250]
0x180033b72  movsxd  rax, [rsp+270h+var_24C]
0x180033b77  shl     rcx, 1Fh
0x180033b7b  or      rcx, rax
0x180033b7e  mov     [rdi], rcx
0x180033b81  xor     ebx, ebx
0x180033b83  lea     rcx, [rsp+270h+var_240]
0x180033b88  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180033b8d  mov     eax, ebx
0x180033b8f  mov     rcx, [rbp+170h+var_20]
0x180033b96  xor     rcx, rsp; StackCookie
0x180033b99  call    __security_check_cookie
0x180033b9e  mov     rbx, [rsp+270h+arg_8]
0x180033ba6  add     rsp, 260h
0x180033bad  pop     r14
0x180033baf  pop     rdi
0x180033bb0  pop     rbp
0x180033bb1  retn
```
