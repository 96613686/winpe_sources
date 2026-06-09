# InitializeDefaultSecurityDescriptor(void)

- ea: `0x180095a30`
- end: `0x180095b8a`
- name: `?InitializeDefaultSecurityDescriptor@@YAJXZ`
- size: `346`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1800258b4`

## callees

- `0x180010244`
- `0x180023020`
- `0x180023a40`
- `0x180095a30`
- `0x1800ceda0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095abe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095abe`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180095b49`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180095b49`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180095b2c`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180095b2c`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180095b14`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180095b14`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180095aae`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180095aae`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180095a6b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180095a6b`

## pseudocode

```c
__int64 InitializeDefaultSecurityDescriptor(void)
{
  DWORD v0; // ebx
  struct _ACL *v1; // rsi
  void *v2; // rdi
  DWORD LastError; // eax
  unsigned int v4; // ebx
  _DWORD pSid[4]; // [rsp+20h] [rbp-28h] BYREF

  pSid[0] = 257;
  pSid[1] = 83886080;
  pSid[2] = 7;
  v0 = GetLengthSid(pSid) + 16;
  v1 = (struct _ACL *)AllocWrapper(v0);
  if ( v1 )
  {
    v2 = AllocWrapper(0x28u);
    if ( v2 )
    {
      if ( InitializeAcl(v1, v0, 2u)
        && AddAccessAllowedAce(v1, 2u, 0x80000000, pSid)
        && InitializeSecurityDescriptor(v2, 1u)
        && SetSecurityDescriptorDacl(v2, 1, v1, 0) )
      {
        LastError = RpcpNormalizeSecurityDescriptor(v2, 1u, &gDefaultSecurityDescriptor);
      }
      else
      {
        LastError = GetLastError();
      }
      v4 = LastError;
    }
    else
    {
      v4 = 14;
    }
    FreeWrapper(v1);
    if ( v2 )
      FreeWrapper(v2);
  }
  else
  {
    return 14;
  }
  return v4;
}

```

## disassembly

```asm
0x180095a30  mov     [rsp+arg_0], rbx
0x180095a35  mov     [rsp+arg_8], rsi
0x180095a3a  push    rdi
0x180095a3b  sub     rsp, 40h
0x180095a3f  mov     rax, cs:__security_cookie
0x180095a46  xor     rax, rsp
0x180095a49  mov     [rsp+48h+var_18], rax
0x180095a4e  lea     rcx, [rsp+48h+pSid]; pSid
0x180095a53  mov     [rsp+48h+pSid], 101h
0x180095a5b  mov     [rsp+48h+var_24], 5000000h
0x180095a63  mov     [rsp+48h+var_20], 7
0x180095a6b  call    cs:__imp_GetLengthSid
0x180095a72  nop     dword ptr [rax+rax+00h]
0x180095a77  lea     ebx, [rax+10h]
0x180095a7a  mov     ecx, ebx; dwBytes
0x180095a7c  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x180095a81  mov     rsi, rax
0x180095a84  test    rax, rax
0x180095a87  jz      loc_180095B76
0x180095a8d  mov     ecx, 28h ; '('; dwBytes
0x180095a92  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x180095a97  mov     rdi, rax
0x180095a9a  test    rax, rax
0x180095a9d  jz      loc_180095B80
0x180095aa3  mov     r8d, 2; dwAclRevision
0x180095aa9  mov     edx, ebx; nAclLength
0x180095aab  mov     rcx, rsi; pAcl
0x180095aae  call    cs:__imp_InitializeAcl
0x180095ab5  nop     dword ptr [rax+rax+00h]
0x180095aba  test    eax, eax
0x180095abc  jnz     short loc_180095B01
0x180095abe  call    cs:__imp_GetLastError
0x180095ac5  nop     dword ptr [rax+rax+00h]
0x180095aca  mov     ebx, eax
0x180095acc  mov     rcx, rsi; lpMem
0x180095acf  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x180095ad4  test    rdi, rdi
0x180095ad7  jz      short loc_180095AE1
0x180095ad9  mov     rcx, rdi; lpMem
0x180095adc  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x180095ae1  mov     eax, ebx
0x180095ae3  mov     rcx, [rsp+48h+var_18]
0x180095ae8  xor     rcx, rsp; StackCookie
0x180095aeb  call    __security_check_cookie
0x180095af0  mov     rbx, [rsp+48h+arg_0]
0x180095af5  mov     rsi, [rsp+48h+arg_8]
0x180095afa  add     rsp, 40h
0x180095afe  pop     rdi
0x180095aff  retn
0x180095b01  lea     r9, [rsp+48h+pSid]; pSid
0x180095b06  mov     edx, 2; dwAceRevision
0x180095b0b  mov     r8d, 80000000h; AccessMask
0x180095b11  mov     rcx, rsi; pAcl
0x180095b14  call    cs:__imp_AddAccessAllowedAce
0x180095b1b  nop     dword ptr [rax+rax+00h]
0x180095b20  test    eax, eax
0x180095b22  jz      short loc_180095ABE
0x180095b24  mov     edx, 1; dwRevision
0x180095b29  mov     rcx, rdi; pSecurityDescriptor
0x180095b2c  call    cs:__imp_InitializeSecurityDescriptor
0x180095b33  nop     dword ptr [rax+rax+00h]
0x180095b38  test    eax, eax
0x180095b3a  jz      short loc_180095ABE
0x180095b3c  xor     r9d, r9d; bDaclDefaulted
0x180095b3f  mov     r8, rsi; pDacl
0x180095b42  mov     rcx, rdi; pSecurityDescriptor
0x180095b45  lea     edx, [r9+1]; bDaclPresent
0x180095b49  call    cs:__imp_SetSecurityDescriptorDacl
0x180095b50  nop     dword ptr [rax+rax+00h]
0x180095b55  test    eax, eax
0x180095b57  jz      loc_180095ABE
0x180095b5d  lea     r8, ?gDefaultSecurityDescriptor@@3PEAXEA; void **
0x180095b64  mov     edx, 1; AutoInheritFlags
0x180095b69  mov     rcx, rdi; CreatorDescriptor
0x180095b6c  call    ?RpcpNormalizeSecurityDescriptor@@YAJPEAXKPEAPEAX@Z; RpcpNormalizeSecurityDescriptor(void *,ulong,void * *)
0x180095b71  jmp     loc_180095ACA
0x180095b76  mov     ebx, 0Eh
0x180095b7b  jmp     loc_180095AE1
0x180095b80  mov     ebx, 0Eh
0x180095b85  jmp     loc_180095ACC
```
