# Smb2ShareQueryMDSPathV2

- ea: `0x140064cf8`
- end: `0x140064f37`
- name: `Smb2ShareQueryMDSPathV2`
- size: `575`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140064a74`

## callees

- `0x1400225c4`
- `0x140038490`
- `0x140064cf8`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140064e44`
- `ntoskrnl!ExAllocatePool2` at `0x140064e44`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064e2b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064ea7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064e2b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064ea7`
- `ntoskrnl!ZwCreateEvent` at `0x140064d74`
- `ntoskrnl!ZwCreateEvent` at `0x140064d74`
- `ntoskrnl!ZwWaitForSingleObject` at `0x140064dfd`
- `ntoskrnl!ZwWaitForSingleObject` at `0x140064dfd`
- `ntoskrnl!NtClose` at `0x140064f05`
- `ntoskrnl!NtClose` at `0x140064f05`
- `ntoskrnl!ZwFsControlFile` at `0x140064ddf`
- `ntoskrnl!ZwFsControlFile` at `0x140064ddf`

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
0x140064cf8  mov     [rsp-8+arg_10], rbx
0x140064cfd  push    rbp
0x140064cfe  push    rsi
0x140064cff  push    rdi
0x140064d00  push    r14
0x140064d02  push    r15
0x140064d04  lea     rbp, [rsp-37h]
0x140064d09  sub     rsp, 0B0h
0x140064d10  mov     rax, cs:__security_cookie
0x140064d17  xor     rax, rsp
0x140064d1a  mov     [rbp+57h+var_28], rax
0x140064d1e  xor     eax, eax
0x140064d20  mov     [rbp+57h+EventHandle], 0
0x140064d28  xorps   xmm0, xmm0
0x140064d2b  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140064d33  mov     r15, rdx
0x140064d36  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 200h
0x140064d3e  mov     r14, rcx
0x140064d41  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x140064d45  xorps   xmm1, xmm1
0x140064d48  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140064d4c  movups  [rbp+57h+var_38], xmm0
0x140064d50  xor     r9d, r9d; EventType
0x140064d53  mov     dword ptr [rbp+57h+var_38], 12h
0x140064d5a  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140064d5e  mov     [rsp+0D0h+InitialState], al; InitialState
0x140064d62  mov     edx, 1F0003h; DesiredAccess
0x140064d67  lea     rcx, [rbp+57h+EventHandle]; EventHandle
0x140064d6b  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x140064d6f  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140064d74  call    cs:__imp_ZwCreateEvent
0x140064d7b  nop     dword ptr [rax+rax+00h]
0x140064d80  mov     ebx, eax
0x140064d82  test    eax, eax
0x140064d84  js      loc_140064EBF
0x140064d8a  mov     esi, 544h
0x140064d8f  mov     r8d, 6232534Ch
0x140064d95  mov     edx, esi
0x140064d97  jmp     loc_140064E3F
0x140064d9c  mov     ebx, 0C000009Ah
0x140064da1  jmp     loc_140064EFC
0x140064da6  mov     rdx, [rbp+57h+EventHandle]; Event
0x140064daa  lea     rax, [rbp+57h+var_38]
0x140064dae  mov     rcx, [r14+58h]; FileHandle
0x140064db2  xor     r9d, r9d; ApcContext
0x140064db5  mov     [rsp+0D0h+OutputBufferLength], esi; OutputBufferLength
0x140064db9  xor     r8d, r8d; ApcRoutine
0x140064dbc  mov     [rsp+0D0h+OutputBuffer], rdi; OutputBuffer
0x140064dc1  mov     [rsp+0D0h+InputBufferLength], 10h; InputBufferLength
0x140064dc9  mov     [rsp+0D0h+InputBuffer], rax; InputBuffer
0x140064dce  lea     rax, [rbp+57h+IoStatusBlock]
0x140064dd2  mov     [rsp+0D0h+FsControlCode], 902D4h; FsControlCode
0x140064dda  mov     qword ptr [rsp+0D0h+InitialState], rax; IoStatusBlock
0x140064ddf  call    cs:__imp_ZwFsControlFile
0x140064de6  nop     dword ptr [rax+rax+00h]
0x140064deb  mov     ebx, eax
0x140064ded  cmp     eax, 103h
0x140064df2  jnz     short loc_140064E0C
0x140064df4  mov     rcx, [rbp+57h+EventHandle]; Handle
0x140064df8  xor     r8d, r8d; Timeout
0x140064dfb  xor     edx, edx; Alertable
0x140064dfd  call    cs:__imp_ZwWaitForSingleObject
0x140064e04  nop     dword ptr [rax+rax+00h]
0x140064e09  mov     ebx, dword ptr [rbp+57h+IoStatusBlock]
0x140064e0c  cmp     ebx, 0C0000023h
0x140064e12  jz      short loc_140064E21
0x140064e14  cmp     ebx, 80000005h
0x140064e1a  jnz     short loc_140064E61
0x140064e1c  mov     esi, [rdi+8]
0x140064e1f  jmp     short loc_140064E23
0x140064e21  add     esi, esi
0x140064e23  mov     edx, 6232534Ch; Tag
0x140064e28  mov     rcx, rdi; P
0x140064e2b  call    cs:__imp_ExFreePoolWithTag
0x140064e32  nop     dword ptr [rax+rax+00h]
0x140064e37  mov     edx, esi
0x140064e39  mov     r8d, 6832534Ch
0x140064e3f  mov     ecx, 102h
0x140064e44  call    cs:__imp_ExAllocatePool2
0x140064e4b  nop     dword ptr [rax+rax+00h]
0x140064e50  mov     rdi, rax
0x140064e53  test    rax, rax
0x140064e56  jz      loc_140064D9C
0x140064e5c  jmp     loc_140064DA6
0x140064e61  test    ebx, ebx
0x140064e63  jns     short loc_140064EB5
0x140064e65  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140064e6c  lea     rax, WPP_GLOBAL_Control
0x140064e73  cmp     rcx, rax
0x140064e76  jz      short loc_140064EA2
0x140064e78  mov     eax, [rcx+2Ch]
0x140064e7b  test    al, 1
0x140064e7d  jz      short loc_140064EA2
0x140064e7f  cmp     byte ptr [rcx+29h], 1
0x140064e83  jb      short loc_140064EA2
0x140064e85  mov     rcx, [rcx+18h]
0x140064e89  lea     r8, WPP_4e8015138ece3414973dc97451d118ee_Traceguids
0x140064e90  mov     edx, 1Ah
0x140064e95  mov     qword ptr [rsp+0D0h+InitialState], r14
0x140064e9a  mov     r9d, ebx
0x140064e9d  call    WPP_SF_dq
0x140064ea2  xor     edx, edx; Tag
0x140064ea4  mov     rcx, rdi; P
0x140064ea7  call    cs:__imp_ExFreePoolWithTag
0x140064eae  nop     dword ptr [rax+rax+00h]
0x140064eb3  xor     edi, edi
0x140064eb5  test    rdi, rdi
0x140064eb8  jz      short loc_140064EFC
0x140064eba  mov     [r15], rdi
0x140064ebd  jmp     short loc_140064EFC
0x140064ebf  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140064ec6  lea     rax, WPP_GLOBAL_Control
0x140064ecd  cmp     rcx, rax
0x140064ed0  jz      short loc_140064EFC
0x140064ed2  mov     eax, [rcx+2Ch]
0x140064ed5  test    al, 1
0x140064ed7  jz      short loc_140064EFC
0x140064ed9  cmp     byte ptr [rcx+29h], 1
0x140064edd  jb      short loc_140064EFC
0x140064edf  mov     rcx, [rcx+18h]
0x140064ee3  lea     r8, WPP_4e8015138ece3414973dc97451d118ee_Traceguids
0x140064eea  mov     edx, 1Bh
0x140064eef  mov     qword ptr [rsp+0D0h+InitialState], r14
0x140064ef4  mov     r9d, ebx
0x140064ef7  call    WPP_SF_dq
0x140064efc  mov     rcx, [rbp+57h+EventHandle]; Handle
0x140064f00  test    rcx, rcx
0x140064f03  jz      short loc_140064F11
0x140064f05  call    cs:__imp_NtClose
0x140064f0c  nop     dword ptr [rax+rax+00h]
0x140064f11  mov     eax, ebx
0x140064f13  mov     rcx, [rbp+57h+var_28]
0x140064f17  xor     rcx, rsp; StackCookie
0x140064f1a  call    __security_check_cookie
0x140064f1f  mov     rbx, [rsp+0D0h+arg_10]
0x140064f27  add     rsp, 0B0h
0x140064f2e  pop     r15
0x140064f30  pop     r14
0x140064f32  pop     rdi
0x140064f33  pop     rsi
0x140064f34  pop     rbp
0x140064f35  retn
```
