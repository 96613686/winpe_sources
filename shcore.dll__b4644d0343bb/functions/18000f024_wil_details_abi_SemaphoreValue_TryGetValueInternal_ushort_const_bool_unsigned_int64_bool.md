# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000f024`
- end: `0x18000f316`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `754`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000b6a8`
- `0x18000d360`

## callees

- `0x18000f008`
- `0x18000f024`
- `0x18000f31c`
- `0x18000f784`
- `0x180053bd8`
- `0x180054410`
- `0x180066910`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000f0e6`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000f239`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000f0e6`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000f239`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f0fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f0fd`

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
  wil::details *v14; // rax
  wil::details *v15; // rdi
  const char *v16; // r9
  int v18; // eax
  void *v19; // rdx
  unsigned int v20; // esi
  void *v21; // rdx
  const wchar_t *v22; // r9
  __int64 v23; // rcx
  WCHAR *v24; // rdx
  __int64 v25; // rax
  WCHAR *v26; // rcx
  int ValueFromSemaphore; // eax
  __int64 v28; // rdx
  WCHAR *v29; // rax
  __int64 v30; // r8
  wil::details *v31; // rax
  const char *v32; // r9
  wil::details *v33; // rbx
  unsigned int LastError; // ebx
  void *v35; // rdx
  WCHAR *v36; // rax
  const wchar_t *v37; // rcx
  __int64 v38; // rbx
  WCHAR *v39; // rdx
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
    v22 = L"_p0";
    v23 = 2147483646;
    v24 = &Name[v13];
    v25 = 260 - v13;
    if ( v13 != 260 )
    {
      do
      {
        if ( !v23 )
          break;
        if ( !*v22 )
          break;
        *v24++ = *v22++;
        --v23;
        --v25;
      }
      while ( v25 );
    }
    v26 = v24 - 1;
    if ( v25 )
      v26 = v24;
    *v26 = 0;
  }
  v14 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v43 = v14;
  v15 = v14;
  if ( !v14 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v16);
    return 0;
  }
  v41 = 0;
  v40 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v14, &v41);
  v20 = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v40);
  }
  else
  {
    v28 = 260;
    v29 = Name;
    do
    {
      if ( !*v29 )
        break;
      ++v29;
      --v28;
    }
    while ( v28 );
    v30 = (260 - v28) & -(__int64)(v28 != 0);
    if ( v28 )
    {
      v36 = &Name[v30];
      v37 = L"h";
      v38 = 260 - v30;
      if ( 260 != v30 )
      {
        do
        {
          if ( !v5 )
            break;
          if ( !*v37 )
            break;
          *v36++ = *v37++;
          --v5;
          --v38;
        }
        while ( v38 );
      }
      v39 = v36 - 1;
      if ( v38 )
        v39 = v36;
      *v39 = 0;
    }
    v31 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
    v42 = v31;
    v33 = v31;
    if ( !v31 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v32);
      wil::details::CloseHandle(v15, v35);
      return LastError;
    }
    v18 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v31, &v40);
    v20 = v18;
    if ( v18 >= 0 )
    {
      wil::details::CloseHandle(v33, v19);
      *a3 = v41 | (unsigned __int64)((__int64)v40 << 31);
      wil::details::CloseHandle(v15, v21);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v18, v40);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v42);
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v43);
  return v20;
}

```

## disassembly

```asm
0x18000f024  mov     [rsp-8+arg_0], rbx
0x18000f029  mov     [rsp-8+arg_8], rsi
0x18000f02e  push    rbp
0x18000f02f  push    rdi
0x18000f030  push    r12
0x18000f032  push    r14
0x18000f034  push    r15
0x18000f036  lea     rbp, [rsp-160h]
0x18000f03e  sub     rsp, 260h
0x18000f045  mov     rax, cs:__security_cookie
0x18000f04c  xor     rax, rsp
0x18000f04f  mov     [rbp+180h+var_30], rax
0x18000f056  xor     r12d, r12d
0x18000f059  lea     rax, [rsp+280h+Name]
0x18000f05e  mov     r14d, 7FFFFFFEh
0x18000f064  mov     [r8], r12
0x18000f067  mov     ebx, 104h
0x18000f06c  mov     r9d, r14d
0x18000f06f  mov     edx, ebx
0x18000f071  mov     r15, r8
0x18000f074  test    r9, r9
0x18000f077  jz      short loc_18000F098
0x18000f079  movzx   r8d, word ptr [rcx]
0x18000f07d  test    r8w, r8w
0x18000f081  jz      short loc_18000F098
0x18000f083  mov     [rax], r8w
0x18000f087  add     rcx, 2
0x18000f08b  add     rax, 2
0x18000f08f  dec     r9
0x18000f092  sub     rdx, 1
0x18000f096  jnz     short loc_18000F074
0x18000f098  test    rdx, rdx
0x18000f09b  lea     rcx, [rax-2]
0x18000f09f  mov     rdx, rbx
0x18000f0a2  cmovnz  rcx, rax
0x18000f0a6  lea     rax, [rsp+280h+Name]
0x18000f0ab  mov     [rcx], r12w
0x18000f0af  cmp     [rax], r12w
0x18000f0b3  jz      short loc_18000F0BF
0x18000f0b5  add     rax, 2
0x18000f0b9  sub     rdx, 1
0x18000f0bd  jnz     short loc_18000F0AF
0x18000f0bf  mov     rcx, rbx
0x18000f0c2  mov     rax, rdx
0x18000f0c5  sub     rcx, rdx
0x18000f0c8  neg     rax
0x18000f0cb  sbb     r8, r8
0x18000f0ce  and     r8, rcx
0x18000f0d1  test    rdx, rdx
0x18000f0d4  jnz     loc_18000F18A
0x18000f0da  lea     r8, [rsp+280h+Name]; lpName
0x18000f0df  xor     edx, edx; bInheritHandle
0x18000f0e1  mov     ecx, 1F0003h; dwDesiredAccess
0x18000f0e6  call    cs:__imp_OpenSemaphoreW
0x18000f0ec  mov     [rsp+280h+var_250], rax
0x18000f0f1  mov     rdi, rax
0x18000f0f4  test    rax, rax
0x18000f0f7  jnz     loc_18000F1DD
0x18000f0fd  call    cs:__imp_GetLastError
0x18000f103  cmp     eax, 2
0x18000f106  jz      short loc_18000F15D
0x18000f108  mov     rcx, [rbp+188h]; this
0x18000f10f  lea     r8, aWil; "wil"
0x18000f116  mov     edx, 0D0h; void *
0x18000f11b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000f120  jmp     short loc_18000F15F
0x18000f122  lea     rdx, [rsp+280h+var_260]; int *
0x18000f127  mov     rcx, rbx; hHandle
0x18000f12a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000f12f  mov     esi, eax
0x18000f131  test    eax, eax
0x18000f133  js      loc_18000F2E0
0x18000f139  mov     rcx, rbx; this
0x18000f13c  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000f141  movsxd  rax, [rsp+280h+var_25C]
0x18000f146  movsxd  rcx, [rsp+280h+var_260]
0x18000f14b  shl     rcx, 1Fh
0x18000f14f  or      rcx, rax
0x18000f152  mov     [r15], rcx
0x18000f155  mov     rcx, rdi; this
0x18000f158  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000f15d  xor     eax, eax
0x18000f15f  mov     rcx, [rbp+180h+var_30]
0x18000f166  xor     rcx, rsp; StackCookie
0x18000f169  call    __security_check_cookie
0x18000f16e  lea     r11, [rsp+280h+var_20]
0x18000f176  mov     rbx, [r11+30h]
0x18000f17a  mov     rsi, [r11+38h]
0x18000f17e  mov     rsp, r11
0x18000f181  pop     r15
0x18000f183  pop     r14
0x18000f185  pop     r12
0x18000f187  pop     rdi
0x18000f188  pop     rbp
0x18000f189  retn
0x18000f18a  mov     rax, rbx
0x18000f18d  lea     rdx, [rsp+280h+Name]
0x18000f192  lea     r9, aP0; "_p0"
0x18000f199  mov     rcx, r14
0x18000f19c  lea     rdx, [rdx+r8*2]
0x18000f1a0  sub     rax, r8
0x18000f1a3  jz      short loc_18000F1C9
0x18000f1a5  test    rcx, rcx
0x18000f1a8  jz      short loc_18000F1C9
0x18000f1aa  movzx   r8d, word ptr [r9]
0x18000f1ae  test    r8w, r8w
0x18000f1b2  jz      short loc_18000F1C9
0x18000f1b4  mov     [rdx], r8w
0x18000f1b8  add     r9, 2
0x18000f1bc  add     rdx, 2
0x18000f1c0  dec     rcx
0x18000f1c3  sub     rax, 1
0x18000f1c7  jnz     short loc_18000F1A5
0x18000f1c9  test    rax, rax
0x18000f1cc  lea     rcx, [rdx-2]
0x18000f1d0  cmovnz  rcx, rdx
0x18000f1d4  mov     [rcx], r12w
0x18000f1d8  jmp     loc_18000F0DA
0x18000f1dd  lea     rdx, [rsp+280h+var_25C]; int *
0x18000f1e2  mov     [rsp+280h+var_25C], r12d
0x18000f1e7  mov     rcx, rdi; hHandle
0x18000f1ea  mov     [rsp+280h+var_260], r12d; int
0x18000f1ef  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000f1f4  mov     esi, eax
0x18000f1f6  test    eax, eax
0x18000f1f8  js      loc_18000F2C3
0x18000f1fe  mov     rdx, rbx
0x18000f201  lea     rax, [rsp+280h+Name]
0x18000f206  cmp     [rax], r12w
0x18000f20a  jz      short loc_18000F216
0x18000f20c  add     rax, 2
0x18000f210  sub     rdx, 1
0x18000f214  jnz     short loc_18000F206
0x18000f216  mov     rcx, rbx
0x18000f219  mov     rax, rdx
0x18000f21c  sub     rcx, rdx
0x18000f21f  neg     rax
0x18000f222  sbb     r8, r8
0x18000f225  and     r8, rcx
0x18000f228  test    rdx, rdx
0x18000f22b  jnz     short loc_18000F279
0x18000f22d  lea     r8, [rsp+280h+Name]; lpName
0x18000f232  xor     edx, edx; bInheritHandle
0x18000f234  mov     ecx, 1F0003h; dwDesiredAccess
0x18000f239  call    cs:__imp_OpenSemaphoreW
0x18000f23f  mov     [rsp+280h+var_258], rax
0x18000f244  mov     rbx, rax
0x18000f247  test    rax, rax
0x18000f24a  jnz     loc_18000F122
0x18000f250  mov     rcx, [rbp+188h]; this
0x18000f257  lea     r8, aWil; "wil"
0x18000f25e  mov     edx, 0DCh; void *
0x18000f263  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000f268  mov     rcx, rdi; this
0x18000f26b  mov     ebx, eax
0x18000f26d  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000f272  mov     eax, ebx
0x18000f274  jmp     loc_18000F15F
0x18000f279  lea     rax, [rsp+280h+Name]
0x18000f27e  lea     rax, [rax+r8*2]
0x18000f282  lea     rcx, asc_1800ABBA8; "h"
0x18000f289  sub     rbx, r8
0x18000f28c  jz      short loc_18000F2AF
0x18000f28e  test    r14, r14
0x18000f291  jz      short loc_18000F2AF
0x18000f293  movzx   edx, word ptr [rcx]
0x18000f296  test    dx, dx
0x18000f299  jz      short loc_18000F2AF
0x18000f29b  mov     [rax], dx
0x18000f29e  add     rcx, 2
0x18000f2a2  add     rax, 2
0x18000f2a6  dec     r14
0x18000f2a9  sub     rbx, 1
0x18000f2ad  jnz     short loc_18000F28E
0x18000f2af  test    rbx, rbx
0x18000f2b2  lea     rdx, [rax-2]
0x18000f2b6  cmovnz  rdx, rax
0x18000f2ba  mov     [rdx], r12w
0x18000f2be  jmp     loc_18000F22D
0x18000f2c3  mov     rcx, [rbp+188h]; this
0x18000f2ca  lea     r8, aWil; "wil"
0x18000f2d1  mov     r9d, eax; char *
0x18000f2d4  mov     edx, 0D6h; void *
0x18000f2d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f2de  jmp     short loc_18000F305
0x18000f2e0  mov     rcx, [rbp+188h]; this
0x18000f2e7  lea     r8, aWil; "wil"
0x18000f2ee  mov     r9d, eax; char *
0x18000f2f1  mov     edx, 0DEh; void *
0x18000f2f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f2fb  lea     rcx, [rsp+280h+var_258]
0x18000f300  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000f305  lea     rcx, [rsp+280h+var_250]
0x18000f30a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000f30f  mov     eax, esi
0x18000f311  jmp     loc_18000F15F
```
