# OpenOrCreateAliasDomainKey(void *,void * *)

- ea: `0x1800401f0`
- end: `0x1800403c4`
- name: `?OpenOrCreateAliasDomainKey@@YAJPEAXPEAPEAX@Z`
- size: `468`
- prototype: `NTSTATUS __fastcall(void *, HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004b9c4`

## callees

- `0x18003d794`
- `0x1800401f0`

## import_xrefs

- `ntdll!RtlpNtSetValueKey` at `0x180040397`
- `ntdll!RtlpNtSetValueKey` at `0x180040397`
- `ntdll!RtlAppendUnicodeToString` at `0x18004023d`
- `ntdll!RtlAppendUnicodeToString` at `0x180040253`
- `ntdll!RtlAppendUnicodeToString` at `0x1800402f4`
- `ntdll!RtlAppendUnicodeToString` at `0x18004030a`
- `ntdll!RtlAppendUnicodeToString` at `0x18004023d`
- `ntdll!RtlAppendUnicodeToString` at `0x180040253`
- `ntdll!RtlAppendUnicodeToString` at `0x1800402f4`
- `ntdll!RtlAppendUnicodeToString` at `0x18004030a`
- `ntdll!RtlpNtCreateKey` at `0x1800402b4`
- `ntdll!RtlpNtCreateKey` at `0x1800402b4`
- `ntdll!RtlCopyUnicodeString` at `0x18004022d`
- `ntdll!RtlCopyUnicodeString` at `0x1800402e4`
- `ntdll!RtlCopyUnicodeString` at `0x18004022d`
- `ntdll!RtlCopyUnicodeString` at `0x1800402e4`
- `ntdll!NtClose` at `0x1800403a7`
- `ntdll!NtClose` at `0x1800403a7`
- `ntdll!RtlpNtQueryValueKey` at `0x180040375`
- `ntdll!RtlpNtQueryValueKey` at `0x180040375`
- `ntdll!RtlpNtOpenKey` at `0x180040347`
- `ntdll!RtlpNtOpenKey` at `0x180040347`

## pseudocode

```c
NTSTATUS __fastcall OpenOrCreateAliasDomainKey(void *a1, HANDLE KeyHandle)
{
  struct _UNICODE_STRING *v4; // rcx
  NTSTATUS result; // eax
  NTSTATUS appended; // eax
  HANDLE KeyHandlea; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-38h] BYREF
  ULONG Type; // [rsp+A0h] [rbp+30h] BYREF
  ULONG Disposition; // [rsp+A8h] [rbp+38h] BYREF

  Disposition = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  memset(&ObjectAttributes.ObjectName, 0, 32);
  RtlCopyUnicodeString(&KeyName, qword_1800EF7C8);
  dword_1800EF708 = RtlAppendUnicodeToString(&KeyName, L"\\Aliases");
  dword_1800EF708 = RtlAppendUnicodeToString(&KeyName, L"\\Members\\");
  dword_1800EF708 = AppendAliasDomainNameToUnicodeString(v4, a1);
  ObjectAttributes.RootDirectory = Handle;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &KeyName;
  result = RtlpNtCreateKey(KeyHandle, 0x2001Fu, &ObjectAttributes, 0, 0, &Disposition);
  dword_1800EF708 = result;
  if ( result >= 0 && Disposition == 1 )
  {
    KeyHandlea = 0;
    RtlCopyUnicodeString(&KeyName, qword_1800EF7C8);
    dword_1800EF708 = RtlAppendUnicodeToString(&KeyName, L"\\Aliases");
    appended = RtlAppendUnicodeToString(&KeyName, L"\\Members\\");
    ObjectAttributes.Length = 48;
    dword_1800EF708 = appended;
    ObjectAttributes.RootDirectory = Handle;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.ObjectName = &KeyName;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    result = RtlpNtOpenKey(&KeyHandlea, 0x2001Fu, &ObjectAttributes, 0);
    dword_1800EF708 = result;
    if ( result >= 0 )
    {
      Type = 0;
      dword_1800EF708 = RtlpNtQueryValueKey(KeyHandlea, &Type, 0, 0, 0);
      if ( dword_1800EF708 >= 0 )
        dword_1800EF708 = RtlpNtSetValueKey(KeyHandlea, ++Type, 0, 0);
      NtClose(KeyHandlea);
      return dword_1800EF708;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800401f0  mov     [rsp-18h+arg_0], rbx
0x1800401f5  push    rbp
0x1800401f6  push    rdi
0x1800401f7  push    r14
0x1800401f9  mov     rbp, rsp
0x1800401fc  sub     rsp, 70h
0x180040200  xorps   xmm0, xmm0
0x180040203  mov     [rbp+arg_18], 0
0x18004020a  mov     rdi, rdx
0x18004020d  lea     r14, KeyName
0x180040214  mov     rdx, cs:qword_1800EF7C8; SourceString
0x18004021b  mov     rbx, rcx
0x18004021e  mov     rcx, r14; DestinationString
0x180040221  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180040225  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180040229  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18004022d  call    cs:__imp_RtlCopyUnicodeString
0x180040233  lea     rdx, aAliases_0; "\\Aliases"
0x18004023a  mov     rcx, r14; Destination
0x18004023d  call    cs:__imp_RtlAppendUnicodeToString
0x180040243  lea     rdx, aMembers; "\\Members\\"
0x18004024a  mov     rcx, r14; Destination
0x18004024d  mov     cs:dword_1800EF708, eax
0x180040253  call    cs:__imp_RtlAppendUnicodeToString
0x180040259  mov     rdx, rbx; void *
0x18004025c  mov     cs:dword_1800EF708, eax
0x180040262  call    ?AppendAliasDomainNameToUnicodeString@@YAJPEAU_UNICODE_STRING@@PEAX@Z; AppendAliasDomainNameToUnicodeString(_UNICODE_STRING *,void *)
0x180040267  mov     cs:dword_1800EF708, eax
0x18004026d  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180040271  mov     rax, cs:Handle
0x180040278  xorps   xmm0, xmm0
0x18004027b  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x18004027f  mov     ebx, 30h ; '0'
0x180040284  lea     rax, [rbp+arg_18]
0x180040288  mov     [rbp+ObjectAttributes.Length], ebx
0x18004028b  mov     [rsp+70h+Disposition], rax; Disposition
0x180040290  xor     r9d, r9d; TitleIndex
0x180040293  mov     edx, 2001Fh; DesiredAccess
0x180040298  mov     [rsp+70h+Class], 0; Class
0x1800402a1  mov     rcx, rdi; KeyHandle
0x1800402a4  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x1800402ab  mov     [rbp+ObjectAttributes.ObjectName], r14
0x1800402af  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800402b4  call    cs:__imp_RtlpNtCreateKey
0x1800402ba  mov     cs:dword_1800EF708, eax
0x1800402c0  test    eax, eax
0x1800402c2  js      loc_1800403B3
0x1800402c8  cmp     [rbp+arg_18], 1
0x1800402cc  jnz     loc_1800403B3
0x1800402d2  mov     rdx, cs:qword_1800EF7C8; SourceString
0x1800402d9  mov     rcx, r14; DestinationString
0x1800402dc  mov     [rbp+KeyHandle], 0
0x1800402e4  call    cs:__imp_RtlCopyUnicodeString
0x1800402ea  lea     rdx, aAliases_0; "\\Aliases"
0x1800402f1  mov     rcx, r14; Destination
0x1800402f4  call    cs:__imp_RtlAppendUnicodeToString
0x1800402fa  lea     rdx, aMembers; "\\Members\\"
0x180040301  mov     rcx, r14; Destination
0x180040304  mov     cs:dword_1800EF708, eax
0x18004030a  call    cs:__imp_RtlAppendUnicodeToString
0x180040310  xorps   xmm0, xmm0
0x180040313  mov     [rbp+ObjectAttributes.Length], ebx
0x180040316  mov     cs:dword_1800EF708, eax
0x18004031c  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180040320  mov     rax, cs:Handle
0x180040327  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x18004032b  xor     r9d, r9d; Unused
0x18004032e  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x180040332  mov     edx, 2001Fh; DesiredAccess
0x180040337  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18004033e  mov     [rbp+ObjectAttributes.ObjectName], r14
0x180040342  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180040347  call    cs:__imp_RtlpNtOpenKey
0x18004034d  mov     cs:dword_1800EF708, eax
0x180040353  test    eax, eax
0x180040355  js      short loc_1800403B3
0x180040357  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18004035b  lea     rdx, [rbp+Type]; Type
0x18004035f  xor     r9d, r9d; DataLength
0x180040362  mov     [rbp+Type], 0
0x180040369  xor     r8d, r8d; Data
0x18004036c  mov     [rsp+70h+Class], 0; Unused
0x180040375  call    cs:__imp_RtlpNtQueryValueKey
0x18004037b  mov     cs:dword_1800EF708, eax
0x180040381  test    eax, eax
0x180040383  js      short loc_1800403A3
0x180040385  mov     edx, [rbp+Type]
0x180040388  xor     r9d, r9d; DataLength
0x18004038b  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18004038f  inc     edx; Type
0x180040391  xor     r8d, r8d; Data
0x180040394  mov     [rbp+Type], edx
0x180040397  call    cs:__imp_RtlpNtSetValueKey
0x18004039d  mov     cs:dword_1800EF708, eax
0x1800403a3  mov     rcx, [rbp+KeyHandle]; Handle
0x1800403a7  call    cs:__imp_NtClose
0x1800403ad  mov     eax, cs:dword_1800EF708
0x1800403b3  mov     rbx, [rsp+70h+arg_0]
0x1800403bb  add     rsp, 70h
0x1800403bf  pop     r14
0x1800403c1  pop     rdi
0x1800403c2  pop     rbp
0x1800403c3  retn
```
