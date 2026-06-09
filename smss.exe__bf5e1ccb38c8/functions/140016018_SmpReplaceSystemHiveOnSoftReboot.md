# SmpReplaceSystemHiveOnSoftReboot

- ea: `0x140016018`
- end: `0x14001617b`
- name: `SmpReplaceSystemHiveOnSoftReboot`
- size: `355`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x14000c638`

## callees

- `0x14000d4c0`
- `0x140013fd8`
- `0x1400158e4`
- `0x140015ef8`
- `0x140016018`
- `0x140017d5c`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x14001605d`
- `ntdll!RtlInitUnicodeString` at `0x1400160b9`
- `ntdll!RtlInitUnicodeString` at `0x1400160ec`
- `ntdll!RtlInitUnicodeString` at `0x140016141`
- `ntdll!RtlInitUnicodeString` at `0x140016152`
- `ntdll!RtlInitUnicodeString` at `0x14001605d`
- `ntdll!RtlInitUnicodeString` at `0x1400160b9`
- `ntdll!RtlInitUnicodeString` at `0x1400160ec`
- `ntdll!RtlInitUnicodeString` at `0x140016141`
- `ntdll!RtlInitUnicodeString` at `0x140016152`
- `ntdll!NtClose` at `0x140016130`
- `ntdll!NtClose` at `0x140016130`

## string_xrefs

- `0x14001602d`: `\SystemRoot\System32\config\SYSTEM.ksr.tmp`
- `0x1400160ae`: `\SystemRoot\System32\config\SYSTEM`
- `0x1400160dd`: `Failed to replace system hive on soft reboot`
- `0x140016104`: `SmpReplaceSystemHiveOnSoftReboot`
- `0x140016136`: `\SystemRoot\System32\config\SYSTEM.LOG1`
- `0x140016147`: `\SystemRoot\System32\config\SYSTEM.LOG2`

## pseudocode

```c
__int64 SmpReplaceSystemHiveOnSoftReboot()
{
  int v0; // r9d
  __int64 result; // rax
  int v2; // eax
  unsigned __int64 v3; // rbx
  int v4[4]; // [rsp+30h] [rbp-49h] BYREF
  struct _UNICODE_STRING *p_DestinationString; // [rsp+40h] [rbp-39h]
  int v6; // [rsp+48h] [rbp-31h]
  int v7; // [rsp+4Ch] [rbp-2Dh]
  __int128 v8; // [rsp+50h] [rbp-29h]
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-19h] BYREF
  struct _UNICODE_STRING v10; // [rsp+70h] [rbp-9h] BYREF
  struct _UNICODE_STRING v11; // [rsp+80h] [rbp+7h] BYREF
  struct _UNICODE_STRING v12; // [rsp+90h] [rbp+17h] BYREF
  struct _UNICODE_STRING v13; // [rsp+A0h] [rbp+27h] BYREF
  unsigned __int64 Parameters[2]; // [rsp+B0h] [rbp+37h] BYREF
  __int128 v15; // [rsp+C0h] [rbp+47h]
  HANDLE Handle; // [rsp+E0h] [rbp+67h] BYREF

  Handle = 0;
  v7 = 0;
  v10 = 0;
  v12 = 0;
  v13 = 0;
  v4[1] = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\SystemRoot\\System32\\config\\SYSTEM.ksr.tmp");
  v4[0] = 48;
  p_DestinationString = &DestinationString;
  LOBYTE(v0) = 1;
  *(_QWORD *)&v4[2] = 0;
  v6 = 64;
  v8 = 0;
  result = SmpOpenTargetFile((int)&Handle, 1114112, (int)v4, v0, 3u);
  if ( (int)result >= 0 )
  {
    RtlInitUnicodeString(&v10, L"\\SystemRoot\\System32\\config\\SYSTEM");
    v2 = SmpRenameTargetFile(&v10, Handle, 1, 0);
    v3 = v2;
    if ( v2 < 0 )
    {
      v11 = 0;
      RtlInitUnicodeString(&v11, L"Failed to replace system hive on soft reboot");
      Parameters[1] = v3;
      Parameters[0] = (unsigned __int64)&v11;
      v15 = 0;
      SmpLogFailure("SmpReplaceSystemHiveOnSoftReboot", 13082, (unsigned int)v3);
      SmpTerminate(Parameters, 1u, 4u);
    }
    NtClose(Handle);
    RtlInitUnicodeString(&v12, L"\\SystemRoot\\System32\\config\\SYSTEM.LOG1");
    RtlInitUnicodeString(&v13, L"\\SystemRoot\\System32\\config\\SYSTEM.LOG2");
    SmpDeleteFile(&v12);
    return SmpDeleteFile(&v13);
  }
  return result;
}

```

## disassembly

```asm
0x140016018  mov     [rsp-8+arg_8], rbx
0x14001601d  push    rbp
0x14001601e  lea     rbp, [rsp-57h]
0x140016023  sub     rsp, 0D0h
0x14001602a  xorps   xmm0, xmm0
0x14001602d  lea     rdx, aSystemrootSyst; "\\SystemRoot\\System32\\config\\SYSTEM."...
0x140016034  xorps   xmm1, xmm1
0x140016037  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14001603b  xor     eax, eax
0x14001603d  movups  [rbp+57h+var_90], xmm0
0x140016041  mov     [rbp+57h+Handle], rax
0x140016045  movups  [rbp+57h+var_90+0Ch], xmm0
0x140016049  movups  xmmword ptr [rbp+57h+var_60.Length], xmm0
0x14001604d  movups  xmmword ptr [rbp+57h+var_40.Length], xmm1
0x140016051  movups  xmmword ptr [rbp+57h+var_30.Length], xmm0
0x140016055  movups  xmmword ptr [rbp+57h+var_A0], xmm0
0x140016059  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14001605d  call    cs:__imp_RtlInitUnicodeString
0x140016063  lea     rax, [rbp+57h+DestinationString]
0x140016067  mov     [rbp+57h+var_A0], 30h ; '0'
0x14001606e  xorps   xmm0, xmm0
0x140016071  mov     qword ptr [rbp+57h+var_90], rax
0x140016075  mov     r9b, 1; int
0x140016078  mov     qword ptr [rbp+57h+var_A0+8], 0
0x140016080  lea     r8, [rbp+57h+var_A0]; int
0x140016084  mov     dword ptr [rbp+57h+var_90+8], 40h ; '@'
0x14001608b  mov     edx, 110000h; int
0x140016090  mov     [rsp+0D0h+var_B0], 3; ULONG
0x140016098  lea     rcx, [rbp+57h+Handle]; int
0x14001609c  movdqu  [rbp+57h+var_80], xmm0
0x1400160a1  call    SmpOpenTargetFile
0x1400160a6  test    eax, eax
0x1400160a8  js      loc_14001616A
0x1400160ae  lea     rdx, aSystemrootSyst_1; "\\SystemRoot\\System32\\config\\SYSTEM"
0x1400160b5  lea     rcx, [rbp+57h+var_60]; DestinationString
0x1400160b9  call    cs:__imp_RtlInitUnicodeString
0x1400160bf  mov     rdx, [rbp+57h+Handle]
0x1400160c3  lea     rcx, [rbp+57h+var_60]
0x1400160c7  xor     r9d, r9d
0x1400160ca  lea     r8d, [r9+1]
0x1400160ce  call    SmpRenameTargetFile
0x1400160d3  movsxd  rbx, eax
0x1400160d6  test    eax, eax
0x1400160d8  jns     short loc_14001612C
0x1400160da  xorps   xmm0, xmm0
0x1400160dd  lea     rdx, aFailedToReplac; "Failed to replace system hive on soft r"...
0x1400160e4  lea     rcx, [rbp+57h+var_50]; DestinationString
0x1400160e8  movups  xmmword ptr [rbp+57h+var_50.Length], xmm0
0x1400160ec  call    cs:__imp_RtlInitUnicodeString
0x1400160f2  lea     rax, [rbp+57h+var_50]
0x1400160f6  mov     [rbp+57h+var_18], rbx
0x1400160fa  xorps   xmm0, xmm0
0x1400160fd  mov     [rbp+57h+Parameters], rax
0x140016101  mov     r8d, ebx
0x140016104  lea     rcx, aSmpreplacesyst; "SmpReplaceSystemHiveOnSoftReboot"
0x14001610b  mov     edx, 331Ah
0x140016110  movups  [rbp+57h+var_10], xmm0
0x140016114  call    SmpLogFailure
0x140016119  mov     edx, 1; UnicodeStringParameterMask
0x14001611e  lea     rcx, [rbp+57h+Parameters]; Parameters
0x140016122  lea     r8d, [rdx+3]; NumberOfParameters
0x140016126  call    SmpTerminate
0x14001612c  mov     rcx, [rbp+57h+Handle]; Handle
0x140016130  call    cs:__imp_NtClose
0x140016136  lea     rdx, aSystemrootSyst_3; "\\SystemRoot\\System32\\config\\SYSTEM."...
0x14001613d  lea     rcx, [rbp+57h+var_40]; DestinationString
0x140016141  call    cs:__imp_RtlInitUnicodeString
0x140016147  lea     rdx, aSystemrootSyst_4; "\\SystemRoot\\System32\\config\\SYSTEM."...
0x14001614e  lea     rcx, [rbp+57h+var_30]; DestinationString
0x140016152  call    cs:__imp_RtlInitUnicodeString
0x140016158  lea     rcx, [rbp+57h+var_40]
0x14001615c  call    SmpDeleteFile
0x140016161  lea     rcx, [rbp+57h+var_30]
0x140016165  call    SmpDeleteFile
0x14001616a  mov     rbx, [rsp+0D0h+arg_8]
0x140016172  add     rsp, 0D0h
0x140016179  pop     rbp
0x14001617a  retn
```
