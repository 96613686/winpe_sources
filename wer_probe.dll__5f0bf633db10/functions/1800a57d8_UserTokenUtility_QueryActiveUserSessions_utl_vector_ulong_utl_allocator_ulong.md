# UserTokenUtility::QueryActiveUserSessions(utl::vector<ulong,utl::allocator<ulong>> &)

- ea: `0x1800a57d8`
- end: `0x1800a59bc`
- name: `?QueryActiveUserSessions@UserTokenUtility@@SAJAEAV?$vector@KV?$allocator@K@utl@@@utl@@@Z`
- size: `484`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800507bc`

## callees

- `0x180007e10`
- `0x18001a2cc`
- `0x18002bed4`
- `0x180053b3c`
- `0x1800a57d8`
- `0x1800a59c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a58d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a58d7`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x1800a58cd`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x1800a58cd`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x1800a59a3`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x1800a59a3`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x1800a5824`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x1800a5824`

## string_xrefs

- `0x1800a5986`: `onecore\windows\feedback\core\wercommon\libex\usertokenutility.cpp`

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
0x1800a57d8  mov     [rsp-28h+arg_0], rbx
0x1800a57dd  push    rbp
0x1800a57de  push    rsi
0x1800a57df  push    rdi
0x1800a57e0  push    r12
0x1800a57e2  push    r14
0x1800a57e4  mov     rbp, rsp
0x1800a57e7  sub     rsp, 40h
0x1800a57eb  mov     rdi, rcx
0x1800a57ee  mov     [rbp+arg_18], 0
0x1800a57f6  mov     [rbp+arg_8], 0
0x1800a57fd  call    IsQueryUserTokenPresent
0x1800a5802  test    al, al
0x1800a5804  jnz     short loc_1800A581C
0x1800a5806  mov     ebx, 80070032h
0x1800a580b  lea     rax, aSystemDoesNotS; "System does not support multiple user s"...
0x1800a5812  mov     edx, 325h
0x1800a5817  jmp     loc_1800A5982
0x1800a581c  lea     rdx, [rbp+arg_18]
0x1800a5820  lea     rcx, [rbp+arg_8]
0x1800a5824  call    cs:__imp_UMgrEnumerateSessionUsers
0x1800a582a  mov     ebx, eax
0x1800a582c  test    eax, eax
0x1800a582e  jns     short loc_1800A5841
0x1800a5830  lea     rax, aUmgrenumerates_0; "UMgrEnumerateSessionUsers failed."
0x1800a5837  mov     edx, 32Dh
0x1800a583c  jmp     loc_1800A5982
0x1800a5841  mov     ecx, [rbp+arg_8]
0x1800a5844  test    ecx, ecx
0x1800a5846  jz      loc_1800A5971
0x1800a584c  cmp     [rbp+arg_18], 0
0x1800a5851  jz      loc_1800A5971
0x1800a5857  mov     rax, [rdi+10h]
0x1800a585b  mov     r12, 1FFFFFFFFFFFFFFFh
0x1800a5865  sub     rax, [rdi]
0x1800a5868  sar     rax, 2
0x1800a586c  cmp     rcx, rax
0x1800a586f  jbe     short loc_1800A589D
0x1800a5871  shr     rax, 2
0x1800a5875  mov     edx, ecx
0x1800a5877  imul    rax, 7
0x1800a587b  add     rax, 8
0x1800a587f  cmp     rax, rcx
0x1800a5882  cmovnb  rdx, rax
0x1800a5886  cmp     rdx, r12
0x1800a5889  cmova   rdx, r12
0x1800a588d  cmp     rcx, rdx
0x1800a5890  ja      short loc_1800A589D
0x1800a5892  mov     rcx, rdi
0x1800a5895  call    ?_SetCapacity@?$vector@KV?$allocator@K@utl@@@utl@@AEAA_N_K@Z; utl::vector<ulong,utl::allocator<ulong>>::_SetCapacity(unsigned __int64)
0x1800a589a  mov     ecx, [rbp+arg_8]
0x1800a589d  xor     ebx, ebx
0x1800a589f  cmp     ebx, ecx
0x1800a58a1  jnb     loc_1800A596D
0x1800a58a7  mov     rax, [rbp+arg_18]
0x1800a58ab  mov     ecx, ebx
0x1800a58ad  add     rcx, rcx
0x1800a58b0  mov     esi, [rax+rcx*8+8]
0x1800a58b4  lea     rcx, [rbp+arg_10]
0x1800a58b8  mov     [rbp+var_10], esi
0x1800a58bb  mov     [rbp+arg_10], 0
0x1800a58c3  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x1800a58c8  mov     rdx, rax
0x1800a58cb  mov     ecx, esi
0x1800a58cd  call    cs:__imp_QueryUserToken
0x1800a58d3  test    eax, eax
0x1800a58d5  jnz     short loc_1800A58E4
0x1800a58d7  call    cs:__imp_GetLastError
0x1800a58dd  cmp     eax, 3F0h
0x1800a58e2  jz      short loc_1800A594A
0x1800a58e4  mov     rax, [rdi+8]
0x1800a58e8  mov     rcx, [rdi+10h]
0x1800a58ec  cmp     rax, rcx
0x1800a58ef  jz      short loc_1800A58F5
0x1800a58f1  mov     [rax], esi
0x1800a58f3  jmp     short loc_1800A5945
0x1800a58f5  mov     r14, [rdi]
0x1800a58f8  sub     rcx, r14
0x1800a58fb  sar     rcx, 2
0x1800a58ff  mov     rax, rcx
0x1800a5902  shr     rax, 2
0x1800a5906  imul    rdx, rax, 7
0x1800a590a  add     rdx, 8
0x1800a590e  cmp     rdx, r12
0x1800a5911  cmova   rdx, r12
0x1800a5915  cmp     rcx, rdx
0x1800a5918  jnb     short loc_1800A595D
0x1800a591a  mov     rcx, rdi
0x1800a591d  call    ?_SetCapacity@?$vector@KV?$allocator@K@utl@@@utl@@AEAA_N_K@Z; utl::vector<ulong,utl::allocator<ulong>>::_SetCapacity(unsigned __int64)
0x1800a5922  test    al, al
0x1800a5924  jz      short loc_1800A595D
0x1800a5926  mov     r8, [rdi+8]
0x1800a592a  lea     rcx, [rbp+var_10]
0x1800a592e  mov     rdx, [rdi]
0x1800a5931  mov     rax, r8
0x1800a5934  sub     rax, rdx
0x1800a5937  sub     rcx, r14
0x1800a593a  cmp     rcx, rax
0x1800a593d  jnb     short loc_1800A5942
0x1800a593f  mov     esi, [rcx+rdx]
0x1800a5942  mov     [r8], esi
0x1800a5945  add     qword ptr [rdi+8], 4
0x1800a594a  lea     rcx, [rbp+arg_10]
0x1800a594e  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800a5953  mov     ecx, [rbp+arg_8]
0x1800a5956  inc     ebx
0x1800a5958  jmp     loc_1800A589F
0x1800a595d  lea     rcx, [rbp+arg_10]
0x1800a5961  mov     ebx, 8007000Eh
0x1800a5966  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800a596b  jmp     short loc_1800A599A
0x1800a596d  xor     ebx, ebx
0x1800a596f  jmp     short loc_1800A599A
0x1800a5971  mov     ebx, 800703F0h
0x1800a5976  lea     rax, aNoSessionUsers; "No session users available."
0x1800a597d  mov     edx, 352h; void *
0x1800a5982  mov     rcx, [rbp+28h]; this
0x1800a5986  lea     r8, aOnecoreWindows_3; "onecore\\windows\\feedback\\core\\werco"...
0x1800a598d  mov     r9d, ebx; char *
0x1800a5990  mov     qword ptr [rsp+40h+var_20], rax; int
0x1800a5995  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800a599a  mov     rcx, [rbp+arg_18]
0x1800a599e  test    rcx, rcx
0x1800a59a1  jz      short loc_1800A59A9
0x1800a59a3  call    cs:__imp_UMgrFreeSessionUsers
0x1800a59a9  mov     eax, ebx
0x1800a59ab  mov     rbx, [rsp+40h+arg_0]
0x1800a59b0  add     rsp, 40h
0x1800a59b4  pop     r14
0x1800a59b6  pop     r12
0x1800a59b8  pop     rdi
0x1800a59b9  pop     rsi
0x1800a59ba  pop     rbp
0x1800a59bb  retn
```
