# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18002bc1c`
- end: `0x18002bdbe`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18002bba8`

## callees

- `0x18001bbec`
- `0x18001c724`
- `0x180026a30`
- `0x180028aa8`
- `0x180029b84`
- `0x18002b3f0`
- `0x18002b410`
- `0x18002bc1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002bc85`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002bd17`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002bc85`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002bd17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bc95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bc95`

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
  int v10; // r8d
  HANDLE v11; // rax
  unsigned int v12; // r8d
  const char *v13; // r9
  int v14; // eax
  int v15; // r8d
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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v10, (const char *)(unsigned int)ValueFromSemaphore);
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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v15, (const char *)(unsigned int)v14);
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
0x18002bc1c  mov     [rsp-8+arg_8], rbx
0x18002bc21  push    rbp
0x18002bc22  push    rdi
0x18002bc23  push    r14
0x18002bc25  lea     rbp, [rsp-160h]
0x18002bc2d  sub     rsp, 260h
0x18002bc34  mov     rax, cs:__security_cookie
0x18002bc3b  xor     rax, rsp
0x18002bc3e  mov     [rbp+170h+var_20], rax
0x18002bc45  mov     rdi, r8
0x18002bc48  mov     qword ptr [r8], 0
0x18002bc4f  mov     r8, rcx; unsigned __int16 *
0x18002bc52  mov     r14d, 104h
0x18002bc58  mov     edx, r14d; unsigned __int64
0x18002bc5b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002bc60  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002bc65  lea     r8, aP0; "_p0"
0x18002bc6c  mov     edx, r14d; unsigned __int64
0x18002bc6f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002bc74  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002bc79  lea     r8, [rsp+270h+Name]; lpName
0x18002bc7e  xor     edx, edx; bInheritHandle
0x18002bc80  mov     ecx, 1F0003h; dwDesiredAccess
0x18002bc85  call    cs:__imp_OpenSemaphoreW
0x18002bc8b  mov     [rsp+270h+var_240], rax
0x18002bc90  test    rax, rax
0x18002bc93  jnz     short loc_18002BCBB
0x18002bc95  call    cs:__imp_GetLastError
0x18002bc9b  cmp     eax, 2
0x18002bc9e  jz      loc_18002BD8D
0x18002bca4  mov     rcx, [rbp+178h]; this
0x18002bcab  lea     edx, [r14-34h]; void *
0x18002bcaf  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002bcb4  mov     ebx, eax
0x18002bcb6  jmp     loc_18002BD8F
0x18002bcbb  lea     rdx, [rsp+270h+var_24C]; int *
0x18002bcc0  mov     [rsp+270h+var_24C], 0
0x18002bcc8  mov     rcx, rax; hHandle
0x18002bccb  mov     [rsp+270h+var_250], 0; int
0x18002bcd3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18002bcd8  mov     ebx, eax
0x18002bcda  test    eax, eax
0x18002bcdc  jns     short loc_18002BCF7
0x18002bcde  mov     rcx, [rbp+178h]; this
0x18002bce5  mov     r9d, eax; char *
0x18002bce8  mov     edx, 0D6h; void *
0x18002bced  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bcf2  jmp     loc_18002BD8F
0x18002bcf7  lea     r8, asc_18003A508; "h"
0x18002bcfe  mov     rdx, r14; unsigned __int64
0x18002bd01  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002bd06  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002bd0b  lea     r8, [rsp+270h+Name]; lpName
0x18002bd10  xor     edx, edx; bInheritHandle
0x18002bd12  mov     ecx, 1F0003h; dwDesiredAccess
0x18002bd17  call    cs:__imp_OpenSemaphoreW
0x18002bd1d  mov     [rsp+270h+var_248], rax
0x18002bd22  test    rax, rax
0x18002bd25  jnz     short loc_18002BD46
0x18002bd27  mov     rcx, [rbp+178h]; this
0x18002bd2e  mov     edx, 0DCh; void *
0x18002bd33  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002bd38  mov     ebx, eax
0x18002bd3a  lea     rcx, [rsp+270h+var_248]
0x18002bd3f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002bd44  jmp     short loc_18002BD8F
0x18002bd46  lea     rdx, [rsp+270h+var_250]; int *
0x18002bd4b  mov     rcx, rax; hHandle
0x18002bd4e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18002bd53  mov     ebx, eax
0x18002bd55  test    eax, eax
0x18002bd57  jns     short loc_18002BD6F
0x18002bd59  mov     rcx, [rbp+178h]; this
0x18002bd60  mov     r9d, eax; char *
0x18002bd63  mov     edx, 0DEh; void *
0x18002bd68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bd6d  jmp     short loc_18002BD3A
0x18002bd6f  lea     rcx, [rsp+270h+var_248]
0x18002bd74  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002bd79  movsxd  rcx, [rsp+270h+var_250]
0x18002bd7e  movsxd  rax, [rsp+270h+var_24C]
0x18002bd83  shl     rcx, 1Fh
0x18002bd87  or      rcx, rax
0x18002bd8a  mov     [rdi], rcx
0x18002bd8d  xor     ebx, ebx
0x18002bd8f  lea     rcx, [rsp+270h+var_240]
0x18002bd94  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002bd99  mov     eax, ebx
0x18002bd9b  mov     rcx, [rbp+170h+var_20]
0x18002bda2  xor     rcx, rsp; StackCookie
0x18002bda5  call    __security_check_cookie
0x18002bdaa  mov     rbx, [rsp+270h+arg_8]
0x18002bdb2  add     rsp, 260h
0x18002bdb9  pop     r14
0x18002bdbb  pop     rdi
0x18002bdbc  pop     rbp
0x18002bdbd  retn
```
