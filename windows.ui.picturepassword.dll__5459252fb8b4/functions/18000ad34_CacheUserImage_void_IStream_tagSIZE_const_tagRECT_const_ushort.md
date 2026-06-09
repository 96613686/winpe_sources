# _CacheUserImage(void *,IStream *,tagSIZE const &,tagRECT const &,ushort * *)

- ea: `0x18000ad34`
- end: `0x18000af96`
- name: `?_CacheUserImage@@YAJPEAXPEAUIStream@@AEBUtagSIZE@@AEBUtagRECT@@PEAPEAG@Z`
- size: `610`
- prototype: `__int64 __fastcall(void *, struct IStream *, const struct tagSIZE *, const struct tagRECT *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x18000b318`

## callees

- `0x180002610`
- `0x1800043a4`
- `0x1800056a0`
- `0x180006414`
- `0x180008558`
- `0x18000ad34`
- `0x180016180`
- `0x180016dfc`
- `0x180016fac`
- `0x18001720c`
- `0x18001f010`

## import_xrefs

- `SHCORE!SHCreateMemStream` at `0x18000ae9d`
- `SHCORE!SHCreateMemStream` at `0x18000ae9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000af57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000af57`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000add2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000addd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000add2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000addd`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000af1a`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000af1a`

## pseudocode

```c
__int64 __fastcall _CacheUserImage(
        void *a1,
        struct IStream *a2,
        const struct tagSIZE *a3,
        const struct tagRECT *a4,
        unsigned __int16 **a5)
{
  int inited; // edi
  IStream *v10; // rax
  struct IStream *v11; // rbx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r9
  __int64 v21; // [rsp+20h] [rbp-E0h]
  __int64 v22; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE v24; // [rsp+50h] [rbp-B0h] BYREF
  BYTE *pInit; // [rsp+58h] [rbp-A8h] BYREF
  struct IStream *v26[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v27; // [rsp+70h] [rbp-90h] BYREF
  WCHAR pszPath[264]; // [rsp+80h] [rbp-80h] BYREF

  v22 = 0;
  *a5 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
  v22 = 0;
  hObject = 0;
  v24 = 0;
  inited = _InitRestrictedProcess(&hObject, &v24);
  if ( inited >= 0 )
  {
    inited = CreateInstanceInProcess(hObject, (__int64)&v22);
    CloseHandle(hObject);
    CloseHandle(v24);
    if ( inited >= 0 )
    {
      v27 = 0;
      inited = (*(__int64 (__fastcall **)(__int64, struct IStream *, __int64 *))(*(_QWORD *)v22 + 32LL))(v22, a2, &v27);
      if ( inited >= 0 )
      {
        inited = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v22 + 40LL))(v22, *a3);
        if ( inited >= 0 )
        {
          *(struct tagRECT *)v26 = *a4;
          inited = (*(__int64 (__fastcall **)(__int64, struct IStream **))(*(_QWORD *)v22 + 48LL))(v22, v26);
          if ( inited >= 0 )
          {
            pInit = 0;
            LODWORD(v24) = 0;
            inited = (*(__int64 (__fastcall **)(__int64, BYTE **, HANDLE *))(*(_QWORD *)v22 + 64LL))(v22, &pInit, &v24);
            if ( inited >= 0 )
            {
              inited = -2147024882;
              v26[0] = 0;
              v10 = SHCreateMemStream(pInit, (UINT)v24);
              Microsoft::WRL::ComPtr<CMarshaledInterface::CMarshalStream>::Attach(v26, v10);
              v11 = v26[0];
              if ( v26[0] )
              {
                hObject = 0;
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&hObject);
                inited = MakeImageStreamOpaque(v11, (struct IStream **)&hObject);
                if ( inited >= 0 )
                {
                  inited = SaveStreamToSystemDataFolder(a1, v12, v13, v14, v21, (__int64)hObject);
                  if ( inited >= 0 )
                  {
                    inited = GetSystemDataFolderForUser(a1, v15, v16, pszPath);
                    if ( inited >= 0 )
                    {
                      inited = PathCchAppend(pszPath, 0x104u, L"background.png");
                      if ( inited >= 0 )
                      {
                        v19 = -1;
                        do
                          ++v19;
                        while ( pszPath[v19] );
                        inited = _AllocStringWorker<CTCoAllocPolicy>(v18, v17, pszPath);
                      }
                    }
                  }
                }
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&hObject);
              }
              CoTaskMemFree(pInit);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v26);
            }
          }
        }
      }
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18000ad34  push    rbp
0x18000ad36  push    rbx
0x18000ad37  push    rsi
0x18000ad38  push    rdi
0x18000ad39  push    r12
0x18000ad3b  push    r13
0x18000ad3d  push    r14
0x18000ad3f  push    r15
0x18000ad41  lea     rbp, [rsp-1A8h]
0x18000ad49  sub     rsp, 2A8h
0x18000ad50  mov     rax, cs:__security_cookie
0x18000ad57  xor     rax, rsp
0x18000ad5a  mov     [rbp+1E0h+var_50], rax
0x18000ad61  mov     r12, [rbp+1E0h+arg_20]
0x18000ad68  mov     rsi, rcx
0x18000ad6b  xor     r13d, r13d
0x18000ad6e  lea     rcx, [rsp+2E0h+var_2A0]
0x18000ad73  mov     r15, r9
0x18000ad76  mov     [rsp+2E0h+var_2A0], r13
0x18000ad7b  mov     r14, r8
0x18000ad7e  mov     rbx, rdx
0x18000ad81  mov     [r12], r13
0x18000ad85  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000ad8a  lea     rdx, [rsp+2E0h+var_290]; void **
0x18000ad8f  mov     [rsp+2E0h+var_2A0], r13
0x18000ad94  lea     rcx, [rsp+2E0h+hObject]; void **
0x18000ad99  mov     [rsp+2E0h+hObject], r13
0x18000ad9e  mov     [rsp+2E0h+var_290], r13
0x18000ada3  call    ?_InitRestrictedProcess@@YAJPEAPEAX0@Z; _InitRestrictedProcess(void * *,void * *)
0x18000ada8  mov     edi, eax
0x18000adaa  test    eax, eax
0x18000adac  js      loc_18000AF67
0x18000adb2  mov     rdx, [rsp+2E0h+var_290]
0x18000adb7  lea     rax, [rsp+2E0h+var_2A0]
0x18000adbc  mov     rcx, [rsp+2E0h+hObject]; ProcessHandle
0x18000adc1  mov     [rsp+2E0h+var_2C0], rax; __int64
0x18000adc6  call    _CreateInstanceInProcess
0x18000adcb  mov     rcx, [rsp+2E0h+hObject]; hObject
0x18000add0  mov     edi, eax
0x18000add2  call    cs:__imp_CloseHandle
0x18000add8  mov     rcx, [rsp+2E0h+var_290]; hObject
0x18000addd  call    cs:__imp_CloseHandle
0x18000ade3  test    edi, edi
0x18000ade5  js      loc_18000AF67
0x18000adeb  mov     rcx, [rsp+2E0h+var_2A0]
0x18000adf0  lea     r8, [rsp+2E0h+var_270]
0x18000adf5  mov     [rsp+2E0h+var_270], r13
0x18000adfa  mov     rdx, rbx
0x18000adfd  mov     rax, [rcx]
0x18000ae00  mov     rax, [rax+20h]
0x18000ae04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae09  mov     edi, eax
0x18000ae0b  test    eax, eax
0x18000ae0d  js      loc_18000AF67
0x18000ae13  mov     rcx, [rsp+2E0h+var_2A0]
0x18000ae18  mov     rdx, [r14]
0x18000ae1b  mov     rax, [rcx]
0x18000ae1e  mov     rax, [rax+28h]
0x18000ae22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae27  mov     edi, eax
0x18000ae29  test    eax, eax
0x18000ae2b  js      loc_18000AF67
0x18000ae31  mov     rcx, [rsp+2E0h+var_2A0]
0x18000ae36  lea     rdx, [rsp+2E0h+var_280]
0x18000ae3b  movaps  xmm0, xmmword ptr [r15]
0x18000ae3f  movdqa  xmmword ptr [rsp+2E0h+var_280], xmm0
0x18000ae45  mov     rax, [rcx]
0x18000ae48  mov     rax, [rax+30h]
0x18000ae4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae51  mov     edi, eax
0x18000ae53  test    eax, eax
0x18000ae55  js      loc_18000AF67
0x18000ae5b  mov     rcx, [rsp+2E0h+var_2A0]
0x18000ae60  lea     r8, [rsp+2E0h+var_290]
0x18000ae65  mov     [rsp+2E0h+pInit], r13
0x18000ae6a  lea     rdx, [rsp+2E0h+pInit]
0x18000ae6f  mov     dword ptr [rsp+2E0h+var_290], r13d
0x18000ae74  mov     rax, [rcx]
0x18000ae77  mov     rax, [rax+40h]
0x18000ae7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae80  mov     edi, eax
0x18000ae82  test    eax, eax
0x18000ae84  js      loc_18000AF67
0x18000ae8a  mov     edx, dword ptr [rsp+2E0h+var_290]; cbInit
0x18000ae8e  mov     edi, 8007000Eh
0x18000ae93  mov     rcx, [rsp+2E0h+pInit]; pInit
0x18000ae98  mov     [rsp+2E0h+var_280], r13
0x18000ae9d  call    cs:__imp_SHCreateMemStream
0x18000aea3  mov     rdx, rax
0x18000aea6  lea     rcx, [rsp+2E0h+var_280]
0x18000aeab  call    ?Attach@?$ComPtr@VCMarshalStream@CMarshaledInterface@@@WRL@Microsoft@@QEAAXPEAVCMarshalStream@CMarshaledInterface@@@Z; Microsoft::WRL::ComPtr<CMarshaledInterface::CMarshalStream>::Attach(CMarshaledInterface::CMarshalStream *)
0x18000aeb0  mov     rbx, [rsp+2E0h+var_280]
0x18000aeb5  test    rbx, rbx
0x18000aeb8  jz      loc_18000AF52
0x18000aebe  lea     rcx, [rsp+2E0h+hObject]
0x18000aec3  mov     [rsp+2E0h+hObject], r13
0x18000aec8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000aecd  lea     rdx, [rsp+2E0h+hObject]; struct IStream **
0x18000aed2  mov     rcx, rbx; struct IStream *
0x18000aed5  call    ?MakeImageStreamOpaque@@YAJPEAUIStream@@PEAPEAU1@@Z; MakeImageStreamOpaque(IStream *,IStream * *)
0x18000aeda  mov     edi, eax
0x18000aedc  test    eax, eax
0x18000aede  js      short loc_18000AF48
0x18000aee0  mov     rax, [rsp+2E0h+hObject]
0x18000aee5  mov     rcx, rsi
0x18000aee8  mov     [rsp+2E0h+var_2B8], rax
0x18000aeed  call    ?SaveStreamToSystemDataFolder@@YAJPEAXW4SYSTEM_DATA_FOLDER_USER_ACCESS@@W4SYSTEM_DATA_FOLDER_FLAGS@@PEBG3PEAUIStream@@W4SAVE_STREAM_MODE@@PEAPEAG@Z; SaveStreamToSystemDataFolder(void *,SYSTEM_DATA_FOLDER_USER_ACCESS,SYSTEM_DATA_FOLDER_FLAGS,ushort const *,ushort const *,IStream *,SAVE_STREAM_MODE,ushort * *)
0x18000aef2  mov     edi, eax
0x18000aef4  test    eax, eax
0x18000aef6  js      short loc_18000AF48
0x18000aef8  lea     r9, [rbp+1E0h+pszPath]
0x18000aefc  mov     rcx, rsi
0x18000aeff  call    ?GetSystemDataFolderForUser@@YAJPEAXPEBGW4SYSTEM_DATA_FOLDER_USER_ACCESS@@PEAGI_N@Z; GetSystemDataFolderForUser(void *,ushort const *,SYSTEM_DATA_FOLDER_USER_ACCESS,ushort *,uint,bool)
0x18000af04  mov     edi, eax
0x18000af06  test    eax, eax
0x18000af08  js      short loc_18000AF48
0x18000af0a  lea     r8, pszMore; "background.png"
0x18000af11  mov     edx, 104h; cchPath
0x18000af16  lea     rcx, [rbp+1E0h+pszPath]; pszPath
0x18000af1a  call    cs:__imp_PathCchAppend
0x18000af20  mov     edi, eax
0x18000af22  test    eax, eax
0x18000af24  js      short loc_18000AF48
0x18000af26  lea     rax, [rbp+1E0h+pszPath]
0x18000af2a  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000af2e  inc     r9
0x18000af31  cmp     [rax+r9*2], r13w
0x18000af36  jnz     short loc_18000AF2E
0x18000af38  lea     r8, [rbp+1E0h+pszPath]
0x18000af3c  mov     [rsp+2E0h+var_2B8], r12
0x18000af41  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18000af46  mov     edi, eax
0x18000af48  lea     rcx, [rsp+2E0h+hObject]
0x18000af4d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000af52  mov     rcx, [rsp+2E0h+pInit]; pv
0x18000af57  call    cs:__imp_CoTaskMemFree
0x18000af5d  lea     rcx, [rsp+2E0h+var_280]
0x18000af62  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000af67  lea     rcx, [rsp+2E0h+var_2A0]
0x18000af6c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000af71  mov     eax, edi
0x18000af73  mov     rcx, [rbp+1E0h+var_50]
0x18000af7a  xor     rcx, rsp; StackCookie
0x18000af7d  call    __security_check_cookie
0x18000af82  add     rsp, 2A8h
0x18000af89  pop     r15
0x18000af8b  pop     r14
0x18000af8d  pop     r13
0x18000af8f  pop     r12
0x18000af91  pop     rdi
0x18000af92  pop     rsi
0x18000af93  pop     rbx
0x18000af94  pop     rbp
0x18000af95  retn
```
