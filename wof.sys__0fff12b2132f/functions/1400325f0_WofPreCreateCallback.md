# WofPreCreateCallback

- ea: `0x1400325f0`
- end: `0x1400329b4`
- name: `WofPreCreateCallback`
- size: `964`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1400014d0`
- `0x14000b760`
- `0x140011640`
- `0x1400325f0`

## import_xrefs

- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14003283f`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14003283f`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400326c5`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400326c5`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14003288d`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14003288d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140032805`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003294a`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140032805`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003294a`
- `FLTMGR!FltGetFileNameInformation` at `0x14003290f`
- `FLTMGR!FltGetFileNameInformation` at `0x14003290f`
- `FLTMGR!FltAddOpenReparseEntry` at `0x140032705`
- `FLTMGR!FltAddOpenReparseEntry` at `0x140032705`
- `FLTMGR!FltReleaseContext` at `0x14003265a`
- `FLTMGR!FltReleaseContext` at `0x140032816`
- `FLTMGR!FltReleaseContext` at `0x14003265a`
- `FLTMGR!FltReleaseContext` at `0x140032816`

## pseudocode

```c
__int64 __fastcall WofPreCreateCallback(PFLT_CALLBACK_DATA CallbackData, __int64 a2, _QWORD *a3)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  PFILE_OBJECT TargetFileObject; // r9
  int v7; // r9d
  PFLT_IO_PARAMETER_BLOCK v8; // rdx
  char *v9; // rax
  void *v10; // rbx
  NTSTATUS v11; // esi
  __int64 result; // rax
  UNICODE_STRING *p_FileName; // rsi
  UCHAR OperationFlags; // r15
  USHORT Length; // bx
  BOOLEAN v16; // r15
  unsigned __int16 v17; // bx
  unsigned __int16 v18; // r8
  WCHAR v19; // ax
  struct _FLT_FILE_NAME_INFORMATION *v20; // rcx
  unsigned int i; // ebp
  __int64 v22; // rcx
  unsigned int (__fastcall *v23)(_QWORD, UNICODE_STRING *, _QWORD); // rax
  int FileNameInformation; // eax
  UNICODE_STRING String1; // [rsp+50h] [rbp-48h] BYREF
  UNICODE_STRING String2; // [rsp+60h] [rbp-38h] BYREF
  PFLT_CONTEXT Context; // [rsp+A0h] [rbp+8h] BYREF

  Iopb = CallbackData->Iopb;
  Context = 0;
  TargetFileObject = Iopb->TargetFileObject;
  if ( (!TargetFileObject->FileName.Buffer || !TargetFileObject->FileName.Length)
    && !TargetFileObject->RelatedFileObject
    || (int)WofGetVolumeContext(*(PFLT_INSTANCE *)(a2 + 24), &Context) < 0 )
  {
    return 1;
  }
  if ( (*((_DWORD *)Context + 14) & 1) != 0 )
  {
    FltReleaseContext(Context);
    return 1;
  }
  FltReleaseContext(Context);
  *a3 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qZDlL(
      WPP_GLOBAL_Control->DeviceExtension,
      CallbackData->Iopb->Parameters.Create.Options & 0xFFFFFF,
      CallbackData->Iopb->TargetFileObject,
      v7);
  v8 = CallbackData->Iopb;
  if ( (*(_DWORD *)(v8->Parameters.WMI.ProviderId + 16) & 0xFFEFFF7F) != 0
    || HIBYTE(v8->Parameters.SetVolumeInformation.FsInformationClass) != 1 )
  {
    p_FileName = &v8->TargetFileObject->FileName;
    Context = 0;
    String1 = 0;
    OperationFlags = v8->OperationFlags;
    Length = p_FileName->Length;
    if ( p_FileName->Length )
      goto LABEL_16;
    FileNameInformation = FltGetFileNameInformation(CallbackData, 0x4000102u, (PFLT_FILE_NAME_INFORMATION *)&Context);
    if ( FileNameInformation < 0 )
    {
      CallbackData->IoStatus.Status = FileNameInformation;
      return 4;
    }
    v20 = (struct _FLT_FILE_NAME_INFORMATION *)Context;
    Length = *((_WORD *)Context + 4);
    p_FileName = (UNICODE_STRING *)((char *)Context + 8);
    if ( Length )
    {
LABEL_16:
      v16 = (unsigned __int8)~OperationFlags >> 7;
      v17 = Length >> 1;
      v18 = v17;
      do
      {
        v19 = p_FileName->Buffer[--v17];
        if ( v19 == 92 )
          break;
        if ( v19 == 58 )
        {
          String1.Buffer = &p_FileName->Buffer[v17];
          *(_QWORD *)&String2.Length = 917516;
          String1.MaximumLength = 2 * (v18 - v17);
          String1.Length = String1.MaximumLength;
          String2.Buffer = L":$DATA";
          if ( RtlCompareUnicodeString(&String1, &String2, v16) )
          {
            for ( i = 0; i < 4; ++i )
            {
              v22 = 424LL * i;
              if ( *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v22) )
              {
                v23 = *(unsigned int (__fastcall **)(_QWORD, UNICODE_STRING *, _QWORD))((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels
                                                                                      + v22
                                                                                      + 136);
                if ( v23 )
                {
                  if ( v23(0, &String1, v16) == -1073741275 )
                  {
                    if ( Context )
                      FltReleaseFileNameInformation((PFLT_FILE_NAME_INFORMATION)Context);
                    CallbackData->IoStatus.Status = -1073741790;
                    return 4;
                  }
                }
              }
            }
          }
          v18 = v17;
        }
      }
      while ( v17 );
      v20 = (struct _FLT_FILE_NAME_INFORMATION *)Context;
    }
    if ( v20 )
      FltReleaseFileNameInformation(v20);
  }
  v9 = (char *)ExAllocateFromPagedLookasideList(&Lookaside);
  v10 = v9;
  if ( v9 )
  {
    *((_QWORD *)v9 + 1) = v9;
    *(_QWORD *)v9 = v9;
    *((_DWORD *)v9 + 4) = FileTag;
    *((_DWORD *)v9 + 5) = 0;
    *(_OWORD *)(v9 + 24) = 0;
    v11 = FltAddOpenReparseEntry(WofGlobal, CallbackData, v9);
    if ( v11 < 0 )
    {
      ExFreeToPagedLookasideList(&Lookaside, v10);
      result = 4;
      CallbackData->IoStatus.Status = v11;
    }
    else
    {
      *a3 = v10;
      return 5;
    }
  }
  else
  {
    CallbackData->IoStatus.Status = -1073741670;
    return 4;
  }
  return result;
}

```

## disassembly

```asm
0x1400325f0  push    rdi
0x1400325f2  push    r12
0x1400325f4  push    r14
0x1400325f6  sub     rsp, 80h
0x1400325fd  mov     rax, [rcx+10h]
0x140032601  xor     r12d, r12d
0x140032604  mov     r14, r8
0x140032607  mov     [rsp+98h+Context], r12
0x14003260f  mov     r10, rdx
0x140032612  mov     rdi, rcx
0x140032615  mov     r9, [rax+8]
0x140032619  cmp     [r9+60h], r12
0x14003261d  jz      loc_140032753
0x140032623  cmp     [r9+58h], r12w
0x140032628  jz      loc_140032753
0x14003262e  mov     rcx, [r10+18h]; Instance
0x140032632  lea     rdx, [rsp+98h+Context]
0x14003263a  call    WofGetVolumeContext
0x14003263f  test    eax, eax
0x140032641  js      loc_140032822
0x140032647  mov     rcx, [rsp+98h+Context]; Context
0x14003264f  mov     eax, [rcx+38h]
0x140032652  test    al, 1
0x140032654  jnz     loc_140032816
0x14003265a  call    cs:__imp_FltReleaseContext
0x140032661  nop     dword ptr [rax+rax+00h]
0x140032666  mov     [r14], r12
0x140032669  lea     rax, WPP_RECORDER_INITIALIZED
0x140032670  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140032677  jnz     loc_140032974
0x14003267d  mov     rdx, [rdi+10h]
0x140032681  mov     [rsp+98h+arg_8], rbx
0x140032689  mov     [rsp+98h+arg_10], rbp
0x140032691  mov     [rsp+98h+arg_18], rsi
0x140032699  mov     rax, [rdx+18h]
0x14003269d  mov     [rsp+98h+var_20], r13
0x1400326a2  mov     [rsp+98h+var_28], r15
0x1400326a7  test    dword ptr [rax+10h], 0FFEFFF7Fh
0x1400326ae  jnz     loc_140032770
0x1400326b4  cmp     byte ptr [rdx+23h], 1
0x1400326b8  jnz     loc_140032770
0x1400326be  lea     rcx, Lookaside; Lookaside
0x1400326c5  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1400326cc  nop     dword ptr [rax+rax+00h]
0x1400326d1  mov     rbx, rax
0x1400326d4  test    rax, rax
0x1400326d7  jz      loc_140032762
0x1400326dd  mov     [rax+8], rax
0x1400326e1  xorps   xmm0, xmm0
0x1400326e4  mov     [rax], rax
0x1400326e7  mov     r8, rbx
0x1400326ea  mov     eax, cs:FileTag
0x1400326f0  mov     rdx, rdi
0x1400326f3  mov     [rbx+10h], eax
0x1400326f6  mov     [rbx+14h], r12d
0x1400326fa  movups  xmmword ptr [rbx+18h], xmm0
0x1400326fe  mov     rcx, cs:WofGlobal
0x140032705  call    cs:__imp_FltAddOpenReparseEntry
0x14003270c  nop     dword ptr [rax+rax+00h]
0x140032711  mov     esi, eax
0x140032713  test    eax, eax
0x140032715  js      loc_140032835
0x14003271b  mov     [r14], rbx
0x14003271e  mov     eax, 5
0x140032723  mov     r13, [rsp+98h+var_20]
0x140032728  mov     rsi, [rsp+98h+arg_18]
0x140032730  mov     rbp, [rsp+98h+arg_10]
0x140032738  mov     rbx, [rsp+98h+arg_8]
0x140032740  mov     r15, [rsp+98h+var_28]
0x140032745  add     rsp, 80h
0x14003274c  pop     r14
0x14003274e  pop     r12
0x140032750  pop     rdi
0x140032751  retn
0x140032753  cmp     [r9+40h], r12
0x140032757  jnz     loc_14003262E
0x14003275d  jmp     loc_140032822
0x140032762  mov     dword ptr [rdi+18h], 0C000009Ah
0x140032769  mov     eax, 4
0x14003276e  jmp     short loc_140032723
0x140032770  mov     rsi, [rdx+8]
0x140032774  mov     rcx, r12
0x140032777  add     rsi, 58h ; 'X'
0x14003277b  mov     [rsp+98h+Context], rcx
0x140032783  xorps   xmm0, xmm0
0x140032786  movups  xmmword ptr [rsp+98h+String1.Length], xmm0
0x14003278b  movzx   r15d, byte ptr [rdx+6]
0x140032790  movzx   ebx, word ptr [rsi]
0x140032793  test    bx, bx
0x140032796  jz      loc_1400328FF
0x14003279c  not     r15b
0x14003279f  lea     r9, aData_0; ":$DATA"
0x1400327a6  shr     r15b, 7
0x1400327aa  mov     r13d, 0FFFFh
0x1400327b0  shr     bx, 1
0x1400327b3  mov     r10d, 0Ch
0x1400327b9  movzx   r8d, bx
0x1400327bd  mov     r11d, 0Eh
0x1400327c3  nop     dword ptr [rax+00h]
0x1400327c7  nop     word ptr [rax+rax+00000000h]
0x1400327d0  mov     rax, [rsi+8]
0x1400327d4  add     bx, r13w
0x1400327d8  movzx   ecx, bx
0x1400327db  lea     rdx, [rax+rcx*2]
0x1400327df  movzx   eax, word ptr [rax+rcx*2]
0x1400327e3  cmp     ax, 5Ch ; '\'
0x1400327e7  jz      short loc_1400327F4
0x1400327e9  cmp     ax, 3Ah ; ':'
0x1400327ed  jz      short loc_140032858
0x1400327ef  test    bx, bx
0x1400327f2  jnz     short loc_1400327D0
0x1400327f4  mov     rcx, [rsp+98h+Context]; FileNameInformation
0x1400327fc  test    rcx, rcx
0x1400327ff  jz      loc_1400326BE
0x140032805  call    cs:__imp_FltReleaseFileNameInformation
0x14003280c  nop     dword ptr [rax+rax+00h]
0x140032811  jmp     loc_1400326BE
0x140032816  call    cs:__imp_FltReleaseContext
0x14003281d  nop     dword ptr [rax+rax+00h]
0x140032822  mov     eax, 1
0x140032827  add     rsp, 80h
0x14003282e  pop     r14
0x140032830  pop     r12
0x140032832  pop     rdi
0x140032833  retn
0x140032835  mov     rdx, rbx; Entry
0x140032838  lea     rcx, Lookaside; Lookaside
0x14003283f  call    cs:__imp_ExFreeToPagedLookasideList
0x140032846  nop     dword ptr [rax+rax+00h]
0x14003284b  mov     eax, 4
0x140032850  mov     [rdi+18h], esi
0x140032853  jmp     loc_140032723
0x140032858  sub     r8w, bx
0x14003285c  mov     [rsp+98h+String1.Buffer], rdx
0x140032861  add     r8w, r8w
0x140032865  mov     qword ptr [rsp+98h+String2.Length], 0E000Ch
0x14003286e  mov     [rsp+98h+String1.MaximumLength], r8w
0x140032874  lea     rdx, [rsp+98h+String2]; String2
0x140032879  mov     [rsp+98h+String1.Length], r8w
0x14003287f  lea     rcx, [rsp+98h+String1]; String1
0x140032884  movzx   r8d, r15b; CaseInSensitive
0x140032888  mov     [rsp+98h+String2.Buffer], r9
0x14003288d  call    cs:__imp_RtlCompareUnicodeString
0x140032894  nop     dword ptr [rax+rax+00h]
0x140032899  test    eax, eax
0x14003289b  jz      short loc_1400328E3
0x14003289d  mov     ebp, r12d
0x1400328a0  cmp     ebp, 4
0x1400328a3  jnb     short loc_1400328E3
0x1400328a5  mov     eax, ebp
0x1400328a7  imul    rcx, rax, 1A8h
0x1400328ae  lea     rax, WPP_MAIN_CB.Queue+10h
0x1400328b5  cmp     [rcx+rax], r12b
0x1400328b9  jz      short loc_1400328DF
0x1400328bb  mov     rax, [rcx+rax+88h]
0x1400328c3  test    rax, rax
0x1400328c6  jz      short loc_1400328DF
0x1400328c8  movzx   r8d, r15b
0x1400328cc  lea     rdx, [rsp+98h+String1]
0x1400328d1  xor     ecx, ecx
0x1400328d3  call    _guard_dispatch_icall
0x1400328d8  cmp     eax, 0C0000225h
0x1400328dd  jz      short loc_14003293D
0x1400328df  inc     ebp
0x1400328e1  jmp     short loc_1400328A0
0x1400328e3  movzx   r8d, bx
0x1400328e7  lea     r9, aData_0; ":$DATA"
0x1400328ee  mov     r10d, 0Ch
0x1400328f4  mov     r11d, 0Eh
0x1400328fa  jmp     loc_1400327EF
0x1400328ff  lea     r8, [rsp+98h+Context]; FileNameInformation
0x140032907  mov     edx, 4000102h; NameOptions
0x14003290c  mov     rcx, rdi; CallbackData
0x14003290f  call    cs:__imp_FltGetFileNameInformation
0x140032916  nop     dword ptr [rax+rax+00h]
0x14003291b  test    eax, eax
0x14003291d  js      short loc_140032967
0x14003291f  mov     rcx, [rsp+98h+Context]
0x140032927  movzx   ebx, word ptr [rcx+8]
0x14003292b  lea     rsi, [rcx+8]
0x14003292f  test    bx, bx
0x140032932  jz      loc_1400327FC
0x140032938  jmp     loc_14003279C
0x14003293d  mov     rcx, [rsp+98h+Context]; FileNameInformation
0x140032945  test    rcx, rcx
0x140032948  jz      short loc_140032956
0x14003294a  call    cs:__imp_FltReleaseFileNameInformation
0x140032951  nop     dword ptr [rax+rax+00h]
0x140032956  mov     dword ptr [rdi+18h], 0C0000022h
0x14003295d  mov     eax, 4
0x140032962  jmp     loc_140032723
0x140032967  mov     [rdi+18h], eax
0x14003296a  mov     eax, 4
0x14003296f  jmp     loc_140032723
0x140032974  mov     rax, [rdi+10h]
0x140032978  movzx   ecx, byte ptr [rax+23h]
0x14003297c  mov     r8, [rax+8]
0x140032980  mov     edx, [rax+20h]
0x140032983  mov     [rsp+98h+var_58], ecx
0x140032987  and     edx, 0FFFFFFh
0x14003298d  mov     rcx, cs:WPP_GLOBAL_Control
0x140032994  mov     [rsp+98h+var_60], edx
0x140032998  lea     rax, [r8+58h]
0x14003299c  mov     [rsp+98h+var_68], rax
0x1400329a1  mov     [rsp+98h+var_70], r8
0x1400329a6  mov     rcx, [rcx+40h]
0x1400329aa  call    WPP_RECORDER_SF_qZDlL
0x1400329af  jmp     loc_14003267D
```
