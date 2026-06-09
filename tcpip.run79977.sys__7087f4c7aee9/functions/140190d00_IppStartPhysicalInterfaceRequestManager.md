# IppStartPhysicalInterfaceRequestManager

- ea: `0x140190d00`
- end: `0x1401910d6`
- name: `IppStartPhysicalInterfaceRequestManager`
- size: `982`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x140054138`
- `0x140190d00`

## import_xrefs

- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140191013`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140191013`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140190ff5`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140190ff5`
- `ntoskrnl!RtlCreateAcl` at `0x140190fc8`
- `ntoskrnl!RtlCreateAcl` at `0x140190fc8`
- `ntoskrnl!RtlLengthSid` at `0x140190f60`
- `ntoskrnl!RtlLengthSid` at `0x140190f60`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140190edc`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140190edc`
- `ntoskrnl!KeInitializeSpinLock` at `0x140190e95`
- `ntoskrnl!KeInitializeSpinLock` at `0x140190ea8`
- `ntoskrnl!KeInitializeSpinLock` at `0x140190ebb`
- `ntoskrnl!KeInitializeSpinLock` at `0x140190e95`
- `ntoskrnl!KeInitializeSpinLock` at `0x140190ea8`
- `ntoskrnl!KeInitializeSpinLock` at `0x140190ebb`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140190ef5`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140190ef5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140191067`
- `ntoskrnl!ExFreePoolWithTag` at `0x140191078`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401910b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140191067`
- `ntoskrnl!ExFreePoolWithTag` at `0x140191078`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401910b3`
- `ntoskrnl!ExAllocatePool2` at `0x140190d4c`
- `ntoskrnl!ExAllocatePool2` at `0x140190f0e`
- `ntoskrnl!ExAllocatePool2` at `0x140190f7b`
- `ntoskrnl!ExAllocatePool2` at `0x140190d4c`
- `ntoskrnl!ExAllocatePool2` at `0x140190f0e`
- `ntoskrnl!ExAllocatePool2` at `0x140190f7b`
- `NETIO!NetioInitializeWorkQueue` at `0x140190daf`
- `NETIO!NetioInitializeWorkQueue` at `0x140190daf`
- `NETIO!NetioShutdownWorkQueue` at `0x14019109e`
- `NETIO!NetioShutdownWorkQueue` at `0x14019109e`
- `NETIO!RtlSuspendTimerWheel` at `0x140190e1c`
- `NETIO!RtlSuspendTimerWheel` at `0x140190e1c`
- `NETIO!RtlCleanupTimerWheel` at `0x14019108f`
- `NETIO!RtlCleanupTimerWheel` at `0x14019108f`
- `NETIO!RtlInitializeTimerWheel` at `0x140190e09`
- `NETIO!RtlInitializeTimerWheel` at `0x140190e09`
- `NETIO!NsiSetObjectSecurity` at `0x14019103e`
- `NETIO!NsiSetObjectSecurity` at `0x14019103e`

## string_xrefs

- `0x140190f98`: `physical interface request ACL (IPNG)`
- `0x140190f2b`: `physical interface request SID (IPNG)`

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
                &TCPIP_MEMORY_FAILURES,
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
              &TCPIP_MEMORY_FAILURES,
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
        &TCPIP_MEMORY_FAILURES,
        v6,
        L"physical interface request queue (IPNG)");
    }
    ExFreePoolWithTag(*(PVOID *)(a1 + 22608), 0);
    return (unsigned int)Acl;
  }
  if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
    McTemplateK0z_EtwWriteTransfer(
      &MICROSOFT_TCPIP_PROVIDER_Context,
      &TCPIP_MEMORY_FAILURES,
      v3,
      L"physical interface request timer table (IPNG)");
  return 3221225626LL;
}

```

## disassembly

```asm
0x140190d00  push    rbp
0x140190d02  push    rbx
0x140190d03  push    rsi
0x140190d04  push    rdi
0x140190d05  push    r12
0x140190d07  push    r13
0x140190d09  push    r14
0x140190d0b  push    r15
0x140190d0d  lea     rbp, [rsp-1Fh]
0x140190d12  sub     rsp, 98h
0x140190d19  xorps   xmm1, xmm1
0x140190d1c  xor     eax, eax
0x140190d1e  xorps   xmm0, xmm0
0x140190d21  mov     [rbp+57h+var_80], rax
0x140190d25  mov     rdi, rcx
0x140190d28  mov     edx, 0F8h
0x140190d2d  mov     r8d, 61545754h
0x140190d33  lea     esi, [rax+40h]
0x140190d36  mov     ecx, esi
0x140190d38  movups  [rbp+57h+SecurityDescriptor], xmm0
0x140190d3c  movups  [rbp+57h+var_90], xmm0
0x140190d40  movups  [rbp+57h+var_78], xmm1
0x140190d44  movups  [rbp+57h+var_68], xmm1
0x140190d48  movups  [rbp+57h+var_58], xmm1
0x140190d4c  call    cs:__imp_ExAllocatePool2
0x140190d53  nop     dword ptr [rax+rax+00h]
0x140190d58  xor     r13d, r13d
0x140190d5b  mov     [rdi+5850h], rax
0x140190d62  test    rax, rax
0x140190d65  jnz     short loc_140190D94
0x140190d67  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, r13b
0x140190d6e  jge     short loc_140190D8A
0x140190d70  lea     r9, aPhysicalInterf; "physical interface request timer table "...
0x140190d77  lea     rdx, TCPIP_MEMORY_FAILURES
0x140190d7e  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140190d85  call    McTemplateK0z_EtwWriteTransfer
0x140190d8a  mov     eax, 0C000009Ah
0x140190d8f  jmp     loc_1401910C1
0x140190d94  mov     r9, cs:IppDeviceObject
0x140190d9b  lea     r12, [rdi+5888h]
0x140190da2  mov     rcx, r12
0x140190da5  lea     rdx, IppPhysicalInterfaceRequestNotificationWorker
0x140190dac  xor     r8d, r8d
0x140190daf  call    cs:__imp_NetioInitializeWorkQueue
0x140190db6  nop     dword ptr [rax+rax+00h]
0x140190dbb  mov     ebx, eax
0x140190dbd  test    eax, eax
0x140190dbf  jns     short loc_140190DED
0x140190dc1  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, r13b
0x140190dc8  jge     loc_1401910AA
0x140190dce  lea     r9, aPhysicalInterf_2; "physical interface request queue (IPNG)"
0x140190dd5  lea     rdx, TCPIP_MEMORY_FAILURES
0x140190ddc  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140190de3  call    McTemplateK0z_EtwWriteTransfer
0x140190de8  jmp     loc_1401910AA
0x140190ded  mov     rcx, [rdi+5850h]
0x140190df4  mov     r14d, 1
0x140190dfa  mov     r9d, r14d
0x140190dfd  mov     dword ptr [rsp+0D0h+Sid], r13d
0x140190e02  mov     r8d, r14d
0x140190e05  lea     edx, [r14+7]
0x140190e09  call    cs:__imp_RtlInitializeTimerWheel
0x140190e10  nop     dword ptr [rax+rax+00h]
0x140190e15  mov     rcx, [rdi+5850h]
0x140190e1c  call    cs:__imp_RtlSuspendTimerWheel
0x140190e23  nop     dword ptr [rax+rax+00h]
0x140190e28  mov     r8, r13
0x140190e2b  mov     rdx, r8
0x140190e2e  lea     rax, [r8+57Eh]
0x140190e35  shl     rdx, 4
0x140190e39  lea     rcx, [rdi+57D8h]
0x140190e40  add     rcx, rdx
0x140190e43  add     rax, rax
0x140190e46  add     r8, r14
0x140190e49  mov     [rdx+rdi+57D8h], rcx
0x140190e51  mov     [rdi+rax*8], rcx
0x140190e55  cmp     r8, 7
0x140190e59  jnz     short loc_140190E2B
0x140190e5b  mov     r8, r13
0x140190e5e  mov     rdx, r8
0x140190e61  lea     rax, [r8+58Ch]
0x140190e68  shl     rdx, 4
0x140190e6c  lea     rcx, [rdi+58B8h]
0x140190e73  add     rcx, rdx
0x140190e76  add     rax, rax
0x140190e79  add     r8, r14
0x140190e7c  mov     [rdx+rdi+58B8h], rcx
0x140190e84  mov     [rdi+rax*8], rcx
0x140190e88  cmp     r8, 7
0x140190e8c  jnz     short loc_140190E5E
0x140190e8e  lea     rcx, [rdi+5928h]; SpinLock
0x140190e95  call    cs:__imp_KeInitializeSpinLock
0x140190e9c  nop     dword ptr [rax+rax+00h]
0x140190ea1  lea     rcx, [rdi+5848h]; SpinLock
0x140190ea8  call    cs:__imp_KeInitializeSpinLock
0x140190eaf  nop     dword ptr [rax+rax+00h]
0x140190eb4  lea     rcx, [rdi+5858h]; SpinLock
0x140190ebb  call    cs:__imp_KeInitializeSpinLock
0x140190ec2  nop     dword ptr [rax+rax+00h]
0x140190ec7  mov     edx, r14d; Revision
0x140190eca  mov     [rdi+5868h], r13b
0x140190ed1  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x140190ed5  mov     [rdi+5860h], r14
0x140190edc  call    cs:__imp_RtlCreateSecurityDescriptor
0x140190ee3  nop     dword ptr [rax+rax+00h]
0x140190ee8  mov     ebx, eax
0x140190eea  test    eax, eax
0x140190eec  js      loc_140191088
0x140190ef2  mov     ecx, r14d; SubAuthorityCount
0x140190ef5  call    cs:__imp_RtlLengthRequiredSid
0x140190efc  nop     dword ptr [rax+rax+00h]
0x140190f01  mov     ebx, 676E7049h
0x140190f06  mov     edx, eax
0x140190f08  mov     r8d, ebx
0x140190f0b  mov     rcx, rsi
0x140190f0e  call    cs:__imp_ExAllocatePool2
0x140190f15  nop     dword ptr [rax+rax+00h]
0x140190f1a  mov     rsi, rax
0x140190f1d  test    rax, rax
0x140190f20  jnz     short loc_140190F4F
0x140190f22  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, r13b
0x140190f29  jge     short loc_140190F45
0x140190f2b  lea     r9, aPhysicalInterf_3; "physical interface request SID (IPNG)"
0x140190f32  lea     rdx, TCPIP_MEMORY_FAILURES
0x140190f39  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140190f40  call    McTemplateK0z_EtwWriteTransfer
0x140190f45  mov     ebx, 0C000009Ah
0x140190f4a  jmp     loc_140191088
0x140190f4f  mov     rcx, rsi; Sid
0x140190f52  mov     dword ptr [rax], 101h
0x140190f58  mov     qword ptr [rax+4], 1000000h
0x140190f60  call    cs:__imp_RtlLengthSid
0x140190f67  nop     dword ptr [rax+rax+00h]
0x140190f6c  mov     r8d, ebx
0x140190f6f  mov     ecx, 40h ; '@'
0x140190f74  lea     r15d, [rax+10h]
0x140190f78  mov     edx, r15d
0x140190f7b  call    cs:__imp_ExAllocatePool2
0x140190f82  nop     dword ptr [rax+rax+00h]
0x140190f87  mov     r14, rax
0x140190f8a  test    rax, rax
0x140190f8d  jnz     short loc_140190FBC
0x140190f8f  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, r13b
0x140190f96  jge     short loc_140190FB2
0x140190f98  lea     r9, aPhysicalInterf_1; "physical interface request ACL (IPNG)"
0x140190f9f  lea     rdx, TCPIP_MEMORY_FAILURES
0x140190fa6  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140190fad  call    McTemplateK0z_EtwWriteTransfer
0x140190fb2  mov     ebx, 0C000009Ah
0x140190fb7  jmp     loc_140191073
0x140190fbc  mov     r8d, 2; AclRevision
0x140190fc2  mov     edx, r15d; AclLength
0x140190fc5  mov     rcx, r14; Acl
0x140190fc8  call    cs:__imp_RtlCreateAcl
0x140190fcf  nop     dword ptr [rax+rax+00h]
0x140190fd4  mov     ebx, eax
0x140190fd6  test    eax, eax
0x140190fd8  js      loc_140191062
0x140190fde  mov     edx, 2; AceRevision
0x140190fe3  mov     [rsp+0D0h+Sid], rsi; Sid
0x140190fe8  mov     r9d, 2001Fh; AccessMask
0x140190fee  mov     rcx, r14; Acl
0x140190ff1  lea     r8d, [rdx+1]; AceFlags
0x140190ff5  call    cs:__imp_RtlAddAccessAllowedAceEx
0x140190ffc  nop     dword ptr [rax+rax+00h]
0x140191001  mov     ebx, eax
0x140191003  test    eax, eax
0x140191005  js      short loc_140191062
0x140191007  xor     r9d, r9d; DaclDefaulted
0x14019100a  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x14019100e  mov     r8, r14; Dacl
0x140191011  mov     dl, 1; DaclPresent
0x140191013  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14019101a  nop     dword ptr [rax+rax+00h]
0x14019101f  mov     rax, [rdi+20h]
0x140191023  lea     rcx, [rbp+57h+var_78]
0x140191027  mov     qword ptr [rbp+57h+var_78+8], rax
0x14019102b  lea     rax, [rbp+57h+SecurityDescriptor]
0x14019102f  mov     qword ptr [rbp+57h+var_58], rax
0x140191033  mov     dword ptr [rbp+57h+var_68], 1Ah
0x14019103a  mov     dword ptr [rbp+57h+var_58+8], r15d
0x14019103e  call    cs:__imp_NsiSetObjectSecurity
0x140191045  nop     dword ptr [rax+rax+00h]
0x14019104a  mov     ebx, eax
0x14019104c  test    eax, eax
0x14019104e  jnz     short loc_140191062
0x140191050  lock inc cs:IpngpReferenceCount
0x140191057  lock add dword ptr [rdi+4D94h], 80h
0x140191062  xor     edx, edx; Tag
0x140191064  mov     rcx, r14; P
0x140191067  call    cs:__imp_ExFreePoolWithTag
0x14019106e  nop     dword ptr [rax+rax+00h]
0x140191073  xor     edx, edx; Tag
0x140191075  mov     rcx, rsi; P
0x140191078  call    cs:__imp_ExFreePoolWithTag
0x14019107f  nop     dword ptr [rax+rax+00h]
0x140191084  test    ebx, ebx
0x140191086  jns     short loc_1401910BF
0x140191088  mov     rcx, [rdi+5850h]
0x14019108f  call    cs:__imp_RtlCleanupTimerWheel
0x140191096  nop     dword ptr [rax+rax+00h]
0x14019109b  mov     rcx, r12
0x14019109e  call    cs:__imp_NetioShutdownWorkQueue
0x1401910a5  nop     dword ptr [rax+rax+00h]
0x1401910aa  mov     rcx, [rdi+5850h]; P
0x1401910b1  xor     edx, edx; Tag
0x1401910b3  call    cs:__imp_ExFreePoolWithTag
0x1401910ba  nop     dword ptr [rax+rax+00h]
0x1401910bf  mov     eax, ebx
0x1401910c1  add     rsp, 98h
0x1401910c8  pop     r15
0x1401910ca  pop     r14
0x1401910cc  pop     r13
0x1401910ce  pop     r12
0x1401910d0  pop     rdi
0x1401910d1  pop     rsi
0x1401910d2  pop     rbx
0x1401910d3  pop     rbp
0x1401910d4  retn
```
