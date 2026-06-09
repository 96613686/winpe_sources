# VsmmCxlpQueryFlatMemoryRanges

- ea: `0x1400e7248`
- end: `0x1400e7761`
- name: `VsmmCxlpQueryFlatMemoryRanges`
- size: `1305`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400e6de8`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x140021c60`
- `0x14002f724`
- `0x1400e700c`
- `0x1400e7248`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400e76fe`
- `ntoskrnl!ZwClose` at `0x1400e7714`
- `ntoskrnl!ZwClose` at `0x1400e76fe`
- `ntoskrnl!ZwClose` at `0x1400e7714`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e772d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e772d`
- `ntoskrnl!ZwCreateEvent` at `0x1400e72cf`
- `ntoskrnl!ZwCreateEvent` at `0x1400e72cf`
- `ntoskrnl!ExAllocatePool2` at `0x1400e73ff`
- `ntoskrnl!ExAllocatePool2` at `0x1400e73ff`
- `ntoskrnl!ZwWaitForSingleObject` at `0x1400e73b5`
- `ntoskrnl!ZwWaitForSingleObject` at `0x1400e7517`
- `ntoskrnl!ZwWaitForSingleObject` at `0x1400e73b5`
- `ntoskrnl!ZwWaitForSingleObject` at `0x1400e7517`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x1400e7396`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x1400e74f8`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x1400e7396`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x1400e74f8`

## pseudocode

```c
__int64 __fastcall VsmmCxlpQueryFlatMemoryRanges(_QWORD *a1)
{
  _DWORD *v2; // rdi
  NTSTATUS v3; // eax
  NTSTATUS Status; // ebx
  int v5; // eax
  _DWORD *Pool2; // rax
  char *v7; // rdx
  int v8; // r8d
  ULONG InitialState; // [rsp+20h] [rbp-E0h]
  char v11; // [rsp+50h] [rbp-B0h] BYREF
  int v12; // [rsp+54h] [rbp-ACh] BYREF
  ULONG v13; // [rsp+58h] [rbp-A8h] BYREF
  int v14; // [rsp+5Ch] [rbp-A4h] BYREF
  void *EventHandle; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE FileHandle; // [rsp+68h] [rbp-98h] BYREF
  ULONG OutputBuffer[2]; // [rsp+70h] [rbp-90h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-88h] BYREF
  __int64 v19; // [rsp+88h] [rbp-78h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-70h] BYREF
  __int128 InputBuffer; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v22; // [rsp+D0h] [rbp-30h]
  struct _EVENT_DATA_DESCRIPTOR v23; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v24[16]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v25[16]; // [rsp+110h] [rbp+10h] BYREF
  int *v26; // [rsp+120h] [rbp+20h]
  __int64 v27; // [rsp+128h] [rbp+28h]
  int *v28; // [rsp+130h] [rbp+30h]
  __int64 v29; // [rsp+138h] [rbp+38h]
  ULONG *v30; // [rsp+140h] [rbp+40h]
  __int64 v31; // [rsp+148h] [rbp+48h]
  int *v32; // [rsp+150h] [rbp+50h]
  __int64 v33; // [rsp+158h] [rbp+58h]

  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 512;
  FileHandle = 0;
  EventHandle = 0;
  v22 = 0;
  *(_QWORD *)OutputBuffer = 0;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = 0;
  IoStatusBlock = 0;
  v2 = 0;
  InputBuffer = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v3 = ZwCreateEvent(&EventHandle, 0x1F0003u, &ObjectAttributes, SynchronizationEvent, 0);
  Status = v3;
  if ( v3 < 0 )
  {
    VidTraceErrorStatusInternal0(
      "VsmmCxlpQueryFlatMemoryRanges",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmcxl.c",
      230,
      (unsigned int)v3);
    goto LABEL_34;
  }
  v5 = VsmmCxlpOpenScmbusCxlDevice(&FileHandle);
  Status = v5;
  if ( v5 < 0 )
  {
    if ( v5 != -1073741275 )
      VidTraceErrorStatusInternal0(
        "VsmmCxlpQueryFlatMemoryRanges",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmcxl.c",
        240,
        (unsigned int)v5);
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
      VidTraceErrorStatusInternal0(
        "VsmmCxlpQueryFlatMemoryRanges",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmcxl.c",
        280,
        (unsigned int)Status);
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
        if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
          goto LABEL_32;
        tlgCreate1Sz_char(v24, "VsmmCxlpQueryFlatMemoryRanges");
        tlgCreate1Sz_char(v25, "onecore\\vm\\vid\\sys\\vsmm\\vsmmcxl.c");
        v13 = 355;
        v26 = (int *)&v13;
        v7 = byte_14005BA15;
        v31 = 1;
        v28 = &v12;
        v11 = *((_BYTE *)v2 + 8);
        v30 = (ULONG *)&v11;
        InitialState = 7;
      }
      else
      {
        Status = -1073741637;
        if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
          goto LABEL_32;
        tlgCreate1Sz_char(v24, "VsmmCxlpQueryFlatMemoryRanges");
        tlgCreate1Sz_char(v25, "onecore\\vm\\vid\\sys\\vsmm\\vsmmcxl.c");
        v13 = 342;
        v31 = 8;
        v26 = (int *)&v13;
        v28 = &v12;
        v19 = (unsigned int)v2[1];
        v30 = (ULONG *)&v19;
        v14 = *v2;
        v32 = &v14;
        InitialState = 8;
        v7 = byte_14005BB01;
        v33 = 4;
      }
      v12 = v8;
      goto LABEL_31;
    }
LABEL_19:
    VidTraceErrorStatusInternal0(
      "VsmmCxlpQueryFlatMemoryRanges",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmcxl.c",
      327,
      (unsigned int)Status);
    goto LABEL_32;
  }
  Status = -1073741670;
  if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
  {
    tlgCreate1Sz_char(v24, "VsmmCxlpQueryFlatMemoryRanges");
    tlgCreate1Sz_char(v25, "onecore\\vm\\vid\\sys\\vsmm\\vsmmcxl.c");
    v14 = 299;
    v26 = &v14;
    v7 = (char *)&word_14005BB5E;
    v12 = -1073741670;
    v28 = &v12;
    v13 = OutputBuffer[1];
    v30 = &v13;
    InitialState = 7;
    v31 = 4;
LABEL_31:
    v27 = 4;
    v29 = 4;
    tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140065110, (unsigned __int8 *)v7, 0, 0, InitialState, &v23);
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
0x1400e7248  mov     [rsp-8+arg_8], rbx
0x1400e724d  mov     [rsp-8+arg_10], rdi
0x1400e7252  push    rbp
0x1400e7253  push    r14
0x1400e7255  push    r15
0x1400e7257  lea     rbp, [rsp-70h]
0x1400e725c  sub     rsp, 170h
0x1400e7263  mov     rax, cs:__security_cookie
0x1400e726a  xor     rax, rsp
0x1400e726d  mov     [rbp+80h+var_20], rax
0x1400e7271  xor     r15d, r15d
0x1400e7274  mov     qword ptr [rbp+80h+ObjectAttributes.Length], 30h ; '0'
0x1400e727c  xorps   xmm0, xmm0
0x1400e727f  mov     qword ptr [rbp+80h+ObjectAttributes.Attributes], 200h
0x1400e7287  xor     eax, eax
0x1400e7289  mov     [rsp+180h+FileHandle], r15
0x1400e728e  mov     r14, rcx
0x1400e7291  mov     [rsp+180h+EventHandle], r15
0x1400e7296  lea     r8, [rbp+80h+ObjectAttributes]; ObjectAttributes
0x1400e729a  mov     [rbp+80h+var_B0], rax
0x1400e729e  mov     edx, 1F0003h; DesiredAccess
0x1400e72a3  mov     qword ptr [rsp+180h+var_110], r15
0x1400e72a8  lea     r9d, [rax+1]; EventType
0x1400e72ac  mov     [rbp+80h+ObjectAttributes.RootDirectory], r15
0x1400e72b0  lea     rcx, [rsp+180h+EventHandle]; EventHandle
0x1400e72b5  mov     [rbp+80h+ObjectAttributes.ObjectName], r15
0x1400e72b9  movups  xmmword ptr [rsp+180h+IoStatusBlock], xmm0
0x1400e72be  mov     edi, r15d
0x1400e72c1  mov     [rsp+180h+InitialState], r15b; InitialState
0x1400e72c6  movups  [rbp+80h+var_C0], xmm0
0x1400e72ca  movdqu  xmmword ptr [rbp+80h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400e72cf  call    cs:__imp_ZwCreateEvent
0x1400e72d6  nop     dword ptr [rax+rax+00h]
0x1400e72db  mov     ebx, eax
0x1400e72dd  test    eax, eax
0x1400e72df  jns     short loc_1400E7302
0x1400e72e1  mov     r9d, eax
0x1400e72e4  lea     rdx, aOnecoreVmVidSy_23; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcxl.c"
0x1400e72eb  mov     r8d, 0E6h
0x1400e72f1  lea     rcx, aVsmmcxlpqueryf; "VsmmCxlpQueryFlatMemoryRanges"
0x1400e72f8  call    VidTraceErrorStatusInternal0
0x1400e72fd  jmp     loc_1400E770A
0x1400e7302  lea     rcx, [rsp+180h+FileHandle]
0x1400e7307  call    VsmmCxlpOpenScmbusCxlDevice
0x1400e730c  mov     ebx, eax
0x1400e730e  test    eax, eax
0x1400e7310  jns     short loc_1400E733E
0x1400e7312  cmp     eax, 0C0000225h
0x1400e7317  jz      loc_1400E76F2
0x1400e731d  mov     r9d, eax
0x1400e7320  lea     rdx, aOnecoreVmVidSy_23; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcxl.c"
0x1400e7327  mov     r8d, 0F0h
0x1400e732d  lea     rcx, aVsmmcxlpqueryf; "VsmmCxlpQueryFlatMemoryRanges"
0x1400e7334  call    VidTraceErrorStatusInternal0
0x1400e7339  jmp     loc_1400E76F2
0x1400e733e  mov     rdx, [rsp+180h+EventHandle]; Event
0x1400e7343  lea     rax, [rsp+180h+var_110]
0x1400e7348  mov     rcx, [rsp+180h+FileHandle]; FileHandle
0x1400e734d  xor     r9d, r9d; ApcContext
0x1400e7350  mov     [rsp+180h+OutputBufferLength], 8; OutputBufferLength
0x1400e7358  xor     r8d, r8d; ApcRoutine
0x1400e735b  mov     [rsp+180h+OutputBuffer], rax; OutputBuffer
0x1400e7360  lea     rax, [rbp+80h+var_C0]
0x1400e7364  mov     [rsp+180h+InputBufferLength], 18h; InputBufferLength
0x1400e736c  mov     [rsp+180h+InputBuffer], rax; InputBuffer
0x1400e7371  lea     rax, [rsp+180h+IoStatusBlock]
0x1400e7376  mov     [rsp+180h+IoControlCode], 660000h; IoControlCode
0x1400e737e  mov     qword ptr [rsp+180h+InitialState], rax; IoStatusBlock
0x1400e7383  mov     dword ptr [rbp+80h+var_C0], 1
0x1400e738a  mov     qword ptr [rbp+80h+var_C0+4], 18h
0x1400e7392  mov     dword ptr [rbp+80h+var_C0+0Ch], r15d
0x1400e7396  call    cs:__imp_ZwDeviceIoControlFile
0x1400e739d  nop     dword ptr [rax+rax+00h]
0x1400e73a2  mov     ebx, eax
0x1400e73a4  cmp     eax, 103h
0x1400e73a9  jnz     short loc_1400E73CB
0x1400e73ab  mov     rcx, [rsp+180h+EventHandle]; Handle
0x1400e73b0  xor     r8d, r8d; Timeout
0x1400e73b3  xor     edx, edx; Alertable
0x1400e73b5  call    cs:__imp_ZwWaitForSingleObject
0x1400e73bc  nop     dword ptr [rax+rax+00h]
0x1400e73c1  mov     ebx, eax
0x1400e73c3  test    eax, eax
0x1400e73c5  js      short loc_1400E73CF
0x1400e73c7  mov     ebx, dword ptr [rsp+180h+IoStatusBlock]
0x1400e73cb  test    ebx, ebx
0x1400e73cd  jns     short loc_1400E73F0
0x1400e73cf  mov     r9d, ebx
0x1400e73d2  lea     rdx, aOnecoreVmVidSy_23; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcxl.c"
0x1400e73d9  mov     r8d, 118h
0x1400e73df  lea     rcx, aVsmmcxlpqueryf; "VsmmCxlpQueryFlatMemoryRanges"
0x1400e73e6  call    VidTraceErrorStatusInternal0
0x1400e73eb  jmp     loc_1400E76F2
0x1400e73f0  mov     edx, [rsp+180h+var_110+4]
0x1400e73f4  mov     ecx, 40h ; '@'
0x1400e73f9  mov     r8d, 6D4D6456h
0x1400e73ff  call    cs:__imp_ExAllocatePool2
0x1400e7406  nop     dword ptr [rax+rax+00h]
0x1400e740b  mov     rdi, rax
0x1400e740e  test    rax, rax
0x1400e7411  jnz     loc_1400E74B8
0x1400e7417  mov     eax, cs:dword_140065110
0x1400e741d  mov     ebx, 0C000009Ah
0x1400e7422  cmp     eax, 2
0x1400e7425  jbe     loc_1400E76F2
0x1400e742b  mov     edx, 100h
0x1400e7430  lea     rcx, dword_140065110
0x1400e7437  call    _tlgKeywordOn
0x1400e743c  test    al, al
0x1400e743e  jz      loc_1400E76F2
0x1400e7444  lea     rdx, aVsmmcxlpqueryf; "VsmmCxlpQueryFlatMemoryRanges"
0x1400e744b  lea     rcx, [rbp+80h+var_80]
0x1400e744f  call    _tlgCreate1Sz_char
0x1400e7454  lea     rdx, aOnecoreVmVidSy_23; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcxl.c"
0x1400e745b  lea     rcx, [rbp+80h+var_70]
0x1400e745f  call    _tlgCreate1Sz_char
0x1400e7464  lea     rax, [rsp+180h+var_124]
0x1400e7469  mov     [rsp+180h+var_124], 12Bh
0x1400e7471  mov     [rbp+80h+var_60], rax
0x1400e7475  lea     rdx, word_14005BB5E
0x1400e747c  lea     rax, [rsp+180h+var_12C]
0x1400e7481  mov     [rsp+180h+var_12C], ebx
0x1400e7485  mov     [rbp+80h+var_50], rax
0x1400e7489  mov     eax, [rsp+180h+var_110+4]
0x1400e748d  mov     [rsp+180h+var_128], eax
0x1400e7491  lea     rax, [rsp+180h+var_128]
0x1400e7496  mov     [rbp+80h+var_40], rax
0x1400e749a  lea     rax, [rbp+80h+var_A0]
0x1400e749e  mov     qword ptr [rsp+180h+IoControlCode], rax
0x1400e74a3  mov     dword ptr [rsp+180h+InitialState], 7
0x1400e74ab  mov     [rbp+80h+var_38], 4
0x1400e74b3  jmp     loc_1400E76D0
0x1400e74b8  mov     eax, [rsp+180h+var_110+4]
0x1400e74bc  xor     r9d, r9d; ApcContext
0x1400e74bf  mov     rdx, [rsp+180h+EventHandle]; Event
0x1400e74c4  xor     r8d, r8d; ApcRoutine
0x1400e74c7  mov     rcx, [rsp+180h+FileHandle]; FileHandle
0x1400e74cc  mov     [rsp+180h+OutputBufferLength], eax; OutputBufferLength
0x1400e74d0  lea     rax, [rbp+80h+var_C0]
0x1400e74d4  mov     [rsp+180h+OutputBuffer], rdi; OutputBuffer
0x1400e74d9  mov     [rsp+180h+InputBufferLength], 18h; InputBufferLength
0x1400e74e1  mov     [rsp+180h+InputBuffer], rax; InputBuffer
0x1400e74e6  lea     rax, [rsp+180h+IoStatusBlock]
0x1400e74eb  mov     [rsp+180h+IoControlCode], 660000h; IoControlCode
0x1400e74f3  mov     qword ptr [rsp+180h+InitialState], rax; IoStatusBlock
0x1400e74f8  call    cs:__imp_ZwDeviceIoControlFile
0x1400e74ff  nop     dword ptr [rax+rax+00h]
0x1400e7504  mov     ebx, eax
0x1400e7506  cmp     eax, 103h
0x1400e750b  jnz     short loc_1400E752D
0x1400e750d  mov     rcx, [rsp+180h+EventHandle]; Handle
0x1400e7512  xor     r8d, r8d; Timeout
0x1400e7515  xor     edx, edx; Alertable
0x1400e7517  call    cs:__imp_ZwWaitForSingleObject
0x1400e751e  nop     dword ptr [rax+rax+00h]
0x1400e7523  mov     ebx, eax
0x1400e7525  test    eax, eax
0x1400e7527  js      short loc_1400E7531
0x1400e7529  mov     ebx, dword ptr [rsp+180h+IoStatusBlock]
0x1400e752d  test    ebx, ebx
0x1400e752f  jns     short loc_1400E7552
0x1400e7531  mov     r9d, ebx
0x1400e7534  lea     rdx, aOnecoreVmVidSy_23; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcxl.c"
0x1400e753b  mov     r8d, 147h
0x1400e7541  lea     rcx, aVsmmcxlpqueryf; "VsmmCxlpQueryFlatMemoryRanges"
0x1400e7548  call    VidTraceErrorStatusInternal0
0x1400e754d  jmp     loc_1400E76F2
0x1400e7552  cmp     dword ptr [rdi+4], 38h ; '8'
0x1400e7556  jb      loc_1400E761D
0x1400e755c  cmp     dword ptr [rdi], 1
0x1400e755f  jnz     loc_1400E761D
0x1400e7565  cmp     [rdi+8], r15d
0x1400e7569  jz      loc_1400E760F
0x1400e756f  mov     eax, cs:dword_140065110
0x1400e7575  mov     r8d, 0C00000BBh
0x1400e757b  mov     ebx, r8d
0x1400e757e  cmp     eax, 2
0x1400e7581  jbe     loc_1400E76F2
0x1400e7587  mov     edx, 100h
0x1400e758c  lea     rcx, dword_140065110
0x1400e7593  call    _tlgKeywordOn
0x1400e7598  test    al, al
0x1400e759a  jz      loc_1400E76F2
0x1400e75a0  lea     rdx, aVsmmcxlpqueryf; "VsmmCxlpQueryFlatMemoryRanges"
0x1400e75a7  lea     rcx, [rbp+80h+var_80]
0x1400e75ab  call    _tlgCreate1Sz_char
0x1400e75b0  lea     rdx, aOnecoreVmVidSy_23; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcxl.c"
0x1400e75b7  lea     rcx, [rbp+80h+var_70]
0x1400e75bb  call    _tlgCreate1Sz_char
0x1400e75c0  lea     rax, [rsp+180h+var_128]
0x1400e75c5  mov     [rsp+180h+var_128], 163h
0x1400e75cd  mov     [rbp+80h+var_60], rax
0x1400e75d1  lea     rdx, byte_14005BA15
0x1400e75d8  lea     rax, [rsp+180h+var_12C]
0x1400e75dd  mov     [rbp+80h+var_38], 1
0x1400e75e5  mov     [rbp+80h+var_50], rax
0x1400e75e9  mov     al, [rdi+8]
0x1400e75ec  mov     [rsp+180h+var_130], al
0x1400e75f0  lea     rax, [rsp+180h+var_130]
0x1400e75f5  mov     [rbp+80h+var_40], rax
0x1400e75f9  lea     rax, [rbp+80h+var_A0]
0x1400e75fd  mov     qword ptr [rsp+180h+IoControlCode], rax
0x1400e7602  mov     dword ptr [rsp+180h+InitialState], 7
0x1400e760a  jmp     loc_1400E76CB
0x1400e760f  mov     [r14], rdi
0x1400e7612  mov     ebx, r15d
0x1400e7615  mov     rdi, r15
0x1400e7618  jmp     loc_1400E76F2
0x1400e761d  mov     eax, cs:dword_140065110
0x1400e7623  mov     r8d, 0C00000BBh
0x1400e7629  mov     ebx, r8d
0x1400e762c  cmp     eax, 2
0x1400e762f  jbe     loc_1400E76F2
0x1400e7635  mov     edx, 100h
0x1400e763a  lea     rcx, dword_140065110
0x1400e7641  call    _tlgKeywordOn
0x1400e7646  test    al, al
0x1400e7648  jz      loc_1400E76F2
0x1400e764e  lea     rdx, aVsmmcxlpqueryf; "VsmmCxlpQueryFlatMemoryRanges"
0x1400e7655  lea     rcx, [rbp+80h+var_80]
0x1400e7659  call    _tlgCreate1Sz_char
0x1400e765e  lea     rdx, aOnecoreVmVidSy_23; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcxl.c"
0x1400e7665  lea     rcx, [rbp+80h+var_70]
0x1400e7669  call    _tlgCreate1Sz_char
0x1400e766e  mov     edx, 8
0x1400e7673  mov     [rsp+180h+var_128], 156h
0x1400e767b  lea     rax, [rsp+180h+var_128]
0x1400e7680  mov     [rbp+80h+var_38], rdx
0x1400e7684  mov     [rbp+80h+var_60], rax
0x1400e7688  lea     rax, [rsp+180h+var_12C]
0x1400e768d  mov     [rbp+80h+var_50], rax
0x1400e7691  mov     eax, [rdi+4]
0x1400e7694  mov     [rbp+80h+var_F8], rax
0x1400e7698  lea     rax, [rbp+80h+var_F8]
0x1400e769c  mov     [rbp+80h+var_40], rax
0x1400e76a0  mov     eax, [rdi]
0x1400e76a2  mov     [rsp+180h+var_124], eax
0x1400e76a6  lea     rax, [rsp+180h+var_124]
0x1400e76ab  mov     [rbp+80h+var_30], rax
0x1400e76af  lea     rax, [rbp+80h+var_A0]
0x1400e76b3  mov     qword ptr [rsp+180h+IoControlCode], rax
0x1400e76b8  mov     dword ptr [rsp+180h+InitialState], edx
0x1400e76bc  lea     rdx, byte_14005BB01
0x1400e76c3  mov     [rbp+80h+var_28], 4
0x1400e76cb  mov     [rsp+180h+var_12C], r8d
0x1400e76d0  xor     r9d, r9d
0x1400e76d3  mov     [rbp+80h+var_58], 4
0x1400e76db  xor     r8d, r8d
0x1400e76de  mov     [rbp+80h+var_48], 4
0x1400e76e6  lea     rcx, dword_140065110
0x1400e76ed  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400e76f2  cmp     [rsp+180h+FileHandle], r15
0x1400e76f7  jz      short loc_1400E770A
0x1400e76f9  mov     rcx, [rsp+180h+FileHandle]; Handle
0x1400e76fe  call    cs:__imp_ZwClose
0x1400e7705  nop     dword ptr [rax+rax+00h]
0x1400e770a  mov     rcx, [rsp+180h+EventHandle]; Handle
0x1400e770f  test    rcx, rcx
0x1400e7712  jz      short loc_1400E7720
0x1400e7714  call    cs:__imp_ZwClose
0x1400e771b  nop     dword ptr [rax+rax+00h]
0x1400e7720  test    rdi, rdi
0x1400e7723  jz      short loc_1400E7739
0x1400e7725  mov     edx, 6D4D6456h; Tag
0x1400e772a  mov     rcx, rdi; P
0x1400e772d  call    cs:__imp_ExFreePoolWithTag
0x1400e7734  nop     dword ptr [rax+rax+00h]
0x1400e7739  mov     eax, ebx
0x1400e773b  mov     rcx, [rbp+80h+var_20]
0x1400e773f  xor     rcx, rsp; StackCookie
0x1400e7742  call    __security_check_cookie
0x1400e7747  lea     r11, [rsp+180h+var_10]
0x1400e774f  mov     rbx, [r11+28h]
0x1400e7753  mov     rdi, [r11+30h]
0x1400e7757  mov     rsp, r11
0x1400e775a  pop     r15
0x1400e775c  pop     r14
0x1400e775e  pop     rbp
0x1400e775f  retn
```
