# ATL::CSecurityDesc::SetOwner(ATL::CSid const &,bool)

- ea: `0x180045720`
- end: `0x18004581b`
- name: `?SetOwner@CSecurityDesc@ATL@@QEAAXAEBVCSid@2@_N@Z`
- size: `251`
- prototype: `void __fastcall(ATL::CSecurityDesc *__hidden this, const struct ATL::CSid *, bool)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800435fc`

## callees

- `0x180006d14`
- `0x180007598`
- `0x180010290`
- `0x180042458`
- `0x180042e4c`
- `0x180043b5c`
- `0x180043bec`
- `0x180045720`

## import_xrefs

- `msvcrt!malloc` at `0x1800457ab`
- `msvcrt!malloc` at `0x1800457ab`
- `msvcrt!free` at `0x1800457f0`
- `msvcrt!free` at `0x18004580d`
- `msvcrt!free` at `0x1800457f0`
- `msvcrt!free` at `0x18004580d`
- `ADVAPI32!CopySid` at `0x1800457cd`
- `ADVAPI32!CopySid` at `0x1800457cd`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x180045767`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x180045767`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x1800457e1`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x1800457e1`

## pseudocode

```c
void __fastcall ATL::CSecurityDesc::SetOwner(PSECURITY_DESCRIPTOR *this, const struct ATL::CSid *a2, char a3)
{
  PSECURITY_DESCRIPTOR v5; // rcx
  DWORD Length; // ebp
  void *v7; // rax
  void *v8; // rdi
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
  Length = ATL::CSid::GetLength(a2);
  v7 = malloc(Length);
  v8 = v7;
  if ( !v7 )
    ATL::AtlThrowImpl(-2147024882);
  if ( !CopySid(Length, v7, (char *)a2 + 8) || !SetSecurityDescriptorOwner(this[1], v8, 0) )
  {
    Error = ATL::AtlHresultFromLastError();
    free(v8);
    ATL::AtlThrowImpl(Error);
  }
  free(pOwner);
}

```

## disassembly

```asm
0x180045720  mov     [rsp+arg_8], rbx
0x180045725  mov     byte ptr [rsp+bOwnerDefaulted], r8b
0x18004572a  push    rbp
0x18004572b  push    rsi
0x18004572c  push    rdi
0x18004572d  sub     rsp, 20h
0x180045731  cmp     qword ptr [rcx+8], 0
0x180045736  mov     rsi, rdx
0x180045739  mov     rbx, rcx
0x18004573c  jz      short loc_180045743
0x18004573e  call    ?MakeAbsolute@CSecurityDesc@ATL@@QEAAXXZ; ATL::CSecurityDesc::MakeAbsolute(void)
0x180045743  mov     rcx, [rbx+8]; pSecurityDescriptor
0x180045747  mov     [rsp+38h+pOwner], 0
0x180045750  test    rcx, rcx
0x180045753  jz      short loc_180045777
0x180045755  lea     r8, [rsp+38h+bOwnerDefaulted]; lpbOwnerDefaulted
0x18004575a  mov     [rsp+38h+bOwnerDefaulted], 0
0x180045762  lea     rdx, [rsp+38h+pOwner]; pOwner
0x180045767  call    cs:__imp_GetSecurityDescriptorOwner
0x18004576d  test    eax, eax
0x18004576f  jnz     short loc_180045788
0x180045771  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x180045777  mov     rcx, rbx; this
0x18004577a  call    ?AllocateAndInitializeSecurityDescriptor@CSecurityDesc@ATL@@IEAAXXZ; ATL::CSecurityDesc::AllocateAndInitializeSecurityDescriptor(void)
0x18004577f  mov     [rsp+38h+pOwner], 0
0x180045788  mov     rcx, rsi; this
0x18004578b  call    ?IsValid@CSid@ATL@@QEBA_NXZ; ATL::CSid::IsValid(void)
0x180045790  test    al, al
0x180045792  jnz     short loc_18004579F
0x180045794  mov     ecx, 80004005h; int
0x180045799  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18004579f  mov     rcx, rsi; this
0x1800457a2  call    ?GetLength@CSid@ATL@@QEBAIXZ; ATL::CSid::GetLength(void)
0x1800457a7  mov     ecx, eax; Size
0x1800457a9  mov     ebp, eax
0x1800457ab  call    cs:__imp_malloc
0x1800457b1  mov     rdi, rax
0x1800457b4  test    rax, rax
0x1800457b7  jnz     short loc_1800457C4
0x1800457b9  mov     ecx, 8007000Eh; int
0x1800457be  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800457c4  lea     r8, [rsi+8]; pSourceSid
0x1800457c8  mov     rdx, rdi; pDestinationSid
0x1800457cb  mov     ecx, ebp; nDestinationSidLength
0x1800457cd  call    cs:__imp_CopySid
0x1800457d3  test    eax, eax
0x1800457d5  jz      short loc_180045803
0x1800457d7  mov     rcx, [rbx+8]; pSecurityDescriptor
0x1800457db  xor     r8d, r8d; bOwnerDefaulted
0x1800457de  mov     rdx, rdi; pOwner
0x1800457e1  call    cs:__imp_SetSecurityDescriptorOwner
0x1800457e7  test    eax, eax
0x1800457e9  jz      short loc_180045803
0x1800457eb  mov     rcx, [rsp+38h+pOwner]; Block
0x1800457f0  call    cs:__imp_free
0x1800457f6  mov     rbx, [rsp+38h+arg_8]
0x1800457fb  add     rsp, 20h
0x1800457ff  pop     rdi
0x180045800  pop     rsi
0x180045801  pop     rbp
0x180045802  retn
0x180045803  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180045808  mov     rcx, rdi; Block
0x18004580b  mov     ebx, eax
0x18004580d  call    cs:__imp_free
0x180045813  mov     ecx, ebx; int
0x180045815  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
