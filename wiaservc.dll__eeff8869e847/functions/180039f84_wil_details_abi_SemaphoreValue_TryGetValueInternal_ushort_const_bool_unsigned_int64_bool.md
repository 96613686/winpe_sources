# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180039f84`
- end: `0x18003a126`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180039f10`

## callees

- `0x180010d78`
- `0x180033cc0`
- `0x180035888`
- `0x1800371a0`
- `0x180038d0c`
- `0x180038d2c`
- `0x180039b40`
- `0x180039f84`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x180039fed`
- `KERNEL32!OpenSemaphoreW` at `0x18003a07f`
- `KERNEL32!OpenSemaphoreW` at `0x180039fed`
- `KERNEL32!OpenSemaphoreW` at `0x18003a07f`
- `KERNEL32!GetLastError` at `0x180039ffd`
- `KERNEL32!GetLastError` at `0x180039ffd`

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
0x180039f84  mov     [rsp-8+arg_8], rbx
0x180039f89  push    rbp
0x180039f8a  push    rdi
0x180039f8b  push    r14
0x180039f8d  lea     rbp, [rsp-160h]
0x180039f95  sub     rsp, 260h
0x180039f9c  mov     rax, cs:__security_cookie
0x180039fa3  xor     rax, rsp
0x180039fa6  mov     [rbp+170h+var_20], rax
0x180039fad  mov     rdi, r8
0x180039fb0  mov     qword ptr [r8], 0
0x180039fb7  mov     r8, rcx; unsigned __int16 *
0x180039fba  mov     r14d, 104h
0x180039fc0  mov     edx, r14d; unsigned __int64
0x180039fc3  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180039fc8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180039fcd  lea     r8, aP0; "_p0"
0x180039fd4  mov     edx, r14d; unsigned __int64
0x180039fd7  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180039fdc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180039fe1  lea     r8, [rsp+270h+Name]; lpName
0x180039fe6  xor     edx, edx; bInheritHandle
0x180039fe8  mov     ecx, 1F0003h; dwDesiredAccess
0x180039fed  call    cs:__imp_OpenSemaphoreW
0x180039ff3  mov     [rsp+270h+var_240], rax
0x180039ff8  test    rax, rax
0x180039ffb  jnz     short loc_18003A023
0x180039ffd  call    cs:__imp_GetLastError
0x18003a003  cmp     eax, 2
0x18003a006  jz      loc_18003A0F5
0x18003a00c  mov     rcx, [rbp+178h]; this
0x18003a013  lea     edx, [r14-34h]; void *
0x18003a017  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003a01c  mov     ebx, eax
0x18003a01e  jmp     loc_18003A0F7
0x18003a023  lea     rdx, [rsp+270h+var_24C]; int *
0x18003a028  mov     [rsp+270h+var_24C], 0
0x18003a030  mov     rcx, rax; hHandle
0x18003a033  mov     [rsp+270h+var_250], 0; int
0x18003a03b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18003a040  mov     ebx, eax
0x18003a042  test    eax, eax
0x18003a044  jns     short loc_18003A05F
0x18003a046  mov     rcx, [rbp+178h]; this
0x18003a04d  mov     r9d, eax; char *
0x18003a050  mov     edx, 0D6h; void *
0x18003a055  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a05a  jmp     loc_18003A0F7
0x18003a05f  lea     r8, asc_180084FC8; "h"
0x18003a066  mov     rdx, r14; unsigned __int64
0x18003a069  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003a06e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003a073  lea     r8, [rsp+270h+Name]; lpName
0x18003a078  xor     edx, edx; bInheritHandle
0x18003a07a  mov     ecx, 1F0003h; dwDesiredAccess
0x18003a07f  call    cs:__imp_OpenSemaphoreW
0x18003a085  mov     [rsp+270h+var_248], rax
0x18003a08a  test    rax, rax
0x18003a08d  jnz     short loc_18003A0AE
0x18003a08f  mov     rcx, [rbp+178h]; this
0x18003a096  mov     edx, 0DCh; void *
0x18003a09b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003a0a0  mov     ebx, eax
0x18003a0a2  lea     rcx, [rsp+270h+var_248]
0x18003a0a7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003a0ac  jmp     short loc_18003A0F7
0x18003a0ae  lea     rdx, [rsp+270h+var_250]; int *
0x18003a0b3  mov     rcx, rax; hHandle
0x18003a0b6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18003a0bb  mov     ebx, eax
0x18003a0bd  test    eax, eax
0x18003a0bf  jns     short loc_18003A0D7
0x18003a0c1  mov     rcx, [rbp+178h]; this
0x18003a0c8  mov     r9d, eax; char *
0x18003a0cb  mov     edx, 0DEh; void *
0x18003a0d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a0d5  jmp     short loc_18003A0A2
0x18003a0d7  lea     rcx, [rsp+270h+var_248]
0x18003a0dc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003a0e1  movsxd  rcx, [rsp+270h+var_250]
0x18003a0e6  movsxd  rax, [rsp+270h+var_24C]
0x18003a0eb  shl     rcx, 1Fh
0x18003a0ef  or      rcx, rax
0x18003a0f2  mov     [rdi], rcx
0x18003a0f5  xor     ebx, ebx
0x18003a0f7  lea     rcx, [rsp+270h+var_240]
0x18003a0fc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003a101  mov     eax, ebx
0x18003a103  mov     rcx, [rbp+170h+var_20]
0x18003a10a  xor     rcx, rsp; StackCookie
0x18003a10d  call    __security_check_cookie
0x18003a112  mov     rbx, [rsp+270h+arg_8]
0x18003a11a  add     rsp, 260h
0x18003a121  pop     r14
0x18003a123  pop     rdi
0x18003a124  pop     rbp
0x18003a125  retn
```
