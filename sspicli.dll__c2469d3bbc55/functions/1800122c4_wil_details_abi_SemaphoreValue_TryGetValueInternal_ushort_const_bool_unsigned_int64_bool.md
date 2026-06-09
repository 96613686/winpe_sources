# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800122c4`
- end: `0x180012494`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `464`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180012094`
- `0x180016100`

## callees

- `0x1800122c4`
- `0x18001249c`
- `0x1800124f4`
- `0x180014028`
- `0x180016174`
- `0x180016198`
- `0x180016cd8`
- `0x180022190`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012446`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012446`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001235d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800123c2`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001235d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800123c2`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_PCNZWCH pszSrc,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  wchar_t *v5; // rax
  __int64 v6; // r11
  __int64 v7; // r8
  HANDLE v8; // rax
  int ValueFromSemaphore; // eax
  unsigned __int64 v10; // rdx
  unsigned int v11; // r8d
  unsigned int LastError; // ebx
  HANDLE v13; // rax
  unsigned int v14; // r8d
  const char *v15; // r9
  int v16; // eax
  unsigned int v17; // r8d
  unsigned int v19; // r8d
  const char *v20; // r9
  size_t v21; // [rsp+20h] [rbp-E0h]
  size_t v22; // [rsp+20h] [rbp-E0h]
  int v23; // [rsp+30h] [rbp-D0h] BYREF
  int v24; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v25; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v26[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v21);
  v5 = pszDest;
  v6 = 260;
  do
  {
    if ( !*v5 )
      break;
    ++v5;
    --v6;
  }
  while ( v6 );
  if ( v6 )
  {
    v7 = (260 - v6) & -(__int64)(v6 != 0);
    StringCopyWorkerW(&pszDest[v7], 260 - v7, (size_t *)v7, L"_p0", v22);
  }
  v8 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v26[0] = v8;
  if ( v8 )
  {
    v24 = 0;
    v23 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v8, &v24);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore >= 0 )
    {
      StringCchCatW(pszDest, v10, L"h");
      v13 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
      v25 = v13;
      if ( v13 )
      {
        v16 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, &v23);
        LastError = v16;
        if ( v16 >= 0 )
        {
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v25);
          *a3 = v24 | (unsigned __int64)((__int64)v23 << 31);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v26);
          return 0;
        }
        wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v17, (const char *)(unsigned int)v16, v22);
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v14, v15);
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v25);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v11, (const char *)(unsigned int)ValueFromSemaphore, v22);
    }
    goto LABEL_17;
  }
  if ( GetLastError() == 2 )
  {
    LastError = 0;
LABEL_17:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v26);
    return LastError;
  }
  return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v19, v20);
}

```

## disassembly

```asm
0x1800122c4  mov     [rsp-8+arg_8], rbx
0x1800122c9  push    rbp
0x1800122ca  push    rsi
0x1800122cb  push    rdi
0x1800122cc  lea     rbp, [rsp-170h]
0x1800122d4  sub     rsp, 270h
0x1800122db  mov     rax, cs:__security_cookie
0x1800122e2  xor     rax, rsp
0x1800122e5  mov     [rbp+180h+var_20], rax
0x1800122ec  xor     esi, esi
0x1800122ee  mov     r9, rcx; pszSrc
0x1800122f1  mov     ebx, 104h
0x1800122f6  mov     [r8], rsi
0x1800122f9  mov     edx, ebx; cchDest
0x1800122fb  lea     rcx, [rsp+280h+pszDest]; pszDest
0x180012300  mov     rdi, r8
0x180012303  call    StringCopyWorkerW
0x180012308  lea     rax, [rsp+280h+pszDest]
0x18001230d  mov     r11d, ebx
0x180012310  cmp     [rax], si
0x180012313  jz      short loc_18001231F
0x180012315  add     rax, 2
0x180012319  sub     r11, 1
0x18001231d  jnz     short loc_180012310
0x18001231f  mov     rcx, rbx
0x180012322  mov     rax, r11
0x180012325  sub     rcx, r11
0x180012328  neg     rax
0x18001232b  sbb     r8, r8
0x18001232e  and     r8, rcx; pcchNewDestLength
0x180012331  test    r11, r11
0x180012334  jz      short loc_180012351
0x180012336  sub     rbx, r8
0x180012339  lea     rcx, [rsp+280h+pszDest]
0x18001233e  lea     rcx, [rcx+r8*2]; pszDest
0x180012342  mov     rdx, rbx; cchDest
0x180012345  lea     r9, aP0; "_p0"
0x18001234c  call    StringCopyWorkerW
0x180012351  lea     r8, [rsp+280h+pszDest]; lpName
0x180012356  xor     edx, edx; bInheritHandle
0x180012358  mov     ecx, 1F0003h; dwDesiredAccess
0x18001235d  call    cs:__imp_OpenSemaphoreW
0x180012363  mov     [rsp+280h+var_240], rax
0x180012368  test    rax, rax
0x18001236b  jz      loc_180012446
0x180012371  lea     rdx, [rsp+280h+var_24C]; int *
0x180012376  mov     [rsp+280h+var_24C], esi
0x18001237a  mov     rcx, rax; hHandle
0x18001237d  mov     [rsp+280h+var_250], esi
0x180012381  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180012386  mov     ebx, eax
0x180012388  test    eax, eax
0x18001238a  jns     short loc_1800123A5
0x18001238c  mov     rcx, [rbp+188h]; this
0x180012393  mov     r9d, eax; char *
0x180012396  mov     edx, 0D6h; void *
0x18001239b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800123a0  jmp     loc_180012453
0x1800123a5  lea     r8, asc_180032524; "h"
0x1800123ac  lea     rcx, [rsp+280h+pszDest]; unsigned __int16 *
0x1800123b1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800123b6  lea     r8, [rsp+280h+pszDest]; lpName
0x1800123bb  xor     edx, edx; bInheritHandle
0x1800123bd  mov     ecx, 1F0003h; dwDesiredAccess
0x1800123c2  call    cs:__imp_OpenSemaphoreW
0x1800123c8  mov     [rsp+280h+var_248], rax
0x1800123cd  test    rax, rax
0x1800123d0  jz      short loc_180012427
0x1800123d2  lea     rdx, [rsp+280h+var_250]; int *
0x1800123d7  mov     rcx, rax; hHandle
0x1800123da  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800123df  mov     ebx, eax
0x1800123e1  test    eax, eax
0x1800123e3  jns     short loc_1800123FB
0x1800123e5  mov     rcx, [rbp+188h]; this
0x1800123ec  mov     r9d, eax; char *
0x1800123ef  mov     edx, 0DEh; void *
0x1800123f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800123f9  jmp     short loc_18001243A
0x1800123fb  lea     rcx, [rsp+280h+var_248]
0x180012400  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180012405  movsxd  rax, [rsp+280h+var_24C]
0x18001240a  movsxd  rcx, [rsp+280h+var_250]
0x18001240f  shl     rcx, 1Fh
0x180012413  or      rcx, rax
0x180012416  mov     [rdi], rcx
0x180012419  lea     rcx, [rsp+280h+var_240]
0x18001241e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180012423  xor     eax, eax
0x180012425  jmp     short loc_180012472
0x180012427  mov     rcx, [rbp+188h]; this
0x18001242e  mov     edx, 0DCh; void *
0x180012433  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180012438  mov     ebx, eax
0x18001243a  lea     rcx, [rsp+280h+var_248]
0x18001243f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180012444  jmp     short loc_180012453
0x180012446  call    cs:__imp_GetLastError
0x18001244c  cmp     eax, 2
0x18001244f  jnz     short loc_180012461
0x180012451  mov     ebx, esi
0x180012453  lea     rcx, [rsp+280h+var_240]
0x180012458  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001245d  mov     eax, ebx
0x18001245f  jmp     short loc_180012472
0x180012461  mov     rcx, [rbp+188h]; this
0x180012468  mov     edx, 0D0h; void *
0x18001246d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180012472  mov     rcx, [rbp+180h+var_20]
0x180012479  xor     rcx, rsp; StackCookie
0x18001247c  call    __security_check_cookie
0x180012481  mov     rbx, [rsp+280h+arg_8]
0x180012489  add     rsp, 270h
0x180012490  pop     rdi
0x180012491  pop     rsi
0x180012492  pop     rbp
0x180012493  retn
```
