# CiSetCatalogHintByFilePath

- ea: `0x18007af9c`
- end: `0x18007b148`
- name: `CiSetCatalogHintByFilePath`
- size: `428`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18007aa18`

## callees

- `0x18007af9c`

## import_xrefs

- `ntdll!NtClose` at `0x18007b0f6`
- `ntdll!NtClose` at `0x18007b0f6`
- `ntdll!RtlFreeHeap` at `0x18007b119`
- `ntdll!RtlFreeHeap` at `0x18007b119`
- `ntdll!NtCreateFile` at `0x18007b091`
- `ntdll!NtCreateFile` at `0x18007b091`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x18007afe7`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x18007afe7`
- `ntdll!NtSetEaFile` at `0x18007b0bc`
- `ntdll!NtSetEaFile` at `0x18007b0bc`
- `ntdll!RtlReleaseRelativeName` at `0x18007b129`
- `ntdll!RtlReleaseRelativeName` at `0x18007b129`
- `ntdll!NtWaitForSingleObject` at `0x18007b0d9`
- `ntdll!NtWaitForSingleObject` at `0x18007b0d9`

## pseudocode

```c
__int64 __fastcall CiSetCatalogHintByFilePath(__int64 a1, ULONG *a2)
{
  __int64 result; // rax
  PVOID v4; // rdi
  HANDLE ContainingDirectory; // rax
  NTSTATUS Status; // ebx
  void *v7; // rsi
  ULONG v8; // r9d
  PVOID P[2]; // [rsp+60h] [rbp-59h] BYREF
  struct _IO_STATUS_BLOCK v10; // [rsp+70h] [rbp-49h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-39h] BYREF
  _RTL_RELATIVE_NAME_U RelativeName; // [rsp+90h] [rbp-29h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-9h] BYREF
  void *FileHandle; // [rsp+130h] [rbp+77h] BYREF

  FileHandle = 0;
  *(_OWORD *)P = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  memset(&RelativeName, 0, sizeof(RelativeName));
  result = RtlDosPathNameToRelativeNtPathName_U_WithStatus(a1, P, 0, &RelativeName);
  if ( (int)result >= 0 )
  {
    v4 = P[1];
    if ( RelativeName.RelativeName.Length )
    {
      LOWORD(P[0]) = RelativeName.RelativeName.Length;
      *(_DWORD *)((char *)P + 2) = *(_DWORD *)&RelativeName.RelativeName.MaximumLength;
      HIWORD(P[0]) = *(&RelativeName.RelativeName.MaximumLength + 2);
      P[1] = RelativeName.RelativeName.Buffer;
      ContainingDirectory = RelativeName.ContainingDirectory;
    }
    else
    {
      ContainingDirectory = 0;
      RelativeName.ContainingDirectory = 0;
    }
    ObjectAttributes.RootDirectory = ContainingDirectory;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)P;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    Status = NtCreateFile(&FileHandle, 0x100010u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 1u, 0x4060u, 0, 0);
    if ( Status >= 0 )
    {
      v7 = FileHandle;
      v8 = *a2;
      v10 = 0;
      Status = NtSetEaFile(FileHandle, &v10, a2 + 1, v8);
      if ( Status == 259 )
      {
        Status = NtWaitForSingleObject(v7, 0, 0);
        if ( Status >= 0 )
          Status = v10.Status;
      }
    }
    if ( FileHandle )
      NtClose(FileHandle);
    if ( v4 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
    RtlReleaseRelativeName(&RelativeName);
    return (unsigned int)Status;
  }
  return result;
}

```

## disassembly

```asm
0x18007af9c  push    rbp
0x18007af9e  push    rbx
0x18007af9f  push    rsi
0x18007afa0  push    rdi
0x18007afa1  push    r14
0x18007afa3  push    r15
0x18007afa5  lea     rbp, [rsp-2Fh]
0x18007afaa  sub     rsp, 0E8h
0x18007afb1  xorps   xmm0, xmm0
0x18007afb4  lea     r9, [rbp+57h+RelativeName]
0x18007afb8  mov     r14, rdx
0x18007afbb  xor     r15d, r15d
0x18007afbe  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18007afc2  xor     eax, eax
0x18007afc4  mov     [rbp+57h+FileHandle], r15
0x18007afc8  xor     r8d, r8d
0x18007afcb  lea     rdx, [rbp+57h+P]
0x18007afcf  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18007afd3  movups  xmmword ptr [rbp+57h+P], xmm0
0x18007afd7  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18007afdb  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18007afdf  movups  xmmword ptr [rbp+57h+RelativeName.RelativeName.Length], xmm0
0x18007afe3  movups  xmmword ptr [rbp+57h+RelativeName.ContainingDirectory], xmm0
0x18007afe7  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U_WithStatus
0x18007afee  nop     dword ptr [rax+rax+00h]
0x18007aff3  test    eax, eax
0x18007aff5  js      loc_18007B137
0x18007affb  movzx   eax, [rbp+57h+RelativeName.RelativeName.Length]
0x18007afff  mov     rdi, [rbp+57h+P+8]
0x18007b003  test    ax, ax
0x18007b006  jz      short loc_18007B028
0x18007b008  mov     word ptr [rbp+57h+P], ax
0x18007b00c  mov     eax, dword ptr [rbp+57h+RelativeName.RelativeName.MaximumLength]
0x18007b00f  mov     dword ptr [rbp+57h+P+2], eax
0x18007b012  movzx   eax, word ptr [rbp+57h+RelativeName.RelativeName+6]
0x18007b016  mov     word ptr [rbp+57h+P+6], ax
0x18007b01a  mov     rax, [rbp+57h+RelativeName.RelativeName.Buffer]
0x18007b01e  mov     [rbp+57h+P+8], rax
0x18007b022  mov     rax, [rbp+57h+RelativeName.ContainingDirectory]
0x18007b026  jmp     short loc_18007B02F
0x18007b028  mov     rax, r15
0x18007b02b  mov     [rbp+57h+RelativeName.ContainingDirectory], rax
0x18007b02f  mov     [rsp+110h+EaLength], r15d; EaLength
0x18007b034  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18007b038  mov     [rsp+110h+EaBuffer], r15; EaBuffer
0x18007b03d  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18007b041  mov     [rsp+110h+CreateOptions], 4060h; CreateOptions
0x18007b049  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18007b04d  mov     [rsp+110h+CreateDisposition], 1; CreateDisposition
0x18007b055  xorps   xmm0, xmm0
0x18007b058  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x18007b05c  mov     edx, 100010h; DesiredAccess
0x18007b061  mov     [rsp+110h+ShareAccess], 7; ShareAccess
0x18007b069  lea     rax, [rbp+57h+P]
0x18007b06d  mov     [rsp+110h+FileAttributes], 80h; FileAttributes
0x18007b075  mov     [rsp+110h+AllocationSize], r15; AllocationSize
0x18007b07a  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18007b081  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18007b088  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18007b08c  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18007b091  call    cs:__imp_NtCreateFile
0x18007b098  nop     dword ptr [rax+rax+00h]
0x18007b09d  mov     ebx, eax
0x18007b09f  test    eax, eax
0x18007b0a1  js      short loc_18007B0ED
0x18007b0a3  mov     rsi, [rbp+57h+FileHandle]
0x18007b0a7  lea     r8, [r14+4]; EaBuffer
0x18007b0ab  mov     r9d, [r14]; EaBufferSize
0x18007b0ae  lea     rdx, [rbp+57h+var_A0]; IoStatusBlock
0x18007b0b2  xorps   xmm0, xmm0
0x18007b0b5  mov     rcx, rsi; FileHandle
0x18007b0b8  movups  xmmword ptr [rbp+57h+var_A0], xmm0
0x18007b0bc  call    cs:__imp_NtSetEaFile
0x18007b0c3  nop     dword ptr [rax+rax+00h]
0x18007b0c8  mov     ebx, eax
0x18007b0ca  cmp     eax, 103h
0x18007b0cf  jnz     short loc_18007B0ED
0x18007b0d1  xor     r8d, r8d; Timeout
0x18007b0d4  xor     edx, edx; Alertable
0x18007b0d6  mov     rcx, rsi; Handle
0x18007b0d9  call    cs:__imp_NtWaitForSingleObject
0x18007b0e0  nop     dword ptr [rax+rax+00h]
0x18007b0e5  test    eax, eax
0x18007b0e7  mov     ebx, eax
0x18007b0e9  cmovns  ebx, dword ptr [rbp+57h+var_A0]
0x18007b0ed  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18007b0f1  test    rcx, rcx
0x18007b0f4  jz      short loc_18007B102
0x18007b0f6  call    cs:__imp_NtClose
0x18007b0fd  nop     dword ptr [rax+rax+00h]
0x18007b102  test    rdi, rdi
0x18007b105  jz      short loc_18007B125
0x18007b107  mov     rcx, gs:60h
0x18007b110  mov     r8, rdi; P
0x18007b113  xor     edx, edx; Flags
0x18007b115  mov     rcx, [rcx+30h]; HeapHandle
0x18007b119  call    cs:__imp_RtlFreeHeap
0x18007b120  nop     dword ptr [rax+rax+00h]
0x18007b125  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x18007b129  call    cs:__imp_RtlReleaseRelativeName
0x18007b130  nop     dword ptr [rax+rax+00h]
0x18007b135  mov     eax, ebx
0x18007b137  add     rsp, 0E8h
0x18007b13e  pop     r15
0x18007b140  pop     r14
0x18007b142  pop     rdi
0x18007b143  pop     rsi
0x18007b144  pop     rbx
0x18007b145  pop     rbp
0x18007b146  retn
```
