# IsAuthenticatedUser(void)

- ea: `0x1800211e8`
- end: `0x18002126f`
- name: `?IsAuthenticatedUser@@YAHXZ`
- size: `135`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180022fe0`

## callees

- `0x1800211e8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180021251`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180021251`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800211ff`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800211ff`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002123a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002123a`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180021220`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180021220`

## pseudocode

```c
__int64 IsAuthenticatedUser(void)
{
  unsigned int v0; // ebx
  void *v1; // rax
  void *v2; // rdi
  WINBOOL IsMember; // [rsp+30h] [rbp+8h] BYREF
  DWORD cbSid; // [rsp+38h] [rbp+10h] BYREF

  v0 = 0;
  IsMember = 0;
  cbSid = 68;
  v1 = malloc(0x44u);
  v2 = v1;
  if ( v1 )
  {
    if ( CreateWellKnownSid(WinAuthenticatedUserSid, 0, v1, &cbSid) && !CheckTokenMembership(0, v2, &IsMember) )
      IsMember = 0;
    free(v2);
    return (unsigned int)IsMember;
  }
  return v0;
}

```

## disassembly

```asm
0x1800211e8  mov     [rsp+arg_10], rbx
0x1800211ed  push    rdi
0x1800211ee  sub     rsp, 20h
0x1800211f2  xor     ebx, ebx
0x1800211f4  mov     [rsp+28h+IsMember], ebx
0x1800211f8  lea     ecx, [rbx+44h]; Size
0x1800211fb  mov     [rsp+28h+cbSid], ecx
0x1800211ff  call    cs:__imp_malloc
0x180021206  nop     dword ptr [rax+rax+00h]
0x18002120b  mov     rdi, rax
0x18002120e  test    rax, rax
0x180021211  jz      short loc_180021261
0x180021213  lea     r9, [rsp+28h+cbSid]; cbSid
0x180021218  mov     r8, rax; pSid
0x18002121b  xor     edx, edx; DomainSid
0x18002121d  lea     ecx, [rbx+11h]; WellKnownSidType
0x180021220  call    cs:__imp_CreateWellKnownSid
0x180021227  nop     dword ptr [rax+rax+00h]
0x18002122c  test    eax, eax
0x18002122e  jz      short loc_18002124E
0x180021230  lea     r8, [rsp+28h+IsMember]; IsMember
0x180021235  mov     rdx, rdi; SidToCheck
0x180021238  xor     ecx, ecx; TokenHandle
0x18002123a  call    cs:__imp_CheckTokenMembership
0x180021241  nop     dword ptr [rax+rax+00h]
0x180021246  test    eax, eax
0x180021248  jnz     short loc_18002124E
0x18002124a  mov     [rsp+28h+IsMember], ebx
0x18002124e  mov     rcx, rdi; Block
0x180021251  call    cs:__imp_free
0x180021258  nop     dword ptr [rax+rax+00h]
0x18002125d  mov     ebx, [rsp+28h+IsMember]
0x180021261  mov     eax, ebx
0x180021263  mov     rbx, [rsp+28h+arg_10]
0x180021268  add     rsp, 20h
0x18002126c  pop     rdi
0x18002126d  retn
```
