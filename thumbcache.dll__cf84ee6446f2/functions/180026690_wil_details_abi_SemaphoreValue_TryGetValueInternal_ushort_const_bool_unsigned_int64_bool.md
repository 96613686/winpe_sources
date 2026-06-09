# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180026690`
- end: `0x18002698b`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `763`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180026224`
- `0x180026450`

## callees

- `0x18000bfd8`
- `0x180026690`
- `0x180026994`
- `0x180033f30`
- `0x1800346ec`
- `0x180034f50`
- `0x180035830`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002676c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002676c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180026748`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002681d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180026748`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002681d`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v5; // rsi
  __int64 v6; // r9
  __int64 v7; // rdx
  bool v9; // zf
  WCHAR *v10; // rcx
  __int64 v11; // rdx
  WCHAR *v12; // rax
  __int64 v13; // r8
  const char *v14; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  __int64 v18; // rdx
  WCHAR *v19; // rax
  __int64 v20; // r8
  const char *v21; // r9
  int v22; // eax
  const unsigned __int16 *v23; // r9
  __int64 v24; // rcx
  WCHAR *v25; // rdx
  __int64 v26; // rax
  WCHAR *v27; // rcx
  WCHAR *v28; // rax
  const unsigned __int16 *v29; // rcx
  __int64 v30; // rdi
  WCHAR *v31; // rdx
  HANDLE v32; // [rsp+20h] [rbp-E0h] BYREF
  int v33; // [rsp+28h] [rbp-D8h] BYREF
  int v34; // [rsp+2Ch] [rbp-D4h] BYREF
  HANDLE hSemaphore; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE v36; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

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
    v23 = L"_p0";
    v24 = 2147483646;
    v25 = &Name[v13];
    v26 = 260 - v13;
    if ( v13 != 260 )
    {
      do
      {
        if ( !v24 )
          break;
        if ( !*v23 )
          break;
        *v25++ = *v23++;
        --v24;
        --v26;
      }
      while ( v26 );
    }
    v27 = v25 - 1;
    if ( v26 )
      v27 = v25;
    *v27 = 0;
  }
  v32 = OpenSemaphoreW(0x1F0003u, 0, Name);
  ____0PEAX__V___unique_any_t_V__semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAA___QEAPEAX_Z(
    &hSemaphore,
    &v32);
  if ( !hSemaphore )
  {
    if ( GetLastError() == 2 )
      LastError = 0;
    else
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v14);
    goto LABEL_14;
  }
  v34 = 0;
  v33 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(hSemaphore, &v34);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      (int)v32);
    goto LABEL_14;
  }
  v18 = 260;
  v19 = Name;
  do
  {
    if ( !*v19 )
      break;
    ++v19;
    --v18;
  }
  while ( v18 );
  v20 = (260 - v18) & -(__int64)(v18 != 0);
  if ( v18 )
  {
    v28 = &Name[v20];
    v29 = L"h";
    v30 = 260 - v20;
    if ( 260 != v20 )
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
  v36 = OpenSemaphoreW(0x1F0003u, 0, Name);
  ____0PEAX__V___unique_any_t_V__semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAA___QEAPEAX_Z(
    &v32,
    &v36);
  if ( !v32 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v21);
LABEL_24:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v32);
LABEL_14:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hSemaphore);
    return LastError;
  }
  v22 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v32, &v33);
  LastError = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDE,
      (unsigned int)"wil",
      (const char *)(unsigned int)v22,
      (int)v32);
    goto LABEL_24;
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v32);
  *a3 = v34 | (unsigned __int64)((__int64)v33 << 31);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hSemaphore);
  return 0;
}

```

## disassembly

```asm
0x180026690  push    rbp
0x180026692  push    rbx
0x180026693  push    rsi
0x180026694  push    rdi
0x180026695  push    r14
0x180026697  push    r15
0x180026699  lea     rbp, [rsp-168h]
0x1800266a1  sub     rsp, 268h
0x1800266a8  mov     rax, cs:__security_cookie
0x1800266af  xor     rax, rsp
0x1800266b2  mov     [rbp+190h+var_40], rax
0x1800266b9  xor     r15d, r15d
0x1800266bc  lea     rax, [rsp+290h+Name]
0x1800266c1  mov     esi, 7FFFFFFEh
0x1800266c6  mov     [r8], r15
0x1800266c9  mov     edi, 104h
0x1800266ce  mov     r9d, esi
0x1800266d1  mov     edx, edi
0x1800266d3  mov     r14, r8
0x1800266d6  test    r9, r9
0x1800266d9  jz      short loc_1800266FA
0x1800266db  movzx   r8d, word ptr [rcx]
0x1800266df  test    r8w, r8w
0x1800266e3  jz      short loc_1800266FA
0x1800266e5  mov     [rax], r8w
0x1800266e9  add     rcx, 2
0x1800266ed  add     rax, 2
0x1800266f1  dec     r9
0x1800266f4  sub     rdx, 1
0x1800266f8  jnz     short loc_1800266D6
0x1800266fa  test    rdx, rdx
0x1800266fd  lea     rcx, [rax-2]
0x180026701  mov     rdx, rdi
0x180026704  cmovnz  rcx, rax
0x180026708  lea     rax, [rsp+290h+Name]
0x18002670d  mov     [rcx], r15w
0x180026711  cmp     [rax], r15w
0x180026715  jz      short loc_180026721
0x180026717  add     rax, 2
0x18002671b  sub     rdx, 1
0x18002671f  jnz     short loc_180026711
0x180026721  mov     rcx, rdi
0x180026724  mov     rax, rdx
0x180026727  sub     rcx, rdx
0x18002672a  neg     rax
0x18002672d  sbb     r8, r8
0x180026730  and     r8, rcx
0x180026733  test    rdx, rdx
0x180026736  jnz     loc_1800268C6
0x18002673c  lea     r8, [rsp+290h+Name]; lpName
0x180026741  xor     edx, edx; bInheritHandle
0x180026743  mov     ecx, 1F0003h; dwDesiredAccess
0x180026748  call    cs:__imp_OpenSemaphoreW
0x18002674e  lea     rdx, [rsp+290h+var_270]
0x180026753  mov     [rsp+290h+var_270], rax; int
0x180026758  lea     rcx, [rsp+290h+hSemaphore]
0x18002675d  call    ??$?0PEAX$$V@?$unique_any_t@V?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAA@$$QEAPEAX@Z
0x180026762  mov     rcx, [rsp+290h+hSemaphore]; hSemaphore
0x180026767  test    rcx, rcx
0x18002676a  jnz     short loc_1800267C0
0x18002676c  call    cs:__imp_GetLastError
0x180026772  cmp     eax, 2
0x180026775  jz      loc_180026983
0x18002677b  mov     rcx, [rbp+198h]; this
0x180026782  lea     r8, aWil; "wil"
0x180026789  mov     edx, 0D0h; void *
0x18002678e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180026793  mov     ebx, eax
0x180026795  lea     rcx, [rsp+290h+hSemaphore]
0x18002679a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002679f  mov     eax, ebx
0x1800267a1  mov     rcx, [rbp+190h+var_40]
0x1800267a8  xor     rcx, rsp; StackCookie
0x1800267ab  call    __security_check_cookie
0x1800267b0  add     rsp, 268h
0x1800267b7  pop     r15
0x1800267b9  pop     r14
0x1800267bb  pop     rdi
0x1800267bc  pop     rsi
0x1800267bd  pop     rbx
0x1800267be  pop     rbp
0x1800267bf  retn
0x1800267c0  lea     rdx, [rsp+290h+var_264]; int *
0x1800267c5  mov     [rsp+290h+var_264], r15d
0x1800267ca  mov     [rsp+290h+var_268], r15d
0x1800267cf  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800267d4  mov     ebx, eax
0x1800267d6  test    eax, eax
0x1800267d8  js      loc_180026963
0x1800267de  mov     rdx, rdi
0x1800267e1  lea     rax, [rsp+290h+Name]
0x1800267e6  cmp     [rax], r15w
0x1800267ea  jz      short loc_1800267F6
0x1800267ec  add     rax, 2
0x1800267f0  sub     rdx, 1
0x1800267f4  jnz     short loc_1800267E6
0x1800267f6  mov     rcx, rdi
0x1800267f9  mov     rax, rdx
0x1800267fc  sub     rcx, rdx
0x1800267ff  neg     rax
0x180026802  sbb     r8, r8
0x180026805  and     r8, rcx
0x180026808  test    rdx, rdx
0x18002680b  jnz     loc_180026919
0x180026811  lea     r8, [rsp+290h+Name]; lpName
0x180026816  xor     edx, edx; bInheritHandle
0x180026818  mov     ecx, 1F0003h; dwDesiredAccess
0x18002681d  call    cs:__imp_OpenSemaphoreW
0x180026823  lea     rdx, [rsp+290h+var_258]
0x180026828  mov     [rsp+290h+var_258], rax
0x18002682d  lea     rcx, [rsp+290h+var_270]
0x180026832  call    ??$?0PEAX$$V@?$unique_any_t@V?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAA@$$QEAPEAX@Z
0x180026837  mov     rcx, [rsp+290h+var_270]; hSemaphore
0x18002683c  test    rcx, rcx
0x18002683f  jz      short loc_180026880
0x180026841  lea     rdx, [rsp+290h+var_268]; int *
0x180026846  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18002684b  mov     ebx, eax
0x18002684d  test    eax, eax
0x18002684f  js      short loc_1800268A9
0x180026851  lea     rcx, [rsp+290h+var_270]
0x180026856  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002685b  movsxd  rax, [rsp+290h+var_264]
0x180026860  movsxd  rcx, [rsp+290h+var_268]
0x180026865  shl     rcx, 1Fh
0x180026869  or      rcx, rax
0x18002686c  mov     [r14], rcx
0x18002686f  lea     rcx, [rsp+290h+hSemaphore]
0x180026874  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180026879  xor     eax, eax
0x18002687b  jmp     loc_1800267A1
0x180026880  mov     rcx, [rbp+198h]; this
0x180026887  lea     r8, aWil; "wil"
0x18002688e  mov     edx, 0DCh; void *
0x180026893  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180026898  mov     ebx, eax
0x18002689a  lea     rcx, [rsp+290h+var_270]
0x18002689f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800268a4  jmp     loc_180026795
0x1800268a9  mov     rcx, [rbp+198h]; this
0x1800268b0  lea     r8, aWil; "wil"
0x1800268b7  mov     r9d, eax; char *
0x1800268ba  mov     edx, 0DEh; void *
0x1800268bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800268c4  jmp     short loc_18002689A
0x1800268c6  mov     rax, rdi
0x1800268c9  lea     rdx, [rsp+290h+Name]
0x1800268ce  lea     r9, aP0; "_p0"
0x1800268d5  mov     rcx, rsi
0x1800268d8  lea     rdx, [rdx+r8*2]
0x1800268dc  sub     rax, r8
0x1800268df  jz      short loc_180026905
0x1800268e1  test    rcx, rcx
0x1800268e4  jz      short loc_180026905
0x1800268e6  movzx   r8d, word ptr [r9]
0x1800268ea  test    r8w, r8w
0x1800268ee  jz      short loc_180026905
0x1800268f0  mov     [rdx], r8w
0x1800268f4  add     r9, 2
0x1800268f8  add     rdx, 2
0x1800268fc  dec     rcx
0x1800268ff  sub     rax, 1
0x180026903  jnz     short loc_1800268E1
0x180026905  test    rax, rax
0x180026908  lea     rcx, [rdx-2]
0x18002690c  cmovnz  rcx, rdx
0x180026910  mov     [rcx], r15w
0x180026914  jmp     loc_18002673C
0x180026919  lea     rax, [rsp+290h+Name]
0x18002691e  lea     rax, [rax+r8*2]
0x180026922  lea     rcx, asc_180050B58; "h"
0x180026929  sub     rdi, r8
0x18002692c  jz      short loc_18002694F
0x18002692e  test    rsi, rsi
0x180026931  jz      short loc_18002694F
0x180026933  movzx   edx, word ptr [rcx]
0x180026936  test    dx, dx
0x180026939  jz      short loc_18002694F
0x18002693b  mov     [rax], dx
0x18002693e  add     rcx, 2
0x180026942  add     rax, 2
0x180026946  dec     rsi
0x180026949  sub     rdi, 1
0x18002694d  jnz     short loc_18002692E
0x18002694f  test    rdi, rdi
0x180026952  lea     rdx, [rax-2]
0x180026956  cmovnz  rdx, rax
0x18002695a  mov     [rdx], r15w
0x18002695e  jmp     loc_180026811
0x180026963  mov     rcx, [rbp+198h]; this
0x18002696a  lea     r8, aWil; "wil"
0x180026971  mov     r9d, eax; char *
0x180026974  mov     edx, 0D6h; void *
0x180026979  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002697e  jmp     loc_180026795
0x180026983  mov     ebx, r15d
0x180026986  jmp     loc_180026795
```
