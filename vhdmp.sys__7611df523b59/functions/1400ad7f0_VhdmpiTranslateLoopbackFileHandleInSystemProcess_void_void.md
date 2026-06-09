# VhdmpiTranslateLoopbackFileHandleInSystemProcess(void *,void * *)

- ea: `0x1400ad7f0`
- end: `0x1400adb0b`
- name: `?VhdmpiTranslateLoopbackFileHandleInSystemProcess@@YAJPEAXPEAPEAX@Z`
- size: `795`
- prototype: `__int64 __fastcall(HANDLE Handle, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400adb20`

## callees

- `0x140023560`
- `0x140035e94`
- `0x14005d7c0`
- `0x1400ad7f0`

## import_xrefs

- `ntoskrnl!ZwFsControlFile` at `0x1400ad8c1`
- `ntoskrnl!ZwFsControlFile` at `0x1400ada33`
- `ntoskrnl!ZwFsControlFile` at `0x1400ad8c1`
- `ntoskrnl!ZwFsControlFile` at `0x1400ada33`
- `ntoskrnl!ZwWaitForSingleObject` at `0x1400ad8de`
- `ntoskrnl!ZwWaitForSingleObject` at `0x1400ada51`
- `ntoskrnl!ZwWaitForSingleObject` at `0x1400ad8de`
- `ntoskrnl!ZwWaitForSingleObject` at `0x1400ada51`
- `ntoskrnl!ZwClose` at `0x1400ada99`
- `ntoskrnl!ZwClose` at `0x1400adabf`
- `ntoskrnl!ZwClose` at `0x1400ada99`
- `ntoskrnl!ZwClose` at `0x1400adabf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400adad8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400adad8`
- `ntoskrnl!ZwOpenFile` at `0x1400ad991`
- `ntoskrnl!ZwOpenFile` at `0x1400ad991`
- `ntoskrnl!ExAllocatePool2` at `0x1400ad86d`
- `ntoskrnl!ExAllocatePool2` at `0x1400ad86d`

## string_xrefs

- `0x1400ad9d0`: `Failed to open a handle to srv: 0x%08x`
- `0x1400ad933`: `VhdmpiTranslateLoopbackFileHandleInSystemProcess`

## pseudocode

```c
__int64 __fastcall VhdmpiTranslateLoopbackFileHandleInSystemProcess(HANDLE Handle, void **a2)
{
  _QWORD *OutputBuffer; // rdi
  NTSTATUS Status; // ebx
  unsigned int v6; // edx
  unsigned __int16 v7; // cx
  char *v8; // rax
  __int128 v9; // xmm0
  __int64 v10; // xmm1_8
  __int64 FsControlCode; // [rsp+28h] [rbp-71h]
  void *FileHandle; // [rsp+50h] [rbp-49h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-41h] BYREF
  _QWORD v15[2]; // [rsp+68h] [rbp-31h] BYREF
  __int128 v16; // [rsp+78h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-11h] BYREF
  __int128 InputBuffer; // [rsp+B8h] [rbp+1Fh] BYREF
  __int128 v19; // [rsp+C8h] [rbp+2Fh]

  v15[0] = 1703960;
  FileHandle = 0;
  v15[1] = L"\\Device\\Srv2";
  InputBuffer = 0;
  v19 = 0;
  v16 = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  OutputBuffer = (_QWORD *)ExAllocatePool2(64, 544, 1849968726);
  if ( !OutputBuffer )
  {
    Status = -1073741670;
    goto LABEL_21;
  }
  Status = ZwFsControlFile(Handle, 0, 0, 0, &IoStatusBlock, 0x140078u, 0, 0, OutputBuffer, 0x220u);
  if ( Status == 259 )
  {
    ZwWaitForSingleObject(Handle, 0, 0);
    Status = IoStatusBlock.Status;
  }
  if ( Status >= 0 )
  {
    ObjectAttributes.ObjectName = (PUNICODE_STRING)v15;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 1600;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    Status = ZwOpenFile(&FileHandle, 0xC0100000, &ObjectAttributes, &IoStatusBlock, 3u, 0x60u);
    if ( Status >= 0 )
    {
      v9 = *(_OWORD *)OutputBuffer;
      v10 = OutputBuffer[2];
      DWORD2(v19) = 0;
      InputBuffer = v9;
      *(_QWORD *)&v19 = v10;
      Status = ZwFsControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x14807Cu, &InputBuffer, 0x20u, &v16, 0x10u);
      if ( Status == 259 )
      {
        ZwWaitForSingleObject(FileHandle, 0, 0);
        Status = IoStatusBlock.Status;
      }
      if ( Status >= 0 )
      {
        ZwClose(FileHandle);
        Status = 0;
        *a2 = (void *)v16;
        FileHandle = 0;
      }
      else if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2048) )
      {
        v7 = 2357;
        v8 = "Failed to get the local handle from srv: 0x%08x";
        goto LABEL_9;
      }
    }
    else if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2048) )
    {
      v7 = 2324;
      v8 = "Failed to open a handle to srv: 0x%08x";
      goto LABEL_9;
    }
  }
  else if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2048) )
  {
    v7 = 2302;
    v8 = "Failed to query the resume key: 0x%08x";
LABEL_9:
    LODWORD(FsControlCode) = Status;
    TraceEvents("VhdmpiTranslateLoopbackFileHandleInSystemProcess", v7, 2u, v6, v8, FsControlCode);
  }
LABEL_21:
  if ( FileHandle )
    ZwClose(FileHandle);
  if ( OutputBuffer )
    ExFreePoolWithTag(OutputBuffer, 0x6E444856u);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1400ad7f0  mov     [rsp-8+arg_10], rbx
0x1400ad7f5  mov     [rsp-8+arg_18], rsi
0x1400ad7fa  push    rbp
0x1400ad7fb  push    rdi
0x1400ad7fc  push    r14
0x1400ad7fe  lea     rbp, [rsp-47h]
0x1400ad803  sub     rsp, 0E0h
0x1400ad80a  mov     rax, cs:__security_cookie
0x1400ad811  xor     rax, rsp
0x1400ad814  mov     [rbp+57h+var_18], rax
0x1400ad818  xorps   xmm0, xmm0
0x1400ad81b  mov     [rbp+57h+var_88], 1A0018h
0x1400ad823  mov     r14, rdx
0x1400ad826  mov     [rbp+57h+FileHandle], 0
0x1400ad82e  mov     rsi, rcx
0x1400ad831  lea     rax, aDeviceSrv2; "\\Device\\Srv2"
0x1400ad838  xorps   xmm1, xmm1
0x1400ad83b  mov     [rbp+57h+var_80], rax
0x1400ad83f  mov     ebx, 220h
0x1400ad844  mov     r8d, 6E444856h
0x1400ad84a  mov     edx, ebx
0x1400ad84c  mov     ecx, 40h ; '@'
0x1400ad851  movups  [rbp+57h+var_38], xmm0
0x1400ad855  movups  [rbp+57h+var_28], xmm0
0x1400ad859  movups  [rbp+57h+var_78], xmm0
0x1400ad85d  movups  xmmword ptr [rbp+57h+var_98], xmm1
0x1400ad861  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1400ad865  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1400ad869  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400ad86d  call    cs:__imp_ExAllocatePool2
0x1400ad874  nop     dword ptr [rax+rax+00h]
0x1400ad879  mov     rdi, rax
0x1400ad87c  test    rax, rax
0x1400ad87f  jnz     short loc_1400AD88B
0x1400ad881  mov     ebx, 0C000009Ah
0x1400ad886  jmp     loc_1400ADAB6
0x1400ad88b  mov     [rsp+0F0h+OutputBufferLength], ebx; OutputBufferLength
0x1400ad88f  lea     rax, [rbp+57h+var_98]
0x1400ad893  mov     [rsp+0F0h+OutputBuffer], rdi; OutputBuffer
0x1400ad898  xor     r9d, r9d; ApcContext
0x1400ad89b  mov     [rsp+0F0h+InputBufferLength], 0; InputBufferLength
0x1400ad8a3  xor     r8d, r8d; ApcRoutine
0x1400ad8a6  mov     [rsp+0F0h+InputBuffer], 0; InputBuffer
0x1400ad8af  xor     edx, edx; Event
0x1400ad8b1  mov     dword ptr [rsp+0F0h+FsControlCode], 140078h; FsControlCode
0x1400ad8b9  mov     rcx, rsi; FileHandle
0x1400ad8bc  mov     [rsp+0F0h+IoStatusBlock], rax; IoStatusBlock
0x1400ad8c1  call    cs:__imp_ZwFsControlFile
0x1400ad8c8  nop     dword ptr [rax+rax+00h]
0x1400ad8cd  mov     ebx, eax
0x1400ad8cf  cmp     eax, 103h
0x1400ad8d4  jnz     short loc_1400AD8ED
0x1400ad8d6  xor     r8d, r8d; Timeout
0x1400ad8d9  xor     edx, edx; Alertable
0x1400ad8db  mov     rcx, rsi; Handle
0x1400ad8de  call    cs:__imp_ZwWaitForSingleObject
0x1400ad8e5  nop     dword ptr [rax+rax+00h]
0x1400ad8ea  mov     ebx, dword ptr [rbp+57h+var_98]
0x1400ad8ed  test    ebx, ebx
0x1400ad8ef  jns     short loc_1400AD94A
0x1400ad8f1  mov     eax, cs:dword_140087708
0x1400ad8f7  cmp     eax, 2
0x1400ad8fa  jbe     loc_1400ADAB6
0x1400ad900  mov     edx, 800h
0x1400ad905  lea     rcx, dword_140087708
0x1400ad90c  call    _tlgKeywordOn
0x1400ad911  test    al, al
0x1400ad913  jz      loc_1400ADAB6
0x1400ad919  mov     ecx, 8FEh
0x1400ad91e  lea     rax, aFailedToQueryT; "Failed to query the resume key: 0x%08x"
0x1400ad925  mov     r9d, edx; int
0x1400ad928  mov     dword ptr [rsp+0F0h+FsControlCode], ebx; char
0x1400ad92c  mov     edx, ecx; int
0x1400ad92e  mov     [rsp+0F0h+IoStatusBlock], rax; char *
0x1400ad933  lea     rcx, aVhdmpitranslat; "VhdmpiTranslateLoopbackFileHandleInSyst"...
0x1400ad93a  mov     r8d, 2; int
0x1400ad940  call    TraceEvents
0x1400ad945  jmp     loc_1400ADAB6
0x1400ad94a  lea     rax, [rbp+57h+var_88]
0x1400ad94e  mov     dword ptr [rsp+0F0h+FsControlCode], 60h ; '`'; OpenOptions
0x1400ad956  xorps   xmm0, xmm0
0x1400ad959  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400ad95d  lea     r9, [rbp+57h+var_98]; IoStatusBlock
0x1400ad961  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400ad968  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400ad96c  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1400ad974  mov     edx, 0C0100000h; DesiredAccess
0x1400ad979  mov     [rbp+57h+ObjectAttributes.Attributes], 640h
0x1400ad980  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1400ad984  mov     dword ptr [rsp+0F0h+IoStatusBlock], 3; ShareAccess
0x1400ad98c  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400ad991  call    cs:__imp_ZwOpenFile
0x1400ad998  nop     dword ptr [rax+rax+00h]
0x1400ad99d  mov     ebx, eax
0x1400ad99f  test    eax, eax
0x1400ad9a1  jns     short loc_1400AD9DC
0x1400ad9a3  mov     eax, cs:dword_140087708
0x1400ad9a9  cmp     eax, 2
0x1400ad9ac  jbe     loc_1400ADAB6
0x1400ad9b2  mov     edx, 800h
0x1400ad9b7  lea     rcx, dword_140087708
0x1400ad9be  call    _tlgKeywordOn
0x1400ad9c3  test    al, al
0x1400ad9c5  jz      loc_1400ADAB6
0x1400ad9cb  mov     ecx, 914h
0x1400ad9d0  lea     rax, aFailedToOpenAH; "Failed to open a handle to srv: 0x%08x"
0x1400ad9d7  jmp     loc_1400AD925
0x1400ad9dc  movups  xmm0, xmmword ptr [rdi]
0x1400ad9df  lea     rax, [rbp+57h+var_78]
0x1400ad9e3  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1400ad9e7  movsd   xmm1, qword ptr [rdi+10h]
0x1400ad9ec  xor     r9d, r9d; ApcContext
0x1400ad9ef  mov     [rsp+0F0h+OutputBufferLength], 10h; OutputBufferLength
0x1400ad9f7  xor     r8d, r8d; ApcRoutine
0x1400ad9fa  mov     [rsp+0F0h+OutputBuffer], rax; OutputBuffer
0x1400ad9ff  xor     edx, edx; Event
0x1400ada01  mov     [rsp+0F0h+InputBufferLength], 20h ; ' '; InputBufferLength
0x1400ada09  lea     rax, [rbp+57h+var_38]
0x1400ada0d  mov     [rsp+0F0h+InputBuffer], rax; InputBuffer
0x1400ada12  lea     rax, [rbp+57h+var_98]
0x1400ada16  mov     dword ptr [rsp+0F0h+FsControlCode], 14807Ch; FsControlCode
0x1400ada1e  mov     [rsp+0F0h+IoStatusBlock], rax; IoStatusBlock
0x1400ada23  mov     dword ptr [rbp+57h+var_28+8], 0
0x1400ada2a  movups  [rbp+57h+var_38], xmm0
0x1400ada2e  movsd   qword ptr [rbp+57h+var_28], xmm1
0x1400ada33  call    cs:__imp_ZwFsControlFile
0x1400ada3a  nop     dword ptr [rax+rax+00h]
0x1400ada3f  mov     ebx, eax
0x1400ada41  cmp     eax, 103h
0x1400ada46  jnz     short loc_1400ADA60
0x1400ada48  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1400ada4c  xor     r8d, r8d; Timeout
0x1400ada4f  xor     edx, edx; Alertable
0x1400ada51  call    cs:__imp_ZwWaitForSingleObject
0x1400ada58  nop     dword ptr [rax+rax+00h]
0x1400ada5d  mov     ebx, dword ptr [rbp+57h+var_98]
0x1400ada60  test    ebx, ebx
0x1400ada62  jns     short loc_1400ADA95
0x1400ada64  mov     eax, cs:dword_140087708
0x1400ada6a  cmp     eax, 2
0x1400ada6d  jbe     short loc_1400ADAB6
0x1400ada6f  mov     edx, 800h
0x1400ada74  lea     rcx, dword_140087708
0x1400ada7b  call    _tlgKeywordOn
0x1400ada80  test    al, al
0x1400ada82  jz      short loc_1400ADAB6
0x1400ada84  mov     ecx, 935h
0x1400ada89  lea     rax, aFailedToGetThe; "Failed to get the local handle from srv"...
0x1400ada90  jmp     loc_1400AD925
0x1400ada95  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1400ada99  call    cs:__imp_ZwClose
0x1400adaa0  nop     dword ptr [rax+rax+00h]
0x1400adaa5  mov     rax, qword ptr [rbp+57h+var_78]
0x1400adaa9  xor     ebx, ebx
0x1400adaab  mov     [r14], rax
0x1400adaae  mov     [rbp+57h+FileHandle], 0
0x1400adab6  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1400adaba  test    rcx, rcx
0x1400adabd  jz      short loc_1400ADACB
0x1400adabf  call    cs:__imp_ZwClose
0x1400adac6  nop     dword ptr [rax+rax+00h]
0x1400adacb  test    rdi, rdi
0x1400adace  jz      short loc_1400ADAE4
0x1400adad0  mov     edx, 6E444856h; Tag
0x1400adad5  mov     rcx, rdi; P
0x1400adad8  call    cs:__imp_ExFreePoolWithTag
0x1400adadf  nop     dword ptr [rax+rax+00h]
0x1400adae4  mov     eax, ebx
0x1400adae6  mov     rcx, [rbp+57h+var_18]
0x1400adaea  xor     rcx, rsp; StackCookie
0x1400adaed  call    __security_check_cookie
0x1400adaf2  lea     r11, [rsp+0F0h+var_10]
0x1400adafa  mov     rbx, [r11+30h]
0x1400adafe  mov     rsi, [r11+38h]
0x1400adb02  mov     rsp, r11
0x1400adb05  pop     r14
0x1400adb07  pop     rdi
0x1400adb08  pop     rbp
0x1400adb09  retn
```
