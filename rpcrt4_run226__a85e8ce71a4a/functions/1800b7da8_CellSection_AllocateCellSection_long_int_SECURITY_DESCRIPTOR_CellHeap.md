# CellSection::AllocateCellSection(long *,int,_SECURITY_DESCRIPTOR *,CellHeap *)

- ea: `0x1800b7da8`
- end: `0x1800b801a`
- name: `?AllocateCellSection@CellSection@@SAPEAV1@PEAJHPEAU_SECURITY_DESCRIPTOR@@PEAVCellHeap@@@Z`
- size: `626`
- prototype: `struct CellSection *__fastcall(int *, int, struct _SECURITY_DESCRIPTOR *, struct CellHeap *)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800b7d54`

## callees

- `0x180085f40`
- `0x1800b7c10`
- `0x1800b7da8`
- `0x1800c7670`
- `0x1800c77ac`
- `0x1800ca140`

## import_xrefs

- `ntdll!NtCreateSection` at `0x1800b7ee1`
- `ntdll!NtCreateSection` at `0x1800b7ee1`
- `ntdll!RtlInitUnicodeString` at `0x1800b7e81`
- `ntdll!RtlInitUnicodeString` at `0x1800b7e81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b7f83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b7fb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b7f83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b7fb7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b7f30`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b7f90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b7f30`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b7f90`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1800b7fac`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1800b7fac`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x1800b7f75`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x1800b7f75`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800b7e12`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800b7e12`

## pseudocode

```c
struct CellSection *__fastcall CellSection::AllocateCellSection(
        int *a1,
        int a2,
        struct _SECURITY_DESCRIPTOR *a3,
        struct CellHeap *a4)
{
  unsigned int v4; // esi
  int v9; // edx
  DWORD CurrentProcessId; // r14d
  int i; // edi
  WCHAR *v12; // rdx
  int RandomNumber; // eax
  int v14; // edx
  NTSTATUS v15; // eax
  void *v16; // rax
  void *v17; // rdi
  DWORD LastError; // eax
  void *v19; // rcx
  struct CellSection *result; // rax
  DWORD v21; // eax
  void *v22; // rcx
  void *v23; // r8
  void *SectionHandle; // [rsp+40h] [rbp-C0h] BYREF
  union _LARGE_INTEGER MaximumSize; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v26; // [rsp+50h] [rbp-B0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-78h] BYREF
  WCHAR SourceString[48]; // [rsp+A0h] [rbp-60h] BYREF

  v4 = 16 * gPageSize;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  SectionHandle = 0;
  MaximumSize.QuadPart = 0;
  CurrentProcessId = GetCurrentProcessId();
  for ( i = 0; i < 301; ++i )
  {
    if ( i == 300 )
    {
      v12 = 0;
    }
    else
    {
      if ( a2 )
      {
        GenerateSectionName(SourceString, v9, CurrentProcessId, 0);
        i = 299;
      }
      else
      {
        RandomNumber = GenerateRandomNumber((unsigned __int8 *)&v26, 8);
        *a1 = RandomNumber;
        if ( RandomNumber )
          return 0;
        GenerateSectionName(SourceString, v14, CurrentProcessId, &v26);
      }
      v12 = SourceString;
    }
    RtlInitUnicodeString(&DestinationString, v12);
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.SecurityQualityOfService = 0;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.SecurityDescriptor = a3;
    MaximumSize.QuadPart = v4;
    v15 = NtCreateSection(&SectionHandle, 0xF0007u, &ObjectAttributes, &MaximumSize, 4u, 0x4000000u, 0);
    if ( v15 >= 0 )
    {
      if ( v15 != 0x40000000 )
        break;
      CloseHandle(SectionHandle);
      SectionHandle = 0;
    }
    else
    {
      if ( v15 == -1073741801 )
        goto LABEL_17;
      if ( v15 == -1073741670 || v15 == -1073741756 )
      {
        *a1 = 1721;
        return 0;
      }
      if ( (unsigned int)(v15 + 1073741773) <= 7 )
      {
        v9 = 197;
        if ( _bittest(&v9, v15 + 1073741773) )
        {
          *a1 = 1766;
          return 0;
        }
      }
      if ( v15 != -1073741788 )
      {
LABEL_17:
        *a1 = 14;
        return 0;
      }
    }
  }
  v16 = MapViewOfFileEx(SectionHandle, 0xF001Fu, 0, 0, (int)v4, 0);
  v17 = v16;
  if ( !v16 )
  {
    LastError = GetLastError();
    v19 = SectionHandle;
    *a1 = LastError;
    CloseHandle(v19);
    return 0;
  }
  if ( !VirtualAlloc(v16, 1u, 0x1000u, 4u) )
  {
    v21 = GetLastError();
    v22 = SectionHandle;
    *a1 = v21;
    CloseDbgSection(v22, v17);
    return 0;
  }
  v23 = SectionHandle;
  *a1 = 0;
  result = CellSection::CellSection((CellSection *)v17, a1, v23, a4, &v26);
  if ( *a1 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x1800b7da8  mov     [rsp-8+arg_8], rbx
0x1800b7dad  push    rbp
0x1800b7dae  push    rsi
0x1800b7daf  push    rdi
0x1800b7db0  push    r12
0x1800b7db2  push    r13
0x1800b7db4  push    r14
0x1800b7db6  push    r15
0x1800b7db8  lea     rbp, [rsp-10h]
0x1800b7dbd  sub     rsp, 110h
0x1800b7dc4  mov     rax, cs:__security_cookie
0x1800b7dcb  xor     rax, rsp
0x1800b7dce  mov     [rbp+40h+var_40], rax
0x1800b7dd2  mov     esi, cs:?gPageSize@@3KA; ulong gPageSize
0x1800b7dd8  xorps   xmm1, xmm1
0x1800b7ddb  xorps   xmm0, xmm0
0x1800b7dde  shl     esi, 4
0x1800b7de1  movups  xmmword ptr [rbp+40h+DestinationString.Length], xmm0
0x1800b7de5  mov     r12, r9
0x1800b7de8  mov     r13, r8
0x1800b7deb  movups  xmmword ptr [rsp+140h+ObjectAttributes.Length], xmm1
0x1800b7df0  mov     r15d, edx
0x1800b7df3  mov     rbx, rcx
0x1800b7df6  movups  xmmword ptr [rsp+140h+ObjectAttributes.ObjectName], xmm1
0x1800b7dfb  mov     [rsp+140h+SectionHandle], 0
0x1800b7e04  movups  xmmword ptr [rsp+140h+ObjectAttributes.SecurityDescriptor], xmm1
0x1800b7e09  mov     qword ptr [rsp+140h+MaximumSize], 0
0x1800b7e12  call    cs:__imp_GetCurrentProcessId
0x1800b7e18  mov     r14d, eax
0x1800b7e1b  xor     edi, edi
0x1800b7e1d  cmp     edi, 12Dh
0x1800b7e23  jge     loc_1800B7F56
0x1800b7e29  cmp     edi, 12Ch
0x1800b7e2f  jnz     short loc_1800B7E35
0x1800b7e31  xor     edx, edx
0x1800b7e33  jmp     short loc_1800B7E7D
0x1800b7e35  test    r15d, r15d
0x1800b7e38  jnz     short loc_1800B7E65
0x1800b7e3a  lea     edx, [r15+8]; int
0x1800b7e3e  lea     rcx, [rsp+140h+var_F0]; unsigned __int8 *
0x1800b7e43  call    ?GenerateRandomNumber@@YAJPEAEH@Z; GenerateRandomNumber(uchar *,int)
0x1800b7e48  mov     [rbx], eax
0x1800b7e4a  test    eax, eax
0x1800b7e4c  jnz     loc_1800B7F96
0x1800b7e52  lea     r9, [rsp+140h+var_F0]; unsigned int *
0x1800b7e57  mov     r8d, r14d; unsigned int
0x1800b7e5a  lea     rcx, [rbp+40h+SourceString]; unsigned __int16 *
0x1800b7e5e  call    ?GenerateSectionName@@YAXPEAGHKPEAK@Z; GenerateSectionName(ushort *,int,ulong,ulong *)
0x1800b7e63  jmp     short loc_1800B7E79
0x1800b7e65  xor     r9d, r9d; unsigned int *
0x1800b7e68  lea     rcx, [rbp+40h+SourceString]; unsigned __int16 *
0x1800b7e6c  mov     r8d, r14d; unsigned int
0x1800b7e6f  call    ?GenerateSectionName@@YAXPEAGHKPEAK@Z; GenerateSectionName(ushort *,int,ulong,ulong *)
0x1800b7e74  mov     edi, 12Bh
0x1800b7e79  lea     rdx, [rbp+40h+SourceString]; SourceString
0x1800b7e7d  lea     rcx, [rbp+40h+DestinationString]; DestinationString
0x1800b7e81  call    cs:__imp_RtlInitUnicodeString
0x1800b7e87  xor     ecx, ecx
0x1800b7e89  mov     [rsp+140h+ObjectAttributes.Length], 30h ; '0'
0x1800b7e91  mov     [rsp+140h+FileHandle], rcx; FileHandle
0x1800b7e96  lea     rax, [rbp+40h+DestinationString]
0x1800b7e9a  mov     [rsp+140h+ObjectAttributes.RootDirectory], rcx
0x1800b7e9f  lea     r9, [rsp+140h+MaximumSize]; MaximumSize
0x1800b7ea4  mov     [rbp+40h+ObjectAttributes.SecurityQualityOfService], rcx
0x1800b7ea8  lea     r8, [rsp+140h+ObjectAttributes]; ObjectAttributes
0x1800b7ead  mov     dword ptr [rsp+140h+MaximumSize+4], ecx
0x1800b7eb1  mov     edx, 0F0007h; DesiredAccess
0x1800b7eb6  mov     [rsp+140h+AllocationAttributes], 4000000h; AllocationAttributes
0x1800b7ebe  lea     rcx, [rsp+140h+SectionHandle]; SectionHandle
0x1800b7ec3  mov     [rsp+140h+SectionPageProtection], 4; SectionPageProtection
0x1800b7ecb  mov     [rsp+140h+ObjectAttributes.Attributes], 40h ; '@'
0x1800b7ed3  mov     [rsp+140h+ObjectAttributes.ObjectName], rax
0x1800b7ed8  mov     [rsp+140h+ObjectAttributes.SecurityDescriptor], r13
0x1800b7edd  mov     dword ptr [rsp+140h+MaximumSize], esi
0x1800b7ee1  call    cs:__imp_NtCreateSection
0x1800b7ee7  test    eax, eax
0x1800b7ee9  jns     short loc_1800B7F24
0x1800b7eeb  cmp     eax, 0C0000017h
0x1800b7ef0  jz      short loc_1800B7F1C
0x1800b7ef2  cmp     eax, 0C000009Ah
0x1800b7ef7  jz      short loc_1800B7F4E
0x1800b7ef9  cmp     eax, 0C0000044h
0x1800b7efe  jz      short loc_1800B7F4E
0x1800b7f00  lea     ecx, [rax+3FFFFFCDh]
0x1800b7f06  cmp     ecx, 7
0x1800b7f09  ja      short loc_1800B7F15
0x1800b7f0b  mov     edx, 0C5h
0x1800b7f10  bt      edx, ecx
0x1800b7f13  jb      short loc_1800B7F46
0x1800b7f15  cmp     eax, 0C0000024h
0x1800b7f1a  jz      short loc_1800B7F3F
0x1800b7f1c  mov     dword ptr [rbx], 0Eh
0x1800b7f22  jmp     short loc_1800B7F96
0x1800b7f24  cmp     eax, 40000000h
0x1800b7f29  jnz     short loc_1800B7F56
0x1800b7f2b  mov     rcx, [rsp+140h+SectionHandle]; hObject
0x1800b7f30  call    cs:__imp_CloseHandle
0x1800b7f36  mov     [rsp+140h+SectionHandle], 0
0x1800b7f3f  inc     edi
0x1800b7f41  jmp     loc_1800B7E1D
0x1800b7f46  mov     dword ptr [rbx], 6E6h
0x1800b7f4c  jmp     short loc_1800B7F96
0x1800b7f4e  mov     dword ptr [rbx], 6B9h
0x1800b7f54  jmp     short loc_1800B7F96
0x1800b7f56  mov     rcx, [rsp+140h+SectionHandle]; hFileMappingObject
0x1800b7f5b  xor     r9d, r9d; dwFileOffsetLow
0x1800b7f5e  movsxd  rax, esi
0x1800b7f61  xor     r8d, r8d; dwFileOffsetHigh
0x1800b7f64  xor     esi, esi
0x1800b7f66  mov     edx, 0F001Fh; dwDesiredAccess
0x1800b7f6b  mov     qword ptr [rsp+140h+AllocationAttributes], rsi; lpBaseAddress
0x1800b7f70  mov     qword ptr [rsp+140h+SectionPageProtection], rax; dwNumberOfBytesToMap
0x1800b7f75  call    cs:__imp_MapViewOfFileEx
0x1800b7f7b  mov     rdi, rax
0x1800b7f7e  test    rax, rax
0x1800b7f81  jnz     short loc_1800B7F9A
0x1800b7f83  call    cs:__imp_GetLastError
0x1800b7f89  mov     rcx, [rsp+140h+SectionHandle]; hObject
0x1800b7f8e  mov     [rbx], eax
0x1800b7f90  call    cs:__imp_CloseHandle
0x1800b7f96  xor     eax, eax
0x1800b7f98  jmp     short loc_1800B7FF3
0x1800b7f9a  mov     edx, 1; dwSize
0x1800b7f9f  mov     r8d, 1000h; flAllocationType
0x1800b7fa5  mov     rcx, rdi; lpAddress
0x1800b7fa8  lea     r9d, [rdx+3]; flProtect
0x1800b7fac  call    cs:__imp_VirtualAlloc
0x1800b7fb2  test    rax, rax
0x1800b7fb5  jnz     short loc_1800B7FCE
0x1800b7fb7  call    cs:__imp_GetLastError
0x1800b7fbd  mov     rcx, [rsp+140h+SectionHandle]; void *
0x1800b7fc2  mov     rdx, rdi; void *
0x1800b7fc5  mov     [rbx], eax
0x1800b7fc7  call    ?CloseDbgSection@@YAXPEAX0@Z; CloseDbgSection(void *,void *)
0x1800b7fcc  jmp     short loc_1800B7F96
0x1800b7fce  mov     r8, [rsp+140h+SectionHandle]; void *
0x1800b7fd3  lea     rax, [rsp+140h+var_F0]
0x1800b7fd8  mov     r9, r12; struct CellHeap *
0x1800b7fdb  mov     qword ptr [rsp+140h+SectionPageProtection], rax; unsigned int *
0x1800b7fe0  mov     rdx, rbx; int *
0x1800b7fe3  mov     [rbx], esi
0x1800b7fe5  mov     rcx, rdi; this
0x1800b7fe8  call    ??0CellSection@@AEAA@PEAJPEAXPEAVCellHeap@@PEAK@Z; CellSection::CellSection(long *,void *,CellHeap *,ulong *)
0x1800b7fed  cmp     [rbx], esi
0x1800b7fef  cmovnz  rax, rsi
0x1800b7ff3  mov     rcx, [rbp+40h+var_40]
0x1800b7ff7  xor     rcx, rsp; StackCookie
0x1800b7ffa  call    __security_check_cookie
0x1800b7fff  mov     rbx, [rsp+140h+arg_8]
0x1800b8007  add     rsp, 110h
0x1800b800e  pop     r15
0x1800b8010  pop     r14
0x1800b8012  pop     r13
0x1800b8014  pop     r12
0x1800b8016  pop     rdi
0x1800b8017  pop     rsi
0x1800b8018  pop     rbp
0x1800b8019  retn
```
