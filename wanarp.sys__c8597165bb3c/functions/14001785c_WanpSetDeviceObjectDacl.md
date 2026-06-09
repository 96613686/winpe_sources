# WanpSetDeviceObjectDacl

- ea: `0x14001785c`
- end: `0x140017a44`
- name: `WanpSetDeviceObjectDacl`
- size: `488`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14001a078`

## callees

- `0x14001785c`

## import_xrefs

- `ntoskrnl!SeExports` at `0x1400178ba`
- `ntoskrnl!SeExports` at `0x140017940`
- `ntoskrnl!SeExports` at `0x140017975`
- `ntoskrnl!ZwClose` at `0x140017a0e`
- `ntoskrnl!ZwClose` at `0x140017a0e`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400179b0`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400179b0`
- `ntoskrnl!ZwSetSecurityObject` at `0x1400179f3`
- `ntoskrnl!ZwSetSecurityObject` at `0x1400179f3`
- `ntoskrnl!RtlCreateAcl` at `0x14001792a`
- `ntoskrnl!RtlCreateAcl` at `0x14001792a`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14001795f`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140017994`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14001795f`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140017994`
- `ntoskrnl!RtlLengthSid` at `0x1400178d2`
- `ntoskrnl!RtlLengthSid` at `0x1400178e3`
- `ntoskrnl!RtlLengthSid` at `0x1400178d2`
- `ntoskrnl!RtlLengthSid` at `0x1400178e3`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400178a4`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400178a4`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400179cf`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400179cf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017a27`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017a27`
- `ntoskrnl!ExAllocatePool2` at `0x140017901`
- `ntoskrnl!ExAllocatePool2` at `0x140017901`

## pseudocode

```c
__int64 __fastcall WanpSetDeviceObjectDacl(void *a1)
{
  struct _ACL *v1; // rdi
  NTSTATUS Acl; // ebx
  PSID SeLocalSystemSid; // rbx
  ULONG v4; // edi
  ULONG v5; // ebx
  struct _ACL *Pool2; // rax
  _OWORD SecurityDescriptor[2]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v9; // [rsp+60h] [rbp-18h]
  HANDLE Handle; // [rsp+88h] [rbp+10h] BYREF

  Handle = 0;
  v1 = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v9 = 0;
  Acl = ObOpenObjectByPointer(a1, 0x200u, 0, 0x40000u, 0, 0, &Handle);
  if ( Acl >= 0 )
  {
    SeLocalSystemSid = SeExports->SeLocalSystemSid;
    v4 = RtlLengthSid(SeExports->SeAliasAdminsSid);
    v5 = v4 + RtlLengthSid(SeLocalSystemSid) + 24;
    Pool2 = (struct _ACL *)ExAllocatePool2(256, v5, 1685090903);
    v1 = Pool2;
    if ( Pool2 )
    {
      Acl = RtlCreateAcl(Pool2, v5, 2u);
      if ( Acl >= 0 )
      {
        Acl = RtlAddAccessAllowedAce(v1, 2u, 0x1F01FFu, SeExports->SeLocalSystemSid);
        if ( Acl >= 0 )
        {
          Acl = RtlAddAccessAllowedAce(v1, 2u, 0x1F01FFu, SeExports->SeAliasAdminsSid);
          if ( Acl >= 0 )
          {
            Acl = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
            if ( Acl >= 0 )
            {
              Acl = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v1, 0);
              if ( Acl >= 0 )
                Acl = ZwSetSecurityObject(Handle, 4u, SecurityDescriptor);
            }
          }
        }
      }
    }
    else
    {
      Acl = -1073741670;
    }
  }
  if ( Handle )
    ZwClose(Handle);
  if ( v1 )
    ExFreePoolWithTag(v1, 0x64707257u);
  return (unsigned int)Acl;
}

```

## disassembly

```asm
0x14001785c  mov     r11, rsp
0x14001785f  mov     [r11+8], rbx
0x140017863  push    rdi
0x140017864  sub     rsp, 70h
0x140017868  xorps   xmm0, xmm0
0x14001786b  mov     qword ptr [r11+10h], 0
0x140017873  xor     eax, eax
0x140017875  xor     edi, edi
0x140017877  movups  [rsp+78h+SecurityDescriptor], xmm0
0x14001787c  mov     r9d, 40000h; DesiredAccess
0x140017882  xor     r8d, r8d; PassedAccessState
0x140017885  movups  [rsp+78h+var_28], xmm0
0x14001788a  mov     [r11-18h], rax
0x14001788e  mov     edx, 200h; HandleAttributes
0x140017893  lea     rax, [r11+10h]
0x140017897  mov     [r11-48h], rax
0x14001789b  mov     [rsp+78h+AccessMode], dil; AccessMode
0x1400178a0  mov     [r11-58h], rdi
0x1400178a4  call    cs:__imp_ObOpenObjectByPointer
0x1400178ab  nop     dword ptr [rax+rax+00h]
0x1400178b0  mov     ebx, eax
0x1400178b2  test    eax, eax
0x1400178b4  js      loc_140017A01
0x1400178ba  mov     rdx, cs:__imp_SeExports
0x1400178c1  mov     rax, [rdx]
0x1400178c4  mov     rcx, [rax+110h]; Sid
0x1400178cb  mov     rbx, [rax+108h]
0x1400178d2  call    cs:__imp_RtlLengthSid
0x1400178d9  nop     dword ptr [rax+rax+00h]
0x1400178de  mov     rcx, rbx; Sid
0x1400178e1  mov     edi, eax
0x1400178e3  call    cs:__imp_RtlLengthSid
0x1400178ea  nop     dword ptr [rax+rax+00h]
0x1400178ef  mov     ecx, 100h
0x1400178f4  mov     r8d, 64707257h
0x1400178fa  lea     ebx, [rax+18h]
0x1400178fd  add     ebx, edi
0x1400178ff  mov     edx, ebx
0x140017901  call    cs:__imp_ExAllocatePool2
0x140017908  nop     dword ptr [rax+rax+00h]
0x14001790d  mov     rdi, rax
0x140017910  test    rax, rax
0x140017913  jnz     short loc_14001791F
0x140017915  mov     ebx, 0C000009Ah
0x14001791a  jmp     loc_140017A01
0x14001791f  mov     r8d, 2; AclRevision
0x140017925  mov     edx, ebx; AclLength
0x140017927  mov     rcx, rdi; Acl
0x14001792a  call    cs:__imp_RtlCreateAcl
0x140017931  nop     dword ptr [rax+rax+00h]
0x140017936  mov     ebx, eax
0x140017938  test    eax, eax
0x14001793a  js      loc_140017A01
0x140017940  mov     rax, cs:__imp_SeExports
0x140017947  mov     edx, 2; AceRevision
0x14001794c  mov     r8d, 1F01FFh; AccessMask
0x140017952  mov     rcx, rdi; Acl
0x140017955  mov     r9, [rax]
0x140017958  mov     r9, [r9+108h]; Sid
0x14001795f  call    cs:__imp_RtlAddAccessAllowedAce
0x140017966  nop     dword ptr [rax+rax+00h]
0x14001796b  mov     ebx, eax
0x14001796d  test    eax, eax
0x14001796f  js      loc_140017A01
0x140017975  mov     rax, cs:__imp_SeExports
0x14001797c  mov     edx, 2; AceRevision
0x140017981  mov     r8d, 1F01FFh; AccessMask
0x140017987  mov     rcx, rdi; Acl
0x14001798a  mov     r9, [rax]
0x14001798d  mov     r9, [r9+110h]; Sid
0x140017994  call    cs:__imp_RtlAddAccessAllowedAce
0x14001799b  nop     dword ptr [rax+rax+00h]
0x1400179a0  mov     ebx, eax
0x1400179a2  test    eax, eax
0x1400179a4  js      short loc_140017A01
0x1400179a6  mov     edx, 1; Revision
0x1400179ab  lea     rcx, [rsp+78h+SecurityDescriptor]; SecurityDescriptor
0x1400179b0  call    cs:__imp_RtlCreateSecurityDescriptor
0x1400179b7  nop     dword ptr [rax+rax+00h]
0x1400179bc  mov     ebx, eax
0x1400179be  test    eax, eax
0x1400179c0  js      short loc_140017A01
0x1400179c2  xor     r9d, r9d; DaclDefaulted
0x1400179c5  lea     rcx, [rsp+78h+SecurityDescriptor]; SecurityDescriptor
0x1400179ca  mov     r8, rdi; Dacl
0x1400179cd  mov     dl, 1; DaclPresent
0x1400179cf  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1400179d6  nop     dword ptr [rax+rax+00h]
0x1400179db  mov     ebx, eax
0x1400179dd  test    eax, eax
0x1400179df  js      short loc_140017A01
0x1400179e1  mov     rcx, [rsp+78h+Handle]; Handle
0x1400179e9  lea     r8, [rsp+78h+SecurityDescriptor]; SecurityDescriptor
0x1400179ee  mov     edx, 4; SecurityInformation
0x1400179f3  call    cs:__imp_ZwSetSecurityObject
0x1400179fa  nop     dword ptr [rax+rax+00h]
0x1400179ff  mov     ebx, eax
0x140017a01  mov     rcx, [rsp+78h+Handle]; Handle
0x140017a09  test    rcx, rcx
0x140017a0c  jz      short loc_140017A1A
0x140017a0e  call    cs:__imp_ZwClose
0x140017a15  nop     dword ptr [rax+rax+00h]
0x140017a1a  test    rdi, rdi
0x140017a1d  jz      short loc_140017A33
0x140017a1f  mov     edx, 64707257h; Tag
0x140017a24  mov     rcx, rdi; P
0x140017a27  call    cs:__imp_ExFreePoolWithTag
0x140017a2e  nop     dword ptr [rax+rax+00h]
0x140017a33  mov     eax, ebx
0x140017a35  mov     rbx, [rsp+78h+arg_0]
0x140017a3d  add     rsp, 70h
0x140017a41  pop     rdi
0x140017a42  retn
```
