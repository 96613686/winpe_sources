# TOKEN_ENTRY::GetPrimaryToken(void)

- ea: `0x180021eb0`
- end: `0x180021f9d`
- name: `?GetPrimaryToken@TOKEN_ENTRY@@UEAAPEAXXZ`
- size: `237`
- prototype: `void *__fastcall(TOKEN_ENTRY *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180021eb0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180021f06`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180021f2a`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180021f06`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180021f2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021f3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021f3d`
- `iisutil!PuDbgPrint` at `0x180021f6e`
- `iisutil!PuDbgPrint` at `0x180021f6e`
- `iisutil!?WriteUnlock@CSmallSpinLock@@QEAAXXZ` at `0x180021f84`
- `iisutil!?WriteUnlock@CSmallSpinLock@@QEAAXXZ` at `0x180021f84`
- `iisutil!?WriteLock@CSmallSpinLock@@QEAAXXZ` at `0x180021eda`
- `iisutil!?WriteLock@CSmallSpinLock@@QEAAXXZ` at `0x180021eda`

## string_xrefs

- `0x180021f55`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`
- `0x180021f5c`: `DuplicateTokenEx failed, GetLastError = %lx\n`
- `0x180021f4a`: `TOKEN_ENTRY::GetPrimaryToken`

## pseudocode

```c
void *__fastcall TOKEN_ENTRY::GetPrimaryToken(HANDLE *this)
{
  void **phNewToken; // rbx
  CSmallSpinLock *v3; // rsi
  DWORD LastError; // eax

  phNewToken = this + 3;
  if ( !this[3] )
  {
    v3 = (CSmallSpinLock *)(this + 31);
    CSmallSpinLock::WriteLock((CSmallSpinLock *)(this + 31));
    if ( !*phNewToken )
    {
      if ( !DuplicateTokenEx(this[2], 0, 0, SecurityDelegation, TokenPrimary, phNewToken)
        && !DuplicateTokenEx(this[2], 0, 0, SecurityImpersonation, TokenPrimary, phNewToken)
        && (g_dwDebugFlags & 3) != 0 )
      {
        LastError = GetLastError();
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\common\\iislogon_lib\\iislogon.cxx",
          1199,
          "TOKEN_ENTRY::GetPrimaryToken",
          "DuplicateTokenEx failed, GetLastError = %lx\n",
          LastError);
      }
      if ( *phNewToken )
        *((_DWORD *)this + 65) |= 2u;
    }
    CSmallSpinLock::WriteUnlock(v3);
  }
  return *phNewToken;
}

```

## disassembly

```asm
0x180021eb0  mov     [rsp+arg_0], rbx
0x180021eb5  mov     [rsp+arg_8], rsi
0x180021eba  push    rdi
0x180021ebb  sub     rsp, 30h
0x180021ebf  lea     rbx, [rcx+18h]
0x180021ec3  mov     rdi, rcx
0x180021ec6  cmp     qword ptr [rbx], 0
0x180021eca  jnz     loc_180021F8A
0x180021ed0  lea     rsi, [rcx+0F8h]
0x180021ed7  mov     rcx, rsi
0x180021eda  call    cs:__imp_?WriteLock@CSmallSpinLock@@QEAAXXZ; CSmallSpinLock::WriteLock(void)
0x180021ee0  cmp     qword ptr [rbx], 0
0x180021ee4  jnz     loc_180021F81
0x180021eea  mov     rcx, [rdi+10h]; hExistingToken
0x180021eee  mov     r9d, 3; ImpersonationLevel
0x180021ef4  mov     [rsp+38h+phNewToken], rbx; phNewToken
0x180021ef9  xor     r8d, r8d; lpTokenAttributes
0x180021efc  xor     edx, edx; dwDesiredAccess
0x180021efe  mov     [rsp+38h+TokenType], 1; TokenType
0x180021f06  call    cs:__imp_DuplicateTokenEx
0x180021f0c  test    eax, eax
0x180021f0e  jnz     short loc_180021F74
0x180021f10  mov     rcx, [rdi+10h]; hExistingToken
0x180021f14  lea     r9d, [rax+2]; ImpersonationLevel
0x180021f18  mov     [rsp+38h+phNewToken], rbx; phNewToken
0x180021f1d  xor     r8d, r8d; lpTokenAttributes
0x180021f20  xor     edx, edx; dwDesiredAccess
0x180021f22  mov     [rsp+38h+TokenType], 1; TokenType
0x180021f2a  call    cs:__imp_DuplicateTokenEx
0x180021f30  test    eax, eax
0x180021f32  jnz     short loc_180021F74
0x180021f34  test    byte ptr cs:g_dwDebugFlags, 3
0x180021f3b  jz      short loc_180021F74
0x180021f3d  call    cs:__imp_GetLastError
0x180021f43  mov     rcx, cs:g_pDebug
0x180021f4a  lea     r9, aTokenEntryGetp; "TOKEN_ENTRY::GetPrimaryToken"
0x180021f51  mov     dword ptr [rsp+38h+phNewToken], eax
0x180021f55  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180021f5c  lea     rax, aDuplicatetoken; "DuplicateTokenEx failed, GetLastError ="...
0x180021f63  mov     r8d, 4AFh
0x180021f69  mov     qword ptr [rsp+38h+TokenType], rax
0x180021f6e  call    cs:__imp_PuDbgPrint
0x180021f74  cmp     qword ptr [rbx], 0
0x180021f78  jz      short loc_180021F81
0x180021f7a  or      dword ptr [rdi+104h], 2
0x180021f81  mov     rcx, rsi
0x180021f84  call    cs:__imp_?WriteUnlock@CSmallSpinLock@@QEAAXXZ; CSmallSpinLock::WriteUnlock(void)
0x180021f8a  mov     rax, [rbx]
0x180021f8d  mov     rbx, [rsp+38h+arg_0]
0x180021f92  mov     rsi, [rsp+38h+arg_8]
0x180021f97  add     rsp, 30h
0x180021f9b  pop     rdi
0x180021f9c  retn
```
