# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180060ac4`
- end: `0x180060c66`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180060a50`

## callees

- `0x18002a9e0`
- `0x18002ae80`
- `0x180055e94`
- `0x18005c730`
- `0x18005de7c`
- `0x18005f8fc`
- `0x180060ac4`
- `0x18007e6d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060b3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060b3d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180060b2d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180060bbf`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180060b2d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180060bbf`

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
0x180060ac4  mov     [rsp-8+arg_8], rbx
0x180060ac9  push    rbp
0x180060aca  push    rdi
0x180060acb  push    r14
0x180060acd  lea     rbp, [rsp-160h]
0x180060ad5  sub     rsp, 260h
0x180060adc  mov     rax, cs:__security_cookie
0x180060ae3  xor     rax, rsp
0x180060ae6  mov     [rbp+170h+var_20], rax
0x180060aed  mov     rdi, r8
0x180060af0  mov     qword ptr [r8], 0
0x180060af7  mov     r8, rcx; unsigned __int16 *
0x180060afa  mov     r14d, 104h
0x180060b00  mov     edx, r14d; unsigned __int64
0x180060b03  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180060b08  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180060b0d  lea     r8, aP0; "_p0"
0x180060b14  mov     edx, r14d; unsigned __int64
0x180060b17  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180060b1c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180060b21  lea     r8, [rsp+270h+Name]; lpName
0x180060b26  xor     edx, edx; bInheritHandle
0x180060b28  mov     ecx, 1F0003h; dwDesiredAccess
0x180060b2d  call    cs:__imp_OpenSemaphoreW
0x180060b33  mov     [rsp+270h+var_240], rax
0x180060b38  test    rax, rax
0x180060b3b  jnz     short loc_180060B63
0x180060b3d  call    cs:__imp_GetLastError
0x180060b43  cmp     eax, 2
0x180060b46  jz      loc_180060C35
0x180060b4c  mov     rcx, [rbp+178h]; this
0x180060b53  lea     edx, [r14-34h]; void *
0x180060b57  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180060b5c  mov     ebx, eax
0x180060b5e  jmp     loc_180060C37
0x180060b63  lea     rdx, [rsp+270h+var_24C]; int *
0x180060b68  mov     [rsp+270h+var_24C], 0
0x180060b70  mov     rcx, rax; hHandle
0x180060b73  mov     [rsp+270h+var_250], 0; int
0x180060b7b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180060b80  mov     ebx, eax
0x180060b82  test    eax, eax
0x180060b84  jns     short loc_180060B9F
0x180060b86  mov     rcx, [rbp+178h]; this
0x180060b8d  mov     r9d, eax; char *
0x180060b90  mov     edx, 0D6h; void *
0x180060b95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180060b9a  jmp     loc_180060C37
0x180060b9f  lea     r8, asc_1800A66B8; "h"
0x180060ba6  mov     rdx, r14; unsigned __int64
0x180060ba9  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180060bae  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180060bb3  lea     r8, [rsp+270h+Name]; lpName
0x180060bb8  xor     edx, edx; bInheritHandle
0x180060bba  mov     ecx, 1F0003h; dwDesiredAccess
0x180060bbf  call    cs:__imp_OpenSemaphoreW
0x180060bc5  mov     [rsp+270h+var_248], rax
0x180060bca  test    rax, rax
0x180060bcd  jnz     short loc_180060BEE
0x180060bcf  mov     rcx, [rbp+178h]; this
0x180060bd6  mov     edx, 0DCh; void *
0x180060bdb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180060be0  mov     ebx, eax
0x180060be2  lea     rcx, [rsp+270h+var_248]
0x180060be7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180060bec  jmp     short loc_180060C37
0x180060bee  lea     rdx, [rsp+270h+var_250]; int *
0x180060bf3  mov     rcx, rax; hHandle
0x180060bf6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180060bfb  mov     ebx, eax
0x180060bfd  test    eax, eax
0x180060bff  jns     short loc_180060C17
0x180060c01  mov     rcx, [rbp+178h]; this
0x180060c08  mov     r9d, eax; char *
0x180060c0b  mov     edx, 0DEh; void *
0x180060c10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180060c15  jmp     short loc_180060BE2
0x180060c17  lea     rcx, [rsp+270h+var_248]
0x180060c1c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180060c21  movsxd  rcx, [rsp+270h+var_250]
0x180060c26  movsxd  rax, [rsp+270h+var_24C]
0x180060c2b  shl     rcx, 1Fh
0x180060c2f  or      rcx, rax
0x180060c32  mov     [rdi], rcx
0x180060c35  xor     ebx, ebx
0x180060c37  lea     rcx, [rsp+270h+var_240]
0x180060c3c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180060c41  mov     eax, ebx
0x180060c43  mov     rcx, [rbp+170h+var_20]
0x180060c4a  xor     rcx, rsp; StackCookie
0x180060c4d  call    __security_check_cookie
0x180060c52  mov     rbx, [rsp+270h+arg_8]
0x180060c5a  add     rsp, 260h
0x180060c61  pop     r14
0x180060c63  pop     rdi
0x180060c64  pop     rbp
0x180060c65  retn
```
