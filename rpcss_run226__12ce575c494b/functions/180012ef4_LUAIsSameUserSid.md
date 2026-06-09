# LUAIsSameUserSid

- ea: `0x180012ef4`
- end: `0x1800130ad`
- name: `LUAIsSameUserSid`
- size: `441`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, HANDLE)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180012dd0`

## callees

- `0x180012ef4`
- `0x1800130b4`
- `0x18009d648`
- `0x18009d68c`
- `0x180102b6c`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x180013014`
- `ntdll!NtQueryInformationToken` at `0x180013082`
- `ntdll!NtQueryInformationToken` at `0x180013014`
- `ntdll!NtQueryInformationToken` at `0x180013082`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013092`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013092`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180012f6e`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001306e`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180012f6e`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001306e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180012f90`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180012f9e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180013025`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180013045`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180012f90`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180012f9e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180013025`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180013045`

## pseudocode

```c
__int64 __fastcall LUAIsSameUserSid(HANDLE TokenHandle, HANDLE a2)
{
  HLOCAL v3; // rbx
  int v5; // r13d
  unsigned int v6; // esi
  int v7; // eax
  HLOCAL v8; // rdi
  HLOCAL hMem; // [rsp+38h] [rbp-18h] BYREF
  HLOCAL v11; // [rsp+40h] [rbp-10h] BYREF
  HANDLE TokenInformation; // [rsp+48h] [rbp-8h]

  v3 = 0;
  v11 = 0;
  hMem = 0;
  TokenInformation = 0;
  if ( !(unsigned int)Feature_ShadowAdmin__private_IsEnabledDeviceUsageNoInline() )
    return 0;
  v5 = 0;
  v6 = 1;
  if ( (int)_LUAGetUserFromToken(TokenHandle, (struct _TOKEN_USER **)&hMem) < 0 )
  {
    v8 = hMem;
  }
  else
  {
    v7 = _LUAGetUserFromToken(a2, (struct _TOKEN_USER **)&v11);
    v3 = v11;
    v8 = hMem;
    if ( v7 >= 0 )
    {
      if ( EqualSid(*(PSID *)hMem, *(PSID *)v11) )
      {
        v5 = 1;
      }
      else if ( (unsigned int)LUAIsShadowAdminEnabled() )
      {
        LUAIsElevatedToken(TokenHandle);
      }
    }
  }
  if ( TokenInformation )
    CloseHandle(TokenInformation);
  if ( v8 )
    LocalFree(v8);
  if ( v3 )
    LocalFree(v3);
  if ( !v5 )
    return 0;
  return v6;
}

```

## disassembly

```asm
0x180012ef4  mov     [rsp-38h+arg_0], rbx
0x180012ef9  push    rbp
0x180012efa  push    rsi
0x180012efb  push    rdi
0x180012efc  push    r12
0x180012efe  push    r13
0x180012f00  push    r14
0x180012f02  push    r15
0x180012f04  mov     rbp, rsp
0x180012f07  sub     rsp, 50h
0x180012f0b  xor     edi, edi
0x180012f0d  mov     r12, rdx
0x180012f10  mov     ebx, edi
0x180012f12  mov     [rbp+arg_18], edi
0x180012f15  mov     [rbp+var_10], rbx
0x180012f19  mov     r15, rcx
0x180012f1c  mov     [rbp+arg_10], edi
0x180012f1f  mov     [rbp+hMem], rdi
0x180012f23  mov     [rbp+TokenInformation], rdi
0x180012f27  mov     [rbp+var_20], edi
0x180012f2a  call    Feature_ShadowAdmin__private_IsEnabledDeviceUsageNoInline
0x180012f2f  test    eax, eax
0x180012f31  jz      loc_180012FCD
0x180012f37  lea     rdx, [rbp+hMem]; struct _TOKEN_USER **
0x180012f3b  mov     rcx, r15; TokenHandle
0x180012f3e  mov     r13d, edi
0x180012f41  mov     r14d, edi
0x180012f44  call    ?_LUAGetUserFromToken@@YAJPEAXPEAPEAU_TOKEN_USER@@@Z; _LUAGetUserFromToken(void *,_TOKEN_USER * *)
0x180012f49  lea     esi, [rdi+1]
0x180012f4c  test    eax, eax
0x180012f4e  js      short loc_180012FC7
0x180012f50  lea     rdx, [rbp+var_10]; struct _TOKEN_USER **
0x180012f54  mov     rcx, r12; TokenHandle
0x180012f57  call    ?_LUAGetUserFromToken@@YAJPEAXPEAPEAU_TOKEN_USER@@@Z; _LUAGetUserFromToken(void *,_TOKEN_USER * *)
0x180012f5c  mov     rbx, [rbp+var_10]
0x180012f60  mov     rdi, [rbp+hMem]
0x180012f64  test    eax, eax
0x180012f66  js      short loc_180012F7B
0x180012f68  mov     rdx, [rbx]; pSid2
0x180012f6b  mov     rcx, [rdi]; pSid1
0x180012f6e  call    cs:__imp_EqualSid
0x180012f74  test    eax, eax
0x180012f76  jz      short loc_180012FD1
0x180012f78  mov     r13d, esi
0x180012f7b  mov     rcx, [rbp+TokenInformation]; hObject
0x180012f7f  test    rcx, rcx
0x180012f82  jnz     loc_180013092
0x180012f88  test    rdi, rdi
0x180012f8b  jz      short loc_180012F96
0x180012f8d  mov     rcx, rdi; hMem
0x180012f90  call    cs:__imp_LocalFree
0x180012f96  test    rbx, rbx
0x180012f99  jz      short loc_180012FA4
0x180012f9b  mov     rcx, rbx; hMem
0x180012f9e  call    cs:__imp_LocalFree
0x180012fa4  test    r13d, r13d
0x180012fa7  jz      loc_18001309D
0x180012fad  mov     eax, esi
0x180012faf  mov     rbx, [rsp+50h+arg_0]
0x180012fb7  add     rsp, 50h
0x180012fbb  pop     r15
0x180012fbd  pop     r14
0x180012fbf  pop     r13
0x180012fc1  pop     r12
0x180012fc3  pop     rdi
0x180012fc4  pop     rsi
0x180012fc5  pop     rbp
0x180012fc6  retn
0x180012fc7  mov     rdi, [rbp+hMem]
0x180012fcb  jmp     short loc_180012F7B
0x180012fcd  xor     eax, eax
0x180012fcf  jmp     short loc_180012FAF
0x180012fd1  call    LUAIsShadowAdminEnabled
0x180012fd6  test    eax, eax
0x180012fd8  jz      short loc_180012F7B
0x180012fda  lea     r8, [rbp+arg_10]
0x180012fde  mov     rcx, r15; TokenHandle
0x180012fe1  lea     rdx, [rbp+arg_18]
0x180012fe5  call    LUAIsElevatedToken
0x180012fea  test    eax, eax
0x180012fec  js      short loc_180012F7B
0x180012fee  cmp     [rbp+arg_10], r13d
0x180012ff2  jz      short loc_180012F7B
0x180012ff4  lea     rax, [rbp+var_20]
0x180012ff8  mov     r9d, 8; TokenInformationLength
0x180012ffe  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180013002  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x180013007  lea     edx, [r9+0Bh]; TokenInformationClass
0x18001300b  cmp     [rbp+arg_18], r13d
0x18001300f  jz      short loc_18001307F
0x180013011  mov     rcx, r15; TokenHandle
0x180013014  call    cs:__imp_NtQueryInformationToken
0x18001301a  test    eax, eax
0x18001301c  js      loc_180012F7B
0x180013022  mov     rcx, rdi; hMem
0x180013025  call    cs:__imp_LocalFree
0x18001302b  mov     rcx, [rbp+TokenInformation]; TokenHandle
0x18001302f  lea     rdx, [rbp+hMem]; struct _TOKEN_USER **
0x180013033  mov     [rbp+hMem], r13
0x180013037  call    ?_LUAGetUserFromToken@@YAJPEAXPEAPEAU_TOKEN_USER@@@Z; _LUAGetUserFromToken(void *,_TOKEN_USER * *)
0x18001303c  mov     rdi, [rbp+hMem]
0x180013040  jmp     short loc_180013060
0x180013042  mov     rcx, rbx; hMem
0x180013045  call    cs:__imp_LocalFree
0x18001304b  mov     rcx, [rbp+TokenInformation]; TokenHandle
0x18001304f  lea     rdx, [rbp+var_10]; struct _TOKEN_USER **
0x180013053  mov     [rbp+var_10], r13
0x180013057  call    ?_LUAGetUserFromToken@@YAJPEAXPEAPEAU_TOKEN_USER@@@Z; _LUAGetUserFromToken(void *,_TOKEN_USER * *)
0x18001305c  mov     rbx, [rbp+var_10]
0x180013060  test    eax, eax
0x180013062  js      loc_180012F7B
0x180013068  mov     rdx, [rbx]; pSid2
0x18001306b  mov     rcx, [rdi]; pSid1
0x18001306e  call    cs:__imp_EqualSid
0x180013074  test    eax, eax
0x180013076  cmovnz  r14d, esi
0x18001307a  jmp     loc_180012F7B
0x18001307f  mov     rcx, r12; TokenHandle
0x180013082  call    cs:__imp_NtQueryInformationToken
0x180013088  test    eax, eax
0x18001308a  js      loc_180012F7B
0x180013090  jmp     short loc_180013042
0x180013092  call    cs:__imp_CloseHandle
0x180013098  jmp     loc_180012F88
0x18001309d  test    r14d, r14d
0x1800130a0  jnz     loc_180012FAD
0x1800130a6  xor     esi, esi
0x1800130a8  jmp     loc_180012FAD
```
