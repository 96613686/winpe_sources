# SmpDeleteFile

- ea: `0x140013fd8`
- end: `0x1400140bf`
- name: `SmpDeleteFile`
- size: `231`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140011d24`
- `0x140016018`

## callees

- `0x1400010ec`
- `0x140013fd8`
- `0x1400140c8`
- `0x1400168b8`

## import_xrefs

- `ntdll!NtOpenFile` at `0x140014038`
- `ntdll!NtOpenFile` at `0x140014038`
- `ntdll!NtClose` at `0x1400140a5`
- `ntdll!NtClose` at `0x1400140a5`

## string_xrefs

- `0x14001405a`: `SmpDeleteFile`

## pseudocode

```c
__int64 __fastcall SmpDeleteFile(struct _UNICODE_STRING *a1)
{
  NTSTATUS v2; // eax
  unsigned int v3; // ebx
  PWSTR Buffer; // r8
  __int64 v5; // rdx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *FileHandle; // [rsp+80h] [rbp+10h] BYREF

  ObjectAttributes.ObjectName = a1;
  FileHandle = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  IoStatusBlock = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v2 = NtOpenFile(&FileHandle, 0x10100u, &ObjectAttributes, &IoStatusBlock, 7u, 0x4040u);
  v3 = v2;
  if ( v2 < 0 )
  {
    if ( a1 )
      Buffer = a1->Buffer;
    else
      Buffer = 0;
    v5 = 11995;
LABEL_6:
    SmpLogFailureString("SmpDeleteFile", v5, Buffer, (unsigned int)v2);
    goto LABEL_13;
  }
  v2 = SmpSetTargetAttributes(FileHandle, 128);
  v3 = v2;
  if ( v2 < 0 )
  {
    if ( a1 )
      Buffer = a1->Buffer;
    else
      Buffer = 0;
    v5 = 12008;
    goto LABEL_6;
  }
  v3 = SmpDeleteTargetFile(FileHandle);
LABEL_13:
  if ( FileHandle )
    NtClose(FileHandle);
  return v3;
}

```

## disassembly

```asm
0x140013fd8  mov     [rsp-8+arg_8], rbx
0x140013fdd  mov     [rsp-8+arg_10], rdi
0x140013fe2  push    rbp
0x140013fe3  mov     rbp, rsp
0x140013fe6  sub     rsp, 70h
0x140013fea  xorps   xmm0, xmm0
0x140013fed  mov     [rbp+ObjectAttributes.ObjectName], rcx
0x140013ff1  xor     eax, eax
0x140013ff3  mov     [rsp+70h+OpenOptions], 4040h; OpenOptions
0x140013ffb  mov     rdi, rcx
0x140013ffe  mov     [rbp+FileHandle], rax
0x140014002  lea     rcx, [rbp+FileHandle]; FileHandle
0x140014006  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x14001400a  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x14001400e  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x140014016  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14001401a  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x140014022  mov     edx, 10100h; DesiredAccess
0x140014027  mov     [rsp+70h+ShareAccess], 7; ShareAccess
0x14001402f  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x140014033  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140014038  call    cs:__imp_NtOpenFile
0x14001403e  mov     ebx, eax
0x140014040  test    eax, eax
0x140014042  jns     short loc_140014068
0x140014044  test    rdi, rdi
0x140014047  jz      short loc_14001404F
0x140014049  mov     r8, [rdi+8]
0x14001404d  jmp     short loc_140014052
0x14001404f  xor     r8d, r8d
0x140014052  mov     edx, 2EDBh
0x140014057  mov     r9d, eax
0x14001405a  lea     rcx, aSmpdeletefile; "SmpDeleteFile"
0x140014061  call    SmpLogFailureString
0x140014066  jmp     short loc_14001409C
0x140014068  mov     rcx, [rbp+FileHandle]
0x14001406c  mov     edx, 80h
0x140014071  call    SmpSetTargetAttributes
0x140014076  mov     ebx, eax
0x140014078  test    eax, eax
0x14001407a  jns     short loc_140014091
0x14001407c  test    rdi, rdi
0x14001407f  jz      short loc_140014087
0x140014081  mov     r8, [rdi+8]
0x140014085  jmp     short loc_14001408A
0x140014087  xor     r8d, r8d
0x14001408a  mov     edx, 2EE8h
0x14001408f  jmp     short loc_140014057
0x140014091  mov     rcx, [rbp+FileHandle]
0x140014095  call    SmpDeleteTargetFile
0x14001409a  mov     ebx, eax
0x14001409c  mov     rcx, [rbp+FileHandle]; Handle
0x1400140a0  test    rcx, rcx
0x1400140a3  jz      short loc_1400140AB
0x1400140a5  call    cs:__imp_NtClose
0x1400140ab  lea     r11, [rsp+70h+var_s0]
0x1400140b0  mov     eax, ebx
0x1400140b2  mov     rbx, [r11+18h]
0x1400140b6  mov     rdi, [r11+20h]
0x1400140ba  mov     rsp, r11
0x1400140bd  pop     rbp
0x1400140be  retn
```
