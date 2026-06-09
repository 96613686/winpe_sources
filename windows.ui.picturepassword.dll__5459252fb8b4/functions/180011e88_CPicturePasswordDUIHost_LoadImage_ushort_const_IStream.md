# CPicturePasswordDUIHost::_LoadImage(ushort const *,IStream * *)

- ea: `0x180011e88`
- end: `0x180011f51`
- name: `?_LoadImage@CPicturePasswordDUIHost@@IEAAJPEBGPEAPEAUIStream@@@Z`
- size: `201`
- prototype: `__int64 __fastcall(CPicturePasswordDUIHost *this, const unsigned __int16 *, struct IStream **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000ee20`
- `0x1800104d0`

## callees

- `0x1800043a4`
- `0x18000ed0c`
- `0x180011b00`
- `0x180011e88`
- `0x180013860`

## import_xrefs

- `SHCORE!IStream_Reset` at `0x180011f27`
- `SHCORE!IStream_Reset` at `0x180011f27`
- `SHCORE!SHCreateStreamOnFileW` at `0x180011f06`
- `SHCORE!SHCreateStreamOnFileW` at `0x180011f06`

## pseudocode

```c
__int64 __fastcall CPicturePasswordDUIHost::_LoadImage(
        CPicturePasswordDUIHost *this,
        const unsigned __int16 *a2,
        struct IStream **a3)
{
  HRESULT FilePath; // ebx
  LPCWSTR pszFile; // [rsp+20h] [rbp-20h] BYREF
  __int64 v8; // [rsp+28h] [rbp-18h]
  __int64 v9; // [rsp+30h] [rbp-10h]
  IStream *ppstm; // [rsp+50h] [rbp+10h] BYREF

  ppstm = this;
  *a3 = 0;
  pszFile = 0;
  v8 = 0;
  v9 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&pszFile);
  v8 = -1;
  v9 = -1;
  FilePath = CPicturePasswordDUIHost::s_GetFilePath(a2, (unsigned __int16 **)&pszFile);
  if ( FilePath >= 0 )
  {
    ppstm = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppstm);
    FilePath = SHCreateStreamOnFileW(pszFile, 0, &ppstm);
    if ( FilePath >= 0 )
    {
      FilePath = MakeMemStreamCopyOfStream(ppstm, a3);
      if ( FilePath >= 0 )
        IStream_Reset(*a3);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppstm);
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&pszFile);
  return (unsigned int)FilePath;
}

```

## disassembly

```asm
0x180011e88  mov     [rsp-8+arg_8], rbx
0x180011e8d  mov     [rsp-8+arg_10], rdi
0x180011e92  mov     [rsp-8+ppstm], rcx
0x180011e97  push    rbp
0x180011e98  mov     rbp, rsp
0x180011e9b  sub     rsp, 40h
0x180011e9f  lea     rcx, [rbp+pszFile]
0x180011ea3  mov     qword ptr [r8], 0
0x180011eaa  mov     rdi, r8
0x180011ead  mov     [rbp+pszFile], 0
0x180011eb5  mov     rbx, rdx
0x180011eb8  mov     [rbp+var_18], 0
0x180011ec0  mov     [rbp+var_10], 0
0x180011ec8  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180011ecd  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011ed1  lea     rdx, [rbp+pszFile]; unsigned __int16 **
0x180011ed5  mov     rcx, rbx; pszMore
0x180011ed8  mov     [rbp+var_18], rax
0x180011edc  mov     [rbp+var_10], rax
0x180011ee0  call    ?s_GetFilePath@CPicturePasswordDUIHost@@KAJPEBGPEAPEAG@Z; CPicturePasswordDUIHost::s_GetFilePath(ushort const *,ushort * *)
0x180011ee5  mov     ebx, eax
0x180011ee7  test    eax, eax
0x180011ee9  js      short loc_180011F36
0x180011eeb  lea     rcx, [rbp+ppstm]
0x180011eef  mov     [rbp+ppstm], 0
0x180011ef7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180011efc  mov     rcx, [rbp+pszFile]; pszFile
0x180011f00  lea     r8, [rbp+ppstm]; ppstm
0x180011f04  xor     edx, edx; grfMode
0x180011f06  call    cs:__imp_SHCreateStreamOnFileW
0x180011f0c  mov     ebx, eax
0x180011f0e  test    eax, eax
0x180011f10  js      short loc_180011F2D
0x180011f12  mov     rcx, [rbp+ppstm]; pstmFrom
0x180011f16  mov     rdx, rdi; struct IStream **
0x180011f19  call    ?MakeMemStreamCopyOfStream@@YAJPEAUIStream@@PEAPEAU1@@Z; MakeMemStreamCopyOfStream(IStream *,IStream * *)
0x180011f1e  mov     ebx, eax
0x180011f20  test    eax, eax
0x180011f22  js      short loc_180011F2D
0x180011f24  mov     rcx, [rdi]; pstm
0x180011f27  call    cs:__imp_IStream_Reset
0x180011f2d  lea     rcx, [rbp+ppstm]
0x180011f31  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180011f36  lea     rcx, [rbp+pszFile]
0x180011f3a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180011f3f  mov     rdi, [rsp+40h+arg_10]
0x180011f44  mov     eax, ebx
0x180011f46  mov     rbx, [rsp+40h+arg_8]
0x180011f4b  add     rsp, 40h
0x180011f4f  pop     rbp
0x180011f50  retn
```
