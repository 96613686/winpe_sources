# RdbDeviceAccessInfoGet(ushort const *,_RDB_DEVICE_ACCESS_INFO *)

- ea: `0x18005c5d0`
- end: `0x18005c81c`
- name: `?RdbDeviceAccessInfoGet@@YAKPEBGPEAU_RDB_DEVICE_ACCESS_INFO@@@Z`
- size: `588`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, wchar_t *)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180007e10`
- `0x18009a978`
- `0x18009e668`
- `0x18009eb8c`

## callees

- `0x180039f94`
- `0x18003bafc`
- `0x18005c5d0`
- `0x18009b0d8`
- `0x18009b200`
- `0x18009b290`
- `0x1800b64c0`

## import_xrefs

- `ntdll!NtCreateFile` at `0x18005c6b2`
- `ntdll!NtCreateFile` at `0x18005c75f`
- `ntdll!NtCreateFile` at `0x18005c6b2`
- `ntdll!NtCreateFile` at `0x18005c75f`
- `ntdll!RtlInitUnicodeString` at `0x18005c64d`
- `ntdll!RtlInitUnicodeString` at `0x18005c6fa`
- `ntdll!RtlInitUnicodeString` at `0x18005c64d`
- `ntdll!RtlInitUnicodeString` at `0x18005c6fa`
- `ntdll!RtlNtStatusToDosError` at `0x18005c6be`
- `ntdll!RtlNtStatusToDosError` at `0x18005c6be`
- `ntdll!NtClose` at `0x18005c7e2`
- `ntdll!NtClose` at `0x18005c7f2`
- `ntdll!NtClose` at `0x18005c7e2`
- `ntdll!NtClose` at `0x18005c7f2`

## pseudocode

```c
__int64 __fastcall RdbDeviceAccessInfoGet(STRSAFE_LPCWSTR pszSrc, wchar_t *a2)
{
  const WCHAR *v2; // rbx
  HRESULT v4; // eax
  ULONG UniqueId; // ebx
  int v6; // eax
  unsigned int v7; // r9d
  unsigned int v8; // r8d
  unsigned int v9; // edx
  unsigned int v10; // r8d
  HANDLE Handle; // [rsp+60h] [rbp-A0h] BYREF
  void *FileHandle; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-80h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t Str[256]; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t pszDest[264]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v2 = a2 + 270;
  FileHandle = 0;
  Handle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  DestinationString = 0;
  v4 = StringCbCopyW(a2 + 270, 0x208u, pszSrc);
  if ( v4 < 0 )
    goto LABEL_2;
  RtlInitUnicodeString(&DestinationString, v2);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v6 = NtCreateFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 0, 0, 7u, 1u, 0x20u, 0, 0);
  if ( v6 < 0 )
    goto LABEL_4;
  v4 = StringCbPrintfW(pszDest, 0x208u, L"%ws\\", v2);
  if ( v4 < 0 )
  {
LABEL_2:
    UniqueId = (unsigned __int16)v4;
    goto LABEL_11;
  }
  RtlInitUnicodeString(&DestinationString, pszDest);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v6 = NtCreateFile(&Handle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 0, 0, 7u, 1u, 0x20u, 0, 0);
  if ( v6 < 0 )
  {
LABEL_4:
    UniqueId = RtlNtStatusToDosError(v6);
  }
  else
  {
    UniqueId = RdbDeviceGetUniqueId(v2, Handle, a2, v7);
    if ( !UniqueId )
    {
      if ( !RdbDeviceParseProductName(a2, a2 + 530, v8)
        || (RdbDeviceCreateUnknownId(Str, v9), (UniqueId = RdbDeviceParseProductName(Str, a2 + 530, v10)) == 0) )
      {
        UniqueId = 0;
        *((_QWORD *)a2 + 197) = FileHandle;
        *((_QWORD *)a2 + 198) = Handle;
        FileHandle = 0;
        Handle = 0;
      }
    }
  }
LABEL_11:
  if ( Handle )
    NtClose(Handle);
  if ( FileHandle )
    NtClose(FileHandle);
  return UniqueId;
}

```

## disassembly

```asm
0x18005c5d0  mov     [rsp-8+arg_10], rbx
0x18005c5d5  push    rbp
0x18005c5d6  push    rsi
0x18005c5d7  push    rdi
0x18005c5d8  lea     rbp, [rsp-3E0h]
0x18005c5e0  sub     rsp, 4E0h
0x18005c5e7  mov     rax, cs:__security_cookie
0x18005c5ee  xor     rax, rsp
0x18005c5f1  mov     [rbp+3F0h+var_20], rax
0x18005c5f8  xorps   xmm0, xmm0
0x18005c5fb  lea     rbx, [rdx+21Ch]
0x18005c602  mov     rdi, rdx
0x18005c605  xor     esi, esi
0x18005c607  mov     r8, rcx; pszSrc
0x18005c60a  mov     [rsp+4F0h+FileHandle], rsi
0x18005c60f  xorps   xmm1, xmm1
0x18005c612  mov     [rsp+4F0h+Handle], rsi
0x18005c617  mov     rcx, rbx; pszDest
0x18005c61a  mov     edx, 208h; cbDest
0x18005c61f  movups  xmmword ptr [rbp+3F0h+ObjectAttributes.Length], xmm0
0x18005c623  movups  xmmword ptr [rbp+3F0h+ObjectAttributes.ObjectName], xmm0
0x18005c627  movups  xmmword ptr [rbp+3F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005c62b  movups  xmmword ptr [rbp+3F0h+IoStatusBlock], xmm0
0x18005c62f  movups  xmmword ptr [rsp+4F0h+DestinationString.Length], xmm1
0x18005c634  call    StringCbCopyW
0x18005c639  test    eax, eax
0x18005c63b  jns     short loc_18005C645
0x18005c63d  movzx   ebx, ax
0x18005c640  jmp     loc_18005C7D8
0x18005c645  mov     rdx, rbx; SourceString
0x18005c648  lea     rcx, [rsp+4F0h+DestinationString]; DestinationString
0x18005c64d  call    cs:__imp_RtlInitUnicodeString
0x18005c653  mov     [rsp+4F0h+EaLength], esi; EaLength
0x18005c657  lea     rax, [rsp+4F0h+DestinationString]
0x18005c65c  mov     [rsp+4F0h+EaBuffer], rsi; EaBuffer
0x18005c661  lea     r9, [rbp+3F0h+IoStatusBlock]; IoStatusBlock
0x18005c665  mov     [rsp+4F0h+CreateOptions], 20h ; ' '; CreateOptions
0x18005c66d  lea     r8, [rbp+3F0h+ObjectAttributes]; ObjectAttributes
0x18005c671  mov     [rsp+4F0h+CreateDisposition], 1; CreateDisposition
0x18005c679  lea     rcx, [rsp+4F0h+FileHandle]; FileHandle
0x18005c67e  mov     [rsp+4F0h+ShareAccess], 7; ShareAccess
0x18005c686  xorps   xmm0, xmm0
0x18005c689  mov     [rsp+4F0h+FileAttributes], esi; FileAttributes
0x18005c68d  mov     edx, 100080h; DesiredAccess
0x18005c692  mov     [rsp+4F0h+AllocationSize], rsi; AllocationSize
0x18005c697  mov     [rbp+3F0h+ObjectAttributes.Length], 30h ; '0'
0x18005c69e  mov     [rbp+3F0h+ObjectAttributes.RootDirectory], rsi
0x18005c6a2  mov     [rbp+3F0h+ObjectAttributes.Attributes], 40h ; '@'
0x18005c6a9  mov     [rbp+3F0h+ObjectAttributes.ObjectName], rax
0x18005c6ad  movdqu  xmmword ptr [rbp+3F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005c6b2  call    cs:__imp_NtCreateFile
0x18005c6b8  test    eax, eax
0x18005c6ba  jns     short loc_18005C6CB
0x18005c6bc  mov     ecx, eax; Status
0x18005c6be  call    cs:__imp_RtlNtStatusToDosError
0x18005c6c4  mov     ebx, eax
0x18005c6c6  jmp     loc_18005C7D8
0x18005c6cb  mov     r9, rbx
0x18005c6ce  lea     r8, aWs_0; "%ws\\"
0x18005c6d5  mov     edx, 208h; cbDest
0x18005c6da  lea     rcx, [rbp+3F0h+pszDest]; pszDest
0x18005c6e1  call    StringCbPrintfW
0x18005c6e6  test    eax, eax
0x18005c6e8  js      loc_18005C63D
0x18005c6ee  lea     rdx, [rbp+3F0h+pszDest]; SourceString
0x18005c6f5  lea     rcx, [rsp+4F0h+DestinationString]; DestinationString
0x18005c6fa  call    cs:__imp_RtlInitUnicodeString
0x18005c700  mov     [rsp+4F0h+EaLength], esi; EaLength
0x18005c704  lea     rax, [rsp+4F0h+DestinationString]
0x18005c709  mov     [rsp+4F0h+EaBuffer], rsi; EaBuffer
0x18005c70e  lea     r9, [rbp+3F0h+IoStatusBlock]; IoStatusBlock
0x18005c712  mov     [rsp+4F0h+CreateOptions], 20h ; ' '; CreateOptions
0x18005c71a  lea     r8, [rbp+3F0h+ObjectAttributes]; ObjectAttributes
0x18005c71e  mov     [rsp+4F0h+CreateDisposition], 1; CreateDisposition
0x18005c726  lea     rcx, [rsp+4F0h+Handle]; FileHandle
0x18005c72b  mov     [rsp+4F0h+ShareAccess], 7; ShareAccess
0x18005c733  xorps   xmm0, xmm0
0x18005c736  mov     [rsp+4F0h+FileAttributes], esi; FileAttributes
0x18005c73a  mov     edx, 100080h; DesiredAccess
0x18005c73f  mov     [rsp+4F0h+AllocationSize], rsi; AllocationSize
0x18005c744  mov     [rbp+3F0h+ObjectAttributes.Length], 30h ; '0'
0x18005c74b  mov     [rbp+3F0h+ObjectAttributes.RootDirectory], rsi
0x18005c74f  mov     [rbp+3F0h+ObjectAttributes.Attributes], 40h ; '@'
0x18005c756  mov     [rbp+3F0h+ObjectAttributes.ObjectName], rax
0x18005c75a  movdqu  xmmword ptr [rbp+3F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005c75f  call    cs:__imp_NtCreateFile
0x18005c765  test    eax, eax
0x18005c767  js      loc_18005C6BC
0x18005c76d  mov     rdx, [rsp+4F0h+Handle]; void *
0x18005c772  mov     r8, rdi; unsigned __int16 *
0x18005c775  mov     rcx, rbx; unsigned __int16 *
0x18005c778  call    ?RdbDeviceGetUniqueId@@YAKPEBGPEAXPEAGK@Z; RdbDeviceGetUniqueId(ushort const *,void *,ushort *,ulong)
0x18005c77d  mov     ebx, eax
0x18005c77f  test    eax, eax
0x18005c781  jnz     short loc_18005C7D8
0x18005c783  lea     rbx, [rdi+424h]
0x18005c78a  mov     rcx, rdi; Str
0x18005c78d  mov     rdx, rbx; pszDest
0x18005c790  call    ?RdbDeviceParseProductName@@YAKPEBGPEAGK@Z; RdbDeviceParseProductName(ushort const *,ushort *,ulong)
0x18005c795  test    eax, eax
0x18005c797  jz      short loc_18005C7B4
0x18005c799  lea     rcx, [rbp+3F0h+Str]; pszDest
0x18005c79d  call    ?RdbDeviceCreateUnknownId@@YAXPEAGK@Z; RdbDeviceCreateUnknownId(ushort *,ulong)
0x18005c7a2  mov     rdx, rbx; pszDest
0x18005c7a5  lea     rcx, [rbp+3F0h+Str]; Str
0x18005c7a9  call    ?RdbDeviceParseProductName@@YAKPEBGPEAGK@Z; RdbDeviceParseProductName(ushort const *,ushort *,ulong)
0x18005c7ae  mov     ebx, eax
0x18005c7b0  test    eax, eax
0x18005c7b2  jnz     short loc_18005C7D8
0x18005c7b4  mov     rax, [rsp+4F0h+FileHandle]
0x18005c7b9  mov     ebx, esi
0x18005c7bb  mov     [rdi+628h], rax
0x18005c7c2  mov     rax, [rsp+4F0h+Handle]
0x18005c7c7  mov     [rdi+630h], rax
0x18005c7ce  mov     [rsp+4F0h+FileHandle], rsi
0x18005c7d3  mov     [rsp+4F0h+Handle], rsi
0x18005c7d8  mov     rcx, [rsp+4F0h+Handle]; Handle
0x18005c7dd  test    rcx, rcx
0x18005c7e0  jz      short loc_18005C7E8
0x18005c7e2  call    cs:__imp_NtClose
0x18005c7e8  mov     rcx, [rsp+4F0h+FileHandle]; Handle
0x18005c7ed  test    rcx, rcx
0x18005c7f0  jz      short loc_18005C7F8
0x18005c7f2  call    cs:__imp_NtClose
0x18005c7f8  mov     eax, ebx
0x18005c7fa  mov     rcx, [rbp+3F0h+var_20]
0x18005c801  xor     rcx, rsp; StackCookie
0x18005c804  call    __security_check_cookie
0x18005c809  mov     rbx, [rsp+4F0h+arg_10]
0x18005c811  add     rsp, 4E0h
0x18005c818  pop     rdi
0x18005c819  pop     rsi
0x18005c81a  pop     rbp
0x18005c81b  retn
```
