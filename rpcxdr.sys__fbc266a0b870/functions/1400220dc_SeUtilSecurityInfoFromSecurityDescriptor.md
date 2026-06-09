# SeUtilSecurityInfoFromSecurityDescriptor

- ea: `0x1400220dc`
- end: `0x1400221d5`
- name: `SeUtilSecurityInfoFromSecurityDescriptor`
- size: `249`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140021004`
- `0x140021c0c`

## callees

- `0x1400220dc`

## import_xrefs

- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x140022176`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x140022176`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140022122`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140022122`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x14002214d`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x14002214d`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14002219e`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14002219e`

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
0x1400220dc  mov     [rsp-18h+arg_0], rbx
0x1400220e1  mov     [rsp-18h+arg_10], rsi
0x1400220e6  push    rbp
0x1400220e7  push    rdi
0x1400220e8  push    r14
0x1400220ea  mov     rbp, rsp
0x1400220ed  sub     rsp, 30h
0x1400220f1  xor     eax, eax
0x1400220f3  mov     byte ptr [rdx], 0
0x1400220f6  mov     [r8], eax
0x1400220f9  mov     rsi, r8
0x1400220fc  mov     r14, rdx
0x1400220ff  mov     [rbp+OwnerDefaulted], 0
0x140022103  lea     r8, [rbp+OwnerDefaulted]; OwnerDefaulted
0x140022107  mov     [rbp+SaclPresent], 0
0x14002210b  lea     rdx, [rbp+Owner]; Owner
0x14002210f  mov     [rbp+Owner], 0
0x140022117  mov     rdi, rcx
0x14002211a  mov     [rbp+Sacl], 0
0x140022122  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x140022129  nop     dword ptr [rax+rax+00h]
0x14002212e  test    eax, eax
0x140022130  js      loc_1400221C1
0x140022136  xor     ebx, ebx
0x140022138  lea     r8, [rbp+OwnerDefaulted]; GroupDefaulted
0x14002213c  cmp     [rbp+Owner], rbx
0x140022140  lea     rdx, [rbp+Owner]; Group
0x140022144  mov     rcx, rdi; SecurityDescriptor
0x140022147  lea     eax, [rbx+1]
0x14002214a  cmovnz  ebx, eax
0x14002214d  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x140022154  nop     dword ptr [rax+rax+00h]
0x140022159  test    eax, eax
0x14002215b  js      short loc_1400221C1
0x14002215d  cmp     [rbp+Owner], 0
0x140022162  jz      short loc_140022167
0x140022164  or      ebx, 2
0x140022167  lea     r9, [rbp+OwnerDefaulted]; SaclDefaulted
0x14002216b  mov     rcx, rdi; SecurityDescriptor
0x14002216e  lea     r8, [rbp+Sacl]; Sacl
0x140022172  lea     rdx, [rbp+SaclPresent]; SaclPresent
0x140022176  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x14002217d  nop     dword ptr [rax+rax+00h]
0x140022182  test    eax, eax
0x140022184  js      short loc_1400221C1
0x140022186  cmp     [rbp+SaclPresent], 0
0x14002218a  jz      short loc_14002218F
0x14002218c  or      ebx, 8
0x14002218f  lea     r9, [rbp+OwnerDefaulted]; DaclDefaulted
0x140022193  mov     rcx, rdi; SecurityDescriptor
0x140022196  lea     r8, [rbp+Sacl]; Dacl
0x14002219a  lea     rdx, [rbp+SaclPresent]; DaclPresent
0x14002219e  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x1400221a5  nop     dword ptr [rax+rax+00h]
0x1400221aa  test    eax, eax
0x1400221ac  js      short loc_1400221C1
0x1400221ae  cmp     [rbp+SaclPresent], 0
0x1400221b2  jz      short loc_1400221B7
0x1400221b4  or      ebx, 4
0x1400221b7  mov     al, [rbp+OwnerDefaulted]
0x1400221ba  mov     [r14], al
0x1400221bd  xor     eax, eax
0x1400221bf  mov     [rsi], ebx
0x1400221c1  mov     rbx, [rsp+30h+arg_0]
0x1400221c6  mov     rsi, [rsp+30h+arg_10]
0x1400221cb  add     rsp, 30h
0x1400221cf  pop     r14
0x1400221d1  pop     rdi
0x1400221d2  pop     rbp
0x1400221d3  retn
```
