# JobSecurity::AddRemovePrincipalAce(void *,void *)

- ea: `0x1800437e0`
- end: `0x180043c8b`
- name: `?AddRemovePrincipalAce@JobSecurity@@QEAAJPEAX0@Z`
- size: `1195`
- prototype: `int(JobSecurity *__hidden this, void *, void *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180023c4c`
- `0x180047ee0`

## callees

- `0x18001fe10`
- `0x180040af0`
- `0x1800437e0`
- `0x1800450ec`

## import_xrefs

- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x180043af5`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x180043af5`
- `ntdll!RtlGetGroupSecurityDescriptor` at `0x180043b69`
- `ntdll!RtlGetGroupSecurityDescriptor` at `0x180043b69`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x180043850`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x180043850`
- `ntdll!RtlGetAce` at `0x1800438b0`
- `ntdll!RtlGetAce` at `0x180043a0a`
- `ntdll!RtlGetAce` at `0x1800438b0`
- `ntdll!RtlGetAce` at `0x180043a0a`
- `ntdll!RtlLengthSid` at `0x18004395a`
- `ntdll!RtlLengthSid` at `0x18004395a`
- `ntdll!RtlCreateAcl` at `0x180043996`
- `ntdll!RtlCreateAcl` at `0x180043996`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1800439b5`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1800439b5`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800439dc`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800439dc`
- `ntdll!RtlAddAce` at `0x180043a8e`
- `ntdll!RtlAddAce` at `0x180043a8e`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180043ad7`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180043ad7`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180043b31`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180043b31`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x180043b8c`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x180043b8c`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x180043ba8`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x180043c07`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x180043ba8`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x180043c07`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180043b4a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180043b4a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004396f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180043bc2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004396f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180043bc2`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800438e8`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180043910`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180043a43`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180043a66`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800438e8`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180043910`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180043a43`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180043a66`

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
    tsched::AutoLocalPtr<_ACL>::~AutoLocalPtr<_ACL>(&v35);
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
        tsched::AutoLocalPtr<_ACL>::~AutoLocalPtr<_ACL>(&v35);
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
    tsched::AutoLocalPtr<_ACL>::~AutoLocalPtr<_ACL>(&v35);
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
    tsched::AutoLocalPtr<_ACL>::~AutoLocalPtr<_ACL>(&v35);
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
  tsched::AutoLocalPtr<_ACL>::~AutoLocalPtr<_ACL>(&v35);
  tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&SelfRelativeSecurityDescriptor);
  return -2147024882;
}

```

## disassembly

```asm
0x1800437e0  mov     [rsp-8+pSid2], r8
0x1800437e5  push    rbp
0x1800437e6  push    rsi
0x1800437e7  push    r12
0x1800437e9  push    r13
0x1800437eb  push    r14
0x1800437ed  lea     rbp, [rsp-37h]
0x1800437f2  sub     rsp, 0A0h
0x1800437f9  xor     r14d, r14d
0x1800437fc  mov     rax, r8
0x1800437ff  mov     [rbp+57h+SelfRelativeSecurityDescriptor], r14
0x180043803  mov     r13d, r14d
0x180043806  mov     [rbp+57h+DaclDefaulted], r13b
0x18004380a  mov     rsi, rdx
0x18004380d  mov     [rbp+57h+DaclPresent], r13b
0x180043811  mov     r12, rcx
0x180043814  mov     [rbp+57h+BufferLength], r14d
0x180043818  mov     [rbp+57h+Dacl], r14
0x18004381c  mov     [rbp+57h+Ace], r14
0x180043820  mov     [rbp+57h+Owner], r14
0x180043824  test    rdx, rdx
0x180043827  jnz     short loc_180043841
0x180043829  test    rax, rax
0x18004382c  jnz     short loc_180043841
0x18004382e  lea     rcx, [rbp+57h+SelfRelativeSecurityDescriptor]
0x180043832  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180043837  mov     eax, 80070057h
0x18004383c  jmp     loc_180043C7A
0x180043841  mov     rcx, [rcx]; SecurityDescriptor
0x180043844  lea     r9, [rbp+57h+DaclDefaulted]; DaclDefaulted
0x180043848  lea     r8, [rbp+57h+Dacl]; Dacl
0x18004384c  lea     rdx, [rbp+57h+DaclPresent]; DaclPresent
0x180043850  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x180043857  nop     dword ptr [rax+rax+00h]
0x18004385c  test    eax, eax
0x18004385e  jns     short loc_180043875
0x180043860  bts     eax, 1Ch
0x180043864  add     rsp, 0A0h
0x18004386b  pop     r14
0x18004386d  pop     r13
0x18004386f  pop     r12
0x180043871  pop     rsi
0x180043872  pop     rbp
0x180043873  retn
0x180043875  mov     [rsp+0C0h+arg_0], rbx
0x18004387d  mov     ebx, r14d
0x180043880  mov     [rsp+0C0h+var_28], rdi
0x180043888  mov     edi, r14d
0x18004388b  mov     [rsp+0C0h+var_30], r15
0x180043893  mov     r15b, 1
0x180043896  mov     byte ptr [rbp+57h+arg_18], r13b
0x18004389a  mov     rcx, [rbp+57h+Dacl]; Acl
0x18004389e  movzx   eax, word ptr [rcx+4]
0x1800438a2  cmp     ebx, eax
0x1800438a4  jge     loc_180043937
0x1800438aa  lea     r8, [rbp+57h+Ace]; Ace
0x1800438ae  mov     edx, ebx; AceIndex
0x1800438b0  call    cs:__imp_RtlGetAce
0x1800438b7  nop     dword ptr [rax+rax+00h]
0x1800438bc  mov     r14d, eax
0x1800438bf  test    eax, eax
0x1800438c1  js      loc_180043AB1
0x1800438c7  mov     rax, [rbp+57h+Ace]
0x1800438cb  cmp     [rax], r13b
0x1800438ce  jnz     short loc_18004392A
0x1800438d0  cmp     dword ptr [rax+4], 120089h
0x1800438d7  jnz     short loc_18004392A
0x1800438d9  lea     r14, [rax+8]
0x1800438dd  test    rsi, rsi
0x1800438e0  jz      short loc_180043901
0x1800438e2  mov     rdx, rsi; pSid2
0x1800438e5  mov     rcx, r14; pSid1
0x1800438e8  call    cs:__imp_EqualSid
0x1800438ef  nop     dword ptr [rax+rax+00h]
0x1800438f4  test    eax, eax
0x1800438f6  jz      short loc_1800438FD
0x1800438f8  xor     r15b, r15b
0x1800438fb  jmp     short loc_180043930
0x1800438fd  mov     rax, [rbp+57h+Ace]
0x180043901  mov     rcx, [rbp+57h+pSid2]
0x180043905  test    rcx, rcx
0x180043908  jz      short loc_18004392A
0x18004390a  mov     rdx, rcx; pSid2
0x18004390d  mov     rcx, r14; pSid1
0x180043910  call    cs:__imp_EqualSid
0x180043917  nop     dword ptr [rax+rax+00h]
0x18004391c  test    eax, eax
0x18004391e  jz      short loc_180043926
0x180043920  mov     byte ptr [rbp+57h+arg_18], 1
0x180043924  jmp     short loc_180043930
0x180043926  mov     rax, [rbp+57h+Ace]
0x18004392a  movzx   eax, word ptr [rax+2]
0x18004392e  add     edi, eax
0x180043930  inc     ebx
0x180043932  jmp     loc_18004389A
0x180043937  test    r15b, r15b
0x18004393a  jnz     short loc_180043946
0x18004393c  cmp     byte ptr [rbp+57h+arg_18], r13b
0x180043940  jz      loc_180043C57
0x180043946  xorps   xmm0, xmm0
0x180043949  xor     eax, eax
0x18004394b  mov     rcx, rsi; Sid
0x18004394e  mov     [rbp+57h+var_40], rax
0x180043952  movups  [rbp+57h+SecurityDescriptor], xmm0
0x180043956  movups  [rbp+57h+var_50], xmm0
0x18004395a  call    cs:__imp_RtlLengthSid
0x180043961  nop     dword ptr [rax+rax+00h]
0x180043966  add     eax, 14h
0x180043969  xor     ecx, ecx; uFlags
0x18004396b  add     edi, eax
0x18004396d  mov     edx, edi; uBytes
0x18004396f  call    cs:__imp_LocalAlloc
0x180043976  nop     dword ptr [rax+rax+00h]
0x18004397b  mov     [rbp+57h+arg_18], rax
0x18004397f  mov     rbx, rax
0x180043982  test    rax, rax
0x180043985  jz      loc_180043BF5
0x18004398b  mov     r8d, 2; AclRevision
0x180043991  mov     edx, edi; AclSize
0x180043993  mov     rcx, rax; Acl
0x180043996  call    cs:__imp_RtlCreateAcl
0x18004399d  nop     dword ptr [rax+rax+00h]
0x1800439a2  mov     edi, eax
0x1800439a4  test    eax, eax
0x1800439a6  js      loc_180043B07
0x1800439ac  mov     edx, 1; Revision
0x1800439b1  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1800439b5  call    cs:__imp_RtlCreateSecurityDescriptor
0x1800439bc  nop     dword ptr [rax+rax+00h]
0x1800439c1  mov     edi, eax
0x1800439c3  test    eax, eax
0x1800439c5  js      loc_180043B07
0x1800439cb  mov     r9, rsi; Sid
0x1800439ce  mov     edx, 2; Revision
0x1800439d3  mov     r8d, 120089h; AccessMask
0x1800439d9  mov     rcx, rbx; Acl
0x1800439dc  call    cs:__imp_RtlAddAccessAllowedAce
0x1800439e3  nop     dword ptr [rax+rax+00h]
0x1800439e8  mov     edi, eax
0x1800439ea  test    eax, eax
0x1800439ec  js      loc_180043B07
0x1800439f2  xor     edi, edi
0x1800439f4  mov     rcx, [rbp+57h+Dacl]; Acl
0x1800439f8  movzx   eax, word ptr [rcx+4]
0x1800439fc  cmp     edi, eax
0x1800439fe  jge     loc_180043AC7
0x180043a04  lea     r8, [rbp+57h+Ace]; Ace
0x180043a08  mov     edx, edi; AceIndex
0x180043a0a  call    cs:__imp_RtlGetAce
0x180043a11  nop     dword ptr [rax+rax+00h]
0x180043a16  mov     r14d, eax
0x180043a19  test    eax, eax
0x180043a1b  js      loc_180043AA8
0x180043a21  mov     r9, [rbp+57h+Ace]
0x180043a25  cmp     [r9], r13b
0x180043a28  jnz     short loc_180043A7A
0x180043a2a  cmp     dword ptr [r9+4], 120089h
0x180043a32  jnz     short loc_180043A7A
0x180043a34  lea     r14, [r9+8]
0x180043a38  test    rsi, rsi
0x180043a3b  jz      short loc_180043A57
0x180043a3d  mov     rdx, rsi; pSid2
0x180043a40  mov     rcx, r14; pSid1
0x180043a43  call    cs:__imp_EqualSid
0x180043a4a  nop     dword ptr [rax+rax+00h]
0x180043a4f  test    eax, eax
0x180043a51  jnz     short loc_180043AA1
0x180043a53  mov     r9, [rbp+57h+Ace]
0x180043a57  mov     rax, [rbp+57h+pSid2]
0x180043a5b  test    rax, rax
0x180043a5e  jz      short loc_180043A7A
0x180043a60  mov     rdx, rax; pSid2
0x180043a63  mov     rcx, r14; pSid1
0x180043a66  call    cs:__imp_EqualSid
0x180043a6d  nop     dword ptr [rax+rax+00h]
0x180043a72  test    eax, eax
0x180043a74  jnz     short loc_180043AA1
0x180043a76  mov     r9, [rbp+57h+Ace]; AceList
0x180043a7a  movzx   eax, word ptr [r9+2]
0x180043a7f  mov     r8d, edi; StartingAceIndex
0x180043a82  mov     edx, 2; AceRevision
0x180043a87  mov     [rsp+0C0h+AceListLength], eax; AceListLength
0x180043a8b  mov     rcx, rbx; Acl
0x180043a8e  call    cs:__imp_RtlAddAce
0x180043a95  nop     dword ptr [rax+rax+00h]
0x180043a9a  mov     r14d, eax
0x180043a9d  test    eax, eax
0x180043a9f  js      short loc_180043AA8
0x180043aa1  inc     edi
0x180043aa3  jmp     loc_1800439F4
0x180043aa8  lea     rcx, [rbp+57h+arg_18]
0x180043aac  call    ??1?$AutoLocalPtr@U_ACL@@@tsched@@QEAA@XZ; tsched::AutoLocalPtr<_ACL>::~AutoLocalPtr<_ACL>(void)
0x180043ab1  lea     rcx, [rbp+57h+SelfRelativeSecurityDescriptor]
0x180043ab5  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180043aba  bts     r14d, 1Ch
0x180043abf  mov     eax, r14d
0x180043ac2  jmp     loc_180043C62
0x180043ac7  movzx   r9d, [rbp+57h+DaclDefaulted]; DaclDefaulted
0x180043acc  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180043ad0  movzx   edx, [rbp+57h+DaclPresent]; DaclPresent
0x180043ad4  mov     r8, rbx; Dacl
0x180043ad7  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180043ade  nop     dword ptr [rax+rax+00h]
0x180043ae3  mov     edi, eax
0x180043ae5  test    eax, eax
0x180043ae7  js      short loc_180043B07
0x180043ae9  mov     rcx, [r12]; SecurityDescriptor
0x180043aed  lea     r8, [rbp+57h+DaclDefaulted]; OwnerDefaulted
0x180043af1  lea     rdx, [rbp+57h+Owner]; Owner
0x180043af5  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x180043afc  nop     dword ptr [rax+rax+00h]
0x180043b01  mov     edi, eax
0x180043b03  test    eax, eax
0x180043b05  jns     short loc_180043B24
0x180043b07  lea     rcx, [rbp+57h+arg_18]
0x180043b0b  call    ??1?$AutoLocalPtr@U_ACL@@@tsched@@QEAA@XZ; tsched::AutoLocalPtr<_ACL>::~AutoLocalPtr<_ACL>(void)
0x180043b10  lea     rcx, [rbp+57h+SelfRelativeSecurityDescriptor]
0x180043b14  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180043b19  bts     edi, 1Ch
0x180043b1d  mov     eax, edi
0x180043b1f  jmp     loc_180043C62
0x180043b24  movzx   r8d, [rbp+57h+DaclDefaulted]; OwnerDefaulted
0x180043b29  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180043b2d  mov     rdx, [rbp+57h+Owner]; Owner
0x180043b31  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x180043b38  nop     dword ptr [rax+rax+00h]
0x180043b3d  mov     edi, eax
0x180043b3f  test    eax, eax
0x180043b41  jns     short loc_180043B5D
0x180043b43  bts     edi, 1Ch
0x180043b47  mov     rcx, rbx; hMem
0x180043b4a  call    cs:__imp_LocalFree
0x180043b51  nop     dword ptr [rax+rax+00h]
0x180043b56  mov     eax, edi
0x180043b58  jmp     loc_180043C62
0x180043b5d  mov     rcx, [r12]; SecurityDescriptor
0x180043b61  lea     r8, [rbp+57h+DaclDefaulted]; GroupDefaulted
0x180043b65  lea     rdx, [rbp+57h+Owner]; Group
0x180043b69  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x180043b70  nop     dword ptr [rax+rax+00h]
0x180043b75  mov     ebx, eax
0x180043b77  test    eax, eax
0x180043b79  js      loc_180043C19
0x180043b7f  movzx   r8d, [rbp+57h+DaclDefaulted]; GroupDefaulted
0x180043b84  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180043b88  mov     rdx, [rbp+57h+Owner]; Group
0x180043b8c  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x180043b93  nop     dword ptr [rax+rax+00h]
0x180043b98  mov     ebx, eax
0x180043b9a  test    eax, eax
0x180043b9c  js      short loc_180043C19
0x180043b9e  lea     r8, [rbp+57h+BufferLength]; BufferLength
0x180043ba2  xor     edx, edx; SelfRelativeSecurityDescriptor
0x180043ba4  lea     rcx, [rbp+57h+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x180043ba8  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x180043baf  nop     dword ptr [rax+rax+00h]
0x180043bb4  mov     ebx, eax
0x180043bb6  cmp     eax, 0C0000023h
0x180043bbb  jnz     short loc_180043C15
0x180043bbd  mov     edx, [rbp+57h+BufferLength]; uBytes
0x180043bc0  xor     ecx, ecx; uFlags
0x180043bc2  call    cs:__imp_LocalAlloc
0x180043bc9  nop     dword ptr [rax+rax+00h]
0x180043bce  mov     rdx, rax
0x180043bd1  lea     rcx, [rbp+57h+SelfRelativeSecurityDescriptor]
0x180043bd5  call    ?Attach@?$AutoLocalPtr@U_SECURITY_DESCRIPTOR@@@tsched@@QEAAXPEAU_SECURITY_DESCRIPTOR@@@Z; tsched::AutoLocalPtr<_SECURITY_DESCRIPTOR>::Attach(_SECURITY_DESCRIPTOR *)
0x180043bda  mov     r13, [rbp+57h+SelfRelativeSecurityDescriptor]
0x180043bde  test    r13, r13
0x180043be1  jnz     short loc_180043BFC
0x180043be3  lea     rcx, [rbp+57h+arg_18]
0x180043be7  call    ??1?$AutoLocalPtr@U_ACL@@@tsched@@QEAA@XZ; tsched::AutoLocalPtr<_ACL>::~AutoLocalPtr<_ACL>(void)
0x180043bec  lea     rcx, [rbp+57h+SelfRelativeSecurityDescriptor]
0x180043bf0  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180043bf5  mov     eax, 8007000Eh
0x180043bfa  jmp     short loc_180043C62
0x180043bfc  lea     r8, [rbp+57h+BufferLength]; BufferLength
0x180043c00  mov     rdx, r13; SelfRelativeSecurityDescriptor
0x180043c03  lea     rcx, [rbp+57h+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x180043c07  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x180043c0e  nop     dword ptr [rax+rax+00h]
0x180043c13  mov     ebx, eax
0x180043c15  test    ebx, ebx
0x180043c17  jns     short loc_180043C33
0x180043c19  lea     rcx, [rbp+57h+arg_18]
0x180043c1d  call    ??1?$AutoLocalPtr@U_ACL@@@tsched@@QEAA@XZ; tsched::AutoLocalPtr<_ACL>::~AutoLocalPtr<_ACL>(void)
0x180043c22  lea     rcx, [rbp+57h+SelfRelativeSecurityDescriptor]
0x180043c26  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180043c2b  bts     ebx, 1Ch
0x180043c2f  mov     eax, ebx
0x180043c31  jmp     short loc_180043C62
0x180043c33  mov     rdx, r13
0x180043c36  mov     [rbp+57h+SelfRelativeSecurityDescriptor], 0
0x180043c3e  mov     rcx, r12
0x180043c41  call    ?Attach@?$AutoLocalPtr@U_SECURITY_DESCRIPTOR@@@tsched@@QEAAXPEAU_SECURITY_DESCRIPTOR@@@Z; tsched::AutoLocalPtr<_SECURITY_DESCRIPTOR>::Attach(_SECURITY_DESCRIPTOR *)
0x180043c46  mov     eax, [rbp+57h+BufferLength]
0x180043c49  lea     rcx, [rbp+57h+arg_18]
0x180043c4d  mov     [r12+8], eax
0x180043c52  call    ??1?$AutoLocalPtr@U_ACL@@@tsched@@QEAA@XZ; tsched::AutoLocalPtr<_ACL>::~AutoLocalPtr<_ACL>(void)
0x180043c57  lea     rcx, [rbp+57h+SelfRelativeSecurityDescriptor]
0x180043c5b  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
  ... truncated ...
```
