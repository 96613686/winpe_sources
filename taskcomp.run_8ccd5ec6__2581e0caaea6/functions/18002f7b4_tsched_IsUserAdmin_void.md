# tsched::IsUserAdmin(void)

- ea: `0x18002f7b4`
- end: `0x18002f834`
- name: `?IsUserAdmin@tsched@@YAHXZ`
- size: `128`
- prototype: `__int64 __fastcall(tsched *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000b218`

## callees

- `0x180005224`
- `0x180007988`
- `0x180007994`
- `0x18002f7b4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002f7f5`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002f7f5`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002f811`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002f811`

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
0x18002f7b4  push    rdi
0x18002f7b6  sub     rsp, 20h
0x18002f7ba  mov     [rsp+28h+IsMember], 0
0x18002f7c2  mov     [rsp+28h+pSid], 0
0x18002f7cb  mov     ecx, 30h ; '0'; unsigned __int64
0x18002f7d0  mov     [rsp+28h+cbSid], ecx
0x18002f7d4  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002f7d9  mov     rdx, rax
0x18002f7dc  lea     rcx, [rsp+28h+pSid]
0x18002f7e1  call    ??4?$AutoVectorPtr@E@wmi@@QEAAAEAV01@PEAE@Z; wmi::AutoVectorPtr<uchar>::operator=(uchar *)
0x18002f7e6  lea     r9, [rsp+28h+cbSid]; cbSid
0x18002f7eb  mov     r8, [rsp+28h+pSid]; pSid
0x18002f7f0  xor     edx, edx; DomainSid
0x18002f7f2  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x18002f7f5  call    cs:__imp_CreateWellKnownSid
0x18002f7fc  nop     dword ptr [rax+rax+00h]
0x18002f801  test    eax, eax
0x18002f803  jz      short loc_18002F81D
0x18002f805  lea     r8, [rsp+28h+IsMember]; IsMember
0x18002f80a  mov     rdx, [rsp+28h+pSid]; SidToCheck
0x18002f80f  xor     ecx, ecx; TokenHandle
0x18002f811  call    cs:__imp_CheckTokenMembership
0x18002f818  nop     dword ptr [rax+rax+00h]
0x18002f81d  mov     edi, [rsp+28h+IsMember]
0x18002f821  mov     rcx, [rsp+28h+pSid]; Block
0x18002f826  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002f82b  mov     eax, edi
0x18002f82d  add     rsp, 20h
0x18002f831  pop     rdi
0x18002f832  retn
```
