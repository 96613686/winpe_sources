# GetWellKnownSids(uchar)

- ea: `0x140004908`
- end: `0x140004c47`
- name: `?GetWellKnownSids@@YAJE@Z`
- size: `831`
- prototype: `__int64 __fastcall(unsigned __int8)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140004e30`

## callees

- `0x140003944`
- `0x140004908`
- `0x14000fd40`

## import_xrefs

- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x140004acb`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x140004acb`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140004b6c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140004bf2`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140004b6c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140004bf2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004a1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004b80`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004bd2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004c0d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004a1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004b80`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004bd2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004c0d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000496b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140004a41`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140004a8d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000496b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140004a41`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140004a8d`
- `ksecdd!SecLookupWellKnownSid` at `0x1400049cd`
- `ksecdd!SecLookupWellKnownSid` at `0x140004a67`
- `ksecdd!SecLookupWellKnownSid` at `0x1400049cd`
- `ksecdd!SecLookupWellKnownSid` at `0x140004a67`
- `FLTMGR!FltReleasePushLockEx` at `0x140004b0b`
- `FLTMGR!FltReleasePushLockEx` at `0x140004c27`
- `FLTMGR!FltReleasePushLockEx` at `0x140004b0b`
- `FLTMGR!FltReleasePushLockEx` at `0x140004c27`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140004943`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140004943`

## string_xrefs

- `0x14000491d`: `Called from system thread; well known SIDs might not be available`
- `0x1400049ee`: `Failed to allocate memory for the well-known SIDs string pointers`
- `0x140004b28`: `Failed to allocate memory for the well-known SID type %u`
- `0x140004bac`: `Failed to look up well-known SID type %u (0x%08X)`
- `0x140004b91`: `Failed to allocate memory for SID unicode string`
- `0x140004b55`: `Failed to convert well-known SID type %u to string (0x%08X)`

## pseudocode

```c
__int64 __fastcall GetWellKnownSids(char a1)
{
  NTSTATUS v1; // ebx
  PUNICODE_STRING *PoolWithTag; // rax
  PUNICODE_STRING *v3; // rdi
  void *v4; // rsi
  ULONG v5; // ebp
  PUNICODE_STRING *v6; // r12
  __int64 v7; // r15
  unsigned int v8; // r14d
  NTSTATUS v9; // eax
  ULONG v10; // ebp
  PVOID v11; // rax
  struct _UNICODE_STRING *v12; // rax
  struct _UNICODE_STRING *v13; // rbp
  NTSTATUS v14; // eax
  char v15; // r13
  PUNICODE_STRING *v16; // rbp
  __int64 v17; // rdi
  ULONG SidSize; // [rsp+78h] [rbp+10h] BYREF
  ULONG v20; // [rsp+80h] [rbp+18h]
  PUNICODE_STRING *v21; // [rsp+88h] [rbp+20h]

  if ( a1 )
  {
    WriteLogMessage(3, L"Called from system thread; well known SIDs might not be available");
    return (unsigned int)-1073740715;
  }
  v1 = 0;
  FltAcquirePushLockExclusiveEx(&qword_140019400, 0);
  if ( dword_140019408 )
    goto LABEL_38;
  PoolWithTag = (PUNICODE_STRING *)ExAllocatePoolWithTag((POOL_TYPE)1025, 0x3C0u, 0x6E6D7377u);
  v3 = PoolWithTag;
  if ( ExPoolZeroingNativelySupported )
  {
    if ( PoolWithTag )
      goto LABEL_7;
LABEL_11:
    WriteLogMessage(3, L"Failed to allocate memory for the well-known SIDs string pointers");
    v1 = -1073741670;
    goto LABEL_38;
  }
  if ( !PoolWithTag )
    goto LABEL_11;
  memset(PoolWithTag, 0, 0x3C0u);
LABEL_7:
  v4 = 0;
  v21 = v3;
  v5 = 0;
  v6 = v3;
  v20 = 0;
  v7 = 0;
  v8 = 120;
  while ( 1 )
  {
    SidSize = 0;
    v9 = SecLookupWellKnownSid((WELL_KNOWN_SID_TYPE)v7, v4, v5, &SidSize);
    v1 = v9;
    if ( v9 == -1073741811 )
    {
      v1 = 0;
      goto LABEL_24;
    }
    if ( v9 == -1073741789 )
    {
      if ( v4 )
        ExFreePoolWithTag(v4, 0x6E6D7377u);
      v10 = SidSize;
      v20 = SidSize;
      v11 = ExAllocatePoolWithTag(PagedPool, SidSize, 0x6E6D7377u);
      v4 = v11;
      if ( !v11 )
      {
        WriteLogMessage(3, L"Failed to allocate memory for the well-known SID type %u", (unsigned int)v7);
        v16 = v21;
        v17 = 0;
        v15 = 1;
        v1 = -1073741670;
        do
        {
LABEL_35:
          RtlFreeUnicodeString(v16[v17]);
          v17 = (unsigned int)(v17 + 1);
        }
        while ( (unsigned int)v17 < v8 );
LABEL_36:
        ExFreePoolWithTag(v6, 0x6E6D7377u);
        goto LABEL_37;
      }
      v1 = SecLookupWellKnownSid((WELL_KNOWN_SID_TYPE)v7, v11, v10, &SidSize);
    }
    if ( v1 < 0 )
      break;
    v12 = (struct _UNICODE_STRING *)ExAllocatePoolWithTag((POOL_TYPE)1025, 0x10u, 0x6E6D7377u);
    v13 = v12;
    if ( ExPoolZeroingNativelySupported )
    {
      if ( !v12 )
      {
LABEL_28:
        WriteLogMessage(3, L"Failed to allocate memory for SID unicode string");
        v1 = -1073741670;
        goto LABEL_30;
      }
    }
    else
    {
      if ( !v12 )
        goto LABEL_28;
      *v12 = 0;
    }
    v14 = RtlConvertSidToUnicodeString(v12, v4, 1u);
    v1 = v14;
    if ( v14 < 0 )
    {
      WriteLogMessage(
        3,
        L"Failed to convert well-known SID type %u to string (0x%08X)",
        (unsigned int)v7,
        (unsigned int)v14);
      RtlFreeUnicodeString(v13);
      ExFreePoolWithTag(v13, 0x6E6D7377u);
      v15 = 1;
      goto LABEL_31;
    }
    v3[v7] = v13;
    v5 = v20;
LABEL_24:
    v7 = (unsigned int)(v7 + 1);
    if ( (unsigned int)v7 >= 0x78 )
    {
      dword_140019408 = 120;
      qword_140019410 = v3;
      FltReleasePushLockEx(&qword_140019400, 0);
      v15 = 0;
      v8 = 0;
      v6 = 0;
      goto LABEL_31;
    }
  }
  WriteLogMessage(3, L"Failed to look up well-known SID type %u (0x%08X)", (unsigned int)v7, (unsigned int)v1);
LABEL_30:
  v15 = 1;
LABEL_31:
  if ( v4 )
    ExFreePoolWithTag(v4, 0x6E6D7377u);
  if ( v6 )
  {
    v17 = 0;
    v16 = v6;
    if ( v8 )
      goto LABEL_35;
    goto LABEL_36;
  }
LABEL_37:
  if ( v15 )
LABEL_38:
    FltReleasePushLockEx(&qword_140019400, 0);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x140004908  push    rbx
0x14000490a  push    rbp
0x14000490b  push    rsi
0x14000490c  push    rdi
0x14000490d  push    r12
0x14000490f  push    r13
0x140004911  push    r14
0x140004913  push    r15
0x140004915  sub     rsp, 28h
0x140004919  test    cl, cl
0x14000491b  jz      short loc_140004938
0x14000491d  lea     rdx, aCalledFromSyst; "Called from system thread; well known S"...
0x140004924  mov     ecx, 3
0x140004929  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x14000492e  mov     ebx, 0C0000455h
0x140004933  jmp     loc_140004C33
0x140004938  xor     edx, edx
0x14000493a  lea     rcx, qword_140019400
0x140004941  xor     ebx, ebx
0x140004943  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14000494a  nop     dword ptr [rax+rax+00h]
0x14000494f  cmp     cs:dword_140019408, ebx
0x140004955  ja      loc_140004C1E
0x14000495b  mov     ebx, 3C0h
0x140004960  mov     r8d, 6E6D7377h; Tag
0x140004966  mov     edx, ebx; NumberOfBytes
0x140004968  lea     ecx, [rbx+41h]; PoolType
0x14000496b  call    cs:__imp_ExAllocatePoolWithTag
0x140004972  nop     dword ptr [rax+rax+00h]
0x140004977  cmp     cs:ExPoolZeroingNativelySupported, 0
0x14000497e  mov     rdi, rax
0x140004981  jnz     short loc_1400049E9
0x140004983  test    rax, rax
0x140004986  jz      short loc_1400049EE
0x140004988  mov     r8d, ebx; Size
0x14000498b  xor     edx, edx; Val
0x14000498d  mov     rcx, rax; void *
0x140004990  call    memset
0x140004995  xor     esi, esi
0x140004997  mov     [rsp+68h+arg_18], rdi
0x14000499f  xor     ebp, ebp
0x1400049a1  mov     [rsp+68h+arg_0], 1
0x1400049a6  mov     r12, rdi
0x1400049a9  mov     [rsp+68h+arg_10], ebp
0x1400049b0  xor     r15d, r15d
0x1400049b3  lea     r14d, [rsi+78h]
0x1400049b7  lea     r9, [rsp+68h+SidSize]; SidSize
0x1400049bc  mov     [rsp+68h+SidSize], 0
0x1400049c4  mov     r8d, ebp; SidBufferSize
0x1400049c7  mov     rdx, rsi; Sid
0x1400049ca  mov     ecx, r15d; SidType
0x1400049cd  call    cs:__imp_SecLookupWellKnownSid
0x1400049d4  nop     dword ptr [rax+rax+00h]
0x1400049d9  mov     ebx, eax
0x1400049db  cmp     eax, 0C000000Dh
0x1400049e0  jnz     short loc_140004A09
0x1400049e2  xor     ebx, ebx
0x1400049e4  jmp     loc_140004AE8
0x1400049e9  test    rdi, rdi
0x1400049ec  jnz     short loc_140004995
0x1400049ee  lea     rdx, aFailedToAlloca_11; "Failed to allocate memory for the well-"...
0x1400049f5  mov     ecx, 3
0x1400049fa  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x1400049ff  mov     ebx, 0C000009Ah
0x140004a04  jmp     loc_140004C1E
0x140004a09  cmp     eax, 0C0000023h
0x140004a0e  jnz     short loc_140004A75
0x140004a10  test    rsi, rsi
0x140004a13  jz      short loc_140004A29
0x140004a15  mov     edx, 6E6D7377h; Tag
0x140004a1a  mov     rcx, rsi; P
0x140004a1d  call    cs:__imp_ExFreePoolWithTag
0x140004a24  nop     dword ptr [rax+rax+00h]
0x140004a29  mov     ebp, [rsp+68h+SidSize]
0x140004a2d  mov     ecx, 1; PoolType
0x140004a32  mov     edx, ebp; NumberOfBytes
0x140004a34  mov     [rsp+68h+arg_10], ebp
0x140004a3b  mov     r8d, 6E6D7377h; Tag
0x140004a41  call    cs:__imp_ExAllocatePoolWithTag
0x140004a48  nop     dword ptr [rax+rax+00h]
0x140004a4d  mov     rsi, rax
0x140004a50  test    rax, rax
0x140004a53  jz      loc_140004B25
0x140004a59  lea     r9, [rsp+68h+SidSize]; SidSize
0x140004a5e  mov     r8d, ebp; SidBufferSize
0x140004a61  mov     rdx, rax; Sid
0x140004a64  mov     ecx, r15d; SidType
0x140004a67  call    cs:__imp_SecLookupWellKnownSid
0x140004a6e  nop     dword ptr [rax+rax+00h]
0x140004a73  mov     ebx, eax
0x140004a75  test    ebx, ebx
0x140004a77  js      loc_140004BA9
0x140004a7d  mov     edx, 10h; NumberOfBytes
0x140004a82  mov     ecx, 401h; PoolType
0x140004a87  mov     r8d, 6E6D7377h; Tag
0x140004a8d  call    cs:__imp_ExAllocatePoolWithTag
0x140004a94  nop     dword ptr [rax+rax+00h]
0x140004a99  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140004aa0  mov     rbp, rax
0x140004aa3  jnz     short loc_140004AB6
0x140004aa5  test    rax, rax
0x140004aa8  jz      loc_140004B91
0x140004aae  xorps   xmm0, xmm0
0x140004ab1  movups  xmmword ptr [rax], xmm0
0x140004ab4  jmp     short loc_140004ABF
0x140004ab6  test    rbp, rbp
0x140004ab9  jz      loc_140004B91
0x140004abf  mov     r8b, 1; AllocateDestinationString
0x140004ac2  mov     rdx, rsi; Sid
0x140004ac5  mov     rcx, rbp; UnicodeString
0x140004ac8  mov     r13, rbp
0x140004acb  call    cs:__imp_RtlConvertSidToUnicodeString
0x140004ad2  nop     dword ptr [rax+rax+00h]
0x140004ad7  mov     ebx, eax
0x140004ad9  test    eax, eax
0x140004adb  js      short loc_140004B52
0x140004add  mov     [rdi+r15*8], rbp
0x140004ae1  mov     ebp, [rsp+68h+arg_10]
0x140004ae8  inc     r15d
0x140004aeb  cmp     r15d, r14d
0x140004aee  jb      loc_1400049B7
0x140004af4  xor     edx, edx
0x140004af6  mov     cs:dword_140019408, r14d
0x140004afd  lea     rcx, qword_140019400
0x140004b04  mov     cs:qword_140019410, rdi
0x140004b0b  call    cs:__imp_FltReleasePushLockEx
0x140004b12  nop     dword ptr [rax+rax+00h]
0x140004b17  xor     r13b, r13b
0x140004b1a  xor     r14d, r14d
0x140004b1d  xor     r12d, r12d
0x140004b20  jmp     loc_140004BC5
0x140004b25  mov     r8d, r15d
0x140004b28  lea     rdx, aFailedToAlloca_8; "Failed to allocate memory for the well-"...
0x140004b2f  mov     ecx, 3
0x140004b34  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x140004b39  mov     rbp, [rsp+68h+arg_18]
0x140004b41  xor     edi, edi
0x140004b43  mov     r13b, [rsp+68h+arg_0]
0x140004b48  mov     ebx, 0C000009Ah
0x140004b4d  jmp     loc_140004BED
0x140004b52  mov     r9d, eax
0x140004b55  lea     rdx, aFailedToConver_0; "Failed to convert well-known SID type %"...
0x140004b5c  mov     r8d, r15d
0x140004b5f  mov     ecx, 3
0x140004b64  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x140004b69  mov     rcx, r13; UnicodeString
0x140004b6c  call    cs:__imp_RtlFreeUnicodeString
0x140004b73  nop     dword ptr [rax+rax+00h]
0x140004b78  mov     edx, 6E6D7377h; Tag
0x140004b7d  mov     rcx, r13; P
0x140004b80  call    cs:__imp_ExFreePoolWithTag
0x140004b87  nop     dword ptr [rax+rax+00h]
0x140004b8c  mov     r13b, 1
0x140004b8f  jmp     short loc_140004BC5
0x140004b91  lea     rdx, aFailedToAlloca_0; "Failed to allocate memory for SID unico"...
0x140004b98  mov     ecx, 3
0x140004b9d  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x140004ba2  mov     ebx, 0C000009Ah
0x140004ba7  jmp     short loc_140004BC0
0x140004ba9  mov     r9d, ebx
0x140004bac  lea     rdx, aFailedToLookUp; "Failed to look up well-known SID type %"...
0x140004bb3  mov     r8d, r15d
0x140004bb6  mov     ecx, 3
0x140004bbb  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x140004bc0  mov     r13b, [rsp+68h+arg_0]
0x140004bc5  test    rsi, rsi
0x140004bc8  jz      short loc_140004BDE
0x140004bca  mov     edx, 6E6D7377h; Tag
0x140004bcf  mov     rcx, rsi; P
0x140004bd2  call    cs:__imp_ExFreePoolWithTag
0x140004bd9  nop     dword ptr [rax+rax+00h]
0x140004bde  test    r12, r12
0x140004be1  jz      short loc_140004C19
0x140004be3  xor     edi, edi
0x140004be5  mov     rbp, r12
0x140004be8  test    r14d, r14d
0x140004beb  jz      short loc_140004C05
0x140004bed  mov     rcx, [rbp+rdi*8+0]; UnicodeString
0x140004bf2  call    cs:__imp_RtlFreeUnicodeString
0x140004bf9  nop     dword ptr [rax+rax+00h]
0x140004bfe  inc     edi
0x140004c00  cmp     edi, r14d
0x140004c03  jb      short loc_140004BED
0x140004c05  mov     edx, 6E6D7377h; Tag
0x140004c0a  mov     rcx, r12; P
0x140004c0d  call    cs:__imp_ExFreePoolWithTag
0x140004c14  nop     dword ptr [rax+rax+00h]
0x140004c19  test    r13b, r13b
0x140004c1c  jz      short loc_140004C33
0x140004c1e  xor     edx, edx
0x140004c20  lea     rcx, qword_140019400
0x140004c27  call    cs:__imp_FltReleasePushLockEx
0x140004c2e  nop     dword ptr [rax+rax+00h]
0x140004c33  mov     eax, ebx
0x140004c35  add     rsp, 28h
0x140004c39  pop     r15
0x140004c3b  pop     r14
0x140004c3d  pop     r13
0x140004c3f  pop     r12
0x140004c41  pop     rdi
0x140004c42  pop     rsi
0x140004c43  pop     rbp
0x140004c44  pop     rbx
0x140004c45  retn
```
