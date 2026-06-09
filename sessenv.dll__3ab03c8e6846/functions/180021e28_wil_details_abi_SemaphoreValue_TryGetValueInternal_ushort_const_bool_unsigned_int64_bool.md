# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180021e28`
- end: `0x180021fc4`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001f6e4`

## callees

- `0x180004e00`
- `0x180016e3c`
- `0x18001a280`
- `0x18001f68c`
- `0x180020980`
- `0x180021a68`
- `0x180021d1c`
- `0x180021e28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021e9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021e9c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180021e8c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180021f1c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180021e8c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180021f1c`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned __int64 v5; // rdx
  HANDLE v6; // rax
  unsigned int v7; // r8d
  const char *v8; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v11; // rdx
  unsigned int v12; // r8d
  HANDLE v13; // rax
  unsigned int v14; // r8d
  const char *v15; // r9
  int v16; // eax
  unsigned int v17; // r8d
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v21; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v22[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v22[0] = v6;
  if ( v6 )
  {
    v20 = 0;
    v19 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v20);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore, v19);
      goto LABEL_13;
    }
    StringCchCatW(Name, v11, L"h");
    v13 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v21 = v13;
    if ( v13 )
    {
      v16 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, &v19);
      LastError = v16;
      if ( v16 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
        *a3 = v20 | (unsigned __int64)((__int64)v19 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v17, (const char *)(unsigned int)v16, v19);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v14, v15);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v7, v8);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v22);
  return LastError;
}

```

## disassembly

```asm
0x180021e28  mov     [rsp-8+arg_8], rbx
0x180021e2d  mov     [rsp-8+arg_18], rdi
0x180021e32  push    rbp
0x180021e33  lea     rbp, [rsp-160h]
0x180021e3b  sub     rsp, 260h
0x180021e42  mov     rax, cs:__security_cookie
0x180021e49  xor     rax, rsp
0x180021e4c  mov     [rbp+160h+var_10], rax
0x180021e53  mov     rdi, r8
0x180021e56  mov     qword ptr [r8], 0
0x180021e5d  mov     r8, rcx; unsigned __int16 *
0x180021e60  mov     edx, 104h; unsigned __int64
0x180021e65  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180021e6a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180021e6f  lea     r8, aP0; "_p0"
0x180021e76  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180021e7b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180021e80  lea     r8, [rsp+260h+Name]; lpName
0x180021e85  xor     edx, edx; bInheritHandle
0x180021e87  mov     ecx, 1F0003h; dwDesiredAccess
0x180021e8c  call    cs:__imp_OpenSemaphoreW
0x180021e92  mov     [rsp+260h+var_230], rax
0x180021e97  test    rax, rax
0x180021e9a  jnz     short loc_180021EC3
0x180021e9c  call    cs:__imp_GetLastError
0x180021ea2  cmp     eax, 2
0x180021ea5  jz      loc_180021F92
0x180021eab  mov     rcx, [rbp+168h]; this
0x180021eb2  mov     edx, 0D0h; void *
0x180021eb7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180021ebc  mov     ebx, eax
0x180021ebe  jmp     loc_180021F94
0x180021ec3  lea     rdx, [rsp+260h+var_23C]; int *
0x180021ec8  mov     [rsp+260h+var_23C], 0
0x180021ed0  mov     rcx, rax; hHandle
0x180021ed3  mov     [rsp+260h+var_240], 0; int
0x180021edb  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180021ee0  mov     ebx, eax
0x180021ee2  test    eax, eax
0x180021ee4  jns     short loc_180021EFF
0x180021ee6  mov     rcx, [rbp+168h]; this
0x180021eed  mov     r9d, eax; char *
0x180021ef0  mov     edx, 0D6h; void *
0x180021ef5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021efa  jmp     loc_180021F94
0x180021eff  lea     r8, asc_180064340; "h"
0x180021f06  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180021f0b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180021f10  lea     r8, [rsp+260h+Name]; lpName
0x180021f15  xor     edx, edx; bInheritHandle
0x180021f17  mov     ecx, 1F0003h; dwDesiredAccess
0x180021f1c  call    cs:__imp_OpenSemaphoreW
0x180021f22  mov     [rsp+260h+var_238], rax
0x180021f27  test    rax, rax
0x180021f2a  jnz     short loc_180021F4B
0x180021f2c  mov     rcx, [rbp+168h]; this
0x180021f33  mov     edx, 0DCh; void *
0x180021f38  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180021f3d  mov     ebx, eax
0x180021f3f  lea     rcx, [rsp+260h+var_238]
0x180021f44  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180021f49  jmp     short loc_180021F94
0x180021f4b  lea     rdx, [rsp+260h+var_240]; int *
0x180021f50  mov     rcx, rax; hHandle
0x180021f53  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180021f58  mov     ebx, eax
0x180021f5a  test    eax, eax
0x180021f5c  jns     short loc_180021F74
0x180021f5e  mov     rcx, [rbp+168h]; this
0x180021f65  mov     r9d, eax; char *
0x180021f68  mov     edx, 0DEh; void *
0x180021f6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021f72  jmp     short loc_180021F3F
0x180021f74  lea     rcx, [rsp+260h+var_238]
0x180021f79  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180021f7e  movsxd  rcx, [rsp+260h+var_240]
0x180021f83  movsxd  rax, [rsp+260h+var_23C]
0x180021f88  shl     rcx, 1Fh
0x180021f8c  or      rcx, rax
0x180021f8f  mov     [rdi], rcx
0x180021f92  xor     ebx, ebx
0x180021f94  lea     rcx, [rsp+260h+var_230]
0x180021f99  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180021f9e  mov     eax, ebx
0x180021fa0  mov     rcx, [rbp+160h+var_10]
0x180021fa7  xor     rcx, rsp; StackCookie
0x180021faa  call    __security_check_cookie
0x180021faf  lea     r11, [rsp+260h+var_s0]
0x180021fb7  mov     rbx, [r11+18h]
0x180021fbb  mov     rdi, [r11+28h]
0x180021fbf  mov     rsp, r11
0x180021fc2  pop     rbp
0x180021fc3  retn
```
