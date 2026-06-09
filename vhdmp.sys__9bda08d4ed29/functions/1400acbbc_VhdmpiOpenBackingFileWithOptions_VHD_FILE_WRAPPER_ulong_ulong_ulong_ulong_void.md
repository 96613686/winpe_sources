# VhdmpiOpenBackingFileWithOptions(_VHD_FILE_WRAPPER *,ulong,ulong,ulong,ulong,void * *)

- ea: `0x1400acbbc`
- end: `0x1400ad150`
- name: `?VhdmpiOpenBackingFileWithOptions@@YAJPEAU_VHD_FILE_WRAPPER@@KKKKPEAPEAX@Z`
- size: `1428`
- prototype: `__int64 __fastcall(struct _VHD_FILE_WRAPPER *, int, ULONG, int, ULONG Options, void **)`
- caller_count: `3`
- callee_count: `13`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400ab4d0`
- `0x1400ac4f8`
- `0x1400adccc`

## callees

- `0x1400010d0`
- `0x1400152fc`
- `0x14001c1d0`
- `0x14001dfd4`
- `0x1400205f0`
- `0x140023980`
- `0x140036284`
- `0x14005dbb0`
- `0x14005e100`
- `0x1400acbbc`
- `0x1400e5ae4`
- `0x1400e8098`
- `0x1400e9190`

## import_xrefs

- `ntoskrnl!IoCreateFileEx` at `0x1400acec6`
- `ntoskrnl!IoCreateFileEx` at `0x1400acec6`
- `ntoskrnl!EtwActivityIdControl` at `0x1400acdd5`
- `ntoskrnl!EtwActivityIdControl` at `0x1400acdd5`

## string_xrefs

- `0x1400ad0a4`: ` (file '%wZ') Failed to open backing file: 0x%08x`
- `0x1400ad01f`: ` (file '%wZ')Successfully opened backing file`
- `0x1400acd93`: `VhdmpiOpenBackingFileWithOptions`
- `0x1400ad03b`: `VhdmpiOpenBackingFileWithOptions`
- `0x1400ad0f3`: `VhdmpiOpenBackingFileWithOptions`
- `0x1400acd73`: ` (file '%wZ')Opening backing file with access %x, sharing %x`
- `0x1400ad0dc`: ` (file '%wZ')Failed to open backing file: 0x%08x`

## pseudocode

```c
__int64 __fastcall VhdmpiOpenBackingFileWithOptions(
        struct _VHD_FILE_WRAPPER *a1,
        int a2,
        ULONG a3,
        int a4,
        ULONG Options,
        void **a6)
{
  ULONG EaLength; // r15d
  __int64 v10; // rdx
  NTSTATUS v11; // edi
  _OWORD *EaBuffer; // r12
  __int128 v13; // xmm0
  int v14; // ecx
  int v15; // r8d
  int v16; // edx
  const wchar_t *v17; // rsi
  int v18; // r9d
  const wchar_t *v19; // rax
  const wchar_t *v20; // rcx
  int v21; // ecx
  int v22; // r8d
  const wchar_t *v23; // rax
  const wchar_t *v24; // rax
  void *v25; // rax
  int v26; // r9d
  int v27; // r9d
  int v28; // edx
  char *v29; // rax
  int v30; // r8d
  _BYTE v32[4]; // [rsp+80h] [rbp-80h] BYREF
  int v33; // [rsp+84h] [rbp-7Ch] BYREF
  const wchar_t *v34; // [rsp+88h] [rbp-78h] BYREF
  ULONG v35; // [rsp+90h] [rbp-70h] BYREF
  int v36; // [rsp+94h] [rbp-6Ch] BYREF
  void *FileHandle; // [rsp+98h] [rbp-68h] BYREF
  void **v38; // [rsp+A0h] [rbp-60h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-58h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v41; // [rsp+F8h] [rbp-8h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+100h] [rbp+0h] BYREF
  GUID ActivityId; // [rsp+110h] [rbp+10h] BYREF
  __int64 v44; // [rsp+120h] [rbp+20h]
  _OWORD v45[6]; // [rsp+130h] [rbp+30h] BYREF

  v38 = a6;
  v33 = a4;
  v41 = 0;
  EaLength = 92;
  memset(&DriverContext, 0, sizeof(DriverContext));
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  memset(v45, 0, 0x5Cu);
  FileHandle = (void *)-1LL;
  ActivityId = 0;
  v44 = 0;
  v11 = VhdmpiFileWrapperInitializeDriverCreateContext(&DriverContext);
  if ( v11 >= 0 )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)((char *)a1 + 16);
    ObjectAttributes.RootDirectory = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    ObjectAttributes.Attributes = 576;
    if ( !(unsigned __int8)VhdmpiIsRemoteSmbFile(a1, v10) || *(_OWORD *)((char *)a1 + 548) == *(_OWORD *)&VhdmpZeroGuid )
    {
      EaBuffer = 0;
      EaLength = 0;
    }
    else
    {
      memset(v45, 0, 0x5Cu);
      BYTE5(v45[0]) = 28;
      WORD3(v45[0]) = 16;
      EaBuffer = v45;
      strcpy((char *)v45 + 8, "ClusteredApplicationInstance");
      LODWORD(v45[0]) = 56;
      v13 = *(_OWORD *)((char *)a1 + 548);
      *((_QWORD *)&v45[3] + 1) = 0x2160000000000LL;
      *(_OWORD *)((char *)&v45[2] + 5) = v13;
      *(_WORD *)((char *)&v45[5] + 7) = 1;
      strcpy((char *)&v45[4], "ApplicationTrafficType");
    }
    v11 = VhdmpiCreateBackingStoreOpenEcp((*((_DWORD *)a1 + 34) & 0x10) != 0, &DriverContext);
    if ( v11 >= 0 )
    {
      if ( (unsigned int)dword_1400876D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 2048) )
        TraceEvents(
          (int)"VhdmpiOpenBackingFileWithOptions",
          3250,
          5,
          v16,
          " (file '%wZ')Opening backing file with access %x, sharing %x",
          (char)a1);
      if ( (Microsoft_Windows_VHDMPEnableBits & 1) != 0 )
        McTemplateK0zq_EtwWriteTransfer(v14, (unsigned int)FileWrapperHandleCreateBegin, v15, *((_QWORD *)a1 + 6), a2);
      EtwActivityIdControl(3u, &ActivityId);
      v44 = 0;
      v17 = L"Unknown";
      if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x10000) )
      {
        v19 = (const wchar_t *)*((_QWORD *)a1 + 6);
        v35 = a3;
        v20 = L"Unknown";
        v36 = a2;
        if ( v19 )
          v20 = v19;
        v32[0] = 0;
        v34 = v20;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v20,
          (unsigned int)word_14007CDEA,
          (unsigned int)&ActivityId,
          v18,
          (__int64)&v34,
          (__int64)v32,
          (__int64)&v36,
          (__int64)&v35);
      }
      v11 = IoCreateFileEx(
              &FileHandle,
              a2 | 0x100000,
              &ObjectAttributes,
              &IoStatusBlock,
              0,
              0x80u,
              a3,
              1u,
              v33 | 0x40,
              EaBuffer,
              EaLength,
              CreateFileTypeNone,
              0,
              Options,
              &DriverContext);
      if ( v11 == -1073741772 )
      {
        if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x10000) )
        {
          v23 = (const wchar_t *)*((_QWORD *)a1 + 6);
          v33 = -1073741772;
          if ( v23 )
            v17 = v23;
          v34 = v17;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            v21,
            (unsigned int)word_14007CD42,
            (unsigned int)&ActivityId,
            v44,
            (__int64)&v34,
            (__int64)&v33);
        }
        goto LABEL_39;
      }
      if ( v11 < 0 && (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x10000) )
      {
        v33 = v11;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          v21,
          (unsigned int)word_14007CD82,
          (unsigned int)&ActivityId,
          v44,
          (__int64)&v33);
      }
      if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x10000) )
      {
        v24 = (const wchar_t *)*((_QWORD *)a1 + 6);
        v33 = v11;
        if ( v24 )
          v17 = v24;
        v34 = v17;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v21,
          (unsigned int)word_14007CDAA,
          (unsigned int)&ActivityId,
          v44,
          (__int64)&v34,
          (__int64)&v33);
      }
      if ( v11 < 0 )
      {
        v22 = -1073741757;
        if ( v11 == -1073741757 )
        {
          if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 2048) )
          {
            v29 = " (file '%wZ')Failed to open backing file: 0x%08x";
            v30 = 4;
            v28 = 3318;
            goto LABEL_45;
          }
LABEL_46:
          if ( (Microsoft_Windows_VHDMPEnableBits & 1) != 0 )
            McTemplateK0zq_EtwWriteTransfer(
              v21,
              (unsigned int)FileWrapperHandleCreateEndFailure,
              v22,
              *((_QWORD *)a1 + 6),
              v11);
          goto LABEL_48;
        }
LABEL_39:
        if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 2048) )
        {
          v28 = 3309;
          v29 = " (file '%wZ') Failed to open backing file: 0x%08x";
          v30 = 2;
LABEL_45:
          TraceEvents((int)"VhdmpiOpenBackingFileWithOptions", v28, v30, v27, v29, (char)a1);
          goto LABEL_46;
        }
        goto LABEL_46;
      }
      v25 = FileHandle;
      FileHandle = (void *)-1LL;
      *v38 = v25;
      if ( (unsigned int)dword_1400876D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 2048) )
        TraceEvents(
          (int)"VhdmpiOpenBackingFileWithOptions",
          3299,
          5,
          v26,
          " (file '%wZ')Successfully opened backing file",
          (char)a1);
      if ( (Microsoft_Windows_VHDMPEnableBits & 1) != 0 )
        McTemplateK0zq_EtwWriteTransfer(v21, (unsigned int)FileWrapperHandleCreateEnd, v22, *((_QWORD *)a1 + 6), 0);
    }
  }
LABEL_48:
  VhdmpiFileWrapperCleanupDriverCreateContext(&DriverContext);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400acbbc  push    rbp
0x1400acbbe  push    rbx
0x1400acbbf  push    rsi
0x1400acbc0  push    rdi
0x1400acbc1  push    r12
0x1400acbc3  push    r13
0x1400acbc5  push    r14
0x1400acbc7  push    r15
0x1400acbc9  lea     rbp, [rsp-0A8h]
0x1400acbd1  sub     rsp, 1A8h
0x1400acbd8  mov     rax, cs:__security_cookie
0x1400acbdf  xor     rax, rsp
0x1400acbe2  mov     [rbp+0E0h+var_50], rax
0x1400acbe9  mov     rax, [rbp+0E0h+arg_28]
0x1400acbf0  xorps   xmm0, xmm0
0x1400acbf3  xorps   xmm1, xmm1
0x1400acbf6  mov     [rbp+0E0h+var_140], rax
0x1400acbfa  xor     eax, eax
0x1400acbfc  mov     [rbp+0E0h+var_15C], r9d
0x1400acc00  mov     r13d, r8d
0x1400acc03  mov     [rbp+0E0h+var_E8], rax
0x1400acc07  mov     r14d, edx
0x1400acc0a  mov     rbx, rcx
0x1400acc0d  xor     edx, edx; Val
0x1400acc0f  lea     rcx, [rbp+0E0h+var_B0]; void *
0x1400acc13  lea     r15d, [rax+5Ch]
0x1400acc17  mov     r8d, r15d; Size
0x1400acc1a  movups  xmmword ptr [rbp+0E0h+var_108.Size], xmm0
0x1400acc1e  movups  xmmword ptr [rbp+0E0h+var_108.DeviceObjectHint], xmm0
0x1400acc22  movups  xmmword ptr [rbp+0E0h+IoStatusBlock], xmm0
0x1400acc26  movups  xmmword ptr [rbp+0E0h+ObjectAttributes.Length], xmm1
0x1400acc2a  movups  xmmword ptr [rbp+0E0h+ObjectAttributes.ObjectName], xmm1
0x1400acc2e  movups  xmmword ptr [rbp+0E0h+ObjectAttributes.SecurityDescriptor], xmm1
0x1400acc32  call    memset
0x1400acc37  xorps   xmm0, xmm0
0x1400acc3a  mov     [rbp+0E0h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x1400acc42  xor     eax, eax
0x1400acc44  lea     rcx, [rbp+0E0h+var_108]; struct _IO_DRIVER_CREATE_CONTEXT *
0x1400acc48  movups  xmmword ptr [rbp+0E0h+ActivityId.Data1], xmm0
0x1400acc4c  mov     [rbp+0E0h+var_C0], rax
0x1400acc50  call    ?VhdmpiFileWrapperInitializeDriverCreateContext@@YAJPEAU_IO_DRIVER_CREATE_CONTEXT@@@Z; VhdmpiFileWrapperInitializeDriverCreateContext(_IO_DRIVER_CREATE_CONTEXT *)
0x1400acc55  xor     esi, esi
0x1400acc57  mov     edi, eax
0x1400acc59  test    eax, eax
0x1400acc5b  js      loc_1400AD121
0x1400acc61  lea     rax, [rbx+10h]
0x1400acc65  mov     [rbp+0E0h+ObjectAttributes.Length], 30h ; '0'
0x1400acc6c  xorps   xmm0, xmm0
0x1400acc6f  mov     [rbp+0E0h+ObjectAttributes.ObjectName], rax
0x1400acc73  mov     rcx, rbx
0x1400acc76  mov     [rbp+0E0h+ObjectAttributes.RootDirectory], rsi
0x1400acc7a  movdqu  xmmword ptr [rbp+0E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400acc7f  mov     [rbp+0E0h+ObjectAttributes.Attributes], 240h
0x1400acc86  call    VhdmpiIsRemoteSmbFile
0x1400acc8b  lea     edi, [rsi+1]
0x1400acc8e  test    al, al
0x1400acc90  jz      loc_1400ACD29
0x1400acc96  mov     rax, [rbx+224h]
0x1400acc9d  cmp     rax, qword ptr cs:VhdmpZeroGuid
0x1400acca4  jnz     short loc_1400ACCB6
0x1400acca6  mov     rax, [rbx+22Ch]
0x1400accad  cmp     rax, qword ptr cs:VhdmpZeroGuid+8
0x1400accb4  jz      short loc_1400ACD29
0x1400accb6  mov     r8, r15; Size
0x1400accb9  lea     rcx, [rbp+0E0h+var_B0]; void *
0x1400accbd  xor     edx, edx; Val
0x1400accbf  call    memset
0x1400accc4  movups  xmm0, xmmword ptr cs:aClusteredappli; "ClusteredApplicationInstance"
0x1400acccb  mov     eax, 10h
0x1400accd0  mov     [rbp+0E0h+var_AB], 1Ch
0x1400accd4  movups  xmm1, xmmword ptr cs:aClusteredappli+0Dh; "icationInstance"
0x1400accdb  mov     [rbp+0E0h+var_AA], ax
0x1400accdf  lea     r12, [rbp+0E0h+var_B0]
0x1400acce3  movups  [rbp+0E0h+var_A8], xmm0
0x1400acce7  mov     [rbp+0E0h+var_B0], 38h ; '8'
0x1400accee  movups  xmm0, xmmword ptr [rbx+224h]
0x1400accf5  mov     [rbp+0E0h+var_78], esi
0x1400accf8  movups  [rbp+0E0h+var_A8+0Dh], xmm1
0x1400accfc  mov     [rbp+0E0h+var_74], 21600h
0x1400acd03  movsd   xmm1, qword ptr cs:aApplicationtra+0Fh; "ficType"
0x1400acd0b  movdqu  [rbp+0E0h+var_8B], xmm0
0x1400acd10  mov     [rbp+0E0h+var_59], di
0x1400acd17  movups  xmm0, xmmword ptr cs:aApplicationtra; "ApplicationTrafficType"
0x1400acd1e  movaps  [rbp+0E0h+var_70], xmm0
0x1400acd22  movsd   qword ptr [rbp+0E0h+var_70+0Fh], xmm1
0x1400acd27  jmp     short loc_1400ACD2F
0x1400acd29  mov     r12, rsi
0x1400acd2c  mov     r15d, esi
0x1400acd2f  mov     ecx, [rbx+88h]
0x1400acd35  lea     rdx, [rbp+0E0h+var_108]; struct _IO_DRIVER_CREATE_CONTEXT *
0x1400acd39  shr     ecx, 4
0x1400acd3c  and     cl, dil; unsigned __int8
0x1400acd3f  call    ?VhdmpiCreateBackingStoreOpenEcp@@YAJEPEAU_IO_DRIVER_CREATE_CONTEXT@@@Z; VhdmpiCreateBackingStoreOpenEcp(uchar,_IO_DRIVER_CREATE_CONTEXT *)
0x1400acd44  mov     edi, eax
0x1400acd46  test    eax, eax
0x1400acd48  js      loc_1400AD121
0x1400acd4e  mov     eax, cs:dword_1400876D0
0x1400acd54  mov     edx, 800h
0x1400acd59  cmp     eax, 5
0x1400acd5c  jbe     short loc_1400ACDA5
0x1400acd5e  lea     rcx, dword_1400876D0
0x1400acd65  call    _tlgKeywordOn
0x1400acd6a  test    al, al
0x1400acd6c  jz      short loc_1400ACDA5
0x1400acd6e  mov     [rsp+1E0h+Disposition], r13d
0x1400acd73  lea     rax, aFileWzOpeningB; " (file '%wZ')Opening backing file with "...
0x1400acd7a  mov     ecx, 0CB2h
0x1400acd7f  mov     [rsp+1E0h+ShareAccess], r14d
0x1400acd84  mov     r9d, edx; int
0x1400acd87  mov     qword ptr [rsp+1E0h+FileAttributes], rbx; char
0x1400acd8c  mov     edx, ecx; int
0x1400acd8e  mov     [rsp+1E0h+AllocationSize], rax; char *
0x1400acd93  lea     rcx, aVhdmpiopenback; "VhdmpiOpenBackingFileWithOptions"
0x1400acd9a  mov     r8d, 5; int
0x1400acda0  call    TraceEvents
0x1400acda5  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, 1
0x1400acdac  mov     edi, 100000h
0x1400acdb1  jz      short loc_1400ACDCC
0x1400acdb3  mov     r9, [rbx+30h]
0x1400acdb7  lea     rdx, FileWrapperHandleCreateBegin
0x1400acdbe  mov     eax, r14d
0x1400acdc1  or      eax, edi
0x1400acdc3  mov     dword ptr [rsp+1E0h+AllocationSize], eax
0x1400acdc7  call    McTemplateK0zq_EtwWriteTransfer
0x1400acdcc  lea     rdx, [rbp+0E0h+ActivityId]; ActivityId
0x1400acdd0  mov     ecx, 3; ControlCode
0x1400acdd5  call    cs:__imp_EtwActivityIdControl
0x1400acddc  nop     dword ptr [rax+rax+00h]
0x1400acde1  mov     eax, cs:dword_140087708
0x1400acde7  mov     [rbp+0E0h+var_C0], rsi
0x1400acdeb  lea     rsi, aUnknown; "Unknown"
0x1400acdf2  cmp     eax, 4
0x1400acdf5  jbe     short loc_1400ACE5E
0x1400acdf7  mov     edx, 10000h
0x1400acdfc  lea     rcx, dword_140087708
0x1400ace03  call    _tlgKeywordOn
0x1400ace08  test    al, al
0x1400ace0a  jz      short loc_1400ACE5E
0x1400ace0c  mov     rax, [rbx+30h]
0x1400ace10  lea     r8, [rbp+0E0h+ActivityId]
0x1400ace14  test    rax, rax
0x1400ace17  mov     [rbp+0E0h+var_150], r13d
0x1400ace1b  mov     rcx, rsi
0x1400ace1e  mov     [rbp+0E0h+var_14C], r14d
0x1400ace22  cmovnz  rcx, rax
0x1400ace26  mov     [rbp+0E0h+var_160], 0
0x1400ace2a  lea     rax, [rbp+0E0h+var_150]
0x1400ace2e  mov     [rbp+0E0h+var_158], rcx
0x1400ace32  mov     qword ptr [rsp+1E0h+Disposition], rax
0x1400ace37  lea     rdx, word_14007CDEA
0x1400ace3e  lea     rax, [rbp+0E0h+var_14C]
0x1400ace42  mov     qword ptr [rsp+1E0h+ShareAccess], rax
0x1400ace47  lea     rax, [rbp+0E0h+var_160]
0x1400ace4b  mov     qword ptr [rsp+1E0h+FileAttributes], rax
0x1400ace50  lea     rax, [rbp+0E0h+var_158]
0x1400ace54  mov     [rsp+1E0h+AllocationSize], rax
0x1400ace59  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400ace5e  mov     ecx, [rbp+0E0h+var_15C]
0x1400ace61  lea     rax, [rbp+0E0h+var_108]
0x1400ace65  mov     [rsp+1E0h+DriverContext], rax; DriverContext
0x1400ace6a  lea     r9, [rbp+0E0h+IoStatusBlock]; IoStatusBlock
0x1400ace6e  mov     eax, [rbp+0E0h+arg_20]
0x1400ace74  lea     r8, [rbp+0E0h+ObjectAttributes]; ObjectAttributes
0x1400ace78  mov     [rsp+1E0h+Options], eax; Options
0x1400ace7c  or      ecx, 40h
0x1400ace7f  mov     [rsp+1E0h+InternalParameters], 0; InternalParameters
0x1400ace88  or      r14d, edi
0x1400ace8b  mov     [rsp+1E0h+CreateFileType], 0; CreateFileType
0x1400ace93  mov     edx, r14d; DesiredAccess
0x1400ace96  mov     [rsp+1E0h+EaLength], r15d; EaLength
0x1400ace9b  mov     [rsp+1E0h+EaBuffer], r12; EaBuffer
0x1400acea0  mov     [rsp+1E0h+CreateOptions], ecx; CreateOptions
0x1400acea4  lea     rcx, [rbp+0E0h+FileHandle]; FileHandle
0x1400acea8  mov     [rsp+1E0h+Disposition], 1; Disposition
0x1400aceb0  mov     [rsp+1E0h+ShareAccess], r13d; ShareAccess
0x1400aceb5  mov     [rsp+1E0h+FileAttributes], 80h; FileAttributes
0x1400acebd  mov     [rsp+1E0h+AllocationSize], 0; AllocationSize
0x1400acec6  call    cs:__imp_IoCreateFileEx
0x1400acecd  nop     dword ptr [rax+rax+00h]
0x1400aced2  mov     edi, eax
0x1400aced4  cmp     eax, 0C0000034h
0x1400aced9  jnz     short loc_1400ACF44
0x1400acedb  mov     eax, cs:dword_140087708
0x1400acee1  cmp     eax, 4
0x1400acee4  jbe     loc_1400AD073
0x1400aceea  mov     edx, 10000h
0x1400aceef  lea     rcx, dword_140087708
0x1400acef6  call    _tlgKeywordOn
0x1400acefb  test    al, al
0x1400acefd  jz      loc_1400AD073
0x1400acf03  mov     rax, [rbx+30h]
0x1400acf07  lea     r8, [rbp+0E0h+ActivityId]
0x1400acf0b  mov     r9, [rbp+0E0h+var_C0]
0x1400acf0f  lea     rdx, word_14007CD42
0x1400acf16  test    rax, rax
0x1400acf19  mov     [rbp+0E0h+var_15C], 0C0000034h
0x1400acf20  cmovnz  rsi, rax
0x1400acf24  lea     rax, [rbp+0E0h+var_15C]
0x1400acf28  mov     qword ptr [rsp+1E0h+FileAttributes], rax
0x1400acf2d  lea     rax, [rbp+0E0h+var_158]
0x1400acf31  mov     [rsp+1E0h+AllocationSize], rax
0x1400acf36  mov     [rbp+0E0h+var_158], rsi
0x1400acf3a  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1400acf3f  jmp     loc_1400AD073
0x1400acf44  test    edi, edi
0x1400acf46  jns     short loc_1400ACF88
0x1400acf48  mov     eax, cs:dword_140087708
0x1400acf4e  cmp     eax, 2
0x1400acf51  jbe     short loc_1400ACF88
0x1400acf53  mov     edx, 10000h
0x1400acf58  lea     rcx, dword_140087708
0x1400acf5f  call    _tlgKeywordOn
0x1400acf64  test    al, al
0x1400acf66  jz      short loc_1400ACF88
0x1400acf68  mov     r9, [rbp+0E0h+var_C0]
0x1400acf6c  lea     rax, [rbp+0E0h+var_15C]
0x1400acf70  lea     r8, [rbp+0E0h+ActivityId]
0x1400acf74  mov     [rsp+1E0h+AllocationSize], rax
0x1400acf79  lea     rdx, word_14007CD82
0x1400acf80  mov     [rbp+0E0h+var_15C], edi
0x1400acf83  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1400acf88  mov     eax, cs:dword_140087708
0x1400acf8e  cmp     eax, 4
0x1400acf91  jbe     short loc_1400ACFE0
0x1400acf93  mov     edx, 10000h
0x1400acf98  lea     rcx, dword_140087708
0x1400acf9f  call    _tlgKeywordOn
0x1400acfa4  test    al, al
0x1400acfa6  jz      short loc_1400ACFE0
0x1400acfa8  mov     rax, [rbx+30h]
0x1400acfac  lea     r8, [rbp+0E0h+ActivityId]
0x1400acfb0  mov     r9, [rbp+0E0h+var_C0]
0x1400acfb4  lea     rdx, word_14007CDAA
0x1400acfbb  test    rax, rax
0x1400acfbe  mov     [rbp+0E0h+var_15C], edi
0x1400acfc1  cmovnz  rsi, rax
0x1400acfc5  lea     rax, [rbp+0E0h+var_15C]
0x1400acfc9  mov     qword ptr [rsp+1E0h+FileAttributes], rax
0x1400acfce  lea     rax, [rbp+0E0h+var_158]
0x1400acfd2  mov     [rsp+1E0h+AllocationSize], rax
0x1400acfd7  mov     [rbp+0E0h+var_158], rsi
0x1400acfdb  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1400acfe0  test    edi, edi
0x1400acfe2  js      loc_1400AD068
0x1400acfe8  mov     rax, [rbp+0E0h+FileHandle]
0x1400acfec  mov     rdx, [rbp+0E0h+var_140]
0x1400acff0  mov     [rbp+0E0h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x1400acff8  mov     [rdx], rax
0x1400acffb  mov     eax, cs:dword_1400876D0
0x1400ad001  cmp     eax, 5
0x1400ad004  jbe     short loc_1400AD047
0x1400ad006  mov     r9d, 800h
0x1400ad00c  lea     rcx, dword_1400876D0
0x1400ad013  mov     edx, r9d
0x1400ad016  call    _tlgKeywordOn
0x1400ad01b  test    al, al
0x1400ad01d  jz      short loc_1400AD047
0x1400ad01f  lea     rax, aFileWzSuccessf_0; " (file '%wZ')Successfully opened backin"...
0x1400ad026  mov     qword ptr [rsp+1E0h+FileAttributes], rbx; char
0x1400ad02b  mov     edx, 0CE3h; int
0x1400ad030  mov     [rsp+1E0h+AllocationSize], rax; char *
0x1400ad035  mov     r8d, 5; int
0x1400ad03b  lea     rcx, aVhdmpiopenback; "VhdmpiOpenBackingFileWithOptions"
0x1400ad042  call    TraceEvents
0x1400ad047  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, 1
0x1400ad04e  jz      loc_1400AD121
0x1400ad054  mov     dword ptr [rsp+1E0h+AllocationSize], 0
0x1400ad05c  lea     rdx, FileWrapperHandleCreateEnd
0x1400ad063  jmp     loc_1400AD118
0x1400ad068  mov     r8d, 0C0000043h
0x1400ad06e  cmp     edi, r8d
0x1400ad071  jz      short loc_1400AD0B3
0x1400ad073  mov     eax, cs:dword_1400876D0
0x1400ad079  cmp     eax, 2
0x1400ad07c  jbe     loc_1400AD104
0x1400ad082  mov     r9d, 800h
0x1400ad088  lea     rcx, dword_1400876D0
0x1400ad08f  mov     edx, r9d
0x1400ad092  call    _tlgKeywordOn
0x1400ad097  test    al, al
0x1400ad099  jz      short loc_1400AD104
0x1400ad09b  mov     edx, 0CEDh
0x1400ad0a0  mov     [rsp+1E0h+ShareAccess], edi
0x1400ad0a4  lea     rax, aFileWzFailedTo_11; " (file '%wZ') Failed to open backing fi"...
0x1400ad0ab  mov     r8d, 2
0x1400ad0b1  jmp     short loc_1400AD0EE
0x1400ad0b3  mov     eax, cs:dword_1400876D0
0x1400ad0b9  cmp     eax, 4
0x1400ad0bc  jbe     short loc_1400AD104
0x1400ad0be  mov     r9d, 800h
0x1400ad0c4  lea     rcx, dword_1400876D0
0x1400ad0cb  mov     edx, r9d
0x1400ad0ce  call    _tlgKeywordOn
0x1400ad0d3  test    al, al
0x1400ad0d5  jz      short loc_1400AD104
0x1400ad0d7  mov     [rsp+1E0h+ShareAccess], r8d
0x1400ad0dc  lea     rax, aFileWzFailedTo_4; " (file '%wZ')Failed to open backing fil"...
0x1400ad0e3  mov     r8d, 4; int
0x1400ad0e9  mov     edx, 0CF6h; int
0x1400ad0ee  mov     qword ptr [rsp+1E0h+FileAttributes], rbx; char
  ... truncated ...
```
