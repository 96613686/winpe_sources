# SdbRegisterDatabaseEx

- ea: `0x140017ef8`
- end: `0x14001850d`
- name: `SdbRegisterDatabaseEx`
- size: `1557`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140004df8`

## callees

- `0x14000d854`
- `0x14000fc40`
- `0x14001008c`
- `0x140015b08`
- `0x140017ef8`
- `0x14002e3e2`
- `0x14002e420`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400183e0`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400183e0`
- `msvcrt!wcschr` at `0x140017fa2`
- `msvcrt!wcschr` at `0x140017fa2`
- `ntdll!RtlInitUnicodeString` at `0x140017fbd`
- `ntdll!RtlInitUnicodeString` at `0x1400180ae`
- `ntdll!RtlInitUnicodeString` at `0x140018180`
- `ntdll!RtlInitUnicodeString` at `0x140017fbd`
- `ntdll!RtlInitUnicodeString` at `0x1400180ae`
- `ntdll!RtlInitUnicodeString` at `0x140018180`
- `ntdll!RtlAllocateHeap` at `0x140018023`
- `ntdll!RtlAllocateHeap` at `0x140018023`
- `ntdll!NtClose` at `0x1400184cb`
- `ntdll!NtClose` at `0x1400184da`
- `ntdll!NtClose` at `0x1400184cb`
- `ntdll!NtClose` at `0x1400184da`
- `ntdll!RtlFreeHeap` at `0x140018497`
- `ntdll!RtlFreeHeap` at `0x1400184bb`
- `ntdll!RtlFreeHeap` at `0x140018497`
- `ntdll!RtlFreeHeap` at `0x1400184bb`
- `ntdll!RtlAppendUnicodeStringToString` at `0x140018166`
- `ntdll!RtlAppendUnicodeStringToString` at `0x140018166`
- `ntdll!RtlAppendUnicodeToString` at `0x140018147`
- `ntdll!RtlAppendUnicodeToString` at `0x140018158`
- `ntdll!RtlAppendUnicodeToString` at `0x140018147`
- `ntdll!RtlAppendUnicodeToString` at `0x140018158`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x140017fd3`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x140018072`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x140017fd3`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x140018072`
- `ntdll!NtCreateKey` at `0x1400181cc`
- `ntdll!NtCreateKey` at `0x14001824b`
- `ntdll!NtCreateKey` at `0x1400181cc`
- `ntdll!NtCreateKey` at `0x14001824b`
- `ntdll!NtSetValueKey` at `0x14001828d`
- `ntdll!NtSetValueKey` at `0x1400182f2`
- `ntdll!NtSetValueKey` at `0x140018341`
- `ntdll!NtSetValueKey` at `0x1400183a7`
- `ntdll!NtSetValueKey` at `0x140018418`
- `ntdll!NtSetValueKey` at `0x14001828d`
- `ntdll!NtSetValueKey` at `0x1400182f2`
- `ntdll!NtSetValueKey` at `0x140018341`
- `ntdll!NtSetValueKey` at `0x1400183a7`
- `ntdll!NtSetValueKey` at `0x140018418`
- `ntdll!NtSetInformationKey` at `0x140018455`
- `ntdll!NtSetInformationKey` at `0x140018455`

## string_xrefs

- `0x1400182a7`: `DatabasePath`
- `0x14001842d`: `DatabaseInstallTimeStamp`
- `0x140018138`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\InstalledSDB`
- `0x140018175`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\InstalledSDB`
- `0x140018037`: `Failed to allocate 0x%lx bytes for the path buffer "%ws"`
- `0x1400181e4`: `Failed to create key "%ws" [%x]`
- `0x140018463`: `Failed to set last write time on key [%x]`

## pseudocode

```c
__int64 __fastcall SdbRegisterDatabaseEx(PCWSTR SourceString, __int64 a2, struct _FILETIME *a3)
{
  unsigned int v5; // r15d
  NTSTATUS v6; // eax
  int v8; // r14d
  NTSTATUS v9; // eax
  int DatabaseInformationByName; // eax
  _QWORD *v11; // rbx
  const char *v12; // r9
  __int64 v13; // r8
  int v14; // eax
  NTSTATUS v15; // eax
  __int64 v16; // r8
  PWSTR Buffer; // rax
  NTSTATUS v18; // eax
  NTSTATUS v19; // eax
  NTSTATUS v20; // eax
  NTSTATUS v21; // eax
  _WORD *v22; // rcx
  __int64 v23; // rax
  NTSTATUS v24; // eax
  struct _FILETIME v25; // rax
  NTSTATUS v26; // eax
  NTSTATUS v27; // eax
  PUNICODE_STRING Class; // [rsp+20h] [rbp-E0h]
  ULONG CreateOptions[2]; // [rsp+28h] [rbp-D8h]
  ULONG CreateOptionsa[2]; // [rsp+28h] [rbp-D8h]
  ULONG CreateOptionsb[2]; // [rsp+28h] [rbp-D8h]
  ULONG CreateOptionsc[2]; // [rsp+28h] [rbp-D8h]
  PULONG Disposition; // [rsp+30h] [rbp-D0h]
  ULONG Length; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+50h] [rbp-B0h] BYREF
  ULONG v37[4]; // [rsp+60h] [rbp-A0h] BYREF
  int Data[4]; // [rsp+70h] [rbp-90h] BYREF
  struct _FILETIME v39; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING v40; // [rsp+88h] [rbp-78h] BYREF
  PVOID P; // [rsp+98h] [rbp-68h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+A0h] [rbp-60h] BYREF
  struct _FILETIME KeySetInformation; // [rsp+A8h] [rbp-58h] BYREF
  void *KeyHandle; // [rsp+B0h] [rbp-50h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B8h] [rbp-48h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+E8h] [rbp-18h] BYREF
  UNICODE_STRING Source; // [rsp+F8h] [rbp-8h] BYREF
  struct _UNICODE_STRING v48; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v49[528]; // [rsp+120h] [rbp+20h] BYREF

  Data[0] = 0x10000;
  P = 0;
  v5 = 0;
  DestinationString = 0;
  Destination = 0;
  v48 = 0;
  v40 = 0;
  Source = 0;
  memset_0(v49, 0, 0x208u);
  KeyHandle = 0;
  Handle = 0;
  v37[0] = 0;
  Length = 0;
  SystemTimeAsFileTime = 0;
  memset(&ObjectAttributes, 0, 44);
  v39 = 0;
  KeySetInformation = 0;
  if ( !wcschr(SourceString, 0x25u) )
  {
    v8 = 0;
    RtlInitUnicodeString(&Destination, SourceString);
    goto LABEL_10;
  }
  RtlInitUnicodeString(&DestinationString, SourceString);
  v6 = RtlExpandEnvironmentStrings_U(0, &DestinationString, &Destination, &Length);
  if ( v6 != -1073741789 )
  {
    AslLogCallPrintf(
      1,
      "SdbRegisterDatabaseEx",
      994,
      "Failed to expand environment strings for \"%ws\" [%x]",
      SourceString,
      v6);
    return 0;
  }
  Destination.Buffer = (PWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, Length);
  if ( !Destination.Buffer )
  {
    AslLogCallPrintf(
      1,
      "SdbRegisterDatabaseEx",
      1004,
      "Failed to allocate 0x%lx bytes for the path buffer \"%ws\"",
      Length,
      SourceString);
    return 0;
  }
  Destination.MaximumLength = Length;
  Destination.Length = 0;
  v8 = 1;
  v9 = RtlExpandEnvironmentStrings_U(0, &DestinationString, &Destination, &Length);
  if ( v9 >= 0 )
  {
LABEL_10:
    DatabaseInformationByName = SdbGetDatabaseInformationByName((__int64)Destination.Buffer, &P);
    v11 = P;
    if ( !DatabaseInformationByName )
    {
      v12 = "Cannot obtain database information for \"%ws\"";
      v13 = 1030;
LABEL_12:
      AslLogCallPrintf(1, "SdbRegisterDatabaseEx", v13, v12, Destination.Buffer);
      goto LABEL_44;
    }
    if ( (*(_BYTE *)P & 1) == 0 )
    {
      v12 = "Cannot register database with no id \"%ws\"";
      v13 = 1035;
      goto LABEL_12;
    }
    v14 = AslGuidToString_UStr(&Source, (char *)P + 24);
    if ( v14 < 0 )
    {
      AslLogCallPrintf(1, "SdbRegisterDatabaseEx", 1041, "Cannot convert guid to unicode string [%x]", v14);
      goto LABEL_44;
    }
    *(_DWORD *)&v40.Length = 34078720;
    v40.Buffer = (PWSTR)v49;
    RtlAppendUnicodeToString(
      &v40,
      L"\\Registry\\Machine\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\InstalledSDB");
    RtlAppendUnicodeToString(&v40, L"\\");
    RtlAppendUnicodeStringToString(&v40, &Source);
    AslAnsiStringFree(&Source);
    RtlInitUnicodeString(
      &v48,
      L"\\Registry\\Machine\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\InstalledSDB");
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &v48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v15 = NtCreateKey(&KeyHandle, 0x2010Fu, &ObjectAttributes, 0, 0, 0, v37);
    if ( v15 >= 0 )
    {
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &v40;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v18 = NtCreateKey(&Handle, 0x2010Fu, &ObjectAttributes, 0, 0, 0, v37);
      if ( v18 >= 0 )
      {
        v19 = NtSetValueKey(
                Handle,
                (PUNICODE_STRING)&g_ustrDatabasePath,
                0,
                1u,
                Destination.Buffer,
                Destination.MaximumLength);
        if ( v19 >= 0 )
        {
          v20 = NtSetValueKey(Handle, (PUNICODE_STRING)&g_ustrDatabaseType, 0, 4u, Data, 4u);
          if ( v20 >= 0 )
          {
            v21 = NtSetValueKey(Handle, (PUNICODE_STRING)&g_ustrRuntimePlatform, 0, 4u, v11 + 5, 4u);
            if ( v21 >= 0 )
            {
              v22 = (_WORD *)v11[2];
              if ( !v22 )
                goto LABEL_36;
              v23 = -1;
              do
                ++v23;
              while ( v22[v23] );
              v24 = NtSetValueKey(Handle, (PUNICODE_STRING)&g_ustrDatabaseDescription, 0, 1u, v22, 2 * v23 + 2);
              if ( v24 < 0 )
              {
                LODWORD(Disposition) = v24;
                AslLogCallPrintf(
                  1,
                  "SdbRegisterDatabaseEx",
                  1160,
                  "Failed to set value \"%ws\" to %ws [%x]",
                  L"DatabaseDescription",
                  v11[2],
                  Disposition);
              }
              else
              {
LABEL_36:
                if ( a3 )
                {
                  v25 = *a3;
                }
                else
                {
                  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
                  v25 = SystemTimeAsFileTime;
                }
                v39 = v25;
                v26 = NtSetValueKey(Handle, (PUNICODE_STRING)&g_ustrInstallTimeStamp, 0, 0xBu, &v39, 8u);
                if ( v26 >= 0 )
                {
                  KeySetInformation = v39;
                  v27 = NtSetInformationKey(Handle, KeyWriteTimeInformation, &KeySetInformation, 8u);
                  if ( v27 >= 0 )
                  {
                    v5 = 1;
                  }
                  else
                  {
                    LODWORD(Class) = v27;
                    AslLogCallPrintf(
                      1,
                      "SdbRegisterDatabaseEx",
                      1199,
                      "Failed to set last write time on key [%x]",
                      Class);
                  }
                }
                else
                {
                  CreateOptionsc[0] = v26;
                  AslLogCallPrintf(
                    1,
                    "SdbRegisterDatabaseEx",
                    1184,
                    "Failed to set value \"%ws\" [%x]",
                    L"DatabaseInstallTimeStamp",
                    *(_QWORD *)CreateOptionsc);
                }
              }
            }
            else
            {
              LODWORD(Disposition) = v21;
              CreateOptionsb[0] = *((_DWORD *)v11 + 10);
              AslLogCallPrintf(
                1,
                "SdbRegisterDatabaseEx",
                1147,
                "Failed to set value \"%ws\" to 0x%lx [%x]",
                L"DatabaseRuntimePlatform",
                *(_QWORD *)CreateOptionsb,
                Disposition);
            }
          }
          else
          {
            LODWORD(Disposition) = v20;
            CreateOptionsa[0] = Data[0];
            AslLogCallPrintf(
              1,
              "SdbRegisterDatabaseEx",
              1135,
              "Failed to set value \"%ws\" to 0x%lx [%x]",
              L"DatabaseType",
              *(_QWORD *)CreateOptionsa,
              Disposition);
          }
        }
        else
        {
          LODWORD(Disposition) = v19;
          AslLogCallPrintf(
            1,
            "SdbRegisterDatabaseEx",
            1123,
            "Failed to set value \"%ws\" to \"%ws\" [%x]",
            L"DatabasePath",
            SourceString,
            Disposition);
        }
LABEL_44:
        if ( v11 && (*(_DWORD *)v11 & 0x10000000) != 0 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
        if ( !v8 )
          goto LABEL_50;
        goto LABEL_48;
      }
      CreateOptions[0] = v18;
      v16 = 1108;
      Buffer = v40.Buffer;
    }
    else
    {
      CreateOptions[0] = v15;
      v16 = 1084;
      Buffer = v48.Buffer;
    }
    AslLogCallPrintf(
      1,
      "SdbRegisterDatabaseEx",
      v16,
      "Failed to create key \"%ws\" [%x]",
      Buffer,
      *(_QWORD *)CreateOptions);
    goto LABEL_44;
  }
  AslLogCallPrintf(
    1,
    "SdbRegisterDatabaseEx",
    1017,
    "Failed to expand environment strings for \"%ws\" [%x]",
    SourceString,
    v9);
LABEL_48:
  if ( Destination.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Destination.Buffer);
LABEL_50:
  if ( Handle )
    NtClose(Handle);
  if ( KeyHandle )
    NtClose(KeyHandle);
  return v5;
}

```

## disassembly

```asm
0x140017ef8  mov     [rsp-8+arg_8], rbx
0x140017efd  push    rbp
0x140017efe  push    rsi
0x140017eff  push    rdi
0x140017f00  push    r12
0x140017f02  push    r13
0x140017f04  push    r14
0x140017f06  push    r15
0x140017f08  lea     rbp, [rsp-240h]
0x140017f10  sub     rsp, 340h
0x140017f17  mov     rax, cs:__security_cookie
0x140017f1e  xor     rax, rsp
0x140017f21  mov     [rbp+270h+var_40], rax
0x140017f28  xorps   xmm0, xmm0
0x140017f2b  mov     [rsp+370h+Data], 10000h
0x140017f33  xorps   xmm1, xmm1
0x140017f36  mov     rsi, r8
0x140017f39  mov     rdi, rcx
0x140017f3c  xor     r12d, r12d
0x140017f3f  mov     r8d, 208h; Size
0x140017f45  mov     [rbp+270h+P], r12
0x140017f49  lea     rcx, [rbp+270h+var_250]; void *
0x140017f4d  xor     edx, edx; Val
0x140017f4f  mov     r15d, r12d
0x140017f52  movups  xmmword ptr [rbp+270h+DestinationString.Length], xmm0
0x140017f56  movups  xmmword ptr [rsp+370h+Destination.Length], xmm1
0x140017f5b  movups  xmmword ptr [rbp+270h+var_268.Length], xmm0
0x140017f5f  movups  xmmword ptr [rbp+270h+var_2E8.Length], xmm1
0x140017f63  movups  xmmword ptr [rbp+270h+Source.Length], xmm0
0x140017f67  call    memset_0
0x140017f6c  xorps   xmm0, xmm0
0x140017f6f  mov     [rbp+270h+KeyHandle], r12
0x140017f73  xor     eax, eax
0x140017f75  mov     [rsp+370h+Handle], r12
0x140017f7a  movups  xmmword ptr [rbp+270h+ObjectAttributes.ObjectName], xmm0
0x140017f7e  mov     rcx, rdi; Str
0x140017f81  mov     [rsp+370h+var_310], r12d
0x140017f86  mov     [rsp+370h+Length], r12d
0x140017f8b  lea     edx, [rax+25h]; Ch
0x140017f8e  mov     qword ptr [rbp+270h+SystemTimeAsFileTime.dwLowDateTime], r12
0x140017f92  movups  xmmword ptr [rbp+270h+ObjectAttributes.Length], xmm0
0x140017f96  mov     [rbp+270h+var_2F0], r12
0x140017f9a  movups  xmmword ptr [rbp+270h+ObjectAttributes+1Ch], xmm0
0x140017f9e  mov     [rbp+270h+KeySetInformation], r12
0x140017fa2  call    cs:__imp_wcschr
0x140017fa8  lea     r13d, [r12+1]
0x140017fad  mov     rdx, rdi; SourceString
0x140017fb0  test    rax, rax
0x140017fb3  jz      loc_1400180A6
0x140017fb9  lea     rcx, [rbp+270h+DestinationString]; DestinationString
0x140017fbd  call    cs:__imp_RtlInitUnicodeString
0x140017fc3  lea     r9, [rsp+370h+Length]; Length
0x140017fc8  xor     ecx, ecx; Environment
0x140017fca  lea     r8, [rsp+370h+Destination]; Destination
0x140017fcf  lea     rdx, [rbp+270h+DestinationString]; Source
0x140017fd3  call    cs:__imp_RtlExpandEnvironmentStrings_U
0x140017fd9  cmp     eax, 0C0000023h
0x140017fde  jz      short loc_14001800C
0x140017fe0  mov     [rsp+370h+CreateOptions], eax
0x140017fe4  lea     r9, aFailedToExpand_4; "Failed to expand environment strings fo"...
0x140017feb  mov     [rsp+370h+Class], rdi
0x140017ff0  mov     r8d, 3E2h
0x140017ff6  lea     rdx, aSdbregisterdat; "SdbRegisterDatabaseEx"
0x140017ffd  mov     ecx, r13d
0x140018000  call    AslLogCallPrintf
0x140018005  xor     eax, eax
0x140018007  jmp     loc_1400184E3
0x14001800c  mov     rcx, gs:60h
0x140018015  mov     edx, 8; Flags
0x14001801a  mov     r8d, [rsp+370h+Length]; Size
0x14001801f  mov     rcx, [rcx+30h]; HeapHandle
0x140018023  call    cs:__imp_RtlAllocateHeap
0x140018029  mov     [rsp+370h+Destination.Buffer], rax
0x14001802e  test    rax, rax
0x140018031  jnz     short loc_14001804F
0x140018033  mov     eax, [rsp+370h+Length]
0x140018037  lea     r9, aFailedToAlloca_4; "Failed to allocate 0x%lx bytes for the "...
0x14001803e  mov     qword ptr [rsp+370h+CreateOptions], rdi
0x140018043  mov     r8d, 3ECh
0x140018049  mov     dword ptr [rsp+370h+Class], eax
0x14001804d  jmp     short loc_140017FF6
0x14001804f  movzx   eax, word ptr [rsp+370h+Length]
0x140018054  lea     r9, [rsp+370h+Length]; Length
0x140018059  lea     r8, [rsp+370h+Destination]; Destination
0x14001805e  mov     [rsp+370h+Destination.MaximumLength], ax
0x140018063  lea     rdx, [rbp+270h+DestinationString]; Source
0x140018067  mov     [rsp+370h+Destination.Length], r12w
0x14001806d  xor     ecx, ecx; Environment
0x14001806f  mov     r14d, r13d
0x140018072  call    cs:__imp_RtlExpandEnvironmentStrings_U
0x140018078  test    eax, eax
0x14001807a  jns     short loc_1400180B4
0x14001807c  mov     [rsp+370h+CreateOptions], eax
0x140018080  lea     r9, aFailedToExpand_4; "Failed to expand environment strings fo"...
0x140018087  mov     r8d, 3F9h
0x14001808d  mov     [rsp+370h+Class], rdi
0x140018092  lea     rdx, aSdbregisterdat; "SdbRegisterDatabaseEx"
0x140018099  mov     ecx, r13d
0x14001809c  call    AslLogCallPrintf
0x1400180a1  jmp     loc_1400184A2
0x1400180a6  lea     rcx, [rsp+370h+Destination]; DestinationString
0x1400180ab  mov     r14d, r12d
0x1400180ae  call    cs:__imp_RtlInitUnicodeString
0x1400180b4  mov     rcx, [rsp+370h+Destination.Buffer]
0x1400180b9  lea     rdx, [rbp+270h+P]
0x1400180bd  call    SdbGetDatabaseInformationByName
0x1400180c2  mov     rbx, [rbp+270h+P]
0x1400180c6  test    eax, eax
0x1400180c8  jnz     short loc_1400180F5
0x1400180ca  lea     r9, aCannotObtainDa; "Cannot obtain database information for "...
0x1400180d1  mov     r8d, 406h
0x1400180d7  mov     rax, [rsp+370h+Destination.Buffer]
0x1400180dc  mov     [rsp+370h+Class], rax
0x1400180e1  lea     rdx, aSdbregisterdat; "SdbRegisterDatabaseEx"
0x1400180e8  mov     ecx, r13d
0x1400180eb  call    AslLogCallPrintf
0x1400180f0  jmp     loc_140018478
0x1400180f5  test    [rbx], r13b
0x1400180f8  jnz     short loc_140018109
0x1400180fa  lea     r9, aCannotRegister; "Cannot register database with no id \"%"...
0x140018101  mov     r8d, 40Bh
0x140018107  jmp     short loc_1400180D7
0x140018109  lea     rdx, [rbx+18h]
0x14001810d  lea     rcx, [rbp+270h+Source]
0x140018111  call    AslGuidToString_UStr
0x140018116  test    eax, eax
0x140018118  jns     short loc_14001812D
0x14001811a  mov     dword ptr [rsp+370h+Class], eax
0x14001811e  lea     r9, aCannotConvertG; "Cannot convert guid to unicode string ["...
0x140018125  mov     r8d, 411h
0x14001812b  jmp     short loc_1400180E1
0x14001812d  lea     rax, [rbp+270h+var_250]
0x140018131  mov     dword ptr [rbp+270h+var_2E8.Length], 2080000h
0x140018138  lea     rdx, aRegistryMachin_2; "\\Registry\\Machine\\Software\\Microsof"...
0x14001813f  mov     [rbp+270h+var_2E8.Buffer], rax
0x140018143  lea     rcx, [rbp+270h+var_2E8]; Destination
0x140018147  call    cs:__imp_RtlAppendUnicodeToString
0x14001814d  lea     rdx, asc_1400326D0; "\\"
0x140018154  lea     rcx, [rbp+270h+var_2E8]; Destination
0x140018158  call    cs:__imp_RtlAppendUnicodeToString
0x14001815e  lea     rdx, [rbp+270h+Source]; Source
0x140018162  lea     rcx, [rbp+270h+var_2E8]; Destination
0x140018166  call    cs:__imp_RtlAppendUnicodeStringToString
0x14001816c  lea     rcx, [rbp+270h+Source]
0x140018170  call    AslAnsiStringFree
0x140018175  lea     rdx, aRegistryMachin_2; "\\Registry\\Machine\\Software\\Microsof"...
0x14001817c  lea     rcx, [rbp+270h+var_268]; DestinationString
0x140018180  call    cs:__imp_RtlInitUnicodeString
0x140018186  lea     rax, [rbp+270h+var_268]
0x14001818a  mov     [rbp+270h+ObjectAttributes.Length], 30h ; '0'
0x140018191  mov     [rbp+270h+ObjectAttributes.ObjectName], rax
0x140018195  lea     r8, [rbp+270h+ObjectAttributes]; ObjectAttributes
0x140018199  lea     rax, [rsp+370h+var_310]
0x14001819e  mov     [rbp+270h+ObjectAttributes.RootDirectory], r12
0x1400181a2  mov     [rsp+370h+Disposition], rax; Disposition
0x1400181a7  lea     rcx, [rbp+270h+KeyHandle]; KeyHandle
0x1400181ab  xorps   xmm0, xmm0
0x1400181ae  mov     [rsp+370h+CreateOptions], r12d; CreateOptions
0x1400181b3  xor     r9d, r9d; TitleIndex
0x1400181b6  mov     [rsp+370h+Class], r12; Class
0x1400181bb  mov     edx, 2010Fh; DesiredAccess
0x1400181c0  mov     [rbp+270h+ObjectAttributes.Attributes], 40h ; '@'
0x1400181c7  movdqu  xmmword ptr [rbp+270h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400181cc  call    cs:__imp_NtCreateKey
0x1400181d2  test    eax, eax
0x1400181d4  jns     short loc_140018204
0x1400181d6  mov     [rsp+370h+CreateOptions], eax
0x1400181da  mov     r8d, 43Ch
0x1400181e0  mov     rax, [rbp+270h+var_268.Buffer]
0x1400181e4  lea     r9, aFailedToCreate_7; "Failed to create key \"%ws\" [%x]"
0x1400181eb  lea     rdx, aSdbregisterdat; "SdbRegisterDatabaseEx"
0x1400181f2  mov     [rsp+370h+Class], rax
0x1400181f7  mov     ecx, r13d
0x1400181fa  call    AslLogCallPrintf
0x1400181ff  jmp     loc_140018478
0x140018204  lea     rax, [rbp+270h+var_2E8]
0x140018208  mov     [rbp+270h+ObjectAttributes.Length], 30h ; '0'
0x14001820f  mov     [rbp+270h+ObjectAttributes.ObjectName], rax
0x140018213  lea     r8, [rbp+270h+ObjectAttributes]; ObjectAttributes
0x140018217  lea     rax, [rsp+370h+var_310]
0x14001821c  mov     [rbp+270h+ObjectAttributes.RootDirectory], r12
0x140018220  mov     [rsp+370h+Disposition], rax; Disposition
0x140018225  lea     rcx, [rsp+370h+Handle]; KeyHandle
0x14001822a  xorps   xmm0, xmm0
0x14001822d  mov     [rsp+370h+CreateOptions], r12d; CreateOptions
0x140018232  xor     r9d, r9d; TitleIndex
0x140018235  mov     [rsp+370h+Class], r12; Class
0x14001823a  mov     edx, 2010Fh; DesiredAccess
0x14001823f  mov     [rbp+270h+ObjectAttributes.Attributes], 40h ; '@'
0x140018246  movdqu  xmmword ptr [rbp+270h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001824b  call    cs:__imp_NtCreateKey
0x140018251  test    eax, eax
0x140018253  jns     short loc_140018268
0x140018255  mov     [rsp+370h+CreateOptions], eax
0x140018259  mov     r8d, 454h
0x14001825f  mov     rax, [rbp+270h+var_2E8.Buffer]
0x140018263  jmp     loc_1400181E4
0x140018268  movzx   eax, [rsp+370h+Destination.MaximumLength]
0x14001826d  lea     rdx, g_ustrDatabasePath; ValueName
0x140018274  mov     rcx, [rsp+370h+Handle]; KeyHandle
0x140018279  mov     r9d, r13d; Type
0x14001827c  mov     [rsp+370h+CreateOptions], eax; DataSize
0x140018280  xor     r8d, r8d; TitleIndex
0x140018283  mov     rax, [rsp+370h+Destination.Buffer]
0x140018288  mov     [rsp+370h+Class], rax; Data
0x14001828d  call    cs:__imp_NtSetValueKey
0x140018293  test    eax, eax
0x140018295  jns     short loc_1400182CD
0x140018297  mov     dword ptr [rsp+370h+Disposition], eax
0x14001829b  lea     r9, aFailedToSetVal_0; "Failed to set value \"%ws\" to \"%ws\" "...
0x1400182a2  mov     qword ptr [rsp+370h+CreateOptions], rdi
0x1400182a7  lea     rax, aDatabasepath; "DatabasePath"
0x1400182ae  mov     r8d, 463h
0x1400182b4  lea     rdx, aSdbregisterdat; "SdbRegisterDatabaseEx"
0x1400182bb  mov     [rsp+370h+Class], rax
0x1400182c0  mov     ecx, r13d
0x1400182c3  call    AslLogCallPrintf
0x1400182c8  jmp     loc_140018478
0x1400182cd  mov     ecx, 4
0x1400182d2  lea     rax, [rsp+370h+Data]
0x1400182d7  mov     [rsp+370h+CreateOptions], ecx; DataSize
0x1400182db  lea     rdx, g_ustrDatabaseType; ValueName
0x1400182e2  mov     r9d, ecx; Type
0x1400182e5  mov     [rsp+370h+Class], rax; Data
0x1400182ea  mov     rcx, [rsp+370h+Handle]; KeyHandle
0x1400182ef  xor     r8d, r8d; TitleIndex
0x1400182f2  call    cs:__imp_NtSetValueKey
0x1400182f8  test    eax, eax
0x1400182fa  jns     short loc_14001831E
0x1400182fc  mov     dword ptr [rsp+370h+Disposition], eax
0x140018300  lea     r9, aFailedToSetVal_1; "Failed to set value \"%ws\" to 0x%lx [%"...
0x140018307  mov     eax, [rsp+370h+Data]
0x14001830b  mov     r8d, 46Fh
0x140018311  mov     [rsp+370h+CreateOptions], eax
0x140018315  lea     rax, aDatabasetype; "DatabaseType"
0x14001831c  jmp     short loc_1400182B4
0x14001831e  mov     rcx, [rsp+370h+Handle]; KeyHandle
0x140018323  lea     rdi, [rbx+28h]
0x140018327  mov     r9d, 4; Type
0x14001832d  lea     rdx, g_ustrRuntimePlatform; ValueName
0x140018334  mov     [rsp+370h+CreateOptions], r9d; DataSize
0x140018339  xor     r8d, r8d; TitleIndex
0x14001833c  mov     [rsp+370h+Class], rdi; Data
0x140018341  call    cs:__imp_NtSetValueKey
0x140018347  test    eax, eax
0x140018349  jns     short loc_14001836E
0x14001834b  mov     dword ptr [rsp+370h+Disposition], eax
0x14001834f  lea     r9, aFailedToSetVal_1; "Failed to set value \"%ws\" to 0x%lx [%"...
0x140018356  mov     eax, [rdi]
0x140018358  mov     r8d, 47Bh
0x14001835e  mov     [rsp+370h+CreateOptions], eax
0x140018362  lea     rax, ValueName; "DatabaseRuntimePlatform"
0x140018369  jmp     loc_1400182B4
0x14001836e  mov     rcx, [rbx+10h]
0x140018372  test    rcx, rcx
0x140018375  jz      short loc_1400183D7
0x140018377  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001837b  inc     rax
0x14001837e  cmp     [rcx+rax*2], r12w
0x140018383  jnz     short loc_14001837B
0x140018385  lea     eax, ds:2[rax*2]
0x14001838c  mov     r9d, r13d; Type
0x14001838f  mov     [rsp+370h+CreateOptions], eax; DataSize
0x140018393  lea     rdx, g_ustrDatabaseDescription; ValueName
0x14001839a  mov     [rsp+370h+Class], rcx; Data
0x14001839f  xor     r8d, r8d; TitleIndex
0x1400183a2  mov     rcx, [rsp+370h+Handle]; KeyHandle
0x1400183a7  call    cs:__imp_NtSetValueKey
0x1400183ad  test    eax, eax
0x1400183af  jns     short loc_1400183D7
0x1400183b1  mov     dword ptr [rsp+370h+Disposition], eax
0x1400183b5  lea     r9, aFailedToSetVal_2; "Failed to set value \"%ws\" to %ws [%x]"
0x1400183bc  mov     rax, [rbx+10h]
0x1400183c0  mov     r8d, 488h
0x1400183c6  mov     qword ptr [rsp+370h+CreateOptions], rax
0x1400183cb  lea     rax, aDatabasedescri; "DatabaseDescription"
0x1400183d2  jmp     loc_1400182B4
0x1400183d7  test    rsi, rsi
0x1400183da  jnz     short loc_1400183EC
0x1400183dc  lea     rcx, [rbp+270h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400183e0  call    cs:__imp_GetSystemTimeAsFileTime
0x1400183e6  mov     rax, qword ptr [rbp+270h+SystemTimeAsFileTime.dwLowDateTime]
0x1400183ea  jmp     short loc_1400183EF
0x1400183ec  mov     rax, [rsi]
0x1400183ef  mov     rcx, [rsp+370h+Handle]; KeyHandle
0x1400183f4  lea     rdx, g_ustrInstallTimeStamp; ValueName
0x1400183fb  mov     edi, 8
0x140018400  mov     [rbp+270h+var_2F0], rax
0x140018404  lea     rax, [rbp+270h+var_2F0]
0x140018408  mov     [rsp+370h+CreateOptions], edi; DataSize
0x14001840c  xor     r8d, r8d; TitleIndex
0x14001840f  mov     [rsp+370h+Class], rax; Data
0x140018414  lea     r9d, [rdi+3]; Type
0x140018418  call    cs:__imp_NtSetValueKey
0x14001841e  test    eax, eax
0x140018420  jns     short loc_14001843F
0x140018422  mov     [rsp+370h+CreateOptions], eax
0x140018426  lea     r9, aFailedToSetVal; "Failed to set value \"%ws\" [%x]"
0x14001842d  lea     rax, aDatabaseinstal; "DatabaseInstallTimeStamp"
0x140018434  mov     r8d, 4A0h
  ... truncated ...
```
