# SeUtilSecurityInfoFromSecurityDescriptor

- ea: `0x1400d4d50`
- end: `0x1400d4e49`
- name: `SeUtilSecurityInfoFromSecurityDescriptor`
- size: `249`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400d45f4`
- `0x1400d4880`

## callees

- `0x1400d4d50`

## import_xrefs

- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x1400d4e12`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x1400d4e12`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x1400d4dea`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x1400d4dea`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x1400d4d96`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x1400d4d96`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x1400d4dc1`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x1400d4dc1`

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
0x1400d4d50  mov     [rsp-18h+arg_0], rbx
0x1400d4d55  mov     [rsp-18h+arg_10], rsi
0x1400d4d5a  push    rbp
0x1400d4d5b  push    rdi
0x1400d4d5c  push    r14
0x1400d4d5e  mov     rbp, rsp
0x1400d4d61  sub     rsp, 30h
0x1400d4d65  xor     eax, eax
0x1400d4d67  mov     byte ptr [rdx], 0
0x1400d4d6a  mov     [r8], eax
0x1400d4d6d  mov     rsi, r8
0x1400d4d70  mov     r14, rdx
0x1400d4d73  mov     [rbp+OwnerDefaulted], 0
0x1400d4d77  lea     r8, [rbp+OwnerDefaulted]; OwnerDefaulted
0x1400d4d7b  mov     [rbp+SaclPresent], 0
0x1400d4d7f  lea     rdx, [rbp+Owner]; Owner
0x1400d4d83  mov     [rbp+Owner], 0
0x1400d4d8b  mov     rdi, rcx
0x1400d4d8e  mov     [rbp+Sacl], 0
0x1400d4d96  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x1400d4d9d  nop     dword ptr [rax+rax+00h]
0x1400d4da2  test    eax, eax
0x1400d4da4  js      loc_1400D4E35
0x1400d4daa  xor     ebx, ebx
0x1400d4dac  lea     r8, [rbp+OwnerDefaulted]; GroupDefaulted
0x1400d4db0  cmp     [rbp+Owner], rbx
0x1400d4db4  lea     rdx, [rbp+Owner]; Group
0x1400d4db8  mov     rcx, rdi; SecurityDescriptor
0x1400d4dbb  lea     eax, [rbx+1]
0x1400d4dbe  cmovnz  ebx, eax
0x1400d4dc1  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x1400d4dc8  nop     dword ptr [rax+rax+00h]
0x1400d4dcd  test    eax, eax
0x1400d4dcf  js      short loc_1400D4E35
0x1400d4dd1  cmp     [rbp+Owner], 0
0x1400d4dd6  jz      short loc_1400D4DDB
0x1400d4dd8  or      ebx, 2
0x1400d4ddb  lea     r9, [rbp+OwnerDefaulted]; SaclDefaulted
0x1400d4ddf  mov     rcx, rdi; SecurityDescriptor
0x1400d4de2  lea     r8, [rbp+Sacl]; Sacl
0x1400d4de6  lea     rdx, [rbp+SaclPresent]; SaclPresent
0x1400d4dea  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x1400d4df1  nop     dword ptr [rax+rax+00h]
0x1400d4df6  test    eax, eax
0x1400d4df8  js      short loc_1400D4E35
0x1400d4dfa  cmp     [rbp+SaclPresent], 0
0x1400d4dfe  jz      short loc_1400D4E03
0x1400d4e00  or      ebx, 8
0x1400d4e03  lea     r9, [rbp+OwnerDefaulted]; DaclDefaulted
0x1400d4e07  mov     rcx, rdi; SecurityDescriptor
0x1400d4e0a  lea     r8, [rbp+Sacl]; Dacl
0x1400d4e0e  lea     rdx, [rbp+SaclPresent]; DaclPresent
0x1400d4e12  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x1400d4e19  nop     dword ptr [rax+rax+00h]
0x1400d4e1e  test    eax, eax
0x1400d4e20  js      short loc_1400D4E35
0x1400d4e22  cmp     [rbp+SaclPresent], 0
0x1400d4e26  jz      short loc_1400D4E2B
0x1400d4e28  or      ebx, 4
0x1400d4e2b  mov     al, [rbp+OwnerDefaulted]
0x1400d4e2e  mov     [r14], al
0x1400d4e31  xor     eax, eax
0x1400d4e33  mov     [rsi], ebx
0x1400d4e35  mov     rbx, [rsp+30h+arg_0]
0x1400d4e3a  mov     rsi, [rsp+30h+arg_10]
0x1400d4e3f  add     rsp, 30h
0x1400d4e43  pop     r14
0x1400d4e45  pop     rdi
0x1400d4e46  pop     rbp
0x1400d4e47  retn
```
