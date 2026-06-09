# SeUtilSecurityInfoFromSecurityDescriptor

- ea: `0x14001931c`
- end: `0x140019415`
- name: `SeUtilSecurityInfoFromSecurityDescriptor`
- size: `249`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140018244`
- `0x140018e4c`

## callees

- `0x14001931c`

## import_xrefs

- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x1400193b6`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x1400193b6`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140019362`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140019362`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x14001938d`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x14001938d`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x1400193de`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x1400193de`

## pseudocode

```c
NTSTATUS __fastcall SeUtilSecurityInfoFromSecurityDescriptor(
        PSECURITY_DESCRIPTOR SecurityDescriptor,
        unsigned __int8 *a2,
        _DWORD *a3)
{
  NTSTATUS result; // eax
  int v7; // ebx
  PSID Owner; // [rsp+20h] [rbp-10h] BYREF
  PACL Sacl; // [rsp+28h] [rbp-8h] BYREF
  unsigned __int8 OwnerDefaulted; // [rsp+58h] [rbp+28h] BYREF
  unsigned __int8 SaclPresent; // [rsp+68h] [rbp+38h] BYREF

  *a2 = 0;
  *a3 = 0;
  OwnerDefaulted = 0;
  SaclPresent = 0;
  Owner = 0;
  Sacl = 0;
  result = RtlGetOwnerSecurityDescriptor(SecurityDescriptor, &Owner, &OwnerDefaulted);
  if ( result >= 0 )
  {
    v7 = Owner != 0;
    result = RtlGetGroupSecurityDescriptor(SecurityDescriptor, &Owner, &OwnerDefaulted);
    if ( result >= 0 )
    {
      if ( Owner )
        v7 |= 2u;
      result = RtlGetSaclSecurityDescriptor(SecurityDescriptor, &SaclPresent, &Sacl, &OwnerDefaulted);
      if ( result >= 0 )
      {
        if ( SaclPresent )
          v7 |= 8u;
        result = RtlGetDaclSecurityDescriptor(SecurityDescriptor, &SaclPresent, &Sacl, &OwnerDefaulted);
        if ( result >= 0 )
        {
          if ( SaclPresent )
            v7 |= 4u;
          *a2 = OwnerDefaulted;
          result = 0;
          *a3 = v7;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14001931c  mov     [rsp-18h+arg_0], rbx
0x140019321  mov     [rsp-18h+arg_10], rsi
0x140019326  push    rbp
0x140019327  push    rdi
0x140019328  push    r14
0x14001932a  mov     rbp, rsp
0x14001932d  sub     rsp, 30h
0x140019331  xor     eax, eax
0x140019333  mov     byte ptr [rdx], 0
0x140019336  mov     [r8], eax
0x140019339  mov     rsi, r8
0x14001933c  mov     r14, rdx
0x14001933f  mov     [rbp+OwnerDefaulted], 0
0x140019343  lea     r8, [rbp+OwnerDefaulted]; OwnerDefaulted
0x140019347  mov     [rbp+SaclPresent], 0
0x14001934b  lea     rdx, [rbp+Owner]; Owner
0x14001934f  mov     [rbp+Owner], 0
0x140019357  mov     rdi, rcx
0x14001935a  mov     [rbp+Sacl], 0
0x140019362  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x140019369  nop     dword ptr [rax+rax+00h]
0x14001936e  test    eax, eax
0x140019370  js      loc_140019401
0x140019376  xor     ebx, ebx
0x140019378  lea     r8, [rbp+OwnerDefaulted]; GroupDefaulted
0x14001937c  cmp     [rbp+Owner], rbx
0x140019380  lea     rdx, [rbp+Owner]; Group
0x140019384  mov     rcx, rdi; SecurityDescriptor
0x140019387  lea     eax, [rbx+1]
0x14001938a  cmovnz  ebx, eax
0x14001938d  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x140019394  nop     dword ptr [rax+rax+00h]
0x140019399  test    eax, eax
0x14001939b  js      short loc_140019401
0x14001939d  cmp     [rbp+Owner], 0
0x1400193a2  jz      short loc_1400193A7
0x1400193a4  or      ebx, 2
0x1400193a7  lea     r9, [rbp+OwnerDefaulted]; SaclDefaulted
0x1400193ab  mov     rcx, rdi; SecurityDescriptor
0x1400193ae  lea     r8, [rbp+Sacl]; Sacl
0x1400193b2  lea     rdx, [rbp+SaclPresent]; SaclPresent
0x1400193b6  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x1400193bd  nop     dword ptr [rax+rax+00h]
0x1400193c2  test    eax, eax
0x1400193c4  js      short loc_140019401
0x1400193c6  cmp     [rbp+SaclPresent], 0
0x1400193ca  jz      short loc_1400193CF
0x1400193cc  or      ebx, 8
0x1400193cf  lea     r9, [rbp+OwnerDefaulted]; DaclDefaulted
0x1400193d3  mov     rcx, rdi; SecurityDescriptor
0x1400193d6  lea     r8, [rbp+Sacl]; Dacl
0x1400193da  lea     rdx, [rbp+SaclPresent]; DaclPresent
0x1400193de  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x1400193e5  nop     dword ptr [rax+rax+00h]
0x1400193ea  test    eax, eax
0x1400193ec  js      short loc_140019401
0x1400193ee  cmp     [rbp+SaclPresent], 0
0x1400193f2  jz      short loc_1400193F7
0x1400193f4  or      ebx, 4
0x1400193f7  mov     al, [rbp+OwnerDefaulted]
0x1400193fa  mov     [r14], al
0x1400193fd  xor     eax, eax
0x1400193ff  mov     [rsi], ebx
0x140019401  mov     rbx, [rsp+30h+arg_0]
0x140019406  mov     rsi, [rsp+30h+arg_10]
0x14001940b  add     rsp, 30h
0x14001940f  pop     r14
0x140019411  pop     rdi
0x140019412  pop     rbp
0x140019413  retn
```
