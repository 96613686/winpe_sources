# WcPreTransaction

- ea: `0x140030438`
- end: `0x140030751`
- name: `WcPreTransaction`
- size: `793`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140024380`

## callees

- `0x140001008`
- `0x140001030`
- `0x1400016f0`
- `0x140001b00`
- `0x1400020c4`
- `0x140007c60`
- `0x140018e28`
- `0x14002eea4`
- `0x140030438`

## import_xrefs

- `ntoskrnl!PsGetSiloIdentifier` at `0x14003057d`
- `ntoskrnl!PsGetSiloIdentifier` at `0x140030677`
- `ntoskrnl!PsGetSiloIdentifier` at `0x14003057d`
- `ntoskrnl!PsGetSiloIdentifier` at `0x140030677`
- `ntoskrnl!IoGetSilo` at `0x14003056e`
- `ntoskrnl!IoGetSilo` at `0x140030668`
- `ntoskrnl!IoGetSilo` at `0x14003056e`
- `ntoskrnl!IoGetSilo` at `0x140030668`
- `ntoskrnl!RtlHashUnicodeString` at `0x1400304f7`
- `ntoskrnl!RtlHashUnicodeString` at `0x1400304f7`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003071b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003071b`
- `FLTMGR!FltGetFileNameInformation` at `0x1400304c0`
- `FLTMGR!FltGetFileNameInformation` at `0x1400304c0`
- `FLTMGR!FltParseFileNameInformation` at `0x1400304d4`
- `FLTMGR!FltParseFileNameInformation` at `0x1400304d4`

## string_xrefs

- `0x1400306ec`: `onecore\base\fs\wci\wcifs\create.c`

## pseudocode

```c
__int64 __fastcall WcPreTransaction(PFLT_CALLBACK_DATA CallbackData, __int64 a2, unsigned int a3)
{
  __int64 v4; // rdx
  int v7; // edx
  int v8; // r9d
  __int64 UnionContext; // r14
  unsigned int Expansion; // edi
  int v11; // r10d
  __int64 v12; // rcx
  __int64 Silo; // rax
  int SiloIdentifier; // eax
  int v15; // r9d
  __int64 v16; // rcx
  __int64 v17; // rax
  int v18; // eax
  char v20; // [rsp+30h] [rbp-59h]
  int v21; // [rsp+40h] [rbp-49h] BYREF
  int v22; // [rsp+44h] [rbp-45h] BYREF
  ULONG HashValue; // [rsp+48h] [rbp-41h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+50h] [rbp-39h] BYREF
  __int64 v25; // [rsp+58h] [rbp-31h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v26[2]; // [rsp+60h] [rbp-29h] BYREF
  int *v27; // [rsp+80h] [rbp-9h]
  __int64 v28; // [rsp+88h] [rbp-1h]
  __int64 *v29; // [rsp+90h] [rbp+7h]
  __int64 v30; // [rsp+98h] [rbp+Fh]
  int *v31; // [rsp+A0h] [rbp+17h]
  __int64 v32; // [rsp+A8h] [rbp+1Fh]

  FileNameInformation = 0;
  v4 = *(_QWORD *)(a2 + 32);
  HashValue = 0;
  if ( WcIsSiloFileObject(*(struct _FLT_INSTANCE **)(a2 + 24), v4) )
  {
    UnionContext = 0;
    if ( (_BYTE)word_14000E6A0 )
    {
      Expansion = WcPreCreateExpansion(CallbackData, a2, a3, v8);
      goto LABEL_20;
    }
    if ( (CallbackData->Iopb->Parameters.Create.Options & 0x2000) == 0
      && FltGetFileNameInformation(CallbackData, 0x102u, &FileNameInformation) >= 0
      && FltParseFileNameInformation(FileNameInformation) >= 0 )
    {
      RtlHashUnicodeString(&FileNameInformation->FinalComponent, 1u, 0, &HashValue);
    }
    if ( (unsigned int)dword_14000E060 > 5 && tlgKeywordOn((__int64)&dword_14000E060, 0x400000000000LL) )
    {
      v12 = *(_QWORD *)(a2 + 32);
      v27 = &v21;
      v25 = HashValue;
      v29 = &v25;
      v21 = v11;
      v28 = 4;
      v30 = 8;
      Silo = IoGetSilo(v12);
      SiloIdentifier = PsGetSiloIdentifier(Silo);
      v32 = 4;
      v22 = SiloIdentifier;
      v31 = &v22;
      tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_14000E060, (unsigned __int8 *)&unk_14000B500, 0, 0, 5u, v26);
    }
    Expansion = -1072103361;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v15 = 49;
      v20 = 22;
LABEL_19:
      LOBYTE(v7) = 3;
      WPP_RECORDER_SF_sDd(
        wil_details_featureDescriptors_a->DeviceExtension,
        v7,
        5,
        v15,
        (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
        v20,
        -1072103361);
    }
  }
  else
  {
    Expansion = 0;
    UnionContext = WcGetUnionContext(
                     CallbackData,
                     *(struct _FLT_INSTANCE **)(a2 + 24),
                     *(struct _FILE_OBJECT **)(a2 + 32));
    if ( UnionContext )
    {
      if ( (unsigned int)dword_14000E060 > 5 && tlgKeywordOn((__int64)&dword_14000E060, 0x400000000000LL) )
      {
        v16 = *(_QWORD *)(a2 + 32);
        v27 = &v22;
        v29 = &v25;
        v22 = 0;
        v28 = 4;
        v25 = 0;
        v30 = 8;
        v17 = IoGetSilo(v16);
        v18 = PsGetSiloIdentifier(v17);
        v32 = 4;
        v21 = v18;
        v31 = &v21;
        tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_14000E060, (unsigned __int8 *)byte_14000B3F1, 0, 0, 5u, v26);
      }
      Expansion = -1072103361;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v15 = 50;
        v20 = 51;
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
0x140030438  push    rbp
0x14003043a  push    rbx
0x14003043b  push    rsi
0x14003043c  push    rdi
0x14003043d  push    r14
0x14003043f  lea     rbp, [rsp-37h]
0x140030444  sub     rsp, 0C0h
0x14003044b  mov     rax, cs:__security_cookie
0x140030452  xor     rax, rsp
0x140030455  mov     [rbp+57h+var_30], rax
0x140030459  mov     rsi, rdx
0x14003045c  mov     [rbp+57h+FileNameInformation], 0
0x140030464  mov     rdx, [rdx+20h]
0x140030468  mov     rbx, rcx
0x14003046b  mov     edi, r8d
0x14003046e  mov     [rbp+57h+HashValue], 0
0x140030475  mov     rcx, [rsi+18h]
0x140030479  call    WcIsSiloFileObject
0x14003047e  test    al, al
0x140030480  jz      loc_1400305F4
0x140030486  xor     r14d, r14d
0x140030489  cmp     byte ptr cs:word_14000E6A0, r14b
0x140030490  jz      short loc_1400304A7
0x140030492  mov     r8d, edi
0x140030495  mov     rdx, rsi
0x140030498  mov     rcx, rbx; CallbackData
0x14003049b  call    WcPreCreateExpansion
0x1400304a0  mov     edi, eax
0x1400304a2  jmp     loc_140030712
0x1400304a7  mov     rax, [rbx+10h]
0x1400304ab  test    dword ptr [rax+20h], 2000h
0x1400304b2  jnz     short loc_140030508
0x1400304b4  lea     r8, [rbp+57h+FileNameInformation]; FileNameInformation
0x1400304b8  mov     edx, 102h; NameOptions
0x1400304bd  mov     rcx, rbx; CallbackData
0x1400304c0  call    cs:__imp_FltGetFileNameInformation
0x1400304c7  nop     dword ptr [rax+rax+00h]
0x1400304cc  test    eax, eax
0x1400304ce  js      short loc_140030503
0x1400304d0  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x1400304d4  call    cs:__imp_FltParseFileNameInformation
0x1400304db  nop     dword ptr [rax+rax+00h]
0x1400304e0  test    eax, eax
0x1400304e2  js      short loc_140030503
0x1400304e4  mov     rcx, [rbp+57h+FileNameInformation]
0x1400304e8  lea     r9, [rbp+57h+HashValue]; HashValue
0x1400304ec  xor     r8d, r8d; HashAlgorithm
0x1400304ef  add     rcx, 58h ; 'X'; String
0x1400304f3  lea     edx, [r8+1]; CaseInSensitive
0x1400304f7  call    cs:__imp_RtlHashUnicodeString
0x1400304fe  nop     dword ptr [rax+rax+00h]
0x140030503  xor     r10d, r10d
0x140030506  jmp     short loc_14003050E
0x140030508  mov     r10d, 1
0x14003050e  mov     eax, cs:dword_14000E060
0x140030514  mov     ebx, 5
0x140030519  cmp     eax, ebx
0x14003051b  jbe     loc_1400305C2
0x140030521  mov     rdx, 400000000000h
0x14003052b  lea     rcx, dword_14000E060
0x140030532  call    _tlgKeywordOn
0x140030537  test    al, al
0x140030539  jz      loc_1400305C2
0x14003053f  mov     rcx, [rsi+20h]
0x140030543  lea     rax, [rbp+57h+var_A0]
0x140030547  mov     [rbp+57h+var_60], rax
0x14003054b  mov     eax, [rbp+57h+HashValue]
0x14003054e  mov     [rbp+57h+var_88], rax
0x140030552  lea     rax, [rbp+57h+var_88]
0x140030556  mov     [rbp+57h+var_50], rax
0x14003055a  mov     [rbp+57h+var_A0], r10d
0x14003055e  mov     [rbp+57h+var_58], 4
0x140030566  mov     [rbp+57h+var_48], 8
0x14003056e  call    cs:__imp_IoGetSilo
0x140030575  nop     dword ptr [rax+rax+00h]
0x14003057a  mov     rcx, rax
0x14003057d  call    cs:__imp_PsGetSiloIdentifier
0x140030584  nop     dword ptr [rax+rax+00h]
0x140030589  xor     r9d, r9d
0x14003058c  mov     [rbp+57h+var_38], 4
0x140030594  mov     [rbp+57h+var_9C], eax
0x140030597  lea     rdx, unk_14000B500
0x14003059e  lea     rax, [rbp+57h+var_9C]
0x1400305a2  xor     r8d, r8d
0x1400305a5  mov     [rbp+57h+var_40], rax
0x1400305a9  lea     rcx, dword_14000E060
0x1400305b0  lea     rax, [rbp+57h+var_80]
0x1400305b4  mov     [rsp+0E0h+var_B8], rax
0x1400305b9  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x1400305bd  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400305c2  mov     eax, 0C019003Fh
0x1400305c7  mov     edi, eax
0x1400305c9  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400305d0  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400305d7  jz      loc_140030712
0x1400305dd  mov     [rsp+0E0h+var_A8], eax
0x1400305e1  mov     r9d, 31h ; '1'
0x1400305e7  mov     dword ptr [rsp+0E0h+var_B0], 816h
0x1400305ef  jmp     loc_1400306E5
0x1400305f4  mov     r8, [rsi+20h]
0x1400305f8  mov     rcx, rbx
0x1400305fb  mov     rdx, [rsi+18h]
0x1400305ff  xor     edi, edi
0x140030601  call    WcGetUnionContext
0x140030606  mov     r14, rax
0x140030609  test    rax, rax
0x14003060c  jz      loc_140030712
0x140030612  mov     ecx, cs:dword_14000E060
0x140030618  lea     ebx, [rdi+5]
0x14003061b  cmp     ecx, ebx
0x14003061d  jbe     loc_1400306BC
0x140030623  mov     rdx, 400000000000h
0x14003062d  lea     rcx, dword_14000E060
0x140030634  call    _tlgKeywordOn
0x140030639  test    al, al
0x14003063b  jz      short loc_1400306BC
0x14003063d  mov     rcx, [rsi+20h]
0x140030641  lea     rax, [rbp+57h+var_9C]
0x140030645  mov     [rbp+57h+var_60], rax
0x140030649  lea     rax, [rbp+57h+var_88]
0x14003064d  mov     [rbp+57h+var_50], rax
0x140030651  mov     [rbp+57h+var_9C], edi
0x140030654  mov     [rbp+57h+var_58], 4
0x14003065c  mov     [rbp+57h+var_88], rdi
0x140030660  mov     [rbp+57h+var_48], 8
0x140030668  call    cs:__imp_IoGetSilo
0x14003066f  nop     dword ptr [rax+rax+00h]
0x140030674  mov     rcx, rax
0x140030677  call    cs:__imp_PsGetSiloIdentifier
0x14003067e  nop     dword ptr [rax+rax+00h]
0x140030683  xor     r9d, r9d
0x140030686  mov     [rbp+57h+var_38], 4
0x14003068e  mov     [rbp+57h+var_A0], eax
0x140030691  lea     rdx, byte_14000B3F1
0x140030698  lea     rax, [rbp+57h+var_A0]
0x14003069c  xor     r8d, r8d
0x14003069f  mov     [rbp+57h+var_40], rax
0x1400306a3  lea     rcx, dword_14000E060
0x1400306aa  lea     rax, [rbp+57h+var_80]
0x1400306ae  mov     [rsp+0E0h+var_B8], rax
0x1400306b3  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x1400306b7  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400306bc  mov     eax, 0C019003Fh
0x1400306c1  mov     edi, eax
0x1400306c3  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400306ca  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400306d1  jz      short loc_140030712
0x1400306d3  mov     [rsp+0E0h+var_A8], eax
0x1400306d7  mov     r9d, 32h ; '2'
0x1400306dd  mov     dword ptr [rsp+0E0h+var_B0], 833h
0x1400306e5  mov     rcx, cs:wil_details_featureDescriptors_a
0x1400306ec  lea     rax, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x1400306f3  mov     [rsp+0E0h+var_B8], rax
0x1400306f8  mov     r8d, ebx
0x1400306fb  lea     rax, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x140030702  mov     dl, 3
0x140030704  mov     [rsp+0E0h+var_C0], rax
0x140030709  mov     rcx, [rcx+40h]
0x14003070d  call    WPP_RECORDER_SF_sDd
0x140030712  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x140030716  test    rcx, rcx
0x140030719  jz      short loc_140030727
0x14003071b  call    cs:__imp_FltReleaseFileNameInformation
0x140030722  nop     dword ptr [rax+rax+00h]
0x140030727  test    r14, r14
0x14003072a  jz      short loc_140030734
0x14003072c  mov     rcx, r14
0x14003072f  call    WcReleaseUnionContext
0x140030734  mov     eax, edi
0x140030736  mov     rcx, [rbp+57h+var_30]
0x14003073a  xor     rcx, rsp; StackCookie
0x14003073d  call    __security_check_cookie
0x140030742  add     rsp, 0C0h
0x140030749  pop     r14
0x14003074b  pop     rdi
0x14003074c  pop     rsi
0x14003074d  pop     rbx
0x14003074e  pop     rbp
0x14003074f  retn
```
