# _RegisterClientAuthInfo(void *)

- ea: `0x1800064d0`
- end: `0x180006566`
- name: `?_RegisterClientAuthInfo@@YAJPEAX@Z`
- size: `150`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006300`
- `0x180012f10`
- `0x180012fa0`
- `0x180013030`

## callees

- `0x1800064d0`
- `0x18000dae0`
- `0x18000e640`

## import_xrefs

- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180006528`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180006528`

## string_xrefs

- `0x180006550`: `onecore\ds\security\gina\profile\userenv\dll\profrpc.cpp`

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
0x1800064d0  sub     rsp, 68h
0x1800064d4  mov     rax, cs:__security_cookie
0x1800064db  xor     rax, rsp
0x1800064de  mov     [rsp+68h+var_18], rax
0x1800064e3  mov     eax, 1
0x1800064e8  mov     [rsp+68h+var_28.ImpersonationType], 3
0x1800064f0  mov     r9d, 0Ah; AuthnSvc
0x1800064f6  mov     [rsp+68h+var_28.Version], eax
0x1800064fa  mov     [rsp+68h+var_28.Capabilities], eax
0x1800064fe  lea     rdx, ServerPrincName; "NT AUTHORITY\\SYSTEM"
0x180006505  mov     [rsp+68h+var_28.IdentityTracking], eax
0x180006509  lea     rax, [rsp+68h+var_28]
0x18000650e  mov     [rsp+68h+SecurityQOS], rax; SecurityQOS
0x180006513  mov     [rsp+68h+AuthzSvc], 0; AuthzSvc
0x18000651b  lea     r8d, [r9-4]; AuthnLevel
0x18000651f  mov     [rsp+68h+AuthIdentity], 0; unsigned int
0x180006528  call    cs:__imp_RpcBindingSetAuthInfoExW
0x18000652f  nop     dword ptr [rax+rax+00h]
0x180006534  test    eax, eax
0x180006536  jnz     short loc_18000654B
0x180006538  mov     rcx, [rsp+68h+var_18]
0x18000653d  xor     rcx, rsp; StackCookie
0x180006540  call    __security_check_cookie
0x180006545  add     rsp, 68h
0x180006549  retn
0x18000654b  mov     rcx, [rsp+68h]; this
0x180006550  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\u"...
0x180006557  mov     r9d, eax; char *
0x18000655a  mov     edx, 88h; void *
0x18000655f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180006564  jmp     short loc_180006538
```
