# SclpGetAndWriteBootEntry

- ea: `0x18000ec38`
- end: `0x18000f109`
- name: `SclpGetAndWriteBootEntry`
- size: `1233`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x18000f4e4`

## callees

- `0x180001c74`
- `0x18000a524`
- `0x18000ec38`
- `0x1800179c5`
- `0x1800179e0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000ee8f`
- `ntdll!RtlAllocateHeap` at `0x18000ee8f`
- `ntdll!RtlInitUnicodeString` at `0x18000ee19`
- `ntdll!RtlInitUnicodeString` at `0x18000ee19`
- `ntdll!NtClose` at `0x18000f0c9`
- `ntdll!NtClose` at `0x18000f0c9`
- `ntdll!RtlFreeHeap` at `0x18000f0b9`
- `ntdll!RtlFreeHeap` at `0x18000f0b9`
- `ntdll!NtCreateFile` at `0x18000ef6c`
- `ntdll!NtCreateFile` at `0x18000ef6c`
- `ntdll!wcsrchr` at `0x18000ed61`
- `ntdll!wcsrchr` at `0x18000ed61`
- `ntdll!NtWriteFile` at `0x18000efc8`
- `ntdll!NtWriteFile` at `0x18000f022`
- `ntdll!NtWriteFile` at `0x18000f06e`
- `ntdll!NtWriteFile` at `0x18000efc8`
- `ntdll!NtWriteFile` at `0x18000f022`
- `ntdll!NtWriteFile` at `0x18000f06e`
- `ntdll!swprintf_s` at `0x18000ed93`
- `ntdll!swprintf_s` at `0x18000ed93`
- `ntdll!NtQuerySystemEnvironmentValueEx` at `0x18000ee39`
- `ntdll!NtQuerySystemEnvironmentValueEx` at `0x18000eee5`
- `ntdll!NtQuerySystemEnvironmentValueEx` at `0x18000ee39`
- `ntdll!NtQuerySystemEnvironmentValueEx` at `0x18000eee5`
- `ntdll!wcsncpy_s` at `0x18000ed1e`
- `ntdll!wcsncpy_s` at `0x18000ed50`
- `ntdll!wcsncpy_s` at `0x18000edc0`
- `ntdll!wcsncpy_s` at `0x18000ed1e`
- `ntdll!wcsncpy_s` at `0x18000ed50`
- `ntdll!wcsncpy_s` at `0x18000edc0`

## string_xrefs

- `0x18000ede8`: `SclpGetAndWriteBootEntry`
- `0x18000ef82`: `(%lx): Failed to create boot entry recovery file`

## pseudocode

```c
__int64 __fastcall SclpGetAndWriteBootEntry(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  __int64 v5; // rax
  wchar_t *v6; // rax
  __int64 v7; // r12
  __int64 v8; // rdi
  NTSTATUS v9; // eax
  unsigned int v10; // ebx
  PVOID Heap; // rax
  void *v12; // rsi
  NTSTATUS v13; // eax
  NTSTATUS v14; // eax
  int v15; // r9d
  char *v16; // rax
  NTSTATUS v17; // eax
  NTSTATUS v18; // eax
  NTSTATUS v19; // eax
  ULONG ShareAccess[2]; // [rsp+30h] [rbp-D0h]
  ULONG ShareAccessa[2]; // [rsp+30h] [rbp-D0h]
  ULONG ReturnLength; // [rsp+60h] [rbp-A0h] BYREF
  void *FileHandle; // [rsp+68h] [rbp-98h] BYREF
  __int64 v25; // [rsp+70h] [rbp-90h] BYREF
  __int64 v26; // [rsp+78h] [rbp-88h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-70h] BYREF
  struct _UNICODE_STRING v29; // [rsp+A0h] [rbp-60h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-50h] BYREF
  GUID VendorGuid; // [rsp+E0h] [rbp-20h] BYREF
  wchar_t Buffer[8]; // [rsp+F0h] [rbp-10h] BYREF
  __int16 v33; // [rsp+100h] [rbp+0h]
  wchar_t Destination[264]; // [rsp+110h] [rbp+10h] BYREF

  v33 = 0;
  DestinationString = 0;
  *(_OWORD *)Buffer = 0;
  memset_0(Destination, 0, 0x208u);
  VendorGuid.Data1 = -1947934879;
  *(_DWORD *)&VendorGuid.Data2 = 299013066;
  ReturnLength = 0;
  v25 = 0;
  v26 = 0;
  *(_DWORD *)VendorGuid.Data4 = -536867414;
  *(_DWORD *)&VendorGuid.Data4[4] = -1943338088;
  FileHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  v29 = 0;
  if ( !a2 || !*(_WORD *)(a2 + 528) || !*(_WORD *)(a2 + 1048) )
    return 3221225485LL;
  wcsncpy_s(Destination, 0x104u, (const wchar_t *)(a2 + 528), 0x103u);
  v4 = -1;
  v5 = -1;
  do
    ++v5;
  while ( Destination[v5] );
  wcsncpy_s(&Destination[v5], 260 - v5, (const wchar_t *)(a2 + 1048), 259 - v5);
  v6 = wcsrchr(Destination, 0x5Cu);
  if ( !v6 || *v6 != 92 )
    return 13;
  v6[1] = 0;
  v7 = *(unsigned int *)(a2 + 4);
  swprintf_s(Buffer, 9u, L"Boot%04x", v7);
  do
    ++v4;
  while ( Destination[v4] );
  wcsncpy_s(&Destination[v4], 260 - v4, Buffer, 259 - v4);
  v8 = a1 + 1152;
  if ( !a1 )
    v8 = 0;
  SclLogGenericMessage(
    v8,
    1,
    (int)SclEvent_Generic_Info,
    690,
    (__int64)"SclpGetAndWriteBootEntry",
    "Writing to NVRBoot file [%ws]",
    Destination);
  RtlInitUnicodeString(&DestinationString, Buffer);
  ReturnLength = 0;
  v9 = NtQuerySystemEnvironmentValueEx(&DestinationString, &VendorGuid, 0, &ReturnLength, 0);
  v10 = v9;
  if ( v9 == -1073741789 )
  {
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, ReturnLength);
    v12 = Heap;
    if ( !Heap )
    {
      v10 = -1073741801;
      SclLogGenericMessage(
        v8,
        3,
        (int)SclEvent_Generic_Error,
        718,
        (__int64)"SclpGetAndWriteBootEntry",
        "Failed to allocate boot entry buffer.");
      goto LABEL_28;
    }
    v13 = NtQuerySystemEnvironmentValueEx(&DestinationString, &VendorGuid, Heap, &ReturnLength, 0);
    v10 = v13;
    if ( v13 )
    {
      ShareAccess[0] = v13;
      SclLogGenericMessage(
        v8,
        3,
        (int)SclEvent_Generic_Error,
        733,
        (__int64)"SclpGetAndWriteBootEntry",
        "(%lx): Failed to get boot entry.",
        *(_QWORD *)ShareAccess);
LABEL_27:
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
      goto LABEL_28;
    }
    INIT_OBJA_EX((__int64)&ObjectAttributes, &v29, Destination, 64, 0);
    v14 = NtCreateFile(&FileHandle, 0x12019Fu, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 3u, 5u, 0x20u, 0, 0);
    v10 = v14;
    if ( v14 >= 0 )
    {
      v25 = v7;
      v17 = NtWriteFile(FileHandle, 0, 0, 0, &IoStatusBlock, &v25, 8u, 0, 0);
      v10 = v17;
      if ( v17 >= 0 )
      {
        v26 = ReturnLength;
        v18 = NtWriteFile(FileHandle, 0, 0, 0, &IoStatusBlock, &v26, 8u, 0, 0);
        v10 = v18;
        if ( v18 >= 0 )
        {
          v19 = NtWriteFile(FileHandle, 0, 0, 0, &IoStatusBlock, v12, ReturnLength, 0, 0);
          v10 = v19;
          if ( v19 >= 0 )
            goto LABEL_27;
          ShareAccessa[0] = v19;
          v15 = 834;
          v16 = "(%lx): Failed writing boot entry to boot entry recovery file.";
        }
        else
        {
          ShareAccessa[0] = v18;
          v15 = 814;
          v16 = "(%lx): Failed writing boot entry size to boot entry recovery file.";
        }
      }
      else
      {
        ShareAccessa[0] = v17;
        v15 = 793;
        v16 = "(%lx): Failed writing boot number to boot entry recovery file.";
      }
    }
    else
    {
      ShareAccessa[0] = v14;
      v15 = 760;
      v16 = "(%lx): Failed to create boot entry recovery file";
    }
    SclLogGenericMessage(
      v8,
      3,
      (int)SclEvent_Generic_Error,
      v15,
      (__int64)"SclpGetAndWriteBootEntry",
      v16,
      *(_QWORD *)ShareAccessa);
    goto LABEL_27;
  }
  SclLogGenericMessage(
    v8,
    3,
    (int)SclEvent_Generic_Error,
    707,
    (__int64)"SclpGetAndWriteBootEntry",
    "(%lx): Failed to get size for boot entry buffer.",
    v9);
LABEL_28:
  if ( FileHandle )
    NtClose(FileHandle);
  return v10;
}

```

## disassembly

```asm
0x18000ec38  mov     [rsp-8+arg_10], rbx
0x18000ec3d  push    rbp
0x18000ec3e  push    rsi
0x18000ec3f  push    rdi
0x18000ec40  push    r12
0x18000ec42  push    r13
0x18000ec44  push    r14
0x18000ec46  push    r15
0x18000ec48  lea     rbp, [rsp-230h]
0x18000ec50  sub     rsp, 330h
0x18000ec57  mov     rax, cs:__security_cookie
0x18000ec5e  xor     rax, rsp
0x18000ec61  mov     [rbp+260h+var_40], rax
0x18000ec68  mov     rdi, rdx
0x18000ec6b  mov     r13, rcx
0x18000ec6e  xorps   xmm0, xmm0
0x18000ec71  lea     rcx, [rbp+260h+Destination]; void *
0x18000ec75  xorps   xmm1, xmm1
0x18000ec78  xor     eax, eax
0x18000ec7a  xor     edx, edx; Val
0x18000ec7c  mov     [rbp+260h+var_260], ax
0x18000ec80  mov     r8d, 208h; Size
0x18000ec86  movups  xmmword ptr [rbp+260h+DestinationString.Length], xmm0
0x18000ec8a  movups  xmmword ptr [rbp+260h+Buffer], xmm1
0x18000ec8e  call    memset_0
0x18000ec93  xorps   xmm0, xmm0
0x18000ec96  mov     [rbp+260h+VendorGuid.Data1], 8BE4DF61h
0x18000ec9d  xor     r12d, r12d
0x18000eca0  mov     dword ptr [rbp+260h+VendorGuid.Data2], 11D293CAh
0x18000eca7  xor     eax, eax
0x18000eca9  mov     [rsp+360h+ReturnLength], r12d
0x18000ecae  mov     [rsp+360h+var_2F0], r12
0x18000ecb3  mov     [rsp+360h+var_2E8], r12
0x18000ecb8  mov     dword ptr [rbp+260h+VendorGuid.Data4], 0E0000DAAh
0x18000ecbf  mov     dword ptr [rbp+260h+VendorGuid.Data4+4], 8C2B0398h
0x18000ecc6  mov     [rsp+360h+FileHandle], r12
0x18000eccb  movups  xmmword ptr [rbp+260h+ObjectAttributes.ObjectName], xmm0
0x18000eccf  movups  xmmword ptr [rbp+260h+ObjectAttributes+1Ch], xmm0
0x18000ecd3  movups  xmmword ptr [rbp+260h+ObjectAttributes.Length], xmm0
0x18000ecd7  movups  xmmword ptr [rbp+260h+IoStatusBlock], xmm0
0x18000ecdb  movups  [rbp+260h+var_2C0], xmm0
0x18000ecdf  test    rdi, rdi
0x18000ece2  jz      loc_18000F0DA
0x18000ece8  lea     r8, [rdi+210h]; Source
0x18000ecef  cmp     r12w, [r8]
0x18000ecf3  jz      loc_18000F0DA
0x18000ecf9  lea     rsi, [rdi+418h]
0x18000ed00  cmp     r12w, [rsi]
0x18000ed04  jz      loc_18000F0DA
0x18000ed0a  mov     r14d, 103h
0x18000ed10  lea     rcx, [rbp+260h+Destination]; Destination
0x18000ed14  mov     r9d, r14d; MaxCount
0x18000ed17  lea     r15d, [r14+1]
0x18000ed1b  mov     edx, r15d; SizeInWords
0x18000ed1e  call    cs:__imp_wcsncpy_s
0x18000ed24  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000ed28  lea     rcx, [rbp+260h+Destination]
0x18000ed2c  mov     rax, rbx
0x18000ed2f  inc     rax
0x18000ed32  cmp     [rcx+rax*2], r12w
0x18000ed37  jnz     short loc_18000ED2F
0x18000ed39  mov     r9, r14
0x18000ed3c  lea     rcx, [rbp+260h+Destination]
0x18000ed40  mov     rdx, r15
0x18000ed43  lea     rcx, [rcx+rax*2]; Destination
0x18000ed47  sub     r9, rax; MaxCount
0x18000ed4a  sub     rdx, rax; SizeInWords
0x18000ed4d  mov     r8, rsi; Source
0x18000ed50  call    cs:__imp_wcsncpy_s
0x18000ed56  mov     esi, 5Ch ; '\'
0x18000ed5b  lea     rcx, [rbp+260h+Destination]; Str
0x18000ed5f  mov     edx, esi; Ch
0x18000ed61  call    cs:__imp_wcsrchr
0x18000ed67  test    rax, rax
0x18000ed6a  jz      loc_18000F0D3
0x18000ed70  cmp     si, [rax]
0x18000ed73  jnz     loc_18000F0D3
0x18000ed79  mov     [rax+2], r12w
0x18000ed7e  lea     r8, aBoot04x; "Boot%04x"
0x18000ed85  mov     r12d, [rdi+4]
0x18000ed89  lea     edx, [rsi-53h]; BufferCount
0x18000ed8c  mov     r9d, r12d
0x18000ed8f  lea     rcx, [rbp+260h+Buffer]; Buffer
0x18000ed93  call    cs:__imp_swprintf_s
0x18000ed99  lea     rcx, [rbp+260h+Destination]
0x18000ed9d  xor     eax, eax
0x18000ed9f  inc     rbx
0x18000eda2  cmp     [rcx+rbx*2], ax
0x18000eda6  jnz     short loc_18000ED9F
0x18000eda8  sub     r14, rbx
0x18000edab  lea     rcx, [rbp+260h+Destination]
0x18000edaf  sub     r15, rbx
0x18000edb2  lea     rcx, [rcx+rbx*2]; Destination
0x18000edb6  mov     r9, r14; MaxCount
0x18000edb9  lea     r8, [rbp+260h+Buffer]; Source
0x18000edbd  mov     rdx, r15; SizeInWords
0x18000edc0  call    cs:__imp_wcsncpy_s
0x18000edc6  xor     r14d, r14d
0x18000edc9  lea     rax, [rbp+260h+Destination]
0x18000edcd  mov     qword ptr [rsp+360h+ShareAccess], rax
0x18000edd2  lea     rdi, [r13+480h]
0x18000edd9  test    r13, r13
0x18000eddc  lea     rax, aWritingToNvrbo; "Writing to NVRBoot file [%ws]"
0x18000ede3  mov     qword ptr [rsp+360h+FileAttributes], rax
0x18000ede8  lea     r13, aSclpgetandwrit; "SclpGetAndWriteBootEntry"
0x18000edef  cmovz   rdi, r14
0x18000edf3  mov     [rsp+360h+Attributes], r13
0x18000edf8  mov     rcx, rdi
0x18000edfb  lea     r8, SclEvent_Generic_Info
0x18000ee02  mov     r9d, 2B2h
0x18000ee08  lea     edx, [r14+1]
0x18000ee0c  call    SclLogGenericMessage
0x18000ee11  lea     rdx, [rbp+260h+Buffer]; SourceString
0x18000ee15  lea     rcx, [rbp+260h+DestinationString]; DestinationString
0x18000ee19  call    cs:__imp_RtlInitUnicodeString
0x18000ee1f  lea     r9, [rsp+360h+ReturnLength]; ReturnLength
0x18000ee24  mov     [rsp+360h+ReturnLength], r14d
0x18000ee29  xor     r8d, r8d; Value
0x18000ee2c  mov     [rsp+360h+Attributes], r14; Attributes
0x18000ee31  lea     rdx, [rbp+260h+VendorGuid]; VendorGuid
0x18000ee35  lea     rcx, [rbp+260h+DestinationString]; VariableName
0x18000ee39  call    cs:__imp_NtQuerySystemEnvironmentValueEx
0x18000ee3f  mov     ebx, eax
0x18000ee41  cmp     eax, 0C0000023h
0x18000ee46  jz      short loc_18000EE7B
0x18000ee48  mov     [rsp+360h+ShareAccess], eax
0x18000ee4c  lea     r8, SclEvent_Generic_Error
0x18000ee53  lea     rax, aLxFailedToGetS; "(%lx): Failed to get size for boot entr"...
0x18000ee5a  mov     r9d, 2C3h
0x18000ee60  mov     qword ptr [rsp+360h+FileAttributes], rax
0x18000ee65  lea     edx, [r14+3]
0x18000ee69  mov     rcx, rdi
0x18000ee6c  mov     [rsp+360h+Attributes], r13
0x18000ee71  call    SclLogGenericMessage
0x18000ee76  jmp     loc_18000F0BF
0x18000ee7b  mov     rcx, gs:60h
0x18000ee84  xor     edx, edx; Flags
0x18000ee86  mov     r8d, [rsp+360h+ReturnLength]; Size
0x18000ee8b  mov     rcx, [rcx+30h]; HeapHandle
0x18000ee8f  call    cs:__imp_RtlAllocateHeap
0x18000ee95  mov     rsi, rax
0x18000ee98  test    rax, rax
0x18000ee9b  jnz     short loc_18000EED0
0x18000ee9d  lea     rax, aFailedToAlloca; "Failed to allocate boot entry buffer."
0x18000eea4  mov     r9d, 2CEh
0x18000eeaa  mov     qword ptr [rsp+360h+FileAttributes], rax
0x18000eeaf  lea     r8, SclEvent_Generic_Error
0x18000eeb6  lea     edx, [rsi+3]
0x18000eeb9  mov     [rsp+360h+Attributes], r13
0x18000eebe  mov     rcx, rdi
0x18000eec1  mov     ebx, 0C0000017h
0x18000eec6  call    SclLogGenericMessage
0x18000eecb  jmp     loc_18000F0BF
0x18000eed0  lea     r9, [rsp+360h+ReturnLength]; ReturnLength
0x18000eed5  mov     [rsp+360h+Attributes], r14; Attributes
0x18000eeda  mov     r8, rsi; Value
0x18000eedd  lea     rdx, [rbp+260h+VendorGuid]; VendorGuid
0x18000eee1  lea     rcx, [rbp+260h+DestinationString]; VariableName
0x18000eee5  call    cs:__imp_NtQuerySystemEnvironmentValueEx
0x18000eeeb  mov     ebx, eax
0x18000eeed  test    eax, eax
0x18000eeef  jz      short loc_18000EF0C
0x18000eef1  mov     [rsp+360h+ShareAccess], eax
0x18000eef5  mov     r9d, 2DDh
0x18000eefb  lea     rax, aLxFailedToGetB; "(%lx): Failed to get boot entry."
0x18000ef02  mov     edx, 3
0x18000ef07  jmp     loc_18000F08E
0x18000ef0c  mov     r9d, 40h ; '@'
0x18000ef12  mov     [rsp+360h+Attributes], r14
0x18000ef17  lea     r8, [rbp+260h+Destination]
0x18000ef1b  lea     rdx, [rbp+260h+var_2C0]
0x18000ef1f  lea     rcx, [rbp+260h+ObjectAttributes]
0x18000ef23  call    INIT_OBJA_EX
0x18000ef28  mov     [rsp+360h+EaLength], r14d; EaLength
0x18000ef2d  lea     r9, [rbp+260h+IoStatusBlock]; IoStatusBlock
0x18000ef31  mov     [rsp+360h+EaBuffer], r14; EaBuffer
0x18000ef36  lea     r8, [rbp+260h+ObjectAttributes]; ObjectAttributes
0x18000ef3a  mov     [rsp+360h+CreateOptions], 20h ; ' '; CreateOptions
0x18000ef42  lea     rcx, [rsp+360h+FileHandle]; FileHandle
0x18000ef47  mov     [rsp+360h+CreateDisposition], 5; CreateDisposition
0x18000ef4f  mov     r15d, 3
0x18000ef55  mov     [rsp+360h+ShareAccess], r15d; ShareAccess
0x18000ef5a  mov     edx, 12019Fh; DesiredAccess
0x18000ef5f  mov     [rsp+360h+FileAttributes], 80h; FileAttributes
0x18000ef67  mov     [rsp+360h+Attributes], r14; AllocationSize
0x18000ef6c  call    cs:__imp_NtCreateFile
0x18000ef72  mov     ebx, eax
0x18000ef74  test    eax, eax
0x18000ef76  jns     short loc_18000EF8E
0x18000ef78  mov     [rsp+360h+ShareAccess], eax
0x18000ef7c  mov     r9d, 2F8h
0x18000ef82  lea     rax, aLxFailedToCrea_7; "(%lx): Failed to create boot entry reco"...
0x18000ef89  jmp     loc_18000F08B
0x18000ef8e  mov     rcx, [rsp+360h+FileHandle]; FileHandle
0x18000ef93  lea     rax, [rsp+360h+var_2F0]
0x18000ef98  mov     qword ptr [rsp+360h+CreateOptions], r14; Key
0x18000ef9d  xor     r9d, r9d; ApcContext
0x18000efa0  mov     qword ptr [rsp+360h+CreateDisposition], r14; ByteOffset
0x18000efa5  xor     r8d, r8d; ApcRoutine
0x18000efa8  mov     [rsp+360h+var_2F0], r12
0x18000efad  xor     edx, edx; Event
0x18000efaf  mov     r12d, 8
0x18000efb5  mov     [rsp+360h+ShareAccess], r12d; Length
0x18000efba  mov     qword ptr [rsp+360h+FileAttributes], rax; Buffer
0x18000efbf  lea     rax, [rbp+260h+IoStatusBlock]
0x18000efc3  mov     [rsp+360h+Attributes], rax; IoStatusBlock
0x18000efc8  call    cs:__imp_NtWriteFile
0x18000efce  mov     ebx, eax
0x18000efd0  test    eax, eax
0x18000efd2  jns     short loc_18000EFEA
0x18000efd4  mov     [rsp+360h+ShareAccess], eax
0x18000efd8  mov     r9d, 319h
0x18000efde  lea     rax, aLxFailedWritin_1; "(%lx): Failed writing boot number to bo"...
0x18000efe5  jmp     loc_18000F08B
0x18000efea  mov     eax, [rsp+360h+ReturnLength]
0x18000efee  xor     r9d, r9d; ApcContext
0x18000eff1  mov     rcx, [rsp+360h+FileHandle]; FileHandle
0x18000eff6  xor     r8d, r8d; ApcRoutine
0x18000eff9  mov     qword ptr [rsp+360h+CreateOptions], r14; Key
0x18000effe  xor     edx, edx; Event
0x18000f000  mov     [rsp+360h+var_2E8], rax
0x18000f005  lea     rax, [rsp+360h+var_2E8]
0x18000f00a  mov     qword ptr [rsp+360h+CreateDisposition], r14; ByteOffset
0x18000f00f  mov     [rsp+360h+ShareAccess], r12d; Length
0x18000f014  mov     qword ptr [rsp+360h+FileAttributes], rax; Buffer
0x18000f019  lea     rax, [rbp+260h+IoStatusBlock]
0x18000f01d  mov     [rsp+360h+Attributes], rax; IoStatusBlock
0x18000f022  call    cs:__imp_NtWriteFile
0x18000f028  mov     ebx, eax
0x18000f02a  test    eax, eax
0x18000f02c  jns     short loc_18000F041
0x18000f02e  mov     [rsp+360h+ShareAccess], eax
0x18000f032  mov     r9d, 32Eh
0x18000f038  lea     rax, aLxFailedWritin; "(%lx): Failed writing boot entry size t"...
0x18000f03f  jmp     short loc_18000F08B
0x18000f041  mov     eax, [rsp+360h+ReturnLength]
0x18000f045  xor     r9d, r9d; ApcContext
0x18000f048  mov     rcx, [rsp+360h+FileHandle]; FileHandle
0x18000f04d  xor     r8d, r8d; ApcRoutine
0x18000f050  mov     qword ptr [rsp+360h+CreateOptions], r14; Key
0x18000f055  xor     edx, edx; Event
0x18000f057  mov     qword ptr [rsp+360h+CreateDisposition], r14; ByteOffset
0x18000f05c  mov     [rsp+360h+ShareAccess], eax; Length
0x18000f060  lea     rax, [rbp+260h+IoStatusBlock]
0x18000f064  mov     qword ptr [rsp+360h+FileAttributes], rsi; Buffer
0x18000f069  mov     [rsp+360h+Attributes], rax; IoStatusBlock
0x18000f06e  call    cs:__imp_NtWriteFile
0x18000f074  mov     ebx, eax
0x18000f076  test    eax, eax
0x18000f078  jns     short loc_18000F0A7
0x18000f07a  mov     [rsp+360h+ShareAccess], eax
0x18000f07e  mov     r9d, 342h
0x18000f084  lea     rax, aLxFailedWritin_0; "(%lx): Failed writing boot entry to boo"...
0x18000f08b  mov     edx, r15d
0x18000f08e  mov     qword ptr [rsp+360h+FileAttributes], rax
0x18000f093  lea     r8, SclEvent_Generic_Error
0x18000f09a  mov     rcx, rdi
0x18000f09d  mov     [rsp+360h+Attributes], r13
0x18000f0a2  call    SclLogGenericMessage
0x18000f0a7  mov     rcx, gs:60h
0x18000f0b0  mov     r8, rsi; P
0x18000f0b3  xor     edx, edx; Flags
0x18000f0b5  mov     rcx, [rcx+30h]; HeapHandle
0x18000f0b9  call    cs:__imp_RtlFreeHeap
0x18000f0bf  mov     rcx, [rsp+360h+FileHandle]; Handle
0x18000f0c4  test    rcx, rcx
0x18000f0c7  jz      short loc_18000F0CF
0x18000f0c9  call    cs:__imp_NtClose
0x18000f0cf  mov     eax, ebx
0x18000f0d1  jmp     short loc_18000F0DF
0x18000f0d3  mov     eax, 0Dh
0x18000f0d8  jmp     short loc_18000F0DF
0x18000f0da  mov     eax, 0C000000Dh
0x18000f0df  mov     rcx, [rbp+260h+var_40]
0x18000f0e6  xor     rcx, rsp; StackCookie
0x18000f0e9  call    __security_check_cookie
0x18000f0ee  mov     rbx, [rsp+360h+arg_10]
0x18000f0f6  add     rsp, 330h
0x18000f0fd  pop     r15
0x18000f0ff  pop     r14
0x18000f101  pop     r13
0x18000f103  pop     r12
0x18000f105  pop     rdi
0x18000f106  pop     rsi
0x18000f107  pop     rbp
0x18000f108  retn
```
