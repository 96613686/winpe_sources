# GetTokenInfo(void *,_TOKEN_USER * *)

- ea: `0x18000e2e0`
- end: `0x18000e39b`
- name: `?GetTokenInfo@@YAJPEAXPEAPEAU_TOKEN_USER@@@Z`
- size: `187`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, struct _TOKEN_USER **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000e3a4`

## callees

- `0x18000bd04`
- `0x18000bd44`
- `0x18000e2e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e31d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e373`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e31d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e373`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e313`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e35a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e313`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e35a`

## pseudocode

```c
signed int __fastcall GetTokenInfo(HANDLE TokenHandle, struct _TOKEN_USER **a2)
{
  struct _TOKEN_USER *v4; // rax
  signed int result; // eax
  DWORD TokenInformationLength; // [rsp+50h] [rbp+18h] BYREF
  DWORD ReturnLength; // [rsp+58h] [rbp+20h] BYREF

  TokenInformationLength = 0;
  ReturnLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
    return -2147024809;
  if ( GetLastError() == 122 )
  {
    v4 = (struct _TOKEN_USER *)operator new(TokenInformationLength);
    *a2 = v4;
    if ( !v4 )
      return -2147024882;
    if ( GetTokenInformation(TokenHandle, TokenUser, v4, TokenInformationLength, &ReturnLength) )
      return 0;
    operator delete(*a2);
    *a2 = 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000e2e0  mov     rax, rsp
0x18000e2e3  mov     [rax+8], rbx
0x18000e2e7  push    rdi
0x18000e2e8  sub     rsp, 30h
0x18000e2ec  xor     r9d, r9d; TokenInformationLength
0x18000e2ef  mov     dword ptr [rax+18h], 0
0x18000e2f6  mov     dword ptr [rax+20h], 0
0x18000e2fd  lea     rax, [rax+18h]
0x18000e301  mov     rbx, rdx
0x18000e304  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18000e309  xor     r8d, r8d; TokenInformation
0x18000e30c  mov     rdi, rcx
0x18000e30f  lea     edx, [r9+1]; TokenInformationClass
0x18000e313  call    cs:__imp_GetTokenInformation
0x18000e319  test    eax, eax
0x18000e31b  jnz     short loc_18000E38B
0x18000e31d  call    cs:__imp_GetLastError
0x18000e323  cmp     eax, 7Ah ; 'z'
0x18000e326  jnz     short loc_18000E373
0x18000e328  mov     ecx, [rsp+38h+TokenInformationLength]; Size
0x18000e32c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e331  mov     [rbx], rax
0x18000e334  test    rax, rax
0x18000e337  jnz     short loc_18000E340
0x18000e339  mov     eax, 8007000Eh
0x18000e33e  jmp     short loc_18000E390
0x18000e340  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18000e345  lea     rcx, [rsp+38h+arg_18]
0x18000e34a  mov     [rsp+38h+ReturnLength], rcx; ReturnLength
0x18000e34f  mov     r8, rax; TokenInformation
0x18000e352  mov     rcx, rdi; TokenHandle
0x18000e355  mov     edx, 1; TokenInformationClass
0x18000e35a  call    cs:__imp_GetTokenInformation
0x18000e360  test    eax, eax
0x18000e362  jnz     short loc_18000E387
0x18000e364  mov     rcx, [rbx]; Block
0x18000e367  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e36c  mov     qword ptr [rbx], 0
0x18000e373  call    cs:__imp_GetLastError
0x18000e379  test    eax, eax
0x18000e37b  jle     short loc_18000E390
0x18000e37d  movzx   eax, ax
0x18000e380  or      eax, 80070000h
0x18000e385  jmp     short loc_18000E390
0x18000e387  xor     eax, eax
0x18000e389  jmp     short loc_18000E390
0x18000e38b  mov     eax, 80070057h
0x18000e390  mov     rbx, [rsp+38h+arg_0]
0x18000e395  add     rsp, 30h
0x18000e399  pop     rdi
0x18000e39a  retn
```
