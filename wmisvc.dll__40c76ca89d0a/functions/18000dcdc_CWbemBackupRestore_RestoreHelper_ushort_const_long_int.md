# CWbemBackupRestore::RestoreHelper(ushort const *,long,int &)

- ea: `0x18000dcdc`
- end: `0x18000e207`
- name: `?RestoreHelper@CWbemBackupRestore@@IEAAJPEBGJAEAH@Z`
- size: `1323`
- prototype: `__int64 __fastcall(CWbemBackupRestore *this, const unsigned __int16 *, int, int *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800144b0`

## callees

- `0x1800039f4`
- `0x1800076e0`
- `0x18000dcdc`
- `0x18000e210`
- `0x180012604`
- `0x18001273c`
- `0x180012c34`
- `0x180013ddc`
- `0x180013edc`
- `0x180013ffc`
- `0x1800148e4`
- `0x1800149e8`
- `0x18001d377`
- `0x18001d3a0`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000de8a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000de8a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e0a1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e0a1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000e0d2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000e0d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e0dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e0dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000dd17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000dd17`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x18000de7f`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x18000de7f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000df69`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000e1cb`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000df69`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000e1cb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000de16`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000de16`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000dddb`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000dddb`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x18000df8a`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x18000df8a`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x18000dd34`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x18000dd34`
- `wbemcomn!EnableAllPrivileges` at `0x18000dda5`
- `wbemcomn!EnableAllPrivileges` at `0x18000dda5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000dd50`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000de35`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000dea4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000dd50`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000de35`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000dea4`
- `wbemcomn!GetMemLogObject` at `0x18000dd40`
- `wbemcomn!GetMemLogObject` at `0x18000de25`
- `wbemcomn!GetMemLogObject` at `0x18000de94`
- `wbemcomn!GetMemLogObject` at `0x18000dd40`
- `wbemcomn!GetMemLogObject` at `0x18000de25`
- `wbemcomn!GetMemLogObject` at `0x18000de94`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e053`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e053`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000e026`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000e026`

## pseudocode

```c
__int64 __fastcall CWbemBackupRestore::RestoreHelper(
        CWbemBackupRestore *this,
        const unsigned __int16 *a2,
        int a3,
        int *a4)
{
  CMemoryLog *MemLogObject; // rax
  __int64 result; // rax
  int RepPath; // edi
  DWORD FileAttributesW; // eax
  HANDLE FileW; // rax
  void *v13; // rdi
  CMemoryLog *v14; // rax
  DWORD FileType; // ebx
  CMemoryLog *v16; // rax
  bool v17; // bl
  unsigned __int16 *v18; // rdx
  char v19; // r15
  unsigned int v20; // edx
  int v21; // r12d
  LPVOID v22; // rbx
  BSTR v23; // rsi
  LSTATUS v24; // eax
  CMemoryLog *v25; // rax
  ULONG BackTraceHash; // [rsp+5Ch] [rbp-49Ch] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-498h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-490h] BYREF
  __int64 v29; // [rsp+70h] [rbp-488h] BYREF
  __int64 v30; // [rsp+78h] [rbp-480h]
  BSTR v31; // [rsp+80h] [rbp-478h] BYREF
  LPVOID v32; // [rsp+88h] [rbp-470h]
  WCHAR FileName[264]; // [rsp+90h] [rbp-468h] BYREF
  unsigned __int16 v34[264]; // [rsp+2A0h] [rbp-258h] BYREF

  *a4 = 0;
  *((_DWORD *)this + 22) |= 2u;
  *((_DWORD *)this + 23) = GetCurrentThreadId();
  BackTraceHash = 0;
  RtlCaptureStackBackTrace(0, 8u, (PVOID *)this + 12, &BackTraceHash);
  if ( *((_DWORD *)this + 16) )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217386);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_da0c108f5fb630a241f44bac5f55929c_Traceguids, 2147749910LL);
    }
    return 2147749910LL;
  }
  try
  {
    EnableAllPrivileges(1u);
    if ( (unsigned int)CheckSecurity(18, 0) )
    {
      if ( a2 )
      {
        if ( (a3 & 0xFFFFFFFE) == 0 )
        {
          FileAttributesW = GetFileAttributesW(a2);
          if ( FileAttributesW != -1 && (FileAttributesW & 0x1650) == 0 )
          {
            FileW = CreateFileW(a2, 0, 7u, 0, 3u, 0x80u, 0);
            v13 = FileW;
            if ( FileW == (HANDLE)-1LL )
            {
              v14 = GetMemLogObject();
              CMemoryLog::Write(v14, -2147217400);
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  20,
                  WPP_da0c108f5fb630a241f44bac5f55929c_Traceguids,
                  2147749896LL);
              }
              return 2147749896LL;
            }
            FileType = GetFileType(FileW);
            CloseHandle(v13);
            if ( FileType != 1 )
            {
              v16 = GetMemLogObject();
              CMemoryLog::Write(v16, -2147217400);
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  21,
                  WPP_da0c108f5fb630a241f44bac5f55929c_Traceguids,
                  2147749896LL);
              }
              return 2147749896LL;
            }
            RepPath = WbemPauseService();
            v17 = RepPath >= 0;
            goto LABEL_28;
          }
        }
      }
      RepPath = -2147217400;
    }
    else
    {
      RepPath = -2147217405;
    }
    v17 = 0;
LABEL_28:
    memset_0(FileName, 0, 0x20Au);
    if ( RepPath >= 0 )
      RepPath = GetRepPath(FileName, v18);
    v19 = 0;
    if ( RepPath >= 0 )
    {
      if ( (unsigned int)wbem_wcsicmp(FileName, a2) )
      {
        DeleteFileW(FileName);
        if ( CopyFileExW(a2, FileName, 0, 0, 0, 0) )
          v19 = 1;
        else
          RepPath = -2147217407;
      }
      else
      {
        *a4 = 1;
      }
    }
    memset_0(v34, 0, 0x20Au);
    if ( RepPath >= 0 )
      RepPath = SaveRepository(v34, v20);
    v21 = 0;
    if ( v17 )
      v21 = WbemContinueService();
    if ( RepPath >= 0 && v21 >= 0 )
    {
      ppv = 0;
      RepPath = CoCreateInstance(&CLSID_WbemLocator, 0, 1u, &IID_IWbemLocator, &ppv);
      v22 = ppv;
      v32 = ppv;
      if ( RepPath >= 0 )
      {
        v29 = 0;
        v23 = SysAllocString(L"root");
        v31 = v23;
        if ( !v23 )
          RepPath = -2147217402;
        if ( RepPath >= 0 )
        {
          phkResult = 0;
          v24 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\WBEM\\CIMOM", 0, 2u, &phkResult);
          if ( v24 )
          {
            if ( v24 > 0 )
              RepPath = (unsigned __int16)v24 | 0x80070000;
            else
              RepPath = v24;
          }
          if ( RepPath >= 0 )
          {
            RegDeleteValueW(phkResult, L"LocaleUpgrade");
            RegCloseKey(phkResult);
            RepPath = (*(__int64 (__fastcall **)(LPVOID, BSTR, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, __int64 *))(*(_QWORD *)ppv + 24LL))(
                        ppv,
                        v23,
                        0,
                        0,
                        0,
                        0,
                        0,
                        0,
                        &v29);
            v30 = v29;
            if ( RepPath == -2147217388 )
              RepPath = -2147217407;
            if ( v29 )
              (*(void (**)(void))(*(_QWORD *)v29 + 16LL))();
            v30 = 0;
          }
        }
        CSysFreeMe::~CSysFreeMe((CSysFreeMe *)&v31);
      }
      if ( v22 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v22 + 16LL))(v22);
      v32 = 0;
      if ( RepPath >= 0 )
      {
        DeleteSavedRepository(v34);
      }
      else if ( (int)WbemPauseService() >= 0 && (int)DeleteRepository() >= 0 && (int)RestoreSavedRepository(v34) >= 0 )
      {
        WbemContinueService();
      }
    }
    if ( v19 && FileName[0] )
      DeleteFileW(FileName);
    if ( RepPath < 0 )
      result = (unsigned int)RepPath;
    else
      result = (unsigned int)v21;
  }
  catch ( CX_MemoryException )
  {
    v25 = GetMemLogObject();
    CMemoryLog::Write(v25, -2147217402);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_da0c108f5fb630a241f44bac5f55929c_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  EnableAllPrivileges(1u);
}

```

## disassembly

```asm
0x18000dcdc  push    rbx
0x18000dcde  push    rsi
0x18000dcdf  push    rdi
0x18000dce0  push    r12
0x18000dce2  push    r13
0x18000dce4  push    r14
0x18000dce6  push    r15
0x18000dce8  sub     rsp, 4C0h
0x18000dcef  mov     rax, cs:__security_cookie
0x18000dcf6  xor     rax, rsp
0x18000dcf9  mov     [rsp+4F8h+var_48], rax
0x18000dd01  mov     r12, r9
0x18000dd04  mov     edi, r8d
0x18000dd07  mov     r14, rdx
0x18000dd0a  mov     rbx, rcx
0x18000dd0d  xor     r13d, r13d
0x18000dd10  mov     [r9], r13d
0x18000dd13  or      dword ptr [rcx+58h], 2
0x18000dd17  call    cs:__imp_GetCurrentThreadId
0x18000dd1d  mov     [rbx+5Ch], eax
0x18000dd20  mov     [rsp+4F8h+BackTraceHash], r13d
0x18000dd25  lea     r8, [rbx+60h]; BackTrace
0x18000dd29  lea     r9, [rsp+4F8h+BackTraceHash]; BackTraceHash
0x18000dd2e  lea     edx, [r13+8]; FramesToCapture
0x18000dd32  xor     ecx, ecx; FramesToSkip
0x18000dd34  call    cs:__imp_RtlCaptureStackBackTrace
0x18000dd3a  cmp     [rbx+40h], r13d
0x18000dd3e  jz      short loc_18000DD99
0x18000dd40  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000dd46  mov     ebx, 80041016h
0x18000dd4b  mov     edx, ebx
0x18000dd4d  mov     rcx, rax
0x18000dd50  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000dd56  lea     rax, WPP_GLOBAL_Control
0x18000dd5d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd64  cmp     rcx, rax
0x18000dd67  jz      short loc_18000DD92
0x18000dd69  lea     esi, [r13+1]
0x18000dd6d  test    [rcx+1Ch], sil
0x18000dd71  jz      short loc_18000DD92
0x18000dd73  cmp     byte ptr [rcx+19h], 2
0x18000dd77  jb      short loc_18000DD92
0x18000dd79  lea     edx, [rsi+12h]
0x18000dd7c  mov     r9d, 80041016h
0x18000dd82  lea     r8, WPP_da0c108f5fb630a241f44bac5f55929c_Traceguids
0x18000dd89  mov     rcx, [rcx+10h]
0x18000dd8d  call    WPP_SF_d
0x18000dd92  mov     eax, ebx
0x18000dd94  jmp     loc_18000E1E3
0x18000dd99  mov     [rsp+4F8h+var_4A4], r13d
0x18000dd9e  mov     esi, 1
0x18000dda3  mov     ecx, esi
0x18000dda5  call    cs:__imp_?EnableAllPrivileges@@YAJK@Z; EnableAllPrivileges(ulong)
0x18000ddab  xor     edx, edx; void **
0x18000ddad  lea     ecx, [rsi+11h]; int
0x18000ddb0  call    ?CheckSecurity@@YAHJPEAPEAX@Z; CheckSecurity(long,void * *)
0x18000ddb5  test    eax, eax
0x18000ddb7  jnz     short loc_18000DDC3
0x18000ddb9  mov     edi, 80041003h
0x18000ddbe  jmp     loc_18000DF0A
0x18000ddc3  test    r14, r14
0x18000ddc6  jz      loc_18000DF05
0x18000ddcc  test    edi, 0FFFFFFFEh
0x18000ddd2  jnz     loc_18000DF05
0x18000ddd8  mov     rcx, r14; lpFileName
0x18000dddb  call    cs:__imp_GetFileAttributesW
0x18000dde1  cmp     eax, 0FFFFFFFFh
0x18000dde4  jz      loc_18000DF05
0x18000ddea  test    eax, 1650h
0x18000ddef  jnz     loc_18000DF05
0x18000ddf5  mov     [rsp+4F8h+hTemplateFile], r13; hTemplateFile
0x18000ddfa  mov     [rsp+4F8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000de02  mov     [rsp+4F8h+dwCreationDisposition], 3; dwCreationDisposition
0x18000de0a  xor     r9d, r9d; lpSecurityAttributes
0x18000de0d  xor     edx, edx; dwDesiredAccess
0x18000de0f  lea     r8d, [r9+7]; dwShareMode
0x18000de13  mov     rcx, r14; lpFileName
0x18000de16  call    cs:__imp_CreateFileW
0x18000de1c  mov     rdi, rax
0x18000de1f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000de23  jnz     short loc_18000DE7C
0x18000de25  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000de2b  mov     edi, 80041008h
0x18000de30  mov     edx, edi
0x18000de32  mov     rcx, rax
0x18000de35  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000de3b  lea     rax, WPP_GLOBAL_Control
0x18000de42  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de49  cmp     rcx, rax
0x18000de4c  jz      short loc_18000DE75
0x18000de4e  test    [rcx+1Ch], sil
0x18000de52  jz      short loc_18000DE75
0x18000de54  cmp     byte ptr [rcx+19h], 2
0x18000de58  jb      short loc_18000DE75
0x18000de5a  mov     edx, 14h
0x18000de5f  mov     r9d, 80041008h
0x18000de65  lea     r8, WPP_da0c108f5fb630a241f44bac5f55929c_Traceguids
0x18000de6c  mov     rcx, [rcx+10h]
0x18000de70  call    WPP_SF_d
0x18000de75  mov     eax, edi
0x18000de77  jmp     loc_18000E1E3
0x18000de7c  mov     rcx, rdi; hFile
0x18000de7f  call    cs:__imp_GetFileType
0x18000de85  mov     ebx, eax
0x18000de87  mov     rcx, rdi; hObject
0x18000de8a  call    cs:__imp_CloseHandle
0x18000de90  cmp     ebx, esi
0x18000de92  jz      short loc_18000DEEB
0x18000de94  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000de9a  mov     edi, 80041008h
0x18000de9f  mov     edx, edi
0x18000dea1  mov     rcx, rax
0x18000dea4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000deaa  lea     rax, WPP_GLOBAL_Control
0x18000deb1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000deb8  cmp     rcx, rax
0x18000debb  jz      short loc_18000DEE4
0x18000debd  test    [rcx+1Ch], sil
0x18000dec1  jz      short loc_18000DEE4
0x18000dec3  cmp     byte ptr [rcx+19h], 2
0x18000dec7  jb      short loc_18000DEE4
0x18000dec9  mov     edx, 15h
0x18000dece  mov     r9d, 80041008h
0x18000ded4  lea     r8, WPP_da0c108f5fb630a241f44bac5f55929c_Traceguids
0x18000dedb  mov     rcx, [rcx+10h]
0x18000dedf  call    WPP_SF_d
0x18000dee4  mov     eax, edi
0x18000dee6  jmp     loc_18000E1E3
0x18000deeb  movzx   ebx, r13b
0x18000deef  mov     [rsp+4F8h+var_4A8], bl
0x18000def3  call    ?WbemPauseService@@YAJXZ; WbemPauseService(void)
0x18000def8  mov     edi, eax
0x18000defa  mov     [rsp+4F8h+var_4A4], eax
0x18000defe  test    eax, eax
0x18000df00  cmovns  ebx, esi
0x18000df03  jmp     short loc_18000DF11
0x18000df05  mov     edi, 80041008h
0x18000df0a  mov     [rsp+4F8h+var_4A4], edi
0x18000df0e  mov     bl, r13b
0x18000df11  mov     [rsp+4F8h+var_4A8], bl
0x18000df15  xor     edx, edx; Val
0x18000df17  mov     r8d, 20Ah; Size
0x18000df1d  lea     rcx, [rsp+4F8h+FileName]; void *
0x18000df25  call    memset_0
0x18000df2a  test    edi, edi
0x18000df2c  js      short loc_18000DF41
0x18000df2e  lea     rcx, [rsp+4F8h+FileName]; unsigned __int16 *
0x18000df36  call    ?GetRepPath@@YAJQEAGPEAG@Z; GetRepPath(ushort * const,ushort *)
0x18000df3b  mov     edi, eax
0x18000df3d  mov     [rsp+4F8h+var_4A4], eax
0x18000df41  mov     r15b, r13b
0x18000df44  mov     [rsp+4F8h+var_4A0], r13b
0x18000df49  test    edi, edi
0x18000df4b  js      short loc_18000DFB2
0x18000df4d  mov     rdx, r14; unsigned __int16 *
0x18000df50  lea     rcx, [rsp+4F8h+FileName]; unsigned __int16 *
0x18000df58  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x18000df5d  test    eax, eax
0x18000df5f  jz      short loc_18000DFAE
0x18000df61  lea     rcx, [rsp+4F8h+FileName]; lpFileName
0x18000df69  call    cs:__imp_DeleteFileW
0x18000df6f  mov     [rsp+4F8h+dwFlagsAndAttributes], r13d; dwCopyFlags
0x18000df74  mov     qword ptr [rsp+4F8h+dwCreationDisposition], r13; pbCancel
0x18000df79  xor     r9d, r9d; lpData
0x18000df7c  xor     r8d, r8d; lpProgressRoutine
0x18000df7f  lea     rdx, [rsp+4F8h+FileName]; lpNewFileName
0x18000df87  mov     rcx, r14; lpExistingFileName
0x18000df8a  call    cs:__imp_CopyFileExW
0x18000df90  mov     r14d, 80041001h
0x18000df96  test    eax, eax
0x18000df98  jnz     short loc_18000DFA4
0x18000df9a  mov     edi, r14d
0x18000df9d  mov     [rsp+4F8h+var_4A4], r14d
0x18000dfa2  jmp     short loc_18000DFB8
0x18000dfa4  mov     r15b, sil
0x18000dfa7  mov     [rsp+4F8h+var_4A0], sil
0x18000dfac  jmp     short loc_18000DFB8
0x18000dfae  mov     [r12], esi
0x18000dfb2  mov     r14d, 80041001h
0x18000dfb8  xor     edx, edx; Val
0x18000dfba  mov     r8d, 20Ah; Size
0x18000dfc0  lea     rcx, [rsp+4F8h+var_258]; void *
0x18000dfc8  call    memset_0
0x18000dfcd  test    edi, edi
0x18000dfcf  js      short loc_18000DFE4
0x18000dfd1  lea     rcx, [rsp+4F8h+var_258]; unsigned __int16 *
0x18000dfd9  call    ?SaveRepository@@YAJPEAGK@Z; SaveRepository(ushort *,ulong)
0x18000dfde  mov     edi, eax
0x18000dfe0  mov     [rsp+4F8h+var_4A4], eax
0x18000dfe4  mov     r12d, r13d
0x18000dfe7  test    bl, bl
0x18000dfe9  jz      short loc_18000DFF3
0x18000dfeb  call    ?WbemContinueService@@YAJXZ; WbemContinueService(void)
0x18000dff0  mov     r12d, eax
0x18000dff3  test    edi, edi
0x18000dff5  js      loc_18000E1B3
0x18000dffb  test    r12d, r12d
0x18000dffe  js      loc_18000E1B3
0x18000e004  mov     [rsp+4F8h+ppv], r13
0x18000e009  lea     rax, [rsp+4F8h+ppv]
0x18000e00e  mov     qword ptr [rsp+4F8h+dwCreationDisposition], rax; ppv
0x18000e013  lea     r9, IID_IWbemLocator; riid
0x18000e01a  mov     r8d, esi; dwClsContext
0x18000e01d  xor     edx, edx; pUnkOuter
0x18000e01f  lea     rcx, CLSID_WbemLocator; rclsid
0x18000e026  call    cs:__imp_CoCreateInstance
0x18000e02c  mov     edi, eax
0x18000e02e  mov     [rsp+4F8h+var_4A4], eax
0x18000e032  mov     rbx, [rsp+4F8h+ppv]
0x18000e037  mov     [rsp+4F8h+var_470], rbx
0x18000e03f  test    eax, eax
0x18000e041  js      loc_18000E15C
0x18000e047  mov     [rsp+4F8h+var_488], r13
0x18000e04c  lea     rcx, psz; "root"
0x18000e053  call    cs:__imp_SysAllocString
0x18000e059  mov     rsi, rax
0x18000e05c  mov     [rsp+4F8h+var_478], rax
0x18000e064  mov     eax, 80041006h
0x18000e069  test    rsi, rsi
0x18000e06c  cmovz   edi, eax
0x18000e06f  mov     [rsp+4F8h+var_4A4], edi
0x18000e073  test    edi, edi
0x18000e075  js      loc_18000E14E
0x18000e07b  mov     [rsp+4F8h+phkResult], r13
0x18000e080  lea     rax, [rsp+4F8h+phkResult]
0x18000e085  mov     qword ptr [rsp+4F8h+dwCreationDisposition], rax; phkResult
0x18000e08a  mov     r9d, 2; samDesired
0x18000e090  xor     r8d, r8d; ulOptions
0x18000e093  lea     rdx, SubKey; "Software\\Microsoft\\WBEM\\CIMOM"
0x18000e09a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000e0a1  call    cs:__imp_RegOpenKeyExW
0x18000e0a7  test    eax, eax
0x18000e0a9  jz      short loc_18000E0BE
0x18000e0ab  jg      short loc_18000E0B1
0x18000e0ad  mov     edi, eax
0x18000e0af  jmp     short loc_18000E0BA
0x18000e0b1  movzx   edi, ax
0x18000e0b4  or      edi, 80070000h
0x18000e0ba  mov     [rsp+4F8h+var_4A4], edi
0x18000e0be  test    edi, edi
0x18000e0c0  js      loc_18000E14E
0x18000e0c6  lea     rdx, aLocaleupgrade; "LocaleUpgrade"
0x18000e0cd  mov     rcx, [rsp+4F8h+phkResult]; hKey
0x18000e0d2  call    cs:__imp_RegDeleteValueW
0x18000e0d8  mov     rcx, [rsp+4F8h+phkResult]; hKey
0x18000e0dd  call    cs:__imp_RegCloseKey
0x18000e0e3  mov     rcx, [rsp+4F8h+ppv]
0x18000e0e8  mov     rax, [rcx]
0x18000e0eb  lea     rdx, [rsp+4F8h+var_488]
0x18000e0f0  mov     [rsp+4F8h+var_4B8], rdx
0x18000e0f5  mov     [rsp+4F8h+var_4C0], r13
0x18000e0fa  mov     [rsp+4F8h+hTemplateFile], r13
0x18000e0ff  mov     [rsp+4F8h+dwFlagsAndAttributes], r13d
0x18000e104  mov     qword ptr [rsp+4F8h+dwCreationDisposition], r13
0x18000e109  xor     r9d, r9d
0x18000e10c  xor     r8d, r8d
0x18000e10f  mov     rdx, rsi
0x18000e112  mov     rax, [rax+18h]
0x18000e116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e11b  mov     edi, eax
0x18000e11d  mov     [rsp+4F8h+var_4A4], eax
0x18000e121  mov     rcx, [rsp+4F8h+var_488]
0x18000e126  mov     [rsp+4F8h+var_480], rcx
0x18000e12b  cmp     eax, 80041014h
0x18000e130  cmovz   edi, r14d
0x18000e134  mov     [rsp+4F8h+var_4A4], edi
0x18000e138  test    rcx, rcx
0x18000e13b  jz      short loc_18000E149
0x18000e13d  mov     rax, [rcx]
0x18000e140  mov     rax, [rax+10h]
0x18000e144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e149  mov     [rsp+4F8h+var_480], r13
0x18000e14e  lea     rcx, [rsp+4F8h+var_478]; this
0x18000e156  call    ??1CSysFreeMe@@QEAA@XZ; CSysFreeMe::~CSysFreeMe(void)
0x18000e15b  nop
0x18000e15c  test    rbx, rbx
0x18000e15f  jz      short loc_18000E170
0x18000e161  mov     rax, [rbx]
0x18000e164  mov     rcx, rbx
0x18000e167  mov     rax, [rax+10h]
0x18000e16b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e170  mov     [rsp+4F8h+var_470], r13
0x18000e178  test    edi, edi
0x18000e17a  jns     short loc_18000E1A6
0x18000e17c  call    ?WbemPauseService@@YAJXZ; WbemPauseService(void)
0x18000e181  test    eax, eax
0x18000e183  js      short loc_18000E1B3
0x18000e185  call    ?DeleteRepository@@YAJXZ; DeleteRepository(void)
0x18000e18a  test    eax, eax
0x18000e18c  js      short loc_18000E1B3
0x18000e18e  lea     rcx, [rsp+4F8h+var_258]; unsigned __int16 *
0x18000e196  call    ?RestoreSavedRepository@@YAJPEBG@Z; RestoreSavedRepository(ushort const *)
0x18000e19b  test    eax, eax
0x18000e19d  js      short loc_18000E1B3
0x18000e19f  call    ?WbemContinueService@@YAJXZ; WbemContinueService(void)
0x18000e1a4  jmp     short loc_18000E1B3
0x18000e1a6  lea     rcx, [rsp+4F8h+var_258]; unsigned __int16 *
0x18000e1ae  call    ?DeleteSavedRepository@@YAJPEBG@Z; DeleteSavedRepository(ushort const *)
0x18000e1b3  test    r15b, r15b
0x18000e1b6  jz      short loc_18000E1D1
  ... truncated ...
```
