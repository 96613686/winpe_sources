# GetSecurityDescriptorForACL

- ea: `0x180012ef8`
- end: `0x180013030`
- name: `GetSecurityDescriptorForACL`
- size: `312`
- prototype: `__int64 __fastcall(PACL pDacl, PACL pSacl, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004f10`
- `0x18001396c`

## callees

- `0x180012ef8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012fb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012fb1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012f23`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012fc5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012f23`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012fc5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012fef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013007`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013015`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012fef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013007`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013015`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180012f6d`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180012f6d`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180012f41`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180012f41`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180012fa1`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180012fde`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180012fa1`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180012fde`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x180012f89`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x180012f89`

## pseudocode

```c
__int64 __fastcall GetSecurityDescriptorForACL(PACL pDacl, PACL pSacl, _QWORD *a3)
{
  HLOCAL v6; // rax
  void *v7; // rdi
  DWORD LastError; // ebx
  void *v9; // rsi
  HLOCAL v10; // rax
  DWORD dwBufferLength; // [rsp+58h] [rbp+20h] BYREF

  dwBufferLength = 0;
  v6 = LocalAlloc(0x40u, 0x28u);
  v7 = v6;
  if ( !v6 )
    return 8;
  v9 = 0;
  if ( !InitializeSecurityDescriptor(v6, 1u)
    || !SetSecurityDescriptorDacl(v7, 1, pDacl, 0)
    || pSacl && !SetSecurityDescriptorSacl(v7, 1, pSacl, 0) )
  {
    goto LABEL_4;
  }
  dwBufferLength = 0;
  if ( !MakeSelfRelativeSD(v7, 0, &dwBufferLength) && dwBufferLength )
  {
    LastError = GetLastError();
    if ( LastError != 122 )
    {
LABEL_5:
      if ( !LastError )
        return LastError;
      goto LABEL_18;
    }
    v10 = LocalAlloc(0x40u, dwBufferLength);
    v9 = v10;
    if ( !v10 )
    {
LABEL_16:
      *a3 = v7;
      return 0;
    }
    if ( MakeSelfRelativeSD(v7, v10, &dwBufferLength) )
    {
      LocalFree(v7);
      v7 = v9;
      goto LABEL_16;
    }
LABEL_4:
    LastError = GetLastError();
    goto LABEL_5;
  }
  LastError = 87;
LABEL_18:
  LocalFree(v7);
  if ( v9 )
    LocalFree(v9);
  return LastError;
}

```

## disassembly

```asm
0x180012ef8  mov     [rsp+arg_0], rbx
0x180012efd  mov     [rsp+arg_8], rbp
0x180012f02  push    rsi
0x180012f03  push    rdi
0x180012f04  push    r14
0x180012f06  sub     rsp, 20h
0x180012f0a  mov     rbx, rdx
0x180012f0d  mov     [rsp+38h+dwBufferLength], 0
0x180012f15  mov     edx, 28h ; '('; uBytes
0x180012f1a  mov     rbp, rcx
0x180012f1d  mov     r14, r8
0x180012f20  lea     ecx, [rdx+18h]; uFlags
0x180012f23  call    cs:__imp_LocalAlloc
0x180012f29  mov     rdi, rax
0x180012f2c  test    rax, rax
0x180012f2f  jnz     short loc_180012F39
0x180012f31  lea     ebx, [rax+8]
0x180012f34  jmp     loc_18001301B
0x180012f39  xor     esi, esi
0x180012f3b  mov     rcx, rdi; pSecurityDescriptor
0x180012f3e  lea     edx, [rsi+1]; dwRevision
0x180012f41  call    cs:__imp_InitializeSecurityDescriptor
0x180012f47  test    eax, eax
0x180012f49  jnz     short loc_180012F60
0x180012f4b  call    cs:__imp_GetLastError
0x180012f51  mov     ebx, eax
0x180012f53  test    ebx, ebx
0x180012f55  jz      loc_18001301B
0x180012f5b  jmp     loc_180013004
0x180012f60  xor     r9d, r9d; bDaclDefaulted
0x180012f63  mov     r8, rbp; pDacl
0x180012f66  mov     rcx, rdi; pSecurityDescriptor
0x180012f69  lea     edx, [r9+1]; bDaclPresent
0x180012f6d  call    cs:__imp_SetSecurityDescriptorDacl
0x180012f73  test    eax, eax
0x180012f75  jz      short loc_180012F4B
0x180012f77  test    rbx, rbx
0x180012f7a  jz      short loc_180012F93
0x180012f7c  xor     r9d, r9d; bSaclDefaulted
0x180012f7f  mov     r8, rbx; pSacl
0x180012f82  mov     rcx, rdi; pSecurityDescriptor
0x180012f85  lea     edx, [r9+1]; bSaclPresent
0x180012f89  call    cs:__imp_SetSecurityDescriptorSacl
0x180012f8f  test    eax, eax
0x180012f91  jz      short loc_180012F4B
0x180012f93  lea     r8, [rsp+38h+dwBufferLength]; lpdwBufferLength
0x180012f98  mov     [rsp+38h+dwBufferLength], esi
0x180012f9c  xor     edx, edx; pSelfRelativeSecurityDescriptor
0x180012f9e  mov     rcx, rdi; pAbsoluteSecurityDescriptor
0x180012fa1  call    cs:__imp_MakeSelfRelativeSD
0x180012fa7  test    eax, eax
0x180012fa9  jnz     short loc_180012FFF
0x180012fab  cmp     [rsp+38h+dwBufferLength], esi
0x180012faf  jbe     short loc_180012FFF
0x180012fb1  call    cs:__imp_GetLastError
0x180012fb7  mov     ebx, eax
0x180012fb9  cmp     eax, 7Ah ; 'z'
0x180012fbc  jnz     short loc_180012F53
0x180012fbe  mov     edx, [rsp+38h+dwBufferLength]; uBytes
0x180012fc2  lea     ecx, [rax-3Ah]; uFlags
0x180012fc5  call    cs:__imp_LocalAlloc
0x180012fcb  mov     rsi, rax
0x180012fce  test    rax, rax
0x180012fd1  jz      short loc_180012FF8
0x180012fd3  lea     r8, [rsp+38h+dwBufferLength]; lpdwBufferLength
0x180012fd8  mov     rdx, rax; pSelfRelativeSecurityDescriptor
0x180012fdb  mov     rcx, rdi; pAbsoluteSecurityDescriptor
0x180012fde  call    cs:__imp_MakeSelfRelativeSD
0x180012fe4  test    eax, eax
0x180012fe6  jz      loc_180012F4B
0x180012fec  mov     rcx, rdi; hMem
0x180012fef  call    cs:__imp_LocalFree
0x180012ff5  mov     rdi, rsi
0x180012ff8  mov     [r14], rdi
0x180012ffb  xor     ebx, ebx
0x180012ffd  jmp     short loc_18001301B
0x180012fff  mov     ebx, 57h ; 'W'
0x180013004  mov     rcx, rdi; hMem
0x180013007  call    cs:__imp_LocalFree
0x18001300d  test    rsi, rsi
0x180013010  jz      short loc_18001301B
0x180013012  mov     rcx, rsi; hMem
0x180013015  call    cs:__imp_LocalFree
0x18001301b  mov     rbp, [rsp+38h+arg_8]
0x180013020  mov     eax, ebx
0x180013022  mov     rbx, [rsp+38h+arg_0]
0x180013027  add     rsp, 20h
0x18001302b  pop     r14
0x18001302d  pop     rdi
0x18001302e  pop     rsi
0x18001302f  retn
```
