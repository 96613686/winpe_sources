# CopyRupFile(ushort const *,ushort const *,int,int)

- ea: `0x18000c25c`
- end: `0x18000c54e`
- name: `?CopyRupFile@@YAJPEBG0HH@Z`
- size: `754`
- prototype: `__int64 __fastcall(char *, char *, int, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800085b0`

## callees

- `0x1800072a0`
- `0x1800095cc`
- `0x18000987c`
- `0x18000c25c`
- `0x18000c554`
- `0x18000c720`
- `0x18000cfe4`
- `0x180017a94`
- `0x180019f0c`
- `0x18001a144`
- `0x18001aafc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c515`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c515`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c2ac`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c2ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c29a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c507`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c29a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c507`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c43b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c43b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c398`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c398`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000c37d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000c37d`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18000c38f`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18000c38f`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000c487`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000c487`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000c494`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000c494`
- `api-ms-win-core-kernel32-private-l1-1-1!PrivCopyFileExW` at `0x18000c338`
- `api-ms-win-core-kernel32-private-l1-1-1!PrivCopyFileExW` at `0x18000c338`

## string_xrefs

- `0x18000c2d4`: `onecore\ds\security\gina\profile\proflib\dir.cpp`
- `0x18000c3ed`: `onecore\ds\security\gina\profile\proflib\dir.cpp`
- `0x18000c473`: `onecore\ds\security\gina\profile\proflib\dir.cpp`
- `0x18000c4b5`: `onecore\ds\security\gina\profile\proflib\dir.cpp`
- `0x18000c4ee`: `onecore\ds\security\gina\profile\proflib\dir.cpp`
- `0x18000c525`: `onecore\ds\security\gina\profile\proflib\dir.cpp`
- `0x18000c2e2`: `_GetTempFileName failed for <%ws>.`
- `0x18000c3e1`: `Failed to rename %ws to %ws`
- `0x18000c455`: `Failed to copy %ws to %ws`
- `0x18000c4a2`: `Failed to delete %ws`

## pseudocode

```c
__int64 __fastcall CopyRupFile(char *a1, char *a2, int a3, int a4)
{
  unsigned __int16 *v8; // rdi
  HANDLE ProcessHeap; // rax
  const unsigned __int16 *v10; // rax
  unsigned __int64 v11; // r9
  WCHAR *v12; // rbx
  const char *TempFileName; // rdi
  HANDLE FileW; // rax
  void *v15; // rdi
  __int64 v16; // rcx
  unsigned int v17; // eax
  __int64 v18; // rcx
  signed int LastError; // eax
  BOOL v20; // eax
  DWORD v21; // eax
  HANDLE v22; // rax
  int dwCreationDisposition; // [rsp+20h] [rbp-68h]
  int v25; // [rsp+40h] [rbp-48h] BYREF
  unsigned __int64 v26[8]; // [rsp+48h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v26[0] = 0;
  StringCchLengthW((const unsigned __int16 *)a2, 0x7FFFFFFFu, v26);
  v8 = (unsigned __int16 *)(v26[0] + 45);
  ProcessHeap = GetProcessHeap();
  v10 = (const unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 2LL * (_QWORD)v8);
  v12 = (WCHAR *)v10;
  if ( v10 )
  {
    TempFileName = (const char *)(unsigned int)proflib::_GetTempFileName((proflib *)a2, v10, v8, v11);
    if ( (int)wil::details::in1diag3::Log_IfFailedMsg(
                retaddr,
                (void *)0x12B,
                (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\dir.cpp",
                TempFileName,
                (int)"_GetTempFileName failed for <%ws>.",
                a2) >= 0 )
    {
      v25 = 0;
      if ( (unsigned int)PrivCopyFileExW(a1, v12, CopyProgressRoutine, 0, &v25, a3 != 0 ? 512 : 1552) )
      {
        LODWORD(v26[0]) = 0;
        if ( a4 )
        {
          FileW = CreateFileW(v12, 0x40000000u, 0, 0, 3u, 0x80u, 0);
          v15 = FileW;
          if ( FileW != (HANDLE)-1LL )
          {
            FlushFileBuffers(FileW);
            CloseHandle(v15);
          }
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
          && (Microsoft_Windows_User_Profiles_GeneralEnableBits & 8) != 0 )
        {
          McTemplateU0zz_EventWriteTransfer(v16, EVENT_COPY_RUP_FILE_COPY_SUCCEEDED, a1, v12);
        }
        v17 = RenameFile((char *)v12, a2);
        LODWORD(TempFileName) = wil::details::in1diag3::Log_IfFailedMsg(
                                  retaddr,
                                  (void *)0x150,
                                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\dir.cpp",
                                  (const char *)v17,
                                  (int)"Failed to rename %ws to %ws",
                                  (const char *)v12,
                                  a2);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
          && (int)TempFileName >= 0
          && (Microsoft_Windows_User_Profiles_GeneralEnableBits & 8) != 0 )
        {
          McTemplateU0z_EventWriteTransfer(v18, EVENT_COPY_RUP_FILE_RENAME_SUCCEEDED, a2);
        }
      }
      else
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        LODWORD(TempFileName) = wil::details::in1diag3::Log_IfFailedMsg(
                                  retaddr,
                                  (void *)0x15C,
                                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\dir.cpp",
                                  (const char *)(unsigned int)LastError,
                                  (int)"Failed to copy %ws to %ws",
                                  a1,
                                  v12);
      }
      if ( SetFileAttributesW(v12, 0x80u) )
      {
        v20 = DeleteFileW(v12);
        wil::details::in1diag3::Log_GetLastErrorIfMsg(
          retaddr,
          (void *)0x162,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\dir.cpp",
          (const char *)!v20,
          (bool)"Failed to delete %ws",
          (const char *)v12);
      }
      else
      {
        v21 = GetLastError();
        if ( v21 != 2 )
          wil::details::in1diag3::Log_Win32Msg(
            retaddr,
            (void *)0x169,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\dir.cpp",
            (const char *)v21,
            (unsigned int)"Failed to set attributes for %ws",
            (const char *)v12);
      }
    }
    v22 = GetProcessHeap();
    HeapFree(v22, 0, v12);
  }
  else
  {
    LODWORD(TempFileName) = wil::details::in1diag3::Log_Hr(
                              retaddr,
                              (void *)0x172,
                              (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\dir.cpp",
                              (const char *)0x8007000ELL,
                              dwCreationDisposition);
  }
  return (unsigned int)TempFileName;
}

```

## disassembly

```asm
0x18000c25c  push    rbx
0x18000c25e  push    rbp
0x18000c25f  push    rdi
0x18000c260  push    r12
0x18000c262  push    r14
0x18000c264  push    r15
0x18000c266  sub     rsp, 58h
0x18000c26a  mov     rbp, rdx
0x18000c26d  mov     [rsp+88h+var_40], 0
0x18000c276  mov     r15d, r8d
0x18000c279  mov     r14, rcx
0x18000c27c  mov     rcx, rbp; unsigned __int16 *
0x18000c27f  lea     r8, [rsp+88h+var_40]; unsigned __int64 *
0x18000c284  mov     edx, 7FFFFFFFh; unsigned __int64
0x18000c289  mov     r12d, r9d
0x18000c28c  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000c291  mov     rdi, [rsp+88h+var_40]
0x18000c296  add     rdi, 2Dh ; '-'
0x18000c29a  call    cs:__imp_GetProcessHeap
0x18000c2a0  lea     r8, [rdi+rdi]; dwBytes
0x18000c2a4  mov     edx, 8; dwFlags
0x18000c2a9  mov     rcx, rax; hHeap
0x18000c2ac  call    cs:__imp_HeapAlloc
0x18000c2b2  mov     rbx, rax
0x18000c2b5  test    rax, rax
0x18000c2b8  jz      loc_18000C51D
0x18000c2be  mov     r8, rdi; unsigned __int16 *
0x18000c2c1  mov     rdx, rax; unsigned __int16 *
0x18000c2c4  mov     rcx, rbp; this
0x18000c2c7  call    ?_GetTempFileName@proflib@@YAJPEBGPEAG_K@Z; proflib::_GetTempFileName(ushort const *,ushort *,unsigned __int64)
0x18000c2cc  mov     rcx, [rsp+88h]; this
0x18000c2d4  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000c2db  mov     edi, eax
0x18000c2dd  mov     qword ptr [rsp+88h+dwFlagsAndAttributes], rbp; char *
0x18000c2e2  lea     rax, aGettempfilenam; "_GetTempFileName failed for <%ws>."
0x18000c2e9  mov     r9d, edi; char *
0x18000c2ec  mov     edx, 12Bh; void *
0x18000c2f1  mov     qword ptr [rsp+88h+dwCreationDisposition], rax; int
0x18000c2f6  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000c2fb  test    eax, eax
0x18000c2fd  js      loc_18000C507
0x18000c303  neg     r15d
0x18000c306  mov     [rsp+88h+var_48], 0
0x18000c30e  lea     r8, _CopyProgressRoutine
0x18000c315  mov     rdx, rbx
0x18000c318  sbb     eax, eax
0x18000c31a  mov     rcx, r14
0x18000c31d  and     eax, 0FFFFFBF0h
0x18000c322  xor     r9d, r9d
0x18000c325  add     eax, 610h
0x18000c32a  mov     [rsp+88h+dwFlagsAndAttributes], eax
0x18000c32e  lea     rax, [rsp+88h+var_48]
0x18000c333  mov     qword ptr [rsp+88h+dwCreationDisposition], rax
0x18000c338  call    cs:__imp_PrivCopyFileExW
0x18000c33e  mov     r15d, 80h
0x18000c344  test    eax, eax
0x18000c346  jz      loc_18000C43B
0x18000c34c  mov     dword ptr [rsp+88h+var_40], 0
0x18000c354  test    r12d, r12d
0x18000c357  jz      short loc_18000C39E
0x18000c359  mov     [rsp+88h+hTemplateFile], 0; hTemplateFile
0x18000c362  xor     r9d, r9d; lpSecurityAttributes
0x18000c365  mov     [rsp+88h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x18000c36a  xor     r8d, r8d; dwShareMode
0x18000c36d  mov     edx, 40000000h; dwDesiredAccess
0x18000c372  mov     [rsp+88h+dwCreationDisposition], 3; dwCreationDisposition
0x18000c37a  mov     rcx, rbx; lpFileName
0x18000c37d  call    cs:__imp_CreateFileW
0x18000c383  mov     rdi, rax
0x18000c386  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000c38a  jz      short loc_18000C39E
0x18000c38c  mov     rcx, rax; hFile
0x18000c38f  call    cs:__imp_FlushFileBuffers
0x18000c395  mov     rcx, rdi; hObject
0x18000c398  call    cs:__imp_CloseHandle
0x18000c39e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18000c3a5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18000c3aa  test    al, al
0x18000c3ac  jz      short loc_18000C3C9
0x18000c3ae  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 8
0x18000c3b5  jz      short loc_18000C3C9
0x18000c3b7  mov     r9, rbx
0x18000c3ba  lea     rdx, EVENT_COPY_RUP_FILE_COPY_SUCCEEDED
0x18000c3c1  mov     r8, r14
0x18000c3c4  call    McTemplateU0zz_EventWriteTransfer
0x18000c3c9  lea     r8, [rsp+88h+var_40]
0x18000c3ce  mov     rdx, rbp; char *
0x18000c3d1  mov     rcx, rbx; char *
0x18000c3d4  call    _RenameFile
0x18000c3d9  mov     rcx, [rsp+88h]; this
0x18000c3e1  lea     rdx, aFailedToRename; "Failed to rename %ws to %ws"
0x18000c3e8  mov     [rsp+88h+hTemplateFile], rbp
0x18000c3ed  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000c3f4  mov     qword ptr [rsp+88h+dwFlagsAndAttributes], rbx; char *
0x18000c3f9  mov     r9d, eax; char *
0x18000c3fc  mov     qword ptr [rsp+88h+dwCreationDisposition], rdx; int
0x18000c401  mov     edx, 150h; void *
0x18000c406  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000c40b  mov     edi, eax
0x18000c40d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18000c414  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18000c419  test    al, al
0x18000c41b  jz      short loc_18000C481
0x18000c41d  test    edi, edi
0x18000c41f  js      short loc_18000C481
0x18000c421  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 8
0x18000c428  jz      short loc_18000C481
0x18000c42a  mov     r8, rbp
0x18000c42d  lea     rdx, EVENT_COPY_RUP_FILE_RENAME_SUCCEEDED
0x18000c434  call    McTemplateU0z_EventWriteTransfer
0x18000c439  jmp     short loc_18000C481
0x18000c43b  call    cs:__imp_GetLastError
0x18000c441  test    eax, eax
0x18000c443  jle     short loc_18000C44D
0x18000c445  movzx   eax, ax
0x18000c448  or      eax, 80070000h
0x18000c44d  mov     rcx, [rsp+88h]; this
0x18000c455  lea     r8, aFailedToCopyWs; "Failed to copy %ws to %ws"
0x18000c45c  mov     [rsp+88h+hTemplateFile], rbx
0x18000c461  mov     r9d, eax; char *
0x18000c464  mov     qword ptr [rsp+88h+dwFlagsAndAttributes], r14; char *
0x18000c469  mov     edx, 15Ch; void *
0x18000c46e  mov     qword ptr [rsp+88h+dwCreationDisposition], r8; int
0x18000c473  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000c47a  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000c47f  mov     edi, eax
0x18000c481  mov     edx, r15d; dwFileAttributes
0x18000c484  mov     rcx, rbx; lpFileName
0x18000c487  call    cs:__imp_SetFileAttributesW
0x18000c48d  test    eax, eax
0x18000c48f  jz      short loc_18000C4CF
0x18000c491  mov     rcx, rbx; lpFileName
0x18000c494  call    cs:__imp_DeleteFileW
0x18000c49a  mov     rcx, [rsp+88h]; this
0x18000c4a2  lea     rdx, aFailedToDelete; "Failed to delete %ws"
0x18000c4a9  test    eax, eax
0x18000c4ab  mov     qword ptr [rsp+88h+dwFlagsAndAttributes], rbx; char *
0x18000c4b0  mov     qword ptr [rsp+88h+dwCreationDisposition], rdx; bool
0x18000c4b5  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000c4bc  setz    al
0x18000c4bf  mov     edx, 162h; void *
0x18000c4c4  movzx   r9d, al; char *
0x18000c4c8  call    ?Log_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Log_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x18000c4cd  jmp     short loc_18000C507
0x18000c4cf  call    cs:__imp_GetLastError
0x18000c4d5  cmp     eax, 2
0x18000c4d8  jz      short loc_18000C507
0x18000c4da  mov     rcx, [rsp+88h]; this
0x18000c4e2  lea     rdx, aFailedToSetAtt; "Failed to set attributes for %ws"
0x18000c4e9  mov     qword ptr [rsp+88h+dwFlagsAndAttributes], rbx; char *
0x18000c4ee  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000c4f5  mov     qword ptr [rsp+88h+dwCreationDisposition], rdx; unsigned int
0x18000c4fa  mov     r9d, eax; char *
0x18000c4fd  mov     edx, 169h; void *
0x18000c502  call    ?Log_Win32Msg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18000c507  call    cs:__imp_GetProcessHeap
0x18000c50d  mov     r8, rbx; lpMem
0x18000c510  xor     edx, edx; dwFlags
0x18000c512  mov     rcx, rax; hHeap
0x18000c515  call    cs:__imp_HeapFree
0x18000c51b  jmp     short loc_18000C53E
0x18000c51d  mov     rcx, [rsp+88h]; this
0x18000c525  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000c52c  mov     r9d, 8007000Eh; char *
0x18000c532  mov     edx, 172h; void *
0x18000c537  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18000c53c  mov     edi, eax
0x18000c53e  mov     eax, edi
0x18000c540  add     rsp, 58h
0x18000c544  pop     r15
0x18000c546  pop     r14
0x18000c548  pop     r12
0x18000c54a  pop     rdi
0x18000c54b  pop     rbp
0x18000c54c  pop     rbx
0x18000c54d  retn
```
