# MergeSdbp_ProcessMergeTargetSubKey(HKEY__ *,ulong,ushort *,ulong,Pca::MergeSdb::Utils::TimeValue,std::list<Pca::MergeSdb::Utils::RegistrationInfo,std::allocator<Pca::MergeSdb::Utils::RegistrationInfo>> &)

- ea: `0x140023638`
- end: `0x1400238b7`
- name: `?MergeSdbp_ProcessMergeTargetSubKey@@YAKPEAUHKEY__@@KPEAGKVTimeValue@Utils@MergeSdb@Pca@@AEAV?$list@VRegistrationInfo@Utils@MergeSdb@Pca@@V?$allocator@VRegistrationInfo@Utils@MergeSdb@Pca@@@std@@@std@@@Z`
- size: `639`
- prototype: `__int64 __fastcall(HKEY hKey, DWORD, WCHAR *, DWORD, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x140024958`

## callees

- `0x1400018b0`
- `0x14001008c`
- `0x140020df0`
- `0x140021ee4`
- `0x140022210`
- `0x140023638`
- `0x14002d660`
- `0x14002e3e2`
- `0x14002e420`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14002375e`
- `ADVAPI32!RegOpenKeyExW` at `0x14002375e`
- `ADVAPI32!RegSetValueExW` at `0x14002380d`
- `ADVAPI32!RegSetValueExW` at `0x14002380d`
- `ADVAPI32!RegEnumKeyExW` at `0x1400236db`
- `ADVAPI32!RegEnumKeyExW` at `0x1400236db`
- `ADVAPI32!RegCloseKey` at `0x14002372e`
- `ADVAPI32!RegCloseKey` at `0x140023886`
- `ADVAPI32!RegCloseKey` at `0x14002372e`
- `ADVAPI32!RegCloseKey` at `0x140023886`
- `KERNEL32!GetLastError` at `0x140023723`
- `KERNEL32!GetLastError` at `0x140023723`
- `KERNEL32!SetLastError` at `0x140023736`
- `KERNEL32!SetLastError` at `0x140023736`

## string_xrefs

- `0x1400237aa`: `Failed to read registration from registry (%d)`
- `0x140023773`: `Failed to open sdb registration '%S' (%d)`

## pseudocode

```c
__int64 __fastcall MergeSdbp_ProcessMergeTargetSubKey(HKEY hKey, DWORD a2, WCHAR *a3, DWORD a4, _QWORD *a5, _QWORD *a6)
{
  LSTATUS RegistrationFromRegistry; // eax
  unsigned int v11; // ebx
  const char *v12; // r9
  __int64 v13; // r8
  HKEY v14; // rdi
  DWORD LastError; // ebx
  LSTATUS v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rbx
  __int64 v19; // rdx
  __int64 v20; // rax
  LPDWORD lpReserved; // [rsp+20h] [rbp-E0h]
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKeya; // [rsp+48h] [rbp-B8h] BYREF
  BYTE Data[16]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v26[64]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v27; // [rsp+A0h] [rbp-60h]
  LPCWSTR lpValueName; // [rsp+C8h] [rbp-38h]
  int v29; // [rsp+F0h] [rbp-10h]
  __int64 v30; // [rsp+F8h] [rbp-8h]

  hKeya = 0;
  memset_0(v26, 0, 0x90u);
  Pca::MergeSdb::Utils::SdbFileData::SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v26);
  v29 = 0;
  v30 = 0;
  cchName = a2;
  RegistrationFromRegistry = RegEnumKeyExW(hKey, a4, a3, &cchName, 0, 0, 0, 0);
  v11 = RegistrationFromRegistry;
  if ( RegistrationFromRegistry )
  {
    if ( RegistrationFromRegistry == 259 )
      goto LABEL_22;
    v12 = "RegEnumKeyExW failed (%d)";
    v13 = 59;
    goto LABEL_4;
  }
  v14 = hKeya;
  if ( hKeya )
  {
    LastError = GetLastError();
    RegCloseKey(v14);
    SetLastError(LastError);
  }
  hKeya = 0;
  v16 = RegOpenKeyExW(hKey, a3, 0, 0x20019u, &hKeya);
  v11 = v16;
  if ( v16 )
  {
    AslLogCallPrintf(1, "MergeSdbp_ProcessMergeTargetSubKey", 68, "Failed to open sdb registration '%S' (%d)", a3, v16);
    goto LABEL_22;
  }
  RegistrationFromRegistry = Pca::MergeSdb::Utils::RegistrationInfo::ReadRegistrationFromRegistry(
                               (Pca::MergeSdb::Utils::RegistrationInfo *)v26,
                               hKeya);
  v11 = RegistrationFromRegistry;
  if ( !RegistrationFromRegistry )
  {
    if ( *a5 < v27 || !v30 || !*(_BYTE *)(v30 + 17) )
    {
      *(_QWORD *)Data = v27;
      if ( !lpValueName )
      {
        v11 = 87;
LABEL_18:
        LODWORD(lpReserved) = v11;
        AslLogCallPrintf(
          1,
          "MergeSdbp_ProcessMergeTargetSubKey",
          90,
          "Failed to add the merge entry to target key (%d)",
          lpReserved);
        goto LABEL_22;
      }
      v11 = RegSetValueExW(hKey, lpValueName, 0, 0xBu, Data, 8u);
      if ( v11 )
        goto LABEL_18;
      v18 = *a6;
      v19 = std::_List_buy<Pca::MergeSdb::Utils::RegistrationInfo>::_Buynode<Pca::MergeSdb::Utils::RegistrationInfo>(
              v17,
              *a6,
              *(_QWORD *)(*a6 + 8LL),
              v26);
      v20 = a6[1];
      if ( v20 == 0x1745D1745D1745CLL )
        std::_Xlength_error("list<T> too long");
      a6[1] = v20 + 1;
      *(_QWORD *)(v18 + 8) = v19;
      **(_QWORD **)(v19 + 8) = v19;
    }
    v11 = 0;
    goto LABEL_22;
  }
  v12 = "Failed to read registration from registry (%d)";
  v13 = 74;
LABEL_4:
  LODWORD(lpReserved) = RegistrationFromRegistry;
  AslLogCallPrintf(1, "MergeSdbp_ProcessMergeTargetSubKey", v13, v12, lpReserved);
LABEL_22:
  Pca::MergeSdb::Utils::SdbFileData::~SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v26);
  if ( hKeya )
    RegCloseKey(hKeya);
  return v11;
}

```

## disassembly

```asm
0x140023638  push    rbp
0x14002363a  push    rbx
0x14002363b  push    rsi
0x14002363c  push    rdi
0x14002363d  push    r14
0x14002363f  push    r15
0x140023641  lea     rbp, [rsp-18h]
0x140023646  sub     rsp, 118h
0x14002364d  mov     rax, cs:__security_cookie
0x140023654  xor     rax, rsp
0x140023657  mov     [rbp+40h+var_40], rax
0x14002365b  mov     edi, r9d
0x14002365e  mov     r14, r8
0x140023661  mov     ebx, edx
0x140023663  mov     r15, rcx
0x140023666  mov     rsi, [rbp+40h+arg_28]
0x14002366a  mov     [rsp+140h+cchName], 0
0x140023672  mov     [rsp+140h+hKey], 0
0x14002367b  xor     edx, edx; Val
0x14002367d  mov     r8d, 90h; Size
0x140023683  lea     rcx, [rsp+140h+var_E0]; void *
0x140023688  call    memset_0
0x14002368d  lea     rcx, [rsp+140h+var_E0]; this
0x140023692  call    ??0SdbFileData@Utils@MergeSdb@Pca@@QEAA@XZ; Pca::MergeSdb::Utils::SdbFileData::SdbFileData(void)
0x140023697  mov     [rbp+40h+var_50], 0
0x14002369e  mov     [rbp+40h+var_48], 0
0x1400236a6  mov     [rsp+140h+cchName], ebx
0x1400236aa  mov     [rsp+140h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1400236b3  mov     [rsp+140h+lpcchClass], 0; lpcchClass
0x1400236bc  mov     [rsp+140h+lpClass], 0; lpClass
0x1400236c5  mov     [rsp+140h+lpReserved], 0; lpReserved
0x1400236ce  lea     r9, [rsp+140h+cchName]; lpcchName
0x1400236d3  mov     r8, r14; lpName
0x1400236d6  mov     edx, edi; dwIndex
0x1400236d8  mov     rcx, r15; hKey
0x1400236db  call    cs:__imp_RegEnumKeyExW
0x1400236e1  mov     ebx, eax
0x1400236e3  test    eax, eax
0x1400236e5  jz      short loc_140023719
0x1400236e7  cmp     eax, 103h
0x1400236ec  jz      loc_140023871
0x1400236f2  lea     r9, aRegenumkeyexwF; "RegEnumKeyExW failed (%d)"
0x1400236f9  mov     r8d, 3Bh ; ';'
0x1400236ff  mov     dword ptr [rsp+140h+lpReserved], eax
0x140023703  lea     rdx, aMergesdbpProce_0; "MergeSdbp_ProcessMergeTargetSubKey"
0x14002370a  mov     ecx, 1
0x14002370f  call    AslLogCallPrintf
0x140023714  jmp     loc_140023871
0x140023719  mov     rdi, [rsp+140h+hKey]
0x14002371e  test    rdi, rdi
0x140023721  jz      short loc_14002373C
0x140023723  call    cs:__imp_GetLastError
0x140023729  mov     ebx, eax
0x14002372b  mov     rcx, rdi; hKey
0x14002372e  call    cs:__imp_RegCloseKey
0x140023734  mov     ecx, ebx; dwErrCode
0x140023736  call    cs:__imp_SetLastError
0x14002373c  mov     [rsp+140h+hKey], 0
0x140023745  lea     rax, [rsp+140h+hKey]
0x14002374a  mov     [rsp+140h+lpReserved], rax; phkResult
0x14002374f  mov     r9d, 20019h; samDesired
0x140023755  xor     r8d, r8d; ulOptions
0x140023758  mov     rdx, r14; lpSubKey
0x14002375b  mov     rcx, r15; hKey
0x14002375e  call    cs:__imp_RegOpenKeyExW
0x140023764  mov     ebx, eax
0x140023766  test    eax, eax
0x140023768  jz      short loc_140023795
0x14002376a  mov     dword ptr [rsp+140h+lpClass], eax
0x14002376e  mov     [rsp+140h+lpReserved], r14
0x140023773  lea     r9, aFailedToOpenSd_2; "Failed to open sdb registration '%S' (%"...
0x14002377a  mov     r8d, 44h ; 'D'
0x140023780  lea     rdx, aMergesdbpProce_0; "MergeSdbp_ProcessMergeTargetSubKey"
0x140023787  lea     ecx, [r8-43h]
0x14002378b  call    AslLogCallPrintf
0x140023790  jmp     loc_140023871
0x140023795  mov     rdx, [rsp+140h+hKey]; hkey
0x14002379a  lea     rcx, [rsp+140h+var_E0]; this
0x14002379f  call    ?ReadRegistrationFromRegistry@RegistrationInfo@Utils@MergeSdb@Pca@@QEAAKPEAUHKEY__@@@Z; Pca::MergeSdb::Utils::RegistrationInfo::ReadRegistrationFromRegistry(HKEY__ *)
0x1400237a4  mov     ebx, eax
0x1400237a6  test    eax, eax
0x1400237a8  jz      short loc_1400237BC
0x1400237aa  lea     r9, aFailedToReadRe_1; "Failed to read registration from regist"...
0x1400237b1  mov     r8d, 4Ah ; 'J'
0x1400237b7  jmp     loc_1400236FF
0x1400237bc  mov     rax, [rbp+40h+var_A0]
0x1400237c0  mov     rcx, [rbp+40h+arg_20]
0x1400237c4  cmp     [rcx], rax
0x1400237c7  jl      short loc_1400237DC
0x1400237c9  mov     rcx, [rbp+40h+var_48]
0x1400237cd  test    rcx, rcx
0x1400237d0  jz      short loc_1400237DC
0x1400237d2  cmp     byte ptr [rcx+11h], 0
0x1400237d6  jnz     loc_14002386F
0x1400237dc  mov     qword ptr [rsp+140h+Data], rax
0x1400237e1  mov     rdx, [rbp+40h+lpValueName]; lpValueName
0x1400237e5  test    rdx, rdx
0x1400237e8  jnz     short loc_1400237EF
0x1400237ea  lea     ebx, [rdx+57h]
0x1400237ed  jmp     short loc_140023819
0x1400237ef  mov     dword ptr [rsp+140h+lpClass], 8; cbData
0x1400237f7  lea     rax, [rsp+140h+Data]
0x1400237fc  mov     [rsp+140h+lpReserved], rax; lpData
0x140023801  mov     r9d, 0Bh; dwType
0x140023807  xor     r8d, r8d; Reserved
0x14002380a  mov     rcx, r15; hKey
0x14002380d  call    cs:__imp_RegSetValueExW
0x140023813  mov     ebx, eax
0x140023815  test    eax, eax
0x140023817  jz      short loc_14002382F
0x140023819  mov     dword ptr [rsp+140h+lpReserved], ebx
0x14002381d  lea     r9, aFailedToAddThe; "Failed to add the merge entry to target"...
0x140023824  mov     r8d, 5Ah ; 'Z'
0x14002382a  jmp     loc_140023703
0x14002382f  mov     rbx, [rsi]
0x140023832  lea     r9, [rsp+140h+var_E0]
0x140023837  mov     r8, [rbx+8]
0x14002383b  mov     rdx, rbx
0x14002383e  call    ??$_Buynode@VRegistrationInfo@Utils@MergeSdb@Pca@@@?$_List_buy@VRegistrationInfo@Utils@MergeSdb@Pca@@V?$allocator@VRegistrationInfo@Utils@MergeSdb@Pca@@@std@@@std@@QEAAPEAU?$_List_node@VRegistrationInfo@Utils@MergeSdb@Pca@@PEAX@1@PEAU21@0$$QEAVRegistrationInfo@Utils@MergeSdb@Pca@@@Z; std::_List_buy<Pca::MergeSdb::Utils::RegistrationInfo>::_Buynode<Pca::MergeSdb::Utils::RegistrationInfo>(std::_List_node<Pca::MergeSdb::Utils::RegistrationInfo,void *> *,std::_List_node<Pca::MergeSdb::Utils::RegistrationInfo,void *> *,Pca::MergeSdb::Utils::RegistrationInfo &&)
0x140023843  mov     rdx, rax
0x140023846  mov     rax, [rsi+8]
0x14002384a  mov     rcx, 1745D1745D1745Ch
0x140023854  sub     rcx, rax
0x140023857  cmp     rcx, 1
0x14002385b  jb      short loc_1400238AA
0x14002385d  inc     rax
0x140023860  mov     [rsi+8], rax
0x140023864  mov     [rbx+8], rdx
0x140023868  mov     rax, [rdx+8]
0x14002386c  mov     [rax], rdx
0x14002386f  xor     ebx, ebx
0x140023871  lea     rcx, [rsp+140h+var_E0]; this
0x140023876  call    ??1SdbFileData@Utils@MergeSdb@Pca@@QEAA@XZ; Pca::MergeSdb::Utils::SdbFileData::~SdbFileData(void)
0x14002387b  nop
0x14002387c  mov     rcx, [rsp+140h+hKey]; hKey
0x140023881  test    rcx, rcx
0x140023884  jz      short loc_14002388C
0x140023886  call    cs:__imp_RegCloseKey
0x14002388c  mov     eax, ebx
0x14002388e  mov     rcx, [rbp+40h+var_40]
0x140023892  xor     rcx, rsp; StackCookie
0x140023895  call    __security_check_cookie
0x14002389a  add     rsp, 118h
0x1400238a1  pop     r15
0x1400238a3  pop     r14
0x1400238a5  pop     rdi
0x1400238a6  pop     rsi
0x1400238a7  pop     rbx
0x1400238a8  pop     rbp
0x1400238a9  retn
0x1400238aa  lea     rcx, aListTTooLong; "list<T> too long"
0x1400238b1  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
