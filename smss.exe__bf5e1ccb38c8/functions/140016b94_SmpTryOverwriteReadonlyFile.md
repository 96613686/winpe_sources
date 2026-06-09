# SmpTryOverwriteReadonlyFile

- ea: `0x140016b94`
- end: `0x140016d31`
- name: `SmpTryOverwriteReadonlyFile`
- size: `413`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140015ae8`

## callees

- `0x1400130f4`
- `0x1400158e4`
- `0x140015ef8`
- `0x1400168b8`
- `0x140016b94`
- `0x14001cc40`

## import_xrefs

- `ntdll!NtClose` at `0x140016c95`
- `ntdll!NtClose` at `0x140016cf7`
- `ntdll!NtClose` at `0x140016d06`
- `ntdll!NtClose` at `0x140016c95`
- `ntdll!NtClose` at `0x140016cf7`
- `ntdll!NtClose` at `0x140016d06`
- `ntdll!NtQueryAttributesFile` at `0x140016c05`
- `ntdll!NtQueryAttributesFile` at `0x140016c05`

## pseudocode

```c
__int64 __fastcall SmpTryOverwriteReadonlyFile(struct _UNICODE_STRING *a1, void *a2, char a3)
{
  __int64 v5; // rdi
  int v7; // ebx
  char v8; // al
  HANDLE Handle; // [rsp+30h] [rbp-39h] BYREF
  __int64 v11; // [rsp+38h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-29h] BYREF
  struct _FILE_BASIC_INFORMATION FileInformation; // [rsp+70h] [rbp+7h] BYREF

  ObjectAttributes.ObjectName = a1;
  Handle = 0;
  ObjectAttributes.RootDirectory = 0;
  v5 = -1;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  v11 = -1;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  memset(&FileInformation, 0, sizeof(FileInformation));
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = NtQueryAttributesFile(&ObjectAttributes, &FileInformation);
  if ( v7 >= 0 )
  {
    if ( (FileInformation.FileAttributes & 0x10) != 0 )
    {
      v7 = -1073741638;
    }
    else if ( (FileInformation.FileAttributes & 1) != 0 )
    {
      if ( a3 != 1 || (v8 = SmpCheckFolderForRedirections(a1, &v11), v5 = v11, v8) )
      {
        v7 = SmpOpenTargetFile(&Handle, 0x100100u, &ObjectAttributes, 1, 3u);
        if ( v7 >= 0 )
        {
          v7 = SmpSetTargetAttributes(Handle, FileInformation.FileAttributes & 0xFFFFFFFE);
          if ( v7 >= 0 )
          {
            NtClose(Handle);
            Handle = 0;
            v7 = SmpRenameTargetFile((const void **)a1, a2, 1, a3);
            if ( v7 < 0 )
            {
              if ( SmpOpenTargetFile(&Handle, 0x110100u, &ObjectAttributes, 1, 3u) >= 0 )
                SmpSetTargetAttributes(Handle, FileInformation.FileAttributes);
            }
            else
            {
              v7 = 0;
            }
          }
        }
      }
      else
      {
        v7 = -1073740533;
      }
    }
    else
    {
      v7 = -1073741823;
    }
  }
  if ( Handle )
    NtClose(Handle);
  if ( v5 != -1 )
    NtClose((HANDLE)v5);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140016b94  mov     [rsp-8+arg_10], rbx
0x140016b99  push    rbp
0x140016b9a  push    rsi
0x140016b9b  push    rdi
0x140016b9c  push    r14
0x140016b9e  push    r15
0x140016ba0  lea     rbp, [rsp-37h]
0x140016ba5  sub     rsp, 0A0h
0x140016bac  mov     rax, cs:__security_cookie
0x140016bb3  xor     rax, rsp
0x140016bb6  mov     [rbp+57h+var_28], rax
0x140016bba  xor     eax, eax
0x140016bbc  mov     [rbp+57h+ObjectAttributes.ObjectName], rcx
0x140016bc0  xorps   xmm0, xmm0
0x140016bc3  mov     qword ptr [rbp+57h+FileInformation.FileAttributes], rax
0x140016bc7  mov     r15, rdx
0x140016bca  mov     [rbp+57h+Handle], rax
0x140016bce  mov     rsi, rcx
0x140016bd1  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x140016bd5  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140016bd9  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140016be1  lea     rdx, [rbp+57h+FileInformation]; FileInformation
0x140016be5  mov     [rbp+57h+var_88], rdi
0x140016be9  lea     rcx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140016bed  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x140016bf5  movups  xmmword ptr [rbp+57h+FileInformation.CreationTime], xmm0
0x140016bf9  mov     r14b, r8b
0x140016bfc  movups  xmmword ptr [rbp+57h+FileInformation.LastWriteTime], xmm0
0x140016c00  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140016c05  call    cs:__imp_NtQueryAttributesFile
0x140016c0b  mov     ebx, eax
0x140016c0d  test    eax, eax
0x140016c0f  js      loc_140016CEE
0x140016c15  test    byte ptr [rbp+57h+FileInformation.FileAttributes], 10h
0x140016c19  jz      short loc_140016C25
0x140016c1b  mov     ebx, 0C00000BAh
0x140016c20  jmp     loc_140016CEE
0x140016c25  test    byte ptr [rbp+57h+FileInformation.FileAttributes], 1
0x140016c29  jnz     short loc_140016C35
0x140016c2b  mov     ebx, 0C0000001h
0x140016c30  jmp     loc_140016CEE
0x140016c35  cmp     r14b, 1
0x140016c39  jnz     short loc_140016C59
0x140016c3b  lea     rdx, [rbp+57h+var_88]
0x140016c3f  mov     rcx, rsi
0x140016c42  call    SmpCheckFolderForRedirections
0x140016c47  mov     rdi, [rbp+57h+var_88]
0x140016c4b  test    al, al
0x140016c4d  jnz     short loc_140016C59
0x140016c4f  mov     ebx, 0C000050Bh
0x140016c54  jmp     loc_140016CEE
0x140016c59  mov     r9b, 1; int
0x140016c5c  mov     [rsp+0C0h+var_A0], 3; ULONG
0x140016c64  lea     r8, [rbp+57h+ObjectAttributes]; int
0x140016c68  mov     edx, 100100h; int
0x140016c6d  lea     rcx, [rbp+57h+Handle]; int
0x140016c71  call    SmpOpenTargetFile
0x140016c76  mov     ebx, eax
0x140016c78  test    eax, eax
0x140016c7a  js      short loc_140016CEE
0x140016c7c  mov     edx, [rbp+57h+FileInformation.FileAttributes]
0x140016c7f  mov     rcx, [rbp+57h+Handle]
0x140016c83  and     edx, 0FFFFFFFEh
0x140016c86  call    SmpSetTargetAttributes
0x140016c8b  mov     ebx, eax
0x140016c8d  test    eax, eax
0x140016c8f  js      short loc_140016CEE
0x140016c91  mov     rcx, [rbp+57h+Handle]; Handle
0x140016c95  call    cs:__imp_NtClose
0x140016c9b  mov     r9b, r14b
0x140016c9e  mov     [rbp+57h+Handle], 0
0x140016ca6  mov     r8d, 1
0x140016cac  mov     rdx, r15
0x140016caf  mov     rcx, rsi
0x140016cb2  call    SmpRenameTargetFile
0x140016cb7  mov     ebx, eax
0x140016cb9  test    eax, eax
0x140016cbb  js      short loc_140016CC1
0x140016cbd  xor     ebx, ebx
0x140016cbf  jmp     short loc_140016CEE
0x140016cc1  mov     r9b, 1; int
0x140016cc4  mov     [rsp+0C0h+var_A0], 3; ULONG
0x140016ccc  lea     r8, [rbp+57h+ObjectAttributes]; int
0x140016cd0  mov     edx, 110100h; int
0x140016cd5  lea     rcx, [rbp+57h+Handle]; int
0x140016cd9  call    SmpOpenTargetFile
0x140016cde  test    eax, eax
0x140016ce0  js      short loc_140016CEE
0x140016ce2  mov     edx, [rbp+57h+FileInformation.FileAttributes]
0x140016ce5  mov     rcx, [rbp+57h+Handle]
0x140016ce9  call    SmpSetTargetAttributes
0x140016cee  mov     rcx, [rbp+57h+Handle]; Handle
0x140016cf2  test    rcx, rcx
0x140016cf5  jz      short loc_140016CFD
0x140016cf7  call    cs:__imp_NtClose
0x140016cfd  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x140016d01  jz      short loc_140016D0C
0x140016d03  mov     rcx, rdi; Handle
0x140016d06  call    cs:__imp_NtClose
0x140016d0c  mov     eax, ebx
0x140016d0e  mov     rcx, [rbp+57h+var_28]
0x140016d12  xor     rcx, rsp; StackCookie
0x140016d15  call    __security_check_cookie
0x140016d1a  mov     rbx, [rsp+0C0h+arg_10]
0x140016d22  add     rsp, 0A0h
0x140016d29  pop     r15
0x140016d2b  pop     r14
0x140016d2d  pop     rdi
0x140016d2e  pop     rsi
0x140016d2f  pop     rbp
0x140016d30  retn
```
