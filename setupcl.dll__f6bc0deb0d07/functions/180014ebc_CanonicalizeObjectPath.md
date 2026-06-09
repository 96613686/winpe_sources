# CanonicalizeObjectPath

- ea: `0x180014ebc`
- end: `0x180014f99`
- name: `CanonicalizeObjectPath`
- size: `221`
- prototype: `__int64 __fastcall(PCWSTR SourceString, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180004c88`
- `0x1800092bc`

## callees

- `0x180014ebc`
- `0x180014fa0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180014f0a`
- `ntdll!RtlInitUnicodeString` at `0x180014f0a`
- `ntdll!NtClose` at `0x180014f75`
- `ntdll!NtClose` at `0x180014f75`
- `ntdll!NtOpenFile` at `0x180014f57`
- `ntdll!NtOpenFile` at `0x180014f57`

## pseudocode

```c
__int64 __fastcall CanonicalizeObjectPath(PCWSTR SourceString, __int64 a2)
{
  NTSTATUS v2; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-50h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  void *FileHandle; // [rsp+90h] [rbp+10h] BYREF

  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  if ( !SourceString || !a2 )
    return 3221225485LL;
  FileHandle = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v2 = NtOpenFile(&FileHandle, 0x100000u, &ObjectAttributes, &IoStatusBlock, 7u, 0x10u);
  if ( v2 >= 0 )
  {
    v2 = CanonicalizeObjectPathByHandle(FileHandle);
    NtClose(FileHandle);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180014ebc  mov     [rsp-8+arg_8], rbx
0x180014ec1  mov     [rsp-8+arg_10], rdi
0x180014ec6  push    rbp
0x180014ec7  mov     rbp, rsp
0x180014eca  sub     rsp, 80h
0x180014ed1  xorps   xmm0, xmm0
0x180014ed4  xor     eax, eax
0x180014ed6  mov     rdi, rdx
0x180014ed9  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180014edd  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180014ee1  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180014ee5  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180014ee9  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x180014eed  test    rcx, rcx
0x180014ef0  jz      loc_180014F7F
0x180014ef6  test    rdx, rdx
0x180014ef9  jz      loc_180014F7F
0x180014eff  mov     rdx, rcx; SourceString
0x180014f02  mov     [rbp+FileHandle], rax
0x180014f06  lea     rcx, [rbp+DestinationString]; DestinationString
0x180014f0a  call    cs:__imp_RtlInitUnicodeString
0x180014f10  lea     rax, [rbp+DestinationString]
0x180014f14  mov     [rsp+80h+OpenOptions], 10h; OpenOptions
0x180014f1c  xorps   xmm0, xmm0
0x180014f1f  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180014f23  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x180014f27  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180014f2e  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180014f32  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180014f3a  mov     edx, 100000h; DesiredAccess
0x180014f3f  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180014f46  lea     rcx, [rbp+FileHandle]; FileHandle
0x180014f4a  mov     [rsp+80h+ShareAccess], 7; ShareAccess
0x180014f52  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180014f57  call    cs:__imp_NtOpenFile
0x180014f5d  mov     ebx, eax
0x180014f5f  test    eax, eax
0x180014f61  js      short loc_180014F7B
0x180014f63  mov     rcx, [rbp+FileHandle]; Handle
0x180014f67  mov     rdx, rdi
0x180014f6a  call    CanonicalizeObjectPathByHandle
0x180014f6f  mov     rcx, [rbp+FileHandle]; Handle
0x180014f73  mov     ebx, eax
0x180014f75  call    cs:__imp_NtClose
0x180014f7b  mov     eax, ebx
0x180014f7d  jmp     short loc_180014F84
0x180014f7f  mov     eax, 0C000000Dh
0x180014f84  lea     r11, [rsp+80h+var_s0]
0x180014f8c  mov     rbx, [r11+18h]
0x180014f90  mov     rdi, [r11+20h]
0x180014f94  mov     rsp, r11
0x180014f97  pop     rbp
0x180014f98  retn
```
