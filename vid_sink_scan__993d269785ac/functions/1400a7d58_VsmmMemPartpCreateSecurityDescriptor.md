# VsmmMemPartpCreateSecurityDescriptor

- ea: `0x1400a7d58`
- end: `0x1400a8035`
- name: `VsmmMemPartpCreateSecurityDescriptor`
- size: `733`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor, PACL Dacl)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400a64c0`
- `0x1400a803c`

## callees

- `0x140021650`
- `0x14002f524`
- `0x140099efc`
- `0x1400a7d58`

## import_xrefs

- `ntoskrnl!RtlLengthRequiredSid` at `0x1400a7e65`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400a7e65`
- `ntoskrnl!RtlInitializeSidEx` at `0x1400a7e96`
- `ntoskrnl!RtlInitializeSidEx` at `0x1400a7f26`
- `ntoskrnl!RtlInitializeSidEx` at `0x1400a7e96`
- `ntoskrnl!RtlInitializeSidEx` at `0x1400a7f26`
- `ntoskrnl!RtlCreateAcl` at `0x1400a7da4`
- `ntoskrnl!RtlCreateAcl` at `0x1400a7da4`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400a7e22`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400a7ed9`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400a7f69`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400a7e22`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400a7ed9`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400a7f69`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400a7fa1`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400a7fa1`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400a7fdc`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400a7fdc`

## string_xrefs

- `0x1400a7dc6`: `VsmmMemPartpCreateSecurityDescriptor`
- `0x1400a7e01`: `VsmmMemPartpCreateSecurityDescriptor`
- `0x1400a7e44`: `VsmmMemPartpCreateSecurityDescriptor`
- `0x1400a7eb8`: `VsmmMemPartpCreateSecurityDescriptor`
- `0x1400a7efb`: `VsmmMemPartpCreateSecurityDescriptor`
- `0x1400a7f48`: `VsmmMemPartpCreateSecurityDescriptor`
- `0x1400a7f8b`: `VsmmMemPartpCreateSecurityDescriptor`
- `0x1400a7fc3`: `VsmmMemPartpCreateSecurityDescriptor`
- `0x1400a7ffe`: `VsmmMemPartpCreateSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall VsmmMemPartpCreateSecurityDescriptor(PSECURITY_DESCRIPTOR SecurityDescriptor, PACL Dacl)
{
  NTSTATUS Acl; // ebx
  ULONG v6; // [rsp+30h] [rbp-39h] BYREF
  int v7; // [rsp+34h] [rbp-35h] BYREF
  __int16 v8; // [rsp+38h] [rbp-31h]
  int v9; // [rsp+3Ch] [rbp-2Dh] BYREF
  __int16 v10; // [rsp+40h] [rbp-29h]
  _BYTE Sid[80]; // [rsp+50h] [rbp-19h] BYREF

  v9 = 0;
  v10 = 1280;
  Acl = RtlCreateAcl(Dacl, 0xECu, 2u);
  if ( Acl < 0 )
  {
    VidTraceErrorStatusInternal0(
      "VsmmMemPartpCreateSecurityDescriptor",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempart.c",
      509);
    return (unsigned int)Acl;
  }
  v6 = 68;
  Acl = VidSidInitializeVmCompute(Sid, &v6);
  if ( Acl < 0 )
  {
    VidTraceErrorStatusInternal0(
      "VsmmMemPartpCreateSecurityDescriptor",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempart.c",
      522);
    return (unsigned int)Acl;
  }
  Acl = RtlAddAccessAllowedAce(Dacl, 2u, 1u, Sid);
  if ( Acl < 0 )
  {
    VidTraceErrorStatusInternal0(
      "VsmmMemPartpCreateSecurityDescriptor",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempart.c",
      534);
    return (unsigned int)Acl;
  }
  v7 = 0;
  v8 = 1280;
  if ( v6 < RtlLengthRequiredSid(2u) )
  {
    Acl = -1073741789;
LABEL_10:
    VidTraceErrorStatusInternal0(
      "VsmmMemPartpCreateSecurityDescriptor",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempart.c",
      545);
    return (unsigned int)Acl;
  }
  Acl = RtlInitializeSidEx(Sid, &v7, 2, 32, 544);
  if ( Acl < 0 )
    goto LABEL_10;
  Acl = RtlAddAccessAllowedAce(Dacl, 2u, 1u, Sid);
  if ( Acl >= 0 )
  {
    Acl = RtlInitializeSidEx(Sid, &v9, 2, 83, 0);
    if ( Acl >= 0 )
    {
      Acl = RtlAddAccessAllowedAce(Dacl, 2u, 1u, Sid);
      if ( Acl >= 0 )
      {
        Acl = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
        if ( Acl >= 0 )
        {
          Acl = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, Dacl, 0);
          if ( Acl >= 0 )
            return 0;
          else
            VidTraceErrorStatusInternal0(
              "VsmmMemPartpCreateSecurityDescriptor",
              "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempart.c",
              610);
        }
        else
        {
          VidTraceErrorStatusInternal0(
            "VsmmMemPartpCreateSecurityDescriptor",
            "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempart.c",
            598);
        }
      }
      else
      {
        VidTraceErrorStatusInternal0(
          "VsmmMemPartpCreateSecurityDescriptor",
          "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempart.c",
          585);
      }
    }
    else
    {
      VidTraceErrorStatusInternal0(
        "VsmmMemPartpCreateSecurityDescriptor",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempart.c",
        573);
    }
  }
  else
  {
    VidTraceErrorStatusInternal0(
      "VsmmMemPartpCreateSecurityDescriptor",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempart.c",
      557);
  }
  return (unsigned int)Acl;
}

```

## disassembly

```asm
0x1400a7d58  mov     [rsp-8+arg_10], rbx
0x1400a7d5d  mov     [rsp-8+arg_18], rsi
0x1400a7d62  push    rbp
0x1400a7d63  push    rdi
0x1400a7d64  push    r15
0x1400a7d66  lea     rbp, [rsp-47h]
0x1400a7d6b  sub     rsp, 0B0h
0x1400a7d72  mov     rax, cs:__security_cookie
0x1400a7d79  xor     rax, rsp
0x1400a7d7c  mov     [rbp+57h+var_20], rax
0x1400a7d80  mov     rdi, rdx
0x1400a7d83  mov     [rbp+57h+var_84], 0
0x1400a7d8a  mov     rsi, rcx
0x1400a7d8d  mov     [rbp+57h+var_80], 500h
0x1400a7d93  mov     r15d, 2
0x1400a7d99  mov     rcx, rdi; Acl
0x1400a7d9c  mov     r8d, r15d; AclRevision
0x1400a7d9f  mov     edx, 0ECh; AclLength
0x1400a7da4  call    cs:__imp_RtlCreateAcl
0x1400a7dab  nop     dword ptr [rax+rax+00h]
0x1400a7db0  mov     ebx, eax
0x1400a7db2  test    eax, eax
0x1400a7db4  jns     short loc_1400A7DD7
0x1400a7db6  mov     r9d, eax
0x1400a7db9  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a7dc0  mov     r8d, 1FDh
0x1400a7dc6  lea     rcx, aVsmmmempartpcr; "VsmmMemPartpCreateSecurityDescriptor"
0x1400a7dcd  call    VidTraceErrorStatusInternal0
0x1400a7dd2  jmp     loc_1400A800E
0x1400a7dd7  lea     rdx, [rbp+57h+var_90]
0x1400a7ddb  mov     [rbp+57h+var_90], 44h ; 'D'
0x1400a7de2  lea     rcx, [rbp+57h+Sid]
0x1400a7de6  call    VidSidInitializeVmCompute
0x1400a7deb  mov     ebx, eax
0x1400a7ded  test    eax, eax
0x1400a7def  jns     short loc_1400A7E12
0x1400a7df1  mov     r9d, eax
0x1400a7df4  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a7dfb  mov     r8d, 20Ah
0x1400a7e01  lea     rcx, aVsmmmempartpcr; "VsmmMemPartpCreateSecurityDescriptor"
0x1400a7e08  call    VidTraceErrorStatusInternal0
0x1400a7e0d  jmp     loc_1400A800E
0x1400a7e12  lea     r9, [rbp+57h+Sid]; Sid
0x1400a7e16  mov     r8d, 1; AccessMask
0x1400a7e1c  mov     edx, r15d; AceRevision
0x1400a7e1f  mov     rcx, rdi; Acl
0x1400a7e22  call    cs:__imp_RtlAddAccessAllowedAce
0x1400a7e29  nop     dword ptr [rax+rax+00h]
0x1400a7e2e  mov     ebx, eax
0x1400a7e30  test    eax, eax
0x1400a7e32  jns     short loc_1400A7E55
0x1400a7e34  mov     r9d, eax
0x1400a7e37  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a7e3e  mov     r8d, 216h
0x1400a7e44  lea     rcx, aVsmmmempartpcr; "VsmmMemPartpCreateSecurityDescriptor"
0x1400a7e4b  call    VidTraceErrorStatusInternal0
0x1400a7e50  jmp     loc_1400A800E
0x1400a7e55  mov     ecx, r15d; SubAuthorityCount
0x1400a7e58  mov     [rbp+57h+var_8C], 0
0x1400a7e5f  mov     [rbp+57h+var_88], 500h
0x1400a7e65  call    cs:__imp_RtlLengthRequiredSid
0x1400a7e6c  nop     dword ptr [rax+rax+00h]
0x1400a7e71  cmp     [rbp+57h+var_90], eax
0x1400a7e74  jnb     short loc_1400A7E7D
0x1400a7e76  mov     ebx, 0C0000023h
0x1400a7e7b  jmp     short loc_1400A7EA8
0x1400a7e7d  mov     r9d, 20h ; ' '
0x1400a7e83  mov     dword ptr [rsp+0C0h+var_A0], 220h
0x1400a7e8b  mov     r8d, r15d
0x1400a7e8e  lea     rdx, [rbp+57h+var_8C]
0x1400a7e92  lea     rcx, [rbp+57h+Sid]
0x1400a7e96  call    cs:__imp_RtlInitializeSidEx
0x1400a7e9d  nop     dword ptr [rax+rax+00h]
0x1400a7ea2  mov     ebx, eax
0x1400a7ea4  test    eax, eax
0x1400a7ea6  jns     short loc_1400A7EC9
0x1400a7ea8  mov     r9d, ebx
0x1400a7eab  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a7eb2  mov     r8d, 221h
0x1400a7eb8  lea     rcx, aVsmmmempartpcr; "VsmmMemPartpCreateSecurityDescriptor"
0x1400a7ebf  call    VidTraceErrorStatusInternal0
0x1400a7ec4  jmp     loc_1400A800E
0x1400a7ec9  lea     r9, [rbp+57h+Sid]; Sid
0x1400a7ecd  mov     r8d, 1; AccessMask
0x1400a7ed3  mov     edx, r15d; AceRevision
0x1400a7ed6  mov     rcx, rdi; Acl
0x1400a7ed9  call    cs:__imp_RtlAddAccessAllowedAce
0x1400a7ee0  nop     dword ptr [rax+rax+00h]
0x1400a7ee5  mov     ebx, eax
0x1400a7ee7  test    eax, eax
0x1400a7ee9  jns     short loc_1400A7F0C
0x1400a7eeb  mov     r9d, eax
0x1400a7eee  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a7ef5  mov     r8d, 22Dh
0x1400a7efb  lea     rcx, aVsmmmempartpcr; "VsmmMemPartpCreateSecurityDescriptor"
0x1400a7f02  call    VidTraceErrorStatusInternal0
0x1400a7f07  jmp     loc_1400A800E
0x1400a7f0c  mov     r9d, 53h ; 'S'
0x1400a7f12  mov     [rsp+0C0h+var_A0], 0
0x1400a7f1b  mov     r8d, r15d
0x1400a7f1e  lea     rdx, [rbp+57h+var_84]
0x1400a7f22  lea     rcx, [rbp+57h+Sid]
0x1400a7f26  call    cs:__imp_RtlInitializeSidEx
0x1400a7f2d  nop     dword ptr [rax+rax+00h]
0x1400a7f32  mov     ebx, eax
0x1400a7f34  test    eax, eax
0x1400a7f36  jns     short loc_1400A7F59
0x1400a7f38  mov     r9d, eax
0x1400a7f3b  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a7f42  mov     r8d, 23Dh
0x1400a7f48  lea     rcx, aVsmmmempartpcr; "VsmmMemPartpCreateSecurityDescriptor"
0x1400a7f4f  call    VidTraceErrorStatusInternal0
0x1400a7f54  jmp     loc_1400A800E
0x1400a7f59  lea     r9, [rbp+57h+Sid]; Sid
0x1400a7f5d  mov     r8d, 1; AccessMask
0x1400a7f63  mov     edx, r15d; AceRevision
0x1400a7f66  mov     rcx, rdi; Acl
0x1400a7f69  call    cs:__imp_RtlAddAccessAllowedAce
0x1400a7f70  nop     dword ptr [rax+rax+00h]
0x1400a7f75  mov     ebx, eax
0x1400a7f77  test    eax, eax
0x1400a7f79  jns     short loc_1400A7F99
0x1400a7f7b  mov     r9d, eax
0x1400a7f7e  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a7f85  mov     r8d, 249h
0x1400a7f8b  lea     rcx, aVsmmmempartpcr; "VsmmMemPartpCreateSecurityDescriptor"
0x1400a7f92  call    VidTraceErrorStatusInternal0
0x1400a7f97  jmp     short loc_1400A800E
0x1400a7f99  mov     edx, 1; Revision
0x1400a7f9e  mov     rcx, rsi; SecurityDescriptor
0x1400a7fa1  call    cs:__imp_RtlCreateSecurityDescriptor
0x1400a7fa8  nop     dword ptr [rax+rax+00h]
0x1400a7fad  mov     ebx, eax
0x1400a7faf  test    eax, eax
0x1400a7fb1  jns     short loc_1400A7FD1
0x1400a7fb3  mov     r9d, eax
0x1400a7fb6  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a7fbd  mov     r8d, 256h
0x1400a7fc3  lea     rcx, aVsmmmempartpcr; "VsmmMemPartpCreateSecurityDescriptor"
0x1400a7fca  call    VidTraceErrorStatusInternal0
0x1400a7fcf  jmp     short loc_1400A800E
0x1400a7fd1  xor     r9d, r9d; DaclDefaulted
0x1400a7fd4  mov     r8, rdi; Dacl
0x1400a7fd7  mov     dl, 1; DaclPresent
0x1400a7fd9  mov     rcx, rsi; SecurityDescriptor
0x1400a7fdc  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1400a7fe3  nop     dword ptr [rax+rax+00h]
0x1400a7fe8  mov     ebx, eax
0x1400a7fea  test    eax, eax
0x1400a7fec  jns     short loc_1400A800C
0x1400a7fee  mov     r9d, eax
0x1400a7ff1  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a7ff8  mov     r8d, 262h
0x1400a7ffe  lea     rcx, aVsmmmempartpcr; "VsmmMemPartpCreateSecurityDescriptor"
0x1400a8005  call    VidTraceErrorStatusInternal0
0x1400a800a  jmp     short loc_1400A800E
0x1400a800c  xor     ebx, ebx
0x1400a800e  mov     eax, ebx
0x1400a8010  mov     rcx, [rbp+57h+var_20]
0x1400a8014  xor     rcx, rsp; StackCookie
0x1400a8017  call    __security_check_cookie
0x1400a801c  lea     r11, [rsp+0C0h+var_10]
0x1400a8024  mov     rbx, [r11+30h]
0x1400a8028  mov     rsi, [r11+38h]
0x1400a802c  mov     rsp, r11
0x1400a802f  pop     r15
0x1400a8031  pop     rdi
0x1400a8032  pop     rbp
0x1400a8033  retn
```
