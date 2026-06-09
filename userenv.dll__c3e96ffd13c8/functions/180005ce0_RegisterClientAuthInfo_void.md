# _RegisterClientAuthInfo(void *)

- ea: `0x180005ce0`
- end: `0x180005d6f`
- name: `?_RegisterClientAuthInfo@@YAJPEAX@Z`
- size: `143`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005b28`
- `0x180011f4c`
- `0x180011fd8`
- `0x180012064`

## callees

- `0x180005ce0`
- `0x18000ce7c`
- `0x18000d9b0`

## import_xrefs

- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180005d38`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180005d38`

## string_xrefs

- `0x180005d59`: `onecore\ds\security\gina\profile\userenv\dll\profrpc.cpp`

## pseudocode

```c
unsigned int __fastcall _RegisterClientAuthInfo(void *a1)
{
  unsigned int result; // eax
  unsigned int AuthIdentity; // [rsp+20h] [rbp-48h]
  RPC_SECURITY_QOS SecurityQOS; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  SecurityQOS.ImpersonationType = 3;
  SecurityQOS.Version = 1;
  SecurityQOS.Capabilities = 1;
  SecurityQOS.IdentityTracking = 1;
  result = RpcBindingSetAuthInfoExW(a1, (RPC_WSTR)L"NT AUTHORITY\\SYSTEM", 6u, 0xAu, 0, 0, &SecurityQOS);
  if ( result )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x88,
             (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\dll\\profrpc.cpp",
             (const char *)result,
             AuthIdentity);
  return result;
}

```

## disassembly

```asm
0x180005ce0  sub     rsp, 68h
0x180005ce4  mov     rax, cs:__security_cookie
0x180005ceb  xor     rax, rsp
0x180005cee  mov     [rsp+68h+var_18], rax
0x180005cf3  mov     eax, 1
0x180005cf8  mov     [rsp+68h+var_28.ImpersonationType], 3
0x180005d00  mov     r9d, 0Ah; AuthnSvc
0x180005d06  mov     [rsp+68h+var_28.Version], eax
0x180005d0a  mov     [rsp+68h+var_28.Capabilities], eax
0x180005d0e  lea     rdx, ServerPrincName; "NT AUTHORITY\\SYSTEM"
0x180005d15  mov     [rsp+68h+var_28.IdentityTracking], eax
0x180005d19  lea     rax, [rsp+68h+var_28]
0x180005d1e  mov     [rsp+68h+SecurityQOS], rax; SecurityQOS
0x180005d23  mov     [rsp+68h+AuthzSvc], 0; AuthzSvc
0x180005d2b  lea     r8d, [r9-4]; AuthnLevel
0x180005d2f  mov     [rsp+68h+AuthIdentity], 0; unsigned int
0x180005d38  call    cs:__imp_RpcBindingSetAuthInfoExW
0x180005d3e  test    eax, eax
0x180005d40  jnz     short loc_180005D54
0x180005d42  mov     rcx, [rsp+68h+var_18]
0x180005d47  xor     rcx, rsp; StackCookie
0x180005d4a  call    __security_check_cookie
0x180005d4f  add     rsp, 68h
0x180005d53  retn
0x180005d54  mov     rcx, [rsp+68h]; this
0x180005d59  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\u"...
0x180005d60  mov     r9d, eax; char *
0x180005d63  mov     edx, 88h; void *
0x180005d68  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180005d6d  jmp     short loc_180005D42
```
