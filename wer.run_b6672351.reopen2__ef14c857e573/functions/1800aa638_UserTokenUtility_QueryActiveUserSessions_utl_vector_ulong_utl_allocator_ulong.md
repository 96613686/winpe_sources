# UserTokenUtility::QueryActiveUserSessions(utl::vector<ulong,utl::allocator<ulong>> &)

- ea: `0x1800aa638`
- end: `0x1800aa835`
- name: `?QueryActiveUserSessions@UserTokenUtility@@SAJAEAV?$vector@KV?$allocator@K@utl@@@utl@@@Z`
- size: `509`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180052cc4`

## callees

- `0x1800058a4`
- `0x180007fd8`
- `0x18002d930`
- `0x1800560ac`
- `0x1800aa638`
- `0x1800aa83c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa743`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa743`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x1800aa733`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x1800aa733`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x1800aa815`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x1800aa815`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x1800aa684`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x1800aa684`

## string_xrefs

- `0x1800aa7f8`: `onecore\windows\feedback\core\wercommon\libex\usertokenutility.cpp`

## pseudocode

```c
__int64 __fastcall UserTokenUtility::QueryActiveUserSessions(__int64 *a1)
{
  int v2; // ebx
  const char *v3; // rax
  __int64 v4; // rdx
  unsigned int v5; // ecx
  unsigned __int64 v6; // rax
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // rax
  unsigned int i; // ebx
  unsigned int v10; // esi
  __int64 v11; // rax
  unsigned int *v12; // rax
  unsigned int *v13; // rcx
  __int64 v14; // r14
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // rdx
  const char *v18; // [rsp+28h] [rbp-18h]
  _DWORD v19[4]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  unsigned int v21; // [rsp+78h] [rbp+38h] BYREF
  __int64 v22; // [rsp+80h] [rbp+40h] BYREF
  __int64 v23; // [rsp+88h] [rbp+48h] BYREF

  v23 = 0;
  v21 = 0;
  if ( !(unsigned __int8)IsQueryUserTokenPresent() )
  {
    v2 = -2147024846;
    v3 = "System does not support multiple user sessions";
    v4 = 805;
LABEL_32:
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\windows\\feedback\\core\\wercommon\\libex\\usertokenutility.cpp",
      (const char *)(unsigned int)v2,
      (int)v3,
      v18);
    goto LABEL_33;
  }
  v2 = UMgrEnumerateSessionUsers(&v21, &v23);
  if ( v2 < 0 )
  {
    v3 = "UMgrEnumerateSessionUsers failed.";
    v4 = 813;
    goto LABEL_32;
  }
  v5 = v21;
  if ( !v21 || !v23 )
  {
    v2 = -2147023888;
    v3 = "No session users available.";
    v4 = 850;
    goto LABEL_32;
  }
  v6 = (a1[2] - *a1) >> 2;
  if ( v21 > v6 )
  {
    v7 = v21;
    v8 = 7 * (v6 >> 2) + 8;
    if ( v8 >= v21 )
      v7 = v8;
    if ( v7 > 0x1FFFFFFFFFFFFFFFLL )
      v7 = 0x1FFFFFFFFFFFFFFFLL;
    if ( v21 <= v7 )
    {
      utl::vector<unsigned long,utl::allocator<unsigned long>>::_SetCapacity(a1);
      v5 = v21;
    }
  }
  for ( i = 0; i < v5; ++i )
  {
    v19[0] = *(_DWORD *)(v23 + 16LL * i + 8);
    v10 = v19[0];
    v22 = 0;
    v11 = tlx::replace<tlx::file_handle_traits>(&v22);
    if ( (unsigned int)QueryUserToken(v10, v11) || GetLastError() != 1008 )
    {
      v12 = (unsigned int *)a1[1];
      v13 = (unsigned int *)a1[2];
      if ( v12 == v13 )
      {
        v14 = *a1;
        v15 = ((__int64)v13 - *a1) >> 2;
        v16 = 7 * (v15 >> 2) + 8;
        if ( v16 > 0x1FFFFFFFFFFFFFFFLL )
          v16 = 0x1FFFFFFFFFFFFFFFLL;
        if ( v15 >= v16 || !(unsigned __int8)utl::vector<unsigned long,utl::allocator<unsigned long>>::_SetCapacity(a1) )
        {
          v2 = -2147024882;
          tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v22);
          goto LABEL_33;
        }
        if ( (unsigned __int64)v19 - v14 < a1[1] - *a1 )
          v10 = *(_DWORD *)((char *)v19 + *a1 - v14);
        *(_DWORD *)a1[1] = v10;
      }
      else
      {
        *v12 = v10;
      }
      a1[1] += 4;
    }
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v22);
    v5 = v21;
  }
  v2 = 0;
LABEL_33:
  if ( v23 )
    UMgrFreeSessionUsers();
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800aa638  mov     [rsp-28h+arg_0], rbx
0x1800aa63d  push    rbp
0x1800aa63e  push    rsi
0x1800aa63f  push    rdi
0x1800aa640  push    r12
0x1800aa642  push    r14
0x1800aa644  mov     rbp, rsp
0x1800aa647  sub     rsp, 40h
0x1800aa64b  mov     rdi, rcx
0x1800aa64e  mov     [rbp+arg_18], 0
0x1800aa656  mov     [rbp+arg_8], 0
0x1800aa65d  call    IsQueryUserTokenPresent
0x1800aa662  test    al, al
0x1800aa664  jnz     short loc_1800AA67C
0x1800aa666  mov     ebx, 80070032h
0x1800aa66b  lea     rax, aSystemDoesNotS; "System does not support multiple user s"...
0x1800aa672  mov     edx, 325h
0x1800aa677  jmp     loc_1800AA7F4
0x1800aa67c  lea     rdx, [rbp+arg_18]
0x1800aa680  lea     rcx, [rbp+arg_8]
0x1800aa684  call    cs:__imp_UMgrEnumerateSessionUsers
0x1800aa68b  nop     dword ptr [rax+rax+00h]
0x1800aa690  mov     ebx, eax
0x1800aa692  test    eax, eax
0x1800aa694  jns     short loc_1800AA6A7
0x1800aa696  lea     rax, aUmgrenumerates_0; "UMgrEnumerateSessionUsers failed."
0x1800aa69d  mov     edx, 32Dh
0x1800aa6a2  jmp     loc_1800AA7F4
0x1800aa6a7  mov     ecx, [rbp+arg_8]
0x1800aa6aa  test    ecx, ecx
0x1800aa6ac  jz      loc_1800AA7E3
0x1800aa6b2  cmp     [rbp+arg_18], 0
0x1800aa6b7  jz      loc_1800AA7E3
0x1800aa6bd  mov     rax, [rdi+10h]
0x1800aa6c1  mov     r12, 1FFFFFFFFFFFFFFFh
0x1800aa6cb  sub     rax, [rdi]
0x1800aa6ce  sar     rax, 2
0x1800aa6d2  cmp     rcx, rax
0x1800aa6d5  jbe     short loc_1800AA703
0x1800aa6d7  shr     rax, 2
0x1800aa6db  mov     edx, ecx
0x1800aa6dd  imul    rax, 7
0x1800aa6e1  add     rax, 8
0x1800aa6e5  cmp     rax, rcx
0x1800aa6e8  cmovnb  rdx, rax
0x1800aa6ec  cmp     rdx, r12
0x1800aa6ef  cmova   rdx, r12
0x1800aa6f3  cmp     rcx, rdx
0x1800aa6f6  ja      short loc_1800AA703
0x1800aa6f8  mov     rcx, rdi
0x1800aa6fb  call    ?_SetCapacity@?$vector@KV?$allocator@K@utl@@@utl@@AEAA_N_K@Z; utl::vector<ulong,utl::allocator<ulong>>::_SetCapacity(unsigned __int64)
0x1800aa700  mov     ecx, [rbp+arg_8]
0x1800aa703  xor     ebx, ebx
0x1800aa705  cmp     ebx, ecx
0x1800aa707  jnb     loc_1800AA7DF
0x1800aa70d  mov     rax, [rbp+arg_18]
0x1800aa711  mov     ecx, ebx
0x1800aa713  add     rcx, rcx
0x1800aa716  mov     esi, [rax+rcx*8+8]
0x1800aa71a  lea     rcx, [rbp+arg_10]
0x1800aa71e  mov     [rbp+var_10], esi
0x1800aa721  mov     [rbp+arg_10], 0
0x1800aa729  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x1800aa72e  mov     rdx, rax
0x1800aa731  mov     ecx, esi
0x1800aa733  call    cs:__imp_QueryUserToken
0x1800aa73a  nop     dword ptr [rax+rax+00h]
0x1800aa73f  test    eax, eax
0x1800aa741  jnz     short loc_1800AA756
0x1800aa743  call    cs:__imp_GetLastError
0x1800aa74a  nop     dword ptr [rax+rax+00h]
0x1800aa74f  cmp     eax, 3F0h
0x1800aa754  jz      short loc_1800AA7BC
0x1800aa756  mov     rax, [rdi+8]
0x1800aa75a  mov     rcx, [rdi+10h]
0x1800aa75e  cmp     rax, rcx
0x1800aa761  jz      short loc_1800AA767
0x1800aa763  mov     [rax], esi
0x1800aa765  jmp     short loc_1800AA7B7
0x1800aa767  mov     r14, [rdi]
0x1800aa76a  sub     rcx, r14
0x1800aa76d  sar     rcx, 2
0x1800aa771  mov     rax, rcx
0x1800aa774  shr     rax, 2
0x1800aa778  imul    rdx, rax, 7
0x1800aa77c  add     rdx, 8
0x1800aa780  cmp     rdx, r12
0x1800aa783  cmova   rdx, r12
0x1800aa787  cmp     rcx, rdx
0x1800aa78a  jnb     short loc_1800AA7CF
0x1800aa78c  mov     rcx, rdi
0x1800aa78f  call    ?_SetCapacity@?$vector@KV?$allocator@K@utl@@@utl@@AEAA_N_K@Z; utl::vector<ulong,utl::allocator<ulong>>::_SetCapacity(unsigned __int64)
0x1800aa794  test    al, al
0x1800aa796  jz      short loc_1800AA7CF
0x1800aa798  mov     r8, [rdi+8]
0x1800aa79c  lea     rcx, [rbp+var_10]
0x1800aa7a0  mov     rdx, [rdi]
0x1800aa7a3  mov     rax, r8
0x1800aa7a6  sub     rax, rdx
0x1800aa7a9  sub     rcx, r14
0x1800aa7ac  cmp     rcx, rax
0x1800aa7af  jnb     short loc_1800AA7B4
0x1800aa7b1  mov     esi, [rcx+rdx]
0x1800aa7b4  mov     [r8], esi
0x1800aa7b7  add     qword ptr [rdi+8], 4
0x1800aa7bc  lea     rcx, [rbp+arg_10]
0x1800aa7c0  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800aa7c5  mov     ecx, [rbp+arg_8]
0x1800aa7c8  inc     ebx
0x1800aa7ca  jmp     loc_1800AA705
0x1800aa7cf  lea     rcx, [rbp+arg_10]
0x1800aa7d3  mov     ebx, 8007000Eh
0x1800aa7d8  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800aa7dd  jmp     short loc_1800AA80C
0x1800aa7df  xor     ebx, ebx
0x1800aa7e1  jmp     short loc_1800AA80C
0x1800aa7e3  mov     ebx, 800703F0h
0x1800aa7e8  lea     rax, aNoSessionUsers; "No session users available."
0x1800aa7ef  mov     edx, 352h; void *
0x1800aa7f4  mov     rcx, [rbp+28h]; this
0x1800aa7f8  lea     r8, aOnecoreWindows_3; "onecore\\windows\\feedback\\core\\werco"...
0x1800aa7ff  mov     r9d, ebx; char *
0x1800aa802  mov     qword ptr [rsp+40h+var_20], rax; int
0x1800aa807  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800aa80c  mov     rcx, [rbp+arg_18]
0x1800aa810  test    rcx, rcx
0x1800aa813  jz      short loc_1800AA821
0x1800aa815  call    cs:__imp_UMgrFreeSessionUsers
0x1800aa81c  nop     dword ptr [rax+rax+00h]
0x1800aa821  mov     eax, ebx
0x1800aa823  mov     rbx, [rsp+40h+arg_0]
0x1800aa828  add     rsp, 40h
0x1800aa82c  pop     r14
0x1800aa82e  pop     r12
0x1800aa830  pop     rdi
0x1800aa831  pop     rsi
0x1800aa832  pop     rbp
0x1800aa833  retn
```
