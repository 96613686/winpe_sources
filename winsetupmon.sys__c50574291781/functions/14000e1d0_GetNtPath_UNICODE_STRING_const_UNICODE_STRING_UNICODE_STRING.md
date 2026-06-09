# GetNtPath(_UNICODE_STRING const *,_UNICODE_STRING *,_UNICODE_STRING *)

- ea: `0x14000e1d0`
- end: `0x14000e480`
- name: `?GetNtPath@@YAJPEBU_UNICODE_STRING@@PEAU1@1@Z`
- size: `688`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String2, PUNICODE_STRING DestinationString, struct _UNICODE_STRING *)`
- caller_count: `11`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140002ffc`
- `0x14000362c`
- `0x140005910`
- `0x140005de4`
- `0x140006924`
- `0x140006bd4`
- `0x1400071f4`
- `0x140007384`
- `0x14000df1c`
- `0x14000e778`
- `0x14000eb0c`

## callees

- `0x140008138`
- `0x14000dd24`
- `0x14000e1d0`
- `0x14000eb68`
- `0x14000f34c`
- `0x14000f684`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14000e43a`
- `ntoskrnl!ZwClose` at `0x14000e43a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000e3e8`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000e3e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e419`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e45a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e419`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e45a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000e376`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000e376`
- `ntoskrnl!ZwOpenSymbolicLinkObject` at `0x14000e30f`
- `ntoskrnl!ZwOpenSymbolicLinkObject` at `0x14000e30f`
- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x14000e347`
- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x14000e3aa`
- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x14000e347`
- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x14000e3aa`

## string_xrefs

- `0x14000e25d`: `WinSetupMon::GetNtPath: Failed to duplicate for NtPath %wZ (0x%08X)`
- `0x14000e2d4`: `WinSetupMon::GetNtPath: Failed GetVolumeSymbolicLinkFromPath for Path %wZ (0x%08X)`
- `0x14000e330`: `WinSetupMon::GetNtPath: Failed OpenSymbolicLinkObject (0x%08X)`
- `0x14000e38b`: `WinSetupMon::GetNtPath: Failed to allocate NtPath buffer`
- `0x14000e3bf`: `WinSetupMon::GetNtPath: Failed QuerySymbolicLinkObject (0x%08X)`
- `0x14000e3fd`: `WinSetupMon::GetNtPath: Failed RtlAppendUnicodeStringToString (0x%08X)`

## pseudocode

```c
__int64 __fastcall GetNtPath(PCUNICODE_STRING String2, PUNICODE_STRING DestinationString, struct _UNICODE_STRING *a3)
{
  int VolumeDeviceInPath; // eax
  NTSTATUS VolumeSymbolicLinkFromPath; // ebx
  const char *v8; // rdx
  unsigned __int16 Length; // ax
  NTSTATUS v10; // eax
  const char *v11; // rdx
  unsigned __int16 v12; // ax
  wchar_t *PoolWithTag; // rax
  unsigned __int16 v14; // ax
  wchar_t *Buffer; // rcx
  void *LinkHandle; // [rsp+20h] [rbp-49h] BYREF
  UNICODE_STRING Source; // [rsp+28h] [rbp-41h] BYREF
  UNICODE_STRING SourceString; // [rsp+38h] [rbp-31h] BYREF
  struct _UNICODE_STRING v20; // [rsp+48h] [rbp-21h] BYREF
  PVOID P[2]; // [rsp+58h] [rbp-11h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-1h] BYREF
  unsigned __int8 v23; // [rsp+D8h] [rbp+6Fh] BYREF
  ULONG ReturnedLength; // [rsp+E8h] [rbp+7Fh] BYREF

  DestinationString->Buffer = 0;
  v23 = 0;
  LinkHandle = 0;
  v20 = 0;
  *(_OWORD *)P = 0;
  Source = 0;
  VolumeDeviceInPath = GetVolumeDeviceInPath(String2, &v20, &Source);
  VolumeSymbolicLinkFromPath = VolumeDeviceInPath;
  if ( VolumeDeviceInPath >= 0 )
  {
    *(&SourceString.MaximumLength + 2) = 0;
    SourceString.Buffer = v20.Buffer;
    *(_DWORD *)&SourceString.MaximumLength = (unsigned __int16)(v20.Length + Source.Length);
    SourceString.Length = v20.Length + Source.Length;
    VolumeSymbolicLinkFromPath = Duplicate(&SourceString, DestinationString);
    if ( VolumeSymbolicLinkFromPath >= 0 )
    {
      a3->Buffer = DestinationString->Buffer;
      Length = v20.Length;
      a3->MaximumLength = v20.Length;
      a3->Length = Length;
      goto LABEL_27;
    }
    v8 = "WinSetupMon::GetNtPath: Failed to duplicate for NtPath %wZ (0x%08X)";
    goto LABEL_4;
  }
  if ( VolumeDeviceInPath == -1073741637 )
  {
    ReturnedLength = 0;
    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
    VolumeSymbolicLinkFromPath = GetVolumeSymbolicLinkFromPath(String2, (PUNICODE_STRING)P, &v23, &Source);
    if ( VolumeSymbolicLinkFromPath >= 0 )
    {
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)P;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v10 = ZwOpenSymbolicLinkObject(&LinkHandle, 0x80000000, &ObjectAttributes);
      VolumeSymbolicLinkFromPath = v10;
      if ( v10 >= 0 )
      {
        VolumeSymbolicLinkFromPath = ZwQuerySymbolicLinkObject(LinkHandle, DestinationString, &ReturnedLength);
        if ( VolumeSymbolicLinkFromPath == -1073741789 )
        {
          v12 = Source.Length + ReturnedLength;
          DestinationString->MaximumLength = Source.Length + ReturnedLength;
          PoolWithTag = (wchar_t *)ExAllocatePoolWithTag(PagedPool, v12, 0x6E6D7377u);
          DestinationString->Buffer = PoolWithTag;
          if ( !PoolWithTag )
          {
            WriteLog(0, "WinSetupMon::GetNtPath: Failed to allocate NtPath buffer");
            VolumeSymbolicLinkFromPath = -1073741670;
            goto LABEL_24;
          }
          VolumeSymbolicLinkFromPath = ZwQuerySymbolicLinkObject(LinkHandle, DestinationString, 0);
        }
        if ( VolumeSymbolicLinkFromPath >= 0 )
        {
          a3->Buffer = DestinationString->Buffer;
          v14 = DestinationString->Length;
          a3->MaximumLength = DestinationString->Length;
          a3->Length = v14;
          if ( !Source.Length )
            goto LABEL_27;
          VolumeSymbolicLinkFromPath = RtlAppendUnicodeStringToString(DestinationString, &Source);
          if ( VolumeSymbolicLinkFromPath >= 0 )
            goto LABEL_27;
          v11 = "WinSetupMon::GetNtPath: Failed RtlAppendUnicodeStringToString (0x%08X)";
        }
        else
        {
          v11 = "WinSetupMon::GetNtPath: Failed QuerySymbolicLinkObject (0x%08X)";
        }
      }
      else
      {
        if ( v10 != -1073741772 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM();
        v11 = "WinSetupMon::GetNtPath: Failed OpenSymbolicLinkObject (0x%08X)";
      }
      WriteLog(0, v11);
      goto LABEL_24;
    }
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
    if ( VolumeSymbolicLinkFromPath != -1073741637 )
    {
      v8 = "WinSetupMon::GetNtPath: Failed GetVolumeSymbolicLinkFromPath for Path %wZ (0x%08X)";
LABEL_4:
      WriteLog(0, v8);
    }
  }
LABEL_24:
  Buffer = DestinationString->Buffer;
  if ( Buffer )
    ExFreePoolWithTag(Buffer, 0x6E6D7377u);
  *DestinationString = 0;
  *a3 = 0;
LABEL_27:
  if ( LinkHandle )
    ZwClose(LinkHandle);
  if ( v23 && P[1] )
    ExFreePoolWithTag(P[1], 0x6E6D7377u);
  return (unsigned int)VolumeSymbolicLinkFromPath;
}

```

## disassembly

```asm
0x14000e1d0  mov     [rsp-8+arg_0], rbx
0x14000e1d5  push    rbp
0x14000e1d6  push    rsi
0x14000e1d7  push    rdi
0x14000e1d8  push    r14
0x14000e1da  push    r15
0x14000e1dc  lea     rbp, [rsp-37h]
0x14000e1e1  sub     rsp, 0A0h
0x14000e1e8  xor     r15d, r15d
0x14000e1eb  xorps   xmm0, xmm0
0x14000e1ee  mov     [rdx+8], r15
0x14000e1f2  mov     rsi, r8
0x14000e1f5  mov     rdi, rdx
0x14000e1f8  mov     [rbp+57h+arg_8], r15b
0x14000e1fc  xorps   xmm1, xmm1
0x14000e1ff  mov     [rbp+57h+LinkHandle], r15
0x14000e203  lea     rdx, [rbp+57h+var_78]; struct _UNICODE_STRING *
0x14000e207  mov     r14, rcx
0x14000e20a  lea     r8, [rbp+57h+Source]; struct _UNICODE_STRING *
0x14000e20e  movups  xmmword ptr [rbp+57h+var_78.Length], xmm0
0x14000e212  movups  xmmword ptr [rbp+57h+P], xmm1
0x14000e216  movups  xmmword ptr [rbp+57h+Source.Length], xmm0
0x14000e21a  call    ?GetVolumeDeviceInPath@@YAJPEBU_UNICODE_STRING@@PEAU1@1@Z; GetVolumeDeviceInPath(_UNICODE_STRING const *,_UNICODE_STRING *,_UNICODE_STRING *)
0x14000e21f  mov     ebx, eax
0x14000e221  test    eax, eax
0x14000e223  js      short loc_14000E288
0x14000e225  mov     rax, [rbp+57h+var_78.Buffer]
0x14000e229  lea     rcx, [rbp+57h+SourceString]; SourceString
0x14000e22d  xorps   xmm0, xmm0
0x14000e230  mov     rdx, rdi; DestinationString
0x14000e233  movups  xmmword ptr [rbp+57h+SourceString.Length], xmm0
0x14000e237  mov     [rbp+57h+SourceString.Buffer], rax
0x14000e23b  movzx   eax, [rbp+57h+Source.Length]
0x14000e23f  add     ax, [rbp+57h+var_78.Length]
0x14000e243  mov     [rbp+57h+SourceString.MaximumLength], ax
0x14000e247  mov     [rbp+57h+SourceString.Length], ax
0x14000e24b  call    ?Duplicate@@YAJPEBU_UNICODE_STRING@@PEAU1@@Z; Duplicate(_UNICODE_STRING const *,_UNICODE_STRING *)
0x14000e250  mov     ebx, eax
0x14000e252  test    eax, eax
0x14000e254  jns     short loc_14000E270
0x14000e256  mov     r9d, eax
0x14000e259  lea     r8, [rbp+57h+SourceString]
0x14000e25d  lea     rdx, aWinsetupmonGet_19; "WinSetupMon::GetNtPath: Failed to dupli"...
0x14000e264  xor     ecx, ecx
0x14000e266  call    ?WriteLog@@YAXW4LogLevel@@PEBDZZ; WriteLog(LogLevel,char const *,...)
0x14000e26b  jmp     loc_14000E40B
0x14000e270  mov     rax, [rdi+8]
0x14000e274  mov     [rsi+8], rax
0x14000e278  movzx   eax, [rbp+57h+var_78.Length]
0x14000e27c  mov     [rsi+2], ax
0x14000e280  mov     [rsi], ax
0x14000e283  jmp     loc_14000E431
0x14000e288  cmp     eax, 0C00000BBh
0x14000e28d  jnz     loc_14000E40B
0x14000e293  xorps   xmm0, xmm0
0x14000e296  mov     [rbp+57h+ReturnedLength], r15d
0x14000e29a  lea     r9, [rbp+57h+Source]; struct _UNICODE_STRING *
0x14000e29e  mov     rcx, r14; String2
0x14000e2a1  lea     r8, [rbp+57h+arg_8]; unsigned __int8 *
0x14000e2a5  lea     rdx, [rbp+57h+P]; DestinationString
0x14000e2a9  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14000e2ad  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14000e2b1  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000e2b5  call    ?GetVolumeSymbolicLinkFromPath@@YAJPEBU_UNICODE_STRING@@PEAU1@PEAE1@Z; GetVolumeSymbolicLinkFromPath(_UNICODE_STRING const *,_UNICODE_STRING *,uchar *,_UNICODE_STRING *)
0x14000e2ba  mov     ebx, eax
0x14000e2bc  test    eax, eax
0x14000e2be  jns     short loc_14000E2E0
0x14000e2c0  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14000e2c5  cmp     ebx, 0C00000BBh
0x14000e2cb  jz      loc_14000E40B
0x14000e2d1  mov     r9d, ebx
0x14000e2d4  lea     rdx, aWinsetupmonGet_9; "WinSetupMon::GetNtPath: Failed GetVolum"...
0x14000e2db  mov     r8, r14
0x14000e2de  jmp     short loc_14000E264
0x14000e2e0  lea     rax, [rbp+57h+P]
0x14000e2e4  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14000e2eb  xorps   xmm0, xmm0
0x14000e2ee  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14000e2f2  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14000e2f6  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x14000e2fa  mov     edx, 80000000h; DesiredAccess
0x14000e2ff  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14000e306  lea     rcx, [rbp+57h+LinkHandle]; LinkHandle
0x14000e30a  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000e30f  call    cs:__imp_ZwOpenSymbolicLinkObject
0x14000e316  nop     dword ptr [rax+rax+00h]
0x14000e31b  mov     ebx, eax
0x14000e31d  test    eax, eax
0x14000e31f  jns     short loc_14000E33C
0x14000e321  cmp     eax, 0C0000034h
0x14000e326  jz      short loc_14000E32D
0x14000e328  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14000e32d  mov     r8d, ebx
0x14000e330  lea     rdx, aWinsetupmonGet_0; "WinSetupMon::GetNtPath: Failed OpenSymb"...
0x14000e337  jmp     loc_14000E404
0x14000e33c  mov     rcx, [rbp+57h+LinkHandle]; LinkHandle
0x14000e340  lea     r8, [rbp+57h+ReturnedLength]; ReturnedLength
0x14000e344  mov     rdx, rdi; LinkTarget
0x14000e347  call    cs:__imp_ZwQuerySymbolicLinkObject
0x14000e34e  nop     dword ptr [rax+rax+00h]
0x14000e353  mov     ebx, eax
0x14000e355  cmp     eax, 0C0000023h
0x14000e35a  jnz     short loc_14000E3B8
0x14000e35c  movzx   eax, word ptr [rbp+57h+ReturnedLength]
0x14000e360  mov     ecx, 1; PoolType
0x14000e365  add     ax, [rbp+57h+Source.Length]
0x14000e369  mov     r8d, 6E6D7377h; Tag
0x14000e36f  movzx   edx, ax; NumberOfBytes
0x14000e372  mov     [rdi+2], dx
0x14000e376  call    cs:__imp_ExAllocatePoolWithTag
0x14000e37d  nop     dword ptr [rax+rax+00h]
0x14000e382  mov     [rdi+8], rax
0x14000e386  test    rax, rax
0x14000e389  jnz     short loc_14000E3A0
0x14000e38b  lea     rdx, aWinsetupmonGet_18; "WinSetupMon::GetNtPath: Failed to alloc"...
0x14000e392  xor     ecx, ecx
0x14000e394  call    ?WriteLog@@YAXW4LogLevel@@PEBDZZ; WriteLog(LogLevel,char const *,...)
0x14000e399  mov     ebx, 0C000009Ah
0x14000e39e  jmp     short loc_14000E40B
0x14000e3a0  mov     rcx, [rbp+57h+LinkHandle]; LinkHandle
0x14000e3a4  xor     r8d, r8d; ReturnedLength
0x14000e3a7  mov     rdx, rdi; LinkTarget
0x14000e3aa  call    cs:__imp_ZwQuerySymbolicLinkObject
0x14000e3b1  nop     dword ptr [rax+rax+00h]
0x14000e3b6  mov     ebx, eax
0x14000e3b8  test    ebx, ebx
0x14000e3ba  jns     short loc_14000E3C8
0x14000e3bc  mov     r8d, ebx
0x14000e3bf  lea     rdx, aWinsetupmonGet_20; "WinSetupMon::GetNtPath: Failed QuerySym"...
0x14000e3c6  jmp     short loc_14000E404
0x14000e3c8  mov     rax, [rdi+8]
0x14000e3cc  mov     [rsi+8], rax
0x14000e3d0  movzx   eax, word ptr [rdi]
0x14000e3d3  mov     [rsi+2], ax
0x14000e3d7  mov     [rsi], ax
0x14000e3da  cmp     [rbp+57h+Source.Length], r15w
0x14000e3df  jbe     short loc_14000E431
0x14000e3e1  lea     rdx, [rbp+57h+Source]; Source
0x14000e3e5  mov     rcx, rdi; Destination
0x14000e3e8  call    cs:__imp_RtlAppendUnicodeStringToString
0x14000e3ef  nop     dword ptr [rax+rax+00h]
0x14000e3f4  mov     ebx, eax
0x14000e3f6  test    eax, eax
0x14000e3f8  jns     short loc_14000E431
0x14000e3fa  mov     r8d, eax
0x14000e3fd  lea     rdx, aWinsetupmonGet_12; "WinSetupMon::GetNtPath: Failed RtlAppen"...
0x14000e404  xor     ecx, ecx
0x14000e406  call    ?WriteLog@@YAXW4LogLevel@@PEBDZZ; WriteLog(LogLevel,char const *,...)
0x14000e40b  mov     rcx, [rdi+8]; P
0x14000e40f  test    rcx, rcx
0x14000e412  jz      short loc_14000E425
0x14000e414  mov     edx, 6E6D7377h; Tag
0x14000e419  call    cs:__imp_ExFreePoolWithTag
0x14000e420  nop     dword ptr [rax+rax+00h]
0x14000e425  xorps   xmm0, xmm0
0x14000e428  xorps   xmm1, xmm1
0x14000e42b  movups  xmmword ptr [rdi], xmm0
0x14000e42e  movups  xmmword ptr [rsi], xmm1
0x14000e431  mov     rcx, [rbp+57h+LinkHandle]; Handle
0x14000e435  test    rcx, rcx
0x14000e438  jz      short loc_14000E446
0x14000e43a  call    cs:__imp_ZwClose
0x14000e441  nop     dword ptr [rax+rax+00h]
0x14000e446  cmp     [rbp+57h+arg_8], r15b
0x14000e44a  jz      short loc_14000E466
0x14000e44c  mov     rcx, [rbp+57h+P+8]; P
0x14000e450  test    rcx, rcx
0x14000e453  jz      short loc_14000E466
0x14000e455  mov     edx, 6E6D7377h; Tag
0x14000e45a  call    cs:__imp_ExFreePoolWithTag
0x14000e461  nop     dword ptr [rax+rax+00h]
0x14000e466  mov     eax, ebx
0x14000e468  mov     rbx, [rsp+0C0h+arg_0]
0x14000e470  add     rsp, 0A0h
0x14000e477  pop     r15
0x14000e479  pop     r14
0x14000e47b  pop     rdi
0x14000e47c  pop     rsi
0x14000e47d  pop     rbp
0x14000e47e  retn
```
