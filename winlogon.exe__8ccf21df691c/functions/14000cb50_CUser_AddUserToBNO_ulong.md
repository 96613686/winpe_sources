# CUser::AddUserToBNO(ulong)

- ea: `0x14000cb50`
- end: `0x14000d4d9`
- name: `?AddUserToBNO@CUser@@QEAAKK@Z`
- size: `2441`
- prototype: `unsigned int __fastcall(CUser *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140047370`

## callees

- `0x1400057f4`
- `0x14000cb50`
- `0x14000d4e0`
- `0x14000d570`
- `0x14000d9d8`
- `0x14000f510`
- `0x140053720`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000ce9d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000ceb9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000ce9d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000ceb9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ce8f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ceab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ce8f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ceab`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x14000ce6e`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x14000ce6e`
- `ntdll!NtOpenFile` at `0x14000d3be`
- `ntdll!NtOpenFile` at `0x14000d3be`
- `ntdll!RtlAppendUnicodeToString` at `0x14000d34d`
- `ntdll!RtlAppendUnicodeToString` at `0x14000d360`
- `ntdll!RtlAppendUnicodeToString` at `0x14000d34d`
- `ntdll!RtlAppendUnicodeToString` at `0x14000d360`
- `ntdll!NtOpenDirectoryObject` at `0x14000ccae`
- `ntdll!NtOpenDirectoryObject` at `0x14000cf57`
- `ntdll!NtOpenDirectoryObject` at `0x14000d0e6`
- `ntdll!NtOpenDirectoryObject` at `0x14000ccae`
- `ntdll!NtOpenDirectoryObject` at `0x14000cf57`
- `ntdll!NtOpenDirectoryObject` at `0x14000d0e6`
- `ntdll!NtSetSecurityObject` at `0x14000ce29`
- `ntdll!NtSetSecurityObject` at `0x14000d05e`
- `ntdll!NtSetSecurityObject` at `0x14000d28f`
- `ntdll!NtSetSecurityObject` at `0x14000d3d5`
- `ntdll!NtSetSecurityObject` at `0x14000ce29`
- `ntdll!NtSetSecurityObject` at `0x14000d05e`
- `ntdll!NtSetSecurityObject` at `0x14000d28f`
- `ntdll!NtSetSecurityObject` at `0x14000d3d5`
- `ntdll!RtlGetAce` at `0x14000d2cd`
- `ntdll!RtlGetAce` at `0x14000d2cd`
- `ntdll!RtlInitUnicodeString` at `0x14000cc68`
- `ntdll!RtlInitUnicodeString` at `0x14000cf11`
- `ntdll!RtlInitUnicodeString` at `0x14000d0a3`
- `ntdll!RtlInitUnicodeString` at `0x14000cc68`
- `ntdll!RtlInitUnicodeString` at `0x14000cf11`
- `ntdll!RtlInitUnicodeString` at `0x14000d0a3`
- `ntdll!NtQuerySystemInformation` at `0x14000cc15`
- `ntdll!NtQuerySystemInformation` at `0x14000cc15`
- `ntdll!RtlNtStatusToDosError` at `0x14000d3e5`
- `ntdll!RtlNtStatusToDosError` at `0x14000d3e5`
- `ntdll!NtClose` at `0x14000cecc`
- `ntdll!NtClose` at `0x14000d478`
- `ntdll!NtClose` at `0x14000d4bf`
- `ntdll!NtClose` at `0x14000d4d1`
- `ntdll!NtClose` at `0x14009d1c3`
- `ntdll!NtClose` at `0x14009d1d3`
- `ntdll!NtClose` at `0x14009d1e3`
- `ntdll!NtClose` at `0x14000cecc`
- `ntdll!NtClose` at `0x14000d478`
- `ntdll!NtClose` at `0x14000d4bf`
- `ntdll!NtClose` at `0x14000d4d1`
- `ntdll!NtClose` at `0x14009d1c3`
- `ntdll!NtClose` at `0x14009d1d3`
- `ntdll!NtClose` at `0x14009d1e3`

## pseudocode

```c
__int64 __fastcall CUser::AddUserToBNO(CUser *this, unsigned int a2)
{
  void *v4; // rdi
  ULONG v5; // ebx
  _QWORD *v6; // r14
  int v7; // eax
  void *v8; // rax
  enum _MANDATORY_LEVEL v9; // edx
  NTSTATUS DaclSecurityDescriptor; // eax
  PACL v11; // rbx
  HANDLE ProcessHeap; // rax
  HANDLE v13; // rax
  void *v14; // rax
  _QWORD *v15; // rax
  struct _ACL *v16; // r15
  ULONG v17; // esi
  int v18; // r8d
  _DWORD *i; // rax
  unsigned __int8 DaclPresent; // [rsp+34h] [rbp-444h] BYREF
  unsigned __int8 DaclDefaulted[3]; // [rsp+35h] [rbp-443h] BYREF
  void *FileHandle; // [rsp+38h] [rbp-440h] BYREF
  int SystemInformation; // [rsp+40h] [rbp-438h] BYREF
  ULONG v25; // [rsp+44h] [rbp-434h]
  void *v26; // [rsp+48h] [rbp-430h]
  HANDLE Handle; // [rsp+50h] [rbp-428h] BYREF
  HANDLE v28; // [rsp+58h] [rbp-420h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+60h] [rbp-418h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-408h] BYREF
  PACL Dacl; // [rsp+A0h] [rbp-3D8h] BYREF
  PVOID Ace; // [rsp+A8h] [rbp-3D0h] BYREF
  PSID v33; // [rsp+B0h] [rbp-3C8h] BYREF
  int v34; // [rsp+B8h] [rbp-3C0h]
  char v35; // [rsp+BCh] [rbp-3BCh]
  PSID v36; // [rsp+C0h] [rbp-3B8h]
  int v37; // [rsp+C8h] [rbp-3B0h]
  char v38; // [rsp+CCh] [rbp-3ACh]
  PSID v39; // [rsp+D0h] [rbp-3A8h]
  int v40; // [rsp+D8h] [rbp-3A0h]
  char v41; // [rsp+DCh] [rbp-39Ch]
  PSID v42; // [rsp+E0h] [rbp-398h]
  int v43; // [rsp+E8h] [rbp-390h]
  char v44; // [rsp+ECh] [rbp-38Ch]
  PSID v45; // [rsp+F0h] [rbp-388h]
  int v46; // [rsp+F8h] [rbp-380h]
  char v47; // [rsp+FCh] [rbp-37Ch]
  PSID v48; // [rsp+100h] [rbp-378h]
  int v49; // [rsp+108h] [rbp-370h]
  char v50; // [rsp+10Ch] [rbp-36Ch]
  PSID v51; // [rsp+110h] [rbp-368h]
  int v52; // [rsp+118h] [rbp-360h]
  char v53; // [rsp+11Ch] [rbp-35Ch]
  PSID v54; // [rsp+120h] [rbp-358h]
  int v55; // [rsp+128h] [rbp-350h]
  char v56; // [rsp+12Ch] [rbp-34Ch]
  PSID v57; // [rsp+130h] [rbp-348h]
  int v58; // [rsp+138h] [rbp-340h]
  char v59; // [rsp+13Ch] [rbp-33Ch]
  PSID v60; // [rsp+140h] [rbp-338h]
  int v61; // [rsp+148h] [rbp-330h]
  char v62; // [rsp+14Ch] [rbp-32Ch]
  PSID v63; // [rsp+150h] [rbp-328h]
  int v64; // [rsp+158h] [rbp-320h]
  char v65; // [rsp+15Ch] [rbp-31Ch]
  _DWORD *v66; // [rsp+160h] [rbp-318h]
  _QWORD *v67; // [rsp+168h] [rbp-310h]
  struct _UNICODE_STRING DestinationString; // [rsp+170h] [rbp-308h] BYREF
  _DWORD v69[3]; // [rsp+180h] [rbp-2F8h] BYREF
  __int64 v70; // [rsp+18Ch] [rbp-2ECh]
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+198h] [rbp-2E0h] BYREF
  WCHAR SourceString[40]; // [rsp+1B0h] [rbp-2C8h] BYREF
  WCHAR Source[128]; // [rsp+200h] [rbp-278h] BYREF
  char v74; // [rsp+300h] [rbp-178h] BYREF

  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  FileHandle = 0;
  DestinationString = 0;
  v28 = 0;
  IoStatusBlock = 0;
  v4 = 0;
  v26 = 0;
  SystemInformation = 0;
  v5 = 0;
  Handle = 0;
  v6 = 0;
  v67 = 0;
  Destination = 0;
  v69[0] = 4;
  v69[1] = 1048578;
  v69[2] = 8;
  v70 = 1048580;
  if ( NtQuerySystemInformation(SystemObjectSecurityMode, &SystemInformation, 4u, 0) < 0 )
    goto LABEL_38;
  if ( !SystemInformation )
    goto LABEL_38;
  v5 = StringCchPrintfW(SourceString, 0x26u, L"\\Sessions\\%d\\BaseNamedObjects", a2);
  if ( v5 )
    goto LABEL_38;
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 0;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = NtOpenDirectoryObject(&FileHandle, 0xE0000u, &ObjectAttributes);
  if ( v7 < 0 )
    goto LABEL_31;
  v33 = g_pSidRestricted;
  v34 = 2;
  v35 = v5;
  v36 = g_pSidWorld;
  v37 = 3;
  v38 = 2;
  v39 = g_pSidAdmin;
  v40 = 131087;
  v41 = v5;
  v42 = (PSID)*((_QWORD *)this + 15);
  v43 = 131087;
  v44 = v5;
  v45 = v42;
  v46 = 0x10000000;
  v47 = 11;
  v48 = (PSID)*((_QWORD *)this + 20);
  v49 = 983055;
  v50 = v5;
  v51 = g_pSidCreator;
  v52 = 0x10000000;
  v53 = 11;
  v54 = g_pSidSystem;
  v55 = 0x10000000;
  v56 = 11;
  v57 = g_pSidSystem;
  v58 = 983055;
  v59 = v5;
  v60 = g_pSidWindowManager;
  v61 = 983055;
  v62 = v5;
  v8 = (void *)CreateSecurityDescriptor(&v33, 10);
  v4 = v8;
  v26 = v8;
  if ( !v8 )
  {
    v5 = 14;
    goto LABEL_38;
  }
  v7 = NtSetSecurityObject(FileHandle, 4u, v8);
  if ( v7 < 0 )
    goto LABEL_31;
  v7 = SetKernelIntegrityLabel(FileHandle, v9);
  if ( v7 < 0 )
    goto LABEL_31;
  Dacl = 0;
  DaclPresent = v5;
  DaclDefaulted[0] = v5;
  DaclSecurityDescriptor = RtlGetDaclSecurityDescriptor(v4, &DaclPresent, &Dacl, DaclDefaulted);
  if ( DaclSecurityDescriptor < 0 )
  {
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        WPP_b346fd90c9c23c4ee3450cad4b06957a_Traceguids,
        (unsigned int)DaclSecurityDescriptor);
    }
  }
  else if ( DaclPresent != (_BYTE)v5 )
  {
    v11 = Dacl;
    if ( Dacl )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v11);
      Dacl = 0;
    }
  }
  v13 = GetProcessHeap();
  HeapFree(v13, 0, v4);
  v4 = 0;
  v26 = 0;
  NtClose(FileHandle);
  FileHandle = 0;
  v5 = StringCchPrintfW(SourceString, 0x26u, L"\\Sessions\\%d", a2);
  if ( v5 )
    goto LABEL_38;
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 0;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = NtOpenDirectoryObject(&FileHandle, 0x60000u, &ObjectAttributes);
  if ( v7 < 0 )
  {
LABEL_31:
    v5 = RtlNtStatusToDosError(v7);
    goto LABEL_38;
  }
  v33 = g_pSidRestricted;
  v34 = 2;
  v35 = 0;
  v36 = g_pSidSystem;
  v37 = 983055;
  v38 = 0;
  v39 = g_pSidAdmin;
  v40 = 983055;
  v41 = 0;
  v42 = g_pSidCreator;
  v43 = 0x10000000;
  v44 = 11;
  v45 = (PSID)*((_QWORD *)this + 15);
  v46 = 2;
  v47 = 0;
  v48 = g_pSidWindowManager;
  v49 = 2;
  v50 = 0;
  v14 = (void *)CreateSecurityDescriptor(&v33, 6);
  v4 = v14;
  v26 = v14;
  if ( v14 )
  {
    v7 = NtSetSecurityObject(FileHandle, 4u, v14);
    if ( v7 < 0 )
      goto LABEL_31;
    v5 = StringCchPrintfW(Source, 0x80u, L"\\Sessions\\%d\\AppContainerNamedObjects", a2);
    if ( v5 )
      goto LABEL_38;
    RtlInitUnicodeString(&Destination, Source);
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 0;
    ObjectAttributes.ObjectName = &Destination;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v7 = NtOpenDirectoryObject(&Handle, 0xE0000u, &ObjectAttributes);
    if ( v7 < 0 )
      goto LABEL_31;
    v33 = g_pSidAnyPackage;
    v34 = 3;
    v35 = 0;
    v36 = g_pSidAnyRestrictedPackage;
    v37 = 3;
    v38 = 0;
    v39 = g_pSidRestricted;
    v40 = 2;
    v41 = 0;
    v42 = g_pSidWorld;
    v43 = 3;
    v44 = 2;
    v45 = g_pSidAdmin;
    v46 = 131087;
    v47 = 0;
    v48 = (PSID)*((_QWORD *)this + 15);
    v49 = 131087;
    v50 = 0;
    v51 = v48;
    v52 = 0x10000000;
    v53 = 11;
    v54 = (PSID)*((_QWORD *)this + 20);
    v55 = 983055;
    v56 = 0;
    v57 = g_pSidCreator;
    v58 = 0x10000000;
    v59 = 11;
    v60 = g_pSidSystem;
    v61 = 0x10000000;
    v62 = 11;
    v63 = g_pSidSystem;
    v64 = 983055;
    v65 = 0;
    v15 = (_QWORD *)CreateSecurityDescriptor(&v33, 10);
    v6 = v15;
    v67 = v15;
    if ( !v15 )
    {
      v5 = 14;
      goto LABEL_38;
    }
    v7 = NtSetSecurityObject(Handle, 4u, v15);
    if ( v7 < 0 )
      goto LABEL_31;
    Ace = 0;
    v25 = 0;
    v66 = 0;
    v16 = (struct _ACL *)v6[4];
    v17 = 0;
    v25 = 0;
    while ( RtlGetAce(v16, v17, &Ace) >= 0 )
    {
      v18 = *((_DWORD *)Ace + 1);
      *((_DWORD *)Ace + 1) = v18 & 0xFFFF0000;
      for ( i = v69; ; i += 2 )
      {
        v66 = i;
        if ( !*i )
          break;
        if ( *i == (unsigned __int16)(v18 & *i) )
          *((_DWORD *)Ace + 1) |= i[1];
      }
      v25 = ++v17;
    }
    *(_QWORD *)&Destination.Length = 19398656;
    Destination.Buffer = (PWSTR)&v74;
    RtlAppendUnicodeToString(&Destination, L"\\Device\\NamedPipe");
    RtlAppendUnicodeToString(&Destination, Source);
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.ObjectName = &Destination;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v7 = NtOpenFile(&v28, 0x1E0000u, &ObjectAttributes, &IoStatusBlock, 3u, 0x21u);
    if ( v7 < 0 )
      goto LABEL_31;
    v7 = NtSetSecurityObject(v28, 4u, v6);
    if ( v7 < 0 )
      goto LABEL_31;
  }
  else
  {
    v5 = 14;
  }
LABEL_38:
  if ( v4 )
    DeleteSecurityDescriptor(v4);
  if ( v6 )
    DeleteSecurityDescriptor(v6);
  if ( FileHandle )
    NtClose(FileHandle);
  if ( Handle )
    NtClose(Handle);
  if ( v28 )
    NtClose(v28);
  return v5;
}

```

## disassembly

```asm
0x14000cb50  push    rbx
0x14000cb52  push    rsi
0x14000cb53  push    rdi
0x14000cb54  push    r12
0x14000cb56  push    r14
0x14000cb58  push    r15
0x14000cb5a  sub     rsp, 448h
0x14000cb61  mov     rax, cs:__security_cookie
0x14000cb68  xor     rax, rsp
0x14000cb6b  mov     [rsp+478h+var_48], rax
0x14000cb73  mov     esi, edx
0x14000cb75  mov     r15, rcx
0x14000cb78  xorps   xmm0, xmm0
0x14000cb7b  movups  xmmword ptr [rsp+478h+ObjectAttributes.Length], xmm0
0x14000cb80  movups  xmmword ptr [rsp+478h+ObjectAttributes.ObjectName], xmm0
0x14000cb88  movups  xmmword ptr [rsp+478h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000cb90  xor     r12d, r12d
0x14000cb93  mov     [rsp+478h+FileHandle], r12
0x14000cb98  movups  xmmword ptr [rsp+478h+DestinationString.Length], xmm0
0x14000cba0  mov     [rsp+478h+var_420], r12
0x14000cba5  xorps   xmm1, xmm1
0x14000cba8  movups  xmmword ptr [rsp+478h+IoStatusBlock], xmm1
0x14000cbb0  mov     edi, r12d
0x14000cbb3  mov     [rsp+478h+var_430], r12
0x14000cbb8  mov     [rsp+478h+SystemInformation], r12d
0x14000cbbd  mov     ebx, r12d
0x14000cbc0  mov     [rsp+478h+Handle], r12
0x14000cbc5  mov     r14d, r12d
0x14000cbc8  mov     [rsp+478h+var_310], r12
0x14000cbd0  movups  xmmword ptr [rsp+478h+Destination.Length], xmm0
0x14000cbd5  mov     [rsp+478h+var_2F8], 4
0x14000cbe0  mov     [rsp+478h+var_2F4], 100002h
0x14000cbeb  mov     [rsp+478h+var_2F0], 8
0x14000cbf6  mov     [rsp+478h+var_2EC], 100004h
0x14000cc02  xor     r9d, r9d; ReturnLength
0x14000cc05  mov     r8d, 4; SystemInformationLength
0x14000cc0b  lea     rdx, [rsp+478h+SystemInformation]; SystemInformation
0x14000cc10  mov     ecx, 46h ; 'F'; SystemInformationClass
0x14000cc15  call    cs:__imp_NtQuerySystemInformation
0x14000cc1b  test    eax, eax
0x14000cc1d  js      loc_14000D464
0x14000cc23  cmp     [rsp+478h+SystemInformation], r12d
0x14000cc28  jz      loc_14000D464
0x14000cc2e  mov     r9d, esi
0x14000cc31  lea     r8, aSessionsDBasen; "\\Sessions\\%d\\BaseNamedObjects"
0x14000cc38  mov     edx, 26h ; '&'; unsigned __int64
0x14000cc3d  lea     rcx, [rsp+478h+SourceString]; unsigned __int16 *
0x14000cc45  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000cc4a  mov     ebx, eax
0x14000cc4c  mov     [rsp+478h+var_448], eax
0x14000cc50  test    eax, eax
0x14000cc52  jnz     loc_14000D464
0x14000cc58  lea     rdx, [rsp+478h+SourceString]; SourceString
0x14000cc60  lea     rcx, [rsp+478h+DestinationString]; DestinationString
0x14000cc68  call    cs:__imp_RtlInitUnicodeString
0x14000cc6e  mov     [rsp+478h+ObjectAttributes.Length], 30h ; '0'
0x14000cc76  mov     [rsp+478h+ObjectAttributes.RootDirectory], r12
0x14000cc7b  mov     [rsp+478h+ObjectAttributes.Attributes], r12d
0x14000cc83  lea     rax, [rsp+478h+DestinationString]
0x14000cc8b  mov     [rsp+478h+ObjectAttributes.ObjectName], rax
0x14000cc93  xorps   xmm0, xmm0
0x14000cc96  movdqu  xmmword ptr [rsp+478h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000cc9f  lea     r8, [rsp+478h+ObjectAttributes]; ObjectAttributes
0x14000cca4  mov     edx, 0E0000h; DesiredAccess
0x14000cca9  lea     rcx, [rsp+478h+FileHandle]; FileHandle
0x14000ccae  call    cs:__imp_NtOpenDirectoryObject
0x14000ccb4  test    eax, eax
0x14000ccb6  js      loc_14000D3E3
0x14000ccbc  mov     rax, cs:g_pSidRestricted
0x14000ccc3  mov     [rsp+478h+var_3C8], rax
0x14000cccb  mov     [rsp+478h+var_3C0], 2
0x14000ccd6  mov     [rsp+478h+var_3BC], bl
0x14000ccdd  mov     rax, cs:g_pSidWorld
0x14000cce4  mov     [rsp+478h+var_3B8], rax
0x14000ccec  mov     [rsp+478h+var_3B0], 3
0x14000ccf7  mov     [rsp+478h+var_3AC], 2
0x14000ccff  mov     rax, cs:g_pSidAdmin
0x14000cd06  mov     [rsp+478h+var_3A8], rax
0x14000cd0e  mov     [rsp+478h+var_3A0], 2000Fh
0x14000cd19  mov     [rsp+478h+var_39C], bl
0x14000cd20  mov     rax, [r15+78h]
0x14000cd24  mov     [rsp+478h+var_398], rax
0x14000cd2c  mov     [rsp+478h+var_390], 2000Fh
0x14000cd37  mov     [rsp+478h+var_38C], bl
0x14000cd3e  mov     [rsp+478h+var_388], rax
0x14000cd46  mov     [rsp+478h+var_380], 10000000h
0x14000cd51  mov     [rsp+478h+var_37C], 0Bh
0x14000cd59  mov     rax, [r15+0A0h]
0x14000cd60  mov     [rsp+478h+var_378], rax
0x14000cd68  mov     [rsp+478h+var_370], 0F000Fh
0x14000cd73  mov     [rsp+478h+var_36C], bl
0x14000cd7a  mov     rax, cs:g_pSidCreator
0x14000cd81  mov     [rsp+478h+var_368], rax
0x14000cd89  mov     [rsp+478h+var_360], 10000000h
0x14000cd94  mov     [rsp+478h+var_35C], 0Bh
0x14000cd9c  mov     rax, cs:g_pSidSystem
0x14000cda3  mov     [rsp+478h+var_358], rax
0x14000cdab  mov     [rsp+478h+var_350], 10000000h
0x14000cdb6  mov     [rsp+478h+var_34C], 0Bh
0x14000cdbe  mov     [rsp+478h+var_348], rax
0x14000cdc6  mov     [rsp+478h+var_340], 0F000Fh
0x14000cdd1  mov     [rsp+478h+var_33C], bl
0x14000cdd8  mov     rax, cs:g_pSidWindowManager
0x14000cddf  mov     [rsp+478h+var_338], rax
0x14000cde7  mov     [rsp+478h+var_330], 0F000Fh
0x14000cdf2  mov     [rsp+478h+var_32C], bl
0x14000cdf9  mov     edx, 0Ah
0x14000cdfe  lea     rcx, [rsp+478h+var_3C8]
0x14000ce06  call    CreateSecurityDescriptor
0x14000ce0b  mov     rdi, rax
0x14000ce0e  mov     [rsp+478h+var_430], rax
0x14000ce13  test    rax, rax
0x14000ce16  jz      loc_14000D43B
0x14000ce1c  mov     r8, rax; SecurityDescriptor
0x14000ce1f  mov     edx, 4; SecurityInformation
0x14000ce24  mov     rcx, [rsp+478h+FileHandle]; Handle
0x14000ce29  call    cs:__imp_NtSetSecurityObject
0x14000ce2f  test    eax, eax
0x14000ce31  js      loc_14000D3E3
0x14000ce37  mov     rcx, [rsp+478h+FileHandle]; Handle
0x14000ce3c  call    ?SetKernelIntegrityLabel@@YAJPEAXW4_MANDATORY_LEVEL@@@Z; SetKernelIntegrityLabel(void *,_MANDATORY_LEVEL)
0x14000ce41  test    eax, eax
0x14000ce43  js      loc_14000D3E3
0x14000ce49  mov     [rsp+478h+Dacl], r12
0x14000ce51  mov     [rsp+478h+DaclPresent], bl
0x14000ce55  mov     [rsp+478h+DaclDefaulted], bl
0x14000ce59  lea     r9, [rsp+478h+DaclDefaulted]; DaclDefaulted
0x14000ce5e  lea     r8, [rsp+478h+Dacl]; Dacl
0x14000ce66  lea     rdx, [rsp+478h+DaclPresent]; DaclPresent
0x14000ce6b  mov     rcx, rdi; SecurityDescriptor
0x14000ce6e  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x14000ce74  test    eax, eax
0x14000ce76  js      loc_14000D3F3
0x14000ce7c  cmp     [rsp+478h+DaclPresent], bl
0x14000ce80  jz      short loc_14000CEAB
0x14000ce82  mov     rbx, [rsp+478h+Dacl]
0x14000ce8a  test    rbx, rbx
0x14000ce8d  jz      short loc_14000CEAB
0x14000ce8f  call    cs:__imp_GetProcessHeap
0x14000ce95  mov     r8, rbx; lpMem
0x14000ce98  xor     edx, edx; dwFlags
0x14000ce9a  mov     rcx, rax; hHeap
0x14000ce9d  call    cs:__imp_HeapFree
0x14000cea3  mov     [rsp+478h+Dacl], r12
0x14000ceab  call    cs:__imp_GetProcessHeap
0x14000ceb1  mov     r8, rdi; lpMem
0x14000ceb4  xor     edx, edx; dwFlags
0x14000ceb6  mov     rcx, rax; hHeap
0x14000ceb9  call    cs:__imp_HeapFree
0x14000cebf  mov     rdi, r12
0x14000cec2  mov     [rsp+478h+var_430], r12
0x14000cec7  mov     rcx, [rsp+478h+FileHandle]; Handle
0x14000cecc  call    cs:__imp_NtClose
0x14000ced2  mov     [rsp+478h+FileHandle], r12
0x14000ced7  mov     r9d, esi
0x14000ceda  lea     r8, aSessionsD; "\\Sessions\\%d"
0x14000cee1  mov     edx, 26h ; '&'; unsigned __int64
0x14000cee6  lea     rcx, [rsp+478h+SourceString]; unsigned __int16 *
0x14000ceee  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000cef3  mov     ebx, eax
0x14000cef5  mov     [rsp+478h+var_448], eax
0x14000cef9  test    eax, eax
0x14000cefb  jnz     loc_14000D464
0x14000cf01  lea     rdx, [rsp+478h+SourceString]; SourceString
0x14000cf09  lea     rcx, [rsp+478h+DestinationString]; DestinationString
0x14000cf11  call    cs:__imp_RtlInitUnicodeString
0x14000cf17  mov     [rsp+478h+ObjectAttributes.Length], 30h ; '0'
0x14000cf1f  mov     [rsp+478h+ObjectAttributes.RootDirectory], r12
0x14000cf24  mov     [rsp+478h+ObjectAttributes.Attributes], r12d
0x14000cf2c  lea     rax, [rsp+478h+DestinationString]
0x14000cf34  mov     [rsp+478h+ObjectAttributes.ObjectName], rax
0x14000cf3c  xorps   xmm0, xmm0
0x14000cf3f  movdqu  xmmword ptr [rsp+478h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000cf48  lea     r8, [rsp+478h+ObjectAttributes]; ObjectAttributes
0x14000cf4d  mov     edx, 60000h; DesiredAccess
0x14000cf52  lea     rcx, [rsp+478h+FileHandle]; FileHandle
0x14000cf57  call    cs:__imp_NtOpenDirectoryObject
0x14000cf5d  test    eax, eax
0x14000cf5f  js      loc_14000D3E3
0x14000cf65  mov     rax, cs:g_pSidRestricted
0x14000cf6c  mov     [rsp+478h+var_3C8], rax
0x14000cf74  mov     [rsp+478h+var_3C0], 2
0x14000cf7f  mov     [rsp+478h+var_3BC], dil
0x14000cf87  mov     rax, cs:g_pSidSystem
0x14000cf8e  mov     [rsp+478h+var_3B8], rax
0x14000cf96  mov     [rsp+478h+var_3B0], 0F000Fh
0x14000cfa1  mov     [rsp+478h+var_3AC], dil
0x14000cfa9  mov     rax, cs:g_pSidAdmin
0x14000cfb0  mov     [rsp+478h+var_3A8], rax
0x14000cfb8  mov     [rsp+478h+var_3A0], 0F000Fh
0x14000cfc3  mov     [rsp+478h+var_39C], dil
0x14000cfcb  mov     rax, cs:g_pSidCreator
0x14000cfd2  mov     [rsp+478h+var_398], rax
0x14000cfda  mov     [rsp+478h+var_390], 10000000h
0x14000cfe5  mov     [rsp+478h+var_38C], 0Bh
0x14000cfed  mov     rax, [r15+78h]
0x14000cff1  mov     [rsp+478h+var_388], rax
0x14000cff9  mov     [rsp+478h+var_380], 2
0x14000d004  mov     [rsp+478h+var_37C], dil
0x14000d00c  mov     rax, cs:g_pSidWindowManager
0x14000d013  mov     [rsp+478h+var_378], rax
0x14000d01b  mov     [rsp+478h+var_370], 2
0x14000d026  mov     [rsp+478h+var_36C], dil
0x14000d02e  mov     edx, 6
0x14000d033  lea     rcx, [rsp+478h+var_3C8]
0x14000d03b  call    CreateSecurityDescriptor
0x14000d040  mov     rdi, rax
0x14000d043  mov     [rsp+478h+var_430], rax
0x14000d048  test    rax, rax
0x14000d04b  jz      loc_14000D446
0x14000d051  mov     r8, rax; SecurityDescriptor
0x14000d054  mov     edx, 4; SecurityInformation
0x14000d059  mov     rcx, [rsp+478h+FileHandle]; Handle
0x14000d05e  call    cs:__imp_NtSetSecurityObject
0x14000d064  test    eax, eax
0x14000d066  js      loc_14000D3E3
0x14000d06c  mov     r9d, esi
0x14000d06f  lea     r8, aSessionsDAppco; "\\Sessions\\%d\\AppContainerNamedObject"...
0x14000d076  mov     edx, 80h; unsigned __int64
0x14000d07b  lea     rcx, [rsp+478h+Source]; unsigned __int16 *
0x14000d083  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000d088  mov     ebx, eax
0x14000d08a  mov     [rsp+478h+var_448], eax
0x14000d08e  test    eax, eax
0x14000d090  jnz     loc_14000D464
0x14000d096  lea     rdx, [rsp+478h+Source]; SourceString
0x14000d09e  lea     rcx, [rsp+478h+Destination]; DestinationString
0x14000d0a3  call    cs:__imp_RtlInitUnicodeString
0x14000d0a9  mov     [rsp+478h+ObjectAttributes.Length], 30h ; '0'
0x14000d0b1  mov     [rsp+478h+ObjectAttributes.RootDirectory], r12
0x14000d0b6  mov     [rsp+478h+ObjectAttributes.Attributes], r12d
0x14000d0be  lea     rax, [rsp+478h+Destination]
0x14000d0c3  mov     [rsp+478h+ObjectAttributes.ObjectName], rax
0x14000d0cb  xorps   xmm0, xmm0
0x14000d0ce  movdqu  xmmword ptr [rsp+478h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000d0d7  lea     r8, [rsp+478h+ObjectAttributes]; ObjectAttributes
0x14000d0dc  mov     edx, 0E0000h; DesiredAccess
0x14000d0e1  lea     rcx, [rsp+478h+Handle]; FileHandle
0x14000d0e6  call    cs:__imp_NtOpenDirectoryObject
0x14000d0ec  test    eax, eax
0x14000d0ee  js      loc_14000D3E3
0x14000d0f4  mov     rax, cs:g_pSidAnyPackage
0x14000d0fb  mov     [rsp+478h+var_3C8], rax
0x14000d103  mov     [rsp+478h+var_3C0], 3
0x14000d10e  mov     [rsp+478h+var_3BC], bl
0x14000d115  mov     rax, cs:g_pSidAnyRestrictedPackage
0x14000d11c  mov     [rsp+478h+var_3B8], rax
0x14000d124  mov     [rsp+478h+var_3B0], 3
0x14000d12f  mov     [rsp+478h+var_3AC], bl
0x14000d136  mov     rax, cs:g_pSidRestricted
0x14000d13d  mov     [rsp+478h+var_3A8], rax
0x14000d145  mov     [rsp+478h+var_3A0], 2
0x14000d150  mov     [rsp+478h+var_39C], bl
0x14000d157  mov     rax, cs:g_pSidWorld
0x14000d15e  mov     [rsp+478h+var_398], rax
0x14000d166  mov     [rsp+478h+var_390], 3
0x14000d171  mov     [rsp+478h+var_38C], 2
0x14000d179  mov     rax, cs:g_pSidAdmin
0x14000d180  mov     [rsp+478h+var_388], rax
0x14000d188  mov     [rsp+478h+var_380], 2000Fh
0x14000d193  mov     [rsp+478h+var_37C], bl
0x14000d19a  mov     rax, [r15+78h]
0x14000d19e  mov     [rsp+478h+var_378], rax
0x14000d1a6  mov     [rsp+478h+var_370], 2000Fh
0x14000d1b1  mov     [rsp+478h+var_36C], bl
0x14000d1b8  mov     [rsp+478h+var_368], rax
0x14000d1c0  mov     [rsp+478h+var_360], 10000000h
0x14000d1cb  mov     [rsp+478h+var_35C], 0Bh
0x14000d1d3  mov     rax, [r15+0A0h]
0x14000d1da  mov     [rsp+478h+var_358], rax
0x14000d1e2  mov     [rsp+478h+var_350], 0F000Fh
0x14000d1ed  mov     [rsp+478h+var_34C], bl
0x14000d1f4  mov     rax, cs:g_pSidCreator
0x14000d1fb  mov     [rsp+478h+var_348], rax
0x14000d203  mov     [rsp+478h+var_340], 10000000h
0x14000d20e  mov     [rsp+478h+var_33C], 0Bh
0x14000d216  mov     rax, cs:g_pSidSystem
0x14000d21d  mov     [rsp+478h+var_338], rax
0x14000d225  mov     [rsp+478h+var_330], 10000000h
0x14000d230  mov     [rsp+478h+var_32C], 0Bh
0x14000d238  mov     [rsp+478h+var_328], rax
0x14000d240  mov     [rsp+478h+var_320], 0F000Fh
0x14000d24b  mov     [rsp+478h+var_31C], bl
0x14000d252  mov     edx, 0Ah
0x14000d257  lea     rcx, [rsp+478h+var_3C8]
0x14000d25f  call    CreateSecurityDescriptor
0x14000d264  mov     r14, rax
0x14000d267  mov     [rsp+478h+var_310], rax
0x14000d26f  test    rax, rax
0x14000d272  jnz     short loc_14000D282
0x14000d274  mov     ebx, 0Eh
0x14000d279  mov     [rsp+478h+var_448], ebx
0x14000d27d  jmp     loc_14000D464
0x14000d282  mov     r8, r14; SecurityDescriptor
0x14000d285  mov     edx, 4; SecurityInformation
0x14000d28a  mov     rcx, [rsp+478h+Handle]; Handle
0x14000d28f  call    cs:__imp_NtSetSecurityObject
0x14000d295  test    eax, eax
0x14000d297  js      loc_14000D3E3
0x14000d29d  mov     [rsp+478h+Ace], r12
  ... truncated ...
```
