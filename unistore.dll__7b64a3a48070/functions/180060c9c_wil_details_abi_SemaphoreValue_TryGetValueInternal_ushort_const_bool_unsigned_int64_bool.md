# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180060c9c`
- end: `0x180060f78`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `732`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180060a64`

## callees

- `0x180060c9c`
- `0x180060f80`
- `0x180060fac`
- `0x18006b91c`
- `0x18006b9b4`
- `0x180072f2c`
- `0x1800c50f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180060da8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180060e7c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180060da8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180060e7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060f17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060f17`

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
  unsigned int LastError; // ebx
  __int64 v23; // rdx
  WCHAR *v24; // rax
  __int64 v25; // r8
  WCHAR *v26; // rax
  const unsigned __int16 *v27; // rcx
  __int64 v28; // rsi
  WCHAR *v29; // rdx
  wil::details *v30; // rax
  const char *v31; // r9
  wil::details *v32; // rbx
  int v33; // eax
  void *v34; // rdx
  int v35; // esi
  void *v36; // rdx
  void *v38; // rdx
  const char *v39; // r9
  int v40; // [rsp+20h] [rbp-E0h] BYREF
  int v41; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v42; // [rsp+28h] [rbp-D8h] BYREF
  wil::details *v43; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

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
  v42 = v19;
  v20 = v19;
  if ( !v19 )
  {
    if ( GetLastError() == 2 )
      LastError = 0;
    else
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v39);
    goto LABEL_40;
  }
  v41 = 0;
  v40 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v19, &v41);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v40);
LABEL_40:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v42);
    return LastError;
  }
  v23 = 260;
  v24 = Name;
  do
  {
    if ( !*v24 )
      break;
    ++v24;
    --v23;
  }
  while ( v23 );
  v25 = (260 - v23) & -(__int64)(v23 != 0);
  if ( v23 )
  {
    v26 = &Name[v25];
    v27 = L"h";
    v28 = 260 - v25;
    if ( 260 != v25 )
    {
      do
      {
        if ( !v5 )
          break;
        if ( !*v27 )
          break;
        *v26++ = *v27++;
        --v5;
        --v28;
      }
      while ( v28 );
    }
    v29 = v26 - 1;
    if ( v28 )
      v29 = v26;
    *v29 = 0;
  }
  v30 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v43 = v30;
  v32 = v30;
  if ( v30 )
  {
    v33 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v30, &v40);
    v35 = v33;
    if ( v33 >= 0 )
    {
      wil::details::CloseHandle(v32, v34);
      *a3 = v41 | (unsigned __int64)((__int64)v40 << 31);
      wil::details::CloseHandle(v20, v36);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v33, v40);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v43);
    LastError = v35;
    goto LABEL_40;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v31);
  wil::details::CloseHandle(v20, v38);
  return LastError;
}

```

## disassembly

```asm
0x180060c9c  mov     [rsp-8+arg_0], rbx
0x180060ca1  mov     [rsp-8+arg_8], rsi
0x180060ca6  push    rbp
0x180060ca7  push    rdi
0x180060ca8  push    r12
0x180060caa  push    r14
0x180060cac  push    r15
0x180060cae  lea     rbp, [rsp-160h]
0x180060cb6  sub     rsp, 260h
0x180060cbd  mov     rax, cs:__security_cookie
0x180060cc4  xor     rax, rsp
0x180060cc7  mov     [rbp+180h+var_30], rax
0x180060cce  xor     r12d, r12d
0x180060cd1  lea     rax, [rsp+280h+Name]
0x180060cd6  mov     r14d, 7FFFFFFEh
0x180060cdc  mov     [r8], r12
0x180060cdf  mov     esi, 104h
0x180060ce4  mov     r9d, r14d
0x180060ce7  mov     edx, esi
0x180060ce9  mov     r15, r8
0x180060cec  test    r9, r9
0x180060cef  jz      short loc_180060D10
0x180060cf1  movzx   r8d, word ptr [rcx]
0x180060cf5  test    r8w, r8w
0x180060cf9  jz      short loc_180060D10
0x180060cfb  mov     [rax], r8w
0x180060cff  add     rcx, 2
0x180060d03  add     rax, 2
0x180060d07  dec     r9
0x180060d0a  sub     rdx, 1
0x180060d0e  jnz     short loc_180060CEC
0x180060d10  test    rdx, rdx
0x180060d13  lea     rcx, [rax-2]
0x180060d17  mov     rdx, rsi
0x180060d1a  cmovnz  rcx, rax
0x180060d1e  lea     rax, [rsp+280h+Name]
0x180060d23  mov     [rcx], r12w
0x180060d27  cmp     [rax], r12w
0x180060d2b  jz      short loc_180060D37
0x180060d2d  add     rax, 2
0x180060d31  sub     rdx, 1
0x180060d35  jnz     short loc_180060D27
0x180060d37  mov     rcx, rsi
0x180060d3a  mov     rax, rdx
0x180060d3d  sub     rcx, rdx
0x180060d40  neg     rax
0x180060d43  sbb     r8, r8
0x180060d46  and     r8, rcx
0x180060d49  test    rdx, rdx
0x180060d4c  jz      short loc_180060D9C
0x180060d4e  mov     rax, rsi
0x180060d51  lea     rdx, [rsp+280h+Name]
0x180060d56  lea     r9, aP0; "_p0"
0x180060d5d  mov     rcx, r14
0x180060d60  lea     rdx, [rdx+r8*2]
0x180060d64  sub     rax, r8
0x180060d67  jz      short loc_180060D8D
0x180060d69  test    rcx, rcx
0x180060d6c  jz      short loc_180060D8D
0x180060d6e  movzx   r8d, word ptr [r9]
0x180060d72  test    r8w, r8w
0x180060d76  jz      short loc_180060D8D
0x180060d78  mov     [rdx], r8w
0x180060d7c  add     r9, 2
0x180060d80  add     rdx, 2
0x180060d84  dec     rcx
0x180060d87  sub     rax, 1
0x180060d8b  jnz     short loc_180060D69
0x180060d8d  test    rax, rax
0x180060d90  lea     rcx, [rdx-2]
0x180060d94  cmovnz  rcx, rdx
0x180060d98  mov     [rcx], r12w
0x180060d9c  lea     r8, [rsp+280h+Name]; lpName
0x180060da1  xor     edx, edx; bInheritHandle
0x180060da3  mov     ecx, 1F0003h; dwDesiredAccess
0x180060da8  call    cs:__imp_OpenSemaphoreW
0x180060dae  mov     [rsp+280h+var_258], rax
0x180060db3  mov     rdi, rax
0x180060db6  test    rax, rax
0x180060db9  jz      loc_180060F17
0x180060dbf  lea     rdx, [rsp+280h+var_25C]; int *
0x180060dc4  mov     [rsp+280h+var_25C], r12d
0x180060dc9  mov     rcx, rax; hHandle
0x180060dcc  mov     [rsp+280h+var_260], r12d; int
0x180060dd1  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180060dd6  mov     ebx, eax
0x180060dd8  test    eax, eax
0x180060dda  jns     short loc_180060DFC
0x180060ddc  mov     rcx, [rbp+188h]; this
0x180060de3  lea     r8, aWil; "wil"
0x180060dea  mov     r9d, eax; char *
0x180060ded  mov     edx, 0D6h; void *
0x180060df2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180060df7  jmp     loc_180060F41
0x180060dfc  mov     rdx, rsi
0x180060dff  lea     rax, [rsp+280h+Name]
0x180060e04  cmp     [rax], r12w
0x180060e08  jz      short loc_180060E14
0x180060e0a  add     rax, 2
0x180060e0e  sub     rdx, 1
0x180060e12  jnz     short loc_180060E04
0x180060e14  mov     rcx, rsi
0x180060e17  mov     rax, rdx
0x180060e1a  sub     rcx, rdx
0x180060e1d  neg     rax
0x180060e20  sbb     r8, r8
0x180060e23  and     r8, rcx
0x180060e26  test    rdx, rdx
0x180060e29  jz      short loc_180060E70
0x180060e2b  lea     rax, [rsp+280h+Name]
0x180060e30  lea     rax, [rax+r8*2]
0x180060e34  lea     rcx, asc_1800DCAB0; "h"
0x180060e3b  sub     rsi, r8
0x180060e3e  jz      short loc_180060E61
0x180060e40  test    r14, r14
0x180060e43  jz      short loc_180060E61
0x180060e45  movzx   edx, word ptr [rcx]
0x180060e48  test    dx, dx
0x180060e4b  jz      short loc_180060E61
0x180060e4d  mov     [rax], dx
0x180060e50  add     rcx, 2
0x180060e54  add     rax, 2
0x180060e58  dec     r14
0x180060e5b  sub     rsi, 1
0x180060e5f  jnz     short loc_180060E40
0x180060e61  test    rsi, rsi
0x180060e64  lea     rdx, [rax-2]
0x180060e68  cmovnz  rdx, rax
0x180060e6c  mov     [rdx], r12w
0x180060e70  lea     r8, [rsp+280h+Name]; lpName
0x180060e75  xor     edx, edx; bInheritHandle
0x180060e77  mov     ecx, 1F0003h; dwDesiredAccess
0x180060e7c  call    cs:__imp_OpenSemaphoreW
0x180060e82  mov     [rsp+280h+var_250], rax
0x180060e87  mov     rbx, rax
0x180060e8a  test    rax, rax
0x180060e8d  jz      short loc_180060EF3
0x180060e8f  lea     rdx, [rsp+280h+var_260]; int *
0x180060e94  mov     rcx, rax; hHandle
0x180060e97  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180060e9c  mov     esi, eax
0x180060e9e  test    eax, eax
0x180060ea0  jns     short loc_180060ECB
0x180060ea2  mov     rcx, [rbp+188h]; this
0x180060ea9  lea     r8, aWil; "wil"
0x180060eb0  mov     r9d, eax; char *
0x180060eb3  mov     edx, 0DEh; void *
0x180060eb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180060ebd  lea     rcx, [rsp+280h+var_250]
0x180060ec2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180060ec7  mov     ebx, esi
0x180060ec9  jmp     short loc_180060F41
0x180060ecb  mov     rcx, rbx; this
0x180060ece  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180060ed3  movsxd  rax, [rsp+280h+var_25C]
0x180060ed8  movsxd  rcx, [rsp+280h+var_260]
0x180060edd  shl     rcx, 1Fh
0x180060ee1  or      rcx, rax
0x180060ee4  mov     [r15], rcx
0x180060ee7  mov     rcx, rdi; this
0x180060eea  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180060eef  xor     eax, eax
0x180060ef1  jmp     short loc_180060F4D
0x180060ef3  mov     rcx, [rbp+188h]; this
0x180060efa  lea     r8, aWil; "wil"
0x180060f01  mov     edx, 0DCh; void *
0x180060f06  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180060f0b  mov     rcx, rdi; this
0x180060f0e  mov     ebx, eax
0x180060f10  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180060f15  jmp     short loc_180060F4B
0x180060f17  call    cs:__imp_GetLastError
0x180060f1d  cmp     eax, 2
0x180060f20  jnz     short loc_180060F27
0x180060f22  mov     ebx, r12d
0x180060f25  jmp     short loc_180060F41
0x180060f27  mov     rcx, [rbp+188h]; this
0x180060f2e  lea     r8, aWil; "wil"
0x180060f35  mov     edx, 0D0h; void *
0x180060f3a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180060f3f  mov     ebx, eax
0x180060f41  lea     rcx, [rsp+280h+var_258]
0x180060f46  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180060f4b  mov     eax, ebx
0x180060f4d  mov     rcx, [rbp+180h+var_30]
0x180060f54  xor     rcx, rsp; StackCookie
0x180060f57  call    __security_check_cookie
0x180060f5c  lea     r11, [rsp+280h+var_20]
0x180060f64  mov     rbx, [r11+30h]
0x180060f68  mov     rsi, [r11+38h]
0x180060f6c  mov     rsp, r11
0x180060f6f  pop     r15
0x180060f71  pop     r14
0x180060f73  pop     r12
0x180060f75  pop     rdi
0x180060f76  pop     rbp
0x180060f77  retn
```
