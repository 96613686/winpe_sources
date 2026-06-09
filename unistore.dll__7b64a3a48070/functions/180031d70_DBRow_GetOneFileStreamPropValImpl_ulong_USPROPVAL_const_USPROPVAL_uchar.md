# DBRow::GetOneFileStreamPropValImpl(ulong,_USPROPVAL const &,_USPROPVAL *,uchar * *)

- ea: `0x180031d70`
- end: `0x18003216a`
- name: `?GetOneFileStreamPropValImpl@DBRow@@IEAAJKAEBU_USPROPVAL@@PEAU2@PEAPEAE@Z`
- size: `1018`
- prototype: `int(DBRow *__hidden this, unsigned int, const struct _USPROPVAL *, struct _USPROPVAL *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18003173c`

## callees

- `0x180004440`
- `0x1800068f0`
- `0x1800086bc`
- `0x180015790`
- `0x180028ef4`
- `0x180029be0`
- `0x180031d70`
- `0x1800325d0`
- `0x1800327b0`
- `0x180034540`
- `0x18006f180`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003205c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800320c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800320f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003205c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800320c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800320f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031f76`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031faa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032054`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031f76`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031faa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032054`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031ef0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031ef0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180031ea3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180031ea3`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180031ec5`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180031ec5`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180031f1d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180031f1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031f41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031f9c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031f41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031f9c`

## string_xrefs

- `0x180031db0`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180031f89`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180031fe8`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18003202f`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18003207f`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x1800320de`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180032138`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`

## pseudocode

```c
__int64 __fastcall DBRow::GetOneFileStreamPropValImpl(
        DBRow *this,
        unsigned int a2,
        const struct _USPROPVAL *a3,
        struct _USPROPVAL *a4,
        WCHAR *lpFileName)
{
  unsigned int v9; // eax
  __int64 v10; // rcx
  WCHAR *v11; // r15
  __int64 v13; // rax
  int v14; // eax
  unsigned int v15; // ebx
  int v16; // eax
  unsigned int v17; // edi
  unsigned int PrimaryId; // ebx
  unsigned int v19; // eax
  int StreamFilePath; // eax
  unsigned __int8 **v21; // rbx
  HANDLE FileW; // rax
  void *v23; // rsi
  DWORD FileSize; // eax
  HLOCAL v25; // rax
  HLOCAL v26; // rdi
  __int64 v27; // r9
  void (*v28)(void); // rax
  signed int LastError; // eax
  signed int v30; // eax
  unsigned int v31; // ebx
  signed int v32; // eax
  HLOCAL v33; // [rsp+40h] [rbp-28h] BYREF
  struct IDBSession *v34[4]; // [rsp+48h] [rbp-20h] BYREF
  struct IDBVolume *v35; // [rsp+B0h] [rbp+48h] BYREF
  DWORD NumberOfBytesRead; // [rsp+B8h] [rbp+50h] BYREF
  __int64 nNumberOfBytesToRead; // [rsp+C0h] [rbp+58h] BYREF
  __int64 v38; // [rsp+C8h] [rbp+60h] BYREF

  v9 = (*(__int64 (__fastcall **)(DBRow *))(*(_QWORD *)this + 32LL))(this);
  if ( !(unsigned int)IsFileStreamSupportedInTable(v9) )
    Log_AssertionEvent(
      v10,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      8297);
  v11 = lpFileName;
  *(_DWORD *)a4 = a2;
  *((_WORD *)a4 + 3) = 256;
  *(_QWORD *)v11 = 0;
  if ( (*((_WORD *)a3 + 3) & 0x100) != 0 || !*((_DWORD *)a3 + 2) )
    return 0;
  v13 = *(_QWORD *)this;
  v35 = 0;
  v14 = (*(__int64 (__fastcall **)(DBRow *, struct IDBVolume **))(v13 + 24))(this, &v35);
  v15 = v14;
  if ( v14 < 0 )
  {
    Log_UnistoreHREvent_0(
      (unsigned int)v14,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      8309);
    if ( !v35 )
      return v15;
    v28 = *(void (**)(void))(*(_QWORD *)v35 + 16LL);
    goto LABEL_31;
  }
  v34[0] = 0;
  v34[1] = 0;
  v16 = auto_DBSession::Open((auto_DBSession *)v34, v35);
  v17 = v16;
  if ( v16 < 0 )
  {
    Log_UnistoreHREvent_0(
      (unsigned int)v16,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      8312);
    goto LABEL_39;
  }
  lpFileName = 0;
  PrimaryId = UnifiedStoreCursorLocation::GetPrimaryId((DBRow *)((char *)this + 32));
  v19 = (*(__int64 (__fastcall **)(DBRow *))(*(_QWORD *)this + 32LL))(this);
  StreamFilePath = DBManager::GetStreamFilePath(v34[0], v19, PrimaryId, a2, 0x80000000, &lpFileName);
  v15 = StreamFilePath;
  if ( StreamFilePath >= 0 )
  {
    v21 = (unsigned __int8 **)lpFileName;
    v38 = -1;
    FileW = CreateFileW(lpFileName, 0x80000000, 3u, 0, 3u, 0, 0);
    v23 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v17 = LastError;
      if ( LastError == 5 )
      {
        *((_WORD *)a4 + 3) = 4352;
        goto LABEL_16;
      }
      if ( LastError > 0 )
        v17 = (unsigned __int16)LastError | 0x80070000;
      tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),-1>::_Delete(&v38);
      auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>(&lpFileName);
      goto LABEL_39;
    }
    v38 = (__int64)FileW;
    nNumberOfBytesToRead = 0;
    FileSize = GetFileSize(FileW, (LPDWORD)&nNumberOfBytesToRead + 1);
    LODWORD(nNumberOfBytesToRead) = FileSize;
    if ( FileSize != -1 )
    {
      if ( HIDWORD(nNumberOfBytesToRead) )
      {
        v27 = 8340;
        v17 = -2147467259;
      }
      else
      {
        if ( !FileSize )
        {
          tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),-1>::_Delete(&v38);
          auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>(&lpFileName);
          v17 = 0;
          goto LABEL_39;
        }
        v25 = LocalAlloc(0x40u, FileSize);
        v33 = v25;
        v26 = v25;
        if ( v25 )
        {
          NumberOfBytesRead = 0;
          if ( ReadFile(v23, v25, nNumberOfBytesToRead, &NumberOfBytesRead, 0) )
          {
            *((_DWORD *)a4 + 2) = NumberOfBytesRead;
            *((_WORD *)a4 + 3) = 0;
            *((_QWORD *)a4 + 2) = v26;
            *(_QWORD *)v11 = v26;
            CloseHandle(v23);
LABEL_16:
            if ( v21 )
              LocalFree(v21);
            auto_DBSession::~auto_DBSession((auto_DBSession *)v34);
            if ( v35 )
              (*(void (__fastcall **)(struct IDBVolume *))(*(_QWORD *)v35 + 16LL))(v35);
            return 0;
          }
          v32 = GetLastError();
          v31 = v32;
          if ( v32 > 0 )
            v31 = (unsigned __int16)v32 | 0x80070000;
          Log_UnistoreHREvent_0(
            v31,
            0,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
            8351);
          auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>(&v33);
          goto LABEL_38;
        }
        v27 = 8348;
        v17 = -2147024882;
      }
      Log_UnistoreHREvent_0(
        v17,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
        v27);
      CloseHandle(v23);
      if ( v21 )
        LocalFree(v21);
      auto_DBSession::~auto_DBSession((auto_DBSession *)v34);
      if ( v35 )
        (*(void (__fastcall **)(struct IDBVolume *))(*(_QWORD *)v35 + 16LL))(v35);
      return v17;
    }
    v30 = GetLastError();
    v31 = v30;
    if ( v30 > 0 )
      v31 = (unsigned __int16)v30 | 0x80070000;
    Log_UnistoreHREvent_0(
      v31,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      8339);
LABEL_38:
    tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),-1>::_Delete(&v38);
    auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>(&lpFileName);
    v17 = v31;
LABEL_39:
    auto_DBSession::~auto_DBSession((auto_DBSession *)v34);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v35);
    return v17;
  }
  Log_UnistoreHREvent_0(
    (unsigned int)StreamFilePath,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
    8321);
  if ( lpFileName )
    LocalFree(lpFileName);
  auto_DBSession::~auto_DBSession((auto_DBSession *)v34);
  if ( v35 )
  {
    v28 = *(void (**)(void))(*(_QWORD *)v35 + 16LL);
LABEL_31:
    v28();
  }
  return v15;
}

```

## disassembly

```asm
0x180031d70  push    rbp
0x180031d72  push    rbx
0x180031d73  push    rsi
0x180031d74  push    rdi
0x180031d75  push    r12
0x180031d77  push    r13
0x180031d79  push    r14
0x180031d7b  push    r15
0x180031d7d  mov     rbp, rsp
0x180031d80  sub     rsp, 68h
0x180031d84  mov     rax, [rcx]
0x180031d87  mov     r14, r9
0x180031d8a  mov     rbx, r8
0x180031d8d  mov     r12d, edx
0x180031d90  mov     rsi, rcx
0x180031d93  mov     rax, [rax+20h]
0x180031d97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031d9c  mov     ecx, eax; unsigned int
0x180031d9e  call    ?IsFileStreamSupportedInTable@@YAHK@Z; IsFileStreamSupportedInTable(ulong)
0x180031da3  xor     r13d, r13d
0x180031da6  test    eax, eax
0x180031da8  jnz     short loc_180031DBC
0x180031daa  mov     r8d, 2069h
0x180031db0  lea     rdx, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180031db7  call    Log_AssertionEvent
0x180031dbc  mov     r15, [rbp+lpFileName]
0x180031dc0  mov     eax, 100h
0x180031dc5  mov     [r14], r12d
0x180031dc8  mov     [r14+6], ax
0x180031dcd  mov     [r15], r13
0x180031dd0  test    [rbx+6], ax
0x180031dd4  jz      short loc_180031DE9
0x180031dd6  xor     eax, eax
0x180031dd8  add     rsp, 68h
0x180031ddc  pop     r15
0x180031dde  pop     r14
0x180031de0  pop     r13
0x180031de2  pop     r12
0x180031de4  pop     rdi
0x180031de5  pop     rsi
0x180031de6  pop     rbx
0x180031de7  pop     rbp
0x180031de8  retn
0x180031de9  cmp     [rbx+8], r13d
0x180031ded  jz      short loc_180031DD6
0x180031def  mov     rax, [rsi]
0x180031df2  lea     rdx, [rbp+arg_0]
0x180031df6  mov     rcx, rsi
0x180031df9  mov     [rbp+arg_0], r13
0x180031dfd  mov     rax, [rax+18h]
0x180031e01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031e06  mov     ebx, eax
0x180031e08  test    eax, eax
0x180031e0a  js      loc_180032029
0x180031e10  mov     rdx, [rbp+arg_0]; struct IDBVolume *
0x180031e14  lea     rcx, [rbp+var_20]; this
0x180031e18  mov     [rbp+var_20], r13
0x180031e1c  mov     [rbp+var_18], r13
0x180031e20  call    ?Open@auto_DBSession@@QEAAJPEAVIDBVolume@@@Z; auto_DBSession::Open(IDBVolume *)
0x180031e25  mov     edi, eax
0x180031e27  test    eax, eax
0x180031e29  js      loc_180032132
0x180031e2f  lea     rcx, [rsi+20h]; this
0x180031e33  mov     [rbp+lpFileName], r13
0x180031e37  call    ?GetPrimaryId@UnifiedStoreCursorLocation@@QEBAKXZ; UnifiedStoreCursorLocation::GetPrimaryId(void)
0x180031e3c  mov     rcx, [rsi]
0x180031e3f  mov     ebx, eax
0x180031e41  mov     rax, [rcx+20h]
0x180031e45  mov     rcx, rsi
0x180031e48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031e4d  lea     rcx, [rbp+lpFileName]
0x180031e51  mov     edi, 80000000h
0x180031e56  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], rcx; unsigned __int16 **
0x180031e5b  mov     r9d, r12d; unsigned int
0x180031e5e  mov     rcx, [rbp+var_20]; struct IDBSession *
0x180031e62  mov     r8d, ebx; unsigned int
0x180031e65  mov     edx, eax; unsigned int
0x180031e67  mov     [rsp+68h+dwCreationDisposition], edi; unsigned int
0x180031e6b  call    ?GetStreamFilePath@DBManager@@SAJPEAVIDBSession@@KKKKPEAPEAG@Z; DBManager::GetStreamFilePath(IDBSession *,ulong,ulong,ulong,ulong,ushort * *)
0x180031e70  mov     ebx, eax
0x180031e72  test    eax, eax
0x180031e74  js      loc_180031FE2
0x180031e7a  mov     rbx, [rbp+lpFileName]
0x180031e7e  mov     r8d, 3; dwShareMode
0x180031e84  mov     [rsp+68h+hTemplateFile], r13; hTemplateFile
0x180031e89  mov     rcx, rbx; lpFileName
0x180031e8c  mov     [rsp+68h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x180031e91  xor     r9d, r9d; lpSecurityAttributes
0x180031e94  mov     edx, edi; dwDesiredAccess
0x180031e96  mov     [rbp+arg_18], 0FFFFFFFFFFFFFFFFh
0x180031e9e  mov     [rsp+68h+dwCreationDisposition], r8d; dwCreationDisposition
0x180031ea3  call    cs:__imp_CreateFileW
0x180031ea9  mov     rsi, rax
0x180031eac  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180031eb0  jz      loc_18003205C
0x180031eb6  lea     rdx, [rbp+FileSizeHigh]; lpFileSizeHigh
0x180031eba  mov     [rbp+arg_18], rax
0x180031ebe  mov     rcx, rax; hFile
0x180031ec1  mov     [rbp+58h], r13
0x180031ec5  call    cs:__imp_GetFileSize
0x180031ecb  mov     [rbp+nNumberOfBytesToRead], eax
0x180031ece  cmp     eax, 0FFFFFFFFh
0x180031ed1  jz      loc_1800320C3
0x180031ed7  cmp     [rbp+FileSizeHigh], r13d
0x180031edb  jnz     loc_180031F7E
0x180031ee1  test    eax, eax
0x180031ee3  jz      loc_180032150
0x180031ee9  mov     edx, eax; uBytes
0x180031eeb  mov     ecx, 40h ; '@'; uFlags
0x180031ef0  call    cs:__imp_LocalAlloc
0x180031ef6  mov     [rbp+var_28], rax
0x180031efa  mov     rdi, rax
0x180031efd  test    rax, rax
0x180031f00  jz      loc_180031FD5
0x180031f06  mov     r8d, [rbp+nNumberOfBytesToRead]; nNumberOfBytesToRead
0x180031f0a  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180031f0e  mov     rdx, rax; lpBuffer
0x180031f11  mov     [rbp+NumberOfBytesRead], r13d
0x180031f15  mov     rcx, rsi; hFile
0x180031f18  mov     qword ptr [rsp+68h+dwCreationDisposition], r13; lpOverlapped
0x180031f1d  call    cs:__imp_ReadFile
0x180031f23  test    eax, eax
0x180031f25  jz      loc_1800320F0
0x180031f2b  mov     eax, [rbp+NumberOfBytesRead]
0x180031f2e  mov     rcx, rsi; hObject
0x180031f31  mov     [r14+8], eax
0x180031f35  mov     [r14+6], r13w
0x180031f3a  mov     [r14+10h], rdi
0x180031f3e  mov     [r15], rdi
0x180031f41  call    cs:__imp_CloseHandle
0x180031f47  test    rbx, rbx
0x180031f4a  jnz     short loc_180031F73
0x180031f4c  lea     rcx, [rbp+var_20]; this
0x180031f50  call    ??1auto_DBSession@@QEAA@XZ; auto_DBSession::~auto_DBSession(void)
0x180031f55  mov     rcx, [rbp+arg_0]
0x180031f59  test    rcx, rcx
0x180031f5c  jz      loc_180031DD6
0x180031f62  mov     rax, [rcx]
0x180031f65  mov     rax, [rax+10h]
0x180031f69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f6e  jmp     loc_180031DD6
0x180031f73  mov     rcx, rbx; hMem
0x180031f76  call    cs:__imp_LocalFree
0x180031f7c  jmp     short loc_180031F4C
0x180031f7e  mov     r9d, 2094h
0x180031f84  mov     edi, 80004005h
0x180031f89  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180031f90  xor     edx, edx
0x180031f92  mov     ecx, edi
0x180031f94  call    Log_UnistoreHREvent_0
0x180031f99  mov     rcx, rsi; hObject
0x180031f9c  call    cs:__imp_CloseHandle
0x180031fa2  test    rbx, rbx
0x180031fa5  jz      short loc_180031FB0
0x180031fa7  mov     rcx, rbx; hMem
0x180031faa  call    cs:__imp_LocalFree
0x180031fb0  lea     rcx, [rbp+var_20]; this
0x180031fb4  call    ??1auto_DBSession@@QEAA@XZ; auto_DBSession::~auto_DBSession(void)
0x180031fb9  mov     rcx, [rbp+arg_0]
0x180031fbd  test    rcx, rcx
0x180031fc0  jz      short loc_180031FCE
0x180031fc2  mov     rdx, [rcx]
0x180031fc5  mov     rax, [rdx+10h]
0x180031fc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031fce  mov     eax, edi
0x180031fd0  jmp     loc_180031DD8
0x180031fd5  mov     r9d, 209Ch
0x180031fdb  mov     edi, 8007000Eh
0x180031fe0  jmp     short loc_180031F89
0x180031fe2  mov     r9d, 2081h
0x180031fe8  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180031fef  mov     edx, 1
0x180031ff4  mov     ecx, ebx
0x180031ff6  call    Log_UnistoreHREvent_0
0x180031ffb  mov     rcx, [rbp+lpFileName]; hMem
0x180031fff  test    rcx, rcx
0x180032002  jnz     short loc_180032054
0x180032004  lea     rcx, [rbp+var_20]; this
0x180032008  call    ??1auto_DBSession@@QEAA@XZ; auto_DBSession::~auto_DBSession(void)
0x18003200d  mov     rcx, [rbp+arg_0]
0x180032011  test    rcx, rcx
0x180032014  jz      short loc_180032022
0x180032016  mov     rax, [rcx]
0x180032019  mov     rax, [rax+10h]
0x18003201d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032022  mov     eax, ebx
0x180032024  jmp     loc_180031DD8
0x180032029  mov     r9d, 2075h
0x18003202f  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180032036  mov     edx, 1
0x18003203b  mov     ecx, ebx
0x18003203d  call    Log_UnistoreHREvent_0
0x180032042  mov     rcx, [rbp+arg_0]
0x180032046  test    rcx, rcx
0x180032049  jz      short loc_180032022
0x18003204b  mov     rdx, [rcx]
0x18003204e  mov     rax, [rdx+10h]
0x180032052  jmp     short loc_18003201D
0x180032054  call    cs:__imp_LocalFree
0x18003205a  jmp     short loc_180032004
0x18003205c  call    cs:__imp_GetLastError
0x180032062  mov     edi, eax
0x180032064  cmp     eax, 5
0x180032067  jnz     loc_18003210E
0x18003206d  mov     word ptr [r14+6], 1100h
0x180032074  jmp     loc_180031F47
0x180032079  mov     r9d, 209Fh
0x18003207f  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180032086  xor     edx, edx
0x180032088  mov     ecx, ebx
0x18003208a  call    Log_UnistoreHREvent_0
0x18003208f  lea     rcx, [rbp+var_28]
0x180032093  call    ??1?$auto_local_array_ptr@E@@QEAA@XZ; auto_local_array_ptr<uchar>::~auto_local_array_ptr<uchar>(void)
0x180032098  lea     rcx, [rbp+arg_18]
0x18003209c  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0?0@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),-1>::_Delete(void)
0x1800320a1  lea     rcx, [rbp+lpFileName]
0x1800320a5  call    ??1?$auto_local_array_ptr@E@@QEAA@XZ; auto_local_array_ptr<uchar>::~auto_local_array_ptr<uchar>(void)
0x1800320aa  mov     edi, ebx
0x1800320ac  lea     rcx, [rbp+var_20]; this
0x1800320b0  call    ??1auto_DBSession@@QEAA@XZ; auto_DBSession::~auto_DBSession(void)
0x1800320b5  lea     rcx, [rbp+arg_0]; void *
0x1800320b9  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x1800320be  jmp     loc_180031FCE
0x1800320c3  call    cs:__imp_GetLastError
0x1800320c9  mov     ebx, eax
0x1800320cb  test    eax, eax
0x1800320cd  jle     short loc_1800320D8
0x1800320cf  movzx   ebx, ax
0x1800320d2  or      ebx, 80070000h
0x1800320d8  mov     r9d, 2093h
0x1800320de  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800320e5  xor     edx, edx
0x1800320e7  mov     ecx, ebx
0x1800320e9  call    Log_UnistoreHREvent_0
0x1800320ee  jmp     short loc_180032098
0x1800320f0  call    cs:__imp_GetLastError
0x1800320f6  mov     ebx, eax
0x1800320f8  test    eax, eax
0x1800320fa  jle     loc_180032079
0x180032100  movzx   ebx, ax
0x180032103  or      ebx, 80070000h
0x180032109  jmp     loc_180032079
0x18003210e  test    eax, eax
0x180032110  jle     short loc_18003211B
0x180032112  movzx   edi, ax
0x180032115  or      edi, 80070000h
0x18003211b  lea     rcx, [rbp+arg_18]
0x18003211f  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0?0@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),-1>::_Delete(void)
0x180032124  lea     rcx, [rbp+lpFileName]
0x180032128  call    ??1?$auto_local_array_ptr@E@@QEAA@XZ; auto_local_array_ptr<uchar>::~auto_local_array_ptr<uchar>(void)
0x18003212d  jmp     loc_1800320AC
0x180032132  mov     r9d, 2078h
0x180032138  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18003213f  mov     edx, 1
0x180032144  mov     ecx, eax
0x180032146  call    Log_UnistoreHREvent_0
0x18003214b  jmp     loc_1800320AC
0x180032150  lea     rcx, [rbp+arg_18]
0x180032154  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0?0@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),-1>::_Delete(void)
0x180032159  lea     rcx, [rbp+lpFileName]
0x18003215d  call    ??1?$auto_local_array_ptr@E@@QEAA@XZ; auto_local_array_ptr<uchar>::~auto_local_array_ptr<uchar>(void)
0x180032162  mov     edi, r13d
0x180032165  jmp     loc_1800320AC
```
