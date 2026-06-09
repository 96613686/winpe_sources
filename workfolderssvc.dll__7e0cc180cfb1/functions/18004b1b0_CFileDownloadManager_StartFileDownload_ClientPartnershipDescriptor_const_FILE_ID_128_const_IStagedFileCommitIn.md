# CFileDownloadManager::StartFileDownload(ClientPartnershipDescriptor const &,_FILE_ID_128 const &,IStagedFileCommitInfo *,ulong,ISyncShareManagerProgressCallback *)

- ea: `0x18004b1b0`
- end: `0x18004b6b4`
- name: `?StartFileDownload@CFileDownloadManager@@UEAAJAEBVClientPartnershipDescriptor@@AEBU_FILE_ID_128@@PEAUIStagedFileCommitInfo@@KPEAUISyncShareManagerProgressCallback@@@Z`
- size: `1284`
- prototype: `int(CFileDownloadManager *__hidden this, const struct ClientPartnershipDescriptor *, const struct _FILE_ID_128 *, struct IStagedFileCommitInfo *, unsigned int, struct ISyncShareManagerProgressCallback *)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180003604`
- `0x180007e10`
- `0x180008b60`
- `0x180009158`
- `0x180010ee0`
- `0x180011314`
- `0x18001133c`
- `0x180049260`
- `0x18004955c`
- `0x18004996c`
- `0x18004a0ec`
- `0x18004b1b0`
- `0x18004b814`
- `0x18013e010`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x18004b29e`
- `KERNEL32!GetCurrentProcessId` at `0x18004b29e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b3ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b419`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b663`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b3ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b419`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b663`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall CFileDownloadManager::StartFileDownload(
        CFileDownloadManager *this,
        const struct ClientPartnershipDescriptor *a2,
        const struct _FILE_ID_128 *a3,
        struct IStagedFileCommitInfo *a4,
        unsigned int a5,
        struct ISyncShareManagerProgressCallback *a6)
{
  _BYTE *v10; // rax
  int v11; // ebx
  char v12; // al
  __int16 v13; // cx
  __int64 *v14; // r12
  __int64 (__fastcall *v15)(char *, LPCRITICAL_SECTION *); // rax
  char *v16; // rcx
  char v17; // al
  CFileDownloadManager *v18; // rcx
  __int64 v19; // rax
  __int64 v20; // r9
  __int64 v21; // rax
  __int64 v23; // rax
  __int64 v24; // r9
  __int64 v25; // rax
  unsigned int v26; // ebx
  int v27; // [rsp+38h] [rbp-100h] BYREF
  int v28; // [rsp+3Ch] [rbp-FCh]
  char v29; // [rsp+40h] [rbp-F8h]
  const char *v30; // [rsp+48h] [rbp-F0h]
  __int64 v31; // [rsp+50h] [rbp-E8h]
  LPCRITICAL_SECTION v32[2]; // [rsp+60h] [rbp-D8h] BYREF
  int pExceptionObject; // [rsp+70h] [rbp-C8h] BYREF
  int v34; // [rsp+74h] [rbp-C4h] BYREF
  int v35; // [rsp+78h] [rbp-C0h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+80h] [rbp-B8h] BYREF
  char v37; // [rsp+88h] [rbp-B0h]
  struct _FILE_ID_128 v38; // [rsp+A0h] [rbp-98h] BYREF
  struct _FILE_ID_128 v39; // [rsp+B0h] [rbp-88h] BYREF
  struct _FILE_ID_128 v40; // [rsp+C0h] [rbp-78h] BYREF
  struct _FILE_ID_128 v41; // [rsp+D0h] [rbp-68h] BYREF
  struct _FILE_ID_128 v42; // [rsp+E0h] [rbp-58h] BYREF
  struct _FILE_ID_128 v43; // [rsp+F0h] [rbp-48h] BYREF

  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) == 0 )
      goto LABEL_8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, WPP_9fffca09c132345368abadf44793045b_Traceguids);
      v10 = WPP_GLOBAL_Control;
    }
  }
  if ( (v10[68] & 8) != 0 && v10[65] >= 6u )
  {
    v11 = 1;
    v12 = 1;
    goto LABEL_9;
  }
LABEL_8:
  v12 = 0;
  v11 = 1;
LABEL_9:
  v27 = 0;
  v28 = 60;
  v29 = v12;
  v30 = "CFileDownloadManager::StartFileDownload";
  v31 = 0;
  if ( !a4 )
  {
    v27 = -2147024809;
    HIWORD(v28) = 67;
    pExceptionObject = -2147024809;
    throw (long *)&pExceptionObject;
  }
  v27 = 0;
  LOWORD(v28) = 67;
  if ( a5 != GetCurrentProcessId() )
    v11 = 0;
  CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(&lpCriticalSection, (char *)this + 184);
  if ( 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)this + 34) - *((_QWORD *)this + 33)) >> 3) >= 0xA )
  {
    ATL::CComPtr<IStagedFileCommitInfo>::CComPtr<IStagedFileCommitInfo>(v32, a4);
    if ( v11 )
    {
      v27 = EcsQueue<ATL::CComPtr<IStagedFileCommitInfo>>::EnQueue((char *)this + 288, v32);
      ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(v32);
      v13 = 86;
      if ( v27 < 0 )
      {
        HIWORD(v28) = 86;
        v34 = v27;
        throw (long *)&v34;
      }
    }
    else
    {
      v27 = EcsQueue<ATL::CComPtr<IStagedFileCommitInfo>>::EnQueue((char *)this + 312, v32);
      ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(v32);
      v13 = 91;
      if ( v27 < 0 )
      {
        HIWORD(v28) = 91;
        v35 = v27;
        throw (long *)&v35;
      }
    }
    LOWORD(v28) = v13;
    if ( v37 )
    {
      LeaveCriticalSection(lpCriticalSection);
      v37 = 0;
    }
    goto LABEL_34;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_ii(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      12,
      WPP_9fffca09c132345368abadf44793045b_Traceguids,
      *(_QWORD *)&a3->Identifier[8],
      *(_QWORD *)a3->Identifier);
  }
  if ( v37 )
  {
    LeaveCriticalSection(lpCriticalSection);
    v37 = 0;
  }
  v14 = (__int64 *)((char *)this - 8);
  v15 = *(__int64 (__fastcall **)(char *, LPCRITICAL_SECTION *))(*((_QWORD *)this - 1) + 32LL);
  v16 = (char *)this - 8;
  if ( v11 )
  {
    *(struct _FILE_ID_128 *)v32 = *a3;
    v17 = v15(v16, v32);
    v18 = (CFileDownloadManager *)((char *)this - 8);
    if ( v17 )
    {
      v40 = *a3;
      CFileDownloadManager::AddOrUpdateActiveDownload(v18, &v40, a4);
      CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v27);
      return 0;
    }
    v38 = *a3;
    CFileDownloadManager::AddOrUpdateActiveDownload(v18, &v38, a4);
    v19 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)a2 + 416);
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v20 + 32LL))(v20, v19);
    v21 = *v14;
    v39 = *a3;
    if ( !(*(unsigned __int8 (__fastcall **)(char *, struct _FILE_ID_128 *))(v21 + 32))((char *)this - 8, &v39) )
      goto LABEL_34;
  }
  else
  {
    v41 = *a3;
    if ( (unsigned __int8)v15(v16, (LPCRITICAL_SECTION *)&v41) )
    {
      v23 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)a2 + 416);
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v24 + 32LL))(v24, v23);
      v25 = *v14;
      v42 = *a3;
      if ( !(*(unsigned __int8 (__fastcall **)(char *, struct _FILE_ID_128 *))(v25 + 32))((char *)this - 8, &v42) )
      {
LABEL_34:
        CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v27);
        return 0;
      }
    }
  }
  v43 = *a3;
  CFileDownloadManager::AddOrUpdateActiveDownload((CFileDownloadManager *)((char *)this - 8), &v43, a4);
  if ( v11 )
  {
    CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(v32, (char *)this + 144);
    v26 = CFileDownloadManager::DownloadInternal((CFileDownloadManager *)((char *)this - 8), a2, a3, a4, v11, a6);
    if ( LOBYTE(v32[1]) )
    {
      LeaveCriticalSection(v32[0]);
      LOBYTE(v32[1]) = 0;
    }
  }
  else
  {
    v26 = CFileDownloadManager::DownloadInternal((CFileDownloadManager *)((char *)this - 8), a2, a3, a4, 0, a6);
  }
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v27);
  return v26;
}

```

## disassembly

```asm
0x18004b1b0  mov     rax, rsp
0x18004b1b3  mov     [rax+20h], r9
0x18004b1b7  mov     [rax+18h], r8
0x18004b1bb  mov     [rax+10h], rdx
0x18004b1bf  mov     [rax+8], rcx
0x18004b1c3  push    rbx
0x18004b1c4  push    rsi
0x18004b1c5  push    rdi
0x18004b1c6  push    r12
0x18004b1c8  push    r13
0x18004b1ca  push    r14
0x18004b1cc  push    r15
0x18004b1ce  sub     rsp, 100h
0x18004b1d5  mov     r15, r9
0x18004b1d8  mov     rsi, r8
0x18004b1db  mov     r13, rdx
0x18004b1de  mov     r14, rcx
0x18004b1e1  lea     r12, WPP_GLOBAL_Control
0x18004b1e8  mov     rax, cs:WPP_GLOBAL_Control
0x18004b1ef  cmp     rax, r12
0x18004b1f2  jz      short loc_18004B21C
0x18004b1f4  test    byte ptr [rax+44h], 8
0x18004b1f8  jz      short loc_18004B233
0x18004b1fa  cmp     byte ptr [rax+41h], 6
0x18004b1fe  jb      short loc_18004B21C
0x18004b200  mov     edx, 0Bh
0x18004b205  lea     r8, WPP_9fffca09c132345368abadf44793045b_Traceguids
0x18004b20c  mov     rcx, [rax+38h]
0x18004b210  call    WPP_SF_
0x18004b215  mov     rax, cs:WPP_GLOBAL_Control
0x18004b21c  test    byte ptr [rax+44h], 8
0x18004b220  jz      short loc_18004B233
0x18004b222  cmp     byte ptr [rax+41h], 6
0x18004b226  jb      short loc_18004B233
0x18004b228  mov     ebx, 1
0x18004b22d  mov     al, bl
0x18004b22f  xor     edi, edi
0x18004b231  jmp     short loc_18004B23B
0x18004b233  xor     edi, edi
0x18004b235  mov     al, dil
0x18004b238  lea     ebx, [rdi+1]
0x18004b23b  mov     [rsp+138h+var_100], edi
0x18004b23f  mov     [rsp+138h+var_FC], 3Ch ; '<'
0x18004b247  mov     [rsp+138h+var_F8], al
0x18004b24b  lea     rax, aCfiledownloadm_0; "CFileDownloadManager::StartFileDownload"
0x18004b252  mov     [rsp+138h+var_F0], rax
0x18004b257  mov     [rsp+138h+var_E8], rdi
0x18004b25c  mov     [rsp+138h+var_108], ebx
0x18004b260  mov     eax, [rsp+138h+var_100]
0x18004b264  mov     [rsp+138h+var_100], eax
0x18004b268  mov     eax, 43h ; 'C'
0x18004b26d  test    r15, r15
0x18004b270  jnz     short loc_18004B295
0x18004b272  mov     ecx, 80070057h
0x18004b277  mov     [rsp+138h+var_100], ecx
0x18004b27b  mov     word ptr [rsp+138h+var_FC+2], ax
0x18004b280  mov     [rsp+138h+pExceptionObject], ecx
0x18004b284  lea     rdx, _TI1J; pThrowInfo
0x18004b28b  lea     rcx, [rsp+138h+pExceptionObject]; pExceptionObject
0x18004b290  call    _CxxThrowException_0
0x18004b295  mov     [rsp+138h+var_100], edi
0x18004b299  mov     word ptr [rsp+138h+var_FC], ax
0x18004b29e  call    cs:__imp_GetCurrentProcessId
0x18004b2a4  cmp     [rsp+138h+arg_20], eax
0x18004b2ab  cmovnz  ebx, edi
0x18004b2ae  mov     [rsp+138h+var_108], ebx
0x18004b2b2  lea     rdx, [r14+0B8h]
0x18004b2b9  lea     rcx, [rsp+138h+lpCriticalSection]
0x18004b2c1  call    ??0?$CEcsExclusiveLock@VCEcsCriticalSection@@@@QEAA@AEAVCEcsCriticalSection@@_N@Z; CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(CEcsCriticalSection &,bool)
0x18004b2c6  nop
0x18004b2c7  mov     rax, [r14+110h]
0x18004b2ce  sub     rax, [r14+108h]
0x18004b2d5  sar     rax, 3
0x18004b2d9  mov     rcx, 0AAAAAAAAAAAAAAABh
0x18004b2e3  imul    rax, rcx
0x18004b2e7  cmp     rax, 0Ah
0x18004b2eb  jb      loc_18004B3CD
0x18004b2f1  mov     rdx, r15
0x18004b2f4  lea     rcx, [rsp+138h+var_D8]
0x18004b2f9  call    ??0?$CComPtr@UIStagedFileCommitInfo@@@ATL@@QEAA@PEAUIStagedFileCommitInfo@@@Z; ATL::CComPtr<IStagedFileCommitInfo>::CComPtr<IStagedFileCommitInfo>(IStagedFileCommitInfo *)
0x18004b2fe  test    ebx, ebx
0x18004b300  jz      short loc_18004B34D
0x18004b302  lea     rdx, [rsp+138h+var_D8]
0x18004b307  lea     rcx, [r14+120h]
0x18004b30e  call    ?EnQueue@?$EcsQueue@V?$CComPtr@UIStagedFileCommitInfo@@@ATL@@@@QEAAJAEBV?$CComPtr@UIStagedFileCommitInfo@@@ATL@@@Z; EcsQueue<ATL::CComPtr<IStagedFileCommitInfo>>::EnQueue(ATL::CComPtr<IStagedFileCommitInfo> const &)
0x18004b313  mov     [rsp+138h+var_100], eax
0x18004b317  lea     rcx, [rsp+138h+var_D8]
0x18004b31c  call    ??1?$CComPtr@UICloudFileInfoFromDisk@@@ATL@@QEAA@XZ; ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(void)
0x18004b321  mov     eax, [rsp+138h+var_100]
0x18004b325  mov     [rsp+138h+var_100], eax
0x18004b329  mov     ecx, 56h ; 'V'
0x18004b32e  test    eax, eax
0x18004b330  jns     short loc_18004B397
0x18004b332  mov     word ptr [rsp+138h+var_FC+2], cx
0x18004b337  mov     [rsp+138h+var_C4], eax
0x18004b33b  lea     rdx, _TI1J; pThrowInfo
0x18004b342  lea     rcx, [rsp+138h+var_C4]; pExceptionObject
0x18004b347  call    _CxxThrowException_0
0x18004b34d  lea     rdx, [rsp+138h+var_D8]
0x18004b352  lea     rcx, [r14+138h]
0x18004b359  call    ?EnQueue@?$EcsQueue@V?$CComPtr@UIStagedFileCommitInfo@@@ATL@@@@QEAAJAEBV?$CComPtr@UIStagedFileCommitInfo@@@ATL@@@Z; EcsQueue<ATL::CComPtr<IStagedFileCommitInfo>>::EnQueue(ATL::CComPtr<IStagedFileCommitInfo> const &)
0x18004b35e  mov     [rsp+138h+var_100], eax
0x18004b362  lea     rcx, [rsp+138h+var_D8]
0x18004b367  call    ??1?$CComPtr@UICloudFileInfoFromDisk@@@ATL@@QEAA@XZ; ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(void)
0x18004b36c  mov     eax, [rsp+138h+var_100]
0x18004b370  mov     [rsp+138h+var_100], eax
0x18004b374  mov     ecx, 5Bh ; '['
0x18004b379  test    eax, eax
0x18004b37b  jns     short loc_18004B397
0x18004b37d  mov     word ptr [rsp+138h+var_FC+2], cx
0x18004b382  mov     [rsp+138h+var_C0], eax
0x18004b386  lea     rdx, _TI1J; pThrowInfo
0x18004b38d  lea     rcx, [rsp+138h+var_C0]; pExceptionObject
0x18004b392  call    _CxxThrowException_0
0x18004b397  mov     word ptr [rsp+138h+var_FC], cx
0x18004b39c  cmp     [rsp+138h+var_B0], dil
0x18004b3a4  jz      short loc_18004B3BC
0x18004b3a6  mov     rcx, [rsp+138h+lpCriticalSection]; lpCriticalSection
0x18004b3ae  call    cs:__imp_LeaveCriticalSection
0x18004b3b4  mov     [rsp+138h+var_B0], dil
0x18004b3bc  lea     rcx, [rsp+138h+var_100]; this
0x18004b3c1  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x18004b3c6  xor     eax, eax
0x18004b3c8  jmp     loc_18004B6A1
0x18004b3cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b3d4  cmp     rcx, r12
0x18004b3d7  jz      short loc_18004B407
0x18004b3d9  test    byte ptr [rcx+44h], 8
0x18004b3dd  jz      short loc_18004B407
0x18004b3df  cmp     byte ptr [rcx+41h], 4
0x18004b3e3  jb      short loc_18004B407
0x18004b3e5  mov     edx, 0Ch
0x18004b3ea  mov     rax, [rsi]
0x18004b3ed  mov     qword ptr [rsp+138h+var_118], rax
0x18004b3f2  mov     r9, [rsi+8]
0x18004b3f6  lea     r8, WPP_9fffca09c132345368abadf44793045b_Traceguids
0x18004b3fd  mov     rcx, [rcx+38h]
0x18004b401  call    WPP_SF_ii
0x18004b406  nop
0x18004b407  cmp     [rsp+138h+var_B0], dil
0x18004b40f  jz      short loc_18004B427
0x18004b411  mov     rcx, [rsp+138h+lpCriticalSection]; lpCriticalSection
0x18004b419  call    cs:__imp_LeaveCriticalSection
0x18004b41f  mov     [rsp+138h+var_B0], dil
0x18004b427  lea     r12, [r14-8]
0x18004b42b  mov     rax, [r12]
0x18004b42f  mov     rax, [rax+20h]
0x18004b433  movups  xmm0, xmmword ptr [rsi]
0x18004b436  mov     rcx, r12
0x18004b439  test    ebx, ebx
0x18004b43b  jz      loc_18004B4FE
0x18004b441  movdqu  xmmword ptr [rsp+138h+var_D8], xmm0
0x18004b447  lea     rdx, [rsp+138h+var_D8]
0x18004b44c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b451  movups  xmm0, xmmword ptr [rsi]
0x18004b454  mov     r8, r15; struct IStagedFileCommitInfo *
0x18004b457  mov     rcx, r12; this
0x18004b45a  test    al, al
0x18004b45c  jnz     short loc_18004B4D6
0x18004b45e  movdqu  xmmword ptr [rsp+138h+var_98.Identifier], xmm0
0x18004b467  lea     rdx, [rsp+138h+var_98]; struct _FILE_ID_128
0x18004b46f  call    ?AddOrUpdateActiveDownload@CFileDownloadManager@@AEAAXU_FILE_ID_128@@PEAUIStagedFileCommitInfo@@@Z; CFileDownloadManager::AddOrUpdateActiveDownload(_FILE_ID_128,IStagedFileCommitInfo *)
0x18004b474  mov     r9, [r14+60h]
0x18004b478  lea     rcx, [r13+1A0h]
0x18004b47f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004b484  mov     rdx, [r9]
0x18004b487  mov     r8, [rdx+20h]
0x18004b48b  mov     rdx, rax
0x18004b48e  mov     rcx, r9
0x18004b491  mov     rax, r8
0x18004b494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b499  mov     rax, [r12]
0x18004b49d  movups  xmm0, xmmword ptr [rsi]
0x18004b4a0  movdqu  [rsp+138h+var_88], xmm0
0x18004b4a9  lea     rdx, [rsp+138h+var_88]
0x18004b4b1  mov     rcx, r12
0x18004b4b4  mov     rax, [rax+20h]
0x18004b4b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b4bd  test    al, al
0x18004b4bf  jnz     loc_18004B576
0x18004b4c5  lea     rcx, [rsp+138h+var_100]; this
0x18004b4ca  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x18004b4cf  xor     eax, eax
0x18004b4d1  jmp     loc_18004B6A1
0x18004b4d6  movdqu  xmmword ptr [rsp+138h+var_78.Identifier], xmm0
0x18004b4df  lea     rdx, [rsp+138h+var_78]; struct _FILE_ID_128
0x18004b4e7  call    ?AddOrUpdateActiveDownload@CFileDownloadManager@@AEAAXU_FILE_ID_128@@PEAUIStagedFileCommitInfo@@@Z; CFileDownloadManager::AddOrUpdateActiveDownload(_FILE_ID_128,IStagedFileCommitInfo *)
0x18004b4ec  nop
0x18004b4ed  lea     rcx, [rsp+138h+var_100]; this
0x18004b4f2  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x18004b4f7  xor     eax, eax
0x18004b4f9  jmp     loc_18004B6A1
0x18004b4fe  movdqu  [rsp+138h+var_68], xmm0
0x18004b507  lea     rdx, [rsp+138h+var_68]
0x18004b50f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b514  test    al, al
0x18004b516  jz      short loc_18004B576
0x18004b518  mov     r9, [r14+60h]
0x18004b51c  lea     rcx, [r13+1A0h]
0x18004b523  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004b528  mov     rdx, [r9]
0x18004b52b  mov     r8, [rdx+20h]
0x18004b52f  mov     rdx, rax
0x18004b532  mov     rcx, r9
0x18004b535  mov     rax, r8
0x18004b538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b53d  mov     rax, [r12]
0x18004b541  movups  xmm0, xmmword ptr [rsi]
0x18004b544  movdqu  [rsp+138h+var_58], xmm0
0x18004b54d  lea     rdx, [rsp+138h+var_58]
0x18004b555  mov     rcx, r12
0x18004b558  mov     rax, [rax+20h]
0x18004b55c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b561  test    al, al
0x18004b563  jnz     short loc_18004B576
0x18004b565  lea     rcx, [rsp+138h+var_100]; this
0x18004b56a  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x18004b56f  xor     eax, eax
0x18004b571  jmp     loc_18004B6A1
0x18004b576  movups  xmm0, xmmword ptr [rsi]
0x18004b579  movdqu  xmmword ptr [rsp+138h+var_48.Identifier], xmm0
0x18004b582  mov     r8, r15; struct IStagedFileCommitInfo *
0x18004b585  lea     rdx, [rsp+138h+var_48]; struct _FILE_ID_128
0x18004b58d  mov     rcx, r12; this
0x18004b590  call    ?AddOrUpdateActiveDownload@CFileDownloadManager@@AEAAXU_FILE_ID_128@@PEAUIStagedFileCommitInfo@@@Z; CFileDownloadManager::AddOrUpdateActiveDownload(_FILE_ID_128,IStagedFileCommitInfo *)
0x18004b595  nop
0x18004b596  jmp     short loc_18004B5C4
0x18004b598  jmp     short loc_18004B59E
0x18004b59a  jmp     short loc_18004B59E
0x18004b59c  jmp     short $+2
0x18004b59e  mov     ebx, [rsp+138h+var_108]
0x18004b5a2  mov     r13, [rsp+138h+arg_8]
0x18004b5aa  mov     rsi, [rsp+138h+arg_10]
0x18004b5b2  mov     r15, [rsp+138h+arg_18]
0x18004b5ba  mov     r14, [rsp+138h+arg_0]
0x18004b5c2  xor     edi, edi
0x18004b5c4  lea     rax, WPP_GLOBAL_Control
0x18004b5cb  mov     r12d, [rsp+138h+var_100]
0x18004b5d0  test    r12d, r12d
0x18004b5d3  jns     short loc_18004B61C
0x18004b5d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b5dc  cmp     rcx, rax
0x18004b5df  jz      short loc_18004B60A
0x18004b5e1  test    byte ptr [rcx+44h], 8
0x18004b5e5  jz      short loc_18004B60A
0x18004b5e7  cmp     byte ptr [rcx+41h], 2
0x18004b5eb  jb      short loc_18004B60A
0x18004b5ed  mov     edx, 0Dh
0x18004b5f2  mov     r9d, r12d
0x18004b5f5  lea     r8, WPP_9fffca09c132345368abadf44793045b_Traceguids
0x18004b5fc  mov     rcx, [rcx+38h]
0x18004b600  call    WPP_SF_d
0x18004b605  mov     r12d, [rsp+138h+var_100]
0x18004b60a  lea     rcx, [rsp+138h+var_100]; this
0x18004b60f  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x18004b614  mov     eax, r12d
0x18004b617  jmp     loc_18004B6A1
0x18004b61c  test    ebx, ebx
0x18004b61e  jz      short loc_18004B670
0x18004b620  lea     rdx, [r14+90h]
0x18004b627  lea     rcx, [rsp+138h+var_D8]
0x18004b62c  call    ??0?$CEcsExclusiveLock@VCEcsCriticalSection@@@@QEAA@AEAVCEcsCriticalSection@@_N@Z; CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(CEcsCriticalSection &,bool)
0x18004b631  nop
0x18004b632  mov     rax, [rsp+138h+arg_28]
0x18004b63a  mov     [rsp+138h+var_110], rax; struct ISyncShareManagerProgressCallback *
0x18004b63f  mov     [rsp+138h+var_118], ebx; int
0x18004b643  mov     r9, r15; struct IStagedFileCommitInfo *
0x18004b646  mov     r8, rsi; struct _FILE_ID_128 *
0x18004b649  mov     rdx, r13; struct ClientPartnershipDescriptor *
0x18004b64c  lea     rcx, [r14-8]; this
0x18004b650  call    ?DownloadInternal@CFileDownloadManager@@AEAAJAEBVClientPartnershipDescriptor@@AEBU_FILE_ID_128@@PEAUIStagedFileCommitInfo@@HPEAUISyncShareManagerProgressCallback@@@Z; CFileDownloadManager::DownloadInternal(ClientPartnershipDescriptor const &,_FILE_ID_128 const &,IStagedFileCommitInfo *,int,ISyncShareManagerProgressCallback *)
0x18004b655  mov     ebx, eax
0x18004b657  cmp     byte ptr [rsp+138h+var_D8+8], dil
0x18004b65c  jz      short loc_18004B695
0x18004b65e  mov     rcx, [rsp+138h+var_D8]; lpCriticalSection
0x18004b663  call    cs:__imp_LeaveCriticalSection
0x18004b669  mov     byte ptr [rsp+138h+var_D8+8], dil
0x18004b66e  jmp     short loc_18004B695
0x18004b670  mov     rax, [rsp+138h+arg_28]
0x18004b678  mov     [rsp+138h+var_110], rax; struct ISyncShareManagerProgressCallback *
0x18004b67d  mov     [rsp+138h+var_118], edi; int
0x18004b681  mov     r9, r15; struct IStagedFileCommitInfo *
0x18004b684  mov     r8, rsi; struct _FILE_ID_128 *
0x18004b687  mov     rdx, r13; struct ClientPartnershipDescriptor *
0x18004b68a  lea     rcx, [r14-8]; this
0x18004b68e  call    ?DownloadInternal@CFileDownloadManager@@AEAAJAEBVClientPartnershipDescriptor@@AEBU_FILE_ID_128@@PEAUIStagedFileCommitInfo@@HPEAUISyncShareManagerProgressCallback@@@Z; CFileDownloadManager::DownloadInternal(ClientPartnershipDescriptor const &,_FILE_ID_128 const &,IStagedFileCommitInfo *,int,ISyncShareManagerProgressCallback *)
0x18004b693  mov     ebx, eax
0x18004b695  lea     rcx, [rsp+138h+var_100]; this
0x18004b69a  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x18004b69f  mov     eax, ebx
0x18004b6a1  add     rsp, 100h
0x18004b6a8  pop     r15
0x18004b6aa  pop     r14
0x18004b6ac  pop     r13
0x18004b6ae  pop     r12
0x18004b6b0  pop     rdi
0x18004b6b1  pop     rsi
0x18004b6b2  pop     rbx
0x18004b6b3  retn
```
