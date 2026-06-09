# SampCheckForDescriptorRestrictions(_SAMP_OBJECT *,_SAMP_OBJECT_TYPE,ulong,_SECURITY_DESCRIPTOR_RELATIVE *)

- ea: `0x18008a720`
- end: `0x18008aa9b`
- name: `?SampCheckForDescriptorRestrictions@@YAJPEAU_SAMP_OBJECT@@W4_SAMP_OBJECT_TYPE@@KPEAU_SECURITY_DESCRIPTOR_RELATIVE@@@Z`
- size: `891`
- prototype: `__int64 __fastcall(__int64, int, int, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18008cd00`

## callees

- `0x18001eb60`
- `0x180027e24`
- `0x18002cd80`
- `0x18005645c`
- `0x18008a720`
- `0x18008aaa4`
- `0x18008b460`

## import_xrefs

- `ntdll!RtlQueryInformationAcl` at `0x18008a89d`
- `ntdll!RtlQueryInformationAcl` at `0x18008a89d`
- `ntdll!RtlValidAcl` at `0x18008a858`
- `ntdll!RtlValidAcl` at `0x18008a858`
- `ntdll!RtlGetAce` at `0x18008a946`
- `ntdll!RtlGetAce` at `0x18008a946`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18008a7cb`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18008a7cb`
- `ntdll!RtlMapGenericMask` at `0x18008a9a8`
- `ntdll!RtlMapGenericMask` at `0x18008a9a8`
- `ntdll!RtlEqualSid` at `0x18008a973`
- `ntdll!RtlEqualSid` at `0x18008a98c`
- `ntdll!RtlEqualSid` at `0x18008a9cd`
- `ntdll!RtlEqualSid` at `0x18008a973`
- `ntdll!RtlEqualSid` at `0x18008a98c`
- `ntdll!RtlEqualSid` at `0x18008a9cd`

## pseudocode

```c
__int64 __fastcall SampCheckForDescriptorRestrictions(__int64 a1, int a2, int a3, void *a4)
{
  bool v6; // zf
  PUNICODE_STRING v8; // rcx
  __int64 v9; // rdx
  PUNICODE_STRING v10; // rcx
  int IsLocalAccountLocalAdmin; // ebx
  __int64 v12; // rdx
  __int64 v13; // r9
  _BYTE *v15; // r15
  int v16; // esi
  ULONG v17; // r14d
  DWORD v18; // eax
  unsigned __int8 DaclPresent; // [rsp+30h] [rbp-39h] BYREF
  unsigned __int8 v20; // [rsp+31h] [rbp-38h] BYREF
  unsigned __int8 DaclDefaulted[2]; // [rsp+32h] [rbp-37h] BYREF
  DWORD AccessMask; // [rsp+34h] [rbp-35h] BYREF
  int v23; // [rsp+38h] [rbp-31h] BYREF
  PVOID Ace; // [rsp+40h] [rbp-29h] BYREF
  PACL Dacl; // [rsp+48h] [rbp-21h] BYREF
  __int64 Information; // [rsp+50h] [rbp-19h] BYREF
  int v27; // [rsp+58h] [rbp-11h]
  struct _GENERIC_MAPPING GenericMapping; // [rsp+60h] [rbp-9h] BYREF
  _BYTE Sid2[32]; // [rsp+70h] [rbp+7h] BYREF

  GenericMapping.GenericRead = 131866;
  v20 = 0;
  DaclPresent = 0;
  DaclDefaulted[0] = 0;
  v23 = 0;
  v6 = (*(_BYTE *)(a1 + 20) & 0x20) == 0;
  Dacl = 0;
  Information = 0;
  v27 = 0;
  Ace = 0;
  AccessMask = 0;
  GenericMapping.GenericWrite = 131140;
  GenericMapping.GenericExecute = 131137;
  GenericMapping.GenericAll = 985087;
  if ( !v6 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    {
      v9 = 73;
LABEL_13:
      WPP_SF_Dd(v8[3].Buffer, v9, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids, 0, 0);
      return 0;
    }
    return 0;
  }
  if ( RtlGetDaclSecurityDescriptor(a4, &DaclPresent, &Dacl, DaclDefaulted) < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    IsLocalAccountLocalAdmin = -1073741593;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    {
      v12 = 74;
      v13 = 3221225703LL;
      goto LABEL_51;
    }
    return (unsigned int)IsLocalAccountLocalAdmin;
  }
  if ( !DaclPresent )
  {
    v8 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    {
      v9 = 75;
      goto LABEL_13;
    }
    return 0;
  }
  if ( !Dacl )
  {
    v8 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    {
      v9 = 76;
      goto LABEL_13;
    }
    return 0;
  }
  if ( !RtlValidAcl(Dacl) )
  {
    v10 = WPP_GLOBAL_Control;
    IsLocalAccountLocalAdmin = -1073741705;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    {
      v12 = 77;
      v13 = 3221225591LL;
      goto LABEL_51;
    }
    return (unsigned int)IsLocalAccountLocalAdmin;
  }
  IsLocalAccountLocalAdmin = RtlQueryInformationAcl(Dacl, &Information, 0xCu, AclSizeInformation);
  if ( IsLocalAccountLocalAdmin < 0 )
    goto LABEL_49;
  if ( a2 != 4 )
    goto LABEL_49;
  IsLocalAccountLocalAdmin = SampIsLocalAccountLocalAdmin((struct _SAMP_OBJECT *)a1, &v20);
  if ( IsLocalAccountLocalAdmin < 0 )
    goto LABEL_49;
  if ( !v20 )
    goto LABEL_45;
  memset(Sid2, 0, 28);
  if ( a3 == 500 )
  {
    v15 = SampAdministratorUserSid;
  }
  else
  {
    IsLocalAccountLocalAdmin = SampBuildNT4FullSid(*((void **)SampDefinedDomains + 170 * *(unsigned int *)(a1 + 200) + 1));
    if ( IsLocalAccountLocalAdmin < 0 )
      goto LABEL_49;
    v15 = Sid2;
  }
  if ( !(_DWORD)Information )
  {
LABEL_53:
    IsLocalAccountLocalAdmin = -1073741719;
    goto LABEL_49;
  }
  v16 = 2047;
  v17 = 0;
  while ( 1 )
  {
    IsLocalAccountLocalAdmin = RtlGetAce(Dacl, v17, &Ace);
    if ( (*((_BYTE *)Ace + 1) & 8) == 0
      && (!*(_BYTE *)Ace || *(_BYTE *)Ace == 1)
      && (RtlEqualSid((char *)Ace + 8, v15) || RtlEqualSid((char *)Ace + 8, SampAdministratorsAliasSid)) )
    {
      AccessMask = *((_DWORD *)Ace + 1);
      RtlMapGenericMask(&AccessMask, &GenericMapping);
      if ( *(_BYTE *)Ace )
      {
        if ( (v16 & AccessMask) != 0 )
          goto LABEL_53;
        goto LABEL_42;
      }
      if ( (*(_BYTE *)(a1 + 192) & 2) != 0 || (v16 & 0x40) == 0 || RtlEqualSid((char *)Ace + 8, v15) )
      {
        v18 = AccessMask;
      }
      else
      {
        v18 = AccessMask & 0xFFFFFFBF;
        AccessMask &= ~0x40u;
      }
      v16 &= ~v18;
      if ( !v16 )
        break;
    }
LABEL_42:
    if ( ++v17 >= (unsigned int)Information )
      goto LABEL_53;
  }
  if ( IsLocalAccountLocalAdmin >= 0 )
  {
LABEL_45:
    if ( (*(_BYTE *)(a1 + 192) & 2) == 0 )
    {
      IsLocalAccountLocalAdmin = SampCheckForcePasswordReset((struct _SAMP_OBJECT *)a1, &v23);
      if ( IsLocalAccountLocalAdmin >= 0 )
      {
        if ( v23 )
          IsLocalAccountLocalAdmin = SampCheckForceResetCanChangePassword((struct _SAMP_OBJECT *)a1, Dacl, Information);
      }
    }
  }
LABEL_49:
  v10 = WPP_GLOBAL_Control;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    v12 = 78;
    v13 = (unsigned int)IsLocalAccountLocalAdmin;
LABEL_51:
    WPP_SF_Dd(v10[3].Buffer, v12, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids, v13, IsLocalAccountLocalAdmin);
  }
  return (unsigned int)IsLocalAccountLocalAdmin;
}

```

## disassembly

```asm
0x18008a720  mov     [rsp-8+arg_8], rbx
0x18008a725  mov     [rsp-8+arg_10], rsi
0x18008a72a  push    rbp
0x18008a72b  push    rdi
0x18008a72c  push    r12
0x18008a72e  push    r14
0x18008a730  push    r15
0x18008a732  lea     rbp, [rsp-37h]
0x18008a737  sub     rsp, 0A0h
0x18008a73e  mov     rax, cs:__security_cookie
0x18008a745  xor     rax, rsp
0x18008a748  mov     [rbp+57h+var_30], rax
0x18008a74c  xor     r12d, r12d
0x18008a74f  mov     [rbp+57h+GenericMapping.GenericRead], 2031Ah
0x18008a756  mov     rdi, rcx
0x18008a759  mov     [rbp+57h+var_8F], r12b
0x18008a75d  xor     ecx, ecx
0x18008a75f  mov     [rbp+57h+DaclPresent], r12b
0x18008a763  mov     rax, r9
0x18008a766  mov     [rbp+57h+DaclDefaulted], r12b
0x18008a76a  mov     r14d, r8d
0x18008a76d  mov     [rbp+57h+var_88], r12d
0x18008a771  test    byte ptr [rdi+14h], 20h
0x18008a775  mov     esi, edx
0x18008a777  mov     [rbp+57h+Dacl], r12
0x18008a77b  mov     [rbp+57h+Information], rcx
0x18008a77f  mov     [rbp+57h+var_68], ecx
0x18008a782  mov     [rbp+57h+Ace], r12
0x18008a786  mov     [rbp+57h+AccessMask], r12d
0x18008a78a  mov     [rbp+57h+GenericMapping.GenericWrite], 20044h
0x18008a791  mov     [rbp+57h+GenericMapping.GenericExecute], 20041h
0x18008a798  mov     [rbp+57h+GenericMapping.GenericAll], 0F07FFh
0x18008a79f  jz      short loc_18008A7BC
0x18008a7a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a7a8  test    dword ptr [rcx+44h], 20000h
0x18008a7af  jz      loc_18008A851
0x18008a7b5  lea     edx, [r12+49h]
0x18008a7ba  jmp     short loc_18008A839
0x18008a7bc  lea     r9, [rbp+57h+DaclDefaulted]; DaclDefaulted
0x18008a7c0  mov     rcx, rax; SecurityDescriptor
0x18008a7c3  lea     r8, [rbp+57h+Dacl]; Dacl
0x18008a7c7  lea     rdx, [rbp+57h+DaclPresent]; DaclPresent
0x18008a7cb  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x18008a7d1  test    eax, eax
0x18008a7d3  jns     short loc_18008A7FE
0x18008a7d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a7dc  mov     ebx, 0C00000E7h
0x18008a7e1  test    dword ptr [rcx+44h], 20000h
0x18008a7e8  jz      loc_18008AA6A
0x18008a7ee  mov     edx, 4Ah ; 'J'
0x18008a7f3  mov     r9d, 0C00000E7h
0x18008a7f9  jmp     loc_18008AA56
0x18008a7fe  cmp     [rbp+57h+DaclPresent], r12b
0x18008a802  jnz     short loc_18008A81B
0x18008a804  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a80b  test    dword ptr [rcx+44h], 20000h
0x18008a812  jz      short loc_18008A851
0x18008a814  mov     edx, 4Bh ; 'K'
0x18008a819  jmp     short loc_18008A839
0x18008a81b  mov     rcx, [rbp+57h+Dacl]; Acl
0x18008a81f  test    rcx, rcx
0x18008a822  jnz     short loc_18008A858
0x18008a824  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a82b  test    dword ptr [rcx+44h], 20000h
0x18008a832  jz      short loc_18008A851
0x18008a834  mov     edx, 4Ch ; 'L'
0x18008a839  mov     rcx, [rcx+38h]
0x18008a83d  lea     r8, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids
0x18008a844  xor     r9d, r9d
0x18008a847  mov     [rsp+0C0h+var_A0], r12d
0x18008a84c  call    WPP_SF_Dd
0x18008a851  xor     eax, eax
0x18008a853  jmp     loc_18008AA6C
0x18008a858  call    cs:__imp_RtlValidAcl
0x18008a85e  test    al, al
0x18008a860  jnz     short loc_18008A88B
0x18008a862  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a869  mov     ebx, 0C0000077h
0x18008a86e  test    dword ptr [rcx+44h], 20000h
0x18008a875  jz      loc_18008AA6A
0x18008a87b  mov     edx, 4Dh ; 'M'
0x18008a880  mov     r9d, 0C0000077h
0x18008a886  jmp     loc_18008AA56
0x18008a88b  mov     rcx, [rbp+57h+Dacl]; Acl
0x18008a88f  lea     rdx, [rbp+57h+Information]; Information
0x18008a893  mov     r9d, 2; InformationClass
0x18008a899  lea     r8d, [r9+0Ah]; InformationLength
0x18008a89d  call    cs:__imp_RtlQueryInformationAcl
0x18008a8a3  mov     ebx, eax
0x18008a8a5  test    eax, eax
0x18008a8a7  js      loc_18008AA3E
0x18008a8ad  cmp     esi, 4
0x18008a8b0  jnz     loc_18008AA3E
0x18008a8b6  lea     rdx, [rbp+57h+var_8F]; unsigned __int8 *
0x18008a8ba  mov     rcx, rdi; struct _SAMP_OBJECT *
0x18008a8bd  call    ?SampIsLocalAccountLocalAdmin@@YAJPEAU_SAMP_OBJECT@@PEAE@Z; SampIsLocalAccountLocalAdmin(_SAMP_OBJECT *,uchar *)
0x18008a8c2  mov     ebx, eax
0x18008a8c4  test    eax, eax
0x18008a8c6  js      loc_18008AA3E
0x18008a8cc  cmp     [rbp+57h+var_8F], r12b
0x18008a8d0  jz      loc_18008AA0B
0x18008a8d6  xorps   xmm0, xmm0
0x18008a8d9  movups  xmmword ptr [rbp+57h+Sid2], xmm0
0x18008a8dd  movups  xmmword ptr [rbp+57h+Sid2+0Ch], xmm0
0x18008a8e1  cmp     r14d, 1F4h
0x18008a8e8  jz      short loc_18008A922
0x18008a8ea  mov     eax, [rdi+0C8h]
0x18008a8f0  lea     r8, [rbp+57h+Sid2]
0x18008a8f4  mov     rcx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x18008a8fb  mov     edx, [rdi+0F8h]
0x18008a901  imul    r9, rax, 550h
0x18008a908  mov     rcx, [r9+rcx+8]; Src
0x18008a90d  call    SampBuildNT4FullSid
0x18008a912  mov     ebx, eax
0x18008a914  test    eax, eax
0x18008a916  js      loc_18008AA3E
0x18008a91c  lea     r15, [rbp+57h+Sid2]
0x18008a920  jmp     short loc_18008A929
0x18008a922  mov     r15, cs:SampAdministratorUserSid
0x18008a929  cmp     dword ptr [rbp+57h+Information], r12d
0x18008a92d  jbe     loc_18008AA94
0x18008a933  mov     esi, 7FFh
0x18008a938  mov     r14d, r12d
0x18008a93b  mov     rcx, [rbp+57h+Dacl]; Acl
0x18008a93f  lea     r8, [rbp+57h+Ace]; Ace
0x18008a943  mov     edx, r14d; AceIndex
0x18008a946  call    cs:__imp_RtlGetAce
0x18008a94c  mov     rdx, [rbp+57h+Ace]
0x18008a950  mov     ebx, eax
0x18008a952  test    byte ptr [rdx+1], 8
0x18008a956  jnz     loc_18008A9F2
0x18008a95c  movzx   ecx, byte ptr [rdx]
0x18008a95f  test    ecx, ecx
0x18008a961  jz      short loc_18008A96C
0x18008a963  cmp     ecx, 1
0x18008a966  jnz     loc_18008A9F2
0x18008a96c  lea     rcx, [rdx+8]; Sid1
0x18008a970  mov     rdx, r15; Sid2
0x18008a973  call    cs:__imp_RtlEqualSid
0x18008a979  test    al, al
0x18008a97b  jnz     short loc_18008A996
0x18008a97d  mov     rcx, [rbp+57h+Ace]
0x18008a981  mov     rdx, cs:SampAdministratorsAliasSid; Sid2
0x18008a988  add     rcx, 8; Sid1
0x18008a98c  call    cs:__imp_RtlEqualSid
0x18008a992  test    al, al
0x18008a994  jz      short loc_18008A9F2
0x18008a996  mov     rax, [rbp+57h+Ace]
0x18008a99a  lea     rdx, [rbp+57h+GenericMapping]; GenericMapping
0x18008a99e  mov     ecx, [rax+4]
0x18008a9a1  mov     [rbp+57h+AccessMask], ecx
0x18008a9a4  lea     rcx, [rbp+57h+AccessMask]; AccessMask
0x18008a9a8  call    cs:__imp_RtlMapGenericMask
0x18008a9ae  mov     rcx, [rbp+57h+Ace]
0x18008a9b2  cmp     [rcx], r12b
0x18008a9b5  jnz     short loc_18008A9ED
0x18008a9b7  test    byte ptr [rdi+0C0h], 2
0x18008a9be  jnz     short loc_18008A9E2
0x18008a9c0  test    sil, 40h
0x18008a9c4  jz      short loc_18008A9E2
0x18008a9c6  add     rcx, 8; Sid1
0x18008a9ca  mov     rdx, r15; Sid2
0x18008a9cd  call    cs:__imp_RtlEqualSid
0x18008a9d3  test    al, al
0x18008a9d5  jnz     short loc_18008A9E2
0x18008a9d7  mov     eax, [rbp+57h+AccessMask]
0x18008a9da  and     eax, 0FFFFFFBFh
0x18008a9dd  mov     [rbp+57h+AccessMask], eax
0x18008a9e0  jmp     short loc_18008A9E5
0x18008a9e2  mov     eax, [rbp+57h+AccessMask]
0x18008a9e5  not     eax
0x18008a9e7  and     esi, eax
0x18008a9e9  jz      short loc_18008AA07
0x18008a9eb  jmp     short loc_18008A9F2
0x18008a9ed  test    [rbp+57h+AccessMask], esi
0x18008a9f0  jnz     short loc_18008A9FF
0x18008a9f2  inc     r14d
0x18008a9f5  cmp     r14d, dword ptr [rbp+57h+Information]
0x18008a9f9  jb      loc_18008A93B
0x18008a9ff  test    esi, esi
0x18008aa01  jnz     loc_18008AA94
0x18008aa07  test    ebx, ebx
0x18008aa09  js      short loc_18008AA3E
0x18008aa0b  test    byte ptr [rdi+0C0h], 2
0x18008aa12  jnz     short loc_18008AA3E
0x18008aa14  lea     rdx, [rbp+57h+var_88]; int *
0x18008aa18  mov     rcx, rdi; struct _SAMP_OBJECT *
0x18008aa1b  call    ?SampCheckForcePasswordReset@@YAJPEAU_SAMP_OBJECT@@PEAH@Z; SampCheckForcePasswordReset(_SAMP_OBJECT *,int *)
0x18008aa20  mov     ebx, eax
0x18008aa22  test    eax, eax
0x18008aa24  js      short loc_18008AA3E
0x18008aa26  cmp     [rbp+57h+var_88], r12d
0x18008aa2a  jz      short loc_18008AA3E
0x18008aa2c  mov     r8d, dword ptr [rbp+57h+Information]; unsigned int
0x18008aa30  mov     rcx, rdi; struct _SAMP_OBJECT *
0x18008aa33  mov     rdx, [rbp+57h+Dacl]; struct _ACL *
0x18008aa37  call    ?SampCheckForceResetCanChangePassword@@YAJPEAU_SAMP_OBJECT@@PEAU_ACL@@K@Z; SampCheckForceResetCanChangePassword(_SAMP_OBJECT *,_ACL *,ulong)
0x18008aa3c  mov     ebx, eax
0x18008aa3e  mov     rcx, cs:WPP_GLOBAL_Control
0x18008aa45  test    dword ptr [rcx+44h], 20000h
0x18008aa4c  jz      short loc_18008AA6A
0x18008aa4e  mov     edx, 4Eh ; 'N'
0x18008aa53  mov     r9d, ebx
0x18008aa56  mov     rcx, [rcx+38h]
0x18008aa5a  lea     r8, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids
0x18008aa61  mov     [rsp+0C0h+var_A0], ebx
0x18008aa65  call    WPP_SF_Dd
0x18008aa6a  mov     eax, ebx
0x18008aa6c  mov     rcx, [rbp+57h+var_30]
0x18008aa70  xor     rcx, rsp; StackCookie
0x18008aa73  call    __security_check_cookie
0x18008aa78  lea     r11, [rsp+0C0h+var_20]
0x18008aa80  mov     rbx, [r11+38h]
0x18008aa84  mov     rsi, [r11+40h]
0x18008aa88  mov     rsp, r11
0x18008aa8b  pop     r15
0x18008aa8d  pop     r14
0x18008aa8f  pop     r12
0x18008aa91  pop     rdi
0x18008aa92  pop     rbp
0x18008aa93  retn
0x18008aa94  mov     ebx, 0C0000069h
0x18008aa99  jmp     short loc_18008AA3E
```
