# IsExistant

- ea: `0x140002064`
- end: `0x1400020d6`
- name: `IsExistant`
- size: `114`
- prototype: `bool __fastcall(struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400028a4`

## callees

- `0x140003770`

## import_xrefs

- `ntdll!NtQueryAttributesFile` at `0x1400020b6`
- `ntdll!NtQueryAttributesFile` at `0x1400020b6`

## pseudocode

```c
bool __fastcall IsExistant(struct _UNICODE_STRING *a1)
{
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-60h] BYREF
  _FILE_BASIC_INFORMATION FileInformation; // [rsp+50h] [rbp-30h] BYREF

  ObjectAttributes.ObjectName = a1;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  memset(&FileInformation, 0, sizeof(FileInformation));
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  return NtQueryAttributesFile(&ObjectAttributes, &FileInformation) >= 0;
}

```

## disassembly

```asm
0x140002064  push    rbp
0x140002066  mov     rbp, rsp
0x140002069  sub     rsp, 80h
0x140002070  mov     rax, cs:__security_cookie
0x140002077  xor     rax, rsp
0x14000207a  mov     [rbp+var_8], rax
0x14000207e  xorps   xmm0, xmm0
0x140002081  mov     [rbp+ObjectAttributes.ObjectName], rcx
0x140002085  xor     edx, edx
0x140002087  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x14000208f  mov     [rbp+ObjectAttributes.RootDirectory], rdx
0x140002093  lea     rcx, [rbp+ObjectAttributes]; ObjectAttributes
0x140002097  xor     eax, eax
0x140002099  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x1400020a1  lea     rdx, [rbp+FileInformation]; FileInformation
0x1400020a5  mov     qword ptr [rbp+FileInformation.FileAttributes], rax
0x1400020a9  movups  xmmword ptr [rbp+FileInformation.CreationTime], xmm0
0x1400020ad  movups  xmmword ptr [rbp+FileInformation.LastWriteTime], xmm0
0x1400020b1  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400020b6  call    cs:__imp_NtQueryAttributesFile
0x1400020bc  shr     eax, 1Fh
0x1400020bf  xor     al, 1
0x1400020c1  mov     rcx, [rbp+var_8]
0x1400020c5  xor     rcx, rsp; StackCookie
0x1400020c8  call    __security_check_cookie
0x1400020cd  add     rsp, 80h
0x1400020d4  pop     rbp
0x1400020d5  retn
```
