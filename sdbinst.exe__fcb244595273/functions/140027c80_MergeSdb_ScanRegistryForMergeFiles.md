# MergeSdb_ScanRegistryForMergeFiles

- ea: `0x140027c80`
- end: `0x140028151`
- name: `MergeSdb_ScanRegistryForMergeFiles`
- size: `1233`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x140008500`

## callees

- `0x14001008c`
- `0x140021ee4`
- `0x140022014`
- `0x140022210`
- `0x140022d24`
- `0x1400245b8`
- `0x140027c80`
- `0x140028714`
- `0x1400293cc`
- `0x14002a3a8`
- `0x14002a404`
- `0x14002ab60`
- `0x14002ac4c`
- `0x14002acfc`
- `0x14002c10c`
- `0x14002de74`
- `0x14002e3e2`
- `0x14002e420`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140027d98`
- `ADVAPI32!RegCloseKey` at `0x1400280b2`
- `ADVAPI32!RegCloseKey` at `0x1400280f4`
- `ADVAPI32!RegCloseKey` at `0x140027d98`
- `ADVAPI32!RegCloseKey` at `0x1400280b2`
- `ADVAPI32!RegCloseKey` at `0x1400280f4`
- `KERNEL32!GetProcessHeap` at `0x140027ce8`
- `KERNEL32!GetProcessHeap` at `0x140027dac`
- `KERNEL32!GetProcessHeap` at `0x1400280c2`
- `KERNEL32!GetProcessHeap` at `0x140028104`
- `KERNEL32!GetProcessHeap` at `0x14002811d`
- `KERNEL32!GetProcessHeap` at `0x140027ce8`
- `KERNEL32!GetProcessHeap` at `0x140027dac`
- `KERNEL32!GetProcessHeap` at `0x1400280c2`
- `KERNEL32!GetProcessHeap` at `0x140028104`
- `KERNEL32!GetProcessHeap` at `0x14002811d`
- `KERNEL32!HeapFree` at `0x140027cf6`
- `KERNEL32!HeapFree` at `0x140027dba`
- `KERNEL32!HeapFree` at `0x1400280d0`
- `KERNEL32!HeapFree` at `0x140028112`
- `KERNEL32!HeapFree` at `0x14002812b`
- `KERNEL32!HeapFree` at `0x140027cf6`
- `KERNEL32!HeapFree` at `0x140027dba`
- `KERNEL32!HeapFree` at `0x1400280d0`
- `KERNEL32!HeapFree` at `0x140028112`
- `KERNEL32!HeapFree` at `0x14002812b`

## string_xrefs

- `0x140027d6c`: `Failed to open SdbUpdates key (%d)`
- `0x140027cbd`: `Failed to get the merge sdb directory path (%d)`
- `0x140027d16`: `Failed to create the merge sdb directory (%d)`
- `0x140027cce`: `MergeSdb_ScanRegistryForMergeFiles`
- `0x140027d27`: `MergeSdb_ScanRegistryForMergeFiles`
- `0x140027d7d`: `MergeSdb_ScanRegistryForMergeFiles`
- `0x140027e84`: `MergeSdb_ScanRegistryForMergeFiles`
- `0x140027f7d`: `MergeSdb_ScanRegistryForMergeFiles`
- `0x140027fe9`: `MergeSdb_ScanRegistryForMergeFiles`
- `0x140028038`: `MergeSdb_ScanRegistryForMergeFiles`
- `0x14002808c`: `MergeSdb_ScanRegistryForMergeFiles`
- `0x140028081`: `Failed to open SdbUpdate -> InputType '%S' key (%d)`
- `0x14002802d`: `Failed to delete sdb file value '%S' in '%S' (%d).`
- `0x140027fd7`: `Failed to write registration information to registry for '%S': (%d)`
- `0x140027d49`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\SdbUpdates`

## pseudocode

```c
__int64 MergeSdb_ScanRegistryForMergeFiles()
{
  unsigned int MergeSdbDirectoryPath; // eax
  unsigned int v1; // edi
  void *v2; // rbx
  HANDLE ProcessHeap; // rax
  unsigned int v5; // eax
  unsigned int v6; // eax
  HKEY v7; // rsi
  HANDLE v8; // rax
  __int64 *v9; // r14
  const unsigned __int16 *v10; // rdi
  int v11; // eax
  __int64 v12; // rcx
  int AllValues; // eax
  __int64 *v14; // rsi
  __int64 *i; // rdi
  bool v16; // cc
  Pca::MergeSdb::Utils::RegValue *v17; // rcx
  const wchar_t *v18; // r12
  unsigned __int64 v19; // r13
  __int64 v20; // xmm1_8
  int v21; // eax
  __int64 v22; // xmm1_8
  int v23; // eax
  __int64 v24; // r8
  unsigned int updated; // eax
  __int64 v26; // xmm1_8
  HKEY v27; // rdi
  HANDLE v28; // rax
  HKEY v29; // rdi
  HANDLE v30; // rax
  HANDLE v31; // rax
  LPVOID lpMem; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v34; // [rsp+58h] [rbp-A8h]
  HKEY v35[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v36; // [rsp+70h] [rbp-90h]
  _QWORD v37[3]; // [rsp+78h] [rbp-88h] BYREF
  __int128 v38; // [rsp+90h] [rbp-70h] BYREF
  __int64 v39; // [rsp+A0h] [rbp-60h]
  _BYTE v40[144]; // [rsp+B0h] [rbp-50h] BYREF
  int v41; // [rsp+140h] [rbp+40h]
  __int64 v42; // [rsp+148h] [rbp+48h]

  lpMem = 0;
  MergeSdbDirectoryPath = Pca::MergeSdb::Utils::RegistrationInfo::GetMergeSdbDirectoryPath(&lpMem);
  v1 = MergeSdbDirectoryPath;
  if ( MergeSdbDirectoryPath )
  {
    AslLogCallPrintf(
      1,
      "MergeSdb_ScanRegistryForMergeFiles",
      1079,
      "Failed to get the merge sdb directory path (%d)",
      MergeSdbDirectoryPath);
    v2 = lpMem;
LABEL_3:
    if ( v2 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v2);
    }
    return v1;
  }
  v2 = lpMem;
  v5 = Pca::MergeSdb::Utils::RegistrationInfo::EnsureDirectory((const unsigned __int16 *)lpMem);
  v1 = v5;
  if ( v5 )
  {
    AslLogCallPrintf(1, "MergeSdb_ScanRegistryForMergeFiles", 1084, "Failed to create the merge sdb directory (%d)", v5);
    goto LABEL_3;
  }
  v34 = 0;
  hKey[0] = 0;
  hKey[1] = 0;
  v6 = Pca::MergeSdb::Utils::RegKey::AssignFromKeyAndSubPath(
         (Pca::MergeSdb::Utils::RegKey *)hKey,
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\SdbUpdates");
  v1 = v6;
  if ( v6 )
  {
    AslLogCallPrintf(1, "MergeSdb_ScanRegistryForMergeFiles", 1097, "Failed to open SdbUpdates key (%d)", v6);
    if ( hKey[1] )
      RegCloseKey(hKey[1]);
    v7 = hKey[0];
    if ( hKey[0] )
    {
      v8 = GetProcessHeap();
      HeapFree(v8, 0, v7);
    }
    goto LABEL_3;
  }
  v9 = &qword_140031120;
  do
  {
    v10 = (const unsigned __int16 *)v9[1];
    v36 = 0;
    v35[0] = 0;
    v35[1] = 0;
    Pca::MergeSdb::Utils::RegKey::Reset((Pca::MergeSdb::Utils::RegKey *)v35);
    if ( !hKey[0] )
    {
      v11 = 5023;
LABEL_48:
      if ( v11 != 2 )
        AslLogCallPrintf(
          1,
          "MergeSdb_ScanRegistryForMergeFiles",
          1107,
          "Failed to open SdbUpdate -> InputType '%S' key (%d)",
          (const wchar_t *)v9[1],
          v11);
      goto LABEL_50;
    }
    if ( HIBYTE(v34) && !(_BYTE)v34 )
    {
      v11 = 2;
      goto LABEL_48;
    }
    if ( !Pca::MergeSdb::Utils::RegKey::EnsureInternalHandle((Pca::MergeSdb::Utils::RegKey *)hKey) )
    {
      v11 = (_BYTE)v34 != 0 ? 1359 : 2;
      goto LABEL_48;
    }
    v11 = Pca::MergeSdb::Utils::RegKey::AssignFromKeyAndSubPath((Pca::MergeSdb::Utils::RegKey *)v35, hKey[1], v10);
    if ( v11 )
      goto LABEL_48;
    v37[1] = 0;
    v37[0] = std::_List_alloc<0,std::_List_base_types<Pca::MergeSdb::Utils::RegValue>>::_Buynode0(v12, 0, 0);
    AllValues = Pca::MergeSdb::Utils::RegKey::GetAllValues((Pca::MergeSdb::Utils::RegKey *)v35);
    if ( AllValues )
    {
      AslLogCallPrintf(
        1,
        "MergeSdb_ScanRegistryForMergeFiles",
        1114,
        "Failed to get the values for InputType '%S' key (%d)",
        (const wchar_t *)v9[1],
        AllValues);
      goto LABEL_23;
    }
    v14 = (__int64 *)v37[0];
    for ( i = *(__int64 **)v37[0]; i != v14; i = (__int64 *)*i )
    {
      v16 = *((_DWORD *)i + 6) <= 3u;
      v17 = (Pca::MergeSdb::Utils::RegValue *)(i + 2);
      lpMem = 0;
      if ( v16 || !*(_QWORD *)v17 )
        v18 = 0;
      else
        v18 = (const wchar_t *)(*(_QWORD *)v17 + 12LL);
      if ( *v18 )
      {
        if ( Pca::MergeSdb::Utils::RegValue::GetValueValue(v17, (const unsigned __int16 **)&lpMem) )
          v19 = (unsigned __int64)lpMem & -(__int64)(*(_WORD *)lpMem != 0);
        else
          v19 = (unsigned __int64)lpMem;
        memset_0(v40, 0, sizeof(v40));
        Pca::MergeSdb::Utils::SdbFileData::SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v40);
        v20 = v9[2];
        v38 = *(_OWORD *)v9;
        v41 = 0;
        v42 = 0;
        v39 = v20;
        v21 = Pca::MergeSdb::Utils::RegistrationInfo::GatherInformationForFile(v40, v18, v19, &v38);
        if ( v21 )
        {
          AslLogCallPrintf(
            1,
            "MergeSdb_ScanRegistryForMergeFiles",
            1130,
            "Failed to gather information for sdb file '%S' (%d)",
            v18,
            v21);
          if ( *((_BYTE *)v9 + 16) )
          {
            v22 = v9[2];
            v38 = *(_OWORD *)v9;
            v39 = v22;
            v23 = MergeSdbp_DeleteRegistrySdbFileValue(v18, &v38);
            if ( v23 )
            {
              v24 = 1135;
              goto LABEL_43;
            }
          }
        }
        else
        {
          updated = Pca::MergeSdb::Utils::RegistrationInfo::AddOrUpdateRegistration((Pca::MergeSdb::Utils::RegistrationInfo *)v40);
          if ( updated )
            AslLogCallPrintf(
              1,
              "MergeSdb_ScanRegistryForMergeFiles",
              1143,
              "Failed to write registration information to registry for '%S': (%d)",
              v18,
              updated);
          if ( *((_BYTE *)v9 + 16) )
          {
            v26 = v9[2];
            v38 = *(_OWORD *)v9;
            v39 = v26;
            v23 = MergeSdbp_DeleteRegistrySdbFileValue(v18, &v38);
            if ( v23 )
            {
              v24 = 1151;
LABEL_43:
              AslLogCallPrintf(
                1,
                "MergeSdb_ScanRegistryForMergeFiles",
                v24,
                "Failed to delete sdb file value '%S' in '%S' (%d).",
                v18,
                (const wchar_t *)v9[1],
                v23);
            }
          }
        }
        Pca::MergeSdb::Utils::SdbFileData::~SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v40);
        continue;
      }
    }
    Pca::MergeSdb::Utils::RegKey::Reset((Pca::MergeSdb::Utils::RegKey *)v35);
LABEL_23:
    std::list<Pca::MergeSdb::Utils::RegValue>::~list<Pca::MergeSdb::Utils::RegValue>(v37);
LABEL_50:
    if ( v35[1] )
      RegCloseKey(v35[1]);
    v27 = v35[0];
    if ( v35[0] )
    {
      v28 = GetProcessHeap();
      HeapFree(v28, 0, v27);
    }
    v9 += 3;
  }
  while ( v9 != &qword_140031198 );
  if ( hKey[1] )
    RegCloseKey(hKey[1]);
  v29 = hKey[0];
  if ( hKey[0] )
  {
    v30 = GetProcessHeap();
    HeapFree(v30, 0, v29);
  }
  if ( v2 )
  {
    v31 = GetProcessHeap();
    HeapFree(v31, 0, v2);
  }
  return 0;
}

```

## disassembly

```asm
0x140027c80  push    rbp
0x140027c82  push    rbx
0x140027c83  push    rsi
0x140027c84  push    rdi
0x140027c85  push    r12
0x140027c87  push    r13
0x140027c89  push    r14
0x140027c8b  lea     rbp, [rsp-60h]
0x140027c90  sub     rsp, 160h
0x140027c97  mov     rax, cs:__security_cookie
0x140027c9e  xor     rax, rsp
0x140027ca1  mov     [rbp+90h+var_40], rax
0x140027ca5  xor     r13d, r13d
0x140027ca8  lea     rcx, [rsp+190h+lpMem]
0x140027cad  mov     [rsp+190h+lpMem], r13
0x140027cb2  call    ?GetMergeSdbDirectoryPath@RegistrationInfo@Utils@MergeSdb@Pca@@SAKAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Pca::MergeSdb::Utils::RegistrationInfo::GetMergeSdbDirectoryPath(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x140027cb7  mov     edi, eax
0x140027cb9  test    eax, eax
0x140027cbb  jz      short loc_140027D03
0x140027cbd  lea     r9, aFailedToGetThe_5; "Failed to get the merge sdb directory p"...
0x140027cc4  mov     dword ptr [rsp+190h+var_170], eax
0x140027cc8  mov     r8d, 437h
0x140027cce  lea     rdx, aMergesdbScanre; "MergeSdb_ScanRegistryForMergeFiles"
0x140027cd5  lea     ecx, [r13+1]
0x140027cd9  call    AslLogCallPrintf
0x140027cde  mov     rbx, [rsp+190h+lpMem]
0x140027ce3  test    rbx, rbx
0x140027ce6  jz      short loc_140027CFC
0x140027ce8  call    cs:__imp_GetProcessHeap
0x140027cee  mov     r8, rbx; lpMem
0x140027cf1  xor     edx, edx; dwFlags
0x140027cf3  mov     rcx, rax; hHeap
0x140027cf6  call    cs:__imp_HeapFree
0x140027cfc  mov     eax, edi
0x140027cfe  jmp     loc_140028133
0x140027d03  mov     rbx, [rsp+190h+lpMem]
0x140027d08  mov     rcx, rbx; unsigned __int16 *
0x140027d0b  call    ?EnsureDirectory@RegistrationInfo@Utils@MergeSdb@Pca@@SAKPEBG@Z; Pca::MergeSdb::Utils::RegistrationInfo::EnsureDirectory(ushort const *)
0x140027d10  mov     edi, eax
0x140027d12  test    eax, eax
0x140027d14  jz      short loc_140027D3A
0x140027d16  lea     r9, aFailedToCreate_11; "Failed to create the merge sdb director"...
0x140027d1d  mov     dword ptr [rsp+190h+var_170], eax
0x140027d21  mov     r8d, 43Ch
0x140027d27  lea     rdx, aMergesdbScanre; "MergeSdb_ScanRegistryForMergeFiles"
0x140027d2e  mov     ecx, 1
0x140027d33  call    AslLogCallPrintf
0x140027d38  jmp     short loc_140027CE3
0x140027d3a  xorps   xmm0, xmm0
0x140027d3d  mov     [rsp+190h+var_138], r13w
0x140027d43  movdqu  xmmword ptr [rsp+190h+hKey], xmm0
0x140027d49  lea     r8, aSoftwareMicros_11; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x140027d50  mov     [rsp+190h+hKey+8], r13
0x140027d55  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x140027d5c  lea     rcx, [rsp+190h+hKey]; this
0x140027d61  call    ?AssignFromKeyAndSubPath@RegKey@Utils@MergeSdb@Pca@@QEAAKPEAUHKEY__@@PEBG@Z; Pca::MergeSdb::Utils::RegKey::AssignFromKeyAndSubPath(HKEY__ *,ushort const *)
0x140027d66  mov     edi, eax
0x140027d68  test    eax, eax
0x140027d6a  jz      short loc_140027DC5
0x140027d6c  lea     r9, aFailedToOpenSd; "Failed to open SdbUpdates key (%d)"
0x140027d73  mov     dword ptr [rsp+190h+var_170], eax
0x140027d77  mov     r8d, 449h
0x140027d7d  lea     rdx, aMergesdbScanre; "MergeSdb_ScanRegistryForMergeFiles"
0x140027d84  mov     ecx, 1
0x140027d89  call    AslLogCallPrintf
0x140027d8e  mov     rcx, [rsp+190h+hKey+8]; hKey
0x140027d93  test    rcx, rcx
0x140027d96  jz      short loc_140027D9E
0x140027d98  call    cs:__imp_RegCloseKey
0x140027d9e  mov     rsi, [rsp+190h+hKey]
0x140027da3  test    rsi, rsi
0x140027da6  jz      loc_140027CE3
0x140027dac  call    cs:__imp_GetProcessHeap
0x140027db2  mov     r8, rsi; lpMem
0x140027db5  xor     edx, edx; dwFlags
0x140027db7  mov     rcx, rax; hHeap
0x140027dba  call    cs:__imp_HeapFree
0x140027dc0  jmp     loc_140027CE3
0x140027dc5  lea     r14, qword_140031120
0x140027dcc  mov     rdi, [r14+8]
0x140027dd0  lea     rcx, [rsp+190h+var_130]; this
0x140027dd5  xorps   xmm0, xmm0
0x140027dd8  mov     [rsp+190h+var_120], 0
0x140027ddf  movdqu  xmmword ptr [rsp+190h+var_130], xmm0
0x140027de5  mov     [rsp+190h+var_130+8], r13
0x140027dea  call    ?Reset@RegKey@Utils@MergeSdb@Pca@@QEAAXXZ; Pca::MergeSdb::Utils::RegKey::Reset(void)
0x140027def  cmp     [rsp+190h+hKey], r13
0x140027df4  jz      loc_140028073
0x140027dfa  cmp     byte ptr [rsp+190h+var_138+1], r13b
0x140027dff  jz      short loc_140027E12
0x140027e01  cmp     byte ptr [rsp+190h+var_138], r13b
0x140027e06  jnz     short loc_140027E12
0x140027e08  mov     eax, 2
0x140027e0d  jmp     loc_140028078
0x140027e12  lea     rcx, [rsp+190h+hKey]; this
0x140027e17  call    ?EnsureInternalHandle@RegKey@Utils@MergeSdb@Pca@@AEAA_NXZ; Pca::MergeSdb::Utils::RegKey::EnsureInternalHandle(void)
0x140027e1c  test    al, al
0x140027e1e  jnz     short loc_140027E35
0x140027e20  mov     al, byte ptr [rsp+190h+var_138]
0x140027e24  neg     al
0x140027e26  sbb     eax, eax
0x140027e28  and     eax, 54Dh
0x140027e2d  add     eax, 2
0x140027e30  jmp     loc_140028078
0x140027e35  mov     rdx, [rsp+190h+hKey+8]; HKEY
0x140027e3a  lea     rcx, [rsp+190h+var_130]; this
0x140027e3f  mov     r8, rdi; unsigned __int16 *
0x140027e42  call    ?AssignFromKeyAndSubPath@RegKey@Utils@MergeSdb@Pca@@QEAAKPEAUHKEY__@@PEBG@Z; Pca::MergeSdb::Utils::RegKey::AssignFromKeyAndSubPath(HKEY__ *,ushort const *)
0x140027e47  test    eax, eax
0x140027e49  jnz     loc_140028078
0x140027e4f  xor     r8d, r8d
0x140027e52  mov     [rbp+90h+var_110], r13
0x140027e56  xor     edx, edx
0x140027e58  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@VRegValue@Utils@MergeSdb@Pca@@V?$allocator@VRegValue@Utils@MergeSdb@Pca@@@std@@@std@@@std@@QEAAPEAU?$_List_node@VRegValue@Utils@MergeSdb@Pca@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<Pca::MergeSdb::Utils::RegValue>>::_Buynode0(std::_List_node<Pca::MergeSdb::Utils::RegValue,void *> *,std::_List_node<Pca::MergeSdb::Utils::RegValue,void *> *)
0x140027e5d  lea     rdx, [rsp+190h+var_118]
0x140027e62  mov     [rsp+190h+var_118], rax
0x140027e67  lea     rcx, [rsp+190h+var_130]; this
0x140027e6c  call    ?GetAllValues@RegKey@Utils@MergeSdb@Pca@@QEAAKAEAV?$list@VRegValue@Utils@MergeSdb@Pca@@V?$allocator@VRegValue@Utils@MergeSdb@Pca@@@std@@@std@@@Z; Pca::MergeSdb::Utils::RegKey::GetAllValues(std::list<Pca::MergeSdb::Utils::RegValue> &)
0x140027e71  test    eax, eax
0x140027e73  jz      short loc_140027EAF
0x140027e75  mov     dword ptr [rsp+190h+var_168], eax
0x140027e79  lea     r9, aFailedToGetThe_3; "Failed to get the values for InputType "...
0x140027e80  mov     rax, [r14+8]
0x140027e84  lea     rdx, aMergesdbScanre; "MergeSdb_ScanRegistryForMergeFiles"
0x140027e8b  mov     r8d, 45Ah
0x140027e91  mov     [rsp+190h+var_170], rax
0x140027e96  mov     ecx, 1
0x140027e9b  call    AslLogCallPrintf
0x140027ea0  lea     rcx, [rsp+190h+var_118]
0x140027ea5  call    ??1?$list@VRegValue@Utils@MergeSdb@Pca@@V?$allocator@VRegValue@Utils@MergeSdb@Pca@@@std@@@std@@QEAA@XZ; std::list<Pca::MergeSdb::Utils::RegValue>::~list<Pca::MergeSdb::Utils::RegValue>(void)
0x140027eaa  jmp     loc_1400280A8
0x140027eaf  mov     rsi, [rsp+190h+var_118]
0x140027eb4  mov     rdi, [rsi]
0x140027eb7  cmp     rdi, rsi
0x140027eba  jz      loc_140028064
0x140027ec0  cmp     dword ptr [rdi+18h], 3
0x140027ec4  lea     rcx, [rdi+10h]; this
0x140027ec8  mov     [rsp+190h+lpMem], r13
0x140027ecd  jbe     short loc_140027EDD
0x140027ecf  mov     r12, [rcx]
0x140027ed2  test    r12, r12
0x140027ed5  jz      short loc_140027EDD
0x140027ed7  add     r12, 0Ch
0x140027edb  jmp     short loc_140027EE0
0x140027edd  mov     r12, r13
0x140027ee0  cmp     [r12], r13w
0x140027ee5  jz      loc_14002805C
0x140027eeb  lea     rdx, [rsp+190h+lpMem]; unsigned __int16 **
0x140027ef0  call    ?GetValueValue@RegValue@Utils@MergeSdb@Pca@@QEBA_NAEAPEBG@Z; Pca::MergeSdb::Utils::RegValue::GetValueValue(ushort const * &)
0x140027ef5  test    al, al
0x140027ef7  jz      short loc_140027F0C
0x140027ef9  mov     rcx, [rsp+190h+lpMem]
0x140027efe  movzx   eax, word ptr [rcx]
0x140027f01  neg     ax
0x140027f04  sbb     r13, r13
0x140027f07  and     r13, rcx
0x140027f0a  jmp     short loc_140027F11
0x140027f0c  mov     r13, [rsp+190h+lpMem]
0x140027f11  xor     edx, edx; Val
0x140027f13  lea     rcx, [rbp+90h+var_E0]; void *
0x140027f17  mov     r8d, 90h; Size
0x140027f1d  call    memset_0
0x140027f22  lea     rcx, [rbp+90h+var_E0]; this
0x140027f26  call    ??0SdbFileData@Utils@MergeSdb@Pca@@QEAA@XZ; Pca::MergeSdb::Utils::SdbFileData::SdbFileData(void)
0x140027f2b  movups  xmm0, xmmword ptr [r14]
0x140027f2f  lea     r9, [rbp+90h+var_100]
0x140027f33  mov     r8, r13
0x140027f36  movsd   xmm1, qword ptr [r14+10h]
0x140027f3c  lea     rcx, [rbp+90h+var_E0]
0x140027f40  mov     rdx, r12
0x140027f43  movaps  [rbp+90h+var_100], xmm0
0x140027f47  mov     [rbp+90h+var_50], 0
0x140027f4e  mov     [rbp+90h+var_48], 0
0x140027f56  movsd   [rbp+90h+var_F0], xmm1
0x140027f5b  call    ?GatherInformationForFile@RegistrationInfo@Utils@MergeSdb@Pca@@QEAAKPEBG0UMergeInputTypeConfig@34@@Z; Pca::MergeSdb::Utils::RegistrationInfo::GatherInformationForFile(ushort const *,ushort const *,Pca::MergeSdb::MergeInputTypeConfig)
0x140027f60  xor     r13d, r13d
0x140027f63  test    eax, eax
0x140027f65  jz      short loc_140027FC6
0x140027f67  mov     dword ptr [rsp+190h+var_168], eax
0x140027f6b  lea     r9, aFailedToGather; "Failed to gather information for sdb fi"...
0x140027f72  mov     r8d, 46Ah
0x140027f78  mov     [rsp+190h+var_170], r12
0x140027f7d  lea     rdx, aMergesdbScanre; "MergeSdb_ScanRegistryForMergeFiles"
0x140027f84  lea     ecx, [r13+1]
0x140027f88  call    AslLogCallPrintf
0x140027f8d  cmp     [r14+10h], r13b
0x140027f91  jz      loc_140028053
0x140027f97  movups  xmm0, xmmword ptr [r14]
0x140027f9b  lea     rdx, [rbp+90h+var_100]
0x140027f9f  mov     rcx, r12
0x140027fa2  movsd   xmm1, qword ptr [r14+10h]
0x140027fa8  movaps  [rbp+90h+var_100], xmm0
0x140027fac  movsd   [rbp+90h+var_F0], xmm1
0x140027fb1  call    ?MergeSdbp_DeleteRegistrySdbFileValue@@YAKPEBGUMergeInputTypeConfig@MergeSdb@Pca@@@Z; MergeSdbp_DeleteRegistrySdbFileValue(ushort const *,Pca::MergeSdb::MergeInputTypeConfig)
0x140027fb6  test    eax, eax
0x140027fb8  jz      loc_140028053
0x140027fbe  mov     r8d, 46Fh
0x140027fc4  jmp     short loc_140028029
0x140027fc6  lea     rcx, [rbp+90h+var_E0]; this
0x140027fca  call    ?AddOrUpdateRegistration@RegistrationInfo@Utils@MergeSdb@Pca@@QEAAKXZ; Pca::MergeSdb::Utils::RegistrationInfo::AddOrUpdateRegistration(void)
0x140027fcf  test    eax, eax
0x140027fd1  jz      short loc_140027FFA
0x140027fd3  mov     dword ptr [rsp+190h+var_168], eax
0x140027fd7  lea     r9, aFailedToWriteR_0; "Failed to write registration informatio"...
0x140027fde  mov     r8d, 477h
0x140027fe4  mov     [rsp+190h+var_170], r12
0x140027fe9  lea     rdx, aMergesdbScanre; "MergeSdb_ScanRegistryForMergeFiles"
0x140027ff0  mov     ecx, 1
0x140027ff5  call    AslLogCallPrintf
0x140027ffa  cmp     [r14+10h], r13b
0x140027ffe  jz      short loc_140028053
0x140028000  movups  xmm0, xmmword ptr [r14]
0x140028004  lea     rdx, [rbp+90h+var_100]
0x140028008  mov     rcx, r12
0x14002800b  movsd   xmm1, qword ptr [r14+10h]
0x140028011  movaps  [rbp+90h+var_100], xmm0
0x140028015  movsd   [rbp+90h+var_F0], xmm1
0x14002801a  call    ?MergeSdbp_DeleteRegistrySdbFileValue@@YAKPEBGUMergeInputTypeConfig@MergeSdb@Pca@@@Z; MergeSdbp_DeleteRegistrySdbFileValue(ushort const *,Pca::MergeSdb::MergeInputTypeConfig)
0x14002801f  test    eax, eax
0x140028021  jz      short loc_140028053
0x140028023  mov     r8d, 47Fh
0x140028029  mov     [rsp+190h+var_160], eax
0x14002802d  lea     r9, aFailedToDelete_9; "Failed to delete sdb file value '%S' in"...
0x140028034  mov     rax, [r14+8]
0x140028038  lea     rdx, aMergesdbScanre; "MergeSdb_ScanRegistryForMergeFiles"
0x14002803f  mov     [rsp+190h+var_168], rax
0x140028044  mov     ecx, 1
0x140028049  mov     [rsp+190h+var_170], r12
0x14002804e  call    AslLogCallPrintf
0x140028053  lea     rcx, [rbp+90h+var_E0]; this
0x140028057  call    ??1SdbFileData@Utils@MergeSdb@Pca@@QEAA@XZ; Pca::MergeSdb::Utils::SdbFileData::~SdbFileData(void)
0x14002805c  mov     rdi, [rdi]
0x14002805f  jmp     loc_140027EB7
0x140028064  lea     rcx, [rsp+190h+var_130]; this
0x140028069  call    ?Reset@RegKey@Utils@MergeSdb@Pca@@QEAAXXZ; Pca::MergeSdb::Utils::RegKey::Reset(void)
0x14002806e  jmp     loc_140027EA0
0x140028073  mov     eax, 139Fh
0x140028078  cmp     eax, 2
0x14002807b  jz      short loc_1400280A8
0x14002807d  mov     dword ptr [rsp+190h+var_168], eax
0x140028081  lea     r9, aFailedToOpenSd_0; "Failed to open SdbUpdate -> InputType '"...
0x140028088  mov     rax, [r14+8]
0x14002808c  lea     rdx, aMergesdbScanre; "MergeSdb_ScanRegistryForMergeFiles"
0x140028093  mov     r8d, 453h
0x140028099  mov     [rsp+190h+var_170], rax
0x14002809e  mov     ecx, 1
0x1400280a3  call    AslLogCallPrintf
0x1400280a8  mov     rcx, [rsp+190h+var_130+8]; hKey
0x1400280ad  test    rcx, rcx
0x1400280b0  jz      short loc_1400280B8
0x1400280b2  call    cs:__imp_RegCloseKey
0x1400280b8  mov     rdi, [rsp+190h+var_130]
0x1400280bd  test    rdi, rdi
0x1400280c0  jz      short loc_1400280D6
0x1400280c2  call    cs:__imp_GetProcessHeap
0x1400280c8  mov     r8, rdi; lpMem
0x1400280cb  xor     edx, edx; dwFlags
0x1400280cd  mov     rcx, rax; hHeap
0x1400280d0  call    cs:__imp_HeapFree
0x1400280d6  add     r14, 18h
0x1400280da  lea     rax, qword_140031198
0x1400280e1  cmp     r14, rax
0x1400280e4  jnz     loc_140027DCC
0x1400280ea  mov     rcx, [rsp+190h+hKey+8]; hKey
0x1400280ef  test    rcx, rcx
0x1400280f2  jz      short loc_1400280FA
0x1400280f4  call    cs:__imp_RegCloseKey
0x1400280fa  mov     rdi, [rsp+190h+hKey]
0x1400280ff  test    rdi, rdi
0x140028102  jz      short loc_140028118
0x140028104  call    cs:__imp_GetProcessHeap
0x14002810a  mov     r8, rdi; lpMem
0x14002810d  xor     edx, edx; dwFlags
0x14002810f  mov     rcx, rax; hHeap
0x140028112  call    cs:__imp_HeapFree
0x140028118  test    rbx, rbx
0x14002811b  jz      short loc_140028131
0x14002811d  call    cs:__imp_GetProcessHeap
0x140028123  mov     r8, rbx; lpMem
0x140028126  xor     edx, edx; dwFlags
0x140028128  mov     rcx, rax; hHeap
0x14002812b  call    cs:__imp_HeapFree
0x140028131  xor     eax, eax
0x140028133  mov     rcx, [rbp+90h+var_40]
0x140028137  xor     rcx, rsp; StackCookie
0x14002813a  call    __security_check_cookie
0x14002813f  add     rsp, 160h
0x140028146  pop     r14
0x140028148  pop     r13
0x14002814a  pop     r12
0x14002814c  pop     rdi
0x14002814d  pop     rsi
0x14002814e  pop     rbx
0x14002814f  pop     rbp
0x140028150  retn
```
