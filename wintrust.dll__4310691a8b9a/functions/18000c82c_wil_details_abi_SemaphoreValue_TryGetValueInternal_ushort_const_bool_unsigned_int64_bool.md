# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000c82c`
- end: `0x18000ca99`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `621`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000c5e8`
- `0x18002c00c`

## callees

- `0x18000c82c`
- `0x18000d1c0`
- `0x18002ba20`
- `0x18002c090`
- `0x18002c1b4`
- `0x180033d30`
- `0x18004deb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ca3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ca3e`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c92f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c99f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c92f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c99f`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  __int64 v5; // r10
  __int64 v6; // r9
  __int64 v7; // rdx
  WCHAR *v8; // rax
  WCHAR v9; // r8
  WCHAR *v10; // rcx
  __int64 v11; // rdx
  WCHAR *v12; // rax
  __int64 v13; // r8
  const unsigned __int16 *v14; // rcx
  __int64 v15; // rax
  WCHAR *v16; // rdx
  unsigned __int16 v17; // r8
  WCHAR *v18; // rcx
  HANDLE v19; // rax
  int ValueFromSemaphore; // eax
  unsigned int LastError; // ebx
  HANDLE v22; // rax
  const char *v23; // r9
  int v24; // eax
  const char *v26; // r9
  int v27; // [rsp+20h] [rbp-E0h] BYREF
  int v28; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v29; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v30[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  v5 = 2147483646;
  v6 = 2147483646;
  v7 = 260;
  v8 = Name;
  do
  {
    if ( !v6 )
      break;
    v9 = *a1;
    if ( !*a1 )
      break;
    ++a1;
    *v8++ = v9;
    --v6;
    --v7;
  }
  while ( v7 );
  v10 = v8 - 1;
  if ( v7 )
    v10 = v8;
  *v10 = 0;
  v11 = 260;
  v12 = Name;
  do
  {
    if ( !*v12 )
      break;
    ++v12;
    --v11;
  }
  while ( v11 );
  v13 = (260 - v11) & -(__int64)(v11 != 0);
  if ( v11 )
  {
    v14 = L"_p0";
    v15 = 260 - v13;
    v16 = &Name[v13];
    if ( v13 != 260 )
    {
      do
      {
        if ( !v5 )
          break;
        v17 = *v14;
        if ( !*v14 )
          break;
        ++v14;
        *v16++ = v17;
        --v5;
        --v15;
      }
      while ( v15 );
    }
    v18 = v16 - 1;
    if ( v15 )
      v18 = v16;
    *v18 = 0;
  }
  v19 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v30[0] = v19;
  if ( v19 )
  {
    v28 = 0;
    v27 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v19, &v28);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore >= 0 )
    {
      StringCchCatW(Name, 0x104u, L"h");
      v22 = OpenSemaphoreW(0x1F0003u, 0, Name);
      v29 = v22;
      if ( v22 )
      {
        v24 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v22, &v27);
        LastError = v24;
        if ( v24 >= 0 )
        {
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v29);
          *a3 = v28 | (unsigned __int64)((__int64)v27 << 31);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v30);
          return 0;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xDE,
          (unsigned int)"wil",
          (const char *)(unsigned int)v24,
          v27);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v29);
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v23);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v29);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v27);
    }
    goto LABEL_28;
  }
  if ( GetLastError() == 2 )
  {
    LastError = 0;
LABEL_28:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v30);
    return LastError;
  }
  return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v26);
}

```

## disassembly

```asm
0x18000c82c  mov     [rsp-8+arg_0], rbx
0x18000c831  mov     [rsp-8+arg_8], rsi
0x18000c836  push    rbp
0x18000c837  push    rdi
0x18000c838  push    r15
0x18000c83a  lea     rbp, [rsp-160h]
0x18000c842  sub     rsp, 260h
0x18000c849  mov     rax, cs:__security_cookie
0x18000c850  xor     rax, rsp
0x18000c853  mov     [rbp+170h+var_20], rax
0x18000c85a  mov     rdi, r8
0x18000c85d  xor     esi, esi
0x18000c85f  mov     [r8], rsi
0x18000c862  mov     r10d, 7FFFFFFEh
0x18000c868  mov     r9d, r10d
0x18000c86b  mov     r15d, 104h
0x18000c871  mov     edx, r15d
0x18000c874  lea     rax, [rsp+270h+Name]
0x18000c879  test    r9, r9
0x18000c87c  jz      short loc_18000C89D
0x18000c87e  movzx   r8d, word ptr [rcx]
0x18000c882  test    r8w, r8w
0x18000c886  jz      short loc_18000C89D
0x18000c888  add     rcx, 2
0x18000c88c  mov     [rax], r8w
0x18000c890  add     rax, 2
0x18000c894  dec     r9
0x18000c897  sub     rdx, 1
0x18000c89b  jnz     short loc_18000C879
0x18000c89d  lea     rcx, [rax-2]
0x18000c8a1  test    rdx, rdx
0x18000c8a4  cmovnz  rcx, rax
0x18000c8a8  mov     [rcx], si
0x18000c8ab  mov     rdx, r15
0x18000c8ae  lea     rax, [rsp+270h+Name]
0x18000c8b3  cmp     [rax], si
0x18000c8b6  jz      short loc_18000C8C2
0x18000c8b8  add     rax, 2
0x18000c8bc  sub     rdx, 1
0x18000c8c0  jnz     short loc_18000C8B3
0x18000c8c2  mov     rax, rdx
0x18000c8c5  mov     rcx, r15
0x18000c8c8  sub     rcx, rdx
0x18000c8cb  neg     rax
0x18000c8ce  sbb     r8, r8
0x18000c8d1  and     r8, rcx
0x18000c8d4  test    rdx, rdx
0x18000c8d7  jz      short loc_18000C923
0x18000c8d9  lea     rcx, aP0; "_p0"
0x18000c8e0  mov     rax, r15
0x18000c8e3  sub     rax, r8
0x18000c8e6  lea     rdx, [rsp+270h+Name]
0x18000c8eb  lea     rdx, [rdx+r8*2]
0x18000c8ef  jz      short loc_18000C915
0x18000c8f1  test    r10, r10
0x18000c8f4  jz      short loc_18000C915
0x18000c8f6  movzx   r8d, word ptr [rcx]
0x18000c8fa  test    r8w, r8w
0x18000c8fe  jz      short loc_18000C915
0x18000c900  add     rcx, 2
0x18000c904  mov     [rdx], r8w
0x18000c908  add     rdx, 2
0x18000c90c  dec     r10
0x18000c90f  sub     rax, 1
0x18000c913  jnz     short loc_18000C8F1
0x18000c915  lea     rcx, [rdx-2]
0x18000c919  test    rax, rax
0x18000c91c  cmovnz  rcx, rdx
0x18000c920  mov     [rcx], si
0x18000c923  lea     r8, [rsp+270h+Name]; lpName
0x18000c928  xor     edx, edx; bInheritHandle
0x18000c92a  mov     ecx, 1F0003h; dwDesiredAccess
0x18000c92f  call    cs:__imp_OpenSemaphoreW
0x18000c935  mov     [rsp+270h+var_240], rax
0x18000c93a  test    rax, rax
0x18000c93d  jz      loc_18000CA3E
0x18000c943  mov     [rsp+270h+var_24C], esi
0x18000c947  mov     [rsp+270h+var_250], esi; int
0x18000c94b  lea     rdx, [rsp+270h+var_24C]; int *
0x18000c950  mov     rcx, rax; hHandle
0x18000c953  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000c958  mov     ebx, eax
0x18000c95a  test    eax, eax
0x18000c95c  jns     short loc_18000C97F
0x18000c95e  mov     rcx, [rbp+178h]; this
0x18000c965  mov     r9d, eax; char *
0x18000c968  lea     r8, aWil; "wil"
0x18000c96f  mov     edx, 0D6h; void *
0x18000c974  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c979  nop
0x18000c97a  jmp     loc_18000CA4B
0x18000c97f  lea     r8, asc_180055B38; "h"
0x18000c986  mov     rdx, r15; unsigned __int64
0x18000c989  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000c98e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c993  lea     r8, [rsp+270h+Name]; lpName
0x18000c998  xor     edx, edx; bInheritHandle
0x18000c99a  mov     ecx, 1F0003h; dwDesiredAccess
0x18000c99f  call    cs:__imp_OpenSemaphoreW
0x18000c9a5  mov     [rsp+270h+var_248], rax
0x18000c9aa  test    rax, rax
0x18000c9ad  jz      short loc_18000CA17
0x18000c9af  lea     rdx, [rsp+270h+var_250]; int *
0x18000c9b4  mov     rcx, rax; hHandle
0x18000c9b7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000c9bc  mov     ebx, eax
0x18000c9be  test    eax, eax
0x18000c9c0  jns     short loc_18000C9EB
0x18000c9c2  mov     rcx, [rbp+178h]; this
0x18000c9c9  mov     r9d, eax; char *
0x18000c9cc  lea     r8, aWil; "wil"
0x18000c9d3  mov     edx, 0DEh; void *
0x18000c9d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c9dd  nop
0x18000c9de  lea     rcx, [rsp+270h+var_248]
0x18000c9e3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000c9e8  nop
0x18000c9e9  jmp     short loc_18000CA4B
0x18000c9eb  lea     rcx, [rsp+270h+var_248]
0x18000c9f0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000c9f5  movsxd  rcx, [rsp+270h+var_250]
0x18000c9fa  shl     rcx, 1Fh
0x18000c9fe  movsxd  rax, [rsp+270h+var_24C]
0x18000ca03  or      rcx, rax
0x18000ca06  mov     [rdi], rcx
0x18000ca09  lea     rcx, [rsp+270h+var_240]
0x18000ca0e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000ca13  xor     eax, eax
0x18000ca15  jmp     short loc_18000CA72
0x18000ca17  mov     rcx, [rbp+178h]; this
0x18000ca1e  lea     r8, aWil; "wil"
0x18000ca25  mov     edx, 0DCh; void *
0x18000ca2a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000ca2f  mov     ebx, eax
0x18000ca31  lea     rcx, [rsp+270h+var_248]
0x18000ca36  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000ca3b  nop
0x18000ca3c  jmp     short loc_18000CA4B
0x18000ca3e  call    cs:__imp_GetLastError
0x18000ca44  cmp     eax, 2
0x18000ca47  jnz     short loc_18000CA59
0x18000ca49  mov     ebx, esi
0x18000ca4b  lea     rcx, [rsp+270h+var_240]
0x18000ca50  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000ca55  mov     eax, ebx
0x18000ca57  jmp     short loc_18000CA72
0x18000ca59  mov     rcx, [rbp+178h]; this
0x18000ca60  lea     r8, aWil; "wil"
0x18000ca67  mov     edx, 0D0h; void *
0x18000ca6c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000ca71  nop
0x18000ca72  mov     rcx, [rbp+170h+var_20]
0x18000ca79  xor     rcx, rsp; StackCookie
0x18000ca7c  call    __security_check_cookie
0x18000ca81  lea     r11, [rsp+270h+var_10]
0x18000ca89  mov     rbx, [r11+20h]
0x18000ca8d  mov     rsi, [r11+28h]
0x18000ca91  mov     rsp, r11
0x18000ca94  pop     r15
0x18000ca96  pop     rdi
0x18000ca97  pop     rbp
0x18000ca98  retn
```
