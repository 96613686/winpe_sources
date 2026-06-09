# CUserContext::Impersonate(void)

- ea: `0x1800401b8`
- end: `0x180040216`
- name: `?Impersonate@CUserContext@@QEAAJXZ`
- size: `94`
- prototype: `signed int __fastcall(CUserContext *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180025d94`
- `0x1800bcd80`

## callees

- `0x1800401b8`
- `0x1800bc048`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800401f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800401f3`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800401e9`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800401e9`
- `RPCRT4!RpcImpersonateClient` at `0x1800401d5`
- `RPCRT4!RpcImpersonateClient` at `0x1800401d5`

## pseudocode

```c
signed int __fastcall CUserContext::Impersonate(CUserContext *this)
{
  void *v2; // rcx
  RPC_STATUS v3; // eax
  signed int result; // eax

  if ( *((_DWORD *)this + 4) )
    CUserContext::RevertToSelf(this);
  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    v3 = RpcImpersonateClient(v2);
    if ( v3 )
      return v3 | 0x80010000;
    goto LABEL_9;
  }
  if ( ImpersonateLoggedOnUser(*(HANDLE *)this) )
  {
LABEL_9:
    *((_DWORD *)this + 4) = 1;
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
0x1800401b8  push    rbx
0x1800401ba  sub     rsp, 20h
0x1800401be  cmp     dword ptr [rcx+10h], 0
0x1800401c2  mov     rbx, rcx
0x1800401c5  jz      short loc_1800401CC
0x1800401c7  call    ?RevertToSelf@CUserContext@@QEAAJXZ; CUserContext::RevertToSelf(void)
0x1800401cc  mov     rcx, [rbx+8]; BindingHandle
0x1800401d0  test    rcx, rcx
0x1800401d3  jz      short loc_1800401E6
0x1800401d5  call    cs:__imp_RpcImpersonateClient
0x1800401db  test    eax, eax
0x1800401dd  jz      short loc_180040207
0x1800401df  or      eax, 80010000h
0x1800401e4  jmp     short loc_180040210
0x1800401e6  mov     rcx, [rbx]; hToken
0x1800401e9  call    cs:__imp_ImpersonateLoggedOnUser
0x1800401ef  test    eax, eax
0x1800401f1  jnz     short loc_180040207
0x1800401f3  call    cs:__imp_GetLastError
0x1800401f9  test    eax, eax
0x1800401fb  jle     short loc_180040210
0x1800401fd  movzx   eax, ax
0x180040200  or      eax, 80070000h
0x180040205  jmp     short loc_180040210
0x180040207  mov     dword ptr [rbx+10h], 1
0x18004020e  xor     eax, eax
0x180040210  add     rsp, 20h
0x180040214  pop     rbx
0x180040215  retn
```
