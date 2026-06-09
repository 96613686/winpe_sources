# CSpp::_EnumerateCacheFilesOnVolume(ushort const *,CSxStringMap *)

- ea: `0x180017600`
- end: `0x180017944`
- name: `?_EnumerateCacheFilesOnVolume@CSpp@@AEAAJPEBGPEAVCSxStringMap@@@Z`
- size: `836`
- prototype: `__int64 __fastcall(CSpp *this, const unsigned __int16 *, struct CSxStringMap *)`
- caller_count: `2`
- callee_count: `14`
- tags: ``

## callers

- `0x180004ff0`
- `0x18001f060`

## callees

- `0x1800074e4`
- `0x18000c894`
- `0x18000e308`
- `0x180017600`
- `0x180020908`
- `0x18002182c`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002d6e8`
- `0x18003532c`
- `0x180035390`
- `0x180035b00`
- `0x180035b9a`
- `0x180035bd0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001774c`
- `KERNEL32!GetLastError` at `0x180017757`
- `KERNEL32!GetLastError` at `0x180017865`
- `KERNEL32!GetLastError` at `0x18001774c`
- `KERNEL32!GetLastError` at `0x180017757`
- `KERNEL32!GetLastError` at `0x180017865`
- `KERNEL32!FindFirstFileW` at `0x180017736`
- `KERNEL32!FindFirstFileW` at `0x180017736`
- `KERNEL32!FindNextFileW` at `0x180017855`
- `KERNEL32!FindNextFileW` at `0x180017855`
- `KERNEL32!FindClose` at `0x1800178e1`
- `KERNEL32!FindClose` at `0x1800178e1`

## string_xrefs

- `0x180017671`: `CSpp::_EnumerateCacheFilesOnVolume`
- `0x180017797`: `( ( ::GetLastError() == ERROR_FILE_NOT_FOUND ) || ( ::GetLastError() == ERROR_PATH_NOT_FOUND ) )`
- `0x1800176e9`: `OnlineMetadataCache`

## pseudocode

```c
__int64 __fastcall CSpp::_EnumerateCacheFilesOnVolume(CSpp *this, const unsigned __int16 *a2, struct CSxStringMap *a3)
{
  BOOL NextFileW; // esi
  __int64 v6; // r14
  CVolumeEntry *v7; // rdi
  _WIN32_FIND_DATAW *p_FindFileData; // rax
  __int16 v9; // ax
  int v10; // ebx
  LPCWSTR v11; // rbx
  char *FirstFileW; // r14
  __int64 v13; // rcx
  int LastFailureAsHRESULT; // eax
  _QWORD *v15; // rcx
  int v16; // edx
  const char *v17; // r9
  int v18; // eax
  bool v19; // sf
  __int16 v20; // ax
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // r8
  const unsigned __int16 *v25; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *v26; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *v27; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *v28; // [rsp+40h] [rbp-C0h]
  const unsigned __int16 *v29; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *v30; // [rsp+50h] [rbp-B0h]
  int v31; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v32; // [rsp+64h] [rbp-9Ch]
  __int16 v33; // [rsp+66h] [rbp-9Ah]
  struct CVolumeEntry *v34; // [rsp+98h] [rbp-68h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+A0h] [rbp-60h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+B0h] [rbp-50h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 145, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids, a2);
  NextFileW = 1;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v31, "CSpp::_EnumerateCacheFilesOnVolume", 9120, 1);
  lpFileName[1] = 0;
  v6 = 592;
  lpFileName[0] = &FileName;
  v7 = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  p_FindFileData = &FindFileData;
  do
  {
    LOBYTE(p_FindFileData->dwFileAttributes) = 0;
    p_FindFileData = (_WIN32_FIND_DATAW *)((char *)p_FindFileData + 1);
    --v6;
  }
  while ( v6 );
  v9 = 9130;
  if ( !a2 || (v32 = 9130, v9 = 9131, !a3) )
  {
    v10 = -2147024809;
    v31 = -2147024809;
    goto LABEL_34;
  }
  v32 = 9131;
  v31 = 0;
  v10 = CBsString::SetPath(
          (CBsString *)lpFileName,
          a2,
          L"System Volume Information\\SPP",
          L"OnlineMetadataCache",
          L"*_OnDiskSnapshotProp",
          v25,
          v26,
          v27,
          v28,
          v29,
          v30);
  v31 = v10;
  v9 = 9134;
  if ( v10 < 0 )
  {
LABEL_34:
    v33 = v9;
    goto LABEL_35;
  }
  v11 = lpFileName[0];
  v32 = 9134;
  FirstFileW = (char *)FindFirstFileW(lpFileName[0], &FindFileData);
  if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    goto LABEL_17;
  if ( GetLastError() == 2 || GetLastError() == 3 )
  {
    v31 = 0;
    v32 = 9142;
    NextFileW = 0;
LABEL_17:
    while ( NextFileW )
    {
      if ( v7 )
        CVolumeEntry::Release(v7);
      v34 = 0;
      v18 = CVolumeEntry::CreateInstance(&v34);
      v7 = v34;
      v19 = v18 < 0;
      v31 = v18;
      v20 = 9151;
      if ( v19
        || (v32 = 9151,
            v31 = CBsString::Set((struct CVolumeEntry *)((char *)v34 + 8), FindFileData.cFileName),
            v20 = 9152,
            v31 < 0) )
      {
        v33 = v20;
        break;
      }
      v32 = 9152;
      v31 = CSxRefMap<CWriterEntryMap,CWriterEntry>::Insert(a3, v7);
      if ( v31 < 0 )
      {
        v33 = 9153;
        break;
      }
      v32 = 9153;
      NextFileW = FindNextFileW(FirstFileW, &FindFileData);
      if ( !NextFileW )
      {
        if ( GetLastError() != 18 )
        {
          LastFailureAsHRESULT = GetLastFailureAsHRESULT(v21);
          v31 = LastFailureAsHRESULT;
          v33 = 9160;
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
          {
            v16 = 147;
            v17 = "( ::GetLastError() == ERROR_NO_MORE_FILES )";
            goto LABEL_15;
          }
          break;
        }
        v31 = 0;
        v32 = 9160;
      }
    }
  }
  else
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v13);
    v31 = LastFailureAsHRESULT;
    v33 = 9142;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
    {
      v16 = 146;
      v17 = "( ( ::GetLastError() == ERROR_FILE_NOT_FOUND ) || ( ::GetLastError() == ERROR_PATH_NOT_FOUND ) )";
LABEL_15:
      WPP_SF_sSd(
        v15[2],
        v16,
        (unsigned int)&WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids,
        (_DWORD)v17,
        (__int64)v11,
        LastFailureAsHRESULT);
    }
  }
  v10 = v31;
  if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    FindClose(FirstFileW);
LABEL_35:
  if ( v7 )
    CVolumeEntry::Release(v7);
  CBsString::_Release((CBsString *)lpFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v31, v22, v23);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180017600  mov     [rsp-8+arg_0], rbx
0x180017605  mov     [rsp-8+arg_18], rsi
0x18001760a  push    rbp
0x18001760b  push    rdi
0x18001760c  push    r13
0x18001760e  push    r14
0x180017610  push    r15
0x180017612  lea     rbp, [rsp-210h]
0x18001761a  sub     rsp, 310h
0x180017621  mov     rax, cs:__security_cookie
0x180017628  xor     rax, rsp
0x18001762b  mov     [rbp+230h+var_30], rax
0x180017632  mov     r15, r8
0x180017635  mov     rbx, rdx
0x180017638  mov     rcx, cs:WPP_GLOBAL_Control
0x18001763f  lea     r13, WPP_GLOBAL_Control
0x180017646  cmp     rcx, r13
0x180017649  jz      short loc_18001766C
0x18001764b  test    dword ptr [rcx+1Ch], 20000000h
0x180017652  jz      short loc_18001766C
0x180017654  mov     rcx, [rcx+10h]
0x180017658  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x18001765f  mov     edx, 91h
0x180017664  mov     r9, rbx
0x180017667  call    WPP_SF_S
0x18001766c  mov     esi, 1
0x180017671  lea     rdx, aCsppEnumeratec; "CSpp::_EnumerateCacheFilesOnVolume"
0x180017678  mov     r9d, esi; unsigned __int16
0x18001767b  lea     rcx, [rsp+330h+var_2D0]; this
0x180017680  mov     r8d, 23A0h; unsigned __int16
0x180017686  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001768b  lea     rax, FileName
0x180017692  mov     [rbp+230h+var_288], 0
0x18001769a  mov     r14d, 250h
0x1800176a0  mov     [rbp+230h+lpFileName], rax
0x1800176a4  mov     r8d, r14d; Size
0x1800176a7  lea     rcx, [rbp+230h+FindFileData]; void *
0x1800176ab  xor     edi, edi
0x1800176ad  xor     edx, edx; Val
0x1800176af  call    memset_0
0x1800176b4  lea     rax, [rbp+230h+FindFileData]
0x1800176b8  mov     [rax], dil
0x1800176bb  add     rax, rsi
0x1800176be  sub     r14, rsi
0x1800176c1  jnz     short loc_1800176B8
0x1800176c3  mov     eax, 23AAh
0x1800176c8  test    rbx, rbx
0x1800176cb  jz      loc_1800178E9
0x1800176d1  mov     [rsp+330h+var_2CC], ax
0x1800176d6  mov     eax, 23ABh
0x1800176db  test    r15, r15
0x1800176de  jz      loc_1800178E9
0x1800176e4  mov     [rsp+330h+var_2CC], ax
0x1800176e9  lea     r9, aOnlinemetadata; "OnlineMetadataCache"
0x1800176f0  lea     rax, aOndisksnapshot; "*_OnDiskSnapshotProp"
0x1800176f7  mov     [rsp+330h+var_2D0], edi
0x1800176fb  lea     r8, aSystemVolumeIn_0; "System Volume Information\\SPP"
0x180017702  mov     [rsp+330h+var_310], rax; unsigned __int16 *
0x180017707  mov     rdx, rbx; unsigned __int16 *
0x18001770a  lea     rcx, [rbp+230h+lpFileName]; this
0x18001770e  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180017713  mov     ebx, eax
0x180017715  mov     [rsp+330h+var_2D0], eax
0x180017719  test    eax, eax
0x18001771b  mov     eax, 23AEh
0x180017720  js      loc_1800178F2
0x180017726  mov     rbx, [rbp+230h+lpFileName]
0x18001772a  lea     rdx, [rbp+230h+FindFileData]; lpFindFileData
0x18001772e  mov     rcx, rbx; lpFileName
0x180017731  mov     [rsp+330h+var_2CC], ax
0x180017736  call    cs:__imp_FindFirstFileW
0x18001773c  mov     r14, rax
0x18001773f  dec     rax
0x180017742  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180017746  jbe     loc_1800177CC
0x18001774c  call    cs:__imp_GetLastError
0x180017752  cmp     eax, 2
0x180017755  jz      short loc_1800177BC
0x180017757  call    cs:__imp_GetLastError
0x18001775d  cmp     eax, 3
0x180017760  jz      short loc_1800177BC
0x180017762  call    GetLastFailureAsHRESULT
0x180017767  mov     ecx, 23B6h
0x18001776c  mov     [rsp+330h+var_2D0], eax
0x180017770  mov     [rsp+330h+var_2CA], cx
0x180017775  mov     rcx, cs:WPP_GLOBAL_Control
0x18001777c  cmp     rcx, r13
0x18001777f  jz      loc_1800178D0
0x180017785  test    dword ptr [rcx+1Ch], 2000000h
0x18001778c  jz      loc_1800178D0
0x180017792  mov     edx, 92h
0x180017797  lea     r9, aGetlasterrorEr; "( ( ::GetLastError() == ERROR_FILE_NOT_"...
0x18001779e  mov     rcx, [rcx+10h]
0x1800177a2  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x1800177a9  mov     dword ptr [rsp+330h+var_308], eax
0x1800177ad  mov     [rsp+330h+var_310], rbx
0x1800177b2  call    WPP_SF_sSd
0x1800177b7  jmp     loc_1800178D0
0x1800177bc  mov     ecx, 23B6h
0x1800177c1  mov     [rsp+330h+var_2D0], edi
0x1800177c5  mov     [rsp+330h+var_2CC], cx
0x1800177ca  xor     esi, esi
0x1800177cc  mov     r13d, 23C1h
0x1800177d2  test    esi, esi
0x1800177d4  jz      loc_1800178D0
0x1800177da  test    rdi, rdi
0x1800177dd  jz      short loc_1800177E7
0x1800177df  mov     rcx, rdi; this
0x1800177e2  call    ?Release@CVolumeEntry@@QEAAKXZ; CVolumeEntry::Release(void)
0x1800177e7  lea     rcx, [rbp+230h+var_298]; struct CVolumeEntry **
0x1800177eb  mov     [rbp+230h+var_298], 0
0x1800177f3  call    ?CreateInstance@CVolumeEntry@@SAJPEAPEAV1@@Z; CVolumeEntry::CreateInstance(CVolumeEntry * *)
0x1800177f8  mov     rdi, [rbp+230h+var_298]
0x1800177fc  test    eax, eax
0x1800177fe  mov     [rsp+330h+var_2D0], eax
0x180017802  mov     eax, 23BFh
0x180017807  js      loc_1800178CB
0x18001780d  lea     rcx, [rdi+8]; this
0x180017811  mov     [rsp+330h+var_2CC], ax
0x180017816  lea     rdx, [rbp+230h+FindFileData.cFileName]; unsigned __int16 *
0x18001781a  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18001781f  mov     [rsp+330h+var_2D0], eax
0x180017823  test    eax, eax
0x180017825  mov     eax, 23C0h
0x18001782a  js      loc_1800178CB
0x180017830  mov     rdx, rdi
0x180017833  mov     [rsp+330h+var_2CC], ax
0x180017838  mov     rcx, r15
0x18001783b  call    ?Insert@?$CSxRefMap@VCWriterEntryMap@@VCWriterEntry@@@@QEAAJPEAVCWriterEntry@@PEAPEAV2@@Z; CSxRefMap<CWriterEntryMap,CWriterEntry>::Insert(CWriterEntry *,CWriterEntry * *)
0x180017840  mov     [rsp+330h+var_2D0], eax
0x180017844  test    eax, eax
0x180017846  js      short loc_1800178C3
0x180017848  lea     rdx, [rbp+230h+FindFileData]; lpFindFileData
0x18001784c  mov     [rsp+330h+var_2CC], r13w
0x180017852  mov     rcx, r14; hFindFile
0x180017855  call    cs:__imp_FindNextFileW
0x18001785b  mov     esi, eax
0x18001785d  test    eax, eax
0x18001785f  jnz     loc_1800177D2
0x180017865  call    cs:__imp_GetLastError
0x18001786b  cmp     eax, 12h
0x18001786e  jnz     short loc_180017883
0x180017870  mov     eax, 23C8h
0x180017875  mov     [rsp+330h+var_2D0], esi
0x180017879  mov     [rsp+330h+var_2CC], ax
0x18001787e  jmp     loc_1800177D2
0x180017883  call    GetLastFailureAsHRESULT
0x180017888  mov     ecx, 23C8h
0x18001788d  mov     [rsp+330h+var_2D0], eax
0x180017891  mov     [rsp+330h+var_2CA], cx
0x180017896  mov     rcx, cs:WPP_GLOBAL_Control
0x18001789d  lea     rdx, WPP_GLOBAL_Control
0x1800178a4  cmp     rcx, rdx
0x1800178a7  jz      short loc_1800178D0
0x1800178a9  test    dword ptr [rcx+1Ch], 2000000h
0x1800178b0  jz      short loc_1800178D0
0x1800178b2  mov     edx, 93h
0x1800178b7  lea     r9, aGetlasterrorEr_0; "( ::GetLastError() == ERROR_NO_MORE_FIL"...
0x1800178be  jmp     loc_18001779E
0x1800178c3  mov     [rsp+330h+var_2CA], r13w
0x1800178c9  jmp     short loc_1800178D0
0x1800178cb  mov     [rsp+330h+var_2CA], ax
0x1800178d0  mov     ebx, [rsp+330h+var_2D0]
0x1800178d4  lea     rax, [r14-1]
0x1800178d8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800178dc  ja      short loc_1800178F7
0x1800178de  mov     rcx, r14; hFindFile
0x1800178e1  call    cs:__imp_FindClose
0x1800178e7  jmp     short loc_1800178F7
0x1800178e9  mov     ebx, 80070057h
0x1800178ee  mov     [rsp+330h+var_2D0], ebx
0x1800178f2  mov     [rsp+330h+var_2CA], ax
0x1800178f7  test    rdi, rdi
0x1800178fa  jz      short loc_180017904
0x1800178fc  mov     rcx, rdi; this
0x1800178ff  call    ?Release@CVolumeEntry@@QEAAKXZ; CVolumeEntry::Release(void)
0x180017904  lea     rcx, [rbp+230h+lpFileName]; this
0x180017908  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18001790d  lea     rcx, [rsp+330h+var_2D0]; this
0x180017912  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180017917  mov     eax, ebx
0x180017919  mov     rcx, [rbp+230h+var_30]
0x180017920  xor     rcx, rsp; StackCookie
0x180017923  call    __security_check_cookie
0x180017928  lea     r11, [rsp+330h+var_20]
0x180017930  mov     rbx, [r11+30h]
0x180017934  mov     rsi, [r11+48h]
0x180017938  mov     rsp, r11
0x18001793b  pop     r15
0x18001793d  pop     r14
0x18001793f  pop     r13
0x180017941  pop     rdi
0x180017942  pop     rbp
0x180017943  retn
```
