# WfpAleGetServiceSidsFromToken

- ea: `0x1400c4bb0`
- end: `0x1400c4fd8`
- name: `WfpAleGetServiceSidsFromToken`
- size: `1064`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task`

## callers

- `0x1400c4750`

## callees

- `0x140014a90`
- `0x1400ad6a0`
- `0x1400c4504`
- `0x1400c4bb0`
- `0x1400e4120`
- `0x1401c1580`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400c4e6d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400c4e6d`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x1400c4df8`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x1400c4e4f`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x1400c4df8`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x1400c4e4f`
- `ntoskrnl!RtlValidSid` at `0x1400c4c78`
- `ntoskrnl!RtlValidSid` at `0x1400c4d3c`
- `ntoskrnl!RtlValidSid` at `0x1400c4c78`
- `ntoskrnl!RtlValidSid` at `0x1400c4d3c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400c4bf1`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400c4bf1`
- `ntoskrnl!RtlSubAuthorityCountSid` at `0x1400c4c8b`
- `ntoskrnl!RtlSubAuthorityCountSid` at `0x1400c4d4f`
- `ntoskrnl!RtlSubAuthorityCountSid` at `0x1400c4c8b`
- `ntoskrnl!RtlSubAuthorityCountSid` at `0x1400c4d4f`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400c4ca1`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400c4d65`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400c4ca1`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400c4d65`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c4dd7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c4dd7`
- `ntoskrnl!ExAllocatePool2` at `0x1400c4c18`
- `ntoskrnl!ExAllocatePool2` at `0x1400c4ce4`
- `ntoskrnl!ExAllocatePool2` at `0x1400c4c18`
- `ntoskrnl!ExAllocatePool2` at `0x1400c4ce4`

## string_xrefs

- `0x1400c4d81`: `RtlConvertSidToUnicodeString`

## pseudocode

```c
__int64 __fastcall WfpAleGetServiceSidsFromToken(__int64 a1)
{
  struct _UNICODE_STRING *v2; // r13
  __int64 v3; // rsi
  __int64 v4; // rbp
  __int64 v5; // rcx
  int v6; // r12d
  int v7; // r15d
  unsigned __int16 v8; // r14
  __int64 v9; // rcx
  unsigned int i; // ebx
  void *v11; // rdi
  __int64 v12; // rcx
  unsigned int j; // ebx
  void *v14; // rdi
  __int64 v15; // r8
  const char *v16; // rdx
  unsigned int v18; // eax
  int Length; // eax
  unsigned int appended; // eax
  unsigned int v21; // eax
  __int64 v22; // rax
  struct _UNICODE_STRING Destination; // [rsp+30h] [rbp-48h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+40h] [rbp-38h] BYREF

  v2 = (struct _UNICODE_STRING *)(a1 + 208);
  Destination = 0;
  UnicodeString = 0;
  RtlInitUnicodeString((PUNICODE_STRING)(a1 + 208), 0);
  v3 = *(_QWORD *)(a1 + 224);
  v4 = 0;
  UnicodeString.Buffer = (PWSTR)ExAllocatePool2(64, 130, 1400073281);
  if ( !UnicodeString.Buffer )
  {
    v22 = WfpReportSysErrorAsNtStatus(v5, "ExAllocatePool2", 3221225495LL);
    v4 = v22;
    if ( v22 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
      {
        WPP_SF_sd(
          WPP_GLOBAL_Control->AttachedDevice,
          15,
          (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
          (unsigned int)"WfpPoolAllocNonPaged",
          v22);
        goto LABEL_21;
      }
    }
  }
  if ( v4 )
    goto LABEL_21;
  v6 = 1;
  v7 = 1;
  v8 = 0;
  memset(UnicodeString.Buffer, 0, 0x82u);
  UnicodeString.MaximumLength = 130;
  for ( i = 0; i < *(_DWORD *)v3; ++i )
  {
    v11 = *(void **)(*(_QWORD *)(v3 + 8) + 16LL * i);
    if ( RtlValidSid(v11) && *RtlSubAuthorityCountSid(v11) && *RtlSubAuthoritySid(v11, 0) == 80 )
    {
      v18 = RtlConvertSidToUnicodeString(&UnicodeString, v11, 0);
      if ( v18 )
      {
LABEL_19:
        v15 = v18;
        v16 = "RtlConvertSidToUnicodeString";
        goto LABEL_20;
      }
      Length = UnicodeString.Length;
      LOWORD(Length) = v8 + UnicodeString.Length;
      if ( (unsigned __int16)(v8 + UnicodeString.Length) < v8 )
        goto LABEL_35;
      if ( v7 )
      {
        v8 += UnicodeString.Length;
        UnicodeString.Length = 0;
        v7 = 0;
      }
      else
      {
        v9 = (unsigned int)(Length + 2);
        if ( (unsigned __int16)(Length + 2) < (unsigned __int16)Length )
          goto LABEL_35;
        v8 = Length + 2;
        UnicodeString.Length = 0;
        v7 = 0;
      }
    }
  }
  if ( !v8 )
    goto LABEL_21;
  if ( (unsigned __int16)(v8 + 2) < v8 )
  {
LABEL_35:
    v15 = 3221225621LL;
    v16 = "RtlUShortAdd";
    goto LABEL_20;
  }
  v4 = 0;
  Destination.Buffer = (PWSTR)ExAllocatePool2(64, (unsigned __int16)(v8 + 2), 1400073281);
  if ( !Destination.Buffer )
  {
    v4 = WfpReportSysErrorAsNtStatus(v12, "ExAllocatePool2", 3221225495LL);
    if ( v4 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
      {
        WPP_SF_sd(
          WPP_GLOBAL_Control->AttachedDevice,
          15,
          (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
          (unsigned int)"WfpPoolAllocNonPaged",
          v4);
        goto LABEL_21;
      }
    }
  }
  if ( v4 )
    goto LABEL_21;
  memset(Destination.Buffer, 0, (unsigned __int16)(v8 + 2));
  Destination.MaximumLength = v8 + 2;
  Destination.Length = 0;
  for ( j = 0; ; ++j )
  {
    if ( j >= *(_DWORD *)v3 )
    {
      *v2 = Destination;
      goto LABEL_34;
    }
    v14 = *(void **)(*(_QWORD *)(v3 + 8) + 16LL * j);
    if ( !RtlValidSid(v14) || !*RtlSubAuthorityCountSid(v14) || *RtlSubAuthoritySid(v14, 0) != 80 )
      continue;
    if ( !v6 )
    {
      v21 = RtlUnicodeStringCatString(&Destination, L",");
      if ( v21 )
        break;
    }
    v18 = RtlConvertSidToUnicodeString(&UnicodeString, v14, 0);
    if ( v18 )
      goto LABEL_19;
    appended = RtlAppendUnicodeStringToString(&Destination, &UnicodeString);
    v9 = 0;
    UnicodeString.Length = 0;
    if ( appended )
    {
      v15 = appended;
      v16 = "RtlAppendUnicodeStringToString";
      goto LABEL_20;
    }
    v6 = 0;
  }
  v15 = v21;
  v16 = "RtlUnicodeStringCatString";
LABEL_20:
  v4 = WfpReportSysErrorAsNtStatus(v9, v16, v15);
LABEL_21:
  if ( Destination.Buffer )
  {
    WfpNamedPoolFree(0x53736C41u);
LABEL_34:
    Destination.Buffer = 0;
  }
  if ( UnicodeString.Buffer )
    ExFreePoolWithTag(UnicodeString.Buffer, 0x53736C41u);
  return v4;
}

```

## disassembly

```asm
0x1400c4bb0  mov     rax, rsp
0x1400c4bb3  push    rbp
0x1400c4bb4  sub     rsp, 70h
0x1400c4bb8  mov     [rax+8], rbx
0x1400c4bbc  xorps   xmm0, xmm0
0x1400c4bbf  mov     [rax+10h], rsi
0x1400c4bc3  mov     rbx, rcx
0x1400c4bc6  mov     [rax+18h], rdi
0x1400c4bca  xorps   xmm1, xmm1
0x1400c4bcd  mov     [rax-10h], r12
0x1400c4bd1  xor     edx, edx; SourceString
0x1400c4bd3  mov     [rax-18h], r13
0x1400c4bd7  lea     r13, [rcx+0D0h]
0x1400c4bde  mov     [rax-20h], r14
0x1400c4be2  mov     rcx, r13; DestinationString
0x1400c4be5  mov     [rax-28h], r15
0x1400c4be9  movups  xmmword ptr [rax-48h], xmm0
0x1400c4bed  movups  xmmword ptr [rax-38h], xmm1
0x1400c4bf1  call    cs:__imp_RtlInitUnicodeString
0x1400c4bf8  nop     dword ptr [rax+rax+00h]
0x1400c4bfd  mov     rsi, [rbx+0E0h]
0x1400c4c04  mov     r8d, 53736C41h
0x1400c4c0a  mov     ebx, 82h
0x1400c4c0f  mov     ecx, 40h ; '@'
0x1400c4c14  mov     edx, ebx
0x1400c4c16  xor     ebp, ebp
0x1400c4c18  call    cs:__imp_ExAllocatePool2
0x1400c4c1f  nop     dword ptr [rax+rax+00h]
0x1400c4c24  mov     [rsp+78h+UnicodeString.Buffer], rax
0x1400c4c29  lea     rdi, WPP_GLOBAL_Control
0x1400c4c30  test    rax, rax
0x1400c4c33  jz      loc_1400C4F08
0x1400c4c39  test    rbp, rbp
0x1400c4c3c  jnz     loc_1400C4D90
0x1400c4c42  mov     rcx, [rsp+78h+UnicodeString.Buffer]; void *
0x1400c4c47  mov     r12d, 1
0x1400c4c4d  mov     r8, rbx; Size
0x1400c4c50  xor     edx, edx; Val
0x1400c4c52  mov     r15d, r12d
0x1400c4c55  xor     r14d, r14d
0x1400c4c58  call    memset
0x1400c4c5d  mov     [rsp+78h+UnicodeString.MaximumLength], bx
0x1400c4c62  xor     ebx, ebx
0x1400c4c64  cmp     ebx, [rsi]
0x1400c4c66  jnb     short loc_1400C4CBA
0x1400c4c68  mov     rax, [rsi+8]
0x1400c4c6c  mov     ecx, ebx
0x1400c4c6e  add     rcx, rcx
0x1400c4c71  mov     rdi, [rax+rcx*8]
0x1400c4c75  mov     rcx, rdi; Sid
0x1400c4c78  call    cs:__imp_RtlValidSid
0x1400c4c7f  nop     dword ptr [rax+rax+00h]
0x1400c4c84  test    al, al
0x1400c4c86  jz      short loc_1400C4CB6
0x1400c4c88  mov     rcx, rdi; Sid
0x1400c4c8b  call    cs:__imp_RtlSubAuthorityCountSid
0x1400c4c92  nop     dword ptr [rax+rax+00h]
0x1400c4c97  cmp     byte ptr [rax], 0
0x1400c4c9a  jz      short loc_1400C4CB6
0x1400c4c9c  xor     edx, edx; SubAuthority
0x1400c4c9e  mov     rcx, rdi; Sid
0x1400c4ca1  call    cs:__imp_RtlSubAuthoritySid
0x1400c4ca8  nop     dword ptr [rax+rax+00h]
0x1400c4cad  cmp     dword ptr [rax], 50h ; 'P'
0x1400c4cb0  jz      loc_1400C4DED
0x1400c4cb6  inc     ebx
0x1400c4cb8  jmp     short loc_1400C4C64
0x1400c4cba  test    r14w, r14w
0x1400c4cbe  jz      loc_1400C4D90
0x1400c4cc4  lea     ebx, [r14+2]
0x1400c4cc8  cmp     bx, r14w
0x1400c4ccc  jb      loc_1400C4EA4
0x1400c4cd2  movzx   edi, bx
0x1400c4cd5  mov     r8d, 53736C41h
0x1400c4cdb  mov     edx, edi
0x1400c4cdd  mov     ecx, 40h ; '@'
0x1400c4ce2  xor     ebp, ebp
0x1400c4ce4  call    cs:__imp_ExAllocatePool2
0x1400c4ceb  nop     dword ptr [rax+rax+00h]
0x1400c4cf0  mov     [rsp+78h+Destination.Buffer], rax
0x1400c4cf5  test    rax, rax
0x1400c4cf8  jz      loc_1400C4F72
0x1400c4cfe  test    rbp, rbp
0x1400c4d01  jnz     loc_1400C4D90
0x1400c4d07  mov     rcx, [rsp+78h+Destination.Buffer]; void *
0x1400c4d0c  mov     r8, rdi; Size
0x1400c4d0f  xor     edx, edx; Val
0x1400c4d11  call    memset
0x1400c4d16  xor     eax, eax
0x1400c4d18  mov     [rsp+78h+Destination.MaximumLength], bx
0x1400c4d1d  mov     [rsp+78h+Destination.Length], ax
0x1400c4d22  xor     ebx, ebx
0x1400c4d24  cmp     ebx, [rsi]
0x1400c4d26  jnb     loc_1400C4E8C
0x1400c4d2c  mov     rax, [rsi+8]
0x1400c4d30  mov     ecx, ebx
0x1400c4d32  add     rcx, rcx
0x1400c4d35  mov     rdi, [rax+rcx*8]
0x1400c4d39  mov     rcx, rdi; Sid
0x1400c4d3c  call    cs:__imp_RtlValidSid
0x1400c4d43  nop     dword ptr [rax+rax+00h]
0x1400c4d48  test    al, al
0x1400c4d4a  jz      short loc_1400C4D7A
0x1400c4d4c  mov     rcx, rdi; Sid
0x1400c4d4f  call    cs:__imp_RtlSubAuthorityCountSid
0x1400c4d56  nop     dword ptr [rax+rax+00h]
0x1400c4d5b  cmp     byte ptr [rax], 0
0x1400c4d5e  jz      short loc_1400C4D7A
0x1400c4d60  xor     edx, edx; SubAuthority
0x1400c4d62  mov     rcx, rdi; Sid
0x1400c4d65  call    cs:__imp_RtlSubAuthoritySid
0x1400c4d6c  nop     dword ptr [rax+rax+00h]
0x1400c4d71  cmp     dword ptr [rax], 50h ; 'P'
0x1400c4d74  jz      loc_1400C4E3B
0x1400c4d7a  inc     ebx
0x1400c4d7c  jmp     short loc_1400C4D24
0x1400c4d7e  mov     r8d, eax
0x1400c4d81  lea     rdx, aRtlconvertsidt; "RtlConvertSidToUnicodeString"
0x1400c4d88  call    WfpReportSysErrorAsNtStatus
0x1400c4d8d  mov     rbp, rax
0x1400c4d90  cmp     [rsp+78h+Destination.Buffer], 0
0x1400c4d96  jnz     loc_1400C4FC4
0x1400c4d9c  mov     rcx, [rsp+78h+UnicodeString.Buffer]; P
0x1400c4da1  mov     r15, [rsp+78h+var_28]
0x1400c4da6  mov     r14, [rsp+78h+var_20]
0x1400c4dab  mov     r13, [rsp+78h+var_18]
0x1400c4db0  mov     r12, [rsp+78h+var_10]
0x1400c4db5  mov     rdi, [rsp+78h+arg_10]
0x1400c4dbd  mov     rsi, [rsp+78h+arg_8]
0x1400c4dc5  mov     rbx, [rsp+78h+arg_0]
0x1400c4dcd  test    rcx, rcx
0x1400c4dd0  jz      short loc_1400C4DE3
0x1400c4dd2  mov     edx, 53736C41h; Tag
0x1400c4dd7  call    cs:__imp_ExFreePoolWithTag
0x1400c4dde  nop     dword ptr [rax+rax+00h]
0x1400c4de3  mov     rax, rbp
0x1400c4de6  add     rsp, 70h
0x1400c4dea  pop     rbp
0x1400c4deb  retn
0x1400c4ded  xor     r8d, r8d; AllocateDestinationString
0x1400c4df0  lea     rcx, [rsp+78h+UnicodeString]; UnicodeString
0x1400c4df5  mov     rdx, rdi; Sid
0x1400c4df8  call    cs:__imp_RtlConvertSidToUnicodeString
0x1400c4dff  nop     dword ptr [rax+rax+00h]
0x1400c4e04  test    eax, eax
0x1400c4e06  jnz     loc_1400C4D7E
0x1400c4e0c  movzx   eax, [rsp+78h+UnicodeString.Length]
0x1400c4e11  add     ax, r14w
0x1400c4e15  cmp     ax, r14w
0x1400c4e19  jb      loc_1400C4EA4
0x1400c4e1f  test    r15d, r15d
0x1400c4e22  jz      loc_1400C4EC5
0x1400c4e28  movzx   r14d, ax
0x1400c4e2c  xor     eax, eax
0x1400c4e2e  mov     [rsp+78h+UnicodeString.Length], ax
0x1400c4e33  xor     r15d, r15d
0x1400c4e36  jmp     loc_1400C4CB6
0x1400c4e3b  test    r12d, r12d
0x1400c4e3e  jz      loc_1400C4EE0
0x1400c4e44  xor     r8d, r8d; AllocateDestinationString
0x1400c4e47  lea     rcx, [rsp+78h+UnicodeString]; UnicodeString
0x1400c4e4c  mov     rdx, rdi; Sid
0x1400c4e4f  call    cs:__imp_RtlConvertSidToUnicodeString
0x1400c4e56  nop     dword ptr [rax+rax+00h]
0x1400c4e5b  test    eax, eax
0x1400c4e5d  jnz     loc_1400C4D7E
0x1400c4e63  lea     rdx, [rsp+78h+UnicodeString]; Source
0x1400c4e68  lea     rcx, [rsp+78h+Destination]; Destination
0x1400c4e6d  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400c4e74  nop     dword ptr [rax+rax+00h]
0x1400c4e79  xor     ecx, ecx
0x1400c4e7b  mov     [rsp+78h+UnicodeString.Length], cx
0x1400c4e80  test    eax, eax
0x1400c4e82  jnz     short loc_1400C4EB6
0x1400c4e84  xor     r12d, r12d
0x1400c4e87  jmp     loc_1400C4D7A
0x1400c4e8c  movups  xmm0, xmmword ptr [rsp+78h+Destination.Length]
0x1400c4e91  movups  xmmword ptr [r13+0], xmm0
0x1400c4e96  mov     [rsp+78h+Destination.Buffer], 0
0x1400c4e9f  jmp     loc_1400C4D9C
0x1400c4ea4  mov     r8d, 0C0000095h
0x1400c4eaa  lea     rdx, aRtlushortadd; "RtlUShortAdd"
0x1400c4eb1  jmp     loc_1400C4D88
0x1400c4eb6  mov     r8d, eax
0x1400c4eb9  lea     rdx, aRtlappendunico; "RtlAppendUnicodeStringToString"
0x1400c4ec0  jmp     loc_1400C4D88
0x1400c4ec5  lea     ecx, [rax+2]
0x1400c4ec8  cmp     cx, ax
0x1400c4ecb  jb      short loc_1400C4EA4
0x1400c4ecd  xor     eax, eax
0x1400c4ecf  movzx   r14d, cx
0x1400c4ed3  mov     [rsp+78h+UnicodeString.Length], ax
0x1400c4ed8  xor     r15d, r15d
0x1400c4edb  jmp     loc_1400C4CB6
0x1400c4ee0  lea     rdx, pszSrc; ","
0x1400c4ee7  lea     rcx, [rsp+78h+Destination]; DestinationString
0x1400c4eec  call    RtlUnicodeStringCatString
0x1400c4ef1  test    eax, eax
0x1400c4ef3  jz      loc_1400C4E44
0x1400c4ef9  mov     r8d, eax
0x1400c4efc  lea     rdx, aRtlunicodestri; "RtlUnicodeStringCatString"
0x1400c4f03  jmp     loc_1400C4D88
0x1400c4f08  mov     r8d, 0C0000017h
0x1400c4f0e  lea     rdx, aExallocatepool; "ExAllocatePool2"
0x1400c4f15  call    WfpReportSysErrorAsNtStatus
0x1400c4f1a  mov     rbp, rax
0x1400c4f1d  test    rax, rax
0x1400c4f20  jz      loc_1400C4C39
0x1400c4f26  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c4f2d  cmp     rcx, rdi
0x1400c4f30  jz      loc_1400C4C39
0x1400c4f36  cmp     byte ptr [rcx+29h], 2
0x1400c4f3a  jb      loc_1400C4C39
0x1400c4f40  test    dword ptr [rcx+2Ch], 1000h
0x1400c4f47  jz      loc_1400C4C39
0x1400c4f4d  mov     [rsp+78h+var_58], eax
0x1400c4f51  mov     rcx, [rcx+18h]
0x1400c4f55  lea     r9, aWfppoolallocno; "WfpPoolAllocNonPaged"
0x1400c4f5c  mov     edx, 0Fh
0x1400c4f61  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x1400c4f68  call    WPP_SF_sd
0x1400c4f6d  jmp     loc_1400C4D90
0x1400c4f72  mov     r8d, 0C0000017h
0x1400c4f78  lea     rdx, aExallocatepool; "ExAllocatePool2"
0x1400c4f7f  call    WfpReportSysErrorAsNtStatus
0x1400c4f84  mov     rbp, rax
0x1400c4f87  test    rax, rax
0x1400c4f8a  jz      loc_1400C4CFE
0x1400c4f90  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c4f97  lea     rax, WPP_GLOBAL_Control
0x1400c4f9e  cmp     rcx, rax
0x1400c4fa1  jz      loc_1400C4CFE
0x1400c4fa7  cmp     byte ptr [rcx+29h], 2
0x1400c4fab  jb      loc_1400C4CFE
0x1400c4fb1  test    dword ptr [rcx+2Ch], 1000h
0x1400c4fb8  jz      loc_1400C4CFE
0x1400c4fbe  mov     [rsp+78h+var_58], ebp
0x1400c4fc2  jmp     short loc_1400C4F51
0x1400c4fc4  lea     rdx, [rsp+78h+Destination.Buffer]
0x1400c4fc9  mov     ecx, 53736C41h; Tag
0x1400c4fce  call    WfpNamedPoolFree
0x1400c4fd3  jmp     loc_1400C4E96
```
