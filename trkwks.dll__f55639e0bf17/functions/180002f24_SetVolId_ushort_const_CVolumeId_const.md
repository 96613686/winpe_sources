# SetVolId(ushort const *,CVolumeId const &)

- ea: `0x180002f24`
- end: `0x1800030b8`
- name: `?SetVolId@@YAJPEBGAEBUCVolumeId@@@Z`
- size: `404`
- prototype: `__int64 __fastcall(PCWSTR DosPathName, const struct CVolumeId *)`
- caller_count: `3`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180002488`
- `0x18000f548`
- `0x18000f744`

## callees

- `0x1800012c8`
- `0x180002f24`
- `0x180010fca`
- `0x180011000`

## import_xrefs

- `ntdll!NtSetVolumeInformationFile` at `0x18000305d`
- `ntdll!NtSetVolumeInformationFile` at `0x18000305d`
- `ntdll!NtOpenFile` at `0x180003009`
- `ntdll!NtOpenFile` at `0x180003009`
- `ntdll!RtlFreeHeap` at `0x18000308c`
- `ntdll!RtlFreeHeap` at `0x18000308c`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180002fa1`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180002fa1`
- `ntdll!NtClose` at `0x18000306f`
- `ntdll!NtClose` at `0x18000306f`

## pseudocode

```c
__int64 __fastcall SetVolId(PCWSTR DosPathName, const struct CVolumeId *a2)
{
  PWSTR Buffer; // rdi
  NTSTATUS v5; // ebx
  void *FileHandle; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING NtPathName; // [rsp+38h] [rbp-C8h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+48h] [rbp-B8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v11[64]; // [rsp+90h] [rbp-70h] BYREF
  _OWORD FsInformation[4]; // [rsp+D0h] [rbp-30h] BYREF

  FileHandle = 0;
  NtPathName = 0;
  memset_0(FsInformation, 0, sizeof(FsInformation));
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  EnableRestorePrivilege();
  if ( RtlDosPathNameToNtPathName_U(DosPathName, &NtPathName, 0, 0) )
  {
    Buffer = NtPathName.Buffer;
    ObjectAttributes.ObjectName = &NtPathName;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v5 = NtOpenFile(&FileHandle, 0x12019Fu, &ObjectAttributes, &IoStatusBlock, 7u, 0x20u);
    if ( v5 < 0 )
    {
      FileHandle = 0;
      goto LABEL_8;
    }
    memset_0(v11, 0, sizeof(v11));
    FsInformation[0] = *(_OWORD *)a2;
    memset(&FsInformation[1], 0, 48);
    v5 = NtSetVolumeInformationFile(FileHandle, &IoStatusBlock, FsInformation, 0x40u, FileFsObjectIdInformation);
  }
  else
  {
    Buffer = 0;
    v5 = -1073741773;
  }
  if ( FileHandle )
    NtClose(FileHandle);
LABEL_8:
  if ( Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180002f24  mov     [rsp-8+arg_8], rbx
0x180002f29  mov     [rsp-8+arg_10], rsi
0x180002f2e  push    rbp
0x180002f2f  push    rdi
0x180002f30  push    r15
0x180002f32  lea     rbp, [rsp-20h]
0x180002f37  sub     rsp, 120h
0x180002f3e  mov     rax, cs:__security_cookie
0x180002f45  xor     rax, rsp
0x180002f48  mov     [rbp+30h+var_20], rax
0x180002f4c  mov     rsi, rdx
0x180002f4f  mov     [rsp+130h+FileHandle], 0
0x180002f58  mov     rbx, rcx
0x180002f5b  xorps   xmm0, xmm0
0x180002f5e  mov     r15d, 40h ; '@'
0x180002f64  lea     rcx, [rbp+30h+FsInformation]; void *
0x180002f68  mov     r8d, r15d; Size
0x180002f6b  xor     edx, edx; Val
0x180002f6d  movups  xmmword ptr [rsp+130h+NtPathName.Length], xmm0
0x180002f72  call    memset_0
0x180002f77  xorps   xmm0, xmm0
0x180002f7a  movups  xmmword ptr [rsp+130h+ObjectAttributes.Length], xmm0
0x180002f7f  movups  xmmword ptr [rsp+130h+ObjectAttributes.ObjectName], xmm0
0x180002f84  movups  xmmword ptr [rsp+130h+ObjectAttributes.SecurityDescriptor], xmm0
0x180002f89  movups  xmmword ptr [rsp+130h+IoStatusBlock], xmm0
0x180002f8e  call    ?EnableRestorePrivilege@@YAXXZ; EnableRestorePrivilege(void)
0x180002f93  xor     r9d, r9d; DirectoryInfo
0x180002f96  lea     rdx, [rsp+130h+NtPathName]; NtPathName
0x180002f9b  xor     r8d, r8d; NtFileNamePart
0x180002f9e  mov     rcx, rbx; DosPathName
0x180002fa1  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180002fa7  test    al, al
0x180002fa9  jnz     short loc_180002FB7
0x180002fab  xor     edi, edi
0x180002fad  mov     ebx, 0C0000033h
0x180002fb2  jmp     loc_180003065
0x180002fb7  mov     rdi, [rsp+130h+NtPathName.Buffer]
0x180002fbc  lea     rax, [rsp+130h+NtPathName]
0x180002fc1  xorps   xmm0, xmm0
0x180002fc4  mov     [rsp+130h+OpenOptions], 20h ; ' '; OpenOptions
0x180002fcc  lea     r9, [rsp+130h+IoStatusBlock]; IoStatusBlock
0x180002fd1  mov     [rsp+130h+ObjectAttributes.ObjectName], rax
0x180002fd6  lea     r8, [rsp+130h+ObjectAttributes]; ObjectAttributes
0x180002fdb  mov     [rsp+130h+ObjectAttributes.Length], 30h ; '0'
0x180002fe3  mov     edx, 12019Fh; DesiredAccess
0x180002fe8  mov     [rsp+130h+ObjectAttributes.RootDirectory], 0
0x180002ff1  lea     rcx, [rsp+130h+FileHandle]; FileHandle
0x180002ff6  mov     [rsp+130h+ObjectAttributes.Attributes], r15d
0x180002ffb  movdqu  xmmword ptr [rsp+130h+ObjectAttributes.SecurityDescriptor], xmm0
0x180003001  mov     [rsp+130h+ShareAccess], 7; ShareAccess
0x180003009  call    cs:__imp_NtOpenFile
0x18000300f  mov     ebx, eax
0x180003011  test    eax, eax
0x180003013  jns     short loc_180003020
0x180003015  mov     [rsp+130h+FileHandle], 0
0x18000301e  jmp     short loc_180003075
0x180003020  mov     r8, r15; Size
0x180003023  lea     rcx, [rbp+30h+var_A0]; void *
0x180003027  xor     edx, edx; Val
0x180003029  call    memset_0
0x18000302e  movups  xmm0, xmmword ptr [rsi]
0x180003031  mov     rcx, [rsp+130h+FileHandle]; FileHandle
0x180003036  lea     r8, [rbp+30h+FsInformation]; FsInformation
0x18000303a  xorps   xmm1, xmm1
0x18000303d  mov     [rsp+130h+ShareAccess], 8; FsInformationClass
0x180003045  mov     r9d, r15d; Length
0x180003048  movaps  [rbp+30h+FsInformation], xmm0
0x18000304c  lea     rdx, [rsp+130h+IoStatusBlock]; IoStatusBlock
0x180003051  movaps  [rbp+30h+var_50], xmm1
0x180003055  movaps  [rbp+30h+var_40], xmm1
0x180003059  movaps  [rbp+30h+var_30], xmm1
0x18000305d  call    cs:__imp_NtSetVolumeInformationFile
0x180003063  mov     ebx, eax
0x180003065  mov     rcx, [rsp+130h+FileHandle]; Handle
0x18000306a  test    rcx, rcx
0x18000306d  jz      short loc_180003075
0x18000306f  call    cs:__imp_NtClose
0x180003075  test    rdi, rdi
0x180003078  jz      short loc_180003092
0x18000307a  mov     rcx, gs:60h
0x180003083  mov     r8, rdi; P
0x180003086  xor     edx, edx; Flags
0x180003088  mov     rcx, [rcx+30h]; HeapHandle
0x18000308c  call    cs:__imp_RtlFreeHeap
0x180003092  mov     eax, ebx
0x180003094  mov     rcx, [rbp+30h+var_20]
0x180003098  xor     rcx, rsp; StackCookie
0x18000309b  call    __security_check_cookie
0x1800030a0  lea     r11, [rsp+130h+var_10]
0x1800030a8  mov     rbx, [r11+28h]
0x1800030ac  mov     rsi, [r11+30h]
0x1800030b0  mov     rsp, r11
0x1800030b3  pop     r15
0x1800030b5  pop     rdi
0x1800030b6  pop     rbp
0x1800030b7  retn
```
