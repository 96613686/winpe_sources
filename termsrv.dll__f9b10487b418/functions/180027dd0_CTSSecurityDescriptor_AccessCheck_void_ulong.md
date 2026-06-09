# CTSSecurityDescriptor::AccessCheck(void *,ulong)

- ea: `0x180027dd0`
- end: `0x180027e82`
- name: `?AccessCheck@CTSSecurityDescriptor@@QEAAJPEAXK@Z`
- size: `178`
- prototype: `__int64 __fastcall(CTSSecurityDescriptor *__hidden this, HANDLE hToken, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007e380`

## callees

- `0x18000a210`
- `0x18000f540`
- `0x180027dd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027e12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027e41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027e12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027e41`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180027df2`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180027df2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180027e08`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180027e08`

## string_xrefs

- `0x180027e5a`: `ImpersonateLoggedOnUser failed: 0x%x in %s`
- `0x180027e61`: `CTSSecurityDescriptor::AccessCheck`
- `0x180027e38`: `this->AccessCheck failed: 0x%x in %s`

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
0x180027dd0  mov     [rsp+arg_0], rbx
0x180027dd5  push    rdi
0x180027dd6  sub     rsp, 20h
0x180027dda  mov     ebx, r8d
0x180027ddd  mov     rdi, rcx
0x180027de0  test    rdx, rdx
0x180027de3  jnz     short loc_180027DEF
0x180027de5  mov     ebx, 80070057h
0x180027dea  jmp     loc_180027E75
0x180027def  mov     rcx, rdx; hToken
0x180027df2  call    cs:__imp_ImpersonateLoggedOnUser
0x180027df8  test    eax, eax
0x180027dfa  jz      short loc_180027E41
0x180027dfc  mov     edx, ebx; unsigned int
0x180027dfe  mov     rcx, rdi; this
0x180027e01  call    ?AccessCheck@CTSSecurityDescriptor@@QEAAJK@Z; CTSSecurityDescriptor::AccessCheck(ulong)
0x180027e06  mov     ebx, eax
0x180027e08  call    cs:__imp_RevertToSelf
0x180027e0e  test    eax, eax
0x180027e10  jnz     short loc_180027E34
0x180027e12  call    cs:__imp_GetLastError
0x180027e18  mov     ebx, eax
0x180027e1a  test    eax, eax
0x180027e1c  jle     short loc_180027E27
0x180027e1e  movzx   ebx, ax
0x180027e21  or      ebx, 80070000h
0x180027e27  test    ebx, ebx
0x180027e29  jns     short loc_180027E75
0x180027e2b  lea     rdx, aReverttoselfFa; "RevertToSelf failed: 0x%x in %s"
0x180027e32  jmp     short loc_180027E61
0x180027e34  test    ebx, ebx
0x180027e36  jns     short loc_180027E75
0x180027e38  lea     rdx, aThisAccesschec; "this->AccessCheck failed: 0x%x in %s"
0x180027e3f  jmp     short loc_180027E61
0x180027e41  call    cs:__imp_GetLastError
0x180027e47  mov     ebx, eax
0x180027e49  test    eax, eax
0x180027e4b  jle     short loc_180027E56
0x180027e4d  movzx   ebx, ax
0x180027e50  or      ebx, 80070000h
0x180027e56  test    ebx, ebx
0x180027e58  jns     short loc_180027E75
0x180027e5a  lea     rdx, aImpersonatelog; "ImpersonateLoggedOnUser failed: 0x%x in"...
0x180027e61  lea     r9, aCtssecuritydes; "CTSSecurityDescriptor::AccessCheck"
0x180027e68  mov     r8d, ebx
0x180027e6b  mov     ecx, 8; int
0x180027e70  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180027e75  mov     eax, ebx
0x180027e77  mov     rbx, [rsp+28h+arg_0]
0x180027e7c  add     rsp, 20h
0x180027e80  pop     rdi
0x180027e81  retn
```
