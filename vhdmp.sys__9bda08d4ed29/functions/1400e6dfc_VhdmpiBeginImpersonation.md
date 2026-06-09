# VhdmpiBeginImpersonation

- ea: `0x1400e6dfc`
- end: `0x1400e6f02`
- name: `VhdmpiBeginImpersonation`
- size: `262`
- prototype: `__int64 __fastcall(PACCESS_TOKEN Token, __int64)`
- caller_count: `11`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002ea1c`
- `0x14004c81c`
- `0x14004d6f8`
- `0x14004e088`
- `0x1400abb54`
- `0x1400abcbc`
- `0x1400ad410`
- `0x1400ae6a0`
- `0x1400ea774`
- `0x1400eaed8`
- `0x1400ed530`

## callees

- `0x140023980`
- `0x140036284`
- `0x1400e6dfc`

## import_xrefs

- `ntoskrnl!PsImpersonateClient` at `0x1400e6e75`
- `ntoskrnl!PsImpersonateClient` at `0x1400e6e75`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x1400e6edc`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x1400e6edc`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x1400e6e4f`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x1400e6e4f`
- `ntoskrnl!SeTokenType` at `0x1400e6e11`
- `ntoskrnl!SeTokenType` at `0x1400e6e11`
- `ntoskrnl!SeTokenImpersonationLevel` at `0x1400e6e25`
- `ntoskrnl!SeTokenImpersonationLevel` at `0x1400e6e25`

## string_xrefs

- `0x1400e6ec1`: `VhdmpiBeginImpersonation`
- `0x1400e6eb3`: `Failed to impersonate client 0x%08x`

## pseudocode

```c
__int64 __fastcall VhdmpiBeginImpersonation(PACCESS_TOKEN Token, __int64 a2)
{
  SECURITY_IMPERSONATION_LEVEL ImpersonationLevel; // esi
  NTSTATUS v5; // ebx
  int v6; // edx
  void *v7; // rcx

  if ( SeTokenType(Token) == TokenImpersonation )
    ImpersonationLevel = (unsigned int)SeTokenImpersonationLevel(Token);
  else
    ImpersonationLevel = SecurityImpersonation;
  *(_QWORD *)(a2 + 8) = PsReferenceImpersonationToken(
                          KeGetCurrentThread(),
                          (PBOOLEAN)(a2 + 1),
                          (PBOOLEAN)(a2 + 2),
                          (PSECURITY_IMPERSONATION_LEVEL)(a2 + 4));
  v5 = PsImpersonateClient(KeGetCurrentThread(), Token, 0, 0, ImpersonationLevel);
  if ( v5 >= 0 )
  {
    *(_BYTE *)a2 = 1;
    return 0;
  }
  else
  {
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 2048) )
      TraceEvents((int)"VhdmpiBeginImpersonation", 6391, 2, v6, "Failed to impersonate client 0x%08x", v5);
    v7 = *(void **)(a2 + 8);
    if ( v7 )
      PsDereferenceImpersonationToken(v7);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400e6dfc  mov     [rsp+arg_0], rbx
0x1400e6e01  mov     [rsp+arg_8], rsi
0x1400e6e06  push    rdi
0x1400e6e07  sub     rsp, 30h
0x1400e6e0b  mov     rdi, rdx
0x1400e6e0e  mov     rbx, rcx
0x1400e6e11  call    cs:__imp_SeTokenType
0x1400e6e18  nop     dword ptr [rax+rax+00h]
0x1400e6e1d  cmp     eax, 2
0x1400e6e20  jnz     short loc_1400E6E35
0x1400e6e22  mov     rcx, rbx
0x1400e6e25  call    cs:__imp_SeTokenImpersonationLevel
0x1400e6e2c  nop     dword ptr [rax+rax+00h]
0x1400e6e31  mov     esi, eax
0x1400e6e33  jmp     short loc_1400E6E3A
0x1400e6e35  mov     esi, 2
0x1400e6e3a  mov     rcx, gs:188h; Thread
0x1400e6e43  lea     r9, [rdi+4]; ImpersonationLevel
0x1400e6e47  lea     r8, [rdi+2]; EffectiveOnly
0x1400e6e4b  lea     rdx, [rdi+1]; CopyOnOpen
0x1400e6e4f  call    cs:__imp_PsReferenceImpersonationToken
0x1400e6e56  nop     dword ptr [rax+rax+00h]
0x1400e6e5b  xor     r9d, r9d; EffectiveOnly
0x1400e6e5e  mov     [rsp+38h+ImpersonationLevel], esi; ImpersonationLevel
0x1400e6e62  mov     [rdi+8], rax
0x1400e6e66  xor     r8d, r8d; CopyOnOpen
0x1400e6e69  mov     rcx, gs:188h; Thread
0x1400e6e72  mov     rdx, rbx; Token
0x1400e6e75  call    cs:__imp_PsImpersonateClient
0x1400e6e7c  nop     dword ptr [rax+rax+00h]
0x1400e6e81  mov     ebx, eax
0x1400e6e83  test    eax, eax
0x1400e6e85  jns     short loc_1400E6EEA
0x1400e6e87  mov     eax, cs:dword_1400876D0
0x1400e6e8d  cmp     eax, 2
0x1400e6e90  jbe     short loc_1400E6ED3
0x1400e6e92  mov     edx, 800h
0x1400e6e97  lea     rcx, dword_1400876D0
0x1400e6e9e  call    _tlgKeywordOn
0x1400e6ea3  test    al, al
0x1400e6ea5  jz      short loc_1400E6ED3
0x1400e6ea7  mov     ecx, 18F7h
0x1400e6eac  mov     dword ptr [rsp+38h+var_10], ebx; char
0x1400e6eb0  mov     r9d, edx; int
0x1400e6eb3  lea     rax, aFailedToImpers; "Failed to impersonate client 0x%08x"
0x1400e6eba  mov     edx, ecx; int
0x1400e6ebc  mov     qword ptr [rsp+38h+ImpersonationLevel], rax; char *
0x1400e6ec1  lea     rcx, aVhdmpibeginimp; "VhdmpiBeginImpersonation"
0x1400e6ec8  mov     r8d, 2; int
0x1400e6ece  call    TraceEvents
0x1400e6ed3  mov     rcx, [rdi+8]; ImpersonationToken
0x1400e6ed7  test    rcx, rcx
0x1400e6eda  jz      short loc_1400E6EEF
0x1400e6edc  call    cs:__imp_PsDereferenceImpersonationToken
0x1400e6ee3  nop     dword ptr [rax+rax+00h]
0x1400e6ee8  jmp     short loc_1400E6EEF
0x1400e6eea  mov     byte ptr [rdi], 1
0x1400e6eed  xor     ebx, ebx
0x1400e6eef  mov     rsi, [rsp+38h+arg_8]
0x1400e6ef4  mov     eax, ebx
0x1400e6ef6  mov     rbx, [rsp+38h+arg_0]
0x1400e6efb  add     rsp, 30h
0x1400e6eff  pop     rdi
0x1400e6f00  retn
```
