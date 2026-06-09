# SIPolicyIsSecurityDescriptorUserWriteable

- ea: `0x18004b91c`
- end: `0x18004ba13`
- name: `SIPolicyIsSecurityDescriptorUserWriteable`
- size: `247`
- prototype: `NTSTATUS __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor, _BYTE *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180042a4c`

## callees

- `0x1800261f0`
- `0x18004b91c`

## import_xrefs

- `ntdll!RtlGetAce` at `0x18004b9c1`
- `ntdll!RtlGetAce` at `0x18004b9c1`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x18004b960`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x18004b960`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18004b993`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18004b993`

## pseudocode

```c
NTSTATUS __fastcall SIPolicyIsSecurityDescriptorUserWriteable(PSECURITY_DESCRIPTOR SecurityDescriptor, _BYTE *a2)
{
  NTSTATUS result; // eax
  PACL v5; // rcx
  ULONG i; // edi
  unsigned __int8 DaclDefaulted[8]; // [rsp+20h] [rbp-20h] BYREF
  PACL Dacl; // [rsp+28h] [rbp-18h] BYREF
  PSID Owner; // [rsp+30h] [rbp-10h] BYREF
  PVOID Ace; // [rsp+38h] [rbp-8h] BYREF
  unsigned __int8 DaclPresent; // [rsp+60h] [rbp+20h] BYREF
  unsigned __int8 OwnerDefaulted; // [rsp+68h] [rbp+28h] BYREF

  Dacl = 0;
  Owner = 0;
  Ace = 0;
  DaclPresent = 0;
  DaclDefaulted[0] = 0;
  OwnerDefaulted = 0;
  result = RtlGetOwnerSecurityDescriptor(SecurityDescriptor, &Owner, &OwnerDefaulted);
  if ( result < 0 )
    return result;
  if ( !Owner || !(unsigned __int8)SIPolicyIsSidKnownAdmin(Owner) )
  {
LABEL_17:
    result = 0;
LABEL_18:
    *a2 = 1;
    return result;
  }
  result = RtlGetDaclSecurityDescriptor(SecurityDescriptor, &DaclPresent, &Dacl, DaclDefaulted);
  if ( result < 0 )
    return result;
  if ( !DaclPresent )
  {
    *a2 = 0;
    return result;
  }
  v5 = Dacl;
  if ( !Dacl )
    goto LABEL_18;
  for ( i = 0; i < v5->AceCount; ++i )
  {
    result = RtlGetAce(v5, i, &Ace);
    if ( result < 0 )
      return result;
    if ( (!*(_BYTE *)Ace || *(_BYTE *)Ace == 9)
      && (*((_DWORD *)Ace + 1) & 0x116) != 0
      && !(unsigned __int8)SIPolicyIsSidKnownAdmin((char *)Ace + 8) )
    {
      goto LABEL_17;
    }
    v5 = Dacl;
  }
  *a2 = 0;
  return 0;
}

```

## disassembly

```asm
0x18004b91c  mov     [rsp-8+arg_0], rbx
0x18004b921  mov     [rsp-8+arg_8], rdi
0x18004b926  push    rbp
0x18004b927  mov     rbp, rsp
0x18004b92a  sub     rsp, 40h
0x18004b92e  mov     rbx, rdx
0x18004b931  mov     [rbp+Dacl], 0
0x18004b939  lea     rdx, [rbp+Owner]; Owner
0x18004b93d  mov     [rbp+Owner], 0
0x18004b945  lea     r8, [rbp+OwnerDefaulted]; OwnerDefaulted
0x18004b949  mov     [rbp+Ace], 0
0x18004b951  mov     rdi, rcx
0x18004b954  mov     [rbp+DaclPresent], 0
0x18004b958  mov     [rbp+DaclDefaulted], 0
0x18004b95c  mov     [rbp+OwnerDefaulted], 0
0x18004b960  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x18004b966  test    eax, eax
0x18004b968  js      loc_18004BA03
0x18004b96e  mov     rcx, [rbp+Owner]; Sid1
0x18004b972  test    rcx, rcx
0x18004b975  jz      loc_18004B9FE
0x18004b97b  call    SIPolicyIsSidKnownAdmin
0x18004b980  test    al, al
0x18004b982  jz      short loc_18004B9FE
0x18004b984  lea     r9, [rbp+DaclDefaulted]; DaclDefaulted
0x18004b988  mov     rcx, rdi; SecurityDescriptor
0x18004b98b  lea     r8, [rbp+Dacl]; Dacl
0x18004b98f  lea     rdx, [rbp+DaclPresent]; DaclPresent
0x18004b993  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x18004b999  test    eax, eax
0x18004b99b  js      short loc_18004BA03
0x18004b99d  cmp     [rbp+DaclPresent], 0
0x18004b9a1  jnz     short loc_18004B9A8
0x18004b9a3  mov     byte ptr [rbx], 0
0x18004b9a6  jmp     short loc_18004BA03
0x18004b9a8  mov     rcx, [rbp+Dacl]; Acl
0x18004b9ac  test    rcx, rcx
0x18004b9af  jz      short loc_18004BA00
0x18004b9b1  xor     edi, edi
0x18004b9b3  movzx   eax, word ptr [rcx+4]
0x18004b9b7  cmp     edi, eax
0x18004b9b9  jnb     short loc_18004B9F7
0x18004b9bb  lea     r8, [rbp+Ace]; Ace
0x18004b9bf  mov     edx, edi; AceIndex
0x18004b9c1  call    cs:__imp_RtlGetAce
0x18004b9c7  test    eax, eax
0x18004b9c9  js      short loc_18004BA03
0x18004b9cb  mov     rcx, [rbp+Ace]
0x18004b9cf  mov     al, [rcx]
0x18004b9d1  test    al, al
0x18004b9d3  jz      short loc_18004B9D9
0x18004b9d5  cmp     al, 9
0x18004b9d7  jnz     short loc_18004B9EF
0x18004b9d9  test    dword ptr [rcx+4], 116h
0x18004b9e0  jz      short loc_18004B9EF
0x18004b9e2  add     rcx, 8; Sid1
0x18004b9e6  call    SIPolicyIsSidKnownAdmin
0x18004b9eb  test    al, al
0x18004b9ed  jz      short loc_18004B9FE
0x18004b9ef  mov     rcx, [rbp+Dacl]
0x18004b9f3  inc     edi
0x18004b9f5  jmp     short loc_18004B9B3
0x18004b9f7  mov     byte ptr [rbx], 0
0x18004b9fa  xor     eax, eax
0x18004b9fc  jmp     short loc_18004BA03
0x18004b9fe  xor     eax, eax
0x18004ba00  mov     byte ptr [rbx], 1
0x18004ba03  mov     rbx, [rsp+40h+arg_0]
0x18004ba08  mov     rdi, [rsp+40h+arg_8]
0x18004ba0d  add     rsp, 40h
0x18004ba11  pop     rbp
0x18004ba12  retn
```
