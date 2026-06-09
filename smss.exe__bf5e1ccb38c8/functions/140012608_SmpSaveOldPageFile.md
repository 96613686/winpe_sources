# SmpSaveOldPageFile

- ea: `0x140012608`
- end: `0x14001279f`
- name: `SmpSaveOldPageFile`
- size: `407`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140009100`

## callees

- `0x1400113a0`
- `0x140012608`
- `0x1400127a8`

## import_xrefs

- `ntdll!NtOpenFile` at `0x14001268f`
- `ntdll!NtOpenFile` at `0x14001268f`
- `ntdll!NtClose` at `0x140012763`
- `ntdll!NtClose` at `0x140012763`
- `ntdll!RtlAllocateHeap` at `0x1400126cc`
- `ntdll!RtlAllocateHeap` at `0x1400126cc`
- `ntdll!RtlFreeHeap` at `0x140012787`
- `ntdll!RtlFreeHeap` at `0x140012787`
- `ntdll!RtlAppendUnicodeToString` at `0x14001270c`
- `ntdll!RtlAppendUnicodeToString` at `0x14001270c`
- `ntdll!RtlCopyUnicodeString` at `0x1400126fb`
- `ntdll!RtlCopyUnicodeString` at `0x1400126fb`

## pseudocode

```c
__int64 __fastcall SmpSaveOldPageFile(UNICODE_STRING *SourceString, _WORD *a2, unsigned int *a3)
{
  bool v3; // cf
  NTSTATUS v8; // ebx
  USHORT v9; // cx
  NTSTATUS appended; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-29h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-9h] BYREF
  void *FileHandle; // [rsp+D0h] [rbp+77h] BYREF

  v3 = *a3 < 0x10;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  FileHandle = 0;
  IoStatusBlock = 0;
  DestinationString = 0;
  if ( !v3 )
    return 3221225623LL;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = SourceString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v8 = NtOpenFile(&FileHandle, 0x80150100, &ObjectAttributes, &IoStatusBlock, 1u, 0x68u);
  if ( v8 >= 0 )
  {
    v9 = a2 ? *a2 + 20 : SourceString->Length + 10;
    DestinationString.MaximumLength = v9;
    DestinationString.Buffer = (PWSTR)RtlAllocateHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v9);
    if ( DestinationString.Buffer )
    {
      if ( a2 )
      {
        appended = RtlUnicodeStringPrintf(&DestinationString, L"%wZ\\pf%02u.dmp", a2, *a3);
      }
      else
      {
        RtlCopyUnicodeString(&DestinationString, SourceString);
        appended = RtlAppendUnicodeToString(&DestinationString, L".dmp");
      }
      v8 = appended;
      if ( appended >= 0 )
      {
        v8 = SmpSavePageFile(FileHandle);
        if ( v8 >= 0 )
        {
          *(struct _UNICODE_STRING *)&a3[4 * *a3 + 2] = DestinationString;
          a3[1] += DestinationString.Length;
          ++*a3;
        }
      }
    }
  }
  if ( FileHandle )
    NtClose(FileHandle);
  if ( v8 < 0 )
  {
    if ( DestinationString.Buffer )
      RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, DestinationString.Buffer);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140012608  push    rbp
0x14001260a  push    rbx
0x14001260b  push    rsi
0x14001260c  push    rdi
0x14001260d  push    r12
0x14001260f  push    r14
0x140012611  lea     rbp, [rsp-2Fh]
0x140012616  sub     rsp, 88h
0x14001261d  xor     eax, eax
0x14001261f  xorps   xmm0, xmm0
0x140012622  cmp     dword ptr [r8], 10h
0x140012626  xorps   xmm1, xmm1
0x140012629  mov     rdi, r8
0x14001262c  mov     dword ptr [rbp+57h+ObjectAttributes+4], eax
0x14001262f  mov     rsi, rdx
0x140012632  mov     dword ptr [rbp+57h+ObjectAttributes+1Ch], eax
0x140012635  mov     r14, rcx
0x140012638  mov     [rbp+57h+FileHandle], rax
0x14001263c  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140012640  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x140012644  jb      short loc_140012650
0x140012646  mov     eax, 0C0000097h
0x14001264b  jmp     loc_14001278F
0x140012650  mov     r12d, 1
0x140012656  mov     [rsp+0B0h+OpenOptions], 68h ; 'h'; OpenOptions
0x14001265e  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140012662  mov     [rsp+0B0h+ShareAccess], r12d; ShareAccess
0x140012667  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14001266b  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140012672  mov     edx, 80150100h; DesiredAccess
0x140012677  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x14001267b  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x14001267f  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x140012686  mov     [rbp+57h+ObjectAttributes.ObjectName], r14
0x14001268a  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001268f  call    cs:__imp_NtOpenFile
0x140012695  mov     ebx, eax
0x140012697  test    eax, eax
0x140012699  js      loc_14001275A
0x14001269f  test    rsi, rsi
0x1400126a2  jz      short loc_1400126AD
0x1400126a4  movzx   ecx, word ptr [rsi]
0x1400126a7  add     cx, 14h
0x1400126ab  jmp     short loc_1400126B5
0x1400126ad  movzx   ecx, word ptr [r14]
0x1400126b1  add     cx, 0Ah
0x1400126b5  mov     [rbp+57h+DestinationString.MaximumLength], cx
0x1400126b9  xor     edx, edx; Flags
0x1400126bb  movzx   r8d, cx; Size
0x1400126bf  mov     rcx, gs:60h
0x1400126c8  mov     rcx, [rcx+30h]; HeapHandle
0x1400126cc  call    cs:__imp_RtlAllocateHeap
0x1400126d2  mov     [rbp+57h+DestinationString.Buffer], rax
0x1400126d6  test    rax, rax
0x1400126d9  jz      short loc_14001275A
0x1400126db  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400126df  test    rsi, rsi
0x1400126e2  jz      short loc_1400126F8
0x1400126e4  mov     r9d, [rdi]
0x1400126e7  lea     rdx, aWzPf02uDmp; "%wZ\\pf%02u.dmp"
0x1400126ee  mov     r8, rsi
0x1400126f1  call    RtlUnicodeStringPrintf
0x1400126f6  jmp     short loc_140012712
0x1400126f8  mov     rdx, r14; SourceString
0x1400126fb  call    cs:__imp_RtlCopyUnicodeString
0x140012701  lea     rdx, SmpSavedPageFileExtension; ".dmp"
0x140012708  lea     rcx, [rbp+57h+DestinationString]; Destination
0x14001270c  call    cs:__imp_RtlAppendUnicodeToString
0x140012712  mov     ebx, eax
0x140012714  test    eax, eax
0x140012716  js      short loc_14001275A
0x140012718  xor     r9d, r9d
0x14001271b  test    rsi, rsi
0x14001271e  jnz     short loc_14001272B
0x140012720  cmp     cs:SmpForceCopyDumpFile, r9b
0x140012727  cmovz   r9d, r12d
0x14001272b  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x14001272f  lea     rdx, [rbp+57h+DestinationString]
0x140012733  xor     r8d, r8d
0x140012736  call    SmpSavePageFile
0x14001273b  mov     ebx, eax
0x14001273d  test    eax, eax
0x14001273f  js      short loc_14001275A
0x140012741  mov     eax, [rdi]
0x140012743  movups  xmm0, xmmword ptr [rbp+57h+DestinationString.Length]
0x140012747  add     rax, rax
0x14001274a  movdqu  xmmword ptr [rdi+rax*8+8], xmm0
0x140012750  movzx   eax, [rbp+57h+DestinationString.Length]
0x140012754  add     [rdi+4], eax
0x140012757  add     [rdi], r12d
0x14001275a  mov     rcx, [rbp+57h+FileHandle]; Handle
0x14001275e  test    rcx, rcx
0x140012761  jz      short loc_140012769
0x140012763  call    cs:__imp_NtClose
0x140012769  test    ebx, ebx
0x14001276b  jns     short loc_14001278D
0x14001276d  cmp     [rbp+57h+DestinationString.Buffer], 0
0x140012772  jz      short loc_14001278D
0x140012774  mov     rcx, gs:60h
0x14001277d  xor     edx, edx; Flags
0x14001277f  mov     r8, [rbp+57h+DestinationString.Buffer]; BaseAddress
0x140012783  mov     rcx, [rcx+30h]; HeapHandle
0x140012787  call    cs:__imp_RtlFreeHeap
0x14001278d  mov     eax, ebx
0x14001278f  add     rsp, 88h
0x140012796  pop     r14
0x140012798  pop     r12
0x14001279a  pop     rdi
0x14001279b  pop     rsi
0x14001279c  pop     rbx
0x14001279d  pop     rbp
0x14001279e  retn
```
