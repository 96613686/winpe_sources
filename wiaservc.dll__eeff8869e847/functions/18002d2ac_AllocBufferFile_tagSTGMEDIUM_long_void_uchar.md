# AllocBufferFile(tagSTGMEDIUM *,long,void * *,uchar * *)

- ea: `0x18002d2ac`
- end: `0x18002d55b`
- name: `?AllocBufferFile@@YAJPEAUtagSTGMEDIUM@@JPEAPEAXPEAPEAE@Z`
- size: `687`
- prototype: `__int64 __fastcall(struct tagSTGMEDIUM *, int, void **, LPVOID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180066774`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x1800202b8`
- `0x18002d2ac`
- `0x18002de18`
- `0x18002def8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002d351`
- `KERNEL32!GetLastError` at `0x18002d351`
- `KERNEL32!CloseHandle` at `0x18002d3d0`
- `KERNEL32!CloseHandle` at `0x18002d521`
- `KERNEL32!CloseHandle` at `0x18002d3d0`
- `KERNEL32!CloseHandle` at `0x18002d521`
- `ole32!CoTaskMemFree` at `0x18002d530`
- `ole32!CoTaskMemFree` at `0x18002d530`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18002d306`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18002d306`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002d342`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002d342`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x18002d3c2`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x18002d3c2`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18002d4eb`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18002d4eb`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x18002d514`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x18002d514`

## string_xrefs

- `0x18002d35a`: `CreateFile on %S failed, GetLastError = 0x%X`
- `0x18002d384`: `CreateFile on %S failed, GetLastError = 0x%X`
- `0x18002d485`: `CoImpersonateClient failed (0x%X)`
- `0x18002d4a9`: `CoImpersonateClient failed (0x%X)`

## pseudocode

```c
__int64 __fastcall AllocBufferFile(struct tagSTGMEDIUM *a1, int a2, void **a3, LPVOID *a4)
{
  SIZE_T v5; // r15
  struct tagWiaTraceData_Type *v8; // rax
  char *v9; // rdx
  unsigned int v10; // r8d
  union tagSTGMEDIUM::$7B772CC839E5463FC51219F893F364BB *p_hBitmap; // rsi
  int LastError; // edi
  HANDLE FileW; // rax
  char *v14; // rbx
  void *v15; // rdx
  void *v16; // rax
  int v17; // edx
  int v18; // ecx
  char *v19; // rbx
  void *v20; // rdx
  void *v21; // rax
  int v22; // edx
  int v23; // ecx
  int v24; // ebp
  char *v25; // rbx
  void *v26; // rdx
  void *v27; // rax
  int v28; // edx
  int v29; // ecx
  char *v30; // rbx
  void *v31; // rdx
  void *v32; // rax
  int v33; // edx
  int v34; // ecx
  HANDLE FileMappingW; // rax
  void *v36; // rbx
  unsigned int dwCreationDisposition; // [rsp+20h] [rbp-A8h]
  _BYTE v39[136]; // [rsp+40h] [rbp-88h] BYREF

  v5 = a2;
  v8 = (struct tagWiaTraceData_Type *)WiaTrace_Trace("::AllocBufferFile");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v39, v9, v10, "AllocBufferFile", dwCreationDisposition, v8);
  *a3 = 0;
  *a4 = 0;
  a1->pUnkForRelease = 0;
  p_hBitmap = (union tagSTGMEDIUM::$7B772CC839E5463FC51219F893F364BB *)&a1->hBitmap;
  LastError = CoImpersonateClient();
  if ( LastError < 0 )
  {
    v30 = (char *)WiaTrace_TraceLog("CoImpersonateClient failed (0x%X)");
    WriteDbgTraceErrorWI("AllocBufferFile", v30);
    WiaTrcLib::Free((WiaTrcLib *)v30, v31);
    v32 = (void *)WiaTrace_Trace("CoImpersonateClient failed (0x%X)", LastError);
    WiaTrace_ProcessTrace_Ex(v34, v33, (int)"AllocBufferFile", 1, v32);
  }
  else
  {
    FileW = CreateFileW(p_hBitmap->lpszFileName, 0xC0000000, 2u, 0, 3u, 0x100080u, 0);
    *a3 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v14 = (char *)WiaTrace_TraceLog("CreateFile on %S failed, GetLastError = 0x%X");
      WriteDbgTraceErrorWI("AllocBufferFile", v14);
      WiaTrcLib::Free((WiaTrcLib *)v14, v15);
      v16 = (void *)WiaTrace_Trace("CreateFile on %S failed, GetLastError = 0x%X", p_hBitmap->lpszFileName, LastError);
      WiaTrace_ProcessTrace_Ex(v18, v17, (int)"AllocBufferFile", 1, v16);
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( LastError >= 0 )
        LastError = -2147467259;
    }
    else if ( GetFileType(FileW) != 1 )
    {
      CloseHandle(*a3);
      *a3 = (void *)-1LL;
      v19 = (char *)WiaTrace_TraceLog("WIA will only transfer to files of type FILE_TYPE_DISK");
      WriteDbgTraceErrorWI("AllocBufferFile", v19);
      WiaTrcLib::Free((WiaTrcLib *)v19, v20);
      v21 = (void *)WiaTrace_Trace("WIA will only transfer to files of type FILE_TYPE_DISK");
      WiaTrace_ProcessTrace_Ex(v23, v22, (int)"AllocBufferFile", 1, v21);
      LastError = -2147024809;
    }
    v24 = SafeCoRevertToSelf();
    if ( v24 < 0 )
    {
      v25 = (char *)WiaTrace_TraceLog("SafeCoRevertToSelf failed (0x%X)");
      WriteDbgTraceErrorWI("AllocBufferFile", v25);
      WiaTrcLib::Free((WiaTrcLib *)v25, v26);
      v27 = (void *)WiaTrace_Trace("SafeCoRevertToSelf failed (0x%X)", v24);
      WiaTrace_ProcessTrace_Ex(v29, v28, (int)"AllocBufferFile", 1, v27);
      LastError = v24;
    }
  }
  if ( !(_DWORD)v5 )
  {
    if ( LastError >= 0 )
      goto LABEL_20;
LABEL_19:
    CoTaskMemFree(p_hBitmap->hMetaFilePict);
    p_hBitmap->hBitmap = 0;
    goto LABEL_20;
  }
  if ( LastError < 0 )
    goto LABEL_19;
  FileMappingW = CreateFileMappingW(*a3, 0, 4u, 0, v5, 0);
  v36 = FileMappingW;
  if ( FileMappingW )
    *a4 = MapViewOfFileEx(FileMappingW, 6u, 0, 0, v5, 0);
  CloseHandle(v36);
LABEL_20:
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v39);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18002d2ac  push    rbx
0x18002d2ae  push    rbp
0x18002d2af  push    rsi
0x18002d2b0  push    rdi
0x18002d2b1  push    r12
0x18002d2b3  push    r14
0x18002d2b5  push    r15
0x18002d2b7  sub     rsp, 90h
0x18002d2be  mov     rbx, rcx
0x18002d2c1  movsxd  r15, edx
0x18002d2c4  lea     rcx, aAllocbufferfil; "::AllocBufferFile"
0x18002d2cb  mov     r12, r9
0x18002d2ce  mov     r14, r8
0x18002d2d1  call    WiaTrace_Trace
0x18002d2d6  lea     rbp, aAllocbufferfil_0; "AllocBufferFile"
0x18002d2dd  mov     qword ptr [rsp+0C8h+dwFlagsAndAttributes], rax; struct tagWiaTraceData_Type *
0x18002d2e2  mov     r9, rbp; char *
0x18002d2e5  lea     rcx, [rsp+0C8h+var_88]; this
0x18002d2ea  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x18002d2ef  mov     qword ptr [r14], 0
0x18002d2f6  mov     qword ptr [r12], 0
0x18002d2fe  mov     qword ptr [rbx+10h], 0
0x18002d306  call    cs:__imp_CoImpersonateClient
0x18002d30c  lea     rsi, [rbx+8]
0x18002d310  mov     edi, eax
0x18002d312  test    eax, eax
0x18002d314  js      loc_18002D483
0x18002d31a  mov     rcx, [rsi]; lpFileName
0x18002d31d  xor     r9d, r9d; lpSecurityAttributes
0x18002d320  mov     [rsp+0C8h+hTemplateFile], 0; hTemplateFile
0x18002d329  mov     edx, 0C0000000h; dwDesiredAccess
0x18002d32e  mov     [rsp+0C8h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x18002d336  mov     [rsp+0C8h+dwCreationDisposition], 3; dwCreationDisposition
0x18002d33e  lea     r8d, [r9+2]; dwShareMode
0x18002d342  call    cs:__imp_CreateFileW
0x18002d348  mov     [r14], rax
0x18002d34b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002d34f  jnz     short loc_18002D3BF
0x18002d351  call    cs:__imp_GetLastError
0x18002d357  mov     rdx, [rsi]
0x18002d35a  lea     rcx, aCreatefileOnSF; "CreateFile on %S failed, GetLastError ="...
0x18002d361  mov     r8d, eax
0x18002d364  mov     edi, eax
0x18002d366  call    WiaTrace_TraceLog
0x18002d36b  mov     rdx, rax; char *
0x18002d36e  mov     rcx, rbp; char *
0x18002d371  mov     rbx, rax
0x18002d374  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002d379  mov     rcx, rbx; this
0x18002d37c  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002d381  mov     rdx, [rsi]
0x18002d384  lea     rcx, aCreatefileOnSF; "CreateFile on %S failed, GetLastError ="...
0x18002d38b  mov     r8d, edi
0x18002d38e  call    WiaTrace_Trace
0x18002d393  mov     r9d, 1; int
0x18002d399  mov     qword ptr [rsp+0C8h+dwCreationDisposition], rax; lpMem
0x18002d39e  mov     r8, rbp; int
0x18002d3a1  call    WiaTrace_ProcessTrace_Ex
0x18002d3a6  test    edi, edi
0x18002d3a8  jle     short loc_18002D3B3
0x18002d3aa  movzx   edi, di
0x18002d3ad  or      edi, 80070000h
0x18002d3b3  test    edi, edi
0x18002d3b5  mov     eax, 80004005h
0x18002d3ba  cmovns  edi, eax
0x18002d3bd  jmp     short loc_18002D423
0x18002d3bf  mov     rcx, rax; hFile
0x18002d3c2  call    cs:__imp_GetFileType
0x18002d3c8  cmp     eax, 1
0x18002d3cb  jz      short loc_18002D423
0x18002d3cd  mov     rcx, [r14]; hObject
0x18002d3d0  call    cs:__imp_CloseHandle
0x18002d3d6  lea     rcx, aWiaWillOnlyTra; "WIA will only transfer to files of type"...
0x18002d3dd  mov     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x18002d3e4  call    WiaTrace_TraceLog
0x18002d3e9  mov     rdx, rax; char *
0x18002d3ec  mov     rcx, rbp; char *
0x18002d3ef  mov     rbx, rax
0x18002d3f2  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002d3f7  mov     rcx, rbx; this
0x18002d3fa  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002d3ff  lea     rcx, aWiaWillOnlyTra; "WIA will only transfer to files of type"...
0x18002d406  call    WiaTrace_Trace
0x18002d40b  mov     r9d, 1; int
0x18002d411  mov     qword ptr [rsp+0C8h+dwCreationDisposition], rax; lpMem
0x18002d416  mov     r8, rbp; int
0x18002d419  call    WiaTrace_ProcessTrace_Ex
0x18002d41e  mov     edi, 80070057h
0x18002d423  call    ?SafeCoRevertToSelf@@YAJXZ; SafeCoRevertToSelf(void)
0x18002d428  mov     ebp, eax
0x18002d42a  test    eax, eax
0x18002d42c  jns     loc_18002D4C8
0x18002d432  mov     edx, eax
0x18002d434  lea     rcx, aSafecorevertto_1; "SafeCoRevertToSelf failed (0x%X)"
0x18002d43b  call    WiaTrace_TraceLog
0x18002d440  mov     rdx, rax; char *
0x18002d443  lea     rcx, aAllocbufferfil_0; "AllocBufferFile"
0x18002d44a  mov     rbx, rax
0x18002d44d  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002d452  mov     rcx, rbx; this
0x18002d455  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002d45a  mov     edx, ebp
0x18002d45c  lea     rcx, aSafecorevertto_1; "SafeCoRevertToSelf failed (0x%X)"
0x18002d463  call    WiaTrace_Trace
0x18002d468  mov     r9d, 1; int
0x18002d46e  mov     qword ptr [rsp+0C8h+dwCreationDisposition], rax; lpMem
0x18002d473  lea     r8, aAllocbufferfil_0; "AllocBufferFile"
0x18002d47a  call    WiaTrace_ProcessTrace_Ex
0x18002d47f  mov     edi, ebp
0x18002d481  jmp     short loc_18002D4C8
0x18002d483  mov     edx, edi
0x18002d485  lea     rcx, aCoimpersonatec; "CoImpersonateClient failed (0x%X)"
0x18002d48c  call    WiaTrace_TraceLog
0x18002d491  mov     rdx, rax; char *
0x18002d494  mov     rcx, rbp; char *
0x18002d497  mov     rbx, rax
0x18002d49a  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002d49f  mov     rcx, rbx; this
0x18002d4a2  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002d4a7  mov     edx, edi
0x18002d4a9  lea     rcx, aCoimpersonatec; "CoImpersonateClient failed (0x%X)"
0x18002d4b0  call    WiaTrace_Trace
0x18002d4b5  mov     r9d, 1; int
0x18002d4bb  mov     qword ptr [rsp+0C8h+dwCreationDisposition], rax; lpMem
0x18002d4c0  mov     r8, rbp; int
0x18002d4c3  call    WiaTrace_ProcessTrace_Ex
0x18002d4c8  test    r15d, r15d
0x18002d4cb  jz      short loc_18002D529
0x18002d4cd  test    edi, edi
0x18002d4cf  js      short loc_18002D52D
0x18002d4d1  mov     rcx, [r14]; hFile
0x18002d4d4  xor     r9d, r9d; dwMaximumSizeHigh
0x18002d4d7  mov     qword ptr [rsp+0C8h+dwFlagsAndAttributes], 0; lpName
0x18002d4e0  xor     edx, edx; lpFileMappingAttributes
0x18002d4e2  mov     [rsp+0C8h+dwCreationDisposition], r15d; dwMaximumSizeLow
0x18002d4e7  lea     r8d, [r9+4]; flProtect
0x18002d4eb  call    cs:__imp_CreateFileMappingW
0x18002d4f1  mov     rbx, rax
0x18002d4f4  test    rax, rax
0x18002d4f7  jz      short loc_18002D51E
0x18002d4f9  xor     r9d, r9d; dwFileOffsetLow
0x18002d4fc  mov     qword ptr [rsp+0C8h+dwFlagsAndAttributes], 0; lpBaseAddress
0x18002d505  xor     r8d, r8d; dwFileOffsetHigh
0x18002d508  mov     qword ptr [rsp+0C8h+dwCreationDisposition], r15; dwNumberOfBytesToMap
0x18002d50d  mov     rcx, rax; hFileMappingObject
0x18002d510  lea     edx, [r9+6]; dwDesiredAccess
0x18002d514  call    cs:__imp_MapViewOfFileEx
0x18002d51a  mov     [r12], rax
0x18002d51e  mov     rcx, rbx; hObject
0x18002d521  call    cs:__imp_CloseHandle
0x18002d527  jmp     short loc_18002D53D
0x18002d529  test    edi, edi
0x18002d52b  jns     short loc_18002D53D
0x18002d52d  mov     rcx, [rsi]; pv
0x18002d530  call    cs:__imp_CoTaskMemFree
0x18002d536  mov     qword ptr [rsi], 0
0x18002d53d  lea     rcx, [rsp+0C8h+var_88]; this
0x18002d542  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x18002d547  mov     eax, edi
0x18002d549  add     rsp, 90h
0x18002d550  pop     r15
0x18002d552  pop     r14
0x18002d554  pop     r12
0x18002d556  pop     rdi
0x18002d557  pop     rsi
0x18002d558  pop     rbp
0x18002d559  pop     rbx
0x18002d55a  retn
```
