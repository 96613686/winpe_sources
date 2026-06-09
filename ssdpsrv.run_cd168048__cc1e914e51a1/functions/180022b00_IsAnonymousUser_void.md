# IsAnonymousUser(void)

- ea: `0x180022b00`
- end: `0x180022b82`
- name: `?IsAnonymousUser@@YAHXZ`
- size: `130`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180022fe0`

## callees

- `0x180022b00`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180022b64`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180022b64`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180022b1a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180022b1a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180022b55`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180022b55`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180022b3b`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180022b3b`

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
0x180022b00  mov     [rsp+arg_10], rbx
0x180022b05  push    rdi
0x180022b06  sub     rsp, 20h
0x180022b0a  mov     edi, 1
0x180022b0f  mov     [rsp+28h+IsMember], edi
0x180022b13  lea     ecx, [rdi+43h]; Size
0x180022b16  mov     [rsp+28h+cbSid], ecx
0x180022b1a  call    cs:__imp_malloc
0x180022b21  nop     dword ptr [rax+rax+00h]
0x180022b26  mov     rbx, rax
0x180022b29  test    rax, rax
0x180022b2c  jz      short loc_180022B74
0x180022b2e  lea     r9, [rsp+28h+cbSid]; cbSid
0x180022b33  mov     r8, rax; pSid
0x180022b36  xor     edx, edx; DomainSid
0x180022b38  lea     ecx, [rdi+0Ch]; WellKnownSidType
0x180022b3b  call    cs:__imp_CreateWellKnownSid
0x180022b42  nop     dword ptr [rax+rax+00h]
0x180022b47  test    eax, eax
0x180022b49  jz      short loc_180022B61
0x180022b4b  lea     r8, [rsp+28h+IsMember]; IsMember
0x180022b50  mov     rdx, rbx; SidToCheck
0x180022b53  xor     ecx, ecx; TokenHandle
0x180022b55  call    cs:__imp_CheckTokenMembership
0x180022b5c  nop     dword ptr [rax+rax+00h]
0x180022b61  mov     rcx, rbx; Block
0x180022b64  call    cs:__imp_free
0x180022b6b  nop     dword ptr [rax+rax+00h]
0x180022b70  mov     edi, [rsp+28h+IsMember]
0x180022b74  mov     rbx, [rsp+28h+arg_10]
0x180022b79  mov     eax, edi
0x180022b7b  add     rsp, 20h
0x180022b7f  pop     rdi
0x180022b80  retn
```
