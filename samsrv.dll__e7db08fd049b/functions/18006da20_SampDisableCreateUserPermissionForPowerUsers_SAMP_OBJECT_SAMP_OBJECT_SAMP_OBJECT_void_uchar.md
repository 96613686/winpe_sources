# SampDisableCreateUserPermissionForPowerUsers(_SAMP_OBJECT *,_SAMP_OBJECT *,_SAMP_OBJECT *,void *,uchar)

- ea: `0x18006da20`
- end: `0x18006ddd7`
- name: `?SampDisableCreateUserPermissionForPowerUsers@@YAJPEAU_SAMP_OBJECT@@00PEAXE@Z`
- size: `951`
- prototype: `int(struct _SAMP_OBJECT *, struct _SAMP_OBJECT *, struct _SAMP_OBJECT *, void *, unsigned __int8)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18001a0f0`
- `0x180025528`
- `0x180027e24`
- `0x18002cd80`
- `0x180037284`
- `0x1800372ac`
- `0x18006da20`
- `0x18008cd00`

## import_xrefs

- `ntdll!RtlAddAccessDeniedAce` at `0x18006dc51`
- `ntdll!RtlAddAccessDeniedAce` at `0x18006dc51`
- `ntdll!RtlAddAce` at `0x18006dc35`
- `ntdll!RtlAddAce` at `0x18006dc35`
- `ntdll!RtlGetAcesBufferSize` at `0x18006dc0e`
- `ntdll!RtlGetAcesBufferSize` at `0x18006dc0e`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x18006dc9e`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x18006dce7`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x18006dc9e`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x18006dce7`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18006dc84`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18006dc84`
- `ntdll!RtlCreateAcl` at `0x18006dbf7`
- `ntdll!RtlCreateAcl` at `0x18006dbf7`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18006dc68`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18006dc68`
- `ntdll!RtlSubAuthoritySid` at `0x18006db6a`
- `ntdll!RtlSubAuthoritySid` at `0x18006db7e`
- `ntdll!RtlSubAuthoritySid` at `0x18006db6a`
- `ntdll!RtlSubAuthoritySid` at `0x18006db7e`
- `ntdll!RtlInitializeSid` at `0x18006db5f`
- `ntdll!RtlInitializeSid` at `0x18006db5f`
- `ntdll!RtlFreeHeap` at `0x18006dd7a`
- `ntdll!RtlFreeHeap` at `0x18006dd7a`
- `ntdll!RtlAllocateHeap` at `0x18006dbda`
- `ntdll!RtlAllocateHeap` at `0x18006dbda`
- `ntdll!RtlLengthRequiredSid` at `0x18006db30`
- `ntdll!RtlLengthRequiredSid` at `0x18006db30`
- `ntdll!RtlLengthSid` at `0x18006dbbd`
- `ntdll!RtlLengthSid` at `0x18006dbbd`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18006dcfa`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18006dcfa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006db3d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006dcc7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006db3d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006dcc7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006dd48`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006dd62`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006dd83`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006dd48`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006dd62`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006dd83`

## pseudocode

```c
__int64 __fastcall SampDisableCreateUserPermissionForPowerUsers(
        struct _SAMP_OBJECT *a1,
        struct _SAMP_OBJECT *a2,
        struct _SAMP_OBJECT *a3,
        void *a4)
{
  struct _ACL *v6; // r14
  void *v7; // r15
  void *v8; // rsi
  PUNICODE_STRING v9; // rcx
  NTSTATUS Acl; // ebx
  int SecurityObject; // eax
  PUNICODE_STRING v12; // rcx
  __int64 v13; // rdx
  ULONG v14; // eax
  HLOCAL v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rdi
  int v18; // ebx
  ULONG v19; // ebx
  struct _ACL *Heap; // rax
  NTSTATUS v21; // eax
  HLOCAL v22; // rax
  HLOCAL v23; // rdi
  ULONG BufferLength; // [rsp+30h] [rbp-51h] BYREF
  ULONG AceListLength; // [rsp+34h] [rbp-4Dh] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-49h]
  _DWORD v28[2]; // [rsp+40h] [rbp-41h] BYREF
  void *v29; // [rsp+48h] [rbp-39h]
  _OWORD SecurityDescriptor[2]; // [rsp+50h] [rbp-31h] BYREF
  __int64 v31; // [rsp+70h] [rbp-11h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+78h] [rbp-9h] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  v28[1] = 0;
  hMem = 0;
  v31 = 0;
  AceListLength = 0;
  v6 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v7 = 0;
  v8 = 0;
  BufferLength = 0;
  v9 = WPP_GLOBAL_Control;
  if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control[3].Buffer, 200, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids);
    v9 = WPP_GLOBAL_Control;
  }
  if ( (*((_BYTE *)a1 + 192) & 2) != 0 )
  {
    Acl = 0;
    if ( *((char *)&v9[4].MaximumLength + 2) < 0 && HIBYTE(v9[4].Length) >= 4u )
      WPP_SF_(v9[3].Buffer, 201, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids);
    goto LABEL_38;
  }
  SecurityObject = SamrQuerySecurityObject(a2);
  Acl = SecurityObject;
  if ( SecurityObject < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) >= 0 || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
      goto LABEL_38;
    v13 = 202;
LABEL_37:
    WPP_SF_d(v12[3].Buffer, v13, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, (unsigned int)SecurityObject);
    goto LABEL_38;
  }
  v14 = RtlLengthRequiredSid(2u);
  v15 = LocalAlloc(0x40u, v14);
  v7 = v15;
  if ( !v15 )
  {
LABEL_13:
    Acl = -1073741801;
    goto LABEL_38;
  }
  RtlInitializeSid(v15, &IdentifierAuthority, 2u);
  *RtlSubAuthoritySid(v7, 0) = 32;
  *RtlSubAuthoritySid(v7, 1u) = 547;
  v16 = *((_QWORD *)hMem + 1);
  if ( (*(_BYTE *)(v16 + 2) & 4) == 0 )
    goto LABEL_15;
  if ( *(__int16 *)(v16 + 2) >= 0 )
  {
    v17 = *(_QWORD *)(v16 + 32);
  }
  else
  {
    if ( !*(_DWORD *)(v16 + 16) )
    {
LABEL_15:
      v17 = 0;
      goto LABEL_20;
    }
    v17 = v16 + *(unsigned int *)(v16 + 16);
  }
LABEL_20:
  v18 = *(unsigned __int16 *)(v17 + 2);
  v19 = RtlLengthSid(v7) + 8 + v18;
  Heap = (struct _ACL *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v19);
  v6 = Heap;
  if ( !Heap )
    goto LABEL_13;
  Acl = RtlCreateAcl(Heap, v19, 2u);
  if ( Acl >= 0 )
  {
    Acl = RtlGetAcesBufferSize(v17, &AceListLength);
    if ( Acl >= 0 )
    {
      Acl = RtlAddAce(v6, 2u, 0, (PVOID)(v17 + 8), AceListLength);
      if ( Acl >= 0 )
      {
        Acl = RtlAddAccessDeniedAce(v6, 2u, 0x50u, v7);
        if ( Acl >= 0 )
        {
          Acl = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
          if ( Acl >= 0 )
          {
            Acl = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v6, 0);
            if ( Acl >= 0 )
            {
              v21 = RtlAbsoluteToSelfRelativeSD(SecurityDescriptor, 0, &BufferLength);
              Acl = v21;
              if ( v21 >= 0 )
              {
                Acl = -1073741823;
                goto LABEL_38;
              }
              if ( v21 == -1073741789 )
              {
                v22 = LocalAlloc(0x40u, BufferLength);
                v8 = v22;
                if ( !v22 )
                {
                  Acl = -1073741670;
                  goto LABEL_38;
                }
                Acl = RtlAbsoluteToSelfRelativeSD(SecurityDescriptor, v22, &BufferLength);
                if ( Acl >= 0 )
                {
                  v29 = v8;
                  v28[0] = GetSecurityDescriptorLength(v8);
                  SecurityObject = SamrSetSecurityObject(a2, 4u, (__int64)v28);
                  Acl = SecurityObject;
                  if ( SecurityObject < 0 )
                  {
                    v12 = WPP_GLOBAL_Control;
                    if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0
                      && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
                    {
                      v13 = 203;
                      goto LABEL_37;
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_38:
  LocalFree(v8);
  v23 = hMem;
  if ( hMem )
  {
    _fgs__SAMPR_LOGON_HOURS((struct _SAMPR_LOGON_HOURS *)hMem);
    LocalFree(v23);
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  LocalFree(v7);
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control[3].Buffer,
      204,
      WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids,
      (unsigned int)Acl,
      Acl);
  return (unsigned int)Acl;
}

```

## disassembly

```asm
0x18006da20  push    rbp
0x18006da22  push    rbx
0x18006da23  push    rsi
0x18006da24  push    rdi
0x18006da25  push    r12
0x18006da27  push    r13
0x18006da29  push    r14
0x18006da2b  push    r15
0x18006da2d  lea     rbp, [rsp-17h]
0x18006da32  sub     rsp, 98h
0x18006da39  mov     rax, cs:__security_cookie
0x18006da40  xor     rax, rsp
0x18006da43  mov     [rbp+4Fh+var_50], rax
0x18006da47  xor     r13d, r13d
0x18006da4a  mov     word ptr [rbp+4Fh+IdentifierAuthority.Value+4], 500h
0x18006da50  xorps   xmm0, xmm0
0x18006da53  mov     [rbp+4Fh+var_8C], r13d
0x18006da57  xor     eax, eax
0x18006da59  mov     [rbp+4Fh+hMem], r13
0x18006da5d  mov     [rbp+4Fh+var_60], rax
0x18006da61  mov     r12, rdx
0x18006da64  mov     rbx, rcx
0x18006da67  mov     [rbp+4Fh+var_9C], r13d
0x18006da6b  mov     r14d, r13d
0x18006da6e  mov     dword ptr [rbp+4Fh+IdentifierAuthority.Value], r13d
0x18006da72  movups  [rbp+4Fh+SecurityDescriptor], xmm0
0x18006da76  mov     r15d, r13d
0x18006da79  mov     esi, r13d
0x18006da7c  movups  [rbp+4Fh+var_70], xmm0
0x18006da80  mov     [rbp+4Fh+BufferLength], r13d
0x18006da84  mov     rcx, cs:WPP_GLOBAL_Control
0x18006da8b  lea     rdi, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x18006da92  test    byte ptr [rcx+44h], 80h
0x18006da96  jz      short loc_18006DAB6
0x18006da98  cmp     byte ptr [rcx+41h], 4
0x18006da9c  jb      short loc_18006DAB6
0x18006da9e  mov     rcx, [rcx+38h]
0x18006daa2  mov     edx, 0C8h
0x18006daa7  mov     r8, rdi
0x18006daaa  call    WPP_SF_
0x18006daaf  mov     rcx, cs:WPP_GLOBAL_Control
0x18006dab6  test    byte ptr [rbx+0C0h], 2
0x18006dabd  jz      short loc_18006DAEC
0x18006dabf  mov     ebx, r13d
0x18006dac2  test    byte ptr [rcx+44h], 80h
0x18006dac6  jz      loc_18006DD45
0x18006dacc  cmp     byte ptr [rcx+41h], 4
0x18006dad0  jb      loc_18006DD45
0x18006dad6  mov     rcx, [rcx+38h]
0x18006dada  mov     edx, 0C9h
0x18006dadf  mov     r8, rdi
0x18006dae2  call    WPP_SF_
0x18006dae7  jmp     loc_18006DD45
0x18006daec  lea     r8, [rbp+4Fh+hMem]
0x18006daf0  mov     edx, 4
0x18006daf5  mov     rcx, r12; struct _SAMP_OBJECT *
0x18006daf8  call    SamrQuerySecurityObject
0x18006dafd  mov     ebx, eax
0x18006daff  test    eax, eax
0x18006db01  jns     short loc_18006DB2B
0x18006db03  mov     rcx, cs:WPP_GLOBAL_Control
0x18006db0a  test    byte ptr [rcx+44h], 80h
0x18006db0e  jz      loc_18006DD45
0x18006db14  cmp     byte ptr [rcx+41h], 2
0x18006db18  jb      loc_18006DD45
0x18006db1e  mov     edx, 0CAh
0x18006db23  mov     r8, rdi
0x18006db26  jmp     loc_18006DD39
0x18006db2b  mov     ecx, 2; SubAuthorityCount
0x18006db30  call    cs:__imp_RtlLengthRequiredSid
0x18006db36  mov     edx, eax; uBytes
0x18006db38  mov     ecx, 40h ; '@'; uFlags
0x18006db3d  call    cs:__imp_LocalAlloc
0x18006db43  mov     r15, rax
0x18006db46  test    rax, rax
0x18006db49  jnz     short loc_18006DB55
0x18006db4b  mov     ebx, 0C0000017h
0x18006db50  jmp     loc_18006DD45
0x18006db55  mov     r8b, 2; SubAuthorityCount
0x18006db58  lea     rdx, [rbp+4Fh+IdentifierAuthority]; IdentifierAuthority
0x18006db5c  mov     rcx, r15; Sid
0x18006db5f  call    cs:__imp_RtlInitializeSid
0x18006db65  xor     edx, edx; SubAuthority
0x18006db67  mov     rcx, r15; Sid
0x18006db6a  call    cs:__imp_RtlSubAuthoritySid
0x18006db70  mov     edx, 1; SubAuthority
0x18006db75  mov     rcx, r15; Sid
0x18006db78  mov     dword ptr [rax], 20h ; ' '
0x18006db7e  call    cs:__imp_RtlSubAuthoritySid
0x18006db84  mov     dword ptr [rax], 223h
0x18006db8a  mov     rax, [rbp+4Fh+hMem]
0x18006db8e  mov     rcx, [rax+8]
0x18006db92  test    byte ptr [rcx+2], 4
0x18006db96  jnz     short loc_18006DB9D
0x18006db98  mov     rdi, r13
0x18006db9b  jmp     short loc_18006DBB6
0x18006db9d  cmp     [rcx+2], r13w
0x18006dba2  jge     short loc_18006DBB2
0x18006dba4  cmp     [rcx+10h], r13d
0x18006dba8  jz      short loc_18006DB98
0x18006dbaa  mov     edi, [rcx+10h]
0x18006dbad  add     rdi, rcx
0x18006dbb0  jmp     short loc_18006DBB6
0x18006dbb2  mov     rdi, [rcx+20h]
0x18006dbb6  movzx   ebx, word ptr [rdi+2]
0x18006dbba  mov     rcx, r15; Sid
0x18006dbbd  call    cs:__imp_RtlLengthSid
0x18006dbc3  mov     rcx, gs:60h
0x18006dbcc  xor     edx, edx; Flags
0x18006dbce  add     eax, 8
0x18006dbd1  add     ebx, eax
0x18006dbd3  mov     r8d, ebx; Size
0x18006dbd6  mov     rcx, [rcx+30h]; HeapHandle
0x18006dbda  call    cs:__imp_RtlAllocateHeap
0x18006dbe0  mov     r14, rax
0x18006dbe3  test    rax, rax
0x18006dbe6  jz      loc_18006DB4B
0x18006dbec  mov     r8d, 2; AclRevision
0x18006dbf2  mov     edx, ebx; AclSize
0x18006dbf4  mov     rcx, rax; Acl
0x18006dbf7  call    cs:__imp_RtlCreateAcl
0x18006dbfd  mov     ebx, eax
0x18006dbff  test    eax, eax
0x18006dc01  js      loc_18006DD45
0x18006dc07  lea     rdx, [rbp+4Fh+var_9C]
0x18006dc0b  mov     rcx, rdi
0x18006dc0e  call    cs:__imp_RtlGetAcesBufferSize
0x18006dc14  mov     ebx, eax
0x18006dc16  test    eax, eax
0x18006dc18  js      loc_18006DD45
0x18006dc1e  mov     eax, [rbp+4Fh+var_9C]
0x18006dc21  lea     r9, [rdi+8]; AceList
0x18006dc25  xor     r8d, r8d; StartingAceIndex
0x18006dc28  mov     [rsp+0D0h+AceListLength], eax; AceListLength
0x18006dc2c  mov     rcx, r14; Acl
0x18006dc2f  lea     edi, [r8+2]
0x18006dc33  mov     edx, edi; AceRevision
0x18006dc35  call    cs:__imp_RtlAddAce
0x18006dc3b  mov     ebx, eax
0x18006dc3d  test    eax, eax
0x18006dc3f  js      loc_18006DD45
0x18006dc45  mov     r9, r15; Sid
0x18006dc48  lea     r8d, [rdi+4Eh]; AccessMask
0x18006dc4c  mov     edx, edi; Revision
0x18006dc4e  mov     rcx, r14; Acl
0x18006dc51  call    cs:__imp_RtlAddAccessDeniedAce
0x18006dc57  mov     ebx, eax
0x18006dc59  test    eax, eax
0x18006dc5b  js      loc_18006DD45
0x18006dc61  lea     edx, [rdi-1]; Revision
0x18006dc64  lea     rcx, [rbp+4Fh+SecurityDescriptor]; SecurityDescriptor
0x18006dc68  call    cs:__imp_RtlCreateSecurityDescriptor
0x18006dc6e  mov     ebx, eax
0x18006dc70  test    eax, eax
0x18006dc72  js      loc_18006DD45
0x18006dc78  xor     r9d, r9d; DaclDefaulted
0x18006dc7b  lea     rcx, [rbp+4Fh+SecurityDescriptor]; SecurityDescriptor
0x18006dc7f  mov     r8, r14; Dacl
0x18006dc82  mov     dl, 1; DaclPresent
0x18006dc84  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x18006dc8a  mov     ebx, eax
0x18006dc8c  test    eax, eax
0x18006dc8e  js      loc_18006DD45
0x18006dc94  lea     r8, [rbp+4Fh+BufferLength]; BufferLength
0x18006dc98  xor     edx, edx; SelfRelativeSecurityDescriptor
0x18006dc9a  lea     rcx, [rbp+4Fh+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x18006dc9e  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x18006dca4  mov     ebx, eax
0x18006dca6  test    eax, eax
0x18006dca8  js      short loc_18006DCB4
0x18006dcaa  mov     ebx, 0C0000001h
0x18006dcaf  jmp     loc_18006DD45
0x18006dcb4  cmp     eax, 0C0000023h
0x18006dcb9  jnz     loc_18006DD45
0x18006dcbf  mov     edx, [rbp+4Fh+BufferLength]; uBytes
0x18006dcc2  mov     ecx, 40h ; '@'; uFlags
0x18006dcc7  call    cs:__imp_LocalAlloc
0x18006dccd  mov     rsi, rax
0x18006dcd0  test    rax, rax
0x18006dcd3  jnz     short loc_18006DCDC
0x18006dcd5  mov     ebx, 0C000009Ah
0x18006dcda  jmp     short loc_18006DD45
0x18006dcdc  lea     r8, [rbp+4Fh+BufferLength]; BufferLength
0x18006dce0  mov     rdx, rsi; SelfRelativeSecurityDescriptor
0x18006dce3  lea     rcx, [rbp+4Fh+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x18006dce7  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x18006dced  mov     ebx, eax
0x18006dcef  test    eax, eax
0x18006dcf1  js      short loc_18006DD45
0x18006dcf3  mov     rcx, rsi; pSecurityDescriptor
0x18006dcf6  mov     [rbp+4Fh+var_88], rsi
0x18006dcfa  call    cs:__imp_GetSecurityDescriptorLength
0x18006dd00  lea     r8, [rbp+4Fh+var_90]
0x18006dd04  mov     edx, 4
0x18006dd09  mov     rcx, r12; struct _SAMP_OBJECT *
0x18006dd0c  mov     [rbp+4Fh+var_90], eax
0x18006dd0f  call    SamrSetSecurityObject
0x18006dd14  mov     ebx, eax
0x18006dd16  test    eax, eax
0x18006dd18  jns     short loc_18006DD45
0x18006dd1a  mov     rcx, cs:WPP_GLOBAL_Control
0x18006dd21  test    byte ptr [rcx+44h], 80h
0x18006dd25  jz      short loc_18006DD45
0x18006dd27  cmp     [rcx+41h], dil
0x18006dd2b  jb      short loc_18006DD45
0x18006dd2d  mov     edx, 0CBh
0x18006dd32  lea     r8, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x18006dd39  mov     rcx, [rcx+38h]
0x18006dd3d  mov     r9d, eax
0x18006dd40  call    WPP_SF_d
0x18006dd45  mov     rcx, rsi; hMem
0x18006dd48  call    cs:__imp_LocalFree
0x18006dd4e  mov     rdi, [rbp+4Fh+hMem]
0x18006dd52  test    rdi, rdi
0x18006dd55  jz      short loc_18006DD68
0x18006dd57  mov     rcx, rdi; struct _SAMPR_LOGON_HOURS *
0x18006dd5a  call    ?_fgs__SAMPR_LOGON_HOURS@@YAXPEAU_SAMPR_LOGON_HOURS@@@Z; _fgs__SAMPR_LOGON_HOURS(_SAMPR_LOGON_HOURS *)
0x18006dd5f  mov     rcx, rdi; hMem
0x18006dd62  call    cs:__imp_LocalFree
0x18006dd68  mov     rcx, gs:60h
0x18006dd71  mov     r8, r14; P
0x18006dd74  xor     edx, edx; Flags
0x18006dd76  mov     rcx, [rcx+30h]; HeapHandle
0x18006dd7a  call    cs:__imp_RtlFreeHeap
0x18006dd80  mov     rcx, r15; hMem
0x18006dd83  call    cs:__imp_LocalFree
0x18006dd89  mov     rcx, cs:WPP_GLOBAL_Control
0x18006dd90  test    dword ptr [rcx+44h], 20000h
0x18006dd97  jz      short loc_18006DDB5
0x18006dd99  mov     rcx, [rcx+38h]
0x18006dd9d  lea     r8, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x18006dda4  mov     edx, 0CCh
0x18006dda9  mov     [rsp+0D0h+AceListLength], ebx
0x18006ddad  mov     r9d, ebx
0x18006ddb0  call    WPP_SF_Dd
0x18006ddb5  mov     eax, ebx
0x18006ddb7  mov     rcx, [rbp+4Fh+var_50]
0x18006ddbb  xor     rcx, rsp; StackCookie
0x18006ddbe  call    __security_check_cookie
0x18006ddc3  add     rsp, 98h
0x18006ddca  pop     r15
0x18006ddcc  pop     r14
0x18006ddce  pop     r13
0x18006ddd0  pop     r12
0x18006ddd2  pop     rdi
0x18006ddd3  pop     rsi
0x18006ddd4  pop     rbx
0x18006ddd5  pop     rbp
0x18006ddd6  retn
```
