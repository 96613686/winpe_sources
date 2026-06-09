# DxgkpCopyFile(ushort const *,ushort const *)

- ea: `0x140237fc0`
- end: `0x140238371`
- name: `?DxgkpCopyFile@@YAJPEBG0@Z`
- size: `945`
- prototype: `__int64 __fastcall(PCWSTR SourceString, PCWSTR)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1402386bc`

## callees

- `0x1400091f0`
- `0x14000d990`
- `0x14001b9c0`
- `0x140237e7c`
- `0x140237fc0`
- `0x1402384d4`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140238321`
- `ntoskrnl!ZwClose` at `0x14023834b`
- `ntoskrnl!ZwClose` at `0x140238321`
- `ntoskrnl!ZwClose` at `0x14023834b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140237ff0`
- `ntoskrnl!RtlInitUnicodeString` at `0x140238003`
- `ntoskrnl!RtlInitUnicodeString` at `0x140237ff0`
- `ntoskrnl!RtlInitUnicodeString` at `0x140238003`
- `ntoskrnl!ZwReadFile` at `0x140238244`
- `ntoskrnl!ZwReadFile` at `0x140238244`
- `ntoskrnl!ZwCreateFile` at `0x1402380a9`
- `ntoskrnl!ZwCreateFile` at `0x1402381c8`
- `ntoskrnl!ZwCreateFile` at `0x1402380a9`
- `ntoskrnl!ZwCreateFile` at `0x1402381c8`
- `ntoskrnl!ZwWriteFile` at `0x140238282`
- `ntoskrnl!ZwWriteFile` at `0x140238282`
- `watchdog!WdLogSingleEntry0` at `0x14023813b`
- `watchdog!WdLogSingleEntry0` at `0x14023813b`
- `watchdog!WdLogSingleEntry1` at `0x1402380ce`
- `watchdog!WdLogSingleEntry1` at `0x1402381e3`
- `watchdog!WdLogSingleEntry1` at `0x14023829d`
- `watchdog!WdLogSingleEntry1` at `0x1402382d1`
- `watchdog!WdLogSingleEntry1` at `0x1402380ce`
- `watchdog!WdLogSingleEntry1` at `0x1402381e3`
- `watchdog!WdLogSingleEntry1` at `0x14023829d`
- `watchdog!WdLogSingleEntry1` at `0x1402382d1`

## string_xrefs

- `0x14023814c`: `Failed allocate memory for CopyBuffer`
- `0x1402380df`: `Failed ZwCreateFile for source in DxgkpCopyFile: 0x%I64x`
- `0x1402382dd`: `Failed ZwReadFile in DxgkpCopyFile: 0x%I64x`
- `0x1402381ef`: `Failed ZwCreateFile for dest in DxgkpCopyFile: 0x%I64x`
- `0x1402382a9`: `Failed ZwWriteFile in DxgkpCopyFile: 0x%I64x`

## pseudocode

```c
__int64 __fastcall DxgkpCopyFile(PCWSTR SourceString, PCWSTR a2)
{
  NTSTATUS v3; // eax
  __int64 v4; // rdi
  void *v5; // rsi
  NTSTATUS v6; // eax
  const wchar_t *v7; // r9
  NTSTATUS v8; // eax
  NTSTATUS v9; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-59h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-49h] BYREF
  struct _UNICODE_STRING v13; // [rsp+80h] [rbp-39h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-29h] BYREF
  struct _OBJECT_ATTRIBUTES v15; // [rsp+C0h] [rbp+7h] BYREF
  HANDLE Handle; // [rsp+130h] [rbp+77h] BYREF
  void *FileHandle; // [rsp+138h] [rbp+7Fh] BYREF

  DestinationString = 0;
  v13 = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  RtlInitUnicodeString(&v13, a2);
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  *(_QWORD *)&v15.Length = 48;
  *(_QWORD *)&v15.Attributes = 576;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v15.RootDirectory = 0;
  v15.ObjectName = &v13;
  *(_OWORD *)&v15.SecurityDescriptor = 0;
  FileHandle = (void *)-1LL;
  Handle = (HANDLE)-1LL;
  IoStatusBlock = 0;
  v3 = ZwCreateFile(&FileHandle, 0x120089u, &ObjectAttributes, &IoStatusBlock, 0, 0, 7u, 1u, 0x4010u, 0, 0);
  if ( v3 < 0 )
  {
    LODWORD(v4) = 0;
    if ( v3 != -1073741772 )
      LODWORD(v4) = v3;
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 465;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Failed ZwCreateFile for source in DxgkpCopyFile: 0x%I64x",
      (int)v4,
      0,
      0,
      0,
      0);
    return (unsigned int)v4;
  }
  v5 = (void *)operator new[](0x10000, 1265072196, 258);
  if ( !v5 )
  {
    WdLogSingleEntry0(6);
    WdLogGlobalForLineNumber = 473;
    DxgkLogInternalTriageEvent(0, 262145, -1, (unsigned int)L"Failed allocate memory for CopyBuffer", 473, 0, 0, 0, 0);
    LODWORD(v4) = -1073741801;
    goto LABEL_17;
  }
  v6 = ZwCreateFile(&Handle, 0x1F019Fu, &v15, &IoStatusBlock, 0, 0x80u, 7u, 5u, 0x4010u, 0, 0);
  v4 = v6;
  if ( v6 >= 0 )
  {
    LODWORD(v4) = DxgkpCopyAttributes(FileHandle, Handle);
    if ( (int)v4 < 0 )
      goto LABEL_17;
    while ( 1 )
    {
      v8 = ZwReadFile(FileHandle, 0, 0, 0, &IoStatusBlock, v5, 0x10000u, 0, 0);
      v4 = v8;
      if ( v8 < 0 )
        break;
      v9 = ZwWriteFile(Handle, 0, 0, 0, &IoStatusBlock, v5, IoStatusBlock.Information, 0, 0);
      v4 = v9;
      if ( v9 < 0 )
      {
        WdLogSingleEntry1(2);
        v7 = L"Failed ZwWriteFile in DxgkpCopyFile: 0x%I64x";
        WdLogGlobalForLineNumber = 546;
        goto LABEL_16;
      }
    }
    if ( v8 == -1073741807 )
    {
      LODWORD(v4) = 0;
      goto LABEL_17;
    }
    WdLogSingleEntry1(2);
    v7 = L"Failed ZwReadFile in DxgkpCopyFile: 0x%I64x";
    WdLogGlobalForLineNumber = 526;
  }
  else
  {
    WdLogSingleEntry1(2);
    v7 = L"Failed ZwCreateFile for dest in DxgkpCopyFile: 0x%I64x";
    WdLogGlobalForLineNumber = 492;
  }
LABEL_16:
  DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v7, v4, 0, 0, 0, 0);
LABEL_17:
  if ( Handle != (HANDLE)-1LL )
  {
    ZwClose(Handle);
    if ( (int)v4 < 0 )
      DxgkpDeleteFile(a2);
  }
  DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v5);
  if ( FileHandle != (void *)-1LL )
    ZwClose(FileHandle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140237fc0  mov     [rsp-8+arg_0], rbx
0x140237fc5  push    rbp
0x140237fc6  push    rsi
0x140237fc7  push    rdi
0x140237fc8  push    r14
0x140237fca  push    r15
0x140237fcc  lea     rbp, [rsp-37h]
0x140237fd1  sub     rsp, 0F0h
0x140237fd8  mov     r14, rdx
0x140237fdb  xorps   xmm0, xmm0
0x140237fde  mov     rdx, rcx; SourceString
0x140237fe1  xorps   xmm1, xmm1
0x140237fe4  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140237fe8  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140237fec  movups  xmmword ptr [rbp+57h+var_90.Length], xmm1
0x140237ff0  call    cs:__imp_RtlInitUnicodeString
0x140237ff7  nop     dword ptr [rax+rax+00h]
0x140237ffc  mov     rdx, r14; SourceString
0x140237fff  lea     rcx, [rbp+57h+var_90]; DestinationString
0x140238003  call    cs:__imp_RtlInitUnicodeString
0x14023800a  nop     dword ptr [rax+rax+00h]
0x14023800f  xor     r15d, r15d
0x140238012  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14023801a  mov     [rsp+110h+EaLength], r15d; EaLength
0x14023801f  lea     rax, [rbp+57h+DestinationString]
0x140238023  mov     [rsp+110h+EaBuffer], r15; EaBuffer
0x140238028  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14023802c  xorps   xmm0, xmm0
0x14023802f  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140238033  lea     rax, [rbp+57h+var_90]
0x140238037  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x14023803f  mov     edi, 4010h
0x140238044  mov     qword ptr [rbp+57h+var_50.Length], 30h ; '0'
0x14023804c  mov     [rsp+110h+CreateOptions], edi; CreateOptions
0x140238050  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140238054  mov     [rsp+110h+CreateDisposition], 1; CreateDisposition
0x14023805c  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x140238060  mov     [rsp+110h+ShareAccess], 7; ShareAccess
0x140238068  mov     edx, 120089h; DesiredAccess
0x14023806d  mov     [rsp+110h+FileAttributes], r15d; FileAttributes
0x140238072  mov     [rsp+110h+AllocationSize], r15; AllocationSize
0x140238077  mov     qword ptr [rbp+57h+var_50.Attributes], 240h
0x14023807f  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x140238083  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140238088  mov     [rbp+57h+var_50.RootDirectory], r15
0x14023808c  mov     [rbp+57h+var_50.ObjectName], rax
0x140238090  movdqu  xmmword ptr [rbp+57h+var_50.SecurityDescriptor], xmm0
0x140238095  mov     [rbp+57h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x14023809d  mov     [rbp+57h+Handle], 0FFFFFFFFFFFFFFFFh
0x1402380a5  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1402380a9  call    cs:__imp_ZwCreateFile
0x1402380b0  nop     dword ptr [rax+rax+00h]
0x1402380b5  test    eax, eax
0x1402380b7  jns     short loc_140238119
0x1402380b9  cmp     eax, 0C0000034h
0x1402380be  lea     ecx, [r15+2]
0x1402380c2  mov     edi, r15d
0x1402380c5  cmovnz  edi, eax
0x1402380c8  movsxd  rbx, edi
0x1402380cb  mov     rdx, rbx
0x1402380ce  call    cs:__imp_WdLogSingleEntry1
0x1402380d5  nop     dword ptr [rax+rax+00h]
0x1402380da  mov     qword ptr [rsp+110h+CreateOptions], r15
0x1402380df  lea     r9, aFailedZwcreate; "Failed ZwCreateFile for source in Dxgkp"...
0x1402380e6  mov     qword ptr [rsp+110h+CreateDisposition], r15
0x1402380eb  or      r8d, 0FFFFFFFFh
0x1402380ef  mov     qword ptr [rsp+110h+ShareAccess], r15
0x1402380f4  mov     edx, 40000h
0x1402380f9  mov     qword ptr [rsp+110h+FileAttributes], r15
0x1402380fe  xor     ecx, ecx
0x140238100  mov     [rsp+110h+AllocationSize], rbx
0x140238105  mov     cs:WdLogGlobalForLineNumber, 1D1h
0x14023810f  call    DxgkLogInternalTriageEvent
0x140238114  jmp     loc_140238357
0x140238119  mov     ebx, 10000h
0x14023811e  mov     edx, 4B677844h
0x140238123  mov     ecx, ebx
0x140238125  mov     r8d, 102h
0x14023812b  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x140238130  mov     rsi, rax
0x140238133  test    rax, rax
0x140238136  jnz     short loc_14023818C
0x140238138  lea     ecx, [rax+6]
0x14023813b  call    cs:__imp_WdLogSingleEntry0
0x140238142  nop     dword ptr [rax+rax+00h]
0x140238147  mov     qword ptr [rsp+110h+CreateOptions], r15
0x14023814c  lea     r9, aFailedAllocate; "Failed allocate memory for CopyBuffer"
0x140238153  mov     qword ptr [rsp+110h+CreateDisposition], r15
0x140238158  mov     eax, 1D9h
0x14023815d  mov     qword ptr [rsp+110h+ShareAccess], r15
0x140238162  or      r8d, 0FFFFFFFFh
0x140238166  mov     qword ptr [rsp+110h+FileAttributes], r15
0x14023816b  mov     edx, 40001h
0x140238170  xor     ecx, ecx
0x140238172  mov     [rsp+110h+AllocationSize], rax
0x140238177  mov     cs:WdLogGlobalForLineNumber, eax
0x14023817d  call    DxgkLogInternalTriageEvent
0x140238182  mov     edi, 0C0000017h
0x140238187  jmp     loc_140238317
0x14023818c  mov     [rsp+110h+EaLength], r15d; EaLength
0x140238191  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140238195  mov     [rsp+110h+EaBuffer], r15; EaBuffer
0x14023819a  lea     r8, [rbp+57h+var_50]; ObjectAttributes
0x14023819e  mov     [rsp+110h+CreateOptions], edi; CreateOptions
0x1402381a2  lea     rcx, [rbp+57h+Handle]; FileHandle
0x1402381a6  mov     [rsp+110h+CreateDisposition], 5; CreateDisposition
0x1402381ae  mov     edx, 1F019Fh; DesiredAccess
0x1402381b3  mov     [rsp+110h+ShareAccess], 7; ShareAccess
0x1402381bb  mov     [rsp+110h+FileAttributes], 80h; FileAttributes
0x1402381c3  mov     [rsp+110h+AllocationSize], r15; AllocationSize
0x1402381c8  call    cs:__imp_ZwCreateFile
0x1402381cf  nop     dword ptr [rax+rax+00h]
0x1402381d4  movsxd  rdi, eax
0x1402381d7  test    eax, eax
0x1402381d9  jns     short loc_140238205
0x1402381db  mov     rdx, rdi
0x1402381de  mov     ecx, 2
0x1402381e3  call    cs:__imp_WdLogSingleEntry1
0x1402381ea  nop     dword ptr [rax+rax+00h]
0x1402381ef  lea     r9, aFailedZwcreate_0; "Failed ZwCreateFile for dest in DxgkpCo"...
0x1402381f6  mov     cs:WdLogGlobalForLineNumber, 1ECh
0x140238200  jmp     loc_1402382EE
0x140238205  mov     rdx, [rbp+57h+Handle]; void *
0x140238209  mov     rcx, [rbp+57h+FileHandle]; void *
0x14023820d  call    ?DxgkpCopyAttributes@@YAJPEAX0@Z; DxgkpCopyAttributes(void *,void *)
0x140238212  mov     edi, eax
0x140238214  test    eax, eax
0x140238216  js      loc_140238317
0x14023821c  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140238220  lea     rax, [rbp+57h+IoStatusBlock]
0x140238224  mov     qword ptr [rsp+110h+CreateOptions], r15; Key
0x140238229  xor     r9d, r9d; ApcContext
0x14023822c  mov     qword ptr [rsp+110h+CreateDisposition], r15; ByteOffset
0x140238231  xor     r8d, r8d; ApcRoutine
0x140238234  mov     [rsp+110h+ShareAccess], ebx; Length
0x140238238  xor     edx, edx; Event
0x14023823a  mov     qword ptr [rsp+110h+FileAttributes], rsi; Buffer
0x14023823f  mov     [rsp+110h+AllocationSize], rax; IoStatusBlock
0x140238244  call    cs:__imp_ZwReadFile
0x14023824b  nop     dword ptr [rax+rax+00h]
0x140238250  movsxd  rdi, eax
0x140238253  test    eax, eax
0x140238255  js      short loc_1402382BC
0x140238257  mov     eax, dword ptr [rbp+57h+IoStatusBlock.Information]
0x14023825a  xor     r9d, r9d; ApcContext
0x14023825d  mov     rcx, [rbp+57h+Handle]; FileHandle
0x140238261  xor     r8d, r8d; ApcRoutine
0x140238264  mov     qword ptr [rsp+110h+CreateOptions], r15; Key
0x140238269  xor     edx, edx; Event
0x14023826b  mov     qword ptr [rsp+110h+CreateDisposition], r15; ByteOffset
0x140238270  mov     [rsp+110h+ShareAccess], eax; Length
0x140238274  lea     rax, [rbp+57h+IoStatusBlock]
0x140238278  mov     qword ptr [rsp+110h+FileAttributes], rsi; Buffer
0x14023827d  mov     [rsp+110h+AllocationSize], rax; IoStatusBlock
0x140238282  call    cs:__imp_ZwWriteFile
0x140238289  nop     dword ptr [rax+rax+00h]
0x14023828e  movsxd  rdi, eax
0x140238291  test    eax, eax
0x140238293  jns     short loc_14023821C
0x140238295  mov     rdx, rdi
0x140238298  mov     ecx, 2
0x14023829d  call    cs:__imp_WdLogSingleEntry1
0x1402382a4  nop     dword ptr [rax+rax+00h]
0x1402382a9  lea     r9, aFailedZwwritef; "Failed ZwWriteFile in DxgkpCopyFile: 0x"...
0x1402382b0  mov     cs:WdLogGlobalForLineNumber, 222h
0x1402382ba  jmp     short loc_1402382EE
0x1402382bc  cmp     edi, 0C0000011h
0x1402382c2  jnz     short loc_1402382C9
0x1402382c4  mov     edi, r15d
0x1402382c7  jmp     short loc_140238317
0x1402382c9  mov     rdx, rdi
0x1402382cc  mov     ecx, 2
0x1402382d1  call    cs:__imp_WdLogSingleEntry1
0x1402382d8  nop     dword ptr [rax+rax+00h]
0x1402382dd  lea     r9, aFailedZwreadfi; "Failed ZwReadFile in DxgkpCopyFile: 0x%"...
0x1402382e4  mov     cs:WdLogGlobalForLineNumber, 20Eh
0x1402382ee  mov     qword ptr [rsp+110h+CreateOptions], r15
0x1402382f3  or      r8d, 0FFFFFFFFh
0x1402382f7  mov     qword ptr [rsp+110h+CreateDisposition], r15
0x1402382fc  mov     edx, 40000h
0x140238301  mov     qword ptr [rsp+110h+ShareAccess], r15
0x140238306  xor     ecx, ecx
0x140238308  mov     qword ptr [rsp+110h+FileAttributes], r15
0x14023830d  mov     [rsp+110h+AllocationSize], rdi
0x140238312  call    DxgkLogInternalTriageEvent
0x140238317  mov     rcx, [rbp+57h+Handle]; Handle
0x14023831b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14023831f  jz      short loc_140238339
0x140238321  call    cs:__imp_ZwClose
0x140238328  nop     dword ptr [rax+rax+00h]
0x14023832d  test    edi, edi
0x14023832f  jns     short loc_140238339
0x140238331  mov     rcx, r14; SourceString
0x140238334  call    ?DxgkpDeleteFile@@YAJPEBG@Z; DxgkpDeleteFile(ushort const *)
0x140238339  mov     rcx, rsi; void *
0x14023833c  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x140238341  mov     rcx, [rbp+57h+FileHandle]; Handle
0x140238345  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140238349  jz      short loc_140238357
0x14023834b  call    cs:__imp_ZwClose
0x140238352  nop     dword ptr [rax+rax+00h]
0x140238357  mov     rbx, [rsp+110h+arg_0]
0x14023835f  mov     eax, edi
0x140238361  add     rsp, 0F0h
0x140238368  pop     r15
0x14023836a  pop     r14
0x14023836c  pop     rdi
0x14023836d  pop     rsi
0x14023836e  pop     rbp
0x14023836f  retn
```
