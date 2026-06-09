# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180030294`
- end: `0x18003055b`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `711`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18002ff44`
- `0x180030010`

## callees

- `0x180030294`
- `0x180030564`
- `0x1800306bc`
- `0x1800306e8`
- `0x18004221c`
- `0x180042424`
- `0x1800767a0`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x1800303a0`
- `KERNEL32!OpenSemaphoreW` at `0x18003049f`
- `KERNEL32!OpenSemaphoreW` at `0x1800303a0`
- `KERNEL32!OpenSemaphoreW` at `0x18003049f`
- `KERNEL32!GetLastError` at `0x1800303b3`
- `KERNEL32!GetLastError` at `0x1800303b3`

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
  unsigned int v21; // r8d
  const char *v22; // r9
  int ValueFromSemaphore; // eax
  unsigned int v25; // r8d
  unsigned int LastError; // ebx
  __int64 v27; // rdx
  WCHAR *v28; // rax
  __int64 v29; // r8
  WCHAR *v30; // rax
  const unsigned __int16 *v31; // rcx
  __int64 v32; // rsi
  WCHAR *v33; // rdx
  wil::details *v34; // rax
  unsigned int v35; // r8d
  const char *v36; // r9
  wil::details *v37; // rbx
  int v38; // eax
  void *v39; // rdx
  unsigned int v40; // r8d
  int v41; // esi
  void *v42; // rdx
  int v43; // [rsp+20h] [rbp-E0h] BYREF
  int v44; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v45; // [rsp+28h] [rbp-D8h] BYREF
  wil::details *v46; // [rsp+30h] [rbp-D0h] BYREF
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
  v46 = v19;
  v20 = v19;
  if ( v19 )
  {
    v44 = 0;
    v43 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v19, &v44);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v25, (const char *)(unsigned int)ValueFromSemaphore, v43);
    }
    else
    {
      v27 = 260;
      v28 = Name;
      do
      {
        if ( !*v28 )
          break;
        ++v28;
        --v27;
      }
      while ( v27 );
      v29 = (260 - v27) & -(__int64)(v27 != 0);
      if ( v27 )
      {
        v30 = &Name[v29];
        v31 = L"h";
        v32 = 260 - v29;
        if ( 260 != v29 )
        {
          do
          {
            if ( !v5 )
              break;
            if ( !*v31 )
              break;
            *v30++ = *v31++;
            --v5;
            --v32;
          }
          while ( v32 );
        }
        v33 = v30 - 1;
        if ( v32 )
          v33 = v30;
        *v33 = 0;
      }
      v34 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
      v45 = v34;
      v37 = v34;
      if ( v34 )
      {
        v38 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v34, &v43);
        v41 = v38;
        if ( v38 >= 0 )
        {
          wil::details::CloseHandle(v37, v39);
          *a3 = v44 | (unsigned __int64)((__int64)v43 << 31);
          wil::details::CloseHandle(v20, v42);
          return 0;
        }
        wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v40, (const char *)(unsigned int)v38, v43);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v45);
        LastError = v41;
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v35, v36);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v45);
      }
    }
  }
  else
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v21, v22);
    LastError = 0;
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v46);
  return LastError;
}

```

## disassembly

```asm
0x180030294  mov     [rsp-8+arg_0], rbx
0x180030299  mov     [rsp-8+arg_8], rsi
0x18003029e  push    rbp
0x18003029f  push    rdi
0x1800302a0  push    r12
0x1800302a2  push    r14
0x1800302a4  push    r15
0x1800302a6  lea     rbp, [rsp-160h]
0x1800302ae  sub     rsp, 260h
0x1800302b5  mov     rax, cs:__security_cookie
0x1800302bc  xor     rax, rsp
0x1800302bf  mov     [rbp+180h+var_30], rax
0x1800302c6  xor     r12d, r12d
0x1800302c9  lea     rax, [rsp+280h+Name]
0x1800302ce  mov     r14d, 7FFFFFFEh
0x1800302d4  mov     [r8], r12
0x1800302d7  mov     esi, 104h
0x1800302dc  mov     r9d, r14d
0x1800302df  mov     edx, esi
0x1800302e1  mov     r15, r8
0x1800302e4  test    r9, r9
0x1800302e7  jz      short loc_180030308
0x1800302e9  movzx   r8d, word ptr [rcx]
0x1800302ed  test    r8w, r8w
0x1800302f1  jz      short loc_180030308
0x1800302f3  mov     [rax], r8w
0x1800302f7  add     rcx, 2
0x1800302fb  add     rax, 2
0x1800302ff  dec     r9
0x180030302  sub     rdx, 1
0x180030306  jnz     short loc_1800302E4
0x180030308  test    rdx, rdx
0x18003030b  lea     rcx, [rax-2]
0x18003030f  mov     rdx, rsi
0x180030312  cmovnz  rcx, rax
0x180030316  lea     rax, [rsp+280h+Name]
0x18003031b  mov     [rcx], r12w
0x18003031f  cmp     [rax], r12w
0x180030323  jz      short loc_18003032F
0x180030325  add     rax, 2
0x180030329  sub     rdx, 1
0x18003032d  jnz     short loc_18003031F
0x18003032f  mov     rcx, rsi
0x180030332  mov     rax, rdx
0x180030335  sub     rcx, rdx
0x180030338  neg     rax
0x18003033b  sbb     r8, r8
0x18003033e  and     r8, rcx
0x180030341  test    rdx, rdx
0x180030344  jz      short loc_180030394
0x180030346  mov     rax, rsi
0x180030349  lea     rdx, [rsp+280h+Name]
0x18003034e  lea     r9, aP0; "_p0"
0x180030355  mov     rcx, r14
0x180030358  lea     rdx, [rdx+r8*2]
0x18003035c  sub     rax, r8
0x18003035f  jz      short loc_180030385
0x180030361  test    rcx, rcx
0x180030364  jz      short loc_180030385
0x180030366  movzx   r8d, word ptr [r9]
0x18003036a  test    r8w, r8w
0x18003036e  jz      short loc_180030385
0x180030370  mov     [rdx], r8w
0x180030374  add     r9, 2
0x180030378  add     rdx, 2
0x18003037c  dec     rcx
0x18003037f  sub     rax, 1
0x180030383  jnz     short loc_180030361
0x180030385  test    rax, rax
0x180030388  lea     rcx, [rdx-2]
0x18003038c  cmovnz  rcx, rdx
0x180030390  mov     [rcx], r12w
0x180030394  lea     r8, [rsp+280h+Name]; lpName
0x180030399  xor     edx, edx; bInheritHandle
0x18003039b  mov     ecx, 1F0003h; dwDesiredAccess
0x1800303a0  call    cs:__imp_OpenSemaphoreW
0x1800303a6  mov     [rsp+280h+var_250], rax
0x1800303ab  mov     rdi, rax
0x1800303ae  test    rax, rax
0x1800303b1  jnz     short loc_1800303FE
0x1800303b3  call    cs:__imp_GetLastError
0x1800303b9  cmp     eax, 2
0x1800303bc  jz      loc_180030556
0x1800303c2  mov     rcx, [rbp+188h]; this
0x1800303c9  mov     edx, 0D0h; void *
0x1800303ce  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800303d3  mov     rcx, [rbp+180h+var_30]
0x1800303da  xor     rcx, rsp; StackCookie
0x1800303dd  call    __security_check_cookie
0x1800303e2  lea     r11, [rsp+280h+var_20]
0x1800303ea  mov     rbx, [r11+30h]
0x1800303ee  mov     rsi, [r11+38h]
0x1800303f2  mov     rsp, r11
0x1800303f5  pop     r15
0x1800303f7  pop     r14
0x1800303f9  pop     r12
0x1800303fb  pop     rdi
0x1800303fc  pop     rbp
0x1800303fd  retn
0x1800303fe  lea     rdx, [rsp+280h+var_25C]; int *
0x180030403  mov     [rsp+280h+var_25C], r12d
0x180030408  mov     rcx, rdi; hHandle
0x18003040b  mov     [rsp+280h+var_260], r12d; int
0x180030410  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180030415  mov     ebx, eax
0x180030417  test    eax, eax
0x180030419  js      loc_18003051E
0x18003041f  mov     rdx, rsi
0x180030422  lea     rax, [rsp+280h+Name]
0x180030427  cmp     [rax], r12w
0x18003042b  jz      short loc_180030437
0x18003042d  add     rax, 2
0x180030431  sub     rdx, 1
0x180030435  jnz     short loc_180030427
0x180030437  mov     rcx, rsi
0x18003043a  mov     rax, rdx
0x18003043d  sub     rcx, rdx
0x180030440  neg     rax
0x180030443  sbb     r8, r8
0x180030446  and     r8, rcx
0x180030449  test    rdx, rdx
0x18003044c  jz      short loc_180030493
0x18003044e  lea     rax, [rsp+280h+Name]
0x180030453  lea     rax, [rax+r8*2]
0x180030457  lea     rcx, asc_18007DD38; "h"
0x18003045e  sub     rsi, r8
0x180030461  jz      short loc_180030484
0x180030463  test    r14, r14
0x180030466  jz      short loc_180030484
0x180030468  movzx   edx, word ptr [rcx]
0x18003046b  test    dx, dx
0x18003046e  jz      short loc_180030484
0x180030470  mov     [rax], dx
0x180030473  add     rcx, 2
0x180030477  add     rax, 2
0x18003047b  dec     r14
0x18003047e  sub     rsi, 1
0x180030482  jnz     short loc_180030463
0x180030484  test    rsi, rsi
0x180030487  lea     rdx, [rax-2]
0x18003048b  cmovnz  rdx, rax
0x18003048f  mov     [rdx], r12w
0x180030493  lea     r8, [rsp+280h+Name]; lpName
0x180030498  xor     edx, edx; bInheritHandle
0x18003049a  mov     ecx, 1F0003h; dwDesiredAccess
0x18003049f  call    cs:__imp_OpenSemaphoreW
0x1800304a5  mov     [rsp+280h+var_258], rax
0x1800304aa  mov     rbx, rax
0x1800304ad  test    rax, rax
0x1800304b0  jz      short loc_1800304F0
0x1800304b2  lea     rdx, [rsp+280h+var_260]; int *
0x1800304b7  mov     rcx, rax; hHandle
0x1800304ba  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800304bf  mov     esi, eax
0x1800304c1  test    eax, eax
0x1800304c3  js      short loc_180030534
0x1800304c5  mov     rcx, rbx; this
0x1800304c8  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800304cd  movsxd  rax, [rsp+280h+var_25C]
0x1800304d2  movsxd  rcx, [rsp+280h+var_260]
0x1800304d7  shl     rcx, 1Fh
0x1800304db  or      rcx, rax
0x1800304de  mov     [r15], rcx
0x1800304e1  mov     rcx, rdi; this
0x1800304e4  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800304e9  xor     eax, eax
0x1800304eb  jmp     loc_1800303D3
0x1800304f0  mov     rcx, [rbp+188h]; this
0x1800304f7  mov     edx, 0DCh; void *
0x1800304fc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180030501  lea     rcx, [rsp+280h+var_258]
0x180030506  mov     ebx, eax
0x180030508  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003050d  lea     rcx, [rsp+280h+var_250]
0x180030512  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180030517  mov     eax, ebx
0x180030519  jmp     loc_1800303D3
0x18003051e  mov     rcx, [rbp+188h]; this
0x180030525  mov     r9d, eax; char *
0x180030528  mov     edx, 0D6h; void *
0x18003052d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030532  jmp     short loc_18003050D
0x180030534  mov     rcx, [rbp+188h]; this
0x18003053b  mov     r9d, esi; char *
0x18003053e  mov     edx, 0DEh; void *
0x180030543  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030548  lea     rcx, [rsp+280h+var_258]
0x18003054d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180030552  mov     ebx, esi
0x180030554  jmp     short loc_18003050D
0x180030556  mov     ebx, r12d
0x180030559  jmp     short loc_18003050D
```
