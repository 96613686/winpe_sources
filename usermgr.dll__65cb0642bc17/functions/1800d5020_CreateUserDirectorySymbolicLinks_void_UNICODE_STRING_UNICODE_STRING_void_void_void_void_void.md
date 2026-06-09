# CreateUserDirectorySymbolicLinks(void *,_UNICODE_STRING *,_UNICODE_STRING *,void *,void * *,void * *,void * *,void * *)

- ea: `0x1800d5020`
- end: `0x1800d5212`
- name: `?CreateUserDirectorySymbolicLinks@@YAJPEAXPEAU_UNICODE_STRING@@10PEAPEAX222@Z`
- size: `498`
- prototype: `__int64 __fastcall(void *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, void *, PHANDLE, PHANDLE SymbolicLinkHandle, PHANDLE, PHANDLE)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800d5218`

## callees

- `0x1800d5020`

## import_xrefs

- `ntdll!NtCreateSymbolicLinkObject` at `0x1800d50c1`
- `ntdll!NtCreateSymbolicLinkObject` at `0x1800d510a`
- `ntdll!NtCreateSymbolicLinkObject` at `0x1800d5153`
- `ntdll!NtCreateSymbolicLinkObject` at `0x1800d5198`
- `ntdll!NtCreateSymbolicLinkObject` at `0x1800d50c1`
- `ntdll!NtCreateSymbolicLinkObject` at `0x1800d510a`
- `ntdll!NtCreateSymbolicLinkObject` at `0x1800d5153`
- `ntdll!NtCreateSymbolicLinkObject` at `0x1800d5198`
- `ntdll!NtClose` at `0x1800d51ac`
- `ntdll!NtClose` at `0x1800d51c1`
- `ntdll!NtClose` at `0x1800d51d6`
- `ntdll!NtClose` at `0x1800d51eb`
- `ntdll!NtClose` at `0x1800d51ac`
- `ntdll!NtClose` at `0x1800d51c1`
- `ntdll!NtClose` at `0x1800d51d6`
- `ntdll!NtClose` at `0x1800d51eb`
- `ntdll!RtlInitUnicodeString` at `0x1800d5086`
- `ntdll!RtlInitUnicodeString` at `0x1800d5086`

## pseudocode

```c
__int64 __fastcall CreateUserDirectorySymbolicLinks(
        void *a1,
        struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3,
        void *a4,
        PHANDLE a5,
        PHANDLE SymbolicLinkHandle,
        PHANDLE a7,
        PHANDLE a8)
{
  NTSTATUS v10; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF

  *a5 = 0;
  *SymbolicLinkHandle = 0;
  *a7 = 0;
  *a8 = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  RtlInitUnicodeString(&DestinationString, L"\\BaseNamedObjects");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&qword_1800FA9C0;
  ObjectAttributes.RootDirectory = a1;
  ObjectAttributes.Attributes = 130;
  ObjectAttributes.SecurityDescriptor = a4;
  ObjectAttributes.SecurityQualityOfService = 0;
  v10 = NtCreateSymbolicLinkObject(SymbolicLinkHandle, 0xF0001u, &ObjectAttributes, &DestinationString);
  if ( v10 < 0 )
    goto LABEL_16;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&qword_1800FA9D0;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = a1;
  ObjectAttributes.Attributes = 130;
  ObjectAttributes.SecurityDescriptor = a4;
  ObjectAttributes.SecurityQualityOfService = 0;
  v10 = NtCreateSymbolicLinkObject(a5, 0xF0001u, &ObjectAttributes, a2);
  if ( v10 < 0 )
    goto LABEL_16;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&qword_1800FA9A0;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = a1;
  ObjectAttributes.Attributes = 130;
  ObjectAttributes.SecurityDescriptor = a4;
  ObjectAttributes.SecurityQualityOfService = 0;
  v10 = NtCreateSymbolicLinkObject(a7, 0xF0001u, &ObjectAttributes, a2);
  if ( v10 < 0
    || (ObjectAttributes.ObjectName = (PUNICODE_STRING)L"02",
        ObjectAttributes.Length = 48,
        ObjectAttributes.RootDirectory = a1,
        ObjectAttributes.Attributes = 130,
        ObjectAttributes.SecurityDescriptor = a4,
        ObjectAttributes.SecurityQualityOfService = 0,
        v10 = NtCreateSymbolicLinkObject(a8, 0xF0001u, &ObjectAttributes, a3),
        v10 < 0) )
  {
LABEL_16:
    if ( *SymbolicLinkHandle )
    {
      NtClose(*SymbolicLinkHandle);
      *SymbolicLinkHandle = 0;
    }
    if ( *a5 )
    {
      NtClose(*a5);
      *a5 = 0;
    }
    if ( *a7 )
    {
      NtClose(*a7);
      *a7 = 0;
    }
    if ( *a8 )
    {
      NtClose(*a8);
      *a8 = 0;
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800d5020  mov     [rsp-38h+arg_0], rbx
0x1800d5025  mov     [rsp-38h+arg_10], r8
0x1800d502a  mov     [rsp-38h+Name], rdx
0x1800d502f  push    rbp
0x1800d5030  push    rsi
0x1800d5031  push    rdi
0x1800d5032  push    r12
0x1800d5034  push    r13
0x1800d5036  push    r14
0x1800d5038  push    r15
0x1800d503a  mov     rbp, rsp
0x1800d503d  sub     rsp, 60h
0x1800d5041  mov     r14, [rbp+arg_20]
0x1800d5045  lea     rdx, aBasenamedobjec; "\\BaseNamedObjects"
0x1800d504c  mov     r15, [rbp+SymbolicLinkHandle]
0x1800d5050  xor     ebx, ebx
0x1800d5052  mov     rsi, [rbp+arg_30]
0x1800d5056  xorps   xmm1, xmm1
0x1800d5059  mov     rdi, [rbp+arg_38]
0x1800d505d  mov     r13, rcx
0x1800d5060  mov     [r14], rbx
0x1800d5063  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800d5067  mov     [r15], rbx
0x1800d506a  xorps   xmm0, xmm0
0x1800d506d  mov     [rsi], rbx
0x1800d5070  mov     r12, r9
0x1800d5073  mov     [rdi], rbx
0x1800d5076  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800d507a  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm1
0x1800d507e  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm1
0x1800d5082  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm1
0x1800d5086  call    cs:__imp_RtlInitUnicodeString
0x1800d508c  lea     rax, qword_1800FA9C0
0x1800d5093  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800d509a  lea     r9, [rbp+DestinationString]; Name
0x1800d509e  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800d50a2  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800d50a6  mov     [rbp+ObjectAttributes.RootDirectory], r13
0x1800d50aa  mov     edx, 0F0001h; DesiredAccess
0x1800d50af  mov     [rbp+ObjectAttributes.Attributes], 82h
0x1800d50b6  mov     rcx, r15; SymbolicLinkHandle
0x1800d50b9  mov     [rbp+ObjectAttributes.SecurityDescriptor], r12
0x1800d50bd  mov     [rbp+ObjectAttributes.SecurityQualityOfService], rbx
0x1800d50c1  call    cs:__imp_NtCreateSymbolicLinkObject
0x1800d50c7  mov     ebx, eax
0x1800d50c9  test    eax, eax
0x1800d50cb  js      loc_1800D51A4
0x1800d50d1  mov     r9, [rbp+Name]; Name
0x1800d50d5  lea     rax, qword_1800FA9D0
0x1800d50dc  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800d50e0  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800d50e4  mov     edx, 0F0001h; DesiredAccess
0x1800d50e9  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800d50f0  mov     rcx, r14; SymbolicLinkHandle
0x1800d50f3  mov     [rbp+ObjectAttributes.RootDirectory], r13
0x1800d50f7  mov     [rbp+ObjectAttributes.Attributes], 82h
0x1800d50fe  mov     [rbp+ObjectAttributes.SecurityDescriptor], r12
0x1800d5102  mov     [rbp+ObjectAttributes.SecurityQualityOfService], 0
0x1800d510a  call    cs:__imp_NtCreateSymbolicLinkObject
0x1800d5110  mov     ebx, eax
0x1800d5112  test    eax, eax
0x1800d5114  js      loc_1800D51A4
0x1800d511a  mov     r9, [rbp+Name]; Name
0x1800d511e  lea     rax, qword_1800FA9A0
0x1800d5125  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800d5129  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800d512d  mov     edx, 0F0001h; DesiredAccess
0x1800d5132  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800d5139  mov     rcx, rsi; SymbolicLinkHandle
0x1800d513c  mov     [rbp+ObjectAttributes.RootDirectory], r13
0x1800d5140  mov     [rbp+ObjectAttributes.Attributes], 82h
0x1800d5147  mov     [rbp+ObjectAttributes.SecurityDescriptor], r12
0x1800d514b  mov     [rbp+ObjectAttributes.SecurityQualityOfService], 0
0x1800d5153  call    cs:__imp_NtCreateSymbolicLinkObject
0x1800d5159  mov     ebx, eax
0x1800d515b  test    eax, eax
0x1800d515d  js      short loc_1800D51A4
0x1800d515f  mov     r9, [rbp+arg_10]; Name
0x1800d5163  lea     rax, a02; "02"
0x1800d516a  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800d516e  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800d5172  mov     edx, 0F0001h; DesiredAccess
0x1800d5177  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800d517e  mov     rcx, rdi; SymbolicLinkHandle
0x1800d5181  mov     [rbp+ObjectAttributes.RootDirectory], r13
0x1800d5185  mov     [rbp+ObjectAttributes.Attributes], 82h
0x1800d518c  mov     [rbp+ObjectAttributes.SecurityDescriptor], r12
0x1800d5190  mov     [rbp+ObjectAttributes.SecurityQualityOfService], 0
0x1800d5198  call    cs:__imp_NtCreateSymbolicLinkObject
0x1800d519e  mov     ebx, eax
0x1800d51a0  test    eax, eax
0x1800d51a2  jns     short loc_1800D51F8
0x1800d51a4  mov     rcx, [r15]; Handle
0x1800d51a7  test    rcx, rcx
0x1800d51aa  jz      short loc_1800D51B9
0x1800d51ac  call    cs:__imp_NtClose
0x1800d51b2  mov     qword ptr [r15], 0
0x1800d51b9  mov     rcx, [r14]; Handle
0x1800d51bc  test    rcx, rcx
0x1800d51bf  jz      short loc_1800D51CE
0x1800d51c1  call    cs:__imp_NtClose
0x1800d51c7  mov     qword ptr [r14], 0
0x1800d51ce  mov     rcx, [rsi]; Handle
0x1800d51d1  test    rcx, rcx
0x1800d51d4  jz      short loc_1800D51E3
0x1800d51d6  call    cs:__imp_NtClose
0x1800d51dc  mov     qword ptr [rsi], 0
0x1800d51e3  mov     rcx, [rdi]; Handle
0x1800d51e6  test    rcx, rcx
0x1800d51e9  jz      short loc_1800D51F8
0x1800d51eb  call    cs:__imp_NtClose
0x1800d51f1  mov     qword ptr [rdi], 0
0x1800d51f8  mov     eax, ebx
0x1800d51fa  mov     rbx, [rsp+60h+arg_0]
0x1800d5202  add     rsp, 60h
0x1800d5206  pop     r15
0x1800d5208  pop     r14
0x1800d520a  pop     r13
0x1800d520c  pop     r12
0x1800d520e  pop     rdi
0x1800d520f  pop     rsi
0x1800d5210  pop     rbp
0x1800d5211  retn
```
