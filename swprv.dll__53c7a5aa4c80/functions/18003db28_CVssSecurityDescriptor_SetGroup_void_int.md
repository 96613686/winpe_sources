# CVssSecurityDescriptor::SetGroup(void *,int)

- ea: `0x18003db28`
- end: `0x18003dc2a`
- name: `?SetGroup@CVssSecurityDescriptor@@QEAAJPEAXH@Z`
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
- `0x18003db28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003db4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dbc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dbef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003db4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dbc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dbef`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18003dbba`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18003dbba`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18003db45`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18003dbe5`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18003db45`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18003dbe5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003db8c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003db8c`

## pseudocode

```c
int __fastcall CVssSecurityDescriptor::SetGroup(CVssSecurityDescriptor *this, void *a2)
{
  int result; // eax
  void *v5; // rcx
  DWORD LengthSid; // esi
  void *v7; // rax
  signed int LastError; // eax
  unsigned int v9; // ebx
  signed int v10; // eax

  if ( SetSecurityDescriptorGroup(*(PSECURITY_DESCRIPTOR *)this, 0, 0) )
  {
    v5 = (void *)*((_QWORD *)this + 2);
    if ( v5 )
    {
      operator delete(v5);
      *((_QWORD *)this + 2) = 0;
    }
    if ( a2 )
    {
      LengthSid = GetLengthSid(a2);
      v7 = operator new[](LengthSid, (const struct std::nothrow_t *)&std::nothrow);
      *((_QWORD *)this + 2) = v7;
      if ( !v7 )
        return -2147024882;
      if ( !CopySid(LengthSid, v7, a2) )
      {
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
LABEL_16:
        operator delete(*((void **)this + 2));
        result = v9;
        *((_QWORD *)this + 2) = 0;
        return result;
      }
      if ( !SetSecurityDescriptorGroup(*(PSECURITY_DESCRIPTOR *)this, *((PSID *)this + 2), 0) )
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
0x18003db28  mov     [rsp+arg_0], rbx
0x18003db2d  mov     [rsp+arg_8], rsi
0x18003db32  push    rdi
0x18003db33  sub     rsp, 20h
0x18003db37  mov     rbx, rdx
0x18003db3a  mov     rdi, rcx
0x18003db3d  mov     rcx, [rcx]; pSecurityDescriptor
0x18003db40  xor     edx, edx; pGroup
0x18003db42  xor     r8d, r8d; bGroupDefaulted
0x18003db45  call    cs:__imp_SetSecurityDescriptorGroup
0x18003db4b  test    eax, eax
0x18003db4d  jnz     short loc_18003DB6A
0x18003db4f  call    cs:__imp_GetLastError
0x18003db55  test    eax, eax
0x18003db57  jle     loc_18003DC1A
0x18003db5d  movzx   eax, ax
0x18003db60  or      eax, 80070000h
0x18003db65  jmp     loc_18003DC1A
0x18003db6a  mov     rcx, [rdi+10h]; Block
0x18003db6e  test    rcx, rcx
0x18003db71  jz      short loc_18003DB80
0x18003db73  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003db78  mov     qword ptr [rdi+10h], 0
0x18003db80  test    rbx, rbx
0x18003db83  jz      loc_18003DC18
0x18003db89  mov     rcx, rbx; pSid
0x18003db8c  call    cs:__imp_GetLengthSid
0x18003db92  mov     ecx, eax; unsigned __int64
0x18003db94  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003db9b  mov     esi, eax
0x18003db9d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003dba2  mov     [rdi+10h], rax
0x18003dba6  test    rax, rax
0x18003dba9  jnz     short loc_18003DBB2
0x18003dbab  mov     eax, 8007000Eh
0x18003dbb0  jmp     short loc_18003DC1A
0x18003dbb2  mov     r8, rbx; pSourceSid
0x18003dbb5  mov     rdx, rax; pDestinationSid
0x18003dbb8  mov     ecx, esi; nDestinationSidLength
0x18003dbba  call    cs:__imp_CopySid
0x18003dbc0  test    eax, eax
0x18003dbc2  jnz     short loc_18003DBDB
0x18003dbc4  call    cs:__imp_GetLastError
0x18003dbca  mov     ebx, eax
0x18003dbcc  test    eax, eax
0x18003dbce  jle     short loc_18003DC03
0x18003dbd0  movzx   ebx, ax
0x18003dbd3  or      ebx, 80070000h
0x18003dbd9  jmp     short loc_18003DC03
0x18003dbdb  mov     rdx, [rdi+10h]; pGroup
0x18003dbdf  xor     r8d, r8d; bGroupDefaulted
0x18003dbe2  mov     rcx, [rdi]; pSecurityDescriptor
0x18003dbe5  call    cs:__imp_SetSecurityDescriptorGroup
0x18003dbeb  test    eax, eax
0x18003dbed  jnz     short loc_18003DC18
0x18003dbef  call    cs:__imp_GetLastError
0x18003dbf5  test    eax, eax
0x18003dbf7  jle     short loc_18003DC01
0x18003dbf9  movzx   eax, ax
0x18003dbfc  or      eax, 80070000h
0x18003dc01  mov     ebx, eax
0x18003dc03  mov     rcx, [rdi+10h]; Block
0x18003dc07  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003dc0c  mov     eax, ebx
0x18003dc0e  mov     qword ptr [rdi+10h], 0
0x18003dc16  jmp     short loc_18003DC1A
0x18003dc18  xor     eax, eax
0x18003dc1a  mov     rbx, [rsp+28h+arg_0]
0x18003dc1f  mov     rsi, [rsp+28h+arg_8]
0x18003dc24  add     rsp, 20h
0x18003dc28  pop     rdi
0x18003dc29  retn
```
