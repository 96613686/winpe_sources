# VhdmpiOpenAutoAttachRegistryKey

- ea: `0x1400bb0fc`
- end: `0x1400bb324`
- name: `VhdmpiOpenAutoAttachRegistryKey`
- size: `552`
- prototype: `__int64 __fastcall(PHANDLE KeyHandle)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400bb32c`
- `0x1400bb538`

## callees

- `0x140023560`
- `0x140035e94`
- `0x14005d7c0`
- `0x1400bb0fc`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400bb1d6`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400bb1d6`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400bb1a8`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400bb1a8`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400bb1c0`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400bb1c0`
- `ntoskrnl!ZwOpenKey` at `0x1400bb2a0`
- `ntoskrnl!ZwOpenKey` at `0x1400bb2a0`
- `ntoskrnl!RtlStringFromGUIDEx` at `0x1400bb16d`
- `ntoskrnl!RtlStringFromGUIDEx` at `0x1400bb16d`
- `ntoskrnl!ZwCreateKey` at `0x1400bb28d`
- `ntoskrnl!ZwCreateKey` at `0x1400bb28d`

## string_xrefs

- `0x1400bb219`: `VhdmpiOpenAutoAttachRegistryKey: Opening %wZ`
- `0x1400bb222`: `VhdmpiOpenAutoAttachRegistryKey`
- `0x1400bb2f1`: `VhdmpiOpenAutoAttachRegistryKey`

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
    if ( (unsigned int)dword_140087708 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
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
    if ( v8 < 0 && (unsigned int)dword_140087708 > 2 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x80000) )
        TraceEvents("VhdmpiOpenAutoAttachRegistryKey", 0x11DDu, v10, v11, "Return with status 0x%08X", v9);
    }
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x1400bb0fc  mov     [rsp-8+arg_10], rbx
0x1400bb101  mov     [rsp-8+arg_18], rdi
0x1400bb106  push    rbp
0x1400bb107  lea     rbp, [rsp-1F0h]
0x1400bb10f  sub     rsp, 2F0h
0x1400bb116  mov     rax, cs:__security_cookie
0x1400bb11d  xor     rax, rsp
0x1400bb120  mov     [rbp+1F0h+var_10], rax
0x1400bb127  xorps   xmm1, xmm1
0x1400bb12a  xorps   xmm0, xmm0
0x1400bb12d  movups  xmmword ptr [rsp+2F0h+Source.Length], xmm0
0x1400bb132  mov     eax, 4Eh ; 'N'
0x1400bb137  mov     rbx, rcx
0x1400bb13a  mov     [rsp+2F0h+Source.MaximumLength], ax
0x1400bb13f  lea     rcx, [rdx+2B0h]
0x1400bb146  lea     rax, [rbp+1F0h+var_260]
0x1400bb14a  mov     dil, r8b
0x1400bb14d  xor     r8d, r8d
0x1400bb150  mov     [rsp+2F0h+Source.Buffer], rax
0x1400bb155  lea     rdx, [rsp+2F0h+Source]
0x1400bb15a  movups  xmmword ptr [rsp+2F0h+DestinationString.Length], xmm0
0x1400bb15f  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.Length], xmm1
0x1400bb164  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.ObjectName], xmm1
0x1400bb169  movups  xmmword ptr [rbp+1F0h+ObjectAttributes.SecurityDescriptor], xmm1
0x1400bb16d  call    cs:__imp_RtlStringFromGUIDEx
0x1400bb174  nop     dword ptr [rax+rax+00h]
0x1400bb179  test    eax, eax
0x1400bb17b  js      loc_1400BB2FF
0x1400bb181  xorps   xmm0, xmm0
0x1400bb184  lea     rdx, stru_140060800; SourceString
0x1400bb18b  movups  xmmword ptr [rsp+2F0h+DestinationString.Length], xmm0
0x1400bb190  mov     eax, 200h
0x1400bb195  lea     rcx, [rsp+2F0h+DestinationString]; DestinationString
0x1400bb19a  mov     [rsp+2F0h+DestinationString.MaximumLength], ax
0x1400bb19f  lea     rax, [rbp+1F0h+var_210]
0x1400bb1a3  mov     [rsp+2F0h+DestinationString.Buffer], rax
0x1400bb1a8  call    cs:__imp_RtlCopyUnicodeString
0x1400bb1af  nop     dword ptr [rax+rax+00h]
0x1400bb1b4  lea     rdx, asc_1400613C0; "\\"
0x1400bb1bb  lea     rcx, [rsp+2F0h+DestinationString]; Destination
0x1400bb1c0  call    cs:__imp_RtlAppendUnicodeToString
0x1400bb1c7  nop     dword ptr [rax+rax+00h]
0x1400bb1cc  lea     rdx, [rsp+2F0h+Source]; Source
0x1400bb1d1  lea     rcx, [rsp+2F0h+DestinationString]; Destination
0x1400bb1d6  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400bb1dd  nop     dword ptr [rax+rax+00h]
0x1400bb1e2  mov     eax, cs:dword_140087708
0x1400bb1e8  mov     r8d, 5
0x1400bb1ee  cmp     eax, r8d
0x1400bb1f1  jbe     short loc_1400BB233
0x1400bb1f3  lea     edx, [r8+0Bh]
0x1400bb1f7  lea     rcx, dword_140087708
0x1400bb1fe  call    _tlgKeywordOn
0x1400bb203  test    al, al
0x1400bb205  jz      short loc_1400BB233
0x1400bb207  lea     rax, [rsp+2F0h+DestinationString]
0x1400bb20c  mov     ecx, 11C9h
0x1400bb211  mov     qword ptr [rsp+2F0h+CreateOptions], rax; char
0x1400bb216  mov     r9d, edx; int
0x1400bb219  lea     rax, aVhdmpiopenauto_0; "VhdmpiOpenAutoAttachRegistryKey: Openin"...
0x1400bb220  mov     edx, ecx; int
0x1400bb222  lea     rcx, aVhdmpiopenauto; "VhdmpiOpenAutoAttachRegistryKey"
0x1400bb229  mov     [rsp+2F0h+Class], rax; char *
0x1400bb22e  call    TraceEvents
0x1400bb233  mov     [rsp+2F0h+ObjectAttributes.Length], 30h ; '0'
0x1400bb23b  lea     rax, [rsp+2F0h+DestinationString]
0x1400bb240  mov     [rsp+2F0h+ObjectAttributes.ObjectName], rax
0x1400bb245  xorps   xmm0, xmm0
0x1400bb248  mov     [rsp+2F0h+ObjectAttributes.RootDirectory], 0
0x1400bb251  lea     r8, [rsp+2F0h+ObjectAttributes]; ObjectAttributes
0x1400bb256  mov     [rsp+2F0h+ObjectAttributes.Attributes], 240h
0x1400bb25e  mov     rcx, rbx; KeyHandle
0x1400bb261  movdqu  xmmword ptr [rbp+1F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400bb266  test    dil, dil
0x1400bb269  jnz     short loc_1400BB29B
0x1400bb26b  mov     [rsp+2F0h+Disposition], 0; Disposition
0x1400bb274  xor     r9d, r9d; TitleIndex
0x1400bb277  mov     [rsp+2F0h+CreateOptions], 0; CreateOptions
0x1400bb27f  mov     edx, 40000000h; DesiredAccess
0x1400bb284  mov     [rsp+2F0h+Class], 0; Class
0x1400bb28d  call    cs:__imp_ZwCreateKey
0x1400bb294  nop     dword ptr [rax+rax+00h]
0x1400bb299  jmp     short loc_1400BB2AC
0x1400bb29b  mov     edx, 10010000h; DesiredAccess
0x1400bb2a0  call    cs:__imp_ZwOpenKey
0x1400bb2a7  nop     dword ptr [rax+rax+00h]
0x1400bb2ac  mov     ebx, eax
0x1400bb2ae  test    eax, eax
0x1400bb2b0  jns     short loc_1400BB2FD
0x1400bb2b2  mov     eax, cs:dword_140087708
0x1400bb2b8  mov     r8d, 2
0x1400bb2be  cmp     eax, r8d
0x1400bb2c1  jbe     short loc_1400BB2FD
0x1400bb2c3  mov     r9d, 80000h
0x1400bb2c9  lea     rcx, dword_140087708
0x1400bb2d0  mov     edx, r9d
0x1400bb2d3  call    _tlgKeywordOn
0x1400bb2d8  test    al, al
0x1400bb2da  jz      short loc_1400BB2FD
0x1400bb2dc  lea     rax, aReturnWithStat_23; "Return with status 0x%08X"
0x1400bb2e3  mov     [rsp+2F0h+CreateOptions], ebx; char
0x1400bb2e7  mov     edx, 11DDh; int
0x1400bb2ec  mov     [rsp+2F0h+Class], rax; char *
0x1400bb2f1  lea     rcx, aVhdmpiopenauto; "VhdmpiOpenAutoAttachRegistryKey"
0x1400bb2f8  call    TraceEvents
0x1400bb2fd  mov     eax, ebx
0x1400bb2ff  mov     rcx, [rbp+1F0h+var_10]
0x1400bb306  xor     rcx, rsp; StackCookie
0x1400bb309  call    __security_check_cookie
0x1400bb30e  lea     r11, [rsp+2F0h+var_s0]
0x1400bb316  mov     rbx, [r11+20h]
0x1400bb31a  mov     rdi, [r11+28h]
0x1400bb31e  mov     rsp, r11
0x1400bb321  pop     rbp
0x1400bb322  retn
```
