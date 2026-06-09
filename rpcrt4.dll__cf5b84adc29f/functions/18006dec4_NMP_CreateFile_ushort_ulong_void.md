# NMP_CreateFile(ushort *,ulong,void * *)

- ea: `0x18006dec4`
- end: `0x18006e108`
- name: `?NMP_CreateFile@@YAJPEAGKPEAPEAX@Z`
- size: `580`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18006d4e0`

## callees

- `0x18006dec4`
- `0x1800ceda0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18006e01c`
- `ntdll!RtlFreeHeap` at `0x18006e01c`
- `ntdll!RtlReleaseRelativeName` at `0x18006dffe`
- `ntdll!RtlReleaseRelativeName` at `0x18006dffe`
- `ntdll!NtCreateFile` at `0x18006dfd8`
- `ntdll!NtCreateFile` at `0x18006dfd8`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x18006df29`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x18006df29`
- `ntdll!RtlNtStatusToDosError` at `0x18006e086`
- `ntdll!RtlNtStatusToDosError` at `0x18006e0d4`
- `ntdll!RtlNtStatusToDosError` at `0x18006e086`
- `ntdll!RtlNtStatusToDosError` at `0x18006e0d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e0a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e0ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e0a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e0ee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006e094`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006e0e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006e094`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006e0e2`

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
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C8h] [rbp+1Fh] BYREF
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
0x18006dec4  mov     [rsp-8+arg_18], rbx
0x18006dec9  push    rbp
0x18006deca  push    rsi
0x18006decb  push    rdi
0x18006decc  lea     rbp, [rsp-47h]
0x18006ded1  sub     rsp, 0F0h
0x18006ded8  mov     rax, cs:__security_cookie
0x18006dedf  xor     rax, rsp
0x18006dee2  mov     [rbp+57h+var_18], rax
0x18006dee6  xorps   xmm0, xmm0
0x18006dee9  mov     [rbp+57h+FileHandle], 0
0x18006def1  xor     eax, eax
0x18006def3  lea     r9, [rbp+57h+RelativeName]
0x18006def7  mov     rsi, r8
0x18006defa  mov     [rbp+57h+var_28], rax
0x18006defe  mov     ebx, edx
0x18006df00  mov     [rbp+57h+var_20], eax
0x18006df03  xorps   xmm1, xmm1
0x18006df06  lea     rdx, [rbp+57h+P]
0x18006df0a  xor     r8d, r8d
0x18006df0d  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18006df11  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18006df15  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18006df19  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18006df1d  movups  xmmword ptr [rbp+57h+P], xmm1
0x18006df21  movups  xmmword ptr [rbp+57h+RelativeName.RelativeName.Length], xmm0
0x18006df25  movups  xmmword ptr [rbp+57h+RelativeName.ContainingDirectory], xmm0
0x18006df29  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U_WithStatus
0x18006df30  nop     dword ptr [rax+rax+00h]
0x18006df35  test    eax, eax
0x18006df37  js      loc_18006E0BD
0x18006df3d  mov     rax, [rbp+57h+RelativeName.ContainingDirectory]
0x18006df41  mov     rdi, [rbp+57h+P+8]
0x18006df45  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x18006df49  lea     rax, [rbp+57h+P]
0x18006df4d  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18006df51  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18006df58  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18006df5f  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], 0
0x18006df67  bt      ebx, 14h
0x18006df6b  jb      loc_18006E04A
0x18006df71  mov     word ptr [rbp+57h+var_20], 101h
0x18006df77  mov     dword ptr [rbp+57h+var_28+4], 2
0x18006df7e  mov     [rsp+100h+EaLength], 0; EaLength
0x18006df86  lea     rax, [rbp+57h+var_28]
0x18006df8a  mov     [rsp+100h+EaBuffer], 0; EaBuffer
0x18006df93  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18006df97  mov     [rsp+100h+CreateOptions], 0; CreateOptions
0x18006df9f  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18006dfa3  mov     [rsp+100h+CreateDisposition], 1; CreateDisposition
0x18006dfab  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18006dfaf  mov     [rsp+100h+ShareAccess], 3; ShareAccess
0x18006dfb7  mov     edx, 0C0100080h; DesiredAccess
0x18006dfbc  mov     [rsp+100h+FileAttributes], 0; FileAttributes
0x18006dfc4  mov     [rsp+100h+AllocationSize], 0; AllocationSize
0x18006dfcd  mov     dword ptr [rbp+57h+var_28], 0Ch
0x18006dfd4  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], rax
0x18006dfd8  call    cs:__imp_NtCreateFile
0x18006dfdf  nop     dword ptr [rax+rax+00h]
0x18006dfe4  test    eax, eax
0x18006dfe6  js      loc_18006E07C
0x18006dfec  xor     ebx, ebx
0x18006dfee  mov     rax, [rbp+57h+FileHandle]
0x18006dff2  mov     [rsi], rax
0x18006dff5  test    rdi, rdi
0x18006dff8  jz      short loc_18006E028
0x18006dffa  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x18006dffe  call    cs:__imp_RtlReleaseRelativeName
0x18006e005  nop     dword ptr [rax+rax+00h]
0x18006e00a  mov     rcx, gs:60h
0x18006e013  mov     r8, rdi; P
0x18006e016  xor     edx, edx; Flags
0x18006e018  mov     rcx, [rcx+30h]; HeapHandle
0x18006e01c  call    cs:__imp_RtlFreeHeap
0x18006e023  nop     dword ptr [rax+rax+00h]
0x18006e028  mov     eax, ebx
0x18006e02a  mov     rcx, [rbp+57h+var_18]
0x18006e02e  xor     rcx, rsp; StackCookie
0x18006e031  call    __security_check_cookie
0x18006e036  mov     rbx, [rsp+100h+arg_18]
0x18006e03e  add     rsp, 0F0h
0x18006e045  pop     rdi
0x18006e046  pop     rsi
0x18006e047  pop     rbp
0x18006e048  retn
0x18006e04a  mov     eax, ebx
0x18006e04c  and     eax, 40000h
0x18006e051  setnz   byte ptr [rbp+57h+var_20]
0x18006e055  neg     eax
0x18006e057  sbb     ecx, ecx
0x18006e059  and     ecx, 0FFFC0000h
0x18006e05f  add     ecx, 0FFEFFFFFh
0x18006e065  and     ecx, ebx
0x18006e067  bt      ecx, 13h
0x18006e06b  jb      short loc_18006E0B3
0x18006e06d  mov     byte ptr [rbp+57h+var_20+1], 0
0x18006e071  shr     ecx, 10h
0x18006e074  mov     dword ptr [rbp+57h+var_28+4], ecx
0x18006e077  jmp     loc_18006DF7E
0x18006e07c  mov     ecx, eax; Status
0x18006e07e  mov     [rbp+57h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x18006e086  call    cs:__imp_RtlNtStatusToDosError
0x18006e08d  nop     dword ptr [rax+rax+00h]
0x18006e092  mov     ecx, eax; dwErrCode
0x18006e094  call    cs:__imp_SetLastError
0x18006e09b  nop     dword ptr [rax+rax+00h]
0x18006e0a0  call    cs:__imp_GetLastError
0x18006e0a7  nop     dword ptr [rax+rax+00h]
0x18006e0ac  mov     ebx, eax
0x18006e0ae  jmp     loc_18006DFEE
0x18006e0b3  mov     byte ptr [rbp+57h+var_20+1], 1
0x18006e0b7  btr     ecx, 13h
0x18006e0bb  jmp     short loc_18006E071
0x18006e0bd  cmp     eax, 0C0000017h
0x18006e0c2  jz      short loc_18006E0D2
0x18006e0c4  cmp     eax, 0C000009Ah
0x18006e0c9  jz      short loc_18006E0D2
0x18006e0cb  mov     ebx, 3
0x18006e0d0  jmp     short loc_18006E0FC
0x18006e0d2  mov     ecx, eax; Status
0x18006e0d4  call    cs:__imp_RtlNtStatusToDosError
0x18006e0db  nop     dword ptr [rax+rax+00h]
0x18006e0e0  mov     ecx, eax; dwErrCode
0x18006e0e2  call    cs:__imp_SetLastError
0x18006e0e9  nop     dword ptr [rax+rax+00h]
0x18006e0ee  call    cs:__imp_GetLastError
0x18006e0f5  nop     dword ptr [rax+rax+00h]
0x18006e0fa  mov     ebx, eax
0x18006e0fc  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x18006e103  jmp     loc_18006E028
```
