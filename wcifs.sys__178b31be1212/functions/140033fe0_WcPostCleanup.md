# WcPostCleanup

- ea: `0x140033fe0`
- end: `0x140034400`
- name: `WcPostCleanup`
- size: `1056`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting`

## callees

- `0x140001008`
- `0x140001030`
- `0x1400020c4`
- `0x140007c60`
- `0x14001bf24`
- `0x14001ce88`
- `0x140033fe0`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x140034066`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140034066`
- `ntoskrnl!IoFileObjectType` at `0x14003403e`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400343b4`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400343b4`
- `ntoskrnl!ObfDereferenceObject` at `0x140034389`
- `ntoskrnl!ObfDereferenceObject` at `0x1400343c9`
- `ntoskrnl!ObfDereferenceObject` at `0x140034389`
- `ntoskrnl!ObfDereferenceObject` at `0x1400343c9`
- `FLTMGR!FltSetInformationFile` at `0x1400340ef`
- `FLTMGR!FltSetInformationFile` at `0x1400340ef`
- `FLTMGR!FltClose` at `0x14003439e`
- `FLTMGR!FltClose` at `0x14003439e`
- `FLTMGR!FltGetStreamContext` at `0x14003433f`
- `FLTMGR!FltGetStreamContext` at `0x14003433f`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140034374`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140034374`
- `FLTMGR!FltReleaseContext` at `0x14003435b`
- `FLTMGR!FltReleaseContext` at `0x14003435b`

## pseudocode

```c
__int64 __fastcall WcPostCleanup(__int64 a1, __int64 a2, _QWORD *a3)
{
  PFLT_FILE_NAME_INFORMATION *v3; // rdi
  __int64 v6; // rax
  NTSTATUS v7; // eax
  int v8; // edx
  int v9; // r9d
  struct _FLT_INSTANCE *v10; // rcx
  NTSTATUS v11; // eax
  int Tombstone; // eax
  int v13; // edx
  int v14; // r10d
  int v15; // eax
  int v16; // edx
  int v17; // esi
  PFLT_FILE_NAME_INFORMATION v18; // rcx
  PFLT_FILE_NAME_INFORMATION v19; // rcx
  char v21; // [rsp+30h] [rbp-59h]
  __int64 v22; // [rsp+38h] [rbp-51h]
  NTSTATUS v23; // [rsp+38h] [rbp-51h]
  int v24; // [rsp+38h] [rbp-51h]
  char v25; // [rsp+40h] [rbp-49h] BYREF
  char v26; // [rsp+41h] [rbp-48h] BYREF
  char FileInformation[2]; // [rsp+42h] [rbp-47h] BYREF
  int v28; // [rsp+44h] [rbp-45h] BYREF
  PFLT_CONTEXT Context; // [rsp+48h] [rbp-41h] BYREF
  PVOID Object; // [rsp+50h] [rbp-39h] BYREF
  __int64 v31; // [rsp+58h] [rbp-31h]
  struct _EVENT_DATA_DESCRIPTOR v32[2]; // [rsp+60h] [rbp-29h] BYREF
  char *v33; // [rsp+80h] [rbp-9h]
  __int64 v34; // [rsp+88h] [rbp-1h]
  char *v35; // [rsp+90h] [rbp+7h]
  __int64 v36; // [rsp+98h] [rbp+Fh]
  int *v37; // [rsp+A0h] [rbp+17h]
  __int64 v38; // [rsp+A8h] [rbp+1Fh]

  v3 = 0;
  v31 = a1;
  Object = 0;
  FileInformation[0] = 0;
  Context = 0;
  v6 = a1;
  if ( a3 )
  {
    v3 = (PFLT_FILE_NAME_INFORMATION *)a3;
    if ( *((_BYTE *)a3 + 17) )
    {
      v7 = ObReferenceObjectByHandle((HANDLE)a3[3], 0x10000u, (POBJECT_TYPE)IoFileObjectType, 0, &Object, 0);
      if ( v7 >= 0 )
      {
        v10 = *(struct _FLT_INSTANCE **)(a2 + 24);
        FileInformation[0] = 0;
        v11 = FltSetInformationFile(v10, (PFILE_OBJECT)Object, FileInformation, 1u, FileDispositionInformation);
        if ( v11 >= 0 || WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_28;
        v23 = v11;
        v9 = 60;
        v21 = -73;
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
LABEL_28:
          if ( *v3 )
            FltReleaseFileNameInformation(*v3);
          v18 = v3[1];
          if ( v18 )
            ObfDereferenceObject(v18);
          v19 = v3[3];
          if ( v19 )
            FltClose(v19);
          ExFreeToPagedLookasideList(&stru_14000E500, v3);
          goto LABEL_35;
        }
        v23 = v7;
        v9 = 59;
        v21 = -87;
      }
      LOBYTE(v8) = 2;
      WPP_RECORDER_SF_sDd(
        wil_details_featureDescriptors_a->DeviceExtension,
        v8,
        6,
        v9,
        (__int64)WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\wcifs.c",
        v21,
        v23);
      goto LABEL_28;
    }
    if ( (*(_BYTE *)(a1 + 32) & 0xC) != 0 )
    {
      Tombstone = WcCreateTombstone(
                    *(PFLT_INSTANCE *)(a2 + 24),
                    (struct _UNICODE_STRING *)(*a3 + 8LL),
                    *((_BYTE *)a3 + 16));
      v28 = Tombstone;
      if ( Tombstone < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v24 = Tombstone;
          LOBYTE(v13) = 2;
          WPP_RECORDER_SF_sDd(
            wil_details_featureDescriptors_a->DeviceExtension,
            v13,
            6,
            61,
            (__int64)WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids,
            (__int64)"onecore\\base\\fs\\wci\\wcifs\\wcifs.c",
            201,
            v24);
        }
        if ( (unsigned int)dword_14000E060 > 5 && tlgKeywordOn((__int64)&dword_14000E060, 0x400000000000LL) )
        {
          v25 = 1;
          v33 = &v25;
          v34 = 1;
          v35 = &v26;
          v26 = 5;
          v37 = &v28;
          v36 = 1;
          v28 = v14;
          v38 = 4;
          tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_14000E060, (unsigned __int8 *)word_14000BD9A, 0, 0, 5u, v32);
        }
      }
    }
    v15 = WcRemoveInMemoryTombstone(*(_QWORD *)(a2 + 24), *a3, a3[1]);
    v17 = v15;
    if ( v15 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v22) = v15;
        LOBYTE(v16) = 2;
        WPP_RECORDER_SF_sDd(
          wil_details_featureDescriptors_a->DeviceExtension,
          v16,
          5,
          62,
          (__int64)WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\wcifs.c",
          221,
          v22);
      }
      if ( (unsigned int)dword_14000E060 > 5 && tlgKeywordOn((__int64)&dword_14000E060, 0x400000000000LL) )
      {
        v26 = 2;
        v33 = &v26;
        v34 = 1;
        v35 = &v25;
        v25 = 5;
        v37 = &v28;
        v36 = 1;
        v28 = v17;
        v38 = 4;
        tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_14000E060, (unsigned __int8 *)&unk_14000BDF8, 0, 0, 5u, v32);
      }
      goto LABEL_28;
    }
    v6 = v31;
  }
  if ( (*(_BYTE *)(v6 + 32) & 0x24) == 4
    && FltGetStreamContext(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), &Context) >= 0 )
  {
    *((_BYTE *)Context + 29) = 1;
    FltReleaseContext(Context);
  }
  if ( v3 )
    goto LABEL_28;
LABEL_35:
  if ( Object )
    ObfDereferenceObject(Object);
  return 0;
}

```

## disassembly

```asm
0x140033fe0  mov     [rsp-8+arg_0], rbx
0x140033fe5  mov     [rsp-8+arg_18], rsi
0x140033fea  push    rbp
0x140033feb  push    rdi
0x140033fec  push    r12
0x140033fee  push    r13
0x140033ff0  push    r15
0x140033ff2  lea     rbp, [rsp-37h]
0x140033ff7  sub     rsp, 0C0h
0x140033ffe  mov     rax, cs:__security_cookie
0x140034005  xor     rax, rsp
0x140034008  mov     [rbp+57h+var_30], rax
0x14003400c  xor     edi, edi
0x14003400e  mov     [rbp+57h+var_88], rcx
0x140034012  mov     [rbp+57h+var_90], rdi
0x140034016  mov     rsi, r8
0x140034019  mov     [rbp+57h+FileInformation], dil
0x14003401d  mov     r13, rdx
0x140034020  mov     [rbp+57h+Context], rdi
0x140034024  mov     rax, rcx
0x140034027  test    r8, r8
0x14003402a  jz      loc_14003432A
0x140034030  cmp     byte ptr [r8+11h], 0
0x140034035  mov     rdi, r8
0x140034038  jz      loc_14003412E
0x14003403e  mov     r8, cs:__imp_IoFileObjectType
0x140034045  lea     rax, [rbp+57h+var_90]
0x140034049  mov     rcx, [rdi+18h]; Handle
0x14003404d  xor     r9d, r9d; AccessMode
0x140034050  mov     [rsp+0E0h+HandleInformation], 0; HandleInformation
0x140034059  mov     edx, 10000h; DesiredAccess
0x14003405e  mov     [rsp+0E0h+Object], rax; Object
0x140034063  mov     r8, [r8]; ObjectType
0x140034066  call    cs:__imp_ObReferenceObjectByHandle
0x14003406d  nop     dword ptr [rax+rax+00h]
0x140034072  test    eax, eax
0x140034074  jns     short loc_1400340D1
0x140034076  lea     rbx, WPP_RECORDER_INITIALIZED
0x14003407d  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140034084  jz      loc_14003436C
0x14003408a  mov     dword ptr [rsp+0E0h+var_A8], eax
0x14003408e  mov     r9d, 3Bh ; ';'
0x140034094  mov     dword ptr [rsp+0E0h+var_B0], 9A9h
0x14003409c  mov     rcx, cs:wil_details_featureDescriptors_a
0x1400340a3  lea     r15, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\wcifs\\wcifs.c"
0x1400340aa  lea     r12, WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids
0x1400340b1  mov     [rsp+0E0h+HandleInformation], r15
0x1400340b6  mov     r8d, 6
0x1400340bc  mov     [rsp+0E0h+Object], r12
0x1400340c1  mov     dl, 2
0x1400340c3  mov     rcx, [rcx+40h]
0x1400340c7  call    WPP_RECORDER_SF_sDd
0x1400340cc  jmp     loc_14003436C
0x1400340d1  mov     rdx, [rbp+57h+var_90]; FileObject
0x1400340d5  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x1400340d9  mov     rcx, [r13+18h]; Instance
0x1400340dd  mov     r9d, 1; Length
0x1400340e3  mov     [rbp+57h+FileInformation], 0
0x1400340e7  mov     dword ptr [rsp+0E0h+Object], 0Dh; FileInformationClass
0x1400340ef  call    cs:__imp_FltSetInformationFile
0x1400340f6  nop     dword ptr [rax+rax+00h]
0x1400340fb  test    eax, eax
0x1400340fd  jns     loc_14003436C
0x140034103  lea     rbx, WPP_RECORDER_INITIALIZED
0x14003410a  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140034111  jz      loc_14003436C
0x140034117  mov     dword ptr [rsp+0E0h+var_A8], eax
0x14003411b  mov     r9d, 3Ch ; '<'
0x140034121  mov     dword ptr [rsp+0E0h+var_B0], 9B7h
0x140034129  jmp     loc_14003409C
0x14003412e  test    byte ptr [rcx+20h], 0Ch
0x140034132  lea     rbx, WPP_RECORDER_INITIALIZED
0x140034139  lea     r15, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\wcifs\\wcifs.c"
0x140034140  lea     r12, WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids
0x140034147  jz      loc_14003423D
0x14003414d  mov     rdx, [r8]
0x140034150  mov     r8b, [r8+10h]
0x140034154  add     rdx, 8
0x140034158  mov     rcx, [r13+18h]; Instance
0x14003415c  call    WcCreateTombstone
0x140034161  mov     [rbp+57h+var_9C], eax
0x140034164  mov     r10d, eax
0x140034167  test    eax, eax
0x140034169  jns     loc_14003423D
0x14003416f  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140034176  jz      short loc_1400341AE
0x140034178  mov     rcx, cs:wil_details_featureDescriptors_a
0x14003417f  mov     r9d, 3Dh ; '='
0x140034185  mov     dword ptr [rsp+0E0h+var_A8], eax
0x140034189  mov     dl, 2
0x14003418b  mov     dword ptr [rsp+0E0h+var_B0], 9C9h
0x140034193  mov     [rsp+0E0h+HandleInformation], r15
0x140034198  mov     rcx, [rcx+40h]
0x14003419c  lea     r8d, [r9-37h]
0x1400341a0  mov     [rsp+0E0h+Object], r12
0x1400341a5  call    WPP_RECORDER_SF_sDd
0x1400341aa  mov     r10d, [rbp+57h+var_9C]
0x1400341ae  mov     eax, cs:dword_14000E060
0x1400341b4  cmp     eax, 5
0x1400341b7  jbe     loc_14003423D
0x1400341bd  mov     rdx, 400000000000h
0x1400341c7  lea     rcx, dword_14000E060
0x1400341ce  call    _tlgKeywordOn
0x1400341d3  test    al, al
0x1400341d5  jz      short loc_14003423D
0x1400341d7  lea     rax, [rbp+57h+var_A0]
0x1400341db  mov     [rbp+57h+var_A0], 1
0x1400341df  mov     [rbp+57h+var_60], rax
0x1400341e3  lea     rdx, word_14000BD9A
0x1400341ea  lea     rax, [rbp+57h+var_9F]
0x1400341ee  mov     [rbp+57h+var_58], 1
0x1400341f6  mov     [rbp+57h+var_50], rax
0x1400341fa  lea     rcx, dword_14000E060
0x140034201  lea     rax, [rbp+57h+var_9C]
0x140034205  mov     [rbp+57h+var_9F], 5
0x140034209  mov     [rbp+57h+var_40], rax
0x14003420d  xor     r9d, r9d
0x140034210  lea     rax, [rbp+57h+var_80]
0x140034214  mov     [rbp+57h+var_48], 1
0x14003421c  mov     [rsp+0E0h+HandleInformation], rax
0x140034221  xor     r8d, r8d
0x140034224  mov     dword ptr [rsp+0E0h+Object], 5
0x14003422c  mov     [rbp+57h+var_9C], r10d
0x140034230  mov     [rbp+57h+var_38], 4
0x140034238  call    _tlgWriteTransfer_EtwWriteTransfer
0x14003423d  mov     r8, [rsi+8]
0x140034241  mov     rdx, [rsi]
0x140034244  mov     rcx, [r13+18h]
0x140034248  call    WcRemoveInMemoryTombstone
0x14003424d  mov     esi, eax
0x14003424f  test    eax, eax
0x140034251  jns     loc_140034326
0x140034257  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14003425e  jz      short loc_140034292
0x140034260  mov     rcx, cs:wil_details_featureDescriptors_a
0x140034267  mov     r9d, 3Eh ; '>'
0x14003426d  mov     dword ptr [rsp+0E0h+var_A8], eax
0x140034271  mov     dl, 2
0x140034273  mov     dword ptr [rsp+0E0h+var_B0], 9DDh
0x14003427b  mov     [rsp+0E0h+HandleInformation], r15
0x140034280  mov     rcx, [rcx+40h]
0x140034284  lea     r8d, [r9-39h]
0x140034288  mov     [rsp+0E0h+Object], r12
0x14003428d  call    WPP_RECORDER_SF_sDd
0x140034292  mov     eax, cs:dword_14000E060
0x140034298  cmp     eax, 5
0x14003429b  jbe     loc_14003436C
0x1400342a1  mov     rdx, 400000000000h
0x1400342ab  lea     rcx, dword_14000E060
0x1400342b2  call    _tlgKeywordOn
0x1400342b7  test    al, al
0x1400342b9  jz      loc_14003436C
0x1400342bf  lea     rax, [rbp+57h+var_9F]
0x1400342c3  mov     [rbp+57h+var_9F], 2
0x1400342c7  mov     [rbp+57h+var_60], rax
0x1400342cb  lea     rdx, unk_14000BDF8
0x1400342d2  lea     rax, [rbp+57h+var_A0]
0x1400342d6  mov     [rbp+57h+var_58], 1
0x1400342de  mov     [rbp+57h+var_50], rax
0x1400342e2  lea     rcx, dword_14000E060
0x1400342e9  lea     rax, [rbp+57h+var_9C]
0x1400342ed  mov     [rbp+57h+var_A0], 5
0x1400342f1  mov     [rbp+57h+var_40], rax
0x1400342f5  xor     r9d, r9d
0x1400342f8  lea     rax, [rbp+57h+var_80]
0x1400342fc  mov     [rbp+57h+var_48], 1
0x140034304  mov     [rsp+0E0h+HandleInformation], rax
0x140034309  xor     r8d, r8d
0x14003430c  mov     dword ptr [rsp+0E0h+Object], 5
0x140034314  mov     [rbp+57h+var_9C], esi
0x140034317  mov     [rbp+57h+var_38], 4
0x14003431f  call    _tlgWriteTransfer_EtwWriteTransfer
0x140034324  jmp     short loc_14003436C
0x140034326  mov     rax, [rbp+57h+var_88]
0x14003432a  mov     al, [rax+20h]
0x14003432d  and     al, 24h
0x14003432f  cmp     al, 4
0x140034331  jnz     short loc_140034367
0x140034333  mov     rdx, [r13+20h]; FileObject
0x140034337  lea     r8, [rbp+57h+Context]; Context
0x14003433b  mov     rcx, [r13+18h]; Instance
0x14003433f  call    cs:__imp_FltGetStreamContext
0x140034346  nop     dword ptr [rax+rax+00h]
0x14003434b  test    eax, eax
0x14003434d  js      short loc_140034367
0x14003434f  mov     rax, [rbp+57h+Context]
0x140034353  mov     byte ptr [rax+1Dh], 1
0x140034357  mov     rcx, [rbp+57h+Context]; Context
0x14003435b  call    cs:__imp_FltReleaseContext
0x140034362  nop     dword ptr [rax+rax+00h]
0x140034367  test    rdi, rdi
0x14003436a  jz      short loc_1400343C0
0x14003436c  mov     rcx, [rdi]; FileNameInformation
0x14003436f  test    rcx, rcx
0x140034372  jz      short loc_140034380
0x140034374  call    cs:__imp_FltReleaseFileNameInformation
0x14003437b  nop     dword ptr [rax+rax+00h]
0x140034380  mov     rcx, [rdi+8]; Object
0x140034384  test    rcx, rcx
0x140034387  jz      short loc_140034395
0x140034389  call    cs:__imp_ObfDereferenceObject
0x140034390  nop     dword ptr [rax+rax+00h]
0x140034395  mov     rcx, [rdi+18h]; FileHandle
0x140034399  test    rcx, rcx
0x14003439c  jz      short loc_1400343AA
0x14003439e  call    cs:__imp_FltClose
0x1400343a5  nop     dword ptr [rax+rax+00h]
0x1400343aa  mov     rdx, rdi; Entry
0x1400343ad  lea     rcx, stru_14000E500; Lookaside
0x1400343b4  call    cs:__imp_ExFreeToPagedLookasideList
0x1400343bb  nop     dword ptr [rax+rax+00h]
0x1400343c0  mov     rcx, [rbp+57h+var_90]; Object
0x1400343c4  test    rcx, rcx
0x1400343c7  jz      short loc_1400343D5
0x1400343c9  call    cs:__imp_ObfDereferenceObject
0x1400343d0  nop     dword ptr [rax+rax+00h]
0x1400343d5  xor     eax, eax
0x1400343d7  mov     rcx, [rbp+57h+var_30]
0x1400343db  xor     rcx, rsp; StackCookie
0x1400343de  call    __security_check_cookie
0x1400343e3  lea     r11, [rsp+0E0h+var_20]
0x1400343eb  mov     rbx, [r11+30h]
0x1400343ef  mov     rsi, [r11+48h]
0x1400343f3  mov     rsp, r11
0x1400343f6  pop     r15
0x1400343f8  pop     r13
0x1400343fa  pop     r12
0x1400343fc  pop     rdi
0x1400343fd  pop     rbp
0x1400343fe  retn
```
