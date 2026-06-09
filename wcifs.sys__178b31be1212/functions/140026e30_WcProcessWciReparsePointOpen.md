# WcProcessWciReparsePointOpen

- ea: `0x140026e30`
- end: `0x140027770`
- name: `WcProcessWciReparsePointOpen`
- size: `2368`
- prototype: `__int64 __fastcall(struct _FLT_CALLBACK_DATA *, void *, struct _FILE_OBJECT *)`
- caller_count: `1`
- callee_count: `20`
- tags: `reparse_path, loader_planting`

## callers

- `0x140025270`

## callees

- `0x140001008`
- `0x140001030`
- `0x1400016f0`
- `0x140001b94`
- `0x140001bc8`
- `0x140001bf8`
- `0x1400020c4`
- `0x140002294`
- `0x1400024fc`
- `0x140004198`
- `0x1400048a4`
- `0x140004f40`
- `0x1400053f8`
- `0x140007c60`
- `0x140014008`
- `0x1400148bc`
- `0x140026e30`
- `0x14002898c`
- `0x140029658`
- `0x14002eea4`

## import_xrefs

- `ntoskrnl!IoSetShadowFileInformation` at `0x140027184`
- `ntoskrnl!IoSetShadowFileInformation` at `0x14002723c`
- `ntoskrnl!IoSetShadowFileInformation` at `0x140027184`
- `ntoskrnl!IoSetShadowFileInformation` at `0x14002723c`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400272fc`
- `ntoskrnl!ExAcquireFastMutex` at `0x140027585`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400272fc`
- `ntoskrnl!ExAcquireFastMutex` at `0x140027585`
- `ntoskrnl!ExReleaseFastMutex` at `0x140027563`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002759d`
- `ntoskrnl!ExReleaseFastMutex` at `0x140027563`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002759d`
- `FLTMGR!FltFlushBuffers2` at `0x1400275fc`
- `FLTMGR!FltFlushBuffers2` at `0x1400275fc`
- `FLTMGR!FltQueryInformationFile` at `0x140026f40`
- `FLTMGR!FltQueryInformationFile` at `0x140026f40`
- `FLTMGR!FltReleaseContext` at `0x14002771d`
- `FLTMGR!FltReleaseContext` at `0x140027731`
- `FLTMGR!FltReleaseContext` at `0x14002771d`
- `FLTMGR!FltReleaseContext` at `0x140027731`

## string_xrefs

- `0x140026f7c`: `onecore\base\fs\wci\wcifs\create.c`
- `0x1400271aa`: `onecore\base\fs\wci\wcifs\create.c`
- `0x14002725e`: `onecore\base\fs\wci\wcifs\create.c`
- `0x1400272b0`: `onecore\base\fs\wci\wcifs\create.c`
- `0x14002737e`: `onecore\base\fs\wci\wcifs\create.c`
- `0x140027465`: `onecore\base\fs\wci\wcifs\create.c`
- `0x1400274d0`: `onecore\base\fs\wci\wcifs\create.c`
- `0x140027533`: `onecore\base\fs\wci\wcifs\create.c`
- `0x140027652`: `onecore\base\fs\wci\wcifs\create.c`
- `0x1400276d7`: `onecore\base\fs\wci\wcifs\create.c`

## pseudocode

```c
__int64 __fastcall WcProcessWciReparsePointOpen(struct _FLT_CALLBACK_DATA *a1, void *a2, struct _FILE_OBJECT *a3)
{
  PVOID FsContext; // rcx
  PFLT_IO_PARAMETER_BLOCK Iopb; // rcx
  ULONG Options; // edi
  int v9; // r14d
  NTSTATUS v10; // eax
  int SetContextFileObject; // ebx
  int v12; // edx
  int v13; // r8d
  int v14; // r9d
  ULONG_PTR Information; // rax
  __int64 v16; // rcx
  PFAST_MUTEX v17; // rsi
  int v18; // eax
  PFLT_CONTEXT v19; // rdi
  bool v20; // zf
  ULONG_PTR v21; // rax
  int v22; // edx
  int v23; // r9d
  int v24; // edx
  __int64 v25; // rcx
  int v26; // eax
  int v27; // eax
  int v28; // edx
  int v29; // r9d
  int v30; // eax
  int v31; // eax
  int v32; // edx
  char v33; // cl
  PFAST_MUTEX *v34; // rcx
  struct _FILE_OBJECT *v35; // r8
  PFLT_CALLBACK_DATA v36; // r15
  _QWORD *Source; // r14
  int v38; // eax
  int v39; // edx
  int FileInformationClass; // [rsp+20h] [rbp-E0h]
  int FileInformationClassa; // [rsp+20h] [rbp-E0h]
  int LengthReturned; // [rsp+28h] [rbp-D8h]
  int v44; // [rsp+30h] [rbp-D0h]
  char v45; // [rsp+30h] [rbp-D0h]
  char v46; // [rsp+30h] [rbp-D0h]
  char v47; // [rsp+40h] [rbp-C0h]
  bool v48; // [rsp+50h] [rbp-B0h]
  PFLT_CONTEXT Context; // [rsp+58h] [rbp-A8h] BYREF
  PVOID FltObject; // [rsp+60h] [rbp-A0h]
  USHORT ShareAccess; // [rsp+68h] [rbp-98h]
  PFLT_CALLBACK_DATA CallbackData; // [rsp+70h] [rbp-90h]
  PFAST_MUTEX FastMutex; // [rsp+78h] [rbp-88h] BYREF
  __int128 v54; // [rsp+80h] [rbp-80h] BYREF
  int v55; // [rsp+90h] [rbp-70h] BYREF
  int v56; // [rsp+94h] [rbp-6Ch] BYREF
  int v57; // [rsp+98h] [rbp-68h] BYREF
  PVOID v58; // [rsp+A0h] [rbp-60h]
  __int64 UnionContext; // [rsp+A8h] [rbp-58h]
  __int128 FileInformation; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v61; // [rsp+C0h] [rbp-40h]
  char v62[32]; // [rsp+D0h] [rbp-30h] BYREF
  int *v63; // [rsp+F0h] [rbp-10h]
  __int64 v64; // [rsp+F8h] [rbp-8h]
  int *v65; // [rsp+100h] [rbp+0h]
  __int64 v66; // [rsp+108h] [rbp+8h]
  int *v67; // [rsp+110h] [rbp+10h]
  __int64 v68; // [rsp+118h] [rbp+18h]

  CallbackData = a1;
  v61 = 0;
  FltObject = a2;
  FsContext = a3->FsContext;
  FileInformation = 0;
  v58 = FsContext;
  Iopb = a1->Iopb;
  v54 = 0;
  Context = 0;
  FastMutex = 0;
  Options = Iopb->Parameters.Create.Options;
  v9 = *(_DWORD *)(Iopb->Parameters.WMI.ProviderId + 16);
  ShareAccess = Iopb->Parameters.Create.ShareAccess;
  v48 = ((ShareAccess - 1) & 0xFFFB) == 0
     && (v9 == 32
      || (unsigned int)(v9 - 1048608) <= 1
      || v9 == 1048737
      || v9 == 1179680
      || v9 == 1179817
      || v9 == 1179808);
  UnionContext = WcGetUnionContext(a1, a2, a3);
  if ( !UnionContext )
  {
    if ( (Options & 0x41) != 0 )
    {
      SetContextFileObject = 0;
      if ( (Options & 0x40) == 0 )
        return (unsigned int)SetContextFileObject;
    }
    else
    {
      v10 = FltQueryInformationFile((PFLT_INSTANCE)a2, a3, &FileInformation, 0x18u, FileStandardInformation, 0);
      SetContextFileObject = v10;
      if ( v10 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_sDqd(
            wil_details_featureDescriptors_a->DeviceExtension,
            2,
            5,
            19,
            (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
            (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
            113,
            (char)a3,
            v10);
        return (unsigned int)-1073741790;
      }
      if ( BYTE5(v61) )
        return (unsigned int)SetContextFileObject;
    }
    return 260;
  }
  SetContextFileObject = WcGetSetContextFileObject(
                           (PFLT_INSTANCE)a2,
                           a3,
                           FileInformationClass,
                           (__int64)&Context,
                           (__int64)&FastMutex);
  if ( (a1->Iopb->OperationFlags & 2) != 0 )
  {
    Information = a1->IoStatus.Information;
    if ( !Information || (v14 = 0, Information == 3) )
      v14 = 1;
    if ( (unsigned int)dword_14000E060 > 5 && (unsigned __int8)tlgKeywordOn(&dword_14000E060, 0x400000000000LL) )
    {
      v56 = v14;
      v63 = &v55;
      v55 = SetContextFileObject;
      v65 = &v56;
      v64 = 4;
      v66 = 4;
      v68 = 4;
      v57 = *(_DWORD *)(UnionContext + 56);
      v67 = &v57;
      tlgWriteTransfer_EtwWriteTransfer(v16, &unk_14000B4A0, 0, 0, 5, v62);
    }
  }
  v17 = FastMutex;
  v18 = 0;
  if ( SetContextFileObject < 0 )
  {
    if ( SetContextFileObject == -1073741195 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_sDq(
          wil_details_featureDescriptors_a->DeviceExtension,
          v12,
          v13,
          v14,
          FileInformationClassa,
          LengthReturned,
          v44,
          (char)a3);
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_sDd(
        wil_details_featureDescriptors_a->DeviceExtension,
        v12,
        5,
        21,
        (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
        195,
        SetContextFileObject);
    }
    goto LABEL_105;
  }
  if ( SetContextFileObject == 260 )
    goto LABEL_33;
  v19 = Context;
  if ( (unsigned __int8)WcIsPlaceHolderDirectory(Context, FastMutex) )
  {
    v20 = (v9 & 0x106) == 0;
    goto LABEL_31;
  }
  if ( (unsigned __int8)WcIsPlaceHolderStream(v19, v17) )
  {
    v21 = CallbackData->IoStatus.Information;
    if ( v21 == 3 || !v21 )
    {
      SetContextFileObject = WcExpandAndWait(CallbackData, FltObject, a3, 1, 19);
      if ( SetContextFileObject < 0 )
        goto LABEL_105;
      if ( *(&v17->Contention + 1) == 1 )
      {
        SetContextFileObject = IoSetShadowFileInformation(a3, 0, 0);
        if ( SetContextFileObject < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_53;
          LOBYTE(v22) = 3;
          WPP_RECORDER_SF_sD(
            wil_details_featureDescriptors_a->DeviceExtension,
            v22,
            5,
            22,
            (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
            (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
            244);
        }
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v23 = 23;
          v45 = -9;
          goto LABEL_52;
        }
      }
    }
    else if ( (v9 & 6) != 0 )
    {
      SetContextFileObject = WcExpandAndWait(CallbackData, FltObject, a3, 1, 16);
      if ( SetContextFileObject < 0 )
        goto LABEL_105;
      if ( *(&v17->Contention + 1) == 1 )
      {
        SetContextFileObject = IoSetShadowFileInformation(a3, 0, 0);
        if ( SetContextFileObject < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_53;
          LOBYTE(v22) = 3;
          WPP_RECORDER_SF_sD(
            wil_details_featureDescriptors_a->DeviceExtension,
            v22,
            5,
            24,
            (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
            (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
            16);
        }
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v23 = 25;
          v45 = 19;
LABEL_52:
          LOBYTE(v22) = 3;
          WPP_RECORDER_SF_sD(
            wil_details_featureDescriptors_a->DeviceExtension,
            v22,
            5,
            v23,
            (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
            (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
            v45);
        }
      }
    }
LABEL_53:
    if ( !(unsigned __int8)WcIsPlaceHolderStream(Context, v17) )
      goto LABEL_105;
    FastMutex = (PFAST_MUTEX)((char *)Context + 8);
    ExAcquireFastMutex((PFAST_MUTEX)((char *)Context + 8));
    v25 = *((_QWORD *)Context + 8);
    *((_QWORD *)&v54 + 1) = v25 + 34;
    LOWORD(v54) = *(_WORD *)(v25 + 32);
    WORD1(v54) = *(_WORD *)(v25 + 32);
    v26 = *(&v17->Contention + 1);
    if ( v26 == 2 )
    {
      if ( !v48 )
        goto LABEL_84;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
        && LOWORD(wil_details_featureDescriptors_a->DeviceType) )
      {
        LOBYTE(v24) = 5;
        WPP_RECORDER_SF_sDZ(
          WcVerboseRecorder,
          v24,
          5,
          29,
          (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
          171,
          (__int64)&v54);
      }
      v31 = WcCopySectionObjectPointers(FltObject, a3);
      SetContextFileObject = v31;
      if ( v31 >= 0 )
        goto LABEL_84;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v32) = 3;
        WPP_RECORDER_SF_sDZd(
          wil_details_featureDescriptors_a->DeviceExtension,
          v32,
          5,
          30,
          (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
          180,
          (__int64)&v54,
          v31);
      }
      goto LABEL_83;
    }
    if ( v48 )
    {
      v27 = WcCopySectionObjectPointers(FltObject, a3);
      SetContextFileObject = v27;
      if ( v27 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
LABEL_60:
          *(&v17->Contention + 1) = 2;
LABEL_83:
          SetContextFileObject = 0;
          goto LABEL_84;
        }
        v47 = v27;
        v29 = 26;
        v46 = 91;
LABEL_59:
        LOBYTE(v28) = 3;
        WPP_RECORDER_SF_sDZd(
          wil_details_featureDescriptors_a->DeviceExtension,
          v28,
          5,
          v29,
          (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
          v46,
          (__int64)&v54,
          v47);
        goto LABEL_60;
      }
      *(&v17->Contention + 1) = 1;
    }
    else
    {
      if ( v26 != 1 || (v9 & 0xFFEDFF76) != 0 || (v9 & 1) != 0 && (ShareAccess & 2) != 0 )
      {
        if ( (v9 & 0xFFEFFF77) != 0 )
        {
          if ( v26 == 1 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v24) = 3;
            WPP_RECORDER_SF_sDZ(
              wil_details_featureDescriptors_a->DeviceExtension,
              v24,
              5,
              28,
              (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
              (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
              151,
              (__int64)&v54);
          }
          *(&v17->Contention + 1) = 2;
        }
        goto LABEL_84;
      }
      v30 = WcCopySectionObjectPointers(FltObject, a3);
      SetContextFileObject = v30;
      if ( v30 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_60;
        v47 = v30;
        v29 = 27;
        v46 = 0x80;
        goto LABEL_59;
      }
    }
LABEL_84:
    ExReleaseFastMutex(FastMutex);
    v33 = *((_BYTE *)v58 + 6);
    if ( (v33 & 4) != 0 )
    {
      if ( (*((_BYTE *)v58 + 4) & 0x40) != 0 )
      {
        ExAcquireFastMutex(*((PFAST_MUTEX *)v58 + 6));
        v34 = (PFAST_MUTEX *)v58;
        *((_BYTE *)v58 + 6) &= ~4u;
        ExReleaseFastMutex(v34[6]);
      }
      else
      {
        *((_BYTE *)v58 + 6) = v33 & 0xFB;
      }
    }
    if ( (v9 & 0x100) != 0 )
    {
      v35 = a3;
      v36 = CallbackData;
      SetContextFileObject = WcSetPlaceHolderFlagsSynchronized(CallbackData, FltObject, v35);
    }
    else
    {
      v36 = CallbackData;
    }
    if ( (v17->Contention & 1) == 0 )
    {
      Source = (_QWORD *)WcGetSource(v17);
      v38 = FltFlushBuffers2(*Source, Source[2], 2, v36);
      SetContextFileObject = v38;
      if ( v38 >= 0 )
      {
        _InterlockedOr((volatile signed __int32 *)&v17->Contention, 1u);
      }
      else if ( v38 == -1073741662 || v38 == -1073741790 && (*(_DWORD *)(Source[4] + 16LL) & 1) != 0 )
      {
        SetContextFileObject = 0;
      }
      else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v39) = 2;
        WPP_RECORDER_SF_sDZd(
          wil_details_featureDescriptors_a->DeviceExtension,
          v39,
          5,
          31,
          (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
          15,
          (__int64)&v54,
          v38);
      }
    }
    goto LABEL_105;
  }
  if ( !(unsigned __int8)WcIsPlaceHolder(Context) )
    goto LABEL_53;
  v20 = (v9 & 0x116) == 0;
LABEL_31:
  if ( !v20 )
  {
    v18 = WcSetPlaceHolderFlagsSynchronized(CallbackData, FltObject, a3);
LABEL_33:
    SetContextFileObject = v18;
  }
LABEL_105:
  if ( Context )
    FltReleaseContext(Context);
  if ( v17 )
    FltReleaseContext(v17);
  WcReleaseUnionContext(UnionContext);
  return (unsigned int)SetContextFileObject;
}

```

## disassembly

```asm
0x140026e30  mov     [rsp-8+arg_18], rbx
0x140026e35  push    rbp
0x140026e36  push    rsi
0x140026e37  push    rdi
0x140026e38  push    r12
0x140026e3a  push    r13
0x140026e3c  push    r14
0x140026e3e  push    r15
0x140026e40  lea     rbp, [rsp-30h]
0x140026e45  sub     rsp, 130h
0x140026e4c  mov     rax, cs:__security_cookie
0x140026e53  xor     rax, rsp
0x140026e56  mov     [rbp+60h+var_40], rax
0x140026e5a  xor     eax, eax
0x140026e5c  mov     [rsp+160h+CallbackData], rcx
0x140026e61  mov     [rbp+60h+var_A0], rax
0x140026e65  xor     r13d, r13d
0x140026e68  mov     rsi, rcx
0x140026e6b  mov     [rsp+160h+FltObject], rdx
0x140026e70  mov     rcx, [r8+18h]
0x140026e74  xorps   xmm0, xmm0
0x140026e77  movups  [rbp+60h+FileInformation], xmm0
0x140026e7b  mov     [rbp+60h+var_C0], rcx
0x140026e7f  mov     rbx, rdx
0x140026e82  mov     rcx, [rsi+10h]
0x140026e86  lea     edx, [r13+1]
0x140026e8a  movups  [rbp+60h+var_E0], xmm0
0x140026e8e  mov     r15, r8
0x140026e91  mov     [rsp+160h+Context], r13
0x140026e96  mov     [rsp+160h+FastMutex], r13
0x140026e9b  mov     rax, [rcx+18h]
0x140026e9f  mov     edi, [rcx+20h]
0x140026ea2  mov     r14d, [rax+10h]
0x140026ea6  movzx   eax, word ptr [rcx+2Ah]
0x140026eaa  mov     ecx, 0FFFBh
0x140026eaf  mov     [rsp+160h+var_F8], ax
0x140026eb4  sub     ax, dx
0x140026eb7  test    cx, ax
0x140026eba  jnz     short loc_140026EF7
0x140026ebc  cmp     r14d, 20h ; ' '
0x140026ec0  jz      short loc_140026EF1
0x140026ec2  lea     eax, [r14-100020h]
0x140026ec9  cmp     eax, edx
0x140026ecb  jbe     short loc_140026EF1
0x140026ecd  cmp     r14d, 1000A1h
0x140026ed4  jz      short loc_140026EF1
0x140026ed6  cmp     r14d, 120020h
0x140026edd  jz      short loc_140026EF1
0x140026edf  cmp     r14d, 1200A9h
0x140026ee6  jz      short loc_140026EF1
0x140026ee8  cmp     r14d, 1200A0h
0x140026eef  jnz     short loc_140026EF7
0x140026ef1  mov     [rsp+160h+var_110], dl
0x140026ef5  jmp     short loc_140026EFC
0x140026ef7  mov     [rsp+160h+var_110], r13b
0x140026efc  mov     rdx, rbx
0x140026eff  mov     rcx, rsi
0x140026f02  call    WcGetUnionContext
0x140026f07  mov     r9d, edi
0x140026f0a  mov     [rbp+60h+var_B8], rax
0x140026f0e  and     r9d, 41h
0x140026f12  test    rax, rax
0x140026f15  jnz     loc_140026FD5
0x140026f1b  test    r9d, r9d
0x140026f1e  jnz     loc_140026FC6
0x140026f24  lea     r12d, [rax+5]
0x140026f28  mov     [rsp+160h+LengthReturned], r13; LengthReturned
0x140026f2d  lea     r9d, [rax+18h]; Length
0x140026f31  mov     [rsp+160h+FileInformationClass], r12d; FileInformationClass
0x140026f36  lea     r8, [rbp+60h+FileInformation]; FileInformation
0x140026f3a  mov     rdx, r15; FileObject
0x140026f3d  mov     rcx, rbx; Instance
0x140026f40  call    cs:__imp_FltQueryInformationFile
0x140026f47  nop     dword ptr [rax+rax+00h]
0x140026f4c  mov     ebx, eax
0x140026f4e  test    eax, eax
0x140026f50  jns     short loc_140026FB2
0x140026f52  lea     rdi, WPP_RECORDER_INITIALIZED
0x140026f59  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140026f60  jz      short loc_140026FA8
0x140026f62  mov     rcx, cs:wil_details_featureDescriptors_a
0x140026f69  lea     r9d, [r12+0Eh]
0x140026f6e  mov     dword ptr [rsp+160h+var_120], eax
0x140026f72  lea     edx, [r12-3]
0x140026f77  mov     [rsp+160h+var_128], r15
0x140026f7c  lea     rax, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x140026f83  mov     dword ptr [rsp+160h+var_130], 271h
0x140026f8b  mov     r8d, r12d
0x140026f8e  mov     rcx, [rcx+40h]
0x140026f92  mov     [rsp+160h+LengthReturned], rax
0x140026f97  lea     rax, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x140026f9e  mov     qword ptr [rsp+160h+FileInformationClass], rax
0x140026fa3  call    WPP_RECORDER_SF_sDqd
0x140026fa8  mov     ebx, 0C0000022h
0x140026fad  jmp     loc_140027746
0x140026fb2  cmp     byte ptr [rbp+60h+var_A0+5], r13b
0x140026fb6  jnz     loc_140027746
0x140026fbc  mov     ebx, 104h
0x140026fc1  jmp     loc_140027746
0x140026fc6  mov     ebx, r13d
0x140026fc9  test    dil, 40h
0x140026fcd  jz      loc_140027746
0x140026fd3  jmp     short loc_140026FBC
0x140026fd5  lea     rcx, [rsp+160h+FastMutex]
0x140026fda  mov     r8, rax
0x140026fdd  mov     [rsp+160h+var_130], rcx; __int64
0x140026fe2  mov     rdx, r15; FileObject
0x140026fe5  lea     rcx, [rsp+160h+Context]
0x140026fea  mov     [rsp+160h+LengthReturned], rcx; __int64
0x140026fef  mov     rcx, rbx; Instance
0x140026ff2  call    WcGetSetContextFileObject
0x140026ff7  mov     r12d, 5
0x140026ffd  mov     ebx, eax
0x140026fff  mov     rax, [rsi+10h]
0x140027003  lea     r13d, [r12-3]
0x140027008  test    [rax+6], r13b
0x14002700c  jz      loc_1400270B2
0x140027012  mov     rax, [rsi+20h]
0x140027016  xor     esi, esi
0x140027018  test    rax, rax
0x14002701b  jz      short loc_140027026
0x14002701d  mov     r9d, esi
0x140027020  cmp     rax, 3
0x140027024  jnz     short loc_14002702C
0x140027026  mov     r9d, 1
0x14002702c  mov     eax, cs:dword_14000E060
0x140027032  cmp     eax, r12d
0x140027035  jbe     short loc_1400270B2
0x140027037  mov     rdx, 400000000000h
0x140027041  lea     rcx, dword_14000E060
0x140027048  call    _tlgKeywordOn
0x14002704d  test    al, al
0x14002704f  jz      short loc_1400270B2
0x140027051  lea     rax, [rbp+60h+var_D0]
0x140027055  mov     [rbp+60h+var_CC], r9d
0x140027059  mov     [rbp+60h+var_70], rax
0x14002705d  lea     rdx, unk_14000B4A0
0x140027064  lea     rax, [rbp+60h+var_CC]
0x140027068  mov     [rbp+60h+var_D0], ebx
0x14002706b  mov     [rbp+60h+var_60], rax
0x14002706f  xor     r9d, r9d
0x140027072  mov     rax, [rbp+60h+var_B8]
0x140027076  xor     r8d, r8d
0x140027079  mov     [rbp+60h+var_68], 4
0x140027081  mov     [rbp+60h+var_58], 4
0x140027089  mov     [rbp+60h+var_48], 4
0x140027091  mov     eax, [rax+38h]
0x140027094  mov     [rbp+60h+var_C8], eax
0x140027097  lea     rax, [rbp+60h+var_C8]
0x14002709b  mov     [rbp+60h+var_50], rax
0x14002709f  lea     rax, [rbp+60h+var_90]
0x1400270a3  mov     [rsp+160h+LengthReturned], rax
0x1400270a8  mov     [rsp+160h+FileInformationClass], r12d
0x1400270ad  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400270b2  mov     rsi, [rsp+160h+FastMutex]
0x1400270b7  xor     eax, eax
0x1400270b9  test    ebx, ebx
0x1400270bb  js      loc_140027691
0x1400270c1  cmp     ebx, 104h
0x1400270c7  jz      short loc_1400270FF
0x1400270c9  mov     rdi, [rsp+160h+Context]
0x1400270ce  mov     rdx, rsi
0x1400270d1  mov     rcx, rdi
0x1400270d4  call    WcIsPlaceHolderDirectory
0x1400270d9  test    al, al
0x1400270db  jz      short loc_140027106
0x1400270dd  test    r14d, 106h
0x1400270e4  jz      loc_140027710
0x1400270ea  mov     rdx, [rsp+160h+FltObject]; FltObject
0x1400270ef  mov     r9d, r13d
0x1400270f2  mov     rcx, [rsp+160h+CallbackData]; CallbackData
0x1400270f7  mov     r8, r15; Object
0x1400270fa  call    WcSetPlaceHolderFlagsSynchronized
0x1400270ff  mov     ebx, eax
0x140027101  jmp     loc_140027710
0x140027106  mov     rdx, rsi
0x140027109  mov     rcx, rdi
0x14002710c  call    WcIsPlaceHolderStream
0x140027111  lea     rdi, WPP_RECORDER_INITIALIZED
0x140027118  test    al, al
0x14002711a  jz      loc_1400273AD
0x140027120  mov     rcx, [rsp+160h+CallbackData]; CallbackData
0x140027125  mov     rax, [rcx+20h]
0x140027129  cmp     rax, 3
0x14002712d  jz      loc_1400271FE
0x140027133  test    rax, rax
0x140027136  jz      loc_1400271FE
0x14002713c  test    r14b, 6
0x140027140  jz      loc_1400272D6
0x140027146  mov     r9, [rsp+160h+Context]
0x14002714b  mov     r8, r15; Object
0x14002714e  mov     rdx, [rsp+160h+FltObject]; FltObject
0x140027153  mov     dword ptr [rsp+160h+LengthReturned], 10h; int
0x14002715b  mov     [rsp+160h+FileInformationClass], 1; int
0x140027163  call    WcExpandAndWait
0x140027168  mov     ebx, eax
0x14002716a  test    eax, eax
0x14002716c  js      loc_140027710
0x140027172  cmp     dword ptr [rsi+14h], 1
0x140027176  jnz     loc_1400272D6
0x14002717c  xor     r8d, r8d
0x14002717f  xor     edx, edx
0x140027181  mov     rcx, r15
0x140027184  call    cs:__imp_IoSetShadowFileInformation
0x14002718b  nop     dword ptr [rax+rax+00h]
0x140027190  mov     ebx, eax
0x140027192  test    eax, eax
0x140027194  jns     short loc_1400271DE
0x140027196  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14002719d  jz      loc_1400272D6
0x1400271a3  mov     rcx, cs:wil_details_featureDescriptors_a
0x1400271aa  lea     rax, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x1400271b1  mov     dword ptr [rsp+160h+var_130], 310h
0x1400271b9  mov     r9d, 18h
0x1400271bf  mov     [rsp+160h+LengthReturned], rax
0x1400271c4  mov     r8d, r12d
0x1400271c7  lea     rax, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x1400271ce  mov     dl, 3
0x1400271d0  mov     rcx, [rcx+40h]
0x1400271d4  mov     qword ptr [rsp+160h+FileInformationClass], rax
0x1400271d9  call    WPP_RECORDER_SF_sD
0x1400271de  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400271e5  jz      loc_1400272D6
0x1400271eb  mov     r9d, 19h
0x1400271f1  mov     dword ptr [rsp+160h+var_130], 313h
0x1400271f9  jmp     loc_1400272A9
0x1400271fe  mov     r9, [rsp+160h+Context]
0x140027203  mov     r8, r15; Object
0x140027206  mov     rdx, [rsp+160h+FltObject]; FltObject
0x14002720b  mov     dword ptr [rsp+160h+LengthReturned], 13h; int
0x140027213  mov     [rsp+160h+FileInformationClass], 1; int
0x14002721b  call    WcExpandAndWait
0x140027220  mov     ebx, eax
0x140027222  test    eax, eax
0x140027224  js      loc_140027710
0x14002722a  cmp     dword ptr [rsi+14h], 1
0x14002722e  jnz     loc_1400272D6
0x140027234  xor     r8d, r8d
0x140027237  xor     edx, edx
0x140027239  mov     rcx, r15
0x14002723c  call    cs:__imp_IoSetShadowFileInformation
0x140027243  nop     dword ptr [rax+rax+00h]
0x140027248  mov     ebx, eax
0x14002724a  test    eax, eax
0x14002724c  jns     short loc_140027292
0x14002724e  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140027255  jz      short loc_1400272D6
0x140027257  mov     rcx, cs:wil_details_featureDescriptors_a
0x14002725e  lea     rax, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x140027265  mov     dword ptr [rsp+160h+var_130], 2F4h
0x14002726d  mov     r9d, 16h
0x140027273  mov     [rsp+160h+LengthReturned], rax
0x140027278  mov     r8d, r12d
0x14002727b  lea     rax, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x140027282  mov     dl, 3
0x140027284  mov     rcx, [rcx+40h]
0x140027288  mov     qword ptr [rsp+160h+FileInformationClass], rax
0x14002728d  call    WPP_RECORDER_SF_sD
0x140027292  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140027299  jz      short loc_1400272D6
0x14002729b  mov     r9d, 17h
0x1400272a1  mov     dword ptr [rsp+160h+var_130], 2F7h
0x1400272a9  mov     rcx, cs:wil_details_featureDescriptors_a
0x1400272b0  lea     rax, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x1400272b7  mov     [rsp+160h+LengthReturned], rax
0x1400272bc  mov     r8d, r12d
0x1400272bf  lea     rax, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x1400272c6  mov     dl, 3
0x1400272c8  mov     qword ptr [rsp+160h+FileInformationClass], rax
0x1400272cd  mov     rcx, [rcx+40h]
0x1400272d1  call    WPP_RECORDER_SF_sD
0x1400272d6  mov     rcx, [rsp+160h+Context]
0x1400272db  mov     rdx, rsi
0x1400272de  call    WcIsPlaceHolderStream
0x1400272e3  test    al, al
0x1400272e5  jz      loc_140027710
0x1400272eb  mov     rax, [rsp+160h+Context]
0x1400272f0  add     rax, 8
0x1400272f4  mov     rcx, rax; FastMutex
0x1400272f7  mov     [rsp+160h+FastMutex], rax
0x1400272fc  call    cs:__imp_ExAcquireFastMutex
0x140027303  nop     dword ptr [rax+rax+00h]
0x140027308  mov     rax, [rsp+160h+Context]
0x14002730d  mov     rcx, [rax+40h]
0x140027311  lea     rax, [rcx+22h]
0x140027315  mov     qword ptr [rbp+60h+var_E0+8], rax
0x140027319  movzx   eax, word ptr [rcx+20h]
0x14002731d  mov     word ptr [rbp+60h+var_E0], ax
0x140027321  movzx   eax, word ptr [rcx+20h]
0x140027325  mov     word ptr [rbp+60h+var_E0+2], ax
0x140027329  mov     eax, [rsi+14h]
0x14002732c  cmp     eax, r13d
0x14002732f  jz      loc_140027497
0x140027335  cmp     [rsp+160h+var_110], 0
0x14002733a  jz      loc_1400273D7
0x140027340  mov     rcx, [rsp+160h+FltObject]
0x140027345  mov     rdx, r15
0x140027348  call    WcCopySectionObjectPointers
0x14002734d  mov     ebx, eax
0x14002734f  test    eax, eax
  ... truncated ...
```
