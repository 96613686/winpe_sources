# CVssHardwareProviderWrapper::LoadData(void)

- ea: `0x14008d76c`
- end: `0x14008de37`
- name: `?LoadData@CVssHardwareProviderWrapper@@AEAAXXZ`
- size: `1739`
- prototype: `void __fastcall(CVssHardwareProviderWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1400b1ae8`

## callees

- `0x1400137c0`
- `0x140013b00`
- `0x140015e38`
- `0x1400330fc`
- `0x14003c174`
- `0x14003fc04`
- `0x14003fcac`
- `0x14008d76c`
- `0x140091560`
- `0x140091584`
- `0x14009197c`
- `0x1400919a0`
- `0x1400921dc`
- `0x1400921e8`
- `0x1400a9608`
- `0x1400a9654`
- `0x1400b1bf4`
- `0x1400f4010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008d867`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008d956`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008db21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008d867`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008d956`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008db21`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14008d85d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14008d94c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14008db17`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14008d85d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14008d94c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14008db17`
- `VSSAPI!LoadVssSnapshotSetDescription` at `0x14008dbb7`
- `VSSAPI!LoadVssSnapshotSetDescription` at `0x14008dbb7`

## string_xrefs

- `0x14008d8c6`: `ReadFile`
- `0x14008d9b0`: `ReadFile`
- `0x14008db7f`: `ReadFile`
- `0x14008da43`: `Cant allocate XML string`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CVssHardwareProviderWrapper::LoadData(CVssHardwareProviderWrapper *this)
{
  HANDLE v2; // rax
  signed int LastError; // eax
  signed int v4; // eax
  unsigned __int64 v5; // rax
  void *v6; // r14
  VSS_SNAPSHOT_SET_LIST *v7; // rax
  VSS_SNAPSHOT_SET_LIST *v8; // rbx
  signed int v9; // eax
  CVssHardwareProviderWrapper *v10; // rcx
  unsigned int v11; // edx
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-1E8h] BYREF
  int i; // [rsp+44h] [rbp-1E4h]
  void *v14; // [rsp+48h] [rbp-1E0h]
  VSS_SNAPSHOT_SET_LIST *v15; // [rsp+50h] [rbp-1D8h]
  const unsigned __int16 *v16; // [rsp+58h] [rbp-1D0h] BYREF
  const unsigned __int16 *v17; // [rsp+60h] [rbp-1C8h]
  const unsigned __int16 *v18; // [rsp+68h] [rbp-1C0h]
  int v19; // [rsp+70h] [rbp-1B8h]
  int v20; // [rsp+74h] [rbp-1B4h]
  int v21; // [rsp+78h] [rbp-1B0h]
  _BYTE v22[120]; // [rsp+80h] [rbp-1A8h] BYREF
  int v23; // [rsp+F8h] [rbp-130h]
  int pExceptionObject; // [rsp+100h] [rbp-128h] BYREF
  GUID v25; // [rsp+110h] [rbp-118h] BYREF
  CVssHardwareProviderWrapper *v26; // [rsp+120h] [rbp-108h]
  void **v27; // [rsp+128h] [rbp-100h] BYREF
  HANDLE hFile; // [rsp+130h] [rbp-F8h]
  int v29; // [rsp+138h] [rbp-F0h] BYREF
  LPVOID v30; // [rsp+140h] [rbp-E8h] BYREF
  int v31; // [rsp+148h] [rbp-E0h]
  unsigned int v32; // [rsp+164h] [rbp-C4h]
  _com_error *v33; // [rsp+1B0h] [rbp-78h] BYREF
  const std::exception *v34; // [rsp+1B8h] [rbp-70h] BYREF
  __int128 v35; // [rsp+1C0h] [rbp-68h] BYREF
  int v36; // [rsp+1D0h] [rbp-58h]
  __int64 Buffer; // [rsp+1D8h] [rbp-50h] BYREF
  int v38; // [rsp+1E0h] [rbp-48h]

  v26 = this;
  v16 = L"base\\stor\\vss\\modules\\coord\\src\\hwwrpdb.cxx";
  v17 = L"CVssHardwareProviderWrapper::LoadData";
  v18 = L"CORHWDBC";
  v19 = 488;
  v20 = 1;
  v21 = 255;
  v23 = 0x1000000;
  memset_0(v22, 0, sizeof(v22));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v30, (__int64)&v16, 0);
  v2 = CVssHardwareProviderWrapper::OpenDatabase(this);
  v27 = &CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
  hFile = v2;
  Buffer = 0;
  v38 = 0;
  NumberOfBytesRead = 0;
  if ( !ReadFile(v2, &Buffer, 0xCu, &NumberOfBytesRead, 0) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v31 = LastError;
    v16 = L"base\\stor\\vss\\modules\\coord\\src\\hwwrpdb.cxx";
    v17 = L"CVssHardwareProviderWrapper::LoadData";
    v18 = L"CORHWDBC";
    v19 = 500;
    v20 = 1;
    v21 = 255;
    v23 = 0x1000000;
    memset_0(v22, 0, sizeof(v22));
    CVssFunctionTracer::CheckForError(&v30, &v16, L"ReadFile");
  }
  if ( Buffer != 0x19D4FEFF5LL )
  {
    v16 = L"base\\stor\\vss\\modules\\coord\\src\\hwwrpdb.cxx";
    v17 = L"CVssHardwareProviderWrapper::LoadData";
    v18 = L"CORHWDBC";
    v19 = 509;
    v20 = 1;
    v21 = 255;
    v23 = 0x1000000;
    memset_0(v22, 0, sizeof(v22));
    CVssFunctionTracer::LogError((__int64)&v30, 0x3012u, (__int64)&v16, 1u);
    v16 = L"base\\stor\\vss\\modules\\coord\\src\\hwwrpdb.cxx";
    v17 = L"CVssHardwareProviderWrapper::LoadData";
    v18 = L"CORHWDBC";
    v19 = 512;
    v20 = 1;
    v21 = 255;
    v23 = 0x1000000;
    memset_0(v22, 0, sizeof(v22));
    CVssFunctionTracer::Throw(&v30, &v16, 2147754754LL, L"Contents of the hardware snapshot set database are invalid");
  }
  for ( i = v38; i; --i )
  {
    v35 = 0;
    v36 = 0;
    if ( !ReadFile(hFile, &v35, 0x14u, &NumberOfBytesRead, 0) )
    {
      v4 = GetLastError();
      if ( v4 > 0 )
        v4 = (unsigned __int16)v4 | 0x80070000;
      v31 = v4;
      v16 = L"base\\stor\\vss\\modules\\coord\\src\\hwwrpdb.cxx";
      v17 = L"CVssHardwareProviderWrapper::LoadData";
      v18 = L"CORHWDBC";
      v19 = 528;
      v20 = 1;
      v21 = 255;
      v23 = 0x1000000;
      memset_0(v22, 0, sizeof(v22));
      CVssFunctionTracer::CheckForError(&v30, &v16, L"ReadFile");
    }
    v5 = 2LL * (unsigned int)v35;
    if ( !is_mul_ok((unsigned int)v35, 2u) )
      v5 = -1;
    v6 = operator new[](v5, (const struct std::nothrow_t *)&std::nothrow);
    v14 = v6;
    if ( !v6 )
    {
      v16 = L"base\\stor\\vss\\modules\\coord\\src\\hwwrpdb.cxx";
      v17 = L"CVssHardwareProviderWrapper::LoadData";
      v18 = L"CORHWDBC";
      v19 = 540;
      v20 = 1;
      v21 = 255;
      v23 = 0x1000000;
      memset_0(v22, 0, sizeof(v22));
      CVssFunctionTracer::Throw(&v30, &v16, 2147942414LL, L"Cant allocate XML string");
    }
    try
    {
      v7 = (VSS_SNAPSHOT_SET_LIST *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v7 )
        v8 = VSS_SNAPSHOT_SET_LIST::VSS_SNAPSHOT_SET_LIST(v7);
      else
        v8 = 0;
      v15 = v8;
      if ( !v8 )
      {
        v16 = L"base\\stor\\vss\\modules\\coord\\src\\hwwrpdb.cxx";
        v17 = L"CVssHardwareProviderWrapper::LoadData";
        v18 = L"CORHWDBC";
        v19 = 547;
        v20 = 1;
        v21 = 255;
        v23 = 0x1000000;
        memset_0(v22, 0, sizeof(v22));
        CVssFunctionTracer::Throw(&v30, &v16, 2147942414LL, L"Cant allocate snapshot set description");
      }
      if ( !ReadFile(hFile, v6, 2 * v35, &NumberOfBytesRead, 0) )
      {
        v9 = GetLastError();
        if ( v9 > 0 )
          v9 = (unsigned __int16)v9 | 0x80070000;
        v31 = v9;
        v16 = L"base\\stor\\vss\\modules\\coord\\src\\hwwrpdb.cxx";
        v17 = L"CVssHardwareProviderWrapper::LoadData";
        v18 = L"CORHWDBC";
        v19 = 553;
        v20 = 1;
        v21 = 255;
        v23 = 0x1000000;
        memset_0(v22, 0, sizeof(v22));
        CVssFunctionTracer::CheckForError(&v30, &v16, L"ReadFile");
      }
      v25 = GUID_NULL;
      v31 = LoadVssSnapshotSetDescription(v6, (char *)v8 + 24, &v25);
      v16 = L"base\\stor\\vss\\modules\\coord\\src\\hwwrpdb.cxx";
      v17 = L"CVssHardwareProviderWrapper::LoadData";
      v18 = L"CORHWDBC";
      v19 = 560;
      v20 = 1;
      v21 = 255;
      v23 = 0x1000000;
      memset_0(v22, 0, sizeof(v22));
      CVssFunctionTracer::CheckForErrorInternal(&v30, &v16, L"LoadVssSnapshotSetDescription");
      v31 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v8 + 3) + 40LL))(
              *((_QWORD *)v8 + 3),
              (__int64)v8 + 8);
      v16 = L"base\\stor\\vss\\modules\\coord\\src\\hwwrpdb.cxx";
      v17 = L"CVssHardwareProviderWrapper::LoadData";
      v18 = L"CORHWDBC";
      v19 = 564;
      v20 = 1;
      v21 = 255;
      v23 = 0x1000000;
      memset_0(v22, 0, sizeof(v22));
      CVssFunctionTracer::CheckForErrorInternal(&v30, &v16, L"IVssSnapshotSetDescription::GetSnapshotSetId");
      v10 = v26;
      *(_QWORD *)v8 = *((_QWORD *)v26 + 22);
      *((_QWORD *)v10 + 22) = v8;
      operator delete(v6);
    }
    catch ( long v29 )
    {
      CVssFunctionTracer::HandleHresultException(
        (CVssFunctionTracer *)&v30,
        v29,
        L"base\\stor\\vss\\modules\\coord\\src\\hwwrpdb.cxx",
        L"CORHWDBC",
        L"CVssHardwareProviderWrapper::LoadData",
        0x23Du,
        v32);
      v6 = v14;
      v8 = v15;
    }
    catch ( _com_error *v33 )
    {
      CVssFunctionTracer::HandleComException(
        (CVssFunctionTracer *)&v30,
        v33,
        L"base\\stor\\vss\\modules\\coord\\src\\hwwrpdb.cxx",
        L"CORHWDBC",
        L"CVssHardwareProviderWrapper::LoadData",
        0x23Du,
        v32);
    }
    catch ( std::bad_alloc )
    {
      CVssFunctionTracer::HandleStdBadAllocException(
        (CVssFunctionTracer *)&v30,
        L"base\\stor\\vss\\modules\\coord\\src\\hwwrpdb.cxx",
        L"CORHWDBC",
        L"CVssHardwareProviderWrapper::LoadData",
        0x23Du,
        v32);
      v6 = v14;
      v8 = v15;
    }
    catch ( const std::exception *v34 )
    {
      CVssFunctionTracer::HandleStdGenericException(
        (CVssFunctionTracer *)&v30,
        v34,
        L"base\\stor\\vss\\modules\\coord\\src\\hwwrpdb.cxx",
        L"CORHWDBC",
        L"CVssHardwareProviderWrapper::LoadData",
        0x23Du,
        v32);
    }
    if ( v31 < 0 )
    {
      operator delete(v6);
      if ( v8 )
        VSS_SNAPSHOT_SET_LIST::`scalar deleting destructor'(v8, v11);
      pExceptionObject = v31;
      throw (long *)&pExceptionObject;
    }
  }
  CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::~CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>(&v27);
  CVssFunctionTracer::~CVssFunctionTracer(&v30);
}

```

## disassembly

```asm
0x14008d76c  push    rbx
0x14008d76e  push    rdi
0x14008d76f  push    r12
0x14008d771  push    r13
0x14008d773  push    r14
0x14008d775  push    r15
0x14008d777  sub     rsp, 1F8h
0x14008d77e  mov     rax, cs:__security_cookie
0x14008d785  xor     rax, rsp
0x14008d788  mov     [rsp+228h+var_40], rax
0x14008d790  mov     rbx, rcx
0x14008d793  mov     [rsp+228h+var_108], rcx
0x14008d79b  lea     r15, aBaseStorVssMod_20; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x14008d7a2  mov     [rsp+228h+var_1D0], r15
0x14008d7a7  lea     r12, aCvsshardwarepr_84; "CVssHardwareProviderWrapper::LoadData"
0x14008d7ae  mov     [rsp+228h+var_1C8], r12
0x14008d7b3  lea     r13, aCorhwdbc; "CORHWDBC"
0x14008d7ba  mov     [rsp+228h+var_1C0], r13
0x14008d7bf  mov     [rsp+228h+var_1B8], 1E8h
0x14008d7c7  mov     [rsp+228h+var_1B4], 1
0x14008d7cf  mov     r14d, 0FFh
0x14008d7d5  mov     [rsp+228h+var_1B0], r14d
0x14008d7da  xor     edi, edi
0x14008d7dc  mov     [rsp+228h+var_130], 1000000h
0x14008d7e7  xor     edx, edx; Val
0x14008d7e9  lea     r8d, [rdi+78h]; Size
0x14008d7ed  lea     rcx, [rsp+228h+var_1A8]; void *
0x14008d7f5  call    memset_0
0x14008d7fa  xor     r8d, r8d
0x14008d7fd  lea     rdx, [rsp+228h+var_1D0]
0x14008d802  lea     rcx, [rsp+228h+var_E8]
0x14008d80a  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x14008d80f  nop
0x14008d810  mov     rcx, rbx; this
0x14008d813  call    ?OpenDatabase@CVssHardwareProviderWrapper@@AEAAPEAXXZ; CVssHardwareProviderWrapper::OpenDatabase(void)
0x14008d818  lea     rcx, ??_7?$CVssAuto@PEAXV?$CVssAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x14008d81f  mov     [rsp+228h+var_100], rcx
0x14008d827  mov     [rsp+228h+hFile], rax
0x14008d82f  xor     ecx, ecx
0x14008d831  mov     [rsp+228h+Buffer], rcx
0x14008d839  mov     [rsp+228h+var_48], ecx
0x14008d840  mov     [rsp+228h+NumberOfBytesRead], edi
0x14008d844  mov     [rsp+228h+lpOverlapped], rdi; lpOverlapped
0x14008d849  lea     r9, [rsp+228h+NumberOfBytesRead]; lpNumberOfBytesRead
0x14008d84e  lea     r8d, [rdi+0Ch]; nNumberOfBytesToRead
0x14008d852  lea     rdx, [rsp+228h+Buffer]; lpBuffer
0x14008d85a  mov     rcx, rax; hFile
0x14008d85d  call    cs:__imp_ReadFile
0x14008d863  test    eax, eax
0x14008d865  jnz     short loc_14008D8E1
0x14008d867  call    cs:__imp_GetLastError
0x14008d86d  test    eax, eax
0x14008d86f  jle     short loc_14008D879
0x14008d871  movzx   eax, ax
0x14008d874  or      eax, 80070000h
0x14008d879  mov     [rsp+228h+var_E0], eax
0x14008d880  mov     [rsp+228h+var_1D0], r15
0x14008d885  mov     [rsp+228h+var_1C8], r12
0x14008d88a  mov     [rsp+228h+var_1C0], r13
0x14008d88f  mov     [rsp+228h+var_1B8], 1F4h
0x14008d897  mov     [rsp+228h+var_1B4], 1
0x14008d89f  mov     [rsp+228h+var_1B0], r14d
0x14008d8a4  mov     [rsp+228h+var_130], 1000000h
0x14008d8af  mov     ebx, 78h ; 'x'
0x14008d8b4  mov     r8d, ebx; Size
0x14008d8b7  xor     edx, edx; Val
0x14008d8b9  lea     rcx, [rsp+228h+var_1A8]; void *
0x14008d8c1  call    memset_0
0x14008d8c6  lea     r8, aReadfile; "ReadFile"
0x14008d8cd  lea     rdx, [rsp+228h+var_1D0]
0x14008d8d2  lea     rcx, [rsp+228h+var_E8]
0x14008d8da  call    ?CheckForError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForError(CVssDebugInfo,ushort const *)
0x14008d8df  jmp     short loc_14008D8E6
0x14008d8e1  mov     ebx, 78h ; 'x'
0x14008d8e6  cmp     dword ptr [rsp+228h+Buffer], 9D4FEFF5h
0x14008d8f1  jnz     loc_14008DD78
0x14008d8f7  cmp     dword ptr [rsp+228h+Buffer+4], 1
0x14008d8ff  jnz     loc_14008DD78
0x14008d905  mov     eax, [rsp+228h+var_48]
0x14008d90c  mov     [rsp+228h+var_1E4], eax
0x14008d910  cmp     [rsp+228h+var_1E4], edi
0x14008d914  jz      loc_14008DD3B
0x14008d91a  xorps   xmm0, xmm0
0x14008d91d  xor     eax, eax
0x14008d91f  movups  [rsp+228h+var_68], xmm0
0x14008d927  mov     [rsp+228h+var_58], eax
0x14008d92e  mov     [rsp+228h+lpOverlapped], rdi; lpOverlapped
0x14008d933  lea     r9, [rsp+228h+NumberOfBytesRead]; lpNumberOfBytesRead
0x14008d938  lea     r8d, [rax+14h]; nNumberOfBytesToRead
0x14008d93c  lea     rdx, [rsp+228h+var_68]; lpBuffer
0x14008d944  mov     rcx, [rsp+228h+hFile]; hFile
0x14008d94c  call    cs:__imp_ReadFile
0x14008d952  test    eax, eax
0x14008d954  jnz     short loc_14008D9C9
0x14008d956  call    cs:__imp_GetLastError
0x14008d95c  test    eax, eax
0x14008d95e  jle     short loc_14008D968
0x14008d960  movzx   eax, ax
0x14008d963  or      eax, 80070000h
0x14008d968  mov     [rsp+228h+var_E0], eax
0x14008d96f  mov     [rsp+228h+var_1D0], r15
0x14008d974  mov     [rsp+228h+var_1C8], r12
0x14008d979  mov     [rsp+228h+var_1C0], r13
0x14008d97e  mov     [rsp+228h+var_1B8], 210h
0x14008d986  mov     [rsp+228h+var_1B4], 1
0x14008d98e  mov     [rsp+228h+var_1B0], r14d
0x14008d993  mov     [rsp+228h+var_130], 1000000h
0x14008d99e  mov     r8, rbx; Size
0x14008d9a1  xor     edx, edx; Val
0x14008d9a3  lea     rcx, [rsp+228h+var_1A8]; void *
0x14008d9ab  call    memset_0
0x14008d9b0  lea     r8, aReadfile; "ReadFile"
0x14008d9b7  lea     rdx, [rsp+228h+var_1D0]
0x14008d9bc  lea     rcx, [rsp+228h+var_E8]
0x14008d9c4  call    ?CheckForError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForError(CVssDebugInfo,ushort const *)
0x14008d9c9  mov     ecx, dword ptr [rsp+228h+var_68]
0x14008d9d0  mov     eax, 2
0x14008d9d5  mul     rcx
0x14008d9d8  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14008d9df  cmovb   rax, rcx
0x14008d9e3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14008d9ea  mov     rcx, rax; unsigned __int64
0x14008d9ed  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14008d9f2  mov     r14, rax
0x14008d9f5  mov     [rsp+228h+var_1E0], rax
0x14008d9fa  test    rax, rax
0x14008d9fd  jnz     short loc_14008DA63
0x14008d9ff  mov     [rsp+228h+var_1D0], r15
0x14008da04  mov     [rsp+228h+var_1C8], r12
0x14008da09  mov     [rsp+228h+var_1C0], r13
0x14008da0e  mov     [rsp+228h+var_1B8], 21Ch
0x14008da16  mov     [rsp+228h+var_1B4], 1
0x14008da1e  mov     [rsp+228h+var_1B0], 0FFh
0x14008da26  mov     [rsp+228h+var_130], 1000000h
0x14008da31  mov     r8, rbx; Size
0x14008da34  xor     edx, edx; Val
0x14008da36  lea     rcx, [rsp+228h+var_1A8]; void *
0x14008da3e  call    memset_0
0x14008da43  lea     r9, aCantAllocateXm; "Cant allocate XML string"
0x14008da4a  mov     r8d, 8007000Eh
0x14008da50  lea     rdx, [rsp+228h+var_1D0]
0x14008da55  lea     rcx, [rsp+228h+var_E8]
0x14008da5d  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x14008da63  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14008da6a  mov     ecx, 20h ; ' '; unsigned __int64
0x14008da6f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14008da74  test    rax, rax
0x14008da77  jz      short loc_14008DA86
0x14008da79  mov     rcx, rax; this
0x14008da7c  call    ??0VSS_SNAPSHOT_SET_LIST@@QEAA@XZ; VSS_SNAPSHOT_SET_LIST::VSS_SNAPSHOT_SET_LIST(void)
0x14008da81  mov     rbx, rax
0x14008da84  jmp     short loc_14008DA89
0x14008da86  mov     rbx, rdi
0x14008da89  mov     [rsp+228h+var_1D8], rbx
0x14008da8e  test    rbx, rbx
0x14008da91  jnz     short loc_14008DAF7
0x14008da93  mov     [rsp+228h+var_1D0], r15
0x14008da98  mov     [rsp+228h+var_1C8], r12
0x14008da9d  mov     [rsp+228h+var_1C0], r13
0x14008daa2  mov     [rsp+228h+var_1B8], 223h
0x14008daaa  mov     [rsp+228h+var_1B4], 1
0x14008dab2  mov     [rsp+228h+var_1B0], 0FFh
0x14008daba  mov     [rsp+228h+var_130], 1000000h
0x14008dac5  xor     edx, edx; Val
0x14008dac7  lea     r8d, [rbx+78h]; Size
0x14008dacb  lea     rcx, [rsp+228h+var_1A8]; void *
0x14008dad3  call    memset_0
0x14008dad8  lea     r9, aCantAllocateSn; "Cant allocate snapshot set description"
0x14008dadf  mov     r8d, 8007000Eh
0x14008dae5  lea     rdx, [rsp+228h+var_1D0]
0x14008daea  lea     rcx, [rsp+228h+var_E8]
0x14008daf2  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x14008daf7  mov     r8d, dword ptr [rsp+228h+var_68]
0x14008daff  add     r8d, r8d; nNumberOfBytesToRead
0x14008db02  mov     [rsp+228h+lpOverlapped], rdi; lpOverlapped
0x14008db07  lea     r9, [rsp+228h+NumberOfBytesRead]; lpNumberOfBytesRead
0x14008db0c  mov     rdx, r14; lpBuffer
0x14008db0f  mov     rcx, [rsp+228h+hFile]; hFile
0x14008db17  call    cs:__imp_ReadFile
0x14008db1d  test    eax, eax
0x14008db1f  jnz     short loc_14008DB98
0x14008db21  call    cs:__imp_GetLastError
0x14008db27  test    eax, eax
0x14008db29  jle     short loc_14008DB33
0x14008db2b  movzx   eax, ax
0x14008db2e  or      eax, 80070000h
0x14008db33  mov     [rsp+228h+var_E0], eax
0x14008db3a  mov     [rsp+228h+var_1D0], r15
0x14008db3f  mov     [rsp+228h+var_1C8], r12
0x14008db44  mov     [rsp+228h+var_1C0], r13
0x14008db49  mov     [rsp+228h+var_1B8], 229h
0x14008db51  mov     [rsp+228h+var_1B4], 1
0x14008db59  mov     [rsp+228h+var_1B0], 0FFh
0x14008db61  mov     [rsp+228h+var_130], 1000000h
0x14008db6c  xor     edx, edx; Val
0x14008db6e  lea     r8d, [rdx+78h]; Size
0x14008db72  lea     rcx, [rsp+228h+var_1A8]; void *
0x14008db7a  call    memset_0
0x14008db7f  lea     r8, aReadfile; "ReadFile"
0x14008db86  lea     rdx, [rsp+228h+var_1D0]
0x14008db8b  lea     rcx, [rsp+228h+var_E8]
0x14008db93  call    ?CheckForError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForError(CVssDebugInfo,ushort const *)
0x14008db98  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x14008db9f  movdqu  [rsp+228h+var_118], xmm0
0x14008dba8  lea     rdx, [rbx+18h]
0x14008dbac  lea     r8, [rsp+228h+var_118]
0x14008dbb4  mov     rcx, r14
0x14008dbb7  call    cs:__imp_LoadVssSnapshotSetDescription
0x14008dbbd  mov     [rsp+228h+var_E0], eax
0x14008dbc4  mov     [rsp+228h+var_1D0], r15
0x14008dbc9  mov     [rsp+228h+var_1C8], r12
0x14008dbce  mov     [rsp+228h+var_1C0], r13
0x14008dbd3  mov     [rsp+228h+var_1B8], 230h
0x14008dbdb  mov     [rsp+228h+var_1B4], 1
0x14008dbe3  mov     [rsp+228h+var_1B0], 0FFh
0x14008dbeb  mov     [rsp+228h+var_130], 1000000h
0x14008dbf6  xor     edx, edx; Val
0x14008dbf8  lea     r8d, [rdx+78h]; Size
0x14008dbfc  lea     rcx, [rsp+228h+var_1A8]; void *
0x14008dc04  call    memset_0
0x14008dc09  lea     r8, aLoadvsssnapsho; "LoadVssSnapshotSetDescription"
0x14008dc10  lea     rdx, [rsp+228h+var_1D0]
0x14008dc15  lea     rcx, [rsp+228h+var_E8]
0x14008dc1d  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x14008dc22  mov     rcx, [rbx+18h]
0x14008dc26  mov     rax, [rcx]
0x14008dc29  lea     rdx, [rbx+8]
0x14008dc2d  mov     rax, [rax+28h]
0x14008dc31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008dc36  mov     [rsp+228h+var_E0], eax
0x14008dc3d  mov     [rsp+228h+var_1D0], r15
0x14008dc42  mov     [rsp+228h+var_1C8], r12
0x14008dc47  mov     [rsp+228h+var_1C0], r13
0x14008dc4c  mov     [rsp+228h+var_1B8], 234h
0x14008dc54  mov     [rsp+228h+var_1B4], 1
0x14008dc5c  mov     [rsp+228h+var_1B0], 0FFh
0x14008dc64  mov     [rsp+228h+var_130], 1000000h
0x14008dc6f  xor     edx, edx; Val
0x14008dc71  lea     r8d, [rdx+78h]; Size
0x14008dc75  lea     rcx, [rsp+228h+var_1A8]; void *
0x14008dc7d  call    memset_0
0x14008dc82  lea     r8, aIvsssnapshotse_9; "IVssSnapshotSetDescription::GetSnapshot"...
0x14008dc89  lea     rdx, [rsp+228h+var_1D0]
0x14008dc8e  lea     rcx, [rsp+228h+var_E8]
0x14008dc96  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x14008dc9b  mov     rcx, [rsp+228h+var_108]
0x14008dca3  mov     rax, [rcx+0B0h]
0x14008dcaa  mov     [rbx], rax
0x14008dcad  mov     [rcx+0B0h], rbx
0x14008dcb4  mov     rcx, r14; Block
0x14008dcb7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14008dcbc  nop
0x14008dcbd  jmp     short loc_14008DCE6
0x14008dcbf  jmp     short loc_14008DCC5
0x14008dcc1  jmp     short loc_14008DCC5
0x14008dcc3  jmp     short $+2
0x14008dcc5  mov     r14, [rsp+228h+var_1E0]
0x14008dcca  mov     rbx, [rsp+228h+var_1D8]
0x14008dccf  xor     edi, edi
0x14008dcd1  lea     r13, aCorhwdbc; "CORHWDBC"
0x14008dcd8  lea     r12, aCvsshardwarepr_84; "CVssHardwareProviderWrapper::LoadData"
0x14008dcdf  lea     r15, aBaseStorVssMod_20; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x14008dce6  cmp     [rsp+228h+var_E0], edi
0x14008dced  jge     short loc_14008DD27
0x14008dcef  mov     rcx, r14; Block
0x14008dcf2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14008dcf7  test    rbx, rbx
0x14008dcfa  jz      short loc_14008DD04
0x14008dcfc  mov     rcx, rbx; this
0x14008dcff  call    ??_GVSS_SNAPSHOT_SET_LIST@@QEAAPEAXI@Z; VSS_SNAPSHOT_SET_LIST::`scalar deleting destructor'(uint)
0x14008dd04  mov     eax, [rsp+228h+var_E0]
0x14008dd0b  mov     [rsp+228h+pExceptionObject], eax
0x14008dd12  lea     rdx, _TI1J; pThrowInfo
0x14008dd19  lea     rcx, [rsp+228h+pExceptionObject]; pExceptionObject
0x14008dd21  call    _CxxThrowException_0
0x14008dd27  dec     [rsp+228h+var_1E4]
0x14008dd2b  mov     ebx, 78h ; 'x'
0x14008dd30  mov     r14d, 0FFh
0x14008dd36  jmp     loc_14008D910
0x14008dd3b  lea     rcx, [rsp+228h+var_100]
0x14008dd43  call    ??1?$CVssAuto@PEAXV?$CVssAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@UEAA@XZ; CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::~CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>(void)
0x14008dd48  nop
0x14008dd49  lea     rcx, [rsp+228h+var_E8]; this
0x14008dd51  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x14008dd56  mov     rcx, [rsp+228h+var_40]
0x14008dd5e  xor     rcx, rsp; StackCookie
0x14008dd61  call    __security_check_cookie
0x14008dd66  add     rsp, 1F8h
0x14008dd6d  pop     r15
0x14008dd6f  pop     r14
0x14008dd71  pop     r13
0x14008dd73  pop     r12
0x14008dd75  pop     rdi
0x14008dd76  pop     rbx
0x14008dd77  retn
0x14008dd78  mov     [rsp+228h+var_1D0], r15
0x14008dd7d  mov     [rsp+228h+var_1C8], r12
0x14008dd82  mov     [rsp+228h+var_1C0], r13
0x14008dd87  mov     [rsp+228h+var_1B8], 1FDh
0x14008dd8f  mov     [rsp+228h+var_1B4], 1
  ... truncated ...
```
