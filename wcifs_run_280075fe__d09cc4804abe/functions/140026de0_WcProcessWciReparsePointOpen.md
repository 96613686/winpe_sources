# WcProcessWciReparsePointOpen

- ea: `0x140026de0`
- end: `0x140027720`
- name: `WcProcessWciReparsePointOpen`
- size: `2368`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `reparse_path, loader_planting`

## callers

- `0x140025220`

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
- `0x140026de0`
- `0x14002893c`
- `0x140029608`
- `0x14002ee54`

## import_xrefs

- `ntoskrnl!IoSetShadowFileInformation` at `0x140027134`
- `ntoskrnl!IoSetShadowFileInformation` at `0x1400271ec`
- `ntoskrnl!IoSetShadowFileInformation` at `0x140027134`
- `ntoskrnl!IoSetShadowFileInformation` at `0x1400271ec`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400272ac`
- `ntoskrnl!ExAcquireFastMutex` at `0x140027535`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400272ac`
- `ntoskrnl!ExAcquireFastMutex` at `0x140027535`
- `ntoskrnl!ExReleaseFastMutex` at `0x140027513`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002754d`
- `ntoskrnl!ExReleaseFastMutex` at `0x140027513`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002754d`
- `FLTMGR!FltFlushBuffers2` at `0x1400275ac`
- `FLTMGR!FltFlushBuffers2` at `0x1400275ac`
- `FLTMGR!FltQueryInformationFile` at `0x140026ef0`
- `FLTMGR!FltQueryInformationFile` at `0x140026ef0`
- `FLTMGR!FltReleaseContext` at `0x1400276cd`
- `FLTMGR!FltReleaseContext` at `0x1400276e1`
- `FLTMGR!FltReleaseContext` at `0x1400276cd`
- `FLTMGR!FltReleaseContext` at `0x1400276e1`

## string_xrefs

- `0x140026f2c`: `onecore\base\fs\wci\wcifs\create.c`
- `0x14002715a`: `onecore\base\fs\wci\wcifs\create.c`
- `0x14002720e`: `onecore\base\fs\wci\wcifs\create.c`
- `0x140027260`: `onecore\base\fs\wci\wcifs\create.c`
- `0x14002732e`: `onecore\base\fs\wci\wcifs\create.c`
- `0x140027415`: `onecore\base\fs\wci\wcifs\create.c`
- `0x140027480`: `onecore\base\fs\wci\wcifs\create.c`
- `0x1400274e3`: `onecore\base\fs\wci\wcifs\create.c`
- `0x140027602`: `onecore\base\fs\wci\wcifs\create.c`
- `0x140027687`: `onecore\base\fs\wci\wcifs\create.c`

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
            WPP_GLOBAL_Control->DeviceExtension,
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
          WPP_GLOBAL_Control->DeviceExtension,
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
        WPP_GLOBAL_Control->DeviceExtension,
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
            WPP_GLOBAL_Control->DeviceExtension,
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
            WPP_GLOBAL_Control->DeviceExtension,
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
            WPP_GLOBAL_Control->DeviceExtension,
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
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
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
          WPP_GLOBAL_Control->DeviceExtension,
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
          WPP_GLOBAL_Control->DeviceExtension,
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
              WPP_GLOBAL_Control->DeviceExtension,
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
          WPP_GLOBAL_Control->DeviceExtension,
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
0x140026de0  mov     [rsp-8+arg_18], rbx
0x140026de5  push    rbp
0x140026de6  push    rsi
0x140026de7  push    rdi
0x140026de8  push    r12
0x140026dea  push    r13
0x140026dec  push    r14
0x140026dee  push    r15
0x140026df0  lea     rbp, [rsp-30h]
0x140026df5  sub     rsp, 130h
0x140026dfc  mov     rax, cs:__security_cookie
0x140026e03  xor     rax, rsp
0x140026e06  mov     [rbp+60h+var_40], rax
0x140026e0a  xor     eax, eax
0x140026e0c  mov     [rsp+160h+CallbackData], rcx
0x140026e11  mov     [rbp+60h+var_A0], rax
0x140026e15  xor     r13d, r13d
0x140026e18  mov     rsi, rcx
0x140026e1b  mov     [rsp+160h+FltObject], rdx
0x140026e20  mov     rcx, [r8+18h]
0x140026e24  xorps   xmm0, xmm0
0x140026e27  movups  [rbp+60h+FileInformation], xmm0
0x140026e2b  mov     [rbp+60h+var_C0], rcx
0x140026e2f  mov     rbx, rdx
0x140026e32  mov     rcx, [rsi+10h]
0x140026e36  lea     edx, [r13+1]
0x140026e3a  movups  [rbp+60h+var_E0], xmm0
0x140026e3e  mov     r15, r8
0x140026e41  mov     [rsp+160h+Context], r13
0x140026e46  mov     [rsp+160h+FastMutex], r13
0x140026e4b  mov     rax, [rcx+18h]
0x140026e4f  mov     edi, [rcx+20h]
0x140026e52  mov     r14d, [rax+10h]
0x140026e56  movzx   eax, word ptr [rcx+2Ah]
0x140026e5a  mov     ecx, 0FFFBh
0x140026e5f  mov     [rsp+160h+var_F8], ax
0x140026e64  sub     ax, dx
0x140026e67  test    cx, ax
0x140026e6a  jnz     short loc_140026EA7
0x140026e6c  cmp     r14d, 20h ; ' '
0x140026e70  jz      short loc_140026EA1
0x140026e72  lea     eax, [r14-100020h]
0x140026e79  cmp     eax, edx
0x140026e7b  jbe     short loc_140026EA1
0x140026e7d  cmp     r14d, 1000A1h
0x140026e84  jz      short loc_140026EA1
0x140026e86  cmp     r14d, 120020h
0x140026e8d  jz      short loc_140026EA1
0x140026e8f  cmp     r14d, 1200A9h
0x140026e96  jz      short loc_140026EA1
0x140026e98  cmp     r14d, 1200A0h
0x140026e9f  jnz     short loc_140026EA7
0x140026ea1  mov     [rsp+160h+var_110], dl
0x140026ea5  jmp     short loc_140026EAC
0x140026ea7  mov     [rsp+160h+var_110], r13b
0x140026eac  mov     rdx, rbx
0x140026eaf  mov     rcx, rsi
0x140026eb2  call    WcGetUnionContext
0x140026eb7  mov     r9d, edi
0x140026eba  mov     [rbp+60h+var_B8], rax
0x140026ebe  and     r9d, 41h
0x140026ec2  test    rax, rax
0x140026ec5  jnz     loc_140026F85
0x140026ecb  test    r9d, r9d
0x140026ece  jnz     loc_140026F76
0x140026ed4  lea     r12d, [rax+5]
0x140026ed8  mov     [rsp+160h+LengthReturned], r13; LengthReturned
0x140026edd  lea     r9d, [rax+18h]; Length
0x140026ee1  mov     [rsp+160h+FileInformationClass], r12d; FileInformationClass
0x140026ee6  lea     r8, [rbp+60h+FileInformation]; FileInformation
0x140026eea  mov     rdx, r15; FileObject
0x140026eed  mov     rcx, rbx; Instance
0x140026ef0  call    cs:__imp_FltQueryInformationFile
0x140026ef7  nop     dword ptr [rax+rax+00h]
0x140026efc  mov     ebx, eax
0x140026efe  test    eax, eax
0x140026f00  jns     short loc_140026F62
0x140026f02  lea     rdi, WPP_RECORDER_INITIALIZED
0x140026f09  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140026f10  jz      short loc_140026F58
0x140026f12  mov     rcx, cs:WPP_GLOBAL_Control
0x140026f19  lea     r9d, [r12+0Eh]
0x140026f1e  mov     dword ptr [rsp+160h+var_120], eax
0x140026f22  lea     edx, [r12-3]
0x140026f27  mov     [rsp+160h+var_128], r15
0x140026f2c  lea     rax, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x140026f33  mov     dword ptr [rsp+160h+var_130], 271h
0x140026f3b  mov     r8d, r12d
0x140026f3e  mov     rcx, [rcx+40h]
0x140026f42  mov     [rsp+160h+LengthReturned], rax
0x140026f47  lea     rax, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x140026f4e  mov     qword ptr [rsp+160h+FileInformationClass], rax
0x140026f53  call    WPP_RECORDER_SF_sDqd
0x140026f58  mov     ebx, 0C0000022h
0x140026f5d  jmp     loc_1400276F6
0x140026f62  cmp     byte ptr [rbp+60h+var_A0+5], r13b
0x140026f66  jnz     loc_1400276F6
0x140026f6c  mov     ebx, 104h
0x140026f71  jmp     loc_1400276F6
0x140026f76  mov     ebx, r13d
0x140026f79  test    dil, 40h
0x140026f7d  jz      loc_1400276F6
0x140026f83  jmp     short loc_140026F6C
0x140026f85  lea     rcx, [rsp+160h+FastMutex]
0x140026f8a  mov     r8, rax
0x140026f8d  mov     [rsp+160h+var_130], rcx; __int64
0x140026f92  mov     rdx, r15; FileObject
0x140026f95  lea     rcx, [rsp+160h+Context]
0x140026f9a  mov     [rsp+160h+LengthReturned], rcx; __int64
0x140026f9f  mov     rcx, rbx; Instance
0x140026fa2  call    WcGetSetContextFileObject
0x140026fa7  mov     r12d, 5
0x140026fad  mov     ebx, eax
0x140026faf  mov     rax, [rsi+10h]
0x140026fb3  lea     r13d, [r12-3]
0x140026fb8  test    [rax+6], r13b
0x140026fbc  jz      loc_140027062
0x140026fc2  mov     rax, [rsi+20h]
0x140026fc6  xor     esi, esi
0x140026fc8  test    rax, rax
0x140026fcb  jz      short loc_140026FD6
0x140026fcd  mov     r9d, esi
0x140026fd0  cmp     rax, 3
0x140026fd4  jnz     short loc_140026FDC
0x140026fd6  mov     r9d, 1
0x140026fdc  mov     eax, cs:dword_14000E060
0x140026fe2  cmp     eax, r12d
0x140026fe5  jbe     short loc_140027062
0x140026fe7  mov     rdx, 400000000000h
0x140026ff1  lea     rcx, dword_14000E060
0x140026ff8  call    _tlgKeywordOn
0x140026ffd  test    al, al
0x140026fff  jz      short loc_140027062
0x140027001  lea     rax, [rbp+60h+var_D0]
0x140027005  mov     [rbp+60h+var_CC], r9d
0x140027009  mov     [rbp+60h+var_70], rax
0x14002700d  lea     rdx, unk_14000B4A0
0x140027014  lea     rax, [rbp+60h+var_CC]
0x140027018  mov     [rbp+60h+var_D0], ebx
0x14002701b  mov     [rbp+60h+var_60], rax
0x14002701f  xor     r9d, r9d
0x140027022  mov     rax, [rbp+60h+var_B8]
0x140027026  xor     r8d, r8d
0x140027029  mov     [rbp+60h+var_68], 4
0x140027031  mov     [rbp+60h+var_58], 4
0x140027039  mov     [rbp+60h+var_48], 4
0x140027041  mov     eax, [rax+38h]
0x140027044  mov     [rbp+60h+var_C8], eax
0x140027047  lea     rax, [rbp+60h+var_C8]
0x14002704b  mov     [rbp+60h+var_50], rax
0x14002704f  lea     rax, [rbp+60h+var_90]
0x140027053  mov     [rsp+160h+LengthReturned], rax
0x140027058  mov     [rsp+160h+FileInformationClass], r12d
0x14002705d  call    _tlgWriteTransfer_EtwWriteTransfer
0x140027062  mov     rsi, [rsp+160h+FastMutex]
0x140027067  xor     eax, eax
0x140027069  test    ebx, ebx
0x14002706b  js      loc_140027641
0x140027071  cmp     ebx, 104h
0x140027077  jz      short loc_1400270AF
0x140027079  mov     rdi, [rsp+160h+Context]
0x14002707e  mov     rdx, rsi
0x140027081  mov     rcx, rdi
0x140027084  call    WcIsPlaceHolderDirectory
0x140027089  test    al, al
0x14002708b  jz      short loc_1400270B6
0x14002708d  test    r14d, 106h
0x140027094  jz      loc_1400276C0
0x14002709a  mov     rdx, [rsp+160h+FltObject]; FltObject
0x14002709f  mov     r9d, r13d
0x1400270a2  mov     rcx, [rsp+160h+CallbackData]; CallbackData
0x1400270a7  mov     r8, r15; Object
0x1400270aa  call    WcSetPlaceHolderFlagsSynchronized
0x1400270af  mov     ebx, eax
0x1400270b1  jmp     loc_1400276C0
0x1400270b6  mov     rdx, rsi
0x1400270b9  mov     rcx, rdi
0x1400270bc  call    WcIsPlaceHolderStream
0x1400270c1  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400270c8  test    al, al
0x1400270ca  jz      loc_14002735D
0x1400270d0  mov     rcx, [rsp+160h+CallbackData]; CallbackData
0x1400270d5  mov     rax, [rcx+20h]
0x1400270d9  cmp     rax, 3
0x1400270dd  jz      loc_1400271AE
0x1400270e3  test    rax, rax
0x1400270e6  jz      loc_1400271AE
0x1400270ec  test    r14b, 6
0x1400270f0  jz      loc_140027286
0x1400270f6  mov     r9, [rsp+160h+Context]
0x1400270fb  mov     r8, r15; Object
0x1400270fe  mov     rdx, [rsp+160h+FltObject]; FltObject
0x140027103  mov     dword ptr [rsp+160h+LengthReturned], 10h; int
0x14002710b  mov     [rsp+160h+FileInformationClass], 1; int
0x140027113  call    WcExpandAndWait
0x140027118  mov     ebx, eax
0x14002711a  test    eax, eax
0x14002711c  js      loc_1400276C0
0x140027122  cmp     dword ptr [rsi+14h], 1
0x140027126  jnz     loc_140027286
0x14002712c  xor     r8d, r8d
0x14002712f  xor     edx, edx
0x140027131  mov     rcx, r15
0x140027134  call    cs:__imp_IoSetShadowFileInformation
0x14002713b  nop     dword ptr [rax+rax+00h]
0x140027140  mov     ebx, eax
0x140027142  test    eax, eax
0x140027144  jns     short loc_14002718E
0x140027146  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14002714d  jz      loc_140027286
0x140027153  mov     rcx, cs:WPP_GLOBAL_Control
0x14002715a  lea     rax, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x140027161  mov     dword ptr [rsp+160h+var_130], 310h
0x140027169  mov     r9d, 18h
0x14002716f  mov     [rsp+160h+LengthReturned], rax
0x140027174  mov     r8d, r12d
0x140027177  lea     rax, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x14002717e  mov     dl, 3
0x140027180  mov     rcx, [rcx+40h]
0x140027184  mov     qword ptr [rsp+160h+FileInformationClass], rax
0x140027189  call    WPP_RECORDER_SF_sD
0x14002718e  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140027195  jz      loc_140027286
0x14002719b  mov     r9d, 19h
0x1400271a1  mov     dword ptr [rsp+160h+var_130], 313h
0x1400271a9  jmp     loc_140027259
0x1400271ae  mov     r9, [rsp+160h+Context]
0x1400271b3  mov     r8, r15; Object
0x1400271b6  mov     rdx, [rsp+160h+FltObject]; FltObject
0x1400271bb  mov     dword ptr [rsp+160h+LengthReturned], 13h; int
0x1400271c3  mov     [rsp+160h+FileInformationClass], 1; int
0x1400271cb  call    WcExpandAndWait
0x1400271d0  mov     ebx, eax
0x1400271d2  test    eax, eax
0x1400271d4  js      loc_1400276C0
0x1400271da  cmp     dword ptr [rsi+14h], 1
0x1400271de  jnz     loc_140027286
0x1400271e4  xor     r8d, r8d
0x1400271e7  xor     edx, edx
0x1400271e9  mov     rcx, r15
0x1400271ec  call    cs:__imp_IoSetShadowFileInformation
0x1400271f3  nop     dword ptr [rax+rax+00h]
0x1400271f8  mov     ebx, eax
0x1400271fa  test    eax, eax
0x1400271fc  jns     short loc_140027242
0x1400271fe  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140027205  jz      short loc_140027286
0x140027207  mov     rcx, cs:WPP_GLOBAL_Control
0x14002720e  lea     rax, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x140027215  mov     dword ptr [rsp+160h+var_130], 2F4h
0x14002721d  mov     r9d, 16h
0x140027223  mov     [rsp+160h+LengthReturned], rax
0x140027228  mov     r8d, r12d
0x14002722b  lea     rax, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x140027232  mov     dl, 3
0x140027234  mov     rcx, [rcx+40h]
0x140027238  mov     qword ptr [rsp+160h+FileInformationClass], rax
0x14002723d  call    WPP_RECORDER_SF_sD
0x140027242  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140027249  jz      short loc_140027286
0x14002724b  mov     r9d, 17h
0x140027251  mov     dword ptr [rsp+160h+var_130], 2F7h
0x140027259  mov     rcx, cs:WPP_GLOBAL_Control
0x140027260  lea     rax, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x140027267  mov     [rsp+160h+LengthReturned], rax
0x14002726c  mov     r8d, r12d
0x14002726f  lea     rax, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x140027276  mov     dl, 3
0x140027278  mov     qword ptr [rsp+160h+FileInformationClass], rax
0x14002727d  mov     rcx, [rcx+40h]
0x140027281  call    WPP_RECORDER_SF_sD
0x140027286  mov     rcx, [rsp+160h+Context]
0x14002728b  mov     rdx, rsi
0x14002728e  call    WcIsPlaceHolderStream
0x140027293  test    al, al
0x140027295  jz      loc_1400276C0
0x14002729b  mov     rax, [rsp+160h+Context]
0x1400272a0  add     rax, 8
0x1400272a4  mov     rcx, rax; FastMutex
0x1400272a7  mov     [rsp+160h+FastMutex], rax
0x1400272ac  call    cs:__imp_ExAcquireFastMutex
0x1400272b3  nop     dword ptr [rax+rax+00h]
0x1400272b8  mov     rax, [rsp+160h+Context]
0x1400272bd  mov     rcx, [rax+40h]
0x1400272c1  lea     rax, [rcx+22h]
0x1400272c5  mov     qword ptr [rbp+60h+var_E0+8], rax
0x1400272c9  movzx   eax, word ptr [rcx+20h]
0x1400272cd  mov     word ptr [rbp+60h+var_E0], ax
0x1400272d1  movzx   eax, word ptr [rcx+20h]
0x1400272d5  mov     word ptr [rbp+60h+var_E0+2], ax
0x1400272d9  mov     eax, [rsi+14h]
0x1400272dc  cmp     eax, r13d
0x1400272df  jz      loc_140027447
0x1400272e5  cmp     [rsp+160h+var_110], 0
0x1400272ea  jz      loc_140027387
0x1400272f0  mov     rcx, [rsp+160h+FltObject]
0x1400272f5  mov     rdx, r15
0x1400272f8  call    WcCopySectionObjectPointers
0x1400272fd  mov     ebx, eax
0x1400272ff  test    eax, eax
  ... truncated ...
```
