# PgmSetTcpInfo

- ea: `0x14001bcec`
- end: `0x14001c011`
- name: `PgmSetTcpInfo`
- size: `805`
- prototype: `__int64 __fastcall(void *, unsigned int, const void *, unsigned __int16)`
- caller_count: `8`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140002048`
- `0x140004b50`
- `0x140004dc0`
- `0x140005e3c`
- `0x14000a868`
- `0x14000ab60`
- `0x14000ae04`
- `0x140038afc`

## callees

- `0x1400050ac`
- `0x14001bcec`
- `0x14001cdf0`
- `0x14001d000`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x14001be01`
- `ntoskrnl!KeStackAttachProcess` at `0x14001be01`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14001bf99`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14001bf99`
- `ntoskrnl!ZwClose` at `0x14001bf4b`
- `ntoskrnl!ZwClose` at `0x14001bf4b`
- `ntoskrnl!ZwCreateEvent` at `0x14001be5d`
- `ntoskrnl!ZwCreateEvent` at `0x14001be5d`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x14001bebd`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x14001bebd`
- `ntoskrnl!NtWaitForSingleObject` at `0x14001bedc`
- `ntoskrnl!NtWaitForSingleObject` at `0x14001bedc`
- `ntoskrnl!PsGetCurrentProcess` at `0x14001bde1`
- `ntoskrnl!PsGetCurrentProcess` at `0x14001bde1`
- `ntoskrnl!ExAllocatePool2` at `0x14001bd65`
- `ntoskrnl!ExAllocatePool2` at `0x14001bd65`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bfdf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bfdf`

## pseudocode

```c
__int64 __fastcall PgmSetTcpInfo(void *a1, unsigned int a2, const void *a3, unsigned __int16 a4)
{
  size_t v4; // rbx
  int v7; // r13d
  __int64 Pool2; // rax
  void *InputBuffer; // rsi
  char v11; // r12
  unsigned int Status; // ebx
  PDEVICE_OBJECT v13; // rcx
  __int64 v14; // rdx
  void *EventHandle; // [rsp+50h] [rbp-C8h] BYREF
  HANDLE FileHandle; // [rsp+58h] [rbp-C0h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-B8h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+90h] [rbp-88h] BYREF
  struct _KAPC_STATE ApcState; // [rsp+A0h] [rbp-78h] BYREF

  v4 = a4;
  FileHandle = a1;
  EventHandle = 0;
  v7 = a4;
  IoStatusBlock = 0;
  memset(&ApcState, 0, sizeof(ApcState));
  memset(&ObjectAttributes, 0, 44);
  Pool2 = ExAllocatePool2(64, (unsigned int)a4 + 28, 846030672);
  InputBuffer = (void *)Pool2;
  if ( !Pool2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids, 28, v4);
    return 3221225626LL;
  }
  *(_QWORD *)Pool2 = 1025;
  *(_DWORD *)(Pool2 + 16) = a2;
  *(_DWORD *)(Pool2 + 8) = 512;
  *(_DWORD *)(Pool2 + 12) = 512;
  *(_DWORD *)(Pool2 + 20) = v7;
  memmove((void *)(Pool2 + 24), a3, v4);
  if ( (PRKPROCESS)PsGetCurrentProcess() == PgmStaticConfig )
  {
    v11 = 0;
  }
  else
  {
    KeStackAttachProcess(PgmStaticConfig, &ApcState);
    v11 = 1;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  Status = ZwCreateEvent(&EventHandle, 0x1F0003u, &ObjectAttributes, SynchronizationEvent, 0);
  if ( (Status & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids, Status, a2);
    goto LABEL_25;
  }
  Status = ZwDeviceIoControlFile(FileHandle, EventHandle, 0, 0, &IoStatusBlock, 0x128004u, InputBuffer, v7 + 28, 0, 0);
  if ( Status == 259 )
    Status = NtWaitForSingleObject(EventHandle, 0, 0);
  if ( Status )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 )
      goto LABEL_21;
    v14 = 32;
  }
  else
  {
    Status = IoStatusBlock.Status;
    if ( IoStatusBlock.Status >= 0 )
      goto LABEL_21;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 )
      goto LABEL_21;
    v14 = 31;
  }
  WPP_SF_Dd(v13->AttachedDevice, v14, WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids, Status, a2);
LABEL_21:
  ZwClose(EventHandle);
LABEL_25:
  if ( v11 )
    KeUnstackDetachProcess(&ApcState);
  if ( Status )
  {
    Status = -1073741823;
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
  {
    WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids, a2, v7);
  }
  ExFreePoolWithTag(InputBuffer, 0);
  return Status;
}

```

## disassembly

```asm
0x14001bcec  mov     r11, rsp
0x14001bcef  push    rbx
0x14001bcf0  push    rsi
0x14001bcf1  push    rdi
0x14001bcf2  push    r12
0x14001bcf4  push    r13
0x14001bcf6  push    r14
0x14001bcf8  push    r15
0x14001bcfa  sub     rsp, 0E0h
0x14001bd01  mov     rax, cs:__security_cookie
0x14001bd08  xor     rax, rsp
0x14001bd0b  mov     [rsp+118h+var_48], rax
0x14001bd13  xorps   xmm0, xmm0
0x14001bd16  movzx   ebx, r9w
0x14001bd1a  xor     eax, eax
0x14001bd1c  mov     [rsp+118h+FileHandle], rcx
0x14001bd21  mov     rdi, r8
0x14001bd24  mov     [rsp+118h+EventHandle], 0
0x14001bd2d  mov     r15d, edx
0x14001bd30  mov     r8d, 326D6750h
0x14001bd36  movups  xmmword ptr [rsp+118h+ObjectAttributes.ObjectName], xmm0
0x14001bd3b  lea     edx, [rbx+1Ch]
0x14001bd3e  mov     r13d, ebx
0x14001bd41  lea     ecx, [rax+40h]
0x14001bd44  movups  xmmword ptr [rsp+118h+IoStatusBlock], xmm0
0x14001bd4c  movups  xmmword ptr [r11-78h], xmm0
0x14001bd51  movups  xmmword ptr [r11-68h], xmm0
0x14001bd56  movups  xmmword ptr [r11-58h], xmm0
0x14001bd5b  movups  xmmword ptr [rsp+118h+ObjectAttributes.Length], xmm0
0x14001bd60  movups  xmmword ptr [rsp+118h+ObjectAttributes+1Ch], xmm0
0x14001bd65  call    cs:__imp_ExAllocatePool2
0x14001bd6c  nop     dword ptr [rax+rax+00h]
0x14001bd71  mov     rsi, rax
0x14001bd74  test    rax, rax
0x14001bd77  jnz     short loc_14001BDB8
0x14001bd79  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bd80  lea     rdi, WPP_GLOBAL_Control
0x14001bd87  cmp     rcx, rdi
0x14001bd8a  jz      short loc_14001BDAE
0x14001bd8c  mov     eax, [rcx+2Ch]
0x14001bd8f  test    al, 2
0x14001bd91  jz      short loc_14001BDAE
0x14001bd93  mov     rcx, [rcx+18h]
0x14001bd97  lea     edx, [rsi+1Eh]
0x14001bd9a  lea     r9d, [rsi+1Ch]
0x14001bd9e  mov     dword ptr [rsp+118h+InitialState], ebx
0x14001bda2  lea     r8, WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids
0x14001bda9  call    WPP_SF_Dd
0x14001bdae  mov     eax, 0C000009Ah
0x14001bdb3  jmp     loc_14001BFED
0x14001bdb8  mov     qword ptr [rax], 401h
0x14001bdbf  lea     rcx, [rsi+18h]; void *
0x14001bdc3  mov     eax, 200h
0x14001bdc8  mov     [rsi+10h], r15d
0x14001bdcc  mov     r8, rbx; Size
0x14001bdcf  mov     [rsi+8], eax
0x14001bdd2  mov     rdx, rdi; Src
0x14001bdd5  mov     [rsi+0Ch], eax
0x14001bdd8  mov     [rsi+14h], r13d
0x14001bddc  call    memmove
0x14001bde1  call    cs:__imp_PsGetCurrentProcess
0x14001bde8  nop     dword ptr [rax+rax+00h]
0x14001bded  mov     rcx, cs:PgmStaticConfig; PROCESS
0x14001bdf4  cmp     rax, rcx
0x14001bdf7  jz      short loc_14001BE12
0x14001bdf9  lea     rdx, [rsp+118h+ApcState]; ApcState
0x14001be01  call    cs:__imp_KeStackAttachProcess
0x14001be08  nop     dword ptr [rax+rax+00h]
0x14001be0d  mov     r12b, 1
0x14001be10  jmp     short loc_14001BE15
0x14001be12  xor     r12b, r12b
0x14001be15  xorps   xmm0, xmm0
0x14001be18  mov     [rsp+118h+ObjectAttributes.Length], 30h ; '0'
0x14001be20  mov     r9d, 1; EventType
0x14001be26  mov     [rsp+118h+ObjectAttributes.RootDirectory], 0
0x14001be2f  lea     r8, [rsp+118h+ObjectAttributes]; ObjectAttributes
0x14001be34  mov     [rsp+118h+ObjectAttributes.Attributes], 240h
0x14001be3c  mov     edx, 1F0003h; DesiredAccess
0x14001be41  mov     [rsp+118h+ObjectAttributes.ObjectName], 0
0x14001be4a  lea     rcx, [rsp+118h+EventHandle]; EventHandle
0x14001be4f  mov     [rsp+118h+InitialState], 0; InitialState
0x14001be54  movdqu  xmmword ptr [rsp+118h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001be5d  call    cs:__imp_ZwCreateEvent
0x14001be64  nop     dword ptr [rax+rax+00h]
0x14001be69  lea     r14, WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids
0x14001be70  mov     ebx, eax
0x14001be72  test    eax, eax
0x14001be74  js      loc_14001BF59
0x14001be7a  mov     rdx, [rsp+118h+EventHandle]; Event
0x14001be7f  lea     eax, [r13+1Ch]
0x14001be83  mov     rcx, [rsp+118h+FileHandle]; FileHandle
0x14001be88  xor     r9d, r9d; ApcContext
0x14001be8b  mov     [rsp+118h+OutputBufferLength], 0; OutputBufferLength
0x14001be93  xor     r8d, r8d; ApcRoutine
0x14001be96  mov     [rsp+118h+OutputBuffer], 0; OutputBuffer
0x14001be9f  mov     [rsp+118h+InputBufferLength], eax; InputBufferLength
0x14001bea3  lea     rax, [rsp+118h+IoStatusBlock]
0x14001beab  mov     [rsp+118h+InputBuffer], rsi; InputBuffer
0x14001beb0  mov     [rsp+118h+IoControlCode], 128004h; IoControlCode
0x14001beb8  mov     qword ptr [rsp+118h+InitialState], rax; IoStatusBlock
0x14001bebd  call    cs:__imp_ZwDeviceIoControlFile
0x14001bec4  nop     dword ptr [rax+rax+00h]
0x14001bec9  mov     ebx, eax
0x14001becb  cmp     eax, 103h
0x14001bed0  jnz     short loc_14001BEEA
0x14001bed2  mov     rcx, [rsp+118h+EventHandle]; Object
0x14001bed7  xor     r8d, r8d; Timeout
0x14001beda  xor     edx, edx; Alertable
0x14001bedc  call    cs:__imp_NtWaitForSingleObject
0x14001bee3  nop     dword ptr [rax+rax+00h]
0x14001bee8  mov     ebx, eax
0x14001beea  lea     rdi, WPP_GLOBAL_Control
0x14001bef1  test    ebx, ebx
0x14001bef3  jnz     short loc_14001BF1A
0x14001bef5  mov     ebx, dword ptr [rsp+118h+IoStatusBlock]
0x14001befc  test    ebx, ebx
0x14001befe  jns     short loc_14001BF46
0x14001bf00  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bf07  cmp     rcx, rdi
0x14001bf0a  jz      short loc_14001BF46
0x14001bf0c  mov     eax, [rcx+2Ch]
0x14001bf0f  test    al, 2
0x14001bf11  jz      short loc_14001BF46
0x14001bf13  mov     edx, 1Fh
0x14001bf18  jmp     short loc_14001BF32
0x14001bf1a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bf21  cmp     rcx, rdi
0x14001bf24  jz      short loc_14001BF46
0x14001bf26  mov     eax, [rcx+2Ch]
0x14001bf29  test    al, 2
0x14001bf2b  jz      short loc_14001BF46
0x14001bf2d  mov     edx, 20h ; ' '
0x14001bf32  mov     rcx, [rcx+18h]
0x14001bf36  mov     r9d, ebx
0x14001bf39  mov     r8, r14
0x14001bf3c  mov     dword ptr [rsp+118h+InitialState], r15d
0x14001bf41  call    WPP_SF_Dd
0x14001bf46  mov     rcx, [rsp+118h+EventHandle]; Handle
0x14001bf4b  call    cs:__imp_ZwClose
0x14001bf52  nop     dword ptr [rax+rax+00h]
0x14001bf57  jmp     short loc_14001BF8C
0x14001bf59  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bf60  lea     rdi, WPP_GLOBAL_Control
0x14001bf67  cmp     rcx, rdi
0x14001bf6a  jz      short loc_14001BF8C
0x14001bf6c  mov     eax, [rcx+2Ch]
0x14001bf6f  test    al, 2
0x14001bf71  jz      short loc_14001BF8C
0x14001bf73  mov     rcx, [rcx+18h]
0x14001bf77  mov     edx, 21h ; '!'
0x14001bf7c  mov     r9d, ebx
0x14001bf7f  mov     dword ptr [rsp+118h+InitialState], r15d
0x14001bf84  mov     r8, r14
0x14001bf87  call    WPP_SF_Dd
0x14001bf8c  test    r12b, r12b
0x14001bf8f  jz      short loc_14001BFA5
0x14001bf91  lea     rcx, [rsp+118h+ApcState]; ApcState
0x14001bf99  call    cs:__imp_KeUnstackDetachProcess
0x14001bfa0  nop     dword ptr [rax+rax+00h]
0x14001bfa5  test    ebx, ebx
0x14001bfa7  jnz     short loc_14001BFD5
0x14001bfa9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bfb0  cmp     rcx, rdi
0x14001bfb3  jz      short loc_14001BFDA
0x14001bfb5  mov     eax, [rcx+2Ch]
0x14001bfb8  test    al, 4
0x14001bfba  jz      short loc_14001BFDA
0x14001bfbc  mov     rcx, [rcx+18h]
0x14001bfc0  lea     edx, [rbx+22h]
0x14001bfc3  mov     r9d, r15d
0x14001bfc6  mov     dword ptr [rsp+118h+InitialState], r13d
0x14001bfcb  mov     r8, r14
0x14001bfce  call    WPP_SF_Dd
0x14001bfd3  jmp     short loc_14001BFDA
0x14001bfd5  mov     ebx, 0C0000001h
0x14001bfda  xor     edx, edx; Tag
0x14001bfdc  mov     rcx, rsi; P
0x14001bfdf  call    cs:__imp_ExFreePoolWithTag
0x14001bfe6  nop     dword ptr [rax+rax+00h]
0x14001bfeb  mov     eax, ebx
0x14001bfed  mov     rcx, [rsp+118h+var_48]
0x14001bff5  xor     rcx, rsp; StackCookie
0x14001bff8  call    __security_check_cookie
0x14001bffd  add     rsp, 0E0h
0x14001c004  pop     r15
0x14001c006  pop     r14
0x14001c008  pop     r13
0x14001c00a  pop     r12
0x14001c00c  pop     rdi
0x14001c00d  pop     rsi
0x14001c00e  pop     rbx
0x14001c00f  retn
```
