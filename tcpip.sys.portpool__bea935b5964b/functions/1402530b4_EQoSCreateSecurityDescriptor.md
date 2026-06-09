# EQoSCreateSecurityDescriptor

- ea: `0x1402530b4`
- end: `0x14025339c`
- name: `EQoSCreateSecurityDescriptor`
- size: `744`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14025e318`

## callees

- `0x1400198ec`
- `0x1401179a8`
- `0x140154840`
- `0x1402530b4`

## import_xrefs

- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1402532d1`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1402532d1`
- `ntoskrnl!RtlCreateAcl` at `0x1402531b8`
- `ntoskrnl!RtlCreateAcl` at `0x1402531b8`
- `ntoskrnl!RtlLengthSid` at `0x140253137`
- `ntoskrnl!RtlLengthSid` at `0x140253137`
- `ntoskrnl!SeExports` at `0x14025330e`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1402530d0`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1402530d0`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140253209`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140253209`
- `ntoskrnl!RtlMapGenericMask` at `0x14025323e`
- `ntoskrnl!RtlMapGenericMask` at `0x14025323e`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14025325f`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14025325f`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x140253325`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x140253325`
- `ntoskrnl!ExFreePoolWithTag` at `0x14025337b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14025337b`

## pseudocode

```c
__int64 __fastcall EQoSCreateSecurityDescriptor(PSECURITY_DESCRIPTOR SecurityDescriptor, __int64 a2, DWORD a3)
{
  NTSTATUS v5; // eax
  unsigned int Acl; // ebx
  ULONG v8; // ebx
  __int64 i; // rdi
  ULONG v10; // eax
  struct _ACL *v11; // rax
  struct _ACL *v12; // rsi
  struct _DEVICE_OBJECT *AttachedDevice; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  struct _GENERIC_MAPPING *FileObjectGenericMapping; // r15
  unsigned int j; // edi
  NTSTATUS v18; // eax
  NTSTATUS v19; // eax
  PDEVICE_OBJECT v20; // r10
  DWORD AccessMask; // [rsp+80h] [rbp+18h] BYREF

  AccessMask = a3;
  v5 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  Acl = v5;
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        17,
        WPP_ac6ac8075c54330b91caa815a7f3d563_Traceguids,
        (unsigned int)v5);
    }
    return Acl;
  }
  v8 = 8;
  for ( i = 0; i != 5; ++i )
  {
    v10 = RtlLengthSid(*(PSID *)(a2 + 16 * i + 8));
    v8 += v10 + 8;
  }
  v11 = (struct _ACL *)EQoSAllocatePoolWithTagPriority(64, v8, 2018726213);
  v12 = v11;
  if ( v11 )
  {
    Acl = RtlCreateAcl(v11, v8, 2u);
    if ( (Acl & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
      {
        AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
        v14 = 19;
        v15 = Acl;
LABEL_39:
        WPP_SF_d(AttachedDevice, v14, WPP_ac6ac8075c54330b91caa815a7f3d563_Traceguids, v15);
      }
LABEL_40:
      ExFreePoolWithTag(v12, 0x78535145u);
      return Acl;
    }
    FileObjectGenericMapping = IoGetFileObjectGenericMapping();
    for ( j = 0; j < 5; ++j )
    {
      AccessMask = *(_DWORD *)(a2 + 16LL * j);
      RtlMapGenericMask(&AccessMask, FileObjectGenericMapping);
      v18 = RtlAddAccessAllowedAce(v12, 2u, AccessMask, *(PSID *)(a2 + 16LL * j + 8));
      Acl = v18;
      if ( v18 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
        {
          WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_ac6ac8075c54330b91caa815a7f3d563_Traceguids, j, v18);
        }
        goto LABEL_40;
      }
    }
    v19 = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v12, 0);
    Acl = v19;
    if ( v19 >= 0 )
    {
      v19 = RtlSetOwnerSecurityDescriptor(SecurityDescriptor, SeExports->SeLocalSystemSid, 0);
      Acl = v19;
      if ( v19 >= 0 )
        return 0;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) == 0 )
      {
        goto LABEL_40;
      }
      v14 = 22;
    }
    else
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) == 0 )
      {
        goto LABEL_40;
      }
      v14 = 21;
    }
    AttachedDevice = v20->AttachedDevice;
    v15 = (unsigned int)v19;
    goto LABEL_39;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_ac6ac8075c54330b91caa815a7f3d563_Traceguids, v8);
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x1402530b4  mov     [rsp+AccessMask], r8d
0x1402530b9  push    rbx
0x1402530ba  push    rbp
0x1402530bb  push    rsi
0x1402530bc  push    rdi
0x1402530bd  push    r14
0x1402530bf  push    r15
0x1402530c1  sub     rsp, 38h
0x1402530c5  mov     r14, rdx
0x1402530c8  mov     rbp, rcx
0x1402530cb  mov     edx, 1; Revision
0x1402530d0  call    cs:__imp_RtlCreateSecurityDescriptor
0x1402530d7  nop     dword ptr [rax+rax+00h]
0x1402530dc  mov     ebx, eax
0x1402530de  test    eax, eax
0x1402530e0  jns     short loc_140253125
0x1402530e2  mov     r10, cs:WPP_GLOBAL_Control
0x1402530e9  lea     rcx, WPP_GLOBAL_Control
0x1402530f0  cmp     r10, rcx
0x1402530f3  jz      short loc_14025311E
0x1402530f5  cmp     byte ptr [r10+29h], 2
0x1402530fa  jb      short loc_14025311E
0x1402530fc  test    dword ptr [r10+2Ch], 40000h
0x140253104  jz      short loc_14025311E
0x140253106  mov     rcx, [r10+18h]
0x14025310a  lea     r8, WPP_ac6ac8075c54330b91caa815a7f3d563_Traceguids
0x140253111  mov     edx, 11h
0x140253116  mov     r9d, eax
0x140253119  call    WPP_SF_d
0x14025311e  mov     eax, ebx
0x140253120  jmp     loc_14025338E
0x140253125  mov     ebx, 8
0x14025312a  xor     edi, edi
0x14025312c  mov     rcx, rdi
0x14025312f  add     rcx, rcx
0x140253132  mov     rcx, [r14+rcx*8+8]; Sid
0x140253137  call    cs:__imp_RtlLengthSid
0x14025313e  nop     dword ptr [rax+rax+00h]
0x140253143  add     ebx, 8
0x140253146  inc     rdi
0x140253149  add     ebx, eax
0x14025314b  cmp     rdi, 5
0x14025314f  jnz     short loc_14025312C
0x140253151  mov     edx, ebx
0x140253153  lea     ecx, [rdi+3Bh]
0x140253156  mov     r8d, 78535145h
0x14025315c  call    EQoSAllocatePoolWithTagPriority
0x140253161  mov     rsi, rax
0x140253164  test    rax, rax
0x140253167  jnz     short loc_1402531AD
0x140253169  mov     r10, cs:WPP_GLOBAL_Control
0x140253170  lea     rcx, WPP_GLOBAL_Control
0x140253177  cmp     r10, rcx
0x14025317a  jz      short loc_1402531A3
0x14025317c  cmp     byte ptr [r10+29h], 2
0x140253181  jb      short loc_1402531A3
0x140253183  test    dword ptr [r10+2Ch], 40000h
0x14025318b  jz      short loc_1402531A3
0x14025318d  mov     rcx, [r10+18h]
0x140253191  lea     edx, [rdi+0Dh]
0x140253194  mov     r9d, ebx
0x140253197  lea     r8, WPP_ac6ac8075c54330b91caa815a7f3d563_Traceguids
0x14025319e  call    WPP_SF_d
0x1402531a3  mov     eax, 0C000009Ah
0x1402531a8  jmp     loc_14025338E
0x1402531ad  mov     r8d, 2; AclRevision
0x1402531b3  mov     edx, ebx; AclLength
0x1402531b5  mov     rcx, rsi; Acl
0x1402531b8  call    cs:__imp_RtlCreateAcl
0x1402531bf  nop     dword ptr [rax+rax+00h]
0x1402531c4  mov     ebx, eax
0x1402531c6  test    eax, eax
0x1402531c8  jns     short loc_140253209
0x1402531ca  mov     rax, cs:WPP_GLOBAL_Control
0x1402531d1  lea     rcx, WPP_GLOBAL_Control
0x1402531d8  cmp     rax, rcx
0x1402531db  jz      loc_140253373
0x1402531e1  cmp     byte ptr [rax+29h], 2
0x1402531e5  jb      loc_140253373
0x1402531eb  test    dword ptr [rax+2Ch], 40000h
0x1402531f2  jz      loc_140253373
0x1402531f8  mov     rcx, [rax+18h]
0x1402531fc  mov     edx, 13h
0x140253201  mov     r9d, ebx
0x140253204  jmp     loc_140253367
0x140253209  call    cs:__imp_IoGetFileObjectGenericMapping
0x140253210  nop     dword ptr [rax+rax+00h]
0x140253215  mov     r15, rax
0x140253218  xor     edi, edi
0x14025321a  cmp     edi, 5
0x14025321d  jnb     loc_1402532C6
0x140253223  mov     ebx, edi
0x140253225  mov     rdx, r15; GenericMapping
0x140253228  add     rbx, rbx
0x14025322b  mov     ecx, [r14+rbx*8]
0x14025322f  mov     [rsp+68h+AccessMask], ecx
0x140253236  lea     rcx, [rsp+68h+AccessMask]; AccessMask
0x14025323e  call    cs:__imp_RtlMapGenericMask
0x140253245  nop     dword ptr [rax+rax+00h]
0x14025324a  mov     r9, [r14+rbx*8+8]; Sid
0x14025324f  mov     edx, 2; AceRevision
0x140253254  mov     r8d, [rsp+68h+AccessMask]; AccessMask
0x14025325c  mov     rcx, rsi; Acl
0x14025325f  call    cs:__imp_RtlAddAccessAllowedAce
0x140253266  nop     dword ptr [rax+rax+00h]
0x14025326b  mov     ebx, eax
0x14025326d  test    eax, eax
0x14025326f  js      short loc_140253275
0x140253271  inc     edi
0x140253273  jmp     short loc_14025321A
0x140253275  mov     r10, cs:WPP_GLOBAL_Control
0x14025327c  lea     rcx, WPP_GLOBAL_Control
0x140253283  cmp     r10, rcx
0x140253286  jz      loc_140253373
0x14025328c  cmp     byte ptr [r10+29h], 2
0x140253291  jb      loc_140253373
0x140253297  test    dword ptr [r10+2Ch], 40000h
0x14025329f  jz      loc_140253373
0x1402532a5  mov     rcx, [r10+18h]
0x1402532a9  lea     r8, WPP_ac6ac8075c54330b91caa815a7f3d563_Traceguids
0x1402532b0  mov     edx, 14h
0x1402532b5  mov     [rsp+68h+var_48], eax
0x1402532b9  mov     r9d, edi
0x1402532bc  call    WPP_SF_Dd
0x1402532c1  jmp     loc_140253373
0x1402532c6  xor     r9d, r9d; DaclDefaulted
0x1402532c9  mov     r8, rsi; Dacl
0x1402532cc  mov     dl, 1; DaclPresent
0x1402532ce  mov     rcx, rbp; SecurityDescriptor
0x1402532d1  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1402532d8  nop     dword ptr [rax+rax+00h]
0x1402532dd  mov     ebx, eax
0x1402532df  test    eax, eax
0x1402532e1  jns     short loc_14025330E
0x1402532e3  mov     r10, cs:WPP_GLOBAL_Control
0x1402532ea  lea     rcx, WPP_GLOBAL_Control
0x1402532f1  cmp     r10, rcx
0x1402532f4  jz      short loc_140253373
0x1402532f6  cmp     byte ptr [r10+29h], 2
0x1402532fb  jb      short loc_140253373
0x1402532fd  test    dword ptr [r10+2Ch], 40000h
0x140253305  jz      short loc_140253373
0x140253307  mov     edx, 15h
0x14025330c  jmp     short loc_140253360
0x14025330e  mov     rax, cs:__imp_SeExports
0x140253315  xor     r8d, r8d; OwnerDefaulted
0x140253318  mov     rcx, rbp; SecurityDescriptor
0x14025331b  mov     rdx, [rax]
0x14025331e  mov     rdx, [rdx+108h]; Owner
0x140253325  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x14025332c  nop     dword ptr [rax+rax+00h]
0x140253331  mov     ebx, eax
0x140253333  test    eax, eax
0x140253335  jns     short loc_14025338C
0x140253337  mov     r10, cs:WPP_GLOBAL_Control
0x14025333e  lea     rcx, WPP_GLOBAL_Control
0x140253345  cmp     r10, rcx
0x140253348  jz      short loc_140253373
0x14025334a  cmp     byte ptr [r10+29h], 2
0x14025334f  jb      short loc_140253373
0x140253351  test    dword ptr [r10+2Ch], 40000h
0x140253359  jz      short loc_140253373
0x14025335b  mov     edx, 16h
0x140253360  mov     rcx, [r10+18h]
0x140253364  mov     r9d, eax
0x140253367  lea     r8, WPP_ac6ac8075c54330b91caa815a7f3d563_Traceguids
0x14025336e  call    WPP_SF_d
0x140253373  mov     edx, 78535145h; Tag
0x140253378  mov     rcx, rsi; P
0x14025337b  call    cs:__imp_ExFreePoolWithTag
0x140253382  nop     dword ptr [rax+rax+00h]
0x140253387  jmp     loc_14025311E
0x14025338c  xor     eax, eax
0x14025338e  add     rsp, 38h
0x140253392  pop     r15
0x140253394  pop     r14
0x140253396  pop     rdi
0x140253397  pop     rsi
0x140253398  pop     rbp
0x140253399  pop     rbx
0x14025339a  retn
```
