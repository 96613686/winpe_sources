# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000e588`
- end: `0x18000e869`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `737`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180020678`

## callees

- `0x18000e568`
- `0x18000e588`
- `0x18000e870`
- `0x18000ea10`
- `0x18002082c`
- `0x180020f6c`
- `0x180032c20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e78c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e78c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000e694`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000e752`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000e694`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000e752`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v5; // r14
  __int64 v6; // r9
  __int64 v7; // rdx
  bool v9; // zf
  WCHAR *v10; // rcx
  __int64 v11; // rdx
  WCHAR *v12; // rax
  __int64 v13; // r8
  const unsigned __int16 *v14; // r9
  __int64 v15; // rcx
  WCHAR *v16; // rdx
  __int64 v17; // rax
  WCHAR *v18; // rcx
  wil::details *v19; // rax
  wil::details *v20; // rdi
  int ValueFromSemaphore; // eax
  unsigned int v22; // r8d
  unsigned int LastError; // esi
  __int64 v24; // rdx
  WCHAR *v25; // rax
  __int64 v26; // r8
  WCHAR *v27; // rax
  const unsigned __int16 *v28; // rcx
  __int64 v29; // rbx
  WCHAR *v30; // rdx
  wil::details *v31; // rax
  const char *v32; // r9
  wil::details *v33; // rbx
  void *v34; // rdx
  const char *v36; // r9
  int v37; // eax
  void *v38; // rdx
  unsigned int v39; // r8d
  void *v40; // rdx
  void *v41; // rdx
  int v42; // [rsp+20h] [rbp-E0h] BYREF
  int v43; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v44; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  v4 = Name;
  v5 = 2147483646;
  *a3 = 0;
  v6 = 2147483646;
  v7 = 260;
  do
  {
    if ( !v6 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v6;
    --v7;
  }
  while ( v7 );
  v9 = v7 == 0;
  v10 = v4 - 1;
  v11 = 260;
  if ( !v9 )
    v10 = v4;
  v12 = Name;
  *v10 = 0;
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
    v15 = 2147483646;
    v16 = &Name[v13];
    v17 = 260 - v13;
    if ( v13 != 260 )
    {
      do
      {
        if ( !v15 )
          break;
        if ( !*v14 )
          break;
        *v16++ = *v14++;
        --v15;
        --v17;
      }
      while ( v17 );
    }
    v18 = v16 - 1;
    if ( v17 )
      v18 = v16;
    *v18 = 0;
  }
  v19 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v44 = v19;
  v20 = v19;
  if ( !v19 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v36);
    LastError = 0;
LABEL_42:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v44);
    return LastError;
  }
  v43 = 0;
  v42 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v19, &v43);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v22, (const char *)(unsigned int)ValueFromSemaphore, v42);
    goto LABEL_42;
  }
  v24 = 260;
  v25 = Name;
  do
  {
    if ( !*v25 )
      break;
    ++v25;
    --v24;
  }
  while ( v24 );
  v26 = (260 - v24) & -(__int64)(v24 != 0);
  if ( v24 )
  {
    v27 = &Name[v26];
    v28 = L"h";
    v29 = 260 - v26;
    if ( 260 != v26 )
    {
      do
      {
        if ( !v5 )
          break;
        if ( !*v28 )
          break;
        *v27++ = *v28++;
        --v5;
        --v29;
      }
      while ( v29 );
    }
    v30 = v27 - 1;
    if ( v29 )
      v30 = v27;
    *v30 = 0;
  }
  v31 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v33 = v31;
  if ( !v31 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v32);
LABEL_33:
    wil::details::CloseHandle(v20, v34);
    return LastError;
  }
  v37 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v31, &v42);
  LastError = v37;
  if ( v37 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v39, (const char *)(unsigned int)v37, v42);
    wil::details::CloseHandle(v33, v41);
    goto LABEL_33;
  }
  wil::details::CloseHandle(v33, v38);
  *a3 = v43 | (unsigned __int64)((__int64)v42 << 31);
  wil::details::CloseHandle(v20, v40);
  return 0;
}

```

## disassembly

```asm
0x18000e588  mov     [rsp-8+arg_0], rbx
0x18000e58d  mov     [rsp-8+arg_8], rsi
0x18000e592  push    rbp
0x18000e593  push    rdi
0x18000e594  push    r12
0x18000e596  push    r14
0x18000e598  push    r15
0x18000e59a  lea     rbp, [rsp-150h]
0x18000e5a2  sub     rsp, 250h
0x18000e5a9  mov     rax, cs:__security_cookie
0x18000e5b0  xor     rax, rsp
0x18000e5b3  mov     [rbp+170h+var_30], rax
0x18000e5ba  xor     r12d, r12d
0x18000e5bd  lea     rax, [rsp+270h+Name]
0x18000e5c2  mov     r14d, 7FFFFFFEh
0x18000e5c8  mov     [r8], r12
0x18000e5cb  mov     ebx, 104h
0x18000e5d0  mov     r9d, r14d
0x18000e5d3  mov     edx, ebx
0x18000e5d5  mov     r15, r8
0x18000e5d8  test    r9, r9
0x18000e5db  jz      short loc_18000E5FC
0x18000e5dd  movzx   r8d, word ptr [rcx]
0x18000e5e1  test    r8w, r8w
0x18000e5e5  jz      short loc_18000E5FC
0x18000e5e7  mov     [rax], r8w
0x18000e5eb  add     rcx, 2
0x18000e5ef  add     rax, 2
0x18000e5f3  dec     r9
0x18000e5f6  sub     rdx, 1
0x18000e5fa  jnz     short loc_18000E5D8
0x18000e5fc  test    rdx, rdx
0x18000e5ff  lea     rcx, [rax-2]
0x18000e603  mov     rdx, rbx
0x18000e606  cmovnz  rcx, rax
0x18000e60a  lea     rax, [rsp+270h+Name]
0x18000e60f  mov     [rcx], r12w
0x18000e613  cmp     [rax], r12w
0x18000e617  jz      short loc_18000E623
0x18000e619  add     rax, 2
0x18000e61d  sub     rdx, 1
0x18000e621  jnz     short loc_18000E613
0x18000e623  mov     rcx, rbx
0x18000e626  mov     rax, rdx
0x18000e629  sub     rcx, rdx
0x18000e62c  neg     rax
0x18000e62f  sbb     r8, r8
0x18000e632  and     r8, rcx
0x18000e635  test    rdx, rdx
0x18000e638  jz      short loc_18000E688
0x18000e63a  mov     rax, rbx
0x18000e63d  lea     rdx, [rsp+270h+Name]
0x18000e642  lea     r9, aP0; "_p0"
0x18000e649  mov     rcx, r14
0x18000e64c  lea     rdx, [rdx+r8*2]
0x18000e650  sub     rax, r8
0x18000e653  jz      short loc_18000E679
0x18000e655  test    rcx, rcx
0x18000e658  jz      short loc_18000E679
0x18000e65a  movzx   r8d, word ptr [r9]
0x18000e65e  test    r8w, r8w
0x18000e662  jz      short loc_18000E679
0x18000e664  mov     [rdx], r8w
0x18000e668  add     r9, 2
0x18000e66c  add     rdx, 2
0x18000e670  dec     rcx
0x18000e673  sub     rax, 1
0x18000e677  jnz     short loc_18000E655
0x18000e679  test    rax, rax
0x18000e67c  lea     rcx, [rdx-2]
0x18000e680  cmovnz  rcx, rdx
0x18000e684  mov     [rcx], r12w
0x18000e688  lea     r8, [rsp+270h+Name]; lpName
0x18000e68d  xor     edx, edx; bInheritHandle
0x18000e68f  mov     ecx, 1F0003h; dwDesiredAccess
0x18000e694  call    cs:__imp_OpenSemaphoreW
0x18000e69b  nop     dword ptr [rax+rax+00h]
0x18000e6a0  mov     [rsp+270h+var_248], rax
0x18000e6a5  mov     rdi, rax
0x18000e6a8  test    rax, rax
0x18000e6ab  jz      loc_18000E78C
0x18000e6b1  lea     rdx, [rsp+270h+var_24C]; int *
0x18000e6b6  mov     [rsp+270h+var_24C], r12d
0x18000e6bb  mov     rcx, rax; hHandle
0x18000e6be  mov     [rsp+270h+var_250], r12d; int
0x18000e6c3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000e6c8  mov     esi, eax
0x18000e6ca  test    eax, eax
0x18000e6cc  js      loc_18000E841
0x18000e6d2  mov     rdx, rbx
0x18000e6d5  lea     rax, [rsp+270h+Name]
0x18000e6da  cmp     [rax], r12w
0x18000e6de  jz      short loc_18000E6EA
0x18000e6e0  add     rax, 2
0x18000e6e4  sub     rdx, 1
0x18000e6e8  jnz     short loc_18000E6DA
0x18000e6ea  mov     rcx, rbx
0x18000e6ed  mov     rax, rdx
0x18000e6f0  sub     rcx, rdx
0x18000e6f3  neg     rax
0x18000e6f6  sbb     r8, r8
0x18000e6f9  and     r8, rcx
0x18000e6fc  test    rdx, rdx
0x18000e6ff  jz      short loc_18000E746
0x18000e701  lea     rax, [rsp+270h+Name]
0x18000e706  lea     rax, [rax+r8*2]
0x18000e70a  lea     rcx, asc_1800414A0; "h"
0x18000e711  sub     rbx, r8
0x18000e714  jz      short loc_18000E737
0x18000e716  test    r14, r14
0x18000e719  jz      short loc_18000E737
0x18000e71b  movzx   edx, word ptr [rcx]
0x18000e71e  test    dx, dx
0x18000e721  jz      short loc_18000E737
0x18000e723  mov     [rax], dx
0x18000e726  add     rcx, 2
0x18000e72a  add     rax, 2
0x18000e72e  dec     r14
0x18000e731  sub     rbx, 1
0x18000e735  jnz     short loc_18000E716
0x18000e737  test    rbx, rbx
0x18000e73a  lea     rdx, [rax-2]
0x18000e73e  cmovnz  rdx, rax
0x18000e742  mov     [rdx], r12w
0x18000e746  lea     r8, [rsp+270h+Name]; lpName
0x18000e74b  xor     edx, edx; bInheritHandle
0x18000e74d  mov     ecx, 1F0003h; dwDesiredAccess
0x18000e752  call    cs:__imp_OpenSemaphoreW
0x18000e759  nop     dword ptr [rax+rax+00h]
0x18000e75e  mov     rbx, rax
0x18000e761  test    rax, rax
0x18000e764  jnz     short loc_18000E7E5
0x18000e766  mov     rcx, [rbp+178h]; this
0x18000e76d  lea     r8, aWil; "wil"
0x18000e774  mov     edx, 0DCh; void *
0x18000e779  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000e77e  mov     esi, eax
0x18000e780  mov     rcx, rdi; this
0x18000e783  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000e788  mov     eax, esi
0x18000e78a  jmp     short loc_18000E7B9
0x18000e78c  call    cs:__imp_GetLastError
0x18000e793  nop     dword ptr [rax+rax+00h]
0x18000e798  cmp     eax, 2
0x18000e79b  jz      loc_18000E857
0x18000e7a1  mov     rcx, [rbp+178h]; this
0x18000e7a8  lea     r8, aWil; "wil"
0x18000e7af  mov     edx, 0D0h; void *
0x18000e7b4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000e7b9  mov     rcx, [rbp+170h+var_30]
0x18000e7c0  xor     rcx, rsp; StackCookie
0x18000e7c3  call    __security_check_cookie
0x18000e7c8  lea     r11, [rsp+270h+var_20]
0x18000e7d0  mov     rbx, [r11+30h]
0x18000e7d4  mov     rsi, [r11+38h]
0x18000e7d8  mov     rsp, r11
0x18000e7db  pop     r15
0x18000e7dd  pop     r14
0x18000e7df  pop     r12
0x18000e7e1  pop     rdi
0x18000e7e2  pop     rbp
0x18000e7e3  retn
0x18000e7e5  lea     rdx, [rsp+270h+var_250]; int *
0x18000e7ea  mov     rcx, rbx; hHandle
0x18000e7ed  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000e7f2  mov     esi, eax
0x18000e7f4  test    eax, eax
0x18000e7f6  js      short loc_18000E820
0x18000e7f8  mov     rcx, rbx; this
0x18000e7fb  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000e800  movsxd  rax, [rsp+270h+var_24C]
0x18000e805  movsxd  rcx, [rsp+270h+var_250]
0x18000e80a  shl     rcx, 1Fh
0x18000e80e  or      rcx, rax
0x18000e811  mov     [r15], rcx
0x18000e814  mov     rcx, rdi; this
0x18000e817  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000e81c  xor     eax, eax
0x18000e81e  jmp     short loc_18000E7B9
0x18000e820  mov     rcx, [rbp+178h]; this
0x18000e827  mov     r9d, eax; char *
0x18000e82a  mov     edx, 0DEh; void *
0x18000e82f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e834  mov     rcx, rbx; this
0x18000e837  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000e83c  jmp     loc_18000E780
0x18000e841  mov     rcx, [rbp+178h]; this
0x18000e848  mov     r9d, eax; char *
0x18000e84b  mov     edx, 0D6h; void *
0x18000e850  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e855  jmp     short loc_18000E85A
0x18000e857  mov     esi, r12d
0x18000e85a  lea     rcx, [rsp+270h+var_248]
0x18000e85f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000e864  jmp     loc_18000E788
```
