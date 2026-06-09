# WfpAleGetServiceSidsFromToken

- ea: `0x1400bb460`
- end: `0x1400bb888`
- name: `WfpAleGetServiceSidsFromToken`
- size: `1064`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task`

## callers

- `0x1400bb000`

## callees

- `0x140053f20`
- `0x14008a370`
- `0x1400badb4`
- `0x1400bb460`
- `0x1400dddb0`
- `0x1401bf940`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400bb71d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400bb71d`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x1400bb6a8`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x1400bb6ff`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x1400bb6a8`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x1400bb6ff`
- `ntoskrnl!RtlValidSid` at `0x1400bb528`
- `ntoskrnl!RtlValidSid` at `0x1400bb5ec`
- `ntoskrnl!RtlValidSid` at `0x1400bb528`
- `ntoskrnl!RtlValidSid` at `0x1400bb5ec`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400bb4a1`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400bb4a1`
- `ntoskrnl!RtlSubAuthorityCountSid` at `0x1400bb53b`
- `ntoskrnl!RtlSubAuthorityCountSid` at `0x1400bb5ff`
- `ntoskrnl!RtlSubAuthorityCountSid` at `0x1400bb53b`
- `ntoskrnl!RtlSubAuthorityCountSid` at `0x1400bb5ff`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400bb551`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400bb615`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400bb551`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400bb615`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bb687`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bb687`
- `ntoskrnl!ExAllocatePool2` at `0x1400bb4c8`
- `ntoskrnl!ExAllocatePool2` at `0x1400bb594`
- `ntoskrnl!ExAllocatePool2` at `0x1400bb4c8`
- `ntoskrnl!ExAllocatePool2` at `0x1400bb594`

## string_xrefs

- `0x1400bb631`: `RtlConvertSidToUnicodeString`

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
0x1400bb460  mov     rax, rsp
0x1400bb463  push    rbp
0x1400bb464  sub     rsp, 70h
0x1400bb468  mov     [rax+8], rbx
0x1400bb46c  xorps   xmm0, xmm0
0x1400bb46f  mov     [rax+10h], rsi
0x1400bb473  mov     rbx, rcx
0x1400bb476  mov     [rax+18h], rdi
0x1400bb47a  xorps   xmm1, xmm1
0x1400bb47d  mov     [rax-10h], r12
0x1400bb481  xor     edx, edx; SourceString
0x1400bb483  mov     [rax-18h], r13
0x1400bb487  lea     r13, [rcx+0D0h]
0x1400bb48e  mov     [rax-20h], r14
0x1400bb492  mov     rcx, r13; DestinationString
0x1400bb495  mov     [rax-28h], r15
0x1400bb499  movups  xmmword ptr [rax-48h], xmm0
0x1400bb49d  movups  xmmword ptr [rax-38h], xmm1
0x1400bb4a1  call    cs:__imp_RtlInitUnicodeString
0x1400bb4a8  nop     dword ptr [rax+rax+00h]
0x1400bb4ad  mov     rsi, [rbx+0E0h]
0x1400bb4b4  mov     r8d, 53736C41h
0x1400bb4ba  mov     ebx, 82h
0x1400bb4bf  mov     ecx, 40h ; '@'
0x1400bb4c4  mov     edx, ebx
0x1400bb4c6  xor     ebp, ebp
0x1400bb4c8  call    cs:__imp_ExAllocatePool2
0x1400bb4cf  nop     dword ptr [rax+rax+00h]
0x1400bb4d4  mov     [rsp+78h+UnicodeString.Buffer], rax
0x1400bb4d9  lea     rdi, WPP_GLOBAL_Control
0x1400bb4e0  test    rax, rax
0x1400bb4e3  jz      loc_1400BB7B8
0x1400bb4e9  test    rbp, rbp
0x1400bb4ec  jnz     loc_1400BB640
0x1400bb4f2  mov     rcx, [rsp+78h+UnicodeString.Buffer]; void *
0x1400bb4f7  mov     r12d, 1
0x1400bb4fd  mov     r8, rbx; Size
0x1400bb500  xor     edx, edx; Val
0x1400bb502  mov     r15d, r12d
0x1400bb505  xor     r14d, r14d
0x1400bb508  call    memset
0x1400bb50d  mov     [rsp+78h+UnicodeString.MaximumLength], bx
0x1400bb512  xor     ebx, ebx
0x1400bb514  cmp     ebx, [rsi]
0x1400bb516  jnb     short loc_1400BB56A
0x1400bb518  mov     rax, [rsi+8]
0x1400bb51c  mov     ecx, ebx
0x1400bb51e  add     rcx, rcx
0x1400bb521  mov     rdi, [rax+rcx*8]
0x1400bb525  mov     rcx, rdi; Sid
0x1400bb528  call    cs:__imp_RtlValidSid
0x1400bb52f  nop     dword ptr [rax+rax+00h]
0x1400bb534  test    al, al
0x1400bb536  jz      short loc_1400BB566
0x1400bb538  mov     rcx, rdi; Sid
0x1400bb53b  call    cs:__imp_RtlSubAuthorityCountSid
0x1400bb542  nop     dword ptr [rax+rax+00h]
0x1400bb547  cmp     byte ptr [rax], 0
0x1400bb54a  jz      short loc_1400BB566
0x1400bb54c  xor     edx, edx; SubAuthority
0x1400bb54e  mov     rcx, rdi; Sid
0x1400bb551  call    cs:__imp_RtlSubAuthoritySid
0x1400bb558  nop     dword ptr [rax+rax+00h]
0x1400bb55d  cmp     dword ptr [rax], 50h ; 'P'
0x1400bb560  jz      loc_1400BB69D
0x1400bb566  inc     ebx
0x1400bb568  jmp     short loc_1400BB514
0x1400bb56a  test    r14w, r14w
0x1400bb56e  jz      loc_1400BB640
0x1400bb574  lea     ebx, [r14+2]
0x1400bb578  cmp     bx, r14w
0x1400bb57c  jb      loc_1400BB754
0x1400bb582  movzx   edi, bx
0x1400bb585  mov     r8d, 53736C41h
0x1400bb58b  mov     edx, edi
0x1400bb58d  mov     ecx, 40h ; '@'
0x1400bb592  xor     ebp, ebp
0x1400bb594  call    cs:__imp_ExAllocatePool2
0x1400bb59b  nop     dword ptr [rax+rax+00h]
0x1400bb5a0  mov     [rsp+78h+Destination.Buffer], rax
0x1400bb5a5  test    rax, rax
0x1400bb5a8  jz      loc_1400BB822
0x1400bb5ae  test    rbp, rbp
0x1400bb5b1  jnz     loc_1400BB640
0x1400bb5b7  mov     rcx, [rsp+78h+Destination.Buffer]; void *
0x1400bb5bc  mov     r8, rdi; Size
0x1400bb5bf  xor     edx, edx; Val
0x1400bb5c1  call    memset
0x1400bb5c6  xor     eax, eax
0x1400bb5c8  mov     [rsp+78h+Destination.MaximumLength], bx
0x1400bb5cd  mov     [rsp+78h+Destination.Length], ax
0x1400bb5d2  xor     ebx, ebx
0x1400bb5d4  cmp     ebx, [rsi]
0x1400bb5d6  jnb     loc_1400BB73C
0x1400bb5dc  mov     rax, [rsi+8]
0x1400bb5e0  mov     ecx, ebx
0x1400bb5e2  add     rcx, rcx
0x1400bb5e5  mov     rdi, [rax+rcx*8]
0x1400bb5e9  mov     rcx, rdi; Sid
0x1400bb5ec  call    cs:__imp_RtlValidSid
0x1400bb5f3  nop     dword ptr [rax+rax+00h]
0x1400bb5f8  test    al, al
0x1400bb5fa  jz      short loc_1400BB62A
0x1400bb5fc  mov     rcx, rdi; Sid
0x1400bb5ff  call    cs:__imp_RtlSubAuthorityCountSid
0x1400bb606  nop     dword ptr [rax+rax+00h]
0x1400bb60b  cmp     byte ptr [rax], 0
0x1400bb60e  jz      short loc_1400BB62A
0x1400bb610  xor     edx, edx; SubAuthority
0x1400bb612  mov     rcx, rdi; Sid
0x1400bb615  call    cs:__imp_RtlSubAuthoritySid
0x1400bb61c  nop     dword ptr [rax+rax+00h]
0x1400bb621  cmp     dword ptr [rax], 50h ; 'P'
0x1400bb624  jz      loc_1400BB6EB
0x1400bb62a  inc     ebx
0x1400bb62c  jmp     short loc_1400BB5D4
0x1400bb62e  mov     r8d, eax
0x1400bb631  lea     rdx, aRtlconvertsidt; "RtlConvertSidToUnicodeString"
0x1400bb638  call    WfpReportSysErrorAsNtStatus
0x1400bb63d  mov     rbp, rax
0x1400bb640  cmp     [rsp+78h+Destination.Buffer], 0
0x1400bb646  jnz     loc_1400BB874
0x1400bb64c  mov     rcx, [rsp+78h+UnicodeString.Buffer]; P
0x1400bb651  mov     r15, [rsp+78h+var_28]
0x1400bb656  mov     r14, [rsp+78h+var_20]
0x1400bb65b  mov     r13, [rsp+78h+var_18]
0x1400bb660  mov     r12, [rsp+78h+var_10]
0x1400bb665  mov     rdi, [rsp+78h+arg_10]
0x1400bb66d  mov     rsi, [rsp+78h+arg_8]
0x1400bb675  mov     rbx, [rsp+78h+arg_0]
0x1400bb67d  test    rcx, rcx
0x1400bb680  jz      short loc_1400BB693
0x1400bb682  mov     edx, 53736C41h; Tag
0x1400bb687  call    cs:__imp_ExFreePoolWithTag
0x1400bb68e  nop     dword ptr [rax+rax+00h]
0x1400bb693  mov     rax, rbp
0x1400bb696  add     rsp, 70h
0x1400bb69a  pop     rbp
0x1400bb69b  retn
0x1400bb69d  xor     r8d, r8d; AllocateDestinationString
0x1400bb6a0  lea     rcx, [rsp+78h+UnicodeString]; UnicodeString
0x1400bb6a5  mov     rdx, rdi; Sid
0x1400bb6a8  call    cs:__imp_RtlConvertSidToUnicodeString
0x1400bb6af  nop     dword ptr [rax+rax+00h]
0x1400bb6b4  test    eax, eax
0x1400bb6b6  jnz     loc_1400BB62E
0x1400bb6bc  movzx   eax, [rsp+78h+UnicodeString.Length]
0x1400bb6c1  add     ax, r14w
0x1400bb6c5  cmp     ax, r14w
0x1400bb6c9  jb      loc_1400BB754
0x1400bb6cf  test    r15d, r15d
0x1400bb6d2  jz      loc_1400BB775
0x1400bb6d8  movzx   r14d, ax
0x1400bb6dc  xor     eax, eax
0x1400bb6de  mov     [rsp+78h+UnicodeString.Length], ax
0x1400bb6e3  xor     r15d, r15d
0x1400bb6e6  jmp     loc_1400BB566
0x1400bb6eb  test    r12d, r12d
0x1400bb6ee  jz      loc_1400BB790
0x1400bb6f4  xor     r8d, r8d; AllocateDestinationString
0x1400bb6f7  lea     rcx, [rsp+78h+UnicodeString]; UnicodeString
0x1400bb6fc  mov     rdx, rdi; Sid
0x1400bb6ff  call    cs:__imp_RtlConvertSidToUnicodeString
0x1400bb706  nop     dword ptr [rax+rax+00h]
0x1400bb70b  test    eax, eax
0x1400bb70d  jnz     loc_1400BB62E
0x1400bb713  lea     rdx, [rsp+78h+UnicodeString]; Source
0x1400bb718  lea     rcx, [rsp+78h+Destination]; Destination
0x1400bb71d  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400bb724  nop     dword ptr [rax+rax+00h]
0x1400bb729  xor     ecx, ecx
0x1400bb72b  mov     [rsp+78h+UnicodeString.Length], cx
0x1400bb730  test    eax, eax
0x1400bb732  jnz     short loc_1400BB766
0x1400bb734  xor     r12d, r12d
0x1400bb737  jmp     loc_1400BB62A
0x1400bb73c  movups  xmm0, xmmword ptr [rsp+78h+Destination.Length]
0x1400bb741  movups  xmmword ptr [r13+0], xmm0
0x1400bb746  mov     [rsp+78h+Destination.Buffer], 0
0x1400bb74f  jmp     loc_1400BB64C
0x1400bb754  mov     r8d, 0C0000095h
0x1400bb75a  lea     rdx, aRtlushortadd; "RtlUShortAdd"
0x1400bb761  jmp     loc_1400BB638
0x1400bb766  mov     r8d, eax
0x1400bb769  lea     rdx, aRtlappendunico; "RtlAppendUnicodeStringToString"
0x1400bb770  jmp     loc_1400BB638
0x1400bb775  lea     ecx, [rax+2]
0x1400bb778  cmp     cx, ax
0x1400bb77b  jb      short loc_1400BB754
0x1400bb77d  xor     eax, eax
0x1400bb77f  movzx   r14d, cx
0x1400bb783  mov     [rsp+78h+UnicodeString.Length], ax
0x1400bb788  xor     r15d, r15d
0x1400bb78b  jmp     loc_1400BB566
0x1400bb790  lea     rdx, pszSrc; ","
0x1400bb797  lea     rcx, [rsp+78h+Destination]; DestinationString
0x1400bb79c  call    RtlUnicodeStringCatString
0x1400bb7a1  test    eax, eax
0x1400bb7a3  jz      loc_1400BB6F4
0x1400bb7a9  mov     r8d, eax
0x1400bb7ac  lea     rdx, aRtlunicodestri; "RtlUnicodeStringCatString"
0x1400bb7b3  jmp     loc_1400BB638
0x1400bb7b8  mov     r8d, 0C0000017h
0x1400bb7be  lea     rdx, aExallocatepool; "ExAllocatePool2"
0x1400bb7c5  call    WfpReportSysErrorAsNtStatus
0x1400bb7ca  mov     rbp, rax
0x1400bb7cd  test    rax, rax
0x1400bb7d0  jz      loc_1400BB4E9
0x1400bb7d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bb7dd  cmp     rcx, rdi
0x1400bb7e0  jz      loc_1400BB4E9
0x1400bb7e6  cmp     byte ptr [rcx+29h], 2
0x1400bb7ea  jb      loc_1400BB4E9
0x1400bb7f0  test    dword ptr [rcx+2Ch], 1000h
0x1400bb7f7  jz      loc_1400BB4E9
0x1400bb7fd  mov     [rsp+78h+var_58], eax
0x1400bb801  mov     rcx, [rcx+18h]
0x1400bb805  lea     r9, aWfppoolallocno; "WfpPoolAllocNonPaged"
0x1400bb80c  mov     edx, 0Fh
0x1400bb811  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x1400bb818  call    WPP_SF_sd
0x1400bb81d  jmp     loc_1400BB640
0x1400bb822  mov     r8d, 0C0000017h
0x1400bb828  lea     rdx, aExallocatepool; "ExAllocatePool2"
0x1400bb82f  call    WfpReportSysErrorAsNtStatus
0x1400bb834  mov     rbp, rax
0x1400bb837  test    rax, rax
0x1400bb83a  jz      loc_1400BB5AE
0x1400bb840  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bb847  lea     rax, WPP_GLOBAL_Control
0x1400bb84e  cmp     rcx, rax
0x1400bb851  jz      loc_1400BB5AE
0x1400bb857  cmp     byte ptr [rcx+29h], 2
0x1400bb85b  jb      loc_1400BB5AE
0x1400bb861  test    dword ptr [rcx+2Ch], 1000h
0x1400bb868  jz      loc_1400BB5AE
0x1400bb86e  mov     [rsp+78h+var_58], ebp
0x1400bb872  jmp     short loc_1400BB801
0x1400bb874  lea     rdx, [rsp+78h+Destination.Buffer]
0x1400bb879  mov     ecx, 53736C41h; Tag
0x1400bb87e  call    WfpNamedPoolFree
0x1400bb883  jmp     loc_1400BB746
```
