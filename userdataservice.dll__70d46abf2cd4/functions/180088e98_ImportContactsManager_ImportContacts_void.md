# ImportContactsManager::_ImportContacts(void)

- ea: `0x180088e98`
- end: `0x1800891f3`
- name: `?_ImportContacts@ImportContactsManager@@AEAAJXZ`
- size: `859`
- prototype: `__int64 __fastcall(ImportContactsManager *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800afee0`

## callees

- `0x180012988`
- `0x180062674`
- `0x180068404`
- `0x18007ba48`
- `0x18007be90`
- `0x180088e98`
- `0x1800891fc`
- `0x180089248`
- `0x18009a498`
- `0x1800aff0c`
- `0x18012c76a`
- `0x18012c7b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180088ec1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180088ec1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800891cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800891cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088f3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088f3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008914f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180089159`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008914f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180089159`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180088f34`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180088f34`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180088f09`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180088f09`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180088fb1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180088fb1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180088fe1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800891bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180088fe1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800891bc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180089185`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180089185`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008901f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008901f`
- `ext-ms-win-security-chambers-l1-1-0!CreateProcessInChamber` at `0x180089134`
- `ext-ms-win-security-chambers-l1-1-0!CreateProcessInChamber` at `0x180089134`
- `ext-ms-win-security-chambers-l1-1-0!GetChamberSidFromId` at `0x18008906f`
- `ext-ms-win-security-chambers-l1-1-0!GetChamberSidFromId` at `0x18008906f`

## string_xrefs

- `0x180089068`: `CommsApplications`
- `0x1800890a2`: `C:\programs\commsapplications\ImportXMLContacts.exe `

## pseudocode

```c
__int64 __fastcall ImportContactsManager::_ImportContacts(struct _RTL_CRITICAL_SECTION *this)
{
  unsigned int v2; // ebx
  const WCHAR *v3; // rcx
  signed int LastError; // eax
  __int64 v5; // r8
  signed int ChamberSidFromId; // edi
  HKEY *phkResult; // rax
  LSTATUS Key; // eax
  __int64 v9; // r8
  int v10; // eax
  __int64 v11; // r8
  void **v12; // rax
  __int64 v13; // r8
  __int64 v14; // r9
  unsigned __int64 v15; // r11
  int v16; // eax
  __int64 v17; // r8
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  void *v20; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v21; // [rsp+60h] [rbp-A0h] BYREF
  char v22; // [rsp+68h] [rbp-98h]
  DWORD cbData; // [rsp+70h] [rbp-90h] BYREF
  BYTE Data[8]; // [rsp+78h] [rbp-88h] BYREF
  HANDLE hObject[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v26; // [rsp+90h] [rbp-70h]
  int v27; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v28[108]; // [rsp+A4h] [rbp-5Ch] BYREF
  _OWORD FileInformation[2]; // [rsp+110h] [rbp+10h] BYREF
  int v30; // [rsp+130h] [rbp+30h]
  unsigned __int16 v31[520]; // [rsp+140h] [rbp+40h] BYREF

  EnterCriticalSection(this);
  if ( this[1].DebugInfo != (PRTL_CRITICAL_SECTION_DEBUG)-1LL )
  {
    v2 = 0;
    v21 = *(_QWORD *)_lambda_a98995495b2f0ca89e3fa4f24af127c7_::_lambda_a98995495b2f0ca89e3fa4f24af127c7_(
                       (_lambda_a98995495b2f0ca89e3fa4f24af127c7_ *)&v21,
                       (struct StoreManagerEnumerator *)this);
    v3 = g_contactsImportFullFilename;
    v22 = 1;
    if ( !g_contactsImportFullFilename )
    {
      Log_AssertionEvent_16();
      v3 = g_contactsImportFullFilename;
    }
    if ( PathFileExistsW(v3) )
    {
      v30 = 0;
      memset(FileInformation, 0, sizeof(FileInformation));
      if ( !GetFileAttributesExW(g_contactsImportFullFilename, GetFileExInfoStandard, FileInformation) )
      {
        LastError = GetLastError();
        ChamberSidFromId = LastError;
        if ( LastError > 0 )
          ChamberSidFromId = (unsigned __int16)LastError | 0x80070000;
        Log_HREvent_35((unsigned int)ChamberSidFromId, 0, v5, 146);
LABEL_10:
        tlx::_UndoSolo__lambda_e085bcbfc21c86b829db8c6ca1023123___::__UndoSolo__lambda_e085bcbfc21c86b829db8c6ca1023123___(&v21);
        v2 = ChamberSidFromId;
        goto LABEL_39;
      }
      hKey = 0;
      phkResult = tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>(&hKey);
      Key = RegCreateKeyExW(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Poom\\Indexing",
              0,
              0,
              0,
              0x2001Fu,
              0,
              phkResult,
              0);
      ChamberSidFromId = Key;
      if ( Key )
      {
        if ( Key > 0 )
          ChamberSidFromId = (unsigned __int16)Key | 0x80070000;
        Log_HREvent_35((unsigned int)ChamberSidFromId, 0, v9, 160);
        goto LABEL_15;
      }
      *(_QWORD *)Data = 0;
      cbData = 8;
      v10 = RegQueryValueExW(hKey, L"ContactsImportTime", 0, 0, Data, &cbData);
      if ( (v10 & 0xFFFFFFFD) != 0 )
      {
        if ( v10 > 0 )
          v10 = (unsigned __int16)v10 | 0x80070000;
        Log_HREvent_35((unsigned int)v10, 0, v11, 171);
      }
      if ( *(_QWORD *)((char *)FileInformation + 4) > *(_QWORD *)Data )
      {
        v20 = 0;
        v12 = tlx::replace<UdmPropertyValue,&void _MidlFreer<UdmPropertyValue>(UdmPropertyValue *)>(&v20);
        ChamberSidFromId = GetChamberSidFromId(L"CommsApplications", v12);
        if ( ChamberSidFromId < 0 )
        {
          v14 = 181;
LABEL_24:
          Log_HREvent_35((unsigned int)ChamberSidFromId, 1, v13, v14);
          auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(&v20);
LABEL_15:
          if ( hKey )
            RegCloseKey(hKey);
          goto LABEL_10;
        }
        ChamberSidFromId = StringCchCopyW(v31, 0x208u, L"C:\\programs\\commsapplications\\ImportXMLContacts.exe ");
        if ( ChamberSidFromId < 0 )
        {
          v14 = 184;
          goto LABEL_24;
        }
        ChamberSidFromId = StringCchCatW(v31, v15, g_contactsImportFullFilename);
        if ( ChamberSidFromId < 0 )
        {
          v14 = 185;
          goto LABEL_24;
        }
        memset_0(v28, 0, 0x64u);
        v27 = 104;
        v26 = 0;
        *(_OWORD *)hObject = 0;
        ChamberSidFromId = CreateProcessInChamber(v20, 0, 0, v31, 0, 0, 0, &v27, hObject);
        if ( ChamberSidFromId < 0 )
        {
          v14 = 200;
          goto LABEL_24;
        }
        CloseHandle(hObject[0]);
        CloseHandle(hObject[1]);
        v16 = RegSetValueExW(hKey, L"ContactsImportTime", 0, 0xBu, (const BYTE *)FileInformation + 4, 8u);
        if ( v16 )
        {
          if ( v16 > 0 )
            v16 = (unsigned __int16)v16 | 0x80070000;
          Log_HREvent_35((unsigned int)v16, 0, v17, 212);
        }
        auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(&v20);
      }
      if ( hKey )
        RegCloseKey(hKey);
    }
    tlx::_UndoSolo__lambda_e085bcbfc21c86b829db8c6ca1023123___::__UndoSolo__lambda_e085bcbfc21c86b829db8c6ca1023123___(&v21);
    goto LABEL_39;
  }
  v2 = 0;
LABEL_39:
  LeaveCriticalSection(this);
  return v2;
}

```

## disassembly

```asm
0x180088e98  push    rbp
0x180088e9a  push    rbx
0x180088e9b  push    rdi
0x180088e9c  push    r14
0x180088e9e  lea     rbp, [rsp-468h]
0x180088ea6  sub     rsp, 568h
0x180088ead  mov     rax, cs:__security_cookie
0x180088eb4  xor     rax, rsp
0x180088eb7  mov     [rbp+480h+var_30], rax
0x180088ebe  mov     r14, rcx
0x180088ec1  call    cs:__imp_EnterCriticalSection
0x180088ec7  cmp     qword ptr [r14+28h], 0FFFFFFFFFFFFFFFFh
0x180088ecc  jnz     short loc_180088ED5
0x180088ece  xor     ebx, ebx
0x180088ed0  jmp     loc_1800891CC
0x180088ed5  mov     rdx, r14; struct StoreManagerEnumerator *
0x180088ed8  lea     rcx, [rsp+580h+var_520]; this
0x180088edd  call    ??0_lambda_a98995495b2f0ca89e3fa4f24af127c7_@@QEAA@PEAVStoreManagerEnumerator@@@Z; _lambda_a98995495b2f0ca89e3fa4f24af127c7_::_lambda_a98995495b2f0ca89e3fa4f24af127c7_(StoreManagerEnumerator *)
0x180088ee2  xor     ebx, ebx
0x180088ee4  mov     rcx, [rax]
0x180088ee7  mov     [rsp+580h+var_520], rcx
0x180088eec  mov     rcx, cs:?g_contactsImportFullFilename@@3V?$auto_ptr@G$1??$_delete@G@tlx@@YAXPEAG@Z@tlx@@A; tlx::auto_ptr<ushort,&tlx::_delete<ushort>(ushort *)> g_contactsImportFullFilename
0x180088ef3  mov     [rsp+580h+var_518], 1
0x180088ef8  test    rcx, rcx
0x180088efb  jnz     short loc_180088F09
0x180088efd  call    Log_AssertionEvent_16
0x180088f02  mov     rcx, cs:?g_contactsImportFullFilename@@3V?$auto_ptr@G$1??$_delete@G@tlx@@YAXPEAG@Z@tlx@@A; pszPath
0x180088f09  call    cs:__imp_PathFileExistsW
0x180088f0f  test    eax, eax
0x180088f11  jz      loc_1800891C2
0x180088f17  mov     rcx, cs:?g_contactsImportFullFilename@@3V?$auto_ptr@G$1??$_delete@G@tlx@@YAXPEAG@Z@tlx@@A; lpFileName
0x180088f1e  lea     r8, [rbp+480h+FileInformation]; lpFileInformation
0x180088f22  xorps   xmm0, xmm0
0x180088f25  xor     eax, eax
0x180088f27  xor     edx, edx; fInfoLevelId
0x180088f29  mov     [rbp+480h+var_450], eax
0x180088f2c  movups  [rbp+480h+FileInformation], xmm0
0x180088f30  movups  [rbp+480h+var_460], xmm0
0x180088f34  call    cs:__imp_GetFileAttributesExW
0x180088f3a  test    eax, eax
0x180088f3c  jnz     short loc_180088F73
0x180088f3e  call    cs:__imp_GetLastError
0x180088f44  mov     edi, eax
0x180088f46  test    eax, eax
0x180088f48  jle     short loc_180088F53
0x180088f4a  movzx   edi, ax
0x180088f4d  or      edi, 80070000h
0x180088f53  xor     edx, edx
0x180088f55  mov     r9d, 92h
0x180088f5b  mov     ecx, edi
0x180088f5d  call    Log_HREvent_35
0x180088f62  lea     rcx, [rsp+580h+var_520]
0x180088f67  call    tlx___UndoSolo__lambda_e085bcbfc21c86b829db8c6ca1023123_______UndoSolo__lambda_e085bcbfc21c86b829db8c6ca1023123___
0x180088f6c  mov     ebx, edi
0x180088f6e  jmp     loc_1800891CC
0x180088f73  lea     rcx, [rsp+580h+hKey]
0x180088f78  mov     [rsp+580h+hKey], rbx
0x180088f7d  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x180088f82  mov     [rsp+580h+lpdwDisposition], rbx; lpdwDisposition
0x180088f87  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Poom\\Indexing"
0x180088f8e  mov     [rsp+580h+phkResult], rax; phkResult
0x180088f93  xor     r9d, r9d; lpClass
0x180088f96  mov     [rsp+580h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x180088f9b  xor     r8d, r8d; Reserved
0x180088f9e  mov     [rsp+580h+samDesired], 2001Fh; samDesired
0x180088fa6  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180088fad  mov     [rsp+580h+dwOptions], ebx; dwOptions
0x180088fb1  call    cs:__imp_RegCreateKeyExW
0x180088fb7  mov     edi, eax
0x180088fb9  test    eax, eax
0x180088fbb  jz      short loc_180088FEC
0x180088fbd  jle     short loc_180088FC8
0x180088fbf  movzx   edi, ax
0x180088fc2  or      edi, 80070000h
0x180088fc8  xor     edx, edx
0x180088fca  mov     r9d, 0A0h
0x180088fd0  mov     ecx, edi
0x180088fd2  call    Log_HREvent_35
0x180088fd7  mov     rcx, [rsp+580h+hKey]; hKey
0x180088fdc  test    rcx, rcx
0x180088fdf  jz      short loc_180088F62
0x180088fe1  call    cs:__imp_RegCloseKey
0x180088fe7  jmp     loc_180088F62
0x180088fec  mov     rcx, [rsp+580h+hKey]; hKey
0x180088ff1  lea     rax, [rsp+580h+cbData]
0x180088ff6  mov     qword ptr [rsp+580h+samDesired], rax; lpcbData
0x180088ffb  lea     rdx, aContactsimport; "ContactsImportTime"
0x180089002  lea     rax, [rsp+580h+Data]
0x180089007  mov     qword ptr [rsp+580h+Data], rbx
0x18008900c  xor     r9d, r9d; lpType
0x18008900f  mov     qword ptr [rsp+580h+dwOptions], rax; lpData
0x180089014  xor     r8d, r8d; lpReserved
0x180089017  mov     [rsp+580h+cbData], 8
0x18008901f  call    cs:__imp_RegQueryValueExW
0x180089025  test    eax, 0FFFFFFFDh
0x18008902a  jz      short loc_180089047
0x18008902c  test    eax, eax
0x18008902e  jle     short loc_180089038
0x180089030  movzx   eax, ax
0x180089033  or      eax, 80070000h
0x180089038  xor     edx, edx
0x18008903a  mov     r9d, 0ABh
0x180089040  mov     ecx, eax
0x180089042  call    Log_HREvent_35
0x180089047  mov     rax, qword ptr [rsp+580h+Data]
0x18008904c  cmp     qword ptr [rbp+480h+FileInformation+4], rax
0x180089050  jbe     loc_1800891B2
0x180089056  lea     rcx, [rsp+580h+var_528]
0x18008905b  mov     [rsp+580h+var_528], rbx
0x180089060  call    ??$replace@UUdmPropertyValue@@$1??$_MidlFreer@UUdmPropertyValue@@@@YAXPEAU1@@Z@tlx@@YAPEAPEAUUdmPropertyValue@@AEAV?$auto_ptr@UUdmPropertyValue@@$1??$_MidlFreer@UUdmPropertyValue@@@@YAXPEAU1@@Z@0@@Z; tlx::replace<UdmPropertyValue,&_MidlFreer<UdmPropertyValue>(UdmPropertyValue *)>(tlx::auto_ptr<UdmPropertyValue,&_MidlFreer<UdmPropertyValue>(UdmPropertyValue *)> &)
0x180089065  mov     rdx, rax
0x180089068  lea     rcx, aCommsapplicati; "CommsApplications"
0x18008906f  call    cs:__imp_GetChamberSidFromId
0x180089075  mov     edi, eax
0x180089077  test    eax, eax
0x180089079  jns     short loc_18008909C
0x18008907b  mov     r9d, 0B5h
0x180089081  mov     edx, 1
0x180089086  mov     ecx, edi
0x180089088  call    Log_HREvent_35
0x18008908d  lea     rcx, [rsp+580h+var_528]
0x180089092  call    ??1?$auto_local_array_ptr@K@@QEAA@XZ; auto_local_array_ptr<ulong>::~auto_local_array_ptr<ulong>(void)
0x180089097  jmp     loc_180088FD7
0x18008909c  mov     r11d, 208h
0x1800890a2  lea     r8, aCProgramsComms; "C:\\programs\\commsapplications\\Import"...
0x1800890a9  mov     edx, r11d; unsigned __int64
0x1800890ac  lea     rcx, [rbp+480h+var_440]; unsigned __int16 *
0x1800890b0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800890b5  mov     edi, eax
0x1800890b7  test    eax, eax
0x1800890b9  jns     short loc_1800890C3
0x1800890bb  mov     r9d, 0B8h
0x1800890c1  jmp     short loc_180089081
0x1800890c3  mov     r8, cs:?g_contactsImportFullFilename@@3V?$auto_ptr@G$1??$_delete@G@tlx@@YAXPEAG@Z@tlx@@A; unsigned __int16 *
0x1800890ca  lea     rcx, [rbp+480h+var_440]; unsigned __int16 *
0x1800890ce  mov     rdx, r11; unsigned __int64
0x1800890d1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800890d6  mov     edi, eax
0x1800890d8  test    eax, eax
0x1800890da  jns     short loc_1800890E4
0x1800890dc  mov     r9d, 0B9h
0x1800890e2  jmp     short loc_180089081
0x1800890e4  xor     edx, edx; Val
0x1800890e6  lea     rcx, [rbp+480h+var_4DC]; void *
0x1800890ea  lea     r8d, [rdx+64h]; Size
0x1800890ee  call    memset_0
0x1800890f3  mov     rcx, [rsp+580h+var_528]
0x1800890f8  lea     r9, [rbp+480h+var_440]
0x1800890fc  xor     eax, eax
0x1800890fe  mov     [rbp+480h+var_4E0], 68h ; 'h'
0x180089105  mov     [rbp+480h+var_4F0], rax
0x180089109  xorps   xmm0, xmm0
0x18008910c  lea     rax, [rbp+480h+hObject]
0x180089110  xor     r8d, r8d
0x180089113  mov     [rsp+580h+lpdwDisposition], rax
0x180089118  xor     edx, edx
0x18008911a  lea     rax, [rbp+480h+var_4E0]
0x18008911e  mov     [rsp+580h+phkResult], rax
0x180089123  mov     [rsp+580h+lpSecurityAttributes], rbx
0x180089128  mov     [rsp+580h+samDesired], ebx
0x18008912c  mov     [rsp+580h+dwOptions], ebx
0x180089130  movups  xmmword ptr [rbp+480h+hObject], xmm0
0x180089134  call    cs:__imp_CreateProcessInChamber
0x18008913a  mov     edi, eax
0x18008913c  test    eax, eax
0x18008913e  jns     short loc_18008914B
0x180089140  mov     r9d, 0C8h
0x180089146  jmp     loc_180089081
0x18008914b  mov     rcx, [rbp+480h+hObject]; hObject
0x18008914f  call    cs:__imp_CloseHandle
0x180089155  mov     rcx, [rbp+480h+hObject+8]; hObject
0x180089159  call    cs:__imp_CloseHandle
0x18008915f  mov     rcx, [rsp+580h+hKey]; hKey
0x180089164  lea     rax, [rbp+480h+FileInformation+4]
0x180089168  mov     [rsp+580h+samDesired], 8; cbData
0x180089170  lea     rdx, aContactsimport; "ContactsImportTime"
0x180089177  mov     r9d, 0Bh; dwType
0x18008917d  mov     qword ptr [rsp+580h+dwOptions], rax; lpData
0x180089182  xor     r8d, r8d; Reserved
0x180089185  call    cs:__imp_RegSetValueExW
0x18008918b  test    eax, eax
0x18008918d  jz      short loc_1800891A8
0x18008918f  jle     short loc_180089199
0x180089191  movzx   eax, ax
0x180089194  or      eax, 80070000h
0x180089199  xor     edx, edx
0x18008919b  mov     r9d, 0D4h
0x1800891a1  mov     ecx, eax
0x1800891a3  call    Log_HREvent_35
0x1800891a8  lea     rcx, [rsp+580h+var_528]
0x1800891ad  call    ??1?$auto_local_array_ptr@K@@QEAA@XZ; auto_local_array_ptr<ulong>::~auto_local_array_ptr<ulong>(void)
0x1800891b2  mov     rcx, [rsp+580h+hKey]; hKey
0x1800891b7  test    rcx, rcx
0x1800891ba  jz      short loc_1800891C2
0x1800891bc  call    cs:__imp_RegCloseKey
0x1800891c2  lea     rcx, [rsp+580h+var_520]
0x1800891c7  call    tlx___UndoSolo__lambda_e085bcbfc21c86b829db8c6ca1023123_______UndoSolo__lambda_e085bcbfc21c86b829db8c6ca1023123___
0x1800891cc  mov     rcx, r14; lpCriticalSection
0x1800891cf  call    cs:__imp_LeaveCriticalSection
0x1800891d5  mov     eax, ebx
0x1800891d7  mov     rcx, [rbp+480h+var_30]
0x1800891de  xor     rcx, rsp; StackCookie
0x1800891e1  call    __security_check_cookie
0x1800891e6  add     rsp, 568h
0x1800891ed  pop     r14
0x1800891ef  pop     rdi
0x1800891f0  pop     rbx
0x1800891f1  pop     rbp
0x1800891f2  retn
```
