# tsched::IsUserAdmin(void)

- ea: `0x18002d774`
- end: `0x18002d7e7`
- name: `?IsUserAdmin@tsched@@YAHXZ`
- size: `115`
- prototype: `__int64 __fastcall(tsched *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000ac28`

## callees

- `0x180004f88`
- `0x1800074c8`
- `0x1800074d4`
- `0x18002d774`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002d7b5`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002d7b5`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002d7cb`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002d7cb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall tsched::IsUserAdmin(tsched *this)
{
  void *v1; // rax
  unsigned int v2; // edi
  WINBOOL IsMember; // [rsp+30h] [rbp+8h] BYREF
  DWORD cbSid; // [rsp+38h] [rbp+10h] BYREF
  PSID pSid; // [rsp+40h] [rbp+18h] BYREF

  IsMember = 0;
  pSid = 0;
  cbSid = 48;
  v1 = operator new[](0x30u);
  wmi::AutoVectorPtr<unsigned char>::operator=(&pSid, v1);
  if ( CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, pSid, &cbSid) )
    CheckTokenMembership(0, pSid, &IsMember);
  v2 = IsMember;
  operator delete(pSid);
  return v2;
}

```

## disassembly

```asm
0x18002d774  push    rdi
0x18002d776  sub     rsp, 20h
0x18002d77a  mov     [rsp+28h+IsMember], 0
0x18002d782  mov     [rsp+28h+pSid], 0
0x18002d78b  mov     ecx, 30h ; '0'; unsigned __int64
0x18002d790  mov     [rsp+28h+cbSid], ecx
0x18002d794  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002d799  mov     rdx, rax
0x18002d79c  lea     rcx, [rsp+28h+pSid]
0x18002d7a1  call    ??4?$AutoVectorPtr@E@wmi@@QEAAAEAV01@PEAE@Z; wmi::AutoVectorPtr<uchar>::operator=(uchar *)
0x18002d7a6  lea     r9, [rsp+28h+cbSid]; cbSid
0x18002d7ab  mov     r8, [rsp+28h+pSid]; pSid
0x18002d7b0  xor     edx, edx; DomainSid
0x18002d7b2  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x18002d7b5  call    cs:__imp_CreateWellKnownSid
0x18002d7bb  test    eax, eax
0x18002d7bd  jz      short loc_18002D7D1
0x18002d7bf  lea     r8, [rsp+28h+IsMember]; IsMember
0x18002d7c4  mov     rdx, [rsp+28h+pSid]; SidToCheck
0x18002d7c9  xor     ecx, ecx; TokenHandle
0x18002d7cb  call    cs:__imp_CheckTokenMembership
0x18002d7d1  mov     edi, [rsp+28h+IsMember]
0x18002d7d5  mov     rcx, [rsp+28h+pSid]; Block
0x18002d7da  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002d7df  mov     eax, edi
0x18002d7e1  add     rsp, 20h
0x18002d7e5  pop     rdi
0x18002d7e6  retn
```
