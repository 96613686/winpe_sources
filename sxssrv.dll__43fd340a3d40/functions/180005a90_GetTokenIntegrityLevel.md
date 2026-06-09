# GetTokenIntegrityLevel

- ea: `0x180005a90`
- end: `0x180005ba4`
- name: `GetTokenIntegrityLevel`
- size: `276`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180005a10`

## callees

- `0x180005a90`
- `0x180006cf0`

## import_xrefs

- `ntdll!RtlInitializeSid` at `0x180005b1b`
- `ntdll!RtlInitializeSid` at `0x180005b1b`
- `ntdll!NtQueryInformationToken` at `0x180005b47`
- `ntdll!NtQueryInformationToken` at `0x180005b47`
- `ntdll!RtlFreeHeap` at `0x180005b8f`
- `ntdll!RtlFreeHeap` at `0x180005b8f`
- `ntdll!RtlAllocateHeap` at `0x180005aec`
- `ntdll!RtlAllocateHeap` at `0x180005aec`
- `ntdll!RtlLengthRequiredSid` at `0x180005ac7`
- `ntdll!RtlLengthRequiredSid` at `0x180005ac7`

## pseudocode

```c
__int64 __fastcall GetTokenIntegrityLevel(HANDLE TokenHandle, _QWORD *a2)
{
  _QWORD *Heap; // rax
  void *v5; // rdi
  NTSTATUS v6; // ebx
  ULONG TokenInformationLength; // [rsp+30h] [rbp-38h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+34h] [rbp-34h] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 4096;
  *(_DWORD *)IdentifierAuthority.Value = 0;
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
0x180005a90  push    rsi
0x180005a92  push    rdi
0x180005a93  push    r14
0x180005a95  sub     rsp, 50h
0x180005a99  mov     rax, cs:__security_cookie
0x180005aa0  xor     rax, rsp
0x180005aa3  mov     [rsp+68h+var_28], rax
0x180005aa8  xor     eax, eax
0x180005aaa  mov     word ptr [rsp+68h+IdentifierAuthority.Value+4], 1000h
0x180005ab1  mov     rsi, rcx
0x180005ab4  mov     [rsp+68h+TokenInformationLength], eax
0x180005ab8  mov     ecx, 1; SubAuthorityCount
0x180005abd  mov     dword ptr [rsp+68h+IdentifierAuthority.Value], eax
0x180005ac1  mov     [rdx], rax
0x180005ac4  mov     r14, rdx
0x180005ac7  call    cs:__imp_RtlLengthRequiredSid
0x180005ace  nop     dword ptr [rax+rax+00h]
0x180005ad3  add     eax, 10h
0x180005ad6  xor     edx, edx; Flags
0x180005ad8  mov     [rsp+68h+TokenInformationLength], eax
0x180005adc  mov     rcx, gs:60h
0x180005ae5  mov     r8d, eax; Size
0x180005ae8  mov     rcx, [rcx+30h]; HeapHandle
0x180005aec  call    cs:__imp_RtlAllocateHeap
0x180005af3  nop     dword ptr [rax+rax+00h]
0x180005af8  mov     rdi, rax
0x180005afb  test    rax, rax
0x180005afe  jz      loc_180005B9D
0x180005b04  lea     rcx, [rax+10h]; Sid
0x180005b08  mov     [rsp+68h+arg_10], rbx
0x180005b10  mov     r8b, 1; SubAuthorityCount
0x180005b13  mov     [rax], rcx
0x180005b16  lea     rdx, [rsp+68h+IdentifierAuthority]; IdentifierAuthority
0x180005b1b  call    cs:__imp_RtlInitializeSid
0x180005b22  nop     dword ptr [rax+rax+00h]
0x180005b27  mov     ebx, eax
0x180005b29  test    eax, eax
0x180005b2b  js      short loc_180005B7D
0x180005b2d  mov     r9d, [rsp+68h+TokenInformationLength]; TokenInformationLength
0x180005b32  lea     rax, [rsp+68h+TokenInformationLength]
0x180005b37  mov     r8, rdi; TokenInformation
0x180005b3a  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x180005b3f  mov     edx, 19h; TokenInformationClass
0x180005b44  mov     rcx, rsi; TokenHandle
0x180005b47  call    cs:__imp_NtQueryInformationToken
0x180005b4e  nop     dword ptr [rax+rax+00h]
0x180005b53  mov     ebx, eax
0x180005b55  test    eax, eax
0x180005b57  js      short loc_180005B7D
0x180005b59  mov     [r14], rdi
0x180005b5c  mov     eax, ebx
0x180005b5e  mov     rbx, [rsp+68h+arg_10]
0x180005b66  mov     rcx, [rsp+68h+var_28]
0x180005b6b  xor     rcx, rsp; StackCookie
0x180005b6e  call    __security_check_cookie
0x180005b73  add     rsp, 50h
0x180005b77  pop     r14
0x180005b79  pop     rdi
0x180005b7a  pop     rsi
0x180005b7b  retn
0x180005b7d  mov     rcx, gs:60h
0x180005b86  mov     r8, rdi; P
0x180005b89  xor     edx, edx; Flags
0x180005b8b  mov     rcx, [rcx+30h]; HeapHandle
0x180005b8f  call    cs:__imp_RtlFreeHeap
0x180005b96  nop     dword ptr [rax+rax+00h]
0x180005b9b  jmp     short loc_180005B5C
0x180005b9d  mov     eax, 0C0000017h
0x180005ba2  jmp     short loc_180005B66
```
