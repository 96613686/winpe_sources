# CThreadSecurityToken::Rollback(int,int)

- ea: `0x3839d52a0`
- end: `0x3839d5449`
- name: `?Rollback@CThreadSecurityToken@@QEAAJHH@Z`
- size: `425`
- prototype: `__int64 __fastcall(CThreadSecurityToken *__hidden this, int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x3839d48a0`

## callees

- `0x38391aed0`
- `0x3839d52a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x3839d532e`
- `KERNEL32!GetLastError` at `0x3839d53a4`
- `KERNEL32!GetLastError` at `0x3839d532e`
- `KERNEL32!GetLastError` at `0x3839d53a4`
- `ADVAPI32!RevertToSelf` at `0x3839d52ef`
- `ADVAPI32!RevertToSelf` at `0x3839d52ef`
- `ADVAPI32!SetThreadToken` at `0x3839d539a`
- `ADVAPI32!SetThreadToken` at `0x3839d539a`

## pseudocode

```c
__int64 __fastcall CThreadSecurityToken::Rollback(HANDLE *this, unsigned int a2, unsigned int a3)
{
  unsigned int v3; // ebx
  wchar_t *v5; // r8
  char *v6; // rcx
  __int64 v7; // rdx
  signed int LastError; // eax
  signed int v10; // eax

  v3 = 0;
  if ( *((_BYTE *)this + 8) )
  {
    if ( (bidGblFlags & 2) != 0 && `CThreadSecurityToken::Rollback'::`10'::_bidPtrSA_030_3286[0] )
      bidTraceW(
        `CThreadSecurityToken::Rollback'::`10'::_bidSrcFileA[0],
        3364864,
        `CThreadSecurityToken::Rollback'::`10'::_bidPtrSA_030_3286[0],
        a2);
    if ( !RevertToSelf() )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      if ( (bidGblFlags & 2) != 0 && `CThreadSecurityToken::Rollback'::`29'::_bidPtrSA_030_3297[0] )
      {
        bidTraceW(
          `CThreadSecurityToken::Rollback'::`29'::_bidSrcFileA[0],
          3376128,
          `CThreadSecurityToken::Rollback'::`29'::_bidPtrSA_030_3297[0],
          v3);
        return v3;
      }
      return v3;
    }
    if ( (bidGblFlags & 2) != 0 && `CThreadSecurityToken::Rollback'::`20'::_bidPtrSA_030_3291[0] )
    {
      v5 = `CThreadSecurityToken::Rollback'::`20'::_bidPtrSA_030_3291[0];
      v6 = `CThreadSecurityToken::Rollback'::`20'::_bidSrcFileA[0];
      v7 = 3369984;
LABEL_23:
      bidTraceW(v6, v7, v5, a3);
    }
  }
  else
  {
    if ( SetThreadToken(0, *this) )
    {
      if ( (bidGblFlags & 2) == 0 || !`CThreadSecurityToken::Rollback'::`49'::_bidPtrSA_030_3310[0] )
        return v3;
      v5 = `CThreadSecurityToken::Rollback'::`49'::_bidPtrSA_030_3310[0];
      v6 = `CThreadSecurityToken::Rollback'::`49'::_bidSrcFileA[0];
      v7 = 3389440;
      goto LABEL_23;
    }
    v10 = GetLastError();
    v3 = v10;
    if ( v10 > 0 )
      v3 = (unsigned __int16)v10 | 0x80070000;
    if ( (bidGblFlags & 2) != 0 && `CThreadSecurityToken::Rollback'::`40'::_bidPtrSA_030_3305[0] )
    {
      bidTraceW(
        `CThreadSecurityToken::Rollback'::`40'::_bidSrcFileA[0],
        3384320,
        `CThreadSecurityToken::Rollback'::`40'::_bidPtrSA_030_3305[0],
        v3);
      return v3;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x3839d52a0  mov     [rsp+arg_0], rbx
0x3839d52a5  mov     [rsp+arg_8], rsi
0x3839d52aa  push    rdi
0x3839d52ab  sub     rsp, 30h
0x3839d52af  xor     ebx, ebx
0x3839d52b1  mov     esi, r8d
0x3839d52b4  mov     edi, edx
0x3839d52b6  cmp     [rcx+8], bl
0x3839d52b9  jz      loc_3839D5395
0x3839d52bf  test    byte ptr cs:_bidGblFlags, 2
0x3839d52c6  jz      short loc_3839D52EF
0x3839d52c8  mov     rax, cs:?_bidPtrSA_030_3286@?9??Rollback@CThreadSecurityToken@@QEAAJHH@Z@4REBGEB; ushort const * const `CThreadSecurityToken::Rollback(int,int)'::`10'::_bidPtrSA_030_3286
0x3839d52cf  test    rax, rax
0x3839d52d2  jz      short loc_3839D52EF
0x3839d52d4  mov     r8, cs:?_bidPtrSA_030_3286@?9??Rollback@CThreadSecurityToken@@QEAAJHH@Z@4REBGEB; ushort const * const `CThreadSecurityToken::Rollback(int,int)'::`10'::_bidPtrSA_030_3286
0x3839d52db  mov     rcx, cs:?_bidSrcFileA@?9??Rollback@CThreadSecurityToken@@QEAAJHH@Z@4REBDEB; char const * const `CThreadSecurityToken::Rollback(int,int)'::`10'::_bidSrcFileA
0x3839d52e2  mov     r9d, edx
0x3839d52e5  mov     edx, 335800h
0x3839d52ea  call    _bidTraceW
0x3839d52ef  call    cs:__imp_RevertToSelf
0x3839d52f5  test    eax, eax
0x3839d52f7  jz      short loc_3839D532E
0x3839d52f9  test    byte ptr cs:_bidGblFlags, 2
0x3839d5300  jz      loc_3839D5437
0x3839d5306  mov     rax, cs:?_bidPtrSA_030_3291@?BE@??Rollback@CThreadSecurityToken@@QEAAJHH@Z@4REBGEB; ushort const * const `CThreadSecurityToken::Rollback(int,int)'::`20'::_bidPtrSA_030_3291
0x3839d530d  test    rax, rax
0x3839d5310  jz      loc_3839D5437
0x3839d5316  mov     r8, cs:?_bidPtrSA_030_3291@?BE@??Rollback@CThreadSecurityToken@@QEAAJHH@Z@4REBGEB; ushort const * const `CThreadSecurityToken::Rollback(int,int)'::`20'::_bidPtrSA_030_3291
0x3839d531d  mov     rcx, cs:?_bidSrcFileA@?BE@??Rollback@CThreadSecurityToken@@QEAAJHH@Z@4REBDEB; char const * const `CThreadSecurityToken::Rollback(int,int)'::`20'::_bidSrcFileA
0x3839d5324  mov     edx, 336C00h
0x3839d5329  jmp     loc_3839D542B
0x3839d532e  call    cs:__imp_GetLastError
0x3839d5334  mov     ebx, eax
0x3839d5336  test    eax, eax
0x3839d5338  jle     short loc_3839D5343
0x3839d533a  movzx   ebx, ax
0x3839d533d  or      ebx, 80070000h
0x3839d5343  test    byte ptr cs:_bidGblFlags, 2
0x3839d534a  jz      loc_3839D5437
0x3839d5350  mov     rax, cs:?_bidPtrSA_030_3297@?BN@??Rollback@CThreadSecurityToken@@QEAAJHH@Z@4REBGEB; ushort const * const `CThreadSecurityToken::Rollback(int,int)'::`29'::_bidPtrSA_030_3297
0x3839d5357  test    rax, rax
0x3839d535a  jz      loc_3839D5437
0x3839d5360  mov     r8, cs:?_bidPtrSA_030_3297@?BN@??Rollback@CThreadSecurityToken@@QEAAJHH@Z@4REBGEB; ushort const * const `CThreadSecurityToken::Rollback(int,int)'::`29'::_bidPtrSA_030_3297
0x3839d5367  mov     rcx, cs:?_bidSrcFileA@?BN@??Rollback@CThreadSecurityToken@@QEAAJHH@Z@4REBDEB; char const * const `CThreadSecurityToken::Rollback(int,int)'::`29'::_bidSrcFileA
0x3839d536e  mov     r9d, ebx
0x3839d5371  mov     edx, 338400h
0x3839d5376  mov     [rsp+38h+var_10], edi
0x3839d537a  mov     [rsp+38h+var_18], esi
0x3839d537e  call    _bidTraceW
0x3839d5383  mov     eax, ebx
0x3839d5385  mov     rbx, [rsp+38h+arg_0]
0x3839d538a  mov     rsi, [rsp+38h+arg_8]
0x3839d538f  add     rsp, 30h
0x3839d5393  pop     rdi
0x3839d5394  retn
0x3839d5395  mov     rdx, [rcx]; Token
0x3839d5398  xor     ecx, ecx; Thread
0x3839d539a  call    cs:__imp_SetThreadToken
0x3839d53a0  test    eax, eax
0x3839d53a2  jnz     short loc_3839D5403
0x3839d53a4  call    cs:__imp_GetLastError
0x3839d53aa  mov     ebx, eax
0x3839d53ac  test    eax, eax
0x3839d53ae  jle     short loc_3839D53B9
0x3839d53b0  movzx   ebx, ax
0x3839d53b3  or      ebx, 80070000h
0x3839d53b9  test    byte ptr cs:_bidGblFlags, 2
0x3839d53c0  jz      short loc_3839D5437
0x3839d53c2  mov     rax, cs:?_bidPtrSA_030_3305@?CI@??Rollback@CThreadSecurityToken@@QEAAJHH@Z@4REBGEB; ushort const * const `CThreadSecurityToken::Rollback(int,int)'::`40'::_bidPtrSA_030_3305
0x3839d53c9  test    rax, rax
0x3839d53cc  jz      short loc_3839D5437
0x3839d53ce  mov     r8, cs:?_bidPtrSA_030_3305@?CI@??Rollback@CThreadSecurityToken@@QEAAJHH@Z@4REBGEB; ushort const * const `CThreadSecurityToken::Rollback(int,int)'::`40'::_bidPtrSA_030_3305
0x3839d53d5  mov     rcx, cs:?_bidSrcFileA@?CI@??Rollback@CThreadSecurityToken@@QEAAJHH@Z@4REBDEB; char const * const `CThreadSecurityToken::Rollback(int,int)'::`40'::_bidSrcFileA
0x3839d53dc  mov     r9d, ebx
0x3839d53df  mov     edx, 33A400h
0x3839d53e4  mov     [rsp+38h+var_10], edi
0x3839d53e8  mov     [rsp+38h+var_18], esi
0x3839d53ec  call    _bidTraceW
0x3839d53f1  mov     eax, ebx
0x3839d53f3  mov     rbx, [rsp+38h+arg_0]
0x3839d53f8  mov     rsi, [rsp+38h+arg_8]
0x3839d53fd  add     rsp, 30h
0x3839d5401  pop     rdi
0x3839d5402  retn
0x3839d5403  test    byte ptr cs:_bidGblFlags, 2
0x3839d540a  jz      short loc_3839D5437
0x3839d540c  mov     rcx, cs:?_bidPtrSA_030_3310@?DB@??Rollback@CThreadSecurityToken@@QEAAJHH@Z@4REBGEB; ushort const * const `CThreadSecurityToken::Rollback(int,int)'::`49'::_bidPtrSA_030_3310
0x3839d5413  test    rcx, rcx
0x3839d5416  jz      short loc_3839D5437
0x3839d5418  mov     r8, cs:?_bidPtrSA_030_3310@?DB@??Rollback@CThreadSecurityToken@@QEAAJHH@Z@4REBGEB; ushort const * const `CThreadSecurityToken::Rollback(int,int)'::`49'::_bidPtrSA_030_3310
0x3839d541f  mov     rcx, cs:?_bidSrcFileA@?DB@??Rollback@CThreadSecurityToken@@QEAAJHH@Z@4REBDEB; char const * const `CThreadSecurityToken::Rollback(int,int)'::`49'::_bidSrcFileA
0x3839d5426  mov     edx, 33B800h
0x3839d542b  mov     r9d, esi
0x3839d542e  mov     [rsp+38h+var_18], edi
0x3839d5432  call    _bidTraceW
0x3839d5437  mov     rsi, [rsp+38h+arg_8]
0x3839d543c  mov     eax, ebx
0x3839d543e  mov     rbx, [rsp+38h+arg_0]
0x3839d5443  add     rsp, 30h
0x3839d5447  pop     rdi
0x3839d5448  retn
```
