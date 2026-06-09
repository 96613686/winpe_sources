# IppStartEchoRequestManager

- ea: `0x140191750`
- end: `0x140191ac0`
- name: `IppStartEchoRequestManager`
- size: `880`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x140053e98`
- `0x140191750`

## import_xrefs

- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140191a00`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140191a00`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1401919e2`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1401919e2`
- `ntoskrnl!RtlCreateAcl` at `0x1401919b5`
- `ntoskrnl!RtlCreateAcl` at `0x1401919b5`
- `ntoskrnl!RtlLengthSid` at `0x14019194d`
- `ntoskrnl!RtlLengthSid` at `0x14019194d`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1401918c9`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1401918c9`
- `ntoskrnl!KeInitializeSpinLock` at `0x14019188a`
- `ntoskrnl!KeInitializeSpinLock` at `0x14019189d`
- `ntoskrnl!KeInitializeSpinLock` at `0x14019188a`
- `ntoskrnl!KeInitializeSpinLock` at `0x14019189d`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1401918e2`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1401918e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140191a51`
- `ntoskrnl!ExFreePoolWithTag` at `0x140191a62`
- `ntoskrnl!ExFreePoolWithTag` at `0x140191a9d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140191a51`
- `ntoskrnl!ExFreePoolWithTag` at `0x140191a62`
- `ntoskrnl!ExFreePoolWithTag` at `0x140191a9d`
- `ntoskrnl!ExAllocatePool2` at `0x14019179c`
- `ntoskrnl!ExAllocatePool2` at `0x1401918fb`
- `ntoskrnl!ExAllocatePool2` at `0x140191968`
- `ntoskrnl!ExAllocatePool2` at `0x14019179c`
- `ntoskrnl!ExAllocatePool2` at `0x1401918fb`
- `ntoskrnl!ExAllocatePool2` at `0x140191968`
- `NETIO!NetioInitializeWorkQueue` at `0x1401917ff`
- `NETIO!NetioInitializeWorkQueue` at `0x1401917ff`
- `NETIO!NetioShutdownWorkQueue` at `0x140191a88`
- `NETIO!NetioShutdownWorkQueue` at `0x140191a88`
- `NETIO!RtlSuspendTimerWheel` at `0x140191844`
- `NETIO!RtlSuspendTimerWheel` at `0x140191844`
- `NETIO!RtlCleanupTimerWheel` at `0x140191a79`
- `NETIO!RtlCleanupTimerWheel` at `0x140191a79`
- `NETIO!RtlInitializeTimerWheel` at `0x140191831`
- `NETIO!RtlInitializeTimerWheel` at `0x140191831`
- `NETIO!NsiSetObjectSecurity` at `0x140191a2b`
- `NETIO!NsiSetObjectSecurity` at `0x140191a2b`

## string_xrefs

- `0x140191918`: `echo request SID (IPNG)`
- `0x140191985`: `echo request ACL (IPNG)`

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
            if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
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
          if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
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
  if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
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
0x140191750  push    rbp
0x140191752  push    rbx
0x140191753  push    rsi
0x140191754  push    rdi
0x140191755  push    r12
0x140191757  push    r13
0x140191759  push    r14
0x14019175b  push    r15
0x14019175d  lea     rbp, [rsp-1Fh]
0x140191762  sub     rsp, 98h
0x140191769  xorps   xmm1, xmm1
0x14019176c  xor     eax, eax
0x14019176e  xorps   xmm0, xmm0
0x140191771  mov     [rbp+57h+var_80], rax
0x140191775  mov     rdi, rcx
0x140191778  mov     edx, 0F8h
0x14019177d  mov     r8d, 61545754h
0x140191783  lea     esi, [rax+40h]
0x140191786  mov     ecx, esi
0x140191788  movups  [rbp+57h+SecurityDescriptor], xmm0
0x14019178c  movups  [rbp+57h+var_90], xmm0
0x140191790  movups  [rbp+57h+var_78], xmm1
0x140191794  movups  [rbp+57h+var_68], xmm1
0x140191798  movups  [rbp+57h+var_58], xmm1
0x14019179c  call    cs:__imp_ExAllocatePool2
0x1401917a3  nop     dword ptr [rax+rax+00h]
0x1401917a8  xor     r13d, r13d
0x1401917ab  mov     [rdi+4E58h], rax
0x1401917b2  test    rax, rax
0x1401917b5  jnz     short loc_1401917E4
0x1401917b7  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, r13b
0x1401917be  jge     short loc_1401917DA
0x1401917c0  lea     r9, aEchoRequestTim; "echo request timer table (IPNG)"
0x1401917c7  lea     rdx, TCPIP_MEMORY_FAILURES
0x1401917ce  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1401917d5  call    McTemplateK0z_EtwWriteTransfer
0x1401917da  mov     eax, 0C000009Ah
0x1401917df  jmp     loc_140191AAB
0x1401917e4  mov     r9, cs:IppDeviceObject
0x1401917eb  lea     r12, [rdi+4E90h]
0x1401917f2  mov     rcx, r12
0x1401917f5  lea     rdx, IppNotifyEchoRequestChangeWorker
0x1401917fc  xor     r8d, r8d
0x1401917ff  call    cs:__imp_NetioInitializeWorkQueue
0x140191806  nop     dword ptr [rax+rax+00h]
0x14019180b  mov     ebx, eax
0x14019180d  test    eax, eax
0x14019180f  js      loc_140191A94
0x140191815  mov     rcx, [rdi+4E58h]
0x14019181c  mov     r14d, 1
0x140191822  mov     r9d, r14d
0x140191825  mov     dword ptr [rsp+0D0h+Sid], r13d
0x14019182a  mov     r8d, r14d
0x14019182d  lea     edx, [r14+7]
0x140191831  call    cs:__imp_RtlInitializeTimerWheel
0x140191838  nop     dword ptr [rax+rax+00h]
0x14019183d  mov     rcx, [rdi+4E58h]
0x140191844  call    cs:__imp_RtlSuspendTimerWheel
0x14019184b  nop     dword ptr [rax+rax+00h]
0x140191850  mov     rdx, r13
0x140191853  mov     rax, rdx
0x140191856  lea     rcx, [rdi+4DE0h]
0x14019185d  shl     rax, 4
0x140191861  add     rcx, rax
0x140191864  mov     [rax+rdi+4DE8h], rcx
0x14019186c  lea     rax, [rdx+4DEh]
0x140191873  add     rax, rax
0x140191876  add     rdx, r14
0x140191879  mov     [rdi+rax*8], rcx
0x14019187d  cmp     rdx, 7
0x140191881  jnz     short loc_140191853
0x140191883  lea     rcx, [rdi+4E50h]; SpinLock
0x14019188a  call    cs:__imp_KeInitializeSpinLock
0x140191891  nop     dword ptr [rax+rax+00h]
0x140191896  lea     rcx, [rdi+4E60h]; SpinLock
0x14019189d  call    cs:__imp_KeInitializeSpinLock
0x1401918a4  nop     dword ptr [rax+rax+00h]
0x1401918a9  mov     edx, r14d; Revision
0x1401918ac  mov     qword ptr [rdi+4E6Ch], 10000h
0x1401918b7  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1401918bb  mov     [rdi+4E74h], r13b
0x1401918c2  mov     [rdi+4E68h], r14d
0x1401918c9  call    cs:__imp_RtlCreateSecurityDescriptor
0x1401918d0  nop     dword ptr [rax+rax+00h]
0x1401918d5  mov     ebx, eax
0x1401918d7  test    eax, eax
0x1401918d9  js      loc_140191A72
0x1401918df  mov     ecx, r14d; SubAuthorityCount
0x1401918e2  call    cs:__imp_RtlLengthRequiredSid
0x1401918e9  nop     dword ptr [rax+rax+00h]
0x1401918ee  mov     ebx, 676E7049h
0x1401918f3  mov     edx, eax
0x1401918f5  mov     r8d, ebx
0x1401918f8  mov     rcx, rsi
0x1401918fb  call    cs:__imp_ExAllocatePool2
0x140191902  nop     dword ptr [rax+rax+00h]
0x140191907  mov     rsi, rax
0x14019190a  test    rax, rax
0x14019190d  jnz     short loc_14019193C
0x14019190f  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, r13b
0x140191916  jge     short loc_140191932
0x140191918  lea     r9, aEchoRequestSid; "echo request SID (IPNG)"
0x14019191f  lea     rdx, TCPIP_MEMORY_FAILURES
0x140191926  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14019192d  call    McTemplateK0z_EtwWriteTransfer
0x140191932  mov     ebx, 0C000009Ah
0x140191937  jmp     loc_140191A72
0x14019193c  mov     rcx, rsi; Sid
0x14019193f  mov     dword ptr [rax], 101h
0x140191945  mov     qword ptr [rax+4], 1000000h
0x14019194d  call    cs:__imp_RtlLengthSid
0x140191954  nop     dword ptr [rax+rax+00h]
0x140191959  mov     r8d, ebx
0x14019195c  mov     ecx, 40h ; '@'
0x140191961  lea     r15d, [rax+10h]
0x140191965  mov     edx, r15d
0x140191968  call    cs:__imp_ExAllocatePool2
0x14019196f  nop     dword ptr [rax+rax+00h]
0x140191974  mov     r14, rax
0x140191977  test    rax, rax
0x14019197a  jnz     short loc_1401919A9
0x14019197c  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, r13b
0x140191983  jge     short loc_14019199F
0x140191985  lea     r9, aEchoRequestAcl; "echo request ACL (IPNG)"
0x14019198c  lea     rdx, TCPIP_MEMORY_FAILURES
0x140191993  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14019199a  call    McTemplateK0z_EtwWriteTransfer
0x14019199f  mov     ebx, 0C000009Ah
0x1401919a4  jmp     loc_140191A5D
0x1401919a9  mov     r8d, 2; AclRevision
0x1401919af  mov     edx, r15d; AclLength
0x1401919b2  mov     rcx, r14; Acl
0x1401919b5  call    cs:__imp_RtlCreateAcl
0x1401919bc  nop     dword ptr [rax+rax+00h]
0x1401919c1  mov     ebx, eax
0x1401919c3  test    eax, eax
0x1401919c5  js      loc_140191A4C
0x1401919cb  mov     edx, 2; AceRevision
0x1401919d0  mov     [rsp+0D0h+Sid], rsi; Sid
0x1401919d5  mov     r9d, 2001Fh; AccessMask
0x1401919db  mov     rcx, r14; Acl
0x1401919de  lea     r8d, [rdx+1]; AceFlags
0x1401919e2  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1401919e9  nop     dword ptr [rax+rax+00h]
0x1401919ee  mov     ebx, eax
0x1401919f0  test    eax, eax
0x1401919f2  js      short loc_140191A4C
0x1401919f4  xor     r9d, r9d; DaclDefaulted
0x1401919f7  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1401919fb  mov     r8, r14; Dacl
0x1401919fe  mov     dl, 1; DaclPresent
0x140191a00  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140191a07  nop     dword ptr [rax+rax+00h]
0x140191a0c  mov     rax, [rdi+20h]
0x140191a10  lea     rcx, [rbp+57h+var_78]
0x140191a14  mov     qword ptr [rbp+57h+var_78+8], rax
0x140191a18  lea     rax, [rbp+57h+SecurityDescriptor]
0x140191a1c  mov     qword ptr [rbp+57h+var_58], rax
0x140191a20  mov     dword ptr [rbp+57h+var_68], 4
0x140191a27  mov     dword ptr [rbp+57h+var_58+8], r15d
0x140191a2b  call    cs:__imp_NsiSetObjectSecurity
0x140191a32  nop     dword ptr [rax+rax+00h]
0x140191a37  mov     ebx, eax
0x140191a39  test    eax, eax
0x140191a3b  jnz     short loc_140191A4C
0x140191a3d  lock inc cs:IpngpReferenceCount
0x140191a44  lock add dword ptr [rdi+4D94h], 20h ; ' '
0x140191a4c  xor     edx, edx; Tag
0x140191a4e  mov     rcx, r14; P
0x140191a51  call    cs:__imp_ExFreePoolWithTag
0x140191a58  nop     dword ptr [rax+rax+00h]
0x140191a5d  xor     edx, edx; Tag
0x140191a5f  mov     rcx, rsi; P
0x140191a62  call    cs:__imp_ExFreePoolWithTag
0x140191a69  nop     dword ptr [rax+rax+00h]
0x140191a6e  test    ebx, ebx
0x140191a70  jns     short loc_140191AA9
0x140191a72  mov     rcx, [rdi+4E58h]
0x140191a79  call    cs:__imp_RtlCleanupTimerWheel
0x140191a80  nop     dword ptr [rax+rax+00h]
0x140191a85  mov     rcx, r12
0x140191a88  call    cs:__imp_NetioShutdownWorkQueue
0x140191a8f  nop     dword ptr [rax+rax+00h]
0x140191a94  mov     rcx, [rdi+4E58h]; P
0x140191a9b  xor     edx, edx; Tag
0x140191a9d  call    cs:__imp_ExFreePoolWithTag
0x140191aa4  nop     dword ptr [rax+rax+00h]
0x140191aa9  mov     eax, ebx
0x140191aab  add     rsp, 98h
0x140191ab2  pop     r15
0x140191ab4  pop     r14
0x140191ab6  pop     r13
0x140191ab8  pop     r12
0x140191aba  pop     rdi
0x140191abb  pop     rsi
0x140191abc  pop     rbx
0x140191abd  pop     rbp
0x140191abe  retn
```
