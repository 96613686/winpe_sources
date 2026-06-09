# SrvAdminDuplicateSecurityDescriptor

- ea: `0x1400073d0`
- end: `0x140007678`
- name: `SrvAdminDuplicateSecurityDescriptor`
- size: `680`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR AbsoluteSecurityDescriptor)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140005570`
- `0x140025b80`

## callees

- `0x140007360`
- `0x1400073d0`
- `0x140007c60`
- `0x14001389c`
- `0x140015790`
- `0x14002a540`

## import_xrefs

- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140007408`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140007408`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x14000751d`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x14002b9bd`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x14000751d`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x14002b9bd`
- `ntoskrnl!RtlValidSecurityDescriptor` at `0x14000744c`
- `ntoskrnl!RtlValidSecurityDescriptor` at `0x14000744c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400074e6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000754a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000757b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400074e6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000754a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000757b`

## pseudocode

```c
__int64 __fastcall SrvAdminDuplicateSecurityDescriptor(
        PSECURITY_DESCRIPTOR AbsoluteSecurityDescriptor,
        void **a2,
        ULONG a3,
        char a4)
{
  ULONG v8; // eax
  unsigned int *PoolWithTag; // rdi
  PDEVICE_OBJECT v11; // rcx
  unsigned int *v12; // rax
  NTSTATUS v13; // r14d
  __int64 v14; // rdx
  ULONG BufferLength; // [rsp+40h] [rbp+8h] BYREF

  BufferLength = 0;
  if ( !AbsoluteSecurityDescriptor || !a2 )
    return 3221225485LL;
  v8 = RtlLengthSecurityDescriptor(AbsoluteSecurityDescriptor);
  BufferLength = v8;
  if ( !v8 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      return 3221225593LL;
    }
    v14 = 10;
    goto LABEL_57;
  }
  if ( a4 )
  {
    PoolWithTag = (unsigned int *)SrvNetAllocatePoolWithTag(258, v8, 1684095315);
    if ( !PoolWithTag )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_caccdeee60b838064f6bc98cb49b4557_Traceguids);
      }
      return 3221225626LL;
    }
    v8 = BufferLength;
  }
  else
  {
    if ( v8 > a3 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_caccdeee60b838064f6bc98cb49b4557_Traceguids);
      }
      return 3221225507LL;
    }
    PoolWithTag = (unsigned int *)*a2;
  }
  if ( *((__int16 *)AbsoluteSecurityDescriptor + 1) < 0 )
  {
    memmove(PoolWithTag, AbsoluteSecurityDescriptor, v8);
LABEL_9:
    if ( RtlValidSecurityDescriptor(PoolWithTag) )
    {
      *a2 = PoolWithTag;
      return 0;
    }
    if ( a4 && PoolWithTag )
    {
      SrvNetUpdateMemStatistics(*(PoolWithTag - 3), *(PoolWithTag - 4), 0);
      ExFreePoolWithTag(PoolWithTag - 4, 0);
    }
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      return 3221225593LL;
    }
    v14 = 15;
LABEL_57:
    WPP_SF_(v11->AttachedDevice, v14, WPP_caccdeee60b838064f6bc98cb49b4557_Traceguids);
    return 3221225593LL;
  }
  v13 = RtlAbsoluteToSelfRelativeSD(AbsoluteSecurityDescriptor, PoolWithTag, &BufferLength);
  if ( v13 == -1073741789 )
  {
    if ( !a4 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_caccdeee60b838064f6bc98cb49b4557_Traceguids, BufferLength);
      }
      return 3221225507LL;
    }
    if ( PoolWithTag )
    {
      SrvNetUpdateMemStatistics(*(PoolWithTag - 3), *(PoolWithTag - 4), 0);
      ExFreePoolWithTag(PoolWithTag - 4, 0);
    }
    v12 = (unsigned int *)SrvNetAllocatePoolWithTag(258, BufferLength, 1684095315);
    PoolWithTag = v12;
    if ( v12 )
    {
      v13 = RtlAbsoluteToSelfRelativeSD(AbsoluteSecurityDescriptor, v12, &BufferLength);
      goto LABEL_50;
    }
    return 3221225626LL;
  }
LABEL_50:
  if ( v13 >= 0 )
    goto LABEL_9;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_caccdeee60b838064f6bc98cb49b4557_Traceguids, (unsigned int)v13);
  }
  if ( a4 && PoolWithTag )
  {
    SrvNetUpdateMemStatistics(*(PoolWithTag - 3), *(PoolWithTag - 4), 0);
    ExFreePoolWithTag(PoolWithTag - 4, 0);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1400073d0  mov     [rsp+arg_10], rbx
0x1400073d5  push    rbp
0x1400073d6  push    rsi
0x1400073d7  push    rdi
0x1400073d8  sub     rsp, 20h
0x1400073dc  mov     [rsp+38h+BufferLength], 0
0x1400073e4  movzx   ebp, r9b
0x1400073e8  mov     edi, r8d
0x1400073eb  mov     rsi, rdx
0x1400073ee  mov     rbx, rcx
0x1400073f1  test    rcx, rcx
0x1400073f4  jz      loc_14000749C
0x1400073fa  test    rdx, rdx
0x1400073fd  jz      loc_14000749C
0x140007403  mov     [rsp+38h+arg_8], r14
0x140007408  call    cs:__imp_RtlLengthSecurityDescriptor
0x14000740f  nop     dword ptr [rax+rax+00h]
0x140007414  mov     [rsp+38h+BufferLength], eax
0x140007418  test    eax, eax
0x14000741a  jz      loc_1400074AF
0x140007420  test    bpl, bpl
0x140007423  jnz     short loc_140007478
0x140007425  cmp     eax, edi
0x140007427  ja      loc_1400075F2
0x14000742d  mov     rdi, [rsi]
0x140007430  cmp     word ptr [rbx+2], 0
0x140007435  jge     loc_14002B9B2
0x14000743b  mov     r8d, eax; Size
0x14000743e  mov     rdx, rbx; Src
0x140007441  mov     rcx, rdi; void *
0x140007444  call    memmove
0x140007449  mov     rcx, rdi; SecurityDescriptor
0x14000744c  call    cs:__imp_RtlValidSecurityDescriptor
0x140007453  nop     dword ptr [rax+rax+00h]
0x140007458  test    al, al
0x14000745a  jz      loc_140007639
0x140007460  mov     [rsi], rdi
0x140007463  xor     eax, eax
0x140007465  mov     r14, [rsp+38h+arg_8]
0x14000746a  mov     rbx, [rsp+38h+arg_10]
0x14000746f  add     rsp, 20h
0x140007473  pop     rdi
0x140007474  pop     rsi
0x140007475  pop     rbp
0x140007476  retn
0x140007478  mov     edx, eax
0x14000747a  mov     ecx, 102h
0x14000747f  mov     r8d, 64614153h
0x140007485  call    SrvNetAllocatePoolWithTag
0x14000748a  mov     rdi, rax
0x14000748d  test    rax, rax
0x140007490  jz      loc_1400075AB
0x140007496  mov     eax, [rsp+38h+BufferLength]
0x14000749a  jmp     short loc_140007430
0x14000749c  mov     rbx, [rsp+38h+arg_10]
0x1400074a1  mov     eax, 0C000000Dh
0x1400074a6  add     rsp, 20h
0x1400074aa  pop     rdi
0x1400074ab  pop     rsi
0x1400074ac  pop     rbp
0x1400074ad  retn
0x1400074af  mov     rcx, cs:WPP_GLOBAL_Control
0x1400074b6  lea     rax, WPP_GLOBAL_Control
0x1400074bd  cmp     rcx, rax
0x1400074c0  jnz     loc_14000758C
0x1400074c6  mov     eax, 0C0000079h
0x1400074cb  jmp     short loc_140007465
0x1400074cd  test    rdi, rdi
0x1400074d0  jz      short loc_1400074F2
0x1400074d2  mov     ecx, [rdi-0Ch]
0x1400074d5  xor     r8d, r8d
0x1400074d8  mov     edx, [rdi-10h]
0x1400074db  call    SrvNetUpdateMemStatistics
0x1400074e0  xor     edx, edx; Tag
0x1400074e2  lea     rcx, [rdi-10h]; P
0x1400074e6  call    cs:__imp_ExFreePoolWithTag
0x1400074ed  nop     dword ptr [rax+rax+00h]
0x1400074f2  mov     edx, [rsp+38h+BufferLength]
0x1400074f6  mov     ecx, 102h
0x1400074fb  mov     r8d, 64614153h
0x140007501  call    SrvNetAllocatePoolWithTag
0x140007506  mov     rdi, rax
0x140007509  test    rax, rax
0x14000750c  jz      loc_14002BA21
0x140007512  lea     r8, [rsp+38h+BufferLength]; BufferLength
0x140007517  mov     rdx, rax; SelfRelativeSecurityDescriptor
0x14000751a  mov     rcx, rbx; AbsoluteSecurityDescriptor
0x14000751d  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x140007524  nop     dword ptr [rax+rax+00h]
0x140007529  mov     r14d, eax
0x14000752c  jmp     loc_14002BA2B
0x140007531  test    rdi, rdi
0x140007534  jz      short loc_140007556
0x140007536  mov     ecx, [rdi-0Ch]
0x140007539  xor     r8d, r8d
0x14000753c  mov     edx, [rdi-10h]
0x14000753f  call    SrvNetUpdateMemStatistics
0x140007544  xor     edx, edx; Tag
0x140007546  lea     rcx, [rdi-10h]; P
0x14000754a  call    cs:__imp_ExFreePoolWithTag
0x140007551  nop     dword ptr [rax+rax+00h]
0x140007556  mov     eax, r14d
0x140007559  jmp     loc_140007465
0x14000755e  test    rdi, rdi
0x140007561  jz      loc_140007642
0x140007567  mov     ecx, [rdi-0Ch]
0x14000756a  xor     r8d, r8d
0x14000756d  mov     edx, [rdi-10h]
0x140007570  call    SrvNetUpdateMemStatistics
0x140007575  xor     edx, edx; Tag
0x140007577  lea     rcx, [rdi-10h]; P
0x14000757b  call    cs:__imp_ExFreePoolWithTag
0x140007582  nop     dword ptr [rax+rax+00h]
0x140007587  jmp     loc_140007642
0x14000758c  mov     eax, [rcx+2Ch]
0x14000758f  test    al, 20h
0x140007591  jz      loc_1400074C6
0x140007597  cmp     byte ptr [rcx+29h], 1
0x14000759b  jb      loc_1400074C6
0x1400075a1  mov     edx, 0Ah
0x1400075a6  jmp     loc_14002BA7A
0x1400075ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400075b2  lea     rax, WPP_GLOBAL_Control
0x1400075b9  cmp     rcx, rax
0x1400075bc  jz      loc_14002BA21
0x1400075c2  mov     eax, [rcx+2Ch]
0x1400075c5  test    al, 20h
0x1400075c7  jz      loc_14002BA21
0x1400075cd  cmp     byte ptr [rcx+29h], 1
0x1400075d1  jb      loc_14002BA21
0x1400075d7  mov     rcx, [rcx+18h]
0x1400075db  lea     r8, WPP_caccdeee60b838064f6bc98cb49b4557_Traceguids
0x1400075e2  mov     edx, 0Bh
0x1400075e7  call    WPP_SF_
0x1400075ec  nop
0x1400075ed  jmp     loc_14002BA21
0x1400075f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400075f9  lea     rax, WPP_GLOBAL_Control
0x140007600  cmp     rcx, rax
0x140007603  jz      loc_14002BA17
0x140007609  mov     eax, [rcx+2Ch]
0x14000760c  test    al, 20h
0x14000760e  jz      loc_14002BA17
0x140007614  cmp     byte ptr [rcx+29h], 1
0x140007618  jb      loc_14002BA17
0x14000761e  mov     rcx, [rcx+18h]
0x140007622  lea     r8, WPP_caccdeee60b838064f6bc98cb49b4557_Traceguids
0x140007629  mov     edx, 0Ch
0x14000762e  call    WPP_SF_
0x140007633  nop
0x140007634  jmp     loc_14002BA17
0x140007639  test    bpl, bpl
0x14000763c  jnz     loc_14000755E
0x140007642  mov     rcx, cs:WPP_GLOBAL_Control
0x140007649  lea     rax, WPP_GLOBAL_Control
0x140007650  cmp     rcx, rax
0x140007653  jz      loc_1400074C6
0x140007659  mov     eax, [rcx+2Ch]
0x14000765c  test    al, 20h
0x14000765e  jz      loc_1400074C6
0x140007664  cmp     byte ptr [rcx+29h], 1
0x140007668  jb      loc_1400074C6
0x14000766e  mov     edx, 0Fh
0x140007673  jmp     loc_14002BA7A
0x14002b9b2  lea     r8, [rsp+38h+BufferLength]; BufferLength
0x14002b9b7  mov     rdx, rdi; SelfRelativeSecurityDescriptor
0x14002b9ba  mov     rcx, rbx; AbsoluteSecurityDescriptor
0x14002b9bd  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x14002b9c4  nop     dword ptr [rax+rax+00h]
0x14002b9c9  mov     r14d, eax
0x14002b9cc  cmp     eax, 0C0000023h
0x14002b9d1  jnz     short loc_14002BA2B
0x14002b9d3  test    bpl, bpl
0x14002b9d6  jnz     loc_1400074CD
0x14002b9dc  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b9e3  lea     rax, WPP_GLOBAL_Control
0x14002b9ea  cmp     rcx, rax
0x14002b9ed  jz      short loc_14002BA17
0x14002b9ef  mov     edx, [rcx+2Ch]
0x14002b9f2  test    dl, 20h
0x14002b9f5  jz      short loc_14002BA17
0x14002b9f7  cmp     byte ptr [rcx+29h], 1
0x14002b9fb  jb      short loc_14002BA17
0x14002b9fd  mov     r9d, [rsp+38h+BufferLength]
0x14002ba02  lea     r8, WPP_caccdeee60b838064f6bc98cb49b4557_Traceguids
0x14002ba09  mov     rcx, [rcx+18h]
0x14002ba0d  mov     edx, 0Dh
0x14002ba12  call    WPP_SF_d
0x14002ba17  mov     eax, 0C0000023h
0x14002ba1c  jmp     loc_140007465
0x14002ba21  mov     eax, 0C000009Ah
0x14002ba26  jmp     loc_140007465
0x14002ba2b  test    r14d, r14d
0x14002ba2e  jns     loc_140007449
0x14002ba34  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ba3b  lea     rax, WPP_GLOBAL_Control
0x14002ba42  cmp     rcx, rax
0x14002ba45  jz      short loc_14002BA6C
0x14002ba47  mov     eax, [rcx+2Ch]
0x14002ba4a  test    al, 20h
0x14002ba4c  jz      short loc_14002BA6C
0x14002ba4e  cmp     byte ptr [rcx+29h], 1
0x14002ba52  jb      short loc_14002BA6C
0x14002ba54  mov     rcx, [rcx+18h]
0x14002ba58  lea     r8, WPP_caccdeee60b838064f6bc98cb49b4557_Traceguids
0x14002ba5f  mov     edx, 0Eh
0x14002ba64  mov     r9d, r14d
0x14002ba67  call    WPP_SF_d
0x14002ba6c  test    bpl, bpl
0x14002ba6f  jz      loc_140007556
0x14002ba75  jmp     loc_140007531
0x14002ba7a  mov     rcx, [rcx+18h]
0x14002ba7e  lea     r8, WPP_caccdeee60b838064f6bc98cb49b4557_Traceguids
0x14002ba85  call    WPP_SF_
0x14002ba8a  nop
0x14002ba8b  jmp     loc_1400074C6
```
