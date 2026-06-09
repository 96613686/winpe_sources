# WimWriteOverlayConfig

- ea: `0x14002bdec`
- end: `0x14002c267`
- name: `WimWriteOverlayConfig`
- size: `1147`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x14002ad28`
- `0x14002b77c`
- `0x14002ba8c`

## callees

- `0x14000d3b8`
- `0x14002b9c0`
- `0x14002bdec`
- `0x14003ca60`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002c247`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c247`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002be3b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002be3b`
- `ntoskrnl!ObfDereferenceObject` at `0x14002c04b`
- `ntoskrnl!ObfDereferenceObject` at `0x14002c0f8`
- `ntoskrnl!ObfDereferenceObject` at `0x14002c1f3`
- `ntoskrnl!ObfDereferenceObject` at `0x14002c21c`
- `ntoskrnl!ObfDereferenceObject` at `0x14002c04b`
- `ntoskrnl!ObfDereferenceObject` at `0x14002c0f8`
- `ntoskrnl!ObfDereferenceObject` at `0x14002c1f3`
- `ntoskrnl!ObfDereferenceObject` at `0x14002c21c`
- `FLTMGR!FltFlushBuffers` at `0x14002bfe1`
- `FLTMGR!FltFlushBuffers` at `0x14002c0d8`
- `FLTMGR!FltFlushBuffers` at `0x14002bfe1`
- `FLTMGR!FltFlushBuffers` at `0x14002c0d8`
- `FLTMGR!FltWriteFile` at `0x14002bf0e`
- `FLTMGR!FltWriteFile` at `0x14002c189`
- `FLTMGR!FltWriteFile` at `0x14002bf0e`
- `FLTMGR!FltWriteFile` at `0x14002c189`
- `FLTMGR!FltSetInformationFile` at `0x14002bf62`
- `FLTMGR!FltSetInformationFile` at `0x14002c03c`
- `FLTMGR!FltSetInformationFile` at `0x14002c1d6`
- `FLTMGR!FltSetInformationFile` at `0x14002bf62`
- `FLTMGR!FltSetInformationFile` at `0x14002c03c`
- `FLTMGR!FltSetInformationFile` at `0x14002c1d6`
- `FLTMGR!FltFsControlFile` at `0x14002bfa0`
- `FLTMGR!FltFsControlFile` at `0x14002bfa0`
- `FLTMGR!FltClose` at `0x14002c05a`
- `FLTMGR!FltClose` at `0x14002c0e8`
- `FLTMGR!FltClose` at `0x14002c207`
- `FLTMGR!FltClose` at `0x14002c231`
- `FLTMGR!FltClose` at `0x14002c05a`
- `FLTMGR!FltClose` at `0x14002c0e8`
- `FLTMGR!FltClose` at `0x14002c207`
- `FLTMGR!FltClose` at `0x14002c231`

## string_xrefs

- `0x14002c084`: `WimOverlay.dat`
- `0x14002be9d`: `WimOverlay.new`
- `0x14002c11a`: `WimOverlay.backup`

## pseudocode

```c
__int64 __fastcall WimWriteOverlayConfig(__int64 a1, void *a2, struct _FILE_OBJECT *a3, void *a4, ULONG Length)
{
  struct _FLT_INSTANCE *v5; // rdi
  char *PoolWithTag; // rsi
  NTSTATUS v11; // ebx
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  int v15; // eax
  __int64 v16; // r15
  PVOID Buffer; // [rsp+20h] [rbp-58h]
  PFILE_OBJECT FileObject; // [rsp+50h] [rbp-28h] BYREF
  HANDLE FileHandle; // [rsp+58h] [rbp-20h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+60h] [rbp-18h] BYREF
  _QWORD FileInformation[2]; // [rsp+68h] [rbp-10h] BYREF
  char v23; // [rsp+C0h] [rbp+48h] BYREF
  ULONG BytesWritten; // [rsp+C8h] [rbp+50h] BYREF
  ULONG LengthReturned; // [rsp+D0h] [rbp+58h] BYREF
  PVOID v26; // [rsp+D8h] [rbp+60h]

  v26 = a4;
  v5 = *(struct _FLT_INSTANCE **)(a1 + 120);
  BytesWritten = 0;
  FileInformation[0] = 0;
  ByteOffset.QuadPart = 0;
  v23 = 0;
  LengthReturned = 0;
  FileHandle = 0;
  FileObject = 0;
  PoolWithTag = (char *)ExAllocatePoolWithTag(PagedPool, 0x30u, 0x66637077u);
  if ( PoolWithTag )
  {
    v15 = WimOpenOverlayConfig(a1, L"WimOverlay.new", 1, &FileHandle, &FileObject);
    v11 = v15;
    if ( v15 >= 0 )
    {
      ByteOffset.QuadPart = 0;
      Buffer = a4;
      v16 = Length;
      v15 = FltWriteFile(v5, FileObject, &ByteOffset, Length, Buffer, 0, &BytesWritten, 0, 0);
      v11 = v15;
      if ( v15 >= 0 )
      {
        FileInformation[0] = v16;
        v11 = FltSetInformationFile(v5, FileObject, FileInformation, 8u, FileEndOfFileInformation);
        if ( v11 < 0 )
          goto LABEL_40;
        v15 = FltFsControlFile(v5, FileObject, 0x9004Fu, 0, 0, 0, 0, &LengthReturned);
        v11 = v15;
        if ( v15 >= 0 )
        {
          v15 = FltFlushBuffers(v5, FileObject);
          v11 = v15;
          if ( v15 >= 0 )
          {
            if ( a2 )
            {
              v23 = 1;
              FltSetInformationFile(v5, a3, &v23, 1u, FileDispositionInformation);
              ObfDereferenceObject(a3);
              FltClose(a2);
              a3 = 0;
              a2 = 0;
            }
            *PoolWithTag = 1;
            *((_QWORD *)PoolWithTag + 1) = 0;
            *((_DWORD *)PoolWithTag + 4) = 28;
            *(_OWORD *)(PoolWithTag + 20) = *(_OWORD *)L"WimOverlay.dat";
            *((_OWORD *)PoolWithTag + 2) = *(_OWORD *)L"rlay.dat";
            v15 = WimRenameOnSystemThread(v5, FileObject, PoolWithTag);
            v11 = v15;
            if ( v15 >= 0 )
            {
              FltFlushBuffers(v5, FileObject);
              FltClose(FileHandle);
              ObfDereferenceObject(FileObject);
              v11 = 0;
              FileHandle = 0;
              FileObject = 0;
              v15 = WimOpenOverlayConfig(a1, L"WimOverlay.backup", 1, &FileHandle, &FileObject);
              if ( v15 >= 0 )
              {
                ByteOffset.QuadPart = 0;
                v15 = FltWriteFile(v5, FileObject, &ByteOffset, v16, v26, 0, &BytesWritten, 0, 0);
                if ( v15 >= 0 )
                {
                  FileInformation[0] = v16;
                  v11 = FltSetInformationFile(v5, FileObject, FileInformation, 8u, FileEndOfFileInformation);
                  if ( v11 < 0 )
                    v11 = 0;
                  goto LABEL_40;
                }
                v12 = WPP_GLOBAL_Control;
                if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                  goto LABEL_40;
                v13 = 25;
              }
              else
              {
                v12 = WPP_GLOBAL_Control;
                if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                  goto LABEL_40;
                v13 = 24;
              }
            }
            else
            {
              v12 = WPP_GLOBAL_Control;
              if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                goto LABEL_40;
              v13 = 23;
            }
          }
          else
          {
            v12 = WPP_GLOBAL_Control;
            if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
              goto LABEL_40;
            v13 = 22;
          }
        }
        else
        {
          v12 = WPP_GLOBAL_Control;
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            goto LABEL_40;
          v13 = 21;
        }
      }
      else
      {
        v12 = WPP_GLOBAL_Control;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          goto LABEL_40;
        v13 = 20;
      }
    }
    else
    {
      v12 = WPP_GLOBAL_Control;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_40;
      v13 = 19;
    }
    v14 = (unsigned int)v15;
    goto LABEL_5;
  }
  v11 = -1073741670;
  v12 = WPP_GLOBAL_Control;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v13 = 18;
    v14 = 3221225626LL;
LABEL_5:
    WPP_SF_d(v12->AttachedDevice, v13, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids, v14);
  }
LABEL_40:
  if ( a3 )
    ObfDereferenceObject(a3);
  if ( a2 )
    FltClose(a2);
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  if ( FileHandle )
    FltClose(FileHandle);
  if ( PoolWithTag )
    ExFreePoolWithTag(PoolWithTag, 0);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14002bdec  mov     [rsp-40h+arg_18], r9
0x14002bdf1  push    rbp
0x14002bdf2  push    rbx
0x14002bdf3  push    rsi
0x14002bdf4  push    rdi
0x14002bdf5  push    r12
0x14002bdf7  push    r13
0x14002bdf9  push    r14
0x14002bdfb  push    r15
0x14002bdfd  mov     rbp, rsp
0x14002be00  sub     rsp, 78h
0x14002be04  mov     rdi, [rcx+78h]
0x14002be08  xor     ebx, ebx
0x14002be0a  mov     r12, r8
0x14002be0d  mov     [rbp+arg_8], ebx
0x14002be10  mov     r14, rdx
0x14002be13  mov     [rbp+FileInformation], rbx
0x14002be17  mov     r13, rcx
0x14002be1a  mov     qword ptr [rbp+ByteOffset], rbx
0x14002be1e  lea     edx, [rbx+30h]; NumberOfBytes
0x14002be21  mov     [rbp+arg_0], bl
0x14002be24  lea     ecx, [rbx+1]; PoolType
0x14002be27  mov     [rbp+LengthReturned], ebx
0x14002be2a  mov     r8d, 66637077h; Tag
0x14002be30  mov     [rbp+FileHandle], rbx
0x14002be34  mov     r15, r9
0x14002be37  mov     [rbp+FileObject], rbx
0x14002be3b  call    cs:__imp_ExAllocatePoolWithTag
0x14002be42  nop     dword ptr [rax+rax+00h]
0x14002be47  mov     rsi, rax
0x14002be4a  test    rax, rax
0x14002be4d  jnz     short loc_14002BE8D
0x14002be4f  mov     ebx, 0C000009Ah
0x14002be54  mov     rcx, cs:WPP_GLOBAL_Control
0x14002be5b  test    dword ptr [rcx+2Ch], 400h
0x14002be62  jz      loc_14002C1EB
0x14002be68  cmp     byte ptr [rcx+29h], 2
0x14002be6c  jb      loc_14002C1EB
0x14002be72  lea     edx, [rax+12h]
0x14002be75  mov     r9d, ebx
0x14002be78  mov     rcx, [rcx+18h]
0x14002be7c  lea     r8, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids
0x14002be83  call    WPP_SF_d
0x14002be88  jmp     loc_14002C1EB
0x14002be8d  lea     rax, [rbp+FileObject]
0x14002be91  mov     r8b, 1
0x14002be94  lea     r9, [rbp+FileHandle]
0x14002be98  mov     [rsp+78h+Buffer], rax
0x14002be9d  lea     rdx, aWimoverlayNew; "WimOverlay.new"
0x14002bea4  mov     rcx, r13
0x14002bea7  call    WimOpenOverlayConfig
0x14002beac  xor     ecx, ecx
0x14002beae  mov     ebx, eax
0x14002beb0  test    eax, eax
0x14002beb2  jns     short loc_14002BEDC
0x14002beb4  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bebb  test    dword ptr [rcx+2Ch], 400h
0x14002bec2  jz      loc_14002C1EB
0x14002bec8  cmp     byte ptr [rcx+29h], 2
0x14002becc  jb      loc_14002C1EB
0x14002bed2  mov     edx, 13h
0x14002bed7  mov     r9d, eax
0x14002beda  jmp     short loc_14002BE78
0x14002bedc  mov     rdx, [rbp+FileObject]; FileObject
0x14002bee0  lea     rax, [rbp+arg_8]
0x14002bee4  mov     [rsp+78h+CallbackContext], rcx; CallbackContext
0x14002bee9  lea     r8, [rbp+ByteOffset]; ByteOffset
0x14002beed  mov     [rsp+78h+CallbackRoutine], rcx; CallbackRoutine
0x14002bef2  mov     [rsp+78h+BytesWritten], rax; BytesWritten
0x14002bef7  mov     [rsp+78h+Flags], ecx; Flags
0x14002befb  mov     qword ptr [rbp+ByteOffset], rcx
0x14002beff  mov     rcx, rdi; InitiatingInstance
0x14002bf02  mov     [rsp+78h+Buffer], r15; Buffer
0x14002bf07  mov     r15d, [rbp+Length]
0x14002bf0b  mov     r9d, r15d; Length
0x14002bf0e  call    cs:__imp_FltWriteFile
0x14002bf15  nop     dword ptr [rax+rax+00h]
0x14002bf1a  mov     ebx, eax
0x14002bf1c  test    eax, eax
0x14002bf1e  jns     short loc_14002BF45
0x14002bf20  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bf27  test    dword ptr [rcx+2Ch], 400h
0x14002bf2e  jz      loc_14002C1EB
0x14002bf34  cmp     byte ptr [rcx+29h], 2
0x14002bf38  jb      loc_14002C1EB
0x14002bf3e  mov     edx, 14h
0x14002bf43  jmp     short loc_14002BED7
0x14002bf45  mov     rdx, [rbp+FileObject]; FileObject
0x14002bf49  lea     r8, [rbp+FileInformation]; FileInformation
0x14002bf4d  mov     r9d, 8; Length
0x14002bf53  mov     [rbp+FileInformation], r15
0x14002bf57  mov     rcx, rdi; Instance
0x14002bf5a  mov     dword ptr [rsp+78h+Buffer], 14h; FileInformationClass
0x14002bf62  call    cs:__imp_FltSetInformationFile
0x14002bf69  nop     dword ptr [rax+rax+00h]
0x14002bf6e  mov     ebx, eax
0x14002bf70  test    eax, eax
0x14002bf72  js      loc_14002C1EB
0x14002bf78  mov     rdx, [rbp+FileObject]; FileObject
0x14002bf7c  lea     rax, [rbp+LengthReturned]
0x14002bf80  mov     [rsp+78h+CallbackRoutine], rax; LengthReturned
0x14002bf85  xor     r9d, r9d; InputBuffer
0x14002bf88  xor     eax, eax
0x14002bf8a  mov     r8d, 9004Fh; FsControlCode
0x14002bf90  mov     dword ptr [rsp+78h+BytesWritten], eax; OutputBufferLength
0x14002bf94  mov     rcx, rdi; Instance
0x14002bf97  mov     qword ptr [rsp+78h+Flags], rax; OutputBuffer
0x14002bf9c  mov     dword ptr [rsp+78h+Buffer], eax; InputBufferLength
0x14002bfa0  call    cs:__imp_FltFsControlFile
0x14002bfa7  nop     dword ptr [rax+rax+00h]
0x14002bfac  mov     ebx, eax
0x14002bfae  test    eax, eax
0x14002bfb0  jns     short loc_14002BFDA
0x14002bfb2  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bfb9  test    dword ptr [rcx+2Ch], 400h
0x14002bfc0  jz      loc_14002C1EB
0x14002bfc6  cmp     byte ptr [rcx+29h], 2
0x14002bfca  jb      loc_14002C1EB
0x14002bfd0  mov     edx, 15h
0x14002bfd5  jmp     loc_14002BED7
0x14002bfda  mov     rdx, [rbp+FileObject]; FileObject
0x14002bfde  mov     rcx, rdi; Instance
0x14002bfe1  call    cs:__imp_FltFlushBuffers
0x14002bfe8  nop     dword ptr [rax+rax+00h]
0x14002bfed  mov     ebx, eax
0x14002bfef  test    eax, eax
0x14002bff1  jns     short loc_14002C01B
0x14002bff3  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bffa  test    dword ptr [rcx+2Ch], 400h
0x14002c001  jz      loc_14002C1EB
0x14002c007  cmp     byte ptr [rcx+29h], 2
0x14002c00b  jb      loc_14002C1EB
0x14002c011  mov     edx, 16h
0x14002c016  jmp     loc_14002BED7
0x14002c01b  test    r14, r14
0x14002c01e  jz      short loc_14002C06C
0x14002c020  mov     r9d, 1; Length
0x14002c026  mov     [rbp+arg_0], 1
0x14002c02a  lea     r8, [rbp+arg_0]; FileInformation
0x14002c02e  mov     dword ptr [rsp+78h+Buffer], 0Dh; FileInformationClass
0x14002c036  mov     rdx, r12; FileObject
0x14002c039  mov     rcx, rdi; Instance
0x14002c03c  call    cs:__imp_FltSetInformationFile
0x14002c043  nop     dword ptr [rax+rax+00h]
0x14002c048  mov     rcx, r12; Object
0x14002c04b  call    cs:__imp_ObfDereferenceObject
0x14002c052  nop     dword ptr [rax+rax+00h]
0x14002c057  mov     rcx, r14; FileHandle
0x14002c05a  call    cs:__imp_FltClose
0x14002c061  nop     dword ptr [rax+rax+00h]
0x14002c066  xor     r12d, r12d
0x14002c069  xor     r14d, r14d
0x14002c06c  mov     byte ptr [rsi], 1
0x14002c06f  mov     r8, rsi
0x14002c072  mov     qword ptr [rsi+8], 0
0x14002c07a  mov     rcx, rdi
0x14002c07d  mov     dword ptr [rsi+10h], 1Ch
0x14002c084  movups  xmm0, xmmword ptr cs:aWimoverlayDat; "WimOverlay.dat"
0x14002c08b  movups  xmmword ptr [rsi+14h], xmm0
0x14002c08f  movups  xmm1, xmmword ptr cs:aWimoverlayDat+0Ch; "rlay.dat"
0x14002c096  movups  xmmword ptr [rsi+20h], xmm1
0x14002c09a  mov     rdx, [rbp+FileObject]
0x14002c09e  call    WimRenameOnSystemThread
0x14002c0a3  mov     ebx, eax
0x14002c0a5  test    eax, eax
0x14002c0a7  jns     short loc_14002C0D1
0x14002c0a9  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c0b0  test    dword ptr [rcx+2Ch], 400h
0x14002c0b7  jz      loc_14002C1EB
0x14002c0bd  cmp     byte ptr [rcx+29h], 2
0x14002c0c1  jb      loc_14002C1EB
0x14002c0c7  mov     edx, 17h
0x14002c0cc  jmp     loc_14002BED7
0x14002c0d1  mov     rdx, [rbp+FileObject]; FileObject
0x14002c0d5  mov     rcx, rdi; Instance
0x14002c0d8  call    cs:__imp_FltFlushBuffers
0x14002c0df  nop     dword ptr [rax+rax+00h]
0x14002c0e4  mov     rcx, [rbp+FileHandle]; FileHandle
0x14002c0e8  call    cs:__imp_FltClose
0x14002c0ef  nop     dword ptr [rax+rax+00h]
0x14002c0f4  mov     rcx, [rbp+FileObject]; Object
0x14002c0f8  call    cs:__imp_ObfDereferenceObject
0x14002c0ff  nop     dword ptr [rax+rax+00h]
0x14002c104  lea     rax, [rbp+FileObject]
0x14002c108  xor     ebx, ebx
0x14002c10a  lea     r9, [rbp+FileHandle]
0x14002c10e  mov     [rsp+78h+Buffer], rax
0x14002c113  mov     r8b, 1
0x14002c116  mov     [rbp+FileHandle], rbx
0x14002c11a  lea     rdx, aWimoverlayBack; "WimOverlay.backup"
0x14002c121  mov     [rbp+FileObject], rbx
0x14002c125  mov     rcx, r13
0x14002c128  call    WimOpenOverlayConfig
0x14002c12d  test    eax, eax
0x14002c12f  jns     short loc_14002C157
0x14002c131  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c138  test    dword ptr [rcx+2Ch], 400h
0x14002c13f  jz      loc_14002C1EB
0x14002c145  cmp     byte ptr [rcx+29h], 2
0x14002c149  jb      loc_14002C1EB
0x14002c14f  lea     edx, [rbx+18h]
0x14002c152  jmp     loc_14002BED7
0x14002c157  mov     rdx, [rbp+FileObject]; FileObject
0x14002c15b  lea     rax, [rbp+arg_8]
0x14002c15f  mov     [rsp+78h+CallbackContext], rbx; CallbackContext
0x14002c164  lea     r8, [rbp+ByteOffset]; ByteOffset
0x14002c168  mov     [rsp+78h+CallbackRoutine], rbx; CallbackRoutine
0x14002c16d  mov     r9d, r15d; Length
0x14002c170  mov     [rsp+78h+BytesWritten], rax; BytesWritten
0x14002c175  mov     rcx, rdi; InitiatingInstance
0x14002c178  mov     rax, [rbp+arg_18]
0x14002c17c  mov     [rsp+78h+Flags], ebx; Flags
0x14002c180  mov     [rsp+78h+Buffer], rax; Buffer
0x14002c185  mov     qword ptr [rbp+ByteOffset], rbx
0x14002c189  call    cs:__imp_FltWriteFile
0x14002c190  nop     dword ptr [rax+rax+00h]
0x14002c195  test    eax, eax
0x14002c197  jns     short loc_14002C1B9
0x14002c199  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c1a0  test    dword ptr [rcx+2Ch], 400h
0x14002c1a7  jz      short loc_14002C1EB
0x14002c1a9  cmp     byte ptr [rcx+29h], 2
0x14002c1ad  jb      short loc_14002C1EB
0x14002c1af  mov     edx, 19h
0x14002c1b4  jmp     loc_14002BED7
0x14002c1b9  mov     rdx, [rbp+FileObject]; FileObject
0x14002c1bd  lea     r8, [rbp+FileInformation]; FileInformation
0x14002c1c1  mov     r9d, 8; Length
0x14002c1c7  mov     [rbp+FileInformation], r15
0x14002c1cb  mov     rcx, rdi; Instance
0x14002c1ce  mov     dword ptr [rsp+78h+Buffer], 14h; FileInformationClass
0x14002c1d6  call    cs:__imp_FltSetInformationFile
0x14002c1dd  nop     dword ptr [rax+rax+00h]
0x14002c1e2  mov     ebx, eax
0x14002c1e4  xor     eax, eax
0x14002c1e6  test    ebx, ebx
0x14002c1e8  cmovs   ebx, eax
0x14002c1eb  test    r12, r12
0x14002c1ee  jz      short loc_14002C1FF
0x14002c1f0  mov     rcx, r12; Object
0x14002c1f3  call    cs:__imp_ObfDereferenceObject
0x14002c1fa  nop     dword ptr [rax+rax+00h]
0x14002c1ff  test    r14, r14
0x14002c202  jz      short loc_14002C213
0x14002c204  mov     rcx, r14; FileHandle
0x14002c207  call    cs:__imp_FltClose
0x14002c20e  nop     dword ptr [rax+rax+00h]
0x14002c213  mov     rcx, [rbp+FileObject]; Object
0x14002c217  test    rcx, rcx
0x14002c21a  jz      short loc_14002C228
0x14002c21c  call    cs:__imp_ObfDereferenceObject
0x14002c223  nop     dword ptr [rax+rax+00h]
0x14002c228  mov     rcx, [rbp+FileHandle]; FileHandle
0x14002c22c  test    rcx, rcx
0x14002c22f  jz      short loc_14002C23D
0x14002c231  call    cs:__imp_FltClose
0x14002c238  nop     dword ptr [rax+rax+00h]
0x14002c23d  test    rsi, rsi
0x14002c240  jz      short loc_14002C253
0x14002c242  xor     edx, edx; Tag
0x14002c244  mov     rcx, rsi; P
0x14002c247  call    cs:__imp_ExFreePoolWithTag
0x14002c24e  nop     dword ptr [rax+rax+00h]
0x14002c253  mov     eax, ebx
0x14002c255  add     rsp, 78h
0x14002c259  pop     r15
0x14002c25b  pop     r14
0x14002c25d  pop     r13
0x14002c25f  pop     r12
0x14002c261  pop     rdi
0x14002c262  pop     rsi
0x14002c263  pop     rbx
0x14002c264  pop     rbp
0x14002c265  retn
```
