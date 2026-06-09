# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18003b0d4`
- end: `0x18003b284`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `432`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18003b050`

## callees

- `0x1800240d0`
- `0x180024150`
- `0x180033dac`
- `0x180037518`
- `0x180039450`
- `0x18003a940`
- `0x18003b0d4`
- `0x18003d810`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b14d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b14d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003b13d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003b1d6`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003b13d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003b1d6`

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
  HANDLE v10; // rax
  unsigned int v11; // r8d
  const char *v12; // r9
  int v13; // eax
  int v15; // [rsp+20h] [rbp-E0h] BYREF
  int v16; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v17; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v18[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18[0] = v5;
  if ( v5 )
  {
    v16 = 0;
    v15 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v16);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v15);
      goto LABEL_13;
    }
    StringCchCatW(Name, 0x104u, L"h");
    v10 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v17 = v10;
    if ( v10 )
    {
      v13 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, &v15);
      LastError = v13;
      if ( v13 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
        *a3 = v16 | (unsigned __int64)((__int64)v15 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v13,
        v15);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v11, v12);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
  return LastError;
}

```

## disassembly

```asm
0x18003b0d4  mov     [rsp-8+arg_8], rbx
0x18003b0d9  push    rbp
0x18003b0da  push    rdi
0x18003b0db  push    r14
0x18003b0dd  lea     rbp, [rsp-160h]
0x18003b0e5  sub     rsp, 260h
0x18003b0ec  mov     rax, cs:__security_cookie
0x18003b0f3  xor     rax, rsp
0x18003b0f6  mov     [rbp+170h+var_20], rax
0x18003b0fd  mov     rdi, r8
0x18003b100  mov     qword ptr [r8], 0
0x18003b107  mov     r8, rcx; unsigned __int16 *
0x18003b10a  mov     r14d, 104h
0x18003b110  mov     edx, r14d; unsigned __int64
0x18003b113  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003b118  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003b11d  lea     r8, aP0; "_p0"
0x18003b124  mov     edx, r14d; unsigned __int64
0x18003b127  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003b12c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003b131  lea     r8, [rsp+270h+Name]; lpName
0x18003b136  xor     edx, edx; bInheritHandle
0x18003b138  mov     ecx, 1F0003h; dwDesiredAccess
0x18003b13d  call    cs:__imp_OpenSemaphoreW
0x18003b143  mov     [rsp+270h+var_240], rax
0x18003b148  test    rax, rax
0x18003b14b  jnz     short loc_18003B173
0x18003b14d  call    cs:__imp_GetLastError
0x18003b153  cmp     eax, 2
0x18003b156  jz      loc_18003B253
0x18003b15c  mov     rcx, [rbp+178h]; this
0x18003b163  lea     edx, [r14-34h]; void *
0x18003b167  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003b16c  mov     ebx, eax
0x18003b16e  jmp     loc_18003B255
0x18003b173  lea     rdx, [rsp+270h+var_24C]; int *
0x18003b178  mov     [rsp+270h+var_24C], 0
0x18003b180  mov     rcx, rax; hHandle
0x18003b183  mov     [rsp+270h+var_250], 0; int
0x18003b18b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18003b190  mov     ebx, eax
0x18003b192  test    eax, eax
0x18003b194  jns     short loc_18003B1B6
0x18003b196  mov     rcx, [rbp+178h]; this
0x18003b19d  lea     r8, aWil; "wil"
0x18003b1a4  mov     r9d, eax; char *
0x18003b1a7  mov     edx, 0D6h; void *
0x18003b1ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b1b1  jmp     loc_18003B255
0x18003b1b6  lea     r8, asc_1800420E0; "h"
0x18003b1bd  mov     rdx, r14; unsigned __int64
0x18003b1c0  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003b1c5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003b1ca  lea     r8, [rsp+270h+Name]; lpName
0x18003b1cf  xor     edx, edx; bInheritHandle
0x18003b1d1  mov     ecx, 1F0003h; dwDesiredAccess
0x18003b1d6  call    cs:__imp_OpenSemaphoreW
0x18003b1dc  mov     [rsp+270h+var_248], rax
0x18003b1e1  test    rax, rax
0x18003b1e4  jnz     short loc_18003B205
0x18003b1e6  mov     rcx, [rbp+178h]; this
0x18003b1ed  mov     edx, 0DCh; void *
0x18003b1f2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003b1f7  mov     ebx, eax
0x18003b1f9  lea     rcx, [rsp+270h+var_248]
0x18003b1fe  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003b203  jmp     short loc_18003B255
0x18003b205  lea     rdx, [rsp+270h+var_250]; int *
0x18003b20a  mov     rcx, rax; hHandle
0x18003b20d  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18003b212  mov     ebx, eax
0x18003b214  test    eax, eax
0x18003b216  jns     short loc_18003B235
0x18003b218  mov     rcx, [rbp+178h]; this
0x18003b21f  lea     r8, aWil; "wil"
0x18003b226  mov     r9d, eax; char *
0x18003b229  mov     edx, 0DEh; void *
0x18003b22e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b233  jmp     short loc_18003B1F9
0x18003b235  lea     rcx, [rsp+270h+var_248]
0x18003b23a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003b23f  movsxd  rcx, [rsp+270h+var_250]
0x18003b244  movsxd  rax, [rsp+270h+var_24C]
0x18003b249  shl     rcx, 1Fh
0x18003b24d  or      rcx, rax
0x18003b250  mov     [rdi], rcx
0x18003b253  xor     ebx, ebx
0x18003b255  lea     rcx, [rsp+270h+var_240]
0x18003b25a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003b25f  mov     eax, ebx
0x18003b261  mov     rcx, [rbp+170h+var_20]
0x18003b268  xor     rcx, rsp; StackCookie
0x18003b26b  call    __security_check_cookie
0x18003b270  mov     rbx, [rsp+270h+arg_8]
0x18003b278  add     rsp, 260h
0x18003b27f  pop     r14
0x18003b281  pop     rdi
0x18003b282  pop     rbp
0x18003b283  retn
```
