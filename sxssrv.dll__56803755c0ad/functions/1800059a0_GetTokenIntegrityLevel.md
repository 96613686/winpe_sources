# GetTokenIntegrityLevel

- ea: `0x1800059a0`
- end: `0x180005ab6`
- name: `GetTokenIntegrityLevel`
- size: `278`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180005920`

## callees

- `0x1800059a0`
- `0x180006c30`

## import_xrefs

- `ntdll!RtlInitializeSid` at `0x180005a2d`
- `ntdll!RtlInitializeSid` at `0x180005a2d`
- `ntdll!NtQueryInformationToken` at `0x180005a59`
- `ntdll!NtQueryInformationToken` at `0x180005a59`
- `ntdll!RtlFreeHeap` at `0x180005aa1`
- `ntdll!RtlFreeHeap` at `0x180005aa1`
- `ntdll!RtlAllocateHeap` at `0x1800059fe`
- `ntdll!RtlAllocateHeap` at `0x1800059fe`
- `ntdll!RtlLengthRequiredSid` at `0x1800059d9`
- `ntdll!RtlLengthRequiredSid` at `0x1800059d9`

## pseudocode

```c
__int64 __fastcall GetTokenIntegrityLevel(HANDLE TokenHandle, _QWORD *a2)
{
  _QWORD *Heap; // rax
  void *v5; // rdi
  NTSTATUS v6; // ebx
  ULONG TokenInformationLength; // [rsp+30h] [rbp-38h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+34h] [rbp-34h] BYREF

  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 4096;
  *a2 = 0;
  TokenInformationLength = RtlLengthRequiredSid(1u) + 16;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, TokenInformationLength);
  v5 = Heap;
  if ( !Heap )
    return 3221225495LL;
  *Heap = Heap + 2;
  v6 = RtlInitializeSid(Heap + 2, &IdentifierAuthority, 1u);
  if ( v6 < 0
    || (v6 = NtQueryInformationToken(
               TokenHandle,
               TokenIntegrityLevel,
               v5,
               TokenInformationLength,
               &TokenInformationLength),
        v6 < 0) )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
  }
  else
  {
    *a2 = v5;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800059a0  push    rsi
0x1800059a2  push    rdi
0x1800059a3  push    r14
0x1800059a5  sub     rsp, 50h
0x1800059a9  mov     rax, cs:__security_cookie
0x1800059b0  xor     rax, rsp
0x1800059b3  mov     [rsp+68h+var_28], rax
0x1800059b8  mov     rsi, rcx
0x1800059bb  mov     dword ptr [rsp+68h+IdentifierAuthority.Value], 0
0x1800059c3  mov     ecx, 1; SubAuthorityCount
0x1800059c8  mov     word ptr [rsp+68h+IdentifierAuthority.Value+4], 1000h
0x1800059cf  mov     r14, rdx
0x1800059d2  mov     qword ptr [rdx], 0
0x1800059d9  call    cs:__imp_RtlLengthRequiredSid
0x1800059e0  nop     dword ptr [rax+rax+00h]
0x1800059e5  add     eax, 10h
0x1800059e8  xor     edx, edx; Flags
0x1800059ea  mov     [rsp+68h+TokenInformationLength], eax
0x1800059ee  mov     rcx, gs:60h
0x1800059f7  mov     r8d, eax; Size
0x1800059fa  mov     rcx, [rcx+30h]; HeapHandle
0x1800059fe  call    cs:__imp_RtlAllocateHeap
0x180005a05  nop     dword ptr [rax+rax+00h]
0x180005a0a  mov     rdi, rax
0x180005a0d  test    rax, rax
0x180005a10  jz      loc_180005AAF
0x180005a16  lea     rcx, [rax+10h]; Sid
0x180005a1a  mov     [rsp+68h+arg_10], rbx
0x180005a22  mov     r8b, 1; SubAuthorityCount
0x180005a25  mov     [rax], rcx
0x180005a28  lea     rdx, [rsp+68h+IdentifierAuthority]; IdentifierAuthority
0x180005a2d  call    cs:__imp_RtlInitializeSid
0x180005a34  nop     dword ptr [rax+rax+00h]
0x180005a39  mov     ebx, eax
0x180005a3b  test    eax, eax
0x180005a3d  js      short loc_180005A8F
0x180005a3f  mov     r9d, [rsp+68h+TokenInformationLength]; TokenInformationLength
0x180005a44  lea     rax, [rsp+68h+TokenInformationLength]
0x180005a49  mov     r8, rdi; TokenInformation
0x180005a4c  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x180005a51  mov     edx, 19h; TokenInformationClass
0x180005a56  mov     rcx, rsi; TokenHandle
0x180005a59  call    cs:__imp_NtQueryInformationToken
0x180005a60  nop     dword ptr [rax+rax+00h]
0x180005a65  mov     ebx, eax
0x180005a67  test    eax, eax
0x180005a69  js      short loc_180005A8F
0x180005a6b  mov     [r14], rdi
0x180005a6e  mov     eax, ebx
0x180005a70  mov     rbx, [rsp+68h+arg_10]
0x180005a78  mov     rcx, [rsp+68h+var_28]
0x180005a7d  xor     rcx, rsp; StackCookie
0x180005a80  call    __security_check_cookie
0x180005a85  add     rsp, 50h
0x180005a89  pop     r14
0x180005a8b  pop     rdi
0x180005a8c  pop     rsi
0x180005a8d  retn
0x180005a8f  mov     rcx, gs:60h
0x180005a98  mov     r8, rdi; P
0x180005a9b  xor     edx, edx; Flags
0x180005a9d  mov     rcx, [rcx+30h]; HeapHandle
0x180005aa1  call    cs:__imp_RtlFreeHeap
0x180005aa8  nop     dword ptr [rax+rax+00h]
0x180005aad  jmp     short loc_180005A6E
0x180005aaf  mov     eax, 0C0000017h
0x180005ab4  jmp     short loc_180005A78
```
