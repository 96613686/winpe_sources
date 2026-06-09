# GetUserSid

- ea: `0x180006a24`
- end: `0x180006b73`
- name: `GetUserSid`
- size: `335`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800080b0`

## callees

- `0x180006a24`

## import_xrefs

- `KERNELBASE!LocalReAlloc` at `0x180006a9f`
- `KERNELBASE!LocalReAlloc` at `0x180006a9f`
- `KERNELBASE!LocalAlloc` at `0x180006a4a`
- `KERNELBASE!LocalAlloc` at `0x180006afc`
- `KERNELBASE!LocalAlloc` at `0x180006a4a`
- `KERNELBASE!LocalAlloc` at `0x180006afc`
- `ntdll!RtlCopySid` at `0x180006b1a`
- `ntdll!RtlCopySid` at `0x180006b1a`
- `ntdll!NtQueryInformationToken` at `0x180006a7c`
- `ntdll!NtQueryInformationToken` at `0x180006ad5`
- `ntdll!NtQueryInformationToken` at `0x180006a7c`
- `ntdll!NtQueryInformationToken` at `0x180006ad5`
- `ntdll!RtlLengthSid` at `0x180006ae8`
- `ntdll!RtlLengthSid` at `0x180006ae8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006b2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006b3e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006b54`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006b2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006b3e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006b54`

## pseudocode

```c
void *__fastcall GetUserSid(HANDLE TokenHandle)
{
  PSID *v2; // rdi
  NTSTATUS v3; // eax
  PSID *v4; // rsi
  PSID *v5; // rcx
  HLOCAL v6; // rax
  void *v7; // rsi
  NTSTATUS v8; // ebx
  ULONG TokenInformationLength; // [rsp+40h] [rbp+8h] BYREF

  TokenInformationLength = 200;
  if ( !TokenHandle )
    return 0;
  v2 = (PSID *)LocalAlloc(0, 0xC8u);
  if ( !v2 )
    return 0;
  v3 = NtQueryInformationToken(TokenHandle, TokenUser, v2, TokenInformationLength, &TokenInformationLength);
  if ( v3 == -1073741789 )
  {
    v4 = v2;
    v2 = (PSID *)LocalReAlloc(v2, TokenInformationLength, 2u);
    if ( !v2 )
    {
      v5 = v4;
LABEL_13:
      LocalFree(v5);
      return 0;
    }
    v3 = NtQueryInformationToken(TokenHandle, TokenUser, v2, TokenInformationLength, &TokenInformationLength);
  }
  if ( v3 < 0
    || (TokenInformationLength = RtlLengthSid(*v2), v6 = LocalAlloc(0, TokenInformationLength), (v7 = v6) == 0) )
  {
    v5 = v2;
    goto LABEL_13;
  }
  v8 = RtlCopySid(TokenInformationLength, v6, *v2);
  LocalFree(v2);
  if ( v8 < 0 )
  {
    LocalFree(v7);
    return 0;
  }
  return v7;
}

```

## disassembly

```asm
0x180006a24  mov     [rsp+arg_8], rbx
0x180006a29  mov     [rsp+arg_10], rsi
0x180006a2e  push    rdi
0x180006a2f  sub     rsp, 30h
0x180006a33  mov     edx, 0C8h; uBytes
0x180006a38  mov     rbx, rcx
0x180006a3b  mov     [rsp+38h+TokenInformationLength], edx
0x180006a3f  test    rcx, rcx
0x180006a42  jz      loc_180006B60
0x180006a48  xor     ecx, ecx; uFlags
0x180006a4a  call    cs:__imp_LocalAlloc
0x180006a51  nop     dword ptr [rax+rax+00h]
0x180006a56  mov     rdi, rax
0x180006a59  test    rax, rax
0x180006a5c  jz      loc_180006B60
0x180006a62  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x180006a67  lea     rax, [rsp+38h+TokenInformationLength]
0x180006a6c  mov     r8, rdi; TokenInformation
0x180006a6f  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180006a74  mov     edx, 1; TokenInformationClass
0x180006a79  mov     rcx, rbx; TokenHandle
0x180006a7c  call    cs:__imp_NtQueryInformationToken
0x180006a83  nop     dword ptr [rax+rax+00h]
0x180006a88  cmp     eax, 0C0000023h
0x180006a8d  jnz     short loc_180006AE1
0x180006a8f  mov     edx, [rsp+38h+TokenInformationLength]; uBytes
0x180006a93  mov     r8d, 2; uFlags
0x180006a99  mov     rcx, rdi; hMem
0x180006a9c  mov     rsi, rdi
0x180006a9f  call    cs:__imp_LocalReAlloc
0x180006aa6  nop     dword ptr [rax+rax+00h]
0x180006aab  mov     rdi, rax
0x180006aae  test    rax, rax
0x180006ab1  jnz     short loc_180006ABB
0x180006ab3  mov     rcx, rsi
0x180006ab6  jmp     loc_180006B54
0x180006abb  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x180006ac0  lea     rax, [rsp+38h+TokenInformationLength]
0x180006ac5  mov     r8, rdi; TokenInformation
0x180006ac8  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180006acd  mov     edx, 1; TokenInformationClass
0x180006ad2  mov     rcx, rbx; TokenHandle
0x180006ad5  call    cs:__imp_NtQueryInformationToken
0x180006adc  nop     dword ptr [rax+rax+00h]
0x180006ae1  test    eax, eax
0x180006ae3  js      short loc_180006B51
0x180006ae5  mov     rcx, [rdi]; Sid
0x180006ae8  call    cs:__imp_RtlLengthSid
0x180006aef  nop     dword ptr [rax+rax+00h]
0x180006af4  mov     edx, eax; uBytes
0x180006af6  xor     ecx, ecx; uFlags
0x180006af8  mov     [rsp+38h+TokenInformationLength], edx
0x180006afc  call    cs:__imp_LocalAlloc
0x180006b03  nop     dword ptr [rax+rax+00h]
0x180006b08  mov     rsi, rax
0x180006b0b  test    rax, rax
0x180006b0e  jz      short loc_180006B51
0x180006b10  mov     r8, [rdi]; SourceSid
0x180006b13  mov     rdx, rax; DestinationSid
0x180006b16  mov     ecx, [rsp+38h+TokenInformationLength]; DestinationSidLength
0x180006b1a  call    cs:__imp_RtlCopySid
0x180006b21  nop     dword ptr [rax+rax+00h]
0x180006b26  mov     rcx, rdi; hMem
0x180006b29  mov     ebx, eax
0x180006b2b  call    cs:__imp_LocalFree
0x180006b32  nop     dword ptr [rax+rax+00h]
0x180006b37  test    ebx, ebx
0x180006b39  jns     short loc_180006B4C
0x180006b3b  mov     rcx, rsi; hMem
0x180006b3e  call    cs:__imp_LocalFree
0x180006b45  nop     dword ptr [rax+rax+00h]
0x180006b4a  xor     esi, esi
0x180006b4c  mov     rax, rsi
0x180006b4f  jmp     short loc_180006B62
0x180006b51  mov     rcx, rdi; hMem
0x180006b54  call    cs:__imp_LocalFree
0x180006b5b  nop     dword ptr [rax+rax+00h]
0x180006b60  xor     eax, eax
0x180006b62  mov     rbx, [rsp+38h+arg_8]
0x180006b67  mov     rsi, [rsp+38h+arg_10]
0x180006b6c  add     rsp, 30h
0x180006b70  pop     rdi
0x180006b71  retn
```
