# SmpCheckForCrashDump

- ea: `0x140011438`
- end: `0x140011752`
- name: `SmpCheckForCrashDump`
- size: `794`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000fcf8`

## callees

- `0x140011438`
- `0x140011c50`
- `0x140011d24`
- `0x1400127a8`
- `0x14001cc05`
- `0x14001cc29`
- `0x14001cc40`

## import_xrefs

- `ntdll!NtOpenFile` at `0x140011525`
- `ntdll!NtOpenFile` at `0x140011525`
- `ntdll!NtClose` at `0x14001164f`
- `ntdll!NtClose` at `0x14001170a`
- `ntdll!NtClose` at `0x14001164f`
- `ntdll!NtClose` at `0x14001170a`
- `ntdll!NtSetValueKey` at `0x1400115ec`
- `ntdll!NtSetValueKey` at `0x1400116d6`
- `ntdll!NtSetValueKey` at `0x1400116ff`
- `ntdll!NtSetValueKey` at `0x1400115ec`
- `ntdll!NtSetValueKey` at `0x1400116d6`
- `ntdll!NtSetValueKey` at `0x1400116ff`
- `ntdll!RtlFreeUnicodeString` at `0x14001171f`
- `ntdll!RtlFreeUnicodeString` at `0x14001171f`
- `ntdll!NtReadFile` at `0x140011569`
- `ntdll!NtReadFile` at `0x140011569`
- `ntdll!NtCreateKey` at `0x1400116a5`
- `ntdll!NtCreateKey` at `0x1400116a5`

## string_xrefs

- `0x140011492`: `\Registry\Machine\System\CurrentControlSet\Control\CrashControl\MachineCrash`
- `0x1400114a9`: `TempDestination`

## pseudocode

```c
char __fastcall SmpCheckForCrashDump(struct _UNICODE_STRING *a1)
{
  char v2; // bl
  void *FileHandle; // [rsp+50h] [rbp-B0h] BYREF
  void *KeyHandle; // [rsp+58h] [rbp-A8h] BYREF
  __int64 Data; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v8[2]; // [rsp+78h] [rbp-88h] BYREF
  __int128 v9; // [rsp+88h] [rbp-78h] BYREF
  struct _UNICODE_STRING v10; // [rsp+98h] [rbp-68h] BYREF
  struct _UNICODE_STRING v11; // [rsp+A8h] [rbp-58h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B8h] [rbp-48h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v14; // [rsp+F8h] [rbp-8h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+100h] [rbp+0h] BYREF
  _DWORD Buffer[1000]; // [rsp+110h] [rbp+10h] BYREF
  char v17; // [rsp+1160h] [rbp+1060h]

  memset_0(Buffer, 0, 0x2000u);
  *(_QWORD *)&ObjectAttributes.Length = 48;
  v8[1] = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\CrashControl\\MachineCrash";
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  v11.Buffer = L"TempDestination";
  v8[0] = 10092696;
  v10.Buffer = L"DumpFile";
  *(_QWORD *)&v11.Length = 2097182;
  v14 = 0;
  *(_QWORD *)&v10.Length = 1179664;
  FileHandle = (void *)-1LL;
  IoStatusBlock = 0;
  KeyHandle = (void *)-1LL;
  UnicodeString = 0;
  ObjectAttributes.RootDirectory = 0;
  v9 = 0;
  ObjectAttributes.ObjectName = a1;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( NtOpenFile(&FileHandle, 0xC0150000, &ObjectAttributes, &IoStatusBlock, 3u, 0x68u) >= 0 )
  {
    v2 = 0;
    if ( NtReadFile(FileHandle, 0, 0, 0, &IoStatusBlock, Buffer, 0x2000u, 0, 0) >= 0
      && Buffer[0] == 1162297680
      && Buffer[1] == 875976004 )
    {
      if ( (v17 & 4) != 0 )
      {
        ValueName.Buffer = L"PagefileTooSmall";
        *(_QWORD *)&ValueName.Length = 2228256;
        Data = MEMORY[0x7FFE0014];
        NtSetValueKey(SmpCrashDumpKey, &ValueName, 0, 0xBu, &Data, 8u);
      }
      if ( (int)SmpGetCrashParameters(&UnicodeString) >= 0
        && (int)SmpGetDumpDestination(Buffer, &UnicodeString, FileHandle, a1, &v9) >= 0
        && (int)SmpSavePageFile(FileHandle) >= 0 )
      {
        v2 = 1;
      }
    }
    NtClose(FileHandle);
    FileHandle = (void *)-1LL;
    if ( v2 )
    {
      ObjectAttributes.ObjectName = (PUNICODE_STRING)v8;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      ObjectAttributes.Attributes = 64;
      if ( NtCreateKey(&KeyHandle, 0x2001Fu, &ObjectAttributes, 0, 0, 1u, 0) >= 0 )
      {
        NtSetValueKey(KeyHandle, &v10, 0, 1u, (PVOID)(*((_QWORD *)&v9 + 1) + 8LL), (unsigned __int16)v9 - 6);
        NtSetValueKey(KeyHandle, &v11, 0, 4u, (char *)&v14 + 4, 4u);
        NtClose(KeyHandle);
        KeyHandle = (void *)-1LL;
      }
    }
  }
  else
  {
    v2 = 0;
  }
  if ( UnicodeString.Length )
    RtlFreeUnicodeString(&UnicodeString);
  return v2;
}

```

## disassembly

```asm
0x140011438  mov     [rsp-8+arg_8], rbx
0x14001143d  mov     [rsp-8+arg_10], rsi
0x140011442  push    rbp
0x140011443  push    rdi
0x140011444  push    r12
0x140011446  push    r13
0x140011448  push    r14
0x14001144a  lea     rbp, [rsp-2020h]
0x140011452  mov     eax, 2120h
0x140011457  call    __chkstk_0
0x14001145c  sub     rsp, rax
0x14001145f  mov     rax, cs:__security_cookie
0x140011466  xor     rax, rsp
0x140011469  mov     [rbp+2040h+var_30], rax
0x140011470  mov     rdi, rcx
0x140011473  mov     r14d, 2000h
0x140011479  mov     r8d, r14d; Size
0x14001147c  lea     rcx, [rbp+2040h+Buffer]; void *
0x140011480  xor     edx, edx; Val
0x140011482  call    memset_0
0x140011487  xorps   xmm0, xmm0
0x14001148a  mov     [rsp+2140h+OpenOptions], 68h ; 'h'; OpenOptions
0x140011492  lea     rax, aRegistryMachin_52; "\\Registry\\Machine\\System\\CurrentCon"...
0x140011499  mov     qword ptr [rbp+2040h+ObjectAttributes.Length], 30h ; '0'
0x1400114a1  mov     [rbp+2040h+var_20C0], rax
0x1400114a5  lea     r9, [rbp+2040h+IoStatusBlock]; IoStatusBlock
0x1400114a9  lea     rax, aTempdestinatio; "TempDestination"
0x1400114b0  mov     qword ptr [rbp+2040h+ObjectAttributes.Attributes], 40h ; '@'
0x1400114b8  mov     [rbp+2040h+var_2098.Buffer], rax
0x1400114bc  lea     r8, [rbp+2040h+ObjectAttributes]; ObjectAttributes
0x1400114c0  lea     rax, aDumpfile; "DumpFile"
0x1400114c7  mov     [rsp+2140h+var_20C8], 9A0098h
0x1400114d0  mov     [rbp+2040h+var_20A8.Buffer], rax
0x1400114d4  lea     rcx, [rsp+2140h+FileHandle]; FileHandle
0x1400114d9  xor     eax, eax
0x1400114db  mov     qword ptr [rbp+2040h+var_2098.Length], 20001Eh
0x1400114e3  or      r12, 0FFFFFFFFFFFFFFFFh
0x1400114e7  mov     [rbp+2040h+var_2048], rax
0x1400114eb  xor     esi, esi
0x1400114ed  mov     qword ptr [rbp+2040h+var_20A8.Length], 120010h
0x1400114f5  mov     edx, 0C0150000h; DesiredAccess
0x1400114fa  mov     [rsp+2140h+FileHandle], r12
0x1400114ff  movups  xmmword ptr [rbp+2040h+IoStatusBlock], xmm0
0x140011503  mov     [rsp+2140h+KeyHandle], r12
0x140011508  movups  xmmword ptr [rbp+2040h+UnicodeString.Length], xmm0
0x14001150c  mov     [rbp+2040h+ObjectAttributes.RootDirectory], rsi
0x140011510  movups  [rbp+2040h+var_20B8], xmm0
0x140011514  mov     [rbp+2040h+ObjectAttributes.ObjectName], rdi
0x140011518  movdqu  xmmword ptr [rbp+2040h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001151d  mov     [rsp+2140h+ShareAccess], 3; ShareAccess
0x140011525  call    cs:__imp_NtOpenFile
0x14001152b  test    eax, eax
0x14001152d  jns     short loc_140011537
0x14001152f  mov     bl, sil
0x140011532  jmp     loc_140011715
0x140011537  mov     rcx, [rsp+2140h+FileHandle]; FileHandle
0x14001153c  lea     rax, [rbp+2040h+Buffer]
0x140011540  mov     [rsp+2140h+Key], rsi; Key
0x140011545  xor     r9d, r9d; ApcContext
0x140011548  mov     [rsp+2140h+ByteOffset], rsi; ByteOffset
0x14001154d  xor     r8d, r8d; ApcRoutine
0x140011550  mov     [rsp+2140h+Length], r14d; Length
0x140011555  xor     edx, edx; Event
0x140011557  mov     qword ptr [rsp+2140h+OpenOptions], rax; Buffer
0x14001155c  lea     rax, [rbp+2040h+IoStatusBlock]
0x140011560  mov     qword ptr [rsp+2140h+ShareAccess], rax; IoStatusBlock
0x140011565  movzx   ebx, sil
0x140011569  call    cs:__imp_NtReadFile
0x14001156f  mov     r14d, 1
0x140011575  test    eax, eax
0x140011577  js      loc_14001164A
0x14001157d  cmp     [rbp+2040h+Buffer], 45474150h
0x140011584  jnz     loc_14001164A
0x14001158a  cmp     [rbp+2040h+var_202C], 34365544h
0x140011591  jnz     loc_14001164A
0x140011597  test    [rbp+2040h+var_FE0], 4
0x14001159e  jz      short loc_1400115F2
0x1400115a0  mov     [rsp+2140h+Data], rsi
0x1400115a5  lea     rax, aPagefiletoosma; "PagefileTooSmall"
0x1400115ac  mov     [rsp+2140h+ValueName.Buffer], rax
0x1400115b1  lea     r9d, [r14+0Ah]; Type
0x1400115b5  mov     qword ptr [rsp+2140h+ValueName.Length], 220020h
0x1400115be  lea     rdx, [rsp+2140h+ValueName]; ValueName
0x1400115c3  mov     eax, 7FFE0014h
0x1400115c8  mov     [rsp+2140h+OpenOptions], 8; DataSize
0x1400115d0  xor     r8d, r8d; TitleIndex
0x1400115d3  mov     rax, [rax]
0x1400115d6  mov     rcx, cs:SmpCrashDumpKey; KeyHandle
0x1400115dd  mov     [rsp+2140h+Data], rax
0x1400115e2  lea     rax, [rsp+2140h+Data]
0x1400115e7  mov     qword ptr [rsp+2140h+ShareAccess], rax; Data
0x1400115ec  call    cs:__imp_NtSetValueKey
0x1400115f2  lea     rcx, [rbp+2040h+UnicodeString]
0x1400115f6  call    SmpGetCrashParameters
0x1400115fb  test    eax, eax
0x1400115fd  js      short loc_14001164A
0x1400115ff  mov     r8, [rsp+2140h+FileHandle]
0x140011604  lea     rax, [rbp+2040h+var_20B8]
0x140011608  mov     r9, rdi
0x14001160b  mov     qword ptr [rsp+2140h+ShareAccess], rax
0x140011610  lea     rdx, [rbp+2040h+UnicodeString]
0x140011614  lea     rcx, [rbp+2040h+Buffer]
0x140011618  call    SmpGetDumpDestination
0x14001161d  test    eax, eax
0x14001161f  js      short loc_14001164A
0x140011621  cmp     cs:SmpForceCopyDumpFile, sil
0x140011628  lea     rdx, [rbp+2040h+var_20B8]
0x14001162c  mov     r8, [rbp+2040h+var_1090]
0x140011633  mov     r9d, esi
0x140011636  mov     rcx, [rsp+2140h+FileHandle]; FileHandle
0x14001163b  cmovz   r9d, r14d
0x14001163f  call    SmpSavePageFile
0x140011644  test    eax, eax
0x140011646  cmovns  ebx, r14d
0x14001164a  mov     rcx, [rsp+2140h+FileHandle]; Handle
0x14001164f  call    cs:__imp_NtClose
0x140011655  mov     [rsp+2140h+FileHandle], r12
0x14001165a  test    bl, bl
0x14001165c  jz      loc_140011715
0x140011662  lea     rax, [rsp+2140h+var_20C8]
0x140011667  mov     qword ptr [rsp+2140h+Length], rsi; Disposition
0x14001166c  xorps   xmm0, xmm0
0x14001166f  mov     [rsp+2140h+OpenOptions], r14d; CreateOptions
0x140011674  xor     r9d, r9d; TitleIndex
0x140011677  mov     [rbp+2040h+ObjectAttributes.ObjectName], rax
0x14001167b  lea     r8, [rbp+2040h+ObjectAttributes]; ObjectAttributes
0x14001167f  mov     qword ptr [rsp+2140h+ShareAccess], rsi; Class
0x140011684  mov     edx, 2001Fh; DesiredAccess
0x140011689  mov     [rbp+2040h+ObjectAttributes.Length], 30h ; '0'
0x140011690  lea     rcx, [rsp+2140h+KeyHandle]; KeyHandle
0x140011695  mov     [rbp+2040h+ObjectAttributes.RootDirectory], rsi
0x140011699  movdqu  xmmword ptr [rbp+2040h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001169e  mov     [rbp+2040h+ObjectAttributes.Attributes], 40h ; '@'
0x1400116a5  call    cs:__imp_NtCreateKey
0x1400116ab  test    eax, eax
0x1400116ad  js      short loc_140011715
0x1400116af  movzx   ecx, word ptr [rbp+2040h+var_20B8]
0x1400116b3  lea     rdx, [rbp+2040h+var_20A8]; ValueName
0x1400116b7  mov     rax, qword ptr [rbp+2040h+var_20B8+8]
0x1400116bb  sub     ecx, 6
0x1400116be  mov     [rsp+2140h+OpenOptions], ecx; DataSize
0x1400116c2  add     rax, 8
0x1400116c6  mov     rcx, [rsp+2140h+KeyHandle]; KeyHandle
0x1400116cb  mov     r9d, r14d; Type
0x1400116ce  xor     r8d, r8d; TitleIndex
0x1400116d1  mov     qword ptr [rsp+2140h+ShareAccess], rax; Data
0x1400116d6  call    cs:__imp_NtSetValueKey
0x1400116dc  mov     rcx, [rsp+2140h+KeyHandle]; KeyHandle
0x1400116e1  lea     rax, [rbp+2040h+var_2048+4]
0x1400116e5  mov     [rsp+2140h+OpenOptions], 4; DataSize
0x1400116ed  lea     rdx, [rbp+2040h+var_2098]; ValueName
0x1400116f1  mov     r9d, 4; Type
0x1400116f7  mov     qword ptr [rsp+2140h+ShareAccess], rax; Data
0x1400116fc  xor     r8d, r8d; TitleIndex
0x1400116ff  call    cs:__imp_NtSetValueKey
0x140011705  mov     rcx, [rsp+2140h+KeyHandle]; Handle
0x14001170a  call    cs:__imp_NtClose
0x140011710  mov     [rsp+2140h+KeyHandle], r12
0x140011715  cmp     [rbp+2040h+UnicodeString.Length], si
0x140011719  jz      short loc_140011725
0x14001171b  lea     rcx, [rbp+2040h+UnicodeString]; UnicodeString
0x14001171f  call    cs:__imp_RtlFreeUnicodeString
0x140011725  mov     al, bl
0x140011727  mov     rcx, [rbp+2040h+var_30]
0x14001172e  xor     rcx, rsp; StackCookie
0x140011731  call    __security_check_cookie
0x140011736  lea     r11, [rsp+2140h+var_20]
0x14001173e  mov     rbx, [r11+38h]
0x140011742  mov     rsi, [r11+40h]
0x140011746  mov     rsp, r11
0x140011749  pop     r14
0x14001174b  pop     r13
0x14001174d  pop     r12
0x14001174f  pop     rdi
0x140011750  pop     rbp
0x140011751  retn
```
