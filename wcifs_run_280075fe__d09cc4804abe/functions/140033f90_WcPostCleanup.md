# WcPostCleanup

- ea: `0x140033f90`
- end: `0x1400343b0`
- name: `WcPostCleanup`
- size: `1056`
- prototype: ``
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
- `0x140033f90`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x140034016`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140034016`
- `ntoskrnl!IoFileObjectType` at `0x140033fee`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140034364`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140034364`
- `ntoskrnl!ObfDereferenceObject` at `0x140034339`
- `ntoskrnl!ObfDereferenceObject` at `0x140034379`
- `ntoskrnl!ObfDereferenceObject` at `0x140034339`
- `ntoskrnl!ObfDereferenceObject` at `0x140034379`
- `FLTMGR!FltSetInformationFile` at `0x14003409f`
- `FLTMGR!FltSetInformationFile` at `0x14003409f`
- `FLTMGR!FltClose` at `0x14003434e`
- `FLTMGR!FltClose` at `0x14003434e`
- `FLTMGR!FltGetStreamContext` at `0x1400342ef`
- `FLTMGR!FltGetStreamContext` at `0x1400342ef`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140034324`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140034324`
- `FLTMGR!FltReleaseContext` at `0x14003430b`
- `FLTMGR!FltReleaseContext` at `0x14003430b`

## pseudocode

```c
__int64 __fastcall WcPostCleanup(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rdi
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
  void *v18; // rcx
  void *v19; // rcx
  char v21; // [rsp+30h] [rbp-59h]
  char v22; // [rsp+38h] [rbp-51h]
  char v23; // [rsp+40h] [rbp-49h] BYREF
  char v24; // [rsp+41h] [rbp-48h] BYREF
  char FileInformation[2]; // [rsp+42h] [rbp-47h] BYREF
  int v26; // [rsp+44h] [rbp-45h] BYREF
  PFLT_CONTEXT Context; // [rsp+48h] [rbp-41h] BYREF
  PVOID Object; // [rsp+50h] [rbp-39h] BYREF
  __int64 v29; // [rsp+58h] [rbp-31h]
  struct _EVENT_DATA_DESCRIPTOR v30[2]; // [rsp+60h] [rbp-29h] BYREF
  char *v31; // [rsp+80h] [rbp-9h]
  __int64 v32; // [rsp+88h] [rbp-1h]
  char *v33; // [rsp+90h] [rbp+7h]
  __int64 v34; // [rsp+98h] [rbp+Fh]
  int *v35; // [rsp+A0h] [rbp+17h]
  __int64 v36; // [rsp+A8h] [rbp+1Fh]

  v3 = 0;
  v29 = a1;
  Object = 0;
  FileInformation[0] = 0;
  Context = 0;
  v6 = a1;
  if ( a3 )
  {
    v3 = a3;
    if ( *(_BYTE *)(a3 + 17) )
    {
      v7 = ObReferenceObjectByHandle(*(HANDLE *)(a3 + 24), 0x10000u, (POBJECT_TYPE)IoFileObjectType, 0, &Object, 0);
      if ( v7 >= 0 )
      {
        v10 = *(struct _FLT_INSTANCE **)(a2 + 24);
        FileInformation[0] = 0;
        v11 = FltSetInformationFile(v10, (PFILE_OBJECT)Object, FileInformation, 1u, FileDispositionInformation);
        if ( v11 >= 0 || WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_28;
        v22 = v11;
        v9 = 60;
        v21 = -73;
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
LABEL_28:
          if ( *(_QWORD *)v3 )
            FltReleaseFileNameInformation(*(PFLT_FILE_NAME_INFORMATION *)v3);
          v18 = *(void **)(v3 + 8);
          if ( v18 )
            ObfDereferenceObject(v18);
          v19 = *(void **)(v3 + 24);
          if ( v19 )
            FltClose(v19);
          ExFreeToPagedLookasideList(&stru_14000E500, (PVOID)v3);
          goto LABEL_35;
        }
        v22 = v7;
        v9 = 59;
        v21 = -87;
      }
      LOBYTE(v8) = 2;
      WPP_RECORDER_SF_sDd(
        WPP_GLOBAL_Control->DeviceExtension,
        v8,
        6,
        v9,
        (__int64)WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\wcifs.c",
        v21,
        v22);
      goto LABEL_28;
    }
    if ( (*(_BYTE *)(a1 + 32) & 0xC) != 0 )
    {
      Tombstone = WcCreateTombstone(
                    *(PFLT_INSTANCE *)(a2 + 24),
                    (struct _UNICODE_STRING *)(*(_QWORD *)a3 + 8LL),
                    *(_BYTE *)(a3 + 16));
      v26 = Tombstone;
      if ( Tombstone < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v13) = 2;
          WPP_RECORDER_SF_sDd(
            WPP_GLOBAL_Control->DeviceExtension,
            v13,
            6,
            61,
            (__int64)WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids,
            (__int64)"onecore\\base\\fs\\wci\\wcifs\\wcifs.c",
            201,
            Tombstone);
        }
        if ( (unsigned int)dword_14000E060 > 5 && (unsigned __int8)tlgKeywordOn(&dword_14000E060, 0x400000000000LL) )
        {
          v23 = 1;
          v31 = &v23;
          v32 = 1;
          v33 = &v24;
          v24 = 5;
          v35 = &v26;
          v34 = 1;
          v26 = v14;
          v36 = 4;
          tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_14000E060, (unsigned __int8 *)word_14000BD9A, 0, 0, 5u, v30);
        }
      }
    }
    v15 = WcRemoveInMemoryTombstone(
            *(struct _FLT_INSTANCE **)(a2 + 24),
            *(_QWORD *)a3,
            *(struct _FILE_OBJECT **)(a3 + 8));
    v17 = v15;
    if ( v15 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v16) = 2;
        WPP_RECORDER_SF_sDd(
          WPP_GLOBAL_Control->DeviceExtension,
          v16,
          5,
          62,
          (__int64)WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\wcifs.c",
          221,
          v15);
      }
      if ( (unsigned int)dword_14000E060 > 5 && (unsigned __int8)tlgKeywordOn(&dword_14000E060, 0x400000000000LL) )
      {
        v24 = 2;
        v31 = &v24;
        v32 = 1;
        v33 = &v23;
        v23 = 5;
        v35 = &v26;
        v34 = 1;
        v26 = v17;
        v36 = 4;
        tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_14000E060, (unsigned __int8 *)&unk_14000BDF8, 0, 0, 5u, v30);
      }
      goto LABEL_28;
    }
    v6 = v29;
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
0x140033f90  mov     [rsp-8+arg_0], rbx
0x140033f95  mov     [rsp-8+arg_18], rsi
0x140033f9a  push    rbp
0x140033f9b  push    rdi
0x140033f9c  push    r12
0x140033f9e  push    r13
0x140033fa0  push    r15
0x140033fa2  lea     rbp, [rsp-37h]
0x140033fa7  sub     rsp, 0C0h
0x140033fae  mov     rax, cs:__security_cookie
0x140033fb5  xor     rax, rsp
0x140033fb8  mov     [rbp+57h+var_30], rax
0x140033fbc  xor     edi, edi
0x140033fbe  mov     [rbp+57h+var_88], rcx
0x140033fc2  mov     [rbp+57h+var_90], rdi
0x140033fc6  mov     rsi, r8
0x140033fc9  mov     [rbp+57h+FileInformation], dil
0x140033fcd  mov     r13, rdx
0x140033fd0  mov     [rbp+57h+Context], rdi
0x140033fd4  mov     rax, rcx
0x140033fd7  test    r8, r8
0x140033fda  jz      loc_1400342DA
0x140033fe0  cmp     byte ptr [r8+11h], 0
0x140033fe5  mov     rdi, r8
0x140033fe8  jz      loc_1400340DE
0x140033fee  mov     r8, cs:__imp_IoFileObjectType
0x140033ff5  lea     rax, [rbp+57h+var_90]
0x140033ff9  mov     rcx, [rdi+18h]; Handle
0x140033ffd  xor     r9d, r9d; AccessMode
0x140034000  mov     [rsp+0E0h+HandleInformation], 0; HandleInformation
0x140034009  mov     edx, 10000h; DesiredAccess
0x14003400e  mov     [rsp+0E0h+Object], rax; Object
0x140034013  mov     r8, [r8]; ObjectType
0x140034016  call    cs:__imp_ObReferenceObjectByHandle
0x14003401d  nop     dword ptr [rax+rax+00h]
0x140034022  test    eax, eax
0x140034024  jns     short loc_140034081
0x140034026  lea     rbx, WPP_RECORDER_INITIALIZED
0x14003402d  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140034034  jz      loc_14003431C
0x14003403a  mov     dword ptr [rsp+0E0h+var_A8], eax
0x14003403e  mov     r9d, 3Bh ; ';'
0x140034044  mov     dword ptr [rsp+0E0h+var_B0], 9A9h
0x14003404c  mov     rcx, cs:WPP_GLOBAL_Control
0x140034053  lea     r15, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\wcifs\\wcifs.c"
0x14003405a  lea     r12, WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids
0x140034061  mov     [rsp+0E0h+HandleInformation], r15
0x140034066  mov     r8d, 6
0x14003406c  mov     [rsp+0E0h+Object], r12
0x140034071  mov     dl, 2
0x140034073  mov     rcx, [rcx+40h]
0x140034077  call    WPP_RECORDER_SF_sDd
0x14003407c  jmp     loc_14003431C
0x140034081  mov     rdx, [rbp+57h+var_90]; FileObject
0x140034085  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x140034089  mov     rcx, [r13+18h]; Instance
0x14003408d  mov     r9d, 1; Length
0x140034093  mov     [rbp+57h+FileInformation], 0
0x140034097  mov     dword ptr [rsp+0E0h+Object], 0Dh; FileInformationClass
0x14003409f  call    cs:__imp_FltSetInformationFile
0x1400340a6  nop     dword ptr [rax+rax+00h]
0x1400340ab  test    eax, eax
0x1400340ad  jns     loc_14003431C
0x1400340b3  lea     rbx, WPP_RECORDER_INITIALIZED
0x1400340ba  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400340c1  jz      loc_14003431C
0x1400340c7  mov     dword ptr [rsp+0E0h+var_A8], eax
0x1400340cb  mov     r9d, 3Ch ; '<'
0x1400340d1  mov     dword ptr [rsp+0E0h+var_B0], 9B7h
0x1400340d9  jmp     loc_14003404C
0x1400340de  test    byte ptr [rcx+20h], 0Ch
0x1400340e2  lea     rbx, WPP_RECORDER_INITIALIZED
0x1400340e9  lea     r15, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\wcifs\\wcifs.c"
0x1400340f0  lea     r12, WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids
0x1400340f7  jz      loc_1400341ED
0x1400340fd  mov     rdx, [r8]
0x140034100  mov     r8b, [r8+10h]
0x140034104  add     rdx, 8
0x140034108  mov     rcx, [r13+18h]; Instance
0x14003410c  call    WcCreateTombstone
0x140034111  mov     [rbp+57h+var_9C], eax
0x140034114  mov     r10d, eax
0x140034117  test    eax, eax
0x140034119  jns     loc_1400341ED
0x14003411f  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140034126  jz      short loc_14003415E
0x140034128  mov     rcx, cs:WPP_GLOBAL_Control
0x14003412f  mov     r9d, 3Dh ; '='
0x140034135  mov     dword ptr [rsp+0E0h+var_A8], eax
0x140034139  mov     dl, 2
0x14003413b  mov     dword ptr [rsp+0E0h+var_B0], 9C9h
0x140034143  mov     [rsp+0E0h+HandleInformation], r15
0x140034148  mov     rcx, [rcx+40h]
0x14003414c  lea     r8d, [r9-37h]
0x140034150  mov     [rsp+0E0h+Object], r12
0x140034155  call    WPP_RECORDER_SF_sDd
0x14003415a  mov     r10d, [rbp+57h+var_9C]
0x14003415e  mov     eax, cs:dword_14000E060
0x140034164  cmp     eax, 5
0x140034167  jbe     loc_1400341ED
0x14003416d  mov     rdx, 400000000000h
0x140034177  lea     rcx, dword_14000E060
0x14003417e  call    _tlgKeywordOn
0x140034183  test    al, al
0x140034185  jz      short loc_1400341ED
0x140034187  lea     rax, [rbp+57h+var_A0]
0x14003418b  mov     [rbp+57h+var_A0], 1
0x14003418f  mov     [rbp+57h+var_60], rax
0x140034193  lea     rdx, word_14000BD9A
0x14003419a  lea     rax, [rbp+57h+var_9F]
0x14003419e  mov     [rbp+57h+var_58], 1
0x1400341a6  mov     [rbp+57h+var_50], rax
0x1400341aa  lea     rcx, dword_14000E060
0x1400341b1  lea     rax, [rbp+57h+var_9C]
0x1400341b5  mov     [rbp+57h+var_9F], 5
0x1400341b9  mov     [rbp+57h+var_40], rax
0x1400341bd  xor     r9d, r9d
0x1400341c0  lea     rax, [rbp+57h+var_80]
0x1400341c4  mov     [rbp+57h+var_48], 1
0x1400341cc  mov     [rsp+0E0h+HandleInformation], rax
0x1400341d1  xor     r8d, r8d
0x1400341d4  mov     dword ptr [rsp+0E0h+Object], 5
0x1400341dc  mov     [rbp+57h+var_9C], r10d
0x1400341e0  mov     [rbp+57h+var_38], 4
0x1400341e8  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400341ed  mov     r8, [rsi+8]
0x1400341f1  mov     rdx, [rsi]
0x1400341f4  mov     rcx, [r13+18h]
0x1400341f8  call    WcRemoveInMemoryTombstone
0x1400341fd  mov     esi, eax
0x1400341ff  test    eax, eax
0x140034201  jns     loc_1400342D6
0x140034207  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14003420e  jz      short loc_140034242
0x140034210  mov     rcx, cs:WPP_GLOBAL_Control
0x140034217  mov     r9d, 3Eh ; '>'
0x14003421d  mov     dword ptr [rsp+0E0h+var_A8], eax
0x140034221  mov     dl, 2
0x140034223  mov     dword ptr [rsp+0E0h+var_B0], 9DDh
0x14003422b  mov     [rsp+0E0h+HandleInformation], r15
0x140034230  mov     rcx, [rcx+40h]
0x140034234  lea     r8d, [r9-39h]
0x140034238  mov     [rsp+0E0h+Object], r12
0x14003423d  call    WPP_RECORDER_SF_sDd
0x140034242  mov     eax, cs:dword_14000E060
0x140034248  cmp     eax, 5
0x14003424b  jbe     loc_14003431C
0x140034251  mov     rdx, 400000000000h
0x14003425b  lea     rcx, dword_14000E060
0x140034262  call    _tlgKeywordOn
0x140034267  test    al, al
0x140034269  jz      loc_14003431C
0x14003426f  lea     rax, [rbp+57h+var_9F]
0x140034273  mov     [rbp+57h+var_9F], 2
0x140034277  mov     [rbp+57h+var_60], rax
0x14003427b  lea     rdx, unk_14000BDF8
0x140034282  lea     rax, [rbp+57h+var_A0]
0x140034286  mov     [rbp+57h+var_58], 1
0x14003428e  mov     [rbp+57h+var_50], rax
0x140034292  lea     rcx, dword_14000E060
0x140034299  lea     rax, [rbp+57h+var_9C]
0x14003429d  mov     [rbp+57h+var_A0], 5
0x1400342a1  mov     [rbp+57h+var_40], rax
0x1400342a5  xor     r9d, r9d
0x1400342a8  lea     rax, [rbp+57h+var_80]
0x1400342ac  mov     [rbp+57h+var_48], 1
0x1400342b4  mov     [rsp+0E0h+HandleInformation], rax
0x1400342b9  xor     r8d, r8d
0x1400342bc  mov     dword ptr [rsp+0E0h+Object], 5
0x1400342c4  mov     [rbp+57h+var_9C], esi
0x1400342c7  mov     [rbp+57h+var_38], 4
0x1400342cf  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400342d4  jmp     short loc_14003431C
0x1400342d6  mov     rax, [rbp+57h+var_88]
0x1400342da  mov     al, [rax+20h]
0x1400342dd  and     al, 24h
0x1400342df  cmp     al, 4
0x1400342e1  jnz     short loc_140034317
0x1400342e3  mov     rdx, [r13+20h]; FileObject
0x1400342e7  lea     r8, [rbp+57h+Context]; Context
0x1400342eb  mov     rcx, [r13+18h]; Instance
0x1400342ef  call    cs:__imp_FltGetStreamContext
0x1400342f6  nop     dword ptr [rax+rax+00h]
0x1400342fb  test    eax, eax
0x1400342fd  js      short loc_140034317
0x1400342ff  mov     rax, [rbp+57h+Context]
0x140034303  mov     byte ptr [rax+1Dh], 1
0x140034307  mov     rcx, [rbp+57h+Context]; Context
0x14003430b  call    cs:__imp_FltReleaseContext
0x140034312  nop     dword ptr [rax+rax+00h]
0x140034317  test    rdi, rdi
0x14003431a  jz      short loc_140034370
0x14003431c  mov     rcx, [rdi]; FileNameInformation
0x14003431f  test    rcx, rcx
0x140034322  jz      short loc_140034330
0x140034324  call    cs:__imp_FltReleaseFileNameInformation
0x14003432b  nop     dword ptr [rax+rax+00h]
0x140034330  mov     rcx, [rdi+8]; Object
0x140034334  test    rcx, rcx
0x140034337  jz      short loc_140034345
0x140034339  call    cs:__imp_ObfDereferenceObject
0x140034340  nop     dword ptr [rax+rax+00h]
0x140034345  mov     rcx, [rdi+18h]; FileHandle
0x140034349  test    rcx, rcx
0x14003434c  jz      short loc_14003435A
0x14003434e  call    cs:__imp_FltClose
0x140034355  nop     dword ptr [rax+rax+00h]
0x14003435a  mov     rdx, rdi; Entry
0x14003435d  lea     rcx, stru_14000E500; Lookaside
0x140034364  call    cs:__imp_ExFreeToPagedLookasideList
0x14003436b  nop     dword ptr [rax+rax+00h]
0x140034370  mov     rcx, [rbp+57h+var_90]; Object
0x140034374  test    rcx, rcx
0x140034377  jz      short loc_140034385
0x140034379  call    cs:__imp_ObfDereferenceObject
0x140034380  nop     dword ptr [rax+rax+00h]
0x140034385  xor     eax, eax
0x140034387  mov     rcx, [rbp+57h+var_30]
0x14003438b  xor     rcx, rsp; StackCookie
0x14003438e  call    __security_check_cookie
0x140034393  lea     r11, [rsp+0E0h+var_20]
0x14003439b  mov     rbx, [r11+30h]
0x14003439f  mov     rsi, [r11+48h]
0x1400343a3  mov     rsp, r11
0x1400343a6  pop     r15
0x1400343a8  pop     r13
0x1400343aa  pop     r12
0x1400343ac  pop     rdi
0x1400343ad  pop     rbp
0x1400343ae  retn
```
