# VhdmpiOpenBackingFile(_VHD_FILE_WRAPPER *,ulong,ulong,uchar,uchar,void * *,_FILE_OBJECT * *,uchar *)

- ea: `0x1400ac4f8`
- end: `0x1400acbb6`
- name: `?VhdmpiOpenBackingFile@@YAJPEAU_VHD_FILE_WRAPPER@@KKEEPEAPEAXPEAPEAU_FILE_OBJECT@@PEAE@Z`
- size: `1726`
- prototype: `__int64 __fastcall(struct _VHD_FILE_WRAPPER *, ACCESS_MASK, __int64, __int64, char, void **, struct _FILE_OBJECT **, unsigned __int8 *)`
- caller_count: `6`
- callee_count: `10`
- tags: ``

## callers

- `0x1400abcbc`
- `0x1400ad158`
- `0x1400ad284`
- `0x1400ad410`
- `0x1400ae6a0`
- `0x1400ec0d8`

## callees

- `0x140019070`
- `0x1400201d0`
- `0x140022eac`
- `0x140023560`
- `0x140035e94`
- `0x1400aafe8`
- `0x1400ac4f8`
- `0x1400acbbc`
- `0x1400ad6d4`
- `0x1400ad718`

## import_xrefs

- `ntoskrnl!ZwFsControlFile` at `0x1400ac76c`
- `ntoskrnl!ZwFsControlFile` at `0x1400aca54`
- `ntoskrnl!ZwFsControlFile` at `0x1400acb3c`
- `ntoskrnl!ZwFsControlFile` at `0x1400ac76c`
- `ntoskrnl!ZwFsControlFile` at `0x1400aca54`
- `ntoskrnl!ZwFsControlFile` at `0x1400acb3c`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400ac62e`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400ac62e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400ac5f9`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400ac5f9`
- `ntoskrnl!ObfDereferenceObject` at `0x1400ac6ce`
- `ntoskrnl!ObfDereferenceObject` at `0x1400ac6ce`
- `ntoskrnl!ZwClose` at `0x1400ac5cc`
- `ntoskrnl!ZwClose` at `0x1400ac6e2`
- `ntoskrnl!ZwClose` at `0x1400ac5cc`
- `ntoskrnl!ZwClose` at `0x1400ac6e2`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400ac799`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400ac799`

## string_xrefs

- `0x1400ac673`: `VhdmpiOpenBackingFile`
- `0x1400ac712`: `VhdmpiOpenBackingFile`
- `0x1400acb6e`: ` (file '%wZ')Failed to mark file handle for SKIP_COHERENCY_SYNC_DISALLOW_WRITES: 0x%08x`
- `0x1400aca84`: ` (file '%wZ')Failed to mark file handle with MARK_HANDLE_ENABLE_CPU_CACHE: 0x%08x`

## pseudocode

```c
__int64 __fastcall VhdmpiOpenBackingFile(
        struct _VHD_FILE_WRAPPER *a1,
        ACCESS_MASK a2,
        __int64 a3,
        __int64 a4,
        char a5,
        void **a6,
        struct _FILE_OBJECT **a7,
        unsigned __int8 *a8)
{
  struct _FILE_OBJECT *v8; // r13
  bool v9; // zf
  __int64 v11; // rdx
  int v13; // edx
  ULONG v14; // r10d
  char v15; // r9
  ULONG v16; // ecx
  int v17; // r9d
  int v18; // eax
  __int64 v19; // r8
  HANDLE v20; // r14
  NTSTATUS Status; // ebx
  NTSTATUS v22; // eax
  __int64 v23; // rdx
  PDEVICE_OBJECT RelatedDeviceObject; // r9
  char v26; // al
  unsigned int v27; // edx
  int v28; // eax
  int v29; // ecx
  HANDLE Handle; // [rsp+50h] [rbp-41h] BYREF
  __int64 InputBuffer; // [rsp+58h] [rbp-39h] BYREF
  PVOID Object; // [rsp+60h] [rbp-31h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp-29h] BYREF
  __int128 v34; // [rsp+78h] [rbp-19h] BYREF
  __int64 v35; // [rsp+88h] [rbp-9h]
  int v36; // [rsp+E0h] [rbp+4Fh]
  char v37; // [rsp+F0h] [rbp+5Fh]
  unsigned __int8 v38; // [rsp+F8h] [rbp+67h]

  v37 = a3;
  Object = 0;
  v35 = 0;
  Handle = 0;
  v8 = 0;
  InputBuffer = 0;
  v9 = (a2 & 0x40000000) == 0;
  v36 = a2 & 0x40000000;
  v11 = *((unsigned int *)a1 + 35);
  LOBYTE(a3) = !v9;
  IoStatusBlock = 0;
  v34 = 0;
  v13 = (unsigned __int8)VhdmpiChangeCacheMode(a1, v11, a3) != 0 ? 0 : 8;
  v16 = v15 != 0;
  v17 = v13 | 2;
  if ( *((_DWORD *)a1 + 35) != 3 )
    v17 = v13;
  v18 = VhdmpiOpenBackingFileWithOptions(a1, a2, v14, v17, v16, &Handle);
  v20 = Handle;
  Status = v18;
  if ( v18 < 0 )
    goto LABEL_15;
  if ( (*((_DWORD *)a1 + 34) & 4) != 0 )
  {
    Status = VhdmpiTranslateLoopbackFileHandle(Handle, &Object);
    if ( Status < 0 )
      goto LABEL_15;
    ZwClose(v20);
    v20 = Object;
  }
  Object = 0;
  v22 = ObReferenceObjectByHandle(v20, a2, 0, 0, &Object, 0);
  v8 = (struct _FILE_OBJECT *)Object;
  Status = v22;
  if ( v22 >= 0 )
  {
    if ( a5 )
    {
      if ( *((_QWORD *)a1 + 67) )
      {
        RelatedDeviceObject = IoGetRelatedDeviceObject((PFILE_OBJECT)Object);
        if ( RelatedDeviceObject != *((PDEVICE_OBJECT *)a1 + 67) )
        {
          if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2048) )
            TraceEvents(
              (int)"VhdmpiOpenBackingFile",
              3472,
              2,
              2048,
              " (file '%wZ')Device object changed: %p vs %p",
              (char)a1);
          Status = -1072103391;
          goto LABEL_15;
        }
      }
    }
    if ( (*((_DWORD *)a1 + 34) & 8) != 0 )
    {
      InputBuffer = 30000;
      Status = ZwFsControlFile(v20, 0, 0, 0, &IoStatusBlock, 0x1401D4u, &InputBuffer, 8u, 0, 0);
      if ( Status == 259 )
      {
        KeWaitForSingleObject(&v8->Event, Executive, 0, 0, 0);
        Status = IoStatusBlock.Status;
      }
      if ( Status != -1073741637 && Status != -1073741808 )
      {
        if ( Status >= 0 )
          goto LABEL_26;
LABEL_40:
        if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2048) )
          TraceEvents(
            (int)"VhdmpiOpenBackingFile",
            3543,
            2,
            2048,
            " (file '%wZ')Failed to enable resiliency: 0x%08x",
            (char)a1);
        goto LABEL_15;
      }
      if ( (*((_DWORD *)a1 + 34) & 0x40) != 0 )
      {
        Status = -1073741637;
        if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2048) )
          TraceEvents(
            (int)"VhdmpiOpenBackingFile",
            3535,
            2,
            2048,
            " (file '%wZ')Can't start VM on SMB share without resiliency support",
            (char)a1);
        goto LABEL_40;
      }
      if ( (unsigned int)dword_140087708 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2048) )
        TraceEvents(
          (int)"VhdmpiOpenBackingFile",
          3525,
          5,
          2048,
          " (file '%wZ')SMB server does not support resiliency",
          (char)a1);
    }
LABEL_26:
    v38 = 0;
    if ( *((_BYTE *)a1 + 624) )
    {
      v26 = VhdmpiCsvResiliencyRequired(a1, v23, v19, RelatedDeviceObject);
      v27 = dword_14008E358;
      if ( v26 )
        v27 = dword_14008E35C;
      Status = VhdmpiSetResiliencyIoTimeout(v8, v27);
      if ( Status < 0 )
      {
        if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2048) )
        {
          VhdmpiIsRemoteSmbFile(a1);
          TraceEvents(
            (int)"VhdmpiOpenBackingFile",
            3558,
            2,
            2048,
            " (file '%wZ')Failed to set resiliency IO timeout SMB[%d] CSV[%d]: 0x%08x",
            (char)a1);
        }
        goto LABEL_15;
      }
      v38 = 1;
      if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2048) )
      {
        VhdmpiIsRemoteSmbFile(a1);
        TraceEvents(
          (int)"VhdmpiOpenBackingFile",
          3570,
          4,
          2048,
          " (file '%wZ')Successfully set resiliency IO timeout %d (ms) SMB[%d] CSV[%d]",
          (char)a1);
      }
    }
    if ( !(unsigned __int8)VhdmpiIsRemoteSmbFile(a1) )
    {
      v28 = *((_DWORD *)a1 + 34);
      if ( (v28 & 0x200) == 0 )
      {
        if ( (v28 & 0x40) != 0 )
        {
          if ( (unsigned __int8)HviIsKernelApertureAvailable() )
          {
            v34 = 0;
            v35 = 0x10000000;
            Status = ZwFsControlFile(v20, 0, 0, 0, &IoStatusBlock, 0x900FCu, &v34, 0x18u, 0, 0);
            if ( Status < 0 )
            {
              if ( (unsigned int)dword_140087708 > 3 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2048) )
                TraceEvents(
                  (int)"VhdmpiOpenBackingFile",
                  3604,
                  3,
                  2048,
                  " (file '%wZ')Failed to mark file handle with MARK_HANDLE_ENABLE_CPU_CACHE: 0x%08x",
                  (char)a1);
              if ( Status != -1073741637 )
              {
                if ( (unsigned int)(Status + 1073741822) > 0xE )
                  goto LABEL_15;
                v29 = 18433;
                if ( !_bittest(&v29, Status + 1073741822) )
                  goto LABEL_15;
              }
            }
          }
        }
        if ( !v36 && (v37 & 2) == 0 && (*((_DWORD *)a1 + 36) & 1) == 0 )
        {
          v34 = 0;
          v35 = 0x4000;
          if ( ZwFsControlFile(v20, 0, 0, 0, &IoStatusBlock, 0x900FCu, &v34, 0x18u, 0, 0) < 0
            && (unsigned int)dword_140087708 > 5
            && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2048) )
          {
            TraceEvents(
              (int)"VhdmpiOpenBackingFile",
              3649,
              5,
              2048,
              " (file '%wZ')Failed to mark file handle for SKIP_COHERENCY_SYNC_DISALLOW_WRITES: 0x%08x",
              (char)a1);
          }
        }
      }
    }
    Status = 0;
    *a6 = v20;
    *a7 = v8;
    *a8 = v38;
    return (unsigned int)Status;
  }
LABEL_15:
  LOBYTE(v19) = *((_DWORD *)a1 + 150) == 3;
  VhdmpiChangeCacheMode(a1, *((unsigned int *)a1 + 35), v19);
  if ( v8 )
    ObfDereferenceObject(v8);
  if ( v20 )
    ZwClose(v20);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1400ac4f8  mov     [rsp-8+arg_10], r8d
0x1400ac4fd  push    rbp
0x1400ac4fe  push    rbx
0x1400ac4ff  push    rsi
0x1400ac500  push    rdi
0x1400ac501  push    r12
0x1400ac503  push    r13
0x1400ac505  push    r14
0x1400ac507  push    r15
0x1400ac509  lea     rbp, [rsp-7]
0x1400ac50e  sub     rsp, 98h
0x1400ac515  xor     eax, eax
0x1400ac517  mov     [rbp+3Fh+var_70], 0
0x1400ac51f  mov     [rbp+3Fh+var_48], rax
0x1400ac523  xorps   xmm0, xmm0
0x1400ac526  mov     [rbp+3Fh+Handle], rax
0x1400ac52a  xor     r13d, r13d
0x1400ac52d  mov     eax, edx
0x1400ac52f  mov     [rbp+3Fh+var_78], 0
0x1400ac537  and     eax, 40000000h
0x1400ac53c  mov     r10d, r8d
0x1400ac53f  mov     esi, edx
0x1400ac541  mov     [rbp+3Fh+arg_0], eax
0x1400ac544  mov     edx, [rcx+8Ch]
0x1400ac54a  setnz   r8b
0x1400ac54e  mov     rdi, rcx
0x1400ac551  movups  xmmword ptr [rbp+3Fh+IoStatusBlock], xmm0
0x1400ac555  movups  [rbp+3Fh+var_58], xmm0
0x1400ac559  call    ?VhdmpiChangeCacheMode@@YAEPEAU_VHD_FILE_WRAPPER@@W4_VHD_FILE_WRAPPER_CACHE_MODE@@E@Z; VhdmpiChangeCacheMode(_VHD_FILE_WRAPPER *,_VHD_FILE_WRAPPER_CACHE_MODE,uchar)
0x1400ac55e  neg     al
0x1400ac560  mov     r8d, r10d; unsigned int
0x1400ac563  lea     rax, [rbp+3Fh+Handle]
0x1400ac567  sbb     edx, edx
0x1400ac569  mov     [rsp+0D0h+HandleInformation], rax; void **
0x1400ac56e  xor     ecx, ecx
0x1400ac570  not     edx
0x1400ac572  and     edx, 8
0x1400ac575  test    r9b, r9b
0x1400ac578  mov     r9d, edx
0x1400ac57b  setnz   cl
0x1400ac57e  or      r9d, 2
0x1400ac582  cmp     dword ptr [rdi+8Ch], 3
0x1400ac589  mov     dword ptr [rsp+0D0h+Object], ecx; unsigned int
0x1400ac58d  mov     rcx, rdi; struct _VHD_FILE_WRAPPER *
0x1400ac590  cmovnz  r9d, edx; unsigned int
0x1400ac594  mov     edx, esi; unsigned int
0x1400ac596  call    ?VhdmpiOpenBackingFileWithOptions@@YAJPEAU_VHD_FILE_WRAPPER@@KKKKPEAPEAX@Z; VhdmpiOpenBackingFileWithOptions(_VHD_FILE_WRAPPER *,ulong,ulong,ulong,ulong,void * *)
0x1400ac59b  mov     r14, [rbp+3Fh+Handle]
0x1400ac59f  mov     ebx, eax
0x1400ac5a1  test    eax, eax
0x1400ac5a3  js      loc_1400AC6AD
0x1400ac5a9  mov     eax, [rdi+88h]
0x1400ac5af  test    al, 4
0x1400ac5b1  jz      short loc_1400AC5DC
0x1400ac5b3  lea     rdx, [rbp+3Fh+var_70]; void **
0x1400ac5b7  mov     rcx, r14; void *
0x1400ac5ba  call    ?VhdmpiTranslateLoopbackFileHandle@@YAJPEAXPEAPEAX@Z; VhdmpiTranslateLoopbackFileHandle(void *,void * *)
0x1400ac5bf  mov     ebx, eax
0x1400ac5c1  test    eax, eax
0x1400ac5c3  js      loc_1400AC6AD
0x1400ac5c9  mov     rcx, r14; Handle
0x1400ac5cc  call    cs:__imp_ZwClose
0x1400ac5d3  nop     dword ptr [rax+rax+00h]
0x1400ac5d8  mov     r14, [rbp+3Fh+var_70]
0x1400ac5dc  lea     rax, [rbp+3Fh+var_70]
0x1400ac5e0  mov     [rsp+0D0h+HandleInformation], r13; HandleInformation
0x1400ac5e5  xor     r9d, r9d; AccessMode
0x1400ac5e8  mov     [rsp+0D0h+Object], rax; Object
0x1400ac5ed  xor     r8d, r8d; ObjectType
0x1400ac5f0  mov     [rbp+3Fh+var_70], r13
0x1400ac5f4  mov     edx, esi; DesiredAccess
0x1400ac5f6  mov     rcx, r14; Handle
0x1400ac5f9  call    cs:__imp_ObReferenceObjectByHandle
0x1400ac600  nop     dword ptr [rax+rax+00h]
0x1400ac605  mov     r13, [rbp+3Fh+var_70]
0x1400ac609  mov     ebx, eax
0x1400ac60b  test    eax, eax
0x1400ac60d  js      loc_1400AC6AD
0x1400ac613  cmp     [rbp+3Fh+arg_20], 0
0x1400ac617  jz      loc_1400AC705
0x1400ac61d  cmp     qword ptr [rdi+218h], 0
0x1400ac625  jz      loc_1400AC705
0x1400ac62b  mov     rcx, r13; FileObject
0x1400ac62e  call    cs:__imp_IoGetRelatedDeviceObject
0x1400ac635  nop     dword ptr [rax+rax+00h]
0x1400ac63a  mov     r9, rax
0x1400ac63d  cmp     rax, [rdi+218h]
0x1400ac644  jz      loc_1400AC705
0x1400ac64a  mov     ecx, cs:dword_140087708
0x1400ac650  cmp     ecx, 2
0x1400ac653  jbe     short loc_1400AC6A8
0x1400ac655  mov     esi, 800h
0x1400ac65a  lea     rcx, dword_140087708
0x1400ac661  mov     edx, esi
0x1400ac663  call    _tlgKeywordOn
0x1400ac668  test    al, al
0x1400ac66a  jz      short loc_1400AC6A8
0x1400ac66c  mov     rax, [rdi+218h]
0x1400ac673  lea     rcx, aVhdmpiopenback_0; "VhdmpiOpenBackingFile"
0x1400ac67a  mov     qword ptr [rsp+0D0h+InputBufferLength], r9
0x1400ac67f  mov     edx, 0D90h; int
0x1400ac684  mov     [rsp+0D0h+InputBuffer], rax
0x1400ac689  mov     r9d, esi; int
0x1400ac68c  lea     rax, aFileWzDeviceOb; " (file '%wZ')Device object changed: %p "...
0x1400ac693  mov     [rsp+0D0h+HandleInformation], rdi; char
0x1400ac698  mov     r8d, 2; int
0x1400ac69e  mov     [rsp+0D0h+Object], rax; char *
0x1400ac6a3  call    TraceEvents
0x1400ac6a8  mov     ebx, 0C0190021h
0x1400ac6ad  cmp     dword ptr [rdi+258h], 3
0x1400ac6b4  mov     rcx, rdi
0x1400ac6b7  mov     edx, [rdi+8Ch]
0x1400ac6bd  setz    r8b
0x1400ac6c1  call    ?VhdmpiChangeCacheMode@@YAEPEAU_VHD_FILE_WRAPPER@@W4_VHD_FILE_WRAPPER_CACHE_MODE@@E@Z; VhdmpiChangeCacheMode(_VHD_FILE_WRAPPER *,_VHD_FILE_WRAPPER_CACHE_MODE,uchar)
0x1400ac6c6  test    r13, r13
0x1400ac6c9  jz      short loc_1400AC6DA
0x1400ac6cb  mov     rcx, r13; Object
0x1400ac6ce  call    cs:__imp_ObfDereferenceObject
0x1400ac6d5  nop     dword ptr [rax+rax+00h]
0x1400ac6da  test    r14, r14
0x1400ac6dd  jz      short loc_1400AC6EE
0x1400ac6df  mov     rcx, r14; Handle
0x1400ac6e2  call    cs:__imp_ZwClose
0x1400ac6e9  nop     dword ptr [rax+rax+00h]
0x1400ac6ee  mov     eax, ebx
0x1400ac6f0  add     rsp, 98h
0x1400ac6f7  pop     r15
0x1400ac6f9  pop     r14
0x1400ac6fb  pop     r13
0x1400ac6fd  pop     r12
0x1400ac6ff  pop     rdi
0x1400ac700  pop     rsi
0x1400ac701  pop     rbx
0x1400ac702  pop     rbp
0x1400ac703  retn
0x1400ac705  mov     eax, [rdi+88h]
0x1400ac70b  lea     r15, dword_140087708
0x1400ac712  lea     r12, aVhdmpiopenback_0; "VhdmpiOpenBackingFile"
0x1400ac719  mov     esi, 800h
0x1400ac71e  test    al, 8
0x1400ac720  jz      loc_1400AC7C8
0x1400ac726  mov     [rsp+0D0h+OutputBufferLength], 0; OutputBufferLength
0x1400ac72e  lea     rax, [rbp+3Fh+var_78]
0x1400ac732  mov     [rsp+0D0h+OutputBuffer], 0; OutputBuffer
0x1400ac73b  xor     r9d, r9d; ApcContext
0x1400ac73e  mov     [rsp+0D0h+InputBufferLength], 8; InputBufferLength
0x1400ac746  xor     r8d, r8d; ApcRoutine
0x1400ac749  mov     [rsp+0D0h+InputBuffer], rax; InputBuffer
0x1400ac74e  xor     edx, edx; Event
0x1400ac750  lea     rax, [rbp+3Fh+IoStatusBlock]
0x1400ac754  mov     dword ptr [rsp+0D0h+HandleInformation], 1401D4h; FsControlCode
0x1400ac75c  mov     rcx, r14; FileHandle
0x1400ac75f  mov     [rsp+0D0h+Object], rax; IoStatusBlock
0x1400ac764  mov     [rbp+3Fh+var_78], 7530h
0x1400ac76c  call    cs:__imp_ZwFsControlFile
0x1400ac773  nop     dword ptr [rax+rax+00h]
0x1400ac778  mov     ebx, eax
0x1400ac77a  cmp     eax, 103h
0x1400ac77f  jnz     short loc_1400AC7A8
0x1400ac781  lea     rcx, [r13+98h]; Object
0x1400ac788  mov     [rsp+0D0h+Object], 0; Timeout
0x1400ac791  xor     r9d, r9d; Alertable
0x1400ac794  xor     r8d, r8d; WaitMode
0x1400ac797  xor     edx, edx; WaitReason
0x1400ac799  call    cs:__imp_KeWaitForSingleObject
0x1400ac7a0  nop     dword ptr [rax+rax+00h]
0x1400ac7a5  mov     ebx, dword ptr [rbp+3Fh+IoStatusBlock]
0x1400ac7a8  cmp     ebx, 0C00000BBh
0x1400ac7ae  jz      loc_1400AC87E
0x1400ac7b4  cmp     ebx, 0C0000010h
0x1400ac7ba  jz      loc_1400AC87E
0x1400ac7c0  test    ebx, ebx
0x1400ac7c2  js      loc_1400AC916
0x1400ac7c8  cmp     byte ptr [rdi+270h], 0
0x1400ac7cf  mov     [rbp+3Fh+arg_18], 0
0x1400ac7d3  jz      loc_1400AC9D5
0x1400ac7d9  mov     rcx, rdi
0x1400ac7dc  call    VhdmpiCsvResiliencyRequired
0x1400ac7e1  mov     edx, cs:dword_14008E358
0x1400ac7e7  test    al, al
0x1400ac7e9  mov     rcx, r13; struct _FILE_OBJECT *
0x1400ac7ec  cmovnz  edx, cs:dword_14008E35C; unsigned int
0x1400ac7f3  mov     [rbp+3Fh+arg_8], edx
0x1400ac7f6  call    ?VhdmpiSetResiliencyIoTimeout@@YAJPEAU_FILE_OBJECT@@K@Z; VhdmpiSetResiliencyIoTimeout(_FILE_OBJECT *,ulong)
0x1400ac7fb  mov     ebx, eax
0x1400ac7fd  test    eax, eax
0x1400ac7ff  mov     eax, cs:dword_140087708
0x1400ac805  jns     loc_1400AC968
0x1400ac80b  cmp     eax, 2
0x1400ac80e  jbe     loc_1400AC6AD
0x1400ac814  mov     rdx, rsi
0x1400ac817  mov     rcx, r15
0x1400ac81a  call    _tlgKeywordOn
0x1400ac81f  test    al, al
0x1400ac821  jz      loc_1400AC6AD
0x1400ac827  mov     edx, [rdi+88h]
0x1400ac82d  mov     rcx, rdi
0x1400ac830  shr     edx, 9
0x1400ac833  and     edx, 1
0x1400ac836  call    VhdmpiIsRemoteSmbFile
0x1400ac83b  xor     ecx, ecx
0x1400ac83d  mov     dword ptr [rsp+0D0h+OutputBuffer], ebx
0x1400ac841  mov     [rsp+0D0h+InputBufferLength], edx
0x1400ac845  test    al, al
0x1400ac847  mov     r10d, 0DE6h
0x1400ac84d  lea     rax, aFileWzFailedTo_0; " (file '%wZ')Failed to set resiliency I"...
0x1400ac854  setnz   cl
0x1400ac857  mov     r9d, esi; int
0x1400ac85a  mov     dword ptr [rsp+0D0h+InputBuffer], ecx
0x1400ac85e  mov     r8d, 2; int
0x1400ac864  mov     [rsp+0D0h+HandleInformation], rdi; char
0x1400ac869  mov     rcx, r12; int
0x1400ac86c  mov     edx, r10d; int
0x1400ac86f  mov     [rsp+0D0h+Object], rax; char *
0x1400ac874  call    TraceEvents
0x1400ac879  jmp     loc_1400AC6AD
0x1400ac87e  mov     eax, [rdi+88h]
0x1400ac884  test    al, 40h
0x1400ac886  mov     eax, cs:dword_140087708
0x1400ac88c  jnz     short loc_1400AC8D6
0x1400ac88e  cmp     eax, 5
0x1400ac891  jbe     loc_1400AC7C8
0x1400ac897  mov     rdx, rsi
0x1400ac89a  mov     rcx, r15
0x1400ac89d  call    _tlgKeywordOn
0x1400ac8a2  test    al, al
0x1400ac8a4  jz      loc_1400AC7C8
0x1400ac8aa  lea     rax, aFileWzSmbServe; " (file '%wZ')SMB server does not suppor"...
0x1400ac8b1  mov     [rsp+0D0h+HandleInformation], rdi; char
0x1400ac8b6  mov     edx, 0DC5h; int
0x1400ac8bb  mov     [rsp+0D0h+Object], rax; char *
0x1400ac8c0  mov     r9d, esi; int
0x1400ac8c3  mov     r8d, 5; int
0x1400ac8c9  mov     rcx, r12; int
0x1400ac8cc  call    TraceEvents
0x1400ac8d1  jmp     loc_1400AC7C8
0x1400ac8d6  mov     ebx, 0C00000BBh
0x1400ac8db  cmp     eax, 2
0x1400ac8de  jbe     short loc_1400AC916
0x1400ac8e0  mov     rdx, rsi
0x1400ac8e3  mov     rcx, r15
0x1400ac8e6  call    _tlgKeywordOn
0x1400ac8eb  test    al, al
0x1400ac8ed  jz      short loc_1400AC916
0x1400ac8ef  lea     rax, aFileWzCanTStar; " (file '%wZ')Can't start VM on SMB shar"...
0x1400ac8f6  mov     [rsp+0D0h+HandleInformation], rdi; char
0x1400ac8fb  mov     edx, 0DCFh; int
0x1400ac900  mov     [rsp+0D0h+Object], rax; char *
0x1400ac905  mov     r9d, esi; int
0x1400ac908  mov     r8d, 2; int
0x1400ac90e  mov     rcx, r12; int
0x1400ac911  call    TraceEvents
0x1400ac916  mov     eax, cs:dword_140087708
0x1400ac91c  cmp     eax, 2
0x1400ac91f  jbe     short loc_1400AC95B
0x1400ac921  mov     rdx, rsi
0x1400ac924  mov     rcx, r15
0x1400ac927  call    _tlgKeywordOn
0x1400ac92c  test    al, al
0x1400ac92e  jz      short loc_1400AC95B
0x1400ac930  mov     dword ptr [rsp+0D0h+InputBuffer], ebx
0x1400ac934  lea     rax, aFileWzFailedTo_5; " (file '%wZ')Failed to enable resilienc"...
0x1400ac93b  mov     [rsp+0D0h+HandleInformation], rdi; char
0x1400ac940  mov     edx, 0DD7h; int
0x1400ac945  mov     r9d, esi; int
0x1400ac948  mov     [rsp+0D0h+Object], rax; char *
0x1400ac94d  mov     r8d, 2; int
0x1400ac953  mov     rcx, r12; int
0x1400ac956  call    TraceEvents
0x1400ac95b  test    ebx, ebx
0x1400ac95d  jns     loc_1400AC6C6
0x1400ac963  jmp     loc_1400AC6AD
0x1400ac968  mov     [rbp+3Fh+arg_18], 1
0x1400ac96c  cmp     eax, 4
0x1400ac96f  jbe     short loc_1400AC9D5
0x1400ac971  mov     rdx, rsi
0x1400ac974  mov     rcx, r15
0x1400ac977  call    _tlgKeywordOn
0x1400ac97c  test    al, al
0x1400ac97e  jz      short loc_1400AC9D5
0x1400ac980  mov     edx, [rdi+88h]
0x1400ac986  mov     rcx, rdi
0x1400ac989  shr     edx, 9
0x1400ac98c  and     edx, 1
0x1400ac98f  call    VhdmpiIsRemoteSmbFile
0x1400ac994  mov     dword ptr [rsp+0D0h+OutputBuffer], edx
0x1400ac998  xor     ecx, ecx
0x1400ac99a  test    al, al
0x1400ac99c  mov     r10d, 0DF2h
0x1400ac9a2  mov     eax, [rbp+3Fh+arg_8]
0x1400ac9a5  mov     r9d, esi; int
0x1400ac9a8  setnz   cl
0x1400ac9ab  mov     r8d, 4; int
0x1400ac9b1  mov     [rsp+0D0h+InputBufferLength], ecx
0x1400ac9b5  mov     edx, r10d; int
0x1400ac9b8  mov     dword ptr [rsp+0D0h+InputBuffer], eax
0x1400ac9bc  mov     rcx, r12; int
0x1400ac9bf  lea     rax, aFileWzSuccessf_1; " (file '%wZ')Successfully set resilienc"...
0x1400ac9c6  mov     [rsp+0D0h+HandleInformation], rdi; char
0x1400ac9cb  mov     [rsp+0D0h+Object], rax; char *
  ... truncated ...
```
