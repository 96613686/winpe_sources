# CTSSecurityDescriptor::AccessCheck(void *,ulong)

- ea: `0x1800294a0`
- end: `0x18002956b`
- name: `?AccessCheck@CTSSecurityDescriptor@@QEAAJPEAXK@Z`
- size: `203`
- prototype: `__int64 __fastcall(CTSSecurityDescriptor *__hidden this, HANDLE hToken, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180081a90`

## callees

- `0x180009940`
- `0x18000fbe0`
- `0x1800294a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800294ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029523`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800294ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029523`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800294c2`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800294c2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800294de`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800294de`

## string_xrefs

- `0x180029542`: `ImpersonateLoggedOnUser failed: 0x%x in %s`
- `0x180029549`: `CTSSecurityDescriptor::AccessCheck`
- `0x18002951a`: `this->AccessCheck failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CTSSecurityDescriptor::AccessCheck(CTSSecurityDescriptor *this, HANDLE hToken, unsigned int a3)
{
  signed int v5; // ebx
  signed int LastError; // eax
  signed int v7; // eax

  if ( hToken )
  {
    if ( ImpersonateLoggedOnUser(hToken) )
    {
      v5 = CTSSecurityDescriptor::AccessCheck(this, a3);
      if ( RevertToSelf() )
      {
        if ( v5 < 0 )
          _DbgPrintMessage(
            8,
            "this->AccessCheck failed: 0x%x in %s",
            (unsigned int)v5,
            "CTSSecurityDescriptor::AccessCheck");
      }
      else
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
        if ( v5 < 0 )
          _DbgPrintMessage(8, "RevertToSelf failed: 0x%x in %s", (unsigned int)v5, "CTSSecurityDescriptor::AccessCheck");
      }
    }
    else
    {
      v7 = GetLastError();
      v5 = v7;
      if ( v7 > 0 )
        v5 = (unsigned __int16)v7 | 0x80070000;
      if ( v5 < 0 )
        _DbgPrintMessage(
          8,
          "ImpersonateLoggedOnUser failed: 0x%x in %s",
          (unsigned int)v5,
          "CTSSecurityDescriptor::AccessCheck");
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800294a0  mov     [rsp+arg_0], rbx
0x1800294a5  push    rdi
0x1800294a6  sub     rsp, 20h
0x1800294aa  mov     ebx, r8d
0x1800294ad  mov     rdi, rcx
0x1800294b0  test    rdx, rdx
0x1800294b3  jnz     short loc_1800294BF
0x1800294b5  mov     ebx, 80070057h
0x1800294ba  jmp     loc_18002955D
0x1800294bf  mov     rcx, rdx; hToken
0x1800294c2  call    cs:__imp_ImpersonateLoggedOnUser
0x1800294c9  nop     dword ptr [rax+rax+00h]
0x1800294ce  test    eax, eax
0x1800294d0  jz      short loc_180029523
0x1800294d2  mov     edx, ebx; unsigned int
0x1800294d4  mov     rcx, rdi; this
0x1800294d7  call    ?AccessCheck@CTSSecurityDescriptor@@QEAAJK@Z; CTSSecurityDescriptor::AccessCheck(ulong)
0x1800294dc  mov     ebx, eax
0x1800294de  call    cs:__imp_RevertToSelf
0x1800294e5  nop     dword ptr [rax+rax+00h]
0x1800294ea  test    eax, eax
0x1800294ec  jnz     short loc_180029516
0x1800294ee  call    cs:__imp_GetLastError
0x1800294f5  nop     dword ptr [rax+rax+00h]
0x1800294fa  mov     ebx, eax
0x1800294fc  test    eax, eax
0x1800294fe  jle     short loc_180029509
0x180029500  movzx   ebx, ax
0x180029503  or      ebx, 80070000h
0x180029509  test    ebx, ebx
0x18002950b  jns     short loc_18002955D
0x18002950d  lea     rdx, aReverttoselfFa; "RevertToSelf failed: 0x%x in %s"
0x180029514  jmp     short loc_180029549
0x180029516  test    ebx, ebx
0x180029518  jns     short loc_18002955D
0x18002951a  lea     rdx, aThisAccesschec; "this->AccessCheck failed: 0x%x in %s"
0x180029521  jmp     short loc_180029549
0x180029523  call    cs:__imp_GetLastError
0x18002952a  nop     dword ptr [rax+rax+00h]
0x18002952f  mov     ebx, eax
0x180029531  test    eax, eax
0x180029533  jle     short loc_18002953E
0x180029535  movzx   ebx, ax
0x180029538  or      ebx, 80070000h
0x18002953e  test    ebx, ebx
0x180029540  jns     short loc_18002955D
0x180029542  lea     rdx, aImpersonatelog; "ImpersonateLoggedOnUser failed: 0x%x in"...
0x180029549  lea     r9, aCtssecuritydes; "CTSSecurityDescriptor::AccessCheck"
0x180029550  mov     r8d, ebx
0x180029553  mov     ecx, 8; int
0x180029558  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002955d  mov     eax, ebx
0x18002955f  mov     rbx, [rsp+28h+arg_0]
0x180029564  add     rsp, 20h
0x180029568  pop     rdi
0x180029569  retn
```
