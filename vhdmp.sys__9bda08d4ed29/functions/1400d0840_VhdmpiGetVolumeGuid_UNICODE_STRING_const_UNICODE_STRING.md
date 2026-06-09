# VhdmpiGetVolumeGuid(_UNICODE_STRING const *,_UNICODE_STRING *)

- ea: `0x1400d0840`
- end: `0x1400d0b7f`
- name: `?VhdmpiGetVolumeGuid@@YAJPEBU_UNICODE_STRING@@PEAU1@@Z`
- size: `831`
- prototype: `int(const struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x1400e63f4`

## callees

- `0x14005de00`
- `0x1400d0840`

## import_xrefs

- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400d098c`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400d098c`
- `ntoskrnl!IofCallDriver` at `0x1400d09a8`
- `ntoskrnl!IofCallDriver` at `0x1400d09a8`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400d0b05`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400d0b05`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x1400d08b8`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x1400d08b8`
- `ntoskrnl!ObfDereferenceObject` at `0x1400d0b54`
- `ntoskrnl!ObfDereferenceObject` at `0x1400d0b54`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400d089b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400d089b`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400d09d2`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400d09d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d09f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d0b28`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d0b3f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d09f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d0b28`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d0b3f`
- `ntoskrnl!ExAllocatePool2` at `0x1400d08e4`
- `ntoskrnl!ExAllocatePool2` at `0x1400d0945`
- `ntoskrnl!ExAllocatePool2` at `0x1400d0ada`
- `ntoskrnl!ExAllocatePool2` at `0x1400d08e4`
- `ntoskrnl!ExAllocatePool2` at `0x1400d0945`
- `ntoskrnl!ExAllocatePool2` at `0x1400d0ada`
- `ntoskrnl!KeInitializeEvent` at `0x1400d092f`
- `ntoskrnl!KeInitializeEvent` at `0x1400d092f`

## string_xrefs

- `0x1400d0877`: `\Device\MountPointManager`

## pseudocode

```c
__int64 __fastcall VhdmpiGetVolumeGuid(const struct _UNICODE_STRING *a1, struct _UNICODE_STRING *a2)
{
  NTSTATUS DeviceObjectPointer; // ebx
  ULONG v5; // esi
  __int64 Pool2; // rax
  void *v7; // r14
  size_t Length; // r8
  PWSTR Buffer; // rdx
  ULONG OutputBufferLength; // ebx
  ULONG *OutputBuffer; // rdi
  IRP *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  WCHAR *v15; // rcx
  WCHAR v16; // ax
  WCHAR *v17; // rax
  UNICODE_STRING SourceString; // [rsp+50h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-9h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp+7h] BYREF
  struct _KEVENT Event; // [rsp+80h] [rbp+17h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+E0h] [rbp+77h] BYREF
  PFILE_OBJECT FileObject; // [rsp+E8h] [rbp+7Fh] BYREF

  DeviceObject = 0;
  FileObject = 0;
  DestinationString = 0;
  memset(&Event, 0, sizeof(Event));
  IoStatusBlock = 0;
  SourceString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\MountPointManager");
  DeviceObjectPointer = IoGetDeviceObjectPointer(&DestinationString, 0x80u, &FileObject, &DeviceObject);
  if ( DeviceObjectPointer >= 0 )
  {
    v5 = a1->Length + 24;
    Pool2 = ExAllocatePool2(256, v5, 1984186454);
    v7 = (void *)Pool2;
    if ( Pool2 )
    {
      Length = a1->Length;
      Buffer = a1->Buffer;
      *(_WORD *)(Pool2 + 20) = Length;
      *(_DWORD *)(Pool2 + 16) = 24;
      memmove((void *)(Pool2 + 24), Buffer, Length);
      OutputBufferLength = 2048;
      KeInitializeEvent(&Event, SynchronizationEvent, 0);
      while ( 1 )
      {
        OutputBuffer = (ULONG *)ExAllocatePool2(256, OutputBufferLength, 1984186454);
        if ( !OutputBuffer
          || (v12 = IoBuildDeviceIoControlRequest(
                      0x6D0008u,
                      DeviceObject,
                      v7,
                      v5,
                      OutputBuffer,
                      OutputBufferLength,
                      0,
                      &Event,
                      &IoStatusBlock)) == 0 )
        {
LABEL_37:
          DeviceObjectPointer = -1073741670;
          goto LABEL_38;
        }
        DeviceObjectPointer = IofCallDriver(DeviceObject, v12);
        if ( DeviceObjectPointer == 259 )
        {
          KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
          DeviceObjectPointer = IoStatusBlock.Status;
        }
        if ( DeviceObjectPointer != -2147483643 )
          break;
        OutputBufferLength = *OutputBuffer;
        ExFreePoolWithTag(OutputBuffer, 0x76444856u);
      }
      if ( DeviceObjectPointer >= 0 )
      {
        v13 = 0;
        DeviceObjectPointer = -1071906796;
        while ( (unsigned int)v13 < OutputBuffer[1] )
        {
          v14 = LOWORD(OutputBuffer[6 * v13 + 3]);
          SourceString.MaximumLength = v14;
          SourceString.Length = v14;
          v15 = (WCHAR *)((char *)OutputBuffer + OutputBuffer[6 * v13 + 2]);
          SourceString.Buffer = v15;
          if ( ((_DWORD)v14 == 96 || (_DWORD)v14 == 98 && v15[48] == 92) && *v15 == 92 )
          {
            v16 = v15[1];
            if ( (v16 == 63 || v16 == 92)
              && v15[2] == 63
              && v15[3] == 92
              && v15[4] == 86
              && v15[5] == 111
              && v15[6] == 108
              && v15[7] == 117
              && v15[8] == 109
              && v15[9] == 101
              && v15[10] == 123
              && v15[19] == 45
              && v15[24] == 45
              && v15[29] == 45
              && v15[34] == 45
              && v15[47] == 125 )
            {
              v17 = (WCHAR *)ExAllocatePool2(256, v14, 1984186454);
              a2->Buffer = v17;
              if ( !v17 )
                goto LABEL_37;
              a2->Length = 0;
              a2->MaximumLength = SourceString.MaximumLength;
              RtlCopyUnicodeString(a2, &SourceString);
              DeviceObjectPointer = 0;
              a2->Buffer[1] = 92;
              break;
            }
          }
          v13 = (unsigned int)(v13 + 1);
        }
      }
LABEL_38:
      ExFreePoolWithTag(v7, 0x76444856u);
      if ( OutputBuffer )
        ExFreePoolWithTag(OutputBuffer, 0x76444856u);
    }
    else
    {
      DeviceObjectPointer = -1073741670;
    }
  }
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  return (unsigned int)DeviceObjectPointer;
}

```

## disassembly

```asm
0x1400d0840  mov     [rsp-8+arg_0], rbx
0x1400d0845  mov     [rsp-8+arg_8], rsi
0x1400d084a  push    rbp
0x1400d084b  push    rdi
0x1400d084c  push    r13
0x1400d084e  push    r14
0x1400d0850  push    r15
0x1400d0852  lea     rbp, [rsp-37h]
0x1400d0857  sub     rsp, 0A0h
0x1400d085e  xorps   xmm0, xmm0
0x1400d0861  mov     [rbp+57h+DeviceObject], 0
0x1400d0869  mov     r15, rdx
0x1400d086c  mov     [rbp+57h+FileObject], 0
0x1400d0874  mov     rdi, rcx
0x1400d0877  lea     rdx, aDeviceMountpoi; "\\Device\\MountPointManager"
0x1400d087e  xor     eax, eax
0x1400d0880  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400d0884  xorps   xmm1, xmm1
0x1400d0887  mov     [rbp+57h+Event.Header.WaitListHead.Blink], rax
0x1400d088b  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400d088f  movups  xmmword ptr [rbp+57h+Event.Header], xmm0
0x1400d0893  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x1400d0897  movups  xmmword ptr [rbp+57h+SourceString.Length], xmm1
0x1400d089b  call    cs:__imp_RtlInitUnicodeString
0x1400d08a2  nop     dword ptr [rax+rax+00h]
0x1400d08a7  lea     r9, [rbp+57h+DeviceObject]; DeviceObject
0x1400d08ab  mov     edx, 80h; DesiredAccess
0x1400d08b0  lea     r8, [rbp+57h+FileObject]; FileObject
0x1400d08b4  lea     rcx, [rbp+57h+DestinationString]; ObjectName
0x1400d08b8  call    cs:__imp_IoGetDeviceObjectPointer
0x1400d08bf  nop     dword ptr [rax+rax+00h]
0x1400d08c4  mov     ebx, eax
0x1400d08c6  test    eax, eax
0x1400d08c8  js      loc_1400D0B4B
0x1400d08ce  movzx   esi, word ptr [rdi]
0x1400d08d1  mov     r13d, 76444856h
0x1400d08d7  add     esi, 18h
0x1400d08da  mov     r8d, r13d
0x1400d08dd  mov     edx, esi
0x1400d08df  mov     ecx, 100h
0x1400d08e4  call    cs:__imp_ExAllocatePool2
0x1400d08eb  nop     dword ptr [rax+rax+00h]
0x1400d08f0  mov     r14, rax
0x1400d08f3  test    rax, rax
0x1400d08f6  jnz     short loc_1400D0902
0x1400d08f8  mov     ebx, 0C000009Ah
0x1400d08fd  jmp     loc_1400D0B4B
0x1400d0902  movzx   r8d, word ptr [rdi]; Size
0x1400d0906  lea     rcx, [rax+18h]; void *
0x1400d090a  mov     rdx, [rdi+8]; Src
0x1400d090e  mov     [rax+14h], r8w
0x1400d0913  mov     dword ptr [rax+10h], 18h
0x1400d091a  call    memmove
0x1400d091f  xor     r8d, r8d; State
0x1400d0922  lea     rcx, [rbp+57h+Event]; Event
0x1400d0926  mov     ebx, 800h
0x1400d092b  lea     edx, [r8+1]; Type
0x1400d092f  call    cs:__imp_KeInitializeEvent
0x1400d0936  nop     dword ptr [rax+rax+00h]
0x1400d093b  mov     edx, ebx
0x1400d093d  mov     r8d, r13d
0x1400d0940  mov     ecx, 100h
0x1400d0945  call    cs:__imp_ExAllocatePool2
0x1400d094c  nop     dword ptr [rax+rax+00h]
0x1400d0951  mov     rdi, rax
0x1400d0954  test    rax, rax
0x1400d0957  jz      loc_1400D0B1D
0x1400d095d  mov     rdx, [rbp+57h+DeviceObject]; DeviceObject
0x1400d0961  lea     rax, [rbp+57h+var_50]
0x1400d0965  mov     [rsp+0C0h+IoStatusBlock], rax; IoStatusBlock
0x1400d096a  mov     r9d, esi; InputBufferLength
0x1400d096d  lea     rax, [rbp+57h+Event]
0x1400d0971  mov     r8, r14; InputBuffer
0x1400d0974  mov     [rsp+0C0h+var_88], rax; Event
0x1400d0979  mov     ecx, 6D0008h; IoControlCode
0x1400d097e  mov     [rsp+0C0h+InternalDeviceIoControl], 0; InternalDeviceIoControl
0x1400d0983  mov     [rsp+0C0h+OutputBufferLength], ebx; OutputBufferLength
0x1400d0987  mov     [rsp+0C0h+OutputBuffer], rdi; OutputBuffer
0x1400d098c  call    cs:__imp_IoBuildDeviceIoControlRequest
0x1400d0993  nop     dword ptr [rax+rax+00h]
0x1400d0998  test    rax, rax
0x1400d099b  jz      loc_1400D0B1D
0x1400d09a1  mov     rcx, [rbp+57h+DeviceObject]; DeviceObject
0x1400d09a5  mov     rdx, rax; Irp
0x1400d09a8  call    cs:__imp_IofCallDriver
0x1400d09af  nop     dword ptr [rax+rax+00h]
0x1400d09b4  mov     ebx, eax
0x1400d09b6  cmp     eax, 103h
0x1400d09bb  jnz     short loc_1400D09E1
0x1400d09bd  xor     r9d, r9d; Alertable
0x1400d09c0  mov     [rsp+0C0h+OutputBuffer], 0; Timeout
0x1400d09c9  xor     r8d, r8d; WaitMode
0x1400d09cc  lea     rcx, [rbp+57h+Event]; Object
0x1400d09d0  xor     edx, edx; WaitReason
0x1400d09d2  call    cs:__imp_KeWaitForSingleObject
0x1400d09d9  nop     dword ptr [rax+rax+00h]
0x1400d09de  mov     ebx, dword ptr [rbp+57h+var_50]
0x1400d09e1  cmp     ebx, 80000005h
0x1400d09e7  jnz     short loc_1400D0A02
0x1400d09e9  mov     ebx, [rdi]
0x1400d09eb  mov     edx, r13d; Tag
0x1400d09ee  mov     rcx, rdi; P
0x1400d09f1  call    cs:__imp_ExFreePoolWithTag
0x1400d09f8  nop     dword ptr [rax+rax+00h]
0x1400d09fd  jmp     loc_1400D093B
0x1400d0a02  test    ebx, ebx
0x1400d0a04  js      loc_1400D0B22
0x1400d0a0a  xor     edx, edx
0x1400d0a0c  mov     ebx, 0C01C0014h
0x1400d0a11  mov     r9w, 2Dh ; '-'
0x1400d0a16  lea     esi, [rdx+5Ch]
0x1400d0a19  cmp     edx, [rdi+4]
0x1400d0a1c  jnb     loc_1400D0B22
0x1400d0a22  lea     rcx, [rdx+rdx*2]
0x1400d0a26  movzx   r8d, word ptr [rdi+rcx*8+0Ch]
0x1400d0a2c  mov     [rbp+57h+SourceString.MaximumLength], r8w
0x1400d0a31  mov     [rbp+57h+SourceString.Length], r8w
0x1400d0a36  mov     ecx, [rdi+rcx*8+8]
0x1400d0a3a  add     rcx, rdi
0x1400d0a3d  mov     [rbp+57h+SourceString.Buffer], rcx
0x1400d0a41  cmp     r8d, 60h ; '`'
0x1400d0a45  jz      short loc_1400D0A53
0x1400d0a47  cmp     r8d, 62h ; 'b'
0x1400d0a4b  jnz     short loc_1400D0AC8
0x1400d0a4d  cmp     [rcx+60h], si
0x1400d0a51  jnz     short loc_1400D0AC8
0x1400d0a53  cmp     [rcx], si
0x1400d0a56  jnz     short loc_1400D0AC8
0x1400d0a58  movzx   eax, word ptr [rcx+2]
0x1400d0a5c  cmp     ax, 3Fh ; '?'
0x1400d0a60  jz      short loc_1400D0A67
0x1400d0a62  cmp     ax, si
0x1400d0a65  jnz     short loc_1400D0AC8
0x1400d0a67  cmp     word ptr [rcx+4], 3Fh ; '?'
0x1400d0a6c  jnz     short loc_1400D0AC8
0x1400d0a6e  cmp     [rcx+6], si
0x1400d0a72  jnz     short loc_1400D0AC8
0x1400d0a74  cmp     word ptr [rcx+8], 56h ; 'V'
0x1400d0a79  jnz     short loc_1400D0AC8
0x1400d0a7b  cmp     word ptr [rcx+0Ah], 6Fh ; 'o'
0x1400d0a80  jnz     short loc_1400D0AC8
0x1400d0a82  cmp     word ptr [rcx+0Ch], 6Ch ; 'l'
0x1400d0a87  jnz     short loc_1400D0AC8
0x1400d0a89  cmp     word ptr [rcx+0Eh], 75h ; 'u'
0x1400d0a8e  jnz     short loc_1400D0AC8
0x1400d0a90  cmp     word ptr [rcx+10h], 6Dh ; 'm'
0x1400d0a95  jnz     short loc_1400D0AC8
0x1400d0a97  cmp     word ptr [rcx+12h], 65h ; 'e'
0x1400d0a9c  jnz     short loc_1400D0AC8
0x1400d0a9e  cmp     word ptr [rcx+14h], 7Bh ; '{'
0x1400d0aa3  jnz     short loc_1400D0AC8
0x1400d0aa5  cmp     [rcx+26h], r9w
0x1400d0aaa  jnz     short loc_1400D0AC8
0x1400d0aac  cmp     [rcx+30h], r9w
0x1400d0ab1  jnz     short loc_1400D0AC8
0x1400d0ab3  cmp     [rcx+3Ah], r9w
0x1400d0ab8  jnz     short loc_1400D0AC8
0x1400d0aba  cmp     [rcx+44h], r9w
0x1400d0abf  jnz     short loc_1400D0AC8
0x1400d0ac1  cmp     word ptr [rcx+5Eh], 7Dh ; '}'
0x1400d0ac6  jz      short loc_1400D0ACF
0x1400d0ac8  inc     edx
0x1400d0aca  jmp     loc_1400D0A19
0x1400d0acf  mov     rdx, r8
0x1400d0ad2  mov     ecx, 100h
0x1400d0ad7  mov     r8d, r13d
0x1400d0ada  call    cs:__imp_ExAllocatePool2
0x1400d0ae1  nop     dword ptr [rax+rax+00h]
0x1400d0ae6  mov     [r15+8], rax
0x1400d0aea  test    rax, rax
0x1400d0aed  jz      short loc_1400D0B1D
0x1400d0aef  xor     eax, eax
0x1400d0af1  lea     rdx, [rbp+57h+SourceString]; SourceString
0x1400d0af5  mov     [r15], ax
0x1400d0af9  mov     rcx, r15; DestinationString
0x1400d0afc  movzx   eax, [rbp+57h+SourceString.MaximumLength]
0x1400d0b00  mov     [r15+2], ax
0x1400d0b05  call    cs:__imp_RtlCopyUnicodeString
0x1400d0b0c  nop     dword ptr [rax+rax+00h]
0x1400d0b11  mov     rax, [r15+8]
0x1400d0b15  xor     ebx, ebx
0x1400d0b17  mov     [rax+2], si
0x1400d0b1b  jmp     short loc_1400D0B22
0x1400d0b1d  mov     ebx, 0C000009Ah
0x1400d0b22  mov     edx, r13d; Tag
0x1400d0b25  mov     rcx, r14; P
0x1400d0b28  call    cs:__imp_ExFreePoolWithTag
0x1400d0b2f  nop     dword ptr [rax+rax+00h]
0x1400d0b34  test    rdi, rdi
0x1400d0b37  jz      short loc_1400D0B4B
0x1400d0b39  mov     edx, r13d; Tag
0x1400d0b3c  mov     rcx, rdi; P
0x1400d0b3f  call    cs:__imp_ExFreePoolWithTag
0x1400d0b46  nop     dword ptr [rax+rax+00h]
0x1400d0b4b  mov     rcx, [rbp+57h+FileObject]; Object
0x1400d0b4f  test    rcx, rcx
0x1400d0b52  jz      short loc_1400D0B60
0x1400d0b54  call    cs:__imp_ObfDereferenceObject
0x1400d0b5b  nop     dword ptr [rax+rax+00h]
0x1400d0b60  lea     r11, [rsp+0C0h+var_20]
0x1400d0b68  mov     eax, ebx
0x1400d0b6a  mov     rbx, [r11+30h]
0x1400d0b6e  mov     rsi, [r11+38h]
0x1400d0b72  mov     rsp, r11
0x1400d0b75  pop     r15
0x1400d0b77  pop     r14
0x1400d0b79  pop     r13
0x1400d0b7b  pop     rdi
0x1400d0b7c  pop     rbp
0x1400d0b7d  retn
```
