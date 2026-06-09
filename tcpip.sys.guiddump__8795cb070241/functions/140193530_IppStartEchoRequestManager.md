# IppStartEchoRequestManager

- ea: `0x140193530`
- end: `0x1401938a0`
- name: `IppStartEchoRequestManager`
- size: `880`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x140014a08`
- `0x140193530`

## import_xrefs

- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1401937e0`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1401937e0`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1401937c2`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1401937c2`
- `ntoskrnl!RtlCreateAcl` at `0x140193795`
- `ntoskrnl!RtlCreateAcl` at `0x140193795`
- `ntoskrnl!RtlLengthSid` at `0x14019372d`
- `ntoskrnl!RtlLengthSid` at `0x14019372d`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1401936a9`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1401936a9`
- `ntoskrnl!KeInitializeSpinLock` at `0x14019366a`
- `ntoskrnl!KeInitializeSpinLock` at `0x14019367d`
- `ntoskrnl!KeInitializeSpinLock` at `0x14019366a`
- `ntoskrnl!KeInitializeSpinLock` at `0x14019367d`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1401936c2`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1401936c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140193831`
- `ntoskrnl!ExFreePoolWithTag` at `0x140193842`
- `ntoskrnl!ExFreePoolWithTag` at `0x14019387d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140193831`
- `ntoskrnl!ExFreePoolWithTag` at `0x140193842`
- `ntoskrnl!ExFreePoolWithTag` at `0x14019387d`
- `ntoskrnl!ExAllocatePool2` at `0x14019357c`
- `ntoskrnl!ExAllocatePool2` at `0x1401936db`
- `ntoskrnl!ExAllocatePool2` at `0x140193748`
- `ntoskrnl!ExAllocatePool2` at `0x14019357c`
- `ntoskrnl!ExAllocatePool2` at `0x1401936db`
- `ntoskrnl!ExAllocatePool2` at `0x140193748`
- `NETIO!NetioInitializeWorkQueue` at `0x1401935df`
- `NETIO!NetioInitializeWorkQueue` at `0x1401935df`
- `NETIO!NetioShutdownWorkQueue` at `0x140193868`
- `NETIO!NetioShutdownWorkQueue` at `0x140193868`
- `NETIO!RtlSuspendTimerWheel` at `0x140193624`
- `NETIO!RtlSuspendTimerWheel` at `0x140193624`
- `NETIO!RtlCleanupTimerWheel` at `0x140193859`
- `NETIO!RtlCleanupTimerWheel` at `0x140193859`
- `NETIO!RtlInitializeTimerWheel` at `0x140193611`
- `NETIO!RtlInitializeTimerWheel` at `0x140193611`
- `NETIO!NsiSetObjectSecurity` at `0x14019380b`
- `NETIO!NsiSetObjectSecurity` at `0x14019380b`

## string_xrefs

- `0x1401936f8`: `echo request SID (IPNG)`
- `0x140193765`: `echo request ACL (IPNG)`

## pseudocode

```c
__int64 __fastcall IppStartEchoRequestManager(__int64 a1)
{
  __int64 Pool2; // rax
  __int64 v3; // r8
  NTSTATUS Acl; // ebx
  __int64 i; // rdx
  __int64 v7; // rcx
  __int64 v8; // rax
  ULONG v9; // eax
  char *v10; // rax
  __int64 v11; // r8
  void *Sid; // rsi
  ULONG v13; // r15d
  struct _ACL *v14; // rax
  __int64 v15; // r8
  struct _ACL *v16; // r14
  _OWORD SecurityDescriptor[2]; // [rsp+30h] [rbp-49h] BYREF
  __int64 v18; // [rsp+50h] [rbp-29h]
  __int128 v19; // [rsp+58h] [rbp-21h] BYREF
  __int128 v20; // [rsp+68h] [rbp-11h]
  __int128 v21; // [rsp+78h] [rbp-1h]

  v18 = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v19 = 0;
  v20 = 0;
  v21 = 0;
  Pool2 = ExAllocatePool2(64, 248, 1632917332);
  *(_QWORD *)(a1 + 20056) = Pool2;
  if ( Pool2 )
  {
    Acl = NetioInitializeWorkQueue(a1 + 20112, IppNotifyEchoRequestChangeWorker, 0, IppDeviceObject);
    if ( Acl >= 0 )
    {
      RtlInitializeTimerWheel(*(_QWORD *)(a1 + 20056), 8, 1, 1, 0);
      RtlSuspendTimerWheel(*(_QWORD *)(a1 + 20056));
      for ( i = 0; i != 7; ++i )
      {
        v7 = 16 * i + a1 + 19936;
        *(_QWORD *)(16 * i + a1 + 19944) = v7;
        v8 = 2 * (i + 1246);
        *(_QWORD *)(a1 + 8 * v8) = v7;
      }
      KeInitializeSpinLock((PKSPIN_LOCK)(a1 + 20048));
      KeInitializeSpinLock((PKSPIN_LOCK)(a1 + 20064));
      *(_QWORD *)(a1 + 20076) = 0x10000;
      *(_BYTE *)(a1 + 20084) = 0;
      *(_DWORD *)(a1 + 20072) = 1;
      Acl = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
      if ( Acl >= 0 )
      {
        v9 = RtlLengthRequiredSid(1u);
        v10 = (char *)ExAllocatePool2(64, v9, 1735290953);
        Sid = v10;
        if ( v10 )
        {
          *(_DWORD *)v10 = 257;
          *(_QWORD *)(v10 + 4) = 0x1000000;
          v13 = RtlLengthSid(v10) + 16;
          v14 = (struct _ACL *)ExAllocatePool2(64, v13, 1735290953);
          v16 = v14;
          if ( v14 )
          {
            Acl = RtlCreateAcl(v14, v13, 2u);
            if ( Acl >= 0 )
            {
              Acl = RtlAddAccessAllowedAceEx(v16, 2u, 3u, 0x2001Fu, Sid);
              if ( Acl >= 0 )
              {
                RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v16, 0);
                *((_QWORD *)&v19 + 1) = *(_QWORD *)(a1 + 32);
                *(_QWORD *)&v21 = SecurityDescriptor;
                LODWORD(v20) = 4;
                DWORD2(v21) = v13;
                Acl = NsiSetObjectSecurity(&v19);
                if ( !Acl )
                {
                  _InterlockedIncrement(&IpngpReferenceCount);
                  _InterlockedAdd((volatile signed __int32 *)(a1 + 19860), 0x20u);
                }
              }
            }
            ExFreePoolWithTag(v16, 0);
          }
          else
          {
            if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
              McTemplateK0z_EtwWriteTransfer(
                &MICROSOFT_TCPIP_PROVIDER_Context,
                TCPIP_MEMORY_FAILURES,
                v15,
                L"echo request ACL (IPNG)");
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
              v11,
              L"echo request SID (IPNG)");
          Acl = -1073741670;
        }
      }
      RtlCleanupTimerWheel(*(_QWORD *)(a1 + 20056));
      NetioShutdownWorkQueue(a1 + 20112);
    }
    ExFreePoolWithTag(*(PVOID *)(a1 + 20056), 0);
    return (unsigned int)Acl;
  }
  if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
    McTemplateK0z_EtwWriteTransfer(
      &MICROSOFT_TCPIP_PROVIDER_Context,
      TCPIP_MEMORY_FAILURES,
      v3,
      L"echo request timer table (IPNG)");
  return 3221225626LL;
}

```

## disassembly

```asm
0x140193530  push    rbp
0x140193532  push    rbx
0x140193533  push    rsi
0x140193534  push    rdi
0x140193535  push    r12
0x140193537  push    r13
0x140193539  push    r14
0x14019353b  push    r15
0x14019353d  lea     rbp, [rsp-1Fh]
0x140193542  sub     rsp, 98h
0x140193549  xorps   xmm1, xmm1
0x14019354c  xor     eax, eax
0x14019354e  xorps   xmm0, xmm0
0x140193551  mov     [rbp+57h+var_80], rax
0x140193555  mov     rdi, rcx
0x140193558  mov     edx, 0F8h
0x14019355d  mov     r8d, 61545754h
0x140193563  lea     esi, [rax+40h]
0x140193566  mov     ecx, esi
0x140193568  movups  [rbp+57h+SecurityDescriptor], xmm0
0x14019356c  movups  [rbp+57h+var_90], xmm0
0x140193570  movups  [rbp+57h+var_78], xmm1
0x140193574  movups  [rbp+57h+var_68], xmm1
0x140193578  movups  [rbp+57h+var_58], xmm1
0x14019357c  call    cs:__imp_ExAllocatePool2
0x140193583  nop     dword ptr [rax+rax+00h]
0x140193588  xor     r13d, r13d
0x14019358b  mov     [rdi+4E58h], rax
0x140193592  test    rax, rax
0x140193595  jnz     short loc_1401935C4
0x140193597  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+3, r13b
0x14019359e  jge     short loc_1401935BA
0x1401935a0  lea     r9, aEchoRequestTim; "echo request timer table (IPNG)"
0x1401935a7  lea     rdx, TCPIP_MEMORY_FAILURES
0x1401935ae  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1401935b5  call    McTemplateK0z_EtwWriteTransfer
0x1401935ba  mov     eax, 0C000009Ah
0x1401935bf  jmp     loc_14019388B
0x1401935c4  mov     r9, cs:IppDeviceObject
0x1401935cb  lea     r12, [rdi+4E90h]
0x1401935d2  mov     rcx, r12
0x1401935d5  lea     rdx, IppNotifyEchoRequestChangeWorker
0x1401935dc  xor     r8d, r8d
0x1401935df  call    cs:__imp_NetioInitializeWorkQueue
0x1401935e6  nop     dword ptr [rax+rax+00h]
0x1401935eb  mov     ebx, eax
0x1401935ed  test    eax, eax
0x1401935ef  js      loc_140193874
0x1401935f5  mov     rcx, [rdi+4E58h]
0x1401935fc  mov     r14d, 1
0x140193602  mov     r9d, r14d
0x140193605  mov     dword ptr [rsp+0D0h+Sid], r13d
0x14019360a  mov     r8d, r14d
0x14019360d  lea     edx, [r14+7]
0x140193611  call    cs:__imp_RtlInitializeTimerWheel
0x140193618  nop     dword ptr [rax+rax+00h]
0x14019361d  mov     rcx, [rdi+4E58h]
0x140193624  call    cs:__imp_RtlSuspendTimerWheel
0x14019362b  nop     dword ptr [rax+rax+00h]
0x140193630  mov     rdx, r13
0x140193633  mov     rax, rdx
0x140193636  lea     rcx, [rdi+4DE0h]
0x14019363d  shl     rax, 4
0x140193641  add     rcx, rax
0x140193644  mov     [rax+rdi+4DE8h], rcx
0x14019364c  lea     rax, [rdx+4DEh]
0x140193653  add     rax, rax
0x140193656  add     rdx, r14
0x140193659  mov     [rdi+rax*8], rcx
0x14019365d  cmp     rdx, 7
0x140193661  jnz     short loc_140193633
0x140193663  lea     rcx, [rdi+4E50h]; SpinLock
0x14019366a  call    cs:__imp_KeInitializeSpinLock
0x140193671  nop     dword ptr [rax+rax+00h]
0x140193676  lea     rcx, [rdi+4E60h]; SpinLock
0x14019367d  call    cs:__imp_KeInitializeSpinLock
0x140193684  nop     dword ptr [rax+rax+00h]
0x140193689  mov     edx, r14d; Revision
0x14019368c  mov     qword ptr [rdi+4E6Ch], 10000h
0x140193697  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x14019369b  mov     [rdi+4E74h], r13b
0x1401936a2  mov     [rdi+4E68h], r14d
0x1401936a9  call    cs:__imp_RtlCreateSecurityDescriptor
0x1401936b0  nop     dword ptr [rax+rax+00h]
0x1401936b5  mov     ebx, eax
0x1401936b7  test    eax, eax
0x1401936b9  js      loc_140193852
0x1401936bf  mov     ecx, r14d; SubAuthorityCount
0x1401936c2  call    cs:__imp_RtlLengthRequiredSid
0x1401936c9  nop     dword ptr [rax+rax+00h]
0x1401936ce  mov     ebx, 676E7049h
0x1401936d3  mov     edx, eax
0x1401936d5  mov     r8d, ebx
0x1401936d8  mov     rcx, rsi
0x1401936db  call    cs:__imp_ExAllocatePool2
0x1401936e2  nop     dword ptr [rax+rax+00h]
0x1401936e7  mov     rsi, rax
0x1401936ea  test    rax, rax
0x1401936ed  jnz     short loc_14019371C
0x1401936ef  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+3, r13b
0x1401936f6  jge     short loc_140193712
0x1401936f8  lea     r9, aEchoRequestSid; "echo request SID (IPNG)"
0x1401936ff  lea     rdx, TCPIP_MEMORY_FAILURES
0x140193706  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14019370d  call    McTemplateK0z_EtwWriteTransfer
0x140193712  mov     ebx, 0C000009Ah
0x140193717  jmp     loc_140193852
0x14019371c  mov     rcx, rsi; Sid
0x14019371f  mov     dword ptr [rax], 101h
0x140193725  mov     qword ptr [rax+4], 1000000h
0x14019372d  call    cs:__imp_RtlLengthSid
0x140193734  nop     dword ptr [rax+rax+00h]
0x140193739  mov     r8d, ebx
0x14019373c  mov     ecx, 40h ; '@'
0x140193741  lea     r15d, [rax+10h]
0x140193745  mov     edx, r15d
0x140193748  call    cs:__imp_ExAllocatePool2
0x14019374f  nop     dword ptr [rax+rax+00h]
0x140193754  mov     r14, rax
0x140193757  test    rax, rax
0x14019375a  jnz     short loc_140193789
0x14019375c  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+3, r13b
0x140193763  jge     short loc_14019377F
0x140193765  lea     r9, aEchoRequestAcl; "echo request ACL (IPNG)"
0x14019376c  lea     rdx, TCPIP_MEMORY_FAILURES
0x140193773  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14019377a  call    McTemplateK0z_EtwWriteTransfer
0x14019377f  mov     ebx, 0C000009Ah
0x140193784  jmp     loc_14019383D
0x140193789  mov     r8d, 2; AclRevision
0x14019378f  mov     edx, r15d; AclLength
0x140193792  mov     rcx, r14; Acl
0x140193795  call    cs:__imp_RtlCreateAcl
0x14019379c  nop     dword ptr [rax+rax+00h]
0x1401937a1  mov     ebx, eax
0x1401937a3  test    eax, eax
0x1401937a5  js      loc_14019382C
0x1401937ab  mov     edx, 2; AceRevision
0x1401937b0  mov     [rsp+0D0h+Sid], rsi; Sid
0x1401937b5  mov     r9d, 2001Fh; AccessMask
0x1401937bb  mov     rcx, r14; Acl
0x1401937be  lea     r8d, [rdx+1]; AceFlags
0x1401937c2  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1401937c9  nop     dword ptr [rax+rax+00h]
0x1401937ce  mov     ebx, eax
0x1401937d0  test    eax, eax
0x1401937d2  js      short loc_14019382C
0x1401937d4  xor     r9d, r9d; DaclDefaulted
0x1401937d7  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1401937db  mov     r8, r14; Dacl
0x1401937de  mov     dl, 1; DaclPresent
0x1401937e0  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1401937e7  nop     dword ptr [rax+rax+00h]
0x1401937ec  mov     rax, [rdi+20h]
0x1401937f0  lea     rcx, [rbp+57h+var_78]
0x1401937f4  mov     qword ptr [rbp+57h+var_78+8], rax
0x1401937f8  lea     rax, [rbp+57h+SecurityDescriptor]
0x1401937fc  mov     qword ptr [rbp+57h+var_58], rax
0x140193800  mov     dword ptr [rbp+57h+var_68], 4
0x140193807  mov     dword ptr [rbp+57h+var_58+8], r15d
0x14019380b  call    cs:__imp_NsiSetObjectSecurity
0x140193812  nop     dword ptr [rax+rax+00h]
0x140193817  mov     ebx, eax
0x140193819  test    eax, eax
0x14019381b  jnz     short loc_14019382C
0x14019381d  lock inc cs:IpngpReferenceCount
0x140193824  lock add dword ptr [rdi+4D94h], 20h ; ' '
0x14019382c  xor     edx, edx; Tag
0x14019382e  mov     rcx, r14; P
0x140193831  call    cs:__imp_ExFreePoolWithTag
0x140193838  nop     dword ptr [rax+rax+00h]
0x14019383d  xor     edx, edx; Tag
0x14019383f  mov     rcx, rsi; P
0x140193842  call    cs:__imp_ExFreePoolWithTag
0x140193849  nop     dword ptr [rax+rax+00h]
0x14019384e  test    ebx, ebx
0x140193850  jns     short loc_140193889
0x140193852  mov     rcx, [rdi+4E58h]
0x140193859  call    cs:__imp_RtlCleanupTimerWheel
0x140193860  nop     dword ptr [rax+rax+00h]
0x140193865  mov     rcx, r12
0x140193868  call    cs:__imp_NetioShutdownWorkQueue
0x14019386f  nop     dword ptr [rax+rax+00h]
0x140193874  mov     rcx, [rdi+4E58h]; P
0x14019387b  xor     edx, edx; Tag
0x14019387d  call    cs:__imp_ExFreePoolWithTag
0x140193884  nop     dword ptr [rax+rax+00h]
0x140193889  mov     eax, ebx
0x14019388b  add     rsp, 98h
0x140193892  pop     r15
0x140193894  pop     r14
0x140193896  pop     r13
0x140193898  pop     r12
0x14019389a  pop     rdi
0x14019389b  pop     rsi
0x14019389c  pop     rbx
0x14019389d  pop     rbp
0x14019389e  retn
```
