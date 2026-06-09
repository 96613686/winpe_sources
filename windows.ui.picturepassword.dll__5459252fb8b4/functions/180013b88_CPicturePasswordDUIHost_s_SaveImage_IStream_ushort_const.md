# CPicturePasswordDUIHost::s_SaveImage(IStream *,ushort const *)

- ea: `0x180013b88`
- end: `0x180013cb0`
- name: `?s_SaveImage@CPicturePasswordDUIHost@@KAJPEAUIStream@@PEBG@Z`
- size: `296`
- prototype: `__int64 __fastcall(struct IStream *pstm, IStream *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180013cc0`

## callees

- `0x1800043a4`
- `0x180011b00`
- `0x180013860`
- `0x180013b88`
- `0x18001f010`

## import_xrefs

- `SHCORE!IStream_Size` at `0x180013c3a`
- `SHCORE!IStream_Size` at `0x180013c3a`
- `SHCORE!IStream_Reset` at `0x180013c86`
- `SHCORE!IStream_Reset` at `0x180013c86`
- `SHCORE!SHCreateStreamOnFileEx` at `0x180013c1f`
- `SHCORE!SHCreateStreamOnFileEx` at `0x180013c1f`

## pseudocode

```c
__int64 __fastcall CPicturePasswordDUIHost::s_SaveImage(struct IStream *pstm, IStream *a2)
{
  HRESULT FilePath; // ebx
  LPCWSTR pszFile; // [rsp+30h] [rbp-20h] BYREF
  __int64 v6; // [rsp+38h] [rbp-18h]
  __int64 v7; // [rsp+40h] [rbp-10h]
  IStream *ppstm; // [rsp+68h] [rbp+18h] BYREF
  ULARGE_INTEGER pui; // [rsp+70h] [rbp+20h] BYREF

  ppstm = a2;
  pszFile = 0;
  v6 = 0;
  v7 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&pszFile);
  v6 = -1;
  v7 = -1;
  FilePath = CPicturePasswordDUIHost::s_GetFilePath(L"Cloud.jpg", (unsigned __int16 **)&pszFile);
  if ( FilePath >= 0 )
  {
    ppstm = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&ppstm);
    FilePath = SHCreateStreamOnFileEx(pszFile, 0x1002u, 0x80u, 1, 0, &ppstm);
    if ( FilePath >= 0 )
    {
      pui.QuadPart = 0;
      FilePath = IStream_Size(pstm, &pui);
      if ( FilePath >= 0 )
      {
        FilePath = (*(__int64 (__fastcall **)(struct IStream *, IStream *, ULARGE_INTEGER, _QWORD, _QWORD))(*(_QWORD *)pstm + 56LL))(
                     pstm,
                     ppstm,
                     pui,
                     0,
                     0);
        if ( FilePath >= 0 )
          FilePath = (*(__int64 (__fastcall **)(IStream *, _QWORD))(*(_QWORD *)ppstm + 64LL))(ppstm, 0);
        IStream_Reset(pstm);
      }
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&ppstm);
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&pszFile);
  return (unsigned int)FilePath;
}

```

## disassembly

```asm
0x180013b88  mov     [rsp-8+arg_0], rbx
0x180013b8d  mov     [rsp-8+arg_18], rdi
0x180013b92  mov     [rsp-8+arg_8], rdx
0x180013b97  push    rbp
0x180013b98  mov     rbp, rsp
0x180013b9b  sub     rsp, 50h
0x180013b9f  mov     rdi, rcx
0x180013ba2  mov     [rbp+pszFile], 0
0x180013baa  lea     rcx, [rbp+pszFile]
0x180013bae  mov     [rbp+var_18], 0
0x180013bb6  mov     [rbp+var_10], 0
0x180013bbe  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180013bc3  or      rax, 0FFFFFFFFFFFFFFFFh
0x180013bc7  lea     rdx, [rbp+pszFile]; unsigned __int16 **
0x180013bcb  lea     rcx, aCloudJpg; "Cloud.jpg"
0x180013bd2  mov     [rbp+var_18], rax
0x180013bd6  mov     [rbp+var_10], rax
0x180013bda  call    ?s_GetFilePath@CPicturePasswordDUIHost@@KAJPEBGPEAPEAG@Z; CPicturePasswordDUIHost::s_GetFilePath(ushort const *,ushort * *)
0x180013bdf  mov     ebx, eax
0x180013be1  test    eax, eax
0x180013be3  js      loc_180013C95
0x180013be9  lea     rcx, [rbp+arg_8]
0x180013bed  mov     [rbp+arg_8], 0
0x180013bf5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180013bfa  mov     rcx, [rbp+pszFile]; pszFile
0x180013bfe  lea     rax, [rbp+arg_8]
0x180013c02  mov     r9d, 1; fCreate
0x180013c08  mov     [rsp+50h+ppstm], rax; ppstm
0x180013c0d  mov     edx, 1002h; grfMode
0x180013c12  mov     [rsp+50h+pstmTemplate], 0; pstmTemplate
0x180013c1b  lea     r8d, [r9+7Fh]; dwAttributes
0x180013c1f  call    cs:__imp_SHCreateStreamOnFileEx
0x180013c25  mov     ebx, eax
0x180013c27  test    eax, eax
0x180013c29  js      short loc_180013C8C
0x180013c2b  lea     rdx, [rbp+pui]; pui
0x180013c2f  mov     qword ptr [rbp+pui], 0
0x180013c37  mov     rcx, rdi; pstm
0x180013c3a  call    cs:__imp_IStream_Size
0x180013c40  mov     ebx, eax
0x180013c42  test    eax, eax
0x180013c44  js      short loc_180013C8C
0x180013c46  mov     rax, [rdi]
0x180013c49  xor     r9d, r9d
0x180013c4c  mov     r8, qword ptr [rbp+pui]
0x180013c50  mov     rcx, rdi
0x180013c53  mov     rdx, [rbp+arg_8]
0x180013c57  mov     [rsp+50h+pstmTemplate], 0
0x180013c60  mov     rax, [rax+38h]
0x180013c64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c69  mov     ebx, eax
0x180013c6b  test    eax, eax
0x180013c6d  js      short loc_180013C83
0x180013c6f  mov     rcx, [rbp+arg_8]
0x180013c73  xor     edx, edx
0x180013c75  mov     rax, [rcx]
0x180013c78  mov     rax, [rax+40h]
0x180013c7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c81  mov     ebx, eax
0x180013c83  mov     rcx, rdi; pstm
0x180013c86  call    cs:__imp_IStream_Reset
0x180013c8c  lea     rcx, [rbp+arg_8]
0x180013c90  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180013c95  lea     rcx, [rbp+pszFile]
0x180013c99  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180013c9e  mov     rdi, [rsp+50h+arg_18]
0x180013ca3  mov     eax, ebx
0x180013ca5  mov     rbx, [rsp+50h+arg_0]
0x180013caa  add     rsp, 50h
0x180013cae  pop     rbp
0x180013caf  retn
```
