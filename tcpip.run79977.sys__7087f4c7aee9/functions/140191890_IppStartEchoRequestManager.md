# IppStartEchoRequestManager

- ea: `0x140191890`
- end: `0x140191c00`
- name: `IppStartEchoRequestManager`
- size: `880`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x140054138`
- `0x140191890`

## import_xrefs

- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140191b40`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140191b40`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140191b22`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140191b22`
- `ntoskrnl!RtlCreateAcl` at `0x140191af5`
- `ntoskrnl!RtlCreateAcl` at `0x140191af5`
- `ntoskrnl!RtlLengthSid` at `0x140191a8d`
- `ntoskrnl!RtlLengthSid` at `0x140191a8d`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140191a09`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140191a09`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401919ca`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401919dd`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401919ca`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401919dd`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140191a22`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140191a22`
- `ntoskrnl!ExFreePoolWithTag` at `0x140191b91`
- `ntoskrnl!ExFreePoolWithTag` at `0x140191ba2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140191bdd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140191b91`
- `ntoskrnl!ExFreePoolWithTag` at `0x140191ba2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140191bdd`
- `ntoskrnl!ExAllocatePool2` at `0x1401918dc`
- `ntoskrnl!ExAllocatePool2` at `0x140191a3b`
- `ntoskrnl!ExAllocatePool2` at `0x140191aa8`
- `ntoskrnl!ExAllocatePool2` at `0x1401918dc`
- `ntoskrnl!ExAllocatePool2` at `0x140191a3b`
- `ntoskrnl!ExAllocatePool2` at `0x140191aa8`
- `NETIO!NetioInitializeWorkQueue` at `0x14019193f`
- `NETIO!NetioInitializeWorkQueue` at `0x14019193f`
- `NETIO!NetioShutdownWorkQueue` at `0x140191bc8`
- `NETIO!NetioShutdownWorkQueue` at `0x140191bc8`
- `NETIO!RtlSuspendTimerWheel` at `0x140191984`
- `NETIO!RtlSuspendTimerWheel` at `0x140191984`
- `NETIO!RtlCleanupTimerWheel` at `0x140191bb9`
- `NETIO!RtlCleanupTimerWheel` at `0x140191bb9`
- `NETIO!RtlInitializeTimerWheel` at `0x140191971`
- `NETIO!RtlInitializeTimerWheel` at `0x140191971`
- `NETIO!NsiSetObjectSecurity` at `0x140191b6b`
- `NETIO!NsiSetObjectSecurity` at `0x140191b6b`

## string_xrefs

- `0x140191ac5`: `echo request ACL (IPNG)`
- `0x140191a58`: `echo request SID (IPNG)`

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
                &TCPIP_MEMORY_FAILURES,
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
              &TCPIP_MEMORY_FAILURES,
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
      &TCPIP_MEMORY_FAILURES,
      v3,
      L"echo request timer table (IPNG)");
  return 3221225626LL;
}

```

## disassembly

```asm
0x140191890  push    rbp
0x140191892  push    rbx
0x140191893  push    rsi
0x140191894  push    rdi
0x140191895  push    r12
0x140191897  push    r13
0x140191899  push    r14
0x14019189b  push    r15
0x14019189d  lea     rbp, [rsp-1Fh]
0x1401918a2  sub     rsp, 98h
0x1401918a9  xorps   xmm1, xmm1
0x1401918ac  xor     eax, eax
0x1401918ae  xorps   xmm0, xmm0
0x1401918b1  mov     [rbp+57h+var_80], rax
0x1401918b5  mov     rdi, rcx
0x1401918b8  mov     edx, 0F8h
0x1401918bd  mov     r8d, 61545754h
0x1401918c3  lea     esi, [rax+40h]
0x1401918c6  mov     ecx, esi
0x1401918c8  movups  [rbp+57h+SecurityDescriptor], xmm0
0x1401918cc  movups  [rbp+57h+var_90], xmm0
0x1401918d0  movups  [rbp+57h+var_78], xmm1
0x1401918d4  movups  [rbp+57h+var_68], xmm1
0x1401918d8  movups  [rbp+57h+var_58], xmm1
0x1401918dc  call    cs:__imp_ExAllocatePool2
0x1401918e3  nop     dword ptr [rax+rax+00h]
0x1401918e8  xor     r13d, r13d
0x1401918eb  mov     [rdi+4E58h], rax
0x1401918f2  test    rax, rax
0x1401918f5  jnz     short loc_140191924
0x1401918f7  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, r13b
0x1401918fe  jge     short loc_14019191A
0x140191900  lea     r9, aEchoRequestTim; "echo request timer table (IPNG)"
0x140191907  lea     rdx, TCPIP_MEMORY_FAILURES
0x14019190e  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140191915  call    McTemplateK0z_EtwWriteTransfer
0x14019191a  mov     eax, 0C000009Ah
0x14019191f  jmp     loc_140191BEB
0x140191924  mov     r9, cs:IppDeviceObject
0x14019192b  lea     r12, [rdi+4E90h]
0x140191932  mov     rcx, r12
0x140191935  lea     rdx, IppNotifyEchoRequestChangeWorker
0x14019193c  xor     r8d, r8d
0x14019193f  call    cs:__imp_NetioInitializeWorkQueue
0x140191946  nop     dword ptr [rax+rax+00h]
0x14019194b  mov     ebx, eax
0x14019194d  test    eax, eax
0x14019194f  js      loc_140191BD4
0x140191955  mov     rcx, [rdi+4E58h]
0x14019195c  mov     r14d, 1
0x140191962  mov     r9d, r14d
0x140191965  mov     dword ptr [rsp+0D0h+Sid], r13d
0x14019196a  mov     r8d, r14d
0x14019196d  lea     edx, [r14+7]
0x140191971  call    cs:__imp_RtlInitializeTimerWheel
0x140191978  nop     dword ptr [rax+rax+00h]
0x14019197d  mov     rcx, [rdi+4E58h]
0x140191984  call    cs:__imp_RtlSuspendTimerWheel
0x14019198b  nop     dword ptr [rax+rax+00h]
0x140191990  mov     rdx, r13
0x140191993  mov     rax, rdx
0x140191996  lea     rcx, [rdi+4DE0h]
0x14019199d  shl     rax, 4
0x1401919a1  add     rcx, rax
0x1401919a4  mov     [rax+rdi+4DE8h], rcx
0x1401919ac  lea     rax, [rdx+4DEh]
0x1401919b3  add     rax, rax
0x1401919b6  add     rdx, r14
0x1401919b9  mov     [rdi+rax*8], rcx
0x1401919bd  cmp     rdx, 7
0x1401919c1  jnz     short loc_140191993
0x1401919c3  lea     rcx, [rdi+4E50h]; SpinLock
0x1401919ca  call    cs:__imp_KeInitializeSpinLock
0x1401919d1  nop     dword ptr [rax+rax+00h]
0x1401919d6  lea     rcx, [rdi+4E60h]; SpinLock
0x1401919dd  call    cs:__imp_KeInitializeSpinLock
0x1401919e4  nop     dword ptr [rax+rax+00h]
0x1401919e9  mov     edx, r14d; Revision
0x1401919ec  mov     qword ptr [rdi+4E6Ch], 10000h
0x1401919f7  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1401919fb  mov     [rdi+4E74h], r13b
0x140191a02  mov     [rdi+4E68h], r14d
0x140191a09  call    cs:__imp_RtlCreateSecurityDescriptor
0x140191a10  nop     dword ptr [rax+rax+00h]
0x140191a15  mov     ebx, eax
0x140191a17  test    eax, eax
0x140191a19  js      loc_140191BB2
0x140191a1f  mov     ecx, r14d; SubAuthorityCount
0x140191a22  call    cs:__imp_RtlLengthRequiredSid
0x140191a29  nop     dword ptr [rax+rax+00h]
0x140191a2e  mov     ebx, 676E7049h
0x140191a33  mov     edx, eax
0x140191a35  mov     r8d, ebx
0x140191a38  mov     rcx, rsi
0x140191a3b  call    cs:__imp_ExAllocatePool2
0x140191a42  nop     dword ptr [rax+rax+00h]
0x140191a47  mov     rsi, rax
0x140191a4a  test    rax, rax
0x140191a4d  jnz     short loc_140191A7C
0x140191a4f  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, r13b
0x140191a56  jge     short loc_140191A72
0x140191a58  lea     r9, aEchoRequestSid; "echo request SID (IPNG)"
0x140191a5f  lea     rdx, TCPIP_MEMORY_FAILURES
0x140191a66  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140191a6d  call    McTemplateK0z_EtwWriteTransfer
0x140191a72  mov     ebx, 0C000009Ah
0x140191a77  jmp     loc_140191BB2
0x140191a7c  mov     rcx, rsi; Sid
0x140191a7f  mov     dword ptr [rax], 101h
0x140191a85  mov     qword ptr [rax+4], 1000000h
0x140191a8d  call    cs:__imp_RtlLengthSid
0x140191a94  nop     dword ptr [rax+rax+00h]
0x140191a99  mov     r8d, ebx
0x140191a9c  mov     ecx, 40h ; '@'
0x140191aa1  lea     r15d, [rax+10h]
0x140191aa5  mov     edx, r15d
0x140191aa8  call    cs:__imp_ExAllocatePool2
0x140191aaf  nop     dword ptr [rax+rax+00h]
0x140191ab4  mov     r14, rax
0x140191ab7  test    rax, rax
0x140191aba  jnz     short loc_140191AE9
0x140191abc  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, r13b
0x140191ac3  jge     short loc_140191ADF
0x140191ac5  lea     r9, aEchoRequestAcl; "echo request ACL (IPNG)"
0x140191acc  lea     rdx, TCPIP_MEMORY_FAILURES
0x140191ad3  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140191ada  call    McTemplateK0z_EtwWriteTransfer
0x140191adf  mov     ebx, 0C000009Ah
0x140191ae4  jmp     loc_140191B9D
0x140191ae9  mov     r8d, 2; AclRevision
0x140191aef  mov     edx, r15d; AclLength
0x140191af2  mov     rcx, r14; Acl
0x140191af5  call    cs:__imp_RtlCreateAcl
0x140191afc  nop     dword ptr [rax+rax+00h]
0x140191b01  mov     ebx, eax
0x140191b03  test    eax, eax
0x140191b05  js      loc_140191B8C
0x140191b0b  mov     edx, 2; AceRevision
0x140191b10  mov     [rsp+0D0h+Sid], rsi; Sid
0x140191b15  mov     r9d, 2001Fh; AccessMask
0x140191b1b  mov     rcx, r14; Acl
0x140191b1e  lea     r8d, [rdx+1]; AceFlags
0x140191b22  call    cs:__imp_RtlAddAccessAllowedAceEx
0x140191b29  nop     dword ptr [rax+rax+00h]
0x140191b2e  mov     ebx, eax
0x140191b30  test    eax, eax
0x140191b32  js      short loc_140191B8C
0x140191b34  xor     r9d, r9d; DaclDefaulted
0x140191b37  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x140191b3b  mov     r8, r14; Dacl
0x140191b3e  mov     dl, 1; DaclPresent
0x140191b40  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140191b47  nop     dword ptr [rax+rax+00h]
0x140191b4c  mov     rax, [rdi+20h]
0x140191b50  lea     rcx, [rbp+57h+var_78]
0x140191b54  mov     qword ptr [rbp+57h+var_78+8], rax
0x140191b58  lea     rax, [rbp+57h+SecurityDescriptor]
0x140191b5c  mov     qword ptr [rbp+57h+var_58], rax
0x140191b60  mov     dword ptr [rbp+57h+var_68], 4
0x140191b67  mov     dword ptr [rbp+57h+var_58+8], r15d
0x140191b6b  call    cs:__imp_NsiSetObjectSecurity
0x140191b72  nop     dword ptr [rax+rax+00h]
0x140191b77  mov     ebx, eax
0x140191b79  test    eax, eax
0x140191b7b  jnz     short loc_140191B8C
0x140191b7d  lock inc cs:IpngpReferenceCount
0x140191b84  lock add dword ptr [rdi+4D94h], 20h ; ' '
0x140191b8c  xor     edx, edx; Tag
0x140191b8e  mov     rcx, r14; P
0x140191b91  call    cs:__imp_ExFreePoolWithTag
0x140191b98  nop     dword ptr [rax+rax+00h]
0x140191b9d  xor     edx, edx; Tag
0x140191b9f  mov     rcx, rsi; P
0x140191ba2  call    cs:__imp_ExFreePoolWithTag
0x140191ba9  nop     dword ptr [rax+rax+00h]
0x140191bae  test    ebx, ebx
0x140191bb0  jns     short loc_140191BE9
0x140191bb2  mov     rcx, [rdi+4E58h]
0x140191bb9  call    cs:__imp_RtlCleanupTimerWheel
0x140191bc0  nop     dword ptr [rax+rax+00h]
0x140191bc5  mov     rcx, r12
0x140191bc8  call    cs:__imp_NetioShutdownWorkQueue
0x140191bcf  nop     dword ptr [rax+rax+00h]
0x140191bd4  mov     rcx, [rdi+4E58h]; P
0x140191bdb  xor     edx, edx; Tag
0x140191bdd  call    cs:__imp_ExFreePoolWithTag
0x140191be4  nop     dword ptr [rax+rax+00h]
0x140191be9  mov     eax, ebx
0x140191beb  add     rsp, 98h
0x140191bf2  pop     r15
0x140191bf4  pop     r14
0x140191bf6  pop     r13
0x140191bf8  pop     r12
0x140191bfa  pop     rdi
0x140191bfb  pop     rsi
0x140191bfc  pop     rbx
0x140191bfd  pop     rbp
0x140191bfe  retn
```
