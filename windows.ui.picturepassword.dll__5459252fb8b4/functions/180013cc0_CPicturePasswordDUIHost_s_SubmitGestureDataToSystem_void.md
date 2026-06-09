# CPicturePasswordDUIHost::s_SubmitGestureDataToSystem(void *)

- ea: `0x180013cc0`
- end: `0x180013f58`
- name: `?s_SubmitGestureDataToSystem@CPicturePasswordDUIHost@@KAKPEAX@Z`
- size: `664`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x1800043a4`
- `0x18000a67c`
- `0x180011b00`
- `0x1800136a8`
- `0x180013860`
- `0x180013b88`
- `0x180013cc0`
- `0x1800185b4`
- `0x1800189c4`
- `0x18001d3f0`
- `0x18001f010`

## import_xrefs

- `SHCORE!IStream_Reset` at `0x180013dee`
- `SHCORE!IStream_Reset` at `0x180013e43`
- `SHCORE!IStream_Reset` at `0x180013dee`
- `SHCORE!IStream_Reset` at `0x180013e43`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180013d73`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180013d73`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180013cdb`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180013cdb`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180013f1b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180013f1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013f0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013f0c`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180013ecb`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180013ecb`

## pseudocode

```c
__int64 __fastcall CPicturePasswordDUIHost::s_SubmitGestureDataToSystem(char *a1)
{
  HRESULT v2; // ebx
  unsigned __int64 v3; // r9
  const unsigned __int8 *v4; // r8
  const unsigned __int8 *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rdx
  __int64 v8; // rcx
  ULONG (__stdcall *Release)(IUnknown *); // rax
  IStream *v10; // rdx
  DWORD dwAuthnLevel[2]; // [rsp+20h] [rbp-60h]
  LPCWSTR lpNewFileName[2]; // [rsp+40h] [rbp-40h] BYREF
  __int64 v14; // [rsp+50h] [rbp-30h]
  LPCWSTR lpExistingFileName; // [rsp+60h] [rbp-20h] BYREF
  __int64 v16; // [rsp+68h] [rbp-18h]
  __int64 v17; // [rsp+70h] [rbp-10h]
  unsigned int v18; // [rsp+B0h] [rbp+30h] BYREF
  IStream *pstm; // [rsp+B8h] [rbp+38h] BYREF
  IUnknown *pProxy; // [rsp+C0h] [rbp+40h] BYREF
  LPVOID pv; // [rsp+C8h] [rbp+48h] BYREF

  v2 = CoInitializeEx(0, 2u);
  if ( v2 >= 0 )
  {
    v3 = *((_QWORD *)a1 + 9);
    v4 = (const unsigned __int8 *)*((_QWORD *)a1 + 8);
    v5 = (const unsigned __int8 *)*((_QWORD *)a1 + 4);
    v6 = 5LL * *((_QWORD *)a1 + 5);
    pv = 0;
    pstm = 0;
    v2 = PackageEnrollmentPayload(v5, 4 * v6, v4, v3, (unsigned __int8 **)&pv, (unsigned __int64 *)&pstm);
    if ( v2 >= 0 )
    {
      pProxy = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&pProxy);
      v2 = CoCreateInstanceAsSystem(v8, v7, &pProxy);
      if ( v2 >= 0 )
      {
        v2 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, 0, 0, 3u, 0, 0);
        if ( v2 >= 0 )
        {
          v18 = 0;
          v2 = ULongLongToULong((unsigned __int64)pstm, &v18);
          if ( v2 >= 0 )
          {
            if ( *((_QWORD *)a1 + 13) )
            {
              pstm = 0;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&pstm);
              v2 = -2147467259;
              pstm = 0;
              if ( *((_QWORD *)a1 + 13) )
              {
                v2 = CMarshaledInterface::_Unmarshal(
                       (CMarshaledInterface *)(a1 + 104),
                       &GUID_0000000c_0000_0000_c000_000000000046,
                       (void **)&pstm,
                       1);
                if ( v2 >= 0 )
                {
                  v2 = IStream_Reset(pstm);
                  if ( v2 >= 0 )
                  {
                    *(_QWORD *)dwAuthnLevel = *((_QWORD *)a1 + 10);
                    Release = pProxy->lpVtbl[1].Release;
                    *(_OWORD *)lpNewFileName = *(_OWORD *)(a1 + 88);
                    v2 = ((__int64 (__fastcall *)(IUnknown *, LPVOID, _QWORD, IStream *, _QWORD, LPCWSTR *))Release)(
                           pProxy,
                           pv,
                           v18,
                           pstm,
                           *(_QWORD *)dwAuthnLevel,
                           lpNewFileName);
                    if ( v2 >= 0 )
                    {
                      IStream_Reset(pstm);
                      if ( (int)CPicturePasswordDUIHost::s_SaveImage(pstm, v10) >= 0 )
                      {
                        lpExistingFileName = 0;
                        v16 = 0;
                        v17 = 0;
                        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&lpExistingFileName);
                        v16 = -1;
                        v17 = -1;
                        if ( (int)CPicturePasswordDUIHost::s_GetFilePath(
                                    L"Cloud.jpg",
                                    (unsigned __int16 **)&lpExistingFileName) >= 0 )
                        {
                          lpNewFileName[0] = 0;
                          lpNewFileName[1] = 0;
                          v14 = 0;
                          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)lpNewFileName);
                          lpNewFileName[1] = (LPCWSTR)-1LL;
                          v14 = -1;
                          if ( (int)CPicturePasswordDUIHost::s_GetFilePath(
                                      L"Local.jpg",
                                      (unsigned __int16 **)lpNewFileName) >= 0 )
                            CopyFileW(lpExistingFileName, lpNewFileName[0], 0);
                          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)lpNewFileName);
                        }
                        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&lpExistingFileName);
                      }
                    }
                  }
                }
              }
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&pstm);
            }
            else
            {
              v2 = ((__int64 (__fastcall *)(IUnknown *, LPVOID, _QWORD))pProxy->lpVtbl[2].QueryInterface)(
                     pProxy,
                     pv,
                     v18);
            }
          }
        }
      }
      CoTaskMemFree(pv);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&pProxy);
    }
    CoUninitialize();
  }
  CPrivateNotificationWindow::PostNotification(*((CPrivateNotificationWindow **)a1 + 2), 0x405u, 0, v2);
  (**(void (__fastcall ***)(char *, __int64))a1)(a1, 1);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180013cc0  push    rbp
0x180013cc2  push    rbx
0x180013cc3  push    rsi
0x180013cc4  push    rdi
0x180013cc5  push    r15
0x180013cc7  mov     rbp, rsp
0x180013cca  sub     rsp, 80h
0x180013cd1  mov     rdi, rcx
0x180013cd4  mov     edx, 2; dwCoInit
0x180013cd9  xor     ecx, ecx; pvReserved
0x180013cdb  call    cs:__imp_CoInitializeEx
0x180013ce1  xor     r15d, r15d
0x180013ce4  mov     ebx, eax
0x180013ce6  test    eax, eax
0x180013ce8  js      loc_180013F21
0x180013cee  mov     rax, [rdi+28h]
0x180013cf2  mov     r9, [rdi+48h]; unsigned __int64
0x180013cf6  mov     r8, [rdi+40h]; unsigned __int8 *
0x180013cfa  mov     rcx, [rdi+20h]; Src
0x180013cfe  lea     rdx, [rax+rax*4]
0x180013d02  mov     [rbp+pv], r15
0x180013d06  lea     rax, [rbp+pstm]
0x180013d0a  shl     rdx, 2; Size
0x180013d0e  mov     qword ptr [rsp+80h+dwImpLevel], rax; unsigned __int64 *
0x180013d13  lea     rax, [rbp+pv]
0x180013d17  mov     qword ptr [rsp+80h+dwAuthnLevel], rax; unsigned __int8 **
0x180013d1c  mov     [rbp+pstm], r15
0x180013d20  call    ?PackageEnrollmentPayload@@YAJPEBE_K01PEAPEAEPEA_K@Z; PackageEnrollmentPayload(uchar const *,unsigned __int64,uchar const *,unsigned __int64,uchar * *,unsigned __int64 *)
0x180013d25  mov     ebx, eax
0x180013d27  test    eax, eax
0x180013d29  js      loc_180013F1B
0x180013d2f  lea     rcx, [rbp+pProxy]
0x180013d33  mov     [rbp+pProxy], r15
0x180013d37  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180013d3c  lea     r8, [rbp+pProxy]
0x180013d40  call    CoCreateInstanceAsSystem
0x180013d45  mov     ebx, eax
0x180013d47  test    eax, eax
0x180013d49  js      loc_180013F08
0x180013d4f  mov     rcx, [rbp+pProxy]; pProxy
0x180013d53  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x180013d56  mov     [rsp+80h+dwCapabilities], r15d; dwCapabilities
0x180013d5b  mov     r8d, edx; dwAuthzSvc
0x180013d5e  mov     [rsp+80h+pAuthInfo], r15; pAuthInfo
0x180013d63  xor     r9d, r9d; pServerPrincName
0x180013d66  mov     [rsp+80h+dwImpLevel], 3; dwImpLevel
0x180013d6e  mov     [rsp+80h+dwAuthnLevel], r15d; dwAuthnLevel
0x180013d73  call    cs:__imp_CoSetProxyBlanket
0x180013d79  mov     ebx, eax
0x180013d7b  test    eax, eax
0x180013d7d  js      loc_180013F08
0x180013d83  mov     rcx, [rbp+pstm]; unsigned __int64
0x180013d87  lea     rdx, [rbp+arg_0]; unsigned int *
0x180013d8b  mov     [rbp+arg_0], r15d
0x180013d8f  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180013d94  mov     ebx, eax
0x180013d96  test    eax, eax
0x180013d98  js      loc_180013F08
0x180013d9e  lea     rsi, [rdi+68h]
0x180013da2  cmp     [rsi], r15
0x180013da5  jz      loc_180013EEE
0x180013dab  lea     rcx, [rbp+pstm]
0x180013daf  mov     [rbp+pstm], r15
0x180013db3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180013db8  mov     ebx, 80004005h
0x180013dbd  mov     [rbp+pstm], r15
0x180013dc1  cmp     [rsi], r15
0x180013dc4  jz      loc_180013EE3
0x180013dca  mov     r9b, 1; bool
0x180013dcd  lea     r8, [rbp+pstm]; void **
0x180013dd1  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046; struct _GUID *
0x180013dd8  mov     rcx, rsi; this
0x180013ddb  call    ?_Unmarshal@CMarshaledInterface@@AEAAJAEBU_GUID@@PEAPEAX_N@Z; CMarshaledInterface::_Unmarshal(_GUID const &,void * *,bool)
0x180013de0  mov     ebx, eax
0x180013de2  test    eax, eax
0x180013de4  js      loc_180013EE3
0x180013dea  mov     rcx, [rbp+pstm]; pstm
0x180013dee  call    cs:__imp_IStream_Reset
0x180013df4  mov     ebx, eax
0x180013df6  test    eax, eax
0x180013df8  js      loc_180013EE3
0x180013dfe  mov     rdx, [rdi+50h]
0x180013e02  lea     r8, [rbp+lpNewFileName]
0x180013e06  mov     rcx, [rbp+pProxy]
0x180013e0a  movups  xmm0, xmmword ptr [rdi+58h]
0x180013e0e  mov     r9, [rbp+pstm]
0x180013e12  mov     qword ptr [rsp+80h+dwImpLevel], r8
0x180013e17  mov     rax, [rcx]
0x180013e1a  mov     r8d, [rbp+arg_0]
0x180013e1e  mov     qword ptr [rsp+80h+dwAuthnLevel], rdx
0x180013e23  mov     rdx, [rbp+pv]
0x180013e27  mov     rax, [rax+28h]
0x180013e2b  movdqu  xmmword ptr [rbp+lpNewFileName], xmm0
0x180013e30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e35  mov     ebx, eax
0x180013e37  test    eax, eax
0x180013e39  js      loc_180013EE3
0x180013e3f  mov     rcx, [rbp+pstm]; pstm
0x180013e43  call    cs:__imp_IStream_Reset
0x180013e49  mov     rcx, [rbp+pstm]; pstm
0x180013e4d  call    ?s_SaveImage@CPicturePasswordDUIHost@@KAJPEAUIStream@@PEBG@Z; CPicturePasswordDUIHost::s_SaveImage(IStream *,ushort const *)
0x180013e52  test    eax, eax
0x180013e54  js      loc_180013EE3
0x180013e5a  lea     rcx, [rbp+lpExistingFileName]
0x180013e5e  mov     [rbp+lpExistingFileName], r15
0x180013e62  mov     [rbp+var_18], r15
0x180013e66  mov     [rbp+var_10], r15
0x180013e6a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180013e6f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180013e73  lea     rdx, [rbp+lpExistingFileName]; unsigned __int16 **
0x180013e77  lea     rcx, aCloudJpg; "Cloud.jpg"
0x180013e7e  mov     [rbp+var_18], rsi
0x180013e82  mov     [rbp+var_10], rsi
0x180013e86  call    ?s_GetFilePath@CPicturePasswordDUIHost@@KAJPEBGPEAPEAG@Z; CPicturePasswordDUIHost::s_GetFilePath(ushort const *,ushort * *)
0x180013e8b  test    eax, eax
0x180013e8d  js      short loc_180013EDA
0x180013e8f  lea     rcx, [rbp+lpNewFileName]
0x180013e93  mov     [rbp+lpNewFileName], r15
0x180013e97  mov     [rbp+lpNewFileName+8], r15
0x180013e9b  mov     [rbp+var_30], r15
0x180013e9f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180013ea4  lea     rdx, [rbp+lpNewFileName]; unsigned __int16 **
0x180013ea8  mov     [rbp+lpNewFileName+8], rsi
0x180013eac  lea     rcx, aLocalJpg; "Local.jpg"
0x180013eb3  mov     [rbp+var_30], rsi
0x180013eb7  call    ?s_GetFilePath@CPicturePasswordDUIHost@@KAJPEBGPEAPEAG@Z; CPicturePasswordDUIHost::s_GetFilePath(ushort const *,ushort * *)
0x180013ebc  test    eax, eax
0x180013ebe  js      short loc_180013ED1
0x180013ec0  mov     rdx, [rbp+lpNewFileName]; lpNewFileName
0x180013ec4  xor     r8d, r8d; bFailIfExists
0x180013ec7  mov     rcx, [rbp+lpExistingFileName]; lpExistingFileName
0x180013ecb  call    cs:__imp_CopyFileW
0x180013ed1  lea     rcx, [rbp+lpNewFileName]
0x180013ed5  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180013eda  lea     rcx, [rbp+lpExistingFileName]
0x180013ede  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180013ee3  lea     rcx, [rbp+pstm]
0x180013ee7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180013eec  jmp     short loc_180013F08
0x180013eee  mov     rcx, [rbp+pProxy]
0x180013ef2  mov     r8d, [rbp+arg_0]
0x180013ef6  mov     rdx, [rbp+pv]
0x180013efa  mov     rax, [rcx]
0x180013efd  mov     rax, [rax+30h]
0x180013f01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f06  mov     ebx, eax
0x180013f08  mov     rcx, [rbp+pv]; pv
0x180013f0c  call    cs:__imp_CoTaskMemFree
0x180013f12  lea     rcx, [rbp+pProxy]
0x180013f16  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180013f1b  call    cs:__imp_CoUninitialize
0x180013f21  mov     rcx, [rdi+10h]; this
0x180013f25  xor     r8d, r8d; unsigned __int64
0x180013f28  movsxd  r9, ebx; __int64
0x180013f2b  mov     edx, 405h; unsigned int
0x180013f30  call    ?PostNotification@CPrivateNotificationWindow@@QEAA_NI_K_J@Z; CPrivateNotificationWindow::PostNotification(uint,unsigned __int64,__int64)
0x180013f35  mov     rax, [rdi]
0x180013f38  mov     edx, 1
0x180013f3d  mov     rcx, rdi
0x180013f40  mov     rax, [rax]
0x180013f43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f48  mov     eax, ebx
0x180013f4a  add     rsp, 80h
0x180013f51  pop     r15
0x180013f53  pop     rdi
0x180013f54  pop     rsi
0x180013f55  pop     rbx
0x180013f56  pop     rbp
0x180013f57  retn
```
