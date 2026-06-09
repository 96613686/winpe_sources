# CopySelfRelativeSD(void *,tlx::unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>> &)

- ea: `0x18003ed4c`
- end: `0x18003edf0`
- name: `?CopySelfRelativeSD@@YAKPEAXAEAV?$unique_any@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@tlx@@@Z`
- size: `164`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003dcc4`
- `0x18003e020`
- `0x18003e14c`
- `0x180060194`
- `0x180076cf0`

## callees

- `0x18003ed4c`
- `0x18003edf8`
- `0x1800d3370`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ede8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ede8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003edc0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003edc0`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18003edb4`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18003edb4`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18003ed85`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18003ed85`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18003eda7`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18003eda7`

## pseudocode

```c
DWORD __fastcall CopySelfRelativeSD(void *Src, void **a2)
{
  DWORD SecurityDescriptorLength; // ebx
  HLOCAL v6; // rax
  WORD pControl; // [rsp+30h] [rbp+8h] BYREF
  DWORD dwRevision; // [rsp+40h] [rbp+18h] BYREF

  tlx::unique_any<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>::reset(a2, 0);
  if ( !Src )
    return 0;
  if ( !IsValidSecurityDescriptor(Src) )
    return 13;
  pControl = 0;
  dwRevision = 0;
  if ( GetSecurityDescriptorControl(Src, &pControl, &dwRevision) )
  {
    SecurityDescriptorLength = GetSecurityDescriptorLength(Src);
    v6 = LocalAlloc(0, SecurityDescriptorLength);
    tlx::unique_any<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>::reset(a2, v6);
    memcpy_0(*a2, Src, SecurityDescriptorLength);
    return 0;
  }
  return GetLastError();
}

```

## disassembly

```asm
0x18003ed4c  mov     [rsp+arg_8], rbx
0x18003ed51  mov     [rsp+arg_18], rsi
0x18003ed56  push    rdi
0x18003ed57  sub     rsp, 20h
0x18003ed5b  mov     rsi, rdx
0x18003ed5e  mov     rdi, rcx
0x18003ed61  mov     rcx, rsi
0x18003ed64  xor     edx, edx
0x18003ed66  call    ?reset@?$unique_any@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>>::reset(void *)
0x18003ed6b  test    rdi, rdi
0x18003ed6e  jnz     short loc_18003ED82
0x18003ed70  xor     eax, eax
0x18003ed72  mov     rbx, [rsp+28h+arg_8]
0x18003ed77  mov     rsi, [rsp+28h+arg_18]
0x18003ed7c  add     rsp, 20h
0x18003ed80  pop     rdi
0x18003ed81  retn
0x18003ed82  mov     rcx, rdi; pSecurityDescriptor
0x18003ed85  call    cs:__imp_IsValidSecurityDescriptor
0x18003ed8b  test    eax, eax
0x18003ed8d  jz      short loc_18003EDE1
0x18003ed8f  xor     eax, eax
0x18003ed91  lea     r8, [rsp+28h+dwRevision]; lpdwRevision
0x18003ed96  lea     rdx, [rsp+28h+pControl]; pControl
0x18003ed9b  mov     [rsp+28h+pControl], ax
0x18003eda0  mov     rcx, rdi; pSecurityDescriptor
0x18003eda3  mov     [rsp+28h+dwRevision], eax
0x18003eda7  call    cs:__imp_GetSecurityDescriptorControl
0x18003edad  test    eax, eax
0x18003edaf  jz      short loc_18003EDE8
0x18003edb1  mov     rcx, rdi; pSecurityDescriptor
0x18003edb4  call    cs:__imp_GetSecurityDescriptorLength
0x18003edba  mov     edx, eax; uBytes
0x18003edbc  xor     ecx, ecx; uFlags
0x18003edbe  mov     ebx, eax
0x18003edc0  call    cs:__imp_LocalAlloc
0x18003edc6  mov     rdx, rax
0x18003edc9  mov     rcx, rsi
0x18003edcc  call    ?reset@?$unique_any@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>>::reset(void *)
0x18003edd1  mov     rcx, [rsi]; void *
0x18003edd4  mov     r8d, ebx; Size
0x18003edd7  mov     rdx, rdi; Src
0x18003edda  call    memcpy_0
0x18003eddf  jmp     short loc_18003ED70
0x18003ede1  mov     eax, 0Dh
0x18003ede6  jmp     short loc_18003ED72
0x18003ede8  call    cs:__imp_GetLastError
0x18003edee  jmp     short loc_18003ED72
```
