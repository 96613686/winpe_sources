# ReconcileFile(ushort const *,ushort const *,ulong,_FILETIME *,_FILETIME *,int)

- ea: `0x180008dd8`
- end: `0x180008fd2`
- name: `?ReconcileFile@@YAHPEBG0KPEAU_FILETIME@@1H@Z`
- size: `506`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpFileName@<rcx>, LPCWSTR@<rdx>, unsigned int@<r8d>, struct _FILETIME *@<r9>, struct _FILETIME *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180008d00`
- `0x18000ab88`

## callees

- `0x180008dd8`
- `0x18000cdc4`
- `0x18000da4c`
- `0x18000de10`
- `0x18000e640`
- `0x180019404`
- `0x18001b8a8`
- `0x18001bcc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008fa8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008fa8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008eea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008eea`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180008f18`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180008f18`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180008e73`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180008eda`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180008e73`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180008eda`

## string_xrefs

- `0x180008e9a`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`

## pseudocode

```c
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
0x180008dd8  push    rbp
0x180008dda  push    rbx
0x180008ddb  push    rsi
0x180008ddc  push    rdi
0x180008ddd  push    r12
0x180008ddf  push    r14
0x180008de1  push    r15
0x180008de3  mov     rbp, rsp
0x180008de6  sub     rsp, 70h
0x180008dea  mov     rax, cs:__security_cookie
0x180008df1  xor     rax, rsp
0x180008df4  mov     [rbp+var_8], rax
0x180008df8  mov     r14, [rbp+arg_20]
0x180008dfc  xor     eax, eax
0x180008dfe  xorps   xmm0, xmm0
0x180008e01  mov     [rbp+var_10], eax
0x180008e04  movups  [rbp+FileInformation], xmm0
0x180008e08  mov     qword ptr [rbp+FileTime1.dwLowDateTime], rax
0x180008e0c  mov     rbx, r9
0x180008e0f  movups  [rbp+var_20], xmm0
0x180008e13  mov     qword ptr [rbp+FileTime2.dwLowDateTime], rax
0x180008e17  mov     esi, r8d
0x180008e1a  mov     r15, rdx
0x180008e1d  mov     r12, rcx
0x180008e20  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x180008e27  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x180008e2c  test    al, al
0x180008e2e  jz      short loc_180008E4F
0x180008e30  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 8
0x180008e37  jz      short loc_180008E4F
0x180008e39  mov     r9, r15
0x180008e3c  mov     [rsp+70h+var_50], esi; unsigned int
0x180008e40  mov     r8, r12
0x180008e43  lea     rdx, EVENT_RECONCILE_FILE_START
0x180008e4a  call    McTemplateU0zzd_EventWriteTransfer
0x180008e4f  test    sil, 1
0x180008e53  jnz     loc_180008F4E
0x180008e59  xor     edi, edi
0x180008e5b  test    rbx, rbx
0x180008e5e  jz      short loc_180008E6A
0x180008e60  mov     eax, [rbx]
0x180008e62  mov     [rbp+FileTime1.dwLowDateTime], eax
0x180008e65  mov     eax, [rbx+4]
0x180008e68  jmp     short loc_180008EB7
0x180008e6a  lea     r8, [rbp+FileInformation]; lpFileInformation
0x180008e6e  xor     edx, edx; fInfoLevelId
0x180008e70  mov     rcx, r12; lpFileName
0x180008e73  call    cs:__imp_GetFileAttributesExW
0x180008e7a  nop     dword ptr [rax+rax+00h]
0x180008e7f  test    eax, eax
0x180008e81  jnz     short loc_180008EAE
0x180008e83  call    cs:__imp_GetLastError
0x180008e8a  nop     dword ptr [rax+rax+00h]
0x180008e8f  mov     ebx, eax
0x180008e91  mov     edx, 7F2h; void *
0x180008e96  mov     rcx, [rbp+38h]; this
0x180008e9a  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x180008ea1  mov     r9d, eax; char *
0x180008ea4  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180008ea9  jmp     loc_180008F7B
0x180008eae  mov     eax, dword ptr [rbp+var_20+4]
0x180008eb1  mov     [rbp+FileTime1.dwLowDateTime], eax
0x180008eb4  mov     eax, dword ptr [rbp+var_20+8]
0x180008eb7  mov     [rbp+FileTime1.dwHighDateTime], eax
0x180008eba  bt      esi, 17h
0x180008ebe  jnb     short loc_180008ED1
0x180008ec0  test    r14, r14
0x180008ec3  jz      short loc_180008ED1
0x180008ec5  mov     eax, [r14]
0x180008ec8  mov     [rbp+FileTime2.dwLowDateTime], eax
0x180008ecb  mov     eax, [r14+4]
0x180008ecf  jmp     short loc_180008F0D
0x180008ed1  lea     r8, [rbp+FileInformation]; lpFileInformation
0x180008ed5  xor     edx, edx; fInfoLevelId
0x180008ed7  mov     rcx, r15; lpFileName
0x180008eda  call    cs:__imp_GetFileAttributesExW
0x180008ee1  nop     dword ptr [rax+rax+00h]
0x180008ee6  test    eax, eax
0x180008ee8  jnz     short loc_180008F04
0x180008eea  call    cs:__imp_GetLastError
0x180008ef1  nop     dword ptr [rax+rax+00h]
0x180008ef6  mov     ebx, eax
0x180008ef8  cmp     eax, 2
0x180008efb  jz      short loc_180008F4E
0x180008efd  mov     edx, 819h
0x180008f02  jmp     short loc_180008E96
0x180008f04  mov     eax, dword ptr [rbp+var_20+4]
0x180008f07  mov     [rbp+FileTime2.dwLowDateTime], eax
0x180008f0a  mov     eax, dword ptr [rbp+var_20+8]
0x180008f0d  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x180008f11  mov     [rbp+FileTime2.dwHighDateTime], eax
0x180008f14  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x180008f18  call    cs:__imp_CompareFileTime
0x180008f1f  nop     dword ptr [rax+rax+00h]
0x180008f24  cmp     eax, 1
0x180008f27  jz      short loc_180008F4E
0x180008f29  cmp     eax, 0FFFFFFFFh
0x180008f2c  jnz     short loc_180008F47
0x180008f2e  test    sil, 10h
0x180008f32  jnz     short loc_180008F4E
0x180008f34  lea     r9, [rbp+FileTime2]; struct _FILETIME *
0x180008f38  mov     r8, r15; unsigned __int16 *
0x180008f3b  lea     rdx, [rbp+FileTime1]; lpFileTime
0x180008f3f  mov     rcx, r12; unsigned __int16 *
0x180008f42  call    ?_WriteConflictEvents@@YAXPEBGPEAU_FILETIME@@01@Z; _WriteConflictEvents(ushort const *,_FILETIME *,ushort const *,_FILETIME *)
0x180008f47  xor     ebx, ebx
0x180008f49  lea     edi, [rbx+1]
0x180008f4c  jmp     short loc_180008F7B
0x180008f4e  mov     r9d, [rbp+arg_28]; int
0x180008f52  and     esi, 8000h
0x180008f58  mov     r8d, esi; int
0x180008f5b  mov     rdx, r15; char *
0x180008f5e  mov     rcx, r12; char *
0x180008f61  call    ?CopyRupFile@@YAJPEBG0HH@Z; CopyRupFile(ushort const *,ushort const *,int,int)
0x180008f66  xor     ebx, ebx
0x180008f68  movzx   edx, ax
0x180008f6b  mov     edi, eax
0x180008f6d  sar     edi, 1Fh
0x180008f70  and     edi, 0FFFFFFFEh
0x180008f73  add     edi, 2
0x180008f76  test    eax, eax
0x180008f78  cmovs   ebx, edx
0x180008f7b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x180008f82  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x180008f87  test    al, al
0x180008f89  jz      short loc_180008FA6
0x180008f8b  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 8
0x180008f92  jz      short loc_180008FA6
0x180008f94  mov     r9d, ebx
0x180008f97  lea     rdx, EVENT_RECONCILE_FILE_END
0x180008f9e  mov     r8d, edi
0x180008fa1  call    McTemplateU0qd_EventWriteTransfer
0x180008fa6  mov     ecx, ebx; dwErrCode
0x180008fa8  call    cs:__imp_SetLastError
0x180008faf  nop     dword ptr [rax+rax+00h]
0x180008fb4  mov     eax, edi
0x180008fb6  mov     rcx, [rbp+var_8]
0x180008fba  xor     rcx, rsp; StackCookie
0x180008fbd  call    __security_check_cookie
0x180008fc2  add     rsp, 70h
0x180008fc6  pop     r15
0x180008fc8  pop     r14
0x180008fca  pop     r12
0x180008fcc  pop     rdi
0x180008fcd  pop     rsi
0x180008fce  pop     rbx
0x180008fcf  pop     rbp
0x180008fd0  retn
```
