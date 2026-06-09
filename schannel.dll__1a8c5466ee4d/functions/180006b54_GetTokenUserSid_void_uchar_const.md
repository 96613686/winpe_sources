# GetTokenUserSid(void *,uchar * const)

- ea: `0x180006b54`
- end: `0x180006bf3`
- name: `?GetTokenUserSid@@YAHPEAXQEAE@Z`
- size: `159`
- prototype: `int(void *, unsigned __int8 *const)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800069b0`
- `0x180064090`
- `0x180072b68`

## callees

- `0x180006b54`
- `0x1800597b0`
- `0x180088a54`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006b9c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006b9c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180006bad`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180006bad`

## pseudocode

```c
__int64 __fastcall GetTokenUserSid(void *a1, unsigned __int8 *const a2)
{
  unsigned int v3; // ebx
  DWORD LengthSid; // eax
  DWORD ReturnLength[4]; // [rsp+30h] [rbp-88h] BYREF
  void *TokenInformation; // [rsp+40h] [rbp-78h] BYREF

  ReturnLength[0] = 0;
  if ( a1 )
  {
    v3 = GetTokenInformation(a1, TokenUser, &TokenInformation, 0x54u, ReturnLength);
    if ( !v3 )
      return v3;
    LengthSid = GetLengthSid(TokenInformation);
    ReturnLength[0] = LengthSid;
    if ( LengthSid <= 0x44 )
    {
      memcpy_0(a2, TokenInformation, LengthSid);
      return v3;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180006b54  mov     [rsp+arg_10], rbx
0x180006b59  push    rdi
0x180006b5a  sub     rsp, 0B0h
0x180006b61  mov     rax, cs:__security_cookie
0x180006b68  xor     rax, rsp
0x180006b6b  mov     [rsp+0B8h+var_18], rax
0x180006b73  mov     [rsp+0B8h+var_88], 0
0x180006b7b  mov     rdi, rdx
0x180006b7e  test    rcx, rcx
0x180006b81  jz      short loc_180006BEF
0x180006b83  mov     r9d, 54h ; 'T'; TokenInformationLength
0x180006b89  lea     rax, [rsp+0B8h+var_88]
0x180006b8e  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x180006b93  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x180006b98  lea     edx, [r9-53h]; TokenInformationClass
0x180006b9c  call    cs:__imp_GetTokenInformation
0x180006ba2  mov     ebx, eax
0x180006ba4  test    eax, eax
0x180006ba6  jz      short loc_180006BCC
0x180006ba8  mov     rcx, [rsp+0B8h+TokenInformation]; pSid
0x180006bad  call    cs:__imp_GetLengthSid
0x180006bb3  mov     [rsp+0B8h+var_88], eax
0x180006bb7  cmp     eax, 44h ; 'D'
0x180006bba  ja      short loc_180006BEF
0x180006bbc  mov     rdx, [rsp+0B8h+TokenInformation]; Src
0x180006bc1  mov     rcx, rdi; void *
0x180006bc4  mov     r8d, eax; Size
0x180006bc7  call    memcpy_0
0x180006bcc  mov     eax, ebx
0x180006bce  mov     rcx, [rsp+0B8h+var_18]
0x180006bd6  xor     rcx, rsp; StackCookie
0x180006bd9  call    __security_check_cookie
0x180006bde  mov     rbx, [rsp+0B8h+arg_10]
0x180006be6  add     rsp, 0B0h
0x180006bed  pop     rdi
0x180006bee  retn
0x180006bef  xor     eax, eax
0x180006bf1  jmp     short loc_180006BCE
```
