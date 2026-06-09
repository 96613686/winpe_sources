# PgmQueryTcpInfo

- ea: `0x14001b8f8`
- end: `0x14001bce6`
- name: `PgmQueryTcpInfo`
- size: `1006`
- prototype: `__int64 __fastcall(void *, __int64, const void *, unsigned int, _QWORD *, ULONG *)`
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140004dc0`
- `0x14000a664`

## callees

- `0x1400050ac`
- `0x140005168`
- `0x14001b8f8`
- `0x14001c688`
- `0x14001cdf0`
- `0x14001d000`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x14001ba0b`
- `ntoskrnl!KeStackAttachProcess` at `0x14001ba0b`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14001bc4f`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14001bc4f`
- `ntoskrnl!ZwClose` at `0x14001bc36`
- `ntoskrnl!ZwClose` at `0x14001bc36`
- `ntoskrnl!ZwCreateEvent` at `0x14001ba6e`
- `ntoskrnl!ZwCreateEvent` at `0x14001ba6e`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x14001bb57`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x14001bb57`
- `ntoskrnl!NtWaitForSingleObject` at `0x14001bb76`
- `ntoskrnl!NtWaitForSingleObject` at `0x14001bb76`
- `ntoskrnl!PsGetCurrentProcess` at `0x14001b9eb`
- `ntoskrnl!PsGetCurrentProcess` at `0x14001b9eb`
- `ntoskrnl!ExAllocatePool2` at `0x14001baf7`
- `ntoskrnl!ExAllocatePool2` at `0x14001baf7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bad6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bcb4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bad6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bcb4`

## pseudocode

```c
__int64 __fastcall PgmQueryTcpInfo(void *a1, __int64 a2, const void *a3, unsigned int a4, _QWORD *a5, ULONG *a6)
{
  void *OutputBuffer; // rsi
  size_t v7; // r10
  unsigned int v8; // r15d
  const void *v9; // r9
  __int64 v10; // rcx
  ULONG OutputBufferLength; // edi
  char v12; // r12
  NTSTATUS v13; // eax
  unsigned int Status; // ebx
  PDEVICE_OBJECT v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 Information_low; // rdx
  void *EventHandle; // [rsp+50h] [rbp-F8h] BYREF
  int v21; // [rsp+58h] [rbp-F0h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-E8h] BYREF
  HANDLE FileHandle; // [rsp+70h] [rbp-D8h]
  _QWORD *v24; // [rsp+78h] [rbp-D0h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-C8h] BYREF
  __int64 InputBuffer; // [rsp+B0h] [rbp-98h] BYREF
  int v27; // [rsp+B8h] [rbp-90h]
  int v28; // [rsp+BCh] [rbp-8Ch]
  int v29; // [rsp+C0h] [rbp-88h]
  __int128 v30; // [rsp+C4h] [rbp-84h] BYREF
  int v31; // [rsp+D4h] [rbp-74h]
  struct _KAPC_STATE ApcState; // [rsp+D8h] [rbp-70h] BYREF

  OutputBuffer = 0;
  v7 = a4;
  v8 = a2;
  FileHandle = a1;
  v9 = a3;
  v10 = 0;
  v21 = v7;
  v24 = a5;
  OutputBufferLength = 0;
  EventHandle = 0;
  IoStatusBlock = 0;
  memset(&ApcState, 0, sizeof(ApcState));
  memset(&ObjectAttributes, 0, 44);
  if ( a5 && a6 && *a6 )
    OutputBufferLength = *a6;
  v31 = 0;
  InputBuffer = 769;
  v27 = 512;
  v28 = 256;
  v29 = a2;
  v30 = 0;
  if ( (_DWORD)v7 && a3 )
    memmove((char *)&v30 + 4, a3, v7);
  if ( (PRKPROCESS)PsGetCurrentProcess(v10, a2, a3, v9) == PgmStaticConfig )
  {
    v12 = 0;
  }
  else
  {
    KeStackAttachProcess(PgmStaticConfig, &ApcState);
    v12 = 1;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v13 = ZwCreateEvent(&EventHandle, 0x1F0003u, &ObjectAttributes, SynchronizationEvent, 0);
  Status = v13;
  if ( v13 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_Dd(
        WPP_GLOBAL_Control->AttachedDevice,
        35,
        WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids,
        (unsigned int)v13,
        v8);
    return Status;
  }
  while ( 1 )
  {
    if ( OutputBuffer )
    {
      ExFreePoolWithTag(OutputBuffer, 0);
      OutputBuffer = 0;
      OutputBufferLength *= 2;
    }
    if ( OutputBufferLength )
    {
      OutputBuffer = (void *)ExAllocatePool2(64, OutputBufferLength, 862807888);
      if ( !OutputBuffer )
        break;
    }
    IoStatusBlock.Status = 0;
    Status = ZwDeviceIoControlFile(
               FileHandle,
               EventHandle,
               0,
               0,
               &IoStatusBlock,
               0x120003u,
               &InputBuffer,
               0x28u,
               OutputBuffer,
               OutputBufferLength);
    if ( Status == 259 )
      Status = NtWaitForSingleObject(EventHandle, 0, 0);
    if ( Status )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 )
        goto LABEL_30;
      v16 = 38;
    }
    else
    {
      Status = IoStatusBlock.Status;
      if ( IoStatusBlock.Status >= 0 )
        goto LABEL_30;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 )
        goto LABEL_30;
      v16 = 37;
    }
    WPP_SF_DDd(
      v15->AttachedDevice,
      v16,
      WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids,
      Status,
      v8,
      OutputBufferLength);
LABEL_30:
    if ( !OutputBufferLength || Status != -2147483643 && Status != -1073741789 )
      goto LABEL_38;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      36,
      WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids,
      OutputBufferLength,
      v8);
  Status = -1073741670;
LABEL_38:
  ZwClose(EventHandle);
  if ( v12 )
    KeUnstackDetachProcess(&ApcState);
  if ( (Status & 0x80000000) != 0 )
  {
    Status = -1073741823;
    if ( OutputBuffer )
      ExFreePoolWithTag(OutputBuffer, 0);
  }
  else
  {
    Information_low = LODWORD(IoStatusBlock.Information);
    if ( OutputBuffer )
    {
      *v24 = OutputBuffer;
      *a6 = Information_low;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
      WPP_SF_Dddd(
        WPP_GLOBAL_Control->AttachedDevice,
        Information_low,
        v17,
        v8,
        v21,
        Information_low,
        OutputBufferLength);
  }
  return Status;
}

```

## disassembly

```asm
0x14001b8f8  mov     r11, rsp
0x14001b8fb  push    rbx
0x14001b8fc  push    rsi
0x14001b8fd  push    rdi
0x14001b8fe  push    r12
0x14001b900  push    r13
0x14001b902  push    r14
0x14001b904  push    r15
0x14001b906  sub     rsp, 110h
0x14001b90d  mov     rax, cs:__security_cookie
0x14001b914  xor     rax, rsp
0x14001b917  mov     [rsp+148h+var_40], rax
0x14001b91f  mov     rax, [rsp+148h+arg_20]
0x14001b927  xorps   xmm0, xmm0
0x14001b92a  mov     r13, [rsp+148h+arg_28]
0x14001b932  xor     esi, esi
0x14001b934  mov     r10d, r9d
0x14001b937  mov     r15d, edx
0x14001b93a  mov     [rsp+148h+FileHandle], rcx
0x14001b93f  mov     r9, r8
0x14001b942  xor     ecx, ecx
0x14001b944  mov     [rsp+148h+var_F0], r10d
0x14001b949  mov     [rsp+148h+var_D0], rax
0x14001b94e  mov     edi, esi
0x14001b950  mov     [rsp+148h+EventHandle], rsi
0x14001b955  movups  xmmword ptr [rsp+148h+ObjectAttributes.ObjectName], xmm0
0x14001b95d  movups  xmmword ptr [rsp+148h+IoStatusBlock], xmm0
0x14001b962  movups  xmmword ptr [r11-70h], xmm0
0x14001b967  movups  xmmword ptr [r11-60h], xmm0
0x14001b96c  movups  xmmword ptr [r11-50h], xmm0
0x14001b971  movups  xmmword ptr [rsp+148h+ObjectAttributes.Length], xmm0
0x14001b979  movups  xmmword ptr [rsp+148h+ObjectAttributes+1Ch], xmm0
0x14001b981  test    rax, rax
0x14001b984  jz      short loc_14001B994
0x14001b986  test    r13, r13
0x14001b989  jz      short loc_14001B994
0x14001b98b  mov     eax, [r13+0]
0x14001b98f  test    eax, eax
0x14001b991  cmovnz  edi, eax
0x14001b994  mov     [rsp+148h+var_74], esi
0x14001b99b  mov     [rsp+148h+var_98], 301h
0x14001b9a7  mov     [rsp+148h+var_90], 200h
0x14001b9b2  mov     [rsp+148h+var_8C], 100h
0x14001b9bd  mov     [rsp+148h+var_88], r15d
0x14001b9c5  movdqu  [rsp+148h+var_84], xmm0
0x14001b9ce  test    r10d, r10d
0x14001b9d1  jz      short loc_14001B9EB
0x14001b9d3  test    r9, r9
0x14001b9d6  jz      short loc_14001B9EB
0x14001b9d8  mov     r8, r10; Size
0x14001b9db  lea     rcx, [rsp+148h+var_84+4]; void *
0x14001b9e3  mov     rdx, r9; Src
0x14001b9e6  call    memmove
0x14001b9eb  call    cs:__imp_PsGetCurrentProcess
0x14001b9f2  nop     dword ptr [rax+rax+00h]
0x14001b9f7  mov     rcx, cs:PgmStaticConfig; PROCESS
0x14001b9fe  cmp     rax, rcx
0x14001ba01  jz      short loc_14001BA1C
0x14001ba03  lea     rdx, [rsp+148h+ApcState]; ApcState
0x14001ba0b  call    cs:__imp_KeStackAttachProcess
0x14001ba12  nop     dword ptr [rax+rax+00h]
0x14001ba17  mov     r12b, 1
0x14001ba1a  jmp     short loc_14001BA1F
0x14001ba1c  mov     r12b, sil
0x14001ba1f  xorps   xmm0, xmm0
0x14001ba22  mov     [rsp+148h+ObjectAttributes.Length], 30h ; '0'
0x14001ba2d  mov     r9d, 1; EventType
0x14001ba33  mov     [rsp+148h+ObjectAttributes.RootDirectory], rsi
0x14001ba3b  lea     r8, [rsp+148h+ObjectAttributes]; ObjectAttributes
0x14001ba43  mov     [rsp+148h+ObjectAttributes.Attributes], 240h
0x14001ba4e  mov     edx, 1F0003h; DesiredAccess
0x14001ba53  mov     [rsp+148h+ObjectAttributes.ObjectName], rsi
0x14001ba5b  lea     rcx, [rsp+148h+EventHandle]; EventHandle
0x14001ba60  mov     [rsp+148h+InitialState], sil; InitialState
0x14001ba65  movdqu  xmmword ptr [rsp+148h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001ba6e  call    cs:__imp_ZwCreateEvent
0x14001ba75  nop     dword ptr [rax+rax+00h]
0x14001ba7a  mov     ebx, eax
0x14001ba7c  test    eax, eax
0x14001ba7e  jns     short loc_14001BAC5
0x14001ba80  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ba87  lea     r14, WPP_GLOBAL_Control
0x14001ba8e  cmp     rcx, r14
0x14001ba91  jz      loc_14001BCC0
0x14001ba97  mov     edx, [rcx+2Ch]
0x14001ba9a  test    dl, 2
0x14001ba9d  jz      loc_14001BCC0
0x14001baa3  mov     rcx, [rcx+18h]
0x14001baa7  lea     r8, WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids
0x14001baae  mov     edx, 23h ; '#'
0x14001bab3  mov     dword ptr [rsp+148h+InitialState], r15d
0x14001bab8  mov     r9d, eax
0x14001babb  call    WPP_SF_Dd
0x14001bac0  jmp     loc_14001BCC0
0x14001bac5  lea     r14, WPP_GLOBAL_Control
0x14001bacc  test    rsi, rsi
0x14001bacf  jz      short loc_14001BAE6
0x14001bad1  xor     edx, edx; Tag
0x14001bad3  mov     rcx, rsi; P
0x14001bad6  call    cs:__imp_ExFreePoolWithTag
0x14001badd  nop     dword ptr [rax+rax+00h]
0x14001bae2  xor     esi, esi
0x14001bae4  add     edi, edi
0x14001bae6  test    edi, edi
0x14001bae8  jz      short loc_14001BB0F
0x14001baea  mov     edx, edi
0x14001baec  mov     ecx, 40h ; '@'
0x14001baf1  mov     r8d, 336D6750h
0x14001baf7  call    cs:__imp_ExAllocatePool2
0x14001bafe  nop     dword ptr [rax+rax+00h]
0x14001bb03  mov     rsi, rax
0x14001bb06  test    rax, rax
0x14001bb09  jz      loc_14001BBFC
0x14001bb0f  mov     rdx, [rsp+148h+EventHandle]; Event
0x14001bb14  lea     rax, [rsp+148h+var_98]
0x14001bb1c  mov     rcx, [rsp+148h+FileHandle]; FileHandle
0x14001bb21  xor     r9d, r9d; ApcContext
0x14001bb24  mov     [rsp+148h+OutputBufferLength], edi; OutputBufferLength
0x14001bb28  xor     r8d, r8d; ApcRoutine
0x14001bb2b  mov     [rsp+148h+OutputBuffer], rsi; OutputBuffer
0x14001bb30  mov     [rsp+148h+InputBufferLength], 28h ; '('; InputBufferLength
0x14001bb38  mov     [rsp+148h+InputBuffer], rax; InputBuffer
0x14001bb3d  lea     rax, [rsp+148h+IoStatusBlock]
0x14001bb42  mov     [rsp+148h+IoControlCode], 120003h; IoControlCode
0x14001bb4a  mov     qword ptr [rsp+148h+InitialState], rax; IoStatusBlock
0x14001bb4f  mov     dword ptr [rsp+148h+IoStatusBlock], 0
0x14001bb57  call    cs:__imp_ZwDeviceIoControlFile
0x14001bb5e  nop     dword ptr [rax+rax+00h]
0x14001bb63  mov     ebx, eax
0x14001bb65  cmp     eax, 103h
0x14001bb6a  jnz     short loc_14001BB84
0x14001bb6c  mov     rcx, [rsp+148h+EventHandle]; Object
0x14001bb71  xor     r8d, r8d; Timeout
0x14001bb74  xor     edx, edx; Alertable
0x14001bb76  call    cs:__imp_NtWaitForSingleObject
0x14001bb7d  nop     dword ptr [rax+rax+00h]
0x14001bb82  mov     ebx, eax
0x14001bb84  test    ebx, ebx
0x14001bb86  jnz     short loc_14001BBAA
0x14001bb88  mov     ebx, dword ptr [rsp+148h+IoStatusBlock]
0x14001bb8c  test    ebx, ebx
0x14001bb8e  jns     short loc_14001BBDE
0x14001bb90  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bb97  cmp     rcx, r14
0x14001bb9a  jz      short loc_14001BBDE
0x14001bb9c  mov     eax, [rcx+2Ch]
0x14001bb9f  test    al, 2
0x14001bba1  jz      short loc_14001BBDE
0x14001bba3  mov     edx, 25h ; '%'
0x14001bba8  jmp     short loc_14001BBC2
0x14001bbaa  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bbb1  cmp     rcx, r14
0x14001bbb4  jz      short loc_14001BBDE
0x14001bbb6  mov     eax, [rcx+2Ch]
0x14001bbb9  test    al, 2
0x14001bbbb  jz      short loc_14001BBDE
0x14001bbbd  mov     edx, 26h ; '&'
0x14001bbc2  mov     rcx, [rcx+18h]
0x14001bbc6  lea     r8, WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids
0x14001bbcd  mov     [rsp+148h+IoControlCode], edi
0x14001bbd1  mov     r9d, ebx
0x14001bbd4  mov     dword ptr [rsp+148h+InitialState], r15d
0x14001bbd9  call    WPP_SF_DDd
0x14001bbde  test    edi, edi
0x14001bbe0  jz      short loc_14001BC31
0x14001bbe2  cmp     ebx, 80000005h
0x14001bbe8  jz      loc_14001BACC
0x14001bbee  cmp     ebx, 0C0000023h
0x14001bbf4  jz      loc_14001BACC
0x14001bbfa  jmp     short loc_14001BC31
0x14001bbfc  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bc03  cmp     rcx, r14
0x14001bc06  jz      short loc_14001BC2C
0x14001bc08  mov     eax, [rcx+2Ch]
0x14001bc0b  test    al, 2
0x14001bc0d  jz      short loc_14001BC2C
0x14001bc0f  mov     rcx, [rcx+18h]
0x14001bc13  lea     r8, WPP_bb24dc9f99d8356a0c4778f616204a55_Traceguids
0x14001bc1a  mov     edx, 24h ; '$'
0x14001bc1f  mov     dword ptr [rsp+148h+InitialState], r15d
0x14001bc24  mov     r9d, edi
0x14001bc27  call    WPP_SF_Dd
0x14001bc2c  mov     ebx, 0C000009Ah
0x14001bc31  mov     rcx, [rsp+148h+EventHandle]; Handle
0x14001bc36  call    cs:__imp_ZwClose
0x14001bc3d  nop     dword ptr [rax+rax+00h]
0x14001bc42  test    r12b, r12b
0x14001bc45  jz      short loc_14001BC5B
0x14001bc47  lea     rcx, [rsp+148h+ApcState]; ApcState
0x14001bc4f  call    cs:__imp_KeUnstackDetachProcess
0x14001bc56  nop     dword ptr [rax+rax+00h]
0x14001bc5b  test    ebx, ebx
0x14001bc5d  js      short loc_14001BCA5
0x14001bc5f  mov     edx, dword ptr [rsp+148h+IoStatusBlock.Information]
0x14001bc63  test    rsi, rsi
0x14001bc66  jz      short loc_14001BC74
0x14001bc68  mov     rax, [rsp+148h+var_D0]
0x14001bc6d  mov     [rax], rsi
0x14001bc70  mov     [r13+0], edx
0x14001bc74  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bc7b  cmp     rcx, r14
0x14001bc7e  jz      short loc_14001BCC0
0x14001bc80  mov     eax, [rcx+2Ch]
0x14001bc83  test    al, 10h
0x14001bc85  jz      short loc_14001BCC0
0x14001bc87  mov     eax, [rsp+148h+var_F0]
0x14001bc8b  mov     r9d, r15d
0x14001bc8e  mov     rcx, [rcx+18h]
0x14001bc92  mov     dword ptr [rsp+148h+InputBuffer], edi
0x14001bc96  mov     [rsp+148h+IoControlCode], edx
0x14001bc9a  mov     dword ptr [rsp+148h+InitialState], eax
0x14001bc9e  call    WPP_SF_Dddd
0x14001bca3  jmp     short loc_14001BCC0
0x14001bca5  mov     ebx, 0C0000001h
0x14001bcaa  test    rsi, rsi
0x14001bcad  jz      short loc_14001BCC0
0x14001bcaf  xor     edx, edx; Tag
0x14001bcb1  mov     rcx, rsi; P
0x14001bcb4  call    cs:__imp_ExFreePoolWithTag
0x14001bcbb  nop     dword ptr [rax+rax+00h]
0x14001bcc0  mov     eax, ebx
0x14001bcc2  mov     rcx, [rsp+148h+var_40]
0x14001bcca  xor     rcx, rsp; StackCookie
0x14001bccd  call    __security_check_cookie
0x14001bcd2  add     rsp, 110h
0x14001bcd9  pop     r15
0x14001bcdb  pop     r14
0x14001bcdd  pop     r13
0x14001bcdf  pop     r12
0x14001bce1  pop     rdi
0x14001bce2  pop     rsi
0x14001bce3  pop     rbx
0x14001bce4  retn
```
