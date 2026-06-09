# IsAuthenticatedUser(void)

- ea: `0x18001fb14`
- end: `0x18001fb82`
- name: `?IsAuthenticatedUser@@YAHXZ`
- size: `110`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180021910`

## callees

- `0x18001fb14`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001fb6b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001fb6b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001fb2b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001fb2b`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001fb5a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001fb5a`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18001fb46`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18001fb46`

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
0x18001fb14  mov     [rsp+arg_10], rbx
0x18001fb19  push    rdi
0x18001fb1a  sub     rsp, 20h
0x18001fb1e  xor     ebx, ebx
0x18001fb20  mov     [rsp+28h+IsMember], ebx
0x18001fb24  lea     ecx, [rbx+44h]; Size
0x18001fb27  mov     [rsp+28h+cbSid], ecx
0x18001fb2b  call    cs:__imp_malloc
0x18001fb31  mov     rdi, rax
0x18001fb34  test    rax, rax
0x18001fb37  jz      short loc_18001FB75
0x18001fb39  lea     r9, [rsp+28h+cbSid]; cbSid
0x18001fb3e  mov     r8, rax; pSid
0x18001fb41  xor     edx, edx; DomainSid
0x18001fb43  lea     ecx, [rbx+11h]; WellKnownSidType
0x18001fb46  call    cs:__imp_CreateWellKnownSid
0x18001fb4c  test    eax, eax
0x18001fb4e  jz      short loc_18001FB68
0x18001fb50  lea     r8, [rsp+28h+IsMember]; IsMember
0x18001fb55  mov     rdx, rdi; SidToCheck
0x18001fb58  xor     ecx, ecx; TokenHandle
0x18001fb5a  call    cs:__imp_CheckTokenMembership
0x18001fb60  test    eax, eax
0x18001fb62  jnz     short loc_18001FB68
0x18001fb64  mov     [rsp+28h+IsMember], ebx
0x18001fb68  mov     rcx, rdi; Block
0x18001fb6b  call    cs:__imp_free
0x18001fb71  mov     ebx, [rsp+28h+IsMember]
0x18001fb75  mov     eax, ebx
0x18001fb77  mov     rbx, [rsp+28h+arg_10]
0x18001fb7c  add     rsp, 20h
0x18001fb80  pop     rdi
0x18001fb81  retn
```
