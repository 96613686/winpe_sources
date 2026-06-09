# SeUtilSecurityInfoFromSecurityDescriptor

- ea: `0x14002151c`
- end: `0x140021615`
- name: `SeUtilSecurityInfoFromSecurityDescriptor`
- size: `249`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140020434`
- `0x14002104c`

## callees

- `0x14002151c`

## import_xrefs

- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x1400215b6`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x1400215b6`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140021562`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140021562`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x14002158d`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x14002158d`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x1400215de`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x1400215de`

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
0x14002151c  mov     [rsp-18h+arg_0], rbx
0x140021521  mov     [rsp-18h+arg_10], rsi
0x140021526  push    rbp
0x140021527  push    rdi
0x140021528  push    r14
0x14002152a  mov     rbp, rsp
0x14002152d  sub     rsp, 30h
0x140021531  xor     eax, eax
0x140021533  mov     byte ptr [rdx], 0
0x140021536  mov     [r8], eax
0x140021539  mov     rsi, r8
0x14002153c  mov     r14, rdx
0x14002153f  mov     [rbp+OwnerDefaulted], 0
0x140021543  lea     r8, [rbp+OwnerDefaulted]; OwnerDefaulted
0x140021547  mov     [rbp+SaclPresent], 0
0x14002154b  lea     rdx, [rbp+Owner]; Owner
0x14002154f  mov     [rbp+Owner], 0
0x140021557  mov     rdi, rcx
0x14002155a  mov     [rbp+Sacl], 0
0x140021562  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x140021569  nop     dword ptr [rax+rax+00h]
0x14002156e  test    eax, eax
0x140021570  js      loc_140021601
0x140021576  xor     ebx, ebx
0x140021578  lea     r8, [rbp+OwnerDefaulted]; GroupDefaulted
0x14002157c  cmp     [rbp+Owner], rbx
0x140021580  lea     rdx, [rbp+Owner]; Group
0x140021584  mov     rcx, rdi; SecurityDescriptor
0x140021587  lea     eax, [rbx+1]
0x14002158a  cmovnz  ebx, eax
0x14002158d  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x140021594  nop     dword ptr [rax+rax+00h]
0x140021599  test    eax, eax
0x14002159b  js      short loc_140021601
0x14002159d  cmp     [rbp+Owner], 0
0x1400215a2  jz      short loc_1400215A7
0x1400215a4  or      ebx, 2
0x1400215a7  lea     r9, [rbp+OwnerDefaulted]; SaclDefaulted
0x1400215ab  mov     rcx, rdi; SecurityDescriptor
0x1400215ae  lea     r8, [rbp+Sacl]; Sacl
0x1400215b2  lea     rdx, [rbp+SaclPresent]; SaclPresent
0x1400215b6  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x1400215bd  nop     dword ptr [rax+rax+00h]
0x1400215c2  test    eax, eax
0x1400215c4  js      short loc_140021601
0x1400215c6  cmp     [rbp+SaclPresent], 0
0x1400215ca  jz      short loc_1400215CF
0x1400215cc  or      ebx, 8
0x1400215cf  lea     r9, [rbp+OwnerDefaulted]; DaclDefaulted
0x1400215d3  mov     rcx, rdi; SecurityDescriptor
0x1400215d6  lea     r8, [rbp+Sacl]; Dacl
0x1400215da  lea     rdx, [rbp+SaclPresent]; DaclPresent
0x1400215de  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x1400215e5  nop     dword ptr [rax+rax+00h]
0x1400215ea  test    eax, eax
0x1400215ec  js      short loc_140021601
0x1400215ee  cmp     [rbp+SaclPresent], 0
0x1400215f2  jz      short loc_1400215F7
0x1400215f4  or      ebx, 4
0x1400215f7  mov     al, [rbp+OwnerDefaulted]
0x1400215fa  mov     [r14], al
0x1400215fd  xor     eax, eax
0x1400215ff  mov     [rsi], ebx
0x140021601  mov     rbx, [rsp+30h+arg_0]
0x140021606  mov     rsi, [rsp+30h+arg_10]
0x14002160b  add     rsp, 30h
0x14002160f  pop     r14
0x140021611  pop     rdi
0x140021612  pop     rbp
0x140021613  retn
```
