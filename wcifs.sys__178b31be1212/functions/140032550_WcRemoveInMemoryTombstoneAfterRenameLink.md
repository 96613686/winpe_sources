# WcRemoveInMemoryTombstoneAfterRenameLink

- ea: `0x140032550`
- end: `0x140032921`
- name: `WcRemoveInMemoryTombstoneAfterRenameLink`
- size: `977`
- prototype: `__int64 __fastcall(__int64, __int64, char)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140031940`

## callees

- `0x140001008`
- `0x140001030`
- `0x140001500`
- `0x1400020c4`
- `0x140007c60`
- `0x14001bf24`
- `0x14002ee60`
- `0x140032550`

## import_xrefs

- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140032763`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140032763`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14003273e`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14003273e`
- `ntoskrnl!RtlDowncaseUnicodeString` at `0x140032644`
- `ntoskrnl!RtlDowncaseUnicodeString` at `0x140032644`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400326fe`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400326fe`
- `ntoskrnl!KeWaitForSingleObject` at `0x140032725`
- `ntoskrnl!KeWaitForSingleObject` at `0x140032725`
- `ntoskrnl!KeSetEvent` at `0x140032892`
- `ntoskrnl!KeSetEvent` at `0x140032892`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400325b6`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400325b6`
- `ntoskrnl!RtlHashUnicodeString` at `0x140032667`
- `ntoskrnl!RtlHashUnicodeString` at `0x140032667`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400326e7`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140032780`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400326e7`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140032780`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003287e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400328ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003287e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400328ac`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14003269c`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14003269c`
- `FLTMGR!FltParseFileName` at `0x1400325e7`
- `FLTMGR!FltParseFileName` at `0x1400325e7`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400328c1`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400328c1`
- `FLTMGR!FltReleaseContext` at `0x1400328d6`
- `FLTMGR!FltReleaseContext` at `0x1400328ea`
- `FLTMGR!FltReleaseContext` at `0x1400328d6`
- `FLTMGR!FltReleaseContext` at `0x1400328ea`

## pseudocode

```c
__int64 __fastcall WcRemoveInMemoryTombstoneAfterRenameLink(__int64 a1, __int64 a2, char a3)
{
  __int64 v3; // rax
  char *v4; // rdi
  __int64 v7; // rbx
  int FileNameInformationUnsafe; // ebx
  char ContextFileObject; // al
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v11; // rax
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v12; // rsi
  int v13; // edx
  __int64 v14; // rcx
  int v16; // [rsp+38h] [rbp-81h]
  char v17; // [rsp+40h] [rbp-79h] BYREF
  char v18; // [rsp+41h] [rbp-78h] BYREF
  ULONG HashValue; // [rsp+44h] [rbp-75h] BYREF
  char *v20; // [rsp+48h] [rbp-71h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+50h] [rbp-69h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-61h] BYREF
  PFLT_CONTEXT Context; // [rsp+68h] [rbp-51h] BYREF
  UNICODE_STRING FileName; // [rsp+70h] [rbp-49h] BYREF
  struct _UNICODE_STRING FinalComponent; // [rsp+80h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v26; // [rsp+90h] [rbp-29h] BYREF
  char *v27; // [rsp+B0h] [rbp-9h]
  __int64 v28; // [rsp+B8h] [rbp-1h]
  char *v29; // [rsp+C0h] [rbp+7h]
  __int64 v30; // [rsp+C8h] [rbp+Fh]
  char **v31; // [rsp+D0h] [rbp+17h]
  __int64 v32; // [rsp+D8h] [rbp+1Fh]

  v3 = *(_QWORD *)(a1 + 16);
  v4 = 0;
  v20 = 0;
  Context = 0;
  v7 = *(_QWORD *)(v3 + 56);
  HashValue = 0;
  FinalComponent = 0;
  FileNameInformation = 0;
  FileName = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  FileName.MaximumLength = *(_WORD *)(v7 + 16);
  FileName.Length = *(_WORD *)(v7 + 16);
  FileName.Buffer = (PWSTR)(v7 + 20);
  FileNameInformationUnsafe = FltParseFileName(&FileName, 0, 0, &FinalComponent);
  if ( FileNameInformationUnsafe >= 0 )
  {
    ContextFileObject = WcGetContextFileObject(
                          *(PFLT_INSTANCE *)(a2 + 24),
                          *(PFILE_OBJECT *)(*(_QWORD *)(a1 + 16) + 40LL),
                          &Context,
                          (PFLT_CONTEXT *)&v20);
    v4 = v20;
    if ( ContextFileObject )
    {
      if ( v20 )
      {
        if ( *((_QWORD *)v20 + 32) )
        {
          FileNameInformationUnsafe = RtlDowncaseUnicodeString(&FinalComponent, &FinalComponent, 0);
          if ( FileNameInformationUnsafe >= 0 )
          {
            FileNameInformationUnsafe = RtlHashUnicodeString(&FinalComponent, 1u, 0, &HashValue);
            if ( FileNameInformationUnsafe >= 0 )
            {
              if ( a3 )
              {
                FileNameInformationUnsafe = FltGetFileNameInformationUnsafe(
                                              *(PFILE_OBJECT *)(*(_QWORD *)(a1 + 16) + 40LL),
                                              *(PFLT_INSTANCE *)(a2 + 24),
                                              0x301u,
                                              &FileNameInformation);
                if ( FileNameInformationUnsafe < 0 )
                  goto LABEL_21;
                DestinationString.MaximumLength = FileNameInformation->Name.MaximumLength + 522;
                FileNameInformationUnsafe = WcAllocateUnicodeString(0x6E664357u, (__int64)&DestinationString);
                if ( FileNameInformationUnsafe < 0 )
                  goto LABEL_21;
                RtlAppendUnicodeStringToString(&DestinationString, &FileNameInformation->Name);
                RtlAppendUnicodeToString(&DestinationString, L"\\");
              }
              KeWaitForSingleObject(v4 + 232, Executive, 0, 0, 0);
              v11 = RtlLookupEntryHashTable(*((PRTL_DYNAMIC_HASH_TABLE *)v4 + 32), HashValue, 0);
              v12 = v11;
              if ( v11 )
              {
                RtlRemoveEntryHashTable(*((PRTL_DYNAMIC_HASH_TABLE *)v4 + 32), v11, 0);
                if ( a3 )
                {
                  RtlAppendUnicodeStringToString(&DestinationString, (PCUNICODE_STRING)&v12[1].Linkage.Blink);
                  FileNameInformationUnsafe = WcCreateTombstone(
                                                *(PFLT_INSTANCE *)(a2 + 24),
                                                &DestinationString,
                                                (char)v12[1].Linkage.Flink);
                  if ( FileNameInformationUnsafe < 0 )
                  {
                    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                    {
                      v16 = FileNameInformationUnsafe;
                      LOBYTE(v13) = 2;
                      WPP_RECORDER_SF_sDd(
                        wil_details_featureDescriptors_a->DeviceExtension,
                        v13,
                        5,
                        28,
                        (__int64)WPP_6c993b8198b53d328fc429e03cc469de_Traceguids,
                        (__int64)"onecore\\base\\fs\\wci\\wcifs\\tombstone.c",
                        31,
                        v16);
                    }
                    if ( (unsigned int)dword_14000E060 > 5 && tlgKeywordOn((__int64)&dword_14000E060, 0x400000000000LL) )
                    {
                      v18 = 7;
                      v17 = 1;
                      v27 = &v17;
                      v28 = 1;
                      v29 = &v18;
                      v30 = 1;
                      v31 = &v20;
                      LODWORD(v20) = FileNameInformationUnsafe;
                      v32 = 4;
                      tlgWriteTransfer_EtwWriteTransfer(v14, (unsigned __int8 *)byte_14000BC63, 0, 0, 5u, &v26);
                    }
                  }
                }
                ExFreePoolWithTag(v12, 0x74684357u);
              }
              KeSetEvent((PRKEVENT)(v4 + 232), 0, 0);
            }
          }
        }
      }
    }
  }
LABEL_21:
  if ( DestinationString.Buffer )
    ExFreePoolWithTag(DestinationString.Buffer, 0x6E664357u);
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( Context )
    FltReleaseContext(Context);
  if ( v4 )
    FltReleaseContext(v4);
  return (unsigned int)FileNameInformationUnsafe;
}

```

## disassembly

```asm
0x140032550  mov     [rsp-8+arg_10], rbx
0x140032555  mov     [rsp-8+arg_18], rsi
0x14003255a  push    rbp
0x14003255b  push    rdi
0x14003255c  push    r12
0x14003255e  push    r14
0x140032560  push    r15
0x140032562  lea     rbp, [rsp-37h]
0x140032567  sub     rsp, 0F0h
0x14003256e  mov     rax, cs:__security_cookie
0x140032575  xor     rax, rsp
0x140032578  mov     [rbp+57h+var_30], rax
0x14003257c  mov     rax, [rcx+10h]
0x140032580  xor     edi, edi
0x140032582  xorps   xmm0, xmm0
0x140032585  mov     [rbp+57h+var_C8], rdi
0x140032589  mov     r14, rdx
0x14003258c  mov     [rbp+57h+Context], rdi
0x140032590  mov     rsi, rcx
0x140032593  xorps   xmm1, xmm1
0x140032596  mov     rbx, [rax+38h]
0x14003259a  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14003259e  xor     edx, edx; SourceString
0x1400325a0  mov     [rbp+57h+HashValue], edi
0x1400325a3  movups  xmmword ptr [rbp+57h+FinalComponent.Length], xmm0
0x1400325a7  mov     [rbp+57h+FileNameInformation], rdi
0x1400325ab  mov     r12b, r8b
0x1400325ae  movups  xmmword ptr [rbp+57h+FileName.Length], xmm1
0x1400325b2  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400325b6  call    cs:__imp_RtlInitUnicodeString
0x1400325bd  nop     dword ptr [rax+rax+00h]
0x1400325c2  movzx   eax, word ptr [rbx+10h]
0x1400325c6  lea     r9, [rbp+57h+FinalComponent]; FinalComponent
0x1400325ca  mov     [rbp+57h+FileName.MaximumLength], ax
0x1400325ce  lea     rcx, [rbp+57h+FileName]; FileName
0x1400325d2  movzx   eax, word ptr [rbx+10h]
0x1400325d6  xor     r8d, r8d; Stream
0x1400325d9  mov     [rbp+57h+FileName.Length], ax
0x1400325dd  xor     edx, edx; Extension
0x1400325df  lea     rax, [rbx+14h]
0x1400325e3  mov     [rbp+57h+FileName.Buffer], rax
0x1400325e7  call    cs:__imp_FltParseFileName
0x1400325ee  nop     dword ptr [rax+rax+00h]
0x1400325f3  mov     ebx, eax
0x1400325f5  test    eax, eax
0x1400325f7  js      loc_14003289E
0x1400325fd  mov     rdx, [rsi+10h]
0x140032601  lea     r9, [rbp+57h+var_C8]
0x140032605  mov     rcx, [r14+18h]; Instance
0x140032609  lea     r8, [rbp+57h+Context]
0x14003260d  mov     rdx, [rdx+28h]; FileObject
0x140032611  call    WcGetContextFileObject
0x140032616  mov     rdi, [rbp+57h+var_C8]
0x14003261a  test    al, al
0x14003261c  jz      loc_14003289E
0x140032622  test    rdi, rdi
0x140032625  jz      loc_14003289E
0x14003262b  cmp     qword ptr [rdi+100h], 0
0x140032633  jz      loc_14003289E
0x140032639  xor     r8d, r8d; AllocateDestinationString
0x14003263c  lea     rdx, [rbp+57h+FinalComponent]; SourceString
0x140032640  lea     rcx, [rbp+57h+FinalComponent]; DestinationString
0x140032644  call    cs:__imp_RtlDowncaseUnicodeString
0x14003264b  nop     dword ptr [rax+rax+00h]
0x140032650  mov     ebx, eax
0x140032652  test    eax, eax
0x140032654  js      loc_14003289E
0x14003265a  lea     r9, [rbp+57h+HashValue]; HashValue
0x14003265e  xor     r8d, r8d; HashAlgorithm
0x140032661  mov     dl, 1; CaseInSensitive
0x140032663  lea     rcx, [rbp+57h+FinalComponent]; String
0x140032667  call    cs:__imp_RtlHashUnicodeString
0x14003266e  nop     dword ptr [rax+rax+00h]
0x140032673  mov     ebx, eax
0x140032675  test    eax, eax
0x140032677  js      loc_14003289E
0x14003267d  test    r12b, r12b
0x140032680  jz      loc_14003270A
0x140032686  mov     rcx, [rsi+10h]
0x14003268a  lea     r9, [rbp+57h+FileNameInformation]; FileNameInformation
0x14003268e  mov     rdx, [r14+18h]; Instance
0x140032692  mov     r8d, 301h; NameOptions
0x140032698  mov     rcx, [rcx+28h]; FileObject
0x14003269c  call    cs:__imp_FltGetFileNameInformationUnsafe
0x1400326a3  nop     dword ptr [rax+rax+00h]
0x1400326a8  mov     ebx, eax
0x1400326aa  test    eax, eax
0x1400326ac  js      loc_14003289E
0x1400326b2  mov     rax, [rbp+57h+FileNameInformation]
0x1400326b6  lea     rdx, [rbp+57h+DestinationString]
0x1400326ba  mov     ecx, 20Ah
0x1400326bf  add     cx, [rax+0Ah]
0x1400326c3  mov     [rbp+57h+DestinationString.MaximumLength], cx
0x1400326c7  mov     ecx, 6E664357h
0x1400326cc  call    WcAllocateUnicodeString
0x1400326d1  mov     ebx, eax
0x1400326d3  test    eax, eax
0x1400326d5  js      loc_14003289E
0x1400326db  mov     rdx, [rbp+57h+FileNameInformation]
0x1400326df  lea     rcx, [rbp+57h+DestinationString]; Destination
0x1400326e3  add     rdx, 8; Source
0x1400326e7  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400326ee  nop     dword ptr [rax+rax+00h]
0x1400326f3  lea     rdx, Source2; "\\"
0x1400326fa  lea     rcx, [rbp+57h+DestinationString]; Destination
0x1400326fe  call    cs:__imp_RtlAppendUnicodeToString
0x140032705  nop     dword ptr [rax+rax+00h]
0x14003270a  lea     r15, [rdi+0E8h]
0x140032711  mov     [rsp+110h+Timeout], 0; Timeout
0x14003271a  mov     rcx, r15; Object
0x14003271d  xor     r9d, r9d; Alertable
0x140032720  xor     r8d, r8d; WaitMode
0x140032723  xor     edx, edx; WaitReason
0x140032725  call    cs:__imp_KeWaitForSingleObject
0x14003272c  nop     dword ptr [rax+rax+00h]
0x140032731  mov     edx, [rbp+57h+HashValue]; Signature
0x140032734  xor     r8d, r8d; Context
0x140032737  mov     rcx, [rdi+100h]; HashTable
0x14003273e  call    cs:__imp_RtlLookupEntryHashTable
0x140032745  nop     dword ptr [rax+rax+00h]
0x14003274a  mov     rsi, rax
0x14003274d  test    rax, rax
0x140032750  jz      loc_14003288A
0x140032756  mov     rcx, [rdi+100h]; HashTable
0x14003275d  xor     r8d, r8d; Context
0x140032760  mov     rdx, rax; Entry
0x140032763  call    cs:__imp_RtlRemoveEntryHashTable
0x14003276a  nop     dword ptr [rax+rax+00h]
0x14003276f  test    r12b, r12b
0x140032772  jz      loc_140032876
0x140032778  lea     rdx, [rsi+20h]; Source
0x14003277c  lea     rcx, [rbp+57h+DestinationString]; Destination
0x140032780  call    cs:__imp_RtlAppendUnicodeStringToString
0x140032787  nop     dword ptr [rax+rax+00h]
0x14003278c  mov     r8b, [rsi+18h]
0x140032790  lea     rdx, [rbp+57h+DestinationString]
0x140032794  mov     rcx, [r14+18h]; Instance
0x140032798  call    WcCreateTombstone
0x14003279d  mov     ebx, eax
0x14003279f  test    eax, eax
0x1400327a1  jns     loc_140032876
0x1400327a7  lea     rax, WPP_RECORDER_INITIALIZED
0x1400327ae  mov     r14d, 5
0x1400327b4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400327bb  jz      short loc_1400327FA
0x1400327bd  mov     rcx, cs:wil_details_featureDescriptors_a
0x1400327c4  lea     rax, aOnecoreBaseFsW_10; "onecore\\base\\fs\\wci\\wcifs\\tombston"...
0x1400327cb  mov     [rsp+110h+var_D8], ebx
0x1400327cf  lea     r9d, [r14+17h]
0x1400327d3  mov     [rsp+110h+var_E0], 51Fh
0x1400327db  mov     r8d, r14d
0x1400327de  mov     [rsp+110h+var_E8], rax
0x1400327e3  mov     dl, 2
0x1400327e5  mov     rcx, [rcx+40h]
0x1400327e9  lea     rax, WPP_6c993b8198b53d328fc429e03cc469de_Traceguids
0x1400327f0  mov     [rsp+110h+Timeout], rax
0x1400327f5  call    WPP_RECORDER_SF_sDd
0x1400327fa  mov     eax, cs:dword_14000E060
0x140032800  cmp     eax, r14d
0x140032803  jbe     short loc_140032876
0x140032805  mov     rdx, 400000000000h
0x14003280f  lea     rcx, dword_14000E060
0x140032816  call    _tlgKeywordOn
0x14003281b  test    al, al
0x14003281d  jz      short loc_140032876
0x14003281f  mov     edx, 1
0x140032824  mov     [rbp+57h+var_CF], 7
0x140032828  lea     rax, [rbp+57h+var_D0]
0x14003282c  mov     [rbp+57h+var_D0], dl
0x14003282f  mov     [rbp+57h+var_60], rax
0x140032833  xor     r9d, r9d
0x140032836  lea     rax, [rbp+57h+var_CF]
0x14003283a  mov     [rbp+57h+var_58], rdx
0x14003283e  mov     [rbp+57h+var_50], rax
0x140032842  xor     r8d, r8d
0x140032845  lea     rax, [rbp+57h+var_C8]
0x140032849  mov     [rbp+57h+var_48], rdx
0x14003284d  mov     [rbp+57h+var_40], rax
0x140032851  lea     rdx, byte_14000BC63
0x140032858  lea     rax, [rbp+57h+var_80]
0x14003285c  mov     dword ptr [rbp+57h+var_C8], ebx
0x14003285f  mov     [rsp+110h+var_E8], rax
0x140032864  mov     dword ptr [rsp+110h+Timeout], r14d
0x140032869  mov     [rbp+57h+var_38], 4
0x140032871  call    _tlgWriteTransfer_EtwWriteTransfer
0x140032876  mov     edx, 74684357h; Tag
0x14003287b  mov     rcx, rsi; P
0x14003287e  call    cs:__imp_ExFreePoolWithTag
0x140032885  nop     dword ptr [rax+rax+00h]
0x14003288a  xor     r8d, r8d; Wait
0x14003288d  xor     edx, edx; Increment
0x14003288f  mov     rcx, r15; Event
0x140032892  call    cs:__imp_KeSetEvent
0x140032899  nop     dword ptr [rax+rax+00h]
0x14003289e  mov     rcx, [rbp+57h+DestinationString.Buffer]; P
0x1400328a2  test    rcx, rcx
0x1400328a5  jz      short loc_1400328B8
0x1400328a7  mov     edx, 6E664357h; Tag
0x1400328ac  call    cs:__imp_ExFreePoolWithTag
0x1400328b3  nop     dword ptr [rax+rax+00h]
0x1400328b8  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x1400328bc  test    rcx, rcx
0x1400328bf  jz      short loc_1400328CD
0x1400328c1  call    cs:__imp_FltReleaseFileNameInformation
0x1400328c8  nop     dword ptr [rax+rax+00h]
0x1400328cd  mov     rcx, [rbp+57h+Context]; Context
0x1400328d1  test    rcx, rcx
0x1400328d4  jz      short loc_1400328E2
0x1400328d6  call    cs:__imp_FltReleaseContext
0x1400328dd  nop     dword ptr [rax+rax+00h]
0x1400328e2  test    rdi, rdi
0x1400328e5  jz      short loc_1400328F6
0x1400328e7  mov     rcx, rdi; Context
0x1400328ea  call    cs:__imp_FltReleaseContext
0x1400328f1  nop     dword ptr [rax+rax+00h]
0x1400328f6  mov     eax, ebx
0x1400328f8  mov     rcx, [rbp+57h+var_30]
0x1400328fc  xor     rcx, rsp; StackCookie
0x1400328ff  call    __security_check_cookie
0x140032904  lea     r11, [rsp+110h+var_20]
0x14003290c  mov     rbx, [r11+40h]
0x140032910  mov     rsi, [r11+48h]
0x140032914  mov     rsp, r11
0x140032917  pop     r15
0x140032919  pop     r14
0x14003291b  pop     r12
0x14003291d  pop     rdi
0x14003291e  pop     rbp
0x14003291f  retn
```
