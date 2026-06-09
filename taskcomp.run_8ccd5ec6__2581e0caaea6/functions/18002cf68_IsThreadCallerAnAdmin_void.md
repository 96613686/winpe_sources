# IsThreadCallerAnAdmin(void *)

- ea: `0x18002cf68`
- end: `0x18002cfce`
- name: `?IsThreadCallerAnAdmin@@YAHPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800036a0`
- `0x180016040`
- `0x180016620`

## callees

- `0x180030700`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002cfa8`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002cfa8`

## pseudocode

```c
__int64 __fastcall IsThreadCallerAnAdmin(void *a1)
{
  BOOL v1; // eax
  WINBOOL IsMember; // [rsp+20h] [rbp-20h] BYREF
  _DWORD SidToCheck[4]; // [rsp+28h] [rbp-18h] BYREF

  SidToCheck[0] = 513;
  IsMember = 0;
  SidToCheck[1] = 83886080;
  SidToCheck[2] = 32;
  SidToCheck[3] = 544;
  v1 = CheckTokenMembership(a1, SidToCheck, &IsMember);
  return IsMember & (unsigned int)-v1;
}

```

## disassembly

```asm
0x18002cf68  push    rbp
0x18002cf6a  mov     rbp, rsp
0x18002cf6d  sub     rsp, 40h
0x18002cf71  mov     rax, cs:__security_cookie
0x18002cf78  xor     rax, rsp
0x18002cf7b  mov     [rbp+var_8], rax
0x18002cf7f  xor     eax, eax
0x18002cf81  mov     [rbp+SidToCheck], 201h
0x18002cf88  lea     r8, [rbp+IsMember]; IsMember
0x18002cf8c  mov     [rbp+IsMember], eax
0x18002cf8f  lea     rdx, [rbp+SidToCheck]; SidToCheck
0x18002cf93  mov     [rbp+var_14], 5000000h
0x18002cf9a  mov     [rbp+var_10], 20h ; ' '
0x18002cfa1  mov     [rbp+var_C], 220h
0x18002cfa8  call    cs:__imp_CheckTokenMembership
0x18002cfaf  nop     dword ptr [rax+rax+00h]
0x18002cfb4  neg     eax
0x18002cfb6  sbb     eax, eax
0x18002cfb8  and     eax, [rbp+IsMember]
0x18002cfbb  mov     rcx, [rbp+var_8]
0x18002cfbf  xor     rcx, rsp; StackCookie
0x18002cfc2  call    __security_check_cookie
0x18002cfc7  add     rsp, 40h
0x18002cfcb  pop     rbp
0x18002cfcc  retn
```
