# CAccessControlList::Callback(_ACCESS_ALLOWED_ACE * const *,int)

- ea: `0x18000f8e0`
- end: `0x18000f915`
- name: `?Callback@CAccessControlList@@EEAAJPEBQEAU_ACCESS_ALLOWED_ACE@@H@Z`
- size: `53`
- prototype: `__int64 __fastcall(CAccessControlList *__hidden this, struct _ACCESS_ALLOWED_ACE *const *, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000f8e0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000f8fb`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000f8fb`

## pseudocode

```c
__int64 __fastcall CAccessControlList::Callback(
        CAccessControlList *this,
        struct _ACCESS_ALLOWED_ACE *const *a2,
        int a3)
{
  if ( EqualSid(&(*a2)->SidStart, *((PSID *)this + 4)) )
    *((_DWORD *)this + 10) = a3;
  return 0;
}

```

## disassembly

```asm
0x18000f8e0  mov     [rsp+arg_0], rbx
0x18000f8e5  push    rdi
0x18000f8e6  sub     rsp, 20h
0x18000f8ea  mov     rbx, rcx
0x18000f8ed  mov     edi, r8d
0x18000f8f0  mov     rcx, [rdx]
0x18000f8f3  add     rcx, 8; pSid1
0x18000f8f7  mov     rdx, [rbx+20h]; pSid2
0x18000f8fb  call    cs:__imp_EqualSid
0x18000f901  test    eax, eax
0x18000f903  jz      short loc_18000F908
0x18000f905  mov     [rbx+28h], edi
0x18000f908  mov     rbx, [rsp+28h+arg_0]
0x18000f90d  xor     eax, eax
0x18000f90f  add     rsp, 20h
0x18000f913  pop     rdi
0x18000f914  retn
```
