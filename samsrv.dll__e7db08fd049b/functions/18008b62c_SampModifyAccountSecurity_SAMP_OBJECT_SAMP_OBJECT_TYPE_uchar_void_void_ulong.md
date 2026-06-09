# SampModifyAccountSecurity(_SAMP_OBJECT *,_SAMP_OBJECT_TYPE,uchar,void *,void * *,ulong *)

- ea: `0x18008b62c`
- end: `0x18008ba33`
- name: `?SampModifyAccountSecurity@@YAJPEAU_SAMP_OBJECT@@W4_SAMP_OBJECT_TYPE@@EPEAXPEAPEAXPEAK@Z`
- size: `1031`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18009642c`
- `0x1800aa648`
- `0x1800aa9f8`

## callees

- `0x180027e24`
- `0x18002cd80`
- `0x18008b62c`

## import_xrefs

- `ntdll!RtlAddAce` at `0x18008b938`
- `ntdll!RtlAddAce` at `0x18008b938`
- `ntdll!RtlSetSecurityObject` at `0x18008b991`
- `ntdll!RtlSetSecurityObject` at `0x18008b991`
- `ntdll!RtlCopySecurityDescriptor` at `0x18008b71e`
- `ntdll!RtlCopySecurityDescriptor` at `0x18008b71e`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18008b7c4`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18008b876`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18008b9a5`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18008b7c4`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18008b876`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18008b9a5`
- `ntdll!RtlQueryInformationAcl` at `0x18008b804`
- `ntdll!RtlQueryInformationAcl` at `0x18008b804`
- `ntdll!RtlDeleteSecurityObject` at `0x18008b9df`
- `ntdll!RtlDeleteSecurityObject` at `0x18008b9df`
- `ntdll!RtlGetAce` at `0x18008b828`
- `ntdll!RtlGetAce` at `0x18008b91a`
- `ntdll!RtlGetAce` at `0x18008b828`
- `ntdll!RtlGetAce` at `0x18008b91a`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18008b7af`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18008b7af`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18008b972`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18008b972`
- `ntdll!RtlAddAccessAllowedAce` at `0x18008b95f`
- `ntdll!RtlAddAccessAllowedAce` at `0x18008b95f`
- `ntdll!RtlCreateAcl` at `0x18008b8fa`
- `ntdll!RtlCreateAcl` at `0x18008b8fa`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18008b76f`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18008b76f`
- `ntdll!RtlSubAuthoritySid` at `0x18008b745`
- `ntdll!RtlSubAuthoritySid` at `0x18008b75c`
- `ntdll!RtlSubAuthoritySid` at `0x18008b745`
- `ntdll!RtlSubAuthoritySid` at `0x18008b75c`
- `ntdll!RtlInitializeSid` at `0x18008b739`
- `ntdll!RtlInitializeSid` at `0x18008b739`
- `ntdll!RtlFreeHeap` at `0x18008b9c6`
- `ntdll!RtlFreeHeap` at `0x18008b9c6`
- `ntdll!RtlAllocateHeap` at `0x18008b8d4`
- `ntdll!RtlAllocateHeap` at `0x18008b8d4`
- `ntdll!RtlLengthSid` at `0x18008b8b7`
- `ntdll!RtlLengthSid` at `0x18008b8b7`
- `ntdll!RtlEqualSid` at `0x18008b840`
- `ntdll!RtlEqualSid` at `0x18008b840`

## pseudocode

```c
__int64 __fastcall SampModifyAccountSecurity(
        __int64 a1,
        int a2,
        char a3,
        void *a4,
        PSECURITY_DESCRIPTOR *a5,
        ULONG *a6)
{
  ACCESS_MASK v6; // r13d
  bool v9; // zf
  PUNICODE_STRING v10; // rcx
  NTSTATUS v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // r9
  PSECURITY_DESCRIPTOR v14; // rcx
  int v15; // r14d
  ULONG v16; // esi
  ULONG v17; // ebx
  unsigned __int16 *v18; // rax
  PSECURITY_DESCRIPTOR v19; // rcx
  struct _ACL *Heap; // rax
  struct _ACL *v22; // rdi
  ULONG v23; // eax
  ULONG i; // ebx
  PSECURITY_DESCRIPTOR v25; // rcx
  unsigned __int8 DaclPresent; // [rsp+30h] [rbp-A9h] BYREF
  char v27; // [rsp+31h] [rbp-A8h]
  unsigned __int8 DaclDefaulted[6]; // [rsp+32h] [rbp-A7h] BYREF
  PSECURITY_DESCRIPTOR pDestinationSecurityDescriptor; // [rsp+38h] [rbp-A1h] BYREF
  PVOID Ace; // [rsp+40h] [rbp-99h] BYREF
  PACL Dacl; // [rsp+48h] [rbp-91h] BYREF
  PGENERIC_MAPPING GenericMapping; // [rsp+50h] [rbp-89h]
  _OWORD SecurityDescriptor[2]; // [rsp+58h] [rbp-81h] BYREF
  __int64 v34; // [rsp+78h] [rbp-61h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+80h] [rbp-59h] BYREF
  __int64 Information; // [rsp+88h] [rbp-51h] BYREF
  int v37; // [rsp+90h] [rbp-49h]
  _DWORD v38[4]; // [rsp+98h] [rbp-41h] BYREF
  _DWORD v39[4]; // [rsp+A8h] [rbp-31h] BYREF
  _BYTE Sid[32]; // [rsp+B8h] [rbp-21h] BYREF

  v27 = a3;
  v6 = 985087;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *a5 = 0;
  *a6 = 0;
  v9 = (*(_BYTE *)(a1 + 192) & 2) == 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  Dacl = 0;
  DaclDefaulted[0] = 0;
  DaclPresent = 0;
  Information = 0;
  v37 = 0;
  Ace = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v34 = 0;
  pDestinationSecurityDescriptor = 0;
  v39[0] = 131088;
  v39[1] = 131086;
  v39[2] = 131073;
  v39[3] = 983071;
  v38[0] = 131866;
  v38[1] = 131140;
  v38[2] = 131137;
  v38[3] = 985087;
  if ( v9 )
  {
    v11 = RtlCopySecurityDescriptor(a4, &pDestinationSecurityDescriptor);
    if ( v11 >= 0 )
    {
      RtlInitializeSid(Sid, &IdentifierAuthority, 2u);
      *RtlSubAuthoritySid(Sid, 0) = 32;
      *RtlSubAuthoritySid(Sid, 1u) = 548;
      RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
      if ( a2 == 4 )
      {
        GenericMapping = (PGENERIC_MAPPING)v38;
      }
      else
      {
        if ( a2 != 2 )
        {
          v11 = -1073741811;
          goto LABEL_37;
        }
        v6 = 983071;
        GenericMapping = (PGENERIC_MAPPING)v39;
      }
      RtlGetDaclSecurityDescriptor(a4, &DaclPresent, &Dacl, DaclDefaulted);
      if ( !DaclPresent )
      {
        v14 = pDestinationSecurityDescriptor;
        *a5 = pDestinationSecurityDescriptor;
        *a6 = RtlLengthSecurityDescriptor(v14);
        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
          WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 33, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids, 0, 0);
        return 0;
      }
      RtlQueryInformationAcl(Dacl, &Information, 0xCu, AclSizeInformation);
      v15 = -1;
      v16 = 8;
      v17 = 0;
      if ( (_DWORD)Information )
      {
        while ( 1 )
        {
          RtlGetAce(Dacl, v17, &Ace);
          v18 = (unsigned __int16 *)Ace;
          if ( *(_BYTE *)Ace )
            goto LABEL_17;
          if ( !RtlEqualSid(Sid, (char *)Ace + 8) )
            break;
          v15 = v17;
LABEL_18:
          if ( ++v17 >= (unsigned int)Information )
            goto LABEL_19;
        }
        v18 = (unsigned __int16 *)Ace;
LABEL_17:
        v16 += v18[1];
        goto LABEL_18;
      }
LABEL_19:
      if ( !v27 )
      {
        if ( v15 != -1 )
        {
          v19 = pDestinationSecurityDescriptor;
          *a5 = pDestinationSecurityDescriptor;
          *a6 = RtlLengthSecurityDescriptor(v19);
          if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
            WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 34, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids, 0, 0);
          return 0;
        }
        v16 += RtlLengthSid(Sid) + 8;
      }
      Heap = (struct _ACL *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v16);
      v22 = Heap;
      if ( Heap )
      {
        RtlCreateAcl(Heap, v16, 2u);
        v23 = Information;
        for ( i = 0; i < v23; ++i )
        {
          if ( i != v15 )
          {
            RtlGetAce(Dacl, i, &Ace);
            RtlAddAce(v22, 2u, 0, Ace, *((unsigned __int16 *)Ace + 1));
            v23 = Information;
          }
        }
        if ( !v27 )
          RtlAddAccessAllowedAce(v22, 2u, v6, Sid);
        RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v22, 0);
        v11 = RtlSetSecurityObject(4u, SecurityDescriptor, &pDestinationSecurityDescriptor, GenericMapping, 0);
        if ( v11 >= 0 )
        {
          v25 = pDestinationSecurityDescriptor;
          *a5 = pDestinationSecurityDescriptor;
          *a6 = RtlLengthSecurityDescriptor(v25);
          pDestinationSecurityDescriptor = 0;
        }
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v22);
      }
      else
      {
        v11 = -1073741670;
      }
    }
LABEL_37:
    if ( pDestinationSecurityDescriptor )
      RtlDeleteSecurityObject(&pDestinationSecurityDescriptor);
    v10 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
      return (unsigned int)v11;
    v12 = 35;
    v13 = (unsigned int)v11;
    goto LABEL_41;
  }
  v10 = WPP_GLOBAL_Control;
  v11 = -1073741823;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    v12 = 32;
    v13 = 3221225473LL;
LABEL_41:
    WPP_SF_Dd(v10[3].Buffer, v12, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids, v13, v11);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18008b62c  push    rbp
0x18008b62e  push    rbx
0x18008b62f  push    rsi
0x18008b630  push    rdi
0x18008b631  push    r12
0x18008b633  push    r13
0x18008b635  push    r14
0x18008b637  push    r15
0x18008b639  lea     rbp, [rsp-0Fh]
0x18008b63e  sub     rsp, 0E8h
0x18008b645  mov     rax, cs:__security_cookie
0x18008b64c  xor     rax, rsp
0x18008b64f  mov     [rbp+47h+var_48], rax
0x18008b653  mov     r15, [rbp+47h+arg_20]
0x18008b657  xor     r14d, r14d
0x18008b65a  mov     r12, [rbp+47h+arg_28]
0x18008b65e  xor     eax, eax
0x18008b660  xorps   xmm0, xmm0
0x18008b663  mov     [rsp+120h+var_EF], r8b
0x18008b668  mov     r13d, 0F07FFh
0x18008b66e  mov     dword ptr [rbp+47h+IdentifierAuthority.Value], r14d
0x18008b672  mov     [r15], r14
0x18008b675  mov     rdi, r9
0x18008b678  mov     [r12], r14d
0x18008b67c  mov     esi, edx
0x18008b67e  test    byte ptr [rcx+0C0h], 2
0x18008b685  mov     word ptr [rbp+47h+IdentifierAuthority.Value+4], 500h
0x18008b68b  mov     [rsp+120h+Dacl], r14
0x18008b690  mov     [rsp+120h+DaclDefaulted], r14b
0x18008b695  mov     [rsp+120h+DaclPresent], r14b
0x18008b69a  mov     [rbp+47h+Information], rax
0x18008b69e  mov     [rbp+47h+var_90], eax
0x18008b6a1  mov     [rsp+120h+Ace], r14
0x18008b6a6  movups  [rsp+120h+SecurityDescriptor], xmm0
0x18008b6ab  mov     [rbp+47h+var_A8], rax
0x18008b6af  movups  [rbp+47h+var_B8], xmm0
0x18008b6b3  mov     [rsp+120h+pDestinationSecurityDescriptor], r14
0x18008b6b8  mov     [rbp+47h+var_78], 20010h
0x18008b6bf  mov     [rbp+47h+var_74], 2000Eh
0x18008b6c6  mov     [rbp+47h+var_70], 20001h
0x18008b6cd  mov     [rbp+47h+var_6C], 0F001Fh
0x18008b6d4  mov     [rbp+47h+var_88], 2031Ah
0x18008b6db  mov     [rbp+47h+var_84], 20044h
0x18008b6e2  mov     [rbp+47h+var_80], 20041h
0x18008b6e9  mov     [rbp+47h+var_7C], r13d
0x18008b6ed  jz      short loc_18008B716
0x18008b6ef  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b6f6  mov     ebx, 0C0000001h
0x18008b6fb  test    dword ptr [rcx+44h], 20000h
0x18008b702  jz      loc_18008BA11
0x18008b708  lea     edx, [rax+20h]
0x18008b70b  mov     r9d, 0C0000001h
0x18008b711  jmp     loc_18008B9FD
0x18008b716  lea     rdx, [rsp+120h+pDestinationSecurityDescriptor]; pDestinationSecurityDescriptor
0x18008b71b  mov     rcx, rdi; pSourceSecurityDescriptor
0x18008b71e  call    cs:__imp_RtlCopySecurityDescriptor
0x18008b724  mov     ebx, eax
0x18008b726  test    eax, eax
0x18008b728  js      loc_18008B9D3
0x18008b72e  mov     r8b, 2; SubAuthorityCount
0x18008b731  lea     rdx, [rbp+47h+IdentifierAuthority]; IdentifierAuthority
0x18008b735  lea     rcx, [rbp+47h+Sid]; Sid
0x18008b739  call    cs:__imp_RtlInitializeSid
0x18008b73f  xor     edx, edx; SubAuthority
0x18008b741  lea     rcx, [rbp+47h+Sid]; Sid
0x18008b745  call    cs:__imp_RtlSubAuthoritySid
0x18008b74b  mov     ebx, 1
0x18008b750  lea     rcx, [rbp+47h+Sid]; Sid
0x18008b754  mov     edx, ebx; SubAuthority
0x18008b756  mov     dword ptr [rax], 20h ; ' '
0x18008b75c  call    cs:__imp_RtlSubAuthoritySid
0x18008b762  mov     edx, ebx; Revision
0x18008b764  lea     rcx, [rsp+120h+SecurityDescriptor]; SecurityDescriptor
0x18008b769  mov     dword ptr [rax], 224h
0x18008b76f  call    cs:__imp_RtlCreateSecurityDescriptor
0x18008b775  cmp     esi, 4
0x18008b778  jnz     short loc_18008B785
0x18008b77a  lea     rbx, [rbp+47h+var_88]
0x18008b77e  mov     [rsp+120h+GenericMapping], rbx
0x18008b783  jmp     short loc_18008B79D
0x18008b785  cmp     esi, 2
0x18008b788  jnz     loc_18008B9CE
0x18008b78e  lea     rax, [rbp+47h+var_78]
0x18008b792  mov     r13d, 0F001Fh
0x18008b798  mov     [rsp+120h+GenericMapping], rax
0x18008b79d  lea     r9, [rsp+120h+DaclDefaulted]; DaclDefaulted
0x18008b7a2  mov     rcx, rdi; SecurityDescriptor
0x18008b7a5  lea     r8, [rsp+120h+Dacl]; Dacl
0x18008b7aa  lea     rdx, [rsp+120h+DaclPresent]; DaclPresent
0x18008b7af  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x18008b7b5  cmp     [rsp+120h+DaclPresent], r14b
0x18008b7ba  jnz     short loc_18008B7F1
0x18008b7bc  mov     rcx, [rsp+120h+pDestinationSecurityDescriptor]; SecurityDescriptor
0x18008b7c1  mov     [r15], rcx
0x18008b7c4  call    cs:__imp_RtlLengthSecurityDescriptor
0x18008b7ca  mov     [r12], eax
0x18008b7ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b7d5  test    dword ptr [rcx+44h], 20000h
0x18008b7dc  jz      loc_18008B8AC
0x18008b7e2  mov     edx, 21h ; '!'
0x18008b7e7  mov     [rsp+120h+AceListLength], r14d
0x18008b7ec  jmp     loc_18008B899
0x18008b7f1  mov     rcx, [rsp+120h+Dacl]; Acl
0x18008b7f6  lea     rdx, [rbp+47h+Information]; Information
0x18008b7fa  mov     r9d, 2; InformationClass
0x18008b800  lea     r8d, [r9+0Ah]; InformationLength
0x18008b804  call    cs:__imp_RtlQueryInformationAcl
0x18008b80a  xor     edi, edi
0x18008b80c  or      r14d, 0FFFFFFFFh
0x18008b810  mov     esi, 8
0x18008b815  mov     ebx, edi
0x18008b817  cmp     dword ptr [rbp+47h+Information], edi
0x18008b81a  jbe     short loc_18008B861
0x18008b81c  mov     rcx, [rsp+120h+Dacl]; Acl
0x18008b821  lea     r8, [rsp+120h+Ace]; Ace
0x18008b826  mov     edx, ebx; AceIndex
0x18008b828  call    cs:__imp_RtlGetAce
0x18008b82e  mov     rax, [rsp+120h+Ace]
0x18008b833  cmp     [rax], dil
0x18008b836  jnz     short loc_18008B854
0x18008b838  lea     rdx, [rax+8]; Sid2
0x18008b83c  lea     rcx, [rbp+47h+Sid]; Sid1
0x18008b840  call    cs:__imp_RtlEqualSid
0x18008b846  test    al, al
0x18008b848  jz      short loc_18008B84F
0x18008b84a  mov     r14d, ebx
0x18008b84d  jmp     short loc_18008B85A
0x18008b84f  mov     rax, [rsp+120h+Ace]
0x18008b854  movzx   eax, word ptr [rax+2]
0x18008b858  add     esi, eax
0x18008b85a  inc     ebx
0x18008b85c  cmp     ebx, dword ptr [rbp+47h+Information]
0x18008b85f  jb      short loc_18008B81C
0x18008b861  cmp     [rsp+120h+var_EF], dil
0x18008b866  jnz     short loc_18008B8C2
0x18008b868  cmp     r14d, 0FFFFFFFFh
0x18008b86c  jz      short loc_18008B8B3
0x18008b86e  mov     rcx, [rsp+120h+pDestinationSecurityDescriptor]; SecurityDescriptor
0x18008b873  mov     [r15], rcx
0x18008b876  call    cs:__imp_RtlLengthSecurityDescriptor
0x18008b87c  mov     [r12], eax
0x18008b880  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b887  test    dword ptr [rcx+44h], 20000h
0x18008b88e  jz      short loc_18008B8AC
0x18008b890  mov     edx, 22h ; '"'
0x18008b895  mov     [rsp+120h+AceListLength], edi
0x18008b899  mov     rcx, [rcx+38h]
0x18008b89d  lea     r8, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids
0x18008b8a4  xor     r9d, r9d
0x18008b8a7  call    WPP_SF_Dd
0x18008b8ac  xor     eax, eax
0x18008b8ae  jmp     loc_18008BA13
0x18008b8b3  lea     rcx, [rbp+47h+Sid]; Sid
0x18008b8b7  call    cs:__imp_RtlLengthSid
0x18008b8bd  add     eax, 8
0x18008b8c0  add     esi, eax
0x18008b8c2  mov     rcx, gs:60h
0x18008b8cb  xor     edx, edx; Flags
0x18008b8cd  mov     r8d, esi; Size
0x18008b8d0  mov     rcx, [rcx+30h]; HeapHandle
0x18008b8d4  call    cs:__imp_RtlAllocateHeap
0x18008b8da  mov     rdi, rax
0x18008b8dd  test    rax, rax
0x18008b8e0  jnz     short loc_18008B8EF
0x18008b8e2  mov     ebx, 0C000009Ah
0x18008b8e7  xor     r14d, r14d
0x18008b8ea  jmp     loc_18008B9D3
0x18008b8ef  mov     r8d, 2; AclRevision
0x18008b8f5  mov     edx, esi; AclSize
0x18008b8f7  mov     rcx, rdi; Acl
0x18008b8fa  call    cs:__imp_RtlCreateAcl
0x18008b900  mov     eax, dword ptr [rbp+47h+Information]
0x18008b903  xor     ebx, ebx
0x18008b905  test    eax, eax
0x18008b907  jz      short loc_18008B947
0x18008b909  cmp     ebx, r14d
0x18008b90c  jz      short loc_18008B941
0x18008b90e  mov     rcx, [rsp+120h+Dacl]; Acl
0x18008b913  lea     r8, [rsp+120h+Ace]; Ace
0x18008b918  mov     edx, ebx; AceIndex
0x18008b91a  call    cs:__imp_RtlGetAce
0x18008b920  mov     r9, [rsp+120h+Ace]; AceList
0x18008b925  xor     r8d, r8d; StartingAceIndex
0x18008b928  mov     rcx, rdi; Acl
0x18008b92b  movzx   eax, word ptr [r9+2]
0x18008b930  lea     edx, [r8+2]; AceRevision
0x18008b934  mov     [rsp+120h+AceListLength], eax; AceListLength
0x18008b938  call    cs:__imp_RtlAddAce
0x18008b93e  mov     eax, dword ptr [rbp+47h+Information]
0x18008b941  inc     ebx
0x18008b943  cmp     ebx, eax
0x18008b945  jb      short loc_18008B909
0x18008b947  xor     r14d, r14d
0x18008b94a  cmp     [rsp+120h+var_EF], r14b
0x18008b94f  jnz     short loc_18008B965
0x18008b951  lea     r9, [rbp+47h+Sid]; Sid
0x18008b955  mov     r8d, r13d; AccessMask
0x18008b958  lea     edx, [r14+2]; Revision
0x18008b95c  mov     rcx, rdi; Acl
0x18008b95f  call    cs:__imp_RtlAddAccessAllowedAce
0x18008b965  xor     r9d, r9d; DaclDefaulted
0x18008b968  lea     rcx, [rsp+120h+SecurityDescriptor]; SecurityDescriptor
0x18008b96d  mov     r8, rdi; Dacl
0x18008b970  mov     dl, 1; DaclPresent
0x18008b972  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x18008b978  mov     r9, [rsp+120h+GenericMapping]; GenericMapping
0x18008b97d  lea     r8, [rsp+120h+pDestinationSecurityDescriptor]; ObjectsSecurityDescriptor
0x18008b982  lea     rdx, [rsp+120h+SecurityDescriptor]; ModificationDescriptor
0x18008b987  mov     qword ptr [rsp+120h+AceListLength], r14; Token
0x18008b98c  mov     ecx, 4; SecurityInformation
0x18008b991  call    cs:__imp_RtlSetSecurityObject
0x18008b997  mov     ebx, eax
0x18008b999  test    eax, eax
0x18008b99b  js      short loc_18008B9B4
0x18008b99d  mov     rcx, [rsp+120h+pDestinationSecurityDescriptor]; SecurityDescriptor
0x18008b9a2  mov     [r15], rcx
0x18008b9a5  call    cs:__imp_RtlLengthSecurityDescriptor
0x18008b9ab  mov     [r12], eax
0x18008b9af  mov     [rsp+120h+pDestinationSecurityDescriptor], r14
0x18008b9b4  mov     rcx, gs:60h
0x18008b9bd  mov     r8, rdi; P
0x18008b9c0  xor     edx, edx; Flags
0x18008b9c2  mov     rcx, [rcx+30h]; HeapHandle
0x18008b9c6  call    cs:__imp_RtlFreeHeap
0x18008b9cc  jmp     short loc_18008B9D3
0x18008b9ce  mov     ebx, 0C000000Dh
0x18008b9d3  cmp     [rsp+120h+pDestinationSecurityDescriptor], r14
0x18008b9d8  jz      short loc_18008B9E5
0x18008b9da  lea     rcx, [rsp+120h+pDestinationSecurityDescriptor]; ObjectDescriptor
0x18008b9df  call    cs:__imp_RtlDeleteSecurityObject
0x18008b9e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b9ec  test    dword ptr [rcx+44h], 20000h
0x18008b9f3  jz      short loc_18008BA11
0x18008b9f5  mov     edx, 23h ; '#'
0x18008b9fa  mov     r9d, ebx
0x18008b9fd  mov     rcx, [rcx+38h]
0x18008ba01  lea     r8, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids
0x18008ba08  mov     [rsp+120h+AceListLength], ebx
0x18008ba0c  call    WPP_SF_Dd
0x18008ba11  mov     eax, ebx
0x18008ba13  mov     rcx, [rbp+47h+var_48]
0x18008ba17  xor     rcx, rsp; StackCookie
0x18008ba1a  call    __security_check_cookie
0x18008ba1f  add     rsp, 0E8h
0x18008ba26  pop     r15
0x18008ba28  pop     r14
0x18008ba2a  pop     r13
0x18008ba2c  pop     r12
0x18008ba2e  pop     rdi
0x18008ba2f  pop     rsi
0x18008ba30  pop     rbx
0x18008ba31  pop     rbp
0x18008ba32  retn
```
