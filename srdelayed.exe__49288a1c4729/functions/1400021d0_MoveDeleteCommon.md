# MoveDeleteCommon

- ea: `0x1400021d0`
- end: `0x140002398`
- name: `MoveDeleteCommon`
- size: `456`
- prototype: `__int64 __fastcall(HANDLE *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140001680`
- `0x140001700`

## callees

- `0x1400021d0`
- `0x140003770`

## import_xrefs

- `ntdll!NtSetInformationFile` at `0x1400022b0`
- `ntdll!NtSetInformationFile` at `0x1400022b0`
- `ntdll!NtClose` at `0x1400022c2`
- `ntdll!NtClose` at `0x140002376`
- `ntdll!NtClose` at `0x1400022c2`
- `ntdll!NtClose` at `0x140002376`
- `ntdll!NtQueryInformationFile` at `0x14000234f`
- `ntdll!NtQueryInformationFile` at `0x14000234f`
- `ntdll!NtOpenFile` at `0x140002273`
- `ntdll!NtOpenFile` at `0x140002324`
- `ntdll!NtOpenFile` at `0x140002273`
- `ntdll!NtOpenFile` at `0x140002324`

## pseudocode

```c
__int64 __fastcall MoveDeleteCommon(HANDLE *a1, struct _UNICODE_STRING *a2, struct _UNICODE_STRING *a3, void *a4)
{
  NTSTATUS v7; // ebx
  HANDLE v8; // rcx
  HANDLE Handle; // [rsp+30h] [rbp-89h] BYREF
  void *FileHandle; // [rsp+38h] [rbp-81h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-79h] BYREF
  struct _IO_STATUS_BLOCK v13; // [rsp+50h] [rbp-69h] BYREF
  struct _OBJECT_ATTRIBUTES v14; // [rsp+60h] [rbp-59h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-29h] BYREF
  __int128 FileInformation; // [rsp+C0h] [rbp+7h] BYREF
  __int128 v17; // [rsp+D0h] [rbp+17h]
  __int64 v18; // [rsp+E0h] [rbp+27h]

  ObjectAttributes.ObjectName = a3;
  Handle = 0;
  v18 = 0;
  ObjectAttributes.RootDirectory = 0;
  FileHandle = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  v13 = 0;
  memset(&v14, 0, sizeof(v14));
  IoStatusBlock = 0;
  FileInformation = 0;
  v17 = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = NtOpenFile(&FileHandle, 0x100100u, &ObjectAttributes, &IoStatusBlock, 3u, 0x204020u);
  if ( v7 >= 0 )
  {
    v18 = 128;
    FileInformation = 0;
    v17 = 0;
    v7 = NtSetInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 0x28u, FileBasicInformation);
  }
  if ( FileHandle )
    NtClose(FileHandle);
  if ( (int)(v7 + 0x80000000) >= 0 && v7 != -1073741772
    || (v14.Length = 48,
        v14.RootDirectory = 0,
        v14.Attributes = 64,
        v14.ObjectName = a2,
        *(_OWORD *)&v14.SecurityDescriptor = 0,
        v7 = NtOpenFile(&Handle, 0x110080u, &v14, &v13, 7u, 0x204020u),
        v7 < 0)
    || a4 && (v7 = NtQueryInformationFile(Handle, &v13, a4, 0x28u, FileBasicInformation), v7 < 0) )
  {
    v8 = Handle;
  }
  else
  {
    v8 = 0;
    *a1 = Handle;
    Handle = 0;
  }
  if ( v8 )
    NtClose(v8);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400021d0  push    rbp
0x1400021d2  push    rbx
0x1400021d3  push    rsi
0x1400021d4  push    rdi
0x1400021d5  push    r14
0x1400021d7  lea     rbp, [rsp-37h]
0x1400021dc  sub     rsp, 0F0h
0x1400021e3  mov     rax, cs:__security_cookie
0x1400021ea  xor     rax, rsp
0x1400021ed  mov     [rbp+57h+var_28], rax
0x1400021f1  xorps   xmm1, xmm1
0x1400021f4  mov     [rbp+57h+ObjectAttributes.ObjectName], r8
0x1400021f8  xorps   xmm0, xmm0
0x1400021fb  mov     [rsp+110h+OpenOptions], 204020h; OpenOptions
0x140002203  xor     eax, eax
0x140002205  mov     [rsp+110h+Handle], 0
0x14000220e  mov     rdi, r9
0x140002211  mov     [rbp+57h+var_30], rax
0x140002215  mov     r14, rdx
0x140002218  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x14000221c  mov     rsi, rcx
0x14000221f  mov     [rsp+110h+FileHandle], 0
0x140002228  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14000222c  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140002234  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140002238  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x140002240  mov     edx, 100100h; DesiredAccess
0x140002245  mov     [rsp+110h+ShareAccess], 3; ShareAccess
0x14000224d  lea     rcx, [rsp+110h+FileHandle]; FileHandle
0x140002252  movups  xmmword ptr [rbp+57h+var_C0], xmm0
0x140002256  movups  xmmword ptr [rbp+57h+var_B0.Length], xmm1
0x14000225a  movups  xmmword ptr [rbp+57h+var_B0.ObjectName], xmm1
0x14000225e  movups  xmmword ptr [rbp+57h+var_B0.SecurityDescriptor], xmm1
0x140002262  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140002266  movups  [rbp+57h+FileInformation], xmm1
0x14000226a  movups  [rbp+57h+var_40], xmm1
0x14000226e  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140002273  call    cs:__imp_NtOpenFile
0x140002279  mov     ebx, eax
0x14000227b  test    eax, eax
0x14000227d  js      short loc_1400022B8
0x14000227f  mov     rcx, [rsp+110h+FileHandle]; FileHandle
0x140002284  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x140002288  xor     eax, eax
0x14000228a  mov     [rsp+110h+ShareAccess], 4; FileInformationClass
0x140002292  xorps   xmm0, xmm0
0x140002295  mov     [rbp+57h+var_30], rax
0x140002299  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14000229d  mov     dword ptr [rbp+57h+var_30], 80h
0x1400022a4  movups  [rbp+57h+FileInformation], xmm0
0x1400022a8  lea     r9d, [rax+28h]; Length
0x1400022ac  movups  [rbp+57h+var_40], xmm0
0x1400022b0  call    cs:__imp_NtSetInformationFile
0x1400022b6  mov     ebx, eax
0x1400022b8  mov     rcx, [rsp+110h+FileHandle]; Handle
0x1400022bd  test    rcx, rcx
0x1400022c0  jz      short loc_1400022C8
0x1400022c2  call    cs:__imp_NtClose
0x1400022c8  mov     ecx, 80000000h
0x1400022cd  lea     eax, [rbx+rcx]
0x1400022d0  test    ecx, eax
0x1400022d2  jnz     short loc_1400022E0
0x1400022d4  cmp     ebx, 0C0000034h
0x1400022da  jnz     loc_14000236C
0x1400022e0  xorps   xmm0, xmm0
0x1400022e3  mov     [rsp+110h+OpenOptions], 204020h; OpenOptions
0x1400022eb  lea     r9, [rbp+57h+var_C0]; IoStatusBlock
0x1400022ef  mov     [rbp+57h+var_B0.Length], 30h ; '0'
0x1400022f6  lea     r8, [rbp+57h+var_B0]; ObjectAttributes
0x1400022fa  mov     [rbp+57h+var_B0.RootDirectory], 0
0x140002302  mov     edx, 110080h; DesiredAccess
0x140002307  mov     [rbp+57h+var_B0.Attributes], 40h ; '@'
0x14000230e  lea     rcx, [rsp+110h+Handle]; FileHandle
0x140002313  mov     [rbp+57h+var_B0.ObjectName], r14
0x140002317  movdqu  xmmword ptr [rbp+57h+var_B0.SecurityDescriptor], xmm0
0x14000231c  mov     [rsp+110h+ShareAccess], 7; ShareAccess
0x140002324  call    cs:__imp_NtOpenFile
0x14000232a  mov     ebx, eax
0x14000232c  test    eax, eax
0x14000232e  js      short loc_14000236C
0x140002330  test    rdi, rdi
0x140002333  jz      short loc_14000235B
0x140002335  mov     rcx, [rsp+110h+Handle]; FileHandle
0x14000233a  lea     rdx, [rbp+57h+var_C0]; IoStatusBlock
0x14000233e  mov     r9d, 28h ; '('; Length
0x140002344  mov     [rsp+110h+ShareAccess], 4; FileInformationClass
0x14000234c  mov     r8, rdi; FileInformation
0x14000234f  call    cs:__imp_NtQueryInformationFile
0x140002355  mov     ebx, eax
0x140002357  test    eax, eax
0x140002359  js      short loc_14000236C
0x14000235b  mov     rax, [rsp+110h+Handle]
0x140002360  xor     ecx, ecx
0x140002362  mov     [rsi], rax
0x140002365  mov     [rsp+110h+Handle], rcx
0x14000236a  jmp     short loc_140002371
0x14000236c  mov     rcx, [rsp+110h+Handle]; Handle
0x140002371  test    rcx, rcx
0x140002374  jz      short loc_14000237C
0x140002376  call    cs:__imp_NtClose
0x14000237c  mov     eax, ebx
0x14000237e  mov     rcx, [rbp+57h+var_28]
0x140002382  xor     rcx, rsp; StackCookie
0x140002385  call    __security_check_cookie
0x14000238a  add     rsp, 0F0h
0x140002391  pop     r14
0x140002393  pop     rdi
0x140002394  pop     rsi
0x140002395  pop     rbx
0x140002396  pop     rbp
0x140002397  retn
```
