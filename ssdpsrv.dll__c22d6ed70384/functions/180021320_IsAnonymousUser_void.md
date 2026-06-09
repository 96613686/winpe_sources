# IsAnonymousUser(void)

- ea: `0x180021320`
- end: `0x180021389`
- name: `?IsAnonymousUser@@YAHXZ`
- size: `105`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180021910`

## callees

- `0x180021320`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180021372`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180021372`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002133a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002133a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180021369`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180021369`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180021355`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180021355`

## pseudocode

```c
__int64 IsAnonymousUser(void)
{
  unsigned int v0; // edi
  void *v1; // rax
  void *v2; // rbx
  WINBOOL IsMember; // [rsp+30h] [rbp+8h] BYREF
  DWORD cbSid; // [rsp+38h] [rbp+10h] BYREF

  v0 = 1;
  IsMember = 1;
  cbSid = 68;
  v1 = malloc(0x44u);
  v2 = v1;
  if ( v1 )
  {
    if ( CreateWellKnownSid(WinAnonymousSid, 0, v1, &cbSid) )
      CheckTokenMembership(0, v2, &IsMember);
    free(v2);
    return (unsigned int)IsMember;
  }
  return v0;
}

```

## disassembly

```asm
0x180021320  mov     [rsp+arg_10], rbx
0x180021325  push    rdi
0x180021326  sub     rsp, 20h
0x18002132a  mov     edi, 1
0x18002132f  mov     [rsp+28h+IsMember], edi
0x180021333  lea     ecx, [rdi+43h]; Size
0x180021336  mov     [rsp+28h+cbSid], ecx
0x18002133a  call    cs:__imp_malloc
0x180021340  mov     rbx, rax
0x180021343  test    rax, rax
0x180021346  jz      short loc_18002137C
0x180021348  lea     r9, [rsp+28h+cbSid]; cbSid
0x18002134d  mov     r8, rax; pSid
0x180021350  xor     edx, edx; DomainSid
0x180021352  lea     ecx, [rdi+0Ch]; WellKnownSidType
0x180021355  call    cs:__imp_CreateWellKnownSid
0x18002135b  test    eax, eax
0x18002135d  jz      short loc_18002136F
0x18002135f  lea     r8, [rsp+28h+IsMember]; IsMember
0x180021364  mov     rdx, rbx; SidToCheck
0x180021367  xor     ecx, ecx; TokenHandle
0x180021369  call    cs:__imp_CheckTokenMembership
0x18002136f  mov     rcx, rbx; Block
0x180021372  call    cs:__imp_free
0x180021378  mov     edi, [rsp+28h+IsMember]
0x18002137c  mov     rbx, [rsp+28h+arg_10]
0x180021381  mov     eax, edi
0x180021383  add     rsp, 20h
0x180021387  pop     rdi
0x180021388  retn
```
