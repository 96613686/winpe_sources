# EQoSCreateSecurityDescriptor

- ea: `0x14024f0b4`
- end: `0x14024f39c`
- name: `EQoSCreateSecurityDescriptor`
- size: `744`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14025a25c`

## callees

- `0x14009a4fc`
- `0x14010e278`
- `0x140152960`
- `0x14024f0b4`

## import_xrefs

- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14024f2d1`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14024f2d1`
- `ntoskrnl!RtlCreateAcl` at `0x14024f1b8`
- `ntoskrnl!RtlCreateAcl` at `0x14024f1b8`
- `ntoskrnl!RtlLengthSid` at `0x14024f137`
- `ntoskrnl!RtlLengthSid` at `0x14024f137`
- `ntoskrnl!SeExports` at `0x14024f30e`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14024f0d0`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14024f0d0`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14024f209`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14024f209`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x14024f325`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x14024f325`
- `ntoskrnl!RtlMapGenericMask` at `0x14024f23e`
- `ntoskrnl!RtlMapGenericMask` at `0x14024f23e`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14024f25f`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14024f25f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024f37b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024f37b`

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
0x14024f0b4  mov     [rsp+AccessMask], r8d
0x14024f0b9  push    rbx
0x14024f0ba  push    rbp
0x14024f0bb  push    rsi
0x14024f0bc  push    rdi
0x14024f0bd  push    r14
0x14024f0bf  push    r15
0x14024f0c1  sub     rsp, 38h
0x14024f0c5  mov     r14, rdx
0x14024f0c8  mov     rbp, rcx
0x14024f0cb  mov     edx, 1; Revision
0x14024f0d0  call    cs:__imp_RtlCreateSecurityDescriptor
0x14024f0d7  nop     dword ptr [rax+rax+00h]
0x14024f0dc  mov     ebx, eax
0x14024f0de  test    eax, eax
0x14024f0e0  jns     short loc_14024F125
0x14024f0e2  mov     r10, cs:WPP_GLOBAL_Control
0x14024f0e9  lea     rcx, WPP_GLOBAL_Control
0x14024f0f0  cmp     r10, rcx
0x14024f0f3  jz      short loc_14024F11E
0x14024f0f5  cmp     byte ptr [r10+29h], 2
0x14024f0fa  jb      short loc_14024F11E
0x14024f0fc  test    dword ptr [r10+2Ch], 40000h
0x14024f104  jz      short loc_14024F11E
0x14024f106  mov     rcx, [r10+18h]
0x14024f10a  lea     r8, WPP_ac6ac8075c54330b91caa815a7f3d563_Traceguids
0x14024f111  mov     edx, 11h
0x14024f116  mov     r9d, eax
0x14024f119  call    WPP_SF_d
0x14024f11e  mov     eax, ebx
0x14024f120  jmp     loc_14024F38E
0x14024f125  mov     ebx, 8
0x14024f12a  xor     edi, edi
0x14024f12c  mov     rcx, rdi
0x14024f12f  add     rcx, rcx
0x14024f132  mov     rcx, [r14+rcx*8+8]; Sid
0x14024f137  call    cs:__imp_RtlLengthSid
0x14024f13e  nop     dword ptr [rax+rax+00h]
0x14024f143  add     ebx, 8
0x14024f146  inc     rdi
0x14024f149  add     ebx, eax
0x14024f14b  cmp     rdi, 5
0x14024f14f  jnz     short loc_14024F12C
0x14024f151  mov     edx, ebx
0x14024f153  lea     ecx, [rdi+3Bh]
0x14024f156  mov     r8d, 78535145h
0x14024f15c  call    EQoSAllocatePoolWithTagPriority
0x14024f161  mov     rsi, rax
0x14024f164  test    rax, rax
0x14024f167  jnz     short loc_14024F1AD
0x14024f169  mov     r10, cs:WPP_GLOBAL_Control
0x14024f170  lea     rcx, WPP_GLOBAL_Control
0x14024f177  cmp     r10, rcx
0x14024f17a  jz      short loc_14024F1A3
0x14024f17c  cmp     byte ptr [r10+29h], 2
0x14024f181  jb      short loc_14024F1A3
0x14024f183  test    dword ptr [r10+2Ch], 40000h
0x14024f18b  jz      short loc_14024F1A3
0x14024f18d  mov     rcx, [r10+18h]
0x14024f191  lea     edx, [rdi+0Dh]
0x14024f194  mov     r9d, ebx
0x14024f197  lea     r8, WPP_ac6ac8075c54330b91caa815a7f3d563_Traceguids
0x14024f19e  call    WPP_SF_d
0x14024f1a3  mov     eax, 0C000009Ah
0x14024f1a8  jmp     loc_14024F38E
0x14024f1ad  mov     r8d, 2; AclRevision
0x14024f1b3  mov     edx, ebx; AclLength
0x14024f1b5  mov     rcx, rsi; Acl
0x14024f1b8  call    cs:__imp_RtlCreateAcl
0x14024f1bf  nop     dword ptr [rax+rax+00h]
0x14024f1c4  mov     ebx, eax
0x14024f1c6  test    eax, eax
0x14024f1c8  jns     short loc_14024F209
0x14024f1ca  mov     rax, cs:WPP_GLOBAL_Control
0x14024f1d1  lea     rcx, WPP_GLOBAL_Control
0x14024f1d8  cmp     rax, rcx
0x14024f1db  jz      loc_14024F373
0x14024f1e1  cmp     byte ptr [rax+29h], 2
0x14024f1e5  jb      loc_14024F373
0x14024f1eb  test    dword ptr [rax+2Ch], 40000h
0x14024f1f2  jz      loc_14024F373
0x14024f1f8  mov     rcx, [rax+18h]
0x14024f1fc  mov     edx, 13h
0x14024f201  mov     r9d, ebx
0x14024f204  jmp     loc_14024F367
0x14024f209  call    cs:__imp_IoGetFileObjectGenericMapping
0x14024f210  nop     dword ptr [rax+rax+00h]
0x14024f215  mov     r15, rax
0x14024f218  xor     edi, edi
0x14024f21a  cmp     edi, 5
0x14024f21d  jnb     loc_14024F2C6
0x14024f223  mov     ebx, edi
0x14024f225  mov     rdx, r15; GenericMapping
0x14024f228  add     rbx, rbx
0x14024f22b  mov     ecx, [r14+rbx*8]
0x14024f22f  mov     [rsp+68h+AccessMask], ecx
0x14024f236  lea     rcx, [rsp+68h+AccessMask]; AccessMask
0x14024f23e  call    cs:__imp_RtlMapGenericMask
0x14024f245  nop     dword ptr [rax+rax+00h]
0x14024f24a  mov     r9, [r14+rbx*8+8]; Sid
0x14024f24f  mov     edx, 2; AceRevision
0x14024f254  mov     r8d, [rsp+68h+AccessMask]; AccessMask
0x14024f25c  mov     rcx, rsi; Acl
0x14024f25f  call    cs:__imp_RtlAddAccessAllowedAce
0x14024f266  nop     dword ptr [rax+rax+00h]
0x14024f26b  mov     ebx, eax
0x14024f26d  test    eax, eax
0x14024f26f  js      short loc_14024F275
0x14024f271  inc     edi
0x14024f273  jmp     short loc_14024F21A
0x14024f275  mov     r10, cs:WPP_GLOBAL_Control
0x14024f27c  lea     rcx, WPP_GLOBAL_Control
0x14024f283  cmp     r10, rcx
0x14024f286  jz      loc_14024F373
0x14024f28c  cmp     byte ptr [r10+29h], 2
0x14024f291  jb      loc_14024F373
0x14024f297  test    dword ptr [r10+2Ch], 40000h
0x14024f29f  jz      loc_14024F373
0x14024f2a5  mov     rcx, [r10+18h]
0x14024f2a9  lea     r8, WPP_ac6ac8075c54330b91caa815a7f3d563_Traceguids
0x14024f2b0  mov     edx, 14h
0x14024f2b5  mov     [rsp+68h+var_48], eax
0x14024f2b9  mov     r9d, edi
0x14024f2bc  call    WPP_SF_Dd
0x14024f2c1  jmp     loc_14024F373
0x14024f2c6  xor     r9d, r9d; DaclDefaulted
0x14024f2c9  mov     r8, rsi; Dacl
0x14024f2cc  mov     dl, 1; DaclPresent
0x14024f2ce  mov     rcx, rbp; SecurityDescriptor
0x14024f2d1  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14024f2d8  nop     dword ptr [rax+rax+00h]
0x14024f2dd  mov     ebx, eax
0x14024f2df  test    eax, eax
0x14024f2e1  jns     short loc_14024F30E
0x14024f2e3  mov     r10, cs:WPP_GLOBAL_Control
0x14024f2ea  lea     rcx, WPP_GLOBAL_Control
0x14024f2f1  cmp     r10, rcx
0x14024f2f4  jz      short loc_14024F373
0x14024f2f6  cmp     byte ptr [r10+29h], 2
0x14024f2fb  jb      short loc_14024F373
0x14024f2fd  test    dword ptr [r10+2Ch], 40000h
0x14024f305  jz      short loc_14024F373
0x14024f307  mov     edx, 15h
0x14024f30c  jmp     short loc_14024F360
0x14024f30e  mov     rax, cs:__imp_SeExports
0x14024f315  xor     r8d, r8d; OwnerDefaulted
0x14024f318  mov     rcx, rbp; SecurityDescriptor
0x14024f31b  mov     rdx, [rax]
0x14024f31e  mov     rdx, [rdx+108h]; Owner
0x14024f325  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x14024f32c  nop     dword ptr [rax+rax+00h]
0x14024f331  mov     ebx, eax
0x14024f333  test    eax, eax
0x14024f335  jns     short loc_14024F38C
0x14024f337  mov     r10, cs:WPP_GLOBAL_Control
0x14024f33e  lea     rcx, WPP_GLOBAL_Control
0x14024f345  cmp     r10, rcx
0x14024f348  jz      short loc_14024F373
0x14024f34a  cmp     byte ptr [r10+29h], 2
0x14024f34f  jb      short loc_14024F373
0x14024f351  test    dword ptr [r10+2Ch], 40000h
0x14024f359  jz      short loc_14024F373
0x14024f35b  mov     edx, 16h
0x14024f360  mov     rcx, [r10+18h]
0x14024f364  mov     r9d, eax
0x14024f367  lea     r8, WPP_ac6ac8075c54330b91caa815a7f3d563_Traceguids
0x14024f36e  call    WPP_SF_d
0x14024f373  mov     edx, 78535145h; Tag
0x14024f378  mov     rcx, rsi; P
0x14024f37b  call    cs:__imp_ExFreePoolWithTag
0x14024f382  nop     dword ptr [rax+rax+00h]
0x14024f387  jmp     loc_14024F11E
0x14024f38c  xor     eax, eax
0x14024f38e  add     rsp, 38h
0x14024f392  pop     r15
0x14024f394  pop     r14
0x14024f396  pop     rdi
0x14024f397  pop     rsi
0x14024f398  pop     rbp
0x14024f399  pop     rbx
0x14024f39a  retn
```
