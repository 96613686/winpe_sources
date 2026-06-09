# VhdmpiOpenAutoAttachRegistryKey

- ea: `0x1400bb0ec`
- end: `0x1400bb314`
- name: `VhdmpiOpenAutoAttachRegistryKey`
- size: `552`
- prototype: `__int64 __fastcall(PHANDLE KeyHandle)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400bb31c`
- `0x1400bb528`

## callees

- `0x140023980`
- `0x140036284`
- `0x14005dbb0`
- `0x1400bb0ec`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400bb1c6`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400bb1c6`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400bb198`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400bb198`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400bb1b0`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400bb1b0`
- `ntoskrnl!ZwOpenKey` at `0x1400bb290`
- `ntoskrnl!ZwOpenKey` at `0x1400bb290`
- `ntoskrnl!RtlStringFromGUIDEx` at `0x1400bb15d`
- `ntoskrnl!RtlStringFromGUIDEx` at `0x1400bb15d`
- `ntoskrnl!ZwCreateKey` at `0x1400bb27d`
- `ntoskrnl!ZwCreateKey` at `0x1400bb27d`

## string_xrefs

- `0x1400bb209`: `VhdmpiOpenAutoAttachRegistryKey: Opening %wZ`
- `0x1400bb212`: `VhdmpiOpenAutoAttachRegistryKey`
- `0x1400bb2e1`: `VhdmpiOpenAutoAttachRegistryKey`

## pseudocode

```c
__int64 __fastcall VhdmpiOpenAutoAttachRegistryKey(PHANDLE KeyHandle, __int64 a2, char a3)
{
  __int64 result; // rax
  unsigned int v6; // edx
  unsigned __int8 v7; // r8
  NTSTATUS v8; // eax
  unsigned int v9; // ebx
  unsigned __int8 v10; // r8
  unsigned int v11; // r9d
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  UNICODE_STRING Source; // [rsp+50h] [rbp-B0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-A0h] BYREF
  char v15; // [rsp+90h] [rbp-70h] BYREF
  char v16; // [rsp+E0h] [rbp-20h] BYREF

  *(_QWORD *)&Source.Length = 5111808;
  Source.Buffer = (PWSTR)&v15;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  result = RtlStringFromGUIDEx(a2 + 688, &Source, 0);
  if ( (int)result >= 0 )
  {
    *(_QWORD *)&DestinationString.Length = 0x2000000;
    DestinationString.Buffer = (PWSTR)&v16;
    RtlCopyUnicodeString(&DestinationString, &stru_140060800);
    RtlAppendUnicodeToString(&DestinationString, L"\\");
    RtlAppendUnicodeStringToString(&DestinationString, &Source);
    if ( (unsigned int)dword_1400876D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
      TraceEvents(
        "VhdmpiOpenAutoAttachRegistryKey",
        0x11C9u,
        v7,
        v6,
        "VhdmpiOpenAutoAttachRegistryKey: Opening %wZ",
        &DestinationString);
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( a3 )
      v8 = ZwOpenKey(KeyHandle, 0x10010000u, &ObjectAttributes);
    else
      v8 = ZwCreateKey(KeyHandle, 0x40000000u, &ObjectAttributes, 0, 0, 0, 0);
    v9 = v8;
    if ( v8 < 0 && (unsigned int)dword_1400876D0 > 2 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x80000) )
        TraceEvents("VhdmpiOpenAutoAttachRegistryKey", 0x11DDu, v10, v11, "Return with status 0x%08X", v9);
    }
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x1400bb0ec  mov     [rsp-8+arg_10], rbx
0x1400bb0f1  mov     [rsp-8+arg_18], rdi
0x1400bb0f6  push    rbp
0x1400bb0f7  lea     rbp, [rsp-1F0h]
0x1400bb0ff  sub     rsp, 2F0h
0x1400bb106  mov     rax, cs:__security_cookie
0x1400bb10d  xor     rax, rsp
0x1400bb110  mov     [rbp+1F0h+var_10], rax
0x1400bb117  xorps   xmm1, xmm1
0x1400bb11a  xorps   xmm0, xmm0
0x1400bb11d  movups  xmmword ptr [rsp+2F0h+Source.Length], xmm0
0x1400bb122  mov     eax, 4Eh ; 'N'
0x1400bb127  mov     rbx, rcx
0x1400bb12a  mov     [rsp+2F0h+Source.MaximumLength], ax
0x1400bb12f  lea     rcx, [rdx+2B0h]
0x1400bb136  lea     rax, [rbp+1F0h+var_260]
0x1400bb13a  mov     dil, r8b
0x1400bb13d  xor     r8d, r8d
0x1400bb140  mov     [rsp+2F0h+Source.Buffer], rax
0x1400bb145  lea     rdx, [rsp+2F0h+Source]
0x1400bb14a  movups  xmmword ptr [rsp+2F0h+DestinationString.Length], xmm0
0x1400bb14f  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.Length], xmm1
0x1400bb154  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.ObjectName], xmm1
0x1400bb159  movups  xmmword ptr [rbp+1F0h+ObjectAttributes.SecurityDescriptor], xmm1
0x1400bb15d  call    cs:__imp_RtlStringFromGUIDEx
0x1400bb164  nop     dword ptr [rax+rax+00h]
0x1400bb169  test    eax, eax
0x1400bb16b  js      loc_1400BB2EF
0x1400bb171  xorps   xmm0, xmm0
0x1400bb174  lea     rdx, stru_140060800; SourceString
0x1400bb17b  movups  xmmword ptr [rsp+2F0h+DestinationString.Length], xmm0
0x1400bb180  mov     eax, 200h
0x1400bb185  lea     rcx, [rsp+2F0h+DestinationString]; DestinationString
0x1400bb18a  mov     [rsp+2F0h+DestinationString.MaximumLength], ax
0x1400bb18f  lea     rax, [rbp+1F0h+var_210]
0x1400bb193  mov     [rsp+2F0h+DestinationString.Buffer], rax
0x1400bb198  call    cs:__imp_RtlCopyUnicodeString
0x1400bb19f  nop     dword ptr [rax+rax+00h]
0x1400bb1a4  lea     rdx, asc_1400613C0; "\\"
0x1400bb1ab  lea     rcx, [rsp+2F0h+DestinationString]; Destination
0x1400bb1b0  call    cs:__imp_RtlAppendUnicodeToString
0x1400bb1b7  nop     dword ptr [rax+rax+00h]
0x1400bb1bc  lea     rdx, [rsp+2F0h+Source]; Source
0x1400bb1c1  lea     rcx, [rsp+2F0h+DestinationString]; Destination
0x1400bb1c6  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400bb1cd  nop     dword ptr [rax+rax+00h]
0x1400bb1d2  mov     eax, cs:dword_1400876D0
0x1400bb1d8  mov     r8d, 5
0x1400bb1de  cmp     eax, r8d
0x1400bb1e1  jbe     short loc_1400BB223
0x1400bb1e3  lea     edx, [r8+0Bh]
0x1400bb1e7  lea     rcx, dword_1400876D0
0x1400bb1ee  call    _tlgKeywordOn
0x1400bb1f3  test    al, al
0x1400bb1f5  jz      short loc_1400BB223
0x1400bb1f7  lea     rax, [rsp+2F0h+DestinationString]
0x1400bb1fc  mov     ecx, 11C9h
0x1400bb201  mov     qword ptr [rsp+2F0h+CreateOptions], rax; char
0x1400bb206  mov     r9d, edx; int
0x1400bb209  lea     rax, aVhdmpiopenauto_0; "VhdmpiOpenAutoAttachRegistryKey: Openin"...
0x1400bb210  mov     edx, ecx; int
0x1400bb212  lea     rcx, aVhdmpiopenauto; "VhdmpiOpenAutoAttachRegistryKey"
0x1400bb219  mov     [rsp+2F0h+Class], rax; char *
0x1400bb21e  call    TraceEvents
0x1400bb223  mov     [rsp+2F0h+ObjectAttributes.Length], 30h ; '0'
0x1400bb22b  lea     rax, [rsp+2F0h+DestinationString]
0x1400bb230  mov     [rsp+2F0h+ObjectAttributes.ObjectName], rax
0x1400bb235  xorps   xmm0, xmm0
0x1400bb238  mov     [rsp+2F0h+ObjectAttributes.RootDirectory], 0
0x1400bb241  lea     r8, [rsp+2F0h+ObjectAttributes]; ObjectAttributes
0x1400bb246  mov     [rsp+2F0h+ObjectAttributes.Attributes], 240h
0x1400bb24e  mov     rcx, rbx; KeyHandle
0x1400bb251  movdqu  xmmword ptr [rbp+1F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400bb256  test    dil, dil
0x1400bb259  jnz     short loc_1400BB28B
0x1400bb25b  mov     [rsp+2F0h+Disposition], 0; Disposition
0x1400bb264  xor     r9d, r9d; TitleIndex
0x1400bb267  mov     [rsp+2F0h+CreateOptions], 0; CreateOptions
0x1400bb26f  mov     edx, 40000000h; DesiredAccess
0x1400bb274  mov     [rsp+2F0h+Class], 0; Class
0x1400bb27d  call    cs:__imp_ZwCreateKey
0x1400bb284  nop     dword ptr [rax+rax+00h]
0x1400bb289  jmp     short loc_1400BB29C
0x1400bb28b  mov     edx, 10010000h; DesiredAccess
0x1400bb290  call    cs:__imp_ZwOpenKey
0x1400bb297  nop     dword ptr [rax+rax+00h]
0x1400bb29c  mov     ebx, eax
0x1400bb29e  test    eax, eax
0x1400bb2a0  jns     short loc_1400BB2ED
0x1400bb2a2  mov     eax, cs:dword_1400876D0
0x1400bb2a8  mov     r8d, 2
0x1400bb2ae  cmp     eax, r8d
0x1400bb2b1  jbe     short loc_1400BB2ED
0x1400bb2b3  mov     r9d, 80000h
0x1400bb2b9  lea     rcx, dword_1400876D0
0x1400bb2c0  mov     edx, r9d
0x1400bb2c3  call    _tlgKeywordOn
0x1400bb2c8  test    al, al
0x1400bb2ca  jz      short loc_1400BB2ED
0x1400bb2cc  lea     rax, aReturnWithStat_23; "Return with status 0x%08X"
0x1400bb2d3  mov     [rsp+2F0h+CreateOptions], ebx; char
0x1400bb2d7  mov     edx, 11DDh; int
0x1400bb2dc  mov     [rsp+2F0h+Class], rax; char *
0x1400bb2e1  lea     rcx, aVhdmpiopenauto; "VhdmpiOpenAutoAttachRegistryKey"
0x1400bb2e8  call    TraceEvents
0x1400bb2ed  mov     eax, ebx
0x1400bb2ef  mov     rcx, [rbp+1F0h+var_10]
0x1400bb2f6  xor     rcx, rsp; StackCookie
0x1400bb2f9  call    __security_check_cookie
0x1400bb2fe  lea     r11, [rsp+2F0h+var_s0]
0x1400bb306  mov     rbx, [r11+20h]
0x1400bb30a  mov     rdi, [r11+28h]
0x1400bb30e  mov     rsp, r11
0x1400bb311  pop     rbp
0x1400bb312  retn
```
