# WcRemoveInMemoryTombstoneAfterRenameLink

- ea: `0x140032500`
- end: `0x1400328d1`
- name: `WcRemoveInMemoryTombstoneAfterRenameLink`
- size: `977`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400318f0`

## callees

- `0x140001008`
- `0x140001030`
- `0x140001500`
- `0x1400020c4`
- `0x140007c60`
- `0x14001bf24`
- `0x14002ee10`
- `0x140032500`

## import_xrefs

- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140032713`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140032713`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x1400326ee`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x1400326ee`
- `ntoskrnl!RtlDowncaseUnicodeString` at `0x1400325f4`
- `ntoskrnl!RtlDowncaseUnicodeString` at `0x1400325f4`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400326ae`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400326ae`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400326d5`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400326d5`
- `ntoskrnl!KeSetEvent` at `0x140032842`
- `ntoskrnl!KeSetEvent` at `0x140032842`
- `ntoskrnl!RtlInitUnicodeString` at `0x140032566`
- `ntoskrnl!RtlInitUnicodeString` at `0x140032566`
- `ntoskrnl!RtlHashUnicodeString` at `0x140032617`
- `ntoskrnl!RtlHashUnicodeString` at `0x140032617`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140032697`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140032730`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140032697`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140032730`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003282e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003285c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003282e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003285c`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14003264c`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14003264c`
- `FLTMGR!FltParseFileName` at `0x140032597`
- `FLTMGR!FltParseFileName` at `0x140032597`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140032871`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140032871`
- `FLTMGR!FltReleaseContext` at `0x140032886`
- `FLTMGR!FltReleaseContext` at `0x14003289a`
- `FLTMGR!FltReleaseContext` at `0x140032886`
- `FLTMGR!FltReleaseContext` at `0x14003289a`

## pseudocode

```c
__int64 __fastcall WcRemoveInMemoryTombstoneAfterRenameLink(__int64 a1, __int64 a2)
{
  __int64 v2; // rax
  __int64 v5; // rbx
  NTSTATUS v6; // ebx
  ULONG HashValue; // [rsp+44h] [rbp-75h]
  __int64 v9; // [rsp+48h] [rbp-71h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+50h] [rbp-69h]
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-61h] BYREF
  PFLT_CONTEXT Context; // [rsp+68h] [rbp-51h]
  UNICODE_STRING FileName; // [rsp+70h] [rbp-49h] BYREF
  struct _UNICODE_STRING FinalComponent; // [rsp+80h] [rbp-39h] BYREF

  v2 = *(_QWORD *)(a1 + 16);
  v9 = 0;
  Context = 0;
  v5 = *(_QWORD *)(v2 + 56);
  HashValue = 0;
  FinalComponent = 0;
  FileNameInformation = 0;
  FileName = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  FileName.MaximumLength = *(_WORD *)(v5 + 16);
  FileName.Length = *(_WORD *)(v5 + 16);
  FileName.Buffer = (PWSTR)(v5 + 20);
  v6 = FltParseFileName(&FileName, 0, 0, &FinalComponent);
  if ( v6 >= 0 )
    WcGetContextFileObject(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(*(_QWORD *)(a1 + 16) + 40LL));
  if ( DestinationString.Buffer )
    ExFreePoolWithTag(DestinationString.Buffer, 0x6E664357u);
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( Context )
    FltReleaseContext(Context);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140032500  mov     [rsp-8+arg_10], rbx
0x140032505  mov     [rsp-8+arg_18], rsi
0x14003250a  push    rbp
0x14003250b  push    rdi
0x14003250c  push    r12
0x14003250e  push    r14
0x140032510  push    r15
0x140032512  lea     rbp, [rsp-37h]
0x140032517  sub     rsp, 0F0h
0x14003251e  mov     rax, cs:__security_cookie
0x140032525  xor     rax, rsp
0x140032528  mov     [rbp+57h+var_30], rax
0x14003252c  mov     rax, [rcx+10h]
0x140032530  xor     edi, edi
0x140032532  xorps   xmm0, xmm0
0x140032535  mov     [rbp+57h+var_C8], rdi
0x140032539  mov     r14, rdx
0x14003253c  mov     [rbp+57h+Context], rdi
0x140032540  mov     rsi, rcx
0x140032543  xorps   xmm1, xmm1
0x140032546  mov     rbx, [rax+38h]
0x14003254a  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14003254e  xor     edx, edx; SourceString
0x140032550  mov     [rbp+57h+HashValue], edi
0x140032553  movups  xmmword ptr [rbp+57h+FinalComponent.Length], xmm0
0x140032557  mov     [rbp+57h+FileNameInformation], rdi
0x14003255b  mov     r12b, r8b
0x14003255e  movups  xmmword ptr [rbp+57h+FileName.Length], xmm1
0x140032562  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140032566  call    cs:__imp_RtlInitUnicodeString
0x14003256d  nop     dword ptr [rax+rax+00h]
0x140032572  movzx   eax, word ptr [rbx+10h]
0x140032576  lea     r9, [rbp+57h+FinalComponent]; FinalComponent
0x14003257a  mov     [rbp+57h+FileName.MaximumLength], ax
0x14003257e  lea     rcx, [rbp+57h+FileName]; FileName
0x140032582  movzx   eax, word ptr [rbx+10h]
0x140032586  xor     r8d, r8d; Stream
0x140032589  mov     [rbp+57h+FileName.Length], ax
0x14003258d  xor     edx, edx; Extension
0x14003258f  lea     rax, [rbx+14h]
0x140032593  mov     [rbp+57h+FileName.Buffer], rax
0x140032597  call    cs:__imp_FltParseFileName
0x14003259e  nop     dword ptr [rax+rax+00h]
0x1400325a3  mov     ebx, eax
0x1400325a5  test    eax, eax
0x1400325a7  js      loc_14003284E
0x1400325ad  mov     rdx, [rsi+10h]
0x1400325b1  lea     r9, [rbp+57h+var_C8]
0x1400325b5  mov     rcx, [r14+18h]; Instance
0x1400325b9  lea     r8, [rbp+57h+Context]
0x1400325bd  mov     rdx, [rdx+28h]; FileObject
0x1400325c1  call    WcGetContextFileObject
0x1400325c6  mov     rdi, [rbp+57h+var_C8]
0x1400325ca  test    al, al
0x1400325cc  jz      loc_14003284E
0x1400325d2  test    rdi, rdi
0x1400325d5  jz      loc_14003284E
0x1400325db  cmp     qword ptr [rdi+100h], 0
0x1400325e3  jz      loc_14003284E
0x1400325e9  xor     r8d, r8d; AllocateDestinationString
0x1400325ec  lea     rdx, [rbp+57h+FinalComponent]; SourceString
0x1400325f0  lea     rcx, [rbp+57h+FinalComponent]; DestinationString
0x1400325f4  call    cs:__imp_RtlDowncaseUnicodeString
0x1400325fb  nop     dword ptr [rax+rax+00h]
0x140032600  mov     ebx, eax
0x140032602  test    eax, eax
0x140032604  js      loc_14003284E
0x14003260a  lea     r9, [rbp+57h+HashValue]; HashValue
0x14003260e  xor     r8d, r8d; HashAlgorithm
0x140032611  mov     dl, 1; CaseInSensitive
0x140032613  lea     rcx, [rbp+57h+FinalComponent]; String
0x140032617  call    cs:__imp_RtlHashUnicodeString
0x14003261e  nop     dword ptr [rax+rax+00h]
0x140032623  mov     ebx, eax
0x140032625  test    eax, eax
0x140032627  js      loc_14003284E
0x14003262d  test    r12b, r12b
0x140032630  jz      loc_1400326BA
0x140032636  mov     rcx, [rsi+10h]
0x14003263a  lea     r9, [rbp+57h+FileNameInformation]; FileNameInformation
0x14003263e  mov     rdx, [r14+18h]; Instance
0x140032642  mov     r8d, 301h; NameOptions
0x140032648  mov     rcx, [rcx+28h]; FileObject
0x14003264c  call    cs:__imp_FltGetFileNameInformationUnsafe
0x140032653  nop     dword ptr [rax+rax+00h]
0x140032658  mov     ebx, eax
0x14003265a  test    eax, eax
0x14003265c  js      loc_14003284E
0x140032662  mov     rax, [rbp+57h+FileNameInformation]
0x140032666  lea     rdx, [rbp+57h+DestinationString]
0x14003266a  mov     ecx, 20Ah
0x14003266f  add     cx, [rax+0Ah]
0x140032673  mov     [rbp+57h+DestinationString.MaximumLength], cx
0x140032677  mov     ecx, 6E664357h
0x14003267c  call    WcAllocateUnicodeString
0x140032681  mov     ebx, eax
0x140032683  test    eax, eax
0x140032685  js      loc_14003284E
0x14003268b  mov     rdx, [rbp+57h+FileNameInformation]
0x14003268f  lea     rcx, [rbp+57h+DestinationString]; Destination
0x140032693  add     rdx, 8; Source
0x140032697  call    cs:__imp_RtlAppendUnicodeStringToString
0x14003269e  nop     dword ptr [rax+rax+00h]
0x1400326a3  lea     rdx, Source2; "\\"
0x1400326aa  lea     rcx, [rbp+57h+DestinationString]; Destination
0x1400326ae  call    cs:__imp_RtlAppendUnicodeToString
0x1400326b5  nop     dword ptr [rax+rax+00h]
0x1400326ba  lea     r15, [rdi+0E8h]
0x1400326c1  mov     [rsp+110h+Timeout], 0; Timeout
0x1400326ca  mov     rcx, r15; Object
0x1400326cd  xor     r9d, r9d; Alertable
0x1400326d0  xor     r8d, r8d; WaitMode
0x1400326d3  xor     edx, edx; WaitReason
0x1400326d5  call    cs:__imp_KeWaitForSingleObject
0x1400326dc  nop     dword ptr [rax+rax+00h]
0x1400326e1  mov     edx, [rbp+57h+HashValue]; Signature
0x1400326e4  xor     r8d, r8d; Context
0x1400326e7  mov     rcx, [rdi+100h]; HashTable
0x1400326ee  call    cs:__imp_RtlLookupEntryHashTable
0x1400326f5  nop     dword ptr [rax+rax+00h]
0x1400326fa  mov     rsi, rax
0x1400326fd  test    rax, rax
0x140032700  jz      loc_14003283A
0x140032706  mov     rcx, [rdi+100h]; HashTable
0x14003270d  xor     r8d, r8d; Context
0x140032710  mov     rdx, rax; Entry
0x140032713  call    cs:__imp_RtlRemoveEntryHashTable
0x14003271a  nop     dword ptr [rax+rax+00h]
0x14003271f  test    r12b, r12b
0x140032722  jz      loc_140032826
0x140032728  lea     rdx, [rsi+20h]; Source
0x14003272c  lea     rcx, [rbp+57h+DestinationString]; Destination
0x140032730  call    cs:__imp_RtlAppendUnicodeStringToString
0x140032737  nop     dword ptr [rax+rax+00h]
0x14003273c  mov     r8b, [rsi+18h]
0x140032740  lea     rdx, [rbp+57h+DestinationString]
0x140032744  mov     rcx, [r14+18h]; Instance
0x140032748  call    WcCreateTombstone
0x14003274d  mov     ebx, eax
0x14003274f  test    eax, eax
0x140032751  jns     loc_140032826
0x140032757  lea     rax, WPP_RECORDER_INITIALIZED
0x14003275e  mov     r14d, 5
0x140032764  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003276b  jz      short loc_1400327AA
0x14003276d  mov     rcx, cs:WPP_GLOBAL_Control
0x140032774  lea     rax, aOnecoreBaseFsW_10; "onecore\\base\\fs\\wci\\wcifs\\tombston"...
0x14003277b  mov     [rsp+110h+var_D8], ebx
0x14003277f  lea     r9d, [r14+17h]
0x140032783  mov     [rsp+110h+var_E0], 51Fh
0x14003278b  mov     r8d, r14d
0x14003278e  mov     [rsp+110h+var_E8], rax
0x140032793  mov     dl, 2
0x140032795  mov     rcx, [rcx+40h]
0x140032799  lea     rax, WPP_6c993b8198b53d328fc429e03cc469de_Traceguids
0x1400327a0  mov     [rsp+110h+Timeout], rax
0x1400327a5  call    WPP_RECORDER_SF_sDd
0x1400327aa  mov     eax, cs:dword_14000E060
0x1400327b0  cmp     eax, r14d
0x1400327b3  jbe     short loc_140032826
0x1400327b5  mov     rdx, 400000000000h
0x1400327bf  lea     rcx, dword_14000E060
0x1400327c6  call    _tlgKeywordOn
0x1400327cb  test    al, al
0x1400327cd  jz      short loc_140032826
0x1400327cf  mov     edx, 1
0x1400327d4  mov     [rbp+57h+var_CF], 7
0x1400327d8  lea     rax, [rbp+57h+var_D0]
0x1400327dc  mov     [rbp+57h+var_D0], dl
0x1400327df  mov     [rbp+57h+var_60], rax
0x1400327e3  xor     r9d, r9d
0x1400327e6  lea     rax, [rbp+57h+var_CF]
0x1400327ea  mov     [rbp+57h+var_58], rdx
0x1400327ee  mov     [rbp+57h+var_50], rax
0x1400327f2  xor     r8d, r8d
0x1400327f5  lea     rax, [rbp+57h+var_C8]
0x1400327f9  mov     [rbp+57h+var_48], rdx
0x1400327fd  mov     [rbp+57h+var_40], rax
0x140032801  lea     rdx, byte_14000BC63
0x140032808  lea     rax, [rbp+57h+var_80]
0x14003280c  mov     dword ptr [rbp+57h+var_C8], ebx
0x14003280f  mov     [rsp+110h+var_E8], rax
0x140032814  mov     dword ptr [rsp+110h+Timeout], r14d
0x140032819  mov     [rbp+57h+var_38], 4
0x140032821  call    _tlgWriteTransfer_EtwWriteTransfer
0x140032826  mov     edx, 74684357h; Tag
0x14003282b  mov     rcx, rsi; P
0x14003282e  call    cs:__imp_ExFreePoolWithTag
0x140032835  nop     dword ptr [rax+rax+00h]
0x14003283a  xor     r8d, r8d; Wait
0x14003283d  xor     edx, edx; Increment
0x14003283f  mov     rcx, r15; Event
0x140032842  call    cs:__imp_KeSetEvent
0x140032849  nop     dword ptr [rax+rax+00h]
0x14003284e  mov     rcx, [rbp+57h+DestinationString.Buffer]; P
0x140032852  test    rcx, rcx
0x140032855  jz      short loc_140032868
0x140032857  mov     edx, 6E664357h; Tag
0x14003285c  call    cs:__imp_ExFreePoolWithTag
0x140032863  nop     dword ptr [rax+rax+00h]
0x140032868  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x14003286c  test    rcx, rcx
0x14003286f  jz      short loc_14003287D
0x140032871  call    cs:__imp_FltReleaseFileNameInformation
0x140032878  nop     dword ptr [rax+rax+00h]
0x14003287d  mov     rcx, [rbp+57h+Context]; Context
0x140032881  test    rcx, rcx
0x140032884  jz      short loc_140032892
0x140032886  call    cs:__imp_FltReleaseContext
0x14003288d  nop     dword ptr [rax+rax+00h]
0x140032892  test    rdi, rdi
0x140032895  jz      short loc_1400328A6
0x140032897  mov     rcx, rdi; Context
0x14003289a  call    cs:__imp_FltReleaseContext
0x1400328a1  nop     dword ptr [rax+rax+00h]
0x1400328a6  mov     eax, ebx
0x1400328a8  mov     rcx, [rbp+57h+var_30]
0x1400328ac  xor     rcx, rsp; StackCookie
0x1400328af  call    __security_check_cookie
0x1400328b4  lea     r11, [rsp+110h+var_20]
0x1400328bc  mov     rbx, [r11+40h]
0x1400328c0  mov     rsi, [r11+48h]
0x1400328c4  mov     rsp, r11
0x1400328c7  pop     r15
0x1400328c9  pop     r14
0x1400328cb  pop     r12
0x1400328cd  pop     rdi
0x1400328ce  pop     rbp
0x1400328cf  retn
```
