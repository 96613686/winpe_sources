# IppStartPhysicalInterfaceRequestManager

- ea: `0x1401929a0`
- end: `0x140192d76`
- name: `IppStartPhysicalInterfaceRequestManager`
- size: `982`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x140014a08`
- `0x1401929a0`

## import_xrefs

- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140192cb3`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140192cb3`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140192c95`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140192c95`
- `ntoskrnl!RtlCreateAcl` at `0x140192c68`
- `ntoskrnl!RtlCreateAcl` at `0x140192c68`
- `ntoskrnl!RtlLengthSid` at `0x140192c00`
- `ntoskrnl!RtlLengthSid` at `0x140192c00`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140192b7c`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140192b7c`
- `ntoskrnl!KeInitializeSpinLock` at `0x140192b35`
- `ntoskrnl!KeInitializeSpinLock` at `0x140192b48`
- `ntoskrnl!KeInitializeSpinLock` at `0x140192b5b`
- `ntoskrnl!KeInitializeSpinLock` at `0x140192b35`
- `ntoskrnl!KeInitializeSpinLock` at `0x140192b48`
- `ntoskrnl!KeInitializeSpinLock` at `0x140192b5b`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140192b95`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140192b95`
- `ntoskrnl!ExFreePoolWithTag` at `0x140192d07`
- `ntoskrnl!ExFreePoolWithTag` at `0x140192d18`
- `ntoskrnl!ExFreePoolWithTag` at `0x140192d53`
- `ntoskrnl!ExFreePoolWithTag` at `0x140192d07`
- `ntoskrnl!ExFreePoolWithTag` at `0x140192d18`
- `ntoskrnl!ExFreePoolWithTag` at `0x140192d53`
- `ntoskrnl!ExAllocatePool2` at `0x1401929ec`
- `ntoskrnl!ExAllocatePool2` at `0x140192bae`
- `ntoskrnl!ExAllocatePool2` at `0x140192c1b`
- `ntoskrnl!ExAllocatePool2` at `0x1401929ec`
- `ntoskrnl!ExAllocatePool2` at `0x140192bae`
- `ntoskrnl!ExAllocatePool2` at `0x140192c1b`
- `NETIO!NetioInitializeWorkQueue` at `0x140192a4f`
- `NETIO!NetioInitializeWorkQueue` at `0x140192a4f`
- `NETIO!NetioShutdownWorkQueue` at `0x140192d3e`
- `NETIO!NetioShutdownWorkQueue` at `0x140192d3e`
- `NETIO!RtlSuspendTimerWheel` at `0x140192abc`
- `NETIO!RtlSuspendTimerWheel` at `0x140192abc`
- `NETIO!RtlCleanupTimerWheel` at `0x140192d2f`
- `NETIO!RtlCleanupTimerWheel` at `0x140192d2f`
- `NETIO!RtlInitializeTimerWheel` at `0x140192aa9`
- `NETIO!RtlInitializeTimerWheel` at `0x140192aa9`
- `NETIO!NsiSetObjectSecurity` at `0x140192cde`
- `NETIO!NsiSetObjectSecurity` at `0x140192cde`

## string_xrefs

- `0x140192bcb`: `physical interface request SID (IPNG)`
- `0x140192c38`: `physical interface request ACL (IPNG)`

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
            if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
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
          if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
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
    else if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
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
  if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
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
0x1401929a0  push    rbp
0x1401929a2  push    rbx
0x1401929a3  push    rsi
0x1401929a4  push    rdi
0x1401929a5  push    r12
0x1401929a7  push    r13
0x1401929a9  push    r14
0x1401929ab  push    r15
0x1401929ad  lea     rbp, [rsp-1Fh]
0x1401929b2  sub     rsp, 98h
0x1401929b9  xorps   xmm1, xmm1
0x1401929bc  xor     eax, eax
0x1401929be  xorps   xmm0, xmm0
0x1401929c1  mov     [rbp+57h+var_80], rax
0x1401929c5  mov     rdi, rcx
0x1401929c8  mov     edx, 0F8h
0x1401929cd  mov     r8d, 61545754h
0x1401929d3  lea     esi, [rax+40h]
0x1401929d6  mov     ecx, esi
0x1401929d8  movups  [rbp+57h+SecurityDescriptor], xmm0
0x1401929dc  movups  [rbp+57h+var_90], xmm0
0x1401929e0  movups  [rbp+57h+var_78], xmm1
0x1401929e4  movups  [rbp+57h+var_68], xmm1
0x1401929e8  movups  [rbp+57h+var_58], xmm1
0x1401929ec  call    cs:__imp_ExAllocatePool2
0x1401929f3  nop     dword ptr [rax+rax+00h]
0x1401929f8  xor     r13d, r13d
0x1401929fb  mov     [rdi+5850h], rax
0x140192a02  test    rax, rax
0x140192a05  jnz     short loc_140192A34
0x140192a07  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+3, r13b
0x140192a0e  jge     short loc_140192A2A
0x140192a10  lea     r9, aPhysicalInterf; "physical interface request timer table "...
0x140192a17  lea     rdx, TCPIP_MEMORY_FAILURES
0x140192a1e  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140192a25  call    McTemplateK0z_EtwWriteTransfer
0x140192a2a  mov     eax, 0C000009Ah
0x140192a2f  jmp     loc_140192D61
0x140192a34  mov     r9, cs:IppDeviceObject
0x140192a3b  lea     r12, [rdi+5888h]
0x140192a42  mov     rcx, r12
0x140192a45  lea     rdx, IppPhysicalInterfaceRequestNotificationWorker
0x140192a4c  xor     r8d, r8d
0x140192a4f  call    cs:__imp_NetioInitializeWorkQueue
0x140192a56  nop     dword ptr [rax+rax+00h]
0x140192a5b  mov     ebx, eax
0x140192a5d  test    eax, eax
0x140192a5f  jns     short loc_140192A8D
0x140192a61  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+3, r13b
0x140192a68  jge     loc_140192D4A
0x140192a6e  lea     r9, aPhysicalInterf_2; "physical interface request queue (IPNG)"
0x140192a75  lea     rdx, TCPIP_MEMORY_FAILURES
0x140192a7c  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140192a83  call    McTemplateK0z_EtwWriteTransfer
0x140192a88  jmp     loc_140192D4A
0x140192a8d  mov     rcx, [rdi+5850h]
0x140192a94  mov     r14d, 1
0x140192a9a  mov     r9d, r14d
0x140192a9d  mov     dword ptr [rsp+0D0h+Sid], r13d
0x140192aa2  mov     r8d, r14d
0x140192aa5  lea     edx, [r14+7]
0x140192aa9  call    cs:__imp_RtlInitializeTimerWheel
0x140192ab0  nop     dword ptr [rax+rax+00h]
0x140192ab5  mov     rcx, [rdi+5850h]
0x140192abc  call    cs:__imp_RtlSuspendTimerWheel
0x140192ac3  nop     dword ptr [rax+rax+00h]
0x140192ac8  mov     r8, r13
0x140192acb  mov     rdx, r8
0x140192ace  lea     rax, [r8+57Eh]
0x140192ad5  shl     rdx, 4
0x140192ad9  lea     rcx, [rdi+57D8h]
0x140192ae0  add     rcx, rdx
0x140192ae3  add     rax, rax
0x140192ae6  add     r8, r14
0x140192ae9  mov     [rdx+rdi+57D8h], rcx
0x140192af1  mov     [rdi+rax*8], rcx
0x140192af5  cmp     r8, 7
0x140192af9  jnz     short loc_140192ACB
0x140192afb  mov     r8, r13
0x140192afe  mov     rdx, r8
0x140192b01  lea     rax, [r8+58Ch]
0x140192b08  shl     rdx, 4
0x140192b0c  lea     rcx, [rdi+58B8h]
0x140192b13  add     rcx, rdx
0x140192b16  add     rax, rax
0x140192b19  add     r8, r14
0x140192b1c  mov     [rdx+rdi+58B8h], rcx
0x140192b24  mov     [rdi+rax*8], rcx
0x140192b28  cmp     r8, 7
0x140192b2c  jnz     short loc_140192AFE
0x140192b2e  lea     rcx, [rdi+5928h]; SpinLock
0x140192b35  call    cs:__imp_KeInitializeSpinLock
0x140192b3c  nop     dword ptr [rax+rax+00h]
0x140192b41  lea     rcx, [rdi+5848h]; SpinLock
0x140192b48  call    cs:__imp_KeInitializeSpinLock
0x140192b4f  nop     dword ptr [rax+rax+00h]
0x140192b54  lea     rcx, [rdi+5858h]; SpinLock
0x140192b5b  call    cs:__imp_KeInitializeSpinLock
0x140192b62  nop     dword ptr [rax+rax+00h]
0x140192b67  mov     edx, r14d; Revision
0x140192b6a  mov     [rdi+5868h], r13b
0x140192b71  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x140192b75  mov     [rdi+5860h], r14
0x140192b7c  call    cs:__imp_RtlCreateSecurityDescriptor
0x140192b83  nop     dword ptr [rax+rax+00h]
0x140192b88  mov     ebx, eax
0x140192b8a  test    eax, eax
0x140192b8c  js      loc_140192D28
0x140192b92  mov     ecx, r14d; SubAuthorityCount
0x140192b95  call    cs:__imp_RtlLengthRequiredSid
0x140192b9c  nop     dword ptr [rax+rax+00h]
0x140192ba1  mov     ebx, 676E7049h
0x140192ba6  mov     edx, eax
0x140192ba8  mov     r8d, ebx
0x140192bab  mov     rcx, rsi
0x140192bae  call    cs:__imp_ExAllocatePool2
0x140192bb5  nop     dword ptr [rax+rax+00h]
0x140192bba  mov     rsi, rax
0x140192bbd  test    rax, rax
0x140192bc0  jnz     short loc_140192BEF
0x140192bc2  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+3, r13b
0x140192bc9  jge     short loc_140192BE5
0x140192bcb  lea     r9, aPhysicalInterf_3; "physical interface request SID (IPNG)"
0x140192bd2  lea     rdx, TCPIP_MEMORY_FAILURES
0x140192bd9  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140192be0  call    McTemplateK0z_EtwWriteTransfer
0x140192be5  mov     ebx, 0C000009Ah
0x140192bea  jmp     loc_140192D28
0x140192bef  mov     rcx, rsi; Sid
0x140192bf2  mov     dword ptr [rax], 101h
0x140192bf8  mov     qword ptr [rax+4], 1000000h
0x140192c00  call    cs:__imp_RtlLengthSid
0x140192c07  nop     dword ptr [rax+rax+00h]
0x140192c0c  mov     r8d, ebx
0x140192c0f  mov     ecx, 40h ; '@'
0x140192c14  lea     r15d, [rax+10h]
0x140192c18  mov     edx, r15d
0x140192c1b  call    cs:__imp_ExAllocatePool2
0x140192c22  nop     dword ptr [rax+rax+00h]
0x140192c27  mov     r14, rax
0x140192c2a  test    rax, rax
0x140192c2d  jnz     short loc_140192C5C
0x140192c2f  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+3, r13b
0x140192c36  jge     short loc_140192C52
0x140192c38  lea     r9, aPhysicalInterf_1; "physical interface request ACL (IPNG)"
0x140192c3f  lea     rdx, TCPIP_MEMORY_FAILURES
0x140192c46  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140192c4d  call    McTemplateK0z_EtwWriteTransfer
0x140192c52  mov     ebx, 0C000009Ah
0x140192c57  jmp     loc_140192D13
0x140192c5c  mov     r8d, 2; AclRevision
0x140192c62  mov     edx, r15d; AclLength
0x140192c65  mov     rcx, r14; Acl
0x140192c68  call    cs:__imp_RtlCreateAcl
0x140192c6f  nop     dword ptr [rax+rax+00h]
0x140192c74  mov     ebx, eax
0x140192c76  test    eax, eax
0x140192c78  js      loc_140192D02
0x140192c7e  mov     edx, 2; AceRevision
0x140192c83  mov     [rsp+0D0h+Sid], rsi; Sid
0x140192c88  mov     r9d, 2001Fh; AccessMask
0x140192c8e  mov     rcx, r14; Acl
0x140192c91  lea     r8d, [rdx+1]; AceFlags
0x140192c95  call    cs:__imp_RtlAddAccessAllowedAceEx
0x140192c9c  nop     dword ptr [rax+rax+00h]
0x140192ca1  mov     ebx, eax
0x140192ca3  test    eax, eax
0x140192ca5  js      short loc_140192D02
0x140192ca7  xor     r9d, r9d; DaclDefaulted
0x140192caa  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x140192cae  mov     r8, r14; Dacl
0x140192cb1  mov     dl, 1; DaclPresent
0x140192cb3  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140192cba  nop     dword ptr [rax+rax+00h]
0x140192cbf  mov     rax, [rdi+20h]
0x140192cc3  lea     rcx, [rbp+57h+var_78]
0x140192cc7  mov     qword ptr [rbp+57h+var_78+8], rax
0x140192ccb  lea     rax, [rbp+57h+SecurityDescriptor]
0x140192ccf  mov     qword ptr [rbp+57h+var_58], rax
0x140192cd3  mov     dword ptr [rbp+57h+var_68], 1Ah
0x140192cda  mov     dword ptr [rbp+57h+var_58+8], r15d
0x140192cde  call    cs:__imp_NsiSetObjectSecurity
0x140192ce5  nop     dword ptr [rax+rax+00h]
0x140192cea  mov     ebx, eax
0x140192cec  test    eax, eax
0x140192cee  jnz     short loc_140192D02
0x140192cf0  lock inc cs:IpngpReferenceCount
0x140192cf7  lock add dword ptr [rdi+4D94h], 80h
0x140192d02  xor     edx, edx; Tag
0x140192d04  mov     rcx, r14; P
0x140192d07  call    cs:__imp_ExFreePoolWithTag
0x140192d0e  nop     dword ptr [rax+rax+00h]
0x140192d13  xor     edx, edx; Tag
0x140192d15  mov     rcx, rsi; P
0x140192d18  call    cs:__imp_ExFreePoolWithTag
0x140192d1f  nop     dword ptr [rax+rax+00h]
0x140192d24  test    ebx, ebx
0x140192d26  jns     short loc_140192D5F
0x140192d28  mov     rcx, [rdi+5850h]
0x140192d2f  call    cs:__imp_RtlCleanupTimerWheel
0x140192d36  nop     dword ptr [rax+rax+00h]
0x140192d3b  mov     rcx, r12
0x140192d3e  call    cs:__imp_NetioShutdownWorkQueue
0x140192d45  nop     dword ptr [rax+rax+00h]
0x140192d4a  mov     rcx, [rdi+5850h]; P
0x140192d51  xor     edx, edx; Tag
0x140192d53  call    cs:__imp_ExFreePoolWithTag
0x140192d5a  nop     dword ptr [rax+rax+00h]
0x140192d5f  mov     eax, ebx
0x140192d61  add     rsp, 98h
0x140192d68  pop     r15
0x140192d6a  pop     r14
0x140192d6c  pop     r13
0x140192d6e  pop     r12
0x140192d70  pop     rdi
0x140192d71  pop     rsi
0x140192d72  pop     rbx
0x140192d73  pop     rbp
0x140192d74  retn
```
