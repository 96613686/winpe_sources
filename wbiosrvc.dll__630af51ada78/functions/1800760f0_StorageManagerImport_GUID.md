# StorageManagerImport(_GUID)

- ea: `0x1800760f0`
- end: `0x18007643c`
- name: `?StorageManagerImport@@YAJU_GUID@@@Z`
- size: `844`
- prototype: `__int64 __fastcall(struct _GUID *__struct_ptr)`
- caller_count: `2`
- callee_count: `21`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180045044`
- `0x180071de8`

## callees

- `0x1800305f4`
- `0x18003903c`
- `0x18003f2dc`
- `0x1800413d8`
- `0x180044b1c`
- `0x18005388c`
- `0x180054720`
- `0x1800549a0`
- `0x180055b14`
- `0x180056358`
- `0x180058680`
- `0x18005e764`
- `0x1800610b4`
- `0x180068f60`
- `0x180075aa4`
- `0x180075abc`
- `0x1800760f0`
- `0x1800764a8`
- `0x1800b8324`
- `0x1800b83d4`
- `0x1800b8450`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007629b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800763a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180076402`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007629b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800763a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180076402`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800761ad`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800761ad`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18007617f`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18007617f`

## string_xrefs

- `0x180076163`: `onecore\ds\security\biometrics\service\server\storagemanager.cpp`
- `0x18007627c`: `onecore\ds\security\biometrics\service\server\storagemanager.cpp`
- `0x180076372`: `onecore\ds\security\biometrics\service\server\storagemanager.cpp`
- `0x1800763cc`: `onecore\ds\security\biometrics\service\server\storagemanager.cpp`
- `0x1800763e2`: `onecore\ds\security\biometrics\service\server\storagemanager.cpp`

## pseudocode

```c
__int64 __fastcall StorageManagerImport(struct _GUID *a1)
{
  int FileHandle; // ebx
  unsigned __int64 FileSize; // rdi
  const char *v4; // r9
  int v5; // eax
  __int64 v6; // rdx
  unsigned __int8 *v7; // r14
  unsigned __int64 v8; // rbx
  int v9; // eax
  int v10; // r15d
  char IsEnabled; // al
  void *v12; // rcx
  bool IsZero; // al
  struct _GUID *v14; // r9
  int v15; // eax
  void *v16; // rcx
  void *v18; // rcx
  bool v19; // zf
  int lpOverlapped; // [rsp+20h] [rbp-69h]
  int lpOverlappeda; // [rsp+20h] [rbp-69h]
  LPVOID lpBuffer; // [rsp+30h] [rbp-59h] BYREF
  unsigned int v23; // [rsp+38h] [rbp-51h] BYREF
  HANDLE hFile[2]; // [rsp+40h] [rbp-49h] BYREF
  struct _GUID v25; // [rsp+50h] [rbp-39h] BYREF
  struct _GUID v26; // [rsp+60h] [rbp-29h] BYREF
  char v27; // [rsp+70h] [rbp-19h]
  DWORD NumberOfBytesRead; // [rsp+80h] [rbp-9h] BYREF
  __int64 v29; // [rsp+88h] [rbp-1h] BYREF
  int v30; // [rsp+90h] [rbp+7h] BYREF
  char v31; // [rsp+94h] [rbp+Bh]
  char v32; // [rsp+98h] [rbp+Fh] BYREF
  struct _GUID v33; // [rsp+A8h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  hFile[0] = 0;
  *(_QWORD *)&v26.Data1 = hFile;
  *(_QWORD *)v26.Data4 = 0;
  v27 = 1;
  v25 = *a1;
  FileHandle = GetFileHandle(&v25, 1, (void **)v26.Data4);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v26);
  if ( FileHandle < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\storagemanager.cpp",
      (const char *)(unsigned int)FileHandle,
      lpOverlapped);
LABEL_38:
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hFile);
    return (unsigned int)FileHandle;
  }
  FileSize = GetFileSize(hFile[0], 0);
  wil::make_unique_hlocal<unsigned char [0]>(&lpBuffer, FileSize);
  NumberOfBytesRead = 0;
  if ( !ReadFile(hFile[0], lpBuffer, FileSize, &NumberOfBytesRead, 0) )
  {
    FileHandle = wil::details::in1diag3::Return_GetLastError(
                   retaddr,
                   (void *)0x49,
                   (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\storagemanager.cpp",
                   v4);
LABEL_36:
    v18 = lpBuffer;
    v19 = lpBuffer == 0;
    lpBuffer = 0;
    if ( !v19 )
      LocalFree(v18);
    goto LABEL_38;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_K2DecryptDataHintReEncryption>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_K2DecryptDataHintReEncryption>::GetImpl'::`2'::impl) )
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      hFile,
      0);
  *(_QWORD *)&v26.Data1 = 0;
  v25 = *a1;
  v5 = BioIsoStorageManagerImportBegin(&v25, FileSize, (unsigned __int64 *)&v26.Data1);
  FileHandle = v5;
  if ( v5 < 0 )
  {
    v6 = 87;
LABEL_34:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\storagemanager.cpp",
      (const char *)(unsigned int)v5,
      lpOverlappeda);
    goto LABEL_36;
  }
  v7 = (unsigned __int8 *)lpBuffer;
  if ( FileSize )
  {
    while ( 1 )
    {
      v8 = FileSize;
      if ( FileSize > *(_QWORD *)&v26.Data1 )
        v8 = *(_QWORD *)&v26.Data1;
      v25 = *a1;
      v9 = BioIsoStorageManagerImportNext(&v25, v7, v8);
      v10 = v9;
      if ( v9 < 0 )
        break;
      v7 += v8;
      FileSize -= v8;
      if ( !FileSize )
        goto LABEL_13;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\storagemanager.cpp",
      (const char *)(unsigned int)v9,
      lpOverlappeda);
    v12 = lpBuffer;
    lpBuffer = 0;
    if ( v12 )
      LocalFree(v12);
    FileHandle = v10;
    goto LABEL_38;
  }
LABEL_13:
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_K2DecryptDataHintReEncryption>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_K2DecryptDataHintReEncryption>::GetImpl'::`2'::impl);
  v25 = *a1;
  if ( IsEnabled )
  {
    v5 = BioIsoStorageManagerImportEnd(&v25);
    FileHandle = v5;
    v23 = v5;
    if ( v5 < 0 )
    {
      v6 = 109;
      goto LABEL_34;
    }
    if ( v5 == 589827 )
    {
      v30 = 0;
      v31 = 0;
      _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(&v30);
      if ( (unsigned int)dword_18010F170 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18010F170, 0x400000000000LL) )
      {
        v29 = 0x1000000;
        v26.Data1 = v23;
        if ( !v31 || (IsZero = _tlgGuidIsZero(&v33), v14 = &v33, IsZero) )
          LODWORD(v14) = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_18010F170,
          (unsigned int)&dword_1800ED69C,
          (unsigned int)&v32,
          (_DWORD)v14,
          (__int64)&v26,
          (__int64)&v29);
      }
      *(_QWORD *)&v25.Data1 = &v30;
      *(_QWORD *)v25.Data4 = &v23;
      v29 = (__int64)&v25;
      v26 = *a1;
      v15 = StorageManagerExport(&v26);
      v23 = v15;
      if ( v15 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x7A,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\storagemanager.cpp",
          (const char *)(unsigned int)v15,
          lpOverlappeda);
      BioTraceUnwinder__lambda_13ca0c16870c55b50f51be10d3aff3bf____::_BioTraceUnwinder__lambda_13ca0c16870c55b50f51be10d3aff3bf____(&v29);
      _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(&v30);
    }
  }
  else
  {
    v5 = BioIsoStorageManagerImportEnd(&v25);
    FileHandle = v5;
    if ( v5 < 0 )
    {
      v6 = 129;
      goto LABEL_34;
    }
  }
  v16 = lpBuffer;
  lpBuffer = 0;
  if ( v16 )
    LocalFree(v16);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hFile);
  return 0;
}

```

## disassembly

```asm
0x1800760f0  mov     [rsp-8+arg_8], rbx
0x1800760f5  mov     [rsp-8+arg_10], rsi
0x1800760fa  push    rbp
0x1800760fb  push    rdi
0x1800760fc  push    r12
0x1800760fe  push    r14
0x180076100  push    r15
0x180076102  lea     rbp, [rsp-37h]
0x180076107  sub     rsp, 0C0h
0x18007610e  mov     rax, cs:__security_cookie
0x180076115  xor     rax, rsp
0x180076118  mov     [rbp+57h+var_28], rax
0x18007611c  mov     rsi, rcx
0x18007611f  xor     r12d, r12d
0x180076122  mov     [rbp+57h+hFile], r12
0x180076126  lea     rax, [rbp+57h+hFile]
0x18007612a  mov     qword ptr [rbp+57h+var_80.Data1], rax
0x18007612e  mov     qword ptr [rbp+57h+var_80.Data4], r12
0x180076132  mov     [rbp+57h+var_70], 1
0x180076136  movups  xmm0, xmmword ptr [rcx]
0x180076139  movdqu  xmmword ptr [rbp+57h+var_90.Data1], xmm0
0x18007613e  lea     r8, [rbp+57h+var_80.Data4]; void **
0x180076142  mov     dl, 1; bool
0x180076144  lea     rcx, [rbp+57h+var_90]; struct _GUID
0x180076148  call    ?GetFileHandle@@YAJU_GUID@@_NPEAPEAX@Z; GetFileHandle(_GUID,bool,void * *)
0x18007614d  mov     ebx, eax
0x18007614f  lea     rcx, [rbp+57h+var_80]
0x180076153  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x180076158  test    ebx, ebx
0x18007615a  jns     short loc_180076179
0x18007615c  mov     rcx, [rbp+5Fh]; this
0x180076160  mov     r9d, ebx; char *
0x180076163  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\biometrics\\serv"...
0x18007616a  lea     edx, [r12+3Ah]; void *
0x18007616f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076174  jmp     loc_180076409
0x180076179  xor     edx, edx; lpFileSizeHigh
0x18007617b  mov     rcx, [rbp+57h+hFile]; hFile
0x18007617f  call    cs:__imp_GetFileSize
0x180076185  mov     ebx, eax
0x180076187  mov     edi, eax
0x180076189  mov     edx, eax
0x18007618b  lea     rcx, [rbp+57h+lpBuffer]
0x18007618f  call    ??$make_unique_hlocal@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<uchar [0]>(unsigned __int64)
0x180076194  nop
0x180076195  mov     [rbp+57h+NumberOfBytesRead], r12d
0x180076199  mov     [rsp+0E0h+lpOverlapped], r12; int
0x18007619e  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800761a2  mov     r8d, ebx; nNumberOfBytesToRead
0x1800761a5  mov     rdx, [rbp+57h+lpBuffer]; lpBuffer
0x1800761a9  mov     rcx, [rbp+57h+hFile]; hFile
0x1800761ad  call    cs:__imp_ReadFile
0x1800761b3  test    eax, eax
0x1800761b5  jz      loc_1800763DE
0x1800761bb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_K2DecryptDataHintReEncryption@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_K2DecryptDataHintReEncryption@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_K2DecryptDataHintReEncryption> `wil::Feature<__WilFeatureTraits_Feature_K2DecryptDataHintReEncryption>::GetImpl(void)'::`2'::impl
0x1800761c2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_K2DecryptDataHintReEncryption@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_K2DecryptDataHintReEncryption>::__private_IsEnabled(void)
0x1800761c7  test    al, al
0x1800761c9  jz      short loc_1800761D6
0x1800761cb  xor     edx, edx
0x1800761cd  lea     rcx, [rbp+57h+hFile]
0x1800761d1  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800761d6  mov     qword ptr [rbp+57h+var_80.Data1], r12
0x1800761da  movups  xmm0, xmmword ptr [rsi]
0x1800761dd  movdqu  xmmword ptr [rbp+57h+var_90.Data1], xmm0
0x1800761e2  lea     r8, [rbp+57h+var_80]; unsigned __int64 *
0x1800761e6  mov     rdx, rdi; unsigned __int64
0x1800761e9  lea     rcx, [rbp+57h+var_90]; struct _GUID
0x1800761ed  call    ?BioIsoStorageManagerImportBegin@@YAJU_GUID@@_KPEA_K@Z; BioIsoStorageManagerImportBegin(_GUID,unsigned __int64,unsigned __int64 *)
0x1800761f2  mov     ebx, eax
0x1800761f4  test    eax, eax
0x1800761f6  jns     short loc_180076202
0x1800761f8  mov     edx, 57h ; 'W'
0x1800761fd  jmp     loc_1800763C9
0x180076202  mov     r14, [rbp+57h+lpBuffer]
0x180076206  test    rdi, rdi
0x180076209  jz      short loc_18007623D
0x18007620b  mov     rbx, rdi
0x18007620e  cmp     rdi, qword ptr [rbp+57h+var_80.Data1]
0x180076212  cmova   rbx, qword ptr [rbp+57h+var_80.Data1]
0x180076217  movups  xmm0, xmmword ptr [rsi]
0x18007621a  movdqu  xmmword ptr [rbp+57h+var_90.Data1], xmm0
0x18007621f  mov     r8, rbx; unsigned __int64
0x180076222  mov     rdx, r14; unsigned __int8 *
0x180076225  lea     rcx, [rbp+57h+var_90]; struct _GUID
0x180076229  call    ?BioIsoStorageManagerImportNext@@YAJU_GUID@@PEAE_K@Z; BioIsoStorageManagerImportNext(_GUID,uchar *,unsigned __int64)
0x18007622e  mov     r15d, eax
0x180076231  test    eax, eax
0x180076233  js      short loc_180076275
0x180076235  add     r14, rbx
0x180076238  sub     rdi, rbx
0x18007623b  jnz     short loc_18007620B
0x18007623d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_K2DecryptDataHintReEncryption@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_K2DecryptDataHintReEncryption@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_K2DecryptDataHintReEncryption> `wil::Feature<__WilFeatureTraits_Feature_K2DecryptDataHintReEncryption>::GetImpl(void)'::`2'::impl
0x180076244  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_K2DecryptDataHintReEncryption@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_K2DecryptDataHintReEncryption>::__private_IsEnabled(void)
0x180076249  movups  xmm0, xmmword ptr [rsi]
0x18007624c  lea     rcx, [rbp+57h+var_90]; struct _GUID
0x180076250  movdqu  xmmword ptr [rbp+57h+var_90.Data1], xmm0
0x180076255  test    al, al
0x180076257  jz      loc_1800763B9
0x18007625d  call    ?BioIsoStorageManagerImportEnd@@YAJU_GUID@@@Z; BioIsoStorageManagerImportEnd(_GUID)
0x180076262  mov     ebx, eax
0x180076264  mov     [rbp+57h+var_A8], eax
0x180076267  test    eax, eax
0x180076269  jns     short loc_1800762A9
0x18007626b  mov     edx, 6Dh ; 'm'
0x180076270  jmp     loc_1800763C9
0x180076275  mov     rcx, [rbp+5Fh]; this
0x180076279  mov     r9d, r15d; char *
0x18007627c  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\biometrics\\serv"...
0x180076283  mov     edx, 64h ; 'd'; void *
0x180076288  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007628d  nop
0x18007628e  mov     rcx, [rbp+57h+lpBuffer]; hMem
0x180076292  mov     [rbp+57h+lpBuffer], r12
0x180076296  test    rcx, rcx
0x180076299  jz      short loc_1800762A1
0x18007629b  call    cs:__imp_LocalFree
0x1800762a1  mov     ebx, r15d
0x1800762a4  jmp     loc_180076409
0x1800762a9  cmp     eax, 90003h
0x1800762ae  jnz     loc_180076398
0x1800762b4  mov     [rbp+57h+var_50], r12d
0x1800762b8  mov     [rbp+57h+var_4C], r12b
0x1800762bc  lea     rcx, [rbp+57h+var_50]
0x1800762c0  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(void)
0x1800762c5  mov     eax, cs:dword_18010F170
0x1800762cb  cmp     eax, 5
0x1800762ce  jbe     short loc_18007633B
0x1800762d0  mov     rdx, 400000000000h
0x1800762da  lea     rcx, dword_18010F170
0x1800762e1  call    _tlgKeywordOn
0x1800762e6  test    al, al
0x1800762e8  jz      short loc_18007633B
0x1800762ea  mov     [rbp+57h+var_58], 1000000h
0x1800762f2  mov     eax, [rbp+57h+var_A8]
0x1800762f5  mov     [rbp+57h+var_80.Data1], eax
0x1800762f8  cmp     [rbp+57h+var_4C], r12b
0x1800762fc  jz      short loc_18007630F
0x1800762fe  lea     rcx, [rbp+57h+var_38]; struct _GUID *
0x180076302  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180076307  test    al, al
0x180076309  lea     r9, [rbp+57h+var_38]
0x18007630d  jz      short loc_180076312
0x18007630f  mov     r9, r12
0x180076312  lea     rax, [rbp+57h+var_58]
0x180076316  mov     [rsp+0E0h+var_B8], rax
0x18007631b  lea     rax, [rbp+57h+var_80]
0x18007631f  mov     [rsp+0E0h+lpOverlapped], rax; int
0x180076324  lea     r8, [rbp+57h+var_48]
0x180076328  lea     rdx, dword_1800ED69C
0x18007632f  lea     rcx, dword_18010F170
0x180076336  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18007633b  lea     rax, [rbp+57h+var_50]
0x18007633f  mov     qword ptr [rbp+57h+var_90.Data1], rax
0x180076343  lea     rax, [rbp+57h+var_A8]
0x180076347  mov     qword ptr [rbp+57h+var_90.Data4], rax
0x18007634b  lea     rax, [rbp+57h+var_90]
0x18007634f  mov     [rbp+57h+var_58], rax
0x180076353  movups  xmm0, xmmword ptr [rsi]
0x180076356  movdqu  xmmword ptr [rbp+57h+var_80.Data1], xmm0
0x18007635b  lea     rcx, [rbp+57h+var_80]; struct _GUID
0x18007635f  call    ?StorageManagerExport@@YAJU_GUID@@@Z; StorageManagerExport(_GUID)
0x180076364  mov     [rbp+57h+var_A8], eax
0x180076367  mov     rcx, [rbp+5Fh]; this
0x18007636b  test    eax, eax
0x18007636d  jns     short loc_180076384
0x18007636f  mov     r9d, eax; char *
0x180076372  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\biometrics\\serv"...
0x180076379  mov     edx, 7Ah ; 'z'; void *
0x18007637e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180076383  nop
0x180076384  lea     rcx, [rbp+57h+var_58]
0x180076388  call    BioTraceUnwinder__lambda_13ca0c16870c55b50f51be10d3aff3bf_______BioTraceUnwinder__lambda_13ca0c16870c55b50f51be10d3aff3bf____
0x18007638d  nop
0x18007638e  lea     rcx, [rbp+57h+var_50]
0x180076392  call    ??1?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(void)
0x180076397  nop
0x180076398  mov     rcx, [rbp+57h+lpBuffer]; hMem
0x18007639c  mov     [rbp+57h+lpBuffer], r12
0x1800763a0  test    rcx, rcx
0x1800763a3  jz      short loc_1800763AC
0x1800763a5  call    cs:__imp_LocalFree
0x1800763ab  nop
0x1800763ac  lea     rcx, [rbp+57h+hFile]
0x1800763b0  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800763b5  xor     eax, eax
0x1800763b7  jmp     short loc_180076414
0x1800763b9  call    ?BioIsoStorageManagerImportEnd@@YAJU_GUID@@@Z; BioIsoStorageManagerImportEnd(_GUID)
0x1800763be  mov     ebx, eax
0x1800763c0  test    eax, eax
0x1800763c2  jns     short loc_180076398
0x1800763c4  mov     edx, 81h; void *
0x1800763c9  mov     r9d, eax; char *
0x1800763cc  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\biometrics\\serv"...
0x1800763d3  mov     rcx, [rbp+5Fh]; this
0x1800763d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800763dc  jmp     short loc_1800763F5
0x1800763de  mov     rcx, [rbp+5Fh]; this
0x1800763e2  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\biometrics\\serv"...
0x1800763e9  mov     edx, 49h ; 'I'; void *
0x1800763ee  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800763f3  mov     ebx, eax
0x1800763f5  mov     rcx, [rbp+57h+lpBuffer]; hMem
0x1800763f9  test    rcx, rcx
0x1800763fc  mov     [rbp+57h+lpBuffer], r12
0x180076400  jz      short loc_180076409
0x180076402  call    cs:__imp_LocalFree
0x180076408  nop
0x180076409  lea     rcx, [rbp+57h+hFile]
0x18007640d  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180076412  mov     eax, ebx
0x180076414  mov     rcx, [rbp+57h+var_28]
0x180076418  xor     rcx, rsp; StackCookie
0x18007641b  call    __security_check_cookie
0x180076420  lea     r11, [rsp+0E0h+var_20]
0x180076428  mov     rbx, [r11+38h]
0x18007642c  mov     rsi, [r11+40h]
0x180076430  mov     rsp, r11
0x180076433  pop     r15
0x180076435  pop     r14
0x180076437  pop     r12
0x180076439  pop     rdi
0x18007643a  pop     rbp
0x18007643b  retn
```
