# StorageManagerExport(_GUID)

- ea: `0x180054720`
- end: `0x180054918`
- name: `?StorageManagerExport@@YAJU_GUID@@@Z`
- size: `504`
- prototype: `__int64 __fastcall(struct _GUID *__struct_ptr)`
- caller_count: `5`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18005262c`
- `0x1800760f0`
- `0x18007a024`
- `0x18008f340`
- `0x18009bd00`

## callees

- `0x18005388c`
- `0x180054720`
- `0x1800549a0`
- `0x180055b14`
- `0x180056358`
- `0x180058680`
- `0x180075abc`
- `0x1800b8120`
- `0x1800b81f0`
- `0x1800b826c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054816`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800548b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054902`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054816`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800548b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054902`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180054898`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180054898`

## string_xrefs

- `0x180054764`: `onecore\ds\security\biometrics\service\server\storagemanager.cpp`
- `0x1800547f3`: `onecore\ds\security\biometrics\service\server\storagemanager.cpp`
- `0x180054862`: `onecore\ds\security\biometrics\service\server\storagemanager.cpp`
- `0x1800548c7`: `onecore\ds\security\biometrics\service\server\storagemanager.cpp`
- `0x1800548e3`: `onecore\ds\security\biometrics\service\server\storagemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall StorageManagerExport(struct _GUID *a1)
{
  int v2; // eax
  unsigned int FileHandle; // ebx
  unsigned __int8 *v5; // rsi
  unsigned __int64 v6; // rbx
  unsigned __int64 v7; // r8
  int v8; // eax
  unsigned int v9; // r15d
  int v10; // eax
  HLOCAL v11; // rcx
  const char *v12; // r9
  HLOCAL v13; // rcx
  HLOCAL v14; // rcx
  int lpOverlapped; // [rsp+20h] [rbp-58h]
  unsigned __int64 v16; // [rsp+30h] [rbp-48h] BYREF
  struct _GUID v17; // [rsp+40h] [rbp-38h] BYREF
  char v18; // [rsp+50h] [rbp-28h]
  struct _GUID v19; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+30h]
  DWORD NumberOfBytesWritten; // [rsp+B0h] [rbp+38h] BYREF
  HLOCAL hMem; // [rsp+B8h] [rbp+40h] BYREF
  HANDLE hFile; // [rsp+C0h] [rbp+48h] BYREF
  unsigned __int64 nNumberOfBytesToWrite; // [rsp+C8h] [rbp+50h] BYREF

  nNumberOfBytesToWrite = 0;
  v16 = 0;
  v17 = *a1;
  v2 = BioIsoStorageManagerExportBegin(&v17, &nNumberOfBytesToWrite, &v16);
  FileHandle = v2;
  if ( v2 >= 0 )
  {
    wil::make_unique_hlocal<unsigned char [0]>(&hMem, nNumberOfBytesToWrite);
    *(_QWORD *)&v17.Data1 = 0;
    v5 = (unsigned __int8 *)hMem;
    v6 = nNumberOfBytesToWrite;
    while ( 1 )
    {
      v7 = v16;
      if ( v6 < v16 )
        v7 = v6;
      v19 = *a1;
      v8 = BioIsoStorageManagerExportNext(&v19, v5, v7, (unsigned __int64 *)&v17.Data1);
      v9 = v8;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA3,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\storagemanager.cpp",
          (const char *)(unsigned int)v8,
          lpOverlapped);
        v14 = hMem;
        hMem = 0;
        if ( v14 )
          LocalFree(v14);
        return v9;
      }
      if ( !*(_QWORD *)&v17.Data1 )
        break;
      v6 -= *(_QWORD *)&v17.Data1;
      v5 += *(_QWORD *)&v17.Data1;
    }
    v19 = *a1;
    v10 = BioIsoStorageManagerExportEnd(&v19);
    FileHandle = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAB,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\storagemanager.cpp",
        (const char *)(unsigned int)v10,
        lpOverlapped);
      goto LABEL_12;
    }
    hFile = 0;
    *(_QWORD *)&v17.Data1 = &hFile;
    *(_QWORD *)v17.Data4 = 0;
    v18 = 1;
    v19 = *a1;
    FileHandle = GetFileHandle(&v19, 0, (void **)v17.Data4);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v17);
    if ( (FileHandle & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB2,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\storagemanager.cpp",
        (const char *)FileHandle,
        lpOverlapped);
LABEL_16:
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
LABEL_12:
      v11 = hMem;
      hMem = 0;
      if ( v11 )
        LocalFree(v11);
      return FileHandle;
    }
    NumberOfBytesWritten = 0;
    if ( !WriteFile(hFile, hMem, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
    {
      FileHandle = wil::details::in1diag3::Return_GetLastError(
                     retaddr,
                     (void *)0xBB,
                     (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\storagemanager.cpp",
                     v12);
      goto LABEL_16;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
    v13 = hMem;
    hMem = 0;
    if ( v13 )
      LocalFree(v13);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x92,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\storagemanager.cpp",
      (const char *)(unsigned int)v2,
      lpOverlapped);
    return FileHandle;
  }
}

```

## disassembly

```asm
0x180054720  push    rbp
0x180054722  push    rbx
0x180054723  push    rsi
0x180054724  push    rdi
0x180054725  push    r12
0x180054727  push    r15
0x180054729  mov     rbp, rsp
0x18005472c  sub     rsp, 78h
0x180054730  mov     rdi, rcx
0x180054733  xor     r12d, r12d
0x180054736  mov     [rbp+nNumberOfBytesToWrite], r12
0x18005473a  mov     [rbp+var_48], r12
0x18005473e  movaps  xmm0, xmmword ptr [rcx]
0x180054741  movdqa  xmmword ptr [rbp+var_38.Data1], xmm0
0x180054746  lea     r8, [rbp+var_48]; unsigned __int64 *
0x18005474a  lea     rdx, [rbp+nNumberOfBytesToWrite]; unsigned __int64 *
0x18005474e  lea     rcx, [rbp+var_38]; struct _GUID
0x180054752  call    ?BioIsoStorageManagerExportBegin@@YAJU_GUID@@PEA_K1@Z; BioIsoStorageManagerExportBegin(_GUID,unsigned __int64 *,unsigned __int64 *)
0x180054757  mov     ebx, eax
0x180054759  test    eax, eax
0x18005475b  jns     short loc_18005477C
0x18005475d  mov     rcx, [rbp+30h]; this
0x180054761  mov     r9d, eax; char *
0x180054764  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\biometrics\\serv"...
0x18005476b  mov     edx, 92h; void *
0x180054770  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054775  mov     eax, ebx
0x180054777  jmp     loc_18005490B
0x18005477c  mov     rdx, [rbp+nNumberOfBytesToWrite]
0x180054780  lea     rcx, [rbp+hMem]
0x180054784  call    ??$make_unique_hlocal@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<uchar [0]>(unsigned __int64)
0x180054789  nop
0x18005478a  mov     qword ptr [rbp+var_38.Data1], r12
0x18005478e  mov     rsi, [rbp+hMem]
0x180054792  mov     rbx, [rbp+nNumberOfBytesToWrite]
0x180054796  mov     r8, [rbp+var_48]
0x18005479a  cmp     rbx, r8
0x18005479d  cmovb   r8, rbx; unsigned __int64
0x1800547a1  movaps  xmm0, xmmword ptr [rdi]
0x1800547a4  movdqa  xmmword ptr [rbp+var_18.Data1], xmm0
0x1800547a9  lea     r9, [rbp+var_38]; unsigned __int64 *
0x1800547ad  mov     rdx, rsi; unsigned __int8 *
0x1800547b0  lea     rcx, [rbp+var_18]; struct _GUID
0x1800547b4  call    ?BioIsoStorageManagerExportNext@@YAJU_GUID@@PEAE_KPEA_K@Z; BioIsoStorageManagerExportNext(_GUID,uchar *,unsigned __int64,unsigned __int64 *)
0x1800547b9  mov     r15d, eax
0x1800547bc  test    eax, eax
0x1800547be  js      loc_1800548DC
0x1800547c4  mov     rax, qword ptr [rbp+var_38.Data1]
0x1800547c8  test    rax, rax
0x1800547cb  jz      short loc_1800547D5
0x1800547cd  sub     rbx, rax
0x1800547d0  add     rsi, rax
0x1800547d3  jmp     short loc_180054796
0x1800547d5  movaps  xmm0, xmmword ptr [rdi]
0x1800547d8  movdqa  xmmword ptr [rbp+var_18.Data1], xmm0
0x1800547dd  lea     rcx, [rbp+var_18]; struct _GUID
0x1800547e1  call    ?BioIsoStorageManagerExportEnd@@YAJU_GUID@@@Z; BioIsoStorageManagerExportEnd(_GUID)
0x1800547e6  mov     ebx, eax
0x1800547e8  test    eax, eax
0x1800547ea  jns     short loc_180054821
0x1800547ec  mov     rcx, [rbp+30h]; this
0x1800547f0  mov     r9d, eax; char *
0x1800547f3  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\biometrics\\serv"...
0x1800547fa  mov     edx, 0ABh; void *
0x1800547ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054804  nop
0x180054805  mov     rcx, [rbp+hMem]; hMem
0x180054809  mov     [rbp+hMem], r12
0x18005480d  test    rcx, rcx
0x180054810  jz      loc_180054775
0x180054816  call    cs:__imp_LocalFree
0x18005481c  jmp     loc_180054775
0x180054821  mov     [rbp+hFile], r12
0x180054825  lea     rax, [rbp+hFile]
0x180054829  mov     qword ptr [rbp+var_38.Data1], rax
0x18005482d  mov     qword ptr [rbp+var_38.Data4], r12
0x180054831  mov     [rbp+var_28], 1
0x180054835  movaps  xmm0, xmmword ptr [rdi]
0x180054838  movdqa  xmmword ptr [rbp+var_18.Data1], xmm0
0x18005483d  lea     r8, [rbp+var_38.Data4]; void **
0x180054841  xor     edx, edx; bool
0x180054843  lea     rcx, [rbp+var_18]; struct _GUID
0x180054847  call    ?GetFileHandle@@YAJU_GUID@@_NPEAPEAX@Z; GetFileHandle(_GUID,bool,void * *)
0x18005484c  mov     ebx, eax
0x18005484e  lea     rcx, [rbp+var_38]
0x180054852  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x180054857  test    ebx, ebx
0x180054859  jns     short loc_18005487F
0x18005485b  mov     rcx, [rbp+30h]; this
0x18005485f  mov     r9d, ebx; char *
0x180054862  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\biometrics\\serv"...
0x180054869  mov     edx, 0B2h; void *
0x18005486e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054873  nop
0x180054874  lea     rcx, [rbp+hFile]
0x180054878  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18005487d  jmp     short loc_180054805
0x18005487f  mov     [rbp+NumberOfBytesWritten], r12d
0x180054883  mov     qword ptr [rsp+78h+lpOverlapped], r12; lpOverlapped
0x180054888  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18005488c  mov     r8d, dword ptr [rbp+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x180054890  mov     rdx, [rbp+hMem]; lpBuffer
0x180054894  mov     rcx, [rbp+hFile]; hFile
0x180054898  call    cs:__imp_WriteFile
0x18005489e  test    eax, eax
0x1800548a0  jz      short loc_1800548C3
0x1800548a2  lea     rcx, [rbp+hFile]
0x1800548a6  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800548ab  nop
0x1800548ac  mov     rcx, [rbp+hMem]; hMem
0x1800548b0  mov     [rbp+hMem], r12
0x1800548b4  test    rcx, rcx
0x1800548b7  jz      short loc_1800548BF
0x1800548b9  call    cs:__imp_LocalFree
0x1800548bf  xor     eax, eax
0x1800548c1  jmp     short loc_18005490B
0x1800548c3  mov     rcx, [rbp+30h]; this
0x1800548c7  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\biometrics\\serv"...
0x1800548ce  mov     edx, 0BBh; void *
0x1800548d3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800548d8  mov     ebx, eax
0x1800548da  jmp     short loc_180054874
0x1800548dc  mov     rcx, [rbp+30h]; this
0x1800548e0  mov     r9d, r15d; char *
0x1800548e3  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\biometrics\\serv"...
0x1800548ea  mov     edx, 0A3h; void *
0x1800548ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800548f4  nop
0x1800548f5  mov     rcx, [rbp+hMem]; hMem
0x1800548f9  mov     [rbp+hMem], r12
0x1800548fd  test    rcx, rcx
0x180054900  jz      short loc_180054908
0x180054902  call    cs:__imp_LocalFree
0x180054908  mov     eax, r15d
0x18005490b  add     rsp, 78h
0x18005490f  pop     r15
0x180054911  pop     r12
0x180054913  pop     rdi
0x180054914  pop     rsi
0x180054915  pop     rbx
0x180054916  pop     rbp
0x180054917  retn
```
