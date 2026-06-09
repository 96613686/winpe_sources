# PgmOpenRegistryParameters

- ea: `0x14000a18c`
- end: `0x14000a2f2`
- name: `PgmOpenRegistryParameters`
- size: `358`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, void **, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14003815c`

## callees

- `0x140005068`
- `0x14000a18c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000a252`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a252`
- `ntoskrnl!ZwClose` at `0x14000a2d7`
- `ntoskrnl!ZwClose` at `0x14000a2d7`
- `ntoskrnl!ZwCreateKey` at `0x14000a1f5`
- `ntoskrnl!ZwCreateKey` at `0x14000a1f5`
- `ntoskrnl!ZwOpenKey` at `0x14000a28f`
- `ntoskrnl!ZwOpenKey` at `0x14000a28f`

## pseudocode

```c
__int64 __fastcall PgmOpenRegistryParameters(struct _UNICODE_STRING *a1, void **a2, void **a3)
{
  NTSTATUS v5; // eax
  unsigned int v6; // ebx
  NTSTATUS v7; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-9h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp+7h] BYREF
  ULONG Disposition; // [rsp+B0h] [rbp+67h] BYREF

  ObjectAttributes.ObjectName = a1;
  Disposition = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  DestinationString = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v5 = ZwCreateKey(a2, 0x20019u, &ObjectAttributes, 0, 0, 0, &Disposition);
  v6 = v5;
  if ( v5 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"Parameters");
    ObjectAttributes.RootDirectory = *a2;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v7 = ZwOpenKey(a3, 0x20019u, &ObjectAttributes);
    v6 = v7;
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          18,
          WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids,
          (unsigned int)v7);
      ZwClose(*a2);
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids, (unsigned int)v5);
  }
  return v6;
}

```

## disassembly

```asm
0x14000a18c  push    rbp
0x14000a18e  push    rbx
0x14000a18f  push    rsi
0x14000a190  push    rdi
0x14000a191  lea     rbp, [rsp-3Fh]
0x14000a196  sub     rsp, 88h
0x14000a19d  xor     eax, eax
0x14000a19f  mov     [rbp+57h+ObjectAttributes.ObjectName], rcx
0x14000a1a3  mov     rdi, rdx
0x14000a1a6  mov     [rbp+57h+arg_0], eax
0x14000a1a9  xorps   xmm0, xmm0
0x14000a1ac  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x14000a1b0  lea     rax, [rbp+57h+arg_0]
0x14000a1b4  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14000a1bc  mov     [rsp+0A0h+Disposition], rax; Disposition
0x14000a1c1  mov     rsi, r8
0x14000a1c4  mov     [rsp+0A0h+CreateOptions], 0; CreateOptions
0x14000a1cc  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14000a1d0  xor     r9d, r9d; TitleIndex
0x14000a1d3  mov     [rsp+0A0h+Class], 0; Class
0x14000a1dc  mov     edx, 20019h; DesiredAccess
0x14000a1e1  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x14000a1e9  mov     rcx, rdi; KeyHandle
0x14000a1ec  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14000a1f0  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000a1f5  call    cs:__imp_ZwCreateKey
0x14000a1fc  nop     dword ptr [rax+rax+00h]
0x14000a201  mov     ebx, eax
0x14000a203  test    eax, eax
0x14000a205  jns     short loc_14000A247
0x14000a207  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a20e  lea     rdx, WPP_GLOBAL_Control
0x14000a215  cmp     rcx, rdx
0x14000a218  jz      loc_14000A2E3
0x14000a21e  mov     edx, [rcx+2Ch]
0x14000a221  test    dl, 2
0x14000a224  jz      loc_14000A2E3
0x14000a22a  mov     rcx, [rcx+18h]
0x14000a22e  lea     r8, WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids
0x14000a235  mov     edx, 11h
0x14000a23a  mov     r9d, eax
0x14000a23d  call    WPP_SF_d
0x14000a242  jmp     loc_14000A2E3
0x14000a247  lea     rdx, SourceString; "Parameters"
0x14000a24e  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14000a252  call    cs:__imp_RtlInitUnicodeString
0x14000a259  nop     dword ptr [rax+rax+00h]
0x14000a25e  mov     rax, [rdi]
0x14000a261  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14000a265  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x14000a269  xorps   xmm0, xmm0
0x14000a26c  lea     rax, [rbp+57h+DestinationString]
0x14000a270  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14000a277  mov     edx, 20019h; DesiredAccess
0x14000a27c  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14000a280  mov     rcx, rsi; KeyHandle
0x14000a283  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14000a28a  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000a28f  call    cs:__imp_ZwOpenKey
0x14000a296  nop     dword ptr [rax+rax+00h]
0x14000a29b  mov     ebx, eax
0x14000a29d  test    eax, eax
0x14000a29f  jns     short loc_14000A2E3
0x14000a2a1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a2a8  lea     rdx, WPP_GLOBAL_Control
0x14000a2af  cmp     rcx, rdx
0x14000a2b2  jz      short loc_14000A2D4
0x14000a2b4  mov     edx, [rcx+2Ch]
0x14000a2b7  test    dl, 2
0x14000a2ba  jz      short loc_14000A2D4
0x14000a2bc  mov     rcx, [rcx+18h]
0x14000a2c0  lea     r8, WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids
0x14000a2c7  mov     edx, 12h
0x14000a2cc  mov     r9d, eax
0x14000a2cf  call    WPP_SF_d
0x14000a2d4  mov     rcx, [rdi]; Handle
0x14000a2d7  call    cs:__imp_ZwClose
0x14000a2de  nop     dword ptr [rax+rax+00h]
0x14000a2e3  mov     eax, ebx
0x14000a2e5  add     rsp, 88h
0x14000a2ec  pop     rdi
0x14000a2ed  pop     rsi
0x14000a2ee  pop     rbx
0x14000a2ef  pop     rbp
0x14000a2f0  retn
```
