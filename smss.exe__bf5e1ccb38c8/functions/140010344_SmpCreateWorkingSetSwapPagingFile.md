# SmpCreateWorkingSetSwapPagingFile

- ea: `0x140010344`
- end: `0x1400107c7`
- name: `SmpCreateWorkingSetSwapPagingFile`
- size: `1155`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000fcf8`

## callees

- `0x140004610`
- `0x140004e30`
- `0x14000d4c0`
- `0x14000d8ec`
- `0x14000f280`
- `0x140010344`
- `0x14001106c`
- `0x1400112c8`
- `0x14001cc40`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x140010400`
- `ntdll!RtlInitUnicodeString` at `0x140010605`
- `ntdll!RtlInitUnicodeString` at `0x140010400`
- `ntdll!RtlInitUnicodeString` at `0x140010605`
- `ntdll!NtOpenFile` at `0x1400106d2`
- `ntdll!NtOpenFile` at `0x1400106d2`
- `ntdll!NtClose` at `0x1400106f0`
- `ntdll!NtClose` at `0x1400106f0`
- `ntdll!RtlUpcaseUnicodeChar` at `0x14001056f`
- `ntdll!RtlUpcaseUnicodeChar` at `0x14001056f`
- `ntdll!RtlFreeUnicodeString` at `0x140010502`
- `ntdll!RtlFreeUnicodeString` at `0x1400107a0`
- `ntdll!RtlFreeUnicodeString` at `0x140010502`
- `ntdll!RtlFreeUnicodeString` at `0x1400107a0`
- `ntdll!NtQueryValueKey` at `0x14001043c`
- `ntdll!NtQueryValueKey` at `0x140010489`
- `ntdll!NtQueryValueKey` at `0x14001043c`
- `ntdll!NtQueryValueKey` at `0x140010489`
- `ntdll!NtCreatePagingFile` at `0x140010754`
- `ntdll!NtCreatePagingFile` at `0x140010754`

## string_xrefs

- `0x14001078b`: `SmpCreateWorkingSetSwapPagingFile`

## pseudocode

```c
__int64 __fastcall SmpCreateWorkingSetSwapPagingFile(__int64 *a1)
{
  int v2; // ebx
  int v3; // edx
  WCHAR v4; // cx
  WCHAR v5; // ax
  __int64 *v6; // rcx
  __int64 v7; // rdi
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // r8
  unsigned __int64 v10; // r9
  unsigned __int64 v11; // r10
  ULONG v12; // ebx
  NTSTATUS v13; // eax
  int v15; // [rsp+30h] [rbp-D0h] BYREF
  ULONG Value; // [rsp+34h] [rbp-CCh] BYREF
  ULONG v17; // [rsp+38h] [rbp-C8h] BYREF
  int v18; // [rsp+3Ch] [rbp-C4h] BYREF
  union _LARGE_INTEGER v19; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v20[2]; // [rsp+48h] [rbp-B8h] BYREF
  ULONG ResultLength; // [rsp+58h] [rbp-A8h] BYREF
  ULONG v22; // [rsp+5Ch] [rbp-A4h] BYREF
  void *FileHandle; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING FileName; // [rsp+70h] [rbp-90h] BYREF
  union _LARGE_INTEGER MaxiumSize; // [rsp+80h] [rbp-80h] BYREF
  union _LARGE_INTEGER InitialSize; // [rsp+88h] [rbp-78h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+90h] [rbp-70h] BYREF
  struct _UNICODE_STRING v28; // [rsp+A0h] [rbp-60h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+B0h] [rbp-50h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+C0h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D0h] [rbp-30h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+100h] [rbp+0h] BYREF
  __int128 KeyValueInformation; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v34[8]; // [rsp+120h] [rbp+20h] BYREF
  unsigned int v35; // [rsp+128h] [rbp+28h]
  int v36; // [rsp+12Ch] [rbp+2Ch] BYREF
  wchar_t pszDest[264]; // [rsp+330h] [rbp+230h] BYREF

  *(_QWORD *)&ValueName.Length = 2097182;
  Value = 0;
  v17 = 0;
  InitialSize.QuadPart = 0;
  MaxiumSize.QuadPart = 0;
  ValueName.Buffer = L"SwapfileControl";
  FileHandle = 0;
  v28.Buffer = L"SwapFile";
  *(_QWORD *)&v28.Length = 1179664;
  v15 = 0;
  DestinationString = 0;
  v18 = 0;
  FileName = 0;
  ResultLength = 0;
  memset(&ObjectAttributes, 0, 44);
  HIDWORD(v20[0]) = 0;
  v22 = 0;
  IoStatusBlock = 0;
  UnicodeString = 0;
  KeyValueInformation = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  if ( !SmpClientSku )
  {
    v2 = -1073741637;
    goto LABEL_46;
  }
  if ( NtQueryValueKey(
         SmpMmKey,
         &ValueName,
         KeyValuePartialInformationAlign64,
         &KeyValueInformation,
         0x10u,
         &ResultLength) >= 0
    && (_DWORD)KeyValueInformation == 4
    && *(_QWORD *)((char *)&KeyValueInformation + 4) == 4 )
  {
LABEL_6:
    v2 = -1073741710;
    goto LABEL_46;
  }
  if ( NtQueryValueKey(SmpMmKey, &v28, KeyValuePartialInformation, v34, 0x210u, &v22) < 0 || v35 > 0x204 )
  {
    if ( !SmpMaxSwapFileSize )
      goto LABEL_6;
    if ( !SmpOsVolumeDescriptor )
    {
      v2 = -1073741275;
      goto LABEL_46;
    }
    v2 = RtlStringCbPrintfW(
           pszDest,
           0x208u,
           L"\\??\\%c:\\%s",
           *(unsigned __int16 *)(SmpOsVolumeDescriptor + 28),
           L"swapfile.sys");
    if ( v2 < 0 )
      goto LABEL_46;
    RtlInitUnicodeString(&FileName, pszDest);
    v7 = SmpOsVolumeDescriptor;
    v8 = SmpMaxSwapFileSize;
    v9 = (-(__int64)((*(_DWORD *)(SmpOsVolumeDescriptor + 16) & 0x20) != 0) & 0xFFFFFFFFF1000000uLL) + 0x10000000;
    v19.QuadPart = v9;
    if ( SmpMaxSwapFileSize == -1 )
    {
      v8 = (unsigned __int64)(3 * SmpMemorySize) >> 1;
      v10 = v8;
    }
    else
    {
      v10 = SmpMaxSwapFileSize;
      if ( v9 >= SmpMaxSwapFileSize )
      {
        v9 = SmpMaxSwapFileSize;
        v19.QuadPart = SmpMaxSwapFileSize;
        v11 = SmpMaxSwapFileSize;
LABEL_29:
        if ( v10 >= *(_QWORD *)(SmpOsVolumeDescriptor + 40) / 0xAuLL )
        {
          v8 = *(_QWORD *)(SmpOsVolumeDescriptor + 40) / 0xAuLL;
          v10 = v8;
        }
        if ( v10 <= v11 )
          v8 = v9;
        v20[0] = v8;
LABEL_34:
        SmpUpdatePagingFileSizes(&v19, v20);
        ObjectAttributes.ObjectName = &FileName;
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 64;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        if ( NtOpenFile(&FileHandle, 0xC0100000, &ObjectAttributes, &IoStatusBlock, 3u, 0x28u) >= 0 )
        {
          SmpTrimPagingFileExtents(FileHandle, &FileName);
          NtClose(FileHandle);
        }
        v12 = 0x80000000;
        if ( (*(_BYTE *)(v7 + 16) & 8) != 0
          && (int)SmpCheckHybridPriority(*(unsigned int *)(v7 + 20), &v15, &v18) >= 0
          && v18
          && (v15 & 0xFFFFFFF0) == 0 )
        {
          v12 = (v15 | 0xFFFFFFE0) << 26;
        }
        InitialSize = v19;
        MaxiumSize = (union _LARGE_INTEGER)v20[0];
        v13 = NtCreatePagingFile(&FileName, &InitialSize, &MaxiumSize, v12);
        v2 = v13;
        if ( v13 < 0 )
        {
          SmpLogFailure("SmpCreateWorkingSetSwapPagingFile", 1994, (unsigned int)v13);
        }
        else
        {
          SmpWsSwapPagefileCreated = 1;
          *a1 = v7;
        }
        goto LABEL_46;
      }
    }
    v11 = v9;
    goto LABEL_29;
  }
  LOWORD(v20[0]) = v35;
  WORD1(v20[0]) = v35;
  v20[1] = &v36;
  v2 = SmpParseCommandLine((__int64)v20, 0, &DestinationString, 0, &UnicodeString);
  if ( v2 >= 0 )
  {
    FileName = DestinationString;
    v2 = SmpParseSwapOrPageFileArguments(&UnicodeString, &Value, &v17);
    RtlFreeUnicodeString(&UnicodeString);
    if ( v2 >= 0 )
    {
      if ( !Value || !v17 )
        goto LABEL_6;
      v3 = 0;
      v19.QuadPart = (unsigned __int64)Value << 20;
      v4 = 63;
      v20[0] = (unsigned __int64)v17 << 20;
      if ( FileName.Length )
      {
        do
        {
          if ( FileName.Buffer[v3] == 58 )
            break;
          v4 = FileName.Buffer[v3++];
        }
        while ( FileName.Length != v3 );
        if ( FileName.Length != v3 )
        {
          v5 = RtlUpcaseUnicodeChar(v4);
          v6 = (__int64 *)SmpVolumeDescriptorList;
          while ( v6 != &SmpVolumeDescriptorList )
          {
            v7 = (__int64)v6;
            v6 = (__int64 *)*v6;
            if ( *(_WORD *)(v7 + 28) == v5 )
              goto LABEL_34;
          }
        }
      }
      v2 = -1073741772;
    }
  }
LABEL_46:
  RtlFreeUnicodeString(&DestinationString);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140010344  push    rbp
0x140010346  push    rbx
0x140010347  push    rsi
0x140010348  push    rdi
0x140010349  push    r14
0x14001034b  push    r15
0x14001034d  lea     rbp, [rsp-458h]
0x140010355  sub     rsp, 558h
0x14001035c  mov     rax, cs:__security_cookie
0x140010363  xor     rax, rsp
0x140010366  mov     [rbp+480h+var_40], rax
0x14001036d  xor     r14d, r14d
0x140010370  mov     qword ptr [rbp+480h+ValueName.Length], 20001Eh
0x140010378  xorps   xmm0, xmm0
0x14001037b  mov     [rsp+580h+Value], r14d
0x140010380  xor     eax, eax
0x140010382  mov     [rsp+580h+var_548], r14d
0x140010387  xorps   xmm1, xmm1
0x14001038a  mov     qword ptr [rbp+480h+InitialSize], r14
0x14001038e  lea     rax, aSwapfilecontro; "SwapfileControl"
0x140010395  mov     qword ptr [rbp+480h+MaxiumSize], r14
0x140010399  mov     [rbp+480h+ValueName.Buffer], rax
0x14001039d  lea     r15d, [r14+20h]
0x1400103a1  lea     rax, aSwapfile; "SwapFile"
0x1400103a8  mov     [rsp+580h+FileHandle], r14
0x1400103ad  mov     rsi, rcx
0x1400103b0  mov     [rbp+480h+var_4E0.Buffer], rax
0x1400103b4  movups  xmmword ptr [rbp+480h+ObjectAttributes.ObjectName], xmm0
0x1400103b8  xor     edx, edx; SourceString
0x1400103ba  mov     qword ptr [rbp+480h+var_4E0.Length], 120010h
0x1400103c2  lea     rcx, [rbp+480h+DestinationString]; DestinationString
0x1400103c6  mov     [rsp+580h+var_550], r14d
0x1400103cb  movups  xmmword ptr [rbp+480h+DestinationString.Length], xmm0
0x1400103cf  lea     ebx, [r14+10h]
0x1400103d3  mov     [rsp+580h+var_544], r14d
0x1400103d8  movups  xmmword ptr [rsp+580h+FileName.Length], xmm1
0x1400103dd  mov     [rsp+580h+var_528], r14d
0x1400103e2  movups  xmmword ptr [rbp+480h+ObjectAttributes.Length], xmm0
0x1400103e6  mov     dword ptr [rsp+580h+var_538+4], r14d
0x1400103eb  movups  xmmword ptr [rbp+480h+ObjectAttributes+1Ch], xmm0
0x1400103ef  mov     [rsp+580h+var_524], r14d
0x1400103f4  movups  xmmword ptr [rbp+480h+IoStatusBlock], xmm0
0x1400103f8  movups  xmmword ptr [rbp+480h+UnicodeString.Length], xmm0
0x1400103fc  movups  [rbp+480h+KeyValueInformation], xmm1
0x140010400  call    cs:__imp_RtlInitUnicodeString
0x140010406  cmp     cs:SmpClientSku, r14b
0x14001040d  jnz     short loc_140010419
0x14001040f  mov     ebx, 0C00000BBh
0x140010414  jmp     loc_14001079C
0x140010419  mov     rcx, cs:SmpMmKey; KeyHandle
0x140010420  lea     rax, [rsp+580h+var_528]
0x140010425  mov     [rsp+580h+ResultLength], rax; ResultLength
0x14001042a  lea     r9, [rbp+480h+KeyValueInformation]; KeyValueInformation
0x14001042e  mov     r8d, 4; KeyValueInformationClass
0x140010434  mov     [rsp+580h+Length], ebx; Length
0x140010438  lea     rdx, [rbp+480h+ValueName]; ValueName
0x14001043c  call    cs:__imp_NtQueryValueKey
0x140010442  test    eax, eax
0x140010444  js      short loc_140010462
0x140010446  cmp     dword ptr [rbp+480h+KeyValueInformation], 4
0x14001044a  jnz     short loc_140010462
0x14001044c  cmp     dword ptr [rbp+480h+KeyValueInformation+4], 4
0x140010450  jnz     short loc_140010462
0x140010452  cmp     dword ptr [rbp+480h+KeyValueInformation+8], r14d
0x140010456  jnz     short loc_140010462
0x140010458  mov     ebx, 0C0000072h
0x14001045d  jmp     loc_14001079C
0x140010462  mov     rcx, cs:SmpMmKey; KeyHandle
0x140010469  lea     rax, [rsp+580h+var_524]
0x14001046e  mov     [rsp+580h+ResultLength], rax; ResultLength
0x140010473  lea     r9, [rbp+480h+var_460]; KeyValueInformation
0x140010477  mov     r8d, 2; KeyValueInformationClass
0x14001047d  mov     [rsp+580h+Length], 210h; Length
0x140010485  lea     rdx, [rbp+480h+var_4E0]; ValueName
0x140010489  call    cs:__imp_NtQueryValueKey
0x14001048f  test    eax, eax
0x140010491  js      loc_1400105A3
0x140010497  mov     rax, [rbp+480h+var_458]
0x14001049b  cmp     eax, 204h
0x1400104a0  ja      loc_1400105A3
0x1400104a6  mov     word ptr [rsp+580h+var_538], ax
0x1400104ab  lea     r8, [rbp+480h+DestinationString]
0x1400104af  mov     word ptr [rsp+580h+var_538+2], ax
0x1400104b4  lea     rcx, [rsp+580h+var_538]
0x1400104b9  lea     rax, [rbp+480h+var_458+4]
0x1400104bd  xor     r9d, r9d
0x1400104c0  mov     [rsp+580h+var_530], rax
0x1400104c5  xor     edx, edx
0x1400104c7  lea     rax, [rbp+480h+UnicodeString]
0x1400104cb  mov     qword ptr [rsp+580h+Length], rax
0x1400104d0  call    SmpParseCommandLine
0x1400104d5  mov     ebx, eax
0x1400104d7  test    eax, eax
0x1400104d9  js      loc_14001079C
0x1400104df  movaps  xmm0, xmmword ptr [rbp+480h+DestinationString.Length]
0x1400104e3  lea     r8, [rsp+580h+var_548]; PULONG
0x1400104e8  lea     rdx, [rsp+580h+Value]; Value
0x1400104ed  movdqa  xmmword ptr [rsp+580h+FileName.Length], xmm0
0x1400104f3  lea     rcx, [rbp+480h+UnicodeString]; String
0x1400104f7  call    SmpParseSwapOrPageFileArguments
0x1400104fc  lea     rcx, [rbp+480h+UnicodeString]; UnicodeString
0x140010500  mov     ebx, eax
0x140010502  call    cs:__imp_RtlFreeUnicodeString
0x140010508  test    ebx, ebx
0x14001050a  js      loc_14001079C
0x140010510  mov     eax, [rsp+580h+Value]
0x140010514  test    eax, eax
0x140010516  jz      loc_140010458
0x14001051c  mov     ecx, [rsp+580h+var_548]
0x140010520  test    ecx, ecx
0x140010522  jz      loc_140010458
0x140010528  movzx   r8d, [rsp+580h+FileName.Length]
0x14001052e  mov     edx, r14d
0x140010531  shl     rax, 14h
0x140010535  mov     [rsp+580h+var_540], rax
0x14001053a  mov     eax, ecx
0x14001053c  shl     rax, 14h
0x140010540  mov     ecx, 3Fh ; '?'
0x140010545  mov     [rsp+580h+var_538], rax
0x14001054a  test    r8d, r8d
0x14001054d  jz      short loc_140010599
0x14001054f  mov     r9, [rsp+580h+FileName.Buffer]
0x140010554  mov     eax, edx
0x140010556  cmp     word ptr [r9+rax*2], 3Ah ; ':'
0x14001055c  jz      short loc_14001056A
0x14001055e  movzx   ecx, word ptr [r9+rax*2]; SourceCharacter
0x140010563  inc     edx
0x140010565  cmp     r8d, edx
0x140010568  jnz     short loc_140010554
0x14001056a  cmp     r8d, edx
0x14001056d  jz      short loc_140010599
0x14001056f  call    cs:__imp_RtlUpcaseUnicodeChar
0x140010575  mov     rcx, cs:SmpVolumeDescriptorList
0x14001057c  lea     rdx, SmpVolumeDescriptorList
0x140010583  cmp     rcx, rdx
0x140010586  jz      short loc_140010599
0x140010588  mov     rdi, rcx
0x14001058b  mov     rcx, [rcx]
0x14001058e  cmp     [rdi+1Ch], ax
0x140010592  jnz     short loc_14001057C
0x140010594  jmp     loc_14001067E
0x140010599  mov     ebx, 0C0000034h
0x14001059e  jmp     loc_14001079C
0x1400105a3  cmp     cs:SmpMaxSwapFileSize, r14
0x1400105aa  jz      loc_140010458
0x1400105b0  mov     rax, cs:SmpOsVolumeDescriptor
0x1400105b7  test    rax, rax
0x1400105ba  jnz     short loc_1400105C6
0x1400105bc  mov     ebx, 0C0000225h
0x1400105c1  jmp     loc_14001079C
0x1400105c6  movzx   r9d, word ptr [rax+1Ch]
0x1400105cb  lea     r8, aCS; "\\??\\%c:\\%s"
0x1400105d2  lea     rax, aSwapfileSys; "swapfile.sys"
0x1400105d9  mov     edx, 208h; cbDest
0x1400105de  lea     rcx, [rbp+480h+pszDest]; pszDest
0x1400105e5  mov     qword ptr [rsp+580h+Length], rax
0x1400105ea  call    RtlStringCbPrintfW
0x1400105ef  mov     ebx, eax
0x1400105f1  test    eax, eax
0x1400105f3  js      loc_14001079C
0x1400105f9  lea     rdx, [rbp+480h+pszDest]; SourceString
0x140010600  lea     rcx, [rsp+580h+FileName]; DestinationString
0x140010605  call    cs:__imp_RtlInitUnicodeString
0x14001060b  mov     rdi, cs:SmpOsVolumeDescriptor
0x140010612  mov     rcx, cs:SmpMaxSwapFileSize
0x140010619  mov     eax, [rdi+10h]
0x14001061c  and     al, r15b
0x14001061f  neg     al
0x140010621  sbb     r8, r8
0x140010624  and     r8, 0FFFFFFFFF1000000h
0x14001062b  add     r8, 10000000h
0x140010632  mov     [rsp+580h+var_540], r8
0x140010637  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14001063b  jnz     loc_14001076C
0x140010641  mov     rax, cs:SmpMemorySize
0x140010648  lea     rcx, [rax+rax*2]
0x14001064c  shr     rcx, 1
0x14001064f  mov     r9, rcx
0x140010652  mov     r10, r8
0x140010655  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14001065f  mul     qword ptr [rdi+28h]
0x140010663  shr     rdx, 3
0x140010667  cmp     r9, rdx
0x14001066a  jb      short loc_140010672
0x14001066c  mov     rcx, rdx
0x14001066f  mov     r9, rdx
0x140010672  cmp     r9, r10
0x140010675  cmovbe  rcx, r8
0x140010679  mov     [rsp+580h+var_538], rcx
0x14001067e  lea     rdx, [rsp+580h+var_538]
0x140010683  lea     rcx, [rsp+580h+var_540]
0x140010688  call    SmpUpdatePagingFileSizes
0x14001068d  lea     rax, [rsp+580h+FileName]
0x140010692  mov     dword ptr [rsp+580h+ResultLength], 28h ; '('; OpenOptions
0x14001069a  xorps   xmm0, xmm0
0x14001069d  mov     [rbp+480h+ObjectAttributes.ObjectName], rax
0x1400106a1  lea     r9, [rbp+480h+IoStatusBlock]; IoStatusBlock
0x1400106a5  mov     [rbp+480h+ObjectAttributes.Length], 30h ; '0'
0x1400106ac  lea     r8, [rbp+480h+ObjectAttributes]; ObjectAttributes
0x1400106b0  mov     [rbp+480h+ObjectAttributes.RootDirectory], r14
0x1400106b4  mov     edx, 0C0100000h; DesiredAccess
0x1400106b9  mov     [rbp+480h+ObjectAttributes.Attributes], 40h ; '@'
0x1400106c0  lea     rcx, [rsp+580h+FileHandle]; FileHandle
0x1400106c5  mov     [rsp+580h+Length], 3; ShareAccess
0x1400106cd  movdqu  xmmword ptr [rbp+480h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400106d2  call    cs:__imp_NtOpenFile
0x1400106d8  test    eax, eax
0x1400106da  js      short loc_1400106F6
0x1400106dc  mov     rcx, [rsp+580h+FileHandle]
0x1400106e1  lea     rdx, [rsp+580h+FileName]
0x1400106e6  call    SmpTrimPagingFileExtents
0x1400106eb  mov     rcx, [rsp+580h+FileHandle]; Handle
0x1400106f0  call    cs:__imp_NtClose
0x1400106f6  test    byte ptr [rdi+10h], 8
0x1400106fa  mov     ebx, 80000000h
0x1400106ff  jz      short loc_140010732
0x140010701  mov     ecx, [rdi+14h]
0x140010704  lea     r8, [rsp+580h+var_544]
0x140010709  lea     rdx, [rsp+580h+var_550]
0x14001070e  call    SmpCheckHybridPriority
0x140010713  test    eax, eax
0x140010715  js      short loc_140010732
0x140010717  cmp     [rsp+580h+var_544], r14d
0x14001071c  jz      short loc_140010732
0x14001071e  test    [rsp+580h+var_550], 0FFFFFFF0h
0x140010726  jnz     short loc_140010732
0x140010728  mov     ebx, [rsp+580h+var_550]
0x14001072c  or      ebx, 0FFFFFFE0h
0x14001072f  shl     ebx, 1Ah
0x140010732  mov     rax, [rsp+580h+var_540]
0x140010737  lea     r8, [rbp+480h+MaxiumSize]; MaxiumSize
0x14001073b  mov     qword ptr [rbp+480h+InitialSize], rax
0x14001073f  lea     rdx, [rbp+480h+InitialSize]; InitialSize
0x140010743  mov     rax, [rsp+580h+var_538]
0x140010748  lea     rcx, [rsp+580h+FileName]; FileName
0x14001074d  mov     r9d, ebx; Reserved
0x140010750  mov     qword ptr [rbp+480h+MaxiumSize], rax
0x140010754  call    cs:__imp_NtCreatePagingFile
0x14001075a  mov     ebx, eax
0x14001075c  test    eax, eax
0x14001075e  js      short loc_140010788
0x140010760  mov     cs:SmpWsSwapPagefileCreated, 1
0x140010767  mov     [rsi], rdi
0x14001076a  jmp     short loc_14001079C
0x14001076c  mov     r9, rcx
0x14001076f  cmp     r8, rcx
0x140010772  jb      loc_140010652
0x140010778  mov     r8, rcx
0x14001077b  mov     [rsp+580h+var_540], rcx
0x140010780  mov     r10, rcx
0x140010783  jmp     loc_140010655
0x140010788  mov     r8d, eax
0x14001078b  lea     rcx, aSmpcreateworki; "SmpCreateWorkingSetSwapPagingFile"
0x140010792  mov     edx, 7CAh
0x140010797  call    SmpLogFailure
0x14001079c  lea     rcx, [rbp+480h+DestinationString]; UnicodeString
0x1400107a0  call    cs:__imp_RtlFreeUnicodeString
0x1400107a6  mov     eax, ebx
0x1400107a8  mov     rcx, [rbp+480h+var_40]
0x1400107af  xor     rcx, rsp; StackCookie
0x1400107b2  call    __security_check_cookie
0x1400107b7  add     rsp, 558h
0x1400107be  pop     r15
0x1400107c0  pop     r14
0x1400107c2  pop     rdi
0x1400107c3  pop     rsi
0x1400107c4  pop     rbx
0x1400107c5  pop     rbp
0x1400107c6  retn
```
