# EventService::ExportLog(ClientObjectWrapper<OperationControl> *,wchar_t const *,wchar_t const *,wchar_t const *,ulong)

- ea: `0x180045b74`
- end: `0x18004629b`
- name: `?ExportLog@EventService@@QEAAXPEAV?$ClientObjectWrapper@VOperationControl@@@@PEB_W11K@Z`
- size: `1831`
- prototype: `unsigned int __fastcall(RTL_SRWLOCK *, __int64, __int64, __int64, LPCWSTR lpFileName, int)`
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18007c180`

## callees

- `0x18000a2a0`
- `0x18000a900`
- `0x18000aa40`
- `0x18000bf10`
- `0x180012018`
- `0x180016250`
- `0x180017128`
- `0x180017b60`
- `0x180019d28`
- `0x18001c320`
- `0x18002dcc0`
- `0x18002e468`
- `0x180045b74`
- `0x180046518`
- `0x1800468e0`
- `0x180046938`
- `0x180046994`
- `0x1800469e8`
- `0x1800471c0`
- `0x1800613d8`
- `0x180077ad0`
- `0x180092008`
- `0x1800a7c0c`
- `0x1800b223c`
- `0x1800d334c`
- `0x1800d3370`
- `0x1800dd010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800460dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800460dc`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800460ce`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800460ce`
- `RPCRT4!RpcImpersonateClient` at `0x180045c15`
- `RPCRT4!RpcImpersonateClient` at `0x180045c15`
- `RPCRT4!RpcRevertToSelf` at `0x18004600b`
- `RPCRT4!RpcRevertToSelf` at `0x18004600b`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
unsigned int __fastcall EventService::ExportLog(
        RTL_SRWLOCK *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        LPCWSTR lpFileName,
        int a6)
{
  char v10; // r13
  __int16 v11; // r15
  wmi::RefBase **v12; // rax
  wmi::RefBase *v13; // rbx
  unsigned int v14; // eax
  unsigned int v15; // esi
  volatile signed __int32 *v16; // rsi
  const WCHAR *v17; // r14
  File *v18; // rdi
  int v19; // r13d
  void *v20; // rdi
  int v21; // edi
  unsigned int v22; // eax
  int v23; // ecx
  int v24; // eax
  int v25; // r12d
  unsigned int result; // eax
  DWORD LastError; // ebx
  __int64 v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // rcx
  void **v31; // rax
  int v32; // [rsp+28h] [rbp-D8h]
  int v33; // [rsp+28h] [rbp-D8h]
  int v34; // [rsp+40h] [rbp-C0h] BYREF
  __int128 pExceptionObject; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v36; // [rsp+58h] [rbp-A8h]
  int v37; // [rsp+60h] [rbp-A0h]
  int v38; // [rsp+64h] [rbp-9Ch]
  int v39; // [rsp+68h] [rbp-98h]
  char v40; // [rsp+6Ch] [rbp-94h]
  File *v41; // [rsp+70h] [rbp-90h] BYREF
  void **v42; // [rsp+78h] [rbp-88h] BYREF
  void *Src; // [rsp+80h] [rbp-80h]
  size_t Size; // [rsp+88h] [rbp-78h]
  char v45; // [rsp+90h] [rbp-70h]
  void **v46; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v47; // [rsp+A8h] [rbp-58h]
  void ***v48; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v49; // [rsp+B8h] [rbp-48h]
  __int64 v50; // [rsp+C0h] [rbp-40h]
  wmi::RefBase *v51; // [rsp+C8h] [rbp-38h]
  volatile signed __int32 *v52; // [rsp+D0h] [rbp-30h]
  _QWORD v53[4]; // [rsp+E0h] [rbp-20h] BYREF
  int v54; // [rsp+100h] [rbp+0h]
  int v55; // [rsp+104h] [rbp+4h]
  char v56[24]; // [rsp+108h] [rbp+8h] BYREF
  char v57[24]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v58; // [rsp+138h] [rbp+38h]
  __int64 v59; // [rsp+140h] [rbp+40h]
  const WCHAR *v60; // [rsp+148h] [rbp+48h]
  int v61; // [rsp+150h] [rbp+50h]
  char v62; // [rsp+154h] [rbp+54h]
  _QWORD v63[2]; // [rsp+158h] [rbp+58h] BYREF
  __int64 v64; // [rsp+168h] [rbp+68h]
  char v65; // [rsp+170h] [rbp+70h]
  char v66[24]; // [rsp+178h] [rbp+78h] BYREF
  void ***v67; // [rsp+190h] [rbp+90h]
  int v68; // [rsp+198h] [rbp+98h]
  __int16 v69; // [rsp+19Ch] [rbp+9Ch]
  __int128 v70; // [rsp+1A0h] [rbp+A0h] BYREF
  __int128 v71; // [rsp+1B0h] [rbp+B0h]
  __int64 v72; // [rsp+1C0h] [rbp+C0h]
  _BYTE v73[72]; // [rsp+1C8h] [rbp+C8h] BYREF
  wmi::RefBase *v74; // [rsp+228h] [rbp+128h] BYREF
  __int64 v75; // [rsp+230h] [rbp+130h]

  v75 = a3;
  v10 = 0;
  v34 = 0;
  EventService::WaitForInit(a1);
  v51 = 0;
  utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(v73);
  v11 = a6;
  v12 = (wmi::RefBase **)EventService::BuildComplexQuery(a1, &v74, *(_QWORD *)(a2 + 16), a3, a4, a6, v73);
  v13 = *v12;
  v51 = *v12;
  *v12 = 0;
  if ( v74 )
    wmi::RefBase::Release(v74);
  v14 = RpcImpersonateClient(0);
  v15 = v14;
  if ( v14 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, v14);
    }
    *(_QWORD *)&pExceptionObject = &byte_1800EC961;
    *((_QWORD *)&pExceptionObject + 1) = 0;
    v36 = 0;
    v37 = v15;
    v38 = -1;
    v39 = -1;
    v40 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  BYTE1(v74) = 1;
  v16 = 0;
  v52 = 0;
  v17 = lpFileName;
  if ( !lpFileName )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, 87);
    }
    pExceptionObject = 0;
    v36 = 0;
    v37 = 87;
    v38 = -1;
    v39 = 1118;
    throw (EvtException *)&pExceptionObject;
  }
  if ( FileExists(lpFileName) )
  {
    if ( (v11 & 0x2000) == 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, 80);
      }
      pExceptionObject = 0;
      v36 = 0;
      v37 = 80;
      v38 = -1;
      v39 = 1105;
      throw (EvtException *)&pExceptionObject;
    }
    if ( !DeleteFileW(v17) )
    {
      LastError = GetLastError();
      if ( !LastError )
        LastError = 1287;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, LastError);
      }
      pExceptionObject = 0;
      v36 = 0;
      v37 = LastError;
      v38 = -1;
      v39 = 1100;
      throw (EvtException *)&pExceptionObject;
    }
  }
  v18 = (File *)operator new(0x348u);
  v41 = v18;
  if ( v18 )
  {
    v28 = -1;
    do
      ++v28;
    while ( v17[v28] );
    v46 = (void **)v17;
    v47 = v28;
    v29 = MakeOrThrowOOM(&pExceptionObject);
    v10 = 1;
    v34 = 1;
    if ( a3 )
    {
      v30 = -1;
      do
        ++v30;
      while ( *(_WORD *)(a3 + 2 * v30) );
      v31 = (void **)a3;
    }
    else
    {
      v30 = 0;
      v31 = 0;
    }
    v46 = v31;
    v47 = v30;
    v16 = (volatile signed __int32 *)File::File(v18, (__int64)&v46, v29, 0);
  }
  if ( v16 )
    _InterlockedIncrement(v16 + 202);
  v52 = v16;
  if ( (v10 & 1) != 0 )
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&pExceptionObject);
  v42 = &Buffer::`vftable';
  v19 = 0;
  Src = 0;
  Size = 0;
  v45 = 1;
  v20 = operator new(0x200u);
  memcpy_0(v20, Src, (unsigned int)Size);
  if ( v45 )
    operator delete(Src);
  HIDWORD(Size) = 512;
  Src = v20;
  v45 = 1;
  v48 = &v42;
  v49 = 0;
  v50 = 0;
  v21 = ((__int64 (__fastcall *)(void ***))v42[2])(&v42);
  v49 = ((__int64 (__fastcall *)(void ***))(*v48)[6])(v48);
  HIDWORD(v50) = v21;
  v70 = 0;
  v71 = 0;
  v72 = 0;
  v41 = 0;
  v34 = -1;
  LOBYTE(v32) = 1;
  if ( (unsigned int)MergedLogQueryResult::GetCurrentRecordAndMoveToNext(v13, -1, &v34, &v48, &v41, v32) == 1 )
  {
    do
    {
      *((_QWORD *)&v70 + 1) = (char *)Src + 16;
      *(_QWORD *)&v71 = (unsigned int)Size - 16LL;
      memset(v53, 0, 24);
      v53[3] = &v70;
      v54 = 1;
      v55 = -1;
      utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(v56);
      utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(v57);
      v58 = 0;
      v59 = 0;
      v60 = &pszFormat;
      v61 = 0;
      v62 = 1;
      v63[0] = &Buffer::`vftable';
      v63[1] = 0;
      v64 = 0;
      v65 = 1;
      Buffer::SetSize((Buffer *)v63, 0);
      HIDWORD(v64) = 0;
      WriteBuffer::WriteBuffer((WriteBuffer *)v66, (struct BufferStream *)v63);
      v67 = 0;
      v68 = 0;
      v69 = 0;
      BinXmlReader::NextReaderData((BinXmlReader *)v53);
      v46 = &BinXmlPublishedEventRecord::`vftable';
      v47 = (__int64)v41;
      v67 = &v46;
      v22 = File::WriteRecord((File *)v16, (struct BinXmlReader *)v53);
      v23 = v19 + 1;
      if ( !v22 )
        v23 = v19;
      v19 = v23;
      WriteBuffer::SetCurrentIndex((WriteBuffer *)&v48, 0);
      ((void (__fastcall *)(void ***, _QWORD))(*v48)[4])(v48, (unsigned int)v50);
      v34 = -1;
      BinXmlReader::~BinXmlReader((BinXmlReader *)v53);
      LOBYTE(v33) = 1;
    }
    while ( (unsigned int)MergedLogQueryResult::GetCurrentRecordAndMoveToNext(v13, -1, &v34, &v48, &v41, v33) == 1 );
    v17 = lpFileName;
    if ( v19
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_DSS(*((_QWORD *)WPP_GLOBAL_Control + 2), v75, (__int64)lpFileName);
    }
  }
  v24 = File::FullFlush(v16, 2);
  v25 = v24;
  if ( v24 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_dS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        70,
        (unsigned int)&WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids,
        v24,
        (__int64)v17);
    }
    *(_QWORD *)&pExceptionObject = &byte_1800EC961;
    *((_QWORD *)&pExceptionObject + 1) = 0;
    v36 = 0;
    v37 = v25;
    v38 = -1;
    v39 = -1;
    v40 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  v42 = &Buffer::`vftable';
  if ( v45 )
    operator delete(Src);
  if ( v16 )
    File::Release((File *)v16);
  RpcRevertToSelf();
  result = utl::vector<QueryChannelInfo,utl::allocator<QueryChannelInfo>>::_Uninit(v73);
  if ( v13 )
    return wmi::RefBase::Release(v13);
  return result;
}

```

## disassembly

```asm
0x180045b74  mov     [rsp-8+arg_0], rbx
0x180045b79  mov     [rsp-8+arg_10], r8
0x180045b7e  push    rbp
0x180045b7f  push    rsi
0x180045b80  push    rdi
0x180045b81  push    r12
0x180045b83  push    r13
0x180045b85  push    r14
0x180045b87  push    r15
0x180045b89  lea     rbp, [rsp-0E0h]
0x180045b91  sub     rsp, 1E0h
0x180045b98  mov     rbx, r9
0x180045b9b  mov     r12, r8
0x180045b9e  mov     rdi, rdx
0x180045ba1  mov     rsi, rcx
0x180045ba4  xor     r14d, r14d
0x180045ba7  mov     r13d, r14d
0x180045baa  mov     [rsp+210h+var_1D0], r14d
0x180045baf  call    ?WaitForInit@EventService@@AEAAXXZ; EventService::WaitForInit(void)
0x180045bb4  mov     [rbp+110h+var_148], r14
0x180045bb8  lea     rcx, [rbp+110h+var_48]; void *
0x180045bbf  call    ??0?$vector@UTmplInstInfo@BinXmlReader@@V?$allocator@UTmplInstInfo@BinXmlReader@@@utl@@@utl@@QEAA@XZ; utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(void)
0x180045bc4  nop
0x180045bc5  lea     rax, [rbp+110h+var_48]
0x180045bcc  mov     [rsp+210h+var_1E0], rax
0x180045bd1  mov     r15d, [rbp+110h+arg_28]
0x180045bd8  mov     dword ptr [rsp+210h+var_1E8], r15d
0x180045bdd  mov     [rsp+210h+var_1F0], rbx
0x180045be2  mov     r9, r12
0x180045be5  mov     r8, [rdi+10h]
0x180045be9  lea     rdx, [rbp+110h+arg_8]
0x180045bf0  mov     rcx, rsi
0x180045bf3  call    ?BuildComplexQuery@EventService@@AEAA?AV?$AutoRef@VMergedLogQueryResult@@@wmi@@PEAVOperationControl@@PEB_W1KAEAV?$vector@UQueryChannelInfo@@V?$allocator@UQueryChannelInfo@@@utl@@@utl@@@Z; EventService::BuildComplexQuery(OperationControl *,wchar_t const *,wchar_t const *,ulong,utl::vector<QueryChannelInfo,utl::allocator<QueryChannelInfo>> &)
0x180045bf8  mov     rbx, [rax]
0x180045bfb  mov     [rbp+110h+var_148], rbx
0x180045bff  mov     [rax], r14
0x180045c02  mov     rcx, [rbp+110h+arg_8]; this
0x180045c09  test    rcx, rcx
0x180045c0c  jz      short loc_180045C13
0x180045c0e  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x180045c13  xor     ecx, ecx; BindingHandle
0x180045c15  call    cs:__imp_RpcImpersonateClient
0x180045c1b  mov     esi, eax
0x180045c1d  test    eax, eax
0x180045c1f  jnz     loc_180046047
0x180045c25  mov     byte ptr [rbp+110h+arg_8+1], 1
0x180045c2c  xor     esi, esi
0x180045c2e  mov     [rbp+110h+var_140], rsi
0x180045c32  mov     r14, [rbp+110h+lpFileName]
0x180045c39  test    r14, r14
0x180045c3c  jnz     short loc_180045CAA
0x180045c3e  lea     rdi, WPP_GLOBAL_Control
0x180045c45  lea     ebx, [rax+57h]
0x180045c48  mov     rcx, cs:WPP_GLOBAL_Control
0x180045c4f  cmp     rcx, rdi
0x180045c52  jz      short loc_180045C76
0x180045c54  test    byte ptr [rcx+1Ch], 8
0x180045c58  jz      short loc_180045C76
0x180045c5a  cmp     byte ptr [rcx+19h], 2
0x180045c5e  jb      short loc_180045C76
0x180045c60  lea     edx, [rax+44h]
0x180045c63  mov     r9d, ebx
0x180045c66  lea     r8, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x180045c6d  mov     rcx, [rcx+10h]
0x180045c71  call    WPP_SF_d
0x180045c76  xorps   xmm0, xmm0
0x180045c79  movdqu  [rsp+210h+pExceptionObject], xmm0
0x180045c7f  mov     [rsp+210h+var_1B8], rsi
0x180045c84  mov     [rsp+210h+var_1B0], ebx
0x180045c88  mov     [rsp+210h+var_1AC], 0FFFFFFFFh
0x180045c90  mov     [rsp+210h+var_1A8], 45Eh
0x180045c98  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180045c9f  lea     rcx, [rsp+210h+pExceptionObject]; pExceptionObject
0x180045ca4  call    _CxxThrowException_0
0x180045caa  mov     rcx, r14; wchar_t *
0x180045cad  call    ?FileExists@@YA_NPEB_W@Z; FileExists(wchar_t const *)
0x180045cb2  test    al, al
0x180045cb4  jnz     loc_1800460C0
0x180045cba  mov     ecx, 348h; dwBytes
0x180045cbf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180045cc4  mov     rdi, rax
0x180045cc7  mov     [rsp+210h+var_1A0], rax
0x180045ccc  or      r15, 0FFFFFFFFFFFFFFFFh
0x180045cd0  test    rax, rax
0x180045cd3  jnz     loc_1800461C7
0x180045cd9  test    rsi, rsi
0x180045cdc  jz      short loc_180045CE5
0x180045cde  lock inc dword ptr [rsi+328h]
0x180045ce5  mov     [rbp+110h+var_140], rsi
0x180045ce9  test    r13b, 1
0x180045ced  jnz     loc_18004624C
0x180045cf3  lea     rax, ??_7Buffer@@6B@; const Buffer::`vftable'
0x180045cfa  mov     [rsp+210h+var_198], rax
0x180045cff  xor     r13d, r13d
0x180045d02  mov     [rbp+110h+Src], r13
0x180045d06  mov     [rbp+110h+Size], r13
0x180045d0a  mov     [rbp+110h+var_180], 1
0x180045d0e  mov     ecx, 200h; dwBytes
0x180045d13  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180045d18  mov     rdi, rax
0x180045d1b  mov     r8d, dword ptr [rbp+110h+Size]; Size
0x180045d1f  mov     rdx, [rbp+110h+Src]; Src
0x180045d23  mov     rcx, rax; void *
0x180045d26  call    memcpy_0
0x180045d2b  cmp     [rbp+110h+var_180], r13b
0x180045d2f  jz      short loc_180045D3A
0x180045d31  mov     rcx, [rbp+110h+Src]; void *
0x180045d35  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180045d3a  mov     dword ptr [rbp+110h+Size+4], 200h
0x180045d41  mov     [rbp+110h+Src], rdi
0x180045d45  mov     [rbp+110h+var_180], 1
0x180045d49  lea     rax, [rsp+210h+var_198]
0x180045d4e  mov     [rbp+110h+var_160], rax
0x180045d52  mov     [rbp+110h+var_158], r13
0x180045d56  mov     [rbp+110h+var_150], r13
0x180045d5a  mov     rax, [rsp+210h+var_198]
0x180045d5f  lea     rcx, [rsp+210h+var_198]
0x180045d64  mov     rax, [rax+10h]
0x180045d68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045d6d  mov     edi, eax
0x180045d6f  mov     rcx, [rbp+110h+var_160]
0x180045d73  mov     rdx, [rcx]
0x180045d76  mov     rax, [rdx+30h]
0x180045d7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045d7f  mov     [rbp+110h+var_158], rax
0x180045d83  mov     dword ptr [rbp+110h+var_150+4], edi
0x180045d86  xorps   xmm0, xmm0
0x180045d89  movdqu  [rbp+110h+var_70], xmm0
0x180045d91  xorps   xmm1, xmm1
0x180045d94  movdqu  [rbp+110h+var_60], xmm1
0x180045d9c  mov     [rbp+110h+var_50], r13
0x180045da3  mov     [rsp+210h+var_1A0], r13
0x180045da8  mov     [rsp+210h+var_1D0], 0FFFFFFFFh
0x180045db0  mov     byte ptr [rsp+210h+var_1E8], 1
0x180045db5  lea     rax, [rsp+210h+var_1A0]
0x180045dba  mov     [rsp+210h+var_1F0], rax
0x180045dbf  lea     r9, [rbp+110h+var_160]
0x180045dc3  lea     r8, [rsp+210h+var_1D0]
0x180045dc8  mov     rdx, r15
0x180045dcb  mov     rcx, rbx
0x180045dce  call    ?GetCurrentRecordAndMoveToNext@MergedLogQueryResult@@QEAA?AW4LogQueryResultStatus@@_KAEAIAEAVWriteBuffer@@PEAT_ULARGE_INTEGER@@_N@Z; MergedLogQueryResult::GetCurrentRecordAndMoveToNext(unsigned __int64,uint &,WriteBuffer &,_ULARGE_INTEGER *,bool)
0x180045dd3  lea     rdi, WPP_GLOBAL_Control
0x180045dda  cmp     eax, 1
0x180045ddd  jnz     loc_180045F54
0x180045de3  xor     r14d, r14d
0x180045de6  lea     r12, ??_7Buffer@@6B@; const Buffer::`vftable'
0x180045ded  mov     rax, [rbp+110h+Src]
0x180045df1  add     rax, 10h
0x180045df5  mov     qword ptr [rbp+110h+var_70+8], rax
0x180045dfc  mov     eax, dword ptr [rbp+110h+Size]
0x180045dff  sub     rax, 10h
0x180045e03  mov     qword ptr [rbp+110h+var_60], rax
0x180045e0a  mov     [rbp+110h+var_130], r14
0x180045e0e  mov     [rbp+110h+var_128], r14
0x180045e12  mov     [rbp+110h+var_120], r14
0x180045e16  lea     rax, [rbp+110h+var_70]
0x180045e1d  mov     [rbp+110h+var_118], rax
0x180045e21  mov     [rbp+110h+var_110], 1
0x180045e28  mov     [rbp+110h+var_10C], 0FFFFFFFFh
0x180045e2f  lea     rcx, [rbp+110h+var_108]; void *
0x180045e33  call    ??0?$vector@UTmplInstInfo@BinXmlReader@@V?$allocator@UTmplInstInfo@BinXmlReader@@@utl@@@utl@@QEAA@XZ; utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(void)
0x180045e38  nop
0x180045e39  lea     rcx, [rbp+110h+var_F0]; void *
0x180045e3d  call    ??0?$vector@UTmplInstInfo@BinXmlReader@@V?$allocator@UTmplInstInfo@BinXmlReader@@@utl@@@utl@@QEAA@XZ; utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(void)
0x180045e42  nop
0x180045e43  mov     [rbp+110h+var_D8], r14
0x180045e47  mov     [rbp+110h+var_D0], r14
0x180045e4b  lea     rax, pszFormat
0x180045e52  mov     [rbp+110h+var_C8], rax
0x180045e56  mov     [rbp+110h+var_C0], r14d
0x180045e5a  mov     [rbp+110h+var_BC], 1
0x180045e5e  mov     [rbp+110h+var_B8], r12
0x180045e62  mov     [rbp+110h+var_B0], r14
0x180045e66  mov     [rbp+110h+var_A8], r14
0x180045e6a  mov     [rbp+110h+var_A0], 1
0x180045e6e  xor     edx, edx; unsigned int
0x180045e70  lea     rcx, [rbp+110h+var_B8]; this
0x180045e74  call    ?SetSize@Buffer@@QEAAXK@Z; Buffer::SetSize(ulong)
0x180045e79  mov     dword ptr [rbp+110h+var_A8+4], r14d
0x180045e7d  lea     rdx, [rbp+110h+var_B8]; struct BufferStream *
0x180045e81  lea     rcx, [rbp+110h+var_98]; this
0x180045e85  call    ??0WriteBuffer@@QEAA@AEAVBufferStream@@@Z; WriteBuffer::WriteBuffer(BufferStream &)
0x180045e8a  mov     [rbp+110h+var_80], r14
0x180045e91  mov     [rbp+110h+var_78], r14d
0x180045e98  mov     [rbp+110h+var_74], r14w
0x180045ea0  lea     rcx, [rbp+110h+var_130]; this
0x180045ea4  call    ?NextReaderData@BinXmlReader@@AEAAXXZ; BinXmlReader::NextReaderData(void)
0x180045ea9  nop
0x180045eaa  lea     rax, ??_7BinXmlPublishedEventRecord@@6B@; const BinXmlPublishedEventRecord::`vftable'
0x180045eb1  mov     [rbp+110h+var_170], rax
0x180045eb5  mov     rax, [rsp+210h+var_1A0]
0x180045eba  mov     [rbp+110h+var_168], rax
0x180045ebe  lea     rax, [rbp+110h+var_170]
0x180045ec2  mov     [rbp+110h+var_80], rax
0x180045ec9  lea     rdx, [rbp+110h+var_130]; struct BinXmlReader *
0x180045ecd  mov     rcx, rsi; this
0x180045ed0  call    ?WriteRecord@File@@QEAAKAEAVBinXmlReader@@@Z; File::WriteRecord(BinXmlReader &)
0x180045ed5  lea     ecx, [r13+1]
0x180045ed9  test    eax, eax
0x180045edb  cmovz   ecx, r13d
0x180045edf  mov     r13d, ecx
0x180045ee2  xor     edx, edx; unsigned int
0x180045ee4  lea     rcx, [rbp+110h+var_160]; this
0x180045ee8  call    ?SetCurrentIndex@WriteBuffer@@QEAAXK@Z; WriteBuffer::SetCurrentIndex(ulong)
0x180045eed  mov     rcx, [rbp+110h+var_160]
0x180045ef1  mov     rax, [rcx]
0x180045ef4  mov     edx, dword ptr [rbp+110h+var_150]
0x180045ef7  mov     rax, [rax+20h]
0x180045efb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045f00  mov     [rsp+210h+var_1D0], 0FFFFFFFFh
0x180045f08  lea     rcx, [rbp+110h+var_130]; this
0x180045f0c  call    ??1BinXmlReader@@QEAA@XZ; BinXmlReader::~BinXmlReader(void)
0x180045f11  mov     byte ptr [rsp+210h+var_1E8], 1
0x180045f16  lea     rax, [rsp+210h+var_1A0]
0x180045f1b  mov     [rsp+210h+var_1F0], rax
0x180045f20  lea     r9, [rbp+110h+var_160]
0x180045f24  lea     r8, [rsp+210h+var_1D0]
0x180045f29  mov     rdx, r15
0x180045f2c  mov     rcx, rbx
0x180045f2f  call    ?GetCurrentRecordAndMoveToNext@MergedLogQueryResult@@QEAA?AW4LogQueryResultStatus@@_KAEAIAEAVWriteBuffer@@PEAT_ULARGE_INTEGER@@_N@Z; MergedLogQueryResult::GetCurrentRecordAndMoveToNext(unsigned __int64,uint &,WriteBuffer &,_ULARGE_INTEGER *,bool)
0x180045f34  cmp     eax, 1
0x180045f37  jz      loc_180045DED
0x180045f3d  test    r13d, r13d
0x180045f40  mov     r14, [rbp+110h+lpFileName]
0x180045f47  mov     r12, [rbp+110h+arg_10]
0x180045f4e  jnz     loc_18004625B
0x180045f54  mov     edx, 2
0x180045f59  mov     rcx, rsi
0x180045f5c  call    ?FullFlush@File@@QEAAKW4FlushType@@@Z; File::FullFlush(FlushType)
0x180045f61  mov     r12d, eax
0x180045f64  xor     r13d, r13d
0x180045f67  test    eax, eax
0x180045f69  jz      short loc_180045FE1
0x180045f6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180045f72  cmp     rcx, rdi
0x180045f75  jnz     short loc_180045FB6
0x180045f77  lea     rax, byte_1800EC961
0x180045f7e  mov     qword ptr [rsp+210h+pExceptionObject], rax
0x180045f83  mov     qword ptr [rsp+210h+pExceptionObject+8], r13
0x180045f88  mov     [rsp+210h+var_1B8], r13
0x180045f8d  mov     [rsp+210h+var_1B0], r12d
0x180045f92  mov     [rsp+210h+var_1AC], 0FFFFFFFFh
0x180045f9a  mov     [rsp+210h+var_1A8], r15d
0x180045f9f  mov     [rsp+210h+var_1A4], r13b
0x180045fa4  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180045fab  lea     rcx, [rsp+210h+pExceptionObject]; pExceptionObject
0x180045fb0  call    _CxxThrowException_0
0x180045fb6  test    byte ptr [rcx+1Ch], 8
0x180045fba  jz      short loc_180045F77
0x180045fbc  cmp     byte ptr [rcx+19h], 3
0x180045fc0  jb      short loc_180045F77
0x180045fc2  mov     edx, 46h ; 'F'
0x180045fc7  mov     [rsp+210h+var_1F0], r14
0x180045fcc  mov     r9d, r12d
0x180045fcf  lea     r8, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x180045fd6  mov     rcx, [rcx+10h]
0x180045fda  call    WPP_SF_dS
0x180045fdf  jmp     short loc_180045F77
0x180045fe1  lea     rax, ??_7Buffer@@6B@; const Buffer::`vftable'
0x180045fe8  mov     [rsp+210h+var_198], rax
0x180045fed  cmp     [rbp+110h+var_180], r13b
0x180045ff1  jz      short loc_180045FFD
0x180045ff3  mov     rcx, [rbp+110h+Src]; void *
0x180045ff7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180045ffc  nop
0x180045ffd  test    rsi, rsi
0x180046000  jz      short loc_18004600B
0x180046002  mov     rcx, rsi; this
0x180046005  call    ?Release@File@@QEAAKXZ; File::Release(void)
0x18004600a  nop
0x18004600b  call    cs:__imp_RpcRevertToSelf
0x180046011  nop
0x180046012  lea     rcx, [rbp+110h+var_48]
0x180046019  call    ?_Uninit@?$vector@UQueryChannelInfo@@V?$allocator@UQueryChannelInfo@@@utl@@@utl@@AEAAXXZ; utl::vector<QueryChannelInfo,utl::allocator<QueryChannelInfo>>::_Uninit(void)
0x18004601e  nop
0x18004601f  test    rbx, rbx
0x180046022  jz      short loc_18004602C
0x180046024  mov     rcx, rbx; this
0x180046027  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x18004602c  mov     rbx, [rsp+210h+arg_0]
0x180046034  add     rsp, 1E0h
0x18004603b  pop     r15
0x18004603d  pop     r14
0x18004603f  pop     r13
0x180046041  pop     r12
0x180046043  pop     rdi
0x180046044  pop     rsi
0x180046045  pop     rbp
0x180046046  retn
0x180046047  lea     rdi, WPP_GLOBAL_Control
0x18004604e  mov     rcx, cs:WPP_GLOBAL_Control
0x180046055  cmp     rcx, rdi
0x180046058  jz      short loc_18004607E
0x18004605a  test    byte ptr [rcx+1Ch], 8
0x18004605e  jz      short loc_18004607E
0x180046060  cmp     byte ptr [rcx+19h], 2
0x180046064  jb      short loc_18004607E
0x180046066  mov     edx, 41h ; 'A'
0x18004606b  mov     r9d, esi
0x18004606e  lea     r8, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
  ... truncated ...
```
