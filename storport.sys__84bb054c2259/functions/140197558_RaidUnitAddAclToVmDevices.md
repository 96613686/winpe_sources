# RaidUnitAddAclToVmDevices

- ea: `0x140197558`
- end: `0x140197738`
- name: `RaidUnitAddAclToVmDevices`
- size: `480`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400cb3e8`

## callees

- `0x1400290b0`
- `0x140197558`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140197703`
- `ntoskrnl!ExFreePoolWithTag` at `0x140197703`
- `ntoskrnl!ZwClose` at `0x140197717`
- `ntoskrnl!ZwClose` at `0x140197717`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1401976cb`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1401976cb`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1401975a9`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1401975a9`
- `ntoskrnl!RtlLengthSid` at `0x1401975f5`
- `ntoskrnl!RtlLengthSid` at `0x140197606`
- `ntoskrnl!RtlLengthSid` at `0x1401975f5`
- `ntoskrnl!RtlLengthSid` at `0x140197606`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14019767e`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1401976ac`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14019767e`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1401976ac`
- `ntoskrnl!RtlCreateAcl` at `0x14019764c`
- `ntoskrnl!RtlCreateAcl` at `0x14019764c`
- `ntoskrnl!ZwSetSecurityObject` at `0x1401976ed`
- `ntoskrnl!ZwSetSecurityObject` at `0x1401976ed`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1401975c7`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1401975c7`
- `ntoskrnl!SeExports` at `0x1401975dd`
- `ntoskrnl!SeExports` at `0x140197662`
- `ntoskrnl!SeExports` at `0x140197690`

## pseudocode

```c
NTSTATUS __fastcall RaidUnitAddAclToVmDevices(__int64 a1)
{
  void *v2; // rcx
  NTSTATUS result; // eax
  NTSTATUS Acl; // ebx
  PSID SeAliasAdminsSid; // rdi
  ULONG v6; // ebx
  ULONG v7; // ebx
  struct _ACL *Pool; // rax
  struct _ACL *v9; // rdi
  _OWORD SecurityDescriptor[2]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v11; // [rsp+60h] [rbp-18h]
  HANDLE Handle; // [rsp+80h] [rbp+8h] BYREF

  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  Handle = 0;
  v2 = *(void **)(a1 + 8);
  v11 = 0;
  result = ObOpenObjectByPointer(v2, 0x200u, 0, 0x40000u, 0, 0, &Handle);
  if ( result >= 0 )
  {
    Acl = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
    if ( Acl >= 0 )
    {
      SeAliasAdminsSid = SeExports->SeAliasAdminsSid;
      v6 = RtlLengthSid(SeExports->SeLocalSystemSid);
      v7 = RtlLengthSid(SeAliasAdminsSid) + 32 + v6;
      Pool = (struct _ACL *)RaidAllocatePool(256, v7, 1818452292, *(_QWORD *)(a1 + 8));
      v9 = Pool;
      if ( Pool )
      {
        Acl = RtlCreateAcl(Pool, v7, 2u);
        if ( Acl >= 0 )
        {
          Acl = RtlAddAccessAllowedAce(v9, 2u, 0x1F01FFu, SeExports->SeAliasAdminsSid);
          if ( Acl >= 0 )
          {
            Acl = RtlAddAccessAllowedAce(v9, 2u, 0x1F01FFu, SeExports->SeLocalSystemSid);
            if ( Acl >= 0 )
            {
              Acl = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v9, 0);
              if ( Acl >= 0 )
                Acl = ZwSetSecurityObject(Handle, 4u, SecurityDescriptor);
            }
          }
        }
        ExFreePoolWithTag(v9, 0x6C636144u);
      }
      else
      {
        Acl = -1073741670;
      }
    }
    ZwClose(Handle);
    return Acl;
  }
  return result;
}

```

## disassembly

```asm
0x140197558  mov     r11, rsp
0x14019755b  mov     [r11+10h], rbx
0x14019755f  mov     [r11+18h], rsi
0x140197563  push    rdi
0x140197564  sub     rsp, 70h
0x140197568  xor     eax, eax
0x14019756a  xorps   xmm0, xmm0
0x14019756d  movups  [rsp+78h+SecurityDescriptor], xmm0
0x140197572  mov     [r11+8], rax
0x140197576  mov     rsi, rcx
0x140197579  mov     rcx, [rcx+8]; Object
0x14019757d  mov     r9d, 40000h; DesiredAccess
0x140197583  movups  [rsp+78h+var_28], xmm0
0x140197588  mov     [r11-18h], rax
0x14019758c  xor     r8d, r8d; PassedAccessState
0x14019758f  lea     rax, [r11+8]
0x140197593  mov     edx, 200h; HandleAttributes
0x140197598  mov     [r11-48h], rax
0x14019759c  mov     [rsp+78h+AccessMode], 0; AccessMode
0x1401975a1  mov     qword ptr [r11-58h], 0
0x1401975a9  call    cs:__imp_ObOpenObjectByPointer
0x1401975b0  nop     dword ptr [rax+rax+00h]
0x1401975b5  test    eax, eax
0x1401975b7  js      loc_140197725
0x1401975bd  mov     edx, 1; Revision
0x1401975c2  lea     rcx, [rsp+78h+SecurityDescriptor]; SecurityDescriptor
0x1401975c7  call    cs:__imp_RtlCreateSecurityDescriptor
0x1401975ce  nop     dword ptr [rax+rax+00h]
0x1401975d3  mov     ebx, eax
0x1401975d5  test    eax, eax
0x1401975d7  js      loc_14019770F
0x1401975dd  mov     rdx, cs:__imp_SeExports
0x1401975e4  mov     rax, [rdx]
0x1401975e7  mov     rcx, [rax+108h]; Sid
0x1401975ee  mov     rdi, [rax+110h]
0x1401975f5  call    cs:__imp_RtlLengthSid
0x1401975fc  nop     dword ptr [rax+rax+00h]
0x140197601  mov     rcx, rdi; Sid
0x140197604  mov     ebx, eax
0x140197606  call    cs:__imp_RtlLengthSid
0x14019760d  nop     dword ptr [rax+rax+00h]
0x140197612  mov     r9, [rsi+8]
0x140197616  mov     ecx, 100h
0x14019761b  add     eax, 20h ; ' '
0x14019761e  mov     r8d, 6C636144h
0x140197624  add     ebx, eax
0x140197626  mov     edx, ebx
0x140197628  call    RaidAllocatePool
0x14019762d  mov     rdi, rax
0x140197630  test    rax, rax
0x140197633  jnz     short loc_14019763F
0x140197635  mov     ebx, 0C000009Ah
0x14019763a  jmp     loc_14019770F
0x14019763f  mov     esi, 2
0x140197644  mov     edx, ebx; AclLength
0x140197646  mov     r8d, esi; AclRevision
0x140197649  mov     rcx, rdi; Acl
0x14019764c  call    cs:__imp_RtlCreateAcl
0x140197653  nop     dword ptr [rax+rax+00h]
0x140197658  mov     ebx, eax
0x14019765a  test    eax, eax
0x14019765c  js      loc_1401976FB
0x140197662  mov     rax, cs:__imp_SeExports
0x140197669  mov     r8d, 1F01FFh; AccessMask
0x14019766f  mov     edx, esi; AceRevision
0x140197671  mov     rcx, rdi; Acl
0x140197674  mov     r9, [rax]
0x140197677  mov     r9, [r9+110h]; Sid
0x14019767e  call    cs:__imp_RtlAddAccessAllowedAce
0x140197685  nop     dword ptr [rax+rax+00h]
0x14019768a  mov     ebx, eax
0x14019768c  test    eax, eax
0x14019768e  js      short loc_1401976FB
0x140197690  mov     rax, cs:__imp_SeExports
0x140197697  mov     r8d, 1F01FFh; AccessMask
0x14019769d  mov     edx, esi; AceRevision
0x14019769f  mov     rcx, rdi; Acl
0x1401976a2  mov     r9, [rax]
0x1401976a5  mov     r9, [r9+108h]; Sid
0x1401976ac  call    cs:__imp_RtlAddAccessAllowedAce
0x1401976b3  nop     dword ptr [rax+rax+00h]
0x1401976b8  mov     ebx, eax
0x1401976ba  test    eax, eax
0x1401976bc  js      short loc_1401976FB
0x1401976be  xor     r9d, r9d; DaclDefaulted
0x1401976c1  lea     rcx, [rsp+78h+SecurityDescriptor]; SecurityDescriptor
0x1401976c6  mov     r8, rdi; Dacl
0x1401976c9  mov     dl, 1; DaclPresent
0x1401976cb  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1401976d2  nop     dword ptr [rax+rax+00h]
0x1401976d7  mov     ebx, eax
0x1401976d9  test    eax, eax
0x1401976db  js      short loc_1401976FB
0x1401976dd  mov     rcx, [rsp+78h+Handle]; Handle
0x1401976e5  lea     r8, [rsp+78h+SecurityDescriptor]; SecurityDescriptor
0x1401976ea  lea     edx, [rsi+2]; SecurityInformation
0x1401976ed  call    cs:__imp_ZwSetSecurityObject
0x1401976f4  nop     dword ptr [rax+rax+00h]
0x1401976f9  mov     ebx, eax
0x1401976fb  mov     edx, 6C636144h; Tag
0x140197700  mov     rcx, rdi; P
0x140197703  call    cs:__imp_ExFreePoolWithTag
0x14019770a  nop     dword ptr [rax+rax+00h]
0x14019770f  mov     rcx, [rsp+78h+Handle]; Handle
0x140197717  call    cs:__imp_ZwClose
0x14019771e  nop     dword ptr [rax+rax+00h]
0x140197723  mov     eax, ebx
0x140197725  lea     r11, [rsp+78h+var_8]
0x14019772a  mov     rbx, [r11+18h]
0x14019772e  mov     rsi, [r11+20h]
0x140197732  mov     rsp, r11
0x140197735  pop     rdi
0x140197736  retn
```
