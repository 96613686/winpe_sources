# GetUserSidFromToken(void *,wistd::unique_ptr<void,wil::function_deleter<void (*)(void *),&PrivMemFree(void *)>> *)

- ea: `0x18003f4ac`
- end: `0x18003f755`
- name: `?GetUserSidFromToken@@YAJPEAXPEAV?$unique_ptr@XU?$function_deleter@P6AXPEAX@Z$1?PrivMemFree@@YAX0@Z@wil@@@wistd@@@Z`
- size: `681`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180012dd0`

## callees

- `0x180003088`
- `0x18001ec28`
- `0x18002ba28`
- `0x18003f4ac`
- `0x180040918`
- `0x18008cd90`
- `0x1800b27e0`
- `0x18010a000`
- `0x18010b010`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18003f4fb`
- `ntdll!NtQueryInformationToken` at `0x18003f5b6`
- `ntdll!NtQueryInformationToken` at `0x18003f4fb`
- `ntdll!NtQueryInformationToken` at `0x18003f5b6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003f617`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003f617`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003f5d7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003f5d7`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18003f5f5`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18003f5f5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003f5c3`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003f5c3`

## string_xrefs

- `0x18003f63a`: `onecore\com\combase\processtoken\processtoken.cxx`
- `0x18003f659`: `onecore\com\combase\processtoken\processtoken.cxx`
- `0x18003f695`: `onecore\com\combase\processtoken\processtoken.cxx`
- `0x18003f6e7`: `onecore\com\combase\processtoken\processtoken.cxx`
- `0x18003f720`: `onecore\com\combase\processtoken\processtoken.cxx`

## pseudocode

```c
__int64 __fastcall GetUserSidFromToken(HANDLE TokenHandle, void **a2)
{
  __int64 v4; // rdx
  unsigned __int64 v5; // rbx
  ULONG *p_TokenInformationLength; // rdi
  unsigned __int64 v7; // rcx
  __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  void *v10; // rsp
  void *v11; // rsp
  NTSTATUS v12; // eax
  SIZE_T LengthSid; // rsi
  void *v14; // rax
  void *v15; // rbx
  const char *v16; // r9
  void *v17; // r8
  unsigned int LastError; // ebx
  ULONG *v20; // rax
  __int64 v21; // [rsp+0h] [rbp-30h] BYREF
  PULONG ReturnLength; // [rsp+20h] [rbp-10h]
  ULONG TokenInformationLength; // [rsp+30h] [rbp+0h] BYREF
  void *v24; // [rsp+38h] [rbp+8h] BYREF
  __int128 v25; // [rsp+40h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+58h]

  TokenInformationLength = 0;
  v25 = 0;
  if ( NtQueryInformationToken(TokenHandle, TokenUser, &v25, 0, &TokenInformationLength) != -1073741789 )
  {
    LastError = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C1,
      (unsigned int)"onecore\\com\\combase\\processtoken\\processtoken.cxx",
      (const char *)0x8000FFFFLL,
      (int)ReturnLength);
    return LastError;
  }
  v5 = TokenInformationLength;
  p_TokenInformationLength = 0;
  if ( !TokenInformationLength )
    goto LABEL_34;
  if ( TokenInformationLength > (unsigned __int64)g_ulMaxStackAllocSize )
    goto LABEL_34;
  v7 = TokenInformationLength + g_ulAdditionalProbeSize + 8;
  if ( v7 < TokenInformationLength || !(unsigned int)VerifyStackAvailable(v7, v4) )
    goto LABEL_34;
  v8 = v5 + 23;
  if ( v5 + 23 <= v5 + 8 )
    v8 = 0xFFFFFFFFFFFFFF0LL;
  v9 = v8 & 0xFFFFFFFFFFFFFFF0uLL;
  v10 = alloca(v9);
  v11 = alloca(v9);
  p_TokenInformationLength = &TokenInformationLength;
  if ( &v21 == (__int64 *)-48LL
    || (TokenInformationLength = 1801679955, (p_TokenInformationLength = (ULONG *)&v24) == 0) )
  {
LABEL_34:
    if ( v5 + 8 >= v5 )
    {
      v20 = (ULONG *)((__int64 (*)(void))g_pfnAllocate)();
      p_TokenInformationLength = v20;
      if ( v20 )
      {
        *v20 = 1885431112;
        p_TokenInformationLength = v20 + 2;
      }
    }
  }
  if ( !p_TokenInformationLength )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C5,
      (unsigned int)"onecore\\com\\combase\\processtoken\\processtoken.cxx",
      (const char *)0x8007000ELL,
      (int)ReturnLength);
    return 2147942414LL;
  }
  v12 = NtQueryInformationToken(
          TokenHandle,
          TokenUser,
          p_TokenInformationLength,
          TokenInformationLength,
          &TokenInformationLength);
  if ( v12 < 0 )
  {
    LastError = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x2CB,
                  (unsigned int)"onecore\\com\\combase\\processtoken\\processtoken.cxx",
                  (const char *)(unsigned int)v12,
                  (int)ReturnLength);
    goto LABEL_28;
  }
  LengthSid = GetLengthSid(*(PSID *)p_TokenInformationLength);
  v14 = HeapAlloc(g_hHeap, 0, LengthSid);
  v24 = v14;
  v15 = v14;
  if ( !v14 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D0,
      (unsigned int)"onecore\\com\\combase\\processtoken\\processtoken.cxx",
      (const char *)0x8007000ELL,
      (int)ReturnLength);
    if ( *(p_TokenInformationLength - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
    return 2147942414LL;
  }
  if ( !CopySid(LengthSid, v14, *(PSID *)p_TokenInformationLength) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x2D2,
                  (unsigned int)"onecore\\com\\combase\\processtoken\\processtoken.cxx",
                  v16);
    wistd::unique_ptr<void,wil::function_deleter<void (*)(void *),&void PrivMemFree(void *)>>::reset(&v24, 0);
LABEL_28:
    if ( *(p_TokenInformationLength - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
    return LastError;
  }
  v17 = *a2;
  *a2 = v15;
  if ( v17 )
    HeapFree(g_hHeap, 0, v17);
  if ( *(p_TokenInformationLength - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  return 0;
}

```

## disassembly

```asm
0x18003f4ac  push    rbp
0x18003f4ae  push    rsi
0x18003f4af  push    rdi
0x18003f4b0  push    r14
0x18003f4b2  push    r15
0x18003f4b4  sub     rsp, 60h
0x18003f4b8  lea     rbp, [rsp+30h]
0x18003f4bd  mov     [rbp+50h+arg_10], rbx
0x18003f4c1  mov     rax, cs:__security_cookie
0x18003f4c8  xor     rax, rbp
0x18003f4cb  mov     [rbp+50h+var_30], rax
0x18003f4cf  xor     r9d, r9d; TokenInformationLength
0x18003f4d2  mov     [rbp+50h+TokenInformationLength], 0
0x18003f4d9  mov     r14, rdx
0x18003f4dc  lea     rax, [rbp+50h+TokenInformationLength]
0x18003f4e0  xorps   xmm0, xmm0
0x18003f4e3  mov     [rsp+80h+ReturnLength], rax; int
0x18003f4e8  lea     r8, [rbp+50h+var_39]
0x18003f4ec  mov     rsi, rcx
0x18003f4ef  lea     edx, [r9+1]; TokenInformationClass
0x18003f4f3  and     r8, 0FFFFFFFFFFFFFFF8h; TokenInformation
0x18003f4f7  movups  xmmword ptr [rbp+10h], xmm0
0x18003f4fb  call    cs:__imp_NtQueryInformationToken
0x18003f501  cmp     eax, 0C0000023h
0x18003f506  jnz     loc_18003F691
0x18003f50c  mov     ebx, [rbp+50h+TokenInformationLength]
0x18003f50f  xor     edi, edi
0x18003f511  mov     r15d, 70616548h
0x18003f517  test    rbx, rbx
0x18003f51a  jz      loc_18003F6B2
0x18003f520  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18003f527  ja      loc_18003F6B2
0x18003f52d  mov     rcx, cs:g_ulAdditionalProbeSize
0x18003f534  add     rcx, 8
0x18003f538  add     rcx, rbx
0x18003f53b  cmp     rcx, rbx
0x18003f53e  jb      loc_18003F6B2
0x18003f544  call    VerifyStackAvailable
0x18003f549  test    eax, eax
0x18003f54b  jz      loc_18003F6B2
0x18003f551  lea     rax, [rbx+8]
0x18003f555  lea     rcx, [rax+0Fh]
0x18003f559  cmp     rcx, rax
0x18003f55c  ja      short loc_18003F568
0x18003f55e  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18003f568  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18003f56c  mov     rax, rcx
0x18003f56f  call    _alloca_probe
0x18003f574  sub     rsp, rcx
0x18003f577  lea     rdi, [rsp+80h+TokenInformationLength]
0x18003f57c  test    rdi, rdi
0x18003f57f  jz      loc_18003F6B2
0x18003f585  mov     dword ptr [rdi], 6B637453h
0x18003f58b  add     rdi, 8
0x18003f58f  jz      loc_18003F6B2
0x18003f595  test    rdi, rdi
0x18003f598  jz      loc_18003F655
0x18003f59e  mov     r9d, [rbp+50h+TokenInformationLength]; TokenInformationLength
0x18003f5a2  lea     rax, [rbp+50h+TokenInformationLength]
0x18003f5a6  mov     r8, rdi; TokenInformation
0x18003f5a9  mov     [rsp+80h+ReturnLength], rax; int
0x18003f5ae  mov     edx, 1; TokenInformationClass
0x18003f5b3  mov     rcx, rsi; TokenHandle
0x18003f5b6  call    cs:__imp_NtQueryInformationToken
0x18003f5bc  test    eax, eax
0x18003f5be  js      short loc_18003F636
0x18003f5c0  mov     rcx, [rdi]; pSid
0x18003f5c3  call    cs:__imp_GetLengthSid
0x18003f5c9  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18003f5d0  xor     edx, edx; dwFlags
0x18003f5d2  mov     r8d, eax; dwBytes
0x18003f5d5  mov     esi, eax
0x18003f5d7  call    cs:__imp_HeapAlloc
0x18003f5dd  mov     [rbp+50h+var_48], rax
0x18003f5e1  mov     rbx, rax
0x18003f5e4  test    rax, rax
0x18003f5e7  jz      loc_18003F71C
0x18003f5ed  mov     r8, [rdi]; pSourceSid
0x18003f5f0  mov     rdx, rax; pDestinationSid
0x18003f5f3  mov     ecx, esi; nDestinationSidLength
0x18003f5f5  call    cs:__imp_CopySid
0x18003f5fb  test    eax, eax
0x18003f5fd  jz      loc_18003F6E3
0x18003f603  mov     r8, [r14]; lpMem
0x18003f606  mov     [r14], rbx
0x18003f609  test    r8, r8
0x18003f60c  jz      short loc_18003F61D
0x18003f60e  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18003f615  xor     edx, edx; dwFlags
0x18003f617  call    cs:__imp_HeapFree
0x18003f61d  lea     rcx, [rdi-8]
0x18003f621  cmp     [rcx], r15d
0x18003f624  jnz     short loc_18003F632
0x18003f626  mov     rax, cs:g_pfnFree
0x18003f62d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f632  xor     eax, eax
0x18003f634  jmp     short loc_18003F675
0x18003f636  mov     rcx, [rbp+58h]; this
0x18003f63a  lea     r8, aOnecoreComComb_112; "onecore\\com\\combase\\processtoken\\pr"...
0x18003f641  mov     r9d, eax; char *
0x18003f644  mov     edx, 2CBh; void *
0x18003f649  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18003f64e  mov     ebx, eax
0x18003f650  jmp     loc_18003F705
0x18003f655  mov     rcx, [rbp+58h]; this
0x18003f659  lea     r8, aOnecoreComComb_112; "onecore\\com\\combase\\processtoken\\pr"...
0x18003f660  mov     r9d, 8007000Eh; char *
0x18003f666  mov     edx, 2C5h; void *
0x18003f66b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f670  mov     eax, 8007000Eh
0x18003f675  mov     rcx, [rbp+50h+var_30]
0x18003f679  xor     rcx, rbp; StackCookie
0x18003f67c  call    __security_check_cookie
0x18003f681  mov     rbx, [rbp+50h+arg_10]
0x18003f685  lea     rsp, [rbp+30h]
0x18003f689  pop     r15
0x18003f68b  pop     r14
0x18003f68d  pop     rdi
0x18003f68e  pop     rsi
0x18003f68f  pop     rbp
0x18003f690  retn
0x18003f691  mov     rcx, [rbp+58h]; this
0x18003f695  lea     r8, aOnecoreComComb_112; "onecore\\com\\combase\\processtoken\\pr"...
0x18003f69c  mov     ebx, 8000FFFFh
0x18003f6a1  mov     edx, 2C1h; void *
0x18003f6a6  mov     r9d, ebx; char *
0x18003f6a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f6ae  mov     eax, ebx
0x18003f6b0  jmp     short loc_18003F675
0x18003f6b2  lea     rcx, [rbx+8]
0x18003f6b6  cmp     rcx, rbx
0x18003f6b9  jb      loc_18003F595
0x18003f6bf  mov     rax, cs:g_pfnAllocate
0x18003f6c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f6cb  mov     rdi, rax
0x18003f6ce  test    rax, rax
0x18003f6d1  jz      loc_18003F595
0x18003f6d7  mov     [rax], r15d
0x18003f6da  add     rdi, 8
0x18003f6de  jmp     loc_18003F595
0x18003f6e3  mov     rcx, [rbp+58h]; this
0x18003f6e7  lea     r8, aOnecoreComComb_112; "onecore\\com\\combase\\processtoken\\pr"...
0x18003f6ee  mov     edx, 2D2h; void *
0x18003f6f3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003f6f8  xor     edx, edx
0x18003f6fa  lea     rcx, [rbp+50h+var_48]
0x18003f6fe  mov     ebx, eax
0x18003f700  call    ?reset@?$unique_ptr@XU?$function_deleter@P6AXPEAX@Z$1?PrivMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAX@Z; wistd::unique_ptr<void,wil::function_deleter<void (*)(void *),&PrivMemFree(void *)>>::reset(void *)
0x18003f705  lea     rcx, [rdi-8]
0x18003f709  cmp     [rcx], r15d
0x18003f70c  jnz     short loc_18003F6AE
0x18003f70e  mov     rax, cs:g_pfnFree
0x18003f715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f71a  jmp     short loc_18003F6AE
0x18003f71c  mov     rcx, [rbp+58h]; this
0x18003f720  lea     r8, aOnecoreComComb_112; "onecore\\com\\combase\\processtoken\\pr"...
0x18003f727  mov     r9d, 8007000Eh; char *
0x18003f72d  mov     edx, 2D0h; void *
0x18003f732  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f737  lea     rcx, [rdi-8]
0x18003f73b  cmp     [rcx], r15d
0x18003f73e  jnz     loc_18003F670
0x18003f744  mov     rax, cs:g_pfnFree
0x18003f74b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f750  jmp     loc_18003F670
```
