# AppendAliasDomainNameToUnicodeString(_UNICODE_STRING *,void *)

- ea: `0x18003d794`
- end: `0x18003d824`
- name: `?AppendAliasDomainNameToUnicodeString@@YAJPEAU_UNICODE_STRING@@PEAX@Z`
- size: `144`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800401f0`

## callees

- `0x18003d794`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18003d80d`
- `ntdll!RtlFreeUnicodeString` at `0x18003d80d`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18003d7cf`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18003d7cf`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18003d7fc`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18003d7fc`
- `ntdll!RtlSubAuthorityCountSid` at `0x18003d7ac`
- `ntdll!RtlSubAuthorityCountSid` at `0x18003d7b7`
- `ntdll!RtlSubAuthorityCountSid` at `0x18003d7de`
- `ntdll!RtlSubAuthorityCountSid` at `0x18003d7ac`
- `ntdll!RtlSubAuthorityCountSid` at `0x18003d7b7`
- `ntdll!RtlSubAuthorityCountSid` at `0x18003d7de`

## pseudocode

```c
__int64 __fastcall AppendAliasDomainNameToUnicodeString(struct _UNICODE_STRING *a1, void *a2)
{
  UCHAR v3; // bl
  __int64 result; // rax
  struct _UNICODE_STRING UnicodeString; // [rsp+20h] [rbp-18h] BYREF

  UnicodeString = 0;
  v3 = *RtlSubAuthorityCountSid(a2);
  *RtlSubAuthorityCountSid(a2) = v3 - 1;
  dword_1800EF708 = RtlConvertSidToUnicodeString(&UnicodeString, a2, 1u);
  *RtlSubAuthorityCountSid(a2) = v3;
  result = (unsigned int)dword_1800EF708;
  if ( dword_1800EF708 >= 0 )
  {
    dword_1800EF708 = RtlAppendUnicodeStringToString(&KeyName, &UnicodeString);
    RtlFreeUnicodeString(&UnicodeString);
    return (unsigned int)dword_1800EF708;
  }
  return result;
}

```

## disassembly

```asm
0x18003d794  mov     [rsp+arg_0], rbx
0x18003d799  push    rdi
0x18003d79a  sub     rsp, 30h
0x18003d79e  xorps   xmm0, xmm0
0x18003d7a1  mov     rcx, rdx; Sid
0x18003d7a4  movups  xmmword ptr [rsp+38h+UnicodeString.Length], xmm0
0x18003d7a9  mov     rdi, rdx
0x18003d7ac  call    cs:__imp_RtlSubAuthorityCountSid
0x18003d7b2  mov     rcx, rdi; Sid
0x18003d7b5  mov     bl, [rax]
0x18003d7b7  call    cs:__imp_RtlSubAuthorityCountSid
0x18003d7bd  mov     cl, bl
0x18003d7bf  mov     r8b, 1; AllocateDestinationString
0x18003d7c2  sub     cl, r8b
0x18003d7c5  mov     rdx, rdi; Sid
0x18003d7c8  mov     [rax], cl
0x18003d7ca  lea     rcx, [rsp+38h+UnicodeString]; UnicodeString
0x18003d7cf  call    cs:__imp_RtlConvertSidToUnicodeString
0x18003d7d5  mov     rcx, rdi; Sid
0x18003d7d8  mov     cs:dword_1800EF708, eax
0x18003d7de  call    cs:__imp_RtlSubAuthorityCountSid
0x18003d7e4  mov     [rax], bl
0x18003d7e6  mov     eax, cs:dword_1800EF708
0x18003d7ec  test    eax, eax
0x18003d7ee  js      short loc_18003D819
0x18003d7f0  lea     rdx, [rsp+38h+UnicodeString]; Source
0x18003d7f5  lea     rcx, KeyName; Destination
0x18003d7fc  call    cs:__imp_RtlAppendUnicodeStringToString
0x18003d802  lea     rcx, [rsp+38h+UnicodeString]; UnicodeString
0x18003d807  mov     cs:dword_1800EF708, eax
0x18003d80d  call    cs:__imp_RtlFreeUnicodeString
0x18003d813  mov     eax, cs:dword_1800EF708
0x18003d819  mov     rbx, [rsp+38h+arg_0]
0x18003d81e  add     rsp, 30h
0x18003d822  pop     rdi
0x18003d823  retn
```
