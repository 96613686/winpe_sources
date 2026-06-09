# ReconcileFile(ushort const *,ushort const *,ulong,_FILETIME *,_FILETIME *,int)

- ea: `0x1800085b0`
- end: `0x180008785`
- name: `?ReconcileFile@@YAHPEBG0KPEAU_FILETIME@@1H@Z`
- size: `469`
- prototype: `__int64 __fastcall(WCHAR *lpFileName, unsigned __int16 *, int, struct _FILETIME *, struct _FILETIME *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800084f0`
- `0x18000a200`

## callees

- `0x1800085b0`
- `0x18000c25c`
- `0x18000cdf0`
- `0x18000d198`
- `0x18000d9b0`
- `0x180017a94`
- `0x180019df0`
- `0x18001a200`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008762`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008762`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008655`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800086b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008655`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800086b0`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800086d8`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800086d8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18000864b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800086a6`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18000864b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800086a6`

## string_xrefs

- `0x180008666`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ReconcileFile(
        WCHAR *lpFileName,
        unsigned __int16 *a2,
        int a3,
        struct _FILETIME *a4,
        struct _FILETIME *a5,
        int a6)
{
  int v10; // ecx
  unsigned int v11; // edi
  DWORD dwHighDateTime; // eax
  DWORD LastError; // eax
  DWORD v14; // ebx
  __int64 v15; // rdx
  DWORD v16; // eax
  LONG v17; // eax
  int v18; // eax
  __int64 v19; // rcx
  unsigned int v21; // [rsp+20h] [rbp-50h]
  FILETIME FileTime2; // [rsp+30h] [rbp-40h] BYREF
  FILETIME FileTime1; // [rsp+38h] [rbp-38h] BYREF
  __int128 FileInformation; // [rsp+40h] [rbp-30h] BYREF
  __int128 v25; // [rsp+50h] [rbp-20h]
  int v26; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  v26 = 0;
  FileInformation = 0;
  FileTime1 = 0;
  v25 = 0;
  FileTime2 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
    && (Microsoft_Windows_User_Profiles_GeneralEnableBits & 8) != 0 )
  {
    McTemplateU0zzd_EventWriteTransfer(
      v10,
      (unsigned int)EVENT_RECONCILE_FILE_START,
      (_DWORD)lpFileName,
      (_DWORD)a2,
      a3);
  }
  if ( (a3 & 1) == 0 )
  {
    v11 = 0;
    if ( a4 )
    {
      FileTime1.dwLowDateTime = a4->dwLowDateTime;
      dwHighDateTime = a4->dwHighDateTime;
    }
    else
    {
      if ( !GetFileAttributesExW(lpFileName, GetFileExInfoStandard, &FileInformation) )
      {
        LastError = GetLastError();
        v14 = LastError;
        v15 = 2034;
LABEL_9:
        wil::details::in1diag3::Log_Win32(
          retaddr,
          (void *)v15,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
          (const char *)LastError,
          v21);
        goto LABEL_25;
      }
      FileTime1.dwLowDateTime = DWORD1(v25);
      dwHighDateTime = DWORD2(v25);
    }
    FileTime1.dwHighDateTime = dwHighDateTime;
    if ( (a3 & 0x800000) != 0 && a5 )
    {
      FileTime2.dwLowDateTime = a5->dwLowDateTime;
      v16 = a5->dwHighDateTime;
      goto LABEL_18;
    }
    if ( GetFileAttributesExW(a2, GetFileExInfoStandard, &FileInformation) )
    {
      FileTime2.dwLowDateTime = DWORD1(v25);
      v16 = DWORD2(v25);
LABEL_18:
      FileTime2.dwHighDateTime = v16;
      v17 = CompareFileTime(&FileTime1, &FileTime2);
      if ( v17 != 1 )
      {
        if ( v17 != -1 )
        {
LABEL_22:
          v14 = 0;
          v11 = 1;
          goto LABEL_25;
        }
        if ( (a3 & 0x10) == 0 )
        {
          _WriteConflictEvents(lpFileName, &FileTime1, a2, &FileTime2);
          goto LABEL_22;
        }
      }
      goto LABEL_23;
    }
    LastError = GetLastError();
    v14 = LastError;
    if ( LastError != 2 )
    {
      v15 = 2073;
      goto LABEL_9;
    }
  }
LABEL_23:
  v18 = CopyRupFile((char *)lpFileName, (char *)a2, (unsigned __int16)a3 & 0x8000, a6);
  v14 = 0;
  v11 = ((v18 >> 31) & 0xFFFFFFFE) + 2;
  if ( v18 < 0 )
    v14 = (unsigned __int16)v18;
LABEL_25:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
    && (Microsoft_Windows_User_Profiles_GeneralEnableBits & 8) != 0 )
  {
    McTemplateU0qd_EventWriteTransfer(v19, EVENT_RECONCILE_FILE_END, v11, v14);
  }
  SetLastError(v14);
  return v11;
}

```

## disassembly

```asm
0x1800085b0  push    rbp
0x1800085b2  push    rbx
0x1800085b3  push    rsi
0x1800085b4  push    rdi
0x1800085b5  push    r12
0x1800085b7  push    r14
0x1800085b9  push    r15
0x1800085bb  mov     rbp, rsp
0x1800085be  sub     rsp, 70h
0x1800085c2  mov     rax, cs:__security_cookie
0x1800085c9  xor     rax, rsp
0x1800085cc  mov     [rbp+var_8], rax
0x1800085d0  mov     r14, [rbp+arg_20]
0x1800085d4  xor     eax, eax
0x1800085d6  xorps   xmm0, xmm0
0x1800085d9  mov     [rbp+var_10], eax
0x1800085dc  movups  [rbp+FileInformation], xmm0
0x1800085e0  mov     qword ptr [rbp+FileTime1.dwLowDateTime], rax
0x1800085e4  mov     rbx, r9
0x1800085e7  movups  [rbp+var_20], xmm0
0x1800085eb  mov     qword ptr [rbp+FileTime2.dwLowDateTime], rax
0x1800085ef  mov     esi, r8d
0x1800085f2  mov     r15, rdx
0x1800085f5  mov     r12, rcx
0x1800085f8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x1800085ff  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x180008604  test    al, al
0x180008606  jz      short loc_180008627
0x180008608  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 8
0x18000860f  jz      short loc_180008627
0x180008611  mov     r9, r15
0x180008614  mov     [rsp+70h+var_50], esi; unsigned int
0x180008618  mov     r8, r12
0x18000861b  lea     rdx, EVENT_RECONCILE_FILE_START
0x180008622  call    McTemplateU0zzd_EventWriteTransfer
0x180008627  test    sil, 1
0x18000862b  jnz     loc_180008708
0x180008631  xor     edi, edi
0x180008633  test    rbx, rbx
0x180008636  jz      short loc_180008642
0x180008638  mov     eax, [rbx]
0x18000863a  mov     [rbp+FileTime1.dwLowDateTime], eax
0x18000863d  mov     eax, [rbx+4]
0x180008640  jmp     short loc_180008683
0x180008642  lea     r8, [rbp+FileInformation]; lpFileInformation
0x180008646  xor     edx, edx; fInfoLevelId
0x180008648  mov     rcx, r12; lpFileName
0x18000864b  call    cs:__imp_GetFileAttributesExW
0x180008651  test    eax, eax
0x180008653  jnz     short loc_18000867A
0x180008655  call    cs:__imp_GetLastError
0x18000865b  mov     ebx, eax
0x18000865d  mov     edx, 7F2h; void *
0x180008662  mov     rcx, [rbp+38h]; this
0x180008666  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x18000866d  mov     r9d, eax; char *
0x180008670  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180008675  jmp     loc_180008735
0x18000867a  mov     eax, dword ptr [rbp+var_20+4]
0x18000867d  mov     [rbp+FileTime1.dwLowDateTime], eax
0x180008680  mov     eax, dword ptr [rbp+var_20+8]
0x180008683  mov     [rbp+FileTime1.dwHighDateTime], eax
0x180008686  bt      esi, 17h
0x18000868a  jnb     short loc_18000869D
0x18000868c  test    r14, r14
0x18000868f  jz      short loc_18000869D
0x180008691  mov     eax, [r14]
0x180008694  mov     [rbp+FileTime2.dwLowDateTime], eax
0x180008697  mov     eax, [r14+4]
0x18000869b  jmp     short loc_1800086CD
0x18000869d  lea     r8, [rbp+FileInformation]; lpFileInformation
0x1800086a1  xor     edx, edx; fInfoLevelId
0x1800086a3  mov     rcx, r15; lpFileName
0x1800086a6  call    cs:__imp_GetFileAttributesExW
0x1800086ac  test    eax, eax
0x1800086ae  jnz     short loc_1800086C4
0x1800086b0  call    cs:__imp_GetLastError
0x1800086b6  mov     ebx, eax
0x1800086b8  cmp     eax, 2
0x1800086bb  jz      short loc_180008708
0x1800086bd  mov     edx, 819h
0x1800086c2  jmp     short loc_180008662
0x1800086c4  mov     eax, dword ptr [rbp+var_20+4]
0x1800086c7  mov     [rbp+FileTime2.dwLowDateTime], eax
0x1800086ca  mov     eax, dword ptr [rbp+var_20+8]
0x1800086cd  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x1800086d1  mov     [rbp+FileTime2.dwHighDateTime], eax
0x1800086d4  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x1800086d8  call    cs:__imp_CompareFileTime
0x1800086de  cmp     eax, 1
0x1800086e1  jz      short loc_180008708
0x1800086e3  cmp     eax, 0FFFFFFFFh
0x1800086e6  jnz     short loc_180008701
0x1800086e8  test    sil, 10h
0x1800086ec  jnz     short loc_180008708
0x1800086ee  lea     r9, [rbp+FileTime2]; struct _FILETIME *
0x1800086f2  mov     r8, r15; unsigned __int16 *
0x1800086f5  lea     rdx, [rbp+FileTime1]; lpFileTime
0x1800086f9  mov     rcx, r12; unsigned __int16 *
0x1800086fc  call    ?_WriteConflictEvents@@YAXPEBGPEAU_FILETIME@@01@Z; _WriteConflictEvents(ushort const *,_FILETIME *,ushort const *,_FILETIME *)
0x180008701  xor     ebx, ebx
0x180008703  lea     edi, [rbx+1]
0x180008706  jmp     short loc_180008735
0x180008708  mov     r9d, [rbp+arg_28]; int
0x18000870c  and     esi, 8000h
0x180008712  mov     r8d, esi; int
0x180008715  mov     rdx, r15; char *
0x180008718  mov     rcx, r12; char *
0x18000871b  call    ?CopyRupFile@@YAJPEBG0HH@Z; CopyRupFile(ushort const *,ushort const *,int,int)
0x180008720  xor     ebx, ebx
0x180008722  movzx   edx, ax
0x180008725  mov     edi, eax
0x180008727  sar     edi, 1Fh
0x18000872a  and     edi, 0FFFFFFFEh
0x18000872d  add     edi, 2
0x180008730  test    eax, eax
0x180008732  cmovs   ebx, edx
0x180008735  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18000873c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x180008741  test    al, al
0x180008743  jz      short loc_180008760
0x180008745  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 8
0x18000874c  jz      short loc_180008760
0x18000874e  mov     r9d, ebx
0x180008751  lea     rdx, EVENT_RECONCILE_FILE_END
0x180008758  mov     r8d, edi
0x18000875b  call    McTemplateU0qd_EventWriteTransfer
0x180008760  mov     ecx, ebx; dwErrCode
0x180008762  call    cs:__imp_SetLastError
0x180008768  mov     eax, edi
0x18000876a  mov     rcx, [rbp+var_8]
0x18000876e  xor     rcx, rsp; StackCookie
0x180008771  call    __security_check_cookie
0x180008776  add     rsp, 70h
0x18000877a  pop     r15
0x18000877c  pop     r14
0x18000877e  pop     r12
0x180008780  pop     rdi
0x180008781  pop     rsi
0x180008782  pop     rbx
0x180008783  pop     rbp
0x180008784  retn
```
