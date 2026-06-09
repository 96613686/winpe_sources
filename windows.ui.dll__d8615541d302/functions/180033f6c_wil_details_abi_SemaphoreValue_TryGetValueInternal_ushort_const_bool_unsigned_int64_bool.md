# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180033f6c`
- end: `0x180034266`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `762`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18003384c`
- `0x180033cdc`

## callees

- `0x180014754`
- `0x180033a50`
- `0x180033f6c`
- `0x18003426c`
- `0x1800343d8`
- `0x1800581b8`
- `0x1800c73c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003402a`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180034146`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003402a`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180034146`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034041`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034041`

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
  const unsigned __int16 *v18; // r9
  __int64 v19; // rcx
  WCHAR *v20; // rdx
  __int64 v21; // rax
  WCHAR *v22; // rcx
  int ValueFromSemaphore; // eax
  unsigned int LastError; // ebx
  __int64 v25; // rdx
  WCHAR *v26; // rax
  __int64 v27; // r8
  wil::details *v28; // rax
  const char *v29; // r9
  wil::details *v30; // rbx
  void *v31; // rdx
  int v32; // eax
  void *v33; // rdx
  int v34; // esi
  void *v35; // rdx
  WCHAR *v36; // rax
  const unsigned __int16 *v37; // rcx
  __int64 v38; // rsi
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
    v18 = L"_p0";
    v19 = 2147483646;
    v20 = &Name[v13];
    v21 = 260 - v13;
    if ( v13 != 260 )
    {
      do
      {
        if ( !v19 )
          break;
        if ( !*v18 )
          break;
        *v20++ = *v18++;
        --v19;
        --v21;
      }
      while ( v21 );
    }
    v22 = v20 - 1;
    if ( v21 )
      v22 = v20;
    *v22 = 0;
  }
  v14 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v43 = v14;
  v15 = v14;
  if ( !v14 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v16);
    LastError = 0;
    goto LABEL_41;
  }
  v41 = 0;
  v40 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v14, &v41);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v40);
LABEL_41:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v43);
    return LastError;
  }
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
    v36 = &Name[v27];
    v37 = L"h";
    v38 = 260 - v27;
    if ( 260 != v27 )
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
  v28 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v42 = v28;
  v30 = v28;
  if ( !v28 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v29);
    wil::details::CloseHandle(v15, v31);
    return LastError;
  }
  v32 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v28, &v40);
  v34 = v32;
  if ( v32 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v32, v40);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v42);
    LastError = v34;
    goto LABEL_41;
  }
  wil::details::CloseHandle(v30, v33);
  *a3 = v41 | (unsigned __int64)((__int64)v40 << 31);
  wil::details::CloseHandle(v15, v35);
  return 0;
}

```

## disassembly

```asm
0x180033f6c  mov     [rsp-8+arg_0], rbx
0x180033f71  mov     [rsp-8+arg_8], rsi
0x180033f76  push    rbp
0x180033f77  push    rdi
0x180033f78  push    r12
0x180033f7a  push    r14
0x180033f7c  push    r15
0x180033f7e  lea     rbp, [rsp-160h]
0x180033f86  sub     rsp, 260h
0x180033f8d  mov     rax, cs:__security_cookie
0x180033f94  xor     rax, rsp
0x180033f97  mov     [rbp+180h+var_30], rax
0x180033f9e  xor     r12d, r12d
0x180033fa1  lea     rax, [rsp+280h+Name]
0x180033fa6  mov     r14d, 7FFFFFFEh
0x180033fac  mov     [r8], r12
0x180033faf  mov     esi, 104h
0x180033fb4  mov     r9d, r14d
0x180033fb7  mov     edx, esi
0x180033fb9  mov     r15, r8
0x180033fbc  test    r9, r9
0x180033fbf  jz      short loc_180033FE0
0x180033fc1  movzx   r8d, word ptr [rcx]
0x180033fc5  test    r8w, r8w
0x180033fc9  jz      short loc_180033FE0
0x180033fcb  mov     [rax], r8w
0x180033fcf  add     rcx, 2
0x180033fd3  add     rax, 2
0x180033fd7  dec     r9
0x180033fda  sub     rdx, 1
0x180033fde  jnz     short loc_180033FBC
0x180033fe0  test    rdx, rdx
0x180033fe3  lea     rcx, [rax-2]
0x180033fe7  mov     rdx, rsi
0x180033fea  cmovnz  rcx, rax
0x180033fee  lea     rax, [rsp+280h+Name]
0x180033ff3  mov     [rcx], r12w
0x180033ff7  cmp     [rax], r12w
0x180033ffb  jz      short loc_180034007
0x180033ffd  add     rax, 2
0x180034001  sub     rdx, 1
0x180034005  jnz     short loc_180033FF7
0x180034007  mov     rcx, rsi
0x18003400a  mov     rax, rdx
0x18003400d  sub     rcx, rdx
0x180034010  neg     rax
0x180034013  sbb     r8, r8
0x180034016  and     r8, rcx
0x180034019  test    rdx, rdx
0x18003401c  jnz     short loc_180034093
0x18003401e  lea     r8, [rsp+280h+Name]; lpName
0x180034023  xor     edx, edx; bInheritHandle
0x180034025  mov     ecx, 1F0003h; dwDesiredAccess
0x18003402a  call    cs:__imp_OpenSemaphoreW
0x180034030  mov     [rsp+280h+var_250], rax
0x180034035  mov     rdi, rax
0x180034038  test    rax, rax
0x18003403b  jnz     loc_1800340E6
0x180034041  call    cs:__imp_GetLastError
0x180034047  cmp     eax, 2
0x18003404a  jz      loc_180034254
0x180034050  mov     rcx, [rbp+188h]; this
0x180034057  lea     r8, aWil; "wil"
0x18003405e  mov     edx, 0D0h; void *
0x180034063  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180034068  mov     rcx, [rbp+180h+var_30]
0x18003406f  xor     rcx, rsp; StackCookie
0x180034072  call    __security_check_cookie
0x180034077  lea     r11, [rsp+280h+var_20]
0x18003407f  mov     rbx, [r11+30h]
0x180034083  mov     rsi, [r11+38h]
0x180034087  mov     rsp, r11
0x18003408a  pop     r15
0x18003408c  pop     r14
0x18003408e  pop     r12
0x180034090  pop     rdi
0x180034091  pop     rbp
0x180034092  retn
0x180034093  mov     rax, rsi
0x180034096  lea     rdx, [rsp+280h+Name]
0x18003409b  lea     r9, aP0; "_p0"
0x1800340a2  mov     rcx, r14
0x1800340a5  lea     rdx, [rdx+r8*2]
0x1800340a9  sub     rax, r8
0x1800340ac  jz      short loc_1800340D2
0x1800340ae  test    rcx, rcx
0x1800340b1  jz      short loc_1800340D2
0x1800340b3  movzx   r8d, word ptr [r9]
0x1800340b7  test    r8w, r8w
0x1800340bb  jz      short loc_1800340D2
0x1800340bd  mov     [rdx], r8w
0x1800340c1  add     r9, 2
0x1800340c5  add     rdx, 2
0x1800340c9  dec     rcx
0x1800340cc  sub     rax, 1
0x1800340d0  jnz     short loc_1800340AE
0x1800340d2  test    rax, rax
0x1800340d5  lea     rcx, [rdx-2]
0x1800340d9  cmovnz  rcx, rdx
0x1800340dd  mov     [rcx], r12w
0x1800340e1  jmp     loc_18003401E
0x1800340e6  lea     rdx, [rsp+280h+var_25C]; int *
0x1800340eb  mov     [rsp+280h+var_25C], r12d
0x1800340f0  mov     rcx, rdi; hHandle
0x1800340f3  mov     [rsp+280h+var_260], r12d; int
0x1800340f8  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800340fd  mov     ebx, eax
0x1800340ff  test    eax, eax
0x180034101  js      loc_18003420E
0x180034107  mov     rdx, rsi
0x18003410a  lea     rax, [rsp+280h+Name]
0x18003410f  cmp     [rax], r12w
0x180034113  jz      short loc_18003411F
0x180034115  add     rax, 2
0x180034119  sub     rdx, 1
0x18003411d  jnz     short loc_18003410F
0x18003411f  mov     rcx, rsi
0x180034122  mov     rax, rdx
0x180034125  sub     rcx, rdx
0x180034128  neg     rax
0x18003412b  sbb     r8, r8
0x18003412e  and     r8, rcx
0x180034131  test    rdx, rdx
0x180034134  jnz     loc_1800341C4
0x18003413a  lea     r8, [rsp+280h+Name]; lpName
0x18003413f  xor     edx, edx; bInheritHandle
0x180034141  mov     ecx, 1F0003h; dwDesiredAccess
0x180034146  call    cs:__imp_OpenSemaphoreW
0x18003414c  mov     [rsp+280h+var_258], rax
0x180034151  mov     rbx, rax
0x180034154  test    rax, rax
0x180034157  jnz     short loc_180034182
0x180034159  mov     rcx, [rbp+188h]; this
0x180034160  lea     r8, aWil; "wil"
0x180034167  mov     edx, 0DCh; void *
0x18003416c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180034171  mov     rcx, rdi; this
0x180034174  mov     ebx, eax
0x180034176  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18003417b  mov     eax, ebx
0x18003417d  jmp     loc_180034068
0x180034182  lea     rdx, [rsp+280h+var_260]; int *
0x180034187  mov     rcx, rbx; hHandle
0x18003418a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18003418f  mov     esi, eax
0x180034191  test    eax, eax
0x180034193  js      loc_18003422B
0x180034199  mov     rcx, rbx; this
0x18003419c  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800341a1  movsxd  rax, [rsp+280h+var_25C]
0x1800341a6  movsxd  rcx, [rsp+280h+var_260]
0x1800341ab  shl     rcx, 1Fh
0x1800341af  or      rcx, rax
0x1800341b2  mov     [r15], rcx
0x1800341b5  mov     rcx, rdi; this
0x1800341b8  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800341bd  xor     eax, eax
0x1800341bf  jmp     loc_180034068
0x1800341c4  lea     rax, [rsp+280h+Name]
0x1800341c9  lea     rax, [rax+r8*2]
0x1800341cd  lea     rcx, asc_180109AD8; "h"
0x1800341d4  sub     rsi, r8
0x1800341d7  jz      short loc_1800341FA
0x1800341d9  test    r14, r14
0x1800341dc  jz      short loc_1800341FA
0x1800341de  movzx   edx, word ptr [rcx]
0x1800341e1  test    dx, dx
0x1800341e4  jz      short loc_1800341FA
0x1800341e6  mov     [rax], dx
0x1800341e9  add     rcx, 2
0x1800341ed  add     rax, 2
0x1800341f1  dec     r14
0x1800341f4  sub     rsi, 1
0x1800341f8  jnz     short loc_1800341D9
0x1800341fa  test    rsi, rsi
0x1800341fd  lea     rdx, [rax-2]
0x180034201  cmovnz  rdx, rax
0x180034205  mov     [rdx], r12w
0x180034209  jmp     loc_18003413A
0x18003420e  mov     rcx, [rbp+188h]; this
0x180034215  lea     r8, aWil; "wil"
0x18003421c  mov     r9d, eax; char *
0x18003421f  mov     edx, 0D6h; void *
0x180034224  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034229  jmp     short loc_180034257
0x18003422b  mov     rcx, [rbp+188h]; this
0x180034232  lea     r8, aWil; "wil"
0x180034239  mov     r9d, esi; char *
0x18003423c  mov     edx, 0DEh; void *
0x180034241  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034246  lea     rcx, [rsp+280h+var_258]
0x18003424b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180034250  mov     ebx, esi
0x180034252  jmp     short loc_180034257
0x180034254  mov     ebx, r12d
0x180034257  lea     rcx, [rsp+280h+var_250]
0x18003425c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180034261  jmp     loc_18003417B
```
