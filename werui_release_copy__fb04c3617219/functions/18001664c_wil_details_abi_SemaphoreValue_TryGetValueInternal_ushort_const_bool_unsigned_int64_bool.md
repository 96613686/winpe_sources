# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18001664c`
- end: `0x1800167e8`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180015490`

## callees

- `0x180007cdc`
- `0x180015410`
- `0x180015b8c`
- `0x180016320`
- `0x180016340`
- `0x180016578`
- `0x18001664c`
- `0x180016c50`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x1800166b0`
- `KERNEL32!OpenSemaphoreW` at `0x180016740`
- `KERNEL32!OpenSemaphoreW` at `0x1800166b0`
- `KERNEL32!OpenSemaphoreW` at `0x180016740`
- `KERNEL32!GetLastError` at `0x1800166c0`
- `KERNEL32!GetLastError` at `0x1800166c0`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        unsigned __int16 *a1,
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
0x18001664c  mov     [rsp-8+arg_8], rbx
0x180016651  mov     [rsp-8+arg_18], rdi
0x180016656  push    rbp
0x180016657  lea     rbp, [rsp-160h]
0x18001665f  sub     rsp, 260h
0x180016666  mov     rax, cs:__security_cookie
0x18001666d  xor     rax, rsp
0x180016670  mov     [rbp+160h+var_10], rax
0x180016677  mov     rdi, r8
0x18001667a  mov     qword ptr [r8], 0
0x180016681  mov     r8, rcx; unsigned __int16 *
0x180016684  mov     edx, 104h; unsigned __int64
0x180016689  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18001668e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180016693  lea     r8, aP0; "_p0"
0x18001669a  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18001669f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800166a4  lea     r8, [rsp+260h+Name]; lpName
0x1800166a9  xor     edx, edx; bInheritHandle
0x1800166ab  mov     ecx, 1F0003h; dwDesiredAccess
0x1800166b0  call    cs:__imp_OpenSemaphoreW
0x1800166b6  mov     [rsp+260h+var_230], rax
0x1800166bb  test    rax, rax
0x1800166be  jnz     short loc_1800166E7
0x1800166c0  call    cs:__imp_GetLastError
0x1800166c6  cmp     eax, 2
0x1800166c9  jz      loc_1800167B6
0x1800166cf  mov     rcx, [rbp+168h]; this
0x1800166d6  mov     edx, 0D0h; void *
0x1800166db  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800166e0  mov     ebx, eax
0x1800166e2  jmp     loc_1800167B8
0x1800166e7  lea     rdx, [rsp+260h+var_23C]; int *
0x1800166ec  mov     [rsp+260h+var_23C], 0
0x1800166f4  mov     rcx, rax; hHandle
0x1800166f7  mov     [rsp+260h+var_240], 0; int
0x1800166ff  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180016704  mov     ebx, eax
0x180016706  test    eax, eax
0x180016708  jns     short loc_180016723
0x18001670a  mov     rcx, [rbp+168h]; this
0x180016711  mov     r9d, eax; char *
0x180016714  mov     edx, 0D6h; void *
0x180016719  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001671e  jmp     loc_1800167B8
0x180016723  lea     r8, asc_18001BA80; "h"
0x18001672a  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18001672f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180016734  lea     r8, [rsp+260h+Name]; lpName
0x180016739  xor     edx, edx; bInheritHandle
0x18001673b  mov     ecx, 1F0003h; dwDesiredAccess
0x180016740  call    cs:__imp_OpenSemaphoreW
0x180016746  mov     [rsp+260h+var_238], rax
0x18001674b  test    rax, rax
0x18001674e  jnz     short loc_18001676F
0x180016750  mov     rcx, [rbp+168h]; this
0x180016757  mov     edx, 0DCh; void *
0x18001675c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180016761  mov     ebx, eax
0x180016763  lea     rcx, [rsp+260h+var_238]
0x180016768  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001676d  jmp     short loc_1800167B8
0x18001676f  lea     rdx, [rsp+260h+var_240]; int *
0x180016774  mov     rcx, rax; hHandle
0x180016777  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001677c  mov     ebx, eax
0x18001677e  test    eax, eax
0x180016780  jns     short loc_180016798
0x180016782  mov     rcx, [rbp+168h]; this
0x180016789  mov     r9d, eax; char *
0x18001678c  mov     edx, 0DEh; void *
0x180016791  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016796  jmp     short loc_180016763
0x180016798  lea     rcx, [rsp+260h+var_238]
0x18001679d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800167a2  movsxd  rcx, [rsp+260h+var_240]
0x1800167a7  movsxd  rax, [rsp+260h+var_23C]
0x1800167ac  shl     rcx, 1Fh
0x1800167b0  or      rcx, rax
0x1800167b3  mov     [rdi], rcx
0x1800167b6  xor     ebx, ebx
0x1800167b8  lea     rcx, [rsp+260h+var_230]
0x1800167bd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800167c2  mov     eax, ebx
0x1800167c4  mov     rcx, [rbp+160h+var_10]
0x1800167cb  xor     rcx, rsp; StackCookie
0x1800167ce  call    __security_check_cookie
0x1800167d3  lea     r11, [rsp+260h+var_s0]
0x1800167db  mov     rbx, [r11+18h]
0x1800167df  mov     rdi, [r11+28h]
0x1800167e3  mov     rsp, r11
0x1800167e6  pop     rbp
0x1800167e7  retn
```
