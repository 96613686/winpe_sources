# CreateTermSrvReadyEvent

- ea: `0x18000ef7c`
- end: `0x18000f376`
- name: `CreateTermSrvReadyEvent`
- size: `1018`
- prototype: `__int64 __fastcall(PHANDLE EventHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180010c30`

## callees

- `0x18000ef7c`
- `0x1800138f0`

## import_xrefs

- `KERNELBASE!WTSGetServiceSessionId` at `0x18000f044`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18000f044`
- `KERNELBASE!LocalAlloc` at `0x18000f1d9`
- `KERNELBASE!LocalAlloc` at `0x18000f1d9`
- `ntdll!NtOpenEvent` at `0x18000f060`
- `ntdll!NtOpenEvent` at `0x18000f060`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x18000f168`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x18000f168`
- `ntdll!RtlFreeSid` at `0x18000f307`
- `ntdll!RtlFreeSid` at `0x18000f31d`
- `ntdll!RtlFreeSid` at `0x18000f333`
- `ntdll!RtlFreeSid` at `0x18000f307`
- `ntdll!RtlFreeSid` at `0x18000f31d`
- `ntdll!RtlFreeSid` at `0x18000f333`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18000f2c5`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18000f2c5`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18000f2a8`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18000f2a8`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000f228`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000f24c`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000f26f`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000f28f`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000f228`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000f24c`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000f26f`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000f28f`
- `ntdll!RtlCreateAcl` at `0x18000f1fe`
- `ntdll!RtlCreateAcl` at `0x18000f1fe`
- `ntdll!RtlLengthSid` at `0x18000f183`
- `ntdll!RtlLengthSid` at `0x18000f197`
- `ntdll!RtlLengthSid` at `0x18000f1ab`
- `ntdll!RtlLengthSid` at `0x18000f1be`
- `ntdll!RtlLengthSid` at `0x18000f183`
- `ntdll!RtlLengthSid` at `0x18000f197`
- `ntdll!RtlLengthSid` at `0x18000f1ab`
- `ntdll!RtlLengthSid` at `0x18000f1be`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000f0a9`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000f0f3`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000f145`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000f0a9`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000f0f3`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000f145`
- `ntdll!RtlInitUnicodeString` at `0x18000f00a`
- `ntdll!RtlInitUnicodeString` at `0x18000f00a`
- `ntdll!NtCreateEvent` at `0x18000f2ef`
- `ntdll!NtCreateEvent` at `0x18000f2ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f347`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f347`

## string_xrefs

- `0x18000efd1`: `\BaseNamedObjects\TermSrvReadyEvent`

## pseudocode

```c
NTSTATUS __fastcall CreateTermSrvReadyEvent(PHANDLE EventHandle)
{
  ULONG SessionId; // ebx
  struct _ACL *v4; // rbx
  NTSTATUS Acl; // edi
  ULONG v6; // r14d
  ULONG v7; // r14d
  ULONG v8; // r14d
  ULONG v9; // r14d
  struct _ACL *v10; // rax
  struct _ACL *v11; // rsi
  PSID Sid; // [rsp+60h] [rbp-A0h] BYREF
  PSID v13; // [rsp+68h] [rbp-98h] BYREF
  PSID v14; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v15[2]; // [rsp+78h] [rbp-88h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-78h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+B8h] [rbp-48h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+C8h] [rbp-38h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v19; // [rsp+D0h] [rbp-30h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v20; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v21[48]; // [rsp+E0h] [rbp-20h] BYREF
  char v22[48]; // [rsp+110h] [rbp+10h] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_DWORD *)v19.Value = 0;
  *(_WORD *)&v19.Value[4] = 256;
  v15[1] = L"lpacSessionManagement";
  *(_DWORD *)v20.Value = 0;
  *(_WORD *)&v20.Value[4] = 3840;
  Sid = 0;
  v13 = 0;
  v14 = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  v15[0] = 2883626;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\BaseNamedObjects\\TermSrvReadyEvent");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  memset(&ObjectAttributes.Attributes, 0, 24);
  SessionId = NtCurrentPeb()->SessionId;
  if ( SessionId != (unsigned int)WTSGetServiceSessionId() )
    return NtOpenEvent(EventHandle, 0x100000u, &ObjectAttributes);
  v4 = 0;
  Acl = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &Sid);
  if ( Acl >= 0 )
  {
    Acl = RtlAllocateAndInitializeSid(&v19, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &v13);
    if ( Acl >= 0 )
    {
      Acl = RtlAllocateAndInitializeSid(&v20, 2u, 2u, 1u, 0, 0, 0, 0, 0, 0, &v14);
      if ( Acl >= 0 )
      {
        Acl = RtlDeriveCapabilitySidsFromName(v15, v22, v21);
        if ( Acl >= 0 )
        {
          v6 = RtlLengthSid(v14);
          v7 = RtlLengthSid(v13) + v6;
          v8 = RtlLengthSid(Sid) + v7;
          v9 = RtlLengthSid(v21) + 64 + v8;
          v10 = (struct _ACL *)LocalAlloc(0, v9 + 40LL);
          v4 = v10;
          if ( v10 )
          {
            v11 = v10 + 5;
            Acl = RtlCreateAcl(v10 + 5, v9, 2u);
            if ( Acl >= 0 )
            {
              Acl = RtlAddAccessAllowedAce(v11, 2u, 0x100000u, v13);
              if ( Acl >= 0 )
              {
                Acl = RtlAddAccessAllowedAce(v11, 2u, 0x100000u, v14);
                if ( Acl >= 0 )
                {
                  Acl = RtlAddAccessAllowedAce(v11, 2u, 0x100000u, v21);
                  if ( Acl >= 0 )
                  {
                    Acl = RtlAddAccessAllowedAce(v11, 2u, 2u, Sid);
                    if ( Acl >= 0 )
                    {
                      Acl = RtlCreateSecurityDescriptor(v4, 1u);
                      if ( Acl >= 0 )
                      {
                        Acl = RtlSetDaclSecurityDescriptor(v4, 1u, v11, 0);
                        if ( Acl >= 0 )
                        {
                          ObjectAttributes.SecurityDescriptor = v4;
                          Acl = NtCreateEvent(EventHandle, 0x2000000u, &ObjectAttributes, NotificationEvent, 0);
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
    }
  }
  if ( Sid )
    RtlFreeSid(Sid);
  if ( v13 )
    RtlFreeSid(v13);
  if ( v14 )
    RtlFreeSid(v14);
  if ( v4 )
    LocalFree(v4);
  return Acl;
}

```

## disassembly

```asm
0x18000ef7c  push    rbp
0x18000ef7e  push    rbx
0x18000ef7f  push    rsi
0x18000ef80  push    rdi
0x18000ef81  push    r12
0x18000ef83  push    r13
0x18000ef85  push    r14
0x18000ef87  push    r15
0x18000ef89  lea     rbp, [rsp-58h]
0x18000ef8e  sub     rsp, 158h
0x18000ef95  mov     rax, cs:__security_cookie
0x18000ef9c  xor     rax, rsp
0x18000ef9f  mov     [rbp+90h+var_50], rax
0x18000efa3  xor     r12d, r12d
0x18000efa6  mov     word ptr [rbp+90h+IdentifierAuthority.Value+4], 500h
0x18000efac  xorps   xmm0, xmm0
0x18000efaf  mov     dword ptr [rbp+90h+IdentifierAuthority.Value], r12d
0x18000efb3  xor     eax, eax
0x18000efb5  mov     dword ptr [rbp+90h+var_C0.Value], r12d
0x18000efb9  lea     rax, aLpacsessionman; "lpacSessionManagement"
0x18000efc0  mov     word ptr [rbp+90h+var_C0.Value+4], 100h
0x18000efc6  mov     r15, rcx
0x18000efc9  mov     [rbp+90h+var_110], rax
0x18000efcd  movups  xmmword ptr [rbp+90h+ObjectAttributes.ObjectName], xmm0
0x18000efd1  lea     rdx, aBasenamedobjec; "\\BaseNamedObjects\\TermSrvReadyEvent"
0x18000efd8  mov     dword ptr [rbp+90h+var_B8.Value], r12d
0x18000efdc  lea     rcx, [rbp+90h+DestinationString]; DestinationString
0x18000efe0  mov     word ptr [rbp+90h+var_B8.Value+4], 0F00h
0x18000efe6  mov     [rsp+190h+var_130], r12
0x18000efeb  mov     [rsp+190h+var_128], r12
0x18000eff0  mov     [rsp+190h+var_120], r12
0x18000eff5  movups  xmmword ptr [rbp+90h+ObjectAttributes.Length], xmm0
0x18000eff9  mov     [rsp+190h+var_118], 2C002Ah
0x18000f002  movups  xmmword ptr [rbp+90h+ObjectAttributes+1Ch], xmm0
0x18000f006  movups  xmmword ptr [rbp+90h+DestinationString.Length], xmm0
0x18000f00a  call    cs:__imp_RtlInitUnicodeString
0x18000f011  nop     dword ptr [rax+rax+00h]
0x18000f016  mov     [rbp+90h+ObjectAttributes.Length], 30h ; '0'
0x18000f01d  lea     rax, [rbp+90h+DestinationString]
0x18000f021  mov     [rbp+90h+ObjectAttributes.ObjectName], rax
0x18000f025  xorps   xmm0, xmm0
0x18000f028  movdqu  xmmword ptr [rbp+90h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000f02d  mov     [rbp+90h+ObjectAttributes.RootDirectory], r12
0x18000f031  mov     [rbp+90h+ObjectAttributes.Attributes], r12d
0x18000f035  mov     rax, gs:60h
0x18000f03e  mov     ebx, [rax+2C0h]
0x18000f044  call    cs:__imp_WTSGetServiceSessionId
0x18000f04b  nop     dword ptr [rax+rax+00h]
0x18000f050  cmp     ebx, eax
0x18000f052  jz      short loc_18000F071
0x18000f054  lea     r8, [rbp+90h+ObjectAttributes]; ObjectAttributes
0x18000f058  mov     edx, 100000h; DesiredAccess
0x18000f05d  mov     rcx, r15; EventHandle
0x18000f060  call    cs:__imp_NtOpenEvent
0x18000f067  nop     dword ptr [rax+rax+00h]
0x18000f06c  jmp     loc_18000F355
0x18000f071  lea     rax, [rsp+190h+var_130]
0x18000f076  xor     r9d, r9d; SubAuthority1
0x18000f079  mov     [rsp+190h+Sid], rax; Sid
0x18000f07e  lea     rcx, [rbp+90h+IdentifierAuthority]; IdentifierAuthority
0x18000f082  mov     [rsp+190h+SubAuthority7], r12d; SubAuthority7
0x18000f087  mov     dl, 1; SubAuthorityCount
0x18000f089  mov     [rsp+190h+SubAuthority6], r12d; SubAuthority6
0x18000f08e  mov     rbx, r12
0x18000f091  mov     [rsp+190h+SubAuthority5], r12d; SubAuthority5
0x18000f096  lea     r8d, [r9+12h]; SubAuthority0
0x18000f09a  mov     [rsp+190h+SubAuthority4], r12d; SubAuthority4
0x18000f09f  mov     [rsp+190h+SubAuthority3], r12d; SubAuthority3
0x18000f0a4  mov     [rsp+190h+SubAuthority2], r12d; SubAuthority2
0x18000f0a9  call    cs:__imp_RtlAllocateAndInitializeSid
0x18000f0b0  nop     dword ptr [rax+rax+00h]
0x18000f0b5  mov     edi, eax
0x18000f0b7  test    eax, eax
0x18000f0b9  js      loc_18000F2FD
0x18000f0bf  lea     rax, [rsp+190h+var_128]
0x18000f0c4  xor     r9d, r9d; SubAuthority1
0x18000f0c7  mov     [rsp+190h+Sid], rax; Sid
0x18000f0cc  lea     rcx, [rbp+90h+var_C0]; IdentifierAuthority
0x18000f0d0  mov     [rsp+190h+SubAuthority7], r12d; SubAuthority7
0x18000f0d5  xor     r8d, r8d; SubAuthority0
0x18000f0d8  mov     [rsp+190h+SubAuthority6], r12d; SubAuthority6
0x18000f0dd  mov     dl, 1; SubAuthorityCount
0x18000f0df  mov     [rsp+190h+SubAuthority5], r12d; SubAuthority5
0x18000f0e4  mov     [rsp+190h+SubAuthority4], r12d; SubAuthority4
0x18000f0e9  mov     [rsp+190h+SubAuthority3], r12d; SubAuthority3
0x18000f0ee  mov     [rsp+190h+SubAuthority2], r12d; SubAuthority2
0x18000f0f3  call    cs:__imp_RtlAllocateAndInitializeSid
0x18000f0fa  nop     dword ptr [rax+rax+00h]
0x18000f0ff  mov     edi, eax
0x18000f101  test    eax, eax
0x18000f103  js      loc_18000F2FD
0x18000f109  lea     rax, [rsp+190h+var_120]
0x18000f10e  mov     r9d, 1; SubAuthority1
0x18000f114  mov     [rsp+190h+Sid], rax; Sid
0x18000f119  lea     rcx, [rbp+90h+var_B8]; IdentifierAuthority
0x18000f11d  mov     [rsp+190h+SubAuthority7], r12d; SubAuthority7
0x18000f122  mov     [rsp+190h+SubAuthority6], r12d; SubAuthority6
0x18000f127  mov     [rsp+190h+SubAuthority5], r12d; SubAuthority5
0x18000f12c  lea     r13d, [r9+1]
0x18000f130  mov     [rsp+190h+SubAuthority4], r12d; SubAuthority4
0x18000f135  mov     r8d, r13d; SubAuthority0
0x18000f138  mov     [rsp+190h+SubAuthority3], r12d; SubAuthority3
0x18000f13d  mov     dl, r13b; SubAuthorityCount
0x18000f140  mov     [rsp+190h+SubAuthority2], r12d; SubAuthority2
0x18000f145  call    cs:__imp_RtlAllocateAndInitializeSid
0x18000f14c  nop     dword ptr [rax+rax+00h]
0x18000f151  mov     edi, eax
0x18000f153  test    eax, eax
0x18000f155  js      loc_18000F2FD
0x18000f15b  lea     r8, [rbp+90h+var_B0]
0x18000f15f  lea     rdx, [rbp+90h+var_80]
0x18000f163  lea     rcx, [rsp+190h+var_118]
0x18000f168  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x18000f16f  nop     dword ptr [rax+rax+00h]
0x18000f174  mov     edi, eax
0x18000f176  test    eax, eax
0x18000f178  js      loc_18000F2FD
0x18000f17e  mov     rcx, [rsp+190h+var_120]; Sid
0x18000f183  call    cs:__imp_RtlLengthSid
0x18000f18a  nop     dword ptr [rax+rax+00h]
0x18000f18f  mov     rcx, [rsp+190h+var_128]; Sid
0x18000f194  mov     r14d, eax
0x18000f197  call    cs:__imp_RtlLengthSid
0x18000f19e  nop     dword ptr [rax+rax+00h]
0x18000f1a3  mov     rcx, [rsp+190h+var_130]; Sid
0x18000f1a8  add     r14d, eax
0x18000f1ab  call    cs:__imp_RtlLengthSid
0x18000f1b2  nop     dword ptr [rax+rax+00h]
0x18000f1b7  lea     rcx, [rbp+90h+var_B0]; Sid
0x18000f1bb  add     r14d, eax
0x18000f1be  call    cs:__imp_RtlLengthSid
0x18000f1c5  nop     dword ptr [rax+rax+00h]
0x18000f1ca  add     eax, 40h ; '@'
0x18000f1cd  xor     ecx, ecx; uFlags
0x18000f1cf  add     r14d, eax
0x18000f1d2  mov     edx, r14d
0x18000f1d5  add     rdx, 28h ; '('; uBytes
0x18000f1d9  call    cs:__imp_LocalAlloc
0x18000f1e0  nop     dword ptr [rax+rax+00h]
0x18000f1e5  mov     rbx, rax
0x18000f1e8  test    rax, rax
0x18000f1eb  jz      loc_18000F2FD
0x18000f1f1  lea     rsi, [rax+28h]
0x18000f1f5  mov     r8d, r13d; AclRevision
0x18000f1f8  mov     rcx, rsi; Acl
0x18000f1fb  mov     edx, r14d; AclSize
0x18000f1fe  call    cs:__imp_RtlCreateAcl
0x18000f205  nop     dword ptr [rax+rax+00h]
0x18000f20a  mov     edi, eax
0x18000f20c  test    eax, eax
0x18000f20e  js      loc_18000F2FD
0x18000f214  mov     r9, [rsp+190h+var_128]; Sid
0x18000f219  mov     r14d, 100000h
0x18000f21f  mov     r8d, r14d; AccessMask
0x18000f222  mov     edx, r13d; Revision
0x18000f225  mov     rcx, rsi; Acl
0x18000f228  call    cs:__imp_RtlAddAccessAllowedAce
0x18000f22f  nop     dword ptr [rax+rax+00h]
0x18000f234  mov     edi, eax
0x18000f236  test    eax, eax
0x18000f238  js      loc_18000F2FD
0x18000f23e  mov     r9, [rsp+190h+var_120]; Sid
0x18000f243  mov     r8d, r14d; AccessMask
0x18000f246  mov     edx, r13d; Revision
0x18000f249  mov     rcx, rsi; Acl
0x18000f24c  call    cs:__imp_RtlAddAccessAllowedAce
0x18000f253  nop     dword ptr [rax+rax+00h]
0x18000f258  mov     edi, eax
0x18000f25a  test    eax, eax
0x18000f25c  js      loc_18000F2FD
0x18000f262  lea     r9, [rbp+90h+var_B0]; Sid
0x18000f266  mov     r8d, r14d; AccessMask
0x18000f269  mov     edx, r13d; Revision
0x18000f26c  mov     rcx, rsi; Acl
0x18000f26f  call    cs:__imp_RtlAddAccessAllowedAce
0x18000f276  nop     dword ptr [rax+rax+00h]
0x18000f27b  mov     edi, eax
0x18000f27d  test    eax, eax
0x18000f27f  js      short loc_18000F2FD
0x18000f281  mov     r9, [rsp+190h+var_130]; Sid
0x18000f286  mov     r8d, r13d; AccessMask
0x18000f289  mov     edx, r13d; Revision
0x18000f28c  mov     rcx, rsi; Acl
0x18000f28f  call    cs:__imp_RtlAddAccessAllowedAce
0x18000f296  nop     dword ptr [rax+rax+00h]
0x18000f29b  mov     edi, eax
0x18000f29d  test    eax, eax
0x18000f29f  js      short loc_18000F2FD
0x18000f2a1  lea     edx, [r13-1]; Revision
0x18000f2a5  mov     rcx, rbx; SecurityDescriptor
0x18000f2a8  call    cs:__imp_RtlCreateSecurityDescriptor
0x18000f2af  nop     dword ptr [rax+rax+00h]
0x18000f2b4  mov     edi, eax
0x18000f2b6  test    eax, eax
0x18000f2b8  js      short loc_18000F2FD
0x18000f2ba  xor     r9d, r9d; DaclDefaulted
0x18000f2bd  mov     r8, rsi; Dacl
0x18000f2c0  mov     dl, 1; DaclPresent
0x18000f2c2  mov     rcx, rbx; SecurityDescriptor
0x18000f2c5  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x18000f2cc  nop     dword ptr [rax+rax+00h]
0x18000f2d1  mov     edi, eax
0x18000f2d3  test    eax, eax
0x18000f2d5  js      short loc_18000F2FD
0x18000f2d7  xor     r9d, r9d; EventType
0x18000f2da  mov     [rbp+90h+ObjectAttributes.SecurityDescriptor], rbx
0x18000f2de  lea     r8, [rbp+90h+ObjectAttributes]; ObjectAttributes
0x18000f2e2  mov     byte ptr [rsp+190h+SubAuthority2], r12b; InitialState
0x18000f2e7  mov     edx, 2000000h; DesiredAccess
0x18000f2ec  mov     rcx, r15; EventHandle
0x18000f2ef  call    cs:__imp_NtCreateEvent
0x18000f2f6  nop     dword ptr [rax+rax+00h]
0x18000f2fb  mov     edi, eax
0x18000f2fd  mov     rcx, [rsp+190h+var_130]; Sid
0x18000f302  test    rcx, rcx
0x18000f305  jz      short loc_18000F313
0x18000f307  call    cs:__imp_RtlFreeSid
0x18000f30e  nop     dword ptr [rax+rax+00h]
0x18000f313  mov     rcx, [rsp+190h+var_128]; Sid
0x18000f318  test    rcx, rcx
0x18000f31b  jz      short loc_18000F329
0x18000f31d  call    cs:__imp_RtlFreeSid
0x18000f324  nop     dword ptr [rax+rax+00h]
0x18000f329  mov     rcx, [rsp+190h+var_120]; Sid
0x18000f32e  test    rcx, rcx
0x18000f331  jz      short loc_18000F33F
0x18000f333  call    cs:__imp_RtlFreeSid
0x18000f33a  nop     dword ptr [rax+rax+00h]
0x18000f33f  test    rbx, rbx
0x18000f342  jz      short loc_18000F353
0x18000f344  mov     rcx, rbx; hMem
0x18000f347  call    cs:__imp_LocalFree
0x18000f34e  nop     dword ptr [rax+rax+00h]
0x18000f353  mov     eax, edi
0x18000f355  mov     rcx, [rbp+90h+var_50]
0x18000f359  xor     rcx, rsp; StackCookie
0x18000f35c  call    __security_check_cookie
0x18000f361  add     rsp, 158h
0x18000f368  pop     r15
0x18000f36a  pop     r14
0x18000f36c  pop     r13
0x18000f36e  pop     r12
0x18000f370  pop     rdi
0x18000f371  pop     rsi
0x18000f372  pop     rbx
0x18000f373  pop     rbp
0x18000f374  retn
```
