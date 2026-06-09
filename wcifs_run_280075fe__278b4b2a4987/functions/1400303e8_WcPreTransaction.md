# WcPreTransaction

- ea: `0x1400303e8`
- end: `0x140030701`
- name: `WcPreTransaction`
- size: `793`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140024330`

## callees

- `0x140001008`
- `0x140001030`
- `0x1400016f0`
- `0x140001b00`
- `0x1400020c4`
- `0x140007c60`
- `0x140018e28`
- `0x14002ee54`
- `0x1400303e8`

## import_xrefs

- `ntoskrnl!PsGetSiloIdentifier` at `0x14003052d`
- `ntoskrnl!PsGetSiloIdentifier` at `0x140030627`
- `ntoskrnl!PsGetSiloIdentifier` at `0x14003052d`
- `ntoskrnl!PsGetSiloIdentifier` at `0x140030627`
- `ntoskrnl!IoGetSilo` at `0x14003051e`
- `ntoskrnl!IoGetSilo` at `0x140030618`
- `ntoskrnl!IoGetSilo` at `0x14003051e`
- `ntoskrnl!IoGetSilo` at `0x140030618`
- `ntoskrnl!RtlHashUnicodeString` at `0x1400304a7`
- `ntoskrnl!RtlHashUnicodeString` at `0x1400304a7`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400306cb`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400306cb`
- `FLTMGR!FltGetFileNameInformation` at `0x140030470`
- `FLTMGR!FltGetFileNameInformation` at `0x140030470`
- `FLTMGR!FltParseFileNameInformation` at `0x140030484`
- `FLTMGR!FltParseFileNameInformation` at `0x140030484`

## string_xrefs

- `0x14003069c`: `onecore\base\fs\wci\wcifs\create.c`

## pseudocode

```c
__int64 __fastcall WcPreTransaction(PFLT_CALLBACK_DATA CallbackData, __int64 a2)
{
  int v4; // edx
  __int64 UnionContext; // r14
  unsigned int Expansion; // edi
  int v7; // r10d
  __int64 v8; // rcx
  __int64 Silo; // rax
  int SiloIdentifier; // eax
  int v11; // r9d
  __int64 v12; // rcx
  __int64 v13; // rax
  int v14; // eax
  char v16; // [rsp+30h] [rbp-59h]
  int v17; // [rsp+40h] [rbp-49h] BYREF
  int v18; // [rsp+44h] [rbp-45h] BYREF
  ULONG HashValue; // [rsp+48h] [rbp-41h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+50h] [rbp-39h] BYREF
  __int64 v21; // [rsp+58h] [rbp-31h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v22[2]; // [rsp+60h] [rbp-29h] BYREF
  int *v23; // [rsp+80h] [rbp-9h]
  __int64 v24; // [rsp+88h] [rbp-1h]
  __int64 *v25; // [rsp+90h] [rbp+7h]
  __int64 v26; // [rsp+98h] [rbp+Fh]
  int *v27; // [rsp+A0h] [rbp+17h]
  __int64 v28; // [rsp+A8h] [rbp+1Fh]

  FileNameInformation = 0;
  HashValue = 0;
  if ( (unsigned __int8)WcIsSiloFileObject(*(_QWORD *)(a2 + 24)) )
  {
    UnionContext = 0;
    if ( (_BYTE)word_14000E6A0 )
    {
      Expansion = WcPreCreateExpansion(CallbackData);
      goto LABEL_20;
    }
    if ( (CallbackData->Iopb->Parameters.Create.Options & 0x2000) == 0
      && FltGetFileNameInformation(CallbackData, 0x102u, &FileNameInformation) >= 0
      && FltParseFileNameInformation(FileNameInformation) >= 0 )
    {
      RtlHashUnicodeString(&FileNameInformation->FinalComponent, 1u, 0, &HashValue);
    }
    if ( (unsigned int)dword_14000E060 > 5 && (unsigned __int8)tlgKeywordOn(&dword_14000E060, 0x400000000000LL) )
    {
      v8 = *(_QWORD *)(a2 + 32);
      v23 = &v17;
      v21 = HashValue;
      v25 = &v21;
      v17 = v7;
      v24 = 4;
      v26 = 8;
      Silo = IoGetSilo(v8);
      SiloIdentifier = PsGetSiloIdentifier(Silo);
      v28 = 4;
      v18 = SiloIdentifier;
      v27 = &v18;
      tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_14000E060, (unsigned __int8 *)&unk_14000B500, 0, 0, 5u, v22);
    }
    Expansion = -1072103361;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v11 = 49;
      v16 = 22;
LABEL_19:
      LOBYTE(v4) = 3;
      WPP_RECORDER_SF_sDd(
        WPP_GLOBAL_Control->DeviceExtension,
        v4,
        5,
        v11,
        (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
        v16,
        63);
    }
  }
  else
  {
    Expansion = 0;
    UnionContext = WcGetUnionContext(CallbackData, *(_QWORD *)(a2 + 24), *(_QWORD *)(a2 + 32));
    if ( UnionContext )
    {
      if ( (unsigned int)dword_14000E060 > 5 && (unsigned __int8)tlgKeywordOn(&dword_14000E060, 0x400000000000LL) )
      {
        v12 = *(_QWORD *)(a2 + 32);
        v23 = &v18;
        v25 = &v21;
        v18 = 0;
        v24 = 4;
        v21 = 0;
        v26 = 8;
        v13 = IoGetSilo(v12);
        v14 = PsGetSiloIdentifier(v13);
        v28 = 4;
        v17 = v14;
        v27 = &v17;
        tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_14000E060, (unsigned __int8 *)byte_14000B3F1, 0, 0, 5u, v22);
      }
      Expansion = -1072103361;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v11 = 50;
        v16 = 51;
        goto LABEL_19;
      }
    }
  }
LABEL_20:
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( UnionContext )
    WcReleaseUnionContext(UnionContext);
  return Expansion;
}

```

## disassembly

```asm
0x1400303e8  push    rbp
0x1400303ea  push    rbx
0x1400303eb  push    rsi
0x1400303ec  push    rdi
0x1400303ed  push    r14
0x1400303ef  lea     rbp, [rsp-37h]
0x1400303f4  sub     rsp, 0C0h
0x1400303fb  mov     rax, cs:__security_cookie
0x140030402  xor     rax, rsp
0x140030405  mov     [rbp+57h+var_30], rax
0x140030409  mov     rsi, rdx
0x14003040c  mov     [rbp+57h+FileNameInformation], 0
0x140030414  mov     rdx, [rdx+20h]
0x140030418  mov     rbx, rcx
0x14003041b  mov     edi, r8d
0x14003041e  mov     [rbp+57h+HashValue], 0
0x140030425  mov     rcx, [rsi+18h]
0x140030429  call    WcIsSiloFileObject
0x14003042e  test    al, al
0x140030430  jz      loc_1400305A4
0x140030436  xor     r14d, r14d
0x140030439  cmp     byte ptr cs:word_14000E6A0, r14b
0x140030440  jz      short loc_140030457
0x140030442  mov     r8d, edi
0x140030445  mov     rdx, rsi
0x140030448  mov     rcx, rbx; CallbackData
0x14003044b  call    WcPreCreateExpansion
0x140030450  mov     edi, eax
0x140030452  jmp     loc_1400306C2
0x140030457  mov     rax, [rbx+10h]
0x14003045b  test    dword ptr [rax+20h], 2000h
0x140030462  jnz     short loc_1400304B8
0x140030464  lea     r8, [rbp+57h+FileNameInformation]; FileNameInformation
0x140030468  mov     edx, 102h; NameOptions
0x14003046d  mov     rcx, rbx; CallbackData
0x140030470  call    cs:__imp_FltGetFileNameInformation
0x140030477  nop     dword ptr [rax+rax+00h]
0x14003047c  test    eax, eax
0x14003047e  js      short loc_1400304B3
0x140030480  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x140030484  call    cs:__imp_FltParseFileNameInformation
0x14003048b  nop     dword ptr [rax+rax+00h]
0x140030490  test    eax, eax
0x140030492  js      short loc_1400304B3
0x140030494  mov     rcx, [rbp+57h+FileNameInformation]
0x140030498  lea     r9, [rbp+57h+HashValue]; HashValue
0x14003049c  xor     r8d, r8d; HashAlgorithm
0x14003049f  add     rcx, 58h ; 'X'; String
0x1400304a3  lea     edx, [r8+1]; CaseInSensitive
0x1400304a7  call    cs:__imp_RtlHashUnicodeString
0x1400304ae  nop     dword ptr [rax+rax+00h]
0x1400304b3  xor     r10d, r10d
0x1400304b6  jmp     short loc_1400304BE
0x1400304b8  mov     r10d, 1
0x1400304be  mov     eax, cs:dword_14000E060
0x1400304c4  mov     ebx, 5
0x1400304c9  cmp     eax, ebx
0x1400304cb  jbe     loc_140030572
0x1400304d1  mov     rdx, 400000000000h
0x1400304db  lea     rcx, dword_14000E060
0x1400304e2  call    _tlgKeywordOn
0x1400304e7  test    al, al
0x1400304e9  jz      loc_140030572
0x1400304ef  mov     rcx, [rsi+20h]
0x1400304f3  lea     rax, [rbp+57h+var_A0]
0x1400304f7  mov     [rbp+57h+var_60], rax
0x1400304fb  mov     eax, [rbp+57h+HashValue]
0x1400304fe  mov     [rbp+57h+var_88], rax
0x140030502  lea     rax, [rbp+57h+var_88]
0x140030506  mov     [rbp+57h+var_50], rax
0x14003050a  mov     [rbp+57h+var_A0], r10d
0x14003050e  mov     [rbp+57h+var_58], 4
0x140030516  mov     [rbp+57h+var_48], 8
0x14003051e  call    cs:__imp_IoGetSilo
0x140030525  nop     dword ptr [rax+rax+00h]
0x14003052a  mov     rcx, rax
0x14003052d  call    cs:__imp_PsGetSiloIdentifier
0x140030534  nop     dword ptr [rax+rax+00h]
0x140030539  xor     r9d, r9d
0x14003053c  mov     [rbp+57h+var_38], 4
0x140030544  mov     [rbp+57h+var_9C], eax
0x140030547  lea     rdx, unk_14000B500
0x14003054e  lea     rax, [rbp+57h+var_9C]
0x140030552  xor     r8d, r8d
0x140030555  mov     [rbp+57h+var_40], rax
0x140030559  lea     rcx, dword_14000E060
0x140030560  lea     rax, [rbp+57h+var_80]
0x140030564  mov     [rsp+0E0h+var_B8], rax
0x140030569  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x14003056d  call    _tlgWriteTransfer_EtwWriteTransfer
0x140030572  mov     eax, 0C019003Fh
0x140030577  mov     edi, eax
0x140030579  lea     rcx, WPP_RECORDER_INITIALIZED
0x140030580  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140030587  jz      loc_1400306C2
0x14003058d  mov     [rsp+0E0h+var_A8], eax
0x140030591  mov     r9d, 31h ; '1'
0x140030597  mov     dword ptr [rsp+0E0h+var_B0], 816h
0x14003059f  jmp     loc_140030695
0x1400305a4  mov     r8, [rsi+20h]
0x1400305a8  mov     rcx, rbx
0x1400305ab  mov     rdx, [rsi+18h]
0x1400305af  xor     edi, edi
0x1400305b1  call    WcGetUnionContext
0x1400305b6  mov     r14, rax
0x1400305b9  test    rax, rax
0x1400305bc  jz      loc_1400306C2
0x1400305c2  mov     ecx, cs:dword_14000E060
0x1400305c8  lea     ebx, [rdi+5]
0x1400305cb  cmp     ecx, ebx
0x1400305cd  jbe     loc_14003066C
0x1400305d3  mov     rdx, 400000000000h
0x1400305dd  lea     rcx, dword_14000E060
0x1400305e4  call    _tlgKeywordOn
0x1400305e9  test    al, al
0x1400305eb  jz      short loc_14003066C
0x1400305ed  mov     rcx, [rsi+20h]
0x1400305f1  lea     rax, [rbp+57h+var_9C]
0x1400305f5  mov     [rbp+57h+var_60], rax
0x1400305f9  lea     rax, [rbp+57h+var_88]
0x1400305fd  mov     [rbp+57h+var_50], rax
0x140030601  mov     [rbp+57h+var_9C], edi
0x140030604  mov     [rbp+57h+var_58], 4
0x14003060c  mov     [rbp+57h+var_88], rdi
0x140030610  mov     [rbp+57h+var_48], 8
0x140030618  call    cs:__imp_IoGetSilo
0x14003061f  nop     dword ptr [rax+rax+00h]
0x140030624  mov     rcx, rax
0x140030627  call    cs:__imp_PsGetSiloIdentifier
0x14003062e  nop     dword ptr [rax+rax+00h]
0x140030633  xor     r9d, r9d
0x140030636  mov     [rbp+57h+var_38], 4
0x14003063e  mov     [rbp+57h+var_A0], eax
0x140030641  lea     rdx, byte_14000B3F1
0x140030648  lea     rax, [rbp+57h+var_A0]
0x14003064c  xor     r8d, r8d
0x14003064f  mov     [rbp+57h+var_40], rax
0x140030653  lea     rcx, dword_14000E060
0x14003065a  lea     rax, [rbp+57h+var_80]
0x14003065e  mov     [rsp+0E0h+var_B8], rax
0x140030663  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x140030667  call    _tlgWriteTransfer_EtwWriteTransfer
0x14003066c  mov     eax, 0C019003Fh
0x140030671  mov     edi, eax
0x140030673  lea     rcx, WPP_RECORDER_INITIALIZED
0x14003067a  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140030681  jz      short loc_1400306C2
0x140030683  mov     [rsp+0E0h+var_A8], eax
0x140030687  mov     r9d, 32h ; '2'
0x14003068d  mov     dword ptr [rsp+0E0h+var_B0], 833h
0x140030695  mov     rcx, cs:WPP_GLOBAL_Control
0x14003069c  lea     rax, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x1400306a3  mov     [rsp+0E0h+var_B8], rax
0x1400306a8  mov     r8d, ebx
0x1400306ab  lea     rax, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x1400306b2  mov     dl, 3
0x1400306b4  mov     [rsp+0E0h+var_C0], rax
0x1400306b9  mov     rcx, [rcx+40h]
0x1400306bd  call    WPP_RECORDER_SF_sDd
0x1400306c2  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x1400306c6  test    rcx, rcx
0x1400306c9  jz      short loc_1400306D7
0x1400306cb  call    cs:__imp_FltReleaseFileNameInformation
0x1400306d2  nop     dword ptr [rax+rax+00h]
0x1400306d7  test    r14, r14
0x1400306da  jz      short loc_1400306E4
0x1400306dc  mov     rcx, r14
0x1400306df  call    WcReleaseUnionContext
0x1400306e4  mov     eax, edi
0x1400306e6  mov     rcx, [rbp+57h+var_30]
0x1400306ea  xor     rcx, rsp; StackCookie
0x1400306ed  call    __security_check_cookie
0x1400306f2  add     rsp, 0C0h
0x1400306f9  pop     r14
0x1400306fb  pop     rdi
0x1400306fc  pop     rsi
0x1400306fd  pop     rbx
0x1400306fe  pop     rbp
0x1400306ff  retn
```
