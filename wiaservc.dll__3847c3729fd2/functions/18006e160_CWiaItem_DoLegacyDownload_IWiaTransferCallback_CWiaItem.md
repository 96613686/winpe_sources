# CWiaItem::DoLegacyDownload(IWiaTransferCallback *,CWiaItem *)

- ea: `0x18006e160`
- end: `0x18006ea24`
- name: `?DoLegacyDownload@CWiaItem@@AEAAJPEAUIWiaTransferCallback@@PEAV1@@Z`
- size: `2244`
- prototype: `__int64 __fastcall(CWiaItem *this, struct IWiaTransferCallback *, struct IWiaItem *)`
- caller_count: `2`
- callee_count: `24`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18006d5f0`
- `0x180070808`

## callees

- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000da10`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002de18`
- `0x18002def8`
- `0x180033878`
- `0x180033cc0`
- `0x180034558`
- `0x180034658`
- `0x180058354`
- `0x180059640`
- `0x1800597b0`
- `0x1800598cc`
- `0x180059b20`
- `0x18005a220`
- `0x1800671d0`
- `0x18006e160`
- `0x180070270`
- `0x1800713f0`
- `0x1800775fc`
- `0x180078010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18006e9d0`
- `KERNEL32!CloseHandle` at `0x18006e9d0`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18006e9de`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18006e9de`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18006e9bc`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18006e9bc`

## string_xrefs

- `0x18006e222`: `ReadMultiple failed to read required property, propid: %d`
- `0x18006e253`: `ReadMultiple failed to read required property, propid: %d`
- `0x18006e239`: `ReadRequiredPropGUID`
- `0x18006e267`: `ReadRequiredPropGUID`
- `0x18006e7be`: `Driver reported error 0x%08X during download, device error = %d`
- `0x18006e7e9`: `Driver reported error 0x%08X during download, device error = %d`

## pseudocode

```c
__int64 __fastcall CWiaItem::DoLegacyDownload(CWiaItem *this, struct IWiaTransferCallback *a2, struct IWiaItem *a3)
{
  unsigned __int64 v4; // r15
  int v5; // r13d
  struct CWiaLegacyDownload *v6; // rsi
  struct IPropertyStorage *v7; // rbx
  BOOL v8; // r14d
  unsigned __int8 *v9; // r12
  int PropGUID; // eax
  unsigned __int64 v11; // rdx
  int inited; // edi
  char *v13; // rbx
  void *v14; // rdx
  void *lpMem; // rax
  int v16; // edx
  int v17; // ecx
  CWiaItem *v18; // rbx
  __int64 (__fastcall *v19)(char *, _BYTE *); // rax
  char *v20; // rbx
  void *v21; // rdx
  void *v22; // rax
  int v23; // edx
  int v24; // ecx
  int v25; // ebx
  void *v26; // rax
  char *v27; // rbx
  void *v28; // rdx
  void *v29; // rax
  int v30; // edx
  int v31; // ecx
  char *v32; // rbx
  void *v33; // rdx
  void *v34; // rax
  int v35; // edx
  int v36; // ecx
  int v37; // r15d
  int v38; // eax
  CWiaItem *v39; // rbx
  char *v40; // rbx
  void *v41; // rdx
  void *v42; // rax
  int v43; // edx
  int v44; // ecx
  int v45; // ebx
  int v46; // eax
  unsigned __int8 *v47; // rcx
  _DWORD *v48; // r15
  char *v49; // rbx
  void *v50; // rdx
  void *v51; // rax
  int v52; // edx
  int v53; // ecx
  char *v54; // rbx
  void *v55; // rdx
  void *v56; // rax
  int v57; // edx
  int v58; // ecx
  int v59; // eax
  __int64 v60; // rcx
  int v61; // eax
  char *v62; // rbx
  void *v63; // rdx
  void *v64; // rax
  int v65; // edx
  int v66; // ecx
  int v67; // eax
  const WCHAR *v68; // rbx
  int v70; // [rsp+30h] [rbp-D0h]
  int v71; // [rsp+34h] [rbp-CCh]
  int v72; // [rsp+34h] [rbp-CCh]
  int v73; // [rsp+38h] [rbp-C8h] BYREF
  int v74; // [rsp+3Ch] [rbp-C4h] BYREF
  int v75; // [rsp+40h] [rbp-C0h] BYREF
  CWiaItem *v76; // [rsp+48h] [rbp-B8h]
  struct IWiaItem *v77; // [rsp+50h] [rbp-B0h]
  int v78; // [rsp+58h] [rbp-A8h]
  struct CWiaLegacyDownload *v79; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int8 *v80; // [rsp+68h] [rbp-98h] BYREF
  HANDLE hObject; // [rsp+70h] [rbp-90h] BYREF
  void *v82; // [rsp+78h] [rbp-88h]
  LPCWSTR lpFileName; // [rsp+80h] [rbp-80h] BYREF
  struct IWiaTransferCallback *v84; // [rsp+88h] [rbp-78h]
  __int128 v85; // [rsp+90h] [rbp-70h] BYREF
  __m256i v86; // [rsp+A0h] [rbp-60h]
  __int128 v87; // [rsp+C0h] [rbp-40h]
  __int128 v88; // [rsp+D0h] [rbp-30h]
  __int128 v89; // [rsp+E0h] [rbp-20h]
  __int128 v90; // [rsp+F0h] [rbp-10h]
  int v91[4]; // [rsp+100h] [rbp+0h]
  __int128 v92; // [rsp+110h] [rbp+10h]
  _BYTE Buf2[20]; // [rsp+120h] [rbp+20h] BYREF
  __int128 v94; // [rsp+140h] [rbp+40h] BYREF
  __m256i v95; // [rsp+150h] [rbp+50h]
  __int128 v96; // [rsp+170h] [rbp+70h]
  __int128 v97; // [rsp+180h] [rbp+80h]
  __int128 v98; // [rsp+190h] [rbp+90h]
  __int128 v99; // [rsp+1A0h] [rbp+A0h]
  __int128 v100; // [rsp+1B0h] [rbp+B0h]
  __int128 v101; // [rsp+1C0h] [rbp+C0h]

  v84 = a2;
  v76 = this;
  v77 = a3;
  memset_0(&v85, 0, 0x90u);
  hObject = (HANDLE)-1LL;
  v4 = (unsigned __int64)&a3[1];
  v79 = 0;
  v82 = 0;
  v71 = 0;
  v78 = 0;
  v75 = 1;
  v5 = 1;
  v73 = 0;
  v70 = 0;
  v6 = 0;
  v80 = 0;
  lpFileName = 0;
  v7 = (struct IPropertyStorage *)((unsigned __int64)&a3[1] & -(__int64)(a3 != 0));
  v8 = 0;
  v9 = 0;
  *(_OWORD *)Buf2 = 0;
  PropGUID = ReadPropGUID(0, v7, (struct _GUID *)Buf2);
  inited = PropGUID;
  if ( PropGUID == 1 )
  {
    inited = -2147024809;
    v13 = (char *)WiaTrace_TraceLog("ReadMultiple failed to read required property, propid: %d");
    WriteDbgTraceErrorWI("ReadRequiredPropGUID", v13);
    WiaTrcLib::Free((WiaTrcLib *)v13, v14);
    lpMem = (void *)WiaTrace_Trace("ReadMultiple failed to read required property, propid: %d", 4106);
    WiaTrace_ProcessTrace_Ex(v17, v16, (int)"ReadRequiredPropGUID", 1, lpMem);
    goto LABEL_32;
  }
  if ( PropGUID < 0 )
    goto LABEL_32;
  inited = ReadRequiredPropLong(0x100Cu, v7, &v73);
  if ( inited < 0 )
    goto LABEL_16;
  if ( v73 != 2 || memcmp_0(&WiaImgFmt_BMP, Buf2, 0x10u) )
    goto LABEL_9;
  *(GUID *)Buf2 = WiaImgFmt_MEMORYBMP;
  inited = CWiaItem::SetTymedAndFormat((CWiaItem *)v77, 128, (struct _GUID *)Buf2);
  if ( inited < 0 )
  {
LABEL_16:
    v18 = v76;
    goto LABEL_17;
  }
  v70 = 1;
LABEL_9:
  v18 = v76;
  v74 = 0;
  inited = ReadPropLong(
             0xC10u,
             (struct IPropertyStorage *)((*((_QWORD *)v76 + 26) + 8LL)
                                       & ((unsigned __int128)-(__int128)*((unsigned __int64 *)v76 + 26) >> 64)),
             &v74);
  if ( inited )
    goto LABEL_17;
  if ( (v74 & 2) == 0 )
  {
    inited = ReadPropLong(
               0xC18u,
               (struct IPropertyStorage *)((*((_QWORD *)v18 + 26) + 8LL)
                                         & ((unsigned __int128)-(__int128)*((unsigned __int64 *)v18 + 26) >> 64)),
               &v75);
    if ( inited )
      goto LABEL_17;
    v5 = v75;
    if ( v73 != 256 && v75 != 1 )
    {
      inited = WritePropLong(
                 0xC18u,
                 (struct IPropertyStorage *)((*((_QWORD *)v18 + 26) + 8LL)
                                           & ((unsigned __int128)-(__int128)*((unsigned __int64 *)v18 + 26) >> 64)),
                 1);
      v8 = inited >= 0;
      if ( !v5 )
      {
        v71 = 1;
        v5 = 1;
      }
LABEL_17:
      if ( inited < 0 )
        goto LABEL_32;
    }
  }
  inited = InitMiniDrvContext(v77, (struct _MINIDRV_TRANSFER_CONTEXT *)&v85);
  if ( inited >= 0 )
  {
    *(_OWORD *)&Buf2[4] = 0;
    *(_DWORD *)&Buf2[16] = v86.m256i_i32[7];
    v19 = *(__int64 (__fastcall **)(char *, _BYTE *))(*((_QWORD *)v18 + 3) + 40LL);
    *(_OWORD *)Buf2 = *(_OWORD *)((char *)&v86.m256i_u64[1] + 4);
    inited = v19((char *)v18 + 24, Buf2);
    if ( inited )
    {
      v20 = (char *)WiaTrace_TraceLog("idtQueryGetData failed, format not supported");
      WriteDbgTraceErrorWI("CWiaItem::DoLegacyDownload", v20);
      WiaTrcLib::Free((WiaTrcLib *)v20, v21);
      v22 = (void *)WiaTrace_Trace("idtQueryGetData failed, format not supported");
      WiaTrace_ProcessTrace_Ex(v24, v23, (int)"CWiaItem::DoLegacyDownload", 1, v22);
      if ( inited >= 0 )
        inited = -2147024809;
      goto LABEL_32;
    }
    if ( v86.m256i_i32[7] == 128 )
    {
      v74 = 0;
      inited = ReadRequiredPropLong(
                 0x1016u,
                 (struct IPropertyStorage *)(v4 & ((unsigned __int128)-(__int128)(unsigned __int64)v77 >> 64)),
                 &v74);
      if ( inited < 0 )
        goto LABEL_32;
      v25 = v74;
      v26 = operator new[](v74);
      v82 = v26;
      if ( v26 )
      {
        HIDWORD(v87) = v25;
        DWORD1(v88) = 1;
        *((_QWORD *)&v89 + 1) = 0x100000001LL;
        *((_QWORD *)&v88 + 1) = v26;
        *(_QWORD *)&v89 = v26;
      }
      else
      {
        v27 = (char *)WiaTrace_TraceLog("Could not allocate the transfer buffer - we are out of memory!");
        WriteDbgTraceErrorWI("CWiaItem::DoLegacyDownload", v27);
        WiaTrcLib::Free((WiaTrcLib *)v27, v28);
        v29 = (void *)WiaTrace_Trace("Could not allocate the transfer buffer - we are out of memory!");
        WiaTrace_ProcessTrace_Ex(v31, v30, (int)"CWiaItem::DoLegacyDownload", 1, v29);
        inited = -2147024882;
      }
      if ( inited < 0 )
        goto LABEL_32;
      v18 = v76;
    }
    else
    {
      v46 = CreateMappedTempFile(v91[2], (unsigned __int16 **)&lpFileName, &hObject, &v80);
      v9 = v80;
      inited = v46;
      if ( v46 < 0 )
        goto LABEL_32;
      if ( v80 )
      {
        v47 = v80;
        *(_QWORD *)&v89 = v80;
        HIDWORD(v87) = v91[2];
        *((_QWORD *)&v88 + 1) = v80;
      }
      else
      {
        v47 = (unsigned __int8 *)v89;
      }
      *(_QWORD *)&v87 = hObject;
      DWORD1(v88) = 1;
      DWORD2(v89) = 0;
      HIDWORD(v89) = v47 != 0;
    }
    inited = CWiaItem::PrepLegacyCallback(
               v18,
               v84,
               (struct _MINIDRV_TRANSFER_CONTEXT *)&v85,
               (struct CWiaItem *)v77,
               &v79);
    if ( inited < 0 )
    {
      v32 = (char *)WiaTrace_TraceLog("Failed to initialize legacy transfer callback (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::DoLegacyDownload", v32);
      WiaTrcLib::Free((WiaTrcLib *)v32, v33);
      v34 = (void *)WiaTrace_Trace("Failed to initialize legacy transfer callback (0x%X)", inited);
      WiaTrace_ProcessTrace_Ex(v36, v35, (int)"CWiaItem::DoLegacyDownload", 1, v34);
    }
    v6 = v79;
  }
LABEL_32:
  v37 = v71;
  v38 = v73;
  while ( !inited && (v5 > 0 || v38 == 256) )
  {
    memset_0(&v94, 0, 0x90u);
    v39 = v76;
    inited = CWiaItem::SetMiniDrvItemProperties(v76, (struct _MINIDRV_TRANSFER_CONTEXT *)&v85);
    if ( inited )
      goto LABEL_61;
    v94 = v85;
    v95 = v86;
    v97 = v88;
    v96 = v87;
    v99 = v90;
    v98 = v89;
    v101 = v92;
    v100 = *(_OWORD *)v91;
    inited = (*(__int64 (__fastcall **)(struct CWiaLegacyDownload *))(*(_QWORD *)v6 + 56LL))(v6);
    if ( inited < 0 )
    {
      v40 = (char *)WiaTrace_TraceLog("GetNextAppStream failed (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::DoLegacyDownload", v40);
      WiaTrcLib::Free((WiaTrcLib *)v40, v41);
      v42 = (void *)WiaTrace_Trace("GetNextAppStream failed (0x%X)", inited);
      WiaTrace_ProcessTrace_Ex(v44, v43, (int)"CWiaItem::DoLegacyDownload", 1, v42);
LABEL_39:
      v45 = 0;
      goto LABEL_51;
    }
    if ( inited )
      goto LABEL_39;
    v72 = v37;
    v48 = (_DWORD *)((char *)v39 + 160);
    inited = (*(__int64 (__fastcall **)(_QWORD, struct IWiaItem *, _QWORD, __int128 *, __int64))(**((_QWORD **)v39 + 19)
                                                                                               + 368LL))(
               *((_QWORD *)v39 + 19),
               v77,
               0,
               &v94,
               (__int64)v39 + 160);
    if ( inited == 1 )
    {
      v49 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(64, 0, "Caller cancelled data acquisition");
      WriteDbgTraceInfoWI("CWiaItem::DoLegacyDownload", v49);
      WiaTrcLib::Free((WiaTrcLib *)v49, v50);
      v51 = (void *)WiaTrace_TraceWithSubCompTraceLevel(64, 0, "Caller cancelled data acquisition");
      WiaTrace_ProcessTrace_Ex(v53, v52, (int)"CWiaItem::DoLegacyDownload", 4, v51);
      v45 = 1;
    }
    else if ( inited >= 0 )
    {
      v45 = 1;
      if ( !inited )
      {
        v37 = v72;
        v78 = 1;
LABEL_53:
        v59 = (*(__int64 (__fastcall **)(struct CWiaLegacyDownload *))(*(_QWORD *)v6 + 64LL))(v6);
        if ( v59 < 0 )
          inited = v59;
        goto LABEL_55;
      }
    }
    else
    {
      v54 = (char *)WiaTrace_TraceLog("Driver reported error 0x%08X during download, device error = %d");
      WriteDbgTraceErrorWI("CWiaItem::DoLegacyDownload", v54);
      WiaTrcLib::Free((WiaTrcLib *)v54, v55);
      v56 = (void *)WiaTrace_Trace("Driver reported error 0x%08X during download, device error = %d", inited, *v48);
      v45 = 1;
      WiaTrace_ProcessTrace_Ex(v58, v57, (int)"CWiaItem::DoLegacyDownload", 1, v56);
    }
    v37 = v72;
LABEL_51:
    if ( v73 == 256 && (unsigned int)(inited + 2145320958) <= 2 )
      goto LABEL_53;
LABEL_55:
    v60 = *((_QWORD *)v6 + 3);
    if ( v60 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
      *((_QWORD *)v6 + 3) = 0;
    }
    if ( v45 )
    {
      v61 = (*(__int64 (__fastcall **)(struct CWiaLegacyDownload *))(*(_QWORD *)v6 + 48LL))(v6);
      if ( inited >= 0 )
      {
        if ( v61 )
          inited = v61;
      }
    }
LABEL_61:
    v38 = v73;
    if ( v73 == 256 )
      break;
    if ( v78 && inited == -2145320957 )
    {
      inited = v37 == 0 ? 0x210001 : 0;
      v62 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                      0,
                      0,
                      "Out of paper, but atleast 1 page successfully transferred using legacy driver, returning %#x",
                      inited);
      WriteDbgTraceInfoWI("CWiaItem::DoLegacyDownload", v62);
      WiaTrcLib::Free((WiaTrcLib *)v62, v63);
      v64 = (void *)WiaTrace_TraceWithSubCompTraceLevel(
                      0,
                      0,
                      "Out of paper, but atleast 1 page successfully transferred using legacy driver, returning %#x",
                      inited);
      WiaTrace_ProcessTrace_Ex(v66, v65, (int)"CWiaItem::DoLegacyDownload", 4, v64);
      break;
    }
    if ( inited )
      break;
    if ( v37 )
      v5 = 1;
    else
      --v5;
  }
  if ( v8 )
    WritePropLong(
      0xC18u,
      (struct IPropertyStorage *)((*((_QWORD *)v76 + 26) + 8LL)
                                & ((unsigned __int128)-(__int128)*((unsigned __int64 *)v76 + 26) >> 64)),
      v75);
  if ( v70 )
  {
    *(GUID *)Buf2 = WiaImgFmt_BMP;
    v67 = CWiaItem::SetTymedAndFormat((CWiaItem *)v77, 2, (struct _GUID *)Buf2);
    if ( inited >= 0 )
    {
      if ( v67 )
        inited = v67;
    }
  }
  if ( v82 )
    operator delete(v82, v11);
  v68 = lpFileName;
  if ( lpFileName )
  {
    if ( v9 )
      UnmapViewOfFile(v9);
    if ( hObject != (HANDLE)-1LL )
      CloseHandle(hObject);
    if ( v68 )
      DeleteFileW(v68);
  }
  if ( v6 )
    (*(void (__fastcall **)(struct CWiaLegacyDownload *))(*(_QWORD *)v6 + 16LL))(v6);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18006e160  mov     [rsp-8+arg_18], rbx
0x18006e165  push    rbp
0x18006e166  push    rsi
0x18006e167  push    rdi
0x18006e168  push    r12
0x18006e16a  push    r13
0x18006e16c  push    r14
0x18006e16e  push    r15
0x18006e170  lea     rbp, [rsp-0E0h]
0x18006e178  sub     rsp, 1E0h
0x18006e17f  mov     rax, cs:__security_cookie
0x18006e186  xor     rax, rsp
0x18006e189  mov     [rbp+110h+var_40], rax
0x18006e190  mov     rbx, r8
0x18006e193  mov     [rbp+110h+var_188], rdx
0x18006e197  mov     [rsp+210h+var_1C8], rcx
0x18006e19c  xor     edx, edx; Val
0x18006e19e  mov     r8d, 90h; Size
0x18006e1a4  mov     [rsp+210h+var_1C0], rbx
0x18006e1a9  lea     rcx, [rbp+110h+var_180]; void *
0x18006e1ad  call    memset_0
0x18006e1b2  xor     ecx, ecx; unsigned int
0x18006e1b4  mov     [rsp+210h+hObject], 0FFFFFFFFFFFFFFFFh
0x18006e1bd  lea     r15, [rbx+8]
0x18006e1c1  mov     [rsp+210h+var_1B0], rcx
0x18006e1c6  xorps   xmm0, xmm0
0x18006e1c9  mov     [rsp+210h+var_198], rcx
0x18006e1ce  lea     r8, [rbp+110h+Buf2]; struct _GUID *
0x18006e1d2  mov     [rsp+210h+var_1DC], ecx
0x18006e1d6  lea     eax, [rcx+1]
0x18006e1d9  mov     [rsp+210h+var_1B8], ecx
0x18006e1dd  mov     [rsp+210h+var_1D0], eax
0x18006e1e1  mov     r13d, eax
0x18006e1e4  mov     rax, rbx
0x18006e1e7  mov     [rsp+210h+var_1D8], ecx
0x18006e1eb  neg     rax
0x18006e1ee  mov     [rsp+210h+var_1E0], ecx
0x18006e1f2  mov     esi, ecx
0x18006e1f4  mov     [rsp+210h+var_1A8], rcx
0x18006e1f9  sbb     rbx, rbx
0x18006e1fc  mov     [rbp+110h+lpFileName], rcx
0x18006e200  and     rbx, r15
0x18006e203  mov     r14d, ecx
0x18006e206  mov     rdx, rbx; struct IPropertyStorage *
0x18006e209  mov     r12d, ecx
0x18006e20c  movups  [rbp+110h+Buf2], xmm0
0x18006e210  call    ?ReadPropGUID@@YAJKPEAUIPropertyStorage@@PEAU_GUID@@@Z; ReadPropGUID(ulong,IPropertyStorage *,_GUID *)
0x18006e215  mov     edi, eax
0x18006e217  cmp     eax, r13d
0x18006e21a  jnz     short loc_18006E278
0x18006e21c  mov     r15d, 100Ah
0x18006e222  lea     rcx, aReadmultipleFa_0; "ReadMultiple failed to read required pr"...
0x18006e229  mov     edx, r15d
0x18006e22c  mov     edi, 80070057h
0x18006e231  call    WiaTrace_TraceLog
0x18006e236  mov     rdx, rax; char *
0x18006e239  lea     rcx, aReadrequiredpr_0; "ReadRequiredPropGUID"
0x18006e240  mov     rbx, rax
0x18006e243  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18006e248  mov     rcx, rbx; this
0x18006e24b  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18006e250  mov     edx, r15d
0x18006e253  lea     rcx, aReadmultipleFa_0; "ReadMultiple failed to read required pr"...
0x18006e25a  call    WiaTrace_Trace
0x18006e25f  mov     r9d, r13d; int
0x18006e262  mov     [rsp+210h+lpMem], rax; lpMem
0x18006e267  lea     r8, aReadrequiredpr_0; "ReadRequiredPropGUID"
0x18006e26e  call    WiaTrace_ProcessTrace_Ex
0x18006e273  jmp     loc_18006E596
0x18006e278  test    eax, eax
0x18006e27a  js      loc_18006E596
0x18006e280  lea     r8, [rsp+210h+var_1D8]; int *
0x18006e285  mov     rdx, rbx; struct IPropertyStorage *
0x18006e288  mov     ecx, 100Ch; unsigned int
0x18006e28d  call    ?ReadRequiredPropLong@@YAJKPEAUIPropertyStorage@@PEAJ@Z; ReadRequiredPropLong(ulong,IPropertyStorage *,long *)
0x18006e292  mov     edi, eax
0x18006e294  test    eax, eax
0x18006e296  js      loc_18006E3AA
0x18006e29c  cmp     [rsp+210h+var_1D8], 2
0x18006e2a1  jnz     short loc_18006E2EB
0x18006e2a3  mov     r8d, 10h; Size
0x18006e2a9  lea     rdx, [rbp+110h+Buf2]; Buf2
0x18006e2ad  lea     rcx, WiaImgFmt_BMP; Buf1
0x18006e2b4  call    memcmp_0
0x18006e2b9  test    eax, eax
0x18006e2bb  jnz     short loc_18006E2EB
0x18006e2bd  movaps  xmm0, xmmword ptr cs:WiaImgFmt_MEMORYBMP.Data1
0x18006e2c4  lea     r8, [rbp+110h+Buf2]; struct _GUID
0x18006e2c8  mov     rcx, [rsp+210h+var_1C0]; this
0x18006e2cd  mov     edx, 80h; int
0x18006e2d2  movdqa  [rbp+110h+Buf2], xmm0
0x18006e2d7  call    ?SetTymedAndFormat@CWiaItem@@QEAAJJU_GUID@@@Z; CWiaItem::SetTymedAndFormat(long,_GUID)
0x18006e2dc  mov     edi, eax
0x18006e2de  test    eax, eax
0x18006e2e0  js      loc_18006E3AA
0x18006e2e6  mov     [rsp+210h+var_1E0], r13d
0x18006e2eb  mov     rbx, [rsp+210h+var_1C8]
0x18006e2f0  lea     r8, [rsp+210h+var_1D4]; int *
0x18006e2f5  mov     [rsp+210h+var_1D4], esi
0x18006e2f9  mov     rax, [rbx+0D0h]
0x18006e300  lea     rcx, [rax+8]
0x18006e304  neg     rax
0x18006e307  sbb     rdx, rdx
0x18006e30a  and     rdx, rcx; struct IPropertyStorage *
0x18006e30d  mov     ecx, 0C10h; unsigned int
0x18006e312  call    ?ReadPropLong@@YAJKPEAUIPropertyStorage@@PEAJ@Z; ReadPropLong(ulong,IPropertyStorage *,long *)
0x18006e317  mov     edi, eax
0x18006e319  test    eax, eax
0x18006e31b  jnz     loc_18006E3AF
0x18006e321  test    byte ptr [rsp+210h+var_1D4], 2
0x18006e326  jnz     loc_18006E3B7
0x18006e32c  mov     rax, [rbx+0D0h]
0x18006e333  lea     r8, [rsp+210h+var_1D0]; int *
0x18006e338  lea     rcx, [rax+8]
0x18006e33c  neg     rax
0x18006e33f  sbb     rdx, rdx
0x18006e342  and     rdx, rcx; struct IPropertyStorage *
0x18006e345  mov     ecx, 0C18h; unsigned int
0x18006e34a  call    ?ReadPropLong@@YAJKPEAUIPropertyStorage@@PEAJ@Z; ReadPropLong(ulong,IPropertyStorage *,long *)
0x18006e34f  mov     edi, eax
0x18006e351  test    eax, eax
0x18006e353  jnz     short loc_18006E3AF
0x18006e355  cmp     [rsp+210h+var_1D8], 100h
0x18006e35d  mov     r13d, [rsp+210h+var_1D0]
0x18006e362  jz      short loc_18006E3B7
0x18006e364  cmp     r13d, 1
0x18006e368  jz      short loc_18006E3B7
0x18006e36a  mov     rax, [rbx+0D0h]
0x18006e371  lea     r8d, [rdi+1]; int
0x18006e375  lea     rcx, [rax+8]
0x18006e379  neg     rax
0x18006e37c  sbb     rdx, rdx
0x18006e37f  and     rdx, rcx; struct IPropertyStorage *
0x18006e382  mov     ecx, 0C18h; unsigned int
0x18006e387  call    ?WritePropLong@@YAJKPEAUIPropertyStorage@@J@Z; WritePropLong(ulong,IPropertyStorage *,long)
0x18006e38c  mov     r14d, eax
0x18006e38f  mov     edi, eax
0x18006e391  not     r14d
0x18006e394  shr     r14d, 1Fh
0x18006e398  test    r13d, r13d
0x18006e39b  jnz     short loc_18006E3AF
0x18006e39d  lea     ecx, [r13+1]
0x18006e3a1  mov     [rsp+210h+var_1DC], ecx
0x18006e3a5  mov     r13d, ecx
0x18006e3a8  jmp     short loc_18006E3AF
0x18006e3aa  mov     rbx, [rsp+210h+var_1C8]
0x18006e3af  test    edi, edi
0x18006e3b1  js      loc_18006E596
0x18006e3b7  mov     rcx, [rsp+210h+var_1C0]; this
0x18006e3bc  lea     rdx, [rbp+110h+var_180]; struct _MINIDRV_TRANSFER_CONTEXT *
0x18006e3c0  call    ?InitMiniDrvContext@@YAJPEAUIWiaItem@@PEAU_MINIDRV_TRANSFER_CONTEXT@@@Z; InitMiniDrvContext(IWiaItem *,_MINIDRV_TRANSFER_CONTEXT *)
0x18006e3c5  mov     edi, eax
0x18006e3c7  test    eax, eax
0x18006e3c9  js      loc_18006E596
0x18006e3cf  mov     eax, [rbp+110h+var_154]
0x18006e3d2  lea     rcx, [rbx+18h]
0x18006e3d6  xorps   xmm0, xmm0
0x18006e3d9  lea     rdx, [rbp+110h+Buf2]
0x18006e3dd  movups  [rbp+110h+Buf2+4], xmm0
0x18006e3e1  mov     [rbp+110h+var_E0], eax
0x18006e3e4  mov     rax, [rcx]
0x18006e3e7  movups  xmm0, [rbp+110h+var_164]
0x18006e3eb  mov     rax, [rax+28h]
0x18006e3ef  movdqu  [rbp+110h+Buf2], xmm0
0x18006e3f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e3f9  mov     edi, eax
0x18006e3fb  test    eax, eax
0x18006e3fd  jz      short loc_18006E45A
0x18006e3ff  lea     rcx, aIdtquerygetdat; "idtQueryGetData failed, format not supp"...
0x18006e406  call    WiaTrace_TraceLog
0x18006e40b  mov     rdx, rax; char *
0x18006e40e  lea     rcx, aCwiaitemDolega; "CWiaItem::DoLegacyDownload"
0x18006e415  mov     rbx, rax
0x18006e418  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18006e41d  mov     rcx, rbx; this
0x18006e420  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18006e425  lea     rcx, aIdtquerygetdat; "idtQueryGetData failed, format not supp"...
0x18006e42c  call    WiaTrace_Trace
0x18006e431  mov     r9d, 1; int
0x18006e437  mov     [rsp+210h+lpMem], rax; lpMem
0x18006e43c  lea     r8, aCwiaitemDolega; "CWiaItem::DoLegacyDownload"
0x18006e443  call    WiaTrace_ProcessTrace_Ex
0x18006e448  test    edi, edi
0x18006e44a  js      loc_18006E596
0x18006e450  mov     edi, 80070057h
0x18006e455  jmp     loc_18006E596
0x18006e45a  cmp     [rbp+110h+var_154], 80h
0x18006e461  jnz     loc_18006E6A7
0x18006e467  mov     rax, [rsp+210h+var_1C0]
0x18006e46c  lea     r8, [rsp+210h+var_1D4]; int *
0x18006e471  neg     rax
0x18006e474  mov     [rsp+210h+var_1D4], esi
0x18006e478  mov     ecx, 1016h; unsigned int
0x18006e47d  sbb     rdx, rdx
0x18006e480  and     rdx, r15; struct IPropertyStorage *
0x18006e483  call    ?ReadRequiredPropLong@@YAJKPEAUIPropertyStorage@@PEAJ@Z; ReadRequiredPropLong(ulong,IPropertyStorage *,long *)
0x18006e488  mov     edi, eax
0x18006e48a  test    eax, eax
0x18006e48c  js      loc_18006E596
0x18006e492  movsxd  rbx, [rsp+210h+var_1D4]
0x18006e497  mov     rcx, rbx; unsigned __int64
0x18006e49a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18006e49f  mov     [rsp+210h+var_198], rax
0x18006e4a4  test    rax, rax
0x18006e4a7  jz      short loc_18006E4C8
0x18006e4a9  mov     r15d, 1
0x18006e4af  mov     [rbp+110h+var_144], ebx
0x18006e4b2  mov     [rbp+110h+var_13C], r15d
0x18006e4b6  mov     dword ptr [rbp+110h+var_130+8], r15d
0x18006e4ba  mov     dword ptr [rbp+110h+var_130+0Ch], r15d
0x18006e4be  mov     [rbp+110h+var_138], rax
0x18006e4c2  mov     qword ptr [rbp+110h+var_130], rax
0x18006e4c6  jmp     short loc_18006E519
0x18006e4c8  lea     rcx, aCouldNotAlloca; "Could not allocate the transfer buffer "...
0x18006e4cf  call    WiaTrace_TraceLog
0x18006e4d4  mov     rdx, rax; char *
0x18006e4d7  lea     rcx, aCwiaitemDolega; "CWiaItem::DoLegacyDownload"
0x18006e4de  mov     rbx, rax
0x18006e4e1  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18006e4e6  mov     rcx, rbx; this
0x18006e4e9  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18006e4ee  lea     rcx, aCouldNotAlloca; "Could not allocate the transfer buffer "...
0x18006e4f5  call    WiaTrace_Trace
0x18006e4fa  mov     r15d, 1
0x18006e500  mov     [rsp+210h+lpMem], rax; lpMem
0x18006e505  mov     r9d, r15d; int
0x18006e508  lea     r8, aCwiaitemDolega; "CWiaItem::DoLegacyDownload"
0x18006e50f  call    WiaTrace_ProcessTrace_Ex
0x18006e514  mov     edi, 8007000Eh
0x18006e519  test    edi, edi
0x18006e51b  js      short loc_18006E596
0x18006e51d  mov     rbx, [rsp+210h+var_1C8]
0x18006e522  mov     r9, [rsp+210h+var_1C0]; struct CWiaItem *
0x18006e527  lea     rax, [rsp+210h+var_1B0]
0x18006e52c  mov     rdx, [rbp+110h+var_188]; struct IWiaTransferCallback *
0x18006e530  lea     r8, [rbp+110h+var_180]; struct _MINIDRV_TRANSFER_CONTEXT *
0x18006e534  mov     rcx, rbx; this
0x18006e537  mov     [rsp+210h+lpMem], rax; struct CWiaLegacyDownload **
0x18006e53c  call    ?PrepLegacyCallback@CWiaItem@@AEAAJPEAUIWiaTransferCallback@@PEAU_MINIDRV_TRANSFER_CONTEXT@@PEAV1@PEAPEAVCWiaLegacyDownload@@@Z; CWiaItem::PrepLegacyCallback(IWiaTransferCallback *,_MINIDRV_TRANSFER_CONTEXT *,CWiaItem *,CWiaLegacyDownload * *)
0x18006e541  mov     edi, eax
0x18006e543  test    eax, eax
0x18006e545  jns     short loc_18006E591
0x18006e547  mov     edx, eax
0x18006e549  lea     rcx, aFailedToInitia_0; "Failed to initialize legacy transfer ca"...
0x18006e550  call    WiaTrace_TraceLog
0x18006e555  mov     rdx, rax; char *
0x18006e558  lea     rcx, aCwiaitemDolega; "CWiaItem::DoLegacyDownload"
0x18006e55f  mov     rbx, rax
0x18006e562  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18006e567  mov     rcx, rbx; this
0x18006e56a  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18006e56f  mov     edx, edi
0x18006e571  lea     rcx, aFailedToInitia_0; "Failed to initialize legacy transfer ca"...
0x18006e578  call    WiaTrace_Trace
0x18006e57d  mov     r9d, r15d; int
0x18006e580  mov     [rsp+210h+lpMem], rax; lpMem
0x18006e585  lea     r8, aCwiaitemDolega; "CWiaItem::DoLegacyDownload"
0x18006e58c  call    WiaTrace_ProcessTrace_Ex
0x18006e591  mov     rsi, [rsp+210h+var_1B0]
0x18006e596  mov     r15d, [rsp+210h+var_1DC]
0x18006e59b  mov     eax, [rsp+210h+var_1D8]
0x18006e59f  test    edi, edi
0x18006e5a1  jnz     loc_18006E93D
0x18006e5a7  test    r13d, r13d
0x18006e5aa  jg      short loc_18006E5B7
0x18006e5ac  cmp     eax, 100h
0x18006e5b1  jnz     loc_18006E93D
0x18006e5b7  xor     edx, edx; Val
0x18006e5b9  lea     rcx, [rbp+110h+var_D0]; void *
0x18006e5bd  mov     r8d, 90h; Size
0x18006e5c3  call    memset_0
0x18006e5c8  mov     rbx, [rsp+210h+var_1C8]
0x18006e5cd  lea     rdx, [rbp+110h+var_180]; struct _MINIDRV_TRANSFER_CONTEXT *
0x18006e5d1  mov     rcx, rbx; this
0x18006e5d4  call    ?SetMiniDrvItemProperties@CWiaItem@@QEAAJPEAU_MINIDRV_TRANSFER_CONTEXT@@@Z; CWiaItem::SetMiniDrvItemProperties(_MINIDRV_TRANSFER_CONTEXT *)
0x18006e5d9  mov     edi, eax
0x18006e5db  test    eax, eax
0x18006e5dd  jnz     loc_18006E87F
0x18006e5e3  movaps  xmm0, [rbp+110h+var_180]
0x18006e5e7  mov     rcx, rsi
0x18006e5ea  movaps  xmm1, xmmword ptr [rbp-60h]
0x18006e5ee  movups  [rbp+110h+var_D0], xmm0
0x18006e5f2  movaps  xmm0, [rbp+110h+var_164+4]
0x18006e5f6  movups  [rbp+110h+var_B0], xmm0
0x18006e5fa  movaps  xmm0, xmmword ptr [rbp-30h]
0x18006e5fe  movups  [rbp+110h+var_C0], xmm1
0x18006e602  movaps  xmm1, xmmword ptr [rbp-40h]
0x18006e606  movups  [rbp+110h+var_90], xmm0
0x18006e60d  movaps  xmm0, [rbp+110h+var_120]
0x18006e611  movups  [rbp+110h+var_A0], xmm1
0x18006e615  movaps  xmm1, [rbp+110h+var_130]
0x18006e619  movups  [rbp+110h+var_70], xmm0
0x18006e620  movaps  xmm0, [rbp+110h+var_100]
0x18006e624  movups  [rbp+110h+var_80], xmm1
0x18006e62b  movaps  xmm1, xmmword ptr [rbp+110h+var_110]
0x18006e62f  movups  [rbp+110h+var_50], xmm0
0x18006e636  movups  [rbp+110h+var_60], xmm1
0x18006e63d  mov     rax, [rsi]
0x18006e640  mov     rax, [rax+38h]
0x18006e644  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
