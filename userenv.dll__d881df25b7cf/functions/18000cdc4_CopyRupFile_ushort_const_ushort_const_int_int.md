# CopyRupFile(ushort const *,ushort const *,int,int)

- ea: `0x18000cdc4`
- end: `0x18000d0ff`
- name: `?CopyRupFile@@YAJPEBG0HH@Z`
- size: `827`
- prototype: `__int64 __fastcall(char *, char *, int, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180008dd8`

## callees

- `0x180007f80`
- `0x180009eac`
- `0x18000a1b4`
- `0x18000cdc4`
- `0x18000d108`
- `0x18000d2f8`
- `0x18000dc50`
- `0x180019404`
- `0x18001b9c4`
- `0x18001bc04`
- `0x18001c64c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d0bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d0bf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ce1a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ce1a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ce02`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d0ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ce02`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d0ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cfc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d06d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cfc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d06d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cf1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cf1e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000cef7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000cef7`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18000cf0f`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18000cf0f`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000d019`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000d019`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000d02c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000d02c`
- `api-ms-win-core-kernel32-private-l1-1-1!PrivCopyFileExW` at `0x18000ceac`
- `api-ms-win-core-kernel32-private-l1-1-1!PrivCopyFileExW` at `0x18000ceac`

## string_xrefs

- `0x18000ce48`: `onecore\ds\security\gina\profile\proflib\dir.cpp`
- `0x18000cf79`: `onecore\ds\security\gina\profile\proflib\dir.cpp`
- `0x18000d005`: `onecore\ds\security\gina\profile\proflib\dir.cpp`
- `0x18000d053`: `onecore\ds\security\gina\profile\proflib\dir.cpp`
- `0x18000d092`: `onecore\ds\security\gina\profile\proflib\dir.cpp`
- `0x18000d0d5`: `onecore\ds\security\gina\profile\proflib\dir.cpp`
- `0x18000ce56`: `_GetTempFileName failed for <%ws>.`
- `0x18000cf6d`: `Failed to rename %ws to %ws`
- `0x18000cfe7`: `Failed to copy %ws to %ws`
- `0x18000d040`: `Failed to delete %ws`

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
        v17 = RenameFile(v12, (const WCHAR *)a2, v26);
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
0x18000cdc4  push    rbx
0x18000cdc6  push    rbp
0x18000cdc7  push    rdi
0x18000cdc8  push    r12
0x18000cdca  push    r14
0x18000cdcc  push    r15
0x18000cdce  sub     rsp, 58h
0x18000cdd2  mov     rbp, rdx
0x18000cdd5  mov     [rsp+88h+var_40], 0
0x18000cdde  mov     r15d, r8d
0x18000cde1  mov     r14, rcx
0x18000cde4  mov     rcx, rbp; unsigned __int16 *
0x18000cde7  lea     r8, [rsp+88h+var_40]; unsigned __int64 *
0x18000cdec  mov     edx, 7FFFFFFFh; unsigned __int64
0x18000cdf1  mov     r12d, r9d
0x18000cdf4  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000cdf9  mov     rdi, [rsp+88h+var_40]
0x18000cdfe  add     rdi, 2Dh ; '-'
0x18000ce02  call    cs:__imp_GetProcessHeap
0x18000ce09  nop     dword ptr [rax+rax+00h]
0x18000ce0e  lea     r8, [rdi+rdi]; dwBytes
0x18000ce12  mov     edx, 8; dwFlags
0x18000ce17  mov     rcx, rax; hHeap
0x18000ce1a  call    cs:__imp_HeapAlloc
0x18000ce21  nop     dword ptr [rax+rax+00h]
0x18000ce26  mov     rbx, rax
0x18000ce29  test    rax, rax
0x18000ce2c  jz      loc_18000D0CD
0x18000ce32  mov     r8, rdi; unsigned __int16 *
0x18000ce35  mov     rdx, rax; unsigned __int16 *
0x18000ce38  mov     rcx, rbp; this
0x18000ce3b  call    ?_GetTempFileName@proflib@@YAJPEBGPEAG_K@Z; proflib::_GetTempFileName(ushort const *,ushort *,unsigned __int64)
0x18000ce40  mov     rcx, [rsp+88h]; this
0x18000ce48  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000ce4f  mov     edi, eax
0x18000ce51  mov     qword ptr [rsp+88h+dwFlagsAndAttributes], rbp; char *
0x18000ce56  lea     rax, aGettempfilenam; "_GetTempFileName failed for <%ws>."
0x18000ce5d  mov     r9d, edi; char *
0x18000ce60  mov     edx, 12Bh; void *
0x18000ce65  mov     qword ptr [rsp+88h+dwCreationDisposition], rax; int
0x18000ce6a  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000ce6f  test    eax, eax
0x18000ce71  js      loc_18000D0AB
0x18000ce77  neg     r15d
0x18000ce7a  mov     [rsp+88h+var_48], 0
0x18000ce82  lea     r8, _CopyProgressRoutine
0x18000ce89  mov     rdx, rbx
0x18000ce8c  sbb     eax, eax
0x18000ce8e  mov     rcx, r14
0x18000ce91  and     eax, 0FFFFFBF0h
0x18000ce96  xor     r9d, r9d
0x18000ce99  add     eax, 610h
0x18000ce9e  mov     [rsp+88h+dwFlagsAndAttributes], eax
0x18000cea2  lea     rax, [rsp+88h+var_48]
0x18000cea7  mov     qword ptr [rsp+88h+dwCreationDisposition], rax
0x18000ceac  call    cs:__imp_PrivCopyFileExW
0x18000ceb3  nop     dword ptr [rax+rax+00h]
0x18000ceb8  mov     r15d, 80h
0x18000cebe  test    eax, eax
0x18000cec0  jz      loc_18000CFC7
0x18000cec6  mov     dword ptr [rsp+88h+var_40], 0
0x18000cece  test    r12d, r12d
0x18000ced1  jz      short loc_18000CF2A
0x18000ced3  mov     [rsp+88h+hTemplateFile], 0; hTemplateFile
0x18000cedc  xor     r9d, r9d; lpSecurityAttributes
0x18000cedf  mov     [rsp+88h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x18000cee4  xor     r8d, r8d; dwShareMode
0x18000cee7  mov     edx, 40000000h; dwDesiredAccess
0x18000ceec  mov     [rsp+88h+dwCreationDisposition], 3; dwCreationDisposition
0x18000cef4  mov     rcx, rbx; lpFileName
0x18000cef7  call    cs:__imp_CreateFileW
0x18000cefe  nop     dword ptr [rax+rax+00h]
0x18000cf03  mov     rdi, rax
0x18000cf06  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000cf0a  jz      short loc_18000CF2A
0x18000cf0c  mov     rcx, rax; hFile
0x18000cf0f  call    cs:__imp_FlushFileBuffers
0x18000cf16  nop     dword ptr [rax+rax+00h]
0x18000cf1b  mov     rcx, rdi; hObject
0x18000cf1e  call    cs:__imp_CloseHandle
0x18000cf25  nop     dword ptr [rax+rax+00h]
0x18000cf2a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18000cf31  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18000cf36  test    al, al
0x18000cf38  jz      short loc_18000CF55
0x18000cf3a  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 8
0x18000cf41  jz      short loc_18000CF55
0x18000cf43  mov     r9, rbx
0x18000cf46  lea     rdx, EVENT_COPY_RUP_FILE_COPY_SUCCEEDED
0x18000cf4d  mov     r8, r14
0x18000cf50  call    McTemplateU0zz_EventWriteTransfer
0x18000cf55  lea     r8, [rsp+88h+var_40]
0x18000cf5a  mov     rdx, rbp; char *
0x18000cf5d  mov     rcx, rbx; char *
0x18000cf60  call    _RenameFile
0x18000cf65  mov     rcx, [rsp+88h]; this
0x18000cf6d  lea     rdx, aFailedToRename; "Failed to rename %ws to %ws"
0x18000cf74  mov     [rsp+88h+hTemplateFile], rbp
0x18000cf79  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000cf80  mov     qword ptr [rsp+88h+dwFlagsAndAttributes], rbx; char *
0x18000cf85  mov     r9d, eax; char *
0x18000cf88  mov     qword ptr [rsp+88h+dwCreationDisposition], rdx; int
0x18000cf8d  mov     edx, 150h; void *
0x18000cf92  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000cf97  mov     edi, eax
0x18000cf99  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18000cfa0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18000cfa5  test    al, al
0x18000cfa7  jz      short loc_18000D013
0x18000cfa9  test    edi, edi
0x18000cfab  js      short loc_18000D013
0x18000cfad  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 8
0x18000cfb4  jz      short loc_18000D013
0x18000cfb6  mov     r8, rbp
0x18000cfb9  lea     rdx, EVENT_COPY_RUP_FILE_RENAME_SUCCEEDED
0x18000cfc0  call    McTemplateU0z_EventWriteTransfer
0x18000cfc5  jmp     short loc_18000D013
0x18000cfc7  call    cs:__imp_GetLastError
0x18000cfce  nop     dword ptr [rax+rax+00h]
0x18000cfd3  test    eax, eax
0x18000cfd5  jle     short loc_18000CFDF
0x18000cfd7  movzx   eax, ax
0x18000cfda  or      eax, 80070000h
0x18000cfdf  mov     rcx, [rsp+88h]; this
0x18000cfe7  lea     r8, aFailedToCopyWs; "Failed to copy %ws to %ws"
0x18000cfee  mov     [rsp+88h+hTemplateFile], rbx
0x18000cff3  mov     r9d, eax; char *
0x18000cff6  mov     qword ptr [rsp+88h+dwFlagsAndAttributes], r14; char *
0x18000cffb  mov     edx, 15Ch; void *
0x18000d000  mov     qword ptr [rsp+88h+dwCreationDisposition], r8; int
0x18000d005  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000d00c  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000d011  mov     edi, eax
0x18000d013  mov     edx, r15d; dwFileAttributes
0x18000d016  mov     rcx, rbx; lpFileName
0x18000d019  call    cs:__imp_SetFileAttributesW
0x18000d020  nop     dword ptr [rax+rax+00h]
0x18000d025  test    eax, eax
0x18000d027  jz      short loc_18000D06D
0x18000d029  mov     rcx, rbx; lpFileName
0x18000d02c  call    cs:__imp_DeleteFileW
0x18000d033  nop     dword ptr [rax+rax+00h]
0x18000d038  mov     rcx, [rsp+88h]; this
0x18000d040  lea     rdx, aFailedToDelete; "Failed to delete %ws"
0x18000d047  test    eax, eax
0x18000d049  mov     qword ptr [rsp+88h+dwFlagsAndAttributes], rbx; char *
0x18000d04e  mov     qword ptr [rsp+88h+dwCreationDisposition], rdx; bool
0x18000d053  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000d05a  setz    al
0x18000d05d  mov     edx, 162h; void *
0x18000d062  movzx   r9d, al; char *
0x18000d066  call    ?Log_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Log_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x18000d06b  jmp     short loc_18000D0AB
0x18000d06d  call    cs:__imp_GetLastError
0x18000d074  nop     dword ptr [rax+rax+00h]
0x18000d079  cmp     eax, 2
0x18000d07c  jz      short loc_18000D0AB
0x18000d07e  mov     rcx, [rsp+88h]; this
0x18000d086  lea     rdx, aFailedToSetAtt; "Failed to set attributes for %ws"
0x18000d08d  mov     qword ptr [rsp+88h+dwFlagsAndAttributes], rbx; char *
0x18000d092  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000d099  mov     qword ptr [rsp+88h+dwCreationDisposition], rdx; unsigned int
0x18000d09e  mov     r9d, eax; char *
0x18000d0a1  mov     edx, 169h; void *
0x18000d0a6  call    ?Log_Win32Msg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18000d0ab  call    cs:__imp_GetProcessHeap
0x18000d0b2  nop     dword ptr [rax+rax+00h]
0x18000d0b7  mov     r8, rbx; lpMem
0x18000d0ba  xor     edx, edx; dwFlags
0x18000d0bc  mov     rcx, rax; hHeap
0x18000d0bf  call    cs:__imp_HeapFree
0x18000d0c6  nop     dword ptr [rax+rax+00h]
0x18000d0cb  jmp     short loc_18000D0EE
0x18000d0cd  mov     rcx, [rsp+88h]; this
0x18000d0d5  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000d0dc  mov     r9d, 8007000Eh; char *
0x18000d0e2  mov     edx, 172h; void *
0x18000d0e7  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18000d0ec  mov     edi, eax
0x18000d0ee  mov     eax, edi
0x18000d0f0  add     rsp, 58h
0x18000d0f4  pop     r15
0x18000d0f6  pop     r14
0x18000d0f8  pop     r12
0x18000d0fa  pop     rdi
0x18000d0fb  pop     rbp
0x18000d0fc  pop     rbx
0x18000d0fd  retn
```
