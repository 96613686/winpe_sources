# IsThreadCallerAnAdmin(void *)

- ea: `0x18002b330`
- end: `0x18002b38f`
- name: `?IsThreadCallerAnAdmin@@YAHPEAX@Z`
- size: `95`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003500`
- `0x180015280`
- `0x1800157e0`

## callees

- `0x18002e5b0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002b370`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002b370`

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
0x18002b330  push    rbp
0x18002b332  mov     rbp, rsp
0x18002b335  sub     rsp, 40h
0x18002b339  mov     rax, cs:__security_cookie
0x18002b340  xor     rax, rsp
0x18002b343  mov     [rbp+var_8], rax
0x18002b347  xor     eax, eax
0x18002b349  mov     [rbp+SidToCheck], 201h
0x18002b350  lea     r8, [rbp+IsMember]; IsMember
0x18002b354  mov     [rbp+IsMember], eax
0x18002b357  lea     rdx, [rbp+SidToCheck]; SidToCheck
0x18002b35b  mov     [rbp+var_14], 5000000h
0x18002b362  mov     [rbp+var_10], 20h ; ' '
0x18002b369  mov     [rbp+var_C], 220h
0x18002b370  call    cs:__imp_CheckTokenMembership
0x18002b376  neg     eax
0x18002b378  sbb     eax, eax
0x18002b37a  and     eax, [rbp+IsMember]
0x18002b37d  mov     rcx, [rbp+var_8]
0x18002b381  xor     rcx, rsp; StackCookie
0x18002b384  call    __security_check_cookie
0x18002b389  add     rsp, 40h
0x18002b38d  pop     rbp
0x18002b38e  retn
```
