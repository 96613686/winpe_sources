# CAppxStreamingDataSource::RemoveAllBlocksAndResetCachedFileSize(bool)

- ea: `0x180216d6c`
- end: `0x180217025`
- name: `?RemoveAllBlocksAndResetCachedFileSize@CAppxStreamingDataSource@@QEAAX_N@Z`
- size: `697`
- prototype: `void __fastcall(CAppxStreamingDataSource *this, char)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, loader_planting`

## callers

- `0x1802145b0`
- `0x180221230`

## callees

- `0x180113ae8`
- `0x180115528`
- `0x18012b618`
- `0x180216580`
- `0x180216d6c`
- `0x18021c654`
- `0x18021ca58`
- `0x18021ca94`
- `0x18021cdb4`
- `0x18021ce04`
- `0x18021f4d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180216ea8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180216ea8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180216e37`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180216e37`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180216e5f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180216e84`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180216e5f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180216e84`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180216ebc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180216ebc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180216f27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180216f27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180216ecb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180216fbf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180216ecb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180216fbf`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180216f19`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180217001`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180216f19`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180217001`

## string_xrefs

- `0x180216f4e`: `DeleteFile(%ws) failed`
- `0x180216ed9`: `CAppxStreamingDataSource::RemoveAllBlocksAndResetCachedFileSize`
- `0x180216fa4`: `CAppxStreamingDataSource::RemoveAllBlocksAndResetCachedFileSize`
- `0x180216f89`: `SusSetFileSize(%ws) failed`

## pseudocode

```c
void __fastcall CAppxStreamingDataSource::RemoveAllBlocksAndResetCachedFileSize(
        CAppxStreamingDataSource *this,
        char a2)
{
  CAppxBlockTable *v3; // rcx
  unsigned int i; // ebx
  CAppxBlockTable *v6; // rcx
  unsigned int v7; // r12d
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  AppxDownloadUtils *v9; // rdi
  RTL_SRWLOCK *v10; // rbx
  PVOID Ptr; // rdi
  WCHAR *v12; // rbx
  signed int LastError; // eax
  unsigned int v14; // ecx
  int v15; // eax
  CAppxBlockTable *v16; // rbx
  const WCHAR *v17; // rcx
  wchar_t **v18; // [rsp+20h] [rbp-30h]
  LPCWSTR v19; // [rsp+38h] [rbp-18h]
  LPCWSTR lpFileName; // [rsp+40h] [rbp-10h] BYREF
  RTL_SRWLOCK *v21; // [rsp+48h] [rbp-8h] BYREF

  v3 = (CAppxBlockTable *)*((_QWORD *)this + 36);
  if ( v3 )
  {
    if ( !a2 )
    {
      if ( *((_BYTE *)this + 196) )
        return;
      for ( i = 0; i < *((_DWORD *)v3 + 13); ++i )
      {
        if ( (unsigned int)CAppxBlockTable::GetBlockState(v3, i) != 1 )
          CAppxBlockTable::SetBlockState(*((_QWORD *)this + 36), i, 4);
        v3 = (CAppxBlockTable *)*((_QWORD *)this + 36);
      }
      CAppxBlockTable::SaveBlockTableExtension(v3);
    }
    v6 = (CAppxBlockTable *)*((_QWORD *)this + 36);
    LODWORD(lpFileName) = 0;
    if ( (int)CAppxBlockTable::GetNextAvailableIndex(v6, (unsigned int *)&lpFileName) >= 0 )
    {
      v7 = (_DWORD)lpFileName - 1;
      if ( (_DWORD)lpFileName != 1 )
      {
        v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 128);
        v9 = (CAppxStreamingDataSource *)((char *)this + 9);
        do
        {
          lpFileName = 0;
          v21 = 0;
          if ( this != (CAppxStreamingDataSource *)-120LL )
            EnterCriticalSection(v8);
          if ( AppxDownloadUtils::GenerateHashAndIndexFilePath(
                 v9,
                 (const unsigned __int8 (*)[20])v7,
                 *((_QWORD *)this + 21),
                 (const wchar_t *)&lpFileName,
                 v18) >= 0 )
          {
            if ( this != (CAppxStreamingDataSource *)-120LL )
              LeaveCriticalSection(v8);
            if ( (int)CAppxStreamingDataSource::GetFileMapEntryForFile(this, v7, 0, &v21) >= 0 )
            {
              v10 = v21;
              AcquireSRWLockExclusive(v21 + 3);
              Ptr = v10->Ptr;
              v10->Ptr = (PVOID)-1LL;
              ReleaseSRWLockExclusive(v10 + 3);
              if ( Ptr != (PVOID)-1LL )
                CloseHandle(Ptr);
              v12 = (WCHAR *)lpFileName;
              v19 = lpFileName;
              if ( a2 )
              {
                WUTrace(0, 0, 4096, 4, 0, L"%hs deleting %ws");
                if ( !DeleteFileW(v12) )
                {
                  LastError = GetLastError();
                  if ( LastError != 2 )
                  {
                    v14 = (unsigned __int16)LastError | 0x80070000;
                    if ( LastError <= 0 )
                      v14 = LastError;
                    WUTrace(
                      "CAppxStreamingDataSource::RemoveAllBlocksAndResetCachedFileSize",
                      3573,
                      4096,
                      3,
                      v14,
                      L"DeleteFile(%ws) failed",
                      v12,
                      v19);
                  }
                }
              }
              else
              {
                WUTrace(0, 0, 4096, 4, 0, L"%hs setting %ws file size to 0");
                v15 = SusSetFileSize(v12, 0);
                if ( v15 < 0 )
                  WUTrace(
                    "CAppxStreamingDataSource::RemoveAllBlocksAndResetCachedFileSize",
                    3593,
                    4096,
                    3,
                    v15,
                    L"SusSetFileSize(%ws) failed",
                    v12,
                    v19);
              }
              if ( v12 )
                SusFree(v12);
              v9 = (CAppxStreamingDataSource *)((char *)this + 9);
              v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 128);
              goto LABEL_35;
            }
          }
          else if ( this != (CAppxStreamingDataSource *)-120LL )
          {
            LeaveCriticalSection(v8);
          }
          if ( lpFileName )
            SusFree((void *)lpFileName);
LABEL_35:
          --v7;
        }
        while ( v7 );
      }
    }
    if ( a2 )
    {
      v16 = (CAppxBlockTable *)*((_QWORD *)this + 36);
      CAppxBlockTable::CloseBlockTableExtensionFile(v16);
      v17 = (const WCHAR *)*((_QWORD *)v16 + 5);
      if ( v17 )
        DeleteFileW(v17);
    }
  }
}

```

## disassembly

```asm
0x180216d6c  mov     [rsp-28h+arg_8], rbx
0x180216d71  mov     [rsp-28h+arg_10], rsi
0x180216d76  mov     [rsp-28h+arg_18], rdi
0x180216d7b  push    rbp
0x180216d7c  push    r12
0x180216d7e  push    r13
0x180216d80  push    r14
0x180216d82  push    r15
0x180216d84  mov     rbp, rsp
0x180216d87  sub     rsp, 50h
0x180216d8b  mov     r15, rcx
0x180216d8e  xor     r14d, r14d
0x180216d91  mov     rcx, [rcx+120h]
0x180216d98  mov     r13b, dl
0x180216d9b  test    rcx, rcx
0x180216d9e  jz      loc_180217007
0x180216da4  test    dl, dl
0x180216da6  jnz     short loc_180216DF1
0x180216da8  cmp     [r15+0C4h], r14b
0x180216daf  jnz     loc_180217007
0x180216db5  mov     ebx, r14d
0x180216db8  cmp     [rcx+34h], r14d
0x180216dbc  jbe     short loc_180216DEC
0x180216dbe  mov     edx, ebx
0x180216dc0  call    ?GetBlockState@CAppxBlockTable@@QEBA?AW4BlockState@@K@Z; CAppxBlockTable::GetBlockState(ulong)
0x180216dc5  cmp     eax, 1
0x180216dc8  jz      short loc_180216DDE
0x180216dca  mov     rcx, [r15+120h]
0x180216dd1  mov     r8d, 4
0x180216dd7  mov     edx, ebx
0x180216dd9  call    ?SetBlockState@CAppxBlockTable@@QEAAJKW4BlockState@@@Z; CAppxBlockTable::SetBlockState(ulong,BlockState)
0x180216dde  mov     rcx, [r15+120h]; this
0x180216de5  inc     ebx
0x180216de7  cmp     ebx, [rcx+34h]
0x180216dea  jb      short loc_180216DBE
0x180216dec  call    ?SaveBlockTableExtension@CAppxBlockTable@@QEAAJXZ; CAppxBlockTable::SaveBlockTableExtension(void)
0x180216df1  mov     rcx, [r15+120h]; this
0x180216df8  lea     rdx, [rbp+lpFileName]; unsigned int *
0x180216dfc  mov     dword ptr [rbp+lpFileName], r14d
0x180216e00  call    ?GetNextAvailableIndex@CAppxBlockTable@@QEBAJPEAK@Z; CAppxBlockTable::GetNextAvailableIndex(ulong *)
0x180216e05  test    eax, eax
0x180216e07  js      loc_180216FE4
0x180216e0d  mov     r12d, dword ptr [rbp+lpFileName]
0x180216e11  add     r12d, 0FFFFFFFFh
0x180216e15  jz      loc_180216FE4
0x180216e1b  lea     rsi, [r15+78h]
0x180216e1f  lea     rbx, [rsi+8]
0x180216e23  lea     rdi, [r15+9]
0x180216e27  mov     [rbp+lpFileName], r14
0x180216e2b  mov     [rbp+var_8], r14
0x180216e2f  test    rsi, rsi
0x180216e32  jz      short loc_180216E3D
0x180216e34  mov     rcx, rbx; lpCriticalSection
0x180216e37  call    cs:__imp_EnterCriticalSection
0x180216e3d  mov     r8, [r15+0A8h]; unsigned int
0x180216e44  lea     r9, [rbp+lpFileName]; wchar_t *
0x180216e48  mov     edx, r12d; unsigned __int8 (*)[20]
0x180216e4b  mov     rcx, rdi; this
0x180216e4e  call    ?GenerateHashAndIndexFilePath@AppxDownloadUtils@@YAJAEAY0BE@$$CBEKPEB_WPEAPEA_W@Z; AppxDownloadUtils::GenerateHashAndIndexFilePath(uchar const (&)[20],ulong,wchar_t const *,wchar_t * *)
0x180216e53  test    eax, eax
0x180216e55  jns     short loc_180216E7C
0x180216e57  test    rsi, rsi
0x180216e5a  jz      short loc_180216E65
0x180216e5c  mov     rcx, rbx; lpCriticalSection
0x180216e5f  call    cs:__imp_LeaveCriticalSection
0x180216e65  mov     rcx, [rbp+lpFileName]; lpMem
0x180216e69  test    rcx, rcx
0x180216e6c  jz      loc_180216FDA
0x180216e72  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180216e77  jmp     loc_180216FDA
0x180216e7c  test    rsi, rsi
0x180216e7f  jz      short loc_180216E8A
0x180216e81  mov     rcx, rbx; lpCriticalSection
0x180216e84  call    cs:__imp_LeaveCriticalSection
0x180216e8a  lea     r9, [rbp+var_8]
0x180216e8e  xor     r8d, r8d
0x180216e91  mov     edx, r12d
0x180216e94  mov     rcx, r15
0x180216e97  call    ?GetFileMapEntryForFile@CAppxStreamingDataSource@@AEAAJKW4GetFileMapEntryLoad@1@PEAPEAUHandleAndProgressInfo@1@@Z; CAppxStreamingDataSource::GetFileMapEntryForFile(ulong,CAppxStreamingDataSource::GetFileMapEntryLoad,CAppxStreamingDataSource::HandleAndProgressInfo * *)
0x180216e9c  test    eax, eax
0x180216e9e  js      short loc_180216E65
0x180216ea0  mov     rbx, [rbp+var_8]
0x180216ea4  lea     rcx, [rbx+18h]; SRWLock
0x180216ea8  call    cs:__imp_AcquireSRWLockExclusive
0x180216eae  mov     rdi, [rbx]
0x180216eb1  lea     rcx, [rbx+18h]; SRWLock
0x180216eb5  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x180216ebc  call    cs:__imp_ReleaseSRWLockExclusive
0x180216ec2  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180216ec6  jz      short loc_180216ED5
0x180216ec8  mov     rcx, rdi; hObject
0x180216ecb  call    cs:__imp_CloseHandle
0x180216ed1  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180216ed5  mov     rbx, [rbp+lpFileName]
0x180216ed9  lea     rax, aCappxstreaming_1; "CAppxStreamingDataSource::RemoveAllBloc"...
0x180216ee0  xor     r14d, r14d
0x180216ee3  mov     [rsp+50h+var_18], rbx
0x180216ee8  xor     edx, edx
0x180216eea  mov     [rsp+50h+var_20], rax
0x180216eef  xor     ecx, ecx
0x180216ef1  mov     r8d, 1000h
0x180216ef7  lea     r9d, [r14+4]
0x180216efb  test    r13b, r13b
0x180216efe  jz      short loc_180216F60
0x180216f00  lea     rax, aHsDeletingWs; "%hs deleting %ws"
0x180216f07  mov     [rsp+50h+var_28], rax
0x180216f0c  mov     [rsp+50h+var_30], r14
0x180216f11  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180216f16  mov     rcx, rbx; lpFileName
0x180216f19  call    cs:__imp_DeleteFileW
0x180216f1f  test    eax, eax
0x180216f21  jnz     loc_180216FB6
0x180216f27  call    cs:__imp_GetLastError
0x180216f2d  cmp     eax, 2
0x180216f30  jz      loc_180216FB6
0x180216f36  movzx   ecx, ax
0x180216f39  mov     edx, 0DF5h
0x180216f3e  or      ecx, 80070000h
0x180216f44  mov     [rsp+50h+var_20], rbx
0x180216f49  test    eax, eax
0x180216f4b  cmovle  ecx, eax
0x180216f4e  lea     rax, aDeletefileWsFa; "DeleteFile(%ws) failed"
0x180216f55  mov     [rsp+50h+var_28], rax
0x180216f5a  mov     dword ptr [rsp+50h+var_30], ecx
0x180216f5e  jmp     short loc_180216F9E
0x180216f60  lea     rax, aHsSettingWsFil; "%hs setting %ws file size to 0"
0x180216f67  mov     [rsp+50h+var_28], rax
0x180216f6c  mov     [rsp+50h+var_30], r14
0x180216f71  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180216f76  xor     edx, edx; unsigned __int64
0x180216f78  mov     rcx, rbx; wchar_t *
0x180216f7b  call    ?SusSetFileSize@@YAJPEB_W_K@Z; SusSetFileSize(wchar_t const *,unsigned __int64)
0x180216f80  test    eax, eax
0x180216f82  jns     short loc_180216FB6
0x180216f84  mov     [rsp+50h+var_20], rbx
0x180216f89  lea     rcx, aSussetfilesize; "SusSetFileSize(%ws) failed"
0x180216f90  mov     [rsp+50h+var_28], rcx
0x180216f95  mov     edx, 0E09h
0x180216f9a  mov     dword ptr [rsp+50h+var_30], eax
0x180216f9e  mov     r9d, 3
0x180216fa4  lea     rcx, aCappxstreaming_1; "CAppxStreamingDataSource::RemoveAllBloc"...
0x180216fab  mov     r8d, 1000h
0x180216fb1  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180216fb6  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180216fba  jz      short loc_180216FC5
0x180216fbc  mov     rcx, rdi; hObject
0x180216fbf  call    cs:__imp_CloseHandle
0x180216fc5  test    rbx, rbx
0x180216fc8  jz      short loc_180216FD2
0x180216fca  mov     rcx, rbx; lpMem
0x180216fcd  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180216fd2  lea     rdi, [r15+9]
0x180216fd6  lea     rbx, [rsi+8]
0x180216fda  add     r12d, 0FFFFFFFFh
0x180216fde  jnz     loc_180216E27
0x180216fe4  test    r13b, r13b
0x180216fe7  jz      short loc_180217007
0x180216fe9  mov     rbx, [r15+120h]
0x180216ff0  mov     rcx, rbx; this
0x180216ff3  call    ?CloseBlockTableExtensionFile@CAppxBlockTable@@AEAAXXZ; CAppxBlockTable::CloseBlockTableExtensionFile(void)
0x180216ff8  mov     rcx, [rbx+28h]; lpFileName
0x180216ffc  test    rcx, rcx
0x180216fff  jz      short loc_180217007
0x180217001  call    cs:__imp_DeleteFileW
0x180217007  lea     r11, [rsp+50h+var_s0]
0x18021700c  mov     rbx, [r11+38h]
0x180217010  mov     rsi, [r11+40h]
0x180217014  mov     rdi, [r11+48h]
0x180217018  mov     rsp, r11
0x18021701b  pop     r15
0x18021701d  pop     r14
0x18021701f  pop     r13
0x180217021  pop     r12
0x180217023  pop     rbp
0x180217024  retn
```
