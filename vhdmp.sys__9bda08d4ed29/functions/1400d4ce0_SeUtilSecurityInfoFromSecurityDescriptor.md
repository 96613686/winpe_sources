# SeUtilSecurityInfoFromSecurityDescriptor

- ea: `0x1400d4ce0`
- end: `0x1400d4dd9`
- name: `SeUtilSecurityInfoFromSecurityDescriptor`
- size: `249`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400d4584`
- `0x1400d4810`

## callees

- `0x1400d4ce0`

## import_xrefs

- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x1400d4da2`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x1400d4da2`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x1400d4d7a`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x1400d4d7a`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x1400d4d26`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x1400d4d26`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x1400d4d51`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x1400d4d51`

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
0x1400d4ce0  mov     [rsp-18h+arg_0], rbx
0x1400d4ce5  mov     [rsp-18h+arg_10], rsi
0x1400d4cea  push    rbp
0x1400d4ceb  push    rdi
0x1400d4cec  push    r14
0x1400d4cee  mov     rbp, rsp
0x1400d4cf1  sub     rsp, 30h
0x1400d4cf5  xor     eax, eax
0x1400d4cf7  mov     byte ptr [rdx], 0
0x1400d4cfa  mov     [r8], eax
0x1400d4cfd  mov     rsi, r8
0x1400d4d00  mov     r14, rdx
0x1400d4d03  mov     [rbp+OwnerDefaulted], 0
0x1400d4d07  lea     r8, [rbp+OwnerDefaulted]; OwnerDefaulted
0x1400d4d0b  mov     [rbp+SaclPresent], 0
0x1400d4d0f  lea     rdx, [rbp+Owner]; Owner
0x1400d4d13  mov     [rbp+Owner], 0
0x1400d4d1b  mov     rdi, rcx
0x1400d4d1e  mov     [rbp+Sacl], 0
0x1400d4d26  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x1400d4d2d  nop     dword ptr [rax+rax+00h]
0x1400d4d32  test    eax, eax
0x1400d4d34  js      loc_1400D4DC5
0x1400d4d3a  xor     ebx, ebx
0x1400d4d3c  lea     r8, [rbp+OwnerDefaulted]; GroupDefaulted
0x1400d4d40  cmp     [rbp+Owner], rbx
0x1400d4d44  lea     rdx, [rbp+Owner]; Group
0x1400d4d48  mov     rcx, rdi; SecurityDescriptor
0x1400d4d4b  lea     eax, [rbx+1]
0x1400d4d4e  cmovnz  ebx, eax
0x1400d4d51  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x1400d4d58  nop     dword ptr [rax+rax+00h]
0x1400d4d5d  test    eax, eax
0x1400d4d5f  js      short loc_1400D4DC5
0x1400d4d61  cmp     [rbp+Owner], 0
0x1400d4d66  jz      short loc_1400D4D6B
0x1400d4d68  or      ebx, 2
0x1400d4d6b  lea     r9, [rbp+OwnerDefaulted]; SaclDefaulted
0x1400d4d6f  mov     rcx, rdi; SecurityDescriptor
0x1400d4d72  lea     r8, [rbp+Sacl]; Sacl
0x1400d4d76  lea     rdx, [rbp+SaclPresent]; SaclPresent
0x1400d4d7a  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x1400d4d81  nop     dword ptr [rax+rax+00h]
0x1400d4d86  test    eax, eax
0x1400d4d88  js      short loc_1400D4DC5
0x1400d4d8a  cmp     [rbp+SaclPresent], 0
0x1400d4d8e  jz      short loc_1400D4D93
0x1400d4d90  or      ebx, 8
0x1400d4d93  lea     r9, [rbp+OwnerDefaulted]; DaclDefaulted
0x1400d4d97  mov     rcx, rdi; SecurityDescriptor
0x1400d4d9a  lea     r8, [rbp+Sacl]; Dacl
0x1400d4d9e  lea     rdx, [rbp+SaclPresent]; DaclPresent
0x1400d4da2  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x1400d4da9  nop     dword ptr [rax+rax+00h]
0x1400d4dae  test    eax, eax
0x1400d4db0  js      short loc_1400D4DC5
0x1400d4db2  cmp     [rbp+SaclPresent], 0
0x1400d4db6  jz      short loc_1400D4DBB
0x1400d4db8  or      ebx, 4
0x1400d4dbb  mov     al, [rbp+OwnerDefaulted]
0x1400d4dbe  mov     [r14], al
0x1400d4dc1  xor     eax, eax
0x1400d4dc3  mov     [rsi], ebx
0x1400d4dc5  mov     rbx, [rsp+30h+arg_0]
0x1400d4dca  mov     rsi, [rsp+30h+arg_10]
0x1400d4dcf  add     rsp, 30h
0x1400d4dd3  pop     r14
0x1400d4dd5  pop     rdi
0x1400d4dd6  pop     rbp
0x1400d4dd7  retn
```
