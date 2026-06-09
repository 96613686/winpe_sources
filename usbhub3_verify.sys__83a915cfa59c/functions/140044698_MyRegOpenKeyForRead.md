# MyRegOpenKeyForRead

- ea: `0x140044698`
- end: `0x140044717`
- name: `MyRegOpenKeyForRead`
- size: `127`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140043784`
- `0x140043a24`
- `0x140043db8`
- `0x140043ebc`
- `0x140044054`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400446c1`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400446c1`
- `ntoskrnl!ZwOpenKey` at `0x1400446ff`
- `ntoskrnl!ZwOpenKey` at `0x1400446ff`

## pseudocode

```c
NTSTATUS __fastcall MyRegOpenKeyForRead(__int64 a1, const WCHAR *a2, void **a3)
{
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF

  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  return ZwOpenKey(a3, 0x20019u, &ObjectAttributes);
}

```

## disassembly

```asm
0x140044698  mov     [rsp-8+arg_0], rbx
0x14004469d  push    rbp
0x14004469e  mov     rbp, rsp
0x1400446a1  sub     rsp, 60h
0x1400446a5  xorps   xmm0, xmm0
0x1400446a8  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400446ac  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1400446b0  xor     eax, eax
0x1400446b2  mov     rbx, r8
0x1400446b5  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1400446b9  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1400446bd  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400446c1  call    cs:__imp_RtlInitUnicodeString
0x1400446c8  nop     dword ptr [rax+rax+00h]
0x1400446cd  lea     rax, [rbp+DestinationString]
0x1400446d1  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400446d8  xorps   xmm0, xmm0
0x1400446db  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1400446df  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400446e3  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1400446eb  mov     edx, 20019h; DesiredAccess
0x1400446f0  mov     [rbp+ObjectAttributes.Attributes], 240h
0x1400446f7  mov     rcx, rbx; KeyHandle
0x1400446fa  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400446ff  call    cs:__imp_ZwOpenKey
0x140044706  nop     dword ptr [rax+rax+00h]
0x14004470b  mov     rbx, [rsp+60h+arg_0]
0x140044710  add     rsp, 60h
0x140044714  pop     rbp
0x140044715  retn
```
