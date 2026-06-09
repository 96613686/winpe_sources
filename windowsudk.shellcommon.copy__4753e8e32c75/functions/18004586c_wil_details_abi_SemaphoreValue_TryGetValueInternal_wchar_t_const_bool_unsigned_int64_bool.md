# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x18004586c`
- end: `0x180045b4b`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `735`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180045fb0`
- `0x1800467c0`

## callees

- `0x180045850`
- `0x18004586c`
- `0x180045b54`
- `0x180045cb0`
- `0x1800e2988`
- `0x1800e34bc`
- `0x18015cb00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180045978`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180045a7e`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180045978`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180045a7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004598b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004598b`

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
  const wchar_t *v14; // r9
  __int64 v15; // rcx
  WCHAR *v16; // rdx
  __int64 v17; // rax
  WCHAR *v18; // rcx
  wil::details *v19; // rax
  wil::details *v20; // rdi
  const char *v21; // r9
  int ValueFromSemaphore; // eax
  unsigned int v24; // esi
  __int64 v25; // rdx
  WCHAR *v26; // rax
  __int64 v27; // r8
  WCHAR *v28; // rax
  const wchar_t *v29; // rcx
  __int64 v30; // rbx
  WCHAR *v31; // rdx
  wil::details *v32; // rax
  const char *v33; // r9
  wil::details *v34; // rbx
  unsigned int LastError; // ebx
  void *v36; // rdx
  int v37; // eax
  void *v38; // rdx
  void *v39; // rdx
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
  v43 = v19;
  v20 = v19;
  if ( !v19 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v21);
    return 0;
  }
  v41 = 0;
  v40 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v19, &v41);
  v24 = ValueFromSemaphore;
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
    v25 = 260;
    v26 = Name;
    do
    {
      if ( !*v26 )
        break;
      ++v26;
      --v25;
    }
    while ( v25 );
    v27 = (260 - v25) & -(__int64)(v25 != 0);
    if ( v25 )
    {
      v28 = &Name[v27];
      v29 = L"h";
      v30 = 260 - v27;
      if ( 260 != v27 )
      {
        do
        {
          if ( !v5 )
            break;
          if ( !*v29 )
            break;
          *v28++ = *v29++;
          --v5;
          --v30;
        }
        while ( v30 );
      }
      v31 = v28 - 1;
      if ( v30 )
        v31 = v28;
      *v31 = 0;
    }
    v32 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
    v42 = v32;
    v34 = v32;
    if ( !v32 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v33);
      wil::details::CloseHandle(v20, v36);
      return LastError;
    }
    v37 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v32, &v40);
    v24 = v37;
    if ( v37 >= 0 )
    {
      wil::details::CloseHandle(v34, v38);
      *a3 = v41 | (unsigned __int64)((__int64)v40 << 31);
      wil::details::CloseHandle(v20, v39);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v37, v40);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v42);
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v43);
  return v24;
}

```

## disassembly

```asm
0x18004586c  mov     [rsp-8+arg_0], rbx
0x180045871  mov     [rsp-8+arg_8], rsi
0x180045876  push    rbp
0x180045877  push    rdi
0x180045878  push    r12
0x18004587a  push    r14
0x18004587c  push    r15
0x18004587e  lea     rbp, [rsp-160h]
0x180045886  sub     rsp, 260h
0x18004588d  mov     rax, cs:__security_cookie
0x180045894  xor     rax, rsp
0x180045897  mov     [rbp+180h+var_30], rax
0x18004589e  xor     r12d, r12d
0x1800458a1  lea     rax, [rsp+280h+Name]
0x1800458a6  mov     r14d, 7FFFFFFEh
0x1800458ac  mov     [r8], r12
0x1800458af  mov     ebx, 104h
0x1800458b4  mov     r9d, r14d
0x1800458b7  mov     edx, ebx
0x1800458b9  mov     r15, r8
0x1800458bc  test    r9, r9
0x1800458bf  jz      short loc_1800458E0
0x1800458c1  movzx   r8d, word ptr [rcx]
0x1800458c5  test    r8w, r8w
0x1800458c9  jz      short loc_1800458E0
0x1800458cb  mov     [rax], r8w
0x1800458cf  add     rcx, 2
0x1800458d3  add     rax, 2
0x1800458d7  dec     r9
0x1800458da  sub     rdx, 1
0x1800458de  jnz     short loc_1800458BC
0x1800458e0  test    rdx, rdx
0x1800458e3  lea     rcx, [rax-2]
0x1800458e7  mov     rdx, rbx
0x1800458ea  cmovnz  rcx, rax
0x1800458ee  lea     rax, [rsp+280h+Name]
0x1800458f3  mov     [rcx], r12w
0x1800458f7  cmp     [rax], r12w
0x1800458fb  jz      short loc_180045907
0x1800458fd  add     rax, 2
0x180045901  sub     rdx, 1
0x180045905  jnz     short loc_1800458F7
0x180045907  mov     rcx, rbx
0x18004590a  mov     rax, rdx
0x18004590d  sub     rcx, rdx
0x180045910  neg     rax
0x180045913  sbb     r8, r8
0x180045916  and     r8, rcx
0x180045919  test    rdx, rdx
0x18004591c  jz      short loc_18004596C
0x18004591e  mov     rax, rbx
0x180045921  lea     rdx, [rsp+280h+Name]
0x180045926  lea     r9, aP0; "_p0"
0x18004592d  mov     rcx, r14
0x180045930  lea     rdx, [rdx+r8*2]
0x180045934  sub     rax, r8
0x180045937  jz      short loc_18004595D
0x180045939  test    rcx, rcx
0x18004593c  jz      short loc_18004595D
0x18004593e  movzx   r8d, word ptr [r9]
0x180045942  test    r8w, r8w
0x180045946  jz      short loc_18004595D
0x180045948  mov     [rdx], r8w
0x18004594c  add     r9, 2
0x180045950  add     rdx, 2
0x180045954  dec     rcx
0x180045957  sub     rax, 1
0x18004595b  jnz     short loc_180045939
0x18004595d  test    rax, rax
0x180045960  lea     rcx, [rdx-2]
0x180045964  cmovnz  rcx, rdx
0x180045968  mov     [rcx], r12w
0x18004596c  lea     r8, [rsp+280h+Name]; lpName
0x180045971  xor     edx, edx; bInheritHandle
0x180045973  mov     ecx, 1F0003h; dwDesiredAccess
0x180045978  call    cs:__imp_OpenSemaphoreW
0x18004597e  mov     [rsp+280h+var_250], rax
0x180045983  mov     rdi, rax
0x180045986  test    rax, rax
0x180045989  jnz     short loc_1800459DD
0x18004598b  call    cs:__imp_GetLastError
0x180045991  cmp     eax, 2
0x180045994  jz      loc_180045AF1
0x18004599a  mov     rcx, [rbp+188h]; this
0x1800459a1  lea     r8, aWil; "wil"
0x1800459a8  mov     edx, 0D0h; void *
0x1800459ad  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800459b2  mov     rcx, [rbp+180h+var_30]
0x1800459b9  xor     rcx, rsp; StackCookie
0x1800459bc  call    __security_check_cookie
0x1800459c1  lea     r11, [rsp+280h+var_20]
0x1800459c9  mov     rbx, [r11+30h]
0x1800459cd  mov     rsi, [r11+38h]
0x1800459d1  mov     rsp, r11
0x1800459d4  pop     r15
0x1800459d6  pop     r14
0x1800459d8  pop     r12
0x1800459da  pop     rdi
0x1800459db  pop     rbp
0x1800459dc  retn
0x1800459dd  lea     rdx, [rsp+280h+var_25C]; int *
0x1800459e2  mov     [rsp+280h+var_25C], r12d
0x1800459e7  mov     rcx, rdi; hHandle
0x1800459ea  mov     [rsp+280h+var_260], r12d; int
0x1800459ef  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800459f4  mov     esi, eax
0x1800459f6  test    eax, eax
0x1800459f8  js      loc_180045AF8
0x1800459fe  mov     rdx, rbx
0x180045a01  lea     rax, [rsp+280h+Name]
0x180045a06  cmp     [rax], r12w
0x180045a0a  jz      short loc_180045A16
0x180045a0c  add     rax, 2
0x180045a10  sub     rdx, 1
0x180045a14  jnz     short loc_180045A06
0x180045a16  mov     rcx, rbx
0x180045a19  mov     rax, rdx
0x180045a1c  sub     rcx, rdx
0x180045a1f  neg     rax
0x180045a22  sbb     r8, r8
0x180045a25  and     r8, rcx
0x180045a28  test    rdx, rdx
0x180045a2b  jz      short loc_180045A72
0x180045a2d  lea     rax, [rsp+280h+Name]
0x180045a32  lea     rax, [rax+r8*2]
0x180045a36  lea     rcx, asc_18050452C; "h"
0x180045a3d  sub     rbx, r8
0x180045a40  jz      short loc_180045A63
0x180045a42  test    r14, r14
0x180045a45  jz      short loc_180045A63
0x180045a47  movzx   edx, word ptr [rcx]
0x180045a4a  test    dx, dx
0x180045a4d  jz      short loc_180045A63
0x180045a4f  mov     [rax], dx
0x180045a52  add     rcx, 2
0x180045a56  add     rax, 2
0x180045a5a  dec     r14
0x180045a5d  sub     rbx, 1
0x180045a61  jnz     short loc_180045A42
0x180045a63  test    rbx, rbx
0x180045a66  lea     rdx, [rax-2]
0x180045a6a  cmovnz  rdx, rax
0x180045a6e  mov     [rdx], r12w
0x180045a72  lea     r8, [rsp+280h+Name]; lpName
0x180045a77  xor     edx, edx; bInheritHandle
0x180045a79  mov     ecx, 1F0003h; dwDesiredAccess
0x180045a7e  call    cs:__imp_OpenSemaphoreW
0x180045a84  mov     [rsp+280h+var_258], rax
0x180045a89  mov     rbx, rax
0x180045a8c  test    rax, rax
0x180045a8f  jnz     short loc_180045ABA
0x180045a91  mov     rcx, [rbp+188h]; this
0x180045a98  lea     r8, aWil; "wil"
0x180045a9f  mov     edx, 0DCh; void *
0x180045aa4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180045aa9  mov     rcx, rdi; this
0x180045aac  mov     ebx, eax
0x180045aae  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180045ab3  mov     eax, ebx
0x180045ab5  jmp     loc_1800459B2
0x180045aba  lea     rdx, [rsp+280h+var_260]; int *
0x180045abf  mov     rcx, rbx; hHandle
0x180045ac2  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180045ac7  mov     esi, eax
0x180045ac9  test    eax, eax
0x180045acb  js      short loc_180045B15
0x180045acd  mov     rcx, rbx; this
0x180045ad0  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180045ad5  movsxd  rax, [rsp+280h+var_25C]
0x180045ada  movsxd  rcx, [rsp+280h+var_260]
0x180045adf  shl     rcx, 1Fh
0x180045ae3  or      rcx, rax
0x180045ae6  mov     [r15], rcx
0x180045ae9  mov     rcx, rdi; this
0x180045aec  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180045af1  xor     eax, eax
0x180045af3  jmp     loc_1800459B2
0x180045af8  mov     rcx, [rbp+188h]; this
0x180045aff  lea     r8, aWil; "wil"
0x180045b06  mov     r9d, eax; char *
0x180045b09  mov     edx, 0D6h; void *
0x180045b0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045b13  jmp     short loc_180045B3A
0x180045b15  mov     rcx, [rbp+188h]; this
0x180045b1c  lea     r8, aWil; "wil"
0x180045b23  mov     r9d, eax; char *
0x180045b26  mov     edx, 0DEh; void *
0x180045b2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045b30  lea     rcx, [rsp+280h+var_258]
0x180045b35  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180045b3a  lea     rcx, [rsp+280h+var_250]
0x180045b3f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180045b44  mov     eax, esi
0x180045b46  jmp     loc_1800459B2
```
