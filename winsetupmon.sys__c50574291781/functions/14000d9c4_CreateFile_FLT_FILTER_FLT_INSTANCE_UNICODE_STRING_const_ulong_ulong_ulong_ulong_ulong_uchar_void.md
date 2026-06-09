# CreateFile(_FLT_FILTER *,_FLT_INSTANCE *,_UNICODE_STRING const *,ulong,ulong,ulong,ulong,ulong,uchar,void * *)

- ea: `0x14000d9c4`
- end: `0x14000dc1c`
- name: `?CreateFile@@YAJPEAU_FLT_FILTER@@PEAU_FLT_INSTANCE@@PEBU_UNICODE_STRING@@KKKKKEPEAPEAX@Z`
- size: `600`
- prototype: `__int64 __usercall@<rax>(PFLT_FILTER Filter@<rcx>, PFLT_INSTANCE Instance@<rdx>, const struct _UNICODE_STRING *@<r8>, unsigned int@<r9d>, ULONG, unsigned int, ULONG, ULONG, unsigned __int8, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140002678`
- `0x14000dd90`

## callees

- `0x14000d9c4`
- `0x14000f684`
- `0x14000f900`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14000da1a`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000da1a`
- `ntoskrnl!IoFileObjectType` at `0x14000dadb`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000daff`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000daff`
- `ntoskrnl!ObfDereferenceObject` at `0x14000dbb6`
- `ntoskrnl!ObfDereferenceObject` at `0x14000dbda`
- `ntoskrnl!ObfDereferenceObject` at `0x14000dbb6`
- `ntoskrnl!ObfDereferenceObject` at `0x14000dbda`
- `FLTMGR!FltSetInformationFile` at `0x14000db94`
- `FLTMGR!FltSetInformationFile` at `0x14000db94`
- `FLTMGR!FltClose` at `0x14000dbef`
- `FLTMGR!FltClose` at `0x14000dbef`
- `FLTMGR!FltQueryInformationFile` at `0x14000db50`
- `FLTMGR!FltQueryInformationFile` at `0x14000db50`
- `FLTMGR!FltCreateFile` at `0x14000dab0`
- `FLTMGR!FltCreateFile` at `0x14000dab0`

## string_xrefs

- `0x14000da2a`: `WinSetupMon::CreateFile: Not called at PASSIVE_LEVEL, bailing`
- `0x14000dac2`: `WinSetupMon::CreateFile: Failed FltCreateFile for [%wZ] (0x%08X)`
- `0x14000db11`: `WinSetupMon::CreateFile: Failed ObReferenceObjectByHandle for [%wZ] (0x%08X)`
- `0x14000db62`: `WinSetupMon::CreateFile: Failed FltQueryInformationFile(FileStandardInformation) for [%wZ] (0x%08X)`
- `0x14000dba6`: `WinSetupMon::CreateFile: Failed FltSetInformationFile(FilePositionInformation) for [%wZ] (0x%08X)`

## pseudocode

```c
__int64 __fastcall CreateFile(
        PFLT_FILTER Filter,
        PFLT_INSTANCE Instance,
        struct _UNICODE_STRING *a3,
        ACCESS_MASK a4,
        ULONG FileAttributes,
        unsigned int a6,
        ULONG CreateDisposition,
        ULONG CreateOptions,
        unsigned __int8 a9,
        void **a10)
{
  unsigned int v14; // ebx
  NTSTATUS v15; // eax
  NTSTATUS v16; // eax
  NTSTATUS v17; // eax
  NTSTATUS v18; // eax
  PVOID Object; // [rsp+70h] [rbp-79h] BYREF
  void *FileHandle; // [rsp+78h] [rbp-71h] BYREF
  __int64 v22; // [rsp+80h] [rbp-69h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-61h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B8h] [rbp-31h] BYREF
  __int128 FileInformation; // [rsp+C8h] [rbp-21h] BYREF
  __int64 v26; // [rsp+D8h] [rbp-11h]

  FileHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  Object = 0;
  IoStatusBlock = 0;
  if ( KeGetCurrentIrql() )
  {
    v14 = -1073741637;
    WriteLog(0, "WinSetupMon::CreateFile: Not called at PASSIVE_LEVEL, bailing");
    goto LABEL_15;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = a3;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v15 = FltCreateFile(
          Filter,
          Instance,
          &FileHandle,
          a4,
          &ObjectAttributes,
          &IoStatusBlock,
          0,
          FileAttributes,
          7u,
          CreateDisposition,
          CreateOptions,
          0,
          0,
          0);
  v14 = v15;
  if ( v15 >= 0 )
  {
    v16 = ObReferenceObjectByHandle(FileHandle, 0x10000000u, (POBJECT_TYPE)IoFileObjectType, 0, &Object, 0);
    v14 = v16;
    if ( v16 < 0 )
    {
      WriteLog(0, "WinSetupMon::CreateFile: Failed ObReferenceObjectByHandle for [%wZ] (0x%08X)", a3, (unsigned int)v16);
      goto LABEL_15;
    }
    if ( !a9 )
      goto LABEL_14;
    v26 = 0;
    FileInformation = 0;
    v17 = FltQueryInformationFile(Instance, (PFILE_OBJECT)Object, &FileInformation, 0x18u, FileStandardInformation, 0);
    v14 = v17;
    if ( v17 < 0 )
    {
      WriteLog(
        0,
        "WinSetupMon::CreateFile: Failed FltQueryInformationFile(FileStandardInformation) for [%wZ] (0x%08X)",
        a3,
        (unsigned int)v17);
      goto LABEL_15;
    }
    if ( *((__int64 *)&FileInformation + 1) > 0
      && (v22 = *((_QWORD *)&FileInformation + 1),
          v18 = FltSetInformationFile(Instance, (PFILE_OBJECT)Object, &v22, 8u, FilePositionInformation),
          v14 = v18,
          v18 < 0) )
    {
      WriteLog(
        0,
        "WinSetupMon::CreateFile: Failed FltSetInformationFile(FilePositionInformation) for [%wZ] (0x%08X)",
        a3,
        (unsigned int)v18);
    }
    else
    {
LABEL_14:
      ObfDereferenceObject(Object);
      *a10 = FileHandle;
      Object = 0;
      FileHandle = 0;
    }
  }
  else
  {
    WriteLog(0, "WinSetupMon::CreateFile: Failed FltCreateFile for [%wZ] (0x%08X)", a3, (unsigned int)v15);
  }
LABEL_15:
  if ( Object )
    ObfDereferenceObject(Object);
  if ( FileHandle )
    FltClose(FileHandle);
  return v14;
}

```

## disassembly

```asm
0x14000d9c4  push    rbp
0x14000d9c6  push    rbx
0x14000d9c7  push    rsi
0x14000d9c8  push    rdi
0x14000d9c9  push    r12
0x14000d9cb  push    r14
0x14000d9cd  push    r15
0x14000d9cf  lea     rbp, [rsp-7]
0x14000d9d4  sub     rsp, 0F0h
0x14000d9db  mov     rax, cs:__security_cookie
0x14000d9e2  xor     rax, rsp
0x14000d9e5  mov     [rbp+37h+var_40], rax
0x14000d9e9  mov     r14, [rbp+37h+arg_48]
0x14000d9f0  xorps   xmm0, xmm0
0x14000d9f3  xor     r12d, r12d
0x14000d9f6  mov     r15d, r9d
0x14000d9f9  mov     [rbp+37h+FileHandle], r12
0x14000d9fd  mov     rdi, r8
0x14000da00  movups  xmmword ptr [rbp+37h+var_98.Length], xmm0
0x14000da04  mov     [rbp+37h+Object], r12
0x14000da08  mov     rsi, rdx
0x14000da0b  movups  xmmword ptr [rbp+37h+var_98.ObjectName], xmm0
0x14000da0f  mov     rbx, rcx
0x14000da12  movups  xmmword ptr [rbp+37h+var_98.SecurityDescriptor], xmm0
0x14000da16  movups  xmmword ptr [rbp+37h+var_68], xmm0
0x14000da1a  call    cs:__imp_KeGetCurrentIrql
0x14000da21  nop     dword ptr [rax+rax+00h]
0x14000da26  test    al, al
0x14000da28  jz      short loc_14000DA42
0x14000da2a  lea     rdx, aWinsetupmonCre_1; "WinSetupMon::CreateFile: Not called at "...
0x14000da31  xor     ecx, ecx
0x14000da33  mov     ebx, 0C00000BBh
0x14000da38  call    ?WriteLog@@YAXW4LogLevel@@PEBDZZ; WriteLog(LogLevel,char const *,...)
0x14000da3d  jmp     loc_14000DBD1
0x14000da42  mov     eax, [rbp+37h+arg_38]
0x14000da45  lea     r8, [rbp+37h+FileHandle]; FileHandle
0x14000da49  mov     [rsp+120h+Flags], r12d; Flags
0x14000da4e  xorps   xmm0, xmm0
0x14000da51  mov     [rsp+120h+EaLength], r12d; EaLength
0x14000da56  mov     r9d, r15d; DesiredAccess
0x14000da59  mov     [rsp+120h+EaBuffer], r12; EaBuffer
0x14000da5e  mov     rdx, rsi; Instance
0x14000da61  mov     [rsp+120h+CreateOptions], eax; CreateOptions
0x14000da65  mov     rcx, rbx; Filter
0x14000da68  mov     eax, [rbp+37h+arg_30]
0x14000da6b  mov     [rsp+120h+CreateDisposition], eax; CreateDisposition
0x14000da6f  mov     eax, [rbp+37h+arg_20]
0x14000da72  mov     [rsp+120h+ShareAccess], 7; ShareAccess
0x14000da7a  mov     [rsp+120h+FileAttributes], eax; FileAttributes
0x14000da7e  lea     rax, [rbp+37h+var_68]
0x14000da82  mov     [rsp+120h+AllocationSize], r12; AllocationSize
0x14000da87  mov     [rsp+120h+IoStatusBlock], rax; IoStatusBlock
0x14000da8c  lea     rax, [rbp+37h+var_98]
0x14000da90  mov     [rsp+120h+ObjectAttributes], rax; ObjectAttributes
0x14000da95  mov     [rbp+37h+var_98.Length], 30h ; '0'
0x14000da9c  mov     [rbp+37h+var_98.RootDirectory], r12
0x14000daa0  mov     [rbp+37h+var_98.Attributes], 240h
0x14000daa7  mov     [rbp+37h+var_98.ObjectName], rdi
0x14000daab  movdqu  xmmword ptr [rbp+37h+var_98.SecurityDescriptor], xmm0
0x14000dab0  call    cs:__imp_FltCreateFile
0x14000dab7  nop     dword ptr [rax+rax+00h]
0x14000dabc  mov     ebx, eax
0x14000dabe  test    eax, eax
0x14000dac0  jns     short loc_14000DADB
0x14000dac2  lea     rdx, aWinsetupmonCre; "WinSetupMon::CreateFile: Failed FltCrea"...
0x14000dac9  mov     r8, rdi
0x14000dacc  mov     r9d, eax
0x14000dacf  xor     ecx, ecx
0x14000dad1  call    ?WriteLog@@YAXW4LogLevel@@PEBDZZ; WriteLog(LogLevel,char const *,...)
0x14000dad6  jmp     loc_14000DBD1
0x14000dadb  mov     r8, cs:__imp_IoFileObjectType
0x14000dae2  lea     rax, [rbp+37h+Object]
0x14000dae6  mov     rcx, [rbp+37h+FileHandle]; Handle
0x14000daea  xor     r9d, r9d; AccessMode
0x14000daed  mov     [rsp+120h+IoStatusBlock], r12; HandleInformation
0x14000daf2  mov     edx, 10000000h; DesiredAccess
0x14000daf7  mov     [rsp+120h+ObjectAttributes], rax; Object
0x14000dafc  mov     r8, [r8]; ObjectType
0x14000daff  call    cs:__imp_ObReferenceObjectByHandle
0x14000db06  nop     dword ptr [rax+rax+00h]
0x14000db0b  mov     ebx, eax
0x14000db0d  test    eax, eax
0x14000db0f  jns     short loc_14000DB1A
0x14000db11  lea     rdx, aWinsetupmonCre_0; "WinSetupMon::CreateFile: Failed ObRefer"...
0x14000db18  jmp     short loc_14000DAC9
0x14000db1a  cmp     [rbp+37h+arg_40], r12b
0x14000db21  jz      loc_14000DBB2
0x14000db27  mov     rdx, [rbp+37h+Object]; FileObject
0x14000db2b  lea     r8, [rbp+37h+FileInformation]; FileInformation
0x14000db2f  xor     eax, eax
0x14000db31  mov     [rsp+120h+IoStatusBlock], r12; LengthReturned
0x14000db36  xorps   xmm0, xmm0
0x14000db39  mov     [rbp+37h+var_48], rax
0x14000db3d  mov     rcx, rsi; Instance
0x14000db40  mov     dword ptr [rsp+120h+ObjectAttributes], 5; FileInformationClass
0x14000db48  movups  [rbp+37h+FileInformation], xmm0
0x14000db4c  lea     r9d, [rax+18h]; Length
0x14000db50  call    cs:__imp_FltQueryInformationFile
0x14000db57  nop     dword ptr [rax+rax+00h]
0x14000db5c  mov     ebx, eax
0x14000db5e  test    eax, eax
0x14000db60  jns     short loc_14000DB6E
0x14000db62  lea     rdx, aWinsetupmonCre_2; "WinSetupMon::CreateFile: Failed FltQuer"...
0x14000db69  jmp     loc_14000DAC9
0x14000db6e  mov     rax, qword ptr [rbp+37h+FileInformation+8]
0x14000db72  test    rax, rax
0x14000db75  jle     short loc_14000DBB2
0x14000db77  mov     rdx, [rbp+37h+Object]; FileObject
0x14000db7b  lea     r8, [rbp+37h+var_A0]; FileInformation
0x14000db7f  mov     r9d, 8; Length
0x14000db85  mov     [rbp+37h+var_A0], rax
0x14000db89  mov     rcx, rsi; Instance
0x14000db8c  mov     dword ptr [rsp+120h+ObjectAttributes], 0Eh; FileInformationClass
0x14000db94  call    cs:__imp_FltSetInformationFile
0x14000db9b  nop     dword ptr [rax+rax+00h]
0x14000dba0  mov     ebx, eax
0x14000dba2  test    eax, eax
0x14000dba4  jns     short loc_14000DBB2
0x14000dba6  lea     rdx, aWinsetupmonCre_3; "WinSetupMon::CreateFile: Failed FltSetI"...
0x14000dbad  jmp     loc_14000DAC9
0x14000dbb2  mov     rcx, [rbp+37h+Object]; Object
0x14000dbb6  call    cs:__imp_ObfDereferenceObject
0x14000dbbd  nop     dword ptr [rax+rax+00h]
0x14000dbc2  mov     rax, [rbp+37h+FileHandle]
0x14000dbc6  mov     [r14], rax
0x14000dbc9  mov     [rbp+37h+Object], r12
0x14000dbcd  mov     [rbp+37h+FileHandle], r12
0x14000dbd1  mov     rcx, [rbp+37h+Object]; Object
0x14000dbd5  test    rcx, rcx
0x14000dbd8  jz      short loc_14000DBE6
0x14000dbda  call    cs:__imp_ObfDereferenceObject
0x14000dbe1  nop     dword ptr [rax+rax+00h]
0x14000dbe6  mov     rcx, [rbp+37h+FileHandle]; FileHandle
0x14000dbea  test    rcx, rcx
0x14000dbed  jz      short loc_14000DBFB
0x14000dbef  call    cs:__imp_FltClose
0x14000dbf6  nop     dword ptr [rax+rax+00h]
0x14000dbfb  mov     eax, ebx
0x14000dbfd  mov     rcx, [rbp+37h+var_40]
0x14000dc01  xor     rcx, rsp; StackCookie
0x14000dc04  call    __security_check_cookie
0x14000dc09  add     rsp, 0F0h
0x14000dc10  pop     r15
0x14000dc12  pop     r14
0x14000dc14  pop     r12
0x14000dc16  pop     rdi
0x14000dc17  pop     rsi
0x14000dc18  pop     rbx
0x14000dc19  pop     rbp
0x14000dc1a  retn
```
