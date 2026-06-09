# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18001d308`
- end: `0x18001d534`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `556`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001c31c`
- `0x180062248`

## callees

- `0x18001c254`
- `0x18001d308`
- `0x180027760`
- `0x180061ddc`
- `0x1800622cc`
- `0x1800700d0`
- `0x180084f50`
- `0x180087d4c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001d3d9`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001d448`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001d3d9`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001d448`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d4da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d4da`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v5; // rdx
  __int64 v7; // r9
  bool v8; // zf
  WCHAR *v9; // rcx
  __int64 v10; // rdx
  WCHAR *v11; // rax
  __int64 v12; // r8
  HANDLE v13; // rax
  int ValueFromSemaphore; // eax
  unsigned int LastError; // ebx
  HANDLE v16; // rax
  const char *v17; // r9
  int v18; // eax
  const char *v20; // r9
  size_t v21; // [rsp+20h] [rbp-E0h]
  int v22; // [rsp+30h] [rbp-D0h] BYREF
  int v23; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v24; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v25[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = Name;
  *a3 = 0;
  v5 = 260;
  v7 = 2147483646;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v7;
    --v5;
  }
  while ( v5 );
  v8 = v5 == 0;
  v9 = v4 - 1;
  v10 = 260;
  if ( !v8 )
    v9 = v4;
  v11 = Name;
  *v9 = 0;
  do
  {
    if ( !*v11 )
      break;
    ++v11;
    --v10;
  }
  while ( v10 );
  if ( v10 )
  {
    v12 = (260 - v10) & -(__int64)(v10 != 0);
    StringCopyWorkerW(&Name[v12], 260 - v12, (size_t *)v12, L"_p0", v21);
  }
  v13 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v25[0] = v13;
  if ( v13 )
  {
    v23 = 0;
    v22 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, &v23);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore >= 0 )
    {
      StringCchCatW(Name, 0x104u, L"h");
      v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
      v24 = v16;
      if ( v16 )
      {
        v18 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v16, &v22);
        LastError = v18;
        if ( v18 >= 0 )
        {
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v24);
          *a3 = v23 | (unsigned __int64)((__int64)v22 << 31);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v25);
          return 0;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xDE,
          (unsigned int)"wil",
          (const char *)(unsigned int)v18,
          v21);
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v17);
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v24);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v21);
    }
    goto LABEL_23;
  }
  if ( GetLastError() == 2 )
  {
    LastError = 0;
LABEL_23:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v25);
    return LastError;
  }
  return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v20);
}

```

## disassembly

```asm
0x18001d308  mov     [rsp-8+arg_0], rbx
0x18001d30d  mov     [rsp-8+arg_8], rsi
0x18001d312  push    rbp
0x18001d313  push    rdi
0x18001d314  push    r14
0x18001d316  lea     rbp, [rsp-170h]
0x18001d31e  sub     rsp, 270h
0x18001d325  mov     rax, cs:__security_cookie
0x18001d32c  xor     rax, rsp
0x18001d32f  mov     [rbp+180h+var_20], rax
0x18001d336  xor     esi, esi
0x18001d338  lea     rax, [rsp+280h+Name]
0x18001d33d  mov     r14d, 104h
0x18001d343  mov     [r8], rsi
0x18001d346  mov     edx, r14d
0x18001d349  mov     rdi, r8
0x18001d34c  mov     r9d, 7FFFFFFEh
0x18001d352  test    r9, r9
0x18001d355  jz      short loc_18001D376
0x18001d357  movzx   r8d, word ptr [rcx]
0x18001d35b  test    r8w, r8w
0x18001d35f  jz      short loc_18001D376
0x18001d361  mov     [rax], r8w
0x18001d365  add     rcx, 2
0x18001d369  add     rax, 2
0x18001d36d  dec     r9
0x18001d370  sub     rdx, 1
0x18001d374  jnz     short loc_18001D352
0x18001d376  test    rdx, rdx
0x18001d379  lea     rcx, [rax-2]
0x18001d37d  mov     rdx, r14
0x18001d380  cmovnz  rcx, rax
0x18001d384  lea     rax, [rsp+280h+Name]
0x18001d389  mov     [rcx], si
0x18001d38c  cmp     [rax], si
0x18001d38f  jz      short loc_18001D39B
0x18001d391  add     rax, 2
0x18001d395  sub     rdx, 1
0x18001d399  jnz     short loc_18001D38C
0x18001d39b  mov     rcx, r14
0x18001d39e  mov     rax, rdx
0x18001d3a1  sub     rcx, rdx
0x18001d3a4  neg     rax
0x18001d3a7  sbb     r8, r8
0x18001d3aa  and     r8, rcx; pcchNewDestLength
0x18001d3ad  test    rdx, rdx
0x18001d3b0  jz      short loc_18001D3CD
0x18001d3b2  mov     rdx, r14
0x18001d3b5  lea     rcx, [rsp+280h+Name]
0x18001d3ba  sub     rdx, r8; cchDest
0x18001d3bd  lea     rcx, [rcx+r8*2]; pszDest
0x18001d3c1  lea     r9, aP0; "_p0"
0x18001d3c8  call    StringCopyWorkerW
0x18001d3cd  lea     r8, [rsp+280h+Name]; lpName
0x18001d3d2  xor     edx, edx; bInheritHandle
0x18001d3d4  mov     ecx, 1F0003h; dwDesiredAccess
0x18001d3d9  call    cs:__imp_OpenSemaphoreW
0x18001d3df  mov     [rsp+280h+var_240], rax
0x18001d3e4  test    rax, rax
0x18001d3e7  jz      loc_18001D4DA
0x18001d3ed  lea     rdx, [rsp+280h+var_24C]; int *
0x18001d3f2  mov     [rsp+280h+var_24C], esi
0x18001d3f6  mov     rcx, rax; hHandle
0x18001d3f9  mov     [rsp+280h+var_250], esi
0x18001d3fd  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001d402  mov     ebx, eax
0x18001d404  test    eax, eax
0x18001d406  jns     short loc_18001D428
0x18001d408  mov     rcx, [rbp+188h]; this
0x18001d40f  lea     r8, aWil; "wil"
0x18001d416  mov     r9d, eax; char *
0x18001d419  mov     edx, 0D6h; void *
0x18001d41e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d423  jmp     loc_18001D4E7
0x18001d428  lea     r8, asc_18010294C; "h"
0x18001d42f  mov     rdx, r14; unsigned __int64
0x18001d432  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001d437  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001d43c  lea     r8, [rsp+280h+Name]; lpName
0x18001d441  xor     edx, edx; bInheritHandle
0x18001d443  mov     ecx, 1F0003h; dwDesiredAccess
0x18001d448  call    cs:__imp_OpenSemaphoreW
0x18001d44e  mov     [rsp+280h+var_248], rax
0x18001d453  test    rax, rax
0x18001d456  jz      short loc_18001D4B4
0x18001d458  lea     rdx, [rsp+280h+var_250]; int *
0x18001d45d  mov     rcx, rax; hHandle
0x18001d460  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001d465  mov     ebx, eax
0x18001d467  test    eax, eax
0x18001d469  jns     short loc_18001D488
0x18001d46b  mov     rcx, [rbp+188h]; this
0x18001d472  lea     r8, aWil; "wil"
0x18001d479  mov     r9d, eax; char *
0x18001d47c  mov     edx, 0DEh; void *
0x18001d481  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d486  jmp     short loc_18001D4CE
0x18001d488  lea     rcx, [rsp+280h+var_248]
0x18001d48d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001d492  movsxd  rax, [rsp+280h+var_24C]
0x18001d497  movsxd  rcx, [rsp+280h+var_250]
0x18001d49c  shl     rcx, 1Fh
0x18001d4a0  or      rcx, rax
0x18001d4a3  mov     [rdi], rcx
0x18001d4a6  lea     rcx, [rsp+280h+var_240]
0x18001d4ab  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001d4b0  xor     eax, eax
0x18001d4b2  jmp     short loc_18001D50D
0x18001d4b4  mov     rcx, [rbp+188h]; this
0x18001d4bb  lea     r8, aWil; "wil"
0x18001d4c2  mov     edx, 0DCh; void *
0x18001d4c7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001d4cc  mov     ebx, eax
0x18001d4ce  lea     rcx, [rsp+280h+var_248]
0x18001d4d3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001d4d8  jmp     short loc_18001D4E7
0x18001d4da  call    cs:__imp_GetLastError
0x18001d4e0  cmp     eax, 2
0x18001d4e3  jnz     short loc_18001D4F5
0x18001d4e5  mov     ebx, esi
0x18001d4e7  lea     rcx, [rsp+280h+var_240]
0x18001d4ec  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001d4f1  mov     eax, ebx
0x18001d4f3  jmp     short loc_18001D50D
0x18001d4f5  mov     rcx, [rbp+188h]; this
0x18001d4fc  lea     r8, aWil; "wil"
0x18001d503  mov     edx, 0D0h; void *
0x18001d508  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001d50d  mov     rcx, [rbp+180h+var_20]
0x18001d514  xor     rcx, rsp; StackCookie
0x18001d517  call    __security_check_cookie
0x18001d51c  lea     r11, [rsp+280h+var_10]
0x18001d524  mov     rbx, [r11+20h]
0x18001d528  mov     rsi, [r11+28h]
0x18001d52c  mov     rsp, r11
0x18001d52f  pop     r14
0x18001d531  pop     rdi
0x18001d532  pop     rbp
0x18001d533  retn
```
