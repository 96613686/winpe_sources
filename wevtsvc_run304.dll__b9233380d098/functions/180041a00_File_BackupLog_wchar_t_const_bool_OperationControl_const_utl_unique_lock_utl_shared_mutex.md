# File::BackupLog(wchar_t const *,bool,OperationControl const *,utl::unique_lock<utl::shared_mutex> &)

- ea: `0x180041a00`
- end: `0x180042371`
- name: `?BackupLog@File@@AEAAXPEB_W_NPEBVOperationControl@@AEAV?$unique_lock@Vshared_mutex@utl@@@utl@@@Z`
- size: `2417`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800415b0`
- `0x1800c58b8`

## callees

- `0x180009c30`
- `0x18003420c`
- `0x180041a00`
- `0x180047a0c`
- `0x18004879c`
- `0x180048ffc`
- `0x180064738`
- `0x18006bbe0`
- `0x1800918a0`
- `0x180092008`
- `0x1800935e4`
- `0x18009aee0`
- `0x18009bb88`
- `0x18009e770`
- `0x1800b23e8`
- `0x1800b26bc`
- `0x1800b2780`
- `0x1800b2794`
- `0x1800b3800`
- `0x1800b3998`
- `0x1800d334c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041d2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004211a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800422f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041d2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004211a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800422f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180041cf0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180041cf0`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x180041b2b`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x180041b2b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18004207c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18004207c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180041b0e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180041e57`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180041b0e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180041e57`
- `RPCRT4!RpcImpersonateClient` at `0x180041a4e`
- `RPCRT4!RpcImpersonateClient` at `0x180041a4e`
- `RPCRT4!RpcRevertToSelf` at `0x180041cfc`
- `RPCRT4!RpcRevertToSelf` at `0x180041cfc`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
RPC_STATUS __fastcall File::BackupLog(__int64 a1, const WCHAR *a2, char a3, __int64 a4, __int64 a5)
{
  unsigned int v8; // eax
  unsigned int v9; // esi
  HANDLE FileW; // rax
  void *v11; // rsi
  __int64 v12; // r9
  unsigned int v13; // eax
  unsigned int v14; // r14d
  RPC_STATUS result; // eax
  DWORD LastError; // edi
  unsigned int v17; // eax
  unsigned int v18; // esi
  _OWORD *FileHeader; // rax
  unsigned int v20; // edx
  unsigned __int64 v21; // r15
  __int64 v22; // r8
  unsigned int v23; // eax
  unsigned int v24; // esi
  __int64 v25; // r14
  unsigned __int64 i; // rbx
  unsigned __int64 v27; // rsi
  DWORD v28; // edi
  DWORD v29; // edi
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  _BYTE pExceptionObject[36]; // [rsp+40h] [rbp-C0h] BYREF
  char v33; // [rsp+64h] [rbp-9Ch]
  _BYTE v34[8]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v35; // [rsp+70h] [rbp-90h] BYREF
  __int64 v36; // [rsp+80h] [rbp-80h]
  int v37; // [rsp+88h] [rbp-78h]
  int v38; // [rsp+8Ch] [rbp-74h]
  int v39; // [rsp+90h] [rbp-70h]
  HANDLE hFile; // [rsp+98h] [rbp-68h] BYREF
  DWORD NumberOfBytesWritten[2]; // [rsp+A0h] [rbp-60h] BYREF
  HANDLE *p_hFile; // [rsp+A8h] [rbp-58h] BYREF
  char v43; // [rsp+B0h] [rbp-50h]
  struct ChunkHeader *v44[7]; // [rsp+B8h] [rbp-48h] BYREF
  UCHAR Buffer[16]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v46; // [rsp+100h] [rbp+0h]
  unsigned __int64 v47[2]; // [rsp+110h] [rbp+10h]
  __int128 v48; // [rsp+120h] [rbp+20h]
  __int128 v49; // [rsp+130h] [rbp+30h]
  __int128 v50; // [rsp+140h] [rbp+40h]
  __int128 v51; // [rsp+150h] [rbp+50h]
  __int128 v52; // [rsp+160h] [rbp+60h]
  _QWORD v53[4]; // [rsp+170h] [rbp+70h] BYREF
  int v54; // [rsp+190h] [rbp+90h]
  int v55; // [rsp+194h] [rbp+94h]
  unsigned __int64 v56; // [rsp+198h] [rbp+98h]
  int v57; // [rsp+1ECh] [rbp+ECh]

  if ( a3 )
  {
    v8 = RpcImpersonateClient(0);
    v9 = v8;
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, v8);
      }
      *(_QWORD *)pExceptionObject = &word_1800EC961;
      *(_QWORD *)&pExceptionObject[8] = 0;
      *(_QWORD *)&pExceptionObject[16] = 0;
      *(_DWORD *)&pExceptionObject[24] = v9;
      *(_QWORD *)&pExceptionObject[28] = -1;
      v33 = 0;
      throw (EvtException *)pExceptionObject;
    }
  }
  v34[0] = a3;
  v34[1] = 1;
  if ( *(_BYTE *)(a1 + 832) )
  {
    FileW = CreateFileW(a2, 0xC0000000, 0, 0, 4u, 0, 0);
    v11 = FileW;
    *(_QWORD *)NumberOfBytesWritten = FileW;
    if ( (unsigned __int64)FileW + 1 <= 1 )
    {
      LastError = GetLastError();
      if ( !LastError )
        LastError = 1287;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, LastError);
      }
      memset(pExceptionObject, 0, 24);
      *(_DWORD *)&pExceptionObject[24] = LastError;
      *(_DWORD *)&pExceptionObject[28] = -1;
      *(_DWORD *)&pExceptionObject[32] = 1973;
      throw (EvtException *)pExceptionObject;
    }
    if ( GetFileType(FileW) != 1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, 4300);
      }
      memset(pExceptionObject, 0, 24);
      *(_QWORD *)&pExceptionObject[24] = -4294962996LL;
      *(_DWORD *)&pExceptionObject[32] = 1977;
      throw (EvtException *)pExceptionObject;
    }
    AddBlankChunk(v11, 1u, 0);
    memset_0(v53, 0, 0x80u);
    strcpy((char *)v53, "ElfFile");
    v53[3] = 0;
    v54 = 128;
    v55 = 196610;
    v56 = CalcFileSizeNeeded(1u);
    v57 = 0;
    v53[2] = 0;
    LOBYTE(dwCreationDisposition) = 0;
    LOBYTE(v12) = 1;
    v13 = File::WriteFileHeader(v11, v53, 0, v12, dwCreationDisposition);
    v14 = v13;
    if ( v13 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, v13);
      }
      *(_QWORD *)pExceptionObject = &word_1800EC961;
      *(_QWORD *)&pExceptionObject[8] = 0;
      *(_QWORD *)&pExceptionObject[16] = 0;
      *(_DWORD *)&pExceptionObject[24] = v14;
      *(_QWORD *)&pExceptionObject[28] = -1;
      v33 = 0;
      throw (EvtException *)pExceptionObject;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        66,
        (unsigned int)&WPP_d3d936efbc913e3641017ad303784371_Traceguids,
        *(_QWORD *)(a1 + 712),
        (__int64)a2);
    }
    result = CloseHandle(v11);
    if ( a3 )
      return RpcRevertToSelf();
  }
  else
  {
    v17 = File::FlushFile(a1, 0, a5);
    v18 = v17;
    if ( v17 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, v17);
      }
      *(_QWORD *)pExceptionObject = &word_1800EC961;
      *(_QWORD *)&pExceptionObject[8] = 0;
      *(_QWORD *)&pExceptionObject[16] = 0;
      *(_DWORD *)&pExceptionObject[24] = v18;
      *(_QWORD *)&pExceptionObject[28] = -1;
      v33 = 0;
      throw (EvtException *)pExceptionObject;
    }
    hFile = CreateFileW(a2, 0x40000000u, 0, 0, 1u, 0, 0);
    if ( (unsigned __int64)hFile + 1 <= 1 )
    {
      v29 = GetLastError();
      if ( !v29 )
        v29 = 1287;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, v29);
      }
      v35 = 0;
      v36 = 0;
      v37 = v29;
      v38 = -1;
      v39 = 1999;
      throw (EvtException *)&v35;
    }
    p_hFile = &hFile;
    v43 = 1;
    FileHeader = (_OWORD *)ReadFileHeader(v53, *(_QWORD *)(a1 + 672));
    *(_OWORD *)Buffer = *FileHeader;
    v46 = FileHeader[1];
    *(_OWORD *)v47 = FileHeader[2];
    v48 = FileHeader[3];
    v49 = FileHeader[4];
    v50 = FileHeader[5];
    v51 = FileHeader[6];
    v52 = FileHeader[7];
    if ( !IsFileHeaderValid(Buffer) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, 1500);
      }
      memset(pExceptionObject, 0, 24);
      *(_QWORD *)&pExceptionObject[24] = -4294965796LL;
      *(_DWORD *)&pExceptionObject[32] = 2010;
      throw (EvtException *)pExceptionObject;
    }
    FileView::FileView((FileView *)v44, v20, 1);
    v21 = CalcNumberOfChunks(v47[1]);
    LOBYTE(v22) = BYTE8(v52) & 1;
    LOBYTE(dwCreationDispositiona) = 8;
    v23 = File::WriteFileHeader(hFile, Buffer, v22, 0, dwCreationDispositiona);
    v24 = v23;
    if ( v23 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, v23);
      }
      *(_QWORD *)pExceptionObject = &word_1800EC961;
      *(_QWORD *)&pExceptionObject[8] = 0;
      *(_QWORD *)&pExceptionObject[16] = 0;
      *(_DWORD *)&pExceptionObject[24] = v24;
      *(_QWORD *)&pExceptionObject[28] = -1;
      v33 = 0;
      throw (EvtException *)pExceptionObject;
    }
    v25 = 128;
    for ( i = 0; i < v21; ++i )
    {
      v27 = (i << 16) + 4096;
      FileView::ReadIn((FileView *)v44, *(void **)(a1 + 672), v27);
      if ( !IsChunkHeaderValid(v44[0]) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, 1500);
        }
        v35 = 0;
        v36 = 0;
        v37 = 1500;
        v38 = -1;
        v39 = 2026;
        throw (EvtException *)&v35;
      }
      *(_OWORD *)pExceptionObject = 0u;
      *(_QWORD *)&pExceptionObject[24] = 0;
      *(_DWORD *)&pExceptionObject[16] = ((_DWORD)i << 16) + 4096;
      *(_DWORD *)&pExceptionObject[20] = HIDWORD(v27);
      NumberOfBytesWritten[0] = 0;
      if ( !WriteFile(hFile, v44[2], 0x10000u, NumberOfBytesWritten, (LPOVERLAPPED)pExceptionObject) )
      {
        v28 = GetLastError();
        if ( !v28 )
          v28 = 1287;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, v28);
        }
        v35 = 0;
        v36 = 0;
        v37 = v28;
        v38 = -1;
        v39 = 2039;
        throw (EvtException *)&v35;
      }
      if ( NumberOfBytesWritten[0] != 0x10000 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, 4317);
        }
        v35 = 0;
        v36 = 0;
        v37 = 4317;
        v38 = -1;
        v39 = 2044;
        throw (EvtException *)&v35;
      }
      v25 += 0x10000;
      CheckCancellation(0);
    }
    if ( !v25 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, 4317);
      }
      v35 = 0;
      v36 = 0;
      v37 = 4317;
      v38 = -1;
      v39 = 2054;
      throw (EvtException *)&v35;
    }
    v43 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        75,
        (unsigned int)&WPP_d3d936efbc913e3641017ad303784371_Traceguids,
        *(_QWORD *)(a1 + 712),
        (__int64)a2);
    }
    FileView::~FileView((FileView *)v44);
    tlx::_UndoSolo__File::BackupLog_::_2_::_lambda_2___::__UndoSolo__File::BackupLog_::_2_::_lambda_2___(&p_hFile);
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hFile);
    return tlx::_UndoSolo__File::BackupLog_::_2_::_lambda_1___::__UndoSolo__File::BackupLog_::_2_::_lambda_1___(v34);
  }
  return result;
}

```

## disassembly

```asm
0x180041a00  mov     [rsp-8+arg_10], rbx
0x180041a05  push    rbp
0x180041a06  push    rsi
0x180041a07  push    rdi
0x180041a08  push    r12
0x180041a0a  push    r13
0x180041a0c  push    r14
0x180041a0e  push    r15
0x180041a10  lea     rbp, [rsp-100h]
0x180041a18  sub     rsp, 200h
0x180041a1f  mov     rax, cs:__security_cookie
0x180041a26  xor     rax, rsp
0x180041a29  mov     [rbp+130h+var_40], rax
0x180041a30  mov     r15b, r8b
0x180041a33  mov     r12, rdx
0x180041a36  mov     rdi, rcx
0x180041a39  mov     rbx, [rbp+130h+arg_20]
0x180041a40  xor     r13d, r13d
0x180041a43  test    r8b, r8b
0x180041a46  jz      loc_180041AD1
0x180041a4c  xor     ecx, ecx; BindingHandle
0x180041a4e  call    cs:__imp_RpcImpersonateClient
0x180041a54  mov     esi, eax
0x180041a56  test    eax, eax
0x180041a58  jz      short loc_180041AD1
0x180041a5a  lea     rcx, WPP_GLOBAL_Control
0x180041a61  mov     r10, cs:WPP_GLOBAL_Control
0x180041a68  cmp     r10, rcx
0x180041a6b  jz      short loc_180041A97
0x180041a6d  test    dword ptr [r10+1Ch], 8000h
0x180041a75  jz      short loc_180041A97
0x180041a77  lea     ebx, [r13+2]
0x180041a7b  cmp     [r10+19h], bl
0x180041a7f  jb      short loc_180041A97
0x180041a81  lea     edx, [rbx+3Ch]
0x180041a84  mov     r9d, eax
0x180041a87  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x180041a8e  mov     rcx, [r10+10h]
0x180041a92  call    WPP_SF_d
0x180041a97  lea     rax, word_1800EC961
0x180041a9e  mov     qword ptr [rsp+230h+pExceptionObject], rax
0x180041aa3  mov     qword ptr [rsp+230h+pExceptionObject+8], r13
0x180041aa8  mov     [rsp+230h+var_1E0], r13
0x180041aad  mov     dword ptr [rsp+230h+var_1D8], esi
0x180041ab1  mov     [rsp+230h+var_1D8+4], 0FFFFFFFFFFFFFFFFh
0x180041aba  mov     [rsp+230h+var_1CC], r13b
0x180041abf  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180041ac6  lea     rcx, [rsp+230h+pExceptionObject]; pExceptionObject
0x180041acb  call    _CxxThrowException_0
0x180041ad1  mov     [rsp+230h+var_1C8], r15b
0x180041ad6  mov     r14d, 1
0x180041adc  mov     [rsp+230h+var_1C7], r14b
0x180041ae1  cmp     [rdi+340h], r13b
0x180041ae8  jz      loc_180041DAF
0x180041aee  mov     [rsp+230h+hTemplateFile], r13; hTemplateFile
0x180041af3  mov     [rsp+230h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x180041af8  mov     [rsp+230h+dwCreationDisposition], 4; dwCreationDisposition
0x180041b00  xor     r9d, r9d; lpSecurityAttributes
0x180041b03  xor     r8d, r8d; dwShareMode
0x180041b06  mov     edx, 0C0000000h; dwDesiredAccess
0x180041b0b  mov     rcx, r12; lpFileName
0x180041b0e  call    cs:__imp_CreateFileW
0x180041b14  mov     rsi, rax
0x180041b17  mov     qword ptr [rbp+130h+NumberOfBytesWritten], rax
0x180041b1b  lea     rcx, [rax+1]
0x180041b1f  cmp     rcx, r14
0x180041b22  jbe     loc_180041D2C
0x180041b28  mov     rcx, rax; hFile
0x180041b2b  call    cs:__imp_GetFileType
0x180041b31  cmp     eax, r14d
0x180041b34  jz      short loc_180041BAA
0x180041b36  lea     rcx, WPP_GLOBAL_Control
0x180041b3d  mov     edi, 10CCh
0x180041b42  mov     rax, cs:WPP_GLOBAL_Control
0x180041b49  cmp     rax, rcx
0x180041b4c  jz      short loc_180041B76
0x180041b4e  test    dword ptr [rax+1Ch], 8000h
0x180041b55  jz      short loc_180041B76
0x180041b57  lea     ebx, [r14+1]
0x180041b5b  cmp     [rax+19h], bl
0x180041b5e  jb      short loc_180041B76
0x180041b60  lea     edx, [rbx+3Eh]
0x180041b63  mov     r9d, edi
0x180041b66  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x180041b6d  mov     rcx, [rax+10h]
0x180041b71  call    WPP_SF_d
0x180041b76  xorps   xmm0, xmm0
0x180041b79  movdqu  [rsp+230h+pExceptionObject], xmm0
0x180041b7f  mov     [rsp+230h+var_1E0], r13
0x180041b84  mov     dword ptr [rsp+230h+var_1D8], edi
0x180041b88  mov     dword ptr [rsp+230h+var_1D8+4], 0FFFFFFFFh
0x180041b90  mov     dword ptr [rsp+60h], 7B9h
0x180041b98  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180041b9f  lea     rcx, [rsp+230h+pExceptionObject]; pExceptionObject
0x180041ba4  call    _CxxThrowException_0
0x180041baa  mov     r9b, [rdi+339h]
0x180041bb1  xor     r8d, r8d; unsigned __int64
0x180041bb4  mov     rdx, r14; unsigned __int64
0x180041bb7  mov     rcx, rsi; void *
0x180041bba  call    AddBlankChunk
0x180041bbf  mov     r14d, 80h
0x180041bc5  mov     r8d, r14d; Size
0x180041bc8  xor     edx, edx; Val
0x180041bca  lea     rcx, [rbp+130h+var_C0]; void *
0x180041bce  call    memset_0
0x180041bd3  mov     rax, qword ptr cs:aElffile; "ElfFile"
0x180041bda  mov     [rbp+130h+var_C0], rax
0x180041bde  mov     [rbp+130h+var_A8], r13
0x180041be5  mov     [rbp+130h+var_A0], r14d
0x180041bec  mov     [rbp+130h+var_9C], 30002h
0x180041bf6  lea     ebx, [r14-7Eh]
0x180041bfa  lea     ecx, [rbx-1]; unsigned __int64
0x180041bfd  call    ?CalcFileSizeNeeded@@YA_K_K@Z; CalcFileSizeNeeded(unsigned __int64)
0x180041c02  mov     [rbp+130h+var_98], rax
0x180041c09  mov     [rbp+130h+var_44], r13d
0x180041c10  mov     [rbp+130h+var_B0], r13
0x180041c17  mov     byte ptr [rsp+230h+dwCreationDisposition], r13b
0x180041c1c  mov     r9b, 1
0x180041c1f  xor     r8d, r8d
0x180041c22  lea     rdx, [rbp+130h+var_C0]
0x180041c26  mov     rcx, rsi
0x180041c29  call    ?WriteFileHeader@File@@CAKPEAXPEAUFileHeader@@_N2W4FileModeFlags@@@Z; File::WriteFileHeader(void *,FileHeader *,bool,bool,FileModeFlags)
0x180041c2e  mov     r14d, eax
0x180041c31  test    eax, eax
0x180041c33  jz      short loc_180041CA9
0x180041c35  lea     rcx, WPP_GLOBAL_Control
0x180041c3c  mov     r10, cs:WPP_GLOBAL_Control
0x180041c43  cmp     r10, rcx
0x180041c46  jz      short loc_180041C6E
0x180041c48  test    dword ptr [r10+1Ch], 8000h
0x180041c50  jz      short loc_180041C6E
0x180041c52  cmp     [r10+19h], bl
0x180041c56  jb      short loc_180041C6E
0x180041c58  lea     edx, [rbx+3Fh]
0x180041c5b  mov     r9d, eax
0x180041c5e  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x180041c65  mov     rcx, [r10+10h]
0x180041c69  call    WPP_SF_d
0x180041c6e  lea     rax, word_1800EC961
0x180041c75  mov     qword ptr [rsp+230h+pExceptionObject], rax
0x180041c7a  mov     qword ptr [rsp+230h+pExceptionObject+8], r13
0x180041c7f  mov     [rsp+230h+var_1E0], r13
0x180041c84  mov     dword ptr [rsp+230h+var_1D8], r14d
0x180041c89  mov     [rsp+230h+var_1D8+4], 0FFFFFFFFFFFFFFFFh
0x180041c92  mov     [rsp+230h+var_1CC], r13b
0x180041c97  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180041c9e  lea     rcx, [rsp+230h+pExceptionObject]; pExceptionObject
0x180041ca3  call    _CxxThrowException_0
0x180041ca9  lea     rcx, WPP_GLOBAL_Control
0x180041cb0  mov     rax, cs:WPP_GLOBAL_Control
0x180041cb7  cmp     rax, rcx
0x180041cba  jz      short loc_180041CED
0x180041cbc  test    dword ptr [rax+1Ch], 200h
0x180041cc3  jz      short loc_180041CED
0x180041cc5  cmp     byte ptr [rax+19h], 4
0x180041cc9  jb      short loc_180041CED
0x180041ccb  mov     edx, 42h ; 'B'
0x180041cd0  mov     qword ptr [rsp+230h+dwCreationDisposition], r12
0x180041cd5  mov     r9, [rdi+2C8h]
0x180041cdc  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x180041ce3  mov     rcx, [rax+10h]
0x180041ce7  call    WPP_SF_SS
0x180041cec  nop
0x180041ced  mov     rcx, rsi; hObject
0x180041cf0  call    cs:__imp_CloseHandle
0x180041cf6  nop
0x180041cf7  test    r15b, r15b
0x180041cfa  jz      short loc_180041D02
0x180041cfc  call    cs:__imp_RpcRevertToSelf
0x180041d02  mov     rcx, [rbp+130h+var_40]
0x180041d09  xor     rcx, rsp; StackCookie
0x180041d0c  call    __security_check_cookie
0x180041d11  mov     rbx, [rsp+230h+arg_10]
0x180041d19  add     rsp, 200h
0x180041d20  pop     r15
0x180041d22  pop     r14
0x180041d24  pop     r13
0x180041d26  pop     r12
0x180041d28  pop     rdi
0x180041d29  pop     rsi
0x180041d2a  pop     rbp
0x180041d2b  retn
0x180041d2c  call    cs:__imp_GetLastError
0x180041d32  nop
0x180041d33  mov     edi, eax
0x180041d35  mov     eax, 507h
0x180041d3a  test    edi, edi
0x180041d3c  cmovz   edi, eax
0x180041d3f  lea     rcx, WPP_GLOBAL_Control
0x180041d46  mov     rax, cs:WPP_GLOBAL_Control
0x180041d4d  cmp     rax, rcx
0x180041d50  jz      short loc_180041D7B
0x180041d52  test    dword ptr [rax+1Ch], 8000h
0x180041d59  jz      short loc_180041D7B
0x180041d5b  mov     ebx, 2
0x180041d60  cmp     [rax+19h], bl
0x180041d63  jb      short loc_180041D7B
0x180041d65  lea     edx, [rbx+3Dh]
0x180041d68  mov     r9d, edi
0x180041d6b  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x180041d72  mov     rcx, [rax+10h]
0x180041d76  call    WPP_SF_d
0x180041d7b  xorps   xmm0, xmm0
0x180041d7e  movdqu  [rsp+230h+pExceptionObject], xmm0
0x180041d84  mov     [rsp+230h+var_1E0], r13
0x180041d89  mov     dword ptr [rsp+230h+var_1D8], edi
0x180041d8d  mov     dword ptr [rsp+230h+var_1D8+4], 0FFFFFFFFh
0x180041d95  mov     dword ptr [rsp+60h], 7B5h
0x180041d9d  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180041da4  lea     rcx, [rsp+230h+pExceptionObject]; pExceptionObject
0x180041da9  call    _CxxThrowException_0
0x180041daf  mov     r8, rbx
0x180041db2  xor     edx, edx
0x180041db4  mov     rcx, rdi
0x180041db7  call    ?FlushFile@File@@AEAAKW4FlushType@@AEAV?$unique_lock@Vshared_mutex@utl@@@utl@@@Z; File::FlushFile(FlushType,utl::unique_lock<utl::shared_mutex> &)
0x180041dbc  mov     esi, eax
0x180041dbe  test    eax, eax
0x180041dc0  jz      short loc_180041E3A
0x180041dc2  lea     rcx, WPP_GLOBAL_Control
0x180041dc9  mov     r10, cs:WPP_GLOBAL_Control
0x180041dd0  cmp     r10, rcx
0x180041dd3  jz      short loc_180041E00
0x180041dd5  test    dword ptr [r10+1Ch], 8000h
0x180041ddd  jz      short loc_180041E00
0x180041ddf  mov     ebx, 2
0x180041de4  cmp     [r10+19h], bl
0x180041de8  jb      short loc_180041E00
0x180041dea  lea     edx, [rbx+41h]
0x180041ded  mov     r9d, eax
0x180041df0  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x180041df7  mov     rcx, [r10+10h]
0x180041dfb  call    WPP_SF_d
0x180041e00  lea     rax, word_1800EC961
0x180041e07  mov     qword ptr [rsp+230h+pExceptionObject], rax
0x180041e0c  mov     qword ptr [rsp+230h+pExceptionObject+8], r13
0x180041e11  mov     [rsp+230h+var_1E0], r13
0x180041e16  mov     dword ptr [rsp+230h+var_1D8], esi
0x180041e1a  mov     [rsp+230h+var_1D8+4], 0FFFFFFFFFFFFFFFFh
0x180041e23  mov     [rsp+230h+var_1CC], r13b
0x180041e28  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180041e2f  lea     rcx, [rsp+230h+pExceptionObject]; pExceptionObject
0x180041e34  call    _CxxThrowException_0
0x180041e3a  mov     [rsp+230h+hTemplateFile], r13; hTemplateFile
0x180041e3f  mov     [rsp+230h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x180041e44  mov     [rsp+230h+dwCreationDisposition], r14d; dwCreationDisposition
0x180041e49  xor     r9d, r9d; lpSecurityAttributes
0x180041e4c  xor     r8d, r8d; dwShareMode
0x180041e4f  mov     edx, 40000000h; dwDesiredAccess
0x180041e54  mov     rcx, r12; lpFileName
0x180041e57  call    cs:__imp_CreateFileW
0x180041e5d  mov     [rbp+130h+hFile], rax
0x180041e61  inc     rax
0x180041e64  cmp     rax, r14
0x180041e67  jbe     loc_1800422F3
0x180041e6d  lea     rax, [rbp+130h+hFile]
0x180041e71  mov     [rbp+130h+var_188], rax
0x180041e75  mov     [rbp+130h+var_180], r14b
0x180041e79  mov     rdx, [rdi+2A0h]
0x180041e80  lea     rcx, [rbp+130h+var_C0]
0x180041e84  call    ReadFileHeader
0x180041e89  movups  xmm0, xmmword ptr [rax]
0x180041e8c  movaps  xmmword ptr [rbp+130h+Buffer], xmm0
0x180041e90  movups  xmm1, xmmword ptr [rax+10h]
0x180041e94  movaps  [rbp+130h+var_130], xmm1
0x180041e98  movups  xmm0, xmmword ptr [rax+20h]
0x180041e9c  movaps  xmmword ptr [rbp+130h+var_120], xmm0
0x180041ea0  movups  xmm1, xmmword ptr [rax+30h]
0x180041ea4  movaps  [rbp+130h+var_110], xmm1
0x180041ea8  movups  xmm0, xmmword ptr [rax+40h]
0x180041eac  movaps  [rbp+130h+var_100], xmm0
0x180041eb0  movups  xmm1, xmmword ptr [rax+50h]
0x180041eb4  movaps  [rbp+130h+var_F0], xmm1
0x180041eb8  movups  xmm0, xmmword ptr [rax+60h]
0x180041ebc  movaps  [rbp+130h+var_E0], xmm0
0x180041ec0  movups  xmm1, xmmword ptr [rax+70h]
0x180041ec4  movaps  [rbp+130h+var_D0], xmm1
0x180041ec8  lea     rcx, [rbp+130h+Buffer]; Buffer
0x180041ecc  call    ?IsFileHeaderValid@@YA_NAEBUFileHeader@@@Z; IsFileHeaderValid(FileHeader const &)
0x180041ed1  test    al, al
0x180041ed3  jnz     short loc_180041F4A
0x180041ed5  lea     rcx, WPP_GLOBAL_Control
0x180041edc  mov     edi, 5DCh
0x180041ee1  mov     rax, cs:WPP_GLOBAL_Control
0x180041ee8  cmp     rax, rcx
0x180041eeb  jz      short loc_180041F16
0x180041eed  test    dword ptr [rax+1Ch], 8000h
0x180041ef4  jz      short loc_180041F16
0x180041ef6  mov     ebx, 2
0x180041efb  cmp     [rax+19h], bl
0x180041efe  jb      short loc_180041F16
0x180041f00  lea     edx, [rbx+43h]
0x180041f03  mov     r9d, edi
0x180041f06  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x180041f0d  mov     rcx, [rax+10h]
0x180041f11  call    WPP_SF_d
0x180041f16  xorps   xmm0, xmm0
0x180041f19  movdqu  [rsp+230h+pExceptionObject], xmm0
0x180041f1f  mov     [rsp+230h+var_1E0], r13
0x180041f24  mov     dword ptr [rsp+230h+var_1D8], edi
0x180041f28  mov     dword ptr [rsp+230h+var_1D8+4], 0FFFFFFFFh
  ... truncated ...
```
