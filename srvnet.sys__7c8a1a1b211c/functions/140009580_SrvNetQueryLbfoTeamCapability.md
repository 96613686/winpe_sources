# SrvNetQueryLbfoTeamCapability

- ea: `0x140009580`
- end: `0x1400098c6`
- name: `SrvNetQueryLbfoTeamCapability`
- size: `838`
- prototype: `__int64 __fastcall(NET_IFINDEX InterfaceIndex)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14004fbf0`

## callees

- `0x140009580`
- `0x14002a3e0`
- `0x14002a840`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14000987e`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000987e`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140009664`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140009682`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140009664`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140009682`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x14000976c`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x14000980f`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x14000976c`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x14000980f`
- `ntoskrnl!ZwOpenFile` at `0x1400096db`
- `ntoskrnl!ZwOpenFile` at `0x1400096db`
- `ntoskrnl!RtlStringFromGUID` at `0x140009644`
- `ntoskrnl!RtlStringFromGUID` at `0x140009644`
- `ntoskrnl!ExAllocatePool2` at `0x14000970b`
- `ntoskrnl!ExAllocatePool2` at `0x1400097b0`
- `ntoskrnl!ExAllocatePool2` at `0x14000970b`
- `ntoskrnl!ExAllocatePool2` at `0x1400097b0`
- `ntoskrnl!ZwClose` at `0x14000984c`
- `ntoskrnl!ZwClose` at `0x1400098b8`
- `ntoskrnl!ZwClose` at `0x14000984c`
- `ntoskrnl!ZwClose` at `0x1400098b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009797`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009865`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009797`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009865`
- `NETIO!ConvertInterfaceIndexToLuid` at `0x14000960a`
- `NETIO!ConvertInterfaceIndexToLuid` at `0x14000960a`
- `NETIO!ConvertInterfaceLuidToGuid` at `0x140009627`
- `NETIO!ConvertInterfaceLuidToGuid` at `0x140009627`

## pseudocode

```c
__int64 __fastcall SrvNetQueryLbfoTeamCapability(NET_IFINDEX InterfaceIndex)
{
  unsigned __int8 v2; // si
  _DWORD *InputBuffer; // rax
  _DWORD *v4; // rdi
  unsigned int v5; // eax
  ULONG InputBufferLength; // ebx
  _DWORD *OutputBuffer; // rax
  unsigned int v8; // ecx
  _DWORD *v9; // rax
  void *FileHandle; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+68h] [rbp-98h] BYREF
  NET_LUID InterfaceLuid; // [rsp+78h] [rbp-88h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-80h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-70h] BYREF
  GUID InterfaceGuid; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v18[96]; // [rsp+D0h] [rbp-30h] BYREF

  v2 = 0;
  memset(v18, 0, 0x5Cu);
  *(_QWORD *)&Destination.Length = 6029312;
  FileHandle = 0;
  InterfaceLuid.Value = 0;
  Destination.Buffer = (PWSTR)v18;
  *(_QWORD *)&GuidString.Length = 0;
  memset(&ObjectAttributes, 0, 44);
  GuidString.Buffer = 0;
  IoStatusBlock = 0;
  InterfaceGuid = 0;
  if ( ConvertInterfaceIndexToLuid(InterfaceIndex, &InterfaceLuid) < 0 )
    goto LABEL_19;
  if ( ConvertInterfaceLuidToGuid(&InterfaceLuid, &InterfaceGuid) < 0 )
    goto LABEL_19;
  if ( RtlStringFromGUID(&InterfaceGuid, &GuidString) < 0 )
    goto LABEL_19;
  if ( RtlAppendUnicodeStringToString(&Destination, &DeviceString) < 0 )
    goto LABEL_19;
  if ( RtlAppendUnicodeStringToString(&Destination, &GuidString) < 0 )
    goto LABEL_19;
  ObjectAttributes.ObjectName = &Destination;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenFile(&FileHandle, 0x12019Fu, &ObjectAttributes, &IoStatusBlock, 7u, 0x20u) < 0 )
    goto LABEL_19;
  InputBuffer = (_DWORD *)ExAllocatePool2(256, 44, 1717719884);
  v4 = InputBuffer;
  if ( !InputBuffer )
    goto LABEL_20;
  *(_QWORD *)InputBuffer = 2884025;
  InputBuffer[2] = 0;
  InputBuffer[3] = 65793;
  *((_WORD *)InputBuffer + 20) = 44;
  if ( !ZwDeviceIoControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x17009Cu, InputBuffer, 0x2Cu, InputBuffer, 0x2Cu) )
  {
    v5 = v4[8];
    if ( v5 > 0x2C )
    {
      InputBufferLength = v5 + 44;
      ExFreePoolWithTag(v4, 0x6662534Cu);
      OutputBuffer = (_DWORD *)ExAllocatePool2(256, InputBufferLength, 1717719884);
      v4 = OutputBuffer;
      if ( OutputBuffer )
      {
        *(_QWORD *)OutputBuffer = 2884025;
        OutputBuffer[2] = 0;
        OutputBuffer[3] = 65793;
        *((_WORD *)OutputBuffer + 20) = 44;
        if ( !ZwDeviceIoControlFile(
                FileHandle,
                0,
                0,
                0,
                &IoStatusBlock,
                0x17009Cu,
                OutputBuffer,
                InputBufferLength,
                OutputBuffer,
                InputBufferLength) )
        {
          v8 = 0;
          v9 = (_DWORD *)((char *)v4 + *((unsigned __int16 *)v4 + 20));
          while ( v8 < v4[6] >> 2 )
          {
            if ( *v9 == -100597503 )
            {
              v2 = 1;
              goto LABEL_17;
            }
            ++v9;
            ++v8;
          }
        }
        goto LABEL_17;
      }
LABEL_20:
      ZwClose(FileHandle);
      goto LABEL_19;
    }
  }
LABEL_17:
  ZwClose(FileHandle);
  if ( v4 )
    ExFreePoolWithTag(v4, 0x6662534Cu);
LABEL_19:
  RtlFreeUnicodeString(&GuidString);
  return v2;
}

```

## disassembly

```asm
0x140009580  mov     [rsp-8+arg_10], rbx
0x140009585  mov     [rsp-8+arg_18], rsi
0x14000958a  push    rbp
0x14000958b  push    rdi
0x14000958c  push    r14
0x14000958e  lea     rbp, [rsp-40h]
0x140009593  sub     rsp, 140h
0x14000959a  mov     rax, cs:__security_cookie
0x1400095a1  xor     rax, rsp
0x1400095a4  mov     [rbp+50h+var_20], rax
0x1400095a8  mov     ebx, ecx
0x1400095aa  xor     edx, edx; Val
0x1400095ac  lea     rcx, [rbp+50h+var_80]; void *
0x1400095b0  mov     r8d, 5Ch ; '\'; Size
0x1400095b6  xor     sil, sil
0x1400095b9  call    memset
0x1400095be  xorps   xmm0, xmm0
0x1400095c1  mov     qword ptr [rsp+150h+Destination.Length], 5C0000h
0x1400095ca  xor     r14d, r14d
0x1400095cd  lea     rdx, [rsp+150h+InterfaceLuid]; InterfaceLuid
0x1400095d2  xor     eax, eax
0x1400095d4  mov     [rsp+150h+FileHandle], r14
0x1400095d9  lea     rax, [rbp+50h+var_80]
0x1400095dd  mov     qword ptr [rsp+150h+InterfaceLuid], r14
0x1400095e2  xorps   xmm1, xmm1
0x1400095e5  mov     [rsp+150h+Destination.Buffer], rax
0x1400095ea  movups  xmmword ptr [rbp+50h+ObjectAttributes.ObjectName], xmm0
0x1400095ee  mov     ecx, ebx; InterfaceIndex
0x1400095f0  mov     qword ptr [rsp+150h+GuidString.Length], r14
0x1400095f5  movups  xmmword ptr [rbp+50h+ObjectAttributes.Length], xmm0
0x1400095f9  mov     [rsp+150h+GuidString.Buffer], r14
0x1400095fe  movups  xmmword ptr [rbp+50h+ObjectAttributes+1Ch], xmm0
0x140009602  movups  xmmword ptr [rbp+50h+IoStatusBlock], xmm0
0x140009606  movups  xmmword ptr [rbp+50h+InterfaceGuid.Data1], xmm1
0x14000960a  call    cs:__imp_ConvertInterfaceIndexToLuid
0x140009611  nop     dword ptr [rax+rax+00h]
0x140009616  test    eax, eax
0x140009618  js      loc_140009879
0x14000961e  lea     rdx, [rbp+50h+InterfaceGuid]; InterfaceGuid
0x140009622  lea     rcx, [rsp+150h+InterfaceLuid]; InterfaceLuid
0x140009627  call    cs:__imp_ConvertInterfaceLuidToGuid
0x14000962e  nop     dword ptr [rax+rax+00h]
0x140009633  test    eax, eax
0x140009635  js      loc_140009879
0x14000963b  lea     rdx, [rsp+150h+GuidString]; GuidString
0x140009640  lea     rcx, [rbp+50h+InterfaceGuid]; Guid
0x140009644  call    cs:__imp_RtlStringFromGUID
0x14000964b  nop     dword ptr [rax+rax+00h]
0x140009650  test    eax, eax
0x140009652  js      loc_140009879
0x140009658  lea     rdx, DeviceString; Source
0x14000965f  lea     rcx, [rsp+150h+Destination]; Destination
0x140009664  call    cs:__imp_RtlAppendUnicodeStringToString
0x14000966b  nop     dword ptr [rax+rax+00h]
0x140009670  test    eax, eax
0x140009672  js      loc_140009879
0x140009678  lea     rdx, [rsp+150h+GuidString]; Source
0x14000967d  lea     rcx, [rsp+150h+Destination]; Destination
0x140009682  call    cs:__imp_RtlAppendUnicodeStringToString
0x140009689  nop     dword ptr [rax+rax+00h]
0x14000968e  test    eax, eax
0x140009690  js      loc_140009879
0x140009696  lea     rax, [rsp+150h+Destination]
0x14000969b  mov     [rsp+150h+OpenOptions], 20h ; ' '; OpenOptions
0x1400096a3  xorps   xmm0, xmm0
0x1400096a6  mov     [rbp+50h+ObjectAttributes.ObjectName], rax
0x1400096aa  lea     r9, [rbp+50h+IoStatusBlock]; IoStatusBlock
0x1400096ae  mov     [rbp+50h+ObjectAttributes.Length], 30h ; '0'
0x1400096b5  lea     r8, [rbp+50h+ObjectAttributes]; ObjectAttributes
0x1400096b9  mov     [rbp+50h+ObjectAttributes.RootDirectory], r14
0x1400096bd  mov     edx, 12019Fh; DesiredAccess
0x1400096c2  mov     [rbp+50h+ObjectAttributes.Attributes], 240h
0x1400096c9  lea     rcx, [rsp+150h+FileHandle]; FileHandle
0x1400096ce  mov     [rsp+150h+ShareAccess], 7; ShareAccess
0x1400096d6  movdqu  xmmword ptr [rbp+50h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400096db  call    cs:__imp_ZwOpenFile
0x1400096e2  nop     dword ptr [rax+rax+00h]
0x1400096e7  test    eax, eax
0x1400096e9  js      loc_140009879
0x1400096ef  mov     [rsp+150h+arg_8], r15
0x1400096f7  mov     r8d, 6662534Ch
0x1400096fd  mov     r15d, 2Ch ; ','
0x140009703  mov     ecx, 100h
0x140009708  mov     edx, r15d
0x14000970b  call    cs:__imp_ExAllocatePool2
0x140009712  nop     dword ptr [rax+rax+00h]
0x140009717  mov     rdi, rax
0x14000971a  test    rax, rax
0x14000971d  jz      loc_1400098B3
0x140009723  mov     [rsp+150h+OutputBufferLength], r15d; OutputBufferLength
0x140009728  xor     r9d, r9d; ApcContext
0x14000972b  mov     [rsp+150h+OutputBuffer], rax; OutputBuffer
0x140009730  xor     r8d, r8d; ApcRoutine
0x140009733  mov     [rsp+150h+InputBufferLength], r15d; InputBufferLength
0x140009738  xor     edx, edx; Event
0x14000973a  mov     [rsp+150h+InputBuffer], rax; InputBuffer
0x14000973f  mov     qword ptr [rax], 2C01B9h
0x140009746  mov     [rax+8], r14d
0x14000974a  mov     dword ptr [rax+0Ch], 10101h
0x140009751  mov     [rax+28h], r15w
0x140009756  lea     rax, [rbp+50h+IoStatusBlock]
0x14000975a  mov     rcx, [rsp+150h+FileHandle]; FileHandle
0x14000975f  mov     [rsp+150h+OpenOptions], 17009Ch; IoControlCode
0x140009767  mov     qword ptr [rsp+150h+ShareAccess], rax; IoStatusBlock
0x14000976c  call    cs:__imp_ZwDeviceIoControlFile
0x140009773  nop     dword ptr [rax+rax+00h]
0x140009778  test    eax, eax
0x14000977a  jnz     loc_140009847
0x140009780  mov     eax, [rdi+20h]
0x140009783  cmp     eax, r15d
0x140009786  jbe     loc_140009847
0x14000978c  mov     edx, 6662534Ch; Tag
0x140009791  lea     ebx, [rax+2Ch]
0x140009794  mov     rcx, rdi; P
0x140009797  call    cs:__imp_ExFreePoolWithTag
0x14000979e  nop     dword ptr [rax+rax+00h]
0x1400097a3  mov     edx, ebx
0x1400097a5  mov     ecx, 100h
0x1400097aa  mov     r8d, 6662534Ch
0x1400097b0  call    cs:__imp_ExAllocatePool2
0x1400097b7  nop     dword ptr [rax+rax+00h]
0x1400097bc  mov     rdi, rax
0x1400097bf  test    rax, rax
0x1400097c2  jz      loc_1400098B3
0x1400097c8  mov     [rsp+150h+OutputBufferLength], ebx; OutputBufferLength
0x1400097cc  xor     r9d, r9d; ApcContext
0x1400097cf  mov     [rsp+150h+OutputBuffer], rax; OutputBuffer
0x1400097d4  xor     r8d, r8d; ApcRoutine
0x1400097d7  mov     [rsp+150h+InputBufferLength], ebx; InputBufferLength
0x1400097db  xor     edx, edx; Event
0x1400097dd  mov     [rsp+150h+InputBuffer], rax; InputBuffer
0x1400097e2  mov     qword ptr [rax], 2C01B9h
0x1400097e9  mov     [rax+8], r14d
0x1400097ed  mov     dword ptr [rax+0Ch], 10101h
0x1400097f4  mov     [rax+28h], r15w
0x1400097f9  lea     rax, [rbp+50h+IoStatusBlock]
0x1400097fd  mov     rcx, [rsp+150h+FileHandle]; FileHandle
0x140009802  mov     [rsp+150h+OpenOptions], 17009Ch; IoControlCode
0x14000980a  mov     qword ptr [rsp+150h+ShareAccess], rax; IoStatusBlock
0x14000980f  call    cs:__imp_ZwDeviceIoControlFile
0x140009816  nop     dword ptr [rax+rax+00h]
0x14000981b  test    eax, eax
0x14000981d  jnz     short loc_140009847
0x14000981f  movzx   eax, word ptr [rdi+28h]
0x140009823  mov     ecx, r14d
0x140009826  mov     edx, [rdi+18h]
0x140009829  add     rax, rdi
0x14000982c  shr     edx, 2
0x14000982f  nop
0x140009830  cmp     ecx, edx
0x140009832  jnb     short loc_140009847
0x140009834  cmp     dword ptr [rax], 0FA010101h
0x14000983a  jz      short loc_140009844
0x14000983c  add     rax, 4
0x140009840  inc     ecx
0x140009842  jmp     short loc_140009830
0x140009844  mov     sil, 1
0x140009847  mov     rcx, [rsp+150h+FileHandle]; Handle
0x14000984c  call    cs:__imp_ZwClose
0x140009853  nop     dword ptr [rax+rax+00h]
0x140009858  test    rdi, rdi
0x14000985b  jz      short loc_140009871
0x14000985d  mov     edx, 6662534Ch; Tag
0x140009862  mov     rcx, rdi; P
0x140009865  call    cs:__imp_ExFreePoolWithTag
0x14000986c  nop     dword ptr [rax+rax+00h]
0x140009871  mov     r15, [rsp+150h+arg_8]
0x140009879  lea     rcx, [rsp+150h+GuidString]; UnicodeString
0x14000987e  call    cs:__imp_RtlFreeUnicodeString
0x140009885  nop     dword ptr [rax+rax+00h]
0x14000988a  movzx   eax, sil
0x14000988e  mov     rcx, [rbp+50h+var_20]
0x140009892  xor     rcx, rsp; StackCookie
0x140009895  call    __security_check_cookie
0x14000989a  lea     r11, [rsp+150h+var_10]
0x1400098a2  mov     rbx, [r11+30h]
0x1400098a6  mov     rsi, [r11+38h]
0x1400098aa  mov     rsp, r11
0x1400098ad  pop     r14
0x1400098af  pop     rdi
0x1400098b0  pop     rbp
0x1400098b1  retn
0x1400098b3  mov     rcx, [rsp+150h+FileHandle]; Handle
0x1400098b8  call    cs:__imp_ZwClose
0x1400098bf  nop     dword ptr [rax+rax+00h]
0x1400098c4  jmp     short loc_140009871
```
