# LUAIsSameUserSid

- ea: `0x1800dbed0`
- end: `0x1800dc077`
- name: `LUAIsSameUserSid`
- size: `423`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, HANDLE)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800b38ec`

## callees

- `0x1800dbb88`
- `0x1800dbccc`
- `0x1800dbe24`
- `0x1800dbed0`
- `0x1800dc080`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800dbf54`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800dbfe7`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800dbf54`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800dbfe7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dc02f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dc02f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800dbfc2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800dc005`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800dc03d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800dc04b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800dbfc2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800dc005`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800dc03d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800dc04b`
- `ntdll!NtQueryInformationToken` at `0x1800dbfb5`
- `ntdll!NtQueryInformationToken` at `0x1800dbff8`
- `ntdll!NtQueryInformationToken` at `0x1800dbfb5`
- `ntdll!NtQueryInformationToken` at `0x1800dbff8`

## pseudocode

```c
__int64 __fastcall LUAIsSameUserSid(HANDLE TokenHandle, HANDLE a2)
{
  HLOCAL v3; // rbx
  __int64 result; // rax
  int v6; // r13d
  unsigned int v7; // esi
  int v8; // eax
  HLOCAL v9; // rdi
  __int64 v10; // rcx
  HLOCAL hMem; // [rsp+38h] [rbp-18h] BYREF
  HLOCAL v12; // [rsp+40h] [rbp-10h] BYREF
  HANDLE TokenInformation; // [rsp+48h] [rbp-8h]

  v3 = 0;
  v12 = 0;
  hMem = 0;
  TokenInformation = 0;
  result = Feature_ShadowAdmin__private_IsEnabledDeviceUsageNoInline();
  if ( (_DWORD)result )
  {
    v6 = 0;
    v7 = 1;
    if ( (int)_LUAGetUserFromToken(TokenHandle, (struct _TOKEN_USER **)&hMem) < 0 )
    {
      v9 = hMem;
    }
    else
    {
      v8 = _LUAGetUserFromToken(a2, (struct _TOKEN_USER **)&v12);
      v3 = v12;
      v9 = hMem;
      if ( v8 >= 0 )
      {
        if ( EqualSid(*(PSID *)hMem, *(PSID *)v12) )
        {
          v6 = 1;
        }
        else if ( (unsigned int)LUAIsShadowAdminEnabled(v10) )
        {
          LUAIsElevatedToken(TokenHandle);
        }
      }
    }
    if ( TokenInformation )
      CloseHandle(TokenInformation);
    if ( v9 )
      LocalFree(v9);
    if ( v3 )
      LocalFree(v3);
    if ( !v6 )
      return 0;
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x1800dbed0  mov     [rsp-38h+arg_0], rbx
0x1800dbed5  push    rbp
0x1800dbed6  push    rsi
0x1800dbed7  push    rdi
0x1800dbed8  push    r12
0x1800dbeda  push    r13
0x1800dbedc  push    r14
0x1800dbede  push    r15
0x1800dbee0  mov     rbp, rsp
0x1800dbee3  sub     rsp, 50h
0x1800dbee7  xor     edi, edi
0x1800dbee9  mov     r12, rdx
0x1800dbeec  mov     ebx, edi
0x1800dbeee  mov     [rbp+arg_18], edi
0x1800dbef1  mov     [rbp+var_10], rbx
0x1800dbef5  mov     r15, rcx
0x1800dbef8  mov     [rbp+arg_10], edi
0x1800dbefb  mov     [rbp+hMem], rdi
0x1800dbeff  mov     [rbp+TokenInformation], rdi
0x1800dbf03  mov     [rbp+var_20], edi
0x1800dbf06  call    Feature_ShadowAdmin__private_IsEnabledDeviceUsageNoInline
0x1800dbf0b  test    eax, eax
0x1800dbf0d  jz      loc_1800DC05F
0x1800dbf13  lea     rdx, [rbp+hMem]; struct _TOKEN_USER **
0x1800dbf17  mov     rcx, r15; TokenHandle
0x1800dbf1a  mov     r13d, edi
0x1800dbf1d  mov     r14d, edi
0x1800dbf20  call    ?_LUAGetUserFromToken@@YAJPEAXPEAPEAU_TOKEN_USER@@@Z; _LUAGetUserFromToken(void *,_TOKEN_USER * *)
0x1800dbf25  mov     esi, 1
0x1800dbf2a  test    eax, eax
0x1800dbf2c  js      loc_1800DC022
0x1800dbf32  lea     rdx, [rbp+var_10]; struct _TOKEN_USER **
0x1800dbf36  mov     rcx, r12; TokenHandle
0x1800dbf39  call    ?_LUAGetUserFromToken@@YAJPEAXPEAPEAU_TOKEN_USER@@@Z; _LUAGetUserFromToken(void *,_TOKEN_USER * *)
0x1800dbf3e  mov     rbx, [rbp+var_10]
0x1800dbf42  mov     rdi, [rbp+hMem]
0x1800dbf46  test    eax, eax
0x1800dbf48  js      loc_1800DC026
0x1800dbf4e  mov     rdx, [rbx]; pSid2
0x1800dbf51  mov     rcx, [rdi]; pSid1
0x1800dbf54  call    cs:__imp_EqualSid
0x1800dbf5a  test    eax, eax
0x1800dbf5c  jz      short loc_1800DBF66
0x1800dbf5e  mov     r13d, esi
0x1800dbf61  jmp     loc_1800DC026
0x1800dbf66  call    LUAIsShadowAdminEnabled
0x1800dbf6b  test    eax, eax
0x1800dbf6d  jz      loc_1800DC026
0x1800dbf73  lea     r8, [rbp+arg_10]
0x1800dbf77  mov     rcx, r15; TokenHandle
0x1800dbf7a  lea     rdx, [rbp+arg_18]
0x1800dbf7e  call    LUAIsElevatedToken
0x1800dbf83  test    eax, eax
0x1800dbf85  js      loc_1800DC026
0x1800dbf8b  cmp     [rbp+arg_10], r13d
0x1800dbf8f  jz      loc_1800DC026
0x1800dbf95  lea     rax, [rbp+var_20]
0x1800dbf99  mov     r9d, 8; TokenInformationLength
0x1800dbf9f  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800dbfa3  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x1800dbfa8  lea     edx, [r9+0Bh]; TokenInformationClass
0x1800dbfac  cmp     [rbp+arg_18], r13d
0x1800dbfb0  jz      short loc_1800DBFF5
0x1800dbfb2  mov     rcx, r15; TokenHandle
0x1800dbfb5  call    cs:__imp_NtQueryInformationToken
0x1800dbfbb  test    eax, eax
0x1800dbfbd  js      short loc_1800DC026
0x1800dbfbf  mov     rcx, rdi; hMem
0x1800dbfc2  call    cs:__imp_LocalFree
0x1800dbfc8  mov     rcx, [rbp+TokenInformation]; TokenHandle
0x1800dbfcc  lea     rdx, [rbp+hMem]; struct _TOKEN_USER **
0x1800dbfd0  mov     [rbp+hMem], r13
0x1800dbfd4  call    ?_LUAGetUserFromToken@@YAJPEAXPEAPEAU_TOKEN_USER@@@Z; _LUAGetUserFromToken(void *,_TOKEN_USER * *)
0x1800dbfd9  mov     rdi, [rbp+hMem]
0x1800dbfdd  test    eax, eax
0x1800dbfdf  js      short loc_1800DC026
0x1800dbfe1  mov     rdx, [rbx]; pSid2
0x1800dbfe4  mov     rcx, [rdi]; pSid1
0x1800dbfe7  call    cs:__imp_EqualSid
0x1800dbfed  test    eax, eax
0x1800dbfef  cmovnz  r14d, esi
0x1800dbff3  jmp     short loc_1800DC026
0x1800dbff5  mov     rcx, r12; TokenHandle
0x1800dbff8  call    cs:__imp_NtQueryInformationToken
0x1800dbffe  test    eax, eax
0x1800dc000  js      short loc_1800DC026
0x1800dc002  mov     rcx, rbx; hMem
0x1800dc005  call    cs:__imp_LocalFree
0x1800dc00b  mov     rcx, [rbp+TokenInformation]; TokenHandle
0x1800dc00f  lea     rdx, [rbp+var_10]; struct _TOKEN_USER **
0x1800dc013  mov     [rbp+var_10], r13
0x1800dc017  call    ?_LUAGetUserFromToken@@YAJPEAXPEAPEAU_TOKEN_USER@@@Z; _LUAGetUserFromToken(void *,_TOKEN_USER * *)
0x1800dc01c  mov     rbx, [rbp+var_10]
0x1800dc020  jmp     short loc_1800DBFDD
0x1800dc022  mov     rdi, [rbp+hMem]
0x1800dc026  mov     rcx, [rbp+TokenInformation]; hObject
0x1800dc02a  test    rcx, rcx
0x1800dc02d  jz      short loc_1800DC035
0x1800dc02f  call    cs:__imp_CloseHandle
0x1800dc035  test    rdi, rdi
0x1800dc038  jz      short loc_1800DC043
0x1800dc03a  mov     rcx, rdi; hMem
0x1800dc03d  call    cs:__imp_LocalFree
0x1800dc043  test    rbx, rbx
0x1800dc046  jz      short loc_1800DC051
0x1800dc048  mov     rcx, rbx; hMem
0x1800dc04b  call    cs:__imp_LocalFree
0x1800dc051  test    r13d, r13d
0x1800dc054  jnz     short loc_1800DC05D
0x1800dc056  test    r14d, r14d
0x1800dc059  jnz     short loc_1800DC05D
0x1800dc05b  xor     esi, esi
0x1800dc05d  mov     eax, esi
0x1800dc05f  mov     rbx, [rsp+50h+arg_0]
0x1800dc067  add     rsp, 50h
0x1800dc06b  pop     r15
0x1800dc06d  pop     r14
0x1800dc06f  pop     r13
0x1800dc071  pop     r12
0x1800dc073  pop     rdi
0x1800dc074  pop     rsi
0x1800dc075  pop     rbp
0x1800dc076  retn
```
