# OpenOrCreateAccountRidKey(void *,void *,void * *)

- ea: `0x1800400ac`
- end: `0x1800401e7`
- name: `?OpenOrCreateAccountRidKey@@YAJPEAX0PEAPEAX@Z`
- size: `315`
- prototype: `NTSTATUS __fastcall(PSID Sid, HANDLE KeyHandle, HANDLE *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004b9c4`

## callees

- `0x180020610`
- `0x1800400ac`

## import_xrefs

- `ntdll!RtlpNtSetValueKey` at `0x1800401bb`
- `ntdll!RtlpNtSetValueKey` at `0x1800401d2`
- `ntdll!RtlpNtSetValueKey` at `0x1800401bb`
- `ntdll!RtlpNtSetValueKey` at `0x1800401d2`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800400d7`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800400ef`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800400d7`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800400ef`
- `ntdll!RtlpNtCreateKey` at `0x180040167`
- `ntdll!RtlpNtCreateKey` at `0x180040167`
- `ntdll!RtlSubAuthoritySid` at `0x1800400fd`
- `ntdll!RtlSubAuthoritySid` at `0x1800400fd`
- `ntdll!RtlpNtQueryValueKey` at `0x18004019a`
- `ntdll!RtlpNtQueryValueKey` at `0x18004019a`

## pseudocode

```c
NTSTATUS __fastcall OpenOrCreateAccountRidKey(PSID Sid, HANDLE KeyHandle, HANDLE *a3)
{
  NTSTATUS result; // eax
  PUCHAR v7; // rax
  ULONG v8; // ecx
  unsigned int v9; // edx
  unsigned int v10; // r8d
  ULONG Disposition; // [rsp+30h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-40h] BYREF
  ULONG Type; // [rsp+B8h] [rbp+40h] BYREF

  Disposition = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( !RtlSubAuthorityCountSid(Sid) )
    return -1073741704;
  v7 = RtlSubAuthorityCountSid(Sid);
  v8 = *RtlSubAuthoritySid(Sid, (unsigned int)*v7 - 1);
  KeyName.Length = 0;
  dword_1800EF708 = SampRtlConvertUlongToUnicodeString(v8, v9, v10, 0, &KeyName);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = KeyHandle;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &KeyName;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = RtlpNtCreateKey(a3, 0x2001Fu, &ObjectAttributes, 0, 0, &Disposition);
  dword_1800EF708 = result;
  if ( result >= 0 && Disposition == 1 )
  {
    Type = 0;
    dword_1800EF708 = RtlpNtQueryValueKey(KeyHandle, &Type, 0, 0, 0);
    if ( dword_1800EF708 >= 0 )
      dword_1800EF708 = RtlpNtSetValueKey(KeyHandle, ++Type, 0, 0);
    result = RtlpNtSetValueKey(*a3, 0, 0, 0);
    dword_1800EF708 = result;
  }
  return result;
}

```

## disassembly

```asm
0x1800400ac  push    rbp
0x1800400ae  push    rbx
0x1800400af  push    rsi
0x1800400b0  push    rdi
0x1800400b1  mov     rbp, rsp
0x1800400b4  sub     rsp, 78h
0x1800400b8  xorps   xmm0, xmm0
0x1800400bb  mov     [rbp+var_48], 0
0x1800400c2  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800400c6  mov     rsi, r8
0x1800400c9  mov     rbx, rdx
0x1800400cc  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800400d0  mov     rdi, rcx
0x1800400d3  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800400d7  call    cs:__imp_RtlSubAuthorityCountSid
0x1800400dd  test    rax, rax
0x1800400e0  jnz     short loc_1800400EC
0x1800400e2  mov     eax, 0C0000078h
0x1800400e7  jmp     loc_1800401DE
0x1800400ec  mov     rcx, rdi; Sid
0x1800400ef  call    cs:__imp_RtlSubAuthorityCountSid
0x1800400f5  mov     rcx, rdi; Sid
0x1800400f8  movzx   edx, byte ptr [rax]
0x1800400fb  dec     edx; SubAuthority
0x1800400fd  call    cs:__imp_RtlSubAuthoritySid
0x180040103  lea     rdi, KeyName
0x18004010a  xor     r9d, r9d; unsigned __int8
0x18004010d  mov     [rsp+78h+Class], rdi; struct _UNICODE_STRING *
0x180040112  mov     ecx, [rax]; Value
0x180040114  xor     eax, eax
0x180040116  mov     cs:KeyName.Length, ax
0x18004011d  call    ?SampRtlConvertUlongToUnicodeString@@YAJKKKEPEAU_UNICODE_STRING@@@Z; SampRtlConvertUlongToUnicodeString(ulong,ulong,ulong,uchar,_UNICODE_STRING *)
0x180040122  mov     cs:dword_1800EF708, eax
0x180040128  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18004012c  lea     rax, [rbp+var_48]
0x180040130  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180040137  xorps   xmm0, xmm0
0x18004013a  mov     [rsp+78h+Disposition], rax; Disposition
0x18004013f  xor     r9d, r9d; TitleIndex
0x180040142  mov     [rsp+78h+Class], 0; Class
0x18004014b  mov     edx, 2001Fh; DesiredAccess
0x180040150  mov     [rbp+ObjectAttributes.RootDirectory], rbx
0x180040154  mov     rcx, rsi; KeyHandle
0x180040157  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18004015e  mov     [rbp+ObjectAttributes.ObjectName], rdi
0x180040162  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180040167  call    cs:__imp_RtlpNtCreateKey
0x18004016d  mov     cs:dword_1800EF708, eax
0x180040173  test    eax, eax
0x180040175  js      short loc_1800401DE
0x180040177  cmp     [rbp+var_48], 1
0x18004017b  jnz     short loc_1800401DE
0x18004017d  xor     r9d, r9d; DataLength
0x180040180  mov     [rbp+Type], 0
0x180040187  xor     r8d, r8d; Data
0x18004018a  mov     [rsp+78h+Class], 0; Unused
0x180040193  lea     rdx, [rbp+Type]; Type
0x180040197  mov     rcx, rbx; KeyHandle
0x18004019a  call    cs:__imp_RtlpNtQueryValueKey
0x1800401a0  mov     cs:dword_1800EF708, eax
0x1800401a6  test    eax, eax
0x1800401a8  js      short loc_1800401C7
0x1800401aa  mov     edx, [rbp+Type]
0x1800401ad  xor     r9d, r9d; DataLength
0x1800401b0  inc     edx; Type
0x1800401b2  xor     r8d, r8d; Data
0x1800401b5  mov     rcx, rbx; KeyHandle
0x1800401b8  mov     [rbp+Type], edx
0x1800401bb  call    cs:__imp_RtlpNtSetValueKey
0x1800401c1  mov     cs:dword_1800EF708, eax
0x1800401c7  mov     rcx, [rsi]; KeyHandle
0x1800401ca  xor     r9d, r9d; DataLength
0x1800401cd  xor     r8d, r8d; Data
0x1800401d0  xor     edx, edx; Type
0x1800401d2  call    cs:__imp_RtlpNtSetValueKey
0x1800401d8  mov     cs:dword_1800EF708, eax
0x1800401de  add     rsp, 78h
0x1800401e2  pop     rdi
0x1800401e3  pop     rsi
0x1800401e4  pop     rbx
0x1800401e5  pop     rbp
0x1800401e6  retn
```
