# SmpSaveOldPageFiles

- ea: `0x140009100`
- end: `0x1400094b9`
- name: `SmpSaveOldPageFiles`
- size: `953`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000fcf8`

## callees

- `0x140004e30`
- `0x140009100`
- `0x1400107e8`
- `0x140012204`
- `0x140012608`
- `0x14001cc29`
- `0x14001cc40`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x140009303`
- `ntdll!RtlInitUnicodeString` at `0x140009303`
- `ntdll!NtClose` at `0x140009407`
- `ntdll!NtClose` at `0x140009407`
- `ntdll!NtOpenKey` at `0x140009206`
- `ntdll!NtOpenKey` at `0x140009206`
- `ntdll!RtlAllocateHeap` at `0x140009348`
- `ntdll!RtlAllocateHeap` at `0x140009348`
- `ntdll!RtlFreeHeap` at `0x14000944b`
- `ntdll!RtlFreeHeap` at `0x14000948c`
- `ntdll!RtlFreeHeap` at `0x14000944b`
- `ntdll!RtlFreeHeap` at `0x14000948c`
- `ntdll!NtSetValueKey` at `0x1400093dc`
- `ntdll!NtSetValueKey` at `0x1400093dc`
- `ntdll!RtlFreeUnicodeString` at `0x14000949a`
- `ntdll!RtlFreeUnicodeString` at `0x14000949a`
- `ntdll!NtQueryValueKey` at `0x14000923c`
- `ntdll!NtQueryValueKey` at `0x14000923c`
- `ntdll!RtlAppendUnicodeStringToString` at `0x140009382`
- `ntdll!RtlAppendUnicodeStringToString` at `0x140009382`
- `ntdll!NtFlushKey` at `0x1400093ef`
- `ntdll!NtFlushKey` at `0x1400093ef`

## string_xrefs

- `0x140009131`: `\Registry\Machine\System\CurrentControlSet\Control\CrashControl\MachineCrash`
- `0x14000915d`: `SavedPageFilePath`

## pseudocode

```c
void SmpSaveOldPageFiles()
{
  __int64 v0; // rcx
  int v1; // eax
  __int64 v2; // rsi
  struct _UNICODE_STRING *v3; // rbx
  int v4; // edi
  unsigned int v5; // esi
  unsigned int v6; // edi
  USHORT Length; // ax
  unsigned int i; // esi
  __int64 v9; // rax
  PVOID *v10; // r14
  struct _UNICODE_STRING ResultLength_8; // [rsp+38h] [rbp-D0h] BYREF
  ULONG ResultLength[2]; // [rsp+48h] [rbp-C0h] BYREF
  void *KeyHandle; // [rsp+50h] [rbp-B8h] BYREF
  _QWORD v14[2]; // [rsp+58h] [rbp-B0h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD v16[2]; // [rsp+78h] [rbp-90h] BYREF
  struct _UNICODE_STRING v17; // [rsp+88h] [rbp-80h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-70h] BYREF
  __int128 v19; // [rsp+C8h] [rbp-40h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+D8h] [rbp-30h] BYREF
  __int128 KeyValueInformation; // [rsp+E8h] [rbp-20h] BYREF
  unsigned int v22[68]; // [rsp+F8h] [rbp-10h] BYREF
  wchar_t pszDest[64]; // [rsp+208h] [rbp+100h] BYREF

  v14[1] = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\CrashControl\\MachineCrash";
  v14[0] = 10092696;
  ValueName.Buffer = L"SavePageFileContents";
  *(_QWORD *)&ValueName.Length = 2752552;
  v16[1] = L"SavedPageFilePath";
  v16[0] = 2359330;
  v17.Buffer = L"SavedPageFiles";
  *(_QWORD *)&v17.Length = 1966108;
  memset(&ObjectAttributes, 0, 44);
  ResultLength[0] = 0;
  v19 = 0;
  DestinationString = 0;
  memset_0(v22, 0, 0x108u);
  KeyHandle = 0;
  ResultLength_8 = 0;
  KeyValueInformation = 0;
  if ( SmpUseDedicatedDumpFile
    && (ObjectAttributes.Length = 48,
        ObjectAttributes.ObjectName = (PUNICODE_STRING)v14,
        ObjectAttributes.RootDirectory = 0,
        ObjectAttributes.Attributes = 64,
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0,
        NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0)
    && NtQueryValueKey(
         SmpCrashDumpKey,
         &ValueName,
         KeyValuePartialInformationAlign64,
         &KeyValueInformation,
         0x10u,
         ResultLength) >= 0
    && (_DWORD)KeyValueInformation == 4
    && DWORD2(KeyValueInformation) == 1 )
  {
    SmpSavePageFiles = 1;
  }
  else if ( !SmpSavePageFiles )
  {
    v3 = 0;
    v4 = 0;
    goto LABEL_25;
  }
  v1 = SmpQueryPathFromRegistry(v0, v16, 0, &v19);
  v2 = SmpExistingPageFilesList;
  v3 = (struct _UNICODE_STRING *)&v19;
  if ( v1 < 0 )
    v3 = 0;
  while ( (__int64 *)v2 != &SmpExistingPageFilesList )
  {
    v4 = SmpSaveOldPageFile((UNICODE_STRING *)(v2 + 16), v3, v22);
    if ( v4 < 0 )
      goto LABEL_25;
    v2 = *(_QWORD *)v2;
  }
  v4 = RtlStringCbPrintfW(pszDest, 0x80u, L"\\??\\%c:\\%s", (unsigned __int16)SmpOsVolumeLetter, L"swapfile.sys");
  if ( v4 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, pszDest);
    SmpSaveOldPageFile(&DestinationString, v3, v22);
    v5 = v22[1] + 2 * (v22[0] + 1);
    if ( v5 <= 0xFFFF )
    {
      ResultLength_8.Buffer = (PWSTR)RtlAllocateHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v5);
      if ( ResultLength_8.Buffer )
      {
        v6 = 0;
        ResultLength_8.MaximumLength = v5;
        if ( v22[0] )
        {
          do
          {
            RtlAppendUnicodeStringToString(&ResultLength_8, (PCUNICODE_STRING)&v22[4 * v6++ + 2]);
            Length = ResultLength_8.Length + 2;
            ResultLength_8.Length += 2;
          }
          while ( v6 < v22[0] );
        }
        else
        {
          Length = ResultLength_8.Length;
        }
        ResultLength_8.Buffer[(unsigned __int64)Length >> 1] = 0;
        ResultLength_8.Length += 2;
        v4 = NtSetValueKey(SmpCrashDumpKey, &v17, 0, 7u, ResultLength_8.Buffer, v5);
        if ( v4 >= 0 )
          NtFlushKey(SmpCrashDumpKey);
      }
      else
      {
        v4 = -1073741670;
      }
    }
    else
    {
      v4 = -1073741562;
    }
  }
LABEL_25:
  if ( KeyHandle )
    NtClose(KeyHandle);
  for ( i = 0; i < v22[0]; ++i )
  {
    v9 = 4LL * i;
    v10 = (PVOID *)&v22[v9 + 4];
    if ( *(_QWORD *)&v22[v9 + 4] )
    {
      if ( v4 < 0 )
        SmpDeletePagingFile((struct _UNICODE_STRING *)&v22[v9 + 2]);
      RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, *v10);
    }
  }
  if ( ResultLength_8.Buffer )
    RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, ResultLength_8.Buffer);
  if ( v3 )
    RtlFreeUnicodeString(v3);
}

```

## disassembly

```asm
0x140009100  mov     r11, rsp
0x140009103  push    rbp
0x140009104  push    rbx
0x140009105  lea     rbp, [r11-1A8h]
0x14000910c  sub     rsp, 298h
0x140009113  mov     rax, cs:__security_cookie
0x14000911a  xor     rax, rsp
0x14000911d  mov     [rbp+1A0h+var_20], rax
0x140009124  xor     eax, eax
0x140009126  mov     [r11+8], rsi
0x14000912a  xorps   xmm0, xmm0
0x14000912d  mov     [r11+10h], rdi
0x140009131  lea     rax, aRegistryMachin_52; "\\Registry\\Machine\\System\\CurrentCon"...
0x140009138  mov     [r11+18h], r14
0x14000913c  mov     [rsp+2A0h+var_248], rax
0x140009141  lea     rcx, [rbp+1A0h+var_1B0]; void *
0x140009145  lea     rax, aSavepagefileco; "SavePageFileContents"
0x14000914c  mov     [rsp+2A0h+var_250], 9A0098h
0x140009155  mov     [rsp+2A0h+ValueName.Buffer], rax
0x14000915a  xorps   xmm1, xmm1
0x14000915d  lea     rax, aSavedpagefilep; "SavedPageFilePath"
0x140009164  mov     qword ptr [rsp+2A0h+ValueName.Length], 2A0028h
0x14000916d  mov     [rsp+78h], rax
0x140009172  xor     r14d, r14d
0x140009175  lea     rax, aSavedpagefiles; "SavedPageFiles"
0x14000917c  mov     [rsp+2A0h+var_230], 240022h
0x140009185  movups  xmmword ptr [rbp+1A0h+ObjectAttributes.ObjectName], xmm0
0x140009189  xor     edx, edx; Val
0x14000918b  mov     [rbp+1A0h+var_220.Buffer], rax
0x14000918f  mov     r8d, 108h; Size
0x140009195  mov     qword ptr [rbp+1A0h+var_220.Length], 1E001Ch
0x14000919d  movups  xmmword ptr [rbp+1A0h+ObjectAttributes.Length], xmm0
0x1400091a1  mov     [rsp+2A0h+var_260], r14d
0x1400091a6  movups  xmmword ptr [rbp+1A0h+ObjectAttributes+1Ch], xmm0
0x1400091aa  movups  [rbp+1A0h+var_1E0], xmm0
0x1400091ae  movups  xmmword ptr [rbp+1A0h+DestinationString.Length], xmm1
0x1400091b2  call    memset_0
0x1400091b7  cmp     cs:SmpUseDedicatedDumpFile, r14b
0x1400091be  xorps   xmm0, xmm0
0x1400091c1  xorps   xmm1, xmm1
0x1400091c4  mov     [rsp+2A0h+KeyHandle], r14
0x1400091c9  movups  xmmword ptr [rsp+2A0h+ResultLength+8], xmm0
0x1400091ce  movups  [rbp+1A0h+KeyValueInformation], xmm1
0x1400091d2  jz      loc_1400092AE
0x1400091d8  lea     rax, [rsp+2A0h+var_250]
0x1400091dd  mov     [rbp+1A0h+ObjectAttributes.Length], 30h ; '0'
0x1400091e4  lea     r8, [rbp+1A0h+ObjectAttributes]; ObjectAttributes
0x1400091e8  mov     [rbp+1A0h+ObjectAttributes.ObjectName], rax
0x1400091ec  mov     edx, 20019h; DesiredAccess
0x1400091f1  mov     [rbp+1A0h+ObjectAttributes.RootDirectory], r14
0x1400091f5  lea     rcx, [rsp+2A0h+KeyHandle]; KeyHandle
0x1400091fa  mov     [rbp+1A0h+ObjectAttributes.Attributes], 40h ; '@'
0x140009201  movdqu  xmmword ptr [rbp+1A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140009206  call    cs:__imp_NtOpenKey
0x14000920c  test    eax, eax
0x14000920e  js      loc_1400092AE
0x140009214  mov     rcx, cs:SmpCrashDumpKey; KeyHandle
0x14000921b  lea     rax, [rsp+2A0h+var_260]
0x140009220  mov     [rsp+2A0h+ResultLength], rax; ResultLength
0x140009225  lea     r9, [rbp+1A0h+KeyValueInformation]; KeyValueInformation
0x140009229  mov     r8d, 4; KeyValueInformationClass
0x14000922f  mov     [rsp+2A0h+Length], 10h; Length
0x140009237  lea     rdx, [rsp+2A0h+ValueName]; ValueName
0x14000923c  call    cs:__imp_NtQueryValueKey
0x140009242  test    eax, eax
0x140009244  js      short loc_1400092AE
0x140009246  cmp     dword ptr [rbp+1A0h+KeyValueInformation], 4
0x14000924a  jnz     short loc_1400092AE
0x14000924c  cmp     dword ptr [rbp+1A0h+KeyValueInformation+8], 1
0x140009250  jnz     short loc_1400092AE
0x140009252  mov     cs:SmpSavePageFiles, 1
0x140009259  lea     r9, [rbp+1A0h+var_1E0]
0x14000925d  mov     [rsp+290h], r15
0x140009265  xor     r8d, r8d
0x140009268  lea     rdx, [rsp+2A0h+var_230]
0x14000926d  call    SmpQueryPathFromRegistry
0x140009272  mov     rsi, cs:SmpExistingPageFilesList
0x140009279  lea     rbx, [rbp+1A0h+var_1E0]
0x14000927d  test    eax, eax
0x14000927f  lea     r15, SmpExistingPageFilesList
0x140009286  cmovs   rbx, r14
0x14000928a  cmp     rsi, r15
0x14000928d  jz      short loc_1400092C2
0x14000928f  lea     rcx, [rsi+10h]; SourceString
0x140009293  mov     rdx, rbx
0x140009296  lea     r8, [rbp+1A0h+var_1B0]
0x14000929a  call    SmpSaveOldPageFile
0x14000929f  mov     edi, eax
0x1400092a1  test    eax, eax
0x1400092a3  js      loc_1400093F5
0x1400092a9  mov     rsi, [rsi]
0x1400092ac  jmp     short loc_14000928A
0x1400092ae  cmp     cs:SmpSavePageFiles, r14b
0x1400092b5  jnz     short loc_140009259
0x1400092b7  mov     rbx, r14
0x1400092ba  mov     edi, r14d
0x1400092bd  jmp     loc_1400093FD
0x1400092c2  movzx   r9d, cs:SmpOsVolumeLetter
0x1400092ca  lea     rax, aSwapfileSys; "swapfile.sys"
0x1400092d1  lea     r8, aCS; "\\??\\%c:\\%s"
0x1400092d8  mov     qword ptr [rsp+2A0h+Length], rax
0x1400092dd  mov     edx, 80h; cbDest
0x1400092e2  lea     rcx, [rbp+1A0h+pszDest]; pszDest
0x1400092e9  call    RtlStringCbPrintfW
0x1400092ee  mov     edi, eax
0x1400092f0  test    eax, eax
0x1400092f2  js      loc_1400093F5
0x1400092f8  lea     rdx, [rbp+1A0h+pszDest]; SourceString
0x1400092ff  lea     rcx, [rbp+1A0h+DestinationString]; DestinationString
0x140009303  call    cs:__imp_RtlInitUnicodeString
0x140009309  lea     r8, [rbp+1A0h+var_1B0]
0x14000930d  mov     rdx, rbx
0x140009310  lea     rcx, [rbp+1A0h+DestinationString]; SourceString
0x140009314  call    SmpSaveOldPageFile
0x140009319  mov     esi, [rbp+1A0h+var_1B0]
0x14000931c  mov     eax, [rbp+1A0h+var_1AC]
0x14000931f  inc     esi
0x140009321  lea     esi, [rax+rsi*2]
0x140009324  cmp     esi, 0FFFFh
0x14000932a  jbe     short loc_140009336
0x14000932c  mov     edi, 0C0000106h
0x140009331  jmp     loc_1400093F5
0x140009336  mov     rcx, gs:60h
0x14000933f  xor     edx, edx; Flags
0x140009341  mov     r8d, esi; Size
0x140009344  mov     rcx, [rcx+30h]; HeapHandle
0x140009348  call    cs:__imp_RtlAllocateHeap
0x14000934e  mov     [rsp+2A0h+Data], rax
0x140009353  test    rax, rax
0x140009356  jnz     short loc_140009362
0x140009358  mov     edi, 0C000009Ah
0x14000935d  jmp     loc_1400093F5
0x140009362  mov     edi, r14d
0x140009365  mov     word ptr [rsp+2A0h+ResultLength+0Ah], si
0x14000936a  cmp     [rbp+1A0h+var_1B0], r14d
0x14000936e  jbe     short loc_14000939F
0x140009370  mov     eax, edi
0x140009372  lea     rdx, [rbp+1A0h+var_1A8]
0x140009376  shl     rax, 4
0x14000937a  lea     rcx, [rsp+2A0h+ResultLength+8]; Destination
0x14000937f  add     rdx, rax; Source
0x140009382  call    cs:__imp_RtlAppendUnicodeStringToString
0x140009388  movzx   eax, word ptr [rsp+2A0h+ResultLength+8]
0x14000938d  inc     edi
0x14000938f  add     ax, 2
0x140009393  mov     word ptr [rsp+2A0h+ResultLength+8], ax
0x140009398  cmp     edi, [rbp+1A0h+var_1B0]
0x14000939b  jb      short loc_140009370
0x14000939d  jmp     short loc_1400093A4
0x14000939f  movzx   eax, word ptr [rsp+2A0h+ResultLength+8]
0x1400093a4  movzx   edx, ax
0x1400093a7  mov     r9d, 7; Type
0x1400093ad  mov     rax, [rsp+2A0h+Data]
0x1400093b2  xor     r8d, r8d; TitleIndex
0x1400093b5  shr     rdx, 1
0x1400093b8  mov     dword ptr [rsp+2A0h+ResultLength], esi; DataSize
0x1400093bc  mov     [rax+rdx*2], r14w
0x1400093c1  lea     rdx, [rbp+1A0h+var_220]; ValueName
0x1400093c5  mov     rax, [rsp+2A0h+Data]
0x1400093ca  mov     rcx, cs:SmpCrashDumpKey; KeyHandle
0x1400093d1  add     word ptr [rsp+2A0h+ResultLength+8], 2
0x1400093d7  mov     qword ptr [rsp+2A0h+Length], rax; Data
0x1400093dc  call    cs:__imp_NtSetValueKey
0x1400093e2  mov     edi, eax
0x1400093e4  test    eax, eax
0x1400093e6  js      short loc_1400093F5
0x1400093e8  mov     rcx, cs:SmpCrashDumpKey; KeyHandle
0x1400093ef  call    cs:__imp_NtFlushKey
0x1400093f5  mov     r15, [rsp+290h]
0x1400093fd  mov     rcx, [rsp+2A0h+KeyHandle]; Handle
0x140009402  test    rcx, rcx
0x140009405  jz      short loc_14000940D
0x140009407  call    cs:__imp_NtClose
0x14000940d  mov     esi, r14d
0x140009410  cmp     [rbp+1A0h+var_1B0], r14d
0x140009414  jbe     short loc_140009458
0x140009416  mov     eax, esi
0x140009418  lea     r14, [rbp+1A0h+var_1A0]
0x14000941c  shl     rax, 4
0x140009420  add     r14, rax
0x140009423  cmp     qword ptr [r14], 0
0x140009427  jz      short loc_140009451
0x140009429  test    edi, edi
0x14000942b  jns     short loc_140009439
0x14000942d  lea     rcx, [rbp+1A0h+var_1A8]
0x140009431  add     rcx, rax
0x140009434  call    SmpDeletePagingFile
0x140009439  mov     rcx, gs:60h
0x140009442  xor     edx, edx; Flags
0x140009444  mov     r8, [r14]; BaseAddress
0x140009447  mov     rcx, [rcx+30h]; HeapHandle
0x14000944b  call    cs:__imp_RtlFreeHeap
0x140009451  inc     esi
0x140009453  cmp     esi, [rbp+1A0h+var_1B0]
0x140009456  jb      short loc_140009416
0x140009458  cmp     [rsp+2A0h+Data], 0
0x14000945e  mov     r14, [rsp+2A0h+arg_10]
0x140009466  mov     rdi, [rsp+2A0h+arg_8]
0x14000946e  mov     rsi, [rsp+2A0h+arg_0]
0x140009476  jz      short loc_140009492
0x140009478  mov     rcx, gs:60h
0x140009481  xor     edx, edx; Flags
0x140009483  mov     r8, [rsp+2A0h+Data]; BaseAddress
0x140009488  mov     rcx, [rcx+30h]; HeapHandle
0x14000948c  call    cs:__imp_RtlFreeHeap
0x140009492  test    rbx, rbx
0x140009495  jz      short loc_1400094A0
0x140009497  mov     rcx, rbx; UnicodeString
0x14000949a  call    cs:__imp_RtlFreeUnicodeString
0x1400094a0  mov     rcx, [rbp+1A0h+var_20]
0x1400094a7  xor     rcx, rsp; StackCookie
0x1400094aa  call    __security_check_cookie
0x1400094af  add     rsp, 298h
0x1400094b6  pop     rbx
0x1400094b7  pop     rbp
0x1400094b8  retn
```
