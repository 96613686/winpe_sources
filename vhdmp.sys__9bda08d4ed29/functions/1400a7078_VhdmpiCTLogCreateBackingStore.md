# VhdmpiCTLogCreateBackingStore

- ea: `0x1400a7078`
- end: `0x1400a764b`
- name: `VhdmpiCTLogCreateBackingStore`
- size: `1491`
- prototype: `__int64 __usercall@<rax>(struct _UNICODE_STRING *@<rcx>, __int64, __int64, __int64, int)`
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140029b04`
- `0x1400a5844`
- `0x1400b36d0`

## callees

- `0x1400152fc`
- `0x140019674`
- `0x140023980`
- `0x14002b280`
- `0x140036284`
- `0x14005dbb0`
- `0x14009d9a4`
- `0x14009e1c0`
- `0x1400a7078`
- `0x1400a7654`
- `0x1400a77e4`
- `0x1400a7958`

## import_xrefs

- `ntoskrnl!ZwCreateFile` at `0x1400a7283`
- `ntoskrnl!ZwCreateFile` at `0x1400a72c7`
- `ntoskrnl!ZwCreateFile` at `0x1400a7283`
- `ntoskrnl!ZwCreateFile` at `0x1400a72c7`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400a73b4`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400a73b4`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400a730d`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400a730d`
- `ntoskrnl!ObfDereferenceObject` at `0x1400a750a`
- `ntoskrnl!ObfDereferenceObject` at `0x1400a750a`
- `ntoskrnl!ZwClose` at `0x1400a7520`
- `ntoskrnl!ZwClose` at `0x1400a7520`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a75ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a75ca`
- `ntoskrnl!ExAllocatePool2` at `0x1400a7187`
- `ntoskrnl!ExAllocatePool2` at `0x1400a7187`
- `ntoskrnl!KeInitializeEvent` at `0x1400a7408`
- `ntoskrnl!KeInitializeEvent` at `0x1400a7420`
- `ntoskrnl!KeInitializeEvent` at `0x1400a7408`
- `ntoskrnl!KeInitializeEvent` at `0x1400a7420`

## string_xrefs

- `0x1400a711b`: `VhdmpiCTLogCreateBackingStore: Entering ... `
- `0x1400a7356`: `Successfully opened file handle for file %S.`
- `0x1400a7130`: `VhdmpiCTLogCreateBackingStore`
- `0x1400a7364`: `VhdmpiCTLogCreateBackingStore`
- `0x1400a74d8`: `VhdmpiCTLogCreateBackingStore`
- `0x1400a7590`: `VhdmpiCTLogCreateBackingStore`
- `0x1400a7615`: `VhdmpiCTLogCreateBackingStore`
- `0x1400a7583`: `VhdmpiCTLogCreateBackingStore: Failed for file %S. Status=0x%08x`
- `0x1400a74c4`: `VhdmpiCTLogCreateBackingStore: BackingStore Successfully created %p.`
- `0x1400a75fa`: `VhdmpiCTLogCreateBackingStore: leaving... (0x%08x)`

## pseudocode

```c
__int64 __fastcall VhdmpiCTLogCreateBackingStore(
        struct _UNICODE_STRING *a1,
        char a2,
        __int64 a3,
        __int64 a4,
        _OWORD *a5,
        char *a6,
        const void **a7,
        unsigned int a8)
{
  unsigned int v10; // edx
  char v11; // r14
  PVOID v12; // r12
  __int64 Pool2; // rdi
  int NtFilePath; // ebx
  const void **v15; // r8
  ULONG CreateOptions; // ebx
  NTSTATUS v17; // eax
  wchar_t *v18; // rsi
  unsigned int v19; // edx
  void *v20; // rax
  unsigned int v21; // edx
  int v22; // ecx
  unsigned int v23; // edx
  const wchar_t *v24; // rax
  unsigned int v25; // r9d
  void *FileHandle; // [rsp+68h] [rbp-98h] BYREF
  PVOID P; // [rsp+70h] [rbp-90h] BYREF
  PVOID Object; // [rsp+78h] [rbp-88h] BYREF
  __int64 v30; // [rsp+80h] [rbp-80h]
  __int64 v31; // [rsp+88h] [rbp-78h]
  const void **v32; // [rsp+90h] [rbp-70h]
  char *v33; // [rsp+98h] [rbp-68h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A0h] [rbp-60h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE EaBuffer[56]; // [rsp+E0h] [rbp-20h] BYREF

  v33 = a6;
  v30 = a4;
  v31 = a3;
  v32 = a7;
  FileHandle = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  memset(EaBuffer, 0, sizeof(EaBuffer));
  if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 4096) )
    TraceEvents("VhdmpiCTLogCreateBackingStore", 0xB9u, 4u, v10, "VhdmpiCTLogCreateBackingStore: Entering ... ");
  FileHandle = 0;
  v11 = 1;
  P = 0;
  *a7 = 0;
  IoStatusBlock = 0;
  v12 = 0;
  Pool2 = 0;
  NtFilePath = VhdmpiDuplicateUnicodeStringToString(a1, &P);
  if ( NtFilePath < 0 )
    goto LABEL_29;
  Pool2 = ExAllocatePool2(72, 4480, 1749305430);
  if ( !Pool2 )
  {
    NtFilePath = -1073741670;
LABEL_29:
    v18 = (wchar_t *)P;
    goto LABEL_30;
  }
  NtFilePath = VhdmpiDuplicateFilePath(0);
  if ( NtFilePath < 0 )
    goto LABEL_29;
  NtFilePath = VhdmpiCreateNtFilePath(a1, (struct _UNICODE_STRING *)(Pool2 + 16));
  if ( NtFilePath < 0 )
    goto LABEL_29;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)(Pool2 + 16);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 1600;
  CreateOptions = ((dword_14008E3A0 - 1) & 0xFFFFFFFD) != 0 ? 66 : 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( !a5
    || (strcpy(&EaBuffer[8], "ClusteredApplicationInstance"),
        *(_QWORD *)EaBuffer = 0x101C0000000000LL,
        *(_OWORD *)&EaBuffer[37] = *a5,
        ZwCreateFile(
          &FileHandle,
          0xC0000000,
          &ObjectAttributes,
          &IoStatusBlock,
          0,
          0x80u,
          1u,
          1u,
          ((dword_14008E3A0 - 1) & 0xFFFFFFFD) != 0 ? 66 : 64,
          EaBuffer,
          0x38u) < 0) )
  {
    v17 = ZwCreateFile(
            &FileHandle,
            0xC0000000,
            &ObjectAttributes,
            &IoStatusBlock,
            0,
            0x80u,
            1u,
            1u,
            CreateOptions,
            0,
            0);
    NtFilePath = v17;
    if ( v17 < 0 )
      goto LABEL_12;
  }
  Object = 0;
  v17 = ObReferenceObjectByHandle(FileHandle, 0xC0000000, 0, 0, &Object, 0);
  v12 = Object;
  NtFilePath = v17;
  if ( v17 < 0 )
  {
LABEL_12:
    if ( v17 != -1073741772 )
      v11 = 0;
    goto LABEL_29;
  }
  v18 = (wchar_t *)P;
  if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 4096) )
    TraceEvents("VhdmpiCTLogCreateBackingStore", 0x163u, 4u, v19, "Successfully opened file handle for file %S.", v18);
  v20 = FileHandle;
  *(_QWORD *)(Pool2 + 48) = v12;
  *(_QWORD *)(Pool2 + 40) = v20;
  v12 = 0;
  FileHandle = 0;
  ExInitializeNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(Pool2 + 4224), 0, 0, 0x200u, 0x40u, 0x68444856u, 0);
  *(_DWORD *)(Pool2 + 4392) = 0;
  *(_BYTE *)(Pool2 + 4352) = 1;
  *(_DWORD *)(Pool2 + 80) = 0;
  *(_DWORD *)(Pool2 + 4356) = 0;
  *(_BYTE *)(Pool2 + 4424) = 0;
  *(_DWORD *)(Pool2 + 4428) = 0;
  *(_QWORD *)(Pool2 + 4384) = 0;
  *(_BYTE *)(Pool2 + 4432) = 0;
  *(_BYTE *)(Pool2 + 4440) = 0;
  KeInitializeEvent((PRKEVENT)(Pool2 + 4360), NotificationEvent, 1u);
  KeInitializeEvent((PRKEVENT)(Pool2 + 4400), NotificationEvent, 1u);
  if ( a2 || (NtFilePath = VhdmpiCTLogInitializeBackingStore(Pool2, v31, v30, a8), NtFilePath >= 0) )
  {
    NtFilePath = VhdmpiCTLogVerifyAndLoadBackingStore((struct _CTLOG_BACKING_STORE *)Pool2);
    if ( NtFilePath >= 0 )
    {
      if ( a2 )
      {
        NtFilePath = VhdmpiClearEOLLocationInHeader(Pool2);
        if ( NtFilePath < 0 )
        {
          v11 = 0;
          goto LABEL_30;
        }
      }
      v15 = v32;
      *(_QWORD *)(Pool2 + 32) = v18;
      v18 = 0;
      *v15 = (const void *)Pool2;
      Pool2 = 0;
      if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 4096) )
        TraceEvents(
          "VhdmpiCTLogCreateBackingStore",
          0x1B7u,
          4u,
          v21,
          "VhdmpiCTLogCreateBackingStore: BackingStore Successfully created %p.",
          *v15);
      NtFilePath = 0;
    }
    v11 = 1;
  }
LABEL_30:
  if ( v33 )
    *v33 = v11;
  if ( v12 )
    ObfDereferenceObject(v12);
  v22 = (int)FileHandle;
  if ( FileHandle )
  {
    ZwClose(FileHandle);
    FileHandle = 0;
  }
  if ( Pool2 )
    VhdmpiCTLogDeleteBackingStore(Pool2);
  if ( NtFilePath < 0 )
  {
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 4096) )
    {
      v24 = (const wchar_t *)&dword_1400613A4;
      if ( v18 )
        v24 = v18;
      TraceEvents(
        "VhdmpiCTLogCreateBackingStore",
        0x1DDu,
        2u,
        v23,
        "VhdmpiCTLogCreateBackingStore: Failed for file %S. Status=0x%08x",
        v24,
        NtFilePath);
    }
    if ( (Microsoft_Windows_VHDMPEnableBits & 4) != 0 )
      McTemplateK0zq_EtwWriteTransfer(v22, (unsigned int)CTLogFileOpenError, (_DWORD)v15, (_DWORD)v18, NtFilePath);
  }
  if ( v18 )
    ExFreePoolWithTag(v18, 0x7A444856u);
  if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 4096) )
    TraceEvents(
      "VhdmpiCTLogCreateBackingStore",
      0x1EDu,
      4u,
      v25,
      "VhdmpiCTLogCreateBackingStore: leaving... (0x%08x)",
      NtFilePath);
  return (unsigned int)NtFilePath;
}

```

## disassembly

```asm
0x1400a7078  mov     [rsp-8+arg_8], rbx
0x1400a707d  push    rbp
0x1400a707e  push    rsi
0x1400a707f  push    rdi
0x1400a7080  push    r12
0x1400a7082  push    r13
0x1400a7084  push    r14
0x1400a7086  push    r15
0x1400a7088  lea     rbp, [rsp-20h]
0x1400a708d  sub     rsp, 120h
0x1400a7094  mov     rax, cs:__security_cookie
0x1400a709b  xor     rax, rsp
0x1400a709e  mov     [rbp+50h+var_38], rax
0x1400a70a2  mov     rax, [rbp+50h+arg_28]
0x1400a70a9  xorps   xmm0, xmm0
0x1400a70ac  mov     rbx, [rbp+50h+arg_30]
0x1400a70b3  xorps   xmm1, xmm1
0x1400a70b6  mov     [rbp+50h+var_B8], rax
0x1400a70ba  xor     r15d, r15d
0x1400a70bd  xor     eax, eax
0x1400a70bf  mov     [rbp+50h+var_D0], r9
0x1400a70c3  mov     [rbp+50h+var_40], rax
0x1400a70c7  mov     r13b, dl
0x1400a70ca  mov     eax, cs:dword_1400876D0
0x1400a70d0  mov     rsi, rcx
0x1400a70d3  mov     [rbp+50h+var_C8], r8
0x1400a70d7  mov     edx, 1000h
0x1400a70dc  mov     [rbp+50h+var_C0], rbx
0x1400a70e0  mov     [rsp+150h+FileHandle], r15
0x1400a70e5  movups  xmmword ptr [rbp+50h+IoStatusBlock], xmm0
0x1400a70e9  movups  xmmword ptr [rbp+50h+ObjectAttributes.Length], xmm0
0x1400a70ed  movups  xmmword ptr [rbp+50h+ObjectAttributes.ObjectName], xmm0
0x1400a70f1  movups  xmmword ptr [rbp+50h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400a70f5  movups  xmmword ptr [rbp+50h+var_70], xmm1
0x1400a70f9  movups  xmmword ptr [rbp+50h+var_70+10h], xmm1
0x1400a70fd  movups  [rbp+50h+var_50], xmm1
0x1400a7101  cmp     eax, 4
0x1400a7104  jbe     short loc_1400A713C
0x1400a7106  lea     rcx, dword_1400876D0
0x1400a710d  call    _tlgKeywordOn
0x1400a7112  test    al, al
0x1400a7114  jz      short loc_1400A713C
0x1400a7116  mov     ecx, 0B9h
0x1400a711b  lea     rax, aVhdmpictlogcre_0; "VhdmpiCTLogCreateBackingStore: Entering"...
0x1400a7122  mov     r9d, edx; int
0x1400a7125  mov     [rsp+150h+AllocationSize], rax; char *
0x1400a712a  mov     edx, ecx; int
0x1400a712c  lea     r8d, [r15+4]; int
0x1400a7130  lea     rcx, aVhdmpictlogcre_3; "VhdmpiCTLogCreateBackingStore"
0x1400a7137  call    TraceEvents
0x1400a713c  xorps   xmm0, xmm0
0x1400a713f  mov     [rsp+150h+FileHandle], r15
0x1400a7144  mov     r14d, 1
0x1400a714a  mov     [rsp+150h+P], r15
0x1400a714f  lea     rdx, [rsp+150h+P]
0x1400a7154  mov     [rsp+150h+var_F0], r14b
0x1400a7159  mov     rcx, rsi
0x1400a715c  mov     [rbx], r15
0x1400a715f  movups  xmmword ptr [rbp+50h+IoStatusBlock], xmm0
0x1400a7163  mov     r12, r15
0x1400a7166  mov     rdi, r15
0x1400a7169  call    VhdmpiDuplicateUnicodeStringToString
0x1400a716e  mov     ebx, eax
0x1400a7170  test    eax, eax
0x1400a7172  js      loc_1400A74F1
0x1400a7178  mov     edx, 1180h
0x1400a717d  lea     ecx, [r14+47h]
0x1400a7181  mov     r8d, 68444856h
0x1400a7187  call    cs:__imp_ExAllocatePool2
0x1400a718e  nop     dword ptr [rax+rax+00h]
0x1400a7193  mov     rdi, rax
0x1400a7196  test    rax, rax
0x1400a7199  jnz     short loc_1400A71A5
0x1400a719b  mov     ebx, 0C000009Ah
0x1400a71a0  jmp     loc_1400A74F1
0x1400a71a5  xor     r8d, r8d
0x1400a71a8  mov     r9, rdi
0x1400a71ab  mov     rdx, rsi
0x1400a71ae  xor     ecx, ecx; Source
0x1400a71b0  call    VhdmpiDuplicateFilePath
0x1400a71b5  mov     ebx, eax
0x1400a71b7  test    eax, eax
0x1400a71b9  js      loc_1400A74F1
0x1400a71bf  lea     r15, [rdi+10h]
0x1400a71c3  mov     rcx, rsi; struct _UNICODE_STRING *
0x1400a71c6  mov     rdx, r15; struct _UNICODE_STRING *
0x1400a71c9  call    VhdmpiCreateNtFilePath
0x1400a71ce  mov     ebx, eax
0x1400a71d0  test    eax, eax
0x1400a71d2  js      loc_1400A74EE
0x1400a71d8  mov     eax, cs:dword_14008E3A0
0x1400a71de  xorps   xmm0, xmm0
0x1400a71e1  dec     eax
0x1400a71e3  mov     [rbp+50h+ObjectAttributes.ObjectName], r15
0x1400a71e7  and     eax, 0FFFFFFFDh
0x1400a71ea  mov     [rbp+50h+ObjectAttributes.Length], 30h ; '0'
0x1400a71f1  neg     eax
0x1400a71f3  mov     [rbp+50h+ObjectAttributes.RootDirectory], r12
0x1400a71f7  mov     rax, [rbp+50h+arg_20]
0x1400a71fe  mov     esi, 0C0000000h
0x1400a7203  sbb     ebx, ebx
0x1400a7205  mov     [rbp+50h+ObjectAttributes.Attributes], 640h
0x1400a720c  and     ebx, 2
0x1400a720f  xor     r15d, r15d
0x1400a7212  add     ebx, 40h ; '@'
0x1400a7215  movdqu  xmmword ptr [rbp+50h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400a721a  test    rax, rax
0x1400a721d  jz      short loc_1400A7293
0x1400a721f  movups  xmm0, xmmword ptr cs:aClusteredappli; "ClusteredApplicationInstance"
0x1400a7226  mov     [rsp+150h+EaLength], 38h ; '8'; EaLength
0x1400a722e  lea     r9, [rbp+50h+IoStatusBlock]; IoStatusBlock
0x1400a7232  movups  xmm1, xmmword ptr cs:aClusteredappli+0Dh; "icationInstance"
0x1400a7239  lea     r8, [rbp+50h+ObjectAttributes]; ObjectAttributes
0x1400a723d  mov     edx, esi; DesiredAccess
0x1400a723f  movups  xmmword ptr [rbp+50h+var_70+8], xmm0
0x1400a7243  lea     rcx, [rsp+150h+FileHandle]; FileHandle
0x1400a7248  mov     dword ptr [rbp+50h+var_70], r15d
0x1400a724c  movups  xmm0, xmmword ptr [rax]
0x1400a724f  lea     rax, [rbp+50h+var_70]
0x1400a7253  mov     dword ptr [rbp+50h+var_70+4], 101C00h
0x1400a725a  mov     [rsp+150h+EaBuffer], rax; EaBuffer
0x1400a725f  mov     [rsp+150h+CreateOptions], ebx; CreateOptions
0x1400a7263  mov     [rsp+150h+CreateDisposition], r14d; CreateDisposition
0x1400a7268  mov     [rsp+150h+ShareAccess], r14d; ShareAccess
0x1400a726d  mov     [rsp+150h+FileAttributes], 80h; FileAttributes
0x1400a7275  mov     [rsp+150h+AllocationSize], r15; AllocationSize
0x1400a727a  movups  xmmword ptr [rbp+50h+var_70+15h], xmm1
0x1400a727e  movdqu  [rbp+50h+var_50+5], xmm0
0x1400a7283  call    cs:__imp_ZwCreateFile
0x1400a728a  nop     dword ptr [rax+rax+00h]
0x1400a728f  test    eax, eax
0x1400a7291  jns     short loc_1400A72EC
0x1400a7293  mov     [rsp+150h+EaLength], r15d; EaLength
0x1400a7298  lea     r9, [rbp+50h+IoStatusBlock]; IoStatusBlock
0x1400a729c  mov     [rsp+150h+EaBuffer], r15; EaBuffer
0x1400a72a1  lea     r8, [rbp+50h+ObjectAttributes]; ObjectAttributes
0x1400a72a5  mov     [rsp+150h+CreateOptions], ebx; CreateOptions
0x1400a72a9  lea     rcx, [rsp+150h+FileHandle]; FileHandle
0x1400a72ae  mov     [rsp+150h+CreateDisposition], r14d; CreateDisposition
0x1400a72b3  mov     edx, esi; DesiredAccess
0x1400a72b5  mov     [rsp+150h+ShareAccess], r14d; ShareAccess
0x1400a72ba  mov     [rsp+150h+FileAttributes], 80h; FileAttributes
0x1400a72c2  mov     [rsp+150h+AllocationSize], r15; AllocationSize
0x1400a72c7  call    cs:__imp_ZwCreateFile
0x1400a72ce  nop     dword ptr [rax+rax+00h]
0x1400a72d3  mov     ebx, eax
0x1400a72d5  test    eax, eax
0x1400a72d7  jns     short loc_1400A72EC
0x1400a72d9  cmp     eax, 0C0000034h
0x1400a72de  jz      loc_1400A74F1
0x1400a72e4  mov     r14b, r15b
0x1400a72e7  jmp     loc_1400A74F1
0x1400a72ec  mov     rcx, [rsp+150h+FileHandle]; Handle
0x1400a72f1  lea     rax, [rsp+150h+Object]
0x1400a72f6  mov     qword ptr [rsp+150h+FileAttributes], r15; HandleInformation
0x1400a72fb  xor     r9d, r9d; AccessMode
0x1400a72fe  xor     r8d, r8d; ObjectType
0x1400a7301  mov     [rsp+150h+AllocationSize], rax; Object
0x1400a7306  mov     edx, esi; DesiredAccess
0x1400a7308  mov     [rsp+150h+Object], r15
0x1400a730d  call    cs:__imp_ObReferenceObjectByHandle
0x1400a7314  nop     dword ptr [rax+rax+00h]
0x1400a7319  mov     r12, [rsp+150h+Object]
0x1400a731e  mov     ebx, eax
0x1400a7320  test    eax, eax
0x1400a7322  js      short loc_1400A72D9
0x1400a7324  mov     eax, cs:dword_1400876D0
0x1400a732a  mov     rsi, [rsp+150h+P]
0x1400a732f  cmp     eax, 4
0x1400a7332  jbe     short loc_1400A7376
0x1400a7334  mov     edx, 1000h
0x1400a7339  lea     rcx, dword_1400876D0
0x1400a7340  call    _tlgKeywordOn
0x1400a7345  test    al, al
0x1400a7347  jz      short loc_1400A7376
0x1400a7349  mov     ecx, 163h
0x1400a734e  mov     qword ptr [rsp+150h+FileAttributes], rsi; char
0x1400a7353  mov     r9d, edx; int
0x1400a7356  lea     rax, aSuccessfullyOp; "Successfully opened file handle for fil"...
0x1400a735d  mov     edx, ecx; int
0x1400a735f  mov     [rsp+150h+AllocationSize], rax; char *
0x1400a7364  lea     rcx, aVhdmpictlogcre_3; "VhdmpiCTLogCreateBackingStore"
0x1400a736b  mov     r8d, 4; int
0x1400a7371  call    TraceEvents
0x1400a7376  mov     rax, [rsp+150h+FileHandle]
0x1400a737b  lea     rcx, [rdi+1080h]; Lookaside
0x1400a7382  mov     word ptr [rsp+150h+ShareAccess], r15w; Depth
0x1400a7388  mov     r9d, 200h; Flags
0x1400a738e  mov     [rdi+30h], r12
0x1400a7392  xor     r8d, r8d; Free
0x1400a7395  mov     [rsp+150h+FileAttributes], 68444856h; Tag
0x1400a739d  xor     edx, edx; Allocate
0x1400a739f  mov     [rdi+28h], rax
0x1400a73a3  mov     r12, r15
0x1400a73a6  mov     [rsp+150h+AllocationSize], 40h ; '@'; Size
0x1400a73af  mov     [rsp+150h+FileHandle], r15
0x1400a73b4  call    cs:__imp_ExInitializeNPagedLookasideList
0x1400a73bb  nop     dword ptr [rax+rax+00h]
0x1400a73c0  mov     [rdi+1128h], r15d
0x1400a73c7  lea     rcx, [rdi+1108h]; Event
0x1400a73ce  mov     r8b, r14b; State
0x1400a73d1  mov     [rdi+1100h], r14b
0x1400a73d8  xor     edx, edx; Type
0x1400a73da  mov     [rdi+50h], r15d
0x1400a73de  mov     [rdi+1104h], r15d
0x1400a73e5  mov     [rdi+1148h], r15b
0x1400a73ec  mov     [rdi+114Ch], r15d
0x1400a73f3  mov     [rdi+1120h], r15
0x1400a73fa  mov     [rdi+1150h], r15b
0x1400a7401  mov     [rdi+1158h], r15b
0x1400a7408  call    cs:__imp_KeInitializeEvent
0x1400a740f  nop     dword ptr [rax+rax+00h]
0x1400a7414  lea     rcx, [rdi+1130h]; Event
0x1400a741b  mov     r8b, r14b; State
0x1400a741e  xor     edx, edx; Type
0x1400a7420  call    cs:__imp_KeInitializeEvent
0x1400a7427  nop     dword ptr [rax+rax+00h]
0x1400a742c  test    r13b, r13b
0x1400a742f  jnz     short loc_1400A7455
0x1400a7431  mov     r9d, [rbp+50h+arg_38]
0x1400a7438  mov     rcx, rdi
0x1400a743b  mov     r8, [rbp+50h+var_D0]
0x1400a743f  mov     rdx, [rbp+50h+var_C8]
0x1400a7443  call    VhdmpiCTLogInitializeBackingStore
0x1400a7448  mov     ebx, eax
0x1400a744a  test    eax, eax
0x1400a744c  js      loc_1400A74F6
0x1400a7452  test    r13b, r13b
0x1400a7455  setz    dl
0x1400a7458  lea     r8, [rsp+150h+var_F0]
0x1400a745d  mov     rcx, rdi; struct _CTLOG_BACKING_STORE *
0x1400a7460  call    VhdmpiCTLogVerifyAndLoadBackingStore
0x1400a7465  mov     ebx, eax
0x1400a7467  test    eax, eax
0x1400a7469  js      short loc_1400A74E7
0x1400a746b  test    r13b, r13b
0x1400a746e  jz      short loc_1400A7483
0x1400a7470  mov     rcx, rdi
0x1400a7473  call    VhdmpiClearEOLLocationInHeader
0x1400a7478  mov     ebx, eax
0x1400a747a  test    eax, eax
0x1400a747c  jns     short loc_1400A7483
0x1400a747e  mov     r14b, r15b
0x1400a7481  jmp     short loc_1400A74F6
0x1400a7483  mov     r8, [rbp+50h+var_C0]
0x1400a7487  mov     [rdi+20h], rsi
0x1400a748b  mov     rsi, r15
0x1400a748e  mov     [r8], rdi
0x1400a7491  mov     rdi, r15
0x1400a7494  mov     eax, cs:dword_1400876D0
0x1400a749a  cmp     eax, 4
0x1400a749d  jbe     short loc_1400A74E4
0x1400a749f  mov     edx, 1000h
0x1400a74a4  lea     rcx, dword_1400876D0
0x1400a74ab  call    _tlgKeywordOn
0x1400a74b0  test    al, al
0x1400a74b2  jz      short loc_1400A74E4
0x1400a74b4  mov     rax, [r8]
0x1400a74b7  mov     ecx, 1B7h
0x1400a74bc  mov     qword ptr [rsp+150h+FileAttributes], rax; char
0x1400a74c1  mov     r9d, edx; int
0x1400a74c4  lea     rax, aVhdmpictlogcre_1; "VhdmpiCTLogCreateBackingStore: BackingS"...
0x1400a74cb  mov     edx, ecx; int
0x1400a74cd  mov     r8d, 4; int
0x1400a74d3  mov     [rsp+150h+AllocationSize], rax; char *
0x1400a74d8  lea     rcx, aVhdmpictlogcre_3; "VhdmpiCTLogCreateBackingStore"
0x1400a74df  call    TraceEvents
0x1400a74e4  mov     ebx, r15d
0x1400a74e7  mov     r14b, [rsp+150h+var_F0]
0x1400a74ec  jmp     short loc_1400A74F6
0x1400a74ee  xor     r15d, r15d
0x1400a74f1  mov     rsi, [rsp+150h+P]
0x1400a74f6  mov     rax, [rbp+50h+var_B8]
0x1400a74fa  test    rax, rax
0x1400a74fd  jz      short loc_1400A7502
0x1400a74ff  mov     [rax], r14b
0x1400a7502  test    r12, r12
0x1400a7505  jz      short loc_1400A7516
0x1400a7507  mov     rcx, r12; Object
0x1400a750a  call    cs:__imp_ObfDereferenceObject
0x1400a7511  nop     dword ptr [rax+rax+00h]
0x1400a7516  mov     rcx, [rsp+150h+FileHandle]; Handle
0x1400a751b  test    rcx, rcx
0x1400a751e  jz      short loc_1400A7531
0x1400a7520  call    cs:__imp_ZwClose
0x1400a7527  nop     dword ptr [rax+rax+00h]
0x1400a752c  mov     [rsp+150h+FileHandle], r15
0x1400a7531  test    rdi, rdi
0x1400a7534  jz      short loc_1400A753E
0x1400a7536  mov     rcx, rdi; char
0x1400a7539  call    VhdmpiCTLogDeleteBackingStore
0x1400a753e  test    ebx, ebx
0x1400a7540  jns     short loc_1400A75BD
0x1400a7542  mov     eax, cs:dword_1400876D0
0x1400a7548  cmp     eax, 2
0x1400a754b  jbe     short loc_1400A75A1
0x1400a754d  mov     edx, 1000h
0x1400a7552  lea     rcx, dword_1400876D0
0x1400a7559  call    _tlgKeywordOn
0x1400a755e  test    al, al
  ... truncated ...
```
