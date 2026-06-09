# SampValidatePassedSD(ulong,_SECURITY_DESCRIPTOR_RELATIVE *)

- ea: `0x18008ba3c`
- end: `0x18008c11a`
- name: `?SampValidatePassedSD@@YAJKPEAU_SECURITY_DESCRIPTOR_RELATIVE@@@Z`
- size: `1758`
- prototype: `__int64 __fastcall(ULONG SecurityDescriptorLength, PSECURITY_DESCRIPTOR SecurityDescriptorInput)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800291c0`
- `0x1800b14a0`

## callees

- `0x180027e24`
- `0x18008ba3c`

## import_xrefs

- `ntdll!RtlValidAcl` at `0x18008bb8c`
- `ntdll!RtlValidAcl` at `0x18008bcf2`
- `ntdll!RtlValidAcl` at `0x18008bb8c`
- `ntdll!RtlValidAcl` at `0x18008bcf2`
- `ntdll!RtlGetSaclSecurityDescriptor` at `0x18008bc63`
- `ntdll!RtlGetSaclSecurityDescriptor` at `0x18008bc63`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18008bafd`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18008bafd`
- `ntdll!RtlGetGroupSecurityDescriptor` at `0x18008bf14`
- `ntdll!RtlGetGroupSecurityDescriptor` at `0x18008bf14`
- `ntdll!RtlLengthSid` at `0x18008be7b`
- `ntdll!RtlLengthSid` at `0x18008bfcb`
- `ntdll!RtlLengthSid` at `0x18008be7b`
- `ntdll!RtlLengthSid` at `0x18008bfcb`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18008c05f`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18008c05f`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x18008bdc4`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x18008bdc4`

## pseudocode

```c
__int64 __fastcall SampValidatePassedSD(ULONG SecurityDescriptorLength, __int16 *SecurityDescriptorInput)
{
  struct _ACL *v5; // rbx
  __int64 AclSize; // rax
  __int64 v7; // rax
  ULONG v8; // eax
  ULONG v9; // eax
  PACL Dacl[5]; // [rsp+30h] [rbp-28h] BYREF
  unsigned __int8 DaclPresent; // [rsp+60h] [rbp+8h] BYREF
  unsigned __int8 DaclDefaulted; // [rsp+70h] [rbp+18h] BYREF
  PSID Owner; // [rsp+78h] [rbp+20h] BYREF

  Dacl[0] = 0;
  Owner = 0;
  DaclPresent = 0;
  DaclDefaulted = 0;
  if ( SecurityDescriptorLength < 0x28 )
  {
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      WPP_SF_Dd(
        WPP_GLOBAL_Control[3].Buffer,
        43,
        WPP_18fb10c206133c98d7a2b000be93359d_Traceguids,
        3221225703LL,
        -1073741593);
    return 3221225703LL;
  }
  v5 = (struct _ACL *)((char *)SecurityDescriptorInput + SecurityDescriptorLength);
  if ( SecurityDescriptorInput[1] >= 0 )
  {
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      WPP_SF_Dd(
        WPP_GLOBAL_Control[3].Buffer,
        44,
        WPP_18fb10c206133c98d7a2b000be93359d_Traceguids,
        3221225703LL,
        -1073741593);
    return 3221225703LL;
  }
  if ( RtlGetDaclSecurityDescriptor(SecurityDescriptorInput, &DaclPresent, Dacl, &DaclDefaulted) < 0 )
  {
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      WPP_SF_Dd(
        WPP_GLOBAL_Control[3].Buffer,
        45,
        WPP_18fb10c206133c98d7a2b000be93359d_Traceguids,
        3221225703LL,
        -1073741593);
    return 3221225703LL;
  }
  if ( DaclPresent && Dacl[0] )
  {
    if ( Dacl[0] > v5 || &Dacl[0][1] > v5 || Dacl[0] < (PACL)SecurityDescriptorInput )
    {
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
        WPP_SF_Dd(
          WPP_GLOBAL_Control[3].Buffer,
          46,
          WPP_18fb10c206133c98d7a2b000be93359d_Traceguids,
          3221225703LL,
          -1073741593);
      return 3221225703LL;
    }
    AclSize = Dacl[0]->AclSize;
    if ( (unsigned int)AclSize > SecurityDescriptorLength || (PACL)((char *)Dacl[0] + AclSize) > v5 )
    {
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
        WPP_SF_Dd(
          WPP_GLOBAL_Control[3].Buffer,
          47,
          WPP_18fb10c206133c98d7a2b000be93359d_Traceguids,
          3221225703LL,
          -1073741593);
      return 3221225703LL;
    }
    if ( !RtlValidAcl(Dacl[0]) )
    {
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
        WPP_SF_Dd(
          WPP_GLOBAL_Control[3].Buffer,
          48,
          WPP_18fb10c206133c98d7a2b000be93359d_Traceguids,
          3221225703LL,
          -1073741593);
      return 3221225703LL;
    }
  }
  if ( RtlGetSaclSecurityDescriptor(SecurityDescriptorInput, &DaclPresent, Dacl, &DaclDefaulted) < 0 )
  {
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      WPP_SF_Dd(
        WPP_GLOBAL_Control[3].Buffer,
        49,
        WPP_18fb10c206133c98d7a2b000be93359d_Traceguids,
        3221225703LL,
        -1073741593);
    return 3221225703LL;
  }
  if ( DaclPresent && Dacl[0] )
  {
    if ( Dacl[0] > v5 || &Dacl[0][1] > v5 || Dacl[0] < (PACL)SecurityDescriptorInput )
    {
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
        WPP_SF_Dd(
          WPP_GLOBAL_Control[3].Buffer,
          50,
          WPP_18fb10c206133c98d7a2b000be93359d_Traceguids,
          3221225703LL,
          -1073741593);
      return 3221225703LL;
    }
    v7 = Dacl[0]->AclSize;
    if ( (unsigned int)v7 > SecurityDescriptorLength || (PACL)((char *)Dacl[0] + v7) > v5 )
    {
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
        WPP_SF_Dd(
          WPP_GLOBAL_Control[3].Buffer,
          51,
          WPP_18fb10c206133c98d7a2b000be93359d_Traceguids,
          3221225703LL,
          -1073741593);
      return 3221225703LL;
    }
    if ( !RtlValidAcl(Dacl[0]) )
    {
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
        WPP_SF_Dd(
          WPP_GLOBAL_Control[3].Buffer,
          52,
          WPP_18fb10c206133c98d7a2b000be93359d_Traceguids,
          3221225703LL,
          -1073741593);
      return 3221225703LL;
    }
  }
  if ( RtlGetOwnerSecurityDescriptor(SecurityDescriptorInput, &Owner, &DaclDefaulted) < 0 )
  {
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      WPP_SF_Dd(
        WPP_GLOBAL_Control[3].Buffer,
        53,
        WPP_18fb10c206133c98d7a2b000be93359d_Traceguids,
        3221225703LL,
        -1073741593);
    return 3221225703LL;
  }
  if ( Owner )
  {
    if ( Owner > v5 || (char *)Owner + 8 > (char *)v5 || Owner < SecurityDescriptorInput )
    {
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
        WPP_SF_Dd(
          WPP_GLOBAL_Control[3].Buffer,
          54,
          WPP_18fb10c206133c98d7a2b000be93359d_Traceguids,
          3221225703LL,
          -1073741593);
      return 3221225703LL;
    }
    if ( *((_BYTE *)Owner + 1) > 0xFu )
    {
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
        WPP_SF_Dd(
          WPP_GLOBAL_Control[3].Buffer,
          55,
          WPP_18fb10c206133c98d7a2b000be93359d_Traceguids,
          3221225703LL,
          -1073741593);
      return 3221225703LL;
    }
    v8 = RtlLengthSid(Owner);
    if ( (char *)Owner + v8 > (char *)v5 )
    {
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
        WPP_SF_Dd(
          WPP_GLOBAL_Control[3].Buffer,
          56,
          WPP_18fb10c206133c98d7a2b000be93359d_Traceguids,
          3221225703LL,
          -1073741593);
      return 3221225703LL;
    }
  }
  if ( RtlGetGroupSecurityDescriptor(SecurityDescriptorInput, &Owner, &DaclDefaulted) < 0 )
  {
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      WPP_SF_Dd(
        WPP_GLOBAL_Control[3].Buffer,
        57,
        WPP_18fb10c206133c98d7a2b000be93359d_Traceguids,
        3221225703LL,
        -1073741593);
    return 3221225703LL;
  }
  if ( !Owner )
  {
LABEL_89:
    if ( RtlValidRelativeSecurityDescriptor(SecurityDescriptorInput, SecurityDescriptorLength, 0) )
    {
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
        WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 63, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids, 0, 0);
      return 0;
    }
    else
    {
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
        WPP_SF_Dd(
          WPP_GLOBAL_Control[3].Buffer,
          61,
          WPP_18fb10c206133c98d7a2b000be93359d_Traceguids,
          3221225703LL,
          -1073741593);
      return 3221225703LL;
    }
  }
  if ( Owner <= v5 && (char *)Owner + 8 <= (char *)v5 && Owner >= SecurityDescriptorInput )
  {
    if ( *((_BYTE *)Owner + 1) > 0xFu )
    {
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
        WPP_SF_Dd(
          WPP_GLOBAL_Control[3].Buffer,
          59,
          WPP_18fb10c206133c98d7a2b000be93359d_Traceguids,
          3221225703LL,
          -1073741593);
      return 3221225703LL;
    }
    v9 = RtlLengthSid(Owner);
    if ( (char *)Owner + v9 > (char *)v5 )
    {
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
        WPP_SF_Dd(
          WPP_GLOBAL_Control[3].Buffer,
          60,
          WPP_18fb10c206133c98d7a2b000be93359d_Traceguids,
          3221225703LL,
          -1073741593);
      return 3221225703LL;
    }
    goto LABEL_89;
  }
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control[3].Buffer,
      58,
      WPP_18fb10c206133c98d7a2b000be93359d_Traceguids,
      3221225703LL,
      -1073741593);
  return 3221225703LL;
}

```

## disassembly

```asm
0x18008ba3c  mov     rax, rsp
0x18008ba3f  mov     [rax+10h], rbx
0x18008ba43  push    rsi
0x18008ba44  push    rdi
0x18008ba45  push    r14
0x18008ba47  sub     rsp, 40h
0x18008ba4b  mov     rdi, rdx
0x18008ba4e  mov     esi, ecx
0x18008ba50  xor     r14d, r14d
0x18008ba53  mov     [rax-28h], r14
0x18008ba57  mov     [rax+20h], r14
0x18008ba5b  mov     [rax+8], r14b
0x18008ba5f  mov     [rax+18h], r14b
0x18008ba63  cmp     ecx, 28h ; '('
0x18008ba66  jnb     short loc_18008BAA3
0x18008ba68  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ba6f  test    dword ptr [rcx+44h], 20000h
0x18008ba76  jz      short loc_18008BA99
0x18008ba78  lea     edx, [r14+2Bh]
0x18008ba7c  mov     dword ptr [rax-38h], 0C00000E7h
0x18008ba83  mov     r9d, 0C00000E7h
0x18008ba89  lea     r8, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids
0x18008ba90  mov     rcx, [rcx+38h]
0x18008ba94  call    WPP_SF_Dd
0x18008ba99  mov     eax, 0C00000E7h
0x18008ba9e  jmp     loc_18008C10C
0x18008baa3  lea     rbx, [rdx+rsi]
0x18008baa7  cmp     [rdx+2], r14w
0x18008baac  jl      short loc_18008BAEB
0x18008baae  mov     rcx, cs:WPP_GLOBAL_Control
0x18008bab5  test    dword ptr [rcx+44h], 20000h
0x18008babc  jz      short loc_18008BAE1
0x18008babe  mov     edx, 2Ch ; ','
0x18008bac3  mov     [rsp+58h+var_38], 0C00000E7h
0x18008bacb  mov     r9d, 0C00000E7h
0x18008bad1  lea     r8, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids
0x18008bad8  mov     rcx, [rcx+38h]
0x18008badc  call    WPP_SF_Dd
0x18008bae1  mov     eax, 0C00000E7h
0x18008bae6  jmp     loc_18008C10C
0x18008baeb  lea     r9, [rsp+58h+DaclDefaulted]; DaclDefaulted
0x18008baf0  lea     r8, [rsp+58h+Dacl]; Dacl
0x18008baf5  lea     rdx, [rsp+58h+DaclPresent]; DaclPresent
0x18008bafa  mov     rcx, rdi; SecurityDescriptor
0x18008bafd  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x18008bb03  test    eax, eax
0x18008bb05  jns     short loc_18008BB44
0x18008bb07  mov     rcx, cs:WPP_GLOBAL_Control
0x18008bb0e  test    dword ptr [rcx+44h], 20000h
0x18008bb15  jz      short loc_18008BB3A
0x18008bb17  mov     edx, 2Dh ; '-'
0x18008bb1c  mov     [rsp+58h+var_38], 0C00000E7h
0x18008bb24  mov     r9d, 0C00000E7h
0x18008bb2a  lea     r8, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids
0x18008bb31  mov     rcx, [rcx+38h]
0x18008bb35  call    WPP_SF_Dd
0x18008bb3a  mov     eax, 0C00000E7h
0x18008bb3f  jmp     loc_18008C10C
0x18008bb44  cmp     [rsp+58h+DaclPresent], r14b
0x18008bb49  jz      loc_18008BC51
0x18008bb4f  mov     rcx, [rsp+58h+Dacl]; Acl
0x18008bb54  test    rcx, rcx
0x18008bb57  jz      loc_18008BC51
0x18008bb5d  cmp     rcx, rbx
0x18008bb60  ja      loc_18008BC14
0x18008bb66  lea     rax, [rcx+8]
0x18008bb6a  cmp     rax, rbx
0x18008bb6d  ja      loc_18008BC14
0x18008bb73  cmp     rcx, rdi
0x18008bb76  jb      loc_18008BC14
0x18008bb7c  movzx   eax, word ptr [rcx+2]
0x18008bb80  cmp     eax, esi
0x18008bb82  ja      short loc_18008BBD7
0x18008bb84  add     rax, rcx
0x18008bb87  cmp     rax, rbx
0x18008bb8a  ja      short loc_18008BBD7
0x18008bb8c  call    cs:__imp_RtlValidAcl
0x18008bb92  test    al, al
0x18008bb94  jnz     loc_18008BC51
0x18008bb9a  mov     rcx, cs:WPP_GLOBAL_Control
0x18008bba1  test    dword ptr [rcx+44h], 20000h
0x18008bba8  jz      short loc_18008BBCD
0x18008bbaa  mov     edx, 30h ; '0'
0x18008bbaf  mov     [rsp+58h+var_38], 0C00000E7h
0x18008bbb7  mov     r9d, 0C00000E7h
0x18008bbbd  lea     r8, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids
0x18008bbc4  mov     rcx, [rcx+38h]
0x18008bbc8  call    WPP_SF_Dd
0x18008bbcd  mov     eax, 0C00000E7h
0x18008bbd2  jmp     loc_18008C10C
0x18008bbd7  mov     rcx, cs:WPP_GLOBAL_Control
0x18008bbde  test    dword ptr [rcx+44h], 20000h
0x18008bbe5  jz      short loc_18008BC0A
0x18008bbe7  mov     edx, 2Fh ; '/'
0x18008bbec  mov     [rsp+58h+var_38], 0C00000E7h
0x18008bbf4  mov     r9d, 0C00000E7h
0x18008bbfa  lea     r8, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids
0x18008bc01  mov     rcx, [rcx+38h]
0x18008bc05  call    WPP_SF_Dd
0x18008bc0a  mov     eax, 0C00000E7h
0x18008bc0f  jmp     loc_18008C10C
0x18008bc14  mov     rcx, cs:WPP_GLOBAL_Control
0x18008bc1b  test    dword ptr [rcx+44h], 20000h
0x18008bc22  jz      short loc_18008BC47
0x18008bc24  mov     edx, 2Eh ; '.'
0x18008bc29  mov     [rsp+58h+var_38], 0C00000E7h
0x18008bc31  mov     r9d, 0C00000E7h
0x18008bc37  lea     r8, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids
0x18008bc3e  mov     rcx, [rcx+38h]
0x18008bc42  call    WPP_SF_Dd
0x18008bc47  mov     eax, 0C00000E7h
0x18008bc4c  jmp     loc_18008C10C
0x18008bc51  lea     r9, [rsp+58h+DaclDefaulted]; SaclDefaulted
0x18008bc56  lea     r8, [rsp+58h+Dacl]; Sacl
0x18008bc5b  lea     rdx, [rsp+58h+DaclPresent]; SaclPresent
0x18008bc60  mov     rcx, rdi; SecurityDescriptor
0x18008bc63  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x18008bc69  test    eax, eax
0x18008bc6b  jns     short loc_18008BCAA
0x18008bc6d  mov     rcx, cs:WPP_GLOBAL_Control
0x18008bc74  test    dword ptr [rcx+44h], 20000h
0x18008bc7b  jz      short loc_18008BCA0
0x18008bc7d  mov     edx, 31h ; '1'
0x18008bc82  mov     [rsp+58h+var_38], 0C00000E7h
0x18008bc8a  mov     r9d, 0C00000E7h
0x18008bc90  lea     r8, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids
0x18008bc97  mov     rcx, [rcx+38h]
0x18008bc9b  call    WPP_SF_Dd
0x18008bca0  mov     eax, 0C00000E7h
0x18008bca5  jmp     loc_18008C10C
0x18008bcaa  cmp     [rsp+58h+DaclPresent], r14b
0x18008bcaf  jz      loc_18008BDB7
0x18008bcb5  mov     rcx, [rsp+58h+Dacl]; Acl
0x18008bcba  test    rcx, rcx
0x18008bcbd  jz      loc_18008BDB7
0x18008bcc3  cmp     rcx, rbx
0x18008bcc6  ja      loc_18008BD7A
0x18008bccc  lea     rax, [rcx+8]
0x18008bcd0  cmp     rax, rbx
0x18008bcd3  ja      loc_18008BD7A
0x18008bcd9  cmp     rcx, rdi
0x18008bcdc  jb      loc_18008BD7A
0x18008bce2  movzx   eax, word ptr [rcx+2]
0x18008bce6  cmp     eax, esi
0x18008bce8  ja      short loc_18008BD3D
0x18008bcea  add     rax, rcx
0x18008bced  cmp     rax, rbx
0x18008bcf0  ja      short loc_18008BD3D
0x18008bcf2  call    cs:__imp_RtlValidAcl
0x18008bcf8  test    al, al
0x18008bcfa  jnz     loc_18008BDB7
0x18008bd00  mov     rcx, cs:WPP_GLOBAL_Control
0x18008bd07  test    dword ptr [rcx+44h], 20000h
0x18008bd0e  jz      short loc_18008BD33
0x18008bd10  mov     edx, 34h ; '4'
0x18008bd15  mov     [rsp+58h+var_38], 0C00000E7h
0x18008bd1d  mov     r9d, 0C00000E7h
0x18008bd23  lea     r8, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids
0x18008bd2a  mov     rcx, [rcx+38h]
0x18008bd2e  call    WPP_SF_Dd
0x18008bd33  mov     eax, 0C00000E7h
0x18008bd38  jmp     loc_18008C10C
0x18008bd3d  mov     rcx, cs:WPP_GLOBAL_Control
0x18008bd44  test    dword ptr [rcx+44h], 20000h
0x18008bd4b  jz      short loc_18008BD70
0x18008bd4d  mov     edx, 33h ; '3'
0x18008bd52  mov     [rsp+58h+var_38], 0C00000E7h
0x18008bd5a  mov     r9d, 0C00000E7h
0x18008bd60  lea     r8, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids
0x18008bd67  mov     rcx, [rcx+38h]
0x18008bd6b  call    WPP_SF_Dd
0x18008bd70  mov     eax, 0C00000E7h
0x18008bd75  jmp     loc_18008C10C
0x18008bd7a  mov     rcx, cs:WPP_GLOBAL_Control
0x18008bd81  test    dword ptr [rcx+44h], 20000h
0x18008bd88  jz      short loc_18008BDAD
0x18008bd8a  mov     edx, 32h ; '2'
0x18008bd8f  mov     [rsp+58h+var_38], 0C00000E7h
0x18008bd97  mov     r9d, 0C00000E7h
0x18008bd9d  lea     r8, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids
0x18008bda4  mov     rcx, [rcx+38h]
0x18008bda8  call    WPP_SF_Dd
0x18008bdad  mov     eax, 0C00000E7h
0x18008bdb2  jmp     loc_18008C10C
0x18008bdb7  lea     r8, [rsp+58h+DaclDefaulted]; OwnerDefaulted
0x18008bdbc  lea     rdx, [rsp+58h+Owner]; Owner
0x18008bdc1  mov     rcx, rdi; SecurityDescriptor
0x18008bdc4  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x18008bdca  test    eax, eax
0x18008bdcc  jns     short loc_18008BE0B
0x18008bdce  mov     rcx, cs:WPP_GLOBAL_Control
0x18008bdd5  test    dword ptr [rcx+44h], 20000h
0x18008bddc  jz      short loc_18008BE01
0x18008bdde  mov     edx, 35h ; '5'
0x18008bde3  mov     [rsp+58h+var_38], 0C00000E7h
0x18008bdeb  mov     r9d, 0C00000E7h
0x18008bdf1  lea     r8, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids
0x18008bdf8  mov     rcx, [rcx+38h]
0x18008bdfc  call    WPP_SF_Dd
0x18008be01  mov     eax, 0C00000E7h
0x18008be06  jmp     loc_18008C10C
0x18008be0b  mov     rcx, [rsp+58h+Owner]; Sid
0x18008be10  test    rcx, rcx
0x18008be13  jz      loc_18008BF07
0x18008be19  cmp     rcx, rbx
0x18008be1c  ja      loc_18008BECA
0x18008be22  lea     rax, [rcx+8]
0x18008be26  cmp     rax, rbx
0x18008be29  ja      loc_18008BECA
0x18008be2f  cmp     rcx, rdi
0x18008be32  jb      loc_18008BECA
0x18008be38  cmp     byte ptr [rcx+1], 0Fh
0x18008be3c  jbe     short loc_18008BE7B
0x18008be3e  mov     rcx, cs:WPP_GLOBAL_Control
0x18008be45  test    dword ptr [rcx+44h], 20000h
0x18008be4c  jz      short loc_18008BE71
0x18008be4e  mov     edx, 37h ; '7'
0x18008be53  mov     [rsp+58h+var_38], 0C00000E7h
0x18008be5b  mov     r9d, 0C00000E7h
0x18008be61  lea     r8, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids
0x18008be68  mov     rcx, [rcx+38h]
0x18008be6c  call    WPP_SF_Dd
0x18008be71  mov     eax, 0C00000E7h
0x18008be76  jmp     loc_18008C10C
0x18008be7b  call    cs:__imp_RtlLengthSid
0x18008be81  mov     eax, eax
0x18008be83  add     rax, [rsp+58h+Owner]
0x18008be88  cmp     rax, rbx
0x18008be8b  jbe     short loc_18008BF07
0x18008be8d  mov     rcx, cs:WPP_GLOBAL_Control
0x18008be94  test    dword ptr [rcx+44h], 20000h
0x18008be9b  jz      short loc_18008BEC0
0x18008be9d  mov     edx, 38h ; '8'
0x18008bea2  mov     [rsp+58h+var_38], 0C00000E7h
0x18008beaa  mov     r9d, 0C00000E7h
0x18008beb0  lea     r8, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids
0x18008beb7  mov     rcx, [rcx+38h]
0x18008bebb  call    WPP_SF_Dd
0x18008bec0  mov     eax, 0C00000E7h
0x18008bec5  jmp     loc_18008C10C
0x18008beca  mov     rcx, cs:WPP_GLOBAL_Control
0x18008bed1  test    dword ptr [rcx+44h], 20000h
0x18008bed8  jz      short loc_18008BEFD
0x18008beda  mov     edx, 36h ; '6'
0x18008bedf  mov     [rsp+58h+var_38], 0C00000E7h
0x18008bee7  mov     r9d, 0C00000E7h
0x18008beed  lea     r8, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids
0x18008bef4  mov     rcx, [rcx+38h]
0x18008bef8  call    WPP_SF_Dd
0x18008befd  mov     eax, 0C00000E7h
0x18008bf02  jmp     loc_18008C10C
0x18008bf07  lea     r8, [rsp+58h+DaclDefaulted]; GroupDefaulted
0x18008bf0c  lea     rdx, [rsp+58h+Owner]; Group
0x18008bf11  mov     rcx, rdi; SecurityDescriptor
0x18008bf14  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x18008bf1a  test    eax, eax
0x18008bf1c  jns     short loc_18008BF5B
0x18008bf1e  mov     rcx, cs:WPP_GLOBAL_Control
0x18008bf25  test    dword ptr [rcx+44h], 20000h
0x18008bf2c  jz      short loc_18008BF51
0x18008bf2e  mov     edx, 39h ; '9'
0x18008bf33  mov     [rsp+58h+var_38], 0C00000E7h
0x18008bf3b  mov     r9d, 0C00000E7h
0x18008bf41  lea     r8, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids
0x18008bf48  mov     rcx, [rcx+38h]
0x18008bf4c  call    WPP_SF_Dd
0x18008bf51  mov     eax, 0C00000E7h
0x18008bf56  jmp     loc_18008C10C
0x18008bf5b  mov     rcx, [rsp+58h+Owner]; Sid
0x18008bf60  test    rcx, rcx
0x18008bf63  jz      loc_18008C057
0x18008bf69  cmp     rcx, rbx
0x18008bf6c  ja      loc_18008C01A
0x18008bf72  lea     rax, [rcx+8]
0x18008bf76  cmp     rax, rbx
0x18008bf79  ja      loc_18008C01A
0x18008bf7f  cmp     rcx, rdi
0x18008bf82  jb      loc_18008C01A
0x18008bf88  cmp     byte ptr [rcx+1], 0Fh
0x18008bf8c  jbe     short loc_18008BFCB
0x18008bf8e  mov     rcx, cs:WPP_GLOBAL_Control
0x18008bf95  test    dword ptr [rcx+44h], 20000h
0x18008bf9c  jz      short loc_18008BFC1
0x18008bf9e  mov     edx, 3Bh ; ';'
0x18008bfa3  mov     [rsp+58h+var_38], 0C00000E7h
0x18008bfab  mov     r9d, 0C00000E7h
0x18008bfb1  lea     r8, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids
0x18008bfb8  mov     rcx, [rcx+38h]
0x18008bfbc  call    WPP_SF_Dd
0x18008bfc1  mov     eax, 0C00000E7h
0x18008bfc6  jmp     loc_18008C10C
0x18008bfcb  call    cs:__imp_RtlLengthSid
0x18008bfd1  mov     eax, eax
0x18008bfd3  add     rax, [rsp+58h+Owner]
0x18008bfd8  cmp     rax, rbx
0x18008bfdb  jbe     short loc_18008C057
0x18008bfdd  mov     rcx, cs:WPP_GLOBAL_Control
0x18008bfe4  test    dword ptr [rcx+44h], 20000h
0x18008bfeb  jz      short loc_18008C010
0x18008bfed  mov     edx, 3Ch ; '<'
  ... truncated ...
```
