# ScpLastGoodWalkDirectoryTreeHelper(_UNICODE_STRING *,ulong,long (*)(_UNICODE_STRING *,_UNICODE_STRING *,ulong,void *),void *,uchar *,ulong,_LIST_ENTRY *)

- ea: `0x140045704`
- end: `0x1400459e4`
- name: `?ScpLastGoodWalkDirectoryTreeHelper@@YAJPEAU_UNICODE_STRING@@KP6AJ00KPEAX@Z1PEAEKPEAU_LIST_ENTRY@@@Z`
- size: `736`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, unsigned int, int (*)(struct _UNICODE_STRING *, struct _UNICODE_STRING *, unsigned int, void *), void *, PVOID FileInformation, unsigned int, struct _LIST_ENTRY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400454ec`

## callees

- `0x140045704`
- `0x14004b1c0`
- `0x140094020`

## import_xrefs

- `ntdll!NtOpenFile` at `0x140045793`
- `ntdll!NtOpenFile` at `0x140045793`
- `ntdll!RtlAppendUnicodeToString` at `0x1400458b1`
- `ntdll!RtlAppendUnicodeToString` at `0x1400458b1`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1400458be`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1400458be`
- `ntdll!NtWaitForSingleObject` at `0x140045804`
- `ntdll!NtWaitForSingleObject` at `0x140045804`
- `ntdll!NtQueryDirectoryFile` at `0x1400457e4`
- `ntdll!NtQueryDirectoryFile` at `0x1400457e4`
- `ntdll!RtlCopyUnicodeString` at `0x1400458a1`
- `ntdll!RtlCopyUnicodeString` at `0x1400458a1`
- `ntdll!NtClose` at `0x1400459be`
- `ntdll!NtClose` at `0x1400459be`
- `ntdll!RtlInitUnicodeString` at `0x14004583f`
- `ntdll!RtlInitUnicodeString` at `0x14004583f`
- `ntdll!RtlFreeHeap` at `0x140045977`
- `ntdll!RtlFreeHeap` at `0x140045977`
- `ntdll!RtlAllocateHeap` at `0x14004586d`
- `ntdll!RtlAllocateHeap` at `0x14004586d`

## pseudocode

```c
__int64 __fastcall ScpLastGoodWalkDirectoryTreeHelper(
        struct _UNICODE_STRING *a1,
        int a2,
        int (*a3)(struct _UNICODE_STRING *, struct _UNICODE_STRING *, unsigned int, void *),
        void *a4,
        unsigned int *FileInformation,
        unsigned int a6,
        struct _LIST_ENTRY *a7)
{
  char v7; // r12
  struct _UNICODE_STRING *v8; // rsi
  char v9; // di
  NTSTATUS Status; // ebx
  struct _LIST_ENTRY *v11; // r15
  unsigned int *v12; // rdi
  NTSTATUS v13; // eax
  unsigned __int64 v14; // rcx
  __int16 v15; // ax
  struct _UNICODE_STRING *Heap; // rax
  struct _LIST_ENTRY *v17; // rsi
  struct _UNICODE_STRING *v18; // r13
  __int64 v19; // r8
  bool v20; // r14
  struct _LIST_ENTRY *Blink; // rax
  BOOLEAN v23; // [rsp+58h] [rbp-71h]
  __int64 v24; // [rsp+68h] [rbp-61h]
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-59h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-49h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-39h] BYREF
  __int16 v29; // [rsp+120h] [rbp+57h]
  void *FileHandle; // [rsp+130h] [rbp+67h] BYREF

  ObjectAttributes.ObjectName = a1;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  v7 = a2;
  v8 = a1;
  FileHandle = 0;
  ObjectAttributes.RootDirectory = 0;
  v9 = 1;
  IoStatusBlock = 0;
  DestinationString = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  Status = NtOpenFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 1u, ~(a2 << 17) & 0x200000 | 0x4001);
  if ( Status >= 0 )
  {
    v11 = a7;
LABEL_3:
    v23 = v9;
    v12 = FileInformation;
    v13 = NtQueryDirectoryFile(
            FileHandle,
            0,
            0,
            0,
            &IoStatusBlock,
            FileInformation,
            0x3FEu,
            FileBothDirectoryInformation,
            0,
            0,
            v23);
    Status = v13;
    if ( v13 >= 0 )
    {
      if ( v13 != 259
        || (Status = NtWaitForSingleObject(FileHandle, 0, 0)) == 0
        && (Status = IoStatusBlock.Status, IoStatusBlock.Status >= 0) )
      {
        while ( 1 )
        {
          v14 = (unsigned __int64)v12[15] >> 1;
          v15 = *((_WORD *)v12 + v14 + 47);
          *((_WORD *)v12 + v14 + 47) = 0;
          v29 = v15;
          RtlInitUnicodeString(&DestinationString, (PCWSTR)v12 + 47);
          v24 = (unsigned __int16)(v8->Length + DestinationString.Length + 2);
          Heap = (struct _UNICODE_STRING *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v24 + 40);
          v17 = (struct _LIST_ENTRY *)Heap;
          if ( !Heap )
          {
            Status = -1073741670;
            goto LABEL_30;
          }
          v18 = Heap + 1;
          Heap[1].Length = 0;
          Heap[1].Buffer = &Heap[2].Length;
          Heap[1].MaximumLength = v24;
          RtlCopyUnicodeString(Heap + 1, a1);
          RtlAppendUnicodeToString(v18, L"\\");
          RtlAppendUnicodeStringToString(v18, &DestinationString);
          v19 = v12[14];
          if ( (v19 & 0x10) == 0 )
            break;
          v20 = !wcsicmp((const wchar_t *)v12 + 47, L".") || !wcsicmp((const wchar_t *)v12 + 47, L"..");
          if ( (v7 & 2) != 0 )
          {
            if ( (v7 & 4) != 0 && v20 )
              goto LABEL_23;
            Status = ((__int64 (__fastcall *)(struct _UNICODE_STRING *, struct _UNICODE_STRING *, _QWORD, _QWORD))a3)(
                       v18,
                       &DestinationString,
                       v12[14],
                       0);
          }
          if ( v20 || (v7 & 8) == 0 )
            goto LABEL_23;
          Blink = v11->Blink;
          if ( Blink->Flink != v11 )
            __fastfail(3u);
          v17->Flink = v11;
          v17->Blink = Blink;
          Blink->Flink = v17;
          v11->Blink = v17;
LABEL_24:
          if ( Status < 0 )
            goto LABEL_30;
          v8 = a1;
          *((_WORD *)v12 + ((unsigned __int64)v12[15] >> 1) + 47) = v29;
          if ( !*v12 )
          {
            v9 = 0;
            goto LABEL_3;
          }
          v12 = (unsigned int *)((char *)v12 + *v12);
        }
        if ( (v7 & 1) != 0 )
          Status = ((__int64 (__fastcall *)(struct _UNICODE_STRING *, struct _UNICODE_STRING *, __int64, _QWORD))a3)(
                     v18,
                     &DestinationString,
                     v19,
                     0);
LABEL_23:
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v17);
        goto LABEL_24;
      }
    }
LABEL_30:
    NtClose(FileHandle);
    if ( Status == -2147483642 )
      return 0;
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x140045704  mov     rax, rsp
0x140045707  mov     [rax+20h], r9
0x14004570b  mov     [rax+18h], r8
0x14004570f  mov     [rax+8], rcx
0x140045713  push    rbp
0x140045714  push    rbx
0x140045715  push    rsi
0x140045716  push    rdi
0x140045717  push    r12
0x140045719  push    r13
0x14004571b  push    r14
0x14004571d  push    r15
0x14004571f  lea     rbp, [rax-47h]
0x140045723  sub     rsp, 0C8h
0x14004572a  mov     eax, edx
0x14004572c  mov     [rbp+3Fh+ObjectAttributes.ObjectName], rcx
0x140045730  shl     eax, 11h
0x140045733  lea     r9, [rbp+3Fh+IoStatusBlock]; IoStatusBlock
0x140045737  not     eax
0x140045739  mov     qword ptr [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x140045741  xorps   xmm0, xmm0
0x140045744  mov     qword ptr [rbp+3Fh+ObjectAttributes.Attributes], 40h ; '@'
0x14004574c  and     eax, 200000h
0x140045751  lea     r8, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x140045755  or      eax, 4001h
0x14004575a  mov     r12d, edx
0x14004575d  mov     rsi, rcx
0x140045760  mov     [rsp+100h+OpenOptions], eax; OpenOptions
0x140045764  xor     r13d, r13d
0x140045767  mov     [rsp+100h+ShareAccess], 1; ShareAccess
0x14004576f  xorps   xmm1, xmm1
0x140045772  mov     [rbp+3Fh+FileHandle], r13
0x140045776  mov     edx, 100001h; DesiredAccess
0x14004577b  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], r13
0x14004577f  lea     rcx, [rbp+3Fh+FileHandle]; FileHandle
0x140045783  mov     dil, 1
0x140045786  movups  xmmword ptr [rbp+3Fh+IoStatusBlock], xmm0
0x14004578a  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm1
0x14004578e  movdqu  xmmword ptr [rbp+3Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x140045793  call    cs:__imp_NtOpenFile
0x140045799  mov     ebx, eax
0x14004579b  test    eax, eax
0x14004579d  js      loc_1400459CE
0x1400457a3  mov     r15, [rbp+3Fh+arg_30]
0x1400457a7  mov     rcx, [rbp+3Fh+FileHandle]; FileHandle
0x1400457ab  lea     rax, [rbp+3Fh+IoStatusBlock]
0x1400457af  mov     [rsp+50h], dil; RestartScan
0x1400457b4  xor     r9d, r9d; ApcContext
0x1400457b7  mov     rdi, [rbp+3Fh+FileInformation]
0x1400457bb  xor     r8d, r8d; ApcRoutine
0x1400457be  mov     [rsp+100h+FileName], r13; FileName
0x1400457c3  xor     edx, edx; Event
0x1400457c5  mov     [rsp+100h+ReturnSingleEntry], r13b; ReturnSingleEntry
0x1400457ca  mov     [rsp+100h+FileInformationClass], 3; FileInformationClass
0x1400457d2  mov     [rsp+100h+Length], 3FEh; Length
0x1400457da  mov     qword ptr [rsp+100h+OpenOptions], rdi; FileInformation
0x1400457df  mov     qword ptr [rsp+100h+ShareAccess], rax; IoStatusBlock
0x1400457e4  call    cs:__imp_NtQueryDirectoryFile
0x1400457ea  mov     ebx, eax
0x1400457ec  test    eax, eax
0x1400457ee  js      loc_1400459BA
0x1400457f4  cmp     eax, 103h
0x1400457f9  jnz     short loc_14004581F
0x1400457fb  mov     rcx, [rbp+3Fh+FileHandle]; Handle
0x1400457ff  xor     r8d, r8d; Timeout
0x140045802  xor     edx, edx; Alertable
0x140045804  call    cs:__imp_NtWaitForSingleObject
0x14004580a  mov     ebx, eax
0x14004580c  test    eax, eax
0x14004580e  jnz     loc_1400459BA
0x140045814  mov     ebx, dword ptr [rbp+3Fh+IoStatusBlock]
0x140045817  test    ebx, ebx
0x140045819  js      loc_1400459BA
0x14004581f  mov     ecx, [rdi+3Ch]
0x140045822  lea     r14, [rdi+5Eh]
0x140045826  shr     rcx, 1
0x140045829  mov     rdx, r14; SourceString
0x14004582c  movzx   eax, word ptr [rdi+rcx*2+5Eh]
0x140045831  mov     [rdi+rcx*2+5Eh], r13w
0x140045837  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x14004583b  mov     [rbp+3Fh+arg_8], ax
0x14004583f  call    cs:__imp_RtlInitUnicodeString
0x140045845  movzx   eax, [rbp+3Fh+DestinationString.Length]
0x140045849  mov     edx, 8; Flags
0x14004584e  mov     rcx, gs:60h
0x140045857  add     ax, 2
0x14004585b  add     ax, [rsi]
0x14004585e  movzx   eax, ax
0x140045861  mov     [rbp+3Fh+var_A0], rax
0x140045865  mov     rcx, [rcx+30h]; HeapHandle
0x140045869  lea     r8, [rax+28h]; Size
0x14004586d  call    cs:__imp_RtlAllocateHeap
0x140045873  mov     rsi, rax
0x140045876  test    rax, rax
0x140045879  jz      loc_1400459B5
0x14004587f  mov     rdx, [rbp+3Fh+SourceString]; SourceString
0x140045883  lea     r13, [rax+10h]
0x140045887  mov     rax, [rbp+3Fh+var_A0]
0x14004588b  xor     ecx, ecx
0x14004588d  mov     [r13+0], cx
0x140045892  lea     rcx, [rsi+20h]
0x140045896  mov     [rsi+18h], rcx
0x14004589a  mov     rcx, r13; DestinationString
0x14004589d  mov     [rsi+12h], ax
0x1400458a1  call    cs:__imp_RtlCopyUnicodeString
0x1400458a7  lea     rdx, SubBlock; "\\"
0x1400458ae  mov     rcx, r13; Destination
0x1400458b1  call    cs:__imp_RtlAppendUnicodeToString
0x1400458b7  lea     rdx, [rbp+3Fh+DestinationString]; Source
0x1400458bb  mov     rcx, r13; Destination
0x1400458be  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400458c4  mov     r8d, [rdi+38h]
0x1400458c8  test    r8b, 10h
0x1400458cc  jz      short loc_14004594A
0x1400458ce  lea     rdx, asc_1400A65F4; "."
0x1400458d5  mov     rcx, r14; String1
0x1400458d8  call    _wcsicmp
0x1400458dd  test    eax, eax
0x1400458df  jz      short loc_1400458F9
0x1400458e1  lea     rdx, asc_1400A78C4; ".."
0x1400458e8  mov     rcx, r14; String1
0x1400458eb  call    _wcsicmp
0x1400458f0  test    eax, eax
0x1400458f2  jz      short loc_1400458F9
0x1400458f4  xor     r14b, r14b
0x1400458f7  jmp     short loc_1400458FC
0x1400458f9  mov     r14b, 1
0x1400458fc  test    r12b, 2
0x140045900  jz      short loc_140045926
0x140045902  test    r12b, 4
0x140045906  jz      short loc_14004590D
0x140045908  test    r14b, r14b
0x14004590b  jnz     short loc_140045965
0x14004590d  mov     r8d, [rdi+38h]
0x140045911  lea     rdx, [rbp+3Fh+DestinationString]
0x140045915  mov     rax, [rbp+3Fh+arg_10]
0x140045919  xor     r9d, r9d
0x14004591c  mov     rcx, r13
0x14004591f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045924  mov     ebx, eax
0x140045926  test    r14b, r14b
0x140045929  jnz     short loc_140045965
0x14004592b  test    r12b, 8
0x14004592f  jz      short loc_140045965
0x140045931  mov     rax, [r15+8]
0x140045935  cmp     [rax], r15
0x140045938  jnz     short loc_1400459AE
0x14004593a  mov     [rsi], r15
0x14004593d  mov     [rsi+8], rax
0x140045941  mov     [rax], rsi
0x140045944  mov     [r15+8], rsi
0x140045948  jmp     short loc_14004597D
0x14004594a  test    r12b, 1
0x14004594e  jz      short loc_140045965
0x140045950  mov     rax, [rbp+3Fh+arg_10]
0x140045954  lea     rdx, [rbp+3Fh+DestinationString]
0x140045958  xor     r9d, r9d
0x14004595b  mov     rcx, r13
0x14004595e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045963  mov     ebx, eax
0x140045965  mov     rcx, gs:60h
0x14004596e  mov     r8, rsi; P
0x140045971  xor     edx, edx; Flags
0x140045973  mov     rcx, [rcx+30h]; HeapHandle
0x140045977  call    cs:__imp_RtlFreeHeap
0x14004597d  xor     r13d, r13d
0x140045980  test    ebx, ebx
0x140045982  js      short loc_1400459BA
0x140045984  mov     eax, [rdi+3Ch]
0x140045987  movzx   ecx, [rbp+3Fh+arg_8]
0x14004598b  mov     rsi, [rbp+3Fh+SourceString]
0x14004598f  shr     rax, 1
0x140045992  mov     [rdi+rax*2+5Eh], cx
0x140045997  cmp     [rdi], r13d
0x14004599a  jz      short loc_1400459A6
0x14004599c  mov     eax, [rdi]
0x14004599e  add     rdi, rax
0x1400459a1  jmp     loc_14004581F
0x1400459a6  mov     dil, r13b
0x1400459a9  jmp     loc_1400457A7
0x1400459ae  mov     ecx, 3
0x1400459b3  int     29h; Win8: RtlFailFast(ecx)
0x1400459b5  mov     ebx, 0C000009Ah
0x1400459ba  mov     rcx, [rbp+3Fh+FileHandle]; Handle
0x1400459be  call    cs:__imp_NtClose
0x1400459c4  cmp     ebx, 80000006h
0x1400459ca  cmovz   ebx, r13d
0x1400459ce  mov     eax, ebx
0x1400459d0  add     rsp, 0C8h
0x1400459d7  pop     r15
0x1400459d9  pop     r14
0x1400459db  pop     r13
0x1400459dd  pop     r12
0x1400459df  pop     rdi
0x1400459e0  pop     rsi
0x1400459e1  pop     rbx
0x1400459e2  pop     rbp
0x1400459e3  retn
```
