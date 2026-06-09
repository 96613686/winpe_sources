# GetUserSidFromToken(void *,wistd::unique_ptr<void,wil::function_deleter<void (*)(void *),&PrivMemFree(void *)>> *)

- ea: `0x180048efc`
- end: `0x1800491ce`
- name: `?GetUserSidFromToken@@YAJPEAXPEAV?$unique_ptr@XU?$function_deleter@P6AXPEAX@Z$1?PrivMemFree@@YAX0@Z@wil@@@wistd@@@Z`
- size: `722`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180016e7c`

## callees

- `0x1800031b8`
- `0x18000ce5c`
- `0x1800210f8`
- `0x180048efc`
- `0x18004a3f4`
- `0x180093f20`
- `0x1800b7ac0`
- `0x180112d00`
- `0x180114010`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x180048f4b`
- `ntdll!NtQueryInformationToken` at `0x18004900c`
- `ntdll!NtQueryInformationToken` at `0x180048f4b`
- `ntdll!NtQueryInformationToken` at `0x18004900c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049089`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049089`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004903d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004903d`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180049061`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180049061`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180049023`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180049023`

## string_xrefs

- `0x1800490b2`: `onecore\com\combase\processtoken\processtoken.cxx`
- `0x1800490d1`: `onecore\com\combase\processtoken\processtoken.cxx`
- `0x18004910e`: `onecore\com\combase\processtoken\processtoken.cxx`
- `0x180049160`: `onecore\com\combase\processtoken\processtoken.cxx`
- `0x180049199`: `onecore\com\combase\processtoken\processtoken.cxx`

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
0x180048efc  push    rbp
0x180048efe  push    rsi
0x180048eff  push    rdi
0x180048f00  push    r14
0x180048f02  push    r15
0x180048f04  sub     rsp, 60h
0x180048f08  lea     rbp, [rsp+30h]
0x180048f0d  mov     [rbp+50h+arg_10], rbx
0x180048f11  mov     rax, cs:__security_cookie
0x180048f18  xor     rax, rbp
0x180048f1b  mov     [rbp+50h+var_30], rax
0x180048f1f  xor     r9d, r9d; TokenInformationLength
0x180048f22  mov     [rbp+50h+TokenInformationLength], 0
0x180048f29  mov     r14, rdx
0x180048f2c  lea     rax, [rbp+50h+TokenInformationLength]
0x180048f30  xorps   xmm0, xmm0
0x180048f33  mov     [rsp+80h+ReturnLength], rax; int
0x180048f38  lea     r8, [rbp+50h+var_39]
0x180048f3c  mov     rsi, rcx
0x180048f3f  lea     edx, [r9+1]; TokenInformationClass
0x180048f43  and     r8, 0FFFFFFFFFFFFFFF8h; TokenInformation
0x180048f47  movups  xmmword ptr [rbp+10h], xmm0
0x180048f4b  call    cs:__imp_NtQueryInformationToken
0x180048f52  nop     dword ptr [rax+rax+00h]
0x180048f57  cmp     eax, 0C0000023h
0x180048f5c  jnz     loc_18004910A
0x180048f62  mov     ebx, [rbp+50h+TokenInformationLength]
0x180048f65  xor     edi, edi
0x180048f67  mov     r15d, 70616548h
0x180048f6d  test    rbx, rbx
0x180048f70  jz      loc_18004912B
0x180048f76  cmp     rbx, cs:g_ulMaxStackAllocSize
0x180048f7d  ja      loc_18004912B
0x180048f83  mov     rcx, cs:g_ulAdditionalProbeSize
0x180048f8a  add     rcx, 8
0x180048f8e  add     rcx, rbx
0x180048f91  cmp     rcx, rbx
0x180048f94  jb      loc_18004912B
0x180048f9a  call    VerifyStackAvailable
0x180048f9f  test    eax, eax
0x180048fa1  jz      loc_18004912B
0x180048fa7  lea     rax, [rbx+8]
0x180048fab  lea     rcx, [rax+0Fh]
0x180048faf  cmp     rcx, rax
0x180048fb2  ja      short loc_180048FBE
0x180048fb4  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180048fbe  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180048fc2  mov     rax, rcx
0x180048fc5  call    _alloca_probe
0x180048fca  sub     rsp, rcx
0x180048fcd  lea     rdi, [rsp+80h+TokenInformationLength]
0x180048fd2  test    rdi, rdi
0x180048fd5  jz      loc_18004912B
0x180048fdb  mov     dword ptr [rdi], 6B637453h
0x180048fe1  add     rdi, 8
0x180048fe5  jz      loc_18004912B
0x180048feb  test    rdi, rdi
0x180048fee  jz      loc_1800490CD
0x180048ff4  mov     r9d, [rbp+50h+TokenInformationLength]; TokenInformationLength
0x180048ff8  lea     rax, [rbp+50h+TokenInformationLength]
0x180048ffc  mov     r8, rdi; TokenInformation
0x180048fff  mov     [rsp+80h+ReturnLength], rax; int
0x180049004  mov     edx, 1; TokenInformationClass
0x180049009  mov     rcx, rsi; TokenHandle
0x18004900c  call    cs:__imp_NtQueryInformationToken
0x180049013  nop     dword ptr [rax+rax+00h]
0x180049018  test    eax, eax
0x18004901a  js      loc_1800490AE
0x180049020  mov     rcx, [rdi]; pSid
0x180049023  call    cs:__imp_GetLengthSid
0x18004902a  nop     dword ptr [rax+rax+00h]
0x18004902f  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180049036  xor     edx, edx; dwFlags
0x180049038  mov     r8d, eax; dwBytes
0x18004903b  mov     esi, eax
0x18004903d  call    cs:__imp_HeapAlloc
0x180049044  nop     dword ptr [rax+rax+00h]
0x180049049  mov     [rbp+50h+var_48], rax
0x18004904d  mov     rbx, rax
0x180049050  test    rax, rax
0x180049053  jz      loc_180049195
0x180049059  mov     r8, [rdi]; pSourceSid
0x18004905c  mov     rdx, rax; pDestinationSid
0x18004905f  mov     ecx, esi; nDestinationSidLength
0x180049061  call    cs:__imp_CopySid
0x180049068  nop     dword ptr [rax+rax+00h]
0x18004906d  test    eax, eax
0x18004906f  jz      loc_18004915C
0x180049075  mov     r8, [r14]; lpMem
0x180049078  mov     [r14], rbx
0x18004907b  test    r8, r8
0x18004907e  jz      short loc_180049095
0x180049080  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180049087  xor     edx, edx; dwFlags
0x180049089  call    cs:__imp_HeapFree
0x180049090  nop     dword ptr [rax+rax+00h]
0x180049095  lea     rcx, [rdi-8]
0x180049099  cmp     [rcx], r15d
0x18004909c  jnz     short loc_1800490AA
0x18004909e  mov     rax, cs:g_pfnFree
0x1800490a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800490aa  xor     eax, eax
0x1800490ac  jmp     short loc_1800490ED
0x1800490ae  mov     rcx, [rbp+58h]; this
0x1800490b2  lea     r8, aOnecoreComComb_112; "onecore\\com\\combase\\processtoken\\pr"...
0x1800490b9  mov     r9d, eax; char *
0x1800490bc  mov     edx, 2CBh; void *
0x1800490c1  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800490c6  mov     ebx, eax
0x1800490c8  jmp     loc_18004917E
0x1800490cd  mov     rcx, [rbp+58h]; this
0x1800490d1  lea     r8, aOnecoreComComb_112; "onecore\\com\\combase\\processtoken\\pr"...
0x1800490d8  mov     r9d, 8007000Eh; char *
0x1800490de  mov     edx, 2C5h; void *
0x1800490e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800490e8  mov     eax, 8007000Eh
0x1800490ed  mov     rcx, [rbp+50h+var_30]
0x1800490f1  xor     rcx, rbp; StackCookie
0x1800490f4  call    __security_check_cookie
0x1800490f9  mov     rbx, [rbp+50h+arg_10]
0x1800490fd  lea     rsp, [rbp+30h]
0x180049101  pop     r15
0x180049103  pop     r14
0x180049105  pop     rdi
0x180049106  pop     rsi
0x180049107  pop     rbp
0x180049108  retn
0x18004910a  mov     rcx, [rbp+58h]; this
0x18004910e  lea     r8, aOnecoreComComb_112; "onecore\\com\\combase\\processtoken\\pr"...
0x180049115  mov     ebx, 8000FFFFh
0x18004911a  mov     edx, 2C1h; void *
0x18004911f  mov     r9d, ebx; char *
0x180049122  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049127  mov     eax, ebx
0x180049129  jmp     short loc_1800490ED
0x18004912b  lea     rcx, [rbx+8]
0x18004912f  cmp     rcx, rbx
0x180049132  jb      loc_180048FEB
0x180049138  mov     rax, cs:g_pfnAllocate
0x18004913f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049144  mov     rdi, rax
0x180049147  test    rax, rax
0x18004914a  jz      loc_180048FEB
0x180049150  mov     [rax], r15d
0x180049153  add     rdi, 8
0x180049157  jmp     loc_180048FEB
0x18004915c  mov     rcx, [rbp+58h]; this
0x180049160  lea     r8, aOnecoreComComb_112; "onecore\\com\\combase\\processtoken\\pr"...
0x180049167  mov     edx, 2D2h; void *
0x18004916c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180049171  xor     edx, edx
0x180049173  lea     rcx, [rbp+50h+var_48]
0x180049177  mov     ebx, eax
0x180049179  call    ?reset@?$unique_ptr@XU?$function_deleter@P6AXPEAX@Z$1?PrivMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAX@Z; wistd::unique_ptr<void,wil::function_deleter<void (*)(void *),&PrivMemFree(void *)>>::reset(void *)
0x18004917e  lea     rcx, [rdi-8]
0x180049182  cmp     [rcx], r15d
0x180049185  jnz     short loc_180049127
0x180049187  mov     rax, cs:g_pfnFree
0x18004918e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049193  jmp     short loc_180049127
0x180049195  mov     rcx, [rbp+58h]; this
0x180049199  lea     r8, aOnecoreComComb_112; "onecore\\com\\combase\\processtoken\\pr"...
0x1800491a0  mov     r9d, 8007000Eh; char *
0x1800491a6  mov     edx, 2D0h; void *
0x1800491ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800491b0  lea     rcx, [rdi-8]
0x1800491b4  cmp     [rcx], r15d
0x1800491b7  jnz     loc_1800490E8
0x1800491bd  mov     rax, cs:g_pfnFree
0x1800491c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800491c9  jmp     loc_1800490E8
```
