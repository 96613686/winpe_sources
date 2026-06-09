# CDVRRingBufferWriter::PrepareAFreeWriterNode(ushort const *,ulong,void * *,ulong,unsigned __int64,unsigned __int64,ulong,CDVRRingBufferWriter::ASF_RECORDER_NODE *,int,_LIST_ENTRY * &)

- ea: `0x18006df48`
- end: `0x18006e992`
- name: `?PrepareAFreeWriterNode@CDVRRingBufferWriter@@IEAAJPEBGKPEAPEAXK_K2KPEAUASF_RECORDER_NODE@1@HAEAPEAU_LIST_ENTRY@@@Z`
- size: `2634`
- prototype: `__int64 __fastcall(CDVRRingBufferWriter *__hidden this, const unsigned __int16 *, unsigned int, void **, unsigned int, unsigned __int64, unsigned __int64, unsigned int, struct CDVRRingBufferWriter::ASF_RECORDER_NODE *, int, struct _LIST_ENTRY **)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180069bb8`
- `0x18006b020`

## callees

- `0x1800017a0`
- `0x1800017e0`
- `0x180001c00`
- `0x18005faec`
- `0x180068d6c`
- `0x180069a9c`
- `0x180069b8c`
- `0x18006df48`
- `0x18006eb20`
- `0x180077c1c`
- `0x18007c3a8`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18006e011`
- `KERNEL32!WaitForSingleObject` at `0x18006e027`
- `KERNEL32!WaitForSingleObject` at `0x18006e011`
- `KERNEL32!WaitForSingleObject` at `0x18006e027`
- `KERNEL32!SetEvent` at `0x18006e8dd`
- `KERNEL32!SetEvent` at `0x1800b46e1`
- `KERNEL32!SetEvent` at `0x18006e8dd`
- `KERNEL32!SetEvent` at `0x1800b46e1`
- `KERNEL32!ResetEvent` at `0x18006e7df`
- `KERNEL32!ResetEvent` at `0x18006e7df`
- `KERNEL32!GetLastError` at `0x18006e038`
- `KERNEL32!GetLastError` at `0x18006e4a3`
- `KERNEL32!GetLastError` at `0x18006e4d2`
- `KERNEL32!GetLastError` at `0x18006e80d`
- `KERNEL32!GetLastError` at `0x18006e038`
- `KERNEL32!GetLastError` at `0x18006e4a3`
- `KERNEL32!GetLastError` at `0x18006e4d2`
- `KERNEL32!GetLastError` at `0x18006e80d`
- `KERNEL32!GetFileAttributesW` at `0x18006e498`
- `KERNEL32!GetFileAttributesW` at `0x18006e498`
- `KERNEL32!SetFileAttributesW` at `0x18006e4c8`
- `KERNEL32!SetFileAttributesW` at `0x18006e4c8`
- `KERNEL32!QueueUserWorkItem` at `0x18006e803`
- `KERNEL32!QueueUserWorkItem` at `0x18006e803`
- `WMVCore!WMCreateWriter` at `0x18006e0fa`
- `WMVCore!WMCreateWriter` at `0x18006e0fa`
- `sbeio!DVRCreateDVRFileSink` at `0x18006e21b`
- `sbeio!DVRCreateDVRFileSink` at `0x18006e21b`

## pseudocode

```c
__int64 __fastcall CDVRRingBufferWriter::PrepareAFreeWriterNode(
        CDVRRingBufferWriter *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        void **a4,
        unsigned int a5,
        unsigned __int64 a6,
        unsigned __int64 a7,
        unsigned int a8,
        struct CDVRRingBufferWriter::ASF_RECORDER_NODE *a9,
        int a10,
        struct _LIST_ENTRY **a11)
{
  unsigned int v12; // r13d
  char *v13; // r14
  struct _LIST_ENTRY *v14; // rsi
  __int64 v15; // rdi
  DWORD v16; // eax
  CDVRRingBufferWriter::ASF_WRITER_NODE *v17; // rax
  unsigned __int64 v18; // rdx
  __int64 v19; // rax
  IWMWriter *v20; // rcx
  int v21; // eax
  unsigned int v22; // eax
  _QWORD *v23; // r14
  signed int v24; // r14d
  void *v25; // r10
  CPVRAsyncWriterCOM *v26; // r13
  unsigned int v27; // edx
  const WCHAR *v28; // r14
  DWORD FileAttributesW; // eax
  DWORD LastError; // eax
  int v31; // r14d
  unsigned int v32; // ecx
  unsigned int v33; // r13d
  __int64 v34; // rdx
  unsigned int RegDWORD; // eax
  WCHAR *v36; // r15
  int v37; // r12d
  signed int v38; // eax
  struct _LIST_ENTRY *Flink; // rax
  struct _LIST_ENTRY *Blink; // rcx
  __int64 v41; // rcx
  int v43; // [rsp+28h] [rbp-140h]
  int v44; // [rsp+28h] [rbp-140h]
  int v45; // [rsp+70h] [rbp-F8h] BYREF
  int v46; // [rsp+74h] [rbp-F4h]
  int v47; // [rsp+78h] [rbp-F0h]
  LPCWSTR lpFileName; // [rsp+80h] [rbp-E8h]
  int v49; // [rsp+88h] [rbp-E0h]
  _QWORD *p_Flink; // [rsp+90h] [rbp-D8h]
  struct _LIST_ENTRY *i; // [rsp+98h] [rbp-D0h]
  unsigned int v52; // [rsp+A0h] [rbp-C8h]
  signed int v53; // [rsp+A4h] [rbp-C4h] BYREF
  unsigned int v54; // [rsp+A8h] [rbp-C0h]
  const unsigned __int16 *v55; // [rsp+B0h] [rbp-B8h]
  struct _LIST_ENTRY **v56; // [rsp+B8h] [rbp-B0h]
  void **v57; // [rsp+C0h] [rbp-A8h]
  struct _LIST_ENTRY **v58; // [rsp+C8h] [rbp-A0h]
  void **v59; // [rsp+D0h] [rbp-98h] BYREF
  int v60; // [rsp+D8h] [rbp-90h]
  int v61; // [rsp+DCh] [rbp-8Ch]
  int v62; // [rsp+E0h] [rbp-88h]
  __int64 v63; // [rsp+E8h] [rbp-80h] BYREF
  __int64 v64; // [rsp+F0h] [rbp-78h] BYREF
  __int64 v65; // [rsp+F8h] [rbp-70h] BYREF
  IWMWriter *ppWriter; // [rsp+100h] [rbp-68h] BYREF
  __int64 v67; // [rsp+108h] [rbp-60h] BYREF
  __int64 v68; // [rsp+110h] [rbp-58h] BYREF
  int v69; // [rsp+118h] [rbp-50h] BYREF
  unsigned int v70; // [rsp+11Ch] [rbp-4Ch] BYREF
  int v71; // [rsp+120h] [rbp-48h] BYREF

  v57 = a4;
  v52 = a3;
  lpFileName = a2;
  v12 = a5;
  v54 = a5;
  v55 = a2;
  v58 = a11;
  v56 = a11;
  v45 = -2147467259;
  v13 = (char *)this + 456;
  i = (struct _LIST_ENTRY *)((char *)this + 456);
  v47 = 0;
  v49 = 0;
  v46 = 0;
  p_Flink = 0;
  v63 = 0;
  v70 = 0;
  v65 = 0;
  v14 = (struct _LIST_ENTRY *)*((_QWORD *)this + 57);
  for ( i = v14; ; i = v14 )
  {
    if ( v14 == (struct _LIST_ENTRY *)v13 )
      goto LABEL_10;
    v15 = (__int64)&v14[-1];
    p_Flink = &v14[-1].Flink;
    if ( !WaitForSingleObject(v14[5].Flink, 0) && !*(_QWORD *)(v15 + 72) )
      break;
LABEL_8:
    v14 = v14->Flink;
  }
  v16 = WaitForSingleObject(*(HANDLE *)(v15 + 88), 0);
  if ( v16 != 258 )
  {
    if ( v16 )
      GetLastError();
    goto LABEL_8;
  }
  if ( v14 != (struct _LIST_ENTRY *)v13 )
    goto LABEL_20;
LABEL_10:
  v17 = (CDVRRingBufferWriter::ASF_WRITER_NODE *)operator new(0x70u);
  if ( v17 )
    v15 = CDVRRingBufferWriter::ASF_WRITER_NODE::ASF_WRITER_NODE(v17, &v45);
  else
    v15 = 0;
  p_Flink = (_QWORD *)v15;
  if ( !v15 )
  {
    v45 = -2147024882;
    goto LABEL_15;
  }
  if ( v45 < 0 )
  {
    CDVRRingBufferWriter::ASF_WRITER_NODE::`scalar deleting destructor'(
      (CDVRRingBufferWriter::ASF_WRITER_NODE *)v15,
      v18);
    v15 = 0;
    p_Flink = 0;
LABEL_15:
    v14 = 0;
    i = 0;
    goto LABEL_95;
  }
  v19 = *(_QWORD *)v13;
  if ( *(char **)(*(_QWORD *)v13 + 8LL) != v13 )
LABEL_94:
    __fastfail(3u);
  v14 = (struct _LIST_ENTRY *)(v15 + 16);
  *(_QWORD *)(v15 + 16) = v19;
  *(_QWORD *)(v15 + 24) = v13;
  *(_QWORD *)(v19 + 8) = v15 + 16;
  *(_QWORD *)v13 = v15 + 16;
  i = (struct _LIST_ENTRY *)(v15 + 16);
LABEL_20:
  v20 = *(IWMWriter **)(v15 + 32);
  if ( !v20 )
  {
    ppWriter = 0;
    v45 = WMCreateWriter(0, &ppWriter);
    if ( v45 < 0 )
      goto LABEL_95;
    *(_QWORD *)(v15 + 32) = ppWriter;
    v20 = ppWriter;
  }
  if ( !*(_QWORD *)(v15 + 40) )
  {
    v67 = 0;
    v45 = ((__int64 (__fastcall *)(IWMWriter *, GUID *, __int64 *))v20->lpVtbl->QueryInterface)(
            v20,
            &IID_IWMWriterAdvanced3,
            &v67);
    if ( v45 < 0 )
      goto LABEL_95;
    *(_QWORD *)(v15 + 40) = v67;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 136LL))(v67);
  }
  if ( !*(_QWORD *)(v15 + 48) )
  {
    v68 = 0;
    v45 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(v15 + 32))(
            *(_QWORD *)(v15 + 32),
            &IID_IWMHeaderInfo,
            &v68);
    if ( v45 < 0 )
      goto LABEL_95;
    *(_QWORD *)(v15 + 48) = v68;
  }
  if ( a9 )
  {
    v21 = *(_DWORD *)(v15 + 108);
    if ( *((_QWORD *)a9 + 3) )
      v22 = v21 & 0xFFFFFFFD;
    else
      v22 = v21 | 2;
    *(_DWORD *)(v15 + 108) = v22;
  }
  else
  {
    *(_DWORD *)(v15 + 108) &= ~2u;
  }
  v23 = (_QWORD *)(v15 + 56);
  v45 = DVRCreateDVRFileSink(*((_QWORD *)this + 9), *((_QWORD *)this + 10), v52, v57, *((_DWORD *)this + 38), v15 + 56);
  if ( v45 < 0 )
  {
LABEL_95:
    v37 = v47;
    v36 = (WCHAR *)lpFileName;
    goto LABEL_96;
  }
  if ( *((_QWORD *)this + 16) )
  {
    v64 = 0;
    v45 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v23)(*v23, &IID_IDVRFileSink2, &v64);
    if ( v45 < 0 )
      goto LABEL_95;
    v24 = 0;
    v53 = 0;
    v25 = operator new(0xA8u);
    if ( v25 )
    {
      v59 = &CPVRStreamProf::`vftable';
      v60 = *((_DWORD *)this + 24);
      v61 = *((_DWORD *)this + 25);
      v62 = *((_DWORD *)this + 26);
      v26 = (CPVRAsyncWriterCOM *)CPVRAsyncWriterCOM::CPVRAsyncWriterCOM(
                                    v25,
                                    *((unsigned int *)this + 34),
                                    *((unsigned int *)this + 35),
                                    *((unsigned int *)this + 36),
                                    *((_DWORD *)this + 37),
                                    *((_QWORD *)this + 16),
                                    *((_QWORD *)this + 20),
                                    v52,
                                    v57,
                                    *((_QWORD *)this + 14),
                                    *((_QWORD *)this + 15),
                                    &v59,
                                    &v53);
      v24 = v53;
    }
    else
    {
      v26 = 0;
    }
    if ( !v26 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
      v45 = -2147024882;
      goto LABEL_95;
    }
    if ( v24 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
      if ( v24 > 0 )
        v24 = (unsigned __int16)v24 | 0x80070000;
      v45 = v24;
      CPVRAsyncWriterCOM::`scalar deleting destructor'(v26, v27);
      goto LABEL_95;
    }
    (*(void (__fastcall **)(CPVRAsyncWriterCOM *))(*(_QWORD *)v26 + 8LL))(v26);
    v45 = (*(__int64 (__fastcall **)(__int64, CPVRAsyncWriterCOM *))(*(_QWORD *)v64 + 80LL))(v64, v26);
    (*(void (__fastcall **)(CPVRAsyncWriterCOM *))(*(_QWORD *)v26 + 16LL))(v26);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
    if ( v45 < 0 )
      goto LABEL_95;
    v23 = (_QWORD *)(v15 + 56);
    v12 = a5;
  }
  v45 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v23)(*v23, &IID_IWMRegisterCallback, &v65);
  if ( v45 < 0 )
    goto LABEL_95;
  v45 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v65 + 24LL))(
          v65,
          ((unsigned __int64)this + 8) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64),
          0);
  if ( v45 < 0 )
    goto LABEL_95;
  if ( a9 || v12 )
  {
LABEL_59:
    v32 = a5;
    v31 = 1;
    goto LABEL_60;
  }
  v28 = lpFileName;
  FileAttributesW = GetFileAttributesW(lpFileName);
  if ( FileAttributesW != -1 )
  {
    if ( !SetFileAttributesW(v28, FileAttributesW & 0xFFFFDFF9) )
    {
      GetLastError();
      v31 = 1;
      v32 = 1;
      goto LABEL_60;
    }
    goto LABEL_59;
  }
  LastError = GetLastError();
  v31 = 1;
  v32 = 1;
  if ( LastError == 2 )
    v32 = v54;
LABEL_60:
  if ( !a9 )
  {
    v33 = 1;
    if ( v32 )
      goto LABEL_66;
LABEL_65:
    v33 = 0;
    goto LABEL_66;
  }
  if ( (*((_BYTE *)a9 + 64) & 8) == 0 )
    goto LABEL_65;
  v33 = 1;
LABEL_66:
  v45 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v15 + 56) + 24LL))(*(_QWORD *)(v15 + 56), v33);
  if ( v45 < 0 )
    goto LABEL_95;
  v34 = *((unsigned int *)this + 15);
  if ( (_DWORD)v34 != -1 )
  {
    v45 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(v15 + 56) + 32LL))(
            *(_QWORD *)(v15 + 56),
            v34,
            *((unsigned int *)this + 16));
    if ( v45 < 0 )
      goto LABEL_95;
    if ( v33 )
    {
      v45 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned int *))(**(_QWORD **)(v15 + 56) + 64LL))(
              *(_QWORD *)(v15 + 56),
              ((unsigned int)(*((_QWORD *)this + 2) / 0x2710uLL) + 10000) / *((_DWORD *)this + 16),
              &v70);
      if ( v45 < 0 )
        goto LABEL_95;
      v45 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v15 + 56) + 48LL))(*(_QWORD *)(v15 + 56), v70);
      if ( v45 < 0 )
        goto LABEL_95;
    }
  }
  v45 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(v15 + 56))(
          *(_QWORD *)(v15 + 56),
          &IID_IWMWriterSink,
          &v63);
  if ( v45 < 0 )
    goto LABEL_95;
  v45 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v15 + 40) + 40LL))(*(_QWORD *)(v15 + 40), v63);
  if ( v45 < 0 )
    goto LABEL_95;
  v49 = 1;
  v45 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v15 + 32) + 32LL))(
          *(_QWORD *)(v15 + 32),
          *((_QWORD *)this + 3));
  if ( v45 < 0 )
    goto LABEL_95;
  v69 = 0;
  v45 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)(v15 + 32) + 48LL))(*(_QWORD *)(v15 + 32), &v69);
  if ( v45 < 0 )
    goto LABEL_95;
  while ( v69 )
  {
    v45 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)(v15 + 32) + 64LL))(
            *(_QWORD *)(v15 + 32),
            (unsigned int)--v69,
            0);
    if ( v45 < 0 )
      goto LABEL_95;
  }
  RegDWORD = GetRegDWORD(*((HKEY *)this + 9), L"SyncTolerance", 0);
  v45 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v15 + 40) + 96LL))(*(_QWORD *)(v15 + 40), RegDWORD);
  if ( v45 < 0 )
    goto LABEL_95;
  v71 = *((_DWORD *)this + 16);
  LOWORD(v43) = 4;
  v45 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const wchar_t *, _QWORD, int *, int))(**(_QWORD **)(v15 + 48) + 48LL))(
          *(_QWORD *)(v15 + 48),
          0,
          L"DVR Index Granularity",
          0,
          &v71,
          v43);
  if ( v45 < 0 )
    goto LABEL_95;
  LOWORD(v44) = 16;
  v45 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const wchar_t *, __int64, GUID *, int))(**(_QWORD **)(v15 + 48) + 48LL))(
          *(_QWORD *)(v15 + 48),
          0,
          L"DVR File Version",
          2,
          &CDVRFileCollection::m_guidV1,
          v44);
  if ( v45 < 0 )
    goto LABEL_95;
  *(_QWORD *)v15 = a6;
  *(_QWORD *)(v15 + 8) = a7;
  *(_DWORD *)(v15 + 80) = a8;
  *(_DWORD *)(v15 + 104) = 0;
  if ( !a9 || (*((_BYTE *)a9 + 64) & 8) != 0 )
    *(_QWORD *)(v15 + 64) = lpFileName;
  v36 = 0;
  v55 = 0;
  *(_QWORD *)(v15 + 72) = a9;
  ResetEvent(*(HANDLE *)(v15 + 96));
  v37 = 1;
  v47 = 1;
  if ( a10 )
  {
    CDVRRingBufferWriter::ProcessOpenRequest((LPVOID)v15);
    goto LABEL_91;
  }
  if ( QueueUserWorkItem(CDVRRingBufferWriter::ProcessOpenRequest, (PVOID)v15, 0x10u) )
  {
LABEL_91:
    v46 = 1;
    Flink = v14->Flink;
    if ( v14->Flink->Blink == v14 )
    {
      Blink = v14->Blink;
      if ( Blink->Flink == v14 )
      {
        Blink->Flink = Flink;
        Flink->Blink = Blink;
        v14->Blink = 0;
        v14->Flink = 0;
        v45 = 0;
        goto LABEL_97;
      }
    }
    goto LABEL_94;
  }
  v38 = GetLastError();
  if ( v38 > 0 )
    v38 = (unsigned __int16)v38 | 0x80070000;
  v45 = v38;
LABEL_96:
  v31 = v46;
LABEL_97:
  if ( v45 >= 0 )
  {
    *v58 = v14;
  }
  else
  {
    *v58 = 0;
    if ( v37 && !v31 )
    {
      *(_QWORD *)v15 = 0;
      *(_QWORD *)(v15 + 8) = 0;
      *(_DWORD *)(v15 + 80) = 0;
      *(_QWORD *)(v15 + 72) = 0;
      operator delete(*(void **)(v15 + 64), v18);
      *(_QWORD *)(v15 + 64) = 0;
      SetEvent(*(HANDLE *)(v15 + 96));
    }
    if ( v49 )
    {
      if ( !v31 )
      {
        (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v15 + 40) + 48LL))(*(_QWORD *)(v15 + 40), v63);
        goto LABEL_104;
      }
    }
    else
    {
LABEL_104:
      if ( !v31 )
      {
        if ( v15 )
        {
          v41 = *(_QWORD *)(v15 + 56);
          if ( v41 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
            *(_QWORD *)(v15 + 56) = 0;
          }
        }
      }
    }
    operator delete(v36, v18);
  }
  if ( v63 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
  if ( v65 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
  return (unsigned int)v45;
}

```

## disassembly

```asm
0x18006df48  mov     r11, rsp
0x18006df4b  push    rbx
0x18006df4c  push    rsi
0x18006df4d  push    rdi
0x18006df4e  push    r12
0x18006df50  push    r13
0x18006df52  push    r14
0x18006df54  push    r15
0x18006df56  sub     rsp, 130h
0x18006df5d  mov     rax, cs:__security_cookie
0x18006df64  xor     rax, rsp
0x18006df67  mov     [rsp+168h+var_40], rax
0x18006df6f  mov     [rsp+168h+var_A8], r9
0x18006df77  mov     [rsp+168h+var_C8], r8d
0x18006df7f  mov     [r11-0E8h], rdx
0x18006df86  mov     r15, rcx
0x18006df89  mov     r13d, [r11+28h]
0x18006df8d  mov     [rsp+168h+var_C0], r13d
0x18006df95  mov     [r11-0B8h], rdx
0x18006df9c  mov     rax, [rsp+168h+arg_50]
0x18006dfa4  mov     [rsp+168h+var_A0], rax
0x18006dfac  mov     [rsp+168h+var_B0], rax
0x18006dfb4  mov     [rsp+168h+var_F8], 80004005h
0x18006dfbc  lea     r14, [rcx+1C8h]
0x18006dfc3  mov     [r11-0D0h], r14
0x18006dfca  xor     ebx, ebx
0x18006dfcc  mov     [rsp+168h+var_F0], ebx
0x18006dfd0  mov     [rsp+168h+var_E0], ebx
0x18006dfd7  mov     [rsp+168h+var_F4], ebx
0x18006dfdb  mov     edi, ebx
0x18006dfdd  mov     [r11-0D8h], rbx
0x18006dfe4  mov     [r11-80h], rbx
0x18006dfe8  mov     [r11-4Ch], ebx
0x18006dfec  mov     [r11-70h], rbx
0x18006dff0  mov     rsi, [r14]
0x18006dff3  mov     [r11-0D0h], rsi
0x18006dffa  cmp     rsi, r14
0x18006dffd  jz      short loc_18006E054
0x18006dfff  lea     rdi, [rsi-10h]
0x18006e003  mov     [rsp+168h+var_D8], rdi
0x18006e00b  xor     edx, edx; dwMilliseconds
0x18006e00d  mov     rcx, [rdi+60h]; hHandle
0x18006e011  call    cs:__imp_WaitForSingleObject
0x18006e017  test    eax, eax
0x18006e019  jnz     short loc_18006E03E
0x18006e01b  cmp     [rdi+48h], rbx
0x18006e01f  jnz     short loc_18006E03E
0x18006e021  xor     edx, edx; dwMilliseconds
0x18006e023  mov     rcx, [rdi+58h]; hHandle
0x18006e027  call    cs:__imp_WaitForSingleObject
0x18006e02d  cmp     eax, 102h
0x18006e032  jz      short loc_18006E04B
0x18006e034  test    eax, eax
0x18006e036  jz      short loc_18006E03E
0x18006e038  call    cs:__imp_GetLastError
0x18006e03e  mov     rsi, [rsi]
0x18006e041  mov     [rsp+168h+var_D0], rsi
0x18006e049  jmp     short loc_18006DFFA
0x18006e04b  cmp     rsi, r14
0x18006e04e  jnz     loc_18006E0E1
0x18006e054  mov     ecx, 70h ; 'p'; Size
0x18006e059  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006e05e  test    rax, rax
0x18006e061  jz      short loc_18006E075
0x18006e063  lea     rdx, [rsp+168h+var_F8]; int *
0x18006e068  mov     rcx, rax; this
0x18006e06b  call    ??0ASF_WRITER_NODE@CDVRRingBufferWriter@@QEAA@PEAJ@Z; CDVRRingBufferWriter::ASF_WRITER_NODE::ASF_WRITER_NODE(long *)
0x18006e070  mov     rdi, rax
0x18006e073  jmp     short loc_18006E078
0x18006e075  mov     rdi, rbx
0x18006e078  mov     [rsp+168h+var_D8], rdi
0x18006e080  test    rdi, rdi
0x18006e083  jnz     short loc_18006E09D
0x18006e085  mov     [rsp+168h+var_F8], 8007000Eh
0x18006e08d  mov     rsi, rbx
0x18006e090  mov     [rsp+168h+var_D0], rbx
0x18006e098  jmp     loc_18006E85F
0x18006e09d  mov     eax, [rsp+168h+var_F8]
0x18006e0a1  test    eax, eax
0x18006e0a3  jns     short loc_18006E0BA
0x18006e0a5  mov     rcx, rdi; this
0x18006e0a8  call    ??_GASF_WRITER_NODE@CDVRRingBufferWriter@@QEAAPEAXI@Z; CDVRRingBufferWriter::ASF_WRITER_NODE::`scalar deleting destructor'(uint)
0x18006e0ad  mov     rdi, rbx
0x18006e0b0  mov     [rsp+168h+var_D8], rbx
0x18006e0b8  jmp     short loc_18006E08D
0x18006e0ba  mov     rax, [r14]
0x18006e0bd  cmp     [rax+8], r14
0x18006e0c1  jnz     loc_18006E858
0x18006e0c7  lea     rsi, [rdi+10h]
0x18006e0cb  mov     [rsi], rax
0x18006e0ce  mov     [rsi+8], r14
0x18006e0d2  mov     [rax+8], rsi
0x18006e0d6  mov     [r14], rsi
0x18006e0d9  mov     [rsp+168h+var_D0], rsi
0x18006e0e1  mov     rcx, [rdi+20h]; pUnkCert
0x18006e0e5  test    rcx, rcx
0x18006e0e8  jnz     short loc_18006E124
0x18006e0ea  mov     [rsp+168h+ppWriter], rbx
0x18006e0f2  lea     rdx, [rsp+168h+ppWriter]; ppWriter
0x18006e0fa  call    cs:__imp_WMCreateWriter
0x18006e100  mov     [rsp+168h+var_F8], eax
0x18006e104  mov     eax, [rsp+168h+var_F8]
0x18006e108  test    eax, eax
0x18006e10a  js      loc_18006E85F
0x18006e110  mov     rax, [rsp+168h+ppWriter]
0x18006e118  mov     [rdi+20h], rax
0x18006e11c  mov     rcx, [rsp+168h+ppWriter]
0x18006e124  cmp     [rdi+28h], rbx
0x18006e128  jnz     short loc_18006E17F
0x18006e12a  mov     [rsp+168h+var_60], rbx
0x18006e132  mov     rax, [rcx]
0x18006e135  lea     r8, [rsp+168h+var_60]
0x18006e13d  lea     rdx, IID_IWMWriterAdvanced3
0x18006e144  mov     rax, [rax]
0x18006e147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e14c  mov     [rsp+168h+var_F8], eax
0x18006e150  mov     eax, [rsp+168h+var_F8]
0x18006e154  test    eax, eax
0x18006e156  js      loc_18006E85F
0x18006e15c  mov     rax, [rsp+168h+var_60]
0x18006e164  mov     [rdi+28h], rax
0x18006e168  mov     rcx, [rsp+168h+var_60]
0x18006e170  mov     rax, [rcx]
0x18006e173  mov     rax, [rax+88h]
0x18006e17a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e17f  cmp     [rdi+30h], rbx
0x18006e183  jnz     short loc_18006E1C7
0x18006e185  mov     [rsp+168h+var_58], rbx
0x18006e18d  mov     rcx, [rdi+20h]
0x18006e191  mov     rax, [rcx]
0x18006e194  lea     r8, [rsp+168h+var_58]
0x18006e19c  lea     rdx, IID_IWMHeaderInfo
0x18006e1a3  mov     rax, [rax]
0x18006e1a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e1ab  mov     [rsp+168h+var_F8], eax
0x18006e1af  mov     eax, [rsp+168h+var_F8]
0x18006e1b3  test    eax, eax
0x18006e1b5  js      loc_18006E85F
0x18006e1bb  mov     rax, [rsp+168h+var_58]
0x18006e1c3  mov     [rdi+30h], rax
0x18006e1c7  mov     r12, [rsp+168h+arg_40]
0x18006e1cf  test    r12, r12
0x18006e1d2  jz      short loc_18006E1EB
0x18006e1d4  mov     eax, [rdi+6Ch]
0x18006e1d7  cmp     [r12+18h], rbx
0x18006e1dc  jnz     short loc_18006E1E3
0x18006e1de  or      eax, 2
0x18006e1e1  jmp     short loc_18006E1E6
0x18006e1e3  and     eax, 0FFFFFFFDh
0x18006e1e6  mov     [rdi+6Ch], eax
0x18006e1e9  jmp     short loc_18006E1EF
0x18006e1eb  and     dword ptr [rdi+6Ch], 0FFFFFFFDh
0x18006e1ef  lea     r14, [rdi+38h]
0x18006e1f3  mov     [rsp+168h+var_140], r14
0x18006e1f8  mov     eax, [r15+98h]
0x18006e1ff  mov     dword ptr [rsp+168h+var_148], eax
0x18006e203  mov     r9, [rsp+168h+var_A8]
0x18006e20b  mov     r8d, [rsp+168h+var_C8]
0x18006e213  mov     rdx, [r15+50h]
0x18006e217  mov     rcx, [r15+48h]
0x18006e21b  call    cs:__imp_DVRCreateDVRFileSink
0x18006e221  mov     [rsp+168h+var_F8], eax
0x18006e225  mov     eax, [rsp+168h+var_F8]
0x18006e229  test    eax, eax
0x18006e22b  js      loc_18006E85F
0x18006e231  cmp     [r15+80h], rbx
0x18006e238  jz      loc_18006E41F
0x18006e23e  mov     [rsp+168h+var_78], rbx
0x18006e246  mov     rcx, [r14]
0x18006e249  mov     rax, [rcx]
0x18006e24c  lea     r8, [rsp+168h+var_78]
0x18006e254  lea     rdx, IID_IDVRFileSink2
0x18006e25b  mov     rax, [rax]
0x18006e25e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e263  mov     [rsp+168h+var_F8], eax
0x18006e267  mov     eax, [rsp+168h+var_F8]
0x18006e26b  test    eax, eax
0x18006e26d  js      loc_18006E85F
0x18006e273  mov     r14d, ebx
0x18006e276  mov     [rsp+168h+var_C4], ebx
0x18006e27d  mov     ecx, 0A8h; Size
0x18006e282  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006e287  mov     r10, rax
0x18006e28a  test    rax, rax
0x18006e28d  jz      loc_18006E354
0x18006e293  lea     rax, ??_7CPVRStreamProf@@6B@; const CPVRStreamProf::`vftable'
0x18006e29a  mov     [rsp+168h+var_98], rax
0x18006e2a2  mov     ecx, [r15+60h]
0x18006e2a6  mov     [rsp+168h+var_90], ecx
0x18006e2ad  mov     ecx, [r15+64h]
0x18006e2b1  mov     [rsp+168h+var_8C], ecx
0x18006e2b8  mov     ecx, [r15+68h]
0x18006e2bc  mov     [rsp+168h+var_88], ecx
0x18006e2c3  lea     rax, [rsp+168h+var_C4]
0x18006e2cb  mov     [rsp+168h+var_108], rax
0x18006e2d0  lea     rax, [rsp+168h+var_98]
0x18006e2d8  mov     [rsp+168h+var_110], rax
0x18006e2dd  mov     rax, [r15+78h]
0x18006e2e1  mov     [rsp+168h+var_118], rax
0x18006e2e6  mov     rax, [r15+70h]
0x18006e2ea  mov     [rsp+168h+var_120], rax
0x18006e2ef  mov     rax, [rsp+168h+var_A8]
0x18006e2f7  mov     [rsp+168h+var_128], rax
0x18006e2fc  mov     eax, [rsp+168h+var_C8]
0x18006e303  mov     [rsp+168h+var_130], eax
0x18006e307  mov     rax, [r15+0A0h]
0x18006e30e  mov     [rsp+168h+var_138], rax
0x18006e313  mov     rax, [r15+80h]
0x18006e31a  mov     [rsp+168h+var_140], rax
0x18006e31f  mov     eax, [r15+94h]
0x18006e326  mov     dword ptr [rsp+168h+var_148], eax
0x18006e32a  mov     r9d, [r15+90h]
0x18006e331  mov     r8d, [r15+8Ch]
0x18006e338  mov     edx, [r15+88h]
0x18006e33f  mov     rcx, r10
0x18006e342  call    ??0CPVRAsyncWriterCOM@@QEAA@KKKKPEAVCAsyncIo@@PEAVCPVRIOCounters@@KPEAPEAXP6AXPEAXK_J4@Z3VCPVRStreamProf@@PEAK@Z; CPVRAsyncWriterCOM::CPVRAsyncWriterCOM(ulong,ulong,ulong,ulong,CAsyncIo *,CPVRIOCounters *,ulong,void * *,void (*)(void *,ulong,__int64,__int64),void *,CPVRStreamProf,ulong *)
0x18006e347  mov     r13, rax
0x18006e34a  mov     r14d, [rsp+168h+var_C4]
0x18006e352  jmp     short loc_18006E357
0x18006e354  mov     r13, rbx
0x18006e357  test    r13, r13
0x18006e35a  jnz     short loc_18006E37D
0x18006e35c  mov     rcx, [rsp+168h+var_78]
0x18006e364  mov     rax, [rcx]
0x18006e367  mov     rax, [rax+10h]
0x18006e36b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e370  mov     [rsp+168h+var_F8], 8007000Eh
0x18006e378  jmp     loc_18006E85F
0x18006e37d  test    r14d, r14d
0x18006e380  jz      short loc_18006E3B8
0x18006e382  mov     rcx, [rsp+168h+var_78]
0x18006e38a  mov     rax, [rcx]
0x18006e38d  mov     rax, [rax+10h]
0x18006e391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e396  test    r14d, r14d
0x18006e399  jle     short loc_18006E3A6
0x18006e39b  movzx   r14d, r14w
0x18006e39f  or      r14d, 80070000h
0x18006e3a6  mov     [rsp+168h+var_F8], r14d
0x18006e3ab  mov     rcx, r13; this
0x18006e3ae  call    ??_GCPVRAsyncWriterCOM@@QEAAPEAXI@Z; CPVRAsyncWriterCOM::`scalar deleting destructor'(uint)
0x18006e3b3  jmp     loc_18006E85F
0x18006e3b8  mov     rax, [r13+0]
0x18006e3bc  mov     rcx, r13
0x18006e3bf  mov     rax, [rax+8]
0x18006e3c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e3c8  mov     rcx, [rsp+168h+var_78]
0x18006e3d0  mov     rax, [rcx]
0x18006e3d3  mov     rdx, r13
0x18006e3d6  mov     rax, [rax+50h]
0x18006e3da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e3df  mov     [rsp+168h+var_F8], eax
0x18006e3e3  mov     rax, [r13+0]
0x18006e3e7  mov     rcx, r13
0x18006e3ea  mov     rax, [rax+10h]
0x18006e3ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e3f3  mov     rcx, [rsp+168h+var_78]
0x18006e3fb  mov     rax, [rcx]
0x18006e3fe  mov     rax, [rax+10h]
0x18006e402  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e407  mov     eax, [rsp+168h+var_F8]
0x18006e40b  test    eax, eax
0x18006e40d  js      loc_18006E85F
0x18006e413  lea     r14, [rdi+38h]
0x18006e417  mov     r13d, [rsp+168h+arg_20]
0x18006e41f  mov     rcx, [r14]
0x18006e422  mov     rax, [rcx]
0x18006e425  lea     r8, [rsp+168h+var_70]
0x18006e42d  lea     rdx, IID_IWMRegisterCallback
0x18006e434  mov     rax, [rax]
0x18006e437  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e43c  mov     [rsp+168h+var_F8], eax
0x18006e440  mov     eax, [rsp+168h+var_F8]
0x18006e444  test    eax, eax
0x18006e446  js      loc_18006E85F
0x18006e44c  mov     rcx, [rsp+168h+var_70]
0x18006e454  mov     r9, [rcx]
0x18006e457  mov     rax, r15
0x18006e45a  lea     r8, [r15+8]
0x18006e45e  neg     rax
0x18006e461  sbb     rdx, rdx
0x18006e464  and     rdx, r8
0x18006e467  xor     r8d, r8d
0x18006e46a  mov     rax, [r9+18h]
0x18006e46e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e473  mov     [rsp+168h+var_F8], eax
0x18006e477  mov     eax, [rsp+168h+var_F8]
0x18006e47b  test    eax, eax
0x18006e47d  js      loc_18006E85F
0x18006e483  test    r12, r12
0x18006e486  jnz     short loc_18006E4E3
0x18006e488  test    r13d, r13d
0x18006e48b  jnz     short loc_18006E4E3
0x18006e48d  mov     r14, [rsp+168h+lpFileName]
0x18006e495  mov     rcx, r14; lpFileName
0x18006e498  call    cs:__imp_GetFileAttributesW
0x18006e49e  cmp     eax, 0FFFFFFFFh
0x18006e4a1  jnz     short loc_18006E4BE
0x18006e4a3  call    cs:__imp_GetLastError
0x18006e4a9  lea     r14d, [r12+1]
  ... truncated ...
```
