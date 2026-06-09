# ORMakeSDRelative

- ea: `0x180073cb8`
- end: `0x180073d98`
- name: `ORMakeSDRelative`
- size: `224`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pAbsoluteSecurityDescriptor)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006fc48`
- `0x1800741a0`
- `0x18007469c`

## callees

- `0x180003b26`
- `0x180003b32`
- `0x180073cb8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073d19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073d67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073d19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073d67`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180073ce7`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180073ce7`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180073d0d`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180073d57`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180073d0d`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180073d57`

## pseudocode

```c
__int64 __fastcall ORMakeSDRelative(PSECURITY_DESCRIPTOR pAbsoluteSecurityDescriptor, _QWORD *a2)
{
  DWORD LastError; // edi
  void *v5; // rax
  PSECURITY_DESCRIPTOR v6; // rbx
  WORD pControl; // [rsp+48h] [rbp+10h] BYREF
  DWORD dwBufferLength; // [rsp+50h] [rbp+18h] BYREF
  DWORD dwRevision; // [rsp+58h] [rbp+20h] BYREF

  dwBufferLength = 0;
  dwRevision = 0;
  pControl = 0;
  GetSecurityDescriptorControl(pAbsoluteSecurityDescriptor, &pControl, &dwRevision);
  if ( (pControl & 0x8000u) != 0 )
  {
    v6 = pAbsoluteSecurityDescriptor;
    goto LABEL_11;
  }
  MakeSelfRelativeSD(pAbsoluteSecurityDescriptor, 0, &dwBufferLength);
  if ( GetLastError() != 122 )
  {
    LastError = 1359;
LABEL_9:
    v6 = 0;
    goto LABEL_12;
  }
  v5 = o__aligned_malloc_0(dwBufferLength, 0x10u);
  v6 = v5;
  if ( !v5 )
  {
    LastError = 8;
    goto LABEL_9;
  }
  if ( MakeSelfRelativeSD(pAbsoluteSecurityDescriptor, v5, &dwBufferLength) )
  {
LABEL_11:
    LastError = 0;
    goto LABEL_12;
  }
  LastError = GetLastError();
  if ( LastError )
  {
    aligned_free(v6);
    goto LABEL_9;
  }
LABEL_12:
  *a2 = v6;
  return LastError;
}

```

## disassembly

```asm
0x180073cb8  push    rbx
0x180073cba  push    rsi
0x180073cbb  push    rdi
0x180073cbc  sub     rsp, 20h
0x180073cc0  mov     rsi, rdx
0x180073cc3  mov     [rsp+38h+dwBufferLength], 0
0x180073ccb  xor     eax, eax
0x180073ccd  mov     [rsp+38h+dwRevision], 0
0x180073cd5  lea     rdx, [rsp+38h+pControl]; pControl
0x180073cda  mov     [rsp+38h+pControl], ax
0x180073cdf  lea     r8, [rsp+38h+dwRevision]; lpdwRevision
0x180073ce4  mov     rdi, rcx
0x180073ce7  call    cs:__imp_GetSecurityDescriptorControl
0x180073cee  nop     dword ptr [rax+rax+00h]
0x180073cf3  mov     eax, 8000h
0x180073cf8  test    [rsp+38h+pControl], ax
0x180073cfd  jnz     loc_180073D85
0x180073d03  lea     r8, [rsp+38h+dwBufferLength]; lpdwBufferLength
0x180073d08  xor     edx, edx; pSelfRelativeSecurityDescriptor
0x180073d0a  mov     rcx, rdi; pAbsoluteSecurityDescriptor
0x180073d0d  call    cs:__imp_MakeSelfRelativeSD
0x180073d14  nop     dword ptr [rax+rax+00h]
0x180073d19  call    cs:__imp_GetLastError
0x180073d20  nop     dword ptr [rax+rax+00h]
0x180073d25  cmp     eax, 7Ah ; 'z'
0x180073d28  jz      short loc_180073D31
0x180073d2a  mov     edi, 54Fh
0x180073d2f  jmp     short loc_180073D81
0x180073d31  mov     ecx, [rsp+38h+dwBufferLength]; Size
0x180073d35  mov     edx, 10h; Alignment
0x180073d3a  call    _o__aligned_malloc_0
0x180073d3f  mov     rbx, rax
0x180073d42  test    rax, rax
0x180073d45  jnz     short loc_180073D4C
0x180073d47  lea     edi, [rax+8]
0x180073d4a  jmp     short loc_180073D81
0x180073d4c  lea     r8, [rsp+38h+dwBufferLength]; lpdwBufferLength
0x180073d51  mov     rdx, rbx; pSelfRelativeSecurityDescriptor
0x180073d54  mov     rcx, rdi; pAbsoluteSecurityDescriptor
0x180073d57  call    cs:__imp_MakeSelfRelativeSD
0x180073d5e  nop     dword ptr [rax+rax+00h]
0x180073d63  test    eax, eax
0x180073d65  jnz     short loc_180073D88
0x180073d67  call    cs:__imp_GetLastError
0x180073d6e  nop     dword ptr [rax+rax+00h]
0x180073d73  mov     edi, eax
0x180073d75  test    eax, eax
0x180073d77  jz      short loc_180073D8A
0x180073d79  mov     rcx, rbx; Block
0x180073d7c  call    _aligned_free
0x180073d81  xor     ebx, ebx
0x180073d83  jmp     short loc_180073D8A
0x180073d85  mov     rbx, rdi
0x180073d88  xor     edi, edi
0x180073d8a  mov     [rsi], rbx
0x180073d8d  mov     eax, edi
0x180073d8f  add     rsp, 20h
0x180073d93  pop     rdi
0x180073d94  pop     rsi
0x180073d95  pop     rbx
0x180073d96  retn
```
