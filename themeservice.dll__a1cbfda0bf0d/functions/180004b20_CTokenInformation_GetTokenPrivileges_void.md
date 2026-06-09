# CTokenInformation::GetTokenPrivileges(void)

- ea: `0x180004b20`
- end: `0x180004baa`
- name: `?GetTokenPrivileges@CTokenInformation@@AEAAXXZ`
- size: `138`
- prototype: `void __fastcall(HANDLE *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800034f0`

## callees

- `0x1800034c4`
- `0x180004b20`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004b4d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004b82`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004b4d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004b82`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004b59`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004b59`

## pseudocode

```c
void __fastcall CTokenInformation::GetTokenPrivileges(HANDLE *this)
{
  HLOCAL v2; // rax
  DWORD TokenInformationLength; // [rsp+40h] [rbp+8h] BYREF

  TokenInformationLength = 0;
  GetTokenInformation(*this, TokenPrivileges, 0, 0, &TokenInformationLength);
  v2 = LocalAlloc(0, TokenInformationLength);
  this[2] = v2;
  if ( v2 )
  {
    if ( !GetTokenInformation(*this, TokenPrivileges, v2, TokenInformationLength, &TokenInformationLength) )
    {
      ReleaseMemoryWorker(this + 2);
      this[2] = 0;
    }
  }
}

```

## disassembly

```asm
0x180004b20  mov     [rsp+arg_8], rbx
0x180004b25  push    rdi
0x180004b26  sub     rsp, 30h
0x180004b2a  mov     rbx, rcx
0x180004b2d  mov     [rsp+38h+TokenInformationLength], 0
0x180004b35  mov     rcx, [rcx]; TokenHandle
0x180004b38  lea     rax, [rsp+38h+TokenInformationLength]
0x180004b3d  xor     r9d, r9d; TokenInformationLength
0x180004b40  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180004b45  xor     r8d, r8d; TokenInformation
0x180004b48  mov     edx, 3; TokenInformationClass
0x180004b4d  call    cs:__imp_GetTokenInformation
0x180004b53  mov     edx, [rsp+38h+TokenInformationLength]; uBytes
0x180004b57  xor     ecx, ecx; uFlags
0x180004b59  call    cs:__imp_LocalAlloc
0x180004b5f  mov     [rbx+10h], rax
0x180004b63  test    rax, rax
0x180004b66  jz      short loc_180004B8C
0x180004b68  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x180004b6d  lea     rcx, [rsp+38h+TokenInformationLength]
0x180004b72  mov     [rsp+38h+ReturnLength], rcx; ReturnLength
0x180004b77  mov     r8, rax; TokenInformation
0x180004b7a  mov     rcx, [rbx]; TokenHandle
0x180004b7d  mov     edx, 3; TokenInformationClass
0x180004b82  call    cs:__imp_GetTokenInformation
0x180004b88  test    eax, eax
0x180004b8a  jz      short loc_180004B97
0x180004b8c  mov     rbx, [rsp+38h+arg_8]
0x180004b91  add     rsp, 30h
0x180004b95  pop     rdi
0x180004b96  retn
0x180004b97  lea     rcx, [rbx+10h]
0x180004b9b  call    ReleaseMemoryWorker
0x180004ba0  mov     qword ptr [rbx+10h], 0
0x180004ba8  jmp     short loc_180004B8C
```
