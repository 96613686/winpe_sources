# WcRevertDelete

- ea: `0x140032928`
- end: `0x140032d74`
- name: `WcRevertDelete`
- size: `1100`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, __int64)`
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
- `0x140032928`

## import_xrefs

- `ntoskrnl!RtlInitEnumerationHashTable` at `0x140032b20`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x140032b20`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140032c78`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140032c78`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x140032ccf`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x140032ccf`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x140032b38`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x140032ca4`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x140032b38`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x140032ca4`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140032ac8`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140032ac8`
- `ntoskrnl!KeWaitForSingleObject` at `0x140032af5`
- `ntoskrnl!KeWaitForSingleObject` at `0x140032af5`
- `ntoskrnl!KeSetEvent` at `0x140032ce3`
- `ntoskrnl!KeSetEvent` at `0x140032ce3`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140032ab0`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140032b78`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140032ab0`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140032b78`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032c8c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032cfe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032c8c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032cfe`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140032d14`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140032d14`
- `FLTMGR!FltGetFileNameInformation` at `0x140032a60`
- `FLTMGR!FltGetFileNameInformation` at `0x140032a60`
- `FLTMGR!FltQueryInformationFile` at `0x1400329aa`
- `FLTMGR!FltQueryInformationFile` at `0x1400329aa`
- `FLTMGR!FltReleaseContext` at `0x140032d2a`
- `FLTMGR!FltReleaseContext` at `0x140032d3e`
- `FLTMGR!FltReleaseContext` at `0x140032d2a`
- `FLTMGR!FltReleaseContext` at `0x140032d3e`

## pseudocode

```c
__int64 __fastcall WcRevertDelete(PFLT_CALLBACK_DATA CallbackData, __int64 a2)
{
  struct _FILE_OBJECT *v3; // rdx
  struct _FLT_INSTANCE *v5; // rcx
  PRTL_DYNAMIC_HASH_TABLE *v6; // rbx
  NTSTATUS v7; // eax
  int v8; // edx
  int UnicodeString; // edi
  char ContextFileObject; // al
  struct _KEVENT *v11; // rsi
  struct _RTL_DYNAMIC_HASH_TABLE *v12; // rcx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v13; // r14
  int v14; // eax
  int v15; // edx
  __int64 v17; // [rsp+38h] [rbp-C8h]
  char v18; // [rsp+40h] [rbp-C0h] BYREF
  char v19; // [rsp+41h] [rbp-BFh] BYREF
  USHORT Length; // [rsp+42h] [rbp-BEh]
  PRTL_DYNAMIC_HASH_TABLE *v21; // [rsp+48h] [rbp-B8h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+58h] [rbp-A8h] BYREF
  PFLT_CONTEXT Context; // [rsp+68h] [rbp-98h] BYREF
  struct _RTL_DYNAMIC_HASH_TABLE_ENUMERATOR Enumerator; // [rsp+70h] [rbp-90h] BYREF
  __int128 FileInformation; // [rsp+98h] [rbp-68h] BYREF
  __int64 v27; // [rsp+A8h] [rbp-58h]
  struct _EVENT_DATA_DESCRIPTOR v28; // [rsp+B0h] [rbp-50h] BYREF
  char *v29; // [rsp+D0h] [rbp-30h]
  __int64 v30; // [rsp+D8h] [rbp-28h]
  char *v31; // [rsp+E0h] [rbp-20h]
  __int64 v32; // [rsp+E8h] [rbp-18h]
  PRTL_DYNAMIC_HASH_TABLE **v33; // [rsp+F0h] [rbp-10h]
  __int64 v34; // [rsp+F8h] [rbp-8h]

  Context = 0;
  v3 = *(struct _FILE_OBJECT **)(a2 + 32);
  FileNameInformation = 0;
  v5 = *(struct _FLT_INSTANCE **)(a2 + 24);
  v6 = 0;
  v21 = 0;
  memset(&Enumerator, 0, sizeof(Enumerator));
  v27 = 0;
  FileInformation = 0;
  Destination = 0;
  v7 = FltQueryInformationFile(v5, v3, &FileInformation, 0x18u, FileStandardInformation, 0);
  UnicodeString = v7;
  if ( v7 >= 0 )
  {
    if ( !BYTE6(v27) )
    {
      ContextFileObject = WcGetContextFileObject(
                            *(PFLT_INSTANCE *)(a2 + 24),
                            *(PFILE_OBJECT *)(a2 + 32),
                            &Context,
                            (PFLT_CONTEXT *)&v21);
      v6 = v21;
      if ( ContextFileObject )
      {
        if ( v21 )
        {
          if ( *((_BYTE *)v21 + 28) )
          {
            UnicodeString = FltGetFileNameInformation(CallbackData, 0x301u, &FileNameInformation);
            if ( UnicodeString >= 0 )
            {
              Destination.MaximumLength = FileNameInformation->Name.MaximumLength + 522;
              UnicodeString = WcAllocateUnicodeString(0x6E664357u, (__int64)&Destination);
              if ( UnicodeString >= 0 )
              {
                RtlAppendUnicodeStringToString(&Destination, &FileNameInformation->Name);
                RtlAppendUnicodeToString(&Destination, L"\\");
                v11 = (struct _KEVENT *)(v6 + 29);
                Length = Destination.Length;
                KeWaitForSingleObject(v6 + 29, Executive, 0, 0, 0);
                v12 = v6[32];
                if ( v12 && v12->NumEntries )
                {
                  RtlInitEnumerationHashTable(v12, &Enumerator);
                  v13 = RtlEnumerateEntryHashTable(v6[32], &Enumerator);
                  if ( v13 )
                  {
                    do
                    {
                      Destination.Length = Length;
                      RtlAppendUnicodeStringToString(&Destination, (PCUNICODE_STRING)&v13[1].Linkage.Blink);
                      v14 = WcCreateTombstone(*(PFLT_INSTANCE *)(a2 + 24), &Destination, (char)v13[1].Linkage.Flink);
                      UnicodeString = v14;
                      if ( v14 < 0 )
                      {
                        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                        {
                          LODWORD(v17) = v14;
                          LOBYTE(v15) = 2;
                          WPP_RECORDER_SF_sDd(
                            wil_details_featureDescriptors_a->DeviceExtension,
                            v15,
                            5,
                            30,
                            (__int64)WPP_6c993b8198b53d328fc429e03cc469de_Traceguids,
                            (__int64)"onecore\\base\\fs\\wci\\wcifs\\tombstone.c",
                            197,
                            v17);
                        }
                        if ( (unsigned int)dword_14000E060 > 5
                          && tlgKeywordOn((__int64)&dword_14000E060, 0x400000000000LL) )
                        {
                          v19 = 6;
                          v18 = 1;
                          v29 = &v18;
                          v30 = 1;
                          v31 = &v19;
                          v32 = 1;
                          v33 = &v21;
                          LODWORD(v21) = UnicodeString;
                          v34 = 4;
                          tlgWriteTransfer_EtwWriteTransfer(
                            (__int64)&dword_14000E060,
                            (unsigned __int8 *)byte_14000BAEB,
                            0,
                            0,
                            5u,
                            &v28);
                        }
                      }
                      RtlRemoveEntryHashTable(v6[32], v13, 0);
                      ExFreePoolWithTag(v13, 0x74684357u);
                      v13 = RtlEnumerateEntryHashTable(v6[32], &Enumerator);
                    }
                    while ( v13 );
                    v11 = (struct _KEVENT *)(v6 + 29);
                  }
                  RtlEndEnumerationHashTable(v6[32], &Enumerator);
                }
                KeSetEvent(v11, 0, 0);
                if ( Destination.Buffer )
                  ExFreePoolWithTag(Destination.Buffer, 0x6E664357u);
              }
            }
          }
        }
      }
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v8) = 2;
    WPP_RECORDER_SF_sDd(
      wil_details_featureDescriptors_a->DeviceExtension,
      v8,
      5,
      29,
      (__int64)WPP_6c993b8198b53d328fc429e03cc469de_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\wcifs\\tombstone.c",
      126,
      v7);
  }
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( Context )
    FltReleaseContext(Context);
  if ( v6 )
    FltReleaseContext(v6);
  return (unsigned int)UnicodeString;
}

```

## disassembly

```asm
0x140032928  mov     [rsp-8+arg_10], rbx
0x14003292d  push    rbp
0x14003292e  push    rsi
0x14003292f  push    rdi
0x140032930  push    r12
0x140032932  push    r13
0x140032934  push    r14
0x140032936  push    r15
0x140032938  lea     rbp, [rsp-10h]
0x14003293d  sub     rsp, 110h
0x140032944  mov     rax, cs:__security_cookie
0x14003294b  xor     rax, rsp
0x14003294e  mov     [rbp+40h+var_40], rax
0x140032952  xor     r15d, r15d
0x140032955  lea     r8, [rbp+40h+FileInformation]; FileInformation
0x140032959  xorps   xmm0, xmm0
0x14003295c  mov     [rsp+140h+LengthReturned], r15; LengthReturned
0x140032961  mov     r13, rdx
0x140032964  mov     [rsp+140h+Context], r15
0x140032969  mov     rdx, [rdx+20h]; FileObject
0x14003296d  xor     eax, eax
0x14003296f  mov     rsi, rcx
0x140032972  mov     qword ptr [rbp+40h+Enumerator.BucketIndex], rax
0x140032976  lea     r14d, [r15+5]
0x14003297a  mov     [rsp+140h+FileNameInformation], r15
0x14003297f  mov     rcx, [r13+18h]; Instance
0x140032983  lea     r9d, [r15+18h]; Length
0x140032987  mov     ebx, r15d
0x14003298a  mov     [rsp+140h+FileInformationClass], r14d; FileInformationClass
0x14003298f  mov     [rsp+140h+var_F8], rbx
0x140032994  movups  xmmword ptr [rsp+140h+Enumerator], xmm0
0x140032999  mov     [rbp+40h+var_98], rax
0x14003299d  movups  xmmword ptr [rbp+40h+Enumerator+10h], xmm0
0x1400329a1  movups  [rbp+40h+FileInformation], xmm0
0x1400329a5  movups  xmmword ptr [rsp+140h+Destination.Length], xmm0
0x1400329aa  call    cs:__imp_FltQueryInformationFile
0x1400329b1  nop     dword ptr [rax+rax+00h]
0x1400329b6  mov     edi, eax
0x1400329b8  test    eax, eax
0x1400329ba  jns     short loc_140032A12
0x1400329bc  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400329c3  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400329ca  jz      loc_140032D0A
0x1400329d0  mov     rcx, cs:wil_details_featureDescriptors_a
0x1400329d7  lea     r9d, [r15+1Dh]
0x1400329db  mov     dword ptr [rsp+140h+var_108], eax
0x1400329df  lea     r15, aOnecoreBaseFsW_10; "onecore\\base\\fs\\wci\\wcifs\\tombston"...
0x1400329e6  mov     [rsp+140h+var_110], 57Eh
0x1400329ee  lea     r12, WPP_6c993b8198b53d328fc429e03cc469de_Traceguids
0x1400329f5  mov     [rsp+140h+LengthReturned], r15
0x1400329fa  mov     r8d, r14d
0x1400329fd  mov     rcx, [rcx+40h]
0x140032a01  mov     dl, 2
0x140032a03  mov     qword ptr [rsp+140h+FileInformationClass], r12
0x140032a08  call    WPP_RECORDER_SF_sDd
0x140032a0d  jmp     loc_140032D0A
0x140032a12  cmp     byte ptr [rbp+40h+var_98+6], r15b
0x140032a16  jnz     loc_140032D0A
0x140032a1c  mov     rdx, [r13+20h]; FileObject
0x140032a20  lea     r9, [rsp+140h+var_F8]
0x140032a25  mov     rcx, [r13+18h]; Instance
0x140032a29  lea     r8, [rsp+140h+Context]
0x140032a2e  call    WcGetContextFileObject
0x140032a33  mov     rbx, [rsp+140h+var_F8]
0x140032a38  test    al, al
0x140032a3a  jz      loc_140032D0A
0x140032a40  test    rbx, rbx
0x140032a43  jz      loc_140032D0A
0x140032a49  cmp     [rbx+1Ch], r15b
0x140032a4d  jz      loc_140032D0A
0x140032a53  lea     r8, [rsp+140h+FileNameInformation]; FileNameInformation
0x140032a58  mov     edx, 301h; NameOptions
0x140032a5d  mov     rcx, rsi; CallbackData
0x140032a60  call    cs:__imp_FltGetFileNameInformation
0x140032a67  nop     dword ptr [rax+rax+00h]
0x140032a6c  mov     edi, eax
0x140032a6e  test    eax, eax
0x140032a70  js      loc_140032D0A
0x140032a76  mov     rax, [rsp+140h+FileNameInformation]
0x140032a7b  lea     rdx, [rsp+140h+Destination]
0x140032a80  mov     ecx, 20Ah
0x140032a85  add     cx, [rax+0Ah]
0x140032a89  mov     [rsp+140h+Destination.MaximumLength], cx
0x140032a8e  mov     ecx, 6E664357h
0x140032a93  call    WcAllocateUnicodeString
0x140032a98  mov     edi, eax
0x140032a9a  test    eax, eax
0x140032a9c  js      loc_140032D0A
0x140032aa2  mov     rdx, [rsp+140h+FileNameInformation]
0x140032aa7  lea     rcx, [rsp+140h+Destination]; Destination
0x140032aac  add     rdx, 8; Source
0x140032ab0  call    cs:__imp_RtlAppendUnicodeStringToString
0x140032ab7  nop     dword ptr [rax+rax+00h]
0x140032abc  lea     rdx, Source2; "\\"
0x140032ac3  lea     rcx, [rsp+140h+Destination]; Destination
0x140032ac8  call    cs:__imp_RtlAppendUnicodeToString
0x140032acf  nop     dword ptr [rax+rax+00h]
0x140032ad4  movzx   eax, [rsp+140h+Destination.Length]
0x140032ad9  lea     rsi, [rbx+0E8h]
0x140032ae0  mov     rcx, rsi; Object
0x140032ae3  mov     [rsp+140h+var_FE], ax
0x140032ae8  xor     r9d, r9d; Alertable
0x140032aeb  mov     qword ptr [rsp+140h+FileInformationClass], r15; Timeout
0x140032af0  xor     r8d, r8d; WaitMode
0x140032af3  xor     edx, edx; WaitReason
0x140032af5  call    cs:__imp_KeWaitForSingleObject
0x140032afc  nop     dword ptr [rax+rax+00h]
0x140032b01  mov     rcx, [rbx+100h]; HashTable
0x140032b08  test    rcx, rcx
0x140032b0b  jz      loc_140032CDB
0x140032b11  cmp     [rcx+14h], r15d
0x140032b15  jz      loc_140032CDB
0x140032b1b  lea     rdx, [rsp+140h+Enumerator]; Enumerator
0x140032b20  call    cs:__imp_RtlInitEnumerationHashTable
0x140032b27  nop     dword ptr [rax+rax+00h]
0x140032b2c  mov     rcx, [rbx+100h]; HashTable
0x140032b33  lea     rdx, [rsp+140h+Enumerator]; Enumerator
0x140032b38  call    cs:__imp_RtlEnumerateEntryHashTable
0x140032b3f  nop     dword ptr [rax+rax+00h]
0x140032b44  mov     r14, rax
0x140032b47  test    rax, rax
0x140032b4a  jz      loc_140032CC3
0x140032b50  lea     rsi, WPP_RECORDER_INITIALIZED
0x140032b57  lea     r15, aOnecoreBaseFsW_10; "onecore\\base\\fs\\wci\\wcifs\\tombston"...
0x140032b5e  lea     r12, WPP_6c993b8198b53d328fc429e03cc469de_Traceguids
0x140032b65  movzx   eax, [rsp+140h+var_FE]
0x140032b6a  lea     rdx, [r14+20h]; Source
0x140032b6e  lea     rcx, [rsp+140h+Destination]; Destination
0x140032b73  mov     [rsp+140h+Destination.Length], ax
0x140032b78  call    cs:__imp_RtlAppendUnicodeStringToString
0x140032b7f  nop     dword ptr [rax+rax+00h]
0x140032b84  mov     r8b, [r14+18h]
0x140032b88  lea     rdx, [rsp+140h+Destination]
0x140032b8d  mov     rcx, [r13+18h]; Instance
0x140032b91  call    WcCreateTombstone
0x140032b96  mov     edi, eax
0x140032b98  test    eax, eax
0x140032b9a  jns     loc_140032C6B
0x140032ba0  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140032ba7  jz      short loc_140032BDB
0x140032ba9  mov     rcx, cs:wil_details_featureDescriptors_a
0x140032bb0  mov     r9d, 1Eh
0x140032bb6  mov     dword ptr [rsp+140h+var_108], eax
0x140032bba  mov     dl, 2
0x140032bbc  mov     [rsp+140h+var_110], 5C5h
0x140032bc4  mov     [rsp+140h+LengthReturned], r15
0x140032bc9  mov     rcx, [rcx+40h]
0x140032bcd  lea     r8d, [r9-19h]
0x140032bd1  mov     qword ptr [rsp+140h+FileInformationClass], r12
0x140032bd6  call    WPP_RECORDER_SF_sDd
0x140032bdb  mov     eax, cs:dword_14000E060
0x140032be1  cmp     eax, 5
0x140032be4  jbe     loc_140032C6B
0x140032bea  mov     rdx, 400000000000h
0x140032bf4  lea     rcx, dword_14000E060
0x140032bfb  call    _tlgKeywordOn
0x140032c00  test    al, al
0x140032c02  jz      short loc_140032C6B
0x140032c04  mov     ecx, 1
0x140032c09  mov     [rsp+140h+var_FF], 6
0x140032c0e  lea     rax, [rsp+140h+var_100]
0x140032c13  mov     [rsp+140h+var_100], cl
0x140032c17  mov     [rbp+40h+var_70], rax
0x140032c1b  lea     rdx, byte_14000BAEB
0x140032c22  lea     rax, [rsp+140h+var_FF]
0x140032c27  mov     [rbp+40h+var_68], rcx
0x140032c2b  mov     [rbp+40h+var_60], rax
0x140032c2f  xor     r9d, r9d
0x140032c32  lea     rax, [rsp+140h+var_F8]
0x140032c37  mov     [rbp+40h+var_58], rcx
0x140032c3b  mov     [rbp+40h+var_50], rax
0x140032c3f  lea     rcx, dword_14000E060
0x140032c46  lea     rax, [rbp+40h+var_90]
0x140032c4a  mov     dword ptr [rsp+140h+var_F8], edi
0x140032c4e  mov     [rsp+140h+LengthReturned], rax
0x140032c53  xor     r8d, r8d
0x140032c56  mov     [rsp+140h+FileInformationClass], 5
0x140032c5e  mov     [rbp+40h+var_48], 4
0x140032c66  call    _tlgWriteTransfer_EtwWriteTransfer
0x140032c6b  mov     rcx, [rbx+100h]; HashTable
0x140032c72  xor     r8d, r8d; Context
0x140032c75  mov     rdx, r14; Entry
0x140032c78  call    cs:__imp_RtlRemoveEntryHashTable
0x140032c7f  nop     dword ptr [rax+rax+00h]
0x140032c84  mov     edx, 74684357h; Tag
0x140032c89  mov     rcx, r14; P
0x140032c8c  call    cs:__imp_ExFreePoolWithTag
0x140032c93  nop     dword ptr [rax+rax+00h]
0x140032c98  mov     rcx, [rbx+100h]; HashTable
0x140032c9f  lea     rdx, [rsp+140h+Enumerator]; Enumerator
0x140032ca4  call    cs:__imp_RtlEnumerateEntryHashTable
0x140032cab  nop     dword ptr [rax+rax+00h]
0x140032cb0  mov     r14, rax
0x140032cb3  test    rax, rax
0x140032cb6  jnz     loc_140032B65
0x140032cbc  lea     rsi, [rbx+0E8h]
0x140032cc3  mov     rcx, [rbx+100h]; HashTable
0x140032cca  lea     rdx, [rsp+140h+Enumerator]; Enumerator
0x140032ccf  call    cs:__imp_RtlEndEnumerationHashTable
0x140032cd6  nop     dword ptr [rax+rax+00h]
0x140032cdb  xor     r8d, r8d; Wait
0x140032cde  xor     edx, edx; Increment
0x140032ce0  mov     rcx, rsi; Event
0x140032ce3  call    cs:__imp_KeSetEvent
0x140032cea  nop     dword ptr [rax+rax+00h]
0x140032cef  mov     rcx, [rsp+140h+Destination.Buffer]; P
0x140032cf4  test    rcx, rcx
0x140032cf7  jz      short loc_140032D0A
0x140032cf9  mov     edx, 6E664357h; Tag
0x140032cfe  call    cs:__imp_ExFreePoolWithTag
0x140032d05  nop     dword ptr [rax+rax+00h]
0x140032d0a  mov     rcx, [rsp+140h+FileNameInformation]; FileNameInformation
0x140032d0f  test    rcx, rcx
0x140032d12  jz      short loc_140032D20
0x140032d14  call    cs:__imp_FltReleaseFileNameInformation
0x140032d1b  nop     dword ptr [rax+rax+00h]
0x140032d20  mov     rcx, [rsp+140h+Context]; Context
0x140032d25  test    rcx, rcx
0x140032d28  jz      short loc_140032D36
0x140032d2a  call    cs:__imp_FltReleaseContext
0x140032d31  nop     dword ptr [rax+rax+00h]
0x140032d36  test    rbx, rbx
0x140032d39  jz      short loc_140032D4A
0x140032d3b  mov     rcx, rbx; Context
0x140032d3e  call    cs:__imp_FltReleaseContext
0x140032d45  nop     dword ptr [rax+rax+00h]
0x140032d4a  mov     eax, edi
0x140032d4c  mov     rcx, [rbp+40h+var_40]
0x140032d50  xor     rcx, rsp; StackCookie
0x140032d53  call    __security_check_cookie
0x140032d58  mov     rbx, [rsp+140h+arg_10]
0x140032d60  add     rsp, 110h
0x140032d67  pop     r15
0x140032d69  pop     r14
0x140032d6b  pop     r13
0x140032d6d  pop     r12
0x140032d6f  pop     rdi
0x140032d70  pop     rsi
0x140032d71  pop     rbp
0x140032d72  retn
```
