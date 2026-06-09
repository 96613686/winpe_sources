# StLoadNamedProfileMetaData(_GUID const *,int,_GUID *,ushort const *,ulong *,uchar * *)

- ea: `0x1800191a0`
- end: `0x1800195f6`
- name: `?StLoadNamedProfileMetaData@@YAKPEBU_GUID@@HPEAU1@PEBGPEAKPEAPEAE@Z`
- size: `1110`
- prototype: `__int64 __fastcall(const struct _GUID *, int, struct _GUID *, LPCWSTR lpValueName, unsigned int *, unsigned __int8 **)`
- caller_count: `5`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180017530`
- `0x180041010`
- `0x1800b8394`
- `0x1800baeb8`
- `0x1800bbac0`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x1800191a0`
- `0x180019820`
- `0x180019bd0`
- `0x180019c60`
- `0x18002f450`
- `0x180106340`
- `0x180107330`
- `0x180108234`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019468`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019493`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019593`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019468`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019493`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019593`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800195c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800195c4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800192b4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800192b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800195b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800195b6`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180019485`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180019485`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180019459`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180019459`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001939f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800194af`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001939f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800194af`
- `ext-ms-win-networking-wlanstorage-l1-1-0!GetCustomStorageRootPath` at `0x180019532`
- `ext-ms-win-networking-wlanstorage-l1-1-0!GetCustomStorageRootPath` at `0x180019532`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180019381`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180019381`

## pseudocode

```c
__int64 __fastcall StLoadNamedProfileMetaData(
        const struct _GUID *a1,
        int a2,
        struct _GUID *a3,
        LPCWSTR lpValueName,
        unsigned int *a5,
        unsigned __int8 **a6)
{
  __int64 FileW; // rsi
  __int64 v11; // rax
  int v12; // edx
  unsigned int RegKeyPath; // edi
  DWORD LastError; // eax
  int BasicProfileFolderPath; // eax
  int v17; // eax
  int CustomStorageRootPath; // eax
  unsigned __int8 *v19; // rcx
  HKEY hKey; // [rsp+50h] [rbp-738h] BYREF
  _FILETIME LastWriteTime; // [rsp+58h] [rbp-730h] BYREF
  OLECHAR sz[40]; // [rsp+60h] [rbp-728h] BYREF
  OLECHAR v23[40]; // [rsp+B0h] [rbp-6D8h] BYREF
  WCHAR FileName[264]; // [rsp+100h] [rbp-688h] BYREF
  _BYTE v25[528]; // [rsp+310h] [rbp-478h] BYREF
  WCHAR SubKey[264]; // [rsp+520h] [rbp-268h] BYREF

  hKey = 0;
  FileW = -1;
  memset_0(FileName, 0, 0x208u);
  LastWriteTime = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 32, &WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids);
  }
  v11 = -1;
  do
  {
    v12 = lpValueName[v11 + 1] - aLastmodified[v11 + 1];
    if ( v12 )
      break;
    v11 += 2;
    if ( v11 == 13 )
      break;
    v12 = lpValueName[v11] - aLastmodified[v11];
  }
  while ( !v12 );
  if ( v12 )
  {
    RegKeyPath = StpGetRegKeyPath(a1, a2, a3, 0, 1, SubKey, 0x104u);
    if ( !RegKeyPath )
    {
      RegKeyPath = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &hKey);
      if ( !RegKeyPath )
      {
        LastError = StpQueryRegValueAllocate(hKey, lpValueName, 3u, a5, a6);
LABEL_10:
        RegKeyPath = LastError;
      }
    }
  }
  else
  {
    if ( IsGetCustomWfdSettingsRegPathPresent() )
    {
      CustomStorageRootPath = GetCustomStorageRootPath(v25, 260, 0);
      RegKeyPath = CustomStorageRootPath;
      if ( CustomStorageRootPath < 0 )
      {
        if ( (CustomStorageRootPath & 0x1FFF0000) == 0x70000 )
          RegKeyPath = (unsigned __int16)CustomStorageRootPath;
        if ( RegKeyPath )
          goto LABEL_11;
      }
    }
    else
    {
      BasicProfileFolderPath = GetBasicProfileFolderPath(4, 0, v25, 260);
      RegKeyPath = BasicProfileFolderPath;
      if ( BasicProfileFolderPath < 0 )
      {
        if ( (BasicProfileFolderPath & 0x1FFF0000) == 0x70000 )
          RegKeyPath = (unsigned __int16)BasicProfileFolderPath;
        if ( RegKeyPath )
          goto LABEL_11;
      }
    }
    StringFromGUID2(a3, sz, 39);
    if ( a1 )
    {
      StringFromGUID2(a1, v23, 39);
      v17 = StringCchPrintfW(
              FileName,
              0x104u,
              L"%s\\%s\\%s\\%s\\%s\\%s.%s",
              v25,
              L"Microsoft\\Wlansvc",
              L"Profiles",
              L"Interfaces",
              v23,
              sz,
              L"xml");
    }
    else
    {
      v17 = StringCchPrintfW(
              FileName,
              0x104u,
              L"%s\\%s\\%s\\%s\\%s.%s",
              v25,
              L"Microsoft\\Wlansvc",
              L"Profiles",
              L"Machine",
              sz,
              L"xml");
    }
    RegKeyPath = v17;
    if ( v17 >= 0 )
    {
      RegKeyPath = 0;
    }
    else
    {
      if ( (v17 & 0x1FFF0000) == 0x70000 )
        RegKeyPath = (unsigned __int16)v17;
      if ( RegKeyPath )
        goto LABEL_11;
    }
    FileW = (__int64)CreateFileW(FileName, 0x80u, 1u, 0, 3u, 0, 0);
    if ( FileW != -1 || (RegKeyPath = GetLastError()) == 0 )
    {
      if ( !GetFileTime((HANDLE)FileW, 0, 0, &LastWriteTime) || (v19 = (unsigned __int8 *)AllocWLMem(8u)) == 0 )
      {
        LastError = GetLastError();
        goto LABEL_10;
      }
      *(_FILETIME *)v19 = LastWriteTime;
      *a5 = 8;
      *a6 = v19;
    }
  }
LABEL_11:
  if ( hKey )
    RegCloseKey(hKey);
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 33, &WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids, RegKeyPath);
  }
  return RegKeyPath;
}

```

## disassembly

```asm
0x1800191a0  push    rbx
0x1800191a2  push    rbp
0x1800191a3  push    rsi
0x1800191a4  push    rdi
0x1800191a5  push    r12
0x1800191a7  push    r13
0x1800191a9  push    r14
0x1800191ab  push    r15
0x1800191ad  sub     rsp, 748h
0x1800191b4  mov     rax, cs:__security_cookie
0x1800191bb  xor     rax, rsp
0x1800191be  mov     [rsp+788h+var_58], rax
0x1800191c6  mov     r15, [rsp+788h+arg_20]
0x1800191ce  mov     r14, r8
0x1800191d1  mov     r12, [rsp+788h+arg_28]
0x1800191d9  mov     edi, edx
0x1800191db  mov     rbp, rcx
0x1800191de  xor     r13d, r13d
0x1800191e1  xor     edx, edx; Val
0x1800191e3  mov     [rsp+788h+hKey], r13
0x1800191e8  mov     r8d, 208h; Size
0x1800191ee  lea     rcx, [rsp+788h+FileName]; void *
0x1800191f6  mov     rbx, r9
0x1800191f9  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180019200  call    memset_0
0x180019205  mov     qword ptr [rsp+788h+LastWriteTime.dwLowDateTime], r13
0x18001920a  mov     rcx, cs:WPP_GLOBAL_Control
0x180019211  lea     r13, WPP_GLOBAL_Control
0x180019218  cmp     rcx, r13
0x18001921b  jnz     loc_180019331
0x180019221  lea     r8, aLastmodified; "LastModified"
0x180019228  mov     rax, rsi
0x18001922b  nop     dword ptr [rax+rax+00h]
0x180019230  movzx   edx, word ptr [rbx+rax*2+2]
0x180019235  movzx   ecx, word ptr [r8+rax*2+2]
0x18001923b  sub     edx, ecx
0x18001923d  jnz     short loc_180019256
0x18001923f  add     rax, 2
0x180019243  cmp     rax, 0Dh
0x180019247  jz      short loc_180019256
0x180019249  movzx   edx, word ptr [rbx+rax*2]
0x18001924d  movzx   ecx, word ptr [r8+rax*2]
0x180019252  sub     edx, ecx
0x180019254  jz      short loc_180019230
0x180019256  test    edx, edx
0x180019258  jz      loc_18001935F
0x18001925e  lea     rax, [rsp+788h+SubKey]
0x180019266  mov     [rsp+788h+hTemplateFile], 104h; unsigned __int64
0x18001926f  mov     qword ptr [rsp+788h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x180019274  xor     r9d, r9d; int
0x180019277  mov     r8, r14; struct _GUID *
0x18001927a  mov     dword ptr [rsp+788h+phkResult], 1; int
0x180019282  mov     edx, edi; int
0x180019284  mov     rcx, rbp; struct _GUID *
0x180019287  call    ?StpGetRegKeyPath@@YAKPEBU_GUID@@HPEAU1@HHPEAG_K@Z; StpGetRegKeyPath(_GUID const *,int,_GUID *,int,int,ushort *,unsigned __int64)
0x18001928c  mov     edi, eax
0x18001928e  test    eax, eax
0x180019290  jnz     short loc_1800192DD
0x180019292  lea     rax, [rsp+788h+hKey]
0x180019297  mov     r9d, 1; samDesired
0x18001929d  xor     r8d, r8d; ulOptions
0x1800192a0  mov     [rsp+788h+phkResult], rax; phkResult
0x1800192a5  lea     rdx, [rsp+788h+SubKey]; lpSubKey
0x1800192ad  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800192b4  call    cs:__imp_RegOpenKeyExW
0x1800192ba  mov     edi, eax
0x1800192bc  test    eax, eax
0x1800192be  jnz     short loc_1800192DD
0x1800192c0  mov     rcx, [rsp+788h+hKey]; hKey
0x1800192c5  mov     r9, r15; unsigned int *
0x1800192c8  mov     r8d, 3; unsigned int
0x1800192ce  mov     [rsp+788h+phkResult], r12; unsigned __int8 **
0x1800192d3  mov     rdx, rbx; lpValueName
0x1800192d6  call    ?StpQueryRegValueAllocate@@YAKPEAUHKEY__@@PEBGKPEAKPEAPEAE@Z; StpQueryRegValueAllocate(HKEY__ *,ushort const *,ulong,ulong *,uchar * *)
0x1800192db  mov     edi, eax
0x1800192dd  mov     rcx, [rsp+788h+hKey]; hKey
0x1800192e2  test    rcx, rcx
0x1800192e5  jnz     loc_1800195B6
0x1800192eb  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800192ef  jnz     loc_1800195C1
0x1800192f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800192fc  cmp     rcx, r13
0x1800192ff  jz      short loc_18001930B
0x180019301  cmp     byte ptr [rcx+69h], 4
0x180019305  jnb     loc_1800195CF
0x18001930b  mov     eax, edi
0x18001930d  mov     rcx, [rsp+788h+var_58]
0x180019315  xor     rcx, rsp; StackCookie
0x180019318  call    __security_check_cookie
0x18001931d  add     rsp, 748h
0x180019324  pop     r15
0x180019326  pop     r14
0x180019328  pop     r13
0x18001932a  pop     r12
0x18001932c  pop     rdi
0x18001932d  pop     rsi
0x18001932e  pop     rbp
0x18001932f  pop     rbx
0x180019330  retn
0x180019331  cmp     byte ptr [rcx+69h], 4
0x180019335  jb      loc_180019221
0x18001933b  test    byte ptr [rcx+6Ch], 1
0x18001933f  jz      loc_180019221
0x180019345  mov     rcx, [rcx+60h]
0x180019349  lea     r8, WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids
0x180019350  mov     edx, 20h ; ' '
0x180019355  call    WPP_SF_
0x18001935a  jmp     loc_180019221
0x18001935f  call    IsGetCustomWfdSettingsRegPathPresent
0x180019364  test    al, al
0x180019366  jnz     loc_180019522
0x18001936c  mov     r9d, 104h
0x180019372  lea     r8, [rsp+788h+var_478]
0x18001937a  xor     edx, edx
0x18001937c  mov     ecx, 4
0x180019381  call    cs:__imp_GetBasicProfileFolderPath
0x180019387  mov     edi, eax
0x180019389  test    eax, eax
0x18001938b  js      loc_18001955E
0x180019391  mov     r8d, 27h ; '''; cchMax
0x180019397  lea     rdx, [rsp+788h+sz]; lpsz
0x18001939c  mov     rcx, r14; rguid
0x18001939f  call    cs:__imp_StringFromGUID2
0x1800193a5  test    rbp, rbp
0x1800193a8  jnz     loc_18001949E
0x1800193ae  lea     rax, aXml; "xml"
0x1800193b5  mov     edx, 104h; unsigned __int64
0x1800193ba  mov     [rsp+788h+var_748], rax
0x1800193bf  lea     r9, [rsp+788h+var_478]
0x1800193c7  lea     rax, [rsp+788h+sz]
0x1800193cc  mov     [rsp+788h+var_750], rax
0x1800193d1  lea     r8, aSSSSSS; "%s\\%s\\%s\\%s\\%s.%s"
0x1800193d8  lea     rax, aMachine_0; "Machine"
0x1800193df  mov     [rsp+788h+hTemplateFile], rax
0x1800193e4  lea     rcx, [rsp+788h+FileName]; unsigned __int16 *
0x1800193ec  lea     rax, aProfiles; "Profiles"
0x1800193f3  mov     qword ptr [rsp+788h+dwFlagsAndAttributes], rax
0x1800193f8  lea     rax, aMicrosoftWlans; "Microsoft\\Wlansvc"
0x1800193ff  mov     [rsp+788h+phkResult], rax
0x180019404  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180019409  mov     edi, eax
0x18001940b  test    eax, eax
0x18001940d  jns     loc_18001957A
0x180019413  and     eax, 1FFF0000h
0x180019418  cmp     eax, 70000h
0x18001941d  jnz     short loc_180019422
0x18001941f  movzx   edi, di
0x180019422  test    edi, edi
0x180019424  jnz     loc_1800192DD
0x18001942a  mov     [rsp+788h+hTemplateFile], 0; hTemplateFile
0x180019433  lea     rcx, [rsp+788h+FileName]; lpFileName
0x18001943b  mov     [rsp+788h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180019443  xor     r9d, r9d; lpSecurityAttributes
0x180019446  mov     edx, 80h; dwDesiredAccess
0x18001944b  mov     dword ptr [rsp+788h+phkResult], 3; dwCreationDisposition
0x180019453  mov     r8d, 1; dwShareMode
0x180019459  call    cs:__imp_CreateFileW
0x18001945f  mov     rsi, rax
0x180019462  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180019466  jnz     short loc_180019478
0x180019468  call    cs:__imp_GetLastError
0x18001946e  mov     edi, eax
0x180019470  test    eax, eax
0x180019472  jnz     loc_1800192DD
0x180019478  lea     r9, [rsp+788h+LastWriteTime]; lpLastWriteTime
0x18001947d  xor     r8d, r8d; lpLastAccessTime
0x180019480  xor     edx, edx; lpCreationTime
0x180019482  mov     rcx, rsi; hFile
0x180019485  call    cs:__imp_GetFileTime
0x18001948b  test    eax, eax
0x18001948d  jnz     loc_180019581
0x180019493  call    cs:__imp_GetLastError
0x180019499  jmp     loc_1800192DB
0x18001949e  mov     r8d, 27h ; '''; cchMax
0x1800194a4  lea     rdx, [rsp+788h+var_6D8]; lpsz
0x1800194ac  mov     rcx, rbp; rguid
0x1800194af  call    cs:__imp_StringFromGUID2
0x1800194b5  lea     rax, aXml; "xml"
0x1800194bc  mov     edx, 104h; unsigned __int64
0x1800194c1  mov     [rsp+788h+var_740], rax
0x1800194c6  lea     r9, [rsp+788h+var_478]
0x1800194ce  lea     rax, [rsp+788h+sz]
0x1800194d3  mov     [rsp+788h+var_748], rax
0x1800194d8  lea     r8, aSSSSSSS; "%s\\%s\\%s\\%s\\%s\\%s.%s"
0x1800194df  lea     rax, [rsp+788h+var_6D8]
0x1800194e7  mov     [rsp+788h+var_750], rax
0x1800194ec  lea     rcx, [rsp+788h+FileName]; unsigned __int16 *
0x1800194f4  lea     rax, aInterfaces; "Interfaces"
0x1800194fb  mov     [rsp+788h+hTemplateFile], rax
0x180019500  lea     rax, aProfiles; "Profiles"
0x180019507  mov     qword ptr [rsp+788h+dwFlagsAndAttributes], rax
0x18001950c  lea     rax, aMicrosoftWlans; "Microsoft\\Wlansvc"
0x180019513  mov     [rsp+788h+phkResult], rax
0x180019518  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001951d  jmp     loc_180019409
0x180019522  xor     r8d, r8d
0x180019525  lea     rcx, [rsp+788h+var_478]
0x18001952d  mov     edx, 104h
0x180019532  call    cs:__imp_GetCustomStorageRootPath
0x180019538  mov     edi, eax
0x18001953a  test    eax, eax
0x18001953c  jns     loc_180019391
0x180019542  and     eax, 1FFF0000h
0x180019547  cmp     eax, 70000h
0x18001954c  jnz     short loc_180019551
0x18001954e  movzx   edi, di
0x180019551  test    edi, edi
0x180019553  jnz     loc_1800192DD
0x180019559  jmp     loc_180019391
0x18001955e  and     eax, 1FFF0000h
0x180019563  cmp     eax, 70000h
0x180019568  jnz     short loc_18001956D
0x18001956a  movzx   edi, di
0x18001956d  test    edi, edi
0x18001956f  jnz     loc_1800192DD
0x180019575  jmp     loc_180019391
0x18001957a  xor     edi, edi
0x18001957c  jmp     loc_18001942A
0x180019581  mov     ecx, 8; dwBytes
0x180019586  call    AllocWLMem
0x18001958b  mov     rcx, rax
0x18001958e  test    rax, rax
0x180019591  jnz     short loc_18001959E
0x180019593  call    cs:__imp_GetLastError
0x180019599  jmp     loc_1800192DB
0x18001959e  mov     rax, qword ptr [rsp+788h+LastWriteTime.dwLowDateTime]
0x1800195a3  mov     [rcx], rax
0x1800195a6  mov     dword ptr [r15], 8
0x1800195ad  mov     [r12], rcx
0x1800195b1  jmp     loc_1800192DD
0x1800195b6  call    cs:__imp_RegCloseKey
0x1800195bc  jmp     loc_1800192EB
0x1800195c1  mov     rcx, rsi; hObject
0x1800195c4  call    cs:__imp_CloseHandle
0x1800195ca  jmp     loc_1800192F5
0x1800195cf  test    byte ptr [rcx+6Ch], 1
0x1800195d3  jz      loc_18001930B
0x1800195d9  mov     rcx, [rcx+60h]
0x1800195dd  lea     r8, WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids
0x1800195e4  mov     edx, 21h ; '!'
0x1800195e9  mov     r9d, edi
0x1800195ec  call    WPP_SF_d
0x1800195f1  jmp     loc_18001930B
```
