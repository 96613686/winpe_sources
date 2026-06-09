# UnionFs::Utils::CopyDataStream(_FLT_INSTANCE const &,_FILE_OBJECT const &,_FLT_INSTANCE const &,_FILE_OBJECT const &,__int64,bool,UnionFs::StackEventTracer &)

- ea: `0x14006ae4c`
- end: `0x14006b07c`
- name: `?CopyDataStream@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@01_J_NAEAVStackEventTracer@2@@Z`
- size: `560`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE InitiatingInstance@<rcx>, PFILE_OBJECT FileObject@<rdx>, PFLT_INSTANCE Instance@<r8>, const struct _FLT_INSTANCE *@<r9>, ULONG BytesWritten, ULONG, bool, struct UnionFs::StackEventTracer *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x14006b084`
- `0x14006be68`

## callees

- `0x140056a50`
- `0x140056ac4`
- `0x14006ae4c`
- `0x14007bc00`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x14006afdd`
- `ntoskrnl!KeDelayExecutionThread` at `0x14006afdd`
- `FLTMGR!FltFreePoolAlignedWithTag` at `0x14006b018`
- `FLTMGR!FltFreePoolAlignedWithTag` at `0x14006b018`
- `FLTMGR!FltAllocatePoolAlignedWithTag` at `0x14006aea1`
- `FLTMGR!FltAllocatePoolAlignedWithTag` at `0x14006aea1`
- `FLTMGR!FltWriteFile` at `0x14006afb8`
- `FLTMGR!FltWriteFile` at `0x14006afb8`
- `FLTMGR!FltReadFile` at `0x14006af30`
- `FLTMGR!FltReadFile` at `0x14006af30`

## string_xrefs

- `0x14006aecc`: `UnionFs::Utils::CopyDataStream`
- `0x14006b054`: `UnionFs::Utils::CopyDataStream`
- `0x14006aeb9`: `ORIGIN: Allocating stream copy buffer`
- `0x14006b069`: `API: Reading source stream`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::CopyDataStream(
        PFLT_INSTANCE InitiatingInstance,
        PFILE_OBJECT FileObject,
        PFLT_INSTANCE Instance,
        struct _FILE_OBJECT *a4,
        __int64 BytesWritten,
        ULONG BytesRead,
        int a7)
{
  __int64 v7; // rdi
  ULONG v8; // esi
  struct _FILE_OBJECT *v10; // r12
  char *Buffer; // r14
  NTSTATUS v13; // ebx
  ULONG v14; // r9d
  const char *v16; // rax
  __int64 v17; // r8
  const char *Flags; // [rsp+28h] [rbp-38h]
  const char *Flagsa; // [rsp+28h] [rbp-38h]
  union _LARGE_INTEGER ByteOffset; // [rsp+50h] [rbp-10h] BYREF
  union _LARGE_INTEGER Interval; // [rsp+58h] [rbp-8h] BYREF

  v7 = BytesWritten;
  v8 = 0x1000000;
  v10 = FileObject;
  if ( BytesWritten < 0x1000000 )
    v8 = (BytesWritten + 4095) & 0xFFFFF000;
  Buffer = (char *)FltAllocatePoolAlignedWithTag(Instance, (POOL_TYPE)512, v8, 0x6E674655u);
  if ( Buffer )
  {
    for ( ByteOffset.QuadPart = 0; ; ByteOffset.QuadPart += BytesRead )
    {
      if ( v7 <= 0 )
      {
        v13 = 0;
        goto LABEL_15;
      }
      BytesRead = 0;
      v13 = FltReadFile(InitiatingInstance, v10, &ByteOffset, v8, Buffer, 5u, &BytesRead, 0, 0);
      if ( v13 < 0 )
        break;
      v14 = BytesRead;
      if ( (BytesRead & 0xFFF) != 0 )
      {
        memset(&Buffer[BytesRead], 0, 4096 - (BytesRead & 0xFFF));
        v14 = BytesRead;
      }
      while ( 1 )
      {
        LODWORD(BytesWritten) = 0;
        v13 = FltWriteFile(
                Instance,
                a4,
                &ByteOffset,
                (v14 + 4095) & 0xFFFFF000,
                Buffer,
                0xFu,
                (PULONG)&BytesWritten,
                0,
                0);
        if ( v13 != -1073741740 )
          break;
        Interval.QuadPart = -100000;
        KeDelayExecutionThread(0, 1u, &Interval);
        v14 = BytesRead;
      }
      v10 = FileObject;
      if ( v13 < 0 )
      {
        v16 = "API: Writing target stream";
        v17 = 0x27D00211999LL;
        goto LABEL_18;
      }
      v7 -= BytesRead;
    }
    v16 = "API: Reading source stream";
    v17 = 0x27C0021196FLL;
LABEL_18:
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)v13,
      a7,
      (struct UnionFs::StackEventTracer *)v17,
      (unsigned __int64)"UnionFs::Utils::CopyDataStream",
      v16,
      Flagsa);
LABEL_15:
    FltFreePoolAlignedWithTag(Instance, Buffer, 0x6E674655u);
  }
  else
  {
    v13 = -1073741670;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      a7,
      (struct UnionFs::StackEventTracer *)0x27B00211951LL,
      (unsigned __int64)"UnionFs::Utils::CopyDataStream",
      "ORIGIN: Allocating stream copy buffer",
      Flags);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14006ae4c  mov     [rsp-38h+arg_0], rbx
0x14006ae51  mov     [rsp-38h+FileObject], r9
0x14006ae56  mov     [rsp-38h+arg_8], rdx
0x14006ae5b  push    rbp
0x14006ae5c  push    rsi
0x14006ae5d  push    rdi
0x14006ae5e  push    r12
0x14006ae60  push    r13
0x14006ae62  push    r14
0x14006ae64  push    r15
0x14006ae66  mov     rbp, rsp
0x14006ae69  sub     rsp, 60h
0x14006ae6d  mov     rdi, [rbp+BytesWritten]
0x14006ae71  mov     esi, 1000000h
0x14006ae76  mov     r15, r8
0x14006ae79  mov     r12, rdx
0x14006ae7c  mov     r13, rcx
0x14006ae7f  cmp     rdi, rsi
0x14006ae82  jge     short loc_14006AE90
0x14006ae84  lea     esi, [rdi+0FFFh]
0x14006ae8a  and     esi, 0FFFFF000h
0x14006ae90  mov     r8d, esi; NumberOfBytes
0x14006ae93  mov     edx, 200h; PoolType
0x14006ae98  mov     r9d, 6E674655h; Tag
0x14006ae9e  mov     rcx, r15; Instance
0x14006aea1  call    cs:__imp_FltAllocatePoolAlignedWithTag
0x14006aea8  nop     dword ptr [rax+rax+00h]
0x14006aead  mov     r14, rax
0x14006aeb0  test    rax, rax
0x14006aeb3  jnz     short loc_14006AEE7
0x14006aeb5  mov     rdx, qword ptr [rbp+arg_30]; int
0x14006aeb9  lea     rax, aOriginAllocati_90; "ORIGIN: Allocating stream copy buffer"
0x14006aec0  mov     ebx, 0C000009Ah
0x14006aec5  mov     [rsp+60h+Buffer], rax; char *
0x14006aeca  mov     ecx, ebx; this
0x14006aecc  lea     r9, aUnionfsUtilsCo_4; "UnionFs::Utils::CopyDataStream"
0x14006aed3  mov     r8, 27B00211951h; struct UnionFs::StackEventTracer *
0x14006aedd  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006aee2  jmp     loc_14006B024
0x14006aee7  mov     qword ptr [rbp+ByteOffset], 0
0x14006aeef  jmp     loc_14006B001
0x14006aef4  mov     [rsp+60h+CallbackContext], 0; CallbackContext
0x14006aefd  lea     rax, [rbp+arg_28]
0x14006af01  mov     [rsp+60h+CallbackRoutine], 0; CallbackRoutine
0x14006af0a  lea     r8, [rbp+ByteOffset]; ByteOffset
0x14006af0e  mov     [rsp+60h+BytesRead], rax; BytesRead
0x14006af13  mov     r9d, esi; Length
0x14006af16  mov     dword ptr [rsp+60h+Flags], 5; Flags
0x14006af1e  mov     rdx, r12; FileObject
0x14006af21  mov     rcx, r13; InitiatingInstance
0x14006af24  mov     [rsp+60h+Buffer], r14; Buffer
0x14006af29  mov     [rbp+arg_28], 0
0x14006af30  call    cs:__imp_FltReadFile
0x14006af37  nop     dword ptr [rax+rax+00h]
0x14006af3c  mov     ebx, eax
0x14006af3e  test    eax, eax
0x14006af40  js      loc_14006B069
0x14006af46  mov     r9d, [rbp+arg_28]
0x14006af4a  mov     ecx, r9d
0x14006af4d  and     ecx, 0FFFh
0x14006af53  jz      short loc_14006AF6D
0x14006af55  mov     r8d, 1000h
0x14006af5b  xor     edx, edx; Val
0x14006af5d  sub     r8d, ecx; Size
0x14006af60  lea     rcx, [r14+r9]; void *
0x14006af64  call    memset
0x14006af69  mov     r9d, [rbp+arg_28]
0x14006af6d  mov     r12, [rbp+FileObject]
0x14006af71  mov     [rsp+60h+CallbackContext], 0; CallbackContext
0x14006af7a  lea     rax, [rbp+BytesWritten]
0x14006af7e  mov     [rsp+60h+CallbackRoutine], 0; CallbackRoutine
0x14006af87  lea     r8, [rbp+ByteOffset]; ByteOffset
0x14006af8b  mov     [rsp+60h+BytesRead], rax; BytesWritten
0x14006af90  add     r9d, 0FFFh
0x14006af97  mov     dword ptr [rsp+60h+Flags], 0Fh; char *
0x14006af9f  and     r9d, 0FFFFF000h; Length
0x14006afa6  mov     rdx, r12; FileObject
0x14006afa9  mov     [rsp+60h+Buffer], r14; Buffer
0x14006afae  mov     rcx, r15; InitiatingInstance
0x14006afb1  mov     dword ptr [rbp+BytesWritten], 0
0x14006afb8  call    cs:__imp_FltWriteFile
0x14006afbf  nop     dword ptr [rax+rax+00h]
0x14006afc4  mov     ebx, eax
0x14006afc6  cmp     eax, 0C0000054h
0x14006afcb  jnz     short loc_14006AFEF
0x14006afcd  lea     r8, [rbp+Interval]; Interval
0x14006afd1  mov     qword ptr [rbp+Interval], 0FFFFFFFFFFFE7960h
0x14006afd9  mov     dl, 1; Alertable
0x14006afdb  xor     ecx, ecx; WaitMode
0x14006afdd  call    cs:__imp_KeDelayExecutionThread
0x14006afe4  nop     dword ptr [rax+rax+00h]
0x14006afe9  mov     r9d, [rbp+arg_28]
0x14006afed  jmp     short loc_14006AF71
0x14006afef  mov     r12, [rbp+arg_8]
0x14006aff3  test    ebx, ebx
0x14006aff5  js      short loc_14006B03F
0x14006aff7  mov     eax, [rbp+arg_28]
0x14006affa  sub     rdi, rax
0x14006affd  add     qword ptr [rbp+ByteOffset], rax
0x14006b001  test    rdi, rdi
0x14006b004  jg      loc_14006AEF4
0x14006b00a  xor     ebx, ebx
0x14006b00c  mov     r8d, 6E674655h; Tag
0x14006b012  mov     rdx, r14; Buffer
0x14006b015  mov     rcx, r15; Instance
0x14006b018  call    cs:__imp_FltFreePoolAlignedWithTag
0x14006b01f  nop     dword ptr [rax+rax+00h]
0x14006b024  mov     eax, ebx
0x14006b026  mov     rbx, [rsp+60h+arg_0]
0x14006b02e  add     rsp, 60h
0x14006b032  pop     r15
0x14006b034  pop     r14
0x14006b036  pop     r13
0x14006b038  pop     r12
0x14006b03a  pop     rdi
0x14006b03b  pop     rsi
0x14006b03c  pop     rbp
0x14006b03d  retn
0x14006b03f  lea     rax, aApiWritingTarg; "API: Writing target stream"
0x14006b046  mov     r8, 27D00211999h; struct UnionFs::StackEventTracer *
0x14006b050  mov     rdx, qword ptr [rbp+arg_30]; int
0x14006b054  lea     r9, aUnionfsUtilsCo_4; "UnionFs::Utils::CopyDataStream"
0x14006b05b  mov     ecx, ebx; this
0x14006b05d  mov     [rsp+60h+Buffer], rax; char *
0x14006b062  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006b067  jmp     short loc_14006B00C
0x14006b069  lea     rax, aApiReadingSour; "API: Reading source stream"
0x14006b070  mov     r8, 27C0021196Fh
0x14006b07a  jmp     short loc_14006B050
```
