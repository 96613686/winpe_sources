# SetupClnEstimateFileSize

- ea: `0x1800071a8`
- end: `0x1800074dd`
- name: `SetupClnEstimateFileSize`
- size: `821`
- prototype: `unsigned __int64 __fastcall(__int64, const WCHAR *, unsigned __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800070b0`

## callees

- `0x180003754`
- `0x180003f00`
- `0x1800047ac`
- `0x180006438`
- `0x1800071a8`
- `0x1800083ac`
- `0x18000854c`
- `0x1800131e0`
- `0x180014010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180007455`
- `msvcrt!_wcsnicmp` at `0x180007455`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007241`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007252`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800072fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000730f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007241`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007252`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800072fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000730f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180007219`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180007219`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800072f4`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800072f4`
- `api-ms-win-core-file-l1-1-0!FindFirstFileNameW` at `0x18000740d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileNameW` at `0x18000740d`
- `api-ms-win-core-file-l1-1-0!FindNextFileNameW` at `0x18000747d`
- `api-ms-win-core-file-l1-1-0!FindNextFileNameW` at `0x18000747d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000749f`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000749f`
- `WDSCORE!CurrentIP` at `0x180007249`
- `WDSCORE!CurrentIP` at `0x180007306`
- `WDSCORE!CurrentIP` at `0x180007249`
- `WDSCORE!CurrentIP` at `0x180007306`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800072bd`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800072bd`

## string_xrefs

- `0x18000726a`: `SetupClnEstimateFileSize Could not open file [%s], status: %x`

## pseudocode

```c
unsigned __int64 __fastcall SetupClnEstimateFileSize(__int64 a1, const WCHAR *a2, unsigned __int64 a3)
{
  unsigned __int64 v3; // rbx
  DWORD LastError; // edi
  __int64 v7; // rsi
  signed int v8; // eax
  struct tagLOG_PARTIAL_MSG *v9; // rax
  HANDLE *v10; // rax
  DWORD v11; // edi
  __int64 v12; // rsi
  signed int v13; // eax
  struct tagLOG_PARTIAL_MSG *v14; // rax
  unsigned __int64 v15; // r14
  _QWORD *v16; // rax
  __int64 v17; // r10
  __int64 v18; // r11
  WCHAR *v19; // r9
  HANDLE FirstFileNameW; // rsi
  const wchar_t *v21; // rdx
  const wchar_t *v22; // rcx
  unsigned __int64 v23; // rax
  size_t v24; // r8
  DWORD StringLength; // [rsp+60h] [rbp-49h] BYREF
  void **v28; // [rsp+68h] [rbp-41h] BYREF
  HANDLE FileW; // [rsp+70h] [rbp-39h] BYREF
  _DWORD v30[2]; // [rsp+78h] [rbp-31h] BYREF
  _QWORD v31[2]; // [rsp+80h] [rbp-29h] BYREF
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+90h] [rbp-19h] BYREF

  v3 = a3;
  if ( *(_DWORD *)(a1 + 32) )
    v3 = *(unsigned int *)(a1 + 32) + a3 - 1 - (*(unsigned int *)(a1 + 32) + a3 - 1) % *(unsigned int *)(a1 + 32);
  v28 = &RAII::CAutoCleanup<void *>::`vftable';
  FileW = CreateFileW(a2, 0x80u, 1u, 0, 3u, 0x80u, 0);
  if ( *(_QWORD *)RAII::CAutoCleanupBase<unsigned short *>::operator&((__int64)&v28) == -1 )
  {
    LastError = GetLastError();
    v7 = CurrentIP();
    v8 = GetLastError();
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    v9 = ConstructPartialMsgW(
           50331648,
           "SetupClnEstimateFileSize Could not open file [%s], status: %x",
           (const char *)a2,
           v8);
    WdsSetupLogMessageW(
      v9,
      0,
      L"D",
      0,
      1582,
      L"base\\ntsetup\\setup\\tools\\setupcln\\setupcln.cpp",
      L"SetupClnEstimateFileSize",
      v7,
      LastError,
      0,
      0);
  }
  else
  {
    memset(&FileInformation, 0, sizeof(FileInformation));
    v10 = (HANDLE *)((__int64 (__fastcall *)(void ***))v28[4])(&v28);
    if ( GetFileInformationByHandle(*v10, &FileInformation) )
    {
      v30[0] = FileInformation.nFileIndexLow;
      v30[1] = FileInformation.nFileIndexHigh;
      v15 = std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Hashval(
              a1 + 96,
              (__int64)v30);
      while ( 1 )
      {
        v16 = std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_End(
                (_QWORD *)(a1 + 96),
                v31,
                v15);
        if ( v18 == *v16 )
          break;
        if ( *(_QWORD *)(v18 + 16) == v17 )
        {
          if ( v18 != *(_QWORD *)(a1 + 96) )
          {
            v3 = 0;
            goto LABEL_35;
          }
          break;
        }
      }
      if ( FileInformation.nNumberOfLinks > 1 )
      {
        std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Insert<unsigned __int64 const &,std::_Nil>(
          (__int64 **)(a1 + 96),
          (__int64)v31,
          (__int64)v30);
        if ( *(_QWORD *)(a1 + 72) )
        {
          v19 = *(WCHAR **)(a1 + 80);
          if ( v19 )
          {
            StringLength = *(_DWORD *)(a1 + 88);
            FirstFileNameW = FindFirstFileNameW(a2, 0, &StringLength, v19);
            if ( FirstFileNameW != (HANDLE)-1LL )
            {
              while ( 1 )
              {
                v21 = (const wchar_t *)(*(_QWORD *)(a1 + 72) + 12LL);
                if ( *(_QWORD *)(a1 + 72) == -12 )
                  break;
                v22 = *(const wchar_t **)(a1 + 80);
                if ( !v22 )
                  break;
                v23 = -1;
                do
                  ++v23;
                while ( v22[v23] );
                v24 = -1;
                do
                  ++v24;
                while ( v21[v24] );
                if ( v24 > v23 || _wcsnicmp(v22, v21, v24) != 0 )
                  goto LABEL_33;
                StringLength = *(_DWORD *)(a1 + 88);
                if ( !FindNextFileNameW(FirstFileNameW, &StringLength, *(PWSTR *)(a1 + 80)) )
                  goto LABEL_34;
              }
              NtCurrentTeb()->LastErrorValue = 87;
LABEL_33:
              v3 = 0;
LABEL_34:
              FindClose(FirstFileNameW);
            }
          }
        }
      }
    }
    else
    {
      v11 = GetLastError();
      v12 = CurrentIP();
      v13 = GetLastError();
      if ( v13 > 0 )
        v13 = (unsigned __int16)v13 | 0x80070000;
      v14 = ConstructPartialMsgW(
              50331648,
              "SetupClnEstimateFileSize Could not get file info for [%s], status: %x",
              (const char *)a2,
              v13);
      WdsSetupLogMessageW(
        v14,
        0,
        L"D",
        0,
        1589,
        L"base\\ntsetup\\setup\\tools\\setupcln\\setupcln.cpp",
        L"SetupClnEstimateFileSize",
        v12,
        v11,
        0,
        0);
    }
  }
LABEL_35:
  v28 = &RAII::CAutoCleanup<void *>::`vftable';
  RAII::CleanupInfo<void *>::Release(&FileW);
  return v3;
}

```

## disassembly

```asm
0x1800071a8  mov     [rsp-8+arg_10], rbx
0x1800071ad  push    rbp
0x1800071ae  push    rsi
0x1800071af  push    rdi
0x1800071b0  push    r12
0x1800071b2  push    r13
0x1800071b4  push    r14
0x1800071b6  push    r15
0x1800071b8  lea     rbp, [rsp-27h]
0x1800071bd  sub     rsp, 0D0h
0x1800071c4  mov     rax, cs:__security_cookie
0x1800071cb  xor     rax, rsp
0x1800071ce  mov     [rbp+57h+var_38], rax
0x1800071d2  mov     rbx, r8
0x1800071d5  mov     r15, rdx
0x1800071d8  mov     rdi, rcx
0x1800071db  xor     r12d, r12d
0x1800071de  cmp     [rcx+20h], r12d
0x1800071e2  jz      short loc_1800071F9
0x1800071e4  mov     r8d, [rcx+20h]
0x1800071e8  dec     rbx
0x1800071eb  add     rbx, r8
0x1800071ee  xor     edx, edx
0x1800071f0  mov     rax, rbx
0x1800071f3  div     r8
0x1800071f6  sub     rbx, rdx
0x1800071f9  mov     [rsp+100h+hTemplateFile], r12; hTemplateFile
0x1800071fe  mov     edx, 80h; dwDesiredAccess
0x180007203  mov     [rsp+100h+dwFlagsAndAttributes], edx; dwFlagsAndAttributes
0x180007207  mov     [rsp+100h+dwCreationDisposition], 3; dwCreationDisposition
0x18000720f  xor     r9d, r9d; lpSecurityAttributes
0x180007212  lea     r8d, [rdx-7Fh]; dwShareMode
0x180007216  mov     rcx, r15; lpFileName
0x180007219  call    cs:__imp_CreateFileW
0x18000721f  lea     r13, ??_7?$CAutoCleanup@PEAX@RAII@@6B@; const RAII::CAutoCleanup<void *>::`vftable'
0x180007226  mov     [rbp+57h+var_98], r13
0x18000722a  mov     [rbp+57h+var_90], rax
0x18000722e  lea     rcx, [rbp+57h+var_98]
0x180007232  call    ??I?$CAutoCleanupBase@PEAG@RAII@@UEBAPEBQEAGXZ; RAII::CAutoCleanupBase<ushort *>::operator&(void)
0x180007237  cmp     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x18000723b  jnz     loc_1800072C8
0x180007241  call    cs:__imp_GetLastError
0x180007247  mov     edi, eax
0x180007249  call    cs:__imp_CurrentIP
0x18000724f  mov     rsi, rax
0x180007252  call    cs:__imp_GetLastError
0x180007258  test    eax, eax
0x18000725a  jle     short loc_180007264
0x18000725c  movzx   eax, ax
0x18000725f  or      eax, 80070000h
0x180007264  mov     r9d, eax
0x180007267  mov     r8, r15
0x18000726a  lea     rdx, aSetupclnestima; "SetupClnEstimateFileSize Could not open"...
0x180007271  mov     ecx, 3000000h; unsigned int
0x180007276  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000727b  mov     [rsp+100h+var_B0], r12d
0x180007280  mov     [rsp+100h+var_B8], r12
0x180007285  mov     [rsp+100h+var_C0], edi
0x180007289  mov     [rsp+100h+var_C8], rsi
0x18000728e  lea     rcx, aSetupclnestima_1; "SetupClnEstimateFileSize"
0x180007295  mov     [rsp+100h+hTemplateFile], rcx
0x18000729a  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupcln\\"...
0x1800072a1  mov     qword ptr [rsp+100h+dwFlagsAndAttributes], rcx
0x1800072a6  mov     [rsp+100h+dwCreationDisposition], 62Eh
0x1800072ae  xor     r9d, r9d
0x1800072b1  lea     r8, aD; "D"
0x1800072b8  xor     edx, edx
0x1800072ba  mov     rcx, rax
0x1800072bd  call    cs:__imp_WdsSetupLogMessageW
0x1800072c3  jmp     loc_1800074A6
0x1800072c8  xorps   xmm0, xmm0
0x1800072cb  xor     eax, eax
0x1800072cd  movups  xmmword ptr [rbp+57h+FileInformation.dwFileAttributes], xmm0
0x1800072d1  movups  xmmword ptr [rbp+57h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x1800072d5  movups  xmmword ptr [rbp+57h+FileInformation.nFileSizeHigh], xmm0
0x1800072d9  mov     [rbp+57h+FileInformation.nFileIndexLow], eax
0x1800072dc  mov     rax, [rbp+57h+var_98]
0x1800072e0  lea     rcx, [rbp+57h+var_98]
0x1800072e4  mov     rax, [rax+20h]
0x1800072e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072ed  lea     rdx, [rbp+57h+FileInformation]; lpFileInformation
0x1800072f1  mov     rcx, [rax]; hFile
0x1800072f4  call    cs:__imp_GetFileInformationByHandle
0x1800072fa  test    eax, eax
0x1800072fc  jnz     short loc_180007370
0x1800072fe  call    cs:__imp_GetLastError
0x180007304  mov     edi, eax
0x180007306  call    cs:__imp_CurrentIP
0x18000730c  mov     rsi, rax
0x18000730f  call    cs:__imp_GetLastError
0x180007315  test    eax, eax
0x180007317  jle     short loc_180007321
0x180007319  movzx   eax, ax
0x18000731c  or      eax, 80070000h
0x180007321  mov     r9d, eax
0x180007324  mov     r8, r15
0x180007327  lea     rdx, aSetupclnestima_0; "SetupClnEstimateFileSize Could not get "...
0x18000732e  mov     ecx, 3000000h; unsigned int
0x180007333  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180007338  mov     [rsp+100h+var_B0], r12d
0x18000733d  mov     [rsp+100h+var_B8], r12
0x180007342  mov     [rsp+100h+var_C0], edi
0x180007346  mov     [rsp+100h+var_C8], rsi
0x18000734b  lea     rcx, aSetupclnestima_1; "SetupClnEstimateFileSize"
0x180007352  mov     [rsp+100h+hTemplateFile], rcx
0x180007357  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupcln\\"...
0x18000735e  mov     qword ptr [rsp+100h+dwFlagsAndAttributes], rcx
0x180007363  mov     [rsp+100h+dwCreationDisposition], 635h
0x18000736b  jmp     loc_1800072AE
0x180007370  mov     eax, [rbp+57h+FileInformation.nFileIndexLow]
0x180007373  mov     dword ptr [rbp+57h+var_88], eax
0x180007376  mov     eax, [rbp+57h+FileInformation.nFileIndexHigh]
0x180007379  mov     dword ptr [rbp+57h+var_88+4], eax
0x18000737c  lea     rsi, [rdi+60h]
0x180007380  lea     rdx, [rbp+57h+var_88]
0x180007384  mov     rcx, rsi
0x180007387  call    ?_Hashval@?$_Hash@V?$_Uset_traits@_KV?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@_K@2@$0A@@std@@@std@@IEBA_KAEB_K@Z; std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Hashval(unsigned __int64 const &)
0x18000738c  mov     r14, rax
0x18000738f  mov     rdx, rax
0x180007392  add     rdx, rdx
0x180007395  mov     rcx, [rsi+10h]
0x180007399  mov     r11, [rcx+rdx*8]
0x18000739d  mov     r10, [rbp+57h+var_88]
0x1800073a1  mov     r8, r14
0x1800073a4  lea     rdx, [rbp+57h+var_80]
0x1800073a8  mov     rcx, rsi
0x1800073ab  call    ?_End@?$_Hash@V?$_Uset_traits@_KV?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@_K@2@$0A@@std@@@std@@IEAA?AV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@_K@std@@@std@@U_Iterator_base0@2@@2@_K@Z; std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_End(unsigned __int64)
0x1800073b0  cmp     r11, [rax]
0x1800073b3  jz      short loc_1800073CD
0x1800073b5  cmp     [r11+10h], r10
0x1800073b9  jz      short loc_1800073C0
0x1800073bb  mov     r11, [r11]
0x1800073be  jmp     short loc_1800073A1
0x1800073c0  cmp     r11, [rsi]
0x1800073c3  jz      short loc_1800073CD
0x1800073c5  mov     rbx, r12
0x1800073c8  jmp     loc_1800074A6
0x1800073cd  cmp     [rbp+57h+FileInformation.nNumberOfLinks], 1
0x1800073d1  jbe     loc_1800074A6
0x1800073d7  lea     r8, [rbp+57h+var_88]
0x1800073db  lea     rdx, [rbp+57h+var_80]
0x1800073df  mov     rcx, rsi
0x1800073e2  call    ??$_Insert@AEB_KU_Nil@std@@@?$_Hash@V?$_Uset_traits@_KV?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@_K@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@_K@std@@@std@@@std@@_N@1@AEB_KU_Nil@1@@Z; std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Insert<unsigned __int64 const &,std::_Nil>(unsigned __int64 const &,std::_Nil)
0x1800073e7  cmp     [rdi+48h], r12
0x1800073eb  jz      loc_1800074A6
0x1800073f1  mov     r9, [rdi+50h]; LinkName
0x1800073f5  test    r9, r9
0x1800073f8  jz      loc_1800074A6
0x1800073fe  mov     eax, [rdi+58h]
0x180007401  mov     [rbp+57h+StringLength], eax
0x180007404  lea     r8, [rbp+57h+StringLength]; StringLength
0x180007408  xor     edx, edx; dwFlags
0x18000740a  mov     rcx, r15; lpFileName
0x18000740d  call    cs:__imp_FindFirstFileNameW
0x180007413  mov     rsi, rax
0x180007416  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000741a  cmp     rax, r14
0x18000741d  jz      loc_1800074A6
0x180007423  mov     rdx, [rdi+48h]
0x180007427  add     rdx, 0Ch; String2
0x18000742b  jz      short loc_180007489
0x18000742d  mov     rcx, [rdi+50h]; String1
0x180007431  test    rcx, rcx
0x180007434  jz      short loc_180007489
0x180007436  mov     rax, r14
0x180007439  inc     rax
0x18000743c  cmp     [rcx+rax*2], r12w
0x180007441  jnz     short loc_180007439
0x180007443  mov     r8, r14
0x180007446  inc     r8; MaxCount
0x180007449  cmp     [rdx+r8*2], r12w
0x18000744e  jnz     short loc_180007446
0x180007450  cmp     r8, rax
0x180007453  ja      short loc_180007465
0x180007455  call    cs:__imp__wcsnicmp
0x18000745b  mov     ecx, r12d
0x18000745e  test    eax, eax
0x180007460  setz    cl
0x180007463  jmp     short loc_180007468
0x180007465  mov     ecx, r12d
0x180007468  test    ecx, ecx
0x18000746a  jz      short loc_180007499
0x18000746c  mov     eax, [rdi+58h]
0x18000746f  mov     [rbp+57h+StringLength], eax
0x180007472  mov     r8, [rdi+50h]; LinkName
0x180007476  lea     rdx, [rbp+57h+StringLength]; StringLength
0x18000747a  mov     rcx, rsi; hFindStream
0x18000747d  call    cs:__imp_FindNextFileNameW
0x180007483  test    eax, eax
0x180007485  jnz     short loc_180007423
0x180007487  jmp     short loc_18000749C
0x180007489  mov     rax, gs:30h
0x180007492  mov     dword ptr [rax+68h], 57h ; 'W'
0x180007499  mov     rbx, r12
0x18000749c  mov     rcx, rsi; hFindFile
0x18000749f  call    cs:__imp_FindClose
0x1800074a5  nop
0x1800074a6  mov     [rbp+57h+var_98], r13
0x1800074aa  lea     rcx, [rbp+57h+var_90]
0x1800074ae  call    ?Release@?$CleanupInfo@PEAX@RAII@@SAXAEAPEAX@Z; RAII::CleanupInfo<void *>::Release(void * &)
0x1800074b3  mov     rax, rbx
0x1800074b6  mov     rcx, [rbp+57h+var_38]
0x1800074ba  xor     rcx, rsp; StackCookie
0x1800074bd  call    __security_check_cookie
0x1800074c2  mov     rbx, [rsp+100h+arg_10]
0x1800074ca  add     rsp, 0D0h
0x1800074d1  pop     r15
0x1800074d3  pop     r14
0x1800074d5  pop     r13
0x1800074d7  pop     r12
0x1800074d9  pop     rdi
0x1800074da  pop     rsi
0x1800074db  pop     rbp
0x1800074dc  retn
```
