# Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts(ushort,ulong,_SID const *,_SID const *,_ACL const *,_ACL const *,Windows::Auto<_SECURITY_DESCRIPTOR> *)

- ea: `0x18001aed4`
- end: `0x18001b040`
- name: `?CreateSecurityDescriptorFromParts@Rtl@Implementation@WCP@Windows@@YAJGKPEBU_SID@@0PEBU_ACL@@1PEAV?$Auto@U_SECURITY_DESCRIPTOR@@@4@@Z`
- size: `364`
- prototype: `__int64 __fastcall(__int64, __int64, void *, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001aa14`

## callees

- `0x180007568`
- `0x18001ab5c`
- `0x18001aed4`
- `0x18001b7b0`

## import_xrefs

- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18001af5d`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18001af5d`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x18001af84`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x18001af84`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18001af0f`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18001af0f`
- `ntdll!RtlFreeHeap` at `0x18001afe0`
- `ntdll!RtlFreeHeap` at `0x18001b01c`
- `ntdll!RtlFreeHeap` at `0x18001afe0`
- `ntdll!RtlFreeHeap` at `0x18001b01c`

## string_xrefs

- `0x18001af2a`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18001af3c`: `Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts`
- `0x18001af23`: `RtlCreateSecurityDescriptor( &AbsoluteSD, (1))`
- `0x18001af71`: `::RtlSetOwnerSecurityDescriptor( &AbsoluteSD, (PSID)Owner, 0)`
- `0x18001af98`: `::RtlSetGroupSecurityDescriptor( &AbsoluteSD, (PSID)Group, 0)`

## pseudocode

```c
__int64 __fastcall Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts(
        __int64 a1,
        __int64 a2,
        void *a3,
        void *a4)
{
  __int64 v6; // rdx
  int v7; // ebx
  const char *v8; // rax
  PVOID v10; // r8
  __int128 P; // [rsp+20h] [rbp-50h] BYREF
  __int64 v12; // [rsp+30h] [rbp-40h]
  const char *v13; // [rsp+38h] [rbp-38h]
  _OWORD SecurityDescriptor[2]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v15; // [rsp+60h] [rbp-10h]

  v15 = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v7 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  if ( v7 < 0 )
  {
    v12 = 346;
    v8 = "RtlCreateSecurityDescriptor( &AbsoluteSD, (1))";
LABEL_3:
    v13 = v8;
    *(_QWORD *)&P = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    *((_QWORD *)&P + 1) = "Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts";
    RtlReportErrorOrigination(
      "Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts",
      v6,
      (unsigned int)v7);
    return (unsigned int)v7;
  }
  v7 = RtlSetOwnerSecurityDescriptor(SecurityDescriptor, a3, 0);
  if ( v7 < 0 )
  {
    v12 = 355;
    v8 = "::RtlSetOwnerSecurityDescriptor( &AbsoluteSD, (PSID)Owner, 0)";
    goto LABEL_3;
  }
  v7 = RtlSetGroupSecurityDescriptor(SecurityDescriptor, a4, 0);
  if ( v7 < 0 )
  {
    v12 = 363;
    v8 = "::RtlSetGroupSecurityDescriptor( &AbsoluteSD, (PSID)Group, 0)";
    goto LABEL_3;
  }
  P = 0u;
  v7 = Windows::Auto<_SECURITY_DESCRIPTOR>::Assign(&P, SecurityDescriptor);
  if ( v7 < 0 )
  {
    if ( (_QWORD)P )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)P);
    return (unsigned int)v7;
  }
  v10 = ::P;
  *(_OWORD *)&::P = P;
  if ( v10 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
  return 0;
}

```

## disassembly

```asm
0x18001aed4  mov     [rsp-18h+arg_0], rbx
0x18001aed9  push    rbp
0x18001aeda  push    rsi
0x18001aedb  push    rdi
0x18001aedc  mov     rbp, rsp
0x18001aedf  sub     rsp, 70h
0x18001aee3  mov     rax, cs:__security_cookie
0x18001aeea  xor     rax, rsp
0x18001aeed  mov     [rbp+var_8], rax
0x18001aef1  xor     eax, eax
0x18001aef3  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18001aef7  xorps   xmm0, xmm0
0x18001aefa  mov     [rbp+var_10], rax
0x18001aefe  mov     rsi, r9
0x18001af01  mov     rdi, r8
0x18001af04  movups  [rbp+SecurityDescriptor], xmm0
0x18001af08  lea     edx, [rax+1]; Revision
0x18001af0b  movups  [rbp+var_20], xmm0
0x18001af0f  call    cs:__imp_RtlCreateSecurityDescriptor
0x18001af15  mov     ebx, eax
0x18001af17  test    eax, eax
0x18001af19  jns     short loc_18001AF53
0x18001af1b  mov     [rbp+var_40], 15Ah
0x18001af23  lea     rax, aRtlcreatesecur; "RtlCreateSecurityDescriptor( &AbsoluteS"...
0x18001af2a  lea     rcx, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18001af31  mov     [rbp+var_38], rax
0x18001af35  mov     qword ptr [rbp+P], rcx
0x18001af39  mov     r8d, ebx
0x18001af3c  lea     rcx, aWindowsWcpImpl_1; "Windows::WCP::Implementation::Rtl::Crea"...
0x18001af43  mov     qword ptr [rbp+P+8], rcx
0x18001af47  call    RtlReportErrorOrigination
0x18001af4c  mov     eax, ebx
0x18001af4e  jmp     loc_18001B024
0x18001af53  xor     r8d, r8d; OwnerDefaulted
0x18001af56  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18001af5a  mov     rdx, rdi; Owner
0x18001af5d  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x18001af63  mov     ebx, eax
0x18001af65  test    eax, eax
0x18001af67  jns     short loc_18001AF7A
0x18001af69  mov     [rbp+var_40], 163h
0x18001af71  lea     rax, aRtlsetownersec; "::RtlSetOwnerSecurityDescriptor( &Absol"...
0x18001af78  jmp     short loc_18001AF2A
0x18001af7a  xor     r8d, r8d; GroupDefaulted
0x18001af7d  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18001af81  mov     rdx, rsi; Group
0x18001af84  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x18001af8a  mov     ebx, eax
0x18001af8c  test    eax, eax
0x18001af8e  jns     short loc_18001AFA1
0x18001af90  mov     [rbp+var_40], 16Bh
0x18001af98  lea     rax, aRtlsetgroupsec; "::RtlSetGroupSecurityDescriptor( &Absol"...
0x18001af9f  jmp     short loc_18001AF2A
0x18001afa1  lea     rdx, [rbp+SecurityDescriptor]
0x18001afa5  mov     qword ptr [rbp+P], 0
0x18001afad  lea     rcx, [rbp+P]
0x18001afb1  mov     qword ptr [rbp+P+8], 0
0x18001afb9  call    ?Assign@?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAJPEBU_SECURITY_DESCRIPTOR@@@Z; Windows::Auto<_SECURITY_DESCRIPTOR>::Assign(_SECURITY_DESCRIPTOR const *)
0x18001afbe  mov     ebx, eax
0x18001afc0  test    eax, eax
0x18001afc2  jns     short loc_18001AFEB
0x18001afc4  mov     r8, qword ptr [rbp+P]; P
0x18001afc8  test    r8, r8
0x18001afcb  jz      loc_18001AF4C
0x18001afd1  mov     rcx, gs:60h
0x18001afda  xor     edx, edx; Flags
0x18001afdc  mov     rcx, [rcx+30h]; HeapHandle
0x18001afe0  call    cs:__imp_RtlFreeHeap
0x18001afe6  jmp     loc_18001AF4C
0x18001afeb  mov     rax, qword ptr [rbp+P]
0x18001afef  mov     r8, qword ptr cs:P; P
0x18001aff6  mov     qword ptr cs:P, rax
0x18001affd  mov     rax, qword ptr [rbp+P+8]
0x18001b001  mov     qword ptr cs:P+8, rax
0x18001b008  test    r8, r8
0x18001b00b  jz      short loc_18001B022
0x18001b00d  mov     rcx, gs:60h
0x18001b016  xor     edx, edx; Flags
0x18001b018  mov     rcx, [rcx+30h]; HeapHandle
0x18001b01c  call    cs:__imp_RtlFreeHeap
0x18001b022  xor     eax, eax
0x18001b024  mov     rcx, [rbp+var_8]
0x18001b028  xor     rcx, rsp; StackCookie
0x18001b02b  call    __security_check_cookie
0x18001b030  mov     rbx, [rsp+70h+arg_0]
0x18001b038  add     rsp, 70h
0x18001b03c  pop     rdi
0x18001b03d  pop     rsi
0x18001b03e  pop     rbp
0x18001b03f  retn
```
