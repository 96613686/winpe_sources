# CallerIdentity::GetImpersonationTokenFromProcess(void *,ulong,void * *)

- ea: `0x180046070`
- end: `0x1800460f5`
- name: `?GetImpersonationTokenFromProcess@CallerIdentity@@YAJPEAXKPEAPEAX@Z`
- size: `133`
- prototype: `int(CallerIdentity *__hidden this, void *, unsigned int, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180045f88`

## callees

- `0x18000b3c0`
- `0x180017714`
- `0x180046070`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180046097`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180046097`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800460c8`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800460c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CallerIdentity::GetImpersonationTokenFromProcess(
        CallerIdentity *this,
        void *a2,
        void **a3,
        void **a4)
{
  int Error; // ebx
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  *a3 = 0;
  TokenHandle = 0;
  if ( OpenProcessToken(this, 0xEu, &TokenHandle) || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    if ( DuplicateTokenEx(TokenHandle, 0xCu, 0, SecurityImpersonation, TokenImpersonation, a3) )
      Error = 0;
    else
      Error = ResultFromKnownLastError();
  }
  CAutoHandle<void *>::~CAutoHandle<void *>(&TokenHandle);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180046070  mov     [rsp+arg_0], rbx
0x180046075  push    rdi
0x180046076  sub     rsp, 30h
0x18004607a  mov     rdi, r8
0x18004607d  mov     qword ptr [r8], 0
0x180046084  mov     [rsp+38h+TokenHandle], 0
0x18004608d  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x180046092  mov     edx, 0Eh; DesiredAccess
0x180046097  call    cs:__imp_OpenProcessToken
0x18004609d  test    eax, eax
0x18004609f  jnz     short loc_1800460AC
0x1800460a1  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800460a6  mov     ebx, eax
0x1800460a8  test    eax, eax
0x1800460aa  js      short loc_1800460DD
0x1800460ac  mov     [rsp+38h+phNewToken], rdi; phNewToken
0x1800460b1  mov     r9d, 2; ImpersonationLevel
0x1800460b7  mov     [rsp+38h+TokenType], r9d; TokenType
0x1800460bc  xor     r8d, r8d; lpTokenAttributes
0x1800460bf  lea     edx, [r9+0Ah]; dwDesiredAccess
0x1800460c3  mov     rcx, [rsp+38h+TokenHandle]; hExistingToken
0x1800460c8  call    cs:__imp_DuplicateTokenEx
0x1800460ce  test    eax, eax
0x1800460d0  jz      short loc_1800460D6
0x1800460d2  xor     ebx, ebx
0x1800460d4  jmp     short loc_1800460DD
0x1800460d6  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800460db  mov     ebx, eax
0x1800460dd  lea     rcx, [rsp+38h+TokenHandle]
0x1800460e2  call    ??1?$CAutoHandle@PEAX@@QEAA@XZ; CAutoHandle<void *>::~CAutoHandle<void *>(void)
0x1800460e7  nop
0x1800460e8  mov     eax, ebx
0x1800460ea  mov     rbx, [rsp+38h+arg_0]
0x1800460ef  add     rsp, 30h
0x1800460f3  pop     rdi
0x1800460f4  retn
```
