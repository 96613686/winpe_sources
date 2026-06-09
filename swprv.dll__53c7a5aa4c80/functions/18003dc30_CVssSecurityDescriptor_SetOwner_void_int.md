# CVssSecurityDescriptor::SetOwner(void *,int)

- ea: `0x18003dc30`
- end: `0x18003dd32`
- name: `?SetOwner@CVssSecurityDescriptor@@QEAAJPEAXH@Z`
- size: `258`
- prototype: `int(CVssSecurityDescriptor *__hidden this, void *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18003ced0`

## callees

- `0x180001674`
- `0x180001af0`
- `0x18003dc30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dc57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dccc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dcf7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dc57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dccc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dcf7`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18003dcc2`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18003dcc2`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18003dc4d`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18003dced`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18003dc4d`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18003dced`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003dc94`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003dc94`

## pseudocode

```c
int __fastcall CVssSecurityDescriptor::SetOwner(CVssSecurityDescriptor *this, void *a2)
{
  int result; // eax
  void *v5; // rcx
  DWORD LengthSid; // esi
  void *v7; // rax
  signed int LastError; // eax
  unsigned int v9; // ebx
  signed int v10; // eax

  if ( SetSecurityDescriptorOwner(*(PSECURITY_DESCRIPTOR *)this, 0, 0) )
  {
    v5 = (void *)*((_QWORD *)this + 1);
    if ( v5 )
    {
      operator delete(v5);
      *((_QWORD *)this + 1) = 0;
    }
    if ( a2 )
    {
      LengthSid = GetLengthSid(a2);
      v7 = operator new[](LengthSid, (const struct std::nothrow_t *)&std::nothrow);
      *((_QWORD *)this + 1) = v7;
      if ( !v7 )
        return -2147024882;
      if ( !CopySid(LengthSid, v7, a2) )
      {
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
LABEL_16:
        operator delete(*((void **)this + 1));
        result = v9;
        *((_QWORD *)this + 1) = 0;
        return result;
      }
      if ( !SetSecurityDescriptorOwner(*(PSECURITY_DESCRIPTOR *)this, *((PSID *)this + 1), 0) )
      {
        v10 = GetLastError();
        if ( v10 > 0 )
          v10 = (unsigned __int16)v10 | 0x80070000;
        v9 = v10;
        goto LABEL_16;
      }
    }
    return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18003dc30  mov     [rsp+arg_0], rbx
0x18003dc35  mov     [rsp+arg_8], rsi
0x18003dc3a  push    rdi
0x18003dc3b  sub     rsp, 20h
0x18003dc3f  mov     rbx, rdx
0x18003dc42  mov     rdi, rcx
0x18003dc45  mov     rcx, [rcx]; pSecurityDescriptor
0x18003dc48  xor     edx, edx; pOwner
0x18003dc4a  xor     r8d, r8d; bOwnerDefaulted
0x18003dc4d  call    cs:__imp_SetSecurityDescriptorOwner
0x18003dc53  test    eax, eax
0x18003dc55  jnz     short loc_18003DC72
0x18003dc57  call    cs:__imp_GetLastError
0x18003dc5d  test    eax, eax
0x18003dc5f  jle     loc_18003DD22
0x18003dc65  movzx   eax, ax
0x18003dc68  or      eax, 80070000h
0x18003dc6d  jmp     loc_18003DD22
0x18003dc72  mov     rcx, [rdi+8]; Block
0x18003dc76  test    rcx, rcx
0x18003dc79  jz      short loc_18003DC88
0x18003dc7b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003dc80  mov     qword ptr [rdi+8], 0
0x18003dc88  test    rbx, rbx
0x18003dc8b  jz      loc_18003DD20
0x18003dc91  mov     rcx, rbx; pSid
0x18003dc94  call    cs:__imp_GetLengthSid
0x18003dc9a  mov     ecx, eax; unsigned __int64
0x18003dc9c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003dca3  mov     esi, eax
0x18003dca5  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003dcaa  mov     [rdi+8], rax
0x18003dcae  test    rax, rax
0x18003dcb1  jnz     short loc_18003DCBA
0x18003dcb3  mov     eax, 8007000Eh
0x18003dcb8  jmp     short loc_18003DD22
0x18003dcba  mov     r8, rbx; pSourceSid
0x18003dcbd  mov     rdx, rax; pDestinationSid
0x18003dcc0  mov     ecx, esi; nDestinationSidLength
0x18003dcc2  call    cs:__imp_CopySid
0x18003dcc8  test    eax, eax
0x18003dcca  jnz     short loc_18003DCE3
0x18003dccc  call    cs:__imp_GetLastError
0x18003dcd2  mov     ebx, eax
0x18003dcd4  test    eax, eax
0x18003dcd6  jle     short loc_18003DD0B
0x18003dcd8  movzx   ebx, ax
0x18003dcdb  or      ebx, 80070000h
0x18003dce1  jmp     short loc_18003DD0B
0x18003dce3  mov     rdx, [rdi+8]; pOwner
0x18003dce7  xor     r8d, r8d; bOwnerDefaulted
0x18003dcea  mov     rcx, [rdi]; pSecurityDescriptor
0x18003dced  call    cs:__imp_SetSecurityDescriptorOwner
0x18003dcf3  test    eax, eax
0x18003dcf5  jnz     short loc_18003DD20
0x18003dcf7  call    cs:__imp_GetLastError
0x18003dcfd  test    eax, eax
0x18003dcff  jle     short loc_18003DD09
0x18003dd01  movzx   eax, ax
0x18003dd04  or      eax, 80070000h
0x18003dd09  mov     ebx, eax
0x18003dd0b  mov     rcx, [rdi+8]; Block
0x18003dd0f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003dd14  mov     eax, ebx
0x18003dd16  mov     qword ptr [rdi+8], 0
0x18003dd1e  jmp     short loc_18003DD22
0x18003dd20  xor     eax, eax
0x18003dd22  mov     rbx, [rsp+28h+arg_0]
0x18003dd27  mov     rsi, [rsp+28h+arg_8]
0x18003dd2c  add     rsp, 20h
0x18003dd30  pop     rdi
0x18003dd31  retn
```
