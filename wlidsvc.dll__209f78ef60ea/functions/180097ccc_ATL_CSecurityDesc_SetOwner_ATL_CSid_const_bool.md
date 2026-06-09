# ATL::CSecurityDesc::SetOwner(ATL::CSid const &,bool)

- ea: `0x180097ccc`
- end: `0x180097dcb`
- name: `?SetOwner@CSecurityDesc@ATL@@QEAAXAEBVCSid@2@_N@Z`
- size: `255`
- prototype: `void __fastcall(ATL::CSecurityDesc *__hidden this, const struct ATL::CSid *, bool)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180097894`

## callees

- `0x18003bcf0`
- `0x18007c2f4`
- `0x18007c408`
- `0x18008b65c`
- `0x180097ccc`
- `0x1800e8f24`
- `0x1800e962c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180097da0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180097dbd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180097da0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180097dbd`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180097d5c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180097d5c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x180097d13`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x180097d13`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180097d7d`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180097d7d`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180097d91`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180097d91`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180097d52`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180097d52`

## pseudocode

```c
void __fastcall ATL::CSecurityDesc::SetOwner(PSECURITY_DESCRIPTOR *this, const struct ATL::CSid *a2, char a3)
{
  PSECURITY_DESCRIPTOR v5; // rcx
  char *v6; // rsi
  DWORD LengthSid; // ebp
  void *v8; // rax
  void *v9; // rdi
  int Error; // ebx
  PSID pOwner; // [rsp+40h] [rbp+8h] BYREF
  WINBOOL bOwnerDefaulted; // [rsp+50h] [rbp+18h] BYREF

  LOBYTE(bOwnerDefaulted) = a3;
  if ( this[1] )
    ATL::CSecurityDesc::MakeAbsolute((ATL::CSecurityDesc *)this);
  v5 = this[1];
  pOwner = 0;
  if ( v5 )
  {
    bOwnerDefaulted = 0;
    if ( !GetSecurityDescriptorOwner(v5, &pOwner, &bOwnerDefaulted) )
      ATL::AtlThrowLastWin32();
  }
  else
  {
    ATL::CSecurityDesc::AllocateAndInitializeSecurityDescriptor((ATL::CSecurityDesc *)this);
    pOwner = 0;
  }
  if ( !ATL::CSid::IsValid(a2) )
    ATL::AtlThrowImpl(-2147467259);
  v6 = (char *)a2 + 8;
  LengthSid = GetLengthSid((char *)a2 + 8);
  v8 = malloc(LengthSid);
  v9 = v8;
  if ( !v8 )
    ATL::AtlThrowImpl(-2147024882);
  if ( !CopySid(LengthSid, v8, v6) || !SetSecurityDescriptorOwner(this[1], v9, 0) )
  {
    Error = ATL::AtlHresultFromLastError();
    free(v9);
    ATL::AtlThrowImpl(Error);
  }
  free(pOwner);
}

```

## disassembly

```asm
0x180097ccc  mov     [rsp+arg_8], rbx
0x180097cd1  mov     byte ptr [rsp+bOwnerDefaulted], r8b
0x180097cd6  push    rbp
0x180097cd7  push    rsi
0x180097cd8  push    rdi
0x180097cd9  sub     rsp, 20h
0x180097cdd  cmp     qword ptr [rcx+8], 0
0x180097ce2  mov     rdi, rdx
0x180097ce5  mov     rbx, rcx
0x180097ce8  jz      short loc_180097CEF
0x180097cea  call    ?MakeAbsolute@CSecurityDesc@ATL@@QEAAXXZ; ATL::CSecurityDesc::MakeAbsolute(void)
0x180097cef  mov     rcx, [rbx+8]; pSecurityDescriptor
0x180097cf3  mov     [rsp+38h+pOwner], 0
0x180097cfc  test    rcx, rcx
0x180097cff  jz      short loc_180097D23
0x180097d01  lea     r8, [rsp+38h+bOwnerDefaulted]; lpbOwnerDefaulted
0x180097d06  mov     [rsp+38h+bOwnerDefaulted], 0
0x180097d0e  lea     rdx, [rsp+38h+pOwner]; pOwner
0x180097d13  call    cs:__imp_GetSecurityDescriptorOwner
0x180097d19  test    eax, eax
0x180097d1b  jnz     short loc_180097D34
0x180097d1d  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x180097d23  mov     rcx, rbx; this
0x180097d26  call    ?AllocateAndInitializeSecurityDescriptor@CSecurityDesc@ATL@@IEAAXXZ; ATL::CSecurityDesc::AllocateAndInitializeSecurityDescriptor(void)
0x180097d2b  mov     [rsp+38h+pOwner], 0
0x180097d34  mov     rcx, rdi; this
0x180097d37  call    ?IsValid@CSid@ATL@@QEBA_NXZ; ATL::CSid::IsValid(void)
0x180097d3c  test    al, al
0x180097d3e  jnz     short loc_180097D4B
0x180097d40  mov     ecx, 80004005h; int
0x180097d45  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180097d4b  lea     rsi, [rdi+8]
0x180097d4f  mov     rcx, rsi; pSid
0x180097d52  call    cs:__imp_GetLengthSid
0x180097d58  mov     ecx, eax; Size
0x180097d5a  mov     ebp, eax
0x180097d5c  call    cs:__imp_malloc
0x180097d62  mov     rdi, rax
0x180097d65  test    rax, rax
0x180097d68  jnz     short loc_180097D75
0x180097d6a  mov     ecx, 8007000Eh; int
0x180097d6f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180097d75  mov     r8, rsi; pSourceSid
0x180097d78  mov     rdx, rdi; pDestinationSid
0x180097d7b  mov     ecx, ebp; nDestinationSidLength
0x180097d7d  call    cs:__imp_CopySid
0x180097d83  test    eax, eax
0x180097d85  jz      short loc_180097DB3
0x180097d87  mov     rcx, [rbx+8]; pSecurityDescriptor
0x180097d8b  xor     r8d, r8d; bOwnerDefaulted
0x180097d8e  mov     rdx, rdi; pOwner
0x180097d91  call    cs:__imp_SetSecurityDescriptorOwner
0x180097d97  test    eax, eax
0x180097d99  jz      short loc_180097DB3
0x180097d9b  mov     rcx, [rsp+38h+pOwner]; Block
0x180097da0  call    cs:__imp_free
0x180097da6  mov     rbx, [rsp+38h+arg_8]
0x180097dab  add     rsp, 20h
0x180097daf  pop     rdi
0x180097db0  pop     rsi
0x180097db1  pop     rbp
0x180097db2  retn
0x180097db3  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180097db8  mov     rcx, rdi; Block
0x180097dbb  mov     ebx, eax
0x180097dbd  call    cs:__imp_free
0x180097dc3  mov     ecx, ebx; int
0x180097dc5  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
