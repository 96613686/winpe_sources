# CTokenInformation::GetTokenGroups(void)

- ea: `0x1800063fc`
- end: `0x180006484`
- name: `?GetTokenGroups@CTokenInformation@@AEAAXXZ`
- size: `136`
- prototype: `void __fastcall(HANDLE *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800045b8`

## callees

- `0x1800034c4`
- `0x1800063fc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006428`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006460`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006428`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006460`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006434`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006434`

## pseudocode

```c
void __fastcall CTokenInformation::GetTokenGroups(HANDLE *this)
{
  HLOCAL v2; // rax
  DWORD TokenInformationLength; // [rsp+40h] [rbp+8h] BYREF

  TokenInformationLength = 0;
  GetTokenInformation(*this, TokenGroups, 0, 0, &TokenInformationLength);
  v2 = LocalAlloc(0, TokenInformationLength);
  this[1] = v2;
  if ( v2 )
  {
    if ( !GetTokenInformation(*this, TokenGroups, v2, TokenInformationLength, &TokenInformationLength) )
    {
      ReleaseMemoryWorker(this + 1);
      this[1] = 0;
    }
  }
}

```

## disassembly

```asm
0x1800063fc  mov     [rsp+arg_8], rbx
0x180006401  push    rdi
0x180006402  sub     rsp, 30h
0x180006406  xor     r9d, r9d; TokenInformationLength
0x180006409  mov     [rsp+38h+TokenInformationLength], 0
0x180006411  mov     rdi, rcx
0x180006414  lea     rax, [rsp+38h+TokenInformationLength]
0x180006419  mov     rcx, [rcx]; TokenHandle
0x18000641c  xor     r8d, r8d; TokenInformation
0x18000641f  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180006424  lea     edx, [r9+2]; TokenInformationClass
0x180006428  call    cs:__imp_GetTokenInformation
0x18000642e  mov     edx, [rsp+38h+TokenInformationLength]; uBytes
0x180006432  xor     ecx, ecx; uFlags
0x180006434  call    cs:__imp_LocalAlloc
0x18000643a  lea     rbx, [rdi+8]
0x18000643e  mov     [rbx], rax
0x180006441  test    rax, rax
0x180006444  jz      short loc_180006479
0x180006446  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18000644b  lea     rcx, [rsp+38h+TokenInformationLength]
0x180006450  mov     [rsp+38h+ReturnLength], rcx; ReturnLength
0x180006455  mov     r8, rax; TokenInformation
0x180006458  mov     rcx, [rdi]; TokenHandle
0x18000645b  mov     edx, 2; TokenInformationClass
0x180006460  call    cs:__imp_GetTokenInformation
0x180006466  test    eax, eax
0x180006468  jnz     short loc_180006479
0x18000646a  mov     rcx, rbx
0x18000646d  call    ReleaseMemoryWorker
0x180006472  mov     qword ptr [rbx], 0
0x180006479  mov     rbx, [rsp+38h+arg_8]
0x18000647e  add     rsp, 30h
0x180006482  pop     rdi
0x180006483  retn
```
