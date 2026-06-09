# VhdmpiGetVolumeGuid(_UNICODE_STRING const *,_UNICODE_STRING *)

- ea: `0x1400d08b0`
- end: `0x1400d0bef`
- name: `?VhdmpiGetVolumeGuid@@YAJPEBU_UNICODE_STRING@@PEAU1@@Z`
- size: `831`
- prototype: `int(const struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x1400e6464`

## callees

- `0x14005da00`
- `0x1400d08b0`

## import_xrefs

- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400d09fc`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400d09fc`
- `ntoskrnl!IofCallDriver` at `0x1400d0a18`
- `ntoskrnl!IofCallDriver` at `0x1400d0a18`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400d0b75`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400d0b75`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x1400d0928`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x1400d0928`
- `ntoskrnl!ObfDereferenceObject` at `0x1400d0bc4`
- `ntoskrnl!ObfDereferenceObject` at `0x1400d0bc4`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400d090b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400d090b`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400d0a42`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400d0a42`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d0a61`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d0b98`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d0baf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d0a61`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d0b98`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d0baf`
- `ntoskrnl!ExAllocatePool2` at `0x1400d0954`
- `ntoskrnl!ExAllocatePool2` at `0x1400d09b5`
- `ntoskrnl!ExAllocatePool2` at `0x1400d0b4a`
- `ntoskrnl!ExAllocatePool2` at `0x1400d0954`
- `ntoskrnl!ExAllocatePool2` at `0x1400d09b5`
- `ntoskrnl!ExAllocatePool2` at `0x1400d0b4a`
- `ntoskrnl!KeInitializeEvent` at `0x1400d099f`
- `ntoskrnl!KeInitializeEvent` at `0x1400d099f`

## string_xrefs

- `0x1400d08e7`: `\Device\MountPointManager`

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
0x1400d08b0  mov     [rsp-8+arg_0], rbx
0x1400d08b5  mov     [rsp-8+arg_8], rsi
0x1400d08ba  push    rbp
0x1400d08bb  push    rdi
0x1400d08bc  push    r13
0x1400d08be  push    r14
0x1400d08c0  push    r15
0x1400d08c2  lea     rbp, [rsp-37h]
0x1400d08c7  sub     rsp, 0A0h
0x1400d08ce  xorps   xmm0, xmm0
0x1400d08d1  mov     [rbp+57h+DeviceObject], 0
0x1400d08d9  mov     r15, rdx
0x1400d08dc  mov     [rbp+57h+FileObject], 0
0x1400d08e4  mov     rdi, rcx
0x1400d08e7  lea     rdx, aDeviceMountpoi; "\\Device\\MountPointManager"
0x1400d08ee  xor     eax, eax
0x1400d08f0  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400d08f4  xorps   xmm1, xmm1
0x1400d08f7  mov     [rbp+57h+Event.Header.WaitListHead.Blink], rax
0x1400d08fb  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400d08ff  movups  xmmword ptr [rbp+57h+Event.Header], xmm0
0x1400d0903  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x1400d0907  movups  xmmword ptr [rbp+57h+SourceString.Length], xmm1
0x1400d090b  call    cs:__imp_RtlInitUnicodeString
0x1400d0912  nop     dword ptr [rax+rax+00h]
0x1400d0917  lea     r9, [rbp+57h+DeviceObject]; DeviceObject
0x1400d091b  mov     edx, 80h; DesiredAccess
0x1400d0920  lea     r8, [rbp+57h+FileObject]; FileObject
0x1400d0924  lea     rcx, [rbp+57h+DestinationString]; ObjectName
0x1400d0928  call    cs:__imp_IoGetDeviceObjectPointer
0x1400d092f  nop     dword ptr [rax+rax+00h]
0x1400d0934  mov     ebx, eax
0x1400d0936  test    eax, eax
0x1400d0938  js      loc_1400D0BBB
0x1400d093e  movzx   esi, word ptr [rdi]
0x1400d0941  mov     r13d, 76444856h
0x1400d0947  add     esi, 18h
0x1400d094a  mov     r8d, r13d
0x1400d094d  mov     edx, esi
0x1400d094f  mov     ecx, 100h
0x1400d0954  call    cs:__imp_ExAllocatePool2
0x1400d095b  nop     dword ptr [rax+rax+00h]
0x1400d0960  mov     r14, rax
0x1400d0963  test    rax, rax
0x1400d0966  jnz     short loc_1400D0972
0x1400d0968  mov     ebx, 0C000009Ah
0x1400d096d  jmp     loc_1400D0BBB
0x1400d0972  movzx   r8d, word ptr [rdi]; Size
0x1400d0976  lea     rcx, [rax+18h]; void *
0x1400d097a  mov     rdx, [rdi+8]; Src
0x1400d097e  mov     [rax+14h], r8w
0x1400d0983  mov     dword ptr [rax+10h], 18h
0x1400d098a  call    memmove
0x1400d098f  xor     r8d, r8d; State
0x1400d0992  lea     rcx, [rbp+57h+Event]; Event
0x1400d0996  mov     ebx, 800h
0x1400d099b  lea     edx, [r8+1]; Type
0x1400d099f  call    cs:__imp_KeInitializeEvent
0x1400d09a6  nop     dword ptr [rax+rax+00h]
0x1400d09ab  mov     edx, ebx
0x1400d09ad  mov     r8d, r13d
0x1400d09b0  mov     ecx, 100h
0x1400d09b5  call    cs:__imp_ExAllocatePool2
0x1400d09bc  nop     dword ptr [rax+rax+00h]
0x1400d09c1  mov     rdi, rax
0x1400d09c4  test    rax, rax
0x1400d09c7  jz      loc_1400D0B8D
0x1400d09cd  mov     rdx, [rbp+57h+DeviceObject]; DeviceObject
0x1400d09d1  lea     rax, [rbp+57h+var_50]
0x1400d09d5  mov     [rsp+0C0h+IoStatusBlock], rax; IoStatusBlock
0x1400d09da  mov     r9d, esi; InputBufferLength
0x1400d09dd  lea     rax, [rbp+57h+Event]
0x1400d09e1  mov     r8, r14; InputBuffer
0x1400d09e4  mov     [rsp+0C0h+var_88], rax; Event
0x1400d09e9  mov     ecx, 6D0008h; IoControlCode
0x1400d09ee  mov     [rsp+0C0h+InternalDeviceIoControl], 0; InternalDeviceIoControl
0x1400d09f3  mov     [rsp+0C0h+OutputBufferLength], ebx; OutputBufferLength
0x1400d09f7  mov     [rsp+0C0h+OutputBuffer], rdi; OutputBuffer
0x1400d09fc  call    cs:__imp_IoBuildDeviceIoControlRequest
0x1400d0a03  nop     dword ptr [rax+rax+00h]
0x1400d0a08  test    rax, rax
0x1400d0a0b  jz      loc_1400D0B8D
0x1400d0a11  mov     rcx, [rbp+57h+DeviceObject]; DeviceObject
0x1400d0a15  mov     rdx, rax; Irp
0x1400d0a18  call    cs:__imp_IofCallDriver
0x1400d0a1f  nop     dword ptr [rax+rax+00h]
0x1400d0a24  mov     ebx, eax
0x1400d0a26  cmp     eax, 103h
0x1400d0a2b  jnz     short loc_1400D0A51
0x1400d0a2d  xor     r9d, r9d; Alertable
0x1400d0a30  mov     [rsp+0C0h+OutputBuffer], 0; Timeout
0x1400d0a39  xor     r8d, r8d; WaitMode
0x1400d0a3c  lea     rcx, [rbp+57h+Event]; Object
0x1400d0a40  xor     edx, edx; WaitReason
0x1400d0a42  call    cs:__imp_KeWaitForSingleObject
0x1400d0a49  nop     dword ptr [rax+rax+00h]
0x1400d0a4e  mov     ebx, dword ptr [rbp+57h+var_50]
0x1400d0a51  cmp     ebx, 80000005h
0x1400d0a57  jnz     short loc_1400D0A72
0x1400d0a59  mov     ebx, [rdi]
0x1400d0a5b  mov     edx, r13d; Tag
0x1400d0a5e  mov     rcx, rdi; P
0x1400d0a61  call    cs:__imp_ExFreePoolWithTag
0x1400d0a68  nop     dword ptr [rax+rax+00h]
0x1400d0a6d  jmp     loc_1400D09AB
0x1400d0a72  test    ebx, ebx
0x1400d0a74  js      loc_1400D0B92
0x1400d0a7a  xor     edx, edx
0x1400d0a7c  mov     ebx, 0C01C0014h
0x1400d0a81  mov     r9w, 2Dh ; '-'
0x1400d0a86  lea     esi, [rdx+5Ch]
0x1400d0a89  cmp     edx, [rdi+4]
0x1400d0a8c  jnb     loc_1400D0B92
0x1400d0a92  lea     rcx, [rdx+rdx*2]
0x1400d0a96  movzx   r8d, word ptr [rdi+rcx*8+0Ch]
0x1400d0a9c  mov     [rbp+57h+SourceString.MaximumLength], r8w
0x1400d0aa1  mov     [rbp+57h+SourceString.Length], r8w
0x1400d0aa6  mov     ecx, [rdi+rcx*8+8]
0x1400d0aaa  add     rcx, rdi
0x1400d0aad  mov     [rbp+57h+SourceString.Buffer], rcx
0x1400d0ab1  cmp     r8d, 60h ; '`'
0x1400d0ab5  jz      short loc_1400D0AC3
0x1400d0ab7  cmp     r8d, 62h ; 'b'
0x1400d0abb  jnz     short loc_1400D0B38
0x1400d0abd  cmp     [rcx+60h], si
0x1400d0ac1  jnz     short loc_1400D0B38
0x1400d0ac3  cmp     [rcx], si
0x1400d0ac6  jnz     short loc_1400D0B38
0x1400d0ac8  movzx   eax, word ptr [rcx+2]
0x1400d0acc  cmp     ax, 3Fh ; '?'
0x1400d0ad0  jz      short loc_1400D0AD7
0x1400d0ad2  cmp     ax, si
0x1400d0ad5  jnz     short loc_1400D0B38
0x1400d0ad7  cmp     word ptr [rcx+4], 3Fh ; '?'
0x1400d0adc  jnz     short loc_1400D0B38
0x1400d0ade  cmp     [rcx+6], si
0x1400d0ae2  jnz     short loc_1400D0B38
0x1400d0ae4  cmp     word ptr [rcx+8], 56h ; 'V'
0x1400d0ae9  jnz     short loc_1400D0B38
0x1400d0aeb  cmp     word ptr [rcx+0Ah], 6Fh ; 'o'
0x1400d0af0  jnz     short loc_1400D0B38
0x1400d0af2  cmp     word ptr [rcx+0Ch], 6Ch ; 'l'
0x1400d0af7  jnz     short loc_1400D0B38
0x1400d0af9  cmp     word ptr [rcx+0Eh], 75h ; 'u'
0x1400d0afe  jnz     short loc_1400D0B38
0x1400d0b00  cmp     word ptr [rcx+10h], 6Dh ; 'm'
0x1400d0b05  jnz     short loc_1400D0B38
0x1400d0b07  cmp     word ptr [rcx+12h], 65h ; 'e'
0x1400d0b0c  jnz     short loc_1400D0B38
0x1400d0b0e  cmp     word ptr [rcx+14h], 7Bh ; '{'
0x1400d0b13  jnz     short loc_1400D0B38
0x1400d0b15  cmp     [rcx+26h], r9w
0x1400d0b1a  jnz     short loc_1400D0B38
0x1400d0b1c  cmp     [rcx+30h], r9w
0x1400d0b21  jnz     short loc_1400D0B38
0x1400d0b23  cmp     [rcx+3Ah], r9w
0x1400d0b28  jnz     short loc_1400D0B38
0x1400d0b2a  cmp     [rcx+44h], r9w
0x1400d0b2f  jnz     short loc_1400D0B38
0x1400d0b31  cmp     word ptr [rcx+5Eh], 7Dh ; '}'
0x1400d0b36  jz      short loc_1400D0B3F
0x1400d0b38  inc     edx
0x1400d0b3a  jmp     loc_1400D0A89
0x1400d0b3f  mov     rdx, r8
0x1400d0b42  mov     ecx, 100h
0x1400d0b47  mov     r8d, r13d
0x1400d0b4a  call    cs:__imp_ExAllocatePool2
0x1400d0b51  nop     dword ptr [rax+rax+00h]
0x1400d0b56  mov     [r15+8], rax
0x1400d0b5a  test    rax, rax
0x1400d0b5d  jz      short loc_1400D0B8D
0x1400d0b5f  xor     eax, eax
0x1400d0b61  lea     rdx, [rbp+57h+SourceString]; SourceString
0x1400d0b65  mov     [r15], ax
0x1400d0b69  mov     rcx, r15; DestinationString
0x1400d0b6c  movzx   eax, [rbp+57h+SourceString.MaximumLength]
0x1400d0b70  mov     [r15+2], ax
0x1400d0b75  call    cs:__imp_RtlCopyUnicodeString
0x1400d0b7c  nop     dword ptr [rax+rax+00h]
0x1400d0b81  mov     rax, [r15+8]
0x1400d0b85  xor     ebx, ebx
0x1400d0b87  mov     [rax+2], si
0x1400d0b8b  jmp     short loc_1400D0B92
0x1400d0b8d  mov     ebx, 0C000009Ah
0x1400d0b92  mov     edx, r13d; Tag
0x1400d0b95  mov     rcx, r14; P
0x1400d0b98  call    cs:__imp_ExFreePoolWithTag
0x1400d0b9f  nop     dword ptr [rax+rax+00h]
0x1400d0ba4  test    rdi, rdi
0x1400d0ba7  jz      short loc_1400D0BBB
0x1400d0ba9  mov     edx, r13d; Tag
0x1400d0bac  mov     rcx, rdi; P
0x1400d0baf  call    cs:__imp_ExFreePoolWithTag
0x1400d0bb6  nop     dword ptr [rax+rax+00h]
0x1400d0bbb  mov     rcx, [rbp+57h+FileObject]; Object
0x1400d0bbf  test    rcx, rcx
0x1400d0bc2  jz      short loc_1400D0BD0
0x1400d0bc4  call    cs:__imp_ObfDereferenceObject
0x1400d0bcb  nop     dword ptr [rax+rax+00h]
0x1400d0bd0  lea     r11, [rsp+0C0h+var_20]
0x1400d0bd8  mov     eax, ebx
0x1400d0bda  mov     rbx, [r11+30h]
0x1400d0bde  mov     rsi, [r11+38h]
0x1400d0be2  mov     rsp, r11
0x1400d0be5  pop     r15
0x1400d0be7  pop     r14
0x1400d0be9  pop     r13
0x1400d0beb  pop     rdi
0x1400d0bec  pop     rbp
0x1400d0bed  retn
```
