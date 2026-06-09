# VhdmpiBeginImpersonation

- ea: `0x1400e6e6c`
- end: `0x1400e6f72`
- name: `VhdmpiBeginImpersonation`
- size: `262`
- prototype: `__int64 __fastcall(PACCESS_TOKEN Token)`
- caller_count: `11`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002e55c`
- `0x14004c42c`
- `0x14004d308`
- `0x14004dc98`
- `0x1400abb54`
- `0x1400abcbc`
- `0x1400ad410`
- `0x1400ae6a0`
- `0x1400ea7e4`
- `0x1400eaf48`
- `0x1400ed5a0`

## callees

- `0x140023560`
- `0x140035e94`
- `0x1400e6e6c`

## import_xrefs

- `ntoskrnl!PsImpersonateClient` at `0x1400e6ee5`
- `ntoskrnl!PsImpersonateClient` at `0x1400e6ee5`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x1400e6f4c`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x1400e6f4c`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x1400e6ebf`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x1400e6ebf`
- `ntoskrnl!SeTokenType` at `0x1400e6e81`
- `ntoskrnl!SeTokenType` at `0x1400e6e81`
- `ntoskrnl!SeTokenImpersonationLevel` at `0x1400e6e95`
- `ntoskrnl!SeTokenImpersonationLevel` at `0x1400e6e95`

## string_xrefs

- `0x1400e6f31`: `VhdmpiBeginImpersonation`
- `0x1400e6f23`: `Failed to impersonate client 0x%08x`

## pseudocode

```c
__int64 __fastcall VhdmpiBeginImpersonation(PACCESS_TOKEN Token, __int64 a2)
{
  SECURITY_IMPERSONATION_LEVEL ImpersonationLevel; // esi
  NTSTATUS v5; // ebx
  unsigned int v6; // edx
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
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2048) )
      TraceEvents("VhdmpiBeginImpersonation", 0x18F7u, 2u, v6, "Failed to impersonate client 0x%08x", v5);
    v7 = *(void **)(a2 + 8);
    if ( v7 )
      PsDereferenceImpersonationToken(v7);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400e6e6c  mov     [rsp+arg_0], rbx
0x1400e6e71  mov     [rsp+arg_8], rsi
0x1400e6e76  push    rdi
0x1400e6e77  sub     rsp, 30h
0x1400e6e7b  mov     rdi, rdx
0x1400e6e7e  mov     rbx, rcx
0x1400e6e81  call    cs:__imp_SeTokenType
0x1400e6e88  nop     dword ptr [rax+rax+00h]
0x1400e6e8d  cmp     eax, 2
0x1400e6e90  jnz     short loc_1400E6EA5
0x1400e6e92  mov     rcx, rbx
0x1400e6e95  call    cs:__imp_SeTokenImpersonationLevel
0x1400e6e9c  nop     dword ptr [rax+rax+00h]
0x1400e6ea1  mov     esi, eax
0x1400e6ea3  jmp     short loc_1400E6EAA
0x1400e6ea5  mov     esi, 2
0x1400e6eaa  mov     rcx, gs:188h; Thread
0x1400e6eb3  lea     r9, [rdi+4]; ImpersonationLevel
0x1400e6eb7  lea     r8, [rdi+2]; EffectiveOnly
0x1400e6ebb  lea     rdx, [rdi+1]; CopyOnOpen
0x1400e6ebf  call    cs:__imp_PsReferenceImpersonationToken
0x1400e6ec6  nop     dword ptr [rax+rax+00h]
0x1400e6ecb  xor     r9d, r9d; EffectiveOnly
0x1400e6ece  mov     [rsp+38h+ImpersonationLevel], esi; ImpersonationLevel
0x1400e6ed2  mov     [rdi+8], rax
0x1400e6ed6  xor     r8d, r8d; CopyOnOpen
0x1400e6ed9  mov     rcx, gs:188h; Thread
0x1400e6ee2  mov     rdx, rbx; Token
0x1400e6ee5  call    cs:__imp_PsImpersonateClient
0x1400e6eec  nop     dword ptr [rax+rax+00h]
0x1400e6ef1  mov     ebx, eax
0x1400e6ef3  test    eax, eax
0x1400e6ef5  jns     short loc_1400E6F5A
0x1400e6ef7  mov     eax, cs:dword_140087708
0x1400e6efd  cmp     eax, 2
0x1400e6f00  jbe     short loc_1400E6F43
0x1400e6f02  mov     edx, 800h
0x1400e6f07  lea     rcx, dword_140087708
0x1400e6f0e  call    _tlgKeywordOn
0x1400e6f13  test    al, al
0x1400e6f15  jz      short loc_1400E6F43
0x1400e6f17  mov     ecx, 18F7h
0x1400e6f1c  mov     dword ptr [rsp+38h+var_10], ebx; char
0x1400e6f20  mov     r9d, edx; int
0x1400e6f23  lea     rax, aFailedToImpers; "Failed to impersonate client 0x%08x"
0x1400e6f2a  mov     edx, ecx; int
0x1400e6f2c  mov     qword ptr [rsp+38h+ImpersonationLevel], rax; char *
0x1400e6f31  lea     rcx, aVhdmpibeginimp; "VhdmpiBeginImpersonation"
0x1400e6f38  mov     r8d, 2; int
0x1400e6f3e  call    TraceEvents
0x1400e6f43  mov     rcx, [rdi+8]; ImpersonationToken
0x1400e6f47  test    rcx, rcx
0x1400e6f4a  jz      short loc_1400E6F5F
0x1400e6f4c  call    cs:__imp_PsDereferenceImpersonationToken
0x1400e6f53  nop     dword ptr [rax+rax+00h]
0x1400e6f58  jmp     short loc_1400E6F5F
0x1400e6f5a  mov     byte ptr [rdi], 1
0x1400e6f5d  xor     ebx, ebx
0x1400e6f5f  mov     rsi, [rsp+38h+arg_8]
0x1400e6f64  mov     eax, ebx
0x1400e6f66  mov     rbx, [rsp+38h+arg_0]
0x1400e6f6b  add     rsp, 30h
0x1400e6f6f  pop     rdi
0x1400e6f70  retn
```
