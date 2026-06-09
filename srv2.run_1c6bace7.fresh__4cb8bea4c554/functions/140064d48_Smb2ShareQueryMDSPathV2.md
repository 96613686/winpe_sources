# Smb2ShareQueryMDSPathV2

- ea: `0x140064d48`
- end: `0x140064f87`
- name: `Smb2ShareQueryMDSPathV2`
- size: `575`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140064ac4`

## callees

- `0x1400225c4`
- `0x140038490`
- `0x140064d48`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140064e94`
- `ntoskrnl!ExAllocatePool2` at `0x140064e94`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064e7b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064ef7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064e7b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064ef7`
- `ntoskrnl!ZwCreateEvent` at `0x140064dc4`
- `ntoskrnl!ZwCreateEvent` at `0x140064dc4`
- `ntoskrnl!ZwWaitForSingleObject` at `0x140064e4d`
- `ntoskrnl!ZwWaitForSingleObject` at `0x140064e4d`
- `ntoskrnl!NtClose` at `0x140064f55`
- `ntoskrnl!NtClose` at `0x140064f55`
- `ntoskrnl!ZwFsControlFile` at `0x140064e2f`
- `ntoskrnl!ZwFsControlFile` at `0x140064e2f`

## pseudocode

```c
__int64 __fastcall Smb2ShareQueryMDSPathV2(__int64 a1, _QWORD *a2)
{
  NTSTATUS Status; // ebx
  ULONG OutputBufferLength; // esi
  __int64 v6; // r8
  __int64 v7; // rdx
  _DWORD *OutputBuffer; // rax
  _DWORD *v9; // rdi
  void *EventHandle; // [rsp+50h] [rbp-29h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-11h] BYREF
  __int128 InputBuffer; // [rsp+98h] [rbp+1Fh] BYREF

  EventHandle = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 512;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = 0;
  InputBuffer = 0;
  LODWORD(InputBuffer) = 18;
  IoStatusBlock = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  Status = ZwCreateEvent(&EventHandle, 0x1F0003u, &ObjectAttributes, NotificationEvent, 0);
  if ( Status >= 0 )
  {
    OutputBufferLength = 1348;
    v6 = 1647465292;
    v7 = 1348;
    while ( 1 )
    {
      OutputBuffer = (_DWORD *)ExAllocatePool2(258, v7, v6);
      v9 = OutputBuffer;
      if ( !OutputBuffer )
      {
        Status = -1073741670;
        goto LABEL_25;
      }
      Status = ZwFsControlFile(
                 *(HANDLE *)(a1 + 88),
                 EventHandle,
                 0,
                 0,
                 &IoStatusBlock,
                 0x902D4u,
                 &InputBuffer,
                 0x10u,
                 OutputBuffer,
                 OutputBufferLength);
      if ( Status == 259 )
      {
        ZwWaitForSingleObject(EventHandle, 0, 0);
        Status = IoStatusBlock.Status;
      }
      if ( Status == -1073741789 )
      {
        OutputBufferLength *= 2;
      }
      else
      {
        if ( Status != -2147483643 )
        {
          if ( Status < 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) )
            {
              WPP_SF_dq(
                WPP_GLOBAL_Control->AttachedDevice,
                26,
                WPP_4e8015138ece3414973dc97451d118ee_Traceguids,
                (unsigned int)Status,
                a1);
            }
            ExFreePoolWithTag(v9, 0);
            v9 = 0;
          }
          if ( v9 )
            *a2 = v9;
          goto LABEL_25;
        }
        OutputBufferLength = v9[2];
      }
      ExFreePoolWithTag(v9, 0x6232534Cu);
      v7 = OutputBufferLength;
      v6 = 1748128588;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_dq(
      WPP_GLOBAL_Control->AttachedDevice,
      27,
      WPP_4e8015138ece3414973dc97451d118ee_Traceguids,
      (unsigned int)Status,
      a1);
  }
LABEL_25:
  if ( EventHandle )
    NtClose(EventHandle);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x140064d48  mov     [rsp-8+arg_10], rbx
0x140064d4d  push    rbp
0x140064d4e  push    rsi
0x140064d4f  push    rdi
0x140064d50  push    r14
0x140064d52  push    r15
0x140064d54  lea     rbp, [rsp-37h]
0x140064d59  sub     rsp, 0B0h
0x140064d60  mov     rax, cs:__security_cookie
0x140064d67  xor     rax, rsp
0x140064d6a  mov     [rbp+57h+var_28], rax
0x140064d6e  xor     eax, eax
0x140064d70  mov     [rbp+57h+EventHandle], 0
0x140064d78  xorps   xmm0, xmm0
0x140064d7b  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140064d83  mov     r15, rdx
0x140064d86  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 200h
0x140064d8e  mov     r14, rcx
0x140064d91  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x140064d95  xorps   xmm1, xmm1
0x140064d98  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140064d9c  movups  [rbp+57h+var_38], xmm0
0x140064da0  xor     r9d, r9d; EventType
0x140064da3  mov     dword ptr [rbp+57h+var_38], 12h
0x140064daa  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140064dae  mov     [rsp+0D0h+InitialState], al; InitialState
0x140064db2  mov     edx, 1F0003h; DesiredAccess
0x140064db7  lea     rcx, [rbp+57h+EventHandle]; EventHandle
0x140064dbb  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x140064dbf  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140064dc4  call    cs:__imp_ZwCreateEvent
0x140064dcb  nop     dword ptr [rax+rax+00h]
0x140064dd0  mov     ebx, eax
0x140064dd2  test    eax, eax
0x140064dd4  js      loc_140064F0F
0x140064dda  mov     esi, 544h
0x140064ddf  mov     r8d, 6232534Ch
0x140064de5  mov     edx, esi
0x140064de7  jmp     loc_140064E8F
0x140064dec  mov     ebx, 0C000009Ah
0x140064df1  jmp     loc_140064F4C
0x140064df6  mov     rdx, [rbp+57h+EventHandle]; Event
0x140064dfa  lea     rax, [rbp+57h+var_38]
0x140064dfe  mov     rcx, [r14+58h]; FileHandle
0x140064e02  xor     r9d, r9d; ApcContext
0x140064e05  mov     [rsp+0D0h+OutputBufferLength], esi; OutputBufferLength
0x140064e09  xor     r8d, r8d; ApcRoutine
0x140064e0c  mov     [rsp+0D0h+OutputBuffer], rdi; OutputBuffer
0x140064e11  mov     [rsp+0D0h+InputBufferLength], 10h; InputBufferLength
0x140064e19  mov     [rsp+0D0h+InputBuffer], rax; InputBuffer
0x140064e1e  lea     rax, [rbp+57h+IoStatusBlock]
0x140064e22  mov     [rsp+0D0h+FsControlCode], 902D4h; FsControlCode
0x140064e2a  mov     qword ptr [rsp+0D0h+InitialState], rax; IoStatusBlock
0x140064e2f  call    cs:__imp_ZwFsControlFile
0x140064e36  nop     dword ptr [rax+rax+00h]
0x140064e3b  mov     ebx, eax
0x140064e3d  cmp     eax, 103h
0x140064e42  jnz     short loc_140064E5C
0x140064e44  mov     rcx, [rbp+57h+EventHandle]; Handle
0x140064e48  xor     r8d, r8d; Timeout
0x140064e4b  xor     edx, edx; Alertable
0x140064e4d  call    cs:__imp_ZwWaitForSingleObject
0x140064e54  nop     dword ptr [rax+rax+00h]
0x140064e59  mov     ebx, dword ptr [rbp+57h+IoStatusBlock]
0x140064e5c  cmp     ebx, 0C0000023h
0x140064e62  jz      short loc_140064E71
0x140064e64  cmp     ebx, 80000005h
0x140064e6a  jnz     short loc_140064EB1
0x140064e6c  mov     esi, [rdi+8]
0x140064e6f  jmp     short loc_140064E73
0x140064e71  add     esi, esi
0x140064e73  mov     edx, 6232534Ch; Tag
0x140064e78  mov     rcx, rdi; P
0x140064e7b  call    cs:__imp_ExFreePoolWithTag
0x140064e82  nop     dword ptr [rax+rax+00h]
0x140064e87  mov     edx, esi
0x140064e89  mov     r8d, 6832534Ch
0x140064e8f  mov     ecx, 102h
0x140064e94  call    cs:__imp_ExAllocatePool2
0x140064e9b  nop     dword ptr [rax+rax+00h]
0x140064ea0  mov     rdi, rax
0x140064ea3  test    rax, rax
0x140064ea6  jz      loc_140064DEC
0x140064eac  jmp     loc_140064DF6
0x140064eb1  test    ebx, ebx
0x140064eb3  jns     short loc_140064F05
0x140064eb5  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140064ebc  lea     rax, WPP_GLOBAL_Control
0x140064ec3  cmp     rcx, rax
0x140064ec6  jz      short loc_140064EF2
0x140064ec8  mov     eax, [rcx+2Ch]
0x140064ecb  test    al, 1
0x140064ecd  jz      short loc_140064EF2
0x140064ecf  cmp     byte ptr [rcx+29h], 1
0x140064ed3  jb      short loc_140064EF2
0x140064ed5  mov     rcx, [rcx+18h]
0x140064ed9  lea     r8, WPP_4e8015138ece3414973dc97451d118ee_Traceguids
0x140064ee0  mov     edx, 1Ah
0x140064ee5  mov     qword ptr [rsp+0D0h+InitialState], r14
0x140064eea  mov     r9d, ebx
0x140064eed  call    WPP_SF_dq
0x140064ef2  xor     edx, edx; Tag
0x140064ef4  mov     rcx, rdi; P
0x140064ef7  call    cs:__imp_ExFreePoolWithTag
0x140064efe  nop     dword ptr [rax+rax+00h]
0x140064f03  xor     edi, edi
0x140064f05  test    rdi, rdi
0x140064f08  jz      short loc_140064F4C
0x140064f0a  mov     [r15], rdi
0x140064f0d  jmp     short loc_140064F4C
0x140064f0f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140064f16  lea     rax, WPP_GLOBAL_Control
0x140064f1d  cmp     rcx, rax
0x140064f20  jz      short loc_140064F4C
0x140064f22  mov     eax, [rcx+2Ch]
0x140064f25  test    al, 1
0x140064f27  jz      short loc_140064F4C
0x140064f29  cmp     byte ptr [rcx+29h], 1
0x140064f2d  jb      short loc_140064F4C
0x140064f2f  mov     rcx, [rcx+18h]
0x140064f33  lea     r8, WPP_4e8015138ece3414973dc97451d118ee_Traceguids
0x140064f3a  mov     edx, 1Bh
0x140064f3f  mov     qword ptr [rsp+0D0h+InitialState], r14
0x140064f44  mov     r9d, ebx
0x140064f47  call    WPP_SF_dq
0x140064f4c  mov     rcx, [rbp+57h+EventHandle]; Handle
0x140064f50  test    rcx, rcx
0x140064f53  jz      short loc_140064F61
0x140064f55  call    cs:__imp_NtClose
0x140064f5c  nop     dword ptr [rax+rax+00h]
0x140064f61  mov     eax, ebx
0x140064f63  mov     rcx, [rbp+57h+var_28]
0x140064f67  xor     rcx, rsp; StackCookie
0x140064f6a  call    __security_check_cookie
0x140064f6f  mov     rbx, [rsp+0D0h+arg_10]
0x140064f77  add     rsp, 0B0h
0x140064f7e  pop     r15
0x140064f80  pop     r14
0x140064f82  pop     rdi
0x140064f83  pop     rsi
0x140064f84  pop     rbp
0x140064f85  retn
```
