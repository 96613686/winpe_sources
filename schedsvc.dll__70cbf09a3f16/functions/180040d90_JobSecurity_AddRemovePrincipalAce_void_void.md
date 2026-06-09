# JobSecurity::AddRemovePrincipalAce(void *,void *)

- ea: `0x180040d90`
- end: `0x1800411ad`
- name: `?AddRemovePrincipalAce@JobSecurity@@QEAAJPEAX0@Z`
- size: `1053`
- prototype: `int __fastcall(PSECURITY_DESCRIPTOR *this, void *, void *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180029978`
- `0x180045df0`

## callees

- `0x180025040`
- `0x18003f380`
- `0x180040d90`
- `0x1800433f0`

## import_xrefs

- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x180041048`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x180041048`
- `ntdll!RtlGetGroupSecurityDescriptor` at `0x1800410aa`
- `ntdll!RtlGetGroupSecurityDescriptor` at `0x1800410aa`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x180040e00`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x180040e00`
- `ntdll!RtlGetAce` at `0x180040e55`
- `ntdll!RtlGetAce` at `0x180040f7f`
- `ntdll!RtlGetAce` at `0x180040e55`
- `ntdll!RtlGetAce` at `0x180040f7f`
- `ntdll!RtlLengthSid` at `0x180040eed`
- `ntdll!RtlLengthSid` at `0x180040eed`
- `ntdll!RtlCreateAcl` at `0x180040f1d`
- `ntdll!RtlCreateAcl` at `0x180040f1d`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180040f36`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180040f36`
- `ntdll!RtlAddAccessAllowedAce` at `0x180040f57`
- `ntdll!RtlAddAccessAllowedAce` at `0x180040f57`
- `ntdll!RtlAddAce` at `0x180040fed`
- `ntdll!RtlAddAce` at `0x180040fed`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180041030`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180041030`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18004107e`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18004107e`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x1800410c7`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x1800410c7`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x1800410dd`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x180041130`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x1800410dd`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x180041130`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041091`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041091`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180040efc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800410f1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180040efc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800410f1`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180040e87`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180040ea9`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180040fae`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180040fcb`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180040e87`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180040ea9`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180040fae`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180040fcb`

## pseudocode

```c
int __fastcall JobSecurity::AddRemovePrincipalAce(PSECURITY_DESCRIPTOR *this, void *a2, void *a3)
{
  PSECURITY_DESCRIPTOR v3; // r13
  NTSTATUS DaclSecurityDescriptor; // eax
  signed int v8; // ebx
  int v9; // edi
  char v10; // r15
  NTSTATUS v11; // r14d
  unsigned __int16 *v12; // rax
  char *v13; // r14
  ULONG v14; // edi
  struct _ACL *v15; // rax
  struct _ACL *v16; // rbx
  NTSTATUS Acl; // edi
  signed int v18; // edi
  unsigned __int16 *v19; // r9
  char *v20; // r14
  NTSTATUS v21; // eax
  int v22; // edi
  NTSTATUS GroupSecurityDescriptor; // ebx
  HLOCAL v24; // rax
  unsigned __int8 DaclPresent[8]; // [rsp+30h] [rbp-39h] BYREF
  PSECURITY_DESCRIPTOR SelfRelativeSecurityDescriptor; // [rsp+38h] [rbp-31h] BYREF
  ULONG BufferLength; // [rsp+40h] [rbp-29h] BYREF
  PVOID Ace; // [rsp+48h] [rbp-21h] BYREF
  PSID Owner; // [rsp+50h] [rbp-19h] BYREF
  PACL Dacl; // [rsp+58h] [rbp-11h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+60h] [rbp-9h] BYREF
  __int64 v32; // [rsp+80h] [rbp+17h]
  unsigned __int8 DaclDefaulted; // [rsp+D8h] [rbp+6Fh] BYREF
  PSID pSid2; // [rsp+E0h] [rbp+77h]
  struct _ACL *v35; // [rsp+E8h] [rbp+7Fh] BYREF

  pSid2 = a3;
  SelfRelativeSecurityDescriptor = 0;
  v3 = 0;
  DaclDefaulted = 0;
  DaclPresent[0] = 0;
  BufferLength = 0;
  Dacl = 0;
  Ace = 0;
  Owner = 0;
  if ( !a2 && !a3 )
  {
    tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&SelfRelativeSecurityDescriptor);
    return -2147024809;
  }
  DaclSecurityDescriptor = RtlGetDaclSecurityDescriptor(*this, DaclPresent, &Dacl, &DaclDefaulted);
  if ( DaclSecurityDescriptor < 0 )
    return DaclSecurityDescriptor | 0x10000000;
  v8 = 0;
  v9 = 0;
  v10 = 1;
  LOBYTE(v35) = 0;
  while ( v8 < Dacl->AceCount )
  {
    v11 = RtlGetAce(Dacl, v8, &Ace);
    if ( v11 < 0 )
    {
LABEL_41:
      tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&SelfRelativeSecurityDescriptor);
      return v11 | 0x10000000;
    }
    v12 = (unsigned __int16 *)Ace;
    if ( !*(_BYTE *)Ace && *((_DWORD *)Ace + 1) == 1179785 )
    {
      v13 = (char *)Ace + 8;
      if ( a2 )
      {
        if ( EqualSid((char *)Ace + 8, a2) )
        {
          v10 = 0;
          goto LABEL_20;
        }
        v12 = (unsigned __int16 *)Ace;
      }
      if ( pSid2 )
      {
        if ( EqualSid(v13, pSid2) )
        {
          LOBYTE(v35) = 1;
          goto LABEL_20;
        }
        v12 = (unsigned __int16 *)Ace;
      }
    }
    v9 += v12[1];
LABEL_20:
    ++v8;
  }
  if ( !v10 && !(_BYTE)v35 )
    goto LABEL_57;
  v32 = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v14 = RtlLengthSid(a2) + 20 + v9;
  v15 = (struct _ACL *)LocalAlloc(0, v14);
  v35 = v15;
  v16 = v15;
  if ( !v15 )
    return -2147024882;
  Acl = RtlCreateAcl(v15, v14, 2u);
  if ( Acl < 0
    || (Acl = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u), Acl < 0)
    || (Acl = RtlAddAccessAllowedAce(v16, 2u, 0x120089u, a2), Acl < 0) )
  {
LABEL_44:
    tsched::AutoLocalPtr<_ACL>::~AutoLocalPtr<_ACL>((void **)&v35);
    tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&SelfRelativeSecurityDescriptor);
    return Acl | 0x10000000;
  }
  v18 = 0;
  while ( 2 )
  {
    if ( v18 < Dacl->AceCount )
    {
      v11 = RtlGetAce(Dacl, v18, &Ace);
      if ( v11 < 0 )
        goto LABEL_40;
      v19 = (unsigned __int16 *)Ace;
      if ( !*(_BYTE *)Ace && *((_DWORD *)Ace + 1) == 1179785 )
      {
        v20 = (char *)Ace + 8;
        if ( !a2 )
          goto LABEL_35;
        if ( EqualSid((char *)Ace + 8, a2) )
          goto LABEL_39;
        v19 = (unsigned __int16 *)Ace;
LABEL_35:
        if ( pSid2 )
        {
          if ( !EqualSid(v20, pSid2) )
          {
            v19 = (unsigned __int16 *)Ace;
            goto LABEL_38;
          }
LABEL_39:
          ++v18;
          continue;
        }
      }
LABEL_38:
      v11 = RtlAddAce(v16, 2u, v18, v19, v19[1]);
      if ( v11 < 0 )
      {
LABEL_40:
        tsched::AutoLocalPtr<_ACL>::~AutoLocalPtr<_ACL>((void **)&v35);
        goto LABEL_41;
      }
      goto LABEL_39;
    }
    break;
  }
  Acl = RtlSetDaclSecurityDescriptor(SecurityDescriptor, DaclPresent[0], v16, DaclDefaulted);
  if ( Acl < 0 )
    goto LABEL_44;
  Acl = RtlGetOwnerSecurityDescriptor(*this, &Owner, &DaclDefaulted);
  if ( Acl < 0 )
    goto LABEL_44;
  v21 = RtlSetOwnerSecurityDescriptor(SecurityDescriptor, Owner, DaclDefaulted);
  if ( v21 < 0 )
  {
    v22 = v21 | 0x10000000;
    LocalFree(v16);
    return v22;
  }
  GroupSecurityDescriptor = RtlGetGroupSecurityDescriptor(*this, &Owner, &DaclDefaulted);
  if ( GroupSecurityDescriptor < 0
    || (GroupSecurityDescriptor = RtlSetGroupSecurityDescriptor(SecurityDescriptor, Owner, DaclDefaulted),
        GroupSecurityDescriptor < 0) )
  {
LABEL_55:
    tsched::AutoLocalPtr<_ACL>::~AutoLocalPtr<_ACL>((void **)&v35);
    tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&SelfRelativeSecurityDescriptor);
    return GroupSecurityDescriptor | 0x10000000;
  }
  GroupSecurityDescriptor = RtlAbsoluteToSelfRelativeSD(SecurityDescriptor, 0, &BufferLength);
  if ( GroupSecurityDescriptor != -1073741789 )
  {
LABEL_54:
    if ( GroupSecurityDescriptor < 0 )
      goto LABEL_55;
    SelfRelativeSecurityDescriptor = 0;
    tsched::AutoLocalPtr<_SECURITY_DESCRIPTOR>::Attach(this, v3);
    *((_DWORD *)this + 2) = BufferLength;
    tsched::AutoLocalPtr<_ACL>::~AutoLocalPtr<_ACL>((void **)&v35);
LABEL_57:
    tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&SelfRelativeSecurityDescriptor);
    return 0;
  }
  v24 = LocalAlloc(0, BufferLength);
  tsched::AutoLocalPtr<_SECURITY_DESCRIPTOR>::Attach(&SelfRelativeSecurityDescriptor, v24);
  v3 = SelfRelativeSecurityDescriptor;
  if ( SelfRelativeSecurityDescriptor )
  {
    GroupSecurityDescriptor = RtlAbsoluteToSelfRelativeSD(
                                SecurityDescriptor,
                                SelfRelativeSecurityDescriptor,
                                &BufferLength);
    goto LABEL_54;
  }
  tsched::AutoLocalPtr<_ACL>::~AutoLocalPtr<_ACL>((void **)&v35);
  tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&SelfRelativeSecurityDescriptor);
  return -2147024882;
}

```

## disassembly

```asm
0x180040d90  mov     [rsp-8+pSid2], r8
0x180040d95  push    rbp
0x180040d96  push    rsi
0x180040d97  push    r12
0x180040d99  push    r13
0x180040d9b  push    r14
0x180040d9d  lea     rbp, [rsp-37h]
0x180040da2  sub     rsp, 0A0h
0x180040da9  xor     r14d, r14d
0x180040dac  mov     rax, r8
0x180040daf  mov     [rbp+57h+SelfRelativeSecurityDescriptor], r14
0x180040db3  mov     r13d, r14d
0x180040db6  mov     [rbp+57h+DaclDefaulted], r13b
0x180040dba  mov     rsi, rdx
0x180040dbd  mov     [rbp+57h+DaclPresent], r13b
0x180040dc1  mov     r12, rcx
0x180040dc4  mov     [rbp+57h+BufferLength], r14d
0x180040dc8  mov     [rbp+57h+Dacl], r14
0x180040dcc  mov     [rbp+57h+Ace], r14
0x180040dd0  mov     [rbp+57h+Owner], r14
0x180040dd4  test    rdx, rdx
0x180040dd7  jnz     short loc_180040DF1
0x180040dd9  test    rax, rax
0x180040ddc  jnz     short loc_180040DF1
0x180040dde  lea     rcx, [rbp+57h+SelfRelativeSecurityDescriptor]
0x180040de2  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180040de7  mov     eax, 80070057h
0x180040dec  jmp     loc_18004119D
0x180040df1  mov     rcx, [rcx]; SecurityDescriptor
0x180040df4  lea     r9, [rbp+57h+DaclDefaulted]; DaclDefaulted
0x180040df8  lea     r8, [rbp+57h+Dacl]; Dacl
0x180040dfc  lea     rdx, [rbp+57h+DaclPresent]; DaclPresent
0x180040e00  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x180040e06  test    eax, eax
0x180040e08  jns     short loc_180040E1E
0x180040e0a  bts     eax, 1Ch
0x180040e0e  add     rsp, 0A0h
0x180040e15  pop     r14
0x180040e17  pop     r13
0x180040e19  pop     r12
0x180040e1b  pop     rsi
0x180040e1c  pop     rbp
0x180040e1d  retn
0x180040e1e  mov     [rsp+0C0h+arg_0], rbx
0x180040e26  mov     ebx, r14d
0x180040e29  mov     [rsp+0C0h+var_28], rdi
0x180040e31  mov     edi, r14d
0x180040e34  mov     [rsp+0C0h+var_30], r15
0x180040e3c  mov     r15b, 1
0x180040e3f  mov     byte ptr [rbp+57h+arg_18], r13b
0x180040e43  mov     rcx, [rbp+57h+Dacl]; Acl
0x180040e47  movzx   eax, word ptr [rcx+4]
0x180040e4b  cmp     ebx, eax
0x180040e4d  jge     short loc_180040ECA
0x180040e4f  lea     r8, [rbp+57h+Ace]; Ace
0x180040e53  mov     edx, ebx; AceIndex
0x180040e55  call    cs:__imp_RtlGetAce
0x180040e5b  mov     r14d, eax
0x180040e5e  test    eax, eax
0x180040e60  js      loc_18004100A
0x180040e66  mov     rax, [rbp+57h+Ace]
0x180040e6a  cmp     [rax], r13b
0x180040e6d  jnz     short loc_180040EBD
0x180040e6f  cmp     dword ptr [rax+4], 120089h
0x180040e76  jnz     short loc_180040EBD
0x180040e78  lea     r14, [rax+8]
0x180040e7c  test    rsi, rsi
0x180040e7f  jz      short loc_180040E9A
0x180040e81  mov     rdx, rsi; pSid2
0x180040e84  mov     rcx, r14; pSid1
0x180040e87  call    cs:__imp_EqualSid
0x180040e8d  test    eax, eax
0x180040e8f  jz      short loc_180040E96
0x180040e91  xor     r15b, r15b
0x180040e94  jmp     short loc_180040EC3
0x180040e96  mov     rax, [rbp+57h+Ace]
0x180040e9a  mov     rcx, [rbp+57h+pSid2]
0x180040e9e  test    rcx, rcx
0x180040ea1  jz      short loc_180040EBD
0x180040ea3  mov     rdx, rcx; pSid2
0x180040ea6  mov     rcx, r14; pSid1
0x180040ea9  call    cs:__imp_EqualSid
0x180040eaf  test    eax, eax
0x180040eb1  jz      short loc_180040EB9
0x180040eb3  mov     byte ptr [rbp+57h+arg_18], 1
0x180040eb7  jmp     short loc_180040EC3
0x180040eb9  mov     rax, [rbp+57h+Ace]
0x180040ebd  movzx   eax, word ptr [rax+2]
0x180040ec1  add     edi, eax
0x180040ec3  inc     ebx
0x180040ec5  jmp     loc_180040E43
0x180040eca  test    r15b, r15b
0x180040ecd  jnz     short loc_180040ED9
0x180040ecf  cmp     byte ptr [rbp+57h+arg_18], r13b
0x180040ed3  jz      loc_18004117A
0x180040ed9  xorps   xmm0, xmm0
0x180040edc  xor     eax, eax
0x180040ede  mov     rcx, rsi; Sid
0x180040ee1  mov     [rbp+57h+var_40], rax
0x180040ee5  movups  [rbp+57h+SecurityDescriptor], xmm0
0x180040ee9  movups  [rbp+57h+var_50], xmm0
0x180040eed  call    cs:__imp_RtlLengthSid
0x180040ef3  add     eax, 14h
0x180040ef6  xor     ecx, ecx; uFlags
0x180040ef8  add     edi, eax
0x180040efa  mov     edx, edi; uBytes
0x180040efc  call    cs:__imp_LocalAlloc
0x180040f02  mov     [rbp+57h+arg_18], rax
0x180040f06  mov     rbx, rax
0x180040f09  test    rax, rax
0x180040f0c  jz      loc_18004111E
0x180040f12  mov     r8d, 2; AclRevision
0x180040f18  mov     edx, edi; AclSize
0x180040f1a  mov     rcx, rax; Acl
0x180040f1d  call    cs:__imp_RtlCreateAcl
0x180040f23  mov     edi, eax
0x180040f25  test    eax, eax
0x180040f27  js      loc_180041054
0x180040f2d  mov     edx, 1; Revision
0x180040f32  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180040f36  call    cs:__imp_RtlCreateSecurityDescriptor
0x180040f3c  mov     edi, eax
0x180040f3e  test    eax, eax
0x180040f40  js      loc_180041054
0x180040f46  mov     r9, rsi; Sid
0x180040f49  mov     edx, 2; Revision
0x180040f4e  mov     r8d, 120089h; AccessMask
0x180040f54  mov     rcx, rbx; Acl
0x180040f57  call    cs:__imp_RtlAddAccessAllowedAce
0x180040f5d  mov     edi, eax
0x180040f5f  test    eax, eax
0x180040f61  js      loc_180041054
0x180040f67  xor     edi, edi
0x180040f69  mov     rcx, [rbp+57h+Dacl]; Acl
0x180040f6d  movzx   eax, word ptr [rcx+4]
0x180040f71  cmp     edi, eax
0x180040f73  jge     loc_180041020
0x180040f79  lea     r8, [rbp+57h+Ace]; Ace
0x180040f7d  mov     edx, edi; AceIndex
0x180040f7f  call    cs:__imp_RtlGetAce
0x180040f85  mov     r14d, eax
0x180040f88  test    eax, eax
0x180040f8a  js      short loc_180041001
0x180040f8c  mov     r9, [rbp+57h+Ace]
0x180040f90  cmp     [r9], r13b
0x180040f93  jnz     short loc_180040FD9
0x180040f95  cmp     dword ptr [r9+4], 120089h
0x180040f9d  jnz     short loc_180040FD9
0x180040f9f  lea     r14, [r9+8]
0x180040fa3  test    rsi, rsi
0x180040fa6  jz      short loc_180040FBC
0x180040fa8  mov     rdx, rsi; pSid2
0x180040fab  mov     rcx, r14; pSid1
0x180040fae  call    cs:__imp_EqualSid
0x180040fb4  test    eax, eax
0x180040fb6  jnz     short loc_180040FFA
0x180040fb8  mov     r9, [rbp+57h+Ace]
0x180040fbc  mov     rax, [rbp+57h+pSid2]
0x180040fc0  test    rax, rax
0x180040fc3  jz      short loc_180040FD9
0x180040fc5  mov     rdx, rax; pSid2
0x180040fc8  mov     rcx, r14; pSid1
0x180040fcb  call    cs:__imp_EqualSid
0x180040fd1  test    eax, eax
0x180040fd3  jnz     short loc_180040FFA
0x180040fd5  mov     r9, [rbp+57h+Ace]; AceList
0x180040fd9  movzx   eax, word ptr [r9+2]
0x180040fde  mov     r8d, edi; StartingAceIndex
0x180040fe1  mov     edx, 2; AceRevision
0x180040fe6  mov     [rsp+0C0h+AceListLength], eax; AceListLength
0x180040fea  mov     rcx, rbx; Acl
0x180040fed  call    cs:__imp_RtlAddAce
0x180040ff3  mov     r14d, eax
0x180040ff6  test    eax, eax
0x180040ff8  js      short loc_180041001
0x180040ffa  inc     edi
0x180040ffc  jmp     loc_180040F69
0x180041001  lea     rcx, [rbp+57h+arg_18]
0x180041005  call    ??1?$AutoLocalPtr@U_ACL@@@tsched@@QEAA@XZ; tsched::AutoLocalPtr<_ACL>::~AutoLocalPtr<_ACL>(void)
0x18004100a  lea     rcx, [rbp+57h+SelfRelativeSecurityDescriptor]
0x18004100e  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180041013  bts     r14d, 1Ch
0x180041018  mov     eax, r14d
0x18004101b  jmp     loc_180041185
0x180041020  movzx   r9d, [rbp+57h+DaclDefaulted]; DaclDefaulted
0x180041025  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180041029  movzx   edx, [rbp+57h+DaclPresent]; DaclPresent
0x18004102d  mov     r8, rbx; Dacl
0x180041030  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180041036  mov     edi, eax
0x180041038  test    eax, eax
0x18004103a  js      short loc_180041054
0x18004103c  mov     rcx, [r12]; SecurityDescriptor
0x180041040  lea     r8, [rbp+57h+DaclDefaulted]; OwnerDefaulted
0x180041044  lea     rdx, [rbp+57h+Owner]; Owner
0x180041048  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x18004104e  mov     edi, eax
0x180041050  test    eax, eax
0x180041052  jns     short loc_180041071
0x180041054  lea     rcx, [rbp+57h+arg_18]
0x180041058  call    ??1?$AutoLocalPtr@U_ACL@@@tsched@@QEAA@XZ; tsched::AutoLocalPtr<_ACL>::~AutoLocalPtr<_ACL>(void)
0x18004105d  lea     rcx, [rbp+57h+SelfRelativeSecurityDescriptor]
0x180041061  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180041066  bts     edi, 1Ch
0x18004106a  mov     eax, edi
0x18004106c  jmp     loc_180041185
0x180041071  movzx   r8d, [rbp+57h+DaclDefaulted]; OwnerDefaulted
0x180041076  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18004107a  mov     rdx, [rbp+57h+Owner]; Owner
0x18004107e  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x180041084  mov     edi, eax
0x180041086  test    eax, eax
0x180041088  jns     short loc_18004109E
0x18004108a  bts     edi, 1Ch
0x18004108e  mov     rcx, rbx; hMem
0x180041091  call    cs:__imp_LocalFree
0x180041097  mov     eax, edi
0x180041099  jmp     loc_180041185
0x18004109e  mov     rcx, [r12]; SecurityDescriptor
0x1800410a2  lea     r8, [rbp+57h+DaclDefaulted]; GroupDefaulted
0x1800410a6  lea     rdx, [rbp+57h+Owner]; Group
0x1800410aa  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x1800410b0  mov     ebx, eax
0x1800410b2  test    eax, eax
0x1800410b4  js      loc_18004113C
0x1800410ba  movzx   r8d, [rbp+57h+DaclDefaulted]; GroupDefaulted
0x1800410bf  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1800410c3  mov     rdx, [rbp+57h+Owner]; Group
0x1800410c7  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x1800410cd  mov     ebx, eax
0x1800410cf  test    eax, eax
0x1800410d1  js      short loc_18004113C
0x1800410d3  lea     r8, [rbp+57h+BufferLength]; BufferLength
0x1800410d7  xor     edx, edx; SelfRelativeSecurityDescriptor
0x1800410d9  lea     rcx, [rbp+57h+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x1800410dd  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x1800410e3  mov     ebx, eax
0x1800410e5  cmp     eax, 0C0000023h
0x1800410ea  jnz     short loc_180041138
0x1800410ec  mov     edx, [rbp+57h+BufferLength]; uBytes
0x1800410ef  xor     ecx, ecx; uFlags
0x1800410f1  call    cs:__imp_LocalAlloc
0x1800410f7  mov     rdx, rax
0x1800410fa  lea     rcx, [rbp+57h+SelfRelativeSecurityDescriptor]
0x1800410fe  call    ?Attach@?$AutoLocalPtr@U_SECURITY_DESCRIPTOR@@@tsched@@QEAAXPEAU_SECURITY_DESCRIPTOR@@@Z; tsched::AutoLocalPtr<_SECURITY_DESCRIPTOR>::Attach(_SECURITY_DESCRIPTOR *)
0x180041103  mov     r13, [rbp+57h+SelfRelativeSecurityDescriptor]
0x180041107  test    r13, r13
0x18004110a  jnz     short loc_180041125
0x18004110c  lea     rcx, [rbp+57h+arg_18]
0x180041110  call    ??1?$AutoLocalPtr@U_ACL@@@tsched@@QEAA@XZ; tsched::AutoLocalPtr<_ACL>::~AutoLocalPtr<_ACL>(void)
0x180041115  lea     rcx, [rbp+57h+SelfRelativeSecurityDescriptor]
0x180041119  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x18004111e  mov     eax, 8007000Eh
0x180041123  jmp     short loc_180041185
0x180041125  lea     r8, [rbp+57h+BufferLength]; BufferLength
0x180041129  mov     rdx, r13; SelfRelativeSecurityDescriptor
0x18004112c  lea     rcx, [rbp+57h+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x180041130  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x180041136  mov     ebx, eax
0x180041138  test    ebx, ebx
0x18004113a  jns     short loc_180041156
0x18004113c  lea     rcx, [rbp+57h+arg_18]
0x180041140  call    ??1?$AutoLocalPtr@U_ACL@@@tsched@@QEAA@XZ; tsched::AutoLocalPtr<_ACL>::~AutoLocalPtr<_ACL>(void)
0x180041145  lea     rcx, [rbp+57h+SelfRelativeSecurityDescriptor]
0x180041149  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x18004114e  bts     ebx, 1Ch
0x180041152  mov     eax, ebx
0x180041154  jmp     short loc_180041185
0x180041156  mov     rdx, r13
0x180041159  mov     [rbp+57h+SelfRelativeSecurityDescriptor], 0
0x180041161  mov     rcx, r12
0x180041164  call    ?Attach@?$AutoLocalPtr@U_SECURITY_DESCRIPTOR@@@tsched@@QEAAXPEAU_SECURITY_DESCRIPTOR@@@Z; tsched::AutoLocalPtr<_SECURITY_DESCRIPTOR>::Attach(_SECURITY_DESCRIPTOR *)
0x180041169  mov     eax, [rbp+57h+BufferLength]
0x18004116c  lea     rcx, [rbp+57h+arg_18]
0x180041170  mov     [r12+8], eax
0x180041175  call    ??1?$AutoLocalPtr@U_ACL@@@tsched@@QEAA@XZ; tsched::AutoLocalPtr<_ACL>::~AutoLocalPtr<_ACL>(void)
0x18004117a  lea     rcx, [rbp+57h+SelfRelativeSecurityDescriptor]
0x18004117e  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180041183  xor     eax, eax
0x180041185  mov     rdi, [rsp+0C0h+var_28]
0x18004118d  mov     rbx, [rsp+0C0h+arg_0]
0x180041195  mov     r15, [rsp+0C0h+var_30]
0x18004119d  add     rsp, 0A0h
0x1800411a4  pop     r14
0x1800411a6  pop     r13
0x1800411a8  pop     r12
0x1800411aa  pop     rsi
0x1800411ab  pop     rbp
0x1800411ac  retn
```
