# _anonymous_namespace_::IsWizardUser

- ea: `0x180383294`
- end: `0x180383399`
- name: `_anonymous_namespace_::IsWizardUser`
- size: `261`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18038203c`

## callees

- `0x180026fe8`
- `0x180095f88`
- `0x18013d800`
- `0x18013f6e0`
- `0x1803831c8`
- `0x180383294`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803832f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803832f5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1803832bb`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1803832bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1803832a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1803832a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180383389`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180383389`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180383377`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180383377`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1803832e7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180383328`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1803832e7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180383328`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180383341`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180383341`

## pseudocode

```c
bool anonymous_namespace_::IsWizardUser()
{
  bool v0; // bl
  HANDLE CurrentProcess; // rax
  void **v2; // rdi
  void *v3; // rcx
  const unsigned __int16 *v4; // rbx
  DWORD TokenInformationLength; // [rsp+50h] [rbp+20h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp+28h] BYREF
  LPWSTR StringSid; // [rsp+60h] [rbp+30h] BYREF

  v0 = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    TokenInformationLength = 0;
    if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) && GetLastError() == 122 )
    {
      v2 = (void **)operator new[](TokenInformationLength);
      if ( GetTokenInformation(TokenHandle, TokenUser, v2, TokenInformationLength, &TokenInformationLength) )
      {
        v3 = *v2;
        StringSid = 0;
        if ( ConvertSidToStringSidW(v3, &StringSid) )
        {
          v4 = StringSid;
          v0 = IsUserOOBE() || IsCredentialReset() || IsCamCxhOnlyUser(v4);
          LocalFree(StringSid);
        }
      }
      operator delete(v2);
    }
    CloseHandle(TokenHandle);
  }
  return v0;
}

```

## disassembly

```asm
0x180383294  push    rbp
0x180383296  push    rbx
0x180383297  push    rdi
0x180383298  mov     rbp, rsp
0x18038329b  sub     rsp, 30h
0x18038329f  xor     bl, bl
0x1803832a1  mov     [rbp+TokenHandle], 0
0x1803832a9  call    cs:__imp_GetCurrentProcess
0x1803832af  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1803832b3  mov     edx, 8; DesiredAccess
0x1803832b8  mov     rcx, rax; ProcessHandle
0x1803832bb  call    cs:__imp_OpenProcessToken
0x1803832c1  test    eax, eax
0x1803832c3  jz      loc_18038338F
0x1803832c9  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1803832cd  lea     rax, [rbp+TokenInformationLength]
0x1803832d1  xor     r9d, r9d; TokenInformationLength
0x1803832d4  mov     [rbp+TokenInformationLength], 0
0x1803832db  xor     r8d, r8d; TokenInformation
0x1803832de  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1803832e3  lea     edx, [r9+1]; TokenInformationClass
0x1803832e7  call    cs:__imp_GetTokenInformation
0x1803832ed  test    eax, eax
0x1803832ef  jnz     loc_180383385
0x1803832f5  call    cs:__imp_GetLastError
0x1803832fb  cmp     eax, 7Ah ; 'z'
0x1803832fe  jnz     loc_180383385
0x180383304  mov     ecx, [rbp+TokenInformationLength]; unsigned __int64
0x180383307  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18038330c  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180383310  mov     rdi, rax
0x180383313  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180383317  lea     rax, [rbp+TokenInformationLength]
0x18038331b  mov     r8, rdi; TokenInformation
0x18038331e  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180383323  mov     edx, 1; TokenInformationClass
0x180383328  call    cs:__imp_GetTokenInformation
0x18038332e  test    eax, eax
0x180383330  jz      short loc_18038337D
0x180383332  mov     rcx, [rdi]; Sid
0x180383335  lea     rdx, [rbp+StringSid]; StringSid
0x180383339  mov     [rbp+StringSid], 0
0x180383341  call    cs:__imp_ConvertSidToStringSidW
0x180383347  test    eax, eax
0x180383349  jz      short loc_18038337D
0x18038334b  mov     rbx, [rbp+StringSid]
0x18038334f  call    ?IsUserOOBE@@YA_NXZ; IsUserOOBE(void)
0x180383354  test    al, al
0x180383356  jnz     short loc_180383371
0x180383358  call    ?IsCredentialReset@@YA_NXZ; IsCredentialReset(void)
0x18038335d  test    al, al
0x18038335f  jnz     short loc_180383371
0x180383361  mov     rcx, rbx; unsigned __int16 *
0x180383364  call    ?IsCamCxhOnlyUser@@YA_NPEBG@Z; IsCamCxhOnlyUser(ushort const *)
0x180383369  test    al, al
0x18038336b  jnz     short loc_180383371
0x18038336d  xor     bl, bl
0x18038336f  jmp     short loc_180383373
0x180383371  mov     bl, 1
0x180383373  mov     rcx, [rbp+StringSid]; hMem
0x180383377  call    cs:__imp_LocalFree
0x18038337d  mov     rcx, rdi; Block
0x180383380  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180383385  mov     rcx, [rbp+TokenHandle]; hObject
0x180383389  call    cs:__imp_CloseHandle
0x18038338f  mov     al, bl
0x180383391  add     rsp, 30h
0x180383395  pop     rdi
0x180383396  pop     rbx
0x180383397  pop     rbp
0x180383398  retn
```
