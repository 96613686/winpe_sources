# NMP_CreateFile(ushort *,ulong,void * *)

- ea: `0x18005d88c`
- end: `0x18005da93`
- name: `?NMP_CreateFile@@YAJPEAGKPEAPEAX@Z`
- size: `519`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18005cf30`

## callees

- `0x18005d88c`
- `0x1800ca140`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18005d9d2`
- `ntdll!RtlFreeHeap` at `0x18005d9d2`
- `ntdll!RtlReleaseRelativeName` at `0x18005d9ba`
- `ntdll!RtlReleaseRelativeName` at `0x18005d9ba`
- `ntdll!NtCreateFile` at `0x18005d99a`
- `ntdll!NtCreateFile` at `0x18005d99a`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x18005d8f1`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x18005d8f1`
- `ntdll!RtlNtStatusToDosError` at `0x18005da35`
- `ntdll!RtlNtStatusToDosError` at `0x18005da71`
- `ntdll!RtlNtStatusToDosError` at `0x18005da35`
- `ntdll!RtlNtStatusToDosError` at `0x18005da71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005da43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005da7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005da43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005da7f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005da3d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005da79`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005da3d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005da79`

## pseudocode

```c
__int64 __fastcall NMP_CreateFile(unsigned __int16 *a1, int a2, void **a3)
{
  NTSTATUS v5; // eax
  PVOID v6; // rdi
  int v7; // eax
  DWORD LastError; // ebx
  unsigned int v10; // ecx
  ULONG v11; // eax
  ULONG v12; // eax
  void *FileHandle; // [rsp+60h] [rbp-49h] BYREF
  PVOID P[2]; // [rsp+68h] [rbp-41h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-31h] BYREF
  _RTL_RELATIVE_NAME_U RelativeName; // [rsp+A8h] [rbp-1h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C8h] [rbp+1Fh] BYREF
  __int64 v18; // [rsp+D8h] [rbp+2Fh] BYREF
  int v19; // [rsp+E0h] [rbp+37h]

  FileHandle = 0;
  v18 = 0;
  v19 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  *(_OWORD *)P = 0;
  memset(&RelativeName, 0, sizeof(RelativeName));
  v5 = RtlDosPathNameToRelativeNtPathName_U_WithStatus(a1, P, 0, &RelativeName);
  if ( v5 < 0 )
  {
    if ( v5 == -1073741801 || v5 == -1073741670 )
    {
      v12 = RtlNtStatusToDosError(v5);
      SetLastError(v12);
      LastError = GetLastError();
    }
    else
    {
      LastError = 3;
    }
    *a3 = (void *)-1LL;
  }
  else
  {
    v6 = P[1];
    ObjectAttributes.RootDirectory = RelativeName.ContainingDirectory;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)P;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.SecurityDescriptor = 0;
    if ( (a2 & 0x100000) != 0 )
    {
      LOBYTE(v19) = (a2 & 0x40000) != 0;
      v10 = a2 & ((-(unsigned __int8)v19 & 0xFFFC0000) - 1048577);
      if ( (v10 & 0x80000) != 0 )
      {
        BYTE1(v19) = 1;
        v10 &= ~0x80000u;
      }
      else
      {
        BYTE1(v19) = 0;
      }
      HIDWORD(v18) = HIWORD(v10);
    }
    else
    {
      LOWORD(v19) = 257;
      HIDWORD(v18) = 2;
    }
    LODWORD(v18) = 12;
    ObjectAttributes.SecurityQualityOfService = &v18;
    v7 = NtCreateFile(&FileHandle, 0xC0100080, &ObjectAttributes, &IoStatusBlock, 0, 0, 3u, 1u, 0, 0, 0);
    if ( v7 < 0 )
    {
      FileHandle = (void *)-1LL;
      v11 = RtlNtStatusToDosError(v7);
      SetLastError(v11);
      LastError = GetLastError();
    }
    else
    {
      LastError = 0;
    }
    *a3 = FileHandle;
    if ( v6 )
    {
      RtlReleaseRelativeName(&RelativeName);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x18005d88c  mov     [rsp-8+arg_18], rbx
0x18005d891  push    rbp
0x18005d892  push    rsi
0x18005d893  push    rdi
0x18005d894  lea     rbp, [rsp-47h]
0x18005d899  sub     rsp, 0F0h
0x18005d8a0  mov     rax, cs:__security_cookie
0x18005d8a7  xor     rax, rsp
0x18005d8aa  mov     [rbp+57h+var_18], rax
0x18005d8ae  xorps   xmm0, xmm0
0x18005d8b1  mov     [rbp+57h+FileHandle], 0
0x18005d8b9  xor     eax, eax
0x18005d8bb  lea     r9, [rbp+57h+RelativeName]
0x18005d8bf  mov     rsi, r8
0x18005d8c2  mov     [rbp+57h+var_28], rax
0x18005d8c6  mov     ebx, edx
0x18005d8c8  mov     [rbp+57h+var_20], eax
0x18005d8cb  xorps   xmm1, xmm1
0x18005d8ce  lea     rdx, [rbp+57h+P]
0x18005d8d2  xor     r8d, r8d
0x18005d8d5  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18005d8d9  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18005d8dd  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005d8e1  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18005d8e5  movups  xmmword ptr [rbp+57h+P], xmm1
0x18005d8e9  movups  xmmword ptr [rbp+57h+RelativeName.RelativeName.Length], xmm0
0x18005d8ed  movups  xmmword ptr [rbp+57h+RelativeName.ContainingDirectory], xmm0
0x18005d8f1  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U_WithStatus
0x18005d8f7  test    eax, eax
0x18005d8f9  js      loc_18005DA5A
0x18005d8ff  mov     rax, [rbp+57h+RelativeName.ContainingDirectory]
0x18005d903  mov     rdi, [rbp+57h+P+8]
0x18005d907  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x18005d90b  lea     rax, [rbp+57h+P]
0x18005d90f  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18005d913  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18005d91a  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18005d921  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], 0
0x18005d929  bt      ebx, 14h
0x18005d92d  jb      loc_18005D9F9
0x18005d933  mov     word ptr [rbp+57h+var_20], 101h
0x18005d939  mov     dword ptr [rbp+57h+var_28+4], 2
0x18005d940  mov     [rsp+100h+EaLength], 0; EaLength
0x18005d948  lea     rax, [rbp+57h+var_28]
0x18005d94c  mov     [rsp+100h+EaBuffer], 0; EaBuffer
0x18005d955  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18005d959  mov     [rsp+100h+CreateOptions], 0; CreateOptions
0x18005d961  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18005d965  mov     [rsp+100h+CreateDisposition], 1; CreateDisposition
0x18005d96d  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18005d971  mov     [rsp+100h+ShareAccess], 3; ShareAccess
0x18005d979  mov     edx, 0C0100080h; DesiredAccess
0x18005d97e  mov     [rsp+100h+FileAttributes], 0; FileAttributes
0x18005d986  mov     [rsp+100h+AllocationSize], 0; AllocationSize
0x18005d98f  mov     dword ptr [rbp+57h+var_28], 0Ch
0x18005d996  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], rax
0x18005d99a  call    cs:__imp_NtCreateFile
0x18005d9a0  test    eax, eax
0x18005d9a2  js      loc_18005DA2B
0x18005d9a8  xor     ebx, ebx
0x18005d9aa  mov     rax, [rbp+57h+FileHandle]
0x18005d9ae  mov     [rsi], rax
0x18005d9b1  test    rdi, rdi
0x18005d9b4  jz      short loc_18005D9D8
0x18005d9b6  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x18005d9ba  call    cs:__imp_RtlReleaseRelativeName
0x18005d9c0  mov     rcx, gs:60h
0x18005d9c9  mov     r8, rdi; P
0x18005d9cc  xor     edx, edx; Flags
0x18005d9ce  mov     rcx, [rcx+30h]; HeapHandle
0x18005d9d2  call    cs:__imp_RtlFreeHeap
0x18005d9d8  mov     eax, ebx
0x18005d9da  mov     rcx, [rbp+57h+var_18]
0x18005d9de  xor     rcx, rsp; StackCookie
0x18005d9e1  call    __security_check_cookie
0x18005d9e6  mov     rbx, [rsp+100h+arg_18]
0x18005d9ee  add     rsp, 0F0h
0x18005d9f5  pop     rdi
0x18005d9f6  pop     rsi
0x18005d9f7  pop     rbp
0x18005d9f8  retn
0x18005d9f9  mov     eax, ebx
0x18005d9fb  and     eax, 40000h
0x18005da00  setnz   byte ptr [rbp+57h+var_20]
0x18005da04  neg     eax
0x18005da06  sbb     ecx, ecx
0x18005da08  and     ecx, 0FFFC0000h
0x18005da0e  add     ecx, 0FFEFFFFFh
0x18005da14  and     ecx, ebx
0x18005da16  bt      ecx, 13h
0x18005da1a  jb      short loc_18005DA50
0x18005da1c  mov     byte ptr [rbp+57h+var_20+1], 0
0x18005da20  shr     ecx, 10h
0x18005da23  mov     dword ptr [rbp+57h+var_28+4], ecx
0x18005da26  jmp     loc_18005D940
0x18005da2b  mov     ecx, eax; Status
0x18005da2d  mov     [rbp+57h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x18005da35  call    cs:__imp_RtlNtStatusToDosError
0x18005da3b  mov     ecx, eax; dwErrCode
0x18005da3d  call    cs:__imp_SetLastError
0x18005da43  call    cs:__imp_GetLastError
0x18005da49  mov     ebx, eax
0x18005da4b  jmp     loc_18005D9AA
0x18005da50  mov     byte ptr [rbp+57h+var_20+1], 1
0x18005da54  btr     ecx, 13h
0x18005da58  jmp     short loc_18005DA20
0x18005da5a  cmp     eax, 0C0000017h
0x18005da5f  jz      short loc_18005DA6F
0x18005da61  cmp     eax, 0C000009Ah
0x18005da66  jz      short loc_18005DA6F
0x18005da68  mov     ebx, 3
0x18005da6d  jmp     short loc_18005DA87
0x18005da6f  mov     ecx, eax; Status
0x18005da71  call    cs:__imp_RtlNtStatusToDosError
0x18005da77  mov     ecx, eax; dwErrCode
0x18005da79  call    cs:__imp_SetLastError
0x18005da7f  call    cs:__imp_GetLastError
0x18005da85  mov     ebx, eax
0x18005da87  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x18005da8e  jmp     loc_18005D9D8
```
