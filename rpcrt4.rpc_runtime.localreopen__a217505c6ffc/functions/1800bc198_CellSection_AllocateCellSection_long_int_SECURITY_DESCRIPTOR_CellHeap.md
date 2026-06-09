# CellSection::AllocateCellSection(long *,int,_SECURITY_DESCRIPTOR *,CellHeap *)

- ea: `0x1800bc198`
- end: `0x1800bc444`
- name: `?AllocateCellSection@CellSection@@SAPEAV1@PEAJHPEAU_SECURITY_DESCRIPTOR@@PEAVCellHeap@@@Z`
- size: `684`
- prototype: `struct CellSection *__fastcall(int *, int, struct _SECURITY_DESCRIPTOR *, struct CellHeap *)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800bc144`

## callees

- `0x180087e00`
- `0x1800bbff0`
- `0x1800bc198`
- `0x1800cc1a8`
- `0x1800cc2f8`
- `0x1800ceda0`

## import_xrefs

- `ntdll!NtCreateSection` at `0x1800bc2dd`
- `ntdll!NtCreateSection` at `0x1800bc2dd`
- `ntdll!RtlInitUnicodeString` at `0x1800bc277`
- `ntdll!RtlInitUnicodeString` at `0x1800bc277`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc394`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc3da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc394`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc3da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bc335`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bc3a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bc335`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bc3a7`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1800bc3c9`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1800bc3c9`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x1800bc380`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x1800bc380`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800bc202`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800bc202`

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
0x1800bc198  mov     [rsp-8+arg_8], rbx
0x1800bc19d  push    rbp
0x1800bc19e  push    rsi
0x1800bc19f  push    rdi
0x1800bc1a0  push    r12
0x1800bc1a2  push    r13
0x1800bc1a4  push    r14
0x1800bc1a6  push    r15
0x1800bc1a8  lea     rbp, [rsp-10h]
0x1800bc1ad  sub     rsp, 110h
0x1800bc1b4  mov     rax, cs:__security_cookie
0x1800bc1bb  xor     rax, rsp
0x1800bc1be  mov     [rbp+40h+var_40], rax
0x1800bc1c2  mov     esi, cs:?gPageSize@@3KA; ulong gPageSize
0x1800bc1c8  xorps   xmm1, xmm1
0x1800bc1cb  xorps   xmm0, xmm0
0x1800bc1ce  shl     esi, 4
0x1800bc1d1  movups  xmmword ptr [rbp+40h+DestinationString.Length], xmm0
0x1800bc1d5  mov     r12, r9
0x1800bc1d8  mov     r13, r8
0x1800bc1db  movups  xmmword ptr [rsp+140h+ObjectAttributes.Length], xmm1
0x1800bc1e0  mov     r15d, edx
0x1800bc1e3  mov     rbx, rcx
0x1800bc1e6  movups  xmmword ptr [rsp+140h+ObjectAttributes.ObjectName], xmm1
0x1800bc1eb  mov     [rsp+140h+SectionHandle], 0
0x1800bc1f4  movups  xmmword ptr [rsp+140h+ObjectAttributes.SecurityDescriptor], xmm1
0x1800bc1f9  mov     qword ptr [rsp+140h+MaximumSize], 0
0x1800bc202  call    cs:__imp_GetCurrentProcessId
0x1800bc209  nop     dword ptr [rax+rax+00h]
0x1800bc20e  mov     r14d, eax
0x1800bc211  xor     edi, edi
0x1800bc213  cmp     edi, 12Dh
0x1800bc219  jge     loc_1800BC361
0x1800bc21f  cmp     edi, 12Ch
0x1800bc225  jnz     short loc_1800BC22B
0x1800bc227  xor     edx, edx
0x1800bc229  jmp     short loc_1800BC273
0x1800bc22b  test    r15d, r15d
0x1800bc22e  jnz     short loc_1800BC25B
0x1800bc230  lea     edx, [r15+8]; int
0x1800bc234  lea     rcx, [rsp+140h+var_F0]; unsigned __int8 *
0x1800bc239  call    ?GenerateRandomNumber@@YAJPEAEH@Z; GenerateRandomNumber(uchar *,int)
0x1800bc23e  mov     [rbx], eax
0x1800bc240  test    eax, eax
0x1800bc242  jnz     loc_1800BC3B3
0x1800bc248  lea     r9, [rsp+140h+var_F0]; unsigned int *
0x1800bc24d  mov     r8d, r14d; unsigned int
0x1800bc250  lea     rcx, [rbp+40h+SourceString]; unsigned __int16 *
0x1800bc254  call    ?GenerateSectionName@@YAXPEAGHKPEAK@Z; GenerateSectionName(ushort *,int,ulong,ulong *)
0x1800bc259  jmp     short loc_1800BC26F
0x1800bc25b  xor     r9d, r9d; unsigned int *
0x1800bc25e  lea     rcx, [rbp+40h+SourceString]; unsigned __int16 *
0x1800bc262  mov     r8d, r14d; unsigned int
0x1800bc265  call    ?GenerateSectionName@@YAXPEAGHKPEAK@Z; GenerateSectionName(ushort *,int,ulong,ulong *)
0x1800bc26a  mov     edi, 12Bh
0x1800bc26f  lea     rdx, [rbp+40h+SourceString]; SourceString
0x1800bc273  lea     rcx, [rbp+40h+DestinationString]; DestinationString
0x1800bc277  call    cs:__imp_RtlInitUnicodeString
0x1800bc27e  nop     dword ptr [rax+rax+00h]
0x1800bc283  xor     ecx, ecx
0x1800bc285  mov     [rsp+140h+ObjectAttributes.Length], 30h ; '0'
0x1800bc28d  mov     [rsp+140h+FileHandle], rcx; FileHandle
0x1800bc292  lea     rax, [rbp+40h+DestinationString]
0x1800bc296  mov     [rsp+140h+ObjectAttributes.RootDirectory], rcx
0x1800bc29b  lea     r9, [rsp+140h+MaximumSize]; MaximumSize
0x1800bc2a0  mov     [rbp+40h+ObjectAttributes.SecurityQualityOfService], rcx
0x1800bc2a4  lea     r8, [rsp+140h+ObjectAttributes]; ObjectAttributes
0x1800bc2a9  mov     dword ptr [rsp+140h+MaximumSize+4], ecx
0x1800bc2ad  mov     edx, 0F0007h; DesiredAccess
0x1800bc2b2  mov     [rsp+140h+AllocationAttributes], 4000000h; AllocationAttributes
0x1800bc2ba  lea     rcx, [rsp+140h+SectionHandle]; SectionHandle
0x1800bc2bf  mov     [rsp+140h+SectionPageProtection], 4; SectionPageProtection
0x1800bc2c7  mov     [rsp+140h+ObjectAttributes.Attributes], 40h ; '@'
0x1800bc2cf  mov     [rsp+140h+ObjectAttributes.ObjectName], rax
0x1800bc2d4  mov     [rsp+140h+ObjectAttributes.SecurityDescriptor], r13
0x1800bc2d9  mov     dword ptr [rsp+140h+MaximumSize], esi
0x1800bc2dd  call    cs:__imp_NtCreateSection
0x1800bc2e4  nop     dword ptr [rax+rax+00h]
0x1800bc2e9  test    eax, eax
0x1800bc2eb  jns     short loc_1800BC329
0x1800bc2ed  cmp     eax, 0C0000017h
0x1800bc2f2  jz      short loc_1800BC31E
0x1800bc2f4  cmp     eax, 0C000009Ah
0x1800bc2f9  jz      short loc_1800BC359
0x1800bc2fb  cmp     eax, 0C0000044h
0x1800bc300  jz      short loc_1800BC359
0x1800bc302  lea     ecx, [rax+3FFFFFCDh]
0x1800bc308  cmp     ecx, 7
0x1800bc30b  ja      short loc_1800BC317
0x1800bc30d  mov     edx, 0C5h
0x1800bc312  bt      edx, ecx
0x1800bc315  jb      short loc_1800BC351
0x1800bc317  cmp     eax, 0C0000024h
0x1800bc31c  jz      short loc_1800BC34A
0x1800bc31e  mov     dword ptr [rbx], 0Eh
0x1800bc324  jmp     loc_1800BC3B3
0x1800bc329  cmp     eax, 40000000h
0x1800bc32e  jnz     short loc_1800BC361
0x1800bc330  mov     rcx, [rsp+140h+SectionHandle]; hObject
0x1800bc335  call    cs:__imp_CloseHandle
0x1800bc33c  nop     dword ptr [rax+rax+00h]
0x1800bc341  mov     [rsp+140h+SectionHandle], 0
0x1800bc34a  inc     edi
0x1800bc34c  jmp     loc_1800BC213
0x1800bc351  mov     dword ptr [rbx], 6E6h
0x1800bc357  jmp     short loc_1800BC3B3
0x1800bc359  mov     dword ptr [rbx], 6B9h
0x1800bc35f  jmp     short loc_1800BC3B3
0x1800bc361  mov     rcx, [rsp+140h+SectionHandle]; hFileMappingObject
0x1800bc366  xor     r9d, r9d; dwFileOffsetLow
0x1800bc369  movsxd  rax, esi
0x1800bc36c  xor     r8d, r8d; dwFileOffsetHigh
0x1800bc36f  xor     esi, esi
0x1800bc371  mov     edx, 0F001Fh; dwDesiredAccess
0x1800bc376  mov     qword ptr [rsp+140h+AllocationAttributes], rsi; lpBaseAddress
0x1800bc37b  mov     qword ptr [rsp+140h+SectionPageProtection], rax; dwNumberOfBytesToMap
0x1800bc380  call    cs:__imp_MapViewOfFileEx
0x1800bc387  nop     dword ptr [rax+rax+00h]
0x1800bc38c  mov     rdi, rax
0x1800bc38f  test    rax, rax
0x1800bc392  jnz     short loc_1800BC3B7
0x1800bc394  call    cs:__imp_GetLastError
0x1800bc39b  nop     dword ptr [rax+rax+00h]
0x1800bc3a0  mov     rcx, [rsp+140h+SectionHandle]; hObject
0x1800bc3a5  mov     [rbx], eax
0x1800bc3a7  call    cs:__imp_CloseHandle
0x1800bc3ae  nop     dword ptr [rax+rax+00h]
0x1800bc3b3  xor     eax, eax
0x1800bc3b5  jmp     short loc_1800BC41C
0x1800bc3b7  mov     edx, 1; dwSize
0x1800bc3bc  mov     r8d, 1000h; flAllocationType
0x1800bc3c2  mov     rcx, rdi; lpAddress
0x1800bc3c5  lea     r9d, [rdx+3]; flProtect
0x1800bc3c9  call    cs:__imp_VirtualAlloc
0x1800bc3d0  nop     dword ptr [rax+rax+00h]
0x1800bc3d5  test    rax, rax
0x1800bc3d8  jnz     short loc_1800BC3F7
0x1800bc3da  call    cs:__imp_GetLastError
0x1800bc3e1  nop     dword ptr [rax+rax+00h]
0x1800bc3e6  mov     rcx, [rsp+140h+SectionHandle]; void *
0x1800bc3eb  mov     rdx, rdi; void *
0x1800bc3ee  mov     [rbx], eax
0x1800bc3f0  call    ?CloseDbgSection@@YAXPEAX0@Z; CloseDbgSection(void *,void *)
0x1800bc3f5  jmp     short loc_1800BC3B3
0x1800bc3f7  mov     r8, [rsp+140h+SectionHandle]; void *
0x1800bc3fc  lea     rax, [rsp+140h+var_F0]
0x1800bc401  mov     r9, r12; struct CellHeap *
0x1800bc404  mov     qword ptr [rsp+140h+SectionPageProtection], rax; unsigned int *
0x1800bc409  mov     rdx, rbx; int *
0x1800bc40c  mov     [rbx], esi
0x1800bc40e  mov     rcx, rdi; this
0x1800bc411  call    ??0CellSection@@AEAA@PEAJPEAXPEAVCellHeap@@PEAK@Z; CellSection::CellSection(long *,void *,CellHeap *,ulong *)
0x1800bc416  cmp     [rbx], esi
0x1800bc418  cmovnz  rax, rsi
0x1800bc41c  mov     rcx, [rbp+40h+var_40]
0x1800bc420  xor     rcx, rsp; StackCookie
0x1800bc423  call    __security_check_cookie
0x1800bc428  mov     rbx, [rsp+140h+arg_8]
0x1800bc430  add     rsp, 110h
0x1800bc437  pop     r15
0x1800bc439  pop     r14
0x1800bc43b  pop     r13
0x1800bc43d  pop     r12
0x1800bc43f  pop     rdi
0x1800bc440  pop     rsi
0x1800bc441  pop     rbp
0x1800bc442  retn
```
