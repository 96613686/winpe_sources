# PfDiGetVolumeInfo

- ea: `0x180007a64`
- end: `0x180007c70`
- name: `PfDiGetVolumeInfo`
- size: `524`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180007840`
- `0x180007cbc`
- `0x180048a24`
- `0x1800553b8`

## callees

- `0x180007a64`
- `0x18003a2ac`
- `0x180063368`
- `0x1800b645a`
- `0x1800b64c0`
- `0x1800b6580`

## import_xrefs

- `ntdll!NtCreateFile` at `0x180007bda`
- `ntdll!NtCreateFile` at `0x180007bda`
- `ntdll!NtQueryObject` at `0x180007afa`
- `ntdll!NtQueryObject` at `0x180007afa`
- `ntdll!NtQueryVolumeInformationFile` at `0x180007c00`
- `ntdll!NtQueryVolumeInformationFile` at `0x180007c00`
- `ntdll!RtlUpcaseUnicodeString` at `0x180007b62`
- `ntdll!RtlUpcaseUnicodeString` at `0x180007b62`
- `ntdll!RtlNtStatusToDosError` at `0x180007b06`
- `ntdll!RtlNtStatusToDosError` at `0x180007b06`
- `ntdll!NtClose` at `0x180007b18`
- `ntdll!NtClose` at `0x180007b18`

## pseudocode

```c
__int64 __fastcall PfDiGetVolumeInfo(void *a1, __int64 a2)
{
  int v4; // eax
  ULONG v5; // ebx
  __int64 v7; // rsi
  __int64 v8; // rbx
  unsigned int v9; // eax
  int v10; // eax
  ULONG ReturnLength; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE Handle; // [rsp+68h] [rbp-98h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-90h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A0h] [rbp-60h] BYREF
  __int128 FsInformation; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v16; // [rsp+C0h] [rbp-40h]
  struct _UNICODE_STRING ObjectInformation[256]; // [rsp+D0h] [rbp-30h] BYREF

  v16 = 0;
  ReturnLength = 0;
  memset(&ObjectAttributes, 0, 44);
  FsInformation = 0;
  IoStatusBlock = 0;
  memset_0(ObjectInformation, 0, sizeof(ObjectInformation));
  Handle = 0;
  v4 = NtQueryObject(a1, ObjectNameInformation, ObjectInformation, 0xFFEu, &ReturnLength);
  if ( v4 < 0 )
    goto LABEL_2;
  v7 = ObjectInformation[0].Length >> 1;
  ObjectInformation[0].Buffer[v7] = 0;
  RtlUpcaseUnicodeString(ObjectInformation, ObjectInformation, 0);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = ObjectInformation;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = NtCreateFile(&Handle, 0x100180u, &ObjectAttributes, &IoStatusBlock, 0, 0, 7u, 1u, 0x20u, 0, 0);
  if ( v4 < 0
    || (v4 = NtQueryVolumeInformationFile(Handle, &IoStatusBlock, &FsInformation, 0x18u, FileFsVolumeInformation),
        (v4 & 0xC0000000) == 0xC0000000) )
  {
LABEL_2:
    v5 = RtlNtStatusToDosError(v4);
  }
  else
  {
    v8 = PfScStringInsertEx(*(_QWORD *)&PfSvcGlobals + 96LL, (unsigned __int8 *)ObjectInformation[0].Buffer, v7, 0);
    if ( v8 )
    {
      PfDiVolumeInfoCleanup(a2);
      v9 = FsInformation;
      *(_WORD *)(a2 + 26) |= 1u;
      *(_QWORD *)a2 = __PAIR64__(DWORD1(FsInformation), v9);
      v10 = DWORD2(FsInformation);
      *(_QWORD *)(a2 + 16) = v8;
      v5 = 0;
      *(_DWORD *)(a2 + 8) = v10;
      *(_WORD *)(a2 + 24) = v7;
    }
    else
    {
      v5 = 8;
    }
  }
  if ( Handle )
    NtClose(Handle);
  return v5;
}

```

## disassembly

```asm
0x180007a64  mov     [rsp-8+arg_10], rbx
0x180007a69  mov     [rsp-8+arg_18], rsi
0x180007a6e  push    rbp
0x180007a6f  push    rdi
0x180007a70  push    r15
0x180007a72  lea     rbp, [rsp-0FE0h]
0x180007a7a  mov     eax, 10E0h
0x180007a7f  call    _alloca_probe
0x180007a84  sub     rsp, rax
0x180007a87  mov     rax, cs:__security_cookie
0x180007a8e  xor     rax, rsp
0x180007a91  mov     [rbp+0FF0h+var_20], rax
0x180007a98  xorps   xmm0, xmm0
0x180007a9b  xor     eax, eax
0x180007a9d  mov     rdi, rdx
0x180007aa0  mov     [rbp+0FF0h+var_1030], rax
0x180007aa4  mov     rbx, rcx
0x180007aa7  mov     [rsp+10F0h+var_1090], eax
0x180007aab  movups  xmmword ptr [rbp+0FF0h+ObjectAttributes.ObjectName], xmm0
0x180007aaf  xor     edx, edx; Val
0x180007ab1  lea     rcx, [rbp+0FF0h+ObjectInformation]; void *
0x180007ab5  mov     r8d, 1000h; Size
0x180007abb  movups  xmmword ptr [rbp+0FF0h+ObjectAttributes+1Ch], xmm0
0x180007abf  movups  xmmword ptr [rsp+10F0h+ObjectAttributes.Length], xmm0
0x180007ac4  movups  [rbp+0FF0h+FsInformation], xmm0
0x180007ac8  movups  xmmword ptr [rbp+0FF0h+IoStatusBlock], xmm0
0x180007acc  call    memset_0
0x180007ad1  lea     rax, [rsp+10F0h+var_1090]
0x180007ad6  mov     [rsp+10F0h+Handle], 0
0x180007adf  mov     r15d, 1
0x180007ae5  mov     [rsp+10F0h+ReturnLength], rax; ReturnLength
0x180007aea  mov     edx, r15d; ObjectInformationClass
0x180007aed  lea     r8, [rbp+0FF0h+ObjectInformation]; ObjectInformation
0x180007af1  mov     r9d, 0FFEh; ObjectInformationLength
0x180007af7  mov     rcx, rbx; Handle
0x180007afa  call    cs:__imp_NtQueryObject
0x180007b00  test    eax, eax
0x180007b02  jns     short loc_180007B47
0x180007b04  mov     ecx, eax; Status
0x180007b06  call    cs:__imp_RtlNtStatusToDosError
0x180007b0c  mov     ebx, eax
0x180007b0e  mov     rcx, [rsp+10F0h+Handle]; Handle
0x180007b13  test    rcx, rcx
0x180007b16  jz      short loc_180007B1E
0x180007b18  call    cs:__imp_NtClose
0x180007b1e  mov     eax, ebx
0x180007b20  mov     rcx, [rbp+0FF0h+var_20]
0x180007b27  xor     rcx, rsp; StackCookie
0x180007b2a  call    __security_check_cookie
0x180007b2f  lea     r11, [rsp+10F0h+var_10]
0x180007b37  mov     rbx, [r11+30h]
0x180007b3b  mov     rsi, [r11+38h]
0x180007b3f  mov     rsp, r11
0x180007b42  pop     r15
0x180007b44  pop     rdi
0x180007b45  pop     rbp
0x180007b46  retn
0x180007b47  movzx   esi, [rbp+0FF0h+ObjectInformation]
0x180007b4b  lea     rdx, [rbp+0FF0h+ObjectInformation]; SourceString
0x180007b4f  mov     rax, [rbp+0FF0h+var_1018]
0x180007b53  xor     ecx, ecx
0x180007b55  shr     esi, 1
0x180007b57  xor     r8d, r8d; AllocateDestinationString
0x180007b5a  mov     [rax+rsi*2], cx
0x180007b5e  lea     rcx, [rbp+0FF0h+ObjectInformation]; DestinationString
0x180007b62  call    cs:__imp_RtlUpcaseUnicodeString
0x180007b68  mov     [rsp+10F0h+EaLength], 0; EaLength
0x180007b70  lea     rax, [rbp+0FF0h+ObjectInformation]
0x180007b74  mov     [rsp+10F0h+EaBuffer], 0; EaBuffer
0x180007b7d  lea     r9, [rbp+0FF0h+IoStatusBlock]; IoStatusBlock
0x180007b81  mov     [rsp+10F0h+CreateOptions], 20h ; ' '; CreateOptions
0x180007b89  lea     r8, [rsp+10F0h+ObjectAttributes]; ObjectAttributes
0x180007b8e  mov     [rsp+10F0h+CreateDisposition], r15d; CreateDisposition
0x180007b93  lea     rcx, [rsp+10F0h+Handle]; FileHandle
0x180007b98  mov     [rsp+10F0h+ShareAccess], 7; ShareAccess
0x180007ba0  xorps   xmm0, xmm0
0x180007ba3  mov     [rsp+10F0h+FileAttributes], 0; FileAttributes
0x180007bab  mov     edx, 100180h; DesiredAccess
0x180007bb0  mov     [rsp+10F0h+ReturnLength], 0; AllocationSize
0x180007bb9  mov     [rsp+10F0h+ObjectAttributes.Length], 30h ; '0'
0x180007bc1  mov     [rsp+10F0h+ObjectAttributes.RootDirectory], 0
0x180007bca  mov     [rbp+0FF0h+ObjectAttributes.Attributes], 40h ; '@'
0x180007bd1  mov     [rbp+0FF0h+ObjectAttributes.ObjectName], rax
0x180007bd5  movdqu  xmmword ptr [rbp+0FF0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180007bda  call    cs:__imp_NtCreateFile
0x180007be0  test    eax, eax
0x180007be2  js      loc_180007B04
0x180007be8  mov     rcx, [rsp+10F0h+Handle]; FileHandle
0x180007bed  lea     r8, [rbp+0FF0h+FsInformation]; FsInformation
0x180007bf1  mov     r9d, 18h; Length
0x180007bf7  mov     dword ptr [rsp+10F0h+ReturnLength], r15d; FsInformationClass
0x180007bfc  lea     rdx, [rbp+0FF0h+IoStatusBlock]; IoStatusBlock
0x180007c00  call    cs:__imp_NtQueryVolumeInformationFile
0x180007c06  mov     edx, 0C0000000h
0x180007c0b  mov     ecx, eax
0x180007c0d  and     ecx, edx
0x180007c0f  cmp     ecx, edx
0x180007c11  jz      loc_180007B04
0x180007c17  mov     rcx, cs:PfSvcGlobals
0x180007c1e  xor     r9d, r9d
0x180007c21  mov     rdx, [rbp+0FF0h+var_1018]
0x180007c25  add     rcx, 60h ; '`'
0x180007c29  mov     r8d, esi
0x180007c2c  call    PfScStringInsertEx
0x180007c31  mov     rbx, rax
0x180007c34  test    rax, rax
0x180007c37  jz      short loc_180007C66
0x180007c39  mov     rcx, rdi
0x180007c3c  call    PfDiVolumeInfoCleanup
0x180007c41  mov     eax, dword ptr [rbp+0FF0h+FsInformation]
0x180007c44  or      [rdi+1Ah], r15w
0x180007c49  mov     [rdi], eax
0x180007c4b  mov     eax, dword ptr [rbp+0FF0h+FsInformation+4]
0x180007c4e  mov     [rdi+4], eax
0x180007c51  mov     eax, dword ptr [rbp+0FF0h+FsInformation+8]
0x180007c54  mov     [rdi+10h], rbx
0x180007c58  xor     ebx, ebx
0x180007c5a  mov     [rdi+8], eax
0x180007c5d  mov     [rdi+18h], si
0x180007c61  jmp     loc_180007B0E
0x180007c66  mov     ebx, 8
0x180007c6b  jmp     loc_180007B0E
```
