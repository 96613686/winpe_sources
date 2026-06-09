# GetDriveLetter(_FLT_VOLUME *,ushort *)

- ea: `0x14000df1c`
- end: `0x14000e1c8`
- name: `?GetDriveLetter@@YAJPEAU_FLT_VOLUME@@PEAG@Z`
- size: `684`
- prototype: `__int64 __fastcall(PFLT_VOLUME Volume, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path, installer_update`

## callers

- `0x14001f410`
- `0x14001f6c0`

## callees

- `0x14000df1c`
- `0x14000e1d0`
- `0x14000f684`
- `0x14000f900`
- `0x14000fd40`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14000e042`
- `ntoskrnl!ObfDereferenceObject` at `0x14000e042`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e00f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e02c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e122`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e00f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e02c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e122`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000e15d`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000e15d`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x14000df98`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x14000df98`
- `FLTMGR!FltGetDiskDeviceObject` at `0x14000df69`
- `FLTMGR!FltGetDiskDeviceObject` at `0x14000df69`
- `FLTMGR!FltGetVolumeName` at `0x14000e0b7`
- `FLTMGR!FltGetVolumeName` at `0x14000e0b7`

## string_xrefs

- `0x14000e182`: `WinSetupMon::GetDriveLetter: Could not get NT path for drive letter %c (0x%08X)`

## pseudocode

```c
__int64 __fastcall GetDriveLetter(PFLT_VOLUME Volume, unsigned __int16 *a2)
{
  NTSTATUS v4; // eax
  unsigned int v5; // ebx
  NTSTATUS v6; // eax
  wchar_t v7; // di
  NTSTATUS v9; // eax
  unsigned __int16 v10; // si
  int NtPath; // eax
  BOOLEAN v12; // al
  wchar_t v13; // cx
  unsigned __int16 v14; // cx
  PDEVICE_OBJECT DiskDeviceObject; // [rsp+20h] [rbp-E0h] BYREF
  PVOID P[2]; // [rsp+28h] [rbp-D8h] BYREF
  struct _UNICODE_STRING VolumeName; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DosName; // [rsp+48h] [rbp-B8h] BYREF
  UNICODE_STRING String2; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING v20; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 v21; // [rsp+78h] [rbp-88h] BYREF
  int v22; // [rsp+7Ah] [rbp-86h]
  _BYTE v23[128]; // [rsp+80h] [rbp-80h] BYREF

  DiskDeviceObject = 0;
  DosName = 0;
  *(_OWORD *)P = 0;
  v4 = FltGetDiskDeviceObject(Volume, &DiskDeviceObject);
  v5 = v4;
  if ( v4 < 0 )
  {
    WriteLog(0, "WinSetupMon::GetDriveLetter: Failed FltGetDeviceObject (0x%08X)", (unsigned int)v4);
    goto LABEL_10;
  }
  v6 = IoVolumeDeviceToDosName(DiskDeviceObject, &DosName);
  v5 = v6;
  if ( v6 < 0 )
  {
    WriteLog(0, "WinSetupMon::GetDriveLetter: Failed IoVolumeDeviceToDosName (0x%08X)", v6);
    memset(v23, 0, sizeof(v23));
    *(_QWORD *)&VolumeName.Length = 0x800000;
    VolumeName.Buffer = (wchar_t *)v23;
    v9 = FltGetVolumeName(Volume, &VolumeName, 0);
    v5 = v9;
    if ( v9 < 0 )
    {
      WriteLog(0, "WinSetupMon::GetDriveLetter: FltGetVolumeName failed (0x%08X)", (unsigned int)v9);
      goto LABEL_10;
    }
    v10 = 65;
    v7 = 0;
    while ( v10 <= 0x5Au )
    {
      v22 = 58;
      v21 = v10;
      *(_QWORD *)&String2.Length = 393220;
      String2.Buffer = &v21;
      v20 = 0;
      if ( P[1] )
        ExFreePoolWithTag(P[1], 0x6E6D7377u);
      *(_OWORD *)P = 0;
      NtPath = GetNtPath(&String2, (PUNICODE_STRING)P, &v20);
      v5 = NtPath;
      if ( NtPath < 0 )
      {
        if ( NtPath != -1073741772 )
          WriteLog(0, "WinSetupMon::GetDriveLetter: Could not get NT path for drive letter %c (0x%08X)", v10, NtPath);
        v5 = 0;
      }
      else
      {
        v12 = RtlEqualUnicodeString(&VolumeName, (PCUNICODE_STRING)P, 1u);
        v13 = v10;
        if ( !v12 )
          v13 = v7;
        v7 = v13;
      }
      ++v10;
      if ( v7 )
        goto LABEL_31;
    }
    goto LABEL_9;
  }
  if ( DosName.Length < 4u )
    goto LABEL_9;
  v7 = *DosName.Buffer;
  if ( (unsigned __int16)(*DosName.Buffer - 97) > 0x19u && (unsigned __int16)(v7 - 65) > 0x19u )
    goto LABEL_9;
  if ( DosName.Buffer[1] != 58 )
    goto LABEL_9;
LABEL_31:
  if ( !v7 )
  {
LABEL_9:
    v5 = -1073741275;
    WriteLog(1, "WinSetupMon::GetDriveLetter: Could not find drive letter for volume");
    goto LABEL_10;
  }
  v14 = v7 - 32;
  if ( (unsigned __int16)(v7 - 97) > 0x19u )
    v14 = v7;
  *a2 = v14;
LABEL_10:
  if ( P[1] )
  {
    ExFreePoolWithTag(P[1], 0x6E6D7377u);
    P[1] = 0;
  }
  if ( DosName.Buffer )
    ExFreePoolWithTag(DosName.Buffer, 0);
  if ( DiskDeviceObject )
    ObfDereferenceObject(DiskDeviceObject);
  return v5;
}

```

## disassembly

```asm
0x14000df1c  mov     [rsp-8+arg_10], rbx
0x14000df21  push    rbp
0x14000df22  push    rsi
0x14000df23  push    rdi
0x14000df24  push    r12
0x14000df26  push    r13
0x14000df28  push    r14
0x14000df2a  push    r15
0x14000df2c  lea     rbp, [rsp-10h]
0x14000df31  sub     rsp, 110h
0x14000df38  mov     rax, cs:__security_cookie
0x14000df3f  xor     rax, rsp
0x14000df42  mov     [rbp+40h+var_40], rax
0x14000df46  mov     r12, rdx
0x14000df49  xorps   xmm0, xmm0
0x14000df4c  xorps   xmm1, xmm1
0x14000df4f  lea     rdx, [rsp+140h+DiskDeviceObject]; DiskDeviceObject
0x14000df54  xor     r13d, r13d
0x14000df57  mov     rdi, rcx
0x14000df5a  mov     [rsp+140h+DiskDeviceObject], r13
0x14000df5f  movups  xmmword ptr [rsp+140h+DosName.Length], xmm0
0x14000df64  movups  xmmword ptr [rsp+140h+P], xmm1
0x14000df69  call    cs:__imp_FltGetDiskDeviceObject
0x14000df70  nop     dword ptr [rax+rax+00h]
0x14000df75  mov     ebx, eax
0x14000df77  test    eax, eax
0x14000df79  jns     short loc_14000DF8E
0x14000df7b  lea     rdx, aWinsetupmonGet_14; "WinSetupMon::GetDriveLetter: Failed Flt"...
0x14000df82  mov     r8d, eax
0x14000df85  xor     ecx, ecx
0x14000df87  call    ?WriteLog@@YAXW4LogLevel@@PEBDZZ; WriteLog(LogLevel,char const *,...)
0x14000df8c  jmp     short loc_14000E000
0x14000df8e  mov     rcx, [rsp+140h+DiskDeviceObject]; VolumeDeviceObject
0x14000df93  lea     rdx, [rsp+140h+DosName]; DosName
0x14000df98  call    cs:__imp_IoVolumeDeviceToDosName
0x14000df9f  nop     dword ptr [rax+rax+00h]
0x14000dfa4  mov     ebx, eax
0x14000dfa6  mov     ecx, 1
0x14000dfab  test    eax, eax
0x14000dfad  js      loc_14000E078
0x14000dfb3  lea     r14d, [rcx+3]
0x14000dfb7  cmp     [rsp+140h+DosName.Length], r14w
0x14000dfbd  jb      short loc_14000DFEF
0x14000dfbf  mov     rax, [rsp+140h+DosName.Buffer]
0x14000dfc4  movzx   edi, word ptr [rax]
0x14000dfc7  lea     eax, [rdi-61h]
0x14000dfca  cmp     ax, 19h
0x14000dfce  jbe     short loc_14000DFD9
0x14000dfd0  lea     eax, [rdi-41h]
0x14000dfd3  cmp     ax, 19h
0x14000dfd7  ja      short loc_14000DFEF
0x14000dfd9  mov     rax, [rsp+140h+DosName.Buffer]
0x14000dfde  mov     r15d, 3Ah ; ':'
0x14000dfe4  cmp     [rax+2], r15w
0x14000dfe9  jz      loc_14000E1A7
0x14000dfef  lea     rdx, aWinsetupmonGet_2; "WinSetupMon::GetDriveLetter: Could not "...
0x14000dff6  mov     ebx, 0C0000225h
0x14000dffb  call    ?WriteLog@@YAXW4LogLevel@@PEBDZZ; WriteLog(LogLevel,char const *,...)
0x14000e000  mov     rcx, [rsp+140h+P+8]; P
0x14000e005  test    rcx, rcx
0x14000e008  jz      short loc_14000E020
0x14000e00a  mov     edx, 6E6D7377h; Tag
0x14000e00f  call    cs:__imp_ExFreePoolWithTag
0x14000e016  nop     dword ptr [rax+rax+00h]
0x14000e01b  mov     [rsp+140h+P+8], r13
0x14000e020  mov     rcx, [rsp+140h+DosName.Buffer]; P
0x14000e025  test    rcx, rcx
0x14000e028  jz      short loc_14000E038
0x14000e02a  xor     edx, edx; Tag
0x14000e02c  call    cs:__imp_ExFreePoolWithTag
0x14000e033  nop     dword ptr [rax+rax+00h]
0x14000e038  mov     rcx, [rsp+140h+DiskDeviceObject]; Object
0x14000e03d  test    rcx, rcx
0x14000e040  jz      short loc_14000E04E
0x14000e042  call    cs:__imp_ObfDereferenceObject
0x14000e049  nop     dword ptr [rax+rax+00h]
0x14000e04e  mov     eax, ebx
0x14000e050  mov     rcx, [rbp+40h+var_40]
0x14000e054  xor     rcx, rsp; StackCookie
0x14000e057  call    __security_check_cookie
0x14000e05c  mov     rbx, [rsp+140h+arg_10]
0x14000e064  add     rsp, 110h
0x14000e06b  pop     r15
0x14000e06d  pop     r14
0x14000e06f  pop     r13
0x14000e071  pop     r12
0x14000e073  pop     rdi
0x14000e074  pop     rsi
0x14000e075  pop     rbp
0x14000e076  retn
0x14000e078  mov     r8d, eax
0x14000e07b  lea     rdx, aWinsetupmonGet_11; "WinSetupMon::GetDriveLetter: Failed IoV"...
0x14000e082  xor     ecx, ecx
0x14000e084  call    ?WriteLog@@YAXW4LogLevel@@PEBDZZ; WriteLog(LogLevel,char const *,...)
0x14000e089  xor     edx, edx; Val
0x14000e08b  lea     rcx, [rbp+40h+var_C0]; void *
0x14000e08f  mov     r8d, 80h; Size
0x14000e095  call    memset
0x14000e09a  lea     rax, [rbp+40h+var_C0]
0x14000e09e  mov     qword ptr [rsp+140h+VolumeName.Length], 800000h
0x14000e0a7  xor     r8d, r8d; BufferSizeNeeded
0x14000e0aa  mov     [rsp+140h+VolumeName.Buffer], rax
0x14000e0af  lea     rdx, [rsp+140h+VolumeName]; VolumeName
0x14000e0b4  mov     rcx, rdi; Volume
0x14000e0b7  call    cs:__imp_FltGetVolumeName
0x14000e0be  nop     dword ptr [rax+rax+00h]
0x14000e0c3  mov     ebx, eax
0x14000e0c5  test    eax, eax
0x14000e0c7  jns     short loc_14000E0D5
0x14000e0c9  lea     rdx, aWinsetupmonGet_15; "WinSetupMon::GetDriveLetter: FltGetVolu"...
0x14000e0d0  jmp     loc_14000DF82
0x14000e0d5  mov     esi, 41h ; 'A'
0x14000e0da  mov     edi, r13d
0x14000e0dd  lea     ecx, [rsi-40h]
0x14000e0e0  lea     r15d, [rsi-7]
0x14000e0e4  cmp     si, 5Ah ; 'Z'
0x14000e0e8  ja      loc_14000DFEF
0x14000e0ee  mov     rcx, [rsp+140h+P+8]; P
0x14000e0f3  lea     rax, [rsp+140h+var_C8]
0x14000e0f8  mov     [rsp+140h+var_C6], r15d
0x14000e0fd  xorps   xmm0, xmm0
0x14000e100  mov     [rsp+140h+var_C8], si
0x14000e105  mov     qword ptr [rsp+140h+String2.Length], 60004h
0x14000e10e  mov     [rsp+140h+String2.Buffer], rax
0x14000e113  movups  xmmword ptr [rsp+140h+var_D8.Length], xmm0
0x14000e118  test    rcx, rcx
0x14000e11b  jz      short loc_14000E12E
0x14000e11d  mov     edx, 6E6D7377h; Tag
0x14000e122  call    cs:__imp_ExFreePoolWithTag
0x14000e129  nop     dword ptr [rax+rax+00h]
0x14000e12e  xorps   xmm0, xmm0
0x14000e131  lea     r8, [rsp+140h+var_D8]; struct _UNICODE_STRING *
0x14000e136  lea     rdx, [rsp+140h+P]; DestinationString
0x14000e13b  lea     rcx, [rsp+140h+String2]; String2
0x14000e140  movups  xmmword ptr [rsp+140h+P], xmm0
0x14000e145  call    ?GetNtPath@@YAJPEBU_UNICODE_STRING@@PEAU1@1@Z; GetNtPath(_UNICODE_STRING const *,_UNICODE_STRING *,_UNICODE_STRING *)
0x14000e14a  mov     ebx, eax
0x14000e14c  test    eax, eax
0x14000e14e  js      short loc_14000E177
0x14000e150  mov     r8b, 1; CaseInSensitive
0x14000e153  lea     rdx, [rsp+140h+P]; String2
0x14000e158  lea     rcx, [rsp+140h+VolumeName]; String1
0x14000e15d  call    cs:__imp_RtlEqualUnicodeString
0x14000e164  nop     dword ptr [rax+rax+00h]
0x14000e169  test    al, al
0x14000e16b  movzx   ecx, si
0x14000e16e  cmovz   cx, di
0x14000e172  movzx   edi, cx
0x14000e175  jmp     short loc_14000E196
0x14000e177  cmp     eax, 0C0000034h
0x14000e17c  jz      short loc_14000E193
0x14000e17e  movzx   r8d, si
0x14000e182  lea     rdx, aWinsetupmonGet_17; "WinSetupMon::GetDriveLetter: Could not "...
0x14000e189  mov     r9d, eax
0x14000e18c  xor     ecx, ecx
0x14000e18e  call    ?WriteLog@@YAXW4LogLevel@@PEBDZZ; WriteLog(LogLevel,char const *,...)
0x14000e193  mov     ebx, r13d
0x14000e196  mov     ecx, 1
0x14000e19b  add     si, cx
0x14000e19e  test    di, di
0x14000e1a1  jz      loc_14000E0E4
0x14000e1a7  test    di, di
0x14000e1aa  jz      loc_14000DFEF
0x14000e1b0  lea     eax, [rdi-61h]
0x14000e1b3  cmp     ax, 19h
0x14000e1b7  lea     ecx, [rdi-20h]
0x14000e1ba  cmova   cx, di
0x14000e1be  mov     [r12], cx
0x14000e1c3  jmp     loc_14000E000
```
