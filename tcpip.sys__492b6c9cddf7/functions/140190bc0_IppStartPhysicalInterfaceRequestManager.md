# IppStartPhysicalInterfaceRequestManager

- ea: `0x140190bc0`
- end: `0x140190f96`
- name: `IppStartPhysicalInterfaceRequestManager`
- size: `982`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x140053e98`
- `0x140190bc0`

## import_xrefs

- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140190ed3`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140190ed3`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140190eb5`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140190eb5`
- `ntoskrnl!RtlCreateAcl` at `0x140190e88`
- `ntoskrnl!RtlCreateAcl` at `0x140190e88`
- `ntoskrnl!RtlLengthSid` at `0x140190e20`
- `ntoskrnl!RtlLengthSid` at `0x140190e20`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140190d9c`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140190d9c`
- `ntoskrnl!KeInitializeSpinLock` at `0x140190d55`
- `ntoskrnl!KeInitializeSpinLock` at `0x140190d68`
- `ntoskrnl!KeInitializeSpinLock` at `0x140190d7b`
- `ntoskrnl!KeInitializeSpinLock` at `0x140190d55`
- `ntoskrnl!KeInitializeSpinLock` at `0x140190d68`
- `ntoskrnl!KeInitializeSpinLock` at `0x140190d7b`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140190db5`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140190db5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140190f27`
- `ntoskrnl!ExFreePoolWithTag` at `0x140190f38`
- `ntoskrnl!ExFreePoolWithTag` at `0x140190f73`
- `ntoskrnl!ExFreePoolWithTag` at `0x140190f27`
- `ntoskrnl!ExFreePoolWithTag` at `0x140190f38`
- `ntoskrnl!ExFreePoolWithTag` at `0x140190f73`
- `ntoskrnl!ExAllocatePool2` at `0x140190c0c`
- `ntoskrnl!ExAllocatePool2` at `0x140190dce`
- `ntoskrnl!ExAllocatePool2` at `0x140190e3b`
- `ntoskrnl!ExAllocatePool2` at `0x140190c0c`
- `ntoskrnl!ExAllocatePool2` at `0x140190dce`
- `ntoskrnl!ExAllocatePool2` at `0x140190e3b`
- `NETIO!NetioInitializeWorkQueue` at `0x140190c6f`
- `NETIO!NetioInitializeWorkQueue` at `0x140190c6f`
- `NETIO!NetioShutdownWorkQueue` at `0x140190f5e`
- `NETIO!NetioShutdownWorkQueue` at `0x140190f5e`
- `NETIO!RtlSuspendTimerWheel` at `0x140190cdc`
- `NETIO!RtlSuspendTimerWheel` at `0x140190cdc`
- `NETIO!RtlCleanupTimerWheel` at `0x140190f4f`
- `NETIO!RtlCleanupTimerWheel` at `0x140190f4f`
- `NETIO!RtlInitializeTimerWheel` at `0x140190cc9`
- `NETIO!RtlInitializeTimerWheel` at `0x140190cc9`
- `NETIO!NsiSetObjectSecurity` at `0x140190efe`
- `NETIO!NsiSetObjectSecurity` at `0x140190efe`

## string_xrefs

- `0x140190e58`: `physical interface request ACL (IPNG)`
- `0x140190deb`: `physical interface request SID (IPNG)`

## pseudocode

```c
__int64 __fastcall IppStartPhysicalInterfaceRequestManager(__int64 a1)
{
  __int64 Pool2; // rax
  __int64 v3; // r8
  NTSTATUS Acl; // ebx
  __int64 v6; // r8
  __int64 i; // r8
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 j; // r8
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rax
  ULONG v15; // eax
  char *v16; // rax
  __int64 v17; // r8
  void *Sid; // rsi
  __int64 v19; // r15
  struct _ACL *v20; // rax
  __int64 v21; // r8
  struct _ACL *v22; // r14
  _OWORD SecurityDescriptor[2]; // [rsp+30h] [rbp-49h] BYREF
  __int64 v24; // [rsp+50h] [rbp-29h]
  __int128 v25; // [rsp+58h] [rbp-21h] BYREF
  __int128 v26; // [rsp+68h] [rbp-11h]
  __int128 v27; // [rsp+78h] [rbp-1h]

  v24 = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v25 = 0;
  v26 = 0;
  v27 = 0;
  Pool2 = ExAllocatePool2(64, 248, 1632917332);
  *(_QWORD *)(a1 + 22608) = Pool2;
  if ( Pool2 )
  {
    Acl = NetioInitializeWorkQueue(a1 + 22664, IppPhysicalInterfaceRequestNotificationWorker, 0, IppDeviceObject);
    if ( Acl >= 0 )
    {
      RtlInitializeTimerWheel(*(_QWORD *)(a1 + 22608), 8, 1, 1, 0);
      RtlSuspendTimerWheel(*(_QWORD *)(a1 + 22608));
      for ( i = 0; i != 7; ++i )
      {
        v8 = 16 * i;
        v9 = 16 * i + a1 + 22488;
        v10 = 2 * (i + 1406);
        *(_QWORD *)(v8 + a1 + 22488) = v9;
        *(_QWORD *)(a1 + 8 * v10) = v9;
      }
      for ( j = 0; j != 7; ++j )
      {
        v12 = 16 * j;
        v13 = 16 * j + a1 + 22712;
        v14 = 2 * (j + 1420);
        *(_QWORD *)(v12 + a1 + 22712) = v13;
        *(_QWORD *)(a1 + 8 * v14) = v13;
      }
      KeInitializeSpinLock((PKSPIN_LOCK)(a1 + 22824));
      KeInitializeSpinLock((PKSPIN_LOCK)(a1 + 22600));
      KeInitializeSpinLock((PKSPIN_LOCK)(a1 + 22616));
      *(_BYTE *)(a1 + 22632) = 0;
      *(_QWORD *)(a1 + 22624) = 1;
      Acl = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
      if ( Acl >= 0 )
      {
        v15 = RtlLengthRequiredSid(1u);
        v16 = (char *)ExAllocatePool2(64, v15, 1735290953);
        Sid = v16;
        if ( v16 )
        {
          *(_DWORD *)v16 = 257;
          *(_QWORD *)(v16 + 4) = 0x1000000;
          v19 = RtlLengthSid(v16) + 16;
          v20 = (struct _ACL *)ExAllocatePool2(64, v19, 1735290953);
          v22 = v20;
          if ( v20 )
          {
            Acl = RtlCreateAcl(v20, v19, 2u);
            if ( Acl >= 0 )
            {
              Acl = RtlAddAccessAllowedAceEx(v22, 2u, 3u, 0x2001Fu, Sid);
              if ( Acl >= 0 )
              {
                RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v22, 0);
                *((_QWORD *)&v25 + 1) = *(_QWORD *)(a1 + 32);
                *(_QWORD *)&v27 = SecurityDescriptor;
                LODWORD(v26) = 26;
                DWORD2(v27) = v19;
                Acl = NsiSetObjectSecurity(&v25);
                if ( !Acl )
                {
                  _InterlockedIncrement(&IpngpReferenceCount);
                  _InterlockedAdd((volatile signed __int32 *)(a1 + 19860), 0x80u);
                }
              }
            }
            ExFreePoolWithTag(v22, 0);
          }
          else
          {
            if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
              McTemplateK0z_EtwWriteTransfer(
                &MICROSOFT_TCPIP_PROVIDER_Context,
                TCPIP_MEMORY_FAILURES,
                v21,
                L"physical interface request ACL (IPNG)");
            Acl = -1073741670;
          }
          ExFreePoolWithTag(Sid, 0);
          if ( Acl >= 0 )
            return (unsigned int)Acl;
        }
        else
        {
          if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
            McTemplateK0z_EtwWriteTransfer(
              &MICROSOFT_TCPIP_PROVIDER_Context,
              TCPIP_MEMORY_FAILURES,
              v17,
              L"physical interface request SID (IPNG)");
          Acl = -1073741670;
        }
      }
      RtlCleanupTimerWheel(*(_QWORD *)(a1 + 22608));
      NetioShutdownWorkQueue(a1 + 22664);
    }
    else if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
    {
      McTemplateK0z_EtwWriteTransfer(
        &MICROSOFT_TCPIP_PROVIDER_Context,
        TCPIP_MEMORY_FAILURES,
        v6,
        L"physical interface request queue (IPNG)");
    }
    ExFreePoolWithTag(*(PVOID *)(a1 + 22608), 0);
    return (unsigned int)Acl;
  }
  if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
    McTemplateK0z_EtwWriteTransfer(
      &MICROSOFT_TCPIP_PROVIDER_Context,
      TCPIP_MEMORY_FAILURES,
      v3,
      L"physical interface request timer table (IPNG)");
  return 3221225626LL;
}

```

## disassembly

```asm
0x140190bc0  push    rbp
0x140190bc2  push    rbx
0x140190bc3  push    rsi
0x140190bc4  push    rdi
0x140190bc5  push    r12
0x140190bc7  push    r13
0x140190bc9  push    r14
0x140190bcb  push    r15
0x140190bcd  lea     rbp, [rsp-1Fh]
0x140190bd2  sub     rsp, 98h
0x140190bd9  xorps   xmm1, xmm1
0x140190bdc  xor     eax, eax
0x140190bde  xorps   xmm0, xmm0
0x140190be1  mov     [rbp+57h+var_80], rax
0x140190be5  mov     rdi, rcx
0x140190be8  mov     edx, 0F8h
0x140190bed  mov     r8d, 61545754h
0x140190bf3  lea     esi, [rax+40h]
0x140190bf6  mov     ecx, esi
0x140190bf8  movups  [rbp+57h+SecurityDescriptor], xmm0
0x140190bfc  movups  [rbp+57h+var_90], xmm0
0x140190c00  movups  [rbp+57h+var_78], xmm1
0x140190c04  movups  [rbp+57h+var_68], xmm1
0x140190c08  movups  [rbp+57h+var_58], xmm1
0x140190c0c  call    cs:__imp_ExAllocatePool2
0x140190c13  nop     dword ptr [rax+rax+00h]
0x140190c18  xor     r13d, r13d
0x140190c1b  mov     [rdi+5850h], rax
0x140190c22  test    rax, rax
0x140190c25  jnz     short loc_140190C54
0x140190c27  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, r13b
0x140190c2e  jge     short loc_140190C4A
0x140190c30  lea     r9, aPhysicalInterf; "physical interface request timer table "...
0x140190c37  lea     rdx, TCPIP_MEMORY_FAILURES
0x140190c3e  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140190c45  call    McTemplateK0z_EtwWriteTransfer
0x140190c4a  mov     eax, 0C000009Ah
0x140190c4f  jmp     loc_140190F81
0x140190c54  mov     r9, cs:IppDeviceObject
0x140190c5b  lea     r12, [rdi+5888h]
0x140190c62  mov     rcx, r12
0x140190c65  lea     rdx, IppPhysicalInterfaceRequestNotificationWorker
0x140190c6c  xor     r8d, r8d
0x140190c6f  call    cs:__imp_NetioInitializeWorkQueue
0x140190c76  nop     dword ptr [rax+rax+00h]
0x140190c7b  mov     ebx, eax
0x140190c7d  test    eax, eax
0x140190c7f  jns     short loc_140190CAD
0x140190c81  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, r13b
0x140190c88  jge     loc_140190F6A
0x140190c8e  lea     r9, aPhysicalInterf_2; "physical interface request queue (IPNG)"
0x140190c95  lea     rdx, TCPIP_MEMORY_FAILURES
0x140190c9c  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140190ca3  call    McTemplateK0z_EtwWriteTransfer
0x140190ca8  jmp     loc_140190F6A
0x140190cad  mov     rcx, [rdi+5850h]
0x140190cb4  mov     r14d, 1
0x140190cba  mov     r9d, r14d
0x140190cbd  mov     dword ptr [rsp+0D0h+Sid], r13d
0x140190cc2  mov     r8d, r14d
0x140190cc5  lea     edx, [r14+7]
0x140190cc9  call    cs:__imp_RtlInitializeTimerWheel
0x140190cd0  nop     dword ptr [rax+rax+00h]
0x140190cd5  mov     rcx, [rdi+5850h]
0x140190cdc  call    cs:__imp_RtlSuspendTimerWheel
0x140190ce3  nop     dword ptr [rax+rax+00h]
0x140190ce8  mov     r8, r13
0x140190ceb  mov     rdx, r8
0x140190cee  lea     rax, [r8+57Eh]
0x140190cf5  shl     rdx, 4
0x140190cf9  lea     rcx, [rdi+57D8h]
0x140190d00  add     rcx, rdx
0x140190d03  add     rax, rax
0x140190d06  add     r8, r14
0x140190d09  mov     [rdx+rdi+57D8h], rcx
0x140190d11  mov     [rdi+rax*8], rcx
0x140190d15  cmp     r8, 7
0x140190d19  jnz     short loc_140190CEB
0x140190d1b  mov     r8, r13
0x140190d1e  mov     rdx, r8
0x140190d21  lea     rax, [r8+58Ch]
0x140190d28  shl     rdx, 4
0x140190d2c  lea     rcx, [rdi+58B8h]
0x140190d33  add     rcx, rdx
0x140190d36  add     rax, rax
0x140190d39  add     r8, r14
0x140190d3c  mov     [rdx+rdi+58B8h], rcx
0x140190d44  mov     [rdi+rax*8], rcx
0x140190d48  cmp     r8, 7
0x140190d4c  jnz     short loc_140190D1E
0x140190d4e  lea     rcx, [rdi+5928h]; SpinLock
0x140190d55  call    cs:__imp_KeInitializeSpinLock
0x140190d5c  nop     dword ptr [rax+rax+00h]
0x140190d61  lea     rcx, [rdi+5848h]; SpinLock
0x140190d68  call    cs:__imp_KeInitializeSpinLock
0x140190d6f  nop     dword ptr [rax+rax+00h]
0x140190d74  lea     rcx, [rdi+5858h]; SpinLock
0x140190d7b  call    cs:__imp_KeInitializeSpinLock
0x140190d82  nop     dword ptr [rax+rax+00h]
0x140190d87  mov     edx, r14d; Revision
0x140190d8a  mov     [rdi+5868h], r13b
0x140190d91  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x140190d95  mov     [rdi+5860h], r14
0x140190d9c  call    cs:__imp_RtlCreateSecurityDescriptor
0x140190da3  nop     dword ptr [rax+rax+00h]
0x140190da8  mov     ebx, eax
0x140190daa  test    eax, eax
0x140190dac  js      loc_140190F48
0x140190db2  mov     ecx, r14d; SubAuthorityCount
0x140190db5  call    cs:__imp_RtlLengthRequiredSid
0x140190dbc  nop     dword ptr [rax+rax+00h]
0x140190dc1  mov     ebx, 676E7049h
0x140190dc6  mov     edx, eax
0x140190dc8  mov     r8d, ebx
0x140190dcb  mov     rcx, rsi
0x140190dce  call    cs:__imp_ExAllocatePool2
0x140190dd5  nop     dword ptr [rax+rax+00h]
0x140190dda  mov     rsi, rax
0x140190ddd  test    rax, rax
0x140190de0  jnz     short loc_140190E0F
0x140190de2  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, r13b
0x140190de9  jge     short loc_140190E05
0x140190deb  lea     r9, aPhysicalInterf_3; "physical interface request SID (IPNG)"
0x140190df2  lea     rdx, TCPIP_MEMORY_FAILURES
0x140190df9  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140190e00  call    McTemplateK0z_EtwWriteTransfer
0x140190e05  mov     ebx, 0C000009Ah
0x140190e0a  jmp     loc_140190F48
0x140190e0f  mov     rcx, rsi; Sid
0x140190e12  mov     dword ptr [rax], 101h
0x140190e18  mov     qword ptr [rax+4], 1000000h
0x140190e20  call    cs:__imp_RtlLengthSid
0x140190e27  nop     dword ptr [rax+rax+00h]
0x140190e2c  mov     r8d, ebx
0x140190e2f  mov     ecx, 40h ; '@'
0x140190e34  lea     r15d, [rax+10h]
0x140190e38  mov     edx, r15d
0x140190e3b  call    cs:__imp_ExAllocatePool2
0x140190e42  nop     dword ptr [rax+rax+00h]
0x140190e47  mov     r14, rax
0x140190e4a  test    rax, rax
0x140190e4d  jnz     short loc_140190E7C
0x140190e4f  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, r13b
0x140190e56  jge     short loc_140190E72
0x140190e58  lea     r9, aPhysicalInterf_1; "physical interface request ACL (IPNG)"
0x140190e5f  lea     rdx, TCPIP_MEMORY_FAILURES
0x140190e66  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140190e6d  call    McTemplateK0z_EtwWriteTransfer
0x140190e72  mov     ebx, 0C000009Ah
0x140190e77  jmp     loc_140190F33
0x140190e7c  mov     r8d, 2; AclRevision
0x140190e82  mov     edx, r15d; AclLength
0x140190e85  mov     rcx, r14; Acl
0x140190e88  call    cs:__imp_RtlCreateAcl
0x140190e8f  nop     dword ptr [rax+rax+00h]
0x140190e94  mov     ebx, eax
0x140190e96  test    eax, eax
0x140190e98  js      loc_140190F22
0x140190e9e  mov     edx, 2; AceRevision
0x140190ea3  mov     [rsp+0D0h+Sid], rsi; Sid
0x140190ea8  mov     r9d, 2001Fh; AccessMask
0x140190eae  mov     rcx, r14; Acl
0x140190eb1  lea     r8d, [rdx+1]; AceFlags
0x140190eb5  call    cs:__imp_RtlAddAccessAllowedAceEx
0x140190ebc  nop     dword ptr [rax+rax+00h]
0x140190ec1  mov     ebx, eax
0x140190ec3  test    eax, eax
0x140190ec5  js      short loc_140190F22
0x140190ec7  xor     r9d, r9d; DaclDefaulted
0x140190eca  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x140190ece  mov     r8, r14; Dacl
0x140190ed1  mov     dl, 1; DaclPresent
0x140190ed3  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140190eda  nop     dword ptr [rax+rax+00h]
0x140190edf  mov     rax, [rdi+20h]
0x140190ee3  lea     rcx, [rbp+57h+var_78]
0x140190ee7  mov     qword ptr [rbp+57h+var_78+8], rax
0x140190eeb  lea     rax, [rbp+57h+SecurityDescriptor]
0x140190eef  mov     qword ptr [rbp+57h+var_58], rax
0x140190ef3  mov     dword ptr [rbp+57h+var_68], 1Ah
0x140190efa  mov     dword ptr [rbp+57h+var_58+8], r15d
0x140190efe  call    cs:__imp_NsiSetObjectSecurity
0x140190f05  nop     dword ptr [rax+rax+00h]
0x140190f0a  mov     ebx, eax
0x140190f0c  test    eax, eax
0x140190f0e  jnz     short loc_140190F22
0x140190f10  lock inc cs:IpngpReferenceCount
0x140190f17  lock add dword ptr [rdi+4D94h], 80h
0x140190f22  xor     edx, edx; Tag
0x140190f24  mov     rcx, r14; P
0x140190f27  call    cs:__imp_ExFreePoolWithTag
0x140190f2e  nop     dword ptr [rax+rax+00h]
0x140190f33  xor     edx, edx; Tag
0x140190f35  mov     rcx, rsi; P
0x140190f38  call    cs:__imp_ExFreePoolWithTag
0x140190f3f  nop     dword ptr [rax+rax+00h]
0x140190f44  test    ebx, ebx
0x140190f46  jns     short loc_140190F7F
0x140190f48  mov     rcx, [rdi+5850h]
0x140190f4f  call    cs:__imp_RtlCleanupTimerWheel
0x140190f56  nop     dword ptr [rax+rax+00h]
0x140190f5b  mov     rcx, r12
0x140190f5e  call    cs:__imp_NetioShutdownWorkQueue
0x140190f65  nop     dword ptr [rax+rax+00h]
0x140190f6a  mov     rcx, [rdi+5850h]; P
0x140190f71  xor     edx, edx; Tag
0x140190f73  call    cs:__imp_ExFreePoolWithTag
0x140190f7a  nop     dword ptr [rax+rax+00h]
0x140190f7f  mov     eax, ebx
0x140190f81  add     rsp, 98h
0x140190f88  pop     r15
0x140190f8a  pop     r14
0x140190f8c  pop     r13
0x140190f8e  pop     r12
0x140190f90  pop     rdi
0x140190f91  pop     rsi
0x140190f92  pop     rbx
0x140190f93  pop     rbp
0x140190f94  retn
```
