# FileStreamProp::CopyOnWrite(void)

- ea: `0x18004eb78`
- end: `0x18004ee84`
- name: `?CopyOnWrite@FileStreamProp@@AEAAJXZ`
- size: `780`
- prototype: `__int64 __fastcall(FileStreamProp *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18004e940`
- `0x18004ea50`

## callees

- `0x180004440`
- `0x1800068f0`
- `0x180034128`
- `0x180034540`
- `0x1800396c8`
- `0x180039898`
- `0x18004eb78`
- `0x180073c64`
- `0x1800b0274`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ec23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004edc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ee14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ec23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004edc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ee14`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004ec13`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004ee09`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004ec13`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004ee09`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18004ecf1`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18004ecf1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ee35`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ee35`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004edb8`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004edb8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004ed87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004ed94`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004ed87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004ed94`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18004ebd6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18004ebd6`
- `UserDataTypeHelperUtil!CreateWrapFileStm` at `0x18004ed0e`
- `UserDataTypeHelperUtil!CreateWrapFileStm` at `0x18004ed0e`

## string_xrefs

- `0x18004ec3e`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\streamprop.cpp`
- `0x18004ec92`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\streamprop.cpp`
- `0x18004ecd4`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\streamprop.cpp`
- `0x18004ed20`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\streamprop.cpp`
- `0x18004eddd`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\streamprop.cpp`

## pseudocode

```c
__int64 __fastcall FileStreamProp::CopyOnWrite(FileStreamProp *this)
{
  void *v3; // rax
  __int64 v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rcx
  void *v7; // rcx
  signed int LastError; // eax
  unsigned int v9; // ebx
  void **v10; // rax
  struct _SECURITY_ATTRIBUTES *v11; // r9
  int FileAndPath; // eax
  const WCHAR *v13; // r15
  int v14; // eax
  int v15; // eax
  __int64 v16; // r9
  __int64 (__fastcall *v17)(FileStreamProp *, __int64, __int64, _QWORD, __int64 *); // rax
  HANDLE *v18; // rsi
  HANDLE CurrentProcess; // rax
  HANDLE v20; // rdi
  void *v21; // rbx
  HANDLE v22; // rax
  signed int v23; // eax
  __int64 v24; // r9
  signed int v25; // eax
  HANDLE v26; // rax
  unsigned int bInheritHandle; // [rsp+28h] [rbp-40h]
  void *dwOptions; // [rsp+30h] [rbp-38h]
  __int64 v29; // [rsp+58h] [rbp-10h] BYREF
  HANDLE hFile; // [rsp+B0h] [rbp+48h] BYREF
  __int64 v31; // [rsp+B8h] [rbp+50h] BYREF
  HANDLE hSourceHandle; // [rsp+C0h] [rbp+58h] BYREF
  __int64 lDistanceToMove; // [rsp+C8h] [rbp+60h] BYREF

  if ( !*((_DWORD *)this + 13) )
    return 0;
  if ( (Microsoft_Windows_UserDataAccess_UnifiedStoreEnableBits & 0x20) != 0 )
  {
    v3 = _t_address();
    bInheritHandle = -1;
    EtwTraceMessage(&ETWMESSAGE, v3, *(_QWORD *)(v4 + 40), -2, 0);
  }
  if ( PathFileExistsW(*((LPCWSTR *)this + 5)) )
    Log_AssertionEvent_17(v6, v5, 800);
  if ( *((_DWORD *)this + 12) )
    Log_AssertionEvent_17(v6, v5, 803);
  v7 = (void *)*((_QWORD *)this + 1);
  lDistanceToMove = 0;
  LODWORD(lDistanceToMove) = SetFilePointer(v7, 0, (PLONG)&lDistanceToMove + 1, 1u);
  if ( (_DWORD)lDistanceToMove == -1 )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    Log_UnistoreHREvent_0(
      v9,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\streamprop.cpp",
      810);
    return v9;
  }
  hSourceHandle = (HANDLE)-1LL;
  v10 = (void **)tlx::replace<void *,int (*)(void *),&int CloseHandle(void *),-1>(&hSourceHandle);
  FileAndPath = StreamHelper::CreateFileAndPath(
                  *((const unsigned __int16 **)this + 5),
                  0xC0000000,
                  7u,
                  v11,
                  2u,
                  bInheritHandle,
                  dwOptions,
                  1,
                  v10);
  v9 = FileAndPath;
  if ( FileAndPath >= 0 )
  {
    v13 = (const WCHAR *)*((_QWORD *)this + 5);
    v14 = (*(__int64 (__fastcall **)(FileStreamProp *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)this + 40LL))(this, 0, 0, 0);
    v9 = v14;
    if ( v14 < 0 )
    {
      Log_UnistoreHREvent_0(
        (unsigned int)v14,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\streamprop.cpp",
        832);
      goto LABEL_17;
    }
    v31 = 0;
    v15 = CreateWrapFileStm(hSourceHandle, &v31, 1, 1);
    v9 = v15;
    if ( v15 >= 0 )
    {
      v17 = *(__int64 (__fastcall **)(FileStreamProp *, __int64, __int64, _QWORD, __int64 *))(*(_QWORD *)this + 56LL);
      v29 = 0;
      v15 = v17(this, v31, -1, 0, &v29);
      v9 = v15;
      if ( v15 >= 0 )
      {
        hFile = (HANDLE)-1LL;
        v18 = (HANDLE *)tlx::replace<void *,int (*)(void *),&int CloseHandle(void *),-1>(&hFile);
        CurrentProcess = GetCurrentProcess();
        v20 = hSourceHandle;
        v21 = CurrentProcess;
        v22 = GetCurrentProcess();
        if ( DuplicateHandle(v22, v20, v21, v18, 0, 0, 2u) )
        {
          if ( SetFilePointer(hFile, lDistanceToMove, (PLONG)&lDistanceToMove + 1, 0) != -1 )
          {
            CloseHandle(*((HANDLE *)this + 1));
            v26 = hFile;
            hFile = (HANDLE)-1LL;
            hSourceHandle = (HANDLE)-1LL;
            *((_QWORD *)this + 1) = v26;
            *((_QWORD *)this + 6) = 1;
            tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),-1>::_Delete(&hFile);
            ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v31);
            v9 = 0;
            goto LABEL_35;
          }
          v25 = GetLastError();
          v9 = v25;
          if ( v25 > 0 )
            v9 = (unsigned __int16)v25 | 0x80070000;
          v24 = 860;
        }
        else
        {
          v23 = GetLastError();
          v9 = v23;
          if ( v23 > 0 )
            v9 = (unsigned __int16)v23 | 0x80070000;
          v24 = 857;
        }
        Log_UnistoreHREvent_0(
          v9,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\streamprop.cpp",
          v24);
        tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),-1>::_Delete(&hFile);
        goto LABEL_22;
      }
      v16 = 844;
    }
    else
    {
      v16 = 838;
    }
    Log_UnistoreHREvent_0(
      (unsigned int)v15,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\streamprop.cpp",
      v16);
LABEL_22:
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v31);
LABEL_17:
    if ( v13 )
      DeleteFileW(v13);
    goto LABEL_35;
  }
  Log_UnistoreHREvent_0(
    (unsigned int)FileAndPath,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\streamprop.cpp",
    824);
LABEL_35:
  tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),-1>::_Delete(&hSourceHandle);
  return v9;
}

```

## disassembly

```asm
0x18004eb78  push    rbp
0x18004eb7a  push    rbx
0x18004eb7b  push    rsi
0x18004eb7c  push    rdi
0x18004eb7d  push    r12
0x18004eb7f  push    r13
0x18004eb81  push    r14
0x18004eb83  push    r15
0x18004eb85  mov     rbp, rsp
0x18004eb88  sub     rsp, 68h
0x18004eb8c  xor     r12d, r12d
0x18004eb8f  mov     r14, rcx
0x18004eb92  cmp     [rcx+34h], r12d
0x18004eb96  jnz     short loc_18004EB9F
0x18004eb98  xor     eax, eax
0x18004eb9a  jmp     loc_18004EE73
0x18004eb9f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004eba3  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UnifiedStoreEnableBits, 20h
0x18004ebaa  jz      short loc_18004EBD2
0x18004ebac  call    ?_t_address@@YAPEAXXZ; _t_address(void)
0x18004ebb1  mov     r8, [rcx+28h]
0x18004ebb5  lea     r9, [rdi-1]
0x18004ebb9  mov     rdx, rax; void *
0x18004ebbc  mov     qword ptr [rsp+68h+bInheritHandle], rdi; unsigned int
0x18004ebc1  lea     rcx, _ETWMESSAGE; EventDescriptor
0x18004ebc8  mov     qword ptr [rsp+68h+dwDesiredAccess], r12
0x18004ebcd  call    ?EtwTraceMessage@@YAXPEBU_EVENT_DESCRIPTOR@@PEAXZZ; EtwTraceMessage(_EVENT_DESCRIPTOR const *,void *,...)
0x18004ebd2  mov     rcx, [r14+28h]; pszPath
0x18004ebd6  call    cs:__imp_PathFileExistsW
0x18004ebdc  test    eax, eax
0x18004ebde  jz      short loc_18004EBEB
0x18004ebe0  mov     r8d, 320h
0x18004ebe6  call    Log_AssertionEvent_17
0x18004ebeb  cmp     [r14+30h], r12d
0x18004ebef  jz      short loc_18004EBFC
0x18004ebf1  mov     r8d, 323h
0x18004ebf7  call    Log_AssertionEvent_17
0x18004ebfc  mov     rcx, [r14+8]; hFile
0x18004ec00  lea     r8, [rbp+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x18004ec04  mov     r13d, 1
0x18004ec0a  mov     [rbp+60h], r12
0x18004ec0e  mov     r9d, r13d; dwMoveMethod
0x18004ec11  xor     edx, edx; lDistanceToMove
0x18004ec13  call    cs:__imp_SetFilePointer
0x18004ec19  or      esi, 0FFFFFFFFh
0x18004ec1c  mov     [rbp+lDistanceToMove], eax
0x18004ec1f  cmp     eax, esi
0x18004ec21  jnz     short loc_18004EC53
0x18004ec23  call    cs:__imp_GetLastError
0x18004ec29  mov     ebx, eax
0x18004ec2b  test    eax, eax
0x18004ec2d  jle     short loc_18004EC38
0x18004ec2f  movzx   ebx, ax
0x18004ec32  or      ebx, 80070000h
0x18004ec38  mov     r9d, 32Ah
0x18004ec3e  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18004ec45  xor     edx, edx
0x18004ec47  mov     ecx, ebx
0x18004ec49  call    Log_UnistoreHREvent_0
0x18004ec4e  jmp     loc_18004EE71
0x18004ec53  lea     rcx, [rbp+hSourceHandle]
0x18004ec57  mov     [rbp+hSourceHandle], rdi
0x18004ec5b  call    ??$replace@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0?0@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0?0@0@@Z; tlx::replace<void *,int (*)(void *),&CloseHandle(void *),-1>(tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),-1> &)
0x18004ec60  mov     rcx, [r14+28h]; unsigned __int16 *
0x18004ec64  mov     edx, 0C0000000h; dwDesiredAccess
0x18004ec69  mov     [rsp+68h+var_28], rax; void **
0x18004ec6e  mov     r8d, 7; dwShareMode
0x18004ec74  mov     [rsp+68h+var_30], r13d; int
0x18004ec79  mov     [rsp+68h+dwDesiredAccess], 2; DWORD
0x18004ec81  call    ?CreateFileAndPath@StreamHelper@@SAJPEBGKKPEAU_SECURITY_ATTRIBUTES@@KKPEAXHPEAPEAX@Z; StreamHelper::CreateFileAndPath(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *,int,void * *)
0x18004ec86  mov     ebx, eax
0x18004ec88  test    eax, eax
0x18004ec8a  jns     short loc_18004ECA8
0x18004ec8c  mov     r9d, 338h
0x18004ec92  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18004ec99  mov     edx, r13d
0x18004ec9c  mov     ecx, eax
0x18004ec9e  call    Log_UnistoreHREvent_0
0x18004eca3  jmp     loc_18004EE68
0x18004eca8  mov     rax, [r14]
0x18004ecab  xor     r9d, r9d
0x18004ecae  mov     r15, [r14+28h]
0x18004ecb2  xor     r8d, r8d
0x18004ecb5  mov     rdx, r12
0x18004ecb8  mov     [rbp+var_18], r12
0x18004ecbc  mov     rcx, r14
0x18004ecbf  mov     rax, [rax+28h]
0x18004ecc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ecc8  mov     ebx, eax
0x18004ecca  test    eax, eax
0x18004eccc  jns     short loc_18004ECFC
0x18004ecce  mov     r9d, 340h
0x18004ecd4  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18004ecdb  mov     edx, r13d
0x18004ecde  mov     ecx, eax
0x18004ece0  call    Log_UnistoreHREvent_0
0x18004ece5  test    r15, r15
0x18004ece8  jz      loc_18004EE68
0x18004ecee  mov     rcx, r15; lpFileName
0x18004ecf1  call    cs:__imp_DeleteFileW
0x18004ecf7  jmp     loc_18004EE68
0x18004ecfc  mov     rcx, [rbp+hSourceHandle]
0x18004ed00  lea     rdx, [rbp+arg_8]
0x18004ed04  mov     r9d, r13d
0x18004ed07  mov     [rbp+arg_8], r12
0x18004ed0b  mov     r8d, r13d
0x18004ed0e  call    cs:__imp_CreateWrapFileStm
0x18004ed14  mov     ebx, eax
0x18004ed16  test    eax, eax
0x18004ed18  jns     short loc_18004ED3C
0x18004ed1a  mov     r9d, 346h
0x18004ed20  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18004ed27  mov     edx, r13d
0x18004ed2a  mov     ecx, eax
0x18004ed2c  call    Log_UnistoreHREvent_0
0x18004ed31  lea     rcx, [rbp+arg_8]; void *
0x18004ed35  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18004ed3a  jmp     short loc_18004ECE5
0x18004ed3c  mov     rax, [r14]
0x18004ed3f  lea     rcx, [rbp+var_10]
0x18004ed43  mov     rdx, [rbp+arg_8]
0x18004ed47  xor     r9d, r9d
0x18004ed4a  mov     qword ptr [rsp+68h+dwDesiredAccess], rcx
0x18004ed4f  mov     rcx, r14
0x18004ed52  mov     dword ptr [rbp+var_18], esi
0x18004ed55  mov     rax, [rax+38h]
0x18004ed59  mov     dword ptr [rbp+var_18+4], esi
0x18004ed5c  mov     r8, [rbp+var_18]
0x18004ed60  mov     [rbp+var_10], r12
0x18004ed64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ed69  mov     ebx, eax
0x18004ed6b  test    eax, eax
0x18004ed6d  jns     short loc_18004ED77
0x18004ed6f  mov     r9d, 34Ch
0x18004ed75  jmp     short loc_18004ED20
0x18004ed77  lea     rcx, [rbp+hFile]
0x18004ed7b  mov     [rbp+hFile], rdi
0x18004ed7f  call    ??$replace@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0?0@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0?0@0@@Z; tlx::replace<void *,int (*)(void *),&CloseHandle(void *),-1>(tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),-1> &)
0x18004ed84  mov     rsi, rax
0x18004ed87  call    cs:__imp_GetCurrentProcess
0x18004ed8d  mov     rdi, [rbp+hSourceHandle]
0x18004ed91  mov     rbx, rax
0x18004ed94  call    cs:__imp_GetCurrentProcess
0x18004ed9a  mov     dword ptr [rsp+68h+dwOptions], 2; dwOptions
0x18004eda2  mov     r9, rsi; lpTargetHandle
0x18004eda5  mov     rcx, rax; hSourceProcessHandle
0x18004eda8  mov     [rsp+68h+bInheritHandle], r12d; bInheritHandle
0x18004edad  mov     r8, rbx; hTargetProcessHandle
0x18004edb0  mov     [rsp+68h+dwDesiredAccess], r12d; dwDesiredAccess
0x18004edb5  mov     rdx, rdi; hSourceHandle
0x18004edb8  call    cs:__imp_DuplicateHandle
0x18004edbe  test    eax, eax
0x18004edc0  jnz     short loc_18004EDFB
0x18004edc2  call    cs:__imp_GetLastError
0x18004edc8  mov     ebx, eax
0x18004edca  test    eax, eax
0x18004edcc  jle     short loc_18004EDD7
0x18004edce  movzx   ebx, ax
0x18004edd1  or      ebx, 80070000h
0x18004edd7  mov     r9d, 359h
0x18004eddd  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18004ede4  xor     edx, edx
0x18004ede6  mov     ecx, ebx
0x18004ede8  call    Log_UnistoreHREvent_0
0x18004eded  lea     rcx, [rbp+hFile]
0x18004edf1  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0?0@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),-1>::_Delete(void)
0x18004edf6  jmp     loc_18004ED31
0x18004edfb  mov     edx, [rbp+lDistanceToMove]; lDistanceToMove
0x18004edfe  lea     r8, [rbp+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x18004ee02  mov     rcx, [rbp+hFile]; hFile
0x18004ee06  xor     r9d, r9d; dwMoveMethod
0x18004ee09  call    cs:__imp_SetFilePointer
0x18004ee0f  cmp     eax, 0FFFFFFFFh
0x18004ee12  jnz     short loc_18004EE31
0x18004ee14  call    cs:__imp_GetLastError
0x18004ee1a  mov     ebx, eax
0x18004ee1c  test    eax, eax
0x18004ee1e  jle     short loc_18004EE29
0x18004ee20  movzx   ebx, ax
0x18004ee23  or      ebx, 80070000h
0x18004ee29  mov     r9d, 35Ch
0x18004ee2f  jmp     short loc_18004EDDD
0x18004ee31  mov     rcx, [r14+8]; hObject
0x18004ee35  call    cs:__imp_CloseHandle
0x18004ee3b  mov     rax, [rbp+hFile]
0x18004ee3f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004ee43  mov     [rbp+hFile], rcx
0x18004ee47  mov     [rbp+hSourceHandle], rcx
0x18004ee4b  lea     rcx, [rbp+hFile]
0x18004ee4f  mov     [r14+8], rax
0x18004ee53  mov     [r14+30h], r13
0x18004ee57  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0?0@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),-1>::_Delete(void)
0x18004ee5c  lea     rcx, [rbp+arg_8]; void *
0x18004ee60  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18004ee65  mov     ebx, r12d
0x18004ee68  lea     rcx, [rbp+hSourceHandle]
0x18004ee6c  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0?0@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),-1>::_Delete(void)
0x18004ee71  mov     eax, ebx
0x18004ee73  add     rsp, 68h
0x18004ee77  pop     r15
0x18004ee79  pop     r14
0x18004ee7b  pop     r13
0x18004ee7d  pop     r12
0x18004ee7f  pop     rdi
0x18004ee80  pop     rsi
0x18004ee81  pop     rbx
0x18004ee82  pop     rbp
0x18004ee83  retn
```
