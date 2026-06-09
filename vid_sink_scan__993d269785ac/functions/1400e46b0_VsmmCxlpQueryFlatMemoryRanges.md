# VsmmCxlpQueryFlatMemoryRanges

- ea: `0x1400e46b0`
- end: `0x1400e4bc9`
- name: `VsmmCxlpQueryFlatMemoryRanges`
- size: `1305`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400e4250`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x140021650`
- `0x14002f524`
- `0x1400e4474`
- `0x1400e46b0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400e4b66`
- `ntoskrnl!ZwClose` at `0x1400e4b7c`
- `ntoskrnl!ZwClose` at `0x1400e4b66`
- `ntoskrnl!ZwClose` at `0x1400e4b7c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e4b95`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e4b95`
- `ntoskrnl!ZwCreateEvent` at `0x1400e4737`
- `ntoskrnl!ZwCreateEvent` at `0x1400e4737`
- `ntoskrnl!ExAllocatePool2` at `0x1400e4867`
- `ntoskrnl!ExAllocatePool2` at `0x1400e4867`
- `ntoskrnl!ZwWaitForSingleObject` at `0x1400e481d`
- `ntoskrnl!ZwWaitForSingleObject` at `0x1400e497f`
- `ntoskrnl!ZwWaitForSingleObject` at `0x1400e481d`
- `ntoskrnl!ZwWaitForSingleObject` at `0x1400e497f`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x1400e47fe`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x1400e4960`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x1400e47fe`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x1400e4960`

## pseudocode

```c
__int64 __fastcall VsmmCxlpQueryFlatMemoryRanges(_QWORD *a1)
{
  _DWORD *v2; // rdi
  NTSTATUS Status; // ebx
  int v4; // eax
  _DWORD *Pool2; // rax
  unsigned __int8 *v6; // rdx
  int v7; // r8d
  ULONG InitialState; // [rsp+20h] [rbp-E0h]
  char v10; // [rsp+50h] [rbp-B0h] BYREF
  int v11; // [rsp+54h] [rbp-ACh] BYREF
  ULONG v12; // [rsp+58h] [rbp-A8h] BYREF
  int v13; // [rsp+5Ch] [rbp-A4h] BYREF
  void *EventHandle; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE FileHandle; // [rsp+68h] [rbp-98h] BYREF
  ULONG OutputBuffer[2]; // [rsp+70h] [rbp-90h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-88h] BYREF
  __int64 v18; // [rsp+88h] [rbp-78h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-70h] BYREF
  __int128 InputBuffer; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v21; // [rsp+D0h] [rbp-30h]
  struct _EVENT_DATA_DESCRIPTOR v22[2]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v23[16]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v24[16]; // [rsp+110h] [rbp+10h] BYREF
  int *v25; // [rsp+120h] [rbp+20h]
  __int64 v26; // [rsp+128h] [rbp+28h]
  int *v27; // [rsp+130h] [rbp+30h]
  __int64 v28; // [rsp+138h] [rbp+38h]
  ULONG *v29; // [rsp+140h] [rbp+40h]
  __int64 v30; // [rsp+148h] [rbp+48h]
  int *v31; // [rsp+150h] [rbp+50h]
  __int64 v32; // [rsp+158h] [rbp+58h]

  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 512;
  FileHandle = 0;
  EventHandle = 0;
  v21 = 0;
  *(_QWORD *)OutputBuffer = 0;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = 0;
  IoStatusBlock = 0;
  v2 = 0;
  InputBuffer = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  Status = ZwCreateEvent(&EventHandle, 0x1F0003u, &ObjectAttributes, SynchronizationEvent, 0);
  if ( Status < 0 )
  {
    VidTraceErrorStatusInternal0("VsmmCxlpQueryFlatMemoryRanges", "onecore\\vm\\vid\\sys\\vsmm\\vsmmcxl.c", 230);
    goto LABEL_34;
  }
  v4 = VsmmCxlpOpenScmbusCxlDevice(&FileHandle);
  Status = v4;
  if ( v4 < 0 )
  {
    if ( v4 != -1073741275 )
      VidTraceErrorStatusInternal0("VsmmCxlpQueryFlatMemoryRanges", "onecore\\vm\\vid\\sys\\vsmm\\vsmmcxl.c", 240);
    goto LABEL_32;
  }
  LODWORD(InputBuffer) = 1;
  *(_QWORD *)((char *)&InputBuffer + 4) = 24;
  HIDWORD(InputBuffer) = 0;
  Status = ZwDeviceIoControlFile(
             FileHandle,
             EventHandle,
             0,
             0,
             &IoStatusBlock,
             0x660000u,
             &InputBuffer,
             0x18u,
             OutputBuffer,
             8u);
  if ( Status == 259 )
  {
    Status = ZwWaitForSingleObject(EventHandle, 0, 0);
    if ( Status < 0 )
    {
LABEL_10:
      VidTraceErrorStatusInternal0("VsmmCxlpQueryFlatMemoryRanges", "onecore\\vm\\vid\\sys\\vsmm\\vsmmcxl.c", 280);
      goto LABEL_32;
    }
    Status = IoStatusBlock.Status;
  }
  if ( Status < 0 )
    goto LABEL_10;
  Pool2 = (_DWORD *)ExAllocatePool2(64, OutputBuffer[1], 1833788502);
  v2 = Pool2;
  if ( Pool2 )
  {
    Status = ZwDeviceIoControlFile(
               FileHandle,
               EventHandle,
               0,
               0,
               &IoStatusBlock,
               0x660000u,
               &InputBuffer,
               0x18u,
               Pool2,
               OutputBuffer[1]);
    if ( Status == 259 )
    {
      Status = ZwWaitForSingleObject(EventHandle, 0, 0);
      if ( Status < 0 )
        goto LABEL_19;
      Status = IoStatusBlock.Status;
    }
    if ( Status >= 0 )
    {
      if ( v2[1] >= 0x38u && *v2 == 1 )
      {
        if ( !v2[2] )
        {
          *a1 = v2;
          Status = 0;
          v2 = 0;
          goto LABEL_32;
        }
        Status = -1073741637;
        if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
          goto LABEL_32;
        tlgCreate1Sz_char(v23, "VsmmCxlpQueryFlatMemoryRanges");
        tlgCreate1Sz_char(v24, "onecore\\vm\\vid\\sys\\vsmm\\vsmmcxl.c");
        v12 = 355;
        v25 = (int *)&v12;
        v6 = (unsigned __int8 *)&byte_14005B4F7;
        v30 = 1;
        v27 = &v11;
        v10 = *((_BYTE *)v2 + 8);
        v29 = (ULONG *)&v10;
        InitialState = 7;
      }
      else
      {
        Status = -1073741637;
        if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
          goto LABEL_32;
        tlgCreate1Sz_char(v23, "VsmmCxlpQueryFlatMemoryRanges");
        tlgCreate1Sz_char(v24, "onecore\\vm\\vid\\sys\\vsmm\\vsmmcxl.c");
        v12 = 342;
        v30 = 8;
        v25 = (int *)&v12;
        v27 = &v11;
        v18 = (unsigned int)v2[1];
        v29 = (ULONG *)&v18;
        v13 = *v2;
        v31 = &v13;
        InitialState = 8;
        v6 = (unsigned __int8 *)word_14005B49A;
        v32 = 4;
      }
      v11 = v7;
      goto LABEL_31;
    }
LABEL_19:
    VidTraceErrorStatusInternal0("VsmmCxlpQueryFlatMemoryRanges", "onecore\\vm\\vid\\sys\\vsmm\\vsmmcxl.c", 327);
    goto LABEL_32;
  }
  Status = -1073741670;
  if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
  {
    tlgCreate1Sz_char(v23, "VsmmCxlpQueryFlatMemoryRanges");
    tlgCreate1Sz_char(v24, "onecore\\vm\\vid\\sys\\vsmm\\vsmmcxl.c");
    v13 = 299;
    v25 = &v13;
    v6 = (unsigned __int8 *)qword_14005B598;
    v11 = -1073741670;
    v27 = &v11;
    v12 = OutputBuffer[1];
    v29 = &v12;
    InitialState = 7;
    v30 = 4;
LABEL_31:
    v26 = 4;
    v28 = 4;
    tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140064110, v6, 0, 0, InitialState, v22);
  }
LABEL_32:
  if ( FileHandle )
    ZwClose(FileHandle);
LABEL_34:
  if ( EventHandle )
    ZwClose(EventHandle);
  if ( v2 )
    ExFreePoolWithTag(v2, 0x6D4D6456u);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1400e46b0  mov     [rsp-8+arg_8], rbx
0x1400e46b5  mov     [rsp-8+arg_10], rdi
0x1400e46ba  push    rbp
0x1400e46bb  push    r14
0x1400e46bd  push    r15
0x1400e46bf  lea     rbp, [rsp-70h]
0x1400e46c4  sub     rsp, 170h
0x1400e46cb  mov     rax, cs:__security_cookie
0x1400e46d2  xor     rax, rsp
0x1400e46d5  mov     [rbp+80h+var_20], rax
0x1400e46d9  xor     r15d, r15d
0x1400e46dc  mov     qword ptr [rbp+80h+ObjectAttributes.Length], 30h ; '0'
0x1400e46e4  xorps   xmm0, xmm0
0x1400e46e7  mov     qword ptr [rbp+80h+ObjectAttributes.Attributes], 200h
0x1400e46ef  xor     eax, eax
0x1400e46f1  mov     [rsp+180h+FileHandle], r15
0x1400e46f6  mov     r14, rcx
0x1400e46f9  mov     [rsp+180h+EventHandle], r15
0x1400e46fe  lea     r8, [rbp+80h+ObjectAttributes]; ObjectAttributes
0x1400e4702  mov     [rbp+80h+var_B0], rax
0x1400e4706  mov     edx, 1F0003h; DesiredAccess
0x1400e470b  mov     qword ptr [rsp+180h+var_110], r15
0x1400e4710  lea     r9d, [rax+1]; EventType
0x1400e4714  mov     [rbp+80h+ObjectAttributes.RootDirectory], r15
0x1400e4718  lea     rcx, [rsp+180h+EventHandle]; EventHandle
0x1400e471d  mov     [rbp+80h+ObjectAttributes.ObjectName], r15
0x1400e4721  movups  xmmword ptr [rsp+180h+IoStatusBlock], xmm0
0x1400e4726  mov     edi, r15d
0x1400e4729  mov     [rsp+180h+InitialState], r15b; InitialState
0x1400e472e  movups  [rbp+80h+var_C0], xmm0
0x1400e4732  movdqu  xmmword ptr [rbp+80h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400e4737  call    cs:__imp_ZwCreateEvent
0x1400e473e  nop     dword ptr [rax+rax+00h]
0x1400e4743  mov     ebx, eax
0x1400e4745  test    eax, eax
0x1400e4747  jns     short loc_1400E476A
0x1400e4749  mov     r9d, eax
0x1400e474c  lea     rdx, aOnecoreVmVidSy_23; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcxl.c"
0x1400e4753  mov     r8d, 0E6h
0x1400e4759  lea     rcx, aVsmmcxlpqueryf; "VsmmCxlpQueryFlatMemoryRanges"
0x1400e4760  call    VidTraceErrorStatusInternal0
0x1400e4765  jmp     loc_1400E4B72
0x1400e476a  lea     rcx, [rsp+180h+FileHandle]
0x1400e476f  call    VsmmCxlpOpenScmbusCxlDevice
0x1400e4774  mov     ebx, eax
0x1400e4776  test    eax, eax
0x1400e4778  jns     short loc_1400E47A6
0x1400e477a  cmp     eax, 0C0000225h
0x1400e477f  jz      loc_1400E4B5A
0x1400e4785  mov     r9d, eax
0x1400e4788  lea     rdx, aOnecoreVmVidSy_23; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcxl.c"
0x1400e478f  mov     r8d, 0F0h
0x1400e4795  lea     rcx, aVsmmcxlpqueryf; "VsmmCxlpQueryFlatMemoryRanges"
0x1400e479c  call    VidTraceErrorStatusInternal0
0x1400e47a1  jmp     loc_1400E4B5A
0x1400e47a6  mov     rdx, [rsp+180h+EventHandle]; Event
0x1400e47ab  lea     rax, [rsp+180h+var_110]
0x1400e47b0  mov     rcx, [rsp+180h+FileHandle]; FileHandle
0x1400e47b5  xor     r9d, r9d; ApcContext
0x1400e47b8  mov     [rsp+180h+OutputBufferLength], 8; OutputBufferLength
0x1400e47c0  xor     r8d, r8d; ApcRoutine
0x1400e47c3  mov     [rsp+180h+OutputBuffer], rax; OutputBuffer
0x1400e47c8  lea     rax, [rbp+80h+var_C0]
0x1400e47cc  mov     [rsp+180h+InputBufferLength], 18h; InputBufferLength
0x1400e47d4  mov     [rsp+180h+InputBuffer], rax; InputBuffer
0x1400e47d9  lea     rax, [rsp+180h+IoStatusBlock]
0x1400e47de  mov     [rsp+180h+IoControlCode], 660000h; IoControlCode
0x1400e47e6  mov     qword ptr [rsp+180h+InitialState], rax; IoStatusBlock
0x1400e47eb  mov     dword ptr [rbp+80h+var_C0], 1
0x1400e47f2  mov     qword ptr [rbp+80h+var_C0+4], 18h
0x1400e47fa  mov     dword ptr [rbp+80h+var_C0+0Ch], r15d
0x1400e47fe  call    cs:__imp_ZwDeviceIoControlFile
0x1400e4805  nop     dword ptr [rax+rax+00h]
0x1400e480a  mov     ebx, eax
0x1400e480c  cmp     eax, 103h
0x1400e4811  jnz     short loc_1400E4833
0x1400e4813  mov     rcx, [rsp+180h+EventHandle]; Handle
0x1400e4818  xor     r8d, r8d; Timeout
0x1400e481b  xor     edx, edx; Alertable
0x1400e481d  call    cs:__imp_ZwWaitForSingleObject
0x1400e4824  nop     dword ptr [rax+rax+00h]
0x1400e4829  mov     ebx, eax
0x1400e482b  test    eax, eax
0x1400e482d  js      short loc_1400E4837
0x1400e482f  mov     ebx, dword ptr [rsp+180h+IoStatusBlock]
0x1400e4833  test    ebx, ebx
0x1400e4835  jns     short loc_1400E4858
0x1400e4837  mov     r9d, ebx
0x1400e483a  lea     rdx, aOnecoreVmVidSy_23; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcxl.c"
0x1400e4841  mov     r8d, 118h
0x1400e4847  lea     rcx, aVsmmcxlpqueryf; "VsmmCxlpQueryFlatMemoryRanges"
0x1400e484e  call    VidTraceErrorStatusInternal0
0x1400e4853  jmp     loc_1400E4B5A
0x1400e4858  mov     edx, [rsp+180h+var_110+4]
0x1400e485c  mov     ecx, 40h ; '@'
0x1400e4861  mov     r8d, 6D4D6456h
0x1400e4867  call    cs:__imp_ExAllocatePool2
0x1400e486e  nop     dword ptr [rax+rax+00h]
0x1400e4873  mov     rdi, rax
0x1400e4876  test    rax, rax
0x1400e4879  jnz     loc_1400E4920
0x1400e487f  mov     eax, cs:dword_140064110
0x1400e4885  mov     ebx, 0C000009Ah
0x1400e488a  cmp     eax, 2
0x1400e488d  jbe     loc_1400E4B5A
0x1400e4893  mov     edx, 100h
0x1400e4898  lea     rcx, dword_140064110
0x1400e489f  call    _tlgKeywordOn
0x1400e48a4  test    al, al
0x1400e48a6  jz      loc_1400E4B5A
0x1400e48ac  lea     rdx, aVsmmcxlpqueryf; "VsmmCxlpQueryFlatMemoryRanges"
0x1400e48b3  lea     rcx, [rbp+80h+var_80]
0x1400e48b7  call    _tlgCreate1Sz_char
0x1400e48bc  lea     rdx, aOnecoreVmVidSy_23; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcxl.c"
0x1400e48c3  lea     rcx, [rbp+80h+var_70]
0x1400e48c7  call    _tlgCreate1Sz_char
0x1400e48cc  lea     rax, [rsp+180h+var_124]
0x1400e48d1  mov     [rsp+180h+var_124], 12Bh
0x1400e48d9  mov     [rbp+80h+var_60], rax
0x1400e48dd  lea     rdx, qword_14005B598
0x1400e48e4  lea     rax, [rsp+180h+var_12C]
0x1400e48e9  mov     [rsp+180h+var_12C], ebx
0x1400e48ed  mov     [rbp+80h+var_50], rax
0x1400e48f1  mov     eax, [rsp+180h+var_110+4]
0x1400e48f5  mov     [rsp+180h+var_128], eax
0x1400e48f9  lea     rax, [rsp+180h+var_128]
0x1400e48fe  mov     [rbp+80h+var_40], rax
0x1400e4902  lea     rax, [rbp+80h+var_A0]
0x1400e4906  mov     qword ptr [rsp+180h+IoControlCode], rax
0x1400e490b  mov     dword ptr [rsp+180h+InitialState], 7
0x1400e4913  mov     [rbp+80h+var_38], 4
0x1400e491b  jmp     loc_1400E4B38
0x1400e4920  mov     eax, [rsp+180h+var_110+4]
0x1400e4924  xor     r9d, r9d; ApcContext
0x1400e4927  mov     rdx, [rsp+180h+EventHandle]; Event
0x1400e492c  xor     r8d, r8d; ApcRoutine
0x1400e492f  mov     rcx, [rsp+180h+FileHandle]; FileHandle
0x1400e4934  mov     [rsp+180h+OutputBufferLength], eax; OutputBufferLength
0x1400e4938  lea     rax, [rbp+80h+var_C0]
0x1400e493c  mov     [rsp+180h+OutputBuffer], rdi; OutputBuffer
0x1400e4941  mov     [rsp+180h+InputBufferLength], 18h; InputBufferLength
0x1400e4949  mov     [rsp+180h+InputBuffer], rax; InputBuffer
0x1400e494e  lea     rax, [rsp+180h+IoStatusBlock]
0x1400e4953  mov     [rsp+180h+IoControlCode], 660000h; IoControlCode
0x1400e495b  mov     qword ptr [rsp+180h+InitialState], rax; IoStatusBlock
0x1400e4960  call    cs:__imp_ZwDeviceIoControlFile
0x1400e4967  nop     dword ptr [rax+rax+00h]
0x1400e496c  mov     ebx, eax
0x1400e496e  cmp     eax, 103h
0x1400e4973  jnz     short loc_1400E4995
0x1400e4975  mov     rcx, [rsp+180h+EventHandle]; Handle
0x1400e497a  xor     r8d, r8d; Timeout
0x1400e497d  xor     edx, edx; Alertable
0x1400e497f  call    cs:__imp_ZwWaitForSingleObject
0x1400e4986  nop     dword ptr [rax+rax+00h]
0x1400e498b  mov     ebx, eax
0x1400e498d  test    eax, eax
0x1400e498f  js      short loc_1400E4999
0x1400e4991  mov     ebx, dword ptr [rsp+180h+IoStatusBlock]
0x1400e4995  test    ebx, ebx
0x1400e4997  jns     short loc_1400E49BA
0x1400e4999  mov     r9d, ebx
0x1400e499c  lea     rdx, aOnecoreVmVidSy_23; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcxl.c"
0x1400e49a3  mov     r8d, 147h
0x1400e49a9  lea     rcx, aVsmmcxlpqueryf; "VsmmCxlpQueryFlatMemoryRanges"
0x1400e49b0  call    VidTraceErrorStatusInternal0
0x1400e49b5  jmp     loc_1400E4B5A
0x1400e49ba  cmp     dword ptr [rdi+4], 38h ; '8'
0x1400e49be  jb      loc_1400E4A85
0x1400e49c4  cmp     dword ptr [rdi], 1
0x1400e49c7  jnz     loc_1400E4A85
0x1400e49cd  cmp     [rdi+8], r15d
0x1400e49d1  jz      loc_1400E4A77
0x1400e49d7  mov     eax, cs:dword_140064110
0x1400e49dd  mov     r8d, 0C00000BBh
0x1400e49e3  mov     ebx, r8d
0x1400e49e6  cmp     eax, 2
0x1400e49e9  jbe     loc_1400E4B5A
0x1400e49ef  mov     edx, 100h
0x1400e49f4  lea     rcx, dword_140064110
0x1400e49fb  call    _tlgKeywordOn
0x1400e4a00  test    al, al
0x1400e4a02  jz      loc_1400E4B5A
0x1400e4a08  lea     rdx, aVsmmcxlpqueryf; "VsmmCxlpQueryFlatMemoryRanges"
0x1400e4a0f  lea     rcx, [rbp+80h+var_80]
0x1400e4a13  call    _tlgCreate1Sz_char
0x1400e4a18  lea     rdx, aOnecoreVmVidSy_23; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcxl.c"
0x1400e4a1f  lea     rcx, [rbp+80h+var_70]
0x1400e4a23  call    _tlgCreate1Sz_char
0x1400e4a28  lea     rax, [rsp+180h+var_128]
0x1400e4a2d  mov     [rsp+180h+var_128], 163h
0x1400e4a35  mov     [rbp+80h+var_60], rax
0x1400e4a39  lea     rdx, byte_14005B4F7
0x1400e4a40  lea     rax, [rsp+180h+var_12C]
0x1400e4a45  mov     [rbp+80h+var_38], 1
0x1400e4a4d  mov     [rbp+80h+var_50], rax
0x1400e4a51  mov     al, [rdi+8]
0x1400e4a54  mov     [rsp+180h+var_130], al
0x1400e4a58  lea     rax, [rsp+180h+var_130]
0x1400e4a5d  mov     [rbp+80h+var_40], rax
0x1400e4a61  lea     rax, [rbp+80h+var_A0]
0x1400e4a65  mov     qword ptr [rsp+180h+IoControlCode], rax
0x1400e4a6a  mov     dword ptr [rsp+180h+InitialState], 7
0x1400e4a72  jmp     loc_1400E4B33
0x1400e4a77  mov     [r14], rdi
0x1400e4a7a  mov     ebx, r15d
0x1400e4a7d  mov     rdi, r15
0x1400e4a80  jmp     loc_1400E4B5A
0x1400e4a85  mov     eax, cs:dword_140064110
0x1400e4a8b  mov     r8d, 0C00000BBh
0x1400e4a91  mov     ebx, r8d
0x1400e4a94  cmp     eax, 2
0x1400e4a97  jbe     loc_1400E4B5A
0x1400e4a9d  mov     edx, 100h
0x1400e4aa2  lea     rcx, dword_140064110
0x1400e4aa9  call    _tlgKeywordOn
0x1400e4aae  test    al, al
0x1400e4ab0  jz      loc_1400E4B5A
0x1400e4ab6  lea     rdx, aVsmmcxlpqueryf; "VsmmCxlpQueryFlatMemoryRanges"
0x1400e4abd  lea     rcx, [rbp+80h+var_80]
0x1400e4ac1  call    _tlgCreate1Sz_char
0x1400e4ac6  lea     rdx, aOnecoreVmVidSy_23; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcxl.c"
0x1400e4acd  lea     rcx, [rbp+80h+var_70]
0x1400e4ad1  call    _tlgCreate1Sz_char
0x1400e4ad6  mov     edx, 8
0x1400e4adb  mov     [rsp+180h+var_128], 156h
0x1400e4ae3  lea     rax, [rsp+180h+var_128]
0x1400e4ae8  mov     [rbp+80h+var_38], rdx
0x1400e4aec  mov     [rbp+80h+var_60], rax
0x1400e4af0  lea     rax, [rsp+180h+var_12C]
0x1400e4af5  mov     [rbp+80h+var_50], rax
0x1400e4af9  mov     eax, [rdi+4]
0x1400e4afc  mov     [rbp+80h+var_F8], rax
0x1400e4b00  lea     rax, [rbp+80h+var_F8]
0x1400e4b04  mov     [rbp+80h+var_40], rax
0x1400e4b08  mov     eax, [rdi]
0x1400e4b0a  mov     [rsp+180h+var_124], eax
0x1400e4b0e  lea     rax, [rsp+180h+var_124]
0x1400e4b13  mov     [rbp+80h+var_30], rax
0x1400e4b17  lea     rax, [rbp+80h+var_A0]
0x1400e4b1b  mov     qword ptr [rsp+180h+IoControlCode], rax
0x1400e4b20  mov     dword ptr [rsp+180h+InitialState], edx
0x1400e4b24  lea     rdx, word_14005B49A
0x1400e4b2b  mov     [rbp+80h+var_28], 4
0x1400e4b33  mov     [rsp+180h+var_12C], r8d
0x1400e4b38  xor     r9d, r9d
0x1400e4b3b  mov     [rbp+80h+var_58], 4
0x1400e4b43  xor     r8d, r8d
0x1400e4b46  mov     [rbp+80h+var_48], 4
0x1400e4b4e  lea     rcx, dword_140064110
0x1400e4b55  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400e4b5a  cmp     [rsp+180h+FileHandle], r15
0x1400e4b5f  jz      short loc_1400E4B72
0x1400e4b61  mov     rcx, [rsp+180h+FileHandle]; Handle
0x1400e4b66  call    cs:__imp_ZwClose
0x1400e4b6d  nop     dword ptr [rax+rax+00h]
0x1400e4b72  mov     rcx, [rsp+180h+EventHandle]; Handle
0x1400e4b77  test    rcx, rcx
0x1400e4b7a  jz      short loc_1400E4B88
0x1400e4b7c  call    cs:__imp_ZwClose
0x1400e4b83  nop     dword ptr [rax+rax+00h]
0x1400e4b88  test    rdi, rdi
0x1400e4b8b  jz      short loc_1400E4BA1
0x1400e4b8d  mov     edx, 6D4D6456h; Tag
0x1400e4b92  mov     rcx, rdi; P
0x1400e4b95  call    cs:__imp_ExFreePoolWithTag
0x1400e4b9c  nop     dword ptr [rax+rax+00h]
0x1400e4ba1  mov     eax, ebx
0x1400e4ba3  mov     rcx, [rbp+80h+var_20]
0x1400e4ba7  xor     rcx, rsp; StackCookie
0x1400e4baa  call    __security_check_cookie
0x1400e4baf  lea     r11, [rsp+180h+var_10]
0x1400e4bb7  mov     rbx, [r11+28h]
0x1400e4bbb  mov     rdi, [r11+30h]
0x1400e4bbf  mov     rsp, r11
0x1400e4bc2  pop     r15
0x1400e4bc4  pop     r14
0x1400e4bc6  pop     rbp
0x1400e4bc7  retn
```
