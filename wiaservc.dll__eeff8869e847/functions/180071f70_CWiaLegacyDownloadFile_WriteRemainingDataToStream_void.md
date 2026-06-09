# CWiaLegacyDownloadFile::WriteRemainingDataToStream(void)

- ea: `0x180071f70`
- end: `0x180072200`
- name: `?WriteRemainingDataToStream@CWiaLegacyDownloadFile@@UEAAJXZ`
- size: `656`
- prototype: `__int64 __fastcall(CWiaLegacyDownloadFile *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x18000b6a0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18002de18`
- `0x18002def8`
- `0x18002e9d8`
- `0x18002eab4`
- `0x180059190`
- `0x180071f70`
- `0x180078010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800720dc`
- `KERNEL32!CloseHandle` at `0x1800720dc`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180071ff0`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180071ff0`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180072022`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180072022`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x18007204f`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x18007204f`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18007207d`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18007207d`

## string_xrefs

- `0x1800720ee`: `CreateFileMapping failed, hr = 0x%X`
- `0x180072118`: `CreateFileMapping failed, hr = 0x%X`
- `0x18007209d`: `CWiaLegacyDownloadFile::WriteRemainingDataToStream`
- `0x1800720cd`: `CWiaLegacyDownloadFile::WriteRemainingDataToStream`
- `0x1800720ff`: `CWiaLegacyDownloadFile::WriteRemainingDataToStream`
- `0x18007212f`: `CWiaLegacyDownloadFile::WriteRemainingDataToStream`
- `0x18007214e`: `CWiaLegacyDownloadFile::WriteRemainingDataToStream`
- `0x18007217b`: `CWiaLegacyDownloadFile::WriteRemainingDataToStream`
- `0x1800721af`: `CWiaLegacyDownloadFile::WriteRemainingDataToStream`
- `0x1800721df`: `CWiaLegacyDownloadFile::WriteRemainingDataToStream`

## pseudocode

```c
__int64 __fastcall CWiaLegacyDownloadFile::WriteRemainingDataToStream(CWiaLegacyDownloadFile *this)
{
  __int64 v2; // rcx
  int v3; // edi
  __int64 v4; // r8
  __int64 v5; // rdx
  int LastErrorHRESULT; // eax
  DWORD dwMaximumSizeLow; // eax
  SIZE_T v8; // rbx
  HANDLE FileMappingW; // rax
  void *v10; // rbp
  const void *v11; // r14
  char *v12; // rbx
  void *v13; // rdx
  void **v14; // rax
  void *v15; // rdx
  __int64 v16; // rcx
  char *v17; // rbx
  void *v18; // rdx
  void **v19; // rax
  void *v20; // rdx
  __int64 v21; // rcx
  char *v22; // rbx
  void *v23; // rdx
  void **v24; // rax
  void *v25; // rdx
  __int64 v26; // rcx
  char *v27; // rbx
  void *v28; // rdx
  void **v29; // rax
  void *v30; // rdx
  __int64 v31; // rcx
  unsigned int v33; // [rsp+50h] [rbp+8h] BYREF
  __int64 v34; // [rsp+58h] [rbp+10h]

  v34 = 0;
  v2 = *((_QWORD *)this + 3);
  v33 = 0;
  v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v2 + 40LL))(v2, 0, 2);
  if ( v3 < 0 )
  {
    v27 = (char *)WiaTrace_TraceLog("Seeking to end of stream failed, hr = 0x%X");
    WriteDbgTraceErrorWI("CWiaLegacyDownloadFile::WriteRemainingDataToStream", v27);
    WiaTrcLib::Free((WiaTrcLib *)v27, v28);
    v29 = (void **)WiaTrace_Trace("Seeking to end of stream failed, hr = 0x%X", v3);
    WiaTrace_ProcessTrace_Ex(v31, v30, (void *)"CWiaLegacyDownloadFile::WriteRemainingDataToStream", 1, v29);
    return (unsigned int)v3;
  }
  v4 = *((unsigned int *)this + 27);
  if ( (_DWORD)v4 )
  {
    v5 = *((_QWORD *)this + 12);
    if ( v5 )
    {
      LastErrorHRESULT = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, unsigned int *))(**((_QWORD **)this + 3)
                                                                                             + 32LL))(
                           *((_QWORD *)this + 3),
                           v5,
                           v4,
                           &v33);
LABEL_15:
      v3 = LastErrorHRESULT;
      goto LABEL_16;
    }
  }
  dwMaximumSizeLow = GetFileSize(*((HANDLE *)this + 11), 0);
  v8 = dwMaximumSizeLow;
  if ( dwMaximumSizeLow == -1 )
  {
    LastErrorHRESULT = GetLastErrorHRESULT();
    goto LABEL_15;
  }
  if ( !dwMaximumSizeLow )
  {
    v22 = (char *)WiaTrace_TraceLogWithSubComp(0, "Driver wrote zero bytes");
    WriteDbgTraceWarningWI("CWiaLegacyDownloadFile::WriteRemainingDataToStream", v22);
    WiaTrcLib::Free((WiaTrcLib *)v22, v23);
    v24 = (void **)WiaTrace_TraceWithSubComp(0, "Driver wrote zero bytes");
    WiaTrace_ProcessTrace_Ex(v26, v25, (void *)"CWiaLegacyDownloadFile::WriteRemainingDataToStream", 2, v24);
LABEL_17:
    *((_QWORD *)this + 7) = v33;
    return (unsigned int)v3;
  }
  FileMappingW = CreateFileMappingW(*((HANDLE *)this + 11), 0, 2u, 0, dwMaximumSizeLow, 0);
  v10 = FileMappingW;
  if ( FileMappingW )
  {
    v11 = MapViewOfFileEx(FileMappingW, 4u, 0, 0, v8, 0);
    if ( v11 )
    {
      v3 = (*(__int64 (__fastcall **)(_QWORD, const void *, _QWORD, unsigned int *))(**((_QWORD **)this + 3) + 32LL))(
             *((_QWORD *)this + 3),
             v11,
             (unsigned int)v8,
             &v33);
      UnmapViewOfFile(v11);
    }
    else
    {
      v3 = GetLastErrorHRESULT();
      v12 = (char *)WiaTrace_TraceLog("MapViewOfFileEx failed, hr = 0x%X");
      WriteDbgTraceErrorWI("CWiaLegacyDownloadFile::WriteRemainingDataToStream", v12);
      WiaTrcLib::Free((WiaTrcLib *)v12, v13);
      v14 = (void **)WiaTrace_Trace("MapViewOfFileEx failed, hr = 0x%X", v3);
      WiaTrace_ProcessTrace_Ex(v16, v15, (void *)"CWiaLegacyDownloadFile::WriteRemainingDataToStream", 1, v14);
    }
    CloseHandle(v10);
  }
  else
  {
    v3 = GetLastErrorHRESULT();
    v17 = (char *)WiaTrace_TraceLog("CreateFileMapping failed, hr = 0x%X");
    WriteDbgTraceErrorWI("CWiaLegacyDownloadFile::WriteRemainingDataToStream", v17);
    WiaTrcLib::Free((WiaTrcLib *)v17, v18);
    v19 = (void **)WiaTrace_Trace("CreateFileMapping failed, hr = 0x%X", v3);
    WiaTrace_ProcessTrace_Ex(v21, v20, (void *)"CWiaLegacyDownloadFile::WriteRemainingDataToStream", 1, v19);
  }
LABEL_16:
  if ( v3 >= 0 )
    goto LABEL_17;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180071f70  mov     rax, rsp
0x180071f73  mov     [rax+18h], rbx
0x180071f77  mov     [rax+20h], rbp
0x180071f7b  push    rsi
0x180071f7c  push    rdi
0x180071f7d  push    r14
0x180071f7f  sub     rsp, 30h
0x180071f83  mov     qword ptr [rax+10h], 0
0x180071f8b  mov     rsi, rcx
0x180071f8e  mov     rcx, [rcx+18h]
0x180071f92  xor     r9d, r9d
0x180071f95  mov     rdx, [rsp+48h+arg_8]
0x180071f9a  mov     dword ptr [rax+8], 0
0x180071fa1  mov     rax, [rcx]
0x180071fa4  lea     ebp, [r9+2]
0x180071fa8  mov     r8d, ebp
0x180071fab  mov     rax, [rax+28h]
0x180071faf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071fb4  mov     edi, eax
0x180071fb6  test    eax, eax
0x180071fb8  js      loc_18007219E
0x180071fbe  mov     r8d, [rsi+6Ch]
0x180071fc2  test    r8d, r8d
0x180071fc5  jz      short loc_180071FEA
0x180071fc7  mov     rdx, [rsi+60h]
0x180071fcb  test    rdx, rdx
0x180071fce  jz      short loc_180071FEA
0x180071fd0  mov     rcx, [rsi+18h]
0x180071fd4  lea     r9, [rsp+48h+arg_0]
0x180071fd9  mov     rax, [rcx]
0x180071fdc  mov     rax, [rax+20h]
0x180071fe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071fe5  jmp     loc_18007218E
0x180071fea  mov     rcx, [rsi+58h]; hFile
0x180071fee  xor     edx, edx; lpFileSizeHigh
0x180071ff0  call    cs:__imp_GetFileSize
0x180071ff6  mov     ebx, eax
0x180071ff8  cmp     eax, 0FFFFFFFFh
0x180071ffb  jz      loc_180072189
0x180072001  test    eax, eax
0x180072003  jz      loc_18007213D
0x180072009  mov     rcx, [rsi+58h]; hFile
0x18007200d  xor     r9d, r9d; dwMaximumSizeHigh
0x180072010  mov     [rsp+48h+lpName], 0; lpName
0x180072019  mov     r8d, ebp; flProtect
0x18007201c  xor     edx, edx; lpFileMappingAttributes
0x18007201e  mov     [rsp+48h+dwMaximumSizeLow], ebx; dwMaximumSizeLow
0x180072022  call    cs:__imp_CreateFileMappingW
0x180072028  mov     rbp, rax
0x18007202b  test    rax, rax
0x18007202e  jz      loc_1800720E7
0x180072034  xor     r9d, r9d; dwFileOffsetLow
0x180072037  mov     [rsp+48h+lpName], 0; lpBaseAddress
0x180072040  xor     r8d, r8d; dwFileOffsetHigh
0x180072043  mov     qword ptr [rsp+48h+dwMaximumSizeLow], rbx; dwNumberOfBytesToMap
0x180072048  mov     rcx, rax; hFileMappingObject
0x18007204b  lea     edx, [r9+4]; dwDesiredAccess
0x18007204f  call    cs:__imp_MapViewOfFileEx
0x180072055  mov     r14, rax
0x180072058  test    rax, rax
0x18007205b  jz      short loc_180072085
0x18007205d  mov     rcx, [rsi+18h]
0x180072061  lea     r9, [rsp+48h+arg_0]
0x180072066  mov     r8d, ebx
0x180072069  mov     rdx, [rcx]
0x18007206c  mov     rax, [rdx+20h]
0x180072070  mov     rdx, r14
0x180072073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072078  mov     rcx, r14; lpBaseAddress
0x18007207b  mov     edi, eax
0x18007207d  call    cs:__imp_UnmapViewOfFile
0x180072083  jmp     short loc_1800720D9
0x180072085  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18007208a  mov     edx, eax
0x18007208c  lea     rcx, aMapviewoffilee; "MapViewOfFileEx failed, hr = 0x%X"
0x180072093  mov     edi, eax
0x180072095  call    WiaTrace_TraceLog
0x18007209a  mov     rdx, rax; char *
0x18007209d  lea     rcx, aCwialegacydown_0; "CWiaLegacyDownloadFile::WriteRemainingD"...
0x1800720a4  mov     rbx, rax
0x1800720a7  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800720ac  mov     rcx, rbx; this
0x1800720af  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800720b4  mov     edx, edi
0x1800720b6  lea     rcx, aMapviewoffilee; "MapViewOfFileEx failed, hr = 0x%X"
0x1800720bd  call    WiaTrace_Trace
0x1800720c2  mov     r9d, 1; int
0x1800720c8  mov     qword ptr [rsp+48h+dwMaximumSizeLow], rax; lpMem
0x1800720cd  lea     r8, aCwialegacydown_0; "CWiaLegacyDownloadFile::WriteRemainingD"...
0x1800720d4  call    WiaTrace_ProcessTrace_Ex
0x1800720d9  mov     rcx, rbp; hObject
0x1800720dc  call    cs:__imp_CloseHandle
0x1800720e2  jmp     loc_180072190
0x1800720e7  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x1800720ec  mov     edx, eax
0x1800720ee  lea     rcx, aCreatefilemapp; "CreateFileMapping failed, hr = 0x%X"
0x1800720f5  mov     edi, eax
0x1800720f7  call    WiaTrace_TraceLog
0x1800720fc  mov     rdx, rax; char *
0x1800720ff  lea     rcx, aCwialegacydown_0; "CWiaLegacyDownloadFile::WriteRemainingD"...
0x180072106  mov     rbx, rax
0x180072109  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18007210e  mov     rcx, rbx; this
0x180072111  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180072116  mov     edx, edi
0x180072118  lea     rcx, aCreatefilemapp; "CreateFileMapping failed, hr = 0x%X"
0x18007211f  call    WiaTrace_Trace
0x180072124  mov     r9d, 1; int
0x18007212a  mov     qword ptr [rsp+48h+dwMaximumSizeLow], rax; lpMem
0x18007212f  lea     r8, aCwialegacydown_0; "CWiaLegacyDownloadFile::WriteRemainingD"...
0x180072136  call    WiaTrace_ProcessTrace_Ex
0x18007213b  jmp     short loc_180072190
0x18007213d  lea     rdx, aDriverWroteZer; "Driver wrote zero bytes"
0x180072144  xor     ecx, ecx
0x180072146  call    WiaTrace_TraceLogWithSubComp
0x18007214b  mov     rdx, rax; char *
0x18007214e  lea     rcx, aCwialegacydown_0; "CWiaLegacyDownloadFile::WriteRemainingD"...
0x180072155  mov     rbx, rax
0x180072158  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18007215d  mov     rcx, rbx; this
0x180072160  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180072165  lea     rdx, aDriverWroteZer; "Driver wrote zero bytes"
0x18007216c  xor     ecx, ecx
0x18007216e  call    WiaTrace_TraceWithSubComp
0x180072173  mov     r9d, ebp; int
0x180072176  mov     qword ptr [rsp+48h+dwMaximumSizeLow], rax; lpMem
0x18007217b  lea     r8, aCwialegacydown_0; "CWiaLegacyDownloadFile::WriteRemainingD"...
0x180072182  call    WiaTrace_ProcessTrace_Ex
0x180072187  jmp     short loc_180072194
0x180072189  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18007218e  mov     edi, eax
0x180072190  test    edi, edi
0x180072192  js      short loc_1800721EB
0x180072194  mov     eax, [rsp+48h+arg_0]
0x180072198  mov     [rsi+38h], rax
0x18007219c  jmp     short loc_1800721EB
0x18007219e  mov     edx, edi
0x1800721a0  lea     rcx, aSeekingToEndOf; "Seeking to end of stream failed, hr = 0"...
0x1800721a7  call    WiaTrace_TraceLog
0x1800721ac  mov     rdx, rax; char *
0x1800721af  lea     rcx, aCwialegacydown_0; "CWiaLegacyDownloadFile::WriteRemainingD"...
0x1800721b6  mov     rbx, rax
0x1800721b9  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800721be  mov     rcx, rbx; this
0x1800721c1  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800721c6  mov     edx, edi
0x1800721c8  lea     rcx, aSeekingToEndOf; "Seeking to end of stream failed, hr = 0"...
0x1800721cf  call    WiaTrace_Trace
0x1800721d4  mov     r9d, 1; int
0x1800721da  mov     qword ptr [rsp+48h+dwMaximumSizeLow], rax; lpMem
0x1800721df  lea     r8, aCwialegacydown_0; "CWiaLegacyDownloadFile::WriteRemainingD"...
0x1800721e6  call    WiaTrace_ProcessTrace_Ex
0x1800721eb  mov     rbx, [rsp+48h+arg_10]
0x1800721f0  mov     eax, edi
0x1800721f2  mov     rbp, [rsp+48h+arg_18]
0x1800721f7  add     rsp, 30h
0x1800721fb  pop     r14
0x1800721fd  pop     rdi
0x1800721fe  pop     rsi
0x1800721ff  retn
```
