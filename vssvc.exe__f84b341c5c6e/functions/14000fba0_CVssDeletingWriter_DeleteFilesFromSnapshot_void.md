# CVssDeletingWriter::DeleteFilesFromSnapshot(void)

- ea: `0x14000fba0`
- end: `0x140010162`
- name: `?DeleteFilesFromSnapshot@CVssDeletingWriter@@IEAAXXZ`
- size: `1474`
- prototype: `void __fastcall(CVssDeletingWriter *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1400d1300`

## callees

- `0x140008908`
- `0x14000c84c`
- `0x14000fba0`
- `0x140010170`
- `0x1400137c0`
- `0x1400139c0`
- `0x140013b00`
- `0x140014650`
- `0x140016a10`
- `0x1400330fc`
- `0x14003a3fc`
- `0x14004ee3c`
- `0x14004ee7c`
- `0x140091560`
- `0x1400921dc`
- `0x1400d0858`
- `0x1400d1074`
- `0x1400f4010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ffc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ffc6`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14000ffbc`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14000ffbc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14000fe4d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14000fe85`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14000fe4d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14000fe85`

## string_xrefs

- `0x14000fbdc`: `CVssDeletingWriter::DeleteFilesFromSnapshot`
- `0x14000fed4`: `CVssDeletingWriter::DeleteFilesFromSnapshot`
- `0x14000ff3e`: `CVssDeletingWriter::DeleteFilesFromSnapshot`
- `0x14000ffda`: `CVssDeletingWriter::DeleteFilesFromSnapshot`
- `0x140010057`: `CVssDeletingWriter::DeleteFilesFromSnapshot`
- `0x14000fbd0`: `base\stor\vss\modules\writers\deletewriter.cpp`
- `0x14000fec7`: `base\stor\vss\modules\writers\deletewriter.cpp`
- `0x14000ffce`: `base\stor\vss\modules\writers\deletewriter.cpp`
- `0x14001004c`: `base\stor\vss\modules\writers\deletewriter.cpp`
- `0x14000fd58`: `SYSTEM\CurrentControlSet\Services\VSS\Settings`
- `0x140010029`: `failed to delete file %s from snapshot.  Error %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CVssDeletingWriter::DeleteFilesFromSnapshot(CVssDeletingWriter *this)
{
  __int64 v2; // rcx
  __int64 v3; // rax
  int v4; // edi
  __int64 v5; // rcx
  BOOL v6; // ebx
  __int64 v7; // r14
  __int64 v8; // r12
  __int64 v9; // r15
  BOOL v10; // r9d
  const unsigned __int16 *v11; // rdx
  bool v12; // r9
  bool v13; // r9
  ULONGLONG TickCount64; // r15
  CVssDeletingWriter::ToDeleteFile *i; // rbx
  int v16; // esi
  DWORD LastError; // esi
  CVssDeletingWriter::ToDeleteFile *v18; // rcx
  __int64 v19; // [rsp+20h] [rbp-E0h]
  unsigned int v20; // [rsp+30h] [rbp-D0h] BYREF
  CVssDeletingWriter::ToDeleteFile *v21[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v22; // [rsp+48h] [rbp-B8h]
  _QWORD v23[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v24[2]; // [rsp+60h] [rbp-A0h] BYREF
  const unsigned __int16 *v25; // [rsp+70h] [rbp-90h] BYREF
  const wchar_t *v26; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v27; // [rsp+80h] [rbp-80h]
  int v28; // [rsp+88h] [rbp-78h]
  int v29; // [rsp+8Ch] [rbp-74h]
  int v30; // [rsp+90h] [rbp-70h]
  _OWORD v31[7]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v32; // [rsp+108h] [rbp+8h]
  int v33; // [rsp+110h] [rbp+10h]
  const unsigned __int16 *v34; // [rsp+118h] [rbp+18h] BYREF
  const wchar_t *v35; // [rsp+120h] [rbp+20h]
  const unsigned __int16 *v36; // [rsp+128h] [rbp+28h]
  int v37; // [rsp+130h] [rbp+30h]
  int v38; // [rsp+134h] [rbp+34h]
  int v39; // [rsp+138h] [rbp+38h]
  _BYTE v40[120]; // [rsp+140h] [rbp+40h] BYREF
  int v41; // [rsp+1B8h] [rbp+B8h]
  _BYTE v42[8]; // [rsp+1C0h] [rbp+C0h] BYREF
  int v43; // [rsp+1C8h] [rbp+C8h]
  WCHAR FileName[264]; // [rsp+230h] [rbp+130h] BYREF

  v25 = L"base\\stor\\vss\\modules\\writers\\deletewriter.cpp";
  v26 = L"CVssDeletingWriter::DeleteFilesFromSnapshot";
  v27 = L"WRTDELET";
  v28 = 263;
  v29 = 4;
  v30 = 255;
  v33 = 0x1000000;
  memset_0(v31, 0, 0x78u);
  CVssFunctionTracer::CVssFunctionTracer(v42, &v25, 0);
  std::vector<CVssDeletingWriter::ToDeleteFile>::vector<CVssDeletingWriter::ToDeleteFile>(v21);
  v24[1] = 0;
  v24[0] = &CVssAutoCOMPtr<_VDS_LUN_INFORMATION *>::`vftable';
  v23[1] = 0;
  v23[0] = 131097;
  v2 = *((_QWORD *)this + 1);
  if ( v2 )
    v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 88LL))(v2);
  else
    LODWORD(v3) = 0;
  if ( (v3 & 0x400000) != 0 )
  {
    v4 = 0;
    v5 = *((_QWORD *)this + 1);
    v6 = v5 && ((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 88LL))(v5) & 0x1000000) != 0;
    v7 = 30000;
    v8 = 30000;
    if ( !v6 )
      v8 = 10000;
    v9 = 50000;
    if ( CVssRegistryKey::Open(
           (CVssRegistryKey *)v23,
           HKEY_LOCAL_MACHINE,
           L"SYSTEM\\CurrentControlSet\\Services\\VSS\\Settings") )
    {
      v20 = 0;
      v11 = L"MaxDeletionTimeOptimized";
      if ( !v6 )
        v11 = L"MaxDeletionTime";
      CVssRegistryKey::GetValue((CVssRegistryKey *)v23, v11, &v20, v10);
      if ( v20 )
        v8 = 1000 * v20;
      v20 = 0;
      CVssRegistryKey::GetValue((CVssRegistryKey *)v23, L"MaxScanningTimeFilespec", &v20, v12);
      if ( v20 )
        v7 = 1000 * v20;
      v20 = 0;
      CVssRegistryKey::GetValue((CVssRegistryKey *)v23, L"MaxScanningTimeGlobal", &v20, v13);
      if ( v20 )
        v9 = 1000 * v20;
    }
    LOBYTE(v10) = 1;
    CVssDeletingWriter::ExpandFiles((_DWORD)this, 1, (unsigned int)v21, v10, v7, v9);
    std::_Sort_unchecked<CVssDeletingWriter::ToDeleteFile *,bool (*)(CVssDeletingWriter::ToDeleteFile &,CVssDeletingWriter::ToDeleteFile &)>(
      v21[0],
      v21[1],
      0x8E38E38E38E38E39uLL * ((v21[1] - v21[0]) >> 3),
      CVssDeletingWriter::DeleteFileComparator);
    TickCount64 = GetTickCount64();
    for ( i = v21[0]; i != v21[1]; i = (CVssDeletingWriter::ToDeleteFile *)((char *)i + 72) )
    {
      if ( v4 == 10 * (v4 / 10) && GetTickCount64() > v8 + TickCount64 )
      {
        v34 = L"base\\stor\\vss\\modules\\writers\\deletewriter.cpp";
        v35 = L"CVssDeletingWriter::DeleteFilesFromSnapshot";
        v36 = L"WRTDELET";
        v37 = 348;
        v38 = 4;
        v39 = 255;
        v41 = 0x1000000;
        memset_0(v40, 0, sizeof(v40));
        CVssFunctionTracer::LogError(v42, 8220, &v34, 4);
        CVssRegistryKey::Close((CVssRegistryKey *)v23);
        CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>(v24);
        v18 = v21[0];
        if ( !v21[0] )
          goto LABEL_36;
        goto LABEL_34;
      }
      v16 = StringCchPrintfW(FileName, 0x104u, L"%s\\%s", *((_QWORD *)i + 2), *((_QWORD *)i + 4));
      v43 = v16;
      if ( v16 >= 0 )
      {
        v25 = L"base\\stor\\vss\\modules\\writers\\deletewriter.cpp";
        v26 = L"CVssDeletingWriter::DeleteFilesFromSnapshot";
        v27 = L"WRTDELET";
        v28 = 369;
        v29 = 4;
        v30 = 255;
        v33 = 0x1000000;
        memset(v31, 0, sizeof(v31));
        v32 = 0;
        CVssFunctionTracer::Trace(v42, &v25, L"deleting file %s", FileName);
        if ( !DeleteFileW(FileName) )
        {
          LastError = GetLastError();
          v25 = L"base\\stor\\vss\\modules\\writers\\deletewriter.cpp";
          v26 = L"CVssDeletingWriter::DeleteFilesFromSnapshot";
          v27 = L"WRTDELET";
          v28 = 373;
          v29 = 4;
          v30 = 255;
          v33 = 0x1000000;
          memset_0(v31, 0, 0x78u);
          LODWORD(v19) = LastError;
          CVssFunctionTracer::Trace(v42, &v25, L"failed to delete file %s from snapshot.  Error %d", FileName, v19);
        }
      }
      else
      {
        v34 = L"base\\stor\\vss\\modules\\writers\\deletewriter.cpp";
        v35 = L"CVssDeletingWriter::DeleteFilesFromSnapshot";
        v36 = L"WRTDELET";
        v37 = 364;
        v38 = 4;
        v39 = 255;
        v41 = 0x1000000;
        memset_0(v40, 0, sizeof(v40));
        CVssFunctionTracer::Trace(v42, &v34, L"StringCchPrintf failed with 0x%08lx", (unsigned int)v16);
      }
      ++v4;
    }
    CVssRegistryKey::Close((CVssRegistryKey *)v23);
    CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>(v24);
    v18 = v21[0];
    if ( !v21[0] )
      goto LABEL_36;
LABEL_34:
    std::_Destroy_range<std::allocator<CVssDeletingWriter::ToDeleteFile>>(v18);
    goto LABEL_35;
  }
  v25 = L"base\\stor\\vss\\modules\\writers\\deletewriter.cpp";
  v26 = L"CVssDeletingWriter::DeleteFilesFromSnapshot";
  v27 = L"WRTDELET";
  v28 = 275;
  v29 = 4;
  v30 = 255;
  v33 = 0x1000000;
  memset_0(v31, 0, 0x78u);
  CVssFunctionTracer::Trace(v42, &v25, L"skipping file deletion since autorecovery isn't enabled");
  CVssRegistryKey::Close((CVssRegistryKey *)v23);
  CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>(v24);
  if ( v21[0] )
  {
    std::_Destroy_range<std::allocator<CVssDeletingWriter::ToDeleteFile>>(v21[0]);
LABEL_35:
    std::_Deallocate<16>(v21[0], 8 * ((signed __int64)(v22 - (unsigned __int64)v21[0]) >> 3));
    v22 = 0;
    *(_OWORD *)v21 = 0;
  }
LABEL_36:
  CVssFunctionTracer::~CVssFunctionTracer((CVssFunctionTracer *)v42);
}

```

## disassembly

```asm
0x14000fba0  push    rbp
0x14000fba2  push    rbx
0x14000fba3  push    rsi
0x14000fba4  push    rdi
0x14000fba5  push    r12
0x14000fba7  push    r13
0x14000fba9  push    r14
0x14000fbab  push    r15
0x14000fbad  lea     rbp, [rsp-358h]
0x14000fbb5  sub     rsp, 458h
0x14000fbbc  mov     rax, cs:__security_cookie
0x14000fbc3  xor     rax, rsp
0x14000fbc6  mov     [rbp+390h+var_50], rax
0x14000fbcd  mov     rsi, rcx
0x14000fbd0  lea     rbx, aBaseStorVssMod_35; "base\\stor\\vss\\modules\\writers\\dele"...
0x14000fbd7  mov     [rsp+490h+var_420], rbx
0x14000fbdc  lea     rdi, aCvssdeletingwr_8; "CVssDeletingWriter::DeleteFilesFromSnap"...
0x14000fbe3  mov     [rsp+490h+var_418], rdi
0x14000fbe8  lea     r14, aWrtdelet; "WRTDELET"
0x14000fbef  mov     [rbp+390h+var_410], r14
0x14000fbf3  mov     [rbp+390h+var_408], 107h
0x14000fbfa  mov     [rbp+390h+var_404], 4
0x14000fc01  mov     [rbp+390h+var_400], 0FFh
0x14000fc08  xor     r13d, r13d
0x14000fc0b  mov     [rbp+390h+var_380], 1000000h
0x14000fc12  xor     edx, edx; Val
0x14000fc14  mov     r8d, 78h ; 'x'; Size
0x14000fc1a  lea     rcx, [rbp+390h+var_3F8]; void *
0x14000fc1e  call    memset_0
0x14000fc23  xor     r8d, r8d
0x14000fc26  lea     rdx, [rsp+490h+var_420]
0x14000fc2b  lea     rcx, [rbp+390h+var_2D0]
0x14000fc32  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x14000fc37  nop
0x14000fc38  lea     rcx, [rsp+490h+var_458]
0x14000fc3d  call    ??0?$vector@UToDeleteFile@CVssDeletingWriter@@V?$allocator@UToDeleteFile@CVssDeletingWriter@@@std@@@std@@QEAA@XZ; std::vector<CVssDeletingWriter::ToDeleteFile>::vector<CVssDeletingWriter::ToDeleteFile>(void)
0x14000fc42  nop
0x14000fc43  mov     [rsp+490h+var_428], r13
0x14000fc48  lea     rax, ??_7?$CVssAutoCOMPtr@PEAU_VDS_LUN_INFORMATION@@@@6B@; const CVssAutoCOMPtr<_VDS_LUN_INFORMATION *>::`vftable'
0x14000fc4f  mov     [rsp+490h+var_430], rax
0x14000fc54  mov     [rsp+490h+var_438], r13
0x14000fc59  mov     [rsp+490h+var_440], 20019h
0x14000fc62  mov     rcx, [rsi+8]
0x14000fc66  test    rcx, rcx
0x14000fc69  jnz     short loc_14000FC70
0x14000fc6b  mov     eax, r13d
0x14000fc6e  jmp     short loc_14000FC7C
0x14000fc70  mov     rax, [rcx]
0x14000fc73  mov     rax, [rax+58h]
0x14000fc77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fc7c  bt      eax, 16h
0x14000fc80  jb      loc_14000FD16
0x14000fc86  mov     [rsp+490h+var_420], rbx
0x14000fc8b  mov     [rsp+490h+var_418], rdi
0x14000fc90  mov     [rbp+390h+var_410], r14
0x14000fc94  mov     [rbp+390h+var_408], 113h
0x14000fc9b  mov     [rbp+390h+var_404], 4
0x14000fca2  mov     [rbp+390h+var_400], 0FFh
0x14000fca9  mov     [rbp+390h+var_380], 1000000h
0x14000fcb0  xor     edx, edx; Val
0x14000fcb2  mov     r8d, 78h ; 'x'; Size
0x14000fcb8  lea     rcx, [rbp+390h+var_3F8]; void *
0x14000fcbc  call    memset_0
0x14000fcc1  lea     r8, aSkippingFileDe; "skipping file deletion since autorecove"...
0x14000fcc8  lea     rdx, [rsp+490h+var_420]
0x14000fccd  lea     rcx, [rbp+390h+var_2D0]
0x14000fcd4  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x14000fcd9  nop
0x14000fcda  lea     rcx, [rsp+490h+var_440]; this
0x14000fcdf  call    ?Close@CVssRegistryKey@@QEAAXXZ; CVssRegistryKey::Close(void)
0x14000fce4  lea     rcx, [rsp+490h+var_430]
0x14000fce9  call    ??1?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@UEAA@XZ; CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>(void)
0x14000fcee  nop
0x14000fcef  mov     rcx, [rsp+490h+var_458]; this
0x14000fcf4  test    rcx, rcx
0x14000fcf7  jz      loc_140010133
0x14000fcfd  mov     rdx, [rsp+490h+var_458+8]
0x14000fd02  call    ??$_Destroy_range@V?$allocator@UToDeleteFile@CVssDeletingWriter@@@std@@@std@@YAXPEAUToDeleteFile@CVssDeletingWriter@@QEAU12@AEAV?$allocator@UToDeleteFile@CVssDeletingWriter@@@0@@Z; std::_Destroy_range<std::allocator<CVssDeletingWriter::ToDeleteFile>>(CVssDeletingWriter::ToDeleteFile *,CVssDeletingWriter::ToDeleteFile * const,std::allocator<CVssDeletingWriter::ToDeleteFile> &)
0x14000fd07  mov     r14, 8E38E38E38E38E39h
0x14000fd11  jmp     loc_140010103
0x14000fd16  mov     edi, r13d
0x14000fd19  mov     rcx, [rsi+8]
0x14000fd1d  test    rcx, rcx
0x14000fd20  jz      short loc_14000FD3B
0x14000fd22  mov     rax, [rcx]
0x14000fd25  mov     rax, [rax+58h]
0x14000fd29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fd2e  bt      eax, 18h
0x14000fd32  jnb     short loc_14000FD3B
0x14000fd34  mov     ebx, 1
0x14000fd39  jmp     short loc_14000FD3E
0x14000fd3b  mov     ebx, r13d
0x14000fd3e  mov     r14d, 7530h
0x14000fd44  mov     r12d, r14d
0x14000fd47  mov     eax, 2710h
0x14000fd4c  test    ebx, ebx
0x14000fd4e  cmovz   r12d, eax
0x14000fd52  mov     r15d, 0C350h
0x14000fd58  lea     r8, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Services\\VS"...
0x14000fd5f  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x14000fd66  lea     rcx, [rsp+490h+var_440]; this
0x14000fd6b  call    ?Open@CVssRegistryKey@@QEAA_NPEAUHKEY__@@PEBGZZ; CVssRegistryKey::Open(HKEY__ *,ushort const *,...)
0x14000fd70  test    al, al
0x14000fd72  jz      loc_14000FE01
0x14000fd78  mov     [rsp+490h+var_460], r13d
0x14000fd7d  lea     r8, [rsp+490h+var_460]; unsigned int *
0x14000fd82  lea     rcx, [rsp+490h+var_440]; this
0x14000fd87  test    ebx, ebx
0x14000fd89  lea     rdx, aMaxdeletiontim; "MaxDeletionTimeOptimized"
0x14000fd90  jnz     short loc_14000FD99
0x14000fd92  lea     rdx, aMaxdeletiontim_0; "MaxDeletionTime"
0x14000fd99  call    ?GetValue@CVssRegistryKey@@QEAA_NPEBGAEAK_N@Z; CVssRegistryKey::GetValue(ushort const *,ulong &,bool)
0x14000fd9e  mov     eax, [rsp+490h+var_460]
0x14000fda2  test    eax, eax
0x14000fda4  jz      short loc_14000FDAD
0x14000fda6  imul    r12d, eax, 3E8h
0x14000fdad  mov     [rsp+490h+var_460], r13d
0x14000fdb2  lea     r8, [rsp+490h+var_460]; unsigned int *
0x14000fdb7  lea     rdx, aMaxscanningtim; "MaxScanningTimeFilespec"
0x14000fdbe  lea     rcx, [rsp+490h+var_440]; this
0x14000fdc3  call    ?GetValue@CVssRegistryKey@@QEAA_NPEBGAEAK_N@Z; CVssRegistryKey::GetValue(ushort const *,ulong &,bool)
0x14000fdc8  mov     eax, [rsp+490h+var_460]
0x14000fdcc  test    eax, eax
0x14000fdce  jz      short loc_14000FDD7
0x14000fdd0  imul    r14d, eax, 3E8h
0x14000fdd7  mov     [rsp+490h+var_460], r13d
0x14000fddc  lea     r8, [rsp+490h+var_460]; unsigned int *
0x14000fde1  lea     rdx, aMaxscanningtim_0; "MaxScanningTimeGlobal"
0x14000fde8  lea     rcx, [rsp+490h+var_440]; this
0x14000fded  call    ?GetValue@CVssRegistryKey@@QEAA_NPEBGAEAK_N@Z; CVssRegistryKey::GetValue(ushort const *,ulong &,bool)
0x14000fdf2  mov     eax, [rsp+490h+var_460]
0x14000fdf6  test    eax, eax
0x14000fdf8  jz      short loc_14000FE01
0x14000fdfa  imul    r15d, eax, 3E8h
0x14000fe01  mov     [rsp+490h+var_468], r15
0x14000fe06  mov     [rsp+490h+var_470], r14
0x14000fe0b  mov     r9b, 1
0x14000fe0e  lea     r8, [rsp+490h+var_458]
0x14000fe13  movzx   edx, r9b
0x14000fe17  mov     rcx, rsi
0x14000fe1a  call    ?ExpandFiles@CVssDeletingWriter@@IEAAX_NV?$back_insert_iterator@V?$vector@UToDeleteFile@CVssDeletingWriter@@V?$allocator@UToDeleteFile@CVssDeletingWriter@@@std@@@std@@@std@@0_K2@Z; CVssDeletingWriter::ExpandFiles(bool,std::back_insert_iterator<std::vector<CVssDeletingWriter::ToDeleteFile>>,bool,unsigned __int64,unsigned __int64)
0x14000fe1f  mov     rdx, [rsp+490h+var_458+8]
0x14000fe24  mov     rcx, [rsp+490h+var_458]
0x14000fe29  mov     r8, rdx
0x14000fe2c  sub     r8, rcx
0x14000fe2f  sar     r8, 3
0x14000fe33  mov     r14, 8E38E38E38E38E39h
0x14000fe3d  imul    r8, r14
0x14000fe41  lea     r9, ?DeleteFileComparator@CVssDeletingWriter@@KA_NAEAUToDeleteFile@1@0@Z; CVssDeletingWriter::DeleteFileComparator(CVssDeletingWriter::ToDeleteFile &,CVssDeletingWriter::ToDeleteFile &)
0x14000fe48  call    ??$_Sort_unchecked@PEAUToDeleteFile@CVssDeletingWriter@@P6A_NAEAU12@0@Z@std@@YAXPEAUToDeleteFile@CVssDeletingWriter@@0_JP6A_NAEAU12@2@Z@Z; std::_Sort_unchecked<CVssDeletingWriter::ToDeleteFile *,bool (*)(CVssDeletingWriter::ToDeleteFile &,CVssDeletingWriter::ToDeleteFile &)>(CVssDeletingWriter::ToDeleteFile *,CVssDeletingWriter::ToDeleteFile *,__int64,bool (*)(CVssDeletingWriter::ToDeleteFile &,CVssDeletingWriter::ToDeleteFile &))
0x14000fe4d  call    cs:__imp_GetTickCount64
0x14000fe53  mov     r15, rax
0x14000fe56  mov     rbx, [rsp+490h+var_458]
0x14000fe5b  nop     dword ptr [rax+rax+00h]
0x14000fe60  cmp     rbx, [rsp+490h+var_458+8]
0x14000fe65  jz      loc_1400100DA
0x14000fe6b  mov     eax, 66666667h
0x14000fe70  imul    edi
0x14000fe72  sar     edx, 2
0x14000fe75  mov     eax, edx
0x14000fe77  shr     eax, 1Fh
0x14000fe7a  add     edx, eax
0x14000fe7c  lea     ecx, [rdx+rdx*4]
0x14000fe7f  add     ecx, ecx
0x14000fe81  cmp     edi, ecx
0x14000fe83  jnz     short loc_14000FE98
0x14000fe85  call    cs:__imp_GetTickCount64
0x14000fe8b  lea     rcx, [r12+r15]
0x14000fe8f  cmp     rax, rcx
0x14000fe92  ja      loc_14001004C
0x14000fe98  mov     rax, [rbx+20h]
0x14000fe9c  mov     [rsp+490h+var_470], rax
0x14000fea1  mov     r9, [rbx+10h]
0x14000fea5  lea     r8, aSS; "%s\\%s"
0x14000feac  mov     edx, 104h; unsigned __int64
0x14000feb1  lea     rcx, [rbp+390h+FileName]; unsigned __int16 *
0x14000feb8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000febd  mov     esi, eax
0x14000febf  mov     [rbp+390h+var_2C8], eax
0x14000fec5  test    eax, eax
0x14000fec7  lea     rax, aBaseStorVssMod_35; "base\\stor\\vss\\modules\\writers\\dele"...
0x14000fece  jns     short loc_14000FF39
0x14000fed0  mov     [rbp+390h+var_378], rax
0x14000fed4  lea     rax, aCvssdeletingwr_8; "CVssDeletingWriter::DeleteFilesFromSnap"...
0x14000fedb  mov     [rbp+390h+var_370], rax
0x14000fedf  lea     rax, aWrtdelet; "WRTDELET"
0x14000fee6  mov     [rbp+390h+var_368], rax
0x14000feea  mov     [rbp+390h+var_360], 16Ch
0x14000fef1  mov     [rbp+390h+var_35C], 4
0x14000fef8  mov     [rbp+390h+var_358], 0FFh
0x14000feff  mov     [rbp+390h+var_2D8], 1000000h
0x14000ff09  xor     edx, edx; Val
0x14000ff0b  mov     r8d, 78h ; 'x'; Size
0x14000ff11  lea     rcx, [rbp+390h+var_350]; void *
0x14000ff15  call    memset_0
0x14000ff1a  mov     r9d, esi
0x14000ff1d  lea     r8, aStringcchprint_13; "StringCchPrintf failed with 0x%08lx"
0x14000ff24  lea     rdx, [rbp+390h+var_378]
0x14000ff28  lea     rcx, [rbp+390h+var_2D0]
0x14000ff2f  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x14000ff34  jmp     loc_140010041
0x14000ff39  mov     [rsp+490h+var_420], rax
0x14000ff3e  lea     rax, aCvssdeletingwr_8; "CVssDeletingWriter::DeleteFilesFromSnap"...
0x14000ff45  mov     [rsp+490h+var_418], rax
0x14000ff4a  lea     rax, aWrtdelet; "WRTDELET"
0x14000ff51  mov     [rbp+390h+var_410], rax
0x14000ff55  mov     [rbp+390h+var_408], 171h
0x14000ff5c  mov     [rbp+390h+var_404], 4
0x14000ff63  mov     [rbp+390h+var_400], 0FFh
0x14000ff6a  mov     [rbp+390h+var_380], 1000000h
0x14000ff71  xorps   xmm0, xmm0
0x14000ff74  xor     eax, eax
0x14000ff76  movups  [rbp+390h+var_3F8], xmm0
0x14000ff7a  movups  [rbp+390h+var_3E8], xmm0
0x14000ff7e  movups  [rbp+390h+var_3D8], xmm0
0x14000ff82  movups  [rbp+390h+var_3C8], xmm0
0x14000ff86  movups  [rbp+390h+var_3B8], xmm0
0x14000ff8a  movups  [rbp+390h+var_3A8], xmm0
0x14000ff8e  movups  [rbp+390h+var_398], xmm0
0x14000ff92  mov     [rbp+390h+var_388], rax
0x14000ff96  lea     r9, [rbp+390h+FileName]
0x14000ff9d  lea     r8, aDeletingFileS; "deleting file %s"
0x14000ffa4  lea     rdx, [rsp+490h+var_420]
0x14000ffa9  lea     rcx, [rbp+390h+var_2D0]
0x14000ffb0  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x14000ffb5  lea     rcx, [rbp+390h+FileName]; lpFileName
0x14000ffbc  call    cs:__imp_DeleteFileW
0x14000ffc2  test    eax, eax
0x14000ffc4  jnz     short loc_140010041
0x14000ffc6  call    cs:__imp_GetLastError
0x14000ffcc  mov     esi, eax
0x14000ffce  lea     rax, aBaseStorVssMod_35; "base\\stor\\vss\\modules\\writers\\dele"...
0x14000ffd5  mov     [rsp+490h+var_420], rax
0x14000ffda  lea     rax, aCvssdeletingwr_8; "CVssDeletingWriter::DeleteFilesFromSnap"...
0x14000ffe1  mov     [rsp+490h+var_418], rax
0x14000ffe6  lea     rax, aWrtdelet; "WRTDELET"
0x14000ffed  mov     [rbp+390h+var_410], rax
0x14000fff1  mov     [rbp+390h+var_408], 175h
0x14000fff8  mov     [rbp+390h+var_404], 4
0x14000ffff  mov     [rbp+390h+var_400], 0FFh
0x140010006  mov     [rbp+390h+var_380], 1000000h
0x14001000d  xor     edx, edx; Val
0x14001000f  mov     r8d, 78h ; 'x'; Size
0x140010015  lea     rcx, [rbp+390h+var_3F8]; void *
0x140010019  call    memset_0
0x14001001e  mov     dword ptr [rsp+490h+var_470], esi
0x140010022  lea     r9, [rbp+390h+FileName]
0x140010029  lea     r8, aFailedToDelete; "failed to delete file %s from snapshot."...
0x140010030  lea     rdx, [rsp+490h+var_420]
0x140010035  lea     rcx, [rbp+390h+var_2D0]
0x14001003c  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x140010041  add     rbx, 48h ; 'H'
0x140010045  inc     edi
0x140010047  jmp     loc_14000FE60
0x14001004c  lea     rax, aBaseStorVssMod_35; "base\\stor\\vss\\modules\\writers\\dele"...
0x140010053  mov     [rbp+390h+var_378], rax
0x140010057  lea     rax, aCvssdeletingwr_8; "CVssDeletingWriter::DeleteFilesFromSnap"...
0x14001005e  mov     [rbp+390h+var_370], rax
0x140010062  lea     rax, aWrtdelet; "WRTDELET"
0x140010069  mov     [rbp+390h+var_368], rax
0x14001006d  mov     [rbp+390h+var_360], 15Ch
0x140010074  mov     [rbp+390h+var_35C], 4
0x14001007b  mov     [rbp+390h+var_358], 0FFh
0x140010082  mov     [rbp+390h+var_2D8], 1000000h
0x14001008c  xor     edx, edx; Val
0x14001008e  mov     r8d, 78h ; 'x'; Size
0x140010094  lea     rcx, [rbp+390h+var_350]; void *
0x140010098  call    memset_0
0x14001009d  mov     r9d, 4
0x1400100a3  lea     r8, [rbp+390h+var_378]
0x1400100a7  mov     edx, 201Ch
0x1400100ac  lea     rcx, [rbp+390h+var_2D0]
0x1400100b3  call    ?LogError@CVssFunctionTracer@@QEAAXKUCVssDebugInfo@@G@Z; CVssFunctionTracer::LogError(ulong,CVssDebugInfo,ushort)
0x1400100b8  nop
0x1400100b9  lea     rcx, [rsp+490h+var_440]; this
0x1400100be  call    ?Close@CVssRegistryKey@@QEAAXXZ; CVssRegistryKey::Close(void)
0x1400100c3  lea     rcx, [rsp+490h+var_430]
0x1400100c8  call    ??1?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@UEAA@XZ; CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>(void)
0x1400100cd  nop
0x1400100ce  mov     rcx, [rsp+490h+var_458]
0x1400100d3  test    rcx, rcx
0x1400100d6  jnz     short loc_1400100F9
0x1400100d8  jmp     short loc_140010133
0x1400100da  lea     rcx, [rsp+490h+var_440]; this
0x1400100df  call    ?Close@CVssRegistryKey@@QEAAXXZ; CVssRegistryKey::Close(void)
0x1400100e4  lea     rcx, [rsp+490h+var_430]
0x1400100e9  call    ??1?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@UEAA@XZ; CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>(void)
0x1400100ee  nop
0x1400100ef  mov     rcx, [rsp+490h+var_458]; this
0x1400100f4  test    rcx, rcx
0x1400100f7  jz      short loc_140010133
0x1400100f9  mov     rdx, [rsp+490h+var_458+8]
0x1400100fe  call    ??$_Destroy_range@V?$allocator@UToDeleteFile@CVssDeletingWriter@@@std@@@std@@YAXPEAUToDeleteFile@CVssDeletingWriter@@QEAU12@AEAV?$allocator@UToDeleteFile@CVssDeletingWriter@@@0@@Z; std::_Destroy_range<std::allocator<CVssDeletingWriter::ToDeleteFile>>(CVssDeletingWriter::ToDeleteFile *,CVssDeletingWriter::ToDeleteFile * const,std::allocator<CVssDeletingWriter::ToDeleteFile> &)
0x140010103  mov     rcx, [rsp+490h+var_458]
0x140010108  mov     rax, [rsp+490h+var_448]
0x14001010d  sub     rax, rcx
0x140010110  sar     rax, 3
0x140010114  imul    rax, r14
0x140010118  lea     rdx, [rax+rax*8]
0x14001011c  shl     rdx, 3
  ... truncated ...
```
